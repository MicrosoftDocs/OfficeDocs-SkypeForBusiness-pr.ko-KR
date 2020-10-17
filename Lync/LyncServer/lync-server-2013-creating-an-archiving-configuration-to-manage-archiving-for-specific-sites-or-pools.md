---
title: 'Lync Server 2013: 특정 사이트 또는 풀에 대 한 보관을 관리 하기 위한 보관 구성 만들기'
description: 'Lync Server 2013: 특정 사이트 또는 풀에 대 한 보관을 관리 하는 보관 구성을 만듭니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Creating an Archiving configuration to manage Archiving for specific sites or pools
ms:assetid: c5c864a6-96c7-4bbb-ab7c-61eb1744246c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205251(v=OCS.15)
ms:contentKeyID: 48185361
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0ab19f2d8900693ef0fcb14d8f6d862b22c355bd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48563114"
---
# <a name="creating-an-archiving-configuration-in-lync-server-2013-to-manage-archiving-for-specific-sites-or-pools"></a><span data-ttu-id="3181a-103">Lync Server 2013에서 보관 구성을 만들어 특정 사이트 또는 풀에 대 한 보관 관리</span><span class="sxs-lookup"><span data-stu-id="3181a-103">Creating an Archiving configuration in Lync Server 2013 to manage Archiving for specific sites or pools</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3181a-104">_**마지막으로 수정 된 항목:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="3181a-104">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="3181a-105">Lync Server 2013 제어판에서는 보관 구성을 사용 하 여 배포에서 보관이 구현 되는 방식을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3181a-105">In Lync Server 2013 Control Panel, you use Archiving configurations to control how archiving is implemented in your deployment.</span></span> <span data-ttu-id="3181a-106">여기에는 다음 보관 구성이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="3181a-106">This includes the following Archiving configurations:</span></span>

  - <span data-ttu-id="3181a-107">Lync Server 2013를 배포할 때 기본적으로 만들어지는 글로벌 구성입니다.</span><span class="sxs-lookup"><span data-stu-id="3181a-107">A global configuration that is created by default when you deploy Lync Server 2013.</span></span>

  - <span data-ttu-id="3181a-108">보관이 특정 사이트 또는 풀에 구현되는 방식을 지정하는 데 사용하도록 만들 수 있는 사이트 수준 및 풀 수준 구성(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="3181a-108">Optional site-level and pool-level configurations that you can create and use to specify how archiving is implemented for specific sites or pools.</span></span>

<span data-ttu-id="3181a-109">보관을 배포할 때 처음으로 보관 구성을 설정하지만 배포 이후에 구성을 변경, 추가 및 삭제할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3181a-109">You initially set up Archiving configurations when you deploy Archiving, but you can change, add, and delete configurations after deployment.</span></span> <span data-ttu-id="3181a-110">지정할 수 있는 옵션 및 보관 구성의 계층 구조를 비롯 하 여 보관 구성이 구현 되는 방식에 대 한 자세한 내용은 계획 설명서, 배포 설명서 또는 작업 설명서의 [Lync Server 2013에서 보관이 작동 하는 방식을](lync-server-2013-how-archiving-works.md) 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="3181a-110">For details about how Archiving configurations are implemented, including which options you can specify and the hierarchy of Archiving configurations, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3181a-111">보관을 사용 하려면 외부 통신을 위해 또는 Lync Server 2013에 있는 사용자에 대해 보관 정책을 사용 하도록 설정할지 여부를 지정 하는 보관 정책 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3181a-111">To use archiving, you must configure Archiving policies to specify whether to enable archiving for internal communications, for external communications, or for both for users homed on Lync Server 2013.</span></span> <span data-ttu-id="3181a-112">기본적으로 보관은 내부 또는 외부 통신 중 하나에 대해 사용하지 않도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="3181a-112">By default, archiving is not enabled for either internal or external communications.</span></span> <span data-ttu-id="3181a-113">어느 정책에서든 보관을 사용하도록 설정하려면 이 섹션에 설명된 대로 먼저 배포 환경과 특정 사이트/풀(선택 사항)에 대해 적합한 보관 구성을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3181a-113">Before enabling Archiving in any policies, you should specify the appropriate Archiving configurations for your deployment and, optionally, for specific sites and pools, as described in this section.</span></span> <span data-ttu-id="3181a-114">보관을 사용 하는 방법에 대 한 자세한 내용은 배포 설명서의 " <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Lync Server 2013에서 보관 정책 구성 및 할당</A> "을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="3181a-114">For details about enabling Archiving, see <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Configuring and assigning Archiving policies in Lync Server 2013</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="3181a-115">Microsoft Exchange 통합을 사용 하 여 Exchange 2013 서버에 보관 데이터와 파일을 저장 하 고 모든 사용자가 Exchange 2013 서버에 속해 있는 보관을 배포 하는 것을 결정 한 경우에는 토폴로지에서 SQL Server 데이터베이스 구성을 제거 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3181a-115">If you decide after you deploy Archiving that you want to use Microsoft Exchange integration to store archiving data and files on Exchange 2013 servers and all your users are homed on your Exchange 2013 servers, you should remove the SQL Server database configuration from your topology.</span></span> <span data-ttu-id="3181a-116">토폴로지 작성기를 사용 하 여이 작업을 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3181a-116">You must use Topology Builder to do this.</span></span> <span data-ttu-id="3181a-117">자세한 내용은 작업 설명서에서 <A href="lync-server-2013-changing-archiving-database-options.md">Lync Server 2013의 보관 데이터베이스 옵션 변경을</A> 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="3181a-117">For details, see <A href="lync-server-2013-changing-archiving-database-options.md">Changing Archiving database options in Lync Server 2013</A> in the Operations documentation.</span></span>



</div>

<div>

## <a name="to-create-an-archiving-configuration-for-a-site-or-pool"></a><span data-ttu-id="3181a-118">사이트 또는 풀의 보관 구성을 만들려면</span><span class="sxs-lookup"><span data-stu-id="3181a-118">To create an archiving configuration for a site or pool</span></span>

1.  <span data-ttu-id="3181a-119">CsArchivingAdministrator 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="3181a-119">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="3181a-120">브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="3181a-120">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="3181a-121">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="3181a-121">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="3181a-122">왼쪽 탐색 모음에서 **모니터링 및 보관**을 클릭하고 **보관 구성**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3181a-122">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>

4.  <span data-ttu-id="3181a-123">**보관 구성** 페이지에서 **새로 만들기**를 클릭하고 다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="3181a-123">On the **Archiving Configuration** page, click **New**, and then do one of the following:</span></span>
    
      - <span data-ttu-id="3181a-124">사이트 보관 구성을 만들려면 **사이트 구성**을 클릭한 후 **사이트 선택**에서 보관을 구성할 사이트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3181a-124">To create a site archiving configuration, click **Site Configuration** and then, in **Select a site**, select the site to be configured for archiving.</span></span>
    
      - <span data-ttu-id="3181a-125">풀 보관 구성을 만들려면 **풀 구성**을 클릭한 후 **풀 선택**에서 보관을 구성할 풀을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3181a-125">To create a pool archiving configuration, click **Pool Configuration** and then, in **Select a pool**, select the pool to be configured for archiving.</span></span>

5.  <span data-ttu-id="3181a-126">**새 보관 설정 만들기**의 **보관 설정** 드롭다운 목록 상자에서 다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="3181a-126">In **New Archiving Setting**, in the **Archiving setting** drop-down list box, do one of the following:</span></span>
    
      - <span data-ttu-id="3181a-127">메신저 대화 세션에 대해서만 보관을 사용하도록 설정하려면 **메신저 대화 세션 보관**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3181a-127">To enable archiving only for instant messaging (IM) sessions, click **Archive IM sessions**.</span></span>
    
      - <span data-ttu-id="3181a-128">메신저 대화 세션 및 웹 회의 모두에 대해 보관을 사용하도록 설정하려면 **메신저 대화 및 웹 회의 세션 보관**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3181a-128">To enable archiving for both IM sessions and web conferences, click **Archive IM and web conferencing sessions**.</span></span>
    
      - <span data-ttu-id="3181a-129">정책에 대해 보관을 사용하지 않도록 설정하려면 **보관 사용 안 함**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3181a-129">To disable archiving for the policy, click **Disable archiving**.</span></span>

6.  <span data-ttu-id="3181a-130">또한 **새 보관 설정**에서 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="3181a-130">Also in **New Archiving Setting**, do the following:</span></span>
    
      - <span data-ttu-id="3181a-131">보관을 사용할 수 없을 경우 작업을 차단하려면 **보관에 실패할 경우 메신저 대화 또는 웹 회의 세션 차단** 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3181a-131">To block activity when archiving is not available, select the **Block instant messaging (IM) or web conferencing sessions if archiving fails** check box.</span></span>
    
      - <span data-ttu-id="3181a-132">Microsoft Exchange Server를 사용 하 여 보관 데이터를 저장 하려면 **Microsoft exchange 통합** 확인란을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="3181a-132">To use Microsoft Exchange Server to store archiving data, click the **Microsoft Exchange integration** check box.</span></span>
    
      - <span data-ttu-id="3181a-133">데이터 삭제를 사용하도록 설정하려면 **보관 데이터 삭제 사용** 대화 상자를 선택한 후 다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="3181a-133">To enable data purging, select the **Enable purging of archiving data** check box, and then do one of the following:</span></span>
        
          - <span data-ttu-id="3181a-134">특정 일 수 이후 삭제되도록 설정하려면 **내보낸 보관 데이터 및 최대 기간(일)이 지난 저장된 보관 데이터 삭제**를 클릭한 다음 일 수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="3181a-134">To specify purging after a specific number of days, click **Purge exported archiving data and stored archiving data after maximum duration (days)**, and then specify the number of days.</span></span>
        
          - <span data-ttu-id="3181a-135">내보낸 보관 데이터로 삭제를 제한하려면 **내보낸 보관 데이터만 삭제**를 클릭합니다,</span><span class="sxs-lookup"><span data-stu-id="3181a-135">To limit purging to archiving data that has been exported, click **Purge exported archiving data only**.</span></span>

7.  <span data-ttu-id="3181a-136">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3181a-136">Click **Commit**.</span></span>

</div>

<div>

## <a name="creating-archiving-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="3181a-137">Windows PowerShell Cmdlet을 사용 하 여 보관 구성 설정 만들기</span><span class="sxs-lookup"><span data-stu-id="3181a-137">Creating Archiving Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="3181a-138">보관 구성 설정은 Windows PowerShell 및 New-CsArchivingConfiguration cmdlet을 사용 하 여 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3181a-138">Archiving configuration settings can be created by using Windows PowerShell and the New-CsArchivingConfiguration cmdlet.</span></span> <span data-ttu-id="3181a-139">이 cmdlet은 Lync Server 2013 관리 셸 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3181a-139">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="3181a-140">원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 사용 하 여 Microsoft Lync Server 2010 관리"를 참조 [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 하세요.</span><span class="sxs-lookup"><span data-stu-id="3181a-140">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-create-a-new-collection-of-archiving-configuration-settings-for-a-site"></a><span data-ttu-id="3181a-141">사이트에 대 한 새 보관 구성 설정 컬렉션을 만들려면</span><span class="sxs-lookup"><span data-stu-id="3181a-141">To create a new collection of archiving configuration settings for a site</span></span>

  - <span data-ttu-id="3181a-142">다음 명령을 실행하면 레드몬드 사이트에 대해 새 보관 구성 설정 컬렉션이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="3181a-142">The following command creates a new collection of archiving configuration settings for the Redmond site:</span></span>
    
        New-CsArchivingConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-create-a-new-collection-of-archiving-configuration-settings-that-only-allow-im-archiving"></a><span data-ttu-id="3181a-143">IM 보관만 허용 하는 새 보관 구성 설정 모음을 만들려면</span><span class="sxs-lookup"><span data-stu-id="3181a-143">To create a new collection of archiving configuration settings that only allow IM archiving</span></span>

  - <span data-ttu-id="3181a-p107">이전 명령에서 필수 Identity 매개 변수를 제외하고는 지정된 매개 변수가 없으므로 새 구성 설정 컬렉션에는 모든 속성의 기본값이 사용됩니다. 다른 속성 값을 사용하는 설정을 만들려면 간단히 적합한 매개 변수와 매개 변수 값을 포함하면 됩니다. 예를 들어 메신저 대화 세션의 보관을 기본적으로 허용하는 보관 구성 설정 컬렉션을 만들려면 다음과 같은 명령만 사용하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3181a-p107">Because no parameters (other than the mandatory Identity parameter) were specified in the preceding command, the new collection of configuration settings will use the default values for all its properties. To create settings that use different property values, simply include the appropriate parameter and parameter value. For example, to create a collection of archiving configuration settings that, by default, allow archiving of instant messaging sessions, only use a command like this:</span></span>
    
        New-CsArchivingConfiguration -Identity "site:Redmond" -EnableArchiving "ImOnly"

</div>

<div>

## <a name="to-specify-multiple-property-values-when-creating-archiving-configuration-settings"></a><span data-ttu-id="3181a-147">보관 구성 설정을 만들 때 여러 속성 값을 지정 하려면</span><span class="sxs-lookup"><span data-stu-id="3181a-147">To specify multiple property values when creating archiving configuration settings</span></span>

  - <span data-ttu-id="3181a-p108">여러 매개 변수를 포함하여 여러 속성 값을 수정할 수 있습니다. 예를 들어 다음 명령을 실행하면 메신저 대화 세션을 보관하고 보관 서비스를 사용할 수 없는 메신저 대화는 차단하는 새로운 설정을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3181a-p108">Multiple property values can be modified by including multiple parameters. For example, this command configures the new settings to archive instant messaging sessions and to block instant messaging of the archiving service is not available:</span></span>
    
        New-CsArchivingConfiguration -Identity "site:Redmond" -EnableArchiving "ImOnly" -BlockOnArchiveFailure $True

</div>

<span data-ttu-id="3181a-150">자세한 내용은 [get-csarchivingconfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsArchivingConfiguration) cmdlet에 대 한 도움말 항목을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="3181a-150">For more information, see the help topic for the [New-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsArchivingConfiguration) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3181a-151">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3181a-151">See Also</span></span>


[<span data-ttu-id="3181a-152">Lync Server 2013에서 보관이 작동 하는 방식</span><span class="sxs-lookup"><span data-stu-id="3181a-152">How Archiving works in Lync Server 2013</span></span>](lync-server-2013-how-archiving-works.md)  


[<span data-ttu-id="3181a-153">조직, 사이트 및 풀에 대 한 Lync Server 2013의 보관 구성 옵션 관리</span><span class="sxs-lookup"><span data-stu-id="3181a-153">Managing Archiving configuration options in Lync Server 2013 for your organization, sites, and pools</span></span>](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

