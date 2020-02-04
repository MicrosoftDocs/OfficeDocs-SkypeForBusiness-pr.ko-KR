---
title: 'Lync Server 2013: 중앙 집중화 된 로깅 서비스에 대 한 공급자 구성'
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
ms.openlocfilehash: 2428bd11e656d0f1b6295e63ca6106fa7edcbb15
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734858"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-providers-for-centralized-logging-service-in-lync-server-2013"></a><span data-ttu-id="99634-102">Lync Server 2013에서 중앙 집중화 된 로깅 서비스에 대 한 공급자 구성</span><span class="sxs-lookup"><span data-stu-id="99634-102">Configuring providers for Centralized Logging Service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="99634-103">_**마지막으로 수정한 주제:** 2014-03-19_</span><span class="sxs-lookup"><span data-stu-id="99634-103">_**Topic Last Modified:** 2014-03-19_</span></span>

<span data-ttu-id="99634-104">중앙 로깅 서비스의 *공급자* 에 대 한 개념 및 구성은 가장 중요 하 게 이해 하는 방법 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="99634-104">The concepts and configuration of *providers* in Centralized Logging Service is one of the most important to grasp.</span></span> <span data-ttu-id="99634-105">*공급자* 는 lync server 추적 모델의 lync server 서버 역할 구성 요소에 직접 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="99634-105">The *providers* map directly to Lync Server server role components in the Lync Server tracing model.</span></span> <span data-ttu-id="99634-106">공급자는 추적 되는 Lync Server 2013의 구성 요소, 수집할 메시지 유형 (예: 치명적, 오류 또는 경고) 및 플래그 (예: TF\_CONNECTION 또는 tf\_Diag)를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="99634-106">The provider defines the components of a Lync Server 2013 that will be traced, the type of messages (for example, fatal, error, or warning) to collect, and the flags (for example, TF\_Connection or TF\_Diag).</span></span> <span data-ttu-id="99634-107">공급자는 각 Lync Server 서버 역할의 추적 가능한 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="99634-107">Providers are the traceable components in each Lync Server server role.</span></span> <span data-ttu-id="99634-108">공급자를 사용 하 여 구성 요소 (예: S4, SIPStack, IM 및 현재 상태)에 추적의 수준과 유형을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="99634-108">By using providers, you define the level and type of tracing on components (for example, S4, SIPStack, IM and Presence).</span></span> <span data-ttu-id="99634-109">정의 된 공급자는 특정 문제 조건을 처리 하는 지정 된 논리적 수집에 대 한 모든 공급자를 그룹화 하는 시나리오에서 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="99634-109">The defined provider is used in a scenario to group all of the providers for a given logical collection that address a specific problem condition.</span></span>

<span data-ttu-id="99634-110">Lync Server Management Shell을 사용 하 여 중앙 집중화 된 로깅 서비스 기능을 실행 하려면 CsAdministrator 또는 CsServerAdministrator 역할 기반 액세스 제어 (RBAC) 보안 그룹 또는 다음 중 하나를 포함 하는 사용자 지정 RBAC 역할의 구성원 이어야 합니다. 두 그룹</span><span class="sxs-lookup"><span data-stu-id="99634-110">To run the Centralized Logging Service functions using the Lync Server Management Shell, you must be a member of either the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> <span data-ttu-id="99634-111">이 cmdlet이 할당 된 모든 RBAC (역할 기반 액세스 제어) (모든 사용자 지정 RBAC 역할 포함)의 목록을 반환 하려면 Lync Server 관리 셸 또는 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="99634-111">To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Lync Server Management Shell or the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Lync Server 2013 cmdlet"}

<span data-ttu-id="99634-112">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="99634-112">For example:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}

