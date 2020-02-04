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
ms.openlocfilehash: 37d0c9ae6512cb7755c7ef73e4cfd3e37b92884d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746198"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-telephone-number-against-a-voice-policy-in-lync-server-2013"></a>Lync Server 2013에서 음성 정책에 대해 전화 번호 테스트

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
<p>Windows PowerShell의 원격 인스턴스를 사용 하 여 실행 하는 경우 CsVoicePolicy cmdlet을 실행 하는 데 필요한 권한이 있는 RBAC 역할을 사용자에 게 할당 해야 합니다. 이 cmdlet을 사용할 수 있는 모든 RBAC 역할 목록을 보려면 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.</p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoicePolicy&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>설명

기업 음성 사용자는 다음 세 가지 사항에 따라 대규모의 PSTN (공개 통신 네트워크) 힌지 (hinge)를 통해 나가는 전화 통화를 할 수 있습니다.

  - 사용자에 게 할당 된 음성 정책.

  - Lync Server에서 PSTN 네트워크로 통화를 라우팅하는 데 사용 되는 음성 경로입니다.

  - PSTN 사용으로 음성 경로를 음성에 연결 하는 Lync Server 속성입니다.

PSTN 사용은 특히 중요 한 음성 정책에 음성 경로를 연결 하는 속성입니다. (음성 정책 및 음성 경로는 하나 이상의 PSTN 사용량이 공통으로 있는 경우 연결 되었다고 말합니다.) 음성 정책은 PSTN 사용을 지정 하지 않고 구성할 수 있습니다. 이 경우 해당 정책을 할당 받은 사용자는 PSTN 네트워크를 통해 발신 전화를 할 수 없습니다. 마찬가지로, 하나 이상의 지정 된 PSTN 사용이 없는 음성 경로는 PSTN 네트워크로 전화를 라우팅할 수 없습니다.

CsVoicePolicy cmdlet은 지정 된 음성 정책에 PSTN 사용이 있는지 확인 하 고 하나 이상의 음성 경로에 따라 사용이 공유 되는지 여부를 검사 합니다. 테스트를 CsVoicePolicy에서 실행 하는 경우 cmdlet은 발견 한 첫 번째 유효한 음성 경로의 이름을 보고 하 고 정책을 경로에 연결 하는 PSTN 사용의 이름을 확인 합니다.

</div>

<div>

## <a name="running-the-test"></a>테스트 실행

테스트 CsVoicePolicy cmdlet을 실행 하려면 먼저 Get-CsVoicePolicy cmdlet을 사용 하 여 테스트할 음성 정책의 인스턴스를 검색 해야 합니다. 그런 다음 해당 인스턴스를 테스트-CsVoicePolicy로 파이프라인 해야 합니다. 예를 들면 다음과 같습니다.

`Get-CsVoicePolicy -Identity "Global" | Test-CsVoicePolicy -TargetNumber "+12065551219"`

이 명령은 CsVoicePolicy를 사용 하 여 음성 정책 인스턴스를 검색 하지 않으므로 실패 합니다.

`Test-CsVoicePolicy -TargetNumber "+12065551219" -VoicePolicy "Global"`

지정 된 전화 번호에 대 한 모든 음성 정책을 확인 하려면 다음과 같은 명령을 사용 합니다.

`Get-CsVoicePolicy | Test-CsVoicePolicy -TargetNumber "+12065551219"`

TargetNumber는 E 164 형식을 사용 하 여 지정 해야 합니다. CsVoicePolicy 형식으로 전화 번호를 정규화 하거나 번역 하는 것은 테스트를 시도 하지 않습니다.

자세한 내용은 테스트 CsVoicePolicy cmdlet에 대 한 도움말 문서를 참조 하세요.

</div>

<div>

## <a name="determining-success-or-failure"></a>성공 또는 실패 확인

음성 정책에서 일치 하는 음성 경로와 일치 하는 PSTN 사용을 찾을 수 있는 경우 경로와 사용이 모두 화면에 표시 됩니다.

FirstMatchingRoute MatchingUsage

\------------------ -------------

RedmondVoiceRoute RedmondPstnUsage

적절 한 음성 경로 또는 적절 한 PSTN 사용을 찾을 수 없는 경우 빈 속성 값이 화면에 표시 됩니다.

FirstMatchingRoute MatchingUsage

\------------------ -------------

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>테스트가 실패할 수 있는 이유

테스트-CsVoicePolicy가 일치 하는 항목을 반환 하지 않으면 음성 정책에서 음성 경로를 사용 하 여 PSTN 사용을 공유 하지 않는다는 의미입니다. 이를 확인 하려면 다음과 같은 cmdlet을 사용 하 여 음성 정책에 할당 된 PSTN 사용량을 확인 합니다.

`Get-CsVoicePolicy -Identity "Global" | Select-Object PstnUsages | Format-List`

다음으로이 명령을 실행 하 여 각 음성 경로에 대 한 PSTN 용도 할당을 확인 합니다.

`Get-CsVoiceRoute | Select-Object Identity, PstnUsages`

일치 하는 항목이 표시 되는 경우 (즉, 음성 경로에 하나 이상의 PSTN 사용량을 공유 하는 하나 이상의 음성 경로가 표시 되는 경우) CsVoiceRoute cmdlet을 실행 하 여 음성 경로가 제공 된 전화 번호로 전화를 걸 수 있는지 확인 해야 합니다.

</div>

<div>

## <a name="see-also"></a>참고 항목


[테스트-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/Test-CsVoicePolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

