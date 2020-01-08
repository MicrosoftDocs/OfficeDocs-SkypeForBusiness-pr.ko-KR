---
title: 'Lync Server 2013: Lync 클라이언트 영상 요구 사항'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Lync client video requirements
ms:assetid: 8f68f4c2-3194-487c-bd2f-fbe71ba8ad70
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688132(v=OCS.15)
ms:contentKeyID: 49733731
ms.date: 01/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 56743abd386cb59b177806eed3d441aaf587ccce
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984581"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-client-video-requirements-for-lync-server-2013"></a><span data-ttu-id="cb09b-102">Lync Server 2013의 lync 클라이언트 비디오 요구 사항</span><span class="sxs-lookup"><span data-stu-id="cb09b-102">Lync client video requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cb09b-103">_**마지막으로 수정한 주제:** 2016-01-29_</span><span class="sxs-lookup"><span data-stu-id="cb09b-103">_**Topic Last Modified:** 2016-01-29_</span></span>

<span data-ttu-id="cb09b-104">이 섹션에서는 Lync 2013 영상 통화에 대 한 비디오 하드웨어 지원 및 다양 한 컴퓨터, 태블릿 및 모바일 장치 구성에 필요한 비디오 품질을 확인 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb09b-104">This section describes video hardware support for Lync 2013 video calls and describes how to determine the expected video quality for various computer, tablet, and mobile device configurations.</span></span>

<div>

## <a name="windows-desktop-and-tablet-video-requirements-and-capabilities"></a><span data-ttu-id="cb09b-105">Windows 데스크톱 및 태블릿 비디오 요구 사항 및 기능</span><span class="sxs-lookup"><span data-stu-id="cb09b-105">Windows Desktop and Tablet Video Requirements and Capabilities</span></span>

<span data-ttu-id="cb09b-106">Lync 2013는 H. 264/MPEG-4/4 부 고급 비디오 코딩 표준을 기반으로 비디오 인코딩 및 디코딩에 대 한 하드웨어 가속을 소개 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb09b-106">Lync 2013 introduces hardware acceleration for video encoding and decoding based on the H.264/MPEG-4 Part 10 Advanced Video Coding standard.</span></span> <span data-ttu-id="cb09b-107">이 기능을 사용 하면 CPU 클럭 속도가 낮은 컴퓨터에서 더 높은 해상도의 인코딩 및 디코딩을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb09b-107">This feature allows computers with lower CPU clock speeds to encode and decode higher resolution video.</span></span> <span data-ttu-id="cb09b-108">비디오 하드웨어 요구 사항은 컴퓨터 구성과 비디오 해상도에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="cb09b-108">Video hardware requirements vary depending on the computer configuration and the video resolution wanted.</span></span>

<div>

## <a name="video-hardware-requirements"></a><span data-ttu-id="cb09b-109">비디오 하드웨어 요구 사항</span><span class="sxs-lookup"><span data-stu-id="cb09b-109">Video Hardware Requirements</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cb09b-110">기능</span><span class="sxs-lookup"><span data-stu-id="cb09b-110">Feature</span></span></th>
<th><span data-ttu-id="cb09b-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="cb09b-111">Requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cb09b-112">DirectX 비디오 가속 (DXVA)을 사용 하는 하드웨어 가속 H/264 디코딩</span><span class="sxs-lookup"><span data-stu-id="cb09b-112">Hardware accelerated H.264 decoding using DirectX Video Acceleration (DXVA)</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="cb09b-113">그래픽 카드는 DirectX 9.0를 지원 해야 하며 DXVA2_ModeH264_VLD_NoFGT 디코딩 모드를 노출 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb09b-113">Graphics card must support DirectX 9.0 and must expose the DXVA2_ModeH264_VLD_NoFGT decoding mode.</span></span></p></li>
<li><p><span data-ttu-id="cb09b-114">최신 그래픽 카드 드라이버를 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb09b-114">The latest graphics card driver must be installed.</span></span></p></li>
</ul>
<div>

