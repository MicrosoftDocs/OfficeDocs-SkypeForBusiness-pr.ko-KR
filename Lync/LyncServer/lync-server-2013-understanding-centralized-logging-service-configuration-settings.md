---
title: 중앙 로깅 서비스 구성 설정 이해
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Understanding Centralized Logging Service configuration settings
ms:assetid: 3c34e600-0b91-43dc-b4cc-90b6a70ee12e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688029(v=OCS.15)
ms:contentKeyID: 49733619
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7a4f9a6a2db8cb4726abc65553fc4482d349f38f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985672"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="understanding-centralized-logging-service-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="6ea48-102">Lync Server 2013의 중앙 로깅 서비스 구성 설정 이해</span><span class="sxs-lookup"><span data-stu-id="6ea48-102">Understanding Centralized Logging Service configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6ea48-103">_**마지막으로 수정한 주제:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="6ea48-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="6ea48-104">중앙 로깅 서비스는 로깅 서비스를 수집 하는 방법, 수집 하는 방법, 수집 하는 위치, 로그 설정에 대해 정의 하도록 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ea48-104">The Centralized Logging Service is configured to define what the logging service is intended to collect, how it collects, where it will collect from, and what the log settings are.</span></span> <span data-ttu-id="6ea48-105">이러한 설정은 전체적으로 (즉, 전체 배포의 경우) 또는 사이트 (즉, 배포의 명명 된 사이트)에 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ea48-105">You define these settings globally (that is, for the entire deployment) or for a site (that is, a named site in your deployment).</span></span> <span data-ttu-id="6ea48-106">정의한 모든 로깅은 로그 시작, 중지, 플러시, 검색 명령에 사용 하는 id에 적합 한 설정을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ea48-106">Any logging that you define will use the settings that are appropriate for the identity that you use for commands to start, stop, flush, and search logs.</span></span>

<div>

## <a name="to-display-the-current-centralized-logging-service-configuration"></a><span data-ttu-id="6ea48-107">현재 중앙 집중화 된 로깅 서비스 구성을 표시 하려면</span><span class="sxs-lookup"><span data-stu-id="6ea48-107">To display the current Centralized Logging Service configuration</span></span>

