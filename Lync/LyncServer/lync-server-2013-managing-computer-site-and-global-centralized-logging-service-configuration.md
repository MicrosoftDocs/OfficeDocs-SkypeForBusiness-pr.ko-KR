---
title: 컴퓨터, 사이트 및 전역 중앙 로깅 서비스 구성 관리
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing computer, site and global Centralized Logging Service configuration
ms:assetid: 93b9a354-9aea-4b3a-a4fe-68a89f436196
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688138(v=OCS.15)
ms:contentKeyID: 49733738
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f2d33a67b0b7e8c7e2771fbdc1055d003717dbb1
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136175"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="managing-computer-site-and-global-centralized-logging-service-configuration-in-lync-server-2013"></a><span data-ttu-id="27622-102">Lync Server 2013에서 컴퓨터, 사이트 및 전역 중앙화 된 로깅 서비스 구성 관리</span><span class="sxs-lookup"><span data-stu-id="27622-102">Managing computer, site and global Centralized Logging Service configuration in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="27622-103">_**마지막으로 수정 된 항목:** 2014-02-04_</span><span class="sxs-lookup"><span data-stu-id="27622-103">_**Topic Last Modified:** 2014-02-04_</span></span>

<span data-ttu-id="27622-104">중앙 로깅 서비스는 단일 컴퓨터, 컴퓨터 풀, 사이트 범위 (즉, 배포에 있는 컴퓨터 및 풀의 컬렉션을 포함 하는 사이트 Redmond)를 포함 하는 범위에서 또는 전역 범위에서 실행할 수 있습니다 ( -배포의 모든 컴퓨터 및 풀)</span><span class="sxs-lookup"><span data-stu-id="27622-104">The Centralized Logging Service can be run at a scope that includes a single computer, a pool of computers, at a site scope (that is, a defined site such as the site Redmond that contains a collection of computer and pools in your deployment), or at a global scope (that is, all computers and pools in your deployment).</span></span>

<span data-ttu-id="27622-105">Lync Server 관리 셸을 사용 하 여 중앙 로깅 서비스 범위를 구성 하려면 CsAdministrator 또는 CsServerAdministrator의 RBAC (역할 기반 액세스 제어) 보안 그룹 또는이를 포함 하는 사용자 지정 RBAC 역할의 구성원 이어야 합니다. 두 그룹 중 하나</span><span class="sxs-lookup"><span data-stu-id="27622-105">To configure the Centralized Logging Service scope by using the Lync Server Management Shell, you must be a member of either the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> <span data-ttu-id="27622-106">직접 만든 사용자 지정 RBAC 역할을 포함 하 여이 cmdlet이 할당 된 모든 RBAC 역할의 목록을 반환 하려면 Lync Server 관리 셸 또는 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="27622-106">To return a list of all the RBAC roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Lync Server Management Shell or the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "<Lync Server 2013 cmdlet>"}

<span data-ttu-id="27622-107">예:</span><span class="sxs-lookup"><span data-stu-id="27622-107">For example:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}

<div>


