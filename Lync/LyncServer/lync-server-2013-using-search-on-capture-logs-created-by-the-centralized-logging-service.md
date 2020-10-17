---
title: 중앙 로깅 서비스에서 만든 캡처 로그에 검색 사용
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using search on capture logs created by the Centralized Logging Service
ms:assetid: 1b75b218-d84f-47a7-8a0a-b7e016b1cc79
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687982(v=OCS.15)
ms:contentKeyID: 49733571
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b054f3ea8a1054be1e920fbbacbfe2e88b157ba7
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48518765"
---
# <a name="using-search-on-capture-logs-created-by-the-centralized-logging-service-in-lync-server-2013"></a>Lync Server 2013의 중앙 로깅 서비스에서 만든 캡처 로그에 검색 사용

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-02-21_

중앙 로깅 서비스의 검색 기능은 다음과 같은 이유로 인해 유용 하 고 강력 합니다.

  - 검색과 결과가 정의하는 조건을 기준으로 단일 컴퓨터, 풀, 사이트 또는 전역 범위에서 실행됩니다.

  - 처음에는 검색 범위를 넓게 지정했다가 나중에 시간, 구성 요소, 컴퓨터 등 보다 구체적인 대상이 지정된 조건으로 좁힐 수 있습니다. 같은 로그를 검색하고 검색 조건이 변경되어도 로깅 세션을 다시 실행할 필요가 없습니다.

  - 범위에 속하는 모든 컴퓨터 및 풀에서 검색 결과를 모은 다음 검색 조건의 모든 결과를 나타내는 단일 출력 파일에 수집 및 집계합니다(검색 시 실행 중이었던 시나리오 및 해당 시나리오에 의해 캡처된 데이터로 제한됨). **Snooper**, **메모장** 등의 익숙한 도구를 사용하여 배포 전체의 출력 파일 및 추적 메시지를 읽습니다.

개별 컴퓨터의 CLSAgent가 하나 이상의 시나리오(지정된 시간에 컴퓨터당 두 개의 시나리오를 실행할 수 있음)를 기준으로 로그를 만듭니다. 로그 및 로그에 연결된 인덱스와 캐시 파일은 CLSAgent를 통해 관리됩니다. 검색을 정의하고 실행하면 검색 명령은 검색할 정보를 CLSAgent에 지시합니다. 그러면 CLSAgent는 로그 파일, 캐시 파일 및 인덱스 파일에 대해 쿼리를 실행하고 검색 결과를 CLSController로 반환합니다. CLSController는 검색 범위 내의 모든 컴퓨터와 풀에서 검색 결과를 받습니다. 그런 다음 CLSController는 로그를 집계(결합)하여 시간 간격순으로 배치합니다(가장 오래된 항목부터 시간상 가장 최근 항목순).

각 검색 후 **Sync-CsClsLogging** cmdlet이 실행되며, 이 cmdlet은 검색에 사용된 캐시를 플러시합니다(CLSAgent가 유지 관리하는 캐시 파일이 아님). 캐시를 플러시하면 CLSController에 다음 검색 작업을 위한 새 로그 및 추적 파일 캡처 버퍼가 생성됩니다.

중앙 로깅 서비스의 이점을 최대한 활용 하려면 조사 중인 문제와 관련 된 컴퓨터 및 풀 로그의 추적 메시지만 반환 하도록 검색을 구성 하는 방법을 잘 이해 해야 합니다. 발행

Lync Server 관리 셸을 사용 하 여 중앙 로깅 서비스 검색 기능을 실행 하려면 CsAdministrator 또는 CsServerAdministrator의 RBAC (역할 기반 액세스 제어) 보안 그룹 또는 이러한 두 그룹 중 하나를 포함 하는 사용자 지정 RBAC 역할의 구성원 이어야 합니다. 직접 만든 사용자 지정 RBAC 역할을 포함 하 여이 cmdlet이 할당 된 모든 RBAC 역할의 목록을 반환 하려면 Lync Server 관리 셸 또는 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Lync Server 2013 cmdlet"}

예를 들면 다음과 같습니다.

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}

이 항목의 나머지 부분에서는 문제 해결 과정을 최적화하기 위해 검색을 정의하는 방법에 대해 중점적으로 설명합니다.

<div>

## <a name="to-run-a-basic-search-by-using-the-centralized-logging-service"></a>중앙 로깅 서비스를 사용 하 여 기본 검색을 실행 하려면

1.  **시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.

