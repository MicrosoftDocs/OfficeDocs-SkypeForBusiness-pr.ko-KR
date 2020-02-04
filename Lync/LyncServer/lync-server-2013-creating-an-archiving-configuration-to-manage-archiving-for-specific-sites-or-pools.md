---
title: 'Lync Server 2013: 특정 사이트 또는 풀에 대 한 보관을 관리 하기 위한 보관 구성 만들기'
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
ms.openlocfilehash: 3b0495a15d19adba9ac21fb7817347a16b78bc13
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762746"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="creating-an-archiving-configuration-in-lync-server-2013-to-manage-archiving-for-specific-sites-or-pools"></a><span data-ttu-id="07b1b-102">Lync Server 2013에서 보관 구성을 만들어 특정 사이트 또는 풀에 대 한 보관 관리</span><span class="sxs-lookup"><span data-stu-id="07b1b-102">Creating an Archiving configuration in Lync Server 2013 to manage Archiving for specific sites or pools</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="07b1b-103">_**마지막으로 수정한 주제:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="07b1b-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="07b1b-104">Lync Server 2013 제어판에서 보관 구성을 사용 하 여 배포에서 보관을 구현 하는 방법을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="07b1b-104">In Lync Server 2013 Control Panel, you use Archiving configurations to control how archiving is implemented in your deployment.</span></span> <span data-ttu-id="07b1b-105">여기에는 다음과 같은 보관 구성이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="07b1b-105">This includes the following Archiving configurations:</span></span>

  - <span data-ttu-id="07b1b-106">Lync Server 2013을 배포할 때 기본적으로 만들어지는 전역 구성입니다.</span><span class="sxs-lookup"><span data-stu-id="07b1b-106">A global configuration that is created by default when you deploy Lync Server 2013.</span></span>

  - <span data-ttu-id="07b1b-107">특정 사이트 또는 풀에 대해 보관을 구현 하는 방법을 지정 하기 위해 만들고 사용할 수 있는 선택적 사이트 수준 및 풀 수준 구성입니다.</span><span class="sxs-lookup"><span data-stu-id="07b1b-107">Optional site-level and pool-level configurations that you can create and use to specify how archiving is implemented for specific sites or pools.</span></span>

<span data-ttu-id="07b1b-108">보관을 배포할 때 초기에 보관 구성을 설정 했지만 배포 후 구성을 변경, 추가 및 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07b1b-108">You initially set up Archiving configurations when you deploy Archiving, but you can change, add, and delete configurations after deployment.</span></span> <span data-ttu-id="07b1b-109">사용자가 지정할 수 있는 옵션 및 보관 구성의 계층 구조를 비롯 하 여 보관 구성을 구현 하는 방법에 대 한 자세한 내용은 계획 문서, 배포 설명서 또는 운영 설명서의 [Lync Server 2013에서 보관을 작동 하는 방법을](lync-server-2013-how-archiving-works.md) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="07b1b-109">For details about how Archiving configurations are implemented, including which options you can specify and the hierarchy of Archiving configurations, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="07b1b-110">보관을 사용 하려면 보관 정책을 구성 하 여 Lync Server 2013에 있는 사용자에 대해 내부 통신, 외부 통신 또는 둘 다에 대해 보관을 사용할지 여부를 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="07b1b-110">To use archiving, you must configure Archiving policies to specify whether to enable archiving for internal communications, for external communications, or for both for users homed on Lync Server 2013.</span></span> <span data-ttu-id="07b1b-111">기본적으로 내부 또는 외부 통신에 대해 보관을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="07b1b-111">By default, archiving is not enabled for either internal or external communications.</span></span> <span data-ttu-id="07b1b-112">모든 정책에서 보관을 사용 하도록 설정 하기 전에이 섹션에서 설명 하는 대로 배포에 적절 한 보관 구성을 지정 하 고, 선택적으로 특정 사이트 및 풀에 대해 해당 하는 경우를 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="07b1b-112">Before enabling Archiving in any policies, you should specify the appropriate Archiving configurations for your deployment and, optionally, for specific sites and pools, as described in this section.</span></span> <span data-ttu-id="07b1b-113">보관을 사용 하도록 설정 하는 방법에 대 한 자세한 내용은 배포 설명서의 <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Lync Server 2013에서 보관 정책 구성 및 할당</A> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="07b1b-113">For details about enabling Archiving, see <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Configuring and assigning Archiving policies in Lync Server 2013</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="07b1b-114">Microsoft Exchange 통합을 사용 하 여 Exchange 2013 서버에 보관 된 데이터와 파일을 저장 하 고 모든 사용자가 Exchange 2013 서버에 있는 경우 보관을 배포 하는 것을 결정 한 경우 SQL Server 데이터베이스 구성을 제거 해야 합니다. 토폴로지에서</span><span class="sxs-lookup"><span data-stu-id="07b1b-114">If you decide after you deploy Archiving that you want to use Microsoft Exchange integration to store archiving data and files on Exchange 2013 servers and all your users are homed on your Exchange 2013 servers, you should remove the SQL Server database configuration from your topology.</span></span> <span data-ttu-id="07b1b-115">이 작업을 수행 하려면 토폴로지 작성기를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="07b1b-115">You must use Topology Builder to do this.</span></span> <span data-ttu-id="07b1b-116">자세한 내용은 운영 설명서의 <A href="lync-server-2013-changing-archiving-database-options.md">Lync Server 2013에서 보관 데이터베이스 옵션 변경을</A> 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="07b1b-116">For details, see <A href="lync-server-2013-changing-archiving-database-options.md">Changing Archiving database options in Lync Server 2013</A> in the Operations documentation.</span></span>



