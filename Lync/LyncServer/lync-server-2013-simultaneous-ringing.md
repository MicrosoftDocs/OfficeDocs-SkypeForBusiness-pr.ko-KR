---
title: 'Lync Server 2013: 동시 신호음 울림'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Simultaneous ringing
ms:assetid: df02f919-4d50-4832-9300-6c51f8b4fc56
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994079(v=OCS.15)
ms:contentKeyID: 51803990
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4e3104da5e7d351bda26698087e97106cafbdff4
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037508"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="simultaneous-ringing-in-lync-server-2013"></a>Lync Server 2013의 동시 신호음

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-03-09_

전화 건 사람이 동시에 벨 울림을 사용 하는 경우 위치 기반 라우팅은 발신자의 위치와 호출한 파티의 끝점을 분석 하 여 통화를 라우팅해야 하는지 여부를 결정 합니다.

다음 표에서는 동시 울림을 사용 하 여 구성 된 사용자와, 동시 신호음 대상이 동일한 네트워크 사이트의 사용자 이거나, 다른 네트워크 사이트에 있거나, 알 수 없는 네트워크 사이트에 있습니다.


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
<th>피호출자와 동일한 네트워크 사이트에 위치</th>
<th>수신자가 아닌 다른 네트워크 사이트에 있음</th>
<th>알 수 없는 네트워크 사이트에 있거나 위치 기반 라우팅을 사용 하도록 설정 되지 않음</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync 사용자</p></td>
<td><p>동시 벨 울림 허용</p></td>
<td><p>동시 벨 울림 허용 안 됨</p></td>
<td><p>동시 벨 울림 허용 안 됨</p></td>
</tr>
</tbody>
</table>

  
다음 표에서는 동일한 네트워크 사이트, 다른 네트워크 사이트 또는 알 수 없는 네트워크 사이트에서 Lync 사용자 (예: Lync 발신자) 로부터의 통화를 보여 줍니다. 수신자는 PSTN 끝점 (즉, 휴대폰)을 동시 링 대상으로 구성 합니다. 이 시나리오에서 위치 기반 라우팅은 호출을 수신자의 동시 링 대상 (예: 휴대폰)으로 라우팅해야 하는지 결정 합니다.


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
<th>피호출자와 동일한 네트워크 사이트에 위치</th>
<th>수신자가 아닌 다른 네트워크 사이트에 있음</th>
<th>알 수 없는 네트워크 사이트에 있거나 위치 기반 라우팅을 사용 하도록 설정 되지 않음</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>PSTN 끝점</p></td>
<td><p>발신자의 사이트 음성 라우팅 정책을 통해 허용 되는 동시 벨 울림</p></td>
<td><p>발신자의 사이트 음성 라우팅 정책을 통해 허용 되는 동시 벨 울림</p></td>
<td><p>발신자의 음성 정책을 통해 허용 되는 동시 링이 위치 기반 라우팅을 사용 하도록 설정 되지 않은 트렁크</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013의 위치 기반 라우팅에 대 한 시나리오](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

