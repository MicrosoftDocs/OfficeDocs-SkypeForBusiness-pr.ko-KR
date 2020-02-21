---
title: 'Lync Server 2013: 응답 그룹 에이전트 그룹 관리'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing Response Group agent groups
ms:assetid: 36084cdc-38f1-4c45-922f-f81c7e86210c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520976(v=OCS.15)
ms:contentKeyID: 48183806
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 015f2e6b8692dd3ea2ea47dda0510f72202c1ebf
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42217924"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="managing-response-group-agent-groups-in-lync-server-2013"></a><span data-ttu-id="d9574-102">Lync Server 2013에서 응답 그룹 에이전트 그룹 관리</span><span class="sxs-lookup"><span data-stu-id="d9574-102">Managing Response Group agent groups in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d9574-103">_**마지막으로 수정 된 항목:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="d9574-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="d9574-p101">에이전트 그룹은 응답 그룹에 대한 통화에 응답하도록 지정된 사용자 그룹으로 구성됩니다. 에이전트 그룹을 만들 때 그룹에 할당되는 에이전트를 선택하고 라우팅 방법 및 에이전트가 그룹에 로그인하고 그룹에서 로그아웃할 수 있는지 여부와 같은 추가 그룹 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d9574-p101">An agent group consists of a group of people who are designated to answer calls to a response group. When you create an agent group, you select the agents who are assigned to the group and specify additional group settings, such as the routing method and whether an agent can sign in to and out of the group.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d9574-106">사용자가 Enterprise Voice를 사용 하도록 설정 해야 에이전트 그룹에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9574-106">Users must be enabled for Enterprise Voice before you can add them to agent groups.</span></span> <span data-ttu-id="d9574-107">사용자가 Enterprise Voice를 사용할 수 있도록 설정 하는 방법에 대 한 자세한 내용은 <A href="lync-server-2013-enable-users-for-enterprise-voice.md">Lync Server 2013에서 사용자에 게 Enterprise Voice 사용</A>을 사용 하도록 설정을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="d9574-107">For details about how to enable a user for Enterprise Voice, see <A href="lync-server-2013-enable-users-for-enterprise-voice.md">Enable users for Enterprise Voice in Lync Server 2013</A>.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="d9574-p103">온-프레미스 사용자만 에이전트가 될 수 있습니다. 에이전트를 온-프레미스에서 온라인으로 이동하면 응답 그룹 통화가 해당 에이전트에게 라우팅되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d9574-p103">Only on-premises users can be agents. If an agent is moved from on-premises to online, Response Group calls will not be routed to that agent.</span></span>



</div>

<span data-ttu-id="d9574-110">Lync Server에 로그인 하거나 외부에서 제외 해야 하는 에이전트를 *공식 에이전트*라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9574-110">An agent who must sign in and out of the group, which is different from signing in or out of Lync Server, is called a *formal agent*.</span></span> <span data-ttu-id="d9574-111">공식 에이전트는 그룹에 로그인해야 그룹에 라우팅된 통화를 수신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9574-111">Formal agents must be signed in to the group before they can receive calls that are routed to the group.</span></span> <span data-ttu-id="d9574-112">이 기능은 비상근직으로 그룹의 호출에 응답하는 에이전트에 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9574-112">This can be useful for agents who answer calls from the group on a part-time basis.</span></span> <span data-ttu-id="d9574-113">공식 에이전트는 Lync 2013에서 메뉴 항목을 클릭 하 여 Windows Internet Explorer 인터넷 브라우저를 열고 웹 페이지 콘솔을 표시 하는 방법으로 그룹에 로그인 하 고 사용자를 제외 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9574-113">Formal agents sign in and out of their groups by clicking a menu item in Lync 2013 to open the Windows Internet Explorer Internet browser and display a webpage console.</span></span>

<span data-ttu-id="d9574-114">그룹에 로그인하거나 그룹에서 로그아웃하지 않는 에이전트를 *비공식 에이전트*라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9574-114">An agent who does not sign in or out of the group is called an *informal agent*.</span></span> <span data-ttu-id="d9574-115">사용자가 Lync Server에 로그인 할 때 비공식 에이전트가 그룹에 자동으로 로그인 되며, 그룹에서 로그 아웃할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d9574-115">Informal agents are automatically signed in to the group when they sign in to Lync Server, and they cannot sign out of the group.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="d9574-p106">사용자를 응답 그룹 에이전트로 할당할 때 해당 사용자가 개인 정보 보호 모드를 사용하도록 설정한 경우 "RGS Presence Watcher" 대화 상대를 검색하여 대화 상대 목록에 추가해야 합니다. 개인 정보 보호 모드를 사용하도록 설정한 에이전트의 대화 상대 목록에 "RGS Presence Watcher"가 없으면 응답 그룹으로 걸려 온 전화를 받을 수 없습니다. 개인 정보 보호 모드를 사용하도록 설정하지 않은 에이전트는 영향을 받지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d9574-p106">When you assign users as response group agents, inform them that, if they have Privacy mode enabled, they need to search for "RGS Presence Watcher" contacts and add them to their Contacts list. Agents who have Privacy mode enabled, but who do not have "RGS Presence Watcher" in their Contacts list, cannot receive calls to the response group. Agents who do not have Privacy mode enabled are not affected.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="d9574-119">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="d9574-119">In This Section</span></span>

  - [<span data-ttu-id="d9574-120">Lync Server 2013에서 에이전트 그룹 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="d9574-120">Create or modify an agent group in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-an-agent-group.md)

  - [<span data-ttu-id="d9574-121">Lync Server 2013에서 에이전트 그룹 삭제</span><span class="sxs-lookup"><span data-stu-id="d9574-121">Delete an agent group in Lync Server 2013</span></span>](lync-server-2013-delete-an-agent-group.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

