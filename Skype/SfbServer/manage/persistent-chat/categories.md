---
title: 영구 채팅 서버에서 비즈니스용 Skype 서버 2015의 범주 관리
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 1/31/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b0c834b9-b5c8-41d5-865b-c8b180e76d13
description: '요약: 비즈니스용 Skype 서버 2015에서 영구 채팅 서버 범주를 관리하는 방법을 설명하는 문서입니다.'
ms.openlocfilehash: 648629e42994c59f5d6ba5ee5592729f4dff0bbe
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815128"
---
# <a name="manage-categories-in-persistent-chat-server-in-skype-for-business-server-2015"></a><span data-ttu-id="d1875-103">영구 채팅 서버에서 비즈니스용 Skype 서버 2015의 범주 관리</span><span class="sxs-lookup"><span data-stu-id="d1875-103">Manage categories in Persistent Chat Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="d1875-104">**요약:** 비즈니스용 Skype 서버 2015에서 영구 채팅 서버 범주를 관리하는 방법을 자세히 알아보고,</span><span class="sxs-lookup"><span data-stu-id="d1875-104">**Summary:** Learn how to manage Persistent Chat Server categories in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="d1875-105">범주는 채팅방을 구성하기 위한 논리 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="d1875-105">A category is a logical structure for organizing chat rooms.</span></span> <span data-ttu-id="d1875-106">범주는 채팅방을 만들거나 참가할 수 있는 사용자 및 사용자 그룹을 제어하기 위한 기본 ACL(액세스 제어 목록) 집합을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="d1875-106">A category defines a default set of access control lists (ACLs) for controlling the users and user groups who can create or join the chat rooms.</span></span> <span data-ttu-id="d1875-107">채팅방 범주에는 채팅방이 포함되지만 다른 범주는 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d1875-107">Chat room categories contain chat rooms, but not other categories.</span></span> <span data-ttu-id="d1875-108">각 범주는 이름, 설명 등의 메타데이터로 해당 콘텐츠를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d1875-108">Each category describes its contents with metadata, such as Name and Description.</span></span> <span data-ttu-id="d1875-109">범주에는 범주에 속한 채팅방의 동작을 제어하기 위해 설정할 수 있는 속성이 있습니다. 예를 들어 채팅방에서 초대 또는 파일 업로드를 허용하는지 또는 채팅 기록을 포함할지 여부</span><span class="sxs-lookup"><span data-stu-id="d1875-109">The category has properties that can be set to control the behavior of the chat rooms belonging to it; for example, whether the chat rooms allow Invitations or File Uploads, or contain Chat History.</span></span> 
  
<span data-ttu-id="d1875-110">범주를 올바르게 사용하여 채팅방을 만들고 관리하는 것이 훨씬 더 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="d1875-110">Creating and managing chat rooms is much easier with the correct use of categories.</span></span> <span data-ttu-id="d1875-111">영구 채팅 서버 관리자는 각 범주에 대해 AllowedMembers 및 Creators를 정의하고 범주에서 만든 모든 채팅방에 적용할 기본 채팅방 설정 및 동작을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1875-111">As a Persistent Chat Server administrator, you can define AllowedMembers and Creators for each category, and also define the default chat room settings and behaviors that will be applied to all chat rooms created in the category.</span></span> <span data-ttu-id="d1875-112">예를 들어 범주의 AllowedMembers를 contoso.com 범주의 채팅방에 구성원으로 Contoso의 그룹 또는 사용자를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1875-112">For example, if you set the category's AllowedMembers to contoso.com, you can add any group or user at Contoso as a member to chat rooms in that category.</span></span> <span data-ttu-id="d1875-113">범주의 허용 구성원을 Sales로 설정하면 이 메일 그룹의 그룹 및 사용자만 해당 범주의 채팅방에 구성원으로 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1875-113">If you set the Allowed Members on a category to Sales, only groups and users in this distribution list can be added as members to chat rooms in that category.</span></span> <span data-ttu-id="d1875-114">Creators 속성을 사용하면 해당 범주에서 대화방을 만들 수 있는 대상을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1875-114">The Creators property enables you to control who can create chat rooms in that category.</span></span> <span data-ttu-id="d1875-115">채팅방을 만든 후 AllowedMembers 그룹의 모든 사용자가 채팅방에서 진행되는 관리 작업(예: 구성원 변경 및 승인)에 대한 관리자로 지정될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1875-115">After the chat room is created, anyone from the AllowedMembers group can be designated as a Manager for ongoing management operations on the rooms (for example, membership changes and approval).</span></span>
  
