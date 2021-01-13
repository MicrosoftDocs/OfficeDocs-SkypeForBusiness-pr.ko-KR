---
title: 비즈니스용 Skype 서버 2015에서 영구 채팅 서버 관리
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c58ee4f4-563b-4d0c-be91-c62df886caa9
description: '요약: 비즈니스용 Skype 서버 2015에서 영구 채팅 서버를 관리하는 방법을 설명하는 문서입니다.'
ms.openlocfilehash: 9a97511f9b4c2adae7ead816e86876f05dd39790
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832888"
---
# <a name="manage-persistent-chat-server-in-skype-for-business-server-2015"></a><span data-ttu-id="deb1d-103">비즈니스용 Skype 서버 2015에서 영구 채팅 서버 관리</span><span class="sxs-lookup"><span data-stu-id="deb1d-103">Manage Persistent Chat Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="deb1d-104">**요약:** 영구 채팅 서버를 관리하는 방법을 비즈니스용 Skype 서버 2015에 대해 자세히 알아보습니다.</span><span class="sxs-lookup"><span data-stu-id="deb1d-104">**Summary:** Learn how to manage Persistent Chat Server in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="deb1d-105">조직에 대해 영구 채팅 서버를 설정할 때 배포 중에 초기 구성을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="deb1d-105">When you set up Persistent Chat Server for your organization, you specify the initial configuration during deployment.</span></span> <span data-ttu-id="deb1d-106">그러나 영구 채팅 서버 지원을 구현하는 방법을 변경하려는 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="deb1d-106">However, there may be times when you want to change how you implement Persistent Chat Server support.</span></span> <span data-ttu-id="deb1d-107">예를 들어 조직 내의 특정 팀 또는 그룹에 대해 다르게 영구 채팅 서버 지원 및 컨트롤을 설정해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="deb1d-107">For example you may need to set up Persistent Chat Server support and controls differently for a specific team or group within your organization.</span></span> <span data-ttu-id="deb1d-108">이 섹션에서는 영구 채팅 서버 배포를 사용자 지정하는 데 도움이 되는 정보와 절차를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="deb1d-108">This section provides information and procedures to help you customize your Persistent Chat Server deployment.</span></span> <span data-ttu-id="deb1d-109">영구 채팅 서버에 대해 구성할 수 있는 기능에 대한 자세한 내용은 비즈니스용 Skype 서버 2015의 영구 채팅 서버 [계획(Plan for Persistent Chat Server)을 참조하세요.](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)</span><span class="sxs-lookup"><span data-stu-id="deb1d-109">For details about the features and functionality that you can configure for Persistent Chat Server, see [Plan for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md).</span></span> <span data-ttu-id="deb1d-110">영구 채팅 서버 배포에 대한 자세한 내용은 비즈니스용 [Skype 서버 2015에서](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md)영구 채팅 서버 배포를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="deb1d-110">For details about deploying Persistent Chat Server, see [Deploy Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md).</span></span> 

> [!NOTE]
> <span data-ttu-id="deb1d-111">영구 채팅은 비즈니스용 Skype 서버 2015에서 사용할 수 있지만 비즈니스용 Skype 서버 2019에서 더 이상 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="deb1d-111">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="deb1d-112">Teams에서 동일한 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="deb1d-112">The same functionality is available in Teams.</span></span> <span data-ttu-id="deb1d-113">자세한 내용은 Microsoft Teams 업그레이드 시작을 [참조하세요.](/microsoftteams/upgrade-start-here)</span><span class="sxs-lookup"><span data-stu-id="deb1d-113">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="deb1d-114">영구 채팅을 사용하려면 이 기능이 필요한 사용자를 Teams로 마이그레이션하거나 비즈니스용 Skype 서버 2015를 계속 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="deb1d-114">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 
  
<span data-ttu-id="deb1d-115">제어판을 사용하거나 cmdlet을 사용하여 영구 채팅 서버를 Windows PowerShell 있습니다.</span><span class="sxs-lookup"><span data-stu-id="deb1d-115">You can manage Persistent Chat Server by using the Control Panel or by using Windows PowerShell cmdlets.</span></span> 
  
