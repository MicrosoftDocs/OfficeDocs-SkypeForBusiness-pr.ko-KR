---
title: 영구 채팅 구성원 자격 이해
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Understanding Persistent Chat membership
ms:assetid: 900392d6-6e9f-4dae-93d6-39d7474409ef
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398730(v=OCS.15)
ms:contentKeyID: 48184781
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e525d93e58e73304b9d3a26248418c88b5e9ea79
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976206"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="understanding-persistent-chat-membership"></a><span data-ttu-id="dfecd-102">영구 채팅 구성원 자격 이해</span><span class="sxs-lookup"><span data-stu-id="dfecd-102">Understanding Persistent Chat membership</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dfecd-103">_**마지막으로 수정한 주제:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="dfecd-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="dfecd-104">영구 채팅방에 대 한 사용자 액세스는 구성원에 의해 관리 됩니다. 사용자가 메시지를 게시 하 고 읽을 수 있으려면 채팅방의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dfecd-104">User access to Persistent Chat rooms is managed by membership; users must be members of a chat room to be able to post and read messages.</span></span> <span data-ttu-id="dfecd-105">채팅방을 지정 하는 **발표자** 만 **Auditorium 채팅방에 게시**를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dfecd-105">Only **Presenters** who have a designated affiliation with chat rooms are allowed to use **Posting to Auditorium rooms**.</span></span> <span data-ttu-id="dfecd-106">Auditorium은 발표자만 게시할 수 있고 모든 사람이 읽을 수 있는 채팅방의 한 유형입니다 ( **일반**).</span><span class="sxs-lookup"><span data-stu-id="dfecd-106">An auditorium is a type of chat room (the other is **Normal**), where only Presenters can post and everyone can read.</span></span>

<span data-ttu-id="dfecd-107">또한 영구 채팅 채팅방은 범주의 규칙에 따라 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="dfecd-107">In addition, Persistent Chat rooms operate under the rules of a category.</span></span> <span data-ttu-id="dfecd-108">범주에 대 한 자세한 내용은 [Lync Server 2013에서 범주, 회의실, 추가 기능 관리](lync-server-2013-managing-categories-rooms-and-add-ins.md)및이 항목의 뒷부분에 나오는 "범주 범위 작동 방식" 및 "방 범주 전략" 섹션을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="dfecd-108">For details about categories, see [Managing categories, rooms, and add-ins in Lync Server 2013](lync-server-2013-managing-categories-rooms-and-add-ins.md), and also the sections "How Category Scoping Works" and "Room Category Strategies" later in this topic.</span></span>

<span data-ttu-id="dfecd-109">영구 채팅 관리자는 채팅방 범주를 만들고 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dfecd-109">A Persistent Chat administrator can create and manage chat room categories.</span></span> <span data-ttu-id="dfecd-110">채팅방 범주를 만들고 관리 하는 과정에서 영구 채팅 관리자는 특정 범주에 해당 하는 채팅방의 구성원 또는 작성자가 될 수 있는 주체 (Active Directory 도메인 서비스 그룹, 컨테이너 및 사용자)를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dfecd-110">As part of creating and managing chat room categories, the Persistent Chat administrator can configure principals (Active Directory Domain Services groups, containers, and users) that have access to be members or creators of chat rooms of a particular category.</span></span>

<div>

## <a name="active-directory-domain-services-and-persistent-chat"></a><span data-ttu-id="dfecd-111">Active Directory 도메인 서비스 및 영구 채팅</span><span class="sxs-lookup"><span data-stu-id="dfecd-111">Active Directory Domain Services and Persistent Chat</span></span>

<span data-ttu-id="dfecd-112">영구 채팅 서버는 내부 영구 채팅 사용자 풀의 Active Directory에 의존 합니다.</span><span class="sxs-lookup"><span data-stu-id="dfecd-112">Persistent Chat Server relies on Active Directory for the pool of internal Persistent Chat users.</span></span> <span data-ttu-id="dfecd-113">영구 채팅 (클라이언트)을 설치한 후에는 룸 범주에 사용자 및 사용자 그룹의 도메인을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dfecd-113">After you install Persistent Chat (client), you can add domains of users and user groups to the room category.</span></span> <span data-ttu-id="dfecd-114">그런 다음 이러한 사용자 및 그룹을 룸 범주의 구성원에 게 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dfecd-114">You can then add these users and groups to the membership of your room categories.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="dfecd-115">영구 채팅방을 변경 하려는 사용자에 게 중복 되는 이름이 없는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dfecd-115">You must ensure that there are no duplicate names for users who want to make changes to their Persistent Chat room(s).</span></span> <span data-ttu-id="dfecd-116">중복 된 사용자 이름이 있는 경우 다른 이름으로 변경 하 여 사용자가 변경 하지 못하도록 차단 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="dfecd-116">If duplicate user names exist, change them to different names to unblock users from making those changes.</span></span> <span data-ttu-id="dfecd-117">Active Directory에서 사용자의 이름이 중복 되 고 해당 룸에서 변경 하려고 하면 사용자에 게 확인을 위해 관리자에 게 문의 하 라는 오류 메시지가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="dfecd-117">If a user has duplicate names in Active Directory and tries to make changes in their room(s), an error message appears prompting the user to contact the administrator for resolution.</span></span>



