---
title: 'Lync Server 2013: Enterprise Voice 구성'
description: 'Lync Server 2013: Enterprise Voice를 구성 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Enterprise Voice
ms:assetid: 7df179fa-d3a2-4b23-a433-b750aedf980b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994041(v=OCS.15)
ms:contentKeyID: 51803952
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 49a231b92bf7b04aa3466927a79258f0cbad4e3f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548434"
---
# <a name="configuring-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="04023-103">Lync Server 2013에서 Enterprise Voice 구성</span><span class="sxs-lookup"><span data-stu-id="04023-103">Configuring Enterprise Voice in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="04023-104">_**마지막으로 수정 된 항목:** 2013-03-12_</span><span class="sxs-lookup"><span data-stu-id="04023-104">_**Topic Last Modified:** 2013-03-12_</span></span>

<span data-ttu-id="04023-105">Enterprise Voice를 배포 하려면 다음을 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="04023-105">To deploy Enterprise Voice, you’ll need to configure the following:</span></span>

  - <span data-ttu-id="04023-106">트렁크 만들기</span><span class="sxs-lookup"><span data-stu-id="04023-106">Create a Trunk</span></span>

  - <span data-ttu-id="04023-107">음성 정책 정의</span><span class="sxs-lookup"><span data-stu-id="04023-107">Define a Voice Policy</span></span>

  - <span data-ttu-id="04023-108">음성 경로 정의</span><span class="sxs-lookup"><span data-stu-id="04023-108">Define a Voice Route</span></span>

  - <span data-ttu-id="04023-109">사용자가 Enterprise Voice를 사용할 수 있도록 설정</span><span class="sxs-lookup"><span data-stu-id="04023-109">Enable Users for Enterprise Voice</span></span>

<div>

## <a name="create-a-trunk"></a><span data-ttu-id="04023-110">트렁크 만들기</span><span class="sxs-lookup"><span data-stu-id="04023-110">Create a Trunk</span></span>

<span data-ttu-id="04023-111">Enterprise Voice 배포에서 트렁크를 정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="04023-111">You must define trunks in your Enterprise Voice deployment.</span></span> <span data-ttu-id="04023-112">Location-Based 라우팅의 경우 트렁크 당 트렁크 구성을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="04023-112">For Location-Based Routing, you must create a trunk configuration per trunk.</span></span> <span data-ttu-id="04023-113">Lync Server 토폴로지 작성기를 사용 하 여 트렁크를 정의 하 고 Lync Server Windows PowerShell 명령, Get-cstrunkconfiguration 또는 Lync Server 제어판을 사용 하 여 해당 트렁크 구성을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="04023-113">Use the Lync Server Topology Builder to define your trunks, and use the Lync Server Windows PowerShell command, New-CsTrunkConfiguration, or the Lync Server Control Panel to define the corresponding trunk configurations.</span></span> <span data-ttu-id="04023-114">트렁크 구성에 대 한 Location-Based 라우팅을 사용 하도록 설정 하는 방법에 대 한 자세한 내용은 [Lync Server 2013에서 Location-Based 라우팅을 사용 하도록 설정](lync-server-2013-enabling-location-based-routing.md)Location-Based 섹션에서 트렁크로의 라우팅을 사용 하도록 설정 하는 방법을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="04023-114">More information on how to enable Location-Based Routing on trunk configurations can be found in the section, Enable Location-Based Routing to Trunks, in the topic, [Enabling Location-Based Routing in Lync Server 2013](lync-server-2013-enabling-location-based-routing.md).</span></span> <span data-ttu-id="04023-115">이 예제의 경우 다음 표에서는이 시나리오에 사용 되는 트렁크을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="04023-115">For this example, the following table illustrates the trunks used in this scenario.</span></span>

