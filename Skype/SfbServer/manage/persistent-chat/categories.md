---
title: 영구 채팅 서버의 범주 관리
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 1/31/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b0c834b9-b5c8-41d5-865b-c8b180e76d13
description: '요약: 비즈니스용 Skype 서버 2015에서 영구 채팅 서버 범주를 관리 하는 방법에 대해 알아봅니다.'
ms.openlocfilehash: 03e01e6221cdb32e4a2c77314e256a195b9ea4d3
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817334"
---
# <a name="manage-categories-in-persistent-chat-server-in-skype-for-business-server-2015"></a><span data-ttu-id="d1a57-103">영구 채팅 서버의 범주 관리</span><span class="sxs-lookup"><span data-stu-id="d1a57-103">Manage categories in Persistent Chat Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="d1a57-104">**요약:** 비즈니스용 Skype 서버 2015에서 영구 채팅 서버 범주를 관리 하는 방법에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="d1a57-104">**Summary:** Learn how to manage Persistent Chat Server categories in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="d1a57-105">범주는 채팅방을 구성 하는 논리적 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="d1a57-105">A category is a logical structure for organizing chat rooms.</span></span> <span data-ttu-id="d1a57-106">범주는 채팅방을 만들거나 참가할 수 있는 사용자 및 사용자 그룹을 제어 하는 기본 Acl (액세스 제어 목록) 집합을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1a57-106">A category defines a default set of access control lists (ACLs) for controlling the users and user groups who can create or join the chat rooms.</span></span> <span data-ttu-id="d1a57-107">채팅방 범주에는 채팅방이 들어 있지만 다른 범주는 포함 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d1a57-107">Chat room categories contain chat rooms, but not other categories.</span></span> <span data-ttu-id="d1a57-108">각 범주는 Name과 Description과 같은 메타데이터를 사용해서 해당 콘텐츠를 기술합니다.</span><span class="sxs-lookup"><span data-stu-id="d1a57-108">Each category describes its contents with metadata, such as Name and Description.</span></span> <span data-ttu-id="d1a57-109">범주에는 자신에 게 속하는 채팅방의 동작을 제어 하기 위해 설정할 수 있는 속성이 있습니다. 예를 들어 채팅방에서 초대 또는 파일 업로드를 허용 하는지 여부 또는 채팅 기록을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1a57-109">The category has properties that can be set to control the behavior of the chat rooms belonging to it; for example, whether the chat rooms allow Invitations or File Uploads, or contain Chat History.</span></span> 
  
<span data-ttu-id="d1a57-110">다양 한 범주를 사용 하 여 채팅방을 만들고 관리 하는 것이 훨씬 쉬워졌습니다.</span><span class="sxs-lookup"><span data-stu-id="d1a57-110">Creating and managing chat rooms is much easier with the correct use of categories.</span></span> <span data-ttu-id="d1a57-111">영구 채팅 서버 관리자는 각 범주에 대해 AllowedMembers 및 작성자를 정의할 수 있으며, 범주에서 만든 모든 채팅방에 적용 되는 기본 채팅방 설정 및 동작을 정의할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1a57-111">As a Persistent Chat Server administrator, you can define AllowedMembers and Creators for each category, and also define the default chat room settings and behaviors that will be applied to all chat rooms created in the category.</span></span> <span data-ttu-id="d1a57-112">예를 들어 범주의 AllowedMembers를 contoso.com로 설정한 경우 Contoso의 모든 그룹 또는 사용자를 해당 범주의 채팅방에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1a57-112">For example, if you set the category's AllowedMembers to contoso.com, you can add any group or user at Contoso as a member to chat rooms in that category.</span></span> <span data-ttu-id="d1a57-113">범주에 허용 되는 구성원을 Sales로 설정한 경우이 메일 그룹의 그룹과 사용자만 구성원으로 추가 하 여 해당 범주의 채팅방을 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1a57-113">If you set the Allowed Members on a category to Sales, only groups and users in this distribution list can be added as members to chat rooms in that category.</span></span> <span data-ttu-id="d1a57-114">작성자 속성을 사용 하 여 해당 범주에서 채팅방을 만들 수 있는 사람을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1a57-114">The Creators property enables you to control who can create chat rooms in that category.</span></span> <span data-ttu-id="d1a57-115">채팅방을 만든 후에는 AllowedMembers 그룹의 모든 사용자를 해당 채팅방에서 진행 중인 관리 작업에 대 한 관리자로 지정할 수 있습니다 (예: 구성원 변경 및 승인).</span><span class="sxs-lookup"><span data-stu-id="d1a57-115">After the chat room is created, anyone from the AllowedMembers group can be designated as a Manager for ongoing management operations on the rooms (for example, membership changes and approval).</span></span>
  
