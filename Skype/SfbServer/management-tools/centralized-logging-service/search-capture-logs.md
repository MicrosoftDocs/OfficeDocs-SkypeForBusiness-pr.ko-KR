---
title: 비즈니스용 Skype 2015의 중앙 로깅 서비스에서 만든 캡처 로그 검색
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 1b75b218-d84f-47a7-8a0a-b7e016b1cc79
description: '요약: 비즈니스용 Skype 서버 2015에서 중앙 집중화 된 로깅 서비스 캡처 로그를 검색 하 고 읽는 방법에 대해 알아봅니다.'
ms.openlocfilehash: 563f2c5e08da0830c3bd03e562d0d94052fa359b
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991453"
---
# <a name="search-capture-logs-created-by-the-centralized-logging-service-in-skype-for-business-server-2015"></a><span data-ttu-id="4e8e5-103">비즈니스용 Skype 2015의 중앙 로깅 서비스에서 만든 캡처 로그 검색</span><span class="sxs-lookup"><span data-stu-id="4e8e5-103">Search capture logs created by the Centralized Logging Service in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="4e8e5-104">**요약:** 비즈니스용 Skype 서버 2015에서 중앙 로깅 서비스 캡처 로그를 검색 하 고 읽는 방법에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="4e8e5-104">**Summary:** Learn how to search and read Centralized Logging Service capture logs in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="4e8e5-105">중앙 로깅 서비스의 검색 기능은 다음과 같은 이유로 유용 하 고 강력 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e8e5-105">The search features in the Centralized Logging Service are useful and powerful for the following reasons:</span></span> 
  
- <span data-ttu-id="4e8e5-106">검색 및 결과는 정의한 기준에 따라 단일 컴퓨터, 풀, 사이트 또는 전역 범위에서 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e8e5-106">Your searches and the results are run on a single computer, a pool, a site, or a global scope, based on the criteria you define.</span></span>
    
- <span data-ttu-id="4e8e5-107">검색은 초기에 광범위 하 게 사용할 수 있으며 시간, 구성 요소 또는 컴퓨터와 같은 더 많은 대상 기준으로 축소 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e8e5-107">Your searches can be initially broad and then narrowed down to more targeted criteria such as time, component, or computer.</span></span> <span data-ttu-id="4e8e5-108">동일한 로그를 검색 하는 경우 검색 조건이 변경 되 면 로깅 세션을 다시 실행할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4e8e5-108">You search against the same logs and don't need to run a logging session again when the search criteria changes.</span></span>
    
- <span data-ttu-id="4e8e5-109">검색 결과는 범위 내 모든 컴퓨터와 풀에서 수집 되며 검색 조건의 모든 결과를 나타내는 단일 출력 파일로 수집 되 고 집계 됩니다 (실행 중인 시나리오와 시스템에서 캡처한 데이터에 따라 제한 됨). 시나리오).</span><span class="sxs-lookup"><span data-stu-id="4e8e5-109">The results of your search are gathered from all computers and pools in the scope, collected and aggregated into a single output file that represents all results of the search criteria (limited to the scenarios that have been running and the data captured by the scenarios).</span></span> <span data-ttu-id="4e8e5-110">**Snooper** 또는 **메모장** 등의 익숙한 도구를 사용 하 여 배포에서 출력 파일 및 추적 메시지를 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e8e5-110">You use familiar tools such as **Snooper** or **Notepad** to read the output file and the trace messages from across your deployment.</span></span>
    
