---
title: 비즈니스용 Skype 서버에서 중앙 로깅 서비스에 대한 시나리오 구성
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 6c3bf826-e7fd-4002-95dc-01020641ef01
description: '요약: 비즈니스용 Skype 서버 2015에서 중앙 로깅 서비스에 대한 시나리오를 만들고 수정하고 제거하는 방법을 설명합니다.'
ms.openlocfilehash: 6ec6764ce3717f38fead9e88c570895f1676310f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51098844"
---
# <a name="configure-scenarios-for-the-centralized-logging-service-in-skype-for-business-server-2015"></a><span data-ttu-id="a3e74-103">비즈니스용 Skype 서버에서 중앙 로깅 서비스에 대한 시나리오 구성</span><span class="sxs-lookup"><span data-stu-id="a3e74-103">Configure scenarios for the Centralized Logging Service in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="a3e74-104">**요약:** 비즈니스용 Skype 서버 2015에서 중앙 로깅 서비스에 대한 시나리오를 만들고 수정하고 제거하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a3e74-104">**Summary:** Learn how to create, modify, and remove scenarios for the Centralized Logging Service in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="a3e74-105">시나리오는 범위(전역, 사이트, 풀 또는 컴퓨터)와 중앙 로깅 서비스에서 사용할 공급자를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="a3e74-105">Scenarios define the scope (that is, global, site, pool, or computer) and what providers to use in the Centralized Logging Service.</span></span> <span data-ttu-id="a3e74-106">시나리오를 사용하면 공급자(예: S4, SIPStack, IM 및 현재 상태)에서 추적을 사용하도록 설정하거나 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3e74-106">By using scenarios, you enable or disable tracing on providers (for example, S4, SIPStack, IM, and Presence).</span></span> <span data-ttu-id="a3e74-107">시나리오를 구성하여 특정 문제 조건을 해결하는 특정 논리 컬렉션에 대한 모든 공급자를 그룹화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3e74-107">By configuring a scenario, you can group all of the providers for a given logical collection that address a specific problem condition.</span></span> <span data-ttu-id="a3e74-108">문제 해결 및 로깅 요구 사항을 충족하기 위해 시나리오를 수정해야 하는 경우 비즈니스용 Skype 서버 2015 디버그 도구는Edit-CsClsScenario라는 함수를 포함하는 clsScenarioEdit.psm1이라는 Windows PowerShell 모듈을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a3e74-108">If you find that a scenario needs to be modified to meet your troubleshooting and logging needs, the Skype for Business Server 2015 Debug Tools provides you a Windows PowerShell module named ClsScenarioEdit.psm1 that contains a function namedEdit-CsClsScenario.</span></span> <span data-ttu-id="a3e74-109">모듈의 목적은 명명된 시나리오의 속성을 편집하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="a3e74-109">The purpose of the module is to edit the properties of the named scenario.</span></span> <span data-ttu-id="a3e74-110">이 항목에서는 이 모듈의 작동 방식에 대한 예제를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a3e74-110">Examples of how this module works are provided in this topic.</span></span> <span data-ttu-id="a3e74-111">더 이상 진행하기 전에 비즈니스용 [](https://go.microsoft.com/fwlink/p/?LinkId=285257) Skype 서버 2015 디버깅 도구를 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="a3e74-111">Download the Skype for Business Server 2015 [Debugging Tools](https://go.microsoft.com/fwlink/p/?LinkId=285257) before going any further.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="a3e74-112">특정 범위(사이트, 전역, 풀 또는 컴퓨터)에 대해 특정 시기에 최대 두 개의 시나리오를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3e74-112">For any given scope—site, global, pool or computer—you can run a maximum of two scenarios at any given time.</span></span> <span data-ttu-id="a3e74-113">현재 실행 중인 시나리오를 확인하기 위해 Windows PowerShell [및 Get-CsClsScenario를 사용 합니다.](/powershell/module/skype/get-csclsscenario?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="a3e74-113">To determine which scenarios are currently running, use Windows PowerShell and [Get-CsClsScenario](/powershell/module/skype/get-csclsscenario?view=skype-ps).</span></span> <span data-ttu-id="a3e74-114">[Set-Windows PowerShell 및 Set-CsClsScenario를](/powershell/module/skype/set-csclsscenario?view=skype-ps)사용하면 실행 중인 시나리오를 동적으로 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3e74-114">By using Windows PowerShell and [Set-CsClsScenario](/powershell/module/skype/set-csclsscenario?view=skype-ps), you can dynamically change which scenarios are running.</span></span> <span data-ttu-id="a3e74-115">로깅 세션 중에 실행 중인 시나리오를 수정하여 수집 중인 데이터를 조정하거나 구체화하고 공급자를 구체화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3e74-115">You can modify which scenarios are running during a logging session to adjust or refine the data you are collecting and from which providers.</span></span> 
  
