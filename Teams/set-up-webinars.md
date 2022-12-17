---
title: 웨비나 설정
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
description: Teams에서 웨비나 및 모임 등록 정책을 관리하는 방법을 알아봅니다.
ms.openlocfilehash: 5493104b93a74dad6763e0a5ba6c9e6fd57575de
ms.sourcegitcommit: b710fc61558a0e031d4e3e4000f234c495e2c4c6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/17/2022
ms.locfileid: "69438476"
---
# <a name="set-up-webinars-in-microsoft-teams"></a>Microsoft Teams에서 웨비나 설정

> [!NOTE]
> 이 문서에서는 미리 보기 상태이며 Teams Premium 라이선스가 필요한 웨비나의 일부 기능에 대해 설명합니다.

이제 Microsoft 새 웨비나 환경을 제공합니다. 이 문서에서는 이러한 기능을 사용하도록 설정을 업데이트하는 방법을 설명합니다.

웨비나를 사용하려는 경우 새 웨비나 환경을 사용하는 것이 좋습니다.

모임 등록에는 기본 웨비나 기능, 모임 등록을 요구하는 기능 및 참석 보고서가 포함됩니다. 새 웨비나 환경을 사용하도록 설정하면 모임 등록 및 다음과 같은 여러 새 웨비나 기능을 사용할 수 있습니다.

- 웨비나에 대한 전용 이벤트 및 등록 페이지
- 공동 이끌이
- 이벤트 페이지의 발표자 bios
- 등록 상태 개요 및 관리

