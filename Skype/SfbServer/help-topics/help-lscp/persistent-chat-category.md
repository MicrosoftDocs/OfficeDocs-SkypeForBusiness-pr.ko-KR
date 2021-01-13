---
title: 영구 채팅 범주
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
- ms.lync.lscp.PersistentChatCategory
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6875d930-7502-4e47-bdb3-45eaeb065350
description: 영구 채팅 페이지의 범주 섹션을 사용하여 범주를 구성할 수 있습니다. 영구 채팅방 범주는 채팅방을 구성하기 위한 논리 구조입니다. 범주는 채팅방을 만들거나 채팅방에 참가할 수 있는 사용자 및 사용자 그룹을 제어하기 위한 기본 ACL(액세스 제어 목록) 집합을 정의합니다. 범주를 사용하여 조직 내의 개별 하위 부문 간에 교신 차단 영역을 적용할 수 있습니다.
ms.openlocfilehash: f7718a5d6cc92c0036f28843d21c4c349c0bc38d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49803748"
---
# <a name="persistent-chat-category"></a><span data-ttu-id="c82c8-106">영구 채팅 범주</span><span class="sxs-lookup"><span data-stu-id="c82c8-106">Persistent Chat Category</span></span>
 
<span data-ttu-id="c82c8-107">영구 채팅 페이지의 **범주**  섹션을 사용하여 범주를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c82c8-107">You can use the **Category** section of the **Persistent Chat** page to configure categories.</span></span> <span data-ttu-id="c82c8-108">영구 채팅방 범주는 채팅방을 구성하기 위한 논리 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="c82c8-108">A Persistent Chat room category is a logical structure for organizing chat rooms.</span></span> <span data-ttu-id="c82c8-109">범주는 채팅방을 만들거나 채팅방에 참가할 수 있는 사용자 및 사용자 그룹을 제어하기 위한 기본 ACL(액세스 제어 목록) 집합을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="c82c8-109">A category defines a default set of access control lists (ACLs) for controlling the users and user groups who may create or join the chat rooms.</span></span> <span data-ttu-id="c82c8-110">범주를 사용하여 조직 내의 개별 하위 부문 간에 교신 차단 영역을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c82c8-110">You can use categories enforce ethical walls between different subdivisions within their organizations.</span></span>
  
<span data-ttu-id="c82c8-111">채팅방 범주는 채팅방은 포함할 수 있지만 다른 범주는 포함할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c82c8-111">Chat room categories may contain chat rooms, but not other categories.</span></span> <span data-ttu-id="c82c8-112">각 범주는 이름 및 설명과 같은 메타데이터를 사용하여 해당 _콘텐츠를_ _설명합니다._</span><span class="sxs-lookup"><span data-stu-id="c82c8-112">Each category describes its contents with metadata, such as  _Name_ and _Description_.</span></span> <span data-ttu-id="c82c8-113">또한 범주에는 채팅방에서 초대 또는 파일 업로드를 허용하거나 채팅 기록을 포함하는 경우와  같이 범주에 속한 채팅방의 동작을 제어하도록 설정할 수 있는 속성이 _있습니다._ </span><span class="sxs-lookup"><span data-stu-id="c82c8-113">In addition, the category has properties which can be set to control the behavior of the chat rooms belonging to it, such as if the chat rooms allow  _Invitations_ or _File Uploads_, or contain  _Chat History_.</span></span>
  
<span data-ttu-id="c82c8-114">새 범주를 만들 경우 영구 채팅 서버의 범주 [관리(비즈니스용 Skype 서버 2015)를 참조하세요.](../../manage/persistent-chat/categories.md)</span><span class="sxs-lookup"><span data-stu-id="c82c8-114">To create a new category, see [Manage categories in Persistent Chat Server in Skype for Business Server 2015](../../manage/persistent-chat/categories.md).</span></span> <span data-ttu-id="c82c8-115">영구 채팅 관리자인 경우 제어판 또는 cmdlet을 사용하여 범주를 Windows PowerShell 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c82c8-115">If you are a Persistent Chat Administrator, you can create categories by using the control panel or Windows PowerShell cmdlets.</span></span>
  
## <a name="tasks-that-you-can-perform"></a><span data-ttu-id="c82c8-116">수행할 수 있는 작업</span><span class="sxs-lookup"><span data-stu-id="c82c8-116">Tasks that you can perform</span></span>

<span data-ttu-id="c82c8-117">**범주** 페이지에서는 다음 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c82c8-117">You can perform the following tasks on the **Category** page:</span></span>
  
- <span data-ttu-id="c82c8-118">새 범주 만들기 또는 편집</span><span class="sxs-lookup"><span data-stu-id="c82c8-118">Create or edit a new category</span></span>
    
- <span data-ttu-id="c82c8-119">범주별로 대화방 이동</span><span class="sxs-lookup"><span data-stu-id="c82c8-119">Move a chat room from one category to another</span></span>
    
