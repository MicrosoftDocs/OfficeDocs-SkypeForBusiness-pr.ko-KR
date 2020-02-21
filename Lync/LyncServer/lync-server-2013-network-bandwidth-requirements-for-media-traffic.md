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
ms.openlocfilehash: a89517fb83fa5cd0c7defd62b47f7ddf9b29a303
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42192551"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="network-bandwidth-requirements-for-media-traffic-in-lync-server-2013"></a>Lync Server 2013의 미디어 트래픽에 대 한 네트워크 대역폭 요구 사항

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2015-09-24_

네트워크 계획에서 중요한 부분은 네트워크가 Lync Server로 생성되는 미디어 트래픽을 처리할 수 있도록 보장하는 것입니다. 이 섹션에서는 이러한 미디어 트래픽을 계획하는 데 도움을 줍니다.

<div>

## <a name="media-traffic-network-usage"></a>미디어 트래픽 네트워크 사용

미디어 트래픽 대역폭 사용량은 코덱 사용, 해상도 및 작업 수준과 같은 다양한 변수로 인해 계산하기 어려울 수 있습니다. 대역폭 사용량은 사용된 코덱과 스트림 작업의 영향을 받으며, 이 둘 모두 시나리오마다 다를 수 있습니다. 다음 표에는 Lync Server 2013 시나리오에서 일반적으로 사용 되는 오디오 코덱이 나와 있습니다.

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
<th>오디오 페이로드 비트 전송률(KBPS)</th>
<th>대역폭 오디오 페이로드 및 IP 헤더만(Kbps)</th>
<th>대역폭 오디오 페이로드, IP 헤더, UDP, RTP 및 SRTP(Kbps)</th>
<th>대역폭 오디오 페이로드, IP 헤더, UDP, RTP, SRTP 및 정방향 오류 정정(Kbps)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTAudio Wideband</p></td>
<td><p>피어-투-피어</p></td>
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
<td><p>전화</p></td>
<td><p>64.0</p></td>
<td><p>80.0</p></td>
<td><p>95.6</p></td>
<td><p>159.6</p></td>
</tr>
<tr class="even">
<td><p>G.722 Stereo</p></td>
<td><p>피어 투 피어, 회의</p></td>
<td><p>128.0</p></td>
<td><p>144.0</p></td>
<td><p>159.6</p></td>
<td><p>223.6</p></td>
</tr>
<tr class="odd">
<td><p>G.711</p></td>
<td><p>PSTN, 회의</p></td>
<td><p>64.0</p></td>
<td><p>80.0</p></td>
<td><p>92.0</p></td>
<td><p>156.0</p></td>
</tr>
<tr class="even">
<td><p>Siren</p></td>
<td><p>전화</p></td>
<td><p>16.0</p></td>
<td><p>32.0</p></td>
<td><p>47.6</p></td>
<td><p>63.6</p></td>
</tr>
</tbody>
</table>


위 표의 대역폭은 20ms 패킷화(초당 50패킷)를 기반으로 하며, Siren 및 G.722의 경우 회의 시나리오의 추가 SRTP(실시간 전송 프로토콜) 오버헤드를 포함하고 스트림이 100% 활성 상태인 것으로 간주합니다. FEC(정방향 오류 정정)는 링크에 패킷 손실이 있는 경우 오디오 스트림의 품질을 유지하는 데 동적으로 사용됩니다.

722 코덱의 스테레오 버전은 Lync 대화방 시스템을 기반으로 하는 시스템에서 사용 되며, 스테레오 마이크 캡처를 통해 수신기가 회의실의 여러 발언 자를을 보다 효율적으로 구분할 수 있습니다.

비디오의 경우 기본 코덱은 임시 확장성을 위한 확장 가능한 비디오 코딩 확장을 포함하는 H.264/MPEG-4 Part 10 고급 비디오 코딩 표준입니다. Lync 2010 또는 Office Communicator 2007 R2 클라이언트와의 상호 운용성을 유지 하기 위해, RTVideo 코덱은 Lync 2013과 레거시 클라이언트 간의 피어 투 피어 통화에 계속 사용 됩니다. 전화 회의 2013 세션에서 lync 2013 종점은 두 비디오 코덱을 사용 하 여 비디오를 인코딩한 후, lync 2013 및 RTVideo bitstream을 Lync 2010 또는 Office Communicator 2007 R2 클라이언트에 보낼 수 있습니다.

