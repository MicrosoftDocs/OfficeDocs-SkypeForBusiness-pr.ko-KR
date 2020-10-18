---
title: 중앙 로깅 서비스에 대해 시작을 사용 하 여 로그 캡처
description: 중앙 로깅 서비스에 대해 시작을 사용 하 여 로그를 캡처합니다.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using Start for the Centralized Logging Service to capture logs
ms:assetid: 0512b9ce-7f5b-48eb-a79e-f3498bacf2de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687958(v=OCS.15)
ms:contentKeyID: 49733543
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6321af0b12f3650d3b741e65968849332b53af45
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48580224"
---
# <a name="using-start-for-the-centralized-logging-service-to-capture-logs-in-lync-server-2013"></a><span data-ttu-id="e019a-103">중앙 로깅 서비스에 시작을 사용 하 여 Lync Server 2013에서 로그 캡처</span><span class="sxs-lookup"><span data-stu-id="e019a-103">Using Start for the Centralized Logging Service to capture logs in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e019a-104">_**마지막으로 수정 된 항목:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="e019a-104">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="e019a-105">중앙 로깅 서비스를 사용 하 여 추적 로그를 캡처하려면 하나 이상의 컴퓨터 및 풀에 대 한 로깅을 시작 하는 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e019a-105">To capture trace logs using the Centralized Logging Service, you issue a command to begin logging on one or more computers and pools.</span></span> <span data-ttu-id="e019a-106">또한 실행 해야 하는 컴퓨터 또는 풀, 실행할 시나리오 (예: AlwaysOn, 다른 미리 정의 된 시나리오, 사용자가 만든 시나리오), 추적에 사용할 Lync Server 구성 요소 (예: S4, 동안의 sipstack)를 정의 하는 매개 변수도 발급 합니다.</span><span class="sxs-lookup"><span data-stu-id="e019a-106">You also issue parameters that define which computers or pools, what scenarios to run (for example, AlwaysOn, another predefined scenario, or a scenario you have created), what Lync Server components (for example, S4, SipStack) to trace.</span></span>

<span data-ttu-id="e019a-107">적절한 정보를 캡처하려면 올바른 시나리오를 사용하여 문제와 관련된 정보를 수집해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e019a-107">To capture the right information, you need to make sure you use the right scenario to collect information that is relevant to the problem.</span></span> <span data-ttu-id="e019a-108">중앙 로깅 서비스에서 시나리오는 서버 구성 요소, 로깅 수준 및 플래그 모음을 기반으로 하 여 로깅을 설정 하는 개념 이며, 서버 단위로 이러한 요소를 정의 하는 것 보다 훨씬 더 효율적이 고 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e019a-108">In the Centralized Logging Service, a scenario is the concept of turning logging on based on a collection of server components, logging levels, and flags, which is much more efficient and useful than having to define these elements on a per-server basis.</span></span> <span data-ttu-id="e019a-109">시나리오를 정의 및 지정하면 인프라 범위 내의 모든 서버 및 풀에서 시나리오가 일관성 있게 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="e019a-109">You define and specify a scenario to run and the scenario is run consistently across all servers and pools in the scope of the infrastructure.</span></span>

