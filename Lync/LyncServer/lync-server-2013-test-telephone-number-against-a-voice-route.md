---
title: 'Lync Server 2013: 음성 경로에 대해 전화 번호 테스트'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Test telephone number against a voice route
ms:assetid: 9a77ed6d-9394-4bef-9344-3d91b6959b97
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725211(v=OCS.15)
ms:contentKeyID: 63969631
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ed50971c9656d454a44eeee627de95c187ef008f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979080"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-telephone-number-against-a-voice-route-in-lync-server-2013"></a>Lync Server 2013에서 음성 경로에 대해 전화 번호 테스트

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
<p>Windows PowerShell의 원격 인스턴스를 사용 하 여 실행 하는 경우 CsVoiceRoute cmdlet을 실행 하는 데 필요한 권한이 있는 RBAC 역할을 사용자에 게 할당 해야 합니다. 이 cmdlet을 사용할 수 있는 모든 RBAC 역할 목록을 보려면 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.</p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoiceRoute&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>설명

음성 경로는 음성 정책으로 함께 작동 하 여 PSTN 네트워크로 엔터프라이즈 음성 통화를 라우팅할 수 있도록 합니다. 각 음성 경로에는 지정 된 음성 경로를 통해 라우팅되는 전화 번호를 식별 하는 정규식 (숫자 패턴)이 포함 됩니다. 경로는이 정규식과 일치 하는 전화 번호를 처리할 수 있습니다. 예를 들어 음성 경로에는 10 자리 숫자를 처리할 수 있는 정규식이 있을 수 있습니다. 즉, 경로는 다음과 같은 전화 번호를 처리할 수 있습니다.

  - 2065551219

경로는 다음 두 숫자 중 하나를 처리할 수 없으며, 둘 다 10 자리입니다.

  - 5551219

  - 12065551219

CsVoiceRoute cmdlet은 지정 된 음성 경로에서 지정한 전화 번호를 라우팅할 수 있는지 여부를 확인 합니다.

</div>

<div>

## <a name="running-the-test"></a>테스트 실행

지정 된 전화 번호를 라우팅하는 데 사용할 음성 경로의 기능을 확인 하는 과정은 2 단계입니다. 먼저 CsVoiceRoute cmdlet을 사용 하 여 해당 음성 경로의 인스턴스를 반환 하 고 CsVoiceRoute cmdlet을 사용 하 여 해당 경로의 대상 전화 번호를 처리할 수 있는지 확인 해야 합니다. 예를 들어이 명령은 RedmondVoiceRoute 음성 경로가 전화 번호 2065551219를 라우팅할 수 있는지 여부를 확인 합니다.

`Get-CsVoiceRoute -Identity "RedmondVoiceRoute" | Test-CsVoiceRoute -TargetNumber "2065551219"`

사용자가 해당 번호로 전화를 걸 것으로 예상 되는 전화 번호를 입력 해야 합니다. 예를 들어 사용자에 게 전화를 걸 때 국가 코드와 지역 번호를 포함 하는 것이 아니면 다음과 같은 구문을 사용 합니다.

`-TargetNumber "5551219"`

이 경우 대상 번호는 국가 코드와 지역 번호를 모두 벗어납니다.

단일 명령을 사용 하 여 지정 된 대상 번호에 대 한 모든 음성 경로를 테스트 하려면 다음과 같은 구문을 사용 합니다.

`Get-CsVoiceRoute | Test-CsVoiceRoute -TargetNumber "2065551219"`

자세한 내용은 테스트 CsVoiceRoute cmdlet에 대 한 도움말 문서를 참조 하세요.

</div>

<div>

## <a name="determining-success-or-failure"></a>성공 또는 실패 확인

음성 경로에서 대상 전화 번호를 라우팅할 수 있는 경우 CsVoiceRoute cmdlet은 True 값만 반환 합니다.

MatchesPattern

\--------------

False

즉, 경로는 대상 번호와 비슷한 숫자를 처리할 수 있습니다. 음성 경로에서 대상 번호를 처리할 수 없는 경우 CsVoiceRoute는 False 값을 반환 합니다.

MatchesPattern

\--------------

해제

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>테스트가 실패할 수 있는 이유

음성 경로를 테스트할 때 "실패"는 관련 용어입니다. 이 경우 경로가 "끊어짐" 이라는 의미는 아니며, 경로가 대상 번호를 처리할 수 없음을 의미 합니다. 음성 경로가 올바르게 구성 되지 않았습니다. 또한 경로가이 패턴을 사용 하 여 숫자를 처리 하도록 의도 되지 않았음을 의미할 수 있습니다. 예를 들어 국가 코드를 포함 하는 모든 전화 번호를 거부 하도록 경로를 구성할 수 있는 지정 된 경로를 통해 다른 국가에 대 한 통화를 라우팅 하지 않으려는 경우 테스트-CsVoiceRoute에서 True를 반환 하는 경우 False를 반환 하는 경우 대상 번호를 올바르게 입력 했는지 확인 합니다. 이 경우 다음과 유사한 명령을 사용 하 여 경로에 대해 구성 된 번호 패턴을 봅니다.

`Get-CsVoiceRoute -Identity "RedmondVoiceRoute" | Select-Object NumberPattern`

</div>

<div>

## <a name="see-also"></a>참고 항목


[테스트-CsVoiceRoute](https://docs.microsoft.com/powershell/module/skype/Test-CsVoiceRoute)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

