---
title: 'Lync Server 2013: 서비스에 대 한 세션 방지'
description: 'Lync Server 2013: 서비스에 대 한 세션을 방지 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Prevent sessions for services
ms:assetid: 977dcc5c-2aac-48ef-86a1-a8d47b4d9e74
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182553(v=OCS.15)
ms:contentKeyID: 48184866
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 846a9da5330c3e64f61c27dfadd883f0c43a0ffa
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579814"
---
# <a name="prevent-sessions-for-services-in-lync-server-2013"></a><span data-ttu-id="bfdd2-103">Lync Server 2013의 서비스에 대 한 세션 방지</span><span class="sxs-lookup"><span data-stu-id="bfdd2-103">Prevent sessions for services in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bfdd2-104">_**마지막으로 수정 된 항목:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="bfdd2-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="bfdd2-105">Lync Server 제어판을 사용 하 여 특정 컴퓨터에서 실행 되는 모든 Lync Server 2013 서비스에 대해 새 세션을 차단 하거나 특정 Lync Server 2013 서비스에 대해 새 세션을 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfdd2-105">You can use Lync Server Control Panel to prevent new sessions for all the Lync Server 2013 services running on a specific computer or to prevent new sessions for a specific Lync Server 2013 service.</span></span>

<div>

## <a name="to-prevent-new-sessions-for-all-lync-server-services-on-a-computer"></a><span data-ttu-id="bfdd2-106">컴퓨터의 모든 Lync Server 서비스에 대한 새 세션을 금지하려면</span><span class="sxs-lookup"><span data-stu-id="bfdd2-106">To prevent new sessions for all Lync Server services on a computer</span></span>

1.  <span data-ttu-id="bfdd2-107">RTCUniversalServerAdmins 그룹의 구성원 이거나이에 해당 하는 사용자 권한이 있는 사용자 계정 또는 CsServerAdministrator 또는 CsAdministrator 역할에 할당 된 경우 Lync Server 2013을 배포한 네트워크에 있는 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="bfdd2-107">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="bfdd2-108">브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="bfdd2-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="bfdd2-109">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="bfdd2-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="bfdd2-110">왼쪽 탐색 모음에서 **토폴로지**를 클릭하고 **상태**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="bfdd2-110">In the left navigation bar, click **Topology** and then click **Status**.</span></span>

4.  <span data-ttu-id="bfdd2-111">**상태** 페이지에서 새 세션을 금지할 서비스를 실행 중인 컴퓨터를 찾기 위해 필요한 경우 목록을 정렬하거나 검색한 다음 해당 컴퓨터를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="bfdd2-111">On the **Status** page, sort or search through the list as needed to find the computer that is running the services for which you want to prevent new sessions, and then click it.</span></span>

5.  <span data-ttu-id="bfdd2-112">**동작**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="bfdd2-112">Click **Action**.</span></span>

6.  <span data-ttu-id="bfdd2-113">**모든 서비스에 대한 새 세션 금지**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="bfdd2-113">Click **Prevent new sessions for all services**.</span></span>

</div>

<div>

## <a name="to-prevent-new-sessions-for-a-specific-service"></a><span data-ttu-id="bfdd2-114">특정 서비스에 대한 새 세션을 금지하려면</span><span class="sxs-lookup"><span data-stu-id="bfdd2-114">To prevent new sessions for a specific service</span></span>

1.  <span data-ttu-id="bfdd2-115">RTCUniversalServerAdmins 그룹의 구성원 이거나이에 해당 하는 사용자 권한이 있는 사용자 계정 또는 CsServerAdministrator 또는 CsAdministrator 역할에 할당 된 경우 Lync Server 2013을 배포한 네트워크에 있는 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="bfdd2-115">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="bfdd2-116">브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="bfdd2-116">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="bfdd2-117">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="bfdd2-117">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="bfdd2-118">왼쪽 탐색 모음에서 **토폴로지**를 클릭하고 **상태**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="bfdd2-118">In the left navigation bar, click **Topology** and then click **Status**.</span></span>

4.  <span data-ttu-id="bfdd2-119">**상태** 페이지에서 시작하거나 중지할 서비스를 실행 중인 컴퓨터를 찾기 위해 필요한 경우 목록을 정렬하거나 검색한 다음 해당 서비스를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="bfdd2-119">On the **Status** page, sort or search through the list as needed to find the computer that is running the service you want to start or stop, and then click it.</span></span>

5.  <span data-ttu-id="bfdd2-120">**속성**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="bfdd2-120">Click **Properties**.</span></span>

6.  <span data-ttu-id="bfdd2-121">필요한 경우 서비스 목록을 정렬하고 새 세션을 금지할 서비스를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="bfdd2-121">Sort the list of services, if necessary, and click the service for which you want to prevent new sessions.</span></span>

7.  <span data-ttu-id="bfdd2-122">**동작**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="bfdd2-122">Click **Action**.</span></span>

8.  <span data-ttu-id="bfdd2-123">**서비스에 대한 새 세션 금지**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="bfdd2-123">Click **Prevent new sessions for service**.</span></span>

9.  <span data-ttu-id="bfdd2-124">**닫기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="bfdd2-124">Click **Close**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="bfdd2-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bfdd2-125">See Also</span></span>


[<span data-ttu-id="bfdd2-126">Lync Server 2013 토폴로지 관리</span><span class="sxs-lookup"><span data-stu-id="bfdd2-126">Managing the Lync Server 2013 topology</span></span>](lync-server-2013-managing-the-lync-server-topology.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

