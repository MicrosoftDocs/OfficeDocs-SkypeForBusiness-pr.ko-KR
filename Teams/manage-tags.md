---
title: Microsoft 팀의 태그 관리
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: acolonna
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Microsoft 팀에서 조직에 태그를 사용 하는 방법을 관리 하는 방법을 알아봅니다.
ms.openlocfilehash: 5da1d1549e6171656b0065036819be0fac450759
ms.sourcegitcommit: 494e5956619084ff8f0a4f42efb5081c4530488a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2020
ms.locfileid: "42551045"
---
# <a name="manage-tags-in-microsoft-teams"></a><span data-ttu-id="2cc95-103">Microsoft 팀의 태그 관리</span><span class="sxs-lookup"><span data-stu-id="2cc95-103">Manage tags in Microsoft Teams</span></span>

> [!NOTE]
> <span data-ttu-id="2cc95-104">아직 Microsoft 팀 관리 센터에이 기능이 표시 되지 않나요?</span><span class="sxs-lookup"><span data-stu-id="2cc95-104">Don't see this feature in the Microsoft Teams admin center yet?</span></span> <span data-ttu-id="2cc95-105">현재 롤아웃 중 이며 아직 조직에서 사용할 수 없을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2cc95-105">It's currently being rolled out and might not be available in your organization yet.</span></span> <span data-ttu-id="2cc95-106">예정 된 팀 기능을 계속 유지 하려면 [Microsoft 365 로드맵을](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=microsoft%2Cteams)확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="2cc95-106">To stay on top of upcoming Teams features, check out the [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=microsoft%2Cteams).</span></span>

<span data-ttu-id="2cc95-107">Microsoft 팀의 태그를 통해 사용자가 팀의 일부 사용자와 통신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2cc95-107">Tags in Microsoft Teams let users communicate with a subset of people on a team.</span></span> <span data-ttu-id="2cc95-108">한 명 또는 여러 팀 구성원에 게 태그를 추가 하 여 사용자의 올바른 하위 집합으로 쉽게 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2cc95-108">Tags can be added to one or multiple team members to easily connect with the right subset of people.</span></span> <span data-ttu-id="2cc95-109">팀 소유자 및 구성원 (기능을 사용 하도록 설정 된 경우) 사용자에 게 하나 이상의 태그를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2cc95-109">Team owners and members (if the feature is enabled for them) can add one or more tags to a person.</span></span> <span data-ttu-id="2cc95-110">그런 다음 팀의 모든 사용자가 채널을 게시할 때 태그를 사용 하거나 해당 태그를 할당 한 사람만 대화를 시작 하는 것을 @mentions 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2cc95-110">The tags can then be used in @mentions by anyone on the team in a channel post or to start a conversation with only those people who are assigned that tag.</span></span>

> [!NOTE]
> <span data-ttu-id="2cc95-111">태그는 개인 채널에서 아직 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2cc95-111">Tags are not yet supported in private channels.</span></span>

## <a name="how-tags-work"></a><span data-ttu-id="2cc95-112">태그가 작동 하는 방식</span><span class="sxs-lookup"><span data-stu-id="2cc95-112">How tags work</span></span>

<span data-ttu-id="2cc95-113">특정 팀의 사용자에 게 태그를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2cc95-113">A tag can be added to a person on a specific team.</span></span> <span data-ttu-id="2cc95-114">태그를 추가한 후에는 채팅 또는 팀의 표준 채널에서 @mentions에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2cc95-114">After a tag is added, it can be used in @mentions in a chat or in any standard channel of the team.</span></span> <span data-ttu-id="2cc95-115">다음은 팀에서 태그를 사용 하는 방법에 대 한 몇 가지 예입니다.</span><span class="sxs-lookup"><span data-stu-id="2cc95-115">Here's some examples of how tags can be used in Teams:</span></span>

- <span data-ttu-id="2cc95-116">스토어 관리자가 채널에 알림을 게시 하 고 모든 cashiers에 게 알려야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cc95-116">A store manager wants to post an announcement to a channel and notify all cashiers.</span></span>
- <span data-ttu-id="2cc95-117">그룹 제품 관리자가 채널의 모든 제품 관리자에 게 메시지를 전송 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cc95-117">A group product manager wants to message all product managers in a channel.</span></span>
- <span data-ttu-id="2cc95-118">병원 관리자가 채널의 모든 radiologists에 게 메시지를 보내려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cc95-118">A hospital administrator wants to send a message to all radiologists in a channel.</span></span>
- <span data-ttu-id="2cc95-119">마케팅 관리자가 모든 설계자와 그룹 채팅을 시작 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cc95-119">A marketing manager wants to start a group chat with all designers.</span></span> 

