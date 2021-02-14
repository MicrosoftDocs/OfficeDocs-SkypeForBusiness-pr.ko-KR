---
title: 비즈니스용 Skype 서버에서 모임 구성 설정 관리
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
ms.assetid: 2e6c4f48-464e-4b8e-b7f4-68cdc1ae4ad9
description: '요약: 비즈니스용 Skype 서버에서 모임 구성 설정을 관리하는 방법을 설명하는 정보를 제공합니다.'
ms.openlocfilehash: c34723219839061e36b2684dff81efd5cd914843
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828088"
---
# <a name="manage-meeting-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="a70ce-103">비즈니스용 Skype 서버에서 모임 구성 설정 관리</span><span class="sxs-lookup"><span data-stu-id="a70ce-103">Manage meeting configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="a70ce-104">**요약:** 비즈니스용 Skype 서버에서 모임 구성 설정을 관리하는 방법을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="a70ce-104">**Summary:** Learn how to manage meeting configuration settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="a70ce-105">이 항목에서는 모임 구성 설정을 관리하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a70ce-105">This topic describes how to manage meeting configuration settings.</span></span> <span data-ttu-id="a70ce-106">회의를 계획 및 배포하는 방법에 대한 자세한 내용은 비즈니스용 [Skype](../../plan-your-deployment/conferencing/conferencing.md) 서버에서 회의 계획 및 비즈니스용 Skype 서버에서 회의 배포를 [참조하세요.](../../deploy/deploy-conferencing/deploy-conferencing.md)</span><span class="sxs-lookup"><span data-stu-id="a70ce-106">For more information about how to plan and deploy conferencing, see [Plan for conferencing in Skype for Business Server](../../plan-your-deployment/conferencing/conferencing.md) and [Deploy conferencing in Skype for Business Server](../../deploy/deploy-conferencing/deploy-conferencing.md).</span></span>
  
<span data-ttu-id="a70ce-107">모임 구성 설정은 익명 사용자 및 전화 접속 회의 사용자가 이러한 모임에 참가할 수 있는 방법(또는 사용자라도)을 제어하는 것 외에도 사용자가 만들 수 있는 모임 유형을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="a70ce-107">Meeting configuration settings dictate the type of meetings that users can create, in addition to controlling how (or even if) anonymous users and dial-in conferencing users can join these meetings.</span></span> <span data-ttu-id="a70ce-108">이러한 설정은 예약된 모임에만 영향을 미치게 됩니다. 비즈니스용 Skype에서 모임 시작 옵션을 클릭하여 만든 Ad-Hoc 모임에는 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a70ce-108">Note that these settings only affect scheduled meetings; they do not affect ad-hoc meetings created by clicking the Meet Now option in Skype for Business.</span></span>
  
<span data-ttu-id="a70ce-109">모임 구성 설정은 다음을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="a70ce-109">Meeting configuration settings define the following:</span></span>
  
- <span data-ttu-id="a70ce-110">공중 전화망(PSTN)에서 전화 접속하는 사용자가 대기실로 이동하는지 여부</span><span class="sxs-lookup"><span data-stu-id="a70ce-110">Whether users dialing in from the public switched telephone network (PSTN) go to the lobby</span></span>
    
- <span data-ttu-id="a70ce-111">발표자로 지정될 수 있는 사용자</span><span class="sxs-lookup"><span data-stu-id="a70ce-111">Who can be a presenter</span></span>
    
- <span data-ttu-id="a70ce-112">회의 유형이 기본적으로 지정되는지 여부</span><span class="sxs-lookup"><span data-stu-id="a70ce-112">Whether conference type is assigned by default</span></span>
    
- <span data-ttu-id="a70ce-113">인증되지 않은 익명 사용자가 기본적으로 허용되는지 여부</span><span class="sxs-lookup"><span data-stu-id="a70ce-113">Whether anonymous (unauthenticated) users are admitted by default</span></span>
    
<span data-ttu-id="a70ce-114">비즈니스용 Skype 서버 제어판 또는 비즈니스용 Skype 서버 관리 셸을 사용하여 모임의 특성을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a70ce-114">You can define characteristics of meetings by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span> 
  
