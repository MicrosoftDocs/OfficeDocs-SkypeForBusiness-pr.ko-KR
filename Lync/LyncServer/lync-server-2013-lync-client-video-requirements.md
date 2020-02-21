---
title: 'Lync Server 2013: Lync 클라이언트 비디오 요구 사항'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync client video requirements
ms:assetid: 8f68f4c2-3194-487c-bd2f-fbe71ba8ad70
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688132(v=OCS.15)
ms:contentKeyID: 49733731
ms.date: 01/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c15eb698babcce1cd104dd7206c037b95d402992
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42186351"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="lync-client-video-requirements-for-lync-server-2013"></a><span data-ttu-id="e96bb-102">Lync Server 2013의 lync 클라이언트 비디오 요구 사항</span><span class="sxs-lookup"><span data-stu-id="e96bb-102">Lync client video requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e96bb-103">_**마지막으로 수정 된 항목:** 2016-01-29_</span><span class="sxs-lookup"><span data-stu-id="e96bb-103">_**Topic Last Modified:** 2016-01-29_</span></span>

<span data-ttu-id="e96bb-104">이 섹션에서는 Lync 2013 비디오 통화에 대 한 비디오 하드웨어 지원에 대해 설명 하 고 다양 한 컴퓨터, 태블릿 및 모바일 장치 구성에서 예상 되는 비디오 품질을 확인 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="e96bb-104">This section describes video hardware support for Lync 2013 video calls and describes how to determine the expected video quality for various computer, tablet, and mobile device configurations.</span></span>

<div>

## <a name="windows-desktop-and-tablet-video-requirements-and-capabilities"></a><span data-ttu-id="e96bb-105">Windows 데스크톱 및 태블릿 비디오 요구 사항 및 기능</span><span class="sxs-lookup"><span data-stu-id="e96bb-105">Windows Desktop and Tablet Video Requirements and Capabilities</span></span>

<span data-ttu-id="e96bb-106">Lync 2013에서는 비디오 인코딩에 대 한 하드웨어 가속을 소개 하 고, 10-44 부분 고급 비디오 코딩 표준을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="e96bb-106">Lync 2013 introduces hardware acceleration for video encoding and decoding based on the H.264/MPEG-4 Part 10 Advanced Video Coding standard.</span></span> <span data-ttu-id="e96bb-107">이 기능은 CPU 클럭 속도가 낮은 컴퓨터가 고해상도 비디오를 인코딩 및 디코딩할 수 있게 해줍니다.</span><span class="sxs-lookup"><span data-stu-id="e96bb-107">This feature allows computers with lower CPU clock speeds to encode and decode higher resolution video.</span></span> <span data-ttu-id="e96bb-108">비디오 하드웨어 요구 사항은 컴퓨터 구성 및 원하는 비디오 해상도에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="e96bb-108">Video hardware requirements vary depending on the computer configuration and the video resolution wanted.</span></span>

<div>

## <a name="video-hardware-requirements"></a><span data-ttu-id="e96bb-109">비디오 하드웨어 요구 사항</span><span class="sxs-lookup"><span data-stu-id="e96bb-109">Video Hardware Requirements</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e96bb-110">기능</span><span class="sxs-lookup"><span data-stu-id="e96bb-110">Feature</span></span></th>
<th><span data-ttu-id="e96bb-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e96bb-111">Requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e96bb-112">DXVA(DirectX 비디오 가속 설정)를 사용한 하드웨어 가속 H.264 디코딩</span><span class="sxs-lookup"><span data-stu-id="e96bb-112">Hardware accelerated H.264 decoding using DirectX Video Acceleration (DXVA)</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="e96bb-113">그래픽 카드가 DirectX 9.0을 지원해야 하며 DXVA2_ModeH264_VLD_NoFGT 디코딩 모드를 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e96bb-113">Graphics card must support DirectX 9.0 and must expose the DXVA2_ModeH264_VLD_NoFGT decoding mode.</span></span></p></li>
<li><p><span data-ttu-id="e96bb-114">최신 그래픽 카드 드라이버를 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e96bb-114">The latest graphics card driver must be installed.</span></span></p></li>
</ul>
<div>

