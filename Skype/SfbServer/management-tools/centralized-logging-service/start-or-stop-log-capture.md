---
title: 비즈니스용 Skype 서버 2015에서 CLS 로그 캡처 시작 또는 중지
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 0512b9ce-7f5b-48eb-a79e-f3498bacf2de
description: '요약: 비즈니스용 Skype 서버 2015에서 중앙 로깅 서비스 로그 캡처 세션을 시작하거나 중지하는 방법을 설명하는 정보를 제공합니다.'
ms.openlocfilehash: cd6864b0d4d16e952f93fe321b49522028d76e5b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49835138"
---
# <a name="start-or-stop-cls-log-capture-in-skype-for-business-server-2015"></a><span data-ttu-id="c7999-103">비즈니스용 Skype 서버 2015에서 CLS 로그 캡처 시작 또는 중지</span><span class="sxs-lookup"><span data-stu-id="c7999-103">Start or stop CLS log capture in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="c7999-104">**요약:** 비즈니스용 Skype 서버 2015에서 중앙 로깅 서비스 로그 캡처 세션을 시작하거나 중지하는 방법에 대해 자세히 알아보습니다.</span><span class="sxs-lookup"><span data-stu-id="c7999-104">**Summary:** Learn how to start or stop a Centralized Logging Service log capture session in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="c7999-105">중앙 로깅 서비스를 사용하여 추적 로그를 캡처하려면 하나 이상의 컴퓨터 및 풀에서 로깅을 시작하는 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="c7999-105">To capture trace logs using the Centralized Logging Service, you issue a command to begin logging on one or more computers and pools.</span></span> <span data-ttu-id="c7999-106">또한 어떤 컴퓨터 또는 풀, 실행할 시나리오(예: AlwaysOn, 미리 정의한 시나리오 또는 만든 시나리오), 추적할 비즈니스용 Skype 서버 구성 요소(예: S4, SipStack)를 정의하는 매개 변수를 발급합니다.</span><span class="sxs-lookup"><span data-stu-id="c7999-106">You also issue parameters that define which computers or pools, what scenarios to run (for example, AlwaysOn, another predefined scenario, or a scenario you have created), what Skype for Business Server components (for example, S4, SipStack) to trace.</span></span>
  
<span data-ttu-id="c7999-107">적절한 정보를 캡처하려면 올바른 시나리오를 사용하여 문제와 관련된 정보를 수집해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7999-107">To capture the right information, you need to make sure you use the right scenario to collect information that is relevant to the problem.</span></span> <span data-ttu-id="c7999-108">중앙 로깅 서비스에서 시나리오는 서버 구성 요소, 로깅 수준 및 플래그 모음을 기반으로 로깅을 설정하는 개념으로, 서버당 이러한 요소를 정의하는 것보다 훨씬 효율적이며 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="c7999-108">In the Centralized Logging Service, a scenario is the concept of turning logging on based on a collection of server components, logging levels, and flags, which is much more efficient and useful than having to define these elements on a per-server basis.</span></span> <span data-ttu-id="c7999-109">시나리오를 정의 및 지정하면 인프라 범위 내의 모든 서버 및 풀에서 시나리오가 일관성 있게 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="c7999-109">You define and specify a scenario to run and the scenario is run consistently across all servers and pools in the scope of the infrastructure.</span></span>
  
