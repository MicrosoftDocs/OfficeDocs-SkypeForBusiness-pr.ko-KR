---
title: 'Lync Server 2013: 통합 연락처 저장소 액세스 테스트'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing Unified Contact Store access
ms:assetid: 761f46bd-2e14-4f40-82b9-afa1eaa816b0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727309(v=OCS.15)
ms:contentKeyID: 63969621
ms.date: 05/16/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5552c03ac18ddd373385674da03d872ce89eb585
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48503905"
---
# <a name="testing-unified-contact-store-access-in-lync-server-2013"></a>Lync Server 2013에서 통합 연락처 저장소 액세스 테스트

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2015-05-15_


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
<p>Windows PowerShell의 원격 인스턴스를 사용 하 여 실행 하는 경우 <strong>test-csunifiedcontactstore</strong> cmdlet을 실행 하는 권한이 있는 RBAC 역할을 사용자에 게 할당 해야 합니다. 이 cmdlet을 사용할 수 있는 모든 RBAC 역할의 목록을 보려면 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsUnifiedContactStore&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>설명

Lync Server 2013에 도입 된 통합 연락처 저장소는 관리자에 게 Lync Server 대신 Microsoft Exchange Server 2013의 사용자 연락처를 저장 하는 옵션을 제공 합니다. 이를 통해 사용자는 Lync 2013 외에도 Outlook Web Access에서 동일한 연락처 집합에 액세스할 수 있습니다. Lync Server 에서도 계속 연락처를 저장할 수 있습니다. 이 경우 사용자는 Outlook 및 Outlook Web Access와 함께 사용 하기 위한 두 가지 연락처 집합, 그리고 Lync 2013와 함께 사용 해야 합니다.

**Test-csunifiedcontactstore** cmdlet을 실행 하 여 사용자의 연락처가 통합 연락처 저장소로 이동 되었는지 여부를 확인할 수 있습니다. **Test-csunifiedcontactstore** cmdlet은 지정 된 사용자 계정을 사용 하 여 통합 연락처 저장소에 연결한 다음 사용자의 대화 상대를 검색 해 봅니다. 검색할 수 있는 연락처가 없는 경우에는 명령이 "사용자에 대 한 연락처를 받지 못했습니다." 라는 메시지와 함께 오류가 발생 합니다. 사용자의 대화 상대가 있는지 확인하세요."라는 메시지가 표시됩니다.

사용자가 통합 연락처 저장소로 마이그레이션 되었지만 해당 대화 상대 목록에 연락처가 없는 경우 **test-csunifiedcontactstore** cmdlet은 실패 합니다. 지정한 사용자에 게 **test-csunifiedcontactstore** cmdlet에 대 한 대화 상대가 하나 이상 있어야 성공적으로 완료 됩니다.

</div>

<div>

## <a name="running-the-test"></a>테스트 실행

다음 예에 나와 있는 명령은 \\ 통합 연락처 저장소에서 user litwareinc kenmyer 연락처를 찾을 수 있는지 여부를 결정 합니다. 이 작업을 수행 하기 위해 예제의 첫 번째 명령은 **Get-Credential** cmdlet을 사용 하 여 사용자 litwareinc kenmyer에 대 한 Windows PowerShell 명령줄 인터페이스 자격 증명 개체를 만듭니다 \\ . 유효한 자격 증명 개체를 만들려면이 계정의 암호를 입력 하 고 **test-csunifiedcontactstore** cmdlet이 검사를 실행할 수 있는지 확인 해야 합니다.

예제의 두 번째 명령은 제공 된 자격 증명 개체 ($x)와 사용자 litwareinc kenmyer의 SIP 주소를 사용 하 여 해당 \\ 연락처를 통합 연락처 저장소에서 찾을 수 있는지 여부를 확인 합니다.

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsUnifiedContactStore -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

</div>

<div>

## <a name="determining-success-or-failure"></a>성공 또는 실패 확인

연락처 저장소에 대 한 액세스 권한이 올바르게 구성 된 경우 결과 속성이 Success로 표시 된 것과 비슷한 출력을 받게 됩니다 **.**

대상 Fqdn: atl-cs-001.litwareinc.com

결과: 성공

대기 시간: 00:00:14.9862716

오류 메시지:

진단을

연락처 저장소에 대 한 액세스를 올바르게 구성 하지 않으면 결과가 **실패로**표시 되 고 오류 및 진단 속성에 추가 정보가 기록 됩니다.

경고: 지정한 정규화 된 자격에 대 한 등록자 포트 번호를 읽지 못했습니다.

FQDN (도메인 이름) 기본 등록자 포트 번호 사용 오류

InvalidOperationException: 토폴로지에서 일치 하는 클러스터를 찾을 수 없습니다.

구독자

SyntheticTransactions SipSyntheticTransaction TryRetri를 관리 합니다.

eveRegistrarPortFromTopology (Int32& registrarPortNumber)

대상 Fqdn: atl-cs-001.litwareinc.com

결과: 실패

대기 시간: 00:00:00

오류 메시지: 10060, 연결 된 파티 때문에 연결 시도가 실패 했습니다.

일정 시간 후에 올바르게 응답 하지 않았거나

연결 된 호스트에서 연결이 실패 했습니다.

10.188.116.96에 응답 하지 못했습니다. 5061

내부 예외:

일정 기간 후에 연결 된 파티가 제대로 응답 하지 않음

연결 된 호스트 때문에 시간이 나 연결에 실패 했습니다.

에서 10.188.116.96에 응답 하지 못했습니다. 5061

진단을

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>테스트가 실패 한 이유

다음은 **test-csunifiedcontactstore에서** 오류가 발생할 수 있는 몇 가지 일반적인 이유입니다.

  - 잘못 된 매개 변수 값이 제공 되었습니다. 사용 하는 경우 선택적 매개 변수를 올바르게 구성 해야 하며 그렇지 않으면 테스트가 실패 합니다. 선택적 매개 변수 없이 명령을 다시 실행 하 여 성공 여부를 확인 합니다.

  - 통합 연락처 저장소에 연결 하지 못했으며 사용자에 대 한 대화 상대를 검색할 수 없습니다. 네트워크 연결 문제가 있을 수 있습니다.

</div>

<div>

## <a name="see-also"></a>참고 항목


[새-Csuser서비스 정책](https://docs.microsoft.com/powershell/module/skype/New-CsUserServicesPolicy)  
[설정-Csuser서비스 정책](https://docs.microsoft.com/powershell/module/skype/Set-CsUserServicesPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

