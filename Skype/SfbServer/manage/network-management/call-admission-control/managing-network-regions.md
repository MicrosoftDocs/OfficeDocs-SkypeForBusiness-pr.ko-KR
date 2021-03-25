---
title: 네트워크 지역 관리
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
description: 네트워크 지역*은 통화 액세스 제어, E9-1-1 및 미디어 우회 구성에 사용되는 네트워크 허브 또는 백본입니다.
ms.openlocfilehash: 2020eea2cf8bf85c915ebf88de6f86cb3a0ee9ca
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51122452"
---
# <a name="managing-network-regions-in-skype-for-business-server"></a><span data-ttu-id="437aa-103">비즈니스용 Skype 서버에서 네트워크 지역 관리</span><span class="sxs-lookup"><span data-stu-id="437aa-103">Managing network regions in Skype for Business Server</span></span>

<span data-ttu-id="437aa-104">*네트워크 지역* 은 통화 허용 제어, E9-1-1 및 미디어 바이패스 구성에 사용되는 네트워크 허브 또는 백본입니다.</span><span class="sxs-lookup"><span data-stu-id="437aa-104">*Network regions* are the network hubs or backbones used in the configuration of call admission control, E9-1-1, and media bypass.</span></span> <span data-ttu-id="437aa-105">다음 절차에 따라 네트워크 지역을 확인, 작성 또는 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="437aa-105">Use the following procedures to view, create, or modify network regions.</span></span> <span data-ttu-id="437aa-106">예를 들어 단일 음성 기능에 대해 네트워크 지역을 이미 만든 경우에는 새 네트워크 지역을 만들 필요가 없으며, 다른 고급 Enterprise Voice 기능도 같은 네트워크 지역을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="437aa-106">For example, if you have already created network regions for one Voice feature, you do not need to create new network regions; other advanced Enterprise Voice features will use those same network regions.</span></span> <span data-ttu-id="437aa-107">그러나 기존 네트워크 지역 정의를 수정하여 기능별 설정을 적용할 수는 있습니다.</span><span class="sxs-lookup"><span data-stu-id="437aa-107">You may, however, need to modify an existing network region definition to apply feature-specific settings.</span></span> <span data-ttu-id="437aa-108">예를 들어 E9-1-1용으로 네트워크 지역을 만든 후(연결된 중앙 사이트가 필요하지 않음) 통화 허용 제어를 배포하는 경우에는 네트워크 지역 정의를 수정하여 중앙 사이트를 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="437aa-108">For example, if you have created network regions for E9-1-1 (which do not require an associated central site) and you then deploy call admission control, you need to modify the network region definitions to specify a central site.</span></span> 

<span data-ttu-id="437aa-109">이 문서의 절차에 따라 네트워크 지역 정보를 보거나 네트워크 지역을 만들거나 수정하거나 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="437aa-109">Use the procedures in this article to view network region information or create, modify, or delete network regions.</span></span> 

## <a name="view-network-region-information"></a><span data-ttu-id="437aa-110">네트워크 지역 정보 보기</span><span class="sxs-lookup"><span data-stu-id="437aa-110">View network region information</span></span> 


<span data-ttu-id="437aa-111">네트워크 지역은 여러 지역의 많은 네트워크 부분을 교차합니다.</span><span class="sxs-lookup"><span data-stu-id="437aa-111">A network region interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="437aa-112">모든 네트워크 지역은 중앙 사이트와 연결되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="437aa-112">Every network region must be associated with a central site.</span></span> <span data-ttu-id="437aa-113">중앙 사이트는 CAC(통화 허용 제어) 대역폭 정책 서비스가 실행되는 데이터 센터 사이트입니다.</span><span class="sxs-lookup"><span data-stu-id="437aa-113">The central site is the data center site on which the call admission control (CAC) bandwidth policy service is running.</span></span> <span data-ttu-id="437aa-114">비즈니스용 Skype 서버 제어판을 사용하여 네트워크 지역을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="437aa-114">You can use Skype for Business Server Control Panel to view network regions.</span></span> <span data-ttu-id="437aa-115">네트워크 지역에는 오디오 및 비디오 연결에 대해 인터넷을 통한 대체 경로가 허용되는지 여부를 결정하는 설정이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="437aa-115">Network regions include settings that determine whether alternate paths through the Internet are allowed for audio and video connections.</span></span> <span data-ttu-id="437aa-116">이 항목을 사용하여 기존 네트워크 지역을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="437aa-116">Use this topic to view existing network regions.</span></span> 

