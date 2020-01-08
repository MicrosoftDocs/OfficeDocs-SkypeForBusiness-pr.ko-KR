---
title: 'Lync Server 2013: 범주 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure categories
ms:assetid: 4547f514-f0c0-404d-890f-092ddeeac852
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204859(v=OCS.15)
ms:contentKeyID: 48184033
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 310d0b2e32c8a21f00e20593a408df260eb80e32
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976258"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-categories-in-lync-server-2013"></a><span data-ttu-id="99c5b-102">Lync Server 2013에서 범주 구성</span><span class="sxs-lookup"><span data-stu-id="99c5b-102">Configure categories in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="99c5b-103">_**마지막으로 수정한 주제:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="99c5b-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="99c5b-104">Lync Server 2013 제어판에서 **영구 채팅** 페이지의 **범주** 섹션을 사용 하 여 범주를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99c5b-104">In Lync Server 2013 Control Panel, you can use the **Category** section of the **Persistent Chat** page to configure categories.</span></span> <span data-ttu-id="99c5b-105">영구 채팅방 범주는 채팅방을 구성 하는 논리적 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="99c5b-105">A Persistent Chat room category is a logical structure for organizing chat rooms.</span></span> <span data-ttu-id="99c5b-106">범주는 채팅방을 만들거나 채팅방에 참가할 수 있는 사용자 및 사용자 그룹을 제어하기 위한 기본 ACL(액세스 제어 목록) 집합을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="99c5b-106">A category defines a default set of access control lists (ACLs) for controlling the users and user groups who may create or join the chat rooms.</span></span> <span data-ttu-id="99c5b-107">범주를 사용하여 조직 내의 개별 하위 부문 간에 교신 차단 영역을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99c5b-107">You can use categories enforce ethical walls between different subdivisions within their organizations.</span></span>

<span data-ttu-id="99c5b-108">채팅방 범주는 채팅방을 포함할 수 있지만 다른 범주는 포함할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="99c5b-108">Chat room categories may contain chat rooms, but not other categories.</span></span> <span data-ttu-id="99c5b-109">각 범주는 Name과 Description과 같은 메타데이터를 사용해서 해당 콘텐츠를 기술합니다.</span><span class="sxs-lookup"><span data-stu-id="99c5b-109">Each category describes its contents with metadata, such as Name and Description.</span></span> <span data-ttu-id="99c5b-110">또한 범주는 채팅방에서 Invitations 또는 File Uploads를 허용하거나 Chat History을 포함하는 등 범주에 속하는 채팅방의 동작을 제어하기 위해 설정할 수 있는 속성을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="99c5b-110">In addition, the category has properties which can be set to control the behavior of the chat rooms belonging to it, such as if the chat rooms allow Invitations or File Uploads, or contain Chat History.</span></span>

<div>

## <a name="to-configure-categories-for-chat-rooms"></a><span data-ttu-id="99c5b-111">채팅방에 대한 범주를 구성하려면</span><span class="sxs-lookup"><span data-stu-id="99c5b-111">To configure categories for chat rooms</span></span>

1.  <span data-ttu-id="99c5b-112">CsPersistentChatAdministrator 또는 CsAdministrator 역할에 지정된 사용자 계정에서 내부 배포의 임의 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="99c5b-112">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="99c5b-113">**시작** 메뉴에서 Lync Server 제어판을 선택 하거나 브라우저 창을 연 다음 관리 URL을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="99c5b-113">From the **Start** menu, select the Lync Server Control Panel or open a browser window, and then enter the Admin URL.</span></span> <span data-ttu-id="99c5b-114">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="99c5b-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="99c5b-115">Windows PowerShell cmdlet을 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99c5b-115">You can also use Windows PowerShell cmdlets.</span></span> <span data-ttu-id="99c5b-116">자세한 내용은 배포 설명서의 <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Windows PowerShell cmdlet을 사용 하 여 영구 채팅 서버 구성을</A> 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="99c5b-116">For details, see <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Configuring Persistent Chat Server by using Windows PowerShell cmdlets</A> in the Deployment documentation.</span></span>

    
    </div>

