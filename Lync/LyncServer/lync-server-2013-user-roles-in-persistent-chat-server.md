---
title: 'Lync Server 2013: 영구 채팅 서버의 사용자 역할'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: User roles in Persistent Chat Server
ms:assetid: 343a0563-9ca5-4ad0-b4f3-a72f1d7f1a81
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ676774(v=OCS.15)
ms:contentKeyID: 49361095
ms.date: 03/19/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 36f84f71ca5253d28d9182acc9279010127ee6f3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984440"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="user-roles-in-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="0234f-102">Lync Server 2013에서 영구 채팅 서버의 사용자 역할</span><span class="sxs-lookup"><span data-stu-id="0234f-102">User roles in Persistent Chat Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0234f-103">_**마지막으로 수정한 주제:** 2015-03-19_</span><span class="sxs-lookup"><span data-stu-id="0234f-103">_**Topic Last Modified:** 2015-03-19_</span></span>

<span data-ttu-id="0234f-104">영구 채팅 서버는 허용/거부 구성원에 대 한 개념을 제공 하며 영구 채팅 범주에 적용 되며 특정 범주의 채팅방에 액세스할 수 있는 사용자를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="0234f-104">Persistent Chat Server provides the concept of Allowed/Denied members, which applies to Persistent Chat categories and controls who can access rooms in a particular category.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="0234f-105">범주에서 허용/거부 구성원은 영구 채팅방에 적용 되는 <STRONG>구성원</STRONG> 역할과 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="0234f-105">Allowed/Denied members in a Category is not the same as a <STRONG>Member</STRONG> role, which applies to a Persistent Chat room.</span></span><BR><span data-ttu-id="0234f-106">검색을 수행 하는 사용자가 허용/거부 구성원 목록에 있는 열려 있는 모든 채팅방이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0234f-106">Searches display all open and closed chat rooms for which the user performing the search is in the Allowed/Denied member list.</span></span> <span data-ttu-id="0234f-107">비밀 룸의 구성원 인 경우 검색을 수행 하는 사용자가 암호를 입력 해야 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0234f-107">Secret rooms are not displayed unless the user who performs the search is a member of the secret room.</span></span> <span data-ttu-id="0234f-108">사용자는 자신이 이미 구성원 이거나 구성원 자격을 요청할 수 있는 채팅방만 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0234f-108">The user can search only for rooms that he or she is already a member of, or those for which they can request membership.</span></span>



</div>

<span data-ttu-id="0234f-109">허용/거부 구성원의 개념에 대 한 주요 근거는 윤리적인 벽입니다.</span><span class="sxs-lookup"><span data-stu-id="0234f-109">The primary rationale for the concept of Allowed/Denied Members is ethical walls.</span></span> <span data-ttu-id="0234f-110">예를 들어 은행 및 금융 기관에서 윤리적인 경계를 사용 하 여 정책 및 규칙을 구현 하는 동안 traders와 분석가가 통신을 공유 하는 것을 방지 하는 것이 일반적입니다.</span><span class="sxs-lookup"><span data-stu-id="0234f-110">For example, it is common in banking and financial institutions to have ethical boundaries that prevent traders and analysts from sharing communications while implementing policies and conventions.</span></span> <span data-ttu-id="0234f-111">이 요구 사항을 충족 하기 위해 관리자는 한 범주에서 상인에 게 회의실을 만들고 사용할 수 있도록 범주를 만들 수 있으며, 다른 범주를 사용 하 여 분석가가 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0234f-111">To address this requirement, an administrator can create categories so that one category allows rooms to be created and used by traders, and another category allows rooms to be created and used by analysts.</span></span> <span data-ttu-id="0234f-112">이 제약 조건은 시스템에 디자인 되어 있으므로 상위 범주에서 허용 되지 않는 경우 사용자를 룸의 구성원으로 추가할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0234f-112">With this constraint is designed into the system prohibits adding a user as a member of the room if the parent category prevents it.</span></span>

