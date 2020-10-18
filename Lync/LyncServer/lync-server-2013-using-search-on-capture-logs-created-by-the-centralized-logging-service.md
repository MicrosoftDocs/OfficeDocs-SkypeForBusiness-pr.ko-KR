---
title: 중앙 로깅 서비스에서 만든 캡처 로그에 검색 사용
description: 중앙 로깅 서비스에서 만든 캡처 로그에 검색 사용
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
ms.openlocfilehash: 2f6517dd3a9df749d2fe65f1b594b9d21204d7fa
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48580254"
---
# <a name="using-search-on-capture-logs-created-by-the-centralized-logging-service-in-lync-server-2013"></a><span data-ttu-id="8d8f2-103">Lync Server 2013의 중앙 로깅 서비스에서 만든 캡처 로그에 검색 사용</span><span class="sxs-lookup"><span data-stu-id="8d8f2-103">Using search on capture logs created by the Centralized Logging Service in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8d8f2-104">_**마지막으로 수정 된 항목:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="8d8f2-104">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="8d8f2-105">중앙 로깅 서비스의 검색 기능은 다음과 같은 이유로 인해 유용 하 고 강력 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d8f2-105">The search features in the Centralized Logging Service are useful and powerful for the following reasons:</span></span>

  - <span data-ttu-id="8d8f2-106">검색과 결과가 정의하는 조건을 기준으로 단일 컴퓨터, 풀, 사이트 또는 전역 범위에서 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="8d8f2-106">Your searches and the results are run on a single computer, a pool, a site, or a global scope, based on the criteria you define.</span></span>

  - <span data-ttu-id="8d8f2-p101">처음에는 검색 범위를 넓게 지정했다가 나중에 시간, 구성 요소, 컴퓨터 등 보다 구체적인 대상이 지정된 조건으로 좁힐 수 있습니다. 같은 로그를 검색하고 검색 조건이 변경되어도 로깅 세션을 다시 실행할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8d8f2-p101">Your searches can be initially broad and then narrowed down to more targeted criteria such as time, component, or computer. You search against the same logs and don’t need to run a logging session again when the search criteria changes.</span></span>

  - <span data-ttu-id="8d8f2-p102">범위에 속하는 모든 컴퓨터 및 풀에서 검색 결과를 모은 다음 검색 조건의 모든 결과를 나타내는 단일 출력 파일에 수집 및 집계합니다(검색 시 실행 중이었던 시나리오 및 해당 시나리오에 의해 캡처된 데이터로 제한됨). **Snooper**, **메모장** 등의 익숙한 도구를 사용하여 배포 전체의 출력 파일 및 추적 메시지를 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="8d8f2-p102">The results of your search are gathered from all computers and pools in the scope, collected and aggregated into a single output file that represents all results of the search criteria (limited to the scenarios that have been running and the data captured by the scenarios). You use familiar tools such as **Snooper** or **Notepad** to read the output file and the trace messages from across your deployment.</span></span>

<span data-ttu-id="8d8f2-p103">개별 컴퓨터의 CLSAgent가 하나 이상의 시나리오(지정된 시간에 컴퓨터당 두 개의 시나리오를 실행할 수 있음)를 기준으로 로그를 만듭니다. 로그 및 로그에 연결된 인덱스와 캐시 파일은 CLSAgent를 통해 관리됩니다. 검색을 정의하고 실행하면 검색 명령은 검색할 정보를 CLSAgent에 지시합니다. 그러면 CLSAgent는 로그 파일, 캐시 파일 및 인덱스 파일에 대해 쿼리를 실행하고 검색 결과를 CLSController로 반환합니다. CLSController는 검색 범위 내의 모든 컴퓨터와 풀에서 검색 결과를 받습니다. 그런 다음 CLSController는 로그를 집계(결합)하여 시간 간격순으로 배치합니다(가장 오래된 항목부터 시간상 가장 최근 항목순).</span><span class="sxs-lookup"><span data-stu-id="8d8f2-p103">The CLSAgent on each individual computer creates the logs based on the scenario or scenarios (two scenarios per computer can be running at any given time). The logs and their associated index and cache files are managed by the CLSAgent. When you define and execute a search, the search command instructs the CLSAgent on what information should be retrieved. The CLSAgent executes the query against the log files, cache files, and index files and returns the results of the search to the CLSContoller. The CLSController receives the search results from all computers and pools in the scope of the search. The CLSController then aggregates (combines) the logs and puts them into time delta order, oldest entry first, and proceeding in time to the most recent entry last.</span></span>

