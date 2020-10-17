---
title: 'Lync Server 2013: 영구 채팅 서버의 사용자 역할'
description: 'Lync Server 2013: 영구 채팅 서버의 사용자 역할'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: User roles in Persistent Chat Server
ms:assetid: 343a0563-9ca5-4ad0-b4f3-a72f1d7f1a81
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ676774(v=OCS.15)
ms:contentKeyID: 49361095
ms.date: 03/19/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aed64aaa9129e6667cd138bc4365acfb2a64d52c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550854"
---
# <a name="user-roles-in-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="f5911-103">Lync Server 2013의 영구 채팅 서버에 있는 사용자 역할</span><span class="sxs-lookup"><span data-stu-id="f5911-103">User roles in Persistent Chat Server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f5911-104">_**마지막으로 수정 된 항목:** 2015-03-19_</span><span class="sxs-lookup"><span data-stu-id="f5911-104">_**Topic Last Modified:** 2015-03-19_</span></span>

<span data-ttu-id="f5911-105">영구 채팅 서버는 허용/거부 구성원의 개념을 제공 하며 영구 채팅 범주에 적용 되며 특정 범주의 대화방에 액세스할 수 있는 사용자를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="f5911-105">Persistent Chat Server provides the concept of Allowed/Denied members, which applies to Persistent Chat categories and controls who can access rooms in a particular category.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="f5911-106">허용/거부 된 구성원은 영구 채팅방에 적용 되는 <STRONG>구성원</STRONG> 역할과는 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="f5911-106">Allowed/Denied members in a Category is not the same as a <STRONG>Member</STRONG> role, which applies to a Persistent Chat room.</span></span><BR><span data-ttu-id="f5911-p101">검색을 수행하면 검색 수행 사용자가 허용 구성원/거부 구성원 목록에 포함된 모든 공개 채팅방 및 비공개 채팅방이 표시됩니다. 비밀 채팅방은 검색 수행 사용자가 해당 방의 구성원이 아니면 표시되지 않습니다. 사용자는 자신이 구성원으로 속해 있거나 구성원 자격을 요청할 수 있는 방만 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5911-p101">Searches display all open and closed chat rooms for which the user performing the search is in the Allowed/Denied member list. Secret rooms are not displayed unless the user who performs the search is a member of the secret room. The user can search only for rooms that he or she is already a member of, or those for which they can request membership.</span></span>



</div>

<span data-ttu-id="f5911-p102">허용 구성원/거부 구성원 개념의 기본적인 기준은 교신 차단 영역입니다. 예를 들어 은행과 금융 기관은 정책 및 규칙을 구현하는 동안 거래자와 분석가들의 통신 내용 공유를 금지하는 교신 차단 경계를 설정할 수 있습니다. 이 요구 사항을 충족하기 위해 관리자는 여러 범주를 만들어 한 범주에서는 거래자들이 방을 작성 및 사용하도록 허용하고 다른 범주에서는 분석가들이 방을 작성 및 사용하도록 허용할 수 있습니다. 이 제약 조건을 포함해 시스템을 디자인하면 상위 범주에서 차단하는 경우 사용자를 방 구성원으로 추가할 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f5911-p102">The primary rationale for the concept of Allowed/Denied Members is ethical walls. For example, it is common in banking and financial institutions to have ethical boundaries that prevent traders and analysts from sharing communications while implementing policies and conventions. To address this requirement, an administrator can create categories so that one category allows rooms to be created and used by traders, and another category allows rooms to be created and used by analysts. With this constraint is designed into the system prohibits adding a user as a member of the room if the parent category prevents it.</span></span>