<span data-ttu-id="d1875-116">범주에 대해 AllowedMembers 및 Creators를 정의하면 다음과 같은 이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1875-116">Defining AllowedMembers and Creators for a category has the following benefits:</span></span>
  
- <span data-ttu-id="d1875-117">이 범주의 모든 대화방은 범주 수준에서 설정된 제한에 의해 바인딩됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1875-117">All chat rooms in this category are bound by the restrictions set at the category level.</span></span> <span data-ttu-id="d1875-118">이를 사용하여 비즈니스 필요 및 액세스 정책에 따라 채팅방을 나누는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1875-118">You can use this to segregate chat rooms based on business need and access policies.</span></span>
    
- <span data-ttu-id="d1875-119">크리에이터스 목록에 있는 사용자는 해당 범주에 새 대화방을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1875-119">A user who is in the Creators list can create new chat rooms in that category.</span></span> <span data-ttu-id="d1875-120">조직의 제한된 수의 직원이 채팅방을 만들 수 있는 시스템을 구현하려는 경우 이 컨트롤을 사용하여 해당 요구 사항을 충족할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1875-120">If you want to implement a system where a restricted number of personnel in the organization can create chat rooms this control can be used to meet that requirements.</span></span> 
    
<span data-ttu-id="d1875-121">범주의 작성자로 식별되는 사용자, US(조직 구성 단위) 및 사용자 그룹은 범주에 방을 만들 수 있는 개인 및 그룹뿐입니다.</span><span class="sxs-lookup"><span data-stu-id="d1875-121">Users, Organization Units (OUs), and user groups that are identified as Creators of the category are the only individuals and groups that are allowed to create rooms in the category.</span></span> <span data-ttu-id="d1875-122">범주를 만든 후 범주의 AllowedMembers 목록에서 사용자, US 및 사용자 그룹을 채팅방 관리자 및 구성원으로 선택하여 채팅방을 관리하고 채팅방에 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1875-122">After the category is created, you can choose users, OUs, and user groups from the category's AllowedMembers list as chat room managers and members to manage and participate in the room.</span></span> 
  
<span data-ttu-id="d1875-123">범주를 구성하기 전에 비즈니스용 Skype 서버 [2015에서](../../plan-your-deployment/persistent-chat-server/categories-chat-rooms-and-user-roles.md)영구 채팅 범주, 채팅방 및 사용자 역할을 읽어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1875-123">Before you configure categories, be sure to read [Persistent chat categories, chat rooms, and user roles in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/categories-chat-rooms-and-user-roles.md).</span></span>
  
<span data-ttu-id="d1875-124">제어판을 사용하거나 cmdlet을 사용하여 범주를 구성하고 관리할 Windows PowerShell 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1875-124">You can configure and manage categories by using the Control Panel or by using Windows PowerShell cmdlets.</span></span>

> [!NOTE]
> <span data-ttu-id="d1875-125">영구 채팅은 비즈니스용 Skype 서버 2015에서 사용할 수 있지만 비즈니스용 Skype 서버 2019에서 더 이상 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d1875-125">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="d1875-126">Teams에서 동일한 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1875-126">The same functionality is available in Teams.</span></span> <span data-ttu-id="d1875-127">자세한 내용은 Microsoft Teams 업그레이드 시작을 [참조하세요.](/microsoftteams/upgrade-start-here)</span><span class="sxs-lookup"><span data-stu-id="d1875-127">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="d1875-128">영구 채팅을 사용하려면 이 기능이 필요한 사용자를 Teams로 마이그레이션하거나 비즈니스용 Skype 서버 2015를 계속 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1875-128">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 
  
## <a name="configure-categories-by-using-the-control-panel"></a><span data-ttu-id="d1875-129">제어판을 사용하여 범주 구성</span><span class="sxs-lookup"><span data-stu-id="d1875-129">Configure categories by using the Control Panel</span></span>

