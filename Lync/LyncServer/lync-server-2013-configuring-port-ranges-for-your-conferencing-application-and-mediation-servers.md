---
title: 'Lync Server 2013: 회의, 응용 프로그램 및 중재 서버에 대 한 포트 범위 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring port ranges for your Conferencing, Application, and Mediation servers
ms:assetid: 4d6eaa5d-0127-453f-be6a-e55384772d83
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204872(v=OCS.15)
ms:contentKeyID: 48184074
ms.date: 05/01/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ecd505990b9a060c3b669700ea9192dc1ad6b84c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42033747"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-port-ranges-in-lync-server-2013-for-your-conferencing-application-and-mediation-servers"></a><span data-ttu-id="7c0f5-102">Lync Server 2013에서 회의, 응용 프로그램 및 중재 서버에 대 한 포트 범위 구성</span><span class="sxs-lookup"><span data-stu-id="7c0f5-102">Configuring port ranges in Lync Server 2013 for your Conferencing, Application, and Mediation servers</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7c0f5-103">_**마지막으로 수정 된 항목:** 2015-04-30_</span><span class="sxs-lookup"><span data-stu-id="7c0f5-103">_**Topic Last Modified:** 2015-04-30_</span></span>

<span data-ttu-id="7c0f5-p101">QoS(서비스 품질)를 구현하기 위해서는 회의, 응용 프로그램 및 중재 서버에서 오디오, 비디오 및 응용 프로그램 공유에 대한 동일한 포트 범위를 구성해야 합니다. 또한 이러한 포트 범위는 어떠한 방식으로든 서로 겹쳐서는 안됩니다. 간단한 예로, 회의 서버에서 비디오를 위해 10000~10999 포트를 사용한다고 가정해보십시오. 이 경우에는 응용 프로그램 및 중재 서버에서도 10000~10999 포트를 비디오용으로 예약해야 합니다. 그렇지 않으면 QoS가 예상한 대로 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7c0f5-p101">In order to implement Quality of Service, you should configure identical port ranges for audio, video, and application sharing on your Conferencing, Application, and Mediation servers; furthermore, those port ranges must not overlap in any way. To use a simple example, suppose you use ports 10000 through 10999 for video on your Conferencing servers. That means that you must also reserve ports 10000 through 10999 for video on your Application and Mediation servers. If you do not, QoS will not work as expected.</span></span>

<span data-ttu-id="7c0f5-p102">이와 비슷하게, 10000~10999 포트를 비디오용으로 예약하지만 10500~11999 포트는 오디오용으로 예약한다고 가정해보십시오. 이 경우에는 포트 범위가 겹치기 때문에 QoS(서비스 품질) 문제가 발생할 수 있습니다. QoS에서는 각 형식이 고유한 포트 집합을 가져야 합니다. 10000~10999 포트를 비디오용으로 사용한다면 다른 범위를 사용해야 합니다(예: 오디오에 11000~11999 사용).</span><span class="sxs-lookup"><span data-stu-id="7c0f5-p102">Similarly, suppose you reserve ports 10000 through 10999 for video, but then reserve ports 10500 through 11999 for audio. This can create problems for Quality of Service, because the port ranges overlap. With QoS, each modality must have a unique set of ports: if you use ports 10000 through 10999 for video, then you'll have to use a different range (for example, 11000 through 11999 for audio).</span></span>

