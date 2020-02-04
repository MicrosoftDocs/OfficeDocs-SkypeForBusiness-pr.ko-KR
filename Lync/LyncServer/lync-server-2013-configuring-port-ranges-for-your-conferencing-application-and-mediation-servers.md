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
ms.openlocfilehash: 54aab5efbca06d918cc2dbeccc0e36aee9d4abf8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756302"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-port-ranges-in-lync-server-2013-for-your-conferencing-application-and-mediation-servers"></a><span data-ttu-id="52c62-102">Lync Server 2013에서 회의, 응용 프로그램 및 중재 서버용 포트 범위 구성</span><span class="sxs-lookup"><span data-stu-id="52c62-102">Configuring port ranges in Lync Server 2013 for your Conferencing, Application, and Mediation servers</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="52c62-103">_**마지막으로 수정한 주제:** 2015-04-30_</span><span class="sxs-lookup"><span data-stu-id="52c62-103">_**Topic Last Modified:** 2015-04-30_</span></span>

<span data-ttu-id="52c62-104">서비스 품질을 구현 하려면, 회의, 응용 프로그램, 중재 서버에서 오디오, 비디오, 응용 프로그램 공유에 대해 동일한 포트 범위를 구성 해야 합니다. 또한 이러한 포트 범위는 어떤 방식으로든 중복 되지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="52c62-104">In order to implement Quality of Service, you should configure identical port ranges for audio, video, and application sharing on your Conferencing, Application, and Mediation servers; furthermore, those port ranges must not overlap in any way.</span></span> <span data-ttu-id="52c62-105">간단한 예제를 사용 하려면 회의 서버의 비디오에 대해 포트 1만 ~ 10999을 (를) 사용 한다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="52c62-105">To use a simple example, suppose you use ports 10000 through 10999 for video on your Conferencing servers.</span></span> <span data-ttu-id="52c62-106">즉, 응용 프로그램 및 중재 서버에서 비디오를 위해 1만 ~ 10999 포트를 예약 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="52c62-106">That means that you must also reserve ports 10000 through 10999 for video on your Application and Mediation servers.</span></span> <span data-ttu-id="52c62-107">그렇지 않으면 QoS가 예상 대로 작동 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="52c62-107">If you do not, QoS will not work as expected.</span></span>

<span data-ttu-id="52c62-108">마찬가지로 비디오용으로 포트 1만 ~ 10999을 예약 하 고 오디오에 대해 포트 10500 ~ 11999을 예약 한다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="52c62-108">Similarly, suppose you reserve ports 10000 through 10999 for video, but then reserve ports 10500 through 11999 for audio.</span></span> <span data-ttu-id="52c62-109">이렇게 하면 포트 범위가 겹치게 되므로 서비스 품질에 대 한 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="52c62-109">This can create problems for Quality of Service, because the port ranges overlap.</span></span> <span data-ttu-id="52c62-110">QoS를 사용 하는 경우 각 모달 포트는 고유한 포트 집합을 사용 해야 합니다. 비디오에 1만 ~ 10999을 사용할 경우 다른 범위를 사용 해야 합니다 (예를 들어 11000 ~ 11999 (오디오)).</span><span class="sxs-lookup"><span data-stu-id="52c62-110">With QoS, each modality must have a unique set of ports: if you use ports 10000 through 10999 for video, then you'll have to use a different range (for example, 11000 through 11999 for audio).</span></span>

