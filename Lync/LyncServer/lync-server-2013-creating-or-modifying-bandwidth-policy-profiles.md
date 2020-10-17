---
title: 'Lync Server 2013: 대역폭 정책 프로필 만들기 또는 수정'
description: 'Lync Server 2013: 대역폭 정책 프로필 만들기 또는 수정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Creating or modifying bandwidth policy profiles
ms:assetid: 08a2e18f-9b0d-4a2f-aa14-13bbf79ec745
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520945(v=OCS.15)
ms:contentKeyID: 48183336
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: de8450cf8f4da53bf4a7e096fd7618b7fc6d055b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562974"
---
# <a name="creating-or-modifying-bandwidth-policy-profiles-in-lync-server-2013"></a><span data-ttu-id="1c355-103">Lync Server 2013에서 대역폭 정책 프로필 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="1c355-103">Creating or modifying bandwidth policy profiles in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1c355-104">_**마지막으로 수정 된 항목:** 2012-10-15_</span><span class="sxs-lookup"><span data-stu-id="1c355-104">_**Topic Last Modified:** 2012-10-15_</span></span>

<span data-ttu-id="1c355-105">대역폭 정책은 CAC(통화 허용 제어)의 일부로 특정 형식에 대한 대역폭 제한을 정의하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c355-105">As part of call admission control (CAC), a bandwidth policy is used to define bandwidth limitations for certain modalities.</span></span> <span data-ttu-id="1c355-106">Microsoft Lync Server 2013에서는 오디오 및 비디오 형식에만 대역폭 제한이 할당 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c355-106">In Microsoft Lync Server 2013, only audio and video modalities can be assigned bandwidth limitations.</span></span> <span data-ttu-id="1c355-107">전체 대역폭 제한 및 세션 제한을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c355-107">You can set overall bandwidth limitations and session limitations.</span></span> <span data-ttu-id="1c355-108">Lync Server 제어판을 사용 하 여 이러한 정책에 대 한 컨테이너 프로필을 만들거나 수정 하거나 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c355-108">You can use the Lync Server Control Panel to create, modify, or delete a container profile for these policies.</span></span> <span data-ttu-id="1c355-109">각 대역폭 정책 프로필은 하나 이상의 네트워크 사이트에 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c355-109">Each bandwidth policy profile can be associated with one or more network sites.</span></span> <span data-ttu-id="1c355-110">다음 절차에 따라 대역폭 정책 프로필을 만들거나 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="1c355-110">Use the following procedures to create or modify a bandwidth policy profile.</span></span> <span data-ttu-id="1c355-111">대역폭 정책 프로필을 삭제 하려면 [Lync Server 2013에서 네트워크 대역폭 정책 프로필 삭제](lync-server-2013-deleting-network-bandwidth-policy-profiles.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1c355-111">To delete a bandwidth policy profile, see [Deleting network bandwidth policy profiles in Lync Server 2013](lync-server-2013-deleting-network-bandwidth-policy-profiles.md)</span></span>

<div>

## <a name="to-create-a-new-bandwidth-policy-profile"></a><span data-ttu-id="1c355-112">새 대역폭 정책 프로필을 만들려면</span><span class="sxs-lookup"><span data-stu-id="1c355-112">To create a new bandwidth policy profile</span></span>

1.  <span data-ttu-id="1c355-113">RTCUniversalServerAdmins 그룹의 구성원 인 사용자 계정 (또는 이와 동등한 사용자 권한 포함) 또는 CsAdministrator 역할이 할당 되 면 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c355-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="1c355-114">브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="1c355-114">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="1c355-115">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="1c355-115">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="1c355-116">왼쪽 탐색 모음에서 **네트워크 구성**을 클릭한 다음 **대역폭 정책**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1c355-116">In the left navigation bar, click **Network Configuration** and then click **Bandwidth Policy**.</span></span>

4.  <span data-ttu-id="1c355-117">**대역폭 정책** 페이지에서 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1c355-117">On the **Bandwidth Policy** page, click **New**.</span></span>

5.  <span data-ttu-id="1c355-p103">**새 대역폭 정책 프로필**에서 **이름** 필드에 이름을 입력합니다. 이 이름은 모든 대역폭 정책 프로필에서 고유해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c355-p103">In **New Bandwidth Policy Profile**, type a name in the **Name** field. This name must be unique among all bandwidth policy profiles.</span></span>

6.  <span data-ttu-id="1c355-p104">**오디오 제한** 필드에 숫자 값을 입력합니다. 이 값은 모든 오디오 연결에 대해 할당할 최대 대역폭 크기(kbps 단위)입니다.</span><span class="sxs-lookup"><span data-stu-id="1c355-p104">In the **Audio limit** field, type a numeric value. This value is the maximum amount of bandwidth to allocate for all audio connections, expressed in kbps.</span></span>

7.  <span data-ttu-id="1c355-p105">**오디오 세션 제한** 필드에 숫자 값을 입력합니다. 이 값은 개별 오디오 연결에 대해 할당할 최대 대역폭 크기(kbps 단위)입니다. 이 값은 40 이상이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c355-p105">Enter a numeric value in the **Audio session limit** field. This value is the maximum amount of bandwidth to allocate for an individual audio connection, expressed in kbps. This value must be 40 or higher.</span></span>

