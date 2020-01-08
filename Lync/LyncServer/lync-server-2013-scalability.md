---
title: Lync Server 2013 확장성
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Scalability
ms:assetid: 46fa0cb5-1507-4a12-ad3f-ba64585e2dc4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg417160(v=OCS.15)
ms:contentKeyID: 48183995
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0dfdc96934871fd2e73af30507288c734e786cc0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985235"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="scalability-with-lync-server-2013"></a><span data-ttu-id="e1069-102">Lync Server 2013의 확장성</span><span class="sxs-lookup"><span data-stu-id="e1069-102">Scalability with Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e1069-103">_**마지막으로 수정한 주제:** 2012-06-25_</span><span class="sxs-lookup"><span data-stu-id="e1069-103">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="e1069-104">Lync Server는 두 버전, Enterprise Edition 및 Standard Edition에서 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e1069-104">Lync Server is offered in two editions, Enterprise Edition and Standard Edition.</span></span> <span data-ttu-id="e1069-105">여러 버전은 주로 다양 한 규모의 조직에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e1069-105">The different editions are intended primarily for different sizes of organizations.</span></span> <span data-ttu-id="e1069-106">다음 표에 나와 있는 것 처럼, 두 버전 모두 작업 부하의 모든 기능을 지원 하며, 고가용성 및 재해 복구를 제외 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1069-106">As shown in the following table, both editions support all functionality in all workloads, except for high availability and disaster recovery.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e1069-107">기능</span><span class="sxs-lookup"><span data-stu-id="e1069-107">Feature</span></span></th>
<th><span data-ttu-id="e1069-108">Enterprise Edition에서 지원 되나요?</span><span class="sxs-lookup"><span data-stu-id="e1069-108">Supported in Enterprise Edition?</span></span></th>
<th><span data-ttu-id="e1069-109">스탠더드 버전에서 지원 되나요?</span><span class="sxs-lookup"><span data-stu-id="e1069-109">Supported in Standard Edition?</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e1069-110">인스턴트 메시지 (IM) 및 현재 상태</span><span class="sxs-lookup"><span data-stu-id="e1069-110">Instant messaging (IM) and presence</span></span></p></td>
<td><p><span data-ttu-id="e1069-111">예</span><span class="sxs-lookup"><span data-stu-id="e1069-111">Yes</span></span></p></td>
<td><p><span data-ttu-id="e1069-112">예</span><span class="sxs-lookup"><span data-stu-id="e1069-112">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e1069-113">회의</span><span class="sxs-lookup"><span data-stu-id="e1069-113">Conferencing</span></span></p></td>
<td><p><span data-ttu-id="e1069-114">예</span><span class="sxs-lookup"><span data-stu-id="e1069-114">Yes</span></span></p></td>
<td><p><span data-ttu-id="e1069-115">예</span><span class="sxs-lookup"><span data-stu-id="e1069-115">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e1069-116">A/V 회의</span><span class="sxs-lookup"><span data-stu-id="e1069-116">A/V conferencing</span></span></p></td>
<td><p><span data-ttu-id="e1069-117">예</span><span class="sxs-lookup"><span data-stu-id="e1069-117">Yes</span></span></p></td>
<td><p><span data-ttu-id="e1069-118">예</span><span class="sxs-lookup"><span data-stu-id="e1069-118">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e1069-119">전화 접속 회의</span><span class="sxs-lookup"><span data-stu-id="e1069-119">Dial-in conferencing</span></span></p></td>
<td><p><span data-ttu-id="e1069-120">예</span><span class="sxs-lookup"><span data-stu-id="e1069-120">Yes</span></span></p></td>
<td><p><span data-ttu-id="e1069-121">예</span><span class="sxs-lookup"><span data-stu-id="e1069-121">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e1069-122">Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="e1069-122">Enterprise Voice</span></span></p></td>
<td><p><span data-ttu-id="e1069-123">예</span><span class="sxs-lookup"><span data-stu-id="e1069-123">Yes</span></span></p></td>
<td><p><span data-ttu-id="e1069-124">예</span><span class="sxs-lookup"><span data-stu-id="e1069-124">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e1069-125">가상</span><span class="sxs-lookup"><span data-stu-id="e1069-125">Virtualization</span></span></p></td>
<td><p><span data-ttu-id="e1069-126">예</span><span class="sxs-lookup"><span data-stu-id="e1069-126">Yes</span></span></p></td>
<td><p><span data-ttu-id="e1069-127">예</span><span class="sxs-lookup"><span data-stu-id="e1069-127">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e1069-128">고가용성, 장애 조치 및 재해 복구</span><span class="sxs-lookup"><span data-stu-id="e1069-128">High availability, failover, and disaster recovery</span></span></p></td>
<td><p><span data-ttu-id="e1069-129">예</span><span class="sxs-lookup"><span data-stu-id="e1069-129">Yes</span></span></p></td>
<td><p><span data-ttu-id="e1069-130">아니요</span><span class="sxs-lookup"><span data-stu-id="e1069-130">No</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

