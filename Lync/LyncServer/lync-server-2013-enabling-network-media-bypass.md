---
title: 'Lync Server 2013: 네트워크 미디어 바이패스 사용'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling network media bypass
ms:assetid: 95c4fa06-49d3-41ac-acdc-7dcda66e5508
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182552(v=OCS.15)
ms:contentKeyID: 48184846
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a269f22eabc294af45697ab1bd2c0eabe4b5aad6
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146431"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enabling-network-media-bypass-in-lync-server-2013"></a><span data-ttu-id="db258-102">Lync Server 2013에서 네트워크 미디어 바이패스 사용</span><span class="sxs-lookup"><span data-stu-id="db258-102">Enabling network media bypass in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="db258-103">_**마지막으로 수정 된 항목:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="db258-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="db258-104">미디어 바이패스 설정은 Microsoft Lync Server 2013 배포 전체에서 전역적으로 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="db258-104">Media bypass settings apply globally across a Microsoft Lync Server 2013 deployment.</span></span> <span data-ttu-id="db258-105">미디어 바이패스는 통화가 중재 서버를 바이패스하도록 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="db258-105">Media bypass allows calls to bypass the Mediation Server.</span></span> <span data-ttu-id="db258-106">미디어 바이패스를 사용 하는 경우에 대 한 자세한 내용은 계획 섹션에서 [Lync Server 2013의 미디어 바이패스 계획](lync-server-2013-planning-for-media-bypass.md) 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="db258-106">For details about when to use Media bypass, see [Planning for media bypass in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) in the Planning section.</span></span>

<span data-ttu-id="db258-107">Lync Server 제어판에서 미디어 바이패스를 사용 하도록 설정 하 고 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="db258-107">You can enable and configure media bypass from the Lync Server Control Panel.</span></span>

<div>

## <a name="to-enable-and-configure-media-bypass"></a><span data-ttu-id="db258-108">미디어 바이패스를 사용하도록 설정 및 구성하려면</span><span class="sxs-lookup"><span data-stu-id="db258-108">To enable and configure media bypass</span></span>

1.  <span data-ttu-id="db258-109">RTCUniversalServerAdmins 그룹의 구성원 인 사용자 계정 (또는 이와 동등한 사용자 권한 포함) 또는 CsAdministrator 역할이 할당 되 면 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="db258-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="db258-110">브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="db258-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="db258-111">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="db258-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="db258-112">왼쪽 탐색 모음에서 **네트워크 구성**을 클릭하고 **전역**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="db258-112">In the left navigation bar, click **Network Configuration** and then click **Global**.</span></span>

4.  <span data-ttu-id="db258-p103">**전역** 페이지에서 **전역** 구성을 클릭합니다. 구성은 항상 하나뿐이며 이름은 항상 전역입니다.</span><span class="sxs-lookup"><span data-stu-id="db258-p103">On the **Global** page, click the **Global** configuration. There is always only one configuration, and it is always named Global.</span></span>

5.  <span data-ttu-id="db258-115">**편집** 메뉴에서 **자세히 보기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="db258-115">On the **Edit** menu, click **View details**.</span></span>

6.  <span data-ttu-id="db258-116">**전역 설정 편집** 페이지에서 **미디어 바이패스 사용** 확인란을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="db258-116">On the **Edit Global Setting** page, click the **Enable media bypass** check box.</span></span>

