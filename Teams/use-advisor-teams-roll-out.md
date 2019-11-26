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
ms.openlocfilehash: f7de348c6f8ca60cc1d062fce79725b4b18d0350
ms.sourcegitcommit: 5a7e273a3636322052e4a48a5a75513cbf5abb84
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "39209194"
---
# <a name="use-advisor-for-teams-to-help-you-roll-out-microsoft-teams"></a>Advisor for Teams를 사용하여 Microsoft Teams 배포

[!INCLUDE [preview-feature](includes/preview-feature.md)]

Advisor for Teams(미리 보기)는 Microsoft 팀이 배포 과정을 안내합니다. Office 365 테넌트 환경을 평가하고 Teams를 성공적으로 배포하기 전에 업데이트 또는 수정해야 할 수 있는 가장 일반적인 구성을 식별합니다. 그런 다음 Advisor for Teams는 배포하려는 각 워크로드에 대한 채널로 배포 팀(Teams에서)을 만듭니다. 서비스 관리 팀의 각 워크로드에는 각 워크로드에 대한 모든 롤아웃 작업이 포함된 포괄적인 Planner 플랜이 함께 제공됩니다.  이 Planner 플랜을 사용하여 프로젝트 관리자, Teams 및 Office 365 관리자, 지원자, 채택 및 사용자 준비 상태 팀 등의 각 롤아웃 단계를 담당하는 사용자에게 작업을 할당합니다. 각 롤아웃 작업에는 해당 작업을 완료하는 데 필요한 모든 가이드 및 리소스가 포함됩니다.

