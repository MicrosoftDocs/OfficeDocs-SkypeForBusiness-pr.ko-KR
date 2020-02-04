---
title: 보관 정책
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.lscp.MonArchPolicyMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9b69f1fa-8f3b-450e-aa89-91fd462f198d
ROBOTS: NOINDEX, NOFOLLOW
description: 보관 정책을 사용 하 여 비즈니스용 Skype 서버에 속한 사용자의 보관을 사용 하도록 설정 하거나 해제 합니다. 각 보관 정책에서 다음 중 하나 또는 둘 다에 대해 보관을 사용하거나 사용하지 않도록 설정할 수 있습니다.
ms.openlocfilehash: 63d1001a972b185fd8e36596798bc23e36a6ca3a
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41704793"
---
# <a name="archiving-policy"></a><span data-ttu-id="5e66f-104">보관 정책</span><span class="sxs-lookup"><span data-stu-id="5e66f-104">Archiving Policy</span></span>
 
<span data-ttu-id="5e66f-105">보관 정책을 사용 하 여 비즈니스용 Skype 서버에 속한 사용자의 보관을 사용 하도록 설정 하거나 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e66f-105">You use Archiving policies to enable and disable archiving for users homed on Skype for Business Server.</span></span> <span data-ttu-id="5e66f-106">각 보관 정책에서 다음 중 하나 또는 둘 다에 대해 보관을 사용하거나 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e66f-106">In each Archiving policy, you can enable or disable archiving for either or both of the following:</span></span>
  
- <span data-ttu-id="5e66f-107">내부 통신</span><span class="sxs-lookup"><span data-stu-id="5e66f-107">Internal communications</span></span>
    
- <span data-ttu-id="5e66f-108">외부 통신(내부 네트워크 외부의 사용자를 한 명 이상 포함하는 통신)</span><span class="sxs-lookup"><span data-stu-id="5e66f-108">External communications (communications that include at least one user outside your internal network)</span></span>
    
<span data-ttu-id="5e66f-109">보관 정책에는 전역 정책과 하나 이상의 사이트 및 사용자 보관 정책(선택 사항)이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="5e66f-109">Archiving policies include the global policy, and, optionally, one or more site and user Archiving policies:</span></span>
  
- <span data-ttu-id="5e66f-110">**글로벌 정책** 전역 정책은 모든 배포에 기본적으로 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="5e66f-110">**Global policy** The global policy is created by default in all deployments.</span></span> <span data-ttu-id="5e66f-111">전역 정책을 편집할 수는 있지만 이 정책을 삭제할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5e66f-111">You can edit the global policy, but you cannot delete this policy.</span></span> <span data-ttu-id="5e66f-112">정책을 삭제하려고 하면 모든 옵션이 기본값으로 다시 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="5e66f-112">If you try to delete it, all options are reset to the defaults.</span></span>
    
- <span data-ttu-id="5e66f-113">**사이트 정책 (선택 사항)** 단일 사이트에 대 한 내부 또는 외부 통신을 사용 하도록 설정 하 고 보관 하지 않도록 구성할 수 있는 하나 이상의 사이트 보관 정책을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e66f-113">**Site policy (optional)** You can specify one or more site Archiving policies, each of which you can configure to enable and disable archiving of internal or external communications for a single site.</span></span> <span data-ttu-id="5e66f-114">사이트 정책은 보관 사이트 정책에 지정된 사이트에 한해 전역 정책에 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="5e66f-114">A site policy overrides the global policy, but only for the sites specified in your Archiving site policies.</span></span> <span data-ttu-id="5e66f-115">사이트 정책은 편집하거나 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e66f-115">You can edit or delete site policies.</span></span>
    
- <span data-ttu-id="5e66f-116">**사용자 정책 (선택 사항)** 특정 사용자 또는 사용자 그룹에 대해 내부 또는 외부 통신을 사용 하도록 설정 하 고 보관 하지 않도록 구성할 수 있는 하나 이상의 사용자 보관 정책을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e66f-116">**User policy (optional)** You can specify one or more user Archiving policies, each of which you can configure to enable and disable archiving of internal or external communications for a specific user or user group.</span></span> <span data-ttu-id="5e66f-117">사용자 정책은 사용자 수준 보관 정책을 할당하는 사용자 및 사용자 그룹에 한해 전역 정책 및 사이트 정책에 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="5e66f-117">A user policy overrides the global policy and site policies, but only for the users and user groups to whom you assign user-level Archiving policies.</span></span> <span data-ttu-id="5e66f-118">사용자 정책은 편집하거나 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e66f-118">You can edit or delete user policies.</span></span>
    
> [!NOTE]
> <span data-ttu-id="5e66f-119">보관 정책은 비즈니스용 Skype Server에 속한 사용자 에게만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5e66f-119">Archiving policies apply only to users homed on Skype for Business Server.</span></span> <span data-ttu-id="5e66f-120">Exchange 통합을 사용 하 여 Microsoft Exchange에 보관 데이터를 저장 하는 경우 exchange 정책은 exchange에 있는 사용자의 보관을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e66f-120">If you use Exchange integration to store archiving data in Microsoft Exchange, then Exchange policies control archiving for users homed on Exchange.</span></span> <span data-ttu-id="5e66f-121">이러한 사용자에 대해 보관을 사용 하도록 설정 하려면 사용자의 사서함이 원본 위치 유지에 배치 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e66f-121">To enable archiving for those users, the user's mailbox must be placed on In-Place Hold.</span></span> 
  