2.  배포의 전역 범위에서 AlwaysOn 시나리오가 실행 중인지 확인한 후 명령 프롬프트에 다음을 입력합니다.
    
        Search-CsClsLogging -OutputFilePath <string value of path and file to write the output file>
    
    <div>
    

    > [!NOTE]
    > 기본적으로 Search-CsClsLogging은 검색 결과를 콘솔로 보냅니다. 검색 결과를 파일에 저장 하려면 – OutputFilePath &lt; 문자열 정규화 된 파일 경로를 사용 &gt; 합니다. -OutputFilePath 매개 변수를 정의하려면 매개 변수의 일부분으로 경로와 파일 이름을 따옴표로 묶인 문자열 형식으로 입력합니다(예: C:\LogFiles\SearchOutput.txt). 이 예제에서는 C:\LogFiles 디렉터리가 있으며 해당 폴더에서 파일 읽기 및 쓰기 권한(수정 NTFS 권한)이 있는지 확인해야 합니다. 출력은 추가되며 기존 로그를 덮어쓰지 않습니다. 별도의 파일이 필요하면 각 검색에 대해 고유한 파일 이름을 정의합니다.

    
    </div>
    
    예를 들면 다음과 같습니다.
    
        Search-CsClsLogging -OutputFilePath "C:\LogFiles\logfile.txt"

</div>

<div>

## <a name="to-run-a-basic-search-on-a-pool-or-computer-by-using-the-centralized-logging-service"></a>중앙 로깅 서비스를 사용 하 여 풀 또는 컴퓨터에서 기본 검색을 실행 하려면

1.  검색을 특정 풀 또는 컴퓨터로 제한하려면 -Computers 매개 변수를 사용합니다(다음과 같이 컴퓨터 정규화된 이름으로 컴퓨터를 정의하고 따옴표로 묶은 다음 쉼표로 구분함).
    
        Search-CsClsLogging -Computers <string value of computer names> -OutputFilePath <string value of path and file to write the output file>
    
    예를 들면 다음과 같습니다.
    
        Search-CsClsLogging -Computers "fe01.contoso.net" -OutputFilePath "C:\LogFiles\logfile.txt"

2.  둘 이상의 컴퓨터를 검색하려면 다음과 같이 여러 컴퓨터 이름을 따옴표로 묶고 쉼표로 구분합니다.
    
        Search-CsClsLogging -Computers "fe01.contoso.net", "fe02.contoso.net", "fe03.contoso.net" -OutputFilePath "C:\LogFiles\logfile.txt"

3.  컴퓨터 하나가 아닌 전체 풀을 검색해야 하는 경우 -Computers 매개 변수를 -Pools로 변경하고 컴퓨터 이름을 제거한 다음 따옴표로 묶고 쉼표로 구분한 하나 이상의 풀로 바꿉니다.
    
    예를 들면 다음과 같습니다.
    
        Search-CsClsLogging -Pools "pool01.contoso.net" -OutputFilePath "C:\Logfiles\logfile.txt"

4.  검색 명령을 사용 하는 경우 배포에서 풀은 프런트 엔드 풀,에 지 풀, 영구 채팅 서버 풀 등 배포의 풀 일 수 있습니다.
    
    예를 들면 다음과 같습니다.
    
        Search-CsClsLogging -Pools "pool01.contoso.net", "pchatpool01.contoso.net", "intedgepool01.contoso.net" -OutputFilePath "C:\Logfiles\logfile.txt"

</div>

<div>

## <a name="to-run-a-search-by-using-time-parameters"></a>시간 매개 변수를 사용하여 검색을 실행하려면

1.  **시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.

2.  기본적으로 검색의 시간 관련 매개 변수 시작 시간은 검색 시작 시간 30분 전입니다. 즉, 오후 4시에 시작하는 검색에서는 컴퓨터 및 풀에서 오후 3시 30분에서 4시 사이에 정의하는 로그를 검색합니다. 현재 시간 60분 또는 3시간 전을 검색해야 하는 경우 -StartTime 매개 변수를 사용하여 날짜 및 시간 문자열을 설정해 검색을 시작할 시간을 지정합니다.
    
    예를 들어 –StartTime 및 –EndTime을 사용하여 시간 및 날짜 범위를 정의하면 풀에서 2012년 11월 20일 오전 8시에서 9시 사이로 검색을 정의할 수 있습니다. 다음과 같이 결과를 c:logfile.txt 파일에 쓰도록 출력 경로를 설정할 수 있습니다 \\ .
    
        Search-CsClsLogging -Pools "pool01.contoso.net" -StartTime "11/20/2012 08:00:00 AM" -EndTime "11/20/2012 09:00:00 AM" -OutputFilePath "C:\Logfiles\logfile.txt"
    
    <div>
    

    > [!NOTE]
    > 지정 하는 시간 및 날짜 문자열은 "날짜 시간" 또는 "시간 날짜"가 될 수 있습니다. "명령은 문자열을 구문 분석 하 고 날짜 및 시간에 적절 한 값을 사용 합니다.

    
    </div>

