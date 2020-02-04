---
title: 'Lync Server 2013: Lync 클라이언트 영상 요구 사항'
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
ms.openlocfilehash: d174b73bd4369220ae83bc8365267a626849e235
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765506"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-client-video-requirements-for-lync-server-2013"></a>Lync Server 2013의 lync 클라이언트 비디오 요구 사항

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2016-01-29_

이 섹션에서는 Lync 2013 영상 통화에 대 한 비디오 하드웨어 지원 및 다양 한 컴퓨터, 태블릿 및 모바일 장치 구성에 필요한 비디오 품질을 확인 하는 방법에 대해 설명 합니다.

<div>

## <a name="windows-desktop-and-tablet-video-requirements-and-capabilities"></a>Windows 데스크톱 및 태블릿 비디오 요구 사항 및 기능

Lync 2013는 H. 264/MPEG-4/4 부 고급 비디오 코딩 표준을 기반으로 비디오 인코딩 및 디코딩에 대 한 하드웨어 가속을 소개 합니다. 이 기능을 사용 하면 CPU 클럭 속도가 낮은 컴퓨터에서 더 높은 해상도의 인코딩 및 디코딩을 할 수 있습니다. 비디오 하드웨어 요구 사항은 컴퓨터 구성과 비디오 해상도에 따라 달라 집니다.

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
<td><p>DirectX 비디오 가속 (DXVA)을 사용 하는 하드웨어 가속 H/264 디코딩</p></td>
<td><ul>
<li><p>그래픽 카드는 DirectX 9.0를 지원 해야 하며 DXVA2_ModeH264_VLD_NoFGT 디코딩 모드를 노출 해야 합니다.</p></li>
<li><p>최신 그래픽 카드 드라이버를 설치 해야 합니다.</p></li>
</ul>
<div>

> [!NOTE]  
> 디코딩 모드에 대 한 자세한 내용은 <A href="http://go.microsoft.com/fwlink/p/?linkid=268530">http://go.microsoft.com/fwlink/p/?LinkId=268530</A>을 참조 하세요.


</div></td>
</tr>
<tr class="even">
<td><p>하드웨어 가속 H. 264 인코딩: 칩셋 요구 사항</p></td>
<td><p>다음과 같은 Intel 하드웨어 가속 비디오 인코딩 솔루션이 지원 됩니다.</p>
<ul>
<li><p>두번째 및 세번째 세대 Intel HD 그래픽 2000, 2500, 3000, 4000 칩셋 (또는 이후 버전)에서 통합 하드웨어 비디오 인코더를 사용 합니다. Intel HD 그래픽 드라이버 15.28.9.2884 설치 또는 다음을 포함 하는 최신 드라이버가 필요 합니다.</p>
<ul>
<li><p>디스플레이 드라이버 9.17.10.2884 또는 최신 드라이버</p></li>
<li><p>HMFT (하드웨어 media foundation transform) 버전 3.12.10.31 또는 최신 HMFT</p></li>
</ul></li>
</ul>
<p>다음 AMD 하드웨어 가속 비디오 인코딩 솔루션이 지원 됩니다 (Lync Server 2013에 대 한 CU1 업데이트 필요).</p>
<ul>
<li><p>Amd 시리즈 가속 프로세서의 통합 가속 처리 장치 및 여러 개의 개별 그래픽 카드에서 사용할 수 있는 AMD 비디오 코덱 엔진. AMD 비디오 코덱 엔진 드라이버 9.12.0.0 이상을 설치 해야 합니다.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>하드웨어 가속 H. 264 인코딩: 카메라 요구 사항</p></td>
<td><p>UVC (USB Video Class) 사양 버전 1.5을 준수 하는 통합 된 H-264 하드웨어 인코더가 USB 비디오 카메라</p>
<div>

> [!NOTE]  
> Lync 2013는 uvc 1.5에 대 한 지원을 포함 하는 Windows 8 또는 Windows 8.1을 사용 하 여 UVC 1.5 카메라를 지원 합니다. Windows 7에는 UVC 1.5에 대 한 지원이 포함 되어 있지 않으므로 Lync 2013에서는 UVC 1.5 카메라가 하드웨어 인코딩 지원이 없는 일반 카메라로 처리 됩니다.


</div></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="determining-h264-video-encoding-and-decoding-capabilities"></a>H/264 비디오 인코딩 및 디코딩 기능 확인

일반적으로 특정 컴퓨터 구성의 최대 인코딩 및 디코딩 기능을 결정 하는 네 가지 주요 요인이 있습니다.

  - DXVA를 사용 하 여 하드웨어 가속 디코딩 지원

  - 하드웨어 가속 인코딩 지원

  - 실제 코어 수

  - WEI (Windows 체험 지 인덱스)

Windows 시스템 평가 도구 (WinSAT)는 WEI를 결정 합니다. WinSAT 도구를 실행 하면% windir%\\성능\\WinSAT\\데이터 저장소 디렉터리에 있는 컴퓨터에 공식적인 평가 XML 문서가 생성 됩니다. 이 XML 파일에는 인코딩 및 디코딩 기능을 결정 하는 데 특히 중요 한 다음 두 가지 점수가 포함 되어 있습니다.

  - VideoEncodeScore는 컴퓨터의 소프트웨어 기반 비디오 인코딩 기능을 나타냅니다.

  - GraphicsScore 값은 컴퓨터의 하드웨어 가속 인코딩 기능을 나타냅니다.