<span data-ttu-id="0234f-113">다음은 네 가지 사용자 역할 영구 채팅 서버입니다.</span><span class="sxs-lookup"><span data-stu-id="0234f-113">Following are the four user roles Persistent Chat Server:</span></span>

  - <span data-ttu-id="0234f-114">**만든 사람:** 채팅방을 만들 수 있는 권한이 있는 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="0234f-114">**Creator:** Users who have permissions to create chat rooms.</span></span> <span data-ttu-id="0234f-115">이러한 사용자는 특정 범주의 작성자 목록에서 해당 범주에 대 한 채팅방을 만들 수 있으며, 범주에 따라 구성원 자격을 할당 하 고, 관리자를 할당 하 여 채팅방을 관리할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0234f-115">These users are in the Creators list of certain categories: they can create chat rooms in that category, and they can also assign membership according to the category, and assign managers to manage the chat room.</span></span> <span data-ttu-id="0234f-116">채팅방을 만드는 사용자는 자동으로 대화방의 관리자로 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0234f-116">The user who creates a chat room is automatically added as a manager of the room.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="0234f-117">작성자 중에는 채팅방 만들기 권한이 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0234f-117">Being a Creator simply provides rights for creating chat rooms.</span></span> <span data-ttu-id="0234f-118">이는 만든 채팅 서비스에 대 한 구성원 자격, 관리자 등을 더욱 구체화할 수 있도록 해 주는 자동 승격 관리자입니다.</span><span class="sxs-lookup"><span data-stu-id="0234f-118">It is the automatic promotion to Manager that enables the Creator to further refine memberships, managers, and so on, on the created chat services.</span></span>

    
    </div>
    
    <span data-ttu-id="0234f-119">이 역할은 조직의 채팅방을 만드는 사용자를 제어할 수 있는 옵션을 제공 하는 데, 특히 정책 및 규칙을 적용 하는 채팅방을 중앙에서 관리 하 고 그 후에 채팅방 관리를 다른 사람에 게 위임 하는 것입니다. 조직의 사용자</span><span class="sxs-lookup"><span data-stu-id="0234f-119">This role exists to give you the option of controlling who creates chat rooms in your organization, particularly if you want to centrally manage creating chat rooms to enforce policies and conventions, and subsequently delegate the chat room management to other users in the organization.</span></span>

  - <span data-ttu-id="0234f-120">**관리자:** 채팅방의 속성을 관리 하는 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="0234f-120">**Manager:** Users who manage properties of a chat room.</span></span> <span data-ttu-id="0234f-121">채팅방 관리자는 구성원 목록 (구성원 추가 및 제거)을 수정 하 고, 채팅방 관리자 목록 (관리자 추가 및 제거)을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0234f-121">Chat room managers can modify the member list (add and remove members), and modify the chat room managers list (add and remove managers).</span></span> <span data-ttu-id="0234f-122">채팅방 관리자는 채팅방에 참가할 수 있도록 구성원 또는 발표자 목록 (auditorium 채팅방)에 자신을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0234f-122">Chat room managers can add themselves to the members or presenters list (for auditorium rooms) so they can participate in the chat room.</span></span> <span data-ttu-id="0234f-123">채팅방 관리자는 채팅방을 사용 하지 않도록 설정할 수 있습니다 (관리자가 사용 하지 않도록 설정 된 채팅방 채팅방을 쿼리하고 영구적으로 삭제할 수 있음).</span><span class="sxs-lookup"><span data-stu-id="0234f-123">Chat room managers can also disable chat rooms (administrators can query for disabled chat rooms and can permanently delete them).</span></span> <span data-ttu-id="0234f-124">관리자는 채팅방의 범주를 제외 하 고 채팅방의 모든 속성을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0234f-124">Managers can change all the properties of a chat room, except the category of the chat room.</span></span> <span data-ttu-id="0234f-125">채팅방을 만든 후에는 영구 채팅 관리자만 범주를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0234f-125">Only the Persistent Chat Administrator can change the category after the chat room has been created.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="0234f-126">관리자가 다른 범주의 작성자 이기도 한 경우, 사용자는 룸을 만들 수 있는 권한이 있는 범주를 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="0234f-126">If the manager is also a Creator in another category, he or she can change the category to one where they are authorized to create rooms.</span></span>

    
    </div>

  - <span data-ttu-id="0234f-127">**회원:** 채팅방의 구성원 인 사용자</span><span class="sxs-lookup"><span data-stu-id="0234f-127">**Member:** Users who are members of a chat room.</span></span> <span data-ttu-id="0234f-128">이러한 사용자는 디렉터리의 채팅방을 볼 수 있습니다 (채팅방이 비밀 인 경우에도), 채팅방에 가입 (읽지 않은 메시지,에 고 필터, 키워드 필터 등의 메타 데이터 옵션 포함) 하 고 채팅방에 참가 합니다 ( 발표자만 게시물을 게시 하 고 콘텐츠를 가져오고 검색할 수 있는 auditorium 공간입니다.</span><span class="sxs-lookup"><span data-stu-id="0234f-128">These users can see the chat rooms in the directory (even if the chat room is secret), as well as subscribe to the chat room (including metadata options such as unread messages, ego filters, and keyword filters), and participate in the chat room (can post, unless the room is an auditorium room where only presenters can post, get content, and search).</span></span> <span data-ttu-id="0234f-129">채팅방의 구성원이 아닌 사용자는 범주의 허용 구성원 목록에 있는 채팅방을 검색할 수 있지만,이 채팅방에 참가 하 여 콘텐츠에 액세스 하려면 액세스를 요청 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0234f-129">Users who aren’t members of the chat room can search for the chat room if they are in the Allowed Members list of the category, but need to request access to join these chat rooms to access content.</span></span> <span data-ttu-id="0234f-130">(시스템에 기본으로 제공 되는 요청 액세스 또는 승인은 없으며,이는 전자 메일, 전화 또는 다른 형태의 연락처를 통해 외부적으로 수행 됩니다.)</span><span class="sxs-lookup"><span data-stu-id="0234f-130">(There is no request access or approvals built into the system; these are done externally by email, phone, or other forms of contact.)</span></span>

  - <span data-ttu-id="0234f-131">**발표자:** Auditorium 방에 게시할 수 있는 사용자</span><span class="sxs-lookup"><span data-stu-id="0234f-131">**Presenter:** Users who can post to an auditorium room.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0234f-132">영구 채팅 서버는 사용자가 특정 사이트에 대 한 채팅방을 만들고 관리할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="0234f-132">Persistent Chat Server lets users create and manage chat room for a specific site.</span></span> <span data-ttu-id="0234f-133">그러나 같은 토폴로지 내에 있는 다른 사이트의 채팅방을 만들거나 관리할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0234f-133">Users cannot, however, create or manage chat rooms on other sites within the same topology.</span></span> <span data-ttu-id="0234f-134">조직의 모든 사이트에 대 한 채팅방 작성자 및 관리자를 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0234f-134">Be sure to specify chat room Creators and Managers for all the sites in your organization.</span></span>



</div>

<span data-ttu-id="0234f-135">다음 역할은 영구 채팅 서버의 관리자 역할입니다.</span><span class="sxs-lookup"><span data-stu-id="0234f-135">The following roles are administrator roles for Persistent Chat Server:</span></span>

  - <span data-ttu-id="0234f-136">**CsPersistentChatAdministrator (영구 채팅 관리자):** 영구 채팅 서버를 관리 하 고 관리 하기 위한 새로운 RBAC (역할 기반 액세스 제어) 역할입니다.</span><span class="sxs-lookup"><span data-stu-id="0234f-136">**Persistent Chat Administrator (CsPersistentChatAdministrator):** This is a new Role-Based Access Control (RBAC) role to administer and manage Persistent Chat Server.</span></span> <span data-ttu-id="0234f-137">CsPersistentChatAdministrator로 지정 된 사용자 또는 보안 그룹은 Windows PowerShell cmdlet을 원격으로 사용 하 여 영구 채팅 서버를 관리할 수 있습니다 (즉, 영구 채팅 서버 이외의 컴퓨터에서).</span><span class="sxs-lookup"><span data-stu-id="0234f-137">Users or security groups designated as CsPersistentChatAdministrator are able administer Persistent Chat Server by using Windows PowerShell cmdlets remotely (that is, from a computer other than the Persistent Chat Server).</span></span> <span data-ttu-id="0234f-138">영구 채팅 서버는 영구 채팅 관리자가 영구 채팅 서버 프런트 엔드 서버의 RTC 로컬 관리자 로컬 그룹의 구성원 인지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="0234f-138">Persistent Chat Server checks that the Persistent Chat Administrator is member of the RTC Local administrator local group on the Persistent Chat Server Front End Server.</span></span>
    
    <span data-ttu-id="0234f-139">CsPersistentChatAdministrator 역할은 채팅방을 관리할 수 있으며 (구성원 자격, 관리자, 범주, 채팅방 표시를 포함 하 여 모든 속성 수정), 채팅방을 만들고 액세스할 수 있는 사용자를 정의 하는 채팅방 범주를 만들고 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="0234f-139">The CsPersistentChatAdministrator role can manage chat rooms (modify all properties including membership, managers, categories, mark rooms as disabled), as well as create and manage chat room categories that define who can create and access chat rooms.</span></span> <span data-ttu-id="0234f-140">또한 관리자는 채팅방을 사용 안 함으로 표시 하 고 더 이상 활성화 되지 않은 채팅방을 정리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0234f-140">Administrators can also mark chat rooms as disabled and clean up chat rooms that are no longer active.</span></span> <span data-ttu-id="0234f-141">관리자는 작성자 또는 허용 구성원 제한에 영향을 받지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0234f-141">Administrators are not subject to the Creators or Allowed Members restrictions.</span></span> <span data-ttu-id="0234f-142">관리자는 모든 종류의 채팅방을 만들고 자신을 채팅방의 구성원으로 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0234f-142">Administrators can create any kind of chat room and add themselves as a member to any chat room.</span></span> <span data-ttu-id="0234f-143">관리자는 또한 영구 채팅 구성 (풀 속성, 전역 설정, 준수 구성)을 수정 하 고 관리할 수 있으며, 이전 그룹 채팅 서버 배포에서 Lync Server 2013 영구 채팅으로 마이그레이션을 계획 하 고 구현할 수 있습니다. Server.</span><span class="sxs-lookup"><span data-stu-id="0234f-143">Administrators can also modify and manage Persistent Chat configuration (pool properties, global settings, and compliance configuration) and can also plan and implement migration from an older Group Chat Server deployment to Lync Server 2013 Persistent Chat Server.</span></span>

  - <span data-ttu-id="0234f-144">**Lync 관리자:** 배포를 담당 하는 Lync Server 2013의 전체 엔터프라이즈 관리자입니다.</span><span class="sxs-lookup"><span data-stu-id="0234f-144">**Lync Administrator:** Overall enterprise administrator for Lync Server 2013 responsible for deployment.</span></span>

  - <span data-ttu-id="0234f-145">**Operations Manager:** 일 대 일 작업의 관리를 담당 하는 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="0234f-145">**Operations Manager:** User responsible for managing day-to-day operations.</span></span>

  - <span data-ttu-id="0234f-146">**타사 개발자 및 파트너:** 타사 개발자는 그룹 대화, 준수 지원, 도구, 웹/모바일 클라이언트, 봇 개발용 프레임 워크에 대 한 윤리적인 벽 솔루션을 제공 하 여 시스템을 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="0234f-146">**Third-party developers and partners:** Third-party developers extend the system, in particular providing an ethical wall solution for group conversations, compliance support and tools, web/mobile clients, and a framework for Bot development.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