<span data-ttu-id="2cc95-120">자세한 내용은 [팀에서 태그를 사용 하 여](https://support.office.com/article/using-tags-in-teams-667bd56f-32b8-4118-9a0b-56807c96d91e)확인해 보세요.</span><span class="sxs-lookup"><span data-stu-id="2cc95-120">To learn more, check out [Using tags in Teams](https://support.office.com/article/using-tags-in-teams-667bd56f-32b8-4118-9a0b-56807c96d91e).</span></span>

## <a name="manage-tags-for-your-organization"></a><span data-ttu-id="2cc95-121">조직의 태그 관리</span><span class="sxs-lookup"><span data-stu-id="2cc95-121">Manage tags for your organization</span></span>

<span data-ttu-id="2cc95-122">관리자는 Microsoft 팀 관리 센터에서 태그를 추가할 수 있는 사람과 사용자의 조직에서 태그를 사용 하는 방법을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2cc95-122">As an admin, you can control who can add tags and how tags are used across your organization in the Microsoft Teams admin center.</span></span>

![Microsoft 팀 관리 센터의 태그 설정 스크린샷](media/manage-tags-admin-settings.png)

### <a name="set-who-can-add-tags"></a><span data-ttu-id="2cc95-124">태그를 추가할 수 있는 사용자 설정</span><span class="sxs-lookup"><span data-stu-id="2cc95-124">Set who can add tags</span></span>

<span data-ttu-id="2cc95-125">기본적으로 팀 소유자는 태그를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2cc95-125">By default, team owners can add tags.</span></span> <span data-ttu-id="2cc95-126">팀 소유자와 팀 구성원이 태그를 추가할 수 있도록이 설정을 변경 하거나 조직의 태그를 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2cc95-126">You can change this setting to allow team owners and team members to add tags or you can turn off tags for your organization.</span></span>

1. <span data-ttu-id="2cc95-127">Microsoft 팀 관리 센터의 왼쪽 탐색 모음에서 **조직 전체 설정** > **팀 설정을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cc95-127">In the left navigation of the Microsoft Teams admin center, click **Org-wide settings** > **Teams settings**.</span></span>
2. <span data-ttu-id="2cc95-128">**태깅**아래에서 **태그**지정 옆에 있는에서 다음 옵션 중 하나를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cc95-128">Under **Tagging**, next to **Tagging is enabled for**, select one of the following options:</span></span>

    - <span data-ttu-id="2cc95-129">**팀 소유자 및 구성원**: 팀 소유자 및 구성원이 태그를 추가할 수 있도록 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cc95-129">**Team owners and members**: Allow team owners and members to add tags.</span></span>
    - <span data-ttu-id="2cc95-130">**팀 소유자**: 팀 소유자가 태그를 추가할 수 있도록 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cc95-130">**Team owners**: Allow team owners to add tags.</span></span>
    - <span data-ttu-id="2cc95-131">**사용 안 함**: 태그 끄기.</span><span class="sxs-lookup"><span data-stu-id="2cc95-131">**Disabled**: Turn off tags.</span></span>

### <a name="configure-tags-settings"></a><span data-ttu-id="2cc95-132">태그 설정 구성</span><span class="sxs-lookup"><span data-stu-id="2cc95-132">Configure tags settings</span></span>

<span data-ttu-id="2cc95-133">조직에서 태그를 사용 하는 방법을 제어 하도록 다음 태그 설정을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2cc95-133">You can configure the following tags settings to control how tags are used across your organization.</span></span>

1. <span data-ttu-id="2cc95-134">Microsoft 팀 관리 센터의 왼쪽 탐색 모음에서 **조직 전체 설정** > **팀 설정을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cc95-134">In the left navigation of the Microsoft Teams admin center, click **Org-wide settings** > **Teams settings**.</span></span>
2. <span data-ttu-id="2cc95-135">**태그**아래에서 조직의 요구 사항에 따라 다음을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cc95-135">Under **Tagging**, set the following, depending on the needs of your organization.</span></span>

    - <span data-ttu-id="2cc95-136">**팀 소유자는 태그를 적용할 수 있는 사람을 무시할 수**있습니다 .이 옵션이 설정 되어 있는 경우 팀 소유자는 구성원에 게 팀 설정에서 태그를 추가 하도록 허용 하거나 허용 하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2cc95-136">**Team owner can override who can apply tags**: When this is turned on, team owners can allow or disallow members to add tags in team settings.</span></span>
    - <span data-ttu-id="2cc95-137">**구성원은 추가 태그를 추가할 수**있습니다. 팀 구성원이 태그를 추가할 수 있도록 허용 하는 경우, 사용자가 설정한 제안 된 기본 태그 이외의 태그를 팀 구성원이 추가 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cc95-137">**Members can add additional tags**: If you allow team members to add tags, turn this on to let team members add tags other than the suggested default tags that you set.</span></span> <span data-ttu-id="2cc95-138">이 옵션이 해제 되어 있는 경우 팀 구성원은 기본 태그만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2cc95-138">If this is turned off, team members can only use the default tags.</span></span>
    - <span data-ttu-id="2cc95-139">**제안 된 기본 태그**:이를 사용 하 여 기본 태그 집합을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cc95-139">**Suggested default tags**: Use this to add a set of default tags.</span></span> <span data-ttu-id="2cc95-140">태그는 최대 25 개까지 추가할 수 있으며, 각 태그는 25 자까지 입력할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2cc95-140">You can add up to 25 tags, and each tag can contain a maximum of 25 characters.</span></span> <span data-ttu-id="2cc95-141">팀 소유자 및 구성원 (해당 기능이 해당 기능을 사용 하도록 설정 된 경우)을 사용 하거나, 해당 제안에 추가 하거나, 새 태그 집합을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2cc95-141">Team owners and members (if the feature is enabled for them) can use these suggestions, add to them, or create a new set of tags.</span></span>

## <a name="manage-tags-settings-for-a-team"></a><span data-ttu-id="2cc95-142">팀의 태그 설정 관리</span><span class="sxs-lookup"><span data-stu-id="2cc95-142">Manage tags settings for a team</span></span>

<span data-ttu-id="2cc95-143">팀 소유자가 Microsoft 팀 관리 센터에서 **태그를 적용할 수 있는 사용자를 재정의할 수** 있는 경우 팀 소유자는 멤버가 팀 수준에서 태그를 추가할 수 있는지 여부를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2cc95-143">If you turned on the **Team owner can override who can apply tags** setting in the Microsoft Teams admin center, team owners can set whether members can add tags at the team level.</span></span> <span data-ttu-id="2cc95-144">이렇게 하려면 팀의 **설정** 탭에서 **태그로**이동한 다음 태그를 추가할 수 있는 사용자를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cc95-144">To do this, on the **Settings** tab for a team, go to **Tags**, and then choose who can add tags.</span></span>

![팀 수준의 태그 설정 스크린샷](media/manage-tags-team-settings.png)

## <a name="add-tags-in-teams"></a><span data-ttu-id="2cc95-146">팀에서 태그 추가</span><span class="sxs-lookup"><span data-stu-id="2cc95-146">Add tags in Teams</span></span>

<span data-ttu-id="2cc95-147">팀에서 팀원에 대 한 팀 관리 페이지의 **구성원** 탭에는 **태그** 열이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2cc95-147">In Teams, the **Members** tab of the Manage team page for a team includes a **Tags** column.</span></span> <span data-ttu-id="2cc95-148">팀 소유자 및 구성원 (이 기능을 사용 하도록 설정 된 경우) 구성원 옆에 있는 **태그 관리** 를 클릭 하 여 해당 구성원에 대 한 추천 태그 목록을 표시 하 고 목록에 태그를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2cc95-148">Team owners and members (if the feature is enabled for them) can click **Manage tags** next to a member to see the list of suggested tags for that member and add tags to the list.</span></span>

![<span data-ttu-id="2cc95-149">팀 클라이언트에서 태그를 적용 하는 방법 스크린샷</span><span class="sxs-lookup"><span data-stu-id="2cc95-149">Screenshot of how to apply tags in the Teams client</span></span> ](media/manage-tags-teams.png) 
