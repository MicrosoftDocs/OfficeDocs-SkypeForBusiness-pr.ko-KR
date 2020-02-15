---
title: 'Lync Server 2013: 장애 조치 (failover) 경로 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring a failover route
ms:assetid: 76e48df4-3b78-4fb7-b1f7-c1e604b81bad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398581(v=OCS.15)
ms:contentKeyID: 48184542
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 17477c647d2e5dd5918225486c43b93a29509fb2
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034228"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-a-failover-route-in-lync-server-2013"></a><span data-ttu-id="59be0-102">Lync Server 2013에서 장애 조치 (failover) 경로 구성</span><span class="sxs-lookup"><span data-stu-id="59be0-102">Configuring a failover route in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="59be0-103">_**마지막으로 수정 된 항목:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="59be0-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="59be0-p101">다음 예제에서는 관리자가 Dallas-GW1이 유지 관리를 위해 다운되거나 다른 이유로 인해 사용할 수 없는 경우 사용할 장애 조치(failover) 경로를 정의할 수 있는 방법을 보여 줍니다. 다음 표에서는 필요한 구성 변경을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="59be0-p101">The following example shows how an administrator can define a failover route for use if the Dallas-GW1 is down for maintenance or is otherwise unavailable. The following tables illustrate the required configuration change.</span></span>