<span data-ttu-id="04023-116">자세한 내용은 [Define 추가 트렁크 in a Topology Builder In Lync Server 2013](lync-server-2013-define-additional-trunks-in-topology-builder.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="04023-116">For more information, see [Define additional trunks in Topology Builder in Lync Server 2013](lync-server-2013-define-additional-trunks-in-topology-builder.md).</span></span>


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
<th><span data-ttu-id="04023-117">트렁크 이름</span><span class="sxs-lookup"><span data-stu-id="04023-117">Trunk name</span></span></th>
<th><span data-ttu-id="04023-118">System type</span><span class="sxs-lookup"><span data-stu-id="04023-118">System type</span></span></th>
<th><span data-ttu-id="04023-119">이름</span><span class="sxs-lookup"><span data-stu-id="04023-119">Name</span></span></th>
<th><span data-ttu-id="04023-120">위치</span><span class="sxs-lookup"><span data-stu-id="04023-120">Location</span></span></th>
<th><span data-ttu-id="04023-121">중재 서버</span><span class="sxs-lookup"><span data-stu-id="04023-121">Mediation Server</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="04023-122">트렁크 1 DEL-GW</span><span class="sxs-lookup"><span data-stu-id="04023-122">Trunk 1 DEL-GW</span></span></p></td>
<td><p><span data-ttu-id="04023-123">PSTN 게이트웨이</span><span class="sxs-lookup"><span data-stu-id="04023-123">PSTN gateway</span></span></p></td>
<td><p><span data-ttu-id="04023-124">DEL-GW</span><span class="sxs-lookup"><span data-stu-id="04023-124">DEL-GW</span></span></p></td>
<td><p><span data-ttu-id="04023-125">Delhi</span><span class="sxs-lookup"><span data-stu-id="04023-125">Delhi</span></span></p></td>
<td><p><span data-ttu-id="04023-126">MS1</span><span class="sxs-lookup"><span data-stu-id="04023-126">MS1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="04023-127">트렁크 2 HYD-GW</span><span class="sxs-lookup"><span data-stu-id="04023-127">Trunk 2 HYD-GW</span></span></p></td>
<td><p><span data-ttu-id="04023-128">PSTN 게이트웨이</span><span class="sxs-lookup"><span data-stu-id="04023-128">PSTN gateway</span></span></p></td>
<td><p><span data-ttu-id="04023-129">HYD-GW</span><span class="sxs-lookup"><span data-stu-id="04023-129">HYD-GW</span></span></p></td>
<td><p><span data-ttu-id="04023-130">Hyderabad</span><span class="sxs-lookup"><span data-stu-id="04023-130">Hyderabad</span></span></p></td>
<td><p><span data-ttu-id="04023-131">MS1</span><span class="sxs-lookup"><span data-stu-id="04023-131">MS1</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="04023-132">트렁크 3 DEL-PBX</span><span class="sxs-lookup"><span data-stu-id="04023-132">Trunk 3 DEL-PBX</span></span></p></td>
<td><p><span data-ttu-id="04023-133">전화가</span><span class="sxs-lookup"><span data-stu-id="04023-133">PBX</span></span></p></td>
<td><p><span data-ttu-id="04023-134">DEL-PBX</span><span class="sxs-lookup"><span data-stu-id="04023-134">DEL-PBX</span></span></p></td>
<td><p><span data-ttu-id="04023-135">Delhi</span><span class="sxs-lookup"><span data-stu-id="04023-135">Delhi</span></span></p></td>
<td><p><span data-ttu-id="04023-136">MS1</span><span class="sxs-lookup"><span data-stu-id="04023-136">MS1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="04023-137">트렁크 4 HYD</span><span class="sxs-lookup"><span data-stu-id="04023-137">Trunk 4 HYD-PBX</span></span></p></td>
<td><p><span data-ttu-id="04023-138">전화가</span><span class="sxs-lookup"><span data-stu-id="04023-138">PBX</span></span></p></td>
<td><p><span data-ttu-id="04023-139">HYD</span><span class="sxs-lookup"><span data-stu-id="04023-139">HYD-PBX</span></span></p></td>
<td><p><span data-ttu-id="04023-140">Hyderabad</span><span class="sxs-lookup"><span data-stu-id="04023-140">Hyderabad</span></span></p></td>
<td><p><span data-ttu-id="04023-141">MS1</span><span class="sxs-lookup"><span data-stu-id="04023-141">MS1</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="defines-voice-policies"></a><span data-ttu-id="04023-142">음성 정책 정의</span><span class="sxs-lookup"><span data-stu-id="04023-142">Defines Voice Policies</span></span>

<span data-ttu-id="04023-143">Enterprise Voice 배포에 대 한 음성 정책을 정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="04023-143">You must define voice policies for your Enterprise Voice deployment.</span></span> <span data-ttu-id="04023-144">Location-Based 라우팅을 사용 하는 데 필요한 하위 집합만 있는 경우 사용자 하위 집합에 대 한 라우팅 제한 사항을 Location-Based 적용 하는 음성 정책을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="04023-144">Define a Voice Policy to enforce Location-Based Routing restrictions to a subset of users if only a subset of them is required to use Location-Based Routing.</span></span> <span data-ttu-id="04023-145">이 예제에서 다음 표에는이 시나리오에서 사용 되는 음성 정책이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04023-145">For this example, the following table illustrates the voice policies used in this scenario.</span></span> <span data-ttu-id="04023-146">Location-Based 라우팅과 관련 된 설정만 설명을 위해 표에 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04023-146">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

<span data-ttu-id="04023-147">자세한 내용은 [Lync Server 2013의 통화 기능 및 권한을 부여 하도록 음성 정책 및 PSTN 사용 레코드 구성을](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="04023-147">For more information, see [Configuring voice policies and PSTN usage records to authorize calling features and privileges in Lync Server 2013](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md).</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="04023-148">음성 정책 1</span><span class="sxs-lookup"><span data-stu-id="04023-148">Voice policy 1</span></span></th>
<th><span data-ttu-id="04023-149">음성 정책 2</span><span class="sxs-lookup"><span data-stu-id="04023-149">Voice policy 2</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="04023-150">음성 정책 ID</span><span class="sxs-lookup"><span data-stu-id="04023-150">Voice policy ID</span></span></p></td>
<td><p><span data-ttu-id="04023-151">뉴델리 voice 정책</span><span class="sxs-lookup"><span data-stu-id="04023-151">Delhi voice policy</span></span></p></td>
<td><p><span data-ttu-id="04023-152">Hyderabad 음성 정책</span><span class="sxs-lookup"><span data-stu-id="04023-152">Hyderabad voice policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="04023-153">PSTN 사용</span><span class="sxs-lookup"><span data-stu-id="04023-153">PSTN usages</span></span></p></td>
<td><p><span data-ttu-id="04023-154">뉴델리 usage, PBX Del usage, PBX Hyd usage</span><span class="sxs-lookup"><span data-stu-id="04023-154">Delhi usage, PBX Del usage, PBX Hyd usage</span></span></p></td>
<td><p><span data-ttu-id="04023-155">Hyderabad 사용 현황, PBX Hyd usage, PBX Del usage</span><span class="sxs-lookup"><span data-stu-id="04023-155">Hyderabad usage, PBX Hyd usage, PBX Del usage</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="04023-156">PreventPSTNTollBypass</span><span class="sxs-lookup"><span data-stu-id="04023-156">PreventPSTNTollBypass</span></span></p></td>
<td><p><span data-ttu-id="04023-157">False</span><span class="sxs-lookup"><span data-stu-id="04023-157">False</span></span></p></td>
<td><p><span data-ttu-id="04023-158">False</span><span class="sxs-lookup"><span data-stu-id="04023-158">False</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="define-voice-routes"></a><span data-ttu-id="04023-159">음성 경로 정의</span><span class="sxs-lookup"><span data-stu-id="04023-159">Define Voice Routes</span></span>

<span data-ttu-id="04023-160">Enterprise Voice 배포용 음성 경로를 정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="04023-160">You must define voice routes for your Enterprise Voice deployment.</span></span> <span data-ttu-id="04023-161">이 예에서는 다음 표에서는이 시나리오에서 사용 되는 음성 경로를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="04023-161">For this example, the following table illustrates the voice routes used in this scenario.</span></span> <span data-ttu-id="04023-162">Location-Based 라우팅과 관련 된 설정만 설명을 위해 표에 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04023-162">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

<span data-ttu-id="04023-163">자세한 내용은 [Lync Server 2013에서 아웃 바운드 통화에 대 한 음성 경로 구성을](lync-server-2013-configuring-voice-routes-for-outbound-calls.md)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="04023-163">For more information, see [Configuring voice routes for outbound calls in Lync Server 2013](lync-server-2013-configuring-voice-routes-for-outbound-calls.md).</span></span>


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
<th></th>
<th><span data-ttu-id="04023-164">음성 경로 1</span><span class="sxs-lookup"><span data-stu-id="04023-164">Voice route 1</span></span></th>
<th><span data-ttu-id="04023-165">음성 경로 2</span><span class="sxs-lookup"><span data-stu-id="04023-165">Voice route 2</span></span></th>
<th><span data-ttu-id="04023-166">음성 경로 3</span><span class="sxs-lookup"><span data-stu-id="04023-166">Voice route 3</span></span></th>
<th><span data-ttu-id="04023-167">음성 경로 4</span><span class="sxs-lookup"><span data-stu-id="04023-167">Voice route 4</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="04023-168">이름</span><span class="sxs-lookup"><span data-stu-id="04023-168">Name</span></span></p></td>
<td><p><span data-ttu-id="04023-169">뉴델리 경로</span><span class="sxs-lookup"><span data-stu-id="04023-169">Delhi route</span></span></p></td>
<td><p><span data-ttu-id="04023-170">Hyderabad 경로</span><span class="sxs-lookup"><span data-stu-id="04023-170">Hyderabad route</span></span></p></td>
<td><p><span data-ttu-id="04023-171">PBX Del 경로</span><span class="sxs-lookup"><span data-stu-id="04023-171">PBX Del route</span></span></p></td>
<td><p><span data-ttu-id="04023-172">PBX Hyd 경로</span><span class="sxs-lookup"><span data-stu-id="04023-172">PBX Hyd route</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="04023-173">PSTN 사용</span><span class="sxs-lookup"><span data-stu-id="04023-173">PSTN usages</span></span></p></td>
<td><p><span data-ttu-id="04023-174">뉴델리 사용</span><span class="sxs-lookup"><span data-stu-id="04023-174">Delhi usage</span></span></p></td>
<td><p><span data-ttu-id="04023-175">Hyderabad 사용 현황</span><span class="sxs-lookup"><span data-stu-id="04023-175">Hyderabad usage</span></span></p></td>
<td><p><span data-ttu-id="04023-176">PBX Del 사용 현황</span><span class="sxs-lookup"><span data-stu-id="04023-176">PBX Del usage</span></span></p></td>
<td><p><span data-ttu-id="04023-177">PBX Hyd 사용 현황</span><span class="sxs-lookup"><span data-stu-id="04023-177">PBX Hyd usage</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="04023-178">트렁크</span><span class="sxs-lookup"><span data-stu-id="04023-178">Trunk</span></span></p></td>
<td><p><span data-ttu-id="04023-179">트렁크 1 DEL-GW</span><span class="sxs-lookup"><span data-stu-id="04023-179">Trunk 1 DEL-GW</span></span></p></td>
<td><p><span data-ttu-id="04023-180">트렁크 2 HYD-GW</span><span class="sxs-lookup"><span data-stu-id="04023-180">Trunk 2 HYD-GW</span></span></p></td>
<td><p><span data-ttu-id="04023-181">트렁크 3 DEL-PBX</span><span class="sxs-lookup"><span data-stu-id="04023-181">Trunk 3 DEL-PBX</span></span></p></td>
<td><p><span data-ttu-id="04023-182">트렁크 4 HYD</span><span class="sxs-lookup"><span data-stu-id="04023-182">Trunk 4 HYD-PBX</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="enable-users-for-enterprise-voice"></a><span data-ttu-id="04023-183">사용자가 Enterprise Voice를 사용할 수 있도록 설정</span><span class="sxs-lookup"><span data-stu-id="04023-183">Enable Users for Enterprise Voice</span></span>

<span data-ttu-id="04023-184">사용자가 Enterprise Voice를 사용할 수 있도록 설정 하 고 이전에 정의한 음성 정책에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="04023-184">Enable users for Enterprise Voice and assign them a voice policy you’ve previously defined.</span></span> <span data-ttu-id="04023-185">이 예제의 경우 다음 표에서는이 시나리오에서 사용 되는 배정을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="04023-185">For this example, the following table illustrates the assignment used in this scenario.</span></span> <span data-ttu-id="04023-186">Location-Based 라우팅과 관련 된 설정만 설명을 위해 표에 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04023-186">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

<span data-ttu-id="04023-187">자세한 내용은 [Lync Server 2013에서 사용자에 게 Enterprise Voice 사용을 설정](lync-server-2013-enable-users-for-enterprise-voice.md)합니다 .를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="04023-187">For more information, see [Enable users for Enterprise Voice in Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md).</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="04023-188">뉴델리에 있는 사용자</span><span class="sxs-lookup"><span data-stu-id="04023-188">Users located in Delhi</span></span></th>
<th><span data-ttu-id="04023-189">Hyderabad에 있는 사용자</span><span class="sxs-lookup"><span data-stu-id="04023-189">Users located in Hyderabad</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="04023-190">연결 된 음성 정책</span><span class="sxs-lookup"><span data-stu-id="04023-190">Associated voice policy</span></span></p></td>
<td><p><span data-ttu-id="04023-191">뉴델리 voice 정책</span><span class="sxs-lookup"><span data-stu-id="04023-191">Delhi voice policy</span></span></p></td>
<td><p><span data-ttu-id="04023-192">Hyderabad 음성 정책</span><span class="sxs-lookup"><span data-stu-id="04023-192">Hyderabad voice policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="04023-193">샘플 사용자</span><span class="sxs-lookup"><span data-stu-id="04023-193">Sample users</span></span></p></td>
<td><p><span data-ttu-id="04023-194">DEL-LYNC-1, DEL-LYNC-2, DEL-LYNC-3</span><span class="sxs-lookup"><span data-stu-id="04023-194">DEL-LYNC-1,DEL-LYNC-2,DEL-LYNC-3</span></span></p></td>
<td><p><span data-ttu-id="04023-195">HYD-1, HYD-2, HYD-3</span><span class="sxs-lookup"><span data-stu-id="04023-195">HYD-LYNC-1, HYD-LYNC-2, HYD-LYNC-3</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="04023-196">참고 항목</span><span class="sxs-lookup"><span data-stu-id="04023-196">See Also</span></span>


[<span data-ttu-id="04023-197">Lync Server 2013에서 Location-Based 라우팅 구성</span><span class="sxs-lookup"><span data-stu-id="04023-197">Configuring Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-configuring-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

