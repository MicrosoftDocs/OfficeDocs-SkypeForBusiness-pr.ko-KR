---
title: 사이트에 할당 된 Kerberos 계정의 구성 테스트
description: 사이트에 할당 된 Kerberos 계정의 구성 테스트
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing configuration of the Kerberos account assigned to a site
ms:assetid: a087d77e-c59e-44f5-9caa-ccfd41be7276
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743837(v=OCS.15)
ms:contentKeyID: 63969637
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0eab1618474a19753a4c6064d59aa4f8a856fceb
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560694"
---
# <a name="testing-configuration-of-the-kerberos-account-assigned-to-a-site-in-lync-server-2013"></a>Lync Server 2013에서 사이트에 할당 된 Kerberos 계정의 구성 테스트

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



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
<p>Windows PowerShell의 원격 인스턴스를 사용 하 여 실행 하는 경우 사용자에 게 Test-CsKerberosAccountAssignment cmdlet을 실행 하는 권한이 있는 RBAC 역할을 할당 해야 합니다. 이 cmdlet을 사용할 수 있는 모든 RBAC 역할의 목록을 보려면 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsKerberosAccountAssignment&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>설명

Test-CsKerberosAccountAssignment cmdlet을 사용 하 여 Kerberos 계정이 지정 된 사이트와 연결 되었는지,이 계정이 제대로 구성 되었는지, 계정이 예상 대로 작동 하는지 확인할 수 있습니다. Kerberos 계정은 IIS (인터넷 정보 서비스)를 실행 하는 사이트의 모든 컴퓨터에 대 한 인증 주체로 작동할 수 있는 컴퓨터 계정입니다. 이러한 계정은 Kerberos 인증 프로토콜을 사용 하기 때문에, 계정을 Kerberos 계정 이라고 하며, 새 인증 프로세스를 Kerberos 웹 인증 이라고 합니다. 이렇게 하면 단일 계정을 사용 하 여 모든 IIS 서버를 관리할 수 있습니다.

자세한 내용은 [get-cskerberosaccountassignment](https://technet.microsoft.com/library/Gg425938(v=OCS.15)) cmdlet에 대 한 도움말 설명서를 참조 하십시오.

</div>

<div>

## <a name="running-the-test"></a>테스트 실행

기본적으로 Test-CsKerberosAccountAssignment는 화면에 출력이 거의 표시 되지 않습니다. 대신, cmdlet에서 반환 된 정보가 HTML 파일에 기록 됩니다. 따라서 Test-Get-cskerberosaccountassignment를 실행할 때마다 Verbose 매개 변수와 Report 매개 변수를 포함 하는 것이 좋습니다. Verbose 매개 변수는 cmdlet이 실행 되는 동안 약간 더 자세한 출력을 화면에 제공 합니다. Report 매개 변수를 사용 하면 Get-cskerberosaccountassignment에서 생성 되는 HTML 파일의 파일 경로와 파일 이름을 지정할 수 있습니다. Report 매개 변수를 포함 하지 않으면 HTML 파일이 사용자 폴더에 자동으로 저장 되 고 ce84964a-c4da-4622-ad34-c54ff3ed361f.html과 같은 이름이 지정 됩니다.

Get-cskerberosaccountassignment를 실행할 때 사이트 Id도 지정 해야 합니다. Kerberos 계정은 사이트 범위에서 할당 됩니다.

다음 명령은 Test-CsKerberosAccountAssignment를 실행 하 고 출력을 C: \\ LogsKerberosTest.html 이라는 파일에 저장 합니다 \\ .

    Test-CsKerberosAccountAssignment -Identity "site:Redmond" -Report "C:\Logs\KerberosTest.html" -Verbose

자세한 내용은 [get-cskerberosaccountassignment](https://technet.microsoft.com/library/Gg425938(v=OCS.15)) cmdlet에 대 한 도움말 설명서를 참조 하십시오.

</div>

<div>

## <a name="determining-success-or-failure"></a>성공 또는 실패 확인

Test-CsKerberosAccountAssignment cmdlet은 성공적인 또는 실패를 나타내는 간단한 표시를 반환 하지 않습니다. 대신 Internet Explorer를 사용 하 여 생성 된 HTML 파일을 확인 해야 합니다.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>테스트가 실패 한 이유

Test-CsKerberosAccountAssignment 실패할 수 있는 몇 가지 일반적인 이유는 다음과 같습니다.

  - 잘못 된 사이트 Id를 지정 했을 수 있습니다. 유효한 사이트 Id 목록을 반환 하려면 다음 명령을 사용 합니다.
    
        Get-CsSite | Select-Identity Identity
    
    사이트 Id는 일반적으로 다음과 같이 표시 됩니다.
    
    사이트: Redmond

  - 지정한 사이트에 Kerberos 계정이 할당 되어 있지 않을 수 있습니다. 다음과 같은 명령을 실행 하 여 Kerberos 계정이 사이트에 할당 되었는지 여부를 확인할 수 있습니다.
    
        Get-CsKerberosAccountAssignment -Identity "site:Redmond"

  - Kerberos 계정에 잘못 된 암호가 있을 수 있습니다. 보고서에 다음과 같은 오류 메시지가 표시 되 면 Kerberos 계정 암호를 다시 설정 해야 할 수 있습니다.
    
    InvalidKerberosConfiguration: Kerberos 구성이 잘못 되었습니다.
    
    InvalidKerberosConfiguration: atl-cs001.litwareinc.com의 Kerberos 구성이 잘못 되었습니다. 지정 된 계정이 litwareinc kerberostest입니다 \\ . 계정이 만료 되지 않았는지와 컴퓨터에 구성 된 암호가 계정의 Active Directory 암호와 일치 하는지 확인 합니다.
    
    [-C44ercosaccountpassword](https://technet.microsoft.com/library/Gg398659(v=OCS.15)) cmdlet을 사용 하 여 암호를 설정할 수 있습니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

