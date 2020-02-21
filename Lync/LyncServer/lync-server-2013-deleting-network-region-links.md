---
title: 'Lync Server 2013: 네트워크 지역 링크 삭제'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting network region links
ms:assetid: 839273cd-d23f-4b38-84e6-d2dc972f49cd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688114(v=OCS.15)
ms:contentKeyID: 49733712
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a19835235921c10c0b3fe2be7d9c269a36dff7b6
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42179685"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deleting-network-region-links-in-lync-server-2013"></a><span data-ttu-id="f9e2a-102">Lync Server 2013에서 네트워크 지역 링크 삭제</span><span class="sxs-lookup"><span data-stu-id="f9e2a-102">Deleting network region links in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f9e2a-103">_**마지막으로 수정 된 항목:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="f9e2a-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="f9e2a-104">CAC(통화 허용 제어)의 일환으로 두 네트워크 지역 간의 링크를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9e2a-104">You can configure links between two network regions as part of call admission control (CAC).</span></span> <span data-ttu-id="f9e2a-105">네트워크 내의 지역은 실제 WAN(Wide Area Network) 연결을 통해 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="f9e2a-105">Regions within a network are linked through physical wide area network (WAN) connectivity.</span></span> <span data-ttu-id="f9e2a-106">Lync Server 제어판을 사용 하 여 두 네트워크 지역 간의 기존 연결을 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9e2a-106">You can use the Lync Server Control Panel to delete an existing link between two network regions.</span></span> <span data-ttu-id="f9e2a-107">네트워크 지역 링크를 만들거나 수정 하는 방법에 대 한 자세한 내용은 [Lync Server 2013에서 네트워크 지역 링크 구성을](lync-server-2013-configuring-network-region-links.md) 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="f9e2a-107">For details about creating or modifying network region link, see [Configuring network region links in Lync Server 2013](lync-server-2013-configuring-network-region-links.md)</span></span>

<div>

## <a name="to-delete-a-network-region-link"></a><span data-ttu-id="f9e2a-108">네트워크 지역 링크를 삭제하려면</span><span class="sxs-lookup"><span data-stu-id="f9e2a-108">To delete a network region link</span></span>

1.  <span data-ttu-id="f9e2a-109">RTCUniversalServerAdmins 그룹의 구성원 인 사용자 계정 (또는 이와 동등한 사용자 권한 포함) 또는 CsAdministrator 역할이 할당 되 면 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9e2a-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="f9e2a-110">브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="f9e2a-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="f9e2a-111">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="f9e2a-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="f9e2a-112">왼쪽 탐색 모음에서 **네트워크 구성**을 클릭한 다음 **지역 링크**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f9e2a-112">In the left navigation bar, click **Network Configuration** and then click **Region Link**.</span></span>

4.  <span data-ttu-id="f9e2a-113">**지역 링크** 페이지에서 삭제할 지역 링크를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f9e2a-113">On the **Region Link** page, click the region link that you want to delete.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f9e2a-p103">한 번에 둘 이상의 지역 링크를 삭제할 수 있습니다. 이렇게 하려면 Ctrl 키를 누른 상태에서 여러 지역 링크를 선택합니다. 또는 모든 지역 링크를 선택하려면 <STRONG>편집</STRONG> 메뉴에서 <STRONG>모두 선택</STRONG>을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f9e2a-p103">You can delete more than one region link at a time. To do this, press CTRL and select multiple region links while holding down the CTRL key. Or, to select all region links, click <STRONG>Select all</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

    
    </div>

5.  <span data-ttu-id="f9e2a-117">**편집** 메뉴에서 **삭제**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f9e2a-117">From the **Edit** menu, select **Delete**.</span></span>

6.  <span data-ttu-id="f9e2a-118">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f9e2a-118">Click **OK**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f9e2a-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f9e2a-119">See Also</span></span>


[<span data-ttu-id="f9e2a-120">Lync Server 2013에서 네트워크 지역 링크 구성</span><span class="sxs-lookup"><span data-stu-id="f9e2a-120">Configuring network region links in Lync Server 2013</span></span>](lync-server-2013-configuring-network-region-links.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

