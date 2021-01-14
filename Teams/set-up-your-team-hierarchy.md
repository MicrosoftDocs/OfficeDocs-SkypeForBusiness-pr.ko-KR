---
title: 팀 대상 계층 구조 설정
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: andfried, acolonna
search.appverid: MET150
description: 대규모 팀 집합에 콘텐츠를 게시하기 위해 조직에서 팀 계층 구조를 설정하는 방법을 배워야 합니다.
audience: admin
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 06244553c051677533d275ad6cd47052775d01f7
ms.sourcegitcommit: ab566ddab9d26440bac1716a975f30e075d0c7b5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/14/2021
ms.locfileid: "49865252"
---
# <a name="set-up-your-team-targeting-hierarchy"></a><span data-ttu-id="f191d-103">팀 대상 계층 구조 설정</span><span class="sxs-lookup"><span data-stu-id="f191d-103">Set up your team targeting hierarchy</span></span>

<span data-ttu-id="f191d-104">팀 대상 계층 구조를 설정하면 조직에서 대규모 팀 집합에 콘텐츠를 게시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f191d-104">Setting up a team targeting hierarchy will allow your organization to publish content to a large set of teams.</span></span> <span data-ttu-id="f191d-105">팀 대상 계층 구조는 계층 구조의 모든 팀이 서로 관련되는 방식, 사용자가 작업을 게시할 수 있는 사용자 및 게시 권한이 있는 팀을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="f191d-105">The team targeting hierarchy defines how all the teams in your hierarchy are related to each other, which users can publish tasks, and which teams users have permissions to publish to.</span></span> <span data-ttu-id="f191d-106">게시 기능은 조직에 대해 팀 대상 계층 구조를 설정하지 않는 한 모든 사용자에 대해 비활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="f191d-106">Publishing features are disabled for all users unless a team targeting hierarchy is set up for your organization.</span></span> <span data-ttu-id="f191d-107">계층 구조를 대상으로 하는 팀을 설정하려면 계층 구조를 정의하는 파일을 만든 다음 Teams에 업로드하여 조직에 적용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f191d-107">To set up a team targeting hierarchy, you'll need to create a file that defines the hierarchy and then upload it to Teams to apply it to your organization.</span></span> <span data-ttu-id="f191d-108">스마마가 업로드된 후 Teams 내의 앱에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f191d-108">After the schema is uploaded, apps within Teams can use it.</span></span> <span data-ttu-id="f191d-109">여기서 스크립트를 사용하여 계층 구조를 설정하고 Teams 테넌트에 업로드하는 연습을 할 수 [있습니다.](https://docs.microsoft.com/microsoftteams/set-up-your-team-hierarchy#Create-a-sample-hierarchy)</span><span class="sxs-lookup"><span data-stu-id="f191d-109">You can practice setting up a hierarchy and uploading it to your Teams tenant using a script [here](https://docs.microsoft.com/microsoftteams/set-up-your-team-hierarchy#Create-a-sample-hierarchy).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f191d-110">초기 릴리스의 경우 작업 앱만 계층적 팀을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="f191d-110">For the initial release, only the Tasks app supports hierarchical teams.</span></span>  <span data-ttu-id="f191d-111">조직에 팀 대상 계층 구조를 적용하면 작업 앱에서 작업을 [게시할](https://support.microsoft.com/office/publish-task-lists-to-create-and-track-work-in-your-organization-095409b3-f5af-40aa-9f9e-339b54e705df) 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f191d-111">Applying a team targeting hierarchy to your organization will enable [task publishing](https://support.microsoft.com/office/publish-task-lists-to-create-and-track-work-in-your-organization-095409b3-f5af-40aa-9f9e-339b54e705df) in the Tasks app.</span></span> <span data-ttu-id="f191d-112">Microsoft Teams의 다른 영역에는 팀 계층 구조가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f191d-112">You won't see a hierarchy of teams in other areas of Microsoft Teams.</span></span>

<span data-ttu-id="f191d-113">다음은 Teams의 작업 앱에서 계층 구조를 나타내는 방법의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="f191d-113">Here's an example of how the hierarchy is represented in the Tasks app in Teams.</span></span> <span data-ttu-id="f191d-114">작업 목록을 만든 후 게시 팀의 구성원은 받는 사람 팀을 선택하여 작업 목록을 보내(게시)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f191d-114">After a task list is created, members of the publishing team can then select the recipient teams to send (publish) the task list to.</span></span> <span data-ttu-id="f191d-115">팀을 선택할 때 게시 팀은 계층 구조, 특성 또는 둘의 조합을 통해 필터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f191d-115">When selecting teams, the publishing team can filter by hierarchy, by attributes, or a combination of both.</span></span><br>

![작업 게시 스크린샷](media/manage-tasks-app-publish.png)

## <a name="terminology"></a><span data-ttu-id="f191d-117">용어</span><span class="sxs-lookup"><span data-stu-id="f191d-117">Terminology</span></span>

<span data-ttu-id="f191d-118">계층을 탐색할 때 다음 용어가 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="f191d-118">The following terms will be important as you navigate hierarchies.</span></span> <span data-ttu-id="f191d-119">Teams를 **노드라고 합니다.**</span><span class="sxs-lookup"><span data-stu-id="f191d-119">Teams will be referred to as **nodes**.</span></span>

* <span data-ttu-id="f191d-120">**루트 노드는** 계층 구조에서 가장 위쪽의 노드입니다.</span><span class="sxs-lookup"><span data-stu-id="f191d-120">**Root nodes** are the topmost nodes in the hierarchy.</span></span> <span data-ttu-id="f191d-121">이 예제에서 Retail Communications는 루트 노드입니다.</span><span class="sxs-lookup"><span data-stu-id="f191d-121">In the example, Retail Communications is a root node.</span></span>
* <span data-ttu-id="f191d-122">**부모 노드와** **자식 노드는** 연결된 두 노드 간의 관계를 나타내는 용어입니다.</span><span class="sxs-lookup"><span data-stu-id="f191d-122">**Parent nodes** and **child nodes** are terms that represent a relationship between two connected nodes.</span></span> <span data-ttu-id="f191d-123">이 예제에서 01지구는 영역 1의 자식 노드입니다.</span><span class="sxs-lookup"><span data-stu-id="f191d-123">In the example, District 01 is a child node of Area 1.</span></span>
* <span data-ttu-id="f191d-124">여러 수준의 자식 수준을 자식이라고 **합니다.**</span><span class="sxs-lookup"><span data-stu-id="f191d-124">Multiple levels of children are referred to as **descendants**.</span></span> <span data-ttu-id="f191d-125">01지구, 스토어 01, Store 03, Store 07, District 02 및 District 03은 모두 영역 1의 후자입니다.</span><span class="sxs-lookup"><span data-stu-id="f191d-125">District 01, Store 01, Store 03, Store 07, District 02, and District 03 are all descendants of Area 1.</span></span>
* <span data-ttu-id="f191d-126">자식이 없는 노드를 리프 **노드라고 합니다.**</span><span class="sxs-lookup"><span data-stu-id="f191d-126">A node with no children is called a **leaf node**.</span></span> <span data-ttu-id="f191d-127">계층 구조의 맨 아래에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f191d-127">They are at the bottom of a hierarchy.</span></span>
* <span data-ttu-id="f191d-128">**받는 사람 팀은** 게시할 특정 콘텐츠 집합을 받기 위해 선택된 팀입니다.</span><span class="sxs-lookup"><span data-stu-id="f191d-128">**Recipient teams** are teams that have been selected to receive a specific set of content to be published.</span></span> <span data-ttu-id="f191d-129">리프 노드가 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f191d-129">They must be leaf nodes.</span></span>

