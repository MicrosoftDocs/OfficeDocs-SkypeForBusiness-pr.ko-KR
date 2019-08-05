---
title: 비즈니스용 Skype 2015에서 CLS 로그 캡처 시작 또는 중지
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 0512b9ce-7f5b-48eb-a79e-f3498bacf2de
description: '요약: 비즈니스용 Skype 서버 2015에서 중앙 집중화 된 로깅 서비스 로그 캡처 세션을 시작 하거나 중지 하는 방법에 대해 알아봅니다.'
ms.openlocfilehash: 49c36620cd58bf113ad1ce7823fcc438d88d8724
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36186798"
---
# <a name="start-or-stop-cls-log-capture-in-skype-for-business-server-2015"></a><span data-ttu-id="957be-103">비즈니스용 Skype 2015에서 CLS 로그 캡처 시작 또는 중지</span><span class="sxs-lookup"><span data-stu-id="957be-103">Start or stop CLS log capture in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="957be-104">**요약:** 비즈니스용 Skype 서버 2015에서 중앙 집중화 된 로깅 서비스 로그 캡처 세션을 시작 하거나 중지 하는 방법에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="957be-104">**Summary:** Learn how to start or stop a Centralized Logging Service log capture session in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="957be-105">중앙 로깅 서비스를 사용 하 여 추적 로그를 캡처하려면 하나 이상의 컴퓨터와 풀에 대 한 로깅을 시작 하는 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="957be-105">To capture trace logs using the Centralized Logging Service, you issue a command to begin logging on one or more computers and pools.</span></span> <span data-ttu-id="957be-106">또한 컴퓨터 또는 풀, 실행할 시나리오 (예: AlwaysOn, 미리 정의 된 다른 시나리오 또는 사용자가 만든 시나리오)를 정의 하는 매개 변수를 발행 하 고 추적에 대 한 비즈니스용 Skype 서버 구성 요소 (예: S4, SipStack)를 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="957be-106">You also issue parameters that define which computers or pools, what scenarios to run (for example, AlwaysOn, another predefined scenario, or a scenario you have created), what Skype for Business Server components (for example, S4, SipStack) to trace.</span></span>
  
<span data-ttu-id="957be-107">적절 한 정보를 캡처하려면 올바른 시나리오를 사용 하 여 문제와 관련 된 정보를 수집 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="957be-107">To capture the right information, you need to make sure you use the right scenario to collect information that is relevant to the problem.</span></span> <span data-ttu-id="957be-108">중앙 로깅 서비스에서 시나리오는 서버 구성 요소, 로깅 수준, 플래그의 컬렉션을 기준으로 로깅을 설정 하는 개념으로, 서버 단위로 이러한 요소를 정의 하는 것 보다 훨씬 더 효율적이 고 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="957be-108">In the Centralized Logging Service, a scenario is the concept of turning logging on based on a collection of server components, logging levels, and flags, which is much more efficient and useful than having to define these elements on a per-server basis.</span></span> <span data-ttu-id="957be-109">실행할 시나리오를 정의 하 고 지정 하면 시나리오가 인프라 범위의 모든 서버와 풀에서 일관 되 게 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="957be-109">You define and specify a scenario to run and the scenario is run consistently across all servers and pools in the scope of the infrastructure.</span></span>
  
