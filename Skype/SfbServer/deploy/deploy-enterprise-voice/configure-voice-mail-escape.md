---
title: 음성 메일 이스케이프를 비즈니스용 Skype
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
description: '요약: 비즈니스용 Skype 서버 관리 셸을 사용하여 음성 메일 이스케이프를 비즈니스용 Skype 서버 방법을 설명하는 방법을 제공합니다.'
ms.openlocfilehash: f94a9e78d5f1b88644691d43b7c24169e6122e6188f7ee45c095521230b6be3f
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54279426"
---
# <a name="configure-voice-mail-escape-in-skype-for-business"></a>음성 메일 이스케이프를 비즈니스용 Skype

**요약:** 비즈니스용 Skype 서버 관리 셸을 사용하여 음성 메일 이스케이프를 비즈니스용 Skype 서버 방법을 학습합니다.

사용자가 휴대폰에 동시 벨 울림을 구성하면 일반적으로 휴대폰이 꺼져 있는지, 배터리 전원이 부족하거나, 범위를 벗어날 경우 발신자는 사용자의 개인 음성 메일로 라우팅됩니다. 이 비즈니스용 Skype 서버 회사 음성 메일 시스템으로 라우팅되는 업무 관련 통화를 옵트인할 수 있습니다. 특히, Timer을 구성할 수 있으며 정의된 시간 범위 내에 통신 사업자 음성 메일이 통화에 응답하면 비즈니스용 Skype 서버 통신 사업자 음성 메일 시스템 및 사용자의 개인 음성 메일과의 연결이 끊어지고 회사 시스템의 사용자의 남은 끝점에서 계속 벨이 울리게 됩니다. 이렇게 하면 발신자를 사용자의 회사 음성 메일로 자동으로 라우팅합니다.

이 구성은 음성 정책 수준에서 비즈니스용 Skype 서버 관리 셸 cmdlet인 **Set-CsVoicePolicy를** 사용하여 다음 매개 변수를 사용하여 수행됩니다.

### <a name="to-configure-voice-mail-escape"></a>음성 메일 이스케이프를 구성합니다.

1. 비즈니스용 Skype 서버 시작: **시작,** 모든 프로그램, 비즈니스용 Skype **2015를** 클릭한 다음 관리 **비즈니스용 Skype 서버 를 클릭합니다.**

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