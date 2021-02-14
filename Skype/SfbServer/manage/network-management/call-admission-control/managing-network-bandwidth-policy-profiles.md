---
title: 네트워크 대역폭 정책 프로필 관리
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
description: 이 문서의 절차에 따라 네트워크 대역폭 정책 프로필을 보거나, 만들거나, 수정하거나, 삭제할 수 있습니다.
ms.openlocfilehash: 69efe657b6df775b9e647a77bef2588cafdc5b03
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816448"
---
# <a name="managing-network-bandwidth-policy-profiles-in-skype-for-business-server"></a><span data-ttu-id="89adf-103">비즈니스용 Skype 서버에서 네트워크 대역폭 정책 프로필 관리</span><span class="sxs-lookup"><span data-stu-id="89adf-103">Managing network bandwidth policy profiles in Skype for Business Server</span></span>

<span data-ttu-id="89adf-104">이 문서의 절차에 따라 네트워크 대역폭 정책 프로필을 보거나, 만들거나, 수정하거나, 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89adf-104">Use the procedures in this article to view, create, modify, or delete network bandwidth policy profiles.</span></span>

## <a name="view-network-bandwidth-policy-profile-information"></a><span data-ttu-id="89adf-105">네트워크 대역폭 정책 프로필 정보 보기</span><span class="sxs-lookup"><span data-stu-id="89adf-105">View network bandwidth policy profile information</span></span>

<span data-ttu-id="89adf-106">대역폭 정책은 CAC(통화 허용 제어)의 일부로 특정 형식에 대한 대역폭 제한을 정의하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="89adf-106">As part of call admission control (CAC), a bandwidth policy is used to define bandwidth limitations for certain modalities.</span></span> <span data-ttu-id="89adf-107">비즈니스용 Skype 서버에서는 오디오 및 비디오 한정자만 대역폭 제한을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89adf-107">In Skype for Business Server, only audio and video modalities can be assigned bandwidth limitations.</span></span> <span data-ttu-id="89adf-108">전체 대역폭 제한 및 세션 제한을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89adf-108">You can set overall bandwidth limitations and session limitations.</span></span> <span data-ttu-id="89adf-109">비즈니스용 Skype 서버 제어판을 사용하여 이러한 정책에 대한 컨테이너 프로필을 만들거나 수정하거나 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89adf-109">You can use the Skype for Business Server Control Panel to create, modify, or delete a container profile for these policies.</span></span> <span data-ttu-id="89adf-110">각 대역폭 정책 프로필은 하나 이상의 네트워크 사이트에 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89adf-110">Each bandwidth policy profile can be associated with one or more network sites.</span></span> <span data-ttu-id="89adf-111">다음 절차에 따라 대역폭 정책 프로필을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89adf-111">Use the following procedures to view a bandwidth policy profile.</span></span> 

### <a name="to-view-a-bandwidth-policy-profile"></a><span data-ttu-id="89adf-112">대역폭 정책 프로필을 보기 위해</span><span class="sxs-lookup"><span data-stu-id="89adf-112">To view a bandwidth policy profile</span></span>

1.  <span data-ttu-id="89adf-113">RTCUniversalServerAdmins 그룹의 구성원 또는 이와 동등한 사용자 권한을 가졌다는 사용자 계정 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포의 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="89adf-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="89adf-114">브라우저 창을 열고 관리 URL을 입력하여 비즈니스용 Skype 서버 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="89adf-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="89adf-115">왼쪽 탐색 모음에서 **네트워크 구성** 을 클릭하고 **대역폭 정책** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="89adf-115">In the left navigation bar, click **Network Configuration** and then click **Bandwidth Policy**.</span></span>

4.  <span data-ttu-id="89adf-116">대역폭 정책 **페이지에서** 보하려는 대역폭 정책 프로필을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="89adf-116">On the **Bandwidth Policy** page, click the bandwidth policy profile that you want to view.</span></span>

5.  <span data-ttu-id="89adf-117">**편집** 메뉴에서 **자세한 정보 표시** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="89adf-117">On the **Edit** menu, click **Show details**.</span></span>


### <a name="viewing-network-bandwidth-policy-profile-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="89adf-118">cmdlet을 사용하여 네트워크 대역폭 정책 프로필 Windows PowerShell 보기</span><span class="sxs-lookup"><span data-stu-id="89adf-118">Viewing network bandwidth policy profile information by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="89adf-119">네트워크 대역폭 프로필은 네트워크 대역폭 Windows PowerShell cmdlet을 사용하여 Get-CsNetworkBandwidthPolicyProfile 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89adf-119">Network bandwidth profiles can be viewed by using Windows PowerShell and the Get-CsNetworkBandwidthPolicyProfile cmdlet.</span></span> <span data-ttu-id="89adf-120">이 cmdlet은 비즈니스용 Skype 서버 관리 셸 또는 비즈니스용 Skype 서버 관리 셸에서 실행할 수 Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="89adf-120">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 


