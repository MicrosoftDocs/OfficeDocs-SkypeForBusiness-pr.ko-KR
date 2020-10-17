---
title: 'Lync Server 2013: 네트워크 서브넷 정보 보기'
description: 'Lync Server 2013: 네트워크 서브넷 정보를 확인 합니다.'
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
ms.openlocfilehash: 313135c43318817391d54f2fa3e73dd318f7a11f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546154"
---
# <a name="viewing-network-subnet-information-in-lync-server-2013"></a><span data-ttu-id="1bd39-103">Lync Server 2013에서 네트워크 서브넷 정보 보기</span><span class="sxs-lookup"><span data-stu-id="1bd39-103">Viewing network subnet information in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1bd39-104">_**마지막으로 수정 된 항목:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="1bd39-104">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="1bd39-105">다음 절차에 따라 네트워크 서브넷을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1bd39-105">You can use the following procedure to view a network subnet.</span></span> <span data-ttu-id="1bd39-106">Lync Server 제어판에서는 네트워크 서브넷을 만들거나 수정 하거나 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1bd39-106">From the Lync Server Control Panel, you can create, modify, or delete a network subnet.</span></span> <span data-ttu-id="1bd39-107">네트워크 서브넷을 만들거나 수정 하는 방법에 대 한 자세한 내용은 [Create or modify network 서브넷 In Lync Server 2013](lync-server-2013-create-or-modify-network-subnets.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="1bd39-107">For details about creating or modifying network subnets, see [Create or modify network subnets in Lync Server 2013](lync-server-2013-create-or-modify-network-subnets.md).</span></span>

<div>

## <a name="to-view-a-network-subnet"></a><span data-ttu-id="1bd39-108">네트워크 서브넷을 보려면</span><span class="sxs-lookup"><span data-stu-id="1bd39-108">To view a network subnet</span></span>

1.  <span data-ttu-id="1bd39-109">RTCUniversalServerAdmins 그룹의 구성원 인 사용자 계정 (또는 이와 동등한 사용자 권한 포함) 또는 CsAdministrator 역할이 할당 되 면 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="1bd39-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="1bd39-110">브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="1bd39-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="1bd39-111">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="1bd39-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="1bd39-112">왼쪽 탐색 모음에서 **네트워크 구성**을 클릭하고 **서브넷**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1bd39-112">In the left navigation bar, click **Network Configuration** and then click **Subnet**.</span></span>

4.  <span data-ttu-id="1bd39-113">**서브넷** 페이지에서 보려는 서브넷을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1bd39-113">On the **Subnet** page, click the subnet that you want to view.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1bd39-114">서브넷을 한 번에 하나만 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1bd39-114">You can only view one subnet at a time.</span></span>

    
    </div>

5.  <span data-ttu-id="1bd39-115">**편집** 메뉴에서 **세부 정보 표시**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1bd39-115">On the **Edit** menu, click **Show details…**.</span></span>

</div>

<div>

## <a name="viewing-network-subnet-configuration-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="1bd39-116">Windows PowerShell Cmdlet을 사용 하 여 네트워크 서브넷 구성 정보 보기</span><span class="sxs-lookup"><span data-stu-id="1bd39-116">Viewing Network Subnet Configuration Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="1bd39-117">네트워크 서브넷 정보는 Windows PowerShell 및 Get-CsNetworkSubnet cmdlet을 사용 하 여 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1bd39-117">Network subnet information can be viewed by using Windows PowerShell and the Get-CsNetworkSubnet cmdlet.</span></span> <span data-ttu-id="1bd39-118">이 cmdlet은 Lync Server 2013 관리 셸 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1bd39-118">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="1bd39-119">원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 사용 하 여 Microsoft Lync Server 2010 관리"를 참조 [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 하세요.</span><span class="sxs-lookup"><span data-stu-id="1bd39-119">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-network-subnet-information"></a><span data-ttu-id="1bd39-120">네트워크 서브넷 정보를 보려면</span><span class="sxs-lookup"><span data-stu-id="1bd39-120">To view network subnet information</span></span>

  - <span data-ttu-id="1bd39-121">모든 네트워크 서브넷에 대 한 정보를 보려면 Lync Server 관리 셸에서 다음 명령을 입력 하 고 enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="1bd39-121">To view information about all your network subnets, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsNetworkSubnet
    
    <span data-ttu-id="1bd39-122">그러면 다음과 같은 정보가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="1bd39-122">That will return information similar to this:</span></span>
    
        Identity      : 172.11.15.0
        MaskBits      : 28
        Description   :
        NetworkSiteID : Redmond
        SubnetID      : 172.11.15.0

</div>

<span data-ttu-id="1bd39-123">자세한 내용은 [Get-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet) cmdlet의 도움말 항목을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="1bd39-123">For more information, see the help topic for the [Get-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="1bd39-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1bd39-124">See Also</span></span>


[<span data-ttu-id="1bd39-125">Lync Server 2013에서 네트워크 서브넷 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="1bd39-125">Create or modify network subnets in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-network-subnets.md)  
[<span data-ttu-id="1bd39-126">Lync Server 2013에서 네트워크 서브넷 삭제</span><span class="sxs-lookup"><span data-stu-id="1bd39-126">Deleting network subnets in Lync Server 2013</span></span>](lync-server-2013-deleting-network-subnets.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

