---
title: 'Lync Server 2013: 중앙 로깅 서비스에 대 한 공급자 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring providers for Centralized Logging Service
ms:assetid: 6a197ecf-b56b-45e0-8e7c-f532ec5164ff
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688082(v=OCS.15)
ms:contentKeyID: 49733678
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 23ba3d903b1d4a33048f5a66738897408c36a94e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147281"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-providers-for-centralized-logging-service-in-lync-server-2013"></a><span data-ttu-id="19c71-102">Lync Server 2013에서 중앙 로깅 서비스에 대 한 공급자 구성</span><span class="sxs-lookup"><span data-stu-id="19c71-102">Configuring providers for Centralized Logging Service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="19c71-103">_**마지막으로 수정 된 항목:** 2014-03-19_</span><span class="sxs-lookup"><span data-stu-id="19c71-103">_**Topic Last Modified:** 2014-03-19_</span></span>

<span data-ttu-id="19c71-104">중앙 로깅 서비스에서 *공급자* 의 개념 및 구성은 이해 하기 가장 중요 한 사항 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="19c71-104">The concepts and configuration of *providers* in Centralized Logging Service is one of the most important to grasp.</span></span> <span data-ttu-id="19c71-105">*공급자* 는 lync server 추적 모델의 lync server 서버 역할 구성 요소에 직접 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="19c71-105">The *providers* map directly to Lync Server server role components in the Lync Server tracing model.</span></span> <span data-ttu-id="19c71-106">공급자는 추적할 Lync Server 2013의 구성 요소, 수집할 메시지 유형 (예: 치명적, 오류 또는 경고) 및 플래그 (TF\_CONNECTION 또는 tf\_Diag)를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="19c71-106">The provider defines the components of a Lync Server 2013 that will be traced, the type of messages (for example, fatal, error, or warning) to collect, and the flags (for example, TF\_Connection or TF\_Diag).</span></span> <span data-ttu-id="19c71-107">공급자는 각 Lync Server 서버 역할의 추적 가능한 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="19c71-107">Providers are the traceable components in each Lync Server server role.</span></span> <span data-ttu-id="19c71-108">공급자를 사용 하 여 구성 요소에 대 한 추적 수준 및 유형 (예: S4, 동안의 sipstack, IM 및 현재 상태)을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="19c71-108">By using providers, you define the level and type of tracing on components (for example, S4, SIPStack, IM and Presence).</span></span> <span data-ttu-id="19c71-109">정의 된 공급자는 특정 문제 조건을 해결 하는 지정 된 논리 컬렉션에 대 한 모든 공급자를 그룹화 하는 시나리오에서 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="19c71-109">The defined provider is used in a scenario to group all of the providers for a given logical collection that address a specific problem condition.</span></span>

<span data-ttu-id="19c71-110">Lync Server 관리 셸을 사용 하 여 중앙화 된 로깅 서비스 기능을 실행 하려면 CsAdministrator 또는 CsServerAdministrator의 RBAC (역할 기반 액세스 제어) 보안 그룹 또는 다음 중 하나를 포함 하는 사용자 지정 RBAC 역할의 구성원 이어야 합니다. 두 그룹</span><span class="sxs-lookup"><span data-stu-id="19c71-110">To run the Centralized Logging Service functions using the Lync Server Management Shell, you must be a member of either the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> <span data-ttu-id="19c71-111">이 cmdlet이 할당 된 모든 RBAC (역할 기반 액세스 제어) 역할 목록을 반환 하려면 (직접 만든 사용자 지정 RBAC 역할 포함) Lync Server 관리 셸 또는 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="19c71-111">To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Lync Server Management Shell or the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Lync Server 2013 cmdlet"}

<span data-ttu-id="19c71-112">예:</span><span class="sxs-lookup"><span data-stu-id="19c71-112">For example:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}