1. <span data-ttu-id="d1875-130">CsPersistentChatAdministrator 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="d1875-130">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="d1875-131">시작 **메뉴에서** 비즈니스용 Skype 서버 제어판을 선택하거나 브라우저 창을 연 다음 관리 URL을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="d1875-131">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="d1875-132">왼쪽 탐색 모음에서 **영구 채팅** 을 클릭하고 **범주** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d1875-132">In the left navigation bar, click **Persistent Chat**, and then click **Category**.</span></span>
    
    <span data-ttu-id="d1875-133">여러 영구 채팅 서버 풀 배포의 경우 드롭다운 목록에서 적절한 풀을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d1875-133">For multiple Persistent Chat Server pool deployments, select the appropriate pool from the drop-down list.</span></span>
    
4. <span data-ttu-id="d1875-134">**범주** 페이지에서 **새로 만들기** 또는 **편집** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d1875-134">On the **Category** page, click **New** or **Edit**.</span></span>
    
5. <span data-ttu-id="d1875-135">서비스 **선택에서** 범주를 만들어야 하는 영구 채팅 서버 풀에 해당하는 서비스를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d1875-135">In **Select a Service**, select the service corresponding to the Persistent Chat Server pool on which the category needs to be created.</span></span> <span data-ttu-id="d1875-136">이 서비스는 영구 채팅 클라이언트가 범주가 속하는 풀을 식별하는 데 사용하는 영구 채팅 서버 풀입니다.</span><span class="sxs-lookup"><span data-stu-id="d1875-136">The service is the Persistent Chat Server pool that the Persistent Chat client uses to identify which pool the category belongs to.</span></span> <span data-ttu-id="d1875-137">범주는 하나의 영구 채팅 서버 풀에만 속할 수 있으며 다른 풀로 이동하거나 공유할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d1875-137">A category can belong to only one Persistent Chat Server pool, and cannot be moved to, or shared with, another pool.</span></span>
    
6. <span data-ttu-id="d1875-138">**새 범주** 에서 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="d1875-138">In **New Category**, do the following:</span></span>
    
   - <span data-ttu-id="d1875-139">**이름** 에서 새 방 범주의 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d1875-139">In **Name**, specify a name for the new room category.</span></span>
    
   - <span data-ttu-id="d1875-140">**설명** 에서 방 범주의 자세한 설명을 입력합니다(예: Contoso의 방 범주).</span><span class="sxs-lookup"><span data-stu-id="d1875-140">In **Description**, provide a detailed description for the room category (for example, a room category for Contoso).</span></span>
    
   - <span data-ttu-id="d1875-141">이 범주에 속하는 대화방에 대해 초대를 사용하도록 설정할 수 있는지 여부를 제어하려면 초대 사용 확인란을 선택하거나 **선택을** 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="d1875-141">To control whether invitations can be enabled for chat rooms that belong to this category, select or clear the **Enable invitations** check box.</span></span> <span data-ttu-id="d1875-142">이 옵션을 선택하면 이 범주의 방에 초대가 있을 수 있습니다. 선택을 취소하면 이 범주의 방에 초대가 허용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d1875-142">If selected, rooms in this category may have invitations on or off; if cleared, the rooms in this category are not allowed to have invitations.</span></span> <span data-ttu-id="d1875-143">대화방에 초대가 있는 경우 새 구성원이 채팅방에 추가되면 영구 채팅 클라이언트에서 새 채팅방에 대한 알림이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1875-143">If a room has invitations on, when a new member is added to a room, he or she gets a notification of the new room in their Persistent Chat client.</span></span>
    
   - <span data-ttu-id="d1875-p109">해당 범주에 속하는 채팅방에서 파일 업로드를 제어하려면 **파일 업로드 사용** 확인란을 선택하거나 선택을 취소합니다. 이 확인란을 선택하는 경우 해당 범주의 방에서 파일 업로드를 사용하거나 사용하지 않도록 설정할 수 있습니다. 이 확인란의 선택을 취소하는 경우에는 해당 범주의 방에서 파일을 업로드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d1875-p109">To control file uploads in chat rooms belonging to this category, select or clear the **Enable file upload** check box. If selected, the rooms of this category can enable or disable file uploads; if cleared, the rooms of this category are not allowed to have file uploads.</span></span>
    
   - <span data-ttu-id="d1875-146">채팅 기록을 제어하려면 채팅 기록 사용 확인란을 **선택하거나** 선택을 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="d1875-146">To control chat history, select or clear the **Enable chat history** check box.</span></span> <span data-ttu-id="d1875-147">이 확인란을 선택하는 경우 방의 채팅 내용이 영구적으로 보존되고, 그렇지 않으면 채팅 메시지가 영구적으로 보존되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d1875-147">If selected, room chats become persistent; otherwise, chat messages are not persisted.</span></span> <span data-ttu-id="d1875-148">준수를 사용하도록 설정한 경우에는 방의 채팅 내용이 준수에 저장되지만 사용자는 이전 메시지에 액세스할 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1875-148">If compliance is enabled, room chats will be saved in compliance, but users will not be able to access older messages.</span></span> <span data-ttu-id="d1875-149">이 옵션은 채팅 기록을 영구적으로 유지하지 않는 실시간 애드워크 공동 작업으로 지정된 채팅방에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1875-149">This option can be used for rooms designated for real-time, ad hoc collaborations that don't need chat history to be persisted.</span></span>
    
