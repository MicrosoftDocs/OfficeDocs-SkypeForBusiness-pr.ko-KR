---
title: 마스터 주소 가이드에 대해 도심 주소 테스트
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing civic addresses against the master street address guide
ms:assetid: dc680de9-2a0f-4fd3-a99e-9bab0bc30ae5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690132(v=OCS.15)
ms:contentKeyID: 63969657
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7f9115e6bc0c65f589effc08ecd5f7b681208a54
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141474"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-civic-addresses-against-the-master-street-address-guide-in-lync-server-2013"></a>Lync Server 2013의 마스터 주소 가이드에 대 한 도심 주소 테스트

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2014-06-05_


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>확인 일정</p></td>
<td><p>매일</p></td>
</tr>
<tr class="even">
<td><p>테스트 도구</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>필요한 권한</p></td>
<td><p>Lync Server 관리 셸을 사용 하 여 로컬로 실행 하는 경우 사용자는 RTCUniversalServerAdmins 보안 그룹의 구성원 이어야 합니다.</p>
<p>Windows PowerShell의 원격 인스턴스를 사용 하 여 실행 하는 경우, 사용자에 게는 CsRegistration cmdlet을 실행 하는 권한이 있는 RBAC 역할을 할당 받아야 합니다. 이 cmdlet을 사용할 수 있는 모든 RBAC 역할의 목록을 보려면 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsLisCivicAddress &quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>설명

Test-csliscivicaddress cmdlet은 LIS (위치 정보 서비스) 데이터베이스에 추가 된 위치를 확인 하는 데 사용 됩니다. 이 cmdlet은 E9-1-1 네트워크 라우팅 공급자에 속한 MSAG (마스터 주소 가이드)에서 찾은 위치에 대해 위치를 비교 하 여 작동 합니다. 네트워크 라우팅 공급자가 없거나 공급자에 연결할 수 없는 경우 테스트가 실패 합니다.

명령에 optional 스위치 매개 변수 UpdateValidationStatus를 추가 하는 경우 테스트를 통과 하는 각 주소에 대해 해당 MSAGValid database 속성이 True로 설정 됩니다.

</div>

<div>

## <a name="running-the-test"></a>테스트 실행

Test-csliscivicaddress cmdlet을 사용 하 여 개별 주소를 테스트 하거나 여러 주소를 테스트할 수 있습니다. 예를 들어이 명령은 Redmond, WA에 있는 단일 주소를 테스트 합니다.

    Test-CsLisCivicAddress -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName Main -StreetSuffix St -PostDirectional "" -City Redmond -State WA -PostalCode 98052 -Country US -UpdateValidationStatus

비교를 통해이 명령은 LIS 데이터베이스에 있는 현재 모든 주소를 테스트 합니다.

    Get-CsLisCivicAddress | Test-CsLisCivicAddress -UpdateValidationStatus

자세한 내용은 [테스트-CsRegistration](https://technet.microsoft.com/library/Gg412737(v=OCS.15)) cmdlet에 대 한 도움말 설명서를 참조 하십시오.

</div>

<div>

## <a name="determining-success-or-failure"></a>성공 또는 실패 확인

Test-csliscivicaddress는 제공 된 주소에 대 한 성공 또는 실패를 보고 합니다. 주소를 찾을 수 없거나 서비스 공급자에 연결할 수 없는 경우 주소 테스트에 실패 합니다.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>테스트가 실패 한 이유

다음은 Test-csliscivicaddress에서 오류가 발생할 수 있는 몇 가지 일반적인 이유입니다.

  - LIS 서비스 공급자를 사용 하지 못할 수 있습니다. Export-cslisconfiguration cmdlet을 실행 하 여 LIS 서비스 공급자의 URL을 검색할 수 있습니다.
    
        Get-CsLisConfiguration 
    
    그런 다음 해당 URL에 ping을 사용 하 여 서비스 공급자가 있는지 확인할 수 있습니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

