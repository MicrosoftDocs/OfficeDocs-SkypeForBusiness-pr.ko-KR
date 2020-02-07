---
title: 조직에서 Microsoft Teams 설정 관리
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: ritikag
search.appverid: MET150
description: 앱, 외부 액세스, 게스트 액세스, Teams 설정, Teams 업그레이드 기본 설정을 포함하여 조직의 Microsoft Teams 조직 전체 설정을 켜거나 끄는 방법을 알아봅니다.
localization_priority: Priority
ms.custom:
- ms.teamsadmincenter.orgwidesettings.teamssettings.targetingintro
- ms.teamsadmincenter.teamssettings.overview
ms.collection:
- M365-collaboration
f1.keywords:
- CSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5eb6fa4a4b8aabcc84f70d6ce33c89fe0d84df98
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41834958"
---
# <a name="manage-microsoft-teams-settings-for-your-organization"></a><span data-ttu-id="c43d1-103">조직에서 Microsoft Teams 설정 관리</span><span class="sxs-lookup"><span data-stu-id="c43d1-103">Manage Microsoft Teams settings for your organization</span></span>

## <a name="teams-apps-settings-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="c43d1-104">Microsoft Teams 관리 센터의 Teams 앱 설정</span><span class="sxs-lookup"><span data-stu-id="c43d1-104">Teams apps settings in the Microsoft Teams admin center</span></span>