<span data-ttu-id="99634-113">이 항목의 나머지 부분에서는 공급자를 정의 하 고, 공급자를 수정 하 고, 문제 해결을 최적화 하는 데 포함 된 공급자 정의에 대해 중점적으로 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="99634-113">The remainder of this topic focuses on how to define providers, modify a provider and what a provider definition contains to optimize your troubleshooting.</span></span> <span data-ttu-id="99634-114">중앙 로깅 서비스 명령을 실행 하는 방법에는 두 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99634-114">There are two ways to issue Centralized Logging Service commands.</span></span> <span data-ttu-id="99634-115">기본적으로\\C: 프로그램 파일\\의 디렉터리에 있는 clscontroller를 사용할 수 있습니다.\\Microsoft Lync Server 2013\\clscontroller.</span><span class="sxs-lookup"><span data-stu-id="99634-115">You can use the CLSController.exe that is located, by default, in the directory C:\\Program Files\\Common Files\\Microsoft Lync Server 2013\\CLSAgent.</span></span> <span data-ttu-id="99634-116">또는 Lync Server Management Shell을 사용 하 여 Windows PowerShell 명령을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99634-116">Or, you can use the Lync Server Management Shell to issue Windows PowerShell commands.</span></span> <span data-ttu-id="99634-117">중요 한 차이점은, 명령줄에서 CLSController. exe를 사용 하는 경우에는 공급자가 이미 정의 되 고 변경할 수 없지만 로그 수준을 정의할 수 있다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="99634-117">The important distinction is that when you use CLSController.exe at the command line there is a finite selection of scenarios available in which the providers are already defined and are not changeable, but you can define the log level.</span></span> <span data-ttu-id="99634-118">Windows PowerShell을 사용 하 여 로깅 세션에서 사용할 새 공급자를 정의 하 고, 생성, 수집 하는 내용, 데이터를 수집 하는 수준에 대 한 완전 한 제어 권한을 가질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99634-118">By using Windows PowerShell, you can define new providers for use in your logging sessions, and have complete control over their creation, what they collect, and at what level they collect data.</span></span>

<div class="">


> [!IMPORTANT]  
> <span data-ttu-id="99634-119">앞에서 언급 했 듯이 공급자는 매우 강력한 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="99634-119">As mentioned, providers are very powerful.</span></span> <span data-ttu-id="99634-120">그러나 시나리오에는 공급자가 표시 하는 구성 요소에서 추적을 설정 하 고 실행 하는 데 필요한 모든 정보의 embodiment 포함 되어 있기 때문에 더 강력 합니다.</span><span class="sxs-lookup"><span data-stu-id="99634-120">However, scenarios are more powerful because they contain the embodiment of all information needed to set and execute tracing on the components that the providers represent.</span></span> <span data-ttu-id="99634-121">시나리오를 공급자 컬렉션으로 사용 하는 경우 많은 정보를 수집 하 고 명령줄에서 한 번에 하나씩 수백 개의 명령을 실행 하는 등 수백 개의 명령이 포함 된 배치 파일을 실행 하는 것에 비해 느슨하게 전환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99634-121">With scenarios being a collection of providers, this could be loosely compared to running a batch file containing hundreds of commands to collect a lot of information versus issuing hundreds of commands, one at a time, at the command line.</span></span><BR><span data-ttu-id="99634-122">공급자의 세부 정보를 자세히 설명 하는 대신 중앙 로깅 서비스는 이미 정의 된 다양 한 시나리오를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="99634-122">Instead of requiring you to dig deeply into the details of providers, the Centralized Logging Service provides a number of scenarios that are already defined for you.</span></span> <span data-ttu-id="99634-123">제공 되는 시나리오는 발생할 수 있는 대부분의 가능한 문제를 다룹니다.</span><span class="sxs-lookup"><span data-stu-id="99634-123">The provided scenarios cover the vast majority of possible issues that you will encounter.</span></span> <span data-ttu-id="99634-124">드문 경우 지만, 공급자를 만들고 정의 하 고 시나리오에 할당 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99634-124">In rare cases, you may need to create and define providers and assign them to scenarios.</span></span> <span data-ttu-id="99634-125">새 공급자 및 시나리오를 만들어야 한다는 것을 조사 하기 전에 제공 되는 각 시나리오에 대해 잘 알고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="99634-125">We strongly recommend that you become familiar with each of the scenarios provided before you investigate the need to create new providers and scenarios.</span></span> <span data-ttu-id="99634-126">공급자를 만드는 방법에 대 한 정보를 참조 하는 것은 시나리오를 통해 추적 정보를 수집 하는 방법에 대 한 자세한 내용은 현재 제공 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="99634-126">While information about creating providers is found here to familiarize you with how the scenarios use the provider elements to collect trace information, details on the providers themselves are not provided at this time.</span></span>



