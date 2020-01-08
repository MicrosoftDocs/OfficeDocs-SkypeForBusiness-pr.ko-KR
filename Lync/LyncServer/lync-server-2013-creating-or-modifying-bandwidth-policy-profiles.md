---
title: 'Lync Server 2013: 대역폭 정책 프로필 만들기 또는 수정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Creating or modifying bandwidth policy profiles
ms:assetid: 08a2e18f-9b0d-4a2f-aa14-13bbf79ec745
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520945(v=OCS.15)
ms:contentKeyID: 48183336
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 38f44d759a77fea03b285d2e1af10838d508a6ba
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984974"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="creating-or-modifying-bandwidth-policy-profiles-in-lync-server-2013"></a><span data-ttu-id="039ff-102">Lync Server 2013에서 대역폭 정책 프로필 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="039ff-102">Creating or modifying bandwidth policy profiles in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="039ff-103">_**마지막으로 수정한 주제:** 2012-10-15_</span><span class="sxs-lookup"><span data-stu-id="039ff-103">_**Topic Last Modified:** 2012-10-15_</span></span>

<span data-ttu-id="039ff-104">호출 허용 제어 (CAC)의 일부로 대역폭 정책은 특정 형식을 대역폭 제한을 정의 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="039ff-104">As part of call admission control (CAC), a bandwidth policy is used to define bandwidth limitations for certain modalities.</span></span> <span data-ttu-id="039ff-105">Microsoft Lync Server 2013에서 오디오 및 비디오 형식을 대역폭 제한을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="039ff-105">In Microsoft Lync Server 2013, only audio and video modalities can be assigned bandwidth limitations.</span></span> <span data-ttu-id="039ff-106">전체 대역폭 제한 및 세션 제한을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="039ff-106">You can set overall bandwidth limitations and session limitations.</span></span> <span data-ttu-id="039ff-107">Lync Server 제어판을 사용 하 여 이러한 정책에 대 한 컨테이너 프로필을 만들거나 수정 하거나 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="039ff-107">You can use the Lync Server Control Panel to create, modify, or delete a container profile for these policies.</span></span> <span data-ttu-id="039ff-108">각 대역폭 정책 프로필을 하나 이상의 네트워크 사이트와 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="039ff-108">Each bandwidth policy profile can be associated with one or more network sites.</span></span> <span data-ttu-id="039ff-109">다음 절차를 사용 하 여 대역폭 정책 프로필을 만들거나 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="039ff-109">Use the following procedures to create or modify a bandwidth policy profile.</span></span> <span data-ttu-id="039ff-110">대역폭 정책 프로필을 삭제 하려면 [Lync Server 2013에서 네트워크 대역폭 정책 프로필 삭제](lync-server-2013-deleting-network-bandwidth-policy-profiles.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="039ff-110">To delete a bandwidth policy profile, see [Deleting network bandwidth policy profiles in Lync Server 2013](lync-server-2013-deleting-network-bandwidth-policy-profiles.md)</span></span>

<div>

## <a name="to-create-a-new-bandwidth-policy-profile"></a><span data-ttu-id="039ff-111">새 대역폭 정책 프로필을 만들려면</span><span class="sxs-lookup"><span data-stu-id="039ff-111">To create a new bandwidth policy profile</span></span>

1.  <span data-ttu-id="039ff-112">RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsAdministrator 역할에 할당 된 경우 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="039ff-112">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="039ff-113">브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="039ff-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="039ff-114">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="039ff-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="039ff-115">왼쪽 탐색 모음에서 **네트워크 구성을** 클릭 한 다음 **대역폭 정책을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="039ff-115">In the left navigation bar, click **Network Configuration** and then click **Bandwidth Policy**.</span></span>

4.  <span data-ttu-id="039ff-116">**대역폭 정책** 페이지에서 **새로 만들기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="039ff-116">On the **Bandwidth Policy** page, click **New**.</span></span>

5.  <span data-ttu-id="039ff-117">**새 대역폭 정책 프로필**의 **이름** 필드에 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="039ff-117">In **New Bandwidth Policy Profile**, type a name in the **Name** field.</span></span> <span data-ttu-id="039ff-118">이 이름은 모든 대역폭 정책 프로필에서 고유 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="039ff-118">This name must be unique among all bandwidth policy profiles.</span></span>

6.  <span data-ttu-id="039ff-119">**오디오 제한** 필드에 숫자 값을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="039ff-119">In the **Audio limit** field, type a numeric value.</span></span> <span data-ttu-id="039ff-120">이 값은 모든 오디오 연결에 할당할 수 있는 대역폭의 최대 양 (kbps로 표시 됨)입니다.</span><span class="sxs-lookup"><span data-stu-id="039ff-120">This value is the maximum amount of bandwidth to allocate for all audio connections, expressed in kbps.</span></span>

7.  <span data-ttu-id="039ff-121">**오디오 세션 제한** 필드에 숫자 값을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="039ff-121">Enter a numeric value in the **Audio session limit** field.</span></span> <span data-ttu-id="039ff-122">이 값은 kbps로 표시 되는 개별 오디오 연결에 할당할 수 있는 대역폭의 최대 양입니다.</span><span class="sxs-lookup"><span data-stu-id="039ff-122">This value is the maximum amount of bandwidth to allocate for an individual audio connection, expressed in kbps.</span></span> <span data-ttu-id="039ff-123">이 값은 40 이상 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="039ff-123">This value must be 40 or higher.</span></span>

8.  <span data-ttu-id="039ff-124">**비디오 제한** 필드에 숫자 값을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="039ff-124">Enter a numeric value in the **Video limit** field.</span></span> <span data-ttu-id="039ff-125">이 값은 모든 비디오 연결에 할당할 수 있는 대역폭의 최대 양 (kbps)입니다.</span><span class="sxs-lookup"><span data-stu-id="039ff-125">This value is the maximum amount of bandwidth to allocate for all video connections, expressed in kbps.</span></span>

9.  <span data-ttu-id="039ff-126">**비디오 세션 제한** 필드에 숫자 값을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="039ff-126">Enter a numeric value in the **Video session limit** field.</span></span> <span data-ttu-id="039ff-127">이 값은 kbps로 표시 되는 개별 비디오 연결에 할당할 수 있는 대역폭의 최대 양입니다.</span><span class="sxs-lookup"><span data-stu-id="039ff-127">This value is the maximum amount of bandwidth to allocate for an individual video connection, expressed in kbps.</span></span> <span data-ttu-id="039ff-128">이 값은 100 이상 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="039ff-128">This value must be 100 or higher.</span></span>

10. <span data-ttu-id="039ff-129">) 이름 만으로 표현할 수 없는이 대역폭 정책 프로필에 대 한 자세한 정보를 제공 하려면 **설명** 필드에 값을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="039ff-129">(Optional) Type a value in the **Description** field to provide more information about this bandwidth policy profile that cannot be expressed by the name alone.</span></span>

