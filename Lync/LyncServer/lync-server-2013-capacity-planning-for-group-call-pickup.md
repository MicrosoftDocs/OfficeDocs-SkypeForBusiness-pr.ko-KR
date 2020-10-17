---
title: 'Lync Server 2013: 그룹 통화 픽업 용량 계획'
description: 'Lync Server 2013: 그룹 통화 픽업 용량 계획'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Capacity planning for Group Call Pickup
ms:assetid: 0d654a19-6cf0-4118-903d-ec2c4e519253
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ984297(v=OCS.15)
ms:contentKeyID: 51476680
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 12648c57d1036a0ed27c60ef6399bf570c5dcd3d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544534"
---
# <a name="capacity-planning-for-group-call-pickup-in-lync-server-2013"></a><span data-ttu-id="25bf4-103">Lync Server 2013의 그룹 통화 픽업 용량 계획</span><span class="sxs-lookup"><span data-stu-id="25bf4-103">Capacity planning for Group Call Pickup in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="25bf4-104">_**마지막으로 수정 된 항목:** 2013-02-12_</span><span class="sxs-lookup"><span data-stu-id="25bf4-104">_**Topic Last Modified:** 2013-02-12_</span></span>

<div id="sectionSection0" class="section">

<span data-ttu-id="25bf4-105">다음 표에서는 용량 계획 요구 사항의 기반으로 사용할 수 있는 그룹 통화 픽업 사용자 모델에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="25bf4-105">The following table describes the Group Call Pickup user model that you can use as the basis for capacity planning requirements.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="25bf4-106">그룹 통화 픽업는 통화 대기 응용 프로그램을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="25bf4-106">Group Call Pickup is based on the Call Park application.</span></span> <span data-ttu-id="25bf4-107">재해 복구 용량 계획을 위해 연결 된 풀의 각 풀은 두 풀에서 그룹 호출 픽업을 포함 하 여 통화 대기 서비스의 작업을 처리할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="25bf4-107">Keep in mind that, for disaster recovery capacity planning, each pool of a paired pool should be able to handle the workloads for Call Park services, including Group Call Pickup, in both pools.</span></span>



</div>

### <a name="group-call-pickup-user-model"></a><span data-ttu-id="25bf4-108">그룹 통화 픽업 사용자 모델</span><span class="sxs-lookup"><span data-stu-id="25bf4-108">Group Call Pickup User Model</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="25bf4-109">메트릭</span><span class="sxs-lookup"><span data-stu-id="25bf4-109">Metric</span></span></th>
<th><span data-ttu-id="25bf4-110">프런트 엔드 풀 당 (8 개의 프런트 엔드 서버 포함)</span><span class="sxs-lookup"><span data-stu-id="25bf4-110">Per Front End pool (with 8 Front End Servers)</span></span></th>
<th><span data-ttu-id="25bf4-111">Standard Edition Server별</span><span class="sxs-lookup"><span data-stu-id="25bf4-111">Per Standard Edition server</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="25bf4-112">그룹 당 추천 사용자 수</span><span class="sxs-lookup"><span data-stu-id="25bf4-112">Recommended number of users per group</span></span></p></td>
<td><p><span data-ttu-id="25bf4-113">50</span><span class="sxs-lookup"><span data-stu-id="25bf4-113">50</span></span></p></td>
<td><p><span data-ttu-id="25bf4-114">50</span><span class="sxs-lookup"><span data-stu-id="25bf4-114">50</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25bf4-115">권장 그룹 수</span><span class="sxs-lookup"><span data-stu-id="25bf4-115">Recommended number of groups</span></span></p></td>
<td><p><span data-ttu-id="25bf4-116">500</span><span class="sxs-lookup"><span data-stu-id="25bf4-116">500</span></span></p></td>
<td><p><span data-ttu-id="25bf4-117">60</span><span class="sxs-lookup"><span data-stu-id="25bf4-117">60</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="25bf4-118">그룹 통화 픽업에 사용 하도록 설정 된 풀 당 최대 사용자 수</span><span class="sxs-lookup"><span data-stu-id="25bf4-118">Maximum number of users per pool enabled for Group Call Pickup</span></span></p></td>
<td><p><span data-ttu-id="25bf4-119">25,000</span><span class="sxs-lookup"><span data-stu-id="25bf4-119">25,000</span></span></p></td>
<td><p><span data-ttu-id="25bf4-120">3000</span><span class="sxs-lookup"><span data-stu-id="25bf4-120">3,000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25bf4-121">분당 그룹 통화 픽업 트럭에 대해 사용 하도록 설정 된 총 사용자에 대 한 수신 전화의 최대 속도입니다.</span><span class="sxs-lookup"><span data-stu-id="25bf4-121">Maximum rate of incoming calls to total users enabled for Group Call Pickup per pool per minute</span></span></p></td>
<td><p><span data-ttu-id="25bf4-122">500</span><span class="sxs-lookup"><span data-stu-id="25bf4-122">500</span></span></p></td>
<td><p><span data-ttu-id="25bf4-123">60</span><span class="sxs-lookup"><span data-stu-id="25bf4-123">60</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="25bf4-124">분당 그룹 호출 픽업가 있는 사용자가 검색 한 통화의 최대 속도입니다.</span><span class="sxs-lookup"><span data-stu-id="25bf4-124">Maximum rate of calls retrieved by users with Group Call Pickup per pool per minute</span></span></p></td>
<td><p><span data-ttu-id="25bf4-125">200</span><span class="sxs-lookup"><span data-stu-id="25bf4-125">200</span></span></p></td>
<td><p><span data-ttu-id="25bf4-126">25@@</span><span class="sxs-lookup"><span data-stu-id="25bf4-126">25</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <UL>
> <LI>
> <P><span data-ttu-id="25bf4-127">프런트 엔드 서버가 8 개 미만인 프런트 엔드 풀의 경우 메트릭을 선형으로 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="25bf4-127">For Front End pools that have fewer than eight Front End Servers, calculate the metrics linearly.</span></span> <span data-ttu-id="25bf4-128">예를 들어 프런트 엔드 풀에 프런트 엔드 서버가 하나인 경우 표에 표시 된 값의 최대 부하를 1/8으로 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="25bf4-128">For example, if your Front End pool has one Front End Server, calculate the maximum load as 1/8 of the values shown in the table.</span></span></P>
> <LI>
> <P><span data-ttu-id="25bf4-129">풀 당 최대 사용자 수를 초과 하지 않을 경우 그룹 당 권장 되는 사용자 수와 그룹 수를 늘리거나 낮출 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25bf4-129">You can increase or decrease the recommended number of users per group and number of groups as long as you do not exceed the maximum number of users per pool.</span></span> <span data-ttu-id="25bf4-130">예를 들어 그룹 통화 픽업에 사용 하도록 설정 된 사용자 수가 사용자 모델 최대 (즉, 120 그룹 시간 25 명의 사용자는 그룹 통화 픽업에 사용 하도록 설정 3000 된 경우) 이므로 Standard Edition 서버는 그룹 당 사용자가 25 명 인 120 그룹을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25bf4-130">For example, your Standard Edition server can have 120 groups with 25 users per group because the number of users enabled for Group Call Pickup is still within the user model maximum (that is, 120 groups times 25 users is 3,000 users enabled for Group Call Pickup).</span></span></P></LI></UL>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