</div>

<div>

## <a name="to-create-an-archiving-configuration-for-a-site-or-pool"></a><span data-ttu-id="07b1b-117">사이트 또는 풀에 대 한 보관 구성을 만들려면</span><span class="sxs-lookup"><span data-stu-id="07b1b-117">To create an archiving configuration for a site or pool</span></span>

1.  <span data-ttu-id="07b1b-118">CsArchivingAdministrator 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="07b1b-118">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="07b1b-119">브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="07b1b-119">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="07b1b-120">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="07b1b-120">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="07b1b-121">왼쪽 탐색 모음에서 **모니터링 및 보관**을 클릭 한 다음 **구성 보관**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="07b1b-121">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>

4.  <span data-ttu-id="07b1b-122">**보관 구성** 페이지에서 **새로 만들기**를 클릭 하 고 다음 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="07b1b-122">On the **Archiving Configuration** page, click **New**, and then do one of the following:</span></span>
    
      - <span data-ttu-id="07b1b-123">사이트 보관 구성을 만들려면 **사이트 구성을** 클릭 한 다음 **사이트 선택**에서 보관을 위해 구성할 사이트를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="07b1b-123">To create a site archiving configuration, click **Site Configuration** and then, in **Select a site**, select the site to be configured for archiving.</span></span>
    
      - <span data-ttu-id="07b1b-124">풀 보관 구성을 만들려면 **풀 구성을** 클릭 한 다음 **풀 선택**에서 보관을 위해 구성할 풀을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="07b1b-124">To create a pool archiving configuration, click **Pool Configuration** and then, in **Select a pool**, select the pool to be configured for archiving.</span></span>

5.  <span data-ttu-id="07b1b-125">**새 보관 설정**의 **보관 설정** 드롭다운 목록 상자에서 다음 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="07b1b-125">In **New Archiving Setting**, in the **Archiving setting** drop-down list box, do one of the following:</span></span>
    
      - <span data-ttu-id="07b1b-126">IM (인스턴트 메시징) 세션에 대해서만 보관을 사용 하도록 설정 하려면 **im 세션 보관**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="07b1b-126">To enable archiving only for instant messaging (IM) sessions, click **Archive IM sessions**.</span></span>
    
      - <span data-ttu-id="07b1b-127">IM 세션과 웹 컨퍼런스 모두에 대해 보관을 사용 하도록 설정 하려면 **im 및 웹 회의 세션 보관**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="07b1b-127">To enable archiving for both IM sessions and web conferences, click **Archive IM and web conferencing sessions**.</span></span>
    
      - <span data-ttu-id="07b1b-128">정책 보관을 사용 하지 않도록 설정 하려면 **보관 사용 안 함을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="07b1b-128">To disable archiving for the policy, click **Disable archiving**.</span></span>

6.  <span data-ttu-id="07b1b-129">또한 **새 보관 설정**에서 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="07b1b-129">Also in **New Archiving Setting**, do the following:</span></span>
    
      - <span data-ttu-id="07b1b-130">보관을 사용할 수 없는 경우 활동을 차단 하려면 **인스턴트 메시지 (IM) 또는 웹 회의 세션 (보관 실패 인 경우) 차단** 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="07b1b-130">To block activity when archiving is not available, select the **Block instant messaging (IM) or web conferencing sessions if archiving fails** check box.</span></span>
    
      - <span data-ttu-id="07b1b-131">Microsoft Exchange Server를 사용 하 여 보관 데이터를 저장 하려면 **Microsoft exchange 통합** 확인란을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="07b1b-131">To use Microsoft Exchange Server to store archiving data, click the **Microsoft Exchange integration** check box.</span></span>
    
      - <span data-ttu-id="07b1b-132">데이터 제거를 사용 하도록 설정 하려면 **데이터 보관 제거 사용** 확인란을 선택 하 고 다음 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="07b1b-132">To enable data purging, select the **Enable purging of archiving data** check box, and then do one of the following:</span></span>
        
          - <span data-ttu-id="07b1b-133">특정 일 수 후 제거를 지정 하려면 **내보낸 데이터 보관 및 최대 기간 (일) 이후 저장 된 데이터 보관**을 클릭 한 다음 일 수를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="07b1b-133">To specify purging after a specific number of days, click **Purge exported archiving data and stored archiving data after maximum duration (days)**, and then specify the number of days.</span></span>
        
          - <span data-ttu-id="07b1b-134">내보낸 데이터 보관을 위해 지우기를 제한 하려면 **내보낸 데이터 보관만**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="07b1b-134">To limit purging to archiving data that has been exported, click **Purge exported archiving data only**.</span></span>

