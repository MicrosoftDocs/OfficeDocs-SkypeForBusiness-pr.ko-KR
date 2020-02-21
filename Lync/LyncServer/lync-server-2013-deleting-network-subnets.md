---
title: 'Lync Server 2013: 네트워크 서브넷 삭제'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting network subnets
ms:assetid: c1850f38-40a3-48c9-b6f1-f181c5e63b6b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721873(v=OCS.15)
ms:contentKeyID: 49733806
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 05e47875007bd9fb7893ad952bea6772d2d9df9b
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42179695"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deleting-network-subnets-in-lync-server-2013"></a><span data-ttu-id="186d5-102">Lync Server 2013에서 네트워크 서브넷 삭제</span><span class="sxs-lookup"><span data-stu-id="186d5-102">Deleting network subnets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="186d5-103">_**마지막으로 수정 된 항목:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="186d5-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="186d5-104">다음 절차를 사용하여 서브넷을 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="186d5-104">You can use the following procedure to delete a subnet.</span></span> <span data-ttu-id="186d5-105">Lync Server 제어판에서는 네트워크 서브넷을 만들거나 수정 하거나 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="186d5-105">From the Lync Server Control Panel, you can create, modify, or delete a network subnet.</span></span> <span data-ttu-id="186d5-106">네트워크 서브넷을 만들거나 수정 하는 방법에 대 한 자세한 내용은 [Create or modify network 서브넷 In Lync Server 2013](lync-server-2013-create-or-modify-network-subnets.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="186d5-106">For details on creating or modifying network subnets, see [Create or modify network subnets in Lync Server 2013](lync-server-2013-create-or-modify-network-subnets.md).</span></span>

<span data-ttu-id="186d5-107">Microsoft Lync Server 2013의 대부분의 배포에서 CAC (통화 허용 제어)가 구현 되는 경우 일반적으로 서브넷 수가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="186d5-107">In most deployments of Microsoft Lync Server 2013 where call admission control (CAC) is implemented, there will typically be a large number of subnets.</span></span> <span data-ttu-id="186d5-108">따라서 Lync Server 관리 셸에서 서브넷을 구성 하는 것이 가장 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="186d5-108">Because of this, it is often best to configure subnets from the Lync Server Management Shell.</span></span> <span data-ttu-id="186d5-109">여기서는 Windows PowerShell cmdlet **가져오기-CSV**와 함께 **새 csnetworksubnet** 을 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="186d5-109">From there you can call **New-CsNetworkSubnet** in conjunction with the Windows PowerShell cmdlet **Import-CSV**.</span></span> <span data-ttu-id="186d5-110">두 cmdlet을 함께 사용하면 CSV(쉼표로 구분된 값) 파일에서 서브넷 설정을 읽어와서 여러 개의 서브넷을 동시에 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="186d5-110">By using these cmdlets together, you can read in subnet settings from a comma-separated values (.csv) file and create multiple subnets at the same time.</span></span> <span data-ttu-id="186d5-111">.csv 파일에서 서브넷을 만드는 방법의 예제는 [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="186d5-111">For examples of how to create subnets from a .csv file, see [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span></span>

<div>

## <a name="to-delete-a-network-subnet"></a><span data-ttu-id="186d5-112">네트워크 서브넷을 삭제하려면</span><span class="sxs-lookup"><span data-stu-id="186d5-112">To delete a network subnet</span></span>

1.  <span data-ttu-id="186d5-113">RTCUniversalServerAdmins 그룹의 구성원 인 사용자 계정 (또는 이와 동등한 사용자 권한 포함) 또는 CsAdministrator 역할이 할당 되 면 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="186d5-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="186d5-114">브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="186d5-114">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="186d5-115">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="186d5-115">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="186d5-116">왼쪽 탐색 모음에서 **네트워크 구성**을 클릭하고 **서브넷**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="186d5-116">In the left navigation bar, click **Network Configuration** and then click **Subnet**.</span></span>

4.  <span data-ttu-id="186d5-117">**서브넷** 페이지에서 삭제할 서브넷을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="186d5-117">On the **Subnet** page, click the subnet that you want to delete.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="186d5-p104">한 번에 둘 이상의 서브넷을 삭제할 수 있습니다. 이렇게 하려면 Ctrl 키를 누른 상태에서 여러 서브넷을 선택합니다. 또는 모든 서브넷을 선택하려면 <STRONG>편집</STRONG> 메뉴에서 <STRONG>모두 선택</STRONG>을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="186d5-p104">You can delete more than one subnet at a time. To do this, press CTRL and select multiple subnets while holding down the CTRL key. Or, to select all subnets, click <STRONG>Select all</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

    
    </div>

5.  <span data-ttu-id="186d5-121">**편집** 메뉴에서 **삭제**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="186d5-121">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="186d5-122">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="186d5-122">Click **OK**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="186d5-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="186d5-123">See Also</span></span>


[<span data-ttu-id="186d5-124">Lync Server 2013에서 네트워크 서브넷 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="186d5-124">Create or modify network subnets in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-network-subnets.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

