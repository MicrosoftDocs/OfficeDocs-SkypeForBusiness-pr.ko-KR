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
ms.openlocfilehash: 7cbe8543f1d26f42186654d2988258e796d7eebb
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42183402"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="purgesettings-table-in-lync-server-2013"></a>Lync Server 2013의 PurgeSettings 테이블

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-09-28_

PurgeSettings 테이블에는 오래된 통화 정보 기록을 CDR 데이터베이스에서 자동으로 삭제할지 여부 및 시기를 지정하는 정보가 포함됩니다. 다음 명령을 실행 하 여 Microsoft Lync Server 2013 관리 셸 내 에서도 제거 관련 정보를 확인할 수 있습니다.

    Get-CsCdrConfiguration

관리자는 PurgeSettings 테이블을 읽기 전용으로 취급 해야 합니다. 통화 정보 제거 설정에 대 한 변경 내용은 [get-cscdrconfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration) 또는 [get-cscdrconfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration) cmdlet을 사용 해야 합니다.

이 표는 Microsoft Lync Server 2013에 도입 되었습니다.


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
<td><p><strong>Id</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p>CDR 삭제 설정 컬렉션에 대한 고유 식별자입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>EnablePurge</strong></p></td>
<td><p>비트만</p></td>
<td></td>
<td><p>True (1)로 설정 하면 Microsoft Lync Server 2013에서는 CDR 데이터베이스에서 오래 된 레코드를 주기적으로 제거 합니다. 삭제는 매일 PurgeHour 설정으로 지정된 시간에 수행됩니다. False(0)로 설정하면 레코드가 데이터베이스에서 자동으로 삭제되지 않습니다. 기본값은 True입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Keepcalldetailfordays는</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>데이터베이스에서 삭제할 CDR 레코드의 기간(일)을 지정합니다. 삭제를 사용하도록 설정한 경우 이 값보다 오래된 CDR 레코드가 데이터베이스에서 삭제됩니다. 기본값은 60일입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>KeepErrorReportForDays</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>데이터베이스에서 삭제할 오류 보고서 레코드의 기간(일)을 지정합니다. 삭제를 사용하도록 설정한 경우 이 값보다 오래된 오류 보고서 레코드가 데이터베이스에서 삭제됩니다. 기본값은 60일입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>PurgeHour</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>데이터베이스 삭제가 수행되는 현지 시간을 지정합니다. 시간은 24시간제를 사용하여 지정합니다. 0은 자정(오전 12:00)을 나타내고 23은 오후 11:00를 나타냅니다. 시간만 지정할 수 있습니다. 즉, 값으로 10(오전 10:00)은 사용할 수는 있지만, 10:30 또는 10.5(오전 10:30)는 사용할 수 없습니다. 기본값은 2(오전 2:00)입니다.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

