---
title: 'Lync Server 2013: Medialofftable'
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
ms.openlocfilehash: 03f967b50c2fa9eae4f2599ce96dc9c592a57006
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48516145"
---
# <a name="medialine-table-in-lync-server-2013"></a>Lync Server 2013의 Medialofftable

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2014-02-21_

각 레코드는 하나의 미디어 회선을 나타냅니다. 일반적으로 오디오 세션에는 하나의 오디오 미디어 회선이 있습니다. 회의 장치를 사용 하거나 갤러리 보기를 사용 하는 경우, A/V (오디오 및 비디오) 세션에는 대개 하나의 오디오 미디어 회선과 하나의 비디오 미디어 회선이 포함 되지만, 세션에는 두 개의 비디오 미디어 회선이 포함 될 수 있습니다.


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
<th><strong>세부 정보</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Conferencedatetime이 동일할</strong></p></td>
<td><p>datetime</p></td>
<td><p>Primary</p></td>
<td><p><a href="lync-server-2013-session-table.md">Lync Server 2013의 Session 테이블</a>에서 참조 됩니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p><a href="lync-server-2013-session-table.md">Lync Server 2013의 Session 테이블</a>에서 참조 됩니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediaLineLabel</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Primary</p></td>
<td><p>0은 기본 오디오이 고 1은 기본 비디오이 고 2는 파노라마 동영상, 3은 응용 프로그램/데스크톱 공유입니다. 이 레이블은 단일 세션 내에서 고유 해야 합니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>ConnectivityIce</strong></p></td>
<td><p>tinyint</p></td>
<td><p> </p></td>
<td><p>이 열은 제공 되지만 Microsoft Lync Server 2013에서는 사용 되지 않습니다. 미디어 회선에 사용 되는 연결에 대 한 정보는 CallerConnectivityICE 및 CalleeConnectivityICE 열에서 캡처됩니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerIceWarningFlags</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Bits 플래그에 설명 된 ICE (대화형 연결 설정) 프로세스에 대 한 정보입니다. 자세한 내용은 다운로드 가능한 <em>Experience Quality Monitoring Server 프로토콜 사양을</em>참조 하십시오.</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeIceWarningFlags</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>CallerIceWarningFlags와 같으며 수신자 쪽에 있습니다. 자세한 내용은 다운로드 가능한 <em>Experience Quality Monitoring Server 프로토콜 사양을</em>참조 하십시오.</p></td>
</tr>
<tr class="odd">
<td><p><strong>보안</strong></p></td>
<td><p>tinyint</p></td>
<td><p> </p></td>
<td><p>사용 중인 보안 프로필입니다. 0은 NONE, 1은 SRTP, 2는 V1입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>전송</strong></p></td>
<td><p>tinyint</p></td>
<td><p> </p></td>
<td><p>0은 UDP, 1은 TCP입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerIPAddr</strong></p></td>
<td><p>int</p></td>
<td><p>외부</p></td>
<td><p>발신자의 IP 주소입니다. 자세한 내용은 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013의 IPAddress 표</a> 를 참조 하세요.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerPort</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>발신자가 사용하는 포트입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerSubnet</strong></p></td>
<td><p>int</p></td>
<td><p> 외부</p></td>
<td><p>발신자의 서브넷입니다. 자세한 내용은 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013의 IPAddress 표</a> 를 참조 하세요.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerInside</strong></p></td>
<td><p>비트만</p></td>
<td><p> </p></td>
<td><p>1은 발신자가 회사 네트워크 내에 있음을 의미하고 0은 발신자가 네트워크 외부에 있음을 의미합니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerMacAddress가)</strong></p></td>
<td><p>int</p></td>
<td><p>외부</p></td>
<td><p><a href="lync-server-2013-macaddress-table.md">Lync Server 2013의 (</a>~) 테이블에서 참조 하는 발신자의 mac 주소입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerRelayIPAddr</strong></p></td>
<td><p>int</p></td>
<td><p>외부</p></td>
<td><p>발신자가 사용 하는 Lync Server A/V에 지 서비스의 IP 주소입니다. 자세한 내용은 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013의 IPAddress 표</a> 를 참조 하세요.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerRelayPort</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>A/V에 지 서비스에서 발신자가 사용 하는 포트입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerCaptureDev</strong></p></td>
<td><p>int</p></td>
<td><p>외부</p></td>
<td><p>발신자가 사용 하는 캡처 장치입니다. <a href="lync-server-2013-device-table.md">Lync Server 2013의 장치 테이블</a>에서 참조 됩니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerRenderDev</strong></p></td>
<td><p>int</p></td>
<td><p>외부</p></td>
<td><p>발신자가 사용 하는 장치를 렌더링 합니다. <a href="lync-server-2013-device-table.md">Lync Server 2013의 장치 테이블</a>에서 참조 됩니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerCaptureDevDriver</strong></p></td>
<td><p>int</p></td>
<td><p>외부</p></td>
<td><p><a href="lync-server-2013-devicedriver-table.md">Lync Server 2013의 Devicedriver 테이블</a>에서 참조 되는 발신자의 캡처 장치용 드라이버입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerRenderDevDriver</strong></p></td>
<td><p>int</p></td>
<td><p>외부</p></td>
<td><p><a href="lync-server-2013-devicedriver-table.md">Lync Server 2013의 Devicedriver 테이블</a>에서 참조 되는 발신자의 렌더 장치에 대 한 드라이버입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerNetworkConnectionType</strong></p></td>
<td><p>tinyint</p></td>
<td><p>외부</p></td>
<td><p>발신자가 네트워크에 연결 되는 방식을 나타냅니다. 값은 <a href="lync-server-2013-networkconnectiondetail-table.md">Lync Server 2013의 Networkconnectiondetail 테이블</a>에서 가져옵니다. WiFi 연결의 경우 유선 연결의 1에 대 한 일반적인 값은 0입니다. 및 3은 이더넷 연결용입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerBssid</strong></p></td>
<td><p>int</p></td>
<td><p>외부</p></td>
<td><p>무선이 사용 되는 경우 발신자의 BSSID입니다. <a href="lync-server-2013-macaddress-table.md">Lync Server 2013의 (</a>~) 테이블에서 참조 됩니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerVPN</strong></p></td>
<td><p>비트만</p></td>
<td></td>
<td><p>발신자의 링크입니다. 1은 VPN(가상 사설망), 0은 비VPN입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerLinkSpeed</strong></p></td>
<td><p>10 진수 (18, 0)</p></td>
<td></td>
<td><p>발신자의 끝점에 대 한 네트워크 연결 속도 (bps)입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeIPAddr</strong></p></td>
<td><p>int</p></td>
<td><p>외부</p></td>
<td><p>통화 수신기의 IP 주소입니다. 자세한 내용은 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013의 IPAddress 표</a> 를 참조 하세요.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleePort</strong></p></td>
<td><p>비트만</p></td>
<td></td>
<td><p>통화 수신기에서 사용 하는 포트입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeSubnet</strong></p></td>
<td><p>int</p></td>
<td><p>외부</p></td>
<td><p>수신자의 서브넷입니다. 자세한 내용은 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013의 IPAddress 표</a> 를 참조 하세요.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeInside</strong></p></td>
<td><p>비트만</p></td>
<td><p> </p></td>
<td><p>1은 통화 수신자가 회사 네트워크 내에 있음을 의미 하 고 0은 통화 수신자가 네트워크 외부에 있음을 의미 합니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeMacAddress</strong></p></td>
<td><p>int</p></td>
<td><p>외부</p></td>
<td><p>수신자 Mac 주소입니다. <a href="lync-server-2013-macaddress-table.md">Lync Server 2013의 (</a>~) 테이블에서 참조 됩니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeRelayIPAddr</strong></p></td>
<td><p>int</p></td>
<td><p>외부</p></td>
<td><p>통화 수신기에서 사용 하는 A/V에 지 서비스의 IP 주소입니다. 자세한 내용은 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013의 IPAddress 표</a> 를 참조 하세요.</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeRelayPort</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>A/V에 지 서비스에서 통화 수신기에 사용 하는 포트입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeCaptureDev</strong></p></td>
<td><p>int</p></td>
<td><p>외부</p></td>
<td><p>통화 수신기에서 사용 되는 캡처 장치입니다. <a href="lync-server-2013-device-table.md">Lync Server 2013의 장치 테이블</a>에서 참조 됩니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeRenderDev</strong></p></td>
<td><p>int</p></td>
<td><p>외부</p></td>
<td><p>통화 수신기에서 사용 하는 장치를 렌더링 합니다. <a href="lync-server-2013-device-table.md">Lync Server 2013의 장치 테이블</a>에서 참조 됩니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeCaptureDevDriver</strong></p></td>
<td><p>int</p></td>
<td><p>외부</p></td>
<td><p>통화 수신기의 캡처 장치에 대 한 드라이버입니다. <a href="lync-server-2013-devicedriver-table.md">Lync Server 2013의 Devicedriver 테이블</a>에서 참조 됩니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeRenderDevDriver</strong></p></td>
<td><p>varchar (256)</p></td>
<td><p>외부</p></td>
<td><p>통화 수신기의 렌더 장치에 대 한 드라이버입니다. <a href="lync-server-2013-devicedriver-table.md">Lync Server 2013의 Devicedriver 테이블</a>에서 참조 됩니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeNetworkConnectionType</strong></p></td>
<td><p>tinyint</p></td>
<td><p>외부</p></td>
<td><p>수신자가 네트워크에 연결 된 방법을 나타냅니다. 값은 <a href="lync-server-2013-networkconnectiondetail-table.md">Lync Server 2013의 Networkconnectiondetail 테이블</a>에서 가져옵니다. WiFi 연결의 경우 유선 연결의 1에 대 한 일반적인 값은 0입니다. 및 3은 이더넷 연결용입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeBssid</strong></p></td>
<td><p>int</p></td>
<td><p>외부</p></td>
<td><p>무선이 사용 되는 경우 수신자의 BSSID입니다. <a href="lync-server-2013-macaddress-table.md">Lync Server 2013의 (</a>~) 테이블에서 참조 됩니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeVPN</strong></p></td>
<td><p>비트만</p></td>
<td><p> </p></td>
<td><p>통화 수신기의 링크입니다. 1은 VPN (가상 사설망), 0은 VPN 외입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeLinkSpeed</strong></p></td>
<td><p>10 진수 (18, 0)</p></td>
<td><p> </p></td>
<td><p>통화 수신기의 끝점에 대 한 네트워크 연결 속도 (bps)입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConversationalMOS</strong></p></td>
<td><p>10 진수 (3, 2)</p></td>
<td><p> </p></td>
<td><p>오디오 세션의 협대역 대화 MOS입니다(두 오디오 스트림을 모두 기반으로 함).</p></td>
</tr>
<tr class="even">
<td><p><strong>AppliedBandwidthLimit</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>다양 한 정책 설정 (TURN, API, SDP, 정책 서버 등)에 따라 지정 된 보내기 쪽 스트림에 실제 대역폭이 적용 됩니다. 이 대역폭은 대역폭 예상에 따라 유효 대역폭이 더 낮을 수 있으므로 유효 대역폭과 혼동해서는 안됩니다. 이 대역폭은 기본적으로 대역폭 예상치로 지정된 한도를 제외하고 송신 스트림이 사용할 수 있는 최대 대역폭입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>AppliedBandwidthSourceKey</strong></p></td>
<td><p>smallint</p></td>
<td></td>
<td><p>적용 되는 대역폭 캡의 출처입니다. 또한 대역폭 제한이 전송 되는 위치 ("정책 서버", "서버 설정", "모달" 등)를 설명 합니다. <a href="lync-server-2013-appliedbandwidthsource-table.md">Lync Server 2013의 AppliedBandwidthSource 테이블</a>에서 참조 됩니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>최초</strong></p></td>
<td><p>비트만</p></td>
<td><p> </p></td>
<td><p>발신자의 메트릭이 수신 되었는지 여부를 나타냅니다. 1이 예 이면 null 값은 no입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>피호출자</strong></p></td>
<td><p>비트만</p></td>
<td><p> </p></td>
<td><p>통화 수신기에서 메트릭을 받았는지 여부를 나타냅니다. 1이 예 이면 null 값은 no입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>MidCallReport</strong></p></td>
<td><p>비트만</p></td>
<td></td>
<td><p>보고서가 세션의 일부 또는 전체 세션에 대 한 것인지를 나타냅니다.</p>
<p>이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ClassifiedPoorCall</strong></p></td>
<td><p>비트만</p></td>
<td></td>
<td><p>통화가 불량 통화 (값 1) 또는 정상 통화 (0)로 분류 되었는지 여부를 나타냅니다.</p>
<p>이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerConnectivityICE</strong></p></td>
<td><p>tinyInt</p></td>
<td></td>
<td><p>발신자가 ICE(Internet Connectivity Establishment) 프로토콜을 사용하여 네트워크에 연결했는지 여부를 나타냅니다.</p>
<p>이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeConnectivityICE</strong></p></td>
<td><p>tinyint</p></td>
<td></td>
<td><p>발신자가 ICE(Internet Connectivity Establishment) 프로토콜을 사용하여 네트워크에 연결했는지 여부를 나타냅니다.</p>
<p>이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerReflexiveLocalIPAddr</strong></p></td>
<td><p>int</p></td>
<td><p>외부</p></td>
<td><p>통화를 시작한 사용자의 재귀 IP 주소입니다. NAT (네트워크 주소 변환)를 사용 하는 조직에서는 재귀 IP 주소가 프록시 서버의 IP 주소입니다.</p>
<p>이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerWiFiDriverDevicesDesc</strong></p></td>
<td><p>int</p></td>
<td><p>외부</p></td>
<td><p>통화를 시작한 사용자가 사용한 WiFi 드라이버에 대 한 장치 설명입니다.</p>
<p>이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerWiFiDriverVersion</strong></p></td>
<td><p>int</p></td>
<td><p>외부</p></td>
<td><p>통화를 시작한 사용자가 사용한 WiFi 드라이버의 버전 번호입니다.</p>
<p>이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleReflexiveLocalIPAddr</strong></p></td>
<td><p>int</p></td>
<td><p>외부</p></td>
<td><p>통화를 받은 사용자의 재귀 IP 주소입니다. NAT (네트워크 주소 변환)를 사용 하는 조직에서는 재귀 IP 주소가 프록시 서버의 IP 주소입니다.</p>
<p>이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeWiFiDriverDevicesDesc</strong></p></td>
<td><p>int</p></td>
<td><p>외부</p></td>
<td><p>통화를 받은 사용자가 사용한 WiFi 드라이버에 대 한 장치 설명입니다.</p>
<p>이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeWiFiDriverVersion</strong></p></td>
<td><p>int</p></td>
<td><p>외부</p></td>
<td><p>통화를 받은 사용자가 사용한 WiFi 드라이버의 버전 번호입니다.</p>
<p>이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

