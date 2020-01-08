---
title: 'Lync Server 2013: 포트 요약-공용 인스턴트 메시지 연결'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Port summary - Public instant messaging connectivity
ms:assetid: f46756ec-1401-4ca2-a4a4-5cd28bcfdc7f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618376(v=OCS.15)
ms:contentKeyID: 49105663
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5bb6b8d0d9277b7d77440519596da76585b9d91b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982831"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---public-instant-messaging-connectivity-in-lync-server-2013"></a>포트 요약-Lync Server 2013의 공개 인스턴트 메시지 연결

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-02-16_

공용 인스턴트 메시징 연결을 지 원하는 데 필요한 포트 및 프로토콜에 대 한 방화벽을 구성 하려면 먼저 SIP/MTLS/TCP 5061에서 Lync 클라이언트에 연락 하거나 Lync에서 공용 메신저 대화 상대에 게 연락할 수 있도록 공용 IM 공급자의 연락처 기능에 대해 양방향으로 확인 합니다.

Windows Live Messenger는 Lync 클라이언트를 사용 하 여 오디오/비디오 통신에 참가할 수 있습니다. 이는 일반적으로 방화벽에서 외부 사용자로 Lync 클라이언트를 지원 하기 위해 사용 하는 매우 유사한 방화벽 포트와 프로토콜 구성에 대 한 계정입니다.

<div>


> [!IMPORTANT]  
> 이전 보다 훨씬 더 많은 수의 Lync는 전세계의 조직과 사용자 간에 연결 하는 강력한 도구입니다. Windows Live Messenger를 사용 하는 페더레이션에서는 Lync Standard CAL (표준 클라이언트 액세스 라이선스) 이외의 추가 사용자/장치 라이선스가 필요 하지 않습니다. Skype 페더레이션이이 목록에 추가 되어 Lync 사용자가 IM 및 음성을 사용 하 여 수백만 명의 사용자에 게 연락할 수 있도록 합니다.<BR>Messenger 클라이언트 연락처와의 페더레이션은 공식적으로 중국을 제외한 2013 년 3 월 15 일에 완료 됩니다. Skype는 이전에 Messenger를 사용 하는 페더레이션 사용자의 페더레이션 클라이언트가 됩니다.



</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a>방화벽 요약-공용 인스턴트 메시지 연결


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>역할/프로토콜/TCP 또는 UDP/포트</th>
<th>원본 IP 주소</th>
<th>대상 IP 주소</th>
<th>상속자</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>MTLS (액세스/SIP)/TCP/5061</p></td>
<td><p>공용 IM 연결 파트너</p></td>
<td><p>Edge 서버 액세스 인터페이스</p></td>
<td><p>SIP를 사용 하는 페더레이션 및 공용 인스턴트 메시지 연결</p></td>
</tr>
<tr class="even">
<td><p>MTLS (액세스/SIP)/TCP/5061</p></td>
<td><p>Edge 서버 액세스 인터페이스</p></td>
<td><p>공용 IM 연결 파트너</p></td>
<td><p>SIP를 사용 하는 페더레이션 및 공용 인스턴트 메시지 연결</p></td>
</tr>
<tr class="odd">
<td><p>TLS (액세스/SIP)/TCP/443</p></td>
<td><p>클라이언트</p></td>
<td><p>Edge 서버 액세스 인터페이스</p></td>
<td><p>외부 사용자 액세스를 위한 클라이언트 대 서버 SIP 트래픽.</p></td>
</tr>
<tr class="even">
<td><p>A/V/RTP/TCP/50000-59999</p></td>
<td><p>Edge 서버 액세스 인터페이스</p></td>
<td><p>실시간 메신저 클라이언트</p></td>
<td><p>공용 메신저 연결이 구성 되어 있는 경우 Windows Live Messenger를 사용 하 여 A/V 세션에 사용 합니다.</p></td>
</tr>
<tr class="odd">
<td><p>A/V/STUN, MSTURN/UDP/3478</p></td>
<td><p>Edge 서버 액세스 인터페이스</p></td>
<td><p>실시간 메신저 클라이언트</p></td>
<td><p>Windows Live Messenger를 사용 하는 공용 메신저 연결에 필요 합니다.</p></td>
</tr>
<tr class="even">
<td><p>A/V/STUN, MSTURN/UDP/3478</p></td>
<td><p>실시간 메신저 클라이언트</p></td>
<td><p>Edge 서버 액세스 인터페이스</p></td>
<td><p>Windows Live Messenger를 사용 하는 공용 메신저 연결에 필요 합니다.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013의 외부 사용자 액세스에 대한 시나리오](lync-server-2013-scenarios-for-external-user-access.md)  
[Lync Server 2013에 대한 외부 A/V 방화벽 및 포트 요구 사항 확인](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

