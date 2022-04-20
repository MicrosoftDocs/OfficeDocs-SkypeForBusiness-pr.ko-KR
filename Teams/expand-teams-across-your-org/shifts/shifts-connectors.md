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
description: Shifts 커넥터 및 이를 사용하여 교대 근무를 인력 관리 시스템에 연결하는 방법에 대해 알아봅니다.
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 930f4b7a311acc7c34e60b7916071d10349c0313
ms.sourcegitcommit: bf0071417188b33fc23e2a420187da5024d4bd40
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/20/2022
ms.locfileid: "64592893"
---
# <a name="shifts-connectors"></a>Shifts 커넥터

## <a name="overview"></a>개요

Shifts 커넥터를 사용하면 Microsoft Teams 일정 관리 도구인 Shifts를 WFM(인력 관리) 시스템과 통합할 수 있습니다. 연결을 설정한 후 일선 작업자는 Shifts 내에서 WFM 시스템에서 일정을 원활하게 보고 관리할 수 있습니다.

WFM 시스템을 Teams 연결하면 일선 직원이 일정을 보다 효과적으로 관리하고 더 높은 참여와 생산성을 위해 일상적인 프로세스를 간소화할 수 있습니다. 일선 작업자는 모든 장치에서 어디서나 작업을 완료해야 하는 일정, 통신 및 협업을 위한 한 자리를 차지합니다.

관리형 및 오픈 소스 Shifts 커넥터를 제공합니다. 이 문서에서는 Shifts 커넥터 및 작동 방식에 대한 개요를 제공합니다.

## <a name="how-shifts-connectors-work"></a>Shifts 커넥터 작동 방식

커넥터는 WFM 시스템과 Shifts 간에 일정 데이터를 동기화하여 조직의 일정을 Teams. 교대 근무는 일선 직원들이 일정 요구에 참여하는 곳입니다. WFM 시스템은 비즈니스 규칙, 규정 준수 및 인텔리전스에 대한 기록 시스템입니다.

커넥터를 통한 데이터 흐름은 일정이 항상 최신 상태인지 확인하는 두 가지 방법입니다. WFM 시스템의 일정은 Shifts와 동기화됩니다. 또한 Shifts의 일정에 대한 변경 내용은 실시간으로 WFM 시스템에 다시 동기화됩니다. 레코드 시스템으로, 데이터가 Shifts에 저장되기 전에 모든 비즈니스 규칙이 WFM 시스템에 의해 적용됩니다.

## <a name="managed-shifts-connectors"></a>관리형 Shifts 커넥터

관리형 Shifts 커넥터는 파트너와 공동으로 개발된 커넥터입니다. 관리형 커넥터는 당사 또는 파트너가 호스트하고 관리합니다. 관리형 커넥터를 사용하면 최소한의 설정만 필요합니다.

### <a name="microsoft-teams-shifts-connector-for-blue-yonder"></a>Blue Yonder용 Microsoft Teams Shifts 커넥터
<a name="blue_yonder"> </a>

Blue Yonder용 Teams Shifts 커넥터는 Microsoft에서 호스트하고 관리하는 자사 제품입니다. 이 커넥터를 사용하면 Shifts를 Blue Yonder WFM(Blue Yonder WFM) 버전 2020.3, 2021.1 또는 2021.2와 통합하여 일정을 관리하고 최신 상태로 유지할 수 있습니다.  

> [!NOTE]
> Blue Yonder WFM 버전 2020.3 또는 2021.1이 있는 경우 2020.3.0.4 또는 2021.1.0.3 패치를 적용합니다. 이 패치는 사용자가 Shifts에서 영구 오류 메시지를 받는 문제를 해결합니다. 또한 사용자가 Shifts에서 가용성을 업데이트하지 못하게 하는 문제를 해결합니다.

