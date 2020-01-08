---
title: 'Lync Server 2013: 음성 구성 테스트'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Test voice configuration
ms:assetid: 574794a3-cb30-4762-bb62-3a68574f05e9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725208(v=OCS.15)
ms:contentKeyID: 63969605
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fbe9be7e0f7962bbab546822e7ce6cd47e063540
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979064"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-voice-configuration-in-lync-server-2013"></a>Lync Server 2013에서 음성 구성 테스트

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2014-05-20_


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
<td><p>권한이 필요 함</p></td>
<td><p>Lync Server Management Shell을 사용 하 여 로컬에서 실행 되는 경우 사용자는 RTCUniversalServerAdmins 보안 그룹의 구성원 이어야 합니다.</p>
<p>Windows PowerShell의 원격 인스턴스를 사용 하 여 실행 하는 경우 CsVoiceTestConfiguration cmdlet을 실행 하는 데 필요한 권한이 있는 RBAC 역할을 사용자에 게 할당 해야 합니다. 이 cmdlet을 사용할 수 있는 모든 RBAC 역할 목록을 보려면 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.</p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoiceTestConfiguration&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>설명

Lync Server에는 다양 한 Windows PowerShell cmdlet (예: CsVoiceRoute 및 테스트-Set-cstrunkconfiguration)이 포함 되어 있으며,이를 통해 엔터프라이즈 음성 인프라의 개별 부분 (음성 경로, 음성)을 확인할 수 있습니다. 정책, SIP trunks-예상 대로 작동 합니다.

모든 개별 부분이 작동 하도록 하는 Enterprise Voice에는 중요 한 반면, 유효한 음성 경로, 유효한 음성 정책, 유효한 SIP 트렁크를 가질 수 있지만, 여전히 사용자가 전화를 걸거나 받을 수는 없습니다. 이 때문에 Lync Server는 음성 테스트 구성을 만드는 기능도 제공 합니다. 음성 테스트 구성은 일반적인 엔터프라이즈 음성 시나리오를 나타냅니다. 음성 경로, 음성 정책, 다이얼 플랜 등을 지정 하 고 해당 개별 항목이 함께 작동 하 여 전화 서비스를 제공할 수 있는지 확인 합니다. 또한 특정 시나리오에서 기대에 대 한 유효성을 검사할 수 있습니다. 예를 들어 다이얼 플랜 A와 음성 정책 B의 조합이 음성 경로 C를 통해 착신 통신 하는 것으로 예상 하 고 있다고 가정 합니다. ExpectedRoute로 음성 경로 C를 입력할 수 있습니다. 테스트를 실행할 때 음성 경로 C가 적용 되지 않으면 테스트에 실패 한 것으로 표시 됩니다.

</div>

<div>

## <a name="running-the-test"></a>테스트 실행

Windows PowerShell을 사용 하 여 음성 구성 컬렉션을 테스트 하기 전에 먼저 Get-CsVoiceTestConfiguration cmdlet을 사용 하 여 이러한 구성 설정의 인스턴스를 검색 해야 합니다. 그런 다음 해당 인스턴스를 테스트-CsVoiceTestConfiguration로 파이프 해야 합니다. 예를 들면 다음과 같습니다.

`Get-CsVoiceTestConfiguration -Identity "RedmondVoiceTestConfiguration" | Test-CsVoiceTestConfiguration`

모든 음성 테스트 구성 설정을 동시에 확인 하려면이 명령을 대신 사용 합니다.

`Get-CsVoiceTestConfiguration | Test-CsVoiceTestConfiguration`

자세한 내용은 테스트 CsVoiceTestConfiguration cmdlet에 대 한 도움말 문서를 참조 하세요.

</div>

<div>

## <a name="determining-success-or-failure"></a>성공 또는 실패 확인

CsVoiceTestConfiguration cmdlet은 테스트 실패 또는 성공 여부를 보고 하 고, 작업을 완료 하는 데 사용 되는 번역 규칙, 음성 경로, PSTN 사용 등의 각 성공한 테스트에 대 한 추가 정보를 제공 합니다.

결과: 성공

TranslatedNumber: + 15551234

MatchingRule: Description =; Pattern = ^ (\\d{4}) $; 번역 = + 1\\d; Name = Test; IsInternalExtension = False

FirstMatchingRoute: 사이트: Redmond

MatchingUsage: Local

테스트에 실패 하면 결과가 실패로 보고 됩니다.

결과: 실패

TranslatedNumber:   

FirstMatchingRoute:

MatchingUsage:      

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>테스트가 실패할 수 있는 이유

음성 테스트 구성 테스트는 음성 정책, 다이얼 플랜, 음성 경로 등의 여러 다른 항목을 테스트 하기 때문에 테스트에 실패 하는 여러 가지 요인이 있습니다. 테스트가 실패 하는 경우 첫 번째 단계는 CsVoiceTestConfiguration cmdlet을 사용 하 여 구성 설정 자체를 검토 하는 것입니다.

`Get-CsVoiceTestConfiguration -Identity "RedmondVoiceTestConfiguration"`

설정이 올바르게 구성 된 것으로 보이는 경우 Verbose 매개 변수를 포함 하 여 테스트를 다시 실행 합니다.

`Get-CsVoiceTestConfiguration -Identity "RedmondVoiceTestConfiguration" | Test-CsVoiceTestConfiguration`

Verbose 매개 변수는 다음 예제에 표시 된 대로 CsVoiceTestConfiguration에서 수행 하는 각 작업의 단계별 계정을 제공 합니다.

자세한 정보: 다이얼 플랜 로드 중: "Global"

VERBOSE: 음성 정책 로드 중: "RedmondDialPlan"

이 단계별 계정은 테스트가 실제로 실패 한 곳에 대 한 유용한 단서를 제공할 수 있습니다. 그렇지 않으면 다른 Windows PowerShell cmdlet (예: CsVoicePolicy)을 사용 하 고, 적절 하 게 시작 하 여 음성 테스트 구성 설정에 포함 된 개별 구성 요소를 확인할 수 있습니다.

그 외에도 테스트에서 호출을 라우팅하고 오류로 표시 될 수 있다는 점에 유의 해야 합니다. ExpectedRoute, ExpectedTranslatedNumber 및 ExpectedUsage에 대 한 값을 입력 하는 경우 발생할 수 있으며 이러한 기대치는 충족 되지 않습니다. 예를 들어 예상 음성 경로로 음성 경로 C를 입력 하는 경우 테스트에서 음성 경로 D를 사용 하 여 통화를 실제로 완료 한다고 가정 합니다. 이 경우 예상 되는 음성 경로를 사용 하지 않아 테스트가 실패 한 것으로 표시 됩니다. 테스트에 실패 하는 경우 ExpectedRoute, ExpectedTranslatedNumber 및 ExpectedUsage에 대 한 값을 제거한 다음 테스트를 다시 실행할 수 있습니다. 이렇게 하면 호출이 완료 되지 않았거나, 문제가 발생 하 여 실제로 다른 작업을 받을 수 있기 때문에 실패 했는지 여부를 확인 하는 데 도움이 됩니다.

</div>

<div>

## <a name="see-also"></a>참고 항목


[테스트-CsVoiceTestConfiguration](https://docs.microsoft.com/powershell/module/skype/Test-CsVoiceTestConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