<span data-ttu-id="f5911-114">다음은 네 가지 사용자 역할 영구 채팅 서버입니다.</span><span class="sxs-lookup"><span data-stu-id="f5911-114">Following are the four user roles Persistent Chat Server:</span></span>

  - <span data-ttu-id="f5911-115">**만든이:** 대화방을 만들 수 있는 권한이 있는 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="f5911-115">**Creator:** Users who have permissions to create chat rooms.</span></span> <span data-ttu-id="f5911-116">이러한 사용자는 특정 범주의 작성자 목록에서 해당 범주에 대화방을 만들 수 있으며, 범주에 따라 멤버 자격을 할당 하 고, 관리자를 할당 하 여 채팅방을 관리할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5911-116">These users are in the Creators list of certain categories: they can create chat rooms in that category, and they can also assign membership according to the category, and assign managers to manage the chat room.</span></span> <span data-ttu-id="f5911-117">대화방을 만드는 사용자는 자동으로 대화방 관리자로 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f5911-117">The user who creates a chat room is automatically added as a manager of the room.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f5911-p104">작성자에게는 단순히 채팅방 작성 권한만 제공됩니다. 작성자가 작성된 채팅 서비스에서 구체적인 구성원 자격, 관리자 등을 추가로 지정할 수 있도록 하기 위해 관리자로 자동 승격되는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="f5911-p104">Being a Creator simply provides rights for creating chat rooms. It is the automatic promotion to Manager that enables the Creator to further refine memberships, managers, and so on, on the created chat services.</span></span>

    
    </div>
    
    <span data-ttu-id="f5911-120">이 역할은 조직에서 채팅방을 작성하는 사람을 제어하는 옵션을 제공하며, 특히 채팅방 만들기를 중앙에서 관리하여 정책과 규칙을 적용하고 이후에 채팅방 관리 권한을 조직의 다른 사용자에게 위임하려는 경우에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f5911-120">This role exists to give you the option of controlling who creates chat rooms in your organization, particularly if you want to centrally manage creating chat rooms to enforce policies and conventions, and subsequently delegate the chat room management to other users in the organization.</span></span>

  - <span data-ttu-id="f5911-121">**관리자:** 대화방의 속성을 관리 하는 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="f5911-121">**Manager:** Users who manage properties of a chat room.</span></span> <span data-ttu-id="f5911-122">채팅방 관리자는 구성원 목록을 수정(구성원 추가/제거)하고 채팅방 관리자 목록을 수정(관리자 추가/제거)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5911-122">Chat room managers can modify the member list (add and remove members), and modify the chat room managers list (add and remove managers).</span></span> <span data-ttu-id="f5911-123">채팅방 관리자는 채팅방에 참가할 수 있도록 자신을 구성원 또는 발표자(강당 채팅방의 경우) 목록에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5911-123">Chat room managers can add themselves to the members or presenters list (for auditorium rooms) so they can participate in the chat room.</span></span> <span data-ttu-id="f5911-124">또한 채팅방을 사용하지 않도록 설정할 수도 있습니다(관리자(administrator)가 사용하지 않도록 설정된 채팅방을 쿼리하여 영구적으로 삭제할 수 있음).</span><span class="sxs-lookup"><span data-stu-id="f5911-124">Chat room managers can also disable chat rooms (administrators can query for disabled chat rooms and can permanently delete them).</span></span> <span data-ttu-id="f5911-125">관리자는 채팅방 범주를 제외한 모든 채팅방 속성을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5911-125">Managers can change all the properties of a chat room, except the category of the chat room.</span></span> <span data-ttu-id="f5911-126">대화방을 만든 후에만 영구 채팅 관리자만 범주를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5911-126">Only the Persistent Chat Administrator can change the category after the chat room has been created.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="f5911-127">다른 범주의 작성자이기도 한 관리자는 해당 범주를 자신이 방을 만들 권한이 있는 범주로 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5911-127">If the manager is also a Creator in another category, he or she can change the category to one where they are authorized to create rooms.</span></span>

    
    </div>

  - <span data-ttu-id="f5911-128">**구성원:** 대화방의 구성원 인 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="f5911-128">**Member:** Users who are members of a chat room.</span></span> <span data-ttu-id="f5911-129">이러한 사용자는 디렉터리의 채팅방(비밀 채팅방 포함)을 보고 채팅방을 구독할 수 있으며(읽지 않은 메시지, 본인 검색 필터 및 키워드 필터와 같은 메타데이터 옵션도 포함됨) 채팅방에 참가할 수 있습니다(발표자만 게시, 콘텐츠 가져오기, 검색을 수행할 수 있는 강당 채팅방을 제외하고는 게시 가능).</span><span class="sxs-lookup"><span data-stu-id="f5911-129">These users can see the chat rooms in the directory (even if the chat room is secret), as well as subscribe to the chat room (including metadata options such as unread messages, ego filters, and keyword filters), and participate in the chat room (can post, unless the room is an auditorium room where only presenters can post, get content, and search).</span></span> <span data-ttu-id="f5911-130">채팅방 구성원이 아닌 사용자는 범주의 허용 구성원 목록에 포함되어 있으면 채팅방을 검색할 수는 있지만, 콘텐츠에 액세스하려면 해당 채팅방 참가 권한을 요청해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f5911-130">Users who aren’t members of the chat room can search for the chat room if they are in the Allowed Members list of the category, but need to request access to join these chat rooms to access content.</span></span> <span data-ttu-id="f5911-131">시스템에서 기본적으로 제공되는 요청 액세스 또는 승인 기능은 없으며, 이러한 작업은 전자 메일/전화/기타 연락 형식을 통해 외부적으로 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="f5911-131">(There is no request access or approvals built into the system; these are done externally by email, phone, or other forms of contact.)</span></span>

  - <span data-ttu-id="f5911-132">**발표자:** 강당 대화방에 게시할 수 있는 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="f5911-132">**Presenter:** Users who can post to an auditorium room.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f5911-133">영구 채팅 서버를 사용 하면 사용자가 특정 사이트에 대해 채팅방을 만들고 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5911-133">Persistent Chat Server lets users create and manage chat room for a specific site.</span></span> <span data-ttu-id="f5911-134">그러나 동일한 토폴로지 내의 다른 사이트에서는 사용자가 채팅방을 만들거나 관리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f5911-134">Users cannot, however, create or manage chat rooms on other sites within the same topology.</span></span> <span data-ttu-id="f5911-135">조직의 모든 사이트에 대해 대화방 작성자 및 관리자를 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f5911-135">Be sure to specify chat room Creators and Managers for all the sites in your organization.</span></span>



