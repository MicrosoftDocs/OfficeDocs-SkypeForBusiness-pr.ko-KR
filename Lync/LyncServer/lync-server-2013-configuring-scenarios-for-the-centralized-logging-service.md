---
title: 'Lync Server 2013: 중앙 로깅 서비스에 대 한 시나리오 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring scenarios for the Centralized Logging Service
ms:assetid: 6c3bf826-e7fd-4002-95dc-01020641ef01
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688085(v=OCS.15)
ms:contentKeyID: 49733682
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fc58e0f29ca0a562a94f771857d88da49d616064
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42199691"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-scenarios-for-the-centralized-logging-service-in-lync-server-2013"></a><span data-ttu-id="66102-102">Lync Server 2013에서 중앙 로깅 서비스에 대 한 시나리오 구성</span><span class="sxs-lookup"><span data-stu-id="66102-102">Configuring scenarios for the Centralized Logging Service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="66102-103">_**마지막으로 수정 된 항목:** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="66102-103">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="66102-104">시나리오는 범위 (전역, 사이트, 풀 또는 컴퓨터)와 중앙 로깅 서비스에서 사용할 공급자를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="66102-104">Scenarios define the scope (that is, global, site, pool, or computer) and what providers to use in the Centralized Logging Service.</span></span> <span data-ttu-id="66102-105">시나리오를 사용 하 여 공급자 (예: S4, 동안의 sipstack, IM 및 현재 상태)에 추적을 사용 하거나 사용 하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66102-105">By using scenarios, you enable or disable tracing on providers (for example, S4, SIPStack, IM, and Presence).</span></span> <span data-ttu-id="66102-106">시나리오를 구성 하 여 특정 문제 조건을 해결 하는 지정 된 논리 컬렉션에 대 한 모든 공급자를 그룹화 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66102-106">By configuring a scenario, you can group all of the providers for a given logical collection that address a specific problem condition.</span></span> <span data-ttu-id="66102-107">문제 해결 및 로깅 요구 사항에 맞게 시나리오를 수정 해야 하는 경우 Lync Server 2013 디버그 도구는 *a* 라는 함수를 포함 하는 Windows PowerShell 모듈 (예: *Edit-csclsscenario)* 을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="66102-107">If you find that a scenario needs to be modified to meet your troubleshooting and logging needs, the Lync Server 2013 Debug Tools provides you a Windows PowerShell module named *ClsController.psm1* that contains a function named *Edit-CsClsScenario*.</span></span> <span data-ttu-id="66102-108">이 모듈은 명명 된 시나리오의 속성을 편집 하는 데 목적이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66102-108">The purpose of the module is to edit the properties of the named scenario.</span></span> <span data-ttu-id="66102-109">이 항목에서는이 모듈이 작동 하는 방식에 대 한 예를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="66102-109">Examples of how this module works are provided in this topic.</span></span> <span data-ttu-id="66102-110">Lync Server 2013 디버그 도구는 다음 링크에서 다운로드 됩니다.[https://go.microsoft.com/fwlink/?LinkId=285257](https://go.microsoft.com/fwlink/?linkid=285257)</span><span class="sxs-lookup"><span data-stu-id="66102-110">The Lync Server 2013 Debug Tools are downloaded from the following link: [https://go.microsoft.com/fwlink/?LinkId=285257](https://go.microsoft.com/fwlink/?linkid=285257)</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="66102-111">지정 된 범위 (사이트, 전역, 풀 또는 컴퓨터)에 대해 언제 든 지 최대 두 개의 시나리오를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66102-111">For any given scope—site, global, pool or computer—you can run a maximum of two scenarios at any given time.</span></span> <span data-ttu-id="66102-112">현재 실행 중인 시나리오를 확인 하려면 Windows PowerShell 및 <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsClsScenario">Get CsClsScenario</A>를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="66102-112">To determine which scenarios are currently running, use Windows PowerShell and <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsClsScenario">Get-CsClsScenario</A>.</span></span> <span data-ttu-id="66102-113">Windows PowerShell 및 <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsClsScenario">설정-CsClsScenario</A>를 사용 하 여 실행 중인 시나리오를 동적으로 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66102-113">By using Windows PowerShell and <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsClsScenario">Set-CsClsScenario</A>, you can dynamically change which scenarios are running.</span></span> <span data-ttu-id="66102-114">로깅 세션 중에 실행 되는 시나리오를 수정 하 여 수집 중인 데이터와 공급자를 조정 하거나 구체화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66102-114">You can modify which scenarios are running during a logging session to adjust or refine the data you are collecting and from which providers.</span></span>



