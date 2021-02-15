---
title: 비즈니스용 Skype 서버의 중앙 로깅 서비스에서 만든 캡처 로그 검색
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 1b75b218-d84f-47a7-8a0a-b7e016b1cc79
description: '요약: 비즈니스용 Skype 서버 2015에서 중앙 로깅 서비스 캡처 로그를 검색하고 읽는 방법을 설명하는 문서를 제공합니다.'
ms.openlocfilehash: 1a030e18f9e59fa26c4bd51aa8c6e69dd96004ba
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49835128"
---
# <a name="search-capture-logs-created-by-the-centralized-logging-service-in-skype-for-business-server-2015"></a><span data-ttu-id="f9cb9-103">비즈니스용 Skype 서버의 중앙 로깅 서비스에서 만든 캡처 로그 검색</span><span class="sxs-lookup"><span data-stu-id="f9cb9-103">Search capture logs created by the Centralized Logging Service in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="f9cb9-104">**요약:** 비즈니스용 Skype 서버 2015에서 중앙 로깅 서비스 캡처 로그를 검색하고 읽는 방법을 학습합니다.</span><span class="sxs-lookup"><span data-stu-id="f9cb9-104">**Summary:** Learn how to search and read Centralized Logging Service capture logs in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="f9cb9-105">중앙 로깅 서비스의 검색 기능은 다음과 같은 이유로 유용하고 강력합니다.</span><span class="sxs-lookup"><span data-stu-id="f9cb9-105">The search features in the Centralized Logging Service are useful and powerful for the following reasons:</span></span> 
  
- <span data-ttu-id="f9cb9-106">검색과 결과가 정의하는 조건을 기준으로 단일 컴퓨터, 풀, 사이트 또는 전역 범위에서 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="f9cb9-106">Your searches and the results are run on a single computer, a pool, a site, or a global scope, based on the criteria you define.</span></span>
    
- <span data-ttu-id="f9cb9-107">처음에는 검색 범위를 넓게 지정했다가 나중에 시간, 구성 요소, 컴퓨터 등 보다 구체적인 대상이 지정된 조건으로 좁힐 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9cb9-107">Your searches can be initially broad and then narrowed down to more targeted criteria such as time, component, or computer.</span></span> <span data-ttu-id="f9cb9-108">동일한 로그를 검색하며 검색 조건이 변경될 때 로깅 세션을 다시 실행할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f9cb9-108">You search against the same logs and don't need to run a logging session again when the search criteria changes.</span></span>
    
- <span data-ttu-id="f9cb9-p102">범위에 속하는 모든 컴퓨터 및 풀에서 검색 결과를 모은 다음 검색 조건의 모든 결과를 나타내는 단일 출력 파일에 수집 및 집계합니다(검색 시 실행 중이었던 시나리오 및 해당 시나리오에 의해 캡처된 데이터로 제한됨). **Snooper**, **메모장** 등의 익숙한 도구를 사용하여 배포 전체의 출력 파일 및 추적 메시지를 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="f9cb9-p102">The results of your search are gathered from all computers and pools in the scope, collected and aggregated into a single output file that represents all results of the search criteria (limited to the scenarios that have been running and the data captured by the scenarios). You use familiar tools such as **Snooper** or **Notepad** to read the output file and the trace messages from across your deployment.</span></span>
    
<span data-ttu-id="f9cb9-p103">개별 컴퓨터의 CLSAgent가 하나 이상의 시나리오(지정된 시간에 컴퓨터당 두 개의 시나리오를 실행할 수 있음)를 기준으로 로그를 만듭니다. 로그 및 로그에 연결된 인덱스와 캐시 파일은 CLSAgent를 통해 관리됩니다. 검색을 정의하고 실행하면 검색 명령은 검색할 정보를 CLSAgent에 지시합니다. 그러면 CLSAgent는 로그 파일, 캐시 파일 및 인덱스 파일에 대해 쿼리를 실행하고 검색 결과를 CLSController로 반환합니다. CLSController는 검색 범위 내의 모든 컴퓨터와 풀에서 검색 결과를 받습니다. 그런 다음 CLSController는 로그를 집계(결합)하여 시간 간격순으로 배치합니다(가장 오래된 항목부터 시간상 가장 최근 항목순).</span><span class="sxs-lookup"><span data-stu-id="f9cb9-p103">The CLSAgent on each individual computer creates the logs based on the scenario or scenarios (two scenarios per computer can be running at any given time). The logs and their associated index and cache files are managed by the CLSAgent. When you define and execute a search, the search command instructs the CLSAgent on what information should be retrieved. The CLSAgent executes the query against the log files, cache files, and index files and returns the results of the search to the CLSContoller. The CLSController receives the search results from all computers and pools in the scope of the search. The CLSController then aggregates (combines) the logs and puts them into time delta order, oldest entry first, and proceeding in time to the most recent entry last.</span></span>
  
