---
title: 회의, 응용 프로그램, 중재 서버의 포트 범위 및 서비스 품질 정책 구성
ms.reviewer: ''
ms:assetid: 4d6eaa5d-0127-453f-be6a-e55384772d83
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204872(v=OCS.15)
ms:contentKeyID: 48184074
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 이 문서에서는 회의, 응용 프로그램, 중재 서버의 포트 범위 및 서비스 품질 정책을 구성 하는 방법을 설명 합니다.
ms.openlocfilehash: e0bd6092792a9ed813aadecc004f58830bc5b133
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36188547"
---
# <a name="configuring-port-ranges-and-a-quality-of-service-policy-for-your-conferencing-application-and-mediation-servers"></a><span data-ttu-id="20f34-103">회의, 응용 프로그램, 중재 서버의 포트 범위 및 서비스 품질 정책 구성</span><span class="sxs-lookup"><span data-stu-id="20f34-103">Configuring port ranges and a Quality of Service policy for your Conferencing, Application, and Mediation servers</span></span>

<span data-ttu-id="20f34-104">이 문서에서는 회의, 응용 프로그램, 중재 서버의 포트 범위 및 서비스 품질 정책을 구성 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="20f34-104">This article describes how to configure port ranges and a Quality of Service policy for your Conferencing, Application, and Mediation servers.</span></span>

## <a name="configure-port-ranges"></a><span data-ttu-id="20f34-105">포트 범위 구성</span><span class="sxs-lookup"><span data-stu-id="20f34-105">Configure port ranges</span></span>

<span data-ttu-id="20f34-106">서비스 품질을 구현 하려면, 회의, 응용 프로그램, 중재 서버에서 오디오, 비디오, 응용 프로그램 공유에 대해 동일한 포트 범위를 구성 해야 합니다. 또한 이러한 포트 범위는 어떤 방식으로든 중복 되지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="20f34-106">To implement Quality of Service, you should configure identical port ranges for audio, video, and application sharing on your Conferencing, Application, and Mediation servers; furthermore, those port ranges must not overlap in any way.</span></span> <span data-ttu-id="20f34-107">간단한 예제를 사용 하려면 회의 서버의 비디오에 대해 포트 1만 ~ 10999을 (를) 사용 한다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="20f34-107">To use a simple example, suppose you use ports 10000 through 10999 for video on your Conferencing servers.</span></span> <span data-ttu-id="20f34-108">즉, 응용 프로그램 및 중재 서버에서 비디오를 위해 1만 ~ 10999 포트를 예약 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="20f34-108">That means that you must also reserve ports 10000 through 10999 for video on your Application and Mediation servers.</span></span> <span data-ttu-id="20f34-109">그렇지 않으면 QoS가 예상 대로 작동 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="20f34-109">If you do not, QoS will not work as expected.</span></span>

<span data-ttu-id="20f34-110">마찬가지로 비디오용으로 포트 1만 ~ 10999을 예약 하 고 오디오에 대해 포트 10500 ~ 11999을 예약 한다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="20f34-110">Similarly, suppose you reserve ports 10000 through 10999 for video, but then reserve ports 10500 through 11999 for audio.</span></span> <span data-ttu-id="20f34-111">이렇게 하면 포트 범위가 겹치게 되므로 서비스 품질에 대 한 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20f34-111">This can create problems for Quality of Service, because the port ranges overlap.</span></span> <span data-ttu-id="20f34-112">QoS를 사용 하는 경우 각 모달 포트는 고유한 포트 집합을 사용 해야 합니다. 비디오에 1만 ~ 10999을 사용할 경우 다른 범위를 사용 해야 합니다 (예: 11000 ~ 11999, 오디오의 경우).</span><span class="sxs-lookup"><span data-stu-id="20f34-112">With QoS, each modality must have a unique set of ports: if you use ports 10000 through 10999 for video, then you'll have to use a different range (for example, 11000 through 11999, for audio).</span></span>

<span data-ttu-id="20f34-113">기본적으로 비즈니스용 Skype 서버에서 오디오 및 비디오 포트 범위가 중복 되지 않습니다. 그러나 오디오 및 비디오 포트 범위와 응용 프로그램 공유에 할당 된 포트 범위가 겹칩니다.</span><span class="sxs-lookup"><span data-stu-id="20f34-113">By default, audio and video port ranges do not overlap in Skype for Business Server; however, the port ranges assigned to application sharing overlap with both the audio and video port ranges.</span></span> <span data-ttu-id="20f34-114">즉, 이러한 범위 중 어느 것도 고유 하지 않음을 의미 합니다. 비즈니스용 Skype 서버 관리 셸에서 다음 세 개의 명령을 실행 하 여 회의, 응용 프로그램 및 중재 서버의 기존 포트 범위를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20f34-114">(Which, in turn, means that none of these ranges are unique.) You can verify the existing port ranges for your Conferencing, Application, and Mediation servers by running the following three commands from within the Skype for Business Server Management Shell:</span></span>

    Get-CsService -ConferencingServer | Select-Object Identity, AudioPortStart, AudioPortCount, VideoPortStart, VideoPortCount, AppSharingPortStart, AppSharingPortCount
    
    Get-CsService -ApplicationServer | Select-Object Identity, AudioPortStart, AudioPortCount
    
    Get-CsService -MediationServer | Select-Object Identity, AudioPortStart, AudioPortCount

