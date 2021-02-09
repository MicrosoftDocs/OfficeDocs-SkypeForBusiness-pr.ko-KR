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
description: Microsoft Teams에서 조직에서 태그를 사용하는 방법을 관리하는 방법을 배워야 합니다.
ms.openlocfilehash: e5222a820a3a721c3692b0cdb272d1c4f3aaea6d
ms.sourcegitcommit: 27bfa015413bc7742bca4ea227e0324da0c740d7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/08/2021
ms.locfileid: "50145855"
---
# <a name="manage-tags-in-microsoft-teams"></a><span data-ttu-id="ce897-103">Microsoft Teams에서 태그 관리</span><span class="sxs-lookup"><span data-stu-id="ce897-103">Manage tags in Microsoft Teams</span></span>

> [!NOTE]
> <span data-ttu-id="ce897-104">이 문서에서 설명하는 기능 중 하나인 Shift로 태그 **지정은** 롤아웃됩니다. 관리자인 경우 메시지 센터(Microsoft 365 관리 센터)에서 해당 지역에 대해 이 기능이 [릴리스될 때를 찾을 수 있습니다.](https://portal.office.com/adminportal/home)</span><span class="sxs-lookup"><span data-stu-id="ce897-104">One of the features discussed in this article, **tagging by shift**, is rolling out. If you're an admin, you can find out when this feature will be released for your region in the Message Center (in the [Microsoft 365 admin center](https://portal.office.com/adminportal/home)).</span></span> <span data-ttu-id="ce897-105">예정된 Teams 기능을 계속 사용하길 [원하면 Microsoft 365 로드맵을 확인해 보아야 합니다.](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=microsoft%2Cteams)</span><span class="sxs-lookup"><span data-stu-id="ce897-105">To stay on top of upcoming Teams features, check out the [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=microsoft%2Cteams).</span></span>

## <a name="overview"></a><span data-ttu-id="ce897-106">개요</span><span class="sxs-lookup"><span data-stu-id="ce897-106">Overview</span></span>

<span data-ttu-id="ce897-107">Microsoft Teams의 태그를 통해 사용자는 팀의 일부 사용자와 빠르고 쉽게 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce897-107">Tags in Microsoft Teams let users quickly and easily connect with a subset of people on a team.</span></span> <span data-ttu-id="ce897-108">사용자 지정 태그를 만들고 할당하여 역할, 프로젝트, 기술 또는 위치와 같은 특성에 따라 다른 사용자로 분류할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce897-108">You can create and assign custom tags to categorize people based on attributes, such as role, project, skill, or location.</span></span> <span data-ttu-id="ce897-109">또는 [Shifts](https://support.microsoft.com/office/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?#PickTab=Shifts) 앱의 일정 및 교대 근무 정보에 따라 태그를 사용자에게 자동으로 할당할 수 있습니다(출시 예정).</span><span class="sxs-lookup"><span data-stu-id="ce897-109">Or, tags can be automatically assigned to people based on their schedule and shift information in the [Shifts app](https://support.microsoft.com/office/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?#PickTab=Shifts) (coming soon).</span></span> <span data-ttu-id="ce897-110">태그를 하나 또는 여러 팀 구성원에게 추가한 후 채널 게시물에서 팀의 @mentions 태그를 할당된 사용자와의 대화를 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce897-110">After a tag is added to one or multiple team members, it can be used in @mentions by anyone on the team in a channel post or to start a conversation with only those people who are assigned that tag.</span></span>

<span data-ttu-id="ce897-111">앞에서 설명한 대로 Teams에는 두 종류의 태그가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce897-111">As mentioned earlier, there are two kinds of tags in Teams.</span></span>

- <span data-ttu-id="ce897-112">**사용자 지정 태그:** 팀 소유자 및 팀 구성원(기능이 사용하도록 설정된 경우)은 수동으로 태그를 만들고 사용자에게 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce897-112">**Custom tags**: Team owners and team members (if the feature is enabled for them) can manually create and assign tags to people.</span></span> <span data-ttu-id="ce897-113">예를 들어 "Designer" 또는 "Radiologist" 태그는 이름을 입력할 필요 없이 팀의 사용자 집합에 도달합니다.</span><span class="sxs-lookup"><span data-stu-id="ce897-113">For example, a "Designer" or "Radiologist" tag will reach those sets of people on a team without having to type their names.</span></span>
- <span data-ttu-id="ce897-114">**교대 근무에 따라** 태그 지정: 이 기능을 사용하면 Teams의 [Shifts](https://support.microsoft.com/office/get-started-in-shifts-5f3e30d8-1821-4904-be26-c3cd25a497d6#bkmk_openshiftsappdesktop) 앱에서 일정 및 교대 근무 그룹 이름과 일치하는 태그가 자동으로 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="ce897-114">**Tagging by shift**: With this feature, people are automatically assigned tags that match their schedule and shift group name in the [Shifts app](https://support.microsoft.com/office/get-started-in-shifts-5f3e30d8-1821-4904-be26-c3cd25a497d6#bkmk_openshiftsappdesktop) in Teams.</span></span> <span data-ttu-id="ce897-115">예를 들어 "EngineerOnCall" 태그는 채팅 또는 채널 게시물에서 태그를 사용할 때 Shifts에서 작업할 예정인 모든 엔지니어에게 도달합니다.</span><span class="sxs-lookup"><span data-stu-id="ce897-115">For example, the "EngineerOnCall" tag reaches all engineers who are scheduled in Shifts to work at the time the tag is used in a chat or channel post.</span></span> <span data-ttu-id="ce897-116">교대 근무에 따라 태그를 지정하면 Teams는 사용자가 정보를 빠르게 릴레이해야 할 때 교대 근무 직원의 이름을 알지 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ce897-116">With tagging by shift, Teams takes the guesswork out of knowing the name of on-shift staff when users need to quickly relay information.</span></span> <span data-ttu-id="ce897-117">Shift에 따라 태그 지정은 Teams에서 Shifts와 통합하여 JDA, Kronos 및 AMiON과 같은 주요 인력 관리 시스템에서 지원할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce897-117">Tagging by shift can also be backed by major workforce management systems like JDA, Kronos, and AMiON by integrating them with Shifts in Teams.</span></span> <span data-ttu-id="ce897-118">이 기능을 설정하는 방법에 대한 자세한 내용은 Shift를 사용하여 태그 [지정을 참조합니다.](#set-up-tagging-by-shift)</span><span class="sxs-lookup"><span data-stu-id="ce897-118">To learn more about how to set up this feature, see [Set up tagging by shift](#set-up-tagging-by-shift).</span></span>

> [!NOTE]
> <span data-ttu-id="ce897-119">태그는 비공개 채널에서 아직 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ce897-119">Tags are not yet supported in private channels.</span></span> <span data-ttu-id="ce897-120">태그는 미국 정부 GCC(Community Cloud)로 롤아웃됩니다.</span><span class="sxs-lookup"><span data-stu-id="ce897-120">Tags are rolling out to US Government Community Cloud (GCC).</span></span> <span data-ttu-id="ce897-121">GCC High 또는 DoD(Department of Defense) 조직에서는 태그를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ce897-121">Tags are not available in GCC High, or Department of Defense (DoD) organizations.</span></span> 

## <a name="how-tags-work"></a><span data-ttu-id="ce897-122">태그 작동 방식</span><span class="sxs-lookup"><span data-stu-id="ce897-122">How tags work</span></span>

<span data-ttu-id="ce897-123">태그를 수동으로 추가하거나 특정 팀의 한 사용자에게 자동으로 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce897-123">A tag can be manually added or automatically assigned to a person on a specific team.</span></span> <span data-ttu-id="ce897-124">그런 다음 채팅의 to 줄에  @mentions 팀의 표준 채널에 있는 게시물에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce897-124">It can then be used in @mentions on the **To** line in a chat or in a post on any standard channel of the team.</span></span> <span data-ttu-id="ce897-125">Teams에서 태그를 사용하는 방법에 대한 몇 가지 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ce897-125">Here's some examples of how tags can be used in Teams:</span></span>

- <span data-ttu-id="ce897-126">매장 관리자는 채널에 공지 사항을 게시하여 모든 계산원에게 알릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce897-126">A store manager posts an announcement to a channel to notify all cashiers.</span></span>
- <span data-ttu-id="ce897-127">병원 관리자가 채널의 모든 방사성 환자에게 메시지를 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="ce897-127">A hospital administrator sends a message to all radiologists in a channel.</span></span>
- <span data-ttu-id="ce897-128">마케팅 관리자가 모든 디자이너와 그룹 채팅을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="ce897-128">A marketing manager starts a group chat with all designers.</span></span>
- <span data-ttu-id="ce897-129">간호사는 모든 통화 중리과 의사에게 메시지를 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="ce897-129">A nurse sends a message to all on-call cardiologists.</span></span> <span data-ttu-id="ce897-130">(곧 지원됨)</span><span class="sxs-lookup"><span data-stu-id="ce897-130">(coming soon)</span></span>
- <span data-ttu-id="ce897-131">시스템 엔지니어는 모든 교대 근무 현장 엔지니어에게 알리기 위해 채널에 공지를 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="ce897-131">A system engineer posts an announcement to a channel to notify all on-shift field engineers.</span></span> <span data-ttu-id="ce897-132">(곧 지원됨)</span><span class="sxs-lookup"><span data-stu-id="ce897-132">(coming soon)</span></span>

<span data-ttu-id="ce897-133">태그가 채널 대화에서 @mentioned 경우 태그와 연결된 팀 구성원은 다른 모든 사용자와 마찬가지로 알림을 @mention.</span><span class="sxs-lookup"><span data-stu-id="ce897-133">When a tag is @mentioned in a channel conversation, team members associated with the tag will get notified, just like any other @mention.</span></span>

## <a name="manage-custom-tags-for-your-organization"></a><span data-ttu-id="ce897-134">조직의 사용자 지정 태그 관리</span><span class="sxs-lookup"><span data-stu-id="ce897-134">Manage custom tags for your organization</span></span>

<span data-ttu-id="ce897-135">관리자는 Microsoft Teams 관리 센터에서 조직 전체에서 태그를 사용하는 방법을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce897-135">As an admin, you can control how tags are used across your organization in the Microsoft Teams admin center.</span></span> <span data-ttu-id="ce897-136">현재 PowerShell을 사용하여 태그를 관리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ce897-136">Currently, you can't use PowerShell to manage tags.</span></span>

![Microsoft Teams 관리 센터의 태그 지정 설정 스크린샷](media/manage-tags-admin-settings.png)

<span data-ttu-id="ce897-138">팀에는 최대 100개 태그가 있을 수 있으며, 최대 100명까지 팀 구성원을 태그에 할당할 수 있으며, 단일 사용자에게 최대 25개 태그를 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce897-138">A team can have up to 100 tags, up to 100 team members can be assigned to a tag, and up to 25 tags can be assigned to a single user.</span></span> 

### <a name="set-who-can-add-custom-tags"></a><span data-ttu-id="ce897-139">사용자 지정 태그를 추가할 수 있는 사용자 설정</span><span class="sxs-lookup"><span data-stu-id="ce897-139">Set who can add custom tags</span></span>

<span data-ttu-id="ce897-140">기본적으로 팀 소유자는 사용자 지정 태그를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce897-140">By default, team owners can add custom tags.</span></span> <span data-ttu-id="ce897-141">팀 소유자와 팀 구성원이 태그를 만들고 편집, 삭제 및 관리할 수 있도록 이 설정을 변경하거나 조직의 태그를 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce897-141">You can change this setting to allow team owners and team members to create, edit, delete, and manage tags or you can turn off tags for your organization.</span></span>

1. <span data-ttu-id="ce897-142">Microsoft Teams 관리 센터의 왼쪽 탐색 모음에서 전체 **설정** Teams 설정을  >  **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="ce897-142">In the left navigation of the Microsoft Teams admin center, click **Org-wide settings** > **Teams settings**.</span></span>
2. <span data-ttu-id="ce897-143">태그 **지정 아래에서** 태그 옆에 있는 다음 옵션 중 하나를 선택합니다. </span><span class="sxs-lookup"><span data-stu-id="ce897-143">Under **Tagging**, next to **Tags are managed by**, select one of the following options:</span></span>

    - <span data-ttu-id="ce897-144">**팀 소유자 및 구성원:** 팀 소유자와 구성원이 태그를 관리할 수 있도록 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="ce897-144">**Team owners and members**: Allow team owners and members to manage tags.</span></span>
    - <span data-ttu-id="ce897-145">**팀 소유자:** 팀 소유자가 태그를 관리할 수 있도록 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="ce897-145">**Team owners**: Allow team owners to manage tags.</span></span>
    - <span data-ttu-id="ce897-146">**사용 안 선:** 태그를 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="ce897-146">**Disabled**: Turn off tags.</span></span>

### <a name="configure-custom-tags-settings"></a><span data-ttu-id="ce897-147">사용자 지정 태그 설정 구성</span><span class="sxs-lookup"><span data-stu-id="ce897-147">Configure custom tags settings</span></span>

<span data-ttu-id="ce897-148">조직 전체에서 사용자 지정 태그를 사용하는 방법을 제어하도록 다음 태그 설정을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce897-148">You can configure the following tags settings to control how custom tags are used across your organization.</span></span>

1. <span data-ttu-id="ce897-149">Microsoft Teams 관리 센터의 왼쪽 탐색 모음에서 전체 설정 Teams **설정을**  >  **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="ce897-149">In the left navigation of the Microsoft Teams admin center, click **Org-wide settings** > **Teams settings**.</span></span>
2. <span data-ttu-id="ce897-150">태그 **지정 아래에서** 조직의 요구에 따라 다음을 설정하세요.</span><span class="sxs-lookup"><span data-stu-id="ce897-150">Under **Tagging**, set the following, depending on the needs of your organization.</span></span>

    - <span data-ttu-id="ce897-151">**태그를** 관리할 수 있는 팀 소유자를 우선할 수 있습니다. 이 설정을 설정하면 팀 소유자는 팀 구성원이 팀  내에서 태그를 만들고 관리할 수 있는지 여부를 설정할 수 있으며 태그 값은 각 팀의 기본값으로 설정하여 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce897-151">**Let team owners override who can manage tags**: When you turn on this setting, team owners can set whether team members can create and manage tags within a team and the value of the **Tags are managed by** setting is the default value for each team.</span></span> <span data-ttu-id="ce897-152">이 설정을 해제하면 태그는 팀당 변경할 수 없는 설정으로 관리됩니다. </span><span class="sxs-lookup"><span data-stu-id="ce897-152">If you turn off this setting, the **Tags are managed by** setting can't be changed per team.</span></span>
    - <span data-ttu-id="ce897-153">**권장 기본 태그:** 이 태그를 사용하여 기본 태그 집합을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="ce897-153">**Suggested default tags**: Use this to add a set of default tags.</span></span> <span data-ttu-id="ce897-154">최대 25개 태그를 추가할 수 있으며 각 태그는 최대 25자까지 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce897-154">You can add up to 25 tags, and each tag can contain a maximum of 25 characters.</span></span> <span data-ttu-id="ce897-155">팀 소유자 및 구성원(기능이 사용하도록 설정된 경우)은 이러한 제안을 사용하여 추가하거나 새 태그 집합을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce897-155">Team owners and members (if the feature is enabled for them) can use these suggestions, add to them, or create a new set of tags.</span></span>
    - <span data-ttu-id="ce897-156">**사용자 지정 태그를** 만들 수 있습니다. 이 설정을 켜서 사람들이 설정한 제안된 기본 태그가 다른 태그를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce897-156">**Let custom tags be created**: Turn on this setting to let people add tags other than the suggested default tags that you set.</span></span> <span data-ttu-id="ce897-157">이 기능을 해제하면 사용자가 제안된 기본 태그만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce897-157">If this is turned off, people can only use the suggested default tags.</span></span> <span data-ttu-id="ce897-158">이 기능을 해제하는 경우 하나 이상의 기본 태그를 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce897-158">If you turn this off, make sure that you add one or more default tags.</span></span>

## <a name="manage-custom-tags-settings-for-a-team"></a><span data-ttu-id="ce897-159">팀에 대한 사용자 지정 태그 설정 관리</span><span class="sxs-lookup"><span data-stu-id="ce897-159">Manage custom tags settings for a team</span></span>

<span data-ttu-id="ce897-160">팀 소유자가  Microsoft Teams 관리 센터에서 태그 설정을 관리할 수 있는 권한을 우선적으로 설정한 경우 팀 소유자는 구성원이 팀 수준에서 태그를 추가할 수 있는지 여부를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce897-160">If you turned on the **Let team owners override who can manage tags** setting in the Microsoft Teams admin center, team owners can set whether members can add tags at the team level.</span></span> <span data-ttu-id="ce897-161">이렇게하려면 팀의  설정 탭에서 태그로 이동한 다음 태그를 추가할 수 있는 사용자 선택</span><span class="sxs-lookup"><span data-stu-id="ce897-161">To do this, on the **Settings** tab for a team, go to **Tags**, and then choose who can add tags.</span></span>

![팀 수준의 태그 설정 스크린샷](media/manage-tags-team-settings.png)

## <a name="use-tags"></a><span data-ttu-id="ce897-163">태그 사용</span><span class="sxs-lookup"><span data-stu-id="ce897-163">Use tags</span></span>

<span data-ttu-id="ce897-164">다음은 사용자 지정 태그를 추가하는 방법과 Shift를 통해 태그 지정을 설정하는 방법(Teams에서 Shifts 앱을 사용하는 경우)입니다.</span><span class="sxs-lookup"><span data-stu-id="ce897-164">Here's how to add custom tags and how to set up tagging by shift (if you're using the Shifts app in Teams).</span></span> <span data-ttu-id="ce897-165">자세한 내용은 Teams에서 태그 [사용에 대해 자세히 알아보고](https://support.office.com/article/using-tags-in-teams-667bd56f-32b8-4118-9a0b-56807c96d91e)</span><span class="sxs-lookup"><span data-stu-id="ce897-165">To learn more, check out [Using tags in Teams](https://support.office.com/article/using-tags-in-teams-667bd56f-32b8-4118-9a0b-56807c96d91e).</span></span>

### <a name="create-and-assign-custom-tags"></a><span data-ttu-id="ce897-166">사용자 지정 태그 만들기 및 할당</span><span class="sxs-lookup"><span data-stu-id="ce897-166">Create and assign custom tags</span></span>

<span data-ttu-id="ce897-167">사용자 지정 태그를 만들고 할당하려면 앱 왼쪽에 있는 **Teams를** 선택한 다음 목록에서 팀을 찾아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce897-167">To create and assign custom tags, select **Teams** on the left side of the app, and then find your team in the list.</span></span> <span data-ttu-id="ce897-168">추가 **̇ ̇ ̇** 선택하고 태그 관리를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="ce897-168">Select **˙˙˙ More options**, and then choose **Manage tags**.</span></span> <span data-ttu-id="ce897-169">여기에서 태그를 만들고 팀의 사용자에게 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce897-169">Here, you can create tags and assign them to people on your team.</span></span>

![<span data-ttu-id="ce897-170">Teams 클라이언트에서 태그를 적용하는 방법 스크린샷</span><span class="sxs-lookup"><span data-stu-id="ce897-170">Screenshot of how to apply tags in the Teams client</span></span> ](media/manage-tags-teams.png)

<span data-ttu-id="ce897-171">태그를 삭제하려면 태그 **̇ ̇ ̇ 추가** 옵션을 선택한 다음 태그 **삭제를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="ce897-171">To delete a tag, select **˙˙˙ More options** next to the tag, and then select **Delete tag**.</span></span>

### <a name="set-up-tagging-by-shift"></a><span data-ttu-id="ce897-172">Shift로 태그 지정 설정</span><span class="sxs-lookup"><span data-stu-id="ce897-172">Set up tagging by shift</span></span>

1. <span data-ttu-id="ce897-173">Teams에서 [Shifts 앱으로 이동하세요.](https://support.microsoft.com/office/get-started-in-shifts-5f3e30d8-1821-4904-be26-c3cd25a497d6#bkmk_openshiftsappdesktop)</span><span class="sxs-lookup"><span data-stu-id="ce897-173">In Teams, go to the [Shifts app](https://support.microsoft.com/office/get-started-in-shifts-5f3e30d8-1821-4904-be26-c3cd25a497d6#bkmk_openshiftsappdesktop).</span></span>
2. <span data-ttu-id="ce897-174">교대 [근무 그룹을 만들고](https://support.microsoft.com/office/fill-out-a-schedule-in-shifts-2d58df9b-1c6c-4c84-b0c3-835de7ad13ea#bkmk_organizeshiftsbygroup) 역할과 같은 특성 다음에 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ce897-174">Create [shift groups](https://support.microsoft.com/office/fill-out-a-schedule-in-shifts-2d58df9b-1c6c-4c84-b0c3-835de7ad13ea#bkmk_organizeshiftsbygroup) and name them after an attribute such as a role.</span></span> <span data-ttu-id="ce897-175">예를 들어 EngineerOnCall입니다.</span><span class="sxs-lookup"><span data-stu-id="ce897-175">For example, EngineerOnCall.</span></span> <span data-ttu-id="ce897-176">교대 근무 그룹 이름은 태그의 이름이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ce897-176">The shift group name will be the name of the tag.</span></span>
3. <span data-ttu-id="ce897-177">[팀 구성원에게](https://support.microsoft.com/office/fill-out-a-schedule-in-shifts-2d58df9b-1c6c-4c84-b0c3-835de7ad13ea) 교대 근무를 할당하여 일정을 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="ce897-177">[Fill out a schedule](https://support.microsoft.com/office/fill-out-a-schedule-in-shifts-2d58df9b-1c6c-4c84-b0c3-835de7ad13ea) by assigning shifts to members of you teams.</span></span> <span data-ttu-id="ce897-178">완료되면 Shifts 앱의 오른쪽 위 모서리에서 팀과 **공유를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="ce897-178">When you're finished, in the upper-right corner of the Shifts app, select **Share with team**.</span></span>
4. <span data-ttu-id="ce897-179">예약된 교대 근무가 태그 지정 서비스를 채우는 데 15분 정도 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="ce897-179">Wait 15 minutes for the scheduled shifts to populate the tagging service.</span></span>
5. <span data-ttu-id="ce897-180">Teams에서 태그를 사용하는 모든 곳에서 태그를 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="ce897-180">Use the tag anywhere you use tags in Teams.</span></span>

<span data-ttu-id="ce897-181">교대 근무에 따라 태그를 지정하면 사용자가 실시간으로 교대 근무에 있는 사용자에게 도달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce897-181">Tagging by shift allows your users to reach the people on-shift in real time.</span></span> <span data-ttu-id="ce897-182">알림은 태그를 사용하여 채팅을 시작하거나 채널 게시물에서 교대 근무 중일 때만 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="ce897-182">Notifications are sent only to those people who are on shift at the time a tag is used to start a chat or in a channel post.</span></span>

## <a name="related-topics"></a><span data-ttu-id="ce897-183">관련 항목</span><span class="sxs-lookup"><span data-stu-id="ce897-183">Related topics</span></span>

[<span data-ttu-id="ce897-184">Teams에서 태그 사용</span><span class="sxs-lookup"><span data-stu-id="ce897-184">Using tags in Teams</span></span>](https://support.office.com/article/using-tags-in-teams-667bd56f-32b8-4118-9a0b-56807c96d91e)

[<span data-ttu-id="ce897-185">Teams에서 조직의 교대 근무 앱 관리</span><span class="sxs-lookup"><span data-stu-id="ce897-185">Manage the Shifts app for your organization in Teams</span></span>](expand-teams-across-your-org/shifts/manage-the-shifts-app-for-your-organization-in-teams.md)

[<span data-ttu-id="ce897-186">Shifts 도움말 설명서</span><span class="sxs-lookup"><span data-stu-id="ce897-186">Shifts Help documentation</span></span>](https://support.microsoft.com/office/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)
