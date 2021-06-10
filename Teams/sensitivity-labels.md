---
title: 에 대한 민감도 Microsoft Teams
ms.author: mikeplum
author: cabailey
manager: laurawi
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
description: 민감도 레이블을 사용하여 팀을 보호하는 방법을 Microsoft Teams.
ms.openlocfilehash: 461daf6e91f9ba276dceef1929601d1188563931
ms.sourcegitcommit: f223b5f3735f165d46bb611a52fcdfb0f4b88f66
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/06/2021
ms.locfileid: "51593866"
---
# <a name="sensitivity-labels-for-microsoft-teams"></a><span data-ttu-id="b425f-103">에 대한 민감도 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b425f-103">Sensitivity labels for Microsoft Teams</span></span>

<span data-ttu-id="b425f-104">[민감도](/microsoft-365/compliance/sensitivity-labels) 레이블을 사용하면 Teams 관리자가 팀 내에서 공동 작업하는 동안 생성된 중요한 조직 콘텐츠에 대한 액세스를 보호하고 규제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b425f-104">[Sensitivity labels](/microsoft-365/compliance/sensitivity-labels) allow Teams admins to protect and regulate access to sensitive organizational content created during collaboration within teams.</span></span> <span data-ttu-id="b425f-105">[Microsoft](/microsoft-365/compliance/go-to-the-securitycompliance-center)규정 준수 센터에서 관련 정책으로 민감도 레이블을 구성한 후 이러한 레이블을 조직의 팀에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b425f-105">After you configure sensitivity labels with their associated policies in the [Microsoft compliance center](/microsoft-365/compliance/go-to-the-securitycompliance-center), these labels can be applied to teams in your organization.</span></span>

<span data-ttu-id="b425f-106">민감도 레이블은 현재 교육 SKUS를 사용하는 고객을 위한 수업 팀에서 지원되지 Teams 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b425f-106">Sensitivity labels are currently unsupported in class teams for customers using Teams Education SKUs.</span></span> <span data-ttu-id="b425f-107">라이선스에 대한 자세한 내용은 서비스 [Microsoft Teams 참조하세요.](/office365/servicedescriptions/teams-service-description)</span><span class="sxs-lookup"><span data-stu-id="b425f-107">To learn more about licensing, see [Microsoft Teams service description](/office365/servicedescriptions/teams-service-description).</span></span>

## <a name="whats-the-difference-between-sensitivity-labels-and-teams-classification-labels"></a><span data-ttu-id="b425f-108">민감도 레이블과 분류 레이블의 Teams 차이점은 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="b425f-108">What's the difference between sensitivity labels and Teams classification labels?</span></span>

<span data-ttu-id="b425f-109">민감도 레이블은 분류 레이블과 다르며, Azure AD 그룹 분류라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="b425f-109">Sensitivity labels are different from classification labels, also known as Azure AD group classification.</span></span> <span data-ttu-id="b425f-110">분류 레이블은 그룹과 연결될 수 있지만 Microsoft 365 실제 정책이 없는 텍스트 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="b425f-110">Classification labels are text strings that can be associated with a Microsoft 365 group but don't have any actual policies associated with them.</span></span> <span data-ttu-id="b425f-111">분류 레이블을 메타데이터로 사용한 다음 내부 도구 및 스크립트와 같은 다른 메서드를 사용하여 정책을 적용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b425f-111">You use classification labels as metadata and then must use other methods such as internal tools and scripts, to enforce policies.</span></span>

<span data-ttu-id="b425f-112">민감도 레이블을 사용하는 이점은 해당 정책이 Microsoft 365 그룹 플랫폼, 규정 준수 센터 및 Teams 결합하여 종단 Teams 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b425f-112">The benefit of using sensitivity labels is that their policies are automatically enforced end-to-end through a combination of the Microsoft 365 Groups platform, the compliance center, and Teams services.</span></span> <span data-ttu-id="b425f-113">민감도 레이블은 조직의 중요한 데이터를 보호하고 내부 정책 또는 규정을 준수하도록 보장하기 위한 강력한 인프라 지원을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b425f-113">Sensitivity labels provide powerful infrastructure support for securing your organization's sensitive data and ensuring compliance with your internal policies or regulations.</span></span>