### <a name="to-view-network-bandwidth-policy-profile-information"></a><span data-ttu-id="89adf-121">네트워크 대역폭 정책 프로필 정보를 보기 위해</span><span class="sxs-lookup"><span data-stu-id="89adf-121">To view network bandwidth policy profile information</span></span>

  - <span data-ttu-id="89adf-122">모든 네트워크 대역폭 정책 프로필에 대한 정보를 확인하려면 비즈니스용 Skype 서버 관리 셸에 다음 명령을 입력하고 Enter를 누르고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89adf-122">To view information about all your network bandwidth policy profiles, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsNetworkBandwidthPolicyProfile
    
    <span data-ttu-id="89adf-123">그러면 다음과 같은 정보가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="89adf-123">That will return information similar to this:</span></span>
    
        Identity          : RedmondBandwidthPolicy
        BWPolicy          : {BWLimit=200;BWSessionLimit=200;
                            BWPolicyModality=Audio, 
                            BWLimit=1400;BWSessionLimit=500;
                            BWPolicyModality=Video}
        BWPolicyProfileID : RedmondBandwidthPolicy
        Description       :


<span data-ttu-id="89adf-124">자세한 내용은 [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile) cmdlet 관련 도움말 항목을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="89adf-124">For more information, see the help topic for the [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile) cmdlet.</span></span>


## <a name="create-or-modify-bandwidth-policy-profiles"></a><span data-ttu-id="89adf-125">대역폭 정책 프로필 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="89adf-125">Create or modify bandwidth policy profiles</span></span>

<span data-ttu-id="89adf-126">대역폭 정책은 CAC(통화 허용 제어)의 일부로 특정 형식에 대한 대역폭 제한을 정의하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="89adf-126">As part of call admission control (CAC), a bandwidth policy is used to define bandwidth limitations for certain modalities.</span></span> <span data-ttu-id="89adf-127">비즈니스용 Skype 서버에서는 오디오 및 비디오 한정자만 대역폭 제한을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89adf-127">In Skype for Business Server, only audio and video modalities can be assigned bandwidth limitations.</span></span> <span data-ttu-id="89adf-128">전체 대역폭 제한 및 세션 제한을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89adf-128">You can set overall bandwidth limitations and session limitations.</span></span> <span data-ttu-id="89adf-129">비즈니스용 Skype 서버 제어판을 사용하여 이러한 정책에 대한 컨테이너 프로필을 만들거나 수정하거나 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89adf-129">You can use the Skype for Business Server Control Panel to create, modify, or delete a container profile for these policies.</span></span> <span data-ttu-id="89adf-130">각 대역폭 정책 프로필은 하나 이상의 네트워크 사이트에 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89adf-130">Each bandwidth policy profile can be associated with one or more network sites.</span></span> <span data-ttu-id="89adf-131">다음 절차에 따라 대역폭 정책 프로필을 만들거나 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="89adf-131">Use the following procedures to create or modify a bandwidth policy profile.</span></span> 

### <a name="to-create-a-new-bandwidth-policy-profile"></a><span data-ttu-id="89adf-132">새 대역폭 정책 프로필을 만들려면</span><span class="sxs-lookup"><span data-stu-id="89adf-132">To create a new bandwidth policy profile</span></span>

1.  <span data-ttu-id="89adf-133">RTCUniversalServerAdmins 그룹의 구성원 또는 이와 동등한 사용자 권한을 가졌다는 사용자 계정 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포의 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="89adf-133">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="89adf-134">브라우저 창을 열고 관리 URL을 입력하여 비즈니스용 Skype 서버 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="89adf-134">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="89adf-135">왼쪽 탐색 모음에서 네트워크 구성을 **클릭한** 다음 **대역폭 정책을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="89adf-135">In the left navigation bar, click **Network Configuration**, and then click **Bandwidth Policy**.</span></span>

4.  <span data-ttu-id="89adf-136">**대역폭 정책** 페이지에서 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="89adf-136">On the **Bandwidth Policy** page, click **New**.</span></span>

5.  <span data-ttu-id="89adf-p104">**새 대역폭 정책 프로필** 에서 **이름** 필드에 이름을 입력합니다. 이 이름은 모든 대역폭 정책 프로필에서 고유해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="89adf-p104">In **New Bandwidth Policy Profile**, type a name in the **Name** field. This name must be unique among all bandwidth policy profiles.</span></span>

