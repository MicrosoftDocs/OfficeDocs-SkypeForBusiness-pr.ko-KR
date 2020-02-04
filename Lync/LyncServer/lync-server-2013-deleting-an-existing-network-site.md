---
title: 'Lync Server 2013: 기존 네트워크 사이트 삭제'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting an existing network site
ms:assetid: 2762149b-3572-4513-b838-beda7fa9e81e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688001(v=OCS.15)
ms:contentKeyID: 49733589
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3c8e3828bccb84fcddb4404dd7228173c63ab8a5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763066"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deleting-an-existing-network-site-in-lync-server-2013"></a><span data-ttu-id="6088d-102">Lync Server 2013에서 기존 네트워크 사이트 삭제</span><span class="sxs-lookup"><span data-stu-id="6088d-102">Deleting an existing network site in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6088d-103">_**마지막으로 수정한 주제:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="6088d-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="6088d-104">네트워크 사이트는 CAC (통화 허용 제어) 또는 향상 된 9-1-1 배포의 각 영역 내에서 구성 된 사무실 또는 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="6088d-104">Network sites are the offices or locations configured within each region of a call admission control (CAC) or Enhanced 9-1-1 deployment.</span></span> <span data-ttu-id="6088d-105">Lync Server 2013 제어판을 사용 하 여 사이트를 구성 하 고 지역을 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6088d-105">You can use the Lync Server 2013 Control Panel to configure sites and associate them with regions.</span></span> <span data-ttu-id="6088d-106">예를 들어 북미, 레드먼드, Vancouver와 같은 네트워크 사이트에 북아메리카 네트워크 지역이 연결 되어 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6088d-106">For example, a network region for North America might be associated with networks sites such as Chicago, Redmond, and Vancouver.</span></span> <span data-ttu-id="6088d-107">사이트에 대 한 모든 사이트에 대해 CAC 네트워크 사이트를 만들어야 하는 경우에도 해당 사이트가 대역폭 제한 없이 구성 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6088d-107">A CAC network site must be created for every site within an organization, even if that site has no bandwidth limitations.</span></span> <span data-ttu-id="6088d-108">Lync Server 제어판에서 네트워크 사이트를 만들고, 수정 하 고, 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6088d-108">From the Lync Server Control Panel you can create, modify, and delete network sites.</span></span> <span data-ttu-id="6088d-109">다음 절차를 사용 하 여 기존 네트워크 사이트를 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="6088d-109">Use the following procedure to delete an existing network site.</span></span> <span data-ttu-id="6088d-110">네트워크 사이트를 만들거나 수정 하는 방법에 대 한 자세한 내용은 [Lync Server 2013에서 네트워크 사이트 만들기 또는 수정을](lync-server-2013-creating-or-modifying-network-sites.md) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6088d-110">For details about creating or modifying network sites, see [Creating or modifying network sites in Lync Server 2013](lync-server-2013-creating-or-modifying-network-sites.md)</span></span>

<div>

## <a name="to-delete-a-network-site"></a><span data-ttu-id="6088d-111">네트워크 사이트를 삭제 하려면</span><span class="sxs-lookup"><span data-stu-id="6088d-111">To delete a network site</span></span>

1.  <span data-ttu-id="6088d-112">RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsAdministrator 역할에 할당 된 경우 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="6088d-112">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="6088d-113">브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="6088d-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="6088d-114">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6088d-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="6088d-115">왼쪽 탐색 모음에서 **네트워크 구성을** 클릭 한 다음 **사이트**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="6088d-115">In the left navigation bar, click **Network Configuration** and then click **Site**.</span></span>

4.  <span data-ttu-id="6088d-116">**사이트** 페이지에서 삭제 하려는 사이트를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="6088d-116">On the **Site** page, click the site that you want to delete.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6088d-117">한 번에 여러 사이트를 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6088d-117">You can delete more than one site at a time.</span></span> <span data-ttu-id="6088d-118">이 작업을 수행 하려면 ctrl 키를 누른 채 여러 사이트를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6088d-118">To do this, press CTRL and select multiple sites while holding down the CTRL key.</span></span> <span data-ttu-id="6088d-119">또는 모든 사이트를 선택 하려면 <STRONG>편집</STRONG> 메뉴에서 <STRONG>모두 선택을</STRONG> 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="6088d-119">Or, to select all sites, click <STRONG>Select all</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

    
    </div>

5.  <span data-ttu-id="6088d-120">**편집** 메뉴에서 **삭제**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="6088d-120">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="6088d-121">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6088d-121">Click **OK**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="6088d-122">네트워크 서브넷과 연결 된 네트워크 사이트는 제거할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6088d-122">You cannot remove a network site if it is associated with a network subnet.</span></span> <span data-ttu-id="6088d-123">서브넷과 연결 된 사이트를 제거 하려고 하면 오류 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6088d-123">If you attempt to remove a site associated with a subnet you will receive an error message.</span></span> <span data-ttu-id="6088d-124">사이트가 서브넷과 연결 되어 있는지 확인 하려면 사이트를 클릭 한 다음 <STRONG>편집</STRONG> 메뉴에서 <STRONG>자세한 정보 표시</STRONG> 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="6088d-124">To see if a site is associated with any subnets, click the site and then click <STRONG>Show details</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

