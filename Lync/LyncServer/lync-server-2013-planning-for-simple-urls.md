---
title: 'Lync Server 2013: 단순 URL 계획'
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
ms.openlocfilehash: 224ca0315aff2618500182398cfe792c9626b883
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41750468"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-simple-urls-in-lync-server-2013"></a>Lync Server 2013의 단순 URL 계획

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2015-12-11_

간단한 Url을 사용 하면 사용자가 쉽게 모임에 참가할 수 있으며 Lync Server 관리 도구를 사용 하는 것이 관리자에 게 더욱 간편해 집니다.

Lync Server는 다음과 같은 세 가지 간단한 Url을 지원 합니다.

  - **회의** 는 사이트 또는 조직의 모든 컨퍼런스에 대 한 기본 URL로 사용 됩니다. 소개 간단한 URL의 예는 https://meet.contoso.com입니다. 특정 모임의 URL은 https://meet.contoso.com/ *사용자 이름*/7322994이 될 수 있습니다.
    
    모임에 참여 하는 간단한 URL을 사용 하 여 모임을 연결 하는 링크는 이해 하기 쉬우며, 의사 소통 및 배포 하기가 쉽습니다.

  - **전화 접속-** 전화 접속 회의 설정 웹 페이지에 액세스할 수 있습니다. 이 페이지에는 전화 회의 전화 접속 번호가 사용 가능한 언어로 표시 되 고, 회의 정보 (예약할 필요는 없음), 전화 회의 DTMF 컨트롤, 개인 식별 번호 관리 지원 ( PIN) 및 지정 된 회의 정보. 모임에 전화를 걸려면 사용자가 필요한 전화 번호와 PIN 정보에 액세스할 수 있도록 전화 접속 간단한 URL이 모든 모임 초대에 포함 되어 있습니다. 전화 접속 간단한 URL의 예는 https://dialin.contoso.com입니다.

  - **관리자** 는 Lync Server 제어판에 빠르게 액세스할 수 있습니다. 조직의 방화벽 내에 있는 컴퓨터에서 관리자는 브라우저에 관리 간단한 URL을 입력 하 여 Lync Server 제어판을 열 수 있습니다. 관리 단순 URL은 조직 내부입니다. 관리 간단한 URL의 예는https://admin.contoso.com

<div>

## <a name="simple-url-scope"></a>간단한 URL 범위

전역 범위를 포함 하도록 간단한 Url을 구성 하거나 조직의 각 중앙 사이트에 대해 서로 다른 간단한 Url을 지정할 수 있습니다. 전역 범위 단순 URL과 사이트 범위 단순 URL이 모두 지정 된 경우 사이트 범위 단순 URL이 우선권을 갖습니다.

대부분의 경우 사용자가 한 사이트에서 다른 사이트로 이동 하는 경우 단순한 URL이 변경 되지 않도록 전역 수준 에서만 간단한 Url을 설정 하는 것이 좋습니다. 이 예외는 다른 사이트의 전화 접속 사용자에 게 다른 전화 번호를 사용 해야 하는 조직입니다. 사이트의 간단한 URL (예: 전화 접속 간단한 URL)을 사이트 수준 간단한 URL로 설정한 경우에는 해당 사이트의 다른 간단한 url도 사이트 수준으로 설정 해야 합니다.

<div>


> [!NOTE]  
> 사이트 범위 단순 Url을 사용 하도록 선택한 경우에는 사용자가 다른 사이트의 프런트 엔드 풀 간을 이동할 수 없습니다. 모임 단순 Url이 사이트 간에 서로 다르기 때문에 사용자가 예약 된 모든 모임에 대 한 일정을 재조정 합니다. 여기에는 백업 관계의 풀이 별도의 사이트에 있는 장애 조치 시나리오가 포함 됩니다. 사이트 범위 단순 Url이 배포 되는 사이트 간에 장애 조치를 해야 하는 경우 URL 범위 때문에 사용자가 자신의 모임에 참가할 수 없게 됩니다. 자세한 내용은 Get-help를 확인 <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsSimpleUrlConfiguration">CsSimpleUrlConfiguration</A>.



</div>

토폴로지 작성기에서 전역 단순 Url을 설정할 수 있습니다. 사이트 수준에서 간단한 URL을 설정 하려면 Set-CsSimpleURLConfiguration cmdlet을 사용 해야 합니다.

</div>

<div>

## <a name="naming-your-simple-urls"></a>간단한 Url 이름 지정

간단한 Url의 이름을 지정 하는 데 권장 되는 세 가지 옵션이 있습니다. 선택 하는 옵션에 따라 간단한 Url을 지 원하는 DNS 레코드 및 인증서 설정 방법에 대 한 영향이 있습니다. 각 옵션에서 조직의 각 SIP 도메인에 대해 하나의 모임 단순 URL을 구성 해야 합니다.

사용 중인 SIP 도메인의 수에 관계 없이 모든 조직에서 전화 접속 및 관리자 용으로 하나의 간단한 URL만 필요 합니다.

