---
title: 'Lync Server 2013: 중앙 로깅 서비스 개요'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of the Centralized Logging Service
ms:assetid: 975718a0-f3e3-404d-9453-6224e73bfdd0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688145(v=OCS.15)
ms:contentKeyID: 49733746
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1460699b6516ab4e510c9715b2464ce442466faa
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755452"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-the-centralized-logging-service-in-lync-server-2013"></a>Lync Server 2013의 중앙 집중화 된 로깅 서비스 개요

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-02-22_

중앙 로깅 서비스는 광범위 하거나 좁은 범위를 사용 하 여 데이터 수집을 위한 수단을 제공 하도록 디자인 되었습니다. 배포의 모든 서버에서 동시에 데이터를 수집 하 고, 추적할 특정 요소를 정의 하 고, 추적 플래그를 설정 하 고, 단일 컴퓨터에서 검색 결과를 반환 하 고, 모든 서버의 모든 데이터에 대 한 집계를 표시할 수 있습니다. 중앙 로깅 서비스는 배포의 모든 서버에서 실행 됩니다. 중앙 로깅 서비스의 아키텍처는 다음 에이전트와 서비스로 구성 됩니다.

  - *중앙 로깅 서비스 에이전트*   clsagent는 컨트롤러와 통신 하는 서비스 실행 파일이 며, 관리자가 컨트롤러가 발급 하는 명령을 받습니다. 에이전트는 각 Lync Server 컴퓨터에서 서비스로 실행 됩니다. 에이전트는 명령을 수신 하 고 명령을 실행 하 고 추적을 위해 정의 된 구성 요소로 메시지를 보내고 추적 로그를 디스크에 기록 합니다. 또한 해당 컴퓨터에 대 한 추적 로그를 읽고 요청 시 추적 데이터를 컨트롤러로 다시 보냅니다. ClsAgent는 **tcp 50001**, **Tcp 50002**및 **tcp 50003**포트의 명령을 수신 합니다.

  - *중앙 로깅 서비스 컨트롤러*   clscontrollerlib는 Lync Server 관리 셸 및 clscontroller .exe에 대 한 명령 실행 엔진입니다. CLSControllerLib는 ClsAgent에 시작, 중지, 플러시 및 검색 명령을 보냅니다. 검색 명령을 보내면 결과 로그가 ClsControllerLib로 반환 되 고 집계 됩니다. 컨트롤러는 에이전트에 명령을 전송 하 고, 해당 명령의 상태를 받고, 검색 범위에 있는 컴퓨터의 모든 에이전트에서 반환 되는 검색 로그 파일 데이터를 관리 하 고, 의미 있고 정렬 된 것으로 로그 데이터를 집계 하는 역할을 합니다. 출력 집합 다음 항목의 정보는 Lync Server 관리 셸을 사용 하는 데 초점을 맞추었습니다. ClsController는 Lync Server 관리 셸에서 사용할 수 있는 기능 및 기능의 하위 집합으로 제한 됩니다. 명령줄에서 ClsController에 대 한 도움말을 보려면 기본 디렉터리 C: `ClsController` \\Program Files\\Common files\\Microsoft Lync Server 2013\\clscontroller에 입력 하 여 사용할 수 있습니다.

**Clscontroller에 대 한 ClsController 통신**

![CLSController와 CLSAgent 간의 관계.](images/JJ688145.68c90811-5cf9-4a84-95b7-ea9ffc61eac4(OCS.15).jpg "CLSController와 CLSAgent 간의 관계.")

Windows Server 명령줄 인터페이스 또는 Lync Server Management Shell을 사용 하 여 명령을 실행 합니다. 명령은 사용자가 로그인 하 여 로컬로 ClsAgent에 또는 배포의 다른 컴퓨터와 풀로 전송 된 컴퓨터에서 실행 됩니다.

