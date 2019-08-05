---
title: 사이트에 대 한 통화 허용 제어 관리
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 네트워크 사이트는 호출 허용 제어 (CAC), E9-1-1, 미디어 바이패스 배포의 각 네트워크 영역 내에 있는 사무실 또는 위치입니다.
ms.openlocfilehash: a90781eae38d92d560dd1bf34db3b6918e8aeaf5
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36188583"
---
# <a name="managing-call-admission-control-for-sites-in-skype-for-business-server"></a><span data-ttu-id="96b32-103">비즈니스용 Skype 서버에서 사이트에 대 한 통화 허용 제어 관리</span><span class="sxs-lookup"><span data-stu-id="96b32-103">Managing call admission control for sites in Skype for Business Server</span></span>

<span data-ttu-id="96b32-104">네트워크 사이트는 호출 허용 제어 (CAC), E9-1-1, 미디어 바이패스 배포의 각 네트워크 영역 내에 있는 사무실 또는 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="96b32-104">Network sites are the offices or locations within each network region of call admission control (CAC), E9-1-1, and media bypass deployments.</span></span> <span data-ttu-id="96b32-105">이 문서의 절차를 사용 하 여 네트워크 사이트에 대 한 통화 허용 제어를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="96b32-105">Use the procedures in this article to configure call admission control for network sites.</span></span>

## <a name="configure-network-site-links"></a><span data-ttu-id="96b32-106">네트워크 사이트 링크 구성</span><span class="sxs-lookup"><span data-stu-id="96b32-106">Configure network site links</span></span>

<span data-ttu-id="96b32-107">CAC (call 허용 제어) 구성 내에서 직접 연결 된 사이트 간의 대역폭 제한을 정의 하는 네트워크 간 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96b32-107">Within a call admission control (CAC) configuration, you can create network inter-site policies that define bandwidth limitations between sites that are directly linked.</span></span> <span data-ttu-id="96b32-108">네트워크 사이트에서 직접 링크를 공유 하는 경우 오디오 및 비디오 연결에 대 한 대역폭 제한이 해당 두 사이트 간에 정의 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96b32-108">When network sites share a direct link, bandwidth limitations for audio and video connections can be defined between those two sites.</span></span> <span data-ttu-id="96b32-109">비즈니스용 Skype Server 제어판을 사용 하 여 네트워크 사이트 정책을 구성할 수는 없습니다 .이 작업은 비즈니스용 Skype 서버 관리 셸에서 cmdlet을 사용 하는 경우에만 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="96b32-109">You cannot use the Skype for Business Server Control Panel to configure network site policies, this can be done only by using cmdlets from the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="96b32-110">비즈니스용 Skype 서버 관리 셸에서 네트워크 사이트 링크 (사이트 간 정책 라고도 함)를 만들고, 수정 하 고, 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96b32-110">You can create, modify, and remove a network site link (also known as a network inter-site policy) from the Skype for Business Server Management Shell.</span></span>

### <a name="to-create-a-network-site-link"></a><span data-ttu-id="96b32-111">네트워크 사이트 링크를 만들려면</span><span class="sxs-lookup"><span data-stu-id="96b32-111">To create a network site link</span></span>

1.  <span data-ttu-id="96b32-112">비즈니스용 Skype 서버 관리 셸이 설치 되어 있는 컴퓨터에 RTCUniversalServerAdmins 그룹의 구성원 또는 필요한 사용자 권한을 사용 하 여 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="96b32-112">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights.</span></span>

2.  <span data-ttu-id="96b32-113">비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **비즈니스용 skype 서버**를 차례로 클릭 한 다음 비즈니스용 **skype server management shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="96b32-113">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business Server**, and then click **Skype for Business Server Management Shell**.</span></span>

3.  <span data-ttu-id="96b32-114">명령 프롬프트에서 다음 명령을 입력 하 고 구성에 유효한 값으로 대체 합니다.</span><span class="sxs-lookup"><span data-stu-id="96b32-114">From the command prompt, type the following command, substituting values that are valid for your configuration:</span></span>
    
        New-CsNetworkInterSitePolicy -Identity Reno_Portland -NetworkSiteID1 Reno -NetworkSiteID2 Portland -BWPolicyProfileID LowBWLimits
    
    <span data-ttu-id="96b32-115">이 예제에서는 Reno 및 포틀랜드 네트워크 사이트 간의 대역폭\_제한을 설정 하는 Reno 포틀랜드 이라는 새 네트워크 사이트 링크를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="96b32-115">This example creates a new network site link named Reno\_Portland that sets bandwidth limitations between the Reno and Portland network sites.</span></span> <span data-ttu-id="96b32-116">네트워크 사이트 및 대역폭 정책 프로필은이 명령을 실행 하기 전에 이미 존재 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="96b32-116">The network sites and the bandwidth policy profile must already exist before running this command.</span></span>