3.  <span data-ttu-id="99c5b-117">왼쪽 탐색 모음에서 **영구 채팅**을 클릭하고 **범주**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="99c5b-117">In the left navigation bar, click **Persistent Chat**, and then click **Category**.</span></span>
    
    <span data-ttu-id="99c5b-118">여러 영구 채팅 서버 풀 배포의 경우 드롭다운 목록에서 적절 한 풀을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="99c5b-118">For multiple Persistent Chat Server pool deployments, select the appropriate pool from the drop-down list.</span></span>

4.  <span data-ttu-id="99c5b-119">**범주** 페이지에서 **새로 만들기** 또는 **편집**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="99c5b-119">On the **Category** page, click **New** or **Edit**.</span></span>

5.  <span data-ttu-id="99c5b-120">**서비스 선택**에서 범주가 생성 되어야 하는 영구 채팅 서버 풀에 해당 하는 서비스를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="99c5b-120">In **Select a Service**, select the service corresponding to the Persistent Chat Server pool on which the category needs to be created.</span></span> <span data-ttu-id="99c5b-121">이 서비스는 영구 채팅 (클라이언트)이 범주가 속해 있는 풀을 식별 하는 데 사용 하는 영구 채팅 서버 풀입니다.</span><span class="sxs-lookup"><span data-stu-id="99c5b-121">The service is the Persistent Chat Server pool that the Persistent Chat (client) uses to identify which pool the category belongs to.</span></span> <span data-ttu-id="99c5b-122">범주는 하나의 영구 채팅 서버 풀에만 속할 수 있으며 다른 그룹으로 이동 하거나 다른 풀에 공유 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="99c5b-122">A category can belong to only one Persistent Chat Server pool, and cannot be moved to another one, or shared with another pool.</span></span>

6.  <span data-ttu-id="99c5b-123">**새 범주**에서 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="99c5b-123">In **New Category**, do the following:</span></span>
    
    1.  <span data-ttu-id="99c5b-124">**이름**에 새로운 채팅방 범주에 대한 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="99c5b-124">In **Name**, specify a name for the new room category.</span></span>
    
    2.  <span data-ttu-id="99c5b-125">**설명**에 채팅방 범주에 대한 자세한 설명을 제공합니다(예: 한미 교역에 대한 채팅방 범주).</span><span class="sxs-lookup"><span data-stu-id="99c5b-125">In **Description**, provide a detailed description for the room category (for example, a room category for Contoso).</span></span>
    
    3.  <span data-ttu-id="99c5b-126">이 범주에 속한 채팅방에 대해 초대를 사용할 수 있는지 여부를 제어 하려면 **초대 사용** 확인란을 선택 하거나 선택을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="99c5b-126">To control whether invitations can be enabled for chat rooms that belong to this category, select or clear the **Enable invitations** check box.</span></span> <span data-ttu-id="99c5b-127">선택 하는 경우이 범주의 채팅방에서 초대를 보내거나 해제할 수 있습니다. 이 확인란을 선택 취소 하면이 범주의 채팅방에서 초대를 할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="99c5b-127">If selected, rooms in this category may have invitations on or off; if cleared, the rooms in this category are not allowed to have invitations.</span></span> <span data-ttu-id="99c5b-128">룸에 대 한 초대가 있는 경우 룸에 새 구성원을 추가할 때 영구 채팅 클라이언트에서 새 룸에 대 한 알림을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="99c5b-128">If a room has invitations on, when a new member is added to a room, he or she gets a notification of the new room in their Persistent Chat client.</span></span>
    
    4.  <span data-ttu-id="99c5b-p107">이 범주에 속하는 채팅방에서 파일 업로드를 제어하려면 **파일 업로드 사용** 확인란을 선택하거나 선택을 취소합니다. 확인란을 선택하면 이 범주의 채팅방에서 파일 업로드를 설정 또는 해제할 수 있으며, 확인란의 선택을 취소하면 이 범주의 채팅방에서 파일 업로드를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="99c5b-p107">To control file uploads in chat rooms belonging to this category, select or clear the **Enable file upload** check box. If selected, the rooms of this category can enable or disable file uploads; if cleared, the rooms of this category are not allowed to have file uploads.</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="99c5b-131">이 설정은 Office Communications Server 2007 R2&nbsp;그룹 채팅 서버 또는 Lync server 2010를 사용 하는 사용자 지정 응용 프로그램 또는 이전 그룹 채팅 클라이언트가 있으므로 서버에서 적용 됩니다. 그룹 채팅을 통해 채팅방에 파일을 게시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99c5b-131">This setting is enforced on the server because custom applications or previous Group Chat clients that use Office Communications Server 2007 R2&nbsp;Group Chat Server or Lync Server 2010, Group Chat can post files to a room.</span></span> <span data-ttu-id="99c5b-132">Lync 2013 클라이언트에는 파일 업로드/다운로드 기능이 없기 때문에 순수한 Lync 2013 배포 또는 Lync 2013 클라이언트를 사용 하는 경우 영구 채팅 서버 채팅방에 파일을 게시할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="99c5b-132">The Lync 2013 client does not have file upload/download capability, so if you have a pure Lync 2013 deployment or Lync 2013 client, it is not possible to post files in a Persistent Chat Server chat room.</span></span>

        
        </div>
    
    5.  <span data-ttu-id="99c5b-133">채팅 기록을 제어 하려면 **채팅 기록 사용** 확인란을 선택 하거나 선택을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="99c5b-133">To control chat history, select or clear the **Enable chat history** check box.</span></span> <span data-ttu-id="99c5b-134">확인란을 선택하면 채팅방 채팅이 영구적으로 저장되고, 그렇지 않으면 채팅 메시지가 저장되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="99c5b-134">If selected, room chats become persistent; otherwise, chat messages are not persisted.</span></span> <span data-ttu-id="99c5b-135">준수 기능이 설정된 경우 채팅방 채팅이 준수 기능으로 저장되지만 사용자가 이전 메시지에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="99c5b-135">If compliance is enabled, room chats will be saved in compliance, but users will not be able to access older messages.</span></span> <span data-ttu-id="99c5b-136">이 옵션은 채팅 기록을 영구 저장할 필요가 없는 실시간 임시 공동 작업을 위해 지정된 채팅방에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99c5b-136">This option can be used for rooms designated for real-time, ad hoc collaborations that don’t need chat history to be persisted.</span></span>

