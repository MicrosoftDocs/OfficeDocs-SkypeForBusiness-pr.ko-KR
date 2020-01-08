---
title: 'Lync Server 2013: 비디오 대역폭 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring video bandwidth in Lync Server
ms:assetid: 446bed91-b26f-4ab2-b2f5-36e6810b405b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204842(v=OCS.15)
ms:contentKeyID: 48183984
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9ee374be85bc9427135ff89f3eb75acefd1cf5a8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980165"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-video-bandwidth-in-lync-server-2013"></a><span data-ttu-id="cc3f9-102">Lync Server 2013에서 비디오 대역폭 구성</span><span class="sxs-lookup"><span data-stu-id="cc3f9-102">Configuring video bandwidth in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cc3f9-103">_**마지막으로 수정한 주제:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="cc3f9-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="cc3f9-104">Lync Server 2013에는 두 개의 타사 통화와 단체 회의를 위한 비디오 관리 설정이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc3f9-104">Lync Server 2013 includes several settings for managing video for two-party calls and multiparty conferences.</span></span> <span data-ttu-id="cc3f9-105">Lync Server 2013을 배포 하는 경우 기본 설정이 조직에 적합 한지 평가 하 고 필요에 따라 수정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc3f9-105">When you deploy Lync Server 2013, you should evaluate whether the default settings are appropriate for your organization, and modify them as necessary.</span></span>

<span data-ttu-id="cc3f9-106">이 섹션에 설명 된 매개 변수는 두 개의 파티 통화와 단체 회의에 모두 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cc3f9-106">The parameters described in this section apply to both two-party calls and multiparty conferencing.</span></span> <span data-ttu-id="cc3f9-107">다음 cmdlet 중 하나를 사용 하 여 이러한 설정을 보거나 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc3f9-107">View or modify these settings by using one of the following cmdlets:</span></span>

  - <span data-ttu-id="cc3f9-108">**Get-CsConferencingPolicy**</span><span class="sxs-lookup"><span data-stu-id="cc3f9-108">**Get-CsConferencingPolicy**</span></span>

  - <span data-ttu-id="cc3f9-109">**Set-CsConferencingPolicy**</span><span class="sxs-lookup"><span data-stu-id="cc3f9-109">**Set-CsConferencingPolicy**</span></span>

  - <span data-ttu-id="cc3f9-110">**New-CsConferencingPolicy**</span><span class="sxs-lookup"><span data-stu-id="cc3f9-110">**New-CsConferencingPolicy**</span></span>