<span data-ttu-id="957be-110">기본 시나리오는 **AlwaysOn**이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="957be-110">The default scenario is called **AlwaysOn**.</span></span> <span data-ttu-id="957be-111">AlwaysOn에 대 한 의도 된 용도는 시나리오 이름에 해당 하는 것 처럼 계속 해 서 시나리오를 실행 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="957be-111">The intended purpose for AlwaysOn is to run the scenario constantly, as the name of the scenario implies.</span></span> <span data-ttu-id="957be-112">AlwaysOn 시나리오는 정보 수준 정보를 수집 합니다 (정보 로깅 수준에는 대부분의 일반적인 서버 구성 요소에 대 한 정보 메시지 외에 치명적, 오류, 경고가 포함 됨).</span><span class="sxs-lookup"><span data-stu-id="957be-112">The AlwaysOn scenario collects Info level information (note that Info logging level includes Fatal, Error, and Warning in addition to Info messages) for many of the most common server components.</span></span> <span data-ttu-id="957be-113">AlwaysOn은 문제가 발생 하기 전과 후에 정보를 수집 합니다.</span><span class="sxs-lookup"><span data-stu-id="957be-113">AlwaysOn collects information before, during, and after a problem occurs.</span></span> <span data-ttu-id="957be-114">이는 OCSLogger 같은 이전 로깅 도구의 일반적인 동작과 크게 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="957be-114">This differs dramatically from the typical behavior of previous logging tools such as OCSLogger.</span></span> <span data-ttu-id="957be-115">문제가 이미 발생 한 후 OCSLogger 실행 하 여 문제를 해결 하기 위해 보유 하 고 있는 데이터는 사전 대응적인이 아니라 반응 하기 때문에 더욱 어려워집니다.</span><span class="sxs-lookup"><span data-stu-id="957be-115">You ran OCSLogger after the problem had already occurred, making your troubleshooting efforts more difficult because the data that you have is reactive, not proactive.</span></span> <span data-ttu-id="957be-116">AlwaysOn에 문제 구성 요소를 가리키기 위해 원하는 정보를 포함 하 고 있지 않은 경우 (AlwaysOn에서 공급자의 범위 및 깊이가 제공 되지 않는 경우)에는 적절 한 수준의 정보가 표시 됩니다. 새 시나리오 만들기, 다른 정보 수집, 다른 검색을 실행 하 여 중요 한 세부 정보 수집 등의 다른 작업을 수행 해야 하는 경우를 rmation.</span><span class="sxs-lookup"><span data-stu-id="957be-116">If AlwaysOn does not contain the information that you are looking for in order to point to the problem component and indicate a course of action to fix it (which is not likely given the breadth and depth of providers in AlwaysOn), it will indicate a reasonable level of information to determine what else you need to do, such as creating a new scenario, gather other information, run a different search to collect more focused details, and so on.</span></span>
  
<span data-ttu-id="957be-117">중앙 로깅 서비스에서는 두 가지 방법으로 명령을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="957be-117">The Centralized Logging Service provides two ways to issue commands.</span></span> <span data-ttu-id="957be-118">비즈니스용 Skype Server Management Shell을 통해 Windows PowerShell을 사용 하는 경우 많은 항목을 집중적으로 정사각형.</span><span class="sxs-lookup"><span data-stu-id="957be-118">A number of topics have been focused squarely on using Windows PowerShell through the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="957be-119">여러 복잡 한 구성과 명령을 사용 하는 기능은 중앙 로깅 서비스 사용을 위해 Windows PowerShell에 우선 합니다.</span><span class="sxs-lookup"><span data-stu-id="957be-119">The ability to use a number of complex configurations and commands favors Windows PowerShell for Centralized Logging Service use.</span></span> <span data-ttu-id="957be-120">비즈니스용 skype Server Management Shell을 통한 Windows PowerShell은 비즈니스용 Skype Server의 모든 기능에서 거의 동일 하 게 사용할 수 있기 때문에 Windows PowerShell 명령만 다룹니다.</span><span class="sxs-lookup"><span data-stu-id="957be-120">Because Windows PowerShell through the Skype for Business Server Management Shell is nearly ubiquitous for all functions in Skype for Business Server, only the Windows PowerShell commands are discussed.</span></span> 
  
### <a name="to-run-start-csclslogging-with-windows-powershell-using-basic-commands"></a><span data-ttu-id="957be-121">기본 명령을 사용 하 여 Windows PowerShell을 사용 하 여 시작-CsClsLogging을 실행 하려면</span><span class="sxs-lookup"><span data-stu-id="957be-121">To run Start-CsClsLogging with Windows PowerShell using basic commands</span></span>