<span data-ttu-id="c7999-p103">기본 시나리오는 **AlwaysOn** 입니다. AlwaysOn은 이름에서 짐작할 수 있듯이 시나리오를 지속적으로 실행하기 위한 용도로 사용됩니다. AlwaysOn 시나리오는 가장 일반적인 대부분의 서버 구성 요소에 대해 정보 수준의 정보를 수집합니다(정보 로깅 수준에는 정보 메시지 외에 심각, 오류 및 경고도 포함됨). AlwaysOn은 문제 발생 전/중/후에 정보를 수집합니다. 이는 OCSLogger와 같은 이전 로깅 도구의 일반적인 동작과는 크게 다릅니다. OCSLogger는 문제가 이미 발생한 후에 실행하는 방식이었으며, 수집되는 데이터가 사전 예방 방식이 아닌 사후 대응 방식이므로 문제를 해결하기가 보다 어려웠습니다. 문제 구성 요소를 파악하고 해당 문제를 해결하기 위한 일련의 동작을 나타내기 위해 확인해야 하는 정보가 AlwaysOn에 포함되어 있지 않은 경우(AlwaysOn에는 매우 다양하고 폭넓은 공급자가 포함되므로 그럴 가능성은 거의 없음), AlwaysOn은 새 시나리오 만들기, 다른 정보 수집, 다른 검색을 실행하여 보다 세부적인 정보 수집 등 수행해야 하는 다른 작업을 결정하기 위한 적절한 정보 수준을 지시합니다.</span><span class="sxs-lookup"><span data-stu-id="c7999-p103">The default scenario is called **AlwaysOn**. The intended purpose for AlwaysOn is to run the scenario constantly, as the name of the scenario implies. The AlwaysOn scenario collects Info level information (note that Info logging level includes Fatal, Error, and Warning in addition to Info messages) for many of the most common server components. AlwaysOn collects information before, during, and after a problem occurs. This differs dramatically from the typical behavior of previous logging tools such as OCSLogger. You ran OCSLogger after the problem had already occurred, making your troubleshooting efforts more difficult because the data that you have is reactive, not proactive. If AlwaysOn does not contain the information that you are looking for in order to point to the problem component and indicate a course of action to fix it (which is not likely given the breadth and depth of providers in AlwaysOn), it will indicate a reasonable level of information to determine what else you need to do, such as creating a new scenario, gather other information, run a different search to collect more focused details, and so on.</span></span>
  
<span data-ttu-id="c7999-117">중앙 로깅 서비스는 명령을 발급하는 두 가지 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c7999-117">The Centralized Logging Service provides two ways to issue commands.</span></span> <span data-ttu-id="c7999-118">많은 항목은 비즈니스용 Skype 서버 관리 셸을 통해 Windows PowerShell 정사각형으로 초점을 맞추고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7999-118">A number of topics have been focused squarely on using Windows PowerShell through the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="c7999-119">다양한 복잡한 구성 및 명령을 사용하는 기능을 통해 중앙 로깅 Windows PowerShell 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7999-119">The ability to use a number of complex configurations and commands favors Windows PowerShell for Centralized Logging Service use.</span></span> <span data-ttu-id="c7999-120">비즈니스 Windows PowerShell 서버 관리 셸을 통해 사용할 수 있는 기능은 비즈니스용 Skype 서버의 모든 기능에 거의 사용되지 Windows PowerShell 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7999-120">Because Windows PowerShell through the Skype for Business Server Management Shell is nearly ubiquitous for all functions in Skype for Business Server, only the Windows PowerShell commands are discussed.</span></span> 
  
### <a name="to-run-start-csclslogging-with-windows-powershell-using-basic-commands"></a><span data-ttu-id="c7999-121">기본 Start-CsClsLogging 사용하여 Windows PowerShell 실행</span><span class="sxs-lookup"><span data-stu-id="c7999-121">To run Start-CsClsLogging with Windows PowerShell using basic commands</span></span>

1. <span data-ttu-id="c7999-122">비즈니스용 Skype 서버 관리 셸 시작: **시작,** 모든 **프로그램,** 비즈니스용 **Skype 2015,** 비즈니스용 Skype 서버 관리 셸을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="c7999-122">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="c7999-123">다음을 입력하여 중앙 로깅 서비스로 로깅 시나리오를 시작하십시오.</span><span class="sxs-lookup"><span data-stu-id="c7999-123">Start a logging scenario with the Centralized Logging Service by typing the following:</span></span>
    
   ```PowerShell
   Start-CsClsLogging -Scenario <name of scenario>
   ```

    <span data-ttu-id="c7999-124">예를 들어 **AlwaysOn** 시나리오를 시작하려면 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="c7999-124">For example, to start the **AlwaysOn** scenario, type:</span></span>
    
   ```PowerShell
   Start-CsClsLogging -Scenario AlwaysOn
   ```

    > [!NOTE]
    > <span data-ttu-id="c7999-125">AlwaysOn 시나리오에는 기본 기간이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c7999-125">The AlwaysOn scenario has no default duration.</span></span> <span data-ttu-id="c7999-126">즉, 이 시나리오는 **Stop-CsClsLogging** cmdlet을 사용하여 명시적으로 중지할 때까지 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="c7999-126">This scenario will run until you explicitly stop it with the **Stop-CsClsLogging** cmdlet.</span></span> <span data-ttu-id="c7999-127">자세한 내용은 [Stop-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/stop-csclslogging?view=skype-ps)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="c7999-127">For details, see [Stop-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/stop-csclslogging?view=skype-ps).</span></span> <span data-ttu-id="c7999-128">다른 모든 시나리오의 경우 기본 기간은 4시간입니다.</span><span class="sxs-lookup"><span data-stu-id="c7999-128">For all other scenarios, the default duration is 4 hours.</span></span> 
  