<span data-ttu-id="96b32-117">자세한 매개 변수 설명은 [New-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="96b32-117">For detailed parameter descriptions, see [New-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy).</span></span> <span data-ttu-id="96b32-118">네트워크 사이트 링크에 적용할 수 있는 대역폭 정책 프로필 목록을 검색 하려면 **CsNetworkBandwidthPolicyProfile** cmdlet을 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="96b32-118">To retrieve a list of bandwidth policy profiles that can be applied to the network site link, call the **Get-CsNetworkBandwidthPolicyProfile** cmdlet.</span></span> <span data-ttu-id="96b32-119">자세한 내용은 [Get-help CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="96b32-119">For details, see [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile).</span></span>

### <a name="to-modify-a-network-site-link"></a><span data-ttu-id="96b32-120">네트워크 사이트 링크를 수정 하려면</span><span class="sxs-lookup"><span data-stu-id="96b32-120">To modify a network site link</span></span>

1.  <span data-ttu-id="96b32-121">비즈니스용 Skype 서버 관리 셸이 설치 되어 있는 컴퓨터에 RTCUniversalServerAdmins 그룹의 구성원 또는 필요한 사용자 권한을 사용 하 여 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="96b32-121">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights.</span></span>

2.  <span data-ttu-id="96b32-122">비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **비즈니스용 skype 서버**를 차례로 클릭 한 다음 비즈니스용 **skype server management shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="96b32-122">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business Server**, and then click **Skype for Business Server Management Shell**.</span></span>

3.  <span data-ttu-id="96b32-123">**Set-CsNetworkInterSitePolicy** cmdlet을 사용 하 여 지정 된 네트워크 사이트 링크의 속성을 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="96b32-123">Use the **Set-CsNetworkInterSitePolicy** cmdlet to modify the properties of a given network site link.</span></span> <span data-ttu-id="96b32-124">(또는 둘 다) 또는 연결 된 사이트를 수정할 수 있으며 링크와 연결 된 대역폭 정책 프로필을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96b32-124">You can modify either (or both) or the connected sites, and you can modify the bandwidth policy profile associated with the link.</span></span> <span data-ttu-id="96b32-125">다음은 Reno\_포틀랜드 라는 사이트 링크의 대역폭 정책 프로필을 수정 하는 예입니다.</span><span class="sxs-lookup"><span data-stu-id="96b32-125">Here is an example of modifying the bandwidth policy profile of a site link named Reno\_Portland:</span></span>
    
        Set-CsNetworkInterSitePolicy -Identity Reno_Portland -BWPolicyProfileID HighBWLimits

<span data-ttu-id="96b32-126">자세한 매개 변수 설명은 [Set-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="96b32-126">For detailed parameter descriptions, see [Set-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy).</span></span>


### <a name="to-delete-a-network-site-link"></a><span data-ttu-id="96b32-127">네트워크 사이트 링크를 삭제 하려면</span><span class="sxs-lookup"><span data-stu-id="96b32-127">To delete a network site link</span></span>

1.  <span data-ttu-id="96b32-128">비즈니스용 Skype 서버 관리 셸이 설치 되어 있는 컴퓨터에 RTCUniversalServerAdmins 그룹의 구성원 또는 필요한 사용자 권한을 사용 하 여 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="96b32-128">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights.</span></span>

2.  <span data-ttu-id="96b32-129">비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **비즈니스용 skype 서버**를 차례로 클릭 한 다음 비즈니스용 **skype server management shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="96b32-129">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business Server**, and then click **Skype for Business Server Management Shell**.</span></span>

3.  <span data-ttu-id="96b32-130">네트워크 사이트 링크를 제거 하려면 **CsNetworkInterSitePolicy** cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="96b32-130">Use the **Remove-CsNetworkInterSitePolicy** cmdlet to remove a network site link.</span></span> <span data-ttu-id="96b32-131">다음 예에서는 Reno\_포틀랜드 네트워크 사이트 링크를 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="96b32-131">The following example deletes the Reno\_Portland network site link:</span></span>
    
        Remove-CsNetworkInterSitePolicy -Identity Reno_Portland

<span data-ttu-id="96b32-132">자세한 매개 변수 설명은 [제거-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="96b32-132">For detailed parameter descriptions, see [Remove-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy).</span></span>


## <a name="view-network-site-information"></a><span data-ttu-id="96b32-133">네트워크 사이트 정보 보기</span><span class="sxs-lookup"><span data-stu-id="96b32-133">View network site information</span></span>

<span data-ttu-id="96b32-134">네트워크 사이트는 CAC (통화 허용 제어) 또는 향상 된 9-1-1 배포의 각 영역 내에서 구성 된 사무실 또는 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="96b32-134">Network sites are the offices or locations configured within each region of a call admission control (CAC) or Enhanced 9-1-1 deployment.</span></span> <span data-ttu-id="96b32-135">비즈니스용 Skype Server 제어판 또는 비즈니스용 Skype 서버 관리 셸에서는 네트워크 사이트 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96b32-135">You can view network site information in either the Skype for Business Server Control Panel or the Skype for Business Server Management Shell.</span></span> 

### <a name="to-view-network-site-information-in-skype-for-business-server-control-panel"></a><span data-ttu-id="96b32-136">비즈니스용 Skype Server 제어판에서 네트워크 사이트 정보를 보려면</span><span class="sxs-lookup"><span data-stu-id="96b32-136">To view network site information in Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="96b32-137">RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsAdministrator 역할에 할당 된 경우 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="96b32-137">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="96b32-138">브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="96b32-138">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="96b32-139">왼쪽 탐색 모음에서 **네트워크 구성을**클릭 한 다음 **사이트**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="96b32-139">In the left navigation bar, click **Network Configuration**, and then click **Site**.</span></span>

4.  <span data-ttu-id="96b32-140">**사이트** 페이지에서 보려는 사이트를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="96b32-140">On the **Site** page, click the site that you want to view.</span></span>
 
    > [!NOTE]  
    > <span data-ttu-id="96b32-141">한 번에 한 사이트의 정보만 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96b32-141">You can only view information for one site at a time.</span></span>

5.  <span data-ttu-id="96b32-142">**편집** 메뉴에서 **세부 정보 표시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="96b32-142">On the **Edit** menu, click **Show details**.</span></span>


### <a name="viewing-network-site-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="96b32-143">Windows PowerShell cmdlet을 사용 하 여 네트워크 사이트 정보 보기</span><span class="sxs-lookup"><span data-stu-id="96b32-143">Viewing network site information by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="96b32-144">Windows PowerShell 및 Get-CsNetworkSite cmdlet을 사용 하 여 네트워크 사이트 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96b32-144">You can view network site information by using Windows PowerShell and the Get-CsNetworkSite cmdlet.</span></span> <span data-ttu-id="96b32-145">이 cmdlet은 비즈니스용 Skype 서버 관리 셸에서 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96b32-145">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

### <a name="to-view-network-site-information"></a><span data-ttu-id="96b32-146">네트워크 사이트 정보를 보려면</span><span class="sxs-lookup"><span data-stu-id="96b32-146">To view network site information</span></span>

  - <span data-ttu-id="96b32-147">모든 네트워크 사이트에 대 한 정보를 보려면 비즈니스용 Skype 서버 관리 셸에서 다음 명령을 입력 한 다음 enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="96b32-147">To view information about all your network sites, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsNetworkSite
    
    <span data-ttu-id="96b32-148">이는 다음과 같은 정보를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="96b32-148">That will return information similar to this:</span></span>
    
        Identity          : Redmond
        NetworkSiteID     : Redmond
        Description       :
        NetworkRegionID   : Pacific Northwest
        BypassID          : 3b232b84-2c1d-4da2-8181-e9330bafebe9
        BWPolicyProfileID :
        LocationPolicy    :

<span data-ttu-id="96b32-149">자세한 내용은 [Get CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite) cmdlet에 대 한 도움말 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="96b32-149">For more information, see the help topic for the [Get-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite) cmdlet.</span></span>


## <a name="create-or-modify-network-sites"></a><span data-ttu-id="96b32-150">네트워크 사이트 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="96b32-150">Create or modify network sites</span></span> 

<span data-ttu-id="96b32-151">네트워크 사이트는 CAC (통화 허용 제어) 또는 향상 된 9-1-1 배포의 각 영역 내에서 구성 된 사무실 또는 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="96b32-151">Network sites are the offices or locations configured within each region of a call admission control (CAC) or Enhanced 9-1-1 deployment.</span></span> <span data-ttu-id="96b32-152">비즈니스용 Skype Server 제어판을 사용 하 여 사이트를 구성 하 고 지역을 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96b32-152">You can use the Skype for Business Server Control Panel to configure sites and associate them with regions.</span></span> <span data-ttu-id="96b32-153">예를 들어 북미, 레드먼드, Vancouver와 같은 네트워크 사이트에 북아메리카 네트워크 지역이 연결 되어 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96b32-153">For example, a network region for North America might be associated with networks sites such as Chicago, Redmond, and Vancouver.</span></span> <span data-ttu-id="96b32-154">사이트에 대 한 모든 사이트에 대해 CAC 네트워크 사이트를 만들어야 하는 경우에도 해당 사이트가 대역폭 제한 없이 구성 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="96b32-154">A CAC network site must be created for every site within an organization, even if that site has no bandwidth limitations.</span></span> <span data-ttu-id="96b32-155">비즈니스용 Skype Server 제어판에서 네트워크 사이트를 만들고, 수정 하 고, 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96b32-155">From the Skype for Business Server Control Panel you can create, modify, and delete network sites.</span></span> <span data-ttu-id="96b32-156">네트워크 사이트를 만들거나 수정 하려면 다음 절차를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="96b32-156">Use the following procedures to create or modify a network site.</span></span> 

### <a name="to-create-a-network-site"></a><span data-ttu-id="96b32-157">네트워크 사이트를 만들려면</span><span class="sxs-lookup"><span data-stu-id="96b32-157">To create a network site</span></span>

1.  <span data-ttu-id="96b32-158">RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsAdministrator 역할에 할당 된 경우 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="96b32-158">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="96b32-159">브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="96b32-159">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="96b32-160">왼쪽 탐색 모음에서 **네트워크 구성을**클릭 한 다음 **사이트**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="96b32-160">In the left navigation bar, click **Network Configuration**, and then click **Site**.</span></span>

4.  <span data-ttu-id="96b32-161">**사이트** 페이지에서 **새로 만들기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="96b32-161">On the **Site** page, click **New**.</span></span>

5.  <span data-ttu-id="96b32-162">**새 사이트**의 **name (이름** ) 필드에이 사이트의 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="96b32-162">In **New Site**, type a name for this site in the **Name** field.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="96b32-163">사이트 이름은 비즈니스용 Skype 서버 배포 내에서 고유 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="96b32-163">Site names must be unique within the Skype for Business Server deployment.</span></span>

6.  <span data-ttu-id="96b32-164">**지역** 드롭다운 목록에서이 사이트와 연결할 네트워크 지역을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="96b32-164">In the **Region** drop-down list, select a network region to associate with this site.</span></span>

7.  <span data-ttu-id="96b32-165">) 이 사이트에 대 한 오디오 또는 비디오 통화에 대 한 대역폭 제한을 설정 하려면 대역폭 **정책** 드롭다운 목록에서 적절 한 설정을 사용 하 여 대역폭 정책 프로필을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="96b32-165">(Optional) If you want to place bandwidth limitations on audio or video calls to this site, select the bandwidth policy profile with the appropriate settings from the **Bandwidth policy** drop-down list.</span></span>
 
    > [!NOTE]  
    > <span data-ttu-id="96b32-166">**네트워크 구성** 그룹의 **정책 Profil** 페이지에서 사용 가능한 대역폭 정책 프로필의 세부 정보를 보거나 새 대역폭 정책 프로필을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96b32-166">You can view the details of the available bandwidth policy profiles, or create a new bandwidth policy profile, on the **Policy Profil** page of the **Network Configuration** group.</span></span> <span data-ttu-id="96b32-167">자세한 내용은 [네트워크 대역폭 정책 프로필 관리](managing-network-bandwidth-policy-profiles.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="96b32-167">For details, see [Managing network bandwidth policy profiles](managing-network-bandwidth-policy-profiles.md).</span></span>

8.  <span data-ttu-id="96b32-168">) 이 사이트에 대 한 위치 설정을 제공 하려면 **위치 정책** 드롭다운 목록에서 위치 정책을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="96b32-168">(Optional) If you want to provide location settings for this site, select a location policy from the **Location policy** drop-down list.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="96b32-169">위치 정책은 사이트에 특정 향상 된 9-1-1 (E9-1-1) 및 클라이언트 위치 설정을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="96b32-169">The location policy assigns specific Enhanced 9-1-1 (E9-1-1) and client location settings to the site.</span></span> <span data-ttu-id="96b32-170">**네트워크 구성** 그룹의 **위치 정책** 페이지에서 사용 가능한 위치 정책의 세부 정보를 보거나 새 위치 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96b32-170">You can view the details of the available location policies, or create a new location policy, from the **Location Policy** page of the **Network Configuration** group.</span></span> 

9.  <span data-ttu-id="96b32-171">) 이름 만으로 표현할 수 없는이 사이트에 대 한 자세한 정보를 제공 하려면 **설명** 필드에 값을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="96b32-171">(Optional) Type a value in the **Description** field to provide more information about this site that cannot be expressed by the name alone.</span></span>

10. <span data-ttu-id="96b32-172">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="96b32-172">Click **Commit**.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="96b32-173">새 네트워크 사이트를 만들 때 **연결 된 서브넷** 테이블을 사용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="96b32-173">You do not use the **Associated Subnets** table when you create a new network site.</span></span> <span data-ttu-id="96b32-174">서브넷을 만들거나 수정할 때 서브넷을 사이트와 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="96b32-174">You associate a subnet with a site when you create or modify the subnet.</span></span> <span data-ttu-id="96b32-175">자세한 내용은 [네트워크 서브넷 관리](managing-network-subnets.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="96b32-175">For details, see [Managing network subnets](managing-network-subnets.md).</span></span>

### <a name="to-modify-a-network-site"></a><span data-ttu-id="96b32-176">네트워크 사이트를 수정 하려면</span><span class="sxs-lookup"><span data-stu-id="96b32-176">To modify a network site</span></span>

1.  <span data-ttu-id="96b32-177">RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsAdministrator 역할에 할당 된 경우 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="96b32-177">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="96b32-178">브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="96b32-178">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="96b32-179">왼쪽 탐색 모음에서 **네트워크 구성을**클릭 한 다음 **사이트**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="96b32-179">In the left navigation bar, click **Network Configuration**, and then click **Site**.</span></span>

4.  <span data-ttu-id="96b32-180">**사이트** 페이지에서 수정 하려는 사이트를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="96b32-180">On the **Site** page, click the site that you want to modify.</span></span>

5.  <span data-ttu-id="96b32-181">**편집** 메뉴에서 **세부 정보 표시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="96b32-181">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="96b32-182">**사이트 편집** 페이지에서 설명, 지역, 대역폭 정책 프로필, 사이트와 연결 된 위치 정책을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96b32-182">On the **Edit Site** page, you can modify the description, region, bandwidth policy profile, and location policy associated with the site.</span></span> <span data-ttu-id="96b32-183">자세한 내용은 위의 [네트워크 사이트 만들기를](#to-create-a-network-site) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="96b32-183">For details, see [To create a network site](#to-create-a-network-site) above.</span></span>

7.  <span data-ttu-id="96b32-184">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="96b32-184">Click **Commit**.</span></span>

<span data-ttu-id="96b32-185">이 페이지에서는 **연결 된 서브넷** 테이블을 수정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="96b32-185">You cannot modify the **Associated Subnets** table on this page.</span></span> <span data-ttu-id="96b32-186">사이트 설정을 수정할 때 어떤 서브넷에 영향을 미치는지 알 수 있도록 관련 서브넷 목록이 참조용으로 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="96b32-186">The list of associated subnets is provided for reference so that you are aware of what subnets will be affected when you modify the site settings.</span></span>


## <a name="delete-an-existing-network-site"></a><span data-ttu-id="96b32-187">기존 네트워크 사이트 삭제</span><span class="sxs-lookup"><span data-stu-id="96b32-187">Delete an existing network site</span></span>

<span data-ttu-id="96b32-188">네트워크 사이트는 CAC (통화 허용 제어) 또는 향상 된 9-1-1 배포의 각 영역 내에서 구성 된 사무실 또는 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="96b32-188">Network sites are the offices or locations configured within each region of a call admission control (CAC) or Enhanced 9-1-1 deployment.</span></span> <span data-ttu-id="96b32-189">비즈니스용 Skype Server 제어판을 사용 하 여 사이트를 구성 하 고 지역을 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96b32-189">You can use the Skype for Business Server Control Panel to configure sites and associate them with regions.</span></span> <span data-ttu-id="96b32-190">예를 들어 북미, 레드먼드, Vancouver와 같은 네트워크 사이트에 북아메리카 네트워크 지역이 연결 되어 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96b32-190">For example, a network region for North America might be associated with networks sites such as Chicago, Redmond, and Vancouver.</span></span> <span data-ttu-id="96b32-191">사이트에 대 한 모든 사이트에 대해 CAC 네트워크 사이트를 만들어야 하는 경우에도 해당 사이트가 대역폭 제한 없이 구성 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="96b32-191">A CAC network site must be created for every site within an organization, even if that site has no bandwidth limitations.</span></span> <span data-ttu-id="96b32-192">비즈니스용 Skype Server 제어판에서 네트워크 사이트를 만들고, 수정 하 고, 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96b32-192">From the Skype for Business Server Control Panel you can create, modify, and delete network sites.</span></span> <span data-ttu-id="96b32-193">다음 절차를 사용 하 여 기존 네트워크 사이트를 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="96b32-193">Use the following procedure to delete an existing network site.</span></span> <span data-ttu-id="96b32-194">네트워크 사이트를 만들거나 수정 하는 방법에 대 한 자세한 내용은 [사이트에 대 한 통화 허용 제어 관리](managing-call-admission-control-for-sites.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="96b32-194">For details about creating or modifying network sites, see [Managing call admission control for sites](managing-call-admission-control-for-sites.md).</span></span>


### <a name="to-delete-a-network-site"></a><span data-ttu-id="96b32-195">네트워크 사이트를 삭제 하려면</span><span class="sxs-lookup"><span data-stu-id="96b32-195">To delete a network site</span></span>

1.  <span data-ttu-id="96b32-196">RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsAdministrator 역할에 할당 된 경우 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="96b32-196">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="96b32-197">브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="96b32-197">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="96b32-198">왼쪽 탐색 모음에서 **네트워크 구성을**클릭 한 다음 **사이트**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="96b32-198">In the left navigation bar, click **Network Configuration**, and then click **Site**.</span></span>

4.  <span data-ttu-id="96b32-199">**사이트** 페이지에서 삭제 하려는 사이트를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="96b32-199">On the **Site** page, click the site that you want to delete.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="96b32-200">한 번에 여러 사이트를 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96b32-200">You can delete more than one site at a time.</span></span> <span data-ttu-id="96b32-201">이 작업을 수행 하려면 ctrl 키를 누른 채 여러 사이트를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="96b32-201">To do this, press CTRL and select multiple sites while holding down the CTRL key.</span></span> <span data-ttu-id="96b32-202">또는 모든 사이트를 선택 하려면 **편집** 메뉴에서 **모두 선택을** 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="96b32-202">Or, to select all sites, click **Select all** on the **Edit** menu.</span></span>

5.  <span data-ttu-id="96b32-203">**편집** 메뉴에서 **삭제**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="96b32-203">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="96b32-204">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="96b32-204">Click **OK**.</span></span>
    

    > [!WARNING]  
    > <span data-ttu-id="96b32-205">네트워크 서브넷과 연결 된 네트워크 사이트는 제거할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="96b32-205">You cannot remove a network site if it is associated with a network subnet.</span></span> <span data-ttu-id="96b32-206">서브넷과 연결 된 사이트를 제거 하려고 하면 오류 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="96b32-206">If you attempt to remove a site associated with a subnet you will receive an error message.</span></span> <span data-ttu-id="96b32-207">사이트가 서브넷과 연결 되어 있는지 확인 하려면 사이트를 클릭 한 다음 **편집** 메뉴에서 **자세한 정보 표시** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="96b32-207">To see if a site is associated with any subnets, click the site and then click **Show details** on the **Edit** menu.</span></span>


## <a name="see-also"></a><span data-ttu-id="96b32-208">참고 항목</span><span class="sxs-lookup"><span data-stu-id="96b32-208">See Also</span></span>


[<span data-ttu-id="96b32-209">새로운 CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="96b32-209">New-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy) 
 
[<span data-ttu-id="96b32-210">Set-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="96b32-210">Set-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy)  

[<span data-ttu-id="96b32-211">제거-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="96b32-211">Remove-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy)  

[<span data-ttu-id="96b32-212">Get-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="96b32-212">Get-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterSitePolicy)  

[<span data-ttu-id="96b32-213">Get-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="96b32-213">Get-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)  

[<span data-ttu-id="96b32-214">새-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="96b32-214">New-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSite)

[<span data-ttu-id="96b32-215">집합-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="96b32-215">Set-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSite)

[<span data-ttu-id="96b32-216">CsNetworkSite 사이트 제거</span><span class="sxs-lookup"><span data-stu-id="96b32-216">Remove-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSite)  

[<span data-ttu-id="96b32-217">Get-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="96b32-217">Get-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite)  
