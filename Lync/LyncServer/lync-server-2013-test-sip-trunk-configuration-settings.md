---
title: 'Lync Server 2013: SIP 트렁크 구성 설정 테스트'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test SIP trunk configuration settings
ms:assetid: c8712308-0e2d-4e39-8f90-d1a250487a94
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721880(v=OCS.15)
ms:contentKeyID: 49733814
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ba8abe19ed739783dc702686d630fb854ab9150a
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42194559"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="test-sip-trunk-configuration-settings-in-lync-server-2013"></a>Lync Server 2013에서 SIP 트렁크 구성 설정 테스트

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-11-01_

SIP 트렁크 구성 설정은 중재 서버 및 PSTN(공중 전화망) 게이트웨이, IP-PBX(Public Branch Exchange) 또는 서비스 공급자의 SBC(세션 경계 컨트롤러) 사이의 관계 및 기능을 정의합니다. 이러한 설정은 지정할 경우 다음과 같은 기능을 수행합니다.

  - 트렁크에 미디어 우회를 설정할지 여부

  - RTCP(Real-time Transport Control Protocol) 패킷이 전송되는 조건

  - SRTP(Secure Real-time Protocol) 암호화가 각 트렁크에 필요한지 여부

Microsoft Lync Server 2013을 설치 하면 SIP 트렁크 구성 설정의 전역 모음이 만들어집니다. 관리자는 사이트 범위 또는 서비스 범위(PSTN 게이트웨이 서비스만 해당)에서 사용자 지정 설정 컬렉션을 만들 수도 있습니다. 관리자는 또한 Test-CsTrunkConfiguration cmdlet을 사용하여 사용자가 거는 번호를 게이트웨이에서 처리할 수 있는 번호로 트렁크가 변환할 수 있는지 확인할 수 있습니다.

트렁크 구성 설정은 Windows PowerShell과 [Test-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/Test-CsTrunkConfiguration) cmdlet을 사용해서만 테스트할 수 있습니다. 이 cmdlet은 Lync Server 2013 관리 셸 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다. 원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.

<div>

## <a name="to-test-sip-trunk-configuration-settings"></a>SIP 트렁크 구성 설정을 테스트 하려면

  - 다음 명령을 실행하면 레드몬드 사이트의 트렁크 구성 설정이 전화 번호(4255551212)를 올바로 변환할 수 있는지 확인할 수 있습니다.
    
        $trunk = Get-CsTrunkConfiguration -Identity "site:Redmond"
        Test-CsTrunkConfiguration -DialedNumber 4255551212 -TrunkConfiguration $trunk

</div>

</div>

<span> </span>

</div>

</div>

</div>

