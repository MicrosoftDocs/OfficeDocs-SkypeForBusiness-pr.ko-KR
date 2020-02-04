---
title: Lync Server 2013 대규모 모임 지원
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Support for large meetings
ms:assetid: 8f0446d5-1ed9-4ea0-bb97-6c062a98a1eb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205090(v=OCS.15)
ms:contentKeyID: 48184820
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d6a8da2c58cc650fa0d2ddb7fe71ba62b4b29af9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731748"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="support-for-large-meetings-in-lync-server-2013"></a><span data-ttu-id="e4d5a-102">Lync Server 2013의 대규모 모임 지원</span><span class="sxs-lookup"><span data-stu-id="e4d5a-102">Support for large meetings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e4d5a-103">_**마지막으로 수정한 주제:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="e4d5a-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="e4d5a-104">Lync Server 2013는 PowerPoint 프레젠테이션 공유를 포함 하 여 오디오/비디오 (A/V) 회의를 사용 하 여 최대 1000 참가자와 모임을 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e4d5a-104">Lync Server 2013 can support meetings with up to 1000 participants using audio/video (A/V) conferencing, including sharing PowerPoint presentations.</span></span> <span data-ttu-id="e4d5a-105">이 지원에는 대규모 모임을 지원 하도록 구성 된 전용 풀이 필요 하며 한 번에 하나의 대규모 모임만 호스트할 수 있도록 관리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e4d5a-105">This support requires a dedicated pool configured to support large meetings and managed in a way that ensures hosting of only a single large meeting at a time.</span></span>

<span data-ttu-id="e4d5a-106">이 섹션에서는 전용 Lync Server 2013 풀을 사용 하 여 대규모 모임을 지원 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4d5a-106">This section describes how to support large meetings using a dedicated Lync Server 2013 pool.</span></span> <span data-ttu-id="e4d5a-107">토폴로지, 하드웨어, 소프트웨어, 구성 요구 사항 등의 전용 풀에 대 한 구현 요구 사항 및 확장성에 대 한 고려 사항에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4d5a-107">It describes scalability considerations and the implementation requirements for a dedicated pool, including topology, hardware, software, and configuration requirements.</span></span> <span data-ttu-id="e4d5a-108">또한 대규모 모임 지원, Lync Server 엔지니어링 팀에서 수행한 서버 확장성 테스트의 테스트 메서드 및 결과에 대 한 요약 및 지원에 대 한 질문과 대답 (faq)에 대 한 모범 사례 권장 사항 집합을 제공 합니다. 모임이 대량으로 진행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e4d5a-108">It also provides a set of best practice recommendations for supporting large meetings, a summary of the test methods and results of server scalability testing conducted by the Lync Server engineering team, and the answers to frequently asked questions about support for large meetings.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="e4d5a-109">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="e4d5a-109">In This Section</span></span>

  - [<span data-ttu-id="e4d5a-110">Lync Server 2013의 회의 확장성 개요</span><span class="sxs-lookup"><span data-stu-id="e4d5a-110">Overview of conferencing scalability in Lync Server 2013</span></span>](lync-server-2013-conferencing-scalability-overview.md)

  - [<span data-ttu-id="e4d5a-111">Lync Server 2013를 사용 하 여 대용량 모임 지원</span><span class="sxs-lookup"><span data-stu-id="e4d5a-111">Supporting large meetings using Lync Server 2013</span></span>](lync-server-2013-supporting-large-meetings.md)

  - [<span data-ttu-id="e4d5a-112">Lync Server 2013에 대 한 대용량 모임 지원 FAQ</span><span class="sxs-lookup"><span data-stu-id="e4d5a-112">Large meeting support FAQ for Lync Server 2013</span></span>](lync-server-2013-large-meeting-support-faq.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

