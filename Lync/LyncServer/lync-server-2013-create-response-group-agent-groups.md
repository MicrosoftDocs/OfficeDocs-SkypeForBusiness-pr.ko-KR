---
title: 'Lync Server 2013: 응답 그룹 에이전트 그룹 만들기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create Response Group agent groups
ms:assetid: 2a80de17-ead0-46e8-8a27-7a4e233dbde0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520969(v=OCS.15)
ms:contentKeyID: 48183688
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: be70adae85256178defca0269e6663bad76dabfc
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151720"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-response-group-agent-groups-lync-server-2013"></a><span data-ttu-id="b3902-102">응답 그룹 에이전트 그룹 만들기 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b3902-102">Create Response Group agent groups Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b3902-103">_**마지막으로 수정 된 항목:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="b3902-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="b3902-104">에이전트 그룹을 만들 때 그룹에 할당되는 에이전트를 선택하고 라우팅 방법 및 에이전트가 그룹에 로그인하고 그룹에서 로그아웃할 수 있는지 여부와 같은 추가 그룹 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b3902-104">When you create an agent group, you select the agents that are assigned to the group and specify additional group settings, such as the routing method and whether an agent can sign in to and out of the group.</span></span>

<span data-ttu-id="b3902-105">Lync Server에 로그인 하거나 외부에서 제외 해야 하는 에이전트를 *공식 에이전트*라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3902-105">An agent who must sign in and out of the group, which is different from signing in or out of Lync Server, is called a *formal agent*.</span></span> <span data-ttu-id="b3902-106">공식 에이전트는 그룹에 로그인해야 그룹에 라우팅된 통화를 수신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3902-106">Formal agents must be signed in to the group before they can receive calls routed to the group.</span></span> <span data-ttu-id="b3902-107">이 기능은 비상근직으로 그룹의 호출에 응답하는 에이전트에 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3902-107">This can be useful for agents who answer calls from the group on a part-time basis.</span></span> <span data-ttu-id="b3902-108">공식 에이전트는 Lync 2013에서 메뉴 항목을 클릭 하 여 Windows Internet Explorer 인터넷 브라우저를 열고 웹 페이지 콘솔을 표시 하는 방법으로 그룹에 로그인 하 고 사용자를 제외 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3902-108">Formal agents sign in and out of their groups by clicking a menu item in Lync 2013 to open the Windows Internet Explorer Internet browser and display a webpage console.</span></span>

<span data-ttu-id="b3902-109">그룹에 로그인하거나 그룹에서 로그아웃하지 않는 에이전트를 *비공식 에이전트*라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3902-109">An agent who does not sign in or out of the group is called an *informal agent*.</span></span> <span data-ttu-id="b3902-110">사용자가 Lync Server에 로그인 할 때 비공식 에이전트가 그룹에 자동으로 로그인 되며, 그룹에서 로그 아웃할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b3902-110">Informal agents are automatically signed in to the group when they sign in to Lync Server, and they cannot sign out of the group.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b3902-p103">온-프레미스 사용자만 에이전트가 될 수 있습니다. 에이전트를 온-프레미스에서 온라인으로 이동하면 응답 그룹 통화가 해당 에이전트에게 라우팅되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b3902-p103">Only on-premises users can be agents. If an agent is moved from on-premises to online, Response Group calls will not be routed to that agent.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="b3902-113">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="b3902-113">In This Section</span></span>

[<span data-ttu-id="b3902-114">Lync Server 2013에서 에이전트 그룹 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="b3902-114">Create or modify an agent group in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-an-agent-group.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