### <a name="to-view-information-about-a-network-region-with-skype-for-business-server-control-panel"></a><span data-ttu-id="437aa-117">비즈니스용 Skype 서버 제어판을 사용하여 네트워크 지역에 대한 정보를 보기 위해</span><span class="sxs-lookup"><span data-stu-id="437aa-117">To view information about a network region with Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="437aa-118">RTCUniversalServerAdmins 그룹의 구성원 또는 이와 동등한 사용자 권한을 가졌다는 사용자 계정 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포의 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="437aa-118">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="437aa-119">브라우저 창을 열고 관리 URL을 입력하여 비즈니스용 Skype 서버 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="437aa-119">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="437aa-120">왼쪽 탐색 모음에서 네트워크 **구성을 클릭한** 다음 지역 을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="437aa-120">In the left navigation bar, click **Network Configuration**, and then click **Region**.</span></span>

4.  <span data-ttu-id="437aa-121">**지역** 페이지에서 보려는 지역을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="437aa-121">On the **Region** page, click the region you want to view.</span></span>
  
    > [!NOTE]  
    > <span data-ttu-id="437aa-122">한 번에 한 지역만 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="437aa-122">You can only view one region at a time.</span></span>

5.  <span data-ttu-id="437aa-123">**편집** 메뉴에서 **세부 정보 표시** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="437aa-123">On the **Edit** menu, click **Show details**.</span></span>


### <a name="viewing-network-region-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="437aa-124">cmdlet을 사용하여 네트워크 지역 Windows PowerShell 보기</span><span class="sxs-lookup"><span data-stu-id="437aa-124">Viewing network region information by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="437aa-125">네트워크 지역 정보와 **Get-CsNetworkRegion** cmdlet을 Windows PowerShell 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="437aa-125">You can view network region information by using Windows PowerShell and the **Get-CsNetworkRegion** cmdlet.</span></span> <span data-ttu-id="437aa-126">비즈니스용 Skype 서버 관리 셸 또는 비즈니스용 Skype 서버 관리 셸에서 이 cmdlet을 실행할 수 Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="437aa-126">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

### <a name="to-view-network-region-information"></a><span data-ttu-id="437aa-127">네트워크 지역 정보를 보기 위해</span><span class="sxs-lookup"><span data-stu-id="437aa-127">To view network region information</span></span>

  - <span data-ttu-id="437aa-128">모든 네트워크 지역에 대한 정보를 보기 위해 비즈니스용 Skype 서버 관리 셸에 다음 명령을 입력한 다음 Enter를 누르고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="437aa-128">To view information about all your network regions, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsNetworkRegion
    
    <span data-ttu-id="437aa-129">그러면 다음과 같은 정보가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="437aa-129">That will return information similar to this:</span></span>
    
        Identity         : Pacific Northwest
        Description      :
        BypassID         : 3b232b84-2c1d-4da2-8181-e9330bafebe9
        CentralSite      : Site:Redmond1
        BWAlternatePaths : {BWPolicyModality=Audio;AlternatePath=True, 
                           BWPolicyModality=Video;AlternatePath=True}
        NetworkRegionID  : Pacific Northwest

<span data-ttu-id="437aa-130">자세한 내용은 [Get-CsNetworkRegion](/powershell/module/skype/Get-CsNetworkRegionLink) cmdlet의 도움말 항목을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="437aa-130">For more information, see the help topic for the [Get-CsNetworkRegion](/powershell/module/skype/Get-CsNetworkRegionLink) cmdlet.</span></span>


## <a name="create-or-modify-network-regions"></a><span data-ttu-id="437aa-131">네트워크 지역 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="437aa-131">Create or modify network regions</span></span> 

