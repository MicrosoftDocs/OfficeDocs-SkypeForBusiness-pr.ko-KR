---
title: 'Lync Server 2013: Enterprise Voice 계획'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for Enterprise Voice
ms:assetid: fd8d5867-0ac9-47f8-94f0-1c3ee5e25575
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413081(v=OCS.15)
ms:contentKeyID: 48185959
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 90b93d43637585f164f2f9d79d48bb7839a6dc56
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42202084"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="320cf-102">Lync Server 2013의 Enterprise Voice 계획</span><span class="sxs-lookup"><span data-stu-id="320cf-102">Planning for Enterprise Voice in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="320cf-103">_**마지막으로 수정 된 항목:** 2013-11-01_</span><span class="sxs-lookup"><span data-stu-id="320cf-103">_**Topic Last Modified:** 2013-11-01_</span></span>

<span data-ttu-id="320cf-104">Enterprise Voice에 대 한 배포 프로세스는 지원 하려는 기존 토폴로지, 인프라 및 Enterprise Voice 기능에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="320cf-104">The deployment process for Enterprise Voice depends on your existing topology, infrastructure, and the Enterprise Voice functionality that you want to support.</span></span> <span data-ttu-id="320cf-105">필수 절차는 선택한 기능에 따라 달라지지만 상위 수준에서 기타 계획 고려 사항을 파악해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="320cf-105">The required procedures will depend on what features you choose, but there are other planning considerations that you must make at a high level.</span></span>

<span data-ttu-id="320cf-106">일반적으로 배포할 사이트 유형 및 수, 지리적 위치, 각 사이트에서의 통화량, 사이트를 연결하는 네트워크 링크 유형, 각 사이트의 음성 기능에 대해 중복성 및 장애 조치 제공 여부 및 기존 PBX 장비 사용 여부 등을 고려합니다.</span><span class="sxs-lookup"><span data-stu-id="320cf-106">In general, consider the type and number of sites that you want to deploy and their geographical locations, the call volume at each site, the types of network links that connect sites, whether you want to provide redundancy and failover for voice functionality for each site, and whether you want to use existing PBX equipment.</span></span> <span data-ttu-id="320cf-107">고가용성과 같이 Lync Server 통신 소프트웨어를 전체적으로 계획할 때 고려해 야 하는 몇 가지 고려 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="320cf-107">There are certain considerations, such as high availability, that you should consider when you plan for Lync Server  communications software as a whole.</span></span> <span data-ttu-id="320cf-108">이러한 고려 사항은 필요에 따라 이 섹션 전체의 항목에서 반복하여 설명됩니다.</span><span class="sxs-lookup"><span data-stu-id="320cf-108">These considerations are discussed in topics throughout this section, as needed.</span></span>

<div>

## <a name="planning-considerations"></a><span data-ttu-id="320cf-109">계획 고려 사항</span><span class="sxs-lookup"><span data-stu-id="320cf-109">Planning Considerations</span></span>

