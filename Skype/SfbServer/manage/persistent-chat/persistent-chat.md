---
title: 비즈니스용 Skype 서버 2015에서 영구 채팅 서버 관리
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c58ee4f4-563b-4d0c-be91-c62df886caa9
description: '요약: 비즈니스용 Skype 서버 2015에서 영구 채팅 서버를 관리 하는 방법에 대해 알아봅니다.'
ms.openlocfilehash: 97cce8adedbb4dea932084497006e3c17bfdd7d8
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817324"
---
# <a name="manage-persistent-chat-server-in-skype-for-business-server-2015"></a><span data-ttu-id="7fc7c-103">비즈니스용 Skype 서버 2015에서 영구 채팅 서버 관리</span><span class="sxs-lookup"><span data-stu-id="7fc7c-103">Manage Persistent Chat Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="7fc7c-104">**요약:** 비즈니스용 Skype 서버 2015에서 영구 채팅 서버를 관리 하는 방법에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="7fc7c-104">**Summary:** Learn how to manage Persistent Chat Server in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="7fc7c-105">조직에 대해 영구 채팅 서버를 설정 하는 경우 배포 중에 초기 구성을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7fc7c-105">When you set up Persistent Chat Server for your organization, you specify the initial configuration during deployment.</span></span> <span data-ttu-id="7fc7c-106">그러나 영구 채팅 서버 지원을 구현 하는 방법을 변경 해야 하는 경우도 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7fc7c-106">However, there may be times when you want to change how you implement Persistent Chat Server support.</span></span> <span data-ttu-id="7fc7c-107">예를 들어 조직 내 특정 팀 또는 그룹에 대해 영구 채팅 서버 지원과 컨트롤을 다르게 설정 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7fc7c-107">For example you may need to set up Persistent Chat Server support and controls differently for a specific team or group within your organization.</span></span> <span data-ttu-id="7fc7c-108">이 섹션에서는 영구 채팅 서버 배포를 사용자 지정 하는 데 도움이 되는 정보와 절차에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="7fc7c-108">This section provides information and procedures to help you customize your Persistent Chat Server deployment.</span></span> <span data-ttu-id="7fc7c-109">영구 채팅 서버에 대해 구성할 수 있는 기능 및 기능에 대 한 자세한 내용은 비즈니스용 [Skype 서버 2015의 영구 채팅 서버 계획](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7fc7c-109">For details about the features and functionality that you can configure for Persistent Chat Server, see [Plan for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md).</span></span> <span data-ttu-id="7fc7c-110">영구 채팅 서버 배포에 대 한 자세한 내용은 비즈니스용 [Skype 서버 2015에서 영구 채팅 서버 배포](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7fc7c-110">For details about deploying Persistent Chat Server, see [Deploy Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md).</span></span> 

> [!NOTE]
> <span data-ttu-id="7fc7c-111">영구 채팅은 비즈니스용 Skype 서버 2015에서 사용할 수 있지만, 비즈니스용 Skype Server 2019에서는 더 이상 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7fc7c-111">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="7fc7c-112">팀 에서도 동일한 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7fc7c-112">The same functionality is available in Teams.</span></span> <span data-ttu-id="7fc7c-113">자세한 내용은 [Microsoft 팀 업그레이드 시작](/microsoftteams/upgrade-start-here)을 참고 하세요.</span><span class="sxs-lookup"><span data-stu-id="7fc7c-113">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="7fc7c-114">영구 채팅을 사용 해야 하는 경우에는이 기능이 필요한 사용자를 팀에 마이그레이션하거나 비즈니스용 Skype 서버 2015를 계속 사용 하는 것이 선택 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7fc7c-114">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 
  
<span data-ttu-id="7fc7c-115">제어판을 사용 하거나 Windows PowerShell cmdlet을 사용 하 여 영구 채팅 서버를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7fc7c-115">You can manage Persistent Chat Server by using the Control Panel or by using Windows PowerShell cmdlets.</span></span> 
  
<span data-ttu-id="7fc7c-116">제어판을 사용 하려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="7fc7c-116">To use the Control Panel:</span></span>
  
