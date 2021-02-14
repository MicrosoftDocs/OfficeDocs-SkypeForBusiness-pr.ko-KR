---
title: 보관 구성
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
- ms.lync.lscp.MonArchSettingMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9c2fd164-a9b8-40e6-a1c4-423a7fe34aba
description: 보관 구성을 사용하여 다음 옵션의 사용 및 비활성화를 포함하여 비즈니스용 Skype 서버 배포에 대한 보관 옵션을 제어합니다.
ms.openlocfilehash: 96a01579f43833017978fc6067b5a86f9e9951aa
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827008"
---
# <a name="archiving-configuration"></a><span data-ttu-id="f29dc-103">보관 구성</span><span class="sxs-lookup"><span data-stu-id="f29dc-103">Archiving Configuration</span></span>
 
<span data-ttu-id="f29dc-104">보관 구성을 사용하여 다음 옵션의 사용 및 비활성화를 포함하여 비즈니스용 Skype 서버 배포에 대한 보관 옵션을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="f29dc-104">You use Archiving configurations to control archiving options for your Skype for Business Server deployment, including enabling and disabling the following options:</span></span>
  
- <span data-ttu-id="f29dc-105">보관에 실패할 경우 메신저 대화 또는 회의 세션 차단</span><span class="sxs-lookup"><span data-stu-id="f29dc-105">Blocking of instant messaging (IM) or conferencing sessions if archiving fails</span></span>
    
- <span data-ttu-id="f29dc-106">Exchange 2013에 있는 사용자를 위한 Exchange 2013 저장소와의 통합</span><span class="sxs-lookup"><span data-stu-id="f29dc-106">Integration with Exchange 2013 storage, for users homed on Exchange 2013</span></span>
    
- <span data-ttu-id="f29dc-107">보관된 데이터 삭제</span><span class="sxs-lookup"><span data-stu-id="f29dc-107">Purging of archived data</span></span>
    
<span data-ttu-id="f29dc-108">보관 구성에는 전역 구성과 하나 이상의 사이트 및 풀 보관 구성(선택 사항)이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="f29dc-108">Archiving configurations include the global configuration and, optionally, one or more site and pool Archiving configurations:</span></span>
  
- <span data-ttu-id="f29dc-109">**전역 구성** 전역 구성은 모든 비즈니스용 Skype 서버 배포에서 기본적으로 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="f29dc-109">**Global configuration** The global configuration is created by default in all Skype for Business Server deployments.</span></span> <span data-ttu-id="f29dc-110">전역 구성을 편집할 수는 있지만 이 보관 구성을 삭제할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f29dc-110">You edit the global configuration, but you cannot delete this Archiving configuration.</span></span> <span data-ttu-id="f29dc-111">해당 구성을 삭제하려고 하면 모든 옵션이 기본값으로 다시 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="f29dc-111">If you try to delete it, all options are reset to the defaults.</span></span>
    
- <span data-ttu-id="f29dc-112">**사이트 구성(선택 사항)** 하나 이상의 사이트 보관 구성을 지정할 수 있습니다. 각 구성은 특정 사이트에 대한 보관 옵션을 제어하도록 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f29dc-112">**Site configuration (optional)** You can specify one or more site Archiving configurations, each of which you can configure to control archiving options for a specific site.</span></span> <span data-ttu-id="f29dc-113">사이트 구성은 보관 사이트 구성에 지정된 사이트에 한해 전역 구성을 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="f29dc-113">A site configuration overrides the global configuration, but only for the sites specified in the Archiving site configurations.</span></span> <span data-ttu-id="f29dc-114">사이트 구성은 편집하거나 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f29dc-114">You can edit or delete site configurations.</span></span>
    
- <span data-ttu-id="f29dc-115">**풀 구성(선택 사항)** 하나 이상의 풀 보관 구성을 지정하여 특정 풀에 대한 보관 옵션을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f29dc-115">**Pool configuration (optional)** You can specify one or more pool Archiving configuration, to control archiving options for a specific pool.</span></span> <span data-ttu-id="f29dc-116">풀 구성은 보관 풀 구성에 지정된 풀에 한해 전역 구성 및 사이트 구성을 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="f29dc-116">A pool configuration overrides the global configuration and site configuration, but only for the pools specified in Archiving pool configurations.</span></span> <span data-ttu-id="f29dc-117">풀 구성은 편집하거나 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f29dc-117">You can edit or delete pool configurations.</span></span>
    
> [!NOTE]
> <span data-ttu-id="f29dc-118">보관 구성은 비즈니스용 Skype 서버에 있는 사용자에게 적용하며, Exchange를 사용하여 Microsoft Exchange에 보관 데이터를 저장하는 경우 Exchange 2013에 있지만 Exchange 2013에 있는 사용자에 대해 약간 다르게 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="f29dc-118">Archiving configurations apply to users homed on Skype for Business Server and, if you use Exchange to store archiving data in Microsoft Exchange, to users homed on Exchange 2013 but are implemented slightly differently for users homed on Exchange 2013.</span></span> <span data-ttu-id="f29dc-119">다음 섹션에서 이러한 차이에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f29dc-119">The differences are described in the next section.</span></span> 
  
