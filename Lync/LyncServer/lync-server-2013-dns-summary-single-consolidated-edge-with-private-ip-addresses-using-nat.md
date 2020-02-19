---
title: DNS 요약-NAT 사용 개인 IP 주소의 단일 통합에 지
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
ms.openlocfilehash: 71395e8107c2a1fcb5bd999bd49ef73ea556fa13
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137787"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dns-summary---single-consolidated-edge-with-private-ip-addresses-using-nat-in-lync-server-2013"></a>Lync Server 2013의 DNS 요약-NAT를 사용 하는 개인 IP 주소의 단일 통합에 지

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2017-03-09_

Lync Server 2013에 대 한 원격 액세스에 대 한 DNS 레코드 요구 사항은 인증서 및 포트의 경우와 비교 하는 것이 아주 간단 합니다. 또한 대부분의 레코드는 Lync 2013를 실행 하는 클라이언트를 구성 하는 방법과 페더레이션을 사용 하는지 여부에 따라 선택적입니다.

Lync 2013 DNS 요구 사항에 대 한 자세한 내용은 [Lync Server 2013에 대 한 DNS 요구 사항 확인](lync-server-2013-determine-dns-requirements.md)을 참조 하십시오.

분할로 인 한 DNS가 구성 되지 않은 경우 Lync 2013을 실행 하는 클라이언트의 자동 구성에 대 한 자세한 내용은 [Lync Server 2013에 대 한 DNS 요구 사항 결정](lync-server-2013-determine-dns-requirements.md)에서 "분할 되지 않은 dns를 사용 하지 않는 자동 구성"을 참조 하십시오.

다음 표에는 단일 통합 에지 토폴로지 그림에 표시된 단일 통합 에지 토폴로지를 지원하는 데 필요한 DNS 레코드가 요약되어 있습니다. 특정 DNS 레코드는 Lync 2013 및 Lync 2010 클라이언트를 자동으로 구성 하는 경우에만 필요 합니다. Gpo (그룹 정책 개체)를 사용 하 여 Lync 클라이언트를 구성 하려는 경우에는 연결 된 자동 구성 레코드가 필요 하지 않습니다.

<div>

## <a name="important-edge-server-network-adapter-requirements"></a>중요:에 지 서버 네트워크 어댑터 요구 사항

라우팅 문제를 방지 하려면에 지 서버에 네트워크 어댑터가 두 개 이상 있는지, 그리고 외부 인터페이스와 연결 된 네트워크 어댑터에만 기본 게이트웨이가 설정 되었는지 확인 합니다. 예를 들어 [Lync Server 2013의 개인 IP 주소와 NAT를 포함 하는 단일 통합](lync-server-2013-single-consolidated-edge-with-private-ip-addresses-and-nat.md)에 지 토폴로지 그림에 표시 된 것 처럼 기본 게이트웨이는 외부 방화벽 (10.45.16.1)을 가리킵니다.

다음과 같이 에지 서버에 네트워크 어댑터 두 개를 구성할 수 있습니다.

  - **네트워크 어댑터 1(내부 인터페이스)**
    
    172.25.33.10이 지정된 내부 인터페이스입니다.
    
    기본 게이트웨이가 정의되어 있지 않습니다.
    
    에 지 내부 인터페이스를 포함 하는 네트워크에서 Lync Server 2013 또는 Lync Server 2013 클라이언트를 실행 하는 서버가 포함 된 네트워크 (예: 172.25.33.0에서 192.168.10.0로의 경로)가 있는지 확인 합니다.

  - **네트워크 어댑터 2(외부 인터페이스)**
    
    이 네트워크 어댑터에는 세 개의 개인 IP(예: 액세스 에지에 10.45.16.10, 웹 회의 에지에 10.45.16.20, AV 에지에 10.45.16.30)
    
    <div>
    

    > [!NOTE]
    > 권장되지는 않지만 세 가지 에지 서비스 인터페이스 모두에 단일 IP 주소를 사용할 수 있습니다. 이렇게 하면 IP 주소가 저장되지만 각 서비스에 서로 다른 포트 번호가 필요합니다. 기본 포트 번호는 443/TCP로, 가장 원격에 있는 방화벽에서 트래픽이 허용되도록 합니다. 이 포트 값을 변경할 경우(예: 액세스 에지에 5061/TCP, 웹 회의 에지에 444/TCP, AV 에지에 443/TCP) 방화벽에서 5061/TCP 및 444/TCP를 통한 트래픽을 허용하지 않는 원격 사용자에게 문제가 될 수 있습니다. 또한 세 가지 고유 IP 주소를 사용할 경우 IP 주소를 기준으로 필터링할 수 있기 때문에 문제를 해결하기가 더 쉬워집니다.

    
    </div>
    
    액세스 에지 IP 주소는 기본 게이트웨이가 통합 라우터로 설정된 기본 IP 주소입니다(10.45.16.1).
    
    웹 회의 및 A/V 에지 IP 주소는 보조 IP 주소입니다.

<div>


> [!TIP]
> 두 개의 네트워크 어댑터를 사용 하 여에 지 서버를 구성 하는 방법은 두 가지 옵션 중 하나입니다. 또 다른 옵션은에 지 서버의 외부에 세 개의 네트워크 어댑터와 내부 측면에 대해 하나의 네트워크 어댑터를 사용 하는 것입니다. 이 옵션의 주요 이점은 각에 지 서버 서비스에 대 한 고유한 네트워크 어댑터 이며, 문제 해결이 필요한 경우 데이터 수집이 더 간결 해질 수 있습니다.



</div>

