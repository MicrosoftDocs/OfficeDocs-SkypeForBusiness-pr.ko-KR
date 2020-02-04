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
ms.openlocfilehash: e6ff4828bdfddbfca7734836fdfdbe24f0b90c4a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765016"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="scalability-with-lync-server-2013"></a><span data-ttu-id="d315e-102">Lync Server 2013의 확장성</span><span class="sxs-lookup"><span data-stu-id="d315e-102">Scalability with Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d315e-103">_**마지막으로 수정한 주제:** 2012-06-25_</span><span class="sxs-lookup"><span data-stu-id="d315e-103">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="d315e-104">Lync Server는 두 버전, Enterprise Edition 및 Standard Edition에서 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d315e-104">Lync Server is offered in two editions, Enterprise Edition and Standard Edition.</span></span> <span data-ttu-id="d315e-105">여러 버전은 주로 다양 한 규모의 조직에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d315e-105">The different editions are intended primarily for different sizes of organizations.</span></span> <span data-ttu-id="d315e-106">다음 표에 나와 있는 것 처럼, 두 버전 모두 작업 부하의 모든 기능을 지원 하며, 고가용성 및 재해 복구를 제외 합니다.</span><span class="sxs-lookup"><span data-stu-id="d315e-106">As shown in the following table, both editions support all functionality in all workloads, except for high availability and disaster recovery.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d315e-107">기능</span><span class="sxs-lookup"><span data-stu-id="d315e-107">Feature</span></span></th>
<th><span data-ttu-id="d315e-108">Enterprise Edition에서 지원 되나요?</span><span class="sxs-lookup"><span data-stu-id="d315e-108">Supported in Enterprise Edition?</span></span></th>
<th><span data-ttu-id="d315e-109">스탠더드 버전에서 지원 되나요?</span><span class="sxs-lookup"><span data-stu-id="d315e-109">Supported in Standard Edition?</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d315e-110">인스턴트 메시지 (IM) 및 현재 상태</span><span class="sxs-lookup"><span data-stu-id="d315e-110">Instant messaging (IM) and presence</span></span></p></td>
<td><p><span data-ttu-id="d315e-111">예</span><span class="sxs-lookup"><span data-stu-id="d315e-111">Yes</span></span></p></td>
<td><p><span data-ttu-id="d315e-112">예</span><span class="sxs-lookup"><span data-stu-id="d315e-112">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d315e-113">회의</span><span class="sxs-lookup"><span data-stu-id="d315e-113">Conferencing</span></span></p></td>
<td><p><span data-ttu-id="d315e-114">예</span><span class="sxs-lookup"><span data-stu-id="d315e-114">Yes</span></span></p></td>
<td><p><span data-ttu-id="d315e-115">예</span><span class="sxs-lookup"><span data-stu-id="d315e-115">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d315e-116">A/V 회의</span><span class="sxs-lookup"><span data-stu-id="d315e-116">A/V conferencing</span></span></p></td>
<td><p><span data-ttu-id="d315e-117">예</span><span class="sxs-lookup"><span data-stu-id="d315e-117">Yes</span></span></p></td>
<td><p><span data-ttu-id="d315e-118">예</span><span class="sxs-lookup"><span data-stu-id="d315e-118">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d315e-119">전화 접속 회의</span><span class="sxs-lookup"><span data-stu-id="d315e-119">Dial-in conferencing</span></span></p></td>
<td><p><span data-ttu-id="d315e-120">예</span><span class="sxs-lookup"><span data-stu-id="d315e-120">Yes</span></span></p></td>
<td><p><span data-ttu-id="d315e-121">예</span><span class="sxs-lookup"><span data-stu-id="d315e-121">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d315e-122">Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="d315e-122">Enterprise Voice</span></span></p></td>
<td><p><span data-ttu-id="d315e-123">예</span><span class="sxs-lookup"><span data-stu-id="d315e-123">Yes</span></span></p></td>
<td><p><span data-ttu-id="d315e-124">예</span><span class="sxs-lookup"><span data-stu-id="d315e-124">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d315e-125">가상</span><span class="sxs-lookup"><span data-stu-id="d315e-125">Virtualization</span></span></p></td>
<td><p><span data-ttu-id="d315e-126">예</span><span class="sxs-lookup"><span data-stu-id="d315e-126">Yes</span></span></p></td>
<td><p><span data-ttu-id="d315e-127">예</span><span class="sxs-lookup"><span data-stu-id="d315e-127">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d315e-128">고가용성, 장애 조치 및 재해 복구</span><span class="sxs-lookup"><span data-stu-id="d315e-128">High availability, failover, and disaster recovery</span></span></p></td>
<td><p><span data-ttu-id="d315e-129">예</span><span class="sxs-lookup"><span data-stu-id="d315e-129">Yes</span></span></p></td>
<td><p><span data-ttu-id="d315e-130">아니요</span><span class="sxs-lookup"><span data-stu-id="d315e-130">No</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