<span data-ttu-id="4e8e5-111">각 개별 컴퓨터의 CLSAgent는 시나리오 또는 시나리오를 기반으로 로그를 만듭니다 (컴퓨터당 두 가지 시나리오는 주어진 시간에 실행 될 수 있음).</span><span class="sxs-lookup"><span data-stu-id="4e8e5-111">The CLSAgent on each individual computer creates the logs based on the scenario or scenarios (two scenarios per computer can be running at any given time).</span></span> <span data-ttu-id="4e8e5-112">로그 및 관련 인덱스 및 캐시 파일은 CLSAgent에서 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e8e5-112">The logs and their associated index and cache files are managed by the CLSAgent.</span></span> <span data-ttu-id="4e8e5-113">검색을 정의 하 고 실행할 때 검색 명령은 검색할 정보에 대해 CLSAgent에 지시 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e8e5-113">When you define and execute a search, the search command instructs the CLSAgent on what information should be retrieved.</span></span> <span data-ttu-id="4e8e5-114">CLSAgent는 로그 파일, 캐시 파일, 인덱스 파일에 대해 쿼리를 실행 하 고 검색 결과를 CLSContoller에 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e8e5-114">The CLSAgent executes the query against the log files, cache files, and index files and returns the results of the search to the CLSContoller.</span></span> <span data-ttu-id="4e8e5-115">CLSController는 검색 범위에 있는 모든 컴퓨터 및 풀에서 검색 결과를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="4e8e5-115">The CLSController receives the search results from all computers and pools in the scope of the search.</span></span> <span data-ttu-id="4e8e5-116">그런 다음 CLSController는 로그를 집계 (결합) 하 고, 오래 된 항목에 먼저 입력 하 고, 최근 항목에 마지막으로 시간을 붙여 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="4e8e5-116">The CLSController then aggregates (combines) the logs and puts them into time delta order, oldest entry first, and proceeding in time to the most recent entry last.</span></span>
  
<span data-ttu-id="4e8e5-117">각 검색 후에 **동기화-CsClsLogging** cmdlet이 실행 되 고, 검색에 사용 되는 캐시를 플러시합니다 (clsagent에서 유지 관리 하는 캐시 파일과 혼동 하지 않음).</span><span class="sxs-lookup"><span data-stu-id="4e8e5-117">After each search, the **Sync-CsClsLogging** cmdlet is run and it flushes the cache used by searches (not to be confused with the cache files maintained by the CLSAgent).</span></span> <span data-ttu-id="4e8e5-118">캐시를 플러시하 면 다음 검색 작업을 위해 CLSController에 정리 된 로그 및 추적 파일 캡처 버퍼가 있는지 확인 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e8e5-118">Flushing the cache helps to ensure that there is a clean log and trace file capture buffer at the CLSController for the next search operation.</span></span>
  
<span data-ttu-id="4e8e5-119">중앙 로깅 서비스의 이점을 최대한 활용 하려면 검색을 구성 하 여 리서치 하려는 문제와 관련 된 컴퓨터 및 풀 로그의 추적 메시지만 반환 하는 방법에 대해 잘 알고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e8e5-119">To get the most benefit from the Centralized Logging Service, you need a good understanding of how to configure search to return only trace messages from the computer and pool logs that are relevant to the issue that you are researching.</span></span> <span data-ttu-id="4e8e5-120">사항</span><span class="sxs-lookup"><span data-stu-id="4e8e5-120">issues</span></span>
  
<span data-ttu-id="4e8e5-121">비즈니스용 Skype Server Management Shell을 사용 하 여 중앙 집중식 로깅 서비스 검색 기능을 실행 하려면 CsAdministrator 또는 CsServerAdministrator 역할 기반 액세스 제어 (RBAC) 보안 그룹 또는 사용자 지정 RBAC 역할 중 하나의 구성원 이어야 합니다. 이러한 두 그룹 중 하나가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e8e5-121">To run the Centralized Logging Service search functions by using the Skype for Business Server Management Shell, you must be a member of either the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> <span data-ttu-id="4e8e5-122">이 cmdlet이 할당 된 모든 RBAC 역할 목록 (직접 만든 사용자 지정 RBAC 역할 포함)을 반환 하려면 비즈니스용 Skype Server 관리 셸 또는 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e8e5-122">To return a list of all the RBAC roles that this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Skype for Business Server Management Shell or the Windows PowerShell prompt:</span></span>
  
```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Skype for Business Server 2015 cmdlet"}
```

<span data-ttu-id="4e8e5-123">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4e8e5-123">For example:</span></span>
  