7. <span data-ttu-id="d1875-150">**범주 편집** 에서 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="d1875-150">In **Edit Category**, do the following:</span></span>
    
   - <span data-ttu-id="d1875-151">구성원 자격의  허용 구성원 섹션에서 범주에 속하는 채팅방의 구성원으로 추가할 수 있는 사용자 및 기타 Active Directory 도메인 서비스 계정(사용자, 메일 그룹, 조직 구성 단위 등)을 추가하거나 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="d1875-151">In **Membership**, in the **Allowed members** section, add or remove users and other Active Directory Domain Services principals (users, distribution groups, organizational units, and so on) that are permitted to be added as members of chat rooms belonging to the category.</span></span> <span data-ttu-id="d1875-152">특정 범주에서 허용된 계정은 방의 구성원만 디렉터리에서 방을 검색할 수 있도록 방이 숨겨져 있지 않은 한 해당 범주에서 방을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1875-152">Principals permitted by a category can search for the rooms in the category (unless the room is hidden, in which case only members of the room can search for it in the directory).</span></span>
    
   - <span data-ttu-id="d1875-153">구성원 **자격의** **거부된** 구성원 섹션에서 방에서 거부된 구성원과 관련된 사용자 및 기타 Active Directory 사용자를 추가하거나 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="d1875-153">In **Membership**, in the **Denied members** section, add or remove users and other Active Directory principals associated with members being denied from the room.</span></span>
    
   - <span data-ttu-id="d1875-154">멤버 **자격의** **크리에이터스 섹션에서** 범주의 작성자와 연결된 사용자 및 기타 Active Directory 사용자를 추가하거나 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="d1875-154">In **Membership**, in the **Creators** section, add or remove users and other Active Directory principals associated with creators for the category.</span></span> <span data-ttu-id="d1875-155">작성자는 채팅방을 만들고 채팅방 관리자 및 구성원을 할당할 권한이 있는 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="d1875-155">A creator is a user who has permissions to create chat rooms and assign chat room managers and members.</span></span>
    
8. <span data-ttu-id="d1875-156">**커밋** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d1875-156">Click **Commit**.</span></span>
    
## <a name="configure-categories-by-using-windows-powershell"></a><span data-ttu-id="d1875-157">다음을 사용하여 범주를 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d1875-157">Configure categories by using Windows PowerShell</span></span>

<span data-ttu-id="d1875-158">다음 cmdlet을 사용하여 범주를 Windows PowerShell 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1875-158">You can configure categories by using the following Windows PowerShell cmdlets:</span></span>
  