3. <span data-ttu-id="c7999-129">Enter 키를 눌러 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="c7999-129">Press Enter to run the command.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="c7999-130">명령이 실행되어 배포의 컴퓨터로부터 상태를 받을 때가지 시간이 약간 걸릴 수 있습니다(30~60초).</span><span class="sxs-lookup"><span data-stu-id="c7999-130">It may take a short amount of time (30 to 60 seconds) for the commands to run and to receive the status back from the computers in your deployment.</span></span> 
  
     ![Start-CsClsLogging 실행.](../../media/Ops_CLS_Show_and_Start_ClsLogging.jpg)
  
4. <span data-ttu-id="c7999-132">다른 시나리오를 시작하려면 실행하려는 추가 시나리오 이름(예: **Authentication** 시나리오)을 포함하여 **Start-CsClsLogging** cmdlet을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c7999-132">To start another scenario, use the **Start-CsClsLogging** cmdlet with the name of the additional scenario to run as follows (for example, the scenario **Authentication**):</span></span>
    
   ```PowerShell
   Start-CsClsLogging -Scenario Authentication
   ```

    > [!IMPORTANT]
    > <span data-ttu-id="c7999-133">지정된 컴퓨터에서 항상 총 2개의 시나리오를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7999-133">You can have a total of two scenarios running on any given computer at any time.</span></span> <span data-ttu-id="c7999-134">명령의 범위가 전역인 경우에는 배포의 모든 컴퓨터에서 시나리오를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="c7999-134">If the command is global in scope, all of the computers in your deployment will run the scenario or scenarios.</span></span> <span data-ttu-id="c7999-135">세 번째 시나리오를 시작하려면 새 시나리오를 실행할 컴퓨터, 풀, 사이트 또는 전역 범위에서 로깅을 중지해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7999-135">To start a third scenario, you must stop logging on the computer, pool, site, or global scope that you want to run the new scenario on.</span></span> <span data-ttu-id="c7999-136">전역 범위를 시작한 경우에는 하나 이상의 컴퓨터 및 풀에서 시나리오 하나 또는 둘 다에 대해 로깅을 중지하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c7999-136">If you have started a global scope, you can stop logging for one or both of the scenarios on one or more computers and pools.</span></span> 
  
### <a name="to-run-start-csclslogging-with-windows-powershell-using-advanced-commands"></a><span data-ttu-id="c7999-137">고급 Start-CsClsLogging 사용하여 Windows PowerShell 실행</span><span class="sxs-lookup"><span data-stu-id="c7999-137">To run Start-CsClsLogging with Windows PowerShell using advanced commands</span></span>

1. <span data-ttu-id="c7999-138">비즈니스용 Skype 서버 관리 셸 시작: **시작,** 모든 **프로그램,** 비즈니스용 **Skype 2015,** 비즈니스용 Skype 서버 관리 셸을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="c7999-138">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="c7999-139">추가 매개 변수를 사용하여 로깅 명령을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7999-139">Additional parameters are available to manage the logging commands.</span></span> <span data-ttu-id="c7999-140">-Duration을 사용하여 시나리오를 실행할 시간을 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7999-140">You can use -Duration to adjust the length of time for the scenario to run.</span></span> <span data-ttu-id="c7999-141">또한 -Computers, 컴퓨터 FQDNS(정식 도메인 이름) 목록(콤보로 구분) 또는 -Pools(로깅을 실행할 풀의 FQDNS 목록)를 정의할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7999-141">You also can define -Computers, a list of computer fully qualified domain names (FQDNs) separated by a comma, or -Pools, a comma separated list of FQDNs for pools that you want to run logging on.</span></span>
    
    <span data-ttu-id="c7999-142">"pool01.contoso.net" 풀에서 UserReplicator 시나리오에 대한 로깅 세션을 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7999-142">You start a logging session for the UserReplicator scenario on the pool "pool01.contoso.net".</span></span> <span data-ttu-id="c7999-143">또한 로깅 세션 기간을 8시간으로 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="c7999-143">You also define the duration of the logging session at 8 hours.</span></span> <span data-ttu-id="c7999-144">이렇게 하려면 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="c7999-144">To do this, type:</span></span>
    
   ```PowerShell
   Start-CsClsLogging -Scenario UserReplicator -Duration 8:00 -Pools "pool01.contoso.net"
   ```

    <span data-ttu-id="c7999-145">이 시나리오가 정상적으로 실행되면 다음과 같은 결과가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="c7999-145">The successful execution of this scenario returns a result like the following:</span></span>
    
     ![Start-CsClsLogging 실행.](../../media/Ops_CsClsLogging_UserReplicator_Exp.jpg)
  
