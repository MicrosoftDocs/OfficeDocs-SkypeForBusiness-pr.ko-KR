---
title: 'Lync Server 2013: 응답 그룹 워크플로 만들기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create Response Group workflows
ms:assetid: 41272258-728d-42bd-b4d4-2a499734c720
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425918(v=OCS.15)
ms:contentKeyID: 48183954
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3ba7d989d1733645c7055fb64d6b790212e15e16
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984130"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-response-group-workflows-in-lync-server-2013"></a><span data-ttu-id="d63f6-102">Lync Server 2013에서 응답 그룹 워크플로 만들기</span><span class="sxs-lookup"><span data-stu-id="d63f6-102">Create Response Group workflows in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d63f6-103">_**마지막으로 수정한 주제:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="d63f6-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="d63f6-104">워크플로는 다른 사용자가 전화를 건 시간으로 울릴 때 까지의 통화 동작을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="d63f6-104">A workflow defines the behavior of a call from the time that the phone rings to the time that someone answers the call.</span></span> <span data-ttu-id="d63f6-105">워크플로는 통화를 보류 하는 데 사용할 큐를 지정 하 고, 헌트 그룹 또는 대화형 응답 그룹에 사용할 질문 및 답변에 사용할 라우팅 방법을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d63f6-105">The workflow specifies the queue to use for holding the call, and specifies the routing method to use for hunt groups or the questions and answers to use for interactive response groups.</span></span> <span data-ttu-id="d63f6-106">워크플로는 환영 메시지, 보류 중인 음악, 업무 시간, 휴일 등의 설정도 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="d63f6-106">A workflow also defines settings such as a welcome message, music on hold, business hours, and holidays.</span></span>

<span data-ttu-id="d63f6-107">응답 그룹 구성 도구를 사용 하 여 워크플로를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d63f6-107">You use the Response Group Configuration Tool to create workflows.</span></span> <span data-ttu-id="d63f6-108">Lync Server 제어판의 응답 그룹 페이지에서 응답 그룹 구성 도구에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d63f6-108">You can access the Response Group Configuration Tool from the Response Group page of Lync Server Control Panel.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d63f6-109">에이전트 그룹과 큐를 사용 하는 워크플로를 만들기 전에 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d63f6-109">You must create agent groups and queues before you create a workflow that uses them.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="d63f6-110">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="d63f6-110">In This Section</span></span>

  - [<span data-ttu-id="d63f6-111">Lync Server 2013에서 헌트 그룹 워크플로 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="d63f6-111">Create or modify a hunt group workflow in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-hunt-group-workflow.md)

  - [<span data-ttu-id="d63f6-112">Lync Server 2013에서 대화형 음성 응답 통화 흐름 설계</span><span class="sxs-lookup"><span data-stu-id="d63f6-112">Design interactive voice response call flows in Lync Server 2013</span></span>](lync-server-2013-design-interactive-voice-response-call-flows.md)

  - [<span data-ttu-id="d63f6-113">Lync Server 2013에서 대화형 워크플로 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="d63f6-113">Create or modify an interactive workflow in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-an-interactive-workflow.md)

</div>

<div>

## <a name="related-sections"></a><span data-ttu-id="d63f6-114">관련 단원</span><span class="sxs-lookup"><span data-stu-id="d63f6-114">Related Sections</span></span>

  - [<span data-ttu-id="d63f6-115">Lync Server 2013에서 응답 그룹 에이전트 그룹 만들기</span><span class="sxs-lookup"><span data-stu-id="d63f6-115">Create Response Group agent groups Lync Server 2013</span></span>](lync-server-2013-create-response-group-agent-groups.md)

  - [<span data-ttu-id="d63f6-116">Lync Server 2013에서 응답 그룹 큐 만들기</span><span class="sxs-lookup"><span data-stu-id="d63f6-116">Create Response Group queues in Lync Server 2013</span></span>](lync-server-2013-create-response-group-queues.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

