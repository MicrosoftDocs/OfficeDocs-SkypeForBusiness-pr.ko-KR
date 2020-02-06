---
title: 네트워크 대역폭 정책 프로필 관리
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 이 문서의 절차를 사용 하 여 네트워크 대역폭 정책 프로필을 보고, 만들고, 수정 하 고, 삭제할 수 있습니다.
ms.openlocfilehash: a9203c0935673e0dfd12d052876f06583c7c92c8
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817507"
---
# <a name="managing-network-bandwidth-policy-profiles-in-skype-for-business-server"></a><span data-ttu-id="54eca-103">비즈니스용 Skype 서버에서 네트워크 대역폭 정책 프로필 관리</span><span class="sxs-lookup"><span data-stu-id="54eca-103">Managing network bandwidth policy profiles in Skype for Business Server</span></span>

<span data-ttu-id="54eca-104">이 문서의 절차를 사용 하 여 네트워크 대역폭 정책 프로필을 보고, 만들고, 수정 하 고, 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54eca-104">Use the procedures in this article to view, create, modify, or delete network bandwidth policy profiles.</span></span>

## <a name="view-network-bandwidth-policy-profile-information"></a><span data-ttu-id="54eca-105">네트워크 대역폭 정책 프로필 정보 보기</span><span class="sxs-lookup"><span data-stu-id="54eca-105">View network bandwidth policy profile information</span></span>

<span data-ttu-id="54eca-106">호출 허용 제어 (CAC)의 일부로 대역폭 정책은 특정 형식을 대역폭 제한을 정의 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="54eca-106">As part of call admission control (CAC), a bandwidth policy is used to define bandwidth limitations for certain modalities.</span></span> <span data-ttu-id="54eca-107">비즈니스용 Skype 서버에서 오디오 및 비디오 형식을 대역폭 제한을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54eca-107">In Skype for Business Server, only audio and video modalities can be assigned bandwidth limitations.</span></span> <span data-ttu-id="54eca-108">전체 대역폭 제한 및 세션 제한을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54eca-108">You can set overall bandwidth limitations and session limitations.</span></span> <span data-ttu-id="54eca-109">비즈니스용 Skype Server 제어판을 사용 하 여 이러한 정책에 대 한 컨테이너 프로필을 만들거나 수정 하거나 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54eca-109">You can use the Skype for Business Server Control Panel to create, modify, or delete a container profile for these policies.</span></span> <span data-ttu-id="54eca-110">각 대역폭 정책 프로필을 하나 이상의 네트워크 사이트와 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54eca-110">Each bandwidth policy profile can be associated with one or more network sites.</span></span> <span data-ttu-id="54eca-111">다음 절차를 사용 하 여 대역폭 정책 프로필을 봅니다.</span><span class="sxs-lookup"><span data-stu-id="54eca-111">Use the following procedures to view a bandwidth policy profile.</span></span> 

### <a name="to-view-a-bandwidth-policy-profile"></a><span data-ttu-id="54eca-112">대역폭 정책 프로필을 보려면</span><span class="sxs-lookup"><span data-stu-id="54eca-112">To view a bandwidth policy profile</span></span>

1.  <span data-ttu-id="54eca-113">RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsAdministrator 역할에 할당 된 경우 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="54eca-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="54eca-114">브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="54eca-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="54eca-115">왼쪽 탐색 모음에서 **네트워크 구성을** 클릭 한 다음 **대역폭 정책을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="54eca-115">In the left navigation bar, click **Network Configuration** and then click **Bandwidth Policy**.</span></span>

4.  <span data-ttu-id="54eca-116">**대역폭 정책** 페이지에서 보려는 대역폭 정책 프로필을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="54eca-116">On the **Bandwidth Policy** page, click the bandwidth policy profile that you want to view.</span></span>

5.  <span data-ttu-id="54eca-117">**편집** 메뉴에서 **세부 정보 표시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="54eca-117">On the **Edit** menu, click **Show details**.</span></span>


### <a name="viewing-network-bandwidth-policy-profile-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="54eca-118">Windows PowerShell cmdlet을 사용 하 여 네트워크 대역폭 정책 프로필 정보 보기</span><span class="sxs-lookup"><span data-stu-id="54eca-118">Viewing network bandwidth policy profile information by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="54eca-119">네트워크 대역폭 프로필은 Windows PowerShell 및 CsNetworkBandwidthPolicyProfile cmdlet을 사용 하 여 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54eca-119">Network bandwidth profiles can be viewed by using Windows PowerShell and the Get-CsNetworkBandwidthPolicyProfile cmdlet.</span></span> <span data-ttu-id="54eca-120">이 cmdlet은 비즈니스용 Skype 서버 관리 셸에서 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54eca-120">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 


