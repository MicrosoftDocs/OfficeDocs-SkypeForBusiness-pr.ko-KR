---
title: 비즈니스용 Skype에서 통화 공원 설정 구성
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 3bed9d09-8363-4fff-a220-f0f6d3a81241
description: 비즈니스용 Skype Server Enterprise Voice에서 통화 공원 설정을 수정 하세요.
ms.openlocfilehash: df7334734784a773abd1df66a7544c3141a9aec9
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233940"
---
# <a name="configure-call-park-settings-in-skype-for-business"></a>비즈니스용 Skype에서 통화 공원 설정 구성

비즈니스용 Skype Server Enterprise Voice에서 통화 공원 설정을 수정 하세요.

기본 통화 공원 설정을 사용 하지 않으려는 경우에는 사용자 지정할 수 있습니다. 통화 공원 응용 프로그램을 설치할 때 전역 설정이 기본적으로 구성 됩니다. 전역 설정을 수정할 수 있으며 사이트 관련 설정을 지정할 수도 있습니다. 새 사이트 관련 설정을 만들려면 **CsCpsConfiguration** cmdlet을 사용 합니다. **Set-CsCpsConfiguration** cmdlet을 사용 하 여 기존 설정을 수정 합니다.

> [!NOTE]
> 최소한 파킹 된 통화가 시간 초과 되 고 ringback 실패할 경우 사용할 대체 대상에 대 한 **Ontimeouturi** 옵션을 구성 하는 것이 좋습니다.

**CsCpsConfiguration** Cmdlet 또는 **Set-CsCpsConfiguration** cmdlet을 사용 하 여 다음 설정을 구성 합니다.


| **이 옵션:**                     | **다음을 지정 합니다.**                                                                                                                                                                                                                                                                                                                   |
|:-------------------------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **CallPickupTimeoutThreshold** <br/> | 통화에 응답 한 전화기로 전화를 걸기 전에 대기 하는 데 걸리는 시간입니다.  <br/> 값은 hh: mm: ss 형식으로 입력 해야 시, 분, 초를 지정할 수 있습니다. 최 솟 값은 10 초 이며 최대값은 10 분입니다. 기본값은 00:01:30입니다.  <br/> |
| **EnableMusicOnHold** <br/>          | 통화가 파킹 되는 동안 호출자가 음악을 재생할 것인지 여부  <br/> 값은 True 또는 False입니다. 기본값은 True입니다.  <br/>                                                                                                                                                                                                                 |
| **MaxCallPickupAttempts** <br/>      | 파킹 된 통화가 **Ontimeouturi**에 대해 지정 된 대체 uri (Fallback Uniform resource Identifier)로 착신 전환 되기 전에 응답 하는 전화의 횟수입니다. 기본값은 1입니다.  <br/>                                                                                                                         |
| **OnTimeoutURI** <br/>               | **MaxCallPickupAttempts** 를 초과 했을 때 응답 하지 않는 파킹 통화가 라우팅되는 사용자 또는 응답 그룹의 SIP 주소입니다. <br/> 값은 sip: 라는 문자열로 시작 하는 SIP URI 여야 합니다. 예를 sip:bob@contoso.com. 기본적으로 전달 주소가 없습니다.  <br/>                                                   |

### <a name="to-configure-call-park-settings"></a>통화 공원 설정을 구성 하려면

1. 비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **비즈니스용 skype 2015**을 차례로 클릭 한 다음 비즈니스용 **skype Server management Shell**을 클릭 합니다.

2. 런

   ```
   New-CsCpsConfiguration -Identity site:<sitename to apply settings> [-CallPickupTimeoutThreshold <hh:mm:ss>] -[EnableMusicOnHold <$true | $false>] [-MaxCallPickupAttempts <number of rings>] [-OnTimeoutURI sip:<sip URI for routing unanswered call>]
   ```

   > [!TIP]
   > 사이트를 식별 하려면 **Get-cssite** cmdlet을 사용 합니다. 자세한 내용은 비즈니스용 Skype 서버 관리 셸 설명서를 참조 하세요.

    예를 들면 다음과 같습니다.

   ```
   New-CsCpsConfiguration -Identity site:Redmond1 -CallPickupTimeoutThreshold 00:01:00 -EnableMusicOnHold $false -MaxCallPickupAttempts 2 -OnTimeoutURI sip:bob@contoso.com
   ```

## <a name="see-also"></a>참고 항목

[통화 대기 음악 사용자 지정 (비즈니스용 Skype 2015)](customize-call-park-music-on-hold.md)

[새로운 CsCpsConfiguration](https://docs.microsoft.com/powershell/module/skype/new-cscpsconfiguration?view=skype-ps)

[Set-CsCpsConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscpsconfiguration?view=skype-ps)

[가져오기-CsSite](https://docs.microsoft.com/powershell/module/skype/get-cssite?view=skype-ps)