1.  <span data-ttu-id="6ea48-108">Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ea48-108">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="6ea48-109">명령줄 프롬프트에 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ea48-109">Type the following at a command-line prompt:</span></span>
    
        Get-CsClsConfiguration
    
    <div>
    

    > [!TIP]
    > <span data-ttu-id="6ea48-110">"Site: Redmond"와 같이 정의 <CODE>-Identity</CODE> 및 범위를 통해 반환 되는 구성 설정의 범위를 좁히거나 확장 하 여 사이트 Redmond에 대 한 CsClsConfiguration만 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ea48-110">You can narrow or expand the scope of the configuration settings that are returned by defining <CODE>-Identity</CODE> and a scope, such as "Site:Redmond" to return only the CsClsConfiguration for the site Redmond.</span></span> <span data-ttu-id="6ea48-111">구성의 지정 된 부분에 대 한 세부 정보를 원하는 경우 다른 Windows PowerShell cmdlet에 출력을 파이프 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ea48-111">If you want details about a given portion of the configuration, you can pipe the output into another Windows PowerShell cmdlet.</span></span> <span data-ttu-id="6ea48-112">예를 들어 "Redmond" 사이트의 구성에 정의 된 시나리오에 대 한 세부 정보를 보려면 다음을 입력 합니다.<CODE>Get-CsClsConfiguration -Identity "site:Redmond" | Select-Object -ExpandPropery Scenarios</CODE></span><span class="sxs-lookup"><span data-stu-id="6ea48-112">For example, to get details about the scenarios defined in the configuration for site "Redmond", type: <CODE>Get-CsClsConfiguration -Identity "site:Redmond" | Select-Object -ExpandPropery Scenarios</CODE></span></span>

    
    </div>
    
    <span data-ttu-id="6ea48-113">![Get CsClsConfiguration의 샘플 출력입니다.] (images/JJ688029.23f98ddc-fc48-499a-b6c5-752611f2a0b0(OCS.15).jpg "Get CsClsConfiguration의 샘플 출력입니다.")</span><span class="sxs-lookup"><span data-stu-id="6ea48-113">![Sample output from Get-CsClsConfiguration.](images/JJ688029.23f98ddc-fc48-499a-b6c5-752611f2a0b0(OCS.15).jpg "Sample output from Get-CsClsConfiguration.")</span></span>
    
    <span data-ttu-id="6ea48-114">Cmdlet의 결과에는 중앙 로깅 서비스의 현재 구성이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ea48-114">The result from the cmdlet displays the current configuration of the Centralized Logging Service.</span></span>
    
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="6ea48-115">구성 설정</span><span class="sxs-lookup"><span data-stu-id="6ea48-115">Configuration Setting</span></span></th>
    <th><span data-ttu-id="6ea48-116">설명</span><span class="sxs-lookup"><span data-stu-id="6ea48-116">Description</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="6ea48-117"><strong>Identity</strong></span><span class="sxs-lookup"><span data-stu-id="6ea48-117"><strong>Identity</strong></span></span></p></td>
    <td><p><span data-ttu-id="6ea48-118">이 구성의 범위 및 이름을 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ea48-118">Identifies the scope and name for this configuration.</span></span> <span data-ttu-id="6ea48-119">글로벌 구성은 한 개, 사이트별 구성은 하나만 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ea48-119">There is only one Global configuration, and one configuration per site.</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="6ea48-120"><strong>시나리오</strong></span><span class="sxs-lookup"><span data-stu-id="6ea48-120"><strong>Scenarios</strong></span></span></p></td>
    <td><p><span data-ttu-id="6ea48-121">이 구성에 대해 정의 된 모든 시나리오의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="6ea48-121">Listing of all scenarios that are defined for this configuration.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="6ea48-122"><strong>SearchTerms</strong></span><span class="sxs-lookup"><span data-stu-id="6ea48-122"><strong>SearchTerms</strong></span></span></p></td>
    <td><p><span data-ttu-id="6ea48-123">구성에 대 한 정의 된 검색 용어입니다.</span><span class="sxs-lookup"><span data-stu-id="6ea48-123">Defined search terms for the configuration.</span></span> <span data-ttu-id="6ea48-124">Office 365, 온-프레미스 배포가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="6ea48-124">Office 365, not on-premises deployments.</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="6ea48-125"><strong>SecurityGroups</strong></span><span class="sxs-lookup"><span data-stu-id="6ea48-125"><strong>SecurityGroups</strong></span></span></p></td>
    <td><p><span data-ttu-id="6ea48-126">사용자 (즉, 보안 그룹의 구성원)를 제어 하는 정의 된 보안 그룹은 자신이 위치한 사이트를 기반으로 하는 컴퓨터를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ea48-126">Defined security groups that control who (that is, members of the security groups) can see computers based on the site they are located in.</span></span> <span data-ttu-id="6ea48-127">이 컨텍스트에서 사이트는 토폴로지 작성기에 정의 된 사이트입니다.</span><span class="sxs-lookup"><span data-stu-id="6ea48-127">Site, in this context, is the site as defined in Topology Builder.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="6ea48-128"><strong>영역과</strong></span><span class="sxs-lookup"><span data-stu-id="6ea48-128"><strong>Regions</strong></span></span></p></td>
    <td><p><span data-ttu-id="6ea48-129">정의 된 지역은 지역 (예: EMEA)에 SecurityGroups를 수집 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ea48-129">Defined regions are used to collect SecurityGroups into a region, for example EMEA.</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="6ea48-130"><strong>EtlFileFolder</strong></span><span class="sxs-lookup"><span data-stu-id="6ea48-130"><strong>EtlFileFolder</strong></span></span></p></td>
    <td><p><span data-ttu-id="6ea48-131">컴퓨터에서 로그 파일이 기록 되는 위치의 정의 된 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="6ea48-131">Defined path to the location where log files are written on computers.</span></span> <span data-ttu-id="6ea48-132">CLSAgent는 로그 파일을 기록 하 고 네트워크 서비스의 컨텍스트에서 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ea48-132">CLSAgent writes the log files and runs under the context of the Network Service.</span></span> <span data-ttu-id="6ea48-133">이 경우에 는% TEMP% 를%WINDIR%\ServiceProfiles\NetworkService\AppData\Local로 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ea48-133">In this case, %TEMP% expands to %WINDIR%\ServiceProfiles\NetworkService\AppData\Local</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="6ea48-134"><strong>EtlFileRolloverSizeMB</strong></span><span class="sxs-lookup"><span data-stu-id="6ea48-134"><strong>EtlFileRolloverSizeMB</strong></span></span></p></td>
    <td><p><span data-ttu-id="6ea48-135">매개 변수는 새 이벤트 추적 로그 (.etl) 파일이 만들어지기 전에 로그 파일의 최대 크기를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="6ea48-135">The parameter indicates the maximum size of the log file before a new event trace log (.etl) file is created.</span></span> <span data-ttu-id="6ea48-136">EtlFileRolloverMinutes에 설정 된 최대 시간이 아직 도달 하지 않은 경우에도 정의 된 크기에 도달 하면 새 로그 파일이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="6ea48-136">A new log file is created when the defined size is reached even if the maximum time set in EtlFileRolloverMinutes has not yet been reached.</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="6ea48-137"><strong>EtlFileRolloverMinutes</strong></span><span class="sxs-lookup"><span data-stu-id="6ea48-137"><strong>EtlFileRolloverMinutes</strong></span></span></p></td>
    <td><p><span data-ttu-id="6ea48-138">새 .etl 파일을 만들기 전에 로그가 대기할 수 있는 최대 시간 (분)을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ea48-138">Defined maximum amount of time, in minutes, that a log can elapse before a new .etl file is created.</span></span> <span data-ttu-id="6ea48-139">EtlFileRolloverSizeMB에 설정 된 최대 크기에 도달 하지 않은 경우에도 타이머가 만료 될 때 새 로그 파일이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="6ea48-139">A new log file is created when the timer expires even if the maximum size set in EtlFileRolloverSizeMB has not yet been reached.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="6ea48-140"><strong>TmfFileSearchPath</strong></span><span class="sxs-lookup"><span data-stu-id="6ea48-140"><strong>TmfFileSearchPath</strong></span></span></p></td>
    <td><p><span data-ttu-id="6ea48-141">추적 메시지 형식 파일을 검색 하는 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="6ea48-141">Location to search for the trace message format files.</span></span> <span data-ttu-id="6ea48-142">추적 메시지 형식 파일은 이진 파일을 사람이 읽을 수 있는 형식으로 변환 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ea48-142">The trace message format files are used to convert the binary files into a human readable format.</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="6ea48-143"><strong>CacheFileLocalFolders</strong></span><span class="sxs-lookup"><span data-stu-id="6ea48-143"><strong>CacheFileLocalFolders</strong></span></span></p></td>
    <td><p><span data-ttu-id="6ea48-144">컴퓨터에 캐시 파일이 기록 되는 위치에 대 한 정의 된 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="6ea48-144">Defined path to the location where cache files are written on computers.</span></span> <span data-ttu-id="6ea48-145">CLSAgent는 캐시 파일을 기록 하 고 네트워크 서비스의 컨텍스트에서 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ea48-145">CLSAgent writes the cache files and runs under the context of the Network Service.</span></span> <span data-ttu-id="6ea48-146">이 경우에 는% TEMP% 를%WINDIR%\ServiceProfiles\NetworkService\AppData\Local.로 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ea48-146">In this case, %TEMP% expands to %WINDIR%\ServiceProfiles\NetworkService\AppData\Local.</span></span> <span data-ttu-id="6ea48-147">기본적으로 캐시 파일 및 로그 파일은 동일한 디렉터리에 기록 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ea48-147">By default, cache files and log files are written to the same directory.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="6ea48-148"><strong>CacheFileNetworkFolder</strong></span><span class="sxs-lookup"><span data-stu-id="6ea48-148"><strong>CacheFileNetworkFolder</strong></span></span></p></td>
    <td><p><span data-ttu-id="6ea48-149">로깅 작업 중 캐시 파일을 받을 UNC (범용 명명 규칙) 경로를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ea48-149">You can define a universal naming convention (UNC) path to receive the cache files during logging operations.</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="6ea48-150"><strong>Cachefilelocal보존 기간</strong></span><span class="sxs-lookup"><span data-stu-id="6ea48-150"><strong>CacheFileLocalRetentionPeriod</strong></span></span></p></td>
    <td><p><span data-ttu-id="6ea48-151">캐시 파일이 유지 되는 최대 시간 (일)으로 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ea48-151">Defined as the maximum time, in days, that cache files are retained.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="6ea48-152"><strong>CacheFileMaxDiskUsage</strong></span><span class="sxs-lookup"><span data-stu-id="6ea48-152"><strong>CacheFileMaxDiskUsage</strong></span></span></p></td>
    <td><p><span data-ttu-id="6ea48-153">캐시 파일에서 사용할 수 있는 디스크 공간의 백분율로 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ea48-153">Defined as the percentage of disk space that can be used by the cache files.</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="6ea48-154"><strong>ComponentThrottleLimit</strong></span><span class="sxs-lookup"><span data-stu-id="6ea48-154"><strong>ComponentThrottleLimit</strong></span></span></p></td>
    <td><p><span data-ttu-id="6ea48-155">자동 스로틀 limiter 트리거되기 전에 구성 요소가 생성할 수 있는 초당 최대 추적 수로 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ea48-155">Defined as the maximum number of traces per second that a component can produce before the automatic throttle limiter is triggered.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="6ea48-156"><strong>ComponentThrottleSample</strong></span><span class="sxs-lookup"><span data-stu-id="6ea48-156"><strong>ComponentThrottleSample</strong></span></span></p></td>
    <td><p><span data-ttu-id="6ea48-157">ComponentThrottleLimit를 초과할 수 있는 60 초의 시간 수입니다.</span><span class="sxs-lookup"><span data-stu-id="6ea48-157">Number of times in 60 seconds that the ComponentThrottleLimit can be exceeded.</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="6ea48-158"><strong>이상 Clsagentserviceversion</strong></span><span class="sxs-lookup"><span data-stu-id="6ea48-158"><strong>MinimumClsAgentServiceVersion</strong></span></span></p></td>
    <td><p><span data-ttu-id="6ea48-159">실행할 수 있는 CLSAgent의 최소 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="6ea48-159">The minimum version of the CLSAgent allowed to run.</span></span> <span data-ttu-id="6ea48-160">이 요소는 Office 365를 대상으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ea48-160">This element is intended for Office 365.</span></span></p></td>
    </tr>
    </tbody>
    </table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="6ea48-161">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6ea48-161">See Also</span></span>


