---
title: Survivable Branch 기기 연결
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 모든 Survivable Branch 기기 (SBA)는 SBA에 대 한 백업 등록 기관 역할을 하는 프런트 엔드 풀과 연결 되어 있습니다. 프런트 엔드 풀을 비즈니스용 Skype 서버 2019로 마이그레이션하는 경우 풀을 업그레이드 하는 동안 프런트 엔드 풀에서 연결을 해제 해야 하며,이 경우, 해당 풀이 비즈니스용 Skype Server 2019로 마이그레이션된 후에는 SBA를 업그레이드 된 전면 E와 다시 연결할 수 있습니다. nd 풀. 이 작업에는 토폴로지 작성기의 레거시 토폴로지에서의 SBA를 삭제 한 다음 비즈니스용 Skype 서버 2019 토폴로지에 추가 됩니다. 레거시 SBA에 있는 사용자는 먼저 다른 프런트 엔드 풀로 이동한 후에 야 토폴로지에서 SBA를 제거할 수 있습니다. SBA를 비즈니스용 Skype 서버 2019 토폴로지에 추가 하면 해당 사용자는 다시 SBA로 이동할 수 있습니다. 이러한 단계는 다음과 같이 요약할 수 있습니다.
ms.openlocfilehash: e5545a2de4eddd65790f425ab888b8fd07faf970
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36239550"
---
# <a name="connect-a-survivable-branch-appliance"></a><span data-ttu-id="3e834-108">Survivable Branch 기기 연결</span><span class="sxs-lookup"><span data-stu-id="3e834-108">Connect a Survivable Branch Appliance</span></span>

<span data-ttu-id="3e834-109">모든 Survivable Branch 기기 (SBA)는 SBA에 대 한 백업 등록 기관 역할을 하는 프런트 엔드 풀과 연결 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e834-109">Every Survivable Branch Appliance (SBA) is associated with a Front End pool that serves as a backup registrar for the SBA.</span></span> <span data-ttu-id="3e834-110">프런트 엔드 풀을 비즈니스용 Skype 서버 2019로 마이그레이션하면 풀이 업그레이드 되는 동안 SBA를 프런트 엔드 풀에서 분리 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e834-110">When the Front End pool is migrated to Skype for Business Server 2019, the SBA must be disassociated from the Front End pool while the pool is upgraded.</span></span> <span data-ttu-id="3e834-111">풀이 비즈니스용 Skype 서버 2019으로 마이그레이션한 후에는 SBA를 업그레이드 된 프런트 엔드 풀에 다시 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e834-111">After the pool has been migrated to Skype for Business Server 2019, the SBA can be re-associated with the upgraded Front End pool.</span></span> <span data-ttu-id="3e834-112">이 작업에는 토폴로지 작성기의 레거시 토폴로지에서의 SBA를 삭제 한 다음 비즈니스용 Skype 서버 2019 토폴로지에 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e834-112">This involves deleting the SBA from the legacy topology in Topology Builder and then adding the SBA to the Skype for Business Server 2019 topology.</span></span> <span data-ttu-id="3e834-113">레거시 SBA에 있는 사용자는 먼저 다른 프런트 엔드 풀로 이동한 후에 야 토폴로지에서 SBA를 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e834-113">Users homed on the legacy SBA must first be moved to another Front End pool before removing the SBA from the topology.</span></span> <span data-ttu-id="3e834-114">SBA가 비즈니스용 Skype 서버 2019 토폴로지에 추가 된 후에는 해당 사용자를 다시 SBA로 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e834-114">After the SBA is added to the Skype for Business Server 2019 topology, those users can be moved back to the SBA.</span></span> <span data-ttu-id="3e834-115">이러한 단계는 다음과 같이 요약할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e834-115">These steps are summarized below:</span></span>
  
1. <span data-ttu-id="3e834-116">레거시 SBA에 속한 분기 사용자를 다른 프런트 엔드 풀로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e834-116">Move branch users homed on the legacy SBA to another Front End pool.</span></span>
    
2. <span data-ttu-id="3e834-117">기존 프런트 엔드 풀을 백업 등록 기관으로 연결 해제 하려면 레거시 토폴로지에서 SBA를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e834-117">Remove SBA from the legacy topology to disconnect the existing Front End pool as a backup registrar.</span></span>
    
3. <span data-ttu-id="3e834-118">비즈니스용 Skype 서버 2019 토폴로지에 새 프런트 엔드 풀을 추가 하 고 백업 등록 기관으로 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e834-118">Add SBA to the Skype for Business Server 2019 topology and configure this new Front End pool as the backup registrar.</span></span> 
    
4. <span data-ttu-id="3e834-119">분기 사용자를 새 비즈니스용 Skype Server 2019 SBA로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e834-119">Move the branch users to the new Skype for Business Server 2019 SBA.</span></span>
    
### <a name="add-legacy-sba-branch-site-to-your-topology"></a><span data-ttu-id="3e834-120">토폴로지에 레거시 SBA 분기 사이트 추가</span><span class="sxs-lookup"><span data-stu-id="3e834-120">Add legacy SBA branch site to your topology</span></span>