### <a name="to-view-network-bandwidth-policy-profile-information"></a><span data-ttu-id="54eca-121">네트워크 대역폭 정책 프로필 정보를 보려면</span><span class="sxs-lookup"><span data-stu-id="54eca-121">To view network bandwidth policy profile information</span></span>

  - <span data-ttu-id="54eca-122">모든 네트워크 대역폭 정책 프로필에 대 한 정보를 보려면 비즈니스용 Skype 서버 관리 셸에서 다음 명령을 입력 한 다음 enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="54eca-122">To view information about all your network bandwidth policy profiles, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsNetworkBandwidthPolicyProfile
    
    <span data-ttu-id="54eca-123">이는 다음과 같은 정보를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="54eca-123">That will return information similar to this:</span></span>
    
        Identity          : RedmondBandwidthPolicy
        BWPolicy          : {BWLimit=200;BWSessionLimit=200;
                            BWPolicyModality=Audio, 
                            BWLimit=1400;BWSessionLimit=500;
                            BWPolicyModality=Video}
        BWPolicyProfileID : RedmondBandwidthPolicy
        Description       :


<span data-ttu-id="54eca-124">자세한 내용은 Get-help cmdlet에 대 한 도움말 항목 [CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="54eca-124">For more information, see the help topic for the [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile) cmdlet.</span></span>


## <a name="create-or-modify-bandwidth-policy-profiles"></a><span data-ttu-id="54eca-125">대역폭 정책 프로필 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="54eca-125">Create or modify bandwidth policy profiles</span></span>

<span data-ttu-id="54eca-126">호출 허용 제어 (CAC)의 일부로 대역폭 정책은 특정 형식을 대역폭 제한을 정의 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="54eca-126">As part of call admission control (CAC), a bandwidth policy is used to define bandwidth limitations for certain modalities.</span></span> <span data-ttu-id="54eca-127">비즈니스용 Skype 서버에서 오디오 및 비디오 형식을 대역폭 제한을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54eca-127">In Skype for Business Server, only audio and video modalities can be assigned bandwidth limitations.</span></span> <span data-ttu-id="54eca-128">전체 대역폭 제한 및 세션 제한을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54eca-128">You can set overall bandwidth limitations and session limitations.</span></span> <span data-ttu-id="54eca-129">비즈니스용 Skype Server 제어판을 사용 하 여 이러한 정책에 대 한 컨테이너 프로필을 만들거나 수정 하거나 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54eca-129">You can use the Skype for Business Server Control Panel to create, modify, or delete a container profile for these policies.</span></span> <span data-ttu-id="54eca-130">각 대역폭 정책 프로필을 하나 이상의 네트워크 사이트와 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54eca-130">Each bandwidth policy profile can be associated with one or more network sites.</span></span> <span data-ttu-id="54eca-131">다음 절차를 사용 하 여 대역폭 정책 프로필을 만들거나 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="54eca-131">Use the following procedures to create or modify a bandwidth policy profile.</span></span> 

### <a name="to-create-a-new-bandwidth-policy-profile"></a><span data-ttu-id="54eca-132">새 대역폭 정책 프로필을 만들려면</span><span class="sxs-lookup"><span data-stu-id="54eca-132">To create a new bandwidth policy profile</span></span>

1.  <span data-ttu-id="54eca-133">RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsAdministrator 역할에 할당 된 경우 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="54eca-133">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="54eca-134">브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="54eca-134">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="54eca-135">왼쪽 탐색 모음에서 **네트워크 구성을**클릭 한 다음 **대역폭 정책을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="54eca-135">In the left navigation bar, click **Network Configuration**, and then click **Bandwidth Policy**.</span></span>

4.  <span data-ttu-id="54eca-136">**대역폭 정책** 페이지에서 **새로 만들기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="54eca-136">On the **Bandwidth Policy** page, click **New**.</span></span>

5.  <span data-ttu-id="54eca-137">**새 대역폭 정책 프로필**의 **이름** 필드에 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="54eca-137">In **New Bandwidth Policy Profile**, type a name in the **Name** field.</span></span> <span data-ttu-id="54eca-138">이 이름은 모든 대역폭 정책 프로필에서 고유 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="54eca-138">This name must be unique among all bandwidth policy profiles.</span></span>

6.  <span data-ttu-id="54eca-139">**오디오 제한** 필드에 숫자 값을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="54eca-139">In the **Audio limit** field, type a numeric value.</span></span> <span data-ttu-id="54eca-140">이 값은 모든 오디오 연결에 할당할 수 있는 대역폭의 최대 양 (kbps로 표시 됨)입니다.</span><span class="sxs-lookup"><span data-stu-id="54eca-140">This value is the maximum amount of bandwidth to allocate for all audio connections, expressed in kbps.</span></span>

7.  <span data-ttu-id="54eca-141">**오디오 세션 제한** 필드에 숫자 값을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="54eca-141">Enter a numeric value in the **Audio session limit** field.</span></span> <span data-ttu-id="54eca-142">이 값은 kbps로 표시 되는 개별 오디오 연결에 할당할 수 있는 대역폭의 최대 양입니다.</span><span class="sxs-lookup"><span data-stu-id="54eca-142">This value is the maximum amount of bandwidth to allocate for an individual audio connection, expressed in kbps.</span></span> <span data-ttu-id="54eca-143">이 값은 40 이상 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="54eca-143">This value must be 40 or higher.</span></span>

8.  <span data-ttu-id="54eca-144">**비디오 제한** 필드에 숫자 값을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="54eca-144">Enter a numeric value in the **Video limit** field.</span></span> <span data-ttu-id="54eca-145">이 값은 모든 비디오 연결에 할당할 수 있는 대역폭의 최대 양 (kbps)입니다.</span><span class="sxs-lookup"><span data-stu-id="54eca-145">This value is the maximum amount of bandwidth to allocate for all video connections, expressed in kbps.</span></span>

9.  <span data-ttu-id="54eca-146">**비디오 세션 제한** 필드에 숫자 값을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="54eca-146">Enter a numeric value in the **Video session limit** field.</span></span> <span data-ttu-id="54eca-147">이 값은 kbps로 표시 되는 개별 비디오 연결에 할당할 수 있는 대역폭의 최대 양입니다.</span><span class="sxs-lookup"><span data-stu-id="54eca-147">This value is the maximum amount of bandwidth to allocate for an individual video connection, expressed in kbps.</span></span> <span data-ttu-id="54eca-148">이 값은 100 이상 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="54eca-148">This value must be 100 or higher.</span></span>

10. <span data-ttu-id="54eca-149">) 이름 만으로 표현할 수 없는이 대역폭 정책 프로필에 대 한 자세한 정보를 제공 하려면 **설명** 필드에 값을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="54eca-149">(Optional) Type a value in the **Description** field to provide more information about this bandwidth policy profile that cannot be expressed by the name alone.</span></span>

