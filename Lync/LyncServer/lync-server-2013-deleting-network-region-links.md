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
ms.openlocfilehash: 158537f2473beba686daa51c5384a45f01432320
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763026"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deleting-network-region-links-in-lync-server-2013"></a><span data-ttu-id="64a0d-102">Lync Server 2013에서 네트워크 지역 링크 삭제</span><span class="sxs-lookup"><span data-stu-id="64a0d-102">Deleting network region links in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="64a0d-103">_**마지막으로 수정한 주제:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="64a0d-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="64a0d-104">두 네트워크 지역 간의 링크를 CAC (call 허용 제어)의 일부로 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64a0d-104">You can configure links between two network regions as part of call admission control (CAC).</span></span> <span data-ttu-id="64a0d-105">네트워크 내의 영역은 실제 WAN (광역 네트워크) 연결을 통해 연결 됩니다.</span><span class="sxs-lookup"><span data-stu-id="64a0d-105">Regions within a network are linked through physical wide area network (WAN) connectivity.</span></span> <span data-ttu-id="64a0d-106">Lync Server 제어판을 사용 하 여 두 네트워크 지역 간의 기존 링크를 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64a0d-106">You can use the Lync Server Control Panel to delete an existing link between two network regions.</span></span> <span data-ttu-id="64a0d-107">네트워크 지역 링크를 만들거나 수정 하는 방법에 대 한 자세한 내용은 [Lync Server 2013에서 네트워크 지역 링크 구성을](lync-server-2013-configuring-network-region-links.md) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="64a0d-107">For details about creating or modifying network region link, see [Configuring network region links in Lync Server 2013](lync-server-2013-configuring-network-region-links.md)</span></span>

<div>

## <a name="to-delete-a-network-region-link"></a><span data-ttu-id="64a0d-108">네트워크 지역 링크를 삭제 하려면</span><span class="sxs-lookup"><span data-stu-id="64a0d-108">To delete a network region link</span></span>

1.  <span data-ttu-id="64a0d-109">RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsAdministrator 역할에 할당 된 경우 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="64a0d-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="64a0d-110">브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="64a0d-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="64a0d-111">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="64a0d-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="64a0d-112">왼쪽 탐색 모음에서 **네트워크 구성을** 클릭 한 다음 **지역 링크**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="64a0d-112">In the left navigation bar, click **Network Configuration** and then click **Region Link**.</span></span>

4.  <span data-ttu-id="64a0d-113">**지역 링크** 페이지에서 삭제 하려는 지역 링크를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="64a0d-113">On the **Region Link** page, click the region link that you want to delete.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="64a0d-114">한 번에 둘 이상의 지역 링크를 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64a0d-114">You can delete more than one region link at a time.</span></span> <span data-ttu-id="64a0d-115">이 작업을 수행 하려면 ctrl 키를 누른 채로 여러 지역 링크를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="64a0d-115">To do this, press CTRL and select multiple region links while holding down the CTRL key.</span></span> <span data-ttu-id="64a0d-116">또는 모든 지역 링크를 선택 하려면 <STRONG>편집</STRONG> 메뉴에서 <STRONG>모두 선택을</STRONG> 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="64a0d-116">Or, to select all region links, click <STRONG>Select all</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

    
    </div>

5.  <span data-ttu-id="64a0d-117">**편집** 메뉴에서 **삭제**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="64a0d-117">From the **Edit** menu, select **Delete**.</span></span>

6.  <span data-ttu-id="64a0d-118">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="64a0d-118">Click **OK**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="64a0d-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="64a0d-119">See Also</span></span>


[<span data-ttu-id="64a0d-120">Lync Server 2013에서 네트워크 지역 링크 구성</span><span class="sxs-lookup"><span data-stu-id="64a0d-120">Configuring network region links in Lync Server 2013</span></span>](lync-server-2013-configuring-network-region-links.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