ClsAgent는 all에 대 한 인덱스 파일을 유지 합니다. 로컬 컴퓨터에 있는 파일을 캐시 합니다. ClsAgent는 옵션 CacheFileLocalFolders에 의해 정의 된 모든 볼륨에서 균등 하 게 분산 되도록 각 볼륨의 80%를 초과 하지 않도록 (즉, 로컬 캐시 위치 및 백분율이 **Set CsClsConfiguration** cmdlet을 사용 하 여 구성할 수 있음)이를 할당 합니다. 또한 ClsAgent는 로컬 컴퓨터에서 이전에 캐싱된 이벤트 추적 로그 (.etl) 파일을 에이징 하는 역할을 합니다. 2 주 후 (즉, **설정-CsClsConfiguration** cmdlet을 사용 하 여 시간을 구성할 수 있음) 이러한 파일은 로컬 컴퓨터에서 파일 공유에 복사 되 고 삭제 됩니다. 자세한 내용은 [Set CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsClsConfiguration)을 참조 하세요. 검색 요청이 수신 되 면 검색 조건을 사용 하 여 에이전트에서 유지 관리 되는 인덱스의 값을 기준으로 검색을 수행 하도록 캐시 된 .etl 파일 집합을 선택 합니다.

<div>


> [!NOTE]  
> 로컬 컴퓨터에서 파일 공유로 이동 된 파일은 ClsAgent를 통해 검색할 수 있습니다. ClsAgent가 파일 공유로 파일을 이동 하면 ClsAgent가 파일의 에이징 및 제거를 유지 하지 않습니다. 파일 공유에서 파일 크기를 모니터링 하 고 삭제 하거나 보관 하는 관리 작업을 정의 해야 합니다.



</div>

