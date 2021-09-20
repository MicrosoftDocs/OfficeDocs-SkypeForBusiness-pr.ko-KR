---
title: Microsoft Teams의 웨비나를 위한 설정
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
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: ''
ms.collection:
- M365-collaboration
- m365initiative-meetings
description: 모임에 대한 Webinar 정책을 관리하는 Teams 대해 자세히 알아보습니다.
ms.openlocfilehash: 78c81e25d246dc450ffcd821d22148c330d38f23
ms.sourcegitcommit: cf2f96dbd485ac4cc822c5a591ccce6b47f12cc7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/20/2021
ms.locfileid: "59456318"
---
# <a name="set-up-for-webinars-in-microsoft-teams"></a>Microsoft Teams의 웨비나를 위한 설정

이 문서에서는 웨비나를 호스트할 조직을 설정하는 데 도움이 됩니다.

## <a name="what-are-webinars"></a>웨비나란?

웨비나는 발표자 및 참가자가 명확한 역할을 가지는 구조화된 모임으로, 교육 목적 또는 영업 및 마케팅 잠재 고객 생성 시나리오에 자주 사용됩니다.

조직에서 웨비나를 설정한 후 사용자는 웨비나를 예약하고 참석자에 대한 등록을 열 수 있습니다. 많은 토론과 작업 할당이 포함된 기존 모임과 달리 웨비나는 대화형 프레젠테이션을 위한 것이고 참석자 분석 도구를 제공합니다.

## <a name="allow-users-to-schedule-webinars-in-the-teams-admin-center"></a>사용자가 관리 센터에서 웨비나 예약을 Teams 허용

관리 센터를 사용하여 Teams 웨비나를 설정할 수 있습니다. 모임 모임 정책에서 Teams 관리 센터에서 웨비나를 설정하는 정책을   >  **찾을 수 있습니다.**

### <a name="allow-meeting-registration"></a>모임 등록 허용

이 기능을 설정하면 사용자가 웨비나를 예약할 수 있습니다. 기본적으로 이 설정은 켜져 있습니다. 모임 등록을 해제하려는 경우 이 정책을 끄기 로 **설정합니다.**

> [!IMPORTANT]
> **모임 등록이** 작동하려면 비공개 모임을 허용해야 합니다. 기본적으로 이 정책은 관리 센터에서 Teams 설정됩니다. 교육 테넌트의 학생의 경우 이 정책은 기본적으로 해제됩니다. 학생을 위해 개인 모임을 사용하도록 설정하는 방법에 대한 자세한 내용은 정책 및 정책 교육용 Teams [참조하세요.](policy-packages-edu.md)

### <a name="who-can-register"></a>Who 수 있습니다.

모든 사용자 **,** 익명 사용자를 포함한 모든 사용자를 선택하면 웨비나에 등록하고 참석할 수 있습니다. 조직의 **모든 사용자를 선택하면** 조직의 사용자만 웨비나에 등록할 수 있습니다. 모임 등록이 해제된 경우 이 옵션을 사용할 수 없습니다. 누구도 웨비나에 등록할 수 없습니다.

> [!NOTE]
> 등록할 **수** Who 기본값은 교육  테넌트의 조직의 모든 사용자입니다. 자세한 내용은 정책 [마법사 교육용 Teams 참조하세요.](easy-policy-setup-edu.md)

### <a name="allow-engagement-report"></a>참여 보고서 허용

