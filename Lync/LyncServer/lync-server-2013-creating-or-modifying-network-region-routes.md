---
title: 'Lync Server 2013: 네트워크 지역 경로 만들기 또는 수정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Creating or modifying network region routes
ms:assetid: 76993daa-76c2-4cec-8363-de8aebef0145
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521016(v=OCS.15)
ms:contentKeyID: 48184540
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2f31daafe6cafbf74f9f12812f8259c24cfa7349
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982369"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="creating-or-modifying-network-region-routes-in-lync-server-2013"></a><span data-ttu-id="50313-102">Lync Server 2013에서 네트워크 지역 경로 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="50313-102">Creating or modifying network region routes in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="50313-103">_**마지막으로 수정한 주제:** 2012-10-08_</span><span class="sxs-lookup"><span data-stu-id="50313-103">_**Topic Last Modified:** 2012-10-08_</span></span>

<span data-ttu-id="50313-104">CAC (호출 허용 제어) 구성 내의 모든 지역에는 다른 모든 지역에 액세스 하는 방법이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="50313-104">Every region within a call admission control (CAC) configuration must have some way to access every other region.</span></span> <span data-ttu-id="50313-105">지역 링크는 지역 간 연결에 대 한 대역폭 제한을 설정 하 고 실제 링크를 표시 하는 경우 경로에 따라 연결이 한 영역에서 다른 지역으로 이동 하는 연결 경로가 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="50313-105">While region links set bandwidth limitations on the connections between regions and also represent the physical links, a route determines which linked path the connection will traverse from one region to another.</span></span> <span data-ttu-id="50313-106">Lync Server 제어판을 사용 하 여 네트워크 지역 경로를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50313-106">You can use Lync Server Control Panel to configure network region routes.</span></span> <span data-ttu-id="50313-107">Lync Server 제어판에서 네트워크 지역 경로를 만들거나 수정 하거나 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50313-107">From Lync Server Control Panel, you can create, modify, or delete a network region route.</span></span> <span data-ttu-id="50313-108">이 항목을 사용 하 여 네트워크 지역 경로를 만들거나 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="50313-108">Use this topic to create or modify a network region route.</span></span> <span data-ttu-id="50313-109">기존 네트워크 지역 경로를 삭제 하는 방법에 대 한 자세한 내용은 [Lync Server 2013에서 기존 네트워크 지역 경로 삭제](lync-server-2013-deleting-existing-network-region-routes.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="50313-109">For details about deleting an existing network region routes, see [Deleting existing network region routes in Lync Server 2013](lync-server-2013-deleting-existing-network-region-routes.md).</span></span>

<div>

## <a name="to-create-a-network-region-route"></a><span data-ttu-id="50313-110">네트워크 지역 경로를 만들려면</span><span class="sxs-lookup"><span data-stu-id="50313-110">To create a network region route</span></span>

1.  <span data-ttu-id="50313-111">RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsAdministrator 역할에 할당 된 경우 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="50313-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="50313-112">브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="50313-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="50313-113">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="50313-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="50313-114">왼쪽 탐색 모음에서 **네트워크 구성을** 클릭 한 다음 **지역 경로**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="50313-114">In the left navigation bar, click **Network Configuration** and then click **Region Route**.</span></span>

4.  <span data-ttu-id="50313-115">**지역 경로** 페이지에서 **새로 만들기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="50313-115">On the **Region Route** page, click **New**.</span></span>

5.  <span data-ttu-id="50313-116">**새 영역 경로**에서 **이름** 필드에 값을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="50313-116">In **New Region Route**, type a value in the **Name** field.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="50313-117">이 값은 Microsoft Lync Server 2013 배포 내에서 고유 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="50313-117">This value must be unique within your Microsoft Lync Server 2013 deployment.</span></span>

    
    </div>

6.  <span data-ttu-id="50313-118">**네트워크 지역 \#1** 드롭다운 목록에서이 경로로 연결할 두 지역 중 하나를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="50313-118">From the **Network region \#1** drop-down list, select one of the two regions to be connected by this route.</span></span>

7.  <span data-ttu-id="50313-119">**네트워크 지역 \#2** 드롭다운 목록에서이 경로의 다른 지역을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="50313-119">From the **Network region \#2** drop-down list, select the other region for this route.</span></span> <span data-ttu-id="50313-120">이 지역은 네트워크 지역 \#1에 대해 선택한 지역과 달라 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="50313-120">This region must be different from the region selected for Network region \#1.</span></span>

8.  <span data-ttu-id="50313-121">**네트워크 영역 링크** 목록 상자를 사용 하 여 경로에 지역 링크를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="50313-121">Use the **Network region links** list box to add region links to the route.</span></span> <span data-ttu-id="50313-122">**추가** 단추를 클릭 하 여 **지역 링크** 페이지를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="50313-122">Click the **Add** button to display the **Region Link** page.</span></span> <span data-ttu-id="50313-123">이 경로에 추가할 지역 링크를 클릭 한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="50313-123">Click a region link to add to this route, and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="50313-124"><STRONG>추가</STRONG> 단추를 계속 클릭 하 여 다른 링크를 추가 하거나 링크를 선택 하 고 <STRONG>제거</STRONG> 를 클릭 하 여 링크를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="50313-124">Continue to click the <STRONG>Add</STRONG> button to add more links, or select a link and click <STRONG>Remove</STRONG> to remove a link.</span></span>

    
    </div>

9.  <span data-ttu-id="50313-125">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="50313-125">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-modify-a-network-region-route"></a><span data-ttu-id="50313-126">네트워크 지역 경로를 수정 하려면</span><span class="sxs-lookup"><span data-stu-id="50313-126">To modify a network region route</span></span>

1.  <span data-ttu-id="50313-127">RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsAdministrator 역할에 할당 된 경우 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="50313-127">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="50313-128">브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="50313-128">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="50313-129">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="50313-129">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="50313-130">왼쪽 탐색 모음에서 **네트워크 구성을** 클릭 한 다음 **지역 경로**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="50313-130">In the left navigation bar, click **Network Configuration** and then click **Region Route**.</span></span>

4.  <span data-ttu-id="50313-131">**지역 경로** 페이지에서 수정 하려는 지역 경로를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="50313-131">On the **Region Route** page, click the region route that you want to modify.</span></span>

5.  <span data-ttu-id="50313-132">**편집** 메뉴에서 **세부 정보 표시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="50313-132">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="50313-133">**지역 경로 편집**에서이 경로 또는 경로와 연결 된 지역 링크를 통해 연결 된 영역을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50313-133">In **Edit Region Route**, you can modify the regions joined by this route and the region links associated with the route.</span></span>

7.  <span data-ttu-id="50313-134">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="50313-134">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="50313-135">참고 항목</span><span class="sxs-lookup"><span data-stu-id="50313-135">See Also</span></span>


[<span data-ttu-id="50313-136">Lync Server 2013에서 기존 네트워크 지역 경로 삭제</span><span class="sxs-lookup"><span data-stu-id="50313-136">Deleting existing network region routes in Lync Server 2013</span></span>](lync-server-2013-deleting-existing-network-region-routes.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

