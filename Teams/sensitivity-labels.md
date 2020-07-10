---
title: Microsoft 팀의 민감도 레이블
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: abgupta
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
description: Microsoft 팀에서 우편물 종류 레이블을 정의 하 고 사용 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: 4f1bdc4715fd1375cff637604c93962e2f30c258
ms.sourcegitcommit: d7f49f8c28cba32d3715ea1965c736e6ba574bda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/09/2020
ms.locfileid: "45091271"
---
# <a name="sensitivity-labels-for-microsoft-teams"></a><span data-ttu-id="4807e-103">Microsoft 팀의 민감도 레이블</span><span class="sxs-lookup"><span data-stu-id="4807e-103">Sensitivity labels for Microsoft Teams</span></span>

<span data-ttu-id="4807e-104">[우편물 종류 레이블을](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) 사용 하면 팀 관리자가 팀 내에서 공동 작업을 수행 하는 중요 한 조직 콘텐츠에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4807e-104">[Sensitivity labels](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) allow Teams admins to regulate access to sensitive organizational content created during collaboration within teams.</span></span> <span data-ttu-id="4807e-105">[보안 & 준수 센터](https://docs.microsoft.com/microsoft-365/compliance/go-to-the-securitycompliance-center)에서 민감도 레이블 및 관련 정책을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4807e-105">You can define sensitivity labels and their associated policies in the [Security & Compliance Center](https://docs.microsoft.com/microsoft-365/compliance/go-to-the-securitycompliance-center).</span></span> <span data-ttu-id="4807e-106">이러한 레이블과 정책은 조직의 팀에 자동으로 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4807e-106">These labels and policies are automatically applied to teams in your organization.</span></span>  

## <a name="whats-the-difference-between-sensitivity-labels-and-teams-classification-labels"></a><span data-ttu-id="4807e-107">민감도 레이블과 팀 분류 레이블의 차이점은 무엇 인가요?</span><span class="sxs-lookup"><span data-stu-id="4807e-107">What's the difference between sensitivity labels and Teams classification labels?</span></span>

<span data-ttu-id="4807e-108">민감도 레이블은 PowerShell을 사용 하 여 만들어야 할 분류 레이블과 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="4807e-108">Sensitivity labels are different from classification labels that require you to create them using PowerShell.</span></span> <span data-ttu-id="4807e-109">분류 레이블은 그룹과 연결 될 수 있지만 관련 된 실제 정책이 없는 텍스트 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="4807e-109">Classification labels are text strings that can be associated with a group but don't have any actual policies associated with them.</span></span> <span data-ttu-id="4807e-110">분류 레이블을 메타 데이터로 사용 하 여 내부 도구 및 스크립트를 통해 정책을 수동으로 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4807e-110">You use classification labels as metadata to manually enforce policies through internal tools and scripts.</span></span>

<span data-ttu-id="4807e-111">다른 한편, 민감도 레이블과 해당 정책은 그룹 플랫폼, 보안 & 준수 센터, 팀 서비스를 조합 하 여 자동으로 종단 간 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4807e-111">On the other hand, sensitivity labels and their policies are automatically enforced end-to-end through a combination of the Groups platform, Security & Compliance Center, and Teams services.</span></span> <span data-ttu-id="4807e-112">민감도 레이블은 조직의 민감한 데이터를 보호 하기 위한 강력한 인프라 지원을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="4807e-112">Sensitivity labels provide powerful infrastructure support for securing your organization's sensitive data.</span></span>  

<span data-ttu-id="4807e-113">분류 레이블을 사용 하 여 기존 그룹을 마이그레이션 하려면 [Microsoft 365 그룹에 대 한 Azure Active Directory 분류 및 민감도 레이블의](https://docs.microsoft.com/microsoft-365/compliance/migrate-aad-classification-sensitivity-labels)지침을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4807e-113">To migrate your existing Groups from using classification labels to using sensitivity labels, use the instructions in [Azure Active Directory classification and sensitivity labels for Microsoft 365 groups](https://docs.microsoft.com/microsoft-365/compliance/migrate-aad-classification-sensitivity-labels).</span></span>
## <a name="create-manage-and-publish-sensitivity-labels-for-teams"></a><span data-ttu-id="4807e-114">팀에 대 한 민감도 레이블 만들기, 관리 및 게시</span><span class="sxs-lookup"><span data-stu-id="4807e-114">Create, manage, and publish sensitivity labels for Teams</span></span>

<span data-ttu-id="4807e-115">팀의 민감도 레이블을 사용, 만들기, 게시 하는 방법에 대 한 자세한 내용은 [Microsoft 365 그룹의 Azure Active Directory 분류 및 민감도 레이블을](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4807e-115">For how to enable, create, and publish sensitivity labels for Teams, see [Azure Active Directory classification and sensitivity labels for Microsoft 365 groups](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).</span></span>

>[!IMPORTANT]
><span data-ttu-id="4807e-116">민감도 레이블을 만들고 업데이트 하 고 삭제 하는 경우에는 레이블을 사용자에 게 게시할 때 주의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4807e-116">Creating, updating and deleting sensitivity labels require careful sequencing with publishing labels to users.</span></span> <span data-ttu-id="4807e-117">시퀀스의 모든 편차를 통해 모든 사용자에 대해 영구 팀 만들기 오류가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4807e-117">Any deviation in the sequence can result in persistent team creation errors for all users.</span></span> <span data-ttu-id="4807e-118">따라서 <a href="#createpublishlabels">레이블을 만들고 게시</a>하 고, <a href="#modifydeletelabels">게시 된 레이블을 수정 및 삭제</a>하 고, <a href="#manageerrors">팀 만들기 오류를 관리</a>하는 경우에는 다음과 같은 작업을 수행 하는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="4807e-118">Therefore, it's critical to do the following when you <a href="#createpublishlabels">create and publish labels</a>, <a href="#modifydeletelabels">modify and delete published labels</a>, and <a href="#manageerrors">manage team creation errors</a>.</span></span>

<span data-ttu-id="4807e-119"><a name="createpublishlabels"> </a> **레이블 만들기 및 게시**</span><span class="sxs-lookup"><span data-stu-id="4807e-119">**Create and publish labels** <a name="createpublishlabels"> </a></span></span>

<span data-ttu-id="4807e-120">보안 & 준수 센터에서 레이블을 만들고 게시 하는 경우 팀 만들기 인터페이스에서 레이블이 표시 되는 데 최대 10 분이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4807e-120">When a label is created and published in the Security & Compliance Center, it can take up to 10 minutes for the label to become visible in the teams creation interface.</span></span> <span data-ttu-id="4807e-121">다음 단계를 사용 하 여 테 넌 트의 모든 사용자에 대 한 레이블을 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="4807e-121">Use the following steps to publish the label for all users in the tenant:</span></span>
1. <span data-ttu-id="4807e-122">테 넌 트의 몇 가지 선택 사용자 계정에 대해 레이블을 만들고 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="4807e-122">Create the label and publish it for a few select user accounts in the tenant.</span></span>
2. <span data-ttu-id="4807e-123">레이블이 게시 되 면 10 분 동안 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="4807e-123">When the label is published, wait 10 minutes.</span></span>
3. <span data-ttu-id="4807e-124">10 분 후에는 레이블에 대 한 액세스 권한이 있는 사용자 계정 중 하나를 사용 하 여 레이블이 포함 된 팀을 만들어 봅니다.</span><span class="sxs-lookup"><span data-stu-id="4807e-124">After 10 minutes, try to create a team with the label using one of the user accounts that have access to the label.</span></span>
4. <span data-ttu-id="4807e-125">팀이 3 단계에서 성공적으로 만들어졌으면 나머지 사용자에 대 한 레이블을 테 넌 트에 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="4807e-125">If the team successfully created in step 3, then go ahead and publish the label for the remaining users in the tenant.</span></span>

<span data-ttu-id="4807e-126">게시 된 <a name="modifydeletelabels"> </a> **레이블 수정 및 삭제**</span><span class="sxs-lookup"><span data-stu-id="4807e-126">**Modify and delete published labels** <a name="modifydeletelabels"> </a></span></span>

<span data-ttu-id="4807e-127">우편물 종류 정책에 연결 된 상태에서 레이블을 삭제 하거나 수정 하면 테 넌 트에서 팀 만들기 오류가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4807e-127">Deleting or modifying the label while it's associated with sensitivity policies can result in team creation failures across the tenant.</span></span> <span data-ttu-id="4807e-128">따라서 레이블을 삭제 하거나 수정 하기 전에 먼저 연결 된 정책에서 레이블의 연관을 해제 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4807e-128">Therefore, before you delete or modify a label, you must first disassociate the label from its associated policies.</span></span> <span data-ttu-id="4807e-129">다음 단계 사용</span><span class="sxs-lookup"><span data-stu-id="4807e-129">Use the following steps</span></span>  
<span data-ttu-id="4807e-130">레이블을 삭제 하거나 수정 하려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="4807e-130">to delete or modify a label:</span></span>
1. <span data-ttu-id="4807e-131">레이블을 사용 하는 모든 정책에서 레이블을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="4807e-131">Remove the label from all policies that use the label.</span></span> <span data-ttu-id="4807e-132">또는 정책 자체를 삭제할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4807e-132">Alternatively, you can also delete the policies themselves.</span></span>
2. <span data-ttu-id="4807e-133">정책에서 레이블을 제거 하거나 정책 자체를 삭제 하면 10 분 후에 추가를 계속 합니다.</span><span class="sxs-lookup"><span data-stu-id="4807e-133">When the label is removed from the policies or the policies themselves are deleted, wait 10 minutes before proceeding further.</span></span>
3. <span data-ttu-id="4807e-134">10 분 후 팀 만들기 인터페이스를 시작 하 고 테 넌 트에서 사용자에 게 레이블이 더 이상 표시 되지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="4807e-134">After 10 minutes, launch the team creation interface and ensure that the label is no longer visible for any user in the tenant.</span></span>
4. <span data-ttu-id="4807e-135">이제 레이블을 안전 하 게 삭제 하거나 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4807e-135">Now you can safely delete or modify the label.</span></span>

<span data-ttu-id="4807e-136">**팀 만들기 오류 관리** <a name="manageerrors"> </a></span><span class="sxs-lookup"><span data-stu-id="4807e-136">**Manage team creation errors** <a name="manageerrors"> </a></span></span>

<span data-ttu-id="4807e-137">공용 미리 보기 중에 팀 만들기가 특정 시점에 실패 하기 시작 하면 다음 두 가지 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4807e-137">If team creation begins to fail at any point during the public preview, you have two options:</span></span>
 - <span data-ttu-id="4807e-138">팀을 만드는 동안 우편물 종류 레이블이 사용자에 게 필수적이 지 않은지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="4807e-138">Ensure that sensitivity labels are not mandatory for any user during team creation.</span></span>
 - <span data-ttu-id="4807e-139">[이 미리 보기 사용](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites#enable-this-preview)에서 스크립트를 사용 하 여 민감도 레이블을 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="4807e-139">Turn off sensitivity labels using the scripts in [Enable this preview](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites#enable-this-preview).</span></span>

<span data-ttu-id="4807e-140">EnableMIPLabels 설정은 다음과 같이 false로 설정 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4807e-140">Note that the EnableMIPLabels setting must be set to false as follows:</span></span>

```console
$setting["EnableMIPLabels"] = "False"
```

## <a name="using-sensitivity-labels-with-teams"></a><span data-ttu-id="4807e-141">팀과 우편물 종류 레이블 사용</span><span class="sxs-lookup"><span data-stu-id="4807e-141">Using sensitivity labels with Teams</span></span>

<span data-ttu-id="4807e-142">조직의 팀에서 민감도 레이블을 사용 하는 방법에 대 한 몇 가지 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4807e-142">Here are some example scenarios of how you can use sensitivity labels with Teams in your organization.</span></span>

### <a name="privacy-setting-of-teams"></a><span data-ttu-id="4807e-143">팀의 개인 정보 설정</span><span class="sxs-lookup"><span data-stu-id="4807e-143">Privacy setting of teams</span></span>

<span data-ttu-id="4807e-144">팀을 만드는 동안 적용 하면 사용자가 특정 개인 정보 (공개 또는 비공개) 설정을 사용 하 여 팀을 만들 수 있는 민감도 레이블을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4807e-144">You can create a sensitivity label that, when applied during team creation, allows users to create teams with a specific privacy (public or private) setting.</span></span>

<span data-ttu-id="4807e-145">예를 들어 보안 & 준수 센터에 "기밀" 이라는 레이블을 만들고이 레이블을 사용 하 여 만든 모든 팀이 개인 팀 이어야 하도록 팀을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="4807e-145">For example, you create a label named “Confidential” in the Security & Compliance Center and you configure Teams so that any team that's created with this label must be a private team.</span></span> <span data-ttu-id="4807e-146">사용자가 새 팀을 만들고 **기밀** 레이블을 선택 하는 경우 사용자가 사용할 수 있는 개인 정보 옵션은 **비공개**입니다.</span><span class="sxs-lookup"><span data-stu-id="4807e-146">When a user creates a new team and selects the **Confidential** label, the only privacy option that's available to the user is **Private**.</span></span> <span data-ttu-id="4807e-147">공개 및 조직 전체와 같은 기타 개인 정보 옵션을 사용자에 게 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4807e-147">Other privacy options such as Public and Org-wide are disabled for the user.</span></span>

![비밀 민감도 레이블의 스크린샷](media/sensitivity-labels-confidential-example.png)

<span data-ttu-id="4807e-149">마찬가지로 사용자가 새 팀을 만들 때 **일반** 을 선택 하는 경우에는 공용 또는 조직 차원의 팀만 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4807e-149">Similarly, if the user selects **General** when they create a new team, they can only create public or org-wide teams.</span></span>

![일반 민감도 레이블의 스크린샷](media/sensitivity-labels-general-example.png)

<span data-ttu-id="4807e-151">팀을 만들 때 우편물 종류 레이블은 팀의 채널 오른쪽 위 모서리에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4807e-151">When the team is created, the sensitivity label is visible in the upper-right corner of channels in the team.</span></span>

![팀 채널의 우편물 종류 레이블 스크린샷](media/sensitivity-labels-channel.png)

<span data-ttu-id="4807e-153">팀 소유자는 팀으로 이동한 다음 **팀 편집**을 클릭 하 여 언제 든 지 팀의 민감도 레이블과 개인 정보 설정을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4807e-153">A team owner can change the sensitivity label and the privacy setting of the team at any time by going to the team, and then clicking **Edit team**.</span></span>

![팀 채널의 우편물 종류 레이블 스크린샷](media/sensitivity-labels-edit-team.png)

### <a name="guest-access-to-teams"></a><span data-ttu-id="4807e-155">팀에 대 한 게스트 액세스</span><span class="sxs-lookup"><span data-stu-id="4807e-155">Guest access to teams</span></span>

<span data-ttu-id="4807e-156">특정 레이블을 사용 하 여 만든 팀에서 게스트 액세스를 허용 하는지 여부를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4807e-156">You can specify whether a team created with a specific label allows guest access.</span></span> <span data-ttu-id="4807e-157">게스트 액세스를 허용 하지 않는 레이블을 사용 하 여 만든 팀은 조직의 사용자만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4807e-157">Teams created with a label that doesn't allow guest access are only available to users in your organization.</span></span> <span data-ttu-id="4807e-158">조직 외부의 사용자를 팀에 추가할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4807e-158">People outside your organization can't be added to the team.</span></span>

### <a name="sensitivity-labels-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="4807e-159">Microsoft 팀 관리 센터의 민감도 레이블</span><span class="sxs-lookup"><span data-stu-id="4807e-159">Sensitivity labels in the Microsoft Teams admin center</span></span>

<span data-ttu-id="4807e-160">Microsoft 팀 관리 센터에서 팀을 만들거나 편집할 때 우편물 종류 레이블을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4807e-160">You can set sensitivity labels when you create or edit a team in the Microsoft Teams admin center.</span></span> <span data-ttu-id="4807e-161">민감도 레이블은 팀 속성과 Microsoft 팀 관리 센터의 팀 관리 페이지에 있는 **분류** 열에도 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4807e-161">Sensitivity labels are also visible in team properties and in the **Classification** column on the Manage teams page of the Microsoft Teams admin center.</span></span>

## <a name="known-issues"></a><span data-ttu-id="4807e-162">알려진 문제</span><span class="sxs-lookup"><span data-stu-id="4807e-162">Known issues</span></span>

<span data-ttu-id="4807e-163">**팀을 만드는 동안 자식 기본 레이블이 표시 되지 않음**</span><span class="sxs-lookup"><span data-stu-id="4807e-163">**Child default labels not showing during team creation**</span></span>

<span data-ttu-id="4807e-164">현재, 팀에 대 한 기본 레이블로 설정 된 자식 레이블이 목록 맨 위에 표시 되지 않으며,이는 팀 만들기 모델의 민감도 레이블 드롭다운입니다.</span><span class="sxs-lookup"><span data-stu-id="4807e-164">Currently, a child label set as the default label for Teams will not show at the top of the list in the sensitivity labels dropdown in the team creation model.</span></span> <span data-ttu-id="4807e-165">팀 작성자는 여전히 드롭다운을 사용 하 여 해결 방법으로 하위 레이블을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4807e-165">Team creators can still use the dropdown to apply the child label as a workaround.</span></span>

<span data-ttu-id="4807e-166">**팀 그래프 Api, Powershell cmdlet 및 템플릿에 대 한 민감도 레이블 지원**</span><span class="sxs-lookup"><span data-stu-id="4807e-166">**Support for sensitivity labels in Teams Graph APIs, Powershell cmdlets and templates**</span></span>

<span data-ttu-id="4807e-167">현재 사용자는 Graph Api, Powershell cmdlet, 템플릿을 통해 직접 만든 팀에 민감도 레이블을 적용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4807e-167">Currently, users won't be able to apply sensitivity labels on teams that are created directly through Graph APIs, Powershell cmdlets, and templates.</span></span>

<span data-ttu-id="4807e-168">**팀의 .EDU Sku에서 민감도 레이블 지원**</span><span class="sxs-lookup"><span data-stu-id="4807e-168">**Support for sensitivity labels in Teams EDU SKUs**</span></span>

<span data-ttu-id="4807e-169">민감도 레이블은 팀 교육 Sku를 사용 하는 고객에 게 현재 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4807e-169">Sensitivity labels are currently unsupported for customers using Teams Education SKUs.</span></span>

<span data-ttu-id="4807e-170">**개인 채널의 SharePoint 사이트 모음에서 우편물 종류 레이블을 직접 편집**</span><span class="sxs-lookup"><span data-stu-id="4807e-170">**Editing sensitivity labels directly on a SharePoint site collection for private channels**</span></span>

<span data-ttu-id="4807e-171">팀에서 만든 개인 채널은 팀에 적용 된 민감도 레이블을 상속 합니다.</span><span class="sxs-lookup"><span data-stu-id="4807e-171">Private channels that are created in a team inherit the sensitivity label which was applied on a team.</span></span> <span data-ttu-id="4807e-172">또한 개인 채널의 SharePoint 사이트 모음에도 동일한 레이블이 자동으로 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4807e-172">Furthermore, the same label is automatically applied on the SharePoint site collection for the private channel.</span></span>

<span data-ttu-id="4807e-173">사용자가 개인 채널의 SharePoint 사이트 모음에서 우편물 종류 레이블을 직접 업데이트 하는 경우 팀 클라이언트에서 해당 레이블이 업데이트 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4807e-173">If a user directly updates the sensitivity label on a SharePoint site collection for a private channel, that label isn't updated in the Teams client.</span></span> <span data-ttu-id="4807e-174">이 시나리오에서는 사용자가 개인 채널 헤더에서 팀에 적용 된 우편물 종류 레이블을 계속 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4807e-174">In this scenario, users will continue to see the sensitivity label applied on a team in the private channel header.</span></span>

<span data-ttu-id="4807e-175">**팀 앱 외부의 민감도 레이블에 적용 된 변경 내용에 대 한 전파 시간**</span><span class="sxs-lookup"><span data-stu-id="4807e-175">**Propagation times for changes applied to sensitivity labels outside the Teams app**</span></span>

<span data-ttu-id="4807e-176">팀 앱 외부의 민감도 레이블에 대 한 변경 사항은 팀 앱에서 적용 하는 데 최대 24 시간까지 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4807e-176">Changes made to sensitivity labels outside the Teams app can take up to 24 hours to reflect in the Teams app.</span></span> <span data-ttu-id="4807e-177">이는 테 넌 트의 레이블을 사용 하거나 사용 하지 않도록 변경한 내용, 레이블 이름, 설정, 정책의 변경에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4807e-177">This applies to any changes made to enable or disable labels for a tenant, changes to label names, settings, and policies.</span></span>

<span data-ttu-id="4807e-178">또한 팀을 지 원하는 그룹 또는 SharePoint 사이트 모음에 직접 변경한 내용은 팀 앱에 전파 하는 데 최대 24 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4807e-178">Additionally, any changes to a label made directly to a group or SharePoint site collection that backs the team can take up to 24 hours to propagate to the Teams app.</span></span>