<span data-ttu-id="cc3f9-111">회의 정책에서 다음 설정을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc3f9-111">Verify the following settings in your conferencing policy:</span></span>

  - <span data-ttu-id="cc3f9-112">**VideoBitRateKb**   이 설정은 사용자가 보내는 비디오에 사용 되는 최대 비디오 비트 전송률을 kbps 단위로 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc3f9-112">**VideoBitRateKb**   This setting specifies the maximum video bit rate in kilobits per second (kbps) used for video sent by a user.</span></span> <span data-ttu-id="cc3f9-113">기본값은 5만 kbps입니다.</span><span class="sxs-lookup"><span data-stu-id="cc3f9-113">The default value is 50000 kbps.</span></span> <span data-ttu-id="cc3f9-114">유효한 값은 0 ~ 5만입니다.</span><span class="sxs-lookup"><span data-stu-id="cc3f9-114">Valid values are 0 to 50000.</span></span>
    
    <span data-ttu-id="cc3f9-115">이 설정은 기본 비디오 및 파노라마 비디오에 별도로 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cc3f9-115">This setting applies separately to main video and panoramic video.</span></span>
    
    <span data-ttu-id="cc3f9-116">예: 2000 kbps를 지정 하는 경우 Lync Server는 파노라마 비디오 스트림에 대 한 기본 비디오 스트림 및 2000 kbps에 대해 2000 kbps를 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc3f9-116">Example: if you specify 2000 kbps, then Lync Server can send 2000 kbps for the main video stream and 2000 kbps for the panoramic video stream.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="cc3f9-117">Lync 2013 끝점의 최대 비디오 네트워크 대역폭은 기본 비디오 2500와 파노라마 비디오의 경우 9kbps에 대 한 8000 kbps입니다.</span><span class="sxs-lookup"><span data-stu-id="cc3f9-117">The maximum video network bandwidth for a Lync 2013 endpoint is 8000 kbps for the main video and 2500 kbps for panoramic video.</span></span> <span data-ttu-id="cc3f9-118">이 최대 값에는 여러 개의 비디오를 받거나 전송 하는 경우에만 해당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cc3f9-118">These maximum values are reached only if multiple videos are received or sent.</span></span> <span data-ttu-id="cc3f9-119">자세한 내용은 <A href="lync-server-2013-network-bandwidth-requirements-for-media-traffic.md">Lync Server 2013의 미디어 트래픽에 대 한 네트워크 대역폭 요구 사항</A>에서 "미디어 트래픽 네트워크 사용량" 섹션을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="cc3f9-119">For details, see the "Media Traffic Network Usage" section in <A href="lync-server-2013-network-bandwidth-requirements-for-media-traffic.md">Network bandwidth requirements for media traffic in Lync Server 2013</A>.</span></span> <span data-ttu-id="cc3f9-120">이 섹션에는 지원 되는 모든 해상도에 대 한 최대 및 표준 비디오 스트림 대역폭이 나열 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cc3f9-120">This section lists the maximum and typical video stream bandwidth for all supported resolutions.</span></span>

    
    </div>

  - <span data-ttu-id="cc3f9-121">\*\*\*\*   Lync Server 2013의 새로운 설정인이 설정을 TotalReceiveVideoBitRateKb 클라이언트에서 받은 모든 비디오 스트림에 대해 허용 되는 최대 비트 전송률 (초당 킬로 비트)을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc3f9-121">**TotalReceiveVideoBitRateKb**   This setting, which is new in Lync Server 2013, specifies the maximum allowed bitrate (in kilobits per second) for all the video streams received by a client.</span></span> <span data-ttu-id="cc3f9-122">즉, 클라이언트가 수신할 수 있는 파노라마 비디오 스트림을 제외한 모든 비디오 스트림의 총 합계를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc3f9-122">That is, it specifies the combined total for all the video streams, except for panoramic video streams, that a client can receive.</span></span> <span data-ttu-id="cc3f9-123">예를 들어 1500 kbps를 지정 하는 경우, 클라이언트는 최대 1500 kbps의 비디오를 받을 수 있으며,이 경우 여러 비디오 스트림 또는 단일 비디오 스트림으로 구성 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc3f9-123">For example, if you specify 1500 kbps, then a client can receive up to 1500 kbps of video, which may consist of multiple video streams or a single video stream.</span></span> <span data-ttu-id="cc3f9-124">이 설정은 Lync Server 2013 클라이언트에만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cc3f9-124">This setting applies only to Lync Server 2013 clients.</span></span>
    
    <span data-ttu-id="cc3f9-125">**TotalReceiveVideoBitRateKb** 의 기본값은 5만 kbps입니다.</span><span class="sxs-lookup"><span data-stu-id="cc3f9-125">The default value for **TotalReceiveVideoBitRateKb** is 50000 kbps.</span></span> <span data-ttu-id="cc3f9-126">갤러리 보기에 대 한 **EnableMultiviewJoin** 설정이 True로 설정 되어 있으면 **TotalReceiveVideoBitRateKb** 420 kbps 미만으로 설정 되지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc3f9-126">If the **EnableMultiviewJoin** setting for Gallery View is set to True, **TotalReceiveVideoBitRateKb** must not be set below 420 kbps.</span></span> <span data-ttu-id="cc3f9-127">갤러리 보기의 **EnableMultiviewJoin** 설정이 False로 설정 된 경우 **TotalReceiveVideoBitRateKb** 는 100 kbps 미만으로 설정 되지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc3f9-127">If the **EnableMultiviewJoin** setting for Gallery View is set to False, **TotalReceiveVideoBitRateKb** must not be set below 100 kbps.</span></span> <span data-ttu-id="cc3f9-128">**EnableMultiviewJoin** 가 True로 설정 되 고 420 kbps 미만으로 설정 되 면 값이 기본적으로 threshold 값이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cc3f9-128">If **EnableMultiviewJoin** is set to True and you set the value below 420 kbps, the values will default to the threshold value.</span></span> <span data-ttu-id="cc3f9-129">이 임계값은 실수로 잘못 구성 되어 사용자 환경이 저하 될 수 있는 것을 방지 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cc3f9-129">This threshold helps prevent accidental misconfiguration that might result in poor user experience.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="cc3f9-130"><STRONG>EnableMultiviewJoin</STRONG> 설정에 대 한 자세한 내용은 <A href="lync-server-2013-configuring-gallery-view.md">Lync Server 2013의 갤러리 보기 구성을</A>참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="cc3f9-130">For details about the <STRONG>EnableMultiviewJoin</STRONG> setting, see <A href="lync-server-2013-configuring-gallery-view.md">Configuring Gallery View in Lync Server 2013</A>.</span></span>

    
    </div>

  - <span data-ttu-id="cc3f9-131">**MaxVideoConferencingResolution**   이 매개 변수는 lync server 2013 컨퍼런스의 lync server 2013 클라이언트에 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cc3f9-131">**MaxVideoConferencingResolution**   This parameter is no longer used for Lync Server 2013 clients in Lync Server 2013 conferences.</span></span> <span data-ttu-id="cc3f9-132">Lync Server 2013 컨퍼런스는이 섹션의 앞부분에서 설명한 비트 전송률 컨트롤을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc3f9-132">Lync Server 2013 conferences use the bit rate controls described earlier in this section.</span></span> <span data-ttu-id="cc3f9-133">이 설정은 Lync Server 2013 컨퍼런스에 참가 하는 레거시 클라이언트에도 계속 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cc3f9-133">This setting is still used for legacy clients joining a Lync Server 2013 conference.</span></span> <span data-ttu-id="cc3f9-134">이 매개 변수는 Lync Server 2013에 있는 사용자가 구성한 컨퍼런스에서 레거시 클라이언트에 허용 되는 최대 해상도를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc3f9-134">This parameter determines the maximum resolution allowed for legacy clients in conferences organized by users who are homed on Lync Server 2013.</span></span> <span data-ttu-id="cc3f9-135">즉, 레거시 클라이언트는 이전 버전의 Lync Server 또는 Office Communications Server와 동일 하 게 취급 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cc3f9-135">That is, legacy clients are treated the same as they were in previous versions of Lync Server or Office Communications Server.</span></span>

