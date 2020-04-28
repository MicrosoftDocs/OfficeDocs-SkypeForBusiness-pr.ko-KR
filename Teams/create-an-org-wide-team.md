---
title: Microsoft Teams에서 조직 전체 팀 만들기
author: LanaChin
ms.author: v-lanac
ms.reviewer: phlouie
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 팀에서 조직 전체 팀을 만들고 관리 하 여 중소 규모 조직의 모든 사용자에 게 자동으로 공동 작업할 수 있는 방법을 제공 하는 방법에 대해 알아봅니다.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 41d7241cc0ffddf1042a3fe46f75def76c1ccf04
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/27/2020
ms.locfileid: "43903033"
---
# <a name="create-an-org-wide-team-in-microsoft-teams"></a><span data-ttu-id="1bb43-103">Microsoft Teams에서 조직 전체 팀 만들기</span><span class="sxs-lookup"><span data-stu-id="1bb43-103">Create an org-wide team in Microsoft Teams</span></span>

<span data-ttu-id="1bb43-104">조직 전체 팀은 중소규모 조직에 속한 모든 사용자에게 공동 작업을 위한 단일 팀의 일원이 될 수 있도록 자동적인 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="1bb43-104">Org-wide teams provide an automatic way for everyone in a small to medium-sized organization to be a part of a single team for collaboration.</span></span>

<span data-ttu-id="1bb43-105">조직 전체 팀을 사용하여 전역 관리자는 조직의 모든 사용자를 가져오고 사용자가 조직에 참여하고 나갈 때 Active Directory를 사용하여 구성원을 최신 상태로 유지하는 공개 팀을 쉽게 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1bb43-105">With org-wide teams, global admins can easily create a public team that pulls in every user in the organization and keeps the membership up to date with Active Directory as users join and leave the organization.</span></span> <span data-ttu-id="1bb43-106">전역 관리자만 조직 전체 팀을 만들 수 있으며 현재 조직 전체 팀은 사용자 수가 5,000명 이하인 조직으로 제한되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1bb43-106">Only global admins can create org-wide teams and currently an org-wide team is limited to organizations with no more than 5,000 users.</span></span> <span data-ttu-id="1bb43-107">테넌트 당 조직 전체 팀의 수도 5개로 제한되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1bb43-107">There's also a limit of five org-wide teams per tenant.</span></span> <span data-ttu-id="1bb43-108">이러한 요구 사항을 충족하는 경우 전역 관리자가 팀을 만드는 과정에서 **팀을 처음부터 구축**을 선택할 때 **조직 전체**를 옵션으로 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1bb43-108">If these requirements are met, global admins will see **Org-wide** as an option when they select **Build a team from scratch** when creating a team.</span></span> 

<span data-ttu-id="1bb43-109">![조직 전체 팀을 만들기 위한 조직 전체 옵션의 스크린샷](media/create-org-wide-team.png "조직 전체 팀을 만들기 위한 조직 전체 옵션의 스크린샷")</span><span class="sxs-lookup"><span data-stu-id="1bb43-109">![Screenshot of the Org-wide option to create an org-wide team](media/create-org-wide-team.png "Screen shot of the Org-wide option to create an org-wide team")</span></span>

