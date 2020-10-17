---
title: 'Lync Server 2013: 수신 전화'
description: 'Lync Server 2013: 수신 전화'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Incoming calls
ms:assetid: 65b9c1b4-6af7-4527-8c33-22c4442bd209
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994038(v=OCS.15)
ms:contentKeyID: 51803948
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3a72c7fc378240f9751eae8e6c24e9cc601b08d3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547734"
---
# <a name="incoming-calls-in-lync-server-2013"></a>Lync Server 2013의 수신 전화

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-03-09_

Location-Based 라우팅을 사용 하도록 설정 된 사용자에 게 들어오는 호출을 라우팅하는 것은 사용자 끝점의 위치에 따라 달라 집니다. 수신 전화의 라우팅은 다음과 같은 방식으로 영향을 받습니다. 사용자가 Location-Based 라우팅 사용 가능 네트워크 사이트에 있는 끝점에 대 한 수신 호출이 있고 해당 끝점이 PSTN 게이트웨이와 동일한 네트워크 사이트에 있는 경우 통화가 라우팅됩니다. 사용자가 Location-Based 라우팅 사용 가능 네트워크 사이트에 있는 끝점에 대 한 수신 호출이 있고 해당 끝점이 PSTN 게이트웨이와 다른 네트워크 사이트에 있는 경우에는 통화가 라우팅되지 않습니다. 사용자가 수신 전화를 거는 PSTN 게이트웨이와 동일한 네트워크 사이트에 있는 끝점이 없으면 수신 전화가 사용자의 음성 메일로 직접 라우팅되고 부재 중 전화 알림이 발신자에 게 전송 됩니다.

Location-Based 라우팅을 사용 하도록 설정 된 사용자의 착신 전환 설정은 계속 적용 되지만 착신 전환 된 통화에는 사용자의 라우팅 제한이 Location-Based 적용 됩니다.

다음 표에서는 수신자의 끝점 위치에 따라 Location-Based 라우팅이 인바운드 호출의 라우팅에 미치는 영향을 보여 줍니다. PSTN 게이트웨이의 네트워크 사이트는 Location-Based 라우팅을 사용 하도록 설정 되며, Location-Based 라우팅은 동일한 네트워크 사이트 내의 끝점에 대 한 PSTN 통화 라우팅만 허용 합니다.

### <a name="callee-receiving-an-inbound-call-from-the-pstn"></a>수신자가 PSTN에서 인바운드 호출을 수신 합니다.

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>PSTN 게이트웨이와 같은 네트워크 사이트에 있는 수신자의 끝점</th>
<th>PSTN 게이트웨이와 동일한 네트워크 사이트에 있는 수신자의 끝점 없음</th>
<th>알 수 없는 네트워크 사이트에 있는 수신자의 끝점 또는 Location-Based 라우팅을 사용 하도록 설정 되지 않음</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>인바운드 PSTN 통화 라우팅</p></td>
<td><p>수신 전화가 수신자의 끝점으로 라우팅됩니다.</p></td>
<td><p>수신 전화가 수신자의 끝점으로 라우팅되지 않습니다.</p></td>
<td><p>수신 전화가 수신자의 끝점으로 라우팅되지 않습니다.</p></td>
</tr>
</tbody>
</table>

  

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013의 Location-Based 라우팅에 대 한 시나리오](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

