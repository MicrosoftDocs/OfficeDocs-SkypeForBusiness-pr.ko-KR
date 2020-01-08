---
title: 'Lync Server 2013: 동시 연결'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Simultaneous ringing
ms:assetid: df02f919-4d50-4832-9300-6c51f8b4fc56
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994079(v=OCS.15)
ms:contentKeyID: 51803990
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f7303c1fc77d109bd08044c8acff56aaf538790d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981538"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="simultaneous-ringing-in-lync-server-2013"></a>Lync Server 2013의 동시 연결

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-03-09_

상대방이 동시 연결을 사용 하도록 설정 하면 위치 기반 라우팅이 호출 당사자의 위치와 호출 대상의 끝점을 분석 하 여 호출을 라우팅해야 하는지 여부를 결정 합니다.

다음 표에서는 동시 신호음을 사용 하 여 구성 된 사용자와 동시에 발생 하는 대상 사용자가 같은 네트워크 사이트의 다른 네트워크 사이트 또는 알 수 없는 네트워크 사이트에 있는 경우를 보여 줍니다.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>에 대 한 수신 PSTN 통화</th>
<th>호출 수신자와 동일한 네트워크 사이트에 위치</th>
<th>호출 수신자가 아닌 다른 네트워크 사이트에 위치</th>
<th>알 수 없는 네트워크 사이트에 있거나 위치 기반 라우팅에 대해 사용 하도록 설정 되지 않음</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync 사용자</p></td>
<td><p>동시 신호음 허용</p></td>
<td><p>동시 반지 허용 되지 않음</p></td>
<td><p>동시 반지 허용 되지 않음</p></td>
</tr>
</tbody>
</table>

  
다음 표에서는 Lync 사용자 (예: Lync 발신자)에서 동일한 네트워크 사이트, 다른 네트워크 사이트 또는 알 수 없는 네트워크 사이트의 통화를 보여 줍니다. 호출 수신자의 PSTN 끝점 (즉, 휴대 전화)이 동시 링 대상으로 구성 되었습니다. 이 시나리오에서 위치 기반 라우팅은 호출을 피호출자의 동시 링 대상 (예: 휴대 전화)에 라우팅해야 하는지 여부를 결정 합니다.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>동시 링 대상</th>
<th>호출 수신자와 동일한 네트워크 사이트에 위치</th>
<th>호출 수신자가 아닌 다른 네트워크 사이트에 위치</th>
<th>알 수 없는 네트워크 사이트에 있거나 위치 기반 라우팅에 대해 사용 하도록 설정 되지 않음</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>PSTN 끝점</p></td>
<td><p>발신자의 사이트 음성 라우팅 정책을 통해 동시 연결 허용</p></td>
<td><p>발신자의 사이트 음성 라우팅 정책을 통해 동시 연결 허용</p></td>
<td><p>발신자의 음성 정책을 통해 허용 된 동시 연결을 통해 위치 기반 라우팅에 대해 trunks을 사용 하지 않습니다.</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013의 위치 기반 라우팅 시나리오](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

