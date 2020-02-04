---
title: 'Lync Server 2013: 인증서 요약-XMPP (확장할 수 있는 메시징 및 현재 상태 프로토콜) 페더레이션'
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
ms.openlocfilehash: 7af2c226397c5225fc26f6dbdf40d12a4bdb1ca0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736628"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-summary---extensible-messaging-and-presence-protocol-xmpp-federation-in-lync-server-2013"></a>인증서 요약-Lync Server 2013의 XMPP (확장할 수 있는 메시징 및 현재 상태 프로토콜) 페더레이션

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-12-23_

XMPP (확장할 수 있는 메시징 및 현재 상태 프로토콜) 파트너와 통신을 사용 하도록 설정 하 고 설정 하기 위한 인증서 요구 사항에 따라 XMPP 도메인의 추가 기록이 필요 합니다. 인증서에 포함 된 레코드는 SAN (주체 대체 이름)으로 XMPP 통신에 참여할 수 있는 도메인이 됩니다. 사용자의 하위 집합에 대해 XMPP를 사용 하는 경우 도메인은 전체 도메인에 대해 XMPP를 사용 하거나 하위 도메인 (예: corp.contoso.com, finance.contoso.com)을 선택할 수 있는 경우 루트 수준 도메인 (예: contoso.com)이 될 수 있습니다.

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
<p>contoso.com</p></td>
<td><p>처음 세 개의 SAN 항목은 전체 Edge 서버에 대 한 일반적인 SAN 항목입니다. Contoso.com는 루트 도메인 수준의 XMPP 파트너와 페더레이션 하는 데 필요한 항목입니다. 이 항목은 접미사 contoso.com를 가진 모든 도메인에 대해 XMPP를 허용 합니다.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013의 예제 XMPP 구성 - Google Talk와 XMPP 페더레이션](lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md)  


[Lync Server 2013의 에지 서버 인증서 계획](lync-server-2013-plan-for-edge-server-certificates.md)  


[Lync Server 2013의 에지 인증서 설정](lync-server-2013-set-up-edge-certificates.md)  
[요청-CsCertificate](https://docs.microsoft.com/powershell/module/skype/Request-CsCertificate)  
[Set-CsCertificate](https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

