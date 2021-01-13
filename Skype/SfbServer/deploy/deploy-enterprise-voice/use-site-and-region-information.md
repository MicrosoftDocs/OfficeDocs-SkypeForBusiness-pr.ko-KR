---
title: 사이트 및 지역 정보를 사용하도록 비즈니스용 Skype 서버에서 미디어 우회 전역 설정 구성
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
ms.assetid: 0a21cdf1-f350-49da-b346-70806f256bea
description: 비즈니스용 Skype 서버 서버의 특정 사이트 및 지역에만 사용하도록 미디어 우회를 Enterprise Voice.
ms.openlocfilehash: 58fd4fca90029a8a5f4cd82c6a9616ae66e69cd0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830588"
---
# <a name="configure-media-bypass-global-settings-in-skype-for-business-server-to-use-site-and-region-information"></a><span data-ttu-id="2389d-103">사이트 및 지역 정보를 사용하도록 비즈니스용 Skype 서버에서 미디어 우회 전역 설정 구성</span><span class="sxs-lookup"><span data-stu-id="2389d-103">Configure media bypass global settings in Skype for Business Server to use site and region information</span></span>
 
<span data-ttu-id="2389d-104">비즈니스용 Skype 서버 서버의 특정 사이트 및 지역에만 사용하도록 미디어 우회를 Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="2389d-104">Configure media bypass to be used for only certain sites and regions in Skype for Business Server Enterprise Voice.</span></span> 
  
 <span data-ttu-id="2389d-105">이 항목의 단계를 사용하여 미디어 우회에 대한 전역 설정을 구성하는 경우 모든 비즈니스용 Skype 끝점과 트렁크 연결에 대해 미디어 우회를 구성한 피어 간에 연결이 좋지 않다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="2389d-105">If you use the steps in this topic to configure global settings for media bypass, the assumption is that you do not have good connectivity between all Skype for Business endpoints and any peer for which you configured media bypass on the trunk connection.</span></span>
  
> [!NOTE]
> <span data-ttu-id="2389d-p101">네트워크 지역 및 네트워크 사이트 정보는 통화 허용 제어와 미디어 바이패스 고급 Enterprise Voice 기능 간에 공유됩니다(둘 다 설정된 경우). 따라서 통화 허용 제어를 이미 구성한 경우 다음 절차에 따라 특별히 미디어 바이패스에 대해 사이트 및 지역 정보를 편집할 필요가 없습니다. 통화 허용 제어에 대한 네트워크 지역 및 사이트를 아직 구성하지 않은 상태에서 미디어 바이패스 설정을 변경하려는 경우에 이 절차의 단계를 따르십시오.</span><span class="sxs-lookup"><span data-stu-id="2389d-p101">Network region and network site information is shared between call admission control and media bypass advanced Enterprise Voice features when both are enabled. Therefore, if you have already configured call admission control, you are not required to use the following procedure to edit the site and region information specifically for media bypass. Follow the steps in this procedure if you have not yet configured network regions and sites for call admission control, and you want to change media bypass settings.</span></span> 
  
<span data-ttu-id="2389d-109">미디어 우회가 제대로 작동하려면 토폴로지 작성기에서 정의한 사이트와 네트워크 지역 및 네트워크 사이트를 구성할 때 정의된 사이트 간에 일관성이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2389d-109">For media bypass to work properly there must be consistency between a site as defined in Topology Builder and as it is defined when you configure network regions and network sites.</span></span> <span data-ttu-id="2389d-110">예를 들어 토폴로지 작성기에서 PSTN 게이트웨이만 배포한 것으로 정의한 분기 사이트가 있는 경우 분기 사이트 사용자가 PSTN 통화를 분기 사이트의 PSTN 게이트웨이를 통해 라우팅될 수 있도록 하는 Enterprise Voice 정책을 사용하여 분기 사이트를 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2389d-110">For example, if you have a branch site that you defined in Topology Builder as having only a PSTN gateway deployed, then that branch site must be configured with an Enterprise Voice policy that enables branch site users to have their PSTN calls routed through the PSTN gateway at the branch site.</span></span>
  
### <a name="to-configure-site-and-region-information-for-media-bypass"></a><span data-ttu-id="2389d-111">미디어 바이패스에 대한 사이트 및 지역 정보를 구성하려면</span><span class="sxs-lookup"><span data-stu-id="2389d-111">To Configure Site and Region Information for Media Bypass</span></span>

