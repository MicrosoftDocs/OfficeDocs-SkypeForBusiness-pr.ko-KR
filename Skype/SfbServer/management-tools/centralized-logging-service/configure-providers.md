---
title: 비즈니스용 Skype 서버에서 중앙 로깅 서비스에 대한 공급자 구성
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
ms.assetid: 6a197ecf-b56b-45e0-8e7c-f532ec5164ff
description: '요약: 비즈니스용 Skype 서버 2015에서 중앙 로깅 서비스에 대한 시나리오 공급자를 구성하는 방법을 설명합니다.'
ms.openlocfilehash: cd0364d6497aa53d258b5346090d6cdd7c338cc3
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51098854"
---
# <a name="configure-providers-for-centralized-logging-service-in-skype-for-business-server-2015"></a><span data-ttu-id="b9370-103">비즈니스용 Skype 서버에서 중앙 로깅 서비스에 대한 공급자 구성</span><span class="sxs-lookup"><span data-stu-id="b9370-103">Configure providers for Centralized Logging Service in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="b9370-104">**요약:** 비즈니스용 Skype 서버 2015에서 중앙 로깅 서비스에 대한 시나리오 공급자를 구성하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b9370-104">**Summary:** Learn how to configure scenario providers for the Centralized Logging Service in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="b9370-105">중앙 로깅 서비스의 공급자 개념 및 구성은 파악하는 데 가장 중요한 요소 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="b9370-105">The concepts and configuration of providers in Centralized Logging Service is one of the most important to grasp.</span></span> <span data-ttu-id="b9370-106">이러한 구성 요소는 비즈니스용 Skype 서버 추적 모델의 비즈니스용 Skype 서버 서버 역할 구성 요소에 직접 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="b9370-106">Theproviders map directly to Skype for Business Server server role components in the Skype for Business Server tracing model.</span></span> <span data-ttu-id="b9370-107">공급자는 추적할 비즈니스용 Skype 서버 2015의 구성 요소, 수집할 메시지 유형(예: 치명적, 오류 또는 경고) 및 플래그(예: TF_Connection 또는 TF_Diag)를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="b9370-107">The provider defines the components of a Skype for Business Server 2015 that will be traced, the type of messages (for example, fatal, error, or warning) to collect, and the flags (for example, TF_Connection or TF_Diag).</span></span> <span data-ttu-id="b9370-108">공급자는 각 비즈니스용 Skype 서버 서버 역할의 추적 가능한 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="b9370-108">Providers are the traceable components in each Skype for Business Server server role.</span></span> <span data-ttu-id="b9370-109">공급자를 사용하여 구성 요소에 대한 추적 수준 및 유형(예: S4, SIPStack, IM 및 현재 상태)을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="b9370-109">By using providers, you define the level and type of tracing on components (for example, S4, SIPStack, IM and Presence).</span></span> <span data-ttu-id="b9370-110">정의된 공급자는 특정 문제 조건을 해결하는 특정 논리 컬렉션에 대한 모든 공급자를 그룹화하는 시나리오에서 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b9370-110">The defined provider is used in a scenario to group all of the providers for a given logical collection that address a specific problem condition.</span></span>
  
<span data-ttu-id="b9370-111">비즈니스용 Skype 서버 관리 셸을 사용하여 중앙 로깅 서비스 기능을 실행하려면 CsAdministrator 또는 CsServerAdministrator RBAC(역할 기반 액세스 제어) 보안 그룹 또는 이러한 두 그룹 중 하나를 포함하는 사용자 지정 RBAC 역할의 구성원이 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9370-111">To run the Centralized Logging Service functions using the Skype for Business Server Management Shell, you must be a member of either the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> <span data-ttu-id="b9370-112">직접 만든 사용자 지정 RBAC(역할 기반 액세스 제어) 역할을 포함하여 이 cmdlet이 할당된 모든 RBAC 역할의 목록을 반환하기 위해 비즈니스용 Skype 서버 관리 셸 또는 Windows PowerShell 프롬프트에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="b9370-112">To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Skype for Business Server Management Shell or the Windows PowerShell prompt:</span></span>
  
```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Skype for Business Server 2015 cmdlet"}
```

<span data-ttu-id="b9370-113">예:</span><span class="sxs-lookup"><span data-stu-id="b9370-113">For example:</span></span>
  
