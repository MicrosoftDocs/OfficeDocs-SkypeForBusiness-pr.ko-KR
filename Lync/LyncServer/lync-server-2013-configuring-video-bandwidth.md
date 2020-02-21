---
title: 'Lync Server 2013: 비디오 대역폭 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring video bandwidth in Lync Server
ms:assetid: 446bed91-b26f-4ab2-b2f5-36e6810b405b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204842(v=OCS.15)
ms:contentKeyID: 48183984
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8995f47ff1059921c324d71cbaca26fa47c50ca0
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42195651"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-video-bandwidth-in-lync-server-2013"></a><span data-ttu-id="721e7-102">Lync Server 2013에서 비디오 대역폭 구성</span><span class="sxs-lookup"><span data-stu-id="721e7-102">Configuring video bandwidth in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="721e7-103">_**마지막으로 수정 된 항목:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="721e7-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="721e7-104">Lync Server 2013에는 두 사용자 간 통화와 단체 회의를 위한 비디오 관리 설정이 몇 가지 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="721e7-104">Lync Server 2013 includes several settings for managing video for two-party calls and multiparty conferences.</span></span> <span data-ttu-id="721e7-105">Lync Server 2013를 배포할 때는 기본 설정이 조직에 적합 한지 여부를 평가 하 고 필요에 따라 수정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="721e7-105">When you deploy Lync Server 2013, you should evaluate whether the default settings are appropriate for your organization, and modify them as necessary.</span></span>

<span data-ttu-id="721e7-p102">이 섹션에 설명된 매개 변수는 두 사용자 간 통화 및 단체 회의 모두에 적용됩니다. 다음 cmdlet 중 하나를 사용하여 설정을 보거나 수정하십시오.</span><span class="sxs-lookup"><span data-stu-id="721e7-p102">The parameters described in this section apply to both two-party calls and multiparty conferencing. View or modify these settings by using one of the following cmdlets:</span></span>

  - <span data-ttu-id="721e7-108">**Get-csconferencingpolicy**</span><span class="sxs-lookup"><span data-stu-id="721e7-108">**Get-CsConferencingPolicy**</span></span>

  - <span data-ttu-id="721e7-109">**Get-csconferencingpolicy**</span><span class="sxs-lookup"><span data-stu-id="721e7-109">**Set-CsConferencingPolicy**</span></span>

  - <span data-ttu-id="721e7-110">**Get-csconferencingpolicy**</span><span class="sxs-lookup"><span data-stu-id="721e7-110">**New-CsConferencingPolicy**</span></span>