```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

<span data-ttu-id="4e8e5-124">이 항목의 나머지 부분에서는 문제 해결을 최적화 하기 위해 검색을 정의 하는 방법에 대해 중점적으로 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e8e5-124">The remainder of this topic focuses on how to define a search to optimize your troubleshooting.</span></span>
  
### <a name="to-run-a-basic-search-by-using-the-centralized-logging-service"></a><span data-ttu-id="4e8e5-125">중앙 로깅 서비스를 사용 하 여 기본 검색을 실행 하려면</span><span class="sxs-lookup"><span data-stu-id="4e8e5-125">To run a basic search by using the Centralized Logging Service</span></span>

1. <span data-ttu-id="4e8e5-126">비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **비즈니스용 skype 2015**을 차례로 클릭 한 다음 비즈니스용 **skype Server management Shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e8e5-126">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="4e8e5-127">전역 범위에서 배포에 AlwaysOn 시나리오가 실행 되 고 있는지 확인 한 다음 명령 프롬프트에서 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e8e5-127">Make sure that you have the AlwaysOn scenario running in your deployment at the global scope and then type the following at a command prompt:</span></span>
    
   ```PowerShell
   Search-CsClsLogging -OutputFilePath <string value of path and file to write the output file>
   ```

> [!NOTE]
> <span data-ttu-id="4e8e5-128">기본적으로 검색-CsClsLogging은 검색 결과를 콘솔에 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="4e8e5-128">By default, Search-CsClsLogging sends the results of the search to the console.</span></span> <span data-ttu-id="4e8e5-129">검색 결과를 파일에 저장 하려는 경우-outputfilepath _ \<문자열 정식 파일 경로\>_ 를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e8e5-129">If you want to save the search results to a file, use -OutputFilePath  _\<string fully qualified file path\>_.</span></span> <span data-ttu-id="4e8e5-130">-OutputFilePath 매개 변수를 정의 하려면 따옴표로 묶인 문자열 형식으로 경로와 파일 이름을 매개 변수의 일부로 제공 합니다 (예: C:\LogFiles\SearchOutput.txt).</span><span class="sxs-lookup"><span data-stu-id="4e8e5-130">To define the -OutputFilePath parameter, supply a path and a filename as part of the parameter in a string format enclosed in quotation marks (for example; C:\LogFiles\SearchOutput.txt).</span></span> <span data-ttu-id="4e8e5-131">이 예제에서는 디렉터리 c 로그 파일이 존재 하 고 폴더에 대 한 읽기 및 쓰기 권한 (NTFS 사용 권한 수정)이 있는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e8e5-131">In this example, you must ensure that the directory C:\LogFiles exists and that you have permissions to Read and Write (NTFS permission Modify) files in the folder.</span></span> <span data-ttu-id="4e8e5-132">출력이 추가 되 고 덮어쓰여지지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4e8e5-132">The output is appended to and is not overwritten.</span></span> <span data-ttu-id="4e8e5-133">별도의 파일이 필요한 경우 각 검색에 대해 고유한 파일 이름을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e8e5-133">If you need separate files, define a distinct file name for each search.</span></span> 
  
<span data-ttu-id="4e8e5-134">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4e8e5-134">For example:</span></span>
    
  ```PowerShell
  Search-CsClsLogging -OutputFilePath "C:\LogFiles\logfile.txt"
  ```

### <a name="to-run-a-basic-search-on-a-pool-or-computer-by-using-the-centralized-logging-service"></a><span data-ttu-id="4e8e5-135">중앙 로깅 서비스를 사용 하 여 풀이나 컴퓨터에서 기본 검색을 실행 하려면</span><span class="sxs-lookup"><span data-stu-id="4e8e5-135">To run a basic search on a pool or computer by using the Centralized Logging Service</span></span>

1. <span data-ttu-id="4e8e5-136">특정 풀이나 컴퓨터로 검색을 제한 하려면-Computers 매개 변수를 컴퓨터의 정규화 된 이름으로 정의한 컴퓨터와 함께 사용 하 고, 다음과 같이 따옴표로 묶이고 쉼표로 구분 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e8e5-136">To limit the search to a specific pool or computer, use the -Computers parameter with the computer defined by a computer fully qualified name, enclosed in quotation marks and separated by a comma as follows:</span></span>
    
   ```PowerShell
   Search-CsClsLogging -Computers <string value of computer names> -OutputFilePath <string value of path and file to write the output file>
   ```

<span data-ttu-id="4e8e5-137">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4e8e5-137">For example:</span></span>
    
  ```PowerShell
  Search-CsClsLogging -Computers "fe01.contoso.net" -OutputFilePath "C:\LogFiles\logfile.txt"
  ```

2. <span data-ttu-id="4e8e5-138">두 대 이상의 컴퓨터를 검색 하려면 다음과 같이 따옴표로 묶여 여러 컴퓨터 이름을 입력 하 고 쉼표로 구분 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e8e5-138">To search more than one computer, type multiple computer names enclosed in quotation marks and separated by commas, such as the following:</span></span>
    
   ```PowerShell
   Search-CsClsLogging -Computers "fe01.contoso.net", "fe02.contoso.net", "fe03.contoso.net" -OutputFilePath "C:\LogFiles\logfile.txt"
   ```

3. <span data-ttu-id="4e8e5-139">단일 컴퓨터 대신 전체 풀을 검색 해야 하는 경우-Computers 매개 변수를-풀링합니다으로 변경 하 고 컴퓨터 이름을 제거한 다음 쉼표로 구분 된 풀 또는 풀로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="4e8e5-139">If you need to search an entire pool instead of a single computer, change the -Computers parameter to -Pools, remove the computer name, and replace it with the pool or pools in quotation marks separated by commas.</span></span>
    
    <span data-ttu-id="4e8e5-140">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4e8e5-140">For example:</span></span>
    
   ```PowerShell
   Search-CsClsLogging -Pools "pool01.contoso.net" -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

