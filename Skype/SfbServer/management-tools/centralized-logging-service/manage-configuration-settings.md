---
title: 비즈니스용 Skype 서버에서 중앙 로깅 서비스 구성 설정 관리
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 8/17/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 93b9a354-9aea-4b3a-a4fe-68a89f436196
description: '요약: 비즈니스용 Skype 서버 2015에서 중앙 로깅 서비스에 대한 구성 설정을 검색, 업데이트 및 만드는 방법을 설명하는 정보를 제공합니다.'
ms.openlocfilehash: dd292465d65116dc1f497a733ca8e010e57b9137
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49835158"
---
# <a name="manage-centralized-logging-service-configuration-settings-in-skype-for-business-server-2015"></a><span data-ttu-id="7d674-103">비즈니스용 Skype 서버에서 중앙 로깅 서비스 구성 설정 관리</span><span class="sxs-lookup"><span data-stu-id="7d674-103">Manage Centralized Logging Service configuration settings in Skype for Business Server 2015</span></span>

<span data-ttu-id="7d674-104">**요약:** 비즈니스용 Skype 서버 2015에서 중앙 로깅 서비스에 대한 구성 설정을 검색, 업데이트 및 만드는 방법을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="7d674-104">**Summary:** Learn how to retrieve, update, and create configuration settings for the Centralized Logging Service in Skype for Business Server 2015.</span></span>

<span data-ttu-id="7d674-105">중앙 로깅 서비스는 CLSController(중앙 로깅 서비스 컨트롤러)에서 만들어서 개별 컴퓨터의 CLSAgent(중앙 로깅 서비스 에이전트)로 명령을 보내는 데 사용하는 설정 및 매개 변수에 의해 제어 및 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d674-105">The Centralized Logging Service is controlled and configured by settings and parameters that are created and used by the Centralized Logging Service Controller (CLSController) to send commands to the individual computer's Centralized Logging Service Agent (CLSAgent).</span></span> <span data-ttu-id="7d674-106">에이전트는 전송된 명령을 처리하고(시작 명령의 경우) 시나리오, 공급자, 추적 기간 및 플래그의 구성을 사용하여 제공된 구성 정보에 따라 추적 로그 수집을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="7d674-106">The agent processes the commands that are sent to it and (in the case of a Start command) uses the configuration of the scenarios, providers, trace duration, and flags to begin collecting trace logs according to the configuration information provided.</span></span>

> [!IMPORTANT]
>  <span data-ttu-id="7d674-107">중앙 로깅 Windows PowerShell 나열된 모든 cmdlet이 비즈니스용 Skype 서버 2015온-프레미스 배포에서 사용하기 위한 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="7d674-107">Not all Windows PowerShell cmdlets listed for the Centralized Logging Service are intended for use with Skype for Business Server 2015 on-premises deployments.</span></span> <span data-ttu-id="7d674-108">작동하지만 다음 cmdlet은 비즈니스용 Skype 서버 2015 배포에서 작동하도록 설계되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7d674-108">Although they may appear to work, the following cmdlets are not designed to function with Skype for Business Server 2015 on-premises deployments:</span></span>