8.  <span data-ttu-id="1c355-p106">**비디오 제한** 필드에 숫자 값을 입력합니다. 이 값은 모든 비디오 연결에 대해 할당할 최대 대역폭 크기(kbps 단위)입니다.</span><span class="sxs-lookup"><span data-stu-id="1c355-p106">Enter a numeric value in the **Video limit** field. This value is the maximum amount of bandwidth to allocate for all video connections, expressed in kbps.</span></span>

9.  <span data-ttu-id="1c355-p107">**비디오 세션 제한** 필드에 숫자 값을 입력합니다. 이 값은 개별 비디오 연결에 대해 할당할 최대 대역폭 크기(kbps 단위)입니다. 이 값은 100 이상이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c355-p107">Enter a numeric value in the **Video session limit** field. This value is the maximum amount of bandwidth to allocate for an individual video connection, expressed in kbps. This value must be 100 or higher.</span></span>

10. <span data-ttu-id="1c355-130">(선택 사항) 이름만으로는 표현할 수 없는 이 대역폭 정책 프로필에 대한 자세한 정보를 제공하려면 **설명** 필드에 값을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="1c355-130">(Optional) Type a value in the **Description** field to provide more information about this bandwidth policy profile that cannot be expressed by the name alone.</span></span>

11. <span data-ttu-id="1c355-131">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1c355-131">Click **Commit**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1c355-132">새 대역폭 정책 프로필을 만들어도 대역폭 제한이 자동으로 적용되지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1c355-132">Creating a new bandwidth policy profile does not automatically enforce bandwidth restrictions.</span></span> <span data-ttu-id="1c355-133">이렇게 하려면 먼저 정책 프로필을 사이트에 연결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c355-133">You must first associate the policy profile with a site.</span></span> <span data-ttu-id="1c355-134">정책 프로필을 사이트에 연결 하는 방법에 대 한 자세한 내용은 <A href="lync-server-2013-creating-or-modifying-network-sites.md">Lync Server 2013에서 네트워크 사이트 만들기 또는 수정을</A>참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="1c355-134">For details about how to associate a policy profile with a site, see <A href="lync-server-2013-creating-or-modifying-network-sites.md">Creating or modifying network sites in Lync Server 2013</A>.</span></span>

    
    </div>

</div>

<div>

## <a name="to-modify-a-bandwidth-policy-profile"></a><span data-ttu-id="1c355-135">대역폭 정책 프로필을 수정하려면</span><span class="sxs-lookup"><span data-stu-id="1c355-135">To modify a bandwidth policy profile</span></span>

1.  <span data-ttu-id="1c355-136">RTCUniversalServerAdmins 그룹의 구성원 인 사용자 계정 (또는 이와 동등한 사용자 권한 포함) 또는 CsAdministrator 역할이 할당 되 면 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c355-136">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="1c355-137">브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="1c355-137">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="1c355-138">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="1c355-138">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="1c355-139">왼쪽 탐색 모음에서 **네트워크 구성**을 클릭하고 **대역폭 정책**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1c355-139">In the left navigation bar, click **Network Configuration** and then click **Bandwidth Policy**.</span></span>

4.  <span data-ttu-id="1c355-140">**대역폭 정책** 페이지에서 수정할 대역폭 정책 프로필을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1c355-140">On the **Bandwidth Policy** page, click the bandwidth policy profile that you want to modify.</span></span>

5.  <span data-ttu-id="1c355-141">**편집** 메뉴에서 **자세한 정보 표시**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1c355-141">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="1c355-142">**대역폭 정책 프로필 편집** 페이지에서 필드의 값을 필요한 대로 수정합니다. 자세한 내용은 이 항목 앞부분의 "대역폭 정책 프로필을 만들려면" 섹션을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="1c355-142">On the **Edit Bandwidth Policy Profile** page, modify the fields as necessary (for details, see the "To create a bandwidth policy profile" section earlier in this topic).</span></span>

7.  <span data-ttu-id="1c355-143">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1c355-143">Click **Commit**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1c355-144">대역폭 정책 프로필을 수정하면 해당 대역폭 정책 프로필과 연결된 모든 네트워크 사이트의 대역폭 제한이 즉시 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c355-144">When you modify the bandwidth policy profile, it will immediately update the bandwidth limitations of all network sites associated with this bandwidth policy profile.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="1c355-145">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1c355-145">See Also</span></span>


[<span data-ttu-id="1c355-146">Lync Server 2013에서 네트워크 대역폭 정책 프로필 삭제</span><span class="sxs-lookup"><span data-stu-id="1c355-146">Deleting network bandwidth policy profiles in Lync Server 2013</span></span>](lync-server-2013-deleting-network-bandwidth-policy-profiles.md)  


[<span data-ttu-id="1c355-147">Lync Server 2013에서 통화 허용 제어 구성</span><span class="sxs-lookup"><span data-stu-id="1c355-147">Configure call admission control in Lync Server 2013</span></span>](lync-server-2013-configure-call-admission-control.md)  
[<span data-ttu-id="1c355-148">Get-csnetworkbandwidthpolicyprofile</span><span class="sxs-lookup"><span data-stu-id="1c355-148">New-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkBandwidthPolicyProfile)  
[<span data-ttu-id="1c355-149">Get-csnetworkbandwidthpolicyprofile</span><span class="sxs-lookup"><span data-stu-id="1c355-149">Set-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkBandwidthPolicyProfile)  
[<span data-ttu-id="1c355-150">Get-csnetworkbandwidthpolicyprofile</span><span class="sxs-lookup"><span data-stu-id="1c355-150">Get-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