<span data-ttu-id="c7999-147">이 예제에서는 AlwaysOn 시나리오와 UserReplicator 시나리오가 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="c7999-147">Note that in this example, the AlwaysOn scenario is running and the UserReplicator scenario is running.</span></span> 
    
## <a name="stop-the-centralized-logging-service-log-capture"></a><span data-ttu-id="c7999-148">중앙 로깅 서비스 로그 캡처 중지</span><span class="sxs-lookup"><span data-stu-id="c7999-148">Stop the Centralized Logging Service log capture</span></span>
<span data-ttu-id="c7999-149"><a name="stop"> </a></span><span class="sxs-lookup"><span data-stu-id="c7999-149"><a name="stop"> </a></span></span>

<span data-ttu-id="c7999-150">Stop-CsClsLogging cmdlet을 사용하여 현재 실행 중인 로깅 세션을 중지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7999-150">You can stop a currently running logging session with the Stop-CsClsLogging cmdlet.</span></span> <span data-ttu-id="c7999-151">일반적으로 로깅 세션을 중지해야 하는 상황은 많지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c7999-151">Generally, there aren't many situations in which you would need to stop a logging session.</span></span> <span data-ttu-id="c7999-152">예를 들어 로깅을 먼저 중지하지 않고도 로그를 검색하고 구성을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7999-152">For example, you can search logs and change configurations without first needing to stop logging.</span></span> <span data-ttu-id="c7999-153">두 시나리오(AlwaysOn 및 UserReplicator)를 실행 중인데 Authentication 관련 정보를 수집해야 하는 경우에는 전역, 사이트, 풀 또는 컴퓨터 범위에서 다른 시나리오 중 하나를 중지해야 Authentication 시나리오 실행을 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7999-153">If you have two scenarios running, for example AlwaysOn and UserReplicator, and you need to collect information related to Authentication, you will need to stop one of the other scenarios (at a global, site, pool or computer scope) before you can start running to Authentication scenario.</span></span> <span data-ttu-id="c7999-154">자세한 내용은 [Stop-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/stop-csclslogging?view=skype-ps)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="c7999-154">For details, see [Stop-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/stop-csclslogging?view=skype-ps).</span></span>
  
> [!NOTE]
> <span data-ttu-id="c7999-155">특정 배포, 풀 또는 컴퓨터에서 실행할 수 있는 시나리오를 결정할 때 AlwaysOn 및 사용자 지정 시나리오의 두 가지 시나리오를 컴퓨터당 실행으로 제한해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7999-155">When determining what scenarios you can run on a given deployment, pool or computer, you need to remember that you are limited to running two scenarios **per computer**: AlwaysOn and one custom scenario.</span></span> <span data-ttu-id="c7999-156">풀에서 활동을 로깅 중이라면 풀을 엔터티 하나로 간주해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7999-156">If you are logging activity on a pool, you should treat a pool as a single entity.</span></span> <span data-ttu-id="c7999-157">대부분의 경우에는 풀의 각 컴퓨터에서 서로 다른 시나리오를 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c7999-157">In most cases, it would not make sense to run different scenarios on each computer in a pool.</span></span> <span data-ttu-id="c7999-158">데이터를 수집 중인 문제를 확인하여 전체 배포에서 지정된 컴퓨터에 가장 적합한 시나리오를 고려하는 것이 적절합니다.</span><span class="sxs-lookup"><span data-stu-id="c7999-158">It does make sense to look at the problem that you are collecting data about and think about what scenario makes the most sense on a given computer in the overall deployment.</span></span> <span data-ttu-id="c7999-159">예를 들어 UserReplicator 시나리오를 고려하는 경우 에지 서버 또는 에지 풀에서 UserReplicator를 실행하는 데는 값이 거의 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c7999-159">For example, if you consider the UserReplicator scenario, there would be very little value in running UserReplicator on an Edge Server or Edge pool.</span></span> 
  