4. <span data-ttu-id="4e8e5-141">검색 명령을 사용 하는 경우에는 배포의 풀 (예: 프런트 엔드 풀, Edge 풀, 영구 채팅 서버 풀 등)과 배포에서 풀로 정의 된 사용자 중 풀이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e8e5-141">When using the search commands, pools can be any pool in your deployment, such as Front End pools, Edge pools, Persistent Chat Server pools, or others that are defined as a pool in your deployment.</span></span>
    
    <span data-ttu-id="4e8e5-142">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4e8e5-142">For example:</span></span>
    
   ```PowerShell
   Search-CsClsLogging -Pools "pool01.contoso.net", "pchatpool01.contoso.net", "intedgepool01.contoso.net" -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

### <a name="to-run-a-search-by-using-time-parameters"></a><span data-ttu-id="4e8e5-143">시간 매개 변수를 사용 하 여 검색을 실행 하려면</span><span class="sxs-lookup"><span data-stu-id="4e8e5-143">To run a search by using time parameters</span></span>

1. <span data-ttu-id="4e8e5-144">비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **비즈니스용 skype 2015**을 차례로 클릭 한 다음 비즈니스용 **skype Server management Shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e8e5-144">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="4e8e5-145">기본적으로 검색의 시간 관련 매개 변수에 대 한 시작 시간은 검색 시작 후 5 분 전의 25 분입니다.</span><span class="sxs-lookup"><span data-stu-id="4e8e5-145">By default, the beginning time for a search's time-specific parameters is 25 minutes prior to five minutes after the time you initiate the search.</span></span> <span data-ttu-id="4e8e5-146">즉, 4:00:00 PM에서 검색 하는 경우 검색 시작 시간은 3:35:00 PM으로 4:05:00 PM으로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e8e5-146">In other words, if we search at 4:00:00 PM, then the search start time will show as 3:35:00 PM to 4:05:00 PM.</span></span> <span data-ttu-id="4e8e5-147">현재 시간 전에 60 분 또는 3 시간 전에 검색 해야 하는 경우-StartTime 매개 변수를 사용 하 고 날짜 및 시간 문자열을 설정 하 여 검색을 시작할 시간을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e8e5-147">If you need to search 60 minutes or 3 hours prior to the current time, use the -StartTime parameter and set the date and time string to indicate the time you want the search to start.</span></span> 
    
    <span data-ttu-id="4e8e5-148">예를 들어-StartTime 및-EndTime을 사용 하 여 시간 및 날짜 범위를 정의 하면 풀의 11/20/2012에 오전 8 시와 9 시 사이의 검색을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e8e5-148">For example, by using -StartTime and -EndTime to define a time and date range, you can define a search between 8 AM and 9 AM on 11/20/2012 on your pool.</span></span> <span data-ttu-id="4e8e5-149">다음과 같이 c:\logfile.txt 이라는 파일에 결과를 기록 하도록 출력 경로를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e8e5-149">You can set the output path to write the results to a file named c:\logfile.txt as follows:</span></span>
    
   ```PowerShell
   Search-CsClsLogging -Pools "pool01.contoso.net" -StartTime "11/20/2012 08:00:00 AM" -EndTime "11/20/2012 09:00:00 AM" -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