<span data-ttu-id="19c71-113">이 항목의 나머지 부분에서는 공급자 정의 방법, 공급자를 수정 하는 방법 및 공급자 정의에 포함 된 문제 해결을 최적화 하는 방법에 대해 중점적으로 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="19c71-113">The remainder of this topic focuses on how to define providers, modify a provider and what a provider definition contains to optimize your troubleshooting.</span></span> <span data-ttu-id="19c71-114">중앙 로깅 서비스 명령을 실행 하는 방법에는 두 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19c71-114">There are two ways to issue Centralized Logging Service commands.</span></span> <span data-ttu-id="19c71-115">기본적으로\\C: Program Files\\Common Files\\Microsoft Lync Server 2013\\clscontroller에 있는 clscontroller를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19c71-115">You can use the CLSController.exe that is located, by default, in the directory C:\\Program Files\\Common Files\\Microsoft Lync Server 2013\\CLSAgent.</span></span> <span data-ttu-id="19c71-116">또는 Lync Server 관리 셸을 사용 하 여 Windows PowerShell 명령을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19c71-116">Or, you can use the Lync Server Management Shell to issue Windows PowerShell commands.</span></span> <span data-ttu-id="19c71-117">중요 한 차이점은 CLSController .exe를 명령줄에서 사용 하는 경우 공급자가 이미 정의 되어 있으며 변경할 수 없지만 로그 수준을 정의할 수도 있다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="19c71-117">The important distinction is that when you use CLSController.exe at the command line there is a finite selection of scenarios available in which the providers are already defined and are not changeable, but you can define the log level.</span></span> <span data-ttu-id="19c71-118">Windows PowerShell을 사용 하 여 로깅 세션에서 사용할 새 공급자를 정의 하 고, 작성, 수집 및 데이터 수집 수준을 완전히 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19c71-118">By using Windows PowerShell, you can define new providers for use in your logging sessions, and have complete control over their creation, what they collect, and at what level they collect data.</span></span>

<div class="">


> [!IMPORTANT]  
> <span data-ttu-id="19c71-119">앞에서 설명한 것 처럼 공급자는 매우 강력 합니다.</span><span class="sxs-lookup"><span data-stu-id="19c71-119">As mentioned, providers are very powerful.</span></span> <span data-ttu-id="19c71-120">그러나 시나리오에는 공급자가 나타내는 구성 요소에 대 한 추적을 설정 하 고 실행 하는 데 필요한 모든 정보의 embodiment 포함 되어 있으므로 더 강력 합니다.</span><span class="sxs-lookup"><span data-stu-id="19c71-120">However, scenarios are more powerful because they contain the embodiment of all information needed to set and execute tracing on the components that the providers represent.</span></span> <span data-ttu-id="19c71-121">시나리오가 공급자의 모음인 경우에는 명령줄에서 수백 개의 명령을 사용 하 여 많은 정보를 수집 하 고 한 번에 하나씩 수백 개의 명령을 실행 하는 것과 비교할 때 보다 느슨하게 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19c71-121">With scenarios being a collection of providers, this could be loosely compared to running a batch file containing hundreds of commands to collect a lot of information versus issuing hundreds of commands, one at a time, at the command line.</span></span><BR><span data-ttu-id="19c71-122">중앙 로깅 서비스는 공급자의 세부 정보를 자세히 파악 하도록 요구 하는 대신 이미 정의 된 여러 시나리오를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="19c71-122">Instead of requiring you to dig deeply into the details of providers, the Centralized Logging Service provides a number of scenarios that are already defined for you.</span></span> <span data-ttu-id="19c71-123">제공 되는 시나리오에서는 발생할 수 있는 대부분의 가능한 문제를 다룹니다.</span><span class="sxs-lookup"><span data-stu-id="19c71-123">The provided scenarios cover the vast majority of possible issues that you will encounter.</span></span> <span data-ttu-id="19c71-124">드문 경우에는 공급자를 만들고 정의 하 여 시나리오에 할당 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19c71-124">In rare cases, you may need to create and define providers and assign them to scenarios.</span></span> <span data-ttu-id="19c71-125">새 공급자 및 시나리오를 만들기 위한 필요성을 조사 하기 전에 제공 되는 각 시나리오에 익숙해지는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="19c71-125">We strongly recommend that you become familiar with each of the scenarios provided before you investigate the need to create new providers and scenarios.</span></span> <span data-ttu-id="19c71-126">공급자를 만드는 방법에 대 한 정보는 시나리오에서 provider 요소를 사용 하 여 추적 정보를 수집 하는 방법을 익히는 데 도움이 되도록 여기에 제공 되며, 공급자 자체에 대 한 세부 정보는 현재 기본적</span><span class="sxs-lookup"><span data-stu-id="19c71-126">While information about creating providers is found here to familiarize you with how the scenarios use the provider elements to collect trace information, details on the providers themselves are not provided at this time.</span></span>



