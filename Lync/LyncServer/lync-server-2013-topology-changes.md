---
title: Lync Server 2013 토폴로지 변경 내용
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
ms.openlocfilehash: c4453a9b5b8a5fcd60eaad1e437fd4800caddfba
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745178"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="topology-changes-in-lync-server-2013"></a><span data-ttu-id="12704-102">Lync Server 2013의 토폴로지 변경 내용</span><span class="sxs-lookup"><span data-stu-id="12704-102">Topology changes in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="12704-103">_**마지막으로 수정한 주제:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="12704-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="12704-104">Lync Server 2013에 대 한 토폴로지 요구 사항과 고려 사항은이 섹션에 설명 된 바와 같이 이전 릴리스의 경우와 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="12704-104">Topology requirements and considerations for Lync Server 2013 are different from those for earlier releases, as described in this section.</span></span>

<div>

## <a name="new-front-end-pools-architecture"></a><span data-ttu-id="12704-105">새 프런트 엔드 풀 아키텍처</span><span class="sxs-lookup"><span data-stu-id="12704-105">New Front End Pools Architecture</span></span>

<span data-ttu-id="12704-106">Lync Server 2013에서는 Enterprise Edition 프런트 엔드 풀의 아키텍처가 분산 시스템 아키텍처로 변경 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="12704-106">In Lync Server 2013, the architecture of Enterprise Edition Front End pools has changed to a distributed systems architecture.</span></span>

<span data-ttu-id="12704-107">이 새로운 아키텍처를 사용 하는 경우 백 엔드 데이터베이스는 더 이상 풀의 실시간 데이터 저장소가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="12704-107">With this new architecture, the Back End database is no longer the real-time data store in a pool.</span></span> <span data-ttu-id="12704-108">특정 사용자에 대 한 정보는 풀의 프런트 엔드 서버 3 대에 보관 됩니다.</span><span class="sxs-lookup"><span data-stu-id="12704-108">Information about a particular user is kept on three Front End Servers in the pool.</span></span> <span data-ttu-id="12704-109">각 사용자에 대해 한 프런트 엔드 서버는 해당 사용자 정보의 마스터 역할을 하며, 두 개의 다른 프런트 엔드 서버는 복제본으로 역할을 합니다.</span><span class="sxs-lookup"><span data-stu-id="12704-109">For each user, one Front End Server acts as the master for that user’s information, and two other Front End Servers serve as replicas.</span></span> <span data-ttu-id="12704-110">프런트 엔드 서버가 중단 되 면 복제본으로 처리 되는 다른 프런트 엔드 서버가 자동으로 마스터로 승격 됩니다.</span><span class="sxs-lookup"><span data-stu-id="12704-110">If a Front End Server goes down, another Front End Server which served as a replica is automatically promoted to master.</span></span>

<span data-ttu-id="12704-111">이는 백그라운드에서 수행 되며, 관리자는 어떤 프런트 엔드 서버가 어떤 사용자에 대 한 마스터 인지 알 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="12704-111">This happens behind the scenes, and administrators do not need to know which Front End Servers are the masters for which users.</span></span> <span data-ttu-id="12704-112">이러한 데이터 저장소 배포는 풀 내의 성능 및 확장성을 개선 하 고 단일 백 엔드 서버의 단일 실패 지점을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="12704-112">This distribution of data storage improves performance and scalability within the pool, and eliminates the single point of failure of a single Back End Server.</span></span>

<span data-ttu-id="12704-113">백 엔드 서버는 사용자 및 회의 데이터에 대 한 백업 저장소 역할을 하며 응답 그룹 데이터베이스와 같은 다른 데이터베이스의 기본 저장소 이기도 합니다.</span><span class="sxs-lookup"><span data-stu-id="12704-113">The Back End Server serves as backup storage for user and conference data, and is also the primary storage for other databases such as the Response Group database.</span></span>