<span data-ttu-id="a70ce-115">모임 설정은 전역 수준(기본적으로 생성), 사이트 수준 또는 풀 수준에서 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a70ce-115">You can specify meeting settings at the global level (created by default), site level, or pool level.</span></span> <span data-ttu-id="a70ce-116">기본적으로 전역 설정은 모임 환경을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="a70ce-116">By default, the global settings define the meeting experience.</span></span> <span data-ttu-id="a70ce-117">풀 수준 설정을 만들면 설정이 해당 풀에서 호스팅된 모든 모임에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a70ce-117">If you create pool-level settings, those settings apply to all meetings hosted by that pool.</span></span> <span data-ttu-id="a70ce-118">풀 수준 설정을 만들지 않으면 사이트 수준 설정이 적용됩니다(있는 경우).</span><span class="sxs-lookup"><span data-stu-id="a70ce-118">If you do not create pool-level settings, site-level settings apply, if they exist.</span></span> <span data-ttu-id="a70ce-119">사이트 수준 설정을 정의하지 않으면 전역 설정이 모든 모임에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a70ce-119">If you do not define site-level settings, the global settings apply to all meetings.</span></span>
  
## <a name="manage-meeting-settings-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="a70ce-120">비즈니스용 Skype 서버 제어판을 사용하여 모임 설정 관리</span><span class="sxs-lookup"><span data-stu-id="a70ce-120">Manage meeting settings by using Skype for Business Server Control Panel</span></span>

<span data-ttu-id="a70ce-121">비즈니스용 Skype 서버 제어판을 사용하여 모임 설정을 관리하려면</span><span class="sxs-lookup"><span data-stu-id="a70ce-121">To manage meeting settings by using Skype for Business Server Control Panel:</span></span>
  
1. <span data-ttu-id="a70ce-122">CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="a70ce-122">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="a70ce-123">비즈니스용 Skype 서버 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="a70ce-123">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="a70ce-124">왼쪽 탐색 모음에서 회의를 클릭한 다음 모임 **구성을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="a70ce-124">In the left navigation bar, click **Conferencing**, and then click **Meeting Configuration**.</span></span>
    
## <a name="manage-meeting-settings-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="a70ce-125">비즈니스용 Skype 서버 관리 셸을 사용하여 모임 설정 관리</span><span class="sxs-lookup"><span data-stu-id="a70ce-125">Manage meeting settings by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="a70ce-126">비즈니스용 Skype 서버 관리 셸을 사용하여 모임을 관리하기 위해 다음 cmdlet을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="a70ce-126">To manage meetings by using Skype for Business Server Management Shell, use the following cmdlets:</span></span>
  
<span data-ttu-id="a70ce-127">**모임 구성 설정**</span><span class="sxs-lookup"><span data-stu-id="a70ce-127">**Meeting configuration settings**</span></span>

|<span data-ttu-id="a70ce-128">**Cmdlet**</span><span class="sxs-lookup"><span data-stu-id="a70ce-128">**Cmdlet**</span></span>|<span data-ttu-id="a70ce-129">**설명**</span><span class="sxs-lookup"><span data-stu-id="a70ce-129">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="a70ce-130">Get-CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="a70ce-130">Get-CsMeetingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csmeetingconfiguration?view=skype-ps) <br/> |<span data-ttu-id="a70ce-131">조직에서 현재 사용 중인 모임 구성 설정에 대한 정보를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="a70ce-131">Returns information about the meeting configuration settings currently in use in your organization.</span></span>  <br/> |
|[<span data-ttu-id="a70ce-132">New-CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="a70ce-132">New-CsMeetingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csmeetingconfiguration?view=skype-ps) <br/> |<span data-ttu-id="a70ce-133">사이트 또는 서비스 범위에서 새 전화 회의 구성 컬렉션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a70ce-133">Creates a new collection of meeting configuration settings at the site or service scope.</span></span>  <br/> |
|[<span data-ttu-id="a70ce-134">Remove-CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="a70ce-134">Remove-CsMeetingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps) <br/> |<span data-ttu-id="a70ce-135">모임 구성 설정의 기존 컬렉션을 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="a70ce-135">Deletes an existing collection of meeting configuration settings.</span></span>  <br/> |
|[<span data-ttu-id="a70ce-136">Set-CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="a70ce-136">Set-CsMeetingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps) <br/> |<span data-ttu-id="a70ce-137">조직에서 현재 사용 중인 모임 구성 설정을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="a70ce-137">Modifies the meeting configuration settings currently in use in your organization.</span></span>  <br/> |
   

