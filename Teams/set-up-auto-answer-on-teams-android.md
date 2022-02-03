---
title: Android 디바이스에 대한 자동 Teams 설정
author: KarliStites
ms.author: kastites
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: kponnus
audience: admin
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- CSH
ms.custom: ''
description: PowerShell을 사용하여 Android 디바이스에 대한 자동 Teams 설정하는 방법에 대해 자세히 알아보습니다.
ms.openlocfilehash: e25b0694b54d1047c64ecaba026380ac9c4a9949
ms.sourcegitcommit: 5e9a8d3cdb72b57adfb842200159c5d753b70ecb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/03/2022
ms.locfileid: "62329107"
---
# <a name="set-up-auto-answer-for-teams-android-devices"></a>Android 디바이스에 대한 자동 Teams 설정

이 문서에서는 Android 디바이스에서 자동 응답 Teams 도움이 됩니다. 자동 답변을 사용하면 관리 권한이 있는 조직의 사용자가 디바이스 설정을 변경하여 들어오는 모임 초대를 자동으로 수락하고 비디오로 자동으로 전화를 수락할 수 있습니다.

## <a name="enable-auto-answer-with-powershell"></a>PowerShell을 사용하여 자동 응답 사용

Android 디바이스에서 자동 응답을 사용하도록 설정하려면 다음 특성을 Teams 있습니다.

- **Set-CsTeamsCallingPolicy -AutoAnswerEnabledType**
- **Set-CsTeamsIPPhonePolicy -SignInMode**

### <a name="1-turn-on-auto-answer-for-incoming-meeting-invites"></a>1. 들어오는 모임 초대에 대한 자동 응답 켜기

**Set-CsTeamsCallingPolicy -AutoAnswerEnabledType** 을 사용하여 들어오는 모임 초대에 대한 자동 답변을 엽니 다. 자동 답변은 기본적으로 **해제** 됩니다. 이 정책은 들어오는 모임 초대에만 적용하며 다른 통화 유형을 지원하지 않습니다. cmdlet에 대한 자세한 내용은 [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy) 를 읽습니다.

```powershell
Set-CsTeamsCallingPolicy -AutoAnswerEnabledType Enabled
```

### <a name="2-set-the-device-sign-in-mode"></a>2. 디바이스 로그인 모드 설정

**Set-CsTeamsIPPhonePolicy -SignInMode** 를 사용하여 디바이스에 대한 로그인 모드를 설정하여 로그인에 로그인할 때 Teams. cmdlet에 대한 자세한 내용은 [Set-CsTeamsIPPhonePolicy](/powershell/module/skype/set-csteamsipphonepolicy) 를 읽습니다.

로그인 모드에는 세 가지 옵션이 있습니다.

- **UserSignIn:** 휴대폰에서 개별 사용자 Teams 환경을 설정합니다.
- **CommonAreaPhoneSignIn:** 휴대폰에서 공통 영역 전화 환경을 사용할 수 있습니다.
- **MeetingSignIn:** 전화에서 회의실 환경을 사용할 수 있습니다.

예를 들어 다음 정책은 로그인 모드를 회의실 환경으로 설정합니다.

```powershell
Set-CsTeamsIPPhonePolicy -Identity Device -SignInMode MeetingSignIn
```

### <a name="configure-device-settings"></a>디바이스 설정 구성

자동 답변을 사용하도록 설정한 후 관리 권한이 있는 사용자는 디바이스 설정에서 기능을 켜면 됩니다. 디바이스 수준에서 기능을 사용하도록 설정하려면 들어오는 모임 초대 **자동 수락을 켜야 합니다**. 비디오로 자동 수락 **을 켜도됩니다**. 두 설정 모두 기본적으로 꺼집니다.

## <a name="related-topics"></a>관련 항목

[Microsoft 지원: 통화 및 디바이스](https://support.microsoft.com/office/calls-and-devices-4d96653e-6176-4978-98ab-2c19df137e43#ID0EBBD=Devices)

[Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy)

[Set-CsTeamsIPPhonePolicy](/powershell/module/skype/set-csteamsipphonepolicy)