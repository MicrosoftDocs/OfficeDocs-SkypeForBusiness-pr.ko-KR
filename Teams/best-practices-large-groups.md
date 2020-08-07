---
title: Microsoft 팀에서 대규모 팀 관리-모범 사례
ms.reviewer: abgupta
author: lolaj
ms.author: serdars
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
description: 조직의 요구 사항에 맞게 Microsoft 팀의 대규모 팀을 관리 하는 모범 사례에 대해 알아봅니다.
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 90345578ceb6bbf8d8752b561511d8df85023bf1
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/06/2020
ms.locfileid: "46582665"
---
<a name="manage-large-teams-in-microsoft-teams---best-practices"></a><span data-ttu-id="57082-103">Microsoft 팀에서 대규모 팀 관리-모범 사례</span><span class="sxs-lookup"><span data-stu-id="57082-103">Manage large teams in Microsoft Teams - Best practices</span></span>
======================================================

<span data-ttu-id="57082-104">Microsoft 팀은 구성원이 수십 명이 고 수천 명의 구성원이 포함 된 대규모 그룹 간의 의사 소통을 원활 하 게 합니다.</span><span class="sxs-lookup"><span data-stu-id="57082-104">Microsoft Teams is equally effective at facilitating communications between small groups with dozens of members and large groups with thousands of members.</span></span> <span data-ttu-id="57082-105">팀 크기에 대 한 업데이트 [팀의 제한 사항 및 사양을](limits-specifications-teams.md) 검토 합니다.</span><span class="sxs-lookup"><span data-stu-id="57082-105">Review [Limits and specifications for Teams](limits-specifications-teams.md) for updates on team sizes.</span></span> <span data-ttu-id="57082-106">팀 크기가 증가 하 여 고유한 관리 및 운영 과제가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="57082-106">Increase in team size leads to unique management and operational challenges.</span></span> <span data-ttu-id="57082-107">이 문서에서는 수천 명의 구성원으로 구성 된 대규모 팀을 만들고 관리 하는 모범 사례에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="57082-107">This article describes best practices for creating and managing large teams comprised of thousands of members.</span></span>

## <a name="value-of-large-teams"></a><span data-ttu-id="57082-108">대규모 팀의 가치</span><span class="sxs-lookup"><span data-stu-id="57082-108">Value of large teams</span></span>

<span data-ttu-id="57082-109">대규모 팀은 다음과 같은 공동 작업 시나리오를 사용 하는 데 매우 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="57082-109">Large teams are very useful in enabling the following collaboration scenarios:</span></span>

- <span data-ttu-id="57082-110">**부서 전체 공동 작업**: 조직에 재무, 운영, R&D 등의 부서가 여러 개 있는 경우 특정 부서의 모든 구성원을 포함 하는 단일 팀을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57082-110">**Department-wide collaboration**: If your organization has multiple departments such as Finance, Operations, R&D etc., then you can create a single team that includes all members in a specific department.</span></span> <span data-ttu-id="57082-111">이제 부서와 관련 된 모든 통신을이 팀에서 공유 하 여 인스턴트에 도달 하 고 회원의 참여를 쉽게 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57082-111">Now all communications relevant to a department can be shared in this team, which facilitates instant reach and engagement from members.</span></span>

- <span data-ttu-id="57082-112">**직원 리소스 그룹의 공동 작업**: 조직에서 다른 부서나 회사 그룹에 속한 상호 관심사를 가진 대규모 사용자 그룹을 보유 하 고 있는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="57082-112">**Collaboration in employee resource groups**: Organizations often have large groups of people with mutual interests who belong to a different department or work group.</span></span> <span data-ttu-id="57082-113">예를 들어 개인 재무 및 투자에 대 한 열정을 공유 하는 사용자 그룹이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57082-113">As an example, there can be a group of people who share a passion for personal finance and investing.</span></span> <span data-ttu-id="57082-114">대규모 조직에서 연결 하는 것이 어려운 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="57082-114">It's often hard to connect in a large organization.</span></span> <span data-ttu-id="57082-115">이러한 그룹에 대 한 커뮤니티를 개발 하기 위해 테 넌 트 관리자는 누구나 참가 하 고 활용할 수 있는 공공 기업 차원의 리소스 그룹 역할을 하는 대규모 팀을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57082-115">To develop communities for such groups, tenant admins can create a large team that serves as a public company-wide resource group that anyone can join and take advantage of.</span></span> <span data-ttu-id="57082-116">결과적으로 이러한 커뮤니티는 신규 및 기존 회원 모두가 즐길 수 있는 정보를 수집 합니다.</span><span class="sxs-lookup"><span data-stu-id="57082-116">Eventually, these communities collect information that both new and existing members can enjoy.</span></span>