</div>

<span data-ttu-id="99634-127">[Lync Server 2013의 중앙 집중화 된 로깅 서비스에 대 한 개요](lync-server-2013-overview-of-the-centralized-logging-service.md)에 도입 된 시나리오에서 사용할 공급자를 정의 하는 주요 요소는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="99634-127">Introduced in [Overview of the Centralized Logging Service in Lync Server 2013](lync-server-2013-overview-of-the-centralized-logging-service.md), the key elements of defining a provider for use in a scenario are:</span></span>

  - <span data-ttu-id="99634-128">**공급자**   ocslogger 사용 하는 데 익숙한 경우 공급자는 ocslogger 로그를 수집 해야 하는 항목을 지정 하기 위해 선택 하는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="99634-128">**Providers**   If you are familiar with OCSLogger, providers are the components that you choose to tell OCSLogger what the tracing engine should collect logs from.</span></span> <span data-ttu-id="99634-129">공급자는 동일한 구성 요소 이며, 대부분의 경우에는 OCSLogger 구성 요소와 동일한 이름을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="99634-129">The providers are the same components, and in many cases have the same name as the components in OCSLogger.</span></span> <span data-ttu-id="99634-130">OCSLogger 익숙하지 않은 경우 공급자는 중앙 로깅 서비스에서 로그를 수집할 수 있는 서버 역할 특정 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="99634-130">If you are not familiar with OCSLogger, providers are server-role specific components that the Centralized Logging Service can collect logs from.</span></span> <span data-ttu-id="99634-131">중앙 로깅 서비스의 경우 CLSAgent는 공급자 구성에 정의 된 구성 요소의 추적을 수행 하는 중앙 로깅 서비스의 아키텍처 부분입니다.</span><span class="sxs-lookup"><span data-stu-id="99634-131">In the case of the Centralized Logging Service, the CLSAgent is the architectural part of the Centralized Logging Service that is doing the tracing of the components that you define in the providers configuration.</span></span>

  - <span data-ttu-id="99634-132">**로깅 수준**   ocslogger는 수집 된 데이터의 세부 수준 수를 선택 하는 옵션을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="99634-132">**Logging levels**   OCSLogger provided the option to choose a number of levels of detail for the data collected.</span></span> <span data-ttu-id="99634-133">이 기능은 중앙 로깅 서비스 및 시나리오의 핵심 부분이 며 **Type** 매개 변수에 의해 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="99634-133">This feature is an integral part of the Centralized Logging Service and scenarios, and is defined by the **Type** parameter.</span></span> <span data-ttu-id="99634-134">다음 중에서 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99634-134">You can choose from the following:</span></span>
    
      - <span data-ttu-id="99634-135">**All**   은 정의 된 공급자의 로그에 대 한 치명적인, 오류, 경고 및 정보 유형의 추적 메시지를 수집 합니다.</span><span class="sxs-lookup"><span data-stu-id="99634-135">**All**   Collects trace messages of type fatal, error, warning, and info to the log for the defined provider.</span></span>
    
      - <span data-ttu-id="99634-136">**치명적**   은 정의 된 공급자에 대 한 오류를 나타내는 추적 메시지만 수집 합니다.</span><span class="sxs-lookup"><span data-stu-id="99634-136">**Fatal**   Collects only the trace messages that indicate a failure for the defined provider.</span></span>
    
      - <span data-ttu-id="99634-137">**오류**   는 정의 된 공급자에 대 한 오류를 나타내는 추적 메시지와 심각한 메시지를 수집 합니다.</span><span class="sxs-lookup"><span data-stu-id="99634-137">**Error**   Collects only the trace messages that indicate an error for the defined provider, plus fatal messages.</span></span>
    
      - <span data-ttu-id="99634-138">**경고**   는 정의 된 공급자에 대 한 경고를 나타내는 추적 메시지와 치명적이 고 오류 메시지를 수집 합니다.</span><span class="sxs-lookup"><span data-stu-id="99634-138">**Warning**   Collects only the trace messages that indicate a warning for the defined provider, plus fatal and error messages.</span></span>
    
      - <span data-ttu-id="99634-139">**정보**   는 정의 된 공급자에 대 한 정보 메시지를 나타내는 추적 메시지와 치명적, 오류, 경고 메시지를 수집 합니다.</span><span class="sxs-lookup"><span data-stu-id="99634-139">**Info**   Collects only the trace messages that indicate an informational message for the defined provider, plus fatal, error, and warning messages.</span></span>
    
      - <span data-ttu-id="99634-140">**Verbose**   는 정의 된 공급자에 대 한 치명적, 오류, 경고 및 정보 유형의 모든 추적 메시지를 수집 합니다.</span><span class="sxs-lookup"><span data-stu-id="99634-140">**Verbose**   Collects all trace messages of type fatal, error, warning and info for the defined provider.</span></span>

  - <span data-ttu-id="99634-141">**Flags**   ocslogger는 추적 파일에서 검색할 수 있는 정보 유형을 정의한 각 공급자에 대 한 플래그를 선택 하는 옵션을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="99634-141">**Flags**   OCSLogger provided the option to choose flags for each provider that defined what type of information you could retrieve from the trace files.</span></span> <span data-ttu-id="99634-142">공급자에 따라 다음 플래그를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99634-142">You can chose the following flags, based on the provider:</span></span>
    
      - <span data-ttu-id="99634-143">**TF\_connection**   연결 관련 로그 항목을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="99634-143">**TF\_Connection**   Provides connection-related log entries.</span></span> <span data-ttu-id="99634-144">이러한 로그에는 특정 구성 요소에 설정 된 연결에 대 한 정보가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="99634-144">These logs include information about connections established to and from a particular component.</span></span> <span data-ttu-id="99634-145">여기에는 중요 한 네트워크 수준 정보 (즉, 연결 개념 없이 구성 요소)도 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99634-145">This may also include significant network-level information (that is, for components without the concept of a connection).</span></span>
    
      - <span data-ttu-id="99634-146">**TF\_security**   는 보안과 관련 된 모든 이벤트/로그 항목을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="99634-146">**TF\_Security**   Provides all events/log entries related to security.</span></span> <span data-ttu-id="99634-147">예를 들어 SipStack의 경우 도메인 유효성 검사 오류, 클라이언트 인증/권한 부여 실패 등의 보안 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="99634-147">For example, for SipStack, these are security events such as domain validation failure, and client authentication/authorization failures.</span></span>
    
      - <span data-ttu-id="99634-148">**TF\_Diag**   는 구성 요소를 진단 하거나 문제를 해결 하는 데 사용할 수 있는 진단 이벤트를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="99634-148">**TF\_Diag**   Provides diagnostics events that you can use to diagnose or troubleshoot the component.</span></span> <span data-ttu-id="99634-149">예를 들어 SipStack의 경우 인증서 오류 또는 DNS 경고/오류입니다.</span><span class="sxs-lookup"><span data-stu-id="99634-149">For example, for SipStack, these are certificate failures, or DNS warnings/errors.</span></span>
    
      - <span data-ttu-id="99634-150">**TF\_프로토콜**   은 SIP 및 결합 된 커뮤니티 코덱 팩 메시지 등의 프로토콜 메시지를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="99634-150">**TF\_Protocol**   Provides protocol messages such as SIP and Combined Community Codec Pack messages.</span></span>
    
      - <span data-ttu-id="99634-151">**TF\_Component**   는 공급자의 일부로 지정 된 구성 요소에 로깅할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="99634-151">**TF\_Component**   Enables logging on the components specified as part of the providers.</span></span>
    
      - <span data-ttu-id="99634-152">**모두**   공급자에 대해 사용할 수 있는 모든 플래그를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="99634-152">**All**   Sets all available flags available for the provider.</span></span>

