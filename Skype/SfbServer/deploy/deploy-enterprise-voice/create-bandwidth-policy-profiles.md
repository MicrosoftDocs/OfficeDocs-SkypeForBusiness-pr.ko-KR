---
title: 비즈니스용 Skype 서버에서 대역폭 정책 프로필 만들기
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a71881ef-b04a-465e-9abb-0577bfd182f3
description: 비즈니스용 Skype 서버에서 통화 Enterprise Voice 제어에 사용되는 대역폭 정책을 만들거나 수정합니다.
ms.openlocfilehash: ac80ebb8b61a763efc0077f267a024a21a359b5d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49824849"
---
# <a name="create-bandwidth-policy-profiles-in-skype-for-business-server"></a><span data-ttu-id="9aa9e-103">비즈니스용 Skype 서버에서 대역폭 정책 프로필 만들기</span><span class="sxs-lookup"><span data-stu-id="9aa9e-103">Create bandwidth policy profiles in Skype for Business Server</span></span> 
 
<span data-ttu-id="9aa9e-104">비즈니스용 Skype 서버에서 통화 Enterprise Voice 제어에 사용되는 대역폭 정책을 만들거나 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="9aa9e-104">Create or modify bandwidth policies, which are used by Enterprise Voice call admission control in Skype for Business Server.</span></span> 
  
<span data-ttu-id="9aa9e-105">대역폭 정책은 실시간 오디오 및 비디오의 대역폭 사용 제한을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="9aa9e-105">Bandwidth policies define limitations on bandwidth usage for real-time audio and video modalities.</span></span> <span data-ttu-id="9aa9e-106">대역폭 정책은 통화 액세스 제어를 위해 여러 네트워크 사이트에 적용할 수 있는bandwidth 정책 프로필에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="9aa9e-106">Bandwidth policies are applied tobandwidth policy profiles, which can be applied to multiple network sites for call admission control.</span></span>
  
<span data-ttu-id="9aa9e-107">CAC 배포에서 설정해야 하는 대역폭 제한에 대한 지침은 비즈니스용 Skype 서버의 통화 제한 [계획(Plan for call admission control)을 참조하세요.](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md)</span><span class="sxs-lookup"><span data-stu-id="9aa9e-107">For guidelines about what bandwidth limits you should set in your CAC deployment, see [Plan for call admission control in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md).</span></span>
  
<span data-ttu-id="9aa9e-p102">다음 절차에서 만들어진 예 정책은 전체 오디오 트래픽, 개별 오디오 세션, 전체 비디오 트래픽 및 개별 비디오 세션에 대한 제한을 설정합니다. 예를 들어 5Mb_Link 대역폭 정책 프로필에서는 다음과 같은 제한이 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="9aa9e-p102">The example policies created in the following procedure set limits for overall audio traffic, individual audio sessions, overall video traffic, and individual video sessions. For example, the 5Mb_Link bandwidth policy profile sets the following limits:</span></span> 
  
- <span data-ttu-id="9aa9e-110">오디오 제한: 2,000kbps</span><span class="sxs-lookup"><span data-stu-id="9aa9e-110">Audio Limit: 2,000 kbps</span></span>
    
- <span data-ttu-id="9aa9e-111">오디오 세션 제한: 200kbps</span><span class="sxs-lookup"><span data-stu-id="9aa9e-111">Audio Session Limit: 200 kbps</span></span>
    
- <span data-ttu-id="9aa9e-112">비디오 제한: 1,400kbps</span><span class="sxs-lookup"><span data-stu-id="9aa9e-112">Video Limit: 1,400 kbps</span></span>
    
- <span data-ttu-id="9aa9e-113">비디오 세션 제한: 700kbps</span><span class="sxs-lookup"><span data-stu-id="9aa9e-113">Video Session Limit: 700 kbps</span></span>
    
> [!NOTE]
> <span data-ttu-id="9aa9e-p103">최소 오디오 세션 제한 값은 40kbps이며, 최소 비디오 세션 제한 값은 100kbps입니다.</span><span class="sxs-lookup"><span data-stu-id="9aa9e-p103">The minimum Audio Session Limit value is 40 kbps. The minimum Video Session Limit value is 100 kbps.</span></span> 
  
