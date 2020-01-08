---
title: 'Lync Server 2013: 주별 작업'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Weekly tasks
ms:assetid: d564839b-b49d-4c5d-b67e-dc5abb0f6980
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn722432(v=OCS.15)
ms:contentKeyID: 63969650
ms.date: 08/20/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7d3128780c456c3f38f306d31f258ce903eb50a5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981512"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="weekly-tasks-in-lync-server-2013"></a><span data-ttu-id="df2b1-102">Lync Server 2013의 주별 작업</span><span class="sxs-lookup"><span data-stu-id="df2b1-102">Weekly tasks in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="df2b1-103">_**마지막으로 수정한 주제:** 2015-08-17_</span><span class="sxs-lookup"><span data-stu-id="df2b1-103">_**Topic Last Modified:** 2015-08-17_</span></span>

<span data-ttu-id="df2b1-104">주간 작업은 일반적으로 로그 및 보고서를 수집 하 고 분석 하는 것과 관련이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df2b1-104">Weekly tasks are generally related to collecting and analyzing logs and reports.</span></span>

<div>

## <a name="archive-event-logs"></a><span data-ttu-id="df2b1-105">이벤트 로그 보관</span><span class="sxs-lookup"><span data-stu-id="df2b1-105">Archive event logs</span></span>

<span data-ttu-id="df2b1-106">이벤트 로그가 필요에 따라 이벤트를 덮어쓰도록 구성 되어 있지 않으면 정기적으로 보관 하 고 삭제 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="df2b1-106">If event logs are not configured to overwrite events as required, they must be regularly archived and deleted.</span></span> <span data-ttu-id="df2b1-107">이 작업은 보안 로그를 시도 하는 경우에 특히 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="df2b1-107">This action is especially important for security logs, which may be required when investigating attempted security breaches.</span></span>

<span data-ttu-id="df2b1-108">조직에서 로그 보관에 대 한 정책 및 절차를 정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="df2b1-108">Your organization will have to define policies and procedures for log archiving.</span></span>

</div>

<div>

## <a name="create-reports"></a><span data-ttu-id="df2b1-109">보고서 만들기</span><span class="sxs-lookup"><span data-stu-id="df2b1-109">Create reports</span></span>

<span data-ttu-id="df2b1-110">용량 계획, SLA 검토 및 성능 분석에 도움이 되는 상태 보고서를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="df2b1-110">Create status reports to help with capacity planning, SLA reviews, and performance analysis.</span></span> <span data-ttu-id="df2b1-111">이벤트 로그 및 시스템 모니터의 일일 데이터를 사용 하 여 디스크, 메모리 및 CPU 사용량에 대 한 보고서를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="df2b1-111">Use daily data from event log and System Monitor to create reports on disk, memory, and CPU usage.</span></span> <span data-ttu-id="df2b1-112">System Center Operations Manager를 사용 하 여 가동 시간 및 사용 가능성 보고서를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="df2b1-112">Use System Center Operations Manager to generate uptime and availability reports.</span></span>

<span data-ttu-id="df2b1-113">조직에서 상태 보고서에 대 한 정책 및 절차를 정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="df2b1-113">Your organization will have to define policies and procedures for status reports.</span></span>

</div>

<div>

## <a name="incident-reports"></a><span data-ttu-id="df2b1-114">사고 보고서</span><span class="sxs-lookup"><span data-stu-id="df2b1-114">Incident reports</span></span>

<span data-ttu-id="df2b1-115">Lync Server와 관련 된 조직의 사고 보고서에 대 한 주간 감사를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="df2b1-115">Perform a weekly audit of your organization’s incident reports that relate to Lync Server.</span></span> <span data-ttu-id="df2b1-116">이 감사에는 다음이 포함 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="df2b1-116">This audit should include the following:</span></span>

  - <span data-ttu-id="df2b1-117">맨 위의 생성, 해결 됨 및 보류 중인 인시던트</span><span class="sxs-lookup"><span data-stu-id="df2b1-117">The top generated, resolved, and pending incidents.</span></span>

  - <span data-ttu-id="df2b1-118">해결 되지 않은 사건에 대 한 해결 방법</span><span class="sxs-lookup"><span data-stu-id="df2b1-118">Solutions for unresolved incidents.</span></span>

  - <span data-ttu-id="df2b1-119">새 문제점 티켓을 포함 하도록 보고서 업데이트</span><span class="sxs-lookup"><span data-stu-id="df2b1-119">Updating reports to include new trouble tickets.</span></span>

  - <span data-ttu-id="df2b1-120">문서 리포지토리를 업데이트 하 여 가이드 문제를 해결 하 고 중단에 대 한 평가를 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="df2b1-120">Updating a document repository for troubleshooting guides and post mortems about outages.</span></span>