> [!NOTE]
> <span data-ttu-id="27622-108">Windows PowerShell에서는 CLSController를 사용 하 여 사용할 수 없는 더 많은 옵션과 추가 구성 옵션을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="27622-108">Windows PowerShell provides you more options and additional configuration options that are not available by using CLSController.exe.</span></span> <span data-ttu-id="27622-109">CLSController는 명령을 실행 하는 빠른 방법으로 간단한 메서드를 제공 하지만 CLSController에서 사용할 수 있는 명령 집합으로 제한 됩니다.</span><span class="sxs-lookup"><span data-stu-id="27622-109">CLSController offers a quick, concise method to run commands, but is limited to the set of commands available for the CLSController.</span></span> <span data-ttu-id="27622-110">Windows PowerShell은 CLSController의 명령 프로세서에서 사용할 수 있는 명령 으로만 제한 되지 않으며 보다 폭넓은 명령 집합 및 다양 한 옵션 집합을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="27622-110">Windows PowerShell is not limited to just the command available to the command processor of the CLSController, and provides a wider set of commands and a richer set of options.</span></span> <span data-ttu-id="27622-111">예를 들어 CLSController는-computers 및-풀에 대 한 범위 옵션을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="27622-111">For example, CLSController.exe does provide you with a scope options for –computers and –pools.</span></span> <span data-ttu-id="27622-112">Windows PowerShell을 사용 하면 대부분의 명령에서 컴퓨터 또는 풀을 표시할 수 있고, 새 시나리오를 정의할 때 (CLSController에는 사용자가 수정할 수 없는 제한 된 수의 시나리오 포함) 사이트 또는 전역 범위를 정의할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27622-112">With Windows PowerShell, you can indicate computers or pools in most commands, and when you define new scenarios (CLSController has a finite number of scenarios that are not user modifiable) you can define a site or global scope.</span></span> <span data-ttu-id="27622-113">Windows PowerShell의이 강력한 기능을 사용 하면 사이트 또는 전역 범위에 대 한 시나리오를 정의할 수 있지만 실제 로깅은 컴퓨터나 풀로 제한 됩니다.</span><span class="sxs-lookup"><span data-stu-id="27622-113">This powerful feature of Windows PowerShell enables you to define a scenario a site or global scope, but limit the actual logging to a computer or pool.</span></span><BR><span data-ttu-id="27622-114">Windows PowerShell 또는 CLSController에서 실행할 수 있는 명령줄 명령 사이에는 근본적인 차이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27622-114">There are fundamental differences between the command-line commands that you can run in Windows PowerShell or CLSController.</span></span> <span data-ttu-id="27622-115">Windows PowerShell을 사용 하면 시나리오를 구성 및 정의 하 고 문제 해결 시나리오에서 이러한 시나리오를 의미 있는 방식으로 다시 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27622-115">Windows PowerShell provides a rich method to configure and define scenarios, and to reuse those scenarios in a meaningful way for your troubleshooting scenarios.</span></span> <span data-ttu-id="27622-116">CLSController를 사용하면 빠르고 효율적으로 명령을 실행하고 결과를 얻을 수 있지만 CLSController의 명령 집합은 명령줄에서 사용할 수 있는 소수의 명령으로 한정됩니다.</span><span class="sxs-lookup"><span data-stu-id="27622-116">While CLSController does provide a fast and efficient way to issue commands and get results, the command set for CLSController is limited by the finite commands that you have available from the command line.</span></span> <span data-ttu-id="27622-117">Windows PowerShell cmdlet과 달리 CLSController에서는 새 시나리오를 정의 하거나, 사이트 또는 전역 수준에서 범위를 관리 하 고, 동적으로 구성할 수 없는 유한 명령 집합의 다양 한 제한 사항을 관리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="27622-117">Unlike the Windows PowerShell cmdlets, CLSController cannot define new scenarios, manage scope at a site or global level, and many other limitations of a finite command set that cannot be dynamically configured.</span></span> <span data-ttu-id="27622-118">CLSController는 빠른 실행을 위한 방법을 제공 하지만, Windows PowerShell을 사용 하면 CLSController를 사용할 때 보다 중앙 로깅 서비스 기능을 확장 하는 방법이 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="27622-118">While CLSController provides a means for fast execution, Windows PowerShell provides a means to extend the Centralized Logging Service functionality beyond what is possible with CLSController.</span></span>



</div>

