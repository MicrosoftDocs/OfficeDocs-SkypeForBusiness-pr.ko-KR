---
title: 비즈니스용 Skype 서버에서 회의 정책 관리
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 34ec5e41-6fe6-450b-81b0-0d17b9989839
description: '요약: 비즈니스용 Skype 서버에서 회의 정책을 관리하는 방법을 설명하는 정보를 제공합니다.'
ms.openlocfilehash: 39855aac09b88852d0931c9b8fbdb8e2e9187c71
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51099104"
---
# <a name="manage-conferencing-policies-in-skype-for-business-server"></a><span data-ttu-id="e6475-103">비즈니스용 Skype 서버에서 회의 정책 관리</span><span class="sxs-lookup"><span data-stu-id="e6475-103">Manage conferencing policies in Skype for Business Server</span></span>
 
<span data-ttu-id="e6475-104">**요약:** 비즈니스용 Skype 서버에서 회의 정책을 관리하는 방법을 알아보습니다.</span><span class="sxs-lookup"><span data-stu-id="e6475-104">**Summary:** Learn how to manage conferencing policies in Skype for Business Server.</span></span>
  
<span data-ttu-id="e6475-105">이 항목에서는 회의 정책을 관리하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e6475-105">This topic describes how to manage conferencing policies.</span></span> <span data-ttu-id="e6475-106">회의를 계획하고 배포하는 방법에 대한 자세한 내용은 [Plan for conferencing in Skype for Business Server](../../plan-your-deployment/conferencing/conferencing.md) 및 Deploy [conferencing in Skype for Business Server를 참조하십시오.](../../deploy/deploy-conferencing/deploy-conferencing.md)</span><span class="sxs-lookup"><span data-stu-id="e6475-106">For more information about how to plan and deploy conferencing, see [Plan for conferencing in Skype for Business Server](../../plan-your-deployment/conferencing/conferencing.md) and [Deploy conferencing in Skype for Business Server](../../deploy/deploy-conferencing/deploy-conferencing.md).</span></span>
  
<span data-ttu-id="e6475-107">회의 정책을 사용하면 모임에 IP 오디오 및 비디오를 포함할 수 있는지 여부부터 최대 참석할 수 있는 사용자 수에 이르기까지 다양한 이벤트 및 참가 옵션을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6475-107">Conferencing policies allow you to define a wide variety of scheduling and participation options, ranging from whether a meeting can include IP audio and video to the maximum number of people who can attend.</span></span> <span data-ttu-id="e6475-108">회의 정책을 사용하여 모임의 보안, 대역폭 및 법적 측면을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6475-108">You can use conferencing policies to manage security, bandwidth, and legal aspects of meetings.</span></span>
  
<span data-ttu-id="e6475-109">회의 정책은 전역 범위, 사이트 범위 및 사용자 범위의 세 가지 수준에서 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6475-109">You can define conferencing policy on three levels: global scope, site scope, and user scope.</span></span> <span data-ttu-id="e6475-110">설정은 가장 좁은 범위에서 가장 넓은 범위순으로 특정 사용자에게 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="e6475-110">Settings apply to a specific user from the narrowest scope to the widest scope.</span></span> <span data-ttu-id="e6475-111">사용자에게 정책을 할당하는 경우 해당 설정이 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="e6475-111">If you assign a policy to a user, those settings take precedence.</span></span> <span data-ttu-id="e6475-112">사용자 정책을 할당하지 않으면 사이트 설정이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="e6475-112">If you do not assign a user policy, site settings apply.</span></span> <span data-ttu-id="e6475-113">사용자 정책이나 사이트 정책을 적용하지 않는 경우에는 글로벌 정책에서 기본 설정을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="e6475-113">If no user or site policies apply, global policy provides the default settings.</span></span>
  
<span data-ttu-id="e6475-p104">글로벌 정책은 기본적으로 있으므로 새 글로벌 정책을 만들 수는 없습니다. 또한 기존 글로벌 정책을 삭제할 수도 없지만, 기존 글로벌 정책을 변경하여 기본 설정을 사용자 지정할 수는 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6475-p104">A global policy exists by default, so you cannot create a new global policy. You also cannot delete the existing global policy, but you can change the existing global policy to customize your default settings.</span></span>
  
