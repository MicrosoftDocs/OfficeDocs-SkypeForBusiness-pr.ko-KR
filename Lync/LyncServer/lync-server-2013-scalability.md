---
title: Lync Server 2013 확장성
description: Lync Server 2013 확장성
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Scalability
ms:assetid: 46fa0cb5-1507-4a12-ad3f-ba64585e2dc4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg417160(v=OCS.15)
ms:contentKeyID: 48183995
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 28cd5820755ffd1eb863ed6f2369b5756a7ae3f5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543794"
---
# <a name="scalability-with-lync-server-2013"></a><span data-ttu-id="edbee-103">Lync Server 2013의 확장성</span><span class="sxs-lookup"><span data-stu-id="edbee-103">Scalability with Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="edbee-104">_**마지막으로 수정 된 항목:** 2012-06-25_</span><span class="sxs-lookup"><span data-stu-id="edbee-104">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="edbee-105">Lync Server는 Enterprise Edition과 Standard Edition의 두 버전으로 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="edbee-105">Lync Server is offered in two editions, Enterprise Edition and Standard Edition.</span></span> <span data-ttu-id="edbee-106">이러한 각 에디션은 서로 다른 규모의 조직을 지원하도록 의도되었습니다.</span><span class="sxs-lookup"><span data-stu-id="edbee-106">The different editions are intended primarily for different sizes of organizations.</span></span> <span data-ttu-id="edbee-107">다음 표에 표시된 것처럼 두 에디션 모두 고가용성 및 재해 복구만 제외하고 모든 작업 부하에서 모든 기능을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="edbee-107">As shown in the following table, both editions support all functionality in all workloads, except for high availability and disaster recovery.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="edbee-108">기능</span><span class="sxs-lookup"><span data-stu-id="edbee-108">Feature</span></span></th>
<th><span data-ttu-id="edbee-109">Enterprise Edition에서 지원 여부</span><span class="sxs-lookup"><span data-stu-id="edbee-109">Supported in Enterprise Edition?</span></span></th>
<th><span data-ttu-id="edbee-110">Standard Edition에서 지원 여부</span><span class="sxs-lookup"><span data-stu-id="edbee-110">Supported in Standard Edition?</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="edbee-111">IM(인스턴트 메시징) 및 현재 상태</span><span class="sxs-lookup"><span data-stu-id="edbee-111">Instant messaging (IM) and presence</span></span></p></td>
<td><p><span data-ttu-id="edbee-112">예</span><span class="sxs-lookup"><span data-stu-id="edbee-112">Yes</span></span></p></td>
<td><p><span data-ttu-id="edbee-113">예</span><span class="sxs-lookup"><span data-stu-id="edbee-113">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="edbee-114">회의</span><span class="sxs-lookup"><span data-stu-id="edbee-114">Conferencing</span></span></p></td>
<td><p><span data-ttu-id="edbee-115">예</span><span class="sxs-lookup"><span data-stu-id="edbee-115">Yes</span></span></p></td>
<td><p><span data-ttu-id="edbee-116">예</span><span class="sxs-lookup"><span data-stu-id="edbee-116">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="edbee-117">A/V 회의</span><span class="sxs-lookup"><span data-stu-id="edbee-117">A/V conferencing</span></span></p></td>
<td><p><span data-ttu-id="edbee-118">예</span><span class="sxs-lookup"><span data-stu-id="edbee-118">Yes</span></span></p></td>
<td><p><span data-ttu-id="edbee-119">예</span><span class="sxs-lookup"><span data-stu-id="edbee-119">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="edbee-120">전화 접속 회의</span><span class="sxs-lookup"><span data-stu-id="edbee-120">Dial-in conferencing</span></span></p></td>
<td><p><span data-ttu-id="edbee-121">예</span><span class="sxs-lookup"><span data-stu-id="edbee-121">Yes</span></span></p></td>
<td><p><span data-ttu-id="edbee-122">예</span><span class="sxs-lookup"><span data-stu-id="edbee-122">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="edbee-123">Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="edbee-123">Enterprise Voice</span></span></p></td>
<td><p><span data-ttu-id="edbee-124">예</span><span class="sxs-lookup"><span data-stu-id="edbee-124">Yes</span></span></p></td>
<td><p><span data-ttu-id="edbee-125">예</span><span class="sxs-lookup"><span data-stu-id="edbee-125">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="edbee-126">가상화</span><span class="sxs-lookup"><span data-stu-id="edbee-126">Virtualization</span></span></p></td>
<td><p><span data-ttu-id="edbee-127">예</span><span class="sxs-lookup"><span data-stu-id="edbee-127">Yes</span></span></p></td>
<td><p><span data-ttu-id="edbee-128">예</span><span class="sxs-lookup"><span data-stu-id="edbee-128">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="edbee-129">고가용성, 장애 조치(Failover) 및 재해 복구</span><span class="sxs-lookup"><span data-stu-id="edbee-129">High availability, failover, and disaster recovery</span></span></p></td>
<td><p><span data-ttu-id="edbee-130">예</span><span class="sxs-lookup"><span data-stu-id="edbee-130">Yes</span></span></p></td>
<td><p><span data-ttu-id="edbee-131">아니요</span><span class="sxs-lookup"><span data-stu-id="edbee-131">No</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

