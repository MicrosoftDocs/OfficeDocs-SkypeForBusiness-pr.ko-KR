---
title: 'Lync Server 2013: 네트워크 서브넷 정보 보기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Viewing network subnet information
ms:assetid: 46f165f2-efe3-4cc1-9fee-a78b7f2ed41e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688044(v=OCS.15)
ms:contentKeyID: 49733636
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7c0877db4871403c93dffe2fabd0c30df495b9ae
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138109"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="viewing-network-subnet-information-in-lync-server-2013"></a><span data-ttu-id="24eac-102">Lync Server 2013에서 네트워크 서브넷 정보 보기</span><span class="sxs-lookup"><span data-stu-id="24eac-102">Viewing network subnet information in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="24eac-103">_**마지막으로 수정 된 항목:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="24eac-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="24eac-104">다음 절차에 따라 네트워크 서브넷을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24eac-104">You can use the following procedure to view a network subnet.</span></span> <span data-ttu-id="24eac-105">Lync Server 제어판에서는 네트워크 서브넷을 만들거나 수정 하거나 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24eac-105">From the Lync Server Control Panel, you can create, modify, or delete a network subnet.</span></span> <span data-ttu-id="24eac-106">네트워크 서브넷을 만들거나 수정 하는 방법에 대 한 자세한 내용은 [Create or modify network 서브넷 In Lync Server 2013](lync-server-2013-create-or-modify-network-subnets.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="24eac-106">For details about creating or modifying network subnets, see [Create or modify network subnets in Lync Server 2013](lync-server-2013-create-or-modify-network-subnets.md).</span></span>

<div>

## <a name="to-view-a-network-subnet"></a><span data-ttu-id="24eac-107">네트워크 서브넷을 보려면</span><span class="sxs-lookup"><span data-stu-id="24eac-107">To view a network subnet</span></span>

1.  <span data-ttu-id="24eac-108">RTCUniversalServerAdmins 그룹의 구성원 인 사용자 계정 (또는 이와 동등한 사용자 권한 포함) 또는 CsAdministrator 역할이 할당 되 면 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="24eac-108">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="24eac-109">브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="24eac-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="24eac-110">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="24eac-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="24eac-111">왼쪽 탐색 모음에서 **네트워크 구성**을 클릭하고 **서브넷**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="24eac-111">In the left navigation bar, click **Network Configuration** and then click **Subnet**.</span></span>

4.  <span data-ttu-id="24eac-112">**서브넷** 페이지에서 보려는 서브넷을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="24eac-112">On the **Subnet** page, click the subnet that you want to view.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="24eac-113">서브넷을 한 번에 하나만 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24eac-113">You can only view one subnet at a time.</span></span>

    
    </div>

5.  <span data-ttu-id="24eac-114">**편집** 메뉴에서 **세부 정보 표시**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="24eac-114">On the **Edit** menu, click **Show details…**.</span></span>

</div>

<div>

## <a name="viewing-network-subnet-configuration-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="24eac-115">Windows PowerShell Cmdlet을 사용 하 여 네트워크 서브넷 구성 정보 보기</span><span class="sxs-lookup"><span data-stu-id="24eac-115">Viewing Network Subnet Configuration Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="24eac-116">네트워크 서브넷 정보는 Windows PowerShell 및 Get-CsNetworkSubnet cmdlet을 사용 하 여 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24eac-116">Network subnet information can be viewed by using Windows PowerShell and the Get-CsNetworkSubnet cmdlet.</span></span> <span data-ttu-id="24eac-117">이 cmdlet은 Lync Server 2013 관리 셸 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24eac-117">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="24eac-118">원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="24eac-118">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-network-subnet-information"></a><span data-ttu-id="24eac-119">네트워크 서브넷 정보를 보려면</span><span class="sxs-lookup"><span data-stu-id="24eac-119">To view network subnet information</span></span>

  - <span data-ttu-id="24eac-120">모든 네트워크 서브넷에 대 한 정보를 보려면 Lync Server 관리 셸에서 다음 명령을 입력 하 고 enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="24eac-120">To view information about all your network subnets, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsNetworkSubnet
    
    <span data-ttu-id="24eac-121">그러면 다음과 같은 정보가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="24eac-121">That will return information similar to this:</span></span>
    
        Identity      : 172.11.15.0
        MaskBits      : 28
        Description   :
        NetworkSiteID : Redmond
        SubnetID      : 172.11.15.0

</div>

<span data-ttu-id="24eac-122">자세한 내용은 [Get-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet) cmdlet의 도움말 항목을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="24eac-122">For more information, see the help topic for the [Get-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="24eac-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="24eac-123">See Also</span></span>


[<span data-ttu-id="24eac-124">Lync Server 2013에서 네트워크 서브넷 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="24eac-124">Create or modify network subnets in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-network-subnets.md)  
[<span data-ttu-id="24eac-125">Lync Server 2013에서 네트워크 서브넷 삭제</span><span class="sxs-lookup"><span data-stu-id="24eac-125">Deleting network subnets in Lync Server 2013</span></span>](lync-server-2013-deleting-network-subnets.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