6.  <span data-ttu-id="89adf-p105">**오디오 제한** 필드에 숫자 값을 입력합니다. 이 값은 모든 오디오 연결에 대해 할당할 최대 대역폭 크기(kbps 단위)입니다.</span><span class="sxs-lookup"><span data-stu-id="89adf-p105">In the **Audio limit** field, type a numeric value. This value is the maximum amount of bandwidth to allocate for all audio connections, expressed in kbps.</span></span>

7.  <span data-ttu-id="89adf-p106">**오디오 세션 제한** 필드에 숫자 값을 입력합니다. 이 값은 개별 오디오 연결에 대해 할당할 최대 대역폭 크기(kbps 단위)입니다. 이 값은 40 이상이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="89adf-p106">Enter a numeric value in the **Audio session limit** field. This value is the maximum amount of bandwidth to allocate for an individual audio connection, expressed in kbps. This value must be 40 or higher.</span></span>

8.  <span data-ttu-id="89adf-p107">**비디오 제한** 필드에 숫자 값을 입력합니다. 이 값은 모든 비디오 연결에 대해 할당할 최대 대역폭 크기(kbps 단위)입니다.</span><span class="sxs-lookup"><span data-stu-id="89adf-p107">Enter a numeric value in the **Video limit** field. This value is the maximum amount of bandwidth to allocate for all video connections, expressed in kbps.</span></span>

9.  <span data-ttu-id="89adf-p108">**비디오 세션 제한** 필드에 숫자 값을 입력합니다. 이 값은 개별 비디오 연결에 대해 할당할 최대 대역폭 크기(kbps 단위)입니다. 이 값은 100 이상이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="89adf-p108">Enter a numeric value in the **Video session limit** field. This value is the maximum amount of bandwidth to allocate for an individual video connection, expressed in kbps. This value must be 100 or higher.</span></span>

10. <span data-ttu-id="89adf-149">(선택 사항) 이름만으로는 표현할 수 없는 이 대역폭 정책 프로필에 대한 자세한 정보를 제공하려면 **설명** 필드에 값을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="89adf-149">(Optional) Type a value in the **Description** field to provide more information about this bandwidth policy profile that cannot be expressed by the name alone.</span></span>

11. <span data-ttu-id="89adf-150">**커밋** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="89adf-150">Click **Commit**.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="89adf-151">새 대역폭 정책 프로필을 만들어도 대역폭 제한이 자동으로 적용되지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="89adf-151">Creating a new bandwidth policy profile does not automatically enforce bandwidth restrictions.</span></span> <span data-ttu-id="89adf-152">이렇게 하려면 먼저 정책 프로필을 사이트에 연결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="89adf-152">You must first associate the policy profile with a site.</span></span> 


### <a name="to-modify-a-bandwidth-policy-profile"></a><span data-ttu-id="89adf-153">대역폭 정책 프로필을 수정하려면</span><span class="sxs-lookup"><span data-stu-id="89adf-153">To modify a bandwidth policy profile</span></span>

1.  <span data-ttu-id="89adf-154">RTCUniversalServerAdmins 그룹의 구성원 또는 이와 동등한 사용자 권한을 가졌다는 사용자 계정 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포의 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="89adf-154">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="89adf-155">브라우저 창을 열고 관리 URL을 입력하여 비즈니스용 Skype 서버 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="89adf-155">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="89adf-156">왼쪽 탐색 모음에서 네트워크 구성을 **클릭한** 다음 **대역폭 정책을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="89adf-156">In the left navigation bar, click **Network Configuration**, and then click **Bandwidth Policy**.</span></span>

4.  <span data-ttu-id="89adf-157">**대역폭 정책** 페이지에서 수정할 대역폭 정책 프로필을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="89adf-157">On the **Bandwidth Policy** page, click the bandwidth policy profile that you want to modify.</span></span>