7.  <span data-ttu-id="db258-117">다음 옵션 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="db258-117">Select one of the following options:</span></span>
    
      - <span data-ttu-id="db258-118">**항상 바이패스**   모든 통화에 대해 미디어 바이패스를 시도 하려면이 옵션을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="db258-118">**Always bypass**   Select this option to attempt media bypass on all calls.</span></span> <span data-ttu-id="db258-119">CAC (통화 허용 제어)가 사용 하도록 설정 된 경우에는이 옵션을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="db258-119">This option will be unavailable if call admission control (CAC) is enabled.</span></span> <span data-ttu-id="db258-120">CAC가 사용 되지 않는 경우에는 다음과 같은 상황에서이 옵션을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="db258-120">If CAC is not enabled, select this option in the following situations:</span></span>
        
          - <span data-ttu-id="db258-121">대역폭을 제어할 필요가 없는 경우</span><span class="sxs-lookup"><span data-stu-id="db258-121">There is no need for bandwidth control.</span></span>
        
          - <span data-ttu-id="db258-122">바이패스가 발생하는 시기를 확인하기 위해 세분화된 구성이 필요하지 않은 경우</span><span class="sxs-lookup"><span data-stu-id="db258-122">There is no need for fine-grained configuration to determine when bypass should happen.</span></span>
        
          - <span data-ttu-id="db258-123">게이트웨이와 클라이언트가 완전히 연결된 경우</span><span class="sxs-lookup"><span data-stu-id="db258-123">There is full connectivity between gateways and clients.</span></span>
    
      - <span data-ttu-id="db258-124">**사이트 및 지역 구성**   사용 CAC가 사용 하도록 설정 된 경우이 옵션은 기본적으로 선택 되며 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="db258-124">**Use sites and region configuration**   If CAC is enabled, this option is selected by default and cannot be changed.</span></span> <span data-ttu-id="db258-125">이 옵션을 선택하면 네트워크 구성 사이트 및 지역이 미디어 바이패스가 가능한 때를 확인하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="db258-125">When this option is selected, network configuration sites and regions will be used to determine when media bypass is possible.</span></span> <span data-ttu-id="db258-126">이 옵션을 선택하면 매핑되지 않은 사이트에 바이패스를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="db258-126">If you select this option, you can choose to enable bypass for sites that are not mapped.</span></span> <span data-ttu-id="db258-127">대역폭 제약 조건이 없는 동일한 지역과 연결된 대규모 사이트가 하나 이상 있고(예: 대규모 중앙 사이트) 대역폭 제약 조건이 있는 동일한 지역과 연결된 분기 사이트도 몇 군데 있는 경우에만 **매핑되지 않은 사이트에 대해 바이패스 사용** 확인란을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="db258-127">Click the **Enable bypass for non-mapped sites** check box only if you have one or more large sites associated with the same region that do not have bandwidth constraints (for example, a large central site) and you also have some branch sites associated with the same region that do have bandwidth constraints.</span></span> <span data-ttu-id="db258-128">매핑되지 않은 사이트에 대해 바이패스를 사용하도록 설정하면, 모든 서브넷이 모든 사이트와 연결되도록 지정할 필요 없이 서브넷이 분기 사이트와 연결되도록만 지정하면 되므로 구성이 능률적이게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="db258-128">When you enable bypass for non-mapped sites, configuration is streamlined because you specify only the subnets associated with the branch sites rather than needing to specify all subnets associated with all sites.</span></span> <span data-ttu-id="db258-129">CAC를 사용하도록 설정한 경우에는 **매핑되지 않은 사이트에 대해 바이패스 사용** 확인란을 선택하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="db258-129">We recommend that you do not select the **Enable bypass for non-mapped sites** check box if CAC is enabled.</span></span>

8.  <span data-ttu-id="db258-130">**커밋**을 클릭하여 변경 내용을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="db258-130">Click **Commit** to save your changes.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="db258-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="db258-131">See Also</span></span>


[<span data-ttu-id="db258-132">Lync Server 2013에서 네트워크 미디어 바이패스 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="db258-132">Disabling network media bypass in Lync Server 2013</span></span>](lync-server-2013-disabling-network-media-bypass.md)  


[<span data-ttu-id="db258-133">Lync Server 2013의 글로벌 미디어 바이패스 옵션</span><span class="sxs-lookup"><span data-stu-id="db258-133">Global media bypass options in Lync Server 2013</span></span>](lync-server-2013-global-media-bypass-options.md)  


[<span data-ttu-id="db258-134">Lync Server 2013의 미디어 바이패스 계획</span><span class="sxs-lookup"><span data-stu-id="db258-134">Planning for media bypass in Lync Server 2013</span></span>](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