다음 세 가지 표에서는 지 원하는 하드웨어 가속에 따라 다양 한 PC 유형의 최대 인코딩 및 디코딩 기능에 대해 설명 합니다. 640x360 이상 해상도의 경우 지원 되는 최대 프레임 속도는 초당 30 프레임 (fps)입니다. 640x360 보다 낮은 해상도의 경우 지원 되는 최대 프레임 속도는 15fps입니다.

### <a name="computer-without-dxva-and-without-hardware-accelerated-encoder"></a>DXVA 및 하드웨어 가속 인코더가 없는 컴퓨터

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>사용할 수 있는 인코더 해상도</th>
<th>지원 되는 디코더 해상도</th>
<th>요구 사항</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>424x240</p></td>
<td><p>424x240 (640x360에만 해당 시나리오의 경우 15fps)</p></td>
<td><p>1 코어 및 VideoEncodeScore ≥ 4.0</p></td>
</tr>
<tr class="even">
<td><p>640x360</p></td>
<td><p>640x360</p></td>
<td><p>2 코어 및 VideoEncodeScore ≥ 4.5</p></td>
</tr>
<tr class="odd">
<td><p>640x360</p></td>
<td><p>1280x720</p></td>
<td><p>2 코어 및 VideoEncodeScore ≥ 4.5</p></td>
</tr>
<tr class="even">
<td><p>640x360</p></td>
<td><p>1920x1080</p></td>
<td><p>4 코어 및 VideoEncodeScore ≥ 4.5</p></td>
</tr>
<tr class="odd">
<td><p>1280x720</p></td>
<td><p>1280x720</p></td>
<td><p>4 코어 및 VideoEncodeScore ≥ 7.3</p></td>
</tr>
<tr class="even">
<td><p>1280x720</p></td>
<td><p>1920x1080</p></td>
<td><p>4 코어 및 VideoEncodeScore ≥ 7.3</p></td>
</tr>
<tr class="odd">
<td><p>1920x1080</p></td>
<td><p>1920x1080</p></td>
<td><p>해당 없음</p></td>
</tr>
</tbody>
</table>


### <a name="computer-with-dxva-but-without-hardware-accelerated-encoder"></a>DXVA 있지만 하드웨어 가속 인코더가 없는 컴퓨터

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>사용할 수 있는 인코더 해상도</th>
<th>지원 되는 디코더 해상도</th>
<th>요구 사항</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>424x240</p></td>
<td><p>1920x1080</p></td>
<td><p>1 코어 및 VideoEncodeScore ≥ 3.0</p></td>
</tr>
<tr class="even">
<td><p>640x360</p></td>
<td><p>1920x1080</p></td>
<td><p>2 코어 및 VideoEncodeScore ≥ 4.5</p></td>
</tr>
<tr class="odd">
<td><p>960x540</p></td>
<td><p>1920x1080</p></td>
<td><p>2 코어 및 VideoEncodeScore ≥ 6.0</p></td>
</tr>
<tr class="even">
<td><p>1280x720</p></td>
<td><p>1920x1080</p></td>
<td><p>4 코어 및 VideoEncodeScore ≥ 6.7</p></td>
</tr>
<tr class="odd">
<td><p>1920x1080</p></td>
<td><p>1920x1080</p></td>
<td><p>4 코어 및 VideoEncodeScore ≥ 8.2</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Windows 7의 WinSAT 점수는 최대 7.9으로 제한 됩니다. 따라서 하드웨어 가속 인코더가 없는 컴퓨터에 대 한 인코딩 접근 권한 값은 Windows 8 또는 Windows 8.1 에서만 가능 하며,이는 최대 WinSAT 점수가 9.9입니다.



</div>

### <a name="computer-with-dxva-and-with-intel-hd-graphics-hardware-accelerated-encoder"></a>DXVA 및 Intel HD 그래픽 하드웨어 가속 인코더를 사용 하는 컴퓨터

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>사용할 수 있는 인코더 해상도</th>
<th>지원 되는 디코더 해상도</th>
<th>요구 사항</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1280x720</p></td>
<td><p>1920x1080</p></td>
<td><p>모든 2 차 및 3 세대 Intel HD 그래픽</p></td>
</tr>
<tr class="even">
<td><p>1920x1080</p></td>
<td><p>1920x1080</p></td>
<td><p>2 차 및 3 세대 Intel HD 그래픽 및 GraphicsScore ≥ 5.0</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<div>

## <a name="mobile-device-video-capabilities"></a>모바일 장치 영상 기능

다음 표에서는 지원 되는 모바일 장치의 최대 비디오 기능에 대해 설명 합니다. 모바일 장치 지원에 대 한 자세한 내용은 [Lync Server 2013의 모바일 클라이언트 계획](lync-server-2013-planning-for-mobile-clients.md)을 참조 하세요.


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
<th>iPad</th>
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
<td><p>장치 모델에 따라 최대 VGA까지</p></td>
</tr>
<tr class="even">
<td><p>H. 264 디코딩 최대 해상도</p></td>
<td><p>비디오</p></td>
<td><p>QVGA: iPhone 4S</p>
<p>VGA: iPhone 5</p>
<p>720p: iPhone 5S 이상</p></td>
<td><p>VGA: iPad 2 이상/이후/iPad 미니 1 이상</p>
<p>720p: iPad Air/iPad 미니 2/iPad 이상</p></td>
<td><p>장치 모델에 따라 최대 VGA까지</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

