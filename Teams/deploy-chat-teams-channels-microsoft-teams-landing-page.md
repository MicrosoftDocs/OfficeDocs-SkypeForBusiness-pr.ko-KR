---
title: Microsoft Teams에서의 채팅, 팀, 채널 & 앱
ms.reviewer: ''
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: 조직의 프로필 및 비즈니스 요구 사항에 따라 Microsoft Teams에서 채팅, 팀, 채널 및 앱을 롤아웃하기 위한 단계별 지침.
localization_priority: Priority
ms.collection:
- M365-collaboration
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.dashboard.helparticle.quickstartteamsadmin
appliesto:
- Microsoft Teams
- seo-marvel-apr2020
ms.openlocfilehash: 3b1546c71cc2796ce599da449ab37bf275384efc
ms.sourcegitcommit: 3323c86f31c5ab304944a34892601fcc7b448025
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/09/2020
ms.locfileid: "44637897"
---
# <a name="chat-teams-channels--apps-in-microsoft-teams"></a>Microsoft Teams에서의 채팅, 팀, 채널 & 앱

Teams는 조직을 위해 즉시 사용 가능한 뛰어난 공동 작업 환경을 제공하고 대부분의 조직에 그 기본 설정이 적합합니다. 이 문서에서는 조직의 프로필 및 비즈니스 요구 사항에 따라 기본 설정을 변경할지 여부를 결정 하는데 도움을 주고 각 변경 내용에 대해 설명을 합니다. 당사는 사용자가 [변경할 가능성이 큰](#core-deployment-decisions) 변경 내용의 핵심 집합에서 시작하여 설정을 두 그룹으로 나누었습니다. 두 번째 그룹은 조직의 요구 사항에 따라 구성하고자 하는 [추가 설정](#additional-deployment-decisions)을 포함합니다. 

시작하려면 당사의 짧은 Teams 채팅, 팀 그리고 채널 비디오(4:30분)를 시청하세요. 

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE476Yj]