<span data-ttu-id="c7999-p111">문제와 영향의 범위를 파악한 후에는 각 컴퓨터와 풀에서 실행할 시나리오를 적절하게 선택해야 합니다. AlwaysOn 시나리오는 다양한 공급자에 대한 정보를 수집하므로 폭넓은 응용 프로그램에 적합하기는 하지만, 특정 시나리오는 특정 컴퓨터나 풀에서만 응용 프로그램과 관련하여 유용합니다. 또한 먼저 지정된 시나리오의 유용성을 파악하지 않고 로깅 세션을 임의로 시작할 때도 주의해야 합니다. 잘못된 시나리오를 사용하거나 작업에 적합한 시나리오를 사용하기는 하지만 잘못된 범위(전역/사이트/풀/컴퓨터)에서 시나리오를 적용하는 경우에는 시나리오를 전혀 실행하지 않은 것과 마찬가지로 부적절한 데이터가 제공될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7999-p111">After you understand the problem and the scope of the impact, you should make careful choices about what scenarios to run on which computers and pools. While the AlwaysOn scenario makes sense for a wide scope application because it collects information on a wide variety of providers, specific scenarios only have application value on specific computers or pools. Also, you should take caution when randomly starting up a logging session without first understanding the value of a given scenario. If you use the wrong scenario, or if you use a scenario that is appropriate for the task and you apply the scenario at the wrong scope (be it global, site, pool, or computer), you can get questionable data that is not very useful—as if you didn't run the scenario at all.</span></span>
  
<span data-ttu-id="c7999-164">비즈니스용 Skype 서버 관리 셸을 사용하여 중앙 로깅 서비스 기능을 제어하려면 CsAdministrator 또는 CsServerAdministrator RBAC(역할 기반 액세스 제어) 보안 그룹의 구성원 또는 이러한 두 그룹 중 하나를 포함하는 사용자 지정 RBAC 역할의 구성원이 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7999-164">To control the Centralized Logging Service functions by using the Skype for Business Server Management Shell, you must be a member of either the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> <span data-ttu-id="c7999-165">직접 만든 사용자 지정 RBAC 역할을 포함하여 이 cmdlet이 할당된 모든 RBAC 역할의 목록을 반환하기 위해 비즈니스용 Skype 서버 관리 셸 또는 Windows PowerShell 프롬프트에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="c7999-165">To return a list of all the RBAC roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Skype for Business Server Management Shell or the Windows PowerShell prompt:</span></span>
  
```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Skype for Business Server 2015 cmdlet"}
```

<span data-ttu-id="c7999-166">예제:</span><span class="sxs-lookup"><span data-stu-id="c7999-166">For example:</span></span>
  
