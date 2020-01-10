---
title: 비즈니스용 Skype에서 음성 메일 esc 구성
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
ms.assetid: a1d19e6c-82ff-4768-8ae5-da981368ce40
description: '요약: 비즈니스용 skype 서버 관리 셸을 사용 하 여 비즈니스용 Skype 서버에서 음성 메일 esc를 구성 하는 방법에 대해 알아봅니다.'
ms.openlocfilehash: 27f283f4bfb64aa950bd9e72a9d6fdc17df91ba0
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/09/2020
ms.locfileid: "41001218"
---
# <a name="configure-voice-mail-escape-in-skype-for-business"></a>비즈니스용 Skype에서 음성 메일 esc 구성

**요약:** 비즈니스용 skype 서버 관리 셸을 사용 하 여 비즈니스용 Skype 서버에서 음성 메일 esc를 구성 하는 방법에 대해 알아봅니다.

사용자가 휴대폰으로 동시 신호음을 구성 하는 경우, 휴대 전화를 끄거나, 배터리 전원이 꺼져 있거나, 범위를 벗어나면 일반적으로 발신자가 사용자의 개인 음성 메일로 라우팅됩니다. 비즈니스용 Skype 서버를 사용 하는 경우 사용자는 회사 음성 메일 시스템으로 라우팅되는 비즈니스 관련 통화를 선택할 수 있습니다. 특히 타이머를 구성할 수 있으며, 통화를 지정 된 시간 범위 내에서 통신 회사의 음성 메일로 수신 하는 경우 비즈니스용 Skype 서버는 해당 통신 회사의 음성 메일 시스템과 사용자의 개인 음성 메일을 연결 해제 합니다. 회사 시스템의 나머지 끝점은 계속 해 서 울립니다. 이 방법으로 발신자는 자동으로 사용자의 회사 음성 메일로 라우팅됩니다.

이 구성은 다음 매개 변수를 사용 하 여 음성 정책 수준에서 비즈니스용 Skype 서버 관리 셸 cmdlet **CsVoicePolicy**를 사용 하 여 수행 됩니다.

### <a name="to-configure-voice-mail-escape"></a>음성 메일 esc를 구성 하려면

1. 비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **비즈니스용 skype 2015**을 차례로 클릭 한 다음 비즈니스용 **skype Server management Shell**을 클릭 합니다.

2. 다음 매개 변수를 **CsVoicePolicy**로 지정 합니다.

   - **EnableVoicemailEscapeTimer** -이탈 타이머를 사용 하거나 사용 하지 않도록 설정 합니다.

   - **PSTNVoicemailEscapeTimer** -제한 시간 값 (밀리초)을 지정 합니다. 기본값은 1500 밀리초 이며, 값의 범위는 0 밀리초 ~ 8000 밀리초입니다.

## <a name="example"></a>예

```powershell
Set-CsVoicePolicy UserVoicePolicy -EnableVoiceMailEscapeTimer $true - PSTNVoicemailEscapeTimer 2000
Set-CsVoicePolicy -Identity site:SitePolicy -EnableVoiceMailEscapeTimer $true -PSTNVoicemailEscapeTimer 1500
```

## <a name="see-also"></a>참고 항목

[음성 정책 및 PSTN 사용 레코드를 구성 하 여 통화 기능 및 사용 권한 승인](https://technet.microsoft.com/library/63f22010-a3d7-4cbd-86e8-6fc0e13c2b84.aspx)