7.  <span data-ttu-id="99c5b-137">**범주 편집**에서 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="99c5b-137">In **Edit Category**, do the following:</span></span>
    
      - <span data-ttu-id="99c5b-138">**구성원 자격**의 허용 된 **구성원** 섹션에서 사용자 및 기타 Active Directory 도메인 서비스 주체 (사용자, 메일 그룹, 조직 구성 단위 등)를 추가 하거나 제거 하 여 범주에 속하는 채팅방의 구성원으로 추가할 수 있도록 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="99c5b-138">In **Membership**, in the **Allowed members** section, add or remove users and other Active Directory Domain Services principals (users, distribution groups, organizational units, and so on) that are permitted to be added as members of chat rooms belonging to the category.</span></span> <span data-ttu-id="99c5b-139">특정 범주에서 허용된 계정은 채팅방의 구성원만 디렉터리에서 채팅방을 검색할 수 있도록 채팅방이 숨겨져 있지 않은 한 해당 범주에서 채팅방을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99c5b-139">Principals permitted by a category can search for the rooms in the category (unless the room is hidden, in which case only members of the room can search for it in the directory).</span></span>
    
      - <span data-ttu-id="99c5b-140">**구성원 자격**의 거부 된 **구성원** 섹션에서 룸에서 거부 되는 구성원과 연결 된 사용자 및 기타 Active Directory 주도자를 추가 하거나 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="99c5b-140">In **Membership**, in the **Denied members** section, add or remove users and other Active Directory principals associated with members being denied from the room.</span></span>
    
      - <span data-ttu-id="99c5b-141">**멤버 자격**의 **작성자** 섹션에서 해당 범주에 대 한 작성자와 연결 된 사용자 및 기타 Active Directory 보안 주체를 추가 하거나 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="99c5b-141">In **Membership**, in the **Creators** section, add or remove users and other Active Directory principals associated with creators for the category.</span></span> <span data-ttu-id="99c5b-142">작성자는 채팅방을 만들고 채팅방 관리자 및 구성원을 지정할 권한이 있는 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="99c5b-142">A creator is a user who has permissions to create chat rooms and assign chat room managers and members.</span></span>

8.  <span data-ttu-id="99c5b-143">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="99c5b-143">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