> [!NOTE]  
> <span data-ttu-id="cb09b-115">디코딩 모드에 대 한 자세한 내용은 <A href="http://go.microsoft.com/fwlink/p/?linkid=268530">http://go.microsoft.com/fwlink/p/?LinkId=268530</A>을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="cb09b-115">For details about decoding modes, see <A href="http://go.microsoft.com/fwlink/p/?linkid=268530">http://go.microsoft.com/fwlink/p/?LinkId=268530</A>.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cb09b-116">하드웨어 가속 H. 264 인코딩: 칩셋 요구 사항</span><span class="sxs-lookup"><span data-stu-id="cb09b-116">Hardware accelerated H.264 encoding: Chipset Requirements</span></span></p></td>
<td><p><span data-ttu-id="cb09b-117">다음과 같은 Intel 하드웨어 가속 비디오 인코딩 솔루션이 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cb09b-117">The following Intel hardware accelerated video encoding solutions are supported:</span></span></p>
<ul>
<li><p><span data-ttu-id="cb09b-118">두번째 및 세번째 세대 Intel HD 그래픽 2000, 2500, 3000, 4000 칩셋 (또는 이후 버전)에서 통합 하드웨어 비디오 인코더를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb09b-118">Second and third generation Intel HD Graphics 2000, 2500, 3000, and 4000 chipsets (or later versions) with integrated hardware video encoders.</span></span> <span data-ttu-id="cb09b-119">Intel HD 그래픽 드라이버 15.28.9.2884 설치 또는 다음을 포함 하는 최신 드라이버가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb09b-119">Installation of the Intel HD Graphics driver 15.28.9.2884 or the latest driver containing the following is required:</span></span></p>
<ul>
<li><p><span data-ttu-id="cb09b-120">디스플레이 드라이버 9.17.10.2884 또는 최신 드라이버</span><span class="sxs-lookup"><span data-stu-id="cb09b-120">Display driver 9.17.10.2884 or the latest driver</span></span></p></li>
<li><p><span data-ttu-id="cb09b-121">HMFT (하드웨어 media foundation transform) 버전 3.12.10.31 또는 최신 HMFT</span><span class="sxs-lookup"><span data-stu-id="cb09b-121">Hardware media foundation transform (HMFT) version 3.12.10.31 or the latest HMFT</span></span></p></li>
</ul></li>
</ul>
<p><span data-ttu-id="cb09b-122">다음 AMD 하드웨어 가속 비디오 인코딩 솔루션이 지원 됩니다 (Lync Server 2013에 대 한 CU1 업데이트 필요).</span><span class="sxs-lookup"><span data-stu-id="cb09b-122">The following AMD hardware accelerated video encoding solutions are supported (requires CU1 Updates for Lync Server 2013):</span></span></p>
<ul>
<li><p><span data-ttu-id="cb09b-123">Amd 시리즈 가속 프로세서의 통합 가속 처리 장치 및 여러 개의 개별 그래픽 카드에서 사용할 수 있는 AMD 비디오 코덱 엔진.</span><span class="sxs-lookup"><span data-stu-id="cb09b-123">AMD Video Codec Engine, which is available in several discrete graphics cards and in integrated accelerated processing units of AMD A-Series Accelerated Processors.</span></span> <span data-ttu-id="cb09b-124">AMD 비디오 코덱 엔진 드라이버 9.12.0.0 이상을 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb09b-124">The AMD Video Codec Engine driver 9.12.0.0 or higher must be installed.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cb09b-125">하드웨어 가속 H. 264 인코딩: 카메라 요구 사항</span><span class="sxs-lookup"><span data-stu-id="cb09b-125">Hardware accelerated H.264 encoding: Camera Requirements</span></span></p></td>
<td><p><span data-ttu-id="cb09b-126">UVC (USB Video Class) 사양 버전 1.5을 준수 하는 통합 된 H-264 하드웨어 인코더가 USB 비디오 카메라</span><span class="sxs-lookup"><span data-stu-id="cb09b-126">USB video cameras with integrated H.264 hardware encoder that conforms to the USB Video Class (UVC) specification version 1.5.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="cb09b-127">Lync 2013는 uvc 1.5에 대 한 지원을 포함 하는 Windows 8 또는 Windows 8.1을 사용 하 여 UVC 1.5 카메라를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb09b-127">Lync 2013 supports UVC 1.5 cameras with Windows 8 or Windows 8.1, which includes support for UVC 1.5.</span></span> <span data-ttu-id="cb09b-128">Windows 7에는 UVC 1.5에 대 한 지원이 포함 되어 있지 않으므로 Lync 2013에서는 UVC 1.5 카메라가 하드웨어 인코딩 지원이 없는 일반 카메라로 처리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cb09b-128">Because Windows 7 does not include support for UVC 1.5, Lync 2013 treats UVC 1.5 cameras as regular cameras with no hardware encoding support.</span></span>