<span data-ttu-id="e019a-p103">기본 시나리오는 **AlwaysOn**입니다. AlwaysOn은 이름에서 짐작할 수 있듯이 시나리오를 지속적으로 실행하기 위한 용도로 사용됩니다. AlwaysOn 시나리오는 가장 일반적인 대부분의 서버 구성 요소에 대해 정보 수준의 정보를 수집합니다(정보 로깅 수준에는 정보 메시지 외에 심각, 오류 및 경고도 포함됨). AlwaysOn은 문제 발생 전/중/후에 정보를 수집합니다. 이는 OCSLogger와 같은 이전 로깅 도구의 일반적인 동작과는 크게 다릅니다. OCSLogger는 문제가 이미 발생한 후에 실행하는 방식이었으며, 수집되는 데이터가 사전 예방 방식이 아닌 사후 대응 방식이므로 문제를 해결하기가 보다 어려웠습니다. 문제 구성 요소를 파악하고 해당 문제를 해결하기 위한 일련의 동작을 나타내기 위해 확인해야 하는 정보가 AlwaysOn에 포함되어 있지 않은 경우(AlwaysOn에는 매우 다양하고 폭넓은 공급자가 포함되므로 그럴 가능성은 거의 없음), AlwaysOn은 새 시나리오 만들기, 다른 정보 수집, 다른 검색을 실행하여 보다 세부적인 정보 수집 등 수행해야 하는 다른 작업을 결정하기 위한 적절한 정보 수준을 지시합니다.</span><span class="sxs-lookup"><span data-stu-id="e019a-p103">The default scenario is called **AlwaysOn**. The intended purpose for AlwaysOn is to run the scenario constantly, as the name of the scenario implies. The AlwaysOn scenario collects Info level information (note that Info logging level includes Fatal, Error, and Warning in addition to Info messages) for many of the most common server components. AlwaysOn collects information before, during, and after a problem occurs. This differs dramatically from the typical behavior of previous logging tools such as OCSLogger. You ran OCSLogger after the problem had already occurred, making your troubleshooting efforts more difficult because the data that you have is reactive, not proactive. If AlwaysOn does not contain the information that you are looking for in order to point to the problem component and indicate a course of action to fix it (which is not likely given the breadth and depth of providers in AlwaysOn), it will indicate a reasonable level of information to determine what else you need to do, such as creating a new scenario, gather other information, run a different search to collect more focused details, and so on.</span></span>

<span data-ttu-id="e019a-117">중앙 로깅 서비스는 명령을 실행 하는 두 가지 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e019a-117">The Centralized Logging Service provides two ways to issue commands.</span></span> <span data-ttu-id="e019a-118">Lync Server 관리 셸을 통해 Windows PowerShell을 사용 하는 경우 squarely에 집중 된 항목이 많이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e019a-118">A number of topics have been focused squarely on using Windows PowerShell through the Lync Server Management Shell.</span></span> <span data-ttu-id="e019a-119">여러 복잡 구성 및 명령을 사용 하는 기능은 중앙 로깅 서비스 사용을 위해 Windows PowerShell에 우위를 둘 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e019a-119">The ability to use a number of complex configurations and commands favors Windows PowerShell for Centralized Logging Service use.</span></span> <span data-ttu-id="e019a-120">Lync server 관리 셸을 통한 Windows PowerShell은 Lync Server의 모든 기능에 대해 거의 모든 작업을 진행 하기 때문에 Windows PowerShell 명령에 대해서만 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="e019a-120">Because Windows PowerShell through the Lync Server Management Shell is nearly ubiquitous for all functions in Lync Server, only the Windows PowerShell commands are discussed.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="e019a-121">명령줄에서 사용할 수 있는 제한 된 명령 집합을 사용 하려는 경우에는 입력 하 여 CLSController.exe에 대 한 지원을 받을 수 있습니다 <CODE>ClsController.exe</CODE> .</span><span class="sxs-lookup"><span data-stu-id="e019a-121">If you decide to use the limited command set available from the command line, you can get help with CLSController.exe by typing <CODE>ClsController.exe</CODE>.</span></span> <span data-ttu-id="e019a-122">기본적으로 <STRONG>ClsController.exe</STRONG> 는 C:\Program Files\Microsoft Lync Server 2013 \ clsagent 디렉터리에 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e019a-122">By default, <STRONG>ClsController.exe</STRONG> is installed in the directory C:\Program Files\Microsoft Lync Server 2013\ClsAgent.</span></span>



</div>

<div>

## <a name="to-run-start-csclslogging-with-windows-powershell-using-basic-commands"></a><span data-ttu-id="e019a-123">기본 명령을 사용 하 여 Windows PowerShell을 사용 하 여 Start-CsClsLogging를 실행 하려면</span><span class="sxs-lookup"><span data-stu-id="e019a-123">To run Start-CsClsLogging with Windows PowerShell using basic commands</span></span>