1. <span data-ttu-id="7fc7c-117">CsPersistentChatAdministrator 또는 CsAdministrator 역할에 지정된 사용자 계정에서 내부 배포의 임의 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="7fc7c-117">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="7fc7c-118">**시작** 메뉴에서 비즈니스용 Skype 서버 제어판을 선택 하거나 브라우저 창을 연 다음 관리 URL을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="7fc7c-118">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="7fc7c-119">왼쪽 탐색 모음에서 **영구 채팅**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="7fc7c-119">In the left navigation bar, click **Persistent Chat**.</span></span>
    
<span data-ttu-id="7fc7c-120">다음 표에는 영구 채팅 서버를 관리 하는 데 사용할 수 있는 Windows PowerShell cmdlet이 요약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7fc7c-120">The following table summarizes the Windows PowerShell cmdlets available to help you manage Persistent Chat Server.</span></span> <span data-ttu-id="7fc7c-121">사용 가능한 모든 매개 변수를 포함 하 여 구문에 대 한 자세한 내용은 비즈니스용 [Skype Server 2015 관리 셸을](../management-shell.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7fc7c-121">For details about syntax, including all available parameters, see [Skype for Business Server 2015 Management Shell](../management-shell.md).</span></span>
  

|<span data-ttu-id="7fc7c-122">**은**</span><span class="sxs-lookup"><span data-stu-id="7fc7c-122">**Cmdlet**</span></span>|<span data-ttu-id="7fc7c-123">**설명**</span><span class="sxs-lookup"><span data-stu-id="7fc7c-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="7fc7c-124">새로운 CsPersistentChatCategory</span><span class="sxs-lookup"><span data-stu-id="7fc7c-124">New-CsPersistentChatCategory</span></span>  <br/> |<span data-ttu-id="7fc7c-125">새 범주 만들기</span><span class="sxs-lookup"><span data-stu-id="7fc7c-125">Creates a new category</span></span>  <br/> |
|<span data-ttu-id="7fc7c-126">Set-CsPersistentChatCategory</span><span class="sxs-lookup"><span data-stu-id="7fc7c-126">Set-CsPersistentChatCategory</span></span>  <br/> |<span data-ttu-id="7fc7c-127">기존 범주에 대 한 설정 구성</span><span class="sxs-lookup"><span data-stu-id="7fc7c-127">Configures settings for an existing category</span></span>  <br/> |
|<span data-ttu-id="7fc7c-128">Get-CsPersistentChatCategory</span><span class="sxs-lookup"><span data-stu-id="7fc7c-128">Get-CsPersistentChatCategory</span></span>  <br/> |<span data-ttu-id="7fc7c-129">범주에 대 한 정보를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="7fc7c-129">Retrieves information about categories</span></span>  <br/> |
|<span data-ttu-id="7fc7c-130">제거-CsPersistentChatCategory</span><span class="sxs-lookup"><span data-stu-id="7fc7c-130">Remove-CsPersistentChatCategory</span></span>  <br/> |<span data-ttu-id="7fc7c-131">범주 제거</span><span class="sxs-lookup"><span data-stu-id="7fc7c-131">Removes a category</span></span>  <br/> |
|<span data-ttu-id="7fc7c-132">새로운 CsPersistentChatRoom</span><span class="sxs-lookup"><span data-stu-id="7fc7c-132">New-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="7fc7c-133">새 채팅방을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7fc7c-133">Creates a new chat room</span></span>  <br/> |
|<span data-ttu-id="7fc7c-134">Set-CsPersistentChatRoom</span><span class="sxs-lookup"><span data-stu-id="7fc7c-134">Set-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="7fc7c-135">기존 채팅방에 대 한 설정을 구성 합니다. 룸에 사용자 및 사용자 그룹 지정</span><span class="sxs-lookup"><span data-stu-id="7fc7c-135">Configures settings for an existing room; assign users and user groups to the room</span></span>  <br/> |
|<span data-ttu-id="7fc7c-136">Get-CsPersistentChatRoom</span><span class="sxs-lookup"><span data-stu-id="7fc7c-136">Get-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="7fc7c-137">채팅방에 대 한 정보를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="7fc7c-137">Retrieves information about rooms</span></span>  <br/> |
|<span data-ttu-id="7fc7c-138">일반-CsPersistentChatRoom</span><span class="sxs-lookup"><span data-stu-id="7fc7c-138">Clear-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="7fc7c-139">채팅방 또는 대화방에서 메시지 지우기</span><span class="sxs-lookup"><span data-stu-id="7fc7c-139">Clears a room or messages from a room</span></span>  <br/> |
|<span data-ttu-id="7fc7c-140">제거-CsPersistentChatRoom</span><span class="sxs-lookup"><span data-stu-id="7fc7c-140">Remove-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="7fc7c-141">채팅방을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="7fc7c-141">Removes a room</span></span>  <br/> |
|<span data-ttu-id="7fc7c-142">제거-CsPersistentChatMessage</span><span class="sxs-lookup"><span data-stu-id="7fc7c-142">Remove-CsPersistentChatMessage</span></span>  <br/> |<span data-ttu-id="7fc7c-143">채팅방에서 메시지를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="7fc7c-143">Removes messages from a room</span></span>  <br/> |
|<span data-ttu-id="7fc7c-144">New-CsPersistentChatAddin</span><span class="sxs-lookup"><span data-stu-id="7fc7c-144">New-CsPersistentChatAddin</span></span>  <br/> |<span data-ttu-id="7fc7c-145">새 추가 기능을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7fc7c-145">Creates a new add-in</span></span>  <br/> |
|<span data-ttu-id="7fc7c-146">Set-CsPersistentChatAddin</span><span class="sxs-lookup"><span data-stu-id="7fc7c-146">Set-CsPersistentChatAddin</span></span>  <br/> |<span data-ttu-id="7fc7c-147">기존 추가 기능에 대 한 설정을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="7fc7c-147">Configures settings for an existing add-in</span></span>  <br/> |
|<span data-ttu-id="7fc7c-148">Get-CsPersistentChatAddin</span><span class="sxs-lookup"><span data-stu-id="7fc7c-148">Get-CsPersistentChatAddin</span></span>  <br/> |<span data-ttu-id="7fc7c-149">추가 기능에 대 한 정보를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="7fc7c-149">Retrieves information about add-ins</span></span>  <br/> |
|<span data-ttu-id="7fc7c-150">제거-CsPersistentChatAddin</span><span class="sxs-lookup"><span data-stu-id="7fc7c-150">Remove-CsPersistentChatAddin</span></span>  <br/> |<span data-ttu-id="7fc7c-151">추가 기능을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="7fc7c-151">Removes an add-in</span></span>  <br/> |
|<span data-ttu-id="7fc7c-152">Set-CsPersistentChatComplianceConfiguration</span><span class="sxs-lookup"><span data-stu-id="7fc7c-152">Set-CsPersistentChatComplianceConfiguration</span></span>  <br/> |<span data-ttu-id="7fc7c-153">준수 구성 설정의 기존 컬렉션을 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7fc7c-153">Modifies an existing collection of compliance configuration settings</span></span>  <br/> |
|<span data-ttu-id="7fc7c-154">Export-CsPersistentChatData</span><span class="sxs-lookup"><span data-stu-id="7fc7c-154">Export-CsPersistentChatData</span></span>  <br/> |<span data-ttu-id="7fc7c-155">영구 채팅 데이터베이스에서 데이터 내보내기</span><span class="sxs-lookup"><span data-stu-id="7fc7c-155">Exports data from a Persistent Chat database</span></span>  <br/> |
|<span data-ttu-id="7fc7c-156">가져오기-CsPersistentChatData</span><span class="sxs-lookup"><span data-stu-id="7fc7c-156">Import-CsPersistentChatData</span></span>  <br/> |<span data-ttu-id="7fc7c-157">이전 버전의 Lync Server에서 내보낸 데이터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="7fc7c-157">Imports data that was exported from a previous version of Lync Server</span></span>  <br/> |
   