> [!NOTE]  
> <span data-ttu-id="e96bb-115">디코딩 모드에 대 한 자세한 내용은 <A href="https://go.microsoft.com/fwlink/p/?linkid=268530">https://go.microsoft.com/fwlink/p/?LinkId=268530</A>를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e96bb-115">For details about decoding modes, see <A href="https://go.microsoft.com/fwlink/p/?linkid=268530">https://go.microsoft.com/fwlink/p/?LinkId=268530</A>.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e96bb-116">하드웨어 가속 H.264 인코딩: 칩셋 요구 사항</span><span class="sxs-lookup"><span data-stu-id="e96bb-116">Hardware accelerated H.264 encoding: Chipset Requirements</span></span></p></td>
<td><p><span data-ttu-id="e96bb-117">다음과 같은 인텔 하드웨어 가속 비디오 인코딩 솔루션이 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e96bb-117">The following Intel hardware accelerated video encoding solutions are supported:</span></span></p>
<ul>
<li><p><span data-ttu-id="e96bb-118">2세대 및 3세대 Intel HD Graphics 2000, 2500, 3000 및 4000 칩셋(또는 최신 버전)과 통합 하드웨어 비디오 인코더</span><span class="sxs-lookup"><span data-stu-id="e96bb-118">Second and third generation Intel HD Graphics 2000, 2500, 3000, and 4000 chipsets (or later versions) with integrated hardware video encoders.</span></span> <span data-ttu-id="e96bb-119">Intel HD Graphics driver 15.28.9.2884 또는 다음이 포함 된 최신 드라이버를 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e96bb-119">Installation of the Intel HD Graphics driver 15.28.9.2884 or the latest driver containing the following is required:</span></span></p>
<ul>
<li><p><span data-ttu-id="e96bb-120">디스플레이 드라이버 9.17.10.2884 또는 최신 드라이버</span><span class="sxs-lookup"><span data-stu-id="e96bb-120">Display driver 9.17.10.2884 or the latest driver</span></span></p></li>
<li><p><span data-ttu-id="e96bb-121">HMFT (하드웨어 미디어 파운데이션 변환) 버전 3.12.10.31 또는 최신 HMFT</span><span class="sxs-lookup"><span data-stu-id="e96bb-121">Hardware media foundation transform (HMFT) version 3.12.10.31 or the latest HMFT</span></span></p></li>
</ul></li>
</ul>
<p><span data-ttu-id="e96bb-122">다음 AMD 하드웨어 가속 비디오 인코딩 솔루션이 지원 됩니다 (Lync Server 2013에 대 한 C U 1 업데이트 필요).</span><span class="sxs-lookup"><span data-stu-id="e96bb-122">The following AMD hardware accelerated video encoding solutions are supported (requires CU1 Updates for Lync Server 2013):</span></span></p>
<ul>
<li><p><span data-ttu-id="e96bb-123">Amd Video Codec Engine: 여러 개별 그래픽 카드와 AMD A 시리즈 가속 프로세서의 통합 된 프로세싱 단위에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e96bb-123">AMD Video Codec Engine, which is available in several discrete graphics cards and in integrated accelerated processing units of AMD A-Series Accelerated Processors.</span></span> <span data-ttu-id="e96bb-124">AMD Video Codec Engine 드라이버 9.12.0.0 이상을 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e96bb-124">The AMD Video Codec Engine driver 9.12.0.0 or higher must be installed.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e96bb-125">하드웨어 가속 H.264 인코딩: 카메라 요구 사항</span><span class="sxs-lookup"><span data-stu-id="e96bb-125">Hardware accelerated H.264 encoding: Camera Requirements</span></span></p></td>
<td><p><span data-ttu-id="e96bb-126">UVC(USB Video Class) 사양 버전 1.5를 준수하는 통합 H.264 하드웨어 인코더가 포함된 USB 비디오 카메라</span><span class="sxs-lookup"><span data-stu-id="e96bb-126">USB video cameras with integrated H.264 hardware encoder that conforms to the USB Video Class (UVC) specification version 1.5.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="e96bb-127">Lync 2013는 UVC 1.5에 대 한 지원을 포함 하는 Windows 8 또는 Windows 8.1가 포함 된 UVC 1.5 카메라를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="e96bb-127">Lync 2013 supports UVC 1.5 cameras with Windows 8 or Windows 8.1, which includes support for UVC 1.5.</span></span> <span data-ttu-id="e96bb-128">Windows 7에는 UVC 1.5에 대한 지원이 포함되지 않기 때문에 Lync 2013은 UVC 1.5 카메라를 일반 카메라로 취급하고 하드웨어 인코딩을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e96bb-128">Because Windows 7 does not include support for UVC 1.5, Lync 2013 treats UVC 1.5 cameras as regular cameras with no hardware encoding support.</span></span>