<span data-ttu-id="f29dc-p105">**보관 구성** 페이지에는 배포에 대해 구성된 각 보관 정책이 나열됩니다. 또한 정책 이름, 범위(글로벌/사이트/풀) 및 각 보관 구성에 대해 사용하도록 설정된 보관 옵션도 표시됩니다. **보관 구성** 페이지에서는 다음 옵션이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="f29dc-p105">The **Archiving Configuration** page lists each Archiving policy that is configured for your deployment. It also shows the policy name, scope (global, site, or pool), and which archiving options are enabled for each Archiving configuration. From the **Archiving Configuration** page, you have the following options:</span></span>
- <span data-ttu-id="f29dc-123">**신규** 다음과 같은 각 선택적 보관 구성을 하나 이상 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f29dc-123">**New** You can add one or more of each of the following optional Archiving configurations.</span></span>
    
  - <span data-ttu-id="f29dc-124">사이트 구성</span><span class="sxs-lookup"><span data-stu-id="f29dc-124">Site configuration</span></span>
    
  - <span data-ttu-id="f29dc-125">풀 구성</span><span class="sxs-lookup"><span data-stu-id="f29dc-125">Pool configuration</span></span>
    
- <span data-ttu-id="f29dc-126">**편집** 페이지에 나열된 보관 구성의 옵션을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f29dc-126">**Edit** You can change the options of any of the Archiving configurations listed on the page.</span></span> <span data-ttu-id="f29dc-127">이 옵션을 사용하여 다음을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f29dc-127">Using this option, you can do the following:</span></span>
    
  - <span data-ttu-id="f29dc-128">**세부 정보 표시** 이 옵션을 선택하면 선택한 보관 구성에 대한 보관 옵션을 변경할 수 있는 대화 상자가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="f29dc-128">**Show details** This option opens a dialog box in which you can change the archiving options for the selected Archiving configuration.</span></span> <span data-ttu-id="f29dc-129">한 번의 보관 구성에 대한 세부 정보만 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f29dc-129">You can only show details for one Archiving configuration at a time.</span></span>
    
  - <span data-ttu-id="f29dc-130">**모두 선택** 이 옵션은 목록의 모든 보관 구성을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f29dc-130">**Select all** This option selects all Archiving configurations in the list.</span></span>
    
  - <span data-ttu-id="f29dc-131">**삭제** 이 옵션은 선택한 모든 보관 구성을 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="f29dc-131">**Delete** This option deletes all selected Archiving configurations.</span></span>
    
- <span data-ttu-id="f29dc-132">**작업** 이 옵션을 사용하면 구성을 편집하는 대신 페이지에 나열된 모든 구성에서 IM 세션 또는 웹 회의 세션 보관을 빠르게 활성화 또는 비활성화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f29dc-132">**Action** You can use this option to quickly enable or disable archiving of IM sessions or web conferencing sessions in any configuration listed on the page, instead of editing the configuration.</span></span> <span data-ttu-id="f29dc-133">동작에서 사용할 수 있는 **옵션은** 보관 구성에 현재 지정된 옵션에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="f29dc-133">The options available under **Action** depend on what option is currently specified in the Archiving configuration.</span></span> <span data-ttu-id="f29dc-134">보관 구성에 현재 적용된 옵션을 제외한 모든 옵션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f29dc-134">All options are available, except the option currently in effect for the Archiving configuration.</span></span> <span data-ttu-id="f29dc-135">옵션은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f29dc-135">Options include the following:</span></span>
    
  - <span data-ttu-id="f29dc-136">**IM 세션 보관**</span><span class="sxs-lookup"><span data-stu-id="f29dc-136">**Archive IM sessions**</span></span>
    
  - <span data-ttu-id="f29dc-137">**메신저 대화 및 웹 회의 세션 보관**</span><span class="sxs-lookup"><span data-stu-id="f29dc-137">**Archive IM and web conferencing sessions**</span></span>
    
  - <span data-ttu-id="f29dc-138">**보관 사용 안 함**</span><span class="sxs-lookup"><span data-stu-id="f29dc-138">**Disable archiving**</span></span>
    
- <span data-ttu-id="f29dc-139">**새로 고침** 보관 구성  페이지를 새로 고쳐 모든 보관 구성의 옵션 상태를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f29dc-139">**Refresh** You can refresh the **Archiving Configuration** page to verify the status of the options of all Archiving configurations.</span></span>
    
<span data-ttu-id="f29dc-140">Exchange 통합을 비롯한 보관 기능에 대한 자세한 내용은 비즈니스용 Skype 서버 [2015의](../../plan-your-deployment/archiving/archiving.md)보관 계획, 비즈니스용 Skype 서버 [2015용](../../deploy/deploy-archiving/deploy-archiving.md)보관 배포 및 비즈니스용 Skype 서버 [2015의](../../manage/archiving/archiving.md)보관 관리를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f29dc-140">For details about the Archiving feature and capabilities, including Exchange integration, see [Plan for archiving in Skype for Business Server 2015](../../plan-your-deployment/archiving/archiving.md), [Deploy archiving for Skype for Business Server 2015](../../deploy/deploy-archiving/deploy-archiving.md), and [Manage archiving in Skype for Business Server 2015](../../manage/archiving/archiving.md).</span></span>

