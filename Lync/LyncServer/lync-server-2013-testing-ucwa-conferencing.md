---
title: 'Lync Server 2013: (c) 회의 테스트'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing UCWA conferencing
ms:assetid: 62b3866a-0759-4b1f-99ec-5a68d6a74f00
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727306(v=OCS.15)
ms:contentKeyID: 63969610
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: af4bd6dd911b43714dffa48c3b21d3329b2aaa01
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42193751"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-ucwa-conferencing-in-lync-server-2013"></a>Lync Server 2013에서 c u c 회의 테스트

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2014-11-03_


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
<p>Windows PowerShell의 원격 인스턴스를 사용 하 여 실행 하는 경우 <strong>test-csucwaconference</strong> cmdlet을 실행 하는 권한이 있는 RBAC 역할을 사용자에 게 할당 해야 합니다. 이 cmdlet을 사용할 수 있는 모든 RBAC 역할의 목록을 보려면 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsUcwaConference&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>설명

**Test-csucwaconference** cmdlet은 테스트 사용자 쌍이 통합 커뮤니케이션 웹 API (c)를 사용 하 여 온라인 회의를 예약, 가입 하 고 수행할 수 있는지 확인 합니다. 이 작업을 수행 하기 위해 cmdlet은 Lync Server web ticket 서비스를 사용 하 여 두 테스트 사용자를 인증 하 고 Lync Server에 등록 합니다. 그 다음 cmdlet은 모임 이끌이 자격 증명을 사용하여 회의를 시작하고 참가자를 모임에 초대합니다. 회의가 완료 되 면 **test-csucwaconference** cmdlet은 사용자가 exchange 인스턴트 메시지와 같은 작업을 수행 하 고 풀을 수행할 수 있는지 확인 한 다음, 회의의 연결을 끊고 두 테스트 사용자의 등록을 취소 합니다. 테스트가 완료 되 면 예약 된 전화 회의도 삭제 됩니다.

**Test-csucwaconference** cmdlet을 사용 하 여 익명 사용자가 온라인 회의에 참가할 수 있는지 여부를 확인할 수도 있습니다.

해당 풀에 **test-csucwaconference** cmdlet이 설치 되어 있지 않으면 Microsoft Lync Server 2010 풀에 대해 테스트를 실행 하지 않아야 합니다. **Test-csucwaconference** 및 wa가 설치 되지 않은 경우에는 해당 호출이 실패 합니다.

</div>

<div>

## <a name="running-the-test"></a>테스트 실행

예제 1의 명령은 테스트 사용자 한 쌍이 풀 atl-cs-001.litwareinc.com에서 UCWA 회의에 참석할 수 있는지 확인합니다. 이 명령은 atl-cs-001.litwareinc.com에 대해 상태 모니터링 구성 테스트 사용자 쌍을 미리 정의하지 않으면 실패합니다.

    Test-CsUcwaConference -TargetFqdn "atl-cs-001.litwareinc.com"

예제 2에 표시 된 명령은 litwareinc\\pilar 및 litwareinc\\kenmyer (사용자 쌍)가 c u 3 회의에 참가 하는 기능을 테스트 합니다. 이 작업을 수행 하기 위해이 예제의 첫 번째 명령은 Get-Credential cmdlet을 사용 하 여 user Pilar Ackerman의 이름과 암호가 포함 된 Windows PowerShell 명령줄 인터페이스 자격 증명 개체를 만듭니다. (로그온 이름, litwareinc\\pilar가 매개 변수로 포함 되었기 때문에 Windows PowerShell 자격 증명 요청 대화 상자에만 관리자가 Pilar Ackerman 계정의 암호를 입력 하면 됩니다.) 그런 다음 결과 credentials 개체가 $cred 1 이라는 변수에 저장 됩니다. 두 번째 명령도 같은 작업을 수행하지만 이번에는 Ken Myer 계정의 자격 증명 개체를 반환합니다.

