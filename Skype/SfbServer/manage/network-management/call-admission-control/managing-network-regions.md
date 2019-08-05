---
title: 네트워크 지역 관리
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 네트워크 지역 *은 통화 허용 제어 (E9-1-1) 및 미디어 바이패스 구성에 사용 되는 네트워크 허브나 백본.
ms.openlocfilehash: 8d1d60389fe910e2b5c2b8b1c357520aad30db96
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36188565"
---
# <a name="managing-network-regions-in-skype-for-business-server"></a><span data-ttu-id="d4243-103">비즈니스용 Skype 서버에서 네트워크 지역 관리</span><span class="sxs-lookup"><span data-stu-id="d4243-103">Managing network regions in Skype for Business Server</span></span>

<span data-ttu-id="d4243-104">*네트워크 지역은* 통화 허용 제어 (E9-1-1) 및 미디어 바이패스 구성에 사용 되는 네트워크 허브나 백본.</span><span class="sxs-lookup"><span data-stu-id="d4243-104">*Network regions* are the network hubs or backbones used in the configuration of call admission control, E9-1-1, and media bypass.</span></span> <span data-ttu-id="d4243-105">네트워크 지역을 확인, 생성 또는 수정 하려면 다음 절차를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4243-105">Use the following procedures to view, create, or modify network regions.</span></span> <span data-ttu-id="d4243-106">예를 들어 한 음성 기능에 대 한 네트워크 지역을 이미 만든 경우 새 네트워크 지역을 만들 필요가 없습니다. 그 밖의 고급 엔터프라이즈 음성 기능으로는 동일한 네트워크 지역을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4243-106">For example, if you have already created network regions for one Voice feature, you do not need to create new network regions; other advanced Enterprise Voice features will use those same network regions.</span></span> <span data-ttu-id="d4243-107">그러나 기능별 설정을 적용 하려면 기존 네트워크 지역 정의를 수정 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4243-107">You may, however, need to modify an existing network region definition to apply feature-specific settings.</span></span> <span data-ttu-id="d4243-108">예를 들어 E9 (연결 된 중앙 사이트가 필요 하지 않음)에 대 한 네트워크 지역을 만든 다음 통화 허용 제어를 배포 하는 경우에는 네트워크 지역 정의를 수정 하 여 중앙 사이트를 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4243-108">For example, if you have created network regions for E9-1-1 (which do not require an associated central site) and you then deploy call admission control, you need to modify the network region definitions to specify a central site.</span></span> 

<span data-ttu-id="d4243-109">이 문서의 절차를 사용 하 여 네트워크 지역 정보를 보거나 네트워크 지역을 만들거나 수정 하거나 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4243-109">Use the procedures in this article to view network region information or create, modify, or delete network regions.</span></span> 

## <a name="view-network-region-information"></a><span data-ttu-id="d4243-110">네트워크 지역 정보 보기</span><span class="sxs-lookup"><span data-stu-id="d4243-110">View network region information</span></span> 


<span data-ttu-id="d4243-111">네트워크 영역은 여러 지리적 영역에 걸친 네트워크의 다양 한 부분을 상호 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4243-111">A network region interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="d4243-112">모든 네트워크 지역은 중앙 사이트와 연결 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4243-112">Every network region must be associated with a central site.</span></span> <span data-ttu-id="d4243-113">중앙 사이트는 CAC (call 허용 제어) 대역폭 정책 서비스가 실행 되는 데이터 센터 사이트입니다.</span><span class="sxs-lookup"><span data-stu-id="d4243-113">The central site is the data center site on which the call admission control (CAC) bandwidth policy service is running.</span></span> <span data-ttu-id="d4243-114">비즈니스용 Skype Server 제어판을 사용 하 여 네트워크 지역을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4243-114">You can use Skype for Business Server Control Panel to view network regions.</span></span> <span data-ttu-id="d4243-115">네트워크 영역에는 오디오 및 비디오 연결에 인터넷을 통한 대체 경로가 허용 되는지 여부를 결정 하는 설정이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d4243-115">Network regions include settings that determine whether alternate paths through the Internet are allowed for audio and video connections.</span></span> <span data-ttu-id="d4243-116">기존 네트워크 지역을 보려면이 항목을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4243-116">Use this topic to view existing network regions.</span></span> 