<span data-ttu-id="d1a57-116">범주에 대해 AllowedMembers 및 작성자를 정의 하면 다음과 같은 이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1a57-116">Defining AllowedMembers and Creators for a category has the following benefits:</span></span>
  
- <span data-ttu-id="d1a57-117">이 범주의 모든 채팅방은 범주 수준에 설정 된 제한 사항에 의해 바인딩됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1a57-117">All chat rooms in this category are bound by the restrictions set at the category level.</span></span> <span data-ttu-id="d1a57-118">이 방법을 사용 하 여 비즈니스 요구 및 액세스 정책에 따라 채팅방을 구분할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1a57-118">You can use this to segregate chat rooms based on business need and access policies.</span></span>
    
- <span data-ttu-id="d1a57-119">작성자 목록에 있는 사용자는 해당 범주에 새 채팅방을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1a57-119">A user who is in the Creators list can create new chat rooms in that category.</span></span> <span data-ttu-id="d1a57-120">조직에서 제한 된 인원의 사용자가 채팅방을 만들 수 있는 시스템을 구현 하려는 경우이 컨트롤을 사용 하 여 해당 요구 사항을 충족 시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1a57-120">If you want to implement a system where a restricted number of personnel in the organization can create chat rooms this control can be used to meet that requirements.</span></span> 
    
<span data-ttu-id="d1a57-121">범주에 대 한 작성자로 식별 된 사용자, 조직 구성 단위 (Ou) 및 사용자 그룹은 범주에서 방을 만들 수 있는 개인과 그룹 뿐입니다.</span><span class="sxs-lookup"><span data-stu-id="d1a57-121">Users, Organization Units (OUs), and user groups that are identified as Creators of the category are the only individuals and groups that are allowed to create rooms in the category.</span></span> <span data-ttu-id="d1a57-122">범주를 만든 후에는 범주의 AllowedMembers 목록에서 사용자, Ou 및 사용자 그룹을 선택 하 여 채팅방에 관리 하 고 참여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1a57-122">After the category is created, you can choose users, OUs, and user groups from the category's AllowedMembers list as chat room managers and members to manage and participate in the room.</span></span> 
  
<span data-ttu-id="d1a57-123">범주를 구성 하기 전에 [비즈니스용 Skype 서버 2015의 영구 채팅 범주, 채팅방, 사용자 역할](../../plan-your-deployment/persistent-chat-server/categories-chat-rooms-and-user-roles.md)을 읽어 보세요.</span><span class="sxs-lookup"><span data-stu-id="d1a57-123">Before you configure categories, be sure to read [Persistent chat categories, chat rooms, and user roles in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/categories-chat-rooms-and-user-roles.md).</span></span>
  
<span data-ttu-id="d1a57-124">제어판을 사용 하거나 Windows PowerShell cmdlet을 사용 하 여 범주를 구성 하 고 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1a57-124">You can configure and manage categories by using the Control Panel or by using Windows PowerShell cmdlets.</span></span>

> [!NOTE]
> <span data-ttu-id="d1a57-125">영구 채팅은 비즈니스용 Skype 서버 2015에서 사용할 수 있지만, 비즈니스용 Skype Server 2019에서는 더 이상 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d1a57-125">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="d1a57-126">팀 에서도 동일한 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1a57-126">The same functionality is available in Teams.</span></span> <span data-ttu-id="d1a57-127">자세한 내용은 [Microsoft 팀 업그레이드 시작](/microsoftteams/upgrade-start-here)을 참고 하세요.</span><span class="sxs-lookup"><span data-stu-id="d1a57-127">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="d1a57-128">영구 채팅을 사용 해야 하는 경우에는이 기능이 필요한 사용자를 팀에 마이그레이션하거나 비즈니스용 Skype 서버 2015를 계속 사용 하는 것이 선택 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1a57-128">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 
  
## <a name="configure-categories-by-using-the-control-panel"></a><span data-ttu-id="d1a57-129">제어판을 사용 하 여 범주 구성</span><span class="sxs-lookup"><span data-stu-id="d1a57-129">Configure categories by using the Control Panel</span></span>

