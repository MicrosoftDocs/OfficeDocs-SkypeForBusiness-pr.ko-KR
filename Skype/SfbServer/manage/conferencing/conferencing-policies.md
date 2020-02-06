---
title: 비즈니스용 Skype 서버에서 회의 정책 관리
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 34ec5e41-6fe6-450b-81b0-0d17b9989839
description: '요약: 비즈니스용 Skype 서버에서 회의 정책을 관리 하는 방법에 대해 알아보세요.'
ms.openlocfilehash: fc069093b9cc7cf5ce0e1e1f1efc0ee9e18e335d
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818649"
---
# <a name="manage-conferencing-policies-in-skype-for-business-server"></a><span data-ttu-id="a03c0-103">비즈니스용 Skype 서버에서 회의 정책 관리</span><span class="sxs-lookup"><span data-stu-id="a03c0-103">Manage conferencing policies in Skype for Business Server</span></span>
 
<span data-ttu-id="a03c0-104">**요약:** 비즈니스용 Skype 서버에서 회의 정책을 관리 하는 방법에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="a03c0-104">**Summary:** Learn how to manage conferencing policies in Skype for Business Server.</span></span>
  
<span data-ttu-id="a03c0-105">이 항목에서는 회의 정책을 관리 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="a03c0-105">This topic describes how to manage conferencing policies.</span></span> <span data-ttu-id="a03c0-106">회의를 계획 하 고 배포 하는 방법에 대 한 자세한 내용은 비즈니스용 [Skype 서버에서 회의 계획](../../plan-your-deployment/conferencing/conferencing.md) 및 비즈니스용 [skype 서버에서 회의 배포](../../deploy/deploy-conferencing/deploy-conferencing.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a03c0-106">For more information about how to plan and deploy conferencing, see [Plan for conferencing in Skype for Business Server](../../plan-your-deployment/conferencing/conferencing.md) and [Deploy conferencing in Skype for Business Server](../../deploy/deploy-conferencing/deploy-conferencing.md).</span></span>
  
<span data-ttu-id="a03c0-107">회의 정책은 모임에서 IP 오디오 및 비디오를 참석할 수 있는 최대 사용자 수까지 포함할 수 있는지 여부에 이르기까지 다양 한 일정 및 참가 옵션을 정의할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="a03c0-107">Conferencing policies allow you to define a wide variety of scheduling and participation options, ranging from whether a meeting can include IP audio and video to the maximum number of people who can attend.</span></span> <span data-ttu-id="a03c0-108">회의 정책을 사용 하 여 모임의 보안, 대역폭 및 법적 측면을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a03c0-108">You can use conferencing policies to manage security, bandwidth, and legal aspects of meetings.</span></span>
  
<span data-ttu-id="a03c0-109">회의 정책은 전역 범위, 사이트 범위, 사용자 범위 등 세 가지 수준에서 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a03c0-109">You can define conferencing policy on three levels: global scope, site scope, and user scope.</span></span> <span data-ttu-id="a03c0-110">설정은 해당 사용자에 게 가장 좁은 범위의 범위에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a03c0-110">Settings apply to a specific user from the narrowest scope to the widest scope.</span></span> <span data-ttu-id="a03c0-111">사용자에 게 정책을 할당 하면 해당 설정이 우선적으로 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a03c0-111">If you assign a policy to a user, those settings take precedence.</span></span> <span data-ttu-id="a03c0-112">사용자 정책을 할당 하지 않으면 사이트 설정이 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a03c0-112">If you do not assign a user policy, site settings apply.</span></span> <span data-ttu-id="a03c0-113">적용 되는 사용자 또는 사이트 정책이 없는 경우 전역 정책은 기본 설정을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a03c0-113">If no user or site policies apply, global policy provides the default settings.</span></span>
  
<span data-ttu-id="a03c0-114">전역 정책은 기본적으로 존재 하므로 새 전역 정책을 만들 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a03c0-114">A global policy exists by default, so you cannot create a new global policy.</span></span> <span data-ttu-id="a03c0-115">또한 기존 전역 정책을 삭제할 수 없지만 기존 전역 정책을 변경 하 여 기본 설정을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a03c0-115">You also cannot delete the existing global policy, but you can change the existing global policy to customize your default settings.</span></span>
  
## <a name="manage-conferencing-policies-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="a03c0-116">비즈니스용 Skype 서버 제어판을 사용 하 여 회의 정책 관리</span><span class="sxs-lookup"><span data-stu-id="a03c0-116">Manage conferencing policies by using Skype for Business Server Control Panel</span></span>

<span data-ttu-id="a03c0-117">비즈니스용 Skype Server 제어판을 사용 하 여 회의 정책을 관리 하려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="a03c0-117">To manage conferencing policies by using Skype for Business Server Control Panel:</span></span>
  
1. <span data-ttu-id="a03c0-118">CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="a03c0-118">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="a03c0-119">비즈니스용 Skype Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="a03c0-119">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="a03c0-120">왼쪽 탐색 모음에서 **회의**를 클릭 한 다음 **회의 정책을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a03c0-120">In the left navigation bar, click **Conferencing**, and then click **Conferencing Policy**.</span></span>
    
## <a name="manage-conferencing-policies-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="a03c0-121">비즈니스용 Skype Server Management Shell을 사용 하 여 회의 정책 관리</span><span class="sxs-lookup"><span data-stu-id="a03c0-121">Manage conferencing policies by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="a03c0-122">비즈니스용 Skype Server Management Shell을 사용 하 여 모임을 관리 하려면 다음 cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a03c0-122">To manage meetings by using Skype for Business Server Management Shell, use the following cmdlets:</span></span>
  
<span data-ttu-id="a03c0-123">**회의 정책 설정**</span><span class="sxs-lookup"><span data-stu-id="a03c0-123">**Conferencing policy settings**</span></span>

|<span data-ttu-id="a03c0-124">**은**</span><span class="sxs-lookup"><span data-stu-id="a03c0-124">**Cmdlet**</span></span>|<span data-ttu-id="a03c0-125">**설명**</span><span class="sxs-lookup"><span data-stu-id="a03c0-125">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="a03c0-126">Get-CsConferencingPolicy</span><span class="sxs-lookup"><span data-stu-id="a03c0-126">Get-CsConferencingPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csconferencingpolicy?view=skype-ps) <br/> |<span data-ttu-id="a03c0-127">조직에서 사용 하도록 구성 된 회의 정책에 대 한 정보를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="a03c0-127">Returns information about the conferencing policies that have been configured for use in your organization.</span></span>  <br/> |
|[<span data-ttu-id="a03c0-128">부여-CsConferencingPolicy</span><span class="sxs-lookup"><span data-stu-id="a03c0-128">Grant-CsConferencingPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csconferencingpolicy?view=skype-ps) <br/> |<span data-ttu-id="a03c0-129">사용자 단위 범위에서 회의 정책을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="a03c0-129">Assigns a conferencing policy at the per-user scope.</span></span>  <br/> |
|[<span data-ttu-id="a03c0-130">New-CsConferencingPolicy</span><span class="sxs-lookup"><span data-stu-id="a03c0-130">New-CsConferencingPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csconferencingpolicy?view=skype-ps) <br/> |<span data-ttu-id="a03c0-131">조직에서 사용할 새 회의 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a03c0-131">Creates a new conferencing policy for use in your organization.</span></span>  <br/> |
|[<span data-ttu-id="a03c0-132">Remove-CsConferencingPolicy</span><span class="sxs-lookup"><span data-stu-id="a03c0-132">Remove-CsConferencingPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csconferencingpolicy?view=skype-ps) <br/> |<span data-ttu-id="a03c0-133">지정 된 회의 정책을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="a03c0-133">Removes the specified conferencing policy.</span></span>  <br/> |
|[<span data-ttu-id="a03c0-134">Set-CsConferencingPolicy</span><span class="sxs-lookup"><span data-stu-id="a03c0-134">Set-CsConferencingPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps) <br/> |<span data-ttu-id="a03c0-135">기존 회의 정책을 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a03c0-135">Modifies an existing conferencing policy.</span></span>  <br/> |
   

