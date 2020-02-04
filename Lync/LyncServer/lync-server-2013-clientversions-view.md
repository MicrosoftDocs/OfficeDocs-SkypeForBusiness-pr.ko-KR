---
title: 'Lync Server 2013: ClientVersions 보기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ClientVersions view
ms:assetid: caf7678f-83a0-46c8-83cc-fee4c3991f52
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721891(v=OCS.15)
ms:contentKeyID: 49733825
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8fd25da49e8a3b6ad7838ff27a4472e711b97421
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756412"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="clientversions-view-in-lync-server-2013"></a>Lync Server 2013의 ClientVersions 보기

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-01_

ClientVersions view는 다양 한 클라이언트 유형 및 데이터베이스에 기록 된 세션에 참가 한 버전에 대 한 정보를 저장 합니다. 뷰의 각 레코드는 하나의 클라이언트 버전을 나타냅니다. 이 보기는 Microsoft Lync Server 2013에서 도입 되었습니다.

<div>


> [!NOTE]  
> 특정 열에 여러 레코드가 있을 수 있습니다.



</div>


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
<td><p><strong>#</strong></p></td>
<td><p>int</p></td>
<td><p>이 클라이언트 유형 및 버전을 식별 하는 고유 번호입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>버전</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>사용자 에이전트를 나타냅니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ClientType</strong></p></td>
<td><p>int</p></td>
<td><p>클라이언트의 유형입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>ClientCategory</strong></p></td>
<td><p>nvarchar (64)</p></td>
<td><p>클라이언트가 속한 범주 예를 들어 클라이언트 Conferencing_Attendant_1 .0는 ClientCategory CA에 속합니다.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

