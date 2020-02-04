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
ms.openlocfilehash: 6001e8b6301df1863de21e0d88369116cef03ff5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756092"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-response-group-agent-groups-in-lync-server-2013"></a><span data-ttu-id="3b36d-102">Lync Server 2013에서 응답 그룹 에이전트 그룹 관리</span><span class="sxs-lookup"><span data-stu-id="3b36d-102">Managing Response Group agent groups in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3b36d-103">_**마지막으로 수정한 주제:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="3b36d-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="3b36d-104">에이전트 그룹은 응답 그룹에 대 한 통화에 응답 하도록 지정 된 사용자 그룹으로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b36d-104">An agent group consists of a group of people who are designated to answer calls to a response group.</span></span> <span data-ttu-id="3b36d-105">에이전트 그룹을 만들 때 그룹에 할당 된 에이전트를 선택 하 고 라우팅 메서드, 에이전트에서 그룹에 로그인 할 수 있는지 여부 등의 추가 그룹 설정을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b36d-105">When you create an agent group, you select the agents who are assigned to the group and specify additional group settings, such as the routing method and whether an agent can sign in to and out of the group.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3b36d-106">사용자가 Enterprise Voice를 사용 하도록 설정 해야 에이전트 그룹에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b36d-106">Users must be enabled for Enterprise Voice before you can add them to agent groups.</span></span> <span data-ttu-id="3b36d-107">엔터프라이즈 음성에 대 한 사용자를 설정 하는 방법에 대 한 자세한 내용은 <A href="lync-server-2013-enable-users-for-enterprise-voice.md">Lync Server 2013에서 엔터프라이즈 음성 사용자 사용</A>을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3b36d-107">For details about how to enable a user for Enterprise Voice, see <A href="lync-server-2013-enable-users-for-enterprise-voice.md">Enable users for Enterprise Voice in Lync Server 2013</A>.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="3b36d-108">온-프레미스 사용자만 에이전트 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b36d-108">Only on-premises users can be agents.</span></span> <span data-ttu-id="3b36d-109">에이전트가 온-프레미스에서 온라인으로 이동 하는 경우 응답 그룹 통화는 해당 에이전트로 라우팅되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3b36d-109">If an agent is moved from on-premises to online, Response Group calls will not be routed to that agent.</span></span>



</div>

<span data-ttu-id="3b36d-110">그룹에 로그인 하 여 Lync Server에 로그인 하거나 로그 아웃 하는 것과는 다른 에이전트를 *공식 에이전트*라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b36d-110">An agent who must sign in and out of the group, which is different from signing in or out of Lync Server, is called a *formal agent*.</span></span> <span data-ttu-id="3b36d-111">정식 에이전트는 그룹으로 라우팅되는 통화를 수신 하기 전에 먼저 그룹에 로그인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b36d-111">Formal agents must be signed in to the group before they can receive calls that are routed to the group.</span></span> <span data-ttu-id="3b36d-112">이는 파트 시간 단위로 그룹에서 전화를 받는 에이전트에 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b36d-112">This can be useful for agents who answer calls from the group on a part-time basis.</span></span> <span data-ttu-id="3b36d-113">공식 에이전트는 Lync 2013에서 메뉴 항목을 클릭 하 여 Windows Internet Explorer 인터넷 브라우저를 열고 웹 페이지 콘솔을 표시 하 여 그룹에 로그인 하 고 로그 아웃 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b36d-113">Formal agents sign in and out of their groups by clicking a menu item in Lync 2013 to open the Windows Internet Explorer Internet browser and display a webpage console.</span></span>

<span data-ttu-id="3b36d-114">그룹에 로그인 하거나 로그 아웃 하지 않은 에이전트를 *비공식적인 에이전트*라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b36d-114">An agent who does not sign in or out of the group is called an *informal agent*.</span></span> <span data-ttu-id="3b36d-115">비공식적인 에이전트는 Lync Server에 로그인 할 때 자동으로 그룹에 로그인 되며 그룹에서 로그 아웃할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3b36d-115">Informal agents are automatically signed in to the group when they sign in to Lync Server, and they cannot sign out of the group.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="3b36d-116">사용자를 응답 그룹 에이전트로 지정 하는 경우 개인 정보 모드를 사용 하도록 설정한 경우 "RGS 현재 감시자" 연락처를 검색 하 여 해당 연락처 목록에 추가 해야 한다는 것을 알립니다.</span><span class="sxs-lookup"><span data-stu-id="3b36d-116">When you assign users as response group agents, inform them that, if they have Privacy mode enabled, they need to search for "RGS Presence Watcher" contacts and add them to their Contacts list.</span></span> <span data-ttu-id="3b36d-117">개인 정보 모드를 사용 하도록 설정 했지만 대화 상대 목록에 "RGS 현재 상태 감시자"가 없는 에이전트는 응답 그룹에 대 한 통화를 받을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3b36d-117">Agents who have Privacy mode enabled, but who do not have "RGS Presence Watcher" in their Contacts list, cannot receive calls to the response group.</span></span> <span data-ttu-id="3b36d-118">개인 정보 모드를 사용할 수 없는 에이전트는 영향을 받지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3b36d-118">Agents who do not have Privacy mode enabled are not affected.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="3b36d-119">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="3b36d-119">In This Section</span></span>

  - [<span data-ttu-id="3b36d-120">Lync Server 2013에서 에이전트 그룹 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="3b36d-120">Create or modify an agent group in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-an-agent-group.md)

  - [<span data-ttu-id="3b36d-121">Lync Server 2013에서 에이전트 그룹 삭제</span><span class="sxs-lookup"><span data-stu-id="3b36d-121">Delete an agent group in Lync Server 2013</span></span>](lync-server-2013-delete-an-agent-group.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