</div>

<span data-ttu-id="19c71-127">[Lync Server 2013의 중앙 로깅 서비스에 대 한 개요](lync-server-2013-overview-of-the-centralized-logging-service.md)에서 소개 된 시나리오에서 사용할 공급자 정의의 주요 요소는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="19c71-127">Introduced in [Overview of the Centralized Logging Service in Lync Server 2013](lync-server-2013-overview-of-the-centralized-logging-service.md), the key elements of defining a provider for use in a scenario are:</span></span>

  - <span data-ttu-id="19c71-128">**공급자**   ocslogger 사용 하는 데 익숙한 경우 공급자는 ocslogger 추적 엔진이 로그를 수집 해야 하는 대상을 알리기 위해 선택한 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="19c71-128">**Providers**   If you are familiar with OCSLogger, providers are the components that you choose to tell OCSLogger what the tracing engine should collect logs from.</span></span> <span data-ttu-id="19c71-129">공급자는 동일한 구성 요소 이며, 대부분의 경우에는 OCSLogger 있는 구성 요소와 이름이 같습니다.</span><span class="sxs-lookup"><span data-stu-id="19c71-129">The providers are the same components, and in many cases have the same name as the components in OCSLogger.</span></span> <span data-ttu-id="19c71-130">OCSLogger 아닌 경우 공급자는 중앙 로깅 서비스에서 로그를 수집할 수 있는 서버 역할 관련 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="19c71-130">If you are not familiar with OCSLogger, providers are server-role specific components that the Centralized Logging Service can collect logs from.</span></span> <span data-ttu-id="19c71-131">중앙 로깅 서비스의 경우 CLSAgent는 공급자 구성에서 정의 하는 구성 요소를 추적 하는 중앙 로깅 서비스의 아키텍처 부분입니다.</span><span class="sxs-lookup"><span data-stu-id="19c71-131">In the case of the Centralized Logging Service, the CLSAgent is the architectural part of the Centralized Logging Service that is doing the tracing of the components that you define in the providers configuration.</span></span>

  - <span data-ttu-id="19c71-132">**로깅 수준**   ocslogger 수집 된 데이터에 대 한 세부 수준 수를 선택 하는 옵션을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="19c71-132">**Logging levels**   OCSLogger provided the option to choose a number of levels of detail for the data collected.</span></span> <span data-ttu-id="19c71-133">이 기능은 중앙 로깅 서비스 및 시나리오의 필수 부분이 며 **Type** 매개 변수에 의해 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="19c71-133">This feature is an integral part of the Centralized Logging Service and scenarios, and is defined by the **Type** parameter.</span></span> <span data-ttu-id="19c71-134">다음 중에서 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19c71-134">You can choose from the following:</span></span>
    
      - <span data-ttu-id="19c71-135">**All**   은 정의 된 공급자에 대 한 로그에 치명적, 오류, 경고 및 정보 유형의 추적 메시지를 수집 합니다.</span><span class="sxs-lookup"><span data-stu-id="19c71-135">**All**   Collects trace messages of type fatal, error, warning, and info to the log for the defined provider.</span></span>
    
      - <span data-ttu-id="19c71-136">**치명적인**   정의 된 공급자에 대 한 오류를 나타내는 추적 메시지만 수집 합니다.</span><span class="sxs-lookup"><span data-stu-id="19c71-136">**Fatal**   Collects only the trace messages that indicate a failure for the defined provider.</span></span>
    
      - <span data-ttu-id="19c71-137">**Error**   정의 된 공급자에 대 한 오류를 나타내는 추적 메시지와 심각한 메시지를 수집 합니다.</span><span class="sxs-lookup"><span data-stu-id="19c71-137">**Error**   Collects only the trace messages that indicate an error for the defined provider, plus fatal messages.</span></span>
    
      - <span data-ttu-id="19c71-138">**Warning**   은 정의 된 공급자에 대 한 경고를 나타내는 추적 메시지와 치명적이 고 오류 메시지를 수집 합니다.</span><span class="sxs-lookup"><span data-stu-id="19c71-138">**Warning**   Collects only the trace messages that indicate a warning for the defined provider, plus fatal and error messages.</span></span>
    
      - <span data-ttu-id="19c71-139">**Info**   는 정의 된 공급자에 대 한 정보 메시지를 나타내는 추적 메시지와 심각, 오류 및 경고 메시지를 수집 합니다.</span><span class="sxs-lookup"><span data-stu-id="19c71-139">**Info**   Collects only the trace messages that indicate an informational message for the defined provider, plus fatal, error, and warning messages.</span></span>
    
      - <span data-ttu-id="19c71-140">**Verbose**   정의 된 공급자에 대 한 치명적, 오류, 경고 및 정보 유형의 모든 추적 메시지를 수집 합니다.</span><span class="sxs-lookup"><span data-stu-id="19c71-140">**Verbose**   Collects all trace messages of type fatal, error, warning and info for the defined provider.</span></span>

  - <span data-ttu-id="19c71-141">**Flags**   ocslogger 추적 파일에서 검색할 수 있는 정보 유형을 정의한 각 공급자에 대해 플래그를 선택 하는 옵션을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="19c71-141">**Flags**   OCSLogger provided the option to choose flags for each provider that defined what type of information you could retrieve from the trace files.</span></span> <span data-ttu-id="19c71-142">공급자에 따라 다음 플래그를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19c71-142">You can chose the following flags, based on the provider:</span></span>
    
      - <span data-ttu-id="19c71-143">**TF\_connection**   연결 관련 로그 항목을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="19c71-143">**TF\_Connection**   Provides connection-related log entries.</span></span> <span data-ttu-id="19c71-144">이러한 로그에는 특정 구성 요소에서 설정 된 연결에 대 한 정보가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="19c71-144">These logs include information about connections established to and from a particular component.</span></span> <span data-ttu-id="19c71-145">여기에는 중요 한 네트워크 수준 정보 (즉, 연결 개념을 제외 하 고 구성 요소)가 포함 될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19c71-145">This may also include significant network-level information (that is, for components without the concept of a connection).</span></span>
    
      - <span data-ttu-id="19c71-146">**TF\_security**   는 보안과 관련 된 모든 이벤트/로그 항목을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="19c71-146">**TF\_Security**   Provides all events/log entries related to security.</span></span> <span data-ttu-id="19c71-147">예를 들어 동안의 sipstack의 경우 도메인 유효성 검사 오류 및 클라이언트 인증/권한 부여 오류와 같은 보안 이벤트가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="19c71-147">For example, for SipStack, these are security events such as domain validation failure, and client authentication/authorization failures.</span></span>
    
      - <span data-ttu-id="19c71-148">**TF\_Diag**   는 구성 요소를 진단 하거나 문제를 해결 하는 데 사용할 수 있는 진단 이벤트를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="19c71-148">**TF\_Diag**   Provides diagnostics events that you can use to diagnose or troubleshoot the component.</span></span> <span data-ttu-id="19c71-149">예를 들어 동안의 sipstack의 경우 인증서 오류 또는 DNS 경고/오류입니다.</span><span class="sxs-lookup"><span data-stu-id="19c71-149">For example, for SipStack, these are certificate failures, or DNS warnings/errors.</span></span>
    
      - <span data-ttu-id="19c71-150">**TF\_protocol**   은 SIP 및 결합 된 커뮤니티 코덱 팩 메시지와 같은 프로토콜 메시지를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="19c71-150">**TF\_Protocol**   Provides protocol messages such as SIP and Combined Community Codec Pack messages.</span></span>
    
      - <span data-ttu-id="19c71-151">**TF\_Component**   는 공급자의 일부로 지정 된 구성 요소에 대해 로깅을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="19c71-151">**TF\_Component**   Enables logging on the components specified as part of the providers.</span></span>
    
      - <span data-ttu-id="19c71-152">**All**   공급자에 대해 사용 가능한 모든 플래그를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="19c71-152">**All**   Sets all available flags available for the provider.</span></span>

