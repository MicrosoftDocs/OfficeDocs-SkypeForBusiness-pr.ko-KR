---
title: 중앙화 된 로깅 서비스 구성 설정 이해
description: 중앙화 된 로깅 서비스 구성 설정 이해
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Understanding Centralized Logging Service configuration settings
ms:assetid: 3c34e600-0b91-43dc-b4cc-90b6a70ee12e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688029(v=OCS.15)
ms:contentKeyID: 49733619
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0f99dbffe15c4b3f0dc13d231c3a2732a8554397
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542404"
---
# <a name="understanding-centralized-logging-service-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="d1042-103">Lync Server 2013의 중앙 로깅 서비스 구성 설정 이해</span><span class="sxs-lookup"><span data-stu-id="d1042-103">Understanding Centralized Logging Service configuration settings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d1042-104">_**마지막으로 수정 된 항목:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="d1042-104">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="d1042-105">중앙 로깅 서비스는 로깅 서비스에서 수집할 대상, 수집 방법, 수집 되는 위치 및 로그 설정에 따라 정의 하도록 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1042-105">The Centralized Logging Service is configured to define what the logging service is intended to collect, how it collects, where it will collect from, and what the log settings are.</span></span> <span data-ttu-id="d1042-106">이러한 설정은 전역으로 (즉, 전체 배포의 경우) 또는 사이트 (즉, 배포의 명명 된 사이트)에 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1042-106">You define these settings globally (that is, for the entire deployment) or for a site (that is, a named site in your deployment).</span></span> <span data-ttu-id="d1042-107">사용자가 정의하는 모든 로깅에는 로그를 시작, 중지, 플러시 및 검색하기 위한 명령에 사용하는 identity에 적합한 설정이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1042-107">Any logging that you define will use the settings that are appropriate for the identity that you use for commands to start, stop, flush, and search logs.</span></span>

<div>

## <a name="to-display-the-current-centralized-logging-service-configuration"></a><span data-ttu-id="d1042-108">현재 중앙화 된 로깅 서비스 구성을 표시 하려면</span><span class="sxs-lookup"><span data-stu-id="d1042-108">To display the current Centralized Logging Service configuration</span></span>

