---
title: Teams의 교대 근무
description: 일정 관리 도구인 Shifts를 설정하고 관리하는 데 필요한 관리자 Teams.
ms.topic: conceptual
author: LanaChin
ms.author: v-lanachin
audience: admin
manager: samanro
f1.keywords:
- NOCSH
ms.service: msteams
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
- microsoftcloud-healthcare
- microsoftcloud-retail
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
- Microsoft Cloud for Retail
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-jun2020
ms.openlocfilehash: 59e62ad1278c2703402a1186d198ae3ad877be63
ms.sourcegitcommit: 2388838163812eeabcbd5331aaf680b79da3ccba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/31/2022
ms.locfileid: "64592774"
---
# <a name="shifts-for-teams"></a>Teams의 교대 근무

작업의 일정 관리 도구인 Shifts는 Teams 일선 인력을 연결하고 동기화합니다. 빠르고 효과적인 일정 관리 및 통신을 위해 먼저 모바일을 구축했습니다. Shifts를 통해 프런트라인 관리자와 작업자는 일정을 원활하게 관리하고 연락할 수 있습니다.

관리자는 팀에 대한 교대 근무 일정을 만들고, 업데이트하고, 관리할 수 있습니다. 교대 근무를 할당하고, 교대 근무를 추가하고, 직원의 일정 요청을 승인할 수 있습니다. 직원들은 자신의 일정과 팀의 일정을 보고, 가용성을 설정하고, 교대 근무를 바꾸거나 제안할지 요청하고, 시간을 요청하고, 시계 안과 퇴근을 할 수 있습니다.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE42FjP]

다음 리소스를 사용하여 조직에서 Shifts를 설정하고 관리하는 데 도움이 됩니다.

## <a name="set-up-and-manage-shifts"></a>Shifts 설정 및 관리

|&nbsp;  |&nbsp; |
|---------|---------|
|<img src="/office/media/icons/calendar-teams.png" alt="Calendar symbol.">   |**[Shifts 관리](shifts/manage-the-shifts-app-for-your-organization-in-teams.md)** 조직의 Shifts를 관리하는 방법에 대해 자세히 알아보습니다.         |
|<img src="/office/media/icons/users-people.png" alt="Users/people symbol.">   |**[교대 근무 관리를 위한 일정 소유자 관리](shifts/schedule-owner-for-shift-management.md)** 이 기능을 사용하면 직원을 팀 소유자로 만들지 않고도 팀 구성원의 권한을 일정 소유자로 승강할 수 있습니다.         |
|<img src="/office/media/icons/help.png" alt="Help symbol.">     | **[데이터 FAQ 이동](shifts/shifts-data-faq.md)** Shifts 데이터가 저장되는 위치 및 Shifts 데이터와 관련된 기타 항목(보존, 검색 및 암호화 포함)에 대해 자세히 알아보습니다.        |

## <a name="shifts-connectors"></a>Shifts 커넥터

WFM(타사 인력 관리) 시스템을 사용하여 계획하는 경우 관리되는 Shifts 커넥터를 통해 Shifts와 직접 통합하고 Open-source Shifts 커넥터를 사용하여 Shifts Graph SDK를 통해 직접 통합할 수 있습니다. 연결을 설정한 후 프런트라인 작업자는 Shifts 내에서 WFM 시스템에서 일정을 원활하게 보고 관리할 수 있습니다.

