---
title: Lync Server 2013 확장성
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
ms.openlocfilehash: 10bf167538158e0f427b1522738374ae7c2b5320
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42182708"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="scalability-with-lync-server-2013"></a><span data-ttu-id="78aca-102">Lync Server 2013의 확장성</span><span class="sxs-lookup"><span data-stu-id="78aca-102">Scalability with Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="78aca-103">_**마지막으로 수정 된 항목:** 2012-06-25_</span><span class="sxs-lookup"><span data-stu-id="78aca-103">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="78aca-104">Lync Server는 Enterprise Edition과 Standard Edition의 두 버전으로 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="78aca-104">Lync Server is offered in two editions, Enterprise Edition and Standard Edition.</span></span> <span data-ttu-id="78aca-105">이러한 각 에디션은 서로 다른 규모의 조직을 지원하도록 의도되었습니다.</span><span class="sxs-lookup"><span data-stu-id="78aca-105">The different editions are intended primarily for different sizes of organizations.</span></span> <span data-ttu-id="78aca-106">다음 표에 표시된 것처럼 두 에디션 모두 고가용성 및 재해 복구만 제외하고 모든 작업 부하에서 모든 기능을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="78aca-106">As shown in the following table, both editions support all functionality in all workloads, except for high availability and disaster recovery.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="78aca-107">기능</span><span class="sxs-lookup"><span data-stu-id="78aca-107">Feature</span></span></th>
<th><span data-ttu-id="78aca-108">Enterprise Edition에서 지원 여부</span><span class="sxs-lookup"><span data-stu-id="78aca-108">Supported in Enterprise Edition?</span></span></th>
<th><span data-ttu-id="78aca-109">Standard Edition에서 지원 여부</span><span class="sxs-lookup"><span data-stu-id="78aca-109">Supported in Standard Edition?</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="78aca-110">IM(인스턴트 메시징) 및 현재 상태</span><span class="sxs-lookup"><span data-stu-id="78aca-110">Instant messaging (IM) and presence</span></span></p></td>
<td><p><span data-ttu-id="78aca-111">예</span><span class="sxs-lookup"><span data-stu-id="78aca-111">Yes</span></span></p></td>
<td><p><span data-ttu-id="78aca-112">예</span><span class="sxs-lookup"><span data-stu-id="78aca-112">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78aca-113">전화</span><span class="sxs-lookup"><span data-stu-id="78aca-113">Conferencing</span></span></p></td>
<td><p><span data-ttu-id="78aca-114">예</span><span class="sxs-lookup"><span data-stu-id="78aca-114">Yes</span></span></p></td>
<td><p><span data-ttu-id="78aca-115">예</span><span class="sxs-lookup"><span data-stu-id="78aca-115">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78aca-116">A/V 회의</span><span class="sxs-lookup"><span data-stu-id="78aca-116">A/V conferencing</span></span></p></td>
<td><p><span data-ttu-id="78aca-117">예</span><span class="sxs-lookup"><span data-stu-id="78aca-117">Yes</span></span></p></td>
<td><p><span data-ttu-id="78aca-118">예</span><span class="sxs-lookup"><span data-stu-id="78aca-118">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78aca-119">전화 접속 회의</span><span class="sxs-lookup"><span data-stu-id="78aca-119">Dial-in conferencing</span></span></p></td>
<td><p><span data-ttu-id="78aca-120">예</span><span class="sxs-lookup"><span data-stu-id="78aca-120">Yes</span></span></p></td>
<td><p><span data-ttu-id="78aca-121">예</span><span class="sxs-lookup"><span data-stu-id="78aca-121">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78aca-122">Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="78aca-122">Enterprise Voice</span></span></p></td>
<td><p><span data-ttu-id="78aca-123">예</span><span class="sxs-lookup"><span data-stu-id="78aca-123">Yes</span></span></p></td>
<td><p><span data-ttu-id="78aca-124">예</span><span class="sxs-lookup"><span data-stu-id="78aca-124">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78aca-125">가상화</span><span class="sxs-lookup"><span data-stu-id="78aca-125">Virtualization</span></span></p></td>
<td><p><span data-ttu-id="78aca-126">예</span><span class="sxs-lookup"><span data-stu-id="78aca-126">Yes</span></span></p></td>
<td><p><span data-ttu-id="78aca-127">예</span><span class="sxs-lookup"><span data-stu-id="78aca-127">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78aca-128">고가용성, 장애 조치(Failover) 및 재해 복구</span><span class="sxs-lookup"><span data-stu-id="78aca-128">High availability, failover, and disaster recovery</span></span></p></td>
<td><p><span data-ttu-id="78aca-129">예</span><span class="sxs-lookup"><span data-stu-id="78aca-129">Yes</span></span></p></td>
<td><p><span data-ttu-id="78aca-130">아니요</span><span class="sxs-lookup"><span data-stu-id="78aca-130">No</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