11. <span data-ttu-id="54eca-150">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="54eca-150">Click **Commit**.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="54eca-151">새 대역폭 정책 프로필을 만들면 자동으로 대역폭 제한이 적용 되지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="54eca-151">Creating a new bandwidth policy profile does not automatically enforce bandwidth restrictions.</span></span> <span data-ttu-id="54eca-152">먼저 정책 프로필을 사이트와 연결 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="54eca-152">You must first associate the policy profile with a site.</span></span> 


### <a name="to-modify-a-bandwidth-policy-profile"></a><span data-ttu-id="54eca-153">대역폭 정책 프로필을 수정 하려면</span><span class="sxs-lookup"><span data-stu-id="54eca-153">To modify a bandwidth policy profile</span></span>

1.  <span data-ttu-id="54eca-154">RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsAdministrator 역할에 할당 된 경우 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="54eca-154">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="54eca-155">브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="54eca-155">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="54eca-156">왼쪽 탐색 모음에서 **네트워크 구성을**클릭 한 다음 **대역폭 정책을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="54eca-156">In the left navigation bar, click **Network Configuration**, and then click **Bandwidth Policy**.</span></span>

4.  <span data-ttu-id="54eca-157">**대역폭 정책** 페이지에서 수정 하려는 대역폭 정책 프로필을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="54eca-157">On the **Bandwidth Policy** page, click the bandwidth policy profile that you want to modify.</span></span>

