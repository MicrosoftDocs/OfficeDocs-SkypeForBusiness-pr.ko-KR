---
title: SBA(Survivable Branch Appliance) 연결
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 모든 SBA(Survivable Branch Appliance)는 SBA용 백업 고급 등록자로 작동하는 프런트 엔드 풀과 연결됩니다. 프런트 엔드 풀이 비즈니스용 Skype 서버 2019로 마이그레이션되는 경우 풀이 업그레이드되는 동안 프런트 엔드 풀에서 SBA의 연결이 되어야 합니다. 풀이 비즈니스용 Skype 서버 2019로 마이그레이션된 후 SBA를 업그레이드된 프런트 엔드 풀과 다시 연결될 수 있습니다. 여기에는 토폴로지 작성기에서 레거시 토폴로지에서 SBA를 삭제한 다음 비즈니스용 Skype 서버 2019 토폴로지에 SBA를 추가하는 과정이 진행됩니다. 레거시 SBA에 있는 사용자는 토폴로지에서 SBA를 제거하기 전에 먼저 다른 프런트 엔드 풀로 이동해야 합니다. SBA가 비즈니스용 Skype 서버 2019 토폴로지에 추가된 후 해당 사용자를 SBA로 다시 이동할 수 있습니다. 이러한 단계는 아래에 요약되어 있습니다.
ms.openlocfilehash: 23fea7694a754b82ecad684d2ea02b603a6c7299
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44751550"
---
# <a name="connect-a-survivable-branch-appliance"></a><span data-ttu-id="d3d69-108">SBA(Survivable Branch Appliance) 연결</span><span class="sxs-lookup"><span data-stu-id="d3d69-108">Connect a Survivable Branch Appliance</span></span>

<span data-ttu-id="d3d69-109">모든 SBA(Survivable Branch Appliance)는 SBA의 백업 등록자 역할을 하는 프런트 엔드 풀과 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3d69-109">Every Survivable Branch Appliance (SBA) is associated with a Front End pool that serves as a backup registrar for the SBA.</span></span> <span data-ttu-id="d3d69-110">프런트 엔드 풀이 비즈니스용 Skype 서버 2019로 마이그레이션되는 경우 풀이 업그레이드되는 동안 프런트 엔드 풀에서 SBA의 연결이 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3d69-110">When the Front End pool is migrated to Skype for Business Server 2019, the SBA must be disassociated from the Front End pool while the pool is upgraded.</span></span> <span data-ttu-id="d3d69-111">풀을 비즈니스용 Skype 서버 2019로 마이그레이션한 후 SBA를 업그레이드된 프런트 엔드 풀과 다시 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="d3d69-111">After the pool has been migrated to Skype for Business Server 2019, the SBA can be re-associated with the upgraded Front End pool.</span></span> <span data-ttu-id="d3d69-112">여기에는 토폴로지 작성기에서 레거시 토폴로지에서 SBA를 삭제한 다음 비즈니스용 Skype 서버 2019 토폴로지에 SBA를 추가하는 과정이 진행됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3d69-112">This involves deleting the SBA from the legacy topology in Topology Builder and then adding the SBA to the Skype for Business Server 2019 topology.</span></span> <span data-ttu-id="d3d69-113">레거시 SBA에 있는 사용자는 토폴로지에서 SBA를 제거하기 전에 먼저 다른 프런트 엔드 풀로 이동해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3d69-113">Users homed on the legacy SBA must first be moved to another Front End pool before removing the SBA from the topology.</span></span> <span data-ttu-id="d3d69-114">SBA가 비즈니스용 Skype 서버 2019 토폴로지에 추가된 후 해당 사용자를 SBA로 다시 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3d69-114">After the SBA is added to the Skype for Business Server 2019 topology, those users can be moved back to the SBA.</span></span> <span data-ttu-id="d3d69-115">이러한 단계는 아래에 요약되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3d69-115">These steps are summarized below:</span></span>
  
1. <span data-ttu-id="d3d69-116">레거시 SBA에 있는 분기 사용자를 다른 프런트 엔드 풀로 이동</span><span class="sxs-lookup"><span data-stu-id="d3d69-116">Move branch users homed on the legacy SBA to another Front End pool.</span></span>
    
2. <span data-ttu-id="d3d69-117">레거시 토폴로지에서 SBA를 제거하여 백업 등록 기관으로 기존 프런트 엔드 풀의 연결을 끊습니다.</span><span class="sxs-lookup"><span data-stu-id="d3d69-117">Remove SBA from the legacy topology to disconnect the existing Front End pool as a backup registrar.</span></span>
    
3. <span data-ttu-id="d3d69-118">비즈니스용 Skype 서버 2019 토폴로지에 SBA를 추가하고 이 새 프런트 엔드 풀을 백업 등록 기관으로 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="d3d69-118">Add SBA to the Skype for Business Server 2019 topology and configure this new Front End pool as the backup registrar.</span></span> 
    
4. <span data-ttu-id="d3d69-119">분기 사용자를 새 비즈니스용 Skype 서버 2019 SBA로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="d3d69-119">Move the branch users to the new Skype for Business Server 2019 SBA.</span></span>
    