<div>

## <a name="to-review-information-about-existing-centralized-logging-service-scenario-providers"></a><span data-ttu-id="19c71-153">기존의 중앙화 된 로깅 서비스 시나리오 공급자에 대 한 정보를 검토 하려면</span><span class="sxs-lookup"><span data-stu-id="19c71-153">To review information about existing Centralized Logging Service scenario providers</span></span>

1.  <span data-ttu-id="19c71-154">**시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="19c71-154">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="19c71-155">기존 공급자의 구성을 검토 하려면 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="19c71-155">To review the configuration of existing providers, type the following:</span></span>
    
        Get-CsClsScenario -Identity <scope and scenario name> 
    
    <span data-ttu-id="19c71-156">예를 들어 전역 회의 전화 교환에 대 한 정보를 검토 하려면 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="19c71-156">For example, to review information about the global conferencing attendant, type:</span></span>
    
        Get-CsClsScenario -Identity "global/CAA"
    
    <span data-ttu-id="19c71-157">이 명령은 연결 된 플래그, 설정 및 구성 요소와 함께 공급자 목록을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="19c71-157">The command displays a list of providers with the associated flags, settings, and components.</span></span> <span data-ttu-id="19c71-158">표시 되는 정보가 충분 하지 않거나 목록이 너무 길어 기본 Windows PowerShell 목록 형식에 맞지 않는 경우 다른 출력 방법을 정의 하 여 추가 정보를 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19c71-158">If the information displayed is not enough or the list is too long for the default Windows PowerShell list format, you can display additional information by defining a different output method.</span></span> <span data-ttu-id="19c71-159">이렇게 하려면 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="19c71-159">To do this, type:</span></span>
    
        Get-CsClsScenario -Identity "global/CAA" | Select-Object -ExpandProperty Provider
    
    <span data-ttu-id="19c71-160">이 명령의 출력은 각 공급자를 5 줄 형식으로 표시 하며,이 형식은 공급자 이름, 로깅 유형, 로깅 수준, 플래그, GUID 및 역할이 각각 하나씩 별도의 줄에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="19c71-160">The output of this command displays each provider displayed in a five line format with the provider name, type of logging, logging level, flags, GUID, and role, each one on a separate line.</span></span>

