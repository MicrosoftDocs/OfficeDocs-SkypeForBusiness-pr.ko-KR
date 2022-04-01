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
ms.openlocfilehash: 930f4b7a311acc7c34e60b7916071d10349c0313
ms.sourcegitcommit: 2388838163812eeabcbd5331aaf680b79da3ccba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/31/2022
ms.locfileid: "64592893"
---
# <a name="shifts-connectors"></a>Shifts 커넥터

## <a name="overview"></a>개요

Shifts 커넥터를 사용하면 WFM(인력 관리) 시스템과 Microsoft Teams 관리 도구인 Shifts를 통합할 수 있습니다. 연결을 설정한 후 프런트라인 작업자는 Shifts 내에서 WFM 시스템에서 일정을 원활하게 보고 관리할 수 있습니다.

WFM 시스템을 연결하여 Teams 일선 직원에게 일정을 보다 효과적으로 관리하고 일상적인 프로세스를 간소화하여 참여도와 생산성을 높이는 데 도움이 됩니다. 프런트라인 작업자는 어디에서나 모든 디바이스에서 작업을 완료해야 하는 일선 작업자의 계획, 통신 및 공동 작업의 한 곳을 사용할 수 있습니다.

관리되는 오픈 소스 Shifts 커넥터를 제공합니다. 이 문서에서는 Shifts 커넥터와 작동 방식에 대한 개요를 제공합니다.

## <a name="how-shifts-connectors-work"></a>Shifts 커넥터 작동 방식

커넥터는 WFM 시스템과 Shifts 간에 일정 데이터를 동기화하여 조직의 일정을 Teams. Shifts는 일선 작업자가 자신의 일과일정 요구에 참여하는 위치입니다. WFM 시스템은 비즈니스 규칙, 규정 준수 및 인텔리전스에 대한 레코드 시스템입니다.

커넥터를 통해 데이터 흐름을 통해 일정을 항상 최신으로 확인할 수 있습니다. WFM 시스템의 일정이 Shifts에 동기화됩니다. 또한 Shifts의 일정에 대한 변경 내용은 실시간으로 WFM 시스템에 다시 동기화됩니다. 레코드 시스템으로 모든 비즈니스 규칙은 Shifts에 데이터가 저장되기 전에 WFM 시스템에 의해 적용됩니다.

## <a name="managed-shifts-connectors"></a>Managed Shifts 커넥터

Managed Shifts 커넥터는 파트너와 공동으로 개발된 커넥터입니다. 관리되는 커넥터는 당사 또는 파트너가 호스팅하고 관리합니다. 관리되는 커넥터를 사용하려면 최소한의 설정만 필요합니다.

### <a name="microsoft-teams-shifts-connector-for-blue-yonder"></a>Microsoft Teams용 Shifts 커넥터
<a name="blue_yonder"> </a>

Blue Yonder용 Teams Shifts 커넥터는 Microsoft에서 호스팅하고 관리하는 첫 번째 제품입니다. 이 커넥터를 사용하면 Shifts를 Blue Yonder WFM(Blue Yonder WFM) 버전 2020.3, 2021.1 또는 2021.2와 통합하여 일정을 관리하고 최신으로 유지할 수 있습니다.  

> [!NOTE]
> Blue Yonder WFM 버전 2020.3 또는 2021.1이 있는 경우 2020.3.0.4 또는 2021.1.0.3 패치를 적용합니다. 이 패치는 사용자가 Shifts에서 영구 오류 메시지를 수신하는 문제를 해결합니다. 또한 사용자가 Shifts에서 가용성을 업데이트하지 못하게 하는 문제를 해결합니다.

:::image type="content" source="../../media/shifts-connector-blue-yonder.png" alt-text="모바일 디바이스의 Shifts에서 교환 요청, 데스크톱의 Teams 요청 및 Blue Yonder WFM의 일정을 보여주는 스크린샷입니다." lightbox="../../media/shifts-connector-blue-yonder.png":::

프런트라인 관리자는 다음을 할 수 있습니다.

- Blue Yonder WFM에서 교대 근무 및 일정을 게시하고 Shifts에서 볼 수 있습니다.
- Blue Yonder WFM에서 열린 교대 근무를 만들고 관리하고 할당하고 Shifts에서 볼 수 있습니다.
- Shifts의 Blue Yonder WFM에서 만든 열린 교대 근무를 할당합니다.
- Blue Yonder WFM에서 시간 끄기, 편집 및 삭제 및 Shifts 보기
- Blue Yonder WFM 및 Shifts에서 작업자의 일정 요청을 보고 승인합니다.
- Blue Yonder WFM에서 작업자 가용성을 설정하고 업데이트하고 Shifts에서 보기를 업데이트합니다.

프런트라인 작업자는 다음을 할 수 있습니다.

- Shifts에서 자신의 팀과 팀의 교대 근무 및 일정을 참조합니다.
- Shifts에서 시간 끄기, 교대 근무 열기 및 교환 교대 근무를 요청합니다.
- Shifts에서 가용성을 설정합니다.

현재 다음 작업은 지원되지 않습니다.

- Shifts에서 교대 근무를 추가, 편집, 삭제, 저장 또는 게시합니다.
- Shifts에서 시간을 추가, 편집, 삭제, 저장 또는 게시합니다.
- Shifts에서 열린 교대 근무를 추가, 편집, 삭제, 저장 또는 게시합니다.

프런트라인 관리자 또는 근무자는 Shifts에서 이러한 작업을 수행하기 위해 할 때 해당 작업이 지원되지 않는다는 메시지를 받게 됩니다.

#### <a name="example-scenario"></a>시나리오 예

