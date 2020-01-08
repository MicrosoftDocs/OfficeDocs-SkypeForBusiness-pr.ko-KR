---
title: 'Lync Server 2013: 인증서 요약 - 조정된 통합 에지, 공용 IP 주소의 DNS 부하 분산'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Certificate summary - Scaled consolidated edge, DNS load balancing with public IP addresses
ms:assetid: e87ac448-ee8f-477a-9f33-ce066c1bf093
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205399(v=OCS.15)
ms:contentKeyID: 48185894
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 07f910656ce80e9b2dc78db0fc73b2f9ef00c4f8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983998"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-summary---scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses-in-lync-server-2013"></a>Lync Server 2013의 인증서 요약 - 조정된 통합 에지, 공용 IP 주소의 DNS 부하 분산

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-09-08_

Microsoft Lync Server 2013는 인증서를 사용 하 여 다른 서버를 상호 인증 하 고 서버에서 서버와 서버 간의 데이터를 클라이언트에 암호화 합니다. 인증서에는 서버와 연결 된 DNS (domain name system) 레코드와 인증서의 주체 이름 (SN) 및 주체 대체 이름 (SAN)의 이름이 일치 해야 합니다. 서버, DNS 레코드, 인증서 항목을 성공적으로 매핑하려면 DNS에 등록 되어 있는 서버 정규화 된 도메인 이름 및 인증서의 SN 및 SAN 항목을 신중 하 게 계획 해야 합니다.

Edge 서버의 외부 인터페이스에 할당 된 인증서는 공용 CA (인증 기관)에서 요청 합니다. 통합 커뮤니케이션의 목적으로 인증서를 제공 하는 데 성공 했다고 보여주는 공용 Ca는 다음 문서에 나열 되어 [http://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=929395](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=929395) 있습니다. 인증서 요청 시 Lync Server 배포 마법사에서 생성 된 인증서 요청을 사용 하거나 수동으로 또는 공용 CA가 제공 하는 프로세스를 통해 요청을 만들 수 있습니다. 인증서를 할당할 때 인증서는 액세스 경계 서비스 인터페이스, 웹 회의에 지 서비스 인터페이스 및 오디오/비디오 인증 서비스에 할당 됩니다. 오디오/비디오 인증 서비스는 오디오 및 비디오 스트림을 암호화 하는 데 인증서를 사용 하지 않는 A/V Edge 서비스와 혼동 하지 않아야 합니다. 내부에 지 서버 인터페이스는 내부 (조직에 대 한) CA 또는 공용 CA의 인증서에 대 한 인증서를 사용할 수 있습니다. 내부 인터페이스 인증서는 SN만 사용 하 고 SAN 항목은 필요 하지 않거나 사용할 필요가 없습니다.

<div>


> [!NOTE]  
> 다음 표에서는 참조에 대 한 주체 대체 이름 목록의 두 번째 SIP 항목 (sip.fabrikam.com)을 보여 줍니다. 조직의 각 SIP 도메인에 대해 인증서 주체 대체 이름 목록에 나열 된 해당 FQDN을 추가 해야 합니다.



</div>

<div>

## <a name="scaled-consolidated-edge-using-dns-load-balancing-with-public-ip-addresses"></a>공용 IP 주소와 함께 DNS 부하 분산을 사용 하 여 크기가 조정 된 통합 된 가장자리


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>요소가</th>
<th>주체 이름</th>
<th>SAN (주체 대체 이름)/Order</th>
<th>메모</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>크기가 조정 된 통합 된 가장자리 (외부 가장자리)</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>webcon.contoso.com</p>
<p>sip.contoso.com</p>
<p>sip.fabrikam.com</p></td>
<td><p>인증서는 공용 CA에서 가져온 것 이어야 하며 AOL과 공용 IM 연결을 배포 하는 경우 서버 EKU 및 클라이언트 EKU가 있어야 합니다. 또한 확장 가능한 Edge 서버의 경우 인증서 개인 키를 내보낼 수 있어야 하 고 각 Edge 서버에 인증서와 개인 키를 복사 해야 합니다. 인증서는 다음에 대 한 외부에 지 인터페이스에 할당 됩니다.</p>
<ul>
<li><p>액세스에 지</p></li>
<li><p>회의 가장자리</p></li>
<li><p>A/V 가장자리</p></li>
</ul>
<p>San은 토폴로지 작성기의 정의에 따라 인증서에 자동으로 추가 됩니다. 추가 SIP 도메인 및 지원 해야 하는 기타 항목에 대해 필요한 경우 SAN 항목을 추가 합니다. 주체 이름이 SAN에 복제 되 고 올바른 작업을 위해 있어야 합니다.</p></td>
</tr>
<tr class="even">
<td><p>크기가 조정 된 통합 된 가장자리 (내부 가장자리)</p></td>
<td><p>lsedge.contoso.net</p></td>
<td><p>SAN 필요 없음</p></td>
<td><p>인증서는 공용 또는 개인 CA에 의해 발급 될 수 있으며 서버 EKU를 포함 해야 합니다. 인증서가 내부에 지 인터페이스에 할당 됩니다.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="certificate-summary--public-instant-messaging-connectivity"></a>인증서 요약-공용 인스턴트 메시지 연결


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>요소가</th>
<th>주체 이름</th>
<th>SAN (주체 대체 이름)/Order</th>
<th>메모</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>외부/액세스에 지</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>sip.contoso.com</p>
<p>webcon.contoso.com</p>
<p>sip.fabrikam.com</p></td>
<td><p>인증서는 공용 CA에서 가져온 것 이어야 하며 AOL과 공용 IM 연결을 배포 하는 경우 서버 EKU 및 클라이언트 EKU가 있어야 합니다. 인증서는 다음에 대 한 외부에 지 인터페이스에 할당 됩니다.</p>
<ul>
<li><p>액세스에 지</p></li>
<li><p>회의 가장자리</p></li>
<li><p>A/V 가장자리</p></li>
</ul>
<p>San은 토폴로지 작성기의 정의에 따라 인증서에 자동으로 추가 됩니다. 추가 SIP 도메인 및 지원 해야 하는 기타 항목에 대해 필요한 경우 SAN 항목을 추가 합니다. 주체 이름이 SAN에 복제 되 고 올바른 작업을 위해 있어야 합니다.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="certificate-summary-for-extensible-messaging-and-presence-protocol"></a>확장 가능한 메시징 및 현재 상태 프로토콜에 대 한 인증서 요약


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>요소가</th>
<th>주체 이름</th>
<th>SAN (주체 대체 이름)/Order</th>
<th>메모</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Edge 서버 또는 Edge 풀에 대 한 액세스에 지 서비스에 할당</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>webcon.contoso.com</p>
<p>sip.contoso.com</p>
<p>sip.fabrikam.com</p>
<p>xmpp.contoso.com</p>
<p><strong>*. contoso.com</strong></p></td>
<td><p>처음 세 개의 SAN 항목은 전체 Edge 서버에 대 한 일반적인 SAN 항목입니다. Contoso.com는 루트 도메인 수준의 XMPP 파트너와 페더레이션 하는 데 필요한 항목입니다. 이 항목은 접미사 *. contoso.com를 사용 하는 모든 도메인에 대해 XMPP를 허용 합니다.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

