---
title: 'Lync Server 2013: 네트워크 지역 링크 정보 보기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Viewing network region link information
ms:assetid: 7b6b2ea2-83d8-4376-afb2-70e5d2cf6444
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688102(v=OCS.15)
ms:contentKeyID: 49733701
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 935d1a98bd4f446ec8861ae8382eb724611a945f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757282"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="viewing-network-region-link-information-in-lync-server-2013"></a><span data-ttu-id="4c975-102">Lync Server 2013에서 네트워크 지역 링크 정보 보기</span><span class="sxs-lookup"><span data-stu-id="4c975-102">Viewing network region link information in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4c975-103">_**마지막으로 수정한 주제:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="4c975-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="4c975-104">호출 허용 제어 (CAC)의 일부로 두 네트워크 지역 간 링크를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c975-104">You can view links between two network regions as part of call admission control (CAC).</span></span> <span data-ttu-id="4c975-105">네트워크 내의 영역은 실제 WAN (광역 네트워크) 연결을 통해 연결 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4c975-105">Regions within a network are linked through physical wide area network (WAN) connectivity.</span></span> <span data-ttu-id="4c975-106">Lync Server 제어판을 사용 하 여 두 네트워크 지역 간의 기존 링크를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c975-106">You can use the Lync Server Control Panel to view an existing link between two network regions.</span></span> <span data-ttu-id="4c975-107">네트워크 지역 링크를 만들거나 수정 하는 방법에 대 한 자세한 내용은 [Lync Server 2013에서 네트워크 지역 링크 구성을](lync-server-2013-configuring-network-region-links.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4c975-107">For details about creating or modifying network region link, see [Configuring network region links in Lync Server 2013](lync-server-2013-configuring-network-region-links.md).</span></span>

<div>

## <a name="to-view-a-network-region-link-in-lync-server-control-panel"></a><span data-ttu-id="4c975-108">Lync Server 제어판에서 네트워크 지역 링크를 보려면</span><span class="sxs-lookup"><span data-stu-id="4c975-108">To view a network region link in Lync Server Control Panel</span></span>

1.  <span data-ttu-id="4c975-109">RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsAdministrator 역할에 할당 된 경우 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c975-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="4c975-110">브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="4c975-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="4c975-111">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4c975-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="4c975-112">왼쪽 탐색 모음에서 **네트워크 구성을** 클릭 한 다음 **지역 링크**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c975-112">In the left navigation bar, click **Network Configuration** and then click **Region Link**.</span></span>

4.  <span data-ttu-id="4c975-113">**지역 링크** 페이지에서 보려는 지역 링크를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c975-113">On the **Region Link** page, click the region link that you want to view.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="4c975-114">한 번에 하나의 지역 링크에 대 한 정보만 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c975-114">You can only view information about one region link at a time.</span></span>

    
    </div>

5.  <span data-ttu-id="4c975-115">**편집** 메뉴에서 **세부 정보 표시**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c975-115">From the **Edit** menu, select **Show details**.</span></span>

</div>

<div>

## <a name="viewing-network-region-link-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="4c975-116">Windows PowerShell Cmdlet을 사용 하 여 네트워크 지역 링크 정보 보기</span><span class="sxs-lookup"><span data-stu-id="4c975-116">Viewing Network Region Link Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="4c975-117">Windows PowerShell 및 **Get-Csnetworkregion 링크** cmdlet을 사용 하 여 네트워크 지역 링크를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c975-117">You can view network region links by using Windows PowerShell and the **Get-CsNetworkRegionLink** cmdlet.</span></span> <span data-ttu-id="4c975-118">Lync Server 2013 관리 셸에서 또는 Windows PowerShell의 원격 세션에서이 cmdlet을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c975-118">You can run this cmdlet from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="4c975-119">원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4c975-119">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-network-region-link-information"></a><span data-ttu-id="4c975-120">네트워크 지역 링크 정보를 보려면</span><span class="sxs-lookup"><span data-stu-id="4c975-120">To view network region link information</span></span>

  - <span data-ttu-id="4c975-121">모든 네트워크 지역 링크에 대 한 정보를 보려면 Lync Server 관리 셸에서 다음 명령을 입력 한 다음 enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="4c975-121">To view information about all your network region links, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsNetworkRegionLink
    
    <span data-ttu-id="4c975-122">이 명령은 다음과 같은 정보를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c975-122">This command returns information similar to the following:</span></span>
    
        Identity            : NorthwestToCalifornia
        BWPolicyProfileID   :
        NetworkRegionLinkID : NorthwestToCalifornia
        NetworkRegionID1    : Pacific Northwest
        NetworkRegionID2    : California

</div>

<span data-ttu-id="4c975-123">자세한 내용은 [Get-Csnetwork국가 링크](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4c975-123">For details, see [Get-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="4c975-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4c975-124">See Also</span></span>


[<span data-ttu-id="4c975-125">Lync Server 2013에서 네트워크 사이트 링크 구성</span><span class="sxs-lookup"><span data-stu-id="4c975-125">Configuring network site links in Lync Server 2013</span></span>](lync-server-2013-configuring-network-site-links.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

