---
title: 비즈니스용 Skype 서버에서 대역폭 정책 프로필 만들기
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a71881ef-b04a-465e-9abb-0577bfd182f3
description: 비즈니스용 Skype 서버에서 엔터프라이즈 음성 통화 허용 제어에 사용 되는 대역폭 정책을 만들거나 수정 합니다.
ms.openlocfilehash: c7fecafe5f036405088a3c6c62b70774b779e266
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36191343"
---
# <a name="create-bandwidth-policy-profiles-in-skype-for-business-server"></a><span data-ttu-id="54a98-103">비즈니스용 Skype 서버에서 대역폭 정책 프로필 만들기</span><span class="sxs-lookup"><span data-stu-id="54a98-103">Create bandwidth policy profiles in Skype for Business Server</span></span> 
 
<span data-ttu-id="54a98-104">비즈니스용 Skype 서버에서 엔터프라이즈 음성 통화 허용 제어에 사용 되는 대역폭 정책을 만들거나 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="54a98-104">Create or modify bandwidth policies, which are used by Enterprise Voice call admission control in Skype for Business Server.</span></span> 
  
<span data-ttu-id="54a98-105">대역폭 정책은 실시간 오디오 및 비디오 형식을 대역폭 사용량에 대 한 제한을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="54a98-105">Bandwidth policies define limitations on bandwidth usage for real-time audio and video modalities.</span></span> <span data-ttu-id="54a98-106">대역폭 정책은 호출 허용 제어를 위해 여러 네트워크 사이트에 적용할 수 있는 tobandwidth 정책 프로필에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="54a98-106">Bandwidth policies are applied tobandwidth policy profiles, which can be applied to multiple network sites for call admission control.</span></span>
  