<div>

## <a name="to-review-information-about-existing-centralized-logging-service-scenario-providers"></a><span data-ttu-id="99634-153">기존 중앙 집중화 된 로깅 서비스 시나리오 공급자에 대 한 정보를 검토 하려면</span><span class="sxs-lookup"><span data-stu-id="99634-153">To review information about existing Centralized Logging Service scenario providers</span></span>

1.  <span data-ttu-id="99634-154">Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="99634-154">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="99634-155">기존 공급자의 구성을 검토 하려면 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="99634-155">To review the configuration of existing providers, type the following:</span></span>
    
        Get-CsClsScenario -Identity <scope and scenario name> 
    
    <span data-ttu-id="99634-156">예를 들어 전역 회의 수행자에 대 한 정보를 검토 하려면 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="99634-156">For example, to review information about the global conferencing attendant, type:</span></span>
    
        Get-CsClsScenario -Identity "global/CAA"
    
    <span data-ttu-id="99634-157">이 명령은 연결 된 플래그, 설정 및 구성 요소와 함께 공급자 목록을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="99634-157">The command displays a list of providers with the associated flags, settings, and components.</span></span> <span data-ttu-id="99634-158">표시 되는 정보가 부족 하거나 목록이 기본 Windows PowerShell 목록 형식에 비해 너무 긴 경우 다른 출력 방법을 정의 하 여 추가 정보를 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99634-158">If the information displayed is not enough or the list is too long for the default Windows PowerShell list format, you can display additional information by defining a different output method.</span></span> <span data-ttu-id="99634-159">이렇게 하려면 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="99634-159">To do this, type:</span></span>
    
        Get-CsClsScenario -Identity "global/CAA" | Select-Object -ExpandProperty Provider
    
    <span data-ttu-id="99634-160">이 명령의 출력은 공급자 이름, 로깅 형식, 로깅 수준, 플래그, GUID, 역할 등 5 개의 줄 형식으로 표시 되는 각 공급자를 각각 별도의 줄에 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="99634-160">The output of this command displays each provider displayed in a five line format with the provider name, type of logging, logging level, flags, GUID, and role, each one on a separate line.</span></span>

