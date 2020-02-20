---
title: 'Lync Server 2013: DNS 요약-조정 된 통합에 지, 공용 IP 주소의 DNS 부하 분산'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Scaled consolidated edge, DNS load balancing with public IP addresses
ms:assetid: dc8f096a-a0a4-4f71-8930-88ff8fc089d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205319(v=OCS.15)
ms:contentKeyID: 48185594
ms.date: 03/09/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4f2cd6350a74f4dd054d30d81ac13c15c829d122
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145887"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dns-summary---scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses-in-lync-server-2013"></a>DNS 요약-조정 된 통합에 지, Lync Server 2013의 공용 IP 주소를 사용한 DNS 부하 분산

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2017-03-09_

Lync Server 2013에 대 한 원격 액세스에 대 한 DNS 레코드 요구 사항은 인증서 및 포트의 경우와 비교 하는 것이 아주 간단 합니다. 또한 대부분의 레코드는 Lync 2013를 실행 하는 클라이언트를 구성 하는 방법과 페더레이션을 사용 하는지 여부에 따라 선택적입니다.

Lync 2013 DNS 요구 사항에 대 한 자세한 내용은 [Lync Server 2013에 대 한 DNS 요구 사항 확인](lync-server-2013-determine-dns-requirements.md)을 참조 하십시오.

분할로 인 한 DNS가 구성 되지 않은 경우 Lync 2013 클라이언트의 자동 구성을 구성 하는 방법에 대 한 자세한 내용은 [Lync Server 2013에 대 한 DNS 요구 사항 확인](lync-server-2013-determine-dns-requirements.md)의 "자동 구성 (분할 되지 않은 dns)" 섹션을 참조 하십시오.

다음 표에는 단일 통합 에지 토폴로지 그림에 표시된 단일 통합 에지 토폴로지를 지원하는 데 필요한 DNS 레코드가 요약되어 있습니다. 특정 DNS 레코드는 Lync 2013 클라이언트를 자동으로 구성 하는 경우에만 필요 합니다. Gpo (그룹 정책 개체)를 사용 하 여 Lync 클라이언트를 구성 하려는 경우에는 관련 레코드가 필요 하지 않습니다.

<div>

## <a name="important-edge-server-network-adapter-requirements"></a>중요:에 지 서버 네트워크 어댑터 요구 사항

라우팅 문제를 방지 하려면에 지 서버에 네트워크 어댑터가 두 개 이상 있는지, 그리고 외부 인터페이스와 연결 된 네트워크 어댑터에만 기본 게이트웨이가 설정 되었는지 확인 합니다. 예를 들어 확장 통합에 지 시나리오 그림에 표시 된 것 처럼, [Lync Server 2013의 공용 IP 주소를 사용한 DNS 부하 분산을 사용](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md) 하는 경우에는 기본 게이트웨이가 외부 방화벽을 가리킵니다.

다음과 같이 각 에지 서버에 네트워크 어댑터 두 개를 구성할 수 있습니다.

  - **네트워크 어댑터 1 - 노드 1(내부 인터페이스)**
    
    172.25.33.10이 할당된 내부 인터페이스입니다.
    
    기본 게이트웨이가 정의되어 있지 않습니다.
    
    에 지 내부 인터페이스를 포함 하는 네트워크에서 Lync Server 2013 또는 Lync Server 2013 클라이언트를 실행 하는 서버가 포함 된 네트워크 (예: 172.25.33.0에서 192.168.10.0로의 경로)가 있는지 확인 합니다.

  - **네트워크 어댑터 1 - 노드 2(내부 인터페이스)**
    
    172.25.33.11이 할당된 내부 인터페이스입니다.
    
    기본 게이트웨이가 정의되어 있지 않습니다.
    
    에 지 내부 인터페이스를 포함 하는 네트워크에서 Lync Server 2013 또는 Lync Server 2013 클라이언트를 실행 하는 서버가 포함 된 네트워크 (예: 172.25.33.0에서 192.168.10.0로의 경로)가 있는지 확인 합니다.

  - **네트워크 어댑터 2 - 노드 1(외부 인터페이스)**
    
    A/V에 지 서비스의 경우이 네트워크 어댑터에는 131.107.155.10 (액세스에 지 서비스, 웹 회의에 지 서비스의 경우 131.107.155.20), 131.107.155.30에 대해 세 개의 개인 IP 주소가 할당 됩니다.
    
    액세스에 지 서비스 공용 IP 주소는 기본 게이트웨이가 공용 라우터로 설정 된 기본 게이트웨이 (131.107.155.1)입니다.
    
    웹 회의에 지 서비스 및 A/V에 지 서비스 개인 IP 주소는 Windows Server에서 **로컬 영역 연결 속성** 의 **인터넷 프로토콜 버전 4 (tcp/IPv4)** 및 **인터넷 프로토콜 버전 6 (tcp/IPv6)** 속성에 대 한 **고급** 섹션에 있는 추가 ip 주소입니다.
    
    <div>
    

    > [!NOTE]  
    > 권장되지는 않지만 세 개의 모든 에지 서비스 인터페이스에 대해 단일 IP 주소를 사용할 수도 있습니다. 이렇게 해서 IP 주소를 절약할 수는 있지만 각 서비스에 대해 서로 다른 포트 번호가 필요합니다. 기본 포트 번호는 대부분의 원격 방화벽에서 트래픽을 허용하도록 보장하는 443/TCP입니다. 포트 값을 다음으로 변경 (예: 액세스에 지 서비스의 경우), A/V에 지 서비스의 경우 444/tcp를 사용 하는 경우 원격 사용자에 게 문제가 발생할 수 있는데,이 경우 해당 방화벽에서 들어오는 방화벽이 5061/tcp 및 444/tcp를 통해 트래픽을 허용 하지 않습니다. 또한 서로 다른 세 개의 IP 주소를 사용하면 IP 주소를 필터링할 수 있어 좀더 쉽게 문제를 해결할 수 있습니다.

    
    </div>

  - **네트워크 어댑터 2 노드 2(외부 인터페이스)**
    
    A/V에 지 서비스의 경우이 네트워크 어댑터에는 131.107.155.11 (액세스에 지 서비스, 웹 회의에 지 서비스의 경우 131.107.155.21), 131.107.155.31에 대해 세 개의 개인 IP 주소가 할당 됩니다.
    
    액세스에 지 서비스 공용 IP 주소는 기본 게이트웨이가 공용 라우터로 설정 된 기본 게이트웨이 (131.107.155.1)입니다.
    
    웹 회의에 지 서비스 및 A/V에 지 서비스 개인 IP 주소는 Windows Server에서 **로컬 영역 연결 속성** 의 **인터넷 프로토콜 버전 4 (tcp/IPv4)** 및 **인터넷 프로토콜 버전 6 (tcp/IPv6)** 속성에 대 한 **고급** 섹션에 있는 추가 ip 주소입니다.

