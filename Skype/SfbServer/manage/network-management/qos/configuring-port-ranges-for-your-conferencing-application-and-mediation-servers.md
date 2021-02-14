---
title: 회의, 응용 프로그램 및 중재 서버에 대한 포트 범위 및 서비스 품질 정책 구성
ms.reviewer: ''
ms:assetid: 4d6eaa5d-0127-453f-be6a-e55384772d83
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204872(v=OCS.15)
ms:contentKeyID: 48184074
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 이 문서에서는 회의, 응용 프로그램 및 중재 서버에 대해 포트 범위 및 서비스 품질 정책을 구성하는 방법에 대해 설명합니다.
ms.openlocfilehash: 8c65e36528615aca181b6aac17aab844c1a4d206
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49800128"
---
# <a name="configuring-port-ranges-and-a-quality-of-service-policy-for-your-conferencing-application-and-mediation-servers"></a><span data-ttu-id="52231-103">회의, 응용 프로그램 및 중재 서버에 대한 포트 범위 및 서비스 품질 정책 구성</span><span class="sxs-lookup"><span data-stu-id="52231-103">Configuring port ranges and a Quality of Service policy for your Conferencing, Application, and Mediation servers</span></span>

<span data-ttu-id="52231-104">이 문서에서는 회의, 응용 프로그램 및 중재 서버에 대해 포트 범위 및 서비스 품질 정책을 구성하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="52231-104">This article describes how to configure port ranges and a Quality of Service policy for your Conferencing, Application, and Mediation servers.</span></span>

## <a name="configure-port-ranges"></a><span data-ttu-id="52231-105">포트 범위 구성</span><span class="sxs-lookup"><span data-stu-id="52231-105">Configure port ranges</span></span>

<span data-ttu-id="52231-106">서비스 품질을 구현하기 위해 회의, 응용 프로그램 및 중재 서버에서 오디오, 비디오 및 응용 프로그램 공유에 대해 동일한 포트 범위를 구성해야 합니다. 또한 이러한 포트 범위가 어떤 식으로도 겹쳐서도 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="52231-106">To implement Quality of Service, you should configure identical port ranges for audio, video, and application sharing on your Conferencing, Application, and Mediation servers; furthermore, those port ranges must not overlap in any way.</span></span> <span data-ttu-id="52231-107">간단한 예제를 사용하기 위해 회의 서버에서 비디오에 포트 10000~10999를 사용하는 경우를 가정해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="52231-107">To use a simple example, suppose you use ports 10000 through 10999 for video on your Conferencing servers.</span></span> <span data-ttu-id="52231-108">즉, 응용 프로그램 및 중재 서버에서 비디오에 대해 포트 10000~10999도 예약해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="52231-108">That means that you must also reserve ports 10000 through 10999 for video on your Application and Mediation servers.</span></span> <span data-ttu-id="52231-109">그렇지 않은 경우 QoS가 예상대로 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="52231-109">If you do not, QoS will not work as expected.</span></span>

<span data-ttu-id="52231-110">마찬가지로, 비디오용 포트 10000~10999를 예약한 다음 오디오에 대해 포트 10500~11999를 예약하는 경우를 가정해 가정해 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="52231-110">Similarly, suppose you reserve ports 10000 through 10999 for video, but then reserve ports 10500 through 11999 for audio.</span></span> <span data-ttu-id="52231-111">포트 범위가 겹치기 때문에 서비스 품질에 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="52231-111">This can create problems for Quality of Service, because the port ranges overlap.</span></span> <span data-ttu-id="52231-112">QoS에서는 각 모달에 고유한 포트 집합이 있어야 합니다. 비디오에 포트 10000~10999를 사용하는 경우 다른 범위(예: 오디오의 경우 11000에서 11999)를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="52231-112">With QoS, each modality must have a unique set of ports: if you use ports 10000 through 10999 for video, then you'll have to use a different range (for example, 11000 through 11999, for audio).</span></span>

<span data-ttu-id="52231-113">기본적으로 비즈니스용 Skype 서버에서는 오디오 및 비디오 포트 범위가 겹치지 않습니다. 그러나 응용 프로그램 공유에 할당된 포트 범위는 오디오 및 비디오 포트 범위와 겹칩니다.</span><span class="sxs-lookup"><span data-stu-id="52231-113">By default, audio and video port ranges do not overlap in Skype for Business Server; however, the port ranges assigned to application sharing overlap with both the audio and video port ranges.</span></span> <span data-ttu-id="52231-114">따라서 이러한 범위가 고유하지 않습니다. 비즈니스용 Skype 서버 관리 셸 내에서 다음 세 가지 명령을 실행하여 회의, 응용 프로그램 및 중재 서버에 대한 기존 포트 범위를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="52231-114">(Which, in turn, means that none of these ranges are unique.) You can verify the existing port ranges for your Conferencing, Application, and Mediation servers by running the following three commands from within the Skype for Business Server Management Shell:</span></span>

    Get-CsService -ConferencingServer | Select-Object Identity, AudioPortStart, AudioPortCount, VideoPortStart, VideoPortCount, AppSharingPortStart, AppSharingPortCount
    
    Get-CsService -ApplicationServer | Select-Object Identity, AudioPortStart, AudioPortCount
    
    Get-CsService -MediationServer | Select-Object Identity, AudioPortStart, AudioPortCount

