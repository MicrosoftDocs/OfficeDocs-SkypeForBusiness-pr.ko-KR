---
title: 'Lync Server 2013: 단순 URL 세부 정보 보기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View simple URL details
ms:assetid: 6ab00f2c-e1d5-4698-a58f-04b72260f9ac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521010(v=OCS.15)
ms:contentKeyID: 48184399
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 853ab8a5727991eace45b452f6991ed2efaacde7
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48518425"
---
# <a name="view-simple-url-details-in-lync-server-2013"></a><span data-ttu-id="20bba-102">Lync Server 2013에서 단순 URL 세부 정보 보기</span><span class="sxs-lookup"><span data-stu-id="20bba-102">View simple URL details in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="20bba-103">_**마지막으로 수정 된 항목:** 2012-10-11_</span><span class="sxs-lookup"><span data-stu-id="20bba-103">_**Topic Last Modified:** 2012-10-11_</span></span>

<span data-ttu-id="20bba-104">Lync Server 2013 제어판을 사용 하 여 Lync Server 2013 환경에 대 한 단순한 URL 세부 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20bba-104">You can use Lync Server 2013 Control Panel to view simple URL details for your Lync Server 2013 environment.</span></span> <span data-ttu-id="20bba-105">단순 Url을 통해 사용자가 모임에 보다 쉽게 참가할 수 있으며 관리자가 관리 도구를 보다 쉽게 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20bba-105">Simple URLs make it easier for users to join meetings, and they make it easier for administrators to get to administrative tools.</span></span> <span data-ttu-id="20bba-106">자세한 내용은 [Lync Server 2013의 단순 Url 계획](lync-server-2013-planning-for-simple-urls.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="20bba-106">For details, see [Planning for simple URLs in Lync Server 2013](lync-server-2013-planning-for-simple-urls.md).</span></span>

<div>

## <a name="to-view-simple-url-details"></a><span data-ttu-id="20bba-107">단순 URL 세부 정보를 보려면</span><span class="sxs-lookup"><span data-stu-id="20bba-107">To view Simple URL details</span></span>

1.  <span data-ttu-id="20bba-108">CsServerAdministrator, CsAdministrator, CsHelpDesk 또는 Csserveradministrator 관리자 역할에 할당 된 사용자 계정에서 내부 배포의 임의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="20bba-108">From a user account that is assigned to the CsServerAdministrator, CsAdministrator, CsHelpDesk, or CsViewOnlyAdministrator role, log on to any computer in your internal deployment.</span></span> <span data-ttu-id="20bba-109">Lync Server 2013에서 사용할 수 있는 미리 정의 된 관리 역할에 대 한 자세한 내용은 [Lync server 2013에서 역할 기반 액세스 제어 계획](lync-server-2013-planning-for-role-based-access-control.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="20bba-109">For details about the predefined administrative roles available in Lync Server 2013, see [Planning for role-based access control in Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md).</span></span>

2.  <span data-ttu-id="20bba-110">브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="20bba-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="20bba-111">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="20bba-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="20bba-112">왼쪽 탐색 모음에서 **토폴로지** 를 클릭 하 고 **단순 URL**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="20bba-112">In the left navigation bar, click **Topology** and then click **Simple URL**.</span></span>

4.  <span data-ttu-id="20bba-113">**단순 URL** 페이지에서 필요한 경우 열 머리글을 클릭 하 여 목록을 정렬 합니다.</span><span class="sxs-lookup"><span data-stu-id="20bba-113">On the **Simple URL** page, click a column heading to sort the list, if needed.</span></span>

5.  <span data-ttu-id="20bba-114">단순 URL 세부 정보를 보려는 이름을 선택 하 고 **속성**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="20bba-114">Select the name for which you want to see simple URL details, and then click **Properties**.</span></span>

6.  <span data-ttu-id="20bba-115">세부 정보를 확인 한 후에는 **닫기를**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="20bba-115">When you are finished viewing details, click **Close**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="20bba-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="20bba-116">See Also</span></span>


[<span data-ttu-id="20bba-117">Lync Server 2013 토폴로지 관리</span><span class="sxs-lookup"><span data-stu-id="20bba-117">Managing the Lync Server 2013 topology</span></span>](lync-server-2013-managing-the-lync-server-topology.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