> [!WARNING]  
> <span data-ttu-id="20f34-115">앞의 명령에서 볼 수 있듯이 각 포트 유형-오디오, 비디오 및 응용 프로그램 공유에는 두 가지 개별 속성 값인 포트 시작 및 포트 카운트가 할당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="20f34-115">As you can see in the preceding commands, each port type – audio, video, and application sharing – is assigned two separate property values: the port start and the port count.</span></span> <span data-ttu-id="20f34-116">포트 시작은 해당 모달에 사용 되는 첫 번째 포트를 나타냅니다. 예를 들어 오디오 포트 시작이 5만와 같으면 오디오 트래픽에 사용 되는 첫 번째 포트가 포트 5만입니다.</span><span class="sxs-lookup"><span data-stu-id="20f34-116">The port start indicates the first port used for that modality; for example, if the audio port start is equal to 50000 that means that the first port used for audio traffic is port 50000.</span></span> <span data-ttu-id="20f34-117">오디오 포트 카운트가 2 (유효한 값이 아니지만 여기서 설명 하기 위해 사용 되는 경우) 인 경우 오디오에 대 한 포트만 두 개만 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="20f34-117">If the audio port count is 2 (which is not a valid value, but is used here for illustration purposes), that means that only two ports are allocated for audio.</span></span> <span data-ttu-id="20f34-118">첫 번째 포트가 포트 5만이 고 총 두 개의 포트가 있는 경우 두 번째 포트는 포트 50001 (포트 범위는 연속적 이어야 함) 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="20f34-118">If the first port is port 50000 and there are a total of two ports, that means the second port must be port 50001 (port ranges have to be contiguous).</span></span> <span data-ttu-id="20f34-119">결과적으로 오디오의 포트 범위는 포트 5만 ~ 50001 (포함)입니다.</span><span class="sxs-lookup"><span data-stu-id="20f34-119">As a result, the port range for audio would be ports 50000 through 50001, inclusive.</span></span><BR><br><span data-ttu-id="20f34-120">단, 응용 프로그램 서버와 중재 서버는 오디오에 대 한 QoS만 지원 합니다. 응용 프로그램 서버나 중재 서버에서 비디오 또는 응용 프로그램 공유 포트를 변경할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="20f34-120">Note, too that Application server and Mediation server only support QoS for audio; you do not need to change video or application sharing ports in your Application servers or Mediation servers.</span></span>

<span data-ttu-id="20f34-121">앞의 세 명령을 실행 하면 비즈니스용 Skype 서버에 대 한 기본 포트 값이 다음과 같이 구성 된 것을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20f34-121">If you run the preceding three commands, you'll see that that the default port values for Skype for Business Server are configured like this:</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="20f34-122">속성</span><span class="sxs-lookup"><span data-stu-id="20f34-122">Property</span></span></th>
<th><span data-ttu-id="20f34-123">회의 서버</span><span class="sxs-lookup"><span data-stu-id="20f34-123">Conferencing Server</span></span></th>
<th><span data-ttu-id="20f34-124">응용 프로그램 서버</span><span class="sxs-lookup"><span data-stu-id="20f34-124">Application Server</span></span></th>
<th><span data-ttu-id="20f34-125">중재 서버</span><span class="sxs-lookup"><span data-stu-id="20f34-125">Mediation Server</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="20f34-126">AudioPortStart</span><span class="sxs-lookup"><span data-stu-id="20f34-126">AudioPortStart</span></span></p></td>
<td><p><span data-ttu-id="20f34-127">49152</span><span class="sxs-lookup"><span data-stu-id="20f34-127">49152</span></span></p></td>
<td><p><span data-ttu-id="20f34-128">49152</span><span class="sxs-lookup"><span data-stu-id="20f34-128">49152</span></span></p></td>
<td><p><span data-ttu-id="20f34-129">49152</span><span class="sxs-lookup"><span data-stu-id="20f34-129">49152</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="20f34-130">AudioPortCount</span><span class="sxs-lookup"><span data-stu-id="20f34-130">AudioPortCount</span></span></p></td>
<td><p><span data-ttu-id="20f34-131">8348</span><span class="sxs-lookup"><span data-stu-id="20f34-131">8348</span></span></p></td>
<td><p><span data-ttu-id="20f34-132">8348</span><span class="sxs-lookup"><span data-stu-id="20f34-132">8348</span></span></p></td>
<td><p><span data-ttu-id="20f34-133">8348</span><span class="sxs-lookup"><span data-stu-id="20f34-133">8348</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="20f34-134">VideoPortStart</span><span class="sxs-lookup"><span data-stu-id="20f34-134">VideoPortStart</span></span></p></td>
<td><p><span data-ttu-id="20f34-135">57501</span><span class="sxs-lookup"><span data-stu-id="20f34-135">57501</span></span></p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="20f34-136">VideoPortCount</span><span class="sxs-lookup"><span data-stu-id="20f34-136">VideoPortCount</span></span></p></td>
<td><p><span data-ttu-id="20f34-137">8034</span><span class="sxs-lookup"><span data-stu-id="20f34-137">8034</span></span></p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="20f34-138">ApplicationSharingPortStart</span><span class="sxs-lookup"><span data-stu-id="20f34-138">ApplicationSharingPortStart</span></span></p></td>
<td><p><span data-ttu-id="20f34-139">49152</span><span class="sxs-lookup"><span data-stu-id="20f34-139">49152</span></span></p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="20f34-140">ApplicationSharingPortCount</span><span class="sxs-lookup"><span data-stu-id="20f34-140">ApplicationSharingPortCount</span></span></p></td>
<td><p><span data-ttu-id="20f34-141">16383</span><span class="sxs-lookup"><span data-stu-id="20f34-141">16383</span></span></p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
</tbody>
</table>

