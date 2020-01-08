---
title: 'Lync Server 2013: 장애 조치(failover) 경로 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring a failover route
ms:assetid: 76e48df4-3b78-4fb7-b1f7-c1e604b81bad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398581(v=OCS.15)
ms:contentKeyID: 48184542
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9e65070326c82e3a30977b3512bd2785d6bb4bd2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985776"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-a-failover-route-in-lync-server-2013"></a><span data-ttu-id="cba2b-102">Lync Server 2013에서 장애 조치(failover) 경로 구성</span><span class="sxs-lookup"><span data-stu-id="cba2b-102">Configuring a failover route in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cba2b-103">_**마지막으로 수정한 주제:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="cba2b-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="cba2b-104">다음 예에서는 관리자가 GW1에서 유지 관리를 위해 중단 되거나 사용할 수 없는 경우에 사용할 장애 조치 경로를 정의 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="cba2b-104">The following example shows how an administrator can define a failover route for use if the Dallas-GW1 is down for maintenance or is otherwise unavailable.</span></span> <span data-ttu-id="cba2b-105">다음 표에는 필요한 구성 변경 내용이 설명 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cba2b-105">The following tables illustrate the required configuration change.</span></span>

### <a name="table-1-user-policy"></a><span data-ttu-id="cba2b-106">표 1</span><span class="sxs-lookup"><span data-stu-id="cba2b-106">Table 1.</span></span> <span data-ttu-id="cba2b-107">사용자 정책</span><span class="sxs-lookup"><span data-stu-id="cba2b-107">User Policy</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cba2b-108">사용자 정책</span><span class="sxs-lookup"><span data-stu-id="cba2b-108">User policy</span></span></th>
<th><span data-ttu-id="cba2b-109">전화 사용</span><span class="sxs-lookup"><span data-stu-id="cba2b-109">Phone usage</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cba2b-110">기본 통화 정책</span><span class="sxs-lookup"><span data-stu-id="cba2b-110">Default Calling Policy</span></span></p></td>
<td><p><span data-ttu-id="cba2b-111">로컬</span><span class="sxs-lookup"><span data-stu-id="cba2b-111">Local</span></span></p>
<p><span data-ttu-id="cba2b-112">GlobalPSTNHopoff</span><span class="sxs-lookup"><span data-stu-id="cba2b-112">GlobalPSTNHopoff</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cba2b-113">Redmond 로컬 정책</span><span class="sxs-lookup"><span data-stu-id="cba2b-113">Redmond Local Policy</span></span></p></td>
<td><p><span data-ttu-id="cba2b-114">RedmondLocal</span><span class="sxs-lookup"><span data-stu-id="cba2b-114">RedmondLocal</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cba2b-115">달라스 호출 정책</span><span class="sxs-lookup"><span data-stu-id="cba2b-115">Dallas Calling Policy</span></span></p></td>
<td><p><span data-ttu-id="cba2b-116">DallasUsers</span><span class="sxs-lookup"><span data-stu-id="cba2b-116">DallasUsers</span></span></p>
<p><span data-ttu-id="cba2b-117">GlobalPSTNHopoff</span><span class="sxs-lookup"><span data-stu-id="cba2b-117">GlobalPSTNHopoff</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="table-2-routes"></a><span data-ttu-id="cba2b-118">표 2.</span><span class="sxs-lookup"><span data-stu-id="cba2b-118">Table 2.</span></span> <span data-ttu-id="cba2b-119">경로도</span><span class="sxs-lookup"><span data-stu-id="cba2b-119">Routes</span></span>

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cba2b-120">경로 이름</span><span class="sxs-lookup"><span data-stu-id="cba2b-120">Route name</span></span></th>
<th><span data-ttu-id="cba2b-121">번호 패턴</span><span class="sxs-lookup"><span data-stu-id="cba2b-121">Number pattern</span></span></th>
<th><span data-ttu-id="cba2b-122">전화 사용</span><span class="sxs-lookup"><span data-stu-id="cba2b-122">Phone usage</span></span></th>
<th><span data-ttu-id="cba2b-123">트렁크</span><span class="sxs-lookup"><span data-stu-id="cba2b-123">Trunk</span></span></th>
<th><span data-ttu-id="cba2b-124">게이트웨이와</span><span class="sxs-lookup"><span data-stu-id="cba2b-124">Gateway</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cba2b-125">Redmond 로컬 경로</span><span class="sxs-lookup"><span data-stu-id="cba2b-125">Redmond Local Route</span></span></p></td>
<td><p><span data-ttu-id="cba2b-126">^\+1 (425 | 206 | 253) (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="cba2b-126">^\+1(425|206|253)(\d{7})$</span></span></p></td>
<td><p><span data-ttu-id="cba2b-127">로컬</span><span class="sxs-lookup"><span data-stu-id="cba2b-127">Local</span></span></p>
<p><span data-ttu-id="cba2b-128">RedmondLocal</span><span class="sxs-lookup"><span data-stu-id="cba2b-128">RedmondLocal</span></span></p></td>
<td><p><span data-ttu-id="cba2b-129">Trunk1</span><span class="sxs-lookup"><span data-stu-id="cba2b-129">Trunk1</span></span></p>
<p><span data-ttu-id="cba2b-130">Trunk2</span><span class="sxs-lookup"><span data-stu-id="cba2b-130">Trunk2</span></span></p></td>
<td><p><span data-ttu-id="cba2b-131">빨강-GW1</span><span class="sxs-lookup"><span data-stu-id="cba2b-131">Red-GW1</span></span></p>
<p><span data-ttu-id="cba2b-132">빨강-GW2</span><span class="sxs-lookup"><span data-stu-id="cba2b-132">Red-GW2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cba2b-133">달라스 로컬 경로</span><span class="sxs-lookup"><span data-stu-id="cba2b-133">Dallas Local Route</span></span></p></td>
<td><p><span data-ttu-id="cba2b-134">^\+1 (972 | 214 | 469) (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="cba2b-134">^\+1(972|214|469)(\d{7})$</span></span></p></td>
<td><p><span data-ttu-id="cba2b-135">로컬</span><span class="sxs-lookup"><span data-stu-id="cba2b-135">Local</span></span></p></td>
<td><p><span data-ttu-id="cba2b-136">Trunk3</span><span class="sxs-lookup"><span data-stu-id="cba2b-136">Trunk3</span></span></p></td>
<td><p><span data-ttu-id="cba2b-137">달라스-GW1</span><span class="sxs-lookup"><span data-stu-id="cba2b-137">Dallas-GW1</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cba2b-138">유니버설 경로</span><span class="sxs-lookup"><span data-stu-id="cba2b-138">Universal Route</span></span></p></td>
<td><p><span data-ttu-id="cba2b-139">^\+? (\d \*) $</span><span class="sxs-lookup"><span data-stu-id="cba2b-139">^\+?(\d\*)$</span></span></p></td>
<td><p><span data-ttu-id="cba2b-140">GlobalPSTNHopoff</span><span class="sxs-lookup"><span data-stu-id="cba2b-140">GlobalPSTNHopoff</span></span></p></td>
<td><p><span data-ttu-id="cba2b-141">Trunk1</span><span class="sxs-lookup"><span data-stu-id="cba2b-141">Trunk1</span></span></p>
<p><span data-ttu-id="cba2b-142">Trunk2</span><span class="sxs-lookup"><span data-stu-id="cba2b-142">Trunk2</span></span></p>
<p><span data-ttu-id="cba2b-143">Trunk3</span><span class="sxs-lookup"><span data-stu-id="cba2b-143">Trunk3</span></span></p></td>
<td><p><span data-ttu-id="cba2b-144">빨강-GW1</span><span class="sxs-lookup"><span data-stu-id="cba2b-144">Red-GW1</span></span></p>
<p><span data-ttu-id="cba2b-145">빨강-GW2</span><span class="sxs-lookup"><span data-stu-id="cba2b-145">Red-GW2</span></span></p>
<p><span data-ttu-id="cba2b-146">달라스-GW1</span><span class="sxs-lookup"><span data-stu-id="cba2b-146">Dallas-GW1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cba2b-147">달라스 사용자 라우팅</span><span class="sxs-lookup"><span data-stu-id="cba2b-147">Dallas Users Route</span></span></p></td>
<td><p><span data-ttu-id="cba2b-148">^\+? (\d \*) $</span><span class="sxs-lookup"><span data-stu-id="cba2b-148">^\+?(\d\*)$</span></span></p></td>
<td><p><span data-ttu-id="cba2b-149">DallasUsers</span><span class="sxs-lookup"><span data-stu-id="cba2b-149">DallasUsers</span></span></p></td>
<td><p><span data-ttu-id="cba2b-150">Trunk3</span><span class="sxs-lookup"><span data-stu-id="cba2b-150">Trunk3</span></span></p></td>
<td><p><span data-ttu-id="cba2b-151">달라스-GW1</span><span class="sxs-lookup"><span data-stu-id="cba2b-151">Dallas-GW1</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="cba2b-152">표 1에서 GlobalPSTNHopoff의 전화 사용은 달라스 호출 정책의 DallasUsers 전화 사용 후에 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cba2b-152">In Table 1, a phone usage of GlobalPSTNHopoff is added after the DallasUsers phone usage in the Dallas Calling Policy.</span></span> <span data-ttu-id="cba2b-153">이렇게 하면 DallasUsers 전화 사용에 대 한 경로를 사용할 수 없는 경우 달라스 호출 정책으로 전화를 걸 때 GlobalPSTNHopoff 전화 사용에 대해 구성 된 경로를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cba2b-153">This enables calls with the Dallas Calling policy to use routes that are configured for the GlobalPSTNHopoff phone usage if a route for the DallasUsers phone usage is unavailable.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

