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
ms.openlocfilehash: d6d5b06123879f2f9724fbd0f49facb8336d9860
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030912"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-client-video-requirements-for-lync-server-2013"></a>Lync Server 2013의 lync 클라이언트 비디오 요구 사항

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2016-01-29_

이 섹션에서는 Lync 2013 비디오 통화에 대 한 비디오 하드웨어 지원에 대해 설명 하 고 다양 한 컴퓨터, 태블릿 및 모바일 장치 구성에서 예상 되는 비디오 품질을 확인 하는 방법에 대해 설명 합니다.

<div>

## <a name="windows-desktop-and-tablet-video-requirements-and-capabilities"></a>Windows 데스크톱 및 태블릿 비디오 요구 사항 및 기능

Lync 2013에서는 비디오 인코딩에 대 한 하드웨어 가속을 소개 하 고, 10-44 부분 고급 비디오 코딩 표준을 기반으로 합니다. 이 기능은 CPU 클럭 속도가 낮은 컴퓨터가 고해상도 비디오를 인코딩 및 디코딩할 수 있게 해줍니다. 비디오 하드웨어 요구 사항은 컴퓨터 구성 및 원하는 비디오 해상도에 따라 다릅니다.

<div>

## <a name="video-hardware-requirements"></a>비디오 하드웨어 요구 사항


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>기능</th>
<th>요구 사항</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DXVA(DirectX 비디오 가속 설정)를 사용한 하드웨어 가속 H.264 디코딩</p></td>
<td><ul>
<li><p>그래픽 카드가 DirectX 9.0을 지원해야 하며 DXVA2_ModeH264_VLD_NoFGT 디코딩 모드를 제공해야 합니다.</p></li>
<li><p>최신 그래픽 카드 드라이버를 설치해야 합니다.</p></li>
</ul>
<div>

> [!NOTE]  
> 디코딩 모드에 대 한 자세한 내용은 <A href="http://go.microsoft.com/fwlink/p/?linkid=268530">http://go.microsoft.com/fwlink/p/?LinkId=268530</A>를 참조 하세요.


</div></td>
</tr>
<tr class="even">
<td><p>하드웨어 가속 H.264 인코딩: 칩셋 요구 사항</p></td>
<td><p>다음과 같은 인텔 하드웨어 가속 비디오 인코딩 솔루션이 지원 됩니다.</p>
<ul>
<li><p>2세대 및 3세대 Intel HD Graphics 2000, 2500, 3000 및 4000 칩셋(또는 최신 버전)과 통합 하드웨어 비디오 인코더 Intel HD Graphics driver 15.28.9.2884 또는 다음이 포함 된 최신 드라이버를 설치 해야 합니다.</p>
<ul>
<li><p>디스플레이 드라이버 9.17.10.2884 또는 최신 드라이버</p></li>
<li><p>HMFT (하드웨어 미디어 파운데이션 변환) 버전 3.12.10.31 또는 최신 HMFT</p></li>
</ul></li>
</ul>
<p>다음 AMD 하드웨어 가속 비디오 인코딩 솔루션이 지원 됩니다 (Lync Server 2013에 대 한 C U 1 업데이트 필요).</p>
<ul>
<li><p>Amd Video Codec Engine: 여러 개별 그래픽 카드와 AMD A 시리즈 가속 프로세서의 통합 된 프로세싱 단위에서 사용할 수 있습니다. AMD Video Codec Engine 드라이버 9.12.0.0 이상을 설치 해야 합니다.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>하드웨어 가속 H.264 인코딩: 카메라 요구 사항</p></td>
<td><p>UVC(USB Video Class) 사양 버전 1.5를 준수하는 통합 H.264 하드웨어 인코더가 포함된 USB 비디오 카메라</p>
<div>

> [!NOTE]  
> Lync 2013는 UVC 1.5에 대 한 지원을 포함 하는 Windows 8 또는 Windows 8.1가 포함 된 UVC 1.5 카메라를 지원 합니다. Windows 7에는 UVC 1.5에 대한 지원이 포함되지 않기 때문에 Lync 2013은 UVC 1.5 카메라를 일반 카메라로 취급하고 하드웨어 인코딩을 지원하지 않습니다.


</div></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="determining-h264-video-encoding-and-decoding-capabilities"></a>H.264 비디오 인코딩 및 디코딩 기능 확인

일반적으로 특정 컴퓨터 구성에 대한 최대 인코딩 및 디코딩 기능을 확인하는 데에는 4가지 기본 요소가 있습니다.

  - DXVA를 사용하는 하드웨어 가속 디코딩에 대한 지원

  - 하드웨어 가속 인코딩 지원

  - 물리적 코어 수

  - WEI(Windows 체험 지수)

WinSAT(Windows 시스템 평가 도구)는 WEI를 확인합니다. WinSAT 도구를 실행 하면% windir%\\Performance\\WinSAT\\데이터 저장소 디렉터리에 있는 컴퓨터에 공식적인 평가 XML 문서가 생성 됩니다. 이 XML 파일에는 인코딩 및 디코딩 기능을 확인하는 데 특히 중요한 다음 두 가지 점수가 포함됩니다.

  - VideoEncodeScore는 컴퓨터의 소프트웨어 기반 비디오 인코딩 기능을 나타냅니다.

  - GraphicsScore 값은 컴퓨터의 하드웨어 가속 인코딩 기능을 나타냅니다.

다음 3개의 테이블에서는 지원하는 하드웨어 가속에 따라 서로 다른 PC 유형에 대한 최대 인코딩 및 디코딩 기능을 설명합니다. 640x360 이상 해상도의 경우 지원되는 최대 프레임 속도는 30fps(초당 프레임 수)입니다. 640x360 미만 해상도의 경우 지원되는 최대 프레임 속도는 15fps입니다.

