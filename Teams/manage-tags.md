---
title: Microsoft Teams에서 태그 관리
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: acolonna, salu
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
description: Microsoft Teams에서 조직에서 태그를 사용하는 방법을 관리하는 방법에 대해 자세히 알아보습니다.
ms.openlocfilehash: c63817f5b3ee9c736311982b54dbc9a220564229
ms.sourcegitcommit: 5a39061c2156531f4b7f5f69eecf81a8c8b238d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/27/2021
ms.locfileid: "52030108"
---
# <a name="manage-tags-in-microsoft-teams"></a><span data-ttu-id="b8dbf-103">Microsoft Teams에서 태그 관리</span><span class="sxs-lookup"><span data-stu-id="b8dbf-103">Manage tags in Microsoft Teams</span></span>

## <a name="overview"></a><span data-ttu-id="b8dbf-104">개요</span><span class="sxs-lookup"><span data-stu-id="b8dbf-104">Overview</span></span>

<span data-ttu-id="b8dbf-105">Microsoft Teams의 태그를 통해 사용자는 팀의 하위 집합과 빠르고 쉽게 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8dbf-105">Tags in Microsoft Teams let users quickly and easily connect with a subset of people on a team.</span></span> <span data-ttu-id="b8dbf-106">역할, 프로젝트, 기술 또는 위치와 같은 특성에 따라 사용자 지정 태그를 만들고 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8dbf-106">You can create and assign custom tags to categorize people based on attributes, such as role, project, skill, or location.</span></span> <span data-ttu-id="b8dbf-107">또는 [Shifts](https://support.microsoft.com/office/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?#PickTab=Shifts) 앱의 일정 및 교대 근무 정보에 따라 태그를 사용자에게 자동으로 할당할 수 있습니다(곧 출시 예정).</span><span class="sxs-lookup"><span data-stu-id="b8dbf-107">Or, tags can be automatically assigned to people based on their schedule and shift information in the [Shifts app](https://support.microsoft.com/office/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?#PickTab=Shifts) (coming soon).</span></span> <span data-ttu-id="b8dbf-108">태그가 하나 또는 여러 팀 구성원에 추가된 후 채널 @mentions 팀의 모든 사용자가 태그를 추가하거나 해당 태그에 할당된 사용자와의 대화를 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8dbf-108">After a tag is added to one or multiple team members, it can be used in @mentions by anyone on the team in a channel post or to start a conversation with only those people who are assigned that tag.</span></span>

<span data-ttu-id="b8dbf-109">앞에서 설명한 대로 Teams에는 두 종류의 태그가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8dbf-109">As mentioned earlier, there are two kinds of tags in Teams.</span></span>

- <span data-ttu-id="b8dbf-110">**사용자 지정 태그:** 팀 소유자 및 팀 구성원(해당 기능을 사용하도록 설정되어 있는 경우)은 수동으로 태그를 만들고 사용자에게 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8dbf-110">**Custom tags**: Team owners and team members (if the feature is enabled for them) can manually create and assign tags to people.</span></span> <span data-ttu-id="b8dbf-111">예를 들어 "Designer" 또는 "Radiologist" 태그는 이름을 입력하지 않고도 팀의 이러한 사용자 집합에 도달합니다.</span><span class="sxs-lookup"><span data-stu-id="b8dbf-111">For example, a "Designer" or "Radiologist" tag will reach those sets of people on a team without having to type their names.</span></span>
- <span data-ttu-id="b8dbf-112">**교대 근무로 태그** 지정 : 이 기능을 사용하면 Teams의 [Shifts](https://support.microsoft.com/office/get-started-in-shifts-5f3e30d8-1821-4904-be26-c3cd25a497d6#bkmk_openshiftsappdesktop) 앱에서 일정 및 교대 근무 그룹 이름과 일치하는 태그가 자동으로 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8dbf-112">**Tagging by shift**: With this feature, people are automatically assigned tags that match their schedule and shift group name in the [Shifts app](https://support.microsoft.com/office/get-started-in-shifts-5f3e30d8-1821-4904-be26-c3cd25a497d6#bkmk_openshiftsappdesktop) in Teams.</span></span> <span data-ttu-id="b8dbf-113">예를 들어 "EngineerOnCall" 태그는 채팅 또는 채널 게시물에서 태그를 사용할 때 Shifts에서 작업할 예정인 모든 엔지니어에게 도달합니다.</span><span class="sxs-lookup"><span data-stu-id="b8dbf-113">For example, the "EngineerOnCall" tag reaches all engineers who are scheduled in Shifts to work at the time the tag is used in a chat or channel post.</span></span> <span data-ttu-id="b8dbf-114">Shift에 따라 태그를 지정하면 Teams는 사용자가 정보를 빠르게 릴레이해야 할 때 교대 근무 직원의 이름을 알지 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b8dbf-114">With tagging by shift, Teams takes the guesswork out of knowing the name of on-shift staff when users need to quickly relay information.</span></span> <span data-ttu-id="b8dbf-115">교대 근무로 태그 지정은 또한 팀의 Shifts와 통합하여 JDA, Kronos 및 AMiON과 같은 주요 인력 관리 시스템에서 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8dbf-115">Tagging by shift can also be backed by major workforce management systems like JDA, Kronos, and AMiON by integrating them with Shifts in Teams.</span></span> <span data-ttu-id="b8dbf-116">이 기능을 설정하는 방법에 대한 자세한 내용은 Shift에 따라 태그 [지정 을 참조합니다.](#set-up-tagging-by-shift)</span><span class="sxs-lookup"><span data-stu-id="b8dbf-116">To learn more about how to set up this feature, see [Set up tagging by shift](#set-up-tagging-by-shift).</span></span>

> [!NOTE]
> <span data-ttu-id="b8dbf-117">태그는 아직 개인 채널에서 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b8dbf-117">Tags are not yet supported in private channels.</span></span> <span data-ttu-id="b8dbf-118">GCC High 또는 DoD(국방부) 조직에서는 태그를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b8dbf-118">Tags are not available in GCC High, or Department of Defense (DoD) organizations.</span></span> 

## <a name="how-tags-work"></a><span data-ttu-id="b8dbf-119">태그 작동 방식</span><span class="sxs-lookup"><span data-stu-id="b8dbf-119">How tags work</span></span>

<span data-ttu-id="b8dbf-120">태그를 수동으로 추가하거나 특정 팀의 사용자에게 자동으로 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8dbf-120">A tag can be manually added or automatically assigned to a person on a specific team.</span></span> <span data-ttu-id="b8dbf-121">그런 다음 채팅에서 to 줄에  @mentions 또는 팀의 모든 표준 채널의 게시물에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8dbf-121">It can then be used in @mentions on the **To** line in a chat or in a post on any standard channel of the team.</span></span> <span data-ttu-id="b8dbf-122">Teams에서 태그를 사용하는 방법에 대한 몇 가지 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b8dbf-122">Here's some examples of how tags can be used in Teams:</span></span>

- <span data-ttu-id="b8dbf-123">상점 관리자는 채널에 공지를 게시하여 모든 계산원에게 알릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8dbf-123">A store manager posts an announcement to a channel to notify all cashiers.</span></span>
- <span data-ttu-id="b8dbf-124">병원 관리자는 채널의 모든 방사선 전문의에게 메시지를 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="b8dbf-124">A hospital administrator sends a message to all radiologists in a channel.</span></span>
- <span data-ttu-id="b8dbf-125">마케팅 관리자는 모든 디자이너와 그룹 채팅을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="b8dbf-125">A marketing manager starts a group chat with all designers.</span></span>
- <span data-ttu-id="b8dbf-126">간호사는 모든 통화 심리학자에게 메시지를 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="b8dbf-126">A nurse sends a message to all on-call cardiologists.</span></span> <span data-ttu-id="b8dbf-127">(곧 지원됨)</span><span class="sxs-lookup"><span data-stu-id="b8dbf-127">(coming soon)</span></span>
- <span data-ttu-id="b8dbf-128">시스템 엔지니어는 모든 교대 근무 현장 엔지니어에게 알리기 위해 채널에 공지를 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="b8dbf-128">A system engineer posts an announcement to a channel to notify all on-shift field engineers.</span></span> <span data-ttu-id="b8dbf-129">(곧 지원됨)</span><span class="sxs-lookup"><span data-stu-id="b8dbf-129">(coming soon)</span></span>

<span data-ttu-id="b8dbf-130">태그가 채널 대화에 @mentioned 경우 태그와 연결된 팀 구성원에게 다른 사용자와 마찬가지로 알림을 @mention.</span><span class="sxs-lookup"><span data-stu-id="b8dbf-130">When a tag is @mentioned in a channel conversation, team members associated with the tag will get notified, just like any other @mention.</span></span>

## <a name="manage-custom-tags-for-your-organization"></a><span data-ttu-id="b8dbf-131">조직의 사용자 지정 태그 관리</span><span class="sxs-lookup"><span data-stu-id="b8dbf-131">Manage custom tags for your organization</span></span>

<span data-ttu-id="b8dbf-132">관리자는 Microsoft Teams 관리 센터에서 조직 전체에서 태그를 사용하는 방법을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8dbf-132">As an admin, you can control how tags are used across your organization in the Microsoft Teams admin center.</span></span> <span data-ttu-id="b8dbf-133">현재 PowerShell을 사용하여 태그를 관리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b8dbf-133">Currently, you can't use PowerShell to manage tags.</span></span>

![Microsoft Teams 관리 센터의 태그 지정 설정 스크린샷](media/manage-tags-admin-settings.png)

<span data-ttu-id="b8dbf-135">팀에는 최대 100개 태그가 있을 수 있으며, 최대 100개 팀 구성원을 태그에 할당할 수 있으며, 단일 사용자에게 최대 25개 태그를 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8dbf-135">A team can have up to 100 tags, up to 100 team members can be assigned to a tag, and up to 25 tags can be assigned to a single user.</span></span> 

### <a name="set-who-can-add-custom-tags"></a><span data-ttu-id="b8dbf-136">사용자 지정 태그를 추가할 수 있는 사용자 설정</span><span class="sxs-lookup"><span data-stu-id="b8dbf-136">Set who can add custom tags</span></span>

<span data-ttu-id="b8dbf-137">기본적으로 팀 소유자는 사용자 지정 태그를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8dbf-137">By default, team owners can add custom tags.</span></span> <span data-ttu-id="b8dbf-138">팀 소유자 및 팀 구성원이 태그를 만들고 편집, 삭제 및 관리할 수 있도록 이 설정을 변경하거나 조직의 태그를 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8dbf-138">You can change this setting to allow team owners and team members to create, edit, delete, and manage tags or you can turn off tags for your organization.</span></span>

1. <span data-ttu-id="b8dbf-139">Microsoft Teams 관리 센터의 왼쪽 탐색에서 **Org-wide 설정** Teams 설정을  >  **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="b8dbf-139">In the left navigation of the Microsoft Teams admin center, click **Org-wide settings** > **Teams settings**.</span></span>
2. <span data-ttu-id="b8dbf-140">태그 **지정 아래에서** **태그** 옆에 있는 에서 관리됩니다. 다음 옵션 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b8dbf-140">Under **Tagging**, next to **Tags are managed by**, select one of the following options:</span></span>

    - <span data-ttu-id="b8dbf-141">**팀 소유자 및 구성원**: 팀 소유자 및 구성원이 태그를 관리할 수 있도록 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="b8dbf-141">**Team owners and members**: Allow team owners and members to manage tags.</span></span>
    - <span data-ttu-id="b8dbf-142">**팀 소유자**: 팀 소유자가 태그를 관리할 수 있도록 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="b8dbf-142">**Team owners**: Allow team owners to manage tags.</span></span>
    - <span data-ttu-id="b8dbf-143">**사용하지 않도록 설정**: 태그를 끄기.</span><span class="sxs-lookup"><span data-stu-id="b8dbf-143">**Disabled**: Turn off tags.</span></span>

### <a name="configure-custom-tags-settings"></a><span data-ttu-id="b8dbf-144">사용자 지정 태그 설정 구성</span><span class="sxs-lookup"><span data-stu-id="b8dbf-144">Configure custom tags settings</span></span>

<span data-ttu-id="b8dbf-145">조직 전체에서 사용자 지정 태그를 사용하는 방법을 제어하도록 다음 태그 설정을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8dbf-145">You can configure the following tags settings to control how custom tags are used across your organization.</span></span>

1. <span data-ttu-id="b8dbf-146">Microsoft Teams 관리 센터의 왼쪽 탐색에서 **Org-wide 설정** Teams 설정을  >  **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="b8dbf-146">In the left navigation of the Microsoft Teams admin center, click **Org-wide settings** > **Teams settings**.</span></span>
2. <span data-ttu-id="b8dbf-147">태그 **지정에서** 조직의 요구에 따라 다음을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="b8dbf-147">Under **Tagging**, set the following, depending on the needs of your organization.</span></span>

    - <span data-ttu-id="b8dbf-148">**태그를** 관리할 수 있는 팀 소유자를 다시 지정하게 합니다. 이 설정을 설정하면 팀 소유자는 팀 구성원이 팀  내에서 태그를 만들고 관리할 수 있는지 여부를 설정할 수 있으며 태그 값은 각 팀의 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="b8dbf-148">**Let team owners override who can manage tags**: When you turn on this setting, team owners can set whether team members can create and manage tags within a team and the value of the **Tags are managed by** setting is the default value for each team.</span></span> <span data-ttu-id="b8dbf-149">이 설정을 해제하면 태그는 팀당 변경할 수 없습니다. </span><span class="sxs-lookup"><span data-stu-id="b8dbf-149">If you turn off this setting, the **Tags are managed by** setting can't be changed per team.</span></span>
    - <span data-ttu-id="b8dbf-150">**제안된 기본 태그:** 이 태그를 사용하여 기본 태그 집합을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="b8dbf-150">**Suggested default tags**: Use this to add a set of default tags.</span></span> <span data-ttu-id="b8dbf-151">최대 25개 태그를 추가할 수 있으며 각 태그에는 최대 25자까지 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8dbf-151">You can add up to 25 tags, and each tag can contain a maximum of 25 characters.</span></span> <span data-ttu-id="b8dbf-152">팀 소유자 및 멤버(해당 기능을 사용하도록 설정되어 있는 경우)는 이러한 제안을 사용하거나, 추가하거나, 새 태그 집합을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8dbf-152">Team owners and members (if the feature is enabled for them) can use these suggestions, add to them, or create a new set of tags.</span></span>
    - <span data-ttu-id="b8dbf-153">**사용자 지정 태그를** 만들 수 있습니다. 이 설정을 켜서 사람들이 설정한 제안된 기본 태그가 다른 태그를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8dbf-153">**Let custom tags be created**: Turn on this setting to let people add tags other than the suggested default tags that you set.</span></span> <span data-ttu-id="b8dbf-154">이 태그가 해제된 경우 사람들은 제안된 기본 태그만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8dbf-154">If this is turned off, people can only use the suggested default tags.</span></span> <span data-ttu-id="b8dbf-155">이 태그를 해제하면 하나 이상의 기본 태그를 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8dbf-155">If you turn this off, make sure that you add one or more default tags.</span></span>

## <a name="manage-custom-tags-settings-for-a-team"></a><span data-ttu-id="b8dbf-156">팀에 대한 사용자 지정 태그 설정 관리</span><span class="sxs-lookup"><span data-stu-id="b8dbf-156">Manage custom tags settings for a team</span></span>

<span data-ttu-id="b8dbf-157">Microsoft Teams 관리  센터에서 태그 설정을 관리할 수 있는 팀 소유자가 다시 지정을 설정한 경우 팀 소유자는 구성원이 팀 수준에서 태그를 추가할 수 있는지 여부를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8dbf-157">If you turned on the **Let team owners override who can manage tags** setting in the Microsoft Teams admin center, team owners can set whether members can add tags at the team level.</span></span> <span data-ttu-id="b8dbf-158">이렇게하려면 팀의 **설정** 탭에서 **태그로** 이동한 다음 태그를 추가할 수 있는 사용자 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b8dbf-158">To do this, on the **Settings** tab for a team, go to **Tags**, and then choose who can add tags.</span></span>

![팀 수준에서 태그 설정 스크린샷](media/manage-tags-team-settings.png)

## <a name="use-tags"></a><span data-ttu-id="b8dbf-160">태그 사용</span><span class="sxs-lookup"><span data-stu-id="b8dbf-160">Use tags</span></span>

<span data-ttu-id="b8dbf-161">사용자 지정 태그를 추가하는 방법과 Shift에 따라 태그 지정을 설정하는 방법(Teams에서 Shifts 앱을 사용하는 경우)</span><span class="sxs-lookup"><span data-stu-id="b8dbf-161">Here's how to add custom tags and how to set up tagging by shift (if you're using the Shifts app in Teams).</span></span> <span data-ttu-id="b8dbf-162">자세한 내용은 Teams 에서 태그 [사용을 체크 아웃합니다.](https://support.office.com/article/using-tags-in-teams-667bd56f-32b8-4118-9a0b-56807c96d91e)</span><span class="sxs-lookup"><span data-stu-id="b8dbf-162">To learn more, check out [Using tags in Teams](https://support.office.com/article/using-tags-in-teams-667bd56f-32b8-4118-9a0b-56807c96d91e).</span></span>

### <a name="create-and-assign-custom-tags"></a><span data-ttu-id="b8dbf-163">사용자 지정 태그 만들기 및 할당</span><span class="sxs-lookup"><span data-stu-id="b8dbf-163">Create and assign custom tags</span></span>

<span data-ttu-id="b8dbf-164">사용자 지정 태그를 만들고 할당하려면 앱 왼쪽에 있는 **Teams를** 선택한 다음 목록에서 팀을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="b8dbf-164">To create and assign custom tags, select **Teams** on the left side of the app, and then find your team in the list.</span></span> <span data-ttu-id="b8dbf-165">추가 ̇ ̇ ̇ 옵션을 **선택한** 다음 태그 **관리 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="b8dbf-165">Select **˙˙˙ More options**, and then choose **Manage tags**.</span></span> <span data-ttu-id="b8dbf-166">여기에서 태그를 만들고 팀의 사용자에게 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8dbf-166">Here, you can create tags and assign them to people on your team.</span></span>

![<span data-ttu-id="b8dbf-167">Teams 클라이언트에서 태그를 적용하는 방법 스크린샷</span><span class="sxs-lookup"><span data-stu-id="b8dbf-167">Screenshot of how to apply tags in the Teams client</span></span> ](media/manage-tags-teams.png)

<span data-ttu-id="b8dbf-168">태그를 삭제하려면 태그 **옆에 ̇ ̇ ̇** 추가 옵션을 선택한 다음 태그 **삭제를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="b8dbf-168">To delete a tag, select **˙˙˙ More options** next to the tag, and then select **Delete tag**.</span></span>

### <a name="set-up-tagging-by-shift"></a><span data-ttu-id="b8dbf-169">Shift에 따라 태그 지정 설정</span><span class="sxs-lookup"><span data-stu-id="b8dbf-169">Set up tagging by shift</span></span>

1. <span data-ttu-id="b8dbf-170">Teams에서 [Shifts 앱으로 이동합니다.](https://support.microsoft.com/office/get-started-in-shifts-5f3e30d8-1821-4904-be26-c3cd25a497d6#bkmk_openshiftsappdesktop)</span><span class="sxs-lookup"><span data-stu-id="b8dbf-170">In Teams, go to the [Shifts app](https://support.microsoft.com/office/get-started-in-shifts-5f3e30d8-1821-4904-be26-c3cd25a497d6#bkmk_openshiftsappdesktop).</span></span>
2. <span data-ttu-id="b8dbf-171">교대 [근무 그룹을 만들고](https://support.microsoft.com/office/fill-out-a-schedule-in-shifts-2d58df9b-1c6c-4c84-b0c3-835de7ad13ea#bkmk_organizeshiftsbygroup) 역할과 같은 특성 후에 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b8dbf-171">Create [shift groups](https://support.microsoft.com/office/fill-out-a-schedule-in-shifts-2d58df9b-1c6c-4c84-b0c3-835de7ad13ea#bkmk_organizeshiftsbygroup) and name them after an attribute such as a role.</span></span> <span data-ttu-id="b8dbf-172">예를 들어 EngineerOnCall입니다.</span><span class="sxs-lookup"><span data-stu-id="b8dbf-172">For example, EngineerOnCall.</span></span> <span data-ttu-id="b8dbf-173">교대 근무 그룹 이름은 태그의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="b8dbf-173">The shift group name will be the name of the tag.</span></span>
3. <span data-ttu-id="b8dbf-174">[팀 구성원에게](https://support.microsoft.com/office/fill-out-a-schedule-in-shifts-2d58df9b-1c6c-4c84-b0c3-835de7ad13ea) 교대 근무를 할당하여 일정을 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="b8dbf-174">[Fill out a schedule](https://support.microsoft.com/office/fill-out-a-schedule-in-shifts-2d58df9b-1c6c-4c84-b0c3-835de7ad13ea) by assigning shifts to members of you teams.</span></span> <span data-ttu-id="b8dbf-175">완료되면 Shifts 앱의 오른쪽 위 모서리에서 팀과 **공유를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="b8dbf-175">When you're finished, in the upper-right corner of the Shifts app, select **Share with team**.</span></span>
4. <span data-ttu-id="b8dbf-176">예약된 교대 근무가 태그 지정 서비스를 채우는 데 15분 정도 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="b8dbf-176">Wait 15 minutes for the scheduled shifts to populate the tagging service.</span></span>
5. <span data-ttu-id="b8dbf-177">Teams에서 태그를 사용하는 어디서나 태그를 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="b8dbf-177">Use the tag anywhere you use tags in Teams.</span></span>

<span data-ttu-id="b8dbf-178">교대 근무로 태그를 지정하면 사용자가 실시간으로 교대 근무하는 사용자에게 도달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8dbf-178">Tagging by shift allows your users to reach the people on-shift in real time.</span></span> <span data-ttu-id="b8dbf-179">알림은 채팅을 시작하거나 채널 게시물에서 태그를 사용할 때 교대 근무 중인 사용자만 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8dbf-179">Notifications are sent only to those people who are on shift at the time a tag is used to start a chat or in a channel post.</span></span>

## <a name="related-topics"></a><span data-ttu-id="b8dbf-180">관련 항목</span><span class="sxs-lookup"><span data-stu-id="b8dbf-180">Related topics</span></span>

[<span data-ttu-id="b8dbf-181">Teams에서 태그 사용</span><span class="sxs-lookup"><span data-stu-id="b8dbf-181">Using tags in Teams</span></span>](https://support.office.com/article/using-tags-in-teams-667bd56f-32b8-4118-9a0b-56807c96d91e)

[<span data-ttu-id="b8dbf-182">Teams에서 조직의 교대 근무 앱 관리</span><span class="sxs-lookup"><span data-stu-id="b8dbf-182">Manage the Shifts app for your organization in Teams</span></span>](expand-teams-across-your-org/shifts/manage-the-shifts-app-for-your-organization-in-teams.md)

[<span data-ttu-id="b8dbf-183">Shifts 도움말 설명서</span><span class="sxs-lookup"><span data-stu-id="b8dbf-183">Shifts Help documentation</span></span>](https://support.microsoft.com/office/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)
