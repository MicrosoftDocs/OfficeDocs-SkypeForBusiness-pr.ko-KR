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
ms.openlocfilehash: 68f2589e6c30a6ca928230dde2deb32f23e91967
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42215874"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="overview-of-the-centralized-logging-service-in-lync-server-2013"></a><span data-ttu-id="7ffe8-102">Lync Server 2013의 중앙 로깅 서비스 개요</span><span class="sxs-lookup"><span data-stu-id="7ffe8-102">Overview of the Centralized Logging Service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7ffe8-103">_**마지막으로 수정 된 항목:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="7ffe8-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="7ffe8-104">중앙 로깅 서비스는 범위가 광범위 하거나 좁은 범위를 사용 하 여 제어 되는 데이터 모음에 대 한 수단을 제공 하도록 설계 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="7ffe8-104">The Centralized Logging Service is designed to provide a means for controlled collection of data—with a broad or narrow scope.</span></span> <span data-ttu-id="7ffe8-105">배포의 모든 서버에서 동시에 데이터를 수집할 수 있으며, 추적할 특정 요소를 정의하고 추적 플래그를 설정하여 단일 컴퓨터에서 검색 결과를 반환하거나 전체 서버의 모든 데이터 집합체에서 검색 결과를 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ffe8-105">You can collect data from all servers in the deployment concurrently, define specific elements to trace, set trace flags and return search results from a single computer or an aggregation of all data from all servers.</span></span> <span data-ttu-id="7ffe8-106">배포의 모든 서버에서 중앙 로깅 서비스가 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7ffe8-106">The Centralized Logging Service runs on all servers in your deployment.</span></span> <span data-ttu-id="7ffe8-107">중앙 로깅 서비스의 아키텍처는 다음과 같은 에이전트와 서비스로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7ffe8-107">The architecture of the Centralized Logging Service is comprised of the following agents and services:</span></span>

  - <span data-ttu-id="7ffe8-108">*중앙 로깅 서비스 에이전트*   clsagent는 컨트롤러와 통신 하 고 관리자가 컨트롤러를 실행 하는 명령을 수신 하는 서비스 실행 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="7ffe8-108">*Centralized Logging Service Agent*   ClsAgent.exe is the service executable that communicates with the controller and receives the commands that the controller is issued by the administrator.</span></span> <span data-ttu-id="7ffe8-109">에이전트는 각 Lync Server 컴퓨터에서 서비스로 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7ffe8-109">The agent is run as a service on each Lync Server computer.</span></span> <span data-ttu-id="7ffe8-110">이 에이전트는 명령을 받으면 명령을 실행하며 추적하도록 정의된 구성 요소에 메시지를 전송하고 추적 로그를 디스크에 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="7ffe8-110">When the agent receives a command, it executes the command, sends messages to the defined components for tracing, and writes the trace logs to disk.</span></span> <span data-ttu-id="7ffe8-111">또한 해당 컴퓨터에 대한 추적 로그를 읽고 요청 시 추적 데이터를 컨트롤러로 다시 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="7ffe8-111">It also reads the trace logs for its computer and sends the trace data back to the controller when requested.</span></span> <span data-ttu-id="7ffe8-112">ClsAgent는 **TCP 50001**, **TCP 50002** 및 **TCP 50003** 포트에서 명령을 수신합니다.</span><span class="sxs-lookup"><span data-stu-id="7ffe8-112">The ClsAgent listens for commands on the following ports: **TCP 50001**, **TCP 50002**, and **TCP 50003**.</span></span>

  - <span data-ttu-id="7ffe8-113">*중앙 로깅 서비스 컨트롤러*   clscontrollerlib는 Lync Server 관리 셸 및 clscontroller .exe에 대 한 명령 실행 엔진입니다.</span><span class="sxs-lookup"><span data-stu-id="7ffe8-113">*Centralized Logging Service Controller*   ClsControllerLib.dll is the command execution engine for the Lync Server Management Shell and for ClsController.exe.</span></span> <span data-ttu-id="7ffe8-114">CLSControllerLib는 ClsAgent에 시작, 중지, 플러시 및 검색 명령을 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="7ffe8-114">CLSControllerLib.dll sends Start, Stop, Flush, and Search commands to the ClsAgent.</span></span> <span data-ttu-id="7ffe8-115">검색 명령을 보내면 결과 로그가 ClsControllerLib로 반환 되 고 집계 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7ffe8-115">When search commands are sent, the resulting logs are returned to the ClsControllerLib.dll and aggregated.</span></span> <span data-ttu-id="7ffe8-116">컨트롤러는 에이전트에 명령을 전송 하 고, 이러한 명령의 상태를 수신 하 고, 검색 범위에 있는 모든 컴퓨터의 모든 에이전트에서 반환 되는 검색 로그 파일 데이터를 관리 하 고, 로그 데이터를 의미 있고 순서가 지정 된 것으로 집계 하는 역할을 합니다. 출력 집합</span><span class="sxs-lookup"><span data-stu-id="7ffe8-116">The controller is responsible for sending commands to the agent, receiving the status of those commands and managing the search log file data as it is returned from all agents on any computer in the search scope, and aggregating the log data into a meaningful and ordered output set.</span></span> <span data-ttu-id="7ffe8-117">다음 항목의 정보는 Lync Server 관리 셸을 사용 하 여 중점적으로 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ffe8-117">The information in the following topics is focused on using the Lync Server Management Shell.</span></span> <span data-ttu-id="7ffe8-118">ClsController이 Lync Server 관리 셸에서 사용할 수 있는 기능 및 기능의 하위 집합으로 제한 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7ffe8-118">ClsController.exe is limited to a subset of the features and functions that are available in the Lync Server Management Shell.</span></span> <span data-ttu-id="7ffe8-119">ClsController에 대 한 도움말은 명령줄에서 기본 `ClsController` 디렉터리 C:\\Program Files\\Common files\\Microsoft Lync Server 2013\\clscontroller에 입력 하 여 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ffe8-119">Help for ClsController.exe is available at the command line by typing `ClsController` in the default directory C:\\Program Files\\Common Files\\Microsoft Lync Server 2013\\ClsAgent.</span></span>