### <a name="computer-without-dxva-and-without-hardware-accelerated-encoder"></a>DXVA 및 하드웨어 가속 인코더가 없는 컴퓨터

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>지원 가능한 인코더 해상도</th>
<th>지원 가능한 디코더 해상도</th>
<th>요구 사항</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>424x240</p></td>
<td><p>424x240(수신 전용 시나리오의 경우 15fps에서 640x360)</p></td>
<td><p>1개 코어 및 VideoEncodeScore ≥ 4.0</p></td>
</tr>
<tr class="even">
<td><p>640x360</p></td>
<td><p>640x360</p></td>
<td><p>2개 코어 및 VideoEncodeScore ≥ 4.5</p></td>
</tr>
<tr class="odd">
<td><p>640x360</p></td>
<td><p>해상도 1280x720</p></td>
<td><p>2개 코어 및 VideoEncodeScore ≥ 4.5</p></td>
</tr>
<tr class="even">
<td><p>640x360</p></td>
<td><p>해상도 1920x1080</p></td>
<td><p>4개 코어 및 VideoEncodeScore ≥ 4.5</p></td>
</tr>
<tr class="odd">
<td><p>해상도 1280x720</p></td>
<td><p>해상도 1280x720</p></td>
<td><p>4개 코어 및 VideoEncodeScore ≥ 7.3</p></td>
</tr>
<tr class="even">
<td><p>해상도 1280x720</p></td>
<td><p>해상도 1920x1080</p></td>
<td><p>4개 코어 및 VideoEncodeScore ≥ 7.3</p></td>
</tr>
<tr class="odd">
<td><p>해상도 1920x1080</p></td>
<td><p>해상도 1920x1080</p></td>
<td><p>해당 없음</p></td>
</tr>
</tbody>
</table>


### <a name="computer-with-dxva-but-without-hardware-accelerated-encoder"></a>DXVA가 있지만 하드웨어 가속 인코더가 없는 컴퓨터

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>지원 가능한 인코더 해상도</th>
<th>지원 가능한 디코더 해상도</th>
<th>요구 사항</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>424x240</p></td>
<td><p>해상도 1920x1080</p></td>
<td><p>1개 코어 및 VideoEncodeScore ≥ 3.0</p></td>
</tr>
<tr class="even">
<td><p>640x360</p></td>
<td><p>해상도 1920x1080</p></td>
<td><p>2개 코어 및 VideoEncodeScore ≥ 4.5</p></td>
</tr>
<tr class="odd">
<td><p>960x540</p></td>
<td><p>해상도 1920x1080</p></td>
<td><p>2개 코어 및 VideoEncodeScore ≥ 6.0</p></td>
</tr>
<tr class="even">
<td><p>해상도 1280x720</p></td>
<td><p>해상도 1920x1080</p></td>
<td><p>4개 코어 및 VideoEncodeScore ≥ 6.7</p></td>
</tr>
<tr class="odd">
<td><p>해상도 1920x1080</p></td>
<td><p>해상도 1920x1080</p></td>
<td><p>4개 코어 및 VideoEncodeScore ≥ 8.2</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Windows 7에서 WinSAT 점수는 최대 7.9로 제한됩니다. 따라서 하드웨어 가속 인코더가 없는 컴퓨터의 인코딩 기능은 최대 WinSAT 점수가 9.9 인 Windows 8 또는 Windows 8.1 에서만 구현할 수 있습니다.



</div>

### <a name="computer-with-dxva-and-with-intel-hd-graphics-hardware-accelerated-encoder"></a>DXVA 및 Intel HD Graphics 하드웨어 가속 인코더가 있는 컴퓨터

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>지원 가능한 인코더 해상도</th>
<th>지원 가능한 디코더 해상도</th>
<th>요구 사항</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>해상도 1280x720</p></td>
<td><p>해상도 1920x1080</p></td>
<td><p>모든 2세대 및 3세대 Intel HD Graphics</p></td>
</tr>
<tr class="even">
<td><p>해상도 1920x1080</p></td>
<td><p>해상도 1920x1080</p></td>
<td><p>2세대 및 3세대 Intel HD Graphics 및 GraphicsScore ≥ 5.0</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<div>

## <a name="mobile-device-video-capabilities"></a>모바일 장치 비디오 기능

다음 표에는 지원 되는 모바일 장치의 최대 비디오 기능에 대 한 설명이 나와 있습니다. 모바일 장치 지원에 대 한 자세한 내용은 [Lync Server 2013에서 모바일 클라이언트 계획](lync-server-2013-planning-for-mobile-clients.md)을 참조 하십시오.


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
<th>기능</th>
<th>Windows Phone</th>
<th>iPhone</th>
<th>용</th>
<th>Android</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>H-264 인코딩 최대 해상도</p></td>
<td><p>비디오</p></td>
<td><p>QVGA: iPhone 4S</p>
<p>VGA: iPhone 5</p>
<p>720p: iPhone 5S 이상</p></td>
<td><p>VGA: iPad 2 이상/이후/iPad 미니 1 이상</p>
<p>720p: iPad Air/iPad 미니 2/iPad 이상</p></td>
<td><p>장치 모델에 따라 최대 VGA</p></td>
</tr>
<tr class="even">
<td><p>H-264 디코딩 최대 해상도</p></td>
<td><p>비디오</p></td>
<td><p>QVGA: iPhone 4S</p>
<p>VGA: iPhone 5</p>
<p>720p: iPhone 5S 이상</p></td>
<td><p>VGA: iPad 2 이상/이후/iPad 미니 1 이상</p>
<p>720p: iPad Air/iPad 미니 2/iPad 이상</p></td>
<td><p>장치 모델에 따라 최대 VGA</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