### <a name="table-1-user-policy"></a><span data-ttu-id="59be0-p102">표 1. 사용자 정책</span><span class="sxs-lookup"><span data-stu-id="59be0-p102">Table 1. User Policy</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="59be0-108">사용자 정책</span><span class="sxs-lookup"><span data-stu-id="59be0-108">User policy</span></span></th>
<th><span data-ttu-id="59be0-109">전화 사용</span><span class="sxs-lookup"><span data-stu-id="59be0-109">Phone usage</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="59be0-110">기본 통화 정책</span><span class="sxs-lookup"><span data-stu-id="59be0-110">Default Calling Policy</span></span></p></td>
<td><p><span data-ttu-id="59be0-111">Local</span><span class="sxs-lookup"><span data-stu-id="59be0-111">Local</span></span></p>
<p><span data-ttu-id="59be0-112">GlobalPSTNHopoff</span><span class="sxs-lookup"><span data-stu-id="59be0-112">GlobalPSTNHopoff</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59be0-113">레드몬드 시내 정책</span><span class="sxs-lookup"><span data-stu-id="59be0-113">Redmond Local Policy</span></span></p></td>
<td><p><span data-ttu-id="59be0-114">RedmondLocal</span><span class="sxs-lookup"><span data-stu-id="59be0-114">RedmondLocal</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59be0-115">달라스 통화 정책</span><span class="sxs-lookup"><span data-stu-id="59be0-115">Dallas Calling Policy</span></span></p></td>
<td><p><span data-ttu-id="59be0-116">DallasUsers</span><span class="sxs-lookup"><span data-stu-id="59be0-116">DallasUsers</span></span></p>
<p><span data-ttu-id="59be0-117">GlobalPSTNHopoff</span><span class="sxs-lookup"><span data-stu-id="59be0-117">GlobalPSTNHopoff</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="table-2-routes"></a><span data-ttu-id="59be0-p103">표 2. 경로</span><span class="sxs-lookup"><span data-stu-id="59be0-p103">Table 2. Routes</span></span>

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
<th><span data-ttu-id="59be0-120">경로 이름</span><span class="sxs-lookup"><span data-stu-id="59be0-120">Route name</span></span></th>
<th><span data-ttu-id="59be0-121">발신 제한</span><span class="sxs-lookup"><span data-stu-id="59be0-121">Number pattern</span></span></th>
<th><span data-ttu-id="59be0-122">전화 사용</span><span class="sxs-lookup"><span data-stu-id="59be0-122">Phone usage</span></span></th>
<th><span data-ttu-id="59be0-123">트렁크</span><span class="sxs-lookup"><span data-stu-id="59be0-123">Trunk</span></span></th>
<th><span data-ttu-id="59be0-124">게이트웨이</span><span class="sxs-lookup"><span data-stu-id="59be0-124">Gateway</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="59be0-125">레드몬드 시내 경로</span><span class="sxs-lookup"><span data-stu-id="59be0-125">Redmond Local Route</span></span></p></td>
<td><p><span data-ttu-id="59be0-126">^\+1 (425 | 206 | 253) (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="59be0-126">^\+1(425|206|253)(\d{7})$</span></span></p></td>
<td><p><span data-ttu-id="59be0-127">Local</span><span class="sxs-lookup"><span data-stu-id="59be0-127">Local</span></span></p>
<p><span data-ttu-id="59be0-128">RedmondLocal</span><span class="sxs-lookup"><span data-stu-id="59be0-128">RedmondLocal</span></span></p></td>
<td><p><span data-ttu-id="59be0-129">Trunk1</span><span class="sxs-lookup"><span data-stu-id="59be0-129">Trunk1</span></span></p>
<p><span data-ttu-id="59be0-130">Trunk2</span><span class="sxs-lookup"><span data-stu-id="59be0-130">Trunk2</span></span></p></td>
<td><p><span data-ttu-id="59be0-131">레드-GW1</span><span class="sxs-lookup"><span data-stu-id="59be0-131">Red-GW1</span></span></p>
<p><span data-ttu-id="59be0-132">레드-GW2</span><span class="sxs-lookup"><span data-stu-id="59be0-132">Red-GW2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59be0-133">달라스 시내 경로</span><span class="sxs-lookup"><span data-stu-id="59be0-133">Dallas Local Route</span></span></p></td>
<td><p><span data-ttu-id="59be0-134">^\+1 (972 | 214 | 469) (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="59be0-134">^\+1(972|214|469)(\d{7})$</span></span></p></td>
<td><p><span data-ttu-id="59be0-135">Local</span><span class="sxs-lookup"><span data-stu-id="59be0-135">Local</span></span></p></td>
<td><p><span data-ttu-id="59be0-136">Trunk3</span><span class="sxs-lookup"><span data-stu-id="59be0-136">Trunk3</span></span></p></td>
<td><p><span data-ttu-id="59be0-137">달라스-GW1</span><span class="sxs-lookup"><span data-stu-id="59be0-137">Dallas-GW1</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59be0-138">범용 경로</span><span class="sxs-lookup"><span data-stu-id="59be0-138">Universal Route</span></span></p></td>
<td><p><span data-ttu-id="59be0-139">^\+? (\d \*) $</span><span class="sxs-lookup"><span data-stu-id="59be0-139">^\+?(\d\*)$</span></span></p></td>
<td><p><span data-ttu-id="59be0-140">GlobalPSTNHopoff</span><span class="sxs-lookup"><span data-stu-id="59be0-140">GlobalPSTNHopoff</span></span></p></td>
<td><p><span data-ttu-id="59be0-141">Trunk1</span><span class="sxs-lookup"><span data-stu-id="59be0-141">Trunk1</span></span></p>
<p><span data-ttu-id="59be0-142">Trunk2</span><span class="sxs-lookup"><span data-stu-id="59be0-142">Trunk2</span></span></p>
<p><span data-ttu-id="59be0-143">Trunk3</span><span class="sxs-lookup"><span data-stu-id="59be0-143">Trunk3</span></span></p></td>
<td><p><span data-ttu-id="59be0-144">레드-GW1</span><span class="sxs-lookup"><span data-stu-id="59be0-144">Red-GW1</span></span></p>
<p><span data-ttu-id="59be0-145">레드-GW2</span><span class="sxs-lookup"><span data-stu-id="59be0-145">Red-GW2</span></span></p>
<p><span data-ttu-id="59be0-146">달라스-GW1</span><span class="sxs-lookup"><span data-stu-id="59be0-146">Dallas-GW1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59be0-147">달라스 사용자 경로</span><span class="sxs-lookup"><span data-stu-id="59be0-147">Dallas Users Route</span></span></p></td>
<td><p><span data-ttu-id="59be0-148">^\+? (\d \*) $</span><span class="sxs-lookup"><span data-stu-id="59be0-148">^\+?(\d\*)$</span></span></p></td>
<td><p><span data-ttu-id="59be0-149">DallasUsers</span><span class="sxs-lookup"><span data-stu-id="59be0-149">DallasUsers</span></span></p></td>
<td><p><span data-ttu-id="59be0-150">Trunk3</span><span class="sxs-lookup"><span data-stu-id="59be0-150">Trunk3</span></span></p></td>
<td><p><span data-ttu-id="59be0-151">달라스-GW1</span><span class="sxs-lookup"><span data-stu-id="59be0-151">Dallas-GW1</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="59be0-p104">표 1에서 GlobalPSTNHopoff의 전화 사용은 달라스 통화 정책의 DallasUsers 전화 사용 뒤에 추가됩니다. 이렇게 하면 DallasUsers 전화 사용의 경로를 사용할 수 없는 경우 달라스 통화 정책의 통화가 GlobalPSTNHopoff 전화에 대해 구성된 경로를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59be0-p104">In Table 1, a phone usage of GlobalPSTNHopoff is added after the DallasUsers phone usage in the Dallas Calling Policy. This enables calls with the Dallas Calling policy to use routes that are configured for the GlobalPSTNHopoff phone usage if a route for the DallasUsers phone usage is unavailable.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