<span data-ttu-id="f9cb9-117">각 검색 후 **Sync-CsClsLogging** cmdlet이 실행되며, 이 cmdlet은 검색에 사용된 캐시를 플러시합니다(CLSAgent가 유지 관리하는 캐시 파일이 아님).</span><span class="sxs-lookup"><span data-stu-id="f9cb9-117">After each search, the **Sync-CsClsLogging** cmdlet is run and it flushes the cache used by searches (not to be confused with the cache files maintained by the CLSAgent).</span></span> <span data-ttu-id="f9cb9-118">캐시를 플러시하면 CLSController에 다음 검색 작업을 위한 새 로그 및 추적 파일 캡처 버퍼가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="f9cb9-118">Flushing the cache helps to ensure that there is a clean log and trace file capture buffer at the CLSController for the next search operation.</span></span>
  
<span data-ttu-id="f9cb9-119">중앙 로깅 서비스를 가장 잘 이용하려면 검색할 문제와 관련된 컴퓨터 및 풀 로그에서 추적 메시지만 반환하도록 검색을 구성하는 방법을 잘 이해해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9cb9-119">To get the most benefit from the Centralized Logging Service, you need a good understanding of how to configure search to return only trace messages from the computer and pool logs that are relevant to the issue that you are researching.</span></span> <span data-ttu-id="f9cb9-120">issues</span><span class="sxs-lookup"><span data-stu-id="f9cb9-120">issues</span></span>
  
<span data-ttu-id="f9cb9-121">비즈니스용 Skype 서버 관리 셸을 사용하여 중앙 로깅 서비스 검색 기능을 실행하려면 CsAdministrator 또는 CsServerAdministrator RBAC(역할 기반 액세스 제어) 보안 그룹의 구성원 또는 이러한 두 그룹 중 하나를 포함하는 사용자 지정 RBAC 역할의 구성원이 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9cb9-121">To run the Centralized Logging Service search functions by using the Skype for Business Server Management Shell, you must be a member of either the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> <span data-ttu-id="f9cb9-122">직접 만든 사용자 지정 RBAC 역할을 포함하여 이 cmdlet이 할당된 모든 RBAC 역할의 목록을 반환하기 위해 비즈니스용 Skype 서버 관리 셸 또는 Windows PowerShell 프롬프트에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="f9cb9-122">To return a list of all the RBAC roles that this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Skype for Business Server Management Shell or the Windows PowerShell prompt:</span></span>
  
```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Skype for Business Server 2015 cmdlet"}
```

<span data-ttu-id="f9cb9-123">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f9cb9-123">For example:</span></span>
  
