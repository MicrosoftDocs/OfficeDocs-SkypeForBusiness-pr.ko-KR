---
title: 'Lync Server 2013: SIP 트렁크'
description: 'Lync Server 2013: SIP 트렁크'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: SIP trunking
ms:assetid: 7c586401-d0e5-4017-b3e1-fe5e7f8fc6db
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398619(v=OCS.15)
ms:contentKeyID: 48184615
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 60b68d9d0400c87de2832d7fe7bdabe4057ec47a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559014"
---
# <a name="sip-trunking-in-lync-server-2013"></a><span data-ttu-id="234a5-103">Lync Server 2013의 SIP 트렁크</span><span class="sxs-lookup"><span data-stu-id="234a5-103">SIP trunking in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="234a5-104">_**마지막으로 수정 된 항목:** 2012-08-13_</span><span class="sxs-lookup"><span data-stu-id="234a5-104">_**Topic Last Modified:** 2012-08-13_</span></span>

<span data-ttu-id="234a5-p101">SIP(Session Initiation Protocol)는 기본 전화 서비스 및 인스턴트 메시징, 회의, 현재 상태 감지, 멀티미디어 등의 추가 실시간 통신 서비스에 대한 VoIP(Voice over IP) 통신 세션을 시작 및 관리하는 데 사용됩니다. 이 섹션에서는 로컬 네트워크의 경계를 넘어 확장되는 SIP 연결 유형인 *SIP 트렁크*를 구현하기 위한 계획 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="234a5-p101">Session Initiation Protocol (SIP) is used to initiate and manage Voice over IP (VoIP) communications sessions for basic telephone service and for additional real-time communication services, such as instant messaging, conferencing, presence detection, and multimedia. This section provides planning information for implementing *SIP trunks*, a type of SIP connection that extends beyond the boundary of your local network.</span></span>

<div>

## <a name="what-is-sip-trunking"></a><span data-ttu-id="234a5-107">SIP 트렁크란?</span><span class="sxs-lookup"><span data-stu-id="234a5-107">What is SIP Trunking?</span></span>

<span data-ttu-id="234a5-p102">SIP 트렁크는 조직과 방화벽 너머의 ITSP(인터넷 전화 통신 서비스 공급자) 간의 SIP 통신 링크를 설정하는 IP 연결입니다. 일반적으로 SIP 트렁크는 조직의 중앙 사이트를 ITSP에 연결하는 데 사용됩니다. 일부의 경우 분기 사이트를 ITSP에 연결하는 데에도 SIP 트렁크를 사용하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="234a5-p102">A SIP trunk is an IP connection that establishes a SIP communications link between your organization and an Internet telephony service provider (ITSP) beyond your firewall. Typically, a SIP trunk is used to connect your organization’s central site to an ITSP. In some cases, you may also opt to use SIP trunking to connect your branch site to an ITSP.</span></span>

<div>

## <a name="sip-trunks-vs-direct-sip-connections"></a><span data-ttu-id="234a5-111">SIP 트렁크와 Direct SIP 연결</span><span class="sxs-lookup"><span data-stu-id="234a5-111">SIP Trunks vs. Direct SIP Connections</span></span>

<span data-ttu-id="234a5-112">*트렁크* 용어는 회로 전환 기술에서 파생 됩니다.</span><span class="sxs-lookup"><span data-stu-id="234a5-112">The term *trunk* is derived from circuit-switched technology.</span></span> <span data-ttu-id="234a5-113">전화 교환 장비를 연결 하는 전용 물리적 회선을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="234a5-113">It refers to a dedicated physical line that connects telephone switching equipment.</span></span> <span data-ttu-id="234a5-114">TDM (시간 구분 멀티플렉싱) 트렁크와 마찬가지로 SIP 트렁크은 별도의 두 SIP 네트워크 (Lync Server 2013 enterprise 및 ITSP) 간의 연결입니다.</span><span class="sxs-lookup"><span data-stu-id="234a5-114">Like their predecessor, time division multiplexing (TDM) trunks, SIP trunks are connections between two separate SIP networks—the Lync Server 2013 enterprise and the ITSP.</span></span> <span data-ttu-id="234a5-115">회로 전환 트렁크 달리 SIP 트렁크는 지원 되는 SIP 트렁크 연결 형식에 대해 설정할 수 있는 가상 연결입니다.</span><span class="sxs-lookup"><span data-stu-id="234a5-115">Unlike circuit-switched trunks, SIP trunks are virtual connections that can be established over any of the supported SIP trunking connection types.</span></span> <span data-ttu-id="234a5-116">지원 되는 연결 유형에 대 한 자세한 내용은 [How to THE SIP 트렁크 in The Lync Server 2013?](lync-server-2013-how-do-i-implement-sip-trunking.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="234a5-116">For details about the supported connection types, see [How do I implement SIP trunking in Lync Server 2013?](lync-server-2013-how-do-i-implement-sip-trunking.md).</span></span>

<span data-ttu-id="234a5-117">반면에 Direct SIP 연결은 로컬 네트워크 경계를 가로지르지 않는 SIP 연결입니다(즉, 내부 네트워크 내에서 PSTN(공중 전화망) 게이트웨이 또는 PBX(Private Branch Exchange)에 연결됨).</span><span class="sxs-lookup"><span data-stu-id="234a5-117">Direct SIP connections, on the other hand, are SIP connections that do not cross the local network boundary (that is, they connect to a public switched telephone network (PSTN) gateway or private branch exchange (PBX) within your internal network).</span></span> <span data-ttu-id="234a5-118">Lync Server 2013에서 직접 SIP 연결을 사용 하는 방법에 대 한 자세한 내용은 [Lync server 2013의 직접 sip 연결](lync-server-2013-direct-sip-connections.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="234a5-118">For details about how you can use direct SIP connections with Lync Server 2013, see [Direct SIP connections in Lync Server 2013](lync-server-2013-direct-sip-connections.md).</span></span>

</div>

</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="234a5-119">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="234a5-119">In This Section</span></span>

  - [<span data-ttu-id="234a5-120">Lync Server 2013의 SIP 트렁크 개요</span><span class="sxs-lookup"><span data-stu-id="234a5-120">Overview of SIP trunking in Lync Server 2013</span></span>](lync-server-2013-overview-of-sip-trunking.md)

  - [<span data-ttu-id="234a5-121">Lync Server 2013에서 SIP 트렁크를 구현 하려면 어떻게 하나요?</span><span class="sxs-lookup"><span data-stu-id="234a5-121">How do I implement SIP trunking in Lync Server 2013?</span></span>](lync-server-2013-how-do-i-implement-sip-trunking.md)

  - [<span data-ttu-id="234a5-122">Lync Server 2013의 SIP 트렁크에 대 한 구성 요소 및 토폴로지</span><span class="sxs-lookup"><span data-stu-id="234a5-122">Components and topologies for SIP trunking in Lync Server 2013</span></span>](lync-server-2013-components-and-topologies-for-sip-trunking.md)

  - [<span data-ttu-id="234a5-123">Lync Server 2013에서 분기 사이트 SIP 트렁크</span><span class="sxs-lookup"><span data-stu-id="234a5-123">Branch site SIP trunking in Lync Server 2013</span></span>](lync-server-2013-branch-site-sip-trunking.md)

  - [<span data-ttu-id="234a5-124">Lync Server 2013에 대 한 SIP 트렁크 배포 검사 목록</span><span class="sxs-lookup"><span data-stu-id="234a5-124">SIP trunk deployment checklist for Lync Server 2013</span></span>](lync-server-2013-sip-trunk-deployment-checklist.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

