---
title: 'Lync Server 2013: 음성 정규화 규칙 확인'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Check voice normalization rules
ms:assetid: bf71a218-71cd-4b64-b8e8-b3a98b6e87a2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725212(v=OCS.15)
ms:contentKeyID: 63969649
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 04e383f38d5af6f106354a766c857635bcd87eb3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733868"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="check-voice-normalization-rules-in-lync-server-2013"></a>Lync Server 2013에서 음성 표준화 규칙 확인

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
<p>Windows PowerShell의 원격 인스턴스를 사용 하 여 실행 하는 경우 CsVoiceNormalizationRule cmdlet을 실행 하는 데 필요한 권한이 있는 RBAC 역할을 사용자에 게 할당 해야 합니다. 이 cmdlet을 사용할 수 있는 모든 RBAC 역할 목록을 보려면 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.</p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoiceNormalizationRule&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>설명

음성 표준화 규칙은 사용자가 전화를 거는 전화 번호 (예: 2065551219)를 Lync Server에서 사용 하는 E-164 형식으로 변환 하는 데 사용 됩니다 (+ 12065551219). 예를 들어 사용자가 국가 코드나 지역 번호 (예: 5551219)를 포함 하지 않고 전화 번호를 사용 하는 습관을 사용 하는 경우에는 해당 번호를 E-164 형식: + 12065551219로 변환할 수 있는 음성 정규화 규칙이 있어야 합니다. 이러한 규칙이 없으면 사용자는 555-1219를 호출할 수 없습니다.

CsVoiceNormalizationRule cmdlet은 지정 된 음성 표준화 규칙이 지정 된 전화 번호를 성공적으로 변환할 수 있는지 확인 합니다. 예를 들어이 명령은 전역 정규화 규칙 NoAreaCode에서 다이얼 문자열 5551219을 표준화 하 고 변환할 수 있는지 여부를 확인 합니다.

`Get-CsVoiceNormalizationRule -Identity "global/NoAreaCode" | Test-CsVoiceNormalizationRule -DialedNumber "5551219"`

</div>

<div>

## <a name="running-the-test"></a>테스트 실행

CsVoiceNormalizationRule cmdlet을 실행 하려면 먼저 Get-CsVoiceNormalizationRule cmdlet을 사용 하 여 테스트할 규칙의 인스턴스를 검색 한 다음 해당 인스턴스를 테스트-CsVoiceNormalizationRule에 파이프 합니다. 다음과 같은 구문은 작동 하지 않습니다.

테스트-CsVoiceNormalizationRule-DialedNumber "12065551219"-NormalizationRule "global/Prefix All"

대신 CsVoiceNormalizationRule 및 Test-CsVoiceNormalizationRule cmdlet을 모두 결합 하는 다음과 같은 구문을 사용 하세요.

Get-CsVoiceNormalizationRule-Id "global/Prefix All" | 테스트-CsVoiceNormalizationRule-DialedNumber "12065551219"

<div>


> [!NOTE]  
> . 또는이 방법을 사용 하 여 규칙의 인스턴스를 검색 한 다음 지정 된 전화 번호에 대해 해당 규칙을 테스트할 수도 있습니다.



</div>

`$x = Get-CsVoiceNormalizationRule -Identity "global/Prefix All"`

`Test-CsVoiceNormalizationRule -DialedNumber "12065551219" -NormalizationRule $x`

DialedNumber 매개 변수에 대 한 값을 정확 하 게 입력 하 여 원하는 번호로 전화를 겁니다. 예를 들어 지정 된 음성 정규화 규칙에서 국가 코드 (값 12065551219의 초기 1)를 자동으로 추가 해야 하는 경우 국가 코드를 종료 합니다.

`-DialedNumber "2065551219"`

규칙이 올바르게 구성 되 면 Lync Server에서 사용 하는 해당 번호를 E-164 형식으로 변환할 때 국가 코드가 자동으로 추가 됩니다.

자세한 내용은 테스트 CsVoiceNormalizationRule cmdlet에 대 한 도움말 문서를 참조 하세요.

</div>

<div>

## <a name="determining-success-or-failure"></a>성공 또는 실패 확인

지정 된 음성 표준화 규칙에서 제공 된 숫자를 변환할 수 있는 경우 번역 된 번호가 화면에 표시 됩니다.

TranslatedNumber

\----------------

\+12065551219

테스트에 실패 하면 빈 번역 번호가 반환 됩니다.

TranslatedNumber

\----------------

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>테스트가 실패할 수 있는 이유

테스트-CsVoiceNormalizationRule가 번역 된 숫자를 반환 하는 경우 지정 된 음성 표준화 규칙에서 제공 된 전화 번호를 Lync Server에서 사용 하는 전자 164 형식으로 변환할 수 없음을 의미 합니다. 이를 확인 하려면 먼저 전화 번호를 올바르게 입력 했는지 확인 합니다. 예를 들어 음성 표준화 규칙에 다음과 같은 번호를 번역 하는 데 문제가 있는 것으로 예상 됩니다.

`-DialedNumber "1"`

숫자가 올바르게 입력 되었다고 가정 하 고 다음 단계는 지정 된 정규화 규칙이 해당 전화 번호를 처리 하도록 디자인 되었는지 확인 하는 것입니다. 예를 들어 12065551219 형식을 처리 하도록 한 정규화 규칙을 디자인할 수 있지만 두 번째 규칙은 숫자 2065551219을 처리 하도록 디자인 될 수 있습니다. (맨 앞에 국가 코드 1을 제외한 전화 번호입니다.) 음성 정규화 규칙에 대 한 자세한 정보를 반환 하려면 다음과 같은 명령을 실행 합니다.

`Get-CsVoiceNormalizationRule -Identity "global/Prefix All" | Format-List`

모든 음성 정규화 규칙에 대 한 자세한 정보를 반환 하려면 대신이 명령을 실행 합니다.

`Get-CsVoiceNormalizationRule | Format-List`

</div>

<div>

## <a name="see-also"></a>참고 항목


[테스트-CsVoiceNormalizationRule](https://docs.microsoft.com/powershell/module/skype/Test-CsVoiceNormalizationRule)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

