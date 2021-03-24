---
title: Microsoft Teams에서의 채팅, 팀, 채널 & 앱
ms.reviewer: ''
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: Microsoft Teams의 채팅, 팀, 앱 및 채널에 대한 Teams 설정을 구성하기 위한 단계별 지침이 포함되어 있습니다.
localization_priority: Priority
ms.collection:
- M365-collaboration
- m365initiative-deployteams
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.dashboard.helparticle.quickstartteamsadmin
appliesto:
- Microsoft Teams
- seo-marvel-apr2020
- seo-marvel-may2020
ms.openlocfilehash: a5cf7c91ef3b0e91504753a1e04ed334f4132adc
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094364"
---
# <a name="chat-teams-channels--apps-in-microsoft-teams"></a><span data-ttu-id="fb2ac-103">Microsoft Teams에서의 채팅, 팀, 채널 & 앱</span><span class="sxs-lookup"><span data-stu-id="fb2ac-103">Chat, teams, channels, & apps in Microsoft Teams</span></span>

<span data-ttu-id="fb2ac-p101">Teams는 조직에 즉시 사용할 수 있는 우수한 협업 환경을 제공하며, 대부분의 조직에서는 기본 설정이 사용된다는 사실을 알게 됩니다. 이 자료에서는 조직의 프로필 및 비즈니스 요구 사항에 따라 기본 설정을 변경할지 여부를 결정하는 데 도움이 되며, 각 변경 사항을 안내합니다. Microsoft는 설정을 두 그룹으로 나누었고, 첫 번째 그룹은 [사용자가 수행할 가능성이 더 높은 변경사항](#core-deployment-decisions)의 핵심 세트부터 시작합니다. 두 번째 그룹에는 조직의 필요에 따라 구성할 수 있는 [추가 설정](#additional-deployment-decisions)이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb2ac-p101">Teams provides a great out-of-the-box collaboration experience for your organization, and most organizations find that the default settings work for them. This article helps you decide whether to change any of the default settings, based on your organization's profile and business requirements, then it walks you through each change. We've split the settings into two groups, starting with the core set of [changes you're more likely to make](#core-deployment-decisions). The second group includes the [additional settings](#additional-deployment-decisions) you may want to configure, based on your organization's needs.</span></span>

<span data-ttu-id="fb2ac-108">시작하려면 당사의 짧은 Teams 채팅, 팀 그리고 채널 비디오(4:30분)를 시청하세요.</span><span class="sxs-lookup"><span data-stu-id="fb2ac-108">To get started, watch our short Teams chat, teams, and channels video (4:30 minutes):</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE476Yj]

