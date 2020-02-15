---
title: 'Lync Server 2013: 중앙 로깅 서비스에 대해 Stop 사용'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using Stop for the Centralized Logging Service
ms:assetid: 09ac093e-8f30-4874-84b4-12548ac8c898
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687964(v=OCS.15)
ms:contentKeyID: 49733549
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1273d961c52b2b02ff90c83dc8f677f57196f2bb
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007527"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-stop-for-the-centralized-logging-service-in-lync-server-2013"></a><span data-ttu-id="c87c6-102">Lync Server 2013에서 중앙화 된 로깅 서비스에 대해 Stop 사용</span><span class="sxs-lookup"><span data-stu-id="c87c6-102">Using Stop for the Centralized Logging Service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c87c6-103">_**마지막으로 수정 된 항목:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="c87c6-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="c87c6-104">Stop-CsClsLogging cmdlet을 사용하여 현재 실행 중인 로깅 세션을 중지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c87c6-104">You can stop a currently running logging session with the Stop-CsClsLogging cmdlet.</span></span> <span data-ttu-id="c87c6-105">일반적으로 로깅 세션을 중지해야 하는 상황은 많지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c87c6-105">Generally, there aren’t many situations in which you would need to stop a logging session.</span></span> <span data-ttu-id="c87c6-106">예를 들어 로깅을 먼저 중지하지 않고도 로그를 검색하고 구성을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c87c6-106">For example, you can search logs and change configurations without first needing to stop logging.</span></span> <span data-ttu-id="c87c6-107">두 시나리오(AlwaysOn 및 UserReplicator)를 실행 중인데 Authentication 관련 정보를 수집해야 하는 경우에는 전역, 사이트, 풀 또는 컴퓨터 범위에서 다른 시나리오 중 하나를 중지해야 Authentication 시나리오 실행을 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c87c6-107">If you have two scenarios running, for example AlwaysOn and UserReplicator, and you need to collect information related to Authentication, you will need to stop one of the other scenarios (at a global, site, pool or computer scope) before you can start running to Authentication scenario.</span></span> <span data-ttu-id="c87c6-108">자세한 내용은 [Stop-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/Stop-CsClsLogging)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="c87c6-108">For details, see [Stop-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/Stop-CsClsLogging).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c87c6-109">지정된 배포, 풀 또는 컴퓨터에서 실행할 수 있는 시나리오를 확인할 때는 <STRONG>컴퓨터당</STRONG> 두 개의 시나리오만 실행할 수 있음을 기억해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c87c6-109">When determining what scenarios you can run on a given deployment, pool or computer, you need to remember that you are limited to running two scenarios <STRONG>per computer</STRONG>.</span></span> <span data-ttu-id="c87c6-110">풀에서 활동을 로깅 중이라면 풀을 엔터티 하나로 간주해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c87c6-110">If you are logging activity on a pool, you should treat a pool as a single entity.</span></span> <span data-ttu-id="c87c6-111">대부분의 경우에는 풀의 각 컴퓨터에서 서로 다른 시나리오를 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c87c6-111">In most cases, it would not make sense to run different scenarios on each computer in a pool.</span></span> <span data-ttu-id="c87c6-112">데이터를 수집 중인 문제를 확인하여 전체 배포에서 지정된 컴퓨터에 가장 적합한 시나리오를 고려하는 것이 적절합니다.</span><span class="sxs-lookup"><span data-stu-id="c87c6-112">It does make sense to look at the problem that you are collecting data about and think about what scenario makes the most sense on a given computer in the overall deployment.</span></span> <span data-ttu-id="c87c6-113">예를 들어 UserReplicator 시나리오를 고려할 경우에는에 지 서버 또는에 지 풀에서 UserReplicator를 실행 하는 데 값이 거의 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c87c6-113">For example, if you consider the UserReplicator scenario, there would be very little value in running UserReplicator on an Edge Server or Edge pool.</span></span><BR><span data-ttu-id="c87c6-p103">문제와 영향의 범위를 파악한 후에는 각 컴퓨터와 풀에서 실행할 시나리오를 적절하게 선택해야 합니다. AlwaysOn 시나리오는 다양한 공급자에 대한 정보를 수집하므로 폭넓은 응용 프로그램에 적합하기는 하지만, 특정 시나리오는 특정 컴퓨터나 풀에서만 응용 프로그램과 관련하여 유용합니다. 또한 먼저 지정된 시나리오의 유용성을 파악하지 않고 로깅 세션을 임의로 시작할 때도 주의해야 합니다. 잘못된 시나리오를 사용하거나 작업에 적합한 시나리오를 사용하기는 하지만 잘못된 범위(전역/사이트/풀/컴퓨터)에서 시나리오를 적용하는 경우에는 시나리오를 전혀 실행하지 않은 것과 마찬가지로 부적절한 데이터가 제공될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c87c6-p103">After you understand the problem and the scope of the impact, you should make careful choices about what scenarios to run on which computers and pools. While the AlwaysOn scenario makes sense for a wide scope application because it collects information on a wide variety of providers, specific scenarios only have application value on specific computers or pools. Also, you should take caution when randomly starting up a logging session without first understanding the value of a given scenario. If you use the wrong scenario, or if you use a scenario that is appropriate for the task and you apply the scenario at the wrong scope (be it global, site, pool, or computer), you can get questionable data that is not very useful—as if you didn't run the scenario at all.</span></span>