<span data-ttu-id="437aa-132">네트워크 지역은 여러 지역의 많은 네트워크 부분을 교차합니다.</span><span class="sxs-lookup"><span data-stu-id="437aa-132">A network region interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="437aa-133">모든 네트워크 지역은 중앙 사이트와 연결되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="437aa-133">Every network region must be associated with a central site.</span></span> <span data-ttu-id="437aa-134">중앙 사이트는 CAC(통화 허용 제어) 대역폭 정책 서비스가 실행되는 데이터 센터 사이트입니다.</span><span class="sxs-lookup"><span data-stu-id="437aa-134">The central site is the data center site on which the call admission control (CAC) bandwidth policy service is running.</span></span> <span data-ttu-id="437aa-135">비즈니스용 Skype 서버 제어판을 사용하여 네트워크 지역을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="437aa-135">You can use the Skype for Business Server Control Panel to configure network regions.</span></span> <span data-ttu-id="437aa-136">네트워크 지역에는 오디오 및 비디오 연결에 대해 인터넷을 통한 대체 경로가 허용되는지 여부를 결정하는 설정이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="437aa-136">Network regions include settings that determine whether alternate paths through the Internet are allowed for audio and video connections.</span></span> <span data-ttu-id="437aa-137">비즈니스용 Skype 서버 제어판에서 네트워크 지역을 만들거나 수정하거나 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="437aa-137">From the Skype for Business Server Control Panel, you can create, modify, or delete a network region.</span></span> <span data-ttu-id="437aa-138">이 항목을 사용하여 네트워크 지역을 만들고 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="437aa-138">Use this topic to create and modify network regions.</span></span> 

### <a name="to-create-a-network-region"></a><span data-ttu-id="437aa-139">네트워크 지역을 만들려면</span><span class="sxs-lookup"><span data-stu-id="437aa-139">To create a network region</span></span>

1.  <span data-ttu-id="437aa-140">RTCUniversalServerAdmins 그룹의 구성원 또는 이와 동등한 사용자 권한을 가졌다는 사용자 계정 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포의 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="437aa-140">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="437aa-141">브라우저 창을 열고 관리 URL을 입력하여 비즈니스용 Skype 서버 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="437aa-141">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="437aa-142">왼쪽 탐색 모음에서 네트워크 **구성을 클릭한** 다음 지역 을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="437aa-142">In the left navigation bar, click **Network Configuration**, and then click **Region**.</span></span>

4.  <span data-ttu-id="437aa-143">**지역** 페이지에서 **새로 만들기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="437aa-143">On the **Region** page, click **New**.</span></span>

5.  <span data-ttu-id="437aa-144">**새 지역** 페이지의 **이름** 필드에 값을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="437aa-144">In the **New Region** page, type a value in the **Name** field.</span></span> <span data-ttu-id="437aa-145">이 값은 비즈니스용 Skype 서버 배포 내에서 고유해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="437aa-145">This value must be unique within your Skype for Business Server deployment.</span></span>

6.  <span data-ttu-id="437aa-146">**중앙 사이트** 드롭다운 목록에서 이 네트워크 지역에 대한 중앙 사이트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="437aa-146">From the **Central site** drop-down list, select the central site for this network region.</span></span>

7.  <span data-ttu-id="437aa-p106">**오디오 대체 경로 사용** 확인란은 기본적으로 선택됩니다. 이 필드는 기본 경로에 적절한 대역폭이 없는 경우 대체 경로를 통해 음성 통화를 라우팅할지 여부를 결정하며, 인터넷으로 오프로드를 해제해야 하는 경우에만 이 확인란을 선택 취소합니다. 통화가 인터넷 통화인 경우 대역폭 설정에 관계없이 이 확인란을 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="437aa-p106">The **Enable audio alternate path** check box is checked by default. This field determines whether audio calls will be routed through an alternate path if adequate bandwidth does not exist in the primary path. Clear this check box only if you need to turn off the offload to the Internet. If any of your calls will be Internet calls, this check box must be checked, regardless of bandwidth settings.</span></span>

8.  <span data-ttu-id="437aa-p107">**비디오 대체 경로 사용** 확인란은 기본적으로 선택됩니다. 이 필드는 기본 경로에 적절한 대역폭이 없는 경우 대체 경로를 통해 화상 통화를 라우팅할지 여부를 결정하며, 인터넷으로 오프로드를 해제해야 하는 경우에만 이 확인란을 선택 취소합니다. 통화가 인터넷 통화인 경우 대역폭 설정에 관계없이 이 확인란을 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="437aa-p107">The **Enable video alternate path** check box is checked by default. This field determines whether video calls will be routed through an alternate path if adequate bandwidth does not exist in the primary path. Clear this check box only if you need to turn off the offload to the Internet. If any of your calls will be Internet calls, this check box must be checked, regardless of bandwidth settings.</span></span>

