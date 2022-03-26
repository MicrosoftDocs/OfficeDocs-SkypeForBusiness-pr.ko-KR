---
title: Microsoft Teams의 앱, 봇 및 커넥터
ms.reviewer: ''
description: 앱, 인공 지능 및 커넥터에 대해 알아보고 조직의 프로필 및 비즈니스 요구 사항에 따라 Microsoft Teams에서 배포할 대상을 결정하는 방법에 대해 알아봅니다.
ms.topic: article
author: guptaashish
ms.author: guptaashish
manager: prkosh
audience: admin
ms.date: 02/10/2021
ms.service: msteams
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
ms.localizationpriority: high
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: be7ee83b510096d8d6ffc0c4a0a5984917ad55c5
ms.sourcegitcommit: 42c355d3f4bbe52c063b8f2119baefc0b88f9563
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2022
ms.locfileid: "64403979"
---
# <a name="about-apps-in-microsoft-teams"></a>Microsoft Teams의 앱 정보

앱을 사용하여 자주 사용하는 서비스에서 콘텐츠를 찾고 Teams에서 공유할 수 있습니다. 앱을 통해 채널 상단에 있는 서비스를 고정하거나 봇과 채팅하거나 작업을 공유하고 지정하는 등의 작업을 수행 할 수 있습니다. 자세한 내용은 [Teams의 앱 개요](https://support.office.com/article/overview-of-apps-in-teams-747492ee-7cdd-4115-a993-8c7e7f98a3d0)를 참조하세요.

Microsoft Teams와 함께 제공되는 앱을 사용하거나, 인증된 타사 앱 및 템플릿을 사용하거나 또는 사용자 지정 앱을 만들어 팀 배포에 앱을 추가할 수 있습니다.

## <a name="use-microsoft-provided-apps"></a>Microsoft 제공 앱 사용

Teams는 목록, 작업, 칭찬, 승인 등의 기본 제공 앱 집합을 제공합니다. 초기 Teams 롤아웃을 진행 시 Planner와 같은 Teams 추천 앱을 포함하는 것이 좋습니다. Teams의 채택을 주도하면서 다른 앱, 봇 및 커넥터를 추가합니다.

## <a name="use-third-party-apps"></a>타사 앱 사용

Microsoft에서 제공하는 앱 외에도 Microsoft에서 인증한 타사 앱을 사용할 수 있습니다. Microsoft는 Microsoft 365 개발자 파트너와 협력하여 Teams 앱 및 추가 기능을 사용하는 데 필요한 정보를 제공합니다. 자세한 내용은 [Microsoft Teams 앱 보안 및 규정 준수](/microsoft-365-app-certification/teams/teams-apps)를 참조하세요.

## <a name="use-open-source-sample-apps-provided-by-microsoft"></a>Microsoft에서 제공하는 오픈 소스 샘플 앱 사용

또한 커뮤니티 기반, 오픈 소스 및 GitHub에서 사용할 수 있는 Microsoft Teams용 [Teams 템플릿](/microsoftteams/platform/samples/app-templates?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fMicrosoftTeams%2ftoc.json), 프로덕션 지원 앱을 사용할 수 있습니다.

## <a name="create-custom-apps"></a>사용자 지정 앱 만들기

[Microsoft Power Platform](/microsoftteams/platform/samples/teams-low-code-solutions) 및 Teams 통합을 사용하여 사용자 지정 낮은 코드 솔루션을 빠르게 빌드할 수 있습니다. 비즈니스 요구에 맞게 사용자 지정 앱을 만들 수도 있습니다. 자세한 내용은 [Microsoft Team용 앱 빌드](/microsoftteams/platform/overview)를 참조하세요.  

## <a name="apps-deployment-decisions"></a>앱 배포 결정사항

Teams는 조직에 즉시 사용할 수 있는 우수한 협업 환경을 제공하며, 대부분의 조직에서는 기본 설정이 사용된다는 사실을 알게 됩니다. 이 자료에서는 조직의 프로필 및 비즈니스 요구 사항에 따라 기본 설정을 변경할지 여부를 결정하는 데 도움이 되며, 각 변경 사항을 안내합니다. Microsoft는 설정을 두 그룹으로 나누었고, 첫 번째 그룹은 [사용자가 수행할 가능성이 더 높은 변경사항](#core-deployment-decisions)의 핵심 세트부터 시작합니다. 두 번째 그룹에는 조직의 필요에 따라 구성할 수 있는 [추가 설정](#additional-deployment-decisions)이 포함됩니다.

## <a name="core-deployment-decisions"></a>핵심 배포 결정사항

대부분의 조직이 변경하려는 앱 설정입니다 (Teams의 기본 설정이 적합하지 않은 경우).

### <a name="app-availability-settings"></a>앱 가용성 설정

Teams는 사용자를 참여시키고 생산성을 지원하며 일반적으로 사용되는 비즈니스 서비스를 Teams로 통합하기 위한 Microsoft 및 타사에서 게시한 앱을 제공합니다.
Teams 스토어에서 앱을 다운로드합니다. 기본적으로 [Teams 스토어 승인 프로세스](/microsoftteams/platform/publishing/apps-publish#microsoft-teams-app-approval-process)를 통해 제출한 사용자 지정 앱을 포함하여 모든 앱이 모든 사용자에게 설정됩니다. 예를 들어, 사용자는 Planner 앱을 사용하여 Teams에서 팀 작업을 구축하고 관리할 수 있습니다.

기본적으로 모든 Microsoft 제공, 타사 및 사용자 지정 앱을 사용할 수 있으며 개별 앱을 설정하거나 해제할 수 있습니다. 전체 조직에 대해 모든 타사 및/또는 사용자 지정 앱을 설정하거나 해제할 수 있는 조직 차원의 설정이 있습니다.

| 본인에게 질의하기 | 작업 |
|--------------|--------|
|기본 Teams 앱 설정을 변경하시겠습니까? | 조직에서 앱을 관리하는 데 사용할 수 있는 정책과 설정에 대한 자세한 내용은 [Microsoft Teams에서 앱 관리 설정](admin-settings.md)을 참조하세요.|

### <a name="app-permissions-and-other-considerations"></a>앱 사용 권한 및 기타 고려 사항

앱은 사용자가 동의하고 정책을 통해 관리자나 IT 전문가가 관리합니다. 그러나 전반적으로 앱의 사용 권한 및 위험 프로필이 앱 자체에 정의됩니다.

앱은 사용자가 동의하고 정책을 통해 관리자나 IT 전문가가 관리합니다. 그러나 앱의 사용 권한 및 위험 프로필이 앱 자체에 정의됩니다.

| 본인에게 질의하기 | 작업 |
|--------------|--------|
|<br>액세스를 허용하려는 앱은 무엇인가요? 액세스를 허용하지 않으려는 앱은 무엇인가요?  | <ul><li>앱, 봇, 탭 또는 커넥터에 대한 액세스를 허용할 때 고려해야 할 사항의 목록을 보려면 [Microsoft Teams 앱 사용 권한과 고려 사항](app-permissions.md)을 참조하세요.</li><li>조직의 사용자가 앱을 사용할 수 있도록 하는 방법에 대한 자세한 내용은 [Microsoft Teams 관리 센터에서 앱 관리](manage-apps.md)를 참조하세요.</li></ul>|

### <a name="bots-for-private-chats-and-channels"></a>개인 채팅 및 채널을 위한 봇

봇은 사용자가 흥미를 느끼거나 정보를 얻고자 하는 세부 정보에 대해 쿼리에 응답하거나 업데이트 및 알림을 제공하는 자동화된 프로그램입니다. 봇은 Teams 채팅을 통해 사용자가 클라우드 서비스(예: 작업 관리, 일정 관리 및 설문조사 등)와 상호 작용할 수 있도록 해줍니다. Teams는 개인 채팅 및 채널을 통해 봇을 지원합니다. 관리자는 Microsoft 365 혹은 Office 365 조직에서 봇의 사용을 허용할지 여부를 제어할 수 있습니다.

| 본인에게 질의하기 | 작업 |
|--------------|--------|
|조직에서 사용자 지정 봇을 허용하고 싶으신가요?|봇 추가에 대한 자세한 내용은 [Microsoft Teams에서 개인 채팅 및 채널을 위한 봇 추가](/microsoftteams/platform/bots/what-are-bots)를 참조하세요. 사용자 지정 봇을 켜거나 끄는 방법에 대한 자세한 내용은 [Microsoft Teams에서 앱 관리 설정](admin-settings.md)을 참조하세요.|

### <a name="built-in-and-custom-tabs"></a>기본 제공 및 사용자 지정 탭

소유자와 팀 구성원은 채널, 비공개 채팅 및 그룹 채팅에 탭을 추가하여 클라우드 서비스와 통합할 수 있습니다. 사용자가 필요로 하거나 가장 많이 사용하는 데이터에 액세스하고 관리하는 데 도움이 되는 탭을 추가합니다. 채널에서는 대화 및 파일 탭이 기본적으로 생성됩니다. 모든 개인 채팅에서 대화, 파일, 조직 및 활동 탭이 기본적으로 생성됩니다. 이러한 기본 제공 탭 외에도 사용자 지정 탭을 디자인하고 추가할 수 있습니다. 조직에서 Teams 앱을 켜거나 끄는 방법에 대해 알아보려면 [Team에서 앱에 대한 관리 설정](admin-settings.md)을 참조하세요.

| 본인에게 질의하기 | 작업 |
|--------------|--------|
|조직에서 사용자 지정 탭을 허용하고 싶으신가요?|자세한 내용은 [Teams에서 기본 제공 및 사용자 지정 탭 사용](built-in-custom-tabs.md)을 참조하세요.|

### <a name="custom-connectors"></a>사용자 지정 커넥터

커넥터는 자주 사용하는 서비스의 콘텐츠와 업데이트를 채널에 직접 제공하여 팀을 최신 상태로 유지합니다. 커넥터를 사용하면 Teams 사용자는 Teams 채팅에서 Twitter, Trello, Wunderlist, GitHub 및 Azure DevOps 서비스와 같은 인기 서비스로부터 업데이트를 받을 수 있습니다.

| 본인에게 질의하기 | 작업 |
|--------------|--------|
|사용자가 사용자 지정 커넥터를 만들 수 있도록 허용하고 싶나요?|자세한 내용은 [Teams에서 사용자 지정 커넥터 사용](office-365-custom-connectors.md)을 참조하세요.|

## <a name="additional-deployment-decisions"></a>추가 배포 결정사항

조직의 요구 사항 및 구성에 따라 이러한 설정을 변경하는 것이 좋습니다.

### <a name="activity-reports"></a>활동 보고서

활동 보고서를 사용하여 조직의 사용자가 Teams를 어떻게 사용하고 있는지 확인할 수 있습니다. 예를 들어, 아직 Teams를 사용하고 있지 않은 경우 Teams를 사용하여 생산성과 공동 작업을 향상 시키는 방법을 모를 수도 있습니다. 조직에서 활동 보고서를 사용하여 교육 및 커뮤니케이션 노력에 대한 우선 순위를 결정할 수 있습니다. 활동 보고서를 보려면 Microsoft 365 혹은 Office 365의 전역 관리자, Teams 서비스 관리자 또는 비즈니스용 Skype 관리자여야 합니다.

| 본인에게 질의하기 | 작업 |
|--------------|--------|
| <br>활동 보고서를 확인해야 하는 사용자는 누구이고 그들은 보고서를 볼 수 있는 올바른 권한을 보유하고 있나요? |<ul><li>사용자에게 관리자 역할을 할당하고 싶지 않은 경우 [보고서 읽기 역할을 할당](teams-activity-reports.md#reports-reader-role)할 수 있습니다.</li><li>Azure Active Directory에서 관리자 역할을 할당하는 방법에 대한 자세한 내용은 [역할 및 사용 권한](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)과 [역할 보기 및 할당](/azure/active-directory/users-groups-roles/directory-manage-roles-portal)을 참조하세요.</li></ul> |

### <a name="app-templates"></a>앱 서식 파일

앱 서식 파일은 커뮤니티 중심의 오픈 소스이며 GitHub에서 사용할 수 있는 Microsoft Teams용 프로덕션 준비 앱입니다. 각각에는 조직에 해당 앱을 배포 및 설치하는 방법에 대한 자세한 지침이 포함되어 있으며, 즉시 설치하고 사용할 수 있는 바로 사용 가능한 앱을 제공합니다.

전체 소스 코드도 제공되므로 세부 정보를 살펴보고 코드를 포크하여 특정 요구 사항에 맞게 변경할 수 있습니다.

| 본인에게 질의하기 | 작업 |
|--------------|--------|
| Icebreaker와 같은 Teams 앱 서식 파일을 설치하고 싶으세요? |자세한 내용을 보려면 [Teams용 앱 서식 파일](/microsoftteams/platform/samples/app-templates?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=MicrosoftTeams%2ftoc.json)을 읽어보세요.|