5.  <span data-ttu-id="89adf-158">**편집** 메뉴에서 **자세한 정보 표시** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="89adf-158">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="89adf-159">대역폭 **정책** 프로필 편집 페이지에서 필요한 경우 필드를 수정합니다(자세한 내용은 새 대역폭 정책 프로필을 만들 [때](#to-create-a-new-bandwidth-policy-profile)참조).</span><span class="sxs-lookup"><span data-stu-id="89adf-159">On the **Edit Bandwidth Policy Profile** page, modify the fields as necessary (for details, see [To create a new bandwidth policy profile](#to-create-a-new-bandwidth-policy-profile)).</span></span>

7.  <span data-ttu-id="89adf-160">**커밋** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="89adf-160">Click **Commit**.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="89adf-161">대역폭 정책 프로필을 수정하면 해당 대역폭 정책 프로필과 연결된 모든 네트워크 사이트의 대역폭 제한이 즉시 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="89adf-161">When you modify the bandwidth policy profile, it will immediately update the bandwidth limitations of all network sites associated with this bandwidth policy profile.</span></span>

  
## <a name="delete-network-bandwidth-policy-profiles"></a><span data-ttu-id="89adf-162">네트워크 대역폭 정책 프로필 삭제</span><span class="sxs-lookup"><span data-stu-id="89adf-162">Delete network bandwidth policy profiles</span></span>

<span data-ttu-id="89adf-163">대역폭 정책은 CAC(통화 허용 제어)의 일부로 특정 형식에 대한 대역폭 제한을 정의하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="89adf-163">As part of call admission control (CAC), a bandwidth policy is used to define bandwidth limitations for certain modalities.</span></span> <span data-ttu-id="89adf-164">비즈니스용 Skype 서버에서는 오디오 및 비디오 한정자만 대역폭 제한을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89adf-164">In Skype for Business Server, only audio and video modalities can be assigned bandwidth limitations.</span></span> <span data-ttu-id="89adf-165">전체 대역폭 제한 및 세션 제한을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89adf-165">You can set overall bandwidth limitations and session limitations.</span></span> <span data-ttu-id="89adf-166">비즈니스용 Skype 서버 제어판을 사용하여 이러한 정책에 대한 컨테이너 프로필을 만들거나 수정하거나 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89adf-166">You can use the Skype for Business Server Control Panel to create, modify, or delete a container profile for these policies.</span></span> <span data-ttu-id="89adf-167">다음 절차에 따라 네트워크 대역폭 정책 프로필을 삭제하십시오.</span><span class="sxs-lookup"><span data-stu-id="89adf-167">Use the following procedures to delete a network bandwidth policy profiles.</span></span> 

### <a name="to-delete-a-bandwidth-policy-profile"></a><span data-ttu-id="89adf-168">대역폭 정책 프로필을 삭제하려면</span><span class="sxs-lookup"><span data-stu-id="89adf-168">To delete a bandwidth policy profile</span></span>

1.  <span data-ttu-id="89adf-169">RTCUniversalServerAdmins 그룹의 구성원 또는 이와 동등한 사용자 권한을 가졌다는 사용자 계정 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포의 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="89adf-169">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="89adf-170">브라우저 창을 열고 관리 URL을 입력하여 비즈니스용 Skype 서버 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="89adf-170">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="89adf-171">왼쪽 탐색 모음에서 네트워크 구성을 **클릭한** 다음 **대역폭 정책을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="89adf-171">In the left navigation bar, click **Network Configuration**, and then click **Bandwidth Policy**.</span></span>

4.  <span data-ttu-id="89adf-172">**대역폭 정책** 페이지에서 삭제하려는 대역폭 정책 프로필을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="89adf-172">On the **Bandwidth Policy** page, click the bandwidth policy profile that you want to delete.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="89adf-p111">한 번에 둘 이상의 프로필을 삭제할 수 있습니다. 이렇게 하려면 Ctrl 키를 누른 상태에서 여러 프로필을 선택합니다. 또는 모든 프로필을 선택하려면 **편집** 메뉴에서 **모두 선택** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="89adf-p111">You can delete more than one profile at a time. To do this, press CTRL and select multiple profiles while holding down the CTRL key. Or, to select all profiles, click **Select all** on the **Edit** menu.</span></span>

5.  <span data-ttu-id="89adf-176">**편집** 메뉴에서 **삭제** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="89adf-176">On the **Edit** menu, click **Delete**.</span></span>
   

    > [!WARNING]  
    > <span data-ttu-id="89adf-177">네트워크 사이트에 연결된 대역폭 정책 프로필은 삭제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="89adf-177">You cannot delete a bandwidth policy profile that is associated with a network site.</span></span> <span data-ttu-id="89adf-178">프로필을 삭제하려면 먼저 네트워크 사이트와의 연결을 제거해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="89adf-178">You must first remove the association with the network site before you can delete the profile.</span></span> 


## <a name="see-also"></a><span data-ttu-id="89adf-179">참고 항목</span><span class="sxs-lookup"><span data-stu-id="89adf-179">See Also</span></span>

[<span data-ttu-id="89adf-180">사이트에 대한 통화 제어 관리</span><span class="sxs-lookup"><span data-stu-id="89adf-180">Managing call admission control for sites</span></span>](managing-call-admission-control-for-sites.md)
 
[<span data-ttu-id="89adf-181">New-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="89adf-181">New-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkBandwidthPolicyProfile)  

[<span data-ttu-id="89adf-182">Set-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="89adf-182">Set-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkBandwidthPolicyProfile)  

[<span data-ttu-id="89adf-183">Get-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="89adf-183">Get-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)  

[<span data-ttu-id="89adf-184">Remove-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="89adf-184">Remove-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkBandwidthPolicyProfile)  
  

