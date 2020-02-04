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
ms.openlocfilehash: 13f5357ae1a0dd4e8db044c2081154d4c3f4febf
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746208"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-sip-trunk-configuration-settings-in-lync-server-2013"></a>Lync Server 2013에서 SIP 트렁크 구성 설정 테스트

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-11-01_

SIP 트렁크 구성 설정은 중재 서버와 PSTN (공개 통신 네트워크) 게이트웨이, IP-공용 분기 교환 (PBX) 또는 서비스 공급자의 SBC (세션 경계 컨트롤러) 간에 관계와 접근 권한 값을 정의 합니다. 이러한 설정은 다음을 지정 하는 등의 작업을 수행 합니다.

  - Trunks에서 미디어 바이패스를 사용 해야 하는지 여부

  - RTCP (실시간 전송 제어 프로토콜) 패킷이 전송 되는 조건입니다.

  - 각 트렁크에서 보안 실시간 프로토콜 (SRTP) 암호화가 필요한 지 여부

Microsoft Lync Server 2013을 설치할 때 SIP 트렁크 구성 설정의 전역 컬렉션이 생성 됩니다. 또한 관리자는 사이트 범위 또는 서비스 범위 (PSTN 게이트웨이 서비스에만 해당)에서 사용자 지정 설정 모음을 만들 수 있습니다. 또한 관리자는 Set-cstrunkconfiguration cmdlet을 사용 하 여 트렁크가 사용자에 게 전화를 거는 번호를 게이트웨이에서 처리할 수 있는 번호로 변환할 수 있는지 확인할 수 있습니다.

트렁크 구성 설정은 Windows PowerShell 및 [테스트 set-cstrunkconfiguration](https://docs.microsoft.com/powershell/module/skype/Test-CsTrunkConfiguration) cmdlet을 사용 하 여 테스트할 수 있습니다. 이 cmdlet은 Lync Server 2013 관리 셸에서 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다. 원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.

<div>

## <a name="to-test-sip-trunk-configuration-settings"></a>SIP 트렁크 구성 설정을 테스트 하려면

  - 이 명령은 Redmond 사이트의 트렁크 구성 설정이 전화 거는 번호 4255551212를 올바르게 변환할 수 있는지 확인 합니다.
    
        $trunk = Get-CsTrunkConfiguration -Identity "site:Redmond"
        Test-CsTrunkConfiguration -DialedNumber 4255551212 -TrunkConfiguration $trunk

</div>

</div>

<span> </span>

</div>

</div>

</div>

