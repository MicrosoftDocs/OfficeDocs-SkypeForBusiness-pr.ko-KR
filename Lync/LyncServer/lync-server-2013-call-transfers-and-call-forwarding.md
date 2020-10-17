---
title: 'Lync Server 2013: 통화 전송 및 착신 전환'
description: 'Lync Server 2013: 통화 전송 및 착신 전환'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call transfers and call forwarding
ms:assetid: 978610ec-63c7-4cf6-ad7a-9ef91559bf12
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994051(v=OCS.15)
ms:contentKeyID: 51803962
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d9359cb64b386d022eab33e4523dfaccf784075b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565254"
---
# <a name="call-transfers-and-call-forwarding-in-lync-server-2013"></a>Lync Server 2013의 통화 전송 및 착신 전환

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-03-09_

PSTN 끝점이 관련 된 경우 Location-Based 라우팅은 calle의 끝점과 해당 통화가 전송 되거나 전달 되는 끝점 (예: 전송/전달 대상)의 위치를 분석 합니다. Location-Based 라우팅은 두 끝점의 위치에 따라 통화를 전송 또는 전달 해야 하는지 여부를 결정 합니다.

다음 표에서는 PSTN 끝점을 사용한 통화에서 Lync 사용자의 시나리오를 보여 주고, Lync 사용자가 통화를 다른 Lync 사용자에 게 전송 합니다. Transferee의 끝점에 대 한 네트워크 사이트 위치에 따라 Location-Based 라우팅은 통화 전송 또는 전달 라우팅에 영향을 줍니다.

### <a name="initiating-call-transfer-or-forward"></a>착신 전환 또는 전달 시작

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>착신 전환/전달을 시작한 사용자</th>
<th>사용자가 시작 하는 통화 전송 또는 전달을 비롯 한 대상 끝점이 동일한 네트워크 사이트에 있습니다.</th>
<th>사용자가 시작 하는 통화 전송 또는 전달을 통해 대상 끝점이 서로 다른 네트워크 사이트에 있습니다.</th>
<th>대상 끝점이 알 수 없는 네트워크 사이트 또는 Location-Based 라우팅에서 네트워크 사이트를 사용 하도록 설정 되지 않음</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync 사용자</p></td>
<td><p>착신 전환 또는 전송이 허용 됨</p></td>
<td><p>착신 전환 또는 전송이 허용 되지 않음</p></td>
<td><p>착신 전환 또는 전송이 허용 되지 않음</p></td>
</tr>
</tbody>
</table>

  

예를 들어 PSTN 끝점을 사용한 통화의 Lync 사용자가 동일한 네트워크 사이트에 있는 다른 Lync 사용자에 게 호출을 전송 합니다. 이 경우에는 통화 전송이 허용 됩니다.

다음 표에서는 다른 Lync 사용자와 통화 했을 때 Lync 사용자의 시나리오를 보여 주고 사용자 중 한 명에 게 통화를 PSTN 끝점으로 전송 합니다. 통화가 전송 되는 사용자의 위치에 따라이 표에서 Location-Based 라우팅이 통화에 미치는 영향을 자세히 설명 합니다.

### <a name="call-transfer-or-forward-to-pstn-endpoint"></a>PSTN 끝점에 대 한 통화 전송 또는 전달

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>착신 전환/전달 끝점 대상</th>
<th>같은 네트워크 사이트의 Lync 사용자</th>
<th>서로 다른 네트워크 사이트의 Lync 사용자</th>
<th>알 수 없는 네트워크 사이트 또는 네트워크 사이트의 Lync 사용자 하나 또는 둘 다를 Location-Based 라우팅에 사용할 수 없습니다.</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>PSTN 끝점</p></td>
<td><p>전송 된 사용자의 사이트 음성 라우팅 정책에 의해 착신 전환 또는 전송 허용</p></td>
<td><p>전송 된 사용자의 사이트 음성 라우팅 정책에 의해 착신 전환 또는 전송 허용</p></td>
<td><p>Location-Based 라우팅에서 사용 하도록 설정 되지 않은 트렁크을 통해서만 전송 된 사용자의 음성 정책에 의해 착신 전환 또는 전송 허용</p></td>
</tr>
</tbody>
</table>

  
예를 들어 동일한 네트워크 사이트에 있는 다른 Lync 사용자와의 통화에서 Lync 사용자는 통화를 PSTN 끝점으로 전송 하며 통화 전송은 허용 됩니다.

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013의 Location-Based 라우팅에 대 한 시나리오](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

