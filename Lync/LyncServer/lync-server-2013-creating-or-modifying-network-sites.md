---
title: 'Lync Server 2013: 네트워크 사이트 만들기 또는 수정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Creating or modifying network sites
ms:assetid: 358aa08a-c5bc-45fc-8017-19e6202f88c5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520975(v=OCS.15)
ms:contentKeyID: 48183801
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3bb09dfcd490d47de1bbfbbde48f538e95fc64cf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984448"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="creating-or-modifying-network-sites-in-lync-server-2013"></a><span data-ttu-id="c5b23-102">Lync Server 2013에서 네트워크 사이트 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="c5b23-102">Creating or modifying network sites in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c5b23-103">_**마지막으로 수정한 주제:** 2012-10-08_</span><span class="sxs-lookup"><span data-stu-id="c5b23-103">_**Topic Last Modified:** 2012-10-08_</span></span>

<span data-ttu-id="c5b23-104">네트워크 사이트는 CAC (통화 허용 제어) 또는 향상 된 9-1-1 배포의 각 영역 내에서 구성 된 사무실 또는 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="c5b23-104">Network sites are the offices or locations configured within each region of a call admission control (CAC) or Enhanced 9-1-1 deployment.</span></span> <span data-ttu-id="c5b23-105">Microsoft Lync Server 2013 제어판을 사용 하 여 사이트를 구성 하 고 지역에 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5b23-105">You can use the Microsoft Lync Server 2013 Control Panel to configure sites and associate them with regions.</span></span> <span data-ttu-id="c5b23-106">예를 들어 북미, 레드먼드, Vancouver와 같은 네트워크 사이트에 북아메리카 네트워크 지역이 연결 되어 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5b23-106">For example, a network region for North America might be associated with networks sites such as Chicago, Redmond, and Vancouver.</span></span> <span data-ttu-id="c5b23-107">사이트에 대 한 모든 사이트에 대해 CAC 네트워크 사이트를 만들어야 하는 경우에도 해당 사이트가 대역폭 제한 없이 구성 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5b23-107">A CAC network site must be created for every site within an organization, even if that site has no bandwidth limitations.</span></span> <span data-ttu-id="c5b23-108">Lync Server 제어판에서 네트워크 사이트를 만들고, 수정 하 고, 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5b23-108">From the Lync Server Control Panel you can create, modify, and delete network sites.</span></span> <span data-ttu-id="c5b23-109">네트워크 사이트를 만들거나 수정 하려면 다음 절차를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5b23-109">Use the following procedures to create or modify a network site.</span></span> <span data-ttu-id="c5b23-110">기존 네트워크 사이트를 삭제 하는 방법에 대 한 자세한 내용은 [Lync Server 2013에서 기존 네트워크 사이트 삭제](lync-server-2013-deleting-an-existing-network-site.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c5b23-110">For details on deleting an existing network site, see [Deleting an existing network site in Lync Server 2013](lync-server-2013-deleting-an-existing-network-site.md).</span></span>

<div>

## <a name="to-create-a-network-site"></a><span data-ttu-id="c5b23-111">네트워크 사이트를 만들려면</span><span class="sxs-lookup"><span data-stu-id="c5b23-111">To create a network site</span></span>

1.  <span data-ttu-id="c5b23-112">RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsAdministrator 역할에 할당 된 경우 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5b23-112">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="c5b23-113">브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="c5b23-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="c5b23-114">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c5b23-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="c5b23-115">왼쪽 탐색 모음에서 **네트워크 구성을** 클릭 한 다음 **사이트**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5b23-115">In the left navigation bar, click **Network Configuration** and then click **Site**.</span></span>

4.  <span data-ttu-id="c5b23-116">**사이트** 페이지에서 **새로 만들기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5b23-116">On the **Site** page, click **New**.</span></span>

5.  <span data-ttu-id="c5b23-117">**새 사이트**의 **name (이름** ) 필드에이 사이트의 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5b23-117">In **New Site**, type a name for this site in the **Name** field.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c5b23-118">사이트 이름은 Lync Server 2013 배포 내에서 고유 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5b23-118">Site names must be unique within the Lync Server 2013 deployment.</span></span>

    
    </div>

6.  <span data-ttu-id="c5b23-119">**지역** 드롭다운 목록에서이 사이트와 연결할 네트워크 지역을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5b23-119">In the **Region** drop-down list, select a network region to associate with this site.</span></span>