- <span data-ttu-id="57082-117">**내부 및 외부 구성원 간의 공동 작업**: 인기 있는 제품은 종종 새로운 제품 릴리스를 시도 하 고 피드백을 제공 하는 초기의 사용자를 위한 커뮤니티를 개발 합니다.</span><span class="sxs-lookup"><span data-stu-id="57082-117">**Collaboration between internal and external members**: Popular products often develop a community of early adopters who are eager to try new product releases and provide feedback.</span></span> <span data-ttu-id="57082-118">초기 성과는 제품 그룹과의 관계를 개발 하 여 제품의 모양을 개선 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="57082-118">Early adopters develop a relationship with product groups to help shape the product.</span></span> <span data-ttu-id="57082-119">이러한 시나리오에서 테 넌 트 관리자는 내부 제품 그룹과 외부 제품 평가자를 모두 포함 하 여 다양 한 제품 개발 프로세스를 촉진 하는 대규모 팀을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57082-119">In such scenarios, tenant admins can set up a large team which includes both internal product groups and external product evaluators to facilitate a rich product development process.</span></span> <span data-ttu-id="57082-120">이러한 팀은 선택 된 고객 집합에 고객 지원을 제공할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57082-120">These teams can also provide customer support to a select set of customers.</span></span>

## <a name="create-teams-from-existing-groups"></a><span data-ttu-id="57082-121">기존 그룹에서 팀 만들기</span><span class="sxs-lookup"><span data-stu-id="57082-121">Create teams from existing groups</span></span>

<span data-ttu-id="57082-122">메일 그룹, 보안 그룹 또는 Office 그룹을 사용 하 여 팀을 빠르게 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="57082-122">Use contact groups, security groups, or Office groups to jump start your team.</span></span> <span data-ttu-id="57082-123">그룹을 가져와 Office 그룹에서 팀을 만들거나 팀을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57082-123">You can import a group to make a team or create a team from an Office group.</span></span>

<span data-ttu-id="57082-124">**그룹을 가져와 팀으로 만들기**: 최대 3500 구성원을 포함 하 여 그룹을 팀에 가져오면 팀에서 그룹의 총 구성원 수를 자동으로 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="57082-124">**Import a group to make a team**: When you import a group with up to 3,500 members into Teams, Teams automatically calculates the total number of members in the group.</span></span> <span data-ttu-id="57082-125">일회성 가져오기 이며 나중에 그룹의 변경 내용이 팀에서 자동으로 업데이트 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="57082-125">This is a one-time import only and future changes in the group will not automatically be updated in Teams.</span></span>

<span data-ttu-id="57082-126">**대규모 microsoft 365 그룹에서 팀 만들기**: 대규모 microsoft 365 그룹에서 팀을 만들면 구성원이 Microsoft 365 그룹 **및** 팀에 자동으로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="57082-126">**Create a team from a large Microsoft 365 group**: When you create a team from a large Microsoft 365 group, members are automatically part of the Microsoft 365 group **and** the team.</span></span> <span data-ttu-id="57082-127">나중에 팀 구성원이 Microsoft 365 그룹에 참가 하거나 탈퇴할 때마다 팀에서 자동으로 추가 되거나 제거 됩니다.</span><span class="sxs-lookup"><span data-stu-id="57082-127">In the future, as team members join or leave the Microsoft 365 group, they're automatically added or removed from the team.</span></span>

## <a name="create-channels-to-focus-discussions"></a><span data-ttu-id="57082-128">토론에 집중할 채널 만들기</span><span class="sxs-lookup"><span data-stu-id="57082-128">Create channels to focus discussions</span></span>

<span data-ttu-id="57082-129">중요 한 채널을 만들어 그룹 토론의 범위를 좁힐 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57082-129">You can narrow the group discussions by creating focused channels.</span></span> <span data-ttu-id="57082-130">[팀 구성에 대 한 모범 사례를](best-practices-organizing.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="57082-130">See [Best practices for organizing teams](best-practices-organizing.md).</span></span>

