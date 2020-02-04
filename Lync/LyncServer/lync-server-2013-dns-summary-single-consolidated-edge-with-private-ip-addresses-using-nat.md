---
title: DNS 요약 - NAT 사용 개인 IP 주소의 단일 통합 에지
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Single consolidated edge with private IP addresses using NAT
ms:assetid: a7e5d792-f397-45e5-af85-20d0f4bf405f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412787(v=OCS.15)
ms:contentKeyID: 48185025
ms.date: 03/09/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3276219fb4c2227cde75cf9a5d3a47616c03336d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736258"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---single-consolidated-edge-with-private-ip-addresses-using-nat-in-lync-server-2013"></a>Lync Server 2013의 DNS 요약 - NAT 사용 개인 IP 주소의 단일 통합 에지

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2017-03-09_

Lync Server 2013에 대 한 원격 액세스에 대 한 DNS 레코드 요구 사항은 인증서 및 포트에 대 한 것과 매우 간단 합니다. 또한 Lync 2013를 실행 하는 클라이언트를 구성 하는 방법과 페더레이션 사용 여부에 따라 많은 레코드가 선택적입니다.

Lync 2013 DNS 요구 사항에 대 한 자세한 내용은 [Lync Server 2013에 대 한 DNS 요구 사항 결정](lync-server-2013-determine-dns-requirements.md)을 참조 하세요.

분할 두뇌 DNS가 구성 되지 않은 경우 Lync 2013를 실행 하는 클라이언트의 자동 구성에 대 한 자세한 내용은 [Lync Server 2013에 대 한 dns 요구 사항 결정](lync-server-2013-determine-dns-requirements.md)에서 "분할 되지 않은 dns를 사용 하지 않는 자동 구성"을 참조 하세요.

다음 표에는 단일 통합 된 Edge 토폴로지 그림에 표시 된 단일 통합 edge 토폴로지를 지 원하는 데 필요한 DNS 레코드에 대 한 요약이 나와 있습니다. 특정 DNS 레코드는 Lync 2013 및 Lync 2010 클라이언트의 자동 구성에만 필요 합니다. Gpo (그룹 정책 개체)를 사용 하 여 Lync 클라이언트를 구성 하려는 경우에는 연결 된 자동 구성 레코드가 필요 하지 않습니다.

<div>

## <a name="important-edge-server-network-adapter-requirements"></a>중요: Edge 서버 네트워크 어댑터 요구 사항

라우팅 문제를 방지 하려면 Edge 서버에 두 개 이상의 네트워크 어댑터가 있고 기본 게이트웨이가 외부 인터페이스와 연결 된 네트워크 어댑터에만 설정 되어 있는지 확인 합니다. 예를 들어 통합 된 단일 edge 토폴로지에서 [Lync Server 2013의 개인 IP 주소와 NAT가 있는 단일 통합 된 가장자리](lync-server-2013-single-consolidated-edge-with-private-ip-addresses-and-nat.md)에 표시 되는 것 처럼 기본 게이트웨이는 외부 방화벽 (10.45.16.1)을 가리킵니다.

다음과 같이 Edge 서버에서 두 개의 네트워크 어댑터를 구성할 수 있습니다.

  - **네트워크 어댑터 1 (내부 인터페이스)**
    
    172.25.33.10이 할당 된 내부 인터페이스입니다.
    
    기본 게이트웨이가 정의 되어 있지 않습니다.
    
    Edge 내부 인터페이스를 포함 하는 네트워크에서 Lync Server 2013 또는 Lync Server 2013 클라이언트를 실행 하는 서버를 포함 하는 네트워크에 대 한 경로가 있는지 확인 합니다 (예: 172.25.33.0에서 192.168.10.0).

  - **네트워크 어댑터 2 (외부 인터페이스)**
    
    이 네트워크 어댑터에는 세 개의 개인 IP 주소가 할당 됩니다 (예: 액세스 Edge 용 10.45.16.10, 10.45.16.20 웹 컨퍼런스 Edge, AV Edge 용 10.45.16.30).
    
    <div>
    

    > [!NOTE]
    > 세 개의 Edge 서비스 인터페이스에 대해 단일 IP 주소를 사용 하는 것은 권장 되지 않지만 가능 합니다. 이것은 IP 주소를 저장 하지만, 서비스 마다 다른 포트 번호가 필요 합니다. 기본 포트 번호는 대부분의 원격 방화벽에서 트래픽을 허용 하도록 보장 하는 443/TCP입니다. 포트 값을 (예:) 액세스 Edge에 대해 5061/tcp로 변경 하면, AV Edge에 대 한 444/TCP는 해당 사용자가 뒤에 있는 방화벽이 5061/TCP 및 444를 통해 트래픽을 허용 하지 않는 리모컨에 문제가 발생할 수 있습니다. 또한 IP 주소에 따라 필터링이 가능 하기 때문에 세 개의 고유한 IP 주소를 통해 문제를 더 쉽게 해결할 수 있습니다.

    
    </div>
    
    Access Edge IP 주소는 기본 게이트웨이가 통합 라우터 (10.45.16.1)로 설정 된 기본입니다.
    
    웹 회의 및 A/V Edge IP 주소 보조.

<div>


> [!TIP]
> 두 개의 네트워크 어댑터를 사용 하 여 Edge 서버를 구성 하는 옵션은 두 가지입니다. 또 다른 옵션은 Edge 서버의 외부 측면에 대 한 네트워크 어댑터와 내부 측면을 각각 세 개 사용 하는 것입니다. 이 옵션의 주요 이점은 각에 지 서버 서비스에 대 한 고유한 네트워크 어댑터 이며 문제 해결이 필요할 때 더욱 간결한 데이터 수집을 할 수 있습니다.



</div>