<span data-ttu-id="fb2ac-109">*2019년 11월의 새로운 기능*</span><span class="sxs-lookup"><span data-stu-id="fb2ac-109">*New in November 2019*</span></span>
 - <span data-ttu-id="fb2ac-p102">이제 [Teams용 어드바이저(미리 보기)를 사용하여 Microsoft Teams](use-advisor-teams-roll-out.md)를 원격 설치할 수 있습니다. Teams용 어드바이저(미리 보기)가 Teams 배포 과정을 안내합니다. Microsoft 365 또는 Office 365 환경을 평가하고 Teams를 성공적으로 배포하기 전에 업데이트하거나 수정해야 하는 가장 일반적인 구성을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="fb2ac-p102">You can now [use Advisor for Teams (preview) to help you roll out Microsoft Teams](use-advisor-teams-roll-out.md). Advisor for Teams (preview) walks you through your Teams rollout. It assesses your Microsoft 365 or Office 365 environment and identifies the most common configurations that you may need to update or modify before you can successfully roll out Teams.</span></span>
 - <span data-ttu-id="fb2ac-113">Teams를 배포, 구성, 관리하는 방법을 보여주는 짧은(8-10분) 비디오를 포함한 [IT YouTube 채널용 Microsoft Teams 중요 기능](https://aka.ms/MicrosoftTeamsforIT)</span><span class="sxs-lookup"><span data-stu-id="fb2ac-113">[Microsoft Teams Essentials for IT YouTube channel](https://aka.ms/MicrosoftTeamsforIT), including short (8-10 minute) videos that show you how to roll out, configure, and manage Teams.</span></span>

> [!TIP]
> <span data-ttu-id="fb2ac-p103">초기 팀 롤아웃에 플래너와 같은 응용프로그램을 포함하는 것이 좋습니다. 팀 채택을 추진할 때 다른 [애플리케이션, 봇 및 커넥터](deploy-apps-microsoft-teams-landing-page.md)를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="fb2ac-p103">We recommend that you include our featured apps -- such as Planner -- in your initial Teams rollout. Add other [apps, bots, and connectors](deploy-apps-microsoft-teams-landing-page.md) as you drive Teams adoption.</span></span>

 > [!Note]
 > <span data-ttu-id="fb2ac-116">여러 플랫폼에서의 Teams 기능에 대한 자세한 내용은 [플랫폼별 Teams 기능을 참조](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)하세요.</span><span class="sxs-lookup"><span data-stu-id="fb2ac-116">For details about Teams features on different platforms, see [Teams features by platform](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).</span></span>

## <a name="chat-deployment-prerequisites"></a><span data-ttu-id="fb2ac-117">채팅 배포 전제 조건</span><span class="sxs-lookup"><span data-stu-id="fb2ac-117">Chat deployment prerequisites</span></span>

<span data-ttu-id="fb2ac-p104">조직 전체에 Teams를 배포하기 전에 시간을 내어 환경이 Teams를 위해 준비가 되었는지 확인합니다. [Teams를 위해 조직의 네트워크 준비](prepare-network.md)를 검토하고 필요한 환경을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="fb2ac-p104">Before you roll out Teams across your organization, take time to confirm that your environment is ready for Teams. Review [Prepare your organization's network for Teams](prepare-network.md) and make any required changes to your environment.</span></span>

|<span data-ttu-id="fb2ac-120">본인에게 질의하기</span><span class="sxs-lookup"><span data-stu-id="fb2ac-120">Ask yourself</span></span>|<span data-ttu-id="fb2ac-121">작업</span><span class="sxs-lookup"><span data-stu-id="fb2ac-121">Action</span></span> |
|------------|-------|
|<span data-ttu-id="fb2ac-122">조직에서 Teams를 배포할 준비가 되었는가?</span><span class="sxs-lookup"><span data-stu-id="fb2ac-122">Is my organization ready to roll out Teams?</span></span>|<span data-ttu-id="fb2ac-123">이 질문에 답변하려면 다음의 사항을 참조하세요:</span><span class="sxs-lookup"><span data-stu-id="fb2ac-123">To answer this question, see:</span></span> <ul><li>[<span data-ttu-id="fb2ac-124">Teams에 대한 조직의 네트워크 준비</span><span class="sxs-lookup"><span data-stu-id="fb2ac-124">Prepare your organization's network for Teams</span></span>](prepare-network.md)</li><li>[<span data-ttu-id="fb2ac-125">URL 및 IP 주소 범위</span><span class="sxs-lookup"><span data-stu-id="fb2ac-125">URLs and IP address ranges</span></span>](office-365-urls-ip-address-ranges.md)</li><li>[<span data-ttu-id="fb2ac-126">팀을 만들 때 Microsoft 365 그룹에 대한 계획</span><span class="sxs-lookup"><span data-stu-id="fb2ac-126">Plan for Microsoft 365 Groups when creating teams</span></span>](plan-office-365-groups.md)</li></ul>|
|||

## <a name="core-deployment-decisions"></a><span data-ttu-id="fb2ac-127">핵심 배포 결정사항</span><span class="sxs-lookup"><span data-stu-id="fb2ac-127">Core deployment decisions</span></span>

<span data-ttu-id="fb2ac-128">이들은 대부분의 조직이 변경하려는 채팅, 팀 그리고 채널의 설정입니다(기본 설정이 조직에 적합하지 않은 경우).</span><span class="sxs-lookup"><span data-stu-id="fb2ac-128">These are the chat, teams, and channels settings that most organizations want to change (if the default settings don't work for them).</span></span>

### <a name="teams-administrators"></a><span data-ttu-id="fb2ac-129">Teams 관리자</span><span class="sxs-lookup"><span data-stu-id="fb2ac-129">Teams administrators</span></span>

<span data-ttu-id="fb2ac-p105">Teams는 조직의 팀을 관리하는 데 사용할 수 있는 일련의 사용자 지정 관리자 역할을 제공합니다. 역할은 관리자에게 다양한 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="fb2ac-p105">Teams provides a set of custom administrator roles that can be used to manage Teams for your organization. The roles provide various capabilities to administrators.</span></span>

| <span data-ttu-id="fb2ac-132">본인에게 질의하기</span><span class="sxs-lookup"><span data-stu-id="fb2ac-132">Ask yourself</span></span> | <span data-ttu-id="fb2ac-133">작업</span><span class="sxs-lookup"><span data-stu-id="fb2ac-133">Action</span></span> |
|--------------|--------|
|<span data-ttu-id="fb2ac-134">Teams 커뮤니케이션 관리자 역할은 누구에게 할당될 것인가요?</span><span class="sxs-lookup"><span data-stu-id="fb2ac-134">Who will be assigned the Teams Communications Administrator role?</span></span>|<span data-ttu-id="fb2ac-135">Teams 관리자 역할에 대한 자세한 내용은 [팀을 관리하기 위한 Microsoft Teams 관리 역할의 활용](using-admin-roles.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fb2ac-135">To learn more about Teams administrator roles see [Use Microsoft Teams admin roles to manage Teams](using-admin-roles.md).</span></span>|
|<span data-ttu-id="fb2ac-136">Teams 커뮤니케이션 지원 기술자 역할은 누구에게 할당될 것인가요?</span><span class="sxs-lookup"><span data-stu-id="fb2ac-136">Who will be assigned the Teams Communications Support Engineer role?</span></span>|<span data-ttu-id="fb2ac-137">관리 역할을 할당하려면 [Azure Active Directory를 사용하여 사용자에게 관리자 및 비관리자 역할 할당](/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fb2ac-137">To assign admin roles, see [Assign administrator and non-administrator roles to users with Active Directory](/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal).</span></span>|
|<span data-ttu-id="fb2ac-138">Teams 커뮤니케이션 지원 전문가자 역할은 누구에게 할당될 것인가요?</span><span class="sxs-lookup"><span data-stu-id="fb2ac-138">Who will be assigned the Teams Communications Support Specialist role?</span></span>||
|||

### <a name="teams-owners-and-members"></a><span data-ttu-id="fb2ac-139">Teams 소유자 및 구성원</span><span class="sxs-lookup"><span data-stu-id="fb2ac-139">Teams owners and members</span></span>

<span data-ttu-id="fb2ac-p106">Teams에서는 관리자 역할 외에도 소유자 및 구성원 사용자 역할을 할당하고 채널 내에서 특정 작업을 수행할 수 있는 사용자를 제어할 수 있는 진행자 기능(조정 기능이 설정된 경우)을 선택적으로 제공할 수 있습니다. 중재를 통해 채널에서 새 게시물을 시작할 수 있는 사용자를 제어하고, 진행자로 팀 구성원을 추가 및 제거하고, 팀 구성원이 기존 채널 메시지에 회신할 수 있는지 여부를 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb2ac-p106">In addition to administrator roles, Teams lets you assign owner and member user roles, and selectively give them moderator capabilities (if moderation has been set up) to control who can perform certain actions within a channel. Moderation allows you to control who can start new posts in a channel, add and remove team members as moderators, and control whether team members can reply to existing channel messages.</span></span>

|<span data-ttu-id="fb2ac-142">본인에게 질의하기</span><span class="sxs-lookup"><span data-stu-id="fb2ac-142">Ask yourself</span></span>|<span data-ttu-id="fb2ac-143">작업</span><span class="sxs-lookup"><span data-stu-id="fb2ac-143">Action</span></span> |
|------------|-------|
|<span data-ttu-id="fb2ac-144">각 역할에는 누가 할당되어야 하나요?</span><span class="sxs-lookup"><span data-stu-id="fb2ac-144">Who should be assigned to each role?</span></span> | <span data-ttu-id="fb2ac-145">각 역할의 기능을 비교하려면 [Microsoft Teams에서 팀 소유자, 조정자 및 구성원 할당하기](assign-roles-permissions.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fb2ac-145">To compare the capabilities of each role, see [Assign team owners, moderators, and members in Microsoft Teams](assign-roles-permissions.md).</span></span>
|<span data-ttu-id="fb2ac-146">사용자 역할은 어떻게 할당하나요?</span><span class="sxs-lookup"><span data-stu-id="fb2ac-146">How do I assign a user role?</span></span> | <span data-ttu-id="fb2ac-147">역할을 할당하거나 변경하려면 [사용자 역할 할당](assign-roles-permissions.md#assign-a-user-role)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fb2ac-147">To assign or change a role, see [Assign a user role](assign-roles-permissions.md#assign-a-user-role).</span></span>
|<span data-ttu-id="fb2ac-148">채널에서 게시나 회신을 할 수 있는 사용자를 통제해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="fb2ac-148">Do I need to control who can post and reply in a channel?</span></span> | <span data-ttu-id="fb2ac-149">조정 기능을 구성하려면 [Microsoft Teams에서 채널 조정 설정 및 관리](manage-channel-moderation-in-teams.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fb2ac-149">To configure moderation, see [Set up and manage channel moderation in Microsoft Teams](manage-channel-moderation-in-teams.md).</span></span>

### <a name="messaging-policies"></a><span data-ttu-id="fb2ac-150">메시징 정책</span><span class="sxs-lookup"><span data-stu-id="fb2ac-150">Messaging policies</span></span>

<span data-ttu-id="fb2ac-p107">메시징 정책은 Teams 내 사용자가 사용할 수 있는 대화 및 채널 메시징 기능을 제어합니다. 예를 들어 보낸 메시지를 편집 및 삭제할 수 있는 사용자, 대화를 사용할 수 있는 사용자, 대화에 밈을 사용할 수 있는 사용자 등이 있습니다. 기본적으로 사용자에게 글로벌 메시징 정책이 할당되고 모든 기능은 **켜짐** 상태입니다. 기본 글로벌 정책을 사용하거나 조직 내 사용자에 대해 하나 이상의 사용자 지정 메시징 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb2ac-p107">Messaging policies control which chat and channel messaging features are available to users in Teams. For example, who can edit and delete sent messages, who can use chat, who can use memes in conversations, and more. By default, users are assigned the global messaging policy and all features are **On**. You can use the default global policy or create one or more custom messaging policies for people in your organization.</span></span> 

|<span data-ttu-id="fb2ac-155">본인에게 질의하기</span><span class="sxs-lookup"><span data-stu-id="fb2ac-155">Ask yourself</span></span>|<span data-ttu-id="fb2ac-156">작업</span><span class="sxs-lookup"><span data-stu-id="fb2ac-156">Action</span></span> |
|------------|-------|
|<span data-ttu-id="fb2ac-157">전역 메시징 정책을 사용자 지정해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="fb2ac-157">Will I customize the global messaging policy?</span></span>|<span data-ttu-id="fb2ac-158">Microsoft Teams 관리 센터를 사용하여 전역 메시징 정책을 변경하거나 새 정책을 추가하는 방법에 대한 자세한 내용은 [Teams에서 메시징 정책 관리](messaging-policies-in-teams.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fb2ac-158">For information about using the Microsoft Teams admin center to change the global messaging policy or add a new policy, see [Manage messaging policies in Teams](messaging-policies-in-teams.md).</span></span>|
|<span data-ttu-id="fb2ac-159">여러개의 메시징 정책이 필요한가요?</span><span class="sxs-lookup"><span data-stu-id="fb2ac-159">Do I require multiple messaging policies?</span></span>|<span data-ttu-id="fb2ac-160">PowerShell에서 메시징 정책을 만들고 할당하려면 [PowerShell 스크립트 샘플 - 메시징 정책 만들기 및 할당](scripts/powershell-script-teams-messaging-policy-edu.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fb2ac-160">To create and assign a messaging policy in PowerShell, see [PowerShell script sample - Create and assign a messaging policy](scripts/powershell-script-teams-messaging-policy-edu.md).</span></span>|
|<span data-ttu-id="fb2ac-161">어떠한 사용자 그룹에 어떠한 메시징 정책을 할당할지를 어떻게 결정하나요?</span><span class="sxs-lookup"><span data-stu-id="fb2ac-161">How will I determine which groups of users get which messaging policy?</span></span>|<span data-ttu-id="fb2ac-162">CsTeamsMessagingPolicy cmdlet에 대한 내용은 [설정-CsTeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fb2ac-162">To learn about the CsTeamsMessagingPolicy cmdlets, see [Set-CsTeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps).</span></span>|
||| 

### <a name="external-access"></a><span data-ttu-id="fb2ac-163">외부 액세스</span><span class="sxs-lookup"><span data-stu-id="fb2ac-163">External access</span></span>

<span data-ttu-id="fb2ac-p108">외부 액세스(이전에는 연합이라고 함)를 통해 팀 및 비즈니스용 Skype 사용자가 조직 외부에 있는 사용자와 통신할 수 있습니다. 이 옵션을 설정하고 허용 목록에 도메인을 추가하면 사용자는 다른 도메인 및 조직의 사용자와 통신할 수 있습니다. 외부 액세스는 개인이 아닌 전체 도메인에 액세스 권한이 부여된다는 점에서 게스트 액세스와 다릅니다. 외부 액세스는 기본적으로 꺼져 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb2ac-p108">External access (formerly known as federation) lets your Teams and Skype for Business users communicate with users who are outside of your organization. By turning this on and adding domains to the allowed list, your users can communicate with users in other domains and organizations. External access differs from guest access in that an entire domain is given access permission, not an individual. External access is turned off by default.</span></span>

|<span data-ttu-id="fb2ac-168">본인에게 질의하기</span><span class="sxs-lookup"><span data-stu-id="fb2ac-168">Ask yourself</span></span>|<span data-ttu-id="fb2ac-169">작업</span><span class="sxs-lookup"><span data-stu-id="fb2ac-169">Action</span></span> |
|------------|-------|
|<ul><li><span data-ttu-id="fb2ac-170">나의 조직의 외부 액세스 기능을 켜야 하나요?</span><span class="sxs-lookup"><span data-stu-id="fb2ac-170">Will I turn on external access for my organization?</span></span></li><li><span data-ttu-id="fb2ac-171">이 기능을 사용하는 경우 나의 조직에서 통신할 수 있는 도메인을 제한하게 되나요?</span><span class="sxs-lookup"><span data-stu-id="fb2ac-171">If enabled, will I limit which domains my organization can communicate with?</span></span></li></ul> |<br><span data-ttu-id="fb2ac-172">외부 액세스 기능을 켜려면 [외부 액세스 계획](manage-external-access.md#plan-for-external-access)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fb2ac-172">To turn on external access, see [Plan for external access](manage-external-access.md#plan-for-external-access).</span></span>|
|||

### <a name="guest-access"></a><span data-ttu-id="fb2ac-173">게스트 액세스</span><span class="sxs-lookup"><span data-stu-id="fb2ac-173">Guest access</span></span>

<span data-ttu-id="fb2ac-p109">Teams 내 게스트 액세스를 통해 조직 외부의 개인이 팀 및 채널에 액세스할 수 있습니다. 게스트 액세스 설정을 사용하여 게스트 사용자가 사용할 수 있거나 사용할 수 없는 기능을 제어할 수 있습니다. 게스트 액세스는 기본적으로 해제되어 있습니다. 자세한 내용은 [Teams의 게스트 액세스 권한](./guest-access.md)을 참조하시기 바랍니다.</span><span class="sxs-lookup"><span data-stu-id="fb2ac-p109">Guest access in Teams lets individuals outside your organization access teams and channels. You can use the guest access settings to control which features guest users can or can't use. Guest access is turned off by default. To learn more, see [Guest access in Teams](./guest-access.md).</span></span>

> [!NOTE]
> <span data-ttu-id="fb2ac-178">외부 액세스 및 게스트 액세스에 대한 자세한 내용은 [Microsoft Teams의 다른 조직의 사용자와 통신](communicate-with-users-from-other-organizations.md)을 참조하세요</span><span class="sxs-lookup"><span data-stu-id="fb2ac-178">For more on External access and Guest access see here - [Communicate with users from other organizations in Microsoft Teams](communicate-with-users-from-other-organizations.md)</span></span>


|<span data-ttu-id="fb2ac-179">본인에게 질의하기</span><span class="sxs-lookup"><span data-stu-id="fb2ac-179">Ask yourself</span></span>|<span data-ttu-id="fb2ac-180">작업</span><span class="sxs-lookup"><span data-stu-id="fb2ac-180">Action</span></span> |
|------------|-------|
|<span data-ttu-id="fb2ac-181">나의 조직의 Teams 액세스 기능을 켜야 하나요?</span><span class="sxs-lookup"><span data-stu-id="fb2ac-181">Will I turn on guest access for my organization?</span></span>|<span data-ttu-id="fb2ac-182">게스트 액세스를 켜려면 [Teams에서 게스트 액세스 설정 또는 해제](set-up-guests.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fb2ac-182">To turn on guest access, see [Turn on or off guest access in Teams](set-up-guests.md).</span></span>|
|<span data-ttu-id="fb2ac-183">이 기능을 사용하는 경우 조직의 게스트가 사용할 수 있는 기능을 사용자 지정할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="fb2ac-183">If enabled, will I customize the features available to guests in my organization?</span></span>|<span data-ttu-id="fb2ac-184">게스트 액세스 기능의 가용성을 사용자 지정 하려면 [Teams에서 게스트 액세스 권한 부여](teams-dependencies.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fb2ac-184">To customize guest access feature availability, see [Authorize guest access in Teams](teams-dependencies.md).</span></span>|
|||

### <a name="teams-settings"></a><span data-ttu-id="fb2ac-185">Teams 설정</span><span class="sxs-lookup"><span data-stu-id="fb2ac-185">Teams settings</span></span>

<span data-ttu-id="fb2ac-p110">Teams 설정을 사용하여 전자 메일 통합, 클라우드 저장소 옵션, 조직 탭, 회의실 장치 설정 및 검색 범위와 같은 기능에 맞게 Teams를 설정할 수 있습니다. 이러한 설정을 변경하면 해당 설정은 조직의 모든 팀에 적용됩니다. 자세한 내용은 [Teams 설정](enable-features-office-365.md#teams-settings)을(를) 참조하시기 바랍니다.</span><span class="sxs-lookup"><span data-stu-id="fb2ac-p110">Teams settings let you set up your teams for features such as email integration, cloud storage options, organization tab, meeting room device setup, and search scope. When you make changes to these settings, they apply to all the teams in your organization. To learn more, see [Teams settings](enable-features-office-365.md#teams-settings).</span></span>

|<span data-ttu-id="fb2ac-189">본인에게 질의하기</span><span class="sxs-lookup"><span data-stu-id="fb2ac-189">Ask yourself</span></span>|<span data-ttu-id="fb2ac-190">작업</span><span class="sxs-lookup"><span data-stu-id="fb2ac-190">Action</span></span> |
|------------|-------|
|<span data-ttu-id="fb2ac-191">나의 조직의 Teams 설정을 사용자 지정할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="fb2ac-191">Will I customize Teams settings for my organization?</span></span> | <span data-ttu-id="fb2ac-192">Teams 설정 및 사용자 지정 방법에 대한 내용은 [Teams 설정](enable-features-office-365.md#teams-settings)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fb2ac-192">To learn about Teams settings and how to customize them, see [Teams settings](enable-features-office-365.md#teams-settings).</span></span>|
|||

### <a name="teams-clients"></a><span data-ttu-id="fb2ac-193">Teams 클라이언트</span><span class="sxs-lookup"><span data-stu-id="fb2ac-193">Teams clients</span></span>

<span data-ttu-id="fb2ac-p111">Teams는 웹에서 데스크톱, 모바일까지 여러 클라이언트를 지원하며, 기본 구성을 통해 사용자는 원하는 클라이언트를 선택할 수 있습니다. 자세한 내용은 [Teams용 클라이언트 가져오기](get-clients.md)를 참조하시기 바랍니다.</span><span class="sxs-lookup"><span data-stu-id="fb2ac-p111">Teams supports a number of clients from web to desktop to mobile, and the default configuration lets users choose whichever clients they want. To learn more, see [Get clients for Teams](get-clients.md).</span></span>

|<span data-ttu-id="fb2ac-196">본인에게 질의하기</span><span class="sxs-lookup"><span data-stu-id="fb2ac-196">Ask yourself</span></span>|<span data-ttu-id="fb2ac-197">작업</span><span class="sxs-lookup"><span data-stu-id="fb2ac-197">Action</span></span> |
|------------|-------|
|<span data-ttu-id="fb2ac-198">나의 조직의 Teams 클라이언트 가용성을 사용자 지정할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="fb2ac-198">Will I customize Teams client availability for my organization?</span></span>|<span data-ttu-id="fb2ac-199">[Teams 앱의 하드웨어 요구 사항](hardware-requirements-for-the-teams-app.md)을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="fb2ac-199">Check out [Hardware requirements for the Teams app](hardware-requirements-for-the-teams-app.md).</span></span> |
|<span data-ttu-id="fb2ac-200">나의 조직의 Teams 클라이언트 설정을 사용자 지정할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="fb2ac-200">Will I customize Teams client settings for my organization?</span></span>|<span data-ttu-id="fb2ac-201">[MSI를 사용하여 Teams를 설치](msi-deployment.md)하는 방법을 학습하세요.</span><span class="sxs-lookup"><span data-stu-id="fb2ac-201">Learn how to [Install Teams using MSI](msi-deployment.md).</span></span>|
|||

### <a name="teams-usage-reporting"></a><span data-ttu-id="fb2ac-202">Teams 사용 현황 보고</span><span class="sxs-lookup"><span data-stu-id="fb2ac-202">Teams usage reporting</span></span>

<span data-ttu-id="fb2ac-p112">전역 관리자, Teams 서비스 관리자 그리고 보고서 구독자 역할은 Teams 사용 현황 보고서를 볼 수 있습니다. 자세한 내용은 [Microsoft 365 사용 분석](/microsoft-365/admin/usage-analytics/usage-analytics)을(를) 참조하시기 바랍니다.</span><span class="sxs-lookup"><span data-stu-id="fb2ac-p112">The Global Admin, Teams Service Admin, and Reports Readers roles can view Teams usage reports. To learn more, see the [Microsoft 365 usage analytics](/microsoft-365/admin/usage-analytics/usage-analytics).</span></span>

|<span data-ttu-id="fb2ac-205">본인에게 질의하기</span><span class="sxs-lookup"><span data-stu-id="fb2ac-205">Ask yourself</span></span>|<span data-ttu-id="fb2ac-206">작업</span><span class="sxs-lookup"><span data-stu-id="fb2ac-206">Action</span></span> |
|------------|-------|
|<br> <span data-ttu-id="fb2ac-207">팀 사용 현황 보고서를 확인해야 하는 사용자는 누구이고 그들은 보고서를 볼 수 있는 올바른 역할을 보유하고 있나요?</span><span class="sxs-lookup"><span data-stu-id="fb2ac-207">Who needs to see the Teams usage reports, and do they have the correct role to view them?</span></span> |<ul><li><span data-ttu-id="fb2ac-208">사용자가 관리자가 아닌 경우에는 [보고서 리더 역할을 할당합니다](teams-activity-reports.md#reports-reader-role).</span><span class="sxs-lookup"><span data-stu-id="fb2ac-208">If the user isn't an admin, [assign the Reports reader role](teams-activity-reports.md#reports-reader-role).</span></span></li><li><span data-ttu-id="fb2ac-209">[역할 및 사용 권한](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)과 [역할 보기 및 지정](/azure/active-directory/users-groups-roles/directory-manage-roles-portal)을 참조하여 Azure Active Directory에서 관리 역할을 할당하는 방법을 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="fb2ac-209">See [Roles and permissions](/azure/active-directory/users-groups-roles/directory-assign-admin-roles) and [View and assign roles](/azure/active-directory/users-groups-roles/directory-manage-roles-portal) to learn how to assign admin roles in Azure Active Directory.</span></span> |
|||

### <a name="teams-default-apps"></a><span data-ttu-id="fb2ac-210">Teams 기본 앱</span><span class="sxs-lookup"><span data-stu-id="fb2ac-210">Teams default apps</span></span> 

<span data-ttu-id="fb2ac-p113">Teams는 사용자를 참여시키고 생산성을 지원하며 자주 사용되는 비즈니스 서비스를 Teams로 통합하기 위해 수많은 제1자(Microsoft 제공) 및 제3자 앱을 제공합니다. Teams Store에서 앱을 가져옵니다. Teams에는 기본적으로 앱이 설정되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb2ac-p113">Teams provides a number of first-party (Microsoft provided) and third-party apps to engage users, support productivity, and integrate commonly used business services into Teams. Get apps from the Teams Store. Apps are turned on by default in Teams.</span></span> 

<span data-ttu-id="fb2ac-214">Teams에서의 앱의 배포 및 관리에 대한 자세한 내용은 당사의 심층적인 [앱, 봇 그리고 커넥터](deploy-apps-microsoft-teams-landing-page.md) 지침을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fb2ac-214">To learn more about rolling out and managing apps in Teams, see our in-depth [Apps, bots, & connectors](deploy-apps-microsoft-teams-landing-page.md) guidance.</span></span>

## <a name="additional-deployment-decisions"></a><span data-ttu-id="fb2ac-215">추가 배포 결정사항</span><span class="sxs-lookup"><span data-stu-id="fb2ac-215">Additional deployment decisions</span></span>

<span data-ttu-id="fb2ac-216">조직의 요구 사항 및 구성에 따라 이러한 설정을 변경하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="fb2ac-216">You may want to change these settings, based on your organization's needs and configuration.</span></span>

### <a name="teams-licensing"></a><span data-ttu-id="fb2ac-217">Teams 라이선싱</span><span class="sxs-lookup"><span data-stu-id="fb2ac-217">Teams licensing</span></span>

<span data-ttu-id="fb2ac-p114">Teams는 많은 Microsoft 365 또는 Office 365 라이선스의 일부로 제공됩니다. Teams 라이선스에 대한 자세한 내용은 [Microsoft Teams 서비스 설명](/office365/servicedescriptions/teams-service-description)을(를) 참조하시기 바랍니다.</span><span class="sxs-lookup"><span data-stu-id="fb2ac-p114">Teams is provided as part of many Microsoft 365 or Office 365 licenses. To learn more about Teams licensing, see [Microsoft Teams service description](/office365/servicedescriptions/teams-service-description).</span></span>

|<span data-ttu-id="fb2ac-220">본인에게 질의하기</span><span class="sxs-lookup"><span data-stu-id="fb2ac-220">Ask yourself</span></span>|<span data-ttu-id="fb2ac-221">작업</span><span class="sxs-lookup"><span data-stu-id="fb2ac-221">Action</span></span> |
|------------|-------|
|<span data-ttu-id="fb2ac-222">사용자는 배포하려는 모든 Teams의 기능을 사용하기 위해 필요한 라이선스가 있나요?</span><span class="sxs-lookup"><span data-stu-id="fb2ac-222">Do my users have the licenses they need in order to use all the Teams features I want to roll out?</span></span> | <span data-ttu-id="fb2ac-223">라이선싱 요구 사항에 대한 자세한 내용은 [Microsoft Teams 서비스 설명](/office365/servicedescriptions/teams-service-description)을 읽어 보세요.</span><span class="sxs-lookup"><span data-stu-id="fb2ac-223">To learn about licensing requirements, read [Microsoft Teams service description](/office365/servicedescriptions/teams-service-description).</span></span>|
|||

### <a name="exchange-and-sharepoint-interoperability"></a><span data-ttu-id="fb2ac-224">Exchange 및 SharePoint 상호 운용성</span><span class="sxs-lookup"><span data-stu-id="fb2ac-224">Exchange and SharePoint interoperability</span></span>

<span data-ttu-id="fb2ac-p115">전체 Teams 환경을 사용하려면 Exchange Online, SharePoint Online 및 Microsoft 365 그룹 생성을 위해 모든 사용자가 사용 가능해야 합니다. 다음 기사에서는 다양한 환경에서 호스팅되는 Exchange 메일박스와 관련된 정보, Exchange 및 팀이 상호 작용하는 방식, SharePoint 및 비즈니스용 OneDrive와 유사한 고려사항을 간략히 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="fb2ac-p115">For the full Teams experience, every user should be enabled for Exchange Online, SharePoint Online, and Microsoft 365 group creation. The following articles outline information related to Exchange mailboxes hosted in various environments, how Exchange and Teams interact, and similar considerations for SharePoint and OneDrive for Business.</span></span>

|<span data-ttu-id="fb2ac-227">본인에게 질의하기</span><span class="sxs-lookup"><span data-stu-id="fb2ac-227">Ask yourself</span></span>|<span data-ttu-id="fb2ac-228">작업</span><span class="sxs-lookup"><span data-stu-id="fb2ac-228">Action</span></span> |
|------------|-------|
| <span data-ttu-id="fb2ac-229">현재의 Exchange 및 SharePoint 배포에 필요한 Teams의 기능을 배포할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="fb2ac-229">Will I be able to deploy the Teams features that I require with the current Exchange and SharePoint deployments?</span></span> |<span data-ttu-id="fb2ac-230">Teams에서의 Exchange 및 SharePoint에 대한 자세한 내용은 다음을 참조하세요:</span><span class="sxs-lookup"><span data-stu-id="fb2ac-230">For more information about Exchange and SharePoint in Teams, see:</span></span><ul><li> [<span data-ttu-id="fb2ac-231">Exchange와 Teams의 상호 작용 방법</span><span class="sxs-lookup"><span data-stu-id="fb2ac-231">How Exchange and Teams interact</span></span>](exchange-teams-interact.md)</li><li>[<span data-ttu-id="fb2ac-232">SharePoint Online 및 비즈니스용 OneDrive가 Teams와 상호 작용하는 방법</span><span class="sxs-lookup"><span data-stu-id="fb2ac-232">How SharePoint Online and OneDrive for Business interact with Teams</span></span>](sharepoint-onedrive-interact.md)|
|||

### <a name="teams-limits-and-specifications"></a><span data-ttu-id="fb2ac-233">Teams의 제한과 사양</span><span class="sxs-lookup"><span data-stu-id="fb2ac-233">Teams limits and specifications</span></span> 

<span data-ttu-id="fb2ac-234">Teams의 엔터프라이즈 배포를 계획할 때 팀의 최대 구성원 수, 사용자가 만들 수 있는 최대 팀 수 등과 같은 관련 제한 사항과 사양을 고려해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb2ac-234">When planning an enterprise deployment of Teams, you should take into account any relevant limitations and specifications, such as the maximum number of members in a team, the maximum number of teams a user can create, and so on.</span></span>

|<span data-ttu-id="fb2ac-235">본인에게 질의하기</span><span class="sxs-lookup"><span data-stu-id="fb2ac-235">Ask yourself</span></span>|<span data-ttu-id="fb2ac-236">작업</span><span class="sxs-lookup"><span data-stu-id="fb2ac-236">Action</span></span> |
|------------|-------|
| <span data-ttu-id="fb2ac-237">Teams의 배포 시 나는 어떠한 제한에 걸리기 쉽나요?</span><span class="sxs-lookup"><span data-stu-id="fb2ac-237">What limits am I likely to hit with my Teams rollout?</span></span> | <span data-ttu-id="fb2ac-238">자세한 내용은 [Teams의 제한과 사양](limits-specifications-teams.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fb2ac-238">To learn more, read [Limits and specifications for Teams](limits-specifications-teams.md).</span></span> |
|||

### <a name="urls-and-ports"></a><span data-ttu-id="fb2ac-239">URL 및 포트</span><span class="sxs-lookup"><span data-stu-id="fb2ac-239">URLs and ports</span></span>

<span data-ttu-id="fb2ac-p116">인터넷 트래픽을 세부적으로 제어하는 조직은 Teams에 맞게 올바르게 구성해야 하는 URL, IP 주소, 포트 및 프로토콜의 최신 목록을 보려면 [URL 및 IP 주소 범위](/office365/enterprise/urls-and-ip-address-ranges)를 읽어야 합니다. Microsoft는 Microsoft 365 및 Office 365 서비스를 지속적으로 개선하고 새로운 기능을 추가하고 있습니다. 즉, 필요한 포트, URL 및 IP 주소가 시간이 지남에 따라 변경될 수 있습니다. 이 정보가 업데이트되거나 변경될 때 알림을 받으려면 RSS를 통해 구독하는 것이 좋습니다. 최소한 [Chat 배포 필수 구성 요소](#chat-deployment-prerequisites)에 위에 나열된 포트를 열었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="fb2ac-p116">Organizations that maintain fine-grained control of their internet traffic should read [URLs and IP address ranges](/office365/enterprise/urls-and-ip-address-ranges) for an up-to-date list of the URLs, IP addresses, ports, and protocols that must be correctly configured for Teams. Microsoft is continuously improving the Microsoft 365 and Office 365 services and adding new functionality, which means the required ports, URLs, and IP addresses may change over time. We recommend that you subscribe via RSS to receive notifications when this information is updated or changed. At a minimum, make sure you've opened the ports listed above in [Chat deployment prerequisites](#chat-deployment-prerequisites).</span></span>

|<span data-ttu-id="fb2ac-244">본인에게 질의하기</span><span class="sxs-lookup"><span data-stu-id="fb2ac-244">Ask yourself</span></span>|<span data-ttu-id="fb2ac-245">작업</span><span class="sxs-lookup"><span data-stu-id="fb2ac-245">Action</span></span> |
|------------|-------|
| <span data-ttu-id="fb2ac-246">사용자가 Teams를 사용할 수 있도록 하려면 인터넷 액세스 규칙이 필요한가요 혹은 필요한 최소 포트를 여는 것으로 충분하나요?</span><span class="sxs-lookup"><span data-stu-id="fb2ac-246">Do I require internet access rules to enable users to use Teams, or is it sufficient to open the minimum required ports?</span></span> | <span data-ttu-id="fb2ac-247">자세한 내용은 [URL 및 IP 주소 범위](office-365-urls-ip-address-ranges.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fb2ac-247">To learn more, see [URLs and IP address ranges](office-365-urls-ip-address-ranges.md).</span></span>|
|||

### <a name="governance-naming-conventions-who-can-create-teams"></a><span data-ttu-id="fb2ac-248">거버넌스 (팀을 만들 수 있는 사용자 명명 규칙)</span><span class="sxs-lookup"><span data-stu-id="fb2ac-248">Governance (naming conventions, who can create teams)</span></span>

<span data-ttu-id="fb2ac-p117">조직에서는 팀 이름 지정 및 분류 방법, 팀 생성 및 팀 만료, 보존 및 아카이빙에 대한 제어를 구현해야 할 수 있습니다. 이를 거버넌스라고 합니다. Azure AD(Azure Active Directory)를 사용하여 이러한 각 영역을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb2ac-p117">Your organization might require that you implement controls on how teams are named and classified, who can create teams, and team expiration, retention, and archiving. This is called governance. You can use Azure Active Directory (Azure AD) to configure each of these areas.</span></span>


| <span data-ttu-id="fb2ac-252">본인에게 질의하기</span><span class="sxs-lookup"><span data-stu-id="fb2ac-252">Ask yourself</span></span> | <span data-ttu-id="fb2ac-253">작업</span><span class="sxs-lookup"><span data-stu-id="fb2ac-253">Action</span></span> |
|--------------|--------|
|<span data-ttu-id="fb2ac-254">팀을 만들 수 있는 사용자에 대한 제어를 수행해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="fb2ac-254">Will I need to implement controls on who can create teams?</span></span>| <span data-ttu-id="fb2ac-255">[Teams에서의 거버넌스 계획](plan-teams-governance.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fb2ac-255">Read [Plan for governance in Teams](plan-teams-governance.md).</span></span>|
|<span data-ttu-id="fb2ac-256">Teams의 명명 규칙 방식에 대한 제어를 수행해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="fb2ac-256">Will I need to implement controls on how teams are named?</span></span>|<span data-ttu-id="fb2ac-257">[Azure AD에서 Microsoft 365 그룹에 대한 명명 정책 적용](/azure/active-directory/users-groups-roles/groups-naming-policy)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fb2ac-257">Read [Enforce a naming policy for Microsoft 365 groups in Azure AD](/azure/active-directory/users-groups-roles/groups-naming-policy).</span></span>|
|||

### <a name="teams-application-policy-side-rail-control"></a><span data-ttu-id="fb2ac-258">Teams 응용 프로그램 정책(측면 레일 제어)</span><span class="sxs-lookup"><span data-stu-id="fb2ac-258">Teams application policy (side-rail control)</span></span>

<span data-ttu-id="fb2ac-p118">고정된 앱이 Teams의 측면 레일에 나타납니다. 팀 응용 프로그램 정책을 만들면 고정된 팀 앱 집합을 미리 구성하여 선택한 사용자 그룹에 대해 팀을 사용자 지정할 수 있습니다. 기본적으로 **Microsoft Teams** 에서 외부 앱 허용 설정이 켜져 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb2ac-p118">A pinned app shows up in the side rail in Teams. By creating Teams application policies, you can preconfigure sets of pinned Teams apps to personalize Teams for select groups of users. By default, the **Allow external apps in Microsoft Teams** setting is turned on.</span></span>

| <span data-ttu-id="fb2ac-262">본인에게 질의하기</span><span class="sxs-lookup"><span data-stu-id="fb2ac-262">Ask yourself</span></span> | <span data-ttu-id="fb2ac-263">작업</span><span class="sxs-lookup"><span data-stu-id="fb2ac-263">Action</span></span> |
|--------------|--------|
|<span data-ttu-id="fb2ac-264">미리 구성된 고정된 Teams 응용 프로그램의 집합을 만들어야 하나요?</span><span class="sxs-lookup"><span data-stu-id="fb2ac-264">Should I create preconfigured sets of pinned Teams applications?</span></span> | <span data-ttu-id="fb2ac-265">[Team에서 앱에 대한 관리 설정](admin-settings.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fb2ac-265">Read [Admin settings for apps in Teams](admin-settings.md).</span></span>|
|<span data-ttu-id="fb2ac-266">어떠한 그룹이 이 앱 그룹화를 적용받을 것인지를 어떻게 결정하나요?</span><span class="sxs-lookup"><span data-stu-id="fb2ac-266">How will I decide which groups receive these app groupings?</span></span>|<span data-ttu-id="fb2ac-267">[Teams 앱 사용 권한 및 고려 사항](app-permissions.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fb2ac-267">Read [Teams apps permissions and considerations](app-permissions.md).</span></span>|
|||

### <a name="archiving-and-compliance"></a><span data-ttu-id="fb2ac-268">보관 및 규정 준수</span><span class="sxs-lookup"><span data-stu-id="fb2ac-268">Archiving and compliance</span></span> 

<span data-ttu-id="fb2ac-p119">조직에서는 팀이 아카이브되는 방식과 특정 유형의 팀에 보관되는 데이터 유형에 대한 제어를 구현해야 할 수 있습니다. 기본적으로 설정되어 있는 Teams 설정을 확인하려면 [Teams 보안 및 규정 준수 개요](security-compliance-overview.md)를 읽으세요.</span><span class="sxs-lookup"><span data-stu-id="fb2ac-p119">Your organization might require that you implement controls on how teams are archived and the types of data that are held in certain types of teams. Read [Overview of security and compliance in Teams](security-compliance-overview.md) to learn which Teams settings are turned on by default.</span></span>

| <span data-ttu-id="fb2ac-271">본인에게 질의하기</span><span class="sxs-lookup"><span data-stu-id="fb2ac-271">Ask yourself</span></span> | <span data-ttu-id="fb2ac-272">작업</span><span class="sxs-lookup"><span data-stu-id="fb2ac-272">Action</span></span> |
|--------------|--------|
|<span data-ttu-id="fb2ac-273">팀 보존을 구성해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="fb2ac-273">Will I need to configure team retention?</span></span>|<span data-ttu-id="fb2ac-274">보존 정책을 설정하려면 [Teams 보존 정책 설정](retention-policies.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fb2ac-274">To set up retention policies, see [Set up Teams retention policies](retention-policies.md).</span></span>|
|<span data-ttu-id="fb2ac-275">팀 보관을 구성해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="fb2ac-275">Will I need to configure team archiving?</span></span>|<span data-ttu-id="fb2ac-276">팀을 보관하거나 복원하려면 [팀의 보관 또는 복원](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fb2ac-276">To archive or restore a team, see [Archive or restore a team](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7).</span></span>|
|<span data-ttu-id="fb2ac-277">추가적 규정 준수 설정을 구성해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="fb2ac-277">Will I need to configure additional compliance settings?</span></span>|<span data-ttu-id="fb2ac-278">보안 및 규정 준수에 대한 자세한 내용은 [Teams에서의 보안 및 규정 준수 개요](security-compliance-overview.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fb2ac-278">For more information about security and compliance, see [Overview of security and compliance in Teams](security-compliance-overview.md).</span></span>|
|||

### <a name="conditional-access"></a><span data-ttu-id="fb2ac-279">조건부 액세스</span><span class="sxs-lookup"><span data-stu-id="fb2ac-279">Conditional access</span></span> 

<span data-ttu-id="fb2ac-p120">Teams는 회의, 일정, 상호 대화, 파일 공유 등 핵심 생산성 시나리오에 Exchange Online, SharePoint Online 및 비즈니스용 Skypes Online에 크게 의존합니다. 이러한 클라우드 앱에 대해 설정된 조건부 액세스 정책은 사용자가 모든 클라이언트에서 Teams로 직접 로그인할 때 Teams에 적용됩니다. Teams 클라우드 앱 제어 측면에 대해 설정된 조건부 액세스 정책(예: 사용자가 특정 네트워크에서 팀 서비스에 액세스할 수 있는지 여부)입니다.</span><span class="sxs-lookup"><span data-stu-id="fb2ac-p120">Teams relies heavily on Exchange Online, SharePoint Online, and Skype for Business Online for core productivity scenarios, including meetings, calendars, interop chats, and file sharing. Conditional access policies that are set for these cloud apps apply to Teams when a user signs in directly to Teams, on any client. Conditional access policies that are set for the Teams cloud app control aspects such as whether users can access Teams services from certain networks.</span></span>

| <span data-ttu-id="fb2ac-283">본인에게 질의하기</span><span class="sxs-lookup"><span data-stu-id="fb2ac-283">Ask yourself</span></span> | <span data-ttu-id="fb2ac-284">작업</span><span class="sxs-lookup"><span data-stu-id="fb2ac-284">Action</span></span> |
|--------------|--------|
|<br><span data-ttu-id="fb2ac-285">Teams에 대한 조건부 액세스를 구성해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="fb2ac-285">Will I need to configure conditional access for Teams?</span></span>|<ul><li><span data-ttu-id="fb2ac-286">액세스 정책의 작동 방식을 이해하려면 [조건부 액세스 정책이 Teams에서 어떻게 작동하나요?](security-compliance-overview.md#how-conditional-access-policies-work-for-teams)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fb2ac-286">To understand how access policies work, see [How do conditional access policies work for Teams?](security-compliance-overview.md#how-conditional-access-policies-work-for-teams)</span></span></li><li><span data-ttu-id="fb2ac-287">Teams에 대한 다단계 인증(MFA)을 설정하려면 다음을 참조하세요:</span><span class="sxs-lookup"><span data-stu-id="fb2ac-287">To set up multi-factor authentication (MFA) for Teams, see:</span></span><ul><li>[<span data-ttu-id="fb2ac-288">빠른 시작: Azure Active Directory 조건부 액세스를 사용하는 특정 앱에 MFA 요구</span><span class="sxs-lookup"><span data-stu-id="fb2ac-288">Quickstart: Require MFA for specific apps with Azure Active Directory conditional access</span></span>](/azure/active-directory/conditional-access/app-based-mfa)</li><li>[<span data-ttu-id="fb2ac-289">Azure Active Directory 조건부 액세스 설정 참조</span><span class="sxs-lookup"><span data-stu-id="fb2ac-289">Azure Active Directory conditional access settings reference</span></span>](/azure/active-directory/conditional-access/technical-reference)</li></ul></ul>|
|||


### <a name="education-edu"></a><span data-ttu-id="fb2ac-290">교육(EDU)</span><span class="sxs-lookup"><span data-stu-id="fb2ac-290">Education (EDU)</span></span> 

<span data-ttu-id="fb2ac-291">교육 분야에 종사하는 IT 전문가는 학생, 교직원 및 다양한 비즈니스 관련 교육 별 시나리오를 충족시키기 위해 맞춤화된 다양한 기능을 제공하는 교육용 Teams를 활용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb2ac-291">IT pros working in education can take advantage of Teams for Education, which comes with a number of capabilities that have been tailored to meet education-specific scenarios for students, faculty, and the wider business.</span></span>

| <span data-ttu-id="fb2ac-292">본인에게 질의하기</span><span class="sxs-lookup"><span data-stu-id="fb2ac-292">Ask yourself</span></span> | <span data-ttu-id="fb2ac-293">작업</span><span class="sxs-lookup"><span data-stu-id="fb2ac-293">Action</span></span> |
|--------------|--------|
|<span data-ttu-id="fb2ac-294">EDU 별 Teams 템플릿을 사용해야 되나요?</span><span class="sxs-lookup"><span data-stu-id="fb2ac-294">Will I use EDU-specific Teams templates?</span></span> |<span data-ttu-id="fb2ac-295">교육용 Teams에 대한 자세한 내용은 [관리자용 Microsoft 교육 거버넌스 FAQ를 참조하세요](plan-teams-governance-edu.md).</span><span class="sxs-lookup"><span data-stu-id="fb2ac-295">To learn more about Teams for Education, see [Microsoft Education governance FAQ for admins](plan-teams-governance-edu.md).</span></span>|
|<span data-ttu-id="fb2ac-296">범위 검색을 배포해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="fb2ac-296">Will I deploy scoped search?</span></span>|<span data-ttu-id="fb2ac-297">EDU용 Teams를 설정하려면 [퀵 스타트 - 교육 관리자용 Teams](teams-quick-start-edu.yml)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fb2ac-297">To set up Teams for EDU, see [Quickstart - Teams for Education admins](teams-quick-start-edu.yml).</span></span>|
|<span data-ttu-id="fb2ac-298">Teams를 School Data Sync 서비스와 통합하여 사용자 계정을 제공하나요?</span><span class="sxs-lookup"><span data-stu-id="fb2ac-298">Will I integrate Teams with the School Data Sync service to provision user accounts?</span></span>|[<span data-ttu-id="fb2ac-299">교육 관리자용 Teams 리소스</span><span class="sxs-lookup"><span data-stu-id="fb2ac-299">Teams resources for Education admins</span></span>](resources-teams-edu.md)|
|||

### <a name="government---gcc-considerations"></a><span data-ttu-id="fb2ac-300">정부 - GCC 고려사항</span><span class="sxs-lookup"><span data-stu-id="fb2ac-300">Government - GCC considerations</span></span>

<span data-ttu-id="fb2ac-301">정부 기관용 Office 365의 사용 - GCC(정부 커뮤니티 클라우드)는 정부의 규정 및 요건을 적용 받는 미국 연방, 주, 지역적,부족적 혹은 영토적 정부 기관 혹은 기타 기관에서 Office 365의 배포를 진행하는 IT 전문가의 요구 사항을 충족하는 데 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="fb2ac-301">The use of Office 365 for Government - GCC (Government Community Cloud) is appropriate to meet the requirements of IT pros who are driving deployments of Office 365 in US federal, state, local, tribal, or territorial government entities or other entities that handle data that's subject to government regulations and requirements.</span></span>

| <span data-ttu-id="fb2ac-302">본인에게 질의하기</span><span class="sxs-lookup"><span data-stu-id="fb2ac-302">Ask yourself</span></span> | <span data-ttu-id="fb2ac-303">작업</span><span class="sxs-lookup"><span data-stu-id="fb2ac-303">Action</span></span> |
|--------------|--------|
| <span data-ttu-id="fb2ac-304">정부 기관용 Office 365 - GCC 환경에서 Teams를 배포해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="fb2ac-304">Will I need to deploy Teams in a Office 365 for Government – GCC environment?</span></span> | <span data-ttu-id="fb2ac-305">배포 관련 고려 사항은 [Office 365 정부 - GCC 배포 계획](plan-for-government-gcc.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fb2ac-305">For deployment considerations, see [Plan for Office 365 Government - GCC deployments](plan-for-government-gcc.md).</span></span>|
|||

## <a name="next-steps"></a><span data-ttu-id="fb2ac-306">다음 단계</span><span class="sxs-lookup"><span data-stu-id="fb2ac-306">Next steps</span></span>
- <span data-ttu-id="fb2ac-307">채팅, 팀, 채널 & 앱의 [도입을 진행합니다](adopt-microsoft-teams-landing-page.md).</span><span class="sxs-lookup"><span data-stu-id="fb2ac-307">[Drive adoption](adopt-microsoft-teams-landing-page.md) of chat, teams, channels, & apps.</span></span>
- <span data-ttu-id="fb2ac-p121">초기 Teams 배포에 플래너와 같은 응용프로그램을 포함합니다. Teams 도입을 추진할 때 다른 [개의 애플리케이션, 봇 및 커넥터](deploy-apps-microsoft-teams-landing-page.md)를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="fb2ac-p121">Include featured apps - such as Planner - in your initial Teams rollout. Add other [apps, bots, & connectors](deploy-apps-microsoft-teams-landing-page.md) as you drive Teams adoption.</span></span>
- [<span data-ttu-id="fb2ac-310">모임 및 회의 출시</span><span class="sxs-lookup"><span data-stu-id="fb2ac-310">Roll out meetings & conferencing</span></span>](deploy-meetings-microsoft-teams-landing-page.md)
- [<span data-ttu-id="fb2ac-311">클라우드 음성 출시</span><span class="sxs-lookup"><span data-stu-id="fb2ac-311">Roll out cloud voice</span></span>](cloud-voice-landing-page.md)