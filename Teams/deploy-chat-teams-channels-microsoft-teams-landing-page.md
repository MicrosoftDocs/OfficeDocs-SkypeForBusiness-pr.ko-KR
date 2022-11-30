---
title: Microsoft Teams에서의 채팅, 팀, 채널 & 앱
ms.reviewer: ''
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
ms.subservice: teams-chat
audience: admin
search.appverid: MET150
description: Microsoft Teams의 채팅, 팀, 앱 및 채널에 대한 Teams 설정을 구성하기 위한 단계별 지침이 포함되어 있습니다.
ms.localizationpriority: high
ms.collection:
- M365-collaboration
- m365initiative-deployteams
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.dashboard.helparticle.quickstartteamsadmin
- intro-get-started
- seo-marvel-apr2020
- seo-marvel-may2020
appliesto: Microsoft Teams
ms.openlocfilehash: dd54d3eb8f7512a9e0f5bc7491decb2b080944b6
ms.sourcegitcommit: 167868ad6fc02676cfdade5d498e7c4e09778bec
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/30/2022
ms.locfileid: "69190339"
---
# <a name="chat-teams-channels--apps-in-microsoft-teams"></a>Microsoft Teams에서의 채팅, 팀, 채널 & 앱

Teams provides a great out-of-the-box collaboration experience for your organization, and most organizations find that the default settings work for them. This article helps you decide whether to change any of the default settings, based on your organization's profile and business requirements, then it walks you through each change. We've split the settings into two groups, starting with the core set of [changes you're more likely to make](#core-deployment-decisions). The second group includes the [additional settings](#additional-deployment-decisions) you may want to configure, based on your organization's needs.

시작하려면 당사의 짧은 Teams 채팅, 팀 그리고 채널 비디오(4:30분)를 시청하세요.

<br/>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE476Yj?autoplay=false]

You can use [Advisor for Teams](use-advisor-teams-roll-out.md) to help you roll out Microsoft Teams. Advisor for Teams walks you through your Teams rollout. It assesses your Microsoft 365 environment and identifies the most common configurations that you may need to update or modify before you can successfully roll out Teams.

> [!TIP]
> 초기 Teams 롤아웃을 진행 시 Planner와 같은 추천 앱을 포함하는 것이 좋습니다. Teams 채택을 추진할 때 다른 Teams [앱을](deploy-apps-microsoft-teams-landing-page.md) 추가합니다.

 > [!Note]
 > 여러 플랫폼에서의 Teams 기능에 대한 자세한 내용은 [플랫폼별 Teams 기능을 참조](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)하세요.

## <a name="chat-deployment-prerequisites"></a>채팅 배포 전제 조건