</div>

<span data-ttu-id="66102-115">Lync Server 관리 셸을 사용 하 여 중앙 로깅 서비스 기능을 실행 하려면 CsAdministrator 또는 CsServerAdministrator의 RBAC (역할 기반 액세스 제어) 보안 그룹 또는 다음 중 하나를 포함 하는 사용자 지정 RBAC 역할의 구성원 이어야 합니다. 두 그룹 중에서</span><span class="sxs-lookup"><span data-stu-id="66102-115">To run the Centralized Logging Service functions by using the Lync Server Management Shell, you must be a member of either the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> <span data-ttu-id="66102-116">직접 만든 사용자 지정 RBAC 역할을 포함 하 여이 cmdlet이 할당 된 모든 RBAC 역할의 목록을 반환 하려면 Lync Server 관리 셸 또는 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="66102-116">To return a list of all the RBAC roles this cmdlet has been assigned to, including any custom RBAC roles you have created yourself, run the following command from the Lync Server Management Shell or the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Lync Server 2013 cmdlet"}

<span data-ttu-id="66102-117">예:</span><span class="sxs-lookup"><span data-stu-id="66102-117">For example:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}

<span data-ttu-id="66102-118">이 항목의 나머지 부분에서는 시나리오를 정의 하 고, 시나리오를 수정 하 고, 실행 중인 시나리오를 검색 하 고, 시나리오를 제거 하 고, 문제 해결을 최적화 하기 위해 시나리오에 포함 된 내용을 지정 하는 방법에 초점을 두고</span><span class="sxs-lookup"><span data-stu-id="66102-118">The remainder of this topic focuses on how to define a scenario, modify a scenario, retrieve what scenarios are running, remove a scenario, and specify what a scenario contains to optimize your troubleshooting.</span></span> <span data-ttu-id="66102-119">중앙 로깅 서비스 명령을 실행 하는 방법에는 두 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66102-119">There are two ways to issue Centralized Logging Service commands.</span></span> <span data-ttu-id="66102-120">기본적으로\\C: Program Files\\Common Files\\Microsoft Lync Server 2013\\clscontroller에 있는 clscontroller를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66102-120">You can use the CLSController.exe that is located, by default, in the directory C:\\Program Files\\Common Files\\Microsoft Lync Server 2013\\CLSAgent.</span></span> <span data-ttu-id="66102-121">또는 Lync Server 관리 셸을 사용 하 여 Windows PowerShell 명령을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66102-121">Or, you can use the Lync Server Management Shell to issue Windows PowerShell commands.</span></span> <span data-ttu-id="66102-122">중요 한 차이점은 CLSController .exe를 명령줄에서 사용 하는 경우 사용 가능한 시나리오를 제한적으로 선택할 수 있다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="66102-122">The important distinction is that when you use CLSController.exe at the command line there is a finite selection of scenarios available.</span></span> <span data-ttu-id="66102-123">Windows PowerShell을 사용 하는 경우 로깅 세션에서 사용할 새 시나리오를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66102-123">When you use Windows PowerShell, you can define new scenarios for use in your logging sessions.</span></span>