```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

> [!NOTE]
> <span data-ttu-id="c7999-167">궁금할 수 있습니다. 이제 로깅을 사용하도록 설정했습니다. 로그는 어디에 보관하나요?</span><span class="sxs-lookup"><span data-stu-id="c7999-167">So you may be wondering: Now that you've enabled logging, where are the logs kept?</span></span> <span data-ttu-id="c7999-168">CLS 에이전트로 전송된 관리 셸 쿼리를 사용하여 로그에 저장된 정보에 액세스하고 결과를 여러 가능한 파일 형식으로 출력할 수 있습니다. 각 서버에서 CLS 에이전트가 레코드를 보관하는 것은 실제로 알지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="c7999-168">Since you'll access the information stored in the logs using management shell queries sent to the CLS Agents, and you can output the results to several possible file formats, where on each server a CLS Agent keeps its records isn't actually important to know.</span></span>  <span data-ttu-id="c7999-169">로그 파일은 지정하고 읽고 분석하는 위치에 저장할 수 있습니다. 로그  파일은Snooper.exe파일과 같은 텍스트 파일을 읽을 수 있는 도구 등 다양한 도구를 **사용하여Notepad.exe.**</span><span class="sxs-lookup"><span data-stu-id="c7999-169">The log files can be saved to a location you specify and  read and analyzed using a variety of tools, including **Snooper.exe** and any tool that can read a text file, such as **Notepad.exe**.</span></span> <span data-ttu-id="c7999-170">Snooper.exe 비즈니스용 Skype 서버 2015 디버그 도구의 일부로 웹 다운로드로 사용할 [수 있습니다.](https://go.microsoft.com/fwlink/p/?LinkId=285257)</span><span class="sxs-lookup"><span data-stu-id="c7999-170">Snooper.exe is part of the Skype for Business Server 2015 Debug Tools and is available as a [Web download](https://go.microsoft.com/fwlink/p/?LinkId=285257).</span></span>

### <a name="to-stop-a-currently-running-centralized-logging-service-session"></a><span data-ttu-id="c7999-171">현재 실행 중인 중앙 로깅 서비스 세션을 중지합니다.</span><span class="sxs-lookup"><span data-stu-id="c7999-171">To stop a currently running Centralized Logging Service session</span></span>

1. <span data-ttu-id="c7999-172">비즈니스용 Skype 서버 관리 셸 시작: **시작,** 모든 **프로그램,** 비즈니스용 **Skype 2015,** 비즈니스용 Skype 서버 관리 셸을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="c7999-172">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="c7999-173">중앙 로깅 서비스를 쿼리하여 다음을 입력하여 현재 실행 중인 시나리오를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="c7999-173">Query the Centralized Logging Service to find out what scenarios are currently running by typing the following:</span></span>
    
   ```PowerShell
   Show-CsClsLogging
   ```

   ![Windows PowerShell 호출한 후 콘솔을 Show-CsCl](../../media/Ops_Show_Stop_CsClsLogging.jpg)
  
   <span data-ttu-id="c7999-175">Show-CsClsLogging의 결과는 실행 중인 시나리오 및 시나리오가 실행되는 범위의 요약입니다.</span><span class="sxs-lookup"><span data-stu-id="c7999-175">The result of Show-CsClsLogging is a summary of the scenarios that are running and what scope they are running in.</span></span> <span data-ttu-id="c7999-176">자세한 내용은 [Show-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/show-csclslogging?view=skype-ps)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="c7999-176">For details, see [Show-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/show-csclslogging?view=skype-ps).</span></span>
    
3. <span data-ttu-id="c7999-177">특정 시나리오를 사용하여 현재 실행 중인 로깅 세션을 중지하려면 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="c7999-177">To stop a currently running logging session with a specific scenario, type:</span></span>
    
   ```PowerShell
   Stop-CsClsLogging -Scenario <scenario name> -Computers <comma separated list of fully qualified computer names> -Pools <comma separated list of fully qualified pool names>
   ```
   <span data-ttu-id="c7999-178">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c7999-178">For example:</span></span>
    
   ```PowerShell
   Stop-CsClsLogging -Scenario UserReplicator -Pools pool01.contoso.net
   ```

   <span data-ttu-id="c7999-179">이 명령은 pool01.contoso.net에서 UserReplicatior 시나리오를 사용한 로깅을 중지합니다.</span><span class="sxs-lookup"><span data-stu-id="c7999-179">This command will stop logging with the UserReplicatior scenario on pool01.contoso.net.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="c7999-180">UserReplicator 시나리오를 사용하여 이 로깅 세션 중에 작성되는 로그는 삭제되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c7999-180">Logs created during this logging session using the UserReplicator scenario are not deleted.</span></span> <span data-ttu-id="c7999-181">Search-CsClsLogging 명령을 사용하면 로깅에 대해 검색을 계속 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7999-181">The logging is still available for you to execute searches against using the Search-CsClsLogging command.</span></span> <span data-ttu-id="c7999-182">자세한 내용은 [Search-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/search-csclslogging?view=skype-ps)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="c7999-182">For details, see [Search-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/search-csclslogging?view=skype-ps).</span></span> 
  
<span data-ttu-id="c7999-p116">Start-CsClsLogging의 보조 명령으로 작동하는 Stop-CsClsLogging cmdlet은 시나리오에 의해 정의된 로깅 세션을 종료하고 로깅 세션에서 작성된 로그를 보관합니다. 지정된 컴퓨터에서 한 번에 두 개의 시나리오를 실행할 수 있습니다. 한 시나리오를 중지하고 다른 시나리오를 사용하여 정보를 수집하는 방법은 대부분의 작업 문제 해결 중에 수행할 수 있는 일반적인 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="c7999-p116">Acting as the companion command to Start-CsClsLogging, the Stop-CsClsLogging cmdlet ends the logging session, defined by scenarios, and retains the logs created by the logging session. You can run two scenarios on a given computer at any time. The method of stopping one scenario to gather information using another scenario is a common task that you can perform during most workload troubleshooting.</span></span>
## <a name="see-also"></a><span data-ttu-id="c7999-186">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c7999-186">See also</span></span>
<span data-ttu-id="c7999-187"><a name="stop"> </a></span><span class="sxs-lookup"><span data-stu-id="c7999-187"><a name="stop"> </a></span></span>

[<span data-ttu-id="c7999-188">비즈니스용 Skype 2015의 중앙 로깅 서비스</span><span class="sxs-lookup"><span data-stu-id="c7999-188">Centralized Logging Service in Skype for Business 2015</span></span>](centralized-logging-service.md)
