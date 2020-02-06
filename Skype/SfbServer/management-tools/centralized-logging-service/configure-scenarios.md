---
title: 비즈니스용 Skype 2015에서 중앙 로깅 서비스에 대한 시나리오 구성
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: '요약: 비즈니스용 Skype 서버 2015에서 중앙 집중화 된 로깅 서비스에 대 한 시나리오를 만들고, 수정 하 고, 제거 하는 방법에 대해 알아봅니다.'
ms.openlocfilehash: b7cfcbc85df7d66374d2bf33d572b9e91b30edde
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816597"
---
# <a name="configure-scenarios-for-the-centralized-logging-service-in-skype-for-business-server-2015"></a><span data-ttu-id="4998d-103">비즈니스용 Skype 2015에서 중앙 로깅 서비스에 대한 시나리오 구성</span><span class="sxs-lookup"><span data-stu-id="4998d-103">Configure scenarios for the Centralized Logging Service in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="4998d-104">**요약:** 비즈니스용 Skype 서버 2015에서 중앙 집중화 된 로깅 서비스에 대 한 시나리오를 만들고, 수정 하 고, 제거 하는 방법에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="4998d-104">**Summary:** Learn how to create, modify, and remove scenarios for the Centralized Logging Service in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="4998d-105">시나리오는 범위 (즉, 전역, 사이트, 풀 또는 컴퓨터)와 중앙 로깅 서비스에서 사용할 공급자를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="4998d-105">Scenarios define the scope (that is, global, site, pool, or computer) and what providers to use in the Centralized Logging Service.</span></span> <span data-ttu-id="4998d-106">시나리오를 사용 하 여 공급자 (예: S4, SIPStack, IM, 현재 상태) 추적을 사용 하거나 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4998d-106">By using scenarios, you enable or disable tracing on providers (for example, S4, SIPStack, IM, and Presence).</span></span> <span data-ttu-id="4998d-107">시나리오를 구성 하 여 특정 문제 조건을 처리 하는 지정 된 논리 컬렉션에 대 한 모든 공급자를 그룹화 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4998d-107">By configuring a scenario, you can group all of the providers for a given logical collection that address a specific problem condition.</span></span> <span data-ttu-id="4998d-108">문제 해결 및 로깅 요구 사항에 맞게 시나리오를 수정 해야 하는 경우 비즈니스용 Skype 서버 2015 디버그 도구는 psm1-CsClsScenario 함수가 포함 된 ClsScenarioEdit 라는 Windows PowerShell 모듈을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="4998d-108">If you find that a scenario needs to be modified to meet your troubleshooting and logging needs, the Skype for Business Server 2015 Debug Tools provides you a Windows PowerShell module named ClsScenarioEdit.psm1 that contains a function namedEdit-CsClsScenario.</span></span> <span data-ttu-id="4998d-109">모듈의 목적은 명명 된 시나리오의 속성을 편집 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="4998d-109">The purpose of the module is to edit the properties of the named scenario.</span></span> <span data-ttu-id="4998d-110">이 모듈의 작동 방식에 대 한 예는이 항목에서 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="4998d-110">Examples of how this module works are provided in this topic.</span></span> <span data-ttu-id="4998d-111">Skype for Business Server 2015 [디버깅 도구](https://go.microsoft.com/fwlink/p/?LinkId=285257) 를 다운로드 한 후 더 자세히 진행 하세요.</span><span class="sxs-lookup"><span data-stu-id="4998d-111">Download the Skype for Business Server 2015 [Debugging Tools](https://go.microsoft.com/fwlink/p/?LinkId=285257) before going any further.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="4998d-112">지정 된 범위 (사이트, 전역, 풀 또는 컴퓨터)에 대해 지정 된 시간에 최대 두 개의 시나리오를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4998d-112">For any given scope—site, global, pool or computer—you can run a maximum of two scenarios at any given time.</span></span> <span data-ttu-id="4998d-113">현재 실행 중인 시나리오를 확인 하려면 Windows PowerShell 및 [가져오기-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/get-csclsscenario?view=skype-ps)를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4998d-113">To determine which scenarios are currently running, use Windows PowerShell and [Get-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/get-csclsscenario?view=skype-ps).</span></span> <span data-ttu-id="4998d-114">Windows PowerShell 및 [Set-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/set-csclsscenario?view=skype-ps)를 사용 하 여 실행 중인 시나리오를 동적으로 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4998d-114">By using Windows PowerShell and [Set-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/set-csclsscenario?view=skype-ps), you can dynamically change which scenarios are running.</span></span> <span data-ttu-id="4998d-115">기록 세션 중에 실행 되는 시나리오를 수정 하 여 수집 하 고 있는 데이터와 공급자를 조정 하거나 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4998d-115">You can modify which scenarios are running during a logging session to adjust or refine the data you are collecting and from which providers.</span></span> 
  