:::image type="content" source="../../media/shifts-connector-blue-yonder.png" alt-text="모바일 디바이스의 Shifts에서 교환 요청, 데스크톱의 Teams 승인 요청 및 Blue Yonder WFM의 일정을 보여 주는 스크린샷" lightbox="../../media/shifts-connector-blue-yonder.png":::

최전방 관리자는 다음을 수행할 수 있습니다.

- Blue Yonder WFM에서 교대 근무 및 일정을 게시하고 Shifts에서 봅니다.
- Blue Yonder WFM에서 열린 교대 근무를 만들고, 관리하고, 할당하고, Shifts에서 봅니다.
- Shifts의 Blue Yonder WFM에서 만든 열린 교대 근무를 할당합니다.
- Blue Yonder WFM에서 휴가를 만들고, 편집하고, 삭제하고, Shifts에서 봅니다.
- Blue Yonder WFM 및 Shifts 모두에서 작업자의 일정 요청을 보고 승인합니다.
- Blue Yonder WFM에서 작업자 가용성을 설정하고 업데이트하고 Shifts에서 봅니다.

일선 근로자는 다음을 수행할 수 있습니다.

- 교대 근무에서 자신과 팀의 교대 근무 및 일정을 확인하세요.
- Shifts에서 휴가를 요청하고, 교대 근무를 열고, 교대 근무를 교환합니다.
- Shifts에서 가용성을 설정합니다.

현재 지원되지 않는 작업은 다음과 같습니다.

- Shifts에서 교대 근무를 추가, 편집, 삭제, 저장 또는 게시합니다.
- Shifts에서 휴가를 추가, 편집, 삭제, 저장 또는 게시합니다.
- Shifts에서 열린 교대 근무를 추가, 편집, 삭제, 저장 또는 게시합니다.

최전방 관리자 또는 작업자가 Shifts에서 이러한 작업을 수행하려고 하면 작업이 지원되지 않는다는 메시지를 받게 됩니다.

#### <a name="example-scenario"></a>시나리오 예

매니저 인 Eden은 커넥터를 통해 Teams Shifts와 동기화되는 Blue Yonder WFM에서 일정을 게시합니다. 직원인 Alex는 모바일 장치에서 Teams 알림을 받고 일정과 할당된 교대 근무를 확인합니다.

Alex는 잠시 쉬어야 하며 교대 근무를 사용하여 하루를 쉬는 것을 요청합니다. 요청은 커넥터를 통해 실시간으로 Blue Yonder WFM으로 전송됩니다. Blue Yonder WFM은 요청이 비즈니스 규칙을 준수하고 요청이 생성되도록 합니다. Eden은 Blue Yonder WFM에서 요청을 보고 승인하며 승인은 Teams 동기화됩니다. (Eden은 Shifts에서 요청을 보고 승인할 수도 있습니다). Alex는 Teams 요청이 승인되었다는 알림을 받고 업데이트된 일정을 확인합니다.

알렉스는 동료와 교대조를 바꾸고 싶어한다. Shifts에서 Alex는 Blue Yonder WFM의 비즈니스 규칙에 따라 교환할 수 있는 모든 교대 근무 목록을 확인합니다. Alex는 현재 Gena에 할당된 교대조를 선택합니다. Gena는 모바일 디바이스에서 Teams 알림을 받고 교환 요청을 수락합니다. Eden은 Shifts에서 요청을 보고 승인하며 승인은 Blue Yonder WFM과 동기화됩니다. (Eden은 Blue Yonder WFM에서 요청을 보고 승인할 수도 있습니다). Alex와 Gena는 Teams 알림을 받고 업데이트된 일정을 확인합니다.

#### <a name="set-up-a-connection"></a>연결 설정

커넥터를 사용하여 Shifts를 Blue Yonder WFM과 통합하는 데는 몇 단계만 걸립니다. Microsoft 365 관리 센터 Shifts 커넥터 마법사를 사용하여 신속하게 연결을 설정할 수 있습니다. 마법사는 선택한 설정에 따라 커넥터를 구성하고 연결을 만듭니다. PowerShell을 사용하려는 경우 연결에 사용할 수 있는 PowerShell 스크립트도 제공합니다.