<span data-ttu-id="7c0f5-111">기본적으로 오디오 및 비디오 포트 범위는 Microsoft Lync Server 2013에서 중복 되지 않습니다. 그러나 응용 프로그램 공유에 할당 된 포트 범위가 오디오 및 비디오 포트 범위와 겹칩니다.</span><span class="sxs-lookup"><span data-stu-id="7c0f5-111">By default, audio and video port ranges do not overlap in Microsoft Lync Server 2013; however, the port ranges assigned to application sharing overlap with both the audio and video port ranges.</span></span> <span data-ttu-id="7c0f5-112">(즉, 이러한 범위는 고유 하지 않을 수 있습니다.) Lync Server 2013 관리 셸에서 다음 세 명령을 실행 하 여 회의, 응용 프로그램 및 중재 서버에 대 한 기존 포트 범위를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c0f5-112">(Which, in turn, means that none of these ranges are unique.) You can verify the existing port ranges for your Conferencing, Application, and Mediation servers by running the following three commands from within the Lync Server 2013 Management Shell:</span></span>

    Get-CsService -ConferencingServer | Select-Object Identity, AudioPortStart, AudioPortCount, VideoPortStart, VideoPortCount, AppSharingPortStart, AppSharingPortCount
    
    Get-CsService -ApplicationServer | Select-Object Identity, AudioPortStart, AudioPortCount
    
    Get-CsService -MediationServer | Select-Object Identity, AudioPortStart, AudioPortCount

<div>


> [!WARNING]  
> <span data-ttu-id="7c0f5-p104">앞의 명령에서 볼 수 있듯이, 각 포트 유형(오디오, 비디오 및 응용 프로그램 공유)에는 두 개의 개별 속성 값인 포트 시작 및 포트 개수 값이 지정됩니다. 포트 시작은 해당 형식에 사용되는 첫 번째 포트를 나타냅니다. 예를 들어 오디오 포트 시작이 50000이면 오디오 트래픽에 사용되는 첫 번째 포트가 포트 50000입니다. 오디오 포트 개수가 2(올바른 값은 아니지만 설명을 위해 사용됨)이면 오디오에 2개의 포트만 지정됩니다. 첫 번째 포트가 포트 50000이고 총 2개의 포트만 있으므로 두 번째 포트는 포트 50001이어야 합니다(포트 범위는 연속되어야 함). 따라서 오디오에 대한 포트 범위는 50000~50001까지입니다.</span><span class="sxs-lookup"><span data-stu-id="7c0f5-p104">As you can see in the preceding commands, each port type – audio, video, and application sharing – is assigned two separate property values: the port start and the port count. The port start indicates the first port used for that modality; for example, if the audio port start is equal to 50000 that means that the first port used for audio traffic is port 50000. If the audio port count is 2 (which is not a valid value, but is used here for illustration purposes) that means that only 2 ports are allocated for audio. If the first port is port 50000 and there are a total of two ports, that means the second port must be port 50001 (port ranges have to be contiguous). As a result, the port range for audio would be ports 50000 through 50001, inclusive.</span></span><BR><span data-ttu-id="7c0f5-118">응용 프로그램 서버 및 중재 서버는 오디오에 대해서만 QoS를 지원합니다. 응용 프로그램 서버 또는 중재 서버에서는 비디오 또는 응용 프로그램 공유 포트를 변경할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7c0f5-118">Note, too that Application server and Mediation server only support QoS for audio; you do not need to change video or application sharing ports in your Application servers or Mediation servers.</span></span>



</div>

