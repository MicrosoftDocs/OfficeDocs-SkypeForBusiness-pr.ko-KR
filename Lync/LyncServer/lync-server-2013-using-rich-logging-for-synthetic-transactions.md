---
title: 'Lync Server 2013: 종합 거래에 대 한 풍부한 로깅 사용'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Using rich logging for synthetic transactions
ms:assetid: 32714a71-9f42-4d5b-a508-e176d8f08bbf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204798(v=OCS.15)
ms:contentKeyID: 48183812
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 455d7bcdc14dd4d701d749407759cead0834906f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983590"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-rich-logging-for-synthetic-transactions-in-lync-server-2013"></a>Lync Server 2013에서 종합 거래에 대 한 풍부한 로깅 사용

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-22_

Microsoft Lync Server 2010에서 도입 된 가상 트랜잭션은 관리자가 사용자가 시스템에 로그인 하거나 인스턴트 메시지를 교환 하거나 휴대폰에 전화를 거는 등의 일반적인 작업을 성공적으로 완료할 수 있는지 확인 하는 방법을 제공 합니다. PSTN (공공 교환 전화 통신망)에서. 이러한 테스트 (Lync Server Windows PowerShell cmdlet 집합으로 패키지 된)는 관리자가 수동으로 수행 하거나 System Center Operations Manager와 같은 응용 프로그램에서 자동으로 실행할 수 있습니다.

Lync Server 2010에서 가상 트랜잭션은 관리자가 시스템의 문제를 식별 하는 데 도움이 되는 매우 유용한 방법을 입증 했습니다. 예를 들어 **테스트-CsRegistration** cmdlet은 일부 사용자가 Lync Server에 등록 하는 데 어려움을 겪고 있다는 사실을 관리자에 게 알릴 수 있습니다. 그러나 이러한 사용자가 Lync Server에 등록 하는 데 어려움이 있는 이유를 관리자가 확인할 수 있도록 하는 것이 가상 트랜잭션은 다소 덜 유용 했습니다. 이는 가상 트랜잭션에서 관리자가 Lync Server의 문제를 해결할 수 있도록 도와주는 자세한 로깅 정보를 제공 하지 않았기 때문입니다. 가장 좋은 이유는, 관리자가 문제가 발생 했을 수 있는 곳으로 추측할 수 있도록 하는 단계별 정보를 제공 하는 가상 트랜잭션의 자세한 출력입니다.

Microsoft Lync Server 2013에서 가상 트랜잭션은 풍부한 로깅을 제공 하도록 다시 설계 되었습니다. "풍부한 로깅"은 가상 트랜잭션을는 하는 각 활동에 대해 다음과 같은 정보가 기록 된다는 의미입니다.

  - 활동이 시작 된 시간

  - 작업이 완료 된 시간

  - 수행 된 작업 (예: 회의 만들기, 참가 또는 탈퇴, Lync Server에 로그인, 인스턴트 메시지 보내기 등)

  - 활동이 실행 될 때 생성 되는 정보, 세부 정보, 경고 또는 오류 메시지

  - SIP 등록 메시지

  - 활동이 실행 될 때 생성 되는 예외 레코드 또는 진단 코드

  - 활동 실행의 순 결과

이 정보는 가상 트랜잭션을 실행할 때마다 자동으로 생성 됩니다. 그러나 정보는 자동으로 로그 파일에 표시 되거나 저장 되지 않습니다. 대신 가상 트랜잭션을 수동으로 실행 하는 관리자는 OutLoggerVariable 매개 변수를 사용 하 여 정보가 저장 되는 Windows PowerShell 변수를 지정할 수 있습니다. 그런 다음 관리자가 XML 또는 HTML 형식으로 풍부한 로그를 저장 및/또는 볼 수 있도록 하는 메서드 쌍을 사용 합니다.

예를 들어 Lync Server 2010 관리자는 다음과 유사한 명령을 사용 하 여 **테스트 CsRegistration** cmdlet을 실행할 수 있습니다.

    Test-CsRegistration -TargetFqdn atl-cs-001.litwareinc.com

관리자는 OutLoggerVariable 매개 변수를 포함 하 고 선택 하는 변수 이름을 입력 하는 옵션을 사용할 수 있습니다.

    Test-CsRegistration -TargetFqdn atl-cs-001.litwareinc.com -OutLoggerVariable RegistrationTest

> [!NOTE]  
> 변수 이름 앞에 $ 문자를 사용 하지 마세요. $RegistrationTest 하지 않고 RegistrationTest와 같은 변수 이름을 사용 합니다.

위의 명령은 다음과 유사한 콘텐츠를 출력 합니다.

    Target Fqdn   : atl-cs-001.litwareinc.com
    Result        : Failure
    Latency       : 00:00:00
    Error Message : This machine does not have any assigned certificates.
    Diagnosis     :

그러나이 오류는 위에 표시 된 오류 메시지 보다 더 자세한 정보를 얻을 수 있습니다. HTML 형식으로 해당 정보에 액세스 하려면 다음과 비슷한 명령을 사용 하 여 변수 RegistrationTest에 저장 된 정보를 HTML 파일에 저장 합니다.

    $RegistrationTest.ToHTML() | Out-File C:\Logs\Registration.html

또는 ToXML () 메서드를 사용 하 여 데이터를 XML 파일에 저장할 수 있습니다.

    $RegistrationTest.ToXML() | Out-File C:\Logs\Registration.xml

이러한 파일은 Internet Explorer, Visual Studio 또는 HTML/XML 파일을 열 수 있는 다른 응용 프로그램을 사용 하 여 볼 수 있습니다.

System Center 내에서 실행 되는 가상 트랜잭션은 오류에 대 한 이러한 로그 파일을 자동으로 생성 합니다. 그러나 Windows PowerShell이 가상 트랜잭션을 로드 하 고 실행할 수 있으려면 실행이 실패 하는 경우에는 이러한 로그가 생성 되지 않습니다.

> [!IMPORTANT]  
> 기본적으로 Lync Server 2013에서는 공유 되지 않는 폴더에 로그 파일을 저장 합니다. 이러한 로그에 쉽게 액세스할 수 있도록 하려면이 폴더를 공유 해야 합니다 (예 \\ \\: atl-litwareinc. com\WatcherNode.


</div>

</div>

</div>

</div>