</div>

<div>

## <a name="to-define-a-new-centralized-logging-service-scenario-provider"></a><span data-ttu-id="19c71-161">새 중앙화 된 로깅 서비스 시나리오 공급자를 정의 하려면</span><span class="sxs-lookup"><span data-stu-id="19c71-161">To define a new Centralized Logging Service scenario provider</span></span>

1.  <span data-ttu-id="19c71-162">**시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="19c71-162">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="19c71-163">시나리오 공급자는 추적, 사용할 플래그, 수집할 세부 정보 수준으로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="19c71-163">A scenario provider consists of a component to trace, flags to use, and a level of detail to collect.</span></span> <span data-ttu-id="19c71-164">다음을 입력 하 여이 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="19c71-164">You do this by typing:</span></span>
    
        $<variableName> = New-CsClsProvider -Name <provider component> -Type <log type> -Level <log level detail type> -Flags <provider trace log flags>
    
    <span data-ttu-id="19c71-165">예를 들어 Lyss 공급자에서 수집할 항목 및 세부 정보 수준을 정의 하는 추적 공급자 정의는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="19c71-165">For example, a trace provider definition that defines what to collect and to what level of detail from the Lyss provider looks like the following:</span></span>
    
        $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Info" -Flags "All"

<span data-ttu-id="19c71-166">– Level은 치명적, 오류, 경고 및 정보 메시지를 수집 합니다.</span><span class="sxs-lookup"><span data-stu-id="19c71-166">The –Level collects fatal, error, warning, and information messages.</span></span> <span data-ttu-id="19c71-167">Lyss 공급자에 대해 정의 된 플래그는 모두 사용 되며 TF\_CONNECTION, tf\_Diag 및 tf\_Protocol을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="19c71-167">The flags used are all of those defined for the Lyss provider, and include TF\_Connection, TF\_Diag and TF\_Protocol.</span></span>

<span data-ttu-id="19c71-168">$LyssProvider 변수를 정의한 후에는이를 **새 CsClsScenario** cmdlet과 함께 사용 하 여 lyss 공급자 로부터 추적을 수집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19c71-168">After the variable $LyssProvider is defined, you can use it with the **New-CsClsScenario** cmdlet to collect traces from the Lyss provider.</span></span> <span data-ttu-id="19c71-169">새 시나리오에 대 한 공급자 만들기 및 할당을 완료 하려면 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="19c71-169">To complete the creation and assignment of the provider to a new scenario, type:</span></span>

    New-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider $LyssProvider

