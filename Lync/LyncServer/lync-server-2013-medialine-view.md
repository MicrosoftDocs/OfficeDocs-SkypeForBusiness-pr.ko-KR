---
title: 'Lync Server 2013: MediaLine'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: MediaLine view
ms:assetid: 132eca13-8913-4218-9eff-4960ced8c3dc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687972(v=OCS.15)
ms:contentKeyID: 49733560
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7aebd16d8bd2efaf8deeb6752deeb199411ab125
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763006"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="medialine-view-in-lync-server-2013"></a>Lync Server 2013의 MediaLine

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-03_

MediaLine는 데이터베이스의 각 미디어 라인에 대 한 정보를 저장 합니다. 일반적으로 하나의 오디오 세션에 오디오 미디어 선이 하나 있습니다. 하나의 오디오 및 비디오 (A/V) 세션에는 일반적으로 오디오 미디어 회선 하 나와 비디오 미디어 라인 하나가 포함 됩니다. 그러나 회의 장치를 사용 하거나 갤러리 보기를 사용 하는 경우에는 세션에 두 개의 비디오 미디어 줄이 포함 될 수 있습니다. 이 보기는 Microsoft Lync Server 2013에서 도입 되었습니다.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>열</th>
<th>데이터 형식</th>
<th>세부적인</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ConferenceDateTime</p></td>
<td><p>dmtf</p></td>
<td><p><a href="lync-server-2013-medialine-table.md">Lync Server 2013의 Medialine 테이블</a>에서 참조 합니다.</p></td>
</tr>
<tr class="even">
<td><p>SessionSeq</p></td>
<td><p>int</p></td>
<td><p><a href="lync-server-2013-medialine-table.md">Lync Server 2013의 Medialine 테이블</a>에서 참조 합니다.</p></td>
</tr>
<tr class="odd">
<td><p>MediaLineLabel</p></td>
<td><p>tinyint</p></td>
<td><p><a href="lync-server-2013-medialine-table.md">Lync Server 2013의 Medialine 테이블</a>에서 참조 합니다.</p></td>
</tr>
<tr class="even">
<td><p>CallerIceWarningFlags</p></td>
<td><p>int</p></td>
<td><p>호출자의 bits 플래그에 설명 된 ICE (대화형 연결 설정) 프로세스에 대 한 정보입니다. 자세한 내용은 경험의 품질 모니터링 서버 프로토콜 사양을 참조 하세요.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeIceWarningFlags</p></td>
<td><p>int</p></td>
<td><p>호출 수신자의 bits 플래그에 설명 된 ICE (대화형 연결 설정) 프로세스에 대 한 정보입니다. 자세한 내용은 경험의 품질 모니터링 서버 프로토콜 사양을 참조 하세요.</p></td>
</tr>
<tr class="even">
<td><p>보안</p></td>
<td><p>tinyint</p></td>
<td><p>사용 중인 보안 프로필 0은 없음, 1은 SRTP, 2는 V1입니다.</p></td>
</tr>
<tr class="odd">
<td><p>운송</p></td>
<td><p>tinyint</p></td>
<td><p>전송 종류. 0은 UDP이 고, 1은 TCP입니다.</p></td>
</tr>
<tr class="even">
<td><p>CallerIPAddr</p></td>
<td><p>var (50)</p></td>
<td><p>발신자의 IP 주소입니다. IPv4 또는 IPv6 주소 중 하나가 될 수 있습니다.</p></td>
</tr>
<tr class="odd">
<td><p>CallerPort</p></td>
<td><p>int</p></td>
<td><p>호출자가 사용 하는 포트입니다.</p></td>
</tr>
<tr class="even">
<td><p>CallerInside</p></td>
<td><p>다소</p></td>
<td><p>호출자가 조직 네트워크 내에 있는지 여부를 나타냅니다. 1은 호출자가 엔터프라이즈 네트워크 내에 있음을 의미 합니다. 0은 호출자가 네트워크 외부에 있음을 의미 합니다.</p></td>
</tr>
<tr class="odd">
<td><p>CallerMacAddress</p></td>
<td><p>varchar (256)</p></td>
<td><p>발신자가 사용 하는 네트워크 인터페이스의 MAC 주소입니다.</p></td>
</tr>
<tr class="even">
<td><p>CallerRelayIPAddr</p></td>
<td><p>var (50)</p></td>
<td><p>발신자가 사용 하는 A/V Edge 서비스의 IP 주소입니다. 자세한 내용은 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013의 IPAddress 테이블</a> 을 참조 하세요.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRelayPort</p></td>
<td><p>int</p></td>
<td><p>호출자가 사용 하는 A/V Edge 서비스에 사용 되는 포트입니다.</p></td>
</tr>
<tr class="even">
<td><p>CallerReflexiveIPAddr</p></td>
<td><p>var (50)</p></td>
<td><p>A/V Edge 서비스에서 보고 한 발신자의 IP 주소입니다. 이 주소는 클라이언트가 NAT 뒤에 있는 경우 CallerIPAddr와 같은 경우에 발생할 수 있습니다.</p></td>
</tr>
<tr class="odd">
<td><p>CallerCaptureDev</p></td>
<td><p>varchar (256)</p></td>
<td><p>발신자의 캡처 장치 이름입니다.</p></td>
</tr>
<tr class="even">
<td><p>CallerRenderDev</p></td>
<td><p>varchar (256)</p></td>
<td><p>발신자의 렌더링 장치 이름.</p></td>
</tr>
<tr class="odd">
<td><p>CallerCaptureDevDriver</p></td>
<td><p>varchar (256)</p></td>
<td><p>발신자의 캡처 장치 드라이버 이름.</p></td>
</tr>
<tr class="even">
<td><p>CallerRenderDevDriver</p></td>
<td><p>varchar (256)</p></td>
<td><p>호출자의 렌더링 장치 드라이버 이름입니다.</p></td>
</tr>
<tr class="odd">
<td><p>CallerWifiDriverDeviceDesc</p></td>
<td><p>varchar (256</p></td>
<td><p>발신자의 Wifi 드라이버 설명.</p></td>
</tr>
<tr class="even">
<td><p>CallerWifiDriverVersion</p></td>
<td><p>varchar (256)</p></td>
<td><p>발신자의 Wifi 드라이버 버전.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeNetworkConnectionDetail</p></td>
<td><p>varchar (256)</p></td>
<td><p>호출자의 네트워크 연결에 대 한 세부 정보입니다. 자세한 내용은 <a href="lync-server-2013-networkconnectiondetail-table.md">Lync Server 2013의 Networkconnectiondetail 테이블</a> 을 참조 하세요.</p></td>
</tr>
<tr class="even">
<td><p>CallerBssid</p></td>
<td><p>varchar (256)</p></td>
<td><p>발신자 WiFi 연결에 사용 되는 기본 서비스 설정 식별자입니다.</p></td>
</tr>
<tr class="odd">
<td><p>CallerVPN</p></td>
<td><p>다소</p></td>
<td><p>호출자가 가상 개인 네트워크를 통해 연결 되었는지 여부를 나타냅니다. 1은 VPN (가상 사설망)이 고 0은 VPN이 아닙니다.</p></td>
</tr>
<tr class="even">
<td><p>CalleeIPAddr</p></td>
<td><p>var (50)</p></td>
<td><p>호출 수신자의 IP 주소입니다. IPv4 또는 IPv6 주소 중 하나가 될 수 있습니다.</p></td>
</tr>
<tr class="odd">
<td><p>CalleePort</p></td>
<td><p>int</p></td>
<td><p>호출 수신자가 사용 하는 포트입니다.</p></td>
</tr>
<tr class="even">
<td><p>CalleeInside</p></td>
<td><p>다소</p></td>
<td><p>호출 수신자가 엔터프라이즈 네트워크 내에 있는지 여부를 나타냅니다. 1은 호출 수신자가 엔터프라이즈 네트워크 내에 있음을 의미 하 고 0은 호출 수신자가 네트워크 외부에 있음을 의미 합니다.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeMacAddress</p></td>
<td><p>varchar (256)</p></td>
<td><p>호출 수신자가 사용 하는 네트워크 인터페이스의 MAC 주소입니다.</p></td>
</tr>
<tr class="even">
<td><p>CalleeRelayIPAddr</p></td>
<td><p>var (50)</p></td>
<td><p>호출 수신자가 사용 하는 A/V Edge 서비스의 IP 주소입니다. 자세한 내용은 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013의 IPAddress 테이블</a> 을 참조 하세요.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRelayPort</p></td>
<td><p>int</p></td>
<td><p>호출 수신자가 사용 하는 A/V Edge 서비스에 사용 되는 포트입니다.</p></td>
</tr>
<tr class="even">
<td><p>Callere| Iveipaddr</p></td>
<td><p>var (50)</p></td>
<td><p>A/V Edge 서비스에서 보고 한 호출 수신자의 IP 주소입니다. 이 주소는 클라이언트가 NAT 뒤에 있는 경우 CalleeIPAddr와 같이 다를 수 있습니다.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeCaptureDev</p></td>
<td><p>var (50)</p></td>
<td><p>호출 수신자의 캡처 디바이스 이름입니다.</p></td>
</tr>
<tr class="even">
<td><p>CalleeRenderDev</p></td>
<td><p>varchar (256)</p></td>
<td><p>피호출자의 렌더링 디바이스 이름입니다.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeCaptureDevDriver</p></td>
<td><p>varchar (256)</p></td>
<td><p>피호출자의 캡처 장치 드라이버 이름입니다.</p></td>
</tr>
<tr class="even">
<td><p>CalleeRenderDevDriver</p></td>
<td><p>varchar (256)</p></td>
<td><p>피호출자의 렌더링 장치 드라이버 이름입니다.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeWifiDriverDeviceDesc</p></td>
<td><p>varchar (256)</p></td>
<td><p>호출 수신자의 Wifi 드라이버 설명입니다.</p></td>
</tr>
<tr class="even">
<td><p>CalleeWifiDriverVersion</p></td>
<td><p>varchar (256</p></td>
<td><p>피호출자의 Wifi 드라이버 버전.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeNetworkConnectionDetail</p></td>
<td><p>varchar (256)</p></td>
<td><p>호출 수신자의 네트워크 연결에 대 한 세부 정보입니다. 자세한 내용은 <a href="lync-server-2013-networkconnectiondetail-table.md">Lync Server 2013의 Networkconnectiondetail 테이블</a> 을 참조 하세요.</p></td>
</tr>
<tr class="even">
<td><p>CalleeBssid</p></td>
<td><p>varchar (256)</p></td>
<td><p>피호출자의 WiFi 연결에 사용 되는 기본 서비스 집합 식별자입니다.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeVPN</p></td>
<td><p>다소</p></td>
<td><p>호출 수신자가 가상 개인 네트워크를 통해 연결 되었는지 여부를 나타냅니다. 1은 VPN (가상 사설망)이 고 0은 VPN이 아닙니다.</p></td>
</tr>
<tr class="even">
<td><p>ConversationalMOS</p></td>
<td><p>10 진수 (3, 2)</p></td>
<td><p>오디오 세션의 Narrowband 대화 SPECIALIST (두 오디오 스트림 모두 기준).</p></td>
</tr>
<tr class="odd">
<td><p>AppliedBandwidthLimit</p></td>
<td><p>int</p></td>
<td><p>다양 한 정책 설정 (TURN, API, SDP, 정책 서버 등)을 지정 하 여 지정 된 보내기 쪽 스트림에 실제 대역폭을 적용 한 것입니다. 대역폭 예측을 기준으로 낮은 유효 대역폭을 사용할 수 있기 때문에 효과적인 대역폭과 혼동 해서는 안 됩니다. 이 값이 기본적으로 최대 대역폭입니다. 송신 스트림은 대역폭 추정치에 의해 부과 된 제한을 받을 수 있습니다.</p></td>
</tr>
<tr class="even">
<td><p>AppliedBandwidthSource</p></td>
<td><p>varchar (256)</p></td>
<td><p>적용 되는 대역폭 캡의 원본입니다. 대역폭 한도가 시작 되는 위치를 설명 합니다 (예: "정책 서버", "서버 설정" 또는 "모달").</p></td>
</tr>
<tr class="odd">
<td><p>호출인</p></td>
<td><p>다소</p></td>
<td><p>호출자의 메트릭을 받았는지 여부를 나타냅니다. 1은 예, 0은 no입니다.</p></td>
</tr>
<tr class="even">
<td><p>피호출자</p></td>
<td><p>다소</p></td>
<td><p>통화 수신기의 메트릭을 받았는지 여부를 나타냅니다. 1은 예, 0은 no입니다.</p></td>
</tr>
<tr class="odd">
<td><p>MidCallReport</p></td>
<td><p>다소</p></td>
<td><p>보고서가 통화 일부 인지 또는 전체 통화에 대 한 것인지를 나타냅니다.</p></td>
</tr>
<tr class="even">
<td><p>ClassifiedPoorCall</p></td>
<td><p>다소</p></td>
<td><p>통화가 불량 통화 (1) 또는 좋은 통화 (0)로 분류 되었는지 여부를 나타냅니다.</p></td>
</tr>
<tr class="odd">
<td><p>CallerConnectivityICE</p></td>
<td><p>tinyint</p></td>
<td><p>발신자가 ICE 프로토콜 (인터넷 연결 설정)을 사용 하 여 네트워크에 연결 되었는지 여부를 나타냅니다.</p></td>
</tr>
<tr class="even">
<td><p>CalleeConnectivityICE</p></td>
<td><p>tinyint</p></td>
<td><p>사용자가 ICE 프로토콜 (인터넷 연결 설정)을 사용 하 여 네트워크에 연결 되어 있는지 여부를 나타냅니다.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