9.  <span data-ttu-id="437aa-155">(선택 사항) **설명** 필드에 값을 입력하여 이름 하나로만 표시될 수 없는 이 지역에 대해 추가 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="437aa-155">(Optional) Type a value in the **Description** field to provide more information about this region that cannot be expressed by the name alone.</span></span>

10. <span data-ttu-id="437aa-156">**커밋** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="437aa-156">Click **Commit**.</span></span>

<span data-ttu-id="437aa-157">네트워크 지역을 만드는 데 **연결된 사이트** 표는 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="437aa-157">The **Associated sites** table is not used for creating a network region.</span></span> <span data-ttu-id="437aa-158">사이트를 만들거나 수정할 때 사이트와 지역이 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="437aa-158">You associate a site with a region when you create or modify the site.</span></span> <span data-ttu-id="437aa-159">자세한 내용은 [Managing call admission control for sites를 참조합니다.](managing-call-admission-control-for-sites.md)</span><span class="sxs-lookup"><span data-stu-id="437aa-159">For details, see [Managing call admission control for sites](managing-call-admission-control-for-sites.md).</span></span>

### <a name="to-modify-a-network-region"></a><span data-ttu-id="437aa-160">네트워크 지역을 수정하려면</span><span class="sxs-lookup"><span data-stu-id="437aa-160">To modify a network region</span></span>

1.  <span data-ttu-id="437aa-161">RTCUniversalServerAdmins 그룹의 구성원 또는 이와 동등한 사용자 권한을 가졌다는 사용자 계정 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포의 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="437aa-161">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="437aa-162">브라우저 창을 열고 관리 URL을 입력하여 비즈니스용 Skype 서버 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="437aa-162">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="437aa-163">왼쪽 탐색 모음에서 네트워크 **구성을 클릭한** 다음 지역 을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="437aa-163">In the left navigation bar, click **Network Configuration**, and then click **Region**.</span></span>

4.  <span data-ttu-id="437aa-164">**지역** 페이지에서 수정할 지역을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="437aa-164">On the **Region** page, click the region that you want to modify.</span></span>

