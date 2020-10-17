---
title: 'Lync Server 2013: 모바일 기능 배포 확인'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verifying your mobility deployment
ms:assetid: 72f9b4d3-57b0-4705-9480-cfdca313a70c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690024(v=OCS.15)
ms:contentKeyID: 48184477
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8fefcdaf1fc84151fd37d7ff29acf66d742425d7
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48527615"
---
# <a name="verifying-your-mobility-deployment-in-lync-server-2013"></a>Lync Server 2013에서 모바일 기능 배포 확인

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-02-12_

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

Lync Server Mobility Service 및 Lync Server 자동 검색 서비스를 배포한 후 테스트 트랜잭션을 실행 하 여 배포가 제대로 작동 하는지 확인 합니다. **Test-csucwaconference** 를 실행 하 여 Lync 2013 모바일 클라이언트를 사용 하는 두 사용자가 회의에서 작성, 참가 및 통신 하는 기능을 테스트할 수 있습니다. 이 테스트 트랜잭션을 사용 하려면 두 명의 실제 사용자 또는 테스트 사용자와 전체 자격 증명이 필요 합니다.

**Test-csmcxp2pim** 를 사용 하 여 Lync 2010 Mobile을 사용 하는 두 사용자 간의 인스턴트 메시지 전송을 테스트 합니다. **Test-csucwaconference**와 마찬가지로 두 명의 실제 사용자 또는 두 개의 미리 정의 된 테스트 사용자를 사용 합니다.

<div>

## <a name="to-test-conferencing-for-lync-2013-mobile-clients"></a>Lync 2013 모바일 클라이언트에 대 한 회의를 테스트 하려면

1.  Lync Server 관리 셸 및 Ocscore 설치 된 모든 컴퓨터에서 CsAdministrator 역할의 구성원으로 로그온 합니다.

2.  **시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.

3.  명령줄에 다음을 입력합니다.
    
        Test-CsUcwaConference -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -OrganizerSipAddress sip:<SIP address of test user 1> -OrganizerCredential <test user 1 credentials> -ParticipantSipAddress sip:<SIP address of test user 2> -ParticipantCredential <test user 2 credentials> -v
    
    스크립트에서 자격 증명을 설정하여 테스트 cmdlet으로 전달할 수 있습니다. 예를 들면 다음과 같습니다.
    
        $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
        $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
        $testuser1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
        $testuser2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
        Test-CsUcwaConference -TargetFqdn pool01.contoso.com -Authentication Negotiate -OrganizerSipAddress sip:UserName1@contoso.com -OrganizerCredential $testuser1 -ParticipantSipAddress sip:UserName2@contoso.com -ParticipantCredential $testuser2 -v

</div>

<div>

## <a name="to-test-person-to-person-instant-messaging-im-for-lync-2010-mobile"></a>Lync 2010 모바일에 대 한 사용자 간 IM (인스턴트 메시징)을 테스트 하려면

1.  Lync Server 관리 셸 및 Ocscore 설치 된 모든 컴퓨터에서 CsAdministrator 역할의 구성원으로 로그온 합니다.

2.  **시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.

3.  명령줄에 다음을 입력합니다.
    
        Test-CsMcxP2PIM -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -SenderSipAddress sip:<SIP address of test user 1> -SenderCredential <test user 1 credentials> -ReceiverSipAddress sip:<SIP address of test user 2> -ReceiverCredential <test user 2 credentials> -v
    
    스크립트에서 자격 증명을 설정하여 테스트 cmdlet으로 전달할 수 있습니다. 예를 들면 다음과 같습니다.
    
        $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
        $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
        $tuc1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
        $tuc2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
        Test-CsMcxP2PIM -TargetFqdn pool01.contoso.com -Authentication Negotiate -SenderSipAddress sip:UserName1@contoso.com -SenderCredential $tuc1 -ReceiverSipAddress sip:UserName2@contoso.com -ReceiverCredential $tuc2 -v

</div>

<div>

## <a name="see-also"></a>참고 항목


[Test-csmcxp2pim](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxP2PIM)  
[Test-csucwaconference](https://docs.microsoft.com/powershell/module/skype/Test-CsUcwaConference)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