1. <span data-ttu-id="d1a57-130">CsPersistentChatAdministrator 또는 CsAdministrator 역할에 지정된 사용자 계정에서 내부 배포의 임의 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="d1a57-130">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="d1a57-131">**시작** 메뉴에서 비즈니스용 Skype 서버 제어판을 선택 하거나 브라우저 창을 연 다음 관리 URL을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1a57-131">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="d1a57-132">왼쪽 탐색 모음에서 **영구 채팅**을 클릭하고 **범주**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d1a57-132">In the left navigation bar, click **Persistent Chat**, and then click **Category**.</span></span>
    
    <span data-ttu-id="d1a57-133">여러 영구 채팅 서버 풀 배포의 경우 드롭다운 목록에서 적절 한 풀을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1a57-133">For multiple Persistent Chat Server pool deployments, select the appropriate pool from the drop-down list.</span></span>
    
4. <span data-ttu-id="d1a57-134">**범주** 페이지에서 **새로 만들기** 또는 **편집**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d1a57-134">On the **Category** page, click **New** or **Edit**.</span></span>
    
5. <span data-ttu-id="d1a57-135">**서비스 선택**에서 범주가 생성 되어야 하는 영구 채팅 서버 풀에 해당 하는 서비스를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1a57-135">In **Select a Service**, select the service corresponding to the Persistent Chat Server pool on which the category needs to be created.</span></span> <span data-ttu-id="d1a57-136">이 서비스는 영구 채팅 클라이언트가 범주가 속해 있는 풀을 식별 하는 데 사용 하는 영구 채팅 서버 풀입니다.</span><span class="sxs-lookup"><span data-stu-id="d1a57-136">The service is the Persistent Chat Server pool that the Persistent Chat client uses to identify which pool the category belongs to.</span></span> <span data-ttu-id="d1a57-137">범주는 하나의 영구 채팅 서버 풀에만 속할 수 있으며 다른 풀로 이동 하거나 공유할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d1a57-137">A category can belong to only one Persistent Chat Server pool, and cannot be moved to, or shared with, another pool.</span></span>
    
6. <span data-ttu-id="d1a57-138">**새 범주**에서 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="d1a57-138">In **New Category**, do the following:</span></span>
    
   - <span data-ttu-id="d1a57-139">**이름**에 새로운 채팅방 범주에 대한 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d1a57-139">In **Name**, specify a name for the new room category.</span></span>
    
   - <span data-ttu-id="d1a57-140">**설명**에 채팅방 범주에 대한 자세한 설명을 제공합니다(예: 한미 교역에 대한 채팅방 범주).</span><span class="sxs-lookup"><span data-stu-id="d1a57-140">In **Description**, provide a detailed description for the room category (for example, a room category for Contoso).</span></span>
    
   - <span data-ttu-id="d1a57-141">이 범주에 속한 채팅방에 대해 초대를 사용할 수 있는지 여부를 제어 하려면 **초대 사용** 확인란을 선택 하거나 선택을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1a57-141">To control whether invitations can be enabled for chat rooms that belong to this category, select or clear the **Enable invitations** check box.</span></span> <span data-ttu-id="d1a57-142">선택 하는 경우이 범주의 채팅방에서 초대를 보내거나 해제할 수 있습니다. 이 확인란을 선택 취소 하면이 범주의 채팅방에서 초대를 할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d1a57-142">If selected, rooms in this category may have invitations on or off; if cleared, the rooms in this category are not allowed to have invitations.</span></span> <span data-ttu-id="d1a57-143">룸에 대 한 초대가 있는 경우 룸에 새 구성원을 추가할 때 영구 채팅 클라이언트에서 새 룸에 대 한 알림을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="d1a57-143">If a room has invitations on, when a new member is added to a room, he or she gets a notification of the new room in their Persistent Chat client.</span></span>
    
   - <span data-ttu-id="d1a57-p109">이 범주에 속하는 채팅방에서 파일 업로드를 제어하려면 **파일 업로드 사용** 확인란을 선택하거나 선택을 취소합니다. 확인란을 선택하면 이 범주의 채팅방에서 파일 업로드를 설정 또는 해제할 수 있으며, 확인란의 선택을 취소하면 이 범주의 채팅방에서 파일 업로드를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d1a57-p109">To control file uploads in chat rooms belonging to this category, select or clear the **Enable file upload** check box. If selected, the rooms of this category can enable or disable file uploads; if cleared, the rooms of this category are not allowed to have file uploads.</span></span>
    
   - <span data-ttu-id="d1a57-146">채팅 기록을 제어 하려면 **채팅 기록 사용** 확인란을 선택 하거나 선택을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1a57-146">To control chat history, select or clear the **Enable chat history** check box.</span></span> <span data-ttu-id="d1a57-147">확인란을 선택하면 채팅방 채팅이 영구적으로 저장되고, 그렇지 않으면 채팅 메시지가 저장되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d1a57-147">If selected, room chats become persistent; otherwise, chat messages are not persisted.</span></span> <span data-ttu-id="d1a57-148">준수 기능이 설정된 경우 채팅방 채팅이 준수 기능으로 저장되지만 사용자가 이전 메시지에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d1a57-148">If compliance is enabled, room chats will be saved in compliance, but users will not be able to access older messages.</span></span> <span data-ttu-id="d1a57-149">이 옵션은 채팅 기록이 필요 하지 않은 실시간 ad hoc 공동 작업에 대해 지정 된 채팅방에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1a57-149">This option can be used for rooms designated for real-time, ad hoc collaborations that don't need chat history to be persisted.</span></span>
    