결과 로그 파일은 **Snooper** 와 **메모장과**같은 텍스트 파일을 읽을 수 있는 도구를 비롯 한 다양 한 도구를 사용 하 여 읽고 분석할 수 있습니다. Snooper는 Lync Server 2013 디버그 도구의 일부 이며에서 [http://go.microsoft.com/fwlink/?LinkId=285257](http://go.microsoft.com/fwlink/?linkid=285257)웹으로 다운로드할 수 있습니다.

OCSLogger 같은 중앙 로깅 서비스에는 추적할 여러 구성 요소가 있으며 TF\_구성 요소 및 tf\_DIAG와 같이 플래그를 선택 하는 옵션을 제공 합니다. 또한 중앙 로깅 서비스는 OCSLogger의 로깅 수준 옵션도 유지 합니다.

명령줄 ClsController에서 Lync Server Management Shell을 사용 하는 경우 가장 중요 한 이점은 문제 공간, 사용자 지정 플래그 및 로깅 수준을 대상으로 하는 선택 된 공급자를 사용 하 여 새 시나리오를 구성 하 고 정의할 수 있다는 것입니다. ClsController에서 사용할 수 있는 시나리오는 실행 파일에 대해 정의 된 것으로 제한 됩니다.

이전 버전에서는 관리자와 지원 담당자가 배포의 컴퓨터에서 추적 파일을 수집할 수 있도록 OCSLogger 제공 되었습니다. 모든 강점에 대 한 OCSLogger 단점을가지고 있습니다. 주어진 시간에 한 컴퓨터 에서만 로그를 수집할 수 있습니다. 각각의 OCSLogger 별도의 복사본을 사용 하 여 여러 컴퓨터에 로그온 할 수 있지만, 여러 개의 로그로 끝나지만 결과를 집계할 수 있는 방법은 없습니다.

사용자가 로그 검색을 요청 하면 ClsController는 요청을 보낼 컴퓨터 (즉, 선택 된 시나리오에 따라)를 결정 합니다. 또한 저장 된 .etl 파일이 있는 파일 공유에 검색을 보낼지 여부를 결정 합니다. 검색 결과가 ClsController에 반환 되 면 컨트롤러는 해당 결과를 사용자에 게 표시 되는 단일 시간 순서 결과 집합으로 병합 합니다. 사용자는 추가 분석을 위해 검색 결과를 로컬 컴퓨터에 저장할 수 있습니다.

로깅 세션을 시작할 때 해결 하려고 하는 문제에 상대적인 시나리오를 지정 합니다. 언제 든 지 두 가지 시나리오를 실행할 수 있습니다. 이러한 두 가지 시나리오 중 하나는 AlwaysOn 시나리오 여야 합니다. 이름에서 알 수 있듯이,이는 항상 배포에서 실행 되 고 모든 컴퓨터, 풀 및 구성 요소에 대 한 정보를 수집 합니다.

<div>


> [!IMPORTANT]  
> 기본적으로 AlwaysOn 시나리오는 배포에서 실행 되지 않습니다. 시나리오를 명시적으로 시작 해야 합니다. 시작 된 후에는 명시적으로 중지 될 때까지 계속 실행 되 고 컴퓨터를 다시 부팅할 때까지 실행 상태가 유지 됩니다. 시나리오 시작 및 중지에 대 한 자세한 내용은 <A href="lync-server-2013-using-start-for-the-centralized-logging-service-to-capture-logs.md">중앙 로깅 서비스에 시작을 사용 하 여 Lync server 2013에서 로그 캡처</A> 및 <A href="lync-server-2013-using-stop-for-the-centralized-logging-service.md">lync Server 2013에서 중앙 로깅 서비스에 대 한 중지 사용</A>을 참조 하세요.



</div>

문제가 발생 하면 보고 된 문제와 관련 된 두 번째 시나리오를 시작 합니다. 문제를 재현 하 고 두 번째 시나리오에 대 한 로깅을 중지 합니다. 보고 된 문제에 상대적인 로그 검색을 시작 합니다. 집계 된 로그 수집은 사이트의 모든 컴퓨터 또는 배포의 전역 범위에서 추적 메시지가 포함 된 로그 파일을 생성 합니다. 검색에서 feasibly 분석할 수 있는 것 보다 더 많은 데이터를 반환 하는 경우 (일반적으로 신호 대 잡음 비율이 라고도 함) 보다 좁은 매개 변수를 사용 하 여 다른 검색을 실행 합니다. 이 시점에서 표시 되는 패턴을 확인 하 고 문제를 보다 명확 하 게 파악 하는 데 도움이 될 수 있습니다. 최종적으로 몇 가지 구체화 된 검색을 수행한 후 문제와 관련 된 데이터를 찾아 근본 원인을 파악할 수 있습니다.

<div>


> [!TIP]  
> Lync Server에 문제가 있는 경우에는 "문제에 대해 이미 알고 있는 사항"을 사용자에 게 문의 하 여 시작 합니다. 문제 경계를 수량화 하는 경우 Lync Server에서 작업 엔터티의 상당 부분을 제거할 수 있습니다.<BR>사용자가 연락처를 찾을 때 현재 결과가 표시 되지 않는 것을 알고 있는 경우를 예로 들어 보겠습니다. 미디어 구성 요소, 엔터프라이즈 음성, 회의 및 기타 다양 한 구성 요소에서 발생 하는 문제를 찾는 것이 아닙니다. 실제로 문제가 발생 한 위치는 클라이언트에서 나 서버 쪽 문제일 수 있습니다. 연락처는 Active Directory에서 사용자 복제기에 의해 수집 되 고 주소록 서버 (ABServer)를 통해 클라이언트에 게 전달 됩니다. 이 ABServer는 RTC 데이터베이스에서 업데이트를 가져와 (사용자 복제기에서 기록 하 고) 기본적으로 1:30 AM을 주소록 파일에 모읍니다. Lync Server 클라이언트는 임의 일정에 따라 새 주소록을 검색 합니다. 프로세스가 작동 하는 방식을 알고 있으므로 사용자 복제기, ABServer가 주소록 파일을 검색 하 고 만들지 않는 경우 Active Directory에서 수집 하는 데이터와 관련 된 문제로 인해 검색을 줄일 수 있습니다. 주소록 파일을 다운로드 하는 중입니다.



</div>

</div>

<span> </span>

</div>

</div>

</div>