Advisor for Teams는 [Teams 관리 센터](https://admin.teams.microsoft.com)의 일부입니다. Advisor for Teams를 처음 사용하려면 대시보드의 **팀 워크로드 배포** 위젯에서 **시작** 단추를 클릭합니다. 또는 **계획** > **관리자**로 이동합니다.

> [!IMPORTANT]
> Advisor for Teams는 Microsoft 365 정부 기관, GCC High 또는 DoD 배포에는 사용할 수 없습니다.

## <a name="using-advisor-for-teams-preview"></a>Advisor for Teams 사용(미리 보기)

Advisor for Teams를 사용하기 위해 Teams 관리자가 될 필요는 없습니다. 조직 내 누구나 사용할 수 있습니다. Advisor for Teams가 Teams 관리 센터에 있어도 관리자가 아닌 사용자가 액세스할 수 있도록 특별 권한을 설정했습니다. 테넌트 준비 상태 평가를 열려면 Teams 관리자, Teams 서비스 관리자 또는 전역 관리자여야 합니다.

Advisor for Teams를 처음으로 사용하는 경우 Teams에서 사용자를 위한 배포 팀이 만들어집니다. 여기에 배포하려는 각 워크로드의 채널이 추가됩니다. 


## <a name="available-advisor-for-teams-plans"></a>사용 가능한 Advisor for Teams 계획

Advisor for Teams가 미리 보기에 있는 동안에는 다음과 같은 두 가지 플랜이 제공됩니다.

1. 채팅, 팀, 채널 및 앱
    - 테넌트 평가
    - 채택 작업을 포함한 Planner 플랜
    - Forms 사용자 설문 조사
1. 모임 및 회의
    - 테넌트 평가
    - 채택 작업을 포함한 Planner 플랜
    - Forms 사용자 설문 조사

채팅, 팀, 채널 및 앱 플랜부터 시작하는 것이 좋습니다. 해당 워크로드 배포가 완료되면 관리자로 돌아가 **채널 추가**를 클릭하여 다음 워크로드를 시작합니다. 

## <a name="tenant-assessment"></a>테넌트 평가
각 플랜에는 Teams를 배포하기 전에 환경의 모든 결함을 확인하고 수정하는 데 사용할 수 있는 테넌트 준비 상태 평가가 포함되어 있습니다. 각 평가에서 검사하는 항목은 다음과 같습니다.

### <a name="chat-teams-channels-and-apps"></a>채팅, 팀, 채널 및 앱


|평가  |알리는 내용  |
|---------|---------|
|Teams 라이선스     |사용 가능한 Teams 라이선스가 포함된 활성 구독이 있는지 여부 |
|Exchange 라이선스     |사용 가능한 Exchange Online 라이선스가 포함된 활성 구독이 있는지 여부 기본 Teams 기능을 사용하는 데는 Exchange가 필요하지 않지만 Exchange와 통합하면 최상의 Teams 환경이 제공됩니다.         |
|SharePoint Online 라이선스     | 사용 가능한 SharePoint Online 라이선스가 포함된 활성 구독이 있는지 여부 파일 저장, 채널 공동 작업 및 채팅을 위해 사용자당 하나의 SharePoint Online 라이선스가 필요합니다. 
|게스트 액세스 사용     |게스트 액세스가 Teams에서 켜져 있는 경우 게스트 액세스에 대한 Azure Active Directory 설정은 검토되지 않습니다.   |
|베니티 도메인 구성     |테넌트에 대해 @onmicrosoft.com이 아닌 도메인이 구성되어 있는지 여부  |
|Office 365 그룹 이름 지정 표준 구성     | Office 365 그룹에 이름 지정 표준이 구성되어 있는지 여부        |
|Office 365 그룹 만료 구성     |  Office 365 그룹에 그룹 만료 정책이 정의되어 있는지 여부 그렇지 않은 경우에는 값이 만료되지 않음으로 설정됩니다.        |
|외부 액세스 구성     |외부 액세스가 켜져 있는 경우 Teams에서 외부 조직과 통신할 수 있습니다.          |

### <a name="meetings-and-conferencing"></a>모임 및 회의


|평가  |알리는 내용  |
|---------|---------|
|Teams 라이선스     |사용 가능한 Teams 라이선스가 포함된 활성 구독이 있는지 여부 |
|Exchange 라이선스     |사용 가능한 Exchange Online 라이선스가 포함된 활성 구독이 있는지 여부 기본 Teams 기능을 사용하는 데는 Exchange가 필요하지 않지만 Exchange와 통합하면 최상의 Teams 환경이 제공됩니다. |
|오디오 회의 라이선스    |오디오 회의 라이선스가 포함된 활성 구독이 있는지 여부 |
|Stream 라이선스     |모임 녹음/녹화를 원하는 경우에 사용할 수 있는 Stream 라이선스가 포함된 활성 구독이 있는지 여부 |
|게스트 액세스     |게스트 액세스가 Teams에서 켜져 있는 경우 게스트 액세스에 대한 Azure Active Directory 설정은 검토되지 않습니다.|
|베니티 도메인     |테넌트에 대해 @onmicrosoft.com이 아닌 도메인이 구성되어 있는지 여부  |
|외부 액세스     |외부 액세스가 켜져 있는 경우 Teams에서 외부 조직과 통신할 수 있습니다. |


### <a name="advisor-bot"></a>관리자 봇
관리자가 배포 팀을 만들면 관리자 봇에서 다음 메시지를 제공합니다.

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
> Advisor for Teams 봇은 기본적으로 사용하도록 설정되어 있습니다. Advisor for Teams를 사용하거나 여기에서 계획할 경우 사용하지 않도록 설정하지 마십시오.


## <a name="frequently-asked-questions"></a>자주하는 질문
### <a name="what-are-the-licensing-requirements-for-advisor-for-teams"></a>Advisor for Teams에 대한 라이선스 요구 사항은 무엇인가요?
Teams에 대한 라이선싱 외애에 다른 추가 라이선스 요구 사항은 없습니다.

### <a name="can-i-delete-the-deployment-team"></a>배포 팀을 삭제할 수 있나요?
Advisor for Teams에서 배포 팀을 만든 이후 삭제 기능을 포함해 다른 모든 팀과 같이 팀을 관리하십시오. Teams 관리 센터를 사용하여 팀을 삭제하지 않는 경우 팀이 존재하는 것으로 보고 됩니다.

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
