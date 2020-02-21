---
title: 'Lync Server 2013: 인증서 요약-XMPP (Extensible messaging and 거점 protocol) 페더레이션'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate summary - Extensible messaging and presence protocol (XMPP) federation
ms:assetid: b059a34e-99df-40af-91fe-fe2aa52841f6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618374(v=OCS.15)
ms:contentKeyID: 49105661
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 45758175a04bad0cc673242087c0a4751c1b01bc
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42187431"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="certificate-summary---extensible-messaging-and-presence-protocol-xmpp-federation-in-lync-server-2013"></a>Lync Server 2013의 인증서 요약-XMPP (Extensible messaging and 현재 상태 프로토콜) 페더레이션

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-12-23_

XMPP (extensible messaging and 현재 상태 프로토콜) 파트너와의 통신을 사용 하도록 설정 하 고 설정 하기 위한 인증서 요구 사항에 따라 XMPP 도메인을 추가로 기록 해야 합니다. 인증서에 포함 된 레코드는 SAN (주체 대체 이름)으로 XMPP 통신에 참가할 수 있는 도메인이 됩니다. 사용자 하위 집합에 XMPP를 사용 하도록 설정 하는 경우 도메인은 루트 수준 도메인 (예: contoso.com)이 될 수 있으며, 전체 도메인에 대해 XMPP를 설정 하거나 하위 도메인 (예: corp.contoso.com, finance.contoso.com)을 선택할 수 있습니다.

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
<p>contoso.com</p></td>
<td><p>처음 세 개의 SAN 항목은 전체에 지 서버에 대 한 일반 SAN 항목입니다. contoso.com은 루트 도메인 수준에서 XMPP 파트너와의 페더레이션을 위해 필요한 항목입니다. 이 항목은 contoso.com 접미사를 가진 모든 도메인에 대해 XMPP를 허용 합니다.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013의 XMPP 구성 예-Google 대화를 사용한 XMPP 페더레이션](lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md)  


[Lync Server 2013의에 지 서버 인증서 계획](lync-server-2013-plan-for-edge-server-certificates.md)  


[Lync Server 2013에 대 한에 지 인증서 설정](lync-server-2013-set-up-edge-certificates.md)  
[요청-Set-cscertificate](https://docs.microsoft.com/powershell/module/skype/Request-CsCertificate)  
[Set-cscertificate](https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