<span data-ttu-id="721e7-111">회의 정책에서 다음 설정을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="721e7-111">Verify the following settings in your conferencing policy:</span></span>

  - <span data-ttu-id="721e7-112">**VideoBitRateKb**   이 설정은 사용자가 보내는 비디오에 사용 되는 최대 비디오 비트 전송률 (kbps)을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="721e7-112">**VideoBitRateKb**   This setting specifies the maximum video bit rate in kilobits per second (kbps) used for video sent by a user.</span></span> <span data-ttu-id="721e7-113">기본값은 5000kbps입니다.</span><span class="sxs-lookup"><span data-stu-id="721e7-113">The default value is 50000 kbps.</span></span> <span data-ttu-id="721e7-114">유효한 값은 0부터 5000까지입니다.</span><span class="sxs-lookup"><span data-stu-id="721e7-114">Valid values are 0 to 50000.</span></span>
    
    <span data-ttu-id="721e7-115">이 설정은 기본 비디오 및 파노라마 비디오에 별개로 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="721e7-115">This setting applies separately to main video and panoramic video.</span></span>
    
    <span data-ttu-id="721e7-116">예: 2000을 지정 하는 경우 Lync Server는 기본 비디오 스트림에 대 한 2000 kbps와 파노라마 비디오 스트림에 대 한 2000 kbps를 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="721e7-116">Example: if you specify 2000 kbps, then Lync Server can send 2000 kbps for the main video stream and 2000 kbps for the panoramic video stream.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="721e7-117">Lync 2013 끝점에 대 한 최대 비디오 네트워크 대역폭은 기본 비디오용 8000 kbps, 파노라마 비디오용 2500 kbps입니다.</span><span class="sxs-lookup"><span data-stu-id="721e7-117">The maximum video network bandwidth for a Lync 2013 endpoint is 8000 kbps for the main video and 2500 kbps for panoramic video.</span></span> <span data-ttu-id="721e7-118">이러한 최대값은 여러 개의 비디오를 수신하거나 전송하는 경우에만 도달합니다.</span><span class="sxs-lookup"><span data-stu-id="721e7-118">These maximum values are reached only if multiple videos are received or sent.</span></span> <span data-ttu-id="721e7-119">자세한 내용은 <A href="lync-server-2013-network-bandwidth-requirements-for-media-traffic.md">Lync Server 2013의 미디어 트래픽에 대 한 네트워크 대역폭 요구 사항</A>에서 "미디어 트래픽 네트워크 사용" 섹션을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="721e7-119">For details, see the "Media Traffic Network Usage" section in <A href="lync-server-2013-network-bandwidth-requirements-for-media-traffic.md">Network bandwidth requirements for media traffic in Lync Server 2013</A>.</span></span> <span data-ttu-id="721e7-120">이 섹션에는 지원되는 모든 해상도에 대한 최대 및 일반 비디오 스트림 대역폭이 표시되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="721e7-120">This section lists the maximum and typical video stream bandwidth for all supported resolutions.</span></span>

    
    </div>

  - <span data-ttu-id="721e7-121">\*\*\*\*   Lync Server 2013의 새로운 설정인이 설정은 클라이언트에서 수신 되는 모든 비디오 스트림에 허용 되는 최대 비트 전송률 (초당 킬로 비트)을 지정 하는 TotalReceiveVideoBitRateKb입니다.</span><span class="sxs-lookup"><span data-stu-id="721e7-121">**TotalReceiveVideoBitRateKb**   This setting, which is new in Lync Server 2013, specifies the maximum allowed bitrate (in kilobits per second) for all the video streams received by a client.</span></span> <span data-ttu-id="721e7-122">즉, 파노라마 비디오 스트림을 제외한 클라이언트에서 수신할 수 있는 모든 비디오 스트림에 대 한 총 합계를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="721e7-122">That is, it specifies the combined total for all the video streams, except for panoramic video streams, that a client can receive.</span></span> <span data-ttu-id="721e7-123">예를 들어, 1500 kbps를 지정 하면 클라이언트가 최대 1500 kbps의 비디오를 받을 수 있으며,이는 여러 비디오 스트림 또는 단일 비디오 스트림으로 구성 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="721e7-123">For example, if you specify 1500 kbps, then a client can receive up to 1500 kbps of video, which may consist of multiple video streams or a single video stream.</span></span> <span data-ttu-id="721e7-124">이 설정은 Lync Server 2013 클라이언트에만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="721e7-124">This setting applies only to Lync Server 2013 clients.</span></span>
    
    <span data-ttu-id="721e7-p106">**TotalReceiveVideoBitRateKb**의 기본값은 50000kbps입니다. 갤러리 보기에 대한 **EnableMultiviewJoin** 설정이 True인 경우, **TotalReceiveVideoBitRateKb**는 420kbps 아래로 설정되지 않아야 합니다. 갤러리 보기에 대한 **EnableMultiviewJoin** 설정이 False인 경우, **TotalReceiveVideoBitRateKb**는 100kbps 아래로 설정되지 않아야 합니다. **EnableMultiviewJoin**이 True로 설정되었고 값을 420kbps 아래로 설정하면 값이 기본적으로 임계값으로 설정됩니다. 이 임계값은 사용자 경험 품질이 저하될 수 있는 잘못된 구성을 실수로 설정하지 않도록 방지합니다.</span><span class="sxs-lookup"><span data-stu-id="721e7-p106">The default value for **TotalReceiveVideoBitRateKb** is 50000 kbps. If the **EnableMultiviewJoin** setting for Gallery View is set to True, **TotalReceiveVideoBitRateKb** must not be set below 420 kbps. If the **EnableMultiviewJoin** setting for Gallery View is set to False, **TotalReceiveVideoBitRateKb** must not be set below 100 kbps. If **EnableMultiviewJoin** is set to True and you set the value below 420 kbps, the values will default to the threshold value. This threshold helps prevent accidental misconfiguration that might result in poor user experience.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="721e7-130"><STRONG>EnableMultiviewJoin</STRONG> 설정에 대 한 자세한 내용은 <A href="lync-server-2013-configuring-gallery-view.md">Lync Server 2013에서 갤러리 보기 구성을</A>참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="721e7-130">For details about the <STRONG>EnableMultiviewJoin</STRONG> setting, see <A href="lync-server-2013-configuring-gallery-view.md">Configuring Gallery View in Lync Server 2013</A>.</span></span>

    
    </div>

  - <span data-ttu-id="721e7-131">**MaxVideoConferencingResolution**   이 매개 변수는 lync server 2013 회의에서 lync server 2013 클라이언트에 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="721e7-131">**MaxVideoConferencingResolution**   This parameter is no longer used for Lync Server 2013 clients in Lync Server 2013 conferences.</span></span> <span data-ttu-id="721e7-132">Lync Server 2013 회의는이 섹션 앞부분에서 설명한 비트 전송률 컨트롤을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="721e7-132">Lync Server 2013 conferences use the bit rate controls described earlier in this section.</span></span> <span data-ttu-id="721e7-133">이 설정은 Lync Server 2013 회의에 참가 하는 레거시 클라이언트에 대해서도 계속 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="721e7-133">This setting is still used for legacy clients joining a Lync Server 2013 conference.</span></span> <span data-ttu-id="721e7-134">이 매개 변수는 Lync Server 2013에 있는 사용자가 구성한 전화 회의의 레거시 클라이언트에 허용 되는 최대 해상도를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="721e7-134">This parameter determines the maximum resolution allowed for legacy clients in conferences organized by users who are homed on Lync Server 2013.</span></span> <span data-ttu-id="721e7-135">즉, 레거시 클라이언트는 이전 버전의 Lync Server 또는 Office Communications Server에서와 동일 하 게 취급 됩니다.</span><span class="sxs-lookup"><span data-stu-id="721e7-135">That is, legacy clients are treated the same as they were in previous versions of Lync Server or Office Communications Server.</span></span>

