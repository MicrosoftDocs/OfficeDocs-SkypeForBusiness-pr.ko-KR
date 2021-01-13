---
title: 사이트에 대한 통화 제어 관리
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 네트워크 사이트는 각 네트워크 지역(CAC), E9-1-1 및 미디어 우회 배포 내의 사무실 또는 위치입니다.
ms.openlocfilehash: dbe02c78c40cab48a79d7c63d3c6239b4ae59458
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816458"
---
# <a name="managing-call-admission-control-for-sites-in-skype-for-business-server"></a><span data-ttu-id="de5ad-103">비즈니스용 Skype에서 사이트에 대한 통화 허용 컨트롤 관리</span><span class="sxs-lookup"><span data-stu-id="de5ad-103">Managing call admission control for sites in Skype for Business Server</span></span>

<span data-ttu-id="de5ad-104">네트워크 사이트는 각 네트워크 지역(CAC), E9-1-1 및 미디어 우회 배포 내의 사무실 또는 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="de5ad-104">Network sites are the offices or locations within each network region of call admission control (CAC), E9-1-1, and media bypass deployments.</span></span> <span data-ttu-id="de5ad-105">이 문서의 절차에 따라 네트워크 사이트에 대한 통화 액세스 제어를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="de5ad-105">Use the procedures in this article to configure call admission control for network sites.</span></span>

## <a name="configure-network-site-links"></a><span data-ttu-id="de5ad-106">네트워크 사이트 링크 구성</span><span class="sxs-lookup"><span data-stu-id="de5ad-106">Configure network site links</span></span>

<span data-ttu-id="de5ad-107">CAC(통화 허용 제어) 구성 내에서 직접 연결된 사이트 간의 대역폭 제한을 정의하는 네트워크 사이트 간 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de5ad-107">Within a call admission control (CAC) configuration, you can create network inter-site policies that define bandwidth limitations between sites that are directly linked.</span></span> <span data-ttu-id="de5ad-108">네트워크 사이트에서 직접 링크를 공유하는 경우 이 두 사이트 간에 오디오 및 비디오 연결에 대한 대역폭 제한이 정의될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de5ad-108">When network sites share a direct link, bandwidth limitations for audio and video connections can be defined between those two sites.</span></span> <span data-ttu-id="de5ad-109">비즈니스용 Skype 서버 제어판을 사용하여 네트워크 사이트 정책을 구성할 수는 없습니다. 이 수행은 비즈니스용 Skype 서버 관리 셸의 cmdlet을 사용만 수행하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="de5ad-109">You cannot use the Skype for Business Server Control Panel to configure network site policies, this can be done only by using cmdlets from the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="de5ad-110">비즈니스용 Skype 서버 관리 셸에서 네트워크 사이트 링크(네트워크 사이트 간 정책)를 만들고 수정하고 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de5ad-110">You can create, modify, and remove a network site link (also known as a network inter-site policy) from the Skype for Business Server Management Shell.</span></span>

### <a name="to-create-a-network-site-link"></a><span data-ttu-id="de5ad-111">네트워크 사이트 링크를 만들려면</span><span class="sxs-lookup"><span data-stu-id="de5ad-111">To create a network site link</span></span>

1.  <span data-ttu-id="de5ad-112">비즈니스용 Skype 서버 관리 셸이 RTCUniversalServerAdmins 그룹의 구성원 또는 필요한 사용자 권한으로 설치된 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="de5ad-112">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights.</span></span>

2.  <span data-ttu-id="de5ad-113">비즈니스용 Skype 서버 관리 셸 시작: **시작,** 모든 **프로그램,** 비즈니스용 **Skype 서버** 및 비즈니스용 Skype 서버 관리 셸을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="de5ad-113">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business Server**, and then click **Skype for Business Server Management Shell**.</span></span>