<span data-ttu-id="c43d1-105">[Microsoft Teams 관리 센터](https://admin.teams.microsoft.com)의 **Teams 앱**에서 조직의 앱을 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="c43d1-105">You manage apps for your organization in **Teams apps** in the [Microsoft Teams admin center](https://admin.teams.microsoft.com).</span></span> <span data-ttu-id="c43d1-106">예를 들어, 조직 전체 또는 특정 Teams 사용자에게 사용할 수 있는 앱을 제어하는 정책을 설정하고, 사용자에게 가장 중요한 앱을 고정하여 Teams를 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c43d1-106">For example, you can set policies to control what apps are available org-wide or to specific Teams users and you can customize Teams by pinning the apps that are most important for your users.</span></span>

<span data-ttu-id="c43d1-107">자세한 내용은 [Team에서 앱에 대한 관리 설정](admin-settings.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c43d1-107">To learn more, see [Admin settings for apps in  Teams](admin-settings.md).</span></span>  

## <a name="teams-org-wide-settings-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="c43d1-108">Microsoft Teams 관리 센터의 Teams 조직 전체 설정</span><span class="sxs-lookup"><span data-stu-id="c43d1-108">Teams org-wide settings in the Microsoft Teams admin center</span></span>

<span data-ttu-id="c43d1-109">Microsoft Teams 관리 센터에서 조직 전체 사용자 설정을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c43d1-109">You can control organization-wide user settings in the Microsoft Teams admin center.</span></span> <span data-ttu-id="c43d1-110">조직 전체 설정을 편집하려면 Microsoft Teams 관리 센터로 이동한 후 **조직 전체 설정**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c43d1-110">To edit org-wide settings, go to the Microsoft Teams admin center, and then select **Org-wide settings**.</span></span> <span data-ttu-id="c43d1-111">다음과 같은 설정을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c43d1-111">You can configure the following settings.</span></span>

### <a name="external-access"></a><span data-ttu-id="c43d1-112">외부 액세스</span><span class="sxs-lookup"><span data-stu-id="c43d1-112">External access</span></span>

<span data-ttu-id="c43d1-113">**외부 액세스**를 사용하면 Teams와 비즈니스용 Skype 사용자가 조직 또는 도메인 외부의 사용자와 통신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c43d1-113">**External access** lets your Teams and Skype for Business users communicate with users who are outside of your organization or domain.</span></span> <span data-ttu-id="c43d1-114">외부 액세스를 구성하려면 [Teams 사용자가 다른 Teams 조직의 사용자와 채팅하고 커뮤니케이션하도록 허용](let-your-teams-users-communicate-with-other-people.md)으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="c43d1-114">To configure external access, go to [Let your Teams users chat and communicate with users in another Teams organization](let-your-teams-users-communicate-with-other-people.md).</span></span>

<span data-ttu-id="c43d1-115">도메인을 추가하거나 차단하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="c43d1-115">To add or block a domain:</span></span>

1. <span data-ttu-id="c43d1-116">**도메인 추가**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c43d1-116">Select **Add a domain**.</span></span>
2. <span data-ttu-id="c43d1-117">도메인 추가 창에서 도메인 이름을 입력하고 스페이스바를 클릭하여 이름을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="c43d1-117">In the Add a domain pane, enter the domain name, and click the space bar to save the name.</span></span>
3. <span data-ttu-id="c43d1-118">**허용됨** 또는 **차단됨**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c43d1-118">Select **Allowed** or **Blocked**.</span></span>
4. <span data-ttu-id="c43d1-119">**완료**를 선택하여 변경 내용을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="c43d1-119">Select **Done** to save your changes.</span></span> 

### <a name="guest-access"></a><span data-ttu-id="c43d1-120">게스트 액세스</span><span class="sxs-lookup"><span data-stu-id="c43d1-120">Guest access</span></span>

<span data-ttu-id="c43d1-121">Microsoft Teams의 **게스트 액세스**를 사용하면 조직의 팀에서 팀과 채널에 대한 액세스 권한을 부여하여 조직 외부의 사용자와 공동 작업을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c43d1-121">**Guest access** in Microsoft Teams allows teams in your organization to collaborate with people outside your organization by granting them access to teams and channels.</span></span> <span data-ttu-id="c43d1-122">비즈니스 또는 소비자 전자 메일 계정(Outlook, Gmail 등)이 있는 사용자는 팀 채팅, 모임 및 파일에 대한 모든 액세스 권한을 부여받아 Teams에서 게스트로 참여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c43d1-122">Anyone with a business or consumer email account, such as Outlook, Gmail, or others, can participate as a guest in Teams with full access to team chats, meetings, and files.</span></span> <span data-ttu-id="c43d1-123">자세한 내용은 [Microsoft Team의 게스트 액세스](guest-access.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c43d1-123">For more information, see [Guest access in Microsoft Teams](guest-access.md).</span></span>

### <a name="teams-settings"></a><span data-ttu-id="c43d1-124">Teams 설정</span><span class="sxs-lookup"><span data-stu-id="c43d1-124">Teams settings</span></span>

<span data-ttu-id="c43d1-125">**Teams 설정**에서 알림과 피드, 전자 메일 통합, 클라우드 저장소 옵션 및 디바이스를 포함하는 Teams의 기능을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c43d1-125">In **Teams settings**, you can set up features for teams including notifications and feeds, email integration, cloud storage options, and devices.</span></span>

#### <a name="notifications-and-feeds"></a><span data-ttu-id="c43d1-126">알림 및 피드</span><span class="sxs-lookup"><span data-stu-id="c43d1-126">Notifications and feeds</span></span>

<span data-ttu-id="c43d1-127">Teams의 사용자 활동 피드에 제안된 피드를 표시할지 여부를 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c43d1-127">Here you can control whether suggested feeds appear in users' activity feed in Teams.</span></span> <span data-ttu-id="c43d1-128">활동 피드에 대한 자세한 내용은 [Teams에서 활동 피드 둘러보기](https://support.office.com/article/explore-the-activity-feed-in-teams-91c635a1-644a-4c60-9c98-233db3e13a56)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c43d1-128">To learn more about the activity feed, see [Explore the Activity feed in Teams](https://support.office.com/article/explore-the-activity-feed-in-teams-91c635a1-644a-4c60-9c98-233db3e13a56).</span></span>

#### <a name="email-integration"></a><span data-ttu-id="c43d1-129">전자 메일 통합</span><span class="sxs-lookup"><span data-stu-id="c43d1-129">Email integration</span></span>

<span data-ttu-id="c43d1-130">사용자가 채널 전자 메일 주소를 사용하여 Teams의 채널에 전자 메일을 보낼 수 있도록 하려면 이 기능을 켭니다.</span><span class="sxs-lookup"><span data-stu-id="c43d1-130">Turn on this feature so users can send email to a channel in Teams, using the channel email address.</span></span> <span data-ttu-id="c43d1-131">사용자는 자신이 소유한 팀에 속한 모든 채널에 대해 이 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c43d1-131">Users can do this for any channel belonging to a team they own.</span></span> <span data-ttu-id="c43d1-132">사용자는 Teams 구성원을 위해 커넥터 추가를 설정한 팀의 모든 채널로 전자 메일을 보낼 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c43d1-132">Users can also send emails to any channel in a team that has adding connectors turned on for team members.</span></span> <span data-ttu-id="c43d1-133">전자 메일 통합을 설정하려면 **사용자가 채널 전자 메일 주소에 전자 메일을 보낼 수 있도록 허용**이 **켬**인지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="c43d1-133">To turn on email integration, make sure that **Allow users to send emails to a channel email address** is **On**.</span></span>

#### <a name="files"></a><span data-ttu-id="c43d1-134">파일</span><span class="sxs-lookup"><span data-stu-id="c43d1-134">Files</span></span>

<span data-ttu-id="c43d1-135">여기서 파일 공유 및 클라우드 파일 저장소 옵션을 켜거나 끌 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c43d1-135">Here you can turn on or turn off file sharing and cloud file storage options.</span></span>

<span data-ttu-id="c43d1-136">사용자는 Teams 채널과 채팅의 클라우드 저장소 서비스에서 파일을 업로드하고 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c43d1-136">Users can upload and share files from cloud storage services in Teams channels and chats.</span></span> <span data-ttu-id="c43d1-137">Teams의 클라우드 저장소 옵션에는 현재 ShareFile, Dropbox, Box, Google Drive가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="c43d1-137">Cloud storage options in Teams currently include ShareFile, Dropbox, Box, and Google Drive.</span></span> <span data-ttu-id="c43d1-138">조직에서 사용하려는 클라우드 저장소 공급자에 대한 스위치를 켭니다.</span><span class="sxs-lookup"><span data-stu-id="c43d1-138">Turn on the switch for the cloud storage providers that your organization wants to use.</span></span>

#### <a name="organization"></a><span data-ttu-id="c43d1-139">조직</span><span class="sxs-lookup"><span data-stu-id="c43d1-139">Organization</span></span>

<span data-ttu-id="c43d1-140">여기에서 사용자 조직에 대한 세부 조직 차트를 보여 주는 **조직** 탭을 켤 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c43d1-140">Here you can turn on the **Organization** tab, which shows the detailed organizational chart for the user’s organization.</span></span> <span data-ttu-id="c43d1-141">자세한 내용은 [Teams에서 조직 탭 사용](https://support.office.com/article/use-the-organization-tab-in-teams-ff02568b-290a-46d6-ae7a-cda22f723894)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c43d1-141">For more information, see [Use the organization tab in Teams](https://support.office.com/article/use-the-organization-tab-in-teams-ff02568b-290a-46d6-ae7a-cda22f723894).</span></span>

#### <a name="devices"></a><span data-ttu-id="c43d1-142">디바이스</span><span class="sxs-lookup"><span data-stu-id="c43d1-142">Devices</span></span>

<span data-ttu-id="c43d1-143">이 설정은 Microsoft Teams 모임에 참석하는 Surface Hub 디바이스에 대한 리소스 계정 동작을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="c43d1-143">These settings control resource account behavior for Surface Hub devices attending Microsoft Teams meetings.</span></span> <span data-ttu-id="c43d1-144">이 설정을 사용하여 인증 요구 사항을 구성하고, 콘텐츠 PIN을 요구하고, 메시지를 보낼 Surface Hub 리소스 계정을 켭니다.</span><span class="sxs-lookup"><span data-stu-id="c43d1-144">Use these settings to configure authentication requirements, require a content PIN, and turn on Surface Hub resource accounts to send messages.</span></span>

- <span data-ttu-id="c43d1-145">**모임 콘텐츠에 액세스하기 위해 보조 인증 형식을 요구합니다.** - 콘텐츠 PIN을 입력할 때의 사용자의 액세스 수준을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c43d1-145">**Require a secondary form of authentication to access meeting content** – Select the level of access that users have when they enter the content PIN.</span></span>
- <span data-ttu-id="c43d1-146">**콘텐츠 PIN 설정** – 사용자는 문서에 대한 무단 액세스를 방지하기 위해 이 PIN을 입력해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c43d1-146">**Set content PIN** – Require users to enter this PIN to prevent unauthorized access to documents.</span></span> <span data-ttu-id="c43d1-147">이렇게 하면 권한이 없는 사용자는 예정된 모임에 참석하거나 첨부 파일을 검색할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c43d1-147">This prevents an unauthorized user from joining upcoming meetings and browsing attachments.</span></span>
- <span data-ttu-id="c43d1-148">**리소스 계정은 메시지를 보낼 수 있습니다.** - Surface Hub 리소스 계정에서 메시지를 보낼 수 있도록 하려면 이 설정을 **켬**으로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c43d1-148">**Resource accounts can send messages** – Turn this setting **On** to allow messages to be sent from the Surface Hub resource account.</span></span>

#### <a name="search-by-name"></a><span data-ttu-id="c43d1-149">이름으로 검색</span><span class="sxs-lookup"><span data-stu-id="c43d1-149">Search by name</span></span>

<span data-ttu-id="c43d1-150">Microsoft Teams 범위 디렉터리 검색은 Exchange APB(주소록 정책)를 사용하여 조직에서 사용자가 조직의 다른 사용자를 찾고 커뮤니케이션하는 방법을 제어하는 가상 경계를 만들 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="c43d1-150">Microsoft Teams scoped directory search uses Exchange address book policy (APB) to allow organizations to create virtual boundaries that control how users can find and communicate with other users in their organization.</span></span> <span data-ttu-id="c43d1-151">다음과 같은 경우 범위 디렉터리 검색을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="c43d1-151">You might want to use a scoped directory search in situations like these:</span></span>

- <span data-ttu-id="c43d1-152">조직의 테넌트 내에 별도로 유지하려는 여러 회사가 있는 경우</span><span class="sxs-lookup"><span data-stu-id="c43d1-152">Your organization has multiple companies within its tenant that you want to keep separate.</span></span> 
- <span data-ttu-id="c43d1-153">학교에서 교사와 학생 간의 채팅을 제한하려고 하는 경우</span><span class="sxs-lookup"><span data-stu-id="c43d1-153">Your school wants to limit chats between faculty and students.</span></span> 

<span data-ttu-id="c43d1-154">범위 디렉터리 검색을 설정하려면 이 설정을 **켬**으로 전환합니다.</span><span class="sxs-lookup"><span data-stu-id="c43d1-154">Switch this setting **On** to turn on scoped directory searches.</span></span>

### <a name="teams-upgrade"></a><span data-ttu-id="c43d1-155">Teams 업그레이드</span><span class="sxs-lookup"><span data-stu-id="c43d1-155">Teams upgrade</span></span>

<span data-ttu-id="c43d1-156">이러한 설정을 사용하여 비즈니스용 Skype에서 Microsoft Teams로 사용자를 업그레이드하는 방법을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c43d1-156">You can use these settings to configure how your users will be upgraded from Skype for Business to Microsoft Teams.</span></span> 

#### <a name="coexistence-mode"></a><span data-ttu-id="c43d1-157">공존 모드</span><span class="sxs-lookup"><span data-stu-id="c43d1-157">Coexistence mode</span></span>
<span data-ttu-id="c43d1-158">다음과 같은 공존 모드를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c43d1-158">You can specify a coexistence mode:</span></span> 

- <span data-ttu-id="c43d1-159">**Teams 전용**</span><span class="sxs-lookup"><span data-stu-id="c43d1-159">**Teams only**</span></span>
- <span data-ttu-id="c43d1-160">**Islands**(Teams와 비즈니스용 Skype의 공존)</span><span class="sxs-lookup"><span data-stu-id="c43d1-160">**Islands** (Teams and Skype for Business will coexist)</span></span>
- <span data-ttu-id="c43d1-161">**비즈니스용 Skype 전용**</span><span class="sxs-lookup"><span data-stu-id="c43d1-161">**Skype for Business only**</span></span>
- <span data-ttu-id="c43d1-162">**Teams 공동 작업이 포함된 비즈니스용 Skype**(사용자는 비즈니스용 Skype로 채팅 및 통화를 받고 모임을 예약하지만 그룹 공동 작업을 위해 Teams를 사용함)</span><span class="sxs-lookup"><span data-stu-id="c43d1-162">**Skype for Business with Teams collaboration** (Users receive chats and calls and schedule meetings in Skype for Business but use  Teams for group collaboration)</span></span>
- <span data-ttu-id="c43d1-163">**Teams 공동 작업 및 모임이 포함된 비즈니스용 Skype**(사용자는 비즈니스용 Skype로 채팅 및 통화를 받지만, 그룹 공동 작업 및 모임 예약을 위해 Teams를 사용함)</span><span class="sxs-lookup"><span data-stu-id="c43d1-163">**Skype for Business with Teams collaboration and meetings** (Users receive chats and calls in Skype for Business but use Teams for group collaboration and to schedule meetings)</span></span>

<span data-ttu-id="c43d1-164">선택하는 공존 모드는 수신 통화 및 채팅의 라우팅과 사용자가 채팅 및 통화를 시작하거나 모임을 예약하는 데 사용하는 앱을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="c43d1-164">The coexistence mode you choose determines the routing of incoming calls and chats and the app that is used by the user to initiate chats and calls or to schedule meetings.</span></span> <span data-ttu-id="c43d1-165">공존 모드에 대한 자세한 내용은 [Microsoft Teams와 비즈니스용 Skype의 공존 및 상호 운용성 이해](teams-and-skypeforbusiness-coexistence-and-interoperability.md)로 이동하세요.</span><span class="sxs-lookup"><span data-stu-id="c43d1-165">For more information about coexistence modes, go to [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md).</span></span>

#### <a name="app-preferences"></a><span data-ttu-id="c43d1-166">앱 기본 설정</span><span class="sxs-lookup"><span data-stu-id="c43d1-166">App preferences</span></span>

<span data-ttu-id="c43d1-167">여기에서 사용자가 비즈니스용 Skype 모임(비즈니스용 Skype 또는 [Skype 모임 앱](https://support.office.com/ko-KR/article/What-is-Skype-Meetings-App-Skype-for-Business-Web-App-1FF3D412-718A-4982-8FF2-A4992608CDB5))에 참가하기 위해 사용하는 앱을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c43d1-167">Here you can choose the app that users will use to join Skype for Business meetings (Skype for Business or the [Skype Meetings App](https://support.office.com/ko-KR/article/What-is-Skype-Meetings-App-Skype-for-Business-Web-App-1FF3D412-718A-4982-8FF2-A4992608CDB5)).</span></span> <span data-ttu-id="c43d1-168">이 설정은 공존 모드 설정에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="c43d1-168">This setting isn't dependent on the coexistence mode setting.</span></span>


#### <a name="network-planner"></a><span data-ttu-id="c43d1-169">Network Planner</span><span class="sxs-lookup"><span data-stu-id="c43d1-169">Network Planner</span></span>

<span data-ttu-id="c43d1-170">Network Planner를 통해 조직 전체에 팀 사용자를 연결하는데 필구한 네트워크 요건을 판단하고 구성하는데 도움을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c43d1-170">Network Planner helps you determine and organize network requirements for connecting Teams users across your organization.</span></span>  <span data-ttu-id="c43d1-171">[Microsoft Teams용 Network Planner 사용](https://docs.microsoft.com/microsoftteams/network-planner) 방법을 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="c43d1-171">Learn how to [Use the Network Planner for Microsoft Teams](https://docs.microsoft.com/microsoftteams/network-planner).</span></span>

<span data-ttu-id="c43d1-172">"비즈니스용 Skype 사용자를 위해 백그라운드에서 Teams 앱 다운로드" 옵션도 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c43d1-172">You can also select the “Download the Teams app in the background for Skype for Business users” option as well.</span></span>  <span data-ttu-id="c43d1-173">기본적으로, 이 설정은 켬으로 설정되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c43d1-173">By default this setting is set to On.</span></span> <span data-ttu-id="c43d1-174">이 설정을 사용하도록 설정하면 Windows PC에서 비즈니스용 Skype 앱을 실행하는 사용자를 위해 Teams 앱이 백그라운드로 다운로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="c43d1-174">With this setting enabled it will download the Teams app in the background for users running the Skype for Business app on Windows PCs.</span></span> <span data-ttu-id="c43d1-175">사용자에 대한 동시 사용 모드가 Teams 전용이거나 보류 중인 업그레이드 알림이 비즈니스용 Skype 앱에서 활성화된 경우 이와 같이 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="c43d1-175">This happens if the Coexistence mode for the user is Teams Only, or if a pending upgrade notification is enabled in the Skype for Business app.</span></span>


## <a name="how-can-i-tell-which-features-are-available"></a><span data-ttu-id="c43d1-176">어떤 기능을 사용할 수 있는지 어떻게 알 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="c43d1-176">How can I tell which features are available?</span></span>

<span data-ttu-id="c43d1-177">새 Teams 기능에 대한 내용은 [Microsoft 365 로드맵](https://www.microsoft.com/en-us/microsoft-365/roadmap?rtc=1&filters=Microsoft%20Teams)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c43d1-177">See the [Microsoft 365 Roadmap](https://www.microsoft.com/en-us/microsoft-365/roadmap?rtc=1&filters=Microsoft%20Teams) for information about new Teams features.</span></span> <span data-ttu-id="c43d1-178">새 기능 및 예정된 기능에 대한 자세한 내용은 Teams의 [새로운 기능](https://support.office.com/en-us/article/what-s-new-in-microsoft-teams-d7092a6d-c896-424c-b362-a472d5f105de?ui=en-US&rs=en-US&ad=US) 페이지 및 Teams의 [기술 커뮤니티 Microsoft Teams 블로그](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/What-s-new-in-Teams-Microsoft-Ignite-Edition/ba-p/252531)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c43d1-178">For more information about new and upcoming features, see the Teams [What's New](https://support.office.com/en-us/article/what-s-new-in-microsoft-teams-d7092a6d-c896-424c-b362-a472d5f105de?ui=en-US&rs=en-US&ad=US) page and the [Tech Community Microsoft Teams blog](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/What-s-new-in-Teams-Microsoft-Ignite-Edition/ba-p/252531) for Teams.</span></span> 

## <a name="more-information"></a><span data-ttu-id="c43d1-179">추가 정보</span><span class="sxs-lookup"><span data-stu-id="c43d1-179">More information</span></span>

<span data-ttu-id="c43d1-180">관리자 기능을 수행할 수 있는 역할에 대한 내용은 [Microsoft Teams 관리자 역할을 사용하여 Teams 관리](using-admin-roles.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c43d1-180">For information about which roles can perform admin functions, see [Use Microsoft Teams admin roles to manage Teams](using-admin-roles.md).</span></span>
