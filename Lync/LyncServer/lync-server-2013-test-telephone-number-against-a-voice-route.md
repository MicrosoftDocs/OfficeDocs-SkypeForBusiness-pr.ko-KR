---
title: 'Lync Server 2013: 음성 경로에 대 한 전화 번호 테스트'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test telephone number against a voice route
ms:assetid: 9a77ed6d-9394-4bef-9344-3d91b6959b97
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725211(v=OCS.15)
ms:contentKeyID: 63969631
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5476d47d0aac550d048e35e617d6d342084ccd75
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42194541"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="test-telephone-number-against-a-voice-route-in-lync-server-2013"></a>Lync Server 2013에서 음성 경로에 대 한 전화 번호 테스트

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
<p>Windows PowerShell의 원격 인스턴스를 사용 하 여 실행 하는 경우 Get-csvoiceroute cmdlet을 실행 하는 권한이 있는 RBAC 역할을 사용자에 게 할당 해야 합니다. 이 cmdlet을 사용할 수 있는 모든 RBAC 역할의 목록을 보려면 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.</p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoiceRoute&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>설명

음성 경로는 회사 음성 통화를 PSTN 네트워크로 라우팅하기 위해 음성 정책과 함께 작동 합니다. 각 음성 경로에는 지정 된 음성 경로를 통해 라우팅되는 전화 번호를 식별 하는 정규식 (숫자 패턴)이 포함 됩니다. 경로는이 정규식과 일치 하는 전화 번호를 처리할 수 있습니다. 예를 들어 음성 경로에는 10 자리 숫자를 처리할 수 있는 정규식이 있을 수 있습니다. 즉, 경로는 다음과 같은 전화 번호를 처리할 수 있습니다.

  - 2065551219

경로는 다음 두 숫자 중에서 하나를 처리할 수 없으며 이러한 값은 10 자리 숫자이 아닙니다.

  - 5551219

  - 12065551219

Get-csvoiceroute cmdlet은 지정한 음성 경로에서 지정 된 전화 번호를 라우트할 수 있는지 여부를 확인 합니다.

</div>

<div>

## <a name="running-the-test"></a>테스트 실행

음성 경로에서 지정 된 전화 번호를 라우팅하는 기능이 두 단계로 진행 되는지 확인 합니다. 먼저 Get-csvoiceroute cmdlet을 사용 하 여 해당 음성 경로의 인스턴스를 반환한 다음 Get-csvoiceroute cmdlet을 사용 하 여 해당 경로의 대상 전화 번호를 처리할 수 있는지 확인 해야 합니다. 예를 들어이 명령은 RedmondVoiceRoute 음성 경로에서 전화 번호 2065551219를 라우팅할 수 있는지 여부를 확인 합니다.

`Get-CsVoiceRoute -Identity "RedmondVoiceRoute" | Test-CsVoiceRoute -TargetNumber "2065551219"`

사용자가 전화를 걸 수 있는 것으로 예상 되는 전화 번호를 입력 해야 합니다. 예를 들어 전화를 걸 때 국가 코드와 지역 번호를 포함 하지 않을 것으로 예상 되 면 다음과 같은 구문을 사용 합니다.

`-TargetNumber "5551219"`

이 경우 대상 번호에 국가 코드와 지역 코드가 모두 표시 됩니다.

단일 명령을 사용 하 여 지정 된 대상 번호에 대 한 모든 음성 경로를 테스트 하려면 다음과 같은 구문을 사용 합니다.

`Get-CsVoiceRoute | Test-CsVoiceRoute -TargetNumber "2065551219"`

자세한 내용은 Get-csvoiceroute cmdlet에 대 한 도움말 설명서를 참조 하십시오.

</div>

<div>

## <a name="determining-success-or-failure"></a>성공 또는 실패 확인

음성 경로에서 대상 전화 번호를 라우팅할 수 있는 경우 Get-csvoiceroute cmdlet은 True 값을 반환 합니다.

MatchesPattern

\--------------

참

즉, 경로는 대상 번호와 비슷한 숫자를 처리할 수 있습니다. 음성 경로에서 대상 번호를 처리할 수 없는 경우 Get-csvoiceroute는 False 값을 반환 합니다.

MatchesPattern

\--------------

False

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>테스트가 실패 한 이유

음성 경로를 테스트할 때는 "실패"가 상대 용어입니다. 이 경우에는 경로가 "끊어짐;" 이라는 의미는 아니므로 경로에서 대상 번호를 처리할 수 없다는 것을 의미 합니다. 음성 경로가 잘못 구성 되었기 때문일 수 있습니다. 또한 경로는이 패턴을 사용 하 여 숫자를 처리 하도록 의도 된 것이 아닙니다. 예를 들어 국가 코드를 포함 하는 모든 전화 번호를 거부 하도록 경로 지정 된 경로를 통해 다른 국가에 대 한 통화를 라우팅 하지 않으려는 경우 Get-csvoiceroute가 True를 반환 하는 경우 False가 반환 되 면 대상 번호를 올바르게 입력 했는지 확인 합니다. 이 경우에는 다음과 같은 명령을 사용 하 여 경로에 대해 구성 된 번호 패턴을 확인 합니다.

`Get-CsVoiceRoute -Identity "RedmondVoiceRoute" | Select-Object NumberPattern`

</div>

<div>

## <a name="see-also"></a>참고 항목


[Get-csvoiceroute](https://docs.microsoft.com/powershell/module/skype/Test-CsVoiceRoute)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

