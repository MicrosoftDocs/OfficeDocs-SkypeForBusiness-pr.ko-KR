---
title: 채널 중재 설정 및 관리
author: cichur
ms.author: v-cichur
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
description: 팀 구성원을 채널 중재자로 추가하는 방법을 포함하여 Microsoft Teams에서 중재를 위해 채널을 설정하는 방법에 대해 자세히 알아보습니다.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 81e5159cf0e64a4c5b88afea51de528c299daf80
ms.sourcegitcommit: a731226d62d8b23fe73bd7bf61654e16367fbd90
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2021
ms.locfileid: "51948644"
---
# <a name="set-up-and-manage-channel-moderation-in-microsoft-teams"></a><span data-ttu-id="6f4a0-103">Microsoft Teams에서 채널 중재 설정 및 관리</span><span class="sxs-lookup"><span data-stu-id="6f4a0-103">Set up and manage channel moderation in Microsoft Teams</span></span>

<span data-ttu-id="6f4a0-104">Microsoft Teams에서 팀 소유자는 표준 채널에 대한 중재를 설정하여 새 게시물을 시작하고 해당 채널의 게시물에 회신할 수 있는 사용자 제어를 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f4a0-104">In Microsoft Teams, team owners can turn on moderation for a standard channel to control who can start new posts and reply to posts in that channel.</span></span>

<span data-ttu-id="6f4a0-105">팀 소유자는 팀 구성원을 중재자로 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f4a0-105">Team owners can also add team members as moderators.</span></span> <span data-ttu-id="6f4a0-106">팀 소유자는 채널 중재를 가장 잘 지원하기 위해 채널 수준에서 주제 전문 지식이 없는 것일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f4a0-106">A team owner might not have the subject matter expertise at the channel level to best support channel moderation.</span></span> <span data-ttu-id="6f4a0-107">특정 팀 구성원이 채널을 중재하도록 허용하면 채널 내에서 콘텐츠 및 컨텍스트를 관리하는 책임은 팀 소유자와 채널 중재자 간에 공유됩니다.</span><span class="sxs-lookup"><span data-stu-id="6f4a0-107">By allowing specific team members to moderate a channel, the responsibility of managing content and context within a channel is shared between team owners and channel moderators.</span></span> <span data-ttu-id="6f4a0-108">예를 들어 팀 소유자는 비즈니스 소유자 또는 콘텐츠 소유자를 중재자로 추가할 수 있습니다. 이를 통해 해당 채널에서 정보 공유를 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f4a0-108">For example, a team owner can add business owners or content owners as moderators, which lets them control information sharing in that channel.</span></span>

> [!NOTE]
> <span data-ttu-id="6f4a0-109">채널 중재는 표준 채널에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f4a0-109">Channel moderation is available for standard channels.</span></span> <span data-ttu-id="6f4a0-110">일반 채널 또는 개인 채널에는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6f4a0-110">It's not available for the General channel or private channels.</span></span>

## <a name="what-can-a-channel-moderator-do"></a><span data-ttu-id="6f4a0-111">채널 중재자는 무엇을 할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="6f4a0-111">What can a channel moderator do?</span></span>

<span data-ttu-id="6f4a0-112">채널 중재자는 다음을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f4a0-112">Channel moderators can:</span></span>

- <span data-ttu-id="6f4a0-113">채널에서 새 게시물을 시작하세요.</span><span class="sxs-lookup"><span data-stu-id="6f4a0-113">Start new posts in the channel.</span></span> <span data-ttu-id="6f4a0-114">채널에 대한 중재가 켜져 있는 경우 중재자만 해당 채널에서 새 게시물을 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f4a0-114">When moderation is turned on for a channel, only moderators can start new posts in that channel.</span></span>
- <span data-ttu-id="6f4a0-115">채널에 팀 구성원을 중재자로 추가하고 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="6f4a0-115">Add and remove team members as moderators to a channel.</span></span> <span data-ttu-id="6f4a0-116">기본적으로 팀 소유자는 채널 중재자이며 제거할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6f4a0-116">Keep in mind that by default, team owners are channel moderators and can't be removed.</span></span>
- <span data-ttu-id="6f4a0-117">팀 구성원이 기존 채널 메시지에 회신할 수 있는지 여부와 봇 및 커넥터가 채널 메시지를 제출할 수 있는지 여부를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="6f4a0-117">Control whether team members can reply to existing channel messages and whether bots and connectors can submit channel messages.</span></span>