<span data-ttu-id="7c0f5-119">앞의 세 명령을 실행 하면 Lync Server 2013의 기본 포트 값이 다음과 같이 구성 된 것을 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c0f5-119">If you run the preceding three commands you'll see that the default port values for Lync Server 2013 are configured like this:</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7c0f5-120">속성</span><span class="sxs-lookup"><span data-stu-id="7c0f5-120">Property</span></span></th>
<th><span data-ttu-id="7c0f5-121">회의 서버</span><span class="sxs-lookup"><span data-stu-id="7c0f5-121">Conferencing Server</span></span></th>
<th><span data-ttu-id="7c0f5-122">응용 프로그램 서버</span><span class="sxs-lookup"><span data-stu-id="7c0f5-122">Application Server</span></span></th>
<th><span data-ttu-id="7c0f5-123">중재 서버</span><span class="sxs-lookup"><span data-stu-id="7c0f5-123">Mediation Server</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7c0f5-124">AudioPortStart</span><span class="sxs-lookup"><span data-stu-id="7c0f5-124">AudioPortStart</span></span></p></td>
<td><p><span data-ttu-id="7c0f5-125">49152</span><span class="sxs-lookup"><span data-stu-id="7c0f5-125">49152</span></span></p></td>
<td><p><span data-ttu-id="7c0f5-126">49152</span><span class="sxs-lookup"><span data-stu-id="7c0f5-126">49152</span></span></p></td>
<td><p><span data-ttu-id="7c0f5-127">49152</span><span class="sxs-lookup"><span data-stu-id="7c0f5-127">49152</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7c0f5-128">AudioPortCount</span><span class="sxs-lookup"><span data-stu-id="7c0f5-128">AudioPortCount</span></span></p></td>
<td><p><span data-ttu-id="7c0f5-129">8348</span><span class="sxs-lookup"><span data-stu-id="7c0f5-129">8348</span></span></p></td>
<td><p><span data-ttu-id="7c0f5-130">8348</span><span class="sxs-lookup"><span data-stu-id="7c0f5-130">8348</span></span></p></td>
<td><p><span data-ttu-id="7c0f5-131">8348</span><span class="sxs-lookup"><span data-stu-id="7c0f5-131">8348</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7c0f5-132">VideoPortStart</span><span class="sxs-lookup"><span data-stu-id="7c0f5-132">VideoPortStart</span></span></p></td>
<td><p><span data-ttu-id="7c0f5-133">57501</span><span class="sxs-lookup"><span data-stu-id="7c0f5-133">57501</span></span></p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7c0f5-134">VideoPortCount</span><span class="sxs-lookup"><span data-stu-id="7c0f5-134">VideoPortCount</span></span></p></td>
<td><p><span data-ttu-id="7c0f5-135">8034</span><span class="sxs-lookup"><span data-stu-id="7c0f5-135">8034</span></span></p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7c0f5-136">ApplicationSharingPortStart</span><span class="sxs-lookup"><span data-stu-id="7c0f5-136">ApplicationSharingPortStart</span></span></p></td>
<td><p><span data-ttu-id="7c0f5-137">49152</span><span class="sxs-lookup"><span data-stu-id="7c0f5-137">49152</span></span></p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7c0f5-138">ApplicationSharingPortCount</span><span class="sxs-lookup"><span data-stu-id="7c0f5-138">ApplicationSharingPortCount</span></span></p></td>
<td><p><span data-ttu-id="7c0f5-139">16383</span><span class="sxs-lookup"><span data-stu-id="7c0f5-139">16383</span></span></p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="7c0f5-140">앞에서 설명한 대로 QoS 용 Lync Server 포트를 구성 하는 경우, 1) 사용자의 회의, 응용 프로그램 및 중재 서버에서 오디오 포트 설정이 동일 해야 합니다. 2) 포트 범위가 겹치지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7c0f5-140">As noted previously, when configuring Lync Server ports for QoS, you should ensure that: 1) audio port settings are identical across yours Conferencing, Application, and Mediation servers; and, 2) port ranges do not overlap.</span></span> <span data-ttu-id="7c0f5-141">위의 표를 자세히 살펴보면 3 개의 서버 유형에 대해 포트 범위가 동일 하다는 것을 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c0f5-141">If you look closely at the preceding table, you will see that the port ranges are identical across the three server types.</span></span> <span data-ttu-id="7c0f5-142">예를 들어 시작 오디오 포트는 각 서버 유형에 대해 포트 49152로 설정 되 고 각 서버의 오디오에 대해 예약 된 총 포트 수는 8348 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c0f5-142">For example, the starting audio port is set to port 49152 on each server type, and the total number of ports reserved for audio in each server is also identical: 8348.</span></span> <span data-ttu-id="7c0f5-143">그러나 포트 범위가 겹치면 오디오 포트는 포트 49152에서 시작 되지만 응용 프로그램을 공유 하기 위해 포트를 별도로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c0f5-143">However, the port ranges overlap: audio ports start at port 49152, but so do the ports set aside for application sharing.</span></span> <span data-ttu-id="7c0f5-144">서비스 품질을 최적의 상태로 사용 하기 위해서는 응용 프로그램 공유를 고유한 포트 범위를 사용 하도록 다시 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c0f5-144">In order to make optimal use of Quality of Service, application sharing should be reconfigured to use a unique port range.</span></span> <span data-ttu-id="7c0f5-145">예를 들어 포트 40803에서 시작 하 고 8348 포트를 사용 하도록 응용 프로그램 공유를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c0f5-145">For example, you could configure application sharing to start at port 40803 and to use 8348 ports.</span></span> <span data-ttu-id="7c0f5-146">(8348 포트가 있습니까?</span><span class="sxs-lookup"><span data-stu-id="7c0f5-146">(Why 8348 ports?</span></span> <span data-ttu-id="7c0f5-147">이러한 값을 함께 추가 하는 경우--40803 + 8348----이를 통해 응용 프로그램 공유는 포트 49150을 통해 포트 40803을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c0f5-147">If you add those values together -- 40803 + 8348 -- that means that application sharing will use ports 40803 through port 49150.</span></span> <span data-ttu-id="7c0f5-148">오디오 포트는 포트 49152까지 시작 되지 않으므로 겹치는 포트 범위가 더 이상 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7c0f5-148">Because audio ports do not begin until port 49152, you will no longer have any overlapping port ranges.)</span></span>

<span data-ttu-id="7c0f5-p106">응용 프로그램 공유에 대해 새 포트 범위를 선택한 후에는 Set-CsConferencingServer cmdlet을 사용하여 항목을 변경할 수 있습니다. 이러한 서버에서 응용 프로그램 공유 트래픽이 처리되지 않기 때문에 이러한 항목은 응용 프로그램 서버 또는 중재 서버에서 변경할 필요가 없습니다. 오디오 트래픽에 사용되는 포트를 다시 지정할 경우에만 해당 서버에서 포트 값을 변경해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c0f5-p106">After you have selected the new port range for application sharing you can make your change by using the Set-CsConferencingServer cmdlet. This change does not need to be made on your Application servers or on your Mediation servers, because these servers do not handle application sharing traffic. You only need to change port values on these servers if you decide to reassign the ports used for audio traffic.</span></span>

<span data-ttu-id="7c0f5-152">단일 회의 서버에서 응용 프로그램 공유에 대 한 포트 값을 수정 하려면 Lync Server 관리 셸에서와 비슷한 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c0f5-152">To modify the port values for application sharing on a single Conferencing server run a command similar to this from within the Lync Server Management Shell:</span></span>

    Set-CsConferenceServer -Identity ConferencingServer:atl-cs-001.litwareinc.com -AppSharingPortStart 40803 -AppSharingPortCount 8348

<span data-ttu-id="7c0f5-153">모든 회의 서버에서 이러한 항목을 변경하려는 경우 대신 다음 명령을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c0f5-153">If you want to make these changes on all your Conferencing servers you can run this command instead:</span></span>

    Get-CsService -ConferencingServer | ForEach-Object {Set-CsConferenceServer -Identity $_.Identity -AppSharingPortStart 40803 -AppSharingPortCount 8348}

<span data-ttu-id="7c0f5-154">포트 설정을 변경한 후에는 변경 내용의 영향을 받는 각 서비스를 중지하고 다시 시작해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c0f5-154">After changing port settings you should stop and then restart each service affected by the changes.</span></span>

<span data-ttu-id="7c0f5-p107">회의 서버, 응용 프로그램 서버 및 중재 서버가 정확히 동일한 포트 범위를 공유할 필요는 없으며, 모든 서버에서 고유한 포트 범위를 별도로 설정하기만 하면 됩니다. 하지만 관리 측면에서는 모든 서버에서 동일한 포트 집합을 사용하는 것이 더 쉬울 것입니다.</span><span class="sxs-lookup"><span data-stu-id="7c0f5-p107">It is not mandatory that your Conferencing servers, Application servers, and Mediation servers share the exact same port range; the only true requirement is that you set aside unique port ranges on all your servers. However, administration will typically be easier if you use the same set of ports on all your servers.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