두 자격 증명 개체를 함께 사용 하는 경우 예제의 세 번째 명령은 두 사용자가 c-WA 회의에 참가할 수 있는지 여부를 확인 합니다. 이 작업을 실행 하기 위해 **test-csucwaconference** Cmdlet은 targetfqdn (등록자 풀의 fqdn)과 함께 다음과 같은 매개 변수를 사용 하 여 호출 됩니다. Organizercredential (모임 이끌이의 SIP 주소) 변수와 (이 사용자에 대 한 자격 증명이 포함 된 Windows PowerShell 개체) ParticipantSipAddress (다른 테스트 사용자의 SIP 주소); 및 ParticipantCredential (다른 사용자의 자격 증명을 포함 하는 Windows PowerShell 명령줄 인터페이스 개체)

    $cred1 = Get-Credential "litwareinc\pilar"
    $cred2 = Get-Credential "litwareinc\kenmyer"
    Test-CsUcwaConference -TargetFqdn atl-cs-001.litwareinc.com -OrganizerSipAddress "sip:pilar@litwareinc.com" -OrganizerCredential $cred1 -ParticipantSipAddress "sip:kenmyer@litwareinc.com" -ParticipantCredential $cred2

</div>

<div>

## <a name="determining-success-or-failure"></a>성공 또는 실패 확인

회의가 올바르게 구성 되 면 다음과 비슷한 출력을 받게 되며 Result 속성이 Success로 표시 됩니다 **.**

대상 Fqdn: atl-cs-001.litwareinc.com

대상 Uri: https://Lynctest를 사용 합니다.

Microsoft.com:443/CertProv/CertProvisiongService.svc

결과: 성공

대기 시간: 00:00:14.9862716

오류 메시지:

진단을

지정 된 사용자가 회의를 사용할 수 없는 경우 결과가 **실패로**표시 되 고 오류 및 진단 속성에 추가 정보가 기록 됩니다.

경고: 지정한 정규화 된 자격에 대 한 등록자 포트 번호를 읽지 못했습니다.

FQDN (도메인 이름) 기본 등록자 포트 번호 사용 오류

InvalidOperationException: 토폴로지에서 일치 하는 클러스터를 찾을 수 없습니다.

구독자

SyntheticTransactions SipSyntheticTransaction TryRetri를 관리 합니다.

eveRegistrarPortFromTopology (Int32& registrarPortNumber)

Test-csucwaconference: 할당 된 테스트 사용자가 없습니다.

\[LyncTest.SelfHost.Corp.Microsoft.com\] 테스트 사용자 구성을 확인 합니다.

줄: 1 문자: 1

\+Test-csucwaconference-TargetFqdn "LyncTest.SelfHost.Corp.Microsoft.com"

\+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

\+CategoryInfo: ResourceUnavailable 사용할 수 없음: (:) \[Test-csucwaconference\]

, InvalidOperationException

\+FullyQualifiedErrorId: NotFoundTestUsers, Microsoft.

eticTransactions

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>테스트가 실패 한 이유

다음은 **test-csucwaconference에서** 오류가 발생할 수 있는 몇 가지 일반적인 이유입니다.

  - 잘못 된 매개 변수 값이 제공 되었습니다. 사용 하는 경우 선택적 매개 변수를 올바르게 구성 해야 하며 그렇지 않으면 테스트가 실패 합니다. 선택적 매개 변수 없이 명령을 다시 실행 하 여 성공 여부를 확인 합니다.

  - 회의를 수행 하는 기능은 회의를 이끄는 사용자에 게 할당 된 회의 정책 ( **test-csucwaconference** cmdlet의 경우 "sender")에 따라 달라 집니다. 이끌이가 자신의 모임에 공동 작업을 포함할 수 없는 경우 (예: 해당 회의 정책에서 EnableDataCollaboration 속성을 False로 설정한 경우) **test-csucwaconference** cmdlet이 실패 합니다.

  - 에 지 서버가 잘못 구성 되었거나 아직 배포 되지 않은 경우에는이 명령이 실패 합니다.

</div>

<div>

## <a name="see-also"></a>참고 항목


[테스트-CsASConference](https://docs.microsoft.com/powershell/module/skype/Test-CsASConference)  
[Test-csdataconference](https://docs.microsoft.com/powershell/module/skype/Test-CsDataConference)  
[CsAVConference 테스트](https://docs.microsoft.com/powershell/module/skype/Test-CsAVConference)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