1. <span data-ttu-id="957be-122">비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **비즈니스용 skype 2015**을 차례로 클릭 한 다음 비즈니스용 **skype Server management Shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="957be-122">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="957be-123">다음을 입력 하 여 중앙 집중화 된 로깅 서비스를 사용 하 여 로깅 시나리오를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="957be-123">Start a logging scenario with the Centralized Logging Service by typing the following:</span></span>
    
   ```
   Start-CsClsLogging -Scenario <name of scenario>
   ```

    <span data-ttu-id="957be-124">예를 들어 **AlwaysOn** 시나리오를 시작 하려면 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="957be-124">For example, to start the **AlwaysOn** scenario, type:</span></span>
    
   ```
   Start-CsClsLogging -Scenario AlwaysOn
   ```

    > [!NOTE]
    > <span data-ttu-id="957be-125">AlwaysOn 시나리오에는 기본 기간이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="957be-125">The AlwaysOn scenario has no default duration.</span></span> <span data-ttu-id="957be-126">이 시나리오는 **중지-CsClsLogging** cmdlet을 사용 하 여 명시적으로 중지할 때까지 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="957be-126">This scenario will run until you explicitly stop it with the **Stop-CsClsLogging** cmdlet.</span></span> <span data-ttu-id="957be-127">자세한 내용은 [중지-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/stop-csclslogging?view=skype-ps)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="957be-127">For details, see [Stop-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/stop-csclslogging?view=skype-ps).</span></span> <span data-ttu-id="957be-128">다른 모든 시나리오의 경우 기본 기간은 4 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="957be-128">For all other scenarios, the default duration is 4 hours.</span></span> 
  
3. <span data-ttu-id="957be-129">Enter 키를 눌러 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="957be-129">Press Enter to run the command.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="957be-130">명령을 실행 하 고 배포의 컴퓨터에서 상태를 다시 받으려면 짧은 시간 (30 ~ 60 초)이 소요 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="957be-130">It may take a short amount of time (30 to 60 seconds) for the commands to run and to receive the status back from the computers in your deployment.</span></span> 
  
     ![Start-CsClsLogging 실행.](../../media/Ops_CLS_Show_and_Start_ClsLogging.jpg)
  
4. <span data-ttu-id="957be-132">다른 시나리오를 시작 하려면 다음과 같이 실행할 추가 시나리오의 이름과 함께 **시작 CsClsLogging** cmdlet을 사용 합니다 (예: 시나리오 **인증**).</span><span class="sxs-lookup"><span data-stu-id="957be-132">To start another scenario, use the **Start-CsClsLogging** cmdlet with the name of the additional scenario to run as follows (for example, the scenario **Authentication**):</span></span>
    
   ```
   Start-CsClsLogging -Scenario Authentication
   ```

    > [!IMPORTANT]
    > <span data-ttu-id="957be-133">언제 든 지 모든 컴퓨터에서 실행 되는 두 시나리오의 총을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="957be-133">You can have a total of two scenarios running on any given computer at any time.</span></span> <span data-ttu-id="957be-134">명령이 전역 범위인 경우 배포의 모든 컴퓨터에서 시나리오를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="957be-134">If the command is global in scope, all of the computers in your deployment will run the scenario or scenarios.</span></span> <span data-ttu-id="957be-135">세 번째 시나리오를 시작 하려면 새 시나리오를 실행 하려는 컴퓨터, 풀, 사이트 또는 전역 범위에 대 한 로깅을 중지 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="957be-135">To start a third scenario, you must stop logging on the computer, pool, site, or global scope that you want to run the new scenario on.</span></span> <span data-ttu-id="957be-136">전역 범위를 시작한 경우 하나 또는 그 이상의 컴퓨터와 풀에 대해 하나 또는 둘 다에 대 한 로깅을 중지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="957be-136">If you have started a global scope, you can stop logging for one or both of the scenarios on one or more computers and pools.</span></span> 
  