11. <span data-ttu-id="039ff-130">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="039ff-130">Click **Commit**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="039ff-131">새 대역폭 정책 프로필을 만들면 자동으로 대역폭 제한이 적용 되지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="039ff-131">Creating a new bandwidth policy profile does not automatically enforce bandwidth restrictions.</span></span> <span data-ttu-id="039ff-132">먼저 정책 프로필을 사이트와 연결 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="039ff-132">You must first associate the policy profile with a site.</span></span> <span data-ttu-id="039ff-133">사이트에 정책 프로필을 연결 하는 방법에 대 한 자세한 내용은 <A href="lync-server-2013-creating-or-modifying-network-sites.md">Lync Server 2013에서 네트워크 사이트 만들기 또는 수정을</A>참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="039ff-133">For details about how to associate a policy profile with a site, see <A href="lync-server-2013-creating-or-modifying-network-sites.md">Creating or modifying network sites in Lync Server 2013</A>.</span></span>

    
    </div>

</div>

<div>

## <a name="to-modify-a-bandwidth-policy-profile"></a><span data-ttu-id="039ff-134">대역폭 정책 프로필을 수정 하려면</span><span class="sxs-lookup"><span data-stu-id="039ff-134">To modify a bandwidth policy profile</span></span>

1.  <span data-ttu-id="039ff-135">RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsAdministrator 역할에 할당 된 경우 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="039ff-135">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="039ff-136">브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="039ff-136">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="039ff-137">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="039ff-137">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="039ff-138">왼쪽 탐색 모음에서 **네트워크 구성을** 클릭 한 다음 **대역폭 정책을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="039ff-138">In the left navigation bar, click **Network Configuration** and then click **Bandwidth Policy**.</span></span>

4.  <span data-ttu-id="039ff-139">**대역폭 정책** 페이지에서 수정 하려는 대역폭 정책 프로필을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="039ff-139">On the **Bandwidth Policy** page, click the bandwidth policy profile that you want to modify.</span></span>

5.  <span data-ttu-id="039ff-140">**편집** 메뉴에서 **세부 정보 표시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="039ff-140">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="039ff-141">**대역폭 정책 프로필 편집** 페이지에서 필요에 따라 필드를 수정 합니다 (자세한 내용은이 항목의 앞부분에 나오는 "대역폭 정책 프로필 만들기" 섹션을 참조 하세요.).</span><span class="sxs-lookup"><span data-stu-id="039ff-141">On the **Edit Bandwidth Policy Profile** page, modify the fields as necessary (for details, see the "To create a bandwidth policy profile" section earlier in this topic).</span></span>

7.  <span data-ttu-id="039ff-142">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="039ff-142">Click **Commit**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="039ff-143">대역폭 정책 프로필을 수정 하면이 대역폭 정책 프로필에 연결 된 모든 네트워크 사이트의 대역폭 제한이 즉시 업데이트 됩니다.</span><span class="sxs-lookup"><span data-stu-id="039ff-143">When you modify the bandwidth policy profile, it will immediately update the bandwidth limitations of all network sites associated with this bandwidth policy profile.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="039ff-144">참고 항목</span><span class="sxs-lookup"><span data-stu-id="039ff-144">See Also</span></span>


[<span data-ttu-id="039ff-145">Lync Server 2013에서 네트워크 대역폭 정책 프로필 삭제</span><span class="sxs-lookup"><span data-stu-id="039ff-145">Deleting network bandwidth policy profiles in Lync Server 2013</span></span>](lync-server-2013-deleting-network-bandwidth-policy-profiles.md)  


[<span data-ttu-id="039ff-146">Lync Server 2013에서 통화 허용 제어 구성</span><span class="sxs-lookup"><span data-stu-id="039ff-146">Configure call admission control in Lync Server 2013</span></span>](lync-server-2013-configure-call-admission-control.md)  
[<span data-ttu-id="039ff-147">새로운 CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="039ff-147">New-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkBandwidthPolicyProfile)  
[<span data-ttu-id="039ff-148">Set-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="039ff-148">Set-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkBandwidthPolicyProfile)  
[<span data-ttu-id="039ff-149">Get-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="039ff-149">Get-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