## <a name="restrict-channel-creation"></a><span data-ttu-id="57082-131">채널 만들기 제한</span><span class="sxs-lookup"><span data-stu-id="57082-131">Restrict channel creation</span></span>

<span data-ttu-id="57082-132">팀 멤버가 채널을 만들 수 있도록 허용 된 경우 해당 팀은 채널 sprawl를 가질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57082-132">If any team member is allowed to create channels, that team can have channel sprawl.</span></span> <span data-ttu-id="57082-133">팀 소유자는 **구성원 권한에 대 한 설정 >** 구성원에 대 한 채널 만들기, 업데이트, 삭제 및 복원 기능을 해제 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="57082-133">Team owners should turn off channel create, update, delete, and restore for members in **Settings > Member permissions**.</span></span> <span data-ttu-id="57082-134">[팀 및 채널 개요](teams-channels-overview.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="57082-134">See [Overview of teams and channels](teams-channels-overview.md).</span></span>

<span data-ttu-id="57082-135">![관리 콘솔 설정 탭의 구성원 권한 섹션을 표시 하는 화면 이미지입니다.](media/no-channel-creation.png "관리 콘솔 설정 탭의 구성원 권한 섹션 화면 이미지 구성원에 게 채널을 만들거나 삭제할 수 있음 옵션이 선택 되어 있지 않습니다.")</span><span class="sxs-lookup"><span data-stu-id="57082-135">![Screen image that shows the member permissions section of the admin console Settings tab.](media/no-channel-creation.png "Screen image that member permissions section of the admin console Settings tab. The allow members to create or delete channels options are unchecked.")</span></span>

## <a name="add-favorite-channels"></a><span data-ttu-id="57082-136">즐겨찾기 채널 추가</span><span class="sxs-lookup"><span data-stu-id="57082-136">Add favorite channels</span></span>

<span data-ttu-id="57082-137">새 사용자 참여 및 콘텐츠 검색의 속도를 높이기 위해 기본적으로 사용자에 게 제공 되는 즐겨찾기 채널을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57082-137">In order to speed up new user engagement and content discovery, you can select favorite channels that are available to the user by default.</span></span> <span data-ttu-id="57082-138">관리 센터의 **채널** 창에서 **구성원에 대해 표시** 열 아래에 있는 채널을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="57082-138">In the **Channels** pane of the admin center, check the channels under the **Show for members** column.</span></span>

