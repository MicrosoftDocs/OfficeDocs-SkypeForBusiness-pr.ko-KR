---
title: 'Lync Server 2013: 발신 전화'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Outgoing calls
ms:assetid: 885ffe6f-cd51-4f21-8d4f-a1ff8d818858
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994049(v=OCS.15)
ms:contentKeyID: 51803960
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e2ccd095cfe27f173ff0fe7ac0dac92ca51a7c1d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983953"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="outgoing-calls-in-lync-server-2013"></a>Lync Server 2013의 발신 전화

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-03-09_

위치 기반 라우팅에 대해 사용 하도록 설정 된 사용자의 아웃 바운드 통화 라우팅은 사용자 끝점의 네트워크 위치에 따라 달라 집니다. 다음 표에서는 위치 기반 라우팅이 호출자 끝점의 위치에 따라 아웃 바운드 호출의 라우팅에 영향을 주는 방식을 보여 줍니다.

### <a name="caller-placing-an-outbound-call-to-the-pstn"></a>발신자가 PSTN으로 발신 전화 걸기

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>위치 기반 라우팅에 사용 되는 네트워크 사이트에 위치한 사용자 끝점</th>
<th>알 수 없는 네트워크 사이트에 있거나 위치 기반 라우팅에 대해 사용 하도록 설정 되지 않은 사용자 끝점</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>아웃 바운드 통화 승인</p></td>
<td><p>통화는 사용자의 음성 정책에 따라 승인 됩니다.</p></td>
<td><p>통화는 사용자의 음성 정책에 따라 승인 됩니다.</p></td>
</tr>
<tr class="even">
<td><p>아웃 바운드 통화 라우팅</p></td>
<td><p>네트워크 사이트의 음성 라우팅 정책에 따라 통화가 전달 됩니다.</p></td>
<td><p>통화는 사용자의 음성 정책에 따라 라우팅 되며 위치 기반 라우팅에 대 한 trunks 사용 하지 않는 경우에만 가능 합니다 (사용 가능한 경우).</p></td>
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

