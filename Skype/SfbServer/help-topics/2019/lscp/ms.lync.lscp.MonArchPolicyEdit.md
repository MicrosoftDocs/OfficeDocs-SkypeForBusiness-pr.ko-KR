---
title: 보관 정책 새로 만들기 또는 기존 편집
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.lscp.MonArchPolicyEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a4f948e7-e8f6-449a-8907-f61c5b143c05
ROBOTS: NOINDEX, NOFOLLOW
description: 보관 정책을 사용 하 여 비즈니스용 Skype 서버에 거주 하는 사용자에 대 한 배포의 내부 및 외부 통신 보관을 제어 합니다. 보관 정책에는 전역 정책과 하나 이상의 사이트 및 사용자 정책(선택 사항)이 포함됩니다.
ms.openlocfilehash: 1eb1f0060e80fbb7d325f5fbe1b7a247d6d006b6
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41691223"
---
# <a name="archiving-policy-create-new-or-edit-existing"></a><span data-ttu-id="e3762-104">보관 정책: 새로 만들기 또는 기존 항목 편집</span><span class="sxs-lookup"><span data-stu-id="e3762-104">Archiving Policy: Create New or Edit Existing</span></span>
 
<span data-ttu-id="e3762-105">보관 정책을 사용 하 여 비즈니스용 Skype 서버에 거주 하는 사용자에 대 한 배포의 내부 및 외부 통신 보관을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3762-105">You use Archiving policies to control archiving of internal and external communications in your deployment for users who are homed on Skype for Business Server.</span></span> <span data-ttu-id="e3762-106">보관 정책에는 전역 정책과 하나 이상의 사이트 및 사용자 정책(선택 사항)이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3762-106">Archiving policies include the global policy, and, optionally, one or more site and user policies:</span></span>
  
- <span data-ttu-id="e3762-107">**글로벌 정책** 전역 정책은 모든 비즈니스용 Skype 서버 배포에 기본적으로 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="e3762-107">**Global policy** The global policy is created by default in all Skype for Business Server deployments.</span></span> <span data-ttu-id="e3762-108">전역 정책을 편집할 수는 있지만 이 정책을 삭제할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e3762-108">You can edit the global policy, but you cannot delete this policy.</span></span> <span data-ttu-id="e3762-109">정책을 삭제하려고 하면 모든 옵션이 기본값으로 다시 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3762-109">If you try to delete it, all options are reset to the defaults.</span></span>
    
- <span data-ttu-id="e3762-110">**사이트 정책 (선택 사항)** 특정 사이트에 대 한 내부 또는 외부 통신을 사용 하도록 설정 하 고 보관 하지 않도록 구성할 수 있는 하나 이상의 사이트 보관 정책을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3762-110">**Site policies (optional)** You can specify one or more site Archiving policies, each of which you can configure to enable and disable archiving of internal or external communications for a specific site.</span></span> <span data-ttu-id="e3762-111">사이트 정책은 보관 정책에 지정된 사이트에 한해 전역 정책에 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="e3762-111">A site policy overrides the global policy, but only for the sites specified in Archiving policies.</span></span> <span data-ttu-id="e3762-112">사이트 정책은 편집하거나 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3762-112">You can edit or delete site policies.</span></span>
    
- <span data-ttu-id="e3762-113">**사용자 정책 (선택 사항)** 특정 사용자에 대 한 내부 또는 외부 통신을 사용 하도록 설정 하 고 보관 하지 않도록 구성할 수 있는 하나 이상의 사용자 보관 정책을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3762-113">**User policies (optional)** You can specify one or more user Archiving policies, each of which you can configure to enable and disable archiving for internal or external communications for a specific user.</span></span> <span data-ttu-id="e3762-114">사용자 정책은 사용자 정책을 할당하는 사용자에 한해 전역 정책 및 사이트 정책에 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="e3762-114">A user policy overrides the global policy and site policies, but only for the user(s) to whom you assign a user policy.</span></span> <span data-ttu-id="e3762-115">사용자 정책은 편집하거나 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3762-115">You can edit or delete user policies.</span></span>
    
> [!NOTE]
> <span data-ttu-id="e3762-116">Exchange 통합을 사용 하 여 Microsoft Exchange에 보관 데이터를 저장 하는 경우 exchange 정책은 exchange에 있는 사용자의 보관을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3762-116">If you use Exchange integration to store archiving data in Microsoft Exchange, then Exchange policies control archiving for users homed on Exchange.</span></span> <span data-ttu-id="e3762-117">이러한 사용자에 대해 보관을 사용 하도록 설정 하려면 사용자의 사서함이 원본 위치 유지에 배치 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3762-117">To enable archiving for those users, the user's mailbox must be placed on In-Place Hold.</span></span> 
  