<span data-ttu-id="deb1d-116">제어판을 사용:</span><span class="sxs-lookup"><span data-stu-id="deb1d-116">To use the Control Panel:</span></span>
  
1. <span data-ttu-id="deb1d-117">CsPersistentChatAdministrator 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="deb1d-117">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="deb1d-118">시작 **메뉴에서** 비즈니스용 Skype 서버 제어판을 선택하거나 브라우저 창을 연 다음 관리 URL을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="deb1d-118">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="deb1d-119">왼쪽 탐색 모음에서 영구 **채팅을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="deb1d-119">In the left navigation bar, click **Persistent Chat**.</span></span>
    
<span data-ttu-id="deb1d-120">다음 표에는 영구 채팅 Windows PowerShell 사용할 수 있는 cmdlet이 요약되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="deb1d-120">The following table summarizes the Windows PowerShell cmdlets available to help you manage Persistent Chat Server.</span></span> <span data-ttu-id="deb1d-121">사용 가능한 모든 매개 변수를 포함하여 구문에 대한 자세한 내용은 [비즈니스용 Skype 서버 2015 관리 셸을 참조하세요.](../management-shell.md)</span><span class="sxs-lookup"><span data-stu-id="deb1d-121">For details about syntax, including all available parameters, see [Skype for Business Server 2015 Management Shell](../management-shell.md).</span></span>
  

