---
title: 'Lync Server 2013: 포트 요약-공용 인스턴트 메시징 연결'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Public instant messaging connectivity
ms:assetid: f46756ec-1401-4ca2-a4a4-5cd28bcfdc7f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618376(v=OCS.15)
ms:contentKeyID: 49105663
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bfc057f4d41104dcebc89003ff77eb75622ee3c1
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42183931"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="port-summary---public-instant-messaging-connectivity-in-lync-server-2013"></a>포트 요약-Lync Server 2013의 공용 인스턴트 메시징 연결

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-02-16_

공용 인스턴트 메시징 연결을 지 원하는 데 필요한 포트 및 프로토콜에 대 한 방화벽을 구성 하려면 먼저 SIP/MTLS/TCP 5061는 공용 IM 공급자에서 Lync 클라이언트에 연결 하거나 Lync에서 공용 IM 대화 상대와 연락 하는 연락처의 기능을 고려 하는 것이 좋습니다.

Windows Live Messenger는 Lync 클라이언트와의 오디오/비디오 통신에 참가할 수 있습니다. 이는 외부 사용자로 Lync 클라이언트를 지원 하기 위해 일반적으로 방화벽에 포함 되는 매우 유사한 방화벽 포트 및 프로토콜 구성에 대 한 계정입니다.

<div>


> [!IMPORTANT]  
> 이전 보다 Lync는 전 세계의 조직과 조직 간에 연결 하는 강력한 도구입니다. Windows Live Messenger와 페더레이션 하려면 Lync Standard CAL (클라이언트 액세스 라이선스) 이외의 추가 사용자/장치 라이선스가 필요 하지 않습니다. Lync 사용자가 IM 및 음성을 사용 하 여 수백만 명의 사용자에 게 도달할 수 있도록 하는이 목록에 Skype 페더레이션이 추가 됩니다.<BR>Messenger 클라이언트 연락처와의 페더레이션은 공식적인 중국을 제외 하 고는 2013 년 3 월 15 일에 공식적으로 끝납니다. Skype는 이전에 Messenger를 사용한 페더레이션 사용자의 페더레이션 클라이언트가 됩니다.



</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a>방화벽 요약 - 공용 인스턴트 메시징 연결


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
<th>Notes</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>MTLS (액세스/SIP)/TCP/5061</p></td>
<td><p>공용 IM 연결 파트너</p></td>
<td><p>에 지 서버 액세스 인터페이스</p></td>
<td><p>SIP를 사용 하는 페더레이션 및 공용 IM 연결의 경우</p></td>
</tr>
<tr class="even">
<td><p>MTLS (액세스/SIP)/TCP/5061</p></td>
<td><p>에 지 서버 액세스 인터페이스</p></td>
<td><p>공용 IM 연결 파트너</p></td>
<td><p>SIP를 사용 하는 페더레이션 및 공용 IM 연결의 경우</p></td>
</tr>
<tr class="odd">
<td><p>TLS (액세스/SIP)/TCP/443</p></td>
<td><p>클라이언트</p></td>
<td><p>에 지 서버 액세스 인터페이스</p></td>
<td><p>외부 사용자 액세스에 대 한 클라이언트-서버 SIP 트래픽</p></td>
</tr>
<tr class="even">
<td><p>A/V/RTP/TCP/50000-59999</p></td>
<td><p>에 지 서버 액세스 인터페이스</p></td>
<td><p>Live Messenger 클라이언트</p></td>
<td><p>공용 IM 연결이 구성된 경우 Windows Live Messenger와의 A/V 세션에 사용됨</p></td>
</tr>
<tr class="odd">
<td><p>A/V/STUN, MSTURN/UDP/3478</p></td>
<td><p>에 지 서버 액세스 인터페이스</p></td>
<td><p>Live Messenger 클라이언트</p></td>
<td><p>Windows Live Messenger와의 공용 IM 연결에 필요 합니다.</p></td>
</tr>
<tr class="even">
<td><p>A/V/STUN, MSTURN/UDP/3478</p></td>
<td><p>Live Messenger 클라이언트</p></td>
<td><p>에 지 서버 액세스 인터페이스</p></td>
<td><p>Windows Live Messenger와의 공용 IM 연결에 필요 합니다.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013의 외부 사용자 액세스에 대 한 시나리오](lync-server-2013-scenarios-for-external-user-access.md)  
[Lync Server 2013에 대 한 외부 A/V 방화벽 및 포트 요구 사항 확인](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