<span data-ttu-id="19c71-170">여기서 $LyssProvider은 **새 CsClsProvider**로 만든 정의 된 시나리오를 포함 하는 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="19c71-170">Where $LyssProvider is the variable containing the defined scenario created with **New-CsClsProvider**.</span></span>

</div>

<div>

## <a name="to-change-an-existing-centralized-logging-service-scenario-provider"></a><span data-ttu-id="19c71-171">기존의 중앙화 된 로깅 서비스 시나리오 공급자를 변경 하려면</span><span class="sxs-lookup"><span data-stu-id="19c71-171">To change an existing Centralized Logging Service scenario provider</span></span>

1.  <span data-ttu-id="19c71-172">**시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="19c71-172">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="19c71-173">기존 공급자의 구성을 업데이트 하거나 변경 하려면 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="19c71-173">To update or change the configuration of an existing provider, type:</span></span>
    
        $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Debug" -Flags "TF_Connection, TF_Diag"
    
    <span data-ttu-id="19c71-174">그런 다음 다음을 입력 하 여 시나리오를 업데이트 하 여 공급자를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="19c71-174">You then update the scenario to assign the provider by typing the following:</span></span>
    
        Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider $LyssProvider

<span data-ttu-id="19c71-175">이 명령의 최종 결과는 시나리오 사이트: Redmond/RedmondLyssInfo에 게 할당 된 공급자에 대 한 플래그 및 수준이 업데이트 된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="19c71-175">The end result of the command is that the scenario site:Redmond/RedmondLyssInfo will have updated flags and level for the provider assigned to it.</span></span> <span data-ttu-id="19c71-176">Get-CsClsScenario를 사용 하 여 새 시나리오를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19c71-176">You can view the new scenario by using Get-CsClsScenario.</span></span> <span data-ttu-id="19c71-177">자세한 내용은 [Get-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/Get-CsClsScenario)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="19c71-177">For details, see [Get-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/Get-CsClsScenario).</span></span>

<div class="">


> [!WARNING]  
> <span data-ttu-id="19c71-178"><STRONG>새-ClsCsProvider</STRONG> 에서는 플래그가 유효한 지 여부를 확인 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="19c71-178"><STRONG>New-ClsCsProvider</STRONG> does not check to determine whether the flags are valid.</span></span> <span data-ttu-id="19c71-179">플래그의 철자 (예: TF_DIAG 또는 TF_CONNECTION)가 올바른지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="19c71-179">Make sure that the spelling of the flags (for example, TF_DIAG or TF_CONNECTION) is spelled correctly.</span></span> <span data-ttu-id="19c71-180">플래그의 철자가 올바르지 않으면 공급자가 필요한 로그 정보를 반환할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="19c71-180">If the flags are not spelled correctly, the provider cannot return the expected log information.</span></span>



</div>

<span data-ttu-id="19c71-181">이 시나리오에 공급자를 더 추가 하려면 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="19c71-181">If you want to add additional providers to this scenario, type the following:</span></span>

    Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider @{Add=$ABSProvider, $CASProvider, S4Provider}

<span data-ttu-id="19c71-182">Add 지시문을 사용 하 여 정의 된 각 공급자는 이미 **새-CsClsProvider** 프로세스를 사용 하 여 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="19c71-182">Where each provider defined with the Add directive has already been defined using the **New-CsClsProvider** process.</span></span>

</div>

<div>

## <a name="to-remove-a-scenario-provider"></a><span data-ttu-id="19c71-183">시나리오 공급자를 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="19c71-183">To remove a scenario provider</span></span>