## <a name="plan-your-hierarchy"></a><span data-ttu-id="f191d-130">계층 구조 계획</span><span class="sxs-lookup"><span data-stu-id="f191d-130">Plan your hierarchy</span></span>

<span data-ttu-id="f191d-131">계층 구조를 정의하는 스마마를 만들기 전에 몇 가지 계획을 세우고 조직을 구성할 방법을 결정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f191d-131">Before you create the schema that defines your hierarchy, you need to do some planning and decide how you want to shape your organization.</span></span>  <span data-ttu-id="f191d-132">첫 번째 우선 순위 중 하나는 다른 그룹에 작업을 게시해야 하는 조직 그룹을 결정하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="f191d-132">One of the first priorities is deciding which organizational groups need to publish tasks to other groups.</span></span> <span data-ttu-id="f191d-133">계층 구조의 각 노드는 작업 그룹 또는 그룹 그룹을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f191d-133">Each node in the hierarchy represents a working group or group of groups.</span></span>

### <a name="permissions-to-publish"></a><span data-ttu-id="f191d-134">게시할 권한</span><span class="sxs-lookup"><span data-stu-id="f191d-134">Permissions to publish</span></span>

<span data-ttu-id="f191d-135">게시 권한은 사용자가 계층 구조에 있는 모든 팀의 구성원인지 여부와 해당 팀의 관계 또는 계층 구조의 다른 팀과의 관계에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="f191d-135">Permission to publish depends on whether a user is a member of any teams in the hierarchy plus the relationship of that team or set of teams to other teams in the hierarchy.</span></span>

> [!NOTE]
> <span data-ttu-id="f191d-136">팀 소유자에게 게시 권한도 부여됩니다.</span><span class="sxs-lookup"><span data-stu-id="f191d-136">The owner of a team is also granted publishing permissions.</span></span>

* <span data-ttu-id="f191d-137">사용자가 계층 구조에 자선이 있는 하나 이상의 팀의 구성원인 경우 해당 사용자는 게시하려는 모든 팀의 구성원이 될 필요 없이 해당 자선 팀에 게시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f191d-137">If a user is a member of at least one team that has descendants in the hierarchy, that user can publish to those descendants without being a member of all teams they want to publish to.</span></span>
* <span data-ttu-id="f191d-138">사용자가 계층 구조에서 하나 이상의 팀의 구성원이지만 계층 구조에 있는 모든 팀의 구성원이 아닌 경우 해당 사용자는 조직에서 게시된 콘텐츠를 보고 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f191d-138">If a user is a member of a least one team in the hierarchy but isn't a member of any team with descendants in the hierarchy, that user can see and receive published content from their organization.</span></span>
* <span data-ttu-id="f191d-139">사용자가 계층 구조에서 팀의 구성원이 아닌 경우 해당 사용자에게 게시 관련 기능이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f191d-139">If a user isn't a member of any team in the hierarchy, that user won't see any publishing-related functionality.</span></span>

### <a name="guidelines"></a><span data-ttu-id="f191d-140">지침</span><span class="sxs-lookup"><span data-stu-id="f191d-140">Guidelines</span></span>

* <span data-ttu-id="f191d-141">조직당 하나의 계층 구조 파일만 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f191d-141">There can only be one hierarchy file applied per organization.</span></span> <span data-ttu-id="f191d-142">그러나 하나의 CSV 파일 내에서 노드의 고유한 계층으로 조직의 여러 부분을 함께 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f191d-142">However, you can include different parts of your organization together as distinct hierarchies of nodes within one CSV file.</span></span> <span data-ttu-id="f191d-143">예를 들어 Contoso Pharmas에는 Pharmacy 루트 노드와 소매 루트 노드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f191d-143">For example, Contoso Pharmaceuticals has a Pharmacy root node and a Retail root node.</span></span> <span data-ttu-id="f191d-144">두 루트 노드에는 여러 개의 자르기 행이 있으며 둘 사이에는 겹치지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f191d-144">Both root nodes have multiple rows of descendants and there's no overlap between them.</span></span>
* <span data-ttu-id="f191d-145">리프 노드만 발행물의 받는 사람일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f191d-145">Only leaf nodes can be recipients of a publication.</span></span> <span data-ttu-id="f191d-146">계층 구조의 다른 노드는 발행물의 받는 사람을 선택하는 데 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="f191d-146">Other nodes in the hierarchy are helpful for selecting recipients of a publication.</span></span>
* <span data-ttu-id="f191d-147">팀은 계층 구조에서 한 번만 표현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f191d-147">A team can only be represented one time in a hierarchy.</span></span>
* <span data-ttu-id="f191d-148">계층 구조는 최대 15,000개 노드를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f191d-148">A hierarchy can contain up to 15,000 nodes.</span></span> <span data-ttu-id="f191d-149">더 큰 조직에 대해 이 제한을 높이기 위해 고객과 협력할 계획입니다.</span><span class="sxs-lookup"><span data-stu-id="f191d-149">We plan to work with customers to raise this limit for larger organizations.</span></span>

### <a name="example-hierarchy"></a><span data-ttu-id="f191d-150">예제 계층 구조</span><span class="sxs-lookup"><span data-stu-id="f191d-150">Example hierarchy</span></span>

<span data-ttu-id="f191d-151">예를 들어 다음 계층 구조에서 회수, 통신 및 HR은 계층 구조의 모든 아래쪽 노드(팀)에 작업을 게시할 수 있지만, Northeast Zone은 뉴욕 스토어 및 보스턴 스토어 팀에만 작업을 게시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f191d-151">For example, in the following hierarchy, Recall, Communications, and HR can publish tasks to every bottom node (team) in the hierarchy, but Northeast Zone can only publish tasks to the New York Store and Boston Store teams.</span></span> <span data-ttu-id="f191d-152">예제 계층 구조를 사용하면 회수, 통신 및 HR 그룹이 CEO의 혜택 정보 또는 메시지와 같이 회사 전체에 적용되는 작업을 게시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f191d-152">The example hierarchy allows the Recall, Communications, and HR groups to publish tasks that apply to the entire company, such as benefits information or messages from the CEO.</span></span> <span data-ttu-id="f191d-153">Northeast Zone은 직원의 일기 예보, 날씨 정보 등 작업을 뉴욕 스토어 및 보스턴 스토어 팀에만 게시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f191d-153">Northeast Zone can publish tasks like personnel scheduling, weather information, and so on, only to the New York Store and Boston Store teams.</span></span>