</div>

</div>

<div>

## <a name="how-category-scoping-works"></a><span data-ttu-id="dfecd-118">범주 범위 작동 방식</span><span class="sxs-lookup"><span data-stu-id="dfecd-118">How Category Scoping Works</span></span>

<span data-ttu-id="dfecd-119">범주는 해당 범주에 속하는 영구 채팅방의 구성원 목록에 있는 모든 사용자와 그룹을 해당 **allowedmembers** 속성에 따라 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="dfecd-119">A category specifies all the users and groups that can be members in a membership list of a Persistent Chat room in that category, based on its **AllowedMembers** property.</span></span> <span data-ttu-id="dfecd-120">예를 들어 범주의 **allowedmembers** 를 contoso.com로 설정한 경우 *contoso* 의 모든 그룹 또는 사용자를 해당 범주의 채팅방에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dfecd-120">For example, if you set the category’s **AllowedMembers** to contoso.com, you can add any group or user at *Contoso* as a member to chat rooms in that category.</span></span> <span data-ttu-id="dfecd-121">범주의 **Allowedmembers** 를 *Sales*로 설정한 경우이 메일 그룹의 그룹과 사용자만 구성원으로 추가 하 여 해당 범주의 채팅방을 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dfecd-121">If you set the **AllowedMembers** on a category to *Sales*, only groups and users in this distribution list can be added as members to chat rooms in that category.</span></span> <span data-ttu-id="dfecd-122">마찬가지로, **작성자** 속성을 사용 하 여 해당 범주에서 채팅방을 만들 수 있는 사람을 제어할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dfecd-122">Similarly, the **Creators** property enables you to control who can create chat rooms in that category.</span></span> <span data-ttu-id="dfecd-123">채팅방을 만든 후에는 **Allowedmembers** 그룹의 모든 사용자를 해당 채팅방에서 진행 중인 관리 작업에 대 한 **관리자로** 지정할 수 있습니다 (예: 회원 변경 및 승인).</span><span class="sxs-lookup"><span data-stu-id="dfecd-123">After the chat room is created, anyone from the **AllowedMembers** group can be designated as a **Manager** for ongoing management operations on the rooms (for example, membership changes and approvals).</span></span>

<span data-ttu-id="dfecd-124">범주에 대해 **Allowedmembers** 및 **작성자** 를 정의 하면 다음과 같은 이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dfecd-124">Defining **AllowedMembers** and **Creators** for a category has the following benefits:</span></span>

  - <span data-ttu-id="dfecd-125">이 범주의 모든 채팅방은 범주 수준에 설정 된 제한 사항에 의해 바인딩됩니다.</span><span class="sxs-lookup"><span data-stu-id="dfecd-125">All chat rooms in this category are bound by the restrictions set at the category level.</span></span> <span data-ttu-id="dfecd-126">이 방법을 사용 하 여 비즈니스 요구 및 액세스 정책에 따라 채팅방을 구분할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dfecd-126">You can use this to segregate chat rooms based on business need and access policies.</span></span>

  - <span data-ttu-id="dfecd-127">**작성자** 목록에 있는 사용자는 해당 범주에 새 채팅방을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dfecd-127">A user who is in the **Creators** list can create new chat rooms in that category.</span></span> <span data-ttu-id="dfecd-128">조직에서 제한 된 인원의 직원이 채팅방을 만들 수 있는 시스템을 구현 하려는 경우이 컨트롤을 사용 하 여 해당 요구 사항을 충족 시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dfecd-128">If you want to implement a system where a restricted number of personnel in the organization can create chat rooms, this control can be used to meet that requirement.</span></span>

</div>

<div>

