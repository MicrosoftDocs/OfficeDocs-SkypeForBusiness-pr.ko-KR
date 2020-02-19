---
title: Lync Server 2013 토폴로지 변경 사항
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Topology changes
ms:assetid: 9e40ef93-9ab0-498c-9bbf-f94584353e53
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688153(v=OCS.15)
ms:contentKeyID: 49733756
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ca14e6696417c8d95ee2b4ce4cd3cbfbf48b8bfa
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141114"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="topology-changes-in-lync-server-2013"></a><span data-ttu-id="df12e-102">Lync Server 2013의 토폴로지 변경 사항</span><span class="sxs-lookup"><span data-stu-id="df12e-102">Topology changes in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="df12e-103">_**마지막으로 수정 된 항목:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="df12e-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="df12e-104">이 섹션에서 설명 하는 것과 같이 Lync Server 2013에 대 한 토폴로지 요구 사항 및 고려 사항은 이전 릴리스와는 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="df12e-104">Topology requirements and considerations for Lync Server 2013 are different from those for earlier releases, as described in this section.</span></span>

<div>

## <a name="new-front-end-pools-architecture"></a><span data-ttu-id="df12e-105">새 프런트 엔드 풀 아키텍처</span><span class="sxs-lookup"><span data-stu-id="df12e-105">New Front End Pools Architecture</span></span>

<span data-ttu-id="df12e-106">Lync Server 2013에서는 Enterprise Edition 프런트 엔드 풀의 아키텍처가 분산 시스템 아키텍처로 변경 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="df12e-106">In Lync Server 2013, the architecture of Enterprise Edition Front End pools has changed to a distributed systems architecture.</span></span>

<span data-ttu-id="df12e-p101">이 새로운 아키텍처에서는 백 엔드 데이터베이스가 더 이상 풀의 실시간 데이터 저장소가 아닙니다. 특정 사용자에 대한 정보는 풀의 세 프런트 엔드 서버에 유지됩니다. 각 사용자에 대해 한 프런트 엔드 서버는 해당 사용자의 정보에 대한 마스터로 작동하고, 나머지 두 프런트 엔드 서버는 복제본으로 작동합니다. 한 프런트 엔드 서버가 다운될 경우 복제본으로 작동하는 다른 프런트 엔드 서버가 자동으로 마스터로 승격됩니다.</span><span class="sxs-lookup"><span data-stu-id="df12e-p101">With this new architecture, the Back End database is no longer the real-time data store in a pool. Information about a particular user is kept on three Front End Servers in the pool. For each user, one Front End Server acts as the master for that user’s information, and two other Front End Servers serve as replicas. If a Front End Server goes down, another Front End Server which served as a replica is automatically promoted to master.</span></span>

<span data-ttu-id="df12e-111">이것은 자동으로 이루어지며 관리자는 어느 프런트 엔드 서버가 어느 사용자의 마스터로 작동하는지 알 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="df12e-111">This happens behind the scenes, and administrators do not need to know which Front End Servers are the masters for which users.</span></span> <span data-ttu-id="df12e-112">이러한 데이터 저장소 배포는 풀 내의 성능 및 확장성을 개선 하 고 단일 백 엔드 서버의 단일 오류 지점을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="df12e-112">This distribution of data storage improves performance and scalability within the pool, and eliminates the single point of failure of a single Back End Server.</span></span>

<span data-ttu-id="df12e-113">백 엔드 서버는 사용자 및 회의 데이터에 대한 백업 저장소로 작동하는 동시에 응답 그룹 데이터베이스와 같은 기타 데이터베이스에 대한 주 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="df12e-113">The Back End Server serves as backup storage for user and conference data, and is also the primary storage for other databases such as the Response Group database.</span></span>