<span data-ttu-id="27622-119">단일 컴퓨터 범위는-Computers 매개 변수를 사용 하 여 [검색-CsClsLogging](https://technet.microsoft.com/library/JJ619189(v=OCS.15)), [Show-csclslogging](https://technet.microsoft.com/library/JJ619173(v=OCS.15)), [Start-](https://technet.microsoft.com/library/JJ619190(v=OCS.15))csclslogging, 작업을 수행 하는 동안, [중지-](https://technet.microsoft.com/library/JJ619180(v=OCS.15))csclslogging, [동기화](https://technet.microsoft.com/library/JJ619169(v=OCS.15)) -csclslogging 및 [업데이트-](https://technet.microsoft.com/library/JJ619170(v=OCS.15)) csclslogging 명령을 실행 하는 동안 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27622-119">A single computer scope can be defined during the execution of a [Search-CsClsLogging](https://technet.microsoft.com/library/JJ619189(v=OCS.15)), [Show-CsClsLogging](https://technet.microsoft.com/library/JJ619173(v=OCS.15)), [Start-CsClsLogging](https://technet.microsoft.com/library/JJ619190(v=OCS.15)), [Stop-CsClsLogging](https://technet.microsoft.com/library/JJ619180(v=OCS.15)), [Sync-CsClsLogging](https://technet.microsoft.com/library/JJ619169(v=OCS.15)) and [Update-CsClsLogging](https://technet.microsoft.com/library/JJ619170(v=OCS.15)) command using the –Computers parameter.</span></span> <span data-ttu-id="27622-120">-Computers 매개 변수에는 대상 컴퓨터 FQDN(정규화된 도메인 이름)의 쉼표로 구분된 목록이 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="27622-120">The –Computers parameter accepts a comma separated list of fully qualified domain names (FQDNs) for the target computer.</span></span>

<div>


> [!TIP]
> <span data-ttu-id="27622-121">또한 -Pools와 로깅 명령을 실행할 풀의 쉼표로 구분된 목록을 정의할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27622-121">You can also define –Pools and a comma separated list of pools that you want to run the logging commands on.</span></span>



</div>

<span data-ttu-id="27622-122">사이트 및 전역 범위는 **새로운**-, **설정** **및 중앙** 집중식 로깅 서비스 cmdlet에서 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="27622-122">Site and Global scopes are defined in the **New-**, **Set-**, and **Remove-** Centralized Logging Service cmdlets.</span></span> <span data-ttu-id="27622-123">다음 예에서는 사이트 범위와 전역 범위를 설정하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="27622-123">The following examples demonstrate how to set a site and a global scope.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="27622-124">예로 든 명령들에는 다른 섹션에서 설명하는 매개 변수와 개념이 포함되어 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27622-124">The commands shown may contain parameters and concepts that are covered in other sections.</span></span> <span data-ttu-id="27622-125">이러한 명령은 <STRONG>-Identity</STRONG> 매개 변수를 사용하여 범위를 정의하는 방법을 보여 주기 위한 것이며, 다른 매개 변수들은 예제 명령을 완성하고 그러한 범위를 지정하는 방법을 보여 주기 위해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="27622-125">The example commands are intended to demonstrate the use of the <STRONG>–Identity</STRONG> parameter to define scope, and the other parameters are included for completeness and to specify the scope.</span></span> <span data-ttu-id="27622-126"><STRONG>Set-CsClsConfiguration</STRONG> cmdlet에 대한 자세한 내용은 작업 설명서에서 <A href="https://technet.microsoft.com/library/JJ619182(v=OCS.15)">Set-CsClsConfiguration</A>을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="27622-126">For details about the <STRONG>Set-CsClsConfiguration</STRONG> cmdlets, see <A href="https://technet.microsoft.com/library/JJ619182(v=OCS.15)">Set-CsClsConfiguration</A> in the Operations documentation.</span></span>



</div>

<div>

## <a name="to-retrieve-the-current-centralized-logging-service-configuration"></a><span data-ttu-id="27622-127">현재 중앙화 된 로깅 서비스 구성을 검색 하려면</span><span class="sxs-lookup"><span data-stu-id="27622-127">To retrieve the current Centralized Logging Service configuration</span></span>

1.  <span data-ttu-id="27622-128">**시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="27622-128">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="27622-129">명령줄 프롬프트에 다음 명령을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="27622-129">Type the following at the command-line prompt:</span></span>
    
        Get-CsClsConfiguration

<span data-ttu-id="27622-130">새로운 구성을 만들거나 기존 구성을 업데이트하려면 **New-CsClsConfiguration** 및 **Set-CsClsConfiguration** cmdlet을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="27622-130">Use the **New-CsClsConfiguration** and **Set-CsClsConfiguration** cmdlets to create a new configuration or to update an existing configuration.</span></span>

<span data-ttu-id="27622-131">**Get-CsClsConfiguration**을 실행 하면 배포에 현재 기본 전역 구성이 있지만 사이트 구성을 정의 하지 않은 다음과 같은 정보가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="27622-131">When you run **Get-CsClsConfiguration**, it displays information similar to the following screen shot, where the deployment currently has the default Global configuration, but no site configurations defined:</span></span>

<span data-ttu-id="27622-132">![Get CsClsConfiguration의 예제 출력입니다.](images/JJ688029.23f98ddc-fc48-499a-b6c5-752611f2a0b0(OCS.15).jpg "Get CsClsConfiguration의 예제 출력입니다.")</span><span class="sxs-lookup"><span data-stu-id="27622-132">![Sample output from Get-CsClsConfiguration.](images/JJ688029.23f98ddc-fc48-499a-b6c5-752611f2a0b0(OCS.15).jpg "Sample output from Get-CsClsConfiguration.")</span></span>

</div>

<div>

## <a name="to-retrieve-the-current-centralized-logging-service-configuration-from-the-computer-local-store"></a><span data-ttu-id="27622-133">컴퓨터 로컬 저장소에서 현재 중앙화 된 로깅 서비스 구성을 검색 하려면</span><span class="sxs-lookup"><span data-stu-id="27622-133">To retrieve the current Centralized Logging Service configuration from the computer local store</span></span>

1.  <span data-ttu-id="27622-134">**시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="27622-134">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="27622-135">명령줄 프롬프트에 다음 명령을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="27622-135">Type the following at the command-line prompt:</span></span>
    
        Get-CsClsConfiguration -LocalStore

<span data-ttu-id="27622-136">**Get-CsClsConfiguration** 에서 매개 변수를 지정 하지 않는 첫 번째 예제를 사용 하는 경우 명령은 데이터에 대 한 중앙 관리 저장소를 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="27622-136">When you use the first example where **Get-CsClsConfiguration** does not specify any parameters, the command references the Central Management store for the data.</span></span> <span data-ttu-id="27622-137">-LocalStore 매개 변수를 지정 하는 경우 명령은 중앙 관리 저장소 대신 컴퓨터 LocalStore를 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="27622-137">If you specify the parameter –LocalStore, the command references the computer LocalStore instead of the Central Management store.</span></span>

</div>

<div>

## <a name="to-retrieve-a-listing-of-scenarios-currently-defined"></a><span data-ttu-id="27622-138">현재 정의된 시나리오 목록을 검색하려면</span><span class="sxs-lookup"><span data-stu-id="27622-138">To retrieve a listing of scenarios currently defined</span></span>

1.  <span data-ttu-id="27622-139">**시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="27622-139">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="27622-140">명령줄 프롬프트에 다음 명령을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="27622-140">Type the following at the command-line prompt:</span></span>
    
        Get-CsClsConfiguration -Identity <scope and name> | Select-Object -ExpandProperty Scenarios
    
    <span data-ttu-id="27622-141">예를 들어 전역 범위로 정의된 시나리오를 검색하려면 다음과 같이 합니다.</span><span class="sxs-lookup"><span data-stu-id="27622-141">For example, to retrieve the scenarios that is defined at the global scope:</span></span>
    
        Get-CsClsConfiguration -Identity "global" | Select-Object -ExpandProperty Scenarios

<span data-ttu-id="27622-142">**Get-CsClsConfiguration** cmdlet은 항상 지정된 범위의 구성에 포함된 시나리오를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="27622-142">The cmdlet **Get-CsClsConfiguration** always displays the scenarios that are a part of a given scope’s configuration.</span></span> <span data-ttu-id="27622-143">대부분의 경우 시나리오가 모두 표시되지 않고 잘려서 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="27622-143">In most cases, all scenarios are not displayed, and are truncated.</span></span> <span data-ttu-id="27622-144">여기에 사용된 명령은 모든 시나리오와 사용된 공급자, 설정 및 플래그에 대한 일부 정보를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="27622-144">The command used here lists all of the scenarios and partial information about what providers, settings, and flags are used.</span></span>

</div>

<div>

## <a name="to-update-a-global-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a><span data-ttu-id="27622-145">Windows PowerShell을 사용 하 여 중앙 로깅 서비스에 대 한 전역 범위를 업데이트 하려면</span><span class="sxs-lookup"><span data-stu-id="27622-145">To update a global scope for the Centralized Logging Service by using Windows PowerShell</span></span>

1.  <span data-ttu-id="27622-146">**시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="27622-146">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="27622-147">명령줄 프롬프트에 다음 명령을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="27622-147">Type the following at the command-line prompt:</span></span>
    
        Set-CsClsConfiguration -Identity <scope> -EtlFileRolloverSizeMB <size for logging file in megabytes>
    
    <span data-ttu-id="27622-148">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="27622-148">For example:</span></span>
    
        Set-CsClsConfiguration -Identity "global" -EtlFileRolloverSizeMB 40

<span data-ttu-id="27622-p109">이 명령을 실행하면 배포에 포함된 각 컴퓨터와 풀의 CLSAgent에서 추적 파일 롤오버 크기 값이 40메가바이트로 설정됩니다. 이 명령은 모든 사이트의 컴퓨터와 풀에 영향을 미쳐 각각의 구성된 추적 로그 롤오버 값이 40메가바이트로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="27622-p109">The command tells the CLSAgent on each computer and pool in the deployment to set the size of the rollover value on the tracing file to 40 megabytes. Computers and pools in all sites are affected by the command, and will set their configured trace log rollover value to 40 megabytes.</span></span>

</div>

<div>

## <a name="to-update-a-site-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a><span data-ttu-id="27622-151">Windows PowerShell을 사용 하 여 중앙화 된 로깅 서비스에 대 한 사이트 범위를 업데이트 하려면</span><span class="sxs-lookup"><span data-stu-id="27622-151">To update a site scope for the Centralized Logging Service by using Windows PowerShell</span></span>

1.  <span data-ttu-id="27622-152">**시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="27622-152">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="27622-153">명령줄 프롬프트에 다음 명령을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="27622-153">Type the following at the command-line prompt:</span></span>
    
        Set-CsClsConfiguration -Identity <scope/site name> -EtlFileRolloverSizeMB <size for logging file in megabytes> -EtlFileFolder <default location %TEMP%\Tracing>
    
    <span data-ttu-id="27622-154">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="27622-154">For example:</span></span>
    
        Set-CsClsConfiguration -Identity "site/Redmond" -EtlFileRolloverSizeMB 40 -EtlFileFolder "C:\LogFiles\Tracing" 
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="27622-p110">이 예에 나와 있듯이 로그 파일의 기본 위치는 %TEMP%\Tracing입니다. 그러나 실제로 파일을 기록하는 것은 CLSAgent이고 CSLAgent는 네트워크 서비스로 실행되므로 %TEMP% 변수는 %WINDIR%\ServiceProfiles\NetworkService\AppData\Local로 확장됩니다.</span><span class="sxs-lookup"><span data-stu-id="27622-p110">As noted in the example, the default location of the log files is %TEMP%\Tracing. However, because it is actually CLSAgent that is writing the file and CSLAgent runs as Network Service, the %TEMP% variable expands to %WINDIR%\ServiceProfiles\NetworkService\AppData\Local.</span></span>

    
    </div>

<span data-ttu-id="27622-p111">이 명령을 실행하면 Redmond 사이트에 포함된 각 컴퓨터와 풀의 CLSAgent에서 추적 파일 롤오버 크기 값이 40메가바이트로 설정됩니다. 다른 사이트의 컴퓨터와 풀은 이 명령의 영향을 받지 않으며 기본적으로 정의되어 있거나(20메가바이트) 로깅 세션을 시작할 때 정의되어 현재 구성된 추적 로그 롤오버 값을 계속 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="27622-p111">The command tells the CLSAgent on each computer and pool in the site Redmond to set the size of the rollover value on the tracing file to 40 megabytes. Computers and pools in other sites will not be affected by the command, and will continue to use the currently configured trace log rollover value defined either by default (20 megabytes) or during the start of the logging session.</span></span>

</div>

<div>

## <a name="to-create-a-new-centralized-logging-service-configuration"></a><span data-ttu-id="27622-159">새 중앙 로깅 서비스 구성을 만들려면</span><span class="sxs-lookup"><span data-stu-id="27622-159">To create a new Centralized Logging Service configuration</span></span>

1.  <span data-ttu-id="27622-160">**시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="27622-160">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="27622-161">명령줄 프롬프트에 다음 명령을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="27622-161">Type the following at the command-line prompt:</span></span>
    
        New-CsClsConfiguration -Identity <scope and name> [CsClsConfiguration options for this site]
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="27622-162">New-CsClsConfiguration을 사용하면 다수의 선택적 구성 설정에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27622-162">New-CsClsConfiguration provides access to a large number of optional configuration settings.</span></span> <span data-ttu-id="27622-163">구성 옵션에 대 한 자세한 내용은 <A href="https://technet.microsoft.com/library/JJ619179(v=OCS.15)">Get-CsClsConfiguration</A> 및 <A href="lync-server-2013-understanding-centralized-logging-service-configuration-settings.md">Lync Server 2013의 중앙 로깅 서비스 구성 설정 이해</A>를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="27622-163">For details about the configuration options, see <A href="https://technet.microsoft.com/library/JJ619179(v=OCS.15)">Get-CsClsConfiguration</A> and <A href="lync-server-2013-understanding-centralized-logging-service-configuration-settings.md">Understanding Centralized Logging Service configuration settings in Lync Server 2013</A>.</span></span>

    
    </div>
    
    <span data-ttu-id="27622-164">예를 들어 캐시 파일의 네트워크 폴더, 로그 파일의 롤오버 기간 및 로그 파일의 롤오버 크기를 정의하는 새로운 구성을 만들려면 다음 명령을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="27622-164">For example, to create a new configuration that defines a network folder for cache files, rollover time period for the log files and rollover size for the log files, you would type:</span></span>
    
        New-CsClsConfiguration -Identity "site:Redmond" -CacheFileNetworkFolder "\\fs01.contoso.net\filestore\logfiles" -EtlFileRolloverMinutes 120 -EtlFileRolloverSizeMB 40

<span data-ttu-id="27622-165">새 구성의 생성을 신중 하 게 계획 하 고 중앙화 된 로깅 서비스에 대 한 새 속성을 정의 하는 방법을 신중히 고려해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="27622-165">You should carefully plan the creation of new configurations and how you define new properties for the Centralized Logging Service.</span></span> <span data-ttu-id="27622-166">구성을 변경할 때에는 주의를 기울여야 하며 변경 후에 문제 시나리오를 올바르게 로깅할 수 있을지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="27622-166">You should be cautious about making changes and make sure you understand the impact on your ability to properly log problem scenarios.</span></span> <span data-ttu-id="27622-167">적절한 크기와 롤오버 기간으로 로그를 더욱 효과적으로 관리하여 문제 발생 시 문제를 손쉽게 해결할 수 있도록 구성을 변경해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="27622-167">You should make changes to the configuration that will enhance your ability to manage logs to a size and a rollover period that will allow problem solving when it arises.</span></span>

</div>

<div>

## <a name="to-remove-an-existing-centralized-logging-service-configuration"></a><span data-ttu-id="27622-168">기존의 중앙화 된 로깅 서비스 구성을 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="27622-168">To remove an existing Centralized Logging Service configuration</span></span>

1.  <span data-ttu-id="27622-169">**시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="27622-169">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="27622-170">명령줄 프롬프트에 다음 명령을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="27622-170">Type the following at the command-line prompt:</span></span>
    
        Remove-CsClsConfiguration -Identity <scope and name>
    
    <span data-ttu-id="27622-171">예를 들어 로그 파일 롤오버 시간을 늘리기 위해 만든 중앙 로깅 서비스 구성을 제거 하려면 롤오버 로그 파일 크기를 높인 다음 다음과 같이 로그 파일 캐시 위치를 네트워크 공유로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="27622-171">For example, to remove a Centralized Logging Service configuration that you created to increase the log file rollover time, increase the rollover log file size, and set the log file cache location to a network share as follows:</span></span>
    
        Remove-CsClsConfiguration -Identity "site:Redmond"
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="27622-172">이 구성은 "새 중앙화 된 로깅 서비스 구성을 만들려면" 절차에서 만든 새 구성입니다.</span><span class="sxs-lookup"><span data-stu-id="27622-172">This is the new configuration that was created in the procedure "To create a new Centralized Logging Service configuration."</span></span>

    
    </div>

<span data-ttu-id="27622-173">사이트 수준 구성을 제거하는 경우 사이트에 전역 설정이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="27622-173">If you choose to remove a site-level configuration, the site will use the global settings.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="27622-174">참고 항목</span><span class="sxs-lookup"><span data-stu-id="27622-174">See Also</span></span>


[<span data-ttu-id="27622-175">Lync Server 2013의 중앙 로깅 서비스 개요</span><span class="sxs-lookup"><span data-stu-id="27622-175">Overview of the Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-overview-of-the-centralized-logging-service.md)  


[<span data-ttu-id="27622-176">Lync Server 2013에서 중앙 로깅 서비스 구성 설정 관리</span><span class="sxs-lookup"><span data-stu-id="27622-176">Managing the Centralized Logging Service configuration settings in Lync Server 2013</span></span>](lync-server-2013-managing-the-centralized-logging-service-configuration-settings.md)  
<span data-ttu-id="27622-177">[설정-CsClsConfiguration](https://technet.microsoft.com/library/JJ619182(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="27622-177">[Set-CsClsConfiguration](https://technet.microsoft.com/library/JJ619182(v=OCS.15))</span></span>  
<span data-ttu-id="27622-178">[Get-CsClsConfiguration](https://technet.microsoft.com/library/JJ619179(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="27622-178">[Get-CsClsConfiguration](https://technet.microsoft.com/library/JJ619179(v=OCS.15))</span></span>  
<span data-ttu-id="27622-179">[신규-CsClsConfiguration](https://technet.microsoft.com/library/JJ619177(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="27622-179">[New-CsClsConfiguration](https://technet.microsoft.com/library/JJ619177(v=OCS.15))</span></span>  
<span data-ttu-id="27622-180">[제거-CsClsConfiguration](https://technet.microsoft.com/library/JJ619191(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="27622-180">[Remove-CsClsConfiguration](https://technet.microsoft.com/library/JJ619191(v=OCS.15))</span></span>  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

