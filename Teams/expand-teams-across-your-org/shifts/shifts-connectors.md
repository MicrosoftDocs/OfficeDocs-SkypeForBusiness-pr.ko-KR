---
title: Shifts 커넥터
author: lanachin
ms.author: v-lanachin
ms.reviewer: aaku
manager: samanro
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Shifts 커넥터와 Shifts를 사용하여 Shifts를 사용자 인력 관리 시스템에 연결하는 방법에 대해 자세히 알아보습니다.
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7a5e330710fcbdbda6c82db2643e1ed7c0fa5a26
ms.sourcegitcommit: 9ef6e36eeba7db70971f4eb1a45f0ded394b1fe6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2022
ms.locfileid: "62192489"
---
# <a name="shifts-connectors"></a>Shifts 커넥터

## <a name="overview"></a>개요

Shifts 커넥터를 사용하면 WFM(인력 관리) 시스템과 Microsoft Teams 관리 도구인 Shifts를 통합할 수 있습니다. 연결을 설정한 후 프런트라인 작업자는 Shifts 내에서 WFM 시스템에서 일정을 원활하게 보고 관리할 수 있습니다.

WFM 시스템을 연결하여 Teams 일선 직원에게 일정을 보다 효율적으로 관리하고 일상적인 프로세스를 간소화하여 참여도와 생산성을 높이는 데 도움이 됩니다. 프런트라인 작업자는 어디에서나 모든 디바이스에서 작업을 완료해야 하는 일선 작업자의 계획, 통신 및 공동 작업의 한 곳을 사용할 수 있습니다.

관리되는 오픈 소스 Shifts 커넥터를 제공합니다. 이 문서에서는 Shifts 커넥터와 작동 방식에 대한 개요를 제공합니다.

## <a name="how-shifts-connectors-work"></a>Shifts 커넥터 작동 방식

커넥터는 WFM 시스템과 Shift 간에 일정 데이터를 동기화하여 조직의 일정을 Teams. Shifts는 일선 작업자가 자신의 일과일정 요구에 참여하는 위치입니다. WFM 시스템은 비즈니스 규칙, 규정 준수 및 인텔리전스에 대한 레코드 시스템입니다.

커넥터를 통해 데이터 흐름을 통해 일정을 항상 최신으로 확인할 수 있습니다. WFM 시스템의 일정이 Shifts에 동기화됩니다. 또한 Shifts의 일정에 대한 변경 내용은 실시간으로 WFM 시스템에 다시 동기화됩니다. 레코드 시스템으로 모든 비즈니스 규칙은 Shifts에 데이터가 저장되기 전에 WFM 시스템에 의해 적용됩니다.

## <a name="managed-shifts-connectors"></a>Managed Shifts 커넥터

Managed Shifts 커넥터는 파트너와 공동으로 개발된 커넥터입니다. 관리되는 커넥터는 당사 또는 파트너가 호스팅하고 관리합니다. 관리되는 커넥터를 사용하려면 최소한의 설정만 필요합니다.

### <a name="reflexis-shifts-connector-for-microsoft-teams"></a>Reflexis Shifts 커넥터를 Microsoft Teams

Reflexis Shifts 커넥터는 Microsoft Teams 호스트 및 관리됩니다. 이 커넥터를 사용하면 Shifts를 Reflexis WFM 시스템과 통합하여 일정을 관리하고 최신으로 유지할 수 있습니다.

프런트라인 작업자는 근무 시간의 Shifts에서 일정에 액세스할 수 Teams 있으며 해당 요청은 Shifts에서 RWS(Reflexis Workforce Scheduler)로 동기화됩니다. RWS에서 만든 요청 및 교대 근무의 상태는 Teams.

:::image type="content" source="../../media/shifts-connector-reflexis.png" alt-text="모바일 디바이스의 교대 근무 목록 및 Reflexis의 일정을 보여주는 스크린샷" lightbox="../../media/shifts-connector-reflexis.png":::

프런트라인 관리자는 다음을 할 수 있습니다.

- Reflexis에서 교대 근무 및 일정을 게시하고 Shifts에서 볼 수 있습니다.
- Reflexis 및 Shifts에서 교대 근무를 편집합니다.
- Reflexis 및 Shifts에서 열린 교대 근무를 만들고 관리하고 할당합니다.
- Reflexis 및 Shifts에서 작업자의 일정 요청을 보고 승인합니다.

프런트라인 작업자는 다음을 할 수 있습니다.

- Shifts에서 자신의 팀과 팀의 교대 근무 및 일정을 참조합니다.
- Shifts에서 시간 끄기, 교대 근무 열기 및 교환 및 제품 교대 근무를 요청합니다.

자세한 내용은 https://connect.zebra.com/microsoft-connectors 으로 이동합니다.

## <a name="open-source-shifts-connectors"></a>오픈 소스 Shifts 커넥터

오픈 소스 Shifts 커넥터는 Shifts api를 사용하여 구축된 커뮤니티 [Graph 통합입니다.](/graph/api/resources/shift) 다음 오픈 소스 커넥터를 사용할 수 있습니다.

- Kronos-to-Teams WFC On-프레미스
- JDA-Teams Shifts 커넥터(Blue Yonder 버전 2017에서 2020.2)

각 커넥터에는 자세한 배포 및 구성 지침이 제공됩니다. 여기에는 Azure Resource Manager(ARM) 배포 스크립트가 포함되어 모든 필요한 서비스를 호스트할 수 Microsoft Azure. 소스 코드 및 배포 스크립트는 리포지토리의 GitHub [사용할 수 있습니다.](https://github.com/OfficeDev/Microsoft-Teams-Shifts-WFM-Connectors) 필요에 맞게 배포하거나 사용자 지정하거나 확장할 수 있습니다.

자세한 내용은 [프로덕션 준비 Shifts 커넥터 를 참조합니다.](/microsoftteams/platform/samples/shifts-wfm-connectors)

## <a name="related-articles"></a>관련 기사

- [Shifts 앱 관리](manage-the-shifts-app-for-your-organization-in-teams.md)