<span data-ttu-id="7ffe8-120">**ClsController에서 ClsAgent로의 통신**</span><span class="sxs-lookup"><span data-stu-id="7ffe8-120">**ClsController communications to ClsAgent**</span></span>

<span data-ttu-id="7ffe8-121">![CLSController와 Clscontroller 간의 관계입니다.](images/JJ688145.68c90811-5cf9-4a84-95b7-ea9ffc61eac4(OCS.15).jpg "CLSController와 Clscontroller 간의 관계입니다.")</span><span class="sxs-lookup"><span data-stu-id="7ffe8-121">![Relationship between CLSController and CLSAgent.](images/JJ688145.68c90811-5cf9-4a84-95b7-ea9ffc61eac4(OCS.15).jpg "Relationship between CLSController and CLSAgent.")</span></span>

<span data-ttu-id="7ffe8-122">Windows Server 명령줄 인터페이스를 사용 하거나 Lync Server 관리 셸을 사용 하 여 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ffe8-122">You issue commands using the Windows Server command-line interface or using the Lync Server Management Shell.</span></span> <span data-ttu-id="7ffe8-123">명령은 로그인된 컴퓨터에서 실행되어 ClsAgent에 로컬로 전송되거나 배포의 다른 컴퓨터 및 풀로 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="7ffe8-123">The commands are executed on the computer you are logged in to and sent to the ClsAgent locally or to the other computers and pools in your deployment.</span></span>

