---
title: Advisor for Teams(미리 보기)를 사용하여 Microsoft Teams 배포
author: lolajacobsen
ms.author: lolaj
ms.reviewer: brandber
manager: serdars
ms.topic: article
ms.service: msteams
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Priority
f1keywords:
- ms.teamsadmincenter.deploymentadvisor.overview
ms.custom: ''
description: Advisor for Teams(미리 보기)를 사용하여 Microsoft Teams 배포를 계획하고 완료할 수 있습니다.
ms.openlocfilehash: 0c5cd0b2bc01b213a10c7a9be79d9ec7dc307fbe
ms.sourcegitcommit: 2fab6105dfc4c225de8c09ab79d9c2c273a3e4f6
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/10/2020
ms.locfileid: "41004783"
---
# <a name="use-advisor-for-teams-to-help-you-roll-out-microsoft-teams"></a>Advisor for Teams를 사용하여 Microsoft Teams 배포

[!INCLUDE [preview-feature](includes/preview-feature.md)]

Advisor for Teams(미리 보기)는 Microsoft 팀이 배포 과정을 안내합니다. Office 365 테넌트 환경을 평가하고 Teams를 성공적으로 배포하기 전에 업데이트 또는 수정해야 할 수 있는 가장 일반적인 구성을 식별합니다. 그런 다음 Advisor for Teams는 배포하려는 각 워크로드에 대한 채널로 배포 팀(Teams에서)을 만듭니다. 서비스 관리 팀의 각 워크로드에는 각 워크로드에 대한 모든 롤아웃 작업이 포함된 포괄적인 Planner 플랜이 함께 제공됩니다.  이 Planner 플랜을 사용하여 프로젝트 관리자, Teams 및 Office 365 관리자, 지원자, 채택 및 사용자 준비 상태 팀 등의 각 롤아웃 단계를 담당하는 사용자에게 작업을 할당합니다. 각 롤아웃 작업에는 해당 작업을 완료하는 데 필요한 모든 가이드 및 리소스가 포함됩니다.

