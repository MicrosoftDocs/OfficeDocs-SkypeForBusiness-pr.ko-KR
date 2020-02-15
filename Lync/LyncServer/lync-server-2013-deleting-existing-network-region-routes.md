---
title: 'Lync Server 2013: 기존 네트워크 지역 경로 삭제'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting existing network region routes
ms:assetid: 6256ff80-5f1e-48b4-928b-24aeb3c1a0e7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688074(v=OCS.15)
ms:contentKeyID: 49733669
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 030980ca18e21915f514435a8682ec8ddcf78286
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048659"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deleting-existing-network-region-routes-in-lync-server-2013"></a><span data-ttu-id="cb460-102">Lync Server 2013에서 기존 네트워크 지역 경로 삭제</span><span class="sxs-lookup"><span data-stu-id="cb460-102">Deleting existing network region routes in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cb460-103">_**마지막으로 수정 된 항목:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="cb460-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="cb460-104">CAC(통화 허용 제어) 구성 내의 모든 지역에는 다른 모든 지역에 액세스할 수 있는 방법이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb460-104">Every region within a call admission control (CAC) configuration must have some way to access every other region.</span></span> <span data-ttu-id="cb460-105">지역 링크는 지역 간 연결에 대한 대역폭 제한을 설정하고 실제 링크를 나타내며, 경로는 한 지역에서 다른 지역으로 연결이 트래버스되는 연결된 경로를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="cb460-105">While region links set bandwidth limitations on the connections between regions and also represent the physical links, a route determines which linked path the connection will traverse from one region to another.</span></span> <span data-ttu-id="cb460-106">Lync Server 제어판을 사용 하 여 네트워크 지역 경로를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb460-106">You can use Lync Server Control Panel to configure network region routes.</span></span> <span data-ttu-id="cb460-107">Lync Server 제어판에서는 네트워크 지역 경로를 만들거나 수정 하거나 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb460-107">From Lync Server Control Panel, you can create, modify, or delete a network region route.</span></span> <span data-ttu-id="cb460-108">이 항목을 사용 하 여 기존 네트워크 지역 경로를 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb460-108">Use this topic to delete existing network region routes.</span></span> <span data-ttu-id="cb460-109">네트워크 지역 경로를 만들거나 수정 하는 방법에 대 한 자세한 내용은 [Lync Server 2013에서 네트워크 지역 경로 만들기 또는 수정을](lync-server-2013-creating-or-modifying-network-region-routes.md)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="cb460-109">For details about creating or modifying network region routes, see [Creating or modifying network region routes in Lync Server 2013](lync-server-2013-creating-or-modifying-network-region-routes.md).</span></span>

<div>

## <a name="to-delete-a-network-region-route"></a><span data-ttu-id="cb460-110">네트워크 지역 경로를 삭제 하려면</span><span class="sxs-lookup"><span data-stu-id="cb460-110">To delete a network region route</span></span>

1.  <span data-ttu-id="cb460-111">RTCUniversalServerAdmins 그룹의 구성원 인 사용자 계정 (또는 이와 동등한 사용자 권한 포함) 또는 CsAdministrator 역할이 할당 되 면 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb460-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="cb460-112">브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="cb460-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="cb460-113">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="cb460-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="cb460-114">왼쪽 탐색 모음에서 **네트워크 구성**을 클릭한 다음 **지역 경로**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="cb460-114">In the left navigation bar, click **Network Configuration** and then click **Region Route**.</span></span>

4.  <span data-ttu-id="cb460-115">**지역 경로** 페이지에서 삭제할 지역 경로를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb460-115">On the **Region Route** page, click the region route that you want to delete.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="cb460-116">한 번에 두 개 이상의 지역 경로를 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb460-116">You can delete more than one region route at a time.</span></span> <span data-ttu-id="cb460-117">이 작업을 수행 하려면 CTRL 키를 누른 상태로 여러 지역 경로를 선택 하 고 CTRL을 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="cb460-117">To do this, press CTRL and select multiple region routes while holding down the CTRL key.</span></span> <span data-ttu-id="cb460-118">모든 지역 경로를 선택 하려면 <STRONG>편집</STRONG> 메뉴에서 <STRONG>모두 선택을</STRONG> 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb460-118">Or, to select all region routes, click <STRONG>Select all</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

    
    </div>

5.  <span data-ttu-id="cb460-119">**편집** 메뉴에서 **삭제**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="cb460-119">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="cb460-120">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="cb460-120">Click **OK**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="cb460-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cb460-121">See Also</span></span>


[<span data-ttu-id="cb460-122">Lync Server 2013에서 네트워크 지역 경로 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="cb460-122">Creating or modifying network region routes in Lync Server 2013</span></span>](lync-server-2013-creating-or-modifying-network-region-routes.md)  


<span data-ttu-id="cb460-123">[네트워크 지역 경로 구성](https://technet.microsoft.com/library/gg133706\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="cb460-123">[Configure a Network Region Route](https://technet.microsoft.com/library/gg133706\(v=ocs.15\))</span></span>  


[<span data-ttu-id="cb460-124">새-Csnetworkinterroute</span><span class="sxs-lookup"><span data-stu-id="cb460-124">New-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterRegionRoute)  
[<span data-ttu-id="cb460-125">설정-Csnetworkinter지역 경로</span><span class="sxs-lookup"><span data-stu-id="cb460-125">Set-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterRegionRoute)  
[<span data-ttu-id="cb460-126">제거-Csnetworkinterroute</span><span class="sxs-lookup"><span data-stu-id="cb460-126">Remove-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterRegionRoute)  
[<span data-ttu-id="cb460-127">Get-Csnetworkinterroute</span><span class="sxs-lookup"><span data-stu-id="cb460-127">Get-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

