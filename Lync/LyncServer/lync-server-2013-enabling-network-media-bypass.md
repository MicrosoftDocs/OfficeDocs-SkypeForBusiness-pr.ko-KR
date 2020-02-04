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
ms.openlocfilehash: 4e0b5e7b060d056a785e80fdf29ded718d120bc1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735798"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-network-media-bypass-in-lync-server-2013"></a><span data-ttu-id="0eb30-102">Lync Server 2013에서 네트워크 미디어 바이패스 사용</span><span class="sxs-lookup"><span data-stu-id="0eb30-102">Enabling network media bypass in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0eb30-103">_**마지막으로 수정한 주제:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="0eb30-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="0eb30-104">미디어 무시 설정은 Microsoft Lync Server 2013 배포 전체에서 전역적으로 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0eb30-104">Media bypass settings apply globally across a Microsoft Lync Server 2013 deployment.</span></span> <span data-ttu-id="0eb30-105">미디어 바이패스는 호출을 사용 하 여 중재 서버를 무시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0eb30-105">Media bypass allows calls to bypass the Mediation Server.</span></span> <span data-ttu-id="0eb30-106">미디어 바이패스를 사용 하는 경우에 대 한 자세한 내용은 계획 섹션의 [Lync Server 2013에서 미디어 바이패스 계획](lync-server-2013-planning-for-media-bypass.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0eb30-106">For details about when to use Media bypass, see [Planning for media bypass in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) in the Planning section.</span></span>

<span data-ttu-id="0eb30-107">Lync Server 제어판에서 미디어 바이패스를 사용 하도록 설정 하 고 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0eb30-107">You can enable and configure media bypass from the Lync Server Control Panel.</span></span>

<div>

## <a name="to-enable-and-configure-media-bypass"></a><span data-ttu-id="0eb30-108">미디어 바이패스를 사용 하도록 설정 하 고 구성 하려면</span><span class="sxs-lookup"><span data-stu-id="0eb30-108">To enable and configure media bypass</span></span>

1.  <span data-ttu-id="0eb30-109">RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsAdministrator 역할에 할당 된 경우 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="0eb30-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="0eb30-110">브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="0eb30-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="0eb30-111">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0eb30-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="0eb30-112">왼쪽 탐색 모음에서 **네트워크 구성을** 클릭 한 다음 **전역**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="0eb30-112">In the left navigation bar, click **Network Configuration** and then click **Global**.</span></span>

4.  <span data-ttu-id="0eb30-113">**전역** 페이지에서 **전역** 구성을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="0eb30-113">On the **Global** page, click the **Global** configuration.</span></span> <span data-ttu-id="0eb30-114">항상 하나의 구성만 있으며 항상 전역 이라는 이름으로 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0eb30-114">There is always only one configuration, and it is always named Global.</span></span>

5.  <span data-ttu-id="0eb30-115">**편집** 메뉴에서 **세부 정보 보기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="0eb30-115">On the **Edit** menu, click **View details**.</span></span>

6.  <span data-ttu-id="0eb30-116">**전역 설정 편집** 페이지에서 **미디어 무시 사용** 확인란을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="0eb30-116">On the **Edit Global Setting** page, click the **Enable media bypass** check box.</span></span>

7.  <span data-ttu-id="0eb30-117">다음 옵션 중 하나를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0eb30-117">Select one of the following options:</span></span>
    
      - <span data-ttu-id="0eb30-118">**항상 건너뛰기**   이 옵션을 선택 하 여 모든 통화에서 미디어를 우회 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="0eb30-118">**Always bypass**   Select this option to attempt media bypass on all calls.</span></span> <span data-ttu-id="0eb30-119">호출 허용 제어 (CAC)를 사용 하는 경우이 옵션을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0eb30-119">This option will be unavailable if call admission control (CAC) is enabled.</span></span> <span data-ttu-id="0eb30-120">CAC를 사용 하도록 설정 하지 않은 경우 다음과 같은 경우이 옵션을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0eb30-120">If CAC is not enabled, select this option in the following situations:</span></span>
        
          - <span data-ttu-id="0eb30-121">대역폭 제어는 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0eb30-121">There is no need for bandwidth control.</span></span>
        
          - <span data-ttu-id="0eb30-122">우회가 발생 하는 경우를 결정할 때는 세밀 한 구성이 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0eb30-122">There is no need for fine-grained configuration to determine when bypass should happen.</span></span>
        
          - <span data-ttu-id="0eb30-123">게이트웨이와 클라이언트 간에는 완전 한 연결이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0eb30-123">There is full connectivity between gateways and clients.</span></span>
    
      - <span data-ttu-id="0eb30-124">**사이트 및 지역 구성**   사용 CAC를 사용 하는 경우이 옵션은 기본적으로 선택 되어 있으며 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0eb30-124">**Use sites and region configuration**   If CAC is enabled, this option is selected by default and cannot be changed.</span></span> <span data-ttu-id="0eb30-125">이 옵션을 선택 하면 네트워크 구성 사이트 및 지역이 미디어 바이패스 가능 여부를 결정 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0eb30-125">When this option is selected, network configuration sites and regions will be used to determine when media bypass is possible.</span></span> <span data-ttu-id="0eb30-126">이 옵션을 선택 하면 매핑되지 않은 사이트에 대해 바이패스를 사용 하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0eb30-126">If you select this option, you can choose to enable bypass for sites that are not mapped.</span></span> <span data-ttu-id="0eb30-127">대역폭 제약 조건이 없는 (예: 대규모 중앙 사이트) 동일한 지역과 연결 된 대규모 사이트가 하나 이상 있는 경우에만 **매핑되지 않은 사이트에 사용 안 함** 확인란을 클릭 하 고 대역폭 제약 조건이 있는 동일한 지역에 연결 된 일부 지점 사이트를 보유 하 고 있는 경우에만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0eb30-127">Click the **Enable bypass for non-mapped sites** check box only if you have one or more large sites associated with the same region that do not have bandwidth constraints (for example, a large central site) and you also have some branch sites associated with the same region that do have bandwidth constraints.</span></span> <span data-ttu-id="0eb30-128">매핑되지 않은 사이트에 대 한 바이패스를 사용 하도록 설정 하면 모든 사이트와 연결 된 모든 서브넷을 지정 하는 대신 지점 사이트와 연결 된 서브넷만 지정 하므로 구성이 간소화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0eb30-128">When you enable bypass for non-mapped sites, configuration is streamlined because you specify only the subnets associated with the branch sites rather than needing to specify all subnets associated with all sites.</span></span> <span data-ttu-id="0eb30-129">CAC를 사용 하는 경우 **매핑되지 않은 사이트에 바이패스 사용** 확인란을 선택 하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="0eb30-129">We recommend that you do not select the **Enable bypass for non-mapped sites** check box if CAC is enabled.</span></span>

8.  <span data-ttu-id="0eb30-130">**커밋을** 클릭 하 여 변경 내용을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="0eb30-130">Click **Commit** to save your changes.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="0eb30-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0eb30-131">See Also</span></span>


[<span data-ttu-id="0eb30-132">Lync Server 2013에서 네트워크 미디어 바이패스를 사용 하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="0eb30-132">Disabling network media bypass in Lync Server 2013</span></span>](lync-server-2013-disabling-network-media-bypass.md)  


[<span data-ttu-id="0eb30-133">Lync Server 2013의 글로벌 미디어 우회 옵션</span><span class="sxs-lookup"><span data-stu-id="0eb30-133">Global media bypass options in Lync Server 2013</span></span>](lync-server-2013-global-media-bypass-options.md)  


[<span data-ttu-id="0eb30-134">Lync Server 2013의 미디어 바이패스 계획</span><span class="sxs-lookup"><span data-stu-id="0eb30-134">Planning for media bypass in Lync Server 2013</span></span>](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