<span data-ttu-id="df2b1-121">조직의 인시던트 추적 시스템은 Lync Server와는 별도로 선택 되어 있으므로 특정 지침이 나 포인터를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="df2b1-121">Since your organization’s incident tracking system is a choice independent of Lync Server, specific instructions or pointers are not available.</span></span> <span data-ttu-id="df2b1-122">조직에서 선택한 시스템에 대 한 설명서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="df2b1-122">Consult the documentation for the system your organization chose.</span></span>

</div>

<div>

## <a name="check-iis-logs-and-performance"></a><span data-ttu-id="df2b1-123">IIS 로그 및 성능 확인</span><span class="sxs-lookup"><span data-stu-id="df2b1-123">Check IIS logs and performance</span></span>

<span data-ttu-id="df2b1-124">IIS (인터넷 정보 서비스) 로그 및 성능에 대 한 주간 검토를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="df2b1-124">Perform a weekly review of Internet Information Services (IIS) logs and performance.</span></span> <span data-ttu-id="df2b1-125">IIS 로그 및 성능을 모니터링 하는 방법에 대 한 자세한 내용은 [Windows Server 2003 IIS (인터넷 정보 서비스) 이벤트 로깅 개요](http://go.microsoft.com/fwlink/?linkid=36077)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="df2b1-125">For more information about how to monitor IIS logs and performance, see [Windows Server 2003 Internet Information Services (IIS) Event Logging Overview](http://go.microsoft.com/fwlink/?linkid=36077).</span></span> <span data-ttu-id="df2b1-126">검토에는 다음이 포함 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="df2b1-126">The review should include the following:</span></span>

  - <span data-ttu-id="df2b1-127">WWW 서비스 캐시를 모니터링 하는 웹 서비스 캐시 카운터입니다.</span><span class="sxs-lookup"><span data-stu-id="df2b1-127">Web Service Cache counters to monitor the WWW service cache.</span></span>

  - <span data-ttu-id="df2b1-128">Asp로 실행 되는 응용 프로그램을 모니터링 하기 위한 Asp (Active Server Pages) 카운터</span><span class="sxs-lookup"><span data-stu-id="df2b1-128">Active Server Pages (ASPs) counters to monitor applications that run as ASPs.</span></span>

</div>

<div>

## <a name="generate-database-reports"></a><span data-ttu-id="df2b1-129">데이터베이스 보고서 생성</span><span class="sxs-lookup"><span data-stu-id="df2b1-129">Generate database reports</span></span>

<span data-ttu-id="df2b1-130">**SQL 데이터베이스에 대 한 보고서를 생성 하려면**</span><span class="sxs-lookup"><span data-stu-id="df2b1-130">**To generate reports on the SQL Database**</span></span>

1.  <span data-ttu-id="df2b1-131">Lync Server 2013을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="df2b1-131">Open Lync Server 2013.</span></span>

2.  <span data-ttu-id="df2b1-132">콘솔 트리에서 포리스트 노드를 확장 하 고 **엔터프라이즈 풀**을 확장 한 다음 데이터베이스 보고서를 생성 하려는 풀을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="df2b1-132">In the console tree, expand the forest node, expand **Enterprise pools**, and then click the pool for which you want to generate a database report.</span></span>

3.  <span data-ttu-id="df2b1-133">세부 정보 창에서 **데이터베이스** 탭을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="df2b1-133">In the details pane, click the **Database** tab.</span></span>

4.  <span data-ttu-id="df2b1-134">**데이터베이스** 탭에서 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="df2b1-134">On the **Database** tab, do the following:</span></span>
    
    1.  <span data-ttu-id="df2b1-135">데이터베이스의 이름을 보려면 **일반 설정**을 확장 하 고 데이터베이스 이름을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="df2b1-135">To view the name of the database, expand **General Settings**, and view the database name.</span></span>
    
    2.  <span data-ttu-id="df2b1-136">풀에 대 한 현재 사용자 요약 통계를 검색 하려면 **사용자 요약 보고서**를 확장 하 고 **이동을**클릭 한 다음 결과를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="df2b1-136">To retrieve current user summary statistics for the pool, expand **User Summary Reports**, click **Go**, and view the results.</span></span>
    
    3.  <span data-ttu-id="df2b1-137">풀의 단일 사용자에 대 한 현재 사용자별 데이터를 검색 하려면 **사용자 단위 보고서**를 확장 하 고 사용자의 SIP URI를 입력 한 다음 **이동을**클릭 하 고 결과를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="df2b1-137">To retrieve current per-user data for a single user of the pool, expand **Per-User Reports**, type the user’s SIP URI, click **Go**, and view the results.</span></span>

<span data-ttu-id="df2b1-138">풀에 대 한 현재 회의 요약 통계를 검색 하려면 **회의 요약 보고서**를 확장 하 고 **이동을**클릭 한 다음 결과를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="df2b1-138">To retrieve current conference summary statistics for the pool, expand **Conference Summary Reports**, click **Go**, and view the results.</span></span>

</div>

<div>

## <a name="check-for-security-and-lync-server-updates"></a><span data-ttu-id="df2b1-139">보안 및 Lync Server 업데이트 확인</span><span class="sxs-lookup"><span data-stu-id="df2b1-139">Check for security and Lync Server updates</span></span>

<span data-ttu-id="df2b1-140">새로운 서비스 팩, 핫픽스 또는 업데이트를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="df2b1-140">Identify any new service packs, hotfixes, or updates.</span></span> <span data-ttu-id="df2b1-141">적절 한 경우 테스트 랩에서 테스트 실습을 진행 하 고 변경 제어 절차를 사용 하 여 배포를 프로덕션 서버로 정렬 합니다.</span><span class="sxs-lookup"><span data-stu-id="df2b1-141">If appropriate, test these in a test lab, and use the change control procedures to arrange for deployment to the production servers.</span></span> <span data-ttu-id="df2b1-142">또한 이제 Windows 업데이트의 일부로 Lync 서버 구성 요소 업데이트를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df2b1-142">Also, Lync Server component updates are now available as part of Windows update.</span></span> <span data-ttu-id="df2b1-143">모든 Lync Server 구성 요소 업데이트는 해당 업데이트가 적용 되는 Lync Server를 실행 하는 모든 서버에서 동시에 업데이트 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="df2b1-143">All Lync Server component updates must be updated at the same time on all of the servers that are running Lync Server for which the updates are applicable.</span></span>

</div>

<div>

## <a name="run-the-lync-server-2013-best-practice-analyzer"></a><span data-ttu-id="df2b1-144">Lync Server 2013 모범 사례 분석기 실행</span><span class="sxs-lookup"><span data-stu-id="df2b1-144">Run the Lync Server 2013 Best Practice Analyzer</span></span>

<span data-ttu-id="df2b1-145">Lync Server 2013 모범 사례 분석기 도구는 구성 정보를 수집 하 고 구성이 Microsoft 모범 사례에 따라 설정 되었는지 여부를 확인 하는 진단 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="df2b1-145">The Lync Server 2013 Best Practices Analyzer Tool is a diagnostic tool that collects configuration information and determines whether the configuration is set according to Microsoft best practices.</span></span> <span data-ttu-id="df2b1-146">이 도구에 대 한 설명서는 [Lync Server 2013 모범 사례 분석기](lync-server-2013-lync-server-best-practices-analyzer.md)에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df2b1-146">Documentation for this tool is at [Lync Server 2013 Best Practices Analyzer](lync-server-2013-lync-server-best-practices-analyzer.md).</span></span>

<span data-ttu-id="df2b1-147">이 도구는 배포의 구성 데이터를 Lync Server의 미리 정의 된 규칙 집합과 비교 하 고 잠재적인 문제를 보고 합니다.</span><span class="sxs-lookup"><span data-stu-id="df2b1-147">The tool compares your deployment’s configuration data against a set of pre-defined rules for Lync Server, and reports potential issues.</span></span> <span data-ttu-id="df2b1-148">보고 된 모든 문제에 대해이 도구는 Lync Server 환경의 현재 구성과 권장 구성을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="df2b1-148">For every issue reported, the tool provides the current configuration in the Lync Server environment, and the recommended configuration.</span></span>

<span data-ttu-id="df2b1-149">올바른 네트워크 액세스를 사용 하면 도구는 Lync Server 2013을 실행 하는 AD DS 및 서버를 검사 하 여 다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df2b1-149">With the correct network access, the tool can examine your AD DS and servers that are running Lync Server 2013 to do the following:</span></span>

  - <span data-ttu-id="df2b1-150">권장 하는 모범 사례에 따라 구성이 설정 되어 있는지 확인 하는 상태 검사를 사전 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="df2b1-150">Proactively perform health checks, verifying that the configuration is set according to recommended best practices</span></span>

  - <span data-ttu-id="df2b1-151">최적이 아닌 구성 설정이 나 지원 되지 않거나 권장 하지 않는 옵션 등의 문제 목록 생성</span><span class="sxs-lookup"><span data-stu-id="df2b1-151">Generate a list of issues, such as suboptimal configuration settings or unsupported or not recommended options</span></span>

  - <span data-ttu-id="df2b1-152">시스템의 일반 상태 판단</span><span class="sxs-lookup"><span data-stu-id="df2b1-152">Judge the general health of a system</span></span>

  - <span data-ttu-id="df2b1-153">특정 문제 해결 도움말</span><span class="sxs-lookup"><span data-stu-id="df2b1-153">Help troubleshoot specific issues</span></span>

  - <span data-ttu-id="df2b1-154">사용할 수 있는 경우 업데이트를 다운로드 하 라는 메시지 표시</span><span class="sxs-lookup"><span data-stu-id="df2b1-154">Prompt you to download updates if they are available</span></span>

  - <span data-ttu-id="df2b1-155">보고 된 문제에 대 한 온라인 및 로컬 설명서를 제공 하 고 문제 해결 팁을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="df2b1-155">Provide online and local documentation about reported issues, and include troubleshooting tips</span></span>

  - <span data-ttu-id="df2b1-156">나중에 검토를 위해 캡처할 수 있는 구성 정보를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="df2b1-156">Generate configuration information that can be captured for later review</span></span>

<span data-ttu-id="df2b1-157">모든 Lync Server 2013 서버에 RTCBPA가 설치 되어 있는지 확인 하 고 주간 상태 검사 보고서를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="df2b1-157">Ensure that the RTCBPA.msi is installed on all Lync Server 2013 servers, and generate a weekly Health Check Report.</span></span> <span data-ttu-id="df2b1-158">필요한 경우 결과를 확인 하 고 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="df2b1-158">Note the results and correct, if necessary.</span></span>

</div>

<div>

## <a name="review-sla-performance-figures"></a><span data-ttu-id="df2b1-159">SLA 성과 수치 검토</span><span class="sxs-lookup"><span data-stu-id="df2b1-159">Review SLA performance figures</span></span>

<span data-ttu-id="df2b1-160">지난 주에 대 한 주요 성과 데이터를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="df2b1-160">Check the key performance data for the previous week.</span></span> <span data-ttu-id="df2b1-161">SLA 요구 사항에 대 한 성과를 검토 합니다.</span><span class="sxs-lookup"><span data-stu-id="df2b1-161">Review performance against the requirements of the SLA.</span></span> <span data-ttu-id="df2b1-162">대상에 도달 하지 않은 추세와 항목을 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="df2b1-162">Identify trends and items that have not met their targets.</span></span>

</div>

<div>

## <a name="review-system-center-operations-manager-management-pack-and-quality-of-experience-reports"></a><span data-ttu-id="df2b1-163">System Center Operations Manager 관리 팩 및 경력 보고서 검토</span><span class="sxs-lookup"><span data-stu-id="df2b1-163">Review System Center Operations Manager Management Pack and quality of experience reports</span></span>

<span data-ttu-id="df2b1-164">Lync Server 2013 관리 팩 및 경력 보고서의 품질을 확인 하 고 검토 합니다.</span><span class="sxs-lookup"><span data-stu-id="df2b1-164">Obtain and review Lync Server 2013 Management Pack and Quality of Experience reports.</span></span>

</div>

<div>

## <a name="generating-and-viewing-database-reports-for-enterprise-pools"></a><span data-ttu-id="df2b1-165">Enterprise 풀에 대 한 데이터베이스 보고서 생성 및 보기</span><span class="sxs-lookup"><span data-stu-id="df2b1-165">Generating and viewing database reports for enterprise pools</span></span>

<span data-ttu-id="df2b1-166">**풀 보고서를 생성 하려면**</span><span class="sxs-lookup"><span data-stu-id="df2b1-166">**To generate pool reports**</span></span>

1.  <span data-ttu-id="df2b1-167">Lync Server 2013을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="df2b1-167">Open Lync Server 2013.</span></span>

2.  <span data-ttu-id="df2b1-168">콘솔 트리에서 포리스트 노드를 확장 하 고 **엔터프라이즈 풀**을 확장 한 다음 데이터베이스 보고서를 생성 하려는 풀을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="df2b1-168">In the console tree, expand the forest node, expand **Enterprise pools**, and then click the pool for which you want to generate a database report.</span></span>

3.  <span data-ttu-id="df2b1-169">세부 정보 창에서 **데이터베이스** 탭을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="df2b1-169">In the details pane, click the **Database** tab.</span></span>

4.  <span data-ttu-id="df2b1-170">**데이터베이스** 탭에서 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="df2b1-170">On the **Database** tab, do the following:</span></span>
    
    1.  <span data-ttu-id="df2b1-171">데이터베이스의 이름을 보려면 **일반 설정**을 확장 하 고 데이터베이스 이름을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="df2b1-171">To view the name of the database, expand **General Settings**, and view the database name.</span></span>
    
    2.  <span data-ttu-id="df2b1-172">풀에 대 한 현재 사용자 요약 통계를 검색 하려면 **사용자 요약 보고서**를 확장 하 고 **이동을**클릭 한 다음 결과를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="df2b1-172">To retrieve current user summary statistics for the pool, expand **User Summary Reports**, click **Go**, and view the results.</span></span>
    
    3.  <span data-ttu-id="df2b1-173">풀의 단일 사용자에 대 한 현재 사용자별 데이터를 검색 하려면 **사용자 단위 보고서**를 확장 하 고 사용자의 SIP URI를 입력 한 다음 **이동을**클릭 하 고 결과를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="df2b1-173">To retrieve current per-user data for a single user of the pool, expand **Per-User Reports**, type the user’s SIP URI, click **Go**, and view the results.</span></span>

<span data-ttu-id="df2b1-174">풀에 대 한 현재 회의 요약 통계를 검색 하려면 **회의 요약 보고서**를 확장 하 고 **이동을**클릭 한 다음 결과를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="df2b1-174">To retrieve current conference summary statistics for the pool, expand **Conference Summary Reports**, click **Go**, and view the results.</span></span>

<span data-ttu-id="df2b1-175">관리자는 각 엔터프라이즈 풀에 대해 **데이터베이스 탭을** 사용 하 여 데이터베이스 이름을 확인 하 고 데이터베이스에서 보고서를 검색 하 고 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df2b1-175">For each Enterprise Pool, administrators can use the **Database** tab to view the database name and retrieve and view reports from the database.</span></span>

### <a name="database-reports-and-descriptions"></a><span data-ttu-id="df2b1-176">데이터베이스 보고서 및 설명</span><span class="sxs-lookup"><span data-stu-id="df2b1-176">Database Reports and Descriptions</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="df2b1-177">여기</span><span class="sxs-lookup"><span data-stu-id="df2b1-177">Section</span></span></th>
<th><span data-ttu-id="df2b1-178">설명</span><span class="sxs-lookup"><span data-stu-id="df2b1-178">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="df2b1-179">사용자 요약 보고서</span><span class="sxs-lookup"><span data-stu-id="df2b1-179">User Summary Reports</span></span></p></td>
<td><p><span data-ttu-id="df2b1-180">Dbanalyze/v/report: diag [/csqlserver: value]</span><span class="sxs-lookup"><span data-stu-id="df2b1-180">Dbanalyze /v /report:diag [/sqlserver:value]</span></span></p>
<p><span data-ttu-id="df2b1-181">이 섹션에는 사용 가능한 사용자 수, 사용자 당 평균 대화 상대 수, 특정 기능에 대 한 사용자 수 등과 같은 풀의 사용자에 대 한 집계 정보가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="df2b1-181">This section displays aggregate information about users in a pool, such as the number of enabled users, the average number of contacts per user, and the number of users for specific features.</span></span></p>
<p><span data-ttu-id="df2b1-182">이러한 보고서를 사용할 때 다음과 같은 정보가 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df2b1-182">When using these reports, the following information may be helpful:</span></span></p>
<ul>
<li><p><span data-ttu-id="df2b1-183">활성화 된 사용자는 Active Directory 사용자 및 컴퓨터 스냅인을 사용 하 여 Lync Server 2013을 사용 하도록 설정 된 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="df2b1-183">An enabled user is a user who is enabled for Lync Server 2013 by using the Active Directory Users and Computers Snap-in.</span></span></p></li>
<li><p><span data-ttu-id="df2b1-184">활성 사용자는 로그온 하거나 등록 한 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="df2b1-184">An active user is a user who has logged on or registered.</span></span></p></li>
<li><p><span data-ttu-id="df2b1-185">요약 보고서에는 연락처에 대 한 통계 정보 집합도 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="df2b1-185">The summary reports also offer a set of statistical information about contacts.</span></span> <span data-ttu-id="df2b1-186">이러한 통계는 적어도 한 번 이상 로그인 한 사용자와 하나 이상의 대화 상대에 대해서만 유효 합니다.</span><span class="sxs-lookup"><span data-stu-id="df2b1-186">These statistics are only valid for the population of users who have logged on at least one time, and who have at least one contact.</span></span> <span data-ttu-id="df2b1-187">따라서 일반적으로 최소한 0 개의 대화 상대 수가 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="df2b1-187">Consequently, you'll typically not see a minimum number of contacts of 0.</span></span> <span data-ttu-id="df2b1-188">이 동작 때문에 사용자에 게 연락처가 없고 (현재 사용자가 등록 한 경우)에는 다음이 표시 될 수 있습니다. &lt;일부 통계&gt; 필드가 비어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df2b1-188">Because of this behavior, if a user has no contacts (but is active, in that the user has registered), you may see: &lt;empty&gt; for some statistics fields.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="df2b1-189">사용자 단위 보고서</span><span class="sxs-lookup"><span data-stu-id="df2b1-189">Per-User Reports</span></span></p></td>
<td><p><span data-ttu-id="df2b1-190">Dbanalyze/v/report: disk [/resqlserver: value]</span><span class="sxs-lookup"><span data-stu-id="df2b1-190">Dbanalyze /v /report:disk [/sqlserver:value]</span></span></p>
<p><span data-ttu-id="df2b1-191">사용자 집단에 대해 계산 되는 요약 보고서와 달리,이는 특정 사용자에 대 한 보고서입니다.</span><span class="sxs-lookup"><span data-stu-id="df2b1-191">Unlike the summary reports, which are calculated over a user population, these are reports about a specific user.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="df2b1-192">회의 요약 보고서</span><span class="sxs-lookup"><span data-stu-id="df2b1-192">Conference Summary Reports</span></span></p></td>
<td><p><span data-ttu-id="df2b1-193">Dbanalyze/v/report: 회의 [/csqlserver: value]</span><span class="sxs-lookup"><span data-stu-id="df2b1-193">Dbanalyze /v /report:conf [/sqlserver:value]</span></span></p>
<p><span data-ttu-id="df2b1-194">이 섹션에는 활성 회의 수 및 총 참가자 수 등의 풀에 대 한 전화 회의 요약 통계에 대 한 집계 정보가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="df2b1-194">This section displays aggregate information about conference summary statistics for the pool, such as the number of active conferences and total number of participants.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="running-bandwidth-utilization-analyzer"></a><span data-ttu-id="df2b1-195">실행 중인 대역폭 이용률 분석기</span><span class="sxs-lookup"><span data-stu-id="df2b1-195">Running Bandwidth Utilization Analyzer</span></span>

<span data-ttu-id="df2b1-196">대역폭 사용률 분석기는 엔터프라이즈 네트워크의 WAN 링크 간에 UC 끝점을 사용 하 여 다양 한 대역폭 사용량 보기에 대 한 보고서를 만드는 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="df2b1-196">Bandwidth Utilization Analyzer is a tool that creates reports about various views of bandwidth consumption by the UC endpoints across WAN links in the enterprise network.</span></span> <span data-ttu-id="df2b1-197">이러한 보고서를 사용 하 여 현재 대역폭 소비 패턴을 이해 하 고 대역폭 용량 계획에 도움을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df2b1-197">These reports can be used to understand the current bandwidth consumption pattern and to help with bandwidth capacity planning.</span></span> <span data-ttu-id="df2b1-198">또한 다양 한 링크에 할당 된 대역폭 용량을 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="df2b1-198">It also iterates on the bandwidth capacity that is assigned to various links.</span></span>

<span data-ttu-id="df2b1-199">이 도구는 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="df2b1-199">This tool does the following:</span></span>

  - <span data-ttu-id="df2b1-200">네트워크를 통해 오디오 사용량에 대 한 특정 보고서를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="df2b1-200">Generates specific reports for audio usage over the network</span></span>

  - <span data-ttu-id="df2b1-201">다양 한 링크에 할당 된 대역폭 용량에 대 한 보다 효과적인 용량 계획 및 반복을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="df2b1-201">Helps with more effective capacity planning and iteration on the bandwidth capacity that is assigned to various links</span></span>

<span data-ttu-id="df2b1-202">대역폭 사용률 분석기는 대역폭 용량 및 사용 현황 보고서의 그래픽 플롯을 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df2b1-202">Bandwidth Utilization Analyzer can generate graphical plots of bandwidth capacity and usage reports.</span></span> <span data-ttu-id="df2b1-203">이러한 작업은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="df2b1-203">They are as follows:</span></span>

  - <span data-ttu-id="df2b1-204">엔터프라이즈 네트워크의 모든 WAN 링크</span><span class="sxs-lookup"><span data-stu-id="df2b1-204">All the WAN links in the enterprise network</span></span>

  - <span data-ttu-id="df2b1-205">선택한 WAN 링크로 필터링 됨</span><span class="sxs-lookup"><span data-stu-id="df2b1-205">Filtered by selected WAN links that were chosen</span></span>

  - <span data-ttu-id="df2b1-206">링크 용량을 초과한 WAN 링크로 필터링 됨</span><span class="sxs-lookup"><span data-stu-id="df2b1-206">Filtered by WAN links that have exceeded link capacity</span></span>

  - <span data-ttu-id="df2b1-207">프로 비전 된 대역폭을 사용 중이 던 WAN 링크로 필터링 됨</span><span class="sxs-lookup"><span data-stu-id="df2b1-207">Filtered by WAN links that were under-using the provisioned bandwidth</span></span>

  - <span data-ttu-id="df2b1-208">중요 한 수준에 도달한 WAN 링크를 기준으로 필터링 (WAN 링크의 대역폭 용량의 90% 보다 큰 대역폭 사용)</span><span class="sxs-lookup"><span data-stu-id="df2b1-208">Filter by WAN links that were reaching critical levels (a bandwidth usage that is greater than 90 percent of bandwidth capacity of the WAN link)</span></span>

  - <span data-ttu-id="df2b1-209">WAN 링크 유형 (네트워크 사이트 링크, 상호 지역 링크, 사이트 내부의 링크)을 기준으로 필터링</span><span class="sxs-lookup"><span data-stu-id="df2b1-209">Filtered by WAN link type—network-site links, interregional links, and links inside a site</span></span>

  - <span data-ttu-id="df2b1-210">네트워크 지역별로 필터링 됨</span><span class="sxs-lookup"><span data-stu-id="df2b1-210">Filtered by network region</span></span>

<span data-ttu-id="df2b1-211">이 도구에 대 한 설명서는 [Lync Server 2013 리소스 키트 도구 문서](http://go.microsoft.com/fwlink/?linkid=623245)에서 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df2b1-211">Documentation for this tool is available at [Lync Server 2013 Resource Kit Tools Documentation](http://go.microsoft.com/fwlink/?linkid=623245).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="df2b1-212">참고 항목</span><span class="sxs-lookup"><span data-stu-id="df2b1-212">See Also</span></span>


[<span data-ttu-id="df2b1-213">주간 작업 검사 목록</span><span class="sxs-lookup"><span data-stu-id="df2b1-213">Weekly task checklist</span></span>](lync-server-2013-operations-checklists.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