<span data-ttu-id="1bb43-110">조직 전체 팀이 만들어지면 모든 전역 관리자가 팀 소유자로 추가되고 모든 활성 사용자가 팀 구성원으로 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="1bb43-110">When an org-wide team is created, all global admins are added as team owners and all active users are added as team members.</span></span> <span data-ttu-id="1bb43-111">라이선스가 없는 사용자도 팀에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="1bb43-111">Unlicensed users are also added to the team.</span></span> <span data-ttu-id="1bb43-112">라이선스가 없는 사용자가 처음으로 Teams에 로그인하면 사용자에게 Microsoft Teams 상업적 클라우드 평가판 라이선스가 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="1bb43-112">The first time an unlicensed user signs in to Teams, the user is assigned a Microsoft Teams Commercial Cloud Trial license.</span></span> <span data-ttu-id="1bb43-113">평가판 라이선스에 대한 자세한 내용은 [Teams 상업적 클라우드 평가판 제품](iw-trial-teams.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1bb43-113">To learn more about the trial license, check out [Manage the Teams Commercial Cloud Trial offer](iw-trial-teams.md).</span></span> 

<span data-ttu-id="1bb43-114">다음 유형의 계정은 조직 전체 팀에 추가할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1bb43-114">These types of accounts won't be added to your org-wide team:</span></span>

- <span data-ttu-id="1bb43-115">로그인이 차단된 계정</span><span class="sxs-lookup"><span data-stu-id="1bb43-115">Accounts that are blocked from sign in</span></span>
- <span data-ttu-id="1bb43-116">게스트 사용자</span><span class="sxs-lookup"><span data-stu-id="1bb43-116">Guest users</span></span>
- <span data-ttu-id="1bb43-117">서비스 계정</span><span class="sxs-lookup"><span data-stu-id="1bb43-117">Service accounts</span></span>
- <span data-ttu-id="1bb43-118">회의실 또는 장비 계정</span><span class="sxs-lookup"><span data-stu-id="1bb43-118">Room or equipment accounts</span></span>
- <span data-ttu-id="1bb43-119">공유 사서함으로 지원되는 계정</span><span class="sxs-lookup"><span data-stu-id="1bb43-119">Accounts backed by a shared mailbox</span></span>

<span data-ttu-id="1bb43-120">조직의 디렉토리가 새 활성 사용자를 포함하도록 업데이트된 경우 또는 사용자가 회사에서 더 이상 일하지 않고 계정이 비활성화된 경우 변경 내용이 자동으로 동기화되고 팀에서 사용자가 추가 또는 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="1bb43-120">As your organization's directory is updated to include new active users or if users no longer work at your company and their account is disabled, changes are automatically synced and the users are added or removed from the team.</span></span> <span data-ttu-id="1bb43-121">팀 구성원은 조직 전체 팀에서 나갈 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1bb43-121">Team members can't leave an org-wide team.</span></span> <span data-ttu-id="1bb43-122">팀 소유자는 필요한 경우 수동으로 사용자를 추가하거나 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1bb43-122">As a team owner, you can manually add or remove users if needed.</span></span>

> [!NOTE]
> - <span data-ttu-id="1bb43-123">전역 관리자로서 팀을 만들 때 **조직 전체** 옵션이 표시되지 않는 경우 이 기능이 아직 배포 중이거나, 조직 전체 팀 개수 제한인 5개에 도달했거나, 조직 구성원의 수가 현재 크기 제한인 5,000명을 넘어서는 경우일 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="1bb43-123">If you don't see the **Org-wide** option when creating a team and you're a global admin, the feature might still be rolling out, you have reached the five org-wide teams limit, or your organization might have more than the current size limit of 5,000 members.</span></span> <span data-ttu-id="1bb43-124">향후에는 이 제한을 높이도록 노력하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1bb43-124">We're looking to increase this limit in the future.</span></span> <span data-ttu-id="1bb43-125">조직 전체 팀은 아직 교육용 Teams에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1bb43-125">Org-wide teams aren't yet available for Teams for Education.</span></span>
> - <span data-ttu-id="1bb43-126">대화방 목록, 장비 및 리소스 계정에 속하지 않는 대화방은 조직 전체 팀에 추가 하거나 동기화 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1bb43-126">Rooms that aren't a part of a room list, equipment, and resource accounts might be added or synced to the org-wide team.</span></span> <span data-ttu-id="1bb43-127">팀 소유자는 팀에서 이러한 계정을 쉽게 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1bb43-127">Team owners can easily remove these accounts from the team.</span></span>
> - <span data-ttu-id="1bb43-128">시스템에서 구성원을 추가하거나 제거하는 모든 작업이 일반 채널에 게시됩니다.</span><span class="sxs-lookup"><span data-stu-id="1bb43-128">All actions by the system to add or remove members are posted in the General channel.</span></span> <span data-ttu-id="1bb43-129">채널은 또한 Teams 클라이언트에 새 활동이 있는 것으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="1bb43-129">The channel will also be marked as having new activity in the Teams client.</span></span>
> - <span data-ttu-id="1bb43-130">조직이 Teams를 처음 사용하고 5,000명 이하의 사용자를 보유한 경우 조직 전체 팀을 자동으로 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="1bb43-130">We'll automatically create an org-wide team for your organization if your organization is new to Teams and has no more than 5,000 users.</span></span> <span data-ttu-id="1bb43-131">팀 이름은 테넌트 이름을 반영하고 일반 채널을 갖게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1bb43-131">The team name will reflect the tenant name and will have a General channel.</span></span> <span data-ttu-id="1bb43-132">전역 관리자는 여느 팀처럼 이 팀을 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1bb43-132">Global admins can edit this team like any other team.</span></span> 

## <a name="best-practices"></a><span data-ttu-id="1bb43-133">모범 사례</span><span class="sxs-lookup"><span data-stu-id="1bb43-133">Best practices</span></span>

<span data-ttu-id="1bb43-134">조직 전체 팀을 최대한 활용하려면 팀 소유자가 다음을 수행하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="1bb43-134">To get the most out of your org-wide team, we recommend team owners do the following.</span></span>

### <a name="allow-only-team-owners-to-post-to-the-general-channel"></a><span data-ttu-id="1bb43-135">팀 소유자만 일반 채널에 게시하도록 허용</span><span class="sxs-lookup"><span data-stu-id="1bb43-135">Allow only team owners to post to the General channel</span></span>

<span data-ttu-id="1bb43-136">팀 소유자만 일반 채널에 게시하여 채널 "소음"을 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1bb43-136">Reduce channel noise by having only team owners post to the General channel.</span></span> <span data-ttu-id="1bb43-137">팀으로 이동하여 **̇ ̇ ̇ 추가 옵션** > **팀 관리**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1bb43-137">Go to the team and click **˙˙˙ More options** > **Manage Team**.</span></span> <span data-ttu-id="1bb43-138">**설정** 탭에서 **구성원 사용 권한** 클릭 > **소유자만 메시지를 게시할 수 있음**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1bb43-138">On the **Settings** tab, click **Member permissions** > select **Only owners can post messages**.</span></span>

### <a name="turn-off-team-and-team-name-mentions"></a><span data-ttu-id="1bb43-139">@팀 및 @[팀 이름] 멘션 해제</span><span class="sxs-lookup"><span data-stu-id="1bb43-139">Turn off @team and @[team name] mentions</span></span>

 <span data-ttu-id="1bb43-140">전체 조직에 과부하가 되는 것을 방지하기 위해 @멘션을 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="1bb43-140">Reduce @mentions to keep them from overloading the entire organization.</span></span> <span data-ttu-id="1bb43-141">팀으로 이동하여 **̇ ̇ ̇ 추가 옵션** > **팀 관리**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1bb43-141">Go to the team and click **˙˙˙ More options** > **Manage Team**.</span></span> <span data-ttu-id="1bb43-142">설정 탭에서 @멘션 클릭 > **구성원에게 @팀 또는 @[팀 이름] 옵션 표시**를 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="1bb43-142">On the **Settings** tab, click <strong>@mentions</strong> > turn off **Show members the option to @team or @[team name]**.</span></span> 

### <a name="automatically-show-important-channels"></a><span data-ttu-id="1bb43-143">중요한 채널 자동 표시</span><span class="sxs-lookup"><span data-stu-id="1bb43-143">Automatically show important channels</span></span>

<span data-ttu-id="1bb43-144">중요한 채널을 표시하여 조직의 모든 사용자가 특정 대화에 참여할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="1bb43-144">Show important channels to ensure everyone in your organization engages in specific conversations.</span></span> <span data-ttu-id="1bb43-145">자세한 내용은 [전체 팀에 대해 채널을 자동으로 즐겨찾기에 추가](https://support.office.com/article/auto-favorite-channels-for-the-whole-team-a948272c-5aa5-429c-863c-4e1e1cd6b0f6)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1bb43-145">To learn more, see [Auto-favorite channels for the whole team](https://support.office.com/article/auto-favorite-channels-for-the-whole-team-a948272c-5aa5-429c-863c-4e1e1cd6b0f6).</span></span> 

### <a name="set-up-channel-moderation"></a><span data-ttu-id="1bb43-146">채널 중재 설정</span><span class="sxs-lookup"><span data-stu-id="1bb43-146">Set up channel moderation</span></span>

<span data-ttu-id="1bb43-147">채널 중재를 설정하고 특정 팀 구성원에게 중재자 역할을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1bb43-147">Consider setting up channel moderation and giving moderator capabilities to certain team members.</span></span> <span data-ttu-id="1bb43-148">(중재가 설정되면 팀 소유자에게 중재자 역할이 자동으로 부여됩니다.) 중재자가 채널에서 새 게시물을 시작할 수 있는 사용자를 제어하고 중재자를 추가 및 제거하며 팀 구성원의 기존 채널 메시지 회신 가능 여부, 봇 및 커넥터에서 채널 메시지의 전송 가능 여부를 제어할 수 있도록 채널 중재를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="1bb43-148">(When moderation is set up, team owners are given moderator capabilities automatically.) Moderators can control who can start a new post in a channel, add and remove moderators, control whether team members can reply to existing channel messages, and control whether bots and connectors can submit channel messages.</span></span> <span data-ttu-id="1bb43-149">자세한 정보는 [Microsoft Teams에서 채널 조정 설정 및 관리](manage-channel-moderation-in-teams.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1bb43-149">For more information, see [Set up and manage channel moderation in Microsoft Teams](manage-channel-moderation-in-teams.md).</span></span>

### <a name="remove-accounts-that-might-not-belong"></a><span data-ttu-id="1bb43-150">소속되지 않은 계정 삭제</span><span class="sxs-lookup"><span data-stu-id="1bb43-150">Remove accounts that might not belong</span></span>

<span data-ttu-id="1bb43-151">구성원이 조직 차원의 팀을 팀 소유자로 남겨둘 수는 없지만 자신이 속해 있지 않은 계정을 제거 하 여 팀 명단을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1bb43-151">Even though members can't leave an org-wide team, as a team owner, you can manage the team roster by removing accounts that don't belong.</span></span> <span data-ttu-id="1bb43-152">**Teams를 사용하여 조직 전체 팀에서 사용자를 제거하도록 합니다**.</span><span class="sxs-lookup"><span data-stu-id="1bb43-152">**Make sure you use Teams to remove users from your org-wide team**.</span></span> <span data-ttu-id="1bb43-153">Microsoft 365 관리 센터 또는 Outlook의 그룹과 같은 다른 방법을 사용하여 사용자를 제거하는 경우 조직 전체 팀에 사용자가 다시 추가될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1bb43-153">If you use another way to remove a user, such as the Microsoft 365 admin center or from a group in Outlook, the user might be added back to the org-wide team.</span></span>

## <a name="faq"></a><span data-ttu-id="1bb43-154">FAQ</span><span class="sxs-lookup"><span data-stu-id="1bb43-154">FAQ</span></span>

### <a name="is-there-a-way-to-create-an-org-wide-team-other-than-using-the-teams-client"></a><span data-ttu-id="1bb43-155">Teams 클라이언트를 사용하지 않고 조직 전체 팀을 만들 수 있는 방법이 있나요?</span><span class="sxs-lookup"><span data-stu-id="1bb43-155">Is there a way to create an org-wide team other than using the Teams client?</span></span>

<span data-ttu-id="1bb43-156">전역 관리자는 Teams 클라이언트를 사용해서만 조직 전체 팀을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1bb43-156">Global admins can only create an org-wide team by using the Teams client.</span></span> <span data-ttu-id="1bb43-157">조직에서 팀 만들기를 PowerShell 사용으로 제한하는 경우 권장되는 해결 방법은 전역 관리자를 팀을 만들 수있는 보안 사용자 그룹에 추가하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="1bb43-157">If your organization limits creating teams to using PowerShell, the recommended workaround is to add your global admins to the security group of users who can create a team.</span></span> <span data-ttu-id="1bb43-158">자세한 내용은 [Microsoft 365 그룹 생성 가능 사용자 관리](https://docs.microsoft.com/office365/admin/create-groups/manage-creation-of-groups)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1bb43-158">For more information, see [Manage who can create Microsoft 365 Groups](https://docs.microsoft.com/office365/admin/create-groups/manage-creation-of-groups).</span></span>

<span data-ttu-id="1bb43-159">이 방식을 사용할 수 없는 경우 PowerShell을 사용하여 공개 팀을 만들고 전역 관리자를 팀 소유자로 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1bb43-159">If this isn't an option, you can use PowerShell to create a public team and add a global admin as the team owner.</span></span> <span data-ttu-id="1bb43-160">그런 다음 전역 관리자가 팀 이름 옆에 있는 **기타 옵션**을 클릭하고 **팀 편집**을 클릭한 다음 개인 정보 보호를 **조직 전체로 변경하면 조직의 모든 사용자가 자동으로 추가됩니다**.</span><span class="sxs-lookup"><span data-stu-id="1bb43-160">Then, have the global admin click **More options** next to the team name, click **Edit team**, and then change the privacy to **Org-wide - Everyone in your organization will be automatically added**.</span></span> <span data-ttu-id="1bb43-161">팀 소유자만 팀 편집 옵션에 액세스할 수 있으며 전역 관리자만 **조직 전체** 옵션을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1bb43-161">Note that only team owners can access the **Edit team** option and only global admins can see the **Org-wide** option.</span></span>

### <a name="is-there-a-way-to-convert-an-existing-team-to-an-org-wide-team"></a><span data-ttu-id="1bb43-162">기존 팀을 조직 전체 팀으로 변환하는 방법이 있나요?</span><span class="sxs-lookup"><span data-stu-id="1bb43-162">Is there a way to convert an existing team to an org-wide team?</span></span>

<span data-ttu-id="1bb43-163">전역 관리자는 Teams 클라이언트에서 기존 팀을 편집하여 조직 전체 팀으로 전환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1bb43-163">Global admins can convert an existing team to an org-wide team by editing it in Teams client.</span></span> <span data-ttu-id="1bb43-164">팀 이름으로 이동하여 **기타 옵션** > **팀 편집**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1bb43-164">Go to the team name, click **More options** > **Edit team**.</span></span>

## <a name="see-also"></a><span data-ttu-id="1bb43-165">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1bb43-165">See also</span></span>

<span data-ttu-id="1bb43-166">[Microsoft Teams에서 회사 전체 팀을 만들기](https://support.office.com/article/037bb27a-bcc9-48fe-8d72-44d9482420a3)에 대한 비디오를 살펴보세요.</span><span class="sxs-lookup"><span data-stu-id="1bb43-166">Watch a video about about [creating a company-wide team in Microsoft Teams](https://support.office.com/article/037bb27a-bcc9-48fe-8d72-44d9482420a3).</span></span>
