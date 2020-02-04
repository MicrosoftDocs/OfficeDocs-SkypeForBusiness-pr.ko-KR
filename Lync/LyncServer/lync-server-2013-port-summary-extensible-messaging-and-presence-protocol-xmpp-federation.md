---
title: 포트 요약-XMPP (확장할 수 있는 메시징 및 현재 상태 프로토콜) 페더레이션
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary -  Extensible messaging and presence protocol (XMPP) federation
ms:assetid: 62e98fab-7add-4983-a3fa-dbe74e1c3849
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618371(v=OCS.15)
ms:contentKeyID: 49105658
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0a18129fce98b3bb9bc613f4fc752daadfb6c5ce
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747618"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---extensible-messaging-and-presence-protocol-xmpp-federation-in-lync-server-2013"></a>포트 요약-Lync Server 2013의 확장 가능한 메시징 및 현재 상태 프로토콜 (XMPP) 페더레이션

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-20_

Edge 서버에 배포 된 XMPP (확장할 수 있는 메시징 및 현재 상태 프로토콜) 프록시에 대해 정의 된 포트와 프로토콜은 XMPP 페더레이션 파트너에서 Edge 서버로 통신을 허용 하 고 Edge 서버와 XMPP 간의 통신에도 사용할 수 있습니다. 페더레이션 파트너. 또한 프런트 엔드 서버 또는 프런트 엔드 풀에서 Edge 서버 또는 Edge 풀로의 내부 방화벽에 규칙이 정의 됩니다.

<div>

## <a name="firewall-summary-for-extensible-messaging-and-presence-protocol"></a>확장 가능한 메시징 및 현재 상태 프로토콜에 대 한 방화벽 요약


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>프로토콜/TCP 또는 UDP/포트</th>
<th>원본 (IP 주소)</th>
<th>대상 (IP 주소)</th>
<th>메모</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>XMPP/TCP/5269</p></td>
<td><p>이상</p></td>
<td><p>액세스에 지 서비스 인터페이스 IP 주소</p></td>
<td><p>XMPP 용 표준 서버 대 서버 통신 포트. 페더레이션된 XMPP 파트너의 Edge 서버 XMPP 프록시에 대 한 통신을 허용 합니다.</p></td>
</tr>
<tr class="even">
<td><p>XMPP/TCP/5269</p></td>
<td><p>액세스에 지 서비스 인터페이스 IP 주소</p></td>
<td><p>이상</p></td>
<td><p>XMPP 용 표준 서버 대 서버 통신 포트. Edge 서버 XMPP 프록시에서 페더레이션된 XMPP 파트너와의 통신을 허용 합니다.</p></td>
</tr>
<tr class="odd">
<td><p>XMPP/MTLS/23456</p></td>
<td><p>이상</p></td>
<td><p>내부에 지 서버 인터페이스 IP</p></td>
<td><p>프런트 엔드 서버 또는 프런트 엔드 풀의 XMPP 게이트웨이에서 Edge 서버에 대 한 내부 XMPP 트래픽</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013의 예제 XMPP 구성 - Google Talk와 XMPP 페더레이션](lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md)  


[Lync Server 2013에서 XMPP 페더레이션 파트너 관리](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

