---
title: 중앙 로깅 서비스에 대 한 시작을 사용 하 여 로그 캡처
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Using Start for the Centralized Logging Service to capture logs
ms:assetid: 0512b9ce-7f5b-48eb-a79e-f3498bacf2de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687958(v=OCS.15)
ms:contentKeyID: 49733543
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5033b4a8dfd8121e2f0b5926623a55358188935e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983318"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-start-for-the-centralized-logging-service-to-capture-logs-in-lync-server-2013"></a><span data-ttu-id="aa19c-102">중앙 로깅 서비스의 시작을 사용 하 여 Lync Server 2013에서 로그 캡처</span><span class="sxs-lookup"><span data-stu-id="aa19c-102">Using Start for the Centralized Logging Service to capture logs in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="aa19c-103">_**마지막으로 수정한 주제:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="aa19c-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="aa19c-104">중앙 로깅 서비스를 사용 하 여 추적 로그를 캡처하려면 하나 이상의 컴퓨터와 풀에 대 한 로깅을 시작 하는 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa19c-104">To capture trace logs using the Centralized Logging Service, you issue a command to begin logging on one or more computers and pools.</span></span> <span data-ttu-id="aa19c-105">또한 컴퓨터 또는 풀, 실행할 시나리오 (예: AlwaysOn, 미리 정의 된 다른 시나리오 또는 사용자가 만든 시나리오)를 정의 하는 매개 변수를 발행 하 고 추적에 대 한 Lync Server 구성 요소 (예: S4, SipStack)를 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa19c-105">You also issue parameters that define which computers or pools, what scenarios to run (for example, AlwaysOn, another predefined scenario, or a scenario you have created), what Lync Server components (for example, S4, SipStack) to trace.</span></span>

<span data-ttu-id="aa19c-106">적절 한 정보를 캡처하려면 올바른 시나리오를 사용 하 여 문제와 관련 된 정보를 수집 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa19c-106">To capture the right information, you need to make sure you use the right scenario to collect information that is relevant to the problem.</span></span> <span data-ttu-id="aa19c-107">중앙 로깅 서비스에서 시나리오는 서버 구성 요소, 로깅 수준, 플래그의 컬렉션을 기준으로 로깅을 설정 하는 개념으로, 서버 단위로 이러한 요소를 정의 하는 것 보다 훨씬 더 효율적이 고 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa19c-107">In the Centralized Logging Service, a scenario is the concept of turning logging on based on a collection of server components, logging levels, and flags, which is much more efficient and useful than having to define these elements on a per-server basis.</span></span> <span data-ttu-id="aa19c-108">실행할 시나리오를 정의 하 고 지정 하면 시나리오가 인프라 범위의 모든 서버와 풀에서 일관 되 게 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="aa19c-108">You define and specify a scenario to run and the scenario is run consistently across all servers and pools in the scope of the infrastructure.</span></span>

