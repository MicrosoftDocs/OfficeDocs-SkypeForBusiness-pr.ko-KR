---
title: Lync Server 2013 Sba (survivable Branch 기기 분기 사이트를 토폴로지에 추가
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Add Lync Server 2013 Survivable Branch Appliance branch site to your topology
ms:assetid: d3142a37-4606-456d-8ea9-6cc0e51e55f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721896(v=OCS.15)
ms:contentKeyID: 49733830
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bfc267d20b9df284e458ff5883cfebb4c1e5b0b0
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145006"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="add-lync-server-2013-survivable-branch-appliance-branch-site-to-your-topology"></a><span data-ttu-id="41ea2-102">Lync Server 2013 Sba (survivable Branch 기기 분기 사이트를 토폴로지에 추가</span><span class="sxs-lookup"><span data-stu-id="41ea2-102">Add Lync Server 2013 Survivable Branch Appliance branch site to your topology</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="41ea2-103">_**마지막으로 수정 된 항목:** 2012-10-07_</span><span class="sxs-lookup"><span data-stu-id="41ea2-103">_**Topic Last Modified:** 2012-10-07_</span></span>

<span data-ttu-id="41ea2-104">Microsoft Lync Server 2013 Sba (survivable Branch 기기 (SBA)는 Microsoft Lync Server 2010 프런트 엔드 풀 (백업 등록자)에 연결할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="41ea2-104">Microsoft Lync Server 2013 Survivable Branch Appliances (SBA) cannot be associated to a Microsoft Lync Server 2010 Front End pool as a backup Registrar.</span></span> <span data-ttu-id="41ea2-105">SBA는 Microsoft Lync Server 2013 프런트 엔드 풀과 연결 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="41ea2-105">The SBA must be associated with a Microsoft Lync Server 2013 Front End pool.</span></span> <span data-ttu-id="41ea2-106">이 단계에서는 Microsoft Lync Server 2013 SBA를 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="41ea2-106">These steps assume a Microsoft Lync Server 2013 SBA.</span></span> <span data-ttu-id="41ea2-107">이 절차는 중앙 사이트에서 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="41ea2-107">Perform this procedure at the central site.</span></span>

<div>

## <a name="to-add-branch-sites-with-microsoft-lync-server-2013-sba-to-your-topology"></a><span data-ttu-id="41ea2-108">토폴로지에 Microsoft Lync Server 2013 SBA가 있는 분기 사이트를 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="41ea2-108">To add branch sites with Microsoft Lync Server 2013 SBA to your topology</span></span>

1.  <span data-ttu-id="41ea2-109">토폴로지 작성기 시작: **시작**, **모든 프로그램**, **Microsoft lync server 2013**을 차례로 클릭 한 다음 **Lync server 토폴로지 작성기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="41ea2-109">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="41ea2-110">콘솔 트리에서 중앙 사이트를 확장 하 고 **분기 사이트**를 확장 한 다음 **새 분기 사이트**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="41ea2-110">In the console tree, expand the central site, expand **Branch Sites**, and then click **New Branch Site**.</span></span>

3.  <span data-ttu-id="41ea2-111">**새 분기 사이트 정의** 대화 상자에서 **이름을**클릭 한 다음 새 분기 사이트의 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="41ea2-111">In the **Define New Branch Site** dialog box, click **Name**, and then type a name for the new branch site.</span></span>

4.  <span data-ttu-id="41ea2-112">(선택 사항) **설명**을 클릭한 다음 분기 사이트에 대한 의미 있는 설명을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="41ea2-112">(Optional) Click **Description**, and then type a meaningful description for the branch site.</span></span>

5.  <span data-ttu-id="41ea2-113">**다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="41ea2-113">Click **Next**.</span></span>

6.  <span data-ttu-id="41ea2-114">(선택 사항) 다음 **새 분기 사이트 정의** 대화 상자에서 다음 중 일부를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="41ea2-114">(Optional) In the next **Define New Branch Site** dialog box, do any of the following:</span></span>
    
      - <span data-ttu-id="41ea2-115">**구/군/시**를 클릭한 다음 분기 사이트가 있는 구/군/시의 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="41ea2-115">Click **City**, and then type the name of the city in which the branch site is located.</span></span>
    
      - <span data-ttu-id="41ea2-116">**시/도/지역**을 클릭한 다음 분기 사이트가 있는 시/도/지역의 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="41ea2-116">Click **State/Region**, and then type the name of the state or region in which the branch site is located.</span></span>
    
      - <span data-ttu-id="41ea2-117">국가 코드를 클릭한 다음 분기 사이트가 있는 국가/지역에 대한 두 자리 국가/지역 번호를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="41ea2-117">Click **Country Code**, and then type the two-digit calling code for the country/region in which the branch site is located.</span></span>

7.  <span data-ttu-id="41ea2-118">**다음**을 클릭하고 다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="41ea2-118">Click **Next**, and then do one of the following:</span></span>
    
      - <span data-ttu-id="41ea2-119">이 사이트에서 Sba (survivable Branch 기기나 Sba (survivable Branch Server를 사용 하는 경우 **이 마법사를 닫을 때 새 Sba (survivable 마법사 열기** 확인란을 선택 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="41ea2-119">If you are using a Survivable Branch Appliance or Survivable Branch Server at this site, be sure that the **Open the New Survivable Wizard when this wizard closes** check box is selected.</span></span>
    
      - <span data-ttu-id="41ea2-120">이 사이트에서 Sba (survivable Branch 기기나 Sba (survivable Branch Server를 사용 하지 않는 경우 **이 마법사를 닫을 때 새 Sba (survivable 마법사 열기** 확인란의 선택을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="41ea2-120">If you are not using a Survivable Branch Appliance or Survivable Branch Server at this site, clear the **Open the New Survivable Wizard when this wizard closes** check box.</span></span>
    
      - <span data-ttu-id="41ea2-121">**마침을**클릭 하 고 마법사에서 열리는 지시를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="41ea2-121">Click **Finish**, and then follow the directions in the wizard that opens.</span></span> <span data-ttu-id="41ea2-122">마법사 항목에 대 한 자세한 내용은 [Define a Sba (survivable Branch 어플라이언스 Or Server in a Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="41ea2-122">For information about wizard items, see [Define a Survivable Branch Appliance or Server in Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md).</span></span>

8.  <span data-ttu-id="41ea2-123">토폴로지에 추가할 각 분기 사이트에 대해 앞의 단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="41ea2-123">Repeat the previous steps for each branch site that you want to add to the topology.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="41ea2-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="41ea2-124">See Also</span></span>


[<span data-ttu-id="41ea2-125">Lync Server 2013에서 Sba (survivable Branch 기기 또는 서버 정의</span><span class="sxs-lookup"><span data-stu-id="41ea2-125">Define a Survivable Branch Appliance or Server in Lync Server 2013</span></span>](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)  
[<span data-ttu-id="41ea2-126">Lync Server 2013에서 분기 사이트에 대 한 PSTN 게이트웨이 정의</span><span class="sxs-lookup"><span data-stu-id="41ea2-126">Define a PSTN gateway for a branch site in Lync Server 2013</span></span>](lync-server-2013-define-a-pstn-gateway-for-a-branch-site.md)  
[<span data-ttu-id="41ea2-127">Lync Server 2013의 미디어 바이패스로 트렁크 구성</span><span class="sxs-lookup"><span data-stu-id="41ea2-127">Configure a trunk with media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[<span data-ttu-id="41ea2-128">Lync Server 2013에서 미디어 바이패스 없이 트렁크 구성</span><span class="sxs-lookup"><span data-stu-id="41ea2-128">Configure a trunk without media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-without-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

