---
title: 'Lync Server 2013: 다이얼 플랜 테스트'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing the dial plan
ms:assetid: 70eec03c-aca3-4106-86a7-77ae96b53779
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690130(v=OCS.15)
ms:contentKeyID: 63969616
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0c758f2f16d59db92841a5e7ef727a41cee8a8d4
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48530445"
---
# <a name="testing-the-dial-plan-in-lync-server-2013"></a>Lync Server 2013에서 다이얼 플랜 테스트

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
<p>Windows PowerShell의 원격 인스턴스를 사용 하 여 실행 하는 경우 사용자에 게 Test-CsDialPlan cmdlet을 실행 하는 권한이 있는 RBAC 역할을 할당 해야 합니다. 이 cmdlet을 사용할 수 있는 모든 RBAC 역할의 목록을 보려면 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsDialPlan&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>설명

Test-CsDialPlan cmdlet을 사용 하면 지정 된 전화 번호에 다이얼 플랜을 적용 한 결과를 볼 수 있습니다. 다이얼 플랜은 Enterprise Voice 사용자가 전화를 걸 수 있도록 하는 데 필요한 정규화 규칙 적용 방법 등의 정보를 제공 합니다. 전화 건 번호와 다이얼 플랜이 제공 되 면이 cmdlet은 다이얼 플랜 내에서 적용 되는 정규화 규칙 및 변환 된 번호를 확인 합니다.

이 cmdlet을 사용 하 여 번호 변환과 관련 된 문제를 해결 하거나 특정 번호에 대해 규칙을 적용 하는 방법을 확인할 수 있습니다.

</div>

<div>

## <a name="running-the-test"></a>테스트 실행

Test-CsDialPlan cmdlet을 사용 하려면 두 가지 작업을 수행 해야 합니다. 먼저 테스트할 다이얼 플랜의 인스턴스를 가져와야 합니다. 이 작업은 Get-CsDialPlan cmdlet을 사용 하 여 수행할 수 있습니다. 두 번째로, 정규화 해야 하는 전화 번호를 지정 해야 합니다. 전화 번호에 사용 되는 형식은 사용자가 전화를 걸고 입력 한 번호와 일치 해야 합니다. 예를 들어이 명령은 다이얼 플랜의 인스턴스를 검색 하 여 RedmondDialPlan를 확인 하 고 전화 번호 12065551219 정규화 가능 여부를 검사 합니다.

    Get-CsDialPlan -Identity "RedmondDialPlan" | Test-CsDialPlan -DialedNumber "12065551219" | Format-List

국가 코드 (이 예에서 1)와 지역 번호 (206)를 자동으로 추가 하는 정규화 규칙이 있는 경우 다음과 같이 전화 번호 5551219를 확인 해야 할 수 있습니다.

    Get-CsDialPlan -Identity "RedmondDialPlan" | Test-CsDialPlan -DialedNumber "5551219" | Format-List

자세한 내용은 [테스트-CsDialPlan 플랜](https://docs.microsoft.com/powershell/module/skype/Test-CsDialPlan) cmdlet에 대 한 도움말 설명서를 참조 하십시오.

</div>

<div>

## <a name="determining-success-or-failure"></a>성공 또는 실패 확인

Test-CsDialPlan 대부분의 Lync Server 테스트 cmdlet은 테스트가 성공 했는지 아니면 실패 하는지를 간접적으로 표시 하기 때문에 이와는 다릅니다. Test-CsDialPlan 사용 하는 경우 다음과 유사한 출력이 표시 되 고 결과에 분명 하 게 레이블이 지정 됩니다.

TargetFqdn: atl-cs-001.litwareinc.com

결과: 성공

대기 시간: 00:00:06.8630376

오류

진단을

대신, Test-CsDialPlan에 성공 하면 지정 된 전화 번호를 성공적으로 변환 하 고 사용할 수 있는 정규화 규칙에 대 한 정보를 받게 됩니다.

TranslatedNumber: + 12065551219

MatchingRule: Description =; Pattern = ^ ( \\ d (11)) $; 번역 = + $1,

Name = All 접두사; IsInternalExtension = False

Test-CsDialPlan이 실패 하는 경우 (즉, 다이얼 플랜에 지정 된 전화 번호를 변환할 수 있는 정규화 규칙이 없는 경우) 다음과 같이 "빈" 출력을 받게 됩니다.

TranslatedNumber :

MatchingRule :

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>테스트가 실패 한 이유

Test-CsDialPlan 실패할 수 있는 몇 가지 일반적인 이유는 다음과 같습니다.

  - 전화 번호를 지정할 때 잘못 된 형식을 사용 했을 수 있습니다. 다이얼 플랜에는 Lync Server에서 사용자가 전화를 걸고 입력 한 번호를 번역할 수 있도록 하는 정규화 규칙이 포함 되어 있습니다. 따라서 다이얼 플랜은 사용자가 전화를 걸 가능성이 있는 번호와 일치 하는 정규화 규칙을 가져야 합니다. 예를 들어 사용자가 국가 코드, 지역 번호 및 전화 번호로 전화를 걸 수 있는 경우이는 다이얼 플랜에 다음과 같은 전화 번호를 처리 하기 위한 정규화 규칙이 있어야 함을 의미 합니다.
    
    12065551219
    
    그러나 마지막 숫자를 제외 하 고 잘못 된 전화 번호를 입력 한 경우에는 Test-CsDialPlan가 실패 합니다. 다이얼 플랜에 문제가 있지만 해석할 수 없는 것 보다 전화 번호를 입력 했기 때문입니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

