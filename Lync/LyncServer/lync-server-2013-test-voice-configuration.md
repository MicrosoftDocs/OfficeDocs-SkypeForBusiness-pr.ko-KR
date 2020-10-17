---
title: 'Lync Server 2013: 음성 구성 테스트'
description: 'Lync Server 2013: 음성 구성을 테스트 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test voice configuration
ms:assetid: 574794a3-cb30-4762-bb62-3a68574f05e9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725208(v=OCS.15)
ms:contentKeyID: 63969605
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4cc05286e5f534b4d469ef561d9ce009367e15be
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557074"
---
# <a name="test-voice-configuration-in-lync-server-2013"></a>Lync Server 2013에서 음성 구성 테스트

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2014-05-20_


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
<p>Windows PowerShell의 원격 인스턴스를 사용 하 여 실행 하는 경우 사용자에 게 Test-CsVoiceTestConfiguration cmdlet을 실행 하는 권한이 있는 RBAC 역할을 할당 해야 합니다. 이 cmdlet을 사용할 수 있는 모든 RBAC 역할의 목록을 보려면 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.</p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoiceTestConfiguration&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>설명

Lync Server에는 엔터프라이즈 음성 인프라의 개별 부분 (음성 경로, 음성 정책, SIP 트렁크)이 예상 대로 작동 하는지 확인할 수 있는 몇 가지 Windows PowerShell cmdlet (Test-CsVoiceRoute 예: Set-csvoicepolicy, Get-cstrunkconfiguration)이 포함 되어 있습니다.

Enterprise Voice에서는 모든 개별 작업을 수행 하는 것이 중요 하지만, 유효한 음성 경로, 유효한 음성 정책 및 유효한 SIP 트렁크를 사용할 수 있지만 사용자는 여전히 전화를 걸거나 받을 수 없습니다. 따라서 Lync Server는 음성 테스트 구성을 만들 수 있는 기능도 제공 합니다. 음성 테스트 구성은 일반적인 Enterprise Voice 시나리오를 나타내며, 음성 경로, 음성 정책, 다이얼 플랜 등을 지정 하 고 해당 개별 항목이 함께 작동 하 여 전화 서비스를 제공할 수 있는지 확인 합니다. 또한 지정 된 시나리오에서 기대치를 확인할 수 있습니다. 예를 들어 다이얼 플랜 A와 음성 정책 B의 조합이 음성 경로 C를 통해 호출 될 것으로 예상 한다고 가정 합니다. 음성 경로 C를 ExpectedRoute으로 입력할 수 있습니다. 테스트를 실행할 때 voice route C를 적용 하지 않으면 테스트가 실패 한 것으로 표시 됩니다.

</div>

<div>

## <a name="running-the-test"></a>테스트 실행

Windows PowerShell을 사용 하 여 음성 구성 모음을 테스트 하기 전에 먼저 Get-CsVoiceTestConfiguration cmdlet을 사용 하 여 이러한 구성 설정의 인스턴스를 검색 해야 합니다. 그런 다음 해당 인스턴스를 수정한 구성은 test-csvoicetestconfiguration으로 파이프 해야 합니다. 예제:

`Get-CsVoiceTestConfiguration -Identity "RedmondVoiceTestConfiguration" | Test-CsVoiceTestConfiguration`

모든 음성 테스트 구성 설정을 동시에 검사 하려면 다음 명령을 대신 사용 합니다.

`Get-CsVoiceTestConfiguration | Test-CsVoiceTestConfiguration`

자세한 내용은 Test-CsVoiceTestConfiguration cmdlet에 대 한 도움말 설명서를 참조 하십시오.

</div>

<div>

## <a name="determining-success-or-failure"></a>성공 또는 실패 확인

Test-CsVoiceTestConfiguration cmdlet은 테스트가 실패 했는지 여부를 보고 하 고, 작업을 완료 하는 데 사용 되는 변환 규칙, 음성 경로 및 PSTN 사용과 같은 성공적인 테스트에 대 한 추가 정보를 제공 합니다.

결과: 성공

TranslatedNumber: + 15551234

MatchingRule: Description =; Pattern = ^ ( \\ d {4} ) $; 번역 = + 1 \\ d; Name = Test; IsInternalExtension = False

FirstMatchingRoute: 사이트: Redmond

MatchingUsage: Local

테스트가 실패 하면 결과가 실패로 보고 됩니다.

결과: 실패

TranslatedNumber:   

FirstMatchingRoute:

MatchingUsage:      

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>테스트가 실패 한 이유

음성 테스트 구성 테스트에서는 음성 정책, 다이얼 플랜, 음성 경로 등 다양 한 항목을 테스트 하기 때문에 테스트에 실패 하는 몇 가지 요인이 있습니다. 테스트가 실패 하는 경우 첫 번째 단계는 Get-CsVoiceTestConfiguration cmdlet을 사용 하 여 구성 설정을 검토 하는 것입니다.

`Get-CsVoiceTestConfiguration -Identity "RedmondVoiceTestConfiguration"`

설정이 올바르게 구성 된 것 처럼 보이는 경우 Verbose 매개 변수를 포함 하 여 테스트를 다시 실행 합니다.

`Get-CsVoiceTestConfiguration -Identity "RedmondVoiceTestConfiguration" | Test-CsVoiceTestConfiguration`

Verbose 매개 변수는 다음 예에 표시 된 대로 Test-CsVoiceTestConfiguration에서 수행 하는 각 작업에 대 한 단계별 계정을 제공 합니다.

자세한 정보 표시: 다이얼 플랜 로드: "Global"

VERBOSE: "RedmondDialPlan" 라는 음성 정책을 로드 합니다.

이 단계별 계정은 테스트가 실제로 실패 한 위치에 대 한 유용한 단서를 제공할 수 있습니다. 그렇지 않은 경우에는 다른 Windows PowerShell cmdlet (예: Set-csvoicepolicy)을 사용 하 고, 체계적으로 시작 하 여 음성 테스트 구성 설정에 포함 된 개별 구성 요소를 확인할 수 있습니다.

이 외에도 테스트에서 전화를 라우팅하고 여전히 실패로 표시 되는 것을 알 수 있습니다. ExpectedRoute, ExpectedTranslatedNumber 및 ExpectedUsage에 대 한 값을 입력 하 고 이러한 기대치가 충족 되지 않는 경우에 발생할 수 있는 문제입니다. 예를 들어 음성 경로 C를 예상 음성 경로로 입력 한다고 가정 하면 테스트에서 음성 경로 D를 사용 하 여 통화를 실제로 완료 합니다. 이 경우 예상 되는 음성 경로를 사용 하지 않았으므로 테스트가 실패로 표시 됩니다. 테스트가 실패 하면 ExpectedRoute, ExpectedTranslatedNumber 및 ExpectedUsage에 대 한 값을 제거한 다음 테스트를 다시 실행할 수 있습니다. 이를 통해 통화를 완료할 수 없거나, 한 가지 작업을 실제로 수신 하는 것으로 예상 했을 때 오류가 발생 했는지 여부를 확인할 수 있습니다.

</div>

<div>

## <a name="see-also"></a>참고 항목


[수정한 구성은 test-csvoicetestconfiguration](https://docs.microsoft.com/powershell/module/skype/Test-CsVoiceTestConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

