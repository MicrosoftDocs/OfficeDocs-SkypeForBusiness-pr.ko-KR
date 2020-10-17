---
title: 통화 정보 기록 및 경험 수준 설정 구성
description: 통화 정보 기록 및 체감 품질 설정 구성
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring call detail recording and Quality of Experience settings
ms:assetid: 009a0499-4f8c-450d-9c72-a565a08e9f7a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204621(v=OCS.15)
ms:contentKeyID: 48183223
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: be0238701f561e6694786faec7fc914dcc9cda40
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567174"
---
# <a name="configuring-call-detail-recording-and-quality-of-experience-settings-in-lync-server-2013"></a>Lync Server 2013에서 통화 정보 기록 및 경험 수준 설정 구성

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-17_

모니터링 저장소를 프런트 엔드 풀과 연결 하 고 나면 모니터링 저장소를 설정한 다음 설치 및 구성 SQL Server Reporting Services 및 모니터링 보고서 Lync Server 관리 셸을 사용 하 여 CDR (통화 정보 기록) 및 QoE (경력 품질) 모니터링을 관리할 수 있습니다. Lync Server 관리 셸 cmdlet을 사용 하면 특정 사이트 또는 전체 Lync Server 배포에 대해 CDR 및/또는 QoE 모니터링을 설정 하 고 사용 하지 않도록 설정할 수 있습니다. 다음과 같이 간단한 명령을 사용 하 여이 작업을 수행할 수 있습니다.

    Set-CsQoEConfiguration -Identity "global" -EnableQoE $False

Microsoft Lync Server 2013을 설치할 때 CDR 및 QoE에 대해 미리 정의 된 전역 구성 설정 모음도 설치 됩니다. 통화 정보 기록에서 사용하는 보다 일반적으로 사용되는 설정 중 일부의 기본값이 아래 표에 나와 있습니다.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>속성</th>
<th>설명</th>
<th>기본값</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>EnableCDR</p></td>
<td><p>CDR을 사용할 수 있는지 여부를 나타냅니다. True인 경우 모든 CDR 레코드가 수집되어 모니터링 데이터베이스에 기록됩니다.</p></td>
<td><p>True</p></td>
</tr>
<tr class="even">
<td><p>은 enablepurging 설정한</p></td>
<td><p>CDR 레코드를 데이터베이스에서 주기적으로 삭제할지 여부를 나타냅니다. True이면 KeepCallDetailForDays(CDR 레코드) 및 KeepErrorReportForDays(CDR 오류) 속성에 지정된 기간이 지난 후 기록이 삭제됩니다. False인 경우에는 CDR 레코드가 무기한 유지됩니다.</p></td>
<td><p>True</p></td>
</tr>
<tr class="odd">
<td><p>Keepcalldetailfordays는</p></td>
<td><p>CDR 레코드를 데이터베이스에 유지할 일 수를 나타냅니다. 지정된 일 수보다 오래된 레코드는 모두 자동으로 삭제됩니다. 그러나 이 작업은 삭제가 사용하도록 설정된 경우에만 수행됩니다.</p>
<p>KeepCallDetailForDays는 1에서 2562일(약 7년) 사이의 정수 값으로 설정할 수 있습니다.</p></td>
<td><p>60일</p></td>
</tr>
<tr class="even">
<td><p>KeepErrorReportForDays</p></td>
<td><p>CDR 오류 보고서가 보관 되는 일 수를 나타냅니다. 지정한 일 수 보다 오래 된 보고서는 자동으로 삭제 됩니다. CDR 오류 보고서는 Microsoft Lync 2013와 같은 클라이언트 응용 프로그램에서 업로드 하는 진단 보고서입니다.</p>
<p>이 속성은 1에서 2562일 사이의 정수 값으로 설정할 수 있습니다.</p></td>
<td><p>60일</p></td>
</tr>
</tbody>
</table>


