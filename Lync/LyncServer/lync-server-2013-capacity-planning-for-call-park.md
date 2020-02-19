---
title: 'Lync Server 2013: 통화 대기에 대 한 용량 계획'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Capacity planning for Call Park
ms:assetid: 75520310-760a-4b1b-bcc1-4d724d13f87a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg416493(v=OCS.15)
ms:contentKeyID: 48184529
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4e3bdb6899ae92d8f4d5561bd81266922284d950
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137217"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="capacity-planning-for-call-park-in-lync-server-2013"></a>Lync Server 2013의 통화 대기에 대 한 용량 계획

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-09-13_

<div id="sectionSection0" class="section">

다음 표에서는 용량 계획 요구 사항의 기반으로 사용할 수 있는 통화 대기 사용자 모델에 대해 설명 합니다.

<div>


> [!IMPORTANT]  
> 재해 복구 용량 계획을 위해 연결 된 풀의 각 풀은 두 풀에서 통화 대기 서비스의 작업을 처리할 수 있어야 합니다.



</div>

### <a name="call-park-user-model"></a>통화 대기 사용자 모델

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>192.168.1.0</th>
<th>프런트 엔드 풀 당 (8 개의 프런트 엔드 서버 포함)</th>
<th>Standard Edition Server별</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>대기 속도</p></td>
<td><p>분당 8개</p></td>
<td><p>분당 1개</p></td>
</tr>
<tr class="even">
<td><p>대기 중인 통화 재개 속도</p></td>
<td><p>분당 8개</p></td>
<td><p>분당 1개</p></td>
</tr>
<tr class="odd">
<td><p>평균 대기 시간</p></td>
<td><p>60초</p></td>
<td><p>60초</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