7.  <span data-ttu-id="c5b23-120">) 이 사이트에 대 한 오디오 또는 비디오 통화에 대 한 대역폭 제한을 설정 하려면 대역폭 **정책** 드롭다운 목록에서 적절 한 설정을 사용 하 여 대역폭 정책 프로필을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5b23-120">(Optional) If you want to place bandwidth limitations on audio or video calls to this site, select the bandwidth policy profile with the appropriate settings from the **Bandwidth policy** drop-down list.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c5b23-121"><STRONG>네트워크 구성</STRONG> 그룹의 <STRONG>정책 프로필</STRONG> 페이지에서 사용 가능한 대역폭 정책 프로필의 세부 정보를 보거나 새 대역폭 정책 프로필을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5b23-121">You can view the details of the available bandwidth policy profiles, or create a new bandwidth policy profile, on the <STRONG>Policy Profile</STRONG> page of the <STRONG>Network Configuration</STRONG> group.</span></span> <span data-ttu-id="c5b23-122">자세한 내용은 <A href="lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md">Lync Server 2013에서 대역폭 정책 프로필 만들기 또는 수정을</A>참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c5b23-122">For details, see <A href="lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md">Creating or modifying bandwidth policy profiles in Lync Server 2013</A>.</span></span>

    
    </div>

8.  <span data-ttu-id="c5b23-123">) 이 사이트에 대 한 위치 설정을 제공 하려면 **위치 정책** 드롭다운 목록에서 위치 정책을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5b23-123">(Optional) If you want to provide location settings for this site, select a location policy from the **Location policy** drop-down list.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c5b23-124">위치 정책은 사이트에 특정 향상 된 9-1-1 (E9-1-1) 및 클라이언트 위치 설정을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5b23-124">The location policy assigns specific Enhanced 9-1-1 (E9-1-1) and client location settings to the site.</span></span> <span data-ttu-id="c5b23-125"><STRONG>네트워크 구성</STRONG> 그룹의 <STRONG>위치 정책</STRONG> 페이지에서 사용 가능한 위치 정책의 세부 정보를 보거나 새 위치 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5b23-125">You can view the details of the available location policies, or create a new location policy, from the <STRONG>Location Policy</STRONG> page of the <STRONG>Network Configuration</STRONG> group.</span></span> <span data-ttu-id="c5b23-126">자세한 내용은 <A href="lync-server-2013-viewing-location-policy-information.md">Lync Server 2013의 위치 정책 정보 보기</A>를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c5b23-126">For details, see <A href="lync-server-2013-viewing-location-policy-information.md">Viewing location policy information in Lync Server 2013</A>.</span></span>

    
    </div>

9.  <span data-ttu-id="c5b23-127">) 이름 만으로 표현할 수 없는이 사이트에 대 한 자세한 정보를 제공 하려면 **설명** 필드에 값을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5b23-127">(Optional) Type a value in the **Description** field to provide more information about this site that cannot be expressed by the name alone.</span></span>

10. <span data-ttu-id="c5b23-128">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c5b23-128">Click **Commit**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c5b23-129">새 네트워크 사이트를 만들 때 <STRONG>연결 된 서브넷</STRONG> 테이블을 사용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c5b23-129">You do not use the <STRONG>Associated Subnets</STRONG> table when you create a new network site.</span></span> <span data-ttu-id="c5b23-130">서브넷을 만들거나 수정할 때 서브넷을 사이트와 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5b23-130">You associate a subnet with a site when you create or modify the subnet.</span></span> <span data-ttu-id="c5b23-131">자세한 내용은 <A href="lync-server-2013-create-or-modify-network-subnets.md">Lync Server 2013에서 네트워크 서브넷 만들기 또는 수정을</A>참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c5b23-131">For details, see <A href="lync-server-2013-create-or-modify-network-subnets.md">Create or modify network subnets in Lync Server 2013</A>.</span></span>

    
    </div>

</div>

<div>

## <a name="to-modify-a-network-site"></a><span data-ttu-id="c5b23-132">네트워크 사이트를 수정 하려면</span><span class="sxs-lookup"><span data-stu-id="c5b23-132">To modify a network site</span></span>

1.  <span data-ttu-id="c5b23-133">RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsAdministrator 역할에 할당 된 경우 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5b23-133">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="c5b23-134">브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="c5b23-134">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="c5b23-135">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c5b23-135">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="c5b23-136">왼쪽 탐색 모음에서 **네트워크 구성을** 클릭 한 다음 **사이트**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5b23-136">In the left navigation bar, click **Network Configuration** and then click **Site**.</span></span>

4.  <span data-ttu-id="c5b23-137">**사이트** 페이지에서 수정 하려는 사이트를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5b23-137">On the **Site** page, click the site that you want to modify.</span></span>