```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

<span data-ttu-id="b9370-114">이 항목의 나머지에서는 문제 해결을 최적화하기 위해 공급자를 정의하고 공급자를 수정하는 방법 및 공급자 정의에 포함된 항목을 중점적으로 다합니다.</span><span class="sxs-lookup"><span data-stu-id="b9370-114">The remainder of this topic focuses on how to define providers, modify a provider and what a provider definition contains to optimize your troubleshooting.</span></span> <span data-ttu-id="b9370-115">중앙 로깅 서비스 명령을 발급하는 방법에는 두 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9370-115">There are two ways to issue Centralized Logging Service commands.</span></span> <span data-ttu-id="b9370-116">기본적으로 C:\Program Files\Common Files\Skype for Business Server 2015\CLSAgent 디렉터리에 있는 CLSController.exe 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9370-116">You can use the CLSController.exe that is located, by default, in the directory C:\Program Files\Common Files\Skype for Business Server 2015\CLSAgent.</span></span> <span data-ttu-id="b9370-117">또는 비즈니스용 Skype 서버 관리 셸을 사용하여 Windows PowerShell 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9370-117">Or, you can use the Skype for Business Server Management Shell to issue Windows PowerShell commands.</span></span> <span data-ttu-id="b9370-118">이 Windows PowerShell 사용하여 로깅 세션에서 사용할 새 공급자를 정의하고 생성, 수집한 데이터 및 데이터를 수집하는 수준에 대한 모든 제어를 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9370-118">By using Windows PowerShell, you can define new providers for use in your logging sessions, and have complete control over their creation, what they collect, and at what level they collect data.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="b9370-119">앞서 언급한 것 처럼 공급자는 매우 강력합니다.</span><span class="sxs-lookup"><span data-stu-id="b9370-119">As mentioned, providers are very powerful.</span></span> <span data-ttu-id="b9370-120">그러나 시나리오는 공급자가 나타내는 구성 요소에 대해 추적을 설정하고 실행하는 데 필요한 모든 정보를 포함하기 때문에 더욱 강력합니다.</span><span class="sxs-lookup"><span data-stu-id="b9370-120">However, scenarios are more powerful because they contain the embodiment of all information needed to set and execute tracing on the components that the providers represent.</span></span> <span data-ttu-id="b9370-121">시나리오가 공급자 모음이 되는 경우 명령줄에서 수백 개의 명령을 실행하는 작업과 동시에 수백 개의 명령을 수집하는 명령이 포함된 배치 파일을 실행하는 경우와 느슨하게 비교할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9370-121">With scenarios being a collection of providers, this could be loosely compared to running a batch file containing hundreds of commands to collect a lot of information versus issuing hundreds of commands, one at a time, at the command line.</span></span> 
  
<span data-ttu-id="b9370-122">중앙 로깅 서비스는 공급자의 세부 정보를 자세히 조사하도록 요구하는 대신 이미 정의된 다양한 시나리오를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b9370-122">Instead of requiring you to dig deeply into the details of providers, the Centralized Logging Service provides a number of scenarios that are already defined for you.</span></span> <span data-ttu-id="b9370-123">제공된 시나리오에서는 발생할 수 있는 대부분의 문제를 다 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b9370-123">The provided scenarios cover the vast majority of possible issues that you will encounter.</span></span> <span data-ttu-id="b9370-124">드문 경우지만 공급자를 만들고 정의하여 시나리오에 할당해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9370-124">In rare cases, you may need to create and define providers and assign them to scenarios.</span></span> <span data-ttu-id="b9370-125">새 공급자 및 시나리오를 만들어야 하는 필요성을 조사하기 전에 제공된 각 시나리오를 익히는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="b9370-125">We strongly recommend that you become familiar with each of the scenarios provided before you investigate the need to create new providers and scenarios.</span></span> <span data-ttu-id="b9370-126">시나리오에서 공급자 요소를 사용하여 추적 정보를 수집하는 방법을 익숙해지기 위해 공급자를 만드는 방법에 대한 정보가 여기에 설명된 반면, 현재는 공급자 자체에 대한 세부 정보가 제공되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b9370-126">While information about creating providers is found here to familiarize you with how the scenarios use the provider elements to collect trace information, details on the providers themselves are not provided at this time.</span></span> 
  
<span data-ttu-id="b9370-127">비즈니스용 [Skype 2015의](centralized-logging-service.md)중앙 로깅 서비스에 도입된 시나리오에서 사용할 공급자를 정의하는 주요 요소는 다음입니다.</span><span class="sxs-lookup"><span data-stu-id="b9370-127">Introduced in [Centralized Logging Service in Skype for Business 2015](centralized-logging-service.md), the key elements of defining a provider for use in a scenario are:</span></span>
  
- <span data-ttu-id="b9370-128">**공급자** OCSLogger에 익숙한 경우 공급자는 추적 엔진이 로그를 수집할지 OCSLogger에 알려 주기 위해 선택하는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="b9370-128">**Providers** If you are familiar with OCSLogger, providers are the components that you choose to tell OCSLogger what the tracing engine should collect logs from.</span></span> <span data-ttu-id="b9370-129">공급자는 동일한 구성 요소로, 대부분의 경우 OCSLogger의 구성 요소와 이름이 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b9370-129">The providers are the same components, and in many cases have the same name as the components in OCSLogger.</span></span> <span data-ttu-id="b9370-130">OCSLogger에 익숙하지 않은 경우 공급자는 중앙 로깅 서비스에서 로그를 수집할 수 있는 서버 역할별 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="b9370-130">If you are not familiar with OCSLogger, providers are server-role specific components that the Centralized Logging Service can collect logs from.</span></span> <span data-ttu-id="b9370-131">중앙 로깅 서비스의 경우 CLSAgent는 공급자 구성에서 정의한 구성 요소의 추적을 수행하고 있는 중앙 로깅 서비스의 아키텍처 부분입니다.</span><span class="sxs-lookup"><span data-stu-id="b9370-131">In the case of the Centralized Logging Service, the CLSAgent is the architectural part of the Centralized Logging Service that is doing the tracing of the components that you define in the providers configuration.</span></span>
    
- <span data-ttu-id="b9370-132">**로깅 수준** OCSLogger는 수집된 데이터에 대한 다양한 세부 정보를 선택할 수 있는 옵션을 제공했습니다.</span><span class="sxs-lookup"><span data-stu-id="b9370-132">**Logging levels** OCSLogger provided the option to choose a number of levels of detail for the data collected.</span></span> <span data-ttu-id="b9370-133">이 기능은 중앙 로깅 서비스 및 시나리오의 핵심 부분으로, **Type** 매개 변수에 의해 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="b9370-133">This feature is an integral part of the Centralized Logging Service and scenarios, and is defined by the **Type** parameter.</span></span> <span data-ttu-id="b9370-134">다음 중에서 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9370-134">You can choose from the following:</span></span>
    
  - <span data-ttu-id="b9370-135">**모두** 정의된 공급자에 대한 로그에 치명적, 오류, 경고, 자세한 정보 및 디버그 정보 유형의 추적 메시지를 수집합니다.</span><span class="sxs-lookup"><span data-stu-id="b9370-135">**All** Collects trace messages of type fatal, error, warning, verbose, and debug info to the log for the defined provider.</span></span>
    
  - <span data-ttu-id="b9370-136">**치명적** "Fatal"으로 정의된 추적 메시지만 수집합니다.</span><span class="sxs-lookup"><span data-stu-id="b9370-136">**Fatal** Collects only the trace messages defined as "Fatal."</span></span>
    
  - <span data-ttu-id="b9370-137">**오류** "오류" 또는 "치명적"으로 정의된 추적 메시지만 수집합니다.</span><span class="sxs-lookup"><span data-stu-id="b9370-137">**Error** Collects only the trace messages defined as "Error" or "Fatal."</span></span>
    
  - <span data-ttu-id="b9370-138">**경고** "경고", "오류" 및 "치명적" 유형의 추적 메시지만 수집합니다.</span><span class="sxs-lookup"><span data-stu-id="b9370-138">**Warning** Collects only the trace messages of type "Warning," "Error" and "Fatal."</span></span>
    
  - <span data-ttu-id="b9370-139">**정보** 정의된 공급자에 대한 정보 메시지를 나타내는 추적 메시지와 치명적, 오류 및 경고 메시지만 수집합니다.</span><span class="sxs-lookup"><span data-stu-id="b9370-139">**Info** Collects only the trace messages that indicate an informational message for the defined provider, plus fatal, error, and warning messages.</span></span>
    
  - <span data-ttu-id="b9370-140">**Verbose** 정의된 공급자에 대해 치명적, 오류, 경고 및 자세한 정보 유형의 추적 메시지를 모두 수집합니다.</span><span class="sxs-lookup"><span data-stu-id="b9370-140">**Verbose** Collects all trace messages of type fatal, error, warning and verbose for the defined provider.</span></span>
    
  - <span data-ttu-id="b9370-141">**디버그는** 기본적으로 '모두'에 해당합니다. 정의된 공급자에 대한 Fatal, Error, Warning, Info, Verbose 및 Debug 유형의 추적을 수집합니다.</span><span class="sxs-lookup"><span data-stu-id="b9370-141">**Debug** this is essentially an equivalent of 'All' - collects traces of type Fatal, Error, Warning, Info, Verbose and Debug for the defined provider.</span></span>
    
- <span data-ttu-id="b9370-142">**플래그** OCSLogger는 추적 파일에서 검색할 수 있는 정보 유형을 정의한 각 공급자에 대해 플래그를 선택하는 옵션을 제공했습니다.</span><span class="sxs-lookup"><span data-stu-id="b9370-142">**Flags** OCSLogger provided the option to choose flags for each provider that defined what type of information you could retrieve from the trace files.</span></span> <span data-ttu-id="b9370-143">공급자에 따라 다음 플래그를 선택 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9370-143">You can chose the following flags, based on the provider:</span></span>
    
  - <span data-ttu-id="b9370-144">**TF_Connection** 연결 관련 로그 항목을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b9370-144">**TF_Connection** Provides connection-related log entries.</span></span> <span data-ttu-id="b9370-145">이러한 로그에는 특정 구성 요소와의 연결에 대한 정보가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="b9370-145">These logs include information about connections established to and from a particular component.</span></span> <span data-ttu-id="b9370-146">여기에는 중요한 네트워크 수준 정보(즉, 연결 개념이 없는 구성 요소의 경우)도 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="b9370-146">This may also include significant network-level information (that is, for components without the concept of a connection).</span></span>
    
  - <span data-ttu-id="b9370-147">**TF_Security** 보안과 관련된 모든 이벤트/로그 항목을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b9370-147">**TF_Security** Provides all events/log entries related to security.</span></span> <span data-ttu-id="b9370-148">예를 들어 SipStack의 경우 이러한 이벤트는 도메인 유효성 검사 실패, 클라이언트 인증/권한 부여 오류와 같은 보안 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="b9370-148">For example, for SipStack, these are security events such as domain validation failure, and client authentication/authorization failures.</span></span>
    
  - <span data-ttu-id="b9370-149">**TF_Diag** 구성 요소를 진단하거나 문제를 해결하는 데 사용할 수 있는 진단 이벤트를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b9370-149">**TF_Diag** Provides diagnostics events that you can use to diagnose or troubleshoot the component.</span></span> <span data-ttu-id="b9370-150">예를 들어 SipStack의 경우 인증서 오류 또는 DNS 경고/오류입니다.</span><span class="sxs-lookup"><span data-stu-id="b9370-150">For example, for SipStack, these are certificate failures, or DNS warnings/errors.</span></span>
    
  - <span data-ttu-id="b9370-151">**TF_Protocol** SIP 및 결합 커뮤니티 코덱 팩 메시지와 같은 프로토콜 메시지를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b9370-151">**TF_Protocol** Provides protocol messages such as SIP and Combined Community Codec Pack messages.</span></span>
    
  - <span data-ttu-id="b9370-152">**TF_Component** 공급자의 일부로 지정된 구성 요소에 대한 로깅을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="b9370-152">**TF_Component** Enables logging on the components specified as part of the providers.</span></span>
    
  - <span data-ttu-id="b9370-153">**모두** 공급자에 사용할 수 있는 모든 플래그를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="b9370-153">**All** Sets all available flags available for the provider.</span></span>
    
### <a name="to-review-information-about-existing-centralized-logging-service-scenario-providers"></a><span data-ttu-id="b9370-154">기존 중앙 로깅 서비스 시나리오 공급자에 대한 정보를 검토하기 위해</span><span class="sxs-lookup"><span data-stu-id="b9370-154">To review information about existing Centralized Logging Service scenario providers</span></span>

1. <span data-ttu-id="b9370-155">비즈니스용 Skype 서버 관리 셸 시작: **시작,** 모든 **프로그램,** 비즈니스용 **Skype 2015,** 비즈니스용 Skype 서버 관리 셸을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="b9370-155">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="b9370-156">기존 공급자의 구성을 검토하려면 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="b9370-156">To review the configuration of existing providers, type the following:</span></span>
    
   ```PowerShell
   Get-CsClsScenario -Identity <scope and scenario name>
   ```

    <span data-ttu-id="b9370-157">예를 들어 전역 회의 참석자에 대한 정보를 검토하기 위해 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="b9370-157">For example, to review information about the global conferencing attendant, type:</span></span>
    
   ```PowerShell
   Get-CsClsScenario -Identity "global/CAA"
   ```

    <span data-ttu-id="b9370-158">이 명령은 연결된 플래그, 설정 및 구성 요소가 있는 공급자 목록을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="b9370-158">The command displays a list of providers with the associated flags, settings, and components.</span></span> <span data-ttu-id="b9370-159">표시되는 정보가 충분하지 않은 경우 목록이 기본 Windows PowerShell 너무 길면 다른 출력 방법을 정의하여 추가 정보를 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9370-159">If the information displayed is not enough or the list is too long for the default Windows PowerShell list format, you can display additional information by defining a different output method.</span></span> <span data-ttu-id="b9370-160">이렇게 하려면 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="b9370-160">To do this, type:</span></span>
    
   ```PowerShell
   Get-CsClsScenario -Identity "global/CAA" | Select-Object -ExpandProperty Provider
   ```

    <span data-ttu-id="b9370-161">이 명령의 출력은 공급자 이름, 로깅 유형, 로깅 수준, 플래그, GUID 및 역할이 각각 별도의 줄에 있는 5줄 형식으로 표시되는 각 공급자를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="b9370-161">The output of this command displays each provider displayed in a five line format with the provider name, type of logging, logging level, flags, GUID, and role, each one on a separate line.</span></span> 
    
### <a name="to-define-a-new-centralized-logging-service-scenario-provider"></a><span data-ttu-id="b9370-162">새 중앙 로깅 서비스 시나리오 공급자를 정의하는 경우</span><span class="sxs-lookup"><span data-stu-id="b9370-162">To define a new Centralized Logging Service scenario provider</span></span>

1. <span data-ttu-id="b9370-163">비즈니스용 Skype 서버 관리 셸 시작: **시작,** 모든 **프로그램,** 비즈니스용 **Skype 2015,** 비즈니스용 Skype 서버 관리 셸을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="b9370-163">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="b9370-164">시나리오 공급자는 추적할 구성 요소, 사용할 플래그 및 수집할 세부 정보 수준으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="b9370-164">A scenario provider consists of a component to trace, flags to use, and a level of detail to collect.</span></span> <span data-ttu-id="b9370-165">다음을 입력하여 이 작업을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9370-165">You do this by typing:</span></span>
    
   ```PowerShell
   $<variableName> = New-CsClsProvider -Name <provider component> -Type <log type> -Level <log level detail type> -Flags <provider trace log flags>
   ```

    <span data-ttu-id="b9370-166">예를 들어 수집할 내용과 Lyss 공급자의 세부 정보 수준을 정의하는 추적 공급자 정의는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b9370-166">For example, a trace provider definition that defines what to collect and to what level of detail from the Lyss provider looks like the following:</span></span>
    
   ```PowerShell
   $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Info" -Flags "All"
   ```

<span data-ttu-id="b9370-167">-Level은 치명적인 오류, 경고 및 정보 메시지를 수집합니다.</span><span class="sxs-lookup"><span data-stu-id="b9370-167">The -Level collects fatal, error, warning, and information messages.</span></span> <span data-ttu-id="b9370-168">사용되는 플래그는 Lyss 공급자에 대해 정의된 모든 플래그로 TF_Connection, TF_Diag 및 TF_Protocol.변수 $LyssProvider 정의한 후 **New-CsClsScenario** cmdlet과 함께 사용하여 Lyss 공급자에서 추적을 수집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9370-168">The flags used are all of those defined for the Lyss provider, and include TF_Connection, TF_Diag and TF_Protocol.After the variable $LyssProvider is defined, you can use it with the **New-CsClsScenario** cmdlet to collect traces from the Lyss provider.</span></span> <span data-ttu-id="b9370-169">공급자 만들기 및 새 시나리오에 대한 공급자 할당을 완료하기 위해 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="b9370-169">To complete the creation and assignment of the provider to a new scenario, type:</span></span>

```PowerShell
New-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider $LyssProvider
```

<span data-ttu-id="b9370-170">여기서 $LyssProvider 는 **New-CsClsProvider로** 만든 정의된 시나리오가 포함된 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="b9370-170">Where $LyssProvider is the variable containing the defined scenario created with **New-CsClsProvider**.</span></span>
### <a name="to-change-an-existing-centralized-logging-service-scenario-provider"></a><span data-ttu-id="b9370-171">기존 중앙 로깅 서비스 시나리오 공급자를 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="b9370-171">To change an existing Centralized Logging Service scenario provider</span></span>

1. <span data-ttu-id="b9370-172">비즈니스용 Skype 서버 관리 셸 시작: **시작,** 모든 **프로그램,** 비즈니스용 **Skype 2015,** 비즈니스용 Skype 서버 관리 셸을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="b9370-172">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="b9370-173">기존 공급자의 구성을 업데이트하거나 변경하려면 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="b9370-173">To update or change the configuration of an existing provider, type:</span></span>
    
   ```PowerShell
   $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Debug" -Flags "TF_Connection, TF_Diag"
   ```

    <span data-ttu-id="b9370-174">그런 다음 다음을 입력하여 공급자를 할당하는 시나리오를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="b9370-174">You then update the scenario to assign the provider by typing the following:</span></span>
    
   ```PowerShell
   Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider $LyssProvider
   ```

<span data-ttu-id="b9370-175">명령의 최종 결과는 시나리오 site:Redmond/RedmondLyssInfo에 할당된 공급자에 대한 플래그 및 수준이 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="b9370-175">The end result of the command is that the scenario site:Redmond/RedmondLyssInfo will have updated flags and level for the provider assigned to it.</span></span> <span data-ttu-id="b9370-176">Get-CsClsScenario를 사용하여 새 시나리오를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9370-176">You can view the new scenario by using Get-CsClsScenario.</span></span> <span data-ttu-id="b9370-177">자세한 내용은 [Get-CsClsScenario를 참조합니다.](/powershell/module/skype/get-csclsscenario?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="b9370-177">For details, see [Get-CsClsScenario](/powershell/module/skype/get-csclsscenario?view=skype-ps).</span></span>
> [!CAUTION]
> <span data-ttu-id="b9370-178">**New-ClsCsProvider는** 플래그가 유효한지 여부를 확인하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b9370-178">**New-ClsCsProvider** does not check to determine whether the flags are valid.</span></span> <span data-ttu-id="b9370-179">플래그의 맞춤법(예: TF_DIAG 또는 TF_CONNECTION)의 철자가 올바른지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="b9370-179">Make sure that the spelling of the flags (for example, TF_DIAG or TF_CONNECTION) is spelled correctly.</span></span> <span data-ttu-id="b9370-180">플래그의 철자가 제대로 지정되지 않은 경우 공급자는 예상 로그 정보를 반환할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b9370-180">If the flags are not spelled correctly, the provider cannot return the expected log information.</span></span>
  
<span data-ttu-id="b9370-181">이 시나리오에 공급자를 더 추가하려는 경우 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="b9370-181">If you want to add additional providers to this scenario, type the following:</span></span>

```PowerShell
Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider @{Add=$ABSProvider, $CASProvider, S4Provider}
```

<span data-ttu-id="b9370-182">Add 지시문으로 정의된 각 공급자는 **New-CsClsProvider** 프로세스를 사용하여 이미 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9370-182">Where each provider defined with the Add directive has already been defined using the **New-CsClsProvider** process.</span></span>
### <a name="to-remove-a-scenario-provider"></a><span data-ttu-id="b9370-183">시나리오 공급자를 제거하려면</span><span class="sxs-lookup"><span data-stu-id="b9370-183">To remove a scenario provider</span></span>

1. <span data-ttu-id="b9370-184">비즈니스용 Skype 서버 관리 셸 시작: **시작,** 모든 **프로그램,** 비즈니스용 **Skype 2015,** 비즈니스용 Skype 서버 관리 셸을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="b9370-184">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="b9370-185">제공된 cmdlet을 사용하면 기존 공급자를 업데이트하고 새 공급자를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9370-185">The cmdlets provided allow you to update existing providers and create new providers.</span></span> <span data-ttu-id="b9370-186">공급자를 제거하려면 Provider 매개 변수의 Replace 지시문을 **Set-CsClsScenario로 지정해야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="b9370-186">To remove a provider, you must use the Replace directive for the Provider parameter to **Set-CsClsScenario**.</span></span> <span data-ttu-id="b9370-187">공급자를 완전히 제거하는 유일한 방법은 공급자를 동일한 이름의 다시 정의된 공급자로 바꾸고 Update 지시문을 사용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b9370-187">The only way to completely remove a provider is to replace it with a redefined provider of the same name and use the Update directive.</span></span> <span data-ttu-id="b9370-188">예를 들어 공급자 LyssProvider는 WPP를 로그 유형으로 정의하고, 수준이 디버그로 설정되고, 플래그 집합은 TF_CONNECTION TF_DIAG.</span><span class="sxs-lookup"><span data-stu-id="b9370-188">For example, our provider LyssProvider is defined with WPP as the log type, level set to Debug, and flags set are TF_CONNECTION and TF_DIAG.</span></span> <span data-ttu-id="b9370-189">플래그를 "모두"로 변경해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9370-189">You need to change the flags to "All".</span></span> <span data-ttu-id="b9370-190">공급자를 변경하기 위해 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="b9370-190">To change the provider, type the following:</span></span>
    
   ```PowerShell
   $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Debug" -Flags "All"
   ```

   ```PowerShell
   Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider @{Replace=$LyssProvider}
   ```

3. <span data-ttu-id="b9370-191">시나리오 및 시나리오와 연결된 공급자를 완전히 제거하려면 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="b9370-191">If you want to completely remove a scenario and the providers associated with it, type the following:</span></span>
    
   ```PowerShell
   Remove-CsClsScenario -Identity <scope and name of scenario>
   ```

    <span data-ttu-id="b9370-192">예:</span><span class="sxs-lookup"><span data-stu-id="b9370-192">For example:</span></span>
    
   ```PowerShell
   Remove-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo"
   ```

    > [!CAUTION]
    > <span data-ttu-id="b9370-193">**Remove-CsClsScenario** cmdlet은 확인 메시지를 표시하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b9370-193">The cmdlet **Remove-CsClsScenario** does not prompt you for confirmation.</span></span> <span data-ttu-id="b9370-194">시나리오가 할당된 공급자와 함께 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="b9370-194">The scenario is deleted, along with the providers that were assigned to it.</span></span> <span data-ttu-id="b9370-195">시나리오를 처음 만드는 데 사용된 명령을 다시 실행하여 시나리오를 다시 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9370-195">You can recreate the scenario by re-running the commands used to create it initially.</span></span> <span data-ttu-id="b9370-196">제거된 시나리오나 공급자를 복구하는 절차는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b9370-196">There is no procedure to recover removed scenarios or providers.</span></span>
  
<span data-ttu-id="b9370-197">**Remove-CsClsScenario** cmdlet을 사용하여 시나리오를 제거하면 해당 시나리오가 범위에서 완전히 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="b9370-197">When you remove a scenario by using the **Remove-CsClsScenario** cmdlet, you completely remove the scenario from the scope.</span></span> <span data-ttu-id="b9370-198">만든 시나리오와 시나리오에 참여한 공급자를 사용하기 위해 새 공급자를 만들어 새 시나리오에 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="b9370-198">To use the scenarios that you created and the providers that were a part of the scenario, you create new providers and assign them to a new scenario.</span></span>
## <a name="see-also"></a><span data-ttu-id="b9370-199">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b9370-199">See also</span></span>

[<span data-ttu-id="b9370-200">Get-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="b9370-200">Get-CsClsScenario</span></span>](/powershell/module/skype/get-csclsscenario?view=skype-ps)
  
[<span data-ttu-id="b9370-201">New-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="b9370-201">New-CsClsScenario</span></span>](/powershell/module/skype/new-csclsscenario?view=skype-ps)
  
[<span data-ttu-id="b9370-202">Remove-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="b9370-202">Remove-CsClsScenario</span></span>](/powershell/module/skype/remove-csclsscenario?view=skype-ps)
  
[<span data-ttu-id="b9370-203">Set-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="b9370-203">Set-CsClsScenario</span></span>](/powershell/module/skype/set-csclsscenario?view=skype-ps)
  
[<span data-ttu-id="b9370-204">New-CsClsProvider</span><span class="sxs-lookup"><span data-stu-id="b9370-204">New-CsClsProvider</span></span>](/powershell/module/skype/new-csclsprovider?view=skype-ps)