<span data-ttu-id="aa19c-109">기본 시나리오는 **AlwaysOn**이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa19c-109">The default scenario is called **AlwaysOn**.</span></span> <span data-ttu-id="aa19c-110">AlwaysOn에 대 한 의도 된 용도는 시나리오 이름에 해당 하는 것 처럼 계속 해 서 시나리오를 실행 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="aa19c-110">The intended purpose for AlwaysOn is to run the scenario constantly, as the name of the scenario implies.</span></span> <span data-ttu-id="aa19c-111">AlwaysOn 시나리오는 정보 수준 정보를 수집 합니다 (정보 로깅 수준에는 대부분의 일반적인 서버 구성 요소에 대 한 정보 메시지 외에 치명적, 오류, 경고가 포함 됨).</span><span class="sxs-lookup"><span data-stu-id="aa19c-111">The AlwaysOn scenario collects Info level information (note that Info logging level includes Fatal, Error, and Warning in addition to Info messages) for many of the most common server components.</span></span> <span data-ttu-id="aa19c-112">AlwaysOn은 문제가 발생 하기 전과 후에 정보를 수집 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa19c-112">AlwaysOn collects information before, during, and after a problem occurs.</span></span> <span data-ttu-id="aa19c-113">이는 OCSLogger 같은 이전 로깅 도구의 일반적인 동작과 크게 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="aa19c-113">This differs dramatically from the typical behavior of previous logging tools such as OCSLogger.</span></span> <span data-ttu-id="aa19c-114">문제가 이미 발생 한 후 OCSLogger 실행 하 여 문제를 해결 하기 위해 보유 하 고 있는 데이터는 사전 대응적인이 아니라 반응 하기 때문에 더욱 어려워집니다.</span><span class="sxs-lookup"><span data-stu-id="aa19c-114">You ran OCSLogger after the problem had already occurred, making your troubleshooting efforts more difficult because the data that you have is reactive, not proactive.</span></span> <span data-ttu-id="aa19c-115">AlwaysOn에 문제 구성 요소를 가리키기 위해 원하는 정보를 포함 하 고 있지 않은 경우 (AlwaysOn에서 공급자의 범위 및 깊이가 제공 되지 않는 경우)에는 적절 한 수준의 정보가 표시 됩니다. 새 시나리오 만들기, 다른 정보 수집, 다른 검색을 실행 하 여 중요 한 세부 정보 수집 등의 다른 작업을 수행 해야 하는 경우를 rmation.</span><span class="sxs-lookup"><span data-stu-id="aa19c-115">If AlwaysOn does not contain the information that you are looking for in order to point to the problem component and indicate a course of action to fix it (which is not likely given the breadth and depth of providers in AlwaysOn), it will indicate a reasonable level of information to determine what else you need to do, such as creating a new scenario, gather other information, run a different search to collect more focused details, and so on.</span></span>

<span data-ttu-id="aa19c-116">중앙 로깅 서비스에서는 두 가지 방법으로 명령을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aa19c-116">The Centralized Logging Service provides two ways to issue commands.</span></span> <span data-ttu-id="aa19c-117">Lync Server Management Shell을 통해 Windows PowerShell을 사용 하는 경우 많은 항목을 집중적으로 정사각형.</span><span class="sxs-lookup"><span data-stu-id="aa19c-117">A number of topics have been focused squarely on using Windows PowerShell through the Lync Server Management Shell.</span></span> <span data-ttu-id="aa19c-118">여러 복잡 한 구성과 명령을 사용 하는 기능은 중앙 로깅 서비스 사용을 위해 Windows PowerShell에 우선 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa19c-118">The ability to use a number of complex configurations and commands favors Windows PowerShell for Centralized Logging Service use.</span></span> <span data-ttu-id="aa19c-119">Lync Server 관리 셸을 통한 Windows PowerShell은 Lync Server의 모든 함수에 대해 거의 모든 기능을 사용할 수 있기 때문에 Windows PowerShell 명령에 대해서만 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa19c-119">Because Windows PowerShell through the Lync Server Management Shell is nearly ubiquitous for all functions in Lync Server, only the Windows PowerShell commands are discussed.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="aa19c-120">명령줄에서 사용할 수 있는 제한 된 명령 집합을 사용 하기로 결정 한 경우, CLSController를 입력 <CODE>ClsController.exe</CODE>하 여 도움을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aa19c-120">If you decide to use the limited command set available from the command line, you can get help with CLSController.exe by typing <CODE>ClsController.exe</CODE>.</span></span> <span data-ttu-id="aa19c-121">기본적으로 <STRONG>Clscontroller</STRONG> 는 디렉터리 C:\Program Files\Microsoft Lync Server 2013 \ clscontroller에 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="aa19c-121">By default, <STRONG>ClsController.exe</STRONG> is installed in the directory C:\Program Files\Microsoft Lync Server 2013\ClsAgent.</span></span>



</div>

<div>

## <a name="to-run-start-csclslogging-with-windows-powershell-using-basic-commands"></a><span data-ttu-id="aa19c-122">기본 명령을 사용 하 여 Windows PowerShell을 사용 하 여 시작-CsClsLogging을 실행 하려면</span><span class="sxs-lookup"><span data-stu-id="aa19c-122">To run Start-CsClsLogging with Windows PowerShell using basic commands</span></span>