|&nbsp;  |&nbsp;  |
|---------|---------|
|<img src="/office/media/icons/connector-teams.png" alt="Connector symbol.">     | **[Shifts 커넥터 개요](shifts/shifts-connectors.md)** Shifts 커넥터와 작동 방식에 대한 개요를 참조하세요. 사용 가능한 관리형 및 오픈 소스 커넥터 및 지원되는 WFM 시스템에 대해 자세히 알아보습니다.   |
|<img src="/office/media/icons/connector-teams.png" alt="Connector symbol.">     | **[Managed Shifts 커넥터](shifts/shifts-connectors.md#managed-shifts-connectors)** 파트너와 공동으로 개발된 Managed Shifts 커넥터는 당사 또는 파트너에 의해 호스트되고 관리됩니다. 자세한 내용은 Microsoft Teams용 [Blue Yonder](shifts/shifts-connectors.md#microsoft-teams-shifts-connector-for-blue-yonder) 및 [Reflexis Shifts 커넥터용 Shifts](shifts/shifts-connectors.md#reflexis-shifts-connector-for-microsoft-teams) 커넥터 Microsoft Teams.    |
|   | **[Shifts 커넥터 마법사를 사용하여 Shifts를 Blue Yonder Workforce Management에 연결](shifts/shifts-connector-wizard.md)** 다음의 Shifts 커넥터 Microsoft 365 관리 센터 WFM 시스템에 대한 연결을 빠르게 설정할 수 있습니다. 현재 마법사는 Blue Yonder Teams Shifts 커넥터를 지원하여 Shifts를 Blue Yonder Workforce Management와 통합합니다.
|  | **[PowerShell을 사용하여 Shifts를 Blue Yonder Workforce Management에 연결](shifts/shifts-connector-blue-yonder-powershell-setup.md)** PowerShell을 사용하여 Blue Yonder용 Shifts Teams 통해 Blue Yonder Workforce Management에 대한 연결을 설정하는 방법에 대해 알아보습니다.         |
|   | **[PowerShell을 사용하여 Blue Yonder Workforce Management에 대한 Shifts 연결을 관리합니다.](shifts/shifts-connector-powershell-manage.md)** Shifts 커넥터 마법사 또는 PowerShell을 통해 설정한 후 PowerShell을 사용하여 Shifts 연결을 Blue Yonder Workforce Management에 관리하는 방법에 대한 지침을 얻습니다.
|<img src="/office/media/icons/api.png" alt="Three gears - API.">    | **[오픈 소스 Shifts 커넥터](/microsoftteams/platform/samples/shifts-wfm-connectors)** 커뮤니티 기반 오픈 소스 [](https://github.com/OfficeDev/Microsoft-Teams-Shifts-WFM-Connectors) 커넥터를 사용하여 Shifts api 및 SDK를 통해 Kronos 또는 JDA WFM 시스템을 통합하는 Graph 방법을 알아보습니다.    |

## <a name="shifts-extensions"></a>Shifts 확장

|&nbsp;|&nbsp;|
| ------------- | ------------- |
| <img src="/office/media/icons/api.png" alt="Three gears - API."> | **[Shift Graph API](/graph/api/resources/shift)** shifts Graph API를 사용하면 Shifts 데이터를 WFM(외부 인력 관리) 시스템과 통합할 수 있습니다. 백 엔드에서 사용자 지정 Shifts 환경을 유연하게 빌드하는 동시에 사용자에게 다양한 프런트 엔드 환경을 Teams.             |
|<img src="/office/media/icons/process-flow-teams.png" alt="Process/flow chart symbol."> | **[Shifts + Power Automate](https://github.com/OfficeDev/Microsoft-Teams-Shifts-Power-Automate-Templates)** Shifts + Power Automate 정보를 받아서 다른 앱으로 사용자 지정 워크플로를 만들고 대규모 작업을 수행할 수 있습니다. 코드가 거의 없는 주요 프로세스를 자동화합니다. 트리거 및 템플릿은 관리자의 승인이 필요하지 않은 경우 교대 근무 요청에 대해 자동 승인을 사용하도록 설정하는 등의 다양한 시나리오를 지원합니다. |

## <a name="featured-training"></a>추천 교육

|&nbsp;|&nbsp;|&nbsp;|&nbsp;|&nbsp;|&nbsp;|
| ------------- | ------------- | ------------- | ------------- | ------------- | ------------- |
| <img src="/office/media/icons/get-started-teams.png" alt="Get started symbol.">  |  [비디오: Shifts란?](https://support.office.com/article/what-is-shifts-f8efe6e4-ddb3-4d23-b81b-bb812296b821) |<img src="/office/media/icons/clock-teams.png" alt="Clock symbol."> |  [비디오: 교대 근무 일정 만들기](https://support.microsoft.com/office/create-a-shifts-schedule-2b94ca38-36db-4a1c-8fee-f8f0fec9a984) |<img src="/office/media/icons/blocks-teams.png" alt="Blocks symbol.">|  [비디오: 교대 근무 일정 관리](https://support.microsoft.com/office/manage-and-view-a-shifts-schedule-63acda7b-ea39-441a-b1c6-c404a72e79f7) |
