---
title: Teams Android 디바이스에 대한 자동 답변 설정
author: mkbond007
ms.author: mabond
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
description: PowerShell을 사용하여 Android 및 Teams 비디오 전화 디바이스에서 Microsoft Teams 룸 대한 자동 응답 기능을 설정하는 방법을 알아봅니다.
ms.openlocfilehash: fac458a2b7b100a2074dbaac0e209fbdd3527eef
ms.sourcegitcommit: 9532eb79310cd653010565607fa394f2b8dd182d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/23/2022
ms.locfileid: "65646597"
---
# <a name="set-up-auto-answer-for-microsoft-teams-rooms-on-android-and-teams-video-phone-devices"></a>Android 및 Teams 비디오 전화 장치에서 Microsoft Teams 룸 대한 자동 답변 설정

이 문서는 Android 및 Teams 비디오 전화 장치에서 Microsoft Teams 룸 자동 응답 기능을 설정하는 데 도움이 됩니다. 자동 답변을 사용하면 관리자 권한이 있는 조직의 사용자가 디바이스 설정을 변경하여 들어오는 모임 초대를 자동으로 수락하고 비디오로 통화를 자동으로 수락할 수 있습니다.

## <a name="enable-auto-answer-with-powershell"></a>PowerShell을 사용하여 자동 답변 사용

다음 특성을 사용하여 Android 및 Teams 비디오 전화 장치에서 Microsoft Teams 룸 자동 답변을 사용하도록 설정합니다.

- **Set-CsTeamsCallingPolicy -AutoAnswerEnabledType**
- **Set-CsTeamsIPPhonePolicy -SignInMode**

### <a name="1-turn-on-auto-answer-for-incoming-meeting-invites"></a>1. 들어오는 모임 초대에 대한 자동 응답 켜기

**Set-CsTeamsCallingPolicy -AutoAnswerEnabledType** 을 사용하여 들어오는 모임 초대에 대한 자동 답변을 켭니다. 자동 응답은 기본적으로 **꺼져** 있습니다. 이 정책은 들어오는 모임 초대에만 적용되며 다른 통화 유형을 지원하지 않습니다. cmdlet에 대한 자세한 내용은 [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy) 를 참조하세요.

```powershell
Set-CsTeamsCallingPolicy -AutoAnswerEnabledType Enabled
```

### <a name="2-set-the-device-sign-in-mode"></a>2. 디바이스 로그인 모드 설정

**Set-CsTeamsIPPhonePolicy -SignInMode** 를 사용하여 Teams 로그인할 때 디바이스의 로그인 모드를 설정하여 동작을 확인합니다. cmdlet에 대한 자세한 내용은 [Set-CsTeamsIPPhonePolicy](/powershell/module/skype/set-csteamsipphonepolicy) 를 참조하세요.

로그인 모드에는 다음 세 가지 옵션이 있습니다.

- **UserSignIn:** 휴대폰에서 개별 사용자 Teams 환경을 사용하도록 설정합니다.
- **CommonAreaPhoneSignIn:** 휴대폰에서 공통 영역 전화 환경을 사용하도록 설정합니다.
- **MeetingSignIn:** 휴대폰에서 회의실 환경을 사용하도록 설정합니다.

예를 들어 다음 정책은 로그인 모드를 회의실 환경으로 설정합니다.

```powershell
Set-CsTeamsIPPhonePolicy -Identity Device -SignInMode MeetingSignIn
```

### <a name="configure-device-settings"></a>디바이스 설정 구성

자동 답변을 사용하도록 설정한 후 관리 권한이 있는 사용자는 디바이스 설정에서 기능을 켤 수 있습니다. 디바이스 수준에서 기능을 사용하도록 설정하려면 **들어오는 모임 초대를 자동으로 수락** 하도록 설정해야 합니다. **비디오로 자동 수락을** 켤 수도 있습니다. 두 설정 모두 기본적으로 꺼져 있습니다.

## <a name="related-topics"></a>관련 항목

[Microsoft 지원: 통화 및 디바이스](https://support.microsoft.com/office/calls-and-devices-4d96653e-6176-4978-98ab-2c19df137e43#ID0EBBD=Devices)

[Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy)

[Set-CsTeamsIPPhonePolicy](/powershell/module/skype/set-csteamsipphonepolicy)
