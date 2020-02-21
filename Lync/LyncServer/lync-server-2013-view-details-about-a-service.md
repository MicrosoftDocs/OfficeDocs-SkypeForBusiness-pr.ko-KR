---
title: 'Lync Server 2013: 서비스에 대 한 세부 정보 보기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View details about a service
ms:assetid: bc8e8202-cd68-47e4-95b2-bb36e51cc124
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182578(v=OCS.15)
ms:contentKeyID: 48185253
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0769c8cc327a3cc4889a79f32bb5b9af0b1e3087
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42211504"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="view-details-about-a-service-in-lync-server-2013"></a><span data-ttu-id="15b68-102">Lync Server 2013의 서비스에 대 한 세부 정보 보기</span><span class="sxs-lookup"><span data-stu-id="15b68-102">View details about a service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="15b68-103">_**마지막으로 수정 된 항목:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="15b68-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="15b68-104">Lync Server 제어판을 사용 하 여 토폴로지의 특정 컴퓨터에서 실행 되는 각 서비스에 대 한 세부 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15b68-104">You can use Lync Server Control Panel to view details about each service that is running on a specific computer in your topology.</span></span> <span data-ttu-id="15b68-105">구체적으로 연관된 데이터베이스, 포트 및 종속 서비스 등과 같은 세부 정보 및 각 서비스의 상태를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15b68-105">You can view the status of each service and details such as the associated databases, ports, and dependent services.</span></span>

<div>

## <a name="to-view-details-for-a-service"></a><span data-ttu-id="15b68-106">서비스에 대한 세부 정보를 보려면</span><span class="sxs-lookup"><span data-stu-id="15b68-106">To view details for a service</span></span>

1.  <span data-ttu-id="15b68-107">Lync Server 2013에 대해 미리 정의 된 관리 역할에 할당 되어 있는 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="15b68-107">From a user account that is assigned to any of the predefined administrative roles for Lync Server 2013, log on to any computer in your internal deployment.</span></span> <span data-ttu-id="15b68-108">Lync Server 2013에서 사용할 수 있는 미리 정의 된 관리 역할에 대 한 자세한 내용은 [Lync server 2013에서 역할 기반 액세스 제어 계획](lync-server-2013-planning-for-role-based-access-control.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="15b68-108">For details about the predefined administrative roles available in Lync Server 2013, see [Planning for role-based access control in Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md).</span></span>

2.  <span data-ttu-id="15b68-109">브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="15b68-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="15b68-110">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="15b68-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="15b68-111">왼쪽 탐색 모음에서 **토폴로지**를 클릭하고 **상태**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="15b68-111">In the left navigation bar, click **Topology** and then click **Status**.</span></span>

4.  <span data-ttu-id="15b68-112">**상태** 페이지에서 목록을 정렬하거나 목록 전체를 검색한 다음 보려는 컴퓨터를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="15b68-112">In the **Status** page, sort or search through the list and then click the computer that you want to view.</span></span>

5.  <span data-ttu-id="15b68-113">**속성**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="15b68-113">Click **Properties**.</span></span>

6.  <span data-ttu-id="15b68-114">**컴퓨터 세부 정보 보기** 창에서 필요한 경우 서비스 목록을 정렬하고 보려는 서비스를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="15b68-114">In the **View Computer Detail** window, sort the list of services, if necessary, and click the service you want to view.</span></span>

7.  <span data-ttu-id="15b68-115">필요에 따라 다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="15b68-115">Do any of the following as needed:</span></span>
    
      - <span data-ttu-id="15b68-116">특정 서비스의 최신 상태를 보려면 **서비스 상태 가져오기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="15b68-116">To see the latest status of that specific service, click **Get service status**.</span></span>
    
      - <span data-ttu-id="15b68-117">특정 서비스의 세부 정보를 보려면 **속성**, **닫기**를 차례로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="15b68-117">To see the details for that specific service, click **Properties** and then click **Close**.</span></span>
    
      - <span data-ttu-id="15b68-118">토폴로지의 모든 컴퓨터 목록으로 돌아가려면 **닫기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="15b68-118">To return to the list of all computers in your topology, click **Close**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="15b68-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="15b68-119">See Also</span></span>


[<span data-ttu-id="15b68-120">Lync Server 2013 토폴로지 관리</span><span class="sxs-lookup"><span data-stu-id="15b68-120">Managing the Lync Server 2013 topology</span></span>](lync-server-2013-managing-the-lync-server-topology.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