</div>

<div>

## <a name="to-define-a-new-centralized-logging-service-scenario-provider"></a><span data-ttu-id="99634-161">중앙 집중화 된 새 로깅 서비스 시나리오 공급자를 정의 하려면</span><span class="sxs-lookup"><span data-stu-id="99634-161">To define a new Centralized Logging Service scenario provider</span></span>

1.  <span data-ttu-id="99634-162">Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="99634-162">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="99634-163">시나리오 공급자는 추적 하는 구성 요소, 사용할 플래그, 수집할 세부 정보 수준으로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="99634-163">A scenario provider consists of a component to trace, flags to use, and a level of detail to collect.</span></span> <span data-ttu-id="99634-164">다음을 입력 하 여이 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="99634-164">You do this by typing:</span></span>
    
        $<variableName> = New-CsClsProvider -Name <provider component> -Type <log type> -Level <log level detail type> -Flags <provider trace log flags>
    
    <span data-ttu-id="99634-165">예를 들어 수집 대상을 정의 하 고 Lyss 공급자의 세부 정보 수준에 대 한 추적 공급자 정의는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="99634-165">For example, a trace provider definition that defines what to collect and to what level of detail from the Lyss provider looks like the following:</span></span>
    
        $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Info" -Flags "All"

<span data-ttu-id="99634-166">– Level은 치명적, 오류, 경고 및 정보 메시지를 수집 합니다.</span><span class="sxs-lookup"><span data-stu-id="99634-166">The –Level collects fatal, error, warning, and information messages.</span></span> <span data-ttu-id="99634-167">사용 된 플래그는 Lyss 공급자에 대해 정의 된 모든 것 이며 TF\_CONNECTION, tf\_Diag 및 tf\_Protocol을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="99634-167">The flags used are all of those defined for the Lyss provider, and include TF\_Connection, TF\_Diag and TF\_Protocol.</span></span>

<span data-ttu-id="99634-168">변수 $LyssProvider 정의 된 후에는 **새 CsClsScenario** cmdlet을 사용 하 여 lyss 공급자에서 추적을 수집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99634-168">After the variable $LyssProvider is defined, you can use it with the **New-CsClsScenario** cmdlet to collect traces from the Lyss provider.</span></span> <span data-ttu-id="99634-169">새 시나리오에 대 한 공급자 만들기 및 할당을 완료 하려면 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="99634-169">To complete the creation and assignment of the provider to a new scenario, type:</span></span>

    New-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider $LyssProvider

