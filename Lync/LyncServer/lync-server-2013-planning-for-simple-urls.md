---
title: 'Lync Server 2013: 단순 Url 계획'
description: 'Lync Server 2013: 단순 Url 계획'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for simple URLs
ms:assetid: 20e4f4b6-b7ff-4297-b00d-d1211ee800ac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398287(v=OCS.15)
ms:contentKeyID: 48183610
ms.date: 12/12/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 10a7f2aaf85dafe5facba7cfd2509cfcc8812d67
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558404"
---
# <a name="planning-for-simple-urls-in-lync-server-2013"></a>Lync Server 2013의 단순 Url 계획

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2015-12-11_

단순 Url은 사용자에 게 모임 참석을 보다 용이 하 게 하며, 관리자가 Lync Server 관리 도구를 보다 쉽게 사용할 수 있도록 합니다.

Lync Server에서는 다음과 같은 세 가지 단순 Url을 지원 합니다.

  - **모임**은 사이트 또는 조직의 모든 전화 회의에 대한 기준 URL로 사용됩니다. 모임 단순 URL의 예는 https://meet.contoso.com 입니다. 특정 모임에 대 한 URL은 https://meet.contoso.com/ *사용자 이름*/7322994이 될 수 있습니다.
    
    모임 단순 URL을 사용하면 모임에 참가할 링크를 쉽게 이해하고 전달하고 배포할 수 있습니다.

  - **전화 접속** 을 사용 하면 전화 접속 회의 설정 웹 페이지에 액세스할 수 있습니다. 이 페이지에는 전화 회의 전화 번호를 사용 가능한 언어로 표시 하 고, 전화 회의 정보 (예약할 필요가 없는 모임의 경우)를 지정 하 고, PIN (개인 식별 번호) 및 할당 된 회의 정보 관리를 지원 합니다. 전화 접속 단순 URL은 모임에 전화를 거는 사용자가 필요한 전화 번호와 PIN 정보에 액세스할 수 있도록 모든 모임 초대에 포함 됩니다. 전화 접속 단순 URL의 예는 https://dialin.contoso.com 입니다.

  - **관리자** 는 Lync Server 제어판에 빠르게 액세스할 수 있도록 합니다. 조직의 방화벽 내에 있는 모든 컴퓨터에서 관리자는 브라우저에 관리 단순 URL을 입력 하 여 Lync Server 제어판을 열 수 있습니다. 관리 단순 URL은 조직의 내부 URL입니다. 관리 단순 URL의 예는 https://admin.contoso.com

<div>

## <a name="simple-url-scope"></a>단순 URL 범위

전역 범위에서 적용되도록 단순 URL을 구성하거나 조직의 각 중앙 사이트에 대해 서로 다른 단순 URL을 지정할 수 있습니다. 전역 범위 단순 URL과 사이트 범위 단순 URL이 모두 지정 된 경우 사이트 범위 단순 URL이 우선 합니다.

대부분의 경우 전역 수준에서만 단순 URL을 설정하여 사이트 간에 이동하더라도 사용자의 모임 단순 URL이 변경되지 않도록 하는 것이 좋습니다. 단, 여러 사이트의 전화 접속 사용자에 서로 다른 전화 번호를 사용해야 하는 조직은 예외입니다. 사이트에서 하나의 단순 URL(예: 전화 접속 단순 URL)을 사이트 수준 단순 URL로 설정한 경우에는 해당 사이트의 다른 단순 URL도 사이트 수준으로 설정해야 합니다.

<div>


> [!NOTE]  
> 사이트 범위가 지정 된 단순 Url을 사용 하도록 선택 하는 경우 사용자가 다른 사이트의 Front-End 풀 간에 이동할 수 없으며, 사용자는 모임 단순 Url이 사이트 간에 서로 다른 것으로 예약 된 모든 모임에 대해 일정을 조정 하지 않아도 됩니다. 여기에는 백업 관계의 풀이 별도의 사이트에 있는 장애 조치 (failover) 시나리오가 포함 됩니다. 사이트 범위가 지정 된 단순 Url이 배포 되는 사이트 간에 장애 조치 (failover)를 수행 해야 하는 경우에는 URL 범위로 인해 사용자가 자신의 모임에 참가할 수 없게 됩니다. 자세한 내용을 보려면 <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsSimpleUrlConfiguration">get-cssimpleurlconfiguration</A>를 확인 하세요.



</div>

토폴로지 작성기에서 전역 단순 Url을 설정할 수 있습니다. 사이트 수준에서 단순 URL을 설정하려면 Set-CsSimpleURLConfiguration cmdlet을 사용해야 합니다.

</div>

<div>

## <a name="naming-your-simple-urls"></a>단순 URL 이름 지정

단순 URL의 이름을 지정할 때 권장되는 세 가지 옵션이 있습니다. 선택한 옵션에 따라 단순 URL을 지원하는 DNS A 레코드 및 인증서 설정 방법이 결정됩니다. 각 옵션에서는 조직의 각 SIP 도메인에 대해 하나의 모임 단순 URL을 구성해야 합니다.

보유한 SIP 도메인 수에 관계없이 전화 접속 단순 URL과 관리 단순 URL은 항상 전체 조직에서 각각 하나씩만 있으면 됩니다.

필요한 DNS A 레코드 및 인증서에 대 한 자세한 내용은 계획 설명서에서 lync server [2013의 단순 url에 대 한 DNS 요구](lync-server-2013-dns-requirements-for-simple-urls.md) 사항 및 [lync server 2013의 내부 서버에 대 한 인증서 요구 사항을](lync-server-2013-certificate-requirements-for-internal-servers.md) 참조 하세요.

옵션 1에서는 각 단순 URL에 대한 새 SIP 도메인 이름을 만듭니다.