1.  <span data-ttu-id="e019a-124">**시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="e019a-124">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="e019a-125">다음을 입력 하 여 중앙화 된 로깅 서비스를 사용 하 여 로깅 시나리오를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="e019a-125">Start a logging scenario with the Centralized Logging Service by typing the following:</span></span>
    
        Start-CsClsLogging -Scenario <name of scenario>
    
    <span data-ttu-id="e019a-126">예를 들어 **AlwaysOn** 시나리오를 시작하려면 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="e019a-126">For example, to start the **AlwaysOn** scenario, type:</span></span>
    
        Start-CsClsLogging -Scenario AlwaysOn
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="e019a-127">AlwaysOn 시나리오에는 기본 기간이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e019a-127">The AlwaysOn scenario has no default duration.</span></span> <span data-ttu-id="e019a-128">즉, 이 시나리오는 <STRONG>Stop-CsClsLogging</STRONG> cmdlet을 사용하여 명시적으로 중지할 때까지 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="e019a-128">This scenario will run until you explicitly stop it with the <STRONG>Stop-CsClsLogging</STRONG> cmdlet.</span></span> <span data-ttu-id="e019a-129">자세한 내용은 <A href="https://technet.microsoft.com/library/JJ619180(v=OCS.15)">Stop-CsClsLogging</A>을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="e019a-129">For details, see <A href="https://technet.microsoft.com/library/JJ619180(v=OCS.15)">Stop-CsClsLogging</A>.</span></span> <span data-ttu-id="e019a-130">다른 모든 시나리오의 경우 기본 기간은 4시간입니다.</span><span class="sxs-lookup"><span data-stu-id="e019a-130">For all other scenarios, the default duration is 4 hours.</span></span>

    
    </div>

3.  <span data-ttu-id="e019a-131">Enter 키를 눌러 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="e019a-131">Press Enter to run the command.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="e019a-132">명령이 실행되어 배포의 컴퓨터로부터 상태를 받을 때가지 시간이 약간 걸릴 수 있습니다(30~60초).</span><span class="sxs-lookup"><span data-stu-id="e019a-132">It may take a short amount of time (30 to 60 seconds) for the commands to run and to receive the status back from the computers in your deployment.</span></span>

    
    </div>
    
    <span data-ttu-id="e019a-133">![시작-CsClsLogging을 실행 합니다.](images/JJ687958.c5be7413-8cef-4de7-9712-944d20cc2fa4(OCS.15).jpg "시작-CsClsLogging을 실행 합니다.")</span><span class="sxs-lookup"><span data-stu-id="e019a-133">![Running Start-CsClsLogging.](images/JJ687958.c5be7413-8cef-4de7-9712-944d20cc2fa4(OCS.15).jpg "Running Start-CsClsLogging.")</span></span>

4.  <span data-ttu-id="e019a-134">다른 시나리오를 시작하려면 실행하려는 추가 시나리오 이름(예: **Authentication** 시나리오)을 포함하여 **Start-CsClsLogging** cmdlet을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e019a-134">To start another scenario, use the **Start-CsClsLogging** cmdlet with the name of the additional scenario to run as follows (for example, the scenario **Authentication**):</span></span>
    
        Start-CsClsLogging -Scenario Authentication
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="e019a-135">지정된 컴퓨터에서 항상 총 2개의 시나리오를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e019a-135">You can have a total of two scenarios running on any given computer at any time.</span></span> <span data-ttu-id="e019a-136">명령의 범위가 전역인 경우에는 배포의 모든 컴퓨터에서 시나리오를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="e019a-136">If the command is global in scope, all of the computers in your deployment will run the scenario or scenarios.</span></span> <span data-ttu-id="e019a-137">세 번째 시나리오를 시작하려면 새 시나리오를 실행할 컴퓨터, 풀, 사이트 또는 전역 범위에서 로깅을 중지해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e019a-137">To start a third scenario, you must stop logging on the computer, pool, site, or global scope that you want to run the new scenario on.</span></span> <span data-ttu-id="e019a-138">전역 범위를 시작한 경우에는 하나 이상의 컴퓨터 및 풀에서 시나리오 하나 또는 둘 다에 대해 로깅을 중지하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e019a-138">If you have started a global scope, you can stop logging for one or both of the scenarios on one or more computers and pools.</span></span> <span data-ttu-id="e019a-139">실행 중인 시나리오를 관리 하는 방법에 대 한 자세한 내용은 Lync Server 2013 및 <A href="https://technet.microsoft.com/library/JJ619180(v=OCS.15)">Stop-CsClsLogging</A> <A href="lync-server-2013-using-stop-for-the-centralized-logging-service.md">에서 중앙화 된 로깅 서비스에 대해 Stop 사용</A> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="e019a-139">For details about managing which scenarios are running, see <A href="lync-server-2013-using-stop-for-the-centralized-logging-service.md">Using Stop for the Centralized Logging Service in Lync Server 2013</A> and <A href="https://technet.microsoft.com/library/JJ619180(v=OCS.15)">Stop-CsClsLogging</A>.</span></span>

    
    </div>

