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
ms.openlocfilehash: 8e2a8a41b67818cf1f2aec9ec8daaa46eeff783a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763462"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-response-group-agent-groups-lync-server-2013"></a><span data-ttu-id="d3d55-102">Lync Server 2013에서 응답 그룹 에이전트 그룹 만들기</span><span class="sxs-lookup"><span data-stu-id="d3d55-102">Create Response Group agent groups Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d3d55-103">_**마지막으로 수정한 주제:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="d3d55-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="d3d55-104">에이전트 그룹을 만들 때 그룹에 할당 된 에이전트를 선택 하 고 라우팅 메서드, 에이전트에서 그룹에 로그인 할 수 있는지 여부 등의 추가 그룹 설정을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3d55-104">When you create an agent group, you select the agents that are assigned to the group and specify additional group settings, such as the routing method and whether an agent can sign in to and out of the group.</span></span>

<span data-ttu-id="d3d55-105">그룹에 로그인 하 여 Lync Server에 로그인 하거나 로그 아웃 하는 것과는 다른 에이전트를 *공식 에이전트*라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3d55-105">An agent who must sign in and out of the group, which is different from signing in or out of Lync Server, is called a *formal agent*.</span></span> <span data-ttu-id="d3d55-106">공식 에이전트는 그룹으로 라우팅된 통화를 수신 하기 전에 먼저 그룹에 로그인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3d55-106">Formal agents must be signed in to the group before they can receive calls routed to the group.</span></span> <span data-ttu-id="d3d55-107">이는 파트 시간 단위로 그룹에서 전화를 받는 에이전트에 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3d55-107">This can be useful for agents who answer calls from the group on a part-time basis.</span></span> <span data-ttu-id="d3d55-108">공식 에이전트는 Lync 2013에서 메뉴 항목을 클릭 하 여 Windows Internet Explorer 인터넷 브라우저를 열고 웹 페이지 콘솔을 표시 하 여 그룹에 로그인 하 고 로그 아웃 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3d55-108">Formal agents sign in and out of their groups by clicking a menu item in Lync 2013 to open the Windows Internet Explorer Internet browser and display a webpage console.</span></span>

<span data-ttu-id="d3d55-109">그룹에 로그인 하거나 로그 아웃 하지 않은 에이전트를 *비공식적인 에이전트*라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3d55-109">An agent who does not sign in or out of the group is called an *informal agent*.</span></span> <span data-ttu-id="d3d55-110">비공식적인 에이전트는 Lync Server에 로그인 할 때 자동으로 그룹에 로그인 되며 그룹에서 로그 아웃할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d3d55-110">Informal agents are automatically signed in to the group when they sign in to Lync Server, and they cannot sign out of the group.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d3d55-111">온-프레미스 사용자만 에이전트 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3d55-111">Only on-premises users can be agents.</span></span> <span data-ttu-id="d3d55-112">에이전트가 온-프레미스에서 온라인으로 이동 하는 경우 응답 그룹 통화는 해당 에이전트로 라우팅되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d3d55-112">If an agent is moved from on-premises to online, Response Group calls will not be routed to that agent.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="d3d55-113">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="d3d55-113">In This Section</span></span>

[<span data-ttu-id="d3d55-114">Lync Server 2013에서 에이전트 그룹 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="d3d55-114">Create or modify an agent group in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-an-agent-group.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