3.  <span data-ttu-id="de5ad-114">명령 프롬프트에서 다음 명령을 입력하여 구성에 대해 올바른 값으로 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="de5ad-114">From the command prompt, type the following command, substituting values that are valid for your configuration:</span></span>
    
        New-CsNetworkInterSitePolicy -Identity Reno_Portland -NetworkSiteID1 Reno -NetworkSiteID2 Portland -BWPolicyProfileID LowBWLimits
    
    <span data-ttu-id="de5ad-115">이 예제에서는 Reno와 Portland 네트워크 사이트 간의 대역폭 제한을 설정하는 Reno Portland라는 새 네트워크 사이트 링크를 \_ 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="de5ad-115">This example creates a new network site link named Reno\_Portland that sets bandwidth limitations between the Reno and Portland network sites.</span></span> <span data-ttu-id="de5ad-116">네트워크 사이트 및 대역폭 정책 프로필은 이 명령을 실행하기 전에 이미 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="de5ad-116">The network sites and the bandwidth policy profile must already exist before running this command.</span></span>

<span data-ttu-id="de5ad-117">매개 변수에 대한 자세한 내용은 [New-CsNetworkInterSitePolicy를 참조하세요.](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy)</span><span class="sxs-lookup"><span data-stu-id="de5ad-117">For detailed parameter descriptions, see [New-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy).</span></span> <span data-ttu-id="de5ad-118">네트워크 사이트 링크에 적용할 수 있는 대역폭 정책 프로필 목록을 검색하려면 **Get-CsNetworkBandwidthPolicyProfile** cmdlet을 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="de5ad-118">To retrieve a list of bandwidth policy profiles that can be applied to the network site link, call the **Get-CsNetworkBandwidthPolicyProfile** cmdlet.</span></span> <span data-ttu-id="de5ad-119">자세한 내용은 [Get-CsNetworkBandwidthPolicyProfile을 참조합니다.](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)</span><span class="sxs-lookup"><span data-stu-id="de5ad-119">For details, see [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile).</span></span>

### <a name="to-modify-a-network-site-link"></a><span data-ttu-id="de5ad-120">네트워크 사이트 링크를 수정하려면</span><span class="sxs-lookup"><span data-stu-id="de5ad-120">To modify a network site link</span></span>

1.  <span data-ttu-id="de5ad-121">비즈니스용 Skype 서버 관리 셸이 RTCUniversalServerAdmins 그룹의 구성원 또는 필요한 사용자 권한으로 설치된 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="de5ad-121">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights.</span></span>

2.  <span data-ttu-id="de5ad-122">비즈니스용 Skype 서버 관리 셸 시작: **시작,** 모든 **프로그램,** 비즈니스용 **Skype 서버,** 비즈니스용 Skype 서버 관리 셸을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="de5ad-122">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business Server**, and then click **Skype for Business Server Management Shell**.</span></span>

3.  <span data-ttu-id="de5ad-123">**Set-CsNetworkInterSitePolicy** cmdlet을 사용하여 해당 네트워크 사이트 링크의 속성을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="de5ad-123">Use the **Set-CsNetworkInterSitePolicy** cmdlet to modify the properties of a given network site link.</span></span> <span data-ttu-id="de5ad-124">연결된 사이트 중 하나(또는 둘 다)를 수정할 수 있으며 링크와 연결된 대역폭 정책 프로필을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de5ad-124">You can modify either (or both) or the connected sites, and you can modify the bandwidth policy profile associated with the link.</span></span> <span data-ttu-id="de5ad-125">다음은 Reno Portland라는 사이트 링크의 대역폭 정책 프로필을 수정하는 \_ 예입니다.</span><span class="sxs-lookup"><span data-stu-id="de5ad-125">Here is an example of modifying the bandwidth policy profile of a site link named Reno\_Portland:</span></span>
    
        Set-CsNetworkInterSitePolicy -Identity Reno_Portland -BWPolicyProfileID HighBWLimits

<span data-ttu-id="de5ad-126">자세한 매개 변수 설명은 [Set-CsNetworkInterSitePolicy를 참조하세요.](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy)</span><span class="sxs-lookup"><span data-stu-id="de5ad-126">For detailed parameter descriptions, see [Set-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy).</span></span>