### <a name="to-view-information-about-a-network-region-with-skype-for-business-server-control-panel"></a><span data-ttu-id="d4243-117">비즈니스용 Skype Server 제어판의 네트워크 지역에 대 한 정보를 보려면</span><span class="sxs-lookup"><span data-stu-id="d4243-117">To view information about a network region with Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="d4243-118">RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsAdministrator 역할에 할당 된 경우 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4243-118">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="d4243-119">브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="d4243-119">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="d4243-120">왼쪽 탐색 모음에서 **네트워크 구성을**클릭 한 다음 **지역을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4243-120">In the left navigation bar, click **Network Configuration**, and then click **Region**.</span></span>

4.  <span data-ttu-id="d4243-121">**지역** 페이지에서 보려는 지역을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4243-121">On the **Region** page, click the region you want to view.</span></span>
  
    > [!NOTE]  
    > <span data-ttu-id="d4243-122">한 번에 한 영역만 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4243-122">You can only view one region at a time.</span></span>

5.  <span data-ttu-id="d4243-123">**편집** 메뉴에서 **세부 정보 표시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4243-123">On the **Edit** menu, click **Show details**.</span></span>


### <a name="viewing-network-region-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="d4243-124">Windows PowerShell cmdlet을 사용 하 여 네트워크 지역 정보 보기</span><span class="sxs-lookup"><span data-stu-id="d4243-124">Viewing network region information by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="d4243-125">Windows PowerShell 및 **Get-CsNetworkRegion** cmdlet을 사용 하 여 네트워크 지역 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4243-125">You can view network region information by using Windows PowerShell and the **Get-CsNetworkRegion** cmdlet.</span></span> <span data-ttu-id="d4243-126">이 cmdlet은 비즈니스용 Skype 서버 관리 셸에서 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4243-126">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

### <a name="to-view-network-region-information"></a><span data-ttu-id="d4243-127">네트워크 지역 정보를 보려면</span><span class="sxs-lookup"><span data-stu-id="d4243-127">To view network region information</span></span>

  - <span data-ttu-id="d4243-128">모든 네트워크 지역에 대 한 정보를 보려면 비즈니스용 Skype 서버 관리 셸에서 다음 명령을 입력 한 다음 enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="d4243-128">To view information about all your network regions, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsNetworkRegion
    
    <span data-ttu-id="d4243-129">이는 다음과 같은 정보를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4243-129">That will return information similar to this:</span></span>
    
        Identity         : Pacific Northwest
        Description      :
        BypassID         : 3b232b84-2c1d-4da2-8181-e9330bafebe9
        CentralSite      : Site:Redmond1
        BWAlternatePaths : {BWPolicyModality=Audio;AlternatePath=True, 
                           BWPolicyModality=Video;AlternatePath=True}
        NetworkRegionID  : Pacific Northwest

<span data-ttu-id="d4243-130">자세한 내용은 [Get CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink) cmdlet에 대 한 도움말 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d4243-130">For more information, see the help topic for the [Get-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink) cmdlet.</span></span>


## <a name="create-or-modify-network-regions"></a><span data-ttu-id="d4243-131">네트워크 지역 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="d4243-131">Create or modify network regions</span></span> 