</div></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="determining-h264-video-encoding-and-decoding-capabilities"></a><span data-ttu-id="cb09b-129">H/264 비디오 인코딩 및 디코딩 기능 확인</span><span class="sxs-lookup"><span data-stu-id="cb09b-129">Determining H.264 Video Encoding and Decoding Capabilities</span></span>

<span data-ttu-id="cb09b-130">일반적으로 특정 컴퓨터 구성의 최대 인코딩 및 디코딩 기능을 결정 하는 네 가지 주요 요인이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb09b-130">Generally, there are four major factors that determine the maximum encoding and decoding capability of a particular computer configuration:</span></span>

  - <span data-ttu-id="cb09b-131">DXVA를 사용 하 여 하드웨어 가속 디코딩 지원</span><span class="sxs-lookup"><span data-stu-id="cb09b-131">Support for hardware accelerated decoding by using DXVA</span></span>

  - <span data-ttu-id="cb09b-132">하드웨어 가속 인코딩 지원</span><span class="sxs-lookup"><span data-stu-id="cb09b-132">Support for hardware accelerated encoding</span></span>

  - <span data-ttu-id="cb09b-133">실제 코어 수</span><span class="sxs-lookup"><span data-stu-id="cb09b-133">Number of physical cores</span></span>

  - <span data-ttu-id="cb09b-134">WEI (Windows 체험 지 인덱스)</span><span class="sxs-lookup"><span data-stu-id="cb09b-134">Windows Experience Index (WEI)</span></span>

<span data-ttu-id="cb09b-135">Windows 시스템 평가 도구 (WinSAT)는 WEI를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb09b-135">The Windows System Assessment Tool (WinSAT) determines the WEI.</span></span> <span data-ttu-id="cb09b-136">WinSAT 도구를 실행 하면% windir%\\성능\\WinSAT\\데이터 저장소 디렉터리에 있는 컴퓨터에 공식적인 평가 XML 문서가 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cb09b-136">When you run the WinSAT tool, it generates a Formal.Assessment XML document on the computer in the %windir%\\Performance\\WinSAT\\DataStore directory.</span></span> <span data-ttu-id="cb09b-137">이 XML 파일에는 인코딩 및 디코딩 기능을 결정 하는 데 특히 중요 한 다음 두 가지 점수가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb09b-137">This XML file contains the following two scores that are of particular importance for determining encoding and decoding capabilities:</span></span>

  - <span data-ttu-id="cb09b-138">VideoEncodeScore는 컴퓨터의 소프트웨어 기반 비디오 인코딩 기능을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="cb09b-138">The VideoEncodeScore indicates the software-based video encoding capability of the computer.</span></span>

  - <span data-ttu-id="cb09b-139">GraphicsScore 값은 컴퓨터의 하드웨어 가속 인코딩 기능을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="cb09b-139">The GraphicsScore value indicates the hardware accelerated encoding capability of the computer.</span></span>