### <a name="to-create-bandwidth-policy-profiles-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="9aa9e-116">비즈니스용 Skype 서버 관리 셸을 사용하여 대역폭 정책 프로필을 만들하려면</span><span class="sxs-lookup"><span data-stu-id="9aa9e-116">To create bandwidth policy profiles by using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="9aa9e-117">비즈니스용 Skype 서버 관리 셸 시작: **시작,** **모든** 프로그램, 비즈니스용 **Skype 2015,** 비즈니스용 Skype 서버 관리 셸을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="9aa9e-117">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="9aa9e-118">만들려는 각 대역폭 정책 프로필에 대해 New-CsNetworkBandwidthPolicyProfile cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="9aa9e-118">For each bandwidth policy profile that you want to create, run the New-CsNetworkBandwidthPolicyProfile cmdlet.</span></span> <span data-ttu-id="9aa9e-119">예를 들어 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="9aa9e-119">For example, run:</span></span>
    
   ```powershell
   New-CsNetworkBandwidthPolicyProfile -Identity 5Mb_Link -Description "BW profile for 5Mb links" -AudioBWLimit 2000 -AudioBWSessionLimit 200 -VideoBWLimit 1400   -VideoBWSessionLimit 700
   ```

   ```powershell
   New-CsNetworkBandwidthPolicyProfile -Identity 10Mb_Link -Description "BW profile for 10Mb links" -AudioBWLimit 4000 -AudioBWSessionLimit 200 -VideoBWLimit 2800 -VideoBWSessionLimit 700
   ```

   ```powershell
   New-CsNetworkBandwidthPolicyProfile -Identity 50Mb_Link -Description "BW profile for 50Mb links" -AudioBWLimit 20000 -AudioBWSessionLimit 200 -VideoBWLimit 14000 -VideoBWSessionLimit 700
   ```

   ```powershell
   New-CsNetworkBandwidthPolicyProfile -Identity 25Mb_Link -Description "BW profile for 25Mb links" -AudioBWLimit 10000 -AudioBWSessionLimit 200 -VideoBWLimit 7000 -VideoBWSessionLimit 700
   ```

### <a name="to-create-bandwidth-policy-profiles-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="9aa9e-120">비즈니스용 Skype 서버 제어판을 사용하여 대역폭 정책 프로필을 만들하려면</span><span class="sxs-lookup"><span data-stu-id="9aa9e-120">To create bandwidth policy profiles by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="9aa9e-121">비즈니스용 Skype 서버 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="9aa9e-121">Open Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="9aa9e-122">왼쪽 탐색 모음에서 **네트워크 구성** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9aa9e-122">In the left navigation bar, click **Network Configuration**.</span></span>
    
3. <span data-ttu-id="9aa9e-123">**정책 프로필** 탐색 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9aa9e-123">Click the **Policy Profile** navigation button.</span></span>
    
4. <span data-ttu-id="9aa9e-124">**새로 만들기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9aa9e-124">Click **New**.</span></span>
    
5. <span data-ttu-id="9aa9e-125">**새 프로필 정책** 페이지에서 **이름** 을 클릭한 후 대역폭 정책 프로필에 대한 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="9aa9e-125">On the **New Policy Profile** page, click **Name** and then type a name for the bandwidth policy profile.</span></span>
    
6. <span data-ttu-id="9aa9e-126">**오디오 제한** 을 클릭하고 결합된 모든 오디오 세션에 허용할 최대 kbps를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="9aa9e-126">Click **Audio limit**, and then type in the maximum number of kbps to allow for all audio sessions combined.</span></span>
    
7. <span data-ttu-id="9aa9e-127">**오디오 세션 제한** 을 클릭하고 각 개별 오디오 세션에 허용할 최대 kbps를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="9aa9e-127">Click **Audio session limit**, and then type in the maximum number of kbps to allow for each individual audio session.</span></span>
    
8. <span data-ttu-id="9aa9e-128">**비디오 제한** 을 클릭하고 결합된 모든 비디오 세션에 허용할 최대 kbps를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="9aa9e-128">Click **Video limit**, and then type in the maximum number of kbps to allow for all video sessions combined.</span></span>
    
9. <span data-ttu-id="9aa9e-129">**비디오 세션 제한** 을 클릭하고 각 개별 비디오 세션에 허용할 최대 kbps를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="9aa9e-129">Click **Video session limit**, and then type in the maximum number of kbps to allow for each individual video session.</span></span>
    
10. <span data-ttu-id="9aa9e-130">경우에 따라 **설명** 을 클릭하고 이 대역폭 정책 프로필을 설명하는 추가 정보를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="9aa9e-130">Optionally, click **Description**, and then type additional information to describe this bandwidth policy profile.</span></span>
    
11. <span data-ttu-id="9aa9e-131">**커밋** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9aa9e-131">Click **Commit**.</span></span>
    
12. <span data-ttu-id="9aa9e-132">토폴로지에 대한 대역폭 정책 프로필 만들기를 종료하려면 다른 대역폭 정책 프로필에 대한 설정을 사용하여 4-11단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="9aa9e-132">To finish creating bandwidth policy profiles for your topology, repeat steps 4 through 11 with settings for other bandwidth policy profiles.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="9aa9e-133">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9aa9e-133">See also</span></span>

[<span data-ttu-id="9aa9e-134">New-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="9aa9e-134">New-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csnetworkbandwidthpolicyprofile?view=skype-ps)
  
[<span data-ttu-id="9aa9e-135">Get-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="9aa9e-135">Get-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csnetworkbandwidthpolicyprofile?view=skype-ps)
  
[<span data-ttu-id="9aa9e-136">Set-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="9aa9e-136">Set-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csnetworkbandwidthpolicyprofile?view=skype-ps)
  
[<span data-ttu-id="9aa9e-137">Remove-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="9aa9e-137">Remove-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkbandwidthpolicyprofile?view=skype-ps)