### <a name="to-run-start-csclslogging-with-windows-powershell-using-advanced-commands"></a><span data-ttu-id="957be-137">고급 명령을 사용 하 여 Windows PowerShell에서 시작-CsClsLogging을 실행 하려면</span><span class="sxs-lookup"><span data-stu-id="957be-137">To run Start-CsClsLogging with Windows PowerShell using advanced commands</span></span>

1. <span data-ttu-id="957be-138">비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **비즈니스용 skype 2015**을 차례로 클릭 한 다음 비즈니스용 **skype Server management Shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="957be-138">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="957be-139">추가 매개 변수를 사용 하 여 로깅 명령을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="957be-139">Additional parameters are available to manage the logging commands.</span></span> <span data-ttu-id="957be-140">-기간을 사용 하 여 시나리오가 실행 되는 시간을 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="957be-140">You can use -Duration to adjust the length of time for the scenario to run.</span></span> <span data-ttu-id="957be-141">또한 컴퓨터, 쉼표로 구분 되는 Fqdn (정규화 된 도메인 이름) 목록, 로깅을 실행 하려는 풀에 대 한 쉼표로 구분 된 Fqdn 목록 등을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="957be-141">You also can define -Computers, a list of computer fully qualified domain names (FQDNs) separated by a comma, or -Pools, a comma separated list of FQDNs for pools that you want to run logging on.</span></span>
    
    <span data-ttu-id="957be-142">"Pool01.contoso.net" 풀의 UserReplicator 시나리오에 대 한 로깅 세션을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="957be-142">You start a logging session for the UserReplicator scenario on the pool "pool01.contoso.net".</span></span> <span data-ttu-id="957be-143">또한 로깅 세션의 기간을 8 시간으로 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="957be-143">You also define the duration of the logging session at 8 hours.</span></span> <span data-ttu-id="957be-144">이렇게 하려면 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="957be-144">To do this, type:</span></span>
    
   ```
   Start-CsClsLogging -Scenario UserReplicator -Duration 8:00 -Pools "pool01.contoso.net"
   ```

    <span data-ttu-id="957be-145">이 시나리오를 성공적으로 실행 하면 다음과 같은 결과가 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="957be-145">The successful execution of this scenario returns a result like the following:</span></span>
    
     ![Start-CsClsLogging 실행.](../../media/Ops_CsClsLogging_UserReplicator_Exp.jpg)
  
<span data-ttu-id="957be-147">이 예제에서는 AlwaysOn 시나리오가 실행 중이 고 UserReplicator 시나리오가 실행 되 고 있는 것을 참고 하세요.</span><span class="sxs-lookup"><span data-stu-id="957be-147">Note that in this example, the AlwaysOn scenario is running and the UserReplicator scenario is running.</span></span> 
    
## <a name="stop-the-centralized-logging-service-log-capture"></a><span data-ttu-id="957be-148">중앙 로깅 서비스 로그 캡처 중지</span><span class="sxs-lookup"><span data-stu-id="957be-148">Stop the Centralized Logging Service log capture</span></span>
<span data-ttu-id="957be-149"><a name="stop"> </a></span><span class="sxs-lookup"><span data-stu-id="957be-149"></span></span>