### <a name="to-delete-a-network-site-link"></a><span data-ttu-id="de5ad-127">네트워크 사이트 링크를 삭제하려면</span><span class="sxs-lookup"><span data-stu-id="de5ad-127">To delete a network site link</span></span>

1.  <span data-ttu-id="de5ad-128">비즈니스용 Skype 서버 관리 셸이 RTCUniversalServerAdmins 그룹의 구성원 또는 필요한 사용자 권한으로 설치된 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="de5ad-128">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights.</span></span>

2.  <span data-ttu-id="de5ad-129">비즈니스용 Skype 서버 관리 셸 시작: **시작,** 모든 **프로그램,** 비즈니스용 **Skype 서버** 및 비즈니스용 Skype 서버 관리 셸을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="de5ad-129">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business Server**, and then click **Skype for Business Server Management Shell**.</span></span>

3.  <span data-ttu-id="de5ad-130">**Remove-CsNetworkInterSitePolicy** cmdlet을 사용하여 네트워크 사이트 링크를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="de5ad-130">Use the **Remove-CsNetworkInterSitePolicy** cmdlet to remove a network site link.</span></span> <span data-ttu-id="de5ad-131">다음 예제에서는 Reno Portland 네트워크 사이트 \_ 링크를 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="de5ad-131">The following example deletes the Reno\_Portland network site link:</span></span>
    
        Remove-CsNetworkInterSitePolicy -Identity Reno_Portland

<span data-ttu-id="de5ad-132">자세한 매개 변수 설명은 [Remove-CsNetworkInterSitePolicy를 참조하세요.](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy)</span><span class="sxs-lookup"><span data-stu-id="de5ad-132">For detailed parameter descriptions, see [Remove-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy).</span></span>


## <a name="view-network-site-information"></a><span data-ttu-id="de5ad-133">네트워크 사이트 정보 보기</span><span class="sxs-lookup"><span data-stu-id="de5ad-133">View network site information</span></span>

<span data-ttu-id="de5ad-134">네트워크 사이트는 CAC(통화 허용 제어) 또는 고급 9-1-1 배포의 각 지역 내에 구성된 사무실 또는 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="de5ad-134">Network sites are the offices or locations configured within each region of a call admission control (CAC) or Enhanced 9-1-1 deployment.</span></span> <span data-ttu-id="de5ad-135">비즈니스용 Skype 서버 제어판 또는 비즈니스용 Skype 서버 관리 셸에서 네트워크 사이트 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de5ad-135">You can view network site information in either the Skype for Business Server Control Panel or the Skype for Business Server Management Shell.</span></span> 

### <a name="to-view-network-site-information-in-skype-for-business-server-control-panel"></a><span data-ttu-id="de5ad-136">비즈니스용 Skype 서버 제어판에서 네트워크 사이트 정보를 보기 위해</span><span class="sxs-lookup"><span data-stu-id="de5ad-136">To view network site information in Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="de5ad-137">RTCUniversalServerAdmins 그룹의 구성원(또는 이와 동등한 사용자 권한)인 사용자 계정에서 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포의 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="de5ad-137">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="de5ad-138">브라우저 창을 열고 관리자 URL을 입력하여 비즈니스용 Skype 서버 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="de5ad-138">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="de5ad-139">왼쪽 탐색 모음에서 네트워크 구성을 클릭한 다음 사이트를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="de5ad-139">In the left navigation bar, click **Network Configuration**, and then click **Site**.</span></span>

4.  <span data-ttu-id="de5ad-140">사이트 **페이지에서** 보하려는 사이트를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="de5ad-140">On the **Site** page, click the site that you want to view.</span></span>
 
    > [!NOTE]  
    > <span data-ttu-id="de5ad-141">한 사이트에 대한 정보는 한 번만 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de5ad-141">You can only view information for one site at a time.</span></span>

5.  <span data-ttu-id="de5ad-142">**편집** 메뉴에서 **자세한 정보 표시** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="de5ad-142">On the **Edit** menu, click **Show details**.</span></span>


