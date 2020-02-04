---
title: 범주를 사용하여 영구 채팅 서버 관리
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Using categories to administer Persistent Chat Server
ms:assetid: dfcb3ad1-da90-467e-b08c-f4e68673b7b5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398988(v=OCS.15)
ms:contentKeyID: 48185628
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 52e56f776969ece55f71355ed7f184dd6dd46a91
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738598"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-categories-to-administer-persistent-chat-server"></a><span data-ttu-id="61622-102">범주를 사용하여 영구 채팅 서버 관리</span><span class="sxs-lookup"><span data-stu-id="61622-102">Using categories to administer Persistent Chat Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="61622-103">_**마지막으로 수정한 주제:** 2013-10-01_</span><span class="sxs-lookup"><span data-stu-id="61622-103">_**Topic Last Modified:** 2013-10-01_</span></span>

<span data-ttu-id="61622-104">영구 채팅 서버 구축은 많은 동시 영구 채팅방을 호스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61622-104">Your Persistent Chat Server deployment can host many concurrent Persistent Chat rooms.</span></span> <span data-ttu-id="61622-105">채팅방은 서버에서 범주 집합으로 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61622-105">Chat rooms can be organized into a set of categories on the server.</span></span> <span data-ttu-id="61622-106">각 채팅방은 한 범주에 속하며 해당 범주의 일부 설정을 상속합니다.</span><span class="sxs-lookup"><span data-stu-id="61622-106">Each chat room belongs to one category, and inherits some settings from that category.</span></span> <span data-ttu-id="61622-107">이러한 구성은 비즈니스 목적에 따라 대화를 식별하는 데 유용한 구조를 만들며 위임된 관리 및 간소화된 관리를 용이하게 합니다.</span><span class="sxs-lookup"><span data-stu-id="61622-107">This organization creates a useful structure for identifying conversations, based on their business purpose, and facilitates delegated administration and simplified management.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="61622-108">대화방의 관리 기능 중 상당수는 사용자를 위해 영구 채팅 (Lync 클라이언트)을 실행 하는 컴퓨터에서 사용할 수 있지만, <STRONG>cspersistentchatadministrator</STRONG> 역할의 영구 채팅 관리자는 Lync Server 제어판 또는 Windows PowerShell cmdlet을 사용 하 여 범주를 만들거나 관리 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="61622-108">Although many of the management features of chat rooms are available in computers running Persistent Chat (Lync client) for the user, Persistent Chat Administrators (in the <STRONG>cspersistentchatadministrator</STRONG> role) must use the Lync Server Control Panel or Windows PowerShell cmdlets to create or manage categories.</span></span>



</div>

<span data-ttu-id="61622-109">영구 채팅 관리자는 Lync Server 제어판 또는 Windows PowerShell cmdlet을 사용 하 여 범주를 만들고 관리 하며 조직의 사용자에 대 한 채팅방에 대 한 액세스를 디자인 합니다.</span><span class="sxs-lookup"><span data-stu-id="61622-109">Persistent Chat administrators use Lync Server Control Panel or Windows PowerShell cmdlets to create and manage categories, and to design access for chat rooms for the users in their organization.</span></span>

<span data-ttu-id="61622-110">한 명 이상의 채팅방을 관리할 수 있는 영구 채팅방 관리자는 Lync 클라이언트를 사용 하 여 회의실을 만들고 관리 하기 위해 회의실 관리 웹 응용 프로그램을 실행할 수 있습니다 (또는 고객이 호출할 사용자 지정 솔루션 및 워크플로를 만들 수 있음).</span><span class="sxs-lookup"><span data-stu-id="61622-110">Persistent Chat room managers, who have the ability to manage one or more chat rooms, can use the Lync client to launch a room management Web application to create and manage rooms (or customers can create custom solutions and workflows to be invoked).</span></span> <span data-ttu-id="61622-111">영구 채팅 관리자는 Lync Server 제어판 또는 Windows PowerShell cmdlet을 사용 하 여 회의실을 만들고 관리할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61622-111">Persistent Chat administrators can also use Lync Server Control Panel or Windows PowerShell cmdlets to create and manage rooms.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="61622-112">영구 채팅방에는 영구 채팅 범주와 같은 이름을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="61622-112">A Persistent Chat room cannot have the same name as a Persistent Chat category.</span></span>



</div>