1.  <span data-ttu-id="aa19c-123">Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa19c-123">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="aa19c-124">다음을 입력 하 여 중앙 집중화 된 로깅 서비스를 사용 하 여 로깅 시나리오를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa19c-124">Start a logging scenario with the Centralized Logging Service by typing the following:</span></span>
    
        Start-CsClsLogging -Scenario <name of scenario>
    
    <span data-ttu-id="aa19c-125">예를 들어 **AlwaysOn** 시나리오를 시작 하려면 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa19c-125">For example, to start the **AlwaysOn** scenario, type:</span></span>
    
        Start-CsClsLogging -Scenario AlwaysOn
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="aa19c-126">AlwaysOn 시나리오에는 기본 기간이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="aa19c-126">The AlwaysOn scenario has no default duration.</span></span> <span data-ttu-id="aa19c-127">이 시나리오는 <STRONG>중지-CsClsLogging</STRONG> cmdlet을 사용 하 여 명시적으로 중지할 때까지 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="aa19c-127">This scenario will run until you explicitly stop it with the <STRONG>Stop-CsClsLogging</STRONG> cmdlet.</span></span> <span data-ttu-id="aa19c-128">자세한 내용은 <A href="https://technet.microsoft.com/en-us/library/JJ619180(v=OCS.15)">중지-CsClsLogging</A>을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="aa19c-128">For details, see <A href="https://technet.microsoft.com/en-us/library/JJ619180(v=OCS.15)">Stop-CsClsLogging</A>.</span></span> <span data-ttu-id="aa19c-129">다른 모든 시나리오의 경우 기본 기간은 4 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="aa19c-129">For all other scenarios, the default duration is 4 hours.</span></span>

    
    </div>

3.  <span data-ttu-id="aa19c-130">Enter 키를 눌러 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa19c-130">Press Enter to run the command.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="aa19c-131">명령을 실행 하 고 배포의 컴퓨터에서 상태를 다시 받으려면 짧은 시간 (30 ~ 60 초)이 소요 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aa19c-131">It may take a short amount of time (30 to 60 seconds) for the commands to run and to receive the status back from the computers in your deployment.</span></span>

    
    </div>
    
    <span data-ttu-id="aa19c-132">![시작-CsClsLogging을 실행 합니다.] (images/JJ687958.c5be7413-8cef-4de7-9712-944d20cc2fa4(OCS.15).jpg "시작-CsClsLogging을 실행 합니다.")</span><span class="sxs-lookup"><span data-stu-id="aa19c-132">![Running Start-CsClsLogging.](images/JJ687958.c5be7413-8cef-4de7-9712-944d20cc2fa4(OCS.15).jpg "Running Start-CsClsLogging.")</span></span>

4.  <span data-ttu-id="aa19c-133">다른 시나리오를 시작 하려면 다음과 같이 실행할 추가 시나리오의 이름과 함께 **시작 CsClsLogging** cmdlet을 사용 합니다 (예: 시나리오 **인증**).</span><span class="sxs-lookup"><span data-stu-id="aa19c-133">To start another scenario, use the **Start-CsClsLogging** cmdlet with the name of the additional scenario to run as follows (for example, the scenario **Authentication**):</span></span>
    
        Start-CsClsLogging -Scenario Authentication
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="aa19c-134">언제 든 지 모든 컴퓨터에서 실행 되는 두 시나리오의 총을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aa19c-134">You can have a total of two scenarios running on any given computer at any time.</span></span> <span data-ttu-id="aa19c-135">명령이 전역 범위인 경우 배포의 모든 컴퓨터에서 시나리오를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa19c-135">If the command is global in scope, all of the computers in your deployment will run the scenario or scenarios.</span></span> <span data-ttu-id="aa19c-136">세 번째 시나리오를 시작 하려면 새 시나리오를 실행 하려는 컴퓨터, 풀, 사이트 또는 전역 범위에 대 한 로깅을 중지 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa19c-136">To start a third scenario, you must stop logging on the computer, pool, site, or global scope that you want to run the new scenario on.</span></span> <span data-ttu-id="aa19c-137">전역 범위를 시작한 경우 하나 또는 그 이상의 컴퓨터와 풀에 대해 하나 또는 둘 다에 대 한 로깅을 중지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aa19c-137">If you have started a global scope, you can stop logging for one or both of the scenarios on one or more computers and pools.</span></span> <span data-ttu-id="aa19c-138">실행 중인 시나리오를 관리 하는 방법에 대 한 자세한 내용은 <A href="lync-server-2013-using-stop-for-the-centralized-logging-service.md">Lync Server 2013 및 CsClsLogging 대 한 중앙 로깅 서비스에 대 한 중지 사용</A> 을 참조 하세요. <A href="https://technet.microsoft.com/en-us/library/JJ619180(v=OCS.15)"></A></span><span class="sxs-lookup"><span data-stu-id="aa19c-138">For details about managing which scenarios are running, see <A href="lync-server-2013-using-stop-for-the-centralized-logging-service.md">Using Stop for the Centralized Logging Service in Lync Server 2013</A> and <A href="https://technet.microsoft.com/en-us/library/JJ619180(v=OCS.15)">Stop-CsClsLogging</A>.</span></span>

    
    </div>

