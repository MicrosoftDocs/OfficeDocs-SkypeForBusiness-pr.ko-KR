---
title: 'Lync Server 2013: 네트워크 지역 링크 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring network region links
ms:assetid: 952bc93e-e6aa-4539-85c7-2b15f14eb382
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182551(v=OCS.15)
ms:contentKeyID: 48184829
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5d069bb5215fc977a35481a916f49e86fa644284
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743478"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-network-region-links-in-lync-server-2013"></a><span data-ttu-id="340aa-102">Lync Server 2013에서 네트워크 지역 링크 구성</span><span class="sxs-lookup"><span data-stu-id="340aa-102">Configuring network region links in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="340aa-103">_**마지막으로 수정한 주제:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="340aa-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="340aa-104">두 네트워크 지역 간의 링크를 CAC (call 허용 제어)의 일부로 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="340aa-104">You can configure links between two network regions as part of call admission control (CAC).</span></span> <span data-ttu-id="340aa-105">네트워크 내의 영역은 실제 WAN (광역 네트워크) 연결을 통해 연결 됩니다.</span><span class="sxs-lookup"><span data-stu-id="340aa-105">Regions within a network are linked through physical wide area network (WAN) connectivity.</span></span> <span data-ttu-id="340aa-106">Lync Server 제어판을 사용 하 여 두 네트워크 지역 간의 링크를 정의 하 고 이러한 지역 간의 오디오 및 비디오 연결에 대 한 대역폭 제한을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="340aa-106">You can use the Lync Server Control Panel to define a link between two network regions and set the bandwidth limitations on audio and video connections between these regions.</span></span> <span data-ttu-id="340aa-107">기존 네트워크 지역 링크를 삭제 하는 방법에 대 한 자세한 내용은 [Lync Server 2013에서 네트워크 지역 링크 삭제](lync-server-2013-deleting-network-region-links.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="340aa-107">For details about deleting an existing network region link, see [Deleting network region links in Lync Server 2013](lync-server-2013-deleting-network-region-links.md).</span></span>

<div>

## <a name="to-create-a-network-region-link"></a><span data-ttu-id="340aa-108">네트워크 지역 링크를 만들려면</span><span class="sxs-lookup"><span data-stu-id="340aa-108">To create a network region link</span></span>

1.  <span data-ttu-id="340aa-109">RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsAdministrator 역할에 할당 된 경우 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="340aa-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="340aa-110">브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="340aa-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="340aa-111">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="340aa-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="340aa-112">왼쪽 탐색 모음에서 **네트워크 구성을** 클릭 한 다음 **지역 링크**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="340aa-112">In the left navigation bar, click **Network Configuration** and then click **Region Link**.</span></span>

4.  <span data-ttu-id="340aa-113">**지역 링크** 페이지에서 **새로 만들기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="340aa-113">On the **Region Link** page, click **New**.</span></span>

5.  <span data-ttu-id="340aa-114">**새 영역 링크**의 **이름** 필드에 값을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="340aa-114">In **New Region Link**, type a value in the **Name** field.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="340aa-115">이 값은 Lync Server 2013 배포 내에서 고유 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="340aa-115">This value must be unique within your Lync Server 2013 deployment.</span></span>

    
    </div>

6.  <span data-ttu-id="340aa-116">**네트워크 지역 \#1** 드롭다운 목록에서 연결할 두 지역 중 하나를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="340aa-116">From the **Network region \#1** drop-down list, select one of the two regions to be linked.</span></span>

7.  <span data-ttu-id="340aa-117">**네트워크 지역 \#2** 드롭다운 목록에서 연결할 다른 영역을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="340aa-117">From the **Network region \#2** drop-down list, select the other region to be linked.</span></span> <span data-ttu-id="340aa-118">이 지역은 네트워크 지역 \#1에 대해 선택한 지역과 달라 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="340aa-118">This region must be different from the region selected for Network region \#1.</span></span>

8.  <span data-ttu-id="340aa-119">) 이러한 지역 간의 오디오 또는 비디오 통화에 대 한 대역폭 제한을 설정 하려면 **대역폭 정책** 드롭다운 목록에서 대역폭 정책 프로필을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="340aa-119">(Optional) If you want to place bandwidth limitations on audio or video calls between these regions, select a bandwidth policy profile from the **Bandwidth policy** drop-down list.</span></span>

9.  <span data-ttu-id="340aa-120">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="340aa-120">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-modify-a-network-region-link"></a><span data-ttu-id="340aa-121">네트워크 지역 링크를 수정 하려면</span><span class="sxs-lookup"><span data-stu-id="340aa-121">To modify a network region link</span></span>

1.  <span data-ttu-id="340aa-122">RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsAdministrator 역할에 할당 된 경우 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="340aa-122">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="340aa-123">브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="340aa-123">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="340aa-124">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="340aa-124">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="340aa-125">왼쪽 탐색 모음에서 **네트워크 구성을** 클릭 한 다음 **지역 링크**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="340aa-125">In the left navigation bar, click **Network Configuration** and then click **Region Link**.</span></span>

4.  <span data-ttu-id="340aa-126">**지역 링크** 페이지에서 수정 하려는 지역 링크를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="340aa-126">On the **Region Link** page, click the region link that you want to modify.</span></span>

5.  <span data-ttu-id="340aa-127">**편집** 메뉴에서 **세부 정보 표시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="340aa-127">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="340aa-128">**지역 편집 링크**에서 연결 된 영역이 나이 링크에 대 한 대역폭 정책 프로필을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="340aa-128">In **Edit Region Link**, you can modify the regions that are linked or the bandwidth policy profile for this link.</span></span>

7.  <span data-ttu-id="340aa-129">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="340aa-129">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="340aa-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="340aa-130">See Also</span></span>


[<span data-ttu-id="340aa-131">Lync Server 2013에서 네트워크 지역 링크 삭제</span><span class="sxs-lookup"><span data-stu-id="340aa-131">Deleting network region links in Lync Server 2013</span></span>](lync-server-2013-deleting-network-region-links.md)  


[<span data-ttu-id="340aa-132">새-Csnetwork국가 링크</span><span class="sxs-lookup"><span data-stu-id="340aa-132">New-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegionLink)  
[<span data-ttu-id="340aa-133">Set-Csnetwork국가 링크</span><span class="sxs-lookup"><span data-stu-id="340aa-133">Set-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegionLink)  
[<span data-ttu-id="340aa-134">-Csnetwork국가 링크 제거</span><span class="sxs-lookup"><span data-stu-id="340aa-134">Remove-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegionLink)  
[<span data-ttu-id="340aa-135">Get-Csnetwork국가 링크</span><span class="sxs-lookup"><span data-stu-id="340aa-135">Get-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>
