---
title: 'Lync Server 2013: 위치 정책 삭제'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting a location policy
ms:assetid: 8ca9ba10-f45f-435a-b39c-519d251e9085
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688125(v=OCS.15)
ms:contentKeyID: 49733724
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dc554d24bc93b81969832c9d8d2b034d071760bf
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42202494"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deleting-a-location-policy-in-lync-server-2013"></a><span data-ttu-id="10029-102">Lync Server 2013에서 위치 정책 삭제</span><span class="sxs-lookup"><span data-stu-id="10029-102">Deleting a location policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="10029-103">_**마지막으로 수정 된 항목:** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="10029-103">_**Topic Last Modified:** 2012-10-10_</span></span>

<span data-ttu-id="10029-104">Lync Server 2013에서는 위치 정책을 사용 하 여 E9-1-1 (고급 9-1-1) 기능 및 사용자 또는 연락처의 위치 설정과 관련 된 설정을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10029-104">In Lync Server 2013, you can use the location policy to apply settings that relate to Enhanced 9-1-1 (E9-1-1) functionality and to location settings for users or contacts.</span></span> <span data-ttu-id="10029-105">위치 정책은 사용자가 E9-1-1을 사용하도록 설정되어 있는지 여부를 확인하고, 설정된 경우 긴급 통화에 대한 동작을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="10029-105">The location policy determines whether a user is enabled for E9-1-1, and if so what the behavior is of an emergency call.</span></span> <span data-ttu-id="10029-106">예를 들어 위치 정책을 사용하여 긴급 통화 번호(예: 한국의 경우 119), 회사 보안 부서에 자동으로 알림을 제공할지 여부 및 통화를 라우팅할 방법을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10029-106">For example, you can use the location policy to define what number constitutes an emergency call (for example, 911 in the United States), whether corporate security should be automatically notified, and how the call should be routed.</span></span>

<span data-ttu-id="10029-107">Lync Server 2013 제어판의 **네트워크 구성** 그룹에서 위치 정책을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10029-107">You can configure location policies from the **Network Configuration** group in Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="10029-108">Lync Server 제어판에서 위치 정책을 보거나 만들거나 수정 하거나 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10029-108">From Lync Server Control Panel you can view, create, modify, or delete location policies.</span></span> <span data-ttu-id="10029-109">위치 정책을 삭제하려면 다음 절차를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="10029-109">Use the following procedures delete a location policy.</span></span> <span data-ttu-id="10029-110">위치 정책을 만들거나 수정 하는 방법에 대 한 자세한 내용은 [Lync Server 2013에서 위치 정책 만들기 또는 수정을](lync-server-2013-creating-or-modifying-a-location-policy.md)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="10029-110">For details on creating or modifying location policies, see [Creating or modifying a location policy in Lync Server 2013](lync-server-2013-creating-or-modifying-a-location-policy.md).</span></span>

<div>

## <a name="to-delete-a-location-policy"></a><span data-ttu-id="10029-111">위치 정책을 삭제하려면</span><span class="sxs-lookup"><span data-stu-id="10029-111">To delete a location policy</span></span>

1.  <span data-ttu-id="10029-112">RTCUniversalServerAdmins 그룹의 구성원 인 사용자 계정 (또는 이와 동등한 사용자 권한 포함) 또는 CsAdministrator 역할이 할당 되 면 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="10029-112">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="10029-113">브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="10029-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="10029-114">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="10029-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="10029-115">왼쪽 탐색 모음에서 **네트워크 구성**을 클릭한 다음 **위치 정책**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="10029-115">In the left navigation bar, click **Network Configuration** and then click **Location Policy**.</span></span>

4.  <span data-ttu-id="10029-116">**위치 정책** 페이지에서 삭제할 위치 정책을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="10029-116">On the **Location Policy** page, select the location policy that you want to delete.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="10029-p104">한 번에 둘 이상의 위치 정책을 삭제할 수 있습니다. 이렇게 하려면 Ctrl 키를 누른 채 여러 정책을 선택합니다. 또는 모든 정책을 선택하려면 <STRONG>편집</STRONG> 메뉴에서 <STRONG>모두 선택</STRONG>을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="10029-p104">You can delete more than one location policy at a time. To do this, press CTRL and select multiple policies while holding down the CTRL key. Or, to select all policies, click <STRONG>Select all</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

    
    </div>

5.  <span data-ttu-id="10029-120">**편집** 메뉴에서 **삭제**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="10029-120">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="10029-121">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="10029-121">Click **OK**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="10029-p105">전역 위치 정책은 삭제할 수 없습니다. 글로벌 정책을 삭제하려고 하면 경고 메시지가 나타나고 해당 정책이 기본값으로 다시 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="10029-p105">You cannot delete the Global location policy. If you attempt to delete the Global policy you will receive a warning message and that policy will be reset to its default values.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="10029-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="10029-124">See Also</span></span>


[<span data-ttu-id="10029-125">Lync Server 2013에서 위치 정책 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="10029-125">Creating or modifying a location policy in Lync Server 2013</span></span>](lync-server-2013-creating-or-modifying-a-location-policy.md)  
[<span data-ttu-id="10029-126">Lync Server 2013에서 위치 정책 정보 보기</span><span class="sxs-lookup"><span data-stu-id="10029-126">Viewing location policy information in Lync Server 2013</span></span>](lync-server-2013-viewing-location-policy-information.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

