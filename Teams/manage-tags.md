---
title: Microsoft 팀의 태그 관리
author: lanachin
ms.author: v-lanac
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
description: Microsoft 팀에서 조직에 태그를 사용 하는 방법을 관리 하는 방법을 알아봅니다.
ms.openlocfilehash: 965de27b2671106bed4e5c877f26a7132bf61040
ms.sourcegitcommit: b07938c0b6edafacaeaaef205a1be00c4c1693ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/16/2020
ms.locfileid: "47940528"
---
# <a name="manage-tags-in-microsoft-teams"></a><span data-ttu-id="5ecfb-103">Microsoft 팀의 태그 관리</span><span class="sxs-lookup"><span data-stu-id="5ecfb-103">Manage tags in Microsoft Teams</span></span>

> [!NOTE]
> <span data-ttu-id="5ecfb-104">이 문서에서 설명 하는 **shift의 태그**지정 기능 중 하나가 아직 해제 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="5ecfb-104">One of the features discussed in this article, **tagging by shift**, hasn't yet been released.</span></span> <span data-ttu-id="5ecfb-105">발표 되었으며 곧 제공 될 예정입니다.</span><span class="sxs-lookup"><span data-stu-id="5ecfb-105">It's been announced, and it's coming soon.</span></span><span data-ttu-id="5ecfb-106">관리자 인 경우 [Microsoft 365 관리 센터](https://portal.office.com/adminportal/home)의 메시지 센터에서이 기능을 언제 릴리스할 것인지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ecfb-106"> If you're an admin, you can find out when this feature will be released in the Message Center (in the [Microsoft 365 admin center](https://portal.office.com/adminportal/home)).</span></span> <span data-ttu-id="5ecfb-107">예정 된 팀 기능을 계속 유지 하려면 [Microsoft 365 로드맵을](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=microsoft%2Cteams)확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="5ecfb-107">To stay on top of upcoming Teams features, check out the [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=microsoft%2Cteams).</span></span>

## <a name="overview"></a><span data-ttu-id="5ecfb-108">개요</span><span class="sxs-lookup"><span data-stu-id="5ecfb-108">Overview</span></span>

<span data-ttu-id="5ecfb-109">Microsoft 팀의 태그를 통해 사용자는 팀의 일부 사용자와 빠르고 쉽게 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ecfb-109">Tags in Microsoft Teams let users quickly and easily connect with a subset of people on a team.</span></span> <span data-ttu-id="5ecfb-110">사용자 지정 태그를 만들고 지정 하 여 특성 (예: 역할, 프로젝트, 기술 또는 위치)을 기준으로 사용자를 분류할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ecfb-110">You can create and assign custom tags to categorize people based on attributes, such as role, project, skill, or location.</span></span> <span data-ttu-id="5ecfb-111">또는 [교대 근무](https://support.microsoft.com/office/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?#PickTab=Shifts) (출시 예정)의 일정 및 교대 정보에 따라 태그를 사용자에 게 자동으로 배정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ecfb-111">Or, tags can be automatically assigned to people based on their schedule and shift information in the [Shifts app](https://support.microsoft.com/office/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?#PickTab=Shifts) (coming soon).</span></span> <span data-ttu-id="5ecfb-112">한 명 또는 여러 팀 구성원에 게 태그를 추가한 후에는 팀의 모든 사용자가 채널을 게시할 수 있도록 하거나 해당 태그를 할당 한 사람만 대화를 시작 하는 등의 작업을 하는 것이 @mentions에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5ecfb-112">After a tag is added to one or multiple team members, it can be used in @mentions by anyone on the team in a channel post or to start a conversation with only those people who are assigned that tag.</span></span>

<span data-ttu-id="5ecfb-113">앞에서 언급 한 것 처럼 팀에는 두 종류의 태그가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ecfb-113">As mentioned earlier, there are two kinds of tags in Teams.</span></span>

- <span data-ttu-id="5ecfb-114">**사용자 지정 태그**: 팀 소유자 및 팀 구성원 (해당 기능이 설정 된 경우)에서 수동으로 태그를 만들고 사용자에 게 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ecfb-114">**Custom tags**: Team owners and team members (if the feature is enabled for them) can manually create and assign tags to people.</span></span> <span data-ttu-id="5ecfb-115">예를 들어 "Designer" 또는 "Radiologist" 태그는 해당 이름을 입력할 필요 없이 팀의 여러 사용자 집합에 도달 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ecfb-115">For example, a "Designer" or "Radiologist" tag will reach those sets of people on a team without having to type their names.</span></span>
- <span data-ttu-id="5ecfb-116">**교대 근무 태그** 지정 (출시 예정):이 기능을 사용 하면 팀의 [교대 근무 앱](https://support.microsoft.com/office/get-started-in-shifts-5f3e30d8-1821-4904-be26-c3cd25a497d6#bkmk_openshiftsappdesktop) 에서 일정 및 이동 그룹 이름과 일치 하는 태그를 자동으로 할당 받습니다.</span><span class="sxs-lookup"><span data-stu-id="5ecfb-116">**Tagging by shift** (coming soon): With this feature, people are automatically assigned tags that match their schedule and shift group name in the [Shifts app](https://support.microsoft.com/office/get-started-in-shifts-5f3e30d8-1821-4904-be26-c3cd25a497d6#bkmk_openshiftsappdesktop) in Teams.</span></span> <span data-ttu-id="5ecfb-117">예를 들어 "EngineerOnCall" 태그는 채팅 또는 채널 게시물에서 태그를 사용 하는 시점에 작업 교대 근무에 예약 된 모든 엔지니어에 게 도달 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ecfb-117">For example, the "EngineerOnCall" tag reaches all engineers who are scheduled in Shifts to work at the time the tag is used in a chat or channel post.</span></span> <span data-ttu-id="5ecfb-118">교대 근무 태그를 사용 하면 사용자가 정보를 빠르게 전달 해야 할 때 교대 근무 직원의 이름을 인식 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5ecfb-118">With tagging by shift, Teams takes the guesswork out of knowing the name of on-shift staff when users need to quickly relay information.</span></span> <span data-ttu-id="5ecfb-119">Shift 키를 사용 하 여 태그를 지정 하는 것은 JDA, 크로노스, AMiON 등의 주요 직원 관리 시스템을 팀의 교대 근무와 통합 하 여 백업할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ecfb-119">Tagging by shift can also be backed by major workforce management systems like JDA, Kronos, and AMiON by integrating them with Shifts in Teams.</span></span> <span data-ttu-id="5ecfb-120">이 기능을 설정 하는 방법에 대해 자세히 알아보려면 [shift 키를 사용한 태그](#set-up-tagging-by-shift-coming-soon)지정을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5ecfb-120">To learn more about how to set up this feature, see [Set up tagging by shift](#set-up-tagging-by-shift-coming-soon).</span></span>

> [!NOTE]
> <span data-ttu-id="5ecfb-121">태그는 개인 채널에서 아직 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5ecfb-121">Tags are not yet supported in private channels.</span></span> <span data-ttu-id="5ecfb-122">미국 정부 커뮤니티 클라우드 (GCC), GCC High 또는 보안 부서 (DoD) 조직에서는 아직 태그를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5ecfb-122">Tags are not yet available in US Government Community Cloud (GCC), GCC High, or Department of Defense (DoD) organizations.</span></span>

## <a name="how-tags-work"></a><span data-ttu-id="5ecfb-123">태그가 작동 하는 방식</span><span class="sxs-lookup"><span data-stu-id="5ecfb-123">How tags work</span></span>

<span data-ttu-id="5ecfb-124">태그는 특정 팀의 사용자에 게 수동으로 추가 하거나 자동으로 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ecfb-124">A tag can be manually added or automatically assigned to a person on a specific team.</span></span> <span data-ttu-id="5ecfb-125">그런 다음 채팅의 **받는** 사람 줄에 있는 @mentions 또는 팀의 표준 채널에 있는 게시물에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ecfb-125">It can then be used in @mentions on the **To** line in a chat or in a post on any standard channel of the team.</span></span> <span data-ttu-id="5ecfb-126">다음은 팀에서 태그를 사용 하는 방법에 대 한 몇 가지 예입니다.</span><span class="sxs-lookup"><span data-stu-id="5ecfb-126">Here's some examples of how tags can be used in Teams:</span></span>

- <span data-ttu-id="5ecfb-127">Store manager는 채널에 알림을 게시 하 여 모든 cashiers에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="5ecfb-127">A store manager posts an announcement to a channel to notify all cashiers.</span></span>
- <span data-ttu-id="5ecfb-128">병원 관리자는 채널의 모든 radiologists에 메시지를 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="5ecfb-128">A hospital administrator sends a message to all radiologists in a channel.</span></span>
- <span data-ttu-id="5ecfb-129">마케팅 관리자는 모든 디자이너와 그룹 채팅을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ecfb-129">A marketing manager starts a group chat with all designers.</span></span>
- <span data-ttu-id="5ecfb-130">Nurse는 모든 통화 cardiologists에 메시지를 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="5ecfb-130">A nurse sends a message to all on-call cardiologists.</span></span> <span data-ttu-id="5ecfb-131">(곧 지원됨)</span><span class="sxs-lookup"><span data-stu-id="5ecfb-131">(coming soon)</span></span>
- <span data-ttu-id="5ecfb-132">시스템 엔지니어가 모든 on shift 필드 엔지니어에 게 알림을 알리기 위해 채널에 공지를 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ecfb-132">A system engineer posts an announcement to a channel to notify all on-shift field engineers.</span></span> <span data-ttu-id="5ecfb-133">(곧 지원됨)</span><span class="sxs-lookup"><span data-stu-id="5ecfb-133">(coming soon)</span></span>

<span data-ttu-id="5ecfb-134">채널 대화에서 태그를 @mentioned 하는 경우 태그와 연결 된 팀 구성원은 다른 @mention 같은 방법으로 알림을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="5ecfb-134">When a tag is @mentioned in a channel conversation, team members associated with the tag will get notified, just like any other @mention.</span></span>

## <a name="manage-custom-tags-for-your-organization"></a><span data-ttu-id="5ecfb-135">조직의 사용자 지정 태그 관리</span><span class="sxs-lookup"><span data-stu-id="5ecfb-135">Manage custom tags for your organization</span></span>

<span data-ttu-id="5ecfb-136">관리자는 Microsoft 팀 관리 센터에서 조직 간에 태그를 사용 하는 방법을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ecfb-136">As an admin, you can control how tags are used across your organization in the Microsoft Teams admin center.</span></span>

![Microsoft 팀 관리 센터의 태그 설정 스크린샷](media/manage-tags-admin-settings.png)

<span data-ttu-id="5ecfb-138">팀은 최대 100 태그를 포함할 수 있으며, 태그에는 최대 100 팀 구성원을 배정할 수 있으며 최대 25 개의 태그를 단일 사용자에 게 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ecfb-138">A team can have up to 100 tags, up to 100 team members can be assigned to a tag, and up to 25 tags can be assigned to a single user.</span></span> 

### <a name="set-who-can-add-custom-tags"></a><span data-ttu-id="5ecfb-139">사용자 지정 태그를 추가할 수 있는 사용자 설정</span><span class="sxs-lookup"><span data-stu-id="5ecfb-139">Set who can add custom tags</span></span>

<span data-ttu-id="5ecfb-140">기본적으로 팀 소유자는 사용자 지정 태그를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ecfb-140">By default, team owners can add custom tags.</span></span> <span data-ttu-id="5ecfb-141">팀 소유자와 팀 구성원이 태그를 만들거나, 편집 하거나, 삭제 하 고, 관리 하는 데 사용할 수 있도록이 설정을 변경 하거나 조직의 태그를 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ecfb-141">You can change this setting to allow team owners and team members to create, edit, delete, and manage tags or you can turn off tags for your organization.</span></span>

1. <span data-ttu-id="5ecfb-142">Microsoft 팀 관리 센터의 왼쪽 탐색 모음에서 **조직 전체 설정**  >  **팀 설정을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ecfb-142">In the left navigation of the Microsoft Teams admin center, click **Org-wide settings** > **Teams settings**.</span></span>
2. <span data-ttu-id="5ecfb-143">**태깅**아래에서 다음 옵션 중 하나를 선택 하 **여 태그**옆에 있는을 (를) 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ecfb-143">Under **Tagging**, next to **Tags are managed by**, select one of the following options:</span></span>

    - <span data-ttu-id="5ecfb-144">**팀 소유자 및 구성원**: 팀 소유자 및 구성원이 태그를 관리할 수 있도록 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ecfb-144">**Team owners and members**: Allow team owners and members to manage tags.</span></span>
    - <span data-ttu-id="5ecfb-145">**팀 소유자**: 팀 소유자가 태그를 관리할 수 있도록 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ecfb-145">**Team owners**: Allow team owners to manage tags.</span></span>
    - <span data-ttu-id="5ecfb-146">**사용 안 함**: 태그 끄기.</span><span class="sxs-lookup"><span data-stu-id="5ecfb-146">**Disabled**: Turn off tags.</span></span>

### <a name="configure-custom-tags-settings"></a><span data-ttu-id="5ecfb-147">사용자 지정 태그 설정 구성</span><span class="sxs-lookup"><span data-stu-id="5ecfb-147">Configure custom tags settings</span></span>

<span data-ttu-id="5ecfb-148">조직에서 사용자 지정 태그를 사용 하는 방법을 제어 하도록 다음 태그 설정을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ecfb-148">You can configure the following tags settings to control how custom tags are used across your organization.</span></span>

1. <span data-ttu-id="5ecfb-149">Microsoft 팀 관리 센터의 왼쪽 탐색 모음에서 **조직 전체 설정**  >  **팀 설정을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ecfb-149">In the left navigation of the Microsoft Teams admin center, click **Org-wide settings** > **Teams settings**.</span></span>
2. <span data-ttu-id="5ecfb-150">**태그**아래에서 조직의 요구 사항에 따라 다음을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ecfb-150">Under **Tagging**, set the following, depending on the needs of your organization.</span></span>

    - <span data-ttu-id="5ecfb-151">**팀 소유자가 태그를 관리할 수 있는 사용자를 재정의 하도록**설정: 팀 소유자는 팀 구성원이 팀 내에서 태그를 만들고 관리할 수 있는지 여부와 태그의 값을 각 팀의 기본값을 설정 **하 여** 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ecfb-151">**Let team owners override who can manage tags**: When you turn on this setting, team owners can set whether team members can create and manage tags within a team and the value of the **Tags are managed by** setting is the default value for each team.</span></span> <span data-ttu-id="5ecfb-152">이 설정을 해제 하는 경우 태그를 **관리 하** 는 설정을 팀 당 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5ecfb-152">If you turn off this setting, the **Tags are managed by** setting can't be changed per team.</span></span>
    - <span data-ttu-id="5ecfb-153">**제안 된 기본 태그**:이를 사용 하 여 기본 태그 집합을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ecfb-153">**Suggested default tags**: Use this to add a set of default tags.</span></span> <span data-ttu-id="5ecfb-154">태그는 최대 25 개까지 추가할 수 있으며, 각 태그는 25 자까지 입력할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ecfb-154">You can add up to 25 tags, and each tag can contain a maximum of 25 characters.</span></span> <span data-ttu-id="5ecfb-155">팀 소유자 및 구성원 (해당 기능이 해당 기능을 사용 하도록 설정 된 경우)을 사용 하거나, 해당 제안에 추가 하거나, 새 태그 집합을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ecfb-155">Team owners and members (if the feature is enabled for them) can use these suggestions, add to them, or create a new set of tags.</span></span>
    - <span data-ttu-id="5ecfb-156">**사용자 지정 태그를 만들 수**있습니다 .이 설정을 사용 하면 사용자가 설정한 제안 된 기본 태그 대신 태그를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ecfb-156">**Let custom tags be created**: Turn on this setting to let people add tags other than the suggested default tags that you set.</span></span> <span data-ttu-id="5ecfb-157">이 기능을 끄면 사용자는 제안 된 기본 태그만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ecfb-157">If this is turned off, people can only use the suggested default tags.</span></span> <span data-ttu-id="5ecfb-158">이 기능을 해제 한 경우 하나 이상의 기본 태그를 추가 했는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ecfb-158">If you turn this off, make sure that you add one or more default tags.</span></span>

## <a name="manage-custom-tags-settings-for-a-team"></a><span data-ttu-id="5ecfb-159">팀에 대 한 사용자 지정 태그 설정 관리</span><span class="sxs-lookup"><span data-stu-id="5ecfb-159">Manage custom tags settings for a team</span></span>

<span data-ttu-id="5ecfb-160">팀 소유자가 Microsoft 팀 관리 센터에서 **태그를 관리할 수 있는 사용자를 재정의 하도록** 설정한 경우 팀 소유자는 멤버가 팀 수준에서 태그를 추가할 수 있는지 여부를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ecfb-160">If you turned on the **Let team owners override who can manage tags** setting in the Microsoft Teams admin center, team owners can set whether members can add tags at the team level.</span></span> <span data-ttu-id="5ecfb-161">이렇게 하려면 팀의 **설정** 탭에서 **태그로**이동한 다음 태그를 추가할 수 있는 사용자를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ecfb-161">To do this, on the **Settings** tab for a team, go to **Tags**, and then choose who can add tags.</span></span>

![팀 수준의 태그 설정 스크린샷](media/manage-tags-team-settings.png)

## <a name="use-tags"></a><span data-ttu-id="5ecfb-163">태그 사용</span><span class="sxs-lookup"><span data-stu-id="5ecfb-163">Use tags</span></span>

<span data-ttu-id="5ecfb-164">사용자 지정 태그를 추가 하는 방법과 shift 키를 사용 하 여 태그를 설정 하는 방법에 대해 설명 합니다 (팀에서 이동 하는 앱의 경우).</span><span class="sxs-lookup"><span data-stu-id="5ecfb-164">Here's how to add custom tags and how to set up tagging by shift (if you're using the Shifts app in Teams).</span></span> <span data-ttu-id="5ecfb-165">자세한 내용은 [팀에서 태그를 사용 하 여](https://support.office.com/article/using-tags-in-teams-667bd56f-32b8-4118-9a0b-56807c96d91e)확인해 보세요.</span><span class="sxs-lookup"><span data-stu-id="5ecfb-165">To learn more, check out [Using tags in Teams](https://support.office.com/article/using-tags-in-teams-667bd56f-32b8-4118-9a0b-56807c96d91e).</span></span>

### <a name="create-and-assign-custom-tags"></a><span data-ttu-id="5ecfb-166">사용자 지정 태그 만들기 및 할당</span><span class="sxs-lookup"><span data-stu-id="5ecfb-166">Create and assign custom tags</span></span>

<span data-ttu-id="5ecfb-167">사용자 지정 태그를 만들고 할당 하려면 앱의 왼쪽에서 **팀** 을 선택한 다음 목록에서 팀을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="5ecfb-167">To create and assign custom tags, select **Teams** on the left side of the app, and then find your team in the list.</span></span> <span data-ttu-id="5ecfb-168">**̇ ̇ ̇ 추가 옵션**을 선택한 다음, **태그 관리**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ecfb-168">Select **˙˙˙ More options**, and then choose **Manage tags**.</span></span> <span data-ttu-id="5ecfb-169">여기서는 태그를 만들어 팀 구성원에 게 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ecfb-169">Here, you can create tags and assign them to people on your team.</span></span>

![<span data-ttu-id="5ecfb-170">팀 클라이언트에서 태그를 적용 하는 방법 스크린샷</span><span class="sxs-lookup"><span data-stu-id="5ecfb-170">Screenshot of how to apply tags in the Teams client</span></span> ](media/manage-tags-teams.png)

<span data-ttu-id="5ecfb-171">태그를 삭제 하려면 태그 옆에 있는 **̇ ̇ ̇ 추가 옵션** 을 선택한 다음 **태그 삭제**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ecfb-171">To delete a tag, select **˙˙˙ More options** next to the tag, and then select **Delete tag**.</span></span>

### <a name="set-up-tagging-by-shift-coming-soon"></a><span data-ttu-id="5ecfb-172">교대 근무 태그 설정 (예정 대로)</span><span class="sxs-lookup"><span data-stu-id="5ecfb-172">Set up tagging by shift (coming soon)</span></span>

1. <span data-ttu-id="5ecfb-173">팀에서 [교대 근무 앱](https://support.microsoft.com/office/get-started-in-shifts-5f3e30d8-1821-4904-be26-c3cd25a497d6#bkmk_openshiftsappdesktop)으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ecfb-173">In Teams, go to the [Shifts app](https://support.microsoft.com/office/get-started-in-shifts-5f3e30d8-1821-4904-be26-c3cd25a497d6#bkmk_openshiftsappdesktop).</span></span>
2. <span data-ttu-id="5ecfb-174">[Shift 그룹](https://support.microsoft.com/office/fill-out-a-schedule-in-shifts-2d58df9b-1c6c-4c84-b0c3-835de7ad13ea#bkmk_organizeshiftsbygroup) 을 만들고 역할과 같은 특성 뒤에 이름을 이름으로 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="5ecfb-174">Create [shift groups](https://support.microsoft.com/office/fill-out-a-schedule-in-shifts-2d58df9b-1c6c-4c84-b0c3-835de7ad13ea#bkmk_organizeshiftsbygroup) and name them after an attribute such as a role.</span></span> <span data-ttu-id="5ecfb-175">예를 EngineerOnCall.</span><span class="sxs-lookup"><span data-stu-id="5ecfb-175">For example, EngineerOnCall.</span></span> <span data-ttu-id="5ecfb-176">Shift 그룹 이름에는 태그의 이름이 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5ecfb-176">The shift group name will be the name of the tag.</span></span>
3. <span data-ttu-id="5ecfb-177">팀 구성원에 게 교대 근무를 배정 하 여 [일정을 작성](https://support.microsoft.com/office/fill-out-a-schedule-in-shifts-2d58df9b-1c6c-4c84-b0c3-835de7ad13ea) 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ecfb-177">[Fill out a schedule](https://support.microsoft.com/office/fill-out-a-schedule-in-shifts-2d58df9b-1c6c-4c84-b0c3-835de7ad13ea) by assigning shifts to members of you teams.</span></span> <span data-ttu-id="5ecfb-178">완료 되 면 이동 앱의 오른쪽 위 모서리에서 **팀과 공유**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ecfb-178">When you're finished, in the upper-right corner of the Shifts app, select **Share with team**.</span></span>
4. <span data-ttu-id="5ecfb-179">태그 서비스를 채우기 위해 예정 된 교대 근무에 대해 15 분간 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="5ecfb-179">Wait 15 minutes for the scheduled shifts to populate the tagging service.</span></span>
5. <span data-ttu-id="5ecfb-180">팀에서 태그를 사용 하는 곳 어디에서 든 태그를 사용 하세요.</span><span class="sxs-lookup"><span data-stu-id="5ecfb-180">Use the tag anywhere you use tags in Teams.</span></span>

<span data-ttu-id="5ecfb-181">Shift 키를 사용 하 여 태그를 지정 하면 사용자가 실시간으로 이동 하는 사람에 게 연락을 주고 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ecfb-181">Tagging by shift allows your users to reach the people on-shift in real time.</span></span> <span data-ttu-id="5ecfb-182">알림은 태그를 사용 하 여 채팅을 시작 하거나 채널을 게시할 때 교대 근무 사용자 에게만 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5ecfb-182">Notifications are sent only to those people who are on shift at the time a tag is used to start a chat or in a channel post.</span></span>

## <a name="related-topics"></a><span data-ttu-id="5ecfb-183">관련 항목</span><span class="sxs-lookup"><span data-stu-id="5ecfb-183">Related topics</span></span>

[<span data-ttu-id="5ecfb-184">팀에서 태그 사용</span><span class="sxs-lookup"><span data-stu-id="5ecfb-184">Using tags in Teams</span></span>](https://support.office.com/article/using-tags-in-teams-667bd56f-32b8-4118-9a0b-56807c96d91e)

[<span data-ttu-id="5ecfb-185">Teams에서 조직의 교대 근무 앱 관리</span><span class="sxs-lookup"><span data-stu-id="5ecfb-185">Manage the Shifts app for your organization in Teams</span></span>](expand-teams-across-your-org/shifts/manage-the-shifts-app-for-your-organization-in-teams.md)

[<span data-ttu-id="5ecfb-186">도움말 문서 이동</span><span class="sxs-lookup"><span data-stu-id="5ecfb-186">Shifts Help documentation</span></span>](https://support.microsoft.com/office/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)