7. <span data-ttu-id="d1a57-150">**범주 편집**에서 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="d1a57-150">In **Edit Category**, do the following:</span></span>
    
   - <span data-ttu-id="d1a57-151">**구성원 자격**의 허용 된 **구성원** 섹션에서 사용자 및 기타 Active Directory 도메인 서비스 주체 (사용자, 메일 그룹, 조직 구성 단위 등)를 추가 하거나 제거 하 여 범주에 속하는 채팅방의 구성원으로 추가할 수 있도록 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1a57-151">In **Membership**, in the **Allowed members** section, add or remove users and other Active Directory Domain Services principals (users, distribution groups, organizational units, and so on) that are permitted to be added as members of chat rooms belonging to the category.</span></span> <span data-ttu-id="d1a57-152">특정 범주에서 허용된 계정은 채팅방의 구성원만 디렉터리에서 채팅방을 검색할 수 있도록 채팅방이 숨겨져 있지 않은 한 해당 범주에서 채팅방을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1a57-152">Principals permitted by a category can search for the rooms in the category (unless the room is hidden, in which case only members of the room can search for it in the directory).</span></span>
    
   - <span data-ttu-id="d1a57-153">**구성원 자격**의 거부 된 **구성원** 섹션에서 룸에서 거부 되는 구성원과 연결 된 사용자 및 기타 Active Directory 주도자를 추가 하거나 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1a57-153">In **Membership**, in the **Denied members** section, add or remove users and other Active Directory principals associated with members being denied from the room.</span></span>
    
   - <span data-ttu-id="d1a57-154">**멤버 자격**의 **작성자** 섹션에서 해당 범주에 대 한 작성자와 연결 된 사용자 및 기타 Active Directory 보안 주체를 추가 하거나 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1a57-154">In **Membership**, in the **Creators** section, add or remove users and other Active Directory principals associated with creators for the category.</span></span> <span data-ttu-id="d1a57-155">작성자는 채팅방을 만들고 채팅방 관리자 및 구성원을 지정할 권한이 있는 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="d1a57-155">A creator is a user who has permissions to create chat rooms and assign chat room managers and members.</span></span>
    
8. <span data-ttu-id="d1a57-156">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d1a57-156">Click **Commit**.</span></span>
    
## <a name="configure-categories-by-using-windows-powershell"></a><span data-ttu-id="d1a57-157">Windows PowerShell을 사용 하 여 범주 구성</span><span class="sxs-lookup"><span data-stu-id="d1a57-157">Configure categories by using Windows PowerShell</span></span>

<span data-ttu-id="d1a57-158">다음 Windows PowerShell cmdlet을 사용 하 여 범주를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1a57-158">You can configure categories by using the following Windows PowerShell cmdlets:</span></span>
  

