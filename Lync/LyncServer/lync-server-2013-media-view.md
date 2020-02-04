---
title: 'Lync Server 2013: 미디어 보기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Media view
ms:assetid: 1a7b2e59-082e-4188-98ae-48ae9bd3494a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687981(v=OCS.15)
ms:contentKeyID: 49733570
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6ad833bc84d488221d46822686077cfde2cda0ff
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765096"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="media-view-in-lync-server-2013"></a>Lync Server 2013의 미디어 보기

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-01_

미디어 보기는 피어 투 피어 세션에 사용 되는 미디어 형식에 대 한 정보를 저장 합니다. 하나 이상의 미디어 유형이 사용 되는 경우 한 세션은 테이블의 여러 레코드로 표시 됩니다. 이 보기는 Microsoft Lync Server 2013에서 도입 되었습니다.

<div>


> [!NOTE]  
> 미디어 보기는 세션의 미디어 기간을 계산 하는 데 사용해 서는 안 됩니다. 이 보기에는 세션의 미디어 교환에 대 한 신호 세부 정보가 포함 됩니다. 미디어 교환은 초대 요청에 의해 수행 되며 StartTime은 초대를 보낸 시간을 나타냅니다. 세션이 허용 된 후에만 미디어가 시작 되므로 초대 시간이 반드시 미디어 시작 시간을 의미 하는 것은 아닙니다.



</div>

미디어 보기에는 아래 나열 된 것 외에도 [Lync Server 2013의 Sessiondetails 보기](lync-server-2013-sessiondetails-view.md) 에 모든 열이 포함 되어 있습니다.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>열</th>
<th>데이터 형식</th>
<th>세부적인</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>미디어</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>미디어 유형입니다. 자세한 내용은 <a href="lync-server-2013-medialist-table.md">Lync Server 2013의 Medialist 테이블</a> 을 참조 하세요.</p></td>
</tr>
<tr class="even">
<td><p><strong>MediaStartTime</strong></p></td>
<td><p>dmtf</p></td>
<td><p>미디어 요청이 전송 된 시간입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediaEndTime</strong></p></td>
<td><p>dmtf</p></td>
<td><p>세션 종료 시간입니다.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

