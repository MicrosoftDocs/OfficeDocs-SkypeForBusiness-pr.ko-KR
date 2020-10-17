---
title: 'Lync Server 2013: 전화 번호를 기준으로 트렁크 구성 확인'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Check trunk configuration against a phone number
ms:assetid: 0800d7a3-fc35-482b-a9a4-203d890bfa45
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725206(v=OCS.15)
ms:contentKeyID: 63969574
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 881e161a01b589db2db172cb5115858b522d262b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48526235"
---
# <a name="check-trunk-configuration-against-a-phone-number-in-lync-server-2013"></a>Lync Server 2013에서 전화 번호를 기준으로 트렁크 구성 확인

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



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
<p>Windows PowerShell의 원격 인스턴스를 사용 하 여 실행 하는 경우 사용자에 게 Test-CsTrunkConfiguration cmdlet을 실행 하는 권한이 있는 RBAC 역할을 할당 해야 합니다. 이 cmdlet을 사용할 수 있는 모든 RBAC 역할의 목록을 보려면 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.</p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsTrunkConfiguration&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>설명

SIP 트렁크 Lync Server 내부 Enterprise Voice network를 다음 중 하나에 연결 합니다.

  - 공중 전화망 (PSTN)

  - IP-PBX (공용 분기 교환)

  - SBC (Session Border Controller)입니다.

Test-CsTrunkConfiguration cmdlet은 사용자가 전화를 걸 수 있는 전화번호를 E. 164 네트워크로 변환 하 고 지정 된 SIP 트렁크를 통해 라우팅되는 것을 확인 합니다.

</div>

<div>

## <a name="running-the-test"></a>테스트 실행

Test-CsTrunkConfiguration cmdlet을 실행 하려면 먼저 Get-CsTrunkConfiguration cmdlet을 사용 하 여 SIP 트렁크 구성 설정 인스턴스를 검색 해야 합니다. 그런 다음 해당 인스턴스는 Get-cstrunkconfiguration로 파이프 됩니다.

`Get-CsTrunkConfiguration -Identity "Global" | Test-CsTrunkConfiguration -DialedNumber "12065551219"`

Get-CsTrunkConfiguration를 먼저 실행 하지 않고 Test-CsTrunkConfiguration를 실행 하는 것은 작동 하지 않습니다. 예를 들어 다음 명령은 데이터를 반환 하지 않고 실패 합니다.

`Test-CsTrunkConfiguration -DialedNumber "12065551219" -TrunkConfiguration "Global"`

SIP 트렁크 구성 설정의 컬렉션이 여러 개 있는 경우 동일한 전화 번호에 대해 각 모음을 테스트 하는 동시에 다음과 같은 명령을 사용할 수 있습니다.

`Get-CsTrunkConfiguration | Test-CsTrunkConfiguration -DialedNumber "12065551219"`

자세한 내용은 Test-CsTrunkConfiguration cmdlet에 대 한 도움말 설명서를 참조 하십시오.

</div>

<div>

## <a name="determining-success-or-failure"></a>성공 또는 실패 확인

전화 건 번호로 전화를 걸 수 Test-CsTrunkConfiguration 경우 변환 된 전화 번호 (E. 164 형식)와 해당 전화 번호를 변환 하는 데 사용 되는 규칙이 모두 화면에 표시 됩니다.

TranslatedNumber MatchingRule

\---------------- ------------

\+12065551219 글로벌/Redmond

테스트가 실패 하면 Test-CsTrunkConfiguration에서 빈 속성 값을 반환 합니다.

TranslatedNumber MatchingRule

\---------------- ------------

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>테스트가 실패 한 이유

Test-CsTrunkConfiguration 일치 하는 항목을 반환 하지 않으면 테스트 중인 트렁크 구성 설정에 전화 건 번호를 E. 164 형식으로 변환 하는 데 사용할 수 있는 발신 전화 번호 변환 규칙이 없는 것입니다. 트렁크 구성 설정 컬렉션에 할당 된 변환 규칙을 검색 하려면 다음과 같은 구문을 사용할 수 있습니다.

`Get-CsTrunkConfiguration -Identity "global" | Select-Object -ExpandProperty OutboundTranslationRulesList`

이는 각 변환 규칙에 대해 다음과 같은 정보를 반환 합니다.

설명: 국가 코드나 지역 코드가 없는 전화 번호입니다.

패턴: ^ \\ + ( \\ d \* ) $

`Translation : $1`

이름: NoAreaCode

이때 패턴 속성의 값 ( [정규식](https://go.microsoft.com/fwlink/?linkid=400464) 문자열)을 확인 하 여 전화 건 번호를 처리 하도록 변환 규칙이 구성 되었는지 여부를 확인 합니다. 그렇지 않은 경우 기존 규칙 (New-csoutboundtranslationrule) 중 하나를 변경 하거나, New-CsOutboundTranslationRule cmdlet을 사용 하 여 컬렉션에 새 규칙을 추가 해야 합니다.

</div>

<div>

## <a name="see-also"></a>참고 항목


[Get-cstrunkconfiguration](https://docs.microsoft.com/powershell/module/skype/Test-CsTrunkConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

