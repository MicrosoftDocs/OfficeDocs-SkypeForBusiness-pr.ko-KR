---
title: 'Lync Server 2013: MediaLine 테이블'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: MediaLine table
ms:assetid: 414b1d63-ae97-4c27-bac0-c9ad0f808ff0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425920(v=OCS.15)
ms:contentKeyID: 48183956
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7488aa258fd30c2f9b519806dc84f9d897a08656
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758756"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="medialine-table-in-lync-server-2013"></a>Lync Server 2013의 MediaLine 테이블

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2014-02-21_

각 레코드는 하나의 미디어 회선을 나타냅니다. (하나의 오디오 세션에는 일반적으로 하나의 오디오 미디어 회선이 있습니다. 회의 장치를 사용 하는 경우 또는 갤러리 보기를 사용 하는 경우 한 오디오 및 비디오 (A/V) 세션에는 일반적으로 하나의 오디오 미디어 회선 및 비디오 미디어 회선이 포함 되지만, 세션에는 두 개의 비디오 미디어 줄이 포함 될 수 있습니다.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>열</strong></th>
<th><strong>데이터 형식</strong></th>
<th><strong>키/인덱스</strong></th>
<th><strong>세부적인</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>ConferenceDateTime</strong></p></td>
<td><p>dmtf</p></td>
<td><p>주요한</p></td>
<td><p><a href="lync-server-2013-session-table.md">Lync Server 2013의 세션 테이블</a>에서 참조 합니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSeq</strong></p></td>
<td><p>int</p></td>
<td><p>주요한</p></td>
<td><p><a href="lync-server-2013-session-table.md">Lync Server 2013의 세션 테이블</a>에서 참조 합니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediaLineLabel</strong></p></td>
<td><p>tinyint</p></td>
<td><p>주요한</p></td>
<td><p>0은 기본 오디오, 1은 기본 비디오, 2는 파노라마 비디오, 3은 응용 프로그램/데스크톱 공유입니다. 이 레이블은 단일 세션 내에서 고유 해야 합니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>ConnectivityIce</strong></p></td>
<td><p>tinyint</p></td>
<td><p> </p></td>
<td><p>이 열은 현재 있지만 Microsoft Lync Server 2013에서 사용 되지 않습니다. 미디어 줄에 사용 되는 연결에 대 한 정보는 CallerConnectivityICE 및 CalleeConnectivityICE 열에 캡처됩니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerIceWarningFlags</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Bits 플래그에 설명 된 ICE (대화형 연결 설정) 프로세스에 대 한 정보입니다. 자세한 내용은 다운로드 가능한 <em>경험 치 모니터링 서버 프로토콜 사양을</em>참조 하세요.</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeIceWarningFlags</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>CallerIceWarningFlags와 동일 하지만 호출 수신자 측에 있습니다. 자세한 내용은 다운로드 가능한 <em>경험 치 모니터링 서버 프로토콜 사양을</em>참조 하세요.</p></td>
</tr>
<tr class="odd">
<td><p><strong>보안</strong></p></td>
<td><p>tinyint</p></td>
<td><p> </p></td>
<td><p>사용 중인 보안 프로필입니다. 0은 없음, 1은 SRTP, 2는 V1입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>운송</strong></p></td>
<td><p>tinyint</p></td>
<td><p> </p></td>
<td><p>0은 UDP이 고, 1은 TCP입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerIPAddr</strong></p></td>
<td><p>int</p></td>
<td><p>외부</p></td>
<td><p>발신자의 IP 주소입니다. 자세한 내용은 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013의 IPAddress 테이블</a> 을 참조 하세요.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerPort</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>호출자가 사용 하는 포트입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerSubnet</strong></p></td>
<td><p>int</p></td>
<td><p> 외부</p></td>
<td><p>호출자의 서브넷입니다. 자세한 내용은 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013의 IPAddress 테이블</a> 을 참조 하세요.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerInside</strong></p></td>
<td><p>다소</p></td>
<td><p> </p></td>
<td><p>1은 발신자가 엔터프라이즈 네트워크 내에 있음을 의미 하 고, 0 이면 발신자가 네트워크 외부에 있음을 의미 합니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerMacAddress</strong></p></td>
<td><p>int</p></td>
<td><p>외부</p></td>
<td><p><a href="lync-server-2013-macaddress-table.md">Lync Server 2013의</a>로이 테이블에서 참조 하는 발신자의 mac 주소입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerRelayIPAddr</strong></p></td>
<td><p>int</p></td>
<td><p>외부</p></td>
<td><p>발신자가 사용 하는 Lync Server A/V Edge 서비스의 IP 주소입니다. 자세한 내용은 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013의 IPAddress 테이블</a> 을 참조 하세요.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerRelayPort</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>발신자에의 한 A/V Edge 서비스에 사용 되는 포트입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerCaptureDev</strong></p></td>
<td><p>int</p></td>
<td><p>외부</p></td>
<td><p>호출자가 사용 하는 캡처 장치입니다. <a href="lync-server-2013-device-table.md">Lync Server 2013의 장치 테이블</a>에서 참조 합니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerRenderDev</strong></p></td>
<td><p>int</p></td>
<td><p>외부</p></td>
<td><p>발신자에 사용 된 장치를 렌더링 합니다. <a href="lync-server-2013-device-table.md">Lync Server 2013의 장치 테이블</a>에서 참조 합니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerCaptureDevDriver</strong></p></td>
<td><p>int</p></td>
<td><p>외부</p></td>
<td><p><a href="lync-server-2013-devicedriver-table.md">Lync Server 2013의 Devicedriver 테이블</a>에서 참조 되는 호출자 캡처 디바이스의 드라이버입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerRenderDevDriver</strong></p></td>
<td><p>int</p></td>
<td><p>외부</p></td>
<td><p><a href="lync-server-2013-devicedriver-table.md">Lync Server 2013의 Devicedriver 테이블</a>에서 참조 하는 호출자의 렌더 디바이스 드라이버입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerNetworkConnectionType</strong></p></td>
<td><p>tinyint</p></td>
<td><p>외부</p></td>
<td><p>발신자가 네트워크에 연결 되는 방법을 나타냅니다. 값은 <a href="lync-server-2013-networkconnectiondetail-table.md">Lync Server 2013의 Networkconnectiondetail 테이블</a>에서 가져옵니다. WiFi 연결에 대 한 유선 연결의 경우 일반적으로 값은 0이 고, 그렇지 않으면-1입니다. 이더넷 연결의 경우 3.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerBssid</strong></p></td>
<td><p>int</p></td>
<td><p>외부</p></td>
<td><p>무선이 사용 되는 경우 발신자의 BSSID입니다. <a href="lync-server-2013-macaddress-table.md">Lync Server 2013의</a>로이 테이블에서 참조 합니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerVPN</strong></p></td>
<td><p>다소</p></td>
<td></td>
<td><p>호출자의 링크입니다. 1은 VPN (가상 사설망)이 고 0은 VPN이 아닙니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerLinkSpeed</strong></p></td>
<td><p>10 진수 (18, 0)</p></td>
<td></td>
<td><p>호출자 끝점에 대 한 bps의 네트워크 링크 속도입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeIPAddr</strong></p></td>
<td><p>int</p></td>
<td><p>외부</p></td>
<td><p>통화 수신기의 IP 주소입니다. 자세한 내용은 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013의 IPAddress 테이블</a> 을 참조 하세요.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleePort</strong></p></td>
<td><p>다소</p></td>
<td></td>
<td><p>전화 수신기에서 사용 하는 포트입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>Calleesnet</strong></p></td>
<td><p>int</p></td>
<td><p>외부</p></td>
<td><p>호출 수신자의 서브넷입니다. 자세한 내용은 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013의 IPAddress 테이블</a> 을 참조 하세요.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeInside</strong></p></td>
<td><p>다소</p></td>
<td><p> </p></td>
<td><p>1은 통화 수신기가 엔터프라이즈 네트워크 내에 있음을 의미 하 고, 0 이면 전화 수신기가 네트워크 외부에 있음을 의미 합니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeMacAddress</strong></p></td>
<td><p>int</p></td>
<td><p>외부</p></td>
<td><p>호출 수신자 Mac 주소입니다. <a href="lync-server-2013-macaddress-table.md">Lync Server 2013의로이 테이블</a>에서 참조 합니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeRelayIPAddr</strong></p></td>
<td><p>int</p></td>
<td><p>외부</p></td>
<td><p>통화 수신기에서 사용 하는 A/V Edge 서비스의 IP 주소입니다. 자세한 내용은 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013의 IPAddress 테이블</a> 을 참조 하세요.</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeRelayPort</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>전화 수신기에 의해 A/V에 지 서비스에 사용 되는 포트입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeCaptureDev</strong></p></td>
<td><p>int</p></td>
<td><p>외부</p></td>
<td><p>호출 수신자가 사용 하는 캡처 장치입니다. <a href="lync-server-2013-device-table.md">Lync Server 2013의 장치 테이블</a>에서 참조 합니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeRenderDev</strong></p></td>
<td><p>int</p></td>
<td><p>외부</p></td>
<td><p>통화 수신기에 사용 되는 장치를 렌더링 합니다. <a href="lync-server-2013-device-table.md">Lync Server 2013의 장치 테이블</a>에서 참조 합니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeCaptureDevDriver</strong></p></td>
<td><p>int</p></td>
<td><p>외부</p></td>
<td><p>전화 수화기 캡처 장치용 드라이버입니다. <a href="lync-server-2013-devicedriver-table.md">Lync Server 2013에서 Devicedriver 테이블</a>에서 참조 했습니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeRenderDevDriver</strong></p></td>
<td><p>varchar (256)</p></td>
<td><p>외부</p></td>
<td><p>통화 수신기의 렌더링 장치 드라이버입니다. <a href="lync-server-2013-devicedriver-table.md">Lync Server 2013에서 Devicedriver 테이블</a>에서 참조 했습니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeNetworkConnectionType</strong></p></td>
<td><p>tinyint</p></td>
<td><p>외부</p></td>
<td><p>호출 수신자가 네트워크에 연결 되는 방법을 나타냅니다. 값은 <a href="lync-server-2013-networkconnectiondetail-table.md">Lync Server 2013의 Networkconnectiondetail 테이블</a>에서 가져옵니다. WiFi 연결에 대 한 유선 연결의 경우 일반적으로 값은 0이 고, 그렇지 않으면-1입니다. 이더넷 연결의 경우 3.</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeBssid</strong></p></td>
<td><p>int</p></td>
<td><p>외부</p></td>
<td><p>무선이 사용 되는 경우 피호출자의 BSSID입니다. <a href="lync-server-2013-macaddress-table.md">Lync Server 2013의</a>로이 테이블에서 참조 합니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeVPN</strong></p></td>
<td><p>다소</p></td>
<td><p> </p></td>
<td><p>전화 수화기의 링크입니다. 1은 VPN (가상 사설망)이 고 0은 VPN이 아닙니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeLinkSpeed</strong></p></td>
<td><p>10 진수 (18, 0)</p></td>
<td><p> </p></td>
<td><p>통화 수신기의 끝점에 대 한 bps의 네트워크 링크 속도입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConversationalMOS</strong></p></td>
<td><p>10 진수 (3, 2)</p></td>
<td><p> </p></td>
<td><p>오디오 세션의 Narrowband 대화 SPECIALIST (두 오디오 스트림 모두 기준).</p></td>
</tr>
<tr class="even">
<td><p><strong>AppliedBandwidthLimit</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>다양 한 정책 설정 (TURN, API, SDP, 정책 서버 등)이 지정 된 지정 된 보내기 쪽 스트림에 적용 되는 실제 대역폭입니다. 대역폭 예측을 기준으로 낮은 유효 대역폭을 사용할 수 있기 때문에 효과적인 대역폭과 혼동 하지 않는 것이 좋습니다. 이 값이 기본적으로 최대 대역폭입니다. 송신 스트림은 대역폭 추정치에 의해 부과 된 제한을 받을 수 있습니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>AppliedBandwidthSourceKey</strong></p></td>
<td><p>smallint</p></td>
<td></td>
<td><p>적용 되는 대역폭 cap의 원본입니다. 이는 대역폭 한도가 어디에서 오는지 ("정책 서버", "서버 켜기", "모달" 등)를 설명 합니다. <a href="lync-server-2013-appliedbandwidthsource-table.md">Lync Server 2013의 AppliedBandwidthSource 테이블</a>에서 참조 합니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>호출인</strong></p></td>
<td><p>다소</p></td>
<td><p> </p></td>
<td><p>호출자의 메트릭을 받았는지 여부를 나타냅니다. 1은 예, null 값은 no입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>피호출자</strong></p></td>
<td><p>다소</p></td>
<td><p> </p></td>
<td><p>통화 수신기의 메트릭을 받았는지 여부를 나타냅니다. 1은 예, null 값은 no입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>MidCallReport</strong></p></td>
<td><p>다소</p></td>
<td></td>
<td><p>보고서가 세션의 일부 인지 또는 전체 세션에 대 한 것인지를 나타냅니다.</p>
<p>이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ClassifiedPoorCall</strong></p></td>
<td><p>다소</p></td>
<td></td>
<td><p>통화가 불량 통화 (값 1) 또는 좋은 통화 (0)로 분류 되었는지 여부를 나타냅니다.</p>
<p>이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerConnectivityICE</strong></p></td>
<td><p>tinyInt</p></td>
<td></td>
<td><p>발신자가 ICE 프로토콜 (인터넷 연결 설정)을 사용 하 여 네트워크에 연결 되었는지 여부를 나타냅니다.</p>
<p>이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeConnectivityICE</strong></p></td>
<td><p>tinyint</p></td>
<td></td>
<td><p>발신자가 ICE 프로토콜 (인터넷 연결 설정)을 사용 하 여 네트워크에 연결 되었는지 여부를 나타냅니다.</p>
<p>이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerReflexiveLocalIPAddr</strong></p></td>
<td><p>int</p></td>
<td><p>외부</p></td>
<td><p>통화를 설정한 사용자의 재귀 IP 주소입니다. NAT (네트워크 주소 변환)를 사용 하는 조직에서 재귀 IP 주소는 프록시 서버의 IP 주소입니다.</p>
<p>이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerWiFiDriverDevicesDesc</strong></p></td>
<td><p>int</p></td>
<td><p>외부</p></td>
<td><p>통화를 설정한 사용자가 사용 하는 WiFi 드라이버에 대 한 디바이스 설명입니다.</p>
<p>이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerWiFiDriverVersion</strong></p></td>
<td><p>int</p></td>
<td><p>외부</p></td>
<td><p>통화를 설정한 사용자가 사용 하는 WiFi 드라이버의 버전 번호입니다.</p>
<p>이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleReflexiveLocalIPAddr</strong></p></td>
<td><p>int</p></td>
<td><p>외부</p></td>
<td><p>통화를 받은 사용자의 재귀 IP 주소입니다. NAT (네트워크 주소 변환)를 사용 하는 조직에서 재귀 IP 주소는 프록시 서버의 IP 주소입니다.</p>
<p>이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeWiFiDriverDevicesDesc</strong></p></td>
<td><p>int</p></td>
<td><p>외부</p></td>
<td><p>통화를 받은 사용자가 사용 하는 WiFi 드라이버에 대 한 디바이스 설명입니다.</p>
<p>이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeWiFiDriverVersion</strong></p></td>
<td><p>int</p></td>
<td><p>외부</p></td>
<td><p>통화를 받은 사용자가 사용 하는 WiFi 드라이버의 버전 번호입니다.</p>
<p>이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