<span data-ttu-id="cc3f9-136">사용자에 게 적용 되는 회의 정책 설정 외에 미디어 구성 설정을 평가 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc3f9-136">In addition to conferencing policy settings that apply to users, evaluate media configuration settings.</span></span> <span data-ttu-id="cc3f9-137">다음 cmdlet 중 하나를 사용 하 여 이러한 설정을 보거나 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc3f9-137">View or modify these settings by using one of the following cmdlets:</span></span>

  - <span data-ttu-id="cc3f9-138">**Get-CsMediaConfiguration**</span><span class="sxs-lookup"><span data-stu-id="cc3f9-138">**Get-CsMediaConfiguration**</span></span>

  - <span data-ttu-id="cc3f9-139">**Set-CsMediaConfiguration**</span><span class="sxs-lookup"><span data-stu-id="cc3f9-139">**Set- CsMediaConfiguration**</span></span>

  - <span data-ttu-id="cc3f9-140">**새로운 CsMediaConfiguration**</span><span class="sxs-lookup"><span data-stu-id="cc3f9-140">**New- CsMediaConfiguration**</span></span>

<span data-ttu-id="cc3f9-141">다음 설정을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc3f9-141">Verify the following setting:</span></span>

  - <span data-ttu-id="cc3f9-142">**MaxVideoRateAllowed**   이 설정에 따라 클라이언트 끝점에서 비디오 신호를 전송할 최대 속도를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc3f9-142">**MaxVideoRateAllowed**   This per-pool setting specifies the maximum rate at which video signals will be transferred at the client endpoints.</span></span> <span data-ttu-id="cc3f9-143">이전 버전의 Lync Server 클라이언트에만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cc3f9-143">It applies only to previous versions of Lync Server clients.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="cc3f9-144">Lync Server 2013 클라이언트는이 설정을 무시 하 고 대신 회의 정책에서 TotalReceiveVideoBitRateKb 설정을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc3f9-144">Lync Server 2013 clients ignore this setting and use the TotalReceiveVideoBitRateKb setting in conferencing policy instead.</span></span>

    
    </div>
    
    <span data-ttu-id="cc3f9-145">기본 값은 HD720P입니다.</span><span class="sxs-lookup"><span data-stu-id="cc3f9-145">The default value is HD720P.</span></span> <span data-ttu-id="cc3f9-146">유효한 값은 HD720p15M, VGA600K 및 CIF250K입니다.</span><span class="sxs-lookup"><span data-stu-id="cc3f9-146">Valid values are HD720p15M, VGA600K, and CIF250K.</span></span>
    
    <span data-ttu-id="cc3f9-147">예: 1500 kbps를 지정 하는 경우 풀의 모든 레거시 클라이언트는 두 사람이 나 단체 회의에서 최대 1500 kbps의 비디오를 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc3f9-147">Example: If you specify 1500 kbps, then all the legacy clients in the pool can receive up to 1500 kbps of video in two-party or multiparty conferences.</span></span>

