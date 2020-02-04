---
title: 'Lync Server 2013: PurgeSettings 테이블'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: PurgeSettings table
ms:assetid: 9ff2c8fc-4ae8-4f22-96a8-1f4d5eecbf2d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205121(v=OCS.15)
ms:contentKeyID: 48184932
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 56ea95d0ba54a34eaa315ff345efb45cd563700c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747028"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="purgesettings-table-in-lync-server-2013"></a>Lync Server 2013의 PurgeSettings 테이블

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-09-28_

PurgeSettings 테이블에는 CDR 데이터베이스에서 오래 된 통화 정보 레코드가 자동으로 삭제 되는지 여부를 지정 하는 정보가 포함 되어 있습니다. 다음 명령을 실행 하 여 Microsoft Lync Server 2013 관리 셸에서에서 제거 관련 정보를 얻을 수도 있습니다.

    Get-CsCdrConfiguration

관리자는 PurgeSettings 테이블을 읽기 전용으로 처리 해야 합니다. 통화 정보 제거 설정의 변경 사항은 [새로운-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration) 또는 [CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration) cmdlet을 사용해 서만 이루어져야 합니다.

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
<th>열</th>
<th>데이터 형식</th>
<th>키/인덱스</th>
<th>세부적인</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>I</strong></p></td>
<td><p>int</p></td>
<td><p>주요한</p></td>
<td><p>CDR 제거 설정 컬렉션의 고유 식별자입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>EnablePurge</strong></p></td>
<td><p>다소</p></td>
<td></td>
<td><p>True (1)로 설정 되 면 Microsoft Lync Server 2013이 CDR 데이터베이스에서 오래 된 레코드를 주기적으로 제거 합니다. 제거는 PurgeHour 설정으로 지정 된 상투메 매일 수행 됩니다. False로 설정 된 경우 레코드가 데이터베이스에서 자동으로 제거 되지 않습니다. 기본값은 True입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>KeepCallDetailForDays</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>데이터베이스에서 제거 되는 CDR 레코드의 보존 기간 (일)을 지정 합니다. 제거를 사용 하는 경우이 값 보다 오래 된 CDR 레코드가 데이터베이스에서 제거 됩니다. 기본값은 60 일입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>KeepErrorReportForDays</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>데이터베이스에서 삭제 되는 오류 보고서 레코드의 기간 (일)을 지정 합니다. 제거를 사용 하는 경우이 값 보다 오래 된 오류 보고서 레코드가 데이터베이스에서 제거 됩니다. 기본값은 60 일입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>PurgeHour</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>데이터베이스 제거를 수행할 현지 시간을 지정 합니다. 시간은 24시간제를 사용하여 지정합니다. 일의 시간만 지정할 수 있음: 값 10 (10:00 AM)은 허용 되지만 10.5의 10:30의 값 (10:30 AM을 나타냄)은 허용 되지 않습니다. 기본값은 2(오전 2:00)입니다.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

