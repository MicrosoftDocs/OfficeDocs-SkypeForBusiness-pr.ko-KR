---
title: 'Lync Server 2013: 위치 기반 라우팅 및 consultative 통화 전송'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Location-Based Routing and consultative call transfers
ms:assetid: b12460c2-36c8-481f-b867-fe10dc1c0bdf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362836(v=OCS.15)
ms:contentKeyID: 56335089
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4e433baf180b8e4abf50ec374848204bf6628eb0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765336"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="location-based-routing-and-consultative-call-transfers-in-lync-server-2013"></a>Lync Server 2013의 위치 기반 라우팅 및 consultative 통화 전송

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-07-31_

위치 기반 라우팅 회의 응용 프로그램은 Lync 모임에 대 한 위치 기반 라우팅을 적용 하는 것 외에도 PSTN 끝점으로 송신 되는 consultative call 전송에 위치 기반 라우팅 제한을 적용 합니다. Consultative 통화 전송은 파티 중 하나가 새 사용자에 게 통화를 전송 하는 두 당사자 간에 설정 된 통화입니다. 예를 들어 PSTN 끝점은 사용자 A (Lync 호출 수신자)를 호출 합니다. 사용자 A는 PSTN 사용자가 사용자 B (Lync 사용자)로 전달 되어야 하는지 결정 합니다. 사용자 A는 통화를 PSTN 사용자에 게 대기 상태로 설정 하 고 사용자 B를 호출 합니다. 사용자 B가 PSTN 사용자와 대화 하는 데 동의 합니다. 사용자 A가 사용자 B에 게 통화를 전송 합니다.

**Consultative 통화 이전 통화 흐름**

![회의에 대한 위치 기반 라우팅 다이어그램](images/Dn362836.e4d43d6f-23d2-49c9-b12b-15248a743f92(OCS.15).jpg "회의에 대한 위치 기반 라우팅 다이어그램")

위치 기반 라우팅이 사용 하도록 설정 된 사용자가 PSTN 끝점의 consultative call 전송을 시작 하면 (앞의 그림과 같이), PSTN 사용자와 Lync 사용자 A 간, 그리고 Lync 사용자 A와 Lync 사용자 B 간의 다른 호출이 두 개의 활성 호출을 만듭니다. 위치 기반 라우팅 회의 응용 프로그램에서 다음 동작이 적용 됩니다.

  - PSTN 통화 라우팅에 대 한 SIP 트렁크에서 Lync 사용자 B (즉, 대상 전송)가 있는 네트워크 사이트로 PSTN 통화를 다시 라우팅하도록 승인 된 경우에는 통화 전송이 허용 됩니다. 그렇지 않으면 consultative 통화 전송이 차단 됩니다. 이 인증은 현재 통화를 PSTN 끝점으로 라우팅하는 SIP 트렁크와 같은 네트워크 사이트에 있는 상대방의 위치를 기반으로 수행 됩니다.

  - 인바운드 PSTN 통화 라우팅에 대 한 SIP 트렁크에서 전송 된 파티 (Lync 사용자 B)가 있는 네트워크 사이트에 대 한 통화를 라우팅할 권한이 없거나, 전송 된 파티가 알 수 없는 네트워크 사이트에 있는 경우 consultative 통화는 PSTN으로 전송 됩니다. 끝점 (즉, 통화 전송 대상)이 차단 됩니다.

다음 표에서는 consultative 통화 전송에 대 한 위치 기반 라우팅 회의 응용 프로그램에서 위치 기반 라우팅 제한을 적용 하는 방법에 대해 설명 합니다. PBX 끝점은 네트워크 사이트와 직접 연결 되지 않지만 PBX에 연결 된 SIP 트렁크에는 네트워크 사이트를 할당할 수 있습니다. 따라서 PBX 끝점은 네트워크 사이트와 간접적으로 연결 될 수 있습니다.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>통화의 네트워크 사이트 전송 파티</p></td>
<td><p>통화 전송 대상의 네트워크 사이트</p></td>
<td><p>결과가</p></td>
</tr>
<tr class="even">
<td><p>PSTN 끝점</p></td>
<td><p>동일한 네트워크 사이트의 Lync 사용자 (예: 사이트 1)</p></td>
<td><p>Consultative 전송이 허용 됩니다.</p></td>
</tr>
<tr class="odd">
<td><p>PSTN 끝점</p></td>
<td><p>다른 네트워크 사이트 (즉, 사이트 2)의 Lync 사용자</p></td>
<td><p>Consultative 전송이 허용 되지 않습니다.</p></td>
</tr>
<tr class="even">
<td><p>PSTN 끝점</p></td>
<td><p>알 수 없는 네트워크 사이트의 Lync 사용자</p></td>
<td><p>Consultative 전송이 허용 되지 않습니다.</p></td>
</tr>
<tr class="odd">
<td><p>PSTN 끝점</p></td>
<td><p>페더레이션 Lync 사용자</p></td>
<td><p>Consultative 전송이 허용 되지 않습니다.</p></td>
</tr>
<tr class="even">
<td><p>PSTN 끝점</p></td>
<td><p>동일한 사이트의 PBX 끝점 (즉, 사이트 1)</p></td>
<td><p>Consultative 전송이 허용 됩니다.</p></td>
</tr>
<tr class="odd">
<td><p>PSTN 끝점</p></td>
<td><p>다른 사이트의 PBX 끝점 (즉, 사이트 2)</p></td>
<td><p>Consultative 전송이 허용 되지 않습니다.</p></td>
</tr>
<tr class="even">
<td><p>동일한 사이트의 PBX 끝점 (즉, 사이트 1)</p></td>
<td><p>PSTN 끝점</p></td>
<td><p>Consultative 전송이 허용 됩니다.</p></td>
</tr>
<tr class="odd">
<td><p>다른 사이트의 PBX 끝점 (즉, 사이트 2)</p></td>
<td><p>PSTN 끝점</p></td>
<td><p>Consultative 전송이 허용 되지 않습니다.</p></td>
</tr>
<tr class="even">
<td><p>모든 사이트의 PBX 끝점</p></td>
<td><p>동일한 네트워크 사이트의 Lync 사용자 (예: 사이트 1)</p></td>
<td><p>Consultative 전송이 허용 됩니다.</p></td>
</tr>
<tr class="odd">
<td><p>모든 사이트의 PBX 끝점</p></td>
<td><p>다른 네트워크 사이트 (즉, 사이트 2)의 Lync 사용자</p></td>
<td><p>Consultative 전송이 허용 됩니다.</p></td>
</tr>
<tr class="even">
<td><p>모든 사이트의 PBX 끝점</p></td>
<td><p>알 수 없는 네트워크 사이트의 Lync 사용자</p></td>
<td><p>Consultative 전송이 허용 됩니다.</p></td>
</tr>
<tr class="odd">
<td><p>모든 사이트의 PBX 끝점</p></td>
<td><p>페더레이션 Lync 사용자</p></td>
<td><p>Consultative 전송이 허용 됩니다.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