마찬가지로, 선택한 QoE 설정에 대한 기본값이 아래 표에 나와 있습니다.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>속성</th>
<th>설명</th>
<th>기본값</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>EnableQoE</p></td>
<td><p>QoE 모니터링을 사용할 수 있는지 여부를 나타냅니다. True인 경우 모든 QoE 레코드가 수집되어 모니터링 데이터베이스에 기록됩니다.</p></td>
<td><p>True</p></td>
</tr>
<tr class="even">
<td><p>은 enablepurging 설정한</p></td>
<td><p>QoE 레코드를 데이터베이스에서 주기적으로 삭제할지 여부를 나타냅니다. True이면 KeepQoEDataForDays 속성에 지정된 기간이 지난 후 레코드가 삭제됩니다. False인 경우 QoE 레코드는 무기한 유지됩니다.</p></td>
<td><p>True</p></td>
</tr>
<tr class="odd">
<td><p>KeepQoEDataForDays</p></td>
<td><p>QoE 레코드를 데이터베이스에 유지할 일 수를 나타냅니다. 지정된 일 수보다 오래된 레코드는 모두 자동으로 삭제됩니다. 그러나 이 작업은 삭제가 사용하도록 설정된 경우에만 수행됩니다.</p>
<p>KeepCallDetailForDays는 1에서 2562일 사이의 정수 값으로 설정할 수 있습니다.</p></td>
<td><p>60일</p></td>
</tr>
</tbody>
</table>


이러한 전역 설정을 수정해야 하는 경우 Set-CsCdrConfiguration 및 Set-CsQoEConfiguration cmdlet을 사용하면 됩니다. 예를 들어 다음 명령(Lync Server 관리 셸 내에서 실행)은 전역 범위에서 CDR 모니터링을 사용하지 않도록 설정합니다. 이를 위해 EnableCDR 속성을 False($False)로 설정합니다.

    Set-CsCdrConfiguration -Identity "global" -EnableCDR $False

모니터링을 사용하지 않도록 설정해도 프런트 엔드 풀에서 모니터링 저장소의 연결이 해제되지 않으며, 백 엔드 모니터링 데이터베이스가 제거되거나 다른 방식으로 영향을 받지도 않습니다. Lync Server 관리 셸을 사용 하 여 CDR 또는 QoE 모니터링과 함께 사용 하지 않도록 설정 하는 경우에는 Lync Server가 모니터링 데이터를 수집 하 고 보관 하지 못하도록 일시적으로 중지 됩니다. 이 경우 CDR 데이터 수집 및 보관을 다시 시작하려면 EnableCDR 속성을 다시 True($True)로 설정하기만 하면 됩니다.

    Set-CsCdrConfiguration -Identity "global" -EnableCDR $True

마찬가지로, 다음 명령은 전역 범위에서 QoE 레코드 삭제를 사용하지 않도록 설정합니다.

    Set-CsQoEConfiguration -Identity "global" -EnablePurging $False

이처럼 전역 설정을 사용할 수 있을 뿐 아니라, CDR 및 QoE 구성 설정을 사이트 범위에도 할당할 수 있습니다. 이렇게 하면 모니터링을 보다 유동적으로 관리할 수 있습니다. 예를 들어 관리자는 Redmond 사이트에 대해서는 CDR 모니터링을 사용하도록 설정하고 Dublin 사이트에 대해서는 CDR 모니터링을 사용하지 않도록 설정할 수 있습니다. 사이트 범위에서 새 CDR 구성 설정을 만들려면 다음과 같은 명령을 사용합니다.

    New-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False

사이트 범위에서 구성된 설정이 전역 범위에서 구성된 설정보다 우선합니다. 예를 들어 Redmond 사이트에 대해 CDR 모니터링이 전역 범위에서는 사용하도록 설정되고 사이트 범위에서는 사용하지 않도록 설정되어 있다고 가정해 보겠습니다. 이는 Redmond 사이트에 있는 사용자의 통화 정보 기록 정보가 보관되지 않음을 의미합니다. 그러나 다른 사이트에 있는 사용자(Redmond 사이트 설정 대신 전역 설정에 의해 관리되는 사용자)의 통화 정보 기록 정보는 보관됩니다.

다음과 같은 명령을 사용하면 사이트 범위에서 새 QoE 구성 설정을 만들 수 있습니다.

    New-CsQoEConfiguration -Identity "site:Redmond" -KeepQoEDataForDays 15

자세한 내용을 보려면 Lync Server 관리 셸 내에서 다음 명령을 입력 합니다.

    Get-Help New-CsCdrConfiguration | more
    Get-Help Set-CsCdrConfiguration | more
    Get-Help New-CsQoEConfiguration | more
    Get-Help Set-CsQoEConfiguration | more

</div>

<span> </span>

</div>

</div>

</div>