</div>

<div>

## <a name="to-run-start-csclslogging-with-windows-powershell-using-advanced-commands"></a><span data-ttu-id="e019a-140">고급 명령을 사용 하 여 Windows PowerShell에서 Start-CsClsLogging를 실행 하려면</span><span class="sxs-lookup"><span data-stu-id="e019a-140">To run Start-CsClsLogging with Windows PowerShell using advanced commands</span></span>

1.  <span data-ttu-id="e019a-141">**시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="e019a-141">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="e019a-142">추가 매개 변수를 사용하여 로깅 명령을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e019a-142">Additional parameters are available to manage the logging commands.</span></span> <span data-ttu-id="e019a-143">–Duration을 사용하여 시나리오를 실행할 기간을 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e019a-143">You can use –Duration to adjust the length of time for the scenario to run.</span></span> <span data-ttu-id="e019a-144">또한 –Computers(쉼표로 구분된 컴퓨터 FQDN(정규화된 도메인 이름) 목록) 또는 –Pools(로깅을 실행할 풀의 쉼표로 구분된 FQDN 목록)를 정의할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e019a-144">You also can define –Computers, a list of computer fully qualified domain names (FQDNs) separated by a comma, or –Pools, a comma separated list of FQDNs for pools that you want to run logging on.</span></span>
    
    <span data-ttu-id="e019a-145">"Pool01.contoso.net" 풀에서 *Userreplicator* 시나리오에 대 한 로깅 세션을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="e019a-145">You start a logging session for the *UserReplicator* scenario on the pool "pool01.contoso.net".</span></span> <span data-ttu-id="e019a-146">또한 로깅 세션 기간을 8시간으로 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="e019a-146">You also define the duration of the logging session at 8 hours.</span></span> <span data-ttu-id="e019a-147">이렇게 하려면 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="e019a-147">To do this, type:</span></span>
    
        Start-CsClsLogging -Scenario UserReplicator -Duration 8:00 -Pools "pool01.contoso.net"
    
    <span data-ttu-id="e019a-148">이 시나리오가 정상적으로 실행되면 다음과 같은 결과가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="e019a-148">The successful execution of this scenario returns a result like the following:</span></span>
    
    <span data-ttu-id="e019a-149">![시작-CsClsLogging을 실행 합니다.](images/JJ687958.399f0c2e-c08c-40ab-b6c6-381dddc12fe9(OCS.15).jpg "시작-CsClsLogging을 실행 합니다.")</span><span class="sxs-lookup"><span data-stu-id="e019a-149">![Running Start-CsClsLogging.](images/JJ687958.399f0c2e-c08c-40ab-b6c6-381dddc12fe9(OCS.15).jpg "Running Start-CsClsLogging.")</span></span>
    
    <span data-ttu-id="e019a-150">이 예제에서는 AlwaysOn 시나리오와 UserReplicator 시나리오가 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="e019a-150">Note that in this example, the AlwaysOn scenario is running and the UserReplicator scenario is running.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e019a-151">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e019a-151">See Also</span></span>


[<span data-ttu-id="e019a-152">Lync Server 2013의 중앙 로깅 서비스 개요</span><span class="sxs-lookup"><span data-stu-id="e019a-152">Overview of the Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-overview-of-the-centralized-logging-service.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