</div>

<span data-ttu-id="c87c6-118">Lync Server 관리 셸을 사용 하 여 중앙화 된 로깅 서비스 기능을 제어 하려면 CsAdministrator 또는 CsServerAdministrator의 RBAC (역할 기반 액세스 제어) 보안 그룹 또는이를 포함 하는 사용자 지정 RBAC 역할의 구성원 이어야 합니다. 두 그룹 중 하나</span><span class="sxs-lookup"><span data-stu-id="c87c6-118">To control the Centralized Logging Service functions by using the Lync Server Management Shell, you must be a member of either the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> <span data-ttu-id="c87c6-119">직접 만든 사용자 지정 RBAC 역할을 포함 하 여이 cmdlet이 할당 된 모든 RBAC 역할의 목록을 반환 하려면 Lync Server 관리 셸 또는 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="c87c6-119">To return a list of all the RBAC roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Lync Server Management Shell or the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Lync Server 2013 cmdlet"}

<span data-ttu-id="c87c6-120">예:</span><span class="sxs-lookup"><span data-stu-id="c87c6-120">For example:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}

<div>

## <a name="to-stop-a-currently-running-centralized-logging-service-session"></a><span data-ttu-id="c87c6-121">현재 실행 중인 중앙 로깅 서비스 세션을 중지 하려면</span><span class="sxs-lookup"><span data-stu-id="c87c6-121">To stop a currently running Centralized Logging Service session</span></span>

1.  <span data-ttu-id="c87c6-122">**시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="c87c6-122">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="c87c6-123">중앙 로깅 서비스를 쿼리하여 다음을 입력 하 여 현재 실행 중인 시나리오를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="c87c6-123">Query the Centralized Logging Service to find out what scenarios are currently running by typing the following:</span></span>
    
        Show-CsClsLogging
    
    <span data-ttu-id="c87c6-124">![Show-CsCl을 호출한 후의 Windows PowerShell 콘솔](images/JJ687964.eb190c32-529c-4277-a731-52c47d22d8fa(OCS.15).jpg "Show-CsCl을 호출한 후의 Windows PowerShell 콘솔")</span><span class="sxs-lookup"><span data-stu-id="c87c6-124">![Windows PowerShell console after calling Show-CsCl](images/JJ687964.eb190c32-529c-4277-a731-52c47d22d8fa(OCS.15).jpg "Windows PowerShell console after calling Show-CsCl")</span></span>
    
    <span data-ttu-id="c87c6-125">Show-CsClsLogging의 결과는 실행 중인 시나리오 및 시나리오가 실행되는 범위의 요약입니다.</span><span class="sxs-lookup"><span data-stu-id="c87c6-125">The result of Show-CsClsLogging is a summary of the scenarios that are running and what scope they are running in.</span></span> <span data-ttu-id="c87c6-126">자세한 내용은 [Show-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/Show-CsClsLogging)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="c87c6-126">For details, see [Show-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/Show-CsClsLogging).</span></span>