5.  <span data-ttu-id="54eca-158">**편집** 메뉴에서 **세부 정보 표시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="54eca-158">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="54eca-159">**대역폭 정책 프로필 편집** 페이지에서 필요에 따라 필드를 수정 합니다 (자세한 내용은 [새 대역폭 정책 프로필 만들기](#to-create-a-new-bandwidth-policy-profile)참조).</span><span class="sxs-lookup"><span data-stu-id="54eca-159">On the **Edit Bandwidth Policy Profile** page, modify the fields as necessary (for details, see [To create a new bandwidth policy profile](#to-create-a-new-bandwidth-policy-profile)).</span></span>

7.  <span data-ttu-id="54eca-160">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="54eca-160">Click **Commit**.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="54eca-161">대역폭 정책 프로필을 수정 하면이 대역폭 정책 프로필에 연결 된 모든 네트워크 사이트의 대역폭 제한이 즉시 업데이트 됩니다.</span><span class="sxs-lookup"><span data-stu-id="54eca-161">When you modify the bandwidth policy profile, it will immediately update the bandwidth limitations of all network sites associated with this bandwidth policy profile.</span></span>

  
## <a name="delete-network-bandwidth-policy-profiles"></a><span data-ttu-id="54eca-162">네트워크 대역폭 정책 프로필 삭제</span><span class="sxs-lookup"><span data-stu-id="54eca-162">Delete network bandwidth policy profiles</span></span>

<span data-ttu-id="54eca-163">호출 허용 제어 (CAC)의 일부로 대역폭 정책은 특정 형식을 대역폭 제한을 정의 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="54eca-163">As part of call admission control (CAC), a bandwidth policy is used to define bandwidth limitations for certain modalities.</span></span> <span data-ttu-id="54eca-164">비즈니스용 Skype 서버에서 오디오 및 비디오 형식을 대역폭 제한을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54eca-164">In Skype for Business Server, only audio and video modalities can be assigned bandwidth limitations.</span></span> <span data-ttu-id="54eca-165">전체 대역폭 제한 및 세션 제한을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54eca-165">You can set overall bandwidth limitations and session limitations.</span></span> <span data-ttu-id="54eca-166">비즈니스용 Skype Server 제어판을 사용 하 여 이러한 정책에 대 한 컨테이너 프로필을 만들거나 수정 하거나 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54eca-166">You can use the Skype for Business Server Control Panel to create, modify, or delete a container profile for these policies.</span></span> <span data-ttu-id="54eca-167">네트워크 대역폭 정책 프로필을 삭제 하려면 다음 절차를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="54eca-167">Use the following procedures to delete a network bandwidth policy profiles.</span></span> 

### <a name="to-delete-a-bandwidth-policy-profile"></a><span data-ttu-id="54eca-168">대역폭 정책 프로필을 삭제 하려면</span><span class="sxs-lookup"><span data-stu-id="54eca-168">To delete a bandwidth policy profile</span></span>

1.  <span data-ttu-id="54eca-169">RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsAdministrator 역할에 할당 된 경우 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="54eca-169">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="54eca-170">브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="54eca-170">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="54eca-171">왼쪽 탐색 모음에서 **네트워크 구성을**클릭 한 다음 **대역폭 정책을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="54eca-171">In the left navigation bar, click **Network Configuration**, and then click **Bandwidth Policy**.</span></span>

4.  <span data-ttu-id="54eca-172">**대역폭 정책** 페이지에서 삭제 하려는 대역폭 정책 프로필을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="54eca-172">On the **Bandwidth Policy** page, click the bandwidth policy profile that you want to delete.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="54eca-173">한 번에 여러 프로필을 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54eca-173">You can delete more than one profile at a time.</span></span> <span data-ttu-id="54eca-174">이 작업을 수행 하려면 ctrl 키를 누른 채 여러 프로필을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="54eca-174">To do this, press CTRL and select multiple profiles while holding down the CTRL key.</span></span> <span data-ttu-id="54eca-175">또는 모든 프로필을 선택 하려면 **편집** 메뉴에서 **모두 선택을** 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="54eca-175">Or, to select all profiles, click **Select all** on the **Edit** menu.</span></span>

5.  <span data-ttu-id="54eca-176">**편집** 메뉴에서 **삭제**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="54eca-176">On the **Edit** menu, click **Delete**.</span></span>
   

    > [!WARNING]  
    > <span data-ttu-id="54eca-177">네트워크 사이트와 연결 된 대역폭 정책 프로필은 삭제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="54eca-177">You cannot delete a bandwidth policy profile that is associated with a network site.</span></span> <span data-ttu-id="54eca-178">프로필을 삭제 하려면 먼저 네트워크 사이트와의 연결을 제거 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="54eca-178">You must first remove the association with the network site before you can delete the profile.</span></span> 


## <a name="see-also"></a><span data-ttu-id="54eca-179">참고 항목</span><span class="sxs-lookup"><span data-stu-id="54eca-179">See Also</span></span>

[<span data-ttu-id="54eca-180">사이트에 대 한 통화 허용 제어 관리</span><span class="sxs-lookup"><span data-stu-id="54eca-180">Managing call admission control for sites</span></span>](managing-call-admission-control-for-sites.md)
 
[<span data-ttu-id="54eca-181">새로운 CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="54eca-181">New-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkBandwidthPolicyProfile)  

[<span data-ttu-id="54eca-182">Set-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="54eca-182">Set-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkBandwidthPolicyProfile)  

[<span data-ttu-id="54eca-183">Get-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="54eca-183">Get-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)  

[<span data-ttu-id="54eca-184">제거-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="54eca-184">Remove-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkBandwidthPolicyProfile)  
  