<span data-ttu-id="52c62-111">기본적으로 Microsoft Lync Server 2013에서 오디오 및 비디오 포트 범위가 중복 되지 않습니다. 그러나 오디오 및 비디오 포트 범위와 응용 프로그램 공유에 할당 된 포트 범위가 겹칩니다.</span><span class="sxs-lookup"><span data-stu-id="52c62-111">By default, audio and video port ranges do not overlap in Microsoft Lync Server 2013; however, the port ranges assigned to application sharing overlap with both the audio and video port ranges.</span></span> <span data-ttu-id="52c62-112">즉, 이러한 범위 중 어느 것도 고유 하지 않음을 의미 합니다. Lync Server 2013 관리 셸에서 다음 세 개의 명령을 실행 하 여 회의, 응용 프로그램 및 중재 서버의 기존 포트 범위를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="52c62-112">(Which, in turn, means that none of these ranges are unique.) You can verify the existing port ranges for your Conferencing, Application, and Mediation servers by running the following three commands from within the Lync Server 2013 Management Shell:</span></span>

    Get-CsService -ConferencingServer | Select-Object Identity, AudioPortStart, AudioPortCount, VideoPortStart, VideoPortCount, AppSharingPortStart, AppSharingPortCount
    
    Get-CsService -ApplicationServer | Select-Object Identity, AudioPortStart, AudioPortCount
    
    Get-CsService -MediationServer | Select-Object Identity, AudioPortStart, AudioPortCount

<div>


> [!WARNING]  
> <span data-ttu-id="52c62-113">앞의 명령에서 볼 수 있듯이 각 포트 유형-오디오, 비디오 및 응용 프로그램 공유에는 두 가지 개별 속성 값인 포트 시작 및 포트 카운트가 할당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="52c62-113">As you can see in the preceding commands, each port type – audio, video, and application sharing – is assigned two separate property values: the port start and the port count.</span></span> <span data-ttu-id="52c62-114">포트 시작은 해당 모달에 사용 되는 첫 번째 포트를 나타냅니다. 예를 들어 오디오 포트 시작이 5만와 같으면 오디오 트래픽에 사용 되는 첫 번째 포트가 포트 5만입니다.</span><span class="sxs-lookup"><span data-stu-id="52c62-114">The port start indicates the first port used for that modality; for example, if the audio port start is equal to 50000 that means that the first port used for audio traffic is port 50000.</span></span> <span data-ttu-id="52c62-115">오디오 포트 카운트가 2 (유효한 값이 아니지만 여기에서 설명 하는 데 사용 됨) 인 경우 오디오에 대해 2 개의 포트만 할당 한다는 의미입니다.</span><span class="sxs-lookup"><span data-stu-id="52c62-115">If the audio port count is 2 (which is not a valid value, but is used here for illustration purposes) that means that only 2 ports are allocated for audio.</span></span> <span data-ttu-id="52c62-116">첫 번째 포트가 포트 5만이 고 총 두 개의 포트가 있는 경우 두 번째 포트는 포트 50001 (포트 범위는 연속적 이어야 함) 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="52c62-116">If the first port is port 50000 and there are a total of two ports, that means the second port must be port 50001 (port ranges have to be contiguous).</span></span> <span data-ttu-id="52c62-117">결과적으로 오디오의 포트 범위는 포트 5만 ~ 50001 (포함)입니다.</span><span class="sxs-lookup"><span data-stu-id="52c62-117">As a result, the port range for audio would be ports 50000 through 50001, inclusive.</span></span><BR><span data-ttu-id="52c62-118">단, 응용 프로그램 서버와 중재 서버는 오디오에 대 한 QoS만 지원 합니다. 응용 프로그램 서버나 중재 서버에서 비디오 또는 응용 프로그램 공유 포트를 변경할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="52c62-118">Note, too that Application server and Mediation server only support QoS for audio; you do not need to change video or application sharing ports in your Application servers or Mediation servers.</span></span>



</div>