단계별 지침은 다음을 참조하세요.

- [Shifts 커넥터 마법사를 사용하여 Shifts를 Blue Yonder Workforce Management에 연결](shifts-connector-wizard.md)
- [PowerShell을 사용하여 Blue Yonder Workforce Management에 교대 근무 연결](shifts-connector-blue-yonder-powershell-setup.md)

연결이 설정되면 언제든지 PowerShell을 사용하여 필요에 따라 연결 설정을 업데이트하고 변경할 수 있습니다. 커넥터 자체에 관해서는 업그레이드 또는 유지 관리에 대해 걱정할 필요가 없습니다. 우리는 그것을 돌봅니다.

### <a name="reflexis-shifts-connector-for-microsoft-teams"></a>Microsoft Teams 대한 Reflexis Shifts 커넥터

Microsoft Teams 대한 Reflexis Shifts 커넥터는 Zebra에서 호스트되고 관리됩니다. 이 커넥터를 사용하면 Shifts를 Reflexis WFM 시스템과 통합하여 일정을 관리하고 최신 상태로 유지할 수 있습니다.

일선 작업자는 Teams 교대 근무 일정에 액세스할 수 있으며, 해당 요청은 Shifts에서 Reflexis RWS(Workforce Scheduler)로 동기화됩니다. RWS에서 만든 요청 및 교대 근무의 상태는 Teams Shifts와 동기화됩니다.

:::image type="content" source="../../media/shifts-connector-reflexis.png" alt-text="모바일 디바이스의 교대 근무 목록과 Reflexis의 일정을 보여 주는 스크린샷" lightbox="../../media/shifts-connector-reflexis.png":::

최전방 관리자는 다음을 수행할 수 있습니다.

- Reflexis에서 교대 근무 및 일정을 게시하고 Shifts에서 볼 수 있습니다.
- Reflexis 및 Shifts 모두에서 교대 근무를 편집합니다.
- Reflexis 및 Shifts 모두에서 열린 교대 근무를 만들고, 관리하고, 할당합니다.
- Reflexis 및 Shifts 모두에서 작업자의 일정 요청을 보고 승인합니다.

일선 근로자는 다음을 수행할 수 있습니다.

- 교대 근무에서 자신과 팀의 교대 근무 및 일정을 확인하세요.
- 교대 근무를 요청하고 교대 근무를 열고 교대 근무를 교환하고 교대 근무를 제공합니다.

자세한 내용을 보려면 .로 이동하세요 https://connect.zebra.com/microsoft-connectors.

## <a name="open-source-shifts-connectors"></a>오픈 소스 Shifts 커넥터

오픈 소스 Shifts 커넥터는 [Shifts Graph API](/graph/api/resources/shift)를 기반으로 하는 커뮤니티 기반 통합입니다. 사용할 수 있는 오픈 소스 커넥터는 다음과 같습니다.

- Kronos-Teams WFC 온-프레미스
- JDA-Teams Shifts 커넥터(Blue Yonder 버전 2017~2020.2)

각 커넥터에는 자세한 배포 및 구성 지침이 제공됩니다. 여기에는 Microsoft Azure 필요한 모든 서비스를 호스트할 수 있는 ARM(Azure Resource Manager) 배포 스크립트가 포함됩니다. 소스 코드 및 배포 스크립트는 [GitHub 리포지토리](https://github.com/OfficeDev/Microsoft-Teams-Shifts-WFM-Connectors)에서 다운로드할 수 있습니다. 필요에 맞게 배포하거나 사용자 지정하거나 확장할 수 있습니다.

자세한 내용은 [프로덕션 지원 Shifts 커넥터를 참조하세요](/microsoftteams/platform/samples/shifts-wfm-connectors).

## <a name="related-articles"></a>관련 기사

- [Shifts 앱 관리](manage-the-shifts-app-for-your-organization-in-teams.md)
