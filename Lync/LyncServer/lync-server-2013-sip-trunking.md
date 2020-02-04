---
title: 'Lync Server 2013: SIP 트렁크'
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
ms.openlocfilehash: d76907c1868e9fccb1a31e705c73807a8cbe501b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764484"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="sip-trunking-in-lync-server-2013"></a><span data-ttu-id="f302b-102">Lync Server 2013의 SIP 트렁크</span><span class="sxs-lookup"><span data-stu-id="f302b-102">SIP trunking in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f302b-103">_**마지막으로 수정한 주제:** 2012-08-13_</span><span class="sxs-lookup"><span data-stu-id="f302b-103">_**Topic Last Modified:** 2012-08-13_</span></span>

<span data-ttu-id="f302b-104">SIP (세션 초기화 프로토콜)는 기본 전화 서비스에 대 한 VoIP (Voice over IP) 통신 세션을 시작 하 고 관리 하는 데 사용 되며 인스턴트 메시지, 회의, 현재 상태 감지 등의 추가 실시간 통신 서비스를 위한 것입니다. 멀티미디어.</span><span class="sxs-lookup"><span data-stu-id="f302b-104">Session Initiation Protocol (SIP) is used to initiate and manage Voice over IP (VoIP) communications sessions for basic telephone service and for additional real-time communication services, such as instant messaging, conferencing, presence detection, and multimedia.</span></span> <span data-ttu-id="f302b-105">이 섹션에서는 로컬 네트워크 경계를 벗어나 확장 되는 sip 연결 유형인 *sip trunks*구현에 대 한 계획 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="f302b-105">This section provides planning information for implementing *SIP trunks*, a type of SIP connection that extends beyond the boundary of your local network.</span></span>

<div>

## <a name="what-is-sip-trunking"></a><span data-ttu-id="f302b-106">SIP 트렁크?</span><span class="sxs-lookup"><span data-stu-id="f302b-106">What is SIP Trunking?</span></span>

<span data-ttu-id="f302b-107">SIP 트렁크는 사용자의 조직과 인터넷 통신 서비스 공급자 (방화벽)의 SIP 통신 연결을 설정 하는 IP 연결입니다.</span><span class="sxs-lookup"><span data-stu-id="f302b-107">A SIP trunk is an IP connection that establishes a SIP communications link between your organization and an Internet telephony service provider (ITSP) beyond your firewall.</span></span> <span data-ttu-id="f302b-108">일반적으로 SIP 트렁크는 조직의 중앙 사이트를 ITSP에 연결 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f302b-108">Typically, a SIP trunk is used to connect your organization’s central site to an ITSP.</span></span> <span data-ttu-id="f302b-109">일부 경우에는 SIP 트렁크를 사용 하 여 지점 사이트를 ITSP에 연결 하도록 선택할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f302b-109">In some cases, you may also opt to use SIP trunking to connect your branch site to an ITSP.</span></span>

<div>

## <a name="sip-trunks-vs-direct-sip-connections"></a><span data-ttu-id="f302b-110">SIP Trunks 및 직접 SIP 연결</span><span class="sxs-lookup"><span data-stu-id="f302b-110">SIP Trunks vs. Direct SIP Connections</span></span>

<span data-ttu-id="f302b-111">*트렁크* 는 회로 교환 기술에서 파생 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f302b-111">The term *trunk* is derived from circuit-switched technology.</span></span> <span data-ttu-id="f302b-112">전화 교환 장비를 연결 하는 전용 물리적 회선을 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="f302b-112">It refers to a dedicated physical line that connects telephone switching equipment.</span></span> <span data-ttu-id="f302b-113">TDM (시간 구분 멀티플렉싱) trunks와 마찬가지로, SIP trunks는 두 개의 별도 SIP 네트워크 (Lync Server 2013 enterprise 및 ITSP) 간 연결입니다.</span><span class="sxs-lookup"><span data-stu-id="f302b-113">Like their predecessor, time division multiplexing (TDM) trunks, SIP trunks are connections between two separate SIP networks—the Lync Server 2013 enterprise and the ITSP.</span></span> <span data-ttu-id="f302b-114">회로 전환 trunks와 달리 SIP trunks는 지원 되는 SIP 트렁크 연결 형식에 따라 설정할 수 있는 가상 연결입니다.</span><span class="sxs-lookup"><span data-stu-id="f302b-114">Unlike circuit-switched trunks, SIP trunks are virtual connections that can be established over any of the supported SIP trunking connection types.</span></span> <span data-ttu-id="f302b-115">지원 되는 연결 형식에 대 한 자세한 내용은 [Lync Server 2013에서 SIP 트렁크을 구현 하는 방법은 무엇 인가요?](lync-server-2013-how-do-i-implement-sip-trunking.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f302b-115">For details about the supported connection types, see [How do I implement SIP trunking in Lync Server 2013?](lync-server-2013-how-do-i-implement-sip-trunking.md).</span></span>

<span data-ttu-id="f302b-116">반면에 직접 SIP 연결은 로컬 네트워크 경계 (즉, 내부 네트워크 내에서 PSTN (공개 통신 네트워크) 게이트웨이 또는 PBX (개인 분기 교환)에 연결 되지 않는 SIP 연결입니다.)</span><span class="sxs-lookup"><span data-stu-id="f302b-116">Direct SIP connections, on the other hand, are SIP connections that do not cross the local network boundary (that is, they connect to a public switched telephone network (PSTN) gateway or private branch exchange (PBX) within your internal network).</span></span> <span data-ttu-id="f302b-117">Lync Server 2013에서 직접 SIP 연결을 사용 하는 방법에 대 한 자세한 내용은 [Lync server 2013에서 직접 sip 연결](lync-server-2013-direct-sip-connections.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f302b-117">For details about how you can use direct SIP connections with Lync Server 2013, see [Direct SIP connections in Lync Server 2013](lync-server-2013-direct-sip-connections.md).</span></span>

</div>

</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="f302b-118">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="f302b-118">In This Section</span></span>

  - [<span data-ttu-id="f302b-119">Lync Server 2013의 SIP 트렁크 개요</span><span class="sxs-lookup"><span data-stu-id="f302b-119">Overview of SIP trunking in Lync Server 2013</span></span>](lync-server-2013-overview-of-sip-trunking.md)

  - [<span data-ttu-id="f302b-120">Lync Server 2013에서 SIP 트렁크를 구현하는 방법</span><span class="sxs-lookup"><span data-stu-id="f302b-120">How do I implement SIP trunking in Lync Server 2013?</span></span>](lync-server-2013-how-do-i-implement-sip-trunking.md)

  - [<span data-ttu-id="f302b-121">Lync Server 2013의 SIP 트렁크에 대한 구성 요소 및 토폴로지</span><span class="sxs-lookup"><span data-stu-id="f302b-121">Components and topologies for SIP trunking in Lync Server 2013</span></span>](lync-server-2013-components-and-topologies-for-sip-trunking.md)

  - [<span data-ttu-id="f302b-122">Lync Server 2013의 지점 사이트 SIP 트렁크</span><span class="sxs-lookup"><span data-stu-id="f302b-122">Branch site SIP trunking in Lync Server 2013</span></span>](lync-server-2013-branch-site-sip-trunking.md)

  - [<span data-ttu-id="f302b-123">Lync Server 2013에 대한 SIP 트렁크 배포 검사 목록</span><span class="sxs-lookup"><span data-stu-id="f302b-123">SIP trunk deployment checklist for Lync Server 2013</span></span>](lync-server-2013-sip-trunk-deployment-checklist.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