<span data-ttu-id="721e7-p108">사용자에게 적용되는 회의 정책 설정 외에도 미디어 구성 설정을 평가하십시오. 다음 cmdlet 중 하나를 사용하여 설정을 보거나 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="721e7-p108">In addition to conferencing policy settings that apply to users, evaluate media configuration settings. View or modify these settings by using one of the following cmdlets:</span></span>

  - <span data-ttu-id="721e7-138">**Get-csmediaconfiguration**</span><span class="sxs-lookup"><span data-stu-id="721e7-138">**Get-CsMediaConfiguration**</span></span>

  - <span data-ttu-id="721e7-139">**Get-csmediaconfiguration**</span><span class="sxs-lookup"><span data-stu-id="721e7-139">**Set- CsMediaConfiguration**</span></span>

  - <span data-ttu-id="721e7-140">**Get-csmediaconfiguration**</span><span class="sxs-lookup"><span data-stu-id="721e7-140">**New- CsMediaConfiguration**</span></span>

<span data-ttu-id="721e7-141">다음 설정을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="721e7-141">Verify the following setting:</span></span>

  - <span data-ttu-id="721e7-142">**MaxVideoRateAllowed**   이 각 풀 설정은 클라이언트 끝점에서 비디오 신호가 전송 되는 최대 속도를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="721e7-142">**MaxVideoRateAllowed**   This per-pool setting specifies the maximum rate at which video signals will be transferred at the client endpoints.</span></span> <span data-ttu-id="721e7-143">이는 이전 버전의 Lync Server 클라이언트에만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="721e7-143">It applies only to previous versions of Lync Server clients.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="721e7-144">Lync Server 2013 클라이언트는이 설정을 무시 하 고 대신 회의 정책에서 TotalReceiveVideoBitRateKb 설정을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="721e7-144">Lync Server 2013 clients ignore this setting and use the TotalReceiveVideoBitRateKb setting in conferencing policy instead.</span></span>

    
    </div>
    
    <span data-ttu-id="721e7-p110">기본값은 HD720P입니다. 유효 값은 HD720p15M, VGA600K 및 CIF250K입니다.</span><span class="sxs-lookup"><span data-stu-id="721e7-p110">The default value is HD720P. Valid values are HD720p15M, VGA600K, and CIF250K.</span></span>
    
    <span data-ttu-id="721e7-147">예: 1500kbps를 지정한 경우 풀의 모든 레거시 클라이언트가 두 사람 간의 회의 또는 단체 회의에서 최대 1500kbps로 비디오를 수신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="721e7-147">Example: If you specify 1500 kbps, then all the legacy clients in the pool can receive up to 1500 kbps of video in two-party or multiparty conferences.</span></span>

<span data-ttu-id="721e7-148">다음 절차는 Lync Server 관리 셸을 사용 하 여이 섹션에서 설명 하는 설정을 수정 하는 예입니다.</span><span class="sxs-lookup"><span data-stu-id="721e7-148">The following procedures are examples of using Lync Server Management Shell to modify the settings described in this section.</span></span>

<div>

## <a name="to-modify-conferencing-policy-for-video-settings"></a><span data-ttu-id="721e7-149">비디오 설정에 대한 회의 정책을 수정하려면</span><span class="sxs-lookup"><span data-stu-id="721e7-149">To modify conferencing policy for video settings</span></span>

1.  <span data-ttu-id="721e7-150">**시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="721e7-150">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="721e7-151">명령줄에서 다음 cmdlet을 실행하여 회의 정책을 편집합니다.</span><span class="sxs-lookup"><span data-stu-id="721e7-151">At the command line, run the following cmdlet to edit conferencing policy:</span></span>
    
        Set-CsConferencingPolicy -Identity Pool01ConferencingPolicy -VideoBitRateKb 2000 -TotalReceiveVideoBitRateKb 2000 

</div>

<div>

## <a name="to-modify-media-configuration-for-legacy-clients"></a><span data-ttu-id="721e7-152">레거시 클라이언트에 대한 미디어 구성을 수정하려면</span><span class="sxs-lookup"><span data-stu-id="721e7-152">To modify media configuration for legacy clients</span></span>

1.  <span data-ttu-id="721e7-153">**시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="721e7-153">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="721e7-154">명령줄에서 다음 cmdlet을 실행하여 미디어 구성을 편집합니다.</span><span class="sxs-lookup"><span data-stu-id="721e7-154">At the command line, run the following cmdlet to edit the media configuration:</span></span>
    
        Set-CsMediaConfiguration -Identity site:Redmond01 -MaxVideoRateAllowed CIF250K

</div>

</div>

<span> </span>

</div>

</div>

</div>