## <a name="scenarios"></a><span data-ttu-id="6f4a0-118">시나리오</span><span class="sxs-lookup"><span data-stu-id="6f4a0-118">Scenarios</span></span>

<span data-ttu-id="6f4a0-119">다음은 조직에서 Teams에서 채널 중재를 사용하는 방법에 대한 몇 가지 예입니다.</span><span class="sxs-lookup"><span data-stu-id="6f4a0-119">Here's some examples of how your organization can use channel moderation in Teams.</span></span>

### <a name="use-a-channel-as-an-announcement-channel"></a><span data-ttu-id="6f4a0-120">채널을 공지 채널로 사용</span><span class="sxs-lookup"><span data-stu-id="6f4a0-120">Use a channel as an announcement channel</span></span>

<span data-ttu-id="6f4a0-121">마케팅 팀은 특정 채널을 사용하여 주요 프로젝트 공지사항 및 결과물 공유</span><span class="sxs-lookup"><span data-stu-id="6f4a0-121">The Marketing team uses a specific channel to share key project announcements and deliverables.</span></span> <span data-ttu-id="6f4a0-122">팀 구성원이 다른 채널에 더 적절하게 속하는 채널에 콘텐츠를 게시하는 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f4a0-122">Sometimes team members post content to the channel that more appropriately belongs in other channels.</span></span> <span data-ttu-id="6f4a0-123">팀 소유자는 팀 구성원이 해당 채널을 사용하여 중요한 사항을 계속 유지하도록 채널의 정보 공유를 공지로만 제한하려는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="6f4a0-123">The team owner wants to restrict information sharing in the channel to only announcements so that team members can use that channel to stay on top of what's important.</span></span>

<span data-ttu-id="6f4a0-124">이 시나리오에서 팀 소유자는 마케팅 잠재 고객에 중재자로 추가하여 채널에 공지 사항을 게시하고 팀 구성원이 해당 채널의 메시지에 회신할 수 있는 기능을 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="6f4a0-124">In this scenario, the team owner adds Marketing leads as moderators so they can post announcements in the channel and turns off the ability for team members to reply to messages in that channel.</span></span>

### <a name="use-a-channel-for-class-discussions-in-teams-for-education"></a><span data-ttu-id="6f4a0-125">교육용 Teams에서 수업 토론에 채널 사용</span><span class="sxs-lookup"><span data-stu-id="6f4a0-125">Use a channel for class discussions in Teams for Education</span></span>

<span data-ttu-id="6f4a0-126">Teams for Education에서 과학 교사는 채널을 사용하여 학생들에게 특정 교실 주제에 대한 집중적인 토론에 참여하기를 원합니다.</span><span class="sxs-lookup"><span data-stu-id="6f4a0-126">In Teams for Education, a science teacher wants to use a channel to engage students in focused discussions on specific classroom topics.</span></span>

<span data-ttu-id="6f4a0-127">이 시나리오에서 교사는 교사의 조교가 채널을 중재할 수 있도록 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="6f4a0-127">In this scenario, the teacher allows their teaching assistants to moderate the channel.</span></span> <span data-ttu-id="6f4a0-128">그런 다음, 조교는 새 게시물을 만들어 학생들과 토론을 시작하고 드라이브할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f4a0-128">The teaching assistants can then create new posts to initiate and drive discussions with students.</span></span>

## <a name="manage-channel-moderation"></a><span data-ttu-id="6f4a0-129">채널 중재 관리</span><span class="sxs-lookup"><span data-stu-id="6f4a0-129">Manage channel moderation</span></span>

<span data-ttu-id="6f4a0-130">Teams에서 채널로 이동하여 추가 옵션을 **클릭합니다.**  >  **채널을 관리합니다.**</span><span class="sxs-lookup"><span data-stu-id="6f4a0-130">In Teams, go to the channel, click **More options ...** > **Manage channel**.</span></span> <span data-ttu-id="6f4a0-131">여기에서 중재를 켜고 끄고, 팀 구성원을 중재자로 추가하고, 기본 설정을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f4a0-131">From here you can turn on and turn off moderation, add team members as moderators, and set preferences.</span></span>