1. <span data-ttu-id="3e834-121">**토폴로지 작성기**를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="3e834-121">Open **Topology Builder**.</span></span>
    
2. <span data-ttu-id="3e834-122">왼쪽 창에서 **분기 사이트**를 마우스 오른쪽 단추로 클릭 한 다음 **새 분기 사이트**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e834-122">In the left pane, right-click **Branch sites**, and then click **New Branch Site**.</span></span>
    
3. <span data-ttu-id="3e834-123">**새 분기 사이트 정의** 대화 상자에서 **이름을**클릭 한 다음 분기 사이트의 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e834-123">In the **Define New Branch Site** dialog box, click **Name**, and then type the name of the branch site.</span></span>
    
4. <span data-ttu-id="3e834-124">) **설명을**클릭 한 다음 분기 사이트에 대 한 의미 있는 설명을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e834-124">(Optional) Click **Description**, and then type a meaningful description for the branch site.</span></span>
    
5. <span data-ttu-id="3e834-125">**다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e834-125">Click **Next**.</span></span>
    
6. <span data-ttu-id="3e834-126">) 다음 **새 분기 사이트 정의** 대화 상자에서 다음 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e834-126">(Optional) In the next **Define New Branch Site** dialog box, do any of the following:</span></span> 
    
    1. <span data-ttu-id="3e834-127">**도시**를 클릭 한 다음 지점 사이트가 있는 도시의 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e834-127">Click **City**, and then type the name of the city in which the branch site is located.</span></span>
    
    2. <span data-ttu-id="3e834-128">**상태/지역을**클릭 한 다음 분기 사이트가 있는 상태 또는 지역의 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e834-128">Click **State/Region**, and then type the name of the state or region in which the branch site is located.</span></span>
    
    3. <span data-ttu-id="3e834-129">**국가 코드**를 클릭 한 다음 분기 사이트가 있는 국가/지역에 대 한 두 자리 통화 코드를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e834-129">Click **Country Code**, and then type the two-digit calling code for the country/region in which the branch site is located.</span></span>
    
7. <span data-ttu-id="3e834-130">**다음**을 클릭 한 다음이 사이트에서 Survivable Branch 기기 또는 서버를 사용 하는 경우 **마법사를 닫을 때 새 Survivable 마법사 열기** 확인란의 선택을 취소 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e834-130">Click **Next**, and then, if you are using a Survivable Branch Appliance or Server at this site, be sure to clear the **Open the New Survivable Wizard when this wizard closes** check box.</span></span> <span data-ttu-id="3e834-131">**마침을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e834-131">Click **Finish**.</span></span>
    
8. <span data-ttu-id="3e834-132">레거시 SBA를 비즈니스용 Skype 서버 2019 프런트 엔드 풀에 연결 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e834-132">To associate the legacy SBA to the Skype for Business Server 2019 Front End pool:</span></span>
    
    1. <span data-ttu-id="3e834-133">생성 된 분기 사이트를 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e834-133">Expand the branch site that has been created.</span></span> 
    
    2. <span data-ttu-id="3e834-134">이전 버전을 마우스 오른쪽 단추로 클릭 한 다음 **새로 만들기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e834-134">Right-click on legacy version, and then click **New**.</span></span>
    
    3. <span data-ttu-id="3e834-135">**Survivable Branch 기기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e834-135">Click **Survivable Branch Appliance**.</span></span>
    
9. <span data-ttu-id="3e834-136">열리는 마법사의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="3e834-136">Follow the directions in the wizard that opens.</span></span> <span data-ttu-id="3e834-137">마법사 항목에 대 한 자세한 내용은 다음을 참고 하세요.</span><span class="sxs-lookup"><span data-stu-id="3e834-137">For information about wizard items, see</span></span>    
   <!-- [Define a Survivable Branch Appliance or Server in Lync 2013](https://technet.microsoft.com/en-us/library/gg398280(v=ocs.15).aspx). -->
   <!-- The above link points to un-rebranded 2013 content we will need to discuss rebrand or bring forward -->
    
    > [!NOTE]
    > <span data-ttu-id="3e834-138">Survivable Branch 기기는 모니터링 저장소에만 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e834-138">A Survivable Branch Appliance can only be associated with a Monitoring Store.</span></span> 
  
10. <span data-ttu-id="3e834-139">이 사이트에서 Survivable Branch 기기 또는 서버를 사용 하 고 있지 않은 경우 마법사를 **닫을 때 새 Survivable 마법사 열기** 확인란의 선택을 취소 하 고 **마침을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e834-139">If you are not using a Survivable Branch Appliance or Server at this site, clear the **Open the New Survivable Wizard when this wizard closes** check box, and then click **Finish**.</span></span>
    
11. <span data-ttu-id="3e834-140">토폴로지에 추가 하려는 각 분기 사이트에 대해 앞의 단계를 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e834-140">Repeat the previous steps for each branch site you want to add to the topology.</span></span>
    

