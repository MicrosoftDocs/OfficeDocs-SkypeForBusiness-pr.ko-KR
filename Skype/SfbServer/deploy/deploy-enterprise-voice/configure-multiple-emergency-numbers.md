---
title: 비즈니스용 Skype에서 여러 응급 번호 구성
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 2e869df0-5fdb-4e70-bd81-cb012556eb1a
description: 비즈니스용 Skype 서버에서 여러 응급 번호를 구성 하는 방법을 알아보려면이 항목을 참조 하세요.
ms.openlocfilehash: 0a2387576418aa2631095c46e970fdfac234ca4c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36197433"
---
# <a name="configure-multiple-emergency-numbers-in-skype-for-business"></a>비즈니스용 Skype에서 여러 응급 번호 구성

비즈니스용 Skype 서버에서 여러 응급 번호를 구성 하는 방법을 알아보려면이 항목을 참조 하세요.

이제 비즈니스용 Skype 서버에서 클라이언트에 대 한 여러 응급 번호를 지원 합니다. 여러 비상 번호는 6 월 2016 누적 업데이트에 도입 된 새로운 기능입니다. 여러 응급 번호를 지원 하도록 환경을 구성 하기 전에 [비즈니스용 Skype 서버에서 여러 응급 번호 요금제](../../plan-your-deployment/enterprise-voice-solution/multiple-emergency-numbers.md)를 읽어 보세요.

> [!NOTE]
> 11 월 2016 누적 업데이트로 아직 업그레이드 하지 않은 경우 비즈니스용 [Skype Server 2015 업데이트](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015)를 참조 하세요. 11 월 2016 누적 업데이트를 사용 하는 경우 지원 되는 응급 번호 수는 5에서 100로 증가 합니다. 

## <a name="configure-multiple-emergency-numbers"></a>여러 비상 전화 번호 구성

여러 비상 번호를 구성 하려면 CsEmergencyNumber cmdlet을 사용 하 여 [새-cslocationpolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) 및 [Set cslocationpolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps) cmdlet에 EmergencyNumbers 매개 변수를 지정 합니다. PSTN 사용 및 필수 위치와 같은 모든 위치 정책 매개 변수에 대 한 자세한 설명은 [Set CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps)를 참조 하세요.

다음 명령은 CsEmergency cmdlet을 사용 하 여 dial 문자열 911를 사용 하 여 새 비상 번호를 만듭니다.

```
> $a = New-CsEmergencyNumber -DialString 911 
```

다음 명령은 Set-CsLocationPolicy cmdlet에서 EmergencyNumbers 매개 변수를 지정 하 여 번호를 지정 된 위치 정책에 연결 합니다.

```
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{add=$a} 
```

다음 예제에서 비상 번호는 단일 다이얼 마스크로 생성 됩니다. 112:

```
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112 
```

다음 명령은 여러 다이얼 마스크가 있는 비상 번호를 만듭니다.

```
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999 
```

다음 예에서는 여러 개의 전화 접속 마스크를 사용 하 여 여러 응급 번호를 추가한 다음 비상 번호를 지정 된 위치 정책에 연결 합니다.

```
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999 
> $b = New-CsEmergencyNumber -DialString 500 -DialMask 501;502
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{add=$a,$b} 
```

다음 예에서는 911 및 450를 모두 사용 하는 의료 보험 제공자에 대해 여러 비상 번호를 구성 합니다. 

```
> $a = New-CsEmergencyNumber -DialString 911 
> $b = New-CsEmergencyNumber -DialString 450
> Set-CsLocationPolicy -Identity US-Hospital -EmergencyNumbers @{add=$a,$b}
```

다음 예에서는 London의 구/군/시에 대해 여러 비상 번호를 구성 합니다.

```
> $a = New-CsEmergencyNumber -DialString 999 -DialMask 144
> $b = New-CsEmergencyNumber -DialString 112 -DialMask 911;117;118
> Set-CsLocationPolicy -Identity London -EmergencyNumbers @{add=$a,$b}
```

다음 예에서는 인도에 대 한 여러 응급 번호를 구성 합니다.

```
> $a = New-CsEmergencyNumber -DialString 100 -DialMask 911
> $b = New-CsEmergencyNumber -DialString 101 
> $c = New-CsEmergencyNumber -DialString 102 
> Set-CsLocationPolicy -Identity India -EmergencyNumbers @{add=$a,$b,$c}
```

다음 예제에서는 Dial 문자열 911 및 다이얼 마스크 112 및 999이 있는 기존 항목을 제거 합니다.

```
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{remove=$a} 
```


