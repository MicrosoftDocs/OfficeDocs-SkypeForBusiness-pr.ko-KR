---
title: 비즈니스용 Skype에서 통화 파크 설정 구성
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
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 3bed9d09-8363-4fff-a220-f0f6d3a81241
description: 비즈니스용 Skype 서버에서 통화 파크 설정을 Enterprise Voice.
ms.openlocfilehash: 2380c9b505ceef6ac5f4bbe04996bfdf611de39c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804118"
---
# <a name="configure-call-park-settings-in-skype-for-business"></a>비즈니스용 Skype에서 통화 파크 설정 구성

비즈니스용 Skype 서버에서 통화 파크 설정을 Enterprise Voice.

기본 통화 파크 설정을 사용하지 않는 경우 사용자 지정할 수 있습니다. 통화 파크 응용 프로그램을 설치하면 전역 설정이 기본적으로 구성됩니다. 전역 설정을 수정할 수 있으며 사이트별 설정을 지정할 수도 있습니다. 새 사이트별 설정을 만들려면 **New-CsCpsConfiguration** cmdlet을 사용합니다. 기존 설정을 수정하려면 **Set-CsCpsConfiguration** cmdlet을 사용합니다.

> [!NOTE]
> 대기된 통화의 시간이 초과되고 되걸기가 실패하는 경우 최소한 대체 대상에서 사용할 **OnTimeoutURI** 옵션을 구성하는 것이 좋습니다.

**New-CsCpsConfiguration** cmdlet 또는 **Set-CsCpsConfiguration** cmdlet을 사용하여 다음 설정 중 원하는 항목을 구성합니다.


| **옵션**                     | **지정 내용**                                                                                                                                                                                                                                                                                                                   |
|:-------------------------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **CallPickupTimeoutThreshold** <br/> | 전화를 받았던 전화기에 벨이 다시 울릴 때까지 통화를 대기하고 있는 시간입니다.  <br/> hh:mm:ss 형식으로 시간, 분 및 초를 지정하여 값을 입력해야 합니다. 최소값은 10초이고 최대값은 10분입니다. 기본값은 00:01:30입니다.  <br/> |
| **EnableMusicOnHold** <br/>          | 통화를 대기하는 동안 전화를 건 사람에게 음악이 재생되는지 여부입니다.  <br/> 값은 True 또는 False이고, 기본값은 True입니다.  <br/>                                                                                                                                                                                                                 |
| **MaxCallPickupAttempts** <br/>      | 대기된 통화를 **OnTimeoutURI** 에 대해 지정된 대체 URI(Uniform Resource Identifier)에 전달할 때까지 해당 통화가 전화기에서 다시 울리는 횟수입니다. 기본값은 1입니다.<br/>                                                                                                                         |
| **OnTimeoutURI** <br/>               | **MaxCallPickupAttempts** 가 초과될 때 응답하지 않은 대기된 통화를 경로 지정할 사용자 또는 응답 그룹의 SIP 주소입니다. <br/> 값은 문자열 sip:로 시작하는 SIP URI여야 합니다(예: sip:bob@contoso.com). 기본적으로는 전달 주소가 지정되지 않습니다.<br/>                                                   |

### <a name="to-configure-call-park-settings"></a>통화 파크 설정을 구성하려면

1. 비즈니스용 Skype 서버 관리 셸 시작: **시작,** 모든 **프로그램,** 비즈니스용 **Skype 2015,** 비즈니스용 Skype 서버 관리 셸을 **클릭합니다.**

2. 을 실행합니다.

   ```powershell
   New-CsCpsConfiguration -Identity site:<sitename to apply settings> [-CallPickupTimeoutThreshold <hh:mm:ss>] -[EnableMusicOnHold <$true | $false>] [-MaxCallPickupAttempts <number of rings>] [-OnTimeoutURI sip:<sip URI for routing unanswered call>]
   ```

   > [!TIP]
   > **Get-CsSite** cmdlet을 사용하여 사이트를 식별합니다. 자세한 내용은 비즈니스용 Skype 서버 관리 셸 설명서를 참조하십시오.

    예제:

   ```powershell
   New-CsCpsConfiguration -Identity site:Redmond1 -CallPickupTimeoutThreshold 00:01:00 -EnableMusicOnHold $false -MaxCallPickupAttempts 2 -OnTimeoutURI sip:bob@contoso.com
   ```

## <a name="see-also"></a>참고 항목

[비즈니스용 통화 파킹 음악 사용자 지정 inSkype for Business 2015](customize-call-park-music-on-hold.md)

[New-CsCpsConfiguration](https://docs.microsoft.com/powershell/module/skype/new-cscpsconfiguration?view=skype-ps)

[Set-CsCpsConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscpsconfiguration?view=skype-ps)

[Get-CsSite](https://docs.microsoft.com/powershell/module/skype/get-cssite?view=skype-ps)