3.  <span data-ttu-id="c87c6-127">특정 시나리오를 사용하여 현재 실행 중인 로깅 세션을 중지하려면 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="c87c6-127">To stop a currently running logging session with a specific scenario, type:</span></span>
    
        Stop-CsClsLogging -Scenario <scenario name> -Computers <comma separated list of fully qualified computer names> -Pools <comma separated list of fully qualified pool names>
    
    <span data-ttu-id="c87c6-128">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c87c6-128">For example:</span></span>
    
        Stop-CsClsLogging -Scenario UserReplicator -Pools pool01.contoso.net
    
    <span data-ttu-id="c87c6-129">이 명령은 pool01.contoso.net에서 UserReplicatior 시나리오를 사용한 로깅을 중지합니다.</span><span class="sxs-lookup"><span data-stu-id="c87c6-129">This command will stop logging with the UserReplicatior scenario on pool01.contoso.net.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c87c6-130">UserReplicator 시나리오를 사용하여 이 로깅 세션 중에 작성되는 로그는 삭제되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c87c6-130">Logs created during this logging session using the UserReplicator scenario are not deleted.</span></span> <span data-ttu-id="c87c6-131">Search-CsClsLogging 명령을 사용하면 로깅에 대해 검색을 계속 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c87c6-131">The logging is still available for you to execute searches against using the Search-CsClsLogging command.</span></span> <span data-ttu-id="c87c6-132">자세한 내용은 <A href="https://docs.microsoft.com/powershell/module/skype/Search-CsClsLogging">Search-CsClsLogging</A>을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="c87c6-132">For details, see <A href="https://docs.microsoft.com/powershell/module/skype/Search-CsClsLogging">Search-CsClsLogging</A>.</span></span>

    
    </div>

<span data-ttu-id="c87c6-p107">Start-CsClsLogging의 보조 명령으로 작동하는 Stop-CsClsLogging cmdlet은 시나리오에 의해 정의된 로깅 세션을 종료하고 로깅 세션에서 작성된 로그를 보관합니다. 지정된 컴퓨터에서 한 번에 두 개의 시나리오를 실행할 수 있습니다. 한 시나리오를 중지하고 다른 시나리오를 사용하여 정보를 수집하는 방법은 대부분의 작업 문제 해결 중에 수행할 수 있는 일반적인 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="c87c6-p107">Acting as the companion command to Start-CsClsLogging, the Stop-CsClsLogging cmdlet ends the logging session, defined by scenarios, and retains the logs created by the logging session. You can run two scenarios on a given computer at any time. The method of stopping one scenario to gather information using another scenario is a common task that you can perform during most workload troubleshooting.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c87c6-136">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c87c6-136">See Also</span></span>


[<span data-ttu-id="c87c6-137">중앙 로깅 서비스에 시작을 사용 하 여 Lync Server 2013에서 로그 캡처</span><span class="sxs-lookup"><span data-stu-id="c87c6-137">Using Start for the Centralized Logging Service to capture logs in Lync Server 2013</span></span>](lync-server-2013-using-start-for-the-centralized-logging-service-to-capture-logs.md)  


[<span data-ttu-id="c87c6-138">Lync Server 2013의 중앙 로깅 서비스 개요</span><span class="sxs-lookup"><span data-stu-id="c87c6-138">Overview of the Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-overview-of-the-centralized-logging-service.md)  


[<span data-ttu-id="c87c6-139">표시-CsClsLogging</span><span class="sxs-lookup"><span data-stu-id="c87c6-139">Show-CsClsLogging</span></span>](https://docs.microsoft.com/powershell/module/skype/Show-CsClsLogging)  
[<span data-ttu-id="c87c6-140">시작-CsClsLogging</span><span class="sxs-lookup"><span data-stu-id="c87c6-140">Start-CsClsLogging</span></span>](https://docs.microsoft.com/powershell/module/skype/Start-CsClsLogging)  
[<span data-ttu-id="c87c6-141">중지-CsClsLogging</span><span class="sxs-lookup"><span data-stu-id="c87c6-141">Stop-CsClsLogging</span></span>](https://docs.microsoft.com/powershell/module/skype/Stop-CsClsLogging)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

