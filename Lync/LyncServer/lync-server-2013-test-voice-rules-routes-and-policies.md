---
title: 'Lync Server 2013: 음성 규칙, 경로 및 정책 테스트'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test voice rules, routes, and policies
ms:assetid: ebb9c3fa-6950-4311-87ca-e1ecd9280a43
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725213(v=OCS.15)
ms:contentKeyID: 63969661
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8da7334e00c0361a5c8ad840dbf57ee7d5024763
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141554"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="test-voice-rules-routes-and-policies-in-lync-server-2013"></a>Lync Server 2013에서 음성 규칙, 경로 및 정책 테스트

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
<p>Windows PowerShell의 원격 인스턴스를 사용 하 여 실행 하는 경우 CsVoiceUser cmdlet을 실행 하는 권한이 있는 RBAC 역할을 사용자에 게 할당 해야 합니다. 이 cmdlet을 사용할 수 있는 모든 RBAC 역할의 목록을 보려면 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.</p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoiceUser&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>설명

사용자가 전화를 걸 때 통화가 목적지에 도달 하기 위해 수행 하는 경로는 해당 사용자에 게 할당 된 정책 및 다이얼 플랜에 따라 달라 집니다. 사용자의 SIP 주소와 전화 번호를 지정 하면 CsVoiceUser cmdlet은 해당 번호에 대 한 통화를 완료할 수 있는지 여부를 확인 합니다. 테스트에 성공 하면 CsVoiceUser에서 다음을 반환 합니다.

  - 사용자의 다이얼 플랜에 따라 E. 164 형식으로 변환 되는 숫자입니다.

  - 해당 변환을 제공한 정규화 규칙입니다.

  - 경로 우선 순위에 따라 사용 되는 음성 경로

  - 사용자의 음성 정책을 음성 경로에 연결한 전화 사용입니다.

CsVoiceUser를 사용 하면 특정 전화 번호가 예상 대로 경로 지정 되 고 변환 되는지 여부를 확인 하 고 개별 사용자가 경험 하는 통화 관련 문제를 해결 하는 데 도움이 될 수 있습니다.

</div>

<div>

## <a name="running-the-test"></a>테스트 실행

CsVoiceUser cmdlet을 실행 하는 경우 전화를 거는 번호 (DialedNumber) 및 테스트할 사용자 계정의 Id 라는 두 가지 정보를 제공 해야 합니다. 예를 들어이 명령은 SIP 주소 sip:kenmyer@litwareinc.com 사용자가 전화 번호 + 1206555-1219에 대 한 호출을 수행 하도록 하는 기능을 테스트 합니다.

`Test-CsVoiceUser -DialedNumber "12065551219" -SipUri "sip:kenmyer@litwareinc.com"`

전화 번호를 지정 하는 방법에 맞는 형식으로 설정 해야 합니다. 예를 들어 사용자가 시외 전화를 걸기 전에 1을 전화를 걸지 않으면 다음 형식을 사용 해야 합니다.

`-DialedNumber "2065551219"`

물론이 경우 숫자 2065551219을 Lync Server에서 사용 되는 E. 164 전화 형식으로 올바르게 변환할 수 있는 정규화 규칙이 없는 경우에는 테스트가 실패 합니다. 자세한 내용은 Get-csvoicenormalizationrule cmdlet에 대 한 도움말 항목을 참조 하십시오.

각 사용자 계정에 대해 이와 동일한 테스트를 실행 하려는 경우에는 다음과 같은 명령을 사용할 수 있습니다.

`Get-CsUser | ForEach-Object {$_.DisplayName; Test-CsVoiceUser -DialedNumber "+12065551219" -SipUri $_.SipAddress} | Format-List`

자세한 내용은 CsVoiceUser cmdlet에 대 한 도움말 설명서를 참조 하십시오.

</div>

<div>

## <a name="determining-success-or-failure"></a>성공 또는 실패 확인

테스트가 성공적으로 완료 되 면 (즉, 사용자가 지정 된 번호로 전화를 걸 수 있는 경우) 출력에는 변환 된 전화 번호와 일치 하는 정규화 규칙 및 음성 경로와 같은 정보가 표시 됩니다.

TranslatedNumber    MatchingRule    FirstMatchingRoute    MatchingUsage

\----------------    ------------    ------------------    -------------

\+12065551219 Descripti    LocalRoute 로컬

Windows PowerShell 화면의 제한 사항으로 인해 적어도 일부 반환 된 정보 (일치 하는 정규화 규칙에 대 한 전체 설명)가 화면에 표시 되지 않을 수 있습니다. 테스트의 성공 또는 실패에만 관심이 있는 경우에는 문제가 없는 것입니다. 반환 된 데이터에 대 한 자세한 내용을 보려면 테스트를 실행할 때 Format cmdlet에 출력을 파이프 합니다.

`Test-CsVoiceUser -DialedNumber "+12065551219" -SipUri "sip:kenmyer@litwareinc.com" -Verbose | Format-List`

그러면 다음과 같은 읽기 쉬운 형식으로 출력을 표시할 수 있습니다.

TranslatedNumber: + 12065551219

MatchingRule: Description =; Pattern = ^ (\\d{11}) $; 번역 = + $1,

Name = All 접두사, IsInternalExtension = False

FirsMatchingRoute: LocalRoute

MatchingUsage: Local

테스트가 실패 하면 CsVoiceUser에서 빈 속성 값 집합을 반환 합니다.

TranslatedNumber MatchingRule FirstMatchingRoute MatchingUsage

\---------------- ------------ ------------------ -------------

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>테스트가 실패 한 이유

CsVoiceUser cmdlet이 실패 하는 이유에는 여러 가지가 있습니다. 제공 된 전화 번호를 변환할 수 있는 정규화 규칙이 없을 수 있습니다. 음성 경로에 문제가 있을 수 있습니다. 해당 사용자에 게 할당 된 다이얼 플랜에 대 한 구성 문제가 있을 수 있습니다. 따라서 CsVoiceUser cmdlet을 실행 하는 경우 Verbose 매개 변수를 포함할 수 있습니다.

`Test-CsVoiceUser -DialedNumber "+12065551219" -SipUri "sip:kenmyer@litwareinc.com" -Verbose`

자세한 정보 표시 cmdlet이 포함 된 경우 CsVoiceUser에서는 검사를 수행할 때 수행 되는 모든 단계의 자세한 계정을 발급 합니다. 예를 들어 다음과 같은 단계를 볼 수 있습니다. 

VERBOSE: id가 "sip:kenmyer@litwareinc.com" 인 사용자 찾기

VERBOSE: 다이얼 플랜 로드: "RedmondDialPlan"

이 추가 정보는 오류의 원인을 정확 하 게 파악 하기 위해 수행할 수 있는 단계에 대 한 힌트를 제공할 수 있습니다. 예를 들어 여기에 표시 된 자세한 정보 출력은 테스트 중인 사용자에 게 다이얼 플랜 RedmondDialPlan이 할당 되었음을 알려 줍니다. 테스트가 실패 한 후에는 RedmondDialPlan에서 제공 된 전화 번호를 변환할 수 있는지 확인 하는 논리적 다음 단계를 수행 합니다.

</div>

<div>

## <a name="see-also"></a>참고 항목


[CsVoiceUser](https://docs.microsoft.com/powershell/module/skype/Test-CsVoiceUser)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