<span data-ttu-id="66102-124">[Lync Server 2013의 중앙화 된 로깅 서비스 개요에 설명](lync-server-2013-overview-of-the-centralized-logging-service.md)된 대로 시나리오의 요소는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="66102-124">As introduced in [Overview of the Centralized Logging Service in Lync Server 2013](lync-server-2013-overview-of-the-centralized-logging-service.md), the elements of a scenario are:</span></span>

  - <span data-ttu-id="66102-125">**공급자**   ocslogger 사용 하는 데 익숙한 경우 공급자는 ocslogger 추적 엔진이 로그를 수집 해야 하는 대상을 알리기 위해 선택한 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="66102-125">**Providers**   If you are familiar with OCSLogger, providers are the components that you choose to tell OCSLogger what the tracing engine should collect logs from.</span></span> <span data-ttu-id="66102-126">공급자는 동일한 구성 요소 이며, 대부분의 경우에는 OCSLogger 있는 구성 요소와 이름이 같습니다.</span><span class="sxs-lookup"><span data-stu-id="66102-126">The providers are the same components, and in many cases have the same name as the components in OCSLogger.</span></span> <span data-ttu-id="66102-127">OCSLogger 사용 하는 방법을 잘 모르는 경우 공급자는 중앙 로깅 서비스가 로그를 수집할 수 있는 서버 역할 관련 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="66102-127">If you are not familiar with OCSLogger, providers are server role specific components that the Centralized Logging Service can collect logs from.</span></span> <span data-ttu-id="66102-128">공급자 구성에 대 한 자세한 내용은 [Lync Server 2013에서 중앙 로깅 서비스에 대 한 공급자 구성을](lync-server-2013-configuring-providers-for-centralized-logging-service.md)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="66102-128">For details about the configuration of providers, see [Configuring providers for Centralized Logging Service in Lync Server 2013](lync-server-2013-configuring-providers-for-centralized-logging-service.md).</span></span>

  - <span data-ttu-id="66102-129">**Identity**   매개 변수-identity는 시나리오의 범위와 이름을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="66102-129">**Identity**   The parameter –Identity sets the scope and name of the scenario.</span></span> <span data-ttu-id="66102-130">예를 들어 범위를 "global"로 설정 하 고 시나리오를 "LyssServiceScenario"로 식별할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66102-130">For example, you could set a scope of “global” and identify the scenario with “LyssServiceScenario”.</span></span> <span data-ttu-id="66102-131">둘을 결합할 때 Id를 정의 합니다 (예: "global/LyssServiceScenario").</span><span class="sxs-lookup"><span data-stu-id="66102-131">When you combine the two, you define the Identity (for example, “global/LyssServiceScenario”).</span></span>
    
    <span data-ttu-id="66102-132">원하는 경우 – Name 및 – Parent 매개 변수를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66102-132">Optionally, you can use the –Name and –Parent parameters.</span></span> <span data-ttu-id="66102-133">시나리오를 고유 하 게 식별 하는 Name 매개 변수를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="66102-133">You define the Name parameter to uniquely identify the scenario.</span></span> <span data-ttu-id="66102-134">Name을 사용 하는 경우에는 Parent를 사용 하 여 전역 또는 사이트에 시나리오를 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="66102-134">If you use Name, you must also use Parent to add the scenario to either global or site.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="66102-135">Name 및 Parent 매개 변수를 사용 하는 경우에는 <STRONG>-Identity</STRONG> 매개 변수를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="66102-135">If you use the Name and Parent parameters, you cannot use the <STRONG>–Identity</STRONG> parameter.</span></span>

    
    </div>

<div>

## <a name="to-create-a-new-scenario-with-the-new-csclsscenario-cmdlet"></a><span data-ttu-id="66102-136">새로운-CsClsScenario cmdlet을 사용 하 여 새 시나리오를 만들려면</span><span class="sxs-lookup"><span data-stu-id="66102-136">To create a new scenario with the New-CsClsScenario cmdlet</span></span>