<span data-ttu-id="cb09b-140">다음 세 가지 표에서는 지 원하는 하드웨어 가속에 따라 다양 한 PC 유형의 최대 인코딩 및 디코딩 기능에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb09b-140">The following three tables explain the maximum encoding and decoding capability for different PC types depending on what hardware acceleration they support.</span></span> <span data-ttu-id="cb09b-141">640x360 이상 해상도의 경우 지원 되는 최대 프레임 속도는 초당 30 프레임 (fps)입니다.</span><span class="sxs-lookup"><span data-stu-id="cb09b-141">For resolutions of 640x360 and higher, the maximum supported frame rate is 30 frames per second (fps).</span></span> <span data-ttu-id="cb09b-142">640x360 보다 낮은 해상도의 경우 지원 되는 최대 프레임 속도는 15fps입니다.</span><span class="sxs-lookup"><span data-stu-id="cb09b-142">For resolutions lower than 640x360, the maximum supported frame rate is 15 fps.</span></span>

### <a name="computer-without-dxva-and-without-hardware-accelerated-encoder"></a><span data-ttu-id="cb09b-143">DXVA 및 하드웨어 가속 인코더가 없는 컴퓨터</span><span class="sxs-lookup"><span data-stu-id="cb09b-143">Computer Without DXVA And Without Hardware Accelerated Encoder</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cb09b-144">사용할 수 있는 인코더 해상도</span><span class="sxs-lookup"><span data-stu-id="cb09b-144">Capable Encoder Resolution</span></span></th>
<th><span data-ttu-id="cb09b-145">지원 되는 디코더 해상도</span><span class="sxs-lookup"><span data-stu-id="cb09b-145">Capable Decoder Resolution</span></span></th>
<th><span data-ttu-id="cb09b-146">요구 사항</span><span class="sxs-lookup"><span data-stu-id="cb09b-146">Requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cb09b-147">424x240</span><span class="sxs-lookup"><span data-stu-id="cb09b-147">424x240</span></span></p></td>
<td><p><span data-ttu-id="cb09b-148">424x240 (640x360에만 해당 시나리오의 경우 15fps)</span><span class="sxs-lookup"><span data-stu-id="cb09b-148">424x240 (640x360 at 15fps for receive only scenarios)</span></span></p></td>
<td><p><span data-ttu-id="cb09b-149">1 코어 및 VideoEncodeScore ≥ 4.0</span><span class="sxs-lookup"><span data-stu-id="cb09b-149">1 Core and VideoEncodeScore ≥ 4.0</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cb09b-150">640x360</span><span class="sxs-lookup"><span data-stu-id="cb09b-150">640x360</span></span></p></td>
<td><p><span data-ttu-id="cb09b-151">640x360</span><span class="sxs-lookup"><span data-stu-id="cb09b-151">640x360</span></span></p></td>
<td><p><span data-ttu-id="cb09b-152">2 코어 및 VideoEncodeScore ≥ 4.5</span><span class="sxs-lookup"><span data-stu-id="cb09b-152">2 Cores and VideoEncodeScore ≥ 4.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cb09b-153">640x360</span><span class="sxs-lookup"><span data-stu-id="cb09b-153">640x360</span></span></p></td>
<td><p><span data-ttu-id="cb09b-154">1280x720</span><span class="sxs-lookup"><span data-stu-id="cb09b-154">1280x720</span></span></p></td>
<td><p><span data-ttu-id="cb09b-155">2 코어 및 VideoEncodeScore ≥ 4.5</span><span class="sxs-lookup"><span data-stu-id="cb09b-155">2 Cores and VideoEncodeScore ≥ 4.5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cb09b-156">640x360</span><span class="sxs-lookup"><span data-stu-id="cb09b-156">640x360</span></span></p></td>
<td><p><span data-ttu-id="cb09b-157">1920x1080</span><span class="sxs-lookup"><span data-stu-id="cb09b-157">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="cb09b-158">4 코어 및 VideoEncodeScore ≥ 4.5</span><span class="sxs-lookup"><span data-stu-id="cb09b-158">4 Cores and VideoEncodeScore ≥ 4.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cb09b-159">1280x720</span><span class="sxs-lookup"><span data-stu-id="cb09b-159">1280x720</span></span></p></td>
<td><p><span data-ttu-id="cb09b-160">1280x720</span><span class="sxs-lookup"><span data-stu-id="cb09b-160">1280x720</span></span></p></td>
<td><p><span data-ttu-id="cb09b-161">4 코어 및 VideoEncodeScore ≥ 7.3</span><span class="sxs-lookup"><span data-stu-id="cb09b-161">4 Cores and VideoEncodeScore ≥ 7.3</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cb09b-162">1280x720</span><span class="sxs-lookup"><span data-stu-id="cb09b-162">1280x720</span></span></p></td>
<td><p><span data-ttu-id="cb09b-163">1920x1080</span><span class="sxs-lookup"><span data-stu-id="cb09b-163">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="cb09b-164">4 코어 및 VideoEncodeScore ≥ 7.3</span><span class="sxs-lookup"><span data-stu-id="cb09b-164">4 Cores and VideoEncodeScore ≥ 7.3</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cb09b-165">1920x1080</span><span class="sxs-lookup"><span data-stu-id="cb09b-165">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="cb09b-166">1920x1080</span><span class="sxs-lookup"><span data-stu-id="cb09b-166">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="cb09b-167">해당 없음</span><span class="sxs-lookup"><span data-stu-id="cb09b-167">N/A</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="computer-with-dxva-but-without-hardware-accelerated-encoder"></a><span data-ttu-id="cb09b-168">DXVA 있지만 하드웨어 가속 인코더가 없는 컴퓨터</span><span class="sxs-lookup"><span data-stu-id="cb09b-168">Computer With DXVA But Without Hardware Accelerated Encoder</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cb09b-169">사용할 수 있는 인코더 해상도</span><span class="sxs-lookup"><span data-stu-id="cb09b-169">Capable Encoder Resolution</span></span></th>
<th><span data-ttu-id="cb09b-170">지원 되는 디코더 해상도</span><span class="sxs-lookup"><span data-stu-id="cb09b-170">Capable Decoder Resolution</span></span></th>
<th><span data-ttu-id="cb09b-171">요구 사항</span><span class="sxs-lookup"><span data-stu-id="cb09b-171">Requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cb09b-172">424x240</span><span class="sxs-lookup"><span data-stu-id="cb09b-172">424x240</span></span></p></td>
<td><p><span data-ttu-id="cb09b-173">1920x1080</span><span class="sxs-lookup"><span data-stu-id="cb09b-173">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="cb09b-174">1 코어 및 VideoEncodeScore ≥ 3.0</span><span class="sxs-lookup"><span data-stu-id="cb09b-174">1 Core and VideoEncodeScore ≥ 3.0</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cb09b-175">640x360</span><span class="sxs-lookup"><span data-stu-id="cb09b-175">640x360</span></span></p></td>
<td><p><span data-ttu-id="cb09b-176">1920x1080</span><span class="sxs-lookup"><span data-stu-id="cb09b-176">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="cb09b-177">2 코어 및 VideoEncodeScore ≥ 4.5</span><span class="sxs-lookup"><span data-stu-id="cb09b-177">2 Cores and VideoEncodeScore ≥ 4.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cb09b-178">960x540</span><span class="sxs-lookup"><span data-stu-id="cb09b-178">960x540</span></span></p></td>
<td><p><span data-ttu-id="cb09b-179">1920x1080</span><span class="sxs-lookup"><span data-stu-id="cb09b-179">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="cb09b-180">2 코어 및 VideoEncodeScore ≥ 6.0</span><span class="sxs-lookup"><span data-stu-id="cb09b-180">2 Cores and VideoEncodeScore ≥ 6.0</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cb09b-181">1280x720</span><span class="sxs-lookup"><span data-stu-id="cb09b-181">1280x720</span></span></p></td>
<td><p><span data-ttu-id="cb09b-182">1920x1080</span><span class="sxs-lookup"><span data-stu-id="cb09b-182">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="cb09b-183">4 코어 및 VideoEncodeScore ≥ 6.7</span><span class="sxs-lookup"><span data-stu-id="cb09b-183">4 Cores and VideoEncodeScore ≥ 6.7</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cb09b-184">1920x1080</span><span class="sxs-lookup"><span data-stu-id="cb09b-184">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="cb09b-185">1920x1080</span><span class="sxs-lookup"><span data-stu-id="cb09b-185">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="cb09b-186">4 코어 및 VideoEncodeScore ≥ 8.2</span><span class="sxs-lookup"><span data-stu-id="cb09b-186">4 Cores and VideoEncodeScore ≥ 8.2</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="cb09b-187">Windows 7의 WinSAT 점수는 최대 7.9으로 제한 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cb09b-187">The WinSAT score on Windows 7 is limited to a maximum of 7.9.</span></span> <span data-ttu-id="cb09b-188">따라서 하드웨어 가속 인코더가 없는 컴퓨터에 대 한 인코딩 접근 권한 값은 Windows 8 또는 Windows 8.1 에서만 가능 하며,이는 최대 WinSAT 점수가 9.9입니다.</span><span class="sxs-lookup"><span data-stu-id="cb09b-188">Therefore, the encoding capability for a computer without a hardware accelerated encoder can only be achieved on Windows 8 or Windows 8.1, where the maximum WinSAT score is 9.9.</span></span>