<span data-ttu-id="6f4a0-132">채널 중재는 채널당 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="6f4a0-132">Channel moderation is a per-channel setting.</span></span> <span data-ttu-id="6f4a0-133">채널 중재에 대한 테넌트 수준 설정은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6f4a0-133">There's no tenant-level setting for channel moderation.</span></span> <span data-ttu-id="6f4a0-134">테넌트 수준 채널 중재 설정을 추가하고자 하는 경우 [Teams UserVoice에서 요청합니다.](https://microsoftteams.uservoice.com/)</span><span class="sxs-lookup"><span data-stu-id="6f4a0-134">If you'd like us to add a tenant-level channel moderation setting, request it on [Teams UserVoice](https://microsoftteams.uservoice.com/).</span></span>

[!INCLUDE [uservoice-disclaimer-note](includes/uservoice-disclaimer-note.md)]

![채널-중재-팀 관리에 대한 기본 설정](media/manage-channel-moderation-in-teams-preferences.png)

### <a name="turn-on-or-turn-off-moderation-for-a-channel"></a><span data-ttu-id="6f4a0-136">채널에 대한 중재 켜기 또는 해제</span><span class="sxs-lookup"><span data-stu-id="6f4a0-136">Turn on or turn off moderation for a channel</span></span>

<span data-ttu-id="6f4a0-137">기본적으로 중재가 해제되어 팀 소유자 및 팀 구성원에게 일반적인 채널 설정이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6f4a0-137">By default, moderation is off, which means that the usual channel settings apply to team owners and team members.</span></span> <span data-ttu-id="6f4a0-138">예를 들어 팀 구성원만 새 게시물을 제한하거나 게스트를 포함한 모든 사용자가 새 게시물을 시작할 수 있도록 허용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f4a0-138">For example, you can restrict new posts to only team members or allow everyone, including guests, to start new posts.</span></span>

<span data-ttu-id="6f4a0-139">채널에 대한 중재를 켜려면 **채널** 중재에서 를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="6f4a0-139">To turn on moderation for a channel, under **Channel moderation**, click **On**.</span></span> <span data-ttu-id="6f4a0-140">채널 중재가 설정된 경우 중재자만 새 게시물을 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f4a0-140">When channel moderation is on, only moderators can start new posts.</span></span> 

### <a name="add-or-remove-channel-moderators"></a><span data-ttu-id="6f4a0-141">채널 중재자 추가 또는 제거</span><span class="sxs-lookup"><span data-stu-id="6f4a0-141">Add or remove channel moderators</span></span>

<span data-ttu-id="6f4a0-142">중재자는 누구인가요? 에서 관리 **를** 클릭한 다음, 팀 구성원을 중재자로 추가하거나 제거합니다. </span><span class="sxs-lookup"><span data-stu-id="6f4a0-142">Under **Who are the moderators?**, click **Manage**, and then add or remove team members as moderators.</span></span> <span data-ttu-id="6f4a0-143">팀 소유자 및 중재자는 다른 중재자 추가 및 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f4a0-143">Team owners and moderators can add and remove other moderators.</span></span>  

### <a name="set-team-member-permissions"></a><span data-ttu-id="6f4a0-144">팀 구성원 권한 설정</span><span class="sxs-lookup"><span data-stu-id="6f4a0-144">Set team member permissions</span></span>

<span data-ttu-id="6f4a0-145">Team **멤버 권한 아래에서** 허용할 활동 옆에 있는 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6f4a0-145">Under **Team member permissions**, select the check boxes next to the activities  you want to allow.</span></span>

## <a name="related-topics"></a><span data-ttu-id="6f4a0-146">관련 항목</span><span class="sxs-lookup"><span data-stu-id="6f4a0-146">Related topics</span></span>

- [<span data-ttu-id="6f4a0-147">Teams의 팀 및 채널 개요</span><span class="sxs-lookup"><span data-stu-id="6f4a0-147">Overview of teams and channels in Teams</span></span>](teams-channels-overview.md)