</div></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="determining-h264-video-encoding-and-decoding-capabilities"></a><span data-ttu-id="e96bb-129">H.264 비디오 인코딩 및 디코딩 기능 확인</span><span class="sxs-lookup"><span data-stu-id="e96bb-129">Determining H.264 Video Encoding and Decoding Capabilities</span></span>

<span data-ttu-id="e96bb-130">일반적으로 특정 컴퓨터 구성에 대한 최대 인코딩 및 디코딩 기능을 확인하는 데에는 4가지 기본 요소가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e96bb-130">Generally, there are four major factors that determine the maximum encoding and decoding capability of a particular computer configuration:</span></span>

  - <span data-ttu-id="e96bb-131">DXVA를 사용하는 하드웨어 가속 디코딩에 대한 지원</span><span class="sxs-lookup"><span data-stu-id="e96bb-131">Support for hardware accelerated decoding by using DXVA</span></span>

  - <span data-ttu-id="e96bb-132">하드웨어 가속 인코딩 지원</span><span class="sxs-lookup"><span data-stu-id="e96bb-132">Support for hardware accelerated encoding</span></span>

  - <span data-ttu-id="e96bb-133">물리적 코어 수</span><span class="sxs-lookup"><span data-stu-id="e96bb-133">Number of physical cores</span></span>

  - <span data-ttu-id="e96bb-134">WEI(Windows 체험 지수)</span><span class="sxs-lookup"><span data-stu-id="e96bb-134">Windows Experience Index (WEI)</span></span>

<span data-ttu-id="e96bb-135">WinSAT(Windows 시스템 평가 도구)는 WEI를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="e96bb-135">The Windows System Assessment Tool (WinSAT) determines the WEI.</span></span> <span data-ttu-id="e96bb-136">WinSAT 도구를 실행 하면% windir%\\Performance\\WinSAT\\데이터 저장소 디렉터리에 있는 컴퓨터에 공식적인 평가 XML 문서가 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e96bb-136">When you run the WinSAT tool, it generates a Formal.Assessment XML document on the computer in the %windir%\\Performance\\WinSAT\\DataStore directory.</span></span> <span data-ttu-id="e96bb-137">이 XML 파일에는 인코딩 및 디코딩 기능을 확인하는 데 특히 중요한 다음 두 가지 점수가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="e96bb-137">This XML file contains the following two scores that are of particular importance for determining encoding and decoding capabilities:</span></span>

  - <span data-ttu-id="e96bb-138">VideoEncodeScore는 컴퓨터의 소프트웨어 기반 비디오 인코딩 기능을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="e96bb-138">The VideoEncodeScore indicates the software-based video encoding capability of the computer.</span></span>

  - <span data-ttu-id="e96bb-139">GraphicsScore 값은 컴퓨터의 하드웨어 가속 인코딩 기능을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="e96bb-139">The GraphicsScore value indicates the hardware accelerated encoding capability of the computer.</span></span>