-  <span data-ttu-id="7d674-109">**CsClsRegion cmdlet:** [Get-CsClsRegion,](https://docs.microsoft.com/powershell/module/skype/get-csclsregion?view=skype-ps) [Set-CsClsRegion,](https://docs.microsoft.com/powershell/module/skype/set-csclsregion?view=skype-ps) [New-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/new-csclsregion?view=skype-ps)및 [Remove-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/remove-csclsregion?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="7d674-109">**CsClsRegion cmdlets:** [Get-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/get-csclsregion?view=skype-ps) ,[Set-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/set-csclsregion?view=skype-ps), [New-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/new-csclsregion?view=skype-ps), and [Remove-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/remove-csclsregion?view=skype-ps).</span></span>
-  <span data-ttu-id="7d674-110">**CsClsSearchTerm cmdlet:** [Get-CsClsSearchTerm](https://docs.microsoft.com/powershell/module/skype/get-csclssearchterm?view=skype-ps) 및 [Set-CsClsSearchTerm](https://docs.microsoft.com/powershell/module/skype/set-csclssearchterm?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="7d674-110">**CsClsSearchTerm cmdlets:** [Get-CsClsSearchTerm](https://docs.microsoft.com/powershell/module/skype/get-csclssearchterm?view=skype-ps) and [Set-CsClsSearchTerm](https://docs.microsoft.com/powershell/module/skype/set-csclssearchterm?view=skype-ps).</span></span>
-  <span data-ttu-id="7d674-111">**CsClsSecurityGroup cmdlets:** [Get-CsClsSecurityGroup,](https://docs.microsoft.com/powershell/module/skype/get-csclssecuritygroup?view=skype-ps) [Set-CsClsSecurityGroup,](https://docs.microsoft.com/powershell/module/skype/set-csclssecuritygroup?view=skype-ps) [New-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/new-csclssecuritygroup?view=skype-ps)및 [Remove-CsClsSecurityGroup.](https://docs.microsoft.com/powershell/module/skype/remove-csclssecuritygroup?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="7d674-111">**CsClsSecurityGroup cmdlets:** [Get-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/get-csclssecuritygroup?view=skype-ps), [Set-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/set-csclssecuritygroup?view=skype-ps),  [New-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/new-csclssecuritygroup?view=skype-ps), and [Remove-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/remove-csclssecuritygroup?view=skype-ps).</span></span>

<span data-ttu-id="7d674-112">이러한 cmdlet에 정의된 설정은 방해가되거나 부정적인 동작을 유발하지 않지만 Microsoft 365 또는 Office 365와 함께 사용할 수 있도록 설계되어 있으며, 이로 인해 예상되는 결과를 On-premises 배포에서 산출하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7d674-112">The settings defined in these cmdlets will not hinder or cause any adverse behavior, but they are designed for use with Microsoft 365 or Office 365 and will not yield the expected results in on-premises deployments.</span></span> <span data-ttu-id="7d674-113">이 말이 온-프레미스 배포에서 이러한 cmdlet을 사용할 수 없음을 의미하는 것은 아니지만 이 설명서에서는 이러한 cmdlet의 용도에 대해 설명하지 않겠습니다.</span><span class="sxs-lookup"><span data-stu-id="7d674-113">This is not to say that there is no use for these cmdlets in on-premises deployments, but their use is a more advanced topic that is not covered in this documentation.</span></span>

<span data-ttu-id="7d674-114">중앙 로깅 서비스는 단일 컴퓨터 또는 컴퓨터 풀을 포함하는 범위, 사이트 범위(즉, 배포에 컴퓨터 및 풀 컬렉션을 포함하는 Redmond 사이트와 같은 정의된 사이트) 또는 전역 범위(즉, 배포의 모든 컴퓨터 및 풀)에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d674-114">The Centralized Logging Service can be run at a scope that includes a single computer or a pool of computers, at a site scope (that is, a defined site such as the site Redmond that contains a collection of computer and pools in your deployment), or at a global scope (that is, all computers and pools in your deployment).</span></span>

<span data-ttu-id="7d674-115">비즈니스용 Skype 서버 관리 셸을 사용하여 중앙 로깅 서비스 범위를 구성하려면 CsAdministrator 또는 CsServerAdministrator RBAC(역할 기반 액세스 제어) 보안 그룹의 구성원 또는 이러한 두 그룹 중 하나를 포함하는 사용자 지정 RBAC 역할의 구성원이 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d674-115">To configure the Centralized Logging Service scope by using the Skype for Business Server Management Shell, you must be a member of either the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> <span data-ttu-id="7d674-116">직접 만든 사용자 지정 RBAC 역할을 포함하여 이 cmdlet이 할당된 모든 RBAC 역할의 목록을 반환하기 위해 비즈니스용 Skype 서버 관리 셸 또는 Windows PowerShell 프롬프트에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="7d674-116">To return a list of all the RBAC roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Skype for Business Server Management Shell or the Windows PowerShell prompt:</span></span>

```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "<Skype for Business cmdlet>"}
```

<span data-ttu-id="7d674-117">예시:</span><span class="sxs-lookup"><span data-stu-id="7d674-117">For example:</span></span>

```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

> [!NOTE]
> <span data-ttu-id="7d674-118">명령줄 명령과 CLSController에서 실행할 수 있는 명령줄 명령은 기본적으로 Windows PowerShell 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d674-118">There are fundamental differences between the command-line commands that you can run in Windows PowerShell or CLSController.</span></span> <span data-ttu-id="7d674-119">Windows PowerShell 시나리오를 구성 및 정의하고 해당 시나리오를 문제 해결 시나리오에 의미 있는 방식으로 다시 사용할 수 있는 다양한 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="7d674-119">Windows PowerShell provides a rich method to configure and define scenarios, and to reuse those scenarios in a meaningful way for your troubleshooting scenarios.</span></span> <span data-ttu-id="7d674-120">CLSController를 사용하면 빠르고 효율적으로 명령을 실행하고 결과를 얻을 수 있지만 CLSController의 명령 집합은 명령줄에서 사용할 수 있는 소수의 명령으로 한정됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d674-120">While CLSController does provide a fast and efficient way to issue commands and get results, the command set for CLSController is limited by the finite commands that you have available from the command line.</span></span> <span data-ttu-id="7d674-121">Windows PowerShell cmdlet과 달리, CLSController는 새 시나리오를 정의하고, 사이트 또는 전역 수준에서 범위를 관리하고, 동적으로 구성할 수 없는 유한 명령 집합의 많은 제한 사항을 정의할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7d674-121">Unlike the Windows PowerShell cmdlets, CLSController cannot define new scenarios, manage scope at a site or global level, and many other limitations of a finite command set that cannot be dynamically configured.</span></span> <span data-ttu-id="7d674-122">CLSController는 빠른 실행을 위한 수단을 Windows PowerShell CLSController를 통해 가능한 범위를 넘어 중앙 로깅 서비스 기능을 확장하는 수단을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="7d674-122">While CLSController provides a means for fast execution, Windows PowerShell provides a means to extend the Centralized Logging Service functionality beyond what is possible with CLSController.</span></span>

<span data-ttu-id="7d674-123">-Computers 매개 변수를 사용하여 [Search-CsClsLogging,](https://docs.microsoft.com/powershell/module/skype/search-csclslogging?view=skype-ps) [Show-CsClsLogging,](https://docs.microsoft.com/powershell/module/skype/show-csclslogging?view=skype-ps) [Start-CsClsLogging, Stop-CsClsLogging,](https://docs.microsoft.com/powershell/module/skype/start-csclslogging?view=skype-ps) [Sync-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/sync-csclslogging?view=skype-ps) 및 [Update-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/update-csclslogging?view=skype-ps) 명령을 실행하는 동안 단일 컴퓨터 범위를 정의할 수 있습니다. [](https://docs.microsoft.com/powershell/module/skype/stop-csclslogging?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="7d674-123">A single computer scope can be defined during the execution of a [Search-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/search-csclslogging?view=skype-ps), [Show-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/show-csclslogging?view=skype-ps), [Start-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/start-csclslogging?view=skype-ps), [Stop-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/stop-csclslogging?view=skype-ps), [Sync-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/sync-csclslogging?view=skype-ps) and [Update-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/update-csclslogging?view=skype-ps) command using the -Computers parameter.</span></span> <span data-ttu-id="7d674-124">-Computers 매개 변수는 대상 컴퓨터의 FQDNS(정식 도메인 이름)의 COMMA로 구분된 목록을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="7d674-124">The -Computers parameter accepts a comma separated list of fully qualified domain names (FQDNs) for the target computer.</span></span>

> [!TIP]
> <span data-ttu-id="7d674-125">로깅 명령을 실행할 풀의 -Pool 및 콤보로 구분된 목록을 정의할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d674-125">You can also define -Pools and a comma separated list of pools that you want to run the logging commands on.</span></span>

<span data-ttu-id="7d674-126">사이트 및 전역 범위는 **New-**, **Set-** 및 **Remove- 중앙** 로깅 서비스 cmdlet에 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d674-126">Site and Global scopes are defined in the **New-**, **Set-**, and **Remove-** Centralized Logging Service cmdlets.</span></span> <span data-ttu-id="7d674-127">다음 예에서는 사이트 범위와 전역 범위를 설정하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7d674-127">The following examples demonstrate how to set a site and a global scope.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7d674-128">예로 든 명령들에는 다른 섹션에서 설명하는 매개 변수와 개념이 포함되어 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d674-128">The commands shown may contain parameters and concepts that are covered in other sections.</span></span> <span data-ttu-id="7d674-129">예제 명령은 **-Identity** 매개 변수를 사용하여 범위를 정의하는 방법을 보여 주며, 다른 매개 변수는 완전성을 위해 포함하며 범위를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7d674-129">The example commands are intended to demonstrate the use of the **-Identity** parameter to define scope, and the other parameters are included for completeness and to specify the scope.</span></span> <span data-ttu-id="7d674-130">**Set-CsClsConfiguration** cmdlet에 대한 자세한 내용은 작업 설명서에서 [Set-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csclsconfiguration?view=skype-ps)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="7d674-130">For details about the **Set-CsClsConfiguration** cmdlets, see [Set-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csclsconfiguration?view=skype-ps) in the Operations documentation.</span></span>

### <a name="to-retrieve-the-current-centralized-logging-service-configuration"></a><span data-ttu-id="7d674-131">현재 중앙 로깅 서비스 구성을 검색하려면</span><span class="sxs-lookup"><span data-stu-id="7d674-131">To retrieve the current Centralized Logging Service configuration</span></span>

1. <span data-ttu-id="7d674-132">비즈니스용 Skype 서버 관리 셸 시작: **시작,** **모든** 프로그램, 비즈니스용 **Skype 2015,** 비즈니스용 Skype 서버 관리 셸을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="7d674-132">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="7d674-133">명령줄 프롬프트에 다음 명령을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="7d674-133">Type the following at the command-line prompt:</span></span>

   ```PowerShell
   Get-CsClsConfiguration
   ```

<span data-ttu-id="7d674-134">**New-CsClsConfiguration** 및 **Set-CsClsConfiguration** cmdlet을 사용하여 새 구성을 만들거나 기존 구성을 업데이트합니다. **Get-CsClsConfiguration을** 실행하면 배포에 현재 기본 전역 구성이 있지만 사이트 구성이 정의되지 않은 다음 스크린샷과 유사한 정보가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d674-134">Use the **New-CsClsConfiguration** and **Set-CsClsConfiguration** cmdlets to create a new configuration or to update an existing configuration.When you run **Get-CsClsConfiguration**, it displays information similar to the following screen shot, where the deployment currently has the default Global configuration, but no site configurations defined:</span></span>

![Get-CsClsConfiguration의 샘플 출력입니다.](../../media/Ops_Get-CsClsConfiguration_Basic.jpg)

### <a name="to-retrieve-the-current-centralized-logging-service-configuration-from-the-computer-local-store"></a><span data-ttu-id="7d674-136">컴퓨터 로컬 저장소에서 현재 중앙 로깅 서비스 구성을 검색하려면</span><span class="sxs-lookup"><span data-stu-id="7d674-136">To retrieve the current Centralized Logging Service configuration from the computer local store</span></span>

1. <span data-ttu-id="7d674-137">비즈니스용 Skype 서버 관리 셸 시작: **시작,** **모든** 프로그램, 비즈니스용 **Skype 2015,** 비즈니스용 Skype 서버 관리 셸을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="7d674-137">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="7d674-138">명령줄 프롬프트에 다음 명령을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="7d674-138">Type the following at the command-line prompt:</span></span>

   ```PowerShell
   Get-CsClsConfiguration -LocalStore
   ```

<span data-ttu-id="7d674-139">**Get-CsClsConfiguration이** 매개 변수를 지정하지 않는 첫 번째 예제를 사용하는 경우 명령은 데이터에 대한 중앙 관리 저장소를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="7d674-139">When you use the first example where **Get-CsClsConfiguration** does not specify any parameters, the command references the Central Management store for the data.</span></span> <span data-ttu-id="7d674-140">-LocalStore 매개 변수를 지정하면 명령은 중앙 관리 저장소 대신 LocalStore 컴퓨터를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="7d674-140">If you specify the parameter -LocalStore, the command references the computer LocalStore instead of the Central Management store.</span></span>
### <a name="to-retrieve-a-listing-of-scenarios-currently-defined"></a><span data-ttu-id="7d674-141">현재 정의된 시나리오 목록을 검색하려면</span><span class="sxs-lookup"><span data-stu-id="7d674-141">To retrieve a listing of scenarios currently defined</span></span>

1. <span data-ttu-id="7d674-142">비즈니스용 Skype 서버 관리 셸 시작: **시작,** **모든** 프로그램, 비즈니스용 **Skype 2015,** 비즈니스용 Skype 서버 관리 셸을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="7d674-142">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="7d674-143">명령줄 프롬프트에 다음 명령을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="7d674-143">Type the following at the command-line prompt:</span></span>

   ```PowerShell
   Get-CsClsConfiguration -Identity <scope and name> | Select-Object -ExpandProperty Scenarios
   ```

    <span data-ttu-id="7d674-144">예를 들어 전역 범위로 정의된 시나리오를 검색하려면 다음과 같이 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d674-144">For example, to retrieve the scenarios that is defined at the global scope:</span></span>

   ```PowerShell
   Get-CsClsConfiguration -Identity "global" | Select-Object -ExpandProperty Scenarios
   ```

<span data-ttu-id="7d674-145">**Get-CsClsConfiguration** cmdlet은 항상 지정한 범위 구성의 일부인 시나리오를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="7d674-145">The cmdlet **Get-CsClsConfiguration** always displays the scenarios that are a part of a given scope's configuration.</span></span> <span data-ttu-id="7d674-146">대부분의 경우 시나리오가 모두 표시되지 않고 잘려서 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d674-146">In most cases, all scenarios are not displayed, and are truncated.</span></span> <span data-ttu-id="7d674-147">여기에 사용된 명령은 모든 시나리오와 사용된 공급자, 설정 및 플래그에 대한 일부 정보를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="7d674-147">The command used here lists all of the scenarios and partial information about what providers, settings, and flags are used.</span></span>
### <a name="to-update-a-global-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a><span data-ttu-id="7d674-148">중앙 로깅 서비스를 사용하여 전역 범위를 업데이트 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="7d674-148">To update a global scope for the Centralized Logging Service by using Windows PowerShell</span></span>

1. <span data-ttu-id="7d674-149">비즈니스용 Skype 서버 관리 셸 시작: **시작,** **모든** 프로그램, 비즈니스용 **Skype 2015,** 비즈니스용 Skype 서버 관리 셸을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="7d674-149">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="7d674-150">명령줄 프롬프트에 다음 명령을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="7d674-150">Type the following at the command-line prompt:</span></span>

   ```PowerShell
   Set-CsClsConfiguration -Identity <scope> -EtlFileRolloverSizeMB <size for logging file in megabytes>
   ```

   <span data-ttu-id="7d674-151">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="7d674-151">For example:</span></span>

   ```PowerShell
   Set-CsClsConfiguration -Identity "global" -EtlFileRolloverSizeMB 40
   ```

<span data-ttu-id="7d674-p111">이 명령을 실행하면 배포에 포함된 각 컴퓨터와 풀의 CLSAgent에서 추적 파일 롤오버 크기 값이 40메가바이트로 설정됩니다. 이 명령은 모든 사이트의 컴퓨터와 풀에 영향을 미쳐 각각의 구성된 추적 로그 롤오버 값이 40메가바이트로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d674-p111">The command tells the CLSAgent on each computer and pool in the deployment to set the size of the rollover value on the tracing file to 40 megabytes. Computers and pools in all sites are affected by the command, and will set their configured trace log rollover value to 40 megabytes.</span></span>
### <a name="to-update-a-site-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a><span data-ttu-id="7d674-154">중앙 로깅 서비스를 사용하여 사이트 범위를 업데이트 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="7d674-154">To update a site scope for the Centralized Logging Service by using Windows PowerShell</span></span>

1. <span data-ttu-id="7d674-155">비즈니스용 Skype 서버 관리 셸 시작: **시작,** **모든** 프로그램, 비즈니스용 **Skype 2015,** 비즈니스용 Skype 서버 관리 셸을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="7d674-155">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="7d674-156">명령줄 프롬프트에 다음 명령을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="7d674-156">Type the following at the command-line prompt:</span></span>

   ```PowerShell
   Set-CsClsConfiguration -Identity <scope/site name> -EtlFileRolloverSizeMB <size for logging file in megabytes>
   ```

   <span data-ttu-id="7d674-157">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="7d674-157">For example:</span></span>

   ```PowerShell
   Set-CsClsConfiguration -Identity "site/Redmond" -EtlFileRolloverSizeMB 40
   ```

> [!NOTE]
> <span data-ttu-id="7d674-p112">이 예에 나와 있듯이 로그 파일의 기본 위치는 %TEMP%\Tracing입니다. 그러나 실제로 파일을 기록하는 것은 CLSAgent이고 CSLAgent는 네트워크 서비스로 실행되므로 %TEMP% 변수는 %WINDIR%\ServiceProfiles\NetworkService\AppData\Local로 확장됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d674-p112">As noted in the example, the default location of the log files is %TEMP%\Tracing. However, because it is actually CLSAgent that is writing the file and CSLAgent runs as Network Service, the %TEMP% variable expands to %WINDIR%\ServiceProfiles\NetworkService\AppData\Local.</span></span>

<span data-ttu-id="7d674-p113">이 명령을 실행하면 Redmond 사이트에 포함된 각 컴퓨터와 풀의 CLSAgent에서 추적 파일 롤오버 크기 값이 40메가바이트로 설정됩니다. 다른 사이트의 컴퓨터와 풀은 이 명령의 영향을 받지 않으며 기본적으로 정의되어 있거나(20메가바이트) 로깅 세션을 시작할 때 정의되어 현재 구성된 추적 로그 롤오버 값을 계속 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7d674-p113">The command tells the CLSAgent on each computer and pool in the site Redmond to set the size of the rollover value on the tracing file to 40 megabytes. Computers and pools in other sites will not be affected by the command, and will continue to use the currently configured trace log rollover value defined either by default (20 megabytes) or during the start of the logging session.</span></span>
### <a name="to-create-a-new-centralized-logging-service-configuration"></a><span data-ttu-id="7d674-162">새 중앙 로깅 서비스 구성을 만들하려면</span><span class="sxs-lookup"><span data-stu-id="7d674-162">To create a new Centralized Logging Service configuration</span></span>

1. <span data-ttu-id="7d674-163">비즈니스용 Skype 서버 관리 셸 시작: **시작,** **모든** 프로그램, 비즈니스용 **Skype 2015,** 비즈니스용 Skype 서버 관리 셸을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="7d674-163">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="7d674-164">명령줄 프롬프트에 다음 명령을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="7d674-164">Type the following at the command-line prompt:</span></span>

   ```PowerShell
   New-CsClsConfiguration -Identity <scope and name> [CsClsConfiguration options for this site]
   ```

    > [!NOTE]
    > <span data-ttu-id="7d674-165">New-CsClsConfiguration을 사용하면 다수의 선택적 구성 설정에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d674-165">New-CsClsConfiguration provides access to a large number of optional configuration settings.</span></span> <span data-ttu-id="7d674-166">구성 옵션에 대한 자세한 내용은 [Get-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csclsconfiguration?view=skype-ps) 및 [Understanding Centralized Logging Service 구성 설정을 참조하세요.](https://technet.microsoft.com/library/3c34e600-0b91-43dc-b4cc-90b6a70ee12e.aspx)</span><span class="sxs-lookup"><span data-stu-id="7d674-166">For details about the configuration options, see [Get-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csclsconfiguration?view=skype-ps) and [Understanding Centralized Logging Service Configuration Settings](https://technet.microsoft.com/library/3c34e600-0b91-43dc-b4cc-90b6a70ee12e.aspx).</span></span>

<span data-ttu-id="7d674-167">예를 들어 캐시 파일의 네트워크 폴더, 로그 파일의 롤오버 기간 및 로그 파일의 롤오버 크기를 정의하는 새로운 구성을 만들려면 다음 명령을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="7d674-167">For example, to create a new configuration that defines a network folder for cache files, rollover time period for the log files and rollover size for the log files, you would type:</span></span>

  ```PowerShell
  New-CsClsConfiguration -Identity "site:Redmond" -CacheFileNetworkFolder "\\fs01.contoso.net\filestore\logfiles" -EtlFileRolloverMinutes 120 -EtlFileRolloverSizeMB 40
  ```

<span data-ttu-id="7d674-168">새 구성 만들기 및 중앙 로깅 서비스에 대한 새 속성을 정의하는 방법을 신중하게 계획해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d674-168">You should carefully plan the creation of new configurations and how you define new properties for the Centralized Logging Service.</span></span> <span data-ttu-id="7d674-169">구성을 변경할 때에는 주의를 기울여야 하며 변경 후에 문제 시나리오를 올바르게 로깅할 수 있을지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d674-169">You should be cautious about making changes and make sure you understand the impact on your ability to properly log problem scenarios.</span></span> <span data-ttu-id="7d674-170">적절한 크기와 롤오버 기간으로 로그를 더욱 효과적으로 관리하여 문제 발생 시 문제를 손쉽게 해결할 수 있도록 구성을 변경해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d674-170">You should make changes to the configuration that will enhance your ability to manage logs to a size and a rollover period that will allow problem solving when it arises.</span></span>
### <a name="to-remove-an-existing-centralized-logging-service-configuration"></a><span data-ttu-id="7d674-171">기존 중앙 로깅 서비스 구성을 제거하려면</span><span class="sxs-lookup"><span data-stu-id="7d674-171">To remove an existing Centralized Logging Service configuration</span></span>

1. <span data-ttu-id="7d674-172">비즈니스용 Skype 서버 관리 셸 시작: **시작,** **모든** 프로그램, 비즈니스용 **Skype 2015,** 비즈니스용 Skype 서버 관리 셸을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="7d674-172">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="7d674-173">명령줄 프롬프트에 다음 명령을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="7d674-173">Type the following at the command-line prompt:</span></span>

   ```PowerShell
   Remove-CsClsConfiguration -Identity <scope and name>
   ```

<span data-ttu-id="7d674-174">예를 들어 로그 파일 롤오버 시간을 늘리기 위해 만든 중앙 로깅 서비스 구성을 제거하려면 롤오버 로그 파일 크기를 늘리고 로그 파일 캐시 위치를 다음과 같이 네트워크 공유로 설정하십시오.</span><span class="sxs-lookup"><span data-stu-id="7d674-174">For example, to remove a Centralized Logging Service configuration that you created to increase the log file rollover time, increase the rollover log file size, and set the log file cache location to a network share as follows:</span></span>

  ```PowerShell
  Remove-CsClsConfiguration -Identity "site:Redmond"
  ```

> [!NOTE]
> <span data-ttu-id="7d674-175">이 구성은 "새 중앙 로깅 서비스 구성을 만들 수 있습니다." 절차에서 만든 새 구성입니다.</span><span class="sxs-lookup"><span data-stu-id="7d674-175">This is the new configuration that was created in the procedure "To create a new Centralized Logging Service configuration."</span></span>

<span data-ttu-id="7d674-176">사이트 수준 구성을 제거하는 경우 사이트에 전역 설정이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d674-176">If you choose to remove a site-level configuration, the site will use the global settings.</span></span>
## <a name="see-also"></a><span data-ttu-id="7d674-177">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7d674-177">See also</span></span>

[<span data-ttu-id="7d674-178">비즈니스용 Skype 서버에서 중앙 로깅 서비스에 대한 공급자 구성</span><span class="sxs-lookup"><span data-stu-id="7d674-178">Configure providers for Centralized Logging Service in Skype for Business Server 2015</span></span>](configure-providers.md)

[<span data-ttu-id="7d674-179">비즈니스용 Skype 서버에서 중앙 로깅 서비스에 대한 시나리오 구성</span><span class="sxs-lookup"><span data-stu-id="7d674-179">Configure scenarios for the Centralized Logging Service in Skype for Business Server 2015</span></span>](configure-scenarios.md)

[<span data-ttu-id="7d674-180">비즈니스용 Skype 2015의 중앙 로깅 서비스</span><span class="sxs-lookup"><span data-stu-id="7d674-180">Centralized Logging Service in Skype for Business 2015</span></span>](centralized-logging-service.md)

[<span data-ttu-id="7d674-181">Set-CsClsConfiguration</span><span class="sxs-lookup"><span data-stu-id="7d674-181">Set-CsClsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csclsconfiguration?view=skype-ps)

[<span data-ttu-id="7d674-182">Get-CsClsConfiguration</span><span class="sxs-lookup"><span data-stu-id="7d674-182">Get-CsClsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csclsconfiguration?view=skype-ps)

[<span data-ttu-id="7d674-183">New-CsClsConfiguration</span><span class="sxs-lookup"><span data-stu-id="7d674-183">New-CsClsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csclsconfiguration?view=skype-ps)

[<span data-ttu-id="7d674-184">Remove-CsClsConfiguration</span><span class="sxs-lookup"><span data-stu-id="7d674-184">Remove-CsClsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csclsconfiguration?view=skype-ps)
