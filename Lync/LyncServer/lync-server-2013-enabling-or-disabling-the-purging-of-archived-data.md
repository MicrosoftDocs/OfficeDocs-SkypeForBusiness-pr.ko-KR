---
title: 'Lync Server 2013: 보관 된 데이터의 삭제를 사용 하거나 사용 하지 않도록 설정'
description: 'Lync Server 2013: 보관 된 데이터의 삭제를 사용 하거나 사용 하지 않도록 설정 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling or disabling the purging of archived data
ms:assetid: 28cef09f-0970-4fc3-8315-f26689e3e187
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520968(v=OCS.15)
ms:contentKeyID: 48183678
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 442b99e2cfa6db303ca8edd216cbdf3b5c13cea9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546464"
---
# <a name="enabling-or-disabling-the-purging-of-archived-data-in-lync-server-2013"></a><span data-ttu-id="d4754-103">Lync Server 2013에서 보관 된 데이터의 삭제를 사용 하거나 사용 하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="d4754-103">Enabling or disabling the purging of archived data in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d4754-104">_**마지막으로 수정 된 항목:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="d4754-104">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="d4754-105">Lync Server 2013 제어판에서는 보관 구성을 사용 하 여 삭제를 사용 하거나 사용 하지 않도록 설정 하 고 제거가 구현 되는 방식을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4754-105">In Lync Server 2013 Control Panel, you use Archiving configurations to enable and disable purging and configure how purging is implemented.</span></span> <span data-ttu-id="d4754-106">여기에는 다음 보관 구성이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="d4754-106">This includes the following Archiving configurations:</span></span>

  - <span data-ttu-id="d4754-107">Lync Server 2013를 배포할 때 기본적으로 만들어지는 글로벌 구성입니다.</span><span class="sxs-lookup"><span data-stu-id="d4754-107">A global configuration that is created by default when you deploy Lync Server 2013.</span></span>

  - <span data-ttu-id="d4754-108">보관이 특정 사이트 또는 풀에 구현되는 방식을 지정하는 데 사용하도록 만들 수 있는 사이트 수준 및 풀 수준 구성(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="d4754-108">Optional site-level and pool-level configurations that you can create and use to specify how archiving is implemented for specific sites or pools.</span></span>

<span data-ttu-id="d4754-109">보관을 배포할 때 처음으로 보관 구성을 설정하지만 배포 이후에 구성을 변경, 추가 및 삭제할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4754-109">You initially set up Archiving configurations when you deploy Archiving, but you can change, add, and delete configurations after deployment.</span></span> <span data-ttu-id="d4754-110">지정할 수 있는 옵션 및 보관 구성의 계층 구조를 비롯 하 여 보관 구성이 구현 되는 방식에 대 한 자세한 내용은 계획 설명서, 배포 설명서 또는 작업 설명서의 [Lync Server 2013에서 보관이 작동 하는 방식을](lync-server-2013-how-archiving-works.md) 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="d4754-110">For details about how Archiving configurations are implemented, including which options you can specify and the hierarchy of Archiving configurations, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d4754-111">Lync Server 2013에 있는 사용자에 대해 보관을 사용 하려면 보관 정책을 구성 하 여 내부 통신, 외부 통신 또는 둘 모두에 대해 보관을 사용 하도록 설정할지 여부를 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4754-111">To use archiving for users who are homed on Lync Server 2013 you must configure Archiving policies to specify whether to enable archiving for internal communications, for external communications, or for both.</span></span> <span data-ttu-id="d4754-112">기본적으로는 내부 또는 외부 통신에 대해 보관이 사용하도록 설정되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d4754-112">By default, archiving is not enabled for either internal or external communications.</span></span> <span data-ttu-id="d4754-113">정책에서 보관을 사용하도록 설정하기 전에 이 섹션에 설명된 대로 배포와 특정 사이트 및 풀(선택 사항)에 적합한 보관 구성을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4754-113">Prior to enabling Archiving in any policies, you should specify the appropriate Archiving configurations for your deployment and, optionally, for specific sites and pools, as described in this section.</span></span> <span data-ttu-id="d4754-114">보관을 사용 하는 방법에 대 한 자세한 내용은 배포 설명서의 " <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Lync Server 2013에서 보관 정책 구성 및 할당</A> "을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="d4754-114">For details about enabling Archiving, see <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Configuring and assigning Archiving policies in Lync Server 2013</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="d4754-115">Microsoft Exchange 통합을 사용 하 여 Exchange 2013 서버에 보관 데이터와 파일을 저장 하 고 모든 사용자가 Exchange 2013 서버에 속해 있는 보관을 배포 하는 것을 결정 한 경우에는 토폴로지에서 SQL Server 데이터베이스 구성을 제거 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4754-115">If you decide after you deploy Archiving that you want to use Microsoft Exchange integration to store archiving data and files on Exchange 2013 servers and all your users are homed on your Exchange 2013 servers, you should remove the SQL Server database configuration from your topology.</span></span> <span data-ttu-id="d4754-116">토폴로지 작성기를 사용 하 여이 작업을 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4754-116">You must use Topology Builder to do this.</span></span> <span data-ttu-id="d4754-117">자세한 내용은 작업 설명서에서 <A href="lync-server-2013-changing-archiving-database-options.md">Lync Server 2013의 보관 데이터베이스 옵션 변경을</A> 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="d4754-117">For details, see <A href="lync-server-2013-changing-archiving-database-options.md">Changing Archiving database options in Lync Server 2013</A> in the Operations documentation.</span></span>



</div>

<div>

## <a name="to-enable-or-disable-purging-for-archiving"></a><span data-ttu-id="d4754-118">보관 삭제를 사용하거나 사용하지 않도록 설정하려면</span><span class="sxs-lookup"><span data-stu-id="d4754-118">To enable or disable purging for archiving</span></span>

1.  <span data-ttu-id="d4754-119">CsArchivingAdministrator 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="d4754-119">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="d4754-120">브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="d4754-120">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="d4754-121">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="d4754-121">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="d4754-122">왼쪽 탐색 모음에서 **모니터링 및 보관**을 클릭하고 **보관 구성**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d4754-122">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>

4.  <span data-ttu-id="d4754-123">보관 구성 목록에서 적절한 전역, 사이트 또는 풀 구성의 이름을 클릭하고 **편집**을 클릭한 후에 **자세한 정보 표시**를 클릭하고 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="d4754-123">Click the name of the appropriate global, site, or pool configuration in the list of archiving configurations, click **Edit**, click **Show details**, and then do the following:</span></span>
    
      - <span data-ttu-id="d4754-124">삭제를 사용하도록 설정하려면 **보관 데이터 삭제 사용** 확인란을 선택하고 다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="d4754-124">To enable purging, select the **Enable purging of archiving data** check box and then do one of the following:</span></span>
        
          - <span data-ttu-id="d4754-125">모든 레코드를 삭제하려면 **내보낸 보관 데이터 및 최대 기간(일)이 지난 저장된 보관 데이터 삭제**를 클릭하고 기간(일)을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d4754-125">To purge all records, click the **Purge exported archiving data and stored archiving data after maximum duration (days)**, and then specify the number of days.</span></span>
        
          - <span data-ttu-id="d4754-126">내보낸 데이터만 삭제하려면 **내보낸 보관 데이터만 삭제**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d4754-126">To purge only the data that has been exported, click **Purge exported archiving data only**.</span></span>
    
      - <span data-ttu-id="d4754-127">삭제를 사용하지 않도록 설정하려면 **보관 데이터 삭제 사용** 확인란 선택을 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="d4754-127">To disable purging, clear the **Enable purging of archiving data** check box.</span></span>

5.  <span data-ttu-id="d4754-128">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d4754-128">Click **Commit**.</span></span>

</div>

<div>

## <a name="enabling-or-disabling-the-purging-of-archiving-data-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="d4754-129">Windows PowerShell Cmdlet을 사용 하 여 보관 데이터 삭제를 사용 하거나 사용 하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="d4754-129">Enabling or Disabling the Purging of Archiving Data by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="d4754-130">Windows PowerShell 및 **get-csarchivingconfiguration** cmdlet을 사용 하 여 보관 데이터의 자동 삭제를 사용 하거나 사용 하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4754-130">Enabling and disabling the automated purging of archiving data can be managed by using Windows PowerShell and the **Set-CsArchivingConfiguration** cmdlet.</span></span> <span data-ttu-id="d4754-131">이 cmdlet은 Lync Server 2013 관리 셸 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4754-131">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="d4754-132">원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 사용 하 여 Microsoft Lync Server 2010 관리"를 참조 [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 하세요.</span><span class="sxs-lookup"><span data-stu-id="d4754-132">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-enable-the-purging-of-all-archiving-data"></a><span data-ttu-id="d4754-133">모든 보관 데이터를 삭제할 수 있도록 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="d4754-133">To enable the purging of all archiving data</span></span>

  - <span data-ttu-id="d4754-134">모든 보관 데이터의 삭제를 사용하도록 설정하려면 **EnablePurging** 속성을 true($True)로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="d4754-134">To enable the purging of all archiving data set the **EnablePurging** property to true ($True).</span></span> <span data-ttu-id="d4754-135">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d4754-135">For example:</span></span>
    
        Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True
    
    <span data-ttu-id="d4754-136">이 명령을 실행 한 후 모든 Lync Server는 **KeepArchivingDataForDays** 속성에 지정한 값 보다 오래 된 모든 보관 레코드를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4754-136">After this command is run, then every day Lync Server will purge all archiving records older than the value specified for the **KeepArchivingDataForDays** property.</span></span>

</div>

<div>

## <a name="to-enable-the-purging-only-of-exported-archiving-data"></a><span data-ttu-id="d4754-137">내보낸 보관 데이터만 삭제할 수 있도록 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="d4754-137">To enable the purging only of exported archiving data</span></span>

  - <span data-ttu-id="d4754-138">[Export-csarchivingdata](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData) cmdlet을 사용 하 여 데이터 파일로 내보낸 보관 레코드에 대 한 삭제를 제한 하려면 PurgeExportedArchivesOnly 속성을 True ($True)로도 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4754-138">To limit purging to archiving records that have been exported to a data file (by using the [Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData) cmdlet) you must also set the PurgeExportedArchivesOnly property to True ($True).</span></span> <span data-ttu-id="d4754-139">예제:</span><span class="sxs-lookup"><span data-stu-id="d4754-139">For example:</span></span>
    
        Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True -PurgeExportedArchivesOnly $True
    
    <span data-ttu-id="d4754-140">이 명령을 실행 한 후에는 Lync Server에서 두 가지 조건을 충족 하는 보관 레코드만 삭제 하 고 1) **KeepArchivingDataForDays** 속성에 지정 된 값 보다 오래 되었습니다. 그리고 2) **export-csarchivingdata** cmdlet을 사용 하 여 내보낸 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d4754-140">After this command is run, Lync Server will only purge archiving records that meet two criteria: 1) they are older than the value specified for the **KeepArchivingDataForDays** property; and, 2) they have been exported by using the **Export-CsArchivingData** cmdlet.</span></span>

