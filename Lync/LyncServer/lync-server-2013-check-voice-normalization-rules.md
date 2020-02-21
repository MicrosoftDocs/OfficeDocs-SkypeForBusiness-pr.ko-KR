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
ms.openlocfilehash: eca48668bf0a19392558e10366f7a9bf4bb202ce
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42206844"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="check-voice-normalization-rules-in-lync-server-2013"></a>Lync Server 2013에서 음성 정규화 규칙 확인

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
<p>Windows PowerShell의 원격 인스턴스를 사용 하 여 실행 하는 경우 Get-csvoicenormalizationrule cmdlet을 실행 하는 권한이 있는 RBAC 역할을 사용자에 게 할당 해야 합니다. 이 cmdlet을 사용할 수 있는 모든 RBAC 역할의 목록을 보려면 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.</p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoiceNormalizationRule&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>설명

음성 정규화 규칙은 사용자가 전화를 건 전화 번호 (예: 2065551219)를 Lync Server (+ 12065551219)에서 사용 하는 E. 164 형식으로 변환 하는 데 사용 됩니다. 예를 들어 사용자가 국가 코드나 지역 번호 (예: 5551219)를 포함 하지 않고 전화 번호에 전화를 거는 습관을 내는 경우 해당 번호를 E. 164 12065551219 형식으로 변환할 수 있는 음성 정규화 규칙을 사용 해야 합니다. 이러한 규칙을 사용 하지 않으면 사용자가 555-1219를 호출할 수 없게 됩니다.

Get-csvoicenormalizationrule cmdlet은 지정 된 음성 정규화 규칙에서 지정 된 전화 번호를 올바르게 변환할 수 있는지 확인 합니다. 예를 들어이 명령은 전역 정규화 규칙 NoAreaCode가 다이얼 문자열 5551219를 정규화 하 고 변환할 수 있는지 여부를 확인 합니다.

`Get-CsVoiceNormalizationRule -Identity "global/NoAreaCode" | Test-CsVoiceNormalizationRule -DialedNumber "5551219"`

</div>

<div>

## <a name="running-the-test"></a>테스트 실행

Get-csvoicenormalizationrule cmdlet을 실행 하려면 먼저 Get-csvoicenormalizationrule cmdlet을 사용 하 여 테스트 중인 규칙의 인스턴스를 검색 한 다음 해당 인스턴스를 테스트-Get-csvoicenormalizationrule으로 파이프 해야 합니다. 다음과 같은 구문이 작동 하지 않습니다.

Get-csvoicenormalizationrule-DialedNumber "12065551219"-NormalizationRule "global/Prefix All"

대신 Get-csvoicenormalizationrule 및 Get-csvoicenormalizationrule cmdlet을 모두 결합 하는 다음과 같은 구문을 사용 합니다.

Get-csvoicenormalizationrule-Identity "global/Prefix All" | Get-csvoicenormalizationrule-DialedNumber "12065551219"

<div>


> [!NOTE]  
> . 또는이 방법을 사용 하 여 규칙 인스턴스를 검색 한 다음 지정 된 전화 번호에 대해 해당 규칙을 테스트할 수도 있습니다.



</div>

`$x = Get-CsVoiceNormalizationRule -Identity "global/Prefix All"`

`Test-CsVoiceNormalizationRule -DialedNumber "12065551219" -NormalizationRule $x`

전화를 걸 예상 대로 DialedNumber 매개 변수의 값을 정확히 입력 합니다. 예를 들어 지정 된 음성 정규화 규칙에서 국가 코드 (값 12065551219의 초기 1)를 자동으로 추가 해야 하는 경우에는 국가 코드를 남겨 두어야 합니다.

`-DialedNumber "2065551219"`

규칙이 올바르게 구성 된 경우 Lync Server에서 사용 하는 E. 164 형식으로 번호를 변환할 때 국가 코드가 자동으로 추가 됩니다.

자세한 내용은 Get-csvoicenormalizationrule cmdlet에 대 한 도움말 설명서를 참조 하십시오.

</div>

<div>

## <a name="determining-success-or-failure"></a>성공 또는 실패 확인

지정 된 음성 정규화 규칙에서 제공 된 숫자를 변환할 수 있으면 번역 된 번호가 화면에 표시 됩니다.

TranslatedNumber

\----------------

\+12065551219

테스트가 실패 하면 빈 변환 번호가 반환 됩니다.

TranslatedNumber

\----------------

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>테스트가 실패 한 이유

Get-csvoicenormalizationrule에서 변환 된 번호를 반환 하는 경우 지정 된 음성 정규화 규칙에서 제공 된 전화 번호를 Lync Server에서 사용 하는 E. 164 형식으로 변환할 수 없음을 의미 합니다. 확인 하려면 먼저 전화 번호를 올바르게 입력 했는지 확인 합니다. 예를 들어 음성 정규화 규칙은 다음과 같은 숫자를 변환 하는 데 문제가 있을 수 있습니다.

`-DialedNumber "1"`

번호를 올바르게 입력 했다고 가정 하 고 다음 단계는 지정 된 정규화 규칙이 해당 전화 번호를 처리 하도록 설계 되었는지 확인 하는 것입니다. 예를 들어 하나의 정규화 규칙은 12065551219 형식을 처리 하도록 설계 되었지만 두 번째 규칙은 숫자 2065551219를 처리 하도록 설계 될 수 있습니다. (전화 번호와 같으며, 국가 코드 1을 제외 하 고 맨 처음에는 동일 합니다.) 음성 정규화 규칙에 대 한 자세한 정보를 반환 하려면 다음과 같은 명령을 실행 합니다.

`Get-CsVoiceNormalizationRule -Identity "global/Prefix All" | Format-List`

모든 음성 정규화 규칙에 대 한 자세한 정보를 반환 하려면 대신 다음 명령을 실행 합니다.

`Get-CsVoiceNormalizationRule | Format-List`

</div>

<div>

## <a name="see-also"></a>참고 항목


[Get-csvoicenormalizationrule](https://docs.microsoft.com/powershell/module/skype/Test-CsVoiceNormalizationRule)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

