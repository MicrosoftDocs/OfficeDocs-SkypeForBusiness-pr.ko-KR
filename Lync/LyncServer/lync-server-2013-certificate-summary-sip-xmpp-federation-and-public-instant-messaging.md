---
title: 인증서 요약-SIP, XMPP 페더레이션 및 공용 인스턴트 메시징
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate summary - SIP, XMPP federation, and public instant messaging
ms:assetid: 933d6351-cfa6-4432-b3ed-1aff3ac92065
ms:mtpsurl: https://technet.microsoft.com/library/JJ618372(v=OCS.15)
ms:contentKeyID: 49105659
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 284a633a2c5ce820009c6672058837bbecb7ecd6
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48517875"
---
# <a name="certificate-summary---sip-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a>인증서 요약-Lync Server 2013의 SIP, XMPP 페더레이션 및 공용 인스턴트 메시징

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-03-15_

Microsoft Lync Server 2013, Lync Server 2010 및 Office Communications Server와 페더레이션 하기 위해 필요한 인증서는 일반적으로 구성, 요청 및에 지 서버에 할당 하는 인증서에 의해 충족 됩니다.

XMPP (extensible messaging and 현재 상태 프로토콜) 파트너와의 통신을 사용 하도록 설정 하 고 설정 하기 위한 인증서 요구 사항은 XMPP 도메인에 항목을 추가 해야 합니다. 인증서에 포함 된 레코드는 SAN (주체 대체 이름)으로 XMPP 통신에 참가할 수 있는 도메인이 됩니다. 사용자 하위 집합에 XMPP를 사용 하도록 설정 하는 경우 도메인은 루트 수준 도메인 (예: contoso.com)이 될 수 있으며, 전체 도메인에 대해 XMPP를 설정 하거나 하위 도메인 (예: corp.contoso.com, finance.contoso.com)을 선택할 수 있습니다.

공용 인스턴트 메시징 연결에 대 한 인증서를 구성 하려면 AOL (북미)에는 인증서가 필요 하 고 클라이언트 EKU도 포함 되어 있는지 여부를 제외 하 고는 다른 SIP 페더레이션 형식 또는 표준에 지 서버 인증서와는 다른 것이 좋습니다. 클라이언트 EKU는 인증서에 추가 되며,에 지 서버에 할당 된 외부 공용 인증서의 일부입니다.

에 지 서버 배포에 대 한 올바른 인증서 요구 사항을 충족 했는지 확인 하려면 **참고**항목 섹션에 나열 되어 있는 항목도 검토 하십시오.

<div>



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
<th>SAN(주체 대체 이름)</th>
<th>설명</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>외부/액세스 에지</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>sip.contoso.com</p>
<p>webcon.contoso.com</p>
<p>contoso.com</p>



> [!NOTE]
> Contoso.com XMPP 네임 스페이스를 지원 하려면


<p>sip.fabrikam.com</p>



> [!NOTE]
> Fabrikam.com SIP 네임 스페이스를 지원 하려면


<p>fabrikam.com</p>



> [!NOTE]
> Fabrikam.com XMPP 네임 스페이스를 지원 하려면

</td>
<td><p>이 인증서는 공용 CA에서 발급 한 것 이어야 하며, AOL과의 공용 IM 연결을 배포 하려면 서버 EKU 및 클라이언트 EKU가 있어야 합니다. 인증서는 다음에 대 한 외부에 지 서버 인터페이스에 할당 됩니다.</p>
<ul>
<li><p>Access Edge service(액세스 에지 서비스)</p></li>
<li><p>웹 회의 에지 서비스</p></li>
<li><p>A/V 에지 서비스</p></li>
</ul>



> [!NOTE]
> 기술적으로 인증서가 A/V에 지에 할당 되지 않습니다. 보안 통신 및 인증은 MRAS (미디어 릴레이 인증 서비스)를 통해 관리 됩니다. MRAS는에 지 서버 내부 인터페이스에 할당 된 인증서를 사용 합니다.


<p>SAN은 토폴로지 작성기에서 사용자의 정의에 따라 인증서에 자동으로 추가됩니다. 필요에 따라 추가 SIP 도메인 및 지원이 필요한 다른 항목에 대해 SAN 항목을 추가할 수 있습니다. 주체 이름은 SAN에 복제되며 올바른 작업을 위해서는 제공되어야 합니다.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013의 XMPP 구성 예-Google 대화를 사용한 XMPP 페더레이션](lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md)  


[Lync Server 2013의에 지 서버 인증서 계획](lync-server-2013-plan-for-edge-server-certificates.md)  
[인증서 요약-Lync Server 2013에서 NAT를 사용 하는 개인 IP 주소의 단일 통합에 지](lync-server-2013-certificate-summary-single-consolidated-edge-with-private-ip-addresses-using-nat.md)  
[인증서 요약-Lync Server 2013의 공용 IP 주소를 포함 하는 단일 통합에 지](lync-server-2013-certificate-summary-single-consolidated-edge-with-public-ip-addresses.md)  
[Lync Server 2013의 인증서 요약-조정 된 통합에 지, NAT 사용 개인 IP 주소의 DNS 부하 분산](lync-server-2013-certificate-summary-scaled-consolidated-edge-dns-load-balancing-private-ip.md)  
[인증서 요약-조정 된 통합에 지, Lync Server 2013의 공용 IP 주소를 사용한 DNS 부하 분산](lync-server-2013-certificate-summary-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)  
[Lync Server 2013의 인증서 요약-하드웨어 부하 분산 장치로 확장 된 통합에 지](lync-server-2013-certificate-summary-scaled-consolidated-edge-with-hardware-load-balancers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

