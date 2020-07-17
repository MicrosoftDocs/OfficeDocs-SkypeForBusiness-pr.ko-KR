---
title: SBA(Survivable Branch Appliance) 연결
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Connect a Survivable Branch Appliance
ms:assetid: fe3167e2-d1b1-4cd4-bf30-262e0e7d14e8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721948(v=OCS.15)
ms:contentKeyID: 49733886
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a0fcba962129353ddeb5e5f4c77520cf6d127733
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754446"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="connect-a-survivable-branch-appliance"></a><span data-ttu-id="e88d2-102">SBA(Survivable Branch Appliance) 연결</span><span class="sxs-lookup"><span data-stu-id="e88d2-102">Connect a Survivable Branch Appliance</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e88d2-103">_**마지막으로 수정 된 항목:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="e88d2-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="e88d2-104">모든 SBA(Survivable Branch Appliance)는 SBA용 백업 고급 등록자로 작동하는 프런트 엔드 풀과 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="e88d2-104">Every Survivable Branch Appliance (SBA) is associated with a Front End pool which serves as a backup registrar for the SBA.</span></span> <span data-ttu-id="e88d2-105">프런트 엔드 풀을 Lync Server 2013로 마이그레이션하면 해당 풀이 업그레이드 되는 동안 Lync Server 2010 프런트 엔드 풀에서 SBA를 분리 해야 하 고, 풀이 Lync Server 2013로 마이그레이션된 후에는 SBA를 업그레이드 된 프런트 엔드 풀과 다시 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e88d2-105">When the Front End pool is migrated to Lync Server 2013, the SBA must be disassociated from the Lync Server 2010 Front End pool while the pool is upgraded, Once the pool has been migrated to Lync Server 2013, the SBA can be re-associated with the upgraded Front End pool.</span></span> <span data-ttu-id="e88d2-106">토폴로지 작성기의 레거시 Lync Server 2010 토폴로지에서 SBA를 삭제 한 다음 SBA를 Lync Server 2013 토폴로지에 추가 하는 것이 여기에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="e88d2-106">This involves deleting the SBA from the legacy Lync Server 2010 topology in Topology Builder and then adding the SBA to the Lync Server 2013 topology.</span></span> <span data-ttu-id="e88d2-107">레거시 Lync Server 2010 SBA에서 홈 사용자를 먼저 다른 프런트 엔드 풀로 이동한 후 토폴로지에서 해당 SBA를 제거 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e88d2-107">Users homed on the legacy Lync Server 2010 SBA must first be moved to another Front End pool before removing the SBA from the topology.</span></span> <span data-ttu-id="e88d2-108">Lync Server 2013 토폴로지에서 SBA를 추가한 후에는 해당 사용자를 SBA로 다시 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e88d2-108">Once the SBA is added to the Lync Server 2013 topology, those users can then be moved back to the SBA.</span></span> <span data-ttu-id="e88d2-109">이러한 단계는 아래에 요약되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e88d2-109">These steps are summarized below:</span></span>

1.  <span data-ttu-id="e88d2-110">레거시 SBA Lync Server 2010에 있는 분기 사용자를 다른 프런트 엔드 풀로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="e88d2-110">Move branch users homed on the legacy SBA Lync Server 2010 to another Front End pool.</span></span>

2.  <span data-ttu-id="e88d2-111">레거시 Lync Server 2010 토폴로지에서 SBA를 제거 하 여 백업 등록자를 기존 프런트 엔드 풀과 연결 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="e88d2-111">Remove SBA from the legacy Lync Server 2010 topology to disconnect the existing Front End pool as a backup registrar.</span></span>

3.  <span data-ttu-id="e88d2-112">Lync Server 2013 토폴로지에 SBA를 추가 하 고이 새 프런트 엔드 풀을 백업 등록자로 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="e88d2-112">Add SBA to the Lync Server 2013 topology and configure this new Front End pool as the backup registrar.</span></span>

4.  <span data-ttu-id="e88d2-113">분기 사용자를 새 Lync Server 2013 SBA로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="e88d2-113">Move the branch users to the new Lync Server 2013 SBA.</span></span>

<span data-ttu-id="e88d2-114">**Lync Server 2010 SBA 분기 사이트를 토폴로지에 추가**</span><span class="sxs-lookup"><span data-stu-id="e88d2-114">**Add Lync Server 2010 SBA Branch Site to Your Topology**</span></span>

1.  <span data-ttu-id="e88d2-115">**토폴로지 작성기**를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="e88d2-115">Open **Topology Builder**.</span></span>

2.  <span data-ttu-id="e88d2-116">왼쪽 창에서 **분기 사이트**를 마우스 오른쪽 단추로 클릭하고 **새 분기 사이트**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e88d2-116">In the left pane right-click **Branch sites**, and then click **New Branch Site**.</span></span>