|<span data-ttu-id="d1a57-159">**은**</span><span class="sxs-lookup"><span data-stu-id="d1a57-159">**Cmdlet**</span></span>|<span data-ttu-id="d1a57-160">**설명**</span><span class="sxs-lookup"><span data-stu-id="d1a57-160">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d1a57-161">새로운 CsPersistentChatCategory</span><span class="sxs-lookup"><span data-stu-id="d1a57-161">New-CsPersistentChatCategory</span></span>  <br/> |<span data-ttu-id="d1a57-162">새 범주 만들기</span><span class="sxs-lookup"><span data-stu-id="d1a57-162">Create a new category</span></span>  <br/> |
|<span data-ttu-id="d1a57-163">Set-CsPersistentChatCategory</span><span class="sxs-lookup"><span data-stu-id="d1a57-163">Set-CsPersistentChatCategory</span></span>  <br/> |<span data-ttu-id="d1a57-164">기존 범주에 대 한 설정 구성</span><span class="sxs-lookup"><span data-stu-id="d1a57-164">Configure settings for an existing category</span></span>  <br/> |
|<span data-ttu-id="d1a57-165">Get-CsPersistentChatCategory</span><span class="sxs-lookup"><span data-stu-id="d1a57-165">Get-CsPersistentChatCategory</span></span>  <br/> |<span data-ttu-id="d1a57-166">범주에 대 한 정보 검색</span><span class="sxs-lookup"><span data-stu-id="d1a57-166">Retrieve information about categories</span></span>  <br/> |
|<span data-ttu-id="d1a57-167">제거-CsPersistentChatCategory</span><span class="sxs-lookup"><span data-stu-id="d1a57-167">Remove-CsPersistentChatCategory</span></span>  <br/> |<span data-ttu-id="d1a57-168">범주 제거</span><span class="sxs-lookup"><span data-stu-id="d1a57-168">Remove a category</span></span>  <br/> |
   
<span data-ttu-id="d1a57-169">범주에 대해 다음 매개 변수를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1a57-169">You can configure the following parameters for categories:</span></span>
  
- <span data-ttu-id="d1a57-170">EnableFileUpload.</span><span class="sxs-lookup"><span data-stu-id="d1a57-170">EnableFileUpload.</span></span> <span data-ttu-id="d1a57-171">범주에 있는 채팅방에 파일 업로드를 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1a57-171">Allows file uploads to the chat rooms in the category.</span></span>
    
- <span data-ttu-id="d1a57-172">초대장을 EnableInvitations</span><span class="sxs-lookup"><span data-stu-id="d1a57-172">EnableInvitations.</span></span> <span data-ttu-id="d1a57-173">범주에 대 한 초대를 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1a57-173">Enables invitations for the category.</span></span> <span data-ttu-id="d1a57-174">AllowedMembers 목록의 사용자는 새 채팅방을 만들 때 새 채팅방에 참가 하기 위한 초대를 자동으로 받습니다.</span><span class="sxs-lookup"><span data-stu-id="d1a57-174">Users on the AllowedMembers list will automatically receive an invitation to join a new chat room at the time the new room is created.</span></span>
    
- <span data-ttu-id="d1a57-175">ChatHistory.</span><span class="sxs-lookup"><span data-stu-id="d1a57-175">ChatHistory.</span></span> <span data-ttu-id="d1a57-176">채팅 기록 기능을 사용 하거나 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1a57-176">Enables or disables the chat history feature.</span></span>
    
- <span data-ttu-id="d1a57-177">제작자.</span><span class="sxs-lookup"><span data-stu-id="d1a57-177">Creators.</span></span> <span data-ttu-id="d1a57-178">범주 내에서 채팅방을 만들 수 있는 사용자를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1a57-178">Specifies the users who are allowed to create chat rooms within the category.</span></span>
    
- <span data-ttu-id="d1a57-179">AllowedMembers.</span><span class="sxs-lookup"><span data-stu-id="d1a57-179">AllowedMembers.</span></span> <span data-ttu-id="d1a57-180">범주 내에서 채팅방에 액세스할 수 있는 사용자를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1a57-180">Specifies the users who are allowed to access chat rooms within the category.</span></span>
    
- <span data-ttu-id="d1a57-181">DeniedMembers.</span><span class="sxs-lookup"><span data-stu-id="d1a57-181">DeniedMembers.</span></span> <span data-ttu-id="d1a57-182">범주 내에서 채팅방에 액세스할 수 없는 사용자를 나열 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1a57-182">Lists the users who are not allowed to access chat rooms within the category.</span></span>
    
