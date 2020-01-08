---
title: 'Lync Server 2013: 보관이 실패 하는 경우 IM 및 웹 회의 세션을 차단 하거나 허용 하도록 중요 모드를 설정 또는 해제 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enabling or disabling critical mode to block or allow IM and web conferencing sessions if Archiving fails
ms:assetid: fafdcd2e-b778-4ed5-a25f-09208aa3b699
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182609(v=OCS.15)
ms:contentKeyID: 48185927
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9c690c235a3a753db8cc07cebbc8749a0d27c99f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983234"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-or-disabling-critical-mode-in-lync-server-2013-to-block-or-allow-im-and-web-conferencing-sessions-if-archiving-fails"></a><span data-ttu-id="fc1e6-102">보관에 실패 한 경우 Lync Server 2013에서 IM 및 웹 회의 세션을 차단 하거나 허용 하기 위해 중요 모드를 사용 하거나 사용 하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="fc1e6-102">Enabling or disabling critical mode in Lync Server 2013 to block or allow IM and web conferencing sessions if Archiving fails</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fc1e6-103">_**마지막으로 수정한 주제:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="fc1e6-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="fc1e6-104">Lync Server 2013 제어판에서 보관 구성을 사용 하 여 중요 모드를 사용 하거나 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc1e6-104">In Lync Server 2013 Control Panel, you use Archiving configurations to enable and disable critical mode.</span></span> <span data-ttu-id="fc1e6-105">여기에는 다음과 같은 보관 구성이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fc1e6-105">This includes the following Archiving configurations:</span></span>

  - <span data-ttu-id="fc1e6-106">Lync Server 2013을 배포할 때 기본적으로 만들어지는 전역 구성입니다.</span><span class="sxs-lookup"><span data-stu-id="fc1e6-106">A global configuration that is created by default when you deploy Lync Server 2013.</span></span>

  - <span data-ttu-id="fc1e6-107">특정 사이트 또는 풀에 대해 보관을 구현 하는 방법을 지정 하기 위해 만들고 사용할 수 있는 선택적 사이트 수준 및 풀 수준 구성입니다.</span><span class="sxs-lookup"><span data-stu-id="fc1e6-107">Optional site-level and pool-level configurations that you can create and use to specify how archiving is implemented for specific sites or pools.</span></span>

<span data-ttu-id="fc1e6-108">보관을 배포할 때 초기에 보관 구성을 설정 했지만 배포 후 구성을 변경, 추가 및 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc1e6-108">You initially set up Archiving configurations when you deploy Archiving, but you can change, add, and delete configurations after deployment.</span></span> <span data-ttu-id="fc1e6-109">사용자가 지정할 수 있는 옵션 및 보관 구성의 계층 구조를 비롯 하 여 보관 구성을 구현 하는 방법에 대 한 자세한 내용은 계획 문서, 배포 설명서 또는 운영 설명서의 [Lync Server 2013에서 보관을 작동 하는 방법을](lync-server-2013-how-archiving-works.md) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="fc1e6-109">For details about how Archiving configurations are implemented, including which options you can specify and the hierarchy of Archiving configurations, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="fc1e6-110">보관을 사용 하려면 보관 정책을 구성 하 여 Lync Server 2013에 있는 사용자에 대해 내부 통신, 외부 통신 또는 둘 다에 대해 보관을 사용할지 여부를 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc1e6-110">To use archiving, you must configure Archiving policies to specify whether to enable archiving for internal communications, for external communications, or for both for users homed on Lync Server 2013.</span></span> <span data-ttu-id="fc1e6-111">기본적으로 내부 또는 외부 통신에 대해 보관을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fc1e6-111">By default, archiving is not enabled for either internal or external communications.</span></span> <span data-ttu-id="fc1e6-112">모든 정책에서 보관을 사용 하도록 설정 하기 전에이 섹션에서 설명 하는 대로 배포에 적절 한 보관 구성을 지정 하 고, 선택적으로 특정 사이트 및 풀에 대해 해당 하는 경우를 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc1e6-112">Prior to enabling Archiving in any policies, you should specify the appropriate Archiving configurations for your deployment and, optionally, for specific sites and pools, as described in this section.</span></span> <span data-ttu-id="fc1e6-113">보관을 사용 하도록 설정 하는 방법에 대 한 자세한 내용은 배포 설명서의 <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Lync Server 2013에서 보관 정책 구성 및 할당</A> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="fc1e6-113">For details about enabling Archiving, see <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Configuring and assigning Archiving policies in Lync Server 2013</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="fc1e6-114">Exchange Server 통합을 사용 하 여 exchange 2013 서버에 보관 데이터와 파일을 저장 하 고 exchange 2013 서버에 모든 사용자가 있는 경우 보관을 배포 하는 것을 결정 한 경우에는 다음에서 SQL Server 데이터베이스 구성을 제거 해야 합니다. 토폴로지.</span><span class="sxs-lookup"><span data-stu-id="fc1e6-114">If you decide after you deploy Archiving that you want to use Exchange Server integration to store archiving data and files on Exchange 2013 servers and all your users are homed on your Exchange 2013 servers, you should remove the SQL Server database configuration from your topology.</span></span> <span data-ttu-id="fc1e6-115">이 작업을 수행 하려면 토폴로지 작성기를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc1e6-115">You must use Topology Builder to do this.</span></span> <span data-ttu-id="fc1e6-116">자세한 내용은 운영 설명서의 <A href="lync-server-2013-changing-archiving-database-options.md">Lync Server 2013에서 보관 데이터베이스 옵션 변경을</A> 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="fc1e6-116">For details, see <A href="lync-server-2013-changing-archiving-database-options.md">Changing Archiving database options in Lync Server 2013</A> in the Operations documentation.</span></span>



