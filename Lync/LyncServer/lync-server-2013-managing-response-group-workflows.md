---
title: 'Lync Server 2013: 응답 그룹 워크플로 관리'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Managing Response Group workflows
ms:assetid: 42cfccdd-2844-4875-b4e3-813e1df15f08
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520986(v=OCS.15)
ms:contentKeyID: 48183974
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3a33c20b48bce7b3402ade6df0e6a6250e76193c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981517"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-response-group-workflows-in-lync-server-2013"></a><span data-ttu-id="7f578-102">Lync Server 2013의 응답 그룹 워크플로 관리</span><span class="sxs-lookup"><span data-stu-id="7f578-102">Managing Response Group workflows in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7f578-103">_**마지막으로 수정한 주제:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="7f578-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="7f578-104">응답 그룹 워크플로는 전화가 전화를 건 시점부터 시간이 울릴 때까지 통화 동작을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f578-104">A Response Group workflow defines the behavior of a call from the time that the phone rings to the time that an agent answers the call.</span></span> <span data-ttu-id="7f578-105">워크플로는 큐 및 라우팅 정보를 포함 하며 헌트 그룹 또는 IVR (대화형 음성 응답) 정보를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f578-105">The workflow includes queue and routing information, and includes either hunt group or interactive voice response (IVR) information.</span></span>

<span data-ttu-id="7f578-106">이 섹션의 항목에서는 IVR 워크플로를 디자인 하는 모범 사례와 사용자 지정 된 비즈니스 시간 및 휴일 집합을 만드는 방법, 워크플로를 만들거나 수정 하는 방법, 작업 그룹을 삭제 하는 방법 등에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f578-106">Topics in this section identify best practices for designing IVR workflows, and explain how to create customized business hours and holiday sets, how to create or modify workflows, and how to delete workgroups.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="7f578-107">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="7f578-107">In This Section</span></span>

  - [<span data-ttu-id="7f578-108">Lync Server 2013에서 대화형 음성 응답 통화 흐름 설계</span><span class="sxs-lookup"><span data-stu-id="7f578-108">Design interactive voice response call flows in Lync Server 2013</span></span>](lync-server-2013-design-interactive-voice-response-call-flows.md)

  - [<span data-ttu-id="7f578-109">) Lync Server 2013에서 응답 그룹 비즈니스 시간 정의</span><span class="sxs-lookup"><span data-stu-id="7f578-109">(Optional) Define Response Group business hours in Lync Server 2013</span></span>](lync-server-2013-optional-define-response-group-business-hours.md)

  - [<span data-ttu-id="7f578-110">) Lync Server 2013에서 응답 그룹의 휴일 집합 정의</span><span class="sxs-lookup"><span data-stu-id="7f578-110">(Optional) Define Response Group holiday sets in Lync Server 2013</span></span>](lync-server-2013-optional-define-response-group-holiday-sets.md)

  - [<span data-ttu-id="7f578-111">Lync Server 2013에서 워크플로 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="7f578-111">Create or modify a workflow in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-workflow.md)

  - [<span data-ttu-id="7f578-112">Lync Server 2013에서 워크플로 삭제</span><span class="sxs-lookup"><span data-stu-id="7f578-112">Delete a workflow in Lync Server 2013</span></span>](lync-server-2013-delete-a-workflow.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