<span data-ttu-id="52c62-119">앞의 세 명령을 실행 하는 경우 Lync Server 2013의 기본 포트 값이 다음과 같이 구성 되어 있는 것을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="52c62-119">If you run the preceding three commands you'll see that the default port values for Lync Server 2013 are configured like this:</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="52c62-120">속성</span><span class="sxs-lookup"><span data-stu-id="52c62-120">Property</span></span></th>
<th><span data-ttu-id="52c62-121">회의 서버</span><span class="sxs-lookup"><span data-stu-id="52c62-121">Conferencing Server</span></span></th>
<th><span data-ttu-id="52c62-122">응용 프로그램 서버</span><span class="sxs-lookup"><span data-stu-id="52c62-122">Application Server</span></span></th>
<th><span data-ttu-id="52c62-123">중재 서버</span><span class="sxs-lookup"><span data-stu-id="52c62-123">Mediation Server</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="52c62-124">AudioPortStart</span><span class="sxs-lookup"><span data-stu-id="52c62-124">AudioPortStart</span></span></p></td>
<td><p><span data-ttu-id="52c62-125">49152</span><span class="sxs-lookup"><span data-stu-id="52c62-125">49152</span></span></p></td>
<td><p><span data-ttu-id="52c62-126">49152</span><span class="sxs-lookup"><span data-stu-id="52c62-126">49152</span></span></p></td>
<td><p><span data-ttu-id="52c62-127">49152</span><span class="sxs-lookup"><span data-stu-id="52c62-127">49152</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52c62-128">AudioPortCount</span><span class="sxs-lookup"><span data-stu-id="52c62-128">AudioPortCount</span></span></p></td>
<td><p><span data-ttu-id="52c62-129">8348</span><span class="sxs-lookup"><span data-stu-id="52c62-129">8348</span></span></p></td>
<td><p><span data-ttu-id="52c62-130">8348</span><span class="sxs-lookup"><span data-stu-id="52c62-130">8348</span></span></p></td>
<td><p><span data-ttu-id="52c62-131">8348</span><span class="sxs-lookup"><span data-stu-id="52c62-131">8348</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52c62-132">VideoPortStart</span><span class="sxs-lookup"><span data-stu-id="52c62-132">VideoPortStart</span></span></p></td>
<td><p><span data-ttu-id="52c62-133">57501</span><span class="sxs-lookup"><span data-stu-id="52c62-133">57501</span></span></p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52c62-134">VideoPortCount</span><span class="sxs-lookup"><span data-stu-id="52c62-134">VideoPortCount</span></span></p></td>
<td><p><span data-ttu-id="52c62-135">8034</span><span class="sxs-lookup"><span data-stu-id="52c62-135">8034</span></span></p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52c62-136">ApplicationSharingPortStart</span><span class="sxs-lookup"><span data-stu-id="52c62-136">ApplicationSharingPortStart</span></span></p></td>
<td><p><span data-ttu-id="52c62-137">49152</span><span class="sxs-lookup"><span data-stu-id="52c62-137">49152</span></span></p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52c62-138">ApplicationSharingPortCount</span><span class="sxs-lookup"><span data-stu-id="52c62-138">ApplicationSharingPortCount</span></span></p></td>
<td><p><span data-ttu-id="52c62-139">16383</span><span class="sxs-lookup"><span data-stu-id="52c62-139">16383</span></span></p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="52c62-140">앞에서 설명한 대로 QoS 용 Lync Server 포트를 구성 하는 경우 다음을 수행 해야 합니다. 1) 오디오 포트 설정이 내 회의, 응용 프로그램, 중재 서버에서 동일 하 게 유지 됩니다. and, 2) 포트 범위가 중복 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="52c62-140">As noted previously, when configuring Lync Server ports for QoS, you should ensure that: 1) audio port settings are identical across yours Conferencing, Application, and Mediation servers; and, 2) port ranges do not overlap.</span></span> <span data-ttu-id="52c62-141">앞의 표에서 자세히 보면 포트 범위가 세 가지 서버 유형 모두와 동일 하다는 것을 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="52c62-141">If you look closely at the preceding table, you will see that the port ranges are identical across the three server types.</span></span> <span data-ttu-id="52c62-142">예를 들어 시작 오디오 포트는 각 서버 유형에 서 포트 49152로 설정 되 고 각 서버에서 오디오에 대해 예약 된 총 포트 수는 동일 합니다 (8348).</span><span class="sxs-lookup"><span data-stu-id="52c62-142">For example, the starting audio port is set to port 49152 on each server type, and the total number of ports reserved for audio in each server is also identical: 8348.</span></span> <span data-ttu-id="52c62-143">그러나 포트 범위가 겹치지만 오디오 포트는 포트 49152에서 시작 하지만, 포트는 응용 프로그램 공유에 대해 별도로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="52c62-143">However, the port ranges overlap: audio ports start at port 49152, but so do the ports set aside for application sharing.</span></span> <span data-ttu-id="52c62-144">서비스 품질을 최적화 하기 위해 고유한 포트 범위를 사용 하도록 응용 프로그램 공유를 다시 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="52c62-144">In order to make optimal use of Quality of Service, application sharing should be reconfigured to use a unique port range.</span></span> <span data-ttu-id="52c62-145">예를 들어 포트 40803에서 시작 하 고 8348 포트를 사용 하도록 응용 프로그램 공유를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="52c62-145">For example, you could configure application sharing to start at port 40803 and to use 8348 ports.</span></span> <span data-ttu-id="52c62-146">(8348 포트가 있는 이유는 무엇 인가요?</span><span class="sxs-lookup"><span data-stu-id="52c62-146">(Why 8348 ports?</span></span> <span data-ttu-id="52c62-147">이러한 값을 함께 추가 하는 경우--40803 + 8348--이는 응용 프로그램 공유가 포트 49150를 통해 포트 40803를 사용 하는 것을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="52c62-147">If you add those values together -- 40803 + 8348 -- that means that application sharing will use ports 40803 through port 49150.</span></span> <span data-ttu-id="52c62-148">오디오 포트는 포트 49152까지 시작 되지 않으므로 겹치는 포트 범위가 더 이상 없습니다.</span><span class="sxs-lookup"><span data-stu-id="52c62-148">Because audio ports do not begin until port 49152, you will no longer have any overlapping port ranges.)</span></span>

<span data-ttu-id="52c62-149">응용 프로그램 공유에 대 한 새 포트 범위를 선택한 후에는 CsConferencingServer cmdlet을 사용 하 여 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="52c62-149">After you have selected the new port range for application sharing you can make your change by using the Set-CsConferencingServer cmdlet.</span></span> <span data-ttu-id="52c62-150">이러한 서버는 응용 프로그램 서버나 중재 서버에서는 이러한 변경 작업을 수행할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="52c62-150">This change does not need to be made on your Application servers or on your Mediation servers, because these servers do not handle application sharing traffic.</span></span> <span data-ttu-id="52c62-151">오디오 트래픽에 사용 되는 포트를 다시 할당 하기로 결정 한 경우에만 이러한 서버에서 포트 값을 변경 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="52c62-151">You only need to change port values on these servers if you decide to reassign the ports used for audio traffic.</span></span>

<span data-ttu-id="52c62-152">단일 회의 서버에서 응용 프로그램 공유에 대 한 포트 값을 수정 하려면 Lync Server 관리 셸에서 다음과 같은 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="52c62-152">To modify the port values for application sharing on a single Conferencing server run a command similar to this from within the Lync Server Management Shell:</span></span>

    Set-CsConferenceServer -Identity ConferencingServer:atl-cs-001.litwareinc.com -AppSharingPortStart 40803 -AppSharingPortCount 8348

<span data-ttu-id="52c62-153">모든 회의 서버에서 이러한 변경 작업을 수행 하려면이 명령을 대신 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="52c62-153">If you want to make these changes on all your Conferencing servers you can run this command instead:</span></span>

    Get-CsService -ConferencingServer | ForEach-Object {Set-CsConferenceServer -Identity $_.Identity -AppSharingPortStart 40803 -AppSharingPortCount 8348}

<span data-ttu-id="52c62-154">포트 설정을 변경한 후 변경 내용에 따라 영향을 받는 각 서비스를 중지 한 다음 다시 시작 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="52c62-154">After changing port settings you should stop and then restart each service affected by the changes.</span></span>

<span data-ttu-id="52c62-155">사용자의 회의 서버, 응용 프로그램 서버, 중재 서버는 똑같은 포트 범위를 공유 하도록 필수가 아닙니다. 유일한 이유는 모든 서버에 고유한 포트 범위를 별도로 설정 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="52c62-155">It is not mandatory that your Conferencing servers, Application servers, and Mediation servers share the exact same port range; the only true requirement is that you set aside unique port ranges on all your servers.</span></span> <span data-ttu-id="52c62-156">그러나 모든 서버에서 동일한 포트 집합을 사용 하는 경우에는 일반적으로 관리 하기가 더 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="52c62-156">However, administration will typically be easier if you use the same set of ports on all your servers.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