5.  <span data-ttu-id="437aa-165">**편집** 메뉴에서 **자세한 정보 표시** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="437aa-165">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="437aa-166">**지역 편집** 페이지에서 오디오 및 비디오 대체 경로를 사용하거나 사용하지 않도록 지정하는 설정을 수정하고 설명을 변경할 수 있습니다(자세한 내용은 이 항목의 이전 섹션인 "네트워크 지역을 만들려면" 섹션 참조).</span><span class="sxs-lookup"><span data-stu-id="437aa-166">On the **Edit Region** page, you can modify the settings for enabling and disabling audio and video alternate paths, and change the description (for details, see the "To create a network region" section earlier in this topic.</span></span>

7.  <span data-ttu-id="437aa-167">**커밋** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="437aa-167">Click **Commit**.</span></span>

<span data-ttu-id="437aa-p109">이 페이지에서 **연결된 사이트** 는 수정할 수 없습니다. 연결된 사이트 목록은 참조용으로 제공되므로 지역 설정을 수정할 때는 영향을 받는 사이트를 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="437aa-p109">You cannot modify the **Associated sites** on this page. The list of associated sites is provided for reference so you are aware of which sites will be affected when you modify the region settings.</span></span>


## <a name="delete-existing-network-regions"></a><span data-ttu-id="437aa-170">기존 네트워크 지역 삭제</span><span class="sxs-lookup"><span data-stu-id="437aa-170">Delete existing network regions</span></span> 

<span data-ttu-id="437aa-171">네트워크 지역은 여러 지역의 많은 네트워크 부분을 교차합니다.</span><span class="sxs-lookup"><span data-stu-id="437aa-171">A network region interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="437aa-172">모든 네트워크 지역은 중앙 사이트와 연결되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="437aa-172">Every network region must be associated with a central site.</span></span> <span data-ttu-id="437aa-173">중앙 사이트는 CAC(통화 허용 제어) 대역폭 정책 서비스가 실행되는 데이터 센터 사이트입니다.</span><span class="sxs-lookup"><span data-stu-id="437aa-173">The central site is the data center site on which the call admission control (CAC) bandwidth policy service is running.</span></span> <span data-ttu-id="437aa-174">비즈니스용 Skype 서버 제어판을 사용하여 네트워크 지역을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="437aa-174">You can use the Skype for Business Server Control Panel to configure network regions.</span></span> <span data-ttu-id="437aa-175">네트워크 지역에는 오디오 및 비디오 연결에 대해 인터넷을 통한 대체 경로가 허용되는지 여부를 결정하는 설정이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="437aa-175">Network regions include settings that determine whether alternate paths through the Internet are allowed for audio and video connections.</span></span> <span data-ttu-id="437aa-176">비즈니스용 Skype 서버 제어판에서 네트워크 지역을 만들거나 수정하거나 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="437aa-176">From the Skype for Business Server Control Panel, you can create, modify, or delete a network region.</span></span> <span data-ttu-id="437aa-177">이 항목을 참조하여 기존 네트워크 지역을 삭제하십시오.</span><span class="sxs-lookup"><span data-stu-id="437aa-177">Use this topic to delete existing network regions.</span></span> 

### <a name="to-delete-a-network-region"></a><span data-ttu-id="437aa-178">네트워크 지역을 삭제하려면</span><span class="sxs-lookup"><span data-stu-id="437aa-178">To delete a network region</span></span>

1.  <span data-ttu-id="437aa-179">RTCUniversalServerAdmins 그룹의 구성원 또는 이와 동등한 사용자 권한을 가졌다는 사용자 계정 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포의 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="437aa-179">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="437aa-180">브라우저 창을 열고 관리 URL을 입력하여 비즈니스용 Skype 서버 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="437aa-180">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="437aa-181">왼쪽 탐색 모음에서 네트워크 **구성을 클릭한** 다음 지역 을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="437aa-181">In the left navigation bar, click **Network Configuration**, and then click **Region**.</span></span>

4.  <span data-ttu-id="437aa-182">**지역** 페이지에서 삭제하려는 지역을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="437aa-182">On the **Region** page, click the region you want to delete.</span></span>
  
    > [!NOTE]  
    > <span data-ttu-id="437aa-p111">한 번에 둘 이상의 지역을 삭제할 수 있습니다. 이렇게 하려면 Ctrl 키를 누른 상태에서 여러 지역을 선택합니다. 또는 지역을 모두 선택하려면 **편집** 메뉴에서 **모두 선택** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="437aa-p111">You can delete more than one region at a time. To do this, press CTRL and select multiple regions while holding down the CTRL key. Or, to select all regions, click **Select all** on the **Edit** menu.</span></span>

5.  <span data-ttu-id="437aa-186">**편집** 메뉴에서 **삭제** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="437aa-186">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="437aa-187">**확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="437aa-187">Click **OK**.</span></span>


    > [!WARNING]  
    > <span data-ttu-id="437aa-188">네트워크 사이트와 연결된 네트워크 지역은 제거할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="437aa-188">A network region cannot be removed if it is associated with a network site.</span></span> <span data-ttu-id="437aa-189">사이트와 연결된 지역을 제거하려고 하면 오류 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="437aa-189">If you attempt to remove a region associated with a site, you will receive an error message.</span></span> <span data-ttu-id="437aa-190">지역이 사이트와 연결되어 있는지 확인하려면 지역을 선택하고 **편집** 메뉴에서 **자세한 정보 표시** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="437aa-190">To see if a region is associated with any sites, select the region and then click **Show details** on the **Edit** menu.</span></span>


## <a name="see-also"></a><span data-ttu-id="437aa-191">참고 항목</span><span class="sxs-lookup"><span data-stu-id="437aa-191">See Also</span></span>

[<span data-ttu-id="437aa-192">네트워크 지역 경로 관리</span><span class="sxs-lookup"><span data-stu-id="437aa-192">Managing network region routes</span></span>](managing-network-region-routes.md)

[<span data-ttu-id="437aa-193">New-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="437aa-193">New-CsNetworkRegion</span></span>](/powershell/module/skype/New-CsNetworkRegion)  

[<span data-ttu-id="437aa-194">Set-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="437aa-194">Set-CsNetworkRegion</span></span>](/powershell/module/skype/Set-CsNetworkRegion)  

[<span data-ttu-id="437aa-195">Remove-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="437aa-195">Remove-CsNetworkRegion</span></span>](/powershell/module/skype/Remove-CsNetworkRegion)  

[<span data-ttu-id="437aa-196">Get-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="437aa-196">Get-CsNetworkRegion</span></span>](/powershell/module/skype/Get-CsNetworkRegionLink)