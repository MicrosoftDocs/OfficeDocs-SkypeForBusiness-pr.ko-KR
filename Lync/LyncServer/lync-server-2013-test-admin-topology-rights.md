---
title: 'Lync Server 2013: 관리 토폴로지 테스트 권한'
description: 'Lync Server 2013: 관리 토폴로지 테스트 권한'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test admin topology rights
ms:assetid: 0c03b7fd-449a-47ad-8263-ce811164cbce
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767943(v=OCS.15)
ms:contentKeyID: 63969575
ms.date: 12/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 22d713297d0e944c7acbc5efcb11b21ea1b26639
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568564"
---
# <a name="test-admin-topology-rights-in-lync-server-2013"></a>Lync Server 2013의 관리 토폴로지 테스트 권한

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2016-12-08_


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>확인 일정</p></td>
<td><p>초기 Lync Server 배포 후 사용 권한 관련 문제가 발생 하는 경우 필요에 따라</p></td>
</tr>
<tr class="even">
<td><p>테스트 도구</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>필요한 권한</p></td>
<td><p>Lync Server 관리 셸을 사용 하 여 로컬로 실행 하는 경우 사용자는 RTCUniversalServerAdmins 보안 그룹의 구성원 이어야 합니다.</p>
<p>Windows PowerShell의 원격 인스턴스를 사용 하 여 실행 하는 경우 사용자에 게 Test-CsSetupPermission cmdlet을 실행 하는 권한이 있는 RBAC 역할을 할당 해야 합니다. 이 cmdlet을 사용할 수 있는 모든 RBAC 역할의 목록을 보려면 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsSetupPermission&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>설명

기본적으로 도메인 관리자만 lync server 토폴로지를 사용 하도록 설정 하 고 Lync Server 인프라를 크게 변경할 수 있습니다. 이는 도메인 관리자와 Lync Server 관리자가 1과 동일한 경우에는 문제가 되지 않습니다. 대부분의 조직에서는 Lync Server 관리자가 전체 도메인에 대 한 관리 권한을 보유 하지 않습니다. 기본적으로 RTCUniversalServerAdmins 그룹의 구성원으로 정의 된 이러한 관리자는 Lync Server 토폴로지를 변경할 수 없습니다. RTCUniversalServerAdmins 그룹의 구성원에 게 토폴로지를 변경할 수 있는 권한을 부여 하려면 [Grant-CsSetupPermission](https://docs.microsoft.com/powershell/module/skype/Grant-CsSetupPermission) cmdlet을 사용 하 여 필요한 Active Directory 권한을 할당 해야 합니다.

Test-CsSetupPermission cmdlet은 Lync Server 또는 해당 구성 요소 중 하나를 설치 하는 데 필요한 사용 권한이 지정 된 Active Directory 컨테이너에 구성 되어 있는지 확인 합니다. 사용 권한이 할당 되지 않은 경우에는 Grant-CsSetupPermission cmdlet을 실행 하 여 RTCUniversalServerAdmins 그룹의 구성원에 게 Lync Server 설치 및 사용 권한을 부여할 수 있습니다.

<div>


> [!NOTE]  
> 부여-CsSetupPermission에서 할당 된 사용 권한의 자세한 목록은 블로그 게시물 <A href="https://blogs.technet.com/b/jenstr/archive/2011/02/07/grant-cssetuppermission-and-grant-csoupermission.aspx">부여-cssetuppermission 및 Grant-Cssetuppermission</A>를 참조 하십시오.



</div>

</div>

<div>

## <a name="running-the-test"></a>테스트 실행

Active Directory 컨테이너에 대 한 설치 권한이 할당 되었는지 확인 하려면 Test-CsSetupPermission cmdlet을 호출 합니다. 확인할 컨테이너의 고유 이름을 지정 합니다. 예를 들어이 명령은 컨테이너 ou = CsServers, dc = litwareinc, dc = com에 대 한 설치 권한을 확인 합니다.

    Test-CsSetupPermission -ComputerOU "ou=CsServers,dc=litwareinc,dc=com"

자세한 내용은 [테스트-CsSetupPermission](https://docs.microsoft.com/powershell/module/skype/Test-CsSetupPermission) cmdlet에 대 한 도움말 항목을 참조 하십시오.

</div>

<div>

## <a name="determining-success-or-failure"></a>성공 또는 실패 확인

Test-CsSetupPermission Active Directory 컨테이너에 필요한 사용 권한이 이미 설정 된 것으로 확인 되 면 cmdlet은 True 값을 반환 합니다.

True

사용 권한을 설정 하지 않으면 Test-CsSetupPermission에서 False 값을 반환 합니다. 일반적으로이 값은 많은 경고 메시지에 포함 됩니다. 예제:

경고: ACE (액세스 제어 항목) atl-cs-001 \\ RTCUniversalServerAdmins; 통해 ExtendedRight; None None 1131f6aa-9c07-11d1-f79f-00c04fc2dcd2

경고: "CN = Computers, DC = litwareinc, DC = com" 개체의 Ace (액세스 제어 항목)가 준비 되지 않았습니다.

False

경고: "테스트-CsSetupPermission" 처리가 경고와 함께 완료 되었습니다. 이 실행 중에 경고 "2"가 기록 되었습니다.

경고: 자세한 결과는 "C: \\ Users \\ Admin \\ AppData \\ Local \\ Temp \\Test-CsSetupPermission-1da99ba6-abe2-45e4-8b16-dfd244763118.html"에서 찾을 수 있습니다.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>테스트가 실패 한 이유

예외가 드물게 발생 하는 경우에는 일반적으로 지정 된 Active Directory 컨테이너에 대해 설치 권한이 할당 되지 않는 Test-CsSetupPermission에 오류가 발생할 수 있습니다. Grant-CsSetupPermission cmdlet을 사용 하 여 이러한 사용 권한을 할당할 수 있습니다. 예를 들어이 명령은 litwareinc.com 도메인의 컴퓨터 컨테이너에 설치 권한을 부여 합니다.

    Grant-CsSetupPermission -ComputerOU "cn=Computers,dc=litwareinc,dc=com"

자세한 내용은 [테스트-CsSetupPermission](https://docs.microsoft.com/powershell/module/skype/Test-CsSetupPermission) cmdlet에 대 한 도움말 항목을 참조 하십시오.

</div>

</div>

<span> </span>

</div>

</div>

</div>