필요한 대역폭은 해상도, 품질 및 프레임 속도에 따라 따릅니다. 각 해상도에 대해 두 가지 비트 전송률이 관련이 있습니다.

  - **최대 페이로드 비트 전송률**   Lync 2013 끝점이이 해상도에서 지 원하는 최대 프레임 속도에서 해상도를 사용 하는 비트 전송률입니다. 이 값은 비디오의 품질 및 프레임 속도를 최상으로 유지합니다.

  - **최소 페이로드 비트 전송률**   이 비트 전송률은 Lync 2013 끝점이 다음의 낮은 해상도로 전환 하는 데 사용할 수 있습니다. 특정 해상도를 보장하기 위해서는 사용 가능한 비디오 페이로드 비트 전송률이 해당 해상도에 대한 최소 비트 전송률 아래로 떨어져서는 안됩니다. 이 값은 최대 비트 전송률이 가능하지 않거나 실용적이지 않을 경우 가능한 최저 값을 이해하는 데 도움이 되는 중요한 값입니다. 일부 사용자의 경우 낮은 비트 전송률의 비디오는 허용할 수 없는 비디오 환경으로 간주될 수 있으므로 이러한 최소 비디오 페이로드 비트 전송률을 고려할 때는 주의가 필요합니다. 사용자의 이동이 거의 없거나 전혀 없는 비디오 장면에서는 실제 비트 전송률이 일시적으로 최소 비트 전송률보다 아래로 떨어질 수 있습니다.

