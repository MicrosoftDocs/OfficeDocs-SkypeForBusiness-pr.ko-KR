---
title: 'Lync Server 2013: 미디어 바이패스 및 통화 허용 제어 서비스'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Media bypass and call admission control
ms:assetid: 120b2a2b-5f97-4735-a2ee-0f849feb8c1d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398203(v=OCS.15)
ms:contentKeyID: 48183454
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3c5e02a57add6b93f1ad5c5efc3ac644e65e97f4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983110"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="media-bypass-and-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="60030-102">Lync Server 2013의 미디어 바이패스 및 통화 허용 제어 서비스</span><span class="sxs-lookup"><span data-stu-id="60030-102">Media bypass and call admission control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="60030-103">_**마지막으로 수정한 주제:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="60030-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="60030-104">미디어 바이패스 및 호출 허용 제어 (CAC)는 함께 작동 하 여 통화 미디어에 대 한 대역폭 제어를 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="60030-104">Media bypass and call admission control (CAC) work together to manage bandwidth control for call media.</span></span> <span data-ttu-id="60030-105">미디어 바이패스는 잘 연결 된 링크 보다 미디어 흐름을 용이 하 게 합니다. CAC는 대역폭 제약 조건이 있는 링크의 트래픽을 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="60030-105">Media bypass facilitates media flow over well-connected links; CAC manages traffic on links with bandwidth constraints.</span></span> <span data-ttu-id="60030-106">미디어 바이패스와 CAC는 함께 사용할 수 없기 때문에 다른 사용자에 대 한 계획을 수립할 때에는 유의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="60030-106">Because Media Bypass and CAC are mutually exclusive, you must be mindful of one when planning for the other.</span></span> <span data-ttu-id="60030-107">다음과 같은 조합이 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="60030-107">The following combinations are supported:</span></span>

  - <span data-ttu-id="60030-108">CAC 및 미디어 바이패스를 모두 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60030-108">CAC and Media Bypass are both enabled.</span></span> <span data-ttu-id="60030-109">미디어 바이패스는 **사이트 및 지역 정보를 사용**하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="60030-109">Media Bypass must be set to **Use Site and Region Information**.</span></span> <span data-ttu-id="60030-110">이 사이트 및 지역 정보는 CAC에 사용 되는 것과 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="60030-110">This site and region information is the same as that used for CAC.</span></span>
    
    <span data-ttu-id="60030-111">CAC를 사용 하도록 설정 하는 경우 두 구성은 함께 사용할 수 없으므로 **항상 무시**를 선택 하거나 그 반대의 경우도 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="60030-111">If you enable CAC, you cannot select **Always Bypass**, and vice-versa, because the two configurations are mutually exclusive.</span></span> <span data-ttu-id="60030-112">즉, 두 가지 중 하나만 지정 된 PSTN 통화에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="60030-112">That is, only one of the two will apply to any given PSTN call.</span></span> <span data-ttu-id="60030-113">먼저 미디어 바이패스가 통화에 적용 되는지 여부를 확인 하는 검사가 이루어집니다.</span><span class="sxs-lookup"><span data-stu-id="60030-113">First, a check is made to determine if media bypass applies to the call.</span></span> <span data-ttu-id="60030-114">그렇다면 CAC는 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="60030-114">If it does, then CAC is not used.</span></span> <span data-ttu-id="60030-115">이는 호출을 우회할 자격이 있는 경우에는 CAC가 필요 하지 않은 연결을 사용 하 여 정의에 따라 의미가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60030-115">This makes sense, because if a call is eligible for bypass, it is by definition using a connection where CAC is not needed.</span></span> <span data-ttu-id="60030-116">우회가 호출에 적용 될 수 없는 경우 (즉, 클라이언트의 및 게이트웨이에서 우회 Id가 일치 하지 않는 경우), CAC가 통화에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="60030-116">If bypass cannot be applied to the call (that is, if the client’s and gateway’s bypass IDs do not match), then CAC is applied to the call.</span></span>

  - <span data-ttu-id="60030-117">CAC를 사용 하지 않도록 설정 하 고 미디어 바이패스를 **항상 무시**로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="60030-117">CAC not enabled and Media Bypass set to **Always Bypass**.</span></span>
    
    <span data-ttu-id="60030-118">이 구성에서는 클라이언트 및 트렁크 서브넷이 모두 시스템에서 계산 되는 한 우회 ID 하나에만 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="60030-118">In this configuration, both client and trunk subnets are mapped to one and only one bypass ID, which is computed by the system.</span></span>

  - <span data-ttu-id="60030-119">CAC가 설정 되지 않고 미디어 우회가 **사이트 및 지역 정보를 사용**하도록 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="60030-119">CAC not enabled and Media Bypass set to **Use Site and Region Information**.</span></span>
    
    <span data-ttu-id="60030-120">**사이트 및 지역 정보 사용** 이 설정 되어 있는 경우에는 CAC 사용 여부에 관계 없이 기본적으로 같은 방식으로 결정을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="60030-120">Where **Use Site and Region Information** is enabled, bypass determination works essentially the same way, regardless of whether CAC is enabled or not.</span></span> <span data-ttu-id="60030-121">즉, 지정 된 PSTN 통화에 대해 클라이언트의 서브넷이 특정 사이트에 매핑되고 해당 서브넷의 우회 ID가 추출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="60030-121">That is, for any given PSTN call, the client’s subnet is mapped to a particular site, and the bypass ID for that subnet is extracted.</span></span> <span data-ttu-id="60030-122">마찬가지로, 게이트웨이 서브넷은 특정 사이트에 매핑되고 해당 서브넷의 우회 ID는 추출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="60030-122">Similarly, the gateway’s subnet is mapped to a particular site, and the bypass ID for that subnet is extracted.</span></span> <span data-ttu-id="60030-123">두 우회 Id가 동일한 경우에만 통화에 대해 예외가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="60030-123">Only if the two bypass IDs are identical will bypass happen for the call.</span></span> <span data-ttu-id="60030-124">두 항목이 동일 하지 않으면 미디어 바이패스는 발생 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="60030-124">If they are not identical, media bypass will not occur.</span></span>
    
    <span data-ttu-id="60030-125">CAC는 전역적으로 사용 하지 않도록 설정 되어 있지만 사이트 및 지역 구성을 사용 하 여 우회 결정을 제어 하려는 경우 각 사이트 및 링크에 대해 대역폭 정책을 정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="60030-125">Even though CAC is disabled globally, bandwidth policy needs to be defined for each site and link if you want to use site-and-region configuration to control the bypass decision.</span></span> <span data-ttu-id="60030-126">대역폭 제약 조건의 실제 값 또는 해당 모달은 중요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="60030-126">The actual value of the bandwidth constraint or its modality doesn’t matter.</span></span> <span data-ttu-id="60030-127">궁극적인 목표는 시스템에서 자동으로 다른 우회 Id를 계산 하 여 잘 연결 되지 않은 다른 로캘에 연결 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="60030-127">The ultimate goal is to have the system automatically calculate different bypass IDs to associate with different locales that are not well connected.</span></span> <span data-ttu-id="60030-128">정의에 따라 대역폭 제약 조건을 정의 하면 링크가 제대로 연결 되지 않은 것입니다.</span><span class="sxs-lookup"><span data-stu-id="60030-128">Defining a bandwidth constraint by definition means a link is not well connected.</span></span>

  - <span data-ttu-id="60030-129">CAC가 사용 하도록 설정 되어 있고 미디어 바이패스를 사용 하도록 설정 되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="60030-129">CAC is enabled and media bypass is not enabled.</span></span> <span data-ttu-id="60030-130">이는 모든 게이트웨이 및 IP Pbx가 잘 연결 되지 않았거나 미디어 바이패스에 대 한 다른 요구 사항을 충족 하지 않는 경우에만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="60030-130">This would apply only where all gateways and IP-PBXs are not well connected or do not meet other requirements for media bypass.</span></span> <span data-ttu-id="60030-131">미디어 바이패스 요구 사항에 대 한 자세한 내용은 [Lync Server 2013의 미디어 바이패스에 대 한 기술 요구 사항을](lync-server-2013-technical-requirements-for-media-bypass.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="60030-131">For details about requirements for media bypass, see [Technical requirements for media bypass in Lync Server 2013](lync-server-2013-technical-requirements-for-media-bypass.md).</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="60030-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="60030-132">See Also</span></span>


[<span data-ttu-id="60030-133">Lync Server 2013의 미디어 바이패스 개요</span><span class="sxs-lookup"><span data-stu-id="60030-133">Overview of media bypass in Lync Server 2013</span></span>](lync-server-2013-overview-of-media-bypass.md)  
[<span data-ttu-id="60030-134">Lync Server 2013의 미디어 바이패스 모드</span><span class="sxs-lookup"><span data-stu-id="60030-134">Media bypass modes in Lync Server 2013</span></span>](lync-server-2013-media-bypass-modes.md)  
[<span data-ttu-id="60030-135">Lync Server 2013의 미디어 바이패스에 대한 기술 요구 사항</span><span class="sxs-lookup"><span data-stu-id="60030-135">Technical requirements for media bypass in Lync Server 2013</span></span>](lync-server-2013-technical-requirements-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

