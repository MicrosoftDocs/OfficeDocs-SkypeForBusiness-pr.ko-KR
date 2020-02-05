---
title: 미디어 구성 비즈니스용 Skype 서버의 전역 설정 무시 사이트 및 지역 정보 사용
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
ms.assetid: 0a21cdf1-f350-49da-b346-70806f256bea
description: 비즈니스용 Skype Server Enterprise Voice에서 특정 사이트 및 지역에 대해서만 미디어 바이패스를 사용 하도록 구성 합니다.
ms.openlocfilehash: 7a424e6737c1165eb037ca1130e3b87c4d0436e0
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41766941"
---
# <a name="configure-media-bypass-global-settings-in-skype-for-business-server-to-use-site-and-region-information"></a><span data-ttu-id="d01ac-103">미디어 구성 비즈니스용 Skype 서버의 전역 설정 무시 사이트 및 지역 정보 사용</span><span class="sxs-lookup"><span data-stu-id="d01ac-103">Configure media bypass global settings in Skype for Business Server to use site and region information</span></span>
 
<span data-ttu-id="d01ac-104">비즈니스용 Skype Server Enterprise Voice에서 특정 사이트 및 지역에 대해서만 미디어 바이패스를 사용 하도록 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="d01ac-104">Configure media bypass to be used for only certain sites and regions in Skype for Business Server Enterprise Voice.</span></span> 
  
 <span data-ttu-id="d01ac-105">이 항목의 단계를 사용 하 여 미디어 바이패스에 대 한 전역 설정을 구성 하는 경우, 모든 비즈니스용 Skype 끝점과 사용자의 트렁크 연결에서 미디어 바이패스를 구성한 피어 사이에는 적절 하 게 연결 되지 않은 것으로 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d01ac-105">If you use the steps in this topic to configure global settings for media bypass, the assumption is that you do not have good connectivity between all Skype for Business endpoints and any peer for which you configured media bypass on the trunk connection.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d01ac-106">네트워크 지역 및 네트워크 사이트 정보는 통화 허용 제어와 미디어 건너뛰기 고급 Enterprise Voice 기능을 모두 사용 하도록 설정 되어 있는 경우 공유 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d01ac-106">Network region and network site information is shared between call admission control and media bypass advanced Enterprise Voice features when both are enabled.</span></span> <span data-ttu-id="d01ac-107">따라서 통화 허용 제어를 이미 구성한 경우에는 다음 절차를 사용 하 여 미디어 바이패스에 대 한 사이트 및 지역 정보를 편집할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d01ac-107">Therefore, if you have already configured call admission control, you are not required to use the following procedure to edit the site and region information specifically for media bypass.</span></span> <span data-ttu-id="d01ac-108">통화 허용 제어에 대해 아직 네트워크 지역과 사이트를 구성 하지 않은 경우 미디어 우회 설정을 변경 하려면이 절차의 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="d01ac-108">Follow the steps in this procedure if you have not yet configured network regions and sites for call admission control, and you want to change media bypass settings.</span></span> 
  
<span data-ttu-id="d01ac-109">미디어 bypass이 제대로 작동 하려면 토폴로지 작성기에 정의 된 사이트와 네트워크 지역 및 네트워크 사이트를 구성할 때 정의 된 것과 동일한 사이트가 일치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d01ac-109">For media bypass to work properly there must be consistency between a site as defined in Topology Builder and as it is defined when you configure network regions and network sites.</span></span> <span data-ttu-id="d01ac-110">예를 들어, PSTN 게이트웨이만 배포 된 상태로 토폴로지 작성기에 정의한 지점 사이트를 사용 하는 경우에는 지점 사이트 사용자가 pstn을 통해 라우팅되는 PSTN 통화를 할 수 있는 엔터프라이즈 음성 정책으로 해당 지점 사이트를 구성 해야 합니다. 지사 사이트의 게이트웨이입니다.</span><span class="sxs-lookup"><span data-stu-id="d01ac-110">For example, if you have a branch site that you defined in Topology Builder as having only a PSTN gateway deployed, then that branch site must be configured with an Enterprise Voice policy that enables branch site users to have their PSTN calls routed through the PSTN gateway at the branch site.</span></span>
  