<span data-ttu-id="957be-150">중지-CsClsLogging cmdlet을 사용 하 여 현재 실행 중인 로깅 세션을 중지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="957be-150">You can stop a currently running logging session with the Stop-CsClsLogging cmdlet.</span></span> <span data-ttu-id="957be-151">일반적으로 로깅 세션을 중지 해야 하는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="957be-151">Generally, there aren't many situations in which you would need to stop a logging session.</span></span> <span data-ttu-id="957be-152">예를 들어 로깅을 중지 하지 않고 로그를 검색 하 고 구성을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="957be-152">For example, you can search logs and change configurations without first needing to stop logging.</span></span> <span data-ttu-id="957be-153">AlwaysOn 및 UserReplicator와 같은 두 가지 시나리오를 실행 하는 경우 인증과 관련 된 정보를 수집 해야 하는 경우에는 실행을 시작 하기 전에 전역, 사이트, 풀 또는 컴퓨터 범위에서 다른 시나리오 중 하나를 중지 해야 합니다. 인증 시나리오.</span><span class="sxs-lookup"><span data-stu-id="957be-153">If you have two scenarios running, for example AlwaysOn and UserReplicator, and you need to collect information related to Authentication, you will need to stop one of the other scenarios (at a global, site, pool or computer scope) before you can start running to Authentication scenario.</span></span> <span data-ttu-id="957be-154">자세한 내용은 [중지-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/stop-csclslogging?view=skype-ps)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="957be-154">For details, see [Stop-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/stop-csclslogging?view=skype-ps).</span></span>
  
> [!NOTE]
> <span data-ttu-id="957be-155">지정 된 배포, 풀 또는 컴퓨터에서 실행할 수 있는 시나리오를 결정할 때는 **컴퓨터당**및 사용자 지정 시나리오 하나에 대해 두 가지 시나리오를 실행 하는 것으로 제한 된다는 점에 유의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="957be-155">When determining what scenarios you can run on a given deployment, pool or computer, you need to remember that you are limited to running two scenarios **per computer**: AlwaysOn and one custom scenario.</span></span> <span data-ttu-id="957be-156">풀에서 활동을 로깅하는 경우 풀을 단일 엔터티로 처리 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="957be-156">If you are logging activity on a pool, you should treat a pool as a single entity.</span></span> <span data-ttu-id="957be-157">대부분의 경우 풀의 각 컴퓨터에서 서로 다른 시나리오를 실행 하는 것은 적절 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="957be-157">In most cases, it would not make sense to run different scenarios on each computer in a pool.</span></span> <span data-ttu-id="957be-158">전체 배포에서 지정 된 컴퓨터에 가장 적합 한 시나리오를 고려 하 여 데이터를 수집 하는 문제를 확인 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="957be-158">It does make sense to look at the problem that you are collecting data about and think about what scenario makes the most sense on a given computer in the overall deployment.</span></span> <span data-ttu-id="957be-159">예를 들어 UserReplicator 시나리오를 고려 하는 경우 Edge 서버 또는 Edge 풀에서 UserReplicator를 실행 하는 데는 매우 적은 값이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="957be-159">For example, if you consider the UserReplicator scenario, there would be very little value in running UserReplicator on an Edge Server or Edge pool.</span></span> 
  
<span data-ttu-id="957be-160">문제와 영향의 범위를 파악 한 후에는 컴퓨터와 풀에 대해 실행할 시나리오를 신중 하 게 선택 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="957be-160">After you understand the problem and the scope of the impact, you should make careful choices about what scenarios to run on which computers and pools.</span></span> <span data-ttu-id="957be-161">AlwaysOn 시나리오는 광범위 한 공급자에 대 한 정보를 수집 하 고, 특정 시나리오는 특정 컴퓨터 또는 풀에 대 한 응용 프로그램 값만 가지 므로 폭넓은 범위 응용 프로그램에 의미가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="957be-161">While the AlwaysOn scenario makes sense for a wide scope application because it collects information on a wide variety of providers, specific scenarios only have application value on specific computers or pools.</span></span> <span data-ttu-id="957be-162">또한 특정 시나리오의 값을 먼저 이해 하지 않고 로깅 세션을 임의로 시작 하는 경우 주의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="957be-162">Also, you should take caution when randomly starting up a logging session without first understanding the value of a given scenario.</span></span> <span data-ttu-id="957be-163">잘못 된 시나리오를 사용 하거나 작업에 적합 한 시나리오를 사용 하 고 잘못 된 범위 (전역, 사이트, 풀 또는 컴퓨터 일 수 있음)에 시나리오를 적용 하는 경우 시나리오를 전혀 실행 하지 않은 것 처럼 중요 하지 않은 데이터를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="957be-163">If you use the wrong scenario, or if you use a scenario that is appropriate for the task and you apply the scenario at the wrong scope (be it global, site, pool, or computer), you can get questionable data that is not very useful—as if you didn't run the scenario at all.</span></span>
  
