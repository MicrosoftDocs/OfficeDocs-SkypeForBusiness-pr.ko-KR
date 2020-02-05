---
title: 비즈니스용 Skype 서버에서 네트워크 지역 링크 만들기
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 비즈니스용 Skype 서버에서 엔터프라이즈 음성 통화 허용 제어에 사용 되는 네트워크 지역 링크를 만들거나 수정 합니다.
ms.openlocfilehash: 20fdbca9eb56fad9b69c6299177301e82fbf115a
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41767911"
---
# <a name="create-network-region-links-in-skype-for-business-server"></a><span data-ttu-id="bac1e-103">비즈니스용 Skype 서버에서 네트워크 지역 링크 만들기</span><span class="sxs-lookup"><span data-stu-id="bac1e-103">Create network region links in Skype for Business Server</span></span>
 
<span data-ttu-id="bac1e-104">비즈니스용 Skype 서버에서 엔터프라이즈 음성 통화 허용 제어에 사용 되는 네트워크 지역 링크를 만들거나 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="bac1e-104">Create or modify network region links, which are used by Enterprise Voice call admission control in Skype for Business Server.</span></span> 
  
<span data-ttu-id="bac1e-105">네트워크 내의 영역은 실제 WAN 연결을 통해 연결 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bac1e-105">Regions within a network are linked through physical WAN connectivity.</span></span> <span data-ttu-id="bac1e-106">네트워크 지역 링크는 CAC (호출 허용 제어)에 대해 구성 된 두 지역 간에 링크를 만들고 이러한 지역 간의 오디오 및 비디오 트래픽에 대 한 대역폭 제한을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="bac1e-106">A network region link creates a link between two regions configured for Call Admission Control (CAC) and sets the bandwidth limitations on audio and video traffic between these regions.</span></span>
  
<span data-ttu-id="bac1e-107">이 예제 토폴로지에는 북미와 APAC 지역 간의 링크와 EMEA와 APAC 지역 간의 링크가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bac1e-107">The example topology has a link between the North America and APAC regions, and a link between the EMEA and APAC regions.</span></span> <span data-ttu-id="bac1e-108">이러한 지역 링크는 지역 링크 대역폭 정보 표에 설명 된 것 처럼 WAN 대역폭에 의해 제한 됩니다 [예: 비즈니스용 Skype 서버에서 통화 허용 제어에 대 한 요구 사항 수집](../../plan-your-deployment/enterprise-voice-solution/example-gathering-requirements.md)</span><span class="sxs-lookup"><span data-stu-id="bac1e-108">Each of these region links is constrained by WAN bandwidth, as described in Region Link Bandwidth Information table in [Example: Gathering requirements for call admission control in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/example-gathering-requirements.md).</span></span>
  
### <a name="to-create-network-region-links-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="bac1e-109">비즈니스용 Skype Server Management Shell을 사용 하 여 네트워크 지역 링크를 만들려면</span><span class="sxs-lookup"><span data-stu-id="bac1e-109">To create network region links by using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="bac1e-110">비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **비즈니스용 skype 2015**을 차례로 클릭 한 다음 비즈니스용 **skype Server management Shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="bac1e-110">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="bac1e-111">새-Csnetworkregion 링크 cmdlet을 실행 하 여 지역 링크를 만들고 적절 한 대역폭 정책 프로필을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="bac1e-111">Run the New-CsNetworkRegionLink cmdlet to create the region links and apply appropriate bandwidth policy profiles.</span></span> <span data-ttu-id="bac1e-112">예를 들어 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="bac1e-112">For example, run:</span></span>
    
   ```powershell
   New-CsNetworkRegionLink -NetworkRegionLinkID NA-EMEA-LINK -NetworkRegionID1 NorthAmerica -NetworkRegionID2 EMEA -BWPolicyProfileID 50Mb_Link
   ```

   ```powershell
   New-CsNetworkRegionLink -NetworkRegionLinkID EMEA-APAC-LINK -NetworkRegionID1 EMEA -NetworkRegionID2 APAC -BWPolicyProfileID 25Mb_Link
   ```