### <a name="dns-records-required-for-single-consolidated-edge-with-private-ip-addresses-using-nat-example"></a>NAT를 사용하며 전용 IP 주소를 갖는 단일 통합 에지 토폴로지에 필요한 DNS 레코드(예)

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Location/TYPE/Port</th>
<th>FQDN/DNS 레코드</th>
<th>IP 주소/FQDN</th>
<th>매핑 대상/설명</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>외부 DNS/A</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>131.107.155.10</p></td>
<td><p>액세스 에지 외부 인터페이스(Contoso). Lync를 사용하도록 설정된 사용자의 모든 SIP 도메인에 대해 필요한 만큼 반복하십시오.</p></td>
</tr>
<tr class="even">
<td><p>외부 DNS/A</p></td>
<td><p>webcon.contoso.com</p></td>
<td><p>131.107.155.20</p></td>
<td><p>웹 회의 에지 외부 인터페이스</p></td>
</tr>
<tr class="odd">
<td><p>외부 DNS/A</p></td>
<td><p>av.contoso.com</p></td>
<td><p>131.107.155.30</p></td>
<td><p>A/V 에지 외부 인터페이스</p></td>
</tr>
<tr class="even">
<td><p>외부 DNS/SRV/443</p></td>
<td><p>_sip _tls. contoso.</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>액세스 에지 외부 인터페이스. Lync 2013 및 Lync 2010 클라이언트가 외부적으로 작동 하도록 자동으로 구성 하는 데 필요 합니다. Lync가 설정된 사용자의 모든 SIP 도메인에 대해 필요한 만큼 반복합니다.</p></td>
</tr>
<tr class="odd">
<td><p>외부 DNS/SRV/5061</p></td>
<td><p>_sipfederationtls _tcp. contoso.</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>SIP 액세스 에지 외부 인터페이스. "허용된 SIP 도메인"(이전 버전의 향상된 페더레이션)으로 알려진 페더레이션 파트너의 자동 DNS 검색을 위해 필요합니다. Lync가 설정된 사용자의 모든 SIP 도메인에 대해 필요한 만큼 반복합니다.</p></td>
</tr>
<tr class="even">
<td><p>내부 DNS/A</p></td>
<td><p>lsedge.contoso.net</p></td>
<td><p>172.25.33.10이 지정</p></td>
<td><p>통합 에지 내부 인터페이스</p></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]
> 앞의 표에 나열되어 있는 레코드는 분할 DNS를 사용하지 않을 경우 레코드가 있어야 할 영역을 강조하기 위해 <EM>.net</EM> 확장명 또는 <EM>.com</EM> 확장명으로 표시되어 있습니다. 분할 DNS를 사용하는 경우에는 모든 레코드가 같은 <EM>.com</EM> 영역에 있으므로 내부 버전인지 아니면 외부 DNS 영역 버전인지만 구분하면 됩니다. 자세한 내용은 <A href="lync-server-2013-determine-dns-requirements.md">Lync Server 2013에 대 한 DNS 요구 사항 결정</A>에서 "분할-두뇌 DNS"를 참조 하십시오.



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
<th>Location/TYPE/Port</th>
<th>FQDN</th>
<th>IP 주소/FQDN 호스트 레코드</th>
<th>매핑 대상/설명</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>외부 DNS/SRV/5061</p></td>
<td><p>_sipfederationtls _tcp. contoso.</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>SIP 액세스 에지 외부 인터페이스. 다른 잠재적인 페더레이션 파트너에 대한 사용자의 페더레이션의 자동 DNS 검색을 위해 필요하며 "허용된 SIP 도메인"으로 알려져 있습니다(이전 릴리스의 향상된 페더레이션). Lync가 설정된 사용자의 모든 SIP 도메인에 대해 필요한 만큼 반복합니다.</p>



> [!IMPORTANT]
> 이 SRV 레코드는 모바일 및 푸시 알림 클리어링 하우스에 필요합니다.

</td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="dns-summary-for-extensible-messaging-and-presence-protocol"></a>XMPP(Extensible Messaging and Presence Protocol)의 DNS 요약


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Location/TYPE/Port</th>
<th>FQDN</th>
<th>IP 주소/FQDN 호스트 레코드</th>
<th>매핑 대상/설명</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>외부 DNS/SRV/5269</p></td>
<td><p>_xmpp-.com. _tcp</p></td>
<td><p>xmpp.contoso.com</p></td>
<td><p>액세스에 지 서비스 또는에 지 풀의 XMPP 프록시 외부 인터페이스 Lync 사용 가능 사용자가 있는 모든 내부 SIP 도메인에 대해 필요에 따라 반복 글로벌 정책, 사용자가 있는 사이트 정책 또는 도메인에 적용 되는 사용자 정책을 통해 외부 액세스 정책을 구성 하 여 XMPP 대화 상대와의 연결을 허용 합니다. Lync 사용 가능 사용자입니다. XMPP 페더레이션 파트너 정책 에서도 허용 되는 XMPP 도메인을 구성 해야 합니다. 자세한 내용은 관련 <strong>항목을 참조</strong> 하십시오.</p></td>
</tr>
<tr class="even">
<td><p>외부 DNS/A</p></td>
<td><p>xmpp.contoso.com(예제)</p></td>
<td><p>XMPP 프록시를 호스팅하는에 지 서버 또는에 지 풀에 있는 액세스에 지 서비스의 IP 주소</p></td>
<td><p>XMPP 프록시 서비스를 호스팅하는 액세스에 지 서비스 또는에 지 풀을 가리킵니다. 일반적으로 사용자가 만드는 SRV 레코드는 이 호스트(A 또는 AAAA) 레코드를 가리킵니다.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

