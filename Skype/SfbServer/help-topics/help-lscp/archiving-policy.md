---
title: 보관 정책
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.MonArchPolicyMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9b69f1fa-8f3b-450e-aa89-91fd462f198d
description: 보관 정책을 사용하여 비즈니스용 Skype 서버에 있는 사용자에 대해 보관을 사용하도록 설정하고 사용하지 않도록 설정할 수 있습니다. 각 보관 정책에서 다음 중 하나 또는 둘 다에 대해 보관을 사용하거나 사용하지 않도록 설정할 수 있습니다.
ms.openlocfilehash: 19bc0612208e719b7a963bf4c7f0dc6a9cc69537
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826948"
---
# <a name="archiving-policy"></a><span data-ttu-id="acf0e-104">보관 정책</span><span class="sxs-lookup"><span data-stu-id="acf0e-104">Archiving Policy</span></span>
 
<span data-ttu-id="acf0e-105">보관 정책을 사용하여 비즈니스용 Skype 서버에 있는 사용자에 대해 보관을 사용하도록 설정하고 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="acf0e-105">You use Archiving policies to enable and disable archiving for users homed on Skype for Business Server.</span></span> <span data-ttu-id="acf0e-106">각 보관 정책에서 다음 중 하나 또는 둘 다에 대해 보관을 사용하거나 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="acf0e-106">In each Archiving policy, you can enable or disable archiving for either or both of the following:</span></span>
  
- <span data-ttu-id="acf0e-107">내부 통신</span><span class="sxs-lookup"><span data-stu-id="acf0e-107">Internal communications</span></span>
    
- <span data-ttu-id="acf0e-108">외부 통신(내부 네트워크 외부의 사용자를 한 명 이상 포함하는 통신)</span><span class="sxs-lookup"><span data-stu-id="acf0e-108">External communications (communications that include at least one user outside your internal network)</span></span>
    
<span data-ttu-id="acf0e-109">보관 정책에는 글로벌 정책과 하나 이상의 사이트 및 사용자 보관 정책(선택 사항)이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="acf0e-109">Archiving policies include the global policy, and, optionally, one or more site and user Archiving policies:</span></span>
  
- <span data-ttu-id="acf0e-110">**글로벌 정책** 전역 정책은 모든 배포에서 기본적으로 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="acf0e-110">**Global policy** The global policy is created by default in all deployments.</span></span> <span data-ttu-id="acf0e-111">글로벌 정책을 편집할 수는 있지만 이 정책을 삭제할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="acf0e-111">You can edit the global policy, but you cannot delete this policy.</span></span> <span data-ttu-id="acf0e-112">해당 정책을 삭제하려고 하면 모든 옵션이 기본값으로 다시 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="acf0e-112">If you try to delete it, all options are reset to the defaults.</span></span>
    
- <span data-ttu-id="acf0e-113">**사이트 정책(선택 사항)** 하나 이상의 사이트 보관 정책을 지정할 수 있으며, 각 정책은 단일 사이트에 대한 내부 또는 외부 통신 보관을 사용하도록 설정하고 사용하지 않도록 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="acf0e-113">**Site policy (optional)** You can specify one or more site Archiving policies, each of which you can configure to enable and disable archiving of internal or external communications for a single site.</span></span> <span data-ttu-id="acf0e-114">사이트 정책은 보관 사이트 정책에 지정된 사이트에 한해 글로벌 정책을 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="acf0e-114">A site policy overrides the global policy, but only for the sites specified in your Archiving site policies.</span></span> <span data-ttu-id="acf0e-115">사이트 정책은 편집하거나 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="acf0e-115">You can edit or delete site policies.</span></span>
    
- <span data-ttu-id="acf0e-116">**사용자 정책(선택 사항)** 하나 이상의 사용자 보관 정책을 지정할 수 있으며, 각 정책은 특정 사용자 또는 사용자 그룹에 대한 내부 또는 외부 통신 보관을 사용하도록 설정하고 사용하지 않도록 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="acf0e-116">**User policy (optional)** You can specify one or more user Archiving policies, each of which you can configure to enable and disable archiving of internal or external communications for a specific user or user group.</span></span> <span data-ttu-id="acf0e-117">사용자 정책은 사용자 수준 보관 정책을 할당하는 사용자 및 사용자 그룹에 한해 글로벌 정책 및 사이트 정책을 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="acf0e-117">A user policy overrides the global policy and site policies, but only for the users and user groups to whom you assign user-level Archiving policies.</span></span> <span data-ttu-id="acf0e-118">사용자 정책은 편집하거나 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="acf0e-118">You can edit or delete user policies.</span></span>
    
> [!NOTE]
> <span data-ttu-id="acf0e-119">보관 정책은 비즈니스용 Skype 서버에 있는 사용자에게만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="acf0e-119">Archiving policies apply only to users homed on Skype for Business Server.</span></span> <span data-ttu-id="acf0e-120">Exchange 통합을 사용하여 Microsoft Exchange에 보관 데이터를 저장하는 경우 Exchange 2013 정책은 Exchange 2013에 있는 사용자의 보관을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="acf0e-120">If you use Exchange integration to store archiving data in Microsoft Exchange, then Exchange 2013 policies control archiving for users homed on Exchange 2013.</span></span> <span data-ttu-id="acf0e-121">이러한 사용자에 대해 보관을 사용하도록 설정하려면 사용자의 사서함이 보류된 In-Place 합니다.</span><span class="sxs-lookup"><span data-stu-id="acf0e-121">To enable archiving for those users, the user's mailbox must be placed on In-Place Hold.</span></span> 
  
