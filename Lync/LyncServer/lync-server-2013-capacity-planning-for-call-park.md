---
title: 'Lync Server 2013: 통화 대기에 대한 용량 계획'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Capacity planning for Call Park
ms:assetid: 75520310-760a-4b1b-bcc1-4d724d13f87a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg416493(v=OCS.15)
ms:contentKeyID: 48184529
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5fe55e09c67e62676202def9e3def3454d7cbd33
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982352"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="capacity-planning-for-call-park-in-lync-server-2013"></a>Lync Server 2013의 통화 대기에 대한 용량 계획

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-09-13_

<div id="sectionSection0" class="section">

다음 표에서는 용량 계획 요구 사항의 기준으로 사용할 수 있는 통화 공원 사용자 모델에 대해 설명 합니다.

<div>


> [!IMPORTANT]  
> 재해 복구 용량 계획을 위해 쌍으로 연결 된 풀의 각 풀은 두 풀의 통화 파킹 서비스에 대 한 작업 부하를 처리할 수 있어야 한다는 점에 유의 하세요.



</div>

### <a name="call-park-user-model"></a>통화 공원 사용자 모델

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>미터</th>
<th>프런트 엔드 풀 단위 (프런트 엔드 서버 8 개)</th>
<th>스탠더드 에디션 서버 당</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>공원 요금</p></td>
<td><p>분당 8</p></td>
<td><p>분당 1</p></td>
</tr>
<tr class="even">
<td><p>파킹 통화 속도 검색</p></td>
<td><p>분당 8</p></td>
<td><p>분당 1</p></td>
</tr>
<tr class="odd">
<td><p>평균 공원 기간</p></td>
<td><p>60 초</p></td>
<td><p>60 초</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