<span data-ttu-id="61622-p103">채팅방 관리자는 채팅방의 범주 변경을 제외한 모든 채팅방 속성을 변경할 수 있습니다. 채팅방 관리자는 다음 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61622-p103">Chat room managers can make changes to all chat room properties, except for changing the category of the room. They cannot be restricted from performing the following actions:</span></span>

  - <span data-ttu-id="61622-115">채팅방 비활성화</span><span class="sxs-lookup"><span data-stu-id="61622-115">Disabling a chat room</span></span>

  - <span data-ttu-id="61622-116">채팅방 이름 변경</span><span class="sxs-lookup"><span data-stu-id="61622-116">Changing a chat room name</span></span>

  - <span data-ttu-id="61622-117">채팅방 설명 변경</span><span class="sxs-lookup"><span data-stu-id="61622-117">Changing a chat room description</span></span>

  - <span data-ttu-id="61622-118">채팅방 유형 변경(강당 및 일반)</span><span class="sxs-lookup"><span data-stu-id="61622-118">Changing a chat room type (Auditorium versus Normal)</span></span>

  - <span data-ttu-id="61622-119">채팅방의 개인 정보 공개 여부 변경(공개, 비공개 및 비밀)</span><span class="sxs-lookup"><span data-stu-id="61622-119">Changing the privacy of a room (open versus closed versus secret)</span></span>

  - <span data-ttu-id="61622-120">구성원 추가 또는 제거</span><span class="sxs-lookup"><span data-stu-id="61622-120">Adding or removing members</span></span>

  - <span data-ttu-id="61622-121">채팅방 관리자 추가 또는 제거</span><span class="sxs-lookup"><span data-stu-id="61622-121">Adding or removing chat room managers</span></span>

  - <span data-ttu-id="61622-122">추가 기능 추가 또는 제거</span><span class="sxs-lookup"><span data-stu-id="61622-122">Adding or removing an add-in</span></span>

  - <span data-ttu-id="61622-123">초대 등의 설정 변경(범주에서 허용되는 경우)</span><span class="sxs-lookup"><span data-stu-id="61622-123">Changing settings such as invitations (according to what’s permitted by the category)</span></span>

<div>

## <a name="delegated-administration"></a><span data-ttu-id="61622-124">위임 된 관리</span><span class="sxs-lookup"><span data-stu-id="61622-124">Delegated Administration</span></span>

<span data-ttu-id="61622-125">일관 된 채팅방을 만들고 관리 하는 것은 범주를 올바르게 사용 하는 것 보다 훨씬 더 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="61622-125">Creating and managing Persistent Chat rooms is much easier with the correct use of categories.</span></span> <span data-ttu-id="61622-126">영구 채팅 관리자는 각 범주에 대해 **Allowedmembers** 및 **작성자** 를 정의할 수 있으며, 범주에서 만든 모든 채팅방에 적용 되는 기본 채팅방 설정 및 동작을 정의할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61622-126">A Persistent Chat Administrator can define **AllowedMembers** and **Creators** for each category, and can also define the default chat room settings and behaviors that will be applied to all chat rooms created in the category.</span></span> <span data-ttu-id="61622-127">영구 채팅 관리자는 Lync Server 제어판 또는 Windows PowerShell cmdlet을 사용 하 여 범주를 만들고 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="61622-127">Persistent Chat administrators create and manage categories by using Lync Server Control Panel or Windows PowerShell cmdlets.</span></span>

<span data-ttu-id="61622-p105">범주의 작성자로 식별되는 사용자, OU(조직 구성 단위), 사용자 그룹은 해당 범주에서 채팅방을 만들 수 있는 개인과 그룹입니다. 이들은 범주를 만든 후 범주의 **AllowedMembers** 목록에서 사용자, OU 및 사용자 그룹을 채팅방을 관리하고 채팅방에 참가할 관리자 및 구성원으로 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61622-p105">Users, Organizational Units (OUs), and user groups that are identified as Creators of the category are the only individuals and groups that are allowed to create rooms in the category. After the category is created, they can choose users, OUs, and user groups from the category’s **AllowedMembers** list as chat room managers and members to manage and participate in the room.</span></span>

<span data-ttu-id="61622-130">범주에서 만든 채팅방은 범주에 의해 적용 되는 정책 및 설정 (예: 룸의 구성원 자격을 받을 수 있는 사용자, 룸을 관리할 수 있는 사람, 파일 업로드가 허용 되는지 여부, 초대 전송 여부 등)을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="61622-130">Chat rooms that are created in a category adhere to the policies and settings enforced by the category (such as who can be in the room’s membership, who can manage the room, whether file uploads are allowed, whether invitations are sent, and so on).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

