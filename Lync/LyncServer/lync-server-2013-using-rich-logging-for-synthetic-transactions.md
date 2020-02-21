---
title: 'Lync Server 2013: 가상 트랜잭션에 대 한 리치 로깅을 사용 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using rich logging for synthetic transactions
ms:assetid: 32714a71-9f42-4d5b-a508-e176d8f08bbf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204798(v=OCS.15)
ms:contentKeyID: 48183812
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b1fd1cfd26e1b5d56a6043e13d348e73e3c2b108
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42212724"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="using-rich-logging-for-synthetic-transactions-in-lync-server-2013"></a>Lync Server 2013에서 가상 트랜잭션에 대 한 리치 로깅 사용

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-22_

Microsoft Lync Server 2010에서 도입 된 가상 트랜잭션은 관리자가 사용자가 시스템에 로그온 하거나 인스턴트 메시지를 교환 하거나 전화를 걸고 있는 등의 일반적인 작업을 성공적으로 완료할 수 있는지 확인 하는 방법을 제공 합니다. 공중 전화망 (PSTN) Lync Server Windows PowerShell cmdlet 집합으로 패키지 된 이러한 테스트는 관리자가 수동으로 수행 하거나 System Center Operations Manager와 같은 응용 프로그램에서 자동으로 실행할 수 있습니다.

Lync Server 2010에서는 관리자가 시스템 문제를 파악 하는 데 도움이 되는 가상 트랜잭션이 입증 되었습니다. 예를 들어, **테스트-CsRegistration** cmdlet은 사용자가 Lync Server에 등록 하는 데 어려움을 겪고 있다는 사실을 관리자에 게 알릴 수 있습니다. 그러나 가상 트랜잭션은 관리자가 Lync Server에 등록 하는 데 어려움이 있는 이유를 확인 하는 데 도움이 되는 다소 덜 유용 합니다. 이는 가상 트랜잭션에서 관리자가 Lync Server의 문제를 해결 하는 데 도움이 되는 자세한 로깅 정보를 제공 하지 않았기 때문 이었습니다. 가상 트랜잭션의 자세한 정보 출력에서 제공하는 단계별 정보를 통해 관리자가 문제 발생 위치를 어느 정도 근접하게 추측할 수는 있습니다.

Microsoft Lync Server 2013에서 가상 트랜잭션은 풍부한 로깅을 제공 하도록 다시 설계 되었습니다. "향상된 로깅"이란 가상 트랜잭션이 수행하는 각 활동에 대해 다음과 같은 정보가 기록된다는 의미입니다.

  - 활동이 시작된 시간

  - 활동이 완료된 시간

  - 수행 된 작업 (예: 회의 만들기, 참가, 탈퇴, Lync Server에 로그인, 인스턴트 메시지 보내기 등)

  - 활동 실행 시 생성된 정보, 자세한 정보, 경고 또는 오류 메시지

  - SIP 등록 메시지

  - 활동 실행 시 생성된 예외 레코드 또는 진단 코드

  - 활동 실행의 순수 결과

이 정보는 가상 트랜잭션을 실행할 때마다 자동으로 생성됩니다. 그러나 정보가 자동으로 표시되거나 로그 파일에 저장되는 것은 아닙니다. 대신, 가상 트랜잭션을 수동으로 실행 하는 관리자는 OutLoggerVariable 매개 변수를 사용 하 여 정보가 저장 될 Windows PowerShell 변수를 지정할 수 있습니다. 그러면 관리자는 두 가지 방법을 통해 향상된 로그를 XML 또는 HTML 형식으로 저장 및/또는 표시할 수 있습니다.

예를 들어 Lync Server 2010 관리자는 다음과 같은 명령을 사용 하 여 **테스트 CsRegistration** cmdlet을 실행할 수 있습니다.

    Test-CsRegistration -TargetFqdn atl-cs-001.litwareinc.com

관리자는 OutLoggerVariable 매개 변수 뒤에 선택한 변수 이름을 붙여 포함할 수 있습니다.

    Test-CsRegistration -TargetFqdn atl-cs-001.litwareinc.com -OutLoggerVariable RegistrationTest

> [!NOTE]  
> 변수 이름 앞에 $ 문자를 붙이지 마십시오. 즉, $RegistrationTest가 아닌 RegistrationTest를 변수 이름으로 사용해야 합니다.

위의 명령은 다음과 같은 콘텐츠를 출력합니다.

    Target Fqdn   : atl-cs-001.litwareinc.com
    Result        : Failure
    Latency       : 00:00:00
    Error Message : This machine does not have any assigned certificates.
    Diagnosis     :

그러나 이 오류에 대해 위에 나와 있는 오류 메시지뿐만 아니라 훨씬 자세한 정보를 확인할 수 있습니다. HTML 형식의 해당 정보에 액세스하려면 다음과 같은 명령을 사용하여 RegistrationTest 변수에 저장된 정보를 HTML 파일에 저장합니다.

    $RegistrationTest.ToHTML() | Out-File C:\Logs\Registration.html

또는 ToXML() 메서드를 사용하여 데이터를 XML 파일에 저장할 수도 있습니다.

    $RegistrationTest.ToXML() | Out-File C:\Logs\Registration.xml

이러한 파일은 Internet Explorer, Visual Studio 또는 HTML/XML 파일을 열 수 있는 다른 응용 프로그램을 사용 하 여 볼 수 있습니다.

System Center Operations Manager 내부에서 실행 되는 가상 트랜잭션은 오류에 대 한 이러한 로그 파일을 자동으로 생성 합니다. 그러나 Windows PowerShell에서 가상 트랜잭션을 로드 하 고 실행할 수 있으려면 실행이 실패 하는 경우에는 이러한 로그가 생성 되지 않습니다.

> [!IMPORTANT]  
> 기본적으로 Lync Server 2013에서는 공유 되지 않는 폴더에 로그 파일을 저장 합니다. 이러한 로그에 쉽게 액세스할 수 있도록 하려면이 폴더를 공유 해야 합니다 (예 \\ \\: litwareinc com\WatcherNode.


</div>

</div>

</div>

</div>