<span data-ttu-id="a3e74-116">비즈니스용 Skype 서버 관리 셸을 사용하여 중앙 로깅 서비스 기능을 실행하려면 CsAdministrator 또는 CsServerAdministrator RBAC(역할 기반 액세스 제어) 보안 그룹 또는 이러한 두 그룹 중 하나를 포함하는 사용자 지정 RBAC 역할의 구성원이 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3e74-116">To run the Centralized Logging Service functions by using the Skype for Business Server Management Shell, you must be a member of either the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> <span data-ttu-id="a3e74-117">직접 만든 사용자 지정 RBAC 역할을 포함하여 이 cmdlet이 할당된 모든 RBAC 역할의 목록을 반환하기 위해 비즈니스용 Skype 서버 관리 셸 또는 Windows PowerShell 프롬프트에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="a3e74-117">To return a list of all the RBAC roles this cmdlet has been assigned to, including any custom RBAC roles you have created yourself, run the following command from the Skype for Business Server Management Shell or the Windows PowerShell prompt:</span></span>
  
```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Skype for Business Server 2015 cmdlet"}
```

<span data-ttu-id="a3e74-118">예:</span><span class="sxs-lookup"><span data-stu-id="a3e74-118">For example:</span></span>
  
```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

<span data-ttu-id="a3e74-119">이 항목의 나머지에서는 시나리오를 정의하고, 시나리오를 수정하고, 실행 중인 시나리오를 검색하고, 시나리오를 제거하고, 문제 해결을 최적화하기 위해 시나리오에 포함된 항목을 지정하는 방법에 대해 중점적으로 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a3e74-119">The remainder of this topic focuses on how to define a scenario, modify a scenario, retrieve what scenarios are running, remove a scenario, and specify what a scenario contains to optimize your troubleshooting.</span></span> <span data-ttu-id="a3e74-120">비즈니스용 Skype 서버 관리 셸을 사용하여 비즈니스용 Skype 서버 Windows PowerShell 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3e74-120">You can use the Skype for Business Server Management Shell to issue Windows PowerShell commands.</span></span> <span data-ttu-id="a3e74-121">로깅 Windows PowerShell 로깅 세션에서 사용할 새 시나리오를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3e74-121">When you use Windows PowerShell, you can define new scenarios for use in your logging sessions.</span></span>
  
<span data-ttu-id="a3e74-122">비즈니스용 [Skype 2015의](centralized-logging-service.md)중앙 로깅 서비스에 도입된 시나리오의 요소는 다음입니다.</span><span class="sxs-lookup"><span data-stu-id="a3e74-122">As introduced in [Centralized Logging Service in Skype for Business 2015](centralized-logging-service.md), the elements of a scenario are:</span></span>
  
- <span data-ttu-id="a3e74-123">**공급자** OCSLogger에 익숙한 경우 공급자는 추적 엔진이 로그를 수집할지 OCSLogger에 알려 주기 위해 선택하는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="a3e74-123">**Providers** If you are familiar with OCSLogger, providers are the components that you choose to tell OCSLogger what the tracing engine should collect logs from.</span></span> <span data-ttu-id="a3e74-124">공급자는 동일한 구성 요소로, 대부분의 경우 OCSLogger의 구성 요소와 이름이 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a3e74-124">The providers are the same components, and in many cases have the same name as the components in OCSLogger.</span></span> <span data-ttu-id="a3e74-125">OCSLogger에 익숙하지 않은 경우 공급자는 중앙 로깅 서비스에서 로그를 수집할 수 있는 서버 역할별 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="a3e74-125">If you are not familiar with OCSLogger, providers are server role specific components that the Centralized Logging Service can collect logs from.</span></span> <span data-ttu-id="a3e74-126">공급자 구성에 대한 자세한 내용은 [Configure providers for Centralized Logging Service in Skype for Business Server 2015을 참조하세요.](configure-providers.md)</span><span class="sxs-lookup"><span data-stu-id="a3e74-126">For details about the configuration of providers, see [Configure providers for Centralized Logging Service in Skype for Business Server 2015](configure-providers.md).</span></span>
    
- <span data-ttu-id="a3e74-127">**ID** 매개 변수 -Identity는 시나리오의 범위와 이름을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="a3e74-127">**Identity** The parameter -Identity sets the scope and name of the scenario.</span></span> <span data-ttu-id="a3e74-128">예를 들어 범위를 "global"으로 설정하고 시나리오를 "LyssServiceScenario"로 식별할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3e74-128">For example, you could set a scope of "global" and identify the scenario with "LyssServiceScenario".</span></span> <span data-ttu-id="a3e74-129">이 두 가지를 결합할 때 ID를 정의합니다(예: "global/LyssServiceScenario").</span><span class="sxs-lookup"><span data-stu-id="a3e74-129">When you combine the two, you define the Identity (for example, "global/LyssServiceScenario").</span></span>
    
    <span data-ttu-id="a3e74-130">원하는 경우 -Name 및 -Parent 매개 변수를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3e74-130">Optionally, you can use the -Name and -Parent parameters.</span></span> <span data-ttu-id="a3e74-131">Name 매개 변수를 정의하여 시나리오를 고유하게 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="a3e74-131">You define the Name parameter to uniquely identify the scenario.</span></span> <span data-ttu-id="a3e74-132">Name을 사용하는 경우 Parent를 사용하여 전역 또는 사이트에 시나리오를 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3e74-132">If you use Name, you must also use Parent to add the scenario to either global or site.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="a3e74-133">Name 및 Parent 매개 변수를 사용하는 경우 **-Identity** 매개 변수를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a3e74-133">If you use the Name and Parent parameters, you cannot use the **-Identity** parameter.</span></span>
  
### <a name="to-create-a-new-scenario-with-the-new-csclsscenario-cmdlet"></a><span data-ttu-id="a3e74-134">cmdlet을 사용하여 새 시나리오를 New-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="a3e74-134">To create a new scenario with the New-CsClsScenario cmdlet</span></span>

1. <span data-ttu-id="a3e74-135">비즈니스용 Skype 서버 관리 셸 시작: **시작,** 모든 **프로그램,** 비즈니스용 **Skype 2015,** 비즈니스용 Skype 서버 관리 셸을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="a3e74-135">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="a3e74-136">로깅 세션에 대한 새 시나리오를 만들 경우 [New-CsClsProvider를](/powershell/module/skype/new-csclsprovider?view=skype-ps) 사용하여 시나리오의 이름(즉, 고유하게 식별되는 방법)을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="a3e74-136">To create a new scenario for a logging session, use [New-CsClsProvider](/powershell/module/skype/new-csclsprovider?view=skype-ps) and define the name of the scenario (that is, how it will be uniquely identified).</span></span> <span data-ttu-id="a3e74-137">WPP에서 로깅 형식(즉, Windows 소프트웨어 추적 전 처리기 및 기본값), EventLog(즉, Windows 이벤트 로그 형식) 또는 IISLog(즉, IIS 로그 파일 형식을 기반으로 하는 ASCII 형식 파일)를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a3e74-137">Choose a type of logging format from WPP (that is, Windows software tracing preprocessor and is the default), EventLog (that is, Windows event log format), or IISLog (that is, ASCII format file based on the IIS log file format).</span></span> <span data-ttu-id="a3e74-138">그런 다음 Level(이 항목의 로깅 수준에 정의된 수준) 및 플래그(이 항목의 플래그에 정의되어 있는 경우)를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="a3e74-138">Next, define Level (as the defined under Logging Levels in this topic), and Flags (as defined under Flags in this topic).</span></span>
    
    <span data-ttu-id="a3e74-139">이 예제 시나리오에서는 예제 공급자 변수로 LyssProvider를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a3e74-139">For this example scenario, we use LyssProvider as the example provider variable.</span></span>
    
    <span data-ttu-id="a3e74-140">정의된 옵션을 사용하여 시나리오를 만들 경우 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="a3e74-140">To create a scenario using the options defined, type:</span></span>
    
   ```PowerShell
   New-CsClsScenario -Identity <scope>/<unique scenario name> -Provider <provider variable>
   ```

    <span data-ttu-id="a3e74-141">예:</span><span class="sxs-lookup"><span data-stu-id="a3e74-141">For example:</span></span>
    
   ```PowerShell
   New-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider $LyssProvider
   ```

    <span data-ttu-id="a3e74-142">-Name 및 -Parent를 사용하는 대체 형식:</span><span class="sxs-lookup"><span data-stu-id="a3e74-142">The alternate format using -Name and -Parent:</span></span>
    
   ```PowerShell
   New-CsClsScenario -Name "LyssServiceScenario" -Parent "site:Redmond" -Provider $LyssProvider
   ```

### <a name="to-create-a-new-scenario-with-multiple-providers-with-the-new-csclsscenario-cmdlet"></a><span data-ttu-id="a3e74-143">cmdlet을 사용하여 여러 공급자를 사용하여 새 시나리오를 New-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="a3e74-143">To create a new scenario with multiple providers with the New-CsClsScenario cmdlet</span></span>

1. <span data-ttu-id="a3e74-144">비즈니스용 Skype 서버 관리 셸 시작: **시작,** 모든 **프로그램,** 비즈니스용 **Skype 2015,** 비즈니스용 Skype 서버 관리 셸을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="a3e74-144">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="a3e74-145">범위당 두 가지 시나리오로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3e74-145">You are limited to two scenarios per scope.</span></span> <span data-ttu-id="a3e74-146">그러나 설정된 수의 공급자로 제한되지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a3e74-146">However, you are not limited to a set number of providers.</span></span> <span data-ttu-id="a3e74-147">이 예제에서는 세 개의 공급자를 만들었다고 가정하고 정의하는 시나리오에 세 공급자를 모두 할당하려는 경우를 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="a3e74-147">In this example, assume that we have created three providers, and you want to assign all three to the scenario you are defining.</span></span> <span data-ttu-id="a3e74-148">공급자 변수 이름은 LyssProvider, ABServerProvider 및 SIPStackProvider입니다.</span><span class="sxs-lookup"><span data-stu-id="a3e74-148">The provider variable names are LyssProvider, ABServerProvider, and SIPStackProvider.</span></span> <span data-ttu-id="a3e74-149">시나리오에 여러 공급자를 정의하고 할당하기 위해 비즈니스용 Skype 서버 관리 셸 또는 명령 프롬프트에 Windows PowerShell 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="a3e74-149">To define and assign multiple providers to a scenario, type the following at a Skype for Business Server Management Shell or Windows PowerShell command prompt:</span></span>
    
   ```PowerShell
   New-CsClsScenario -Identity "site:Redmond/CollectDataScenario" -Provider @{Add=$LyssProvider, $ABServerProvider,  $SIPStackProvider}
   ```

    > [!NOTE]
    > <span data-ttu-id="a3e74-150">이 규칙은 Windows PowerShell 사용하여 값의 해시 테이블을 만드는 규칙을  `@{<variable>=<value1>, <value2>, <value>…}` assplatting라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3e74-150">As it is known in Windows PowerShell, the convention for creating a hash table of values using  `@{<variable>=<value1>, <value2>, <value>…}` is known assplatting.</span></span> <span data-ttu-id="a3e74-151">2016의 스플래팅에 대한 자세한 Windows PowerShell 를 [https://go.microsoft.com/fwlink/p/?LinkId=267760](/previous-versions/technet-magazine/gg675931(v=msdn.10)) 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="a3e74-151">For details about splatting in Windows PowerShell, see [https://go.microsoft.com/fwlink/p/?LinkId=267760](/previous-versions/technet-magazine/gg675931(v=msdn.10)).</span></span> 
  
### <a name="to-modify-an-existing-scenario-with-the-set-csclsscenario-cmdlet"></a><span data-ttu-id="a3e74-152">cmdlet을 통해 기존 시나리오를 Set-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="a3e74-152">To modify an existing scenario with the Set-CsClsScenario cmdlet</span></span>

1. <span data-ttu-id="a3e74-153">비즈니스용 Skype 서버 관리 셸 시작: **시작,** 모든 **프로그램,** 비즈니스용 **Skype 2015,** 비즈니스용 Skype 서버 관리 셸을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="a3e74-153">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="a3e74-154">범위당 두 가지 시나리오로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3e74-154">You are limited to two scenarios per scope.</span></span> <span data-ttu-id="a3e74-155">로깅 캡처 세션이 진행 중인 경우에도 언제든 실행 중인 시나리오를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3e74-155">You can change which scenarios are running at any time, even when a logging capture session is in process.</span></span> <span data-ttu-id="a3e74-156">실행 중인 시나리오를 다시 디자인하면 현재 로깅 세션에서 제거된 시나리오의 사용을 중지한 다음 새 시나리오 사용을 시작하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3e74-156">If you redefine the running scenarios, the current logging session will stop using the scenario that was removed and then begin using the new scenario.</span></span> <span data-ttu-id="a3e74-157">그러나 제거된 시나리오로 캡처된 로깅 정보는 캡처된 로그에 남아 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3e74-157">However, the logging information that was captured with the removed scenario remains in the captured logs.</span></span> <span data-ttu-id="a3e74-158">새 시나리오를 정의하기 위해 다음을(즉, "S4Provider"라는 이미 정의된 공급자를 추가하는 경우) 다음을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a3e74-158">To define a new scenario, do the following (that is, assuming the addition of an already defined provider named "S4Provider"):</span></span>
    
   ```PowerShell
   Set-CsClsScenario -Identity <name of scope and scenario defined by New-CsClsScenario> -Provider @{Add=<new provider to add>}
   ```

    <span data-ttu-id="a3e74-159">예:</span><span class="sxs-lookup"><span data-stu-id="a3e74-159">For example:</span></span>
    
   ```PowerShell
   Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Add=$S4Provider}
   ```

    <span data-ttu-id="a3e74-160">공급자를 대체하려는 경우 현재 집합을 대체할 단일 공급자 또는 콤보로 구분된 공급자 목록을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="a3e74-160">If you want to replace providers, define a single provider or a comma separated list of providers to replace the current set.</span></span> <span data-ttu-id="a3e74-161">여러 공급자 중 하나만 교체하려는 경우 현재 공급자를 새 공급자로 추가하여 새 공급자와 기존 공급자를 모두 포함하는 새 공급자 집합을 만드면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3e74-161">If you only want to replace one of many providers, add the current providers with the new providers to create a new set of providers that contains both new providers and existing providers.</span></span> <span data-ttu-id="a3e74-162">모든 공급자를 새 집합으로 바꾸기 위해 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="a3e74-162">To replace all providers with a new set, type the following:</span></span>
    
   ```PowerShell
   Set-CsClsScenario -Identity <name of scope and scenario defined by New-CsClsScenario> -Provider @{Replace=<providers to replace existing provider set>}
   ```

    <span data-ttu-id="a3e74-163">예를 들어 현재 $LyssProvider, $ABServerProvider 및 $SIPStackProvider $LyssServiceProvider.</span><span class="sxs-lookup"><span data-stu-id="a3e74-163">For example, to replace the current set of $LyssProvider, $ABServerProvider, and $SIPStackProvider with $LyssServiceProvider:</span></span>
    
   ```PowerShell
   Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Replace=$LyssServiceProvider}
   ```

    <span data-ttu-id="a3e74-164">현재 $LyssProvider, $ABServerProvider 및 $SIPStackProvider 집합의 $LyssProvider 공급자만 $LyssServiceProvider 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="a3e74-164">To replace just the $LyssProvider provider from the current set of $LyssProvider, $ABServerProvider, and $SIPStackProvider with $LyssServiceProvider, type the following:</span></span>
    
   ```PowerShell
   Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Replace=$LyssServiceProvider, $ABServerProvider, $SIPStackProvider}
   ```

### <a name="to-remove-an-existing-scenario-with-the-remove-csclsscenario-cmdlet"></a><span data-ttu-id="a3e74-165">cmdlet을 사용하여 기존 시나리오를 Remove-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="a3e74-165">To remove an existing scenario with the Remove-CsClsScenario cmdlet</span></span>

1. <span data-ttu-id="a3e74-166">비즈니스용 Skype 서버 관리 셸 시작: **시작,** 모든 **프로그램,** 비즈니스용 **Skype 2015,** 비즈니스용 Skype 서버 관리 셸을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="a3e74-166">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="a3e74-167">이전에 정의한 시나리오를 제거하려면 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="a3e74-167">If you want to remove a scenario that has been previously defined, type the following:</span></span>
    
   ```PowerShell
   Remove-CsClsScenario -Identity <name of scope and scenario>
   ```

    <span data-ttu-id="a3e74-168">예를 들어 정의된 시나리오 site:Redmond/LyssServiceScenario를 제거하려면</span><span class="sxs-lookup"><span data-stu-id="a3e74-168">For example, to remove the defined scenario site:Redmond/LyssServiceScenario:</span></span>
    
   ```PowerShell
   Remove-CsClsScenario -Identity "site:Redmond/LyssServiceScenario"
   ```

<span data-ttu-id="a3e74-169">**Remove-CsClsScenario** cmdlet은 지정된 시나리오를 제거하지만, 캡처된 추적은 로그에서 계속 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3e74-169">The **Remove-CsClsScenario** cmdlet removes the specified scenario, but the traces that have been captured are still available in the logs for you to search on.</span></span>
### <a name="to-load-and-unload-the-edit-csclsscenario-cmdlet-using-the-clsscenarioeditpsm1-module"></a><span data-ttu-id="a3e74-170">ClsScenarioEdit.psm1 Edit-CsClsScenario cmdlet을 로드하고 언로드</span><span class="sxs-lookup"><span data-stu-id="a3e74-170">To load and unload the Edit-CsClsScenario cmdlet using the ClsScenarioEdit.psm1 module</span></span>

1. <span data-ttu-id="a3e74-171">비즈니스용 Skype 서버 관리 셸 시작: **시작,** 모든 **프로그램,** 비즈니스용 **Skype 2015,** 비즈니스용 Skype 서버 관리 셸을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="a3e74-171">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="a3e74-172">ClsScenarioEdit.psm1 모듈은 별도의 웹 다운로드로 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3e74-172">The ClsScenarioEdit.psm1 module is provided as a separate Web download.</span></span> <span data-ttu-id="a3e74-173">모듈은 비즈니스용 Skype 서버 2015 디버깅 도구의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="a3e74-173">The module is part of the Skype for Business Server 2015 Debugging tools.</span></span> <span data-ttu-id="a3e74-174">기본적으로 디버깅 도구는 C:\Program Files\Skype for Business Server 2015\Debugging Tools 디렉터리에 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3e74-174">By default, the debugging tools are installed in the directory C:\Program Files\Skype for Business Server 2015\Debugging Tools.</span></span> 
  
2. <span data-ttu-id="a3e74-175">다음 Windows PowerShell 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="a3e74-175">From the Windows PowerShell, type:</span></span>
    
   ```PowerShell
   Import-Module "CDBurn\OCO\amd64\Support"
   ```

    > [!TIP]
    > <span data-ttu-id="a3e74-176">모듈을 로드하면 명령 프롬프트가 Windows PowerShell 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3e74-176">Successful loading of the module returns you to the Windows PowerShell command prompt.</span></span> <span data-ttu-id="a3e74-177">모듈이 로드되어 있으며 사용 가능한 Edit-CsClsScenario 확인을 위해 를  `Get-Help Edit-CsClsScenario` 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="a3e74-177">To confirm that the module is loaded and that Edit-CsClsScenario is available, type  `Get-Help Edit-CsClsScenario`.</span></span> <span data-ttu-id="a3e74-178">EditCsClsScenario 구문의 기본 동의어가 표시해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3e74-178">You should see the basic synopsis of the syntax for EditCsClsScenario.</span></span> 
  
3. <span data-ttu-id="a3e74-179">모듈을 언로드하기 위해 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="a3e74-179">To unload the modules, type:</span></span>
    
   ```PowerShell
   Remove-Module ClsController
   ```

    > [!TIP]
    > <span data-ttu-id="a3e74-180">모듈을 성공적으로 언로드하면 명령 프롬프트로 Windows PowerShell 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3e74-180">Successful unloading of the module returns you to the Windows PowerShell command prompt.</span></span> <span data-ttu-id="a3e74-181">모듈이 언로드된 것이면 을  `Get-Help Edit-CsClsScenario` 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="a3e74-181">To confirm that the module is unloaded, type  `Get-Help Edit-CsClsScenario`.</span></span> <span data-ttu-id="a3e74-182">Windows PowerShell cmdlet에 대한 도움말을 찾으며 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="a3e74-182">Windows PowerShell will attempt to locate the help for the cmdlet and fail.</span></span> 
  
### <a name="to-remove-an-existing-provider-from-a-scenario-with-the-edit-clscontroller-module"></a><span data-ttu-id="a3e74-183">모듈을 사용하여 시나리오에서 기존 공급자를 Edit-ClsController</span><span class="sxs-lookup"><span data-stu-id="a3e74-183">To remove an existing provider from a scenario with the Edit-ClsController module</span></span>

1. <span data-ttu-id="a3e74-184">비즈니스용 Skype 서버 관리 셸 시작: **시작,** 모든 **프로그램,** 비즈니스용 **Skype 2015,** 비즈니스용 Skype 서버 관리 셸을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="a3e74-184">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="a3e74-185">다음 Windows PowerShell 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="a3e74-185">From the Windows PowerShell, type:</span></span>
    
   ```PowerShell
   Import-Module "CDBurn\OCO\amd64\Support"
   ```

    > [!TIP]
    > <span data-ttu-id="a3e74-186">모듈을 로드하면 명령 프롬프트가 Windows PowerShell 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3e74-186">Successful loading of the module returns you to the Windows PowerShell command prompt.</span></span> <span data-ttu-id="a3e74-187">모듈이 로드되어 있으며 사용 가능한 Edit-CsClsScenario 확인을 위해 를  `Get-Help Edit-CsClsScenario` 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="a3e74-187">To confirm that the module is loaded and that Edit-CsClsScenario is available, type  `Get-Help Edit-CsClsScenario`.</span></span> <span data-ttu-id="a3e74-188">EditCsClsScenario 구문의 기본 동의어가 표시해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3e74-188">You should see the basic synopsis of the syntax for EditCsClsScenario.</span></span> 
  
3. <span data-ttu-id="a3e74-189">AlwaysOn 시나리오에서 공급자를 제거하려면 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="a3e74-189">To remove a provider from the AlwaysOn scenario, type:</span></span>
    
   ```PowerShell
   Edit-CsClsScenario -ScenarioName <string of the scenario to edit> -ProviderName <string of the provider to remove> -Remove
   ```

   <span data-ttu-id="a3e74-190">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="a3e74-190">For Example:</span></span>
    
   ```PowerShell
   Edit-CsClsScenario -ScenarioName AlwaysOn -ProviderName ChatServer -Remove
   ```

   <span data-ttu-id="a3e74-191">ScenarioName 및 ProviderName 매개 변수는 명령줄의 예상 위치에 정의되어야 하는 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="a3e74-191">The parameters ScenarioName and ProviderName are positional (that is, they must be defined in the expected position in the command line) parameters.</span></span> <span data-ttu-id="a3e74-192">시나리오 이름이 위치 2에 있으며 공급자가 위치 3에 있는 경우 위치 1로 cmdlet의 이름을 상대로 매개 변수 이름을 명시적으로 정의할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a3e74-192">The parameter name does not have to be explicitly defined if the scenario name is in position two and the provider is in position three, relative to the name of the cmdlet as position one.</span></span> <span data-ttu-id="a3e74-193">이 정보를 사용하여 이전 명령은 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="a3e74-193">Using this information, the previous command would be typed as:</span></span>
    
   ```PowerShell
   Edit-CsClsScenario AlwaysOn ChatServer -Remove
   ```

   <span data-ttu-id="a3e74-194">매개 변수 값의 위치 배치는 -Scenario 및 -Provider에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3e74-194">The positional placing of the parameter values applies only to -Scenario and -Provider.</span></span> <span data-ttu-id="a3e74-195">다른 모든 매개 변수는 명시적으로 정의되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3e74-195">All other parameters must be explicitly defined.</span></span>
    
### <a name="to-add-a-provider-to-a-scenario-with-the-edit-clscontroller-module"></a><span data-ttu-id="a3e74-196">모듈을 사용하여 시나리오에 공급자를 Edit-ClsController</span><span class="sxs-lookup"><span data-stu-id="a3e74-196">To add a provider to a scenario with the Edit-ClsController module</span></span>

1. <span data-ttu-id="a3e74-197">비즈니스용 Skype 서버 관리 셸 시작: **시작,** 모든 **프로그램,** 비즈니스용 **Skype 2015,** 비즈니스용 Skype 서버 관리 셸을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="a3e74-197">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="a3e74-198">AlwaysOn 시나리오에 공급자를 추가하기 위해 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="a3e74-198">To add a provider to the AlwaysOn scenario, type:</span></span>
    
   ```PowerShell
   Edit-CsClsScenario -ScenarioName <string of the scenario to edit> -ProviderName <string of the provider to add> -Level <string of type level> -Flags <string of type flags>
   ```

    <span data-ttu-id="a3e74-199">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="a3e74-199">For Example:</span></span>
    
   ```PowerShell
   Edit-CsClsScenario -ScenarioName AlwaysOn -ProviderName ChatServer -Level Info -Flags TF_COMPONENT
   ```

    <span data-ttu-id="a3e74-200">-Loglevel은 Fatal, Error, Warning, Info, Verbose, Debug 또는 All 유형일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3e74-200">-Loglevel can be of the type Fatal, Error, Warning, Info, Verbose, Debug, or All.</span></span> <span data-ttu-id="a3e74-201">-Flags는 공급자가 지원하는 플래그(예: TF_COMPONENT, TF_DIAG.</span><span class="sxs-lookup"><span data-stu-id="a3e74-201">-Flags can be any of the flags that the provider supports, such as TF_COMPONENT, TF_DIAG.</span></span> <span data-ttu-id="a3e74-202">-Flags는 ALL 값일 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3e74-202">-Flags can also be of value ALL</span></span>
    
   <span data-ttu-id="a3e74-203">이전 예제는 cmdlet의 위치 기능을 사용하여 입력할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3e74-203">The previous example can also be typed using the positional feature of the cmdlet.</span></span> <span data-ttu-id="a3e74-204">예를 들어 AlwaysOn 시나리오에 공급자 ChatServer를 추가하기 위해 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="a3e74-204">For example, to add the provider ChatServer to the AlwaysOn scenario, type:</span></span>
    
   ```PowerShell
   Edit-CsClsScenario AlwaysOn ChatServer -Level Info -Flags ALL
   ```