```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

<span data-ttu-id="f9cb9-124">이 항목의 나머지 부분에서는 문제 해결 과정을 최적화하기 위해 검색을 정의하는 방법에 대해 중점적으로 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f9cb9-124">The remainder of this topic focuses on how to define a search to optimize your troubleshooting.</span></span>
  
### <a name="to-run-a-basic-search-by-using-the-centralized-logging-service"></a><span data-ttu-id="f9cb9-125">중앙 로깅 서비스를 사용하여 기본 검색을 실행하기 위해</span><span class="sxs-lookup"><span data-stu-id="f9cb9-125">To run a basic search by using the Centralized Logging Service</span></span>

1. <span data-ttu-id="f9cb9-126">비즈니스용 Skype 서버 관리 셸 시작: **시작,** **모든** 프로그램, 비즈니스용 **Skype 2015,** 비즈니스용 Skype 서버 관리 셸을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="f9cb9-126">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="f9cb9-127">배포의 전역 범위에서 AlwaysOn 시나리오가 실행 중인지 확인한 후 명령 프롬프트에 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="f9cb9-127">Make sure that you have the AlwaysOn scenario running in your deployment at the global scope and then type the following at a command prompt:</span></span>
    
   ```PowerShell
   Search-CsClsLogging -OutputFilePath <string value of path and file to write the output file>
   ```

> [!NOTE]
> <span data-ttu-id="f9cb9-128">기본적으로 Search-CsClsLogging은 검색 결과를 콘솔로 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="f9cb9-128">By default, Search-CsClsLogging sends the results of the search to the console.</span></span> <span data-ttu-id="f9cb9-129">검색 결과를 파일에 저장하려는 경우 -OutputFilePath를 사용  _\<string fully qualified file path\>_ 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9cb9-129">If you want to save the search results to a file, use -OutputFilePath  _\<string fully qualified file path\>_.</span></span> <span data-ttu-id="f9cb9-130">-OutputFilePath 매개 변수를 정의하기 위해 매개 변수의 일부로 경로와 파일 이름을 인용 부호(예: C:\LogFiles\SearchOutput.txt)로 묶은 문자열 형식으로 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f9cb9-130">To define the -OutputFilePath parameter, supply a path and a filename as part of the parameter in a string format enclosed in quotation marks (for example; C:\LogFiles\SearchOutput.txt).</span></span> <span data-ttu-id="f9cb9-131">이 예제에서는 C:\LogFiles 디렉터리가 있으며 해당 폴더에서 파일 읽기 및 쓰기 권한(수정 NTFS 권한)이 있는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9cb9-131">In this example, you must ensure that the directory C:\LogFiles exists and that you have permissions to Read and Write (NTFS permission Modify) files in the folder.</span></span> <span data-ttu-id="f9cb9-132">출력은 추가되며 기존 로그를 덮어쓰지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f9cb9-132">The output is appended to and is not overwritten.</span></span> <span data-ttu-id="f9cb9-133">별도의 파일이 필요하면 각 검색에 대해 고유한 파일 이름을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="f9cb9-133">If you need separate files, define a distinct file name for each search.</span></span> 
  
<span data-ttu-id="f9cb9-134">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f9cb9-134">For example:</span></span>
    
  ```PowerShell
  Search-CsClsLogging -OutputFilePath "C:\LogFiles\logfile.txt"
  ```

### <a name="to-run-a-basic-search-on-a-pool-or-computer-by-using-the-centralized-logging-service"></a><span data-ttu-id="f9cb9-135">중앙 로깅 서비스를 사용하여 풀 또는 컴퓨터에서 기본 검색을 실행하려면</span><span class="sxs-lookup"><span data-stu-id="f9cb9-135">To run a basic search on a pool or computer by using the Centralized Logging Service</span></span>

1. <span data-ttu-id="f9cb9-136">검색을 특정 풀 또는 컴퓨터로 제한하려면 컴퓨터의 정식 이름으로 정의된 컴퓨터와 함께 -Computers 매개 변수를 사용하며 따따오기 표시로 묶고 다음과 같이 COMMA로 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="f9cb9-136">To limit the search to a specific pool or computer, use the -Computers parameter with the computer defined by a computer fully qualified name, enclosed in quotation marks and separated by a comma as follows:</span></span>
    
   ```PowerShell
   Search-CsClsLogging -Computers <string value of computer names> -OutputFilePath <string value of path and file to write the output file>
   ```

<span data-ttu-id="f9cb9-137">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f9cb9-137">For example:</span></span>
    
  ```PowerShell
  Search-CsClsLogging -Computers "fe01.contoso.net" -OutputFilePath "C:\LogFiles\logfile.txt"
  ```

2. <span data-ttu-id="f9cb9-138">둘 이상의 컴퓨터를 검색하려면 다음과 같이 여러 컴퓨터 이름을 따옴표로 묶고 쉼표로 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="f9cb9-138">To search more than one computer, type multiple computer names enclosed in quotation marks and separated by commas, such as the following:</span></span>
    
   ```PowerShell
   Search-CsClsLogging -Computers "fe01.contoso.net", "fe02.contoso.net", "fe03.contoso.net" -OutputFilePath "C:\LogFiles\logfile.txt"
   ```

3. <span data-ttu-id="f9cb9-139">단일 컴퓨터 대신 전체 풀을 검색해야 하는 경우 -Computers 매개 변수를 -Pools로 변경하고 컴퓨터 이름을 제거한 다음 0.0으로 구분된 따량 표시의 풀 또는 풀로 바꿔야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9cb9-139">If you need to search an entire pool instead of a single computer, change the -Computers parameter to -Pools, remove the computer name, and replace it with the pool or pools in quotation marks separated by commas.</span></span>
    
    <span data-ttu-id="f9cb9-140">예시:</span><span class="sxs-lookup"><span data-stu-id="f9cb9-140">For example:</span></span>
    
   ```PowerShell
   Search-CsClsLogging -Pools "pool01.contoso.net" -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