<span data-ttu-id="320cf-110">특정 엔터프라이즈 음성 기능 또는 배포 시나리오 또는 구성 요소의 배포와 관련 된 계획 결정을 보려면이 섹션의 항목을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="320cf-110">For planning decisions that pertain to the deployment of a particular Enterprise Voice capability or deployment scenario or component, consult the topics in this section.</span></span>

  - [<span data-ttu-id="320cf-111">Lync Server 2013에서 Enterprise Voice에 대 한 요구 사항 정의</span><span class="sxs-lookup"><span data-stu-id="320cf-111">Defining your requirements for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-defining-your-requirements-for-enterprise-voice.md)

  - [<span data-ttu-id="320cf-112">Lync Server 2013의 음성 사용량 및 트래픽 예상</span><span class="sxs-lookup"><span data-stu-id="320cf-112">Estimating voice usage and traffic for Lync Server 2013</span></span>](lync-server-2013-estimating-voice-usage-and-traffic.md)

  - [<span data-ttu-id="320cf-113">Lync Server 2013의 고급 Enterprise Voice 기능에 대 한 네트워크 설정</span><span class="sxs-lookup"><span data-stu-id="320cf-113">Network settings for the advanced Enterprise Voice features in Lync Server 2013</span></span>](lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md)

  - [<span data-ttu-id="320cf-114">Lync Server 2013의 Enterprise Voice에 필요한 구성 요소</span><span class="sxs-lookup"><span data-stu-id="320cf-114">Components required for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-components-required-for-enterprise-voice.md)

  - [<span data-ttu-id="320cf-115">Lync Server 2013의 Enterprise Voice 복구 계획</span><span class="sxs-lookup"><span data-stu-id="320cf-115">Planning for Enterprise Voice resiliency in Lync Server 2013</span></span>](lync-server-2013-planning-for-enterprise-voice-resiliency.md)

  - [<span data-ttu-id="320cf-116">Lync Server 2013의 Exchange 통합 메시징 통합 계획</span><span class="sxs-lookup"><span data-stu-id="320cf-116">Planning for Exchange Unified Messaging integration in Lync Server 2013</span></span>](lync-server-2013-planning-for-exchange-unified-messaging-integration.md)

  - [<span data-ttu-id="320cf-117">Lync Server 2013의 통화 허용 제어 계획</span><span class="sxs-lookup"><span data-stu-id="320cf-117">Planning for call admission control in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-admission-control.md)

  - [<span data-ttu-id="320cf-118">Lync Server 2013의 응급 서비스 계획 (E9-1-1)</span><span class="sxs-lookup"><span data-stu-id="320cf-118">Planning for emergency services (E9-1-1) in Lync Server 2013</span></span>](lync-server-2013-planning-for-emergency-services-e9-1-1.md)

  - [<span data-ttu-id="320cf-119">Lync Server 2013의 미디어 바이패스 계획</span><span class="sxs-lookup"><span data-stu-id="320cf-119">Planning for media bypass in Lync Server 2013</span></span>](lync-server-2013-planning-for-media-bypass.md)

  - [<span data-ttu-id="320cf-120">Lync Server 2013를 사용 하 여 전용 전화선 계획</span><span class="sxs-lookup"><span data-stu-id="320cf-120">Planning for private telephone lines with Lync Server 2013</span></span>](lync-server-2013-planning-for-private-telephone-lines.md)

  - [<span data-ttu-id="320cf-121">Lync Server 2013의 위치 기반 라우팅 계획</span><span class="sxs-lookup"><span data-stu-id="320cf-121">Planning for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-planning-for-location-based-routing.md)

  - [<span data-ttu-id="320cf-122">Lync Server 2013의 Enterprise Voice 복구 계획</span><span class="sxs-lookup"><span data-stu-id="320cf-122">Planning for Enterprise Voice resiliency in Lync Server 2013</span></span>](lync-server-2013-planning-for-enterprise-voice-resiliency.md)

  - [<span data-ttu-id="320cf-123">Lync Server 2013의 Enterprise Voice에 대 한 배포 지침</span><span class="sxs-lookup"><span data-stu-id="320cf-123">Deployment guidelines for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-deployment-guidelines-for-enterprise-voice.md)

  - [<span data-ttu-id="320cf-124">Lync Server 2013의 Enterprise Voice에 대 한 배포 프로세스 개요</span><span class="sxs-lookup"><span data-stu-id="320cf-124">Deployment process overview for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-deployment-process-overview-for-enterprise-voice.md)

  - [<span data-ttu-id="320cf-125">Lync Server 2013에서 Enterprise Voice로 사용자 이동</span><span class="sxs-lookup"><span data-stu-id="320cf-125">Moving users to Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-moving-users-to-enterprise-voice.md)

  - [<span data-ttu-id="320cf-126">Lync Server 2013의 lync PreCall 진단 도구</span><span class="sxs-lookup"><span data-stu-id="320cf-126">Lync PreCall Diagnostics Tool in Lync Server 2013</span></span>](lync-server-2013-lync-precall-diagnostics-tool.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