1.  <span data-ttu-id="d1042-109">**시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="d1042-109">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="d1042-110">명령줄 프롬프트에 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="d1042-110">Type the following at a command-line prompt:</span></span>
    
        Get-CsClsConfiguration
    
    <div>
    

    > [!TIP]
    > <span data-ttu-id="d1042-111">"Site: Redmond"와 같이 정의 및 범위로 반환 되는 구성 설정의 범위를 좁히거나 확장 <CODE>-Identity</CODE> 하 여 사이트 Redmond에 대 한 CsClsConfiguration만 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1042-111">You can narrow or expand the scope of the configuration settings that are returned by defining <CODE>-Identity</CODE> and a scope, such as "Site:Redmond" to return only the CsClsConfiguration for the site Redmond.</span></span> <span data-ttu-id="d1042-112">구성의 지정 된 부분에 대 한 세부 정보를 원하는 경우 다른 Windows PowerShell cmdlet에 출력을 파이프 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1042-112">If you want details about a given portion of the configuration, you can pipe the output into another Windows PowerShell cmdlet.</span></span> <span data-ttu-id="d1042-113">예를 들어 "Redmond" 사이트의 구성에 정의 된 시나리오에 대 한 세부 정보를 보려면 다음을 입력 합니다. <CODE>Get-CsClsConfiguration -Identity "site:Redmond" | Select-Object -ExpandPropery Scenarios</CODE></span><span class="sxs-lookup"><span data-stu-id="d1042-113">For example, to get details about the scenarios defined in the configuration for site "Redmond", type: <CODE>Get-CsClsConfiguration -Identity "site:Redmond" | Select-Object -ExpandPropery Scenarios</CODE></span></span>

    
    </div>
    
    <span data-ttu-id="d1042-114">![Get CsClsConfiguration의 예제 출력입니다.](images/JJ688029.23f98ddc-fc48-499a-b6c5-752611f2a0b0(OCS.15).jpg "Get CsClsConfiguration의 예제 출력입니다.")</span><span class="sxs-lookup"><span data-stu-id="d1042-114">![Sample output from Get-CsClsConfiguration.](images/JJ688029.23f98ddc-fc48-499a-b6c5-752611f2a0b0(OCS.15).jpg "Sample output from Get-CsClsConfiguration.")</span></span>
    
    <span data-ttu-id="d1042-115">이 cmdlet의 결과에는 중앙화 된 로깅 서비스의 현재 구성이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1042-115">The result from the cmdlet displays the current configuration of the Centralized Logging Service.</span></span>
    
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="d1042-116">구성 설정</span><span class="sxs-lookup"><span data-stu-id="d1042-116">Configuration Setting</span></span></th>
    <th><span data-ttu-id="d1042-117">설명</span><span class="sxs-lookup"><span data-stu-id="d1042-117">Description</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="d1042-118"><strong>ID</strong></span><span class="sxs-lookup"><span data-stu-id="d1042-118"><strong>Identity</strong></span></span></p></td>
    <td><p><span data-ttu-id="d1042-p103">이 구성의 범위 및 이름을 식별합니다. 전역 구성 한 개와 사이트당 한 개의 구성만 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1042-p103">Identifies the scope and name for this configuration. There is only one Global configuration, and one configuration per site.</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="d1042-121"><strong>시나리오</strong></span><span class="sxs-lookup"><span data-stu-id="d1042-121"><strong>Scenarios</strong></span></span></p></td>
    <td><p><span data-ttu-id="d1042-122">이 구성에 대해 정의된 모든 시나리오를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="d1042-122">Listing of all scenarios that are defined for this configuration.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="d1042-123"><strong>SearchTerms</strong></span><span class="sxs-lookup"><span data-stu-id="d1042-123"><strong>SearchTerms</strong></span></span></p></td>
    <td><p><span data-ttu-id="d1042-124">구성에 대해 정의된 검색어입니다.</span><span class="sxs-lookup"><span data-stu-id="d1042-124">Defined search terms for the configuration.</span></span> <span data-ttu-id="d1042-125">온-프레미스 배포를 사용 하지 않는 Office 365 또는 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d1042-125">Office 365 or Microsoft 365, not on-premises deployments.</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="d1042-126"><strong>SecurityGroups</strong></span><span class="sxs-lookup"><span data-stu-id="d1042-126"><strong>SecurityGroups</strong></span></span></p></td>
    <td><p><span data-ttu-id="d1042-127">사용자가 위치한 사이트를 기반으로 컴퓨터를 볼 수 있는 사용자(즉, 보안 그룹의 구성원)를 제어하는 정의된 보안 그룹입니다.</span><span class="sxs-lookup"><span data-stu-id="d1042-127">Defined security groups that control who (that is, members of the security groups) can see computers based on the site they are located in.</span></span> <span data-ttu-id="d1042-128">이 컨텍스트에서 사이트는 토폴로지 작성기에 정의 된 사이트입니다.</span><span class="sxs-lookup"><span data-stu-id="d1042-128">Site, in this context, is the site as defined in Topology Builder.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="d1042-129"><strong>일치</strong></span><span class="sxs-lookup"><span data-stu-id="d1042-129"><strong>Regions</strong></span></span></p></td>
    <td><p><span data-ttu-id="d1042-130">정의된 지역은 특정 지역(예: EMEA)에서 SecurityGroups를 수집하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1042-130">Defined regions are used to collect SecurityGroups into a region, for example EMEA.</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="d1042-131"><strong>EtlFileFolder</strong></span><span class="sxs-lookup"><span data-stu-id="d1042-131"><strong>EtlFileFolder</strong></span></span></p></td>
    <td><p><span data-ttu-id="d1042-p106">컴퓨터에서 로그 파일을 기록할 위치에 대해 정의된 경로입니다. CLSAgent는 네트워크 서비스의 컨텍스트에 따라 로그 파일을 기록하고 실행됩니다. 여기에서 %TEMP%는 %WINDIR%\ServiceProfiles\NetworkService\AppData\Local로 확장됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1042-p106">Defined path to the location where log files are written on computers. CLSAgent writes the log files and runs under the context of the Network Service. In this case, %TEMP% expands to %WINDIR%\ServiceProfiles\NetworkService\AppData\Local</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="d1042-135"><strong>EtlFileRolloverSizeMB</strong></span><span class="sxs-lookup"><span data-stu-id="d1042-135"><strong>EtlFileRolloverSizeMB</strong></span></span></p></td>
    <td><p><span data-ttu-id="d1042-p107">이 매개 변수는 새 이벤트 추적 로그(.etl) 파일을 만들기 전 로그 파일의 최대 크기를 나타냅니다. EtlFileRolloverMinutes에 설정된 최대 시간에 아직 도달하지 않았어도 정의된 크기에 도달하면 새 로그 파일이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="d1042-p107">The parameter indicates the maximum size of the log file before a new event trace log (.etl) file is created. A new log file is created when the defined size is reached even if the maximum time set in EtlFileRolloverMinutes has not yet been reached.</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="d1042-138"><strong>EtlFileRolloverMinutes</strong></span><span class="sxs-lookup"><span data-stu-id="d1042-138"><strong>EtlFileRolloverMinutes</strong></span></span></p></td>
    <td><p><span data-ttu-id="d1042-p108">새 .etl 파일을 만들기 전에 로그에서 경과될 수 있도록 정의된 최대 시간(분)입니다. 할 수 있도록 EtlFileRolloverSizeMB에 설정된 최대 크기에 아직 도달하지 않았어도 타이머 시간이 초과되면 새 로그 파일이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="d1042-p108">Defined maximum amount of time, in minutes, that a log can elapse before a new .etl file is created. A new log file is created when the timer expires even if the maximum size set in EtlFileRolloverSizeMB has not yet been reached.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="d1042-141"><strong>TmfFileSearchPath</strong></span><span class="sxs-lookup"><span data-stu-id="d1042-141"><strong>TmfFileSearchPath</strong></span></span></p></td>
    <td><p><span data-ttu-id="d1042-p109">추적 메시지 형식 파일을 검색할 위치입니다. 추적 메시지 형식 파일은 바이너리 파일을 사람이 읽을 수 있는 형식으로 변환하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1042-p109">Location to search for the trace message format files. The trace message format files are used to convert the binary files into a human readable format.</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="d1042-144"><strong>Cachefilelocalfolders 경로가</strong></span><span class="sxs-lookup"><span data-stu-id="d1042-144"><strong>CacheFileLocalFolders</strong></span></span></p></td>
    <td><p><span data-ttu-id="d1042-p110">컴퓨터에서 캐시 파일을 기록할 위치에 대해 정의된 경로입니다. CLSAgent는 네트워크 서비스의 컨텍스트에 따라 캐시 파일을 기록하고 실행됩니다. 여기서 %TEMP%는 %WINDIR%\ServiceProfiles\NetworkService\AppData\Local로 확장됩니다. 기본적으로 캐시 파일과 로그 파일은 동일한 디렉터리에 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1042-p110">Defined path to the location where cache files are written on computers. CLSAgent writes the cache files and runs under the context of the Network Service. In this case, %TEMP% expands to %WINDIR%\ServiceProfiles\NetworkService\AppData\Local. By default, cache files and log files are written to the same directory.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="d1042-149"><strong>CacheFileNetworkFolder</strong></span><span class="sxs-lookup"><span data-stu-id="d1042-149"><strong>CacheFileNetworkFolder</strong></span></span></p></td>
    <td><p><span data-ttu-id="d1042-150">로깅 작업 중 캐시 파일을 수신하기 위한 UNC(범용 명명 규칙) 경로를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1042-150">You can define a universal naming convention (UNC) path to receive the cache files during logging operations.</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="d1042-151"><strong>Cachefilelocal보존 기간</strong></span><span class="sxs-lookup"><span data-stu-id="d1042-151"><strong>CacheFileLocalRetentionPeriod</strong></span></span></p></td>
    <td><p><span data-ttu-id="d1042-152">캐시 파일을 보존할 수 있는 최대 시간(일)으로 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1042-152">Defined as the maximum time, in days, that cache files are retained.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="d1042-153"><strong>CacheFileMaxDiskUsage</strong></span><span class="sxs-lookup"><span data-stu-id="d1042-153"><strong>CacheFileMaxDiskUsage</strong></span></span></p></td>
    <td><p><span data-ttu-id="d1042-154">캐시 파일이 사용할 수 있는 디스크 공간 비율로 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1042-154">Defined as the percentage of disk space that can be used by the cache files.</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="d1042-155"><strong>ComponentThrottleLimit</strong></span><span class="sxs-lookup"><span data-stu-id="d1042-155"><strong>ComponentThrottleLimit</strong></span></span></p></td>
    <td><p><span data-ttu-id="d1042-156">자동 스로틀 리미터가 트리거되기 전 구성 요소가 생성할 수 있는 초당 최대 추적 수로 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1042-156">Defined as the maximum number of traces per second that a component can produce before the automatic throttle limiter is triggered.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="d1042-157"><strong>ComponentThrottleSample</strong></span><span class="sxs-lookup"><span data-stu-id="d1042-157"><strong>ComponentThrottleSample</strong></span></span></p></td>
    <td><p><span data-ttu-id="d1042-158">ComponentThrottleLimit를 초과할 수 있는 횟수(60초 이내)입니다.</span><span class="sxs-lookup"><span data-stu-id="d1042-158">Number of times in 60 seconds that the ComponentThrottleLimit can be exceeded.</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="d1042-159"><strong>이상 Clsagentserviceversion</strong></span><span class="sxs-lookup"><span data-stu-id="d1042-159"><strong>MinimumClsAgentServiceVersion</strong></span></span></p></td>
    <td><p><span data-ttu-id="d1042-160">실행할 수 있는 CLSAgent의 최소 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="d1042-160">The minimum version of the CLSAgent allowed to run.</span></span> <span data-ttu-id="d1042-161">이 요소는 Office 365 또는 Microsoft 365에 사용 하기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d1042-161">This element is intended for Office 365 or Microsoft 365.</span></span></p></td>
    </tr>
    </tbody>
    </table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d1042-162">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d1042-162">See Also</span></span>


