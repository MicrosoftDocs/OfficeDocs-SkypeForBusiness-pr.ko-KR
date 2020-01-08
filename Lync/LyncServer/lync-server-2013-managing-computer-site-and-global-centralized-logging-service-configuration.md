---
title: 컴퓨터, 사이트 및 전역 중앙 로깅 서비스 구성 관리
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Managing computer, site and global Centralized Logging Service configuration
ms:assetid: 93b9a354-9aea-4b3a-a4fe-68a89f436196
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688138(v=OCS.15)
ms:contentKeyID: 49733738
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 02c18e57b81daf93139493d046b8b2124e04e767
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982062"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-computer-site-and-global-centralized-logging-service-configuration-in-lync-server-2013"></a><span data-ttu-id="ed3d2-102">Lync Server 2013에서 컴퓨터, 사이트 및 전역 중앙 로깅 서비스 구성 관리</span><span class="sxs-lookup"><span data-stu-id="ed3d2-102">Managing computer, site and global Centralized Logging Service configuration in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ed3d2-103">_**마지막으로 수정한 주제:** 2014-02-04_</span><span class="sxs-lookup"><span data-stu-id="ed3d2-103">_**Topic Last Modified:** 2014-02-04_</span></span>

<span data-ttu-id="ed3d2-104">중앙 로깅 서비스는 단일 컴퓨터, 컴퓨터 풀, 사이트 범위 (예: 배포의 컴퓨터 및 풀의 컬렉션이 포함 된 사이트) 또는 전역 범위 (즉, 지정 된 사이트)에서 실행할 수 있습니다. , 배포의 모든 컴퓨터 및 풀.</span><span class="sxs-lookup"><span data-stu-id="ed3d2-104">The Centralized Logging Service can be run at a scope that includes a single computer, a pool of computers, at a site scope (that is, a defined site such as the site Redmond that contains a collection of computer and pools in your deployment), or at a global scope (that is, all computers and pools in your deployment).</span></span>

<span data-ttu-id="ed3d2-105">Lync Server Management Shell을 사용 하 여 중앙 로깅 서비스 범위를 구성 하려면 CsAdministrator 또는 CsServerAdministrator 역할 기반 액세스 제어 (RBAC) 보안 그룹 또는 다음을 포함 하는 사용자 지정 RBAC 역할의 구성원 이어야 합니다. 두 그룹 중 하나.</span><span class="sxs-lookup"><span data-stu-id="ed3d2-105">To configure the Centralized Logging Service scope by using the Lync Server Management Shell, you must be a member of either the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> <span data-ttu-id="ed3d2-106">이 cmdlet이 할당 된 모든 RBAC 역할 목록 (직접 만든 사용자 지정 RBAC 역할 포함)을 반환 하려면 Lync Server 관리 셸 또는 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed3d2-106">To return a list of all the RBAC roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Lync Server Management Shell or the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "<Lync Server 2013 cmdlet>"}

<span data-ttu-id="ed3d2-107">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ed3d2-107">For example:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}

<div>