</div>

<span data-ttu-id="f5911-136">다음 역할은 영구 채팅 서버의 관리자 역할입니다.</span><span class="sxs-lookup"><span data-stu-id="f5911-136">The following roles are administrator roles for Persistent Chat Server:</span></span>

  - <span data-ttu-id="f5911-137">**영구 채팅 관리자 (CsPersistentChatAdministrator):** 영구 채팅 서버를 관리 하 고 관리 하기 위한 새로운 RBAC (Role-Based 액세스 제어) 역할입니다.</span><span class="sxs-lookup"><span data-stu-id="f5911-137">**Persistent Chat Administrator (CsPersistentChatAdministrator):** This is a new Role-Based Access Control (RBAC) role to administer and manage Persistent Chat Server.</span></span> <span data-ttu-id="f5911-138">CsPersistentChatAdministrator로 지정 된 사용자 또는 보안 그룹은 영구 채팅 서버가 아닌 컴퓨터에서 원격으로 Windows PowerShell cmdlet을 사용 하 여 영구적 채팅 서버를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5911-138">Users or security groups designated as CsPersistentChatAdministrator are able administer Persistent Chat Server by using Windows PowerShell cmdlets remotely (that is, from a computer other than the Persistent Chat Server).</span></span> <span data-ttu-id="f5911-139">영구 채팅 서버는 영구 채팅 관리자가 영구 채팅 서버 프런트 엔드 서버에서 RTC 로컬 관리자 로컬 그룹의 구성원 인지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="f5911-139">Persistent Chat Server checks that the Persistent Chat Administrator is member of the RTC Local administrator local group on the Persistent Chat Server Front End Server.</span></span>
    
    <span data-ttu-id="f5911-140">CsPersistentChatAdministrator 역할은 채팅방을 관리(구성원 자격/관리자/범주를 비롯한 모든 속성을 수정하고 방을 사용할 수 없도록 표시)할 수 있으며 채팅방을 만들고 액세스할 수 있는 사용자를 정의하는 채팅방 범주를 만들고 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5911-140">The CsPersistentChatAdministrator role can manage chat rooms (modify all properties including membership, managers, categories, mark rooms as disabled), as well as create and manage chat room categories that define who can create and access chat rooms.</span></span> <span data-ttu-id="f5911-141">또한 관리자는 채팅방을 사용할 수 없도록 표시하고 더 이상 사용되지 않는 채팅방을 정리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5911-141">Administrators can also mark chat rooms as disabled and clean up chat rooms that are no longer active.</span></span> <span data-ttu-id="f5911-142">관리자에게는 작성자 또는 허용 구성원의 제한이 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f5911-142">Administrators are not subject to the Creators or Allowed Members restrictions.</span></span> <span data-ttu-id="f5911-143">관리자는 어떤 종류의 채팅방이든 만들 수 있으며 모든 채팅방에 자신을 구성원으로 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5911-143">Administrators can create any kind of chat room and add themselves as a member to any chat room.</span></span> <span data-ttu-id="f5911-144">또한 관리자는 영구 채팅 구성 (풀 속성, 전역 설정 및 준수 구성)을 수정 하 고 관리할 수 있으며, 이전 그룹 채팅 서버 배포에서 Lync Server 2013 영구 채팅 서버로의 마이그레이션을 계획 하 고 구현할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5911-144">Administrators can also modify and manage Persistent Chat configuration (pool properties, global settings, and compliance configuration) and can also plan and implement migration from an older Group Chat Server deployment to Lync Server 2013 Persistent Chat Server.</span></span>

  - <span data-ttu-id="f5911-145">**Lync 관리자:** 배포를 담당 하는 Lync Server 2013의 전반적인 엔터프라이즈 관리자</span><span class="sxs-lookup"><span data-stu-id="f5911-145">**Lync Administrator:** Overall enterprise administrator for Lync Server 2013 responsible for deployment.</span></span>

  - <span data-ttu-id="f5911-146">**Operations Manager:** 일상적인 작업 관리를 담당 하는 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="f5911-146">**Operations Manager:** User responsible for managing day-to-day operations.</span></span>

  - <span data-ttu-id="f5911-147">타사 **개발자 및 파트너:** 타사 개발자는 시스템을 확장 하 고, 특히 그룹 대화, 규정 준수 지원 및 도구, 웹/모바일 클라이언트 및 Bot 개발을 위한 프레임 워크에 대 한 교신 차단 영역 벽 솔루션을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="f5911-147">**Third-party developers and partners:** Third-party developers extend the system, in particular providing an ethical wall solution for group conversations, compliance support and tools, web/mobile clients, and a framework for Bot development.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

