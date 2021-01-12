---
title: Microsoft Teams의 민감도 레이블
ms.author: mikeplum
author: MikePlumleyMSFT
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
description: Microsoft Teams에서 민감도 레이블을 정의하고 사용하는 방법을 배워야 합니다.
ms.openlocfilehash: d021954a32cc2d93fb7b17726720396e66b4fd39
ms.sourcegitcommit: b68a7b5100fc2b47ae81f465d48d1ac2348c1744
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/11/2021
ms.locfileid: "49795780"
---
# <a name="sensitivity-labels-for-microsoft-teams"></a><span data-ttu-id="631ab-103">Microsoft Teams의 민감도 레이블</span><span class="sxs-lookup"><span data-stu-id="631ab-103">Sensitivity labels for Microsoft Teams</span></span>

<span data-ttu-id="631ab-104">[민감도 레이블을 사용하면](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) Teams 관리자가 팀 내에서 공동 작업하는 동안 생성된 중요한 조직 콘텐츠에 대한 액세스를 규제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="631ab-104">[Sensitivity labels](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) allow Teams admins to regulate access to sensitive organizational content created during collaboration within teams.</span></span> <span data-ttu-id="631ab-105">준수 센터에서 민감도 레이블 및 관련 정책을 정의할 [수 있습니다.](https://docs.microsoft.com/microsoft-365/compliance/go-to-the-securitycompliance-center)</span><span class="sxs-lookup"><span data-stu-id="631ab-105">You can define sensitivity labels and their associated policies in the [Compliance Center](https://docs.microsoft.com/microsoft-365/compliance/go-to-the-securitycompliance-center).</span></span> <span data-ttu-id="631ab-106">이러한 레이블 및 정책은 조직의 팀에 자동으로 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="631ab-106">These labels and policies are automatically applied to teams in your organization.</span></span>  

## <a name="whats-the-difference-between-sensitivity-labels-and-teams-classification-labels"></a><span data-ttu-id="631ab-107">민감도 레이블과 Teams 분류 레이블의 차이점은 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="631ab-107">What's the difference between sensitivity labels and Teams classification labels?</span></span>

<span data-ttu-id="631ab-108">민감도 레이블은 분류 레이블과 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="631ab-108">Sensitivity labels are different from classification labels.</span></span> <span data-ttu-id="631ab-109">분류 레이블은 Microsoft 365 그룹과 연결될 수 있지만 연결된 실제 정책이 없는 텍스트 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="631ab-109">Classification labels are text strings that can be associated with a Microsoft 365 Group but don't have any actual policies associated with them.</span></span> <span data-ttu-id="631ab-110">분류 레이블을 메타데이터로 사용하여 내부 도구 및 스크립트를 통해 정책을 수동으로 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="631ab-110">You use classification labels as metadata to manually enforce policies through internal tools and scripts.</span></span>

<span data-ttu-id="631ab-111">반면에 민감도 레이블 및 해당 정책은 그룹 플랫폼, Security & 준수 센터 및 Teams 서비스의 조합을 통해 종단 & 자동으로 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="631ab-111">On the other hand, sensitivity labels and their policies are automatically enforced end-to-end through a combination of the Groups platform, Security & Compliance Center, and Teams services.</span></span> <span data-ttu-id="631ab-112">민감도 레이블은 조직의 중요한 데이터를 보호하는 강력한 인프라 지원을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="631ab-112">Sensitivity labels provide powerful infrastructure support for securing your organization's sensitive data.</span></span>  

<span data-ttu-id="631ab-113">기존 그룹을 분류 레이블 사용에서 민감도 레이블 사용으로 마이그레이션하려면 [Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/migrate-aad-classification-sensitivity-labels)그룹에 대한 Azure Active Directory 분류 및 민감도 레이블의 지침을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="631ab-113">To migrate your existing groups from using classification labels to using sensitivity labels, use the instructions in [Azure Active Directory classification and sensitivity labels for Microsoft 365 groups](https://docs.microsoft.com/microsoft-365/compliance/migrate-aad-classification-sensitivity-labels).</span></span>

## <a name="create-manage-and-publish-sensitivity-labels-for-teams"></a><span data-ttu-id="631ab-114">Teams에 대한 민감도 레이블 만들기, 관리 및 게시</span><span class="sxs-lookup"><span data-stu-id="631ab-114">Create, manage, and publish sensitivity labels for Teams</span></span>

<span data-ttu-id="631ab-115">Teams에 대한 민감도 레이블을 사용하도록 설정, 만들기 및 게시하는 방법에 대한 자세한 내용은 민감도 레이블을 사용하여 [Microsoft Teams, Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)그룹 및 SharePoint 사이트의 콘텐츠를 보호하세요.</span><span class="sxs-lookup"><span data-stu-id="631ab-115">For how to enable, create, and publish sensitivity labels for Teams, see [Use sensitivity labels to protect content in Microsoft Teams, Microsoft 365 groups, and SharePoint sites](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).</span></span>

>[!IMPORTANT]
><span data-ttu-id="631ab-116">민감도 레이블을 만들고, 업데이트하고, 삭제하려면 사용자에게 레이블을 게시하는 신중한 시차를 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="631ab-116">Creating, updating and deleting sensitivity labels require careful sequencing with publishing labels to users.</span></span> <span data-ttu-id="631ab-117">시퀀스의 모든 오차로 인해 모든 사용자에 대한 영구 팀 만들기 오류가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="631ab-117">Any deviation in the sequence can result in persistent team creation errors for all users.</span></span> <span data-ttu-id="631ab-118">따라서 레이블을 만들고 <a href="#createpublishlabels">게시하고,</a>게시된 레이블을 수정 및 삭제하고, <a href="#modifydeletelabels"></a>팀 만들기 오류를 관리할 때 다음을 해야 <a href="#manageerrors">합니다.</a></span><span class="sxs-lookup"><span data-stu-id="631ab-118">Therefore, it's critical to do the following when you <a href="#createpublishlabels">create and publish labels</a>, <a href="#modifydeletelabels">modify and delete published labels</a>, and <a href="#manageerrors">manage team creation errors</a>.</span></span>

<span data-ttu-id="631ab-119">**레이블 만들기 및 게시** <a name="createpublishlabels"></a></span><span class="sxs-lookup"><span data-stu-id="631ab-119">**Create and publish labels** <a name="createpublishlabels"> </a></span></span>

<span data-ttu-id="631ab-120">레이블을 만들어 준수 센터에 게시하면 팀 만들기 인터페이스에 레이블이 표시될 때 최대 10분이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="631ab-120">When a label is created and published in the Compliance Center, it can take up to 10 minutes for the label to become visible in the teams creation interface.</span></span> <span data-ttu-id="631ab-121">다음 단계를 사용하여 테넌트의 모든 사용자에 대한 레이블을 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="631ab-121">Use the following steps to publish the label for all users in the tenant:</span></span>
1. <span data-ttu-id="631ab-122">레이블을 만들고 테넌트에서 몇 가지 선택된 사용자 계정에 대해 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="631ab-122">Create the label and publish it for a few select user accounts in the tenant.</span></span>
2. <span data-ttu-id="631ab-123">레이블이 게시될 때 10분 정도 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="631ab-123">When the label is published, wait 10 minutes.</span></span>
3. <span data-ttu-id="631ab-124">10분 후에 레이블에 대한 액세스 권한이 있는 사용자 계정 중 하나를 사용하여 레이블이 있는 팀을 만들어 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="631ab-124">After 10 minutes, try to create a team with the label using one of the user accounts that have access to the label.</span></span>
4. <span data-ttu-id="631ab-125">팀이 3단계에서 성공적으로 만든 경우 계속 진행하여 테넌트의 나머지 사용자에 대한 레이블을 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="631ab-125">If the team successfully created in step 3, then go ahead and publish the label for the remaining users in the tenant.</span></span>

<span data-ttu-id="631ab-126">**게시된 레이블 수정 및 삭제** <a name="modifydeletelabels"></a></span><span class="sxs-lookup"><span data-stu-id="631ab-126">**Modify and delete published labels** <a name="modifydeletelabels"> </a></span></span>

<span data-ttu-id="631ab-127">민감도 정책과 연결된 레이블을 삭제하거나 수정하면 테넌트 전체에서 팀 만들기에 실패할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="631ab-127">Deleting or modifying the label while it's associated with sensitivity policies can result in team creation failures across the tenant.</span></span> <span data-ttu-id="631ab-128">따라서 레이블을 삭제하거나 수정하기 전에 먼저 연결된 정책에서 레이블을 연결 취소해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="631ab-128">Therefore, before you delete or modify a label, you must first disassociate the label from its associated policies.</span></span> <span data-ttu-id="631ab-129">다음 단계 사용</span><span class="sxs-lookup"><span data-stu-id="631ab-129">Use the following steps</span></span>  
<span data-ttu-id="631ab-130">레이블을 삭제하거나 수정하려면:</span><span class="sxs-lookup"><span data-stu-id="631ab-130">to delete or modify a label:</span></span>
1. <span data-ttu-id="631ab-131">레이블을 사용하는 모든 정책에서 레이블을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="631ab-131">Remove the label from all policies that use the label.</span></span> <span data-ttu-id="631ab-132">또는 정책 자체를 삭제할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="631ab-132">Alternatively, you can also delete the policies themselves.</span></span>
2. <span data-ttu-id="631ab-133">레이블이 정책에서 제거되거나 정책 자체가 삭제되면 10분 동안 기다렸다가 계속 진행합니다.</span><span class="sxs-lookup"><span data-stu-id="631ab-133">When the label is removed from the policies or the policies themselves are deleted, wait 10 minutes before proceeding further.</span></span>
3. <span data-ttu-id="631ab-134">10분 후에 팀 만들기 인터페이스를 시작하고 테넌트의 모든 사용자에게 레이블이 더 이상 표시되지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="631ab-134">After 10 minutes, launch the team creation interface and ensure that the label is no longer visible for any user in the tenant.</span></span>
4. <span data-ttu-id="631ab-135">이제 레이블을 안전하게 삭제하거나 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="631ab-135">Now you can safely delete or modify the label.</span></span>

<span data-ttu-id="631ab-136">**팀 만들기 오류 관리** <a name="manageerrors"></a></span><span class="sxs-lookup"><span data-stu-id="631ab-136">**Manage team creation errors** <a name="manageerrors"> </a></span></span>

<span data-ttu-id="631ab-137">공개 미리 보기 중 어느 시점에서든 팀 만들기가 실패하기 시작하는 경우 다음 두 가지 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="631ab-137">If team creation begins to fail at any point during the public preview, you have two options:</span></span>
 - <span data-ttu-id="631ab-138">팀을 만들 때 민감도 레이블이 사용자에 대해 필수가 아닌지 확인</span><span class="sxs-lookup"><span data-stu-id="631ab-138">Ensure that sensitivity labels are not mandatory for any user during team creation.</span></span>
 - <span data-ttu-id="631ab-139">이 미리 보기 사용에서 스크립트를 사용하여 민감도 [레이블을 해제합니다.](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites#enable-this-preview)</span><span class="sxs-lookup"><span data-stu-id="631ab-139">Turn off sensitivity labels using the scripts in [Enable this preview](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites#enable-this-preview).</span></span>

<span data-ttu-id="631ab-140">EnableMIPLabels 설정은 다음과 같이 false로 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="631ab-140">Note that the EnableMIPLabels setting must be set to false as follows:</span></span>

```console
$setting["EnableMIPLabels"] = "False"
```

## <a name="using-sensitivity-labels-with-teams"></a><span data-ttu-id="631ab-141">Teams에서 민감도 레이블 사용</span><span class="sxs-lookup"><span data-stu-id="631ab-141">Using sensitivity labels with Teams</span></span>

<span data-ttu-id="631ab-142">다음은 조직의 Teams에서 민감도 레이블을 사용하는 방법에 대한 몇 가지 예제 시나리오입니다.</span><span class="sxs-lookup"><span data-stu-id="631ab-142">Here are some example scenarios of how you can use sensitivity labels with Teams in your organization.</span></span>

### <a name="privacy-setting-of-teams"></a><span data-ttu-id="631ab-143">팀의 개인 정보 설정</span><span class="sxs-lookup"><span data-stu-id="631ab-143">Privacy setting of teams</span></span>

<span data-ttu-id="631ab-144">팀을 만드는 동안 적용될 때 사용자가 특정 개인 정보(공개 또는 비공개) 설정으로 팀을 만들 수 있도록 하는 민감도 레이블을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="631ab-144">You can create a sensitivity label that, when applied during team creation, allows users to create teams with a specific privacy (public or private) setting.</span></span>

<span data-ttu-id="631ab-145">예를 들어 보안 & 준수 센터에서 "기밀"이라는 레이블을 만들고 이 레이블로 만든 모든 팀이 비공개 팀이 되어야 하도록 Teams를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="631ab-145">For example, you create a label named “Confidential” in the Security & Compliance Center and you configure Teams so that any team that's created with this label must be a private team.</span></span> <span data-ttu-id="631ab-146">사용자가 새 팀을 만들고 기밀  레이블을 선택하면 사용자가 사용할 수 있는 유일한 개인 정보 옵션은 **비공개입니다.**</span><span class="sxs-lookup"><span data-stu-id="631ab-146">When a user creates a new team and selects the **Confidential** label, the only privacy option that's available to the user is **Private**.</span></span> <span data-ttu-id="631ab-147">공개 및 전체와 같은 기타 개인 정보 옵션은 사용자에 대해 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="631ab-147">Other privacy options such as Public and Org-wide are disabled for the user.</span></span>

![기밀 민감도 레이블 스크린샷](media/sensitivity-labels-confidential-example.png)

<span data-ttu-id="631ab-149">마찬가지로 사용자가 새 팀을 만들 때 **일반을** 선택하는 경우 공개 또는 전체 팀만 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="631ab-149">Similarly, if the user selects **General** when they create a new team, they can only create public or org-wide teams.</span></span>

![일반 민감도 레이블 스크린샷](media/sensitivity-labels-general-example.png)

<span data-ttu-id="631ab-151">팀을 만들면 민감도 레이블이 팀의 채널 오른쪽 위 모서리에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="631ab-151">When the team is created, the sensitivity label is visible in the upper-right corner of channels in the team.</span></span>

![팀 채널의 민감도 레이블 스크린샷](media/sensitivity-labels-channel.png)

<span data-ttu-id="631ab-153">팀 소유자는 팀으로 이동한 다음 편집 팀을 클릭하여 팀의 민감도 레이블 및 개인 정보 설정을 변경할 **수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="631ab-153">A team owner can change the sensitivity label and the privacy setting of the team at any time by going to the team, and then clicking **Edit team**.</span></span>

![팀 속성의 민감도 레이블 스크린샷](media/sensitivity-labels-edit-team.png)

### <a name="guest-access-to-teams"></a><span data-ttu-id="631ab-155">팀에 대한 게스트 액세스</span><span class="sxs-lookup"><span data-stu-id="631ab-155">Guest access to teams</span></span>

<span data-ttu-id="631ab-156">특정 레이블을 사용하여 만든 팀이 게스트 액세스를 허용할지 여부를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="631ab-156">You can specify whether a team created with a specific label allows guest access.</span></span> <span data-ttu-id="631ab-157">게스트 액세스를 허용하지 않는 레이블로 만든 팀은 조직의 사용자만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="631ab-157">Teams created with a label that doesn't allow guest access are only available to users in your organization.</span></span> <span data-ttu-id="631ab-158">조직 외부의 사람은 팀에 추가할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="631ab-158">People outside your organization can't be added to the team.</span></span>

### <a name="sensitivity-labels-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="631ab-159">Microsoft Teams 관리 센터의 민감도 레이블</span><span class="sxs-lookup"><span data-stu-id="631ab-159">Sensitivity labels in the Microsoft Teams admin center</span></span>

<span data-ttu-id="631ab-160">Microsoft Teams 관리 센터에서 팀을 만들거나 편집할 때 민감도 레이블을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="631ab-160">You can set sensitivity labels when you create or edit a team in the Microsoft Teams admin center.</span></span> <span data-ttu-id="631ab-161">민감도 레이블은 팀 속성 및 Microsoft  Teams 관리 센터의 팀 관리 페이지의 분류 열에도 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="631ab-161">Sensitivity labels are also visible in team properties and in the **Classification** column on the Manage teams page of the Microsoft Teams admin center.</span></span>

## <a name="known-issues"></a><span data-ttu-id="631ab-162">알려진 문제</span><span class="sxs-lookup"><span data-stu-id="631ab-162">Known issues</span></span>

<span data-ttu-id="631ab-163">**Teams Graph API, PowerShell cmdlet 및 템플릿에서 민감도 레이블 지원**</span><span class="sxs-lookup"><span data-stu-id="631ab-163">**Support for sensitivity labels in Teams Graph APIs, PowerShell cmdlets and templates**</span></span>

<span data-ttu-id="631ab-164">현재 사용자는 Graph API, PowerShell cmdlet 및 템플릿을 통해 직접 만든 팀에 민감도 레이블을 적용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="631ab-164">Currently, users won't be able to apply sensitivity labels on teams that are created directly through Graph APIs, PowerShell cmdlets, and templates.</span></span>

<span data-ttu-id="631ab-165">**Teams EDU SKU의 민감도 레이블 지원**</span><span class="sxs-lookup"><span data-stu-id="631ab-165">**Support for sensitivity labels in Teams EDU SKUs**</span></span>

<span data-ttu-id="631ab-166">민감도 레이블은 현재 Teams Education SKUS를 사용하는 고객에게 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="631ab-166">Sensitivity labels are currently unsupported for customers using Teams Education SKUs.</span></span>

<span data-ttu-id="631ab-167">**개인 채널의 SharePoint 사이트 모음에서 직접 민감도 레이블 편집**</span><span class="sxs-lookup"><span data-stu-id="631ab-167">**Editing sensitivity labels directly on a SharePoint site collection for private channels**</span></span>

<span data-ttu-id="631ab-168">팀에서 만든 비공개 채널은 팀에 적용된 민감도 레이블을 상속합니다.</span><span class="sxs-lookup"><span data-stu-id="631ab-168">Private channels that are created in a team inherit the sensitivity label which was applied on a team.</span></span> <span data-ttu-id="631ab-169">또한 동일한 레이블이 개인 채널의 SharePoint 사이트 모음에 자동으로 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="631ab-169">Furthermore, the same label is automatically applied on the SharePoint site collection for the private channel.</span></span>

<span data-ttu-id="631ab-170">사용자가 개인 채널의 SharePoint 사이트 모음에서 민감도 레이블을 직접 업데이트하는 경우 해당 레이블은 Teams 클라이언트에서 업데이트되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="631ab-170">If a user directly updates the sensitivity label on a SharePoint site collection for a private channel, that label isn't updated in the Teams client.</span></span> <span data-ttu-id="631ab-171">이 시나리오에서 사용자는 개인 채널 헤더에서 팀에 적용된 민감도 레이블을 계속 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="631ab-171">In this scenario, users will continue to see the sensitivity label applied on a team in the private channel header.</span></span>

<span data-ttu-id="631ab-172">**Teams 앱 외부의 민감도 레이블에 적용된 변경 내용의 전파 시간**</span><span class="sxs-lookup"><span data-stu-id="631ab-172">**Propagation times for changes applied to sensitivity labels outside the Teams app**</span></span>

<span data-ttu-id="631ab-173">Teams 앱 외부의 민감도 레이블에 대한 변경 내용은 Teams 앱에 반영하는 데 최대 24시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="631ab-173">Changes made to sensitivity labels outside the Teams app can take up to 24 hours to reflect in the Teams app.</span></span> <span data-ttu-id="631ab-174">이는 테넌트에 대한 레이블을 사용 또는 사용하지 않도록 설정하기 위해 변경한 내용, 레이블 이름, 설정 및 정책에 대한 변경 내용에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="631ab-174">This applies to any changes made to enable or disable labels for a tenant, changes to label names, settings, and policies.</span></span>

<span data-ttu-id="631ab-175">또한 팀을 지원하는 그룹 또는 SharePoint 사이트 모음에 직접 적용된 레이블을 변경하면 Teams 앱에 전파되는 데 최대 24시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="631ab-175">Additionally, any changes to a label made directly to a group or SharePoint site collection that backs the team can take up to 24 hours to propagate to the Teams app.</span></span>