1.  <span data-ttu-id="66102-137">**시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="66102-137">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="66102-138">로깅 세션에 대 한 새 시나리오를 만들려면 [새-CsClsProvider](https://docs.microsoft.com/powershell/module/skype/New-CsClsProvider) 를 사용 하 고 시나리오 이름 (즉, 고유 하 게 식별 되는 방법)을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="66102-138">To create a new scenario for a logging session, use [New-CsClsProvider](https://docs.microsoft.com/powershell/module/skype/New-CsClsProvider) and define the name of the scenario (that is, how it will be uniquely identified).</span></span> <span data-ttu-id="66102-139">WPP (Windows 소프트웨어 추적 전처리기 및 기본값), EventLog (즉, Windows 이벤트 로그 형식) 또는 IISLog (즉, IIS 로그 파일 형식을 기반으로 하는 ASCII 형식 파일)에서 로깅 형식 유형을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="66102-139">Choose a type of logging format from WPP (that is, Windows software tracing preprocessor and is the default), EventLog (that is, Windows event log format), or IISLog (that is, ASCII format file based on the IIS log file format).</span></span> <span data-ttu-id="66102-140">그런 다음 수준 (이 항목의 로깅 수준에 정의 됨) 및 플래그 (이 항목의 플래그에 정의 됨)를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="66102-140">Next, define Level (as the defined under Logging Levels in this topic), and Flags (as defined under Flags in this topic).</span></span>
    
    <span data-ttu-id="66102-141">이 예제 시나리오에서는 예제 공급자 변수로 LyssProvider를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="66102-141">For this example scenario, we use LyssProvider as the example provider variable.</span></span>
    
    <span data-ttu-id="66102-142">정의 된 옵션을 사용 하 여 시나리오를 만들려면 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="66102-142">To create a scenario using the options defined, type:</span></span>
    
        New-CsClsScenario -Identity <scope>/<unique scenario name> -Provider <provider variable>
    
    <span data-ttu-id="66102-143">예:</span><span class="sxs-lookup"><span data-stu-id="66102-143">For example:</span></span>
    
        New-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider $LyssProvider
    
    <span data-ttu-id="66102-144">-Name 및 – Parent를 사용 하는 대체 형식은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="66102-144">The alternate format using –Name and –Parent:</span></span>
    
        New-CsClsScenario -Name "LyssServiceScenario" -Parent "site:Redmond" -Provider $LyssProvider

</div>

<div>

## <a name="to-create-a-new-scenario-with-multiple-providers-with-the-new-csclsscenario-cmdlet"></a><span data-ttu-id="66102-145">새로운-CsClsScenario cmdlet을 사용 하 여 여러 공급자가 포함 된 새 시나리오를 만들려면</span><span class="sxs-lookup"><span data-stu-id="66102-145">To create a new scenario with multiple providers with the New-CsClsScenario cmdlet</span></span>

1.  <span data-ttu-id="66102-146">**시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="66102-146">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="66102-147">범위 당 두 개의 시나리오로 제한 됩니다.</span><span class="sxs-lookup"><span data-stu-id="66102-147">You are limited to two scenarios per scope.</span></span> <span data-ttu-id="66102-148">그러나 설정 된 공급자 수로 제한 되지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="66102-148">However, you are not limited to a set number of providers.</span></span> <span data-ttu-id="66102-149">이 예제에서는 공급자를 세 개 만들고이 세 가지를 모두 정의 하는 시나리오에 할당 하려고 한다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="66102-149">In this example, assume that we have created three providers, and you want to assign all three to the scenario you are defining.</span></span> <span data-ttu-id="66102-150">공급자 변수 이름은 LyssProvider, ABServerProvider 및 SIPStackProvider입니다.</span><span class="sxs-lookup"><span data-stu-id="66102-150">The provider variable names are LyssProvider, ABServerProvider, and SIPStackProvider.</span></span> <span data-ttu-id="66102-151">여러 공급자를 정의 하 고 시나리오에 할당 하려면 Lync Server 관리 셸 또는 Windows PowerShell 명령 프롬프트에 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="66102-151">To define and assign multiple providers to a scenario, type the following at a Lync Server Management Shell or Windows PowerShell command prompt:</span></span>
    
        New-CsClsScenario -Identity "site:Redmond/CollectDataScenario" -Provider @{Add=$LyssProvider, $ABServerProvider,  $SIPStackProvider}
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="66102-152">Windows PowerShell에서 알 수 있듯이 값을 사용 하 <CODE>@{&lt;variable&gt;=&lt;value1&gt;, &lt;value2&gt;, &lt;value&gt;...}</CODE> 는 해시 테이블을 만드는 규칙을 <EM>splatting</EM>이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="66102-152">As it is known in Windows PowerShell, the convention for creating a hash table of values using <CODE>@{&lt;variable&gt;=&lt;value1&gt;, &lt;value2&gt;, &lt;value&gt;...}</CODE> is known as <EM>splatting</EM>.</span></span> <span data-ttu-id="66102-153">Windows PowerShell의 splatting에 대 한 자세한 내용은 <A href="https://go.microsoft.com/fwlink/p/?linkid=267760">https://go.microsoft.com/fwlink/p/?LinkId=267760</A>를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="66102-153">For details about splatting in Windows PowerShell, see <A href="https://go.microsoft.com/fwlink/p/?linkid=267760">https://go.microsoft.com/fwlink/p/?LinkId=267760</A>.</span></span>

    
    </div>

</div>

<div>

## <a name="to-modify-an-existing-scenario-with-the-set-csclsscenario-cmdlet"></a><span data-ttu-id="66102-154">설정-CsClsScenario cmdlet을 사용 하 여 기존 시나리오를 수정 하려면</span><span class="sxs-lookup"><span data-stu-id="66102-154">To modify an existing scenario with the Set-CsClsScenario cmdlet</span></span>

1.  <span data-ttu-id="66102-155">**시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="66102-155">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="66102-156">범위 당 두 개의 시나리오로 제한 됩니다.</span><span class="sxs-lookup"><span data-stu-id="66102-156">You are limited to two scenarios per scope.</span></span> <span data-ttu-id="66102-157">로깅 캡처 세션이 진행 중인 경우에도 언제 든 지 실행 되는 시나리오를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66102-157">You can change which scenarios are running at any time, even when a logging capture session is in process.</span></span> <span data-ttu-id="66102-158">실행 중인 시나리오를 다시 정의 하는 경우 현재 로깅 세션은 제거 된 시나리오 사용을 중지 한 다음 새 시나리오를 사용 하기 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="66102-158">If you redefine the running scenarios, the current logging session will stop using the scenario that was removed and then begin using the new scenario.</span></span> <span data-ttu-id="66102-159">그러나 제거 된 시나리오를 사용 하 여 캡처한 로깅 정보는 캡처한 로그에 남아 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66102-159">However, the logging information that was captured with the removed scenario remains in the captured logs.</span></span> <span data-ttu-id="66102-160">새 시나리오를 정의 하려면 다음을 수행 합니다 (즉, "S4Provider" 라는 이미 정의 된 공급자를 추가 한다고 가정).</span><span class="sxs-lookup"><span data-stu-id="66102-160">To define a new scenario, do the following (that is, assuming the addition of an already defined provider named “S4Provider”):</span></span>
    
        Set-CsClsScenario -Identity <name of scope and scenario defined by New-CsClsScenario> -Provider @{Add=<new provider to add>}
    
    <span data-ttu-id="66102-161">예:</span><span class="sxs-lookup"><span data-stu-id="66102-161">For example:</span></span>
    
        Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Add=$S4Provider}
    
    <span data-ttu-id="66102-162">공급자를 바꾸려면 single provider 또는 쉼표로 구분 된 공급자 목록을 정의 하 여 현재 집합을 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="66102-162">If you want to replace providers, define a single provider or a comma separated list of providers to replace the current set.</span></span> <span data-ttu-id="66102-163">대부분의 공급자 중 하나를 바꾸려는 경우 새 공급자와 현재 공급자를 추가 하 여 새 공급자와 기존 공급자를 모두 포함 하는 새 공급자 집합을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="66102-163">If you only want to replace one of many providers, add the current providers with the new providers to create a new set of providers that contains both new providers and existing providers.</span></span> <span data-ttu-id="66102-164">모든 공급자를 새 집합으로 바꾸려면 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="66102-164">To replace all providers with a new set, type the following:</span></span>
    
        Set-CsClsScenario -Identity <name of scope and scenario defined by New-CsClsScenario> -Provider @{Replace=<providers to replace existing provider set>}
    
    <span data-ttu-id="66102-165">예를 들어 현재 $LyssProvider, $ABServerProvider 및 $SIPStackProvider를 $LyssServiceProvider으로 바꾸려면 다음과 같이 합니다.</span><span class="sxs-lookup"><span data-stu-id="66102-165">For example, to replace the current set of $LyssProvider, $ABServerProvider, and $SIPStackProvider with $LyssServiceProvider:</span></span>
    
        Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Replace=$LyssServiceProvider}
    
    <span data-ttu-id="66102-166">현재 $LyssProvider 집합에서 $LyssProvider 공급자로, $ABServerProvider 및 $LyssServiceProvider을 사용 하 여 $SIPStackProvider를 교체 하려면 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="66102-166">To replace just the $LyssProvider provider from the current set of $LyssProvider, $ABServerProvider, and $SIPStackProvider with $LyssServiceProvider, type the following:</span></span>
    
        Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Replace=$LyssServiceProvider, $ABServerProvider, $SIPStackProvider}

