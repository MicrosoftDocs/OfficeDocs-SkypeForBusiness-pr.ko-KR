---
title: 'Lync Server 2013: 네트워크 서브넷 삭제'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deleting network subnets
ms:assetid: c1850f38-40a3-48c9-b6f1-f181c5e63b6b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721873(v=OCS.15)
ms:contentKeyID: 49733806
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 93806d3e9d5f0cb7f004a90d6f461b363aff65f0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978936"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deleting-network-subnets-in-lync-server-2013"></a><span data-ttu-id="3a843-102">Lync Server 2013에서 네트워크 서브넷 삭제</span><span class="sxs-lookup"><span data-stu-id="3a843-102">Deleting network subnets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3a843-103">_**마지막으로 수정한 주제:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="3a843-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="3a843-104">다음 절차를 사용 하 여 서브넷을 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a843-104">You can use the following procedure to delete a subnet.</span></span> <span data-ttu-id="3a843-105">Lync Server 제어판에서 네트워크 서브넷을 만들거나 수정 하거나 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a843-105">From the Lync Server Control Panel, you can create, modify, or delete a network subnet.</span></span> <span data-ttu-id="3a843-106">네트워크 서브넷을 만들거나 수정 하는 방법에 대 한 자세한 내용은 [Lync Server 2013에서 네트워크 서브넷 만들기 또는 수정을](lync-server-2013-create-or-modify-network-subnets.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3a843-106">For details on creating or modifying network subnets, see [Create or modify network subnets in Lync Server 2013](lync-server-2013-create-or-modify-network-subnets.md).</span></span>

<span data-ttu-id="3a843-107">Microsoft Lync Server 2013에서 호출 허용 제어 (CAC)가 구현 되는 대부분의 배포에서는 일반적으로 많은 수의 서브넷이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a843-107">In most deployments of Microsoft Lync Server 2013 where call admission control (CAC) is implemented, there will typically be a large number of subnets.</span></span> <span data-ttu-id="3a843-108">이 때문에 Lync Server 관리 셸에서 서브넷을 구성 하는 것이 가장 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="3a843-108">Because of this, it is often best to configure subnets from the Lync Server Management Shell.</span></span> <span data-ttu-id="3a843-109">여기서는 Windows PowerShell cmdlet **가져오기-CSV**와 함께 **새 csnetworksubnet** 을 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a843-109">From there you can call **New-CsNetworkSubnet** in conjunction with the Windows PowerShell cmdlet **Import-CSV**.</span></span> <span data-ttu-id="3a843-110">이러한 cmdlet을 함께 사용 하 여 쉼표로 구분 된 값 (.csv) 파일의 서브넷 설정을 읽고 동시에 여러 개의 서브넷을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a843-110">By using these cmdlets together, you can read in subnet settings from a comma-separated values (.csv) file and create multiple subnets at the same time.</span></span> <span data-ttu-id="3a843-111">.Csv 파일에서 서브넷을 만드는 방법에 대 한 예는 [새 CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3a843-111">For examples of how to create subnets from a .csv file, see [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span></span>

<div>

## <a name="to-delete-a-network-subnet"></a><span data-ttu-id="3a843-112">네트워크 서브넷을 삭제 하려면</span><span class="sxs-lookup"><span data-stu-id="3a843-112">To delete a network subnet</span></span>

1.  <span data-ttu-id="3a843-113">RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsAdministrator 역할에 할당 된 경우 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a843-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="3a843-114">브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="3a843-114">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="3a843-115">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3a843-115">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="3a843-116">왼쪽 탐색 모음에서 **네트워크 구성을** 클릭 한 다음 **서브넷**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a843-116">In the left navigation bar, click **Network Configuration** and then click **Subnet**.</span></span>

4.  <span data-ttu-id="3a843-117">**서브넷** 페이지에서 삭제 하려는 서브넷을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a843-117">On the **Subnet** page, click the subnet that you want to delete.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3a843-118">한 번에 둘 이상의 서브넷을 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a843-118">You can delete more than one subnet at a time.</span></span> <span data-ttu-id="3a843-119">이 작업을 수행 하려면 ctrl 키를 누른 채 여러 서브넷을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a843-119">To do this, press CTRL and select multiple subnets while holding down the CTRL key.</span></span> <span data-ttu-id="3a843-120">또는 모든 서브넷을 선택 하려면 <STRONG>편집</STRONG> 메뉴에서 <STRONG>모두 선택을</STRONG> 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a843-120">Or, to select all subnets, click <STRONG>Select all</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

    
    </div>

5.  <span data-ttu-id="3a843-121">**편집** 메뉴에서 **삭제**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a843-121">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="3a843-122">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3a843-122">Click **OK**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3a843-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3a843-123">See Also</span></span>


[<span data-ttu-id="3a843-124">Lync Server 2013에서 네트워크 서브넷 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="3a843-124">Create or modify network subnets in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-network-subnets.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

