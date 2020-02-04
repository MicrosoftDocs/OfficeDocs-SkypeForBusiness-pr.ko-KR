---
title: 통화 정보 기록 및 체감 품질 설정 구성
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
ms.openlocfilehash: 504c2221e9f8a3ef32e2cebbb792f5e03aef15c5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756342"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-call-detail-recording-and-quality-of-experience-settings-in-lync-server-2013"></a>Lync Server 2013에서 통화 정보 기록 및 환경 품질 설정 구성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-17_

프런트 엔드 풀과 모니터링 저장소를 연결 하 고 모니터링 저장소를 설정한 다음 설치 및 구성 SQL Server Reporting Services 및 모니터링 보고서를 사용 하 여, CDR (통화 정보 기록) 및 경력 (체감 품질)을 관리할 수 있습니다. Lync Server Management Shell을 사용 하 여 모니터링 Lync Server 관리 셸 cmdlet을 사용 하면 특정 사이트 또는 전체 Lync Server 배포에 대해 CDR 및/또는 체감 품질 모니터링을 활성화 및 비활성화할 수 있습니다. 다음과 같이 간단한 명령으로 수행할 수 있습니다.

    Set-CsQoEConfiguration -Identity "global" -EnableQoE $False

Microsoft Lync Server 2013을 설치할 때 CDR 및 체감 품질에 대해 미리 정의 된 전역 구성 설정 모음도 설치 됩니다. 통화 정보 기록에 사용 되는 일반적으로 사용 되는 일부 설정에 대 한 기본값은 다음 표에 나와 있습니다.


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
<td><p>CDR를 사용할 수 있는지 여부를 나타냅니다. True 인 경우 모든 CDR 레코드가 수집 되 고 모니터링 데이터베이스에 기록 됩니다.</p></td>
<td><p>False</p></td>
</tr>
<tr class="even">
<td><p>EnablePurging</p></td>
<td><p>CDR 레코드를 데이터베이스에서 정기적으로 삭제할지 여부를 나타냅니다. True 인 경우 KeepCallDetailForDays 속성 (CDR 레코드) 및 KeepErrorReportForDays (CDR 오류의 경우)에서 지정한 기간 후 레코드가 삭제 됩니다. False 인 경우, CDR 레코드가 무기한 유지 됩니다.</p></td>
<td><p>False</p></td>
</tr>
<tr class="odd">
<td><p>KeepCallDetailForDays</p></td>
<td><p>CDR 레코드가 데이터베이스에 유지 되는 일 수를 나타냅니다. 지정 된 일 수 보다 오래 된 레코드는 자동으로 삭제 됩니다. 그러나이는 제거가 활성화 된 경우에만 발생 합니다.</p>
<p>KeepCallDetailForDays는 1 ~ 2562 일 (약 7 년) 사이의 정수 값으로 설정할 수 있습니다.</p></td>
<td><p>60일</p></td>
</tr>
<tr class="even">
<td><p>KeepErrorReportForDays</p></td>
<td><p>CDR 오류 보고서 보관 일 수를 나타냅니다. 지정 된 일 수 보다 오래 된 보고서는 자동으로 삭제 됩니다. CDR 오류 보고서는 Microsoft Lync 2013 등의 클라이언트 응용 프로그램에서 업로드 하는 진단 보고서입니다.</p>
<p>이 속성은 1에서 2562 일 사이의 정수 값으로 설정할 수 있습니다.</p></td>
<td><p>60일</p></td>
</tr>
</tbody>
</table>