|<span data-ttu-id="d1875-159">**Cmdlet**</span><span class="sxs-lookup"><span data-stu-id="d1875-159">**Cmdlet**</span></span>|<span data-ttu-id="d1875-160">**설명**</span><span class="sxs-lookup"><span data-stu-id="d1875-160">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d1875-161">New-CsPersistentChatCategory</span><span class="sxs-lookup"><span data-stu-id="d1875-161">New-CsPersistentChatCategory</span></span>  <br/> |<span data-ttu-id="d1875-162">새 범주 만들기</span><span class="sxs-lookup"><span data-stu-id="d1875-162">Create a new category</span></span>  <br/> |
|<span data-ttu-id="d1875-163">Set-CsPersistentChatCategory</span><span class="sxs-lookup"><span data-stu-id="d1875-163">Set-CsPersistentChatCategory</span></span>  <br/> |<span data-ttu-id="d1875-164">기존 범주에 대한 설정 구성</span><span class="sxs-lookup"><span data-stu-id="d1875-164">Configure settings for an existing category</span></span>  <br/> |
|<span data-ttu-id="d1875-165">Get-CsPersistentChatCategory</span><span class="sxs-lookup"><span data-stu-id="d1875-165">Get-CsPersistentChatCategory</span></span>  <br/> |<span data-ttu-id="d1875-166">범주에 대한 정보 검색</span><span class="sxs-lookup"><span data-stu-id="d1875-166">Retrieve information about categories</span></span>  <br/> |
|<span data-ttu-id="d1875-167">Remove-CsPersistentChatCategory</span><span class="sxs-lookup"><span data-stu-id="d1875-167">Remove-CsPersistentChatCategory</span></span>  <br/> |<span data-ttu-id="d1875-168">범주 제거</span><span class="sxs-lookup"><span data-stu-id="d1875-168">Remove a category</span></span>  <br/> |
   
<span data-ttu-id="d1875-169">범주에 대해 다음 매개 변수를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1875-169">You can configure the following parameters for categories:</span></span>
  
- <span data-ttu-id="d1875-170">EnableFileUpload.</span><span class="sxs-lookup"><span data-stu-id="d1875-170">EnableFileUpload.</span></span> <span data-ttu-id="d1875-171">범주의 채팅방에 파일 업로드를 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="d1875-171">Allows file uploads to the chat rooms in the category.</span></span>
    
- <span data-ttu-id="d1875-172">EnableInvitations.</span><span class="sxs-lookup"><span data-stu-id="d1875-172">EnableInvitations.</span></span> <span data-ttu-id="d1875-173">범주에 대한 초대를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1875-173">Enables invitations for the category.</span></span> <span data-ttu-id="d1875-174">AllowedMembers 목록의 사용자는 새 채팅방을 만들 때 새 채팅방에 참가하는 초대를 자동으로 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1875-174">Users on the AllowedMembers list will automatically receive an invitation to join a new chat room at the time the new room is created.</span></span>
    
- <span data-ttu-id="d1875-175">ChatHistory.</span><span class="sxs-lookup"><span data-stu-id="d1875-175">ChatHistory.</span></span> <span data-ttu-id="d1875-176">채팅 기록 기능을 활성화 또는 비활성화합니다.</span><span class="sxs-lookup"><span data-stu-id="d1875-176">Enables or disables the chat history feature.</span></span>
    
- <span data-ttu-id="d1875-177">작성자.</span><span class="sxs-lookup"><span data-stu-id="d1875-177">Creators.</span></span> <span data-ttu-id="d1875-178">범주 내에서 채팅방을 만들 수 있는 사용자를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d1875-178">Specifies the users who are allowed to create chat rooms within the category.</span></span>
    
- <span data-ttu-id="d1875-179">AllowedMembers.</span><span class="sxs-lookup"><span data-stu-id="d1875-179">AllowedMembers.</span></span> <span data-ttu-id="d1875-180">범주 내에서 대화방에 액세스할 수 있는 사용자를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d1875-180">Specifies the users who are allowed to access chat rooms within the category.</span></span>
    
- <span data-ttu-id="d1875-181">DeniedMembers.</span><span class="sxs-lookup"><span data-stu-id="d1875-181">DeniedMembers.</span></span> <span data-ttu-id="d1875-182">범주 내에서 채팅방에 액세스할 수 없는 사용자를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="d1875-182">Lists the users who are not allowed to access chat rooms within the category.</span></span>
    
<span data-ttu-id="d1875-183">모든 매개 변수를 포함하여 cmdlet 구문에 대한 자세한 내용은 [비즈니스용 Skype 서버 2015 관리 셸을 참조하세요.](../management-shell.md)</span><span class="sxs-lookup"><span data-stu-id="d1875-183">For complete information about cmdlet syntax, including all parameters, see [Skype for Business Server 2015 Management Shell](../management-shell.md).</span></span>
  