1.  <span data-ttu-id="19c71-184">**시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="19c71-184">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="19c71-185">제공 된 cmdlet을 사용 하면 기존 공급자를 업데이트 하 고 새 공급자를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19c71-185">The cmdlets provided allow you to update existing providers and create new providers.</span></span> <span data-ttu-id="19c71-186">공급자를 제거 하려면 Provider 매개 변수의 Replace 지시문을 **설정-CsClsScenario**로 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="19c71-186">To remove a provider, you must use the Replace directive for the Provider parameter to **Set-CsClsScenario**.</span></span> <span data-ttu-id="19c71-187">공급자를 완전히 제거 하는 유일한 방법은이를 동일한 이름의 다시 정의 된 공급자로 바꾸고 Update 지시문을 사용 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="19c71-187">The only way to completely remove a provider is to replace it with a redefined provider of the same name and use the Update directive.</span></span> <span data-ttu-id="19c71-188">예를 들어 provider LyssProvider는 WPP를 사용 하 여 정의 되며,이 형식은 디버그로 설정 되며, 플래그 집합은 TF\_CONNECTION and tf\_DIAG입니다.</span><span class="sxs-lookup"><span data-stu-id="19c71-188">For example, our provider LyssProvider is defined with WPP as the log type, level set to Debug, and flags set are TF\_CONNECTION and TF\_DIAG.</span></span> <span data-ttu-id="19c71-189">플래그를 "All"로 변경 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="19c71-189">You need to change the flags to “All”.</span></span> <span data-ttu-id="19c71-190">공급자를 변경 하려면 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="19c71-190">To change the provider, type the following:</span></span>
    
        $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Debug" -Flags "All"

     &nbsp;
    
        Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider @{Replace=$LyssProvider}

3.  <span data-ttu-id="19c71-191">시나리오와 해당 역할과 연결 된 공급자를 완전히 제거 하려면 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="19c71-191">If you want to completely remove a scenario and the providers associated with it, type the following:</span></span>
    
        Remove-CsClsScenario -Identity <scope and name of scenario>
    
    <span data-ttu-id="19c71-192">예:</span><span class="sxs-lookup"><span data-stu-id="19c71-192">For example:</span></span>
    
        Remove-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo"
    
    <div class="">
    

    > [!WARNING]  
    > <span data-ttu-id="19c71-193">Cmdlet <STRONG>제거-CsClsScenario</STRONG> 에서는 확인 메시지를 표시 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="19c71-193">The cmdlet <STRONG>Remove-CsClsScenario</STRONG> does not prompt you for confirmation.</span></span> <span data-ttu-id="19c71-194">시나리오가 할당 된 공급자와 함께 삭제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="19c71-194">The scenario is deleted, along with the providers that were assigned to it.</span></span> <span data-ttu-id="19c71-195">처음에 사용 하는 데 사용한 명령을 다시 실행 하 여 시나리오를 다시 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19c71-195">You can recreate the scenario by re-running the commands used to create it initially.</span></span> <span data-ttu-id="19c71-196">제거 된 시나리오 또는 공급자를 복구 하는 절차는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="19c71-196">There is no procedure to recover removed scenarios or providers.</span></span>

    
    </div>

<span data-ttu-id="19c71-197">**제거-CsClsScenario** cmdlet을 사용 하 여 시나리오를 제거 하면 범위에서 시나리오가 완전히 제거 됩니다.</span><span class="sxs-lookup"><span data-stu-id="19c71-197">When you remove a scenario by using the **Remove-CsClsScenario** cmdlet, you completely remove the scenario from the scope.</span></span> <span data-ttu-id="19c71-198">만든 시나리오 및 시나리오의 일부인 공급자를 사용 하려면 새 공급자를 만들고 새 시나리오에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="19c71-198">To use the scenarios that you created and the providers that were a part of the scenario, you create new providers and assign them to a new scenario.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="19c71-199">참고 항목</span><span class="sxs-lookup"><span data-stu-id="19c71-199">See Also</span></span>


[<span data-ttu-id="19c71-200">Get-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="19c71-200">Get-CsClsScenario</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsClsScenario)  
[<span data-ttu-id="19c71-201">새 CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="19c71-201">New-CsClsScenario</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsClsScenario)  
[<span data-ttu-id="19c71-202">제거-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="19c71-202">Remove-CsClsScenario</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsClsScenario)  
[<span data-ttu-id="19c71-203">설정-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="19c71-203">Set-CsClsScenario</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsClsScenario)  
[<span data-ttu-id="19c71-204">새-CsClsProvider</span><span class="sxs-lookup"><span data-stu-id="19c71-204">New-CsClsProvider</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsClsProvider)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