필요한 DNS A 레코드 및 인증서에 대 한 자세한 내용은 [Lync server 2013의 간단한 url에 대 한 DNS 요구 사항](lync-server-2013-dns-requirements-for-simple-urls.md) 및 계획 설명서의 [lync server 2013의 내부 서버에 대 한 인증서 요구](lync-server-2013-certificate-requirements-for-internal-servers.md) 사항을 참조 하세요.

옵션 1에서 각 단순 URL에 대 한 새 SIP 도메인 이름을 만듭니다.

이 옵션을 사용 하는 경우 각 단순 URL에 대 한 별도의 DNS A 레코드가 필요 하며, 각 일치 하는 단순 URL은 인증서에 명명 되어야 합니다.

### <a name="simple-url-naming-option-1"></a>간단한 URL 명명 옵션 1

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>간단한 URL</strong></p></td>
<td><p><strong>예</strong></p></td>
</tr>
<tr class="even">
<td><p>시켜</p></td>
<td><p>https://meet.contoso.comhttps://meet.fabrikam.com(조직의 각 SIP 도메인에 대해 하나씩)</p></td>
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


옵션 2에서는 간단한 Url이 도메인 이름 lync.contoso.com를 기반으로 합니다. 따라서 세 가지 유형의 간단한 Url을 모두 사용할 수 있는 하나의 DNS A 레코드도 필요 합니다. 이 DNS A 레코드는 lync.contoso.com를 참조 합니다. 또한 조직의 다른 SIP 도메인에 대 한 별도의 DNS A 레코드가 필요 합니다.

### <a name="simple-url-naming-option-2"></a>간단한 URL 명명 옵션 2

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>간단한 URL</strong></p></td>
<td><p><strong>예</strong></p></td>
</tr>
<tr class="even">
<td><p>시켜</p></td>
<td><p>https://lync.contoso.com/Meethttps://lync.fabrikam.com/Meet(조직의 각 SIP 도메인에 대해 하나씩)</p></td>
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


옵션 3은 많은 SIP 도메인이 있는 경우 각 사용자에 게 별도의 단순 Url을 사용 하도록 하 고, 이러한 간단한 Url에 대 한 DNS 레코드 및 인증서 요구 사항을 최소화 하려는 경우에 가장 유용 합니다.

### <a name="simple-url-naming-option-3"></a>간단한 URL 명명 옵션 3

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>간단한 URL</strong></p></td>
<td><p><strong>예</strong></p></td>
</tr>
<tr class="even">
<td><p>시켜</p></td>
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

## <a name="simple-url-naming-and-validation-rules"></a>간단한 URL 명명 및 유효성 검사 규칙

토폴로지 작성기 및 Lync Server Management Shell cmdlet은 간단한 Url에 대 한 여러 가지 유효성 검사 규칙을 적용 합니다. 간단한 Url을 시작 및 전화 접속으로 설정 해야 하지만 관리자 용으로 설정 하는 것은 선택 사항입니다. 각 SIP 도메인에는 별도의 단순 URL이 필요 하지만, 전체 조직에 대해 하나의 전화 접속 단순 url과 하나의 관리자 단순 URL만 있으면 됩니다.

조직의 각 단순 URL은 고유한 이름을 가져야 하 고 다른 간단한 URL의 접두사가 될 수 없습니다 (예를 들어, lync.contoso.com/Meet를 사용 하 여 단순한 url로 시작 하 고 lync.contoso.com/Meet/Dialin를 전화 접속 간단한 URL로 설정할 수 없습니다). 간단한 URL 이름에는 풀의 FQDN 또는 포트 정보 (예: 허용 되지 않음) https://FQDN:88/meet 가 포함 될 수 없습니다. 모든 단순 Url은 https://접두사로 시작 해야 합니다.

간단한 Url에는 영숫자 문자 (a-z, A-z, 0-9, 마침표 (.)만 포함할 수 있습니다. 다른 문자를 사용 하는 경우 간단한 Url이 예상 대로 작동 하지 않을 수 있습니다.

</div>

<div>

## <a name="changing-simple-urls-after-deployment"></a>배포 후 간단한 Url 변경

초기 배포 후 간단한 URL을 변경 하는 경우에는 변경 내용이 간단한 Url에 대 한 DNS 레코드 및 인증서에 영향을 주는 방식을 알아야 합니다. 간단한 URL의 기본이 변경 되는 경우 DNS 레코드 및 인증서도 변경 해야 합니다. 예를 들어 lync.contoso.com에서 https://lync.contoso.com/Meet 로 https://meet.contoso.com 변경 하면 기본 URL이 MEET.CONTOSO.COM로 변경 되므로 DNS 레코드와 인증서를 변경 해야 meet.contoso.com을 참조할 수 있습니다. 간단한 URL을에서 https://lync.contoso.com/Meet 으로 https://lync.contoso.com/Meetings변경한 경우 lync.contoso.com의 기본 url은 동일 하 게 유지 되므로 DNS 또는 인증서를 변경할 필요가 없습니다.

그러나 간단한 URL 이름을 변경할 때마다 각 디렉터 및 프런트 엔드 서버에서 **-CsComputer** 를 실행 하 여 변경 내용을 등록 해야 합니다.

</div>

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013의 단순 URL에 대한 DNS 요구 사항](lync-server-2013-dns-requirements-for-simple-urls.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

