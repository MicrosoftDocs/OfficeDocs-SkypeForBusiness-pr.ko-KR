---
title: Lync Server 2013 미디어 트래픽에 대 한 네트워크 대역폭 요구 사항
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Network bandwidth requirements for media traffic
ms:assetid: 83e83b16-0f0e-4d87-901a-0faa4618cdc2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688118(v=OCS.15)
ms:contentKeyID: 49733716
ms.date: 09/25/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 684f13a10c066e8902bed0024d7546017450ee9e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765929"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="network-bandwidth-requirements-for-media-traffic-in-lync-server-2013"></a>Lync Server 2013의 미디어 트래픽에 대 한 네트워크 대역폭 요구 사항

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2015-09-24_

네트워크 계획의 중요 한 부분은 네트워크에서 Lync Server가 생성 한 미디어 트래픽을 처리할 수 있는지 확인 하는 것입니다. 이 섹션에서는 해당 미디어 트래픽을 계획 하는 데 도움이 됩니다.

<div>

## <a name="media-traffic-network-usage"></a>미디어 트래픽 네트워크 사용

미디어 트래픽 대역폭 사용은 코덱 사용, 해상도, 활동 수준과 같은 다양 한 변수의 수로 인해 계산 하는 데 어려움이 있을 수 있습니다. 대역폭 사용은 사용 되는 코덱의 함수와 스트림의 작업 (시나리오 간에 따라 다름)입니다. 다음 표에는 Lync Server 2013 시나리오에서 자주 사용 하는 오디오 코덱이 나와 있습니다.

### <a name="audio-codec-bandwidth"></a>오디오 코덱 대역폭

<table style="width:100%;">
<colgroup>
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
</colgroup>
<thead>
<tr class="header">
<th>오디오 코덱</th>
<th>시나리오</th>
<th>오디오 페이로드 비트 전송률 (KBPS)</th>
<th>대역폭 오디오 페이로드 및 IP 머리글만 (Kbps)</th>
<th>대역폭 오디오 페이로드, IP 헤더, UDP, RTP 및 SRTP (Kbps)</th>
<th>대역폭 오디오 페이로드, IP 헤더, UDP, RTP, SRTP 및 착신 전환 오류 수정 (Kbps)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTAudio 광대역</p></td>
<td><p>피어 투 피어</p></td>
<td><p>29.0</p></td>
<td><p>45.0</p></td>
<td><p>57.0</p></td>
<td><p>86.0</p></td>
</tr>
<tr class="even">
<td><p>RTAudio Narrowband</p></td>
<td><p>피어 투 피어, PSTN</p></td>
<td><p>11.8</p></td>
<td><p>27.8</p></td>
<td><p>39.8</p></td>
<td><p>51.6</p></td>
</tr>
<tr class="odd">
<td><p>722</p></td>
<td><p>회의</p></td>
<td><p>64.0</p></td>
<td><p>80.0</p></td>
<td><p>95.6</p></td>
<td><p>159.6</p></td>
</tr>
<tr class="even">
<td><p>G. 722 스테레오</p></td>
<td><p>피어 투 피어, 회의</p></td>
<td><p>128.0</p></td>
<td><p>144.0</p></td>
<td><p>159.6</p></td>
<td><p>223.6</p></td>
</tr>
<tr class="odd">
<td><p>711</p></td>
<td><p>PSTN, 회의</p></td>
<td><p>64.0</p></td>
<td><p>80.0</p></td>
<td><p>92.0</p></td>
<td><p>156.0</p></td>
</tr>
<tr class="even">
<td><p>사이렌</p></td>
<td><p>회의</p></td>
<td><p>16.0</p></td>
<td><p>32.0</p></td>
<td><p>47.6</p></td>
<td><p>63.6</p></td>
</tr>
</tbody>
</table>


이전 표의 대역폭 번호는 20ms packetization (초당 50 패킷)와 Siren 및 G에 대 한 추가 보안 실시간 전송 프로토콜 (SRTP)을 포함 하 고 있으며, 722에는 회의 시나리오에서 발생 하는 추가적인 안전 하 고, 스트림이 100% 활성 인 것으로 가정 합니다. FEC (정방향 오류 수정)는 오디오 스트림의 품질을 유지 하는 데 도움이 되는 링크에 패킷이 손실 되는 경우 동적으로 사용 됩니다.

722 코덱의 스테레오 버전은 Lync 대화방 시스템을 기반으로 하는 시스템에서 사용 되며,이를 통해 수신기가 회의실의 여러 talkers를 더 효과적으로 구분할 수 있도록 하는 스테레오 마이크 캡처를 사용할 수 있습니다.

