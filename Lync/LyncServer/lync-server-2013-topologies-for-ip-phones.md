---
title: 'Lync Server 2013: IP 휴대폰용 토폴로지'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Topologies for IP phones
ms:assetid: 26ebffcf-43ff-4e70-847d-0fbc90e94e57
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425740(v=OCS.15)
ms:contentKeyID: 48183662
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9d3247783acb0f65fb069f418c4a66a4c53b1a83
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980242"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="topologies-for-ip-phones-in-lync-server-2013"></a><span data-ttu-id="f3c0d-102">Lync Server 2013의 IP 전화에 대 한 토폴로지</span><span class="sxs-lookup"><span data-stu-id="f3c0d-102">Topologies for IP phones in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f3c0d-103">_**마지막으로 수정한 주제:** 2012-06-21_</span><span class="sxs-lookup"><span data-stu-id="f3c0d-103">_**Topic Last Modified:** 2012-06-21_</span></span>

<span data-ttu-id="f3c0d-104">이 섹션에서는 연결 프로세스에 대 한 개요를 제공 하 고 내부 및 외부 네트워크에서 IP 휴대폰을 연결 하는 방법의 차이점에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3c0d-104">This section provides an overview of the connectivity process and explains the differences between how an IP phone connects in an internal and external network.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f3c0d-105">Lync Server는 다음 IP 전화에 대 한 지원을 제공 합니다. Aastra 6721ip 일반 지역 전화기, Aastra 6721ip 일반 전화기, HP 4110 IP 전화 (공통 지역 전화), HP 4120 IP 전화 (일반 전화), Polycom CX600 IP 일반 전화기, Polycom CX700 IP 일반 전화기, Polycom CX500 IP 일반적인 지역 전화 및 Polycom CX3000 IP 컨퍼런스 휴대폰.</span><span class="sxs-lookup"><span data-stu-id="f3c0d-105">Lync Server provides support for the following IP phones: the Aastra 6721ip common area phone, Aastra 6725ip desk phone, HP 4110 IP Phone (common area phone), HP 4120 IP Phone (desk phone), Polycom CX600 IP desk phone, Polycom CX700 IP desk phone, Polycom CX500 IP common area phone, and Polycom CX3000 IP conference phone.</span></span> <span data-ttu-id="f3c0d-106">이러한 휴대폰의 경우에는 Polycom CX700 모두 Lync Phone 에디션을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3c0d-106">Of those phones, all but the Polycom CX700 can run Lync Phone Edition.</span></span>



</div>

<span data-ttu-id="f3c0d-107">다음 다이어그램은 회사 환경 내에서 장치 연결과 관련 된 모든 구성 요소를 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3c0d-107">The following diagram describes all the components involved in device connectivity within the corporate environment.</span></span>

<span data-ttu-id="f3c0d-108">**내부 토폴로지**</span><span class="sxs-lookup"><span data-stu-id="f3c0d-108">**Internal Topology**</span></span>

<span data-ttu-id="f3c0d-109">![3d88893e-df57-46e3-855a-a1d24589030a](images/Gg425740.3d88893e-df57-46e3-855a-a1d24589030a(OCS.15).jpg "3d88893e-df57-46e3-855a-a1d24589030a")</span><span class="sxs-lookup"><span data-stu-id="f3c0d-109">![3d88893e-df57-46e3-855a-a1d24589030a](images/Gg425740.3d88893e-df57-46e3-855a-a1d24589030a(OCS.15).jpg "3d88893e-df57-46e3-855a-a1d24589030a")</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f3c0d-110">앞의 그림은 논리적 표현이 며, 실제 개요는 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="f3c0d-110">The previous figure is a logical representation, not a physical overview.</span></span> <span data-ttu-id="f3c0d-111">예를 들어 AD DS (Active Directory 도메인 서비스)는 Lync Server 구성 요소와 동일한 컴퓨터에 있는 경우에는 거의 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f3c0d-111">For example, Active Directory Domain Services (AD DS) is rarely located on the same machine as any Lync Server components.</span></span> <span data-ttu-id="f3c0d-112">사용자 저장소는 백 엔드 서버나 보관 및 모니터링 서버에 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3c0d-112">The user store can be located on the Back End Server or on the Archiving and Monitoring Servers.</span></span> <span data-ttu-id="f3c0d-113">Lync Server 관리 셸, 웹 서버 및 업데이트 서비스는 모두 프런트 엔드 서버 역할의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="f3c0d-113">The Lync Server Management Shell, web server, and update services are all part of the Front End Server role.</span></span>



</div>

<span data-ttu-id="f3c0d-114">다음 다이어그램은 장치가 회사 네트워크 외부에 있는 경우 관련 구성 요소에 대 한 개요를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3c0d-114">The following diagram provides an overview of the components involved when the device is located outside the corporate network.</span></span>

<span data-ttu-id="f3c0d-115">**외부 토폴로지**</span><span class="sxs-lookup"><span data-stu-id="f3c0d-115">**External Topology**</span></span>

<span data-ttu-id="f3c0d-116">![8ce6bb8e-b89c-4c4e-ac6d-41ac6c68f6f3](images/Gg425740.8ce6bb8e-b89c-4c4e-ac6d-41ac6c68f6f3(OCS.15).jpg "8ce6bb8e-b89c-4c4e-ac6d-41ac6c68f6f3")</span><span class="sxs-lookup"><span data-stu-id="f3c0d-116">![8ce6bb8e-b89c-4c4e-ac6d-41ac6c68f6f3](images/Gg425740.8ce6bb8e-b89c-4c4e-ac6d-41ac6c68f6f3(OCS.15).jpg "8ce6bb8e-b89c-4c4e-ac6d-41ac6c68f6f3")</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f3c0d-117">장치 업데이트 웹 서비스는 외부 및 내부 웹 사이트를 제공 하지만 여기에 외부 연결만 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f3c0d-117">The Device Update Web service provides an external and internal website, but only the external one is shown here.</span></span><BR><span data-ttu-id="f3c0d-118">외부 액세스를 사용 하도록 설정 하는 경우 조직에 대 한 디바이스 업데이트 웹 서비스의 위치 및 해당 URL을 DNS에 게시 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3c0d-118">The location of the Registrar and the URL of the Device Update Web service for the organization must be published in DNS if external access is to be enabled.</span></span> <span data-ttu-id="f3c0d-119">또한 Edge 서버는 디바이스에서 회사 환경으로의 외부 통신을 허용 하 고 다시 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3c0d-119">Additionally, the Edge Server must be deployed and correctly configured to allow external communications from the device to the corporate environment and back.</span></span> <span data-ttu-id="f3c0d-120">이는 Edge 배포가 장치 연결에 국한 되지 않으므로 이전 다이어그램에서 생략 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f3c0d-120">This is omitted from the previous diagram because Edge deployment is not specific to device connectivity.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

