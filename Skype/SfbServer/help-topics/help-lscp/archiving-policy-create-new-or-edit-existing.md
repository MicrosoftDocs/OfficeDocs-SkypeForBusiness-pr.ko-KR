---
title: 보관 정책 새로 만들기 또는 기존 데이터 편집
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
- ms.lync.lscp.MonArchPolicyEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a4f948e7-e8f6-449a-8907-f61c5b143c05
description: 보관 정책을 사용하여 비즈니스용 Skype 서버에 있는 사용자에 대한 배포의 내부 및 외부 통신 보관을 제어합니다. 보관 정책에는 글로벌 정책과 하나 이상의 사이트 및 사용자 정책(선택 사항)이 포함됩니다.
ms.openlocfilehash: 9c852c592776f9e529c11dd46272715af52e8111
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826968"
---
# <a name="archiving-policy-create-new-or-edit-existing"></a><span data-ttu-id="13e6a-104">보관 정책: 새로 만들기 또는 기존 항목 편집</span><span class="sxs-lookup"><span data-stu-id="13e6a-104">Archiving Policy: Create New or Edit Existing</span></span>
 
<span data-ttu-id="13e6a-105">보관 정책을 사용하여 비즈니스용 Skype 서버에 있는 사용자에 대한 배포의 내부 및 외부 통신 보관을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="13e6a-105">You use Archiving policies to control archiving of internal and external communications in your deployment for users who are homed on Skype for Business Server.</span></span> <span data-ttu-id="13e6a-106">보관 정책에는 글로벌 정책과 하나 이상의 사이트 및 사용자 정책(선택 사항)이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="13e6a-106">Archiving policies include the global policy, and, optionally, one or more site and user policies:</span></span>
  
- <span data-ttu-id="13e6a-107">**글로벌 정책** 글로벌 정책은 모든 비즈니스용 Skype 서버 배포에서 기본적으로 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="13e6a-107">**Global policy** The global policy is created by default in all Skype for Business Server deployments.</span></span> <span data-ttu-id="13e6a-108">글로벌 정책을 편집할 수는 있지만 이 정책을 삭제할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="13e6a-108">You can edit the global policy, but you cannot delete this policy.</span></span> <span data-ttu-id="13e6a-109">해당 정책을 삭제하려고 하면 모든 옵션이 기본값으로 다시 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="13e6a-109">If you try to delete it, all options are reset to the defaults.</span></span>
    
- <span data-ttu-id="13e6a-110">**사이트 정책(선택 사항)** 하나 이상의 사이트 보관 정책을 지정할 수 있으며, 각 정책은 특정 사이트에 대한 내부 또는 외부 통신 보관을 사용하도록 설정하고 사용하지 않도록 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13e6a-110">**Site policies (optional)** You can specify one or more site Archiving policies, each of which you can configure to enable and disable archiving of internal or external communications for a specific site.</span></span> <span data-ttu-id="13e6a-111">사이트 정책은 보관 정책에 지정된 사이트에 한해 글로벌 정책을 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="13e6a-111">A site policy overrides the global policy, but only for the sites specified in Archiving policies.</span></span> <span data-ttu-id="13e6a-112">사이트 정책은 편집하거나 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13e6a-112">You can edit or delete site policies.</span></span>
    
- <span data-ttu-id="13e6a-113">**사용자 정책(선택 사항)** 하나 이상의 사용자 보관 정책을 지정할 수 있으며, 각 정책은 특정 사용자에 대한 내부 또는 외부 통신에 대해 보관을 사용하도록 설정하고 사용하지 않도록 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13e6a-113">**User policies (optional)** You can specify one or more user Archiving policies, each of which you can configure to enable and disable archiving for internal or external communications for a specific user.</span></span> <span data-ttu-id="13e6a-114">사용자 정책은 사용자 정책을 할당하는 사용자에 한해 글로벌 정책 및 사이트 정책을 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="13e6a-114">A user policy overrides the global policy and site policies, but only for the user(s) to whom you assign a user policy.</span></span> <span data-ttu-id="13e6a-115">사용자 정책은 편집하거나 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13e6a-115">You can edit or delete user policies.</span></span>
    
> [!NOTE]
> <span data-ttu-id="13e6a-116">Exchange 통합을 사용하여 Microsoft Exchange에 보관 데이터를 저장하는 경우 Exchange 2013 정책은 Exchange 2013에 있는 사용자의 보관을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="13e6a-116">If you use Exchange integration to store archiving data in Microsoft Exchange, then Exchange 2013 policies control archiving for users homed on Exchange 2013.</span></span> <span data-ttu-id="13e6a-117">이러한 사용자에 대해 보관을 사용하도록 설정하려면 사용자의 사서함이 보류된 In-Place 합니다.</span><span class="sxs-lookup"><span data-stu-id="13e6a-117">To enable archiving for those users, the user's mailbox must be placed on In-Place Hold.</span></span> 
  
