---
title: Advisor for Teams를 사용하여 Microsoft Teams 배포
ms.author: mikeplum
author: MikePlumleyMSFT
ms.reviewer: pkrebs
manager: serdars
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
- remotework
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: high
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.deploymentadvisor.overview
- chat-teams-channels-revamp
description: 'Advisor for Teams로 Microsoft Teams 사용을 계획하고 성공적으로 배포하세요.  '
ms.openlocfilehash: e691a224679b8026ec91ecf3b1b5c16f6016c20e
ms.sourcegitcommit: dc5b3870fd338f7e9ab0a602a44eaf9feb595b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/30/2022
ms.locfileid: "69198330"
---
# <a name="use-advisor-for-teams-to-help-you-roll-out-microsoft-teams"></a>Advisor for Teams를 사용하여 Microsoft Teams 배포

Advisor for Teams는 Microsoft Teams 배포 과정을 안내합니다. Microsoft 365 조직 환경을 평가하고 Teams를 성공적으로 배포하기 전에 업데이트 또는 수정해야 할 가장 일반적인 구성을 파악합니다. 그런 다음 Advisor for Teams는 배포하려는 각 워크로드에 대한 채널로 배포 팀(Teams에서)을 만듭니다. 서비스 관리 팀의 각 워크로드에는 각 워크로드에 대한 모든 롤아웃 작업이 포함된 포괄적인 Planner 플랜이 함께 제공됩니다.  이 Planner 플랜을 사용하여 프로젝트 관리자, Teams 관리자, 지원자, 채택 및 사용자 준비 팀 등 각각의 롤아웃 단계를 담당하는 사용자에게 작업을 할당합니다. 각 롤아웃 작업에는 해당 작업을 완료하는 데 필요한 모든 가이드 및 리소스가 포함됩니다.

