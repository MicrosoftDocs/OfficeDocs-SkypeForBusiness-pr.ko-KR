---
title: 비즈니스용 Skype에서 여러 응급 전화 번호 구성
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 2e869df0-5fdb-4e70-bd81-cb012556eb1a
description: 비즈니스용 Skype 서버에서 여러 응급 번호를 구성 하는 방법을 알아보려면이 항목을 읽어 보십시오.
ms.openlocfilehash: 81d3dbed919c936eb8a656d123f5c44e445044d7
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42027799"
---
# <a name="configure-multiple-emergency-numbers-in-skype-for-business"></a>비즈니스용 Skype에서 여러 응급 전화 번호 구성

비즈니스용 Skype 서버에서 여러 응급 번호를 구성 하는 방법을 알아보려면이 항목을 읽어 보십시오.

이제 비즈니스용 Skype 서버는 클라이언트에 대 한 여러 응급 전화 번호를 지원 합니다. 여러 응급 번호는 6 월 2016 누적 업데이트에 도입 된 새로운 기능입니다. 여러 응급 번호를 지원 하도록 환경을 구성 하기 전에 [비즈니스용 Skype 서버에서 여러 응급 번호에 대 한 요금제](../../plan-your-deployment/enterprise-voice-solution/multiple-emergency-numbers.md)를 읽어야 합니다.

> [!NOTE]
> 11 월 2016 누적 업데이트를 아직 업그레이드 하지 않은 경우 [비즈니스용 Skype 서버 2015 업데이트](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)를 참조 하세요. 11 월 2016 누적 업데이트를 사용 하는 경우, 지원 응급 번호의 수는 5에서 100로 증가 합니다.

## <a name="configure-multiple-emergency-numbers"></a>여러 응급 번호 구성

여러 응급 번호를 구성 하려면 CsEmergencyNumber cmdlet을 사용 하 여 EmergencyNumbers 매개 변수를 [새-cslocationpolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) 및 [Set-cslocationpolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps) cmdlet과 함께 지정 합니다. PSTN 사용 및 필수 위치와 같은 모든 위치 정책 매개 변수에 대 한 자세한 내용은 [Set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps)를 참조 하십시오.

다음 명령은 CsEmergency cmdlet을 사용 하 여 전화 걸기 문자열 911의 새 응급 번호를 만듭니다.

```powershell
> $a = New-CsEmergencyNumber -DialString 911
```

다음 명령은 Set-CsLocationPolicy cmdlet에 EmergencyNumbers 매개 변수를 지정 하 여 지정 된 위치 정책과 번호를 연결 합니다.

```powershell
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{add=$a}
```

다음 예에서 비상 번호는 하나의 다이얼 마스크로 만들어지며, 112:

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112
```

다음 명령은 전화 걸기 마스크가 여러 개인 비상 번호를 만듭니다.

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999
```

다음은 여러 개의 전화 걸기 마스크를 사용 하 여 여러 응급 번호를 추가한 다음, 비상 번호를 지정 된 위치 정책과 연결 하는 예입니다.

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999
> $b = New-CsEmergencyNumber -DialString 500 -DialMask 501;502
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{add=$a,$b}
```

다음 예에서는 911와 450를 모두 사용 하는 의료 보험 공급자에 대해 여러 응급 번호를 구성 합니다.

```powershell
> $a = New-CsEmergencyNumber -DialString 911
> $b = New-CsEmergencyNumber -DialString 450
> Set-CsLocationPolicy -Identity US-Hospital -EmergencyNumbers @{add=$a,$b}
```

다음 예에서는 런던의 구/군/시에 대해 여러 응급 전화 번호를 구성 합니다.

```powershell
> $a = New-CsEmergencyNumber -DialString 999 -DialMask 144
> $b = New-CsEmergencyNumber -DialString 112 -DialMask 911;117;118
> Set-CsLocationPolicy -Identity London -EmergencyNumbers @{add=$a,$b}
```

다음 예에서는 인도에 대해 여러 응급 번호를 구성 합니다.

```powershell
> $a = New-CsEmergencyNumber -DialString 100 -DialMask 911
> $b = New-CsEmergencyNumber -DialString 101
> $c = New-CsEmergencyNumber -DialString 102
> Set-CsLocationPolicy -Identity India -EmergencyNumbers @{add=$a,$b,$c}
```

다음 예에서는 Dial 문자열 911 및 다이얼 마스크 112 및 999의 기존 항목을 제거 합니다.

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{remove=$a}
```
