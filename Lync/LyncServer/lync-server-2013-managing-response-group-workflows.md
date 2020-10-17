---
title: 'Lync Server 2013: 응답 그룹 워크플로 관리'
description: 'Lync Server 2013: 응답 그룹 워크플로를 관리 하는 중입니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing Response Group workflows
ms:assetid: 42cfccdd-2844-4875-b4e3-813e1df15f08
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520986(v=OCS.15)
ms:contentKeyID: 48183974
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2223fed2b5b030a2c92e0b958ae8545a7717f848
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560414"
---
# <a name="managing-response-group-workflows-in-lync-server-2013"></a><span data-ttu-id="e9c1c-103">Lync Server 2013에서 응답 그룹 워크플로 관리</span><span class="sxs-lookup"><span data-stu-id="e9c1c-103">Managing Response Group workflows in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e9c1c-104">_**마지막으로 수정 된 항목:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="e9c1c-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="e9c1c-105">응답 그룹 워크플로는 전화가 전화를 걸 때부터 상담원이 통화에 응답 한 시간까지 호출 동작을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9c1c-105">A Response Group workflow defines the behavior of a call from the time that the phone rings to the time that an agent answers the call.</span></span> <span data-ttu-id="e9c1c-106">워크플로에는 큐 및 라우팅 정보가 포함되며, 헌트 그룹 또는 IVR(대화형 음성 응답) 정보도 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="e9c1c-106">The workflow includes queue and routing information, and includes either hunt group or interactive voice response (IVR) information.</span></span>

<span data-ttu-id="e9c1c-107">이 섹션의 항목은 IVR 워크플로 디자인을 위한 모범 사례를 식별하고 사용자 지정된 업무 시간 및 휴일 집합을 만들고, 워크플로를 만들거나 수정하고, 작업 그룹을 삭제하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e9c1c-107">Topics in this section identify best practices for designing IVR workflows, and explain how to create customized business hours and holiday sets, how to create or modify workflows, and how to delete workgroups.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="e9c1c-108">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="e9c1c-108">In This Section</span></span>

  - [<span data-ttu-id="e9c1c-109">Lync Server 2013의 대화형 음성 응답 통화 흐름 디자인</span><span class="sxs-lookup"><span data-stu-id="e9c1c-109">Design interactive voice response call flows in Lync Server 2013</span></span>](lync-server-2013-design-interactive-voice-response-call-flows.md)

  - [<span data-ttu-id="e9c1c-110">반드시 Lync Server 2013에서 응답 그룹 업무 시간 정의</span><span class="sxs-lookup"><span data-stu-id="e9c1c-110">(Optional) Define Response Group business hours in Lync Server 2013</span></span>](lync-server-2013-optional-define-response-group-business-hours.md)

  - [<span data-ttu-id="e9c1c-111">반드시 Lync Server 2013에서 응답 그룹 휴일 집합 정의</span><span class="sxs-lookup"><span data-stu-id="e9c1c-111">(Optional) Define Response Group holiday sets in Lync Server 2013</span></span>](lync-server-2013-optional-define-response-group-holiday-sets.md)

  - [<span data-ttu-id="e9c1c-112">Lync Server 2013에서 워크플로 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="e9c1c-112">Create or modify a workflow in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-workflow.md)

  - [<span data-ttu-id="e9c1c-113">Lync Server 2013에서 워크플로 삭제</span><span class="sxs-lookup"><span data-stu-id="e9c1c-113">Delete a workflow in Lync Server 2013</span></span>](lync-server-2013-delete-a-workflow.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