마찬가지로, 선택한 체감 품질 설정에 대 한 기본값이이 표에 표시 됩니다.


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
<td><p>체감 품질 모니터링을 사용할 수 있는지 여부를 나타냅니다. True 인 경우 모든 체감 품질 레코드가 수집 되 고 모니터링 데이터베이스에 기록 됩니다.</p></td>
<td><p>False</p></td>
</tr>
<tr class="even">
<td><p>EnablePurging</p></td>
<td><p>체감 품질 레코드를 데이터베이스에서 정기적으로 삭제할지 여부를 나타냅니다. True 인 경우 KeepQoEDataForDays 속성에 지정 된 기간 후에 레코드가 삭제 됩니다. False 인 경우 체감 품질 레코드는 무한정 유지 됩니다.</p></td>
<td><p>False</p></td>
</tr>
<tr class="odd">
<td><p>KeepQoEDataForDays</p></td>
<td><p>체감 품질 레코드가 데이터베이스에 유지 되는 일 수를 나타냅니다. 지정 된 일 수 보다 오래 된 레코드는 자동으로 삭제 됩니다. 그러나이는 제거가 활성화 된 경우에만 발생 합니다.</p>
<p>KeepCallDetailForDays는 1에서 2562 일 사이의 모든 정수 값으로 설정할 수 있습니다.</p></td>
<td><p>60일</p></td>
</tr>
</tbody>
</table>


이러한 전역 설정을 수정 해야 하는 경우 CsCdrConfiguration 및 CsQoEConfiguration cmdlet을 사용 하 여이 작업을 수행할 수 있습니다. 예를 들어 Lync Server Management Shell 내에서 실행 되는이 명령은 전역 범위에서 CDR 모니터링을 사용 하지 않도록 설정 합니다. 이것은 EnableCDR 속성을 False ($False)로 설정 하 여 수행 됩니다.

    Set-CsCdrConfiguration -Identity "global" -EnableCDR $False

모니터링을 사용 하지 않도록 설정 해도 프런트 엔드 풀의 모니터링 저장소는 분리 되지 않으며 백엔드 모니터링 데이터베이스에 대 한 제거 또는 영향을 받지 않는다는 점에 유의 하세요. Lync Server Management Shell을 사용 하 여 CDR 또는 체감 품질 모니터링을 비활성화 하는 경우에는 일시적으로 Lync Server가 모니터링 데이터를 수집 하 고 보관 하지 못하게 됩니다. 이 경우,이 경우 CDR 데이터를 수집 하 고 보관 하는 작업을 다시 시작 하려면 EnableCDR 속성을 True ($True)로 다시 설정 하기만 하면 됩니다.

    Set-CsCdrConfiguration -Identity "global" -EnableCDR $True

마찬가지로,이 명령은 전역 범위에서 체감 품질 레코드 제거를 비활성화 합니다.

    Set-CsQoEConfiguration -Identity "global" -EnablePurging $False

전역 설정 외에 CDR 및 체감 품질 구성 설정은 사이트 범위에 할당할 수 있습니다. 이렇게 하면 모니터링할 때 추가적으로 관리 유연성을 제공 합니다. 예를 들어 관리자는 Redmond 사이트에 대해 CDR 모니터링을 사용 하도록 설정할 수 있지만, 더블린 사이트에 대 한 CDR 모니터링을 사용 하지 않도록 설정 합니다. 사이트 범위에서 새 CDR 구성 설정을 만들려면 다음과 같은 명령을 사용 합니다.

    New-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False

사이트 범위에서 구성한 설정이 전역 범위에서 구성 된 설정 보다 우선 한다는 점에 유의 하세요. 예를 들어, 전역 범위에서 CDR 모니터링을 사용 하도록 설정 했지만 사이트 범위 (Redmond 사이트의 경우)에서 사용할 수 없는 경우 이는 레드먼드 사이트의 사용자에 대 한 통화 정보 기록 정보가 보관 되지 않는다는 의미입니다. 그러나 다른 사이트 (즉, Redmond 사이트 설정 대신 전역 설정에서 관리 하는 사용자)의 사용자에 게는 통화 정보 기록 정보가 보관 됩니다.

다음과 같은 명령을 사용 하 여 사이트 범위에서 새 체감 품질 구성 설정을 만들 수 있습니다.

    New-CsQoEConfiguration -Identity "site:Redmond" -KeepQoEDataForDays 15

자세한 내용은 Lync Server 관리 셸 내에서 다음 명령을 입력 합니다.

    Get-Help New-CsCdrConfiguration | more
    Get-Help Set-CsCdrConfiguration | more
    Get-Help New-CsQoEConfiguration | more
    Get-Help Set-CsQoEConfiguration | more

</div>

<span> </span>

</div>

</div>

</div>

