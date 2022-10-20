---
title: Microsoft Teams의 웨비나를 위한 설정
ms.author: mabond
author: mkbond007
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
- highpri
description: Teams 모임에 대한 웨비나 정책을 관리하는 방법을 알아봅니다.
ms.openlocfilehash: 2c83452a37752745072b8a128f9e0eec8db3d7c0
ms.sourcegitcommit: f0e2a5928e9b959daf45202b9f256f65c2087195
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/20/2022
ms.locfileid: "68614581"
---
# <a name="set-up-for-webinars-in-microsoft-teams"></a>Microsoft Teams의 웨비나를 위한 설정

이 문서는 웹 세미나를 호스트하도록 조직을 설정하는 데 도움이 됩니다.

## <a name="what-are-webinars"></a>웨비나란?

웨비나는 발표자와 참가자가 명확한 역할을 갖는 구조화된 모임으로, 종종 교육 목적이나 영업 및 마케팅 리드 생성 시나리오에 사용됩니다.

조직에서 웨비나를 설정한 후 사용자는 웨비나를 예약하고 참석자에게 등록을 열 수 있습니다. 많은 토론 및 작업 할당이 포함된 기존 모임과 달리 웨비나는 대화형 프레젠테이션을 위한 것이며 참석자 분석을 위한 도구를 제공합니다.

> [!IMPORTANT]
> 사용자가 웹 세미나를 설정할 수 있도록 하려면 개인 목록 만들기를 사용하도록 설정하여 SharePoint에서 Microsoft Lists 구성해야 합니다. 자세한 내용은 [Microsoft Lists 대한 제어 설정을](/sharepoint/control-lists) 참조하세요.

## <a name="allow-users-to-schedule-webinars-in-the-teams-admin-center"></a>사용자가 Teams 관리 센터에서 웨비나를 예약할 수 있도록 허용

Teams 관리 센터를 사용하여 조직에 대한 웨비나를 설정할 수 있습니다. Teams 관리 센터에서 **모임 모임** 정책 아래에 웹 세미나를 설정하는 **정책을** 찾을 수 있습니다 > .

### <a name="meeting-registration"></a>모임 등록

이 기능을 켜면 사용자가 웨비나를 예약할 수 있습니다. 기본적으로 이 설정은 켜져 있습니다. 모임 등록을 해제하려면 이 정책을 **끄** 도록 설정합니다.

> [!IMPORTANT]
> 모임 등록이 작동하려면 **비공개 모임 일정이** 설정되어야 합니다. 기본적으로 이 정책은 Teams 관리 센터에서 설정됩니다. 교육 테넌트에 있는 학생의 경우 이 정책은 기본적으로 꺼져 있습니다. 학생을 위한 비공개 모임 예약을 사용하도록 설정하는 방법에 대한 자세한 내용은 [교육용 Teams 정책 및 정책 패키지를 참조하세요](policy-packages-edu.md).

### <a name="who-can-register"></a>등록할 수 있는 사용자

**모든 사용자를** 선택하면 익명 사용자를 포함한 모든 사용자가 웨비나에 등록하고 참석할 수 있습니다. **조직의 모든** 사용자를 선택하는 경우 조직의 사용자만 웨비나에 등록할 수 있습니다. 모임 등록이 해제된 경우 이 옵션을 사용할 수 없으며 아무도 웨비나에 등록할 수 없습니다.

> [!NOTE]
> **등록할 수 있는 사용자의** 기본값은 교육 테넌트에 **있는 조직의 모든** 사용자입니다. 자세한 내용은 [교육용 Teams 정책 마법사](easy-policy-setup-edu.md)를 참조하세요.

### <a name="engagement-report"></a>참여 보고서

