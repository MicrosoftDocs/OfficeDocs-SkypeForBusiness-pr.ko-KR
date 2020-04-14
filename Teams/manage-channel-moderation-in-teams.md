---
title: 채널 중재 설정 및 관리
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: jotaing
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: 팀 구성원을 채널 중재자로 추가 하는 방법을 포함 하 여 Microsoft 팀에서 중재를 위해 채널을 설정 하는 방법에 대해 알아봅니다.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 6cdf6988afb9afbd91c2bfd19ed516c8e8fdf702
ms.sourcegitcommit: 379bfaf6b0584c1ac93341af605f93ab932a442b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/13/2020
ms.locfileid: "43240618"
---
# <a name="set-up-and-manage-channel-moderation-in-microsoft-teams"></a><span data-ttu-id="0d030-103">Microsoft 팀에서 채널 중재 설정 및 관리</span><span class="sxs-lookup"><span data-stu-id="0d030-103">Set up and manage channel moderation in Microsoft Teams</span></span>

<span data-ttu-id="0d030-104">Microsoft 팀에서 팀 소유자는 표준 채널에 대 한 중재를 설정 하 여 새 게시물을 시작 하 고 해당 채널의 게시물에 회신할 수 있는 사용자를 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d030-104">In Microsoft Teams, team owners can turn on moderation for a standard channel to control who can start new posts and reply to posts in that channel.</span></span>

<span data-ttu-id="0d030-105">팀 소유자는 팀 구성원을 중재자로 추가할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d030-105">Team owners can also add team members as moderators.</span></span> <span data-ttu-id="0d030-106">팀 소유자는 채널 수준에 대 한 실무 전문성을 제공 하지 않을 수 있으며 채널 중재를 최적화 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0d030-106">A team owner might not have the subject matter expertise at the channel level to best support channel moderation.</span></span> <span data-ttu-id="0d030-107">특정 팀 멤버가 채널을 중간에 할 수 있도록 허용 하 여 채널 내에서 콘텐츠 및 컨텍스트를 관리 하는 책임은 팀 소유자와 채널 중재자 간에 공유 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0d030-107">By allowing specific team members to moderate a channel, the responsibility of managing content and context within a channel is shared between team owners and channel moderators.</span></span> <span data-ttu-id="0d030-108">예를 들어 팀 소유자는 비즈니스 소유자 또는 콘텐츠 소유자를 중재자로 추가 하 여 해당 채널에서 정보 공유를 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d030-108">For example, a team owner can add business owners or content owners as moderators, which lets them control information sharing in that channel.</span></span>

> [!NOTE]
> <span data-ttu-id="0d030-109">현재는 표준 채널에 대해 채널 중재를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d030-109">Currently, channel moderation is available for standard channels.</span></span> <span data-ttu-id="0d030-110">개인 채널에는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0d030-110">It's not available for private channels.</span></span>

## <a name="what-can-a-channel-moderator-do"></a><span data-ttu-id="0d030-111">채널 중재자는 어떤 작업을 할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="0d030-111">What can a channel moderator do?</span></span>

<span data-ttu-id="0d030-112">채널 중재자는 다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d030-112">Channel moderators can:</span></span>

- <span data-ttu-id="0d030-113">채널에서 새 게시물을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d030-113">Start new posts in the channel.</span></span> <span data-ttu-id="0d030-114">채널에 대 한 중재가 설정 되어 있는 경우 중재자만 해당 채널에서 새 게시물을 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d030-114">When moderation is turned on for a channel, only moderators can start new posts in that channel.</span></span>
- <span data-ttu-id="0d030-115">팀 구성원을 한 채널에 대 한 중재자로 추가 하 고 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d030-115">Add and remove team members as moderators to a channel.</span></span> <span data-ttu-id="0d030-116">기본적으로 팀 소유자는 채널 중재자 이며 제거할 수 없다는 점에 유의 하세요.</span><span class="sxs-lookup"><span data-stu-id="0d030-116">Keep in mind that by default, team owners are channel moderators and can't be removed.</span></span>
- <span data-ttu-id="0d030-117">팀 구성원이 기존 채널 메시지에 회신할 수 있는지 여부와 인공 지능 및 커넥터에서 채널 메시지를 제출할 수 있는 여부를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d030-117">Control whether team members can reply to existing channel messages and whether bots and connectors can submit channel messages.</span></span>