</div>

<div>

## <a name="to-remove-an-existing-scenario-with-the-remove-csclsscenario-cmdlet"></a><span data-ttu-id="66102-167">제거-CsClsScenario cmdlet을 사용 하 여 기존 시나리오를 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="66102-167">To remove an existing scenario with the Remove-CsClsScenario cmdlet</span></span>

1.  <span data-ttu-id="66102-168">**시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="66102-168">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="66102-169">이전에 정의 된 시나리오를 제거 하려면 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="66102-169">If you want to remove a scenario that has been previously defined, type the following:</span></span>
    
        Remove-CsClsScenario -Identity <name of scope and scenario>
    
    <span data-ttu-id="66102-170">예를 들어 정의 된 시나리오 사이트를 제거 하려면 다음을 수행 합니다. Redmond/LyssServiceScenario:</span><span class="sxs-lookup"><span data-stu-id="66102-170">For example, to remove the defined scenario site:Redmond/LyssServiceScenario:</span></span>
    
        Remove-CsClsScenario -Identity "site:Redmond/LyssServiceScenario"

<span data-ttu-id="66102-171">**제거-CsClsScenario** cmdlet은 지정 된 시나리오를 제거 하지만 캡처한 추적은 계속 해 서 검색을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66102-171">The **Remove-CsClsScenario** cmdlet removes the specified scenario, but the traces that have been captured are still available in the logs for you to search on.</span></span>