이 옵션을 사용하는 경우 각 단순 URL에 대해 별도의 DNS A 레코드가 필요하며 각 모임 단순 URL의 이름이 인증서에 지정되어 있어야 합니다.

### <a name="simple-url-naming-option-1"></a>단순 URL 이름 지정 옵션 1

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>단순 URL</strong></p></td>
<td><p><strong>예</strong></p></td>
</tr>
<tr class="even">
<td><p>조건</p></td>
<td><p>https://meet.contoso.com, https://meet.fabrikam.com 등은 (조직의 각 SIP 도메인에 대해 하나씩)</p></td>
</tr>
<tr class="odd">
<td><p>전화 접속</p></td>
<td><p>https://dialin.contoso.com</p></td>
</tr>
<tr class="even">
<td><p>관리자</p></td>
<td><p>https://admin.contoso.com</p></td>
</tr>
</tbody>
</table>


옵션 2를 사용하는 경우에는 단순 URL이 도메인 이름 lync.contoso.com을 기반으로 하므로 세 가지 유형의 단순 URL 모두에서 사용할 수 있는 DNS A 레코드가 하나만 있으면 됩니다. 이 DNS A 레코드는 lync.contoso.com을 참조합니다. 조직의 다른 SIP 도메인에 대해서는 여전히 별도의 DNS A 레코드가 필요합니다.

### <a name="simple-url-naming-option-2"></a>단순 URL 이름 지정 옵션 2

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>단순 URL</strong></p></td>
<td><p><strong>예</strong></p></td>
</tr>
<tr class="even">
<td><p>조건</p></td>
<td><p>https://lync.contoso.com/Meet, https://lync.fabrikam.com/Meet 등은 (조직의 각 SIP 도메인에 대해 하나씩)</p></td>
</tr>
<tr class="odd">
<td><p>전화 접속</p></td>
<td><p>https://lync.contoso.com/Dialin</p></td>
</tr>
<tr class="even">
<td><p>관리자</p></td>
<td><p>https://lync.contoso.com/Admin</p></td>
</tr>
</tbody>
</table>


옵션 3은 많은 SIP 도메인이 있고 각각에 별도의 모임 단순 URL을 사용하지만 이러한 단순 URL에 필요한 DNS 레코드 및 인증서를 최소화하려는 경우에 가장 유용합니다.

### <a name="simple-url-naming-option-3"></a>단순 URL 이름 지정 옵션 3

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>단순 URL</strong></p></td>
<td><p><strong>예</strong></p></td>
</tr>
<tr class="even">
<td><p>조건</p></td>
<td><p>https://lync.contoso.com/contosoSIPdomain/Meet</p>
<p>https://lync.contoso.com/fabrikamSIPdomain/Meet</p></td>
</tr>
<tr class="odd">
<td><p>전화 접속</p></td>
<td><p>https://lync.contoso.com/Dialin</p></td>
</tr>
<tr class="even">
<td><p>관리자</p></td>
<td><p>https://lync.contoso.com/Admin</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="simple-url-naming-and-validation-rules"></a>단순 URL 이름 지정 및 유효성 검사 규칙

토폴로지 작성기 및 Lync Server 관리 셸 cmdlet은 단순 Url에 대 한 몇 가지 유효성 검사 규칙을 적용 합니다. 모임 및 전화 접속 단순 URL은 필수 설정이지만 관리 단순 URL은 선택 사항입니다. 모임 단순 URL은 SIP 도메인마다 별도의 URL이 있어야 하지만 전화 접속 단순 URL과 관리 단순 URL은 전체 조직에 하나만 있으면 됩니다.

조직의 각 단순 URL은 고유한 이름을 사용해야 하며 다른 단순 URL의 접두사가 될 수 없습니다(예: lync.contoso.com/Meet를 모임 단순 URL로 설정하고 lync.contoso.com/Meet/Dialin을 전화 접속 단순 URL로 설정할 수는 없음). 단순 URL 이름에는 풀의 FQDN을 포함할 수 없으며 모든 포트 정보 (예: https://FQDN:88/meet 허용 되지 않음)가 포함 됩니다. 모든 단순 URL은 https:// 접두사로 시작해야 합니다.

단순 URL은 영숫자(즉, a-z, A-Z, 0-9 및 마침표(.))만 포함할 수 있습니다. 다른 문자를 사용하면 단순 URL이 예상대로 작동하지 않을 수 있습니다.

</div>

<div>

## <a name="changing-simple-urls-after-deployment"></a>배포 후 단순 URL 변경

초기 배포 후 단순 URL을 변경하려면 단순 URL의 DNS 레코드 및 인증서가 이러한 변경으로 인해 받을 수 있는 영향을 파악해야 합니다. 단순 URL의 기준이 변경되면 DNS 레코드 및 인증서도 변경해야 합니다. 예를 들어에서를 변경 하면 https://lync.contoso.com/Meet https://meet.contoso.com 기본 URL이 lync.contoso.com에서 meet.contoso.com으로 변경 되므로 DNS 레코드 및 인증서를 변경 하 여 meet.contoso.com를 참조 해야 합니다. 단순 URL을에서로 변경한 경우 https://lync.contoso.com/Meet https://lync.contoso.com/Meetings lync.contoso.com의 기본 url은 동일 하 게 유지 되므로 DNS 또는 인증서를 변경할 필요가 없습니다.

그러나 단순 URL 이름을 변경할 때마다 각 디렉터 및 프런트 엔드 서버에서 **CsComputer를 사용** 하 여 변경 내용을 등록 해야 합니다.

</div>

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013의 단순 Url에 대 한 DNS 요구 사항](lync-server-2013-dns-requirements-for-simple-urls.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

