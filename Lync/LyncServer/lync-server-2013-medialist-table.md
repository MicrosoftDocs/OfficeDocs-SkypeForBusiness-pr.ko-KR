---
title: 'Lync Server 2013: MediaList 테이블'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: MediaList table
ms:assetid: 1f440590-c1bc-483e-b7bc-6cc763847768
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398279(v=OCS.15)
ms:contentKeyID: 48183579
ms.date: 07/12/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7a22ef9b9e0ef429fcac96a7f7d5c87093f79a02
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48505725"
---
# <a name="medialist-table-in-lync-server-2013"></a>Lync Server 2013의 MediaList 테이블

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2016-07-12_

MediaList 테이블은 다양한 미디어 유형 목록이 저장된 정적 테이블입니다.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>열</th>
<th>데이터 형식</th>
<th>키/인덱스</th>
<th>세부 정보</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>MediaId</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Primary</p></td>
<td><p>값: 1-7</p></td>
</tr>
<tr class="even">
<td><p><strong>미디어</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td></td>
<td><p>MediaID 및 Media 값의 정적 매핑:</p>
<ul>
<li><p>1-IM</p></li>
<li><p>2 -- 파일 전송</p></li>
<li><p>3 -- 원격 지원</p></li>
<li><p>4 -- 응용 프로그램 공유</p></li>
<li><p>5-오디오</p></li>
<li><p>6-비디오</p></li>
<li><p>7 -- 응용 프로그램 초대</p></li>
</ul></td>
</tr>
</tbody>
</table>


LcsCDR에서 MediaTypes의 값에 대 한 형식 형식을 확인 하려는 경우 다음 Join 조각을 사용 해야 합니다.

    LEFT JOIN on Media.MediaId = MediaList.MediaId

</div>

<span> </span>

</div>

</div>

</div>