### <a name="create-a-new-category"></a><span data-ttu-id="d1875-184">새 범주 만들기</span><span class="sxs-lookup"><span data-stu-id="d1875-184">Create a new category</span></span>

<span data-ttu-id="d1875-185">**New-CsPersistentChatCategory** cmdlet을 사용하여 새 범주를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1875-185">You can create a new category by using the **New-CsPersistentChatCategory** cmdlet.</span></span> <span data-ttu-id="d1875-186">예를 들어 다음 명령은 풀 이름에 HelpDesk라는 새 범주를 atl-cs-001.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="d1875-186">For example, the following command creates a new category named HelpDesk on the pool atl-cs-001.contoso.com.</span></span> <span data-ttu-id="d1875-187">이 예제에서는 파일 업로드를 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="d1875-187">In this example, file upload is enabled:</span></span>
  
```PowerShell
New-CsPersistentChatCategory -Name "HelpDesk" -PersistentChatPoolFqdn "atl-cs-001.contoso.com" -EnableFileUpload 
```

### <a name="configure-an-existing-category"></a><span data-ttu-id="d1875-188">기존 범주 구성</span><span class="sxs-lookup"><span data-stu-id="d1875-188">Configure an existing category</span></span>

<span data-ttu-id="d1875-189">**Set-CsPersistentCategory** cmdlet을 사용하여 기존 범주를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1875-189">You can configure an existing category by using the **Set-CsPersistentCategory** cmdlet.</span></span>
  
<span data-ttu-id="d1875-190">예를 들어 다음 명령은 user1이 AllowedMember 및 Creator이고 user2는 범주의 방에 대한 액세스가 거부됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1875-190">For example, the following command specifies that user1 is an AllowedMember and a Creator, while user2 is denied access to the rooms in the category:</span></span>
  
```PowerShell
Set-CsPersistentChatCategory -Identity testCat -AllowedMembers @{Add="sip:user1@contoso.com", "CN=container,DC=contoso,DC=com"}  -DeniedMembers @{Add="sip:user2@contoso.com"}
Set-CsPersistentChatCategory -Identity testCat -Creators @{Add="sip:user1@contoso.com"}
```

### <a name="get-information-about-categories"></a><span data-ttu-id="d1875-191">범주에 대한 정보 얻기</span><span class="sxs-lookup"><span data-stu-id="d1875-191">Get information about categories</span></span>

<span data-ttu-id="d1875-192">**Get-CsPersistentChatCategory** cmdlet을 사용하여 범주에 대한 정보를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1875-192">You can get information about categories by using the **Get-CsPersistentChatCategory** cmdlet.</span></span> <span data-ttu-id="d1875-193">예를 들어 다음 명령은 조직의 모든 영구 채팅 범주에 대한 정보를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="d1875-193">For example, the following command returns information for all the Persistent Chat categories in the organization:</span></span>
  
```PowerShell
Get-CsPersistentChatCategory
```

### <a name="remove-a-category"></a><span data-ttu-id="d1875-194">범주 제거</span><span class="sxs-lookup"><span data-stu-id="d1875-194">Remove a category</span></span>

<span data-ttu-id="d1875-195">**Remove-CsPersistentChatCategory** cmdlet을 사용하여 범주를 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1875-195">You can remove a category by using the **Remove-CsPersistentChatCategory** cmdlet.</span></span> <span data-ttu-id="d1875-196">범주를 제거하기 전에 먼저 범주 아래에 있는 모든 채팅방을 삭제하거나 채팅방을 새 범주로 이동해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1875-196">Before removing a category, you must first either delete all chat rooms under it or move the chat rooms to a new category.</span></span> <span data-ttu-id="d1875-197">예를 들어 다음 명령은 ID가 "atl-cs-001.contoso.com\helpdesk"인 범주를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="d1875-197">For example, the following command removes the category that has the Identity "atl-cs-001.contoso.com\helpdesk":</span></span>
  
```PowerShell
Remove-CsPersistentChatCategory -Identity "atl-cs-001.contoso.com\helpdesk"
```