<span data-ttu-id="57082-139">![관리 콘솔의 채널 창을 표시 하는 화면 이미지입니다.](media/favorite-channels.png "관리 콘솔의 채널 창을 표시 하는 화면 이미지입니다. 일부 채널은 구성원에 대해 확인을 선택 합니다.")</span><span class="sxs-lookup"><span data-stu-id="57082-139">![Screen image that shows the channels pane of the admin console.](media/favorite-channels.png "Screen image that shows channels pane of the admin console. Some channels are checked for Show for members.")</span></span>

 <span data-ttu-id="57082-140">자세한 내용은 [첫 번째 팀 및 채널 만들기](get-started-with-teams-create-your-first-teams-and-channels.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="57082-140">See [Create your first teams and channels](get-started-with-teams-create-your-first-teams-and-channels.md) for details.</span></span>

## <a name="regulate-applications-and-bots-in-large-teams"></a><span data-ttu-id="57082-141">대규모 팀의 응용 프로그램 및 인공 지능 규정</span><span class="sxs-lookup"><span data-stu-id="57082-141">Regulate applications and bots in large teams</span></span>

<span data-ttu-id="57082-142">팀 소유자는 방해가 되는 응용 프로그램 또는 인공 지능 추가를 방지 하기 위해 팀 구성원에 대 한 앱 및 커넥터를 비활성화, 추가, 제거, 업로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57082-142">To prevent addition of distracting applications or bots, team owners can disable, add, remove, and upload apps and connectors for team members.</span></span> <span data-ttu-id="57082-143">관리 센터의 **설정 > 구성원 권한**에서 구성원이 앱 또는 커넥터를 추가할 수 있도록 허용 하는 세 가지 옵션의 선택을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="57082-143">In the admin center under **Settings > Member permissions**, uncheck the three options that allow members to add apps or connectors.</span></span>

<span data-ttu-id="57082-144">![설정 창의 구성원 권한 섹션을 보여 주는 화면 이미지입니다.](media/disable-bots-connectors.png "설정 창의 구성원 권한 섹션을 보여 주는 화면 이미지입니다. 구성원이 앱 또는 커넥터를 추가할 수 있도록 허용 하는 옵션이 선택 되어 있지 않습니다.")</span><span class="sxs-lookup"><span data-stu-id="57082-144">![Screen image that shows the Member permissions section of the Settings pane.](media/disable-bots-connectors.png "Screen image that shows the Member permission section of the Settings pane. The options for allow members to add apps or connectors are unchecked.")</span></span>

<span data-ttu-id="57082-145">[앱, 인공 & 커넥터를](deploy-apps-microsoft-teams-landing-page.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="57082-145">See [Apps, bots, & connectors](deploy-apps-microsoft-teams-landing-page.md).</span></span>

## <a name="regulate-team-and-channel-mentions"></a><span data-ttu-id="57082-146">팀 및 채널 멘 션 규제</span><span class="sxs-lookup"><span data-stu-id="57082-146">Regulate team and channel mentions</span></span>

<span data-ttu-id="57082-147">팀과 채널 멘 션을 사용 하 여 전체 팀의 주의를 특정 채널 게시물에 그릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57082-147">Team and channel mentions can be used to draw the attention of the whole team to certain channel posts.</span></span> <span data-ttu-id="57082-148">게시물에 멘 션을 사용 하면 수천 명의 팀 구성원에 게 알림이 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="57082-148">Once a mention is used in a post, a notification is sent to thousands of team members.</span></span> <span data-ttu-id="57082-149">알림이 너무 자주 발생 하는 경우 팀 구성원이 오버 로드 되 고 팀 소유자에 게 문제가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57082-149">If the notifications are too frequent, then team members can become overloaded and might complain to team owners.</span></span> <span data-ttu-id="57082-150">팀 또는 채널 멘 션을 방지 하려면 팀 **설정 > @mentions** 창에서 확인란의 선택을 취소 하 여 구성원에 대 한 팀 및 채널 멘 션을 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="57082-150">To prevent team or channel mentions, turn off team and channel mentions for members by unchecking the boxes in the teams **Settings > @mentions** pane.</span></span>

<span data-ttu-id="57082-151">![설정 창의 at 멘 션 섹션을 표시 하는 화면 이미지](media/no-at-mentions.png "설정 창의 at 멘 션 섹션을 표시 하는 화면 이미지 회원에 게 액세스를 표시 하 고 부여 하는 옵션은 선택 되어 있지 않습니다.")</span><span class="sxs-lookup"><span data-stu-id="57082-151">![Screen image that shows the at Mentions section of the Settings pane.](media/no-at-mentions.png "Screen image that shows the at Mentions section of the Settings pane. The options for show and give members access to at mentions are unchecked.")</span></span>

## <a name="consider-setting-up-moderation-in-your-channels"></a><span data-ttu-id="57082-152">채널에서 중재 설정 고려하기</span><span class="sxs-lookup"><span data-stu-id="57082-152">Consider setting up moderation in your channels</span></span>

<span data-ttu-id="57082-153">팀 소유자는 채널에 대한 중재를 설정하여 해당 채널에서 새 게시물을 시작하고 채널의 게시물에 회신할 수 있는 사용자를 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57082-153">Team owners can turn on moderation for a channel to control who can start new posts and reply to posts in that channel.</span></span> <span data-ttu-id="57082-154">중재를 설정할 때 한 명 이상의 팀 구성원을 선택하여 중재자로 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57082-154">When you set up moderation, you can choose one or more team members to be moderators.</span></span> <span data-ttu-id="57082-155">팀 소유자는 기본적으로 중재자입니다.</span><span class="sxs-lookup"><span data-stu-id="57082-155">Team owners are moderators by default.</span></span> <span data-ttu-id="57082-156">자세한 내용은 [채널 중재 설정 및 관리](manage-channel-moderation-in-teams.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="57082-156">For more information, see [Set up and manage channel moderation](manage-channel-moderation-in-teams.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="57082-157">관련 항목</span><span class="sxs-lookup"><span data-stu-id="57082-157">Related topics</span></span>

- [<span data-ttu-id="57082-158">팀 구성 모범 사례</span><span class="sxs-lookup"><span data-stu-id="57082-158">Best practices for organizing Teams</span></span>](best-practices-organizing.md)
- [<span data-ttu-id="57082-159">조직 전체 팀 만들기</span><span class="sxs-lookup"><span data-stu-id="57082-159">Create an org-wide team</span></span>](create-an-org-wide-team.md)
