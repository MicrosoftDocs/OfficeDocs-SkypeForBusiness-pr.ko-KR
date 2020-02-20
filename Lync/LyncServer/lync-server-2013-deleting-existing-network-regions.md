---
title: 'Lync Server 2013: 기존 네트워크 지역 삭제'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting existing network regions
ms:assetid: c7293a2f-2b49-4c4a-903f-f7edcea2bc5f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721882(v=OCS.15)
ms:contentKeyID: 49733815
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b94b3614dcf2b09ab96b2deede70554f1d3e6f50
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146171"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deleting-existing-network-regions-in-lync-server-2013"></a><span data-ttu-id="a0083-102">Lync Server 2013에서 기존 네트워크 지역 삭제</span><span class="sxs-lookup"><span data-stu-id="a0083-102">Deleting existing network regions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a0083-103">_**마지막으로 수정 된 항목:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="a0083-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="a0083-104">네트워크 지역은 여러 지역의 많은 네트워크 부분을 교차합니다.</span><span class="sxs-lookup"><span data-stu-id="a0083-104">A network region interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="a0083-105">모든 네트워크 지역은 중앙 사이트와 연결되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0083-105">Every network region must be associated with a central site.</span></span> <span data-ttu-id="a0083-106">중앙 사이트는 CAC(통화 허용 제어) 대역폭 정책 서비스가 실행되는 데이터 센터 사이트입니다.</span><span class="sxs-lookup"><span data-stu-id="a0083-106">The central site is the data center site on which the call admission control (CAC) bandwidth policy service is running.</span></span> <span data-ttu-id="a0083-107">Lync Server 제어판을 사용 하 여 네트워크 지역을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0083-107">You can use Lync Server Control Panel to configure network regions.</span></span> <span data-ttu-id="a0083-108">네트워크 지역에는 오디오 및 비디오 연결에 대해 인터넷을 통한 대체 경로가 허용되는지 여부를 결정하는 설정이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="a0083-108">Network regions include settings that determine whether alternate paths through the Internet are allowed for audio and video connections.</span></span> <span data-ttu-id="a0083-109">Lync Server 제어판에서는 네트워크 지역을 만들거나 수정 하거나 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0083-109">From the Lync Server Control Panel, you can create, modify, or delete a network region.</span></span> <span data-ttu-id="a0083-110">이 항목을 참조하여 기존 네트워크 지역을 삭제하십시오.</span><span class="sxs-lookup"><span data-stu-id="a0083-110">Use this topic to delete existing network regions.</span></span> <span data-ttu-id="a0083-111">기존 네트워크 지역을 만들거나 수정 하는 방법에 대 한 자세한 내용은 [Lync Server 2013에서 네트워크 지역 만들기 또는 수정을](lync-server-2013-creating-or-modifying-network-regions.md)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="a0083-111">For details about creating or modifying existing network regions, see [Creating or modifying network regions in Lync Server 2013](lync-server-2013-creating-or-modifying-network-regions.md).</span></span>

<div>

## <a name="to-delete-a-network-region"></a><span data-ttu-id="a0083-112">네트워크 지역을 삭제하려면</span><span class="sxs-lookup"><span data-stu-id="a0083-112">To delete a network region</span></span>

1.  <span data-ttu-id="a0083-113">RTCUniversalServerAdmins 그룹의 구성원 인 사용자 계정 (또는 이와 동등한 사용자 권한 포함) 또는 CsAdministrator 역할이 할당 되 면 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0083-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="a0083-114">브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="a0083-114">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="a0083-115">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="a0083-115">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="a0083-116">왼쪽 탐색 표시줄에서 **네트워크 구성**을 클릭한 다음 **지역**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a0083-116">In the left navigation bar, click **Network Configuration** and then click **Region**.</span></span>

4.  <span data-ttu-id="a0083-117">**지역** 페이지에서 삭제하려는 지역을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a0083-117">On the **Region** page, click the region you want to delete.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a0083-p103">한 번에 둘 이상의 지역을 삭제할 수 있습니다. 이렇게 하려면 Ctrl 키를 누른 상태에서 여러 지역을 선택합니다. 또는 지역을 모두 선택하려면 <STRONG>편집</STRONG> 메뉴에서 <STRONG>모두 선택</STRONG>을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a0083-p103">You can delete more than one region at a time. To do this, press CTRL and select multiple regions while holding down the CTRL key. Or, to select all regions, click <STRONG>Select all</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

    
    </div>

5.  <span data-ttu-id="a0083-121">**편집** 메뉴에서 **삭제**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a0083-121">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="a0083-122">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a0083-122">Click **OK**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="a0083-p104">네트워크 사이트와 연결된 네트워크 지역은 제거할 수 없습니다. 사이트와 연결된 지역을 제거하려고 시도하면 오류 메시지가 표시됩니다. 지역이 사이트와 연결되어 있는지 확인하려면 지역을 선택하고 <STRONG>편집</STRONG> 메뉴에서 <STRONG>자세한 정보 표시</STRONG>를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a0083-p104">A network region cannot be removed if it is associated with a network site. If you attempt to remove a region associated with a site you will receive an error message. To see if a region is associated with any sites, select the region and then click <STRONG>Show details</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a0083-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a0083-126">See Also</span></span>


[<span data-ttu-id="a0083-127">Lync Server 2013에서 네트워크 지역 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="a0083-127">Creating or modifying network regions in Lync Server 2013</span></span>](lync-server-2013-creating-or-modifying-network-regions.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