</div>

<div>

## <a name="to-load-and-unload-the-edit-csclsscenario-cmdlet-using-the-clscontrollerpsm1-module"></a><span data-ttu-id="66102-172">ClsController. a 모듈을 사용 하 여 편집-CsClsScenario cmdlet을 로드 하 고 언로드하려면</span><span class="sxs-lookup"><span data-stu-id="66102-172">To load and unload the Edit-CsClsScenario cmdlet using the ClsController.psm1 module</span></span>

1.  <span data-ttu-id="66102-173">**시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="66102-173">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="66102-174">ClsController 모듈은 별도의 웹 다운로드로 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="66102-174">The ClsController.psm1 module is provided as a separate Web download.</span></span> <span data-ttu-id="66102-175">이 모듈은 Lync Server 2013 디버깅 도구의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="66102-175">The module is part of the Lync Server 2013 Debugging tools.</span></span> <span data-ttu-id="66102-176">기본적으로 디버깅 도구는 C:\Program Files\Lync Server 2013 \ 디버깅 도구 디렉터리에 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="66102-176">By default, the debugging tools are installed in the directory C:\Program Files\Lync Server 2013\Debugging Tools.</span></span>

    
    </div>

2.  <span data-ttu-id="66102-177">Windows PowerShell에서 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="66102-177">From the Windows PowerShell, type:</span></span>
    
        Import-Module "C:\Program Files\Lync Server 2013\Debugging Tools\ClsController.psm1"
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="66102-178">모듈 로드에 성공 하면 Windows PowerShell 명령 프롬프트로 돌아갑니다.</span><span class="sxs-lookup"><span data-stu-id="66102-178">Successful loading of the module returns you to the Windows PowerShell command prompt.</span></span> <span data-ttu-id="66102-179">모듈이 로드 되 고 편집-CsClsScenario를 사용할 수 있는지 확인 하려면를 입력 <CODE>Get-Help Edit-CsClsScenario</CODE>합니다.</span><span class="sxs-lookup"><span data-stu-id="66102-179">To confirm that the module is loaded and that Edit-CsClsScenario is available, type <CODE>Get-Help Edit-CsClsScenario</CODE>.</span></span> <span data-ttu-id="66102-180">EditCsClsScenario에 대 한 구문의 기본 개요 표시 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="66102-180">You should see the basic synopsis of the syntax for EditCsClsScenario.</span></span>

    
    </div>

3.  <span data-ttu-id="66102-181">모듈을 언로드하려면 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="66102-181">To unload the modules, type:</span></span>
    
        Remove-Module ClsController
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="66102-182">모듈을 성공적으로 언로드하면 Windows PowerShell 명령 프롬프트로 돌아갑니다.</span><span class="sxs-lookup"><span data-stu-id="66102-182">Successful unloading of the module returns you to the Windows PowerShell command prompt.</span></span> <span data-ttu-id="66102-183">모듈이 언로드되는 지 확인 하려면를 입력 <CODE>Get-Help Edit-CsClsScenario</CODE>합니다.</span><span class="sxs-lookup"><span data-stu-id="66102-183">To confirm that the module is unloaded, type <CODE>Get-Help Edit-CsClsScenario</CODE>.</span></span> <span data-ttu-id="66102-184">Windows PowerShell에서 cmdlet에 대 한 도움말을 찾으려고 하 고 실패 했습니다.</span><span class="sxs-lookup"><span data-stu-id="66102-184">Windows PowerShell will attempt to locate the help for the cmdlet and fail.</span></span>

    
    </div>

</div>

<div>

