---
title: 'Lync Server 2013: 워크플로 만들기 또는 수정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a workflow
ms:assetid: 5ac1c0f3-e82f-40ca-b972-91950e38c05b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520997(v=OCS.15)
ms:contentKeyID: 48184225
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9d6ca3eb81d44f5776178ba8ff631a960ba85874
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151800"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-workflow-in-lync-server-2013"></a><span data-ttu-id="8ec05-102">Lync Server 2013에서 워크플로 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="8ec05-102">Create or modify a workflow in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8ec05-103">_**마지막으로 수정 된 항목:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="8ec05-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="8ec05-104">Lync Server 2013에서는 두 가지 유형의 워크플로 (헌트 그룹 및 IVR (대화형 음성 응답)를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ec05-104">Lync Server 2013 supports two types of workflows: hunt group and interactive voice response (IVR).</span></span> <span data-ttu-id="8ec05-105">워크플로를 만들 때는 응답 그룹 구성 도구를 사용 하 여 응답 그룹 응용 프로그램에서 발신자에 게 요청할 큐와 환영 메시지, 보류 중인 음악, 업무 시간 및 질문 등의 기타 설정을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ec05-105">When you create a workflow, you use the Response Group Configuration Tool to specify the queue to use and other settings, such as a welcome message, music on hold, business hours, and questions that the Response Group application asks the caller.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8ec05-p102">에이전트 그룹 및 큐를 먼저 만든 후에 해당 그룹과 큐를 사용하는 워크플로를 만들어야 합니다. 여러 워크플로에 사용할 수 있는 미리 정의된 업무 시간 및 휴일을 만들려면 해당 시간 및 휴일을 사용하는 워크플로를 만들기 전에 시간과 휴일을 먼저 정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ec05-p102">You must create agent groups and queues before you create a workflow that uses them. If you want to create predefined business hours and holidays that you can use for multiple workflows, you must also define these hours and holidays before you create a workflow that uses them.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="8ec05-108">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="8ec05-108">In This Section</span></span>

  - [<span data-ttu-id="8ec05-109">Lync Server 2013에서 헌트 그룹 워크플로 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="8ec05-109">Create or modify a hunt group workflow in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-hunt-group-workflow.md)

  - [<span data-ttu-id="8ec05-110">Lync Server 2013에서 대화형 워크플로 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="8ec05-110">Create or modify an interactive workflow in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-an-interactive-workflow.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="8ec05-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8ec05-111">See Also</span></span>


[<span data-ttu-id="8ec05-112">Lync Server 2013에서 에이전트 그룹 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="8ec05-112">Create or modify an agent group in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-an-agent-group.md)  
[<span data-ttu-id="8ec05-113">Lync Server 2013에서 큐 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="8ec05-113">Create or modify a queue in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-queue.md)  
[<span data-ttu-id="8ec05-114">반드시 Lync Server 2013에서 응답 그룹 휴일 집합 정의</span><span class="sxs-lookup"><span data-stu-id="8ec05-114">(Optional) Define Response Group holiday sets in Lync Server 2013</span></span>](lync-server-2013-optional-define-response-group-holiday-sets.md)  


[<span data-ttu-id="8ec05-115">반드시 Lync Server 2013에서 응답 그룹 업무 시간 정의</span><span class="sxs-lookup"><span data-stu-id="8ec05-115">(Optional) Define Response Group business hours in Lync Server 2013</span></span>](lync-server-2013-optional-define-response-group-business-hours.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