1. <span data-ttu-id="2389d-112">브라우저 창을 열고 관리자 URL을 입력하여 비즈니스용 Skype 서버 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="2389d-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
2. <span data-ttu-id="2389d-113">왼쪽 탐색 모음에서 **네트워크 구성** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="2389d-113">In the left navigation bar, click **Network Configuration**.</span></span>
    
3. <span data-ttu-id="2389d-114">테이블에서 **전역** 구성을 두 번 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="2389d-114">Double-click the **Global** configuration in the table.</span></span>
    
4. <span data-ttu-id="2389d-115">**전역 설정 편집** 페이지에서 **미디어 바이패스 사용** 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2389d-115">On the **Edit Global Setting** page, select the **Enable media bypass** check box.</span></span>
    
5. <span data-ttu-id="2389d-116">**사이트 및 지역 구성 사용** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="2389d-116">Click **Use sites and region configuration**.</span></span>
    
6. <span data-ttu-id="2389d-117">필요한 경우 **매핑되지 않은 사이트에 대해 바이패스 사용** 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2389d-117">If necessary, select the **Enable bypass for non-mapped sites** check box.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="2389d-p103">이 확인란은 대역폭 제한이 없는 하나 이상의 큰 사이트(예: 대규모 중앙 사이트)를 같은 지역과 연결했지만 대역폭이 제한된 일부 분기 사이트도 이 지역과 연결한 경우에만 선택합니다. 매핑되지 않은 사이트에 대해 바이패스를 사용하도록 설정하면 모든 사이트와 연결된 모든 서브넷을 지정할 필요 없이 분기 사이트와 연결된 서브넷만 지정하면 되므로 구성이 간소화됩니다. 통화 허용 제어가 설정된 경우에는 이 확인란을 선택하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="2389d-p103">Select this check box only if you have one or more large sites associated with the same region that do not have bandwidth constraints (for example, a large central site), but you also have some branch sites associated with the same region that do have bandwidth constraints. When you enable bypass for non-mapped sites, configuration is streamlined in that you specify only the subnets associated with the branch sites, rather than needing to specify all subnets associated with all sites. We recommend that you do not select this check box if call admission control is enabled.</span></span> 
  
7. <span data-ttu-id="2389d-121">**커밋** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="2389d-121">Click **Commit**.</span></span>
    
<span data-ttu-id="2389d-122">다음으로 서브넷을 네트워크 사이트에 연결에 설명된 바와 같이 네트워크 사이트에 [서브넷을 추가합니다.](deploy-network.md#BKMK_AssociateSubnets)</span><span class="sxs-lookup"><span data-stu-id="2389d-122">Next, add subnets to the network site, as described in [Associate a subnet with a network site](deploy-network.md#BKMK_AssociateSubnets).</span></span> <span data-ttu-id="2389d-123">모든 서브넷을 네트워크 사이트와 연결하면 미디어 바이패스 배포가 완료됩니다.</span><span class="sxs-lookup"><span data-stu-id="2389d-123">After you associate all subnets with network sites, media bypass deployment is complete.</span></span>
> [!IMPORTANT]
> <span data-ttu-id="2389d-124">네트워크 지역 및 네트워크 사이트를 아직 만들지 않은 경우 미디어 바이패스 배포를 진행하려면 먼저 네트워크 지역과 네트워크 사이트를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2389d-124">If you have not already created network regions and network sites, you must first create those before you can proceed with media bypass deployment.</span></span> <span data-ttu-id="2389d-125">자세한 내용은 비즈니스용 Skype에서 네트워크 지역, 사이트 및 [서브넷 배포를 참조하세요.](deploy-network.md)</span><span class="sxs-lookup"><span data-stu-id="2389d-125">For details, see [Deploy network regions, sites and subnets in Skype for Business](deploy-network.md).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="2389d-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2389d-126">See also</span></span>

[<span data-ttu-id="2389d-127">네트워크 사이트에 서브넷 연결</span><span class="sxs-lookup"><span data-stu-id="2389d-127">Associate a subnet with a network site</span></span>](deploy-network.md#BKMK_AssociateSubnets)