## <a name="scenarios"></a><span data-ttu-id="0d030-118">시나리오</span><span class="sxs-lookup"><span data-stu-id="0d030-118">Scenarios</span></span>

<span data-ttu-id="0d030-119">다음은 조직에서 팀의 채널 중재를 사용 하는 방법에 대 한 몇 가지 예입니다.</span><span class="sxs-lookup"><span data-stu-id="0d030-119">Here's some examples of how your organization can use channel moderation in Teams.</span></span>

### <a name="use-a-channel-as-an-announcement-channel"></a><span data-ttu-id="0d030-120">채널을 알림 채널로 사용</span><span class="sxs-lookup"><span data-stu-id="0d030-120">Use a channel as an announcement channel</span></span>

<span data-ttu-id="0d030-121">마케팅 팀은 특정 채널을 사용 하 여 주요 프로젝트 공지 사항 및 결과물을 공유 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d030-121">The Marketing team uses a specific channel to share key project announcements and deliverables.</span></span> <span data-ttu-id="0d030-122">팀 구성원이 다른 채널에 더 적절 한 콘텐츠를 채널에 게시 하는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d030-122">Sometimes team members post content to the channel that more appropriately belongs in other channels.</span></span> <span data-ttu-id="0d030-123">팀 소유자는 팀 구성원이 해당 채널을 사용 하 여 중요 한 역할을 할 수 있도록 채널의 정보 공유를 알림만 제한 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d030-123">The team owner wants to restrict information sharing in the channel to only announcements so that team members can use that channel to stay on top of what's important.</span></span>

<span data-ttu-id="0d030-124">이 시나리오에서 팀 소유자는 마케팅 잠재 고객을 중재자로 추가 하 여 채널에 알림을 게시 하 고 팀 구성원이 해당 채널의 메시지에 회신 하는 기능을 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d030-124">In this scenario, the team owner adds Marketing leads as moderators so they can post announcements in the channel and turns off the ability for team members to reply to messages in that channel.</span></span>

### <a name="use-a-channel-for-class-discussions-in-teams-for-education"></a><span data-ttu-id="0d030-125">교육 팀에서 수업 토론을 위해 채널 사용</span><span class="sxs-lookup"><span data-stu-id="0d030-125">Use a channel for class discussions in Teams for Education</span></span>

<span data-ttu-id="0d030-126">교육 팀에서 과학 교사는 채널을 사용 하 여 특정 강의실 주제에 대 한 중요 한 토론에 참여 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d030-126">In Teams for Education, a science teacher want to use a channel to engage students in focused discussions on specific classroom topics.</span></span>

<span data-ttu-id="0d030-127">이 시나리오에서 교사는 해당 조교의 교육 도우미를 사용 하 여 채널을 중간에 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d030-127">In this scenario, the teacher allows their teaching assistants to moderate the channel.</span></span> <span data-ttu-id="0d030-128">그런 다음 교육 도우미가 학생 들과 함께 토론을 시작 하 고 드라이브를 만드는 새 게시물을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d030-128">The teaching assistants can then create new posts to initiate and drive discussions with students.</span></span>

## <a name="manage-channel-moderation"></a><span data-ttu-id="0d030-129">채널 중재 관리</span><span class="sxs-lookup"><span data-stu-id="0d030-129">Manage channel moderation</span></span>

<span data-ttu-id="0d030-130">팀에서 채널로 이동 하 고 **기타 옵션 ...** 을 클릭 합니다.  >  **채널을 관리**합니다.</span><span class="sxs-lookup"><span data-stu-id="0d030-130">In Teams, go to the channel, click **More options ...** > **Manage channel**.</span></span> <span data-ttu-id="0d030-131">여기서는 중재 기능을 설정 및 해제 하 고 팀 구성원을 중재자로 추가 하 고 기본 설정을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d030-131">From here you can turn on and turn off moderation, add team members as moderators, and set preferences.</span></span>

