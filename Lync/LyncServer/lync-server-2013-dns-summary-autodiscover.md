---
title: 'Lync Server 2013: DNS 요약-자동 검색'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Autodiscover
ms:assetid: b336a2ae-0e58-4b74-b606-aedbbd411587
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945644(v=OCS.15)
ms:contentKeyID: 51541504
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fc30b787d938825f229f28b10d54907ad26a4d35
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48501325"
---
# <a name="dns-summary---autodiscover-in-lync-server-2013"></a>Lync Server 2013의 DNS 요약-자동 검색

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-02-13_

자동 검색은 HTTP 또는 HTTPS를 통한 통신을 허용 하는 유연한 서비스입니다. 이를 위해 DNS (domain name system) 및 자동 검색 서비스를 호스트 하는 서버에서 사용 하는 인증서를 올바르게 구성 해야 합니다. 인증서 요구 사항은 [Lync Server 2013의 인증서 요약-자동 검색](lync-server-2013-certificate-summary-autodiscover.md)에 설명 되어 있습니다.

<div>


> [!IMPORTANT]  
> Lync Server 클라이언트의 DNS 조회 논리는 구체적인 확인 순서를 사용 합니다. 항상 lyncdiscoverinternal를 모두 포함 해야 합니다. &lt; 도메인 &gt; 및 lyncdiscover &lt; &gt; DNS의 도메인 Lyncdiscoverinternal를 제외 합니다. &lt; 도메인 레코드를 사용 하면 &gt; 내부 클라이언트가 의도 한 서비스에 연결 하지 못하거나 잘못 된 자동 검색 응답을 받을 수 없게 됩니다.



</div>

### <a name="internal-dns-records"></a>내부 DNS 레코드

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>레코드 종류</th>
<th>호스트 이름</th>
<th>확인 대상</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CNAME</p></td>
<td><p>&lt;Lyncdiscoverinternal 내부 도메인 이름&gt;</p></td>
<td><p>디렉터 풀에 대 한 내부 웹 서비스 FQDN (있는 경우) 또는 디렉터가 없는 경우 프런트 엔드 풀에 대해 사용할 수 있습니다.</p></td>
</tr>
<tr class="even">
<td><p>A (호스트, if IPv6, AAAA)</p></td>
<td><p>&lt;lyncdiscoverinternal 내부 도메인 이름&gt;</p></td>
<td><p>디렉터 풀에 대 한 내부 웹 서비스 IP 주소 (부하 분산 장치를 사용 하는 경우 VIP (가상 IP) 주소)가 있고 디렉터가 없는 경우 프런트 엔드 풀이 하나 이상 있어야 합니다.</p></td>
</tr>
</tbody>
</table>


다음 외부 DNS 레코드 중 하나를 만들어야 합니다.

### <a name="external-dns-records"></a>외부 DNS 레코드

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>레코드 종류</th>
<th>호스트 이름</th>
<th>확인 대상</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CNAME</p></td>
<td><p>lyncdiscover &lt; microsoft.rtc.management.xds.sipdomain object&gt;</p></td>
<td><p>디렉터 풀에 대 한 외부 웹 서비스 FQDN (있는 경우) 또는 디렉터가 없는 경우 프런트 엔드 풀의 경우.</p></td>
</tr>
<tr class="even">
<td><p>A (호스트, if IPv6, AAAA)</p></td>
<td><p>lyncdiscover &lt; microsoft.rtc.management.xds.sipdomain object&gt;</p></td>
<td><p>역방향 프록시의 외부 또는 공용 IP 주소입니다.</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> 외부 트래픽은 역방향 프록시를 통과합니다.



</div>

<div>


> [!NOTE]  
> 모바일 장치는 서로 다른 도메인에서 여러 SSL(Secure Sockets Layer) 인증서를 지원할 수 없습니다. 따라서 HTTPS를 통해서는 다른 도메인으로의 CNAME 리디렉션이 지원되지 않습니다. 예를 들어 director.contoso.net 주소로 리디렉션되는 lyncdiscover.contoso.com의 DNS CNAME 레코드는 HTTPS에서 지원되지 않습니다. 이러한 토폴로지에서는 HTTP를 통해 CNAME 리디렉션이 확인되도록 모바일 장치 클라이언트가 첫 번째 요청에 대해 HTTP를 사용해야 합니다. 후속 요청에서는 HTTPS를 사용합니다. 이 시나리오를 지원하려면 포트 80(HTTP)에 대한 웹 게시 규칙을 사용하여 역방향 프록시를 구성해야 합니다. 자세한 내용은 <A href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">Lync Server 2013에서 모바일 기능에 대 한 역방향 프록시 구성</A>의 "포트 80에 대 한 웹 게시 규칙을 만들려면"을 참조 하십시오. 동일한 도메인으로의 CNAME 리디렉션은 HTTPS를 통해 지원됩니다. 이 경우 대상 도메인의 인증서가 원래 도메인을 포함 합니다.



</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에서 모바일 기능에 대 한 역방향 프록시 구성](lync-server-2013-configuring-the-reverse-proxy-for-mobility.md)  


[Lync Server 2013의 인증서 요약-자동 검색](lync-server-2013-certificate-summary-autodiscover.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

