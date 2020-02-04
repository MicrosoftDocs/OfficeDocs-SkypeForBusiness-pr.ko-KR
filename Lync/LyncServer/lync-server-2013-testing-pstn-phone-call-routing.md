---
title: 'Lync Server 2013: PSTN 전화 통화 라우팅 테스트'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing PSTN phone call routing
ms:assetid: 301dd44d-03e9-41cd-9722-54e00365aa45
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727302(v=OCS.15)
ms:contentKeyID: 63969598
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2dabe54fb2ba4df864d172015efb62ef161c77cb
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745598"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-pstn-phone-call-routing-in-lync-server-2013"></a>Lync Server 2013에서 PSTN 전화 통화 라우팅 테스트

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2014-11-01_


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>확인 일정</p></td>
<td><p>Daily</p></td>
</tr>
<tr class="even">
<td><p>테스트 도구</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>권한이 필요 함</p></td>
<td><p>Lync Server Management Shell을 사용 하 여 로컬에서 실행 되는 경우 사용자는 RTCUniversalServerAdmins 보안 그룹의 구성원 이어야 합니다.</p>
<p>Windows PowerShell의 원격 인스턴스를 사용 하 여 실행 하는 경우 <strong>CsInterTrunkRouting</strong> cmdlet을 실행 하는 데 필요한 권한이 있는 RBAC 역할을 사용자에 게 할당 해야 합니다. 이 cmdlet을 사용할 수 있는 모든 RBAC 역할 목록을 보려면 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsInterTrunkRouting&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>설명

**CsInterTrunkRouting** cmdlet은 한 SIP에서 다른 통화로 통화를 라우팅할 수 있는지 확인 합니다. 이를 위해 cmdlet에는 전화 번호와 트렁크 구성이 제공 됩니다. 그런 다음 **CsInterTrunkRouting** 는 지정 된 번호에 대해 일치 하는 경로 및 일치 하는 PSTN 용도를 보고 합니다. Trunks에 지정 된 전화 번호와 일치 하는 숫자 패턴이 있고 trunks에서 하나 이상의 PSTN 사용을 공유 하는 경우에만 trunks 간에 호출을 라우팅할 수 있습니다.

</div>

<div>

## <a name="running-the-test"></a>테스트 실행

아래 표시 된 명령은 사용자가 Redmond 사이트의 트렁크 구성 설정을 사용 하 여 전화 번호 1-206-555-1219에 통화할 수 있도록 일치 하는 경로 및 일치 하는 전화를 반환 합니다.

    $trunk = Get-CsTrunkConfiguration -Identity "site:Redmond"
    
    Test-CsInterTrunkRouting -TargetNumber "tel:+12065551219" -TrunkConfiguration $trunk

</div>

<div>

## <a name="determining-success-or-failure"></a>성공 또는 실패 확인

한 SIP에서 다른 통화로 통화를 라우팅할 수 있는 경우 다음과 유사한 출력이 표시 됩니다.

FirstMatchingRoute MatchingUsage MatchingRoutes

\------------------ ------------- --------------

RedmondRoute LocalUsage {RedmondRoute}

테스트에 실패 하면 다음과 같은 출력이 표시 됩니다.

테스트-CsInterTrunkRouting: 매개 변수에서 인수 변환을 처리할 수 없음

'TrunkConfiguration'. 잘못 된 TrunkConfigurationsetting (매개 변수). 를 지정 합니다.

올바른 설정 (매개 변수)을 선택한 다음 다시 시도 하세요.

줄: 1 char: 79

\+테스트-CsInterTrunkRouting-TargetNumber "tel: + 12065551219"

\-TrunkConfiguration $t

\+

~~

\+CategoryInfo: InvalidData: (:) \[CsInterTrunkRouting\](대만)

ameterBindingArgumentTransformationException

\+FullyQualifiedErrorId: ParameterArgumentTransformationError, Microsoft. R

tc. 관리. TestOcsInterTrunkRoutingCmdlet

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>테스트가 실패할 수 있는 이유

**테스트 CsInterTrunkRouting** 가 실패할 수 있는 몇 가지 일반적인 이유는 다음과 같습니다.

  - 잘못 된 매개 변수를 지정 했습니다. 트렁크가 아직 올바르게 구성 되지 않았거나 지정 된 대상 번호가 올바르지 않거나 올바르지 않을 수 있습니다.

</div>

<div>

## <a name="see-also"></a>참고 항목


[Get-CsTrunk](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunk)  
[Get-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunkConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

