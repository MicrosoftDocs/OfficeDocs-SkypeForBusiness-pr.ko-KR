---
title: 2013에서 여러 긴급 비즈니스용 Skype
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 이 항목을 읽고 응급 번호를 여러 개 구성하는 방법을 비즈니스용 Skype 서버.
ms.openlocfilehash: e0a12bb63578e5070a079b6ab4561d67255f7199a0042066467fb40eafb54637
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54300344"
---
# <a name="configure-multiple-emergency-numbers-in-skype-for-business"></a>2013에서 여러 긴급 비즈니스용 Skype

이 항목을 읽고 응급 번호를 여러 개 구성하는 방법을 비즈니스용 Skype 서버.

비즈니스용 Skype 서버 클라이언트에 대해 여러 긴급 번호를 지원할 수 있습니다. 여러 긴급 번호는 2016년 6월 누적 업데이트에 도입된 새로운 기능입니다. 여러 긴급 번호를 지원하도록 환경을 구성하기 전에 에서 여러 긴급 [번호 계획을 비즈니스용 Skype 서버.](../../plan-your-deployment/enterprise-voice-solution/multiple-emergency-numbers.md)

> [!NOTE]
> 아직 2016년 11월 누적 업데이트로 업그레이드하지 않은 경우 [Updates to 비즈니스용 Skype 서버 2015를 참조하세요.](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015) 2016년 11월 누적 업데이트를 통해 지원 긴급 번호 수는 5에서 100으로 증가합니다.

## <a name="configure-multiple-emergency-numbers"></a>여러 긴급 번호 구성

여러 긴급 번호를 구성하기 위해 New-CsEmergencyNumber cmdlet을 사용하여 EmergencyNumbers 매개 변수를 [New-CsLocationPolicy 및 Set-CsLocationPolicy](/powershell/module/skype/new-cslocationpolicy?view=skype-ps) cmdlet과 함께 지정합니다. [](/powershell/module/skype/set-cslocationpolicy?view=skype-ps) 필요한 PSTN 사용 및 위치와 같은 모든 위치 정책 매개 변수에 대한 자세한 내용은 [Set-CsLocationPolicy 를 참조하세요.](/powershell/module/skype/set-cslocationpolicy?view=skype-ps)

다음 명령은 다음 cmdlet을 사용하여 전화 문자열 911이 있는 새 긴급 New-CsEmergency 만듭니다.

```powershell
> $a = New-CsEmergencyNumber -DialString 911
```

다음 명령은 Set-CsLocationPolicy cmdlet에 EmergencyNumbers 매개 변수를 지정하여 번호를 지정된 위치 정책에 연결합니다.

```powershell
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{add=$a}
```

다음 예에서는 단일 다이얼 마스크 112를 사용하여 긴급 번호를 생성합니다.

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112
```

다음 명령은 여러 개의 다이얼 마스크가 있는 긴급 번호를 만듭니다.

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999
```

다음 예에서는 여러 개의 다이얼 마스크가 있는 여러 긴급 번호를 추가한 다음 긴급 번호를 지정된 위치 정책에 연결합니다.

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999
> $b = New-CsEmergencyNumber -DialString 500 -DialMask 501;502
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{add=$a,$b}
```

다음 예에서는 911과 450을 모두 사용하는 의료 서비스 공급자에 대해 여러 긴급 번호를 구성합니다.

```powershell
> $a = New-CsEmergencyNumber -DialString 911
> $b = New-CsEmergencyNumber -DialString 450
> Set-CsLocationPolicy -Identity US-Hospital -EmergencyNumbers @{add=$a,$b}
```

다음 예에서는 런던 시에 대해 여러 긴급 번호를 구성합니다.

```powershell
> $a = New-CsEmergencyNumber -DialString 999 -DialMask 144
> $b = New-CsEmergencyNumber -DialString 112 -DialMask 911;117;118
> Set-CsLocationPolicy -Identity London -EmergencyNumbers @{add=$a,$b}
```

다음 예에서는 인도에 대해 여러 긴급 번호를 구성합니다.

```powershell
> $a = New-CsEmergencyNumber -DialString 100 -DialMask 911
> $b = New-CsEmergencyNumber -DialString 101
> $c = New-CsEmergencyNumber -DialString 102
> Set-CsLocationPolicy -Identity India -EmergencyNumbers @{add=$a,$b,$c}
```

다음 예에서는 Dial 문자열 911 및 Dial 마스크 112 및 999가 있는 기존 항목을 제거합니다.

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{remove=$a}
```