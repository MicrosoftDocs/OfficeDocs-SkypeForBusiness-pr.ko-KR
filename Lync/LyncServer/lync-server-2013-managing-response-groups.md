---
title: 'Lync Server 2013: 응답 그룹 관리'
description: 'Lync Server 2013: 응답 그룹 관리'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing response groups
ms:assetid: 5a804d7d-3c1a-4647-a0e0-d5c4c8c23b73
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520996(v=OCS.15)
ms:contentKeyID: 48184222
ms.date: 02/01/2018
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 138ece386d55895893402e5a1fdead58790504f5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572634"
---
# <a name="managing-response-groups-in-lync-server-2013"></a><span data-ttu-id="5ac50-103">Lync Server 2013에서 응답 그룹 관리</span><span class="sxs-lookup"><span data-stu-id="5ac50-103">Managing response groups in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5ac50-104">_**마지막으로 수정 된 항목:** 2018-02-01_</span><span class="sxs-lookup"><span data-stu-id="5ac50-104">_**Topic Last Modified:** 2018-02-01_</span></span>

<span data-ttu-id="5ac50-105">응답 그룹은 지원 센터 등의 특정 위치로 건 통화를 대기시켰다가 *에이전트*라는 지정된 사용자 그룹으로 라우팅할 수 있도록 하는 통화 관리 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="5ac50-105">Response groups are a call management feature that enables you to queue calls that are made to a specific area, such as a Help Desk, and then route the calls to a designated group of people, called *agents*.</span></span>

<span data-ttu-id="5ac50-106">응답 그룹을 관리하려면 전화를 건 시간부터 에이전트가 전화를 받을 때까지 수행되는 작업을 정의하는 에이전트 그룹, 큐 및 워크플로를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="5ac50-106">To manage response groups, you configure agent groups, queues, and workflows, which define what happens to a call from the time it is placed until an agent answers it.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5ac50-107">응답 그룹 배포의 단일 풀에 300 개 보다 많은 워크플로가 있는 경우 Lync Server 관리 셸 cmdlet을 사용 하 여 워크플로를 만드는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="5ac50-107">If you have more than 300 workflows in a single pool in your Response Group deployment, it is better to use Lync Server Management Shell cmdlets to create the workflows.</span></span> <span data-ttu-id="5ac50-108">워크플로가 300개보다 많은 풀에 대해 응답 그룹 구성 도구를 사용하여 워크플로를 만드는 경우 웹 페이지 로드 시간이 오래 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ac50-108">If you use the Response Group Configuration Tool to create workflows for a pool that has more than 300 workflows, the webpage takes a long time to load.</span></span> <span data-ttu-id="5ac50-109">큐를 통해 워크플로와 간접적으로 연결 된 에이전트의 수는 페이지 로드에 비례적으로 영향을 주는 것도 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ac50-109">The number of agents that are indirectly associated with workflows through the queues also has a proportional effect on page loading.</span></span>



</div>

<span data-ttu-id="5ac50-110">이 섹션의 항목에서는 배포에서 응답 그룹 응용 프로그램을 사용자 지정 하 고 유지 관리 하기 위해 수행할 수 있는 작업에 대 한 단계별 절차를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ac50-110">Topics in this section provide step-by-step procedures for tasks that you can perform to customize and maintain the Response Group application in your deployment</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="5ac50-111">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="5ac50-111">In This Section</span></span>

  - [<span data-ttu-id="5ac50-112">Lync Server 2013에서 응답 그룹 에이전트 그룹 관리</span><span class="sxs-lookup"><span data-stu-id="5ac50-112">Managing Response Group agent groups in Lync Server 2013</span></span>](lync-server-2013-managing-response-group-agent-groups.md)

  - [<span data-ttu-id="5ac50-113">Lync Server 2013에서 응답 그룹 큐 관리</span><span class="sxs-lookup"><span data-stu-id="5ac50-113">Managing Response Group queues in Lync Server 2013</span></span>](lync-server-2013-managing-response-group-queues.md)

  - [<span data-ttu-id="5ac50-114">Lync Server 2013에서 응답 그룹 워크플로 관리</span><span class="sxs-lookup"><span data-stu-id="5ac50-114">Managing Response Group workflows in Lync Server 2013</span></span>](lync-server-2013-managing-response-group-workflows.md)

  - [<span data-ttu-id="5ac50-115">Lync Server 2013에서 응용 프로그램 수준 응답 그룹 설정 관리</span><span class="sxs-lookup"><span data-stu-id="5ac50-115">Managing application-level Response Group settings in Lync Server 2013</span></span>](lync-server-2013-managing-application-level-response-group-settings.md)

  - [<span data-ttu-id="5ac50-116">Lync Server 2013의 새 풀로 응답 그룹 이동</span><span class="sxs-lookup"><span data-stu-id="5ac50-116">Moving response groups to a new pool in Lync Server 2013</span></span>](lync-server-2013-moving-response-groups-to-a-new-pool.md)

  - [<span data-ttu-id="5ac50-117">재해 발생 시 Lync Server 2013의 응답 그룹 관리</span><span class="sxs-lookup"><span data-stu-id="5ac50-117">Managing response groups in Lync Server 2013 during a disaster</span></span>](lync-server-2013-managing-response-groups-during-a-disaster.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

