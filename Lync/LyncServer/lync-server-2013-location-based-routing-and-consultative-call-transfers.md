---
title: 'Lync Server 2013: Location-Based 라우팅 및 문의 후 통화 전송'
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
ms.openlocfilehash: 75284736af1307aff4e9c51c8118cf64dbd08568
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48513815"
---
# <a name="location-based-routing-and-consultative-call-transfers-in-lync-server-2013"></a>Lync Server 2013의 라우팅 및 문의 후 통화 전송 Location-Based

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-07-31_

Location-Based 라우팅 회의 응용 프로그램은 Lync 모임에 대 한 Location-Based 라우팅을 적용 하는 것 외에 PSTN 끝점으로 송신 되는 문의 후 통화 전송에 대 한 Location-Based 라우팅 제한이 적용 됩니다. 문의 후 통화 전송은 두 당사자 중 한 사람이 새 사용자에 게 통화를 전송 하는 통화입니다. 예를 들어 PSTN 끝점이 사용자 A (Lync 수신자)를 호출 합니다. 사용자 A PSTN 사용자를 사용자 B (Lync 사용자)에 게 전달 해야 하는지 결정 합니다. 사용자 A가 통화를 PSTN 사용자에 게 저장 하 고 사용자 B에 게 전화 합니다. 사용자 A는 통화 대기를 사용자 B에 게 전송 합니다.

**통화 전송 통화 흐름 문의 후**

![회의 다이어그램의 위치 기반 라우팅](images/Dn362836.e4d43d6f-23d2-49c9-b12b-15248a743f92(OCS.15).jpg "회의 다이어그램의 위치 기반 라우팅")

Location-Based 라우팅이 사용 하도록 설정 된 경우 이전 그림에 표시 된 것 처럼 PSTN 끝점의 통화 전송이 시작 되 면 두 개의 활성 통화, 즉 PSTN 사용자와 Lync 사용자 A 간의 통화, 그리고 Lync 사용자 A와 lync 사용자 B 간의 호출이 만들어집니다. Location-Based 라우팅 회의 응용 프로그램에서 다음 동작이 적용 됩니다.

  - PSTN 통화에 대 한 SIP 트렁크 라우팅에 Lync 사용자 B (즉, 전송 대상)가 있는 네트워크 사이트로 PSTN 통화를 다시 라우팅할 수 있는 권한이 있는 경우에는 통화 전송이 허용 됩니다. 그렇지 않으면 문의 후 통화 전송이 차단 됩니다. 이 인증은 현재 통화를 PSTN 끝점으로 라우팅하는 SIP 트렁크와 동일한 네트워크 사이트에 있는 전송 된 파티의 위치를 기반으로 수행 됩니다.

  - 인바운드 PSTN 통화에 대 한 SIP 트렁크 라우팅에 전송 된 파티 (Lync user B)가 있는 네트워크 사이트로 통화를 라우팅할 권한이 없거나, 전송 된 파티가 알 수 없는 네트워크 사이트에 있는 경우에는 통화 전송 대상으로 PSTN 끝점으로 전송 되는 문의 후 호출이 차단 됩니다.

다음 표에서는 문의 후 통화 전송에 대 한 Location-Based Routing 회의 응용 프로그램에서 Location-Based 라우팅 제한이 적용 되는 방식을 설명 합니다. PBX 끝점이 네트워크 사이트에 직접 연결 되어 있지 않더라도 PBX에 연결 된 SIP 트렁크에 네트워크 사이트를 할당할 수 있습니다. 따라서 PBX 끝점이 네트워크 사이트에 간접적으로 연결 될 수 있습니다.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>통화 전송 된 파티의 네트워크 사이트</p></td>
<td><p>통화 전송 대상의 네트워크 사이트</p></td>
<td><p>동작과</p></td>
</tr>
<tr class="even">
<td><p>PSTN 끝점</p></td>
<td><p>같은 네트워크 사이트의 Lync 사용자 (예: 사이트 1)</p></td>
<td><p>문의 후 전송이 허용 됩니다.</p></td>
</tr>
<tr class="odd">
<td><p>PSTN 끝점</p></td>
<td><p>서로 다른 네트워크 사이트의 Lync 사용자 (예: 사이트 2)</p></td>
<td><p>문의 후 전송을 허용 하지 않습니다.</p></td>
</tr>
<tr class="even">
<td><p>PSTN 끝점</p></td>
<td><p>알 수 없는 네트워크 사이트의 Lync 사용자</p></td>
<td><p>문의 후 전송을 허용 하지 않습니다.</p></td>
</tr>
<tr class="odd">
<td><p>PSTN 끝점</p></td>
<td><p>페더레이션 Lync 사용자</p></td>
<td><p>문의 후 전송을 허용 하지 않습니다.</p></td>
</tr>
<tr class="even">
<td><p>PSTN 끝점</p></td>
<td><p>동일한 사이트의 PBX 끝점 (예: 사이트 1)</p></td>
<td><p>문의 후 전송이 허용 됩니다.</p></td>
</tr>
<tr class="odd">
<td><p>PSTN 끝점</p></td>
<td><p>다른 사이트의 PBX 끝점 (예: 사이트 2)</p></td>
<td><p>문의 후 전송을 허용 하지 않습니다.</p></td>
</tr>
<tr class="even">
<td><p>동일한 사이트의 PBX 끝점 (예: 사이트 1)</p></td>
<td><p>PSTN 끝점</p></td>
<td><p>문의 후 전송이 허용 됩니다.</p></td>
</tr>
<tr class="odd">
<td><p>다른 사이트의 PBX 끝점 (예: 사이트 2)</p></td>
<td><p>PSTN 끝점</p></td>
<td><p>문의 후 전송을 허용 하지 않습니다.</p></td>
</tr>
<tr class="even">
<td><p>모든 사이트의 PBX 끝점</p></td>
<td><p>같은 네트워크 사이트의 Lync 사용자 (예: 사이트 1)</p></td>
<td><p>문의 후 전송이 허용 됩니다.</p></td>
</tr>
<tr class="odd">
<td><p>모든 사이트의 PBX 끝점</p></td>
<td><p>서로 다른 네트워크 사이트의 Lync 사용자 (예: 사이트 2)</p></td>
<td><p>문의 후 전송이 허용 됩니다.</p></td>
</tr>
<tr class="even">
<td><p>모든 사이트의 PBX 끝점</p></td>
<td><p>알 수 없는 네트워크 사이트의 Lync 사용자</p></td>
<td><p>문의 후 전송이 허용 됩니다.</p></td>
</tr>
<tr class="odd">
<td><p>모든 사이트의 PBX 끝점</p></td>
<td><p>페더레이션 Lync 사용자</p></td>
<td><p>문의 후 전송이 허용 됩니다.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