> [!NOTE]
> <span data-ttu-id="ed3d2-108">Windows PowerShell에서는 CLSController를 사용 하 여 사용할 수 없는 더 많은 옵션과 추가 구성 옵션을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed3d2-108">Windows PowerShell provides you more options and additional configuration options that are not available by using CLSController.exe.</span></span> <span data-ttu-id="ed3d2-109">CLSController는 명령을 실행 하는 간략 하 고 간결한 메서드를 제공 하지만 CLSController에서 사용할 수 있는 명령 집합으로 제한 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed3d2-109">CLSController offers a quick, concise method to run commands, but is limited to the set of commands available for the CLSController.</span></span> <span data-ttu-id="ed3d2-110">Windows PowerShell은 CLSController의 명령 프로세서에서 사용할 수 있는 명령 으로만 제한 되지 않으며 광범위 한 명령 집합 및 다양 한 옵션 집합을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed3d2-110">Windows PowerShell is not limited to just the command available to the command processor of the CLSController, and provides a wider set of commands and a richer set of options.</span></span> <span data-ttu-id="ed3d2-111">예를 들어 CLSController는 – 컴퓨터 및 – 풀에 대 한 범위 옵션을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed3d2-111">For example, CLSController.exe does provide you with a scope options for –computers and –pools.</span></span> <span data-ttu-id="ed3d2-112">Windows PowerShell을 사용 하면 대부분의 명령에 컴퓨터 또는 풀을 표시할 수 있으며, 새 시나리오를 정의할 때 (CLSController에 사용자가 수정할 수 없는 제한 된 수의 시나리오가 있는 경우) 사이트 또는 전역 범위를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed3d2-112">With Windows PowerShell, you can indicate computers or pools in most commands, and when you define new scenarios (CLSController has a finite number of scenarios that are not user modifiable) you can define a site or global scope.</span></span> <span data-ttu-id="ed3d2-113">이 Windows PowerShell의 강력한 기능을 통해 사이트 또는 전역 범위에 시나리오를 정의할 수 있지만 실제 로깅은 컴퓨터 또는 풀로 제한 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed3d2-113">This powerful feature of Windows PowerShell enables you to define a scenario a site or global scope, but limit the actual logging to a computer or pool.</span></span><BR><span data-ttu-id="ed3d2-114">Windows PowerShell 또는 CLSController에서 실행할 수 있는 명령줄 명령 간에는 기본적인 차이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed3d2-114">There are fundamental differences between the command-line commands that you can run in Windows PowerShell or CLSController.</span></span> <span data-ttu-id="ed3d2-115">Windows PowerShell은 시나리오를 구성 및 정의 하 고 문제 해결 시나리오에 의미 있는 방식으로 해당 시나리오를 다시 사용 하는 다양 한 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed3d2-115">Windows PowerShell provides a rich method to configure and define scenarios, and to reuse those scenarios in a meaningful way for your troubleshooting scenarios.</span></span> <span data-ttu-id="ed3d2-116">CLSController는 명령을 실행 하 고 결과를 얻을 수 있는 빠르고 효율적인 방법을 제공 하지만 CLSController에 대 한 명령 집합은 명령줄에서 사용할 수 있는 유한 명령으로 제한 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed3d2-116">While CLSController does provide a fast and efficient way to issue commands and get results, the command set for CLSController is limited by the finite commands that you have available from the command line.</span></span> <span data-ttu-id="ed3d2-117">Windows PowerShell cmdlet과 달리 CLSController는 새 시나리오를 정의 하거나, 사이트 또는 전역 수준의 범위를 관리 하 고, 동적으로 구성할 수 없는 유한 명령 집합의 여러 다른 제한 사항에 대 한 다양 한 제한을 정의할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ed3d2-117">Unlike the Windows PowerShell cmdlets, CLSController cannot define new scenarios, manage scope at a site or global level, and many other limitations of a finite command set that cannot be dynamically configured.</span></span> <span data-ttu-id="ed3d2-118">CLSController는 빠른 실행을 위한 수단을 제공 하는 반면, Windows PowerShell은 CLSController에서 가능한 기능 외에 중앙 집중식 로깅 서비스 기능을 확장 하는 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed3d2-118">While CLSController provides a means for fast execution, Windows PowerShell provides a means to extend the Centralized Logging Service functionality beyond what is possible with CLSController.</span></span>



</div>