[<span data-ttu-id="6ea48-162">Lync Server 2013의 중앙 집중화 된 로깅 서비스 개요</span><span class="sxs-lookup"><span data-stu-id="6ea48-162">Overview of the Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-overview-of-the-centralized-logging-service.md)  


<span data-ttu-id="6ea48-163">[Set-CsClsConfiguration](https://technet.microsoft.com/en-us/library/JJ619182(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6ea48-163">[Set-CsClsConfiguration](https://technet.microsoft.com/en-us/library/JJ619182(v=OCS.15))</span></span>  
<span data-ttu-id="6ea48-164">[-CsClsConfiguration 제거](https://technet.microsoft.com/en-us/library/JJ619191(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6ea48-164">[Remove-CsClsConfiguration](https://technet.microsoft.com/en-us/library/JJ619191(v=OCS.15))</span></span>  
<span data-ttu-id="6ea48-165">[New-CsClsConfiguration](https://technet.microsoft.com/en-us/library/JJ619177(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6ea48-165">[New-CsClsConfiguration](https://technet.microsoft.com/en-us/library/JJ619177(v=OCS.15))</span></span>  
<span data-ttu-id="6ea48-166">[Get-CsClsConfiguration](https://technet.microsoft.com/en-us/library/JJ619179(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6ea48-166">[Get-CsClsConfiguration](https://technet.microsoft.com/en-us/library/JJ619179(v=OCS.15))</span></span>  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

