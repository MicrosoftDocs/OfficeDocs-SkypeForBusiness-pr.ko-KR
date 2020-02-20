---
title: 'Lync Server 2013: 인증서 요약-조정 된 통합에 지, 공용 IP 주소의 DNS 부하 분산'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate summary - Scaled consolidated edge, DNS load balancing with public IP addresses
ms:assetid: e87ac448-ee8f-477a-9f33-ce066c1bf093
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205399(v=OCS.15)
ms:contentKeyID: 48185894
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 352a5b675de94cfb32bc65fe4c78d91d55ef9f87
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151158"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="certificate-summary---scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses-in-lync-server-2013"></a>인증서 요약-조정 된 통합에 지, Lync Server 2013의 공용 IP 주소를 사용한 DNS 부하 분산

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-09-08_

Microsoft Lync Server 2013에서는 인증서를 사용 하 여 다른 서버를 상호 인증 하 고 서버에서 서버 및 서버 간 데이터를 클라이언트로 암호화 합니다. 인증서는 서버와 연결된 DNS(Domain Name System) 레코드와 인증서에 적힌 SN(주체 이름) 및 SAN(주체 대체 이름)이 일치해야 합니다. 서버, DNS 레코드 및 인증서 항목을 성공적으로 매핑하기 위해서는 DNS에 등록된 대로 의도한 서버의 FQDN(정규화된 도메인 이름)과 인증서의 SN 및 SAN 항목을 신중하게 계획해야 합니다.

에 지 서버의 외부 인터페이스에 할당 된 인증서가 공용 CA (인증 기관)에서 요청 됩니다. 통합 통신을 위해 인증서를 제공 하는 데 성공 했다고 보여 주는 공용 Ca는 다음 문서에 나와 있습니다 [https://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=929395](https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=929395) . 인증서를 요청할 때 Lync Server 배포 마법사에서 생성 된 인증서 요청을 사용 하거나 공용 ca가 제공 하는 프로세스에 따라 수동으로 요청을 만들 수 있습니다. 인증서를 할당 하면 인증서가 액세스에 지 서비스 인터페이스, 웹 회의에 지 서비스 인터페이스 및 오디오/비디오 인증 서비스에 할당 됩니다. 오디오/비디오 인증 서비스는 인증서를 사용 하 여 오디오 및 비디오 스트림을 암호화 하지 않는 A/V에 지 서비스와 혼동 해서는 안 됩니다. 내부에 지 서버 인터페이스는 내부 (조직) CA의 인증서 또는 공용 CA의 인증서를 사용할 수 있습니다. 내부 인터페이스 인증서에는 SN만 사용되고 SAN 항목은 필요하지 않고 사용되지 않습니다.

<div>


> [!NOTE]  
> 다음 표의 주체 대체 이름 목록에는 참조용으로 두 번째 SIP 항목(sip.fabrikam.com)이 나와 있습니다. 조직의 각 SIP 도메인에 대해, 인증서 주체 대체 이름 목록에 나열된 해당 FQDN을 추가해야 합니다.



</div>

<div>

## <a name="scaled-consolidated-edge-using-dns-load-balancing-with-public-ip-addresses"></a>공용 IP 주소를 사용한 DNS 부하 분산을 사용 하 여 확장 된 통합에 지


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>구성 요소</th>
<th>주체 이름</th>
<th>SAN(주체 대체 이름)/순서</th>
<th>설명</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>확장된 통합 에지(외부 에지)</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>webcon.contoso.com</p>
<p>sip.contoso.com</p>
<p>sip.fabrikam.com</p></td>
<td><p>인증서는 공용 CA의 인증서여야 하며, AOL과의 공용 IM 연결을 배포하려는 경우 서버 EKU 및 클라이언트 EKU를 포함해야 합니다. 또한 확장 된에 지 서버의 경우 인증서 개인 키를 내보낼 수 있어야 하 고 인증서와 개인 키를 각에 지 서버에 복사 해야 합니다. 인증서는 다음에 대한 외부 에지 인터페이스에 지정됩니다.</p>
<ul>
<li><p>액세스 에지</p></li>
<li><p>회의 에지</p></li>
<li><p>A/V 에지</p></li>
</ul>
<p>SAN은 토폴로지 작성기에서 사용자의 정의에 따라 인증서에 자동으로 추가됩니다. 필요에 따라 추가 SIP 도메인 및 지원이 필요한 다른 항목에 대해 SAN 항목을 추가할 수 있습니다. 주체 이름은 SAN에 복제되며 올바른 작업을 위해서는 제공되어야 합니다.</p></td>
</tr>
<tr class="even">
<td><p>확장된 통합 에지(내부 에지)</p></td>
<td><p>lsedge.contoso.net</p></td>
<td><p>SAN이 필요하지 않습니다.</p></td>
<td><p>인증서는 공용 또는 개인 CA에서 발급할 수 있으며, 서버 EKU를 포함해야 합니다. 인증서는 내부 에지 인터페이스에 지정됩니다.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="certificate-summary--public-instant-messaging-connectivity"></a>인증서 요약 - 공용 인스턴트 메시징 연결


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>구성 요소</th>
<th>주체 이름</th>
<th>SAN(주체 대체 이름)/순서</th>
<th>설명</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>외부/액세스 에지</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>sip.contoso.com</p>
<p>webcon.contoso.com</p>
<p>sip.fabrikam.com</p></td>
<td><p>인증서는 공용 CA의 인증서여야 하며, AOL과의 공용 IM 연결을 배포하려는 경우 서버 EKU 및 클라이언트 EKU를 포함해야 합니다. 인증서는 다음에 대한 외부 에지 인터페이스에 지정됩니다.</p>
<ul>
<li><p>액세스 에지</p></li>
<li><p>회의 에지</p></li>
<li><p>A/V 에지</p></li>
</ul>
<p>SAN은 토폴로지 작성기에서 사용자의 정의에 따라 인증서에 자동으로 추가됩니다. 필요에 따라 추가 SIP 도메인 및 지원이 필요한 다른 항목에 대해 SAN 항목을 추가할 수 있습니다. 주체 이름은 SAN에 복제되며 올바른 작업을 위해서는 제공되어야 합니다.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="certificate-summary-for-extensible-messaging-and-presence-protocol"></a>XMPP(Extensible Messaging and Presence Protocol)의 인증서 요약


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>구성 요소</th>
<th>주체 이름</th>
<th>SAN(주체 대체 이름)/순서</th>
<th>설명</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>에 지 서버 또는에 지 풀에 대 한 액세스에 지 서비스 할당</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>webcon.contoso.com</p>
<p>sip.contoso.com</p>
<p>sip.fabrikam.com</p>
<p>xmpp.contoso.com</p>
<p><strong>* contoso.com</strong></p></td>
<td><p>처음 세 개의 SAN 항목은 전체에 지 서버에 대 한 일반 SAN 항목입니다. contoso.com은 루트 도메인 수준에서 XMPP 파트너와의 페더레이션을 위해 필요한 항목입니다. 이 항목은 접미사가 *.contoso.com인 모든 도메인에 대해 XMPP를 허용합니다.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

