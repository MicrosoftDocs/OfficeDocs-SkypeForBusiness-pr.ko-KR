---
title: 비즈니스용 Skype 서버에서 모임 구성 설정 관리
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2e6c4f48-464e-4b8e-b7f4-68cdc1ae4ad9
description: '요약: 비즈니스용 Skype 서버에서 모임 구성 설정을 관리 하는 방법에 대해 알아봅니다.'
ms.openlocfilehash: d9ed049fe4873428729149e1ea624bf715bb81ac
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36189651"
---
# <a name="manage-meeting-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="7d3a1-103">비즈니스용 Skype 서버에서 모임 구성 설정 관리</span><span class="sxs-lookup"><span data-stu-id="7d3a1-103">Manage meeting configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="7d3a1-104">**요약:** 비즈니스용 Skype 서버에서 모임 구성 설정을 관리 하는 방법에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="7d3a1-104">**Summary:** Learn how to manage meeting configuration settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="7d3a1-105">이 항목에서는 모임 구성 설정을 관리 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d3a1-105">This topic describes how to manage meeting configuration settings.</span></span> <span data-ttu-id="7d3a1-106">회의를 계획 하 고 배포 하는 방법에 대 한 자세한 내용은 비즈니스용 [Skype 서버에서 회의 계획](../../plan-your-deployment/conferencing/conferencing.md) 및 비즈니스용 [skype 서버에서 회의 배포](../../deploy/deploy-conferencing/deploy-conferencing.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7d3a1-106">For more information about how to plan and deploy conferencing, see [Plan for conferencing in Skype for Business Server](../../plan-your-deployment/conferencing/conferencing.md) and [Deploy conferencing in Skype for Business Server](../../deploy/deploy-conferencing/deploy-conferencing.md).</span></span>
  
<span data-ttu-id="7d3a1-107">모임 구성 설정에서는 사용자가 만들 수 있는 모임의 유형 외에도 익명 사용자 및 전화 접속 회의 사용자가 이러한 모임에 참가할 수 있는 방법 (또는 경우)을 제어할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d3a1-107">Meeting configuration settings dictate the type of meetings that users can create, in addition to controlling how (or even if) anonymous users and dial-in conferencing users can join these meetings.</span></span> <span data-ttu-id="7d3a1-108">이러한 설정은 예정 된 모임에만 영향을 줍니다. 비즈니스용 Skype에서 모임 시작 옵션을 클릭 하 여 만든 임시 모임에는 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7d3a1-108">Note that these settings only affect scheduled meetings; they do not affect ad-hoc meetings created by clicking the Meet Now option in Skype for Business.</span></span>
  
<span data-ttu-id="7d3a1-109">모임 구성 설정에서 다음을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d3a1-109">Meeting configuration settings define the following:</span></span>
  
- <span data-ttu-id="7d3a1-110">사용자가 공공 전화망 (PSTN)에서 전화 접속을 할 수 있는지 여부 대기실로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d3a1-110">Whether users dialing in from the public switched telephone network (PSTN) go to the lobby</span></span>
    
- <span data-ttu-id="7d3a1-111">발표자가 될 수 있는 사람</span><span class="sxs-lookup"><span data-stu-id="7d3a1-111">Who can be a presenter</span></span>
    
- <span data-ttu-id="7d3a1-112">회의 종류가 기본적으로 할당 되는지 여부</span><span class="sxs-lookup"><span data-stu-id="7d3a1-112">Whether conference type is assigned by default</span></span>
    
- <span data-ttu-id="7d3a1-113">익명 (인증 되지 않은) 사용자가 기본적으로 허가 되었는지 여부</span><span class="sxs-lookup"><span data-stu-id="7d3a1-113">Whether anonymous (unauthenticated) users are admitted by default</span></span>
    
<span data-ttu-id="7d3a1-114">비즈니스용 Skype Server 제어판을 사용 하거나 비즈니스용 Skype Server Management Shell을 사용 하 여 모임의 특성을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d3a1-114">You can define characteristics of meetings by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span> 
  
