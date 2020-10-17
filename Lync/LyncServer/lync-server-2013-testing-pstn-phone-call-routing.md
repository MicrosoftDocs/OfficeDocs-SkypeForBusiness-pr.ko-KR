---
title: 'Lync Server 2013: PSTN 전화 통화 라우팅 테스트'
description: 'Lync Server 2013: PSTN 전화 통화 라우팅을 테스트 합니다.'
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
ms.openlocfilehash: da931b43176932a9b6781fa27318e83e6994548c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556274"
---
# <a name="testing-pstn-phone-call-routing-in-lync-server-2013"></a>Lync Server 2013에서 PSTN 전화 통화 라우팅 테스트

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2014-11-01_


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
<p>Windows PowerShell의 원격 인스턴스를 사용 하 여 실행 하는 경우 <strong>test-csintertrunkrouting</strong> cmdlet을 실행 하는 권한이 있는 RBAC 역할을 사용자에 게 할당 해야 합니다. 이 cmdlet을 사용할 수 있는 모든 RBAC 역할의 목록을 보려면 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsInterTrunkRouting&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>설명

**Test-csintertrunkrouting** cmdlet은 통화를 다른 SIP로 라우팅할 수 있는지 확인 합니다. 이 작업을 수행 하기 위해 cmdlet에는 전화 번호와 트렁크 구성이 지정 됩니다. 그런 다음 **test-csintertrunkrouting** 는 지정 된 번호에 대해 일치 하는 경로 및 일치 하는 PSTN 용도를 보고 합니다. 트렁크에 지정 된 전화 번호와 일치 하는 번호 패턴이 있고 트렁크에서 PSTN 사용을 하나 이상 공유 하는 경우에만 트렁크 간에 통화를 라우팅할 수 있습니다.

</div>

<div>

## <a name="running-the-test"></a>테스트 실행

아래에 나와 있는 명령은 사용자가 Redmond 사이트의 트렁크 구성 설정을 사용 하 여 전화 번호 1-206-555-1219에 전화를 걸 수 있도록 하는 일치 경로 및 일치 하는 전화 사용을 반환 합니다.

    $trunk = Get-CsTrunkConfiguration -Identity "site:Redmond"
    
    Test-CsInterTrunkRouting -TargetNumber "tel:+12065551219" -TrunkConfiguration $trunk

</div>

<div>

## <a name="determining-success-or-failure"></a>성공 또는 실패 확인

통화 간 통신을 다른 SIP로 라우팅할 수 있으면 다음과 같은 출력이 표시 됩니다.

FirstMatchingRoute MatchingUsage MatchingRoutes

\------------------ ------------- --------------

RedmondRoute LocalUsage {RedmondRoute}

테스트가 실패 하면 다음과 같은 출력이 표시 됩니다.

Test-CsInterTrunkRouting: 매개 변수에서 인수 변환을 처리할 수 없습니다.

' Microsoft.rtc.management.writableconfig.settings.trunkconfiguration.trunkconfiguration 유형의 ' 잘못 된 TrunkConfigurationsetting (매개 변수)입니다. 를 지정 합니다.

유효한 설정 (매개 변수)을 선택한 다음 다시 시도 하십시오.

줄: 1 char: 79

\+ Test-CsInterTrunkRouting-TargetNumber "tel: + 12065551219"

\-Microsoft.rtc.management.writableconfig.settings.trunkconfiguration.trunkconfiguration 유형의 $t

\+

~~

\+CategoryInfo: InvalidData: (:) \[ Test-csintertrunkrouting (대만) \]

ameterBindingArgumentTransformationException

\+ FullyQualifiedErrorId: ParameterArgumentTransformationError (Microsoft. R)

tc. TestOcsInterTrunkRoutingCmdlet를 관리 합니다.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>테스트가 실패 한 이유

다음은 **test-csintertrunkrouting에서** 오류가 발생할 수 있는 몇 가지 일반적인 이유입니다.

  - 잘못 된 매개 변수를 지정 했습니다. 트렁크가 제대로 구성 되어 있지 않거나 지정 된 대상 번호가 잘못 되었거나 잘못 되었을 수 있습니다.

</div>

<div>

## <a name="see-also"></a>참고 항목


[Get-cstrunk](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunk)  
[Get-cstrunkconfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunkConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