Advisor for Teams는 [Teams 관리 센터](https://admin.teams.microsoft.com)의 일부입니다. 적어도 Microsoft 365 Business Basic 라이선스가 있어야 하며, Advisor for Teams에 Forms 및 Planner를 통합하는데 활용할 수 있습니다. Teams용 어드바이저의 사용을 시작하려면 대시보드의 **Teams 워크로드 배포** 위젯에서 **시작** 단추를 클릭합니다. 또는 **계획** > **Teams Advisor** 로 이동합니다.

> [!IMPORTANT]
> Advisor for Teams는 Microsoft 365 정부 기관(GCC High 또는 DoD) 배포에 사용할 수 없습니다.

Teams용 어드바이저 환경의 지도된 개요를 보려면 Microsoft Mechanics 비디오 [Microsoft Teams 배포 및 구성](https://youtu.be/o2mlsUubIO4?t=50)을 확인하세요.

## <a name="using-advisor-for-teams"></a>Advisor for Teams 사용

**Advisor for Teams를 사용하려면 Teams, Forms 및 Planner 라이선스가 필요합니다.** 그러나 Advisor for Teams를 사용하기 위해 Teams 관리자가 될 필요는 없습니다. 조직 내 누구나 사용할 수 있습니다. Advisor for Teams가 Teams 관리 센터에 있어도 관리자가 아닌 사용자가 액세스할 수 있도록 특별 권한을 설정했습니다. 테넌트 준비 상태 평가를 열려면 Teams 관리자, Teams 관리자 또는 전역 관리자이어야 합니다(이는 특수한 비관리자 역할이 평가를 기반으로 하는 Microsoft Graph API로의 액세스 권한이 없기 때문입니다).

> [!IMPORTANT]
> Teams 관리 센터의 **계획** 에 **Teams Advisor** 가 없는 경우, 사용자에게 Teams에 대한 라이선스가 없는 것입니다.

Teams용 어드바이저를 처음으로 사용하는 경우 Teams에서 사용자를 위한 배포 팀이 만들어집니다. 선택하는 각 작업에 대한 채널을 추가합니다.

> [!IMPORTANT]
> 배포 팀이 이미 만들어진 경우 또 다른 사용자가 팀을 만들려고 하면 지원 팀에 문의하라는 오류 메시지가 표시됩니다. 이는 Teams가 기존 팀과 해당 구성원에 대한 정보를 실수로 노출하는 것을 방지할 수 있습니다. 배포 팀의 소유자에게 사용자를 추가하도록 요청하거나 지원 담당자에게 도움을 요청하세요.

## <a name="available-advisor-for-teams-plans"></a>사용 가능한 Teams용 어드바이저 계획

Advisor for Teams는 현재 다음 계획을 제공합니다.

1. 채팅, 팀, 채널 및 앱
    - 테넌트 평가
    - 채택 작업을 포함한 Planner 플랜
    - Forms 사용자 설문 조사
    - Teams용 어드바이저 봇
1. 모 및 회의
    - 테넌트 평가
    - 채택 작업을 포함한 Planner 플랜
    - Forms 사용자 설문 조사
    - Teams용 어드바이저 봇
1. 비즈니스용 Skype 업그레이드
    - 테넌트 평가
    - 채택 작업을 포함한 Planner 플랜
    - Forms 사용자 설문 조사
    - Teams용 어드바이저 봇
    - 현재 비즈니스용 Skype Online 또는 비즈니스용 Skype 온-프레미스 환경을 사용하고 있는 고객을 위해 설계된 비즈니스용 Skype 업그레이드 플랜을 사용하면 더 이상 업그레이드를 진행하는 동안 어림짐작으로 수행을 하지 않아도 될 수 있게 도움을 받을 수 있습니다. 변화를 구현하는 데 입증된 성공 프레임워크를 활용하여 이 플랜은 사용자가 Teams를 이제 시작하고 있거나, 이미 비즈니스용 Skype와 함께 사용하고 있거나 혹은 업그레이드할 준비가 되었는지에 상관없이 단계별 프로세스를 안내합니다. 이 플랜은 또한 사용자를 [온라인 지침과 모범 사례](./upgrade-start-here.md), [다운로드 가능한 자산](https://aka.ms/UpgradeSuccessKit), [라이브 1: 많은 계획 워크숍](./upgrade-workshops-landing-page.yml) 그리고 성공을 지원하기 위한 추가 리소스로 연결시켜줄 것입니다.
1. 교육(교육 조직에만 표시됨)
    - 테넌트 평가
    - 채택 작업을 포함한 Planner 플랜
    - Forms 사용자 설문 조사
    - Teams용 어드바이저 봇
    - 교육 기관을 위해 설계된 교육 플랜은 교육 기관에서 팀을 배치, 채택 및 관리하는 데 도움이 됩니다.

상업적인 조직의 경우 채팅, 팀, 채널 및 앱 플랜부터 시작하는 것이 좋습니다. 교육 기관의 경우 교육 플랜부터 시작하는 것이 좋습니다. 해당 워크로드 배포가 완료되면 Teams용 어드바이저로 돌아가 **채널 추가** 를 선택하여 다음 작업을 시작하세요.



## <a name="tenant-assessment"></a>테넌트 평가

각 플랜에는 Teams를 배포하기 전에 개선이 필요할 수 있는 환경의 모든 측면을 신속히 확인하는 데 사용할 수 있는 테넌트 준비 상태 평가가 포함되어 있습니다. 평가는 필수 구성 요소와 모범 사례를 포함합니다. 각 평가 테스트에는 녹색 확인 표시 또는 주황색 경고 삼각형이 있습니다.

- <sub><img src="media/use-advisor-teams-roll-out-image2.png" alt="Green check mark"/></img></sub>녹색 확인 표시는 테넌트가 특정 테스트를 통과 했다는 의미입니다.
- <sub><img src="media/use-advisor-teams-roll-out-image1.png" alt="Yellow alert mark"/></img></sub>주황색 경고 삼각형은 조치가 필요한지의 여부를 판단하기 위해 후속 조치를 취할 것을 제안한다는 의미입니다(예: Microsoft 365 그룹 만료 정책 사용을 권장하지만 필수는 아님).

> [!IMPORTANT]
> 관리자 역할이 있는 사용자가 Teams용 어드바이저를 시작하면 모든 평가가 백그라운드에서 실행됩니다. 항목을 업데이트하거나 재구성하는 경우 최대 24시간 동안 평가에 반영되지 않을 수 있습니다.

아래의 섹션은 어떤 것이 필수 구성 요소인지 혹은 모범 사례인지와 각 평가 검사가 수행하는 작업 및 이유 그리고 필요에 따른 재구성에 대 한 지침을 포함하여 각 평가에 대해 설명합니다.

### <a name="assessment-tests-for-all-workloads"></a>모든 작업에 대한 평가 테스트

|평가 테스트  |알리는 내용  |
|---------|---------|
|베니티 도메인이 구성됨     |테넌트에 대해 non-@onmicrosoft.com이 도메인이 구성되어 있는 경우(예: @contoso.onmicrosoft.com). 예를 들어 @onmicrosoft .com 도메인을 사용하거나 베니티 도메인을 구성할 수 있습니다. 자세한 내용은 [Microsoft 365에 도메인 추가](/microsoft-365/admin/setup/add-domain)를 참조하세요. |
|Teams 라이선스     |이는 필수 구성 요소입니다. Teams를 배포하려면 Teams 라이선스가 **있어야 합니다**. Microsoft Graph를 쿼리하여 Teams 라이선스가 있는지 확인합니다(적어도 하나의 할당할 수 있는 라이선스). 자세한 내용은 [Microsoft Teams 서비스 설명](/office365/servicedescriptions/teams-service-description)을 읽어 보세요.    |
|EXCHANGE ONLINE 라이선스     |사용 가능한 Exchange Online 라이선스가 포함된 활성 구독이 있는지 여부 기본 Teams 기능을 사용하는 데는 Exchange가 필요하지 않지만 Exchange와 통합하면 최상의 Teams 환경이 제공됩니다. Microsoft Graph를 쿼리하여 테넌트와 연결된 구독을 분석하고 적격의 Exchange Online 라이선스 구독을 보유하고 있는지 확인합니다(적어도 하나의 할당할 수 있는 라이선스). 자세한 내용은 [Exchange 및 Teams가 상호 작용하는 방법](exchange-teams-interact.md)을 참조하세요.    |
|SharePoint Online 라이선스     |사용 가능한 SharePoint Online 라이선스가 포함된 활성 구독이 있는지 여부 채팅에서 파일 저장소에 비즈니스용 OneDrive를 제공하도록 사용자 1인당 SharePoint Online 라이선스를 보유할 것을 권장합니다. Microsoft Graph를 쿼리하여 SharePoint Online 라이선스가 있는지 확인합니다(적어도 하나의 할당할 수 있는 라이선스). 자세한 내용은 [SharePoint Online 및 비즈니스용 OneDrive가 Teams와 상호 작용하는 방법](./sharepoint-onedrive-interact.md)을 참조하세요.    |
|게스트 액세스 사용     |[게스트 액세스](guest-access.md)가 Teams에서 설정되어 있는 여부 게스트 액세스를 사용하여 Teams에 참가하도록 외부 사용자를 초대할 수 있습니다. [Teams 게스트 액세스 검사 목록](/microsoft-365/solutions/collaborate-as-team)을 사용하여 Teams에서 게스트 액세스 설정 과정을 단계별로 확인합니다. 검사 목록은 필수 Azure AD 구성을 포함합니다. |
|외부 액세스 구성됨     |[외부 액세스](manage-external-access.md) 기능이 설정되어 있는지 여부. 기본적으로는 열기 페더레이션을 통해 설정됩니다. |

### <a name="assessments-for-chat-teams-channels-and-apps"></a>채팅, 팀, 채널 및 앱 평가

[모든 작업에 대한 평가 테스트](#assessment-tests-for-all-workloads) 외에도 채팅, 팀, 채널 및 앱 작업에 대해 다음의 추가 평가가 시행됩니다.

|평가 테스트  |알리는 내용  |
|---------|---------|
|Microsoft 365 그룹 명명 정책이 구성됨     |Microsoft 365 그룹에 명명 표준이 구성되어 있는지 여부 Microsoft 365 그룹 명명 정책을 사용하면 조직이 일관된 명명 전략을 사용자가 만든 팀에 적용하고 또한 Outlook, SharePoint, Planner 및 Yammer를 포함한 다른 그룹 작업에도 적용할 수 있습니다. 이 테스트에서는 Microsoft Graph를 통해 Azure AD를 쿼리하여 Microsoft 365 그룹에 적용되는 명명 정책의 존재 여부를 확인합니다. 자세한 내용은 [그룹 명명 정책](/microsoft-365/admin/create-groups/groups-naming-policy)을 참조하세요.    |
|Microsoft 365 그룹 만료 정책이 구성됨     |Microsoft 365 그룹에 대한 그룹 만료 정책이 정의되어있는지 여부 이는 조직에서 자동으로 비활성 팀을 제거할 수 있도록 해줍니다. 이는 기본적으로 해제되어 있습니다. 이 테스트에서는 Microsoft Graph를 통해 Azure AD를 쿼리하고 기본값에서 값이 수정되었는지를 보고합니다. 자세한 내용은 [Microsoft 365 그룹 만료 정책](/microsoft-365/admin/create-groups/office-365-groups-expiration-policy)을 참조하세요.    |

### <a name="assessments-for-meetings-and-conferencing"></a>모임 및 회의에 대한 평가

[모든 작업에 대한 평가 테스트](#assessment-tests-for-all-workloads) 외에도 모임 및 회의 작업에 대해 다음의 추가 평가가 시행됩니다.

|평가 테스트  |알리는 내용  |
|---------|---------|
|오디오 회의 라이선스    |오디오 회의 라이선스가 포함된 활성 구독이 있는지 여부 오디오 회의 브리지를 배포하는 경우 이는 필수 구성 요소입니다. Microsoft Graph를 쿼리하여 오디오 회의 라이선스가 있는지(적어도 할당할 하나의 라이선스가 있음) 확인합니다. 자세한 내용은 [Teams 추가 기능](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)을 참조하세요.    |
|Stream 라이선스     |Microsoft Stream 라이선스가 포함된 활성 구독이 있는지 여부 이는 모임 녹화를 설정하려면 필수 구성 요소입니다. Microsoft Graph를 쿼리하여 Microsoft Stream 라이선스가 있는지 확인합니다(적어도 하나의 할당할 수 있는 라이선스). Stream에 대한 자세한 내용과 설정 방법은 [Teams 클라우드 모임 녹화](cloud-recording.md)를 참조하세요.

### <a name="assessments-for-skype-for-business-upgrade"></a>비즈니스용 Skype 업그레이드 평가

[모든 작업에 대한 평가 테스트](#assessment-tests-for-all-workloads) 외에 비즈니스용 Skype 업그레이드는 모임 및 회의 계획에 사용되는 평가도 포함합니다.

### <a name="advisor-for-teams-bot"></a>Teams용 어드바이저 봇

Teams용 어드바이저가 배포 팀을 만들면 어드바이저 봇에서 다음의 메시지를 일반 채널에서 제공합니다.

>**Microsoft Teams의 배포 팀에 오신 것을 환영합니다!**
>  
>이 팀의 목적은 필요한 모든 리소스를 제공하고 프로젝트 팀을 위한 공동 작업 공간을 제공하여 조직의 Teams 롤아웃 과정을 안내하는 것입니다. Advisor for Teams를 사용하여 만든 각 채널에는 단계별 Planner 플랜 및 롤아웃 전체에서 사용할 수 있는 Forms 사용자 설문 조사 등 기타 리소스가 포함됩니다. 언제든지 Teams 관리 센터를 사용하여 테넌트 준비 상태 평가로 돌아가 검토하거나 추가 워크로드 플랜을 추가할 수 있습니다.
>
>**조치 사항**
>
>- Teams 또는 Planner를 처음 사용할 경우 [Teams 안내](https://teamsdemo.office.com/)를 확인하고 [Planner 빠른 시작 비디오](https://support.office.com/article/microsoft-planner-video-training-4d71390f-08d8-4db0-84ea-92fb078687c7)를 시청하십시오.
>- Teams의 배포 팀에 문의하십시오. 워크로드 채널(예: 채팅, 팀, 채널 및 앱)을 선택하고 **Planner** 탭을 선택하여 시작합니다.
>
>Advisor for Teams에 대해 자세히 알아보려면 [Advisor for Teams를 사용하여 Microsoft Teams 배포](use-advisor-teams-roll-out.md)를 참조하십시오.
>

> [!IMPORTANT]
> Advisor for Teams 봇은 배포 팀에 환영 메시지를 보내는 데만 사용됩니다. 추가 데이터가 수집되지 않습니다.

> [!IMPORTANT]
> Teams용 어드바이저 봇은 기본적으로 사용하도록 설정되어 있습니다. Teams용 어드바이저를 사용할 계획인 경우 사용을 해제하지 않습니다.

## <a name="advisor-for-teams-and-microsoft-365-learning-pathways"></a>Teams용 어드바이저 및 Microsoft 365 학습 경로

[Microsoft 365 학습 경로](/office365/customlearning/)는 사용자를 교육하도록 사용자 지정할 수 있는 주문형 학습 솔루션으로, 조직 내 Teams 사용 및 채택률을 높일 수 있습니다. Teams용 어드바이저와 학습 경로를 사용하여 사용자를 신속하게 시작하고 채택을 유도할 수 있습니다.

학습 경로를 통해 SharePoint Online 사이트 서식 파일과 사용자를 위한 학습 사이트를 쉽게 구축할 수 있습니다. 학습 경로 교육 포털을 사용자 정의하여 사용자의 필요에 맞는 교육 및 지원 콘텐츠를 포함할 수 있습니다. Microsoft 온라인 카탈로그의 Teams 재생 목록을 사용하고 재생 목록을 추가할 수 있습니다.

학습 경로에 학습 사이트를 만든 다음 팀의 채널에 탭으로 추가하여 사용자가 빠르고 쉽게 액세스할 수 있습니다.

예를 들어 Teams용 어드바이저를 학습 경로와 함께 사용하여 지원 센터 및 챔피언을 교육한 다음 학습 경로가 최종 사용자 교육을 지원하게 할 수 있습니다. 지원 센터 및 챔피언을 Teams로 온보드를 지원하는 학습 사이트를 만든 다음 롤아웃 중인 각 워크로드 채널에 탭으로 추가합니다. 그런 다음 지원 센터 및 챔피언은 학습 경로 교육 포털에 링크와 사용자 지정 재생 목록이 포함된 지원 페이지를 만들어 Teams의 사용자를 지원할 수 있습니다. 이 지원 페이지를 모든 팀의 채널에 추가하여 최종 사용자를 교육할 수 있습니다.

다음은 Teams용 어드바이저를 학습 경로와 함께 사용하는 방법에 대한 개요입니다.

### <a name="get-started-in-learning-pathways"></a>학습 경로에서 시작

학습 경로를 시작하려면[학습 경로를 사용하여 시작](/office365/customlearning/)을 참조하세요.

환경에서 새 학습 경로 솔루션을 설정하려면 [새 학습 경로 솔루션 프로비저닝](/office365/customlearning/custom_provision)을 참조하세요.

### <a name="create-a-learning-plan"></a>학습 계획 만들기

#### <a name="plan-your-learning-content"></a>학습 콘텐츠 계획

학습 경로에서 사이트를 구축하기 전에 시간을 내어 사용 가능한 학습 리소스 및 기능을 검토하고 수집하세요. 학습 경로를 통해 Microsoft 365 교육 페이지의 콘텐츠를 사용하고 사용자가 만든 콘텐츠를 추가하여 사이트를 고유한 요구에 맞게 조정할 수 있습니다.

자세한 내용은 [교육 경로 콘텐츠 계획](/office365/customlearning/custom_plancontent) 및 [원격 인력 지원 리소스](/office365/customlearning/custom_plancontent_remoteresources)를 참조하세요.

#### <a name="explore-teams-content-in-learning-pathways"></a>학습 경로에서 Teams 콘텐츠 살펴보기

학습 경로는 온라인 카탈로그에 연결된 웹 파트를 사용하여 SharePoint 사이트를 제공합니다. 웹 파트를 호스트하는 Microsoft 365 교육 페이지에는 학습 경로에서 사용할 수 있는 모든 교육 과정이 표시됩니다. 사용 가능한 기능과 콘텐츠를 구성하는 방법에 대해 자세히 알아보세요.

[학습 경로 사이트로 이동하고](/office365/customlearning/custom_goto) **Microsoft 365 교육** 을 선택한 다음 **Microsoft Teams** 를 선택하여 온라인 카탈로그의 모든 Teams 교육 재생 목록을 표시하세요. 재생 목록을 선택하고 **다음** 및 **이전** 단추를 선택하여 탐색합니다. 아래쪽 화살표를 클릭하여 재생 목록의 내용을 보고 특정 항목으로 이동할 수도 있습니다.

#### <a name="take-an-inventory-of-teams-learning-resources-in-your-organization"></a>조직 내 팀 학습 리소스 인벤토리 수집

조직에서 이미 사용할 수 있는 Teams 학습 콘텐츠를 검토하세요. 예를 들어 Teams에 대해 사용자 지정 온보딩, 교육 또는 지원 콘텐츠를 이미 개발했을 수 있습니다. 기존 SharePoint 자산은 재생 목록에서 Microsoft 콘텐츠와 섞여 조직에 맞는 대상 재생 목록을 만들 수 있습니다.

#### <a name="build-your-site-in-learning-pathways"></a>학습 경로에서 사이트 작성

[관리자 성공 센터](/office365/customlearning/custom_successcenter) 교육 경로에서는 조직에서 학습 경로를 계획하고 사용자 지정하는 데 도움이 되는 지침과 리소스를 제공합니다. [사이트 사용자 지정 방법](/office365/customlearning/custom_overview), 콘텐츠 표시 및 숨기기, 사용자 지정 재생 목록 작성 등에 대해 알아보세요.

관리 성공 센터에 액세스하려면 학습 경로 홈페이지에서 **관리자 성공 센터** 를 선택합니다.

#### <a name="add-your-site-to-teams"></a>Teams에 사이트 추가

사이트가 준비되면 모든 팀의 채널에 쉽고 빠르게 액세스할 수 있도록 추가합니다.

1. Teams에서 팀으로 이동하고 채널을 선택합니다.
2. 채널 페이지의 맨 위에서 **+** (**탭 추가**)를 선택합니다.
3. **SharePoint 페이지** 를 선택하고 **모든 SharePoint 사이트에서 페이지 추가** 를 선택합니다.
4. 학습용 경로 사이트 URL을 붙여넣고 **저장** 을 선택합니다.

자세한 내용은 [Teams 채널에 SharePoint 페이지 또는 목록 추가](https://support.microsoft.com/office/add-a-sharepoint-page-or-list-to-a-channel-in-teams-131edef1-455f-4c67-a8ce-efa2ebf25f0b)를 참조하세요.

### <a name="train-your-support-team"></a>지원 팀 교육

학습 경로 사이트의 리소스를 사용하여 지원 센터와 챔피언을 Teams에 온보드할 수 있습니다. Teams 사용자를 지원하는 데 필요한 도구와 정보를 준비하세요.

Teams 지원 센터 및 챔피언을 준비하는 방법에 대한 지침 및 리소스는 [조직 교육](https://adoption.microsoft.com/microsoft-teams/#train-your-org) 및 [챔피언 빌드](https://adoption.microsoft.com/microsoft-teams/#build-champions)를 참조하세요.

사용자의 "방법" 질문에 대한 연락 담당자로서 지원 센터와 챔피언은 학습 경로 사이트를 사용하여 사용자를 교육하고 지원 티켓을 만드는 대안으로 사용할 수 있습니다. 교육 및 지원 페이지를 작성하여 [학습 경로 사이트를 사용자 지정](/office365/customlearning/)하도록 지원 센터와 챔피언에게 권장한 다음 사용자가 자체 서비스할 수 있도록 팀의 [채널에 탭으로 추가](#add-your-site-to-teams)합니다.

### <a name="drive-adoption"></a>도입 주도

사이트를 사용자 지정하고 학습 계획을 종합한 다음 사용자가 학습 경로를 통해 지속적인 학습을 하도록 장려할 수 있는 방법을 생각해 보세요.

Use your communication channels to promote the site and generate awareness. For example, include a standard tagline such as “Check out our training and support site for how to get productive with Teams” in communications to your users.

팀별로 공동 작업할 수 있는 방법을 강조 표시하여 사용자를 참여시키고 학습 경로 사이트로 안내하여 학습 방법을 학습할 수 있습니다.

성공적인 롤아웃 및 도입 계획을 구현하는 데 도움이 되는 지침, 도입 키트, 모범 사례 등이 포함된 리소스를 확인하세요.  

- [학습용 경로 도입 구동](/office365/customlearning/driveadoption)
- [Teams 채택](adopt-microsoft-teams-landing-page.md)
- [Teams 채택 리소스](https://adoption.microsoft.com/microsoft-teams/)

## <a name="frequently-asked-questions"></a>자주 묻는 질문

### <a name="what-are-the-licensing-requirements-for-advisor-for-teams"></a>Teams용 어드바이저에 대한 라이선스 요구 사항

적어도 Microsoft 365 Business Basics가 있어야 하며 이를 통해 Teams용 어드바이저의 양식 및 플래너와의 통합을 활용할 수 있습니다.

### <a name="can-i-delete-the-deployment-team"></a>배포 팀을 삭제할 수 있나요?

Advisor for Teams에서 배포 팀을 만든 이후 삭제 기능을 포함해 다른 모든 팀과 같이 팀을 관리하십시오. Teams 관리 센터를 사용하여 팀을 삭제하지 않는 경우 Teams 관리 센터는 팀이 존재하는 것으로 표시합니다.

### <a name="can-i-add-or-remove-channels-in-the-deployment-team"></a>배포 팀에서 채널을 추가하거나 제거할 수 있나요?

예. 배포 팀이 만들어졌으면 다른 모든 팀과 동일한 방식으로 채널을 관리하게 됩니다.

### <a name="can-i-add-or-remove-project-team-members-in-the-deployment-team"></a>배포 팀에서 프로젝트 팀 구성원을 추가하거나 제거할 수 있나요?

예. 배포 팀이 만들어지고 나면 다른 모든 팀과 동일한 방식으로 관리하게 됩니다.

### <a name="can-i-modify-the-planner-plans"></a>Planner 플랜을 수정할 수 있나요?

예, Advisor for Teams에서 배포 팀을 만든 후에는 Teams 배포를 최상으로 지원하도록 Planner 플랜을 업데이트해야 합니다. 버킷, 작업, 작업 세부 정보 등 다른 Planner 플랜처럼 모든 요소를 수정할 수 있습니다.

### <a name="can-i-modify-the-forms-survey"></a>Forms 설문 조사를 수정할 수 있나요?

예, Teams용 어드바이저에서 배포 팀을 만든 후에는 필요에 따라 Forms 설문 조사를 수정할 수 있습니다.

### <a name="are-there-any-differences-between-advisor-for-teams-in-gcc"></a>GCC에서 Teams의 관리자들 사이에 차이가 있나요?

예. 현재 GCC에서는 Teams Forms 앱을 사용할 수 없으므로 사용자 설문 조사 양식이 생성은 되지만 계획 채널에 고정되어 있지 않습니다.

### <a name="what-information-is-advisor-for-teams-collecting-about-my-organization"></a>내 조직에 대해 Teams용 어드바이저에서 어떤 정보를 수집하나요?

Advisor for Teams에서는 EUII(최종 사용자 식별 정보) 이외의 정보를 수집하는 데 사용자의 동의를 요청합니다. 수집된 정보는 Advisor for Teams에서 어떻게 효과적으로 성공적인 결과를 유도하고 있는지, 그리고 향상해야 할 부분은 무엇인지에 대해 Microsoft에 피드백을 제공하는 원격 분석 양식에 있습니다. 이와 같은 데이터는 Microsoft가 배포를 지원하기 위한 노력의 일환으로 사용자의 조직에 적극적으로 관여할 기회를 식별하는 데 사용됩니다.

### <a name="can-i-use-advisor-for-teams-with-fasttrack"></a>Teams용 어드바이저를 FastTrack과 사용할 수 있나요?

Yes, FastTrack leverages Advisor for Teams for all customers looking to deploy Teams. They can assist with the initial setup of your Deployment team using Advisor for Teams (if required) and also provide as-needed support on specific topics during your Teams rollout.

### <a name="can-i-use-advisor-for-teams-with-a-partner"></a>Teams용 어드바이저를 파트너와 함께 사용할 수 있나요?

예, Teams 배포를 위해 배포 파트너를 사용하는 중에도 Advisor for Teams를 사용할 수 있습니다. 파트너가 CSP이고 사용자의 테넌트를 대신 관리할 경우 Advisor for Teams를 사용하여 배포 팀을 만들고 전체 프로젝트 이행을 지원할 수 있습니다. 또한 배포 팀에서 해당 사용자를 게스트로 추가하여 모든 파트너와 함께 작업하여 전체 프로젝트 팀원으로서 참여하게 할 수 있습니다.

### <a name="how-do-i-use-planner"></a>Planner를 사용하려면 어떻게 해야 하나요?

[Microsoft Planner 도움말](https://support.office.com/article/Microsoft-Planner-help-4a9a13c6-3adf-4a60-a6fc-15c0b15e16fc) 및 [Planner 빠른 시작 비디오](https://support.office.com/article/microsoft-planner-video-training-4d71390f-08d8-4db0-84ea-92fb078687c7)를 확인하십시오.

### <a name="how-do-i-use-forms"></a>Forms를 사용하려면 어떻게 해야 하나요?

[Forms 도움말 센터](https://support.office.com/forms)로 이동하십시오.

## <a name="related-topics"></a>관련 항목

[Teams 관리자 사용자 지정](/office365/customlearning/custom_teamsadvisor)

[Teams를 배포하는 방법](./deploy-overview.md)

[Teams에서 팀을 구성하는 방법에 대한 모범 사례](best-practices-organizing.md)

[라이선싱에 대한 제품 이름 및 서비스 계획 식별자](/azure/active-directory/users-groups-roles/licensing-service-plan-reference)