<span data-ttu-id="54a98-107">CAC 배포에 설정 해야 하는 대역폭 제한에 대 한 지침은 비즈니스용 [Skype 서버의 통화 허용 제어 계획](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="54a98-107">For guidelines about what bandwidth limits you should set in your CAC deployment, see [Plan for call admission control in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md).</span></span>
  
<span data-ttu-id="54a98-108">다음 절차에서 만든 예제 정책은 전체 오디오 트래픽, 개별 오디오 세션, 전체 비디오 트래픽, 개별 비디오 세션에 대 한 제한을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="54a98-108">The example policies created in the following procedure set limits for overall audio traffic, individual audio sessions, overall video traffic, and individual video sessions.</span></span> <span data-ttu-id="54a98-109">예를 들어 5Mb_Link 대역폭 정책 프로필에는 다음 한도가 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="54a98-109">For example, the 5Mb_Link bandwidth policy profile sets the following limits:</span></span> 
  
- <span data-ttu-id="54a98-110">오디오 제한: 2000 kbps</span><span class="sxs-lookup"><span data-stu-id="54a98-110">Audio Limit: 2,000 kbps</span></span>
    
- <span data-ttu-id="54a98-111">오디오 세션 제한: 200 kbps</span><span class="sxs-lookup"><span data-stu-id="54a98-111">Audio Session Limit: 200 kbps</span></span>
    
- <span data-ttu-id="54a98-112">비디오 제한: 1400 kbps</span><span class="sxs-lookup"><span data-stu-id="54a98-112">Video Limit: 1,400 kbps</span></span>
    
- <span data-ttu-id="54a98-113">비디오 세션 제한: 700 kbps</span><span class="sxs-lookup"><span data-stu-id="54a98-113">Video Session Limit: 700 kbps</span></span>
    
> [!NOTE]
> <span data-ttu-id="54a98-114">최소 오디오 세션 제한 값은 40 kbps입니다.</span><span class="sxs-lookup"><span data-stu-id="54a98-114">The minimum Audio Session Limit value is 40 kbps.</span></span> <span data-ttu-id="54a98-115">최소 비디오 세션 제한 값은 100 kbps입니다.</span><span class="sxs-lookup"><span data-stu-id="54a98-115">The minimum Video Session Limit value is 100 kbps.</span></span> 
  
### <a name="to-create-bandwidth-policy-profiles-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="54a98-116">비즈니스용 Skype Server Management Shell을 사용 하 여 대역폭 정책 프로필을 만들려면</span><span class="sxs-lookup"><span data-stu-id="54a98-116">To create bandwidth policy profiles by using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="54a98-117">비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **비즈니스용 skype 2015**을 차례로 클릭 한 다음 비즈니스용 **skype Server management Shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="54a98-117">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="54a98-118">만들려는 각 대역폭 정책 프로필에 대해 새 CsNetworkBandwidthPolicyProfile cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="54a98-118">For each bandwidth policy profile that you want to create, run the New-CsNetworkBandwidthPolicyProfile cmdlet.</span></span> <span data-ttu-id="54a98-119">예를 들어 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="54a98-119">For example, run:</span></span>
    
   ```
   New-CsNetworkBandwidthPolicyProfile -Identity 5Mb_Link -Description "BW profile for 5Mb links" -AudioBWLimit 2000 -AudioBWSessionLimit 200 -VideoBWLimit 1400   -VideoBWSessionLimit 700
   ```

   ```
   New-CsNetworkBandwidthPolicyProfile -Identity 10Mb_Link -Description "BW profile for 10Mb links" -AudioBWLimit 4000 -AudioBWSessionLimit 200 -VideoBWLimit 2800 -VideoBWSessionLimit 700
   ```

   ```
   New-CsNetworkBandwidthPolicyProfile -Identity 50Mb_Link -Description "BW profile for 50Mb links" -AudioBWLimit 20000 -AudioBWSessionLimit 200 -VideoBWLimit 14000 -VideoBWSessionLimit 700
   ```

   ```
   New-CsNetworkBandwidthPolicyProfile -Identity 25Mb_Link -Description "BW profile for 25Mb links" -AudioBWLimit 10000 -AudioBWSessionLimit 200 -VideoBWLimit 7000 -VideoBWSessionLimit 700
   ```

### <a name="to-create-bandwidth-policy-profiles-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="54a98-120">비즈니스용 Skype Server 제어판을 사용 하 여 대역폭 정책 프로필 만들기</span><span class="sxs-lookup"><span data-stu-id="54a98-120">To create bandwidth policy profiles by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="54a98-121">비즈니스용 Skype Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="54a98-121">Open Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="54a98-122">왼쪽 탐색 모음에서 **네트워크 구성을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="54a98-122">In the left navigation bar, click **Network Configuration**.</span></span>
    
3. <span data-ttu-id="54a98-123">**정책 프로필** 탐색 단추를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="54a98-123">Click the **Policy Profile** navigation button.</span></span>
    
4. <span data-ttu-id="54a98-124">**새로 만들기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="54a98-124">Click **New**.</span></span>
    
5. <span data-ttu-id="54a98-125">**새 정책 프로필** 페이지에서 **이름을** 클릭 한 다음 대역폭 정책 프로필의 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="54a98-125">On the **New Policy Profile** page, click **Name** and then type a name for the bandwidth policy profile.</span></span>
    
6. <span data-ttu-id="54a98-126">**오디오 제한을**클릭 한 다음 최대 kbps를 입력 하 여 모든 오디오 세션을 결합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54a98-126">Click **Audio limit**, and then type in the maximum number of kbps to allow for all audio sessions combined.</span></span>
    
7. <span data-ttu-id="54a98-127">**오디오 세션 제한을**클릭 한 다음 최대 kbps를 입력 하 여 각 개별 오디오 세션을 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="54a98-127">Click **Audio session limit**, and then type in the maximum number of kbps to allow for each individual audio session.</span></span>
    
8. <span data-ttu-id="54a98-128">**비디오 제한을**클릭 한 다음 최대 kbps를 입력 하 여 모든 비디오 세션을 결합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54a98-128">Click **Video limit**, and then type in the maximum number of kbps to allow for all video sessions combined.</span></span>
    
9. <span data-ttu-id="54a98-129">**비디오 세션 제한을**클릭 한 다음 최대 kbps를 입력 하 여 각 개별 비디오 세션을 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="54a98-129">Click **Video session limit**, and then type in the maximum number of kbps to allow for each individual video session.</span></span>
    
10. <span data-ttu-id="54a98-130">필요에 따라 **설명을**클릭 한 다음이 대역폭 정책 프로필을 설명 하는 추가 정보를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="54a98-130">Optionally, click **Description**, and then type additional information to describe this bandwidth policy profile.</span></span>
    
11. <span data-ttu-id="54a98-131">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="54a98-131">Click **Commit**.</span></span>
    
12. <span data-ttu-id="54a98-132">토폴로지에 대 한 대역폭 정책 프로필 만들기를 완료 하려면 다른 대역폭 정책 프로필에 대 한 설정을 사용 하 여 4 ~ 11 단계를 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="54a98-132">To finish creating bandwidth policy profiles for your topology, repeat steps 4 through 11 with settings for other bandwidth policy profiles.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="54a98-133">참고 항목</span><span class="sxs-lookup"><span data-stu-id="54a98-133">See also</span></span>

[<span data-ttu-id="54a98-134">새로운 CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="54a98-134">New-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csnetworkbandwidthpolicyprofile?view=skype-ps)
  
[<span data-ttu-id="54a98-135">Get-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="54a98-135">Get-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csnetworkbandwidthpolicyprofile?view=skype-ps)
  
[<span data-ttu-id="54a98-136">Set-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="54a98-136">Set-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csnetworkbandwidthpolicyprofile?view=skype-ps)
  
[<span data-ttu-id="54a98-137">제거-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="54a98-137">Remove-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkbandwidthpolicyprofile?view=skype-ps)