<span data-ttu-id="8d8f2-117">각 검색 후 **Sync-CsClsLogging** cmdlet이 실행되며, 이 cmdlet은 검색에 사용된 캐시를 플러시합니다(CLSAgent가 유지 관리하는 캐시 파일이 아님).</span><span class="sxs-lookup"><span data-stu-id="8d8f2-117">After each search, the **Sync-CsClsLogging** cmdlet is run and it flushes the cache used by searches (not to be confused with the cache files maintained by the CLSAgent).</span></span> <span data-ttu-id="8d8f2-118">캐시를 플러시하면 CLSController에 다음 검색 작업을 위한 새 로그 및 추적 파일 캡처 버퍼가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="8d8f2-118">Flushing the cache helps to ensure that there is a clean log and trace file capture buffer at the CLSController for the next search operation.</span></span>

<span data-ttu-id="8d8f2-119">중앙 로깅 서비스의 이점을 최대한 활용 하려면 조사 중인 문제와 관련 된 컴퓨터 및 풀 로그의 추적 메시지만 반환 하도록 검색을 구성 하는 방법을 잘 이해 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d8f2-119">To get the most benefit from the Centralized Logging Service, you need a good understanding of how to configure search to return only trace messages from the computer and pool logs that are relevant to the issue that you are researching.</span></span> <span data-ttu-id="8d8f2-120">발행</span><span class="sxs-lookup"><span data-stu-id="8d8f2-120">issues</span></span>

<span data-ttu-id="8d8f2-121">Lync Server 관리 셸을 사용 하 여 중앙 로깅 서비스 검색 기능을 실행 하려면 CsAdministrator 또는 CsServerAdministrator의 RBAC (역할 기반 액세스 제어) 보안 그룹 또는 이러한 두 그룹 중 하나를 포함 하는 사용자 지정 RBAC 역할의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d8f2-121">To run the Centralized Logging Service search functions by using the Lync Server Management Shell, you must be a member of either the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> <span data-ttu-id="8d8f2-122">직접 만든 사용자 지정 RBAC 역할을 포함 하 여이 cmdlet이 할당 된 모든 RBAC 역할의 목록을 반환 하려면 Lync Server 관리 셸 또는 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d8f2-122">To return a list of all the RBAC roles that this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Lync Server Management Shell or the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Lync Server 2013 cmdlet"}

<span data-ttu-id="8d8f2-123">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="8d8f2-123">For example:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}

<span data-ttu-id="8d8f2-124">이 항목의 나머지 부분에서는 문제 해결 과정을 최적화하기 위해 검색을 정의하는 방법에 대해 중점적으로 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8d8f2-124">The remainder of this topic focuses on how to define a search to optimize your troubleshooting.</span></span>

<div>

## <a name="to-run-a-basic-search-by-using-the-centralized-logging-service"></a><span data-ttu-id="8d8f2-125">중앙 로깅 서비스를 사용 하 여 기본 검색을 실행 하려면</span><span class="sxs-lookup"><span data-stu-id="8d8f2-125">To run a basic search by using the Centralized Logging Service</span></span>

1.  <span data-ttu-id="8d8f2-126">**시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="8d8f2-126">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="8d8f2-127">배포의 전역 범위에서 AlwaysOn 시나리오가 실행 중인지 확인한 후 명령 프롬프트에 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="8d8f2-127">Make sure that you have the AlwaysOn scenario running in your deployment at the global scope and then type the following at a command prompt:</span></span>
    
        Search-CsClsLogging -OutputFilePath <string value of path and file to write the output file>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="8d8f2-128">기본적으로 Search-CsClsLogging은 검색 결과를 콘솔로 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="8d8f2-128">By default, Search-CsClsLogging sends the results of the search to the console.</span></span> <span data-ttu-id="8d8f2-129">검색 결과를 파일에 저장 하려면 – OutputFilePath &lt; 문자열 정규화 된 파일 경로를 사용 &gt; 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d8f2-129">If you want to save the search results to a file, use –OutputFilePath &lt;string fully qualified file path&gt;.</span></span> <span data-ttu-id="8d8f2-130">-OutputFilePath 매개 변수를 정의하려면 매개 변수의 일부분으로 경로와 파일 이름을 따옴표로 묶인 문자열 형식으로 입력합니다(예: C:\LogFiles\SearchOutput.txt).</span><span class="sxs-lookup"><span data-stu-id="8d8f2-130">To define the –OutputFilePath parameter, supply a path and a filename as part of the parameter in a string format enclosed in quotation marks (for example; C:\LogFiles\SearchOutput.txt).</span></span> <span data-ttu-id="8d8f2-131">이 예제에서는 C:\LogFiles 디렉터리가 있으며 해당 폴더에서 파일 읽기 및 쓰기 권한(수정 NTFS 권한)이 있는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d8f2-131">In this example, you must ensure that the directory C:\LogFiles exists and that you have permissions to Read and Write (NTFS permission Modify) files in the folder.</span></span> <span data-ttu-id="8d8f2-132">출력은 추가되며 기존 로그를 덮어쓰지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8d8f2-132">The output is appended to and is not overwritten.</span></span> <span data-ttu-id="8d8f2-133">별도의 파일이 필요하면 각 검색에 대해 고유한 파일 이름을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="8d8f2-133">If you need separate files, define a distinct file name for each search.</span></span>

    
    </div>
    
    <span data-ttu-id="8d8f2-134">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="8d8f2-134">For example:</span></span>
    
        Search-CsClsLogging -OutputFilePath "C:\LogFiles\logfile.txt"

