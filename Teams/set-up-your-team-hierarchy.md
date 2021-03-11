---
title: 팀 대상 계층 구조 설정
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: andfried, acolonna
search.appverid: MET150
description: 조직에서 팀 계층 구조를 설정하여 대규모 팀 집합에 콘텐츠를 게시하는 방법에 대해 자세히 알아보겠습니다.
audience: admin
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: fcdae04ce87db82bd5f18e818dcf194fc7ff38c7
ms.sourcegitcommit: 31a585cc0fe6350efacf3a7771d1e590d5e4233c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/10/2021
ms.locfileid: "50615044"
---
# <a name="set-up-your-team-targeting-hierarchy"></a><span data-ttu-id="ed741-103">팀 대상 계층 구조 설정</span><span class="sxs-lookup"><span data-stu-id="ed741-103">Set up your team targeting hierarchy</span></span>

<span data-ttu-id="ed741-104">팀 대상 계층 구조를 설정하면 조직에서 대규모 팀 집합에 콘텐츠를 게시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed741-104">Setting up a team targeting hierarchy will allow your organization to publish content to a large set of teams.</span></span> <span data-ttu-id="ed741-105">팀 대상 계층 구조는 계층 구조의 모든 팀이 서로 관련되는 방법, 사용자가 작업을 게시할 수 있는 팀 및 게시할 권한이 있는 팀을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="ed741-105">The team targeting hierarchy defines how all the teams in your hierarchy are related to each other, which users can publish tasks, and which teams users have permissions to publish to.</span></span> <span data-ttu-id="ed741-106">조직에 대해 팀 대상 계층 구조가 설정되지 않는 한 모든 사용자에 대해 게시 기능을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ed741-106">Publishing features are disabled for all users unless a team targeting hierarchy is set up for your organization.</span></span> <span data-ttu-id="ed741-107">팀 대상 계층 구조를 설정하려면 계층 구조를 정의하는 파일을 만든 다음 Teams에 업로드하여 조직에 적용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed741-107">To set up a team targeting hierarchy, you'll need to create a file that defines the hierarchy and then upload it to Teams to apply it to your organization.</span></span> <span data-ttu-id="ed741-108">스마마가 업로드된 후 Teams 내의 앱은 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed741-108">After the schema is uploaded, apps within Teams can use it.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ed741-109">초기 릴리스의 경우 작업 앱만 계층적 팀을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="ed741-109">For the initial release, only the Tasks app supports hierarchical teams.</span></span>  <span data-ttu-id="ed741-110">조직에 팀 대상 계층 구조를 적용하면 작업 [앱에서](https://support.microsoft.com/office/publish-task-lists-to-create-and-track-work-in-your-organization-095409b3-f5af-40aa-9f9e-339b54e705df) 태스크 게시가 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed741-110">Applying a team targeting hierarchy to your organization will enable [task publishing](https://support.microsoft.com/office/publish-task-lists-to-create-and-track-work-in-your-organization-095409b3-f5af-40aa-9f9e-339b54e705df) in the Tasks app.</span></span> <span data-ttu-id="ed741-111">Microsoft Teams의 다른 영역에는 팀 계층 구조가 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ed741-111">You won't see a hierarchy of teams in other areas of Microsoft Teams.</span></span>

<span data-ttu-id="ed741-112">다음은 Teams의 작업 앱에서 계층 구조를 나타내는 방법에 대한 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="ed741-112">Here's an example of how the hierarchy is represented in the Tasks app in Teams.</span></span> <span data-ttu-id="ed741-113">작업 목록을 만든 후 게시 팀의 구성원은 받는 사람 팀을 선택하여 작업 목록을 보내(게시)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed741-113">After a task list is created, members of the publishing team can then select the recipient teams to send (publish) the task list to.</span></span> <span data-ttu-id="ed741-114">팀을 선택할 때 게시 팀은 계층 구조, 특성 또는 둘 다의 조합을 통해 필터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed741-114">When selecting teams, the publishing team can filter by hierarchy, by attributes, or a combination of both.</span></span><br>

![작업을 게시하는 스크린샷](media/manage-tasks-app-publish.png)

## <a name="terminology"></a><span data-ttu-id="ed741-116">용어</span><span class="sxs-lookup"><span data-stu-id="ed741-116">Terminology</span></span>

<span data-ttu-id="ed741-117">계층을 탐색할 때 다음 용어가 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="ed741-117">The following terms will be important as you navigate hierarchies.</span></span> <span data-ttu-id="ed741-118">팀을 노드라고 **합니다.**</span><span class="sxs-lookup"><span data-stu-id="ed741-118">Teams will be referred to as **nodes**.</span></span>

* <span data-ttu-id="ed741-119">**루트 노드는** 계층 구조에서 가장 상위 노드입니다.</span><span class="sxs-lookup"><span data-stu-id="ed741-119">**Root nodes** are the topmost nodes in the hierarchy.</span></span> <span data-ttu-id="ed741-120">이 예제에서 Retail Communications는 루트 노드입니다.</span><span class="sxs-lookup"><span data-stu-id="ed741-120">In the example, Retail Communications is a root node.</span></span>
* <span data-ttu-id="ed741-121">**부모 노드** 및 **자식 노드는** 연결된 두 노드 간의 관계를 나타내는 용어입니다.</span><span class="sxs-lookup"><span data-stu-id="ed741-121">**Parent nodes** and **child nodes** are terms that represent a relationship between two connected nodes.</span></span> <span data-ttu-id="ed741-122">예제에서 01 지구는 영역 1의 자식 노드입니다.</span><span class="sxs-lookup"><span data-stu-id="ed741-122">In the example, District 01 is a child node of Area 1.</span></span>
* <span data-ttu-id="ed741-123">여러 수준의 자식은 자식이라고 **합니다.**</span><span class="sxs-lookup"><span data-stu-id="ed741-123">Multiple levels of children are referred to as **descendants**.</span></span> <span data-ttu-id="ed741-124">지구 01, Store 01, Store 03, Store 07, District 02 및 District 03은 모두 지역 1의 후원자입니다.</span><span class="sxs-lookup"><span data-stu-id="ed741-124">District 01, Store 01, Store 03, Store 07, District 02, and District 03 are all descendants of Area 1.</span></span>
* <span data-ttu-id="ed741-125">자식이 없는 노드를 리프 **노드라고 합니다.**</span><span class="sxs-lookup"><span data-stu-id="ed741-125">A node with no children is called a **leaf node**.</span></span> <span data-ttu-id="ed741-126">계층 구조의 맨 아래에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed741-126">They are at the bottom of a hierarchy.</span></span>
* <span data-ttu-id="ed741-127">**받는 사람 팀은** 게시할 특정 콘텐츠 집합을 받기 위해 선택된 팀입니다.</span><span class="sxs-lookup"><span data-stu-id="ed741-127">**Recipient teams** are teams that have been selected to receive a specific set of content to be published.</span></span> <span data-ttu-id="ed741-128">리프 노드가 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed741-128">They must be leaf nodes.</span></span>

## <a name="plan-your-hierarchy"></a><span data-ttu-id="ed741-129">계층 구조 계획</span><span class="sxs-lookup"><span data-stu-id="ed741-129">Plan your hierarchy</span></span>

<span data-ttu-id="ed741-130">계층 구조를 정의하는 도마를 만들기 전에 계획을 세우고 조직을 구성할 방법을 결정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed741-130">Before you create the schema that defines your hierarchy, you need to do some planning and decide how you want to shape your organization.</span></span>  <span data-ttu-id="ed741-131">첫 번째 우선 순위 중 하나는 다른 그룹에 작업을 게시해야 하는 조직 그룹을 결정하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ed741-131">One of the first priorities is deciding which organizational groups need to publish tasks to other groups.</span></span> <span data-ttu-id="ed741-132">계층 구조의 각 노드는 작업 그룹 또는 그룹 그룹을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ed741-132">Each node in the hierarchy represents a working group or group of groups.</span></span>

### <a name="permissions-to-publish"></a><span data-ttu-id="ed741-133">게시할 권한</span><span class="sxs-lookup"><span data-stu-id="ed741-133">Permissions to publish</span></span>

<span data-ttu-id="ed741-134">게시 권한은 사용자가 계층 구조의 모든 팀의 구성원인지 여부와 해당 팀 또는 계층 구조의 다른 팀과의 관계에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="ed741-134">Permission to publish depends on whether a user is a member of any teams in the hierarchy plus the relationship of that team or set of teams to other teams in the hierarchy.</span></span>

> [!NOTE]
> <span data-ttu-id="ed741-135">팀의 소유자에게 게시 권한도 부여됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed741-135">The owner of a team is also granted publishing permissions.</span></span>

* <span data-ttu-id="ed741-136">사용자가 계층 구조에 자선이 있는 하나 이상의 팀의 구성원인 경우 해당 사용자는 게시하려는 모든 팀의 구성원이지 않고 해당 후속 팀에 게시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed741-136">If a user is a member of at least one team that has descendants in the hierarchy, that user can publish to those descendants without being a member of all teams they want to publish to.</span></span>
* <span data-ttu-id="ed741-137">사용자가 계층 구조에서 하나 이상의 팀의 구성원이지만 계층 구조에 있는 후속 팀의 구성원이 아닌 경우 해당 사용자는 조직에서 게시된 콘텐츠를 보고 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed741-137">If a user is a member of a least one team in the hierarchy but isn't a member of any team with descendants in the hierarchy, that user can see and receive published content from their organization.</span></span>
* <span data-ttu-id="ed741-138">사용자가 계층 구조의 팀 구성원이 아닌 경우 해당 사용자는 게시 관련 기능을 볼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ed741-138">If a user isn't a member of any team in the hierarchy, that user won't see any publishing-related functionality.</span></span>

### <a name="guidelines"></a><span data-ttu-id="ed741-139">지침</span><span class="sxs-lookup"><span data-stu-id="ed741-139">Guidelines</span></span>

* <span data-ttu-id="ed741-140">조직당 하나의 계층 구조 파일만 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed741-140">There can only be one hierarchy file applied per organization.</span></span> <span data-ttu-id="ed741-141">그러나 하나의 CSV 파일 내에 노드의 고유한 계층으로 조직의 여러 부분을 함께 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed741-141">However, you can include different parts of your organization together as distinct hierarchies of nodes within one CSV file.</span></span> <span data-ttu-id="ed741-142">예를 들어 Contoso Pharmaceuticals에는 약국 루트 노드와 소매 루트 노드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed741-142">For example, Contoso Pharmaceuticals has a Pharmacy root node and a Retail root node.</span></span> <span data-ttu-id="ed741-143">두 루트 노드에는 여러 행의 후원 행이 있으며 둘 사이에는 겹치지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ed741-143">Both root nodes have multiple rows of descendants and there's no overlap between them.</span></span>
* <span data-ttu-id="ed741-144">리프 노드만 발행물의 받는 사람일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed741-144">Only leaf nodes can be recipients of a publication.</span></span> <span data-ttu-id="ed741-145">계층 구조의 다른 노드는 발행물의 받는 사람을 선택하는 데 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="ed741-145">Other nodes in the hierarchy are helpful for selecting recipients of a publication.</span></span>
* <span data-ttu-id="ed741-146">팀은 계층 구조에서 한 번만 표현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed741-146">A team can only be represented one time in a hierarchy.</span></span>
* <span data-ttu-id="ed741-147">계층 구조에는 최대 15,000개 노드가 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed741-147">A hierarchy can contain up to 15,000 nodes.</span></span> <span data-ttu-id="ed741-148">대규모 조직에 대해 이 한도를 높이기 위해 고객과 협력할 계획입니다.</span><span class="sxs-lookup"><span data-stu-id="ed741-148">We plan to work with customers to raise this limit for larger organizations.</span></span>

### <a name="example-hierarchy"></a><span data-ttu-id="ed741-149">예제 계층 구조</span><span class="sxs-lookup"><span data-stu-id="ed741-149">Example hierarchy</span></span>

<span data-ttu-id="ed741-150">예를 들어 다음 계층 구조에서 리콜, 통신 및 HR은 계층 구조의 모든 아래쪽 노드(팀)에 작업을 게시할 수 있지만 북동부 영역은 뉴욕 스토어 및 보스턴 스토어 팀에만 작업을 게시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed741-150">For example, in the following hierarchy, Recall, Communications, and HR can publish tasks to every bottom node (team) in the hierarchy, but Northeast Zone can only publish tasks to the New York Store and Boston Store teams.</span></span> <span data-ttu-id="ed741-151">예제 계층 구조를 사용하면 회수, 통신 및 HR 그룹이 CEO의 혜택 정보 또는 메시지와 같은 회사 전체에 적용되는 작업을 게시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed741-151">The example hierarchy allows the Recall, Communications, and HR groups to publish tasks that apply to the entire company, such as benefits information or messages from the CEO.</span></span> <span data-ttu-id="ed741-152">Northeast Zone은 직원의 일과 같은 작업을 뉴욕 스토어 및 보스턴 스토어 팀에만 게시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed741-152">Northeast Zone can publish tasks like personnel scheduling, weather information, and so on, only to the New York Store and Boston Store teams.</span></span>

![팀 계층적 예제](media/team-targeting-schema-example-new.png)

## <a name="create-your-hierarchy"></a><span data-ttu-id="ed741-154">계층 구조 만들기</span><span class="sxs-lookup"><span data-stu-id="ed741-154">Create your hierarchy</span></span>

> [!NOTE]
> <span data-ttu-id="ed741-155">이 문서의 나머지부분에서는 받는 사람 팀에 작업을 게시하는 컨텍스트에서 팀 계층 구조 설정에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ed741-155">The remainder of this article discusses setting up a team hierarchy in the context of publishing tasks to recipient teams.</span></span> <span data-ttu-id="ed741-156">작업 게시가 활성화되면 태스크 게시가 나타나는 작업 앱 개요는 [Teams에서](https://docs.microsoft.com/MicrosoftTeams/manage-tasks-app) 조직의 작업 앱 관리를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ed741-156">Refer to [Manage the Tasks app for your organization in Teams](https://docs.microsoft.com/MicrosoftTeams/manage-tasks-app) for an overview of the Tasks app, where task publishing appears when enabled.</span></span>

<span data-ttu-id="ed741-157">계층 구조를 정의하는척도는 CSV(콤마로 구분된 값) 파일을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed741-157">The schema that defines your hierarchy is based on a comma-separated values (CSV) file.</span></span> <span data-ttu-id="ed741-158">CSV 파일의 각 행은 팀 계층 구조 내의 하나의 노드에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="ed741-158">Each row in the CSV file corresponds to one node within the hierarchy of teams.</span></span> <span data-ttu-id="ed741-159">각 행에는 계층 구조 내에서 노드의 이름을 입력하고, 선택적으로 팀에 연결하며, 이를 지원하는 앱의 팀을 필터링하는 데 사용할 수 있는 특성을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="ed741-159">Each row contains information that names the node within the hierarchy, optionally links it to a team, and includes attributes that can be used to filter teams in apps that support it.</span></span>

<span data-ttu-id="ed741-160">또한 게시 팀에서 받는 사람 팀에 보낸 콘텐츠를 구성하는 데 사용할 수 있는 범주인 버킷을 정의하여 관련 콘텐츠를 보다 쉽게 보고 정렬하고 집중할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed741-160">You can also define **buckets**, which are categories that the publishing team can use to organize content sent to recipient teams to make it easier for them to view, sort, and focus on relevant content.</span></span>

### <a name="add-required-columns"></a><span data-ttu-id="ed741-161">필요한 열 추가</span><span class="sxs-lookup"><span data-stu-id="ed741-161">Add required columns</span></span>

<span data-ttu-id="ed741-162">CSV 파일에는 첫 번째 열부터 다음 세 개의 열이 다음 순서로 포함되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed741-162">The CSV file must contain the following three columns, in the following order, starting at the first column.</span></span> <span data-ttu-id="ed741-163">태스크를 수신하려면 노드를 팀에 연결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed741-163">A node must be linked to a team for it to receive tasks.</span></span>

| <span data-ttu-id="ed741-164">열 이름</span><span class="sxs-lookup"><span data-stu-id="ed741-164">Column name</span></span>   | <span data-ttu-id="ed741-165">필수</span><span class="sxs-lookup"><span data-stu-id="ed741-165">Required</span></span> | <span data-ttu-id="ed741-166">설명</span><span class="sxs-lookup"><span data-stu-id="ed741-166">Description</span></span>   |
----------------|----------|---------------|
| <span data-ttu-id="ed741-167">DisplayName</span><span class="sxs-lookup"><span data-stu-id="ed741-167">DisplayName</span></span>    | <span data-ttu-id="ed741-168">예</span><span class="sxs-lookup"><span data-stu-id="ed741-168">Yes</span></span>      | <span data-ttu-id="ed741-169">이 필드는 노드의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="ed741-169">This field is the name of the node.</span></span> <span data-ttu-id="ed741-170">이름은 최대 100자까지 길고 A-Z, a-z 및 0-9 문자만 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed741-170">The name can be up to 100 characters long and contain only the characters A-Z, a-z, and 0-9.</span></span> <span data-ttu-id="ed741-171">노드 이름은 고유해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed741-171">Node names must be unique.</span></span> |
| <span data-ttu-id="ed741-172">ParentName</span><span class="sxs-lookup"><span data-stu-id="ed741-172">ParentName</span></span>    | <span data-ttu-id="ed741-173">예</span><span class="sxs-lookup"><span data-stu-id="ed741-173">Yes</span></span>       | <span data-ttu-id="ed741-174">부모 노드의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="ed741-174">This is the name of the parent node.</span></span> <span data-ttu-id="ed741-175">여기서 지정한 값은 부모 노드의 **DisplayName** 필드의 값과 정확히 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed741-175">The value you specify here must match the value in the **DisplayName** field of the parent node exactly.</span></span> <span data-ttu-id="ed741-176">두 개 이상의 상위 노드를 추가하려는 경우 세미코론(세미코론)으로 각 부모 노드 이름을 ;).</span><span class="sxs-lookup"><span data-stu-id="ed741-176">If you want to add more than one parent node, separate each parent node name with a semicolon (;).</span></span> <span data-ttu-id="ed741-177">최대 25개 부모 노드를 추가할 수 있으며 각 상위 노드 이름은 최대 2500자까지 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed741-177">You can add up to 25 parent nodes, and each parent node name can be up to 2500 characters long.</span></span> <span data-ttu-id="ed741-178">노드는 상위 노드가 루트 노드인 경우 여러 개의 상위 노드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed741-178">A node can have multiple parent nodes only if the parent nodes are root nodes.</span></span>   <br><br><span data-ttu-id="ed741-179">**중요** 계층 구조에서 상위 상위에 있는 부모가 계층 구조의 하위 하위 노드를 참조하는 루프를 만들지 않도록 주의하세요.</span><span class="sxs-lookup"><span data-stu-id="ed741-179">**IMPORTANT** Be careful not to create a loop where a parent higher up in the hierarchy references a child node lower in the hierarchy.</span></span> <span data-ttu-id="ed741-180">지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ed741-180">This isn't supported.</span></span> |
| <span data-ttu-id="ed741-181">TeamId</span><span class="sxs-lookup"><span data-stu-id="ed741-181">TeamId</span></span>        | <span data-ttu-id="ed741-182">예. 팀에서 작업을 게시하거나 부모 노드에서 작업을 수신하는 경우</span><span class="sxs-lookup"><span data-stu-id="ed741-182">Yes, if the team publishes tasks or receives tasks from a parent node</span></span>       | <span data-ttu-id="ed741-183">여기에는 노드를 연결하려는 팀의 ID가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed741-183">This contains the ID of the team you want to link a node to.</span></span> <span data-ttu-id="ed741-184">각 노드는 고유한 팀을 참조해야 있으므로 각 TeamId 값은 계층 구조 파일에 한 번만 나타날 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed741-184">Each node must refer to a unique team, so each TeamId value may appear only once in the hierarchy file.</span></span> <span data-ttu-id="ed741-185">노드를 연결하려는 팀의 ID를 얻으면 다음 PowerShell 명령을 `Get-Team | Export-Csv TeamList.csv` 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="ed741-185">To get the ID of a team you want to link a node to, run the following PowerShell command: `Get-Team | Export-Csv TeamList.csv`.</span></span> <span data-ttu-id="ed741-186">이 명령은 조직의 팀을 나열하고 각 팀의 이름 및 ID를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="ed741-186">This command lists the teams in your organization and includes the name and ID for each team.</span></span> <span data-ttu-id="ed741-187">연결하려는 팀의 이름을 찾은 다음 이 필드에 ID를 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="ed741-187">Find the name of the team you want to link to, and then copy the ID into this field.</span></span>|

> [!NOTE]
> <span data-ttu-id="ed741-188">노드가 루트 노드 또는 리프 노드가 아니고 게시 및 보고에 해당하는 권한을 부여하기 위해 팀 멤버 자격이 필요하지 않은 경우 TeamId를 비워 두면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed741-188">If a node isn't a root node or a leaf node and you don't need the team membership to grant the corresponding permissions for publishing and reporting, you can leave the TeamId blank.</span></span> <span data-ttu-id="ed741-189">이 메서드는 받는 사람 팀을 선택할 때 또는 해당 팀이 없는 완료 보고서를 볼 때 더 세분성을 추가하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed741-189">This method can be used to add more granularity when choosing recipient teams or for viewing completion reports without having a corresponding team.</span></span>

### <a name="add-attribute-columns"></a><span data-ttu-id="ed741-190">특성 열 추가</span><span class="sxs-lookup"><span data-stu-id="ed741-190">Add attribute columns</span></span>

<span data-ttu-id="ed741-191">필요한 세 열을 추가한 후 선택적 특성 열을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed741-191">After you add the three required columns, you can add optional attribute columns.</span></span> <span data-ttu-id="ed741-192">이러한 특성은 작업을 게시할 속성을 보다 쉽게 선택할 수 있도록 노드를 필터링하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed741-192">These attributes can be used to filter nodes so that you can more easily select the ones you want to publish tasks to.</span></span> <span data-ttu-id="ed741-193">해당 특성에 대한 값이 상호 배타적인지 여부에 따라 특성을 정의하는 두 가지 방법이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed741-193">There are two ways to define your attributes, depending on whether values for that attribute are mutually exclusive.</span></span>

|<span data-ttu-id="ed741-194">특성을 추가하는 방법</span><span class="sxs-lookup"><span data-stu-id="ed741-194">Ways to add attributes</span></span>|<span data-ttu-id="ed741-195">설명</span><span class="sxs-lookup"><span data-stu-id="ed741-195">Description</span></span> |<span data-ttu-id="ed741-196">예제</span><span class="sxs-lookup"><span data-stu-id="ed741-196">Example</span></span>  |
|---|---------|---------|
|<span data-ttu-id="ed741-197">특성의 값이 상호 배타적이면 지정한 열 이름이 특성의 이름이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed741-197">If the values for an attribute are mutually exclusive, the column name you specify becomes the name of the attribute.</span></span>|<span data-ttu-id="ed741-198">각 행은 해당 특성에 대한 하나의 값을 포함할 수 있으며, 각 특성 열에는 최대 50개 고유 값이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed741-198">Each row can contain one value for that attribute, and each attribute column can have up to 50 unique values.</span></span> <span data-ttu-id="ed741-199">각 값은 최대 100자까지 길 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed741-199">Each value can be up to 100 characters long.</span></span> <span data-ttu-id="ed741-200">특성 열에 지정한 특성 값 집합은 팀 대상 계층 구조를 사용하여 받는 사람 팀을 선택할 때 해당 특성에 대한 필터 값으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed741-200">The set of attribute values you specify in the attribute column will be displayed as filter values for that attribute when selecting recipient teams using the team targeting hierarchy.</span></span>|<span data-ttu-id="ed741-201">사용자가 레이아웃으로 저장소를 필터링할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed741-201">You want users to be able to filter stores by layout.</span></span> <span data-ttu-id="ed741-202">저장소에 레이아웃이 하나만 있기 때문에 이 특성의 값은 상호 배타적입니다.</span><span class="sxs-lookup"><span data-stu-id="ed741-202">The values for this attribute are mutually exclusive because a store can have only one layout.</span></span> <br><br><span data-ttu-id="ed741-203">레이아웃에 따라 저장소를 필터링하는 특성을 추가하기 위해 저장소 레이아웃이라는 열을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="ed741-203">To add an attribute to filter stores by layout, add a column named Store layout.</span></span> <span data-ttu-id="ed741-204">이 예제에서는 Store 레이아웃 특성에 대한 값이 Compact, Standard 및 Large입니다.</span><span class="sxs-lookup"><span data-stu-id="ed741-204">In this example, values for the Store layout attribute are Compact, Standard, and Large.</span></span>
|<span data-ttu-id="ed741-205">특성에 대해 여러 값을 표시해야 하는 경우 값이 상호 배타적이지 않은 경우 열 이름에 **대해 AttributeName:UniqueValue** 형식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ed741-205">If you need to indicate multiple values for an attribute and the values aren't mutually exclusive, use the **AttributeName:UniqueValue** format for the column names.</span></span> <br><br><span data-ttu-id="ed741-206">**중요** 영어 전용 콜론(:) 유니코드는 특성 열분리자로 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ed741-206">**IMPORTANT** Make sure to use the English-only colon (:) as unicode isn't supported as an attribute column delimiter.</span></span> |<span data-ttu-id="ed741-207">콜론 앞에 있는 텍스트 문자열(:) 는 특성의 이름이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed741-207">The text string before the colon (:) becomes the name of the attribute.</span></span> <span data-ttu-id="ed741-208">콜론 앞에 동일한 텍스트 문자열이 포함된 모든 열(:) 필터링 메뉴의 섹션으로 그룹화됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed741-208">All columns that contain the same text string before the colons (:) are grouped together into a section in the filtering menu.</span></span> <span data-ttu-id="ed741-209">콜론 다음의 각 문자열은 이 섹션의 값이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed741-209">Each of the strings after the colon become the values for that section.</span></span><br><br><span data-ttu-id="ed741-210">각 행에는 해당 특성에 대한 값이 0(0) 또는 1일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed741-210">Each row can have a value of 0 (zero) or 1 for that attribute.</span></span> <span data-ttu-id="ed741-211">값이 0이면 특성이 노드에 적용되지 않습니다. 1 값은 특성이 해당 노드에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed741-211">A value of 0 means that the attribute doesn't apply to the node and a value of 1 means that the attribute applies to that node.</span></span>|<span data-ttu-id="ed741-212">사용자가 부서에 따라 저장소를 필터링할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed741-212">You want users to be able to filter stores by department.</span></span> <span data-ttu-id="ed741-213">저장소에 여러 부서가 있을 수 있으므로 이 특성의 값은 상호 배타적이지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ed741-213">A store can have multiple departments and so the values for this attribute aren't mutually exclusive.</span></span><br><br><span data-ttu-id="ed741-214">이 예제에서는 Departments:Clothing, Departments:Electronics, Departments:Foods, Departments:Home and Garden, Departments:Sporting goods를 특성 열로 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="ed741-214">In this example, we add Departments:Clothing, Departments:Electronics, Departments:Foods, Departments:Home and Garden, Departments:Sporting goods as attribute columns.</span></span> <span data-ttu-id="ed741-215">부서는 특성 이름이 며 사용자는 의류, 전자 제품, 식품, 가정 및 정원 및 스포츠 제품 부서를 통해 필터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed741-215">Departments becomes the attribute name and users can filter by the Clothing, Electronics, Foods, Home and Garden, and Sporting goods departments.</span></span>|

<span data-ttu-id="ed741-216">특성 열을 추가할 때 다음을 염두에 두어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed741-216">When you add an attribute column, keep the following in mind:</span></span>

* <span data-ttu-id="ed741-217">지정한 열 이름 또는 콜론 앞에 지정한 열 이름(:) 는 특성의 이름이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed741-217">The column name you specify or the column name that you specify before the colon (:) becomes the name of the attribute.</span></span> <span data-ttu-id="ed741-218">이 값은 계층 구조를 사용하는 Teams 앱에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed741-218">This value will be displayed in the Teams apps that use the hierarchy.</span></span>
* <span data-ttu-id="ed741-219">계층 구조에 최대 50개 특성 열을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed741-219">You can have up to 50 attribute columns in your hierarchy.</span></span>
* <span data-ttu-id="ed741-220">열 이름은 최대 100자까지 사용할 수 있으며 A-Z, a-z 및 0-9 및 공백만 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed741-220">The column name can be up to 100 characters long and contain only the characters A-Z, a-z, and 0-9, and spaces.</span></span> <span data-ttu-id="ed741-221">열 이름은 고유해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed741-221">Column names must be unique.</span></span>

### <a name="add-bucket-columns"></a><span data-ttu-id="ed741-222">버킷 열 추가</span><span class="sxs-lookup"><span data-stu-id="ed741-222">Add bucket columns</span></span>

<span data-ttu-id="ed741-223">버킷 열을 추가하여 작업을 구성할 수 있는 그룹화인 버킷을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed741-223">You can add bucket columns to create buckets, which are groupings into which tasks can be organized.</span></span> <span data-ttu-id="ed741-224">각 버킷은 CSV 파일에서 자체 열을 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="ed741-224">Each bucket gets its own column in the CSV file.</span></span> <span data-ttu-id="ed741-225">만든 버킷은 게시 팀에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed741-225">The buckets you create are made available to the publishing team.</span></span> <span data-ttu-id="ed741-226">그런 다음 게시 팀은 이러한 버킷을 사용하여 받는 사람 팀에 대한 작업을 분류할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed741-226">The publishing team can then use these buckets to categorize tasks for the recipient teams.</span></span> <span data-ttu-id="ed741-227">팀에 버킷이 아직 없는 경우 태스크가 게시될 때 버킷이 수요에 따라 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed741-227">If a bucket doesn't already exist on a team, buckets are created on-demand when tasks are published.</span></span>

<span data-ttu-id="ed741-228">작업 항목을 한 번씩 중앙에서 분류하여 게시 팀은 작업 목록을 받는 수십, 수백 또는 수천 명의 받는 사람 팀에 대해 작업 목록을 미리 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed741-228">By categorizing the work items one time centrally, the publishing team can pre-organize the task list for all the tens, hundreds, or thousands of recipient teams that receive the task list.</span></span> <span data-ttu-id="ed741-229">그런 다음 받는 사람 팀은 작업과 가장 관련된 영역에 집중하기 위해 버킷으로 작업을 정렬하고 필터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed741-229">The recipient teams can then sort and filter their tasks by bucket to focus on the area most relevant to their work.</span></span>

<span data-ttu-id="ed741-230">버킷 열을 추가할 때 다음을 유의합니다.</span><span class="sxs-lookup"><span data-stu-id="ed741-230">When you add a bucket column, note the following:</span></span>

* <span data-ttu-id="ed741-231">열 이름은 버킷의 이름이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed741-231">The column name becomes the name of the bucket.</span></span> <span data-ttu-id="ed741-232">지정한 각 버킷은 계층 구조를 사용하는 Teams 앱의 버킷 목록에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed741-232">Each bucket you specify will appear in the Buckets list in the Teams apps that use the hierarchy.</span></span>
* <span data-ttu-id="ed741-233">중요한 정보는 버킷 이름에 포함하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="ed741-233">We recommend that you don't include sensitive information in bucket names.</span></span> <span data-ttu-id="ed741-234">현재 게시 팀은 게시를 통해 버킷을 제거할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ed741-234">At this time, publishing teams can't remove a bucket through publishing after it's created.</span></span>
* <span data-ttu-id="ed741-235">열 이름은 해시태그(#) 앞에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed741-235">The column name must be preceded by a hashtag (#).</span></span> <span data-ttu-id="ed741-236">최대 100자까지 길고 A-Z, a-z 및 0-9 문자만 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed741-236">It can be up to 100 characters long and contain only the characters A-Z, a-z, and 0-9.</span></span> <span data-ttu-id="ed741-237">예를 들어 #Operations #Frozen 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed741-237">For example, #Operations and #Frozen Goods.</span></span>
* <span data-ttu-id="ed741-238">계층 구조에는 최대 25개 버킷 열이 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed741-238">A hierarchy may contain up to 25 bucket columns.</span></span> <span data-ttu-id="ed741-239">대규모 조직에 대한 이 제한을 높이기 위해 고객과 협력할 계획입니다.</span><span class="sxs-lookup"><span data-stu-id="ed741-239">We plan to work with customers to increase this limit for larger organizations.</span></span>

### <a name="example"></a><span data-ttu-id="ed741-240">예제</span><span class="sxs-lookup"><span data-stu-id="ed741-240">Example</span></span>

<span data-ttu-id="ed741-241">이전 이미지에 표시된 계층 구조를 지원하기 위해 만들어질 Schema CSV 파일의 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ed741-241">Here's an example of a schema CSV file that would be created to support the hierarchy shown in the previous image.</span></span> <span data-ttu-id="ed741-242">이 계획에는 다음이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed741-242">This schema contains the following:</span></span>

* <span data-ttu-id="ed741-243">이라는 세 개의 필수 열 `TargetName` `ParentName` 및 `TeamId`</span><span class="sxs-lookup"><span data-stu-id="ed741-243">Three required columns named `TargetName`, `ParentName`, and `TeamId`</span></span>
* <span data-ttu-id="ed741-244">이라는 3개의 특성 `Store layout` `Departments:Clothing` 열 및 `Departments:Foods`</span><span class="sxs-lookup"><span data-stu-id="ed741-244">Three attribute columns named `Store layout`, `Departments:Clothing`, and `Departments:Foods`</span></span>
* <span data-ttu-id="ed741-245">이라는 세 개의 버킷 열 `Fresh Foods` `Frozen Foods` 및 `Women's Wear`</span><span class="sxs-lookup"><span data-stu-id="ed741-245">Three bucket columns named `Fresh Foods`, `Frozen Foods`, and `Women's Wear`</span></span>

<span data-ttu-id="ed741-246">특성에는 `Store layout` , 및 를 포함 하는 `Compact` 값이 `Standard` `Large` 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed741-246">The `Store layout` attribute has values that include `Compact`, `Standard`, and `Large`.</span></span> <span data-ttu-id="ed741-247">특성 `Departments` 열은 (0) 또는 의 값으로 설정할 `0` 수 `1` 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed741-247">The `Departments` attribute columns can be set to a value of `0` (zero) or `1`.</span></span> <span data-ttu-id="ed741-248">레이아웃 및 특성은 위의 `Store` `Departments` 이미지에 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ed741-248">The `Store` layout and `Departments` attributes aren't shown in the image above.</span></span> <span data-ttu-id="ed741-249">노드 항목에 특성을 추가할 수 있는 방법을 보여 주기 위해 여기에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed741-249">They're added here to help show how attributes can be added to node entries.</span></span> <span data-ttu-id="ed741-250">세 개의 버킷 열도 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="ed741-250">The same is true for the three bucket columns.</span></span>

```CSV
TargetName,ParentName,TeamId,Store layout,Departments:Clothing,Departments:Foods,#Fresh Foods,#Frozen Foods,#Women's Wear
Recall,,db23e6ba-04a6-412a-95e8-49e5b01943ba,,,,,,
Communications,,145399ce-a761-4843-a110-3077249037fc,,,,,,
HR,,,,,,,,
East Regional Office,,,,,,,,
West Regional Office,,,,,,,,
Northeast Zone,East Regional Office,,,,,,,
Southeast Zone,East Regional Office,,,,,,,
New York Store,Northeast Zone,e2ba65f6-25e7-488b-b8f0-b8562d5de60a,Large,1,1,,,
Boston Store,Northeast Zone,0454f08a-0507-437c-969a-682eb2fae7fc,Standard,1,1,,,
Miami Store,Southeast Zone,619d6e4e-5f68-4b36-8e1f-16c98d7396c1,Compact,0,1,,,
New Orleans Store,Southeast Zone,6be960b8-72af-4561-a343-9ac4711874eb,Compact,0,1,,,
Seattle Store,West Regional Zone,487c0d20-4e55-4dc2-8187-a24c826e0fee,Standard,1,1,,,
Los Angeles Store,West Regional Zone,204a1287-2efb-4a8a-88e0-56fbaf5a2389,Large,1,1,,,
```

## <a name="apply-your-hierarchy"></a><span data-ttu-id="ed741-251">계층 구조 적용</span><span class="sxs-lookup"><span data-stu-id="ed741-251">Apply your hierarchy</span></span>

<span data-ttu-id="ed741-252">Schema CSV 파일에서 계층 구조를 정의한 후 Teams에 업로드할 준비가 된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ed741-252">After you've defined your hierarchy in the schema CSV file, you're ready to upload it to Teams.</span></span> <span data-ttu-id="ed741-253">이렇게 하여 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="ed741-253">To do this, run the following command.</span></span> <span data-ttu-id="ed741-254">이 단계를하려면 전역 관리자 또는 Teams 서비스 관리자가 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed741-254">You must be a global admin or Teams service admin to do this step.</span></span>

```powershell
Set-TeamTargetingHierarchy -FilePath "C:\ContosoTeamSchema.csv"
```

### <a name="update-your-hierarchy"></a><span data-ttu-id="ed741-255">계층 구조 업데이트</span><span class="sxs-lookup"><span data-stu-id="ed741-255">Update your hierarchy</span></span>

<span data-ttu-id="ed741-256">위와 동일한 PowerShell 명령을 사용하여 이전 계층 구조를 대체하기 위해 새 계층 구조를 업로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed741-256">You can upload a new hierarchy to replace the old one using the same PowerShell command as above.</span></span> <span data-ttu-id="ed741-257">새 계층 구조를 업로드할 때마다 이전 계층 구조가 대체됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed741-257">Each time you upload a new hierarchy, it replaces the previous hierarchy.</span></span>

### <a name="check-the-status-of-your-hierarchy"></a><span data-ttu-id="ed741-258">계층 구조 상태 확인</span><span class="sxs-lookup"><span data-stu-id="ed741-258">Check the status of your hierarchy</span></span>

<span data-ttu-id="ed741-259">다음 명령을 실행하여 계층 구조 업로드 상태를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed741-259">You can run the following command to check the status of your hierarchy upload.</span></span>

```powershell
Get-TeamTargetingHierarchyStatus
```

<span data-ttu-id="ed741-260">명령은 다음 필드를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="ed741-260">The command will return the following fields:</span></span>

<span data-ttu-id="ed741-261">필드</span><span class="sxs-lookup"><span data-stu-id="ed741-261">Field</span></span>|<span data-ttu-id="ed741-262">설명</span><span class="sxs-lookup"><span data-stu-id="ed741-262">Description</span></span>
-----|------------
<span data-ttu-id="ed741-263">ID</span><span class="sxs-lookup"><span data-stu-id="ed741-263">Id</span></span> | <span data-ttu-id="ed741-264">업로드에 대한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="ed741-264">The unique ID for the upload.</span></span>
<span data-ttu-id="ed741-265">상태</span><span class="sxs-lookup"><span data-stu-id="ed741-265">Status</span></span> | <span data-ttu-id="ed741-266">상태 업로드.</span><span class="sxs-lookup"><span data-stu-id="ed741-266">Upload status.</span></span> <span data-ttu-id="ed741-267">값에는 **시작,** **유효성 검사,** **성공** 및 **실패가 포함됩니다.**</span><span class="sxs-lookup"><span data-stu-id="ed741-267">Values include **Starting**, **Validating**, **Successful**, and **Failed**</span></span>
<span data-ttu-id="ed741-268">ErrorDetails</span><span class="sxs-lookup"><span data-stu-id="ed741-268">ErrorDetails</span></span> | <span data-ttu-id="ed741-269">업로드 오류가 있는 경우 세부 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="ed741-269">Details if there's an upload error.</span></span> <span data-ttu-id="ed741-270">오류 세부 정보에 대한 자세한 내용은 문제 해결 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ed741-270">For more information about the error details, see the Troubleshooting section.</span></span> <span data-ttu-id="ed741-271">오류가 없는 경우 이 필드는 비어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed741-271">If there's no error, this field is blank.</span></span>
<span data-ttu-id="ed741-272">LastUpdatedAt</span><span class="sxs-lookup"><span data-stu-id="ed741-272">LastUpdatedAt</span></span> | <span data-ttu-id="ed741-273">타임스탬프 및 파일이 마지막으로 업데이트된 날짜입니다.</span><span class="sxs-lookup"><span data-stu-id="ed741-273">Timestamp and date of when the file was last updated.</span></span>
<span data-ttu-id="ed741-274">LastModifiedBy</span><span class="sxs-lookup"><span data-stu-id="ed741-274">LastModifiedBy</span></span> | <span data-ttu-id="ed741-275">파일을 수정한 마지막 사용자의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="ed741-275">The ID of the last user who modified the file.</span></span>
<span data-ttu-id="ed741-276">FileName</span><span class="sxs-lookup"><span data-stu-id="ed741-276">FileName</span></span> | <span data-ttu-id="ed741-277">CSV의 파일 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="ed741-277">The file name of the CSV.</span></span>

## <a name="remove-your-hierarchy"></a><span data-ttu-id="ed741-278">계층 구조 제거</span><span class="sxs-lookup"><span data-stu-id="ed741-278">Remove your hierarchy</span></span>

<span data-ttu-id="ed741-279">조직의 모든 사용자에  대해 게시된 목록 탭을 즉시 사용하지 않도록 설정하려면 계층 구조를 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed741-279">If you want to immediately disable the **Published lists** tab for all users in your organization, you can remove your hierarchy.</span></span> <span data-ttu-id="ed741-280">사용자는 게시된 목록 탭  또는 탭의 기능에 액세스할 수 없습니다.  여기에는 게시, 초안 목록에 액세스, 게시, 게시, 게시 및 중복 목록 및 보고를 볼 수 있는 새 작업 목록을 만드는 기능을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="ed741-280">Users won't have access to the **Published lists** tab or any of the functionalities on the tab.  This includes the ability to create new task lists to publish, access draft lists, publish, unpublish, and duplicate lists, and view reporting.</span></span> <span data-ttu-id="ed741-281">계층 구조를 제거해도 이전에 게시된 작업이 게시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ed741-281">Removing the hierarchy doesn't unpublish tasks that were previously published.</span></span> <span data-ttu-id="ed741-282">이러한 작업은 받는 사람 팀이 완료할 수 있도록 계속 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed741-282">These tasks will remain available for recipient teams to complete.</span></span>

<span data-ttu-id="ed741-283">계층 구조를 제거하려면 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="ed741-283">To remove your hierarchy, run the following command.</span></span> <span data-ttu-id="ed741-284">이 단계를 수행하려면 관리자가 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed741-284">You must be an admin to perform this step.</span></span>

```powershell
Remove-TeamTargetingHierarchy
```

<span data-ttu-id="ed741-285">삭제를 확인할 때 상태 메시지는 여전히 이전의 도마가 표시되고, 다시 삭제하려고 하면 개체가 null인 오류가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed741-285">When confirming deletion, the status message will still display the previous schema is present, although attempting to delete again returns an error that the object is null.</span></span>

## <a name="create-a-sample-hierarchy"></a><span data-ttu-id="ed741-286">샘플 계층 구조 만들기</span><span class="sxs-lookup"><span data-stu-id="ed741-286">Create a sample hierarchy</span></span>

### <a name="install-the-teams-powershell-module"></a><span data-ttu-id="ed741-287">Teams PowerShell 모듈 설치</span><span class="sxs-lookup"><span data-stu-id="ed741-287">Install the Teams PowerShell module</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ed741-288">이 단계를 수행하려면 PowerShell 갤러리에서 Teams PowerShell 공개 미리 보기 모듈을 설치하고 [사용해야 합니다.](https://www.powershellgallery.com/packages/MicrosoftTeams/)</span><span class="sxs-lookup"><span data-stu-id="ed741-288">To perform this step, you must install and use the Teams PowerShell public preview module from the [PowerShell Gallery](https://www.powershellgallery.com/packages/MicrosoftTeams/).</span></span> <span data-ttu-id="ed741-289">모듈을 설치하는 방법에 대한 단계는 [Teams PowerShell 설치를 참조하세요.](teams-powershell-install.md)</span><span class="sxs-lookup"><span data-stu-id="ed741-289">For steps on how to install the module, see [Install Teams PowerShell](teams-powershell-install.md).</span></span>

### <a name="sample-script"></a><span data-ttu-id="ed741-290">샘플 스크립트</span><span class="sxs-lookup"><span data-stu-id="ed741-290">Sample script</span></span>

<span data-ttu-id="ed741-291">다음 스크립트를 사용하여 팀을 만들고 .csv 파일을 Microsoft Teams 테넌트에 업로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed741-291">The following script can be used to create the teams and upload a .csv file to your Microsoft Teams tenant.</span></span> <span data-ttu-id="ed741-292">기존 계층 구조가 있는 경우 이 스크립트가 대체됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed741-292">If you have an existing hierarchy, this script will replace it.</span></span>

#### <a name="create-teams-for-a-simple-hierarchy"></a><span data-ttu-id="ed741-293">간단한 계층 구조에 대한 팀 만들기</span><span class="sxs-lookup"><span data-stu-id="ed741-293">Create teams for a simple hierarchy</span></span>

```powershell
$tm1 = New-Team -DisplayName "HQ"
$tm2 = New-Team -DisplayName "North"
$tm3 = New-Team -DisplayName "Store 1"
$tm4 = New-Team -DisplayName "Store 2"
$tm5 = New-Team -DisplayName "South"
$tm6 = New-Team -DisplayName "Store 3"
$tm7 = New-Team -DisplayName "Store 4"
```

#### <a name="use-team-data-to-create-comma-separated-output-displayname-parentname-teamid"></a><span data-ttu-id="ed741-294">팀 데이터를 사용하여 콤마로 구분된 출력을 만들 수 있습니다(DisplayName, ParentName, TeamId)</span><span class="sxs-lookup"><span data-stu-id="ed741-294">Use team data to create comma-separated output (DisplayName, ParentName, TeamId)</span></span>

```powershell
$csvOutput = "DisplayName" + "," + "ParentName" + "," + "TeamId" + "`n"
$csvOutput = $csvOutput + $tm1.DisplayName + "," + "," + $tm1.GroupID + "`n"
$csvOutput = $csvOutput + $tm2.DisplayName + "," + $tm1.DisplayName + "," + $tm2.GroupID + "`n"
$csvOutput = $csvOutput + $tm3.DisplayName + "," + $tm2.DisplayName + "," + $tm3.GroupID + "`n"
$csvOutput = $csvOutput + $tm4.DisplayName + "," + $tm2.DisplayName + "," + $tm4.GroupID + "`n"
$csvOutput = $csvOutput + $tm5.DisplayName + "," + $tm1.DisplayName + "," + $tm5.GroupID + "`n"
$csvOutput = $csvOutput + $tm6.DisplayName + "," + $tm5.DisplayName + "," + $tm6.GroupID + "`n"
$csvOutput = $csvOutput + $tm7.DisplayName + "," + $tm5.DisplayName + "," + $tm7.GroupID 
```

#### <a name="save-output-to-a-csv-file-in-the-downloads-folder"></a><span data-ttu-id="ed741-295">다운로드 폴더에서 .csv 파일에 출력 **저장**</span><span class="sxs-lookup"><span data-stu-id="ed741-295">Save output to a .csv file in the **Downloads** folder</span></span>

```powershell
$csvOutputPath = $env:USERPROFILE + "\downloads\testhierarchy-" + (Get-Date -Format "yyyy-MM-dd-hhmmss") + ".csv" 
$csvOutput | Out-File $csvOutputPath
```

#### <a name="upload-the-hierarchy"></a><span data-ttu-id="ed741-296">계층 구조 업로드</span><span class="sxs-lookup"><span data-stu-id="ed741-296">Upload the hierarchy</span></span>

```powershell
Set-TeamTargetingHierarchy -FilePath $csvOutputPath
Get-TeamTargetingHierarchyStatus
```

## <a name="troubleshooting"></a><span data-ttu-id="ed741-297">문제 해결</span><span class="sxs-lookup"><span data-stu-id="ed741-297">Troubleshooting</span></span>

### <a name="how-to-view-error-details"></a><span data-ttu-id="ed741-298">오류 세부 정보를 보는 방법</span><span class="sxs-lookup"><span data-stu-id="ed741-298">How to view error details</span></span>

<span data-ttu-id="ed741-299">다음 명령을 실행하여 오류의 원인을 이해하고 오류 세부 정보를 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed741-299">You can run the following command to understand what is causing an error and return the error details.</span></span>

```powershell
(Get-TeamTargetingHierarchyStatus).ErrorDetails.ErrorMessage
```

### <a name="you-receive-an-error-message-when-you-upload-your-schema-csv-file"></a><span data-ttu-id="ed741-300">Schema CSV 파일을 업로드할 때 오류 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed741-300">You receive an error message when you upload your schema CSV file</span></span>

<span data-ttu-id="ed741-301">오류 메시지에 문제 해결 정보가 포함되어야 하여, 왜 스마마를 업로드할 수 없는지 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ed741-301">Take note of the error message as it should include troubleshooting information to indicate why the schema couldn't be uploaded.</span></span> <span data-ttu-id="ed741-302">오류 메시지의 정보를 기반으로 Schema CSV 파일을 검토하고 편집한 다음 다시 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="ed741-302">Review and edit your schema CSV file based on the information in the error message and then try again.</span></span>

### <a name="you-receive-an-error-invalidteamid-error-message-when-you-upload-your-schema-csv-file"></a><span data-ttu-id="ed741-303">Schema CSV 파일을 업로드할 때 "Error: InvalidTeamId" 오류 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed741-303">You receive an "Error: InvalidTeamId" error message when you upload your schema CSV file</span></span>

<span data-ttu-id="ed741-304">Schema CSV 파일을 업로드하려고 할 때 다음과 같은 오류 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed741-304">When you try to upload your schema CSV file, you get the following error message:</span></span>

```console
Error: InvalidTeamId
Description: TeamID in row # doesn't match a valid Group ID. Please view our documentation to learn how to get the proper GroupID for each team.
```

<span data-ttu-id="ed741-305">Schema CSV 파일에서 팀에 대해 올바른 TeamId를 사용하고 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="ed741-305">Check to make sure that you're using the correct TeamId for the team in your schema CSV file.</span></span> <span data-ttu-id="ed741-306">TeamId는 팀을 백업하는 Microsoft 365 그룹의 그룹 ID와 동일해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed741-306">The TeamId should be the same as the Group ID of the Microsoft 365 group that backs the team.</span></span> <span data-ttu-id="ed741-307">Microsoft Teams 관리 센터에서 팀의 그룹 ID를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed741-307">You can look up the Group ID of the team in the Microsoft Teams admin center.</span></span>

1. <span data-ttu-id="ed741-308">Microsoft Teams 관리 센터의 왼쪽 [탐색에서](https://admin.teams.microsoft.com/)Teams 관리   >  **팀으로 이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="ed741-308">In the left navigation of the [Microsoft Teams admin center](https://admin.teams.microsoft.com/), go to **Teams** > **Manage teams**.</span></span>
2. <span data-ttu-id="ed741-309">그룹 **ID** 열이 표에 표시되지 않는  경우 표의 오른쪽 위 모서리에 있는 열 편집을 선택한 다음 그룹 **ID 를 를 켜면 됩니다.**</span><span class="sxs-lookup"><span data-stu-id="ed741-309">If the **Group ID** column isn't displayed in the table, select **Edit columns** in the upper-right corner of the table, and then turn on **Group ID**.</span></span>
3. <span data-ttu-id="ed741-310">목록에서 팀을 찾은 다음 그룹 ID를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="ed741-310">Find the team in the list, and then locate the Group ID.</span></span>

<span data-ttu-id="ed741-311">Schema CSV 파일의 TeamId가 Microsoft Teams 관리 센터에 표시되는 그룹 ID와 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed741-311">Make sure that the TeamId in your schema CSV file matches the Group ID that's displayed in the Microsoft Teams admin center.</span></span>

## <a name="related-topics"></a><span data-ttu-id="ed741-312">관련 항목</span><span class="sxs-lookup"><span data-stu-id="ed741-312">Related topics</span></span>

* [<span data-ttu-id="ed741-313">Teams에서 조직의 작업 앱 관리</span><span class="sxs-lookup"><span data-stu-id="ed741-313">Manage the Tasks app for your organization in Teams</span></span>](manage-tasks-app.md)
* [<span data-ttu-id="ed741-314">Teams PowerShell 개요</span><span class="sxs-lookup"><span data-stu-id="ed741-314">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