Lync 2013은 더 많은 해상도를 지원 합니다. 이를 통해 여러 가지 네트워크 대역폭 및 수신 클라이언트 기능에 맞게 조정할 수 있습니다. 또한 Lync 2013에 대 한 기본 가로 세로 비율이 16:9로 변경 되었습니다. 16:9 가로 세로 비율의 캡처를 허용하지 않는 웹 캠에서는 여전히 4:3 가로 세로 비율이 지원됩니다.

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
<th>최대 비디오 페이로드 비트 전송률(Kbps)</th>
<th>최소 비디오 페이로드 비트 전송률(Kbps)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>.H. 264</p></td>
<td><p>320x180 (16:9)</p>
<p>212x160 (4:3)</p></td>
<td><p>250</p></td>
<td><p>15 </p></td>
</tr>
<tr class="even">
<td><p>.H-264/RTVideo</p></td>
<td><p>424x240 (16:9))</p>
<p>320x240 (4:3</p></td>
<td><p>350</p></td>
<td><p>100</p></td>
</tr>
<tr class="odd">
<td><p>.H. 264</p></td>
<td><p>480x270 (16:9)</p>
<p>424x320 (4:3)</p></td>
<td><p>450</p></td>
<td><p>200</p></td>
</tr>
<tr class="even">
<td><p>.H-264/RTVideo</p></td>
<td><p>640x360 (16:9)</p>
<p>640x480 (4:3)</p></td>
<td><p>800</p></td>
<td><p>300</p></td>
</tr>
<tr class="odd">
<td><p>.H. 264</p></td>
<td><p>848x480 (16:9)</p></td>
<td><p>1500</p></td>
<td><p>400</p></td>
</tr>
<tr class="even">
<td><p>.H. 264</p></td>
<td><p>960x540 (16:9)</p></td>
<td><p>2000</p></td>
<td><p>500</p></td>
</tr>
<tr class="odd">
<td><p>.H-264/RTVideo</p></td>
<td><p>해상도 1280x720 (16:9)</p></td>
<td><p>2500</p></td>
<td><p>700</p></td>
</tr>
<tr class="even">
<td><p>.H. 264</p></td>
<td><p>해상도 1920x1080 (16:9)</p></td>
<td><p>4000</p></td>
<td><p>1500</p></td>
</tr>
<tr class="odd">
<td><p>.H-264/RTVideo</p></td>
<td><p>960x144 (20:3)</p></td>
<td><p>500</p></td>
<td><p>15 </p></td>
</tr>
<tr class="even">
<td><p>.H. 264</p></td>
<td><p>1280x192 (20:3)</p></td>
<td><p>1000</p></td>
<td><p>250</p></td>
</tr>
<tr class="odd">
<td><p>.H. 264</p></td>
<td><p>1920x288 (20:3)</p></td>
<td><p>2000</p></td>
<td><p>500</p></td>
</tr>
</tbody>
</table>


비디오 FEC는 사용된 경우에 비디오 페이로드 비트 전송률에 포함되므로 비디오 FEC가 포함된 값과 비디오 FEC가 포함되지 않은 값이 별도로 없습니다.

끝점에서는 오디오 또는 비디오 패킷을 지속적으로 스트리밍하지 않습니다. 시나리오에 따라 패킷이 스트림에 대해 전송되는 빈도를 나타내는 스트림 작업 수준이 다릅니다. 스트림 작업은 미디어 및 시나리오에 따라 달라지면 사용되는 코덱과는 관련이 없습니다. 피어 투 피어 시나리오의 경우:

  - 끝점에서 사용자가 발표할 때만 스트림을 보냅니다.

  - 두 참가자 모두 오디오 스트림을 받습니다.

  - 비디오를 사용하는 경우 두 끝점 모두 전체 통화 중에 비디오 스트림을 보내고 받습니다.

  - 움직임이 거의 없거나 전혀 없는 비디오 장면의 경우 비디오 코덱이 변화가 없는 비디오 지역의 인코딩을 건너뛸 수 있으므로 실제 비트 전송률이 일시적으로 매우 낮아질 수 있습니다.

회의 시나리오의 경우:

  - 끝점에서 사용자가 발표할 때만 스트림을 보냅니다.

  - 모든 참가자가 오디오 스트림을 받습니다.

  - 비디오를 사용하는 경우 모든 참가자는 최대 5개의 수신 비디오 스트림과 1개의 파노라마(예: 가로 세로 비율 20:3) 비디오 스트림을 수신할 수 있습니다. 기본적으로 5개의 수신 비디오 스트림은 현재 발언자 기록을 기반으로 하지만 사용자가 비디오 스트림을 수신하려는 참가자를 수동으로 선택할 수도 있습니다.

  - 사용자의 송신 비디오 스트림을 켜는 각 참가자는 하나 이상의 비디오 스트림을 전송합니다. Lync 2013에서는 모든 수신 클라이언트의 비디오 품질을 최적화 하기 위해 최대 5 개의 비디오 스트림을 보내는 기능을 추가 합니다. 전송되는 비디오 스트림의 실제 개수는 CPU 성능, 사용 가능한 업링크 대역폭 및 특정 비디오 스트림을 요청하는 수신 클라이언트 수를 기반으로 전송자에 의해 결정됩니다. 가장 일반적으로 레거시 클라이언트가 회의에 참가할 때는 한 개의 H.264와 한 개의 RTVideo 비디오 스트림이 전송됩니다. 또 다른 일반적인 시나리오에서는 서로 다른 수신자 요청을 수용할 수 있도록 여러 개의 H.264 비디오 스트림(예: 서로 다른 비디오 해상도 사용)이 전송됩니다.

오디오 및 비디오 미디어의 RTP(Real-Time Transport Protocol)에 필요한 대역폭 외에 RTCP(Real-time Transmission Control Protocol)에도 대역폭이 필요합니다. RTCP는 통계 보고 및 RTP 스트림의 대역 외 제어에 사용됩니다. 계획할 때 아래 RTCP 트래픽 표에 나와 있는 대역폭을 사용할 수 있습니다. 이러한 값은 RTCP에 사용되는 최대 대역폭을 나타내며, 제어 데이터가 다르기 때문에 오디오 스트림과 비디오 스트림 간에 차이가 있습니다.

### <a name="rtcp-bandwidth"></a>RTCP 대역폭

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>미디어</th>
<th>RTCP 최대 대역폭(Kbps)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>오디오만</p></td>
<td><p>2-5</p></td>
</tr>
<tr class="even">
<td><p>비디오(H.264 또는 RTVideo만 전송/수신됨)</p></td>
<td><p>10 </p></td>
</tr>
<tr class="odd">
<td><p>비디오(H.264 및 RTVideo가 전송/수신됨)</p></td>
<td><p>15 </p></td>
</tr>
</tbody>
</table>


용량 계획 시 다음 두 대역폭을 고려합니다.

  - **최대 대역폭 (FEC**   불포함)-FEC 없이 시나리오에 사용 되는 일반적인 코덱과 스트림의 일반적인 작업을 포함 하 여 스트림에 사용 되는 최대 대역폭을 만듭니다.이는 스트림이 100% activity이 고 FEC 사용을 트리거하는 패킷 손실이 없는 경우의 대역폭입니다.이는 지정 된 시나리오에서 코덱을 사용 하도록 허용 하기 위해 할당 해야 하는 대역폭의 양을 계산 하는 데 유용 합니다. 

  - **최대 대역폭 (FEC**   )-stream의 일반적인 작업과 FEC에서 사용 되는 일반적인 코덱을 비롯 하 여 스트림이 소비 하는 최대 대역폭을 포함 합니다. 이는 stream이 100% activity이 고 FEC 사용을 트리거하여 품질을 개선 하기 위해 패킷 손실이 발생 하는 경우의 대역폭입니다. 이는 지정 된 시나리오에서 코덱을 사용 하도록 허용 하기 위해 할당 해야 하는 대역폭의 양을 계산 하 고 FEC을 사용 하 여 패킷 손실 조건에 품질을 유지할 수 있도록 하는 데 관심을 두어야 합니다. 

다음 표에는 일반적으로 추가 대역폭 값인 **일반 대역폭이**나열 되어 있습니다. 이는 스트림의 일반적인 작업과 시나리오에서 사용 되는 일반적인 코덱을 포함 하 여 스트림이 소비 하는 평균 대역폭입니다. 이 대역폭은 지정 된 시간에 미디어 트래픽이 소비 하는 대역폭의 양을 대략적으로 결정 하는 데 사용할 수 있지만, 작업 수준이 average 보다 높은 경우에는 개별 통화가이 값을 초과 하기 때문에 용량 계획에 사용 하면 안 됩니다. 아래 표의 일반적인 비디오 스트림 대역폭은 측정 된 고객 데이터에서 관찰 된 것과 같은 다양 한 비디오 해상도를 기반으로 합니다. 예를 들어 피어 투 피어 세션에서 대부분의 사용자는 기본 비디오 렌더링 창을 사용 하지만 일부 사용자는 비디오 해상도가 더 높은 것을 허용 하도록 Lync 응용 프로그램을 향상 시키거나 최대화 합니다.

다음 표에서는 여러 시나리오에 대한 세 가지 대역폭 값을 제공합니다.

### <a name="audiovideo-capacity-planning-for-peer-to-peer-sessions"></a>피어 투 피어 세션에 대한 오디오/비디오 용량 계획

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
<th>코덱</th>
<th>일반적인 스트림 대역폭(Kbps)</th>
<th>FEC 제외 최대 스트림 대역폭</th>
<th>FEC 포함 최대 스트림 대역폭</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>오디오만</p></td>
<td><p>RTAudio Wideband</p></td>
<td><p>39.8</p></td>
<td><p>62</p></td>
<td><p>91</p></td>
</tr>
<tr class="even">
<td><p>오디오만</p></td>
<td><p>RTAudio Narrowband</p></td>
<td><p>29.3</p></td>
<td><p>44.8</p></td>
<td><p>56.6</p></td>
</tr>
<tr class="odd">
<td><p>Lync 2013 끝점을 호출할 때 기본 비디오</p></td>
<td><p>.H. 264</p></td>
<td><p>460</p></td>
<td><p>4010(최대 해상도 1920x1080)</p></td>
<td><p>해당 없음</p></td>
</tr>
<tr class="even">
<td><p>Lync 2010 또는 Office Communicator 2007 R2 끝점을 호출할 때 기본 비디오</p></td>
<td><p>RTVideo</p></td>
<td><p>460</p></td>
<td><p>2510(최대 해상도 1280x720)</p></td>
<td><p>해당 없음</p></td>
</tr>
<tr class="odd">
<td><p>Lync 2013 끝점을 호출할 때 파노라마 비디오</p></td>
<td><p>.H. 264</p></td>
<td><p>190</p></td>
<td><p>2010(최대 해상도 1920x288)</p></td>
<td><p>해당 없음</p></td>
</tr>
<tr class="even">
<td><p>Lync 2010 또는 Office Communicator 2007 R2 끝점을 호출할 때 파노라마 비디오</p></td>
<td><p>RTVideo</p></td>
<td><p>190</p></td>
<td><p>510(최대 해상도 960x144)</p></td>
<td><p>해당 없음</p></td>
</tr>
</tbody>
</table>


### <a name="audiovideo-capacity-planning-for-conferences"></a>전화 회의에 대한 오디오/비디오 용량 계획

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
<th>일반적인 코덱</th>
<th>일반적인 스트림 대역폭(Kbps)</th>
<th>FEC 제외 최대 스트림 대역폭</th>
<th>FEC 포함 최대 스트림 대역폭</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>오디오만</p></td>
<td><p>722</p></td>
<td><p>46.1</p></td>
<td><p>100.6</p></td>
<td><p>164.6</p></td>
</tr>
<tr class="even">
<td><p>오디오만</p></td>
<td><p>Siren</p></td>
<td><p>25.5</p></td>
<td><p>52.6</p></td>
<td><p>68.6</p></td>
</tr>
<tr class="odd">
<td><p>기본 비디오 수신</p></td>
<td><p>H.264 및/또는 RTVideo</p></td>
<td><p>260</p></td>
<td><p>8015</p></td>
<td><p>해당 없음</p></td>
</tr>
<tr class="even">
<td><p>기본 비디오 송신</p></td>
<td><p>H.264 및/또는 RTVideo</p></td>
<td><p>270</p></td>
<td><p>8015</p></td>
<td><p>해당 없음</p></td>
</tr>
<tr class="odd">
<td><p>파노라마 비디오 수신</p></td>
<td><p>H.264 및/또는 RTVideo</p></td>
<td><p>190</p></td>
<td><p>2010(최대 해상도 1920x288)</p></td>
<td><p>해당 없음</p></td>
</tr>
<tr class="even">
<td><p>파노라마 비디오 송신</p></td>
<td><p>H.264 및/또는 RTVideo</p></td>
<td><p>190</p></td>
<td><p>2515(다중 해상도/코덱을 사용하여 비트스트림 전송)</p></td>
<td><p>해당 없음</p></td>
</tr>
</tbody>
</table>


기본 비디오의 경우 일반 및 최대 스트림 대역폭은 수신된 모든 비디오 스트림 및 송신된 모든 비디오 스트림에 대해 집계된 대역폭입니다. 다중 비디오 스트림의 경우에는 여러 비디오 회의에서 사용되는 콘텐츠 공유로 인해 비디오 창이 훨씬 작아지고 따라서 비디오 해상도도 작아지기 때문에 피어 투 피어 시나리오보다 일반 비디오 대역폭이 더 작습니다. 지원되는 최대 집계된 비디오 페이로드 대역폭은 송신 및 수신 스트림 모두 8000Kbps이며 두 개의 수신 1920x1080p 비디오 스트림이 있는 경우에 사용됩니다.

파노라마 비디오의 일반 스트림 대역폭은 최대 960x144 파노라마 비디오로만 스트리밍하는 현재 사용 가능한 장치를 기반으로 합니다. 1920x288 파노라마 비디오를 지원하는 장치를 사용할 수 있게 되면 일반 스트림 대역폭도 늘어날 예정입니다.

### <a name="audio-capacity-planning-for-pstn"></a>PSTN에 대한 오디오 용량 계획

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
<th>일반적인 코덱</th>
<th>일반적인 스트림 대역폭(Kbps)</th>
<th>FEC 제외 최대 스트림 대역폭</th>
<th>FEC 포함 최대 스트림 대역폭</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>오디오만</p></td>
<td><p>G.711 (전화 회의의 PSTN 참가자 포함)</p></td>
<td><p>64.8</p></td>
<td><p>97</p></td>
<td><p>161</p></td>
</tr>
<tr class="even">
<td><p>오디오만</p></td>
<td><p>RTAudio Narrowband</p></td>
<td><p>30.9</p></td>
<td><p>44.8</p></td>
<td><p>56.6</p></td>
</tr>
</tbody>
</table>


이러한 표의 네트워크 대역폭은 단방향 트래픽만 나타내며 각 스트림에 대해 5Kbps의 RTCP 트래픽 오버헤드를 포함합니다. 비디오의 경우 최대 비디오 비트 전송률은 최대 스트림을 계산하는 데 사용됩니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