</div>

<div>

## <a name="to-run-a-basic-search-on-a-pool-or-computer-by-using-the-centralized-logging-service"></a><span data-ttu-id="8d8f2-135">중앙 로깅 서비스를 사용 하 여 풀 또는 컴퓨터에서 기본 검색을 실행 하려면</span><span class="sxs-lookup"><span data-stu-id="8d8f2-135">To run a basic search on a pool or computer by using the Centralized Logging Service</span></span>

1.  <span data-ttu-id="8d8f2-136">검색을 특정 풀 또는 컴퓨터로 제한하려면 -Computers 매개 변수를 사용합니다(다음과 같이 컴퓨터 정규화된 이름으로 컴퓨터를 정의하고 따옴표로 묶은 다음 쉼표로 구분함).</span><span class="sxs-lookup"><span data-stu-id="8d8f2-136">To limit the search to a specific pool or computer, use the –Computers parameter with the computer defined by a computer fully qualified name, enclosed in quotation marks and separated by a comma as follows:</span></span>
    
        Search-CsClsLogging -Computers <string value of computer names> -OutputFilePath <string value of path and file to write the output file>
    
    <span data-ttu-id="8d8f2-137">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="8d8f2-137">For example:</span></span>
    
        Search-CsClsLogging -Computers "fe01.contoso.net" -OutputFilePath "C:\LogFiles\logfile.txt"

2.  <span data-ttu-id="8d8f2-138">둘 이상의 컴퓨터를 검색하려면 다음과 같이 여러 컴퓨터 이름을 따옴표로 묶고 쉼표로 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="8d8f2-138">To search more than one computer, type multiple computer names enclosed in quotation marks and separated by commas, such as the following:</span></span>
    
        Search-CsClsLogging -Computers "fe01.contoso.net", "fe02.contoso.net", "fe03.contoso.net" -OutputFilePath "C:\LogFiles\logfile.txt"

3.  <span data-ttu-id="8d8f2-139">컴퓨터 하나가 아닌 전체 풀을 검색해야 하는 경우 -Computers 매개 변수를 -Pools로 변경하고 컴퓨터 이름을 제거한 다음 따옴표로 묶고 쉼표로 구분한 하나 이상의 풀로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="8d8f2-139">If you need to search an entire pool instead of a single computer, change the –Computers parameter to –Pools, remove the computer name, and replace it with the pool or pools in quotation marks separated by commas.</span></span>
    
    <span data-ttu-id="8d8f2-140">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="8d8f2-140">For example:</span></span>
    
        Search-CsClsLogging -Pools "pool01.contoso.net" -OutputFilePath "C:\Logfiles\logfile.txt"

4.  <span data-ttu-id="8d8f2-141">검색 명령을 사용 하는 경우 배포에서 풀은 프런트 엔드 풀,에 지 풀, 영구 채팅 서버 풀 등 배포의 풀 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d8f2-141">When using the search commands, pools can be any pool in your deployment, such as Front End pools, Edge pools, Persistent Chat Server pools, or others that are defined as a pool in your deployment.</span></span>
    
    <span data-ttu-id="8d8f2-142">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="8d8f2-142">For example:</span></span>
    
        Search-CsClsLogging -Pools "pool01.contoso.net", "pchatpool01.contoso.net", "intedgepool01.contoso.net" -OutputFilePath "C:\Logfiles\logfile.txt"

