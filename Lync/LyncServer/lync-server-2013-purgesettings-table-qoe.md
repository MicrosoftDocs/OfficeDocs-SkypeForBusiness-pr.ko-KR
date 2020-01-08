---
title: 'Lync Server 2013: PurgeSettings table (체감 품질)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: PurgeSettings table (QoE)
ms:assetid: 31b85d1c-3f32-4f67-94bf-9389cdd282c5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204788(v=OCS.15)
ms:contentKeyID: 48183777
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a3cc227d11ee723acb5a49c50d5b8d4d7e819062
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983690"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="purgesettings-table-qoe-in-lync-server-2013"></a>Lync Server 2013의 PurgeSettings 테이블 (체감 품질)

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-02_

PurgeSettings 테이블에는 체감 품질 데이터베이스에서 오래 된 경력 품질 레코드가 자동으로 삭제 되는지 여부를 지정 하는 정보가 포함 되어 있습니다. 다음 명령을 실행 하 여 Microsoft Lync Server 2013 관리 셸에서에서 제거 관련 정보를 얻을 수도 있습니다.

    Get-CsQoEConfiguration

이 표는 Microsoft Lync Server 2013에서 도입 되었습니다.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>열</strong></th>
<th><strong>데이터 형식</strong></th>
<th><strong>키/인덱스</strong></th>
<th><strong>세부적인</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>I</strong></p></td>
<td><p>int</p></td>
<td><p>주요한</p></td>
<td><p>체감 품질 purge 설정 컬렉션의 고유 식별자입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>EnablePurge</strong></p></td>
<td><p>다소</p></td>
<td></td>
<td><p>True (1)로 설정 하면 Microsoft Lync Server 2013 체감 품질 데이터베이스에서 오래 된 레코드가 주기적으로 제거 됩니다. 제거는 PurgeHour 설정으로 지정 된 상투메 매일 수행 됩니다. False로 설정 된 경우 레코드가 데이터베이스에서 자동으로 제거 되지 않습니다. 기본값은 True입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>KeepQoEDataForDays</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>데이터베이스에서 삭제 되는 체감 품질 레코드의 기간 (일)을 지정 합니다. 제거를 사용 하는 경우이 값 보다 오래 된 체감 품질 레코드는 데이터베이스에서 제거 됩니다. 기본값은 60 일입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>PurgeHour</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>데이터베이스 제거를 수행할 현지 시간을 지정 합니다. 시간은 24시간제를 사용하여 지정합니다. 일의 시간만 지정할 수 있음: 값 10 (10:00 AM)은 허용 되지만 10.5의 10:30의 값 (10:30 AM을 나타냄)은 허용 되지 않습니다. 기본값은 1 (1:00 AM)입니다. 데이터베이스 제거를 수행할 현지 시간을 지정 합니다. 시간은 24시간제를 사용하여 지정합니다. 일의 시간만 지정할 수 있음: 값 10 (10:00 AM)은 허용 되지만 10.5의 10:30의 값 (10:30 AM을 나타냄)은 허용 되지 않습니다. 기본값은 1 (1:00 AM)입니다.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

