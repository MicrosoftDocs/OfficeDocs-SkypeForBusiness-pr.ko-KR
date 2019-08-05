---
title: 비즈니스용 Skype 2015에서 중앙 로깅 서비스 구성 설정 관리
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 8/17/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 93b9a354-9aea-4b3a-a4fe-68a89f436196
description: '요약: 비즈니스용 Skype Server 2015에서 중앙 집중화 된 로깅 서비스의 구성 설정을 검색, 업데이트 및 만드는 방법에 대해 알아봅니다.'
ms.openlocfilehash: e6c1f9c893d0b5e745e558ed37570429689259d9
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36186816"
---
# <a name="manage-centralized-logging-service-configuration-settings-in-skype-for-business-server-2015"></a><span data-ttu-id="196e4-103">비즈니스용 Skype 2015에서 중앙 로깅 서비스 구성 설정 관리</span><span class="sxs-lookup"><span data-stu-id="196e4-103">Manage Centralized Logging Service configuration settings in Skype for Business Server 2015</span></span>

<span data-ttu-id="196e4-104">**요약:** 비즈니스용 Skype 서버 2015에서 중앙 로깅 서비스에 대 한 구성 설정을 검색, 업데이트 및 만드는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="196e4-104">**Summary:** Learn how to retrieve, update, and create configuration settings for the Centralized Logging Service in Skype for Business Server 2015.</span></span>

<span data-ttu-id="196e4-105">중앙 로깅 서비스는 각 컴퓨터의 중앙 로깅 서비스 에이전트에 명령을 전송 하기 위해 중앙 집중식 로깅 서비스 컨트롤러 (CLSController)에서 만들고 사용 하는 설정 및 매개 변수를 통해 제어 및 구성 됩니다 ( CLSAgent).</span><span class="sxs-lookup"><span data-stu-id="196e4-105">The Centralized Logging Service is controlled and configured by settings and parameters that are created and used by the Centralized Logging Service Controller (CLSController) to send commands to the individual computer's Centralized Logging Service Agent (CLSAgent).</span></span> <span data-ttu-id="196e4-106">에이전트는 여기에 전송 된 명령을 처리 하 고 (시작 명령의 경우) 시나리오, 공급자, 추적 기간 및 플래그 구성을 사용 하 여 제공 되는 구성 정보에 따라 추적 로그 수집을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="196e4-106">The agent processes the commands that are sent to it and (in the case of a Start command) uses the configuration of the scenarios, providers, trace duration, and flags to begin collecting trace logs according to the configuration information provided.</span></span>

> [!IMPORTANT]
>  <span data-ttu-id="196e4-107">중앙 로깅 서비스에 대해 나열 된 모든 Windows PowerShell cmdlet은 비즈니스용 Skype Server 2015 온-프레미스 배포에만 사용할 수 있는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="196e4-107">Not all Windows PowerShell cmdlets listed for the Centralized Logging Service are intended for use with Skype for Business Server 2015 on-premises deployments.</span></span> <span data-ttu-id="196e4-108">이는 작동 하는 것 처럼 보일 수 있지만, 다음 cmdlet는 비즈니스용 Skype Server 2015 온-프레미스 배포에서 작동 하도록 설계 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="196e4-108">Although they may appear to work, the following cmdlets are not designed to function with Skype for Business Server 2015 on-premises deployments:</span></span>