</div>

<div>

## <a name="to-run-start-csclslogging-with-windows-powershell-using-advanced-commands"></a><span data-ttu-id="aa19c-139">고급 명령을 사용 하 여 Windows PowerShell에서 시작-CsClsLogging을 실행 하려면</span><span class="sxs-lookup"><span data-stu-id="aa19c-139">To run Start-CsClsLogging with Windows PowerShell using advanced commands</span></span>

1.  <span data-ttu-id="aa19c-140">Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa19c-140">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="aa19c-141">추가 매개 변수를 사용 하 여 로깅 명령을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aa19c-141">Additional parameters are available to manage the logging commands.</span></span> <span data-ttu-id="aa19c-142">– Duration을 사용 하 여 시나리오가 실행 되는 시간을 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aa19c-142">You can use –Duration to adjust the length of time for the scenario to run.</span></span> <span data-ttu-id="aa19c-143">또한 컴퓨터, 쉼표로 구분 된 컴퓨터의 Fqdn (정규화 된 도메인 이름) 목록 또는 로깅을 실행 하려는 풀에 대해 쉼표로 구분 된 Fqdn 목록을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aa19c-143">You also can define –Computers, a list of computer fully qualified domain names (FQDNs) separated by a comma, or –Pools, a comma separated list of FQDNs for pools that you want to run logging on.</span></span>
    
    <span data-ttu-id="aa19c-144">"Pool01.contoso.net" 풀의 *Userreplicator* 시나리오에 대 한 로깅 세션을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa19c-144">You start a logging session for the *UserReplicator* scenario on the pool "pool01.contoso.net".</span></span> <span data-ttu-id="aa19c-145">또한 로깅 세션의 기간을 8 시간으로 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa19c-145">You also define the duration of the logging session at 8 hours.</span></span> <span data-ttu-id="aa19c-146">이렇게 하려면 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa19c-146">To do this, type:</span></span>
    
        Start-CsClsLogging -Scenario UserReplicator -Duration 8:00 -Pools "pool01.contoso.net"
    
    <span data-ttu-id="aa19c-147">이 시나리오를 성공적으로 실행 하면 다음과 같은 결과가 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="aa19c-147">The successful execution of this scenario returns a result like the following:</span></span>
    
    <span data-ttu-id="aa19c-148">![시작-CsClsLogging을 실행 합니다.] (images/JJ687958.399f0c2e-c08c-40ab-b6c6-381dddc12fe9(OCS.15).jpg "시작-CsClsLogging을 실행 합니다.")</span><span class="sxs-lookup"><span data-stu-id="aa19c-148">![Running Start-CsClsLogging.](images/JJ687958.399f0c2e-c08c-40ab-b6c6-381dddc12fe9(OCS.15).jpg "Running Start-CsClsLogging.")</span></span>
    
    <span data-ttu-id="aa19c-149">이 예제에서는 AlwaysOn 시나리오가 실행 중이 고 UserReplicator 시나리오가 실행 되 고 있는 것을 참고 하세요.</span><span class="sxs-lookup"><span data-stu-id="aa19c-149">Note that in this example, the AlwaysOn scenario is running and the UserReplicator scenario is running.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="aa19c-150">참고 항목</span><span class="sxs-lookup"><span data-stu-id="aa19c-150">See Also</span></span>


[<span data-ttu-id="aa19c-151">Lync Server 2013의 중앙 집중화 된 로깅 서비스 개요</span><span class="sxs-lookup"><span data-stu-id="aa19c-151">Overview of the Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-overview-of-the-centralized-logging-service.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