</div>

<div>

## <a name="to-enable-or-disable-blocking-of-im-and-web-conferencing-sessions-if-archiving-fails"></a><span data-ttu-id="fc1e6-117">보관이 실패 하는 경우 IM 및 웹 회의 세션 차단 사용 또는 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="fc1e6-117">To enable or disable blocking of IM and web conferencing sessions if archiving fails</span></span>

1.  <span data-ttu-id="fc1e6-118">CsArchivingAdministrator 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc1e6-118">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="fc1e6-119">브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="fc1e6-119">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="fc1e6-120">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="fc1e6-120">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="fc1e6-121">왼쪽 탐색 모음에서 **모니터링 및 보관**을 클릭 한 다음 **구성 보관**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc1e6-121">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>

4.  <span data-ttu-id="fc1e6-122">보관 구성 목록에서 적절 한 전역, 사이트 또는 풀 구성의 이름을 클릭 하 고 **편집**을 클릭 한 다음 **세부 정보 표시**를 클릭 하 고 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc1e6-122">Click the name of the appropriate global, site, or pool configuration in the list of archiving configurations, click **Edit**, click **Show details**, and then do the following:</span></span>

5.  <span data-ttu-id="fc1e6-123">오류가 발생할 때 보관이 작동 하는 방식을 설정 하려면 **IM (인스턴트 메시징) 또는 웹 회의 세션 (보관 실패 시) 차단** 확인란을 선택 하거나 선택을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc1e6-123">To set how archiving behaves when a failure occurs, select or clear the **Block instant messaging (IM) or web conferencing sessions if archiving fails** check box.</span></span>

6.  <span data-ttu-id="fc1e6-124">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="fc1e6-124">Click **Commit**.</span></span>

</div>

<div>

## <a name="enabling-and-disabling-critical-mode-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="fc1e6-125">Windows PowerShell Cmdlet을 사용 하 여 중요 모드 사용 및 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="fc1e6-125">Enabling and Disabling Critical Mode by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="fc1e6-126">**Set-CsArchivingConfiguration** cmdlet을 사용 하 여 중요 한 모드를 사용 하도록 설정 하거나 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc1e6-126">You can enable or disable critical mode using the **Set-CsArchivingConfiguration** cmdlet.</span></span> <span data-ttu-id="fc1e6-127">Lync Server 2013 관리 셸 또는 Windows PowerShell의 원격 세션에서이 cmdlet을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc1e6-127">You can run this cmdlet from either the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="fc1e6-128">원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="fc1e6-128">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-enable-critical-mode"></a><span data-ttu-id="fc1e6-129">중요 모드를 사용 하도록 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="fc1e6-129">To enable critical mode</span></span>

  - <span data-ttu-id="fc1e6-130">중요 모드를 사용 하도록 설정 하려면 BlockOnArchiveFailure 속성 값을 True ($True)로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc1e6-130">To enable critical mode, set the value of the BlockOnArchiveFailure property to True ($True).</span></span> <span data-ttu-id="fc1e6-131">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="fc1e6-131">For example:</span></span>
    
        Set-CsArchivingConfiguration -Identity "site:Redmond" -BlockOnArchiveFailure $True

</div>

<div>

## <a name="to-disable-critical-mode"></a><span data-ttu-id="fc1e6-132">중요 모드를 비활성화 하려면</span><span class="sxs-lookup"><span data-stu-id="fc1e6-132">To disable critical mode</span></span>

  - <span data-ttu-id="fc1e6-133">중요 모드를 사용 하지 않도록 설정 하려면 BlockOnArchiveFailure 속성의 값을 False ($False)로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc1e6-133">To disable critical mode, set the value of the BlockOnArchiveFailure property to False ($False).</span></span> <span data-ttu-id="fc1e6-134">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="fc1e6-134">For example:</span></span>
    
        Set-CsArchivingConfiguration -Identity "site:Redmond" -BlockOnArchiveFailure $False

</div>

<span data-ttu-id="fc1e6-135">자세한 내용은 [Set-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsArchivingConfiguration) cmdlet에 대 한 도움말 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="fc1e6-135">For more information, see the Help topic for the [Set-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsArchivingConfiguration) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="fc1e6-136">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fc1e6-136">See Also</span></span>


[<span data-ttu-id="fc1e6-137">Lync Server 2013에서 데이터베이스 보관 옵션 변경</span><span class="sxs-lookup"><span data-stu-id="fc1e6-137">Changing Archiving database options in Lync Server 2013</span></span>](lync-server-2013-changing-archiving-database-options.md)  


[<span data-ttu-id="fc1e6-138">Lync Server 2013에서 보관 하는 방식</span><span class="sxs-lookup"><span data-stu-id="fc1e6-138">How Archiving works in Lync Server 2013</span></span>](lync-server-2013-how-archiving-works.md)  


[<span data-ttu-id="fc1e6-139">조직, 사이트 및 풀에 대 한 Lync Server 2013의 보관 구성 옵션 관리</span><span class="sxs-lookup"><span data-stu-id="fc1e6-139">Managing Archiving configuration options in Lync Server 2013 for your organization, sites, and pools</span></span>](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