</div>

<div>

## <a name="to-run-a-search-by-using-time-parameters"></a><span data-ttu-id="8d8f2-143">시간 매개 변수를 사용하여 검색을 실행하려면</span><span class="sxs-lookup"><span data-stu-id="8d8f2-143">To run a search by using time parameters</span></span>

1.  <span data-ttu-id="8d8f2-144">**시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="8d8f2-144">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="8d8f2-p108">기본적으로 검색의 시간 관련 매개 변수 시작 시간은 검색 시작 시간 30분 전입니다. 즉, 오후 4시에 시작하는 검색에서는 컴퓨터 및 풀에서 오후 3시 30분에서 4시 사이에 정의하는 로그를 검색합니다. 현재 시간 60분 또는 3시간 전을 검색해야 하는 경우 -StartTime 매개 변수를 사용하여 날짜 및 시간 문자열을 설정해 검색을 시작할 시간을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8d8f2-p108">By default, the beginning time for a search's time-specific parameters is 30 minutes prior to the time you initiate the search. In other words, if you initiate your search at 4:00:00 PM, the search will search the logs for the computers and pools that you define from 3:30:00 PM until 4:00:00 PM. If you need to search 60 minutes or 3 hours prior to the current time, use the –StartTime parameter and set the date and time string to indicate the time you want the search to start.</span></span>
    
    <span data-ttu-id="8d8f2-148">예를 들어 –StartTime 및 –EndTime을 사용하여 시간 및 날짜 범위를 정의하면 풀에서 2012년 11월 20일 오전 8시에서 9시 사이로 검색을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d8f2-148">For example, by using –StartTime and –EndTime to define a time and date range, you can define a search between 8 AM and 9 AM on 11/20/2012 on your pool.</span></span> <span data-ttu-id="8d8f2-149">다음과 같이 결과를 c:logfile.txt 파일에 쓰도록 출력 경로를 설정할 수 있습니다 \\ .</span><span class="sxs-lookup"><span data-stu-id="8d8f2-149">You can set the output path to write the results to a file named c:\\logfile.txt as follows:</span></span>
    
        Search-CsClsLogging -Pools "pool01.contoso.net" -StartTime "11/20/2012 08:00:00 AM" -EndTime "11/20/2012 09:00:00 AM" -OutputFilePath "C:\Logfiles\logfile.txt"
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="8d8f2-150">지정 하는 시간 및 날짜 문자열은 "날짜 시간" 또는 "시간 날짜"가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d8f2-150">The time and date string that you specify can be "date time" or "time date.</span></span> <span data-ttu-id="8d8f2-151">"명령은 문자열을 구문 분석 하 고 날짜 및 시간에 적절 한 값을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d8f2-151">" The command will parse the string and use the appropriate values for date and time.</span></span>

    
    </div>

3.  <span data-ttu-id="8d8f2-p111">2012년 11월 20일 오전 11시부터 로그를 검색하려면 -StartTime을 정의합니다. 구체적인 -EndTime을 정의하지 않는 경우 검색의 기본 시간 범위는 30분입니다. 이 경우 수행되는 검색은 정의된 컴퓨터에서 오전 11시에서 11시 30분 사이의 로그를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="8d8f2-p111">If you want to retrieve logs beginning at 11:00:00 AM on 11/20/2012, you define the –StartTime. The default time range for the search is 30 minutes unless you define a specific –EndTime. The resulting search will return logs from the defined computer or pools from 11:00:00 AM to 11:30:00 AM.</span></span>
    
    <span data-ttu-id="8d8f2-155">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="8d8f2-155">For example:</span></span>
    
        Search-CsClsLogging -Pools "pool01.contoso.net" -StartTime "11/20/2012 11:00:00 AM" -OutputFilePath "C:\Logfiles\logfile.txt"

4.  <span data-ttu-id="8d8f2-p112">특정 기간 내의 로그 검색을 수행하려면 -StartTime과 -EndTime을 정의합니다. edge01.contoso.net 컴퓨터에서 오후 1시~2시 45분의 로그를 검색해야 한다고 가정해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="8d8f2-p112">To conduct a search of logs within a specific period of time, define a –StartTime and an –EndTime. You need logs from 1 PM to 2:45 PM on the computer edge01.contoso.net.</span></span>
    
    <span data-ttu-id="8d8f2-158">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="8d8f2-158">For example:</span></span>
    
        Search-CsClsLogging -Computers "edge01.contoso.net" -StartTime "11/20/2012 1:00:00 PM" -EndTime "11/20/2012 2:45:00 PM" -OutputFilePath "C:\Logfiles\logfile.txt"