- <span data-ttu-id="c82c8-120">채팅방 또는 범주 삭제</span><span class="sxs-lookup"><span data-stu-id="c82c8-120">Delete a chat room or category</span></span>
    
## <a name="to-configure-categories-for-chat-rooms"></a><span data-ttu-id="c82c8-121">채팅방에 대한 범주를 구성하려면</span><span class="sxs-lookup"><span data-stu-id="c82c8-121">To configure categories for chat rooms</span></span>

1. <span data-ttu-id="c82c8-122">CsPersistentChatAdministrator 또는 CsAdministrator 역할에 지정된 사용자 계정에서 내부 배포의 임의 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="c82c8-122">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="c82c8-123">시작 **메뉴에서** 비즈니스용 Skype 서버 제어판을 선택하거나 브라우저 창을 연 다음 관리 URL을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="c82c8-123">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="c82c8-124">왼쪽 탐색 모음에서 **영구 채팅** 을 클릭하고 **범주** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c82c8-124">In the left navigation bar, click **Persistent Chat**, and then click **Category**.</span></span>
    
    <span data-ttu-id="c82c8-125">여러 영구 채팅 서버 풀 배포의 경우 드롭다운 목록에서 적절한 풀을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c82c8-125">For multiple Persistent Chat Server pool deployments, select the appropriate pool from the drop-down list.</span></span>
    
4. <span data-ttu-id="c82c8-126">**범주** 페이지에서 **새로 만들기** 또는 **편집** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c82c8-126">On the **Category** page, click **New** or **Edit**.</span></span>
    
5. <span data-ttu-id="c82c8-127">서비스 **선택에서** 범주를 만들어야 하는 영구 채팅 서버 풀에 해당하는 서비스를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c82c8-127">In **Select a Service**, select the service corresponding to the Persistent Chat Server pool on which the category needs to be created.</span></span> <span data-ttu-id="c82c8-128">서비스는 영구 채팅(클라이언트)이 범주가 속하는 풀을 식별하는 데 사용하는 영구 채팅 서버 풀입니다.</span><span class="sxs-lookup"><span data-stu-id="c82c8-128">The service is the Persistent Chat Server pool that the Persistent Chat (client) uses to identify which pool the category belongs to.</span></span> <span data-ttu-id="c82c8-129">범주는 하나의 영구 채팅 서버 풀에만 속할 수 있으며 다른 풀로 이동하거나 다른 풀과 공유할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c82c8-129">A category can belong to only one Persistent Chat Server pool, and cannot be moved to another one, or shared with another pool.</span></span>
    
6. <span data-ttu-id="c82c8-130">**새 범주** 에서 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="c82c8-130">In **New Category**, do the following:</span></span>
    
7. <span data-ttu-id="c82c8-131">**이름** 에서 새 방 범주의 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c82c8-131">In **Name**, specify a name for the new room category.</span></span>
    
8. <span data-ttu-id="c82c8-132">**설명** 에서 방 범주의 자세한 설명을 입력합니다(예: Contoso의 방 범주).</span><span class="sxs-lookup"><span data-stu-id="c82c8-132">In **Description**, provide a detailed description for the room category (for example, a room category for Contoso).</span></span>
    
9. <span data-ttu-id="c82c8-133">이 범주에 속하는 대화방에 대해 초대를 사용하도록 설정할 수 있는지 여부를 제어하려면 초대 사용 확인란을 선택하거나 **선택을** 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="c82c8-133">To control whether invitations can be enabled for chat rooms that belong to this category, select or clear the **Enable invitations** check box.</span></span> <span data-ttu-id="c82c8-134">이 옵션을 선택하면 이 범주의 방에 초대가 있을 수 있습니다. 선택을 취소하면 이 범주의 방에 초대가 허용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c82c8-134">If selected, rooms in this category may have invitations on or off; if cleared, the rooms in this category are not allowed to have invitations.</span></span> <span data-ttu-id="c82c8-135">대화방에 초대가 있는 경우 새 구성원이 채팅방에 추가되면 영구 채팅 클라이언트에서 새 채팅방에 대한 알림이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c82c8-135">If a room has invitations on, when a new member is added to a room, he or she gets a notification of the new room in their Persistent Chat client.</span></span>
    