4. <span data-ttu-id="f9cb9-141">검색 명령을 사용하는 경우 풀은 배포의 모든 풀(예: 프런트 엔드 풀, 에지 풀, 영구 채팅 서버 풀 또는 배포에서 풀로 정의된 다른 풀)일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9cb9-141">When using the search commands, pools can be any pool in your deployment, such as Front End pools, Edge pools, Persistent Chat Server pools, or others that are defined as a pool in your deployment.</span></span>
    
    <span data-ttu-id="f9cb9-142">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f9cb9-142">For example:</span></span>
    
   ```PowerShell
   Search-CsClsLogging -Pools "pool01.contoso.net", "pchatpool01.contoso.net", "intedgepool01.contoso.net" -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

### <a name="to-run-a-search-by-using-time-parameters"></a><span data-ttu-id="f9cb9-143">시간 매개 변수를 사용하여 검색을 실행하려면</span><span class="sxs-lookup"><span data-stu-id="f9cb9-143">To run a search by using time parameters</span></span>

1. <span data-ttu-id="f9cb9-144">비즈니스용 Skype 서버 관리 셸 시작: **시작,** **모든** 프로그램, 비즈니스용 **Skype 2015,** 비즈니스용 Skype 서버 관리 셸을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="f9cb9-144">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="f9cb9-145">기본적으로 검색의 시간별 매개 변수의 시작 시간은 검색을 시작한 후 5분 전인 25분입니다.</span><span class="sxs-lookup"><span data-stu-id="f9cb9-145">By default, the beginning time for a search's time-specific parameters is 25 minutes prior to five minutes after the time you initiate the search.</span></span> <span data-ttu-id="f9cb9-146">즉, 오후 4:00:00에 검색하는 경우 검색 시작 시간은 오후 3시 35분에서 오후 4시 5분까지로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f9cb9-146">In other words, if we search at 4:00:00 PM, then the search start time will show as 3:35:00 PM to 4:05:00 PM.</span></span> <span data-ttu-id="f9cb9-147">현재 시간 60분 또는 3시간 전에 검색해야 하는 경우 -StartTime 매개 변수를 사용하여 날짜 및 시간 문자열을 설정하여 검색을 시작할 시간을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f9cb9-147">If you need to search 60 minutes or 3 hours prior to the current time, use the -StartTime parameter and set the date and time string to indicate the time you want the search to start.</span></span> 
    
    <span data-ttu-id="f9cb9-148">예를 들어 -StartTime 및 -EndTime을 사용하여 시간 및 날짜 범위를 정의하여 풀에서 2012년 11월 20일 오전 8시에서 9시 사이에 검색을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9cb9-148">For example, by using -StartTime and -EndTime to define a time and date range, you can define a search between 8 AM and 9 AM on 11/20/2012 on your pool.</span></span> <span data-ttu-id="f9cb9-149">그리고 다음과 같이 결과를 c:\logfile.txt라는 파일에 쓰도록 출력 경로를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9cb9-149">You can set the output path to write the results to a file named c:\logfile.txt as follows:</span></span>
    
   ```PowerShell
   Search-CsClsLogging -Pools "pool01.contoso.net" -StartTime "11/20/2012 08:00:00 AM" -EndTime "11/20/2012 09:00:00 AM" -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