### <a name="viewing-network-site-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="de5ad-143">cmdlet을 사용하여 네트워크 사이트 Windows PowerShell 보기</span><span class="sxs-lookup"><span data-stu-id="de5ad-143">Viewing network site information by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="de5ad-144">네트워크 사이트 정보는 네트워크 사이트 Windows PowerShell cmdlet을 사용하여 Get-CsNetworkSite 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de5ad-144">You can view network site information by using Windows PowerShell and the Get-CsNetworkSite cmdlet.</span></span> <span data-ttu-id="de5ad-145">이 cmdlet은 비즈니스용 Skype 서버 관리 셸 또는 비즈니스용 Skype 서버 관리 셸에서 실행할 수 Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="de5ad-145">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

### <a name="to-view-network-site-information"></a><span data-ttu-id="de5ad-146">네트워크 사이트 정보를 보기 위해</span><span class="sxs-lookup"><span data-stu-id="de5ad-146">To view network site information</span></span>

  - <span data-ttu-id="de5ad-147">모든 네트워크 사이트에 대한 정보를 보시다시피 비즈니스용 Skype 서버 관리 셸에서 다음 명령을 입력하고 Enter를 누르고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de5ad-147">To view information about all your network sites, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsNetworkSite
    
    <span data-ttu-id="de5ad-148">그러면 다음과 같은 정보가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="de5ad-148">That will return information similar to this:</span></span>
    
        Identity          : Redmond
        NetworkSiteID     : Redmond
        Description       :
        NetworkRegionID   : Pacific Northwest
        BypassID          : 3b232b84-2c1d-4da2-8181-e9330bafebe9
        BWPolicyProfileID :
        LocationPolicy    :

<span data-ttu-id="de5ad-149">자세한 내용은 [Get-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite) cmdlet에 대한 도움말 항목을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="de5ad-149">For more information, see the help topic for the [Get-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite) cmdlet.</span></span>


## <a name="create-or-modify-network-sites"></a><span data-ttu-id="de5ad-150">네트워크 사이트 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="de5ad-150">Create or modify network sites</span></span> 

<span data-ttu-id="de5ad-151">네트워크 사이트는 CAC(통화 허용 제어) 또는 고급 9-1-1 배포의 각 지역 내에 구성된 사무실 또는 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="de5ad-151">Network sites are the offices or locations configured within each region of a call admission control (CAC) or Enhanced 9-1-1 deployment.</span></span> <span data-ttu-id="de5ad-152">비즈니스용 Skype 서버 제어판을 사용하여 사이트를 구성하고 지역과 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="de5ad-152">You can use the Skype for Business Server Control Panel to configure sites and associate them with regions.</span></span> <span data-ttu-id="de5ad-153">예를 들어 북미 지역의 네트워크 지역은 Chicago, Redmond 및 Vancouver와 같은 네트워크 사이트와 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de5ad-153">For example, a network region for North America might be associated with networks sites such as Chicago, Redmond, and Vancouver.</span></span> <span data-ttu-id="de5ad-154">대역폭 제한이 없는 사이트를 포함하여 조직 내의 모든 사이트에는 CAC 네트워크 사이트를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="de5ad-154">A CAC network site must be created for every site within an organization, even if that site has no bandwidth limitations.</span></span> <span data-ttu-id="de5ad-155">비즈니스용 Skype 서버 제어판에서 네트워크 사이트를 만들고 수정하고 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de5ad-155">From the Skype for Business Server Control Panel you can create, modify, and delete network sites.</span></span> <span data-ttu-id="de5ad-156">다음 절차에 따라 네트워크 사이트를 만들거나 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="de5ad-156">Use the following procedures to create or modify a network site.</span></span> 

### <a name="to-create-a-network-site"></a><span data-ttu-id="de5ad-157">네트워크 사이트를 만들려면</span><span class="sxs-lookup"><span data-stu-id="de5ad-157">To create a network site</span></span>

1.  <span data-ttu-id="de5ad-158">RTCUniversalServerAdmins 그룹의 구성원(또는 이와 동등한 사용자 권한)인 사용자 계정에서 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포의 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="de5ad-158">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="de5ad-159">브라우저 창을 열고 관리자 URL을 입력하여 비즈니스용 Skype 서버 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="de5ad-159">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="de5ad-160">왼쪽 탐색 모음에서 네트워크 구성을 클릭한 다음 사이트를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="de5ad-160">In the left navigation bar, click **Network Configuration**, and then click **Site**.</span></span>