<span data-ttu-id="e96bb-p106">다음 3개의 테이블에서는 지원하는 하드웨어 가속에 따라 서로 다른 PC 유형에 대한 최대 인코딩 및 디코딩 기능을 설명합니다. 640x360 이상 해상도의 경우 지원되는 최대 프레임 속도는 30fps(초당 프레임 수)입니다. 640x360 미만 해상도의 경우 지원되는 최대 프레임 속도는 15fps입니다.</span><span class="sxs-lookup"><span data-stu-id="e96bb-p106">The following three tables explain the maximum encoding and decoding capability for different PC types depending on what hardware acceleration they support. For resolutions of 640x360 and higher, the maximum supported frame rate is 30 frames per second (fps). For resolutions lower than 640x360, the maximum supported frame rate is 15 fps.</span></span>

### <a name="computer-without-dxva-and-without-hardware-accelerated-encoder"></a><span data-ttu-id="e96bb-143">DXVA 및 하드웨어 가속 인코더가 없는 컴퓨터</span><span class="sxs-lookup"><span data-stu-id="e96bb-143">Computer Without DXVA And Without Hardware Accelerated Encoder</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e96bb-144">지원 가능한 인코더 해상도</span><span class="sxs-lookup"><span data-stu-id="e96bb-144">Capable Encoder Resolution</span></span></th>
<th><span data-ttu-id="e96bb-145">지원 가능한 디코더 해상도</span><span class="sxs-lookup"><span data-stu-id="e96bb-145">Capable Decoder Resolution</span></span></th>
<th><span data-ttu-id="e96bb-146">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e96bb-146">Requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e96bb-147">424x240</span><span class="sxs-lookup"><span data-stu-id="e96bb-147">424x240</span></span></p></td>
<td><p><span data-ttu-id="e96bb-148">424x240(수신 전용 시나리오의 경우 15fps에서 640x360)</span><span class="sxs-lookup"><span data-stu-id="e96bb-148">424x240 (640x360 at 15fps for receive only scenarios)</span></span></p></td>
<td><p><span data-ttu-id="e96bb-149">1개 코어 및 VideoEncodeScore ≥ 4.0</span><span class="sxs-lookup"><span data-stu-id="e96bb-149">1 Core and VideoEncodeScore ≥ 4.0</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e96bb-150">640x360</span><span class="sxs-lookup"><span data-stu-id="e96bb-150">640x360</span></span></p></td>
<td><p><span data-ttu-id="e96bb-151">640x360</span><span class="sxs-lookup"><span data-stu-id="e96bb-151">640x360</span></span></p></td>
<td><p><span data-ttu-id="e96bb-152">2개 코어 및 VideoEncodeScore ≥ 4.5</span><span class="sxs-lookup"><span data-stu-id="e96bb-152">2 Cores and VideoEncodeScore ≥ 4.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e96bb-153">640x360</span><span class="sxs-lookup"><span data-stu-id="e96bb-153">640x360</span></span></p></td>
<td><p><span data-ttu-id="e96bb-154">해상도 1280x720</span><span class="sxs-lookup"><span data-stu-id="e96bb-154">1280x720</span></span></p></td>
<td><p><span data-ttu-id="e96bb-155">2개 코어 및 VideoEncodeScore ≥ 4.5</span><span class="sxs-lookup"><span data-stu-id="e96bb-155">2 Cores and VideoEncodeScore ≥ 4.5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e96bb-156">640x360</span><span class="sxs-lookup"><span data-stu-id="e96bb-156">640x360</span></span></p></td>
<td><p><span data-ttu-id="e96bb-157">해상도 1920x1080</span><span class="sxs-lookup"><span data-stu-id="e96bb-157">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="e96bb-158">4개 코어 및 VideoEncodeScore ≥ 4.5</span><span class="sxs-lookup"><span data-stu-id="e96bb-158">4 Cores and VideoEncodeScore ≥ 4.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e96bb-159">해상도 1280x720</span><span class="sxs-lookup"><span data-stu-id="e96bb-159">1280x720</span></span></p></td>
<td><p><span data-ttu-id="e96bb-160">해상도 1280x720</span><span class="sxs-lookup"><span data-stu-id="e96bb-160">1280x720</span></span></p></td>
<td><p><span data-ttu-id="e96bb-161">4개 코어 및 VideoEncodeScore ≥ 7.3</span><span class="sxs-lookup"><span data-stu-id="e96bb-161">4 Cores and VideoEncodeScore ≥ 7.3</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e96bb-162">해상도 1280x720</span><span class="sxs-lookup"><span data-stu-id="e96bb-162">1280x720</span></span></p></td>
<td><p><span data-ttu-id="e96bb-163">해상도 1920x1080</span><span class="sxs-lookup"><span data-stu-id="e96bb-163">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="e96bb-164">4개 코어 및 VideoEncodeScore ≥ 7.3</span><span class="sxs-lookup"><span data-stu-id="e96bb-164">4 Cores and VideoEncodeScore ≥ 7.3</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e96bb-165">해상도 1920x1080</span><span class="sxs-lookup"><span data-stu-id="e96bb-165">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="e96bb-166">해상도 1920x1080</span><span class="sxs-lookup"><span data-stu-id="e96bb-166">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="e96bb-167">해당 없음</span><span class="sxs-lookup"><span data-stu-id="e96bb-167">N/A</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="computer-with-dxva-but-without-hardware-accelerated-encoder"></a><span data-ttu-id="e96bb-168">DXVA가 있지만 하드웨어 가속 인코더가 없는 컴퓨터</span><span class="sxs-lookup"><span data-stu-id="e96bb-168">Computer With DXVA But Without Hardware Accelerated Encoder</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e96bb-169">지원 가능한 인코더 해상도</span><span class="sxs-lookup"><span data-stu-id="e96bb-169">Capable Encoder Resolution</span></span></th>
<th><span data-ttu-id="e96bb-170">지원 가능한 디코더 해상도</span><span class="sxs-lookup"><span data-stu-id="e96bb-170">Capable Decoder Resolution</span></span></th>
<th><span data-ttu-id="e96bb-171">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e96bb-171">Requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e96bb-172">424x240</span><span class="sxs-lookup"><span data-stu-id="e96bb-172">424x240</span></span></p></td>
<td><p><span data-ttu-id="e96bb-173">해상도 1920x1080</span><span class="sxs-lookup"><span data-stu-id="e96bb-173">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="e96bb-174">1개 코어 및 VideoEncodeScore ≥ 3.0</span><span class="sxs-lookup"><span data-stu-id="e96bb-174">1 Core and VideoEncodeScore ≥ 3.0</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e96bb-175">640x360</span><span class="sxs-lookup"><span data-stu-id="e96bb-175">640x360</span></span></p></td>
<td><p><span data-ttu-id="e96bb-176">해상도 1920x1080</span><span class="sxs-lookup"><span data-stu-id="e96bb-176">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="e96bb-177">2개 코어 및 VideoEncodeScore ≥ 4.5</span><span class="sxs-lookup"><span data-stu-id="e96bb-177">2 Cores and VideoEncodeScore ≥ 4.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e96bb-178">960x540</span><span class="sxs-lookup"><span data-stu-id="e96bb-178">960x540</span></span></p></td>
<td><p><span data-ttu-id="e96bb-179">해상도 1920x1080</span><span class="sxs-lookup"><span data-stu-id="e96bb-179">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="e96bb-180">2개 코어 및 VideoEncodeScore ≥ 6.0</span><span class="sxs-lookup"><span data-stu-id="e96bb-180">2 Cores and VideoEncodeScore ≥ 6.0</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e96bb-181">해상도 1280x720</span><span class="sxs-lookup"><span data-stu-id="e96bb-181">1280x720</span></span></p></td>
<td><p><span data-ttu-id="e96bb-182">해상도 1920x1080</span><span class="sxs-lookup"><span data-stu-id="e96bb-182">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="e96bb-183">4개 코어 및 VideoEncodeScore ≥ 6.7</span><span class="sxs-lookup"><span data-stu-id="e96bb-183">4 Cores and VideoEncodeScore ≥ 6.7</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e96bb-184">해상도 1920x1080</span><span class="sxs-lookup"><span data-stu-id="e96bb-184">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="e96bb-185">해상도 1920x1080</span><span class="sxs-lookup"><span data-stu-id="e96bb-185">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="e96bb-186">4개 코어 및 VideoEncodeScore ≥ 8.2</span><span class="sxs-lookup"><span data-stu-id="e96bb-186">4 Cores and VideoEncodeScore ≥ 8.2</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="e96bb-187">Windows 7에서 WinSAT 점수는 최대 7.9로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="e96bb-187">The WinSAT score on Windows 7 is limited to a maximum of 7.9.</span></span> <span data-ttu-id="e96bb-188">따라서 하드웨어 가속 인코더가 없는 컴퓨터의 인코딩 기능은 최대 WinSAT 점수가 9.9 인 Windows 8 또는 Windows 8.1 에서만 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e96bb-188">Therefore, the encoding capability for a computer without a hardware accelerated encoder can only be achieved on Windows 8 or Windows 8.1, where the maximum WinSAT score is 9.9.</span></span>



