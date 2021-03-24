---
title: 비즈니스용 Skype에서 음성 메일 이스케이프 구성
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
ms.assetid: a1d19e6c-82ff-4768-8ae5-da981368ce40
description: '요약: 비즈니스용 Skype 서버 관리 셸을 사용하여 비즈니스용 Skype 서버에서 음성 메일 이스케이프를 구성하는 방법을 학습합니다.'
ms.openlocfilehash: c74142cf3b0f6c9d5a871e116d8e163a095ad3cd
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51106374"
---
# <a name="configure-voice-mail-escape-in-skype-for-business"></a>비즈니스용 Skype에서 음성 메일 이스케이프 구성

**요약:** 비즈니스용 Skype 서버 관리 셸을 사용하여 비즈니스용 Skype 서버에서 음성 메일 이스케이프를 구성하는 방법을 학습합니다.

사용자가 휴대폰에 동시 벨 울림을 구성하면 일반적으로 휴대폰이 꺼져 있는지, 배터리 전원이 부족하거나, 범위를 벗어날 경우 발신자는 사용자의 개인 음성 메일로 라우팅됩니다. 비즈니스용 Skype 서버를 사용하여 사용자는 회사 음성 메일 시스템으로 업무 관련 통화를 라우팅할 수 있습니다. 특히, Timer을 구성할 수 있으며 정의된 시간 범위 내에 통신 사업자 음성 메일이 통화에 응답하면 비즈니스용 Skype 서버는 통신 사업자 음성 메일 시스템(및 사용자의 개인 음성 메일)과의 연결을 끊고 회사 시스템의 사용자의 나머지 끝점에서 계속 벨이 울리게 됩니다. 이렇게 하면 발신자를 사용자의 회사 음성 메일로 자동으로 라우팅합니다.

이 구성은 다음 매개 변수를 사용하여 음성 정책 수준에서 비즈니스용 Skype 서버 관리 셸 cmdlet인 **Set-CsVoicePolicy를** 사용하여 수행됩니다.

### <a name="to-configure-voice-mail-escape"></a>음성 메일 이스케이프를 구성합니다.

1. 비즈니스용 Skype 서버 관리 셸 시작: **시작,** 모든 **프로그램,** 비즈니스용 **Skype 2015,** 비즈니스용 Skype 서버 관리 셸을 **클릭합니다.**

2. **Set-CsVoicePolicy** 에 다음 매개 변수를 지정합니다.

   - **EnableVoicemailEscapeTimer** - 이스케이프 타이머를 사용하거나 사용하지 않도록 설정합니다.

   - **PSTNVoicemailEscapeTimer** - 시간 제한 값을 밀리초 단위로 지정합니다. 기본값은 1500밀리초이며 0~8000밀리초 범위에서 값을 지정할 수 있습니다.

## <a name="example"></a>예제

```powershell
Set-CsVoicePolicy UserVoicePolicy -EnableVoiceMailEscapeTimer $true - PSTNVoicemailEscapeTimer 2000
Set-CsVoicePolicy -Identity site:SitePolicy -EnableVoiceMailEscapeTimer $true -PSTNVoicemailEscapeTimer 1500
```

## <a name="see-also"></a>참고 항목

[통화 기능 및 권한을 부여하도록 통화 정책 및 PSTN 사용 레코드 구성](/previous-versions/office/lync-server-2013/lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges)