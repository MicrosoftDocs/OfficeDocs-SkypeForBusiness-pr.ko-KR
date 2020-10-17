---
title: 'Lync Server 2013: 영구 채팅 서버에 필요한 리소스'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Required resources
ms:assetid: bce50b95-f3c8-407e-963a-d8896ee77fbc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205211(v=OCS.15)
ms:contentKeyID: 48185255
ms.date: 02/05/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 156a3ffef41782760124f0eb791cf2fdb71a1235
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48511945"
---
# <a name="required-resources-for-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="b917f-102">Lync Server 2013의 영구 채팅 서버에 필요한 리소스</span><span class="sxs-lookup"><span data-stu-id="b917f-102">Required resources for Persistent Chat Server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b917f-103">_**마지막으로 수정 된 항목:** 2016-02-05_</span><span class="sxs-lookup"><span data-stu-id="b917f-103">_**Topic Last Modified:** 2016-02-05_</span></span>

<span data-ttu-id="b917f-104">영구 채팅 서버에 대 한 고가용성 및 재해 복구를 수행 하려면 일반적으로 전체 작업에 필요한 것 보다 더 많은 리소스가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="b917f-104">High availability and disaster recovery for Persistent Chat Server requires additional resources beyond what is typically needed for full operation.</span></span> <span data-ttu-id="b917f-105">고가용성 및 재해 복구를 위해 영구 채팅 서버를 구성 하기 전에 표준 영구 채팅 서버 작업에 필요한 사항 외에 다음과 같은 리소스가 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="b917f-105">Before configuring Persistent Chat Server for high availability and disaster recovery, ensure that you have the following resources in addition to what is required for standard Persistent Chat Server operation.</span></span> <span data-ttu-id="b917f-106">추가 구성 정보에 대 한 자세한 내용은 [Lync server 2013에서 영구 채팅 서버 구성을](lync-server-2013-configuring-persistent-chat-server.md)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="b917f-106">For additional configuration information, see [Configuring Persistent Chat Server in Lync Server 2013](lync-server-2013-configuring-persistent-chat-server.md).</span></span>

  - <span data-ttu-id="b917f-107">영구 채팅 서버 서비스의 홈 프런트 엔드가 있는 동일한 물리적 데이터 센터에 있는 단일 전용 데이터베이스 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="b917f-107">One dedicated database instance located in the same physical data center in which the home front end of the Persistent Chat Server service is located.</span></span> <span data-ttu-id="b917f-108">이 데이터베이스는 기본 영구 채팅 데이터베이스에 대 한 SQL Server 미러 서버 역할을 합니다.</span><span class="sxs-lookup"><span data-stu-id="b917f-108">This database will serve as the SQL Server mirror for the primary Persistent Chat database.</span></span> <span data-ttu-id="b917f-109">선택적으로 미러 데이터베이스에 대 한 자동화 된 장애 조치 (failover)를 사용 하려는 경우 미러링 모니터로 사용할 추가 SQL Server를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b917f-109">Optionally, designate an additional SQL Server to serve as the mirroring witness if you want an automated failover to the mirror database.</span></span>

  - <span data-ttu-id="b917f-110">다른 실제 데이터 센터에 있는 전용 데이터베이스 인스턴스 하나.</span><span class="sxs-lookup"><span data-stu-id="b917f-110">One dedicated database instance located in the other physical data center.</span></span> <span data-ttu-id="b917f-111">이 데이터베이스는 기본 데이터 센터에 있는 데이터베이스에 대 한 SQL Server 로그 전달 보조 데이터베이스 역할을 합니다.</span><span class="sxs-lookup"><span data-stu-id="b917f-111">This database will serve as the SQL Server Log Shipping secondary database for the database in the primary data center.</span></span>

  - <span data-ttu-id="b917f-112">보조 데이터베이스에 대 한 SQL Server 미러로 사용할 하나의 전용 데이터베이스 인스턴스만 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b917f-112">One dedicated database instance to serve as the SQL Server mirror for the secondary database.</span></span> <span data-ttu-id="b917f-113">선택적으로 추가 SQL Server를 미러링 모니터 서버로 서버에 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b917f-113">Optionally, designate an additional SQL Server to server as the mirroring witness.</span></span> <span data-ttu-id="b917f-114">이 두 가지 모두 보조 데이터베이스와 동일한 실제 데이터 센터에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b917f-114">Both of these must be located in the same physical data center as the secondary database.</span></span>

  - <span data-ttu-id="b917f-115">영구 채팅 서버 준수를 사용 하도록 설정 하는 경우에는 세 가지 전용 데이터베이스 인스턴스가 추가로 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="b917f-115">If Persistent Chat Server compliance is enabled, an additional three dedicated database instances are required.</span></span> <span data-ttu-id="b917f-116">해당 배포는 이전에 영구 채팅 데이터베이스에 대해 설명한 것과 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="b917f-116">Their distribution is the same as those previously outlined for the Persistent Chat database.</span></span> <span data-ttu-id="b917f-117">준수 데이터베이스는 동일한 SQL Server 인스턴스를 영구 채팅 데이터베이스와 공유 하는 것이 가능 하지만 고가용성 및 재해 복구를 위한 독립 실행형 인스턴스를 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="b917f-117">While it is possible for the compliance database to share the same SQL Server instance as the Persistent Chat database, we recommend standalone instances for high availability and disaster recovery.</span></span>

  - <span data-ttu-id="b917f-118">SQL Server 로그 전달 트랜잭션 로그에 대해 파일 공유를 만들고 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b917f-118">A file share must be created and designated for the SQL Server Log Shipping transaction logs.</span></span> <span data-ttu-id="b917f-119">영구 채팅 데이터베이스를 실행 하는 두 데이터 센터 모두의 모든 SQL 서버에는이 파일 공유에 대 한 읽기/쓰기 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b917f-119">All SQL Servers in both data centers that run Persistent Chat databases must have read/write access to this file share.</span></span> <span data-ttu-id="b917f-120">이 공유는 FileStore 역할의 일부로 정의되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b917f-120">This share is not defined as part of a FileStore role.</span></span>

  - <span data-ttu-id="b917f-121">주 서버 파일 공유에서 복사 되는 SQL Server 트랜잭션 로그의 대상 폴더로 사용할 보조 데이터베이스 서버의 파일 공유입니다.</span><span class="sxs-lookup"><span data-stu-id="b917f-121">A file share on the secondary database server to serve as the destination folder for the SQL Server transaction logs that are copied from the primary server file share.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b917f-122">영구 채팅 서버 풀의 활성 영구 채팅 서버는 토폴로지에 정의 된 다음 홉 Lync 풀과 동일한 표준 시간대에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b917f-122">Active Persistent Chat servers in a Persistent Chat Server pool MUST reside in the same time zone as the next hop Lync Pool defined in the topology.</span></span>