<span data-ttu-id="99634-170">여기서 $LyssProvider은 **새 CsClsProvider**를 사용 하 여 만든 정의 된 시나리오를 포함 하는 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="99634-170">Where $LyssProvider is the variable containing the defined scenario created with **New-CsClsProvider**.</span></span>

</div>

<div>

## <a name="to-change-an-existing-centralized-logging-service-scenario-provider"></a><span data-ttu-id="99634-171">기존 중앙 집중화 된 로깅 서비스 시나리오 공급자를 변경 하려면</span><span class="sxs-lookup"><span data-stu-id="99634-171">To change an existing Centralized Logging Service scenario provider</span></span>

1.  <span data-ttu-id="99634-172">Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="99634-172">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="99634-173">기존 공급자의 구성을 업데이트 하거나 변경 하려면 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="99634-173">To update or change the configuration of an existing provider, type:</span></span>
    
        $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Debug" -Flags "TF_Connection, TF_Diag"
    
    <span data-ttu-id="99634-174">그런 다음 시나리오를 업데이트 하 여 다음을 입력 하 여 공급자를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="99634-174">You then update the scenario to assign the provider by typing the following:</span></span>
    
        Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider $LyssProvider

<span data-ttu-id="99634-175">이 명령의 최종 결과는 시나리오 사이트: 레드먼드/RedmondLyssInfo에 할당 된 공급자에 대 한 플래그와 수준을 업데이트 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="99634-175">The end result of the command is that the scenario site:Redmond/RedmondLyssInfo will have updated flags and level for the provider assigned to it.</span></span> <span data-ttu-id="99634-176">Get-CsClsScenario를 사용 하 여 새 시나리오를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99634-176">You can view the new scenario by using Get-CsClsScenario.</span></span> <span data-ttu-id="99634-177">자세한 내용은 [Get CsClsScenario](https://docs.microsoft.com/powershell/module/skype/Get-CsClsScenario)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="99634-177">For details, see [Get-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/Get-CsClsScenario).</span></span>

<div class="">


> [!WARNING]  
> <span data-ttu-id="99634-178"><STRONG>새-ClsCsProvider</STRONG> 는 플래그가 유효한 지 여부를 확인 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="99634-178"><STRONG>New-ClsCsProvider</STRONG> does not check to determine whether the flags are valid.</span></span> <span data-ttu-id="99634-179">플래그의 맞춤법 (예: TF_DIAG 또는 TF_CONNECTION)이 정확한 지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="99634-179">Make sure that the spelling of the flags (for example, TF_DIAG or TF_CONNECTION) is spelled correctly.</span></span> <span data-ttu-id="99634-180">플래그에 맞춤법이 잘못 된 경우 공급자는 필요한 로그 정보를 반환할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="99634-180">If the flags are not spelled correctly, the provider cannot return the expected log information.</span></span>



</div>

<span data-ttu-id="99634-181">이 시나리오에 추가 공급자를 추가 하려면 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="99634-181">If you want to add additional providers to this scenario, type the following:</span></span>

    Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider @{Add=$ABSProvider, $CASProvider, S4Provider}

<span data-ttu-id="99634-182">Add 지시문을 사용 하 여 정의 된 각 공급자는 이미 **새 CsClsProvider** 프로세스를 사용 하 여 정의 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="99634-182">Where each provider defined with the Add directive has already been defined using the **New-CsClsProvider** process.</span></span>

</div>

<div>

## <a name="to-remove-a-scenario-provider"></a><span data-ttu-id="99634-183">시나리오 공급자를 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="99634-183">To remove a scenario provider</span></span>

