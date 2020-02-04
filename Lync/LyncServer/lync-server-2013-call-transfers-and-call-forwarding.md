---
title: 'Lync Server 2013: 통화 전송 및 착신 전환'
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
ms.openlocfilehash: 512deaf8af03f112e35443c25e46685c42a2f2e6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742958"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-transfers-and-call-forwarding-in-lync-server-2013"></a>Lync Server 2013의 통화 전송 및 착신 전환

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-03-09_

PSTN 끝점을 사용 하는 경우 위치 기반 라우팅은 calle의 끝점 위치와 호출이 전송 되거나 전달 되는 끝점 (즉, 전송/전달 대상)을 분석 합니다. 위치 기반 라우팅은 두 끝점의 위치에 따라 통화를 전송 하거나 전달 해야 하는지 여부를 결정 합니다.

다음 표에서는 PSTN 끝점을 사용한 통화에서 Lync 사용자의 시나리오를 보여 주고, Lync 사용자는 다른 Lync 사용자에 게 통화를 전송 합니다. Transferee 종점의 네트워크 사이트 위치에 따라 위치 기반 라우팅은 착신 전환 또는 전달 라우팅에 영향을 줍니다.

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
<th>통화 이전/전달을 시작 하는 사용자</th>
<th>사용자가 착신 전환 또는 전달을 시작 하는 것과 동일한 네트워크 사이트에 대상 끝점이 있습니다.</th>
<th>사용자가 착신 전환 또는 전달을 시작할 때 대상 끝점이 다른 네트워크 사이트에 있습니다.</th>
<th>대상 끝점이 알 수 없는 네트워크 사이트에 있거나 위치 기반 라우팅에 대해 네트워크 사이트를 사용 하도록 설정 되지 않았습니다.</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync 사용자</p></td>
<td><p>착신 통화 또는 전송이 허용 됨</p></td>
<td><p>착신 통화 또는 전송이 허용 되지 않음</p></td>
<td><p>착신 통화 또는 전송이 허용 되지 않음</p></td>
</tr>
</tbody>
</table>

  

예: PSTN 끝점으로 전화를 걸고 있는 Lync 사용자는 같은 네트워크 사이트에 있는 다른 Lync 사용자에 게 통화를 전송 합니다. 이 경우에는 통화 전송이 허용 됩니다.

다음 표에서는 다른 Lync 사용자와의 통화에서 Lync 사용자의 시나리오를 보여 주고, 사용자 중 하나가 PSTN 끝점으로 통화를 전송 합니다. 통화가 전송 되는 사용자의 위치에 따라이 표에서는 위치 기반 라우팅이 통화에 미치는 영향에 대해 자세히 설명 합니다.

### <a name="call-transfer-or-forward-to-pstn-endpoint"></a>PSTN 끝점으로 착신 전환 또는 전달

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
<th>동일한 네트워크 사이트의 Lync 사용자</th>
<th>다른 네트워크 사이트의 Lync 사용자</th>
<th>알 수 없는 네트워크 사이트 또는 네트워크 사이트의 Lync 사용자 하나 또는 둘 다가 위치 기반 라우팅에 대해 사용 하도록 설정 되지 않음</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>PSTN 끝점</p></td>
<td><p>전송 된 사용자의 사이트 음성 라우팅 정책에 따라 착신 전환 또는 전송 허용</p></td>
<td><p>전송 된 사용자의 사이트 음성 라우팅 정책에 따라 착신 전환 또는 전송 허용</p></td>
<td><p>위치 기반 라우팅에 대해 trunks를 통해서만 전송 된 사용자의 음성 정책에 따라 착신 전환 또는 전송이 허용 됨</p></td>
</tr>
</tbody>
</table>

  
예를 들어 동일한 네트워크 사이트에 있는 다른 Lync 사용자와의 통화에서 Lync 사용자는 통화를 PSTN 끝점으로 전송 하 고 통화 전송은 허용 됩니다.

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013의 위치 기반 라우팅 시나리오](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