5.  <span data-ttu-id="c5b23-138">**편집** 메뉴에서 **세부 정보 표시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5b23-138">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="c5b23-139">**사이트 편집** 페이지에서 설명, 지역, 대역폭 정책 프로필, 사이트와 연결 된 위치 정책을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5b23-139">On the **Edit Site** page, you can modify the description, region, bandwidth policy profile, and location policy associated with the site.</span></span> <span data-ttu-id="c5b23-140">자세한 내용은이 항목의 앞부분에 있는 "네트워크 사이트 만들기" 섹션을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c5b23-140">For details, see "To create a network site" section earlier in this topic.</span></span>

7.  <span data-ttu-id="c5b23-141">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c5b23-141">Click **Commit**.</span></span>

<span data-ttu-id="c5b23-142">이 페이지에서는 **연결 된 서브넷** 테이블을 수정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c5b23-142">You cannot modify the **Associated Subnets** table on this page.</span></span> <span data-ttu-id="c5b23-143">사이트 설정을 수정할 때 어떤 서브넷에 영향을 미치는지 알 수 있도록 관련 서브넷 목록이 참조용으로 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5b23-143">The list of associated subnets is provided for reference so that you are aware of what subnets will be affected when you modify the site settings.</span></span>

</div>

<div>

## <a name="to-delete-a-network-site"></a><span data-ttu-id="c5b23-144">네트워크 사이트를 삭제 하려면</span><span class="sxs-lookup"><span data-stu-id="c5b23-144">To delete a network site</span></span>

1.  <span data-ttu-id="c5b23-145">RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsAdministrator 역할에 할당 된 경우 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5b23-145">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="c5b23-146">브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="c5b23-146">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="c5b23-147">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c5b23-147">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="c5b23-148">왼쪽 탐색 모음에서 **네트워크 구성을** 클릭 한 다음 **사이트**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5b23-148">In the left navigation bar, click **Network Configuration** and then click **Site**.</span></span>

4.  <span data-ttu-id="c5b23-149">**사이트** 페이지에서 삭제 하려는 사이트를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5b23-149">On the **Site** page, click the site that you want to delete.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c5b23-150">한 번에 여러 사이트를 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5b23-150">You can delete more than one site at a time.</span></span> <span data-ttu-id="c5b23-151">이 작업을 수행 하려면 ctrl 키를 누른 채 여러 사이트를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5b23-151">To do this, press CTRL and select multiple sites while holding down the CTRL key.</span></span> <span data-ttu-id="c5b23-152">또는 모든 사이트를 선택 하려면 <STRONG>편집</STRONG> 메뉴에서 <STRONG>모두 선택을</STRONG> 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5b23-152">Or, to select all sites, click <STRONG>Select all</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

    
    </div>

5.  <span data-ttu-id="c5b23-153">**편집** 메뉴에서 **삭제**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5b23-153">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="c5b23-154">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c5b23-154">Click **OK**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="c5b23-155">네트워크 서브넷과 연결 된 네트워크 사이트는 제거할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c5b23-155">You cannot remove a network site if it is associated with a network subnet.</span></span> <span data-ttu-id="c5b23-156">서브넷과 연결 된 사이트를 제거 하려고 하면 오류 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5b23-156">If you attempt to remove a site associated with a subnet you will receive an error message.</span></span> <span data-ttu-id="c5b23-157">사이트가 서브넷과 연결 되어 있는지 확인 하려면 사이트를 클릭 한 다음 <STRONG>편집</STRONG> 메뉴에서 <STRONG>자세한 정보 표시</STRONG> 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5b23-157">To see if a site is associated with any subnets, click the site and then click <STRONG>Show details</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c5b23-158">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c5b23-158">See Also</span></span>


[<span data-ttu-id="c5b23-159">Lync Server 2013에서 기존 네트워크 사이트 삭제</span><span class="sxs-lookup"><span data-stu-id="c5b23-159">Deleting an existing network site in Lync Server 2013</span></span>](lync-server-2013-deleting-an-existing-network-site.md)  


[<span data-ttu-id="c5b23-160">새-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="c5b23-160">New-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSite)  
[<span data-ttu-id="c5b23-161">집합-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="c5b23-161">Set-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSite)  
[<span data-ttu-id="c5b23-162">CsNetworkSite 사이트 제거</span><span class="sxs-lookup"><span data-stu-id="c5b23-162">Remove-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSite)  
[<span data-ttu-id="c5b23-163">Get-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="c5b23-163">Get-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

