---
title: 'Lync Server 2013: 발신 전화'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Outgoing calls
ms:assetid: 885ffe6f-cd51-4f21-8d4f-a1ff8d818858
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994049(v=OCS.15)
ms:contentKeyID: 51803960
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6a77ddf0757cd463bb8f1b95dbecfe90fd1086c9
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48524405"
---
# <a name="outgoing-calls-in-lync-server-2013"></a>Lync Server 2013의 발신 전화

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-03-09_

Location-Based 라우팅에서 사용 하도록 설정 된 사용자의 아웃 바운드 호출 라우팅은 사용자 끝점의 네트워크 위치에 따라 영향을 받습니다. 다음 표에서는 Location-Based 라우팅이 발신자의 끝점 위치에 따라 아웃 바운드 호출의 라우팅에 미치는 영향을 보여 줍니다.

### <a name="caller-placing-an-outbound-call-to-the-pstn"></a>발신자가 PSTN에 대 한 아웃 바운드 호출을 합니다.

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>Location-Based 라우팅을 위해 사용 하도록 설정 된 네트워크 사이트에 있는 사용자 끝점</th>
<th>사용자 끝점이 알 수 없는 네트워크 사이트에 있거나 Location-Based 라우팅을 위해 사용할 수 없습니다.</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>아웃 바운드 호출 권한 부여</p></td>
<td><p>사용자의 음성 정책에 따라 통화가 승인 됨</p></td>
<td><p>사용자의 음성 정책에 따라 통화가 승인 됨</p></td>
</tr>
<tr class="even">
<td><p>아웃 바운드 통화 라우팅</p></td>
<td><p>통화가 네트워크 사이트의 음성 라우팅 정책에 따라 라우팅됩니다.</p></td>
<td><p>전화가 사용자의 음성 정책에 따라 Location-Based 라우팅에 사용 하도록 설정 되지 않은 트렁크를 통해서만 라우팅됩니다 (가능한 경우).</p></td>
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