</div>

<span data-ttu-id="b917f-123">다음 그림에서는 전체 영구 채팅 서버 풀을 서로 다른 두 개의 늘인 풀 토폴로지에서 구성 하는 방법에 대 한 예를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b917f-123">The following figures provide examples about how the entire Persistent Chat Server pool can be configured in the two different stretched pool topologies:</span></span>

  - <span data-ttu-id="b917f-124">데이터 센터가 높은 대역폭/짧은 대기 시간을 사용하여 지리적으로 분산된 경우의 확장 영구 채팅 서버 풀</span><span class="sxs-lookup"><span data-stu-id="b917f-124">Stretched Persistent Chat Server pool when data centers are geo-located with high bandwidth/low latency.</span></span>

  - <span data-ttu-id="b917f-125">데이터 센터가 낮은 대역폭/긴 대기 시간을 사용하여 지리적으로 분산된 경우의 확장 영구 채팅 서버 풀</span><span class="sxs-lookup"><span data-stu-id="b917f-125">Stretched Persistent Chat Server pool when data centers are geo-located with low bandwidth/high latency.</span></span>

<span data-ttu-id="b917f-126">다음 그림에서는 데이터 센터가 높은 대역폭/짧은 대기 시간을 사용 하 여 지리적으로 분산 된 확장 된 영구 채팅 서버 풀 토폴로지를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b917f-126">The following figure shows a stretched Persistent Chat Server pool topology where data centers are geo-located with high bandwidth/low latency.</span></span>

<span data-ttu-id="b917f-127">**데이터 센터가 높은 대역폭/짧은 대기 시간을 사용하여 지리적으로 분산된 경우의 확장 영구 채팅 서버 풀**</span><span class="sxs-lookup"><span data-stu-id="b917f-127">**Stretched Persistent Chat Server pool when data centers are geo-located with high bandwidth/low latency.**</span></span>

<span data-ttu-id="b917f-128">![영구 채팅 서버 풀 HBW 구성 검사](images/JJ205211.55d10910-c824-41e6-bed2-08d13a2abd65(OCS.15).jpg "영구 채팅 서버 풀 HBW 구성 검사")</span><span class="sxs-lookup"><span data-stu-id="b917f-128">![Persistent Chat Server pool HBW configuration exam](images/JJ205211.55d10910-c824-41e6-bed2-08d13a2abd65(OCS.15).jpg "Persistent Chat Server pool HBW configuration exam")</span></span>

<span data-ttu-id="b917f-129">다음 그림에서는 데이터 센터가 낮은 대역폭/긴 대기 시간을 사용 하 여 지리적으로 분산 된 확장 된 영구 채팅 서버 풀 토폴로지를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b917f-129">The following figure shows a stretched Persistent Chat Server pool topology where data centers are geo-located with low bandwidth/high latency.</span></span>

<span data-ttu-id="b917f-130">**데이터 센터가 낮은 대역폭/긴 대기 시간을 사용하여 지리적으로 분산된 경우의 확장 영구 채팅 서버 풀**</span><span class="sxs-lookup"><span data-stu-id="b917f-130">**Stretched Persistent Chat Server pool when data centers are geo-located with low bandwidth/high latency.**</span></span>

<span data-ttu-id="b917f-131">![영구 채팅 서버 풀 LBW 구성 검사](images/JJ205211.586b0a3a-3767-4991-944f-ee54389512aa(OCS.15).jpg "영구 채팅 서버 풀 LBW 구성 검사")</span><span class="sxs-lookup"><span data-stu-id="b917f-131">![Persistent Chat Server pool LBW configuration exam](images/JJ205211.586b0a3a-3767-4991-944f-ee54389512aa(OCS.15).jpg "Persistent Chat Server pool LBW configuration exam")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

