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
localization_priority: Normal
search.appverid: MET150
description: Microsoft 팀에서 우편물 종류 레이블을 정의 하 고 사용 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: 3a0c40a51653a525587a0662949a3fdd4e63faf4
ms.sourcegitcommit: 4a4ed872eff22663720296ae29c0e644286857f2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/15/2019
ms.locfileid: "38653599"
---
# <a name="sensitivity-labels-for-microsoft-teams"></a><span data-ttu-id="b8794-103">Microsoft 팀의 민감도 레이블</span><span class="sxs-lookup"><span data-stu-id="b8794-103">Sensitivity labels for Microsoft Teams</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="b8794-104">[우편물 종류 레이블을](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) 사용 하면 팀 관리자가 팀 내에서 공동 작업을 수행 하는 중요 한 조직 콘텐츠에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8794-104">[Sensitivity labels](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) allow Teams admins to regulate access to sensitive organizational content created during collaboration within teams.</span></span> <span data-ttu-id="b8794-105">[보안 & 준수 센터](https://docs.microsoft.com/microsoft-365/compliance/go-to-the-securitycompliance-center)에서 민감도 레이블 및 관련 정책을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8794-105">You can define sensitivity labels and their associated policies in the [Security & Compliance Center](https://docs.microsoft.com/microsoft-365/compliance/go-to-the-securitycompliance-center).</span></span> <span data-ttu-id="b8794-106">이러한 레이블과 정책은 조직의 팀에 자동으로 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8794-106">These labels and policies are automatically applied to teams in your organization.</span></span>  

## <a name="whats-the-difference-between-sensitivity-labels-and-teams-classification-labels"></a><span data-ttu-id="b8794-107">민감도 레이블과 팀 분류 레이블의 차이점은 무엇 인가요?</span><span class="sxs-lookup"><span data-stu-id="b8794-107">What's the difference between sensitivity labels and Teams classification labels?</span></span>

<span data-ttu-id="b8794-108">민감도 레이블은 PowerShell을 사용 하 여 만들어야 할 분류 레이블과 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="b8794-108">Sensitivity labels are different from classification labels that require you to create them using PowerShell.</span></span> <span data-ttu-id="b8794-109">분류 레이블은 그룹과 연결 될 수 있지만 관련 된 실제 정책이 없는 텍스트 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="b8794-109">Classification labels are text strings that can be associated with a group but don't have any actual policies associated with them.</span></span> <span data-ttu-id="b8794-110">분류 레이블을 메타 데이터로 사용 하 여 내부 도구 및 스크립트를 통해 정책을 수동으로 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8794-110">You use classification labels as metadata to manually enforce policies through internal tools and scripts.</span></span>

<span data-ttu-id="b8794-111">다른 한편, 민감도 레이블과 해당 정책은 그룹 플랫폼, 보안 & 준수 센터, 팀 서비스를 조합 하 여 자동으로 종단 간 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8794-111">On the other hand, sensitivity labels and their policies are automatically enforced end-to-end through a combination of the Groups platform, Security & Compliance Center, and Teams services.</span></span> <span data-ttu-id="b8794-112">민감도 레이블은 조직의 민감한 데이터를 보호 하기 위한 강력한 인프라 지원을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8794-112">Sensitivity labels provide powerful infrastructure support for securing your organization's sensitive data.</span></span>  

## <a name="create-and-publish-sensitivity-labels-for-teams"></a><span data-ttu-id="b8794-113">팀에 대 한 민감도 레이블 만들기 및 게시</span><span class="sxs-lookup"><span data-stu-id="b8794-113">Create and publish sensitivity labels for Teams</span></span>

