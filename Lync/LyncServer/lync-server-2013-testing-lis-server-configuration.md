---
title: 'Lync Server 2013: LIS Server 구성 테스트'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing LIS server configuration
ms:assetid: 6b06e7ab-522f-41a2-878b-e89cd4e3c6da
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690129(v=OCS.15)
ms:contentKeyID: 63969614
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c38c0e05647e13a1da1f4a5f173b3e92c37a5300
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036286"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-lis-server-configuration-in-lync-server-2013"></a>Lync Server 2013에서 LIS 서버 구성 테스트

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
<p>Windows PowerShell의 원격 인스턴스를 사용 하 여 실행 하는 경우 Export-cslisconfiguration cmdlet을 실행 하는 권한이 있는 RBAC 역할을 사용자에 게 할당 해야 합니다. 이 cmdlet을 사용할 수 있는 모든 RBAC 역할의 목록을 보려면 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsLisConfiguration&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>설명

Export-cslisconfiguration cmdlet은 LIS 웹 서비스에 연결할 수 있는지 확인 합니다. 웹 서비스에 연결할 수 있으면 특정 위치를 찾을 수 있는지 여부에 관계 없이 테스트가 성공으로 간주 됩니다.

</div>

<div>

## <a name="running-the-test"></a>테스트 실행

CsLisConfguration cmdlet은 미리 구성 된 테스트 계정 (Lync Server 테스트 실행을 위한 테스트 계정 설정 참조) 또는 Lync Server를 사용 하도록 설정 된 사용자의 계정 중 하나를 사용 하 여 실행할 수 있습니다. 테스트 계정을 사용 하 여이 검사를 실행 하려면 테스트할 Lync Server 풀의 FQDN만 지정 하면 됩니다. 예:

    Test-CsLisConfiguration -TargetFqdn "atl-cs-001.litwareinc.com"

실제 사용자 계정을 사용 하 여이 검사를 실행 하려면 먼저 계정 이름과 암호가 포함 된 Windows PowerShell 자격 증명 개체를 만들어야 합니다. 그런 다음 Export-cslisconfiguration를 호출 하면 해당 자격 증명 개체 및 해당 계정에 할당 된 SIP 주소를 포함 해야 합니다.

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsLisConfiguration -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

자세한 내용은 [export-cslisconfiguration](https://docs.microsoft.com/powershell/module/skype/Test-CsLisConfiguration) cmdlet에 대 한 도움말 설명서를 참조 하십시오.

</div>

<div>

## <a name="determining-success-or-failure"></a>성공 또는 실패 확인

LIS가 올바르게 구성 된 경우 결과 속성이 Success로 표시 된 것과 비슷한 출력을 받게 됩니다 **.**

TargetUrihttps://atl-cs-001.litwareinc.com:443/locationinformation/

liservice .svc

TargetFqdn: atl-cs-001.litwareinc.com

결과: 성공

대기 시간: 00:00:06.1616913

오류

진단을

지정 된 사용자가 로그온 하거나 로그 오프할 수 없으면 결과가 실패로 표시 되 고 오류 및 진단 속성에 추가 정보가 기록 됩니다.

TargetUri

TargetFqdn: atl-cs-001.litwareinc.com

결과: 실패

대기 시간: 00:00:00

오류: 11004, 요청한 이름이 올바르지만 요청 된 데이터가 없습니다.

형식이 발견 됨

진단을

Export-cslisconfiguration: 토폴로지에서 일치 하는 클러스터를 찾을 수 없습니다.

예를 들어 위의 출력에는 "토폴로지에 일치 하는 클러스터가 없습니다." 라는 노트가 포함 되어 있습니다. 일반적으로에 지 서버에 문제가 있음을 나타내는 경우:에 지 서버를 사용 하 여 서비스 공급자에 연결 하 고 주소를 확인 하는 LIS입니다.

Export-cslisconfiguration에 오류가 발생 한 경우에는 다음 시간에 Verbose 매개 변수를 포함 하 여 테스트를 다시 실행할 수 있습니다.

    Test-CsLisConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

Verbose 매개 변수가 포함 된 경우 Export-cslisconfiguration는 지정 된 사용자가 Lync Server에 로그온 할 수 있는지 확인할 때 시도한 각 작업의 단계별 계정을 반환 합니다. 예:

통화 위치 정보 서비스입니다.

서비스 경로 =https://atl-cs-001.litwareinc.com:443/locationinformation/liservice.svc

Subnet =

BssId = 5

ChassisId =

PortId =

PortIdSubType = 정의 되지 않은 형식

Mac

응답 코드 Item400를 사용 하 여 예외 ' 위치 정보 웹 서비스 요청이 실패 했습니다. 워크플로 SyntheticTrsnactions가 실행 되는 동안 발생 합니다.

이전 출력을 자세히 살펴보면 cmdlet이 위치 정보 서비스에 대 한 호출을 시도 하면 실패 한 것을 볼 수 있습니다. 이 통화에서 사용 된 매개 변수 중 하나는 다음과 같습니다.

BssId = 5

이 값은 기본 BssID (서비스 집합 Id)에 사용할 수 없습니다. 대신 BssID는 다음과 유사 합니다.

12-34-56-78-90-ab

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>테스트가 실패 한 이유

다음은 Export-cslisconfiguration에서 오류가 발생할 수 있는 몇 가지 일반적인 이유입니다.

  - 잘못 된 매개 변수 값이 제공 되었습니다. 앞의 예제에 나와 있는 것 처럼 선택적 매개 변수를 올바르게 구성 해야 하며 그렇지 않으면 테스트가 실패 합니다. 선택적 매개 변수 없이 명령을 다시 실행 하 여 성공 여부를 확인 합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