Advisor for Teams는 [Teams 관리 센터](https://admin.teams.microsoft.com)의 일부입니다. 적어도 Office 365 Business Essentials 라이선스가 있어야 하며 이를 통해 Teams용 어드바이저의 양식 및 플래너와의 통합을 활용할 수 있습니다. Teams용 어드바이저의 사용을 시작하려면 대시보드의 **Teams 워크로드 배포** 위젯에서 **시작** 단추를 클릭합니다. 또는 **계획** > **Teams Advisor**로 이동합니다.

> [!IMPORTANT]
> Advisor for Teams는 Microsoft 365 정부 기관, GCC High 또는 DoD 배포에는 사용할 수 없습니다.

Teams용 어드바이저 환경의 지도된 개요를 보려면 Microsoft Mechanics 비디오 [Microsoft Teams 배포 및 구성](https://youtu.be/o2mlsUubIO4?t=50)을 확인하세요.

## <a name="using-advisor-for-teams-preview"></a>Advisor for Teams 사용(미리 보기)

**Advisor for Teams를 사용하려면 Teams, Forms 및 Planner 라이선스가 필요합니다.** 그러나 Advisor for Teams를 사용하기 위해 Teams 관리자가 될 필요는 없습니다. 조직 내 누구나 사용할 수 있습니다. Advisor for Teams가 Teams 관리 센터에 있어도 관리자가 아닌 사용자가 액세스할 수 있도록 특별 권한을 설정했습니다. 테넌트 준비 상태 평가를 열려면 Teams 관리자, Teams 서비스 관리자 또는 전역 관리자이어야 합니다(이는 특수한 비관리자 역할이 평가를 기반으로 하는 Microsoft Graph API로의 액세스 권한이 없기 때문입니다).

> [!IMPORTANT]
> Teams 관리 센터의 **계획**에 **Teams Advisor**가 없는 경우, 사용자에게 Teams에 대한 라이선스가 없는 것입니다. 이 현상은 차후에 변경 예정입니다.

Teams용 어드바이저를 처음으로 사용하는 경우 Teams에서 사용자를 위한 배포 팀이 만들어집니다. 선택하는 각 작업에 대한 채널을 추가합니다.

> [!IMPORTANT]
> 배포 팀이 이미 만들어진 경우 다른 사용자가 이를 만들려고 하면 지원 팀에 문의하라는 오류 메시지가 표시됩니다. 이는 Teams가 기존 팀과 해당 구성원에 대한 정보를 실수로 노출하는 것을 방지할 수 있습니다. 배포 팀의 소유자에게 사용자를 추가하도록 요청하거나 지원 담당자에게 도움을 요청하세요.

## <a name="available-advisor-for-teams-plans"></a>사용 가능한 Teams용 어드바이저 계획

Teams용 어드바이저가 미리 보기에 있는 동안에는 다음과 같은 두 가지 플랜이 제공됩니다.

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

채팅, 팀, 채널 및 앱 플랜부터 시작하는 것이 좋습니다. 해당 워크로드 배포가 완료되면 Teams용 어드바이저로 돌아가 **채널 추가**를 클릭하여 다음 작업을 시작합니다.

## <a name="tenant-assessment"></a>테넌트 평가
각 플랜에는 Teams를 배포하기 전에 개선이 필요할 수 있는 환경의 모든 측면을 신속히 확인하는 데 사용할 수 있는 테넌트 준비 상태 평가가 포함되어 있습니다. 평가는 필수 구성 요소와 모범 사례를 포함합니다. 각 평가 테스트에는 녹색 확인 표시 또는 주황색 경고 삼각형이 있습니다. 

- <sub><img src="media/use-advisor-teams-roll-out-image2.png" alt="Green check mark"/></img></sub>녹색 확인 표시는 테넌트가 특정 테스트를 통과 했다는 의미입니다. 
- <sub><img src="media/use-advisor-teams-roll-out-image1.png" alt="Yellow alert mark"/></img></sub>주황색 경고 삼각형은 조치가 필요한지의 여부를 판단하기 위해 후속 조치를 취할 것을 제안함을 의미합니다(예: Office 365 그룹 만료 정책을 권장하지만 필수는 아님).

> [!IMPORTANT]
> 관리자 역할이 있는 사용자가 Teams용 어드바이저를 시작하면 모든 평가가 백그라운드에서 실행됩니다. 항목을 업데이트하거나 재구성하는 경우 최대 24시간 동안 평가에 반영되지 않을 수 있습니다. 이는 일시적입니다. Teams용 어드바이저가 미리 보기를 나가는 즉시 일반적으로 가용하게 되며 평가는 거의 실시간으로 업데이트됩니다.

아래의 섹션은 어떤 것이 필수 구성 요소인지 혹은 모범 사례인지와 각 평가 검사가 수행하는 작업 및 이유 그리고 필요에 따른 재구성에 대 한 지침을 포함하여 각 평가에 대해 설명합니다.

### <a name="assessment-tests-for-all-workloads"></a>모든 작업에 대한 평가 테스트

|평가 테스트  |알리는 내용  |
|---------|---------|
|베니티 도메인이 구성됨     |테넌트에 대해 non-@onmicrosoft.com이 도메인이 구성되어 있는 경우(예: @contoso.onmicrosoft.com). 예를 들어 @onmicrosoft .com 도메인을 사용하거나 베니티 도메인을 구성할 수 있습니다. 자세한 내용은 [Office 365에 도메인 추가](https://docs.microsoft.com/office365/admin/setup/add-domain)를 참조하세요. |
|Teams 라이선스     |이는 필수 구성 요소입니다. Teams를 배포하려면 Teams 라이선스가 **있어야 합니다**. Microsoft Graph를 쿼리하여 Teams 라이선스가 있는지 확인합니다(적어도 하나의 할당할 수 있는 라이선스). 자세한 내용은 [Teams의 사용을 위한 Office 365 라이선싱](https://docs.microsoft.com/microsoftteams/office-365-licensing)을 참조하세요.    |
|EXCHANGE ONLINE 라이선스     |사용 가능한 Exchange Online 라이선스가 포함된 활성 구독이 있는지 여부 기본 Teams 기능을 사용하는 데는 Exchange가 필요하지 않지만 Exchange와 통합하면 최상의 Teams 환경이 제공됩니다. Microsoft Graph를 쿼리하여 테넌트와 연결된 구독을 분석하고 적격의 Exchange Online 라이선스 구독을 보유하고 있는지 확인합니다(적어도 하나의 할당할 수 있는 라이선스). 자세한 내용은 [Exchange 및 Teams가 상호 작용하는 방법](exchange-teams-interact.md)을 참조하세요.    |
|SharePoint Online 라이선스     |사용 가능한 SharePoint Online 라이선스가 포함된 활성 구독이 있는지 여부 채팅에서 파일 저장소에 비즈니스용 OneDrive를 제공하도록 사용자 1인당 SharePoint Online 라이선스를 보유할 것을 권장합니다. Microsoft Graph를 쿼리하여 SharePoint Online 라이선스가 있는지 확인합니다(적어도 하나의 할당할 수 있는 라이선스). 자세한 내용은 [SharePoint Online 및 비즈니스용 OneDrive가 Teams와 상호 작용하는 방법](https://docs.microsoft.com/microsoftteams/sharepoint-onedrive-interact)을 참조하세요.    |
|게스트 액세스 사용     |[게스트 액세스](guest-access.md)가 Teams에서 설정되어 있는 여부 게스트 액세스를 사용하여 Teams에 참가하도록 외부 사용자를 초대할 수 있습니다. [Teams 게스트 액세스 검사 목록](guest-access-checklist.md)을 사용하여 Teams에서 게스트 액세스 설정 과정을 단계별로 확인합니다. 검사 목록은 필수 Azure AD 구성을 포함합니다. |
|외부 액세스 구성됨     |[외부 액세스](manage-external-access.md) 기능이 설정되어 있는지 여부. 기본적으로는 열기 페더레이션을 통해 설정됩니다. |

### <a name="assessments-for-chat-teams-channels-and-apps"></a>채팅, 팀, 채널 및 앱 평가

[모든 작업에 대한 평가 테스트](#assessment-tests-for-all-workloads) 외에도 채팅, 팀, 채널 및 앱 작업에 대해 다음의 추가 평가가 시행됩니다.

|평가 테스트  |알리는 내용  |
|---------|---------|
|Office 365 그룹 명명 정책이 구성됨     |Office 365 그룹에 명명 표준이 구성되어 있는지 여부 Office 365 그룹 명명 정책을 사용하면 조직이 일관된 명명 전략을 사용자가 만든 팀에 적용하고 또한 Outlook, SharePoint, Planner 및 Yammer를 비롯한 다른 그룹 작업에도 적용할 수 있습니다. 이 테스트에서는 Microsoft Graph를 통해 Azure AD를 쿼리하여 Office 365 그룹에 적용되는 명명 정책의 존재 여부를 확인합니다. 자세한 내용은 [Office 365 그룹 명명 정책](https://docs.microsoft.com/office365/admin/create-groups/groups-naming-policy)을 참조하세요.    |
|Office 365 그룹 만료 정책이 구성됨     |Office 365 그룹에 대한 그룹 만료 정책이 정의되어있는지 여부 이는 조직에서 자동으로 비활성 팀을 제거할 수 있도록 해줍니다. 이는 기본적으로 해제되어 있습니다. 이 테스트에서는 Microsoft Graph를 통해 Azure AD를 쿼리하고 기본값에서 값이 수정되었는지를 보고합니다. 자세한 내용은 [Office 365 그룹 만료 정책](https://docs.microsoft.com/office365/admin/create-groups/office-365-groups-expiration-policy)을 참조하세요.    |

### <a name="assessments-for-meetings-and-conferencing"></a>모임 및 회의에 대한 평가

[모든 작업에 대한 평가 테스트](#assessment-tests-for-all-workloads) 외에도 모임 및 회의 작업에 대해 다음의 추가 평가가 시행됩니다.

|평가 테스트  |알리는 내용  |
|---------|---------|
|오디오 회의 라이선스    |오디오 회의 라이선스가 포함된 활성 구독이 있는지 여부 오디오 회의 브리지를 배포하는 경우 이는 필수 구성 요소입니다. Microsoft Graph를 쿼리하여 오디오 회의 라이선스가 있는지(적어도 할당할 하나의 라이선스가 있음) 확인합니다. 자세한 내용은 [Teams 추가 기능](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)을 참조하세요.    |
|Stream 라이선스     |Microsoft Stream 라이선스가 포함된 활성 구독이 있는지 여부 이는 모임 녹화를 설정하려면 필수 구성 요소입니다. Microsoft Graph를 쿼리하여 Microsoft Stream 라이선스가 있는지 확인합니다(적어도 하나의 할당할 수 있는 라이선스). Stream에 대한 자세한 내용과 설정 방법은 [Teams 클라우드 모임 녹화](cloud-recording.md)를 참조하세요.

### <a name="advisor-for-teams-bot"></a>Teams용 어드바이저 봇

Teams용 어드바이저가 배포 팀을 만들면 어드바이저 봇에서 다음의 메시지를 일반 채널에서 제공합니다.

>**Microsoft Teams의 배포 팀에 오신 것을 환영합니다!**
>  
>이 팀의 목적은 필요한 모든 리소스를 제공하고 프로젝트 팀을 위한 공동 작업 공간을 제공하여 조직의 Teams 롤아웃 과정을 안내하는 것입니다. Advisor for Teams를 사용하여 만든 각 채널에는 단계별 Planner 플랜 및 롤아웃 전체에서 사용할 수 있는 Forms 사용자 설문 조사 등 기타 리소스가 포함됩니다. 언제든지 Teams 관리 센터를 사용하여 테넌트 준비 상태 평가로 돌아가 검토하거나 추가 워크로드 플랜을 추가할 수 있습니다.
> 
>**조치 사항** 
>- Teams 또는 Planner를 처음 사용할 경우 [Teams 안내](https://teamsdemo.office.com/)를 확인하고 [Planner 빠른 시작 비디오](https://support.office.com/article/microsoft-planner-video-training-4d71390f-08d8-4db0-84ea-92fb078687c7)를 시청하십시오. 
>- Teams의 배포 팀에 문의하십시오. 워크로드 채널(예: 채팅, 팀, 채널 및 앱)을 선택하고 **Planner** 탭을 선택하여 시작합니다.
> 
>Advisor for Teams에 대해 자세히 알아보려면 [Advisor for Teams를 사용하여 Microsoft Teams 배포](use-advisor-teams-roll-out.md)를 참조하십시오.
>

> [!IMPORTANT]
> Advisor for Teams 봇은 배포 팀에 환영 메시지를 보내는 데만 사용됩니다. 추가 데이터가 수집되지 않습니다.

> [!IMPORTANT]
> Teams용 어드바이저 봇은 기본적으로 사용하도록 설정되어 있습니다. Teams용 어드바이저를 사용할 계획인 경우 사용을 해제하지 않습니다.

## <a name="frequently-asked-questions"></a>자주하는 질문
### <a name="what-are-the-licensing-requirements-for-advisor-for-teams"></a>Advisor for Teams에 대한 라이선스 요구 사항은 무엇인가요?
적어도 Office 365 Business Essentials이 있어야 하며 이를 통해 Teams용 어드바이저의 양식 및 플래너와의 통합을 활용할 수 있습니다.

### <a name="can-i-delete-the-deployment-team"></a>배포 팀을 삭제할 수 있나요?
Advisor for Teams에서 배포 팀을 만든 이후 삭제 기능을 포함해 다른 모든 팀과 같이 팀을 관리하십시오. Teams 관리 센터를 사용하여 팀을 삭제하지 않는 경우 Teams 관리 센터는 팀이 존재하는 것으로 표시합니다. 이는 임시적이며 Teams용 어드바이저가 미리 보기 기간을 떠나면 일반적으로 가용하게 됩니다.

### <a name="can-i-add-or-remove-channels-in-the-deployment-team"></a>배포 팀에서 채널을 추가하거나 제거할 수 있나요?
예. 배포 팀이 만들어졌으면 다른 모든 팀과 동일한 방식으로 채널을 관리하게 됩니다.

### <a name="can-i-add-or-remove-project-team-members-in-the-deployment-team"></a>배포 팀에서 프로젝트 팀 구성원을 추가하거나 제거할 수 있나요?
예. 배포 팀이 만들어지고 나면 다른 모든 팀과 동일한 방식으로 관리하게 됩니다.

### <a name="can-i-modify-the-planner-plans"></a>Planner 플랜을 수정할 수 있나요?
예, Advisor for Teams에서 배포 팀을 만든 후에는 Teams 배포를 최상으로 지원하도록 Planner 플랜을 업데이트해야 합니다. 버킷, 작업, 작업 세부 정보 등 다른 Planner 플랜처럼 모든 요소를 수정할 수 있습니다.

### <a name="can-i-modify-the-forms-survey"></a>Forms 설문 조사를 수정할 수 있나요?
예, Advisor for Teams에서 배포 팀을 만든 후에는 필요에 따라 Forms 설문 조사를 수정할 수 있습니다.

### <a name="what-information-is-advisor-for-teams-collecting-about-my-organization"></a>내 조직에 대해 Advisor for Teams에서 어떤 정보를 수집하나요?
Advisor for Teams에서는 EUII(최종 사용자 식별 정보) 이외의 정보를 수집하는 데 사용자의 동의를 요청합니다. 수집된 정보는 Advisor for Teams에서 어떻게 효과적으로 성공적인 결과를 유도하고 있는지, 그리고 향상해야 할 부분은 무엇인지에 대해 Microsoft에 피드백을 제공하는 원격 분석 양식에 있습니다. 이와 같은 데이터는 Microsoft가 배포를 지원하기 위한 노력의 일환으로 사용자의 조직에 적극적으로 관여할 기회를 식별하는 데 사용됩니다.

### <a name="can-i-use-advisor-for-teams-with-fasttrack"></a>Advisor for Teams를 FastTrack과 사용할 수 있나요?
예, FastTrack에서는 Teams을 배포하려는 모든 고객을 위해 Advisor for Teams를 활용합니다. Advisor for Teams(필요할 경우)를 사용하여 배포 팀 초기 설정을 지원하고 Teams 롤아웃 중 특정 주제에 대해 필요할 경우 지원을 제공할 수도 있습니다.

### <a name="can-i-use-advisor-for-teams-with-a-partner"></a>Advisor for Teams를 파트너와 함께 사용할 수 있나요?
예, Teams 배포를 위해 배포 파트너를 사용하는 중에도 Advisor for Teams를 사용할 수 있습니다. 파트너가 CSP이고 사용자의 테넌트를 대신 관리할 경우 Advisor for Teams를 사용하여 배포 팀을 만들고 전체 프로젝트 이행을 지원할 수 있습니다. 또한 배포 팀에서 해당 사용자를 게스트로 추가하여 모든 파트너와 함께 작업하여 전체 프로젝트 팀원으로서 참여하게 할 수 있습니다.

### <a name="how-do-i-use-planner"></a>Planner를 사용하려면 어떻게 해야 합니까?
[Microsoft Planner 도움말](https://support.office.com/article/Microsoft-Planner-help-4a9a13c6-3adf-4a60-a6fc-15c0b15e16fc) 및 [Planner 빠른 시작 비디오](https://support.office.com/article/microsoft-planner-video-training-4d71390f-08d8-4db0-84ea-92fb078687c7)를 확인하십시오. 

### <a name="how-do-i-use-forms"></a>Forms를 사용하려면 어떻게 해야 합니까?
[Forms 도움말 센터](https://support.office.com/forms)로 이동하십시오.

## <a name="related-topics"></a>관련 항목

[Teams를 배포하는 방법](How-to-roll-out-teams.md)

[라이선싱에 대한 제품 이름 및 서비스 계획 식별자](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference
) 
