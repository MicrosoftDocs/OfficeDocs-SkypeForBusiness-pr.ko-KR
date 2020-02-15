---
title: 'Lync Server 2013: 네트워크 지역 정보 보기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Viewing network region information
ms:assetid: 665740d0-a3ed-460f-8337-5ed945f90589
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688076(v=OCS.15)
ms:contentKeyID: 49733672
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ed95953b7016264b47d63d53e14442a108320c08
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42028919"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="viewing-network-region-information-in-lync-server-2013"></a><span data-ttu-id="aac79-102">Lync Server 2013에서 네트워크 지역 정보 보기</span><span class="sxs-lookup"><span data-stu-id="aac79-102">Viewing network region information in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="aac79-103">_**마지막으로 수정 된 항목:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="aac79-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="aac79-104">네트워크 지역은 여러 지역의 많은 네트워크 부분을 교차합니다.</span><span class="sxs-lookup"><span data-stu-id="aac79-104">A network region interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="aac79-105">모든 네트워크 지역은 중앙 사이트와 연결되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aac79-105">Every network region must be associated with a central site.</span></span> <span data-ttu-id="aac79-106">중앙 사이트는 CAC(통화 허용 제어) 대역폭 정책 서비스가 실행되는 데이터 센터 사이트입니다.</span><span class="sxs-lookup"><span data-stu-id="aac79-106">The central site is the data center site on which the call admission control (CAC) bandwidth policy service is running.</span></span> <span data-ttu-id="aac79-107">Lync Server 제어판을 사용 하 여 네트워크 지역을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aac79-107">You can use Lync Server Control Panel to view network regions.</span></span> <span data-ttu-id="aac79-108">네트워크 지역에는 오디오 및 비디오 연결에 대해 인터넷을 통한 대체 경로가 허용되는지 여부를 결정하는 설정이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="aac79-108">Network regions include settings that determine whether alternate paths through the Internet are allowed for audio and video connections.</span></span> <span data-ttu-id="aac79-109">이 항목을 사용하여 기존 네트워크 지역을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="aac79-109">Use this topic to view existing network regions.</span></span> <span data-ttu-id="aac79-110">기존 네트워크 지역을 만들거나 수정 하는 방법에 대 한 자세한 내용은 [Lync Server 2013에서 네트워크 지역 만들기 또는 수정을](lync-server-2013-creating-or-modifying-network-regions.md)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="aac79-110">For details about creating or modifying existing network regions, see [Creating or modifying network regions in Lync Server 2013](lync-server-2013-creating-or-modifying-network-regions.md).</span></span>

<div>

## <a name="to-view-information-about-a-network-region-with-lync-server-control-panel"></a><span data-ttu-id="aac79-111">Lync Server 제어판을 사용 하 여 네트워크 지역에 대 한 정보를 보려면</span><span class="sxs-lookup"><span data-stu-id="aac79-111">To view information about a network region with Lync Server Control Panel</span></span>

1.  <span data-ttu-id="aac79-112">RTCUniversalServerAdmins 그룹의 구성원 인 사용자 계정 (또는 이와 동등한 사용자 권한 포함) 또는 CsAdministrator 역할이 할당 되 면 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="aac79-112">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="aac79-113">브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="aac79-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="aac79-114">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="aac79-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="aac79-115">왼쪽 탐색 표시줄에서 **네트워크 구성**을 클릭한 다음 **지역**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="aac79-115">In the left navigation bar, click **Network Configuration** and then click **Region**.</span></span>

4.  <span data-ttu-id="aac79-116">**지역** 페이지에서 보려는 지역을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="aac79-116">On the **Region** page, click the region you want to view.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="aac79-117">한 번에 한 지역만 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aac79-117">You can only view one region at a time.</span></span>

    
    </div>

5.  <span data-ttu-id="aac79-118">**편집** 메뉴에서 **세부 정보 표시**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="aac79-118">On the **Edit** menu, click **Show details**.</span></span>

</div>

<div>

## <a name="viewing-network-region-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="aac79-119">Windows PowerShell Cmdlet을 사용 하 여 네트워크 지역 정보 보기</span><span class="sxs-lookup"><span data-stu-id="aac79-119">Viewing Network Region Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="aac79-120">Windows PowerShell 및 **Get-CsNetworkRegion** cmdlet을 사용 하 여 네트워크 지역 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aac79-120">You can view network region information by using Windows PowerShell and the **Get-CsNetworkRegion** cmdlet.</span></span> <span data-ttu-id="aac79-121">Lync Server 2013 관리 셸 또는 Windows PowerShell의 원격 세션에서이 cmdlet을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aac79-121">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="aac79-122">원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="aac79-122">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-network-region-information"></a><span data-ttu-id="aac79-123">네트워크 지역 정보를 보려면</span><span class="sxs-lookup"><span data-stu-id="aac79-123">To view network region information</span></span>

  - <span data-ttu-id="aac79-124">모든 네트워크 지역에 대 한 정보를 보려면 Lync Server 관리 셸에서 다음 명령을 입력 하 고 enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="aac79-124">To view information about all your network regions, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsNetworkRegion
    
    <span data-ttu-id="aac79-125">그러면 다음과 같은 정보가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="aac79-125">That will return information similar to this:</span></span>
    
        Identity         : Pacific Northwest
        Description      :
        BypassID         : 3b232b84-2c1d-4da2-8181-e9330bafebe9
        CentralSite      : Site:Redmond1
        BWAlternatePaths : {BWPolicyModality=Audio;AlternatePath=True, 
                           BWPolicyModality=Video;AlternatePath=True}
        NetworkRegionID  : Pacific Northwest

</div>

<span data-ttu-id="aac79-126">자세한 내용은 [Get-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink) cmdlet의 도움말 항목을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="aac79-126">For more information, see the help topic for the [Get-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="aac79-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="aac79-127">See Also</span></span>


[<span data-ttu-id="aac79-128">Lync Server 2013에서 네트워크 지역 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="aac79-128">Creating or modifying network regions in Lync Server 2013</span></span>](lync-server-2013-creating-or-modifying-network-regions.md)  
[<span data-ttu-id="aac79-129">Lync Server 2013에서 기존 네트워크 지역 삭제</span><span class="sxs-lookup"><span data-stu-id="aac79-129">Deleting existing network regions in Lync Server 2013</span></span>](lync-server-2013-deleting-existing-network-regions.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

