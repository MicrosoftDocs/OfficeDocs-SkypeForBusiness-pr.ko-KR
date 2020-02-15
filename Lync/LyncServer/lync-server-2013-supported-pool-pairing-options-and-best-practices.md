---
title: Lync Server 2013 지원 되는 풀 페어링 옵션 및 모범 사례
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Supported pool pairing options and best practices
ms:assetid: 142caf34-0f20-47f3-9d32-ce25ab622fad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204697(v=OCS.15)
ms:contentKeyID: 48183478
ms.date: 03/09/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 963f1532ca7a1aa5402a54936909a22727ab9716
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006846"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="supported-pool-pairing-options-and-best-practices-for-lync-server-2013"></a><span data-ttu-id="806b4-102">Lync Server 2013에 대 한 지원 되는 풀 페어링 옵션 및 모범 사례</span><span class="sxs-lookup"><span data-stu-id="806b4-102">Supported pool pairing options and best practices for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="806b4-103">_**마지막으로 수정 된 항목:** 2017-03-09_</span><span class="sxs-lookup"><span data-stu-id="806b4-103">_**Topic Last Modified:** 2017-03-09_</span></span>

<span data-ttu-id="806b4-p101">쌍으로 지정된 프런트 엔드 풀을 포함할 두 데이터 센터 간의 거리에는 제한이 없습니다. 같은 지역에 있으며 고속 링크가 설정된 두 데이터 센터를 사용하는 것이 좋습니다. 단일 재해가 두 데이터 센터에서 동시에 발생하지 않도록 두 데이터 센터가 충분히 떨어져 있는 것이 가장 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="806b4-p101">There is no restriction on the distance between two data centers that are to include Front End pools paired with each other. We recommend that you use two data centers in the same world region, with high-speed links between them. It is best if the two data centers are separated enough to avoid a single disaster hitting both at the same time.</span></span>

<span data-ttu-id="806b4-107">두 데이터 센터가 서로 다른 지역에 있어도 되지만 이 경우 데이터 복제 대기 시간으로 인해 데이터 손실률이 높아질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="806b4-107">Having two data centers across world regions is possible, but could incur higher data loss due to latency in data replication.</span></span>

<span data-ttu-id="806b4-108">쌍으로 지정할 풀을 계획할 때는 다음 쌍만 지원 된다는 점에 유의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="806b4-108">When you plan which pools to pair, you must keep in mind that only the following pairings are supported:</span></span>

  - <span data-ttu-id="806b4-p102">Enterprise Edition 풀은 다른 Enterprise Edition 풀과만 쌍으로 지정할 수 있습니다. Standard Edition 풀은 다른 Standard Edition 풀과만 쌍으로 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="806b4-p102">Enterprise Edition pools can be paired only with other Enterprise Edition pools. Similarly, Standard Edition pools can be paired only with other Standard Edition pools.</span></span>

  - <span data-ttu-id="806b4-p103">물리적 풀은 다른 물리적 풀과만 쌍으로 지정할 수 있습니다. 마찬가지로 가상 풀은 다른 가상 풀과만 쌍으로 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="806b4-p103">Physical pools can be paired only with other physical pools. Similarly, virtual pools can be paired only with other virtual pools.</span></span>

  - <span data-ttu-id="806b4-113">함께 사용할 풀은 동일한 운영 체제를 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="806b4-113">Pools that are paired together must be running the same operating system.</span></span>

<span data-ttu-id="806b4-114">토폴로지 작성기 또는 토폴로지 유효성 검사에서 이러한 권장 사항을 따르지 않는 방식으로 두 풀을 쌍으로 지정하는 작업을 차단할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="806b4-114">Neither Topology Builder nor topology validation will prohibit pairing two pools in a way that does not follow these recommendations.</span></span> <span data-ttu-id="806b4-115">예를 들어 토폴로지 작성기에서는 Enterprise Edition 풀과 Standard Edition 풀의 쌍 지정을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="806b4-115">For example, Topology Builder allows you to pair an Enterprise Edition pool with a Standard Edition pool.</span></span> <span data-ttu-id="806b4-116">그러나 이러한 쌍 유형은 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="806b4-116">However, these types of pairings are not supported.</span></span>

<span data-ttu-id="806b4-117">쌍의 각 풀에는 재해 발생 시 두 풀의 모든 사용자 작업을 처리할 수 있는 용량이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="806b4-117">Each pool in a pair should have the capacity to serve all users from both pools in the event of a disaster.</span></span>

<span data-ttu-id="806b4-118">Enterprise Edition 풀을 쌍으로 지정하는 경우에는 백 엔드 서버에 대해 고가용성을 구현할 수도 있지만, Standard Edition 풀 쌍의 경우에는 재해 복구 조치만 사용 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="806b4-118">If you pair Enterprise Edition pools, you can also implement high availability on the Back End Servers, but for pairs of Standard Edition pools only the disaster recovery measures are available.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

