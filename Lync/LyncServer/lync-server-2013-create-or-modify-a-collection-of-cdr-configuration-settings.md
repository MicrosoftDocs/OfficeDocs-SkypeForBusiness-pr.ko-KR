---
title: 'Lync Server 2013: CDR 구성 설정 모음 만들기 또는 수정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a collection of CDR configuration settings
ms:assetid: c830be5a-2a82-468d-9c46-d3fec0f79fd0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721878(v=OCS.15)
ms:contentKeyID: 49733812
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 37ed8be52827f56b14c52f1bddd950ab39883cdf
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763360"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-collection-of-cdr-configuration-settings-in-lync-server-2013"></a>Lync Server 2013에서 CDR 구성 설정 모음 만들기 또는 수정

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-02-23_

CDR (통화 정보 기록)를 사용 하면 피어 투 피어 인스턴트 메시지 세션, VoIP (Voice over 인터넷 프로토콜) 전화 통화, 회의 통화 등의 사용 현황을 추적할 수 있습니다. 이 사용 현황 데이터에는 누가 누구에 게, 그들이 통화 되었는지, 그리고 그에 얼마나 오랜 시간에 대 한 정보가 포함 됩니다.

Microsoft Lync Server 2013을 설치할 때 CDR 구성 설정의 단일 전역 컬렉션이 만들어집니다. 또한 관리자는 사이트 범위에서 사용자 지정 설정을 만드는 옵션도 있습니다. 이러한 사이트 범위 설정이 사용 될 때마다 전역 설정 보다 우선적으로 적용 됩니다. 예를 들어 Redmond 사이트에 대 한 사이트 범위 설정을 만드는 경우 전역 설정이 아닌 해당 설정이 Redmond에서 CDR를 관리 하는 데 사용 됩니다.

Lync Server 제어판 또는 [New CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration) cmdlet 중 하나를 사용 하 여 CDR 구성 설정을 만들 수 있습니다. Lync Server 제어판 또는 [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration) cmdlet을 사용 하 여 기존 설정을 수정할 수 있습니다. Lync Server 제어판을 사용 하 여 설정을 만들거나 수정 하는 경우 다음 옵션을 사용할 수 있습니다.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>UI 설정</th>
<th>PowerShell 매개 변수</th>
<th>설명</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>이름</p></td>
<td><p>Identity</p></td>
<td><p>생성 되는 CDR 구성 설정의 고유 식별자입니다. 이러한 설정은 사이트 범위 에서만 만들 수 있습니다.</p></td>
</tr>
<tr class="even">
<td><p>CDRs의 모니터링 사용</p></td>
<td><p>EnableCDR</p></td>
<td><p>CDR를 사용할 수 있는지 여부를 나타냅니다.</p></td>
</tr>
<tr class="odd">
<td><p>CDRs를 제거 하도록 설정</p></td>
<td><p>EnablePurging</p></td>
<td><p>Cdr 레코드가 CDR 데이터베이스에서 정기적으로 삭제 되는지 여부를 나타냅니다.</p></td>
</tr>
<tr class="even">
<td><p>최대 기간 (일) 동안 CDRs 유지</p></td>
<td><p>KeepCallDetailForDays</p></td>
<td><p>Cdr 레코드가 CDR 데이터베이스에 유지 되는 일 수를 나타냅니다. 지정 된 일 수 보다 오래 된 레코드는 자동으로 삭제 됩니다. (제거는 제거를 사용 하는 경우에만 사용할 수 있습니다.)</p></td>
</tr>
<tr class="odd">
<td><p>최대 기간 동안 오류 보고서 데이터 유지 (일)</p></td>
<td><p>KeepErrorReportForDays</p></td>
<td><p>CDR 오류 보고서가 유지 되는 일 수를 나타냅니다. 지정 된 일 수 보다 오래 된 보고서는 자동으로 삭제 됩니다. CDR 오류 보고서는 클라이언트 응용 프로그램에서 업로드 하는 진단 보고서입니다.</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> 새로운 CsCdrConfiguration 및 CsCdrConfiguration cmdlet에는 Lync Server 제어판에서 사용할 수 없는 추가 옵션이 포함 되어 있습니다. 자세한 내용은 <A href="https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration">CsCdrConfiguration</A> 및 <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration">Set-CsCdrConfiguration</A> 도움말 항목을 참조 하세요.



