---
title: 'Lync Server 2013: 미디어 바이패스 모드'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Media bypass modes
ms:assetid: 38c06c81-7e45-4423-9e00-7fbfa4befe46
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425862(v=OCS.15)
ms:contentKeyID: 48183898
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 56e3c70e8bfc1a475436df97e4f2e3a5b4f32689
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42217664"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="media-bypass-modes-in-lync-server-2013"></a><span data-ttu-id="5ea6b-102">Lync Server 2013의 미디어 바이패스 모드</span><span class="sxs-lookup"><span data-stu-id="5ea6b-102">Media bypass modes in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5ea6b-103">_**마지막으로 수정 된 항목:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="5ea6b-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="5ea6b-p101">미디어 바이패스는 전역적으로, 그리고 개별 PSTN 트렁크에 대해 구성해야 합니다. 미디어 바이패스를 전역적으로 사용하도록 설정할 때는 **항상 바이패스**와 **사이트 및 지역 정보 사용**의 두 가지 옵션 중에서 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ea6b-p101">You must configure media bypass both globally and for each individual PSTN trunk. When enabling media bypass globally, you have two choices: **Always Bypass** and **Use Site and Region Information**.</span></span>

<span data-ttu-id="5ea6b-p102">옵션 이름에서 알 수 있듯이, **항상 바이패스**는 모든 PSTN 통화에 대해 바이패스를 시도한다는 의미입니다. 통화 허용 제어를 사용하도록 설정할 필요가 없으며, 미디어 바이패스 시도 시기와 관련하여 자세한 구성 정보도 지정할 필요가 없는 배포에서는 **항상 바이패스**를 사용합니다. 또한, 클라이언트와 PSTN 게이트웨이가 완전히 연결되는 경우에도 **항상 바이패스**가 사용됩니다. 이 구성에서는 모든 서브넷이 단일 바이패스 ID에 매핑됩니다. ID는 이 항목 하나뿐이며, 시스템에서 자동으로 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="5ea6b-p102">As the name suggests, **Always Bypass** means that bypass will be attempted for all PSTN calls. **Always Bypass** is used for deployments where there is no need to enable call admission control, nor is there a need to specify detailed configuration information regarding when to attempt media bypass. Furthermore, **Always Bypass** is used when there is full connectivity between clients and PSTN gateways. In this configuration, all subnets are mapped to one and only one bypass ID, which is computed by the system.</span></span>

<span data-ttu-id="5ea6b-p103">**사이트 및 지역 정보 사용**을 사용하는 경우 사이트 및 지역 구성과 연결된 바이패스 ID를 사용하여 바이패스 관련 결정을 내립니다. 이 구성에서는 대부분의 일반 토폴로지에 대해 바이패스를 유동적으로 구성할 수 있습니다. 바이패스 수행 시기를 세밀하게 제어할 수 있으며, CAC(통화 허용 제어)와의 상호 작용도 지원되기 때문입니다. 시스템에서는 다음과 같이 바이패스 ID를 자동으로 할당하여 작업을 손쉽게 수행할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ea6b-p103">With **Use Site and Region Information**, the bypass ID associated with site and region configuration is used to make the bypass decision. This configuration provides the flexibility to configure bypass for most common topologies, as it gives you fine-grained control over when bypass happens, in addition to supporting interactions with call admission control (CAC). The system tries to ease your task by automatically assigning bypass IDs as follows.</span></span>

  - <span data-ttu-id="5ea6b-113">시스템에서 각 지역에 단일 고유 바이패스 ID를 자동으로 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="5ea6b-113">The system automatically assigns a single unique bypass ID to each region.</span></span>

  - <span data-ttu-id="5ea6b-114">대역폭 제약 조건 없이 WAN 링크를 통해 지역에 연결된 사이트는 지역과 동일한 바이패스 ID를 상속합니다.</span><span class="sxs-lookup"><span data-stu-id="5ea6b-114">Any site connected to a region over a WAN link without bandwidth constraints inherits the same bypass ID as the region.</span></span>

  - <span data-ttu-id="5ea6b-115">대역폭이 제한된 WAN 링크를 통해 지역에 연결된 사이트에는 지역과 다른 바이패스 ID가 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="5ea6b-115">A site associated with the region over a WAN link with constrained bandwidth is assigned a different bypass ID from that of the region.</span></span>

  - <span data-ttu-id="5ea6b-116">각 사이트와 연결된 서브넷은 해당 사이트의 바이패스 ID를 상속합니다.</span><span class="sxs-lookup"><span data-stu-id="5ea6b-116">Subnets associated with each site inherit the bypass ID for that site.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="5ea6b-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5ea6b-117">See Also</span></span>


[<span data-ttu-id="5ea6b-118">Lync Server 2013의 미디어 바이패스 개요</span><span class="sxs-lookup"><span data-stu-id="5ea6b-118">Overview of media bypass in Lync Server 2013</span></span>](lync-server-2013-overview-of-media-bypass.md)  
[<span data-ttu-id="5ea6b-119">Lync Server 2013의 미디어 바이패스 및 통화 허용 제어 서비스</span><span class="sxs-lookup"><span data-stu-id="5ea6b-119">Media bypass and call admission control in Lync Server 2013</span></span>](lync-server-2013-media-bypass-and-call-admission-control.md)  
[<span data-ttu-id="5ea6b-120">Lync Server 2013의 미디어 바이패스에 대 한 기술 요구 사항</span><span class="sxs-lookup"><span data-stu-id="5ea6b-120">Technical requirements for media bypass in Lync Server 2013</span></span>](lync-server-2013-technical-requirements-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

