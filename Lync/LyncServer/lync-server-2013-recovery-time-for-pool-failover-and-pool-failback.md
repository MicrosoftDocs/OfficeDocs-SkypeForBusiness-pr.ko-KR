---
title: 풀 장애 조치 (failover) 및 풀 장애 복구를 위한 Lync Server 2013 복구 시간
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Recovery time for pool failover and pool failback
ms:assetid: 902c658f-8442-4d0d-b3ad-bf795ecd550d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205079(v=OCS.15)
ms:contentKeyID: 48184786
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8692e01ed9691f69da7be78a2e0437e7829594cb
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050170"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="recovery-time-for-pool-failover-and-pool-failback-in-lync-server-2013"></a><span data-ttu-id="aad27-102">Lync Server 2013의 풀 장애 조치 (failover) 및 풀 장애 복구 (failback)</span><span class="sxs-lookup"><span data-stu-id="aad27-102">Recovery time for pool failover and pool failback in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="aad27-103">_**마지막으로 수정 된 항목:** 2012-09-10_</span><span class="sxs-lookup"><span data-stu-id="aad27-103">_**Topic Last Modified:** 2012-09-10_</span></span>

<span data-ttu-id="aad27-104">풀 장애 조치 (failover) 및 풀 장애 복구 (failback)의 경우, RTO (복구 시간 목표)에 대 한 엔지니어링 대상이 30 분입니다.</span><span class="sxs-lookup"><span data-stu-id="aad27-104">For pool failover and pool failback, the engineering target for recovery time objective (RTO) is 30 minutes.</span></span> <span data-ttu-id="aad27-105">관리자가 재해가 발생 했으며 장애 조치 (failover) 절차를 시작한 후에 장애 조치 (failover)를 수행 하는 데 소요 되는 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="aad27-105">This is the time required for the failover to happen, after administrators have determined there was a disaster and initiated the failover procedures.</span></span> <span data-ttu-id="aad27-106">여기에는 관리자가 상황을 평가 하 고 결정을 내리는 시간이 포함 되지 않으며 장애 조치 (failover)가 완료 된 후 사용자가 다시 로그인 하는 시간도 포함 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="aad27-106">It does not include the time for administrators to assess the situation and make a decision, nor does it include the time for users to sign in again after failover is complete.</span></span>

<span data-ttu-id="aad27-107">풀 장애 조치 (failover) 및 풀 장애 복구 (failback)의 경우, RPO (복구 지점 목표)에 대 한 엔지니어링 대상이 30 분입니다.</span><span class="sxs-lookup"><span data-stu-id="aad27-107">For pool failover and pool failback, the engineering target for recovery point objective (RPO) is 30 minutes.</span></span> <span data-ttu-id="aad27-108">백업 서비스의 복제 대기 시간으로 인해 재해로 인해 손실 될 수 있는 데이터 측정 시간을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="aad27-108">This represents the time measure of data that could be lost due to the disaster, due to replication latency of the Backup Service.</span></span> <span data-ttu-id="aad27-109">예를 들어 풀이 오전 10:00 시에 다운 되 고 RPO가 30 분 후에는 풀에 데이터를 기록 하는 시간: 오전 9:30</span><span class="sxs-lookup"><span data-stu-id="aad27-109">For example, if a pool goes down at 10:00 A.M., and the RPO is 30 minutes, data written to the pool between 9:30 A.M.</span></span> <span data-ttu-id="aad27-110">및 10:00이 백업 풀로 복제 되지 않아 손실 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aad27-110">and 10:00 A.M.might not have replicated to the backup pool, and would be lost.</span></span>

<span data-ttu-id="aad27-111">이 문서의 모든 RTO 및 RPO 번호는 두 개의 데이터 센터가 같은 세계 지역 내에 있는 것으로 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="aad27-111">All RTO and RPO numbers in this document assume that the two data centers are located within the same world region with high-speed, low-latency transport between the two sites.</span></span> <span data-ttu-id="aad27-112">이러한 수치는 데이터 복제에 백로그가 없는 미리 정의 된 사용자 모델과 관련 하 여, 4만 동시 활성 사용자 및 20만 사용자가 Lync를 사용할 수 있는 풀에 대해 측정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="aad27-112">These numbers are measured for a pool with 40,000 concurrently active users and 200,000 users enabled for Lync with respect to a pre-defined user model where there is no backlog in data replication.</span></span> <span data-ttu-id="aad27-113">성능 테스트 및 유효성 검사에 따라 변경 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aad27-113">They are subject to change based on performance testing and validation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