<span data-ttu-id="acf0e-p107">**보관 정책** 페이지에는 배포에 대해 구성된 각 보관 정책이 나열됩니다. 또한 정책 이름, 범위(글로벌/사이트/사용자) 및 각 보관 정책에 대해 사용하도록 설정된 보관 옵션도 표시됩니다. **보관 정책** 페이지에서는 다음 옵션이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="acf0e-p107">The **Archiving Policy** page lists each Archiving policy that is configured for your deployment. It also shows the policy name, scope (global, site, or user), and which archiving options are enabled for each Archiving policy. From the **Archiving Policy** page, you have the following options:</span></span>
- <span data-ttu-id="acf0e-125">**신규** 다음과 같은 각 선택적 보관 정책을 하나 이상 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="acf0e-125">**New** You can add one or more of each of the following optional Archiving policies:</span></span>
    
  - <span data-ttu-id="acf0e-126">사이트 정책</span><span class="sxs-lookup"><span data-stu-id="acf0e-126">Site policy</span></span>
    
  - <span data-ttu-id="acf0e-127">사용자 정책</span><span class="sxs-lookup"><span data-stu-id="acf0e-127">User policy</span></span>
    
- <span data-ttu-id="acf0e-128">**편집** 페이지에 나열된 보관 정책의 옵션을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="acf0e-128">**Edit** You can change the options of any of the Archiving policies listed on the page.</span></span> <span data-ttu-id="acf0e-129">이 옵션을 사용하여 다음을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="acf0e-129">Using this option, you can do the following:</span></span>
    
  - <span data-ttu-id="acf0e-130">**자세한 정보 표시**   이 옵션을 선택하면 보관 정책에 대한 보관 옵션을 변경할 수 있는 대화 상자가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="acf0e-130">**Show details** This option opens a dialog box in which you can change the archiving options for an Archiving policy.</span></span>
    
  - <span data-ttu-id="acf0e-131">**모두 선택** 이 옵션을 선택하면 목록의 모든 보관 정책이 선택됩니다.</span><span class="sxs-lookup"><span data-stu-id="acf0e-131">**Select all** This option selects all Archiving policies in the list.</span></span>
    
  - <span data-ttu-id="acf0e-132">**삭제** 이 옵션을 선택하면 선택되어 있는 모든 보관 정책이 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="acf0e-132">**Delete** This option deletes all selected Archiving policies.</span></span>
    
- <span data-ttu-id="acf0e-133">**작업** 이 옵션을 사용하면 정책을 편집하는 대신 페이지에 나열된 모든 정책에서 내부 또는 외부 통신 보관을 빠르게 활성화 또는 비활성화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="acf0e-133">**Action** You can use this option to quickly enable or disable archiving of internal or external communications in any policy listed on the page, instead of editing the policy.</span></span> <span data-ttu-id="acf0e-134">작업에서 사용할 수 있는 **옵션은** 보관 정책에 현재 지정된 옵션에 따라 달라 습니다.</span><span class="sxs-lookup"><span data-stu-id="acf0e-134">The options available under **Action** depend on what option is currently specified in the Archiving policy.</span></span> <span data-ttu-id="acf0e-135">보관 정책에 현재 적용된 옵션을 제외한 모든 옵션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="acf0e-135">All options are available, except the option currently in effect for the Archiving policy.</span></span> <span data-ttu-id="acf0e-136">옵션은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="acf0e-136">Options include the following:</span></span>
    
  - <span data-ttu-id="acf0e-137">**내부 통신 보관 사용**</span><span class="sxs-lookup"><span data-stu-id="acf0e-137">**Enable Archiving of internal communications**</span></span>
    
  - <span data-ttu-id="acf0e-138">**내부 통신 보관 사용 안 함**</span><span class="sxs-lookup"><span data-stu-id="acf0e-138">**Disable Archiving of internal communications**</span></span>
    
  - <span data-ttu-id="acf0e-139">**외부 통신 보관 사용**</span><span class="sxs-lookup"><span data-stu-id="acf0e-139">**Enable Archiving of external communications**</span></span>
    
  - <span data-ttu-id="acf0e-140">**외부 통신 보관 사용 안 함**</span><span class="sxs-lookup"><span data-stu-id="acf0e-140">**Disable Archiving of external communications**</span></span>
    
- <span data-ttu-id="acf0e-141">**새로 고침** 보관 정책  페이지를 새로 고쳐 모든 보관 정책의 옵션 상태를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="acf0e-141">**Refresh** You can refresh the **Archiving Policy** page to verify the status of the options of all Archiving policies.</span></span>
    
<span data-ttu-id="acf0e-142">Exchange 통합을 비롯한 보관 기능에 대한 자세한 내용은 비즈니스용 Skype 서버 [2015의](../../plan-your-deployment/archiving/archiving.md)보관 계획, 비즈니스용 Skype 서버 [2015용](../../deploy/deploy-archiving/deploy-archiving.md)보관 배포 및 비즈니스용 Skype 서버 [2015의](../../manage/archiving/archiving.md)보관 관리를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="acf0e-142">For details about the Archiving feature and capabilities, including Exchange integration, see [Plan for archiving in Skype for Business Server 2015](../../plan-your-deployment/archiving/archiving.md), [Deploy archiving for Skype for Business Server 2015](../../deploy/deploy-archiving/deploy-archiving.md), and [Manage archiving in Skype for Business Server 2015](../../manage/archiving/archiving.md).</span></span>