<span data-ttu-id="957be-164">비즈니스용 Skype Server Management Shell을 사용 하 여 중앙 집중화 된 로깅 서비스 기능을 제어 하려면 CsAdministrator 또는 CsServerAdministrator 역할 기반 액세스 제어 (RBAC) 보안 그룹 또는 사용자 지정 RBAC 역할 중 하나의 구성원 이어야 합니다. 이러한 두 그룹 중 하나가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="957be-164">To control the Centralized Logging Service functions by using the Skype for Business Server Management Shell, you must be a member of either the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> <span data-ttu-id="957be-165">이 cmdlet이 할당 된 모든 RBAC 역할 목록 (직접 만든 사용자 지정 RBAC 역할 포함)을 반환 하려면 비즈니스용 Skype Server 관리 셸 또는 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="957be-165">To return a list of all the RBAC roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Skype for Business Server Management Shell or the Windows PowerShell prompt:</span></span>
  
```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Skype for Business Server 2015 cmdlet"}
```

<span data-ttu-id="957be-166">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="957be-166">For example:</span></span>
  
```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

> [!NOTE]
> <span data-ttu-id="957be-167">이제 로깅이 설정 되었고 로그가 어디에 보관 되는지 궁금할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="957be-167">So you may be wondering: Now that you've enabled logging, where are the logs kept?</span></span> <span data-ttu-id="957be-168">CLS 에이전트로 전송 되는 관리 셸 쿼리를 사용 하 여 로그에 저장 된 정보에 액세스 하 고, 각 서버에서 CLS 에이전트가 해당 레코드를 유지 하는 데 실제로 중요 하지 않은 여러 가지 파일 형식으로 결과를 출력할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="957be-168">Since you'll access the information stored in the logs using management shell queries sent to the CLS Agents, and you can output the results to several possible file formats, where on each server a CLS Agent keeps its records isn't actually important to know.</span></span>  <span data-ttu-id="957be-169">로그 파일은 **Snooper** 등의 다양 한 도구를 사용 하 여 사용자가 지정 하 고 읽고 분석 한 위치에 저장할 수 있습니다 (예: **notepad.exe**와 같은 텍스트 파일을 읽을 수 있는 도구).</span><span class="sxs-lookup"><span data-stu-id="957be-169">The log files can be saved to a location you specify and  read and analyzed using a variety of tools, including **Snooper.exe** and any tool that can read a text file, such as **Notepad.exe**.</span></span> <span data-ttu-id="957be-170">Snooper는 비즈니스용 Skype 서버 2015 디버그 도구의 일부 이며 [웹 다운로드](https://go.microsoft.com/fwlink/p/?LinkId=285257)로 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="957be-170">Snooper.exe is part of the Skype for Business Server 2015 Debug Tools and is available as a [Web download](https://go.microsoft.com/fwlink/p/?LinkId=285257).</span></span>

### <a name="to-stop-a-currently-running-centralized-logging-service-session"></a><span data-ttu-id="957be-171">현재 실행 중인 중앙 집중화 된 로깅 서비스 세션을 중지 하려면</span><span class="sxs-lookup"><span data-stu-id="957be-171">To stop a currently running Centralized Logging Service session</span></span>

1. <span data-ttu-id="957be-172">비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **비즈니스용 skype 2015**을 차례로 클릭 한 다음 비즈니스용 **skype Server management Shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="957be-172">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="957be-173">중앙 로깅 서비스를 쿼리하여 다음을 입력 하 여 현재 실행 중인 시나리오를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="957be-173">Query the Centralized Logging Service to find out what scenarios are currently running by typing the following:</span></span>
    
   ```
   Show-CsClsLogging
   ```

   ![Show-CsCl 호출 후의 Windows PowerShell 콘솔](../../media/Ops_Show_Stop_CsClsLogging.jpg)
  
   <span data-ttu-id="957be-175">Show-CsClsLogging 결과는 실행 중인 시나리오 및 실행 중인 범위에 대 한 요약입니다.</span><span class="sxs-lookup"><span data-stu-id="957be-175">The result of Show-CsClsLogging is a summary of the scenarios that are running and what scope they are running in.</span></span> <span data-ttu-id="957be-176">자세한 내용은 [-CsClsLogging 표시](https://docs.microsoft.com/powershell/module/skype/show-csclslogging?view=skype-ps)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="957be-176">For details, see [Show-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/show-csclslogging?view=skype-ps).</span></span>
    
3. <span data-ttu-id="957be-177">특정 시나리오에서 현재 실행 중인 로깅 세션을 중지 하려면 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="957be-177">To stop a currently running logging session with a specific scenario, type:</span></span>
    
   ```
   Stop-CsClsLogging -Scenario <scenario name> -Computers <comma separated list of fully qualified computer names> -Pools <comma separated list of fully qualified pool names>
   ```
   <span data-ttu-id="957be-178">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="957be-178">For example:</span></span>
    
   ```
   Stop-CsClsLogging -Scenario UserReplicator -Pools pool01.contoso.net
   ```

   <span data-ttu-id="957be-179">이 명령은 pool01.contoso.net에서 UserReplicatior 시나리오에 대 한 로깅을 중지 합니다.</span><span class="sxs-lookup"><span data-stu-id="957be-179">This command will stop logging with the UserReplicatior scenario on pool01.contoso.net.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="957be-180">UserReplicator 시나리오를 사용 하 여이 로깅 세션 중에 만든 로그는 삭제 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="957be-180">Logs created during this logging session using the UserReplicator scenario are not deleted.</span></span> <span data-ttu-id="957be-181">검색-CsClsLogging 명령을 사용 하 여 검색을 실행 하는 데에도 로깅을 계속 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="957be-181">The logging is still available for you to execute searches against using the Search-CsClsLogging command.</span></span> <span data-ttu-id="957be-182">자세한 내용은 [검색-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/search-csclslogging?view=skype-ps)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="957be-182">For details, see [Search-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/search-csclslogging?view=skype-ps).</span></span> 
  
<span data-ttu-id="957be-183">자매-CsClsLogging을 시작 하는 데 도우미 명령으로 작동 하는 경우 CsClsLogging cmdlet은 시나리오에 정의 된 로깅 세션을 종료 하 고 로깅 세션에서 만든 로그를 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="957be-183">Acting as the companion command to Start-CsClsLogging, the Stop-CsClsLogging cmdlet ends the logging session, defined by scenarios, and retains the logs created by the logging session.</span></span> <span data-ttu-id="957be-184">언제 든 지 지정 된 컴퓨터에서 두 가지 시나리오를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="957be-184">You can run two scenarios on a given computer at any time.</span></span> <span data-ttu-id="957be-185">다른 시나리오를 사용 하 여 정보를 수집 하기 위해 한 시나리오를 중지 하는 방법은 대부분의 작업 부하 문제 해결 중에 수행할 수 있는 일반적인 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="957be-185">The method of stopping one scenario to gather information using another scenario is a common task that you can perform during most workload troubleshooting.</span></span>
## <a name="see-also"></a><span data-ttu-id="957be-186">참고 항목</span><span class="sxs-lookup"><span data-stu-id="957be-186">See also</span></span>
<span data-ttu-id="957be-187"><a name="stop"> </a></span><span class="sxs-lookup"><span data-stu-id="957be-187"></span></span>

[<span data-ttu-id="957be-188">비즈니스용 Skype 2015의 중앙 로깅 서비스</span><span class="sxs-lookup"><span data-stu-id="957be-188">Centralized Logging Service in Skype for Business 2015</span></span>](centralized-logging-service.md)
