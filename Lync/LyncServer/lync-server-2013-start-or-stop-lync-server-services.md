---
title: 'Lync Server 2013: Lync Server 서비스 시작 또는 중지'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Start or stop Lync Server 2013 services
ms:assetid: 1c70b4ec-9de5-4f7a-a3c9-c0eb76710505
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520958(v=OCS.15)
ms:contentKeyID: 48183554
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8ab531875145315b6a505bd0b324e9fdb4d77d5d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48532985"
---
# <a name="start-or-stop-lync-server-2013-services"></a><span data-ttu-id="a6839-102">Lync Server 2013 서비스 시작 또는 중지</span><span class="sxs-lookup"><span data-stu-id="a6839-102">Start or stop Lync Server 2013 services</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a6839-103">_**마지막으로 수정 된 항목:** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="a6839-103">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="a6839-104">Lync Server 제어판을 사용 하 여 특정 컴퓨터에서 실행 되는 모든 Lync Server 2013 서비스를 시작 또는 중지 하거나 특정 서비스를 시작 하거나 중지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6839-104">You can use Lync Server Control Panel to start or stop all the Lync Server 2013 services running on a specific computer or to start or stop a specific service.</span></span>

<div>

## <a name="to-start-or-stop-all-lync-server-services-on-a-computer"></a><span data-ttu-id="a6839-105">컴퓨터의 모든 Lync Server 서비스를 시작 또는 중지하려면</span><span class="sxs-lookup"><span data-stu-id="a6839-105">To start or stop all Lync Server services on a computer</span></span>

1.  <span data-ttu-id="a6839-106">RTCUniversalServerAdmins 그룹의 구성원 이거나이에 해당 하는 사용자 권한이 있는 사용자 계정 또는 CsServerAdministrator 또는 CsAdministrator 역할에 할당 된 경우 Lync Server 2013을 배포한 네트워크에 있는 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6839-106">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span> <span data-ttu-id="a6839-107">다음과 같은 명령을 실행 하 여 CsServerAdministrator 또는 CsAdministrator RBAC 역할에 할당 되었는지 여부를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6839-107">You can determine whether you have been assigned the CsServerAdministrator or the CsAdministrator RBAC role by running a command similar to the following:</span></span>
    
        Get-CsAdminRoleAssignment -Identity "kenmyer"

2.  <span data-ttu-id="a6839-108">브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="a6839-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="a6839-109">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="a6839-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="a6839-110">왼쪽 탐색 모음에서 **토폴로지**를 클릭하고 **상태**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a6839-110">In the left navigation bar, click **Topology** and then click **Status**.</span></span>

4.  <span data-ttu-id="a6839-111">**상태** 페이지에서 시작하거나 중지할 서비스를 실행 중인 컴퓨터를 찾기 위해 필요한 경우 목록을 정렬하거나 검색한 다음 해당 서비스를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a6839-111">On the **Status** page, sort or search through the list as needed to find the computer that is running the services you want to start or stop, and then click it.</span></span>

5.  <span data-ttu-id="a6839-112">**동작**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a6839-112">Click **Action**.</span></span>

6.  <span data-ttu-id="a6839-113">**모든 서비스 시작** 또는 **모든 서비스 중지**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a6839-113">Click **Start All services** or **Stop All services**.</span></span>

</div>

<div>

## <a name="to-start-or-stop-a-specific-service"></a><span data-ttu-id="a6839-114">특정 서비스를 시작 또는 중지하려면</span><span class="sxs-lookup"><span data-stu-id="a6839-114">To start or stop a specific service</span></span>

1.  <span data-ttu-id="a6839-115">CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="a6839-115">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="a6839-116">브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="a6839-116">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="a6839-117">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="a6839-117">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="a6839-118">왼쪽 탐색 모음에서 **토폴로지**를 클릭하고 **상태**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a6839-118">In the left navigation bar, click **Topology** and then click **Status**.</span></span>

4.  <span data-ttu-id="a6839-119">**상태** 페이지에서 시작하거나 중지할 서비스를 실행 중인 컴퓨터를 찾기 위해 필요한 경우 목록을 정렬하거나 검색한 다음 해당 서비스를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a6839-119">On the **Status** page, sort or search through the list as needed to find the computer that is running the service you want to start or stop, and then click it.</span></span>

5.  <span data-ttu-id="a6839-120">**속성**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a6839-120">Click **Properties**.</span></span>

6.  <span data-ttu-id="a6839-121">필요한 경우 서비스 목록을 정렬하고 시작 또는 중지할 서비스를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a6839-121">Sort the list of services, if necessary, and click the service you want to start or stop.</span></span>

7.  <span data-ttu-id="a6839-122">**동작**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a6839-122">Click **Action**.</span></span>

8.  <span data-ttu-id="a6839-123">**서비스 시작** 또는 **서비스 중지**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a6839-123">Click **Start service** or **Stop service**.</span></span>

9.  <span data-ttu-id="a6839-124">**닫기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a6839-124">Click **Close**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a6839-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a6839-125">See Also</span></span>


[<span data-ttu-id="a6839-126">Lync Server 2013의 서비스에 대 한 세션 방지</span><span class="sxs-lookup"><span data-stu-id="a6839-126">Prevent sessions for services in Lync Server 2013</span></span>](lync-server-2013-prevent-sessions-for-services.md)  


[<span data-ttu-id="a6839-127">Lync Server 2013 토폴로지 관리</span><span class="sxs-lookup"><span data-stu-id="a6839-127">Managing the Lync Server 2013 topology</span></span>](lync-server-2013-managing-the-lync-server-topology.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