> [!WARNING]  
> <span data-ttu-id="52231-115">앞의 명령에서 볼 수 있니, 각 포트 유형(오디오, 비디오 및 응용 프로그램 공유)에는 포트 시작 및 포트 수의 두 가지 별도 속성 값이 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="52231-115">As you can see in the preceding commands, each port type – audio, video, and application sharing – is assigned two separate property values: the port start and the port count.</span></span> <span data-ttu-id="52231-116">포트 시작은 해당 모달에 사용되는 첫 번째 포트를 나타냅니다. 예를 들어 오디오 포트 시작이 50000이면 오디오 트래픽에 사용되는 첫 번째 포트가 포트 50000입니다.</span><span class="sxs-lookup"><span data-stu-id="52231-116">The port start indicates the first port used for that modality; for example, if the audio port start is equal to 50000 that means that the first port used for audio traffic is port 50000.</span></span> <span data-ttu-id="52231-117">오디오 포트 수가 2(유효한 값은 아니며 설명을 위해 여기에 사용)이면 오디오에 대해 두 개의 포트만 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="52231-117">If the audio port count is 2 (which is not a valid value, but is used here for illustration purposes), that means that only two ports are allocated for audio.</span></span> <span data-ttu-id="52231-118">첫 번째 포트가 포트 50000인 경우 총 2개의 포트가 있는 경우 두 번째 포트는 포트 50001(포트 범위는 연속해야 합니다)을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="52231-118">If the first port is port 50000 and there are a total of two ports, that means the second port must be port 50001 (port ranges have to be contiguous).</span></span> <span data-ttu-id="52231-119">따라서 오디오에 대한 포트 범위는 포트 50000에서 50001(포함)입니다.</span><span class="sxs-lookup"><span data-stu-id="52231-119">As a result, the port range for audio would be ports 50000 through 50001, inclusive.</span></span><BR><br><span data-ttu-id="52231-120">응용 프로그램 서버 및 중재 서버는 오디오에 대해서만 QoS를 지원합니다. 응용 프로그램 서버 또는 중재 서버에서는 비디오 또는 응용 프로그램 공유 포트를 변경할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="52231-120">Note, too that Application server and Mediation server only support QoS for audio; you do not need to change video or application sharing ports in your Application servers or Mediation servers.</span></span>

<span data-ttu-id="52231-121">앞의 세 명령을 실행하면 비즈니스용 Skype 서버의 기본 포트 값이 아래와 같이 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="52231-121">If you run the preceding three commands, you'll see that that the default port values for Skype for Business Server are configured like this:</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="52231-122">속성</span><span class="sxs-lookup"><span data-stu-id="52231-122">Property</span></span></th>
<th><span data-ttu-id="52231-123">회의 서버</span><span class="sxs-lookup"><span data-stu-id="52231-123">Conferencing Server</span></span></th>
<th><span data-ttu-id="52231-124">응용 프로그램 서버</span><span class="sxs-lookup"><span data-stu-id="52231-124">Application Server</span></span></th>
<th><span data-ttu-id="52231-125">중재 서버</span><span class="sxs-lookup"><span data-stu-id="52231-125">Mediation Server</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="52231-126">AudioPortStart</span><span class="sxs-lookup"><span data-stu-id="52231-126">AudioPortStart</span></span></p></td>
<td><p><span data-ttu-id="52231-127">49152</span><span class="sxs-lookup"><span data-stu-id="52231-127">49152</span></span></p></td>
<td><p><span data-ttu-id="52231-128">49152</span><span class="sxs-lookup"><span data-stu-id="52231-128">49152</span></span></p></td>
<td><p><span data-ttu-id="52231-129">49152</span><span class="sxs-lookup"><span data-stu-id="52231-129">49152</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52231-130">AudioPortCount</span><span class="sxs-lookup"><span data-stu-id="52231-130">AudioPortCount</span></span></p></td>
<td><p><span data-ttu-id="52231-131">8348</span><span class="sxs-lookup"><span data-stu-id="52231-131">8348</span></span></p></td>
<td><p><span data-ttu-id="52231-132">8348</span><span class="sxs-lookup"><span data-stu-id="52231-132">8348</span></span></p></td>
<td><p><span data-ttu-id="52231-133">8348</span><span class="sxs-lookup"><span data-stu-id="52231-133">8348</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52231-134">VideoPortStart</span><span class="sxs-lookup"><span data-stu-id="52231-134">VideoPortStart</span></span></p></td>
<td><p><span data-ttu-id="52231-135">57501</span><span class="sxs-lookup"><span data-stu-id="52231-135">57501</span></span></p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52231-136">VideoPortCount</span><span class="sxs-lookup"><span data-stu-id="52231-136">VideoPortCount</span></span></p></td>
<td><p><span data-ttu-id="52231-137">8034</span><span class="sxs-lookup"><span data-stu-id="52231-137">8034</span></span></p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52231-138">ApplicationSharingPortStart</span><span class="sxs-lookup"><span data-stu-id="52231-138">ApplicationSharingPortStart</span></span></p></td>
<td><p><span data-ttu-id="52231-139">49152</span><span class="sxs-lookup"><span data-stu-id="52231-139">49152</span></span></p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52231-140">ApplicationSharingPortCount</span><span class="sxs-lookup"><span data-stu-id="52231-140">ApplicationSharingPortCount</span></span></p></td>
<td><p><span data-ttu-id="52231-141">16383</span><span class="sxs-lookup"><span data-stu-id="52231-141">16383</span></span></p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
</tbody>
</table>

