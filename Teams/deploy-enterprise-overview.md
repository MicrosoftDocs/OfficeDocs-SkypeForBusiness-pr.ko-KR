---
title: Microsoft Teams 엔터프라이즈 배포 개요
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
description: Microsoft Teams의 엔터프라이즈 기능을 배포하는 방법을 알아봅니다.
ms.localizationpriority: high
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-deployteams
appliesto:
- Microsoft Teams
ms.openlocfilehash: f6e6a2835df6f00bc9103594b1cfe5ae011c6960
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58617424"
---
# <a name="teams-enterprise-deployment-overview"></a>Teams 엔터프라이즈 배포 개요

중견 기업/대기업인 경우, 사용자에게 서비스를 배포할 방법, Microsoft Teams 클라이언트를 배포할 방법, 네트워크 디자인이 실시간 커뮤니케이션 품질에 미치는 영향 등을 고려해야 합니다. 조직 내 Teams 배포 계획 수립에 도움이 될만한 문서에 대한 포인터는 다음 섹션을 확인하세요.

> [!NOTE]
> 아직 완료하지 않은 경우, Teams 배포 파일럿을 시작하는 것이 좋습니다. 파일럿을 통해 사용자와 일부 얼리어답터는 계획 및 최종 배포 전에 Teams와 Teams의 기능에 익숙해질 수 있습니다. 파일럿을 시작하는 방법에 대한 자세한 내용은 [Microsoft Teams 시작](get-started-with-teams-quick-start.md)을 참조하세요.

섹션을 읽고 조직에 Teams 배포를 시작할 준비가 되었다면 [기업에서 Microsoft Teams 설정](deploy-enterprise-setup.md)을 참조하세요.

## <a name="architecture"></a>아키텍처

Teams는 Microsoft 365와 긴밀하게 통합되어 있으며 채팅, 파일 공유, 모임, 전화, 비디오 스트리밍 등 다양한 기능을 사용할 수 있습니다. Teams를 배포하기 전에 [Microsoft Teams IT 아키텍처 및 전화 솔루션 포스터](teams-architecture-solutions-posters.md)를 확인하여 Teams가 다른 Microsoft 365 앱과 작동하는 방식을 확인하여 사용자를 위한 완벽한 공동 작업 환경을 만드세요.

## <a name="workloads"></a>워크로드

Teams에는 서로 독립적으로 구현할 수 있는 세 가지 워크로드(**채팅, 팀 및 채널**, **모임 및 회의**, **전화 시스템 및 공중 전화망(PSTN) 연결)** 이 있습니다. 각 워크로드에는 해당 워크로드에 대한 정보를 더 쉽게 찾을 수 있도록 문서에 자체 섹션이 있습니다. 여기에는 배포 계획 정보가 포함됩니다.

배포하려는 워크로드에 대한 배포 계획 정보를 확인하려면 다음 문서를 참조하세요.

- [채팅, 팀 및 채널](deploy-chat-teams-channels-microsoft-teams-landing-page.md)
- [모임 및 회의](deploy-meetings-microsoft-teams-landing-page.md)
- [전화 시스템 및 공중 전화망(PSTN) 연결](cloud-voice-landing-page.md)

## <a name="network-planner"></a>네트워크 플래너

Teams에 대한 네트워크 계획은 사용자 수가 많거나, 네트워크 규모가 복잡하거나 또는 둘 다에 해당하는 경우 매우 중요합니다. Teams는 음성 통화 및 화상 회의를 지원하며, 두 팀 모두 실시간 통신을 통해 사용자에게 최상의 환경을 제공합니다. 네트워크는 다음과 같아야 합니다.

- 동시 음성 통화, 화상 회의, 모임, 화면 공유 수를 수용할 수 있는 충분한 대역폭양이 있어야 합니다.
- 실시간 통신 프로토콜을 지원하는 네트워크 하드웨어가 있어야 합니다.
- 네트워크의 장치, Microsoft 365 서비스 및 외부 사용자 간에 필요한 네트워크 포트를 허용해야 합니다.

Teams 네트워크 요구 사항을 이해하는 데 도움이 되는 문서는 다음 문서를 참조하세요.

- [Microsoft Teams에 대한 조직의 네트워크 준비](prepare-network.md)
- [Teams 또는 비즈니스용 Skype Online 용 프록시 서버](proxy-servers-for-skype-for-business-online.md)

계획에 도움을 줄 수 있도록 Teams에는 네트워크 플래너가 포함됩니다. 네트워크 플래너는 사용자가 있는 사용자의 수와 유형, 조직에 있는 사이트 수, 네트워크 연결의 대역폭양 등에 대해 질문합니다. 네트워크 플래너는 이 정보를 사용하여 각 활동에 대한 대역폭 요구 사항과 권장 사항을 표시하는 보고서를 만듭니다.

 > [!div class="nextstepaction"]