<span data-ttu-id="7ffe8-124">ClsAgent는 로컬 컴퓨터에 있는 모든 .CACHE 파일의 인덱스 파일을 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="7ffe8-124">ClsAgent maintains an index file of all .CACHE files that it has on the local machine.</span></span> <span data-ttu-id="7ffe8-125">ClsAgent는 CacheFileLocalFolders 옵션으로 정의된 모든 볼륨에 걸쳐 균등하게 분산되도록 .CACHE 파일을 할당하며 각 볼륨의 80% 이하만 사용합니다(**Set-CsClsConfiguration** cmdlet을 사용하여 로컬 캐시 위치와 비율을 구성 가능).</span><span class="sxs-lookup"><span data-stu-id="7ffe8-125">ClsAgent allocates them so that they are evenly distributed across volumes defined by the option CacheFileLocalFolders, never consuming more than 80% of each volume (that is, the local cache location and the percentage is configurable using the **Set-CsClsConfiguration** cmdlet).</span></span> <span data-ttu-id="7ffe8-126">또한 ClsAgent는 오래된 캐시된 이벤트 추적 로그(.etl) 파일을 로컬 컴퓨터에서 에이징합니다.</span><span class="sxs-lookup"><span data-stu-id="7ffe8-126">ClsAgent is also responsible for aging old cached event trace log (.etl) files off the local machine.</span></span> <span data-ttu-id="7ffe8-127">2주 후에(**Set-CsClsConfiguration** cmdlet을 사용하여 기간을 구성 가능) 이러한 파일은 파일 공유로 복사되어 로컬 컴퓨터에서 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="7ffe8-127">After two weeks (that is, the timeframe is configurable using the **Set-CsClsConfiguration** cmdlet) these files are copied to a file share and deleted from the local computer.</span></span> <span data-ttu-id="7ffe8-128">자세한 내용은 [Set-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsClsConfiguration)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="7ffe8-128">For details, see [Set-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsClsConfiguration).</span></span> <span data-ttu-id="7ffe8-129">검색 요청이 수신되면 검색 조건을 사용하여 캐시된 .etl 파일 집합을 선택하고 에이전트에서 유지되는 인덱스의 값을 사용하여 검색을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="7ffe8-129">When a search request is received, the search criteria is used to select the set of cached .etl files to perform the search based on the values in the index maintained by the agent.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7ffe8-p106">로컬 컴퓨터에서 파일 공유로 이동된 파일은 ClsAgent에서 검색할 수 있습니다. ClsAgent에서 파일을 파일 공유로 이동한 후에는 해당 파일의 에이징 및 제거를 유지하지 않습니다. 사용자는 파일 공유에서 파일 크기를 모니터링하여 파일을 삭제하거나 보관하는 관리 작업을 정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ffe8-p106">Files that are moved to the file share from the local computer can be searched by ClsAgent. Once ClsAgent moves the files to the file share, the aging and removal of files is not maintained by ClsAgent. You should define an administrative task to monitor the size of the files in the file share and delete them or archive them.</span></span>



</div>