<span data-ttu-id="13e6a-118">새 보관 정책 또는 기존 보관 정책의 설정을 구성하려면 다음 옵션을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="13e6a-118">To configure the settings for a new or existing Archiving policy, you specify the following options:</span></span>
- <span data-ttu-id="13e6a-119">**이름** 각 보관 정책에는 이름이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="13e6a-119">**Name** Each Archiving policy requires a name.</span></span> <span data-ttu-id="13e6a-120">이름은 추가 또는 편집하는 정책 유형에 따라 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="13e6a-120">The name is determined by the type of policy that you are adding or editing:</span></span>
    
  - <span data-ttu-id="13e6a-121">**글로벌 정책** 기본 이름은 Global입니다.</span><span class="sxs-lookup"><span data-stu-id="13e6a-121">**Global policy** The default name is Global.</span></span> <span data-ttu-id="13e6a-122">보다 설명적인 이름으로 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13e6a-122">You can change it to a more descriptive name.</span></span> <span data-ttu-id="13e6a-123">예를 들면 'Contoso 북미 조직'과 같은 이름을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13e6a-123">For example, Contoso North American Organization.</span></span>
    
  - <span data-ttu-id="13e6a-124">**사이트 정책** 이 대화 상자에 나열된 사이트에는 배포에서 사용 가능한 모든 사이트가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="13e6a-124">**Site policy** The sites listed in this dialog box include all available sites in your deployment.</span></span> <span data-ttu-id="13e6a-125">사이트 하나를 클릭하여 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="13e6a-125">Click a single site to select it.</span></span> <span data-ttu-id="13e6a-126">예를 들면 'Redmond 데이터 센터'와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="13e6a-126">For example, Redmond Data Center.</span></span>
    
  - <span data-ttu-id="13e6a-127">**사용자 정책** 특정 사용자의 이름이나 조직에 있는 사용자 그룹 또는 팀의 이름과 같은 적절한 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="13e6a-127">**User policy** Specify an appropriate name, such as the name of a specific user or the name of a user group or team in your organization.</span></span> <span data-ttu-id="13e6a-128">예를 들어 '법률 부서'와 같이 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13e6a-128">For example, Legal Department.</span></span>
    
- <span data-ttu-id="13e6a-129">**설명** 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="13e6a-129">**Description** This is optional.</span></span> <span data-ttu-id="13e6a-130">정책의 범위 또는 사용과 같은 추가 세부 정보를 제공하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13e6a-130">Use it to provide additional details, such as the scope or use of the policy.</span></span> <span data-ttu-id="13e6a-131">예를 들어 다른 사이트의 법률 부서와 조율합니다.</span><span class="sxs-lookup"><span data-stu-id="13e6a-131">For example, Coordinate with Legal Departments of Other Sites.</span></span>
    
- <span data-ttu-id="13e6a-132">**내부 통신 보관** 내부 네트워크에서 통신 보관을 사용하도록 설정하려면 이 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="13e6a-132">**Archive internal communications** Select this check box to enable archiving of communications on your internal network.</span></span> <span data-ttu-id="13e6a-133">기본적으로 이 정책은 모든 정책에서 사용하도록 설정되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="13e6a-133">By default, this is not enabled in any policy.</span></span>
    
- <span data-ttu-id="13e6a-134">**외부 통신 보관** 원격 사용자(익명 및 PIC 설정 사용자 포함) 및 페더링 파트너와 같은 외부 사용자를 포함한 통신 보관을 사용하도록 설정하려면 이 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="13e6a-134">**Archive external communications** Select this check box to enable archiving of communications that include external users, such as remote users, (including anonymous and PIC-setting users), and federated partners.</span></span> <span data-ttu-id="13e6a-135">기본적으로 이 설정은 모든 정책에서 사용하도록 설정되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="13e6a-135">By default, this is not enabled in any policy.</span></span>
    
<span data-ttu-id="13e6a-136">Exchange 통합을 비롯한 보관 기능에 대한 자세한 내용은 비즈니스용 Skype 서버 [2015의](../../plan-your-deployment/archiving/archiving.md)보관 계획, 비즈니스용 Skype 서버 [2015용](../../deploy/deploy-archiving/deploy-archiving.md)보관 배포 및 비즈니스용 Skype 서버 [2015의](../../manage/archiving/archiving.md)보관 관리를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="13e6a-136">For details about the Archiving feature and capabilities, including Exchange integration, see [Plan for archiving in Skype for Business Server 2015](../../plan-your-deployment/archiving/archiving.md), [Deploy archiving for Skype for Business Server 2015](../../deploy/deploy-archiving/deploy-archiving.md), and [Manage archiving in Skype for Business Server 2015](../../manage/archiving/archiving.md).</span></span>