3.  <span data-ttu-id="e88d2-117">**새 분기 사이트 정의** 대화 상자에서 **이름**을 클릭한 다음 분기 사이트의 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="e88d2-117">In the **Define New Branch Site** dialog box, click **Name**, and then type the name of the branch site.</span></span>

4.  <span data-ttu-id="e88d2-118">(선택 사항) **설명**을 클릭한 다음 분기 사이트에 대한 의미 있는 설명을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="e88d2-118">(Optional) Click **Description**, and then type a meaningful description for the branch site.</span></span>

5.  <span data-ttu-id="e88d2-119">**다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e88d2-119">Click **Next**.</span></span>

6.  <span data-ttu-id="e88d2-120">(선택 사항) 다음 **새 분기 사이트 정의** 대화 상자에서 다음 중 일부를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="e88d2-120">(Optional) In the next **Define New Branch Site** dialog box, do any of the following:</span></span>
    
    1.  <span data-ttu-id="e88d2-121">**구/군/시**를 클릭한 다음 분기 사이트가 있는 구/군/시의 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="e88d2-121">Click **City**, and then type the name of the city in which the branch site is located.</span></span>
    
    2.  <span data-ttu-id="e88d2-122">**시/도/지역**을 클릭한 다음 분기 사이트가 있는 시/도/지역의 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="e88d2-122">Click **State/Region**, and then type the name of the state or region in which the branch site is located.</span></span>
    
    3.  <span data-ttu-id="e88d2-123">국가 코드를 클릭한 다음 분기 사이트가 있는 국가/지역에 대한 두 자리 국가/지역 번호를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="e88d2-123">Click **Country Code**, and then type the two-digit calling code for the country/region in which the branch site is located.</span></span>

7.  <span data-ttu-id="e88d2-124">**다음**을 클릭하고 다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="e88d2-124">Click **Next**, and then do one of the following:</span></span>
    
    1.  <span data-ttu-id="e88d2-p102">이 사이트에서 Lync 2010 SBA(Survivable Branch Appliance) 또는 Server를 사용 중인 경우 **이 마법사가 닫히면 새 SBA(Survivable Branch Appliance) 마법사를 엽니다.** 옵션의 선택을 취소해야 합니다. **마침**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e88d2-p102">If you are using a Lync 2010 Survivable Branch Appliance or Server at this site, be sure to uncheck the **Open the New Survivable Wizard when this wizard closes** option. Click **Finish**.</span></span>

8.  <span data-ttu-id="e88d2-127">레거시 Lync Server 2010 SBA를 Lync Server 2013 프런트 엔드 풀에 연결 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e88d2-127">To associate the legacy Lync Server 2010 SBA to the Lync Server 2013 Front End pool:</span></span>
    
    1.  <span data-ttu-id="e88d2-128">만들어진 분기 사이트를 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="e88d2-128">Expand the branch site that has been created.</span></span>
    
    2.  <span data-ttu-id="e88d2-129">**Lync Server 2010**을 마우스 오른쪽 단추로 클릭하고 **새로 만들기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e88d2-129">Right click on **Lync Server 2010** and then click **New**.</span></span>
    
    3.  <span data-ttu-id="e88d2-130">**SBA(Survivable Branch Appliance)…** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e88d2-130">Click **Survivable Branch Appliance…**</span></span>

9.  <span data-ttu-id="e88d2-131">표시되는 마법사의 지침을 따르십시오.</span><span class="sxs-lookup"><span data-stu-id="e88d2-131">Follow the directions in the wizard that opens.</span></span> <span data-ttu-id="e88d2-132">마법사 항목에 대 한 자세한 내용은 [Define a Sba (survivable Branch 어플라이언스 Or Server in a Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="e88d2-132">For information about wizard items, see [Define a Survivable Branch Appliance or Server in Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e88d2-133">Lync Server 2010 Sba (survivable Branch 어플라이언스는 Lync Server 2010 모니터링 저장소에만 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e88d2-133">A Lync Server 2010 Survivable Branch Appliance can only be associated with a Lync Server 2010 Monitoring Store.</span></span>

    
    </div>

10. <span data-ttu-id="e88d2-134">이 사이트에서 SBA 또는 지속 가능 분기 서버를 사용하지 않는 경우에는 **이 마법사가 닫히면 새 지속 가능 마법사 열기** 확인란의 선택을 취소한 다음 **마침**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e88d2-134">If you are not using a Survivable Branch Appliance or Server at this site, clear the **Open the New Survivable Wizard when this wizard closes** check box, and then click **Finish**.</span></span>

11. <span data-ttu-id="e88d2-135">토폴로지에 추가할 각 분기 사이트에 대해 이전 단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="e88d2-135">Repeat the previous steps for each branch site you want to add to the topology.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