<span data-ttu-id="d4243-132">네트워크 영역은 여러 지리적 영역에 걸친 네트워크의 다양 한 부분을 상호 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4243-132">A network region interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="d4243-133">모든 네트워크 지역은 중앙 사이트와 연결 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4243-133">Every network region must be associated with a central site.</span></span> <span data-ttu-id="d4243-134">중앙 사이트는 CAC (call 허용 제어) 대역폭 정책 서비스가 실행 되는 데이터 센터 사이트입니다.</span><span class="sxs-lookup"><span data-stu-id="d4243-134">The central site is the data center site on which the call admission control (CAC) bandwidth policy service is running.</span></span> <span data-ttu-id="d4243-135">비즈니스용 Skype Server 제어판을 사용 하 여 네트워크 지역을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4243-135">You can use the Skype for Business Server Control Panel to configure network regions.</span></span> <span data-ttu-id="d4243-136">네트워크 영역에는 오디오 및 비디오 연결에 인터넷을 통한 대체 경로가 허용 되는지 여부를 결정 하는 설정이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d4243-136">Network regions include settings that determine whether alternate paths through the Internet are allowed for audio and video connections.</span></span> <span data-ttu-id="d4243-137">비즈니스용 Skype 서버 제어판에서 네트워크 지역을 만들거나 수정 하거나 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4243-137">From the Skype for Business Server Control Panel, you can create, modify, or delete a network region.</span></span> <span data-ttu-id="d4243-138">이 항목을 사용 하 여 네트워크 지역을 만들고 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4243-138">Use this topic to create and modify network regions.</span></span> 

### <a name="to-create-a-network-region"></a><span data-ttu-id="d4243-139">네트워크 지역을 만들려면</span><span class="sxs-lookup"><span data-stu-id="d4243-139">To create a network region</span></span>

1.  <span data-ttu-id="d4243-140">RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsAdministrator 역할에 할당 된 경우 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4243-140">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="d4243-141">브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="d4243-141">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="d4243-142">왼쪽 탐색 모음에서 **네트워크 구성을**클릭 한 다음 **지역을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4243-142">In the left navigation bar, click **Network Configuration**, and then click **Region**.</span></span>

4.  <span data-ttu-id="d4243-143">**지역** 페이지에서 **새로 만들기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4243-143">On the **Region** page, click **New**.</span></span>

5.  <span data-ttu-id="d4243-144">**새 지역** 페이지의 **이름** 필드에 값을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4243-144">In the **New Region** page, type a value in the **Name** field.</span></span> <span data-ttu-id="d4243-145">이 값은 비즈니스용 Skype 서버 배포 내에서 고유 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4243-145">This value must be unique within your Skype for Business Server deployment.</span></span>

6.  <span data-ttu-id="d4243-146">**중앙 사이트** 드롭다운 목록에서이 네트워크 영역에 대 한 중앙 사이트를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4243-146">From the **Central site** drop-down list, select the central site for this network region.</span></span>

7.  <span data-ttu-id="d4243-147">**오디오 대체 경로 사용** 확인란이 기본적으로 선택 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4243-147">The **Enable audio alternate path** check box is checked by default.</span></span> <span data-ttu-id="d4243-148">이 필드는 기본 경로에 적절 한 대역폭이 없는 경우 오디오 통화가 대체 경로를 통해 라우팅되는 지를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4243-148">This field determines whether audio calls will be routed through an alternate path if adequate bandwidth does not exist in the primary path.</span></span> <span data-ttu-id="d4243-149">인터넷에 대 한 오프 로드를 해제 해야 하는 경우에만이 확인란의 선택을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4243-149">Clear this check box only if you need to turn off the offload to the Internet.</span></span> <span data-ttu-id="d4243-150">인터넷에 전화를 거는 경우 대역폭 설정에 관계 없이이 확인란을 선택 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4243-150">If any of your calls will be Internet calls, this check box must be checked, regardless of bandwidth settings.</span></span>

8.  <span data-ttu-id="d4243-151">**비디오 대체 경로 사용** 확인란이 기본적으로 선택 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4243-151">The **Enable video alternate path** check box is checked by default.</span></span> <span data-ttu-id="d4243-152">이 필드는 기본 경로에 적절 한 대역폭이 없는 경우 영상 통화를 대체 경로를 통해 라우팅할 지 여부를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4243-152">This field determines whether video calls will be routed through an alternate path if adequate bandwidth does not exist in the primary path.</span></span> <span data-ttu-id="d4243-153">인터넷에 대 한 오프 로드를 해제 해야 하는 경우에만이 확인란의 선택을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4243-153">Clear this check box only if you need to turn off the offload to the Internet.</span></span> <span data-ttu-id="d4243-154">인터넷에 전화를 거는 경우 대역폭 설정에 관계 없이이 확인란을 선택 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4243-154">If any of your calls will be Internet calls, this check box must be checked, regardless of bandwidth settings.</span></span>