*2019년 11월의 새로운 기능*
 - 사용자는 이제 [Advisor for Teams(미리 보기)를 사용하여 Microsoft Teams 배포에 도움을 받을 수 있습니다](use-advisor-teams-roll-out.md). Advisor for Teams(미리 보기)는 Teams의 배포 과정을 안내합니다. Advisor for Teams(미리 보기)는 Office 365 환경을 평가하고 Teams를 성공적으로 배포하기 전에 업데이트 또는 수정해야 할 수 있는 가장 일반적인 구성을 식별합니다.
 - Teams를 배포, 구성, 관리하는 방법을 보여주는 짧은(8-10분) 비디오를 포함한 [IT YouTube 채널용 Microsoft Teams 중요 기능](https://aka.ms/MicrosoftTeamsforIT)

> [!TIP]
> 초기 Teams 롤아웃을 진행 시 Planner와 같은 추천 앱을 포함하는 것이 좋습니다. Teams의 채택을 진행하면서 다른 [앱, 봇 및 커넥터](deploy-apps-microsoft-teams-landing-page.md)를 추가합니다.

## <a name="chat-deployment-prerequisites"></a>채팅 배포 전제 조건

조직에서 Teams를 배포하기 전에 환경이 이를 수용할 준비가 되었는지 확인할 시간을 갖습니다. [Teams를 위한 조직의 네트워크 준비](prepare-network.md)를 검토하고 환경을 필요한 대로 변경합니다.

|본인에게 질의하기|작업 |
|------------|-------|
|조직에서 Teams를 배포할 준비가 되었는가?|이 질문에 답변하려면 다음의 사항을 참조하세요: <ul><li>[Teams에 대한 조직의 네트워크 준비](prepare-network.md)</li><li>[Office 365 URL 및 IP 주소 범위](office-365-urls-ip-address-ranges.md)</li><li>[팀을 만들 때 Microsoft 365 그룹에 대한 계획](plan-office-365-groups.md)</li></ul>|
|||

## <a name="core-deployment-decisions"></a>핵심 배포 결정사항

이들은 대부분의 조직이 변경하려는 채팅, 팀 그리고 채널의 설정입니다(기본 설정이 조직에 적합하지 않은 경우).

### <a name="teams-administrators"></a>Teams 관리자

Teams는 조직의 팀을 관리하는데 사용할 수 있는 사용자 지정 관리자 역할의 집합을 제공합니다. 역할은 관리자에게 다양한 기능을 제공합니다.

| 본인에게 질의하기 | 작업 |
|--------------|--------|
|Teams 커뮤니케이션 관리자 역할은 누구에게 할당될 것인가요?|Teams 관리자 역할에 대한 자세한 내용은 [팀을 관리하기 위한 Microsoft Teams 관리 역할의 활용](using-admin-roles.md)을 참조하세요.|
|Teams 커뮤니케이션 지원 기술자 역할은 누구에게 할당될 것인가요?|관리 역할을 할당하려면 [Azure Active Directory를 사용하여 사용자에게 관리자 및 비관리자 역할 할당](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal)을 참조하세요.|
|Teams 커뮤니케이션 지원 전문가자 역할은 누구에게 할당될 것인가요?||
|||

### <a name="teams-owners-and-members"></a>Teams 소유자 및 구성원

관리자 역할 이외에 팀에서 Teams는 소유자와 구성원 사용자 역할을 할당하고(조정 기능이 설정된 경우) 선택적으로 조정자 기능을 제공하여 채널 내에서 특정 작업을 수행할 수 있는 사용자를 조정할 수 있도록 해줍니다. 조정 기능을 통해 사용자는 채널에서 새 게시물을 시작할 수 있는 사용자를 통제하고 조정자로서 구성원을 추가 및 제거하며 팀 구성원이 기존의 채널 메시지에 회신할 수 있는지를 제어할 수 있습니다.

|본인에게 질의하기|작업 |
|------------|-------|
|각 역할에는 누가 할당되어야 하나요? | 각 역할의 기능을 비교하려면 [Microsoft Teams에서 팀 소유자, 조정자 및 구성원 할당하기](assign-roles-permissions.md)를 참조하세요.
|사용자 역할은 어떻게 할당하나요? | 역할을 할당하거나 변경하려면 [사용자 역할 할당](assign-roles-permissions.md#assign-a-user-role)을 참조하세요.
|채널에서 게시나 회신을 할 수 있는 사용자를 통제해야 하나요? | 조정 기능을 구성하려면 [Microsoft Teams에서 채널 조정 설정 및 관리](manage-channel-moderation-in-teams.md)를 참조하세요.

### <a name="messaging-policies"></a>메시징 정책

메시징 정책은 Teams에서 사용자에게 제공되는 채팅 및 채널 메시징 기능을 제어합니다. 예를 들어 보낸 메시지를 편집하고 삭제할 수 있는 사용자, 채팅을 사용할 수 있는 사용자, 대화에서 밈를 사용할 수 있는 사용자 등이 있습니다. 기본적으로 사용자에게는 전역 메시징 정책이 할당되고 모든 기능은 **켜짐**으로 되어있습니다. 조직의 사용자에게 기본 전역 정책을 사용하거나 하나 혹은 이상의 사용자 지정 메시징 정책을 만들 수 있습니다. 

|본인에게 질의하기|작업 |
|------------|-------|
|전역 메시징 정책을 사용자 지정해야 하나요?|Microsoft Teams 관리 센터를 사용하여 전역 메시징 정책을 변경하거나 새 정책을 추가하는 방법에 대한 자세한 내용은 [Teams에서 메시징 정책 관리](messaging-policies-in-teams.md)를 참조하세요.|
|여러개의 메시징 정책이 필요한가요?|PowerShell에서 메시징 정책을 만들고 할당하려면 [PowerShell 스크립트 샘플 - 메시징 정책 만들기 및 할당](scripts/powershell-script-teams-messaging-policy-edu.md)을 참조하세요.|
|어떠한 사용자 그룹에 어떠한 메시징 정책을 할당할지를 어떻게 결정하나요?|CsTeamsMessagingPolicy cmdlet에 대한 내용은 [설정-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)를 참조하세요.|
||| 

### <a name="external-access"></a>외부 액세스

외부 액세스 (이전에는 페더레이션으로 알려짐)를 사용하면 Teams와 비즈니스용 Skype 사용자가 조직 외부의 사용자와 통신할 수 있습니다. 이 기능을 켜고 허용 목록에 도메인을 추가하면 사용자가 다른 도메인 및 조직의 사용자와 통신할 수 있습니다.외부 액세스는 개인이 아니라 전체 도메인에 대 한 액세스 권한이 부여된다는 점에서 게스트 액세스와는 다릅니다. 외부 액세스 기능은 기본적으로 꺼져있습니다.

|본인에게 질의하기|작업 |
|------------|-------|
|<ul><li>나의 조직의 외부 액세스 기능을 켜야 하나요?</li><li>이 기능을 사용하는 경우 나의 조직에서 통신할 수 있는 도메인을 제한하게 되나요?</li></ul> |<br>외부 액세스 기능을 켜려면 [외부 액세스 계획](manage-external-access.md#plan-for-external-access)을 참조하세요.|
|||

### <a name="guest-access"></a>게스트 액세스

Teams에서 게스트 액세스를 사용하여 조직 외부의 개인 사용자는 팀과 채널에 액세스할 수 있습니다. 게스트 액세스 설정을 사용하여 게스트 사용자가 사용할 수 있거나 사용할 수 없는 기능을 제어할 수 있습니다. 게스트 액세스 기능은 기본적으로 꺼져있습니다. 자세한 내용은 [Teams에서의 게스트 액세스](https://docs.microsoft.com/microsoftteams/guest-access)를 참조하세요.

> [!NOTE]
> 외부 액세스 및 게스트 액세스에 대한 자세한 내용은 [Microsoft Teams의 다른 조직의 사용자와 통신](communicate-with-users-from-other-organizations.md)을 참조하세요


|본인에게 질의하기|작업 |
|------------|-------|
|나의 조직의 Teams 액세스 기능을 켜야 하나요?|게스트 액세스를 켜려면 [Teams에서 게스트 액세스 설정 또는 해제](set-up-guests.md)를 참조하세요.|
|이 기능을 사용하는 경우 조직의 게스트가 사용할 수 있는 기능을 사용자 지정할 수 있나요?|게스트 액세스 기능의 가용성을 사용자 지정 하려면 [Teams에서 게스트 액세스 권한 부여](teams-dependencies.md)를 참조하세요.|
|||

### <a name="teams-settings"></a>Teams 설정

Teams 설정을 사용하여 팀에 전자 메일의 통합, 클라우드 저장소 옵션, 조직 탭, 회의실 장치 설정 및 검색 범위와 같은 기능을 설정할 수 있습니다. 이러한 설정을 변경하면 변경 사항은 조직의 모든 팀에 적용됩니다.자세히 알아보려면 [Teams 설정](enable-features-office-365.md#teams-settings)을 참조하세요.

|본인에게 질의하기|작업 |
|------------|-------|
|나의 조직의 Teams 설정을 사용자 지정할 수 있나요? | Teams 설정 및 사용자 지정 방법에 대한 내용은 [Teams 설정](enable-features-office-365.md#teams-settings)을 참조하세요.|
|||

### <a name="teams-clients"></a>Teams 클라이언트

Teams는 웹에서 데스크톱 그리고 모바일까지 여러 클라이언트를 지원하고, 그 기본 구성은 사용자가 원하는 클라이언트를 선택할 수 있도록 해줍니다.자세한 내용은 [Teams용 클라이언트 가져오기](get-clients.md)를 참조하세요.

|본인에게 질의하기|작업 |
|------------|-------|
|나의 조직의 Teams 클라이언트 가용성을 사용자 지정할 수 있나요?|[Teams 앱의 하드웨어 요구 사항](hardware-requirements-for-the-teams-app.md)을 참조합니다. |
|나의 조직의 Teams 클라이언트 설정을 사용자 지정할 수 있나요?|[MSI를 사용하여 Teams를 설치](msi-deployment.md)하는 방법을 학습하세요.|
|||


### <a name="teams-usage-reporting"></a>Teams 사용 현황 보고

Office 365의 전역 관리자, Teams 서비스 관리 그리고 보고서 리더 역할은 팀 사용 현황 보고서를 볼 수 있습니다. 자세한 내용은 [Microsoft 365 사용 현황 분석 문서](https://docs.microsoft.com/office365/admin/usage-analytics/usage-analytics?redirectSourcePath=%252farticle%252fMicrosoft-365-usage-analytics-77ff780d-ab19-4553-adea-09cb65ad0f1f&view=o365-worldwide)를 참조하세요.

|본인에게 질의하기|작업 |
|------------|-------|
|<br> 팀 사용 현황 보고서를 확인해야 하는 사용자는 누구이고 그들은 보고서를 볼 수 있는 올바른 역할을 보유하고 있나요? |<ul><li>사용자가 관리자가 아닌 경우에는 [보고서 리더 역할을 할당합니다](teams-activity-reports.md#reports-reader-role).</li><li>[역할 및 사용 권한](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)과 [역할 보기 및 지정](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-manage-roles-portal)을 참조하여 Azure Active Directory에서 관리 역할을 할당하는 방법을 알아보세요. |
|||

### <a name="teams-default-apps"></a>Teams 기본 앱 

Teams는 사용자를 참여시키고 생산성을 지원 하고 자주 사용하는 비즈니스 서비스를 Teams로 통합하기 위한 여러 자사(Microsoft 제공) 및 타사의 앱을 제공합니다. Teams 스토어에서 앱을 다운로드합니다. Teams에서 앱은 기본적으로 켜집니다. 

Teams에서의 앱의 배포 및 관리에 대한 자세한 내용은 당사의 심층적인 [앱, 봇 그리고 커넥터](deploy-apps-microsoft-teams-landing-page.md) 지침을 참조하세요.


## <a name="additional-deployment-decisions"></a>추가 배포 결정사항

조직의 요구 사항 및 구성에 따라 이러한 설정을 변경하는 것이 좋습니다.

### <a name="teams-licensing"></a>Teams 라이선싱

Teams는 많은 Office 365 라이선스의 일부로 제공됩니다. Teams 라이선싱에 대한 자세한 내용은 [Microsoft Teams 서비스 설명](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)을 참조하세요.

|본인에게 질의하기|작업 |
|------------|-------|
|사용자는 배포하려는 모든 Teams의 기능을 사용하기 위해 필요한 라이선스가 있나요? | 라이선싱 요구 사항에 대한 자세한 내용은 [Microsoft Teams 서비스 설명](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)을 읽어 보세요.|
|||

### <a name="exchange-and-sharepoint-interoperability"></a>Exchange 및 SharePoint 상호 운용성 

완전한 Teams 환경이 되려면 모든 사용자가 Exchange Online, SharePoint Online 및 Microsoft 365 그룹 만들기가 가능하도록 설정해야 합니다. 다음의 문서는 다양한 환경에서 호스팅되는 Exchange 메일함과 관련된 정보, Exchange와 Teams가 상호 작용하는 방법 그리고 SharePoint 및 비즈니스용 OneDrive에 대한 이와 유사한 고려 사항에 관련된 정보를 간략하게 설명합니다. 

|본인에게 질의하기|작업 |
|------------|-------|
| 현재의 Exchange 및 SharePoint 배포에 필요한 Teams의 기능을 배포할 수 있나요? |Teams에서의 Exchange 및 SharePoint에 대한 자세한 내용은 다음을 참조하세요:<ul><li> [Exchange와 Teams의 상호 작용 방법](exchange-teams-interact.md)</li><li>[SharePoint Online 및 비즈니스용 OneDrive가 Teams와 상호 작용하는 방법](sharepoint-onedrive-interact.md)|
|||

### <a name="teams-limits-and-specifications"></a>Teams의 제한과 사양 

Teams의 엔터프라이즈 배포를 계획할 때 팀의 최대 구성원 수, 사용자가 만들 수 있는 최대 팀 수 등과 같은 관련 제한 사항과 사양을 고려해 야 합니다.

|본인에게 질의하기|작업 |
|------------|-------|
| Teams의 배포 시 나는 어떠한 제한에 걸리기 쉽나요? | 자세한 내용은 [Teams의 제한과 사양](limits-specifications-teams.md)를 참조하세요. |
|||

### <a name="office-365-urls-and-ports"></a>Office 365 URL 및 포트

인터넷 트래픽의 세분화된 컨트롤을 유지하는 조직은 Teams에 맞게 올바르게 구성해야 하는 URL, IP 주소, 포트 및 프로토콜의 최신 목록을 위해 [Office 365 URL 및 IP 주소 범위](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges)를 참조합니다. Microsoft는 계속해서 Office 365 서비스를 개선 하고 새 기능을 추가하고 있으며 이는 필수 포트, URL, IP 주소가 시간이 지나면서 변경됨을 의미합니다. 이러한 정보가 업데이트되거나 변경될 시 알림을 받도록 RSS를 통해 구독을 할 것을 권장합니다. 적어도 위의 [채팅 배포 전제 조건](#chat-deployment-prerequisites)에 나열된 포트를 열었는지를 확인합니다.

|본인에게 질의하기|작업 |
|------------|-------|
| 사용자가 Teams를 사용할 수 있도록 하려면 인터넷 액세스 규칙이 필요한가요 혹은 필요한 최소 포트를 여는 것으로 충분하나요? | 자세한 내용은 [Office 365 URL 및 IP 주소 범위](office-365-urls-ip-address-ranges.md)를 참조하세요.|
|||


### <a name="governance-naming-conventions-who-can-create-teams"></a>거버넌스 (팀을 만들 수 있는 사용자 명명 규칙)

조직에서는 사용자가 팀을 명명하고 분류하는 방법, 팀, 팀의 만료, 보존 및 보관에 대한 제어를 수행하도록 요구할 수도 있습니다. 이를 거버넌스라고 합니다. Azure Active Directory(Azure AD)를 사용하여 이러한 각 영역을 구성할 수 있습니다.


| 본인에게 질의하기 | 작업 |
|--------------|--------|
|팀을 만들 수 있는 사용자에 대한 제어를 수행해야 하나요?| [Teams에서의 거버넌스 계획](plan-teams-governance.md)을 참조하세요.|
|Teams의 명명 규칙 방식에 대한 제어를 수행해야 하나요?|[Azure AD에서 Microsoft 365 그룹에 대한 명명 정책 적용](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-naming-policy)을 참조하세요.|
|||

### <a name="teams-application-policy-side-rail-control"></a>Teams 응용 프로그램 정책(측면 레일 제어)

고정된 앱은 Teams의 측면 레일에 표시됩니다. Teams 응용 프로그램 정책을 만들면 선택된 사용자 그룹에 대해 Teams를 사용자 지정하기 위해 고정된 Teams 앱의 집합을 미리 구성할 수 있습니다. 기본적으로 **Microsoft Teams에서 외부 앱 허용** 설정은 켜져있습니다.

| 본인에게 질의하기 | 작업 |
|--------------|--------|
|미리 구성된 고정된 Teams 응용 프로그램의 집합을 만들어야 하나요? | [Team에서 앱에 대한 관리 설정](admin-settings.md)을 참조하세요.|
|어떠한 그룹이 이 앱 그룹화를 적용받을 것인지를 어떻게 결정하나요?|[Teams 앱 사용 권한 및 고려 사항](app-permissions.md)을 참조하세요.|
|||

### <a name="archiving-and-compliance"></a>보관 및 규정 준수 

조직에서 사용자에게 팀을 보관하는 방법과 특정 유형의 팀에 보유되는 데이터 유형에 대한 제어를 수행하도록 요구할 수도 있습니다. [Teams에서의 보안 및 규정 준수 개요](security-compliance-overview.md)를 참조하여 기본적으로 켜지는 설정에 대해 알아보세요.

| 본인에게 질의하기 | 작업 |
|--------------|--------|
|팀 보존을 구성해야 하나요?|보존 정책을 설정하려면 [Teams 보존 정책 설정](retention-policies.md)을 참조하세요.|
|팀 보관을 구성해야 하나요?|팀을 보관하거나 복원하려면 [팀의 보관 또는 복원](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7)을 참조하세요.|
|추가적 규정 준수 설정을 구성해야 하나요?|보안 및 규정 준수에 대한 자세한 내용은 [Teams에서의 보안 및 규정 준수 개요](security-compliance-overview.md)를 참조하세요.|
|||

### <a name="conditional-access"></a>조건부 액세스 

Teams는 모임, 일정, 인터롭 차트 그리고 파일 공유를 포함하는 핵심 생산성 시나리오를 위해 Exchange Online 및 SharePoint Online 그리고 비즈니스용 Skype에 크게 의존합니다. 이러한 클라우드 앱에 설정된 조건부 액세스 정책은 사용자가 모든 클라이언트에서 직접 Teams로 로그인할 때 Teams에 적용됩니다. Teams 클라우드 앱에 설정된 조건부 액세스 정책은 사용자가 특정 네트워크에서 Teams 서비스에 액세스할 수 있는지와 같은 다양한 기능을 제어합니다.

| 본인에게 질의하기 | 작업 |
|--------------|--------|
|<br>Teams에 대한 조건부 액세스를 구성해야 하나요?|<ul><li>액세스 정책의 작동 방식을 이해하려면 [조건부 액세스 정책이 Teams에서 어떻게 작동하나요?](security-compliance-overview.md#how-conditional-access-policies-work-for-teams)를 참조하세요.</li><li>Teams에 대한 다단계 인증(MFA)을 설정하려면 다음을 참조하세요:<ul><li>[빠른 시작: Azure Active Directory 조건부 액세스를 사용하는 특정 앱에 MFA 요구](https://docs.microsoft.com/azure/active-directory/conditional-access/app-based-mfa)</li><li>[Azure Active Directory 조건부 액세스 설정 참조](https://docs.microsoft.com/azure/active-directory/conditional-access/technical-reference)</li></ul></ul>|
|||


### <a name="education-edu"></a>교육(EDU) 

교육 분야에 종사하는 IT 전문가는 학생, 교직원 및 다양한 비즈니스 관련 교육 별 시나리오를 충족시키기 위해 맞춤화된 다양한 기능을 제공하는 교육용 Teams를 활용할 수 있습니다.

| 본인에게 질의하기 | 작업 |
|--------------|--------|
|EDU 별 Teams 템플릿을 사용해야 되나요? |교육용 Teams에 대한 자세한 내용은 [관리자용 Microsoft 교육 거버넌스 FAQ를 참조하세요](plan-teams-governance-edu.md).|
|범위 검색을 배포해야 하나요?|EDU용 Teams를 설정하려면 [퀵 스타트 - 교육 관리자용 Teams](teams-quick-start-edu.yml)를 참조하세요.|
|Teams를 School Data Sync 서비스와 통합하여 사용자 계정을 제공하나요?|[교육 관리자용 Teams 리소스](resources-teams-edu.md)|
|||

### <a name="government---gcc-considerations"></a>정부 - GCC 고려사항

정부용 Microsoft 365의 사용 - GCC(정부 커뮤니티 클라우드)는 정부의 규정 및 요건을 적용 받는 미국 연방, 주, 지역적,부족적 혹은 영토적 정부 기관 혹은 기타 기관에서 Office 365의 배포를 진행하는 IT 전문가의 요구 사항을 충족하는 데 적합합니다.

| 본인에게 질의하기 | 작업 |
|--------------|--------|
| Microsoft 365 정부 - GCC 환경에서 Teams를 배포해야 하나요? | 배포 관련 고려 사항은 [Microsoft 365 정부 - GCC 배포](plan-for-government-gcc.md) 계획을 참조하세요.|
|||

## <a name="next-steps"></a>다음 단계
- 채팅, 팀, 채널 & 앱의 [도입을 진행합니다](adopt-microsoft-teams-landing-page.md).
- 초기 Teams 롤아웃을 진행 시 Planner와 같은 추천 앱을 포함합니다. Teams의 채택을 진행하면서 다른 [앱, 봇 & 커넥터](deploy-apps-microsoft-teams-landing-page.md)를 추가합니다.
- [모임 및 회의 출시](deploy-meetings-microsoft-teams-landing-page.md)
- [클라우드 음성 출시](cloud-voice-landing-page.md)