이 기능을 설정하면 이끌이가 설정한 웨비나에 등록하고 참석한 사람에 대한 보고서를 볼 수 있습니다. 이 정책은 기본적으로 꺼집니다. 자세한 내용은 참여 보고서 허용 Teams 모임 정책을 [참조하세요.](meeting-policies-in-teams-general.md#allow-engagement-report) 최종 사용자 경험에 대한 자세한 내용은 모임 출석 보고서 보기 및 [다운로드를 참조하세요.](https://support.microsoft.com/office/view-and-download-meeting-attendance-reports-in-teams-ae7cf170-530c-47d3-84c1-3aedac74d310?ui=en-US&#x26;rs=en-US&#x26;ad=US)

## <a name="allow-users-to-schedule-webinars-using-powershell"></a>PowerShell을 사용하여 사용자가 웨비나 예약 허용

Windows PowerShell **Set-CsTeamsMeetingPolicy** cmdlet에서 다음 특성을 사용하여 Teams.

- AllowMeetingRegistration
- WhoCanRegister
- AllowPrivateMeetingScheduling

cmdlet에 대한 자세한 내용은 [Set-CsTeamsMeetingPolicy를](/powershell/module/skype/set-csteamsmeetingpolicy) 읽습니다.

> [!NOTE]
> 이러한 cmdlet을 실행하려면 먼저 PowerShell에 Microsoft Teams 있어야 합니다. 자세한 내용은 [PowerShell을 사용하여 Teams Microsoft Teams 참조하세요.](/microsoftteams/teams-powershell-managing-teams)

### <a name="allow-users-to-schedule-webinars"></a>사용자가 웨비나 예약 허용

조직의 사용자로만 등록을 제한하거나 테넌트 내부 및 외부의 모든 사용자에게 등록을 열 수 있습니다. 기본적으로 **WhoCanRegister는** **전역(Org-wide default)** 정책에 대한 **모든** 사용자로 설정되어 있습니다. 모임 등록을 해제하려는 경우 **AllowMeetingRegistration을 False로** **설정합니다.**

> [!IMPORTANT]
> **AllowPrivateMeetingScheduling은** **AllowMeetingRegistration이** 작동하려면 True로 설정해야 합니다.  또한 Microsoft Lists 설정해야 SharePoint. 자세한 내용은 에 대한 제어 [설정을 Microsoft Lists.](/sharepoint/control-lists)

1. 모임 등록 켜기

```powershell
Set-CsTeamsMeetingPolicy -AllowMeetingRegistration $True
```

2. 비공개 모임일정 설정

```powershell
Set-CsTeamsMeetingPolicy -AllowPrivateMeetingScheduling $True
```

3. 웨비나에 등록할 수 있는 사용자 구성

***조직의 사용자만* 웨비나에 등록할 수 있도록 허용**

```powershell
Set-CsTeamsMeetingPolicy -WhoCanRegister EveryoneInCompany
```

**익명 사용자를 비롯한 모든 사용자가 웨비나에 등록할 수 있도록 허용하기 위해 다음을 실행합니다.**

```powershell
Set-CsTeamsMeetingPolicy -WhoCanRegister Everyone
```

> [!CAUTION]
> 모임 설정에서 익명 조인이 해제된 경우 익명 사용자는 웨비나에 참가할 수 없습니다. 자세한 내용을 알아보고 이 설정을 사용하도록 설정하려면 에서 모임 [설정을 Teams.](meeting-settings-in-teams.md)

### <a name="collect-meeting-attendance"></a>모임 참석자 수집

주최자가 등록하고 참석한 웨비나를 분석하려면 **AllowEngagementReport** 정책을 설정해야 합니다. 이렇게 하여 PowerShell에서 다음 명령을 실행합니다.

```powershell
Set-CsTeamsMeetingPolicy -AllowEngagementReport Enabled
```

## <a name="configure-webinar-settings"></a>웨비나 설정 구성

웨비나에 대한 환경을 사용하도록 설정한 후 추가 관리자 관리가 필요하지 않습니다. 정책은 웨비나 이끌이에 대해 표시하는 옵션을 제어합니다.

## <a name="related-topics"></a>관련 항목

- [Teams 모임 정책 - 일반](meeting-policies-in-teams-general.md)
- [Set-CsTeamsMeetingPolicy 설명서](/powershell/module/skype/set-csteamsmeetingpolicy)
- [교육용 Teams 정책 마법사](easy-policy-setup-edu.md)