Before you roll out Teams across your organization, take time to confirm that your environment is ready for Teams. Review [Prepare your organization's network for Teams](prepare-network.md) and make any required changes to your environment.

|본인에게 질의하기|작업 |
|------------|-------|
|조직에서 Teams를 배포할 준비가 되었는가?|이 질문에 답변하려면 다음의 사항을 참조하세요: <ul><li>[Teams에 대한 조직의 네트워크 준비](prepare-network.md)</li><li>[URL 및 IP 주소 범위](office-365-urls-ip-address-ranges.md)</li><li>[팀을 만들 때 Microsoft 365 그룹에 대한 계획](plan-office-365-groups.md)</li></ul>|

## <a name="core-deployment-decisions"></a>핵심 배포 결정사항

이들은 대부분의 조직이 변경하려는 채팅, 팀 그리고 채널의 설정입니다(기본 설정이 조직에 적합하지 않은 경우).

### <a name="teams-administrators"></a>Teams 관리자

Teams provides a set of custom administrator roles that can be used to manage Teams for your organization. The roles provide various capabilities to administrators.

| 본인에게 질의하기 | 작업 |
|--------------|--------|
|Teams 커뮤니케이션 관리자 역할은 누구에게 할당될 것인가요?|Teams 관리자 역할에 대한 자세한 내용은 [팀을 관리하기 위한 Microsoft Teams 관리 역할의 활용](using-admin-roles.md)을 참조하세요.|
|Teams 커뮤니케이션 지원 기술자 역할은 누구에게 할당될 것인가요?|관리 역할을 할당하려면 [Azure Active Directory를 사용하여 사용자에게 관리자 및 비관리자 역할 할당](/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal)을 참조하세요.|
|Teams 커뮤니케이션 지원 전문가자 역할은 누구에게 할당될 것인가요?||

### <a name="teams-owners-and-members"></a>Teams 소유자 및 구성원

In addition to administrator roles, Teams lets you assign owner and member user roles, and selectively give them moderator capabilities (if moderation has been set up) to control who can perform certain actions within a channel. Moderation allows you to control who can start new posts in a channel, add and remove team members as moderators, and control whether team members can reply to existing channel messages.

|본인에게 질의하기|작업 |
|------------|-------|
|각 역할에는 누가 할당되어야 하나요? | 각 역할의 기능을 비교하려면 [Microsoft Teams에서 팀 소유자, 조정자 및 구성원 할당하기](assign-roles-permissions.md)를 참조하세요.
|사용자 역할은 어떻게 할당하나요? | 역할을 할당하거나 변경하려면 [사용자 역할 할당](assign-roles-permissions.md)을 참조하세요.
|채널에서 게시나 회신을 할 수 있는 사용자를 통제해야 하나요? | 조정 기능을 구성하려면 [Microsoft Teams에서 채널 조정 설정 및 관리](manage-channel-moderation-in-teams.md)를 참조하세요.

### <a name="messaging-policies"></a>메시징 정책

Messaging policies control which chat and channel messaging features are available to users in Teams. For example, who can edit and delete sent messages, who can use chat, who can use memes in conversations, and more. By default, users are assigned the global messaging policy and all features are **On**. You can use the default global policy or create one or more custom messaging policies for people in your organization.

|본인에게 질의하기|작업 |
|------------|-------|
|전역 메시징 정책을 사용자 지정해야 하나요?|Microsoft Teams 관리 센터를 사용하여 전역 메시징 정책을 변경하거나 새 정책을 추가하는 방법에 대한 자세한 내용은 [Teams에서 메시징 정책 관리](messaging-policies-in-teams.md)를 참조하세요.|
|여러개의 메시징 정책이 필요한가요?|PowerShell에서 메시징 정책을 만들고 할당하려면 [PowerShell 스크립트 샘플 - 메시징 정책 만들기 및 할당](scripts/powershell-script-teams-messaging-policy-edu.md)을 참조하세요.|
|어떠한 사용자 그룹에 어떠한 메시징 정책을 할당할지를 어떻게 결정하나요?|CsTeamsMessagingPolicy cmdlet에 대한 내용은 [설정-CsTeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy)를 참조하세요.|

### <a name="external-access"></a>외부 액세스

External access (federation) lets your users communicate with people outside of your organization via chat. By turning this on and adding domains to the allowed list, your users can communicate with users in other domains and organizations. External access is turned on by default.

|본인에게 질의하기|작업 |
|------------|-------|
|<ul><li>조직에서 외부 모임 및 채팅을 끌까요?</li><li>이 기능을 사용하는 경우 나의 조직에서 통신할 수 있는 도메인을 제한하게 되나요?</li></ul> |<br>외부 모임 및 채팅을 켜거나 끄려면 [외부 모임 및 채팅 관리](manage-external-access.md)를 참조하세요.|

### <a name="guest-access"></a>게스트 액세스

Guest access in Teams lets individuals outside your organization access teams and channels. You can use the guest access settings to control which features guests can or can't use. Guest access is turned on by default. To learn more, see [Guest access in Teams](./guest-access.md).

> [!NOTE]
> 외부 액세스 및 게스트 액세스에 대한 자세한 내용은 [Microsoft Teams의 다른 조직의 사용자와 통신](communicate-with-users-from-other-organizations.md)을 참조하세요

|본인에게 질의하기|작업 |
|------------|-------|
|나의 조직의 Teams 액세스 기능을 꺼야 하나요?|게스트 액세스를 켜거나 끄려면 [Teams에서 게스트 액세스 설정 또는 해제](set-up-guests.md)를 참조하세요.|
|이 기능을 사용하는 경우 조직의 게스트가 사용할 수 있는 기능을 사용자 지정할 수 있나요?|게스트 액세스 기능의 가용성을 사용자 지정 하려면 [Teams에서 게스트 액세스 권한 부여](teams-dependencies.md)를 참조하세요.|

### <a name="private-channels"></a>비공개 채널

비공개 채널을 사용하면 팀 구성원의 하위 집합이 다른 팀 구성원이 보거나 액세스할 수 없는 비공개 공간에서 공동 작업할 수 있습니다. 이미 팀 구성원인 경우 게스트를 포함한 모든 사용자가 비공개 채널의 구성원으로 추가될 수 있습니다.

|본인에게 질의하기|작업 |
|------------|-------|
|팀 소유자와 구성원이 비공개 채널을 만들 수 있도록 허용해야하나요?|조직에 대한 비공개 채널 정책을 설정하려면 [Microsoft Teams에서 채널 정책 관리](teams-policies.md)를 참조하세요.|

### <a name="shared-channels"></a>공유 채널

공유 채널을 사용하면 팀의 구성원이 아닌 사용자를 채널에 추가할 수 있습니다. 여기에는 조직 외부에 있는 사용자가 포함됩니다. 공유 채널은 외부 사용자가 디렉터리에 게스트 계정을 필요로 하지 않는다는 점에서 게스트 액세스보다 더 많은 이점을 제공합니다.

|본인에게 질의하기|작업 |
|------------|-------|
|어떤 상황에서 공유 채널과 게스트 액세스를 사용해야 하나요?|[Microsoft Teams의 공유 채널](shared-channels.md)을 참조하세요.|
|<ul><li>팀 소유자가 공유 채널을 만들 수 있도록 허용해야 하나요?</li><li>팀 소유자가 조직 외부의 사용자와 채널을 공유할 수 있도록 허용해야 하나요?</li><li>사용자가 조직 외부의 공유 채널에 참여할 수 있도록 허용해야 하나요?</li></ul> |<br>조직에 대한 공유 채널 정책을 설정하려면 [Microsoft Teams에서 채널 정책 관리](teams-policies.md)를 참조하세요.|

### <a name="teams-settings"></a>Teams 설정

Teams settings let you set up your teams for features such as email integration, cloud storage options, organization tab, meeting room device setup, and search scope. When you make changes to these settings, they apply to all the teams in your organization. To learn more, see [Teams settings](enable-features-office-365.md#teams-settings).

|본인에게 질의하기|작업 |
|------------|-------|
|나의 조직의 Teams 설정을 사용자 지정할 수 있나요? | Teams 설정 및 사용자 지정 방법에 대한 내용은 [Teams 설정](enable-features-office-365.md#teams-settings)을 참조하세요.|

### <a name="teams-clients"></a>Teams 클라이언트

Teams supports a number of clients from web to desktop to mobile, and the default configuration lets users choose whichever clients they want. To learn more, see [Get clients for Teams](get-clients.md).

|본인에게 질의하기|작업 |
|------------|-------|
|나의 조직의 Teams 클라이언트 가용성을 사용자 지정할 수 있나요?|[Teams 앱의 하드웨어 요구 사항](hardware-requirements-for-the-teams-app.md)을 참조합니다. |
|나의 조직의 Teams 클라이언트 설정을 사용자 지정할 수 있나요?|[MSI를 사용하여 Teams를 설치](msi-deployment.md)하는 방법을 학습하세요.|

### <a name="teams-usage-reporting"></a>Teams 사용 현황 보고

The Global Admin, Teams Service Admin, and Reports Readers roles can view Teams usage reports. To learn more, see the [Microsoft 365 usage analytics](/microsoft-365/admin/usage-analytics/usage-analytics).

|본인에게 질의하기|작업 |
|------------|-------|
|<br> 팀 사용 현황 보고서를 확인해야 하는 사용자는 누구이고 그들은 보고서를 볼 수 있는 올바른 역할을 보유하고 있나요? |<ul><li>사용자가 관리자가 아닌 경우에는 [보고서 리더 역할을 할당합니다](teams-activity-reports.md#reports-reader-role).</li><li>[역할 및 사용 권한](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)과 [역할 보기 및 지정](/azure/active-directory/users-groups-roles/directory-manage-roles-portal)을 참조하여 Azure Active Directory에서 관리 역할을 할당하는 방법을 알아보세요.|

### <a name="teams-default-apps"></a>Teams 기본 앱

Teams provides a number of first-party (Microsoft provided) and third-party apps to engage users, support productivity, and integrate commonly used business services into Teams. Get apps from the Teams Store. Apps are turned on by default in Teams.

Teams에서 앱을 배포하고 관리하는 방법에 대한 자세한 내용은 심층 [적인 앱 관리](deploy-apps-microsoft-teams-landing-page.md) 지침을 참조하세요.

## <a name="additional-deployment-decisions"></a>추가 배포 결정사항

조직의 요구 사항 및 구성에 따라 이러한 설정을 변경하는 것이 좋습니다.

### <a name="teams-licensing"></a>Teams 라이선싱

Teams는 많은 Microsoft 365 라이선스의 일부로 제공됩니다.

|본인에게 질의하기|작업 |
|------------|-------|
|사용자는 배포하려는 모든 Teams의 기능을 사용하기 위해 필요한 라이선스가 있나요? | 라이선싱 요구 사항에 대한 자세한 내용은 [Microsoft Teams 서비스 설명](/office365/servicedescriptions/teams-service-description)을 읽어 보세요.|

### <a name="exchange-and-sharepoint-interoperability"></a>Exchange 및 SharePoint 상호 운용성

For the full Teams experience, every user should be enabled for Exchange, SharePoint, and Microsoft 365 group creation. The following articles outline information related to Exchange mailboxes hosted in various environments, how Exchange and Teams interact, and similar considerations for SharePoint and OneDrive.

|본인에게 질의하기|작업 |
|------------|-------|
| 현재의 Exchange 및 SharePoint 배포에 필요한 Teams의 기능을 배포할 수 있나요? |Teams에서의 Exchange 및 SharePoint에 대한 자세한 내용은 다음을 참조하세요:<ul><li> [Exchange와 Teams의 상호 작용 방법](exchange-teams-interact.md)</li><li>[SharePoint Online 및 OneDrive가 Teams와 상호 작용하는 방법](sharepoint-onedrive-interact.md)|

### <a name="teams-limits-and-specifications"></a>Teams의 제한과 사양

Teams의 엔터프라이즈 배포를 계획할 때 팀의 최대 구성원 수, 사용자가 만들 수 있는 최대 팀 수 등과 같은 관련 제한 사항과 사양을 고려해 야 합니다.

|본인에게 질의하기|작업 |
|------------|-------|
| Teams의 배포 시 나는 어떠한 제한에 걸리기 쉽나요? | 자세한 내용은 [Teams의 제한과 사양](limits-specifications-teams.md)를 참조하세요. |

### <a name="urls-and-ports"></a>URL 및 포트

Organizations that maintain fine-grained control of their internet traffic should read [URLs and IP address ranges](/office365/enterprise/urls-and-ip-address-ranges) for an up-to-date list of the URLs, IP addresses, ports, and protocols that must be correctly configured for Teams. Microsoft is continuously improving the Microsoft 365 services and adding new functionality, which means the required ports, URLs, and IP addresses may change over time. We recommend that you subscribe via RSS to receive notifications when this information is updated or changed. At a minimum, make sure you've opened the ports listed above in [Chat deployment prerequisites](#chat-deployment-prerequisites).

|본인에게 질의하기|작업 |
|------------|-------|
| 사용자가 Teams를 사용할 수 있도록 하려면 인터넷 액세스 규칙이 필요한가요 혹은 필요한 최소 포트를 여는 것으로 충분하나요? | 자세한 내용은 [URL 및 IP 주소 범위](office-365-urls-ip-address-ranges.md)를 참조하세요.|

### <a name="governance-naming-conventions-who-can-create-teams"></a>거버넌스 (팀을 만들 수 있는 사용자 명명 규칙)

Your organization might require that you implement controls on how teams are named and classified, who can create teams, and team expiration, retention, and archiving. This is called governance. You can use Azure Active Directory (Azure AD) to configure each of these areas.

| 본인에게 질의하기 | 작업 |
|--------------|--------|
|팀을 만들 수 있는 사용자에 대한 제어를 수행해야 하나요?| [Teams에서의 거버넌스 계획](plan-teams-governance.md)을 참조하세요.|
|Teams의 명명 규칙 방식에 대한 제어를 수행해야 하나요?|[Azure AD에서 Microsoft 365 그룹에 대한 명명 정책 적용](/azure/active-directory/users-groups-roles/groups-naming-policy)을 참조하세요.|

### <a name="teams-application-policy-side-rail-control"></a>Teams 응용 프로그램 정책(측면 레일 제어)

A pinned app shows up in the side rail in Teams. By creating Teams application policies, you can preconfigure sets of pinned Teams apps to personalize Teams for select groups of users. By default, the **Allow external apps in Microsoft Teams** setting is turned on.

| 본인에게 질의하기 | 작업 |
|--------------|--------|
|미리 구성된 고정된 Teams 응용 프로그램의 집합을 만들어야 하나요? | [Team에서 앱에 대한 관리 설정](admin-settings.md)을 참조하세요.|
|어떠한 그룹이 이 앱 그룹화를 적용받을 것인지를 어떻게 결정하나요?|[Teams 앱 사용 권한 및 고려 사항](app-permissions.md)을 참조하세요.|

### <a name="archiving-and-compliance"></a>보관 및 규정 준수

Your organization might require that you implement controls on how teams are archived and the types of data that are held in certain types of teams. Read [Overview of security and compliance in Teams](security-compliance-overview.md) to learn which Teams settings are turned on by default.

| 본인에게 질의하기 | 작업 |
|--------------|--------|
|팀 보존을 구성해야 하나요?|보존 정책을 설정하려면 [Teams 보존 정책 설정](retention-policies.md)을 참조하세요.|
|팀 보관을 구성해야 하나요?|팀을 보관하거나 복원하려면 [팀의 보관 또는 복원](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7)을 참조하세요.|
|추가적 규정 준수 설정을 구성해야 하나요?|보안 및 규정 준수에 대한 자세한 내용은 [Teams에서의 보안 및 규정 준수 개요](security-compliance-overview.md)를 참조하세요.|

### <a name="conditional-access"></a>조건부 액세스

Teams relies heavily on Exchange and SharePoint for core productivity scenarios, including meetings, calendars, interop chats, and file sharing. Conditional access policies that are set for these cloud apps apply to Teams when a user signs in directly to Teams, on any client. Conditional access policies that are set for the Teams cloud app control aspects such as whether users can access Teams services from certain networks.

| 본인에게 질의하기 | 작업 |
|--------------|--------|
|<br>Teams에 대한 조건부 액세스를 구성해야 하나요?|<ul><li>액세스 정책의 작동 방식을 이해하려면 [조건부 액세스 정책이 Teams에서 어떻게 작동하나요?](security-compliance-overview.md#how-conditional-access-policies-work-for-teams)를 참조하세요.</li><li>Teams에 대한 다단계 인증(MFA)을 설정하려면 다음을 참조하세요:<ul><li>[빠른 시작: Azure Active Directory 조건부 액세스를 사용하는 특정 앱에 MFA 요구](/azure/active-directory/conditional-access/app-based-mfa)</li><li>[Azure Active Directory 조건부 액세스 설정 참조](/azure/active-directory/conditional-access/technical-reference)</li></ul></ul>|

### <a name="education-edu"></a>교육(EDU)

교육 분야에 종사하는 IT 전문가는 학생, 교직원 및 다양한 비즈니스 관련 교육 별 시나리오를 충족시키기 위해 맞춤화된 다양한 기능을 제공하는 교육용 Teams를 활용할 수 있습니다.

| 본인에게 질의하기 | 작업 |
|--------------|--------|
|EDU 별 Teams 템플릿을 사용해야 되나요? |교육용 Teams에 대한 자세한 내용은 [관리자용 Microsoft 교육 거버넌스 FAQ를 참조하세요](plan-teams-governance-edu.md).|
|범위 검색을 배포해야 하나요?|EDU용 Teams를 설정하려면 [퀵 스타트 - 교육 관리자용 Teams](teams-quick-start-edu.yml)를 참조하세요.|
|Teams를 School Data Sync 서비스와 통합하여 사용자 계정을 제공하나요?|[교육 관리자용 Teams 리소스](resources-teams-edu.md)|

### <a name="government---gcc-considerations"></a>정부 - GCC 고려사항

정부 기관용 Office 365의 사용 - GCC(정부 커뮤니티 클라우드)는 정부의 규정 및 요건을 적용 받는 미국 연방, 주, 지역적,부족적 혹은 영토적 정부 기관 혹은 기타 기관에서 Office 365의 배포를 진행하는 IT 전문가의 요구 사항을 충족하는 데 적합합니다.

| 본인에게 질의하기 | 작업 |
|--------------|--------|
| 정부 기관용 Office 365 - GCC 환경에서 Teams를 배포해야 하나요? | 배포 관련 고려 사항은 [Office 365 정부 - GCC 배포 계획](plan-for-government-gcc.md)을 참조하세요.|

## <a name="next-steps"></a>다음 단계

- 채팅, 팀, 채널 & 앱의 [도입을 진행합니다](adopt-microsoft-teams-landing-page.md).
- 초기 Teams 롤아웃을 진행 시 Planner와 같은 추천 앱을 포함합니다. Teams 채택을 추진할 때 다른 Teams [앱을](deploy-apps-microsoft-teams-landing-page.md) 추가합니다.
- [모임 및 회의 출시](deploy-meetings-microsoft-teams-landing-page.md)
- [클라우드 음성 출시](cloud-voice-landing-page.md)