7.  <span data-ttu-id="07b1b-135">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="07b1b-135">Click **Commit**.</span></span>

</div>

<div>

## <a name="creating-archiving-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="07b1b-136">Windows PowerShell Cmdlet을 사용 하 여 보관 구성 설정 만들기</span><span class="sxs-lookup"><span data-stu-id="07b1b-136">Creating Archiving Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="07b1b-137">Windows PowerShell 및 새 CsArchivingConfiguration cmdlet을 사용 하 여 보관 구성 설정을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07b1b-137">Archiving configuration settings can be created by using Windows PowerShell and the New-CsArchivingConfiguration cmdlet.</span></span> <span data-ttu-id="07b1b-138">이 cmdlet은 Lync Server 2013 관리 셸에서 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07b1b-138">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="07b1b-139">원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="07b1b-139">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-create-a-new-collection-of-archiving-configuration-settings-for-a-site"></a><span data-ttu-id="07b1b-140">사이트에 대 한 새 보관 구성 설정 모음을 만들려면</span><span class="sxs-lookup"><span data-stu-id="07b1b-140">To create a new collection of archiving configuration settings for a site</span></span>

  - <span data-ttu-id="07b1b-141">다음 명령은 Redmond 사이트의 보관 구성 설정에 대 한 새 컬렉션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="07b1b-141">The following command creates a new collection of archiving configuration settings for the Redmond site:</span></span>
    
        New-CsArchivingConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-create-a-new-collection-of-archiving-configuration-settings-that-only-allow-im-archiving"></a><span data-ttu-id="07b1b-142">IM 보관만 허용 하는 새 보관 구성 설정 모음을 만들려면</span><span class="sxs-lookup"><span data-stu-id="07b1b-142">To create a new collection of archiving configuration settings that only allow IM archiving</span></span>

  - <span data-ttu-id="07b1b-143">앞의 명령에서 필수 Id 매개 변수 이외의 매개 변수를 지정 하지 않았으므로 새 구성 설정 모음에는 해당 속성에 대 한 기본값이 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="07b1b-143">Because no parameters (other than the mandatory Identity parameter) were specified in the preceding command, the new collection of configuration settings will use the default values for all its properties.</span></span> <span data-ttu-id="07b1b-144">다른 속성 값을 사용 하는 설정을 만들려면 간단히 적절 한 매개 변수와 매개 변수 값을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="07b1b-144">To create settings that use different property values, simply include the appropriate parameter and parameter value.</span></span> <span data-ttu-id="07b1b-145">예를 들어, 기본적으로 인스턴트 메시징 세션 보관을 허용 하는 보관 구성 설정 모음을 만들려면 다음과 같은 명령만 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="07b1b-145">For example, to create a collection of archiving configuration settings that, by default, allow archiving of instant messaging sessions, only use a command like this:</span></span>
    
        New-CsArchivingConfiguration -Identity "site:Redmond" -EnableArchiving "ImOnly"

</div>

<div>

## <a name="to-specify-multiple-property-values-when-creating-archiving-configuration-settings"></a><span data-ttu-id="07b1b-146">보관 구성 설정을 만들 때 여러 속성 값을 지정 하려면</span><span class="sxs-lookup"><span data-stu-id="07b1b-146">To specify multiple property values when creating archiving configuration settings</span></span>

  - <span data-ttu-id="07b1b-147">여러 매개 변수를 포함 하 여 여러 속성 값을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07b1b-147">Multiple property values can be modified by including multiple parameters.</span></span> <span data-ttu-id="07b1b-148">예를 들어이 명령은 메신저 대화 서비스를 보관 하기 위해 새로운 설정을 구성 하 고 보관 서비스의 인스턴트 메시지를 차단 합니다.</span><span class="sxs-lookup"><span data-stu-id="07b1b-148">For example, this command configures the new settings to archive instant messaging sessions and to block instant messaging of the archiving service is not available:</span></span>
    
        New-CsArchivingConfiguration -Identity "site:Redmond" -EnableArchiving "ImOnly" -BlockOnArchiveFailure $True

</div>

<span data-ttu-id="07b1b-149">자세한 내용은 [새 CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsArchivingConfiguration) cmdlet에 대 한 도움말 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="07b1b-149">For more information, see the help topic for the [New-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsArchivingConfiguration) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="07b1b-150">참고 항목</span><span class="sxs-lookup"><span data-stu-id="07b1b-150">See Also</span></span>


[<span data-ttu-id="07b1b-151">Lync Server 2013에서 보관 하는 방식</span><span class="sxs-lookup"><span data-stu-id="07b1b-151">How Archiving works in Lync Server 2013</span></span>](lync-server-2013-how-archiving-works.md)  


[<span data-ttu-id="07b1b-152">조직, 사이트 및 풀에 대 한 Lync Server 2013의 보관 구성 옵션 관리</span><span class="sxs-lookup"><span data-stu-id="07b1b-152">Managing Archiving configuration options in Lync Server 2013 for your organization, sites, and pools</span></span>](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