1.  <span data-ttu-id="99634-184">Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="99634-184">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="99634-185">제공 된 cmdlet을 사용 하 여 기존 공급자를 업데이트 하 고 새 공급자를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99634-185">The cmdlets provided allow you to update existing providers and create new providers.</span></span> <span data-ttu-id="99634-186">공급자를 제거 하려면 Provider 매개 변수에 대 한 Replace 지시문을 **Set-CsClsScenario**에 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="99634-186">To remove a provider, you must use the Replace directive for the Provider parameter to **Set-CsClsScenario**.</span></span> <span data-ttu-id="99634-187">공급자를 완전히 제거 하는 유일한 방법은 동일한 이름의 재정의 된 공급자로 바꾼 다음 Update 지시문을 사용 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="99634-187">The only way to completely remove a provider is to replace it with a redefined provider of the same name and use the Update directive.</span></span> <span data-ttu-id="99634-188">예를 들어, 공급자 LyssProvider는 WPP를 사용 하 여 로그 유형, 디버그로 설정 된 수준 집합, 그리고 flags 집합\_은 tf CONNECTION\_및 tf DIAG로 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="99634-188">For example, our provider LyssProvider is defined with WPP as the log type, level set to Debug, and flags set are TF\_CONNECTION and TF\_DIAG.</span></span> <span data-ttu-id="99634-189">플래그를 "모두"로 변경 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="99634-189">You need to change the flags to “All”.</span></span> <span data-ttu-id="99634-190">공급자를 변경 하려면 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="99634-190">To change the provider, type the following:</span></span>
    
        $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Debug" -Flags "All"

     &nbsp;
    
        Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider @{Replace=$LyssProvider}

3.  <span data-ttu-id="99634-191">시나리오 및이에 연결 된 공급자를 완전히 제거 하려면 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="99634-191">If you want to completely remove a scenario and the providers associated with it, type the following:</span></span>
    
        Remove-CsClsScenario -Identity <scope and name of scenario>
    
    <span data-ttu-id="99634-192">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="99634-192">For example:</span></span>
    
        Remove-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo"
    
    <div class="">
    

    > [!WARNING]  
    > <span data-ttu-id="99634-193">Cmdlet <STRONG>제거-CsClsScenario</STRONG> 에서는 확인 메시지가 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="99634-193">The cmdlet <STRONG>Remove-CsClsScenario</STRONG> does not prompt you for confirmation.</span></span> <span data-ttu-id="99634-194">시나리오는 자신에 게 할당 된 공급자와 함께 삭제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="99634-194">The scenario is deleted, along with the providers that were assigned to it.</span></span> <span data-ttu-id="99634-195">처음으로 생성 하는 데 사용 된 명령을 다시 실행 하 여 시나리오를 다시 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99634-195">You can recreate the scenario by re-running the commands used to create it initially.</span></span> <span data-ttu-id="99634-196">제거 된 시나리오 또는 공급자를 복구 하는 방법은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="99634-196">There is no procedure to recover removed scenarios or providers.</span></span>

    
    </div>

<span data-ttu-id="99634-197">**제거-CsClsScenario** cmdlet을 사용 하 여 시나리오를 제거 하면 범위에서 해당 시나리오가 완전히 제거 됩니다.</span><span class="sxs-lookup"><span data-stu-id="99634-197">When you remove a scenario by using the **Remove-CsClsScenario** cmdlet, you completely remove the scenario from the scope.</span></span> <span data-ttu-id="99634-198">자신이 만든 시나리오와 시나리오의 일부인 공급자를 사용 하려면 새 공급자를 만들고 새 시나리오에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="99634-198">To use the scenarios that you created and the providers that were a part of the scenario, you create new providers and assign them to a new scenario.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="99634-199">참고 항목</span><span class="sxs-lookup"><span data-stu-id="99634-199">See Also</span></span>


[<span data-ttu-id="99634-200">Get-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="99634-200">Get-CsClsScenario</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsClsScenario)  
[<span data-ttu-id="99634-201">신규-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="99634-201">New-CsClsScenario</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsClsScenario)  
[<span data-ttu-id="99634-202">-CsClsScenario 제거</span><span class="sxs-lookup"><span data-stu-id="99634-202">Remove-CsClsScenario</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsClsScenario)  
[<span data-ttu-id="99634-203">Set-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="99634-203">Set-CsClsScenario</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsClsScenario)  
[<span data-ttu-id="99634-204">새-CsClsProvider</span><span class="sxs-lookup"><span data-stu-id="99634-204">New-CsClsProvider</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsClsProvider)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

