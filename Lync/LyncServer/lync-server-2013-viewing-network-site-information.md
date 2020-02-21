---
title: 'Lync Server 2013: 네트워크 사이트 정보 보기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Viewing network site information
ms:assetid: 24a97d98-b168-4016-81bf-c2c478092b87
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687996(v=OCS.15)
ms:contentKeyID: 49733586
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8bf9f10ed66fec57516f14cf17a71692fc360da7
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42211174"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="viewing-network-site-information-in-lync-server-2013"></a><span data-ttu-id="8ac5b-102">Lync Server 2013에서 네트워크 사이트 정보 보기</span><span class="sxs-lookup"><span data-stu-id="8ac5b-102">Viewing network site information in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8ac5b-103">_**마지막으로 수정 된 항목:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="8ac5b-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="8ac5b-104">네트워크 사이트는 CAC(통화 허용 제어) 또는 고급 9-1-1 배포의 각 지역 내에 구성된 사무실 또는 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="8ac5b-104">Network sites are the offices or locations configured within each region of a call admission control (CAC) or Enhanced 9-1-1 deployment.</span></span> <span data-ttu-id="8ac5b-105">Lync Server 2013 제어판 또는 Lync Server 관리 셸에서 네트워크 사이트 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ac5b-105">You can view network site information in either Lync Server 2013 Control Panel or Lync Server Management Shell .</span></span> <span data-ttu-id="8ac5b-106">네트워크 사이트를 만들거나 수정 하는 방법에 대 한 자세한 내용은 [Lync Server 2013에서 네트워크 사이트 만들기 또는 수정을](lync-server-2013-creating-or-modifying-network-sites.md)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="8ac5b-106">For details about creating or modifying network sites, see [Creating or modifying network sites in Lync Server 2013](lync-server-2013-creating-or-modifying-network-sites.md).</span></span>

<div>

## <a name="to-view-network-site-information-in-lync-server-control-panel"></a><span data-ttu-id="8ac5b-107">Lync Server 제어판에서 네트워크 사이트 정보를 보려면</span><span class="sxs-lookup"><span data-stu-id="8ac5b-107">To view network site information in Lync Server Control Panel</span></span>

1.  <span data-ttu-id="8ac5b-108">RTCUniversalServerAdmins 그룹의 구성원 인 사용자 계정 (또는 이와 동등한 사용자 권한 포함) 또는 CsAdministrator 역할이 할당 되 면 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ac5b-108">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="8ac5b-109">브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="8ac5b-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="8ac5b-110">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="8ac5b-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="8ac5b-111">왼쪽 탐색 모음에서 **네트워크 구성**을 클릭하고 **사이트**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8ac5b-111">In the left navigation bar, click **Network Configuration** and then click **Site**.</span></span>

4.  <span data-ttu-id="8ac5b-112">**사이트** 페이지에서 보려는 사이트를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ac5b-112">On the **Site** page, click the site that you want to view.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="8ac5b-113">한 번에 한 사이트에 대 한 정보만 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ac5b-113">You can only view information for one site at a time.</span></span>

    
    </div>

5.  <span data-ttu-id="8ac5b-114">**편집** 메뉴에서 **자세한 정보 표시**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8ac5b-114">On the **Edit** menu, click **Show details**.</span></span>

</div>

<div>

## <a name="viewing-network-site-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="8ac5b-115">Windows PowerShell Cmdlet을 사용 하 여 네트워크 사이트 정보 보기</span><span class="sxs-lookup"><span data-stu-id="8ac5b-115">Viewing Network Site Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="8ac5b-116">Windows PowerShell 및 Get-CsNetworkSite cmdlet을 사용 하 여 네트워크 사이트 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ac5b-116">You can view network site information by using Windows PowerShell and the Get-CsNetworkSite cmdlet.</span></span> <span data-ttu-id="8ac5b-117">이 cmdlet은 Lync Server 2013 관리 셸 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ac5b-117">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="8ac5b-118">원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8ac5b-118">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-network-site-information"></a><span data-ttu-id="8ac5b-119">네트워크 사이트 정보를 보려면</span><span class="sxs-lookup"><span data-stu-id="8ac5b-119">To view network site information</span></span>

  - <span data-ttu-id="8ac5b-120">모든 네트워크 사이트에 대 한 정보를 보려면 Lync Server 관리 셸에서 다음 명령을 입력 하 고 enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="8ac5b-120">To view information about all your network sites, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsNetworkSite
    
    <span data-ttu-id="8ac5b-121">그러면 다음과 같은 정보가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="8ac5b-121">That will return information similar to this:</span></span>
    
        Identity          : Redmond
        NetworkSiteID     : Redmond
        Description       :
        NetworkRegionID   : Pacific Northwest
        BypassID          : 3b232b84-2c1d-4da2-8181-e9330bafebe9
        BWPolicyProfileID :
        LocationPolicy    :

</div>

<span data-ttu-id="8ac5b-122">자세한 내용은 [Get-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite) cmdlet에 대 한 도움말 항목을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="8ac5b-122">For more information, see the help topic for the [Get-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="8ac5b-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8ac5b-123">See Also</span></span>


[<span data-ttu-id="8ac5b-124">Lync Server 2013에서 네트워크 사이트 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="8ac5b-124">Creating or modifying network sites in Lync Server 2013</span></span>](lync-server-2013-creating-or-modifying-network-sites.md)  
[<span data-ttu-id="8ac5b-125">Lync Server 2013에서 기존 네트워크 사이트 삭제</span><span class="sxs-lookup"><span data-stu-id="8ac5b-125">Deleting an existing network site in Lync Server 2013</span></span>](lync-server-2013-deleting-an-existing-network-site.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