</div>

### <a name="computer-with-dxva-and-with-intel-hd-graphics-hardware-accelerated-encoder"></a><span data-ttu-id="cb09b-189">DXVA 및 Intel HD 그래픽 하드웨어 가속 인코더를 사용 하는 컴퓨터</span><span class="sxs-lookup"><span data-stu-id="cb09b-189">Computer With DXVA And With Intel HD Graphics Hardware Accelerated Encoder</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cb09b-190">사용할 수 있는 인코더 해상도</span><span class="sxs-lookup"><span data-stu-id="cb09b-190">Capable Encoder Resolution</span></span></th>
<th><span data-ttu-id="cb09b-191">지원 되는 디코더 해상도</span><span class="sxs-lookup"><span data-stu-id="cb09b-191">Capable Decoder Resolution</span></span></th>
<th><span data-ttu-id="cb09b-192">요구 사항</span><span class="sxs-lookup"><span data-stu-id="cb09b-192">Requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cb09b-193">1280x720</span><span class="sxs-lookup"><span data-stu-id="cb09b-193">1280x720</span></span></p></td>
<td><p><span data-ttu-id="cb09b-194">1920x1080</span><span class="sxs-lookup"><span data-stu-id="cb09b-194">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="cb09b-195">모든 2 차 및 3 세대 Intel HD 그래픽</span><span class="sxs-lookup"><span data-stu-id="cb09b-195">All 2nd and 3rd generation Intel HD Graphics</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cb09b-196">1920x1080</span><span class="sxs-lookup"><span data-stu-id="cb09b-196">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="cb09b-197">1920x1080</span><span class="sxs-lookup"><span data-stu-id="cb09b-197">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="cb09b-198">2 차 및 3 세대 Intel HD 그래픽 및 GraphicsScore ≥ 5.0</span><span class="sxs-lookup"><span data-stu-id="cb09b-198">2nd and 3rd generation Intel HD Graphics and GraphicsScore ≥ 5.0</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<div>

