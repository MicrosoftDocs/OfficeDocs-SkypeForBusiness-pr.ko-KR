---
title: 비즈니스용 Skype 서버에서 네트워크 지역 링크 만들기
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
ms.assetid: f8163910-8935-475d-88a2-3aa44feb9dbe
description: 비즈니스용 Skype 서버에서 통화 Enterprise Voice 제어에 사용되는 네트워크 지역 링크를 만들거나 수정합니다.
ms.openlocfilehash: 5fd9657b3919e80552a82912550e7314297182cc
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093106"
---
# <a name="create-network-region-links-in-skype-for-business-server"></a><span data-ttu-id="b9988-103">비즈니스용 Skype 서버에서 네트워크 지역 링크 만들기</span><span class="sxs-lookup"><span data-stu-id="b9988-103">Create network region links in Skype for Business Server</span></span>
 
<span data-ttu-id="b9988-104">비즈니스용 Skype 서버에서 통화 Enterprise Voice 제어에 사용되는 네트워크 지역 링크를 만들거나 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="b9988-104">Create or modify network region links, which are used by Enterprise Voice call admission control in Skype for Business Server.</span></span> 
  
<span data-ttu-id="b9988-105">네트워크 내의 지역은 실제 WAN 연결을 통해 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="b9988-105">Regions within a network are linked through physical WAN connectivity.</span></span> <span data-ttu-id="b9988-106">네트워크 지역 링크는 CAC(통화 제어)에 대해 구성된 두 지역 간에 링크를 만들고 이러한 지역 간의 오디오 및 비디오 트래픽에 대한 대역폭 제한을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="b9988-106">A network region link creates a link between two regions configured for Call Admission Control (CAC) and sets the bandwidth limitations on audio and video traffic between these regions.</span></span>
  
<span data-ttu-id="b9988-107">이 토폴로지 예에는 북미와 APAC 지역 간 링크 및 EMEA와 APAC 지역 간 링크가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="b9988-107">The example topology has a link between the North America and APAC regions, and a link between the EMEA and APAC regions.</span></span> <span data-ttu-id="b9988-108">이러한 각 지역 링크는 예제: 비즈니스용 Skype 서버의 통화 제한에 대한 요구 사항 수집의 지역 링크 대역폭 정보 표에 설명된 WAN 대역폭에 [의해 제한됩니다.](../../plan-your-deployment/enterprise-voice-solution/example-gathering-requirements.md)</span><span class="sxs-lookup"><span data-stu-id="b9988-108">Each of these region links is constrained by WAN bandwidth, as described in Region Link Bandwidth Information table in [Example: Gathering requirements for call admission control in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/example-gathering-requirements.md).</span></span>
  
### <a name="to-create-network-region-links-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="b9988-109">비즈니스용 Skype 서버 관리 셸을 사용하여 네트워크 지역 링크를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9988-109">To create network region links by using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="b9988-110">비즈니스용 Skype 서버 관리 셸 시작: **시작,** 모든 **프로그램,** 비즈니스용 **Skype 2015,** 비즈니스용 Skype 서버 관리 셸을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="b9988-110">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="b9988-111">New-CsNetworkRegionLink cmdlet를 실행하여 지역 링크를 만들고 적합한 대역폭 정책 프로필을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="b9988-111">Run the New-CsNetworkRegionLink cmdlet to create the region links and apply appropriate bandwidth policy profiles.</span></span> <span data-ttu-id="b9988-112">예를 들어 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="b9988-112">For example, run:</span></span>
    
   ```powershell
   New-CsNetworkRegionLink -NetworkRegionLinkID NA-EMEA-LINK -NetworkRegionID1 NorthAmerica -NetworkRegionID2 EMEA -BWPolicyProfileID 50Mb_Link
   ```

   ```powershell
   New-CsNetworkRegionLink -NetworkRegionLinkID EMEA-APAC-LINK -NetworkRegionID1 EMEA -NetworkRegionID2 APAC -BWPolicyProfileID 25Mb_Link
   ```

### <a name="to-create-network-region-links-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="b9988-113">비즈니스용 Skype 서버 제어판을 사용하여 네트워크 지역 링크를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9988-113">To create network region links by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="b9988-114">비즈니스용 Skype 서버 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="b9988-114">Open Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="b9988-115">왼쪽 탐색 모음에서 **네트워크 구성** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b9988-115">In the left navigation bar, click **Network Configuration**.</span></span>
    
3. <span data-ttu-id="b9988-116">**지역 링크** 탐색 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b9988-116">Click the **Region Link** navigation button.</span></span>
    
4. <span data-ttu-id="b9988-117">**새로 만들기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b9988-117">Click **New**.</span></span>
    
5. <span data-ttu-id="b9988-118">**새 지역 링크** 페이지에서 **이름** 을 클릭하고 네트워크 지역 링크에 대한 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="b9988-118">On the **New Region Link** page, click **Name** and then type a name for the network region link.</span></span>
    
6. <span data-ttu-id="b9988-119">**네트워크 지역 #1** 을 클릭하고 목록에서 네트워크 지역 #2에 연결할 네트워크 지역을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b9988-119">Click **Network Region #1**, and then click the network region in the list that you want to link to Network Region #2.</span></span>
    
7. <span data-ttu-id="b9988-120">**네트워크 지역 #2** 를 클릭하고 목록에서 네트워크 지역 #1에 연결할 네트워크 지역을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b9988-120">Click **Network Region #2**, and then click a network region in the list that you want to link to Network Region #1.</span></span>
    
8. <span data-ttu-id="b9988-121">(선택 사항) **대역폭 정책** 을 클릭하고 네트워크 지역 링크에 적용할 대역폭 정책 프로필을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b9988-121">Optionally, click **Bandwidth policy**, and then select the bandwidth policy profile that you want to apply to the network region link.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="b9988-122">네트워크 지역 링크에 대역폭 제한이 있고 CAC를 사용하여 해당 링크에 대해 미디어 트래픽을 제어할 경우에만 대역폭 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="b9988-122">Apply a bandwidth policy only if the network region link is bandwidth-constrained and you want to use CAC to control media traffic on that link.</span></span> 
  
9. <span data-ttu-id="b9988-123">**커밋** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b9988-123">Click **Commit**.</span></span>
    
10. <span data-ttu-id="b9988-124">토폴로지에 대한 네트워크 지역 링크 만들기를 종료하려면 다른 지역에 대한 설정을 사용하여 4-9단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="b9988-124">To finish creating network region links for your topology, repeat steps 4 through 9 with settings for other regions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="b9988-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b9988-125">See also</span></span>

[<span data-ttu-id="b9988-126">New-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="b9988-126">New-CsNetworkRegionLink</span></span>](/powershell/module/skype/new-csnetworkregionlink?view=skype-ps)
  
[<span data-ttu-id="b9988-127">Get-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="b9988-127">Get-CsNetworkRegionLink</span></span>](/powershell/module/skype/get-csnetworkregionlink?view=skype-ps)
  
[<span data-ttu-id="b9988-128">Set-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="b9988-128">Set-CsNetworkRegionLink</span></span>](/powershell/module/skype/set-csnetworkregionlink?view=skype-ps)
  
[<span data-ttu-id="b9988-129">Remove-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="b9988-129">Remove-CsNetworkRegionLink</span></span>](/powershell/module/skype/remove-csnetworkregionlink?view=skype-ps)