|<span data-ttu-id="deb1d-122">**Cmdlet**</span><span class="sxs-lookup"><span data-stu-id="deb1d-122">**Cmdlet**</span></span>|<span data-ttu-id="deb1d-123">**설명**</span><span class="sxs-lookup"><span data-stu-id="deb1d-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="deb1d-124">New-CsPersistentChatCategory</span><span class="sxs-lookup"><span data-stu-id="deb1d-124">New-CsPersistentChatCategory</span></span>  <br/> |<span data-ttu-id="deb1d-125">새 범주를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="deb1d-125">Creates a new category</span></span>  <br/> |
|<span data-ttu-id="deb1d-126">Set-CsPersistentChatCategory</span><span class="sxs-lookup"><span data-stu-id="deb1d-126">Set-CsPersistentChatCategory</span></span>  <br/> |<span data-ttu-id="deb1d-127">기존 범주에 대한 설정 구성</span><span class="sxs-lookup"><span data-stu-id="deb1d-127">Configures settings for an existing category</span></span>  <br/> |
|<span data-ttu-id="deb1d-128">Get-CsPersistentChatCategory</span><span class="sxs-lookup"><span data-stu-id="deb1d-128">Get-CsPersistentChatCategory</span></span>  <br/> |<span data-ttu-id="deb1d-129">범주에 대한 정보 검색</span><span class="sxs-lookup"><span data-stu-id="deb1d-129">Retrieves information about categories</span></span>  <br/> |
|<span data-ttu-id="deb1d-130">Remove-CsPersistentChatCategory</span><span class="sxs-lookup"><span data-stu-id="deb1d-130">Remove-CsPersistentChatCategory</span></span>  <br/> |<span data-ttu-id="deb1d-131">범주 제거</span><span class="sxs-lookup"><span data-stu-id="deb1d-131">Removes a category</span></span>  <br/> |
|<span data-ttu-id="deb1d-132">New-CsPersistentChatRoom</span><span class="sxs-lookup"><span data-stu-id="deb1d-132">New-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="deb1d-133">새 대화방을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="deb1d-133">Creates a new chat room</span></span>  <br/> |
|<span data-ttu-id="deb1d-134">Set-CsPersistentChatRoom</span><span class="sxs-lookup"><span data-stu-id="deb1d-134">Set-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="deb1d-135">기존 방에 대한 설정을 구성합니다. 방에 사용자 및 사용자 그룹 할당</span><span class="sxs-lookup"><span data-stu-id="deb1d-135">Configures settings for an existing room; assign users and user groups to the room</span></span>  <br/> |
|<span data-ttu-id="deb1d-136">Get-CsPersistentChatRoom</span><span class="sxs-lookup"><span data-stu-id="deb1d-136">Get-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="deb1d-137">방에 대한 정보를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="deb1d-137">Retrieves information about rooms</span></span>  <br/> |
|<span data-ttu-id="deb1d-138">Clear-CsPersistentChatRoom</span><span class="sxs-lookup"><span data-stu-id="deb1d-138">Clear-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="deb1d-139">방 또는 방의 메시지 지우기</span><span class="sxs-lookup"><span data-stu-id="deb1d-139">Clears a room or messages from a room</span></span>  <br/> |
|<span data-ttu-id="deb1d-140">Remove-CsPersistentChatRoom</span><span class="sxs-lookup"><span data-stu-id="deb1d-140">Remove-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="deb1d-141">방 제거</span><span class="sxs-lookup"><span data-stu-id="deb1d-141">Removes a room</span></span>  <br/> |
|<span data-ttu-id="deb1d-142">Remove-CsPersistentChatMessage</span><span class="sxs-lookup"><span data-stu-id="deb1d-142">Remove-CsPersistentChatMessage</span></span>  <br/> |<span data-ttu-id="deb1d-143">방에서 메시지 제거</span><span class="sxs-lookup"><span data-stu-id="deb1d-143">Removes messages from a room</span></span>  <br/> |
|<span data-ttu-id="deb1d-144">New-CsPersistentChatAddin</span><span class="sxs-lookup"><span data-stu-id="deb1d-144">New-CsPersistentChatAddin</span></span>  <br/> |<span data-ttu-id="deb1d-145">새 추가 기능 생성</span><span class="sxs-lookup"><span data-stu-id="deb1d-145">Creates a new add-in</span></span>  <br/> |
|<span data-ttu-id="deb1d-146">Set-CsPersistentChatAddin</span><span class="sxs-lookup"><span data-stu-id="deb1d-146">Set-CsPersistentChatAddin</span></span>  <br/> |<span data-ttu-id="deb1d-147">기존 추가 기능의 설정 구성</span><span class="sxs-lookup"><span data-stu-id="deb1d-147">Configures settings for an existing add-in</span></span>  <br/> |
|<span data-ttu-id="deb1d-148">Get-CsPersistentChatAddin</span><span class="sxs-lookup"><span data-stu-id="deb1d-148">Get-CsPersistentChatAddin</span></span>  <br/> |<span data-ttu-id="deb1d-149">추가 기능 관련 정보 검색</span><span class="sxs-lookup"><span data-stu-id="deb1d-149">Retrieves information about add-ins</span></span>  <br/> |
|<span data-ttu-id="deb1d-150">Remove-CsPersistentChatAddin</span><span class="sxs-lookup"><span data-stu-id="deb1d-150">Remove-CsPersistentChatAddin</span></span>  <br/> |<span data-ttu-id="deb1d-151">추가 기능 제거</span><span class="sxs-lookup"><span data-stu-id="deb1d-151">Removes an add-in</span></span>  <br/> |
|<span data-ttu-id="deb1d-152">Set-CsPersistentChatComplianceConfiguration</span><span class="sxs-lookup"><span data-stu-id="deb1d-152">Set-CsPersistentChatComplianceConfiguration</span></span>  <br/> |<span data-ttu-id="deb1d-153">준수 구성 설정의 기존 컬렉션을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="deb1d-153">Modifies an existing collection of compliance configuration settings</span></span>  <br/> |
|<span data-ttu-id="deb1d-154">Export-CsPersistentChatData</span><span class="sxs-lookup"><span data-stu-id="deb1d-154">Export-CsPersistentChatData</span></span>  <br/> |<span data-ttu-id="deb1d-155">영구 채팅 데이터베이스에서 데이터 내보내기</span><span class="sxs-lookup"><span data-stu-id="deb1d-155">Exports data from a Persistent Chat database</span></span>  <br/> |
|<span data-ttu-id="deb1d-156">Import-CsPersistentChatData</span><span class="sxs-lookup"><span data-stu-id="deb1d-156">Import-CsPersistentChatData</span></span>  <br/> |<span data-ttu-id="deb1d-157">이전 버전의 Lync Server에서 내보운 데이터 가져오기</span><span class="sxs-lookup"><span data-stu-id="deb1d-157">Imports data that was exported from a previous version of Lync Server</span></span>  <br/> |
   