> [!NOTE]
> <span data-ttu-id="4e8e5-150">지정 하는 시간 및 날짜 문자열은 "날짜 시간" 또는 "시간 날짜" 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e8e5-150">The time and date string that you specify can be "date time" or "time date.</span></span> <span data-ttu-id="4e8e5-151">"명령은 문자열을 구문 분석 하 고, cmdlet을 실행 하는 컴퓨터의 로캘 및 culture 설정 및 날짜 및 시간에 적절 한 값을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e8e5-151">" The command will parse the string and use the appropriate values for date and time and your locale and culture settings on the machine you are running cmdlet from.</span></span> 
  
3. <span data-ttu-id="4e8e5-152">11:00:00 오전 11/20/2012에 시작 되는 로그를 검색 하려면-StartTime을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e8e5-152">If you want to retrieve logs beginning at 11:00:00 AM on 11/20/2012, you define the -StartTime.</span></span> <span data-ttu-id="4e8e5-153">특정 EndTime을 정의 하지 않는 한 검색의 기본 시간 범위는 30 분입니다.</span><span class="sxs-lookup"><span data-stu-id="4e8e5-153">The default time range for the search is 30 minutes unless you define a specific -EndTime.</span></span> <span data-ttu-id="4e8e5-154">결과 검색은 정의 된 컴퓨터 또는 풀의 로그를 오전 11:00:00에서 11:30:00 AM으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e8e5-154">The resulting search will return logs from the defined computer or pools from 11:00:00 AM to 11:30:00 AM.</span></span>
    
<span data-ttu-id="4e8e5-155">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4e8e5-155">For example:</span></span>
    
  ```PowerShell
  Search-CsClsLogging -Pools "pool01.contoso.net" -StartTime "11/20/2012 11:00:00 AM" -OutputFilePath "C:\Logfiles\logfile.txt"
  ```

4. <span data-ttu-id="4e8e5-156">특정 기간 내에 로그 검색을 수행 하려면-StartTime 및-EndTime을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e8e5-156">To conduct a search of logs within a specific period of time, define a -StartTime and an -EndTime.</span></span> <span data-ttu-id="4e8e5-157">컴퓨터 edge01.contoso.net 1 PM부터 2:45 PM 까지의 로그가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e8e5-157">You need logs from 1 PM to 2:45 PM on the computer edge01.contoso.net.</span></span> 
    
<span data-ttu-id="4e8e5-158">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4e8e5-158">For example:</span></span>
    
  ```
  Search-CsClsLogging -Computers "edge01.contoso.net" -StartTime "11/20/2012 1:00:00 PM" -EndTime "11/20/2012 2:45:00 PM" -OutputFilePath "C:\Logfiles\logfile.txt"
  ```

### <a name="to-run-an-advanced-search-by-using-other-criteria-and-matching-options"></a><span data-ttu-id="4e8e5-159">다른 조건과 일치 옵션을 사용 하 여 고급 검색을 실행 하려면</span><span class="sxs-lookup"><span data-stu-id="4e8e5-159">To run an advanced search by using other criteria and matching options</span></span>

1. <span data-ttu-id="4e8e5-160">비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **비즈니스용 skype 2015**을 차례로 클릭 한 다음 비즈니스용 **skype Server management Shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e8e5-160">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="4e8e5-161">특정 구성 요소에 대 한 추적을 수집 하는 명령을 실행 하려면 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e8e5-161">To run a command to collect traces for specific components, type the following:</span></span>
    
   ```PowerShell
   Search-CsClsLogging -Components <components to search on> -OutputFilePath <fully qualified path to output logs>
   ```

<span data-ttu-id="4e8e5-162">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4e8e5-162">For example:</span></span>
    
  ```PowerShell
  Search-CsClsLogging -Components "SIPStack","S4","UserServices" -OutputFilePath "C:\Logfiles\logfile.txt"
  ```

<span data-ttu-id="4e8e5-163">결과 검색은 지난 30 분 동안 배포의 모든 컴퓨터와 풀에 대 한 SIPStack, S4 및 UserServices에 대 한 추적 구성 요소가 있는 모든 로그 항목을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e8e5-163">The resulting search returns all log entries that have trace components for SIPStack, S4, and UserServices on all computers and pools in your deployment for the past 30 minutes.</span></span>
    