이 작업이 완료되면 이끌이는 설정한 웨비나를 등록하고 참석한 사람에 대한 보고서를 볼 수 있습니다. 이 정책은 기본적으로 설정됩니다. 자세한 내용은 [Teams - Engagement 보고서의 모임 정책을](meeting-policies-in-teams-general.md#engagement-report) 참조하세요. 최종 사용자 환경에 대한 자세한 내용은 [모임 참석 보고서 보기 및 다운로드](https://support.microsoft.com/office/view-and-download-meeting-attendance-reports-in-teams-ae7cf170-530c-47d3-84c1-3aedac74d310?ui=en-US&#x26;rs=en-US&#x26;ad=US)를 참조하세요.

## <a name="allow-users-to-schedule-webinars-using-powershell"></a>사용자가 PowerShell을 사용하여 웨비나를 예약하도록 허용

**Windows PowerShell Set-CsTeamsMeetingPolicy** cmdlet 내에서 다음 특성을 사용하여 Teams의 웨비나에 대해 설정할 수 있습니다.

- AllowMeetingRegistration
- WhoCanRegister
- AllowPrivateMeetingScheduling

cmdlet에 대한 자세한 내용은 [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) 를 참조하세요.

> [!NOTE]
> 이러한 cmdlet을 실행하려면 먼저 Microsoft Teams PowerShell에 연결해야 합니다. 자세한 내용은 [Microsoft Teams PowerShell을 사용하여 Teams 관리를](/microsoftteams/teams-powershell-managing-teams) 참조하세요.

### <a name="allow-users-to-schedule-webinars"></a>사용자가 웹 세미나를 예약하도록 허용

조직의 사용자만 등록을 제한하거나 테넌트 내부 및 외부의 모든 사용자에게 등록을 열 수 있습니다. 기본적으로 **WhoCanRegister** 는 전역 **(조직 전체 기본값)** 정책의 **모든** 사용자로 설정됩니다. 모임 등록을 해제하려면 **AllowMeetingRegistration을** **False** 로 설정합니다.

> [!IMPORTANT]
> **AllowMeetingRegistration** 이 작동하려면 **AllowPrivateMeetingScheduling** 을 **True** 로 설정해야 합니다.

1. 모임 등록 켜기

```powershell
Set-CsTeamsMeetingPolicy -AllowMeetingRegistration $True
```

2. 비공개 모임 일정 설정

```powershell
Set-CsTeamsMeetingPolicy -AllowPrivateMeetingScheduling $True
```

3. 웹 세미나에 등록할 수 있는 사용자 구성

**조직의 사용자 *만* 웹 세미나에 등록할 수 있도록 허용**

```powershell
Set-CsTeamsMeetingPolicy -WhoCanRegister EveryoneInCompany
```

**익명 사용자를 포함한 모든 사용자가 웹 세미나에 등록할 수 있도록 하려면 다음을 실행합니다.**

```powershell
Set-CsTeamsMeetingPolicy -WhoCanRegister Everyone
```

> [!CAUTION]
> 모임 설정에서 익명 참가가 해제된 경우 익명 사용자는 웨비나에 참가할 수 없습니다. 자세한 내용을 알아보고 이 설정을 사용하도록 설정하려면 [Teams의 모임 설정을 참조하세요](meeting-settings-in-teams.md).

### <a name="collect-meeting-attendance"></a>모임 참석 수집

**AllowEngagementReport** 매개 변수를 사용하면 누가 웨비나를 등록하고 참석했는지 확인할 수 있습니다. 이 정책은 기본적으로 켜져 있습니다. 끄려면 PowerShell에서 다음 명령을 실행합니다.

```powershell
Set-CsTeamsMeetingPolicy -AllowEngagementReport Disabled
```

## <a name="configure-webinar-settings"></a>웹 세미나 설정 구성

웹 세미나에 대한 환경을 사용하도록 설정한 후에는 추가 관리자 관리가 필요하지 않습니다. 정책은 웹 세미나 이끌이에 대해 표시되는 옵션을 제어합니다.

## <a name="related-topics"></a>관련 주제

- [Teams의 모임 정책 - 일반](meeting-policies-in-teams-general.md)
- [Set-CsTeamsMeetingPolicy 설명서](/powershell/module/skype/set-csteamsmeetingpolicy)
- [교육용 Teams 정책 마법사](easy-policy-setup-edu.md)
