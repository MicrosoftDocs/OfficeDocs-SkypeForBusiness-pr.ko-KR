---
title: 'Lync Server 2013: 이벤트 로그 확인'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Checking event logs
ms:assetid: 5500720d-c628-4dbd-84bc-a5becc39b99c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720914(v=OCS.15)
ms:contentKeyID: 63969602
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1506f94f0a049a6bb4fdd90875dae50548b5f516
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984736"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="checking-event-logs-in-lync-server-2013"></a><span data-ttu-id="aef6c-102">Lync Server 2013에서 이벤트 로그 검사</span><span class="sxs-lookup"><span data-stu-id="aef6c-102">Checking event logs in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="aef6c-103">_**마지막으로 수정한 주제:** 2014-08-06_</span><span class="sxs-lookup"><span data-stu-id="aef6c-103">_**Topic Last Modified:** 2014-08-06_</span></span>

<span data-ttu-id="aef6c-104">[Windows 이벤트 뷰어](http://go.microsoft.com/fwlink/p/?linkid=314067) 를 사용 하 여 이벤트 로그를 보고 서비스 오류, AD DS의 복제 오류, 가상 메모리 및 디스크 공간 같은 시스템 리소스에 대 한 경고에 대 한 정보를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aef6c-104">You can use [Windows Event Viewer](http://go.microsoft.com/fwlink/p/?linkid=314067) to view event logs and obtain information about service failures, replication errors in the AD DS, and warnings about system resources such as virtual memory and disk space.</span></span> <span data-ttu-id="aef6c-105">이벤트 뷰어는 Windows Server 2008 및 2012에 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aef6c-105">Event Viewer is included with Windows Server 2008 and 2012.</span></span>

<span data-ttu-id="aef6c-106">Lync Server 2013 로깅 도구에서 디버그 세션을 종료할 때 **로그 파일 분석** 을 클릭 하 여 Snooper 도구를 사용 하 여 로그 파일을 봅니다.</span><span class="sxs-lookup"><span data-stu-id="aef6c-106">In the Lync Server 2013 Logging Tool, when you end the debug session, click **Analyze Log Files** to view the log files by using the Snooper tool.</span></span>

<span data-ttu-id="aef6c-107">이벤트 뷰어는 컴퓨터의 응용 프로그램, 보안 및 시스템 이벤트에 대 한 로그를 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="aef6c-107">Event Viewer maintains logs about application, security, and system events on the computer.</span></span> <span data-ttu-id="aef6c-108">Lync Server 2013 및 Windows는 모두 경고 및 오류 조건을 이벤트 로그에 보고 합니다.</span><span class="sxs-lookup"><span data-stu-id="aef6c-108">Both Lync Server 2013 and Windows report warnings and error conditions to the event logs.</span></span> <span data-ttu-id="aef6c-109">따라서 매일 이벤트 로그를 검토 합니다.</span><span class="sxs-lookup"><span data-stu-id="aef6c-109">Therefore, review event logs daily.</span></span>

<span data-ttu-id="aef6c-110">이벤트 뷰어를 사용 하 여 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="aef6c-110">Use Event Viewer to:</span></span>

  - <span data-ttu-id="aef6c-111">이벤트 로그를 보고 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="aef6c-111">View and manage event logs.</span></span>

  - <span data-ttu-id="aef6c-112">해결 해야 하는 하드웨어, 소프트웨어 및 시스템 문제에 대 한 정보를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aef6c-112">Obtain information about hardware, software, and system issues that must be resolved.</span></span>

  - <span data-ttu-id="aef6c-113">이후 조치가 필요한 추세를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="aef6c-113">Identify trends that require future action.</span></span>

<span data-ttu-id="aef6c-114">Windows Server 운영 체제에서 Lync Server를 실행 하는 서버는 네 가지 유형의 로그에 이벤트를 기록 합니다.</span><span class="sxs-lookup"><span data-stu-id="aef6c-114">A server that is running Lync Server on a Windows Server operating system records events in four types of logs:</span></span>

  - <span data-ttu-id="aef6c-115">**응용**   프로그램 로그 응용 프로그램 로그에는 응용 프로그램 또는 프로그램에 의해 기록 된 이벤트가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="aef6c-115">**Application logs**   The Application log contains events logged by applications or programs.</span></span> <span data-ttu-id="aef6c-116">로깅할 이벤트는 개발자가 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="aef6c-116">Developers determine which events to log.</span></span> <span data-ttu-id="aef6c-117">예를 들어 데이터베이스 프로그램은 응용 프로그램 로그에 파일 오류를 기록할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="aef6c-117">For example, a database program might record a file error in the Application log.</span></span> <span data-ttu-id="aef6c-118">대부분의 Lync Server 2013 관련 이벤트는 응용 프로그램 로그에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="aef6c-118">Most Lync Server 2013-related events appear in the Application log.</span></span>

  - <span data-ttu-id="aef6c-119">**보안 로그**   보안 로그는 파일 또는 기타 개체 만들기, 열기, 삭제 등의 리소스 사용과 관련 된 이벤트 외에도 유효 하거나 유효 하지 않은 로그온 시도 등의 이벤트를 기록 합니다.</span><span class="sxs-lookup"><span data-stu-id="aef6c-119">**Security logs**   The Security log records events such as valid and not valid logon tries in addition to events related to resource use such as creating, opening, or deleting files or other objects.</span></span> <span data-ttu-id="aef6c-120">예를 들어 로그온 감사를 사용 하는 경우 시스템에 로그온 하려는 시도가 보안 로그에 기록 됩니다.</span><span class="sxs-lookup"><span data-stu-id="aef6c-120">For example, if logon auditing is enabled, attempts to log on to the system are recorded in the Security log.</span></span>

  - <span data-ttu-id="aef6c-121">**시스템 로그**   시스템 로그에는 Windows 시스템 구성 요소에 의해 기록 된 이벤트가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="aef6c-121">**System logs**   The System log contains events logged by Windows system components.</span></span> <span data-ttu-id="aef6c-122">예를 들어 시작 중에 로드 하는 드라이버 또는 기타 시스템 구성 요소의 오류는 시스템 로그에 기록 됩니다.</span><span class="sxs-lookup"><span data-stu-id="aef6c-122">For example, the failure of a driver or other system component to load during startup is recorded in the System log.</span></span> <span data-ttu-id="aef6c-123">시스템 구성 요소가 기록 하는 이벤트 유형은 서버에서 미리 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="aef6c-123">The event types logged by system components are predetermined by the server.</span></span>

  - <span data-ttu-id="aef6c-124">**Lync Server 2013**   로깅 도구는 인증, 연결, 사용자 작업과 관련 된 중요 한 이벤트를 기록 합니다.</span><span class="sxs-lookup"><span data-stu-id="aef6c-124">**Lync Server 2013**   The logging tool records significant events related to authentication, connections, and user actions.</span></span> <span data-ttu-id="aef6c-125">진단 로깅을 사용 하도록 설정한 후에는 이벤트 뷰어에서 로그 항목을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aef6c-125">After enabling diagnostic logging, you can view the log entries in Event Viewer.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="aef6c-126">Microsoft 고객 지원 서비스에서이 작업을 수행 해야 하는 경우를 제외 하 고는 최대 로깅 설정을 사용 하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="aef6c-126">We do not recommend that you use the maximum logging settings unless you are instructed to do this by Microsoft Customer Support Services.</span></span> <span data-ttu-id="aef6c-127">최대 로깅은 중요 한 리소스를 포기 하 고, 다 수의 "가양성", 즉 최대 로깅에서 기록 되지만 실제로 예상 되는 오류를 초래 하 고 문제의 원인이 되지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="aef6c-127">Maximum logging drains significant resources and can give many “false positives,” that is, errors that get logged only at maximum logging but are really expected and are not a cause of concern.</span></span> <span data-ttu-id="aef6c-128">또한 진단 로깅을 영구적으로 사용 하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="aef6c-128">We also recommend that you do not enable diagnostic logging permanently.</span></span> <span data-ttu-id="aef6c-129">문제를 해결할 때만 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="aef6c-129">Use it only when troubleshooting.</span></span>



</div>

<span data-ttu-id="aef6c-130">각 이벤트 뷰어 로그 내에서 Lync Server 2013는 정보, 경고 및 오류 이벤트를 기록 합니다.</span><span class="sxs-lookup"><span data-stu-id="aef6c-130">Within each Event Viewer log, Lync Server 2013 records informational, warning, and error events.</span></span> <span data-ttu-id="aef6c-131">이러한 로그를 면밀 하 게 모니터링 하 여 Lync Server 2013 서버에서 수행 되는 트랜잭션의 유형을 추적 합니다.</span><span class="sxs-lookup"><span data-stu-id="aef6c-131">Monitor these logs closely to track the types of transactions being conducted on the Lync Server 2013 servers.</span></span> <span data-ttu-id="aef6c-132">공간 부족을 방지 하려면 정기적으로 로그를 보관 하거나 자동 롤오버를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aef6c-132">You should periodically archive the logs or use automatic rollover to avoid running out of space.</span></span> <span data-ttu-id="aef6c-133">로그 파일은 일정 한 공간을 차지할 수 있으므로 로그 크기 (예: 50 MB)를 늘리고, Lync Server 2013 서버에서 새 이벤트를 계속 쓸 수 있도록이를 덮어쓰도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="aef6c-133">Because log files can occupy a finite amount of space, increase the log size (for example, to 50 MB) and set it to overwrite so that the Lync Server 2013 Server can continue to write new events.</span></span>

<span data-ttu-id="aef6c-134">다음 도구 및 기술을 사용 하 여 이벤트 로그 관리를 자동화할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aef6c-134">You can also automate event log administration by using the following tools and technologies:</span></span>

  - <span data-ttu-id="aef6c-135">System Center Operations Manager는 Lync Server 2013 서버의 상태와 사용을 모니터링 합니다.</span><span class="sxs-lookup"><span data-stu-id="aef6c-135">System Center Operations Manager monitors the health and use of Lync Server 2013 servers.</span></span> <span data-ttu-id="aef6c-136">Lync Server 2013 관리 팩 Operations Manager for Lync Server 2013를 실행 하는 서버에 대 한 특별 한 모니터링을 제공 하 여 Operations Manager를 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="aef6c-136">Lync Server 2013 Management Pack for Operations Manager extends Operations Manager by providing specialized monitoring for servers that are running Lync Server 2013.</span></span>

  - <span data-ttu-id="aef6c-137">Lync Server 2013의 Operations Manager 용 관리 팩에는 Lync Server 2013의 표준 및 엔터프라이즈 버전이 모니터링 됩니다.</span><span class="sxs-lookup"><span data-stu-id="aef6c-137">The Lync Server 2013 Management Pack for Operations Manager monitors Standard and Enterprise Edition of Lync Server 2013.</span></span> <span data-ttu-id="aef6c-138">또한이 릴리스에는 이전에 별도의 관리 팩을 설치한 체감 품질 (환경 품질) 관리 팩이 통합 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aef6c-138">This release also incorporates the Quality of Experience (QoE) Management Pack which was previously a separate management pack.</span></span>

<span data-ttu-id="aef6c-139">모니터링 되는 유형은 이벤트 로그 항목, 성능 카운터 및 체감 품질의 상태 모니터링입니다.</span><span class="sxs-lookup"><span data-stu-id="aef6c-139">Monitored types are event log entries, performance counters and stateful monitoring of QoE.</span></span> <span data-ttu-id="aef6c-140">이 버전의 관리 팩은 Lync Server 2013 및 2010만 모니터링 하며 Office Communications Server 2007을 모니터링 하는 데 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="aef6c-140">This version of the management pack only monitors Lync Server 2013 and 2010, and cannot be used to monitor Office Communications Server 2007.</span></span>

<span data-ttu-id="aef6c-141">관리 팩은 다음과 같은 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="aef6c-141">The management pack provides the following features:</span></span>

  - <span data-ttu-id="aef6c-142">서비스가 이벤트에 영향을 주는 경고</span><span class="sxs-lookup"><span data-stu-id="aef6c-142">Alerts indicating service affecting events</span></span>

  - <span data-ttu-id="aef6c-143">구성을 나타내는 경고 및 다른 비 서비스 문제에 영향을 주는 메시지</span><span class="sxs-lookup"><span data-stu-id="aef6c-143">Alerts indicating configuration, and other non-service impacting issues</span></span>

  - <span data-ttu-id="aef6c-144">Lync Server 서비스의 상태 모니터링</span><span class="sxs-lookup"><span data-stu-id="aef6c-144">State monitoring of Lync Server services</span></span>

  - <span data-ttu-id="aef6c-145">제품 정보: 확인 된 문제의 원인 및 해결</span><span class="sxs-lookup"><span data-stu-id="aef6c-145">Product knowledge: Cause and resolution of identified issues</span></span>

<span data-ttu-id="aef6c-146">Lync Server 2013 관리 팩에 대 한 자세한 내용은 [System Center Operations Manager를 사용 하 여 Lync server 2013 모니터링](lync-server-2013-monitoring-lync-server-with-system-center-operations-manager.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="aef6c-146">For more information about Lync Server 2013 Management Pack, refer to [Monitoring Lync Server 2013 with System Center Operations Manager](lync-server-2013-monitoring-lync-server-with-system-center-operations-manager.md).</span></span>

<span data-ttu-id="aef6c-147">**이벤트 빗질**   이벤트 빗질 도구는 여러 컴퓨터의 이벤트 로그에서 특정 이벤트를 하나의 중앙 위치로 수집 합니다.</span><span class="sxs-lookup"><span data-stu-id="aef6c-147">**Event Comb**   The Event Comb tool collects specific events from the event logs of several computers to one central location.</span></span> <span data-ttu-id="aef6c-148">이를 통해 이벤트 Id 또는 지정 된 이벤트 원본 에서만 보고할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aef6c-148">It lets you report on only the event IDs or event sources it specifies.</span></span> <span data-ttu-id="aef6c-149">이벤트 빗질에 대 한 자세한 내용은 [계정 잠금 및 관리 도구](http://go.microsoft.com/fwlink/?linkid=35607) 웹 사이트를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="aef6c-149">For more information about Event Comb, see the [Account Lockout and Management Tools](http://go.microsoft.com/fwlink/?linkid=35607) website.</span></span>

<span data-ttu-id="aef6c-150">\*\*\*\*   Windows Server 2012의 이벤트 트리거 관리자가 프로그램을 실행 하거나, 전자 메일 메시지를 보내거나, 화상 메시지를 표시할 수 있는 windows 이벤트 뷰어 내에서 "이 이벤트에 작업을 첨부할 수 있습니다."</span><span class="sxs-lookup"><span data-stu-id="aef6c-150">**Event triggers**   In Windows Server 2012 you can "Attach a Task to This Event" within the Windows Event Viewer—where an administrator can either run a program, send an email message or display an on-screen message.</span></span> <span data-ttu-id="aef6c-151">이 기능에 대 한 자세한 내용은 Windows Server 2008 R2 항목 지정 된 [이벤트에 대 한 응답으로 작업 실행](http://technet.microsoft.com/en-us/library/cc748900.aspx)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="aef6c-151">For more information about this feature, see the Windows Server 2008 R2 topic [Run a Task in Response to a Given Event](http://technet.microsoft.com/en-us/library/cc748900.aspx).</span></span> <span data-ttu-id="aef6c-152">' Eventtrigger '와 같은 명령줄 도구를 사용 하 여 이벤트 로그를 만들고 쿼리하고 기록 된 특정 이벤트와 프로그램을 연결할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aef6c-152">You can also use command-line tools such as ‘Eventtrigger.exe’ to create and query event logs and associate programs with particular logged events.</span></span> <span data-ttu-id="aef6c-153">Eventtriggers를 사용 하 여 특정 이벤트가 발생할 때 프로그램을 실행 하는 이벤트 트리거를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aef6c-153">By using Eventtriggers.exe, you can create event triggers that run programs when specific events occur.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="aef6c-154">참고 항목</span><span class="sxs-lookup"><span data-stu-id="aef6c-154">See Also</span></span>


[<span data-ttu-id="aef6c-155">Windows 이벤트 뷰어</span><span class="sxs-lookup"><span data-stu-id="aef6c-155">Windows Event Viewer</span></span>](http://go.microsoft.com/fwlink/p/?linkid=314067)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