<span data-ttu-id="0d030-132">채널 중재는 채널 별로 설정 된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="0d030-132">Channel moderation is a per-channel setting.</span></span> <span data-ttu-id="0d030-133">채널 중재에 대 한 테 넌 트 수준 설정은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0d030-133">There's no tenant-level setting for channel moderation.</span></span> <span data-ttu-id="0d030-134">테 넌 트 수준 채널 중재 설정을 추가 하려면 [팀 UserVoice](https://microsoftteams.uservoice.com/)에 요청 하세요.</span><span class="sxs-lookup"><span data-stu-id="0d030-134">If you'd like us to add a tenant-level channel moderation setting, request it on [Teams UserVoice](https://microsoftteams.uservoice.com/).</span></span>

![manage-channel-moderation-in-teams-preferences](media/manage-channel-moderation-in-teams-preferences.png)

### <a name="turn-on-or-turn-off-moderation-for-a-channel"></a><span data-ttu-id="0d030-136">채널에 대 한 중재 설정 또는 해제</span><span class="sxs-lookup"><span data-stu-id="0d030-136">Turn on or turn off moderation for a channel</span></span>

<span data-ttu-id="0d030-137">기본적으로 중재는 해제 되어 있으며,이는 일반적인 채널 설정이 팀 소유자 및 팀 구성원에 게 적용 됨을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d030-137">By default, moderation is off, which means that the usual channel settings apply to team owners and team members.</span></span> <span data-ttu-id="0d030-138">예를 들어 새 게시물을 팀 구성원 으로만 제한 하거나 게스트를 포함 하 여 모든 사용자가 새 게시물을 시작 하도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d030-138">For example, you can restrict new posts to only team members or allow everyone, including guests, to start new posts.</span></span>

<span data-ttu-id="0d030-139">채널에 대 한 중재를 설정 하려면 **채널 중재** **에서 설정을 클릭 합니다**.</span><span class="sxs-lookup"><span data-stu-id="0d030-139">To turn on moderation for a channel, under **Channel moderation**, click **On**.</span></span> <span data-ttu-id="0d030-140">채널 중재가 설정 되어 있는 경우 중재자만 새 게시물을 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d030-140">When channel moderation is on, only moderators can start new posts.</span></span> 

### <a name="add-or-remove-channel-moderators"></a><span data-ttu-id="0d030-141">채널 중재자 추가 또는 제거</span><span class="sxs-lookup"><span data-stu-id="0d030-141">Add or remove channel moderators</span></span>

<span data-ttu-id="0d030-142">**중재자**인 경우 **관리**를 클릭 한 다음 팀 구성원을 중재자로 추가 하거나 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d030-142">Under **Who are the moderators?**, click **Manage**, and then add or remove team members as moderators.</span></span> <span data-ttu-id="0d030-143">팀 소유자와 중재자는 다른 중재자를 추가 하 고 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d030-143">Team owners and moderators can add and remove other moderators.</span></span>  

### <a name="set-team-member-permissions"></a><span data-ttu-id="0d030-144">팀 구성원 권한 설정</span><span class="sxs-lookup"><span data-stu-id="0d030-144">Set team member permissions</span></span>

<span data-ttu-id="0d030-145">**팀 구성원 권한**에서 허용 하려는 작업 옆에 있는 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d030-145">Under **Team member permissions**, select the check boxes next to the activities  you want to allow.</span></span>

## <a name="related-topics"></a><span data-ttu-id="0d030-146">관련 항목</span><span class="sxs-lookup"><span data-stu-id="0d030-146">Related topics</span></span>

- [<span data-ttu-id="0d030-147">Teams의 팀 및 채널 개요</span><span class="sxs-lookup"><span data-stu-id="0d030-147">Overview of teams and channels in Teams</span></span>](teams-channels-overview.md)