</div>

<div>

## <a name="to-run-an-advanced-search-by-using-other-criteria-and-matching-options"></a><span data-ttu-id="8d8f2-159">다른 조건 및 일치 옵션을 사용하여 고급 검색을 실행하려면</span><span class="sxs-lookup"><span data-stu-id="8d8f2-159">To run an advanced search by using other criteria and matching options</span></span>

1.  <span data-ttu-id="8d8f2-160">**시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="8d8f2-160">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="8d8f2-161">명령을 실행하여 특정 구성 요소의 추적을 수집하려면 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="8d8f2-161">To run a command to collect traces for specific components, type the following:</span></span>
    
        Search-CsClsLogging -Components <components to search on> -OutputFilePath <fully qualified path to output logs>
    
    <span data-ttu-id="8d8f2-162">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="8d8f2-162">For example:</span></span>
    
        Search-CsClsLogging -Components "SIPStack","S4","UserServices" -OutputFilePath "C:\Logfiles\logfile.txt"
    
    <span data-ttu-id="8d8f2-163">이 경우 실행되는 검색은 배포의 모든 컴퓨터 및 풀에서 지난 30분 동안의 SIPStack, S4 및 UserServices에 대한 추적 구성 요소를 포함하는 모든 로그 항목을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="8d8f2-163">The resulting search returns all log entries that have trace components for SIPStack, S4, and UserServices on all computers and pools in your deployment for the past 30 minutes.</span></span>

3.  <span data-ttu-id="8d8f2-164">동일한 구성 요소가 있는 검색을 pool01.contoso.net 이라는 프런트 엔드 풀로만 제한 하려면 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d8f2-164">To limit the search with the same components to just your Front End pool named pool01.contoso.net, type:</span></span>
    
        Search-CsClsLogging -Components "SIPStack","S4","UserServices" -OutputFilePath "C:\Logfiles\logfile.txt"

4.  <span data-ttu-id="8d8f2-p113">매개 변수가 여러 개인 경우 명령에 사용되는 기본 검색 논리는 정의된 각 매개 변수에 대해 논리 OR을 사용하는 것입니다. **-MatchAll** 매개 변수를 지정하면 이 동작을 변경할 수 있습니다. 이렇게 하려면 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="8d8f2-p113">The default search logic for commands with multiple parameters is to use the logical OR with each of the defined parameters. You can change this behavior by specifying the **–MatchAll** parameter. To do this, type the following:</span></span>
    
        Search-CsClsLogging -CallId "d0af828e49fa4dcb99f5f80223a634bc" -Components "SIPStack","S4","UserServices" -MatchAll -OutputFilePath "C:\Logfiles\logfile.txt"

5.  <span data-ttu-id="8d8f2-p114">AlwaysOn과 같이 시나리오가 지속적으로 실행되도록 설정되어 있거나 장기 실행 시나리오를 정의한 경우에는 로그가 로컬 컴퓨터에서 파일 공유로 이동될 수 있습니다. 이 경우 New-CsClsConfiguration을 사용하여 새 구성을 만들거나 Set-CsClsConfiguration을 사용하여 기존 구성을 수정하는 방법으로 CacheFileNetworkFolder 매개 변수를 사용해 파일 공유를 정의합니다. 검색에서 검색할 로그 모음에 파일 공유를 포함하지 않으려면 다음과 같이 SkipNetworkLogs 매개 변수를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8d8f2-p114">If your scenarios are set to run constantly, such as AlwaysOn, or you have defined a long-running scenario logs may roll off of the local machine onto the file share. You define the file share by using the CacheFileNetworkFolder parameter by using New-CsClsConfiguration to create a new configuration or modifying an existing configuration with Set-CsClsConfiguration. If you do not want the search to include the file share in the collection of logs to search, use the SkipNetworkLogs parameter as follows:</span></span>
    
        Search-CsClsLogging -Components "SIPStack","S4","UserServices" -StartTime "11/1/2012 00:00:01 AM" -EndTime "11/20/2012 2:45:00 PM" -SkipNetworkLogs -OutputFilePath "C:\Logfiles\logfile.txt"

</div>

</div>

<span> </span>

</div>

</div>

</div>