<span data-ttu-id="12704-114">이러한 개선 사항은 풀을 계획 하 고 유지 관리 하는 방법에도 변화가 있음을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="12704-114">These improvements also mean there are changes in how you plan and maintain your pools.</span></span> <span data-ttu-id="12704-115">프런트 엔드 풀 아키텍처가 디자인 된 모든 복제본을 제공 하기 위해 모든 Enterprise Edition 프런트 엔드 풀에는 3 개 이상의 프런트 엔드 서버가 포함 된 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="12704-115">We recommend that all your Enterprise Edition Front End pools include at least three Front End Servers, to provide the full number of replicas that the Front End pool architecture is designed for.</span></span> <span data-ttu-id="12704-116">또한 프런트 엔드 풀에 서버를 추가 하거나, 서버를 제거 하거나, 서버를 업그레이드 하는 경우에는 특정 절차를 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="12704-116">Additionally, you must follow certain procedures when adding servers to a Front End pool, removing servers from it, or upgrading servers.</span></span> <span data-ttu-id="12704-117">자세한 내용은 [Lync Server 2013의 프런트 엔드 서버, 인스턴트 메시징 및 현재 상태에 대 한 토폴로지 및 구성 요소](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="12704-117">For more information, see [Topologies and components for Front End Servers, instant messaging, and presence in Lync Server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md).</span></span>

<div>

## <a name="server-role-topology-changes"></a><span data-ttu-id="12704-118">서버 역할 토폴로지가 변경 되는 경우</span><span class="sxs-lookup"><span data-stu-id="12704-118">Server Role Topology Changes</span></span>

<span data-ttu-id="12704-119">다른 서버에서 이전에 실행 한 일부 서버 역할이 프런트 엔드 서버 역할에 통합 되어 하드웨어 비용을 절약할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="12704-119">Some server roles that previously ran on separate servers are now consolidated into the Front End Server role, enabling you to save on hardware costs</span></span>

  - <span data-ttu-id="12704-120">Lync Server 2013에서 A/V 회의 서버는 항상 프런트 엔드 서버와 collocated 됩니다.</span><span class="sxs-lookup"><span data-stu-id="12704-120">In Lync Server 2013, A/V Conferencing Server is always collocated with Front End Server.</span></span>

  - <span data-ttu-id="12704-121">이제 모니터링과 아카이빙 모두의 프런트 엔드가 항상 프런트 엔드 서버와 collocated 됩니다.</span><span class="sxs-lookup"><span data-stu-id="12704-121">The front ends for both Monitoring and Archiving are now always collocated with Front End Server.</span></span> <span data-ttu-id="12704-122">각 모니터링 및 보관에는 각각 프런트 엔드 풀의 백 엔드 데이터베이스와 동일한 서버에 collocated 될 수 있거나 별도의 백 엔드 서버에 호스팅될 수 있는 별도의 백 엔드 데이터베이스가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="12704-122">Monitoring and Archiving each still require a separate Back-End Database, which can be collocated on the same server as the Front End Pool’s back-end database, or can be hosted on separate Back-End Servers.</span></span>

  - <span data-ttu-id="12704-123">영구 채팅 서버는 이제 서버 역할입니다.</span><span class="sxs-lookup"><span data-stu-id="12704-123">Persistent Chat Server is now a server role.</span></span> <span data-ttu-id="12704-124">Microsoft Lync Server 2010에서 그룹 채팅 서버는 Microsoft Lync Server 2010 용 타사 신뢰할 수 있는 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="12704-124">In Microsoft Lync Server 2010, Group Chat Server was a third-party trusted application for Microsoft Lync Server 2010.</span></span> <span data-ttu-id="12704-125">Lync Server 2013에서 영구 채팅 서버 기능은 다음과 같은 세 가지 새로운 서버 역할을 사용 하 여 구현 됩니다.</span><span class="sxs-lookup"><span data-stu-id="12704-125">In Lync Server 2013, Persistent Chat Server functionality is implemented using three new server roles:</span></span>
    
      - <span data-ttu-id="12704-126">**PersistentChatService:** 프런트 엔드 역할로 구현 된 기본 영구 채팅 서버 서비스</span><span class="sxs-lookup"><span data-stu-id="12704-126">**PersistentChatService:** Main Persistent Chat Server services implemented as a front end role</span></span>
    
      - <span data-ttu-id="12704-127">**PersistentChatStore:** 백 엔드 서버 역할</span><span class="sxs-lookup"><span data-stu-id="12704-127">**PersistentChatStore:** Back End Server role</span></span>
    
      - <span data-ttu-id="12704-128">**PersistentChatComplianceStore:** 영구 채팅 준수를 위한 백 엔드 서버 역할</span><span class="sxs-lookup"><span data-stu-id="12704-128">**PersistentChatComplianceStore:** Back End Server role for Persistent Chat Compliance</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