<span data-ttu-id="e3762-118">새 보관 정책 또는 기존 보관 정책의 설정을 구성하려면 다음 옵션을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e3762-118">To configure the settings for a new or existing Archiving policy, you specify the following options:</span></span>
- <span data-ttu-id="e3762-119">**이름** 각 보관 정책에는 이름이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3762-119">**Name** Each Archiving policy requires a name.</span></span> <span data-ttu-id="e3762-120">이름은 추가 하거나 편집 하는 정책의 유형에 따라 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3762-120">The name is determined by the type of policy that you are adding or editing:</span></span>
    
  - <span data-ttu-id="e3762-121">**글로벌 정책** 기본 이름은 전역입니다.</span><span class="sxs-lookup"><span data-stu-id="e3762-121">**Global policy** The default name is Global.</span></span> <span data-ttu-id="e3762-122">보다 설명적인 이름으로 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3762-122">You can change it to a more descriptive name.</span></span> <span data-ttu-id="e3762-123">예를 들면 '한미 교역 북미 조직'과 같은 이름을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3762-123">For example, Contoso North American Organization.</span></span>
    
  - <span data-ttu-id="e3762-124">**사이트 정책** 이 대화 상자에 나열 된 사이트에는 배포에서 사용할 수 있는 모든 사이트가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3762-124">**Site policy** The sites listed in this dialog box include all available sites in your deployment.</span></span> <span data-ttu-id="e3762-125">사이트 하나를 클릭하여 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e3762-125">Click a single site to select it.</span></span> <span data-ttu-id="e3762-126">예를 들면 'Redmond 데이터 센터'와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e3762-126">For example, Redmond Data Center.</span></span>
    
  - <span data-ttu-id="e3762-127">**사용자 정책** 특정 사용자의 이름이 나 조직의 사용자 그룹 또는 팀 이름 등의 적절 한 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3762-127">**User policy** Specify an appropriate name, such as the name of a specific user or the name of a user group or team in your organization.</span></span> <span data-ttu-id="e3762-128">예를 들어 '법률 부서'와 같이 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3762-128">For example, Legal Department.</span></span>
    
- <span data-ttu-id="e3762-129">**설명** 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="e3762-129">**Description** This is optional.</span></span> <span data-ttu-id="e3762-130">이 기능을 사용 하 여 정책의 범위 또는 사용 등 추가 세부 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3762-130">Use it to provide additional details, such as the scope or use of the policy.</span></span> <span data-ttu-id="e3762-131">예를 들어 다른 사이트의 법률 부서를 사용 하 여 조정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3762-131">For example, Coordinate with Legal Departments of Other Sites.</span></span>
    
- <span data-ttu-id="e3762-132">**내부 통신 보관** 내부 네트워크에서 통신 보관을 사용 하도록 설정 하려면이 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3762-132">**Archive internal communications** Select this check box to enable archiving of communications on your internal network.</span></span> <span data-ttu-id="e3762-133">기본적으로이 방법은 모든 정책에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e3762-133">By default, this is not enabled in any policy.</span></span>
    
- <span data-ttu-id="e3762-134">**외부 통신 보관** 외부 사용자 (예: 익명 사용자와 PIC 설정 사용자 포함) 및 페더레이션 파트너를 포함 하는 통신 보관을 사용 하도록 설정 하려면이 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3762-134">**Archive external communications** Select this check box to enable archiving of communications that include external users, such as remote users, (including anonymous and PIC-setting users), and federated partners.</span></span> <span data-ttu-id="e3762-135">기본적으로이 방법은 모든 정책에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e3762-135">By default, this is not enabled in any policy.</span></span>
    
<span data-ttu-id="e3762-136">Exchange 통합을 포함 하 여 보관 기능 및 기능에 대 한 자세한 내용은 비즈니스용 [Skype 서버에서 보관 계획](../../../plan-your-deployment/archiving/archiving.md), 비즈니스용 [skype server 용 보관 배포](../../../deploy/deploy-archiving/deploy-archiving.md)및 비즈니스용 [skype 서버에서 보관 관리](../../../manage/archiving/archiving.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e3762-136">For details about the Archiving feature and capabilities, including Exchange integration, see [Plan for archiving in Skype for Business Server](../../../plan-your-deployment/archiving/archiving.md), [Deploy archiving for Skype for Business Server](../../../deploy/deploy-archiving/deploy-archiving.md), and [Manage archiving in Skype for Business Server](../../../manage/archiving/archiving.md).</span></span>