-  <span data-ttu-id="196e4-109">**Csclsregion cmdlet:** [Get-csclsregion](https://docs.microsoft.com/powershell/module/skype/get-csclsregion?view=skype-ps) ,[Set-csclsregion](https://docs.microsoft.com/powershell/module/skype/set-csclsregion?view=skype-ps), [New-csclsregion](https://docs.microsoft.com/powershell/module/skype/new-csclsregion?view=skype-ps), [제거-csclsregion](https://docs.microsoft.com/powershell/module/skype/remove-csclsregion?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="196e4-109">**CsClsRegion cmdlets:** [Get-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/get-csclsregion?view=skype-ps) ,[Set-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/set-csclsregion?view=skype-ps), [New-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/new-csclsregion?view=skype-ps), and [Remove-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/remove-csclsregion?view=skype-ps).</span></span>
-  <span data-ttu-id="196e4-110">**Csclssearchterm cmdlet:** [Get-csclssearchterm](https://docs.microsoft.com/powershell/module/skype/get-csclssearchterm?view=skype-ps) 및 [Set csclssearchterm](https://docs.microsoft.com/powershell/module/skype/set-csclssearchterm?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="196e4-110">**CsClsSearchTerm cmdlets:** [Get-CsClsSearchTerm](https://docs.microsoft.com/powershell/module/skype/get-csclssearchterm?view=skype-ps) and [Set-CsClsSearchTerm](https://docs.microsoft.com/powershell/module/skype/set-csclssearchterm?view=skype-ps).</span></span>
-  <span data-ttu-id="196e4-111">**Csclssecuritygroup cmdlet:** [Get-csclssecuritygroup](https://docs.microsoft.com/powershell/module/skype/get-csclssecuritygroup?view=skype-ps), [Set-csclssecuritygroup](https://docs.microsoft.com/powershell/module/skype/set-csclssecuritygroup?view=skype-ps), [New-Csclssecuritygroup](https://docs.microsoft.com/powershell/module/skype/new-csclssecuritygroup?view=skype-ps)및 [Remove-csclssecuritygroup](https://docs.microsoft.com/powershell/module/skype/remove-csclssecuritygroup?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="196e4-111">**CsClsSecurityGroup cmdlets:** [Get-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/get-csclssecuritygroup?view=skype-ps), [Set-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/set-csclssecuritygroup?view=skype-ps),  [New-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/new-csclssecuritygroup?view=skype-ps), and [Remove-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/remove-csclssecuritygroup?view=skype-ps).</span></span>

<span data-ttu-id="196e4-112">이러한 cmdlet에 정의 된 설정은 방해 하거나 부정적인 동작을 발생 시 키 지 않으며, Microsoft Office 365에서 사용 하도록 디자인 되었으며 온-프레미스 배포에서 예상 되는 결과가 생성 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="196e4-112">The settings defined in these cmdlets will not hinder or cause any adverse behavior, but they are designed for use with Microsoft Office 365 and will not yield the expected results in on-premises deployments.</span></span> <span data-ttu-id="196e4-113">이는 온-프레미스 배포에서 이러한 cmdlet을 사용 하지 않는 것이 아니라,이를 사용 하는 것이이 문서에서 다루지 않는 고급 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="196e4-113">This is not to say that there is no use for these cmdlets in on-premises deployments, but their use is a more advanced topic that is not covered in this documentation.</span></span>

<span data-ttu-id="196e4-114">중앙 로깅 서비스는 사이트 범위 (즉, 배포의 컴퓨터 및 풀의 컬렉션을 포함 하는 사이트 Redmond) 또는 전역 범위 (즉, 지정 된 사이트)에서 단일 컴퓨터 또는 컴퓨터의 풀을 포함 하는 범위에서 실행할 수 있습니다. , 배포의 모든 컴퓨터 및 풀.</span><span class="sxs-lookup"><span data-stu-id="196e4-114">The Centralized Logging Service can be run at a scope that includes a single computer or a pool of computers, at a site scope (that is, a defined site such as the site Redmond that contains a collection of computer and pools in your deployment), or at a global scope (that is, all computers and pools in your deployment).</span></span>

<span data-ttu-id="196e4-115">비즈니스용 Skype Server Management Shell을 사용 하 여 중앙 로깅 서비스 범위를 구성 하려면 CsAdministrator 또는 CsServerAdministrator 역할 기반 액세스 제어 (RBAC) 보안 그룹 또는 사용자 지정 RBAC 역할의 구성원 이어야 합니다. 두 그룹 중 하나를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="196e4-115">To configure the Centralized Logging Service scope by using the Skype for Business Server Management Shell, you must be a member of either the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> <span data-ttu-id="196e4-116">이 cmdlet이 할당 된 모든 RBAC 역할 목록 (직접 만든 사용자 지정 RBAC 역할 포함)을 반환 하려면 비즈니스용 Skype Server 관리 셸 또는 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="196e4-116">To return a list of all the RBAC roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Skype for Business Server Management Shell or the Windows PowerShell prompt:</span></span>

```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "<Skype for Business cmdlet>"}
```

<span data-ttu-id="196e4-117">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="196e4-117">For example:</span></span>

```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

> [!NOTE]
> <span data-ttu-id="196e4-118">Windows PowerShell 또는 CLSController에서 실행할 수 있는 명령줄 명령 간에는 기본적인 차이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="196e4-118">There are fundamental differences between the command-line commands that you can run in Windows PowerShell or CLSController.</span></span> <span data-ttu-id="196e4-119">Windows PowerShell은 시나리오를 구성 및 정의 하 고 문제 해결 시나리오에 의미 있는 방식으로 해당 시나리오를 다시 사용 하는 다양 한 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="196e4-119">Windows PowerShell provides a rich method to configure and define scenarios, and to reuse those scenarios in a meaningful way for your troubleshooting scenarios.</span></span> <span data-ttu-id="196e4-120">CLSController는 명령을 실행 하 고 결과를 얻을 수 있는 빠르고 효율적인 방법을 제공 하지만 CLSController에 대 한 명령 집합은 명령줄에서 사용할 수 있는 유한 명령으로 제한 됩니다.</span><span class="sxs-lookup"><span data-stu-id="196e4-120">While CLSController does provide a fast and efficient way to issue commands and get results, the command set for CLSController is limited by the finite commands that you have available from the command line.</span></span> <span data-ttu-id="196e4-121">Windows PowerShell cmdlet과 달리 CLSController는 새 시나리오를 정의 하거나, 사이트 또는 전역 수준의 범위를 관리 하 고, 동적으로 구성할 수 없는 유한 명령 집합의 여러 다른 제한 사항에 대 한 다양 한 제한을 정의할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="196e4-121">Unlike the Windows PowerShell cmdlets, CLSController cannot define new scenarios, manage scope at a site or global level, and many other limitations of a finite command set that cannot be dynamically configured.</span></span> <span data-ttu-id="196e4-122">CLSController는 빠른 실행을 위한 수단을 제공 하는 반면, Windows PowerShell은 CLSController에서 가능한 기능 외에 중앙 집중식 로깅 서비스 기능을 확장 하는 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="196e4-122">While CLSController provides a means for fast execution, Windows PowerShell provides a means to extend the Centralized Logging Service functionality beyond what is possible with CLSController.</span></span>

<span data-ttu-id="196e4-123">[검색-](https://docs.microsoft.com/powershell/module/skype/search-csclslogging?view=skype-ps)csclslogging, [표시-](https://docs.microsoft.com/powershell/module/skype/show-csclslogging?view=skype-ps)csclslogging, [시작-](https://docs.microsoft.com/powershell/module/skype/start-csclslogging?view=skype-ps)csclslogging, [중지-](https://docs.microsoft.com/powershell/module/skype/stop-csclslogging?view=skype-ps)Csclslogging, [동기화-](https://docs.microsoft.com/powershell/module/skype/sync-csclslogging?view=skype-ps) csclslogging 및 [업데이트-](https://docs.microsoft.com/powershell/module/skype/update-csclslogging?view=skype-ps) csclslogging을 실행 하는 동안 단일 컴퓨터 범위를 정의할 수 있습니다. -Computers 매개 변수를 사용 하는 명령입니다.</span><span class="sxs-lookup"><span data-stu-id="196e4-123">A single computer scope can be defined during the execution of a [Search-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/search-csclslogging?view=skype-ps), [Show-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/show-csclslogging?view=skype-ps), [Start-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/start-csclslogging?view=skype-ps), [Stop-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/stop-csclslogging?view=skype-ps), [Sync-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/sync-csclslogging?view=skype-ps) and [Update-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/update-csclslogging?view=skype-ps) command using the -Computers parameter.</span></span> <span data-ttu-id="196e4-124">-Computers 매개 변수는 대상 컴퓨터에 대 한 Fqdn (정규화 된 도메인 이름) 목록을 쉼표로 구분 하 여 받아들입니다.</span><span class="sxs-lookup"><span data-stu-id="196e4-124">The -Computers parameter accepts a comma separated list of fully qualified domain names (FQDNs) for the target computer.</span></span>

> [!TIP]
> <span data-ttu-id="196e4-125">또한 로깅 명령을 실행할 풀의 목록 및 쉼표로 구분 된 목록을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="196e4-125">You can also define -Pools and a comma separated list of pools that you want to run the logging commands on.</span></span>

<span data-ttu-id="196e4-126">사이트 및 전역 범위는 **새로운**중앙의 로깅 서비스 cmdlet \*\*\*\* 에 정의 되어 있습니다 \*\*\*\* .</span><span class="sxs-lookup"><span data-stu-id="196e4-126">Site and Global scopes are defined in the **New-**, **Set-**, and **Remove-** Centralized Logging Service cmdlets.</span></span> <span data-ttu-id="196e4-127">다음 예제에서는 사이트 및 전역 범위를 설정 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="196e4-127">The following examples demonstrate how to set a site and a global scope.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="196e4-128">표시 되는 명령에는 다른 섹션에서 설명 하는 매개 변수 및 개념이 포함 되어 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="196e4-128">The commands shown may contain parameters and concepts that are covered in other sections.</span></span> <span data-ttu-id="196e4-129">이 예제 명령은 **-Identity** 매개 변수를 사용 하 여 범위를 정의 하 고 나머지 매개 변수는 완전성을 위해 포함 하며 범위를 지정 하기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="196e4-129">The example commands are intended to demonstrate the use of the **-Identity** parameter to define scope, and the other parameters are included for completeness and to specify the scope.</span></span> <span data-ttu-id="196e4-130">**Set-csclsconfiguration** cmdlet에 대 한 자세한 내용은 작업 설명서의 [Set-csclsconfiguration](https://docs.microsoft.com/powershell/module/skype/set-csclsconfiguration?view=skype-ps) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="196e4-130">For details about the **Set-CsClsConfiguration** cmdlets, see [Set-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csclsconfiguration?view=skype-ps) in the Operations documentation.</span></span>

### <a name="to-retrieve-the-current-centralized-logging-service-configuration"></a><span data-ttu-id="196e4-131">현재 중앙 집중화 된 로깅 서비스 구성을 검색 하려면</span><span class="sxs-lookup"><span data-stu-id="196e4-131">To retrieve the current Centralized Logging Service configuration</span></span>

1. <span data-ttu-id="196e4-132">비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **비즈니스용 skype 2015**을 차례로 클릭 한 다음 비즈니스용 **skype Server management Shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="196e4-132">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="196e4-133">명령줄 프롬프트에 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="196e4-133">Type the following at the command-line prompt:</span></span>

   ```
   Get-CsClsConfiguration
   ```

<span data-ttu-id="196e4-134">새 구성을 만들거나 기존 구성을 업데이트 하기 위해 **새로운 csclsconfiguration** 및 **Set csclsconfiguration** cmdlet을 사용 합니다. **Get-CsClsConfiguration**을 실행 하면 배포에 현재 기본 전역 구성이 있지만 사이트 구성이 정의 되지 않은 다음 스크린샷은 다음과 같은 정보가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="196e4-134">Use the **New-CsClsConfiguration** and **Set-CsClsConfiguration** cmdlets to create a new configuration or to update an existing configuration.When you run **Get-CsClsConfiguration**, it displays information similar to the following screen shot, where the deployment currently has the default Global configuration, but no site configurations defined:</span></span>

![Get-CsClsConfiguration의 샘플 출력.](../../media/Ops_Get-CsClsConfiguration_Basic.jpg)

### <a name="to-retrieve-the-current-centralized-logging-service-configuration-from-the-computer-local-store"></a><span data-ttu-id="196e4-136">컴퓨터 로컬 저장소에서 현재 중앙 집중화 된 로깅 서비스 구성을 검색 하려면</span><span class="sxs-lookup"><span data-stu-id="196e4-136">To retrieve the current Centralized Logging Service configuration from the computer local store</span></span>

1. <span data-ttu-id="196e4-137">비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **비즈니스용 skype 2015**을 차례로 클릭 한 다음 비즈니스용 **skype Server management Shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="196e4-137">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="196e4-138">명령줄 프롬프트에 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="196e4-138">Type the following at the command-line prompt:</span></span>

   ```
   Get-CsClsConfiguration -LocalStore
   ```

<span data-ttu-id="196e4-139">**Get-CsClsConfiguration** 이 매개 변수를 지정 하지 않는 첫 번째 예제를 사용 하는 경우 명령은 데이터에 대 한 중앙 관리 저장소를 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="196e4-139">When you use the first example where **Get-CsClsConfiguration** does not specify any parameters, the command references the Central Management store for the data.</span></span> <span data-ttu-id="196e4-140">매개 변수-LocalStore를 지정 하는 경우이 명령은 중앙 관리 저장소 대신 컴퓨터 LocalStore를 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="196e4-140">If you specify the parameter -LocalStore, the command references the computer LocalStore instead of the Central Management store.</span></span>
### <a name="to-retrieve-a-listing-of-scenarios-currently-defined"></a><span data-ttu-id="196e4-141">현재 정의 된 시나리오 목록을 검색 하려면</span><span class="sxs-lookup"><span data-stu-id="196e4-141">To retrieve a listing of scenarios currently defined</span></span>

1. <span data-ttu-id="196e4-142">비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **비즈니스용 skype 2015**을 차례로 클릭 한 다음 비즈니스용 **skype Server management Shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="196e4-142">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="196e4-143">명령줄 프롬프트에 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="196e4-143">Type the following at the command-line prompt:</span></span>

   ```
   Get-CsClsConfiguration -Identity <scope and name> | Select-Object -ExpandProperty Scenarios
   ```

    <span data-ttu-id="196e4-144">예를 들어 전역 범위에서 정의 된 시나리오를 검색 하려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="196e4-144">For example, to retrieve the scenarios that is defined at the global scope:</span></span>

   ```
   Get-CsClsConfiguration -Identity "global" | Select-Object -ExpandProperty Scenarios
   ```

<span data-ttu-id="196e4-145">Cmdlet **Get CsClsConfiguration** 은 항상 지정 된 범위의 구성에 속하는 시나리오를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="196e4-145">The cmdlet **Get-CsClsConfiguration** always displays the scenarios that are a part of a given scope's configuration.</span></span> <span data-ttu-id="196e4-146">대부분의 경우, 모든 시나리오가 표시 되지 않고 잘릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="196e4-146">In most cases, all scenarios are not displayed, and are truncated.</span></span> <span data-ttu-id="196e4-147">여기에 사용 되는 명령에는 모든 시나리오와 사용 되는 공급자, 설정 및 플래그에 대 한 일부 정보가 나열 됩니다.</span><span class="sxs-lookup"><span data-stu-id="196e4-147">The command used here lists all of the scenarios and partial information about what providers, settings, and flags are used.</span></span>
### <a name="to-update-a-global-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a><span data-ttu-id="196e4-148">Windows PowerShell을 사용 하 여 중앙 로깅 서비스에 대 한 전역 범위를 업데이트 하려면</span><span class="sxs-lookup"><span data-stu-id="196e4-148">To update a global scope for the Centralized Logging Service by using Windows PowerShell</span></span>

1. <span data-ttu-id="196e4-149">비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **비즈니스용 skype 2015**을 차례로 클릭 한 다음 비즈니스용 **skype Server management Shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="196e4-149">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="196e4-150">명령줄 프롬프트에 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="196e4-150">Type the following at the command-line prompt:</span></span>

   ```
   Set-CsClsConfiguration -Identity <scope> -EtlFileRolloverSizeMB <size for logging file in megabytes>
   ```

   <span data-ttu-id="196e4-151">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="196e4-151">For example:</span></span>

   ```
   Set-CsClsConfiguration -Identity "global" -EtlFileRolloverSizeMB 40
   ```

<span data-ttu-id="196e4-152">이 명령은 배포의 각 컴퓨터와 풀에 CLSAgent를 알려 추적 파일의 롤오버 값 크기를 40 메가바이트 단위로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="196e4-152">The command tells the CLSAgent on each computer and pool in the deployment to set the size of the rollover value on the tracing file to 40 megabytes.</span></span> <span data-ttu-id="196e4-153">모든 사이트의 컴퓨터 및 풀은 명령의 영향을 받으며, 구성 된 추적 로그 롤오버 값을 40 메가바이트 ()로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="196e4-153">Computers and pools in all sites are affected by the command, and will set their configured trace log rollover value to 40 megabytes.</span></span>
### <a name="to-update-a-site-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a><span data-ttu-id="196e4-154">Windows PowerShell을 사용 하 여 중앙 로깅 서비스의 사이트 범위를 업데이트 하려면</span><span class="sxs-lookup"><span data-stu-id="196e4-154">To update a site scope for the Centralized Logging Service by using Windows PowerShell</span></span>

1. <span data-ttu-id="196e4-155">비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **비즈니스용 skype 2015**을 차례로 클릭 한 다음 비즈니스용 **skype Server management Shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="196e4-155">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="196e4-156">명령줄 프롬프트에 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="196e4-156">Type the following at the command-line prompt:</span></span>

   ```
   Set-CsClsConfiguration -Identity <scope/site name> -EtlFileRolloverSizeMB <size for logging file in megabytes>
   ```

   <span data-ttu-id="196e4-157">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="196e4-157">For example:</span></span>

   ```
   Set-CsClsConfiguration -Identity "site/Redmond" -EtlFileRolloverSizeMB 40
   ```

> [!NOTE]
> <span data-ttu-id="196e4-158">이 예제에 나와 있는 것 처럼 로그 파일의 기본 위치는%TEMP%\Tracing.입니다.</span><span class="sxs-lookup"><span data-stu-id="196e4-158">As noted in the example, the default location of the log files is %TEMP%\Tracing.</span></span> <span data-ttu-id="196e4-159">그러나 파일을 기록 하 고 CSLAgent가 네트워크 서비스로 실행 되는 실제 CLSAgent 이기 때문에% TEMP% 변수는%WINDIR%\ServiceProfiles\NetworkService\AppData\Local.로 확장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="196e4-159">However, because it is actually CLSAgent that is writing the file and CSLAgent runs as Network Service, the %TEMP% variable expands to %WINDIR%\ServiceProfiles\NetworkService\AppData\Local.</span></span>

<span data-ttu-id="196e4-160">이 명령은 사이트 Redmond의 각 컴퓨터와 풀의 CLSAgent에 게 추적 파일의 롤오버 값 크기를 40 mb로 설정 하도록 지시 합니다.</span><span class="sxs-lookup"><span data-stu-id="196e4-160">The command tells the CLSAgent on each computer and pool in the site Redmond to set the size of the rollover value on the tracing file to 40 megabytes.</span></span> <span data-ttu-id="196e4-161">다른 사이트의 컴퓨터와 풀은 명령에 영향을 받지 않으며, 기본적으로 (20mb) 또는 로깅 세션 시작 중에 정의 된 현재 구성 되어 있는 추적 로그 롤오버 값이 계속 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="196e4-161">Computers and pools in other sites will not be affected by the command, and will continue to use the currently configured trace log rollover value defined either by default (20 megabytes) or during the start of the logging session.</span></span>
### <a name="to-create-a-new-centralized-logging-service-configuration"></a><span data-ttu-id="196e4-162">중앙 집중화 된 새 로깅 서비스 구성을 만들려면</span><span class="sxs-lookup"><span data-stu-id="196e4-162">To create a new Centralized Logging Service configuration</span></span>

1. <span data-ttu-id="196e4-163">비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **비즈니스용 skype 2015**을 차례로 클릭 한 다음 비즈니스용 **skype Server management Shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="196e4-163">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="196e4-164">명령줄 프롬프트에 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="196e4-164">Type the following at the command-line prompt:</span></span>

   ```
   New-CsClsConfiguration -Identity <scope and name> [CsClsConfiguration options for this site]
   ```

    > [!NOTE]
    > <span data-ttu-id="196e4-165">새로운-CsClsConfiguration을 사용 하면 많은 선택적 구성 설정에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="196e4-165">New-CsClsConfiguration provides access to a large number of optional configuration settings.</span></span> <span data-ttu-id="196e4-166">구성 옵션에 대 한 자세한 내용은 [CsClsConfiguration 가져오기](https://docs.microsoft.com/powershell/module/skype/get-csclsconfiguration?view=skype-ps) 및 [중앙 로깅 서비스 구성 설정 이해](https://technet.microsoft.com/library/3c34e600-0b91-43dc-b4cc-90b6a70ee12e.aspx)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="196e4-166">For details about the configuration options, see [Get-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csclsconfiguration?view=skype-ps) and [Understanding Centralized Logging Service Configuration Settings](https://technet.microsoft.com/library/3c34e600-0b91-43dc-b4cc-90b6a70ee12e.aspx).</span></span>

<span data-ttu-id="196e4-167">예를 들어 캐시 파일에 대 한 네트워크 폴더, 로그 파일에 대 한 롤오버 기간 및 로그 파일에 대 한 롤오버 크기를 정의 하는 새 구성을 만들려면 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="196e4-167">For example, to create a new configuration that defines a network folder for cache files, rollover time period for the log files and rollover size for the log files, you would type:</span></span>

  ```
  New-CsClsConfiguration -Identity "site:Redmond" -CacheFileNetworkFolder "\\fs01.contoso.net\filestore\logfiles" -EtlFileRolloverMinutes 120 -EtlFileRolloverSizeMB 40
  ```

<span data-ttu-id="196e4-168">새 구성 만들기와 중앙 로깅 서비스의 새 속성을 정의 하는 방법을 주의 깊게 계획 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="196e4-168">You should carefully plan the creation of new configurations and how you define new properties for the Centralized Logging Service.</span></span> <span data-ttu-id="196e4-169">변경 하는 데는 주의를 기울여야 하며 문제 시나리오를 올바르게 기록 하는 기능에 대 한 영향을 이해 하 고 있는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="196e4-169">You should be cautious about making changes and make sure you understand the impact on your ability to properly log problem scenarios.</span></span> <span data-ttu-id="196e4-170">로그를 크기와 관리 하는 기능을 개선 하 고 발생 하는 문제 해결을 가능 하 게 하는 구성 변경 작업을 수행 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="196e4-170">You should make changes to the configuration that will enhance your ability to manage logs to a size and a rollover period that will allow problem solving when it arises.</span></span>
### <a name="to-remove-an-existing-centralized-logging-service-configuration"></a><span data-ttu-id="196e4-171">기존 중앙 로깅 서비스 구성을 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="196e4-171">To remove an existing Centralized Logging Service configuration</span></span>

1. <span data-ttu-id="196e4-172">비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **비즈니스용 skype 2015**을 차례로 클릭 한 다음 비즈니스용 **skype Server management Shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="196e4-172">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="196e4-173">명령줄 프롬프트에 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="196e4-173">Type the following at the command-line prompt:</span></span>

   ```
   Remove-CsClsConfiguration -Identity <scope and name>
   ```

<span data-ttu-id="196e4-174">예를 들어 로그 파일 롤오버 시간을 늘리기 위해 만든 중앙 로깅 서비스 구성을 제거 하려면 롤오버 로그 파일 크기를 늘리고 다음과 같이 로그 파일 캐시 위치를 네트워크 공유로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="196e4-174">For example, to remove a Centralized Logging Service configuration that you created to increase the log file rollover time, increase the rollover log file size, and set the log file cache location to a network share as follows:</span></span>

  ```
  Remove-CsClsConfiguration -Identity "site:Redmond"
  ```

> [!NOTE]
> <span data-ttu-id="196e4-175">"새 중앙 로깅 서비스 구성을 만들려면" 절차에서 만든 새 구성입니다.</span><span class="sxs-lookup"><span data-stu-id="196e4-175">This is the new configuration that was created in the procedure "To create a new Centralized Logging Service configuration."</span></span>

<span data-ttu-id="196e4-176">사이트 수준 구성을 제거 하도록 선택 하면 사이트에 전역 설정이 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="196e4-176">If you choose to remove a site-level configuration, the site will use the global settings.</span></span>
## <a name="see-also"></a><span data-ttu-id="196e4-177">참고 항목</span><span class="sxs-lookup"><span data-stu-id="196e4-177">See also</span></span>

[<span data-ttu-id="196e4-178">비즈니스용 Skype 2015에서 중앙 로깅 서비스에 대한 공급자 구성</span><span class="sxs-lookup"><span data-stu-id="196e4-178">Configure providers for Centralized Logging Service in Skype for Business Server 2015</span></span>](configure-providers.md)

[<span data-ttu-id="196e4-179">비즈니스용 Skype 2015에서 중앙 로깅 서비스에 대한 시나리오 구성</span><span class="sxs-lookup"><span data-stu-id="196e4-179">Configure scenarios for the Centralized Logging Service in Skype for Business Server 2015</span></span>](configure-scenarios.md)

[<span data-ttu-id="196e4-180">비즈니스용 Skype 2015의 중앙 로깅 서비스</span><span class="sxs-lookup"><span data-stu-id="196e4-180">Centralized Logging Service in Skype for Business 2015</span></span>](centralized-logging-service.md)

[<span data-ttu-id="196e4-181">Set-CsClsConfiguration</span><span class="sxs-lookup"><span data-stu-id="196e4-181">Set-CsClsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csclsconfiguration?view=skype-ps)

[<span data-ttu-id="196e4-182">Get-CsClsConfiguration</span><span class="sxs-lookup"><span data-stu-id="196e4-182">Get-CsClsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csclsconfiguration?view=skype-ps)

[<span data-ttu-id="196e4-183">New-CsClsConfiguration</span><span class="sxs-lookup"><span data-stu-id="196e4-183">New-CsClsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csclsconfiguration?view=skype-ps)

[<span data-ttu-id="196e4-184">-CsClsConfiguration 제거</span><span class="sxs-lookup"><span data-stu-id="196e4-184">Remove-CsClsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csclsconfiguration?view=skype-ps)
