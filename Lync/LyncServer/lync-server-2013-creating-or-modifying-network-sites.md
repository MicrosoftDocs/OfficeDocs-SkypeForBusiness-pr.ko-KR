---
title: 'Lync Server 2013: 네트워크 사이트 만들기 또는 수정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Creating or modifying network sites
ms:assetid: 358aa08a-c5bc-45fc-8017-19e6202f88c5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520975(v=OCS.15)
ms:contentKeyID: 48183801
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1e7c3db5b37cba514a0c07e11a907628dcc7823f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42047611"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="creating-or-modifying-network-sites-in-lync-server-2013"></a><span data-ttu-id="e9526-102">Lync Server 2013에서 네트워크 사이트 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="e9526-102">Creating or modifying network sites in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e9526-103">_**마지막으로 수정 된 항목:** 2012-10-08_</span><span class="sxs-lookup"><span data-stu-id="e9526-103">_**Topic Last Modified:** 2012-10-08_</span></span>

<span data-ttu-id="e9526-104">네트워크 사이트는 CAC(통화 허용 제어) 또는 고급 9-1-1 배포의 각 지역 내에 구성된 사무실 또는 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="e9526-104">Network sites are the offices or locations configured within each region of a call admission control (CAC) or Enhanced 9-1-1 deployment.</span></span> <span data-ttu-id="e9526-105">Microsoft Lync Server 2013 제어판을 사용 하 여 사이트를 구성 하 고 지역에 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e9526-105">You can use the Microsoft Lync Server 2013 Control Panel to configure sites and associate them with regions.</span></span> <span data-ttu-id="e9526-106">예를 들어 북미 지역의 네트워크 지역은 Chicago, Redmond 및 Vancouver와 같은 네트워크 사이트와 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e9526-106">For example, a network region for North America might be associated with networks sites such as Chicago, Redmond, and Vancouver.</span></span> <span data-ttu-id="e9526-107">대역폭 제한이 없는 사이트를 포함하여 조직 내의 모든 사이트에는 CAC 네트워크 사이트를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9526-107">A CAC network site must be created for every site within an organization, even if that site has no bandwidth limitations.</span></span> <span data-ttu-id="e9526-108">Lync Server 컨트롤 패널에서는 네트워크 사이트를 만들고, 수정 하 고, 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e9526-108">From the Lync Server Control Panel you can create, modify, and delete network sites.</span></span> <span data-ttu-id="e9526-109">다음 절차에 따라 네트워크 사이트를 만들거나 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="e9526-109">Use the following procedures to create or modify a network site.</span></span> <span data-ttu-id="e9526-110">기존 네트워크 사이트를 삭제 하는 방법에 대 한 자세한 내용은 [Lync Server 2013에서 기존 네트워크 사이트 삭제](lync-server-2013-deleting-an-existing-network-site.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="e9526-110">For details on deleting an existing network site, see [Deleting an existing network site in Lync Server 2013](lync-server-2013-deleting-an-existing-network-site.md).</span></span>

<div>

## <a name="to-create-a-network-site"></a><span data-ttu-id="e9526-111">네트워크 사이트를 만들려면</span><span class="sxs-lookup"><span data-stu-id="e9526-111">To create a network site</span></span>

1.  <span data-ttu-id="e9526-112">RTCUniversalServerAdmins 그룹의 구성원 인 사용자 계정 (또는 이와 동등한 사용자 권한 포함) 또는 CsAdministrator 역할이 할당 되 면 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9526-112">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="e9526-113">브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="e9526-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="e9526-114">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="e9526-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="e9526-115">왼쪽 탐색 모음에서 **네트워크 구성**을 클릭하고 **사이트**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e9526-115">In the left navigation bar, click **Network Configuration** and then click **Site**.</span></span>

4.  <span data-ttu-id="e9526-116">**사이트** 페이지에서 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e9526-116">On the **Site** page, click **New**.</span></span>

5.  <span data-ttu-id="e9526-117">**새 사이트**에서 **이름** 필드에 해당 사이트의 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="e9526-117">In **New Site**, type a name for this site in the **Name** field.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e9526-118">사이트 이름은 Lync Server 2013 배포 내에서 고유 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9526-118">Site names must be unique within the Lync Server 2013 deployment.</span></span>

    
    </div>

6.  <span data-ttu-id="e9526-119">**지역** 드롭다운 목록에서 이 사이트에 연결할 네트워크 지역을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e9526-119">In the **Region** drop-down list, select a network region to associate with this site.</span></span>

7.  <span data-ttu-id="e9526-120">(선택 사항) 이 사이트에 대한 오디오 또는 비디오 통화에 대역폭 제한을 적용하려면 **대역폭 정책** 드롭다운 목록에서 적절한 설정이 포함된 대역폭 정책 프로필을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e9526-120">(Optional) If you want to place bandwidth limitations on audio or video calls to this site, select the bandwidth policy profile with the appropriate settings from the **Bandwidth policy** drop-down list.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e9526-121"><STRONG>네트워크 구성</STRONG> 그룹의 <STRONG>정책 프로필</STRONG> 페이지에서 사용 가능한 대역폭 정책 프로필의 세부 정보를 보거나 새 대역폭 정책 프로필을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e9526-121">You can view the details of the available bandwidth policy profiles, or create a new bandwidth policy profile, on the <STRONG>Policy Profile</STRONG> page of the <STRONG>Network Configuration</STRONG> group.</span></span> <span data-ttu-id="e9526-122">자세한 내용은 <A href="lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md">Lync Server 2013에서 대역폭 정책 프로필 만들기 또는 수정을</A>참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="e9526-122">For details, see <A href="lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md">Creating or modifying bandwidth policy profiles in Lync Server 2013</A>.</span></span>

    
    </div>

8.  <span data-ttu-id="e9526-123">(선택 사항) 이 사이트에 대해 위치 설정을 제공하려면 **위치 정책** 드롭다운 목록에서 위치 정책을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e9526-123">(Optional) If you want to provide location settings for this site, select a location policy from the **Location policy** drop-down list.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e9526-124">위치 정책은 사이트에 특정 E9-1-1(고급 9-1-1) 및 클라이언트 위치 설정을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="e9526-124">The location policy assigns specific Enhanced 9-1-1 (E9-1-1) and client location settings to the site.</span></span> <span data-ttu-id="e9526-125"><STRONG>네트워크 구성</STRONG> 그룹의 <STRONG>위치 정책</STRONG> 페이지에서 사용 가능한 위치 정책의 세부 정보를 보거나 새 위치 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e9526-125">You can view the details of the available location policies, or create a new location policy, from the <STRONG>Location Policy</STRONG> page of the <STRONG>Network Configuration</STRONG> group.</span></span> <span data-ttu-id="e9526-126">자세한 내용은 <A href="lync-server-2013-viewing-location-policy-information.md">Lync Server 2013에서 위치 정책 정보 보기</A>를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="e9526-126">For details, see <A href="lync-server-2013-viewing-location-policy-information.md">Viewing location policy information in Lync Server 2013</A>.</span></span>

    
    </div>

9.  <span data-ttu-id="e9526-127">(선택 사항) 이름만으로는 표현할 수 없는 이 사이트에 대한 자세한 정보를 제공하려면 **설명** 필드에 값을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="e9526-127">(Optional) Type a value in the **Description** field to provide more information about this site that cannot be expressed by the name alone.</span></span>

10. <span data-ttu-id="e9526-128">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e9526-128">Click **Commit**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e9526-129">새 네트워크 사이트를 만들 때는 <STRONG>연결된 서브넷</STRONG> 표를 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e9526-129">You do not use the <STRONG>Associated Subnets</STRONG> table when you create a new network site.</span></span> <span data-ttu-id="e9526-130">서브넷을 만들거나 수정할 때 서브넷을 사이트에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="e9526-130">You associate a subnet with a site when you create or modify the subnet.</span></span> <span data-ttu-id="e9526-131">자세한 내용은 <A href="lync-server-2013-create-or-modify-network-subnets.md">Lync Server 2013에서 네트워크 서브넷 만들기 또는 수정을</A>참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="e9526-131">For details, see <A href="lync-server-2013-create-or-modify-network-subnets.md">Create or modify network subnets in Lync Server 2013</A>.</span></span>

    
    </div>

</div>

<div>

## <a name="to-modify-a-network-site"></a><span data-ttu-id="e9526-132">네트워크 사이트를 수정하려면</span><span class="sxs-lookup"><span data-stu-id="e9526-132">To modify a network site</span></span>

1.  <span data-ttu-id="e9526-133">RTCUniversalServerAdmins 그룹의 구성원 인 사용자 계정 (또는 이와 동등한 사용자 권한 포함) 또는 CsAdministrator 역할이 할당 되 면 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9526-133">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="e9526-134">브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="e9526-134">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="e9526-135">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="e9526-135">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="e9526-136">왼쪽 탐색 모음에서 **네트워크 구성**을 클릭하고 **사이트**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e9526-136">In the left navigation bar, click **Network Configuration** and then click **Site**.</span></span>

4.  <span data-ttu-id="e9526-137">**사이트** 페이지에서 수정할 사이트를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e9526-137">On the **Site** page, click the site that you want to modify.</span></span>

5.  <span data-ttu-id="e9526-138">**편집** 메뉴에서 **자세한 정보 표시**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e9526-138">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="e9526-p107">**사이트 편집** 페이지에서 사이트에 연결된 위치 정책, 대역폭 정책 프로필, 지역 및 설명을 수정할 수 있습니다. 자세한 내용은 이 항목의 앞부분에 나오는 "네트워크 사이트를 만들려면" 섹션을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="e9526-p107">On the **Edit Site** page, you can modify the description, region, bandwidth policy profile, and location policy associated with the site. For details, see "To create a network site" section earlier in this topic.</span></span>

7.  <span data-ttu-id="e9526-141">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e9526-141">Click **Commit**.</span></span>

<span data-ttu-id="e9526-p108">이 페이지의 **연결된 서브넷** 표는 수정할 수 없습니다. 연결된 서브넷 목록은 사이트 설정 수정 시 영향을 받는 서브넷을 확인할 수 있도록 참조용으로 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="e9526-p108">You cannot modify the **Associated Subnets** table on this page. The list of associated subnets is provided for reference so that you are aware of what subnets will be affected when you modify the site settings.</span></span>

</div>

<div>

## <a name="to-delete-a-network-site"></a><span data-ttu-id="e9526-144">네트워크 사이트를 삭제하려면</span><span class="sxs-lookup"><span data-stu-id="e9526-144">To delete a network site</span></span>

1.  <span data-ttu-id="e9526-145">RTCUniversalServerAdmins 그룹의 구성원 인 사용자 계정 (또는 이와 동등한 사용자 권한 포함) 또는 CsAdministrator 역할이 할당 되 면 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9526-145">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="e9526-146">브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="e9526-146">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="e9526-147">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="e9526-147">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="e9526-148">왼쪽 탐색 모음에서 **네트워크 구성**을 클릭하고 **사이트**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e9526-148">In the left navigation bar, click **Network Configuration** and then click **Site**.</span></span>

4.  <span data-ttu-id="e9526-149">**사이트** 페이지에서 삭제할 사이트를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e9526-149">On the **Site** page, click the site that you want to delete.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e9526-p110">한 번에 둘 이상의 사이트를 삭제할 수 있습니다. 이렇게 하려면 Ctrl 키를 누른 상태에서 여러 사이트를 선택합니다. 또는 모든 사이트를 선택하려면 <STRONG>편집</STRONG> 메뉴에서 <STRONG>모두 선택</STRONG>을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e9526-p110">You can delete more than one site at a time. To do this, press CTRL and select multiple sites while holding down the CTRL key. Or, to select all sites, click <STRONG>Select all</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

    
    </div>

5.  <span data-ttu-id="e9526-153">**편집** 메뉴에서 **삭제**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e9526-153">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="e9526-154">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e9526-154">Click **OK**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="e9526-p111">네트워크 서브넷과 연결된 네트워크 사이트는 제거할 수 없습니다. 서브넷과 연결된 사이트를 제거하려고 시도하면 오류 메시지가 표시됩니다. 사이트가 서브넷에 연결되어 있는지 확인하려면 <STRONG>편집</STRONG> 메뉴에서 <STRONG>자세한 정보 표시</STRONG>를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e9526-p111">You cannot remove a network site if it is associated with a network subnet. If you attempt to remove a site associated with a subnet you will receive an error message. To see if a site is associated with any subnets, click the site and then click <STRONG>Show details</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e9526-158">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e9526-158">See Also</span></span>


[<span data-ttu-id="e9526-159">Lync Server 2013에서 기존 네트워크 사이트 삭제</span><span class="sxs-lookup"><span data-stu-id="e9526-159">Deleting an existing network site in Lync Server 2013</span></span>](lync-server-2013-deleting-an-existing-network-site.md)  


[<span data-ttu-id="e9526-160">새-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="e9526-160">New-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSite)  
[<span data-ttu-id="e9526-161">설정-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="e9526-161">Set-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSite)  
[<span data-ttu-id="e9526-162">CsNetworkSite를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9526-162">Remove-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSite)  
[<span data-ttu-id="e9526-163">Get-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="e9526-163">Get-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

