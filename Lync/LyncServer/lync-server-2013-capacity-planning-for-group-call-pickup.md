---
title: 'Lync Server 2013: 그룹 통화 픽업 용량 계획'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Capacity planning for Group Call Pickup
ms:assetid: 0d654a19-6cf0-4118-903d-ec2c4e519253
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ984297(v=OCS.15)
ms:contentKeyID: 51476680
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ba588de723e7482039fdae4b97991080a1b92c47
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983354"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="capacity-planning-for-group-call-pickup-in-lync-server-2013"></a><span data-ttu-id="8e520-102">Lync Server 2013의 그룹 통화 픽업에 대 한 용량 계획</span><span class="sxs-lookup"><span data-stu-id="8e520-102">Capacity planning for Group Call Pickup in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8e520-103">_**마지막으로 수정한 주제:** 2013-02-12_</span><span class="sxs-lookup"><span data-stu-id="8e520-103">_**Topic Last Modified:** 2013-02-12_</span></span>

<div id="sectionSection0" class="section">

<span data-ttu-id="8e520-104">다음 표에서는 용량 계획 요구 사항의 기준으로 사용할 수 있는 그룹 통화 픽업 사용자 모델에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e520-104">The following table describes the Group Call Pickup user model that you can use as the basis for capacity planning requirements.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="8e520-105">그룹 통화 픽업는 통화 공원 응용 프로그램을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e520-105">Group Call Pickup is based on the Call Park application.</span></span> <span data-ttu-id="8e520-106">재해 복구 용량 계획을 위해 쌍으로 연결 된 풀의 각 풀은 그룹 통화 픽업을 포함 한 통화 공원 서비스의 작업량을 두 풀에서 처리할 수 있어야 한다는 점에 유의 하세요.</span><span class="sxs-lookup"><span data-stu-id="8e520-106">Keep in mind that, for disaster recovery capacity planning, each pool of a paired pool should be able to handle the workloads for Call Park services, including Group Call Pickup, in both pools.</span></span>



</div>

### <a name="group-call-pickup-user-model"></a><span data-ttu-id="8e520-107">그룹 통화 픽업 사용자 모델</span><span class="sxs-lookup"><span data-stu-id="8e520-107">Group Call Pickup User Model</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8e520-108">미터</span><span class="sxs-lookup"><span data-stu-id="8e520-108">Metric</span></span></th>
<th><span data-ttu-id="8e520-109">프런트 엔드 풀 단위 (프런트 엔드 서버 8 개)</span><span class="sxs-lookup"><span data-stu-id="8e520-109">Per Front End pool (with 8 Front End Servers)</span></span></th>
<th><span data-ttu-id="8e520-110">스탠더드 에디션 서버 당</span><span class="sxs-lookup"><span data-stu-id="8e520-110">Per Standard Edition server</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8e520-111">그룹 당 권장 되는 사용자 수</span><span class="sxs-lookup"><span data-stu-id="8e520-111">Recommended number of users per group</span></span></p></td>
<td><p><span data-ttu-id="8e520-112">50</span><span class="sxs-lookup"><span data-stu-id="8e520-112">50</span></span></p></td>
<td><p><span data-ttu-id="8e520-113">50</span><span class="sxs-lookup"><span data-stu-id="8e520-113">50</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8e520-114">추천 그룹 수</span><span class="sxs-lookup"><span data-stu-id="8e520-114">Recommended number of groups</span></span></p></td>
<td><p><span data-ttu-id="8e520-115">500</span><span class="sxs-lookup"><span data-stu-id="8e520-115">500</span></span></p></td>
<td><p><span data-ttu-id="8e520-116">60</span><span class="sxs-lookup"><span data-stu-id="8e520-116">60</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8e520-117">그룹 통화 픽업에 사용할 수 있는 풀 당 최대 사용자 수</span><span class="sxs-lookup"><span data-stu-id="8e520-117">Maximum number of users per pool enabled for Group Call Pickup</span></span></p></td>
<td><p><span data-ttu-id="8e520-118">25000</span><span class="sxs-lookup"><span data-stu-id="8e520-118">25,000</span></span></p></td>
<td><p><span data-ttu-id="8e520-119">3000</span><span class="sxs-lookup"><span data-stu-id="8e520-119">3,000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8e520-120">분당 그룹 통화 픽업에 대해 사용 하도록 설정 된 총 사용자에 대 한 최대 수신 통화 속도입니다.</span><span class="sxs-lookup"><span data-stu-id="8e520-120">Maximum rate of incoming calls to total users enabled for Group Call Pickup per pool per minute</span></span></p></td>
<td><p><span data-ttu-id="8e520-121">500</span><span class="sxs-lookup"><span data-stu-id="8e520-121">500</span></span></p></td>
<td><p><span data-ttu-id="8e520-122">60</span><span class="sxs-lookup"><span data-stu-id="8e520-122">60</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8e520-123">분 당 그룹 통화 픽업 트럭을 사용 하 여 사용자가 검색 한 통화의 최대 속도입니다.</span><span class="sxs-lookup"><span data-stu-id="8e520-123">Maximum rate of calls retrieved by users with Group Call Pickup per pool per minute</span></span></p></td>
<td><p><span data-ttu-id="8e520-124">200</span><span class="sxs-lookup"><span data-stu-id="8e520-124">200</span></span></p></td>
<td><p><span data-ttu-id="8e520-125">km</span><span class="sxs-lookup"><span data-stu-id="8e520-125">25</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <UL>
> <LI>
> <P><span data-ttu-id="8e520-126">프런트 엔드 서버를 8 개 미만으로 하는 프런트 엔드 풀의 경우 메트릭을 선형으로 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e520-126">For Front End pools that have fewer than eight Front End Servers, calculate the metrics linearly.</span></span> <span data-ttu-id="8e520-127">예를 들어 프런트 엔드 풀에 프런트 엔드 서버가 한 개 있는 경우 최대 로드를 표에 표시 된 값의 1/8로 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e520-127">For example, if your Front End pool has one Front End Server, calculate the maximum load as 1/8 of the values shown in the table.</span></span></P>
> <LI>
> <P><span data-ttu-id="8e520-128">풀 당 최대 사용자 수를 초과 하지 않는 한 그룹 당 권장 되는 사용자 수와 그룹 수를 늘리거나 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e520-128">You can increase or decrease the recommended number of users per group and number of groups as long as you do not exceed the maximum number of users per pool.</span></span> <span data-ttu-id="8e520-129">예를 들어 그룹 통화 픽업에 대해 사용 하도록 설정 된 사용자 수가 최대 사용자 모델 (즉, 120 그룹 시간 25 명의 사용자는 그룹 통화 픽업에 대해 사용 하도록 설정 3000 되어 있음)에 포함 되어 있기 때문에 Standard Edition 서버는 그룹당 25 명의 사용자를 갖는 120 그룹을 가질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e520-129">For example, your Standard Edition server can have 120 groups with 25 users per group because the number of users enabled for Group Call Pickup is still within the user model maximum (that is, 120 groups times 25 users is 3,000 users enabled for Group Call Pickup).</span></span></P></LI></UL>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