</div>

### <a name="computer-with-dxva-and-with-intel-hd-graphics-hardware-accelerated-encoder"></a><span data-ttu-id="e96bb-189">DXVA 및 Intel HD Graphics 하드웨어 가속 인코더가 있는 컴퓨터</span><span class="sxs-lookup"><span data-stu-id="e96bb-189">Computer With DXVA And With Intel HD Graphics Hardware Accelerated Encoder</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e96bb-190">지원 가능한 인코더 해상도</span><span class="sxs-lookup"><span data-stu-id="e96bb-190">Capable Encoder Resolution</span></span></th>
<th><span data-ttu-id="e96bb-191">지원 가능한 디코더 해상도</span><span class="sxs-lookup"><span data-stu-id="e96bb-191">Capable Decoder Resolution</span></span></th>
<th><span data-ttu-id="e96bb-192">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e96bb-192">Requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e96bb-193">해상도 1280x720</span><span class="sxs-lookup"><span data-stu-id="e96bb-193">1280x720</span></span></p></td>
<td><p><span data-ttu-id="e96bb-194">해상도 1920x1080</span><span class="sxs-lookup"><span data-stu-id="e96bb-194">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="e96bb-195">모든 2세대 및 3세대 Intel HD Graphics</span><span class="sxs-lookup"><span data-stu-id="e96bb-195">All 2nd and 3rd generation Intel HD Graphics</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e96bb-196">해상도 1920x1080</span><span class="sxs-lookup"><span data-stu-id="e96bb-196">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="e96bb-197">해상도 1920x1080</span><span class="sxs-lookup"><span data-stu-id="e96bb-197">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="e96bb-198">2세대 및 3세대 Intel HD Graphics 및 GraphicsScore ≥ 5.0</span><span class="sxs-lookup"><span data-stu-id="e96bb-198">2nd and 3rd generation Intel HD Graphics and GraphicsScore ≥ 5.0</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<div>