> [네트워크 플래너로 이동](https://admin.teams.microsoft.com/networkplanner/organization)

(네트워크 플래너를 열려는 경우, [Microsoft 365 전역 관리자](/microsoft-365/admin/add-users/about-admin-roles#commonly-used-microsoft-365-admin-center-roles)여야 합니다.)

네트워크 플래너 작동 방식에 대한 자세한 내용은 [Microsoft Teams용 네트워크 플래너 사용](network-planner.md)을 참조하세요.

네트워크 플래너가 네트워크를 계획하는 방법에 대한 예제를 확인하려면 [네트워크 플래너 사용 - 예제 시나리오](tutorial-network-planner-example.yml)를 참조하세요.

## <a name="teams-advisor"></a>Teams 어드바이저

Teams 어드바이저는 팀, 채널, 파일 공유 및 Planner를 모아 조직의 배포 프로젝트를 만드는 Teams 내 솔루션입니다. Teams 어드바이저는 사용자가 선택한 워크로드(예: 채팅, 팀 및 채널)와 관련된 프로젝트 계획을 작성합니다. 이 작업에는 배포 중에 수행해야 하는 권장 작업이 포함됩니다. 각 작업에는 프로세스를 안내하는 지침, 제안 및 관련 문서에 대한 링크가 포함되어 있습니다. 한 개 이상의 사용자에게 작업을 쉽게 할당하고 각 작업에 대한 시작 및 종료 날짜를 지정할 수 있습니다.

> [!TIP]
> Microsoft Learn에서 [Teams Advisor를 사용하여 원격 설치](/learn/modules/m365-teams-rollout-using-advisor/) 모듈을 완료하여 Teams 어드바이저를 사용하여 Teams 배포를 계획하는 방법을 참조하세요.

> [!div class="nextstepaction"]
> [Teams 어드바이저로 이동](https://admin.teams.microsoft.com/teams-deployment)

(Teams 어드바이저를 열려는 경우, [Microsoft 365 전역 관리자](/microsoft-365/admin/add-users/about-admin-roles#commonly-used-microsoft-365-admin-center-roles)여야 합니다.)

Teams 어드바이저의 작동 방법에 대한 자세한 내용은 [Teams 어드바이저를 사용하여 Microsoft Teams 배포](use-advisor-teams-roll-out.md)를 참조하세요.

## <a name="lifecycle-and-governance-planning"></a>수명 주기 및 거버넌스 계획

Teams 배포를 계획할 때 조직의 팀, 채널, 파일 수명 주기 등을 고려해야 합니다. 또한 저장할 정보 유형에 대해 고민해야 합니다. Teams는 특정 프로젝트나 부서에 대해 만들어지거나 전체 조직의 중앙 리소스로 사용될 수 있습니다. 다른 요구 사항을 가진 사용에는 다음과 같은 질문이 제기될 수 있습니다.

- 팀이 얼마나 유지될 것인가?
- 누가 팀과 채널을 소유하고 관리해야 하나?
- 일부 팀에 적용되는 특정 규정 준수 요구 사항을 다른 팀에도 적용해야 하나?
- 사용자가 올바른 팀을 식별하는 데 도움이 되는 이름 정책이 있어야 하나?

초기 배포의 일부로 정책 및 지침을 만들면 사용자가 필요한 정보를 찾을 수 있도록 하는 데 도움이 됩니다. 그러나 적절한 정책은 정보 누출로부터 조직을 보호하고, 규정 요구 사항을 준수하고, 보관 목적으로 필요한 정보를 보존하는 데 도움이 됩니다.

Teams의 수명 주기 관리 및 거버넌스에 대한 자세한 내용은 다음을 참조하세요.

- [Teams에서 수명 주기 관리 계획](plan-teams-lifecycle.md)
- [Teams에서 거버넌스 계획](plan-teams-governance.md)

## <a name="adoption"></a>채택

조직과 사용자가 Teams를 최대한 활용하려면 채택 프로그램이 필요합니다. 효과적인 채택 프로그램은 다음을 수행할 수 있는 얼리어답터를 동원할 수 있습니다.

- 동료와 비즈니스 또는 그룹 리더에게 Teams의 이점을 설명합니다.
- Teams가 어떻게 공동 작업을 개선하고 서로 더 쉽게 연결할 수 있는지 보는 다른 사람들에게 흥미를 유발합니다.
- 기존 비즈니스 프로세스를 평가하고 Teams가 여기에 통합될 수 있는 방법을 추천할 수 있도록 지원합니다.
- 채택 프로세스를 개선하는 데 도움이 되는 개선 사항과 문제를 배포 팀에 다시 보고합니다.

채택 프로그램 설정에 대한 자세한 내용은 [Microsoft Teams 채택](adopt-microsoft-teams-landing-page.md)을 참조하세요.