<span data-ttu-id="5e66f-p107">**보관 정책** 페이지에는 배포에 대해 구성된 각 보관 정책이 나열됩니다. 또한 정책 이름, 범위(전역/사이트/사용자) 및 각 보관 정책에 대해 사용하도록 설정된 보관 옵션도 표시됩니다. **보관 정책** 페이지에서는 다음 옵션이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="5e66f-p107">The **Archiving Policy** page lists each Archiving policy that is configured for your deployment. It also shows the policy name, scope (global, site, or user), and which archiving options are enabled for each Archiving policy. From the **Archiving Policy** page, you have the following options:</span></span>
- <span data-ttu-id="5e66f-125">**새로운** 다음 선택적 보관 정책 각각을 하나 이상 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e66f-125">**New** You can add one or more of each of the following optional Archiving policies:</span></span>
    
  - <span data-ttu-id="5e66f-126">사이트 정책</span><span class="sxs-lookup"><span data-stu-id="5e66f-126">Site policy</span></span>
    
  - <span data-ttu-id="5e66f-127">사용자 정책</span><span class="sxs-lookup"><span data-stu-id="5e66f-127">User policy</span></span>
    
- <span data-ttu-id="5e66f-128">**편집** 페이지에 나열 된 보관 정책의 옵션을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e66f-128">**Edit** You can change the options of any of the Archiving policies listed on the page.</span></span> <span data-ttu-id="5e66f-129">이 옵션을 사용 하 여 다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e66f-129">Using this option, you can do the following:</span></span>
    
  - <span data-ttu-id="5e66f-130">**자세한 정보 표시** 이 옵션을 선택하면 보관 정책에 대한 보관 옵션을 변경할 수 있는 대화 상자가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="5e66f-130">**Show details** This option opens a dialog box in which you can change the archiving options for an Archiving policy.</span></span>
    
  - <span data-ttu-id="5e66f-131">**모두 선택** 이 옵션을 선택하면 목록의 모든 보관 정책이 선택됩니다.</span><span class="sxs-lookup"><span data-stu-id="5e66f-131">**Select all** This option selects all Archiving policies in the list.</span></span>
    
  - <span data-ttu-id="5e66f-132">**삭제** 이 옵션을 선택하면 선택되어 있는 모든 보관 정책이 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="5e66f-132">**Delete** This option deletes all selected Archiving policies.</span></span>
    
- <span data-ttu-id="5e66f-133">**작업** 이 옵션을 사용 하 여 정책을 편집 하는 대신 페이지에 나열 된 모든 정책에서 내부 또는 외부 통신의 보관을 빠르게 사용 하거나 사용 하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e66f-133">**Action** You can use this option to quickly enable or disable archiving of internal or external communications in any policy listed on the page, instead of editing the policy.</span></span> <span data-ttu-id="5e66f-134">**작업** 에서 사용할 수 있는 옵션은 보관 정책에 현재 지정 되어 있는 옵션에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="5e66f-134">The options available under **Action** depend on what option is currently specified in the Archiving policy.</span></span> <span data-ttu-id="5e66f-135">현재는 보관 정책에 적용 되는 옵션을 제외한 모든 옵션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e66f-135">All options are available, except the option currently in effect for the Archiving policy.</span></span> <span data-ttu-id="5e66f-136">옵션에는 다음이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5e66f-136">Options include the following:</span></span>
    
  - <span data-ttu-id="5e66f-137">**내부 통신 보관 사용**</span><span class="sxs-lookup"><span data-stu-id="5e66f-137">**Enable Archiving of internal communications**</span></span>
    
  - <span data-ttu-id="5e66f-138">**내부 통신 보관 사용 안 함**</span><span class="sxs-lookup"><span data-stu-id="5e66f-138">**Disable Archiving of internal communications**</span></span>
    
  - <span data-ttu-id="5e66f-139">**외부 통신 보관 사용**</span><span class="sxs-lookup"><span data-stu-id="5e66f-139">**Enable Archiving of external communications**</span></span>
    
  - <span data-ttu-id="5e66f-140">**외부 통신 보관 사용 안 함**</span><span class="sxs-lookup"><span data-stu-id="5e66f-140">**Disable Archiving of external communications**</span></span>
    
- <span data-ttu-id="5e66f-141">**새로 고침** **보관 정책** 페이지를 새로 고쳐 모든 보관 정책 옵션의 상태를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e66f-141">**Refresh** You can refresh the **Archiving Policy** page to verify the status of the options of all Archiving policies.</span></span>
    
<span data-ttu-id="5e66f-142">Exchange 통합을 포함 하 여 보관 기능 및 기능에 대 한 자세한 내용은 비즈니스용 [Skype 서버에서 보관 계획](../../../plan-your-deployment/archiving/archiving.md), 비즈니스용 [skype server 용 보관 배포](../../../deploy/deploy-archiving/deploy-archiving.md)및 비즈니스용 [skype 서버에서 보관 관리](../../../manage/archiving/archiving.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5e66f-142">For details about the Archiving feature and capabilities, including Exchange integration, see [Plan for archiving in Skype for Business Server](../../../plan-your-deployment/archiving/archiving.md), [Deploy archiving for Skype for Business Server](../../../deploy/deploy-archiving/deploy-archiving.md), and [Manage archiving in Skype for Business Server](../../../manage/archiving/archiving.md).</span></span>