관리자인 Eden은 Blue Yonder WFM에서 일정을 게시합니다. 이 일정은 커넥터를 통해 Teams Shifts에 동기화됩니다. 직원인 Alex는 모바일 장치에서 Teams 알림을 받을 수 있으며 일정 및 할당된 교대 근무를 확인합니다.

Alex는 시간을 끄고 Shifts를 사용하여 하루를 요청해야 합니다. 요청은 실시간으로 커넥터를 통해 Blue Yonder WFM으로 전송됩니다. Blue Yonder WFM은 요청이 비즈니스 규칙을 준수하고 요청이 생성되도록 합니다. Eden은 Blue Yonder WFM에서 요청을 보고 승인하고 승인을 Teams. (Eden은 Shifts에서 요청을 보고 승인할 수 있습니다. Alex는 Teams 요청이 승인되고 업데이트된 일정을  보기로 알 수 있습니다.

Alex는 동료와 교대 근무를 바꾸고자 합니다. Shifts에서 Alex는 Blue Yonder WFM의 비즈니스 규칙에 따라 교환할 수 있는 모든 교대 근무 목록이 표시됩니다. Alex는 현재 Gena에 할당된 교대 근무를 선택했습니다. Gena는 모바일 디바이스에서 Teams 알림을 받아 교환 요청을 수락합니다. Eden은 Shifts에서 요청을 보고 승인하고 승인을 Blue Yonder WFM에 동기화합니다. (Eden은 Blue Yonder WFM에서 요청을 보고 승인할 수 있습니다. Alex 및 Gena는 업데이트된 일정을 Teams 알림을 습니다.

#### <a name="set-up-a-connection"></a>연결 설정

커넥터를 사용하여 Shifts를 Blue Yonder WFM과 통합하는 데는 몇 단계가 필요합니다. 연결선의 Shifts 커넥터 마법사를 사용하여 Microsoft 365 관리 센터 빠르게 설정할 수 있습니다. 마법사는 선택한 설정에 따라 커넥터를 구성하고 연결을 만듭니다. PowerShell을 사용하려면 연결에 사용할 수 있는 PowerShell 스크립트도 제공합니다.

단계별 지침은 다음을 참조하세요.

- [Shifts 커넥터 마법사를 사용하여 Shifts를 Blue Yonder Workforce Management에 연결](shifts-connector-wizard.md)
- [PowerShell을 사용하여 Shifts를 Blue Yonder Workforce Management에 연결](shifts-connector-blue-yonder-powershell-setup.md)

연결을 설정한 후 PowerShell을 사용하여 필요할 때 연결 설정을 업데이트하고 변경할 수 있습니다. 커넥터 자체에 대해 업그레이드 또는 유지 관리에 대해 걱정할 필요가 없습니다. 이를 관리합니다.

### <a name="reflexis-shifts-connector-for-microsoft-teams"></a>Reflexis Shifts 커넥터를 Microsoft Teams

Reflexis Shifts 커넥터는 Microsoft Teams 호스트되고 관리됩니다. 이 커넥터를 사용하면 Shifts를 Reflexis WFM 시스템과 통합하여 일정을 관리하고 최신으로 유지할 수 있습니다.

프런트라인 작업자는 작업의 Shifts에서 일정에 액세스할 수 Teams 있으며 해당 요청은 Shifts에서 RWS(Reflexis Workforce Scheduler)로 동기화됩니다. RWS에서 만든 요청 및 교대 근무의 상태는 Teams.

:::image type="content" source="../../media/shifts-connector-reflexis.png" alt-text="모바일 디바이스의 교대 근무 목록과 Reflexis의 일정을 보여주는 스크린샷." lightbox="../../media/shifts-connector-reflexis.png":::

프런트라인 관리자는 다음을 할 수 있습니다.

- Reflexis에서 교대 근무 및 일정을 게시하고 Shifts에서 볼 수 있습니다.
- Reflexis 및 Shifts에서 교대 근무를 편집합니다.
- Reflexis 및 Shifts에서 열린 교대 근무를 만들고 관리하고 할당합니다.
- Reflexis 및 Shifts에서 작업자의 일정 요청을 보고 승인합니다.

프런트라인 작업자는 다음을 할 수 있습니다.

- Shifts에서 자신의 팀과 팀의 교대 근무 및 일정을 참조합니다.
- Shifts에서 시간 끄기, 교대 근무 열기 및 교환 및 제품 교대 근무를 요청합니다.

자세한 내용은 으로 이동합니다 https://connect.zebra.com/microsoft-connectors.

## <a name="open-source-shifts-connectors"></a>오픈 소스 Shifts 커넥터

오픈 소스 Shifts 커넥터는 Shifts api를 사용하여 구축된 커뮤니티 [Graph 통합입니다](/graph/api/resources/shift). 다음 오픈 소스 커넥터를 사용할 수 있습니다.

- Kronos-to-Teams WFC On-프레미스
- JDA-Teams Shifts 커넥터(Blue Yonder 버전 2017에서 2020.2)

각 커넥터에는 자세한 배포 및 구성 지침이 제공됩니다. Azure Resource Manager(ARM) 배포 스크립트를 포함하여 모든 필요한 서비스를 호스트할 수 Microsoft Azure. 소스 코드 및 배포 스크립트는 리포지토리에서 다운로드할 [GitHub 있습니다](https://github.com/OfficeDev/Microsoft-Teams-Shifts-WFM-Connectors). 필요에 맞게 배포하거나 사용자 지정하거나 확장할 수 있습니다.

자세한 내용은 [프로덕션 준비 Shifts 커넥터를 참조합니다](/microsoftteams/platform/samples/shifts-wfm-connectors).

## <a name="related-articles"></a>관련 기사

- [Shifts 앱 관리](manage-the-shifts-app-for-your-organization-in-teams.md)
