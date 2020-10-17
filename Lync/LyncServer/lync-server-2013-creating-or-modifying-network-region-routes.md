---
title: 'Lync Server 2013: 네트워크 지역 경로 만들기 또는 수정'
description: 'Lync Server 2013: 네트워크 지역 경로를 만들거나 수정 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Creating or modifying network region routes
ms:assetid: 76993daa-76c2-4cec-8363-de8aebef0145
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521016(v=OCS.15)
ms:contentKeyID: 48184540
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 89106c905419778776ea16341f247027d49f1195
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544094"
---
# <a name="creating-or-modifying-network-region-routes-in-lync-server-2013"></a><span data-ttu-id="11e5c-103">Lync Server 2013에서 네트워크 지역 경로 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="11e5c-103">Creating or modifying network region routes in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="11e5c-104">_**마지막으로 수정 된 항목:** 2012-10-08_</span><span class="sxs-lookup"><span data-stu-id="11e5c-104">_**Topic Last Modified:** 2012-10-08_</span></span>

<span data-ttu-id="11e5c-105">CAC(통화 허용 제어) 구성 내의 모든 지역에는 다른 모든 지역에 액세스할 수 있는 방법이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="11e5c-105">Every region within a call admission control (CAC) configuration must have some way to access every other region.</span></span> <span data-ttu-id="11e5c-106">지역 링크는 지역 간 연결에 대한 대역폭 제한을 설정하고 실제 링크를 나타내며, 경로는 한 지역에서 다른 지역으로 연결이 트래버스되는 연결된 경로를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="11e5c-106">While region links set bandwidth limitations on the connections between regions and also represent the physical links, a route determines which linked path the connection will traverse from one region to another.</span></span> <span data-ttu-id="11e5c-107">Lync Server 제어판을 사용 하 여 네트워크 지역 경로를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11e5c-107">You can use Lync Server Control Panel to configure network region routes.</span></span> <span data-ttu-id="11e5c-108">Lync Server 제어판에서는 네트워크 지역 경로를 만들거나 수정 하거나 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11e5c-108">From Lync Server Control Panel, you can create, modify, or delete a network region route.</span></span> <span data-ttu-id="11e5c-109">이 항목의 정보에 따라 네트워크 지역을 만들거나 수정하십시오.</span><span class="sxs-lookup"><span data-stu-id="11e5c-109">Use this topic to create or modify a network region route.</span></span> <span data-ttu-id="11e5c-110">기존 네트워크 지역 경로를 삭제 하는 방법에 대 한 자세한 내용은 [Lync Server 2013에서 기존 네트워크 지역 경로 삭제](lync-server-2013-deleting-existing-network-region-routes.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="11e5c-110">For details about deleting an existing network region routes, see [Deleting existing network region routes in Lync Server 2013](lync-server-2013-deleting-existing-network-region-routes.md).</span></span>

<div>

## <a name="to-create-a-network-region-route"></a><span data-ttu-id="11e5c-111">네트워크 지역 경로를 만들려면</span><span class="sxs-lookup"><span data-stu-id="11e5c-111">To create a network region route</span></span>

1.  <span data-ttu-id="11e5c-112">RTCUniversalServerAdmins 그룹의 구성원 인 사용자 계정 (또는 이와 동등한 사용자 권한 포함) 또는 CsAdministrator 역할이 할당 되 면 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="11e5c-112">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="11e5c-113">브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="11e5c-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="11e5c-114">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="11e5c-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="11e5c-115">왼쪽 탐색 모음에서 **네트워크 구성**을 클릭한 다음 **지역 경로**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="11e5c-115">In the left navigation bar, click **Network Configuration** and then click **Region Route**.</span></span>

4.  <span data-ttu-id="11e5c-116">**지역 경로** 페이지에서 **새로 만들기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="11e5c-116">On the **Region Route** page, click **New**.</span></span>

5.  <span data-ttu-id="11e5c-117">**새 지역 경로**에서 **이름** 필드에 값을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="11e5c-117">In **New Region Route**, type a value in the **Name** field.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="11e5c-118">이 값은 Microsoft Lync Server 2013 배포 내에서 고유 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="11e5c-118">This value must be unique within your Microsoft Lync Server 2013 deployment.</span></span>

    
    </div>

6.  <span data-ttu-id="11e5c-119">**네트워크 지역 \# 1** 드롭다운 목록에서이 경로를 사용 하 여 연결할 두 지역 중 하나를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="11e5c-119">From the **Network region \#1** drop-down list, select one of the two regions to be connected by this route.</span></span>

7.  <span data-ttu-id="11e5c-120">**네트워크 지역 \# 2** 드롭다운 목록에서이 경로의 다른 지역을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="11e5c-120">From the **Network region \#2** drop-down list, select the other region for this route.</span></span> <span data-ttu-id="11e5c-121">이 지역은 네트워크 지역 1에 대해 선택 된 지역과 달라 야 합니다 \# .</span><span class="sxs-lookup"><span data-stu-id="11e5c-121">This region must be different from the region selected for Network region \#1.</span></span>

8.  <span data-ttu-id="11e5c-p104">**네트워크 지역 링크** 목록 상자를 사용하여 경로에 지역 링크를 추가합니다. **추가** 단추를 클릭하여 **지역 링크** 페이지를 표시합니다. 이 경로에 추가할 지역 링크를 클릭한 다음 **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="11e5c-p104">Use the **Network region links** list box to add region links to the route. Click the **Add** button to display the **Region Link** page. Click a region link to add to this route, and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="11e5c-125">계속해서 링크를 더 추가하려면 <STRONG>추가</STRONG> 단추를 클릭하고 링크를 제거하려면 링크를 선택하고 <STRONG>제거</STRONG>를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="11e5c-125">Continue to click the <STRONG>Add</STRONG> button to add more links, or select a link and click <STRONG>Remove</STRONG> to remove a link.</span></span>

    
    </div>

9.  <span data-ttu-id="11e5c-126">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="11e5c-126">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-modify-a-network-region-route"></a><span data-ttu-id="11e5c-127">네트워크 지역 경로를 수정하려면</span><span class="sxs-lookup"><span data-stu-id="11e5c-127">To modify a network region route</span></span>

1.  <span data-ttu-id="11e5c-128">RTCUniversalServerAdmins 그룹의 구성원 인 사용자 계정 (또는 이와 동등한 사용자 권한 포함) 또는 CsAdministrator 역할이 할당 되 면 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="11e5c-128">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="11e5c-129">브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="11e5c-129">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="11e5c-130">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="11e5c-130">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="11e5c-131">왼쪽 탐색 모음에서 **네트워크 구성**을 클릭한 다음 **지역 경로**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="11e5c-131">In the left navigation bar, click **Network Configuration** and then click **Region Route**.</span></span>

4.  <span data-ttu-id="11e5c-132">**지역 경로** 페이지에서 수정할 지역 경로를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="11e5c-132">On the **Region Route** page, click the region route that you want to modify.</span></span>

5.  <span data-ttu-id="11e5c-133">**편집** 메뉴에서 **세부 정보 표시**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="11e5c-133">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="11e5c-134">**지역 경로 편집**에서 이 경로에 참가하는 지역 및 해당 경로와 연결된 지역 링크를 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11e5c-134">In **Edit Region Route**, you can modify the regions joined by this route and the region links associated with the route.</span></span>

7.  <span data-ttu-id="11e5c-135">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="11e5c-135">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="11e5c-136">참고 항목</span><span class="sxs-lookup"><span data-stu-id="11e5c-136">See Also</span></span>


[<span data-ttu-id="11e5c-137">Lync Server 2013에서 기존 네트워크 지역 경로 삭제</span><span class="sxs-lookup"><span data-stu-id="11e5c-137">Deleting existing network region routes in Lync Server 2013</span></span>](lync-server-2013-deleting-existing-network-region-routes.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