### <a name="add-legacy-sba-branch-site-to-your-topology"></a><span data-ttu-id="d3d69-120">토폴로지에 레거시 SBA 분기 사이트 추가</span><span class="sxs-lookup"><span data-stu-id="d3d69-120">Add legacy SBA branch site to your topology</span></span>

1. <span data-ttu-id="d3d69-121">**토폴로지 작성기** 를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="d3d69-121">Open **Topology Builder**.</span></span>
    
2. <span data-ttu-id="d3d69-122">왼쪽 창에서 분기 사이트를 마우스 오른쪽 **단추로** 클릭한 다음 새 분기 **사이트를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="d3d69-122">In the left pane, right-click **Branch sites**, and then click **New Branch Site**.</span></span>
    
3. <span data-ttu-id="d3d69-123">**새 분기 사이트 정의** 대화 상자에서 **이름** 을 클릭한 다음 분기 사이트의 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="d3d69-123">In the **Define New Branch Site** dialog box, click **Name**, and then type the name of the branch site.</span></span>
    
4. <span data-ttu-id="d3d69-124">(선택 사항) **설명** 을 클릭한 다음 분기 사이트에 대한 의미 있는 설명을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="d3d69-124">(Optional) Click **Description**, and then type a meaningful description for the branch site.</span></span>
    
5. <span data-ttu-id="d3d69-125">**다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d3d69-125">Click **Next**.</span></span>
    
6. <span data-ttu-id="d3d69-126">(선택 사항) 다음 **새 분기 사이트 정의** 대화 상자에서 다음 중 일부를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="d3d69-126">(Optional) In the next **Define New Branch Site** dialog box, do any of the following:</span></span> 
    
    1. <span data-ttu-id="d3d69-127">**구/군/시** 를 클릭한 다음 분기 사이트가 있는 구/군/시의 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="d3d69-127">Click **City**, and then type the name of the city in which the branch site is located.</span></span>
    
    2. <span data-ttu-id="d3d69-128">**시/도/지역** 을 클릭한 다음 분기 사이트가 있는 시/도/지역의 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="d3d69-128">Click **State/Region**, and then type the name of the state or region in which the branch site is located.</span></span>
    
    3. <span data-ttu-id="d3d69-129">국가 코드를 클릭한 다음 분기 사이트가 있는 국가/지역에 대한 두 자리 국가/지역 번호를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="d3d69-129">Click **Country Code**, and then type the two-digit calling code for the country/region in which the branch site is located.</span></span>
    
7. <span data-ttu-id="d3d69-130">다음을 **클릭하고** 이 사이트에서 Survivable Branch Appliance 또는 Server를 사용하는 경우 이 마법사가 닫히면 새 **Survivable Wizard** 열기 선택을 취소해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3d69-130">Click **Next**, and then, if you are using a Survivable Branch Appliance or Server at this site, be sure to clear the **Open the New Survivable Wizard when this wizard closes** check box.</span></span> <span data-ttu-id="d3d69-131">**마침** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d3d69-131">Click **Finish**.</span></span>
    
8. <span data-ttu-id="d3d69-132">레거시 SBA를 비즈니스용 Skype 서버 2019 프런트 엔드 풀에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="d3d69-132">To associate the legacy SBA to the Skype for Business Server 2019 Front End pool:</span></span>
    
    1. <span data-ttu-id="d3d69-133">만들어진 분기 사이트를 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="d3d69-133">Expand the branch site that has been created.</span></span> 
    
    2. <span data-ttu-id="d3d69-134">레거시 버전을 마우스 오른쪽 단추로 클릭한 다음 새로 **고치기 를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="d3d69-134">Right-click on legacy version, and then click **New**.</span></span>
    
    3. <span data-ttu-id="d3d69-135">Survivable **Branch Appliance를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="d3d69-135">Click **Survivable Branch Appliance**.</span></span>
    
9. <span data-ttu-id="d3d69-136">표시되는 마법사의 지침을 따르십시오.</span><span class="sxs-lookup"><span data-stu-id="d3d69-136">Follow the directions in the wizard that opens.</span></span> <span data-ttu-id="d3d69-137">마법사 항목에 대한 자세한 내용은 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d3d69-137">For information about wizard items, see</span></span>    
   <!-- [Define a Survivable Branch Appliance or Server in Lync 2013](https://technet.microsoft.com/library/gg398280(v=ocs.15).aspx). -->
   <!-- The above link points to un-rebranded 2013 content we will need to discuss rebrand or bring forward -->
    
    > [!NOTE]
    > <span data-ttu-id="d3d69-138">Survivable Branch Appliance는 모니터링 저장소에만 연결될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3d69-138">A Survivable Branch Appliance can only be associated with a Monitoring Store.</span></span> 
  
10. <span data-ttu-id="d3d69-139">이 사이트에서 SBA 또는 지속 가능 분기 서버를 사용하지 않는 경우에는 **이 마법사가 닫히면 새 지속 가능 마법사 열기** 확인란의 선택을 취소한 다음 **마침** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d3d69-139">If you are not using a Survivable Branch Appliance or Server at this site, clear the **Open the New Survivable Wizard when this wizard closes** check box, and then click **Finish**.</span></span>
    
11. <span data-ttu-id="d3d69-140">토폴로지에 추가할 각 분기 사이트에 대해 이전 단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="d3d69-140">Repeat the previous steps for each branch site you want to add to the topology.</span></span>
    