### <a name="to-create-network-region-links-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="bac1e-113">비즈니스용 Skype Server 제어판을 사용 하 여 네트워크 지역 링크를 만들려면</span><span class="sxs-lookup"><span data-stu-id="bac1e-113">To create network region links by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="bac1e-114">비즈니스용 Skype Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="bac1e-114">Open Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="bac1e-115">왼쪽 탐색 모음에서 **네트워크 구성을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="bac1e-115">In the left navigation bar, click **Network Configuration**.</span></span>
    
3. <span data-ttu-id="bac1e-116">**지역 링크** 탐색 단추를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="bac1e-116">Click the **Region Link** navigation button.</span></span>
    
4. <span data-ttu-id="bac1e-117">**새로 만들기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="bac1e-117">Click **New**.</span></span>
    
5. <span data-ttu-id="bac1e-118">**새 지역 링크** 페이지에서 **이름을** 클릭 한 다음 네트워크 지역 링크의 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="bac1e-118">On the **New Region Link** page, click **Name** and then type a name for the network region link.</span></span>
    
6. <span data-ttu-id="bac1e-119">**네트워크 지역 #1**를 클릭 한 다음 목록에서 네트워크 지역 #2 연결할 네트워크 지역을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="bac1e-119">Click **Network Region #1**, and then click the network region in the list that you want to link to Network Region #2.</span></span>
    
7. <span data-ttu-id="bac1e-120">**네트워크 지역 #2**클릭 한 다음 목록에서 네트워크 지역 #1 연결할 네트워크 지역을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="bac1e-120">Click **Network Region #2**, and then click a network region in the list that you want to link to Network Region #1.</span></span>
    
8. <span data-ttu-id="bac1e-121">필요에 따라 **대역폭 정책을**클릭 한 다음 네트워크 지역 링크에 적용 하려는 대역폭 정책 프로필을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="bac1e-121">Optionally, click **Bandwidth policy**, and then select the bandwidth policy profile that you want to apply to the network region link.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="bac1e-122">네트워크 지역 링크에 대역폭이 제한 되어 있고 CAC를 사용 하 여 해당 링크의 미디어 트래픽을 제어 하려는 경우에만 대역폭 정책을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="bac1e-122">Apply a bandwidth policy only if the network region link is bandwidth-constrained and you want to use CAC to control media traffic on that link.</span></span> 
  
9. <span data-ttu-id="bac1e-123">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="bac1e-123">Click **Commit**.</span></span>
    
10. <span data-ttu-id="bac1e-124">토폴로지에 대 한 네트워크 지역 링크 만들기를 마치려면 다른 지역에 대 한 설정을 사용 하 여 4 ~ 9 단계를 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="bac1e-124">To finish creating network region links for your topology, repeat steps 4 through 9 with settings for other regions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="bac1e-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bac1e-125">See also</span></span>

[<span data-ttu-id="bac1e-126">새-Csnetwork국가 링크</span><span class="sxs-lookup"><span data-stu-id="bac1e-126">New-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csnetworkregionlink?view=skype-ps)
  
[<span data-ttu-id="bac1e-127">Get-Csnetwork국가 링크</span><span class="sxs-lookup"><span data-stu-id="bac1e-127">Get-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csnetworkregionlink?view=skype-ps)
  
[<span data-ttu-id="bac1e-128">Set-Csnetwork국가 링크</span><span class="sxs-lookup"><span data-stu-id="bac1e-128">Set-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csnetworkregionlink?view=skype-ps)
  
[<span data-ttu-id="bac1e-129">-Csnetwork국가 링크 제거</span><span class="sxs-lookup"><span data-stu-id="bac1e-129">Remove-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkregionlink?view=skype-ps)