비디오의 경우 기본 코덱은 고속 확장성에 대 한 확장 가능한 비디오 코딩 확장과 함께 H/264/MPEG-4 부품 10의 고급 영상 코딩 표준입니다. Lync 2010 또는 Office Communicator 2007 R2 클라이언트와의 상호 운용성을 유지 하기 위해 Lync 2013 및 레거시 클라이언트 간의 피어 투 피어 통화에는 여전히 RTVideo 코덱이 사용 됩니다. Lync 2013와 레거시 클라이언트가 모두 포함 된 회의 세션에서 Lync 2013 끝점은 두 비디오 코덱을 모두 사용 하 여 비디오를 인코딩한 후 Lync 2013 및 RTVideo bitstream에 Lync 2010 또는 Office Communicator 2007 R2 클라이언트로 보낼 수 있습니다.

필요한 대역폭은 해상도, 품질 및 프레임 속도에 따라 달라 집니다. 각 해상도에 대해 흥미로운 두 가지 비트 전송률이 있습니다.

  - **최대 페이로드 비트 전송률**   이 해상도에서 지원 되는 최대 프레임 속도로는 Lync 2013 끝점에서 해상도를 사용 하는 비트 전송률입니다. 이 값은 최고 품질과 프레임 속도의 비디오를 허용 하기 때문에 재미 있습니다.

  - **최소 페이로드 비트 전송률**   다음의 낮은 해상도로 전환 되는 Lync 2013 끝점의 비트 전송률입니다. 특정 해상도를 보장 하기 위해 사용 가능한 비디오 페이로드 비트 전송률이 해당 해상도에 대 한이 최소 비트 전송률을 벗어나는 것이 아니어야 합니다. 이 값은 최대 비트 전송률을 사용할 수 없거나 실용적 일 때 가능한 가장 낮은 값을 이해할 수 있도록 하는 데 유용 합니다. 일부 사용자의 경우 낮은 비트 전송률 비디오는 허용 되지 않는 비디오 환경으로 간주 될 수 있으므로이 최소 비디오 페이로드 비트 전송률을 고려할 때는 주의를 기울여야 합니다. 사용자가 거의 또는 전혀 이동 하지 않고 비디오 장면을 사용 하는 경우 실제 비트 전송률이 일시적으로 최소 비트 전송률 미만으로 떨어질 수 있습니다.

Lync 2013는 더 많은 해상도를 지원 합니다. 이렇게 하면 다양 한 네트워크 대역폭과 클라이언트 접근 권한 값을 보다 효율적으로 조정할 수 있습니다. 또한 Lync 2013에 대 한 기본 가로 세로 비율이 16:9로 변경 되었습니다. 4:3 가로 세로 비율은 16:9 가로 세로 비율에서 캡처를 허용 하지 않는 웹캠 에서도 지원 됩니다.