<div>


> [!TIP]  
> 두 개의 네트워크 어댑터를 사용 하 여에 지 서버를 구성 하는 방법은 두 가지 옵션 중 하나입니다. 또 다른 옵션은에 지 서버의 외부에 세 개의 네트워크 어댑터와 내부 측면에 대해 하나의 네트워크 어댑터를 사용 하는 것입니다. 이 옵션의 주요 이점은 각에 지 서버 서비스에 대 한 고유한 네트워크 어댑터 이며, 문제 해결이 필요한 경우 데이터 수집이 더 간결 해질 수 있습니다.



</div>

### <a name="dns-records-required-for-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses-example"></a>확장된 통합 에지에 필요한 DNS 레코드, 공용 IP 주소로 DNS 부하 분산(예)

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
<td><p>131.107.155.10 및 131.107.155.11</p></td>
<td><p>Lync (액세스에 지 서비스) 외부 인터페이스 (Contoso) 모든 SIP 도메인에 필요할 때 반복 사용 사용자</p></td>
</tr>
<tr class="even">
<td><p>외부 DNS/A</p></td>
<td><p>webcon.contoso.com</p></td>
<td><p>131.107.155.20 및 131.107.155.21</p></td>
<td><p>웹 회의에 지 서비스 외부 인터페이스</p></td>
</tr>
<tr class="odd">
<td><p>외부 DNS/A</p></td>
<td><p>av.contoso.com</p></td>
<td><p>131.107.155.30 및 131.107.155.31</p></td>
<td><p>A/V에 지 서비스 외부 인터페이스</p></td>
</tr>
<tr class="even">
<td><p>외부 DNS/SRV/443</p></td>
<td><p>_sip _tls. contoso.</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>액세스에 지 서비스 외부 인터페이스 Lync 2013 및 Lync 2010 클라이언트가 외부적으로 작동 하도록 자동으로 구성 하는 데 필요 합니다. Lync가 설정된 사용자의 모든 SIP 도메인에 대해 필요한 만큼 반복합니다.</p></td>
</tr>
<tr class="odd">
<td><p>외부 DNS/SRV/5061</p></td>
<td><p>_sipfederationtls _tcp. contoso.</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>액세스에 지 서비스 외부 인터페이스는 "허용 된 SIP 도메인" (이전 릴리스의 확장 페더레이션 이라고 함) 이라는 페더레이션 파트너의 자동 DNS 검색에 필요 합니다. Lync를 사용하도록 설정된 사용자가 포함된 모든 SIP 도메인에 대해 필요한 만큼 반복합니다.</p></td>
</tr>
<tr class="even">
<td><p>내부 DNS/A</p></td>
<td><p>lsedge.contoso.net</p></td>
<td><p>172.25.33.10 및 172.25.33.11</p></td>
<td><p>통합 에지 내부 인터페이스</p></td>
</tr>
</tbody>
</table>


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
<td><p>SIP 액세스에 지 서비스 외부 인터페이스는 다른 잠재적 페더레이션 파트너에 대 한 페더레이션을 자동으로 검색 하는 데 필요 하며, "허용 SIP 도메인" (이전 릴리스의 향상 된 페더레이션 이라고 함) 이라고 합니다.</p>
<div>

> [!IMPORTANT]  
> Lync를 사용할 수 있는 모든 SIP 도메인 및 푸시 알림 서비스 또는 Apple 푸시 알림 서비스를 사용 하는 Microsoft Lync 모바일 클라이언트에 대해 필요에 따라 반복


</div></td>
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