## <a name="mobile-device-video-capabilities"></a><span data-ttu-id="cb09b-199">모바일 장치 영상 기능</span><span class="sxs-lookup"><span data-stu-id="cb09b-199">Mobile Device Video Capabilities</span></span>

<span data-ttu-id="cb09b-200">다음 표에서는 지원 되는 모바일 장치의 최대 비디오 기능에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb09b-200">The following table describes the maximum video capabilities for supported mobile devices.</span></span> <span data-ttu-id="cb09b-201">모바일 장치 지원에 대 한 자세한 내용은 [Lync Server 2013의 모바일 클라이언트 계획](lync-server-2013-planning-for-mobile-clients.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="cb09b-201">For more information about mobile device support, see [Planning for mobile clients in Lync Server 2013](lync-server-2013-planning-for-mobile-clients.md).</span></span>


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
<th><span data-ttu-id="cb09b-202">기능</span><span class="sxs-lookup"><span data-stu-id="cb09b-202">Feature</span></span></th>
<th><span data-ttu-id="cb09b-203">Windows Phone</span><span class="sxs-lookup"><span data-stu-id="cb09b-203">Windows Phone</span></span></th>
<th><span data-ttu-id="cb09b-204">iPhone</span><span class="sxs-lookup"><span data-stu-id="cb09b-204">iPhone</span></span></th>
<th><span data-ttu-id="cb09b-205">iPad</span><span class="sxs-lookup"><span data-stu-id="cb09b-205">iPad</span></span></th>
<th><span data-ttu-id="cb09b-206">Android</span><span class="sxs-lookup"><span data-stu-id="cb09b-206">Android</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cb09b-207">H-264 인코딩 최대 해상도</span><span class="sxs-lookup"><span data-stu-id="cb09b-207">H.264 encoding maximum resolution</span></span></p></td>
<td><p><span data-ttu-id="cb09b-208">비디오</span><span class="sxs-lookup"><span data-stu-id="cb09b-208">VGA</span></span></p></td>
<td><p><span data-ttu-id="cb09b-209">QVGA: iPhone 4S</span><span class="sxs-lookup"><span data-stu-id="cb09b-209">QVGA: iPhone 4S</span></span></p>
<p><span data-ttu-id="cb09b-210">VGA: iPhone 5</span><span class="sxs-lookup"><span data-stu-id="cb09b-210">VGA: iPhone 5</span></span></p>
<p><span data-ttu-id="cb09b-211">720p: iPhone 5S 이상</span><span class="sxs-lookup"><span data-stu-id="cb09b-211">720p: iPhone 5S and later</span></span></p></td>
<td><p><span data-ttu-id="cb09b-212">VGA: iPad 2 이상/이후/iPad 미니 1 이상</span><span class="sxs-lookup"><span data-stu-id="cb09b-212">VGA: iPad 2 and later/iPad mini 1 and later</span></span></p>
<p><span data-ttu-id="cb09b-213">720p: iPad Air/iPad 미니 2/iPad 이상</span><span class="sxs-lookup"><span data-stu-id="cb09b-213">720p: iPad Air/iPad mini 2/iPad Pro and later</span></span></p></td>
<td><p><span data-ttu-id="cb09b-214">장치 모델에 따라 최대 VGA까지</span><span class="sxs-lookup"><span data-stu-id="cb09b-214">Up to VGA depending on device model</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cb09b-215">H. 264 디코딩 최대 해상도</span><span class="sxs-lookup"><span data-stu-id="cb09b-215">H.264 decoding maximum resolution</span></span></p></td>
<td><p><span data-ttu-id="cb09b-216">비디오</span><span class="sxs-lookup"><span data-stu-id="cb09b-216">VGA</span></span></p></td>
<td><p><span data-ttu-id="cb09b-217">QVGA: iPhone 4S</span><span class="sxs-lookup"><span data-stu-id="cb09b-217">QVGA: iPhone 4S</span></span></p>
<p><span data-ttu-id="cb09b-218">VGA: iPhone 5</span><span class="sxs-lookup"><span data-stu-id="cb09b-218">VGA: iPhone 5</span></span></p>
<p><span data-ttu-id="cb09b-219">720p: iPhone 5S 이상</span><span class="sxs-lookup"><span data-stu-id="cb09b-219">720p: iPhone 5S and later</span></span></p></td>
<td><p><span data-ttu-id="cb09b-220">VGA: iPad 2 이상/이후/iPad 미니 1 이상</span><span class="sxs-lookup"><span data-stu-id="cb09b-220">VGA: iPad 2 and later/iPad mini 1 and later</span></span></p>
<p><span data-ttu-id="cb09b-221">720p: iPad Air/iPad 미니 2/iPad 이상</span><span class="sxs-lookup"><span data-stu-id="cb09b-221">720p: iPad Air/iPad mini 2/iPad Pro and later</span></span></p></td>
<td><p><span data-ttu-id="cb09b-222">장치 모델에 따라 최대 VGA까지</span><span class="sxs-lookup"><span data-stu-id="cb09b-222">Up to VGA depending on device model</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

