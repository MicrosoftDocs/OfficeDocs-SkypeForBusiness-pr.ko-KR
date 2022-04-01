---
title: Microsoft Teams의 앱 정보 알기
ms.reviewer: ''
description: 앱에 대해 알아보고 조직의 프로필 및 비즈니스 요구 사항에 따라 Teams에서 허용할 앱을 결정합니다.
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
ms.openlocfilehash: b6fd5ef344550cf85420faef1748c34f6e87e88b
ms.sourcegitcommit: cbdc80c302e97d18a923ef57bb5d4b6cf7676d00
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/30/2022
ms.locfileid: "64556529"
---
# <a name="about-apps-in-microsoft-teams"></a>Microsoft Teams의 앱 정보

앱을 사용하여 자주 사용하는 서비스에서 콘텐츠를 찾고 Teams에서 공유할 수 있습니다. 채널 맨 위에 서비스를 고정하거나, 봇을 사용하여 알림을 자동화하거나, 작업을 공유하고 할당하는 등의 작업을 수행할 수 있습니다. 앱 사용에 대한 자세한 내용은 [최종 사용자용 앱 개요](https://support.office.com/article/overview-of-apps-in-teams-747492ee-7cdd-4115-a993-8c7e7f98a3d0)를 참조하세요.

최종 사용자가 Teams에서 사용할 수 있는 다양한 유형의 앱은 Microsoft에서 만든 앱, 인증된 타사 앱 및 자체 조직에서 만든 사용자 지정 앱입니다.

## <a name="use-microsoft-provided-apps"></a>Microsoft 제공 앱 사용

Teams는 목록, 작업, 칭찬, 승인 등의 기본 제공 앱 집합을 제공합니다. 초기 Teams 롤아웃을 진행 시 Planner와 같은 Teams 추천 앱을 포함하는 것이 좋습니다. Teams 채택을 추진할 때 다른 앱을 추가합니다. 활동 스트림, 채팅, 일정 및 통화와 같은 일부 기본 기능은 기본적으로 사용할 수 있으며 최종 사용자가 쉽게 액세스할 수 있도록 고정됩니다.

## <a name="use-third-party-apps"></a>타사 앱 사용

Microsoft에서 제공하는 앱 외에도 Microsoft에서 인증한 타사 앱을 사용할 수 있습니다. Microsoft는 Microsoft 365 개발자 파트너와 협력하여 Teams 앱 사용에 대한 결정을 신속하게 처리하는 데 필요한 정보를 제공합니다. 자세한 내용은 [Microsoft Teams 앱 보안 및 규정 준수](/microsoft-365-app-certification/teams/teams-apps)를 참조하세요.

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

앱은 사용자가 동의하고 정책을 통해 관리자나 IT 전문가가 관리합니다. 그러나 앱의 사용 권한 및 위험 프로필이 앱 자체에 정의됩니다.

| 본인에게 질의하기 | 작업 |
|--------------|--------|
|<br>액세스를 허용하려는 앱은 무엇인가요? 액세스를 허용하지 않으려는 앱은 무엇인가요?  | <ul><li>앱, 봇, 탭 또는 커넥터에 대한 액세스를 허용할 때 고려해야 할 사항의 목록을 보려면 [Microsoft Teams 앱 사용 권한과 고려 사항](app-permissions.md)을 참조하세요.</li><li>조직의 사용자가 앱을 사용할 수 있도록 하는 방법에 대한 자세한 내용은 [Microsoft Teams 관리 센터에서 앱 관리](manage-apps.md)를 참조하세요.</li></ul>|

<!--- TBD: Rewrite this to talk about bots and tabs as a capability of apps. Admins do not govern bots, tabs, etc. Admins only govern apps that contain capabilities such as connectors, bots, etc. This writeup gives an impression that admins manage apps + bots + tabs + connectors, etc.

### Bots for private chats and channels

Bots are automated programs that respond to queries or give updates and notifications about details users find interesting or want to stay informed about. Bots allow users to interact with cloud services such as task management, scheduling, and polling in a Teams chat. Teams supports bots in private chats and channels. Administrators can control whether the use of bots is allowed in a Microsoft 365 or Office 365 organization.

| Ask yourself | Action |
|--------------|--------|
|Do I want to allow custom bots in my organization?|For more information about adding bots, see [Add bots for private chats and channels in Microsoft Teams](/microsoftteams/platform/bots/what-are-bots). For information about turning custom bots on or off, see [Admin settings for apps in Microsoft Teams](admin-settings.md).|

### Built-in and custom tabs

Owners and team members can add tabs to a channel, private chat, and group chat to help integrate their cloud services. Add tabs to help users access and manage the data they need or use the most. In channels, the Conversations and Files tabs are created by default. In every private chat, the Conversations, Files, Organization, and Activity tabs are created by default. In addition to these built-in tabs, you can design and add custom tabs. To learn about turning Teams apps on or off for your organization, read [Admin settings for apps in Teams](admin-settings.md).

| Ask yourself | Action |
|--------------|--------|
|Do I want to allow custom tabs in my organization?|For more information, see [Use built-in and custom tabs in Teams](built-in-custom-tabs.md).|

### Custom connectors

Connectors keep your team current by delivering content and updates from services you frequently use directly into a channel. With connectors, your Teams users can receive updates from popular services such as Trello, Wunderlist, GitHub, and Azure DevOps Services in their Teams chats.

| Ask yourself | Action |
|--------------|--------|
|Do I want to allow users to create custom connectors?|For more information, see [Use custom connectors in Teams](office-365-custom-connectors.md).|

--->

## <a name="additional-deployment-decisions"></a>추가 배포 결정사항

조직의 요구 사항 및 구성에 따라 이 설정을 변경할 수 있습니다.

### <a name="activity-reports"></a>활동 보고서

활동 보고서를 사용하여 조직의 사용자가 Teams를 어떻게 사용하고 있는지 확인할 수 있습니다. 예를 들어, 아직 Teams를 사용하고 있지 않은 경우 Teams를 사용하여 생산성과 공동 작업을 향상 시키는 방법을 모를 수도 있습니다. 조직에서 활동 보고서를 사용하여 교육 및 커뮤니케이션 노력에 대한 우선 순위를 결정할 수 있습니다. 활동 보고서를 보려면 Microsoft 365 혹은 Office 365의 전역 관리자, Teams 서비스 관리자 또는 비즈니스용 Skype 관리자여야 합니다.

| 본인에게 질의하기 | 작업 |
|--------------|--------|
| <br>활동 보고서를 확인해야 하는 사용자는 누구이고 그들은 보고서를 볼 수 있는 올바른 권한을 보유하고 있나요? |<ul><li>사용자에게 관리자 역할을 할당하고 싶지 않은 경우 [보고서 읽기 역할을 할당](teams-activity-reports.md#reports-reader-role)할 수 있습니다.</li><li>Azure Active Directory에서 관리자 역할을 할당하는 방법에 대한 자세한 내용은 [역할 및 사용 권한](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)과 [역할 보기 및 할당](/azure/active-directory/users-groups-roles/directory-manage-roles-portal)을 참조하세요.</li></ul> |

### <a name="app-templates"></a>앱 서식 파일

앱 서식 파일은 커뮤니티 중심의 오픈 소스이며 GitHub에서 사용할 수 있는 Microsoft용 프로덕션 준비 앱입니다. 각 앱에는 조직에 맞게 배포하고 설치하기 위한 자세한 지침이 포함되어 있으며 즉시 설치하고 사용할 수 있는 바로 사용 가능한 앱입니다.

전체 소스 코드도 제공되므로 세부 정보를 살펴보고 코드를 포크하여 특정 요구 사항에 맞게 변경할 수 있습니다.

| 본인에게 질의하기 | 작업 |
|--------------|--------|
| Icebreaker와 같은 Teams 앱 서식 파일을 설치하고 싶으세요? |자세한 내용을 보려면 [Teams용 앱 서식 파일](/microsoftteams/platform/samples/app-templates?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=MicrosoftTeams%2ftoc.json)을 읽어보세요.|