3. <span data-ttu-id="4e8e5-164">Pool01.contoso.net 라는 프런트 엔드 풀에 대해서도 동일한 구성 요소로 검색을 제한 하려면 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e8e5-164">To limit the search with the same components to just your Front End pool named pool01.contoso.net, type:</span></span>
    
   ```PowerShell
   Search-CsClsLogging -Components "SIPStack","S4","UserServices" -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

4. <span data-ttu-id="4e8e5-165">여러 매개 변수가 있는 명령에 대 한 기본 검색 논리는 정의 된 각 매개 변수와 논리 OR를 사용 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="4e8e5-165">The default search logic for commands with multiple parameters is to use the logical OR with each of the defined parameters.</span></span> <span data-ttu-id="4e8e5-166">**-Matchall** 매개 변수를 지정 하 여이 동작을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e8e5-166">You can change this behavior by specifying the **-MatchAll** parameter.</span></span> <span data-ttu-id="4e8e5-167">이렇게 하려면 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e8e5-167">To do this, type the following:</span></span>
    
   ```PowerShell
   Search-CsClsLogging -CallId "d0af828e49fa4dcb99f5f80223a634bc" -Components "SIPStack","S4","UserServices" -MatchAll -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

5. <span data-ttu-id="4e8e5-168">시나리오가 AlwaysOn과 같이 지속적으로 실행 되도록 설정 되어 있거나 장기 실행 시나리오 로그가 사용자가 로컬 컴퓨터를 파일 공유로 롤백할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e8e5-168">If your scenarios are set to run constantly, such as AlwaysOn, or you have defined a long-running scenario logs may roll off of the local machine onto the file share.</span></span> <span data-ttu-id="4e8e5-169">새 구성을 만들거나 Set-CsClsConfiguration을 사용 하 여 기존 구성을 수정 하기 위해 새로운 CsClsConfiguration을 사용 하 여 CacheFileNetworkFolder 매개 변수를 사용 하 여 파일 공유를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e8e5-169">You define the file share by using the CacheFileNetworkFolder parameter by using New-CsClsConfiguration to create a new configuration or modifying an existing configuration with Set-CsClsConfiguration.</span></span> <span data-ttu-id="4e8e5-170">검색할 로그 모음에 파일 공유를 포함 하지 않으려면 다음과 같이 SkipNetworkLogs 매개 변수를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e8e5-170">If you do not want the search to include the file share in the collection of logs to search, use the SkipNetworkLogs parameter as follows:</span></span>
    
   ```PowerShell
   Search-CsClsLogging -Components "SIPStack","S4","UserServices" -StartTime "11/1/2012 00:00:01 AM" -EndTime "11/20/2012 2:45:00 PM" -SkipNetworkLogs -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

## <a name="read-capture-logs-from-the-centralized-logging-service"></a><span data-ttu-id="4e8e5-171">중앙 로깅 서비스에서 캡처 로그 읽기</span><span class="sxs-lookup"><span data-stu-id="4e8e5-171">Read capture logs from the Centralized Logging Service</span></span>

<span data-ttu-id="4e8e5-172">검색을 실행 한 후 보고 된 문제를 추적 하는 데 사용할 수 있는 파일을가지고 있는 경우 중앙 로깅 서비스의 실질적인 이점을 얻게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e8e5-172">You realize the real benefit of the Centralized Logging Service after you run the search and you have a file that you can use to track down a reported problem.</span></span> <span data-ttu-id="4e8e5-173">파일을 읽을 수 있는 방법에는 여러 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e8e5-173">There are a number of ways that you can read the file.</span></span> <span data-ttu-id="4e8e5-174">출력 파일은 표준 텍스트 형식으로 되어 있으며, Notepad.exe 또는 텍스트 파일을 열고 읽는 데 사용할 수 있는 다른 프로그램을 사용 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e8e5-174">The output file is in a standard text format and you can use Notepad.exe or any other programs that will allow you to open and read a text file.</span></span> <span data-ttu-id="4e8e5-175">대용량 파일과 복잡 한 문제가 발생 하는 경우 중앙 로깅 서비스에서 로깅 출력을 읽고 구문 분석 하도록 디자인 된 Snooper 같은 도구를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e8e5-175">For larger files and more complex issues, you could use a tool like Snooper.exe that is designed to read and parse the logging output from the Centralized Logging Service.</span></span> <span data-ttu-id="4e8e5-176">Snooper는 별도의 다운로드로 제공 되는 디버그 도구에 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e8e5-176">Snooper is included with the Debug Tools that are available as a separate download.</span></span> <span data-ttu-id="4e8e5-177">디버그 도구는 다음과 같이 [https://go.microsoft.com/fwlink/?LinkId=285257](https://go.microsoft.com/fwlink/?LinkId=285257)다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e8e5-177">You can download the Debug Tools here: [https://go.microsoft.com/fwlink/?LinkId=285257](https://go.microsoft.com/fwlink/?LinkId=285257).</span></span> <span data-ttu-id="4e8e5-178">디버그 도구를 설치 하면 짧은 컷 및 메뉴 항목이 만들어지지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4e8e5-178">When you install the Debug Tools, short cuts and menu items are not created.</span></span> <span data-ttu-id="4e8e5-179">디버그 도구를 설치한 후 Windows 탐색기, 명령줄 창 또는 비즈니스용 Skype Server Management Shell을 열고 Business Server 2015 용 C:\Program Files\Skype 디렉터리 (기본 위치)로 이동 하 여 디버깅 도구를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4e8e5-179">After you install the Debug Tools, open Windows Explorer, a command-line window, or Skype for Business Server Management Shell and go to the directory (default location) C:\Program Files\Skype for Business Server 2015\Debugging Tools.</span></span> <span data-ttu-id="4e8e5-180">Snooper를 두 번 클릭 하거나 Snooper를 입력 한 다음 명령줄 또는 비즈니스용 Skype Server Management Shell을 사용 하는 경우 enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="4e8e5-180">Double-click Snooper.exe or type Snooper.exe, and then press ENTER if you are using the command line or Skype for Business Server Management Shell.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="4e8e5-181">이 항목의 목적은 문제 해결 기법을 자세히 설명 하 고 논의 하는 것이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="4e8e5-181">The intent of this topic is not to detail and discuss troubleshooting techniques.</span></span> <span data-ttu-id="4e8e5-182">문제 해결 및 관련 프로세스는 복잡 한 주제입니다.</span><span class="sxs-lookup"><span data-stu-id="4e8e5-182">Troubleshooting and the processes around it is a complex subject.</span></span> <span data-ttu-id="4e8e5-183">해결 방법에 대 한 자세한 내용과 특정 작업 부하 문제 해결에 대 한 자세한 내용은의 [https://go.microsoft.com/fwlink/p/?linkId=211003](https://go.microsoft.com/fwlink/p/?linkId=211003)Microsoft Lync Server 2010 Resource Kit 책을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4e8e5-183">For details about troubleshooting basics and troubleshooting specific workloads, see the Microsoft Lync Server 2010 Resource Kit book at [https://go.microsoft.com/fwlink/p/?linkId=211003](https://go.microsoft.com/fwlink/p/?linkId=211003).</span></span> <span data-ttu-id="4e8e5-184">프로세스와 절차는 계속 해 서 비즈니스용 Skype 서버 2015에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e8e5-184">The processes and procedures still apply to Skype for Business Server 2015.</span></span> 
  
### <a name="to-open-a-log-file-in-snooper"></a><span data-ttu-id="4e8e5-185">Snooper에서 로그 파일을 열려면</span><span class="sxs-lookup"><span data-stu-id="4e8e5-185">To open a log file in Snooper</span></span>

1. <span data-ttu-id="4e8e5-186">Snooper를 사용 하 고 로그 파일을 열려면 로그 파일에 대 한 읽기 권한이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e8e5-186">To use Snooper and open log files, you need read access to the log files.</span></span> <span data-ttu-id="4e8e5-187">Snooper를 사용 하 고 로그 파일에 액세스 하려면 CsAdministrator의 구성원 이거나,이 두 그룹 중 하나를 포함 하는 CsServerAdministrator 역할 기반 액세스 컨트롤 (RBAC) 보안 그룹 또는 사용자 지정 RBAC 역할 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e8e5-187">To use Snooper and access the log files you must be a member of the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> 
    
2. <span data-ttu-id="4e8e5-188">디버깅 도구 (LSnooper Cdebugtools)를 설치한 후 Windows 탐색기 또는 명령줄을 사용 하 여 디렉터리를 위치로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e8e5-188">After the installation of the Debugging Tools (LyncDebugTools.msi), change directory to the location of Snooper.exe using Windows Explorer or from the command line.</span></span> <span data-ttu-id="4e8e5-189">기본적으로 디버깅 도구는 Business Server 2015 \ 디버깅 도구에 대 한 C:\Program Files\Skype에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e8e5-189">By default, the debugging tools are located in C:\Program Files\Skype for Business Server 2015\Debugging Tools.</span></span> <span data-ttu-id="4e8e5-190">Snooper를 두 번 클릭 하거나 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e8e5-190">Double-click or run Snooper.exe.</span></span>
    
3. <span data-ttu-id="4e8e5-191">Snooper가 열리면 **파일**을 마우스 오른쪽 단추로 클릭 하 고 **OpenFile**을 클릭 하 고 로그 파일을 찾은 다음 **열기** 대화 상자에서 파일을 선택 하 고 **열기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e8e5-191">After Snooper is open, right-click **File**, click **OpenFile**, find your log files, select a file in the **Open** dialog box, and then click **Open**.</span></span>
    
4. <span data-ttu-id="4e8e5-192">**추적** 탭에 로그 파일의 **추적** 메시지가 표시 됩니다. 수집 된 추적의 메시지 내용을 보려면 **메시지** 탭을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e8e5-192">The log file's **Trace** messages are displayed on the **Trace** tab. Click the **Messages** tab to view the message contents of the collected traces.</span></span>
    
### <a name="to-display-a-call-flow-diagram"></a><span data-ttu-id="4e8e5-193">통화 흐름 다이어그램을 표시 하려면</span><span class="sxs-lookup"><span data-stu-id="4e8e5-193">To display a call flow diagram</span></span>

1. <span data-ttu-id="4e8e5-194">Snooper를 사용 하 고 로그 파일을 열려면 로그 파일에 대 한 읽기 권한이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e8e5-194">To use Snooper and open log files, you need read access to the log files.</span></span> <span data-ttu-id="4e8e5-195">Snooper를 사용 하 고 로그 파일에 액세스 하려면 CsAdministrator의 구성원 이거나,이 두 그룹 중 하나를 포함 하는 CsServerAdministrator 역할 기반 액세스 컨트롤 (RBAC) 보안 그룹 또는 사용자 지정 RBAC 역할을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e8e5-195">To use Snooper and access the log files, you need to be a member of the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span>
    
2. <span data-ttu-id="4e8e5-196">로그 파일을 열고 **메시지** 탭을 클릭 하 고 메시지 보기에서 대화를 선택 하거나 **추적** 탭에서 추적 구성 요소를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e8e5-196">Open a log file and click the **Messages** tab, select a conversation in the messages view or select a trace component on the **Trace** tab.</span></span>
    
3. <span data-ttu-id="4e8e5-197">**통화 흐름**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e8e5-197">Click **Call Flow**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="4e8e5-198">호출 흐름의 일부가 아닌 메시지 또는 추적을 클릭 하면 다이어그램이 나타나지 않으며 "이 메시지는 callSnooper에 적합 하지 않습니다." 라는 상태 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e8e5-198">If you click on a message or trace that is not part of a call flow, the diagram will not appear and a status message appears at the bottom of Snooper stating "This message is not eligible for callfow".</span></span> <span data-ttu-id="4e8e5-199">다른 메시지 또는 추적을 선택 하면 메시지 또는 추적이 호출 흐름의 일부인 경우 호출 흐름이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e8e5-199">Choose another message or trace and the call flow will appear if the message or trace is part of a call flow.</span></span> 
  
4. <span data-ttu-id="4e8e5-200">메시지 또는 추적 선을 이동 하 고 새 다이어그램을 표시 하기 위해 호출 흐름 다이어그램이 업데이트 또는 변경 되는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e8e5-200">Move through the Messages or the Trace lines and note whether the call flow diagram updates or changes to display a new diagram.</span></span>
    
5. <span data-ttu-id="4e8e5-201">요소 위에 커서를 올리면 호출 메시지, 끝점 및 기타 구성 요소에 대 한 정보를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e8e5-201">Hover over elements to get information about call messages, endpoints, and other components.</span></span>