### <a name="to-configure-site-and-region-information-for-media-bypass"></a><span data-ttu-id="d01ac-111">미디어 바이패스에 대 한 사이트 및 지역 정보를 구성 하려면</span><span class="sxs-lookup"><span data-stu-id="d01ac-111">To Configure Site and Region Information for Media Bypass</span></span>

1. <span data-ttu-id="d01ac-112">브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="d01ac-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
2. <span data-ttu-id="d01ac-113">왼쪽 탐색 모음에서 **네트워크 구성을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d01ac-113">In the left navigation bar, click **Network Configuration**.</span></span>
    
3. <span data-ttu-id="d01ac-114">표에서 **전역** 구성을 두 번 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d01ac-114">Double-click the **Global** configuration in the table.</span></span>
    
4. <span data-ttu-id="d01ac-115">**전역 설정 편집** 페이지에서 **미디어 무시 사용** 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d01ac-115">On the **Edit Global Setting** page, select the **Enable media bypass** check box.</span></span>
    
5. <span data-ttu-id="d01ac-116">**사이트 및 지역 구성 사용을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d01ac-116">Click **Use sites and region configuration**.</span></span>
    
6. <span data-ttu-id="d01ac-117">필요한 경우 **매핑되지 않은 사이트에 바이패스 사용** 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d01ac-117">If necessary, select the **Enable bypass for non-mapped sites** check box.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="d01ac-118">대역폭 제약 조건이 없는 (예: 대규모 중앙 사이트) 동일한 지역과 연결 된 대규모 사이트가 하나 이상 있는 경우에만이 확인란을 선택 하 고, 대역폭이 있는 동일한 지역에 연결 된 일부 지점 사이트도 사항이.</span><span class="sxs-lookup"><span data-stu-id="d01ac-118">Select this check box only if you have one or more large sites associated with the same region that do not have bandwidth constraints (for example, a large central site), but you also have some branch sites associated with the same region that do have bandwidth constraints.</span></span> <span data-ttu-id="d01ac-119">매핑되지 않은 사이트에 대해 바이패스를 사용 하도록 설정 하면 모든 사이트와 연결 된 모든 서브넷을 지정할 필요 없이 분기 사이트와 연결 된 서브넷만 지정 하는 구성이 간소화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d01ac-119">When you enable bypass for non-mapped sites, configuration is streamlined in that you specify only the subnets associated with the branch sites, rather than needing to specify all subnets associated with all sites.</span></span> <span data-ttu-id="d01ac-120">통화 허용 제어를 사용 하는 경우이 확인란을 선택 하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="d01ac-120">We recommend that you do not select this check box if call admission control is enabled.</span></span> 
  
7. <span data-ttu-id="d01ac-121">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d01ac-121">Click **Commit**.</span></span>
    
<span data-ttu-id="d01ac-122">다음으로, [서브넷을 네트워크 사이트에 연결](deploy-network.md#BKMK_AssociateSubnets)의 설명에 따라 네트워크 사이트에 서브넷을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="d01ac-122">Next, add subnets to the network site, as described in [Associate a subnet with a network site](deploy-network.md#BKMK_AssociateSubnets).</span></span> <span data-ttu-id="d01ac-123">모든 서브넷을 네트워크 사이트에 연결한 후에는 미디어 바이패스 배포가 완료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d01ac-123">After you associate all subnets with network sites, media bypass deployment is complete.</span></span>
> [!IMPORTANT]
> <span data-ttu-id="d01ac-124">아직 네트워크 지역과 네트워크 사이트를 만들지 않은 경우에는 먼저 해당 지역을 만들어야 미디어 건너뛰기 배포를 진행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d01ac-124">If you have not already created network regions and network sites, you must first create those before you can proceed with media bypass deployment.</span></span> <span data-ttu-id="d01ac-125">자세한 내용은 [비즈니스용 Skype에서 네트워크 지역, 사이트 및 서브넷 배포](deploy-network.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d01ac-125">For details, see [Deploy network regions, sites and subnets in Skype for Business](deploy-network.md).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="d01ac-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d01ac-126">See also</span></span>

[<span data-ttu-id="d01ac-127">네트워크 사이트에 서브넷 연결</span><span class="sxs-lookup"><span data-stu-id="d01ac-127">Associate a subnet with a network site</span></span>](deploy-network.md#BKMK_AssociateSubnets)

