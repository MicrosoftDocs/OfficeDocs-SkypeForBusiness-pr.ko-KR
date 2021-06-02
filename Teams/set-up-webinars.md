---
title: 웨비나에 대해 Microsoft Teams
author: KarliStites
ms.author: kastites
manager: serdars
ms.reviewer: sachung, emryan
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: ''
ms.collection:
- M365-collaboration
- m365initiative-meetings
description: 모임에 대한 Webinar 정책을 관리하는 Teams 대해 자세히 알아보습니다.
ms.openlocfilehash: aafa7b57eea1228fa5565bb4d5e95304b42751a3
ms.sourcegitcommit: 90615674e9703aa5ea32be64ab3638aa30e83127
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/02/2021
ms.locfileid: "52718049"
---
# <a name="set-up-for-webinars-in-microsoft-teams"></a>웨비나에 대해 Microsoft Teams

이 문서에서는 웨비나를 호스트할 조직을 설정하는 데 도움이 됩니다.

## <a name="what-are-webinars"></a>웨비나란?

웨비나는 강사와 참가자가 명확한 역할을 가지는 구조화된 모임으로, 교육 목적 또는 영업 및 마케팅 리드 생성 시나리오에 자주 사용됩니다.

조직에서 웨비나를 설정한 후 사용자는 웨비나를 예약하고 참석자에 대한 등록을 열 수 있습니다. 많은 토론과 작업 할당이 포함된 기존 모임과 달리 웨비나는 대화형 프레젠테이션을 위한 것이고 참석자 분석 도구를 제공합니다.

## <a name="allow-users-to-schedule-webinars-using-powershell"></a>PowerShell을 사용하여 사용자가 웨비나 예약 허용

Windows PowerShell **Set-CsTeamsMeetingPolicy** cmdlet에서 다음 특성을 사용하여 Teams.

- AllowMeetingRegistration
- WhoCanRegister
- AllowPrivateMeetingScheduling

cmdlet에 대한 자세한 내용은 [Set-CsTeamsMeetingPolicy를](/powershell/module/skype/set-csteamsmeetingpolicy) 읽습니다.

> [!NOTE]
> 이러한 cmdlet을 실행하려면 먼저 온라인 PowerShell에 비즈니스용 Skype 있어야 합니다. 자세한 내용은 [PowerShell에서](/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)비즈니스용 Skype 온라인 Microsoft 365 Office 365 참조하세요.

### <a name="allow-users-to-schedule-webinars"></a>사용자가 웨비나 예약 허용

조직의 사용자가 웨비나를 예약할 수 있도록 허용하기 위해 다음을 실행합니다.

```powershell
Set-CsTeamsMeetingPolicy -AllowMeetingRegistration $True
```
### <a name="configure-who-can-register-for-webinars"></a>웨비나에 등록할 수 있는 사용자 구성

조직의 사용자로만 등록을 제한하거나 테넌트 내부 및 외부의 모든 사용자에게 등록을 열 수 있습니다. 기본적으로 **WhoCanRegister를** 사용하도록 설정하고 모든 으로 **설정합니다.** 모임 등록을 해제하려는 경우 **AllowMeetingRegistration을 False로** **설정합니다.**

> [!IMPORTANT]
> **AllowPrivateMeetingScheduling은** **AllowMeetingRegistration이** 작동하려면 True로 설정해야 합니다.  또한 Microsoft Lists는 Microsoft 목록에서 설정해야 SharePoint. 자세한 내용은 [Microsoft Lists에 대한 제어 설정을 참조하세요.](/sharepoint/control-lists)

**조직의 *사용자만* 웨비나에 등록할 수 있도록 허용하기 위해 다음을 실행합니다.**

```powershell
Set-CsTeamsMeetingPolicy -AllowPrivateMeetingScheduling $True
```

그런 다음, 다음을 실행합니다.

```powershell
Set-CsTeamsMeetingPolicy -WhoCanRegister EveryoneInCompany
```

**익명 사용자를 비롯한 모든 사용자가 웨비나에 등록할 수 있도록 허용하기 위해 다음을 실행합니다.**

```powershell
Set-CsTeamsMeetingPolicy -AllowPrivateMeetingScheduling $True
```

그런 다음, 다음을 실행합니다.

```powershell
Set-CsTeamsMeetingPolicy -WhoCanRegister Everyone
```

> [!IMPORTANT]
> 모임 설정에서 익명 조인이 해제된 경우 익명 사용자는 웨비나에 참가할 수 없습니다. 자세한 내용을 알아보고 이 설정을 사용하도록 설정하려면 에서 모임 [설정을 Teams.](meeting-settings-in-teams.md)

### <a name="collect-meeting-attendance"></a>모임 참석자 수집

주최자가 등록하고 참석한 웨비나를 분석하려면 **AllowEngagementReport** 정책을 설정해야 합니다. 이렇게 하여 PowerShell에서 다음 명령을 실행합니다.

```powershell
Set-CsTeamsMeetingPolicy -AllowEngagementReport Enabled
```

### <a name="configure-webinar-settings"></a>웨비나 설정 구성

웨비나에 대한 환경을 사용하도록 설정한 후 추가 관리자 관리가 필요하지 않습니다. 정책은 웨비나 이끌이에 대해 표시하는 옵션을 제어합니다.

## <a name="related-topics"></a>관련 항목

- [Teams 모임 정책 - 일반](meeting-policies-in-teams-general.md)
- [Set-CsTeamsMeetingPolicy 설명서](/powershell/module/skype/set-csteamsmeetingpolicy)
