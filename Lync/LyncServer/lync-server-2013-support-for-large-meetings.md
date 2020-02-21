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
ms.openlocfilehash: cb551013a07cf16236e9fae5f8c3a3056bdb2f51
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42181641"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="support-for-large-meetings-in-lync-server-2013"></a><span data-ttu-id="82e98-102">Lync Server 2013의 대규모 모임 지원</span><span class="sxs-lookup"><span data-stu-id="82e98-102">Support for large meetings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="82e98-103">_**마지막으로 수정 된 항목:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="82e98-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="82e98-104">Lync Server 2013에서는 PowerPoint 프레젠테이션 공유를 포함 하 여 A/V (오디오/비디오) 회의를 사용 하는 최대 1000 참가자와의 모임을 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82e98-104">Lync Server 2013 can support meetings with up to 1000 participants using audio/video (A/V) conferencing, including sharing PowerPoint presentations.</span></span> <span data-ttu-id="82e98-105">이러한 지원을 위해서는 대규모 모임을 지원하도록 구성된 전용 풀이 필요하며, 단일 대규모 모임을 한 번에 하나만 호스팅하도록 보장하는 방식으로 관리되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="82e98-105">This support requires a dedicated pool configured to support large meetings and managed in a way that ensures hosting of only a single large meeting at a time.</span></span>

<span data-ttu-id="82e98-106">이 섹션에서는 전용 Lync Server 2013 풀을 사용 하 여 대규모 모임을 지 원하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="82e98-106">This section describes how to support large meetings using a dedicated Lync Server 2013 pool.</span></span> <span data-ttu-id="82e98-107">토폴로지, 하드웨어, 소프트웨어 및 구성 요구 사항을 포함 하 여 전용 풀에 대 한 구현 요구 사항 및 확장성에 대 한 고려 사항을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="82e98-107">It describes scalability considerations and the implementation requirements for a dedicated pool, including topology, hardware, software, and configuration requirements.</span></span> <span data-ttu-id="82e98-108">또한 대규모 모임을 지원 하기 위한 모범 사례 권장 사항과 Lync Server 엔지니어링 팀이 수행 하는 서버 확장성 테스트의 결과와 테스트 방법에 대 한 요약 및 지원에 대 한 질문과 대답이 제공 됩니다. 대규모 모임</span><span class="sxs-lookup"><span data-stu-id="82e98-108">It also provides a set of best practice recommendations for supporting large meetings, a summary of the test methods and results of server scalability testing conducted by the Lync Server engineering team, and the answers to frequently asked questions about support for large meetings.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="82e98-109">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="82e98-109">In This Section</span></span>

  - [<span data-ttu-id="82e98-110">Lync Server 2013의 회의 확장성 개요</span><span class="sxs-lookup"><span data-stu-id="82e98-110">Overview of conferencing scalability in Lync Server 2013</span></span>](lync-server-2013-conferencing-scalability-overview.md)

  - [<span data-ttu-id="82e98-111">Lync Server 2013를 사용 하 여 대규모 모임 지원</span><span class="sxs-lookup"><span data-stu-id="82e98-111">Supporting large meetings using Lync Server 2013</span></span>](lync-server-2013-supporting-large-meetings.md)

  - [<span data-ttu-id="82e98-112">Lync Server 2013에 대 한 대규모 모임 지원 FAQ</span><span class="sxs-lookup"><span data-stu-id="82e98-112">Large meeting support FAQ for Lync Server 2013</span></span>](lync-server-2013-large-meeting-support-faq.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