<span data-ttu-id="20f34-142">앞에서 설명한 대로 QoS 용 비즈니스용 Skype 서버 포트를 구성 하는 경우에는 다음을 수행 해야 합니다. 1) 오디오 포트 설정이 회의, 응용 프로그램, 중재 서버에서 동일 하 게 유지 됩니다. and, 2) 포트 범위가 중복 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="20f34-142">As noted previously, when configuring Skype for Business Server ports for QoS, you should ensure that: 1) audio port settings are identical across yours Conferencing, Application, and Mediation servers; and, 2) port ranges do not overlap.</span></span> <span data-ttu-id="20f34-143">앞의 표에서 자세히 보면 포트 범위가 세 가지 서버 유형 모두와 동일 하다는 것을 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20f34-143">If you look closely at the preceding table, you will see that the port ranges are identical across the three server types.</span></span> <span data-ttu-id="20f34-144">예를 들어 시작 오디오 포트는 각 서버 유형에 서 포트 49152로 설정 되 고 각 서버에서 오디오에 대해 예약 된 총 포트 수는 동일 합니다 (8348).</span><span class="sxs-lookup"><span data-stu-id="20f34-144">For example, the starting audio port is set to port 49152 on each server type, and the total number of ports reserved for audio in each server is also identical: 8348.</span></span> <span data-ttu-id="20f34-145">그러나 포트 범위가 겹치지만 오디오 포트는 포트 49152에서 시작 하지만, 포트는 응용 프로그램 공유에 대해 별도로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="20f34-145">However, the port ranges overlap: audio ports start at port 49152, but so do the ports set aside for application sharing.</span></span> <span data-ttu-id="20f34-146">서비스 품질을 최적화 하기 위해 고유한 포트 범위를 사용 하도록 응용 프로그램 공유를 다시 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="20f34-146">In order to make optimal use of Quality of Service, application sharing should be reconfigured to use a unique port range.</span></span> <span data-ttu-id="20f34-147">예를 들어 포트 40803에서 시작 하 고 8348 포트를 사용 하도록 응용 프로그램 공유를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20f34-147">For example, you could configure application sharing to start at port 40803 and to use 8348 ports.</span></span> <span data-ttu-id="20f34-148">(8348 포트가 있는 이유는 무엇 인가요?</span><span class="sxs-lookup"><span data-stu-id="20f34-148">(Why 8348 ports?</span></span> <span data-ttu-id="20f34-149">이러한 값을 함께 추가 하는 경우--40803 + 8348--이는 응용 프로그램 공유가 포트 49150를 통해 포트 40803를 사용 하는 것을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="20f34-149">If you add those values together -- 40803 + 8348 -- that means that application sharing will use ports 40803 through port 49150.</span></span> <span data-ttu-id="20f34-150">오디오 포트는 포트 49152까지 시작 되지 않으므로 겹치는 포트 범위가 더 이상 없습니다.</span><span class="sxs-lookup"><span data-stu-id="20f34-150">Because audio ports do not begin until port 49152, you will no longer have any overlapping port ranges.)</span></span>

<span data-ttu-id="20f34-151">응용 프로그램 공유에 대 한 새 포트 범위를 선택한 후에는 CsConferencingServer cmdlet을 사용 하 여 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20f34-151">After you have selected the new port range for application sharing, you can make your change by using the Set-CsConferencingServer cmdlet.</span></span> <span data-ttu-id="20f34-152">이러한 서버는 응용 프로그램 서버나 중재 서버에서는 이러한 변경 작업을 수행할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="20f34-152">This change does not need to be made on your Application servers or on your Mediation servers, because these servers do not handle application sharing traffic.</span></span> <span data-ttu-id="20f34-153">오디오 트래픽에 사용 되는 포트를 다시 할당 하기로 결정 한 경우에만 이러한 서버에서 포트 값을 변경 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="20f34-153">You only need to change port values on these servers if you decide to reassign the ports used for audio traffic.</span></span>

<span data-ttu-id="20f34-154">단일 회의 서버에서 응용 프로그램 공유에 대 한 포트 값을 수정 하려면 비즈니스용 Skype 서버 관리 셸에서 다음과 같은 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="20f34-154">To modify the port values for application sharing on a single Conferencing server, run a command similar to this from within the Skype for Business Server Management Shell:</span></span>

    Set-CsConferenceServer -Identity ConferencingServer:atl-cs-001.litwareinc.com -AppSharingPortStart 40803 -AppSharingPortCount 8348

<span data-ttu-id="20f34-155">모든 회의 서버에서 이러한 변경 작업을 수행 하려면이 명령을 대신 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20f34-155">If you want to make these changes on all your Conferencing servers, you can run this command instead:</span></span>

    Get-CsService -ConferencingServer | ForEach-Object {Set-CsConferenceServer -Identity $_.Identity -AppSharingPortStart 40803 -AppSharingPortCount 8348}

<span data-ttu-id="20f34-156">포트 설정을 변경한 후 변경 내용에 영향을 받는 각 서비스를 중지 한 다음 다시 시작 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="20f34-156">After changing port settings, you should stop and then restart each service affected by the changes.</span></span>

<span data-ttu-id="20f34-157">사용자의 회의 서버, 응용 프로그램 서버, 중재 서버는 똑같은 포트 범위를 공유 하도록 필수가 아닙니다. 유일한 이유는 모든 서버에 고유한 포트 범위를 별도로 설정 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="20f34-157">It is not mandatory that your Conferencing servers, Application servers, and Mediation servers share the exact same port range; the only true requirement is that you set aside unique port ranges on all your servers.</span></span> <span data-ttu-id="20f34-158">그러나 모든 서버에서 동일한 포트 집합을 사용 하는 경우에는 일반적으로 관리 하기가 더 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="20f34-158">However, administration will typically be easier if you use the same set of ports on all your servers.</span></span>

## <a name="configure-a-quality-of-service-policy-in-skype-for-business-server-for-your-conferencing-application-and-mediation-servers"></a><span data-ttu-id="20f34-159">비즈니스용 Skype 서버에서 회의, 응용 프로그램 및 중재 서버용 서비스 품질 정책 구성</span><span class="sxs-lookup"><span data-stu-id="20f34-159">Configure a Quality of Service policy in Skype for Business Server for your Conferencing, Application, and Mediation servers</span></span>

<span data-ttu-id="20f34-160">포트 범위를 구성 하면 지정 된 유형의 모든 트래픽 (예: 모든 오디오 트래픽)이 동일한 포트 집합을 통과 하도록 하 여 서비스 품질을 쉽게 활용할 수가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20f34-160">Configuring port ranges facilitates the use of Quality of Service by ensuring that all traffic of a specified type (for example, all audio traffic) travels through the same set of ports.</span></span> <span data-ttu-id="20f34-161">이렇게 하면 시스템에서 지정 된 패킷을 쉽게 식별 하 고 표시할 수 있습니다. 포트 49152이 오디오 트래픽에 대해 예약 되어 있으면 포트 49152을 통해 이동 하는 모든 패킷을 오디오 패킷으로 표시 하는 DSCP 코드로 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20f34-161">This makes it easy for the system to identify and mark a given packet: if port 49152 is reserved for audio traffic, then any packet traveling through port 49152 can be marked with a DSCP code that indicates that this is an audio packet.</span></span> <span data-ttu-id="20f34-162">그런 다음 라우터는 패킷을 오디오 패킷으로 식별 하 고, 표시 되지 않은 패킷 (예: 한 서버에서 다른 서버로 파일을 복사 하는 데 사용 되는 패킷) 보다 높은 우선 순위를 부여 합니다.</span><span class="sxs-lookup"><span data-stu-id="20f34-162">In turn, this enables routers to identify the packet as an audio packet, and give it higher priority than unmarked packets (such as packets used to copy a file from one server to another).</span></span>

<span data-ttu-id="20f34-163">그러나 포트 집합을 특정 트래픽 유형으로 제한 하면 해당 포트를 통해 전달 되는 패킷이 적절 한 DSCP 코드로 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="20f34-163">However, simply restricting a set of ports to a specific type of traffic does not result in packets traveling through those ports being marked with the appropriate DSCP code.</span></span> <span data-ttu-id="20f34-164">포트 범위를 정의 하는 것 외에도 각 포트 범위와 연결 되는 DSCP 코드를 지정 하는 서비스 품질 정책도 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="20f34-164">In addition to defining port ranges, you must also create Quality of Service policies that specify the DSCP code to be associated with each port range.</span></span> <span data-ttu-id="20f34-165">비즈니스용 Skype 서버의 경우 일반적으로 오디오와 비디오용 중 하나에 대 한 두 개의 정책을 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="20f34-165">For Skype for Business Server, that typically means creating two policies: one for audio and one for video.</span></span>

<span data-ttu-id="20f34-166">서비스 품질 정책은 그룹 정책을 사용 하 여 가장 쉽게 만들고 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="20f34-166">Quality of Service policies are most easily created, and managed, by using Group Policy.</span></span> <span data-ttu-id="20f34-167">(이 동일한 정책은 로컬 보안 정책을 사용 하 여 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20f34-167">(These same policies can also be created by using local security policies.</span></span> <span data-ttu-id="20f34-168">그러나 이렇게 하면 모든 컴퓨터에서 동일한 절차를 반복 해야 합니다. 첫 번째 QoS 정책 집합 (오디오 및 비디오용)은 회의 서버, 애플리케이션 서버 및/또는 중재 서버 서비스를 실행 하는 비즈니스용 Skype 서버 컴퓨터에만 적용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="20f34-168">However, that requires you to repeat the same procedure on each and every computer.) Your initial set of QoS policies (one for audio and one for video) should be applied only to Skype for Business Server computers running the Conferencing server, Application server, and/or Mediation server services.</span></span> <span data-ttu-id="20f34-169">이러한 모든 컴퓨터가 동일한 Active Directory OU에 있는 경우 새 GPO (그룹 정책 개체)를 해당 OU에 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20f34-169">If all of these computers are located in the same Active Directory OU, you can simply assign the new Group Policy object (GPO) to that OU.</span></span> <span data-ttu-id="20f34-170">또는 다른 단계를 수행 하 여 새 정책을 지정 된 컴퓨터에 적용할 수 있습니다. 예를 들어 적절 한 컴퓨터를 보안 그룹에 배치 하 고 그룹 정책 보안 필터링을 사용 하 여 해당 보안 그룹에만 GPO를 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20f34-170">Alternatively, you can take other steps to target the new policy to the specified computers; for example, you can place the appropriate computers in a security group, then use Group Policy security filtering to apply the GPO just to that security group.</span></span>

<span data-ttu-id="20f34-171">오디오를 관리 하는 서비스 품질 정책을 만들려면 그룹 정책 관리가 설치 된 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="20f34-171">To create a Quality of Service policy for managing audio, log on to a computer where Group Policy Management has been installed.</span></span> <span data-ttu-id="20f34-172">그룹 정책 관리를 열고 ( **시작**을 클릭 하 고 **관리 도구**를 가리킨 다음 **그룹 정책 관리**클릭) 다음 절차를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="20f34-172">Open Group Policy Management (click **Start**, point to **Administrative Tools**, and then click **Group Policy Management**) and then complete the following procedure:</span></span>

1.  <span data-ttu-id="20f34-173">그룹 정책 관리에서 새 정책을 만들 컨테이너를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="20f34-173">In Group Policy Management, locate the container where the new policy should be created.</span></span> <span data-ttu-id="20f34-174">예를 들어 비즈니스용 skype 서버 컴퓨터를 모두 비즈니스용 Skype 서버 라는 OU에 배치 하면 비즈니스용 Skype 서버 OU에 새 정책이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="20f34-174">For example, if all your Skype for Business Server computers are located in an OU named Skype for Business Server, then the new policy should be created in the Skype for Business Server OU.</span></span>

2.  <span data-ttu-id="20f34-175">적절 한 컨테이너를 마우스 오른쪽 단추로 클릭 한 다음 **이 도메인에서 GPO 만들기를 클릭 하 고 여기에 연결**합니다.</span><span class="sxs-lookup"><span data-stu-id="20f34-175">Right-click the appropriate container, and then click **Create a GPO in this domain, and Link it here**.</span></span>

3.  <span data-ttu-id="20f34-176">**새 GPO** 대화 상자의 **이름** 상자에 새 그룹 정책 개체의 이름 (예: **비즈니스용 Skype Server QoS**)을 입력 한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="20f34-176">In the **New GPO** dialog box, type a name for the new Group Policy object in the **Name** box (for example, **Skype for Business Server QoS**), and then click **OK**.</span></span>

4.  <span data-ttu-id="20f34-177">새로 만든 정책을 마우스 오른쪽 단추로 클릭 한 다음 **편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="20f34-177">Right-click the newly-created policy, and then click **Edit**.</span></span>

5.  <span data-ttu-id="20f34-178">그룹 정책 관리 편집기에서 **컴퓨터 구성**, **정책**, **Windows 설정을**차례로 확장 하 고 **정책 기반 QoS**를 마우스 오른쪽 단추로 클릭 한 다음 **새 정책 만들기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="20f34-178">In the Group Policy Management Editor, expand **Computer Configuration**, expand **Policies**, expand **Windows Settings**, right-click **Policy-based QoS**, and then click **Create new policy**.</span></span>

6.  <span data-ttu-id="20f34-179">**정책 기반 QoS** 대화 상자의 열기 페이지에서 **이름** 상자에 새 정책의 이름 (예: **비즈니스용 Skype Server QoS**)을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="20f34-179">In the **Policy-based QoS** dialog box, on the opening page, type a name for the new policy (e.g., **Skype for Business Server QoS**) in the **Name** box.</span></span> <span data-ttu-id="20f34-180">**DSCP 값 지정** 을 선택 하 고 값을 **46**로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="20f34-180">Select **Specify DSCP Value** and set the value to **46**.</span></span> <span data-ttu-id="20f34-181">**아웃 바운드 스로틀 속도 지정** 을 선택 하지 않은 상태로 두고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="20f34-181">Leave **Specify Outbound Throttle Rate** unselected, and then click **Next**.</span></span>

7.  <span data-ttu-id="20f34-182">다음 페이지에서 **모든 응용 프로그램이** 선택 되어 있는지 확인 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="20f34-182">On the next page, make sure that **All applications** is selected, and then click **Next**.</span></span> <span data-ttu-id="20f34-183">이렇게 하면 모든 응용 프로그램이 지정한 포트 범위에서 지정 된 DSCP 코드를 갖는 패킷과 일치 시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20f34-183">This simply ensures that all applications will match packets from the specified port range with the specified DSCP code.</span></span>

8.  <span data-ttu-id="20f34-184">세 번째 페이지에서 **원본 ip 주소와 대상 ip 주소가** 모두 선택 되어 있는지 확인 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="20f34-184">On the third page, make sure that both **Any source IP address and Any destination IP address** are selected, and then click **Next**.</span></span> <span data-ttu-id="20f34-185">이러한 두 가지 설정은 해당 패킷과 전송 되는 컴퓨터 (ip 주소) 및 해당 패킷을 받을 컴퓨터 (IP 주소)에 관계 없이 패킷이 관리 됨을 보장 합니다.</span><span class="sxs-lookup"><span data-stu-id="20f34-185">These two settings ensure that packets will be managed regardless of which computer (IP address) sent those packets and which computer (IP address) will receive those packets.</span></span>

9.  <span data-ttu-id="20f34-186">4 페이지에서 **이 QoS 정책이 적용 되는 프로토콜 선택** 드롭다운 목록에서 **TCP 및 UDP** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="20f34-186">On page four, select **TCP and UDP** from the **Select the protocol this QoS policy applies to** dropdown list.</span></span> <span data-ttu-id="20f34-187">TCP (전송 제어 프로토콜) 및 UDP (사용자 데이터 그램 프로토콜)는 비즈니스용 Skype Server 및 해당 클라이언트 응용 프로그램에서 가장 일반적으로 사용 되는 두 가지 네트워킹 프로토콜입니다.</span><span class="sxs-lookup"><span data-stu-id="20f34-187">TCP (Transmission Control Protocol) and UDP (User Datagram Protocol) are the two networking protocols most-commonly used by Skype for Business Server and its client applications.</span></span>

10. <span data-ttu-id="20f34-188">**원본 포트 번호를 지정 하는**제목 아래에서 **이 원본 포트 또는 범위를**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="20f34-188">Under the heading **Specify the source port number**, select **From this source port or range**.</span></span> <span data-ttu-id="20f34-189">해당 텍스트 상자에 오디오 전송용으로 예약 된 포트 범위를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="20f34-189">In the accompanying text box, type the port range reserved for audio transmissions.</span></span> <span data-ttu-id="20f34-190">예를 들어 오디오 트래픽용 포트 57500를 통해 포트 49152를 예약한 경우이 형식을 사용 하 여 포트 범위를 입력 합니다 ( **49152:57500**).</span><span class="sxs-lookup"><span data-stu-id="20f34-190">For example, if you reserved ports 49152 through ports 57500 for audio traffic, enter the port range using this format: **49152:57500**.</span></span> <span data-ttu-id="20f34-191">**마침을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="20f34-191">Click **Finish**.</span></span>

> [!NOTE]  
> <span data-ttu-id="20f34-192">46의 DSCP 값은 일부 임의적인 반면, DSCP 46는 오디오 패킷을 표시 하는 데 자주 사용 되지만 오디오 통신에는 DSCP 46을 사용할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="20f34-192">The DSCP value of 46 is somewhat arbitrary: although DSCP 46 is often used for marking audio packets, you do not have to use DSCP 46 for audio communications.</span></span> <span data-ttu-id="20f34-193">이미 QoS를 구현 했으며 오디오에 다른 DSCP 코드를 사용 하는 경우 (예: DSCP 40) 동일한 코드를 사용 하도록 서비스 품질 정책을 구성 해야 합니다 (즉, 오디오의 경우 40).</span><span class="sxs-lookup"><span data-stu-id="20f34-193">If you have already implemented QoS and you are using a different DSCP code for audio (for example, DSCP 40), you should configure your Quality of Service policy to use that same code (i.e., 40 for audio).</span></span> <span data-ttu-id="20f34-194">지금 바로 서비스 품질을 구현 하는 경우 오디오 패킷을 표시 하는 데 일반적으로 사용 되는 DSCP 46을 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="20f34-194">If you are just now implementing Quality of Service, then it is recommended that you use DSCP 46 for audio, simply because that value is commonly used to mark audio packets.</span></span>

<span data-ttu-id="20f34-195">오디오 트래픽에 대 한 QoS 정책을 만든 후에는 비디오 트래픽에 대 한 두 번째 정책을 만들고, 선택적으로 응용 프로그램 공유 트래픽을 관리 하는 세 번째 정책을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="20f34-195">After you have created the QoS policy for audio traffic, you should then create a second policy for video traffic (and, optionally, a third policy for managing application sharing traffic).</span></span> <span data-ttu-id="20f34-196">비디오에 대 한 정책을 만들려면 오디오 정책을 만들 때 팔 로우 하는 기본 절차를 따르고 다음과 같이 대체 합니다.</span><span class="sxs-lookup"><span data-stu-id="20f34-196">To create a policy for video, follow the same basic procedure you followed when creating the audio policy, making these substitutions:</span></span>

  - <span data-ttu-id="20f34-197">다른 고유 정책 이름 (예: **비즈니스용 Skype Server 비디오**)을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="20f34-197">Use a different (and unique) policy name (for example, **Skype for Business Server Video**).</span></span>

  - <span data-ttu-id="20f34-198">DSCP 값을 46 대신 **34** 로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="20f34-198">Set the DSCP value to **34** instead of 46.</span></span> <span data-ttu-id="20f34-199">(DSCP 값 34를 사용 하지 않아도 된다는 점에 유의 하세요.</span><span class="sxs-lookup"><span data-stu-id="20f34-199">(Note that you do not have to use a DSCP value of 34.</span></span> <span data-ttu-id="20f34-200">유일한 요구 사항은 오디오에 사용 하는 것 보다 비디오에 다른 DSCP 값을 사용 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="20f34-200">The only requirement is that you use a different DSCP value for video than you used for audio.)</span></span>

  - <span data-ttu-id="20f34-201">이전에 구성한 비디오 트래픽에 대 한 포트 범위를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="20f34-201">Use the previously configured port range for video traffic.</span></span> <span data-ttu-id="20f34-202">예를 들어 비디오에 대 한 65535 57501를 예약한 포트를 사용 하는 경우 포트 범위를 this: **57501:65535**로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="20f34-202">For example, if you have reserved ports 57501 through 65535 for video, set the port range to this: **57501:65535**.</span></span>

<span data-ttu-id="20f34-203">응용 프로그램 공유 트래픽을 관리 하기 위한 정책을 만들려는 경우 세 번째 정책을 만들어 다음과 같이 대체 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="20f34-203">If you decide to create a policy for managing application sharing traffic, you must create a third policy, making the following substitutions:</span></span>

  - <span data-ttu-id="20f34-204">다른 고유 정책 이름 (예: **비즈니스용 Skype 서버 응용 프로그램 공유**)을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="20f34-204">Use a different (and unique) policy name (for example, **Skype for Business Server Application Sharing**).</span></span>

  - <span data-ttu-id="20f34-205">46 대신 DSCP 값을 **24** 로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="20f34-205">Set the DSCP value to **24** instead of 46.</span></span> <span data-ttu-id="20f34-206">(다시 한번, DSCP 값 24를 사용할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="20f34-206">(Again, you do not have to use a DSCP value of 24.</span></span> <span data-ttu-id="20f34-207">유일한 요구 사항은 오디오 또는 비디오에 사용 하는 것과는 다른 DSCP 값을 응용 프로그램 공유에 사용 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="20f34-207">The only requirement is that you use a different DSCP value for application sharing than you used for audio or for video.)</span></span>

  - <span data-ttu-id="20f34-208">이전에 구성한 비디오 트래픽에 대 한 포트 범위를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="20f34-208">Use the previously configured port range for video traffic.</span></span> <span data-ttu-id="20f34-209">예를 들어 응용 프로그램 공유에 대해 포트 40803 ~ 49151을 (를) 예약한 경우 포트 범위를 this: **40803:49151**로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="20f34-209">For example, if you have reserved ports 40803 through 49151 for application sharing, set the port range to this: **40803:49151**.</span></span>

<span data-ttu-id="20f34-210">만든 새 정책은 비즈니스용 Skype 서버 컴퓨터에서 그룹 정책을 새로 고칠 때까지 적용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="20f34-210">The new policies you have created will not take effect until Group Policy has been refreshed on your Skype for Business Server computers.</span></span> <span data-ttu-id="20f34-211">그룹 정책은 주기적으로 자체적으로 새로 고쳐지고 그룹 정책을 새로 고쳐야 하는 각 컴퓨터에서 다음 명령을 실행 하 여 즉시 새로 고칠 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20f34-211">Although Group Policy periodically refreshes on its own, you can force an immediate refresh by running the following command on each computer where Group Policy needs to be refreshed:</span></span>

    Gpupdate.exe /force

<span data-ttu-id="20f34-212">이 명령은 비즈니스용 Skype 서버 관리 셸에서 또는 관리자 자격 증명으로 실행 되는 명령 창 내에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20f34-212">This command can be run from within the Skype for Business Server Management Shell or from any command window that is running under administrator credentials.</span></span> <span data-ttu-id="20f34-213">명령 창을 관리자 자격 증명으로 실행 하려면 **시작**을 클릭 하 고 **명령 프롬프트**를 마우스 오른쪽 단추로 클릭 한 다음 **관리자 권한으로 실행**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="20f34-213">To run a command window under administrator credentials, click **Start**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span>

<span data-ttu-id="20f34-214">새 QoS 정책이 적용 되었는지 확인 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="20f34-214">To verify that the new QoS policies have been applied, do the following:</span></span>

1.  <span data-ttu-id="20f34-215">비즈니스용 Skype 서버 컴퓨터에서 **시작**을 클릭 한 다음 **실행**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="20f34-215">On a Skype for Business Server computer, click **Start**, and then click **Run**.</span></span>

2.  <span data-ttu-id="20f34-216">**실행** 대화 상자에서 **regedit**를 입력 한 다음 enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="20f34-216">In the **Run** dialog box, type **regedit**, and then press ENTER.</span></span>

3.  <span data-ttu-id="20f34-217">레지스트리 편집기에서 **컴퓨터**를 확장 하 고 **,\_HKEY\_LOCAL MACHINE**을 확장 하 고, **소프트웨어**, **정책**, **Microsoft**, **Windows**를 차례로 확장 한 다음 **QoS**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="20f34-217">In Registry Editor, expand **Computer**, expand **HKEY\_LOCAL\_MACHINE**, expand **SOFTWARE**, expand **Policies**, expand **Microsoft**, expand **Windows**, and then click **QoS**.</span></span> <span data-ttu-id="20f34-218">**Qos** 아래에는 방금 만든 각 QoS 정책에 대 한 레지스트리 키가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="20f34-218">Under **QoS** you should see registry keys for each of the QoS policies you just created.</span></span> <span data-ttu-id="20f34-219">예를 들어 새로운 정책 두 개 (비즈니스용 Skype Server 오디오 QoS와 다른 명명 된 비즈니스용 Skype Server 비디오 QoS)를 만든 경우 비즈니스용 Skype Server 오디오 QoS 및 비즈니스용 skype Server 비디오 QoS에 대 한 레지스트리 항목이 표시 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="20f34-219">For example, if you created two new policies (one named Skype for Business Server Audio QoS and the other named Skype for Business Server Video QoS), you should see registry entries for Skype for Business Server Audio QoS and Skype for Business Server Video QoS.</span></span>

<span data-ttu-id="20f34-220">네트워크 패킷이 적절 한 DSCP 값으로 표시 되도록 하려면 다음 절차를 완료 하 여 각 컴퓨터에 새 레지스트리 항목을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="20f34-220">To help ensure that network packets are marked with the appropriate DSCP value, you should also create a new registry entry on each computer by completing the following procedure:</span></span>

1.  <span data-ttu-id="20f34-221">**시작**을 클릭 한 다음 **실행**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="20f34-221">Click **Start**, and then click **Run**.</span></span>

2.  <span data-ttu-id="20f34-222">**실행** 대화 상자에서 **regedit**를 입력 한 다음 enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="20f34-222">In the **Run** dialog box, type **regedit**, and then press ENTER.</span></span>

3.  <span data-ttu-id="20f34-223">레지스트리 편집기에서 **\_HKEY\_LOCAL MACHINE**을 확장 하 고 **시스템**, **CurrentControlSet**를 차례로 확장 한 다음 **서비스**를 확장 한 다음 **Tcpip**를 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="20f34-223">In the Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **SYSTEM**, expand **CurrentControlSet**, expand **services**, and then expand **Tcpip**.</span></span>

4.  <span data-ttu-id="20f34-224">**Tcpip**를 마우스 오른쪽 단추로 클릭 하 고 **새로 만들기**를 가리킨 다음 **키**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="20f34-224">Right-click **Tcpip**, point to **New**, and then click **Key**.</span></span> <span data-ttu-id="20f34-225">새 레지스트리 키를 만들고 **QoS**를 입력 한 다음 enter 키를 눌러 키의 이름을 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="20f34-225">After the new registry key is created, type **QoS**, and then press ENTER to rename the key.</span></span>

5.  <span data-ttu-id="20f34-226">**QoS**를 마우스 오른쪽 단추로 클릭 하 고 **새로 만들기**를 가리킨 다음 **문자열 값**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="20f34-226">Right-click **QoS**, point to **New**, and then click **String Value**.</span></span> <span data-ttu-id="20f34-227">새 레지스트리 값을 만든 후에는 **NLA를 사용 하지 않음을**입력 하 고 enter 키를 눌러 값의 이름을 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="20f34-227">After the new registry value is created, type **Do not use NLA**, and then press ENTER to rename the value.</span></span>

6.  <span data-ttu-id="20f34-228">**NLA를 사용 하지 않음을**두 번 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="20f34-228">Double-click **Do not use NLA**.</span></span> <span data-ttu-id="20f34-229">**문자열 편집** 대화 상자의 **값 데이터** 상자에 **1** 을 입력 한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="20f34-229">In the **Edit String** dialog box, type **1** in the **Value data** box, and then click **OK**.</span></span>

7.  <span data-ttu-id="20f34-230">레지스트리 편집기를 닫고 컴퓨터를 다시 부팅 합니다.</span><span class="sxs-lookup"><span data-stu-id="20f34-230">Close the Registry Editor and reboot your computer.</span></span>