> [!NOTE]
> <span data-ttu-id="f9cb9-150">지정하는 시간 및 날짜 문자열은 "날짜 시간" 또는 "시간 날짜"일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9cb9-150">The time and date string that you specify can be "date time" or "time date.</span></span> <span data-ttu-id="f9cb9-151">"이 명령은 문자열을 구문 분석하고 날짜 및 시간의 적절한 값과 cmdlet을 실행 중인 컴퓨터의 로컬 및 문화권 설정을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f9cb9-151">" The command will parse the string and use the appropriate values for date and time and your locale and culture settings on the machine you are running cmdlet from.</span></span> 
  
3. <span data-ttu-id="f9cb9-152">2012년 11월 20일 오전 11시부터 로그를 검색하려면 -StartTime을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="f9cb9-152">If you want to retrieve logs beginning at 11:00:00 AM on 11/20/2012, you define the -StartTime.</span></span> <span data-ttu-id="f9cb9-153">특정 -EndTime을 정의하지 않는 한 검색의 기본 시간 범위는 30분입니다.</span><span class="sxs-lookup"><span data-stu-id="f9cb9-153">The default time range for the search is 30 minutes unless you define a specific -EndTime.</span></span> <span data-ttu-id="f9cb9-154">이 경우 수행되는 검색은 정의된 컴퓨터에서 오전 11시에서 11시 30분 사이의 로그를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="f9cb9-154">The resulting search will return logs from the defined computer or pools from 11:00:00 AM to 11:30:00 AM.</span></span>
    
<span data-ttu-id="f9cb9-155">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f9cb9-155">For example:</span></span>
    
  ```PowerShell
  Search-CsClsLogging -Pools "pool01.contoso.net" -StartTime "11/20/2012 11:00:00 AM" -OutputFilePath "C:\Logfiles\logfile.txt"
  ```

4. <span data-ttu-id="f9cb9-156">특정 기간 내에 로그 검색을 수행하려면 -StartTime 및 -EndTime을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="f9cb9-156">To conduct a search of logs within a specific period of time, define a -StartTime and an -EndTime.</span></span> <span data-ttu-id="f9cb9-157">edge01.contoso.net 컴퓨터에서 오후 1시~2시 45분의 로그를 검색해야 한다고 가정해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="f9cb9-157">You need logs from 1 PM to 2:45 PM on the computer edge01.contoso.net.</span></span> 
    
<span data-ttu-id="f9cb9-158">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f9cb9-158">For example:</span></span>
    
  ```
  Search-CsClsLogging -Computers "edge01.contoso.net" -StartTime "11/20/2012 1:00:00 PM" -EndTime "11/20/2012 2:45:00 PM" -OutputFilePath "C:\Logfiles\logfile.txt"
  ```

### <a name="to-run-an-advanced-search-by-using-other-criteria-and-matching-options"></a><span data-ttu-id="f9cb9-159">다른 조건 및 일치 옵션을 사용하여 고급 검색을 실행하려면</span><span class="sxs-lookup"><span data-stu-id="f9cb9-159">To run an advanced search by using other criteria and matching options</span></span>

1. <span data-ttu-id="f9cb9-160">비즈니스용 Skype 서버 관리 셸 시작: **시작,** **모든** 프로그램, 비즈니스용 **Skype 2015,** 비즈니스용 Skype 서버 관리 셸을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="f9cb9-160">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="f9cb9-161">명령을 실행하여 특정 구성 요소의 추적을 수집하려면 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="f9cb9-161">To run a command to collect traces for specific components, type the following:</span></span>
    
   ```PowerShell
   Search-CsClsLogging -Components <components to search on> -OutputFilePath <fully qualified path to output logs>
   ```

<span data-ttu-id="f9cb9-162">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f9cb9-162">For example:</span></span>
    
  ```PowerShell
  Search-CsClsLogging -Components "SIPStack","S4","UserServices" -OutputFilePath "C:\Logfiles\logfile.txt"
  ```

<span data-ttu-id="f9cb9-163">이 경우 실행되는 검색은 배포의 모든 컴퓨터 및 풀에서 지난 30분 동안의 SIPStack, S4 및 UserServices에 대한 추적 구성 요소를 포함하는 모든 로그 항목을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="f9cb9-163">The resulting search returns all log entries that have trace components for SIPStack, S4, and UserServices on all computers and pools in your deployment for the past 30 minutes.</span></span>
    