[Teams 웹 세미나 시작](https://support.microsoft.com/office/42f3f874-22dc-4289-b53f-bbc1a69013e3)에서 최종 사용자가 사용할 수 있는 새로운 기능에 대해 자세히 알아보세요.

조직에서 모임 등록을 사용하도록 설정한 경우 새로 만든 모든 웨비나에는 새 환경이 있습니다. 이전에 예약된 웨비나는 이전 웨비나 환경을 사용합니다. 새 환경은 TeamsEventsPolicy를 사용합니다. 웨비나를 해제한 경우 새 환경이 출시될 때 웹 세미나가 꺼져 있습니다.

현재 기본 웨비나 환경은 Teams 모임 정책(Set-CsTeamsMeetingPolicy)을 사용하여 모임 등록에 의해 제어됩니다. 나중에 모임 등록 설정은 웨비나를 제어하지 않습니다. 웹 세미나는 Teams 이벤트 정책(Set-CsTeamsEventsPolicy)에 의해 제어되는 것으로 전환되고 있습니다.

새 웨비나 환경은 PowerShell에서 구성됩니다. [새 웨비나 환경을 설정하는 방법에](#set-up-new-webinar-experience) 대한 예제를 참조하세요.

모임, 웨비나 및 라이브 이벤트의 차이점에 대한 자세한 내용은 [모임, 웨비나 및 라이브 이벤트를 참조하세요](quick-start-meetings-live-events.md).

> [!NOTE]
> 새 웨비나 환경은 Microsoft 365 GCC, Microsoft 365GCC High 또는 Microsoft 365 DoD에 사용할 수 없습니다. 기존 웨비나 환경은 Microsoft 365 GCC High 또는 Microsoft 365 DoD에 사용할 수 없습니다.

> [!IMPORTANT]
> 사용자가 웨비나를 설정할 수 있도록 하려면 eDiscovery 목적으로 개인 목록을 만들도록 설정하여 SharePoint에서 Microsoft Lists 구성해야 합니다. 자세한 내용은 [Microsoft Lists 대한 설정 제어를 참조하세요](/sharepoint/control-lists).

## <a name="set-up-new-webinar-experience"></a>새 웨비나 환경 설정

PowerShell을 사용하여 조직에 대한 새 웨비나 환경을 설정해야 합니다. Teams 관리 센터에서 새 웨비나 환경을 구성하는 기능은 아직 사용할 수 없습니다.

새 웨비나 환경을 사용하려면 모임 등록이 설정되어야 합니다.

### <a name="configure-the-new-webinar-experience-with-powershell"></a>PowerShell을 사용하여 새 웨비나 환경 구성

새 웨비나 환경을 설정하려면 **Windows PowerShell Set-CsTeamsEventsPolicy** cmdlet 내에서 다음 특성을 사용합니다.

|매개 변수|기본 설정|설명|
|---------|-----------|---------------|
|AllowWebinars|사용|이 설정은 사용자가 웨비나를 만들 수 있는지 여부를 결정합니다.|
|EventAccessType|모든 사용자|이 설정은 등록할 이벤트 등록 페이지 또는 이벤트 사이트에 액세스할 수 있는 사용자와 이벤트에서 세션에 참가할 수 있는 사용자 유형을 결정합니다.|

이러한 cmdlet을 실행하려면 먼저 Microsoft Teams PowerShell에 연결해야 합니다. 자세한 내용은 [Microsoft Teams PowerShell을 사용하여 Teams 관리를 참조하세요](/microsoftteams/teams-powershell-managing-teams).

1. 모임 등록을 켭니다.

    ```powershell
    Set-CsTeamsMeetingPolicy -Identity <policy name> -AllowMeetingRegistration $True
    ```

1. 새 웨비나 환경을 활성화합니다.

    ```powershell
    Set-CsTeamsEventsPolicy -Identity <policy name> -AllowWebinars Enabled
    ```

1. 웨비나 및 모임에 등록할 수 있는 사용자를 구성합니다.

    - **조직의 **_only_* _ 사용자가 웨비나 및 meetings_ 등록하도록 허용*

        ```powershell
        Set-CsTeamsEventsPolicy -Identity <policy name> -EventAccessType EveryoneInCompanyExcludingGuests
        ```

    - **익명 사용자를 포함한 모든 사용자가 웨비나 및 모임에 등록할 수 있도록 허용**

        ```powershell
        Set-CsTeamsEventsPolicy -Identity <policy name> -EventAccessType Everyone
        ```

> [!IMPORTANT]
> 모임 **설정** 에서 **익명 사용자가 모임에 참가할 수** 없으면 익명 사용자는 웨비나에 참가할 수 없습니다. 자세한 내용을 알아보고 이 설정을 사용하도록 설정하려면 [Teams의 모임 설정을 참조하세요](meeting-settings-in-teams.md).

## <a name="configure-meeting-registration"></a>모임 등록 구성

웨비나를 사용하려면 모임 등록을 켜야 합니다.

모임 **모임 정책** 아래의 Teams 관리 센터를 사용하여 **모임** >  등록 및 웨비나를 설정할 수 있습니다.

### <a name="meeting-registration"></a>모임 등록

**모임 등록** 을 켜면 조직의 사용자가 등록이 필요한 웨비나 및 모임을 예약할 수 있습니다. 기본적으로 이 설정은 켜져 있습니다. 모임 등록 및 웨비나를 끄려면 이 정책을 **끄** 기로 설정합니다.

**모임 등록이** 작동하려면 비공개 모임 일정이 설정되어야 합니다. [비공개 모임 일정](meeting-policies-in-teams-general.md)에 대해 자세히 알아보세요.

교육 테넌트 학생의 경우 이 정책은 기본적으로 꺼져 있습니다. 학생을 위한 비공개 모임 예약을 사용하도록 설정하는 방법에 대한 자세한 내용은 [교육용 Teams 정책 및 정책 패키지를 참조하세요](policy-packages-edu.md).

#### <a name="who-can-register"></a>등록할 수 있는 사용자

> [!NOTE]
> 이 정책은 새 웨비나 환경에는 적용되지 않습니다. 새 웨비나 환경에 등록할 수 있는 사용자를 구성하려면 [PowerShell을 사용하여 새 웨비나 환경 구성](#configure-the-new-webinar-experience-with-powershell)에 표시된 대로 를 사용합니다`Set-CsTeamsEventsPolicy -EventAccessType`.

이 정책은 모임 등록으로만 웨비나를 등록하고 참석할 수 있는 사용자를 제어합니다. 이 정책에는 **모임 등록** 이 켜져 있는 경우에만 사용할 수 있는 두 가지 옵션이 있습니다. 기본적으로 **등록할 수 있는 사람은** **모두** 로 설정됩니다.

**모든 사용자를** 선택하면 익명 사용자를 포함한 모든 사용자가 웨비나에 등록하고 참석할 수 있습니다. **조직의 모든 사용자를** 선택하는 경우 조직의 사용자만 웨비나에 등록하고 참석할 수 있습니다. 모임 등록이 꺼져 있으면 등록 **할 수 있는 사람** 설정을 사용할 수 없으며 아무도 웨비나에 등록할 수 없습니다.

**등록할 수 있는 사용자의** 기본값은 교육 테넌트 **에서 조직의 모든 사람** 입니다. 자세한 내용은 [교육용 Teams 정책 마법사](easy-policy-setup-edu.md)를 참조하세요.

## <a name="collect-webinar-and-meeting-registration-attendance"></a>웨비나 및 모임 등록 참석 수집

**모임 모임** > **정책** 아래의 Teams 관리 센터를 사용하여 **참여 보고서를** 켤 수 있습니다.

이 상태가 되면 이끌이는 설정한 웨비나 또는 모임에 등록하고 참석한 사람에 대한 보고서를 볼 수 있습니다. 이 정책은 기본적으로 설정됩니다. 자세한 내용은 [Teams의 모임 정책 - 참여 보고서를 참조하세요](meeting-policies-in-teams-general.md#engagement-report). 최종 사용자 환경에 대한 자세한 내용은 [모임 참석 보고서 보기 및 다운로드](https://support.microsoft.com/office/ae7cf170-530c-47d3-84c1-3aedac74d310)를 참조하세요.

PowerShell에서 **AllowEngagementReport** 매개 변수를 사용하여 이를 켤 수 있습니다. 이 정책은 기본적으로 설정됩니다. 해제하려면 PowerShell에서 다음 명령을 실행합니다.

```powershell
Set-CsTeamsMeetingPolicy -Identity <policy name> -AllowEngagementReport Disabled
```

cmdlet에 대한 자세한 내용은 [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) 를 참조하세요.

## <a name="turn-off-webinars"></a>웨비나 끄기

PowerShell을 사용하여 웨비나를 끌 수 있습니다. 그러면 모임 등록만 있는 웨비나뿐만 아니라 새 웨비나 환경도 해제됩니다.

다음 PowerShell 스크립트를 사용하여 웨비나를 끕니다.

```powershell
Set-CsTeamsMeetingPolicy -Identity <policy name> -AllowMeetingRegistration $False
Set-CSTeamsEventsPolicy -Identity <policy name> -AllowWebinars Disabled
```

## <a name="related-topics"></a>관련 주제

- [Teams의 모임 정책 - 일반](meeting-policies-in-teams-general.md)
- [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)
- [Set-CsTeamsEventsPolicy](/powershell/module/teams/set-csteamseventspolicy)
