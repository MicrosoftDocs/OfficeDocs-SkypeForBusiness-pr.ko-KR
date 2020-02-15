---
title: 'Lync Server 2013: 음성 정책에 대해 전화 번호 테스트'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test telephone number against a voice policy
ms:assetid: 30c51700-17c6-4c57-891a-8d5ec30b50ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725207(v=OCS.15)
ms:contentKeyID: 63969596
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a234419dc6f06ae9bdc8d7c198873bdc3c706701
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2020
ms.locfileid: "41985093"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-telephone-number-against-a-voice-policy-in-lync-server-2013"></a>Lync Server 2013의 음성 정책에 대해 전화 번호 테스트

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
<p>Windows PowerShell의 원격 인스턴스를 사용 하 여 실행 하는 경우 Set-csvoicepolicy cmdlet을 실행 하는 권한이 있는 RBAC 역할을 사용자에 게 할당 해야 합니다. 이 cmdlet을 사용할 수 있는 모든 RBAC 역할의 목록을 보려면 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.</p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoicePolicy&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>설명

Enterprise Voice 사용자가 다음 세 가지 작업을 통해 대규모의 PSTN (공중 전화망) 힌지를 통해 나가는 전화 통화를 수행할 수 있는 기능입니다.

  - 사용자에 게 할당 된 음성 정책

  - Lync Server에서 PSTN 네트워크로 통화를 라우팅하는 데 사용 되는 음성 경로입니다.

  - PSTN 사용 (음성 정책을 음성 경로에 연결 하는 Lync Server 속성)입니다.

PSTN 사용은 특히 중요 한 음성 정책을 음성 경로에 연결 하는 속성입니다. (음성 정책 및 음성 경로는 하나 이상의 PSTN 사용량이 공통으로 있는 경우 연결 되었다고 말합니다.) 음성 정책은 PSTN 사용을 지정 하지 않고 구성할 수 있습니다. 이 경우 해당 정책이 할당 된 사용자가 PSTN 네트워크를 통해 발신 전화를 걸 수 없습니다. 마찬가지로 지정 된 PSTN 사용량이 하나 이상 없는 음성 경로는 통화를 PSTN 네트워크로 라우팅할 수 없습니다.

Set-csvoicepolicy cmdlet은 지정 된 음성 정책에 PSTN 사용이 있는지 확인 하 고, 하나 이상의 음성 경로를 통해 사용을 공유 합니다. Set-csvoicepolicy에서 실행 하는 확인이 성공 하면 cmdlet은 찾은 첫 번째 유효한 음성 경로의 이름 및 정책을 경로에 연결 하는 PSTN 사용 이름도 보고 합니다.

</div>

<div>

## <a name="running-the-test"></a>테스트 실행

Set-csvoicepolicy cmdlet을 실행 하려면 먼저 Set-csvoicepolicy cmdlet을 사용 하 여 테스트할 음성 정책의 인스턴스를 검색 해야 합니다. 그런 다음 해당 인스턴스를 Set-csvoicepolicy으로 파이프 해야 합니다. 예:

`Get-CsVoicePolicy -Identity "Global" | Test-CsVoicePolicy -TargetNumber "+12065551219"`

음성 정책 인스턴스를 검색 하기 위해 Set-csvoicepolicy를 사용 하지 않는이 명령은 실패 합니다.

`Test-CsVoicePolicy -TargetNumber "+12065551219" -VoicePolicy "Global"`

지정 된 전화 번호에 대해 모든 음성 정책을 확인 하려면 다음과 같은 명령을 사용 합니다.

`Get-CsVoicePolicy | Test-CsVoicePolicy -TargetNumber "+12065551219"`

TargetNumber는 E. 164 형식을 사용 하 여 지정 해야 합니다. Set-csvoicepolicy은 전화 번호를 정규화 하거나 E. 164 형식으로 변환 하지 않습니다.

자세한 내용은 Set-csvoicepolicy cmdlet에 대 한 도움말 설명서를 참조 하십시오.

</div>

<div>

## <a name="determining-success-or-failure"></a>성공 또는 실패 확인

음성 정책이 일치 하는 음성 경로 및 일치 하는 PSTN 사용을 찾을 수 있으면 경로와 사용 현황이 모두 화면에 표시 됩니다.

FirstMatchingRoute MatchingUsage

\------------------ -------------

RedmondVoiceRoute RedmondPstnUsage

적절 한 음성 경로 또는 적절 한 PSTN 사용을 찾을 수 없는 경우 빈 속성 값이 화면에 표시 됩니다.

FirstMatchingRoute MatchingUsage

\------------------ -------------

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>테스트가 실패 한 이유

Set-csvoicepolicy에서 일치 하는 항목을 반환 하지 않으면 음성 정책이 음성 경로와 함께 PSTN 사용을 공유 하지 않는 것을 의미할 수 있습니다. 이를 확인 하려면 다음과 같은 cmdlet을 사용 하 여 음성 정책에 할당 된 PSTN 사용법을 확인 합니다.

`Get-CsVoicePolicy -Identity "Global" | Select-Object PstnUsages | Format-List`

다음으로, 다음 명령을 실행 하 여 각 음성 경로에 대 한 PSTN 사용 할당을 확인 합니다.

`Get-CsVoiceRoute | Select-Object Identity, PstnUsages`

일치 하는 항목이 표시 되는 경우 즉, 음성 정책을 사용 하 여 하나 이상의 음성 경로를 공유 하는 경우에는 Get-csvoiceroute cmdlet을 실행 하 여 음성 경로에서 제공 된 전화 번호로 전화를 걸 수 있는지 확인 해야 합니다.

</div>

<div>

## <a name="see-also"></a>참고 항목


[Set-csvoicepolicy](https://docs.microsoft.com/powershell/module/skype/Test-CsVoicePolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