<span data-ttu-id="b425f-114">현재 분류 레이블을 사용하는 경우 민감도 레이블로 마이그레이션하는 방법에 대한 자세한 내용은 다음 설명서를 [참조하세요. 클래식 Azure AD 그룹 분류.](/microsoft-365/compliance/sensitivity-labels-teams-groups-sites#classic-azure-ad-group-classification)</span><span class="sxs-lookup"><span data-stu-id="b425f-114">If you currently use classification labels, see the following documentation for more information and instructions how to migrate them to sensitivity labels: [Classic Azure AD group classification](/microsoft-365/compliance/sensitivity-labels-teams-groups-sites#classic-azure-ad-group-classification).</span></span>

## <a name="example-scenarios-for-sensitivity-labels"></a><span data-ttu-id="b425f-115">민감도 레이블에 대한 예제 시나리오</span><span class="sxs-lookup"><span data-stu-id="b425f-115">Example scenarios for sensitivity labels</span></span>

<span data-ttu-id="b425f-116">조직에서 민감도 레이블을 사용하여 민감도 레이블을 사용하는 Teams 예제 시나리오:</span><span class="sxs-lookup"><span data-stu-id="b425f-116">Example scenarios for how you can use sensitivity labels with Teams in your organization:</span></span>

- [<span data-ttu-id="b425f-117">팀에 대한 개인 정보 수준 설정(공용 또는 비공개)</span><span class="sxs-lookup"><span data-stu-id="b425f-117">Set the privacy level (public or private) for teams</span></span>](#set-the-privacy-level-for-teams)
- [<span data-ttu-id="b425f-118">팀에 대한 게스트 액세스 제어</span><span class="sxs-lookup"><span data-stu-id="b425f-118">Control guest access to teams</span></span>](#control-guest-access-to-teams)

### <a name="set-the-privacy-level-for-teams"></a><span data-ttu-id="b425f-119">팀에 대한 개인 정보 수준 설정</span><span class="sxs-lookup"><span data-stu-id="b425f-119">Set the privacy level for teams</span></span>

<span data-ttu-id="b425f-120">팀을 만드는 동안 적용할 때 사용자가 특정 개인 정보(공개 또는 비공개) 설정을 사용하여 팀을 만들 수 있도록 하는 민감도 레이블을 만들고 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b425f-120">You can create and configure a sensitivity label that, when applied during team creation, allows users to create teams with a specific privacy (public or private) setting.</span></span>

<span data-ttu-id="b425f-121">예를 들어 개인으로 구성된 레이블 개인 정보 옵션이 있는 "기밀"이라는 민감도 레이블을 만들고 **게시합니다.**</span><span class="sxs-lookup"><span data-stu-id="b425f-121">For example, you create and publish a sensitivity label named "Confidential" that has the label privacy option configured as **Private**.</span></span> <span data-ttu-id="b425f-122">결과적으로 이 레이블로 만든 모든 팀은 개인 팀이 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b425f-122">As a result, any team that's created with this label must be a private team.</span></span> 

<span data-ttu-id="b425f-123">사용자가 새 팀을 만들고 기밀  레이블을 선택하면 사용자가 사용할 수 있는 유일한 개인 정보 옵션은 **비공개입니다.**</span><span class="sxs-lookup"><span data-stu-id="b425f-123">When a user creates a new team and selects the **Confidential** label, the only privacy option that's available to the user is **Private**.</span></span> <span data-ttu-id="b425f-124">공용 및 조직 전체와 같은 다른 개인 정보 보호 옵션은 사용자가 다음을 선택할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b425f-124">Other privacy options such as Public and Org-wide aren't available for the user to select:</span></span>

![기밀 민감도 레이블 스크린샷](media/sensitivity-labels-confidential-example.png)

<span data-ttu-id="b425f-126">마찬가지로 레이블 개인 정보 보호 옵션이 공용으로 구성된 "일반"이라는 민감도 레이블을 만들고 **게시합니다.**</span><span class="sxs-lookup"><span data-stu-id="b425f-126">Similarly, you create and publish a sensitivity label named "General" that has the label privacy option configured as **Public**.</span></span> <span data-ttu-id="b425f-127">사용자가 새 팀을 만들 때 이 레이블을 선택할 때만 공개 또는 전체 팀을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b425f-127">When a user creates a new team, they can only create public or org-wide teams when they select this label:</span></span>

![일반 민감도 레이블 스크린샷](media/sensitivity-labels-general-example.png)

<span data-ttu-id="b425f-129">팀을 만들면 팀의 채널 오른쪽 위 모서리에 민감도 레이블이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="b425f-129">When the team is created, the sensitivity label is visible in the upper-right corner of channels in the team.</span></span> 

> [!NOTE]
> <span data-ttu-id="b425f-130">"Confidential\Finance"같은 계층적 부모-자식 레이블을 사용하는 경우 상위 레이블만 채널 헤더에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="b425f-130">If you are using hierarchical parent-child labels such as "Confidential\Finance", then only the parent label will be shown in the channel header.</span></span>

![팀 채널의 민감도 레이블 스크린샷](media/sensitivity-labels-channel.png)

<span data-ttu-id="b425f-132">팀 소유자는 팀으로 이동하여 팀의 민감도 레이블 및 개인 정보 설정을 변경한 다음 팀 편집 을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="b425f-132">A team owner can change the sensitivity label and the privacy setting of the team at any time by going to the team, and then click **Edit team**.</span></span>

![팀 속성의 민감도 레이블 스크린샷](media/sensitivity-labels-edit-team.png)

### <a name="control-guest-access-to-teams"></a><span data-ttu-id="b425f-134">팀에 대한 게스트 액세스 제어</span><span class="sxs-lookup"><span data-stu-id="b425f-134">Control guest access to teams</span></span>

<span data-ttu-id="b425f-135">민감도 레이블을 사용하여 팀에 대한 게스트 액세스를 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b425f-135">You can use sensitivity labels to control guest access to your teams.</span></span> <span data-ttu-id="b425f-136">Teams 액세스를 허용하지 않는 레이블로 만든 사용자는 조직의 사용자만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b425f-136">Teams created with a label that doesn't allow guest access are only available to users in your organization.</span></span> <span data-ttu-id="b425f-137">조직 외부의 사람들은 팀에 추가할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b425f-137">People outside your organization can't be added to the team.</span></span>

## <a name="microsoft-teams-admin-center"></a><span data-ttu-id="b425f-138">Microsoft Teams 관리 센터</span><span class="sxs-lookup"><span data-stu-id="b425f-138">Microsoft Teams admin center</span></span>

<span data-ttu-id="b425f-139">관리 센터에서 팀을 만들거나 편집할 때 민감도 레이블을 적용할 Microsoft Teams 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b425f-139">You can apply sensitivity labels when you create or edit a team in the Microsoft Teams admin center.</span></span> 

<span data-ttu-id="b425f-140">민감도 레이블은 팀 속성 및 관리  센터의 팀  관리 페이지의 분류 Microsoft Teams 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="b425f-140">Sensitivity labels are also visible in team properties and in the **Classification** column on the **Manage teams** page of the Microsoft Teams admin center.</span></span>

## <a name="limitations"></a><span data-ttu-id="b425f-141">제한 사항</span><span class="sxs-lookup"><span data-stu-id="b425f-141">Limitations</span></span>

<span data-ttu-id="b425f-142">민감도 레이블을 사용하기 전에 Teams 제한 사항을 알고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b425f-142">Before you use sensitivity labels for Teams, be aware of the following limitations:</span></span>

- <span data-ttu-id="b425f-143">**하위 레이블에는 부모 레이블 이름이 표시되지 않습니다.**</span><span class="sxs-lookup"><span data-stu-id="b425f-143">**Parent label names aren't displayed for sublabels**</span></span>
    
    <span data-ttu-id="b425f-144">Teams 하위 레이블을 지원하지만 부모 레이블의 이름이 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b425f-144">Teams supports sublabels but doesn't display the name of the parent label.</span></span> <span data-ttu-id="b425f-145">예를 들어  기밀 \\ **모든 직원은** 모든 **직원으로 표시됩니다.**</span><span class="sxs-lookup"><span data-stu-id="b425f-145">For example, **Confidential** \\ **All Employees** displays as **All Employees**.</span></span>

- <span data-ttu-id="b425f-146">**민감도 레이블은 API, PowerShell cmdlet 및 Teams Graph 지원되지 않습니다.**</span><span class="sxs-lookup"><span data-stu-id="b425f-146">**Sensitivity labels aren't supported by Teams Graph APIs, PowerShell cmdlets, and templates**</span></span>
    
    <span data-ttu-id="b425f-147">사용자는 기본 API, PowerShell cmd Teams let 및 Teams Graph 통해 직접 팀을 만드는 동안 민감도 레이블을 지정할 Teams 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b425f-147">Users won't be able to specify sensitivity labels while creating teams directly through Teams Graph APIs, Teams PowerShell cmdlets, and Teams templates.</span></span> <span data-ttu-id="b425f-148">그러나 최신 그룹 Graph API 및 PowerShell cmdlet을 사용하면 레이블이 있는 그룹을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b425f-148">However Modern Groups Graph APIs and PowerShell cmdlets do allow creation of groups with labels.</span></span> <span data-ttu-id="b425f-149">따라서 사용자는 먼저 그룹 api 또는 PowerShell cmdlet을 사용하여 그룹 Graph 그룹을 만든 다음 이러한 그룹을 그룹으로 변환하여 Teams.</span><span class="sxs-lookup"><span data-stu-id="b425f-149">So users can first create Groups with labels using Groups Graph APIs or PowerShell cmdlets and then convert these Groups in to Teams.</span></span>

- <span data-ttu-id="b425f-150">**개인 채널에 대한 지원**</span><span class="sxs-lookup"><span data-stu-id="b425f-150">**Support for private channels**</span></span>
    
    <span data-ttu-id="b425f-151">팀에서 만든 개인 채널은 팀에 적용된 민감도 레이블을 상속합니다.</span><span class="sxs-lookup"><span data-stu-id="b425f-151">Private channels that are created in a team inherit the sensitivity label that was applied on a team.</span></span> <span data-ttu-id="b425f-152">동일한 레이블은 개인 채널에 대한 SharePoint 사이트 모음에 자동으로 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b425f-152">The same label is automatically applied on the SharePoint site collection for the private channel.</span></span>
    
    <span data-ttu-id="b425f-153">그러나 사용자가 개인 채널에 대한 SharePoint 사이트에서 민감도 레이블을 직접 변경하는 경우 해당 레이블 변경은 해당 Teams 반영되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b425f-153">However, if a user directly changes the sensitivity label on a SharePoint site for a private channel, that label change isn't reflected in the Teams client.</span></span> <span data-ttu-id="b425f-154">이 시나리오에서 사용자는 개인 채널 헤더에서 팀에 적용된 원래 민감도 레이블을 계속 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b425f-154">In this scenario, users continue to see the original sensitivity label applied on the team in the private channel header.</span></span>

## <a name="how-to-create-and-configure-sensitivity-labels-for-teams"></a><span data-ttu-id="b425f-155">사용자에 대한 민감도 레이블을 만들고 구성하는 Teams</span><span class="sxs-lookup"><span data-stu-id="b425f-155">How to create and configure sensitivity labels for Teams</span></span>

<span data-ttu-id="b425f-156">다음에 대한 민감도 레이블을 만들고 Microsoft 365 설명서의 지침을 Teams.</span><span class="sxs-lookup"><span data-stu-id="b425f-156">Use the instructions from the Microsoft 365 documentation to create and configure sensitivity labels for Teams:</span></span> 

- <span data-ttu-id="b425f-157">[민감도 레이블을](/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)사용하여 Microsoft Teams, 그룹 및 Microsoft 365 사이트의 콘텐츠를 SharePoint.</span><span class="sxs-lookup"><span data-stu-id="b425f-157">[Use sensitivity labels to protect content in Microsoft Teams, Microsoft 365 groups, and SharePoint sites](/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).</span></span>