</div>

<div>

## <a name="to-disable-the-purging-of-all-archiving-data"></a><span data-ttu-id="d4754-141">모든 보관 데이터의 삭제를 사용 하지 않도록 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="d4754-141">To disable the purging of all archiving data</span></span>

  - <span data-ttu-id="d4754-142">보관 레코드의 자동 삭제를 사용하지 않도록 설정하려면 **EnablePurging** 속성을 False($False)로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="d4754-142">To disable the automated purging of archiving records, set the **EnablePurging** property to False ($False).</span></span> <span data-ttu-id="d4754-143">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d4754-143">For example:</span></span>
    
        Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $False

</div>

<span data-ttu-id="d4754-144">보관 데이터를 제거 하기 위한 추가 옵션을 비롯 한 자세한 내용은 [get-csarchivingconfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsArchivingConfiguration) cmdlet에 대 한 도움말 항목을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="d4754-144">For more information, including additional options for purging archiving data, see the help topic for the [Set-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsArchivingConfiguration) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d4754-145">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d4754-145">See Also</span></span>


[<span data-ttu-id="d4754-146">Lync Server 2013에서 보관이 작동 하는 방식</span><span class="sxs-lookup"><span data-stu-id="d4754-146">How Archiving works in Lync Server 2013</span></span>](lync-server-2013-how-archiving-works.md)  


[<span data-ttu-id="d4754-147">Lync Server 2013에서 보관 정책 구성 및 할당</span><span class="sxs-lookup"><span data-stu-id="d4754-147">Configuring and assigning Archiving policies in Lync Server 2013</span></span>](lync-server-2013-configuring-and-assigning-archiving-policies.md)  
[<span data-ttu-id="d4754-148">조직, 사이트 및 풀에 대 한 Lync Server 2013의 보관 구성 옵션 관리</span><span class="sxs-lookup"><span data-stu-id="d4754-148">Managing Archiving configuration options in Lync Server 2013 for your organization, sites, and pools</span></span>](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