</div>

<div>

## <a name="to-create-cdr-configuration-settings-by-using-lync-server-control-panel"></a>Lync Server 제어판을 사용 하 여 CDR 구성 설정을 만들려면

1.  Lync Server 제어판에서 **모니터링 및 보관**을 클릭 합니다.

2.  **통화 정보 기록** 탭에서 **새로 만들기**를 클릭 합니다.

3.  **사이트 선택** 대화 상자에서 새 구성 설정을 만들 사이트를 선택 합니다. 대화 상자가 비어 있으면 모든 사이트에 CDR 구성 설정 컬렉션이 이미 할당 되었음을 의미 합니다. 각 사이트는 해당 컬렉션 하나로 제한 됩니다. 이 경우 설정을 삭제 하 고 다시 만들거나 기존 설정을 수정 하면 됩니다.

4.  **새 CDR (통화 정보 기록) 설정** 대화 상자에서 원하는 항목을 선택한 다음 **커밋을**클릭 합니다.

</div>

<div>

## <a name="to-modify-existing-cdr-configuration-settings-by-using-lync-server-control-panel"></a>Lync Server 제어판을 사용 하 여 기존 CDR 구성 설정을 수정 하려면

1.  Lync Server 제어판에서 **모니터링 및 보관**을 클릭 합니다.

2.  수정할 설정 모음을 두 번 클릭 하거나 모음을 선택 하 고 **편집**을 클릭 한 다음 **세부 정보 표시**를 클릭 합니다. 한 번에 하나의 컬렉션만 수정할 수 있습니다. 여러 컬렉션을 동일 하 게 변경 하려면 Lync Server 관리 셸을 대신 사용 합니다.

3.  **CDR (통화 정보 기록 편집) 설정** 대화 상자에서 원하는 항목을 선택한 다음 **커밋을**클릭 합니다.

</div>

<div>

## <a name="creating-cdr-configuration-settings-by-using-windows-powershell-cmdlets"></a>Windows PowerShell Cmdlet을 사용 하 여 CDR 구성 설정 만들기

Windows PowerShell 및 **새 CsCdrConfiguration** cmdlet을 사용 하 여 CDR 구성 설정을 만들 수도 있습니다. Lync Server 2013 관리 셸에서 또는 Windows PowerShell의 원격 세션에서이 cmdlet을 실행할 수 있습니다. 원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.

<div>

## <a name="to-create-a-new-collection-of-cdr-configuration-settings"></a>CDR 구성 설정의 새 컬렉션을 만들려면

  - 이 명령은 Redmond 사이트에 적용 되는 새 CDR 구성 설정 모음을 만듭니다.
    
        New-CsCdrConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-create-a-collection-of-cdr-configuration-settings-that-disable-call-detail-recording"></a>통화 정보 기록을 사용 하지 않도록 설정 하는 CDR 구성 설정 모음을 만들려면

  - 앞의 명령에서 필수 Id 매개 변수 이외의 매개 변수를 지정 하지 않았으므로 새 구성 설정 모음에는 해당 속성에 대 한 기본값이 사용 됩니다. 다른 속성 값을 사용 하는 설정을 만들려면 간단히 적절 한 매개 변수와 매개 변수 값을 포함 합니다. 예를 들어 기본적으로 통화 정보를 사용 하지 않도록 설정 허용에 대 한 컬렉션을 만들려면 다음과 같은 명령을 사용 합니다.
    
        New-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False

</div>

<div>

## <a name="to-specify-multiple-property-values-when-creating-a-new-collection-of-cdr-configuration-settings"></a>CDR 구성 설정의 새 컬렉션을 만들 때 여러 속성 값을 지정 하려면

  - 여러 매개 변수를 포함 하 여 여러 속성 값을 수정할 수 있습니다. 예를 들어이 명령은 90 일간 30 일간 오류 보고서에 대 한 통화 세부 정보 기록을 유지 하도록 새로운 설정을 구성 합니다.
    
        New-CsCdrConfiguration -Identity "site:Redmond" -KeepCallDetailForDays 30 -KeepErrorReportForDays 90

</div>

자세한 내용은 [새 CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration) cmdlet에 대 한 도움말 항목을 참조 하세요.

</div>

</div>

<span> </span>

</div>

</div>

</div>