[<span data-ttu-id="d1042-163">Lync Server 2013의 중앙 로깅 서비스 개요</span><span class="sxs-lookup"><span data-stu-id="d1042-163">Overview of the Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-overview-of-the-centralized-logging-service.md)  


<span data-ttu-id="d1042-164">[설정-CsClsConfiguration](https://technet.microsoft.com/library/JJ619182(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d1042-164">[Set-CsClsConfiguration](https://technet.microsoft.com/library/JJ619182(v=OCS.15))</span></span>  
<span data-ttu-id="d1042-165">[제거-CsClsConfiguration](https://technet.microsoft.com/library/JJ619191(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d1042-165">[Remove-CsClsConfiguration](https://technet.microsoft.com/library/JJ619191(v=OCS.15))</span></span>  
<span data-ttu-id="d1042-166">[신규-CsClsConfiguration](https://technet.microsoft.com/library/JJ619177(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d1042-166">[New-CsClsConfiguration](https://technet.microsoft.com/library/JJ619177(v=OCS.15))</span></span>  
<span data-ttu-id="d1042-167">[Get-CsClsConfiguration](https://technet.microsoft.com/library/JJ619179(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d1042-167">[Get-CsClsConfiguration](https://technet.microsoft.com/library/JJ619179(v=OCS.15))</span></span>  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

