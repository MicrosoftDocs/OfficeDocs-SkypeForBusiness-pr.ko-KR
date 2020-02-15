---
title: 포트 요약-XMPP (Extensible messaging and 현재 상태 프로토콜) 페더레이션
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
ms.openlocfilehash: 24bbe3d8e38c5226efa81a55f072f8216791b6a4
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038410"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---extensible-messaging-and-presence-protocol-xmpp-federation-in-lync-server-2013"></a>포트 요약-Lync Server 2013의 XMPP (확장 가능한 메시징 및 현재 상태 프로토콜) 페더레이션

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-20_

에 지 서버에 배포 된 XMPP (extensible messaging and 거점 protocol) 프록시에 대해 정의 된 포트 및 프로토콜은 XMPP 페더레이션 파트너에서에 지 서버로의 통신을 허용 하 고,에 지 서버에서 XMPP로의 통신도 가능 합니다. 페더레이션 파트너 또한 프런트 엔드 서버 또는 프런트 엔드 풀에서에 지 서버 또는에 지 풀에 대 한 내부 연결 방화벽에서 규칙이 정의 됩니다.

<div>

## <a name="firewall-summary-for-extensible-messaging-and-presence-protocol"></a>확장 가능 메시징 및 현재 상태 프로토콜에 대한 방화벽 요약


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
<th>원본(IP 주소)</th>
<th>대상(IP 주소)</th>
<th>설명</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>XMPP/TCP/5269</p></td>
<td><p>모두</p></td>
<td><p>액세스에 지 서비스 인터페이스 IP 주소</p></td>
<td><p>XMPP용 표준 서버 간 통신 포트입니다. 페더레이션 XMPP 파트너의에 지 서버 XMPP 프록시에 대 한 통신을 허용 합니다.</p></td>
</tr>
<tr class="even">
<td><p>XMPP/TCP/5269</p></td>
<td><p>액세스에 지 서비스 인터페이스 IP 주소</p></td>
<td><p>모두</p></td>
<td><p>XMPP용 표준 서버 간 통신 포트입니다. 에 지 서버 XMPP 프록시에서 페더레이션 XMPP 파트너와의 통신을 허용 합니다.</p></td>
</tr>
<tr class="odd">
<td><p>XMPP/MTLS/23456</p></td>
<td><p>모두</p></td>
<td><p>내부에 지 서버 인터페이스 IP</p></td>
<td><p>프런트 엔드 서버 또는 프런트 엔드 풀의 XMPP 게이트웨이에서에 지 서버에 대 한 내부 XMPP 트래픽</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013의 XMPP 구성 예-Google 대화를 사용한 XMPP 페더레이션](lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md)  


[Lync Server 2013에서 XMPP 페더레이션 파트너 관리](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