![팀 계층적 예제](media/team-targeting-schema-example-new.png)

## <a name="create-your-hierarchy"></a><span data-ttu-id="f191d-155">계층 구조 만들기</span><span class="sxs-lookup"><span data-stu-id="f191d-155">Create your hierarchy</span></span>

> [!NOTE]
> <span data-ttu-id="f191d-156">이 문서의 나머지에서는 받는 사람 팀에 작업을 게시하는 컨텍스트에서 팀 계층 구조를 설정하는 데 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f191d-156">The remainder of this article discusses setting up a team hierarchy in the context of publishing tasks to recipient teams.</span></span> <span data-ttu-id="f191d-157">작업 [게시를](https://docs.microsoft.com/MicrosoftTeams/manage-tasks-app) 사용하도록 설정하면 나타나는 작업 앱의 개요는 Teams에서 조직의 작업 앱 관리를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f191d-157">Refer to [Manage the Tasks app for your organization in Teams](https://docs.microsoft.com/MicrosoftTeams/manage-tasks-app) for an overview of the Tasks app, where task publishing appears when enabled.</span></span>

<span data-ttu-id="f191d-158">계층 구조를 정의하는 스마는 CSV(콤마로 구분된 값) 파일을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="f191d-158">The schema that defines your hierarchy is based on a comma-separated values (CSV) file.</span></span> <span data-ttu-id="f191d-159">CSV 파일의 각 행은 팀 계층 구조 내의 한 노드에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="f191d-159">Each row in the CSV file corresponds to one node within the hierarchy of teams.</span></span> <span data-ttu-id="f191d-160">각 행에는 계층 구조 내의 노드 이름을 입력하고, 선택적으로 팀에 연결하며, 이를 지원하는 앱에서 팀을 필터링하는 데 사용할 수 있는 특성이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f191d-160">Each row contains information that names the node within the hierarchy, optionally links it to a team, and includes attributes that can be used to filter teams in apps that support it.</span></span>

<span data-ttu-id="f191d-161">또한 게시 팀이 받는 사람 팀에 전송된 콘텐츠를 구성하는 데 사용할 수 있는 범주인 버킷을 정의하여 관련 콘텐츠를 더 쉽게 보고, 정렬하고, 집중할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f191d-161">You can also define **buckets**, which are categories that the publishing team can use to organize content sent to recipient teams to make it easier for them to view, sort, and focus on relevant content.</span></span>

### <a name="add-required-columns"></a><span data-ttu-id="f191d-162">필요한 열 추가</span><span class="sxs-lookup"><span data-stu-id="f191d-162">Add required columns</span></span>

<span data-ttu-id="f191d-163">CSV 파일에는 첫 번째 열부터 다음 세 개의 열이 다음 순서대로 포함되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f191d-163">The CSV file must contain the following three columns, in the following order, starting at the first column.</span></span> <span data-ttu-id="f191d-164">태스크를 수신하려면 노드를 팀에 연결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f191d-164">A node must be linked to a team for it to receive tasks.</span></span>

| <span data-ttu-id="f191d-165">열 이름</span><span class="sxs-lookup"><span data-stu-id="f191d-165">Column name</span></span>   | <span data-ttu-id="f191d-166">필수</span><span class="sxs-lookup"><span data-stu-id="f191d-166">Required</span></span> | <span data-ttu-id="f191d-167">설명</span><span class="sxs-lookup"><span data-stu-id="f191d-167">Description</span></span>   |
----------------|----------|---------------|
| <span data-ttu-id="f191d-168">DisplayName</span><span class="sxs-lookup"><span data-stu-id="f191d-168">DisplayName</span></span>    | <span data-ttu-id="f191d-169">예</span><span class="sxs-lookup"><span data-stu-id="f191d-169">Yes</span></span>      | <span data-ttu-id="f191d-170">이 필드는 노드의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="f191d-170">This field is the name of the node.</span></span> <span data-ttu-id="f191d-171">이름은 최대 100자까지 사용할 수 있으며 A-Z, a-z 및 0-9 문자만 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f191d-171">The name can be up to 100 characters long and contain only the characters A-Z, a-z, and 0-9.</span></span> <span data-ttu-id="f191d-172">노드 이름은 고유해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f191d-172">Node names must be unique.</span></span> |
| <span data-ttu-id="f191d-173">ParentName</span><span class="sxs-lookup"><span data-stu-id="f191d-173">ParentName</span></span>    | <span data-ttu-id="f191d-174">예</span><span class="sxs-lookup"><span data-stu-id="f191d-174">Yes</span></span>       | <span data-ttu-id="f191d-175">부모 노드의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="f191d-175">This is the name of the parent node.</span></span> <span data-ttu-id="f191d-176">여기서 지정한 값은 부모 노드의 **DisplayName** 필드 값과 정확히 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f191d-176">The value you specify here must match the value in the **DisplayName** field of the parent node exactly.</span></span> <span data-ttu-id="f191d-177">두 개 이상의 부모 노드를 추가하려는 경우 각 부모 노드 이름을 세미코론(;).</span><span class="sxs-lookup"><span data-stu-id="f191d-177">If you want to add more than one parent node, separate each parent node name with a semicolon (;).</span></span> <span data-ttu-id="f191d-178">최대 25개 부모 노드를 추가할 수 있으며 각 부모 노드 이름은 최대 2500자까지 입력할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f191d-178">You can add up to 25 parent nodes, and each parent node name can be up to 2500 characters long.</span></span> <span data-ttu-id="f191d-179">노드는 부모 노드가 루트 노드인 경우 여러 부모 노드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f191d-179">A node can have multiple parent nodes only if the parent nodes are root nodes.</span></span>   <br><br><span data-ttu-id="f191d-180">**중요** 계층 구조에서 상위 부모가 계층 구조의 하위 노드를 참조하는 루프를 만들지 않도록 주의하세요.</span><span class="sxs-lookup"><span data-stu-id="f191d-180">**IMPORTANT** Be careful not to create a loop where a parent higher up in the hierarchy references a child node lower in the hierarchy.</span></span> <span data-ttu-id="f191d-181">지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f191d-181">This isn't supported.</span></span> |
| <span data-ttu-id="f191d-182">TeamId</span><span class="sxs-lookup"><span data-stu-id="f191d-182">TeamId</span></span>        | <span data-ttu-id="f191d-183">예, 팀이 태스크를 게시하거나 부모 노드에서 작업을 수신하는 경우</span><span class="sxs-lookup"><span data-stu-id="f191d-183">Yes, if the team publishes tasks or receives tasks from a parent node</span></span>       | <span data-ttu-id="f191d-184">여기에는 노드를 연결하려는 팀의 ID가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f191d-184">This contains the ID of the team you want to link a node to.</span></span> <span data-ttu-id="f191d-185">각 노드는 고유한 팀을 참조해야 하여 각 TeamId 값은 계층 구조 파일에 한 번만 나타날 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f191d-185">Each node must refer to a unique team, so each TeamId value may appear only once in the hierarchy file.</span></span> <span data-ttu-id="f191d-186">노드를 연결하려는 팀의 ID를 얻으면 다음 PowerShell 명령을 `Get-Team | Export-Csv TeamList.csv` 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="f191d-186">To get the ID of a team you want to link a node to, run the following PowerShell command: `Get-Team | Export-Csv TeamList.csv`.</span></span> <span data-ttu-id="f191d-187">이 명령은 조직의 팀을 나열하고 각 팀의 이름과 ID를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="f191d-187">This command lists the teams in your organization and includes the name and ID for each team.</span></span> <span data-ttu-id="f191d-188">연결하려는 팀의 이름을 찾은 다음 이 필드에 ID를 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="f191d-188">Find the name of the team you want to link to, and then copy the ID into this field.</span></span>|

> [!NOTE]
> <span data-ttu-id="f191d-189">노드가 루트 노드 또는 리프 노드가 아니고 게시 및 보고에 해당하는 권한을 부여하기 위해 팀 멤버 자격이 필요하지 않은 경우 TeamId를 비워 두면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f191d-189">If a node isn't a root node or a leaf node and you don't need the team membership to grant the corresponding permissions for publishing and reporting, you can leave the TeamId blank.</span></span> <span data-ttu-id="f191d-190">이 방법은 받는 사람 팀을 선택할 때 더 세분성을 추가하거나 해당 팀이 없는 완료 보고서를 보는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f191d-190">This method can be used to add more granularity when choosing recipient teams or for viewing completion reports without having a corresponding team.</span></span>

### <a name="add-attribute-columns"></a><span data-ttu-id="f191d-191">특성 열 추가</span><span class="sxs-lookup"><span data-stu-id="f191d-191">Add attribute columns</span></span>

<span data-ttu-id="f191d-192">세 개의 필수 열을 추가한 후 선택적 특성 열을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f191d-192">After you add the three required columns, you can add optional attribute columns.</span></span> <span data-ttu-id="f191d-193">이러한 특성은 태스크를 게시하려는 특성을 보다 쉽게 선택할 수 있도록 노드를 필터링하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f191d-193">These attributes can be used to filter nodes so that you can more easily select the ones you want to publish tasks to.</span></span> <span data-ttu-id="f191d-194">해당 특성의 값이 상호 배타적인지 여부에 따라 특성을 정의하는 두 가지 방법이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f191d-194">There are two ways to define your attributes, depending on whether values for that attribute are mutually exclusive.</span></span>

|<span data-ttu-id="f191d-195">특성을 추가하는 방법</span><span class="sxs-lookup"><span data-stu-id="f191d-195">Ways to add attributes</span></span>|<span data-ttu-id="f191d-196">설명</span><span class="sxs-lookup"><span data-stu-id="f191d-196">Description</span></span> |<span data-ttu-id="f191d-197">예제</span><span class="sxs-lookup"><span data-stu-id="f191d-197">Example</span></span>  |
|---|---------|---------|
|<span data-ttu-id="f191d-198">특성 값이 상호 배타적이면 지정한 열 이름이 특성의 이름이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f191d-198">If the values for an attribute are mutually exclusive, the column name you specify becomes the name of the attribute.</span></span>|<span data-ttu-id="f191d-199">각 행은 해당 특성에 대해 하나의 값을 포함할 수 있으며, 각 특성 열에는 최대 50개 고유 값이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f191d-199">Each row can contain one value for that attribute, and each attribute column can have up to 50 unique values.</span></span> <span data-ttu-id="f191d-200">각 값은 최대 100자까지 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f191d-200">Each value can be up to 100 characters long.</span></span> <span data-ttu-id="f191d-201">특성 열에 지정한 특성 값 집합은 팀 대상 계층 구조를 사용하여 받는 사람 팀을 선택할 때 해당 특성에 대한 필터 값으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f191d-201">The set of attribute values you specify in the attribute column will be displayed as filter values for that attribute when selecting recipient teams using the team targeting hierarchy.</span></span>|<span data-ttu-id="f191d-202">사용자가 레이아웃을 통해 저장소를 필터링할 수 있도록 하려는 경우</span><span class="sxs-lookup"><span data-stu-id="f191d-202">You want users to be able to filter stores by layout.</span></span> <span data-ttu-id="f191d-203">저장소에 레이아웃이 하나만 있기 때문에 이 특성의 값은 상호 배타적입니다.</span><span class="sxs-lookup"><span data-stu-id="f191d-203">The values for this attribute are mutually exclusive because a store can have only one layout.</span></span> <br><br><span data-ttu-id="f191d-204">레이아웃을 통해 저장소를 필터링하는 특성을 추가하기 위해 스토어 레이아웃이라는 열을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f191d-204">To add an attribute to filter stores by layout, add a column named Store layout.</span></span> <span data-ttu-id="f191d-205">이 예제에서 스토어 레이아웃 특성의 값은 Compact, Standard 및 Large입니다.</span><span class="sxs-lookup"><span data-stu-id="f191d-205">In this example, values for the Store layout attribute are Compact, Standard, and Large.</span></span>
|<span data-ttu-id="f191d-206">특성에 대해 여러 값을 나타내야 하지만 값이 상호 배타적이지 않은 경우 열 이름에 **AttributeName:UniqueValue** 형식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f191d-206">If you need to indicate multiple values for an attribute and the values aren't mutually exclusive, use the **AttributeName:UniqueValue** format for the column names.</span></span> <br><br><span data-ttu-id="f191d-207">**중요** 영어 전용 콜론(:) 유니코드는 특성 열 디리미터로 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f191d-207">**IMPORTANT** Make sure to use the English-only colon (:) as unicode isn't supported as an attribute column delimiter.</span></span> |<span data-ttu-id="f191d-208">콜론 앞의 텍스트 문자열(:) 특성의 이름이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f191d-208">The text string before the colon (:) becomes the name of the attribute.</span></span> <span data-ttu-id="f191d-209">콜론 앞에 동일한 텍스트 문자열이 포함된 모든 열(:) 필터링 메뉴의 섹션으로 그룹화됩니다.</span><span class="sxs-lookup"><span data-stu-id="f191d-209">All columns that contain the same text string before the colons (:) are grouped together into a section in the filtering menu.</span></span> <span data-ttu-id="f191d-210">콜론 뒤의 각 문자열은 이 섹션의 값이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f191d-210">Each of the strings after the colon become the values for that section.</span></span><br><br><span data-ttu-id="f191d-211">각 행의 값은 해당 특성에 대해 0 또는 1일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f191d-211">Each row can have a value of 0 (zero) or 1 for that attribute.</span></span> <span data-ttu-id="f191d-212">값이 0이면 특성이 노드에 적용되지 않는 것이고 값 1은 특성이 해당 노드에 적용된다는 의미입니다.</span><span class="sxs-lookup"><span data-stu-id="f191d-212">A value of 0 means that the attribute doesn't apply to the node and a value of 1 means that the attribute applies to that node.</span></span>|<span data-ttu-id="f191d-213">사용자가 부서를 통해 저장소를 필터링할 수 있도록 하려는 경우</span><span class="sxs-lookup"><span data-stu-id="f191d-213">You want users to be able to filter stores by department.</span></span> <span data-ttu-id="f191d-214">저장소에는 여러 부서가 있을 수 있으므로 이 특성의 값은 상호 배타적이지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f191d-214">A store can have multiple departments and so the values for this attribute aren't mutually exclusive.</span></span><br><br><span data-ttu-id="f191d-215">이 예제에서는 Departments:의류, Departments:Electronics, Departments:Foods, Departments:Home and Garden, Departments:Sporting 상품을 특성 열로 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f191d-215">In this example, we add Departments:Clothing, Departments:Electronics, Departments:Foods, Departments:Home and Garden, Departments:Sporting goods as attribute columns.</span></span> <span data-ttu-id="f191d-216">부서는 특성 이름이 됐고 사용자는 의류, 전자, 음식, 집 및 정원 및 스포츠 상품 부서를 통해 필터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f191d-216">Departments becomes the attribute name and users can filter by the Clothing, Electronics, Foods, Home and Garden, and Sporting goods departments.</span></span>|

<span data-ttu-id="f191d-217">특성 열을 추가할 때 다음에 유의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f191d-217">When you add an attribute column, keep the following in mind:</span></span>

* <span data-ttu-id="f191d-218">지정한 열 이름 또는 콜론 앞에 지정한 열 이름(:) 특성의 이름이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f191d-218">The column name you specify or the column name that you specify before the colon (:) becomes the name of the attribute.</span></span> <span data-ttu-id="f191d-219">이 값은 계층 구조를 사용하는 Teams 앱에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f191d-219">This value will be displayed in the Teams apps that use the hierarchy.</span></span>
* <span data-ttu-id="f191d-220">계층 구조에 최대 50개 특성 열을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f191d-220">You can have up to 50 attribute columns in your hierarchy.</span></span>
* <span data-ttu-id="f191d-221">열 이름은 최대 100자까지 사용할 수 있으며 문자 A-Z, a-z 및 0-9 및 공백만 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f191d-221">The column name can be up to 100 characters long and contain only the characters A-Z, a-z, and 0-9, and spaces.</span></span> <span data-ttu-id="f191d-222">열 이름은 고유해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f191d-222">Column names must be unique.</span></span>

### <a name="add-bucket-columns"></a><span data-ttu-id="f191d-223">버킷 열 추가</span><span class="sxs-lookup"><span data-stu-id="f191d-223">Add bucket columns</span></span>

<span data-ttu-id="f191d-224">버킷 열을 추가하여 작업을 구성할 수 있는 그룹화인 버킷을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f191d-224">You can add bucket columns to create buckets, which are groupings into which tasks can be organized.</span></span> <span data-ttu-id="f191d-225">각 버킷은 CSV 파일에서 자체 열을 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="f191d-225">Each bucket gets its own column in the CSV file.</span></span> <span data-ttu-id="f191d-226">만든 버킷은 게시 팀에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f191d-226">The buckets you create are made available to the publishing team.</span></span> <span data-ttu-id="f191d-227">게시 팀은 이러한 버킷을 사용하여 받는 사람 팀에 대한 작업을 분류할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f191d-227">The publishing team can then use these buckets to categorize tasks for the recipient teams.</span></span> <span data-ttu-id="f191d-228">팀에 버킷이 아직 없는 경우 작업이 게시될 때 필요한 경우 버킷이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="f191d-228">If a bucket doesn't already exist on a team, buckets are created on-demand when tasks are published.</span></span>

<span data-ttu-id="f191d-229">작업 항목을 한 번 중앙에서 분류하여 게시 팀은 작업 목록을 받는 수십, 수백 또는 수천 명의 받는 사람 팀에 대해 작업 목록을 미리 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f191d-229">By categorizing the work items one time centrally, the publishing team can pre-organize the task list for all the tens, hundreds, or thousands of recipient teams that receive the task list.</span></span> <span data-ttu-id="f191d-230">그런 다음 받는 사람 팀은 버킷별로 작업을 정렬하고 필터링하여 업무와 가장 관련성이 높은 영역에 집중할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f191d-230">The recipient teams can then sort and filter their tasks by bucket to focus on the area most relevant to their work.</span></span>

<span data-ttu-id="f191d-231">버킷 열을 추가할 때 다음에 유의합니다.</span><span class="sxs-lookup"><span data-stu-id="f191d-231">When you add a bucket column, note the following:</span></span>

* <span data-ttu-id="f191d-232">열 이름은 버킷의 이름이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f191d-232">The column name becomes the name of the bucket.</span></span> <span data-ttu-id="f191d-233">지정한 각 버킷은 계층 구조를 사용하는 Teams 앱의 버킷 목록에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f191d-233">Each bucket you specify will appear in the Buckets list in the Teams apps that use the hierarchy.</span></span>
* <span data-ttu-id="f191d-234">버킷 이름에 중요한 정보를 포함하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="f191d-234">We recommend that you don't include sensitive information in bucket names.</span></span> <span data-ttu-id="f191d-235">현재 게시 팀은 버킷을 만든 후 게시를 통해 버킷을 제거할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f191d-235">At this time, publishing teams can't remove a bucket through publishing after it's created.</span></span>
* <span data-ttu-id="f191d-236">열 이름 앞에 해시태그(#)가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f191d-236">The column name must be preceded by a hashtag (#).</span></span> <span data-ttu-id="f191d-237">최대 100자까지 사용할 수 있으며 A-Z, a-z 및 0-9 문자만 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f191d-237">It can be up to 100 characters long and contain only the characters A-Z, a-z, and 0-9.</span></span> <span data-ttu-id="f191d-238">예를 들어 #Operations #Frozen 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f191d-238">For example, #Operations and #Frozen Goods.</span></span>
* <span data-ttu-id="f191d-239">계층 구조에는 최대 25개 버킷 열이 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f191d-239">A hierarchy may contain up to 25 bucket columns.</span></span> <span data-ttu-id="f191d-240">더 큰 조직에 대해 이 제한을 늘리기 위해 고객과 협력할 계획입니다.</span><span class="sxs-lookup"><span data-stu-id="f191d-240">We plan to work with customers to increase this limit for larger organizations.</span></span>

### <a name="example"></a><span data-ttu-id="f191d-241">예제</span><span class="sxs-lookup"><span data-stu-id="f191d-241">Example</span></span>

<span data-ttu-id="f191d-242">다음은 이전 이미지에 표시된 계층 구조를 지원하기 위해 만들어질 SCHEMA CSV 파일의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="f191d-242">Here's an example of a schema CSV file that would be created to support the hierarchy shown in the previous image.</span></span> <span data-ttu-id="f191d-243">이 Schema에는 다음이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f191d-243">This schema contains the following:</span></span>

* <span data-ttu-id="f191d-244">3개의 필수 열 `TargetName` `ParentName` , 및 `TeamId`</span><span class="sxs-lookup"><span data-stu-id="f191d-244">Three required columns named `TargetName`, `ParentName`, and `TeamId`</span></span>
* <span data-ttu-id="f191d-245">3개의 특성 `Store layout` 열, `Departments:Clothing` 및 `Departments:Foods`</span><span class="sxs-lookup"><span data-stu-id="f191d-245">Three attribute columns named `Store layout`, `Departments:Clothing`, and `Departments:Foods`</span></span>
* <span data-ttu-id="f191d-246">3개의 버킷 열 `Fresh Foods` `Frozen Foods` , 및 `Women's Wear`</span><span class="sxs-lookup"><span data-stu-id="f191d-246">Three bucket columns named `Fresh Foods`, `Frozen Foods`, and `Women's Wear`</span></span>

<span data-ttu-id="f191d-247">특성에는 `Store layout` `Compact` , 및 `Standard` .를 포함 하는 값이 `Large` 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f191d-247">The `Store layout` attribute has values that include `Compact`, `Standard`, and `Large`.</span></span> <span data-ttu-id="f191d-248">특성 `Departments` 열은 값(0) 또는 `0` 0으로 설정할 수 `1` 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f191d-248">The `Departments` attribute columns can be set to a value of `0` (zero) or `1`.</span></span> <span data-ttu-id="f191d-249">레이아웃 `Store` 및 `Departments` 특성은 위의 이미지에 나와 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f191d-249">The `Store` layout and `Departments` attributes aren't shown in the image above.</span></span> <span data-ttu-id="f191d-250">노드 항목에 특성을 추가하는 방법을 보여 주기 위해 여기에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="f191d-250">They're added here to help show how attributes can be added to node entries.</span></span> <span data-ttu-id="f191d-251">세 개의 버킷 열도 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="f191d-251">The same is true for the three bucket columns.</span></span>

```CSV
"TargetName,ParentName,TeamId,Store layout,Departments:Clothing,Departments:Foods,#Fresh Foods,#Frozen Foods,#Women's Wear"
"Recall,,db23e6ba-04a6-412a-95e8-49e5b01943ba,,,,,,"
"Communications,,145399ce-a761-4843-a110-3077249037fc,,,,,,"
"HR,,,,,,,,,,"
"East Regional Office,,,,,,,,,,"
"West Regional Office,,,,,,,,,,"
"Northeast Zone,East Regional Office,,,,,,,,"
"Southeast Zone,East Regional Office,,,,,,,,"
"New York Store,Northeast Zone,e2ba65f6-25e7-488b-b8f0-b8562d5de60a,Large,1,1,,,"
"Boston Store,Northeast Zone,0454f08a-0507-437c-969a-682eb2fae7fc,Standard,1,1,,,"
"Miami Store,Southeast Zone,619d6e4e-5f68-4b36-8e1f-16c98d7396c1,Compact,0,1,,,"
"New Orleans Store,Southeast Zone,6be960b8-72af-4561-a343-9ac4711874eb,Compact,0,1,,,"
"Seattle Store,West Regional Zone,487c0d20-4e55-4dc2-8187-a24c826e0fee,Standard,1,1,,,"
"Los Angeles Store,West Regional Zone,204a1287-2efb-4a8a-88e0-56fbaf5a2389,Large,1,1,,,"
```

## <a name="apply-your-hierarchy"></a><span data-ttu-id="f191d-252">계층 구조 적용</span><span class="sxs-lookup"><span data-stu-id="f191d-252">Apply your hierarchy</span></span>

<span data-ttu-id="f191d-253">Schema CSV 파일에서 계층 구조를 정의한 후 Teams에 업로드할 준비가 된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="f191d-253">After you've defined your hierarchy in the schema CSV file, you're ready to upload it to Teams.</span></span> <span data-ttu-id="f191d-254">이를 위해 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="f191d-254">To do this, run the following command.</span></span> <span data-ttu-id="f191d-255">이 단계를하려면 전역 관리자 또는 Teams 서비스 관리자 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f191d-255">You must be a global admin or Teams service admin to do this step.</span></span>

```powershell
Set-TeamTargetingHierarchy -FilePath "C:\ContosoTeamSchema.csv"
```

### <a name="update-your-hierarchy"></a><span data-ttu-id="f191d-256">계층 구조 업데이트</span><span class="sxs-lookup"><span data-stu-id="f191d-256">Update your hierarchy</span></span>

<span data-ttu-id="f191d-257">위와 동일한 PowerShell 명령을 사용하여 이전 계층 구조를 대체하는 새 계층 구조를 업로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f191d-257">You can upload a new hierarchy to replace the old one using the same PowerShell command as above.</span></span> <span data-ttu-id="f191d-258">새 계층 구조를 업로드할 때마다 이전 계층 구조가 대체됩니다.</span><span class="sxs-lookup"><span data-stu-id="f191d-258">Each time you upload a new hierarchy, it replaces the previous hierarchy.</span></span>

### <a name="check-the-status-of-your-hierarchy"></a><span data-ttu-id="f191d-259">계층 구조 상태 확인</span><span class="sxs-lookup"><span data-stu-id="f191d-259">Check the status of your hierarchy</span></span>

<span data-ttu-id="f191d-260">다음 명령을 실행하여 계층 구조 업로드의 상태를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f191d-260">You can run the following command to check the status of your hierarchy upload.</span></span>

```powershell
Get-TeamTargetingHierarchyStatus
```

<span data-ttu-id="f191d-261">명령은 다음 필드를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="f191d-261">The command will return the following fields:</span></span>

<span data-ttu-id="f191d-262">필드</span><span class="sxs-lookup"><span data-stu-id="f191d-262">Field</span></span>|<span data-ttu-id="f191d-263">설명</span><span class="sxs-lookup"><span data-stu-id="f191d-263">Description</span></span>
-----|------------
<span data-ttu-id="f191d-264">ID</span><span class="sxs-lookup"><span data-stu-id="f191d-264">Id</span></span> | <span data-ttu-id="f191d-265">업로드에 대한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="f191d-265">The unique ID for the upload.</span></span>
<span data-ttu-id="f191d-266">상태</span><span class="sxs-lookup"><span data-stu-id="f191d-266">Status</span></span> | <span data-ttu-id="f191d-267">업로드 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="f191d-267">Upload status.</span></span> <span data-ttu-id="f191d-268">값에는 **시작,** 유효성 **검사, 성공** **및** **실패가 포함됩니다.**</span><span class="sxs-lookup"><span data-stu-id="f191d-268">Values include **Starting**, **Validating**, **Successful**, and **Failed**</span></span>
<span data-ttu-id="f191d-269">ErrorDetails</span><span class="sxs-lookup"><span data-stu-id="f191d-269">ErrorDetails</span></span> | <span data-ttu-id="f191d-270">업로드 오류가 있는 경우 세부 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="f191d-270">Details if there's an upload error.</span></span> <span data-ttu-id="f191d-271">오류 세부 정보에 대한 자세한 내용은 문제 해결 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f191d-271">For more information about the error details, see the Troubleshooting section.</span></span> <span data-ttu-id="f191d-272">오류가 없는 경우 이 필드는 비어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f191d-272">If there's no error, this field is blank.</span></span>
<span data-ttu-id="f191d-273">LastUpdatedAt</span><span class="sxs-lookup"><span data-stu-id="f191d-273">LastUpdatedAt</span></span> | <span data-ttu-id="f191d-274">파일이 마지막으로 업데이트된 타임스탬프 및 날짜입니다.</span><span class="sxs-lookup"><span data-stu-id="f191d-274">Timestamp and date of when the file was last updated.</span></span>
<span data-ttu-id="f191d-275">LastModifiedBy</span><span class="sxs-lookup"><span data-stu-id="f191d-275">LastModifiedBy</span></span> | <span data-ttu-id="f191d-276">파일을 수정한 마지막 사용자의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="f191d-276">The ID of the last user who modified the file.</span></span>
<span data-ttu-id="f191d-277">FileName</span><span class="sxs-lookup"><span data-stu-id="f191d-277">FileName</span></span> | <span data-ttu-id="f191d-278">CSV의 파일 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="f191d-278">The file name of the CSV.</span></span>

## <a name="remove-your-hierarchy"></a><span data-ttu-id="f191d-279">계층 구조 제거</span><span class="sxs-lookup"><span data-stu-id="f191d-279">Remove your hierarchy</span></span>

<span data-ttu-id="f191d-280">조직의 모든 사용자에  대해 게시된 목록 탭을 즉시 사용하지 않도록 설정하려면 계층 구조를 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f191d-280">If you want to immediately disable the **Published lists** tab for all users in your organization, you can remove your hierarchy.</span></span> <span data-ttu-id="f191d-281">사용자는 게시된 목록 탭  또는 탭의 기능에 액세스할 수 없습니다.  여기에는 새 작업 목록을 만들어 게시, 초안 목록에 액세스, 게시 및 중복 목록을 보고하는 기능을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="f191d-281">Users won't have access to the **Published lists** tab or any of the functionalities on the tab.  This includes the ability to create new task lists to publish, access draft lists, publish, unpublish, and duplicate lists, and view reporting.</span></span> <span data-ttu-id="f191d-282">계층 구조를 제거해도 이전에 게시된 작업이 게시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f191d-282">Removing the hierarchy doesn't unpublish tasks that were previously published.</span></span> <span data-ttu-id="f191d-283">이러한 작업은 받는 사람 팀이 완료할 수 있도록 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="f191d-283">These tasks will remain available for recipient teams to complete.</span></span>

<span data-ttu-id="f191d-284">계층 구조를 제거하려면 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="f191d-284">To remove your hierarchy, run the following command.</span></span> <span data-ttu-id="f191d-285">이 단계를 수행하려면 관리자 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f191d-285">You must be an admin to perform this step.</span></span>

```powershell
Remove-TeamTargetingHierarchy
```

<span data-ttu-id="f191d-286">삭제를 확인하면 개체가 null인 오류를 반환하겠지만, 삭제를 다시 시도하면 상태 메시지에 이전의 상태가 계속 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f191d-286">When confirming deletion, the status message will still display the previous schema is present, although attempting to delete again returns an error that the object is null.</span></span>

## <a name="create-a-sample-hierarchy"></a><span data-ttu-id="f191d-287">샘플 계층 구조 만들기</span><span class="sxs-lookup"><span data-stu-id="f191d-287">Create a sample hierarchy</span></span>

### <a name="install-the-teams-powershell-module"></a><span data-ttu-id="f191d-288">Teams PowerShell 모듈 설치</span><span class="sxs-lookup"><span data-stu-id="f191d-288">Install the Teams PowerShell module</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f191d-289">이 단계를 수행하려면 PowerShell 갤러리에서 Teams PowerShell 공개 미리 보기 모듈을 [설치하고 사용해야 합니다.](https://www.powershellgallery.com/packages/MicrosoftTeams/)</span><span class="sxs-lookup"><span data-stu-id="f191d-289">To perform this step, you must install and use the Teams PowerShell public preview module from the [PowerShell Gallery](https://www.powershellgallery.com/packages/MicrosoftTeams/).</span></span> <span data-ttu-id="f191d-290">모듈을 설치하는 방법에 대한 단계는 [Teams PowerShell 설치를 참조하세요.](teams-powershell-install.md)</span><span class="sxs-lookup"><span data-stu-id="f191d-290">For steps on how to install the module, see [Install Teams PowerShell](teams-powershell-install.md).</span></span>

### <a name="sample-script"></a><span data-ttu-id="f191d-291">샘플 스크립트</span><span class="sxs-lookup"><span data-stu-id="f191d-291">Sample script</span></span>

<span data-ttu-id="f191d-292">다음 스크립트를 사용하여 팀을 만들고 .csv 파일을 Microsoft Teams 테넌트에 업로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f191d-292">The following script can be used to create the teams and upload a .csv file to your Microsoft Teams tenant.</span></span> <span data-ttu-id="f191d-293">기존 계층 구조가 있는 경우 이 스크립트는 계층 구조를 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="f191d-293">If you have an existing hierarchy, this script will replace it.</span></span>

#### <a name="create-teams-for-a-simple-hierarchy"></a><span data-ttu-id="f191d-294">간단한 계층 구조를 위한 팀 만들기</span><span class="sxs-lookup"><span data-stu-id="f191d-294">Create teams for a simple hierarchy</span></span>

```powershell
$tm1 = New-Team -DisplayName "HQ"
$tm2 = New-Team -DisplayName "North"
$tm3 = New-Team -DisplayName "Store 1"
$tm4 = New-Team -DisplayName "Store 2"
$tm5 = New-Team -DisplayName "South"
$tm6 = New-Team -DisplayName "Store 3"
$tm7 = New-Team -DisplayName "Store 4"
```

#### <a name="use-team-data-to-create-comma-separated-output-displayname-parentname-teamid"></a><span data-ttu-id="f191d-295">팀 데이터를 사용하여 콤마로 구분된 출력 만들기(DisplayName, ParentName, TeamId)</span><span class="sxs-lookup"><span data-stu-id="f191d-295">Use team data to create comma-separated output (DisplayName, ParentName, TeamId)</span></span>

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

#### <a name="save-output-to-a-csv-file-in-the-downloads-folder"></a><span data-ttu-id="f191d-296">다운로드 폴더의 .csv 파일에 출력 **저장**</span><span class="sxs-lookup"><span data-stu-id="f191d-296">Save output to a .csv file in the **Downloads** folder</span></span>

```powershell
$csvOutputPath = $env:USERPROFILE + "\downloads\testhierarchy-" + (Get-Date -Format "yyyy-MM-dd-hhmmss") + ".csv" 
$csvOutput | Out-File $csvOutputPath
```

#### <a name="upload-the-hierarchy"></a><span data-ttu-id="f191d-297">계층 구조 업로드</span><span class="sxs-lookup"><span data-stu-id="f191d-297">Upload the hierarchy</span></span>

```powershell
Set-TeamTargetingHierarchy -FilePath $csvOutputPath
Get-TeamTargetingHierarchyStatus
```

## <a name="troubleshooting"></a><span data-ttu-id="f191d-298">문제 해결</span><span class="sxs-lookup"><span data-stu-id="f191d-298">Troubleshooting</span></span>

### <a name="how-to-view-error-details"></a><span data-ttu-id="f191d-299">오류 세부 정보를 보는 방법</span><span class="sxs-lookup"><span data-stu-id="f191d-299">How to view error details</span></span>

<span data-ttu-id="f191d-300">다음 명령을 실행하여 오류의 원인을 이해하고 오류 세부 정보를 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f191d-300">You can run the following command to understand what is causing an error and return the error details.</span></span>

```powershell
(Get-TeamTargetingHierarchyStatus).ErrorDetails.ErrorMessage
```

### <a name="you-receive-an-error-message-when-you-upload-your-schema-csv-file"></a><span data-ttu-id="f191d-301">Schema CSV 파일을 업로드할 때 오류 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f191d-301">You receive an error message when you upload your schema CSV file</span></span>

<span data-ttu-id="f191d-302">문제 해결 정보를 포함해야 하여 이 오류 메시지를 메모해 두어, 이 문제를 해결할 수 없는 이유를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f191d-302">Take note of the error message as it should include troubleshooting information to indicate why the schema couldn't be uploaded.</span></span> <span data-ttu-id="f191d-303">오류 메시지의 정보를 기반으로 SCHEMA CSV 파일을 검토하고 편집한 다음 다시 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="f191d-303">Review and edit your schema CSV file based on the information in the error message and then try again.</span></span>

### <a name="you-receive-an-error-invalidteamid-error-message-when-you-upload-your-schema-csv-file"></a><span data-ttu-id="f191d-304">Schema CSV 파일을 업로드할 때 "오류: InvalidTeamId" 오류 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f191d-304">You receive an "Error: InvalidTeamId" error message when you upload your schema CSV file</span></span>

<span data-ttu-id="f191d-305">Schema CSV 파일을 업로드하려고 할 때 다음과 같은 오류 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f191d-305">When you try to upload your schema CSV file, you get the following error message:</span></span>

```console
Error: InvalidTeamId
Description: TeamID in row # doesn't match a valid Group ID. Please view our documentation to learn how to get the proper GroupID for each team.
```

<span data-ttu-id="f191d-306">Schema CSV 파일에서 팀에 대해 올바른 TeamId를 사용하고 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="f191d-306">Check to make sure that you're using the correct TeamId for the team in your schema CSV file.</span></span> <span data-ttu-id="f191d-307">TeamId는 팀을 지원하는 Microsoft 365 그룹의 그룹 ID와 동일해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f191d-307">The TeamId should be the same as the Group ID of the Microsoft 365 group that backs the team.</span></span> <span data-ttu-id="f191d-308">Microsoft Teams 관리 센터에서 팀의 그룹 ID를 찾아 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f191d-308">You can look up the Group ID of the team in the Microsoft Teams admin center.</span></span>

1. <span data-ttu-id="f191d-309">[Microsoft Teams](https://admin.teams.microsoft.com/)관리 센터의 왼쪽 탐색 모음에서 Teams **관리**  >  **팀으로 이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="f191d-309">In the left navigation of the [Microsoft Teams admin center](https://admin.teams.microsoft.com/), go to **Teams** > **Manage teams**.</span></span>
2. <span data-ttu-id="f191d-310">테이블에 그룹 **ID** 열이 표시되지 않는  경우 테이블의 오른쪽 위 모서리에 있는 열 편집을 선택한 다음 그룹 **ID를 켜면 됩니다.**</span><span class="sxs-lookup"><span data-stu-id="f191d-310">If the **Group ID** column isn't displayed in the table, select **Edit columns** in the upper-right corner of the table, and then turn on **Group ID**.</span></span>
3. <span data-ttu-id="f191d-311">목록에서 팀을 찾은 다음 그룹 ID를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="f191d-311">Find the team in the list, and then locate the Group ID.</span></span>

<span data-ttu-id="f191d-312">Schema CSV 파일의 TeamId가 Microsoft Teams 관리 센터에 표시되는 그룹 ID와 일치하는지 확인</span><span class="sxs-lookup"><span data-stu-id="f191d-312">Make sure that the TeamId in your schema CSV file matches the Group ID that's displayed in the Microsoft Teams admin center.</span></span>

## <a name="related-topics"></a><span data-ttu-id="f191d-313">관련 항목</span><span class="sxs-lookup"><span data-stu-id="f191d-313">Related topics</span></span>

* [<span data-ttu-id="f191d-314">Teams에서 조직의 작업 앱 관리</span><span class="sxs-lookup"><span data-stu-id="f191d-314">Manage the Tasks app for your organization in Teams</span></span>](manage-tasks-app.md)
* [<span data-ttu-id="f191d-315">Teams PowerShell 개요</span><span class="sxs-lookup"><span data-stu-id="f191d-315">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
