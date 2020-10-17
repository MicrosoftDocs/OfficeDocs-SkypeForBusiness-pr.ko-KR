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
ms.openlocfilehash: d0e6cd8658278a8d7798153698355f5a73f2952b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48516155"
---
# <a name="media-view-in-lync-server-2013"></a>Lync Server 2013의 미디어 보기

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-01_

Media 보기에는 피어 투 피어 세션에 사용되는 단일 미디어 유형에 대한 정보가 저장됩니다. 둘 이상의 미디어 유형이 사용된 경우 하나의 세션이 테이블에 여러 레코드로 표시됩니다. 이 보기는 Microsoft Lync Server 2013에 도입 되었습니다.

<div>


> [!NOTE]  
> Media 보기를 사용하여 세션의 미디어 기간을 계산해서는 안 됩니다. 이 보기에는 세션에 포함된 미디어 교환의 신호 세부 정보가 포함됩니다. 미디어 교환은 INVITE 요청에 의해 수행되며 StartTime은 INVITE가 전송된 시간을 나타냅니다. 미디어는 세션이 수락된 후에만 시작되므로 초대 시간이 반드시 미디어 시작 시간인 것은 아닙니다.



</div>

미디어 보기에는 아래 나열 된 것 외에도 [Lync Server 2013의 Sessiondetails view](lync-server-2013-sessiondetails-view.md) 의 모든 열이 포함 되어 있습니다.


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
<th>세부 정보</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>미디어</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>미디어 유형입니다. 자세한 내용은 <a href="lync-server-2013-medialist-table.md">Lync Server 2013에서 Medialist 테이블</a> 을 참조 하십시오.</p></td>
</tr>
<tr class="even">
<td><p><strong>MediaStartTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>미디어 요청을 보낸 시간입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediaEndTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>세션 종료 시간입니다.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