3. <span data-ttu-id="f9cb9-164">동일한 구성 요소로 검색을 이름 있는 프런트 엔드 풀로만 제한하고 pool01.contoso.net 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="f9cb9-164">To limit the search with the same components to just your Front End pool named pool01.contoso.net, type:</span></span>
    
   ```PowerShell
   Search-CsClsLogging -Components "SIPStack","S4","UserServices" -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

4. <span data-ttu-id="f9cb9-165">매개 변수가 여러 개인 경우 명령에 사용되는 기본 검색 논리는 정의된 각 매개 변수에 대해 논리 OR을 사용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="f9cb9-165">The default search logic for commands with multiple parameters is to use the logical OR with each of the defined parameters.</span></span> <span data-ttu-id="f9cb9-166">**-MatchAll** 매개 변수를 지정하여 이 동작을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9cb9-166">You can change this behavior by specifying the **-MatchAll** parameter.</span></span> <span data-ttu-id="f9cb9-167">이렇게 하려면 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="f9cb9-167">To do this, type the following:</span></span>
    
   ```PowerShell
   Search-CsClsLogging -CallId "d0af828e49fa4dcb99f5f80223a634bc" -Components "SIPStack","S4","UserServices" -MatchAll -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

5. <span data-ttu-id="f9cb9-p114">AlwaysOn과 같이 시나리오가 지속적으로 실행되도록 설정되어 있거나 장기 실행 시나리오를 정의한 경우에는 로그가 로컬 컴퓨터에서 파일 공유로 이동될 수 있습니다. 이 경우 New-CsClsConfiguration을 사용하여 새 구성을 만들거나 Set-CsClsConfiguration을 사용하여 기존 구성을 수정하는 방법으로 CacheFileNetworkFolder 매개 변수를 사용해 파일 공유를 정의합니다. 검색에서 검색할 로그 모음에 파일 공유를 포함하지 않으려면 다음과 같이 SkipNetworkLogs 매개 변수를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f9cb9-p114">If your scenarios are set to run constantly, such as AlwaysOn, or you have defined a long-running scenario logs may roll off of the local machine onto the file share. You define the file share by using the CacheFileNetworkFolder parameter by using New-CsClsConfiguration to create a new configuration or modifying an existing configuration with Set-CsClsConfiguration. If you do not want the search to include the file share in the collection of logs to search, use the SkipNetworkLogs parameter as follows:</span></span>
    
   ```PowerShell
   Search-CsClsLogging -Components "SIPStack","S4","UserServices" -StartTime "11/1/2012 00:00:01 AM" -EndTime "11/20/2012 2:45:00 PM" -SkipNetworkLogs -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

## <a name="read-capture-logs-from-the-centralized-logging-service"></a><span data-ttu-id="f9cb9-171">중앙 로깅 서비스에서 캡처 로그 읽기</span><span class="sxs-lookup"><span data-stu-id="f9cb9-171">Read capture logs from the Centralized Logging Service</span></span>

<span data-ttu-id="f9cb9-172">검색을 실행하고 보고된 문제를 추적하는 데 사용할 수 있는 파일이 있는 경우 중앙 로깅 서비스의 실제 이점을 실현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9cb9-172">You realize the real benefit of the Centralized Logging Service after you run the search and you have a file that you can use to track down a reported problem.</span></span> <span data-ttu-id="f9cb9-173">파일을 읽을 수 있는 방법은 여러 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9cb9-173">There are a number of ways that you can read the file.</span></span> <span data-ttu-id="f9cb9-174">출력 파일이 표준 텍스트 형식이면 Notepad.exe 또는 텍스트 파일을 열고 읽을 수 있는 기타 프로그램을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9cb9-174">The output file is in a standard text format and you can use Notepad.exe or any other programs that will allow you to open and read a text file.</span></span> <span data-ttu-id="f9cb9-175">파일 크기가 크고 복잡한 문제의 경우 중앙 로깅 서비스에서 로깅 출력을 읽고 구문 분석하도록 설계된 Snooper.exe 도구와 같은 도구를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9cb9-175">For larger files and more complex issues, you could use a tool like Snooper.exe that is designed to read and parse the logging output from the Centralized Logging Service.</span></span> <span data-ttu-id="f9cb9-176">Snooper는 별도의 다운로드로 사용할 수 있는 디버그 도구에 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9cb9-176">Snooper is included with the Debug Tools that are available as a separate download.</span></span> <span data-ttu-id="f9cb9-177">다음에서 디버그 도구를 다운로드할 수 [https://go.microsoft.com/fwlink/?LinkId=285257](https://go.microsoft.com/fwlink/?LinkId=285257) 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9cb9-177">You can download the Debug Tools here: [https://go.microsoft.com/fwlink/?LinkId=285257](https://go.microsoft.com/fwlink/?LinkId=285257).</span></span> <span data-ttu-id="f9cb9-178">디버그 도구를 설치하면 짧은 잘라 내기 및 메뉴 항목이 만들어지지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f9cb9-178">When you install the Debug Tools, short cuts and menu items are not created.</span></span> <span data-ttu-id="f9cb9-179">디버그 도구를 설치한 후 Windows 탐색기, 명령줄 창 또는 비즈니스용 Skype 서버 관리 셸을 열고 디렉터리(기본 위치) C:\Program Files\Skype for Business Server 2015\디버깅 도구로 이동하십시오.</span><span class="sxs-lookup"><span data-stu-id="f9cb9-179">After you install the Debug Tools, open Windows Explorer, a command-line window, or Skype for Business Server Management Shell and go to the directory (default location) C:\Program Files\Skype for Business Server 2015\Debugging Tools.</span></span> <span data-ttu-id="f9cb9-180">명령줄이나 Snooper.exe 셸을 사용하려면 Snooper.exe 입력한 다음 Enter를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f9cb9-180">Double-click Snooper.exe or type Snooper.exe, and then press ENTER if you are using the command line or Skype for Business Server Management Shell.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="f9cb9-181">이 문서에서는 문제 해결 기술에 대해 자세히 설명하거나 논의하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f9cb9-181">The intent of this topic is not to detail and discuss troubleshooting techniques.</span></span> <span data-ttu-id="f9cb9-182">문제 해결 및 관련 프로세스는 복잡한 주제입니다.</span><span class="sxs-lookup"><span data-stu-id="f9cb9-182">Troubleshooting and the processes around it is a complex subject.</span></span> <span data-ttu-id="f9cb9-183">기본 사항 문제 해결 및 특정 작업 문제 해결에 대한 자세한 내용은 Microsoft Lync Server 2010 Resource Kit book(Microsoft Lync Server 2010 Resource Kit)을 [https://go.microsoft.com/fwlink/p/?linkId=211003](https://go.microsoft.com/fwlink/p/?linkId=211003) 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="f9cb9-183">For details about troubleshooting basics and troubleshooting specific workloads, see the Microsoft Lync Server 2010 Resource Kit book at [https://go.microsoft.com/fwlink/p/?linkId=211003](https://go.microsoft.com/fwlink/p/?linkId=211003).</span></span> <span data-ttu-id="f9cb9-184">프로세스 및 절차는 비즈니스용 Skype 서버 2015에도 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f9cb9-184">The processes and procedures still apply to Skype for Business Server 2015.</span></span> 
  
### <a name="to-open-a-log-file-in-snooper"></a><span data-ttu-id="f9cb9-185">Snooper에서 로그 파일을 열려면</span><span class="sxs-lookup"><span data-stu-id="f9cb9-185">To open a log file in Snooper</span></span>

1. <span data-ttu-id="f9cb9-p117">Snooper를 사용하여 로그 파일을 열려면 로그 파일에 대한 읽기 액세스 권한이 있어야 합니다. Snooper를 사용하여 로그 파일에 액세스하려면 CsAdministrator 또는 CsServerAdministrator RBAC(역할 기반 액세스 제어) 보안 그룹의 구성원이거나 이들 두 그룹 중 하나를 포함하는 사용자 지정 RBAC 역할의 구성원이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9cb9-p117">To use Snooper and open log files, you need read access to the log files. To use Snooper and access the log files you must be a member of the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> 
    
2. <span data-ttu-id="f9cb9-188">디버깅 도구(LyncDebugTools.msi)를 설치한 후 디렉터리를 Windows 탐색기 또는 명령줄에서 Snooper.exe 위치로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="f9cb9-188">After the installation of the Debugging Tools (LyncDebugTools.msi), change directory to the location of Snooper.exe using Windows Explorer or from the command line.</span></span> <span data-ttu-id="f9cb9-189">기본적으로 디버깅 도구는 C:\Program Files\Skype for Business Server 2015\Debugging Tools에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9cb9-189">By default, the debugging tools are located in C:\Program Files\Skype for Business Server 2015\Debugging Tools.</span></span> <span data-ttu-id="f9cb9-190">Snooper.exe를 두 번 클릭하거나 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="f9cb9-190">Double-click or run Snooper.exe.</span></span>
    
3. <span data-ttu-id="f9cb9-191">Snooper가 열리면 **File(파일)** 을 클릭하고 **OpenFile** 을 클릭한 다음 **Open(열기)** 대화 상자에서 로그 파일을 찾아 선택한 후 **Open(열기)** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f9cb9-191">After Snooper is open, right-click **File**, click **OpenFile**, find your log files, select a file in the **Open** dialog box, and then click **Open**.</span></span>
    
4. <span data-ttu-id="f9cb9-192">로그 파일의 **추적** 메시지가 추적 **탭에** 표시됩니다. 메시지 **탭을 클릭하여** 수집된 추적의 메시지 내용을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9cb9-192">The log file's **Trace** messages are displayed on the **Trace** tab. Click the **Messages** tab to view the message contents of the collected traces.</span></span>
    
### <a name="to-display-a-call-flow-diagram"></a><span data-ttu-id="f9cb9-193">통화 흐름 다이어그램을 표시하려면</span><span class="sxs-lookup"><span data-stu-id="f9cb9-193">To display a call flow diagram</span></span>

1. <span data-ttu-id="f9cb9-p119">Snooper를 사용하여 로그 파일을 열려면 로그 파일에 대한 읽기 액세스 권한이 있어야 합니다. Snooper를 사용하여 로그 파일에 액세스하려면 CsAdministrator 또는 CsServerAdministrator RBAC(역할 기반 액세스 제어) 보안 그룹의 구성원이거나 이들 두 그룹 중 하나를 포함하는 사용자 지정 RBAC 역할의 구성원이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9cb9-p119">To use Snooper and open log files, you need read access to the log files. To use Snooper and access the log files, you need to be a member of the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span>
    
2. <span data-ttu-id="f9cb9-196">로그 파일을 열고 **Messages(메시지)** 탭을 클릭한 다음 메시지 보기에서 대화를 선택하거나, **Trace(추적)** 탭에서 추적 구성 요소를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f9cb9-196">Open a log file and click the **Messages** tab, select a conversation in the messages view or select a trace component on the **Trace** tab.</span></span>
    
3. <span data-ttu-id="f9cb9-197">**Call Flow(통화 흐름)** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f9cb9-197">Click **Call Flow**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="f9cb9-198">통화 흐름에 속하지 않는 메시지나 추적을 클릭하면 다이어그램이 나타나지 않습니다. 그러면 Snooper 아래쪽에 "이 메시지는 콜오프할 수 없습니다."라는 상태 메시지가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="f9cb9-198">If you click on a message or trace that is not part of a call flow, the diagram will not appear and a status message appears at the bottom of Snooper stating "This message is not eligible for callfow".</span></span> <span data-ttu-id="f9cb9-199">통화 흐름의 일부인 다른 메시지나 추적을 선택하면 통화 흐름이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="f9cb9-199">Choose another message or trace and the call flow will appear if the message or trace is part of a call flow.</span></span> 
  
4. <span data-ttu-id="f9cb9-200">메시지 또는 추적 줄 간을 이동하여 통화 흐름 다이어그램이 새로운 다이어그램을 표시하도록 업데이트 또는 변경되는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="f9cb9-200">Move through the Messages or the Trace lines and note whether the call flow diagram updates or changes to display a new diagram.</span></span>
    
5. <span data-ttu-id="f9cb9-201">통화 메시지, 끝점, 기타 구성 요소에 대한 정보를 확인하려면 요소 위에 마우스 커서를 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="f9cb9-201">Hover over elements to get information about call messages, endpoints, and other components.</span></span>