<span data-ttu-id="cc3f9-148">다음 절차에서는 Lync Server Management Shell을 사용 하 여이 섹션에서 설명 하는 설정을 수정 하는 예를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="cc3f9-148">The following procedures are examples of using Lync Server Management Shell to modify the settings described in this section.</span></span>

<div>

## <a name="to-modify-conferencing-policy-for-video-settings"></a><span data-ttu-id="cc3f9-149">비디오 설정에 대 한 회의 정책을 수정 하려면</span><span class="sxs-lookup"><span data-stu-id="cc3f9-149">To modify conferencing policy for video settings</span></span>

1.  <span data-ttu-id="cc3f9-150">Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc3f9-150">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="cc3f9-151">명령줄에서 다음 cmdlet을 실행 하 여 회의 정책을 편집 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc3f9-151">At the command line, run the following cmdlet to edit conferencing policy:</span></span>
    
        Set-CsConferencingPolicy -Identity Pool01ConferencingPolicy -VideoBitRateKb 2000 -TotalReceiveVideoBitRateKb 2000 

</div>

<div>

## <a name="to-modify-media-configuration-for-legacy-clients"></a><span data-ttu-id="cc3f9-152">레거시 클라이언트에 대 한 미디어 구성을 수정 하려면</span><span class="sxs-lookup"><span data-stu-id="cc3f9-152">To modify media configuration for legacy clients</span></span>

1.  <span data-ttu-id="cc3f9-153">Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc3f9-153">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="cc3f9-154">명령줄에서 다음 cmdlet을 실행 하 여 미디어 구성을 편집 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc3f9-154">At the command line, run the following cmdlet to edit the media configuration:</span></span>
    
        Set-CsMediaConfiguration -Identity site:Redmond01 -MaxVideoRateAllowed CIF250K

</div>

</div>

<span> </span>

</div>

</div>

</div>