<span data-ttu-id="df12e-114">또한 이러한 향상을 통해 풀을 계획하고 유지 관리하는 방식이 달라졌습니다.</span><span class="sxs-lookup"><span data-stu-id="df12e-114">These improvements also mean there are changes in how you plan and maintain your pools.</span></span> <span data-ttu-id="df12e-115">모든 Enterprise Edition 프런트 엔드 풀에는 프런트 엔드 풀 아키텍처를 디자인 한 전체 복제본 수를 제공 하기 위해 프런트 엔드 서버를 3 개 이상 포함 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="df12e-115">We recommend that all your Enterprise Edition Front End pools include at least three Front End Servers, to provide the full number of replicas that the Front End pool architecture is designed for.</span></span> <span data-ttu-id="df12e-116">또한 프런트 엔드 풀에 서버를 추가 하거나, 서버에서 서버를 제거 하거나, 서버의 업그레이드를 수행할 때 특정 절차를 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="df12e-116">Additionally, you must follow certain procedures when adding servers to a Front End pool, removing servers from it, or upgrading servers.</span></span> <span data-ttu-id="df12e-117">자세한 내용은 [Lync Server 2013의 프런트 엔드 서버, 인스턴트 메시징 및 현재 상태에 대 한 토폴로지 및 구성 요소](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="df12e-117">For more information, see [Topologies and components for Front End Servers, instant messaging, and presence in Lync Server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md).</span></span>

<div>

## <a name="server-role-topology-changes"></a><span data-ttu-id="df12e-118">서버 역할 토폴로지 변경 사항</span><span class="sxs-lookup"><span data-stu-id="df12e-118">Server Role Topology Changes</span></span>

<span data-ttu-id="df12e-119">이전에 별도 서버에서 실행된 일부 서버가 이제 프런트 엔드 서버 역할로 통합되었습니다. 이를 통해 하드웨어 비용을 절감할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df12e-119">Some server roles that previously ran on separate servers are now consolidated into the Front End Server role, enabling you to save on hardware costs</span></span>

  - <span data-ttu-id="df12e-120">Lync Server 2013에서는 A/V 회의 서버가 항상 프런트 엔드 서버를 사용 하 여 배치 된 됩니다.</span><span class="sxs-lookup"><span data-stu-id="df12e-120">In Lync Server 2013, A/V Conferencing Server is always collocated with Front End Server.</span></span>

  - <span data-ttu-id="df12e-p104">이제 모니터링과 보관용 프런트 엔드가 항상 프런트 엔드 서버와 함께 배치됩니다. 모니터링과 보관에는 여전히 각각 별도의 백 엔드 데이터베이스가 필요하며, 이를 프런트 엔드 풀의 백 엔드 데이터베이스와 같은 서버에 배치하거나 별도의 백 엔드 서버에 호스팅할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df12e-p104">The front ends for both Monitoring and Archiving are now always collocated with Front End Server. Monitoring and Archiving each still require a separate Back-End Database, which can be collocated on the same server as the Front End Pool’s back-end database, or can be hosted on separate Back-End Servers.</span></span>

  - <span data-ttu-id="df12e-123">영구 채팅 서버는 이제 서버 역할입니다.</span><span class="sxs-lookup"><span data-stu-id="df12e-123">Persistent Chat Server is now a server role.</span></span> <span data-ttu-id="df12e-124">Microsoft Lync Server 2010에서 그룹 채팅 서버는 Microsoft Lync Server 2010에 대 한 타사 트러스트 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="df12e-124">In Microsoft Lync Server 2010, Group Chat Server was a third-party trusted application for Microsoft Lync Server 2010.</span></span> <span data-ttu-id="df12e-125">Lync Server 2013에서는 영구 채팅 서버 기능이 다음과 같은 세 가지 새 서버 역할을 사용 하 여 구현 됩니다.</span><span class="sxs-lookup"><span data-stu-id="df12e-125">In Lync Server 2013, Persistent Chat Server functionality is implemented using three new server roles:</span></span>
    
      - <span data-ttu-id="df12e-126">**PersistentChatService:** 프런트 엔드 역할로 구현 되는 기본 영구 채팅 서버 서비스</span><span class="sxs-lookup"><span data-stu-id="df12e-126">**PersistentChatService:** Main Persistent Chat Server services implemented as a front end role</span></span>
    
      - <span data-ttu-id="df12e-127">**PersistentChatStore:** 백 엔드 서버 역할</span><span class="sxs-lookup"><span data-stu-id="df12e-127">**PersistentChatStore:** Back End Server role</span></span>
    
      - <span data-ttu-id="df12e-128">**PersistentChatComplianceStore:** 영구 채팅 준수에 대 한 백 엔드 서버 역할</span><span class="sxs-lookup"><span data-stu-id="df12e-128">**PersistentChatComplianceStore:** Back End Server role for Persistent Chat Compliance</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