### <a name="dns-records-required-for-single-consolidated-edge-with-private-ip-addresses-using-nat-example"></a>NAT를 사용 하 여 개인 IP 주소가 있는 단일 통합 된 가장자리에 대해 필요한 DNS 레코드 (예제)

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>위치/형식/포트</th>
<th>FQDN/DNS 레코드</th>
<th>IP 주소/FQDN</th>
<th>/메모에 매핑</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>외부 DNS/A</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>131.107.155.10</p></td>
<td><p>Lync를 사용 하는 사용자가 모든 SIP 도메인에 필요한 경우 액세스에 지 외부 인터페이스 (Contoso) 반복</p></td>
</tr>
<tr class="even">
<td><p>외부 DNS/A</p></td>
<td><p>webcon.contoso.com</p></td>
<td><p>131.107.155.20</p></td>
<td><p>웹 회의 가장자리 외부 인터페이스</p></td>
</tr>
<tr class="odd">
<td><p>외부 DNS/A</p></td>
<td><p>av.contoso.com</p></td>
<td><p>131.107.155.30</p></td>
<td><p>A/V Edge 외부 인터페이스</p></td>
</tr>
<tr class="even">
<td><p>외부 DNS/SRV/443</p></td>
<td><p>_sip _tls. m m .com</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>액세스에 지 외부 인터페이스. 외부에서 작동 하도록 Lync 2013 및 Lync 2010 클라이언트를 자동으로 구성 하는 데 필요 합니다. Lync를 사용 하는 사용자가 있는 모든 SIP 도메인에 대해 필요한 경우 반복 합니다.</p></td>
</tr>
<tr class="odd">
<td><p>External DNS/SRV/5061</p></td>
<td><p>_sipfederationtls _tcp. m m .com</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>"허용 된 SIP 도메인" 이라고 알려진 페더레이션 파트너의 자동 DNS 검색에는 SIP 액세스에 지 외부 인터페이스가 필요 합니다 (이전 릴리스의 확장 페더레이션 이라고 함). Lync를 사용 하는 사용자가 있는 모든 SIP 도메인에 대해 필요한 경우 반복</p></td>
</tr>
<tr class="even">
<td><p>내부 DNS/A</p></td>
<td><p>lsedge.contoso.net</p></td>
<td><p>172.25.33.10</p></td>
<td><p>통합 된 가장자리 내부 인터페이스</p></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]
> 이전 표에 나열 된 레코드는 <EM>.net</EM> 확장 또는 <EM>.com</EM> 확장명으로 표시 되어 분할 하는 DNS를 사용 하지 않는 경우에는 해당 영역이 있어야 하는 영역을 강조 표시 합니다. 분할 하는 DNS를 사용 하는 경우에는 모든 레코드가 내부 또는 외부 DNS 영역 버전에 있든 관계 없이 동일한 <EM>.com</EM> 영역에 있습니다. 자세한 내용은 <A href="lync-server-2013-determine-dns-requirements.md">Lync Server 2013의 dns 요구 사항 결정</A>에서 "분할-두뇌 dns"를 참조 하세요.



</div>

</div>

<div>

## <a name="records-required-for-federation"></a>페더레이션에 필요한 레코드


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>위치/형식/포트</th>
<th>Q</th>
<th>IP 주소/FQDN 호스트 레코드</th>
<th>/메모에 매핑</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>External DNS/SRV/5061</p></td>
<td><p>_sipfederationtls _tcp. m m .com</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>SIP 액세스에 지 외부 인터페이스는 다른 잠재적 페더레이션 파트너에 대 한 페더레이션 자동 DNS 검색을 위해 필요 하며, "허용 된 SIP 도메인" (이전 릴리스의 확장 페더레이션 이라고 함) 이라고 합니다. Lync를 사용 하는 사용자가 있는 모든 SIP 도메인에 대해 필요한 경우 반복</p>



> [!IMPORTANT]
> 이 SRV 레코드는 이동성 및 푸시 알림 클리어 링 하우스에 필요 합니다.

</td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="dns-summary-for-extensible-messaging-and-presence-protocol"></a>확장 가능 메시지 및 현재 상태 프로토콜에 대 한 DNS 요약


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>위치/형식/포트</th>
<th>Q</th>
<th>IP 주소/FQDN 호스트 레코드</th>
<th>/메모에 매핑</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>외부 DNS/SRV/5269</p></td>
<td><p>_xmpp-서버 _tcp. c a m.</p></td>
<td><p>xmpp.contoso.com</p></td>
<td><p>액세스에 지 서비스 또는 Edge 풀의 XMPP 프록시 외부 인터페이스. Lync를 사용 하는 모든 내부 SIP 도메인에 대해 필요에 따라 반복 글로벌 정책, 사용자가 있는 사이트 정책, 또는에 적용 된 사용자 정책을 통해 외부 액세스 정책의 구성을 통해 XMPP 연락처와의 연결을 허용 하는 사용자가 Lync를 사용할 수 있는 사용자. 허용 되는 XMPP 도메인은 XMPP 페더레이션 파트너 정책 에서도 구성 되어야 합니다. 자세한 내용은 관련 <strong>항목을 참조 하세요.</strong></p></td>
</tr>
<tr class="even">
<td><p>외부 DNS/A</p></td>
<td><p>xmpp.contoso.com (예:)</p></td>
<td><p>XMPP 프록시를 호스팅하는 Edge 서버 또는 Edge 풀에 있는 액세스에 지 서비스의 IP 주소</p></td>
<td><p>XMPP 프록시 서비스를 호스트 하는 액세스에 지 서비스 또는 Edge 풀을 가리킵니다. 일반적으로 사용자가 만든 SRV 레코드는이 호스트 (A 또는 AAAA) 레코드를 가리킵니다.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