## <a name="mobile-device-video-capabilities"></a><span data-ttu-id="e96bb-199">모바일 장치 비디오 기능</span><span class="sxs-lookup"><span data-stu-id="e96bb-199">Mobile Device Video Capabilities</span></span>

<span data-ttu-id="e96bb-200">다음 표에는 지원 되는 모바일 장치의 최대 비디오 기능에 대 한 설명이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e96bb-200">The following table describes the maximum video capabilities for supported mobile devices.</span></span> <span data-ttu-id="e96bb-201">모바일 장치 지원에 대 한 자세한 내용은 [Lync Server 2013에서 모바일 클라이언트 계획](lync-server-2013-planning-for-mobile-clients.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="e96bb-201">For more information about mobile device support, see [Planning for mobile clients in Lync Server 2013](lync-server-2013-planning-for-mobile-clients.md).</span></span>


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
<th><span data-ttu-id="e96bb-202">기능</span><span class="sxs-lookup"><span data-stu-id="e96bb-202">Feature</span></span></th>
<th><span data-ttu-id="e96bb-203">Windows Phone</span><span class="sxs-lookup"><span data-stu-id="e96bb-203">Windows Phone</span></span></th>
<th><span data-ttu-id="e96bb-204">iPhone</span><span class="sxs-lookup"><span data-stu-id="e96bb-204">iPhone</span></span></th>
<th><span data-ttu-id="e96bb-205">용</span><span class="sxs-lookup"><span data-stu-id="e96bb-205">iPad</span></span></th>
<th><span data-ttu-id="e96bb-206">Android</span><span class="sxs-lookup"><span data-stu-id="e96bb-206">Android</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e96bb-207">H-264 인코딩 최대 해상도</span><span class="sxs-lookup"><span data-stu-id="e96bb-207">H.264 encoding maximum resolution</span></span></p></td>
<td><p><span data-ttu-id="e96bb-208">비디오</span><span class="sxs-lookup"><span data-stu-id="e96bb-208">VGA</span></span></p></td>
<td><p><span data-ttu-id="e96bb-209">QVGA: iPhone 4S</span><span class="sxs-lookup"><span data-stu-id="e96bb-209">QVGA: iPhone 4S</span></span></p>
<p><span data-ttu-id="e96bb-210">VGA: iPhone 5</span><span class="sxs-lookup"><span data-stu-id="e96bb-210">VGA: iPhone 5</span></span></p>
<p><span data-ttu-id="e96bb-211">720p: iPhone 5S 이상</span><span class="sxs-lookup"><span data-stu-id="e96bb-211">720p: iPhone 5S and later</span></span></p></td>
<td><p><span data-ttu-id="e96bb-212">VGA: iPad 2 이상/이후/iPad 미니 1 이상</span><span class="sxs-lookup"><span data-stu-id="e96bb-212">VGA: iPad 2 and later/iPad mini 1 and later</span></span></p>
<p><span data-ttu-id="e96bb-213">720p: iPad Air/iPad 미니 2/iPad 이상</span><span class="sxs-lookup"><span data-stu-id="e96bb-213">720p: iPad Air/iPad mini 2/iPad Pro and later</span></span></p></td>
<td><p><span data-ttu-id="e96bb-214">장치 모델에 따라 최대 VGA</span><span class="sxs-lookup"><span data-stu-id="e96bb-214">Up to VGA depending on device model</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e96bb-215">H-264 디코딩 최대 해상도</span><span class="sxs-lookup"><span data-stu-id="e96bb-215">H.264 decoding maximum resolution</span></span></p></td>
<td><p><span data-ttu-id="e96bb-216">비디오</span><span class="sxs-lookup"><span data-stu-id="e96bb-216">VGA</span></span></p></td>
<td><p><span data-ttu-id="e96bb-217">QVGA: iPhone 4S</span><span class="sxs-lookup"><span data-stu-id="e96bb-217">QVGA: iPhone 4S</span></span></p>
<p><span data-ttu-id="e96bb-218">VGA: iPhone 5</span><span class="sxs-lookup"><span data-stu-id="e96bb-218">VGA: iPhone 5</span></span></p>
<p><span data-ttu-id="e96bb-219">720p: iPhone 5S 이상</span><span class="sxs-lookup"><span data-stu-id="e96bb-219">720p: iPhone 5S and later</span></span></p></td>
<td><p><span data-ttu-id="e96bb-220">VGA: iPad 2 이상/이후/iPad 미니 1 이상</span><span class="sxs-lookup"><span data-stu-id="e96bb-220">VGA: iPad 2 and later/iPad mini 1 and later</span></span></p>
<p><span data-ttu-id="e96bb-221">720p: iPad Air/iPad 미니 2/iPad 이상</span><span class="sxs-lookup"><span data-stu-id="e96bb-221">720p: iPad Air/iPad mini 2/iPad Pro and later</span></span></p></td>
<td><p><span data-ttu-id="e96bb-222">장치 모델에 따라 최대 VGA</span><span class="sxs-lookup"><span data-stu-id="e96bb-222">Up to VGA depending on device model</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