### <a name="video-resolution-bandwidth"></a>비디오 해상도 대역폭

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>비디오 코덱</th>
<th>해상도 및 가로 세로 비율</th>
<th>최대 비디오 페이로드 비트 전송률 (Kbps)</th>
<th>최소 비디오 페이로드 비트 전송률 (Kbps)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>H. 264</p></td>
<td><p>320x180 (16:9)</p>
<p>212x160 (4:3)</p></td>
<td><p>250</p></td>
<td><p>~</p></td>
</tr>
<tr class="even">
<td><p>H./RTVideo</p></td>
<td><p>424x240 (16:9))</p>
<p>320x240 (4:3</p></td>
<td><p>350</p></td>
<td><p>100</p></td>
</tr>
<tr class="odd">
<td><p>H. 264</p></td>
<td><p>480x270 (16:9)</p>
<p>424x320 (4:3)</p></td>
<td><p>450</p></td>
<td><p>200</p></td>
</tr>
<tr class="even">
<td><p>H./RTVideo</p></td>
<td><p>640x360 (16:9)</p>
<p>640x480 (4:3)</p></td>
<td><p>800</p></td>
<td><p>300</p></td>
</tr>
<tr class="odd">
<td><p>H. 264</p></td>
<td><p>848x480 (16:9)</p></td>
<td><p>1500</p></td>
<td><p>400</p></td>
</tr>
<tr class="even">
<td><p>H. 264</p></td>
<td><p>960x540 (16:9)</p></td>
<td><p>2000</p></td>
<td><p>500</p></td>
</tr>
<tr class="odd">
<td><p>H./RTVideo</p></td>
<td><p>1280x720 (16:9)</p></td>
<td><p>2500</p></td>
<td><p>700</p></td>
</tr>
<tr class="even">
<td><p>H. 264</p></td>
<td><p>1920x1080 (16:9)</p></td>
<td><p>4000</p></td>
<td><p>1500</p></td>
</tr>
<tr class="odd">
<td><p>H./RTVideo</p></td>
<td><p>960x144-4 (20:3)</p></td>
<td><p>500</p></td>
<td><p>~</p></td>
</tr>
<tr class="even">
<td><p>H. 264</p></td>
<td><p>1280x192 (20:3)</p></td>
<td><p>1000</p></td>
<td><p>250</p></td>
</tr>
<tr class="odd">
<td><p>H. 264</p></td>
<td><p>1920x288 (20:3)</p></td>
<td><p>2000</p></td>
<td><p>500</p></td>
</tr>
</tbody>
</table>


비디오 FEC 사용 될 때 비디오 페이로드 비트 전송률에 포함 되어 비디오 FEC 및 비디오 FEC 없이는 별도의 값이 없습니다.

끝점은 오디오 또는 비디오 패킷을 계속 스트리밍할 수 없습니다. 시나리오에 따라 스트림에 대해 패킷이 전송 되는 빈도를 나타내는 다양 한 수준의 스트림 활동이 있습니다. 스트림의 활동은 미디어와 시나리오에 따라 다르며, 사용 중인 코덱에 종속 되지 않습니다. 피어 투 피어 시나리오에서 다음을 수행 합니다.

  - 끝점은 사용자가 말할 때만 오디오 스트림을 보냅니다.

  - 두 참가자 모두 오디오 스트림을 받습니다.

  - 비디오를 사용 하는 경우 양쪽 끝점에서 전체 통화 중에 비디오 스트림을 보내고 받습니다.

  - 움직임이 거의 없거나 전혀 없는 비디오 장면의 경우 비디오 코덱이 비디오의 인코딩 영역을 변경 하지 않고 건너뛰기 때문에 실제 비트 전송률이 일시적으로 매우 낮을 수 있습니다.

회의 시나리오에서 다음을 수행 합니다.

  - 끝점은 사용자가 말할 때만 오디오 스트림을 보냅니다.

  - 모든 참가자가 오디오 스트림을 받습니다.

  - 비디오를 사용 하는 경우 모든 참가자는 최대 5 개의 수신 비디오 스트림 및 하나의 파노라마 (예: 가로 세로 비율 20:3) 비디오 스트림을 받을 수 있습니다. 기본적으로 5 개의 수신 비디오 스트림은 활성 발표자 기록을 기반으로 하지만 사용자가 비디오 스트림을 수신 하려는 참가자를 수동으로 선택할 수도 있습니다.

  - 사용자의 전송 비디오 스트림을 설정 하는 각 참가자는 하나 이상의 비디오 스트림을 보냅니다. Lync 2013는 최대 5 개의 비디오 스트림을 보내는 기능을 추가 하 여 받는 모든 클라이언트에 대 한 비디오 품질을 최적화 합니다. 보내는 비디오 스트림의 실제 수는 CPU 용량, 사용 가능한 업링크 대역폭, 특정 비디오 스트림을 요청 하는 수신 클라이언트 수에 따라 보낸 사람에 의해 결정 됩니다. 가장 일반적인 경우는 레거시 클라이언트가 컨퍼런스에 참가 하는 경우 하나의 .H 및 RTVideo 비디오 스트림 하나를 전송 하는 것입니다. 또 다른 일반적인 시나리오는 다양 한 비디오 해상도를 사용 하 여 여러 개의 H 264 비디오 스트림이 다른 수신기 요청을 수용 하도록 보내는 것입니다.

오디오 및 비디오 미디어에 대 한 RTP (실시간 전송 프로토콜) 트래픽에 필요한 대역폭 외에도 RTCP (실시간 전송 제어 프로토콜)에 대 한 대역폭이 필요 합니다. RTCP는 RTP 스트림의 대역외 제어 및 통계 보고에 사용 됩니다. 계획을 위해 RTCP 트래픽에 대해 다음 표의 대역폭 번호를 사용 합니다. 이러한 값은 RTCP에 사용 되는 최대 대역폭을 나타내며, 컨트롤 데이터의 차이로 인해 오디오와 비디오 스트림 간에 차이가 있습니다.

### <a name="rtcp-bandwidth"></a>RTCP 대역폭

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>미디어</th>
<th>RTCP 최대 대역폭 (Kbps)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>오디오</p></td>
<td><p>5mb</p></td>
</tr>
<tr class="even">
<td><p>비디오 (H e s e e r i p e e i p//또는 RTVideo 보내거나 받을</p></td>
<td><p>1천만</p></td>
</tr>
<tr class="odd">
<td><p>비디오 (H e r a p s 및 RTVideo 전송/수신)</p></td>
<td><p>~</p></td>
</tr>
</tbody>
</table>


용량 계획을 위해 다음 두 가지 대역폭을 사용 하는 것이 중요 합니다.

  - **FEC 없는 최대 대역폭**   스트림의 일반적인 작업 및 FEC 없이 시나리오에 사용 되는 일반적인 코덱을 비롯 하 여 스트림이 소모 하는 최대 대역폭입니다.스트림이 100% activity이 고 FEC 사용을 트리거하는 패킷 손실이 없는 경우의 대역폭입니다.이는 지정 된 시나리오에서 코덱을 사용할 수 있도록 할당 해야 하는 대역폭의 양을 계산 하는 데 흥미롭습니다. 

  - **FEC를 사용 하는 최대 대역폭**   은 스트림의 일반적인 작업과 FEC에서 시나리오에 사용 되는 일반적인 코덱을 비롯 하 여 스트림이 소모 하는 최대 대역폭을 포함 합니다. 이는 스트림이 100% 활동에 있고, 품질 개선을 위해 FEC 사용을 트리거하는 패킷 손실로 인해 발생 하는 대역폭입니다. 이는 특정 시나리오에서 코덱을 사용할 수 있도록 할당 해야 하는 대역폭을 계산 하 고 FEC를 사용 하 여 패킷 손실 조건에 품질을 유지할 수 있도록 하는 데 흥미롭습니다. 

다음 표에는 **일반 대역폭과**추가 대역폭 값도 나열 되어 있습니다. 이는 스트림의 일반적인 작업과 시나리오에 사용 되는 일반적인 코덱을 비롯 하 여 스트림이 소모 하는 평균 대역폭입니다. 이 대역폭은 지정 된 시간에 미디어 트래픽에 의해 소모 되는 대역폭의 크기를 대략적으로 결정 하는 데 사용 될 수 있지만, 작업 수준이 평균 보다 높은 경우 개별 호출이이 값을 초과 하기 때문에 용량 계획에 사용 하지 않아야 합니다. 아래 표에 나와 있는 일반적인 비디오 스트림 대역폭은 측정 한 고객 데이터에서 관측 된 다양 한 비디오 해상도의 혼합을 기준으로 합니다. 예를 들어 피어 투 피어 세션에서 대부분의 사용자는 기본 비디오 렌더링 창을 사용 하 고, 일부 사용자는 빠른 비디오 해상도를 허용 하도록 Lync 응용 프로그램을 늘리거나 최대화 합니다.

다음 표에서는 다양 한 시나리오에 대해 이러한 세 가지 대역폭 값을 제공 합니다.

### <a name="audiovideo-capacity-planning-for-peer-to-peer-sessions"></a>피어 투 피어 세션에 대 한 오디오/비디오 용량 계획

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
<th>미디어</th>
<th>코덱이나</th>
<th>일반적인 스트림 대역폭 (Kbps)</th>
<th>FEC 없는 최대 스트림 대역폭</th>
<th>FEC 있는 최대 스트림 대역폭</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>오디오</p></td>
<td><p>RTAudio 광대역</p></td>
<td><p>39.8</p></td>
<td><p>62</p></td>
<td><p>91</p></td>
</tr>
<tr class="even">
<td><p>오디오</p></td>
<td><p>RTAudio Narrowband</p></td>
<td><p>29.3</p></td>
<td><p>44.8</p></td>
<td><p>56.6</p></td>
</tr>
<tr class="odd">
<td><p>Lync 2013 끝점으로 전화를 걸 때의 기본 비디오</p></td>
<td><p>H. 264</p></td>
<td><p>460</p></td>
<td><p>4010 (1920x1080의 최대 해상도)</p></td>
<td><p>해당 없음</p></td>
</tr>
<tr class="even">
<td><p>Lync 2010 또는 Office Communicator 2007 R2 끝점으로 전화를 걸 때의 기본 비디오</p></td>
<td><p>RTVideo</p></td>
<td><p>460</p></td>
<td><p>2510 (1280x720의 최대 해상도)</p></td>
<td><p>해당 없음</p></td>
</tr>
<tr class="odd">
<td><p>Lync 2013 끝점을 호출할 때 파노라마 비디오가 나타난다</p></td>
<td><p>H. 264</p></td>
<td><p>190</p></td>
<td><p>2010 (1920x288의 최대 해상도)</p></td>
<td><p>해당 없음</p></td>
</tr>
<tr class="even">
<td><p>Lync 2010 또는 Office Communicator 2007 R2 끝점으로 전화를 걸 때 파노라마 비디오</p></td>
<td><p>RTVideo</p></td>
<td><p>190</p></td>
<td><p>510 (96x 0x144의 최대 해상도)</p></td>
<td><p>해당 없음</p></td>
</tr>
</tbody>
</table>


### <a name="audiovideo-capacity-planning-for-conferences"></a>회의를 위한 오디오/비디오 용량 계획

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
<th>미디어</th>
<th>일반 코덱</th>
<th>일반적인 스트림 대역폭 (Kbps)</th>
<th>FEC 없는 최대 스트림 대역폭</th>
<th>FEC 있는 최대 스트림 대역폭</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>오디오</p></td>
<td><p>722</p></td>
<td><p>46.1</p></td>
<td><p>100.6</p></td>
<td><p>164.6</p></td>
</tr>
<tr class="even">
<td><p>오디오</p></td>
<td><p>사이렌</p></td>
<td><p>25.5</p></td>
<td><p>52.6</p></td>
<td><p>68.6</p></td>
</tr>
<tr class="odd">
<td><p>기본 비디오 수신</p></td>
<td><p>H. e 8 및/또는 RTVideo</p></td>
<td><p>260</p></td>
<td><p>8015</p></td>
<td><p>해당 없음</p></td>
</tr>
<tr class="even">
<td><p>기본 비디오 보내기</p></td>
<td><p>H. e 8 및/또는 RTVideo</p></td>
<td><p>270</p></td>
<td><p>8015</p></td>
<td><p>해당 없음</p></td>
</tr>
<tr class="odd">
<td><p>파노라마 비디오 수신</p></td>
<td><p>H. e 8 및/또는 RTVideo</p></td>
<td><p>190</p></td>
<td><p>2010 (1920x288의 최대 해상도)</p></td>
<td><p>해당 없음</p></td>
</tr>
<tr class="even">
<td><p>파노라마 비디오 보내기</p></td>
<td><p>H. e 8 및/또는 RTVideo</p></td>
<td><p>190</p></td>
<td><p>2515 (여러 해상도/코덱을 사용 하 여 bitstreams 전송</p></td>
<td><p>해당 없음</p></td>
</tr>
</tbody>
</table>


기본 비디오의 경우 일반 및 최대 스트림 대역폭은 수신 되는 모든 비디오 스트림과 모든 비디오 스트림 보내기에 걸쳐 집계 된 대역폭입니다. 비디오 스트림이 여러 개 있는 경우에도 많은 비디오 회의에서 콘텐츠 공유를 사용 하 여 비디오 창이 작아 비디오 해상도가 축소 되므로 일반적인 영상 대역폭이 피어 투 피어 시나리오 보다 작습니다. 지원 되는 최대 집계 비디오 페이로드 대역폭은 두 가지로 이루어진 송신 및 수신 스트림 (예: 둘 이상의 수신 1920x1080p 비디오 스트림이 있는 경우)에 대해 8000 Kbps입니다.

파노라마 비디오에 대 한 일반적인 스트림 대역폭은 96f0x144 파노라마 비디오만 스트리밍하는 현재 사용 가능한 장치를 기반으로 합니다. 1920x288 파노라마 비디오가 있는 장치를 사용할 수 있게 되 면 일반적인 스트림 대역폭이 증가할 것으로 예상 됩니다.

### <a name="audio-capacity-planning-for-pstn"></a>PSTN에 대 한 오디오 용량 계획

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
<th>미디어</th>
<th>일반 코덱</th>
<th>일반적인 스트림 대역폭 (Kbps)</th>
<th>FEC 없는 최대 스트림 대역폭</th>
<th>FEC 있는 최대 스트림 대역폭</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>오디오</p></td>
<td><p>711 (회의의 PSTN 참가자가 포함 되어 있습니다.)</p></td>
<td><p>64.8</p></td>
<td><p>97</p></td>
<td><p>161</p></td>
</tr>
<tr class="even">
<td><p>오디오</p></td>
<td><p>RTAudio Narrowband</p></td>
<td><p>30.9</p></td>
<td><p>44.8</p></td>
<td><p>56.6</p></td>
</tr>
</tbody>
</table>


이러한 테이블의 네트워크 대역폭 번호는 단방향 트래픽만 나타내며 각 스트림에 대해 RTCP 트래픽 오버 헤드에 대해 5ghz를 포함 합니다. 비디오용 최대 비디오 비트 전송률이 최대 스트림을 계산 하는 데 사용 됩니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