## <a name="room-category-strategies"></a><span data-ttu-id="dfecd-129">방 범주 전략</span><span class="sxs-lookup"><span data-stu-id="dfecd-129">Room Category Strategies</span></span>

<span data-ttu-id="dfecd-130">범주의 **Allowedmembers** 는이 범주에서 영구 채팅방을 사용할 모든 사용자를 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dfecd-130">A category’s **AllowedMembers** must include all users who will use any Persistent Chat room in this category.</span></span> <span data-ttu-id="dfecd-131">비즈니스 데이터를 보호 하 고 적절 한 수준의 액세스를 보장 하는 요구 사항에 따라 하나 이상의 범주를 정의 하 여 채팅방에서 검색 하 고 참여할 수 있는 사용자를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dfecd-131">Depending on your requirements to protect business data and ensure the appropriate level of access, you may want to define one or more categories to specify who can search and participate in rooms.</span></span> <span data-ttu-id="dfecd-132">특정 사용자 (중앙 헬프데스크 또는 전일 근무 직원만 해당)만 회의실을 만들 수 있도록 허용 하려면 범주 **작성자** 의 범위를 지정 하 여 해당 요구 사항을 충족 시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dfecd-132">If you want to allow only a particular set of users (a central helpdesk, or only full-time employees) to create rooms, you can scope the **Creators** of a category to satisfy that requirement.</span></span>

<span data-ttu-id="dfecd-133">범주를 사용 하 여 윤리적인 벽을 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dfecd-133">Categories can also be used to create ethical walls.</span></span> <span data-ttu-id="dfecd-134">윤리적인 벽은 조직에 대 한 모든 충돌을 방지 합니다.</span><span class="sxs-lookup"><span data-stu-id="dfecd-134">Ethical walls prevent any conflict of interest in an organization.</span></span> <span data-ttu-id="dfecd-135">예를 들어 관리자는 traders의 범주에 있는 채팅방만 만들 수 있으며, 다른 범주에 있는 채팅방은 분석가만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dfecd-135">For example, an administrator can create chat rooms in a category for traders only, whereas chat rooms in another category can be used by analysts only.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="dfecd-136">Lync Server 2013, 영구 채팅 서버에서는 페더레이션 사용자에 대 한 액세스를 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dfecd-136">In Lync Server 2013, Persistent Chat Server, we do not support access to federated users.</span></span> <span data-ttu-id="dfecd-137">이전 버전의 영구 채팅 서버에 있는 페더레이션 사용자가 채팅을 하는 경우에는 마이그레이션됩니다.</span><span class="sxs-lookup"><span data-stu-id="dfecd-137">If there are chats from federated users in previous versions of Persistent Chat Server, they will be migrated.</span></span> <span data-ttu-id="dfecd-138">페더레이션 사용자는 사용 하지 않는 사용자로 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dfecd-138">The federated users are added as disabled principals.</span></span>



</div>

</div>

<div>

## <a name="narrowing-the-members-to-user-groups"></a><span data-ttu-id="dfecd-139">구성원을 사용자 그룹으로 축소</span><span class="sxs-lookup"><span data-stu-id="dfecd-139">Narrowing the Members to User Groups</span></span>

<span data-ttu-id="dfecd-140">도메인을 범주에 추가 하는 경우 해당 도메인에 그룹 개체가 포함 된 사용자 그룹을 사용할 수 있으므로 해당 항목을 해당 범주의 룸 구성원으로 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dfecd-140">When you add a domain to a category, the user groups whose group objects are contained in that domain are available to you so that you can specify them as members of rooms in that category.</span></span>

<span data-ttu-id="dfecd-141">일반적으로 범주 노드의 **Allowedmembers** 및 **작성자**를 정의 하기 위해 도메인 및 조직 구성 단위와 같은 Active Directory 컨테이너를 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="dfecd-141">We recommend, as a general rule, that you use Active Directory containers, such as domains and organizational units, for defining a category’s **AllowedMembers** and **Creators**.</span></span> <span data-ttu-id="dfecd-142">모든 도메인의 개체를 **Allowedmembers** 또는 **제작자** 목록에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dfecd-142">You can add objects from any domain to an **AllowedMembers** or **Creators** list.</span></span> <span data-ttu-id="dfecd-143">이 범주 아래에 있는 룸에는 **Allowedmembers** 또는 **작성자** 목록 내의 개체만 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dfecd-143">Only objects within the **AllowedMembers** or **Creators** list can be added to rooms under that category.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