<span data-ttu-id="7ffe8-133">결과 로그 파일은 **Snooper.exe**를 비롯한 다양한 도구와 텍스트 파일을 읽을 수 있는 모든 도구(예: **Notepad.exe**)를 사용하여 읽고 분석할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ffe8-133">The resulting log files can be read and analyzed using a variety of tools, including **Snooper.exe** and any tool that can read a text file, such as **Notepad.exe**.</span></span> <span data-ttu-id="7ffe8-134">Snooper은 Lync Server 2013 디버그 도구에 속하며에서 [https://go.microsoft.com/fwlink/?LinkId=285257](https://go.microsoft.com/fwlink/?linkid=285257)웹으로 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ffe8-134">Snooper.exe is part of the Lync Server 2013 Debug Tools and is available as a Web download from [https://go.microsoft.com/fwlink/?LinkId=285257](https://go.microsoft.com/fwlink/?linkid=285257).</span></span>

<span data-ttu-id="7ffe8-135">OCSLogger와 마찬가지로, 중앙화 된 로깅 서비스에는 추적할 구성 요소가 몇 개 있으며, TF\_COMPONENT 및 tf\_DIAG와 같은 플래그를 선택할 수 있는 옵션을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ffe8-135">Like OCSLogger, the Centralized Logging Service has several components to trace against, and provides options to select flags, such as TF\_COMPONENT and TF\_DIAG.</span></span> <span data-ttu-id="7ffe8-136">또한 중앙화 된 로깅 서비스에는 OCSLogger의 로깅 수준 옵션도 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7ffe8-136">Centralized Logging Service also retains the logging level options of OCSLogger.</span></span>

<span data-ttu-id="7ffe8-137">명령줄 ClsController에서 Lync Server 관리 셸을 사용 하는 가장 중요 한 이점은 문제 공간, 사용자 지정 플래그 및 로깅 수준을 대상으로 하는 선택한 공급자를 사용 하 여 새 시나리오를 구성 하 고 정의할 수 있다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="7ffe8-137">The most important advantage to using the Lync Server Management Shell over the command-line ClsController is that you can configure and define new scenarios using selected providers that target the problem space, custom flags, and logging levels.</span></span> <span data-ttu-id="7ffe8-138">반면 ClsController에서 사용할 수 있는 시나리오는 실행 파일에 정의된 시나리오로 한정됩니다.</span><span class="sxs-lookup"><span data-stu-id="7ffe8-138">The scenarios available to ClsController are limited to those that are defined for the executable.</span></span>

<span data-ttu-id="7ffe8-p110">이전 버전에서는 관리자와 지원 담당자가 배포의 컴퓨터에서 추적 파일을 수집할 수 있도록 OCSLogger.exe가 제공되었습니다. OCSLogger는 다양한 장점이 있지만 한 가지 단점이 있습니다. 즉, 한 번에 한 컴퓨터에서만 로그를 수집할 수 있습니다. 별도의 OCSLogger를 사용하여 여러 컴퓨터에 로그온할 수도 있지만 이렇게 하면 여러 로그가 생성되며 결과를 집계하기 어렵습니다.</span><span class="sxs-lookup"><span data-stu-id="7ffe8-p110">In previous versions, OCSLogger.exe was provided to enable administrators and support personnel to collect trace files from computers in the deployment. OCSLogger, for all of its strengths, had a shortcoming. You could only collect logs on one computer at a given time. You could log on to multiple computers by using separate copies of OCSLogger, but you ended up with multiple logs and no easy way to aggregate the results.</span></span>

<span data-ttu-id="7ffe8-p111">사용자가 로그 검색을 요청하면 ClsController는 선택된 시나리오에 따라 요청을 전송할 컴퓨터를 결정합니다. 또한 저장된 .etl 파일이 있는 파일 공유로 검색을 전송해야 할지 여부를 결정합니다. 검색 결과가 ClsController에 반환되면 이 컨트롤러는 결과를 시간순으로 정렬된 단일 결과 집합으로 병합하여 사용자에게 제공합니다. 사용자는 검색 결과를 로컬 컴퓨터에 저장하여 추가로 분석할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ffe8-p111">When a user requests a log search, the ClsController determines which machines to send the request to (that is, based on the scenarios selected). It also determines whether the search needs to be sent to the file share where the saved .etl files are located. When the search results are returned to the ClsController, the controller merges the results into a single time-ordered result set that is presented to the user. Users can save the search results to their local machine for further analysis.</span></span>

<span data-ttu-id="7ffe8-p112">로깅 세션을 시작할 때 해결할 문제와 관련된 시나리오를 지정해야 합니다. 한 번에 두 시나리오를 실행할 수 있으며, 그 중 하나는 AlwaysOn 시나리오여야 합니다. 이름에서 알 수 있듯이 AlwaysOn 시나리오는 모든 컴퓨터, 풀 및 구성 요소에 대한 정보를 수집하며 배포에서 항상 실행되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ffe8-p112">When you start a logging session, you specify scenarios that are relative to the problem that you are trying to resolve. You can have two scenarios running at any time. One of these two scenarios should be the AlwaysOn scenario. As the name implies, it should always be running in your deployment, collecting information on all computers, pools, and components.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="7ffe8-151">기본적으로 AlwaysOn 시나리오는 배포에서 실행 되 고 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7ffe8-151">By default, the AlwaysOn scenario is not running in your deployment.</span></span> <span data-ttu-id="7ffe8-152">이 시나리오는 명시적으로 시작 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ffe8-152">You must explicitly start the scenario.</span></span> <span data-ttu-id="7ffe8-153">일단 시작 되 면이 작업은 명시적으로 중지 될 때까지 계속 실행 되며, 실행 중 상태는 컴퓨터를 다시 부팅 하는 과정을 통해 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7ffe8-153">Once started, it will continue to run until explicitly stopped, and the running state will persist through reboots of the computers.</span></span> <span data-ttu-id="7ffe8-154">시작 및 중지 시나리오에 대 한 자세한 내용은 <A href="lync-server-2013-using-start-for-the-centralized-logging-service-to-capture-logs.md">중앙화 된 로깅 서비스에 시작을 사용 하 여 Lync server 2013에서 로그 캡처</A> 및 <A href="lync-server-2013-using-stop-for-the-centralized-logging-service.md">lync Server 2013의 중앙 로깅 서비스에 대해 중지를 사용</A>을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="7ffe8-154">For details on starting and stopping scenarios, see <A href="lync-server-2013-using-start-for-the-centralized-logging-service-to-capture-logs.md">Using Start for the Centralized Logging Service to capture logs in Lync Server 2013</A> and <A href="lync-server-2013-using-stop-for-the-centralized-logging-service.md">Using Stop for the Centralized Logging Service in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="7ffe8-p114">문제가 발생할 경우 보고된 문제와 관련된 두 번째 시나리오를 시작합니다. 문제를 재현하고 두 번째 시나리오의 로깅을 중지합니다. 그런 다음 보고된 문제와 관련된 로그 검색을 시작합니다. 집계된 로그 컬렉션을 사용하여 사이트 내 모든 컴퓨터 또는 전체 배포 범위의 추적 메시지가 포함된 로그 파일이 생성됩니다. 검색 결과 제대로 분석할 수 없을 정도로 많은 데이터가 반환될 경우("신호 대 노이즈 비율"에서 노이즈가 너무 높음) 보다 좁은 범위의 매개 변수를 사용하여 검색을 다시 실행할 수 있습니다. 이렇게 하면 나타나는 패턴을 인식하여 문제에 더욱 명확하게 중점을 둘 수 있습니다. 몇 번의 구체화된 검색을 통해 문제와 관련된 데이터를 찾아 근본 원인을 파악할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ffe8-p114">When a problem occurs, start a second scenario that relates to the problem reported. Reproduce the problem, and stop the logging for the second scenario. Begin your log searches relative to the problem reported. The aggregated collection of logs produces a log file that contains trace messages from all computers in your site or global scope of your deployment. If the search returns more data than you can feasibly analyze (typically known as a signal-to-noise ratio, where the noise is too high), you run another search with narrower parameters. At this point, you can begin to notice patterns that show up and can help you get a clearer focus on the problem. Ultimately, after you perform a couple of refined searches you can find data that is relevant to the problem and figure out the root cause.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="7ffe8-162">Lync Server에서 문제가 발생 한 경우에는 "문제에 대해 이미 파악 한 것은 무엇 인가요?" 라는 메시지가 표시 되 면 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ffe8-162">When presented with a problem scenario in Lync Server, start by asking yourself “What do I already know about the problem?”</span></span> <span data-ttu-id="7ffe8-163">문제 경계를 정량화 하는 경우 Lync Server에서 작업 엔터티의 대규모 부분을 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ffe8-163">If you quantify the problem boundaries, you can eliminate a large part of the operational entities in Lync Server.</span></span><BR><span data-ttu-id="7ffe8-164">사용자가 연락처를 검색할 때 최신 결과를 얻지 못하며 여러분이 이 사실을 알고 있는 시나리오를 예로 들어 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="7ffe8-164">Consider an example scenario where you know that users are not getting current results when looking for a contact.</span></span> <span data-ttu-id="7ffe8-165">미디어 구성 요소, Enterprise Voice, 회의 및 기타 다양 한 구성 요소에서 발생 하는 문제를 찾는 지점은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7ffe8-165">There is no point in looking for problems in the media components, Enterprise Voice, conferencing, and a number of other components.</span></span> <span data-ttu-id="7ffe8-166">이 상황에서 모르는 사항은 문제가 실제로 발생한 위치(클라이언트 쪽 또는 서버 쪽)일 것입니다.</span><span class="sxs-lookup"><span data-stu-id="7ffe8-166">What you may not know is where the problem actually is: on the client, or is this a server-side problem?</span></span> <span data-ttu-id="7ffe8-167">연락처는 사용자 복제기에 의해 Active Directory에서 수집 되며 주소록 서버 (ABServer)를 통해 클라이언트로 배달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7ffe8-167">Contacts are collected from Active Directory by the User Replicator and delivered to the client by way of the Address Book Server (ABServer).</span></span> <span data-ttu-id="7ffe8-168">ABServer는 기본적으로 오전 1:30에 RTC 데이터베이스(여기에 User Replicator가 업데이트 기록)에서 업데이트를 가져와 주소록 파일에 수집합니다.</span><span class="sxs-lookup"><span data-stu-id="7ffe8-168">The ABServer gets its updates from the RTC database (where User Replicator wrote them) and collects them into address book files, by default – 1:30 AM.</span></span> <span data-ttu-id="7ffe8-169">Lync Server 클라이언트는 임의 일정에 따라 새 주소록을 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ffe8-169">The Lync Server clients retrieve the new address book on a randomized schedule.</span></span> <span data-ttu-id="7ffe8-170">프로세스가 작동 하는 방식을 알고 있으므로 사용자 복제기, ABServer가 주소록 파일을 검색 하 여 만들지 않는 등 Active Directory에서 수집한 데이터와 관련 된 문제를 검색 하는 것을 줄일 수 있습니다. 주소록 파일 다운로드</span><span class="sxs-lookup"><span data-stu-id="7ffe8-170">Because you know how the process works, you can reduce your search for the potential cause to an issue related to data being collected from Active Directory by the User Replicator, the ABServer not retrieving and creating the address book files, or the clients not downloading the address book file.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

