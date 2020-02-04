---
title: 인증서 요약-SIP, XMPP 페더레이션 및 공개 인스턴트 메시지
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
ms.openlocfilehash: 0fc3b7a1745d045954fb06403dbb3359fb699a29
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730218"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="certificate-summary---sip-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a>인증서 요약-SIP, XMPP 페더레이션 및 Lync Server 2013의 공개 인스턴트 메시지

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-03-15_

Microsoft Lync Server 2013, Lync Server 2010 및 Office Communications Server와 페더레이션 하는 데 필요한 인증서는 일반적으로 사용자가 구성 하 고, 요청 하 고, Edge 서버에 할당 하는 인증서에 의해 충족 됩니다.

확장 가능한 메시징 및 현재 상태 프로토콜 (XMPP) 파트너와 통신을 설정 하 고 설정 하기 위한 인증서 요구 사항은 XMPP 도메인에 대 한 항목을 추가로 추가 해야 합니다. 인증서에 포함 된 레코드는 SAN (주체 대체 이름)으로 XMPP 통신에 참여할 수 있는 도메인이 됩니다. 사용자의 하위 집합에 대해 XMPP를 사용 하는 경우 도메인은 전체 도메인에 대해 XMPP를 사용 하거나 하위 도메인 (예: corp.contoso.com, finance.contoso.com)을 선택할 수 있는 경우 루트 수준 도메인 (예: contoso.com)이 될 수 있습니다.

공용 인스턴트 메시징 연결에 대 한 인증서를 구성 하려면 다른 SIP 페더레이션 형식 또는 표준 Edge 서버 인증서 (AOL)에 인증서 나 인증서가 필요 하다는 점을 제외 하 고는 아무 것도 없음에 유의 하세요 ( 클라이언트 EKU도 포함 하는 Edge 풀의 케이스입니다. 클라이언트 EKU는 인증서에 추가 되며, 사용자의 Edge 서버에 할당 된 외부 공용 인증서의 일부입니다.

Edge 서버 배포에 대 한 올바른 인증서 요구 사항이 충족 되었는지 확인 하려면 **참고**항목 섹션에 나열 된 항목을 검토 하세요.

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
<th>요소가</th>
<th>주체 이름</th>
<th>주제 대체 이름 (SAN)</th>
<th>메모</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>외부/액세스에 지</p></td>
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
<td><p>인증서는 공용 CA에서 가져와야 하며 AOL과의 공용 IM 연결이 배포 될 경우 서버 EKU 및 클라이언트 EKU가 있어야 합니다. 인증서는 다음에 대 한 외부에 지 서버 인터페이스에 할당 됩니다.</p>
<ul>
<li><p>액세스에 지 서비스</p></li>
<li><p>웹 회의에 지 서비스</p></li>
<li><p>A/V에 지 서비스</p></li>
</ul>



> [!NOTE]
> 기술적으로 인증서는 A/V에 할당 되지 않습니다. 보안 통신 및 인증은 MRAS (미디어 릴레이 인증 서비스)를 통해 관리 됩니다. MRAS는 Edge 서버 내부 인터페이스에 할당 된 인증서를 사용 합니다.


<p>San은 토폴로지 작성기의 정의에 따라 인증서에 자동으로 추가 됩니다. 추가 SIP 도메인 및 지원 해야 하는 기타 항목에 대해 필요한 경우 SAN 항목을 추가 합니다. 주체 이름이 SAN에 복제 되 고 올바른 작업을 위해 있어야 합니다.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013의 예제 XMPP 구성 - Google Talk와 XMPP 페더레이션](lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md)  


[Lync Server 2013의 에지 서버 인증서 계획](lync-server-2013-plan-for-edge-server-certificates.md)  
[인증서 요약 - Lync Server 2013의 NAT 사용 개인 IP 주소의 단일 통합 에지](lync-server-2013-certificate-summary-single-consolidated-edge-with-private-ip-addresses-using-nat.md)  
[Lync Server 2013의 인증서 요약 - 공용 IP 주소의 단일 통합 에지](lync-server-2013-certificate-summary-single-consolidated-edge-with-public-ip-addresses.md)  
[Lync Server 2013의 인증서 요약 - 조정된 통합 에지, NAT 사용 개인 IP 주소의 DNS 부하 분산](lync-server-2013-certificate-summary-scaled-consolidated-edge-dns-load-balancing-private-ip.md)  
[Lync Server 2013의 인증서 요약 - 조정된 통합 에지, 공용 IP 주소의 DNS 부하 분산](lync-server-2013-certificate-summary-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)  
[Lync Server 2013의 인증서 요약 - 하드웨어 부하 분산 장치를 사용하는 조정된 통합 에지](lync-server-2013-certificate-summary-scaled-consolidated-edge-with-hardware-load-balancers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

