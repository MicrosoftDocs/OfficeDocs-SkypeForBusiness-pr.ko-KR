---
title: 'Lync Server 2013: 미디어 바이패스 모드'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Media bypass modes
ms:assetid: 38c06c81-7e45-4423-9e00-7fbfa4befe46
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425862(v=OCS.15)
ms:contentKeyID: 48183898
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a08ec3ae6d985c18e20964a857a74ad40bc7668d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984729"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="media-bypass-modes-in-lync-server-2013"></a><span data-ttu-id="a76de-102">Lync Server 2013의 미디어 바이패스 모드</span><span class="sxs-lookup"><span data-stu-id="a76de-102">Media bypass modes in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a76de-103">_**마지막으로 수정한 주제:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="a76de-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="a76de-104">미디어 우회를 각 개별 PSTN 트렁크에 대해 전역적으로 또는 개별적으로 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a76de-104">You must configure media bypass both globally and for each individual PSTN trunk.</span></span> <span data-ttu-id="a76de-105">미디어 우회를 전역적으로 사용 하는 경우 두 가지 선택이 가능 합니다. 항상 **사이트 및 지역 정보**를 **우회** 하 고 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a76de-105">When enabling media bypass globally, you have two choices: **Always Bypass** and **Use Site and Region Information**.</span></span>

<span data-ttu-id="a76de-106">이름에서 알 수 있듯이, 모든 PSTN 호출에 대해 bypass을 시도 하는 것은 **항상 무시** 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a76de-106">As the name suggests, **Always Bypass** means that bypass will be attempted for all PSTN calls.</span></span> <span data-ttu-id="a76de-107">**항상 바이패스** 는 통화 허용 제어를 사용할 필요가 없는 배포에 사용 되며 미디어를 우회 하는 경우에 대 한 자세한 구성 정보를 지정할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a76de-107">**Always Bypass** is used for deployments where there is no need to enable call admission control, nor is there a need to specify detailed configuration information regarding when to attempt media bypass.</span></span> <span data-ttu-id="a76de-108">더욱이 클라이언트와 PSTN 게이트웨이 간에 완전 한 연결이 있는 경우 **항상 Bypass** 를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a76de-108">Furthermore, **Always Bypass** is used when there is full connectivity between clients and PSTN gateways.</span></span> <span data-ttu-id="a76de-109">이 구성에서는 모든 서브넷이 한 번의 우회 ID로 매핑되고 시스템에서 계산 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a76de-109">In this configuration, all subnets are mapped to one and only one bypass ID, which is computed by the system.</span></span>

<span data-ttu-id="a76de-110">**사이트 및 지역 정보를 사용**하면 사이트 및 지역 구성과 연결 된 우회 ID를 사용 하 여 우회를 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a76de-110">With **Use Site and Region Information**, the bypass ID associated with site and region configuration is used to make the bypass decision.</span></span> <span data-ttu-id="a76de-111">이 구성은 bypass이 발생 하는 경우에 대 한 세부적인 제어 기능을 제공 하 고 호출 허용 제어 (CAC)와의 상호 작용을 지원 하기 때문에 대부분의 일반적인 토폴로지에 대해 우회를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a76de-111">This configuration provides the flexibility to configure bypass for most common topologies, as it gives you fine-grained control over when bypass happens, in addition to supporting interactions with call admission control (CAC).</span></span> <span data-ttu-id="a76de-112">시스템은 다음과 같이 우회 Id를 자동으로 할당 하 여 작업을 간편 하 게 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="a76de-112">The system tries to ease your task by automatically assigning bypass IDs as follows.</span></span>

  - <span data-ttu-id="a76de-113">시스템은 각 지역에 고유한 단일 우회 ID를 자동으로 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="a76de-113">The system automatically assigns a single unique bypass ID to each region.</span></span>

  - <span data-ttu-id="a76de-114">대역폭 제약 조건을 사용 하지 않고 WAN 링크를 통해 지역에 연결 된 모든 사이트는 지역과 동일한 우회 ID를 상속 합니다.</span><span class="sxs-lookup"><span data-stu-id="a76de-114">Any site connected to a region over a WAN link without bandwidth constraints inherits the same bypass ID as the region.</span></span>

  - <span data-ttu-id="a76de-115">제한 된 대역폭이 있는 WAN 링크를 통해 지역에 연결 된 사이트에는 지역과 다른 우회 ID가 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a76de-115">A site associated with the region over a WAN link with constrained bandwidth is assigned a different bypass ID from that of the region.</span></span>

  - <span data-ttu-id="a76de-116">각 사이트에 연결 된 서브넷은 해당 사이트의 우회 ID를 상속 합니다.</span><span class="sxs-lookup"><span data-stu-id="a76de-116">Subnets associated with each site inherit the bypass ID for that site.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="a76de-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a76de-117">See Also</span></span>


[<span data-ttu-id="a76de-118">Lync Server 2013의 미디어 바이패스 개요</span><span class="sxs-lookup"><span data-stu-id="a76de-118">Overview of media bypass in Lync Server 2013</span></span>](lync-server-2013-overview-of-media-bypass.md)  
[<span data-ttu-id="a76de-119">Lync Server 2013의 미디어 바이패스 및 통화 허용 제어 서비스</span><span class="sxs-lookup"><span data-stu-id="a76de-119">Media bypass and call admission control in Lync Server 2013</span></span>](lync-server-2013-media-bypass-and-call-admission-control.md)  
[<span data-ttu-id="a76de-120">Lync Server 2013의 미디어 바이패스에 대한 기술 요구 사항</span><span class="sxs-lookup"><span data-stu-id="a76de-120">Technical requirements for media bypass in Lync Server 2013</span></span>](lync-server-2013-technical-requirements-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