4.  <span data-ttu-id="de5ad-161">**사이트** 페이지에서 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="de5ad-161">On the **Site** page, click **New**.</span></span>

5.  <span data-ttu-id="de5ad-162">**새 사이트** 에서 **이름** 필드에 해당 사이트의 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="de5ad-162">In **New Site**, type a name for this site in the **Name** field.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="de5ad-163">사이트 이름은 비즈니스용 Skype 서버 배포 내에서 고유해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="de5ad-163">Site names must be unique within the Skype for Business Server deployment.</span></span>

6.  <span data-ttu-id="de5ad-164">**지역** 드롭다운 목록에서 이 사이트에 연결할 네트워크 지역을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="de5ad-164">In the **Region** drop-down list, select a network region to associate with this site.</span></span>

7.  <span data-ttu-id="de5ad-165">(선택 사항) 이 사이트에 대한 오디오 또는 비디오 통화에 대역폭 제한을 적용하려면 **대역폭 정책** 드롭다운 목록에서 적절한 설정이 포함된 대역폭 정책 프로필을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="de5ad-165">(Optional) If you want to place bandwidth limitations on audio or video calls to this site, select the bandwidth policy profile with the appropriate settings from the **Bandwidth policy** drop-down list.</span></span>
 
    > [!NOTE]  
    > <span data-ttu-id="de5ad-166">네트워크 구성 그룹의 정책 프로파일 페이지에서 사용 가능한 대역폭 정책 프로필의 세부  정보를 보거나 새 대역폭 정책 프로필을 만들 **수** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de5ad-166">You can view the details of the available bandwidth policy profiles, or create a new bandwidth policy profile, on the **Policy Profil** page of the **Network Configuration** group.</span></span> <span data-ttu-id="de5ad-167">자세한 내용은 네트워크 대역폭 정책 [프로필 관리를 참조하세요.](managing-network-bandwidth-policy-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="de5ad-167">For details, see [Managing network bandwidth policy profiles](managing-network-bandwidth-policy-profiles.md).</span></span>

8.  <span data-ttu-id="de5ad-168">(선택 사항) 이 사이트에 대해 위치 설정을 제공하려면 **위치 정책** 드롭다운 목록에서 위치 정책을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="de5ad-168">(Optional) If you want to provide location settings for this site, select a location policy from the **Location policy** drop-down list.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="de5ad-169">위치 정책은 사이트에 특정 E9-1-1(고급 9-1-1) 및 클라이언트 위치 설정을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="de5ad-169">The location policy assigns specific Enhanced 9-1-1 (E9-1-1) and client location settings to the site.</span></span> <span data-ttu-id="de5ad-170">**네트워크 구성** 그룹의 **위치 정책** 페이지에서 사용 가능한 위치 정책의 세부 정보를 보거나 새 위치 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de5ad-170">You can view the details of the available location policies, or create a new location policy, from the **Location Policy** page of the **Network Configuration** group.</span></span> 

9.  <span data-ttu-id="de5ad-171">(선택 사항) 이름만으로는 표현할 수 없는 이 사이트에 대한 자세한 정보를 제공하려면 **설명** 필드에 값을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="de5ad-171">(Optional) Type a value in the **Description** field to provide more information about this site that cannot be expressed by the name alone.</span></span>

10. <span data-ttu-id="de5ad-172">**커밋** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="de5ad-172">Click **Commit**.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="de5ad-173">새 네트워크 사이트를 만들 때는 **연결된 서브넷** 표를 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="de5ad-173">You do not use the **Associated Subnets** table when you create a new network site.</span></span> <span data-ttu-id="de5ad-174">서브넷을 만들거나 수정할 때 서브넷을 사이트에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="de5ad-174">You associate a subnet with a site when you create or modify the subnet.</span></span> <span data-ttu-id="de5ad-175">자세한 내용은 네트워크 [서브넷 관리를 참조합니다.](managing-network-subnets.md)</span><span class="sxs-lookup"><span data-stu-id="de5ad-175">For details, see [Managing network subnets](managing-network-subnets.md).</span></span>