<span data-ttu-id="b8794-114">팀의 민감도 레이블을 사용, 만들기, 게시 하는 방법에 대 한 자세한 내용은 [Microsoft 팀, Office 365 그룹 및 SharePoint 사이트에 민감도 레이블 사용](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b8794-114">For how to enable, create, and publish sensitivity labels for Teams, see [Use sensitivity labels with Microsoft Teams, Office 365 groups, and SharePoint sites](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).</span></span>

## <a name="using-sensitivity-labels-with-teams"></a><span data-ttu-id="b8794-115">팀과 우편물 종류 레이블 사용</span><span class="sxs-lookup"><span data-stu-id="b8794-115">Using sensitivity labels with Teams</span></span>

<span data-ttu-id="b8794-116">조직의 팀에서 민감도 레이블을 사용 하는 방법에 대 한 몇 가지 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b8794-116">Here are some example scenarios of how you can use sensitivity labels with Teams in your organization.</span></span>

### <a name="privacy-setting-of-teams"></a><span data-ttu-id="b8794-117">팀의 개인 정보 설정</span><span class="sxs-lookup"><span data-stu-id="b8794-117">Privacy setting of teams</span></span>

<span data-ttu-id="b8794-118">팀을 만드는 동안 적용 하면 사용자가 특정 개인 정보 (공개 또는 비공개) 설정을 사용 하 여 팀을 만들 수 있는 민감도 레이블을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8794-118">You can create a sensitivity label that, when applied during team creation, allows users to create teams with a specific privacy (public or private) setting.</span></span>

<span data-ttu-id="b8794-119">예를 들어 보안 & 준수 센터에 "기밀" 이라는 레이블을 만들고이 레이블을 사용 하 여 만든 모든 팀이 개인 팀 이어야 하도록 팀을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8794-119">For example, you create a label named “Confidential” in the Security & Compliance Center and you configure Teams so that any team that's created with this label must be a private team.</span></span> <span data-ttu-id="b8794-120">사용자가 새 팀을 만들고 **기밀** 레이블을 선택 하는 경우 사용자가 사용할 수 있는 개인 정보 옵션은 **비공개**입니다.</span><span class="sxs-lookup"><span data-stu-id="b8794-120">When a user creates a new team and selects the **Confidential** label, the only privacy option that's available to the user is **Private**.</span></span> <span data-ttu-id="b8794-121">공개 및 조직 전체와 같은 기타 개인 정보 옵션을 사용자에 게 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b8794-121">Other privacy options such as Public and Org-wide are disabled for the user.</span></span>

![비밀 민감도 레이블의 스크린샷](media/sensitivity-labels-confidential-example.png)

<span data-ttu-id="b8794-123">마찬가지로 사용자가 새 팀을 만들 때 **일반** 을 선택 하는 경우에는 공용 또는 조직 차원의 팀만 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8794-123">Similarly, if the user selects **General** when they create a new team, they can only create public or org-wide teams.</span></span>

![일반 민감도 레이블의 스크린샷](media/sensitivity-labels-general-example.png)

<span data-ttu-id="b8794-125">팀을 만들 때 우편물 종류 레이블은 팀의 채널 오른쪽 위 모서리에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8794-125">When the team is created, the sensitivity label is visible in the upper-right corner of channels in the team.</span></span>

![팀 채널의 우편물 종류 레이블 스크린샷](media/sensitivity-labels-channel.png)

<span data-ttu-id="b8794-127">팀 소유자는 팀으로 이동한 다음 **팀 편집**을 클릭 하 여 언제 든 지 팀의 민감도 레이블과 개인 정보 설정을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8794-127">A team owner can change the sensitivity label and the privacy setting of the team at any time by going to the team, and then clicking **Edit team**.</span></span>

![팀 채널의 우편물 종류 레이블 스크린샷](media/sensitivity-labels-edit-team.png)

### <a name="guest-access-to-teams"></a><span data-ttu-id="b8794-129">팀에 대 한 게스트 액세스</span><span class="sxs-lookup"><span data-stu-id="b8794-129">Guest access to teams</span></span>

<span data-ttu-id="b8794-130">특정 레이블을 사용 하 여 만든 팀에서 게스트 액세스를 허용 하는지 여부를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8794-130">You can specify whether a team created with a specific label allows guest access.</span></span> <span data-ttu-id="b8794-131">게스트 액세스를 허용 하지 않는 레이블을 사용 하 여 만든 팀은 조직의 사용자만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8794-131">Teams created with a label that doesn't allow guest access are only available to users in your organization.</span></span> <span data-ttu-id="b8794-132">조직 외부의 사용자를 팀에 추가할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b8794-132">People outside your organization can't be added to the team.</span></span>

## <a name="known-issues"></a><span data-ttu-id="b8794-133">알려진 문제</span><span class="sxs-lookup"><span data-stu-id="b8794-133">Known issues</span></span>

<span data-ttu-id="b8794-134">**Microsoft 팀 관리 센터의 민감도 레이블 지원**</span><span class="sxs-lookup"><span data-stu-id="b8794-134">**Support for sensitivity labels in the Microsoft Teams admin center**</span></span>

<span data-ttu-id="b8794-135">현재 Microsoft 팀 관리 센터에서는 우편물 종류 레이블이 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b8794-135">Currently, sensitivity labels are not supported in the Microsoft Teams admin center.</span></span> <span data-ttu-id="b8794-136">우편물 종류 레이블을 사용 하는 경우 팀을 만들거나 편집할 때 우편물 종류 레이블을 설정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b8794-136">If you use sensitivity labels, you won't be able to set sensitivity labels when you create or edit a team.</span></span> <span data-ttu-id="b8794-137">민감도 레이블은 팀 속성에도 표시 되지 않으며 Microsoft 팀 관리 센터의 **분류** 열에 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b8794-137">Sensitivity labels are also not visible in team properties and won't be visible in the **Classification** column in the Microsoft Teams admin center.</span></span>

<span data-ttu-id="b8794-138">**팀 그래프 Api, Powershell cmdlet 및 템플릿에 대 한 민감도 레이블 지원**</span><span class="sxs-lookup"><span data-stu-id="b8794-138">**Support for sensitivity labels in Teams Graph APIs, Powershell cmdlets and templates**</span></span>

<span data-ttu-id="b8794-139">현재 사용자는 Graph Api, Powershell cmdlet, 템플릿을 통해 직접 만든 팀에 민감도 레이블을 적용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b8794-139">Currently, users won't be able to apply sensitivity labels on teams that are created directly through Graph APIs, Powershell cmdlets, and templates.</span></span>

<span data-ttu-id="b8794-140">**개인 채널의 SharePoint 사이트 모음에서 우편물 종류 레이블을 직접 편집**</span><span class="sxs-lookup"><span data-stu-id="b8794-140">**Editing sensitivity labels directly on a SharePoint site collection for private channels**</span></span>

<span data-ttu-id="b8794-141">팀에서 만든 개인 채널은 팀에 적용 된 민감도 레이블을 상속 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8794-141">Private channels that are created in a team inherit the sensitivity label which was applied on a team.</span></span> <span data-ttu-id="b8794-142">또한 개인 채널의 SharePoint 사이트 모음에도 동일한 레이블이 자동으로 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8794-142">Furthermore, the same label is automatically applied on the SharePoint site collection for the private channel.</span></span>

<span data-ttu-id="b8794-143">사용자가 개인 채널의 SharePoint 사이트 모음에서 우편물 종류 레이블을 직접 업데이트 하는 경우 팀 클라이언트에서 해당 레이블이 업데이트 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b8794-143">If a user directly updates the sensitivity label on a SharePoint site collection for a private channel, that label isn't updated in the Teams client.</span></span> <span data-ttu-id="b8794-144">이 시나리오에서는 사용자가 개인 채널 헤더에서 팀에 적용 된 우편물 종류 레이블을 계속 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8794-144">In this scenario, users will continue to see the sensitivity label applied on a team in the private channel header.</span></span>

<span data-ttu-id="b8794-145">**팀 앱 외부의 민감도 레이블에 적용 된 변경 내용에 대 한 전파 시간**</span><span class="sxs-lookup"><span data-stu-id="b8794-145">**Propagation times for changes applied to sensitivity labels outside the Teams app**</span></span>

<span data-ttu-id="b8794-146">팀 앱 외부의 민감도 레이블에 대 한 변경 사항은 팀 앱에서 적용 하는 데 최대 24 시간까지 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8794-146">Changes made to sensitivity labels outside the Teams app can take up to 24 hours to reflect in the Teams app.</span></span> <span data-ttu-id="b8794-147">이는 테 넌 트의 레이블을 사용 하거나 사용 하지 않도록 변경한 내용, 레이블 이름, 설정, 정책의 변경에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8794-147">This applies to any changes made to enable or disable labels for a tenant, changes to label names, settings, and policies.</span></span>

<span data-ttu-id="b8794-148">또한 팀을 지 원하는 그룹 또는 SharePoint 사이트 모음에 직접 변경한 내용은 팀 앱에 전파 하는 데 최대 24 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8794-148">Additionally, any changes to a label made directly to a group or SharePoint site collection that backs the team can take up to 24 hours to propagate to the Teams app.</span></span>