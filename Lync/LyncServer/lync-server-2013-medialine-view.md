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
ms.openlocfilehash: 5c6e5fd3c1afe27bc1baa8790527ee239bdba990
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42039708"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="medialine-view-in-lync-server-2013"></a>Lync Server 2013의 MediaLine

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-03_

미디어 회선 보기에는 데이터베이스의 각 미디어 회선에 대한 정보가 저장됩니다. 하나의 오디오 세션은 일반적으로 오디오 미디어 회선 하나를 포함합니다. 하나의 A/V(오디오 및 비디오) 세션은 보통 오디오 미디어 회선과 비디오 미디어 회선을 하나씩 포함하지만, 회의 장치나 갤러리 보기를 사용하는 경우에는 세션이 비디오 미디어 회선 두 개를 포함할 수 있습니다. 이 보기는 Microsoft Lync Server 2013에 도입 되었습니다.


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
<th>세부 정보</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Conferencedatetime이 동일할</p></td>
<td><p>datetime</p></td>
<td><p><a href="lync-server-2013-medialine-table.md">Lync Server 2013의 Medialofftable</a>에서 참조 됩니다.</p></td>
</tr>
<tr class="even">
<td><p>SessionSeq</p></td>
<td><p>int</p></td>
<td><p><a href="lync-server-2013-medialine-table.md">Lync Server 2013의 Medialofftable</a>에서 참조 됩니다.</p></td>
</tr>
<tr class="odd">
<td><p>MediaLineLabel</p></td>
<td><p>tinyint</p></td>
<td><p><a href="lync-server-2013-medialine-table.md">Lync Server 2013의 Medialofftable</a>에서 참조 됩니다.</p></td>
</tr>
<tr class="even">
<td><p>CallerIceWarningFlags</p></td>
<td><p>int</p></td>
<td><p>비트 플래그로 설명된 발신자 측 ICE(Interactive Connectivity Establishment) 프로세스에 대한 정보입니다. 자세한 내용은 체감 품질 모니터링 서버 프로토콜 사양을 참조하십시오.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeIceWarningFlags</p></td>
<td><p>int</p></td>
<td><p>수신자에 대해 비트 플래그로 설명되는 ICE(Interactive Connectivity Establishment) 프로세스에 대한 정보입니다. 자세한 내용은 체감 품질 모니터링 서버 프로토콜 사양을 참조하십시오.</p></td>
</tr>
<tr class="even">
<td><p>보안</p></td>
<td><p>tinyint</p></td>
<td><p>사용 중인 보안 프로필입니다. 0은 NONE, 1은 SRTP, 2는 V1입니다.</p></td>
</tr>
<tr class="odd">
<td><p>전송</p></td>
<td><p>tinyint</p></td>
<td><p>전송 유형입니다. 0은 UDP, 1은 TCP입니다.</p></td>
</tr>
<tr class="even">
<td><p>CallerIPAddr</p></td>
<td><p>var (50)</p></td>
<td><p>발신자의 IP 주소입니다. IPv4 또는 IPv6 주소일 수 있습니다.</p></td>
</tr>
<tr class="odd">
<td><p>CallerPort</p></td>
<td><p>int</p></td>
<td><p>발신자가 사용하는 포트입니다.</p></td>
</tr>
<tr class="even">
<td><p>CallerInside</p></td>
<td><p>비트만</p></td>
<td><p>발신자가 조직 네트워크 내부에 있는지 여부를 나타냅니다. 값이 1이면 발신자가 엔터프라이즈 네트워크 내부에 있는 것입니다. 값이 0이면 발신자가 네트워크 외부에 있는 것입니다.</p></td>
</tr>
<tr class="odd">
<td><p>CallerMacAddress가)</p></td>
<td><p>varchar (256)</p></td>
<td><p>발신자가 사용하는 네트워크 인터페이스의 MAC 주소입니다.</p></td>
</tr>
<tr class="even">
<td><p>CallerRelayIPAddr</p></td>
<td><p>var (50)</p></td>
<td><p>A/V 에지 서비스에서 발신자가 사용하는 IP 주소입니다. 자세한 내용은 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013의 IPAddress 표</a> 를 참조 하세요.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRelayPort</p></td>
<td><p>int</p></td>
<td><p>A/V 에지 서비스에서 발신자가 사용하는 포트입니다.</p></td>
</tr>
<tr class="even">
<td><p>CallerReflexiveIPAddr</p></td>
<td><p>var (50)</p></td>
<td><p>A/V 에지 서비스에서 보고한 발신자의 IP 주소입니다. 클라이언트에 NAT가 적용되는 등의 경우 이 주소는 CallerIPAddr과 다를 수 있습니다.</p></td>
</tr>
<tr class="odd">
<td><p>CallerCaptureDev</p></td>
<td><p>varchar (256)</p></td>
<td><p>발신자의 캡처 장치 이름입니다.</p></td>
</tr>
<tr class="even">
<td><p>CallerRenderDev</p></td>
<td><p>varchar (256)</p></td>
<td><p>발신자의 렌더링 장치 이름입니다.</p></td>
</tr>
<tr class="odd">
<td><p>CallerCaptureDevDriver</p></td>
<td><p>varchar (256)</p></td>
<td><p>발신자의 캡처 장치 드라이버 이름입니다.</p></td>
</tr>
<tr class="even">
<td><p>CallerRenderDevDriver</p></td>
<td><p>varchar (256)</p></td>
<td><p>발신자의 렌더링 장치 드라이버 이름입니다.</p></td>
</tr>
<tr class="odd">
<td><p>CallerWifiDriverDeviceDesc</p></td>
<td><p>varchar (256</p></td>
<td><p>발신자의 Wi-Fi 드라이버 설명입니다.</p></td>
</tr>
<tr class="even">
<td><p>CallerWifiDriverVersion</p></td>
<td><p>varchar (256)</p></td>
<td><p>발신자의 Wi-Fi 드라이버 버전입니다.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeNetworkConnectionDetail</p></td>
<td><p>varchar (256)</p></td>
<td><p>발신자의 네트워크 연결 세부 정보입니다. 자세한 내용은 <a href="lync-server-2013-networkconnectiondetail-table.md">Lync Server 2013에서 Networkconnectiondetail 테이블</a> 을 참조 하십시오.</p></td>
</tr>
<tr class="even">
<td><p>CallerBssid</p></td>
<td><p>varchar (256)</p></td>
<td><p>발신자 Wi-Fi 연결에 사용되는 기본 서비스 집합 식별자입니다.</p></td>
</tr>
<tr class="odd">
<td><p>CallerVPN</p></td>
<td><p>비트만</p></td>
<td><p>발신자가 가상 사설망을 통해 연결했는지 여부를 나타냅니다. 1은 VPN(가상 사설망), 0은 비 VPN입니다.</p></td>
</tr>
<tr class="even">
<td><p>CalleeIPAddr</p></td>
<td><p>var (50)</p></td>
<td><p>수신자의 IP 주소입니다. IPv4 또는 IPv6 주소일 수 있습니다.</p></td>
</tr>
<tr class="odd">
<td><p>CalleePort</p></td>
<td><p>int</p></td>
<td><p>수신자가 사용하는 포트입니다.</p></td>
</tr>
<tr class="even">
<td><p>CalleeInside</p></td>
<td><p>비트만</p></td>
<td><p>수신자가 엔터프라이즈 네트워크 내부에 있는지 여부를 나타냅니다. 값이 1이면 수신자가 엔터프라이즈 네트워크 내부에 있는 것입니다. 값이 0이면 수신자가 네트워크 외부에 있는 것입니다.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeMacAddress</p></td>
<td><p>varchar (256)</p></td>
<td><p>수신자가 사용하는 네트워크 인터페이스의 MAC 주소입니다.</p></td>
</tr>
<tr class="even">
<td><p>CalleeRelayIPAddr</p></td>
<td><p>var (50)</p></td>
<td><p>수신자가 사용하는 A/V 에지 서비스의 IP 주소입니다. 자세한 내용은 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013의 IPAddress 표</a> 를 참조 하세요.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRelayPort</p></td>
<td><p>int</p></td>
<td><p>A/V 에지 서비스에서 수신자가 사용하는 포트입니다.</p></td>
</tr>
<tr class="even">
<td><p>Callere과, Iveipaddr</p></td>
<td><p>var (50)</p></td>
<td><p>A/V 에지 서비스에서 보고한 수신자의 IP 주소입니다. 클라이언트에 NAT가 적용되는 등의 경우 이 주소는 CalleeIPAddr과 다를 수 있습니다.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeCaptureDev</p></td>
<td><p>var (50)</p></td>
<td><p>수신자의 캡처 장치 이름입니다.</p></td>
</tr>
<tr class="even">
<td><p>CalleeRenderDev</p></td>
<td><p>varchar (256)</p></td>
<td><p>수신자의 렌더링 장치 이름입니다.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeCaptureDevDriver</p></td>
<td><p>varchar (256)</p></td>
<td><p>수신자의 캡처 장치 드라이버 이름입니다.</p></td>
</tr>
<tr class="even">
<td><p>CalleeRenderDevDriver</p></td>
<td><p>varchar (256)</p></td>
<td><p>수신자의 렌더링 장치 드라이버 이름입니다.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeWifiDriverDeviceDesc</p></td>
<td><p>varchar (256)</p></td>
<td><p>수신자의 Wi-Fi 드라이버 설명입니다.</p></td>
</tr>
<tr class="even">
<td><p>CalleeWifiDriverVersion</p></td>
<td><p>varchar (256</p></td>
<td><p>수신자의 Wi-Fi 드라이버 버전입니다.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeNetworkConnectionDetail</p></td>
<td><p>varchar (256)</p></td>
<td><p>수신자의 네트워크 연결 세부 정보입니다. 자세한 내용은 <a href="lync-server-2013-networkconnectiondetail-table.md">Lync Server 2013에서 Networkconnectiondetail 테이블</a> 을 참조 하십시오.</p></td>
</tr>
<tr class="even">
<td><p>CalleeBssid</p></td>
<td><p>varchar (256)</p></td>
<td><p>수신자 Wi-Fi 연결에 사용되는 기본 서비스 집합 식별자입니다.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeVPN</p></td>
<td><p>비트만</p></td>
<td><p>수신자가 가상 사설망을 통해 연결했는지 여부를 나타냅니다. 1은 VPN(가상 사설망), 0은 비 VPN입니다.</p></td>
</tr>
<tr class="even">
<td><p>ConversationalMOS</p></td>
<td><p>10 진수 (3, 2)</p></td>
<td><p>오디오 세션의 협대역 대화 MOS입니다(두 오디오 스트림을 모두 기반으로 함).</p></td>
</tr>
<tr class="odd">
<td><p>AppliedBandwidthLimit</p></td>
<td><p>int</p></td>
<td><p>다양한 정책 설정(TURN, API, SDP, 정책 서버 등)이 제공된 지정된 송신 쪽 스트림에 적용되는 실제 대역폭입니다. 대역폭 예상치에 따라 유효 대역폭은 더 낮을 수 있으므로 이 대역폭을 유효 대역폭과 혼동해서는 안 됩니다. 이 대역폭은 기본적으로 대역폭 예상치로 지정된 한도를 제외하고 송신 스트림이 사용할 수 있는 최대 대역폭입니다.</p></td>
</tr>
<tr class="even">
<td><p>AppliedBandwidthSource</p></td>
<td><p>varchar (256)</p></td>
<td><p>적용 중인 대역폭의 원본입니다. 이 원본은 대역폭 제한이 시작되는 위치(예: "정책 서버", "TURN 서버" 또는 "형식")를 설명합니다.</p></td>
</tr>
<tr class="odd">
<td><p>최초</p></td>
<td><p>비트만</p></td>
<td><p>발신자의 메트릭이 수신되었는지 여부를 나타냅니다. 1은 예, 0은 아니요입니다.</p></td>
</tr>
<tr class="even">
<td><p>피호출자</p></td>
<td><p>비트만</p></td>
<td><p>통화 수신자의 메트릭이 수신되었는지 여부를 나타냅니다. 1은 예, 0은 아니요입니다.</p></td>
</tr>
<tr class="odd">
<td><p>MidCallReport</p></td>
<td><p>비트만</p></td>
<td><p>보고서가 통화의 일부분에 대한 것인지 전체 통화에 대한 것인지를 나타냅니다.</p></td>
</tr>
<tr class="even">
<td><p>ClassifiedPoorCall</p></td>
<td><p>비트만</p></td>
<td><p>통화가 불량 통화(1)로 분류되었는지 양호한 통화(0)로 분류되었는지를 나타냅니다.</p></td>
</tr>
<tr class="odd">
<td><p>CallerConnectivityICE</p></td>
<td><p>tinyint</p></td>
<td><p>발신자가 ICE(Internet Connectivity Establishment) 프로토콜을 사용하여 네트워크에 연결했는지 여부를 나타냅니다.</p></td>
</tr>
<tr class="even">
<td><p>CalleeConnectivityICE</p></td>
<td><p>tinyint</p></td>
<td><p>전화를 건 사용자가 ICE(Internet Connectivity Establishment) 프로토콜을 사용하여 네트워크에 연결했는지 여부를 나타냅니다.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