## <a name="manage-conferencing-policies-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="e6475-116">비즈니스용 Skype 서버 제어판을 사용하여 회의 정책 관리</span><span class="sxs-lookup"><span data-stu-id="e6475-116">Manage conferencing policies by using Skype for Business Server Control Panel</span></span>

<span data-ttu-id="e6475-117">비즈니스용 Skype 서버 제어판을 사용하여 회의 정책을 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="e6475-117">To manage conferencing policies by using Skype for Business Server Control Panel:</span></span>
  
1. <span data-ttu-id="e6475-118">CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="e6475-118">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="e6475-119">비즈니스용 Skype 서버 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="e6475-119">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="e6475-120">왼쪽 탐색 모음에서 회의 를 클릭한 다음 회의 정책을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="e6475-120">In the left navigation bar, click **Conferencing**, and then click **Conferencing Policy**.</span></span>
    
## <a name="manage-conferencing-policies-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="e6475-121">비즈니스용 Skype 서버 관리 셸을 사용하여 회의 정책 관리</span><span class="sxs-lookup"><span data-stu-id="e6475-121">Manage conferencing policies by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="e6475-122">비즈니스용 Skype 서버 관리 셸을 사용하여 모임을 관리하기 위해 다음 cmdlet을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="e6475-122">To manage meetings by using Skype for Business Server Management Shell, use the following cmdlets:</span></span>
  
<span data-ttu-id="e6475-123">**회의 정책 설정**</span><span class="sxs-lookup"><span data-stu-id="e6475-123">**Conferencing policy settings**</span></span>

|<span data-ttu-id="e6475-124">**Cmdlet**</span><span class="sxs-lookup"><span data-stu-id="e6475-124">**Cmdlet**</span></span>|<span data-ttu-id="e6475-125">**설명**</span><span class="sxs-lookup"><span data-stu-id="e6475-125">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="e6475-126">Get-CsConferencingPolicy</span><span class="sxs-lookup"><span data-stu-id="e6475-126">Get-CsConferencingPolicy</span></span>](/powershell/module/skype/get-csconferencingpolicy?view=skype-ps) <br/> |<span data-ttu-id="e6475-127">조직에서 사용하도록 구성된 회의 정책에 대한 정보를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="e6475-127">Returns information about the conferencing policies that have been configured for use in your organization.</span></span>  <br/> |
|[<span data-ttu-id="e6475-128">Grant-CsConferencingPolicy</span><span class="sxs-lookup"><span data-stu-id="e6475-128">Grant-CsConferencingPolicy</span></span>](/powershell/module/skype/grant-csconferencingpolicy?view=skype-ps) <br/> |<span data-ttu-id="e6475-129">사용자별 범위에서 전화 회의 정책을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="e6475-129">Assigns a conferencing policy at the per-user scope.</span></span>  <br/> |
|[<span data-ttu-id="e6475-130">New-CsConferencingPolicy</span><span class="sxs-lookup"><span data-stu-id="e6475-130">New-CsConferencingPolicy</span></span>](/powershell/module/skype/new-csconferencingpolicy?view=skype-ps) <br/> |<span data-ttu-id="e6475-131">조직에서 사용할 새 회의 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="e6475-131">Creates a new conferencing policy for use in your organization.</span></span>  <br/> |
|[<span data-ttu-id="e6475-132">Remove-CsConferencingPolicy</span><span class="sxs-lookup"><span data-stu-id="e6475-132">Remove-CsConferencingPolicy</span></span>](/powershell/module/skype/remove-csconferencingpolicy?view=skype-ps) <br/> |<span data-ttu-id="e6475-133">지정한 회의 정책을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="e6475-133">Removes the specified conferencing policy.</span></span>  <br/> |
|[<span data-ttu-id="e6475-134">Set-CsConferencingPolicy</span><span class="sxs-lookup"><span data-stu-id="e6475-134">Set-CsConferencingPolicy</span></span>](/powershell/module/skype/set-csconferencingpolicy?view=skype-ps) <br/> |<span data-ttu-id="e6475-135">기존 회의 정책을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="e6475-135">Modifies an existing conferencing policy.</span></span>  <br/> |