<span data-ttu-id="7d3a1-115">전역 수준 (기본적으로 만들어짐), 사이트 수준 또는 풀 수준에서 모임 설정을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d3a1-115">You can specify meeting settings at the global level (created by default), site level, or pool level.</span></span> <span data-ttu-id="7d3a1-116">기본적으로 전역 설정은 모임 환경을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d3a1-116">By default, the global settings define the meeting experience.</span></span> <span data-ttu-id="7d3a1-117">풀 수준 설정을 만드는 경우 해당 설정이 해당 풀에서 호스트 하는 모든 모임에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d3a1-117">If you create pool-level settings, those settings apply to all meetings hosted by that pool.</span></span> <span data-ttu-id="7d3a1-118">풀 수준 설정을 만들지 않으면 사이트 수준 설정이 있는 경우 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d3a1-118">If you do not create pool-level settings, site-level settings apply, if they exist.</span></span> <span data-ttu-id="7d3a1-119">사이트 수준 설정을 정의 하지 않으면 모든 모임에 전역 설정이 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d3a1-119">If you do not define site-level settings, the global settings apply to all meetings.</span></span>
  
## <a name="manage-meeting-settings-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="7d3a1-120">비즈니스용 Skype 서버 제어판을 사용 하 여 모임 설정 관리</span><span class="sxs-lookup"><span data-stu-id="7d3a1-120">Manage meeting settings by using Skype for Business Server Control Panel</span></span>

<span data-ttu-id="7d3a1-121">비즈니스용 Skype Server 제어판을 사용 하 여 모임 설정을 관리 하려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d3a1-121">To manage meeting settings by using Skype for Business Server Control Panel:</span></span>
  
1. <span data-ttu-id="7d3a1-122">CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d3a1-122">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="7d3a1-123">비즈니스용 Skype Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="7d3a1-123">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="7d3a1-124">왼쪽 탐색 모음에서 **회의**를 클릭 한 다음 **모임 구성을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d3a1-124">In the left navigation bar, click **Conferencing**, and then click **Meeting Configuration**.</span></span>
    
## <a name="manage-meeting-settings-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="7d3a1-125">비즈니스용 Skype Server Management Shell을 사용 하 여 모임 설정 관리</span><span class="sxs-lookup"><span data-stu-id="7d3a1-125">Manage meeting settings by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="7d3a1-126">비즈니스용 Skype Server Management Shell을 사용 하 여 모임을 관리 하려면 다음 cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d3a1-126">To manage meetings by using Skype for Business Server Management Shell, use the following cmdlets:</span></span>
  
<span data-ttu-id="7d3a1-127">**모임 구성 설정**</span><span class="sxs-lookup"><span data-stu-id="7d3a1-127">**Meeting configuration settings**</span></span>

|<span data-ttu-id="7d3a1-128">**은**</span><span class="sxs-lookup"><span data-stu-id="7d3a1-128">**Cmdlet**</span></span>|<span data-ttu-id="7d3a1-129">**설명**</span><span class="sxs-lookup"><span data-stu-id="7d3a1-129">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="7d3a1-130">Get-CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="7d3a1-130">Get-CsMeetingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csmeetingconfiguration?view=skype-ps) <br/> |<span data-ttu-id="7d3a1-131">조직에서 현재 사용 중인 모임 구성 설정에 대 한 정보를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d3a1-131">Returns information about the meeting configuration settings currently in use in your organization.</span></span>  <br/> |
|[<span data-ttu-id="7d3a1-132">New-CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="7d3a1-132">New-CsMeetingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csmeetingconfiguration?view=skype-ps) <br/> |<span data-ttu-id="7d3a1-133">사이트 또는 서비스 범위에서 모임 구성 설정의 새 컬렉션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7d3a1-133">Creates a new collection of meeting configuration settings at the site or service scope.</span></span>  <br/> |
|[<span data-ttu-id="7d3a1-134">제거-CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="7d3a1-134">Remove-CsMeetingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps) <br/> |<span data-ttu-id="7d3a1-135">기존 모임 구성 설정 모음을 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d3a1-135">Deletes an existing collection of meeting configuration settings.</span></span>  <br/> |
|[<span data-ttu-id="7d3a1-136">Set-CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="7d3a1-136">Set-CsMeetingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps) <br/> |<span data-ttu-id="7d3a1-137">조직에서 현재 사용 중인 모임 구성 설정을 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d3a1-137">Modifies the meeting configuration settings currently in use in your organization.</span></span>  <br/> |
   

