---
title: 'Lync Server 2013: Lync Server 2013 서버 인증서 확인'
description: 'Lync Server 2013: Lync Server 2013 서버 인증서를 확인 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Check server certificates
ms:assetid: 7b0474e8-0efe-47f0-84eb-a1ba575dabfd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725210(v=OCS.15)
ms:contentKeyID: 63969620
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 641651cb425b4fe8bd820bcebfa277084233bb1d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543594"
---
# <a name="check-lync-server-2013-server-certificates"></a>Lync Server 2013 서버 인증서 확인

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2014-11-01_


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>확인 일정</p></td>
<td><p>월간</p></td>
</tr>
<tr class="even">
<td><p>테스트 도구</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>필요한 권한</p></td>
<td><p>Lync Server 관리 셸을 사용 하 여 로컬로 실행 하는 경우 사용자는 RTCUniversalServerAdmins 보안 그룹의 구성원 이어야 합니다.</p>
<p>Windows PowerShell의 원격 인스턴스를 사용 하 여 실행 하는 경우 사용자에 게 Get-CsCertificate cmdlet을 실행 하는 권한이 있는 RBAC 역할을 할당 해야 합니다. 이 cmdlet을 사용할 수 있는 모든 RBAC 역할의 목록을 보려면 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.</p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Get-CsCertificate&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>설명

Get-CsCertificate cmdlet을 사용 하 여 각 Lync Server 인증서에 대 한 정보를 검색할 수 있습니다. 인증서에는 기본 제공 만료 날짜가 있으므로 특히 중요 합니다. 예를 들어 개인적으로 발급 된 인증서는 일반적으로 12 개월 후에 만료 됩니다. Lync Server 인증서가 만료 되 면 해당 인증서를 갱신 하거나 대체할 때까지 해당 기능이 손실 됩니다.

</div>

<div>

## <a name="running-the-test"></a>테스트 실행

각 Lync Server 인증서에 대 한 정보를 반환 하려면 다음 명령을 실행 하면 됩니다.

`Get-CsCertificate`

만료 날짜를 기준으로 반품 인증서 정보를 필터링 할 수도 있습니다. 예를 들어이 명령은 반환 된 데이터를 만료 된 인증서 (이후에는 사용할 수 없음)로 제한 합니다. 2014:

`Get-CsCertificate | Where-Object {$_.NotAfter -lt "6/1/2014"}`

자세한 내용은 Get-CsCertificate cmdlet에 대 한 도움말 설명서를 참조 하십시오.

Test-CsCertificateConfiguration cmdlet이 존재 하더라도 관리자에 게는 그다지 유용 하지 않습니다. 대신이 cmdlet은 인증서 마법사에서 주로 사용 됩니다. 이 cmdlet은 작동 하지만 다음 출력 예제에 표시 된 것 처럼 반환 되는 정보는 최소 값입니다.

지문 사용

\---------- ---

A9D51A2911C74FABFF7F2A8A994B20857D399107 기본값

</div>

<div>

## <a name="reviewing-the-output"></a>출력 검토

Get-CsCertificate cmdlet은 각 Lync Server 인증서에 대해 다음과 같은 정보를 반환 합니다.

발급자: CN = FabrikamCA

NotAfter: 12/28/2015 3:35:41 PM

NotBefore: 오후 1/2/2014 12:49:37

일련 번호: 611BB01200000000000C

제목: CN = LYNC-SE.fabrikam.com

AlternativeNames: {sip.fabrikam.com, LYNC-SE.fabrikam.com,

meet.fabrikam.com, admin.fabrikam.com}

지문: A9D51A2911C74FABFF7F2A8A994B20857D399107

사용: 기본값

일반적으로 Lync Server 인증서와 관련 된 주요 문제에는 인증서가 적용 되는 경우 (NotBefore) 또는 만료 되는 경우 (예: NotAfter)와 같은 날짜 및 시간이 포함 됩니다. 이러한 날짜와 시간은 매우 중요 하기 때문에, 반환 된 데이터를 인증서 사용, 인증서 일련 번호, 인증서 만료 날짜 등의 정보로 제한할 수 있습니다. 그런 다음 모든 인증서를 신속 하 게 검토 하 고 만료 되는 경우를 확인할 수 있습니다. 해당 정보만 반환 하려면 다음과 같이 명령을 옵션과 함께 사용 합니다.

`Get-CsCertificate | Select-Object Use, SerialNumber, NotAfter | Sort-Object NotAfter`

이 명령은 다음과 비슷한 데이터를 반환 하 고 만료 날짜 순서 대로 인증서를 정렬 합니다.

다음 이후 번호 사이 사용

\--- ------------ --------

기본값 611BB01200000000000C 12/28/2015 3:35:41 PM

WebServicesInteral 32980AA20BBB20000191 02/15/2016 2:16:12 PM

WebServicesExternal 0451B012003872651A0C 02/20/2016 7:11:58 AM

인증서 문제가 있는 경우 인증서에 대해 구성 된 AlternativeNames를 검토 하는 것이 좋습니다. 언뜻 보면 이것이 문제가 되는 것 처럼 보입니다. 기본적으로 콘솔 창의 크기에 따라 Get-CsCertificate 모든 이름을 표시 하지 못할 수 있습니다.

AlternativeNames: {sip.fabrikam.com, LYNC.fabrikam.com,

meet.fabrikam.com, fabrika

인증서에 할당 된 대체 이름을 모두 보려면 다음과 같은 명령을 사용 합니다.

`Get-CsCertificate | Where-Object {$_.SerialNumber -eq "611BB01200000000000C"} | Select-Object -ExpandProperty AlternativeNames`

이를 통해 인증서의 모든 대체 이름을 표시 해야 합니다.

sip.fabrikam.com

LYNC.fabrikam.com

meet.fabrikam.com

admin.fabrikam.com

LYNC-SE.fabrikam.com

Dialin.fabrikam.com

</div>

<div>

## <a name="see-also"></a>참고 항목


[Set-cscertificate](https://docs.microsoft.com/powershell/module/skype/Get-CsCertificate)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