<span data-ttu-id="4998d-116">비즈니스용 Skype Server Management Shell을 사용 하 여 중앙 로깅 서비스 기능을 실행 하려면 CsAdministrator 또는 CsServerAdministrator 역할 기반 액세스 제어 (RBAC) 보안 그룹 또는 사용자 지정 RBAC 역할의 구성원 이어야 합니다. 두 그룹 중 하나를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="4998d-116">To run the Centralized Logging Service functions by using the Skype for Business Server Management Shell, you must be a member of either the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> <span data-ttu-id="4998d-117">직접 만든 사용자 지정 RBAC 역할을 포함 하 여이 cmdlet에 할당 된 모든 RBAC 역할 목록을 반환 하려면 비즈니스용 Skype Server 관리 셸 또는 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="4998d-117">To return a list of all the RBAC roles this cmdlet has been assigned to, including any custom RBAC roles you have created yourself, run the following command from the Skype for Business Server Management Shell or the Windows PowerShell prompt:</span></span>
  
```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Skype for Business Server 2015 cmdlet"}
```

<span data-ttu-id="4998d-118">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4998d-118">For example:</span></span>
  
```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

<span data-ttu-id="4998d-119">이 항목의 나머지 부분에서는 시나리오를 정의 하 고, 시나리오를 수정 하 고, 실행 중인 시나리오를 검색 하 고, 시나리오를 제거 하 고, 문제 해결을 최적화 하기 위해 시나리오가 포함할 항목을 지정 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="4998d-119">The remainder of this topic focuses on how to define a scenario, modify a scenario, retrieve what scenarios are running, remove a scenario, and specify what a scenario contains to optimize your troubleshooting.</span></span> <span data-ttu-id="4998d-120">비즈니스용 Skype Server Management Shell을 사용 하 여 Windows PowerShell 명령을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4998d-120">You can use the Skype for Business Server Management Shell to issue Windows PowerShell commands.</span></span> <span data-ttu-id="4998d-121">Windows PowerShell을 사용 하는 경우 로깅 세션에서 사용할 새 시나리오를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4998d-121">When you use Windows PowerShell, you can define new scenarios for use in your logging sessions.</span></span>
  
<span data-ttu-id="4998d-122">[비즈니스의 비즈니스용 Skype 2015 중앙 로깅 서비스](centralized-logging-service.md)에 도입 된 것 처럼 시나리오의 요소는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4998d-122">As introduced in [Centralized Logging Service in Skype for Business 2015](centralized-logging-service.md), the elements of a scenario are:</span></span>
  
- <span data-ttu-id="4998d-123">**공급자** OCSLogger 사용 하는 데 익숙한 경우 공급자는 OCSLogger 로그를 수집 하는 대상에 게 지정 하도록 선택 하는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="4998d-123">**Providers** If you are familiar with OCSLogger, providers are the components that you choose to tell OCSLogger what the tracing engine should collect logs from.</span></span> <span data-ttu-id="4998d-124">공급자는 동일한 구성 요소 이며, 대부분의 경우에는 OCSLogger 구성 요소와 동일한 이름을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4998d-124">The providers are the same components, and in many cases have the same name as the components in OCSLogger.</span></span> <span data-ttu-id="4998d-125">OCSLogger 익숙하지 않은 경우 공급자는 중앙 로깅 서비스가 로그를 수집할 수 있는 서버 역할 특정 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="4998d-125">If you are not familiar with OCSLogger, providers are server role specific components that the Centralized Logging Service can collect logs from.</span></span> <span data-ttu-id="4998d-126">공급자 구성에 대 한 자세한 내용은 비즈니스용 [Skype 서버 2015에서 중앙 집중화 된 로깅 서비스에 대 한 공급자 구성을](configure-providers.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4998d-126">For details about the configuration of providers, see [Configure providers for Centralized Logging Service in Skype for Business Server 2015](configure-providers.md).</span></span>
    
- <span data-ttu-id="4998d-127">**Id** 매개 변수 Id는 시나리오의 범위와 이름을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4998d-127">**Identity** The parameter -Identity sets the scope and name of the scenario.</span></span> <span data-ttu-id="4998d-128">예를 들어 "전역" 범위를 설정 하 고 "LyssServiceScenario"를 사용 하 여 시나리오를 식별할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4998d-128">For example, you could set a scope of "global" and identify the scenario with "LyssServiceScenario".</span></span> <span data-ttu-id="4998d-129">두 가지를 결합 하면 Id를 정의 합니다 (예: "global/LyssServiceScenario").</span><span class="sxs-lookup"><span data-stu-id="4998d-129">When you combine the two, you define the Identity (for example, "global/LyssServiceScenario").</span></span>
    
    <span data-ttu-id="4998d-130">선택적으로-Name 및-Parent 매개 변수를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4998d-130">Optionally, you can use the -Name and -Parent parameters.</span></span> <span data-ttu-id="4998d-131">Name 매개 변수를 정의 하 여 시나리오를 고유 하 게 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="4998d-131">You define the Name parameter to uniquely identify the scenario.</span></span> <span data-ttu-id="4998d-132">이름을 사용 하는 경우에는 Parent를 사용 하 여 전역 또는 사이트 중 하나에 시나리오를 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4998d-132">If you use Name, you must also use Parent to add the scenario to either global or site.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="4998d-133">Name 및 Parent 매개 변수를 사용 하는 경우 **-Identity** 매개 변수를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4998d-133">If you use the Name and Parent parameters, you cannot use the **-Identity** parameter.</span></span>
  
### <a name="to-create-a-new-scenario-with-the-new-csclsscenario-cmdlet"></a><span data-ttu-id="4998d-134">새-CsClsScenario cmdlet을 사용 하 여 새 시나리오를 만들려면</span><span class="sxs-lookup"><span data-stu-id="4998d-134">To create a new scenario with the New-CsClsScenario cmdlet</span></span>

1. <span data-ttu-id="4998d-135">비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **비즈니스용 skype 2015**을 차례로 클릭 한 다음 비즈니스용 **skype Server management Shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4998d-135">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="4998d-136">로깅 세션에 대 한 새 시나리오를 만들려면 [새 CsClsProvider](https://docs.microsoft.com/powershell/module/skype/new-csclsprovider?view=skype-ps) 를 사용 하 고 시나리오 이름 (즉, 고유 하 게 식별 되는 방법)을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="4998d-136">To create a new scenario for a logging session, use [New-CsClsProvider](https://docs.microsoft.com/powershell/module/skype/new-csclsprovider?view=skype-ps) and define the name of the scenario (that is, how it will be uniquely identified).</span></span> <span data-ttu-id="4998d-137">WPP (즉, Windows 소프트웨어 추적 전처리기를 사용 하는 경우 기본값), EventLog (Windows 이벤트 로그 형식) 또는 IISLog (즉, IIS 로그 파일 형식을 기반으로 하는 ASCII 형식 파일)의 로깅 형식 유형을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4998d-137">Choose a type of logging format from WPP (that is, Windows software tracing preprocessor and is the default), EventLog (that is, Windows event log format), or IISLog (that is, ASCII format file based on the IIS log file format).</span></span> <span data-ttu-id="4998d-138">다음으로,이 항목의 로깅 수준 아래에 정의 된 대로 수준을 정의 하 고이 항목의 Flags 아래에 정의 된 플래그를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4998d-138">Next, define Level (as the defined under Logging Levels in this topic), and Flags (as defined under Flags in this topic).</span></span>
    
    <span data-ttu-id="4998d-139">이 예제 시나리오에서는 예제 공급자 변수로 LyssProvider를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4998d-139">For this example scenario, we use LyssProvider as the example provider variable.</span></span>
    
    <span data-ttu-id="4998d-140">정의 된 옵션을 사용 하 여 시나리오를 만들려면 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="4998d-140">To create a scenario using the options defined, type:</span></span>
    
   ```PowerShell
   New-CsClsScenario -Identity <scope>/<unique scenario name> -Provider <provider variable>
   ```

    <span data-ttu-id="4998d-141">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4998d-141">For example:</span></span>
    
   ```PowerShell
   New-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider $LyssProvider
   ```

    <span data-ttu-id="4998d-142">-Name 및-Parent를 사용 하는 대체 형식은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4998d-142">The alternate format using -Name and -Parent:</span></span>
    
   ```PowerShell
   New-CsClsScenario -Name "LyssServiceScenario" -Parent "site:Redmond" -Provider $LyssProvider
   ```

### <a name="to-create-a-new-scenario-with-multiple-providers-with-the-new-csclsscenario-cmdlet"></a><span data-ttu-id="4998d-143">새-CsClsScenario cmdlet을 사용 하는 여러 공급자를 사용 하 여 새 시나리오를 만들려면</span><span class="sxs-lookup"><span data-stu-id="4998d-143">To create a new scenario with multiple providers with the New-CsClsScenario cmdlet</span></span>

1. <span data-ttu-id="4998d-144">비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **비즈니스용 skype 2015**을 차례로 클릭 한 다음 비즈니스용 **skype Server management Shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4998d-144">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="4998d-145">범위 당 두 개의 시나리오로 제한 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4998d-145">You are limited to two scenarios per scope.</span></span> <span data-ttu-id="4998d-146">그러나 설정 된 공급자 수로 제한 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4998d-146">However, you are not limited to a set number of providers.</span></span> <span data-ttu-id="4998d-147">이 예제에서는 세 개의 공급자를 만들었고이 세 가지를 정의 하는 시나리오에 모두 할당 하려고 한다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4998d-147">In this example, assume that we have created three providers, and you want to assign all three to the scenario you are defining.</span></span> <span data-ttu-id="4998d-148">공급자 변수 이름은 LyssProvider, ABServerProvider, SIPStackProvider입니다.</span><span class="sxs-lookup"><span data-stu-id="4998d-148">The provider variable names are LyssProvider, ABServerProvider, and SIPStackProvider.</span></span> <span data-ttu-id="4998d-149">시나리오에 여러 공급자를 정의 하 고 할당 하려면 비즈니스용 Skype 서버 관리 셸 또는 Windows PowerShell 명령 프롬프트에서 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="4998d-149">To define and assign multiple providers to a scenario, type the following at a Skype for Business Server Management Shell or Windows PowerShell command prompt:</span></span>
    
   ```PowerShell
   New-CsClsScenario -Identity "site:Redmond/CollectDataScenario" -Provider @{Add=$LyssProvider, $ABServerProvider,  $SIPStackProvider}
   ```

    > [!NOTE]
    > <span data-ttu-id="4998d-150">Windows PowerShell에서 알 수 있듯이, 사용 하 `@{<variable>=<value1>, <value2>, <value>…}` 는 해시 테이블 값을 만드는 규칙은 알려진 assplatting입니다.</span><span class="sxs-lookup"><span data-stu-id="4998d-150">As it is known in Windows PowerShell, the convention for creating a hash table of values using  `@{<variable>=<value1>, <value2>, <value>…}` is known assplatting.</span></span> <span data-ttu-id="4998d-151">Windows PowerShell의 splatting에 대 한 자세한 내용은 [https://go.microsoft.com/fwlink/p/?LinkId=267760](https://go.microsoft.com/fwlink/p/?LinkId=267760)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4998d-151">For details about splatting in Windows PowerShell, see [https://go.microsoft.com/fwlink/p/?LinkId=267760](https://go.microsoft.com/fwlink/p/?LinkId=267760).</span></span> 
  
### <a name="to-modify-an-existing-scenario-with-the-set-csclsscenario-cmdlet"></a><span data-ttu-id="4998d-152">Set-CsClsScenario cmdlet을 사용 하 여 기존 시나리오를 수정 하려면</span><span class="sxs-lookup"><span data-stu-id="4998d-152">To modify an existing scenario with the Set-CsClsScenario cmdlet</span></span>

1. <span data-ttu-id="4998d-153">비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **비즈니스용 skype 2015**을 차례로 클릭 한 다음 비즈니스용 **skype Server management Shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4998d-153">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="4998d-154">범위 당 두 개의 시나리오로 제한 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4998d-154">You are limited to two scenarios per scope.</span></span> <span data-ttu-id="4998d-155">로깅 캡처 세션이 진행 중인 경우에도 언제 든 지 실행 되는 시나리오를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4998d-155">You can change which scenarios are running at any time, even when a logging capture session is in process.</span></span> <span data-ttu-id="4998d-156">실행 중인 시나리오를 재정의 하는 경우 현재 로깅 세션은 제거 된 시나리오 사용을 중지 하 고 새 시나리오 사용을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="4998d-156">If you redefine the running scenarios, the current logging session will stop using the scenario that was removed and then begin using the new scenario.</span></span> <span data-ttu-id="4998d-157">그러나 제거 된 시나리오를 사용 하 여 캡처한 로깅 정보는 캡처한 로그에 남아 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4998d-157">However, the logging information that was captured with the removed scenario remains in the captured logs.</span></span> <span data-ttu-id="4998d-158">새 시나리오를 정의 하려면 다음을 수행 합니다 (즉, "S4Provider" 이라는 이미 정의 된 공급자가 추가 된 경우).</span><span class="sxs-lookup"><span data-stu-id="4998d-158">To define a new scenario, do the following (that is, assuming the addition of an already defined provider named "S4Provider"):</span></span>
    
   ```PowerShell
   Set-CsClsScenario -Identity <name of scope and scenario defined by New-CsClsScenario> -Provider @{Add=<new provider to add>}
   ```

    <span data-ttu-id="4998d-159">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4998d-159">For example:</span></span>
    
   ```PowerShell
   Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Add=$S4Provider}
   ```

    <span data-ttu-id="4998d-160">공급자를 바꾸려면 단일 공급자나 쉼표로 구분 된 공급자 목록을 정의 하 여 현재 집합을 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="4998d-160">If you want to replace providers, define a single provider or a comma separated list of providers to replace the current set.</span></span> <span data-ttu-id="4998d-161">여러 공급자 중 하나만 바꾸려면 새 공급자와 현재 공급자를 추가 하 여 새 공급자 및 기존 공급자를 모두 포함 하는 새 공급자 집합을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4998d-161">If you only want to replace one of many providers, add the current providers with the new providers to create a new set of providers that contains both new providers and existing providers.</span></span> <span data-ttu-id="4998d-162">모든 공급자를 새 집합으로 바꾸려면 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="4998d-162">To replace all providers with a new set, type the following:</span></span>
    
   ```PowerShell
   Set-CsClsScenario -Identity <name of scope and scenario defined by New-CsClsScenario> -Provider @{Replace=<providers to replace existing provider set>}
   ```

    <span data-ttu-id="4998d-163">예를 들어 현재 $LyssProvider 집합, $ABServerProvider 및 $SIPStackProvider을 $LyssServiceProvider로 바꾸려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="4998d-163">For example, to replace the current set of $LyssProvider, $ABServerProvider, and $SIPStackProvider with $LyssServiceProvider:</span></span>
    
   ```PowerShell
   Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Replace=$LyssServiceProvider}
   ```

    <span data-ttu-id="4998d-164">현재 $LyssProvider 집합에서 $LyssProvider 공급자로, $ABServerProvider, $LyssServiceProvider으로 $SIPStackProvider를 바꾸려면 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="4998d-164">To replace just the $LyssProvider provider from the current set of $LyssProvider, $ABServerProvider, and $SIPStackProvider with $LyssServiceProvider, type the following:</span></span>
    
   ```PowerShell
   Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Replace=$LyssServiceProvider, $ABServerProvider, $SIPStackProvider}
   ```

### <a name="to-remove-an-existing-scenario-with-the-remove-csclsscenario-cmdlet"></a><span data-ttu-id="4998d-165">제거-CsClsScenario cmdlet을 사용 하 여 기존 시나리오를 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="4998d-165">To remove an existing scenario with the Remove-CsClsScenario cmdlet</span></span>

1. <span data-ttu-id="4998d-166">비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **비즈니스용 skype 2015**을 차례로 클릭 한 다음 비즈니스용 **skype Server management Shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4998d-166">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="4998d-167">이전에 정의한 시나리오를 제거 하려면 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="4998d-167">If you want to remove a scenario that has been previously defined, type the following:</span></span>
    
   ```PowerShell
   Remove-CsClsScenario -Identity <name of scope and scenario>
   ```

    <span data-ttu-id="4998d-168">예를 들어 정의 된 시나리오 사이트를 제거 하려면: Redmond/LyssServiceScenario:</span><span class="sxs-lookup"><span data-stu-id="4998d-168">For example, to remove the defined scenario site:Redmond/LyssServiceScenario:</span></span>
    
   ```PowerShell
   Remove-CsClsScenario -Identity "site:Redmond/LyssServiceScenario"
   ```

<span data-ttu-id="4998d-169">지정 된 시나리오는 **제거-CsClsScenario** cmdlet을 통해 제거 되지만, 캡처한 추적은 검색에 사용할 수 있도록 로그에 남아 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4998d-169">The **Remove-CsClsScenario** cmdlet removes the specified scenario, but the traces that have been captured are still available in the logs for you to search on.</span></span>
### <a name="to-load-and-unload-the-edit-csclsscenario-cmdlet-using-the-clsscenarioeditpsm1-module"></a><span data-ttu-id="4998d-170">Psm1 모듈을 사용 하 여 편집-CsClsScenario cmdlet을 로드 하 고 언로드하려면 ClsScenarioEdit</span><span class="sxs-lookup"><span data-stu-id="4998d-170">To load and unload the Edit-CsClsScenario cmdlet using the ClsScenarioEdit.psm1 module</span></span>

1. <span data-ttu-id="4998d-171">비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **비즈니스용 skype 2015**을 차례로 클릭 한 다음 비즈니스용 **skype Server management Shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4998d-171">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="4998d-172">ClsScenarioEdit psm1 모듈은 별도의 웹 다운로드로 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4998d-172">The ClsScenarioEdit.psm1 module is provided as a separate Web download.</span></span> <span data-ttu-id="4998d-173">모듈은 비즈니스용 Skype 서버 2015 디버깅 도구의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="4998d-173">The module is part of the Skype for Business Server 2015 Debugging tools.</span></span> <span data-ttu-id="4998d-174">기본적으로 디버깅 도구는 Business Server 2015 용 C:\Program Files\Skype 디렉터리 디버깅 도구에 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4998d-174">By default, the debugging tools are installed in the directory C:\Program Files\Skype for Business Server 2015\Debugging Tools.</span></span> 
  
2. <span data-ttu-id="4998d-175">Windows PowerShell에서 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="4998d-175">From the Windows PowerShell, type:</span></span>
    
   ```PowerShell
   Import-Module "CDBurn\OCO\amd64\Support"
   ```

    > [!TIP]
    > <span data-ttu-id="4998d-176">모듈을 성공적으로 로드 하면 Windows PowerShell 명령 프롬프트로 돌아갑니다.</span><span class="sxs-lookup"><span data-stu-id="4998d-176">Successful loading of the module returns you to the Windows PowerShell command prompt.</span></span> <span data-ttu-id="4998d-177">모듈이 로드 되 고 편집-CsClsScenario을 사용할 수 있는지 확인 하려면 다음을 입력 `Get-Help Edit-CsClsScenario`합니다.</span><span class="sxs-lookup"><span data-stu-id="4998d-177">To confirm that the module is loaded and that Edit-CsClsScenario is available, type  `Get-Help Edit-CsClsScenario`.</span></span> <span data-ttu-id="4998d-178">EditCsClsScenario에 대 한 구문의 기본 synopsis를 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4998d-178">You should see the basic synopsis of the syntax for EditCsClsScenario.</span></span> 
  
3. <span data-ttu-id="4998d-179">모듈을 언로드하려면 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="4998d-179">To unload the modules, type:</span></span>
    
   ```PowerShell
   Remove-Module ClsController
   ```

    > [!TIP]
    > <span data-ttu-id="4998d-180">모듈을 성공적으로 언로드하면 Windows PowerShell 명령 프롬프트로 돌아갑니다.</span><span class="sxs-lookup"><span data-stu-id="4998d-180">Successful unloading of the module returns you to the Windows PowerShell command prompt.</span></span> <span data-ttu-id="4998d-181">모듈이 언로드되는 지 확인 하려면를 입력 `Get-Help Edit-CsClsScenario`합니다.</span><span class="sxs-lookup"><span data-stu-id="4998d-181">To confirm that the module is unloaded, type  `Get-Help Edit-CsClsScenario`.</span></span> <span data-ttu-id="4998d-182">Windows PowerShell에서 cmdlet에 대 한 도움말을 찾으려고 시도 하 고 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="4998d-182">Windows PowerShell will attempt to locate the help for the cmdlet and fail.</span></span> 
  
### <a name="to-remove-an-existing-provider-from-a-scenario-with-the-edit-clscontroller-module"></a><span data-ttu-id="4998d-183">ClsController 모듈을 사용 하 여 시나리오에서 기존 공급자를 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="4998d-183">To remove an existing provider from a scenario with the Edit-ClsController module</span></span>

1. <span data-ttu-id="4998d-184">비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **비즈니스용 skype 2015**을 차례로 클릭 한 다음 비즈니스용 **skype Server management Shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4998d-184">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="4998d-185">Windows PowerShell에서 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="4998d-185">From the Windows PowerShell, type:</span></span>
    
   ```PowerShell
   Import-Module "CDBurn\OCO\amd64\Support"
   ```

    > [!TIP]
    > <span data-ttu-id="4998d-186">모듈을 성공적으로 로드 하면 Windows PowerShell 명령 프롬프트로 돌아갑니다.</span><span class="sxs-lookup"><span data-stu-id="4998d-186">Successful loading of the module returns you to the Windows PowerShell command prompt.</span></span> <span data-ttu-id="4998d-187">모듈이 로드 되 고 편집-CsClsScenario을 사용할 수 있는지 확인 하려면 다음을 입력 `Get-Help Edit-CsClsScenario`합니다.</span><span class="sxs-lookup"><span data-stu-id="4998d-187">To confirm that the module is loaded and that Edit-CsClsScenario is available, type  `Get-Help Edit-CsClsScenario`.</span></span> <span data-ttu-id="4998d-188">EditCsClsScenario에 대 한 구문의 기본 synopsis를 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4998d-188">You should see the basic synopsis of the syntax for EditCsClsScenario.</span></span> 
  
3. <span data-ttu-id="4998d-189">AlwaysOn 시나리오에서 공급자를 제거 하려면 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="4998d-189">To remove a provider from the AlwaysOn scenario, type:</span></span>
    
   ```PowerShell
   Edit-CsClsScenario -ScenarioName <string of the scenario to edit> -ProviderName <string of the provider to remove> -Remove
   ```

   <span data-ttu-id="4998d-190">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="4998d-190">For Example:</span></span>
    
   ```PowerShell
   Edit-CsClsScenario -ScenarioName AlwaysOn -ProviderName ChatServer -Remove
   ```

   <span data-ttu-id="4998d-191">ScenarioName 및 ProviderName 매개 변수는 위치 (즉, 명령줄의 예상 위치에서 정의 되어야 함) 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="4998d-191">The parameters ScenarioName and ProviderName are positional (that is, they must be defined in the expected position in the command line) parameters.</span></span> <span data-ttu-id="4998d-192">시나리오 이름이 두 위치에 있고 공급자가 cmdlet의 이름을 위치 1로 기준으로 하는 3 위치에 있는 경우 매개 변수 이름을 명시적으로 정의할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4998d-192">The parameter name does not have to be explicitly defined if the scenario name is in position two and the provider is in position three, relative to the name of the cmdlet as position one.</span></span> <span data-ttu-id="4998d-193">이 정보를 사용 하 여 이전 명령은 다음과 같이 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="4998d-193">Using this information, the previous command would be typed as:</span></span>
    
   ```PowerShell
   Edit-CsClsScenario AlwaysOn ChatServer -Remove
   ```

   <span data-ttu-id="4998d-194">매개 변수 값을 배치 하는 위치는 Scenario 및-Provider에만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4998d-194">The positional placing of the parameter values applies only to -Scenario and -Provider.</span></span> <span data-ttu-id="4998d-195">다른 모든 매개 변수는 명시적으로 정의 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4998d-195">All other parameters must be explicitly defined.</span></span>
    
### <a name="to-add-a-provider-to-a-scenario-with-the-edit-clscontroller-module"></a><span data-ttu-id="4998d-196">ClsController 모듈을 사용 하 여 시나리오에 공급자를 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="4998d-196">To add a provider to a scenario with the Edit-ClsController module</span></span>

1. <span data-ttu-id="4998d-197">비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **비즈니스용 skype 2015**을 차례로 클릭 한 다음 비즈니스용 **skype Server management Shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4998d-197">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="4998d-198">AlwaysOn 시나리오에 공급자를 추가 하려면 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="4998d-198">To add a provider to the AlwaysOn scenario, type:</span></span>
    
   ```PowerShell
   Edit-CsClsScenario -ScenarioName <string of the scenario to edit> -ProviderName <string of the provider to add> -Level <string of type level> -Flags <string of type flags>
   ```

    <span data-ttu-id="4998d-199">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="4998d-199">For Example:</span></span>
    
   ```PowerShell
   Edit-CsClsScenario -ScenarioName AlwaysOn -ProviderName ChatServer -Level Info -Flags TF_COMPONENT
   ```

    <span data-ttu-id="4998d-200">-Loglevel은 치명적, 오류, 경고, 정보, 자세한 정보 표시, 디버그 또는 모두 유형이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4998d-200">-Loglevel can be of the type Fatal, Error, Warning, Info, Verbose, Debug, or All.</span></span> <span data-ttu-id="4998d-201">-Flags는 공급자가 지 원하는 플래그 (예: TF_COMPONENT TF_DIAG) 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4998d-201">-Flags can be any of the flags that the provider supports, such as TF_COMPONENT, TF_DIAG.</span></span> <span data-ttu-id="4998d-202">-Flags는 모두 값 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4998d-202">-Flags can also be of value ALL</span></span>
    
   <span data-ttu-id="4998d-203">앞의 예제는 cmdlet의 위치 기능을 사용 하 여 입력할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4998d-203">The previous example can also be typed using the positional feature of the cmdlet.</span></span> <span data-ttu-id="4998d-204">예를 들어, AlwaysOn 시나리오에 공급자 이름 서버를 추가 하려면 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="4998d-204">For example, to add the provider ChatServer to the AlwaysOn scenario, type:</span></span>
    
   ```PowerShell
   Edit-CsClsScenario AlwaysOn ChatServer -Level Info -Flags ALL
   ```