10. <span data-ttu-id="c82c8-p107">해당 범주에 속하는 채팅방에서 파일 업로드를 제어하려면 **파일 업로드 사용** 확인란을 선택하거나 선택을 취소합니다. 이 확인란을 선택하는 경우 해당 범주의 방에서 파일 업로드를 사용하거나 사용하지 않도록 설정할 수 있습니다. 이 확인란의 선택을 취소하는 경우에는 해당 범주의 방에서 파일을 업로드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c82c8-p107">To control file uploads in chat rooms belonging to this category, select or clear the **Enable file upload** check box. If selected, the rooms of this category can enable or disable file uploads; if cleared, the rooms of this category are not allowed to have file uploads.</span></span>
    
     > [!IMPORTANT]
     > <span data-ttu-id="c82c8-138">이 설정은 Office Communications Server 2007 R2 그룹 채팅 서버 또는 Lync Server 2010을 사용하는 사용자 지정 응용 프로그램 또는 이전 그룹 채팅 클라이언트가 파일을 방에 게시할 수 있기 때문에 서버에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c82c8-138">This setting is enforced on the server because custom applications or previous Group Chat clients that use Office Communications Server 2007 R2 Group Chat Server or Lync Server 2010, Group Chat can post files to a room.</span></span> <span data-ttu-id="c82c8-139">Lync 2013 클라이언트에는 파일 업로드/다운로드 기능이 없습니다. 따라서 순수 Lync 2013 배포 또는 Lync 2013 클라이언트가 있는 경우 영구 채팅 서버 대화방에 파일을 게시할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c82c8-139">The Lync 2013 client does not have file upload/download capability, so if you have a pure Lync 2013 deployment or Lync 2013 client, it is not possible to post files in a Persistent Chat Server chat room.</span></span> 
  
11. <span data-ttu-id="c82c8-140">채팅 기록을 제어하려면 채팅 기록 사용 확인란을 **선택하거나** 선택을 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="c82c8-140">To control chat history, select or clear the **Enable chat history** check box.</span></span> <span data-ttu-id="c82c8-141">이 확인란을 선택하는 경우 방의 채팅 내용이 영구적으로 보존되고, 그렇지 않으면 채팅 메시지가 영구적으로 보존되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c82c8-141">If selected, room chats become persistent; otherwise, chat messages are not persisted.</span></span> <span data-ttu-id="c82c8-142">준수를 사용하도록 설정한 경우에는 방의 채팅 내용이 준수에 저장되지만 사용자는 이전 메시지에 액세스할 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c82c8-142">If compliance is enabled, room chats will be saved in compliance, but users will not be able to access older messages.</span></span> <span data-ttu-id="c82c8-143">이 옵션은 채팅 기록을 영구적으로 유지하지 않는 실시간 애드워크 공동 작업으로 지정된 채팅방에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c82c8-143">This option can be used for rooms designated for real-time, ad hoc collaborations that don't need chat history to be persisted.</span></span>
    
12. <span data-ttu-id="c82c8-144">**범주 편집** 에서 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="c82c8-144">In **Edit Category**, do the following:</span></span>
    
    - <span data-ttu-id="c82c8-145">구성원 자격의  허용 구성원 섹션에서 범주에 속하는 채팅방의 구성원으로 추가할 수 있는 사용자 및 기타 Active Directory 도메인 서비스 계정(사용자, 메일 그룹, 조직 구성 단위 등)을 추가하거나 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="c82c8-145">In **Membership**, in the **Allowed members** section, add or remove users and other Active Directory Domain Services principals (users, distribution groups, organizational units, and so on) that are permitted to be added as members of chat rooms belonging to the category.</span></span> <span data-ttu-id="c82c8-146">특정 범주에서 허용된 계정은 방의 구성원만 디렉터리에서 방을 검색할 수 있도록 방이 숨겨져 있지 않은 한 해당 범주에서 방을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c82c8-146">Principals permitted by a category can search for the rooms in the category (unless the room is hidden, in which case only members of the room can search for it in the directory).</span></span>
    
    - <span data-ttu-id="c82c8-147">구성원 **자격의** **거부된** 구성원 섹션에서 방에서 거부된 구성원과 관련된 사용자 및 기타 Active Directory 사용자를 추가하거나 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="c82c8-147">In **Membership**, in the **Denied members** section, add or remove users and other Active Directory principals associated with members being denied from the room.</span></span>
    
    - <span data-ttu-id="c82c8-148">멤버 **자격의** **크리에이터스 섹션에서** 범주의 작성자와 연결된 사용자 및 기타 Active Directory 사용자를 추가하거나 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="c82c8-148">In **Membership**, in the **Creators** section, add or remove users and other Active Directory principals associated with creators for the category.</span></span> <span data-ttu-id="c82c8-149">작성자는 채팅방을 만들고 채팅방 관리자 및 구성원을 할당할 권한이 있는 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="c82c8-149">A creator is a user who has permissions to create chat rooms and assign chat room managers and members.</span></span>
    
13. <span data-ttu-id="c82c8-150">**커밋** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c82c8-150">Click **Commit**.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="c82c8-151">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c82c8-151">See also</span></span>

<span data-ttu-id="c82c8-152">영구 채팅 서버 기능에 대한 자세한 내용은 비즈니스용 Skype 서버 [2015의](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)영구 채팅 서버 계획, 비즈니스용 Skype 서버 [2015에서](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md)영구 채팅 서버 배포 및 영구 채팅 서버 관리(비즈니스용 [Skype 서버 2015)를](../../manage/persistent-chat/persistent-chat.md)참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c82c8-152">For details about Persistent Chat Server features and capabilities, see [Plan for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md), [Deploy Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md), and [Manage Persistent Chat Server in Skype for Business Server 2015](../../manage/persistent-chat/persistent-chat.md).</span></span>
  