## <a name="to-remove-an-existing-provider-from-a-scenario-with-the-edit-clscontroller-module"></a><span data-ttu-id="66102-185">기존 공급자를 시나리오에서 편집-ClsController 모듈을 사용 하 여 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="66102-185">To remove an existing provider from a scenario with the Edit-ClsController module</span></span>

1.  <span data-ttu-id="66102-186">**시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="66102-186">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="66102-187">AlwaysOn 시나리오에서 공급자를 제거 하려면 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="66102-187">To remove a provider from the AlwaysOn scenario, type:</span></span>
    
        Edit-CsClsScenario -ScenarioName <string of the scenario to edit> -ProviderName <string of the provider to remove> -Remove
    
    <span data-ttu-id="66102-188">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="66102-188">For Example:</span></span>
    
        Edit-CsClsScenario -ScenarioName AlwaysOn -ProviderName ChatServer -Remove
    
    <span data-ttu-id="66102-189">ScenarioName 및 ProviderName 매개 변수는 위치 (명령줄의 예상 위치에서 정의 되어야 함) 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="66102-189">The parameters ScenarioName and ProviderName are positional (that is, they must be defined in the expected position in the command line) parameters.</span></span> <span data-ttu-id="66102-190">시나리오 이름이 2 위치에 있고 공급자가 3 위치, 즉 cmdlet의 이름을 위치 1로 지정 하는 경우 매개 변수 이름을 명시적으로 정의할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="66102-190">The parameter name does not have to be explicitly defined if the scenario name is in position two and the provider is in position three, relative to the name of the cmdlet as position one.</span></span> <span data-ttu-id="66102-191">이 정보를 사용 하면 위의 명령에 다음과 같은 형식이 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="66102-191">Using this information, the previous command would be typed as:</span></span>
    
        Edit-CsClsScenario AlwaysOn ChatServer -Remove
    
    <span data-ttu-id="66102-192">매개 변수 값을 배치 하는 위치는 – Scenario 및 – Provider에만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="66102-192">The positional placing of the parameter values applies only to –Scenario and –Provider.</span></span> <span data-ttu-id="66102-193">다른 모든 매개 변수는 명시적으로 정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="66102-193">All other parameters must be explicitly defined.</span></span>

</div>

<div>

## <a name="to-add-a-provider-to-a-scenario-with-the-edit-clscontroller-module"></a><span data-ttu-id="66102-194">ClsController 모듈을 사용 하 여 시나리오에 공급자를 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="66102-194">To add a provider to a scenario with the Edit-ClsController module</span></span>

1.  <span data-ttu-id="66102-195">**시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="66102-195">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="66102-196">AlwaysOn 시나리오에 공급자를 추가 하려면 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="66102-196">To add a provider to the AlwaysOn scenario, type:</span></span>
    
        Edit-CsClsScenario -ScenarioName <string of the scenario to edit> -ProviderName <string of the provider to add> -Level <string of type level> -Flags <string of type flags>
    
    <span data-ttu-id="66102-197">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="66102-197">For Example:</span></span>
    
        Edit-CsClsScenario -ScenarioName AlwaysOn -ProviderName ChatServer -Level Info -Flags TF_COMPONENT
    
    <span data-ttu-id="66102-198">\-Loglevel은 치명적, Error, Warning, Info, Verbose, Debug 또는 All 형식일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66102-198">\-Loglevel can be of the type Fatal, Error, Warning, Info, Verbose, Debug, or All.</span></span> <span data-ttu-id="66102-199">-Flags는 TF\_COMPONENT, tf\_DIAG와 같이 공급자에서 지 원하는 모든 플래그를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66102-199">–Flags can be any of the flags that the provider supports, such as TF\_COMPONENT, TF\_DIAG.</span></span> <span data-ttu-id="66102-200">-Flags는 모두 값일 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66102-200">–Flags can also be of value ALL</span></span>
    
    <span data-ttu-id="66102-201">Cmdlet의 위치 기능을 사용 하 여 앞의 예제를 입력할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66102-201">The previous example can also be typed using the positional feature of the cmdlet.</span></span> <span data-ttu-id="66102-202">예를 들어 AlwaysOn 시나리오에 provider \ 서버를 추가 하려면 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="66102-202">For example, to add the provider ChatServer to the AlwaysOn scenario, type:</span></span>
    
        Edit-CsClsScenario AlwaysOn ChatServer -Level Info -Flags ALL

</div>

</div>

<span> </span>

</div>

</div>

</div>