<span data-ttu-id="52231-142">앞서 언급했듯이 QoS에 대해 비즈니스용 Skype 서버 포트를 구성할 때 다음을 보장해야 합니다. 1) 오디오 포트 설정이 회의, 응용 프로그램 및 중재 서버에서 동일합니다. 2) 포트 범위가 겹치지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="52231-142">As noted previously, when configuring Skype for Business Server ports for QoS, you should ensure that: 1) audio port settings are identical across yours Conferencing, Application, and Mediation servers; and, 2) port ranges do not overlap.</span></span> <span data-ttu-id="52231-143">앞의 표를 자세히 보면 세 가지 서버 유형에서 포트 범위가 동일하다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="52231-143">If you look closely at the preceding table, you will see that the port ranges are identical across the three server types.</span></span> <span data-ttu-id="52231-144">예를 들어 시작 오디오 포트는 각 서버 유형에서 포트 49152로 설정되어 있으며 각 서버의 오디오에 예약된 총 포트 수도 동일합니다. 8348.</span><span class="sxs-lookup"><span data-stu-id="52231-144">For example, the starting audio port is set to port 49152 on each server type, and the total number of ports reserved for audio in each server is also identical: 8348.</span></span> <span data-ttu-id="52231-145">그러나 포트 범위가 겹칩니다. 오디오 포트는 포트 49152에서 시작되지만 응용 프로그램 공유를 위해 포트를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="52231-145">However, the port ranges overlap: audio ports start at port 49152, but so do the ports set aside for application sharing.</span></span> <span data-ttu-id="52231-146">서비스의 품질을 최적화하기 위해 고유한 포트 범위를 사용할 수 있도록 응용 프로그램 공유를 다시 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="52231-146">In order to make optimal use of Quality of Service, application sharing should be reconfigured to use a unique port range.</span></span> <span data-ttu-id="52231-147">예를 들어 포트 40803에서 시작하여 8348 포트를 사용하도록 응용 프로그램 공유를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="52231-147">For example, you could configure application sharing to start at port 40803 and to use 8348 ports.</span></span> <span data-ttu-id="52231-148">(8348 포트가 있는 이유는 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="52231-148">(Why 8348 ports?</span></span> <span data-ttu-id="52231-149">이러한 값을 함께 추가하는 경우(40803 + 8348) 응용 프로그램 공유에서 포트 40803 ~ 포트 49150을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="52231-149">If you add those values together -- 40803 + 8348 -- that means that application sharing will use ports 40803 through port 49150.</span></span> <span data-ttu-id="52231-150">오디오 포트는 포트 49152까지 시작되지 않습니다. 더 이상 겹치는 포트 범위가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="52231-150">Because audio ports do not begin until port 49152, you will no longer have any overlapping port ranges.)</span></span>

<span data-ttu-id="52231-151">응용 프로그램 공유를 위한 새 포트 범위를 선택한 후 이 cmdlet을 사용하여 변경할 Set-CsConferencingServer 있습니다.</span><span class="sxs-lookup"><span data-stu-id="52231-151">After you have selected the new port range for application sharing, you can make your change by using the Set-CsConferencingServer cmdlet.</span></span> <span data-ttu-id="52231-152">이러한 서버에서 응용 프로그램 공유 트래픽이 처리되지 않기 때문에 이러한 항목은 응용 프로그램 서버 또는 중재 서버에서 변경할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="52231-152">This change does not need to be made on your Application servers or on your Mediation servers, because these servers do not handle application sharing traffic.</span></span> <span data-ttu-id="52231-153">오디오 트래픽에 사용되는 포트를 다시 지정할 경우에만 해당 서버에서 포트 값을 변경해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="52231-153">You only need to change port values on these servers if you decide to reassign the ports used for audio traffic.</span></span>

<span data-ttu-id="52231-154">단일 회의 서버에서 응용 프로그램 공유에 대한 포트 값을 수정하려면 비즈니스용 Skype 서버 관리 셸 내에서 이와 유사한 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="52231-154">To modify the port values for application sharing on a single Conferencing server, run a command similar to this from within the Skype for Business Server Management Shell:</span></span>

    Set-CsConferenceServer -Identity ConferencingServer:atl-cs-001.litwareinc.com -AppSharingPortStart 40803 -AppSharingPortCount 8348

<span data-ttu-id="52231-155">모든 회의 서버에서 이러한 변경을 적용하려는 경우 다음 명령을 대신 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="52231-155">If you want to make these changes on all your Conferencing servers, you can run this command instead:</span></span>

    Get-CsService -ConferencingServer | ForEach-Object {Set-CsConferenceServer -Identity $_.Identity -AppSharingPortStart 40803 -AppSharingPortCount 8348}

<span data-ttu-id="52231-156">포트 설정을 변경한 후 변경 내용의 영향을 받는 각 서비스를 중지했다가 다시 시작해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="52231-156">After changing port settings, you should stop and then restart each service affected by the changes.</span></span>

<span data-ttu-id="52231-p107">회의 서버, 응용 프로그램 서버 및 중재 서버가 정확히 동일한 포트 범위를 공유할 필요는 없으며, 모든 서버에서 고유한 포트 범위를 별도로 설정하기만 하면 됩니다. 하지만 관리 측면에서는 모든 서버에서 동일한 포트 집합을 사용하는 것이 더 쉬울 것입니다.</span><span class="sxs-lookup"><span data-stu-id="52231-p107">It is not mandatory that your Conferencing servers, Application servers, and Mediation servers share the exact same port range; the only true requirement is that you set aside unique port ranges on all your servers. However, administration will typically be easier if you use the same set of ports on all your servers.</span></span>

## <a name="configure-a-quality-of-service-policy-in-skype-for-business-server-for-your-conferencing-application-and-mediation-servers"></a><span data-ttu-id="52231-159">회의, 응용 프로그램 및 중재 서버에 대한 비즈니스용 Skype 서버에서 서비스 품질 정책 구성</span><span class="sxs-lookup"><span data-stu-id="52231-159">Configure a Quality of Service policy in Skype for Business Server for your Conferencing, Application, and Mediation servers</span></span>

<span data-ttu-id="52231-p108">포트 범위를 구성하면 지정된 유형의 모든 트래픽(예: 모든 오디오 트래픽)이 동일한 포트 집합을 통과하도록 보장하여 QoS(서비스 품질)를 쉽게 사용할 수 있습니다. 이렇게 하면 시스템에서 특정 패킷을 쉽게 식별하고 표시할 수 있습니다. 포트 49152가 오디오 트래픽을 위해 예약된 경우 포트 49152를 통과하는 모든 패킷에 이 패킷이 오디오 패킷임을 나타내는 DSCP 코드를 표시할 수 있습니다. 이렇게 하면 라우터가 패킷을 오디오 패킷으로 식별하고 표시되지 않은 패킷(예: 서버 간 파일 복사에 사용되는 패킷)보다 높은 우선 순위를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="52231-p108">Configuring port ranges facilitates the use of Quality of Service by ensuring that all traffic of a specified type (for example, all audio traffic) travels through the same set of ports. This makes it easy for the system to identify and mark a given packet: if port 49152 is reserved for audio traffic, then any packet traveling through port 49152 can be marked with a DSCP code that indicates that this is an audio packet. In turn, this enables routers to identify the packet as an audio packet, and give it higher priority than unmarked packets (such as packets used to copy a file from one server to another).</span></span>

<span data-ttu-id="52231-163">하지만 단순히 포트 집합을 특정 트래픽 유형으로 제한하는 것만으로는 패킷이 적절한 DSCP 코드로 표시된 포트를 통과할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="52231-163">However, simply restricting a set of ports to a specific type of traffic does not result in packets traveling through those ports being marked with the appropriate DSCP code.</span></span> <span data-ttu-id="52231-164">포트 범위를 정의하는 것 외에도 각 포트 범위와 연결될 DSCP 코드를 지정하는 서비스 품질 정책도 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="52231-164">In addition to defining port ranges, you must also create Quality of Service policies that specify the DSCP code to be associated with each port range.</span></span> <span data-ttu-id="52231-165">비즈니스용 Skype 서버의 경우 일반적으로 오디오용 정책과 비디오용 정책 두 개를 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="52231-165">For Skype for Business Server, that typically means creating two policies: one for audio and one for video.</span></span>

<span data-ttu-id="52231-166">서비스 품질 정책은 그룹 정책을 사용하여 가장 쉽게 만들어 관리됩니다.</span><span class="sxs-lookup"><span data-stu-id="52231-166">Quality of Service policies are most easily created, and managed, by using Group Policy.</span></span> <span data-ttu-id="52231-167">로컬 보안 정책을 사용해서도 이와 동일한 정책을 만들 수 있지만 이렇게 하려면 모든 컴퓨터에서 동일한 절차를 반복해서 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="52231-167">(These same policies can also be created by using local security policies.</span></span> <span data-ttu-id="52231-168">그러나 이 경우 각 컴퓨터와 모든 컴퓨터에서 동일한 절차를 반복해야 합니다. 초기 QoS 정책 집합(오디오 및 비디오용 1개)은 회의 서버, 응용 프로그램 서버 및/또는 중재 서버 서비스를 실행하는 비즈니스용 Skype 서버 컴퓨터에만 적용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="52231-168">However, that requires you to repeat the same procedure on each and every computer.) Your initial set of QoS policies (one for audio and one for video) should be applied only to Skype for Business Server computers running the Conferencing server, Application server, and/or Mediation server services.</span></span> <span data-ttu-id="52231-169">이러한 모든 컴퓨터가 동일한 Active Directory OU에 있는 경우 해당 OU에 새 GPO(그룹 정책 개체)를 할당하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="52231-169">If all of these computers are located in the same Active Directory OU, you can simply assign the new Group Policy object (GPO) to that OU.</span></span> <span data-ttu-id="52231-170">예를 들어 보안 그룹에 적절한 컴퓨터를 배치한 후 그룹 정책 보안 필터링을 사용해서 GPO를 해당 보안 그룹에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="52231-170">Alternatively, you can take other steps to target the new policy to the specified computers; for example, you can place the appropriate computers in a security group, then use Group Policy security filtering to apply the GPO just to that security group.</span></span>

<span data-ttu-id="52231-171">오디오 관리를 위한 서비스 품질 정책을 만들하려면 그룹 정책 관리가 설치된 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="52231-171">To create a Quality of Service policy for managing audio, log on to a computer where Group Policy Management has been installed.</span></span> <span data-ttu-id="52231-172">그룹 정책 관리를 열고(시작, 관리 도구를 클릭한 다음 그룹 정책 관리를 **클릭)** 다음 절차를 완료합니다.  </span><span class="sxs-lookup"><span data-stu-id="52231-172">Open Group Policy Management (click **Start**, point to **Administrative Tools**, and then click **Group Policy Management**) and then complete the following procedure:</span></span>

1.  <span data-ttu-id="52231-173">그룹 정책 관리에서 새 정책을 만들 컨테이너를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="52231-173">In Group Policy Management, locate the container where the new policy should be created.</span></span> <span data-ttu-id="52231-174">예를 들어 모든 비즈니스용 Skype 서버 컴퓨터가 비즈니스용 Skype 서버라는 OU에 있는 경우 비즈니스용 Skype 서버 OU에서 새 정책을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="52231-174">For example, if all your Skype for Business Server computers are located in an OU named Skype for Business Server, then the new policy should be created in the Skype for Business Server OU.</span></span>

2.  <span data-ttu-id="52231-175">적절한 컨테이너를 마우스 오른쪽 단추로 클릭한 다음 이 도메인에서 GPO 만들기를 클릭하고 여기에 **연결합니다.**</span><span class="sxs-lookup"><span data-stu-id="52231-175">Right-click the appropriate container, and then click **Create a GPO in this domain, and Link it here**.</span></span>

3.  <span data-ttu-id="52231-176">새 **GPO** 대화 상자의 이름 상자에 새 그룹  정책 개체의 이름을 입력하고(예: 비즈니스용 **Skype 서버 QoS)** 확인을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="52231-176">In the **New GPO** dialog box, type a name for the new Group Policy object in the **Name** box (for example, **Skype for Business Server QoS**), and then click **OK**.</span></span>

4.  <span data-ttu-id="52231-177">새로 만든 정책을 마우스 오른쪽 단추로 클릭한 다음 편집을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="52231-177">Right-click the newly-created policy, and then click **Edit**.</span></span>

5.  <span data-ttu-id="52231-178">그룹 정책 관리 편집기에서 **컴퓨터 구성**, **정책**, **Windows 설정** 을 확장하고 **정책 기반 QoS** 를 확장하고 **새 정책 만들기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="52231-178">In the Group Policy Management Editor, expand **Computer Configuration**, expand **Policies**, expand **Windows Settings**, right-click **Policy-based QoS**, and then click **Create new policy**.</span></span>

6.  <span data-ttu-id="52231-179">정책 기반 **QoS** 대화 상자의 열기 페이지에서 이름 상자에 새 정책의 이름(예: 비즈니스용 **Skype 서버 QoS)을** **입력합니다.**</span><span class="sxs-lookup"><span data-stu-id="52231-179">In the **Policy-based QoS** dialog box, on the opening page, type a name for the new policy (e.g., **Skype for Business Server QoS**) in the **Name** box.</span></span> <span data-ttu-id="52231-180">**DSCP 값 지정** 을 선택하고 값을 **46** 으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="52231-180">Select **Specify DSCP Value** and set the value to **46**.</span></span> <span data-ttu-id="52231-181">**아웃바운드 스로틀 속도 지정** 은 선택되지 않은 상태로 두고 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="52231-181">Leave **Specify Outbound Throttle Rate** unselected, and then click **Next**.</span></span>

7.  <span data-ttu-id="52231-182">다음 페이지에서 모든 응용  프로그램이 선택되어 있는지 확인한 후 다음을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="52231-182">On the next page, make sure that **All applications** is selected, and then click **Next**.</span></span> <span data-ttu-id="52231-183">이렇게 하면 모든 응용 프로그램이 지정된 DSCP 코드로 지정된 포트 범위의 패킷과 일치하도록 보장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="52231-183">This simply ensures that all applications will match packets from the specified port range with the specified DSCP code.</span></span>

8.  <span data-ttu-id="52231-184">세 번째 페이지에서 원본 IP 주소와 모든 대상 **IP** 주소가 모두 선택되어 있는지 확인한 후 다음을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="52231-184">On the third page, make sure that both **Any source IP address and Any destination IP address** are selected, and then click **Next**.</span></span> <span data-ttu-id="52231-185">이러한 두 설정은 해당 패킷을 전송하는 컴퓨터(IP 주소) 및 패킷을 수신하는 컴퓨터(IP 주소)에 관계없이 패킷이 관리되도록 보장합니다.</span><span class="sxs-lookup"><span data-stu-id="52231-185">These two settings ensure that packets will be managed regardless of which computer (IP address) sent those packets and which computer (IP address) will receive those packets.</span></span>

9.  <span data-ttu-id="52231-186">4페이지에서는 **이 QoS 정책이 적용되는 프로토콜 선택** 드롭다운 목록에서 **TCP 및 UDP** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="52231-186">On page four, select **TCP and UDP** from the **Select the protocol this QoS policy applies to** dropdown list.</span></span> <span data-ttu-id="52231-187">TCP(Transmission Control Protocol) 및 UDP(User Datagram Protocol)는 비즈니스용 Skype 서버 및 해당 클라이언트 응용 프로그램에서 가장 일반적으로 사용되는 두 가지 네트워킹 프로토콜입니다.</span><span class="sxs-lookup"><span data-stu-id="52231-187">TCP (Transmission Control Protocol) and UDP (User Datagram Protocol) are the two networking protocols most-commonly used by Skype for Business Server and its client applications.</span></span>

10. <span data-ttu-id="52231-188">**원본 포트 번호 지정** 제목 아래에서 **이 원본 포트 또는 범위부터** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="52231-188">Under the heading **Specify the source port number**, select **From this source port or range**.</span></span> <span data-ttu-id="52231-189">포함된 텍스트 상자에는 오디오 전송에 예약된 포트 범위를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="52231-189">In the accompanying text box, type the port range reserved for audio transmissions.</span></span> <span data-ttu-id="52231-190">예를 들어 오디오 트래픽에 대해 포트 49152~ 포트 57500을 예약한 경우 다음 형식을 사용하여 포트 범위를 입력합니다. **49152:57500**.</span><span class="sxs-lookup"><span data-stu-id="52231-190">For example, if you reserved ports 49152 through ports 57500 for audio traffic, enter the port range using this format: **49152:57500**.</span></span> <span data-ttu-id="52231-191">**마침** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="52231-191">Click **Finish**.</span></span>

> [!NOTE]  
> <span data-ttu-id="52231-192">DSCP 값 46은 다소 임의적입니다. DSCP 46은 오디오 패킷을 표시하는 데 자주 사용되는 경우가 지만 오디오 통신에 DSCP 46을 사용할 것은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="52231-192">The DSCP value of 46 is somewhat arbitrary: although DSCP 46 is often used for marking audio packets, you do not have to use DSCP 46 for audio communications.</span></span> <span data-ttu-id="52231-193">QoS를 이미 구현한 경우 오디오에 다른 DSCP 코드(예: DSCP 40)를 사용하는 경우 동일한 코드(예: 오디오의 경우 40)를 사용하도록 서비스 품질 정책을 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="52231-193">If you have already implemented QoS and you are using a different DSCP code for audio (for example, DSCP 40), you should configure your Quality of Service policy to use that same code (i.e., 40 for audio).</span></span> <span data-ttu-id="52231-194">이제 서비스 품질을 구현하는 경우 해당 값이 오디오 패킷을 표시하는 데 일반적으로 사용된다고 하여 오디오에 DSCP 46을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="52231-194">If you are just now implementing Quality of Service, then it is recommended that you use DSCP 46 for audio, simply because that value is commonly used to mark audio packets.</span></span>

<span data-ttu-id="52231-195">오디오 트래픽에 대한 QoS 정책을 만든 후 비디오 트래픽에 대한 두 번째 정책과 응용 프로그램 공유 트래픽을 관리하기 위한 세 번째 정책(선택 사항)을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="52231-195">After you have created the QoS policy for audio traffic, you should then create a second policy for video traffic (and, optionally, a third policy for managing application sharing traffic).</span></span> <span data-ttu-id="52231-196">비디오용 정책을 만들려면 오디오 정책을 만들 때 수행한 것과 기본적으로는 같은 절차를 따르되 다음 항목을 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="52231-196">To create a policy for video, follow the same basic procedure you followed when creating the audio policy, making these substitutions:</span></span>

  - <span data-ttu-id="52231-197">다른 고유한 정책 이름(예: 비즈니스용 **Skype 서버 비디오)을 사용하세요.**</span><span class="sxs-lookup"><span data-stu-id="52231-197">Use a different (and unique) policy name (for example, **Skype for Business Server Video**).</span></span>

  - <span data-ttu-id="52231-p120">DSCP 값을 46이 아닌 **34** 로 설정합니다. DSCP 값 34를 반드시 사용할 필요는 없습니다. 오디오에 사용한 것과는 다른 DSCP 값을 비디오에 사용하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="52231-p120">Set the DSCP value to **34** instead of 46. (Note that you do not have to use a DSCP value of 34. The only requirement is that you use a different DSCP value for video than you used for audio.)</span></span>

  - <span data-ttu-id="52231-201">비디오 트래픽에 대해 이전에 구성된 포트 범위를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="52231-201">Use the previously configured port range for video traffic.</span></span> <span data-ttu-id="52231-202">예를 들어 비디오용 포트 57501~65535를 예약한 경우 포트 범위를 **57501:65535로** 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="52231-202">For example, if you have reserved ports 57501 through 65535 for video, set the port range to this: **57501:65535**.</span></span>

<span data-ttu-id="52231-203">응용 프로그램 공유 트래픽을 관리하기 위한 정책을 만드는 경우 세 번째 정책을 만들어 다음을 다음과 같이 대치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="52231-203">If you decide to create a policy for managing application sharing traffic, you must create a third policy, making the following substitutions:</span></span>

  - <span data-ttu-id="52231-204">다른 고유한 정책 이름(예: 비즈니스용 Skype 서버 응용 프로그램 **공유)을 사용하세요.**</span><span class="sxs-lookup"><span data-stu-id="52231-204">Use a different (and unique) policy name (for example, **Skype for Business Server Application Sharing**).</span></span>

  - <span data-ttu-id="52231-p122">DSCP 값을 46이 아닌 **24** 로 설정합니다. DSCP 값 24를 반드시 사용할 필요는 없습니다. 오디오나 비디오에 사용한 것과는 다른 DSCP 값을 응용 프로그램 공유에 사용하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="52231-p122">Set the DSCP value to **24** instead of 46. (Again, you do not have to use a DSCP value of 24. The only requirement is that you use a different DSCP value for application sharing than you used for audio or for video.)</span></span>

  - <span data-ttu-id="52231-208">비디오 트래픽에 대해 이전에 구성된 포트 범위를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="52231-208">Use the previously configured port range for video traffic.</span></span> <span data-ttu-id="52231-209">예를 들어 응용 프로그램 공유를 위해 포트 40803~ 49151을 예약한 경우 포트 범위를 **40803:49151로** 설정하십시오.</span><span class="sxs-lookup"><span data-stu-id="52231-209">For example, if you have reserved ports 40803 through 49151 for application sharing, set the port range to this: **40803:49151**.</span></span>

<span data-ttu-id="52231-210">만든 새 정책은 비즈니스용 Skype 서버 컴퓨터에서 그룹 정책을 새로 고칠 때까지 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="52231-210">The new policies you have created will not take effect until Group Policy has been refreshed on your Skype for Business Server computers.</span></span> <span data-ttu-id="52231-211">그룹 정책은 일정한 간격에 따라 자체적으로 새로 고쳐지기는 하지만, 그룹 정책을 새로 고쳐야 하는 각 컴퓨터에서 다음 명령을 실행하면 그룹 정책을 강제로 즉시 새로 고칠 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="52231-211">Although Group Policy periodically refreshes on its own, you can force an immediate refresh by running the following command on each computer where Group Policy needs to be refreshed:</span></span>

    Gpupdate.exe /force

<span data-ttu-id="52231-212">이 명령은 비즈니스용 Skype 서버 관리 셸 내에서 또는 관리자 자격 증명으로 실행되는 모든 명령 창에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="52231-212">This command can be run from within the Skype for Business Server Management Shell or from any command window that is running under administrator credentials.</span></span> <span data-ttu-id="52231-213">관리자 자격 증명을 사용한 명령 창을 실행하려면 **시작** 을 클릭하고 **명령 프롬프트** 를 마우스 오른쪽 단추로 클릭한 후 **관리자 권한으로 실행** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="52231-213">To run a command window under administrator credentials, click **Start**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span>

<span data-ttu-id="52231-214">새 QoS 정책이 적용되었는지 확인하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="52231-214">To verify that the new QoS policies have been applied, do the following:</span></span>

1.  <span data-ttu-id="52231-215">비즈니스용 Skype 서버 컴퓨터에서 시작을 클릭한 다음 실행을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="52231-215">On a Skype for Business Server computer, click **Start**, and then click **Run**.</span></span>

2.  <span data-ttu-id="52231-216">실행 **대화 상자에서** **regedit를** 입력한 다음 Enter를 누르고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="52231-216">In the **Run** dialog box, type **regedit**, and then press ENTER.</span></span>

3.  <span data-ttu-id="52231-217">레지스트리 편집기에서 **컴퓨터,** **HKEY \_ \_ 로컬** 컴퓨터, **소프트웨어** 확장, 정책 **확장,** **Microsoft** 확장, **Windows** 확장, **QoS를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="52231-217">In Registry Editor, expand **Computer**, expand **HKEY\_LOCAL\_MACHINE**, expand **SOFTWARE**, expand **Policies**, expand **Microsoft**, expand **Windows**, and then click **QoS**.</span></span> <span data-ttu-id="52231-218">**QoS** 아래에 바로 전에 만든 각 QoS 정책에 대한 레지스트리 키가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="52231-218">Under **QoS** you should see registry keys for each of the QoS policies you just created.</span></span> <span data-ttu-id="52231-219">예를 들어 두 개의 새 정책(비즈니스용 Skype 서버 오디오 QoS 및 다른 명명된 비즈니스용 Skype 서버 비디오 QoS)을 만든 경우 비즈니스용 Skype 서버 오디오 QoS 및 비즈니스용 Skype 서버 비디오 QoS에 대한 레지스트리 항목이 표시되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="52231-219">For example, if you created two new policies (one named Skype for Business Server Audio QoS and the other named Skype for Business Server Video QoS), you should see registry entries for Skype for Business Server Audio QoS and Skype for Business Server Video QoS.</span></span>

<span data-ttu-id="52231-220">네트워크 패킷이 적절한 DSCP 값으로 표시되도록 하려면 다음 절차를 완료하여 각 컴퓨터에서 새 레지스트리 항목도 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="52231-220">To help ensure that network packets are marked with the appropriate DSCP value, you should also create a new registry entry on each computer by completing the following procedure:</span></span>

1.  <span data-ttu-id="52231-221">**시작** 을 클릭한 다음 **실행** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="52231-221">Click **Start**, and then click **Run**.</span></span>

2.  <span data-ttu-id="52231-222">실행 **대화 상자에서** **regedit를** 입력한 다음 Enter를 누르고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="52231-222">In the **Run** dialog box, type **regedit**, and then press ENTER.</span></span>

3.  <span data-ttu-id="52231-223">레지스트리 편집기에서 **HKEY \_ LOCAL \_ MACHINE,** **SYSTEM,** **CurrentControlSet,** 서비스 및 **Tcpip를** 확장합니다. </span><span class="sxs-lookup"><span data-stu-id="52231-223">In the Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **SYSTEM**, expand **CurrentControlSet**, expand **services**, and then expand **Tcpip**.</span></span>

4.  <span data-ttu-id="52231-224">**Tcpip** 를 마우스 오른쪽 단추로 클릭하고 **새로 만들기** 를 가리킨 다음 **키** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="52231-224">Right-click **Tcpip**, point to **New**, and then click **Key**.</span></span> <span data-ttu-id="52231-225">새 레지스트리 키를 만든 후 **QoS를** 입력한 다음 Enter 키를 눌러 키 이름을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="52231-225">After the new registry key is created, type **QoS**, and then press ENTER to rename the key.</span></span>

5.  <span data-ttu-id="52231-226">**QoS** 를 마우스 오른쪽 단추로 클릭하고 **새로 만들기** 를 가리킨 다음 **문자열 값** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="52231-226">Right-click **QoS**, point to **New**, and then click **String Value**.</span></span> <span data-ttu-id="52231-227">새 레지스트리 값을 만든 후 **NLA를** 사용하지 말고 Enter를 눌러 값 이름을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="52231-227">After the new registry value is created, type **Do not use NLA**, and then press ENTER to rename the value.</span></span>

6.  <span data-ttu-id="52231-228">NLA 사용 안 를 두 **번 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="52231-228">Double-click **Do not use NLA**.</span></span> <span data-ttu-id="52231-229">문자열 **편집** 대화 상자에서 값 데이터  **상자에 1을** 입력하고 확인을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="52231-229">In the **Edit String** dialog box, type **1** in the **Value data** box, and then click **OK**.</span></span>

7.  <span data-ttu-id="52231-230">레지스트리 편집기를 닫고 컴퓨터를 다시 시작하십시오.</span><span class="sxs-lookup"><span data-stu-id="52231-230">Close the Registry Editor and reboot your computer.</span></span>