### <a name="to-modify-a-network-site"></a><span data-ttu-id="de5ad-176">네트워크 사이트를 수정하려면</span><span class="sxs-lookup"><span data-stu-id="de5ad-176">To modify a network site</span></span>

1.  <span data-ttu-id="de5ad-177">RTCUniversalServerAdmins 그룹의 구성원(또는 이와 동등한 사용자 권한)인 사용자 계정에서 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포의 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="de5ad-177">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="de5ad-178">브라우저 창을 열고 관리자 URL을 입력하여 비즈니스용 Skype 서버 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="de5ad-178">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="de5ad-179">왼쪽 탐색 모음에서 네트워크 구성을 클릭한 다음 사이트를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="de5ad-179">In the left navigation bar, click **Network Configuration**, and then click **Site**.</span></span>

4.  <span data-ttu-id="de5ad-180">**사이트** 페이지에서 수정할 사이트를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="de5ad-180">On the **Site** page, click the site that you want to modify.</span></span>

5.  <span data-ttu-id="de5ad-181">**편집** 메뉴에서 **자세한 정보 표시** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="de5ad-181">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="de5ad-182">**사이트 편집** 페이지에서 사이트에 연결된 위치 정책, 대역폭 정책 프로필, 지역 및 설명을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de5ad-182">On the **Edit Site** page, you can modify the description, region, bandwidth policy profile, and location policy associated with the site.</span></span> <span data-ttu-id="de5ad-183">자세한 내용은 위의 네트워크 [사이트를 만들 수](#to-create-a-network-site) 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de5ad-183">For details, see [To create a network site](#to-create-a-network-site) above.</span></span>

7.  <span data-ttu-id="de5ad-184">**커밋** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="de5ad-184">Click **Commit**.</span></span>

<span data-ttu-id="de5ad-p114">이 페이지의 **연결된 서브넷** 표는 수정할 수 없습니다. 연결된 서브넷 목록은 사이트 설정 수정 시 영향을 받는 서브넷을 확인할 수 있도록 참조용으로 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="de5ad-p114">You cannot modify the **Associated Subnets** table on this page. The list of associated subnets is provided for reference so that you are aware of what subnets will be affected when you modify the site settings.</span></span>


## <a name="delete-an-existing-network-site"></a><span data-ttu-id="de5ad-187">기존 네트워크 사이트 삭제</span><span class="sxs-lookup"><span data-stu-id="de5ad-187">Delete an existing network site</span></span>

<span data-ttu-id="de5ad-188">네트워크 사이트는 CAC(통화 허용 제어) 또는 고급 9-1-1 배포의 각 지역 내에 구성된 사무실 또는 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="de5ad-188">Network sites are the offices or locations configured within each region of a call admission control (CAC) or Enhanced 9-1-1 deployment.</span></span> <span data-ttu-id="de5ad-189">비즈니스용 Skype 서버 제어판을 사용하여 사이트를 구성하고 지역과 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="de5ad-189">You can use the Skype for Business Server Control Panel to configure sites and associate them with regions.</span></span> <span data-ttu-id="de5ad-190">예를 들어 북미 지역의 네트워크 지역은 Chicago, Redmond 및 Vancouver와 같은 네트워크 사이트와 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de5ad-190">For example, a network region for North America might be associated with networks sites such as Chicago, Redmond, and Vancouver.</span></span> <span data-ttu-id="de5ad-191">대역폭 제한이 없는 사이트를 포함하여 조직 내의 모든 사이트에는 CAC 네트워크 사이트를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="de5ad-191">A CAC network site must be created for every site within an organization, even if that site has no bandwidth limitations.</span></span> <span data-ttu-id="de5ad-192">비즈니스용 Skype 서버 제어판에서 네트워크 사이트를 만들고 수정하고 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de5ad-192">From the Skype for Business Server Control Panel you can create, modify, and delete network sites.</span></span> <span data-ttu-id="de5ad-193">다음 절차에 따라 기존 네트워크 사이트를 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="de5ad-193">Use the following procedure to delete an existing network site.</span></span> <span data-ttu-id="de5ad-194">네트워크 사이트 만들기 또는 수정에 대한 자세한 내용은 사이트에 대한 통화 입력 제어 [관리 기능을 참조합니다.](managing-call-admission-control-for-sites.md)</span><span class="sxs-lookup"><span data-stu-id="de5ad-194">For details about creating or modifying network sites, see [Managing call admission control for sites](managing-call-admission-control-for-sites.md).</span></span>


### <a name="to-delete-a-network-site"></a><span data-ttu-id="de5ad-195">네트워크 사이트를 삭제하려면</span><span class="sxs-lookup"><span data-stu-id="de5ad-195">To delete a network site</span></span>

1.  <span data-ttu-id="de5ad-196">RTCUniversalServerAdmins 그룹의 구성원(또는 이와 동등한 사용자 권한)인 사용자 계정에서 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포의 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="de5ad-196">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="de5ad-197">브라우저 창을 열고 관리자 URL을 입력하여 비즈니스용 Skype 서버 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="de5ad-197">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="de5ad-198">왼쪽 탐색 모음에서 네트워크 구성을 클릭한 다음 사이트를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="de5ad-198">In the left navigation bar, click **Network Configuration**, and then click **Site**.</span></span>

4.  <span data-ttu-id="de5ad-199">**사이트** 페이지에서 삭제할 사이트를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="de5ad-199">On the **Site** page, click the site that you want to delete.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="de5ad-p116">한 번에 둘 이상의 사이트를 삭제할 수 있습니다. 이렇게 하려면 Ctrl 키를 누른 상태에서 여러 사이트를 선택합니다. 또는 모든 사이트를 선택하려면 **편집** 메뉴에서 **모두 선택** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="de5ad-p116">You can delete more than one site at a time. To do this, press CTRL and select multiple sites while holding down the CTRL key. Or, to select all sites, click **Select all** on the **Edit** menu.</span></span>

5.  <span data-ttu-id="de5ad-203">**편집** 메뉴에서 **삭제** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="de5ad-203">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="de5ad-204">**확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="de5ad-204">Click **OK**.</span></span>
    

    > [!WARNING]  
    > <span data-ttu-id="de5ad-p117">네트워크 서브넷과 연결된 네트워크 사이트는 제거할 수 없습니다. 서브넷과 연결된 사이트를 제거하려고 시도하면 오류 메시지가 표시됩니다. 사이트가 서브넷에 연결되어 있는지 확인하려면 **편집** 메뉴에서 **자세한 정보 표시** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="de5ad-p117">You cannot remove a network site if it is associated with a network subnet. If you attempt to remove a site associated with a subnet you will receive an error message. To see if a site is associated with any subnets, click the site and then click **Show details** on the **Edit** menu.</span></span>


## <a name="see-also"></a><span data-ttu-id="de5ad-208">참고 항목</span><span class="sxs-lookup"><span data-stu-id="de5ad-208">See Also</span></span>


[<span data-ttu-id="de5ad-209">New-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="de5ad-209">New-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy) 
 
[<span data-ttu-id="de5ad-210">Set-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="de5ad-210">Set-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy)  

[<span data-ttu-id="de5ad-211">Remove-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="de5ad-211">Remove-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy)  

[<span data-ttu-id="de5ad-212">Get-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="de5ad-212">Get-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterSitePolicy)  

[<span data-ttu-id="de5ad-213">Get-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="de5ad-213">Get-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)  

[<span data-ttu-id="de5ad-214">New-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="de5ad-214">New-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSite)

[<span data-ttu-id="de5ad-215">Set-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="de5ad-215">Set-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSite)

[<span data-ttu-id="de5ad-216">Remove-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="de5ad-216">Remove-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSite)  

[<span data-ttu-id="de5ad-217">Get-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="de5ad-217">Get-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite)  