3.  2012년 11월 20일 오전 11시부터 로그를 검색하려면 -StartTime을 정의합니다. 구체적인 -EndTime을 정의하지 않는 경우 검색의 기본 시간 범위는 30분입니다. 이 경우 수행되는 검색은 정의된 컴퓨터에서 오전 11시에서 11시 30분 사이의 로그를 반환합니다.
    
    예를 들면 다음과 같습니다.
    
        Search-CsClsLogging -Pools "pool01.contoso.net" -StartTime "11/20/2012 11:00:00 AM" -OutputFilePath "C:\Logfiles\logfile.txt"

4.  특정 기간 내의 로그 검색을 수행하려면 -StartTime과 -EndTime을 정의합니다. edge01.contoso.net 컴퓨터에서 오후 1시~2시 45분의 로그를 검색해야 한다고 가정해 보겠습니다.
    
    예를 들면 다음과 같습니다.
    
        Search-CsClsLogging -Computers "edge01.contoso.net" -StartTime "11/20/2012 1:00:00 PM" -EndTime "11/20/2012 2:45:00 PM" -OutputFilePath "C:\Logfiles\logfile.txt"

</div>

<div>

## <a name="to-run-an-advanced-search-by-using-other-criteria-and-matching-options"></a>다른 조건 및 일치 옵션을 사용하여 고급 검색을 실행하려면

1.  **시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.

2.  명령을 실행하여 특정 구성 요소의 추적을 수집하려면 다음을 입력합니다.
    
        Search-CsClsLogging -Components <components to search on> -OutputFilePath <fully qualified path to output logs>
    
    예를 들면 다음과 같습니다.
    
        Search-CsClsLogging -Components "SIPStack","S4","UserServices" -OutputFilePath "C:\Logfiles\logfile.txt"
    
    이 경우 실행되는 검색은 배포의 모든 컴퓨터 및 풀에서 지난 30분 동안의 SIPStack, S4 및 UserServices에 대한 추적 구성 요소를 포함하는 모든 로그 항목을 반환합니다.

3.  동일한 구성 요소가 있는 검색을 pool01.contoso.net 이라는 프런트 엔드 풀로만 제한 하려면 다음을 입력 합니다.
    
        Search-CsClsLogging -Components "SIPStack","S4","UserServices" -OutputFilePath "C:\Logfiles\logfile.txt"

4.  매개 변수가 여러 개인 경우 명령에 사용되는 기본 검색 논리는 정의된 각 매개 변수에 대해 논리 OR을 사용하는 것입니다. **-MatchAll** 매개 변수를 지정하면 이 동작을 변경할 수 있습니다. 이렇게 하려면 다음을 입력합니다.
    
        Search-CsClsLogging -CallId "d0af828e49fa4dcb99f5f80223a634bc" -Components "SIPStack","S4","UserServices" -MatchAll -OutputFilePath "C:\Logfiles\logfile.txt"

5.  AlwaysOn과 같이 시나리오가 지속적으로 실행되도록 설정되어 있거나 장기 실행 시나리오를 정의한 경우에는 로그가 로컬 컴퓨터에서 파일 공유로 이동될 수 있습니다. 이 경우 New-CsClsConfiguration을 사용하여 새 구성을 만들거나 Set-CsClsConfiguration을 사용하여 기존 구성을 수정하는 방법으로 CacheFileNetworkFolder 매개 변수를 사용해 파일 공유를 정의합니다. 검색에서 검색할 로그 모음에 파일 공유를 포함하지 않으려면 다음과 같이 SkipNetworkLogs 매개 변수를 사용합니다.
    
        Search-CsClsLogging -Components "SIPStack","S4","UserServices" -StartTime "11/1/2012 00:00:01 AM" -EndTime "11/20/2012 2:45:00 PM" -SkipNetworkLogs -OutputFilePath "C:\Logfiles\logfile.txt"

</div>

</div>

<span> </span>

</div>

</div>

</div>