<span data-ttu-id="d1a57-183">모든 매개 변수를 포함 하 여 cmdlet 구문에 대 한 자세한 내용은 비즈니스용 [Skype Server 2015 관리 셸을](../management-shell.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d1a57-183">For complete information about cmdlet syntax, including all parameters, see [Skype for Business Server 2015 Management Shell](../management-shell.md).</span></span>
  
### <a name="create-a-new-category"></a><span data-ttu-id="d1a57-184">새 범주 만들기</span><span class="sxs-lookup"><span data-stu-id="d1a57-184">Create a new category</span></span>

<span data-ttu-id="d1a57-185">**새 CsPersistentChatCategory** cmdlet을 사용 하 여 새 범주를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1a57-185">You can create a new category by using the **New-CsPersistentChatCategory** cmdlet.</span></span> <span data-ttu-id="d1a57-186">예를 들어 다음 명령은 풀 atl-cs-001.contoso.com에 기술 지원팀 이라는 새 범주를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d1a57-186">For example, the following command creates a new category named HelpDesk on the pool atl-cs-001.contoso.com.</span></span> <span data-ttu-id="d1a57-187">이 예제에서는 파일 업로드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1a57-187">In this example, file upload is enabled:</span></span>
  
```PowerShell
New-CsPersistentChatCategory -Name "HelpDesk" -PersistentChatPoolFqdn "atl-cs-001.contoso.com" -EnableFileUpload 
```

### <a name="configure-an-existing-category"></a><span data-ttu-id="d1a57-188">기존 범주 구성</span><span class="sxs-lookup"><span data-stu-id="d1a57-188">Configure an existing category</span></span>

<span data-ttu-id="d1a57-189">**Set-CsPersistentCategory** cmdlet을 사용 하 여 기존 범주를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1a57-189">You can configure an existing category by using the **Set-CsPersistentCategory** cmdlet.</span></span>
  
<span data-ttu-id="d1a57-190">예를 들어 다음 명령은 user1이 AllowedMember이 고 작성자 인 반면, %2은 (는) 범주에 있는 채팅방에 대 한 액세스를 거부 하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1a57-190">For example, the following command specifies that user1 is an AllowedMember and a Creator, while user2 is denied access to the rooms in the category:</span></span>
  
```PowerShell
Set-CsPersistentChatCategory -Identity testCat -AllowedMembers @{Add="sip:user1@contoso.com", "CN=container,DC=contoso,DC=com"}  -DeniedMembers @{Add="sip:user2@contoso.com"}
Set-CsPersistentChatCategory -Identity testCat -Creators @{Add="sip:user1@contoso.com"}
```

### <a name="get-information-about-categories"></a><span data-ttu-id="d1a57-191">범주에 대 한 정보 가져오기</span><span class="sxs-lookup"><span data-stu-id="d1a57-191">Get information about categories</span></span>

<span data-ttu-id="d1a57-192">**CsPersistentChatCategory** cmdlet을 사용 하 여 범주에 대 한 정보를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1a57-192">You can get information about categories by using the **Get-CsPersistentChatCategory** cmdlet.</span></span> <span data-ttu-id="d1a57-193">예를 들어 다음 명령은 조직의 모든 영구 채팅 범주에 대 한 정보를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1a57-193">For example, the following command returns information for all the Persistent Chat categories in the organization:</span></span>
  
```PowerShell
Get-CsPersistentChatCategory
```

### <a name="remove-a-category"></a><span data-ttu-id="d1a57-194">범주 제거</span><span class="sxs-lookup"><span data-stu-id="d1a57-194">Remove a category</span></span>

<span data-ttu-id="d1a57-195">**제거-CsPersistentChatCategory** cmdlet을 사용 하 여 범주를 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1a57-195">You can remove a category by using the **Remove-CsPersistentChatCategory** cmdlet.</span></span> <span data-ttu-id="d1a57-196">범주를 제거 하기 전에 먼저 모든 채팅방을 삭제 하거나 채팅방을 새 범주로 이동 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1a57-196">Before removing a category, you must first either delete all chat rooms under it or move the chat rooms to a new category.</span></span> <span data-ttu-id="d1a57-197">예를 들어 다음 명령을 실행 하면 "atl-cs-001-com\helpdesk" 라는 Id를 가진 범주가 제거 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1a57-197">For example, the following command removes the category that has the Identity "atl-cs-001.contoso.com\helpdesk":</span></span>
  
```PowerShell
Remove-CsPersistentChatCategory -Identity "atl-cs-001.contoso.com\helpdesk"
```