<span data-ttu-id="ed3d2-119">[Search-](https://technet.microsoft.com/en-us/library/JJ619189(v=OCS.15))csclslogging, [표시-csclslogging](https://technet.microsoft.com/en-us/library/JJ619173(v=OCS.15)), [시작-csclslogging](https://technet.microsoft.com/en-us/library/JJ619190(v=OCS.15)), [동기화-](https://technet.microsoft.com/en-us/library/JJ619169(v=OCS.15)) csclslogging, Sync-csclslogging, [–](https://technet.microsoft.com/en-us/library/JJ619180(v=OCS.15))Computers 매개 변수를 사용 하 여 [csclslogging Update](https://technet.microsoft.com/en-us/library/JJ619170(v=OCS.15)) 명령을 실행 하는 동안 단일 컴퓨터 범위를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed3d2-119">A single computer scope can be defined during the execution of a [Search-CsClsLogging](https://technet.microsoft.com/en-us/library/JJ619189(v=OCS.15)), [Show-CsClsLogging](https://technet.microsoft.com/en-us/library/JJ619173(v=OCS.15)), [Start-CsClsLogging](https://technet.microsoft.com/en-us/library/JJ619190(v=OCS.15)), [Stop-CsClsLogging](https://technet.microsoft.com/en-us/library/JJ619180(v=OCS.15)), [Sync-CsClsLogging](https://technet.microsoft.com/en-us/library/JJ619169(v=OCS.15)) and [Update-CsClsLogging](https://technet.microsoft.com/en-us/library/JJ619170(v=OCS.15)) command using the –Computers parameter.</span></span> <span data-ttu-id="ed3d2-120">– Computers 매개 변수는 대상 컴퓨터에 대 한 Fqdn (정규화 된 도메인 이름) 목록을 쉼표로 구분 하 여 받아들입니다.</span><span class="sxs-lookup"><span data-stu-id="ed3d2-120">The –Computers parameter accepts a comma separated list of fully qualified domain names (FQDNs) for the target computer.</span></span>

<div>


> [!TIP]
> <span data-ttu-id="ed3d2-121">로깅 명령을 실행 하려는 풀 및 쉼표로 구분 된 풀 목록을 정의할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed3d2-121">You can also define –Pools and a comma separated list of pools that you want to run the logging commands on.</span></span>



</div>

<span data-ttu-id="ed3d2-122">사이트 및 전역 범위는 **새로운** **중앙의 로깅**서비스 cmdlet에 정의 되어 있습니다 \*\*\*\* .</span><span class="sxs-lookup"><span data-stu-id="ed3d2-122">Site and Global scopes are defined in the **New-**, **Set-**, and **Remove-** Centralized Logging Service cmdlets.</span></span> <span data-ttu-id="ed3d2-123">다음 예제에서는 사이트 및 전역 범위를 설정 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ed3d2-123">The following examples demonstrate how to set a site and a global scope.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="ed3d2-124">표시 되는 명령에는 다른 섹션에서 설명 하는 매개 변수 및 개념이 포함 되어 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed3d2-124">The commands shown may contain parameters and concepts that are covered in other sections.</span></span> <span data-ttu-id="ed3d2-125">예제 명령은 <STRONG>– Identity</STRONG> 매개 변수를 사용 하 여 범위를 정의 하 고 나머지 매개 변수를 완전성에 포함 하 고 범위를 지정 하기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ed3d2-125">The example commands are intended to demonstrate the use of the <STRONG>–Identity</STRONG> parameter to define scope, and the other parameters are included for completeness and to specify the scope.</span></span> <span data-ttu-id="ed3d2-126"><STRONG>Set-csclsconfiguration</STRONG> cmdlet에 대 한 자세한 내용은 작업 설명서의 <A href="https://technet.microsoft.com/en-us/library/JJ619182(v=OCS.15)">Set-csclsconfiguration</A> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ed3d2-126">For details about the <STRONG>Set-CsClsConfiguration</STRONG> cmdlets, see <A href="https://technet.microsoft.com/en-us/library/JJ619182(v=OCS.15)">Set-CsClsConfiguration</A> in the Operations documentation.</span></span>



</div>

<div>

## <a name="to-retrieve-the-current-centralized-logging-service-configuration"></a><span data-ttu-id="ed3d2-127">현재 중앙 집중화 된 로깅 서비스 구성을 검색 하려면</span><span class="sxs-lookup"><span data-stu-id="ed3d2-127">To retrieve the current Centralized Logging Service configuration</span></span>

1.  <span data-ttu-id="ed3d2-128">Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed3d2-128">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="ed3d2-129">명령줄 프롬프트에 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed3d2-129">Type the following at the command-line prompt:</span></span>
    
        Get-CsClsConfiguration

<span data-ttu-id="ed3d2-130">새 구성을 만들거나 기존 구성을 업데이트 하기 위해 **새로운 csclsconfiguration** 및 **Set csclsconfiguration** cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed3d2-130">Use the **New-CsClsConfiguration** and **Set-CsClsConfiguration** cmdlets to create a new configuration or to update an existing configuration.</span></span>

<span data-ttu-id="ed3d2-131">**Get-CsClsConfiguration**을 실행 하면 배포에 현재 기본 전역 구성이 있지만 사이트 구성이 정의 되지 않은 다음 스크린샷은 다음과 같은 정보가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed3d2-131">When you run **Get-CsClsConfiguration**, it displays information similar to the following screen shot, where the deployment currently has the default Global configuration, but no site configurations defined:</span></span>

<span data-ttu-id="ed3d2-132">![Get CsClsConfiguration의 샘플 출력입니다.] (images/JJ688029.23f98ddc-fc48-499a-b6c5-752611f2a0b0(OCS.15).jpg "Get CsClsConfiguration의 샘플 출력입니다.")</span><span class="sxs-lookup"><span data-stu-id="ed3d2-132">![Sample output from Get-CsClsConfiguration.](images/JJ688029.23f98ddc-fc48-499a-b6c5-752611f2a0b0(OCS.15).jpg "Sample output from Get-CsClsConfiguration.")</span></span>

</div>

<div>

## <a name="to-retrieve-the-current-centralized-logging-service-configuration-from-the-computer-local-store"></a><span data-ttu-id="ed3d2-133">컴퓨터 로컬 저장소에서 현재 중앙 집중화 된 로깅 서비스 구성을 검색 하려면</span><span class="sxs-lookup"><span data-stu-id="ed3d2-133">To retrieve the current Centralized Logging Service configuration from the computer local store</span></span>

1.  <span data-ttu-id="ed3d2-134">Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed3d2-134">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="ed3d2-135">명령줄 프롬프트에 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed3d2-135">Type the following at the command-line prompt:</span></span>
    
        Get-CsClsConfiguration -LocalStore

<span data-ttu-id="ed3d2-136">**Get-CsClsConfiguration** 이 매개 변수를 지정 하지 않는 첫 번째 예제를 사용 하는 경우 명령은 데이터에 대 한 중앙 관리 저장소를 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed3d2-136">When you use the first example where **Get-CsClsConfiguration** does not specify any parameters, the command references the Central Management store for the data.</span></span> <span data-ttu-id="ed3d2-137">-LocalStore 매개 변수를 지정 하는 경우이 명령은 중앙 관리 저장소 대신 컴퓨터 LocalStore를 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed3d2-137">If you specify the parameter –LocalStore, the command references the computer LocalStore instead of the Central Management store.</span></span>

</div>

<div>

## <a name="to-retrieve-a-listing-of-scenarios-currently-defined"></a><span data-ttu-id="ed3d2-138">현재 정의 된 시나리오 목록을 검색 하려면</span><span class="sxs-lookup"><span data-stu-id="ed3d2-138">To retrieve a listing of scenarios currently defined</span></span>

1.  <span data-ttu-id="ed3d2-139">Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed3d2-139">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="ed3d2-140">명령줄 프롬프트에 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed3d2-140">Type the following at the command-line prompt:</span></span>
    
        Get-CsClsConfiguration -Identity <scope and name> | Select-Object -ExpandProperty Scenarios
    
    <span data-ttu-id="ed3d2-141">예를 들어 전역 범위에서 정의 된 시나리오를 검색 하려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed3d2-141">For example, to retrieve the scenarios that is defined at the global scope:</span></span>
    
        Get-CsClsConfiguration -Identity "global" | Select-Object -ExpandProperty Scenarios

<span data-ttu-id="ed3d2-142">Cmdlet **Get CsClsConfiguration** 은 항상 지정 된 범위의 구성에 속하는 시나리오를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed3d2-142">The cmdlet **Get-CsClsConfiguration** always displays the scenarios that are a part of a given scope’s configuration.</span></span> <span data-ttu-id="ed3d2-143">대부분의 경우, 모든 시나리오가 표시 되지 않고 잘릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed3d2-143">In most cases, all scenarios are not displayed, and are truncated.</span></span> <span data-ttu-id="ed3d2-144">여기에 사용 되는 명령에는 모든 시나리오와 사용 되는 공급자, 설정 및 플래그에 대 한 일부 정보가 나열 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed3d2-144">The command used here lists all of the scenarios and partial information about what providers, settings, and flags are used.</span></span>

</div>

<div>

## <a name="to-update-a-global-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a><span data-ttu-id="ed3d2-145">Windows PowerShell을 사용 하 여 중앙 로깅 서비스에 대 한 전역 범위를 업데이트 하려면</span><span class="sxs-lookup"><span data-stu-id="ed3d2-145">To update a global scope for the Centralized Logging Service by using Windows PowerShell</span></span>

1.  <span data-ttu-id="ed3d2-146">Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed3d2-146">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="ed3d2-147">명령줄 프롬프트에 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed3d2-147">Type the following at the command-line prompt:</span></span>
    
        Set-CsClsConfiguration -Identity <scope> -EtlFileRolloverSizeMB <size for logging file in megabytes>
    
    <span data-ttu-id="ed3d2-148">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ed3d2-148">For example:</span></span>
    
        Set-CsClsConfiguration -Identity "global" -EtlFileRolloverSizeMB 40

<span data-ttu-id="ed3d2-149">이 명령은 배포의 각 컴퓨터와 풀에 CLSAgent를 알려 추적 파일의 롤오버 값 크기를 40 메가바이트 단위로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed3d2-149">The command tells the CLSAgent on each computer and pool in the deployment to set the size of the rollover value on the tracing file to 40 megabytes.</span></span> <span data-ttu-id="ed3d2-150">모든 사이트의 컴퓨터 및 풀은 명령의 영향을 받으며, 구성 된 추적 로그 롤오버 값을 40 메가바이트 ()로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed3d2-150">Computers and pools in all sites are affected by the command, and will set their configured trace log rollover value to 40 megabytes.</span></span>

</div>

<div>

## <a name="to-update-a-site-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a><span data-ttu-id="ed3d2-151">Windows PowerShell을 사용 하 여 중앙 로깅 서비스의 사이트 범위를 업데이트 하려면</span><span class="sxs-lookup"><span data-stu-id="ed3d2-151">To update a site scope for the Centralized Logging Service by using Windows PowerShell</span></span>

1.  <span data-ttu-id="ed3d2-152">Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed3d2-152">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="ed3d2-153">명령줄 프롬프트에 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed3d2-153">Type the following at the command-line prompt:</span></span>
    
        Set-CsClsConfiguration -Identity <scope/site name> -EtlFileRolloverSizeMB <size for logging file in megabytes> -EtlFileFolder <default location %TEMP%\Tracing>
    
    <span data-ttu-id="ed3d2-154">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ed3d2-154">For example:</span></span>
    
        Set-CsClsConfiguration -Identity "site/Redmond" -EtlFileRolloverSizeMB 40 -EtlFileFolder "C:\LogFiles\Tracing" 
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="ed3d2-155">이 예제에 나와 있는 것 처럼 로그 파일의 기본 위치 는%TEMP%\Tracing.입니다.</span><span class="sxs-lookup"><span data-stu-id="ed3d2-155">As noted in the example, the default location of the log files is %TEMP%\Tracing.</span></span> <span data-ttu-id="ed3d2-156">그러나 파일을 기록 하 고 CSLAgent가 네트워크 서비스로 실행 되는 실제 CLSAgent 이기 때문 에% TEMP% 변수 는%WINDIR%\ServiceProfiles\NetworkService\AppData\Local.로 확장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed3d2-156">However, because it is actually CLSAgent that is writing the file and CSLAgent runs as Network Service, the %TEMP% variable expands to %WINDIR%\ServiceProfiles\NetworkService\AppData\Local.</span></span>

    
    </div>

<span data-ttu-id="ed3d2-157">이 명령은 사이트 Redmond의 각 컴퓨터와 풀의 CLSAgent에 게 추적 파일의 롤오버 값 크기를 40 mb로 설정 하도록 지시 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed3d2-157">The command tells the CLSAgent on each computer and pool in the site Redmond to set the size of the rollover value on the tracing file to 40 megabytes.</span></span> <span data-ttu-id="ed3d2-158">다른 사이트의 컴퓨터와 풀은 명령에 영향을 받지 않으며, 기본적으로 (20mb) 또는 로깅 세션 시작 중에 정의 된 현재 구성 되어 있는 추적 로그 롤오버 값이 계속 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed3d2-158">Computers and pools in other sites will not be affected by the command, and will continue to use the currently configured trace log rollover value defined either by default (20 megabytes) or during the start of the logging session.</span></span>

</div>

<div>

## <a name="to-create-a-new-centralized-logging-service-configuration"></a><span data-ttu-id="ed3d2-159">중앙 집중화 된 새 로깅 서비스 구성을 만들려면</span><span class="sxs-lookup"><span data-stu-id="ed3d2-159">To create a new Centralized Logging Service configuration</span></span>

1.  <span data-ttu-id="ed3d2-160">Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed3d2-160">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="ed3d2-161">명령줄 프롬프트에 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed3d2-161">Type the following at the command-line prompt:</span></span>
    
        New-CsClsConfiguration -Identity <scope and name> [CsClsConfiguration options for this site]
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="ed3d2-162">새로운-CsClsConfiguration을 사용 하면 많은 선택적 구성 설정에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed3d2-162">New-CsClsConfiguration provides access to a large number of optional configuration settings.</span></span> <span data-ttu-id="ed3d2-163">구성 옵션에 대 한 자세한 내용은 온 <A href="https://technet.microsoft.com/en-us/library/JJ619179(v=OCS.15)">-CsClsConfiguration</A> 및 <A href="lync-server-2013-understanding-centralized-logging-service-configuration-settings.md">Lync Server 2013의 중앙 로깅 서비스 구성 설정 이해</A>를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ed3d2-163">For details about the configuration options, see <A href="https://technet.microsoft.com/en-us/library/JJ619179(v=OCS.15)">Get-CsClsConfiguration</A> and <A href="lync-server-2013-understanding-centralized-logging-service-configuration-settings.md">Understanding Centralized Logging Service configuration settings in Lync Server 2013</A>.</span></span>

    
    </div>
    
    <span data-ttu-id="ed3d2-164">예를 들어 캐시 파일에 대 한 네트워크 폴더, 로그 파일에 대 한 롤오버 기간 및 로그 파일에 대 한 롤오버 크기를 정의 하는 새 구성을 만들려면 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed3d2-164">For example, to create a new configuration that defines a network folder for cache files, rollover time period for the log files and rollover size for the log files, you would type:</span></span>
    
        New-CsClsConfiguration -Identity "site:Redmond" -CacheFileNetworkFolder "\\fs01.contoso.net\filestore\logfiles" -EtlFileRolloverMinutes 120 -EtlFileRolloverSizeMB 40

<span data-ttu-id="ed3d2-165">새 구성 만들기와 중앙 로깅 서비스의 새 속성을 정의 하는 방법을 주의 깊게 계획 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed3d2-165">You should carefully plan the creation of new configurations and how you define new properties for the Centralized Logging Service.</span></span> <span data-ttu-id="ed3d2-166">변경 하는 데는 주의를 기울여야 하며 문제 시나리오를 올바르게 기록 하는 기능에 대 한 영향을 이해 하 고 있는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed3d2-166">You should be cautious about making changes and make sure you understand the impact on your ability to properly log problem scenarios.</span></span> <span data-ttu-id="ed3d2-167">로그를 크기와 관리 하는 기능을 개선 하 고 발생 하는 문제 해결을 가능 하 게 하는 구성 변경 작업을 수행 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="ed3d2-167">You should make changes to the configuration that will enhance your ability to manage logs to a size and a rollover period that will allow problem solving when it arises.</span></span>

</div>

<div>

## <a name="to-remove-an-existing-centralized-logging-service-configuration"></a><span data-ttu-id="ed3d2-168">기존 중앙 로깅 서비스 구성을 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="ed3d2-168">To remove an existing Centralized Logging Service configuration</span></span>

1.  <span data-ttu-id="ed3d2-169">Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed3d2-169">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="ed3d2-170">명령줄 프롬프트에 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed3d2-170">Type the following at the command-line prompt:</span></span>
    
        Remove-CsClsConfiguration -Identity <scope and name>
    
    <span data-ttu-id="ed3d2-171">예를 들어 로그 파일 롤오버 시간을 늘리기 위해 만든 중앙 로깅 서비스 구성을 제거 하려면 롤오버 로그 파일 크기를 늘리고 다음과 같이 로그 파일 캐시 위치를 네트워크 공유로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed3d2-171">For example, to remove a Centralized Logging Service configuration that you created to increase the log file rollover time, increase the rollover log file size, and set the log file cache location to a network share as follows:</span></span>
    
        Remove-CsClsConfiguration -Identity "site:Redmond"
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="ed3d2-172">"새 중앙 로깅 서비스 구성을 만들려면" 절차에서 만든 새 구성입니다.</span><span class="sxs-lookup"><span data-stu-id="ed3d2-172">This is the new configuration that was created in the procedure "To create a new Centralized Logging Service configuration."</span></span>

    
    </div>

<span data-ttu-id="ed3d2-173">사이트 수준 구성을 제거 하도록 선택 하면 사이트에 전역 설정이 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed3d2-173">If you choose to remove a site-level configuration, the site will use the global settings.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ed3d2-174">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ed3d2-174">See Also</span></span>


[<span data-ttu-id="ed3d2-175">Lync Server 2013의 중앙 집중화 된 로깅 서비스 개요</span><span class="sxs-lookup"><span data-stu-id="ed3d2-175">Overview of the Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-overview-of-the-centralized-logging-service.md)  


[<span data-ttu-id="ed3d2-176">Lync Server 2013에서 중앙 집중화 된 로깅 서비스 구성 설정 관리</span><span class="sxs-lookup"><span data-stu-id="ed3d2-176">Managing the Centralized Logging Service configuration settings in Lync Server 2013</span></span>](lync-server-2013-managing-the-centralized-logging-service-configuration-settings.md)  
<span data-ttu-id="ed3d2-177">[Set-CsClsConfiguration](https://technet.microsoft.com/en-us/library/JJ619182(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ed3d2-177">[Set-CsClsConfiguration](https://technet.microsoft.com/en-us/library/JJ619182(v=OCS.15))</span></span>  
<span data-ttu-id="ed3d2-178">[Get-CsClsConfiguration](https://technet.microsoft.com/en-us/library/JJ619179(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ed3d2-178">[Get-CsClsConfiguration](https://technet.microsoft.com/en-us/library/JJ619179(v=OCS.15))</span></span>  
<span data-ttu-id="ed3d2-179">[New-CsClsConfiguration](https://technet.microsoft.com/en-us/library/JJ619177(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ed3d2-179">[New-CsClsConfiguration](https://technet.microsoft.com/en-us/library/JJ619177(v=OCS.15))</span></span>  
<span data-ttu-id="ed3d2-180">[-CsClsConfiguration 제거](https://technet.microsoft.com/en-us/library/JJ619191(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ed3d2-180">[Remove-CsClsConfiguration](https://technet.microsoft.com/en-us/library/JJ619191(v=OCS.15))</span></span>  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

