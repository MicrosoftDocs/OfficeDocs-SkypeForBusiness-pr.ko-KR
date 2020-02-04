---
title: DNS 요약-XMPP (확장할 수 있는 메시징 및 현재 상태 프로토콜) 페더레이션
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Extensible messaging and presence protocol (XMPP) federation
ms:assetid: 0f720a2a-8ab5-43cc-882a-ab595ed3cec7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618368(v=OCS.15)
ms:contentKeyID: 49105655
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 941996ea1167cf9baeee05567a00c71ea5ed4baa
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737228"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---extensible-messaging-and-presence-protocol-xmpp-federation-in-lync-server-2013"></a>DNS 요약-Lync Server 2013의 확장 가능한 메시징 및 현재 상태 프로토콜 (XMPP) 페더레이션

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2014-04-08_

배포에 대해 XMPP (확장할 수 있는 메시징 및 현재 상태 프로토콜)를 구성 하려면 외부 DNS 서버에 Edge 서버 또는 Edge 풀의 액세스 경계 서비스에 대 한 레코드를 확인 하는 두 개의 DNS (Domain Name System) 레코드를 만듭니다.

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

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에서 XMPP 페더레이션 설정](lync-server-2013-setting-up-xmpp-federation.md)  


[Lync Server 2013에 대한 DNS 요구 사항 확인](lync-server-2013-determine-dns-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