9.  <span data-ttu-id="d4243-155">) 이름 만으로 표현할 수 없는이 영역에 대 한 자세한 정보를 제공 하려면 **설명** 필드에 값을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4243-155">(Optional) Type a value in the **Description** field to provide more information about this region that cannot be expressed by the name alone.</span></span>

10. <span data-ttu-id="d4243-156">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d4243-156">Click **Commit**.</span></span>

<span data-ttu-id="d4243-157">**연결 된 사이트** 테이블은 네트워크 지역을 만드는 데 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d4243-157">The **Associated sites** table is not used for creating a network region.</span></span> <span data-ttu-id="d4243-158">사이트를 만들거나 수정할 때 사이트를 영역과 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4243-158">You associate a site with a region when you create or modify the site.</span></span> <span data-ttu-id="d4243-159">자세한 내용은 [사이트에 대 한 통화 허용 제어 관리](managing-call-admission-control-for-sites.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d4243-159">For details, see [Managing call admission control for sites](managing-call-admission-control-for-sites.md).</span></span>

### <a name="to-modify-a-network-region"></a><span data-ttu-id="d4243-160">네트워크 지역 수정</span><span class="sxs-lookup"><span data-stu-id="d4243-160">To modify a network region</span></span>

1.  <span data-ttu-id="d4243-161">RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsAdministrator 역할에 할당 된 경우 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4243-161">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="d4243-162">브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="d4243-162">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="d4243-163">왼쪽 탐색 모음에서 **네트워크 구성을**클릭 한 다음 **지역을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4243-163">In the left navigation bar, click **Network Configuration**, and then click **Region**.</span></span>

4.  <span data-ttu-id="d4243-164">**지역** 페이지에서 수정 하려는 지역을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4243-164">On the **Region** page, click the region that you want to modify.</span></span>

5.  <span data-ttu-id="d4243-165">**편집** 메뉴에서 **세부 정보 표시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4243-165">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="d4243-166">**지역 편집** 페이지에서 오디오 및 비디오 대체 경로를 사용 하거나 사용 하지 않도록 설정 하는 설정을 수정 하 고 설명 (자세한 내용은이 항목의 "네트워크 영역 만들기" 섹션을 참조 하세요.)을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4243-166">On the **Edit Region** page, you can modify the settings for enabling and disabling audio and video alternate paths, and change the description (for details, see the "To create a network region" section earlier in this topic.</span></span>

7.  <span data-ttu-id="d4243-167">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d4243-167">Click **Commit**.</span></span>

<span data-ttu-id="d4243-168">이 페이지에서 **연결 된 사이트** 를 수정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d4243-168">You cannot modify the **Associated sites** on this page.</span></span> <span data-ttu-id="d4243-169">연결 된 사이트 목록은 지역 설정을 수정할 때 영향을 받는 사이트를 알 수 있도록 참조용으로 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d4243-169">The list of associated sites is provided for reference so you are aware of which sites will be affected when you modify the region settings.</span></span>


## <a name="delete-existing-network-regions"></a><span data-ttu-id="d4243-170">기존 네트워크 지역 삭제</span><span class="sxs-lookup"><span data-stu-id="d4243-170">Delete existing network regions</span></span> 

<span data-ttu-id="d4243-171">네트워크 영역은 여러 지리적 영역에 걸친 네트워크의 다양 한 부분을 상호 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4243-171">A network region interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="d4243-172">모든 네트워크 지역은 중앙 사이트와 연결 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4243-172">Every network region must be associated with a central site.</span></span> <span data-ttu-id="d4243-173">중앙 사이트는 CAC (call 허용 제어) 대역폭 정책 서비스가 실행 되는 데이터 센터 사이트입니다.</span><span class="sxs-lookup"><span data-stu-id="d4243-173">The central site is the data center site on which the call admission control (CAC) bandwidth policy service is running.</span></span> <span data-ttu-id="d4243-174">비즈니스용 Skype Server 제어판을 사용 하 여 네트워크 지역을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4243-174">You can use the Skype for Business Server Control Panel to configure network regions.</span></span> <span data-ttu-id="d4243-175">네트워크 영역에는 오디오 및 비디오 연결에 인터넷을 통한 대체 경로가 허용 되는지 여부를 결정 하는 설정이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d4243-175">Network regions include settings that determine whether alternate paths through the Internet are allowed for audio and video connections.</span></span> <span data-ttu-id="d4243-176">비즈니스용 Skype 서버 제어판에서 네트워크 지역을 만들거나 수정 하거나 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4243-176">From the Skype for Business Server Control Panel, you can create, modify, or delete a network region.</span></span> <span data-ttu-id="d4243-177">이 항목을 사용 하 여 기존 네트워크 지역을 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4243-177">Use this topic to delete existing network regions.</span></span> 

### <a name="to-delete-a-network-region"></a><span data-ttu-id="d4243-178">네트워크 지역을 삭제 하려면</span><span class="sxs-lookup"><span data-stu-id="d4243-178">To delete a network region</span></span>

1.  <span data-ttu-id="d4243-179">RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsAdministrator 역할에 할당 된 경우 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4243-179">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="d4243-180">브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="d4243-180">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="d4243-181">왼쪽 탐색 모음에서 **네트워크 구성을**클릭 한 다음 **지역을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4243-181">In the left navigation bar, click **Network Configuration**, and then click **Region**.</span></span>

4.  <span data-ttu-id="d4243-182">**지역** 페이지에서 삭제 하려는 지역을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4243-182">On the **Region** page, click the region you want to delete.</span></span>
  
    > [!NOTE]  
    > <span data-ttu-id="d4243-183">한 번에 여러 지역을 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4243-183">You can delete more than one region at a time.</span></span> <span data-ttu-id="d4243-184">이 작업을 수행 하려면 ctrl 키를 누른 채 여러 지역을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4243-184">To do this, press CTRL and select multiple regions while holding down the CTRL key.</span></span> <span data-ttu-id="d4243-185">또는 모든 지역을 선택 하려면 **편집** 메뉴에서 **모두 선택을** 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4243-185">Or, to select all regions, click **Select all** on the **Edit** menu.</span></span>

5.  <span data-ttu-id="d4243-186">**편집** 메뉴에서 **삭제**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4243-186">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="d4243-187">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d4243-187">Click **OK**.</span></span>


    > [!WARNING]  
    > <span data-ttu-id="d4243-188">네트워크 사이트와 연결 된 네트워크 지역은 제거할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d4243-188">A network region cannot be removed if it is associated with a network site.</span></span> <span data-ttu-id="d4243-189">사이트와 연결 된 영역을 제거 하려고 하면 오류 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d4243-189">If you attempt to remove a region associated with a site, you will receive an error message.</span></span> <span data-ttu-id="d4243-190">영역이 사이트와 연결 되어 있는지 확인 하려면 지역을 선택 하 고 **편집** 메뉴에서 **세부 정보 표시** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4243-190">To see if a region is associated with any sites, select the region and then click **Show details** on the **Edit** menu.</span></span>


## <a name="see-also"></a><span data-ttu-id="d4243-191">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d4243-191">See Also</span></span>

[<span data-ttu-id="d4243-192">네트워크 지역 경로 관리</span><span class="sxs-lookup"><span data-stu-id="d4243-192">Managing network region routes</span></span>](managing-network-region-routes.md)

[<span data-ttu-id="d4243-193">새-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="d4243-193">New-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion)  

[<span data-ttu-id="d4243-194">Set-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="d4243-194">Set-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegion)  

[<span data-ttu-id="d4243-195">CsNetworkRegion 제거</span><span class="sxs-lookup"><span data-stu-id="d4243-195">Remove-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegion)  

[<span data-ttu-id="d4243-196">Get-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="d4243-196">Get-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)  
