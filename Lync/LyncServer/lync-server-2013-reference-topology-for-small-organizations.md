---
title: 소규모 조직에 대 한 Lync Server 2013 참조 토폴로지
description: 소규모 조직에 대 한 Lync Server 2013 참조 토폴로지
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Reference topology for small organizations
ms:assetid: 0453aeee-c41f-44e6-a6e0-aaace526ca08
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398095(v=OCS.15)
ms:contentKeyID: 48183272
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7f2f23a963543c303e54f8f2773d499e8317a63a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48578634"
---
# <a name="reference-topology-for-lync-server-2013-in-small-organizations"></a><span data-ttu-id="a9d53-103">소규모 조직의 Lync Server 2013에 대 한 참조 토폴로지</span><span class="sxs-lookup"><span data-stu-id="a9d53-103">Reference topology for Lync Server 2013 in small organizations</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a9d53-104">_**마지막으로 수정 된 항목:** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="a9d53-104">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="a9d53-105">소규모 조직의 참조 토폴로지는 Lync Server를 실행 하는 서버 3 대만 배포 하 여 강력 하 고 가용성이 높은 솔루션을 배포 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a9d53-105">The reference topology for small organizations shows how you can deploy a robust, highly available solution by deploying only three servers running Lync Server.</span></span>

<span data-ttu-id="a9d53-106">**소규모 조직에 대 한 참조 토폴로지**</span><span class="sxs-lookup"><span data-stu-id="a9d53-106">**Reference topology for small organizations**</span></span>

<span data-ttu-id="a9d53-107">![3 개의 서버를 배포 하는 참조 토폴로지 다이어그램](images/Gg398095.25196d0d-dd07-451b-83ba-94c0ddf59030(OCS.15).jpg "3 개의 서버를 배포 하는 참조 토폴로지 다이어그램")</span><span class="sxs-lookup"><span data-stu-id="a9d53-107">![Reference topology deploying three servers diagram](images/Gg398095.25196d0d-dd07-451b-83ba-94c0ddf59030(OCS.15).jpg "Reference topology deploying three servers diagram")</span></span>

  - <span data-ttu-id="a9d53-108">배포 된 Standard **Edition Server 쌍**     이 조직에는 4000 명의 사용자가 중앙 사이트에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9d53-108">**Pair of Standard Edition Servers Deployed**    This organization has 4,000 users at their central site.</span></span> <span data-ttu-id="a9d53-109">조직은 두 개의 Standard Edition 서버를 배포 하 고이를 하나로 연결 하 여 고가용성 및 재해 복구를 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9d53-109">The organization has deployed two Standard Edition servers and paired them together to enable high availability and disaster recovery.</span></span> <span data-ttu-id="a9d53-110">각 서버 홈 2000 사용자는 아니지만, 모든 사용자에 대 한 정보는 두 서버 간에 동기화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a9d53-110">Each server homes 2,000 users, but information about all users is synchronized between the two servers.</span></span> <span data-ttu-id="a9d53-111">그 중 하나가 다운 되 면 관리자가 다른 서버에서 해당 사용자를 처리 하는 데 장애가 발생 하 여 사용자의 업무 중단을 최소화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9d53-111">If one goes down, an administrator can fail over those users to be served by the other server, with a minimum of disruption to users.</span></span> <span data-ttu-id="a9d53-112">Lync Server 2013의 고가용성 및 재해 복구 기능에 대 한 자세한 내용은 [Lync server 2013에서 고가용성 및 재해 복구 계획](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="a9d53-112">For more information about high availability and disaster recovery features in Lync Server 2013, see [Planning for high availability and disaster recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span></span>

  - <span data-ttu-id="a9d53-113">**에 지 서버 배포를 권장 합니다.**     내부 IM, 현재 상태 및 회의에에 지 서버를 배포 하는 것은 필요 하지 않지만 소규모 배포의 경우에도 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="a9d53-113">**Edge Server deployment is recommended.**   Although deploying an Edge Server is not required for internal IM, presence and conferencing, we recommend it even for small deployments.</span></span> <span data-ttu-id="a9d53-114">현재 조직의 방화벽 외부에 있는 사용자에 게 서비스를 제공 하기 위해에 지 서버를 배포 하 여 Lync Server 투자를 최대화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9d53-114">You can maximize your Lync Server investment by deploying an Edge Server to provide service to users currently outside your organization’s firewalls.</span></span> <span data-ttu-id="a9d53-115">이점은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a9d53-115">The benefits include the following:</span></span>
    
      - <span data-ttu-id="a9d53-116">조직의 사용자가 Lync Server 기능을 사용할 수 있으며, 홈에서 작업 중이거나 여행 중에는 작동 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a9d53-116">Your organization’s own users can use Lync Server functionality, if they are working from home or are out on the road.</span></span>
    
      - <span data-ttu-id="a9d53-117">사용자가 외부 사용자를 모임에 초대할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9d53-117">Your users can invite outside users to participate in meetings.</span></span>
    
      - <span data-ttu-id="a9d53-118">Lync Server도 사용 하는 파트너, 공급 업체 또는 고객 조직이 있는 경우 해당 조직과의 *페더레이션 관계* 를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9d53-118">If you have a partner, vendor or customer organization that also uses Lync Server, you can form a *federated relationship* with that organization.</span></span> <span data-ttu-id="a9d53-119">그러면 Lync Server 배포에서 해당 페더레이션 조직의 사용자를 인식 하 고 보다 나은 공동 작업을 가능 하 게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a9d53-119">Your Lync Server deployment would then recognize users from that federated organization, leading to better collaboration.</span></span>
    
      - <span data-ttu-id="a9d53-120">사용자는 Windows Live, AOL, Yahoo \! 및 Google 대화를 비롯 한 공용 IM 서비스 사용자와 인스턴트 메시지를 교환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9d53-120">Your users can exchange instant messages with users of public IM services, including any or all of the following: Windows Live, AOL, Yahoo\!, and Google Talk.</span></span> <span data-ttu-id="a9d53-121">이러한 서비스와의 공용 IM 연결에는 별도의 라이선스가 필요할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9d53-121">A separate license might be required for public IM connectivity with these services.</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <UL>
        > <LI>
        > <P><span data-ttu-id="a9d53-122">2012 년 9 월 1 일, Microsoft Lync 공용 IM 연결 사용자 구독 라이선스 ("PIC USL")를 신규 또는 갱신 동의를 위해 더 이상 구매할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a9d53-122">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="a9d53-123">활성 라이선스를 사용 하는 고객은 Yahoo!에 계속 페더레이션 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9d53-123">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="a9d53-124">서비스 종료 날짜까지 메신저</span><span class="sxs-lookup"><span data-stu-id="a9d53-124">Messenger until the service shut down date.</span></span> <span data-ttu-id="a9d53-125">AOL 및 Yahoo!의 6 월 2014 일 종료 날짜</span><span class="sxs-lookup"><span data-stu-id="a9d53-125">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="a9d53-126">이 발표 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a9d53-126">has been announced.</span></span> <span data-ttu-id="a9d53-127">자세한 내용은 <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013에서 공용 인스턴트 메신저 연결에 대 한 지원을</A>참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a9d53-127">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
        > <LI>
        > <P><span data-ttu-id="a9d53-128">PIC USL은 Lync Server 또는 Office Communications Server와 Yahoo!을 페더레이션 하는 데 필요한 사용자별 구독 라이선스입니다.</span><span class="sxs-lookup"><span data-stu-id="a9d53-128">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="a9d53-129">메신저로.</span><span class="sxs-lookup"><span data-stu-id="a9d53-129">Messenger.</span></span> <span data-ttu-id="a9d53-130">이 서비스를 제공 하는 Microsoft의 기능은 기본 규약에 따라 세로 맞춤에 사용 되는 Yahoo!에 대 한 지원을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9d53-130">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
        > <LI>
        > <P><span data-ttu-id="a9d53-131">이전 보다 Lync는 전 세계의 조직과 조직 간에 연결 하는 강력한 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="a9d53-131">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="a9d53-132">Windows Live Messenger와 페더레이션 하려면 Lync Standard CAL 외에 추가 사용자/장치 라이선스가 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a9d53-132">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="a9d53-133">Lync 사용자가 IM 및 음성을 사용 하 여 수백만 명의 사용자에 게 도달할 수 있도록 하는이 목록에 Skype 페더레이션이 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a9d53-133">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>

        
        </div>

  - <span data-ttu-id="a9d53-134">**지 속성**     분기 사이트 이 조직은 Lync Server의 Enterprise Voice 기능 파일럿 프로그램을 실행 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9d53-134">**Branch site survivability.**   This organization is running a pilot program of the Enterprise Voice feature of Lync Server.</span></span> <span data-ttu-id="a9d53-135">일부 사용자는 Lync Server를 유일한 음성 솔루션으로 사용 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9d53-135">Some users are using Lync Server as their sole voice solution.</span></span> <span data-ttu-id="a9d53-136">이러한 음성 파일럿 사용자 중 일부는 분기 사이트에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9d53-136">Some of these Voice pilot users are located at the branch site.</span></span> <span data-ttu-id="a9d53-137">분기 사이트에 중앙 사이트에 대 한 신뢰할 수 있는 WAN (광역 네트워크) 링크가 없기 때문에 Sba (survivable Branch 기기가 배포 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a9d53-137">The branch site does not have a reliable wide area network (WAN) link to the central site, so a Survivable Branch Appliance is deployed there.</span></span> <span data-ttu-id="a9d53-138">이 배포를 통해 WAN 링크가 다운 될 경우 분기 사이트의 사용자는 계속 해 서 통화를 받고 수신할 수 있으며 (두 통화를 모두 수행 하 여 조직 및 PSTN 통화 내) 음성 메일 기능을 사용 하 고 두 명의 타사 IM (인스턴트 메시징)과 통신 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9d53-138">With this deployed, if the WAN link goes down, users at the branch site can still make and receive calls (both calls within the organization and PSTN calls), have voice mail functionality, and communicate with two-party instant messaging (IM).</span></span> <span data-ttu-id="a9d53-139">또한 WAN 링크를 사용할 수 없는 경우에도 사용자가 인증을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9d53-139">Users can also be authenticated when the WAN link is unavailable as well.</span></span>

  - <span data-ttu-id="a9d53-140">**Exchange UM 배포**</span><span class="sxs-lookup"><span data-stu-id="a9d53-140">**Exchange UM deployment.**</span></span> <span data-ttu-id="a9d53-141">이 참조 토폴로지에는 Lync Server가 아닌 Microsoft Exchange Server를 실행 하는 Exchange UM (통합 메시징) 서버가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9d53-141">This reference topology includes an Exchange Unified Messaging (UM) Server, which runs Microsoft Exchange Server, not Lync Server.</span></span>
    
    <span data-ttu-id="a9d53-142">Exchange UM에 대 한 자세한 내용은 계획 설명서의 lync server 2013에서 Lync server 2013 및 [Hosted Exchange 통합 메시징 통합](lync-server-2013-hosted-exchange-unified-messaging-integration.md) 의 [exchange 통합 메시징 통합 계획](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a9d53-142">For details about Exchange UM, see [Planning for Exchange Unified Messaging integration in Lync Server 2013](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) and [Hosted Exchange Unified Messaging integration in Lync Server 2013](lync-server-2013-hosted-exchange-unified-messaging-integration.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="a9d53-143">**Office Web Apps 서버.**</span><span class="sxs-lookup"><span data-stu-id="a9d53-143">**Office Web Apps Server.**</span></span> <span data-ttu-id="a9d53-144">웹 회의를 사용하는 모든 조직에서 Office Web Apps Server 또는 Office Web Apps Server 팜을 배포하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="a9d53-144">We recommend deploying an Office Web Apps Server or Office Web Apps Server farm in every organization that uses web conferencing.</span></span> <span data-ttu-id="a9d53-145">Office Web Apps 서버를 사용 하면 PowerPoint 슬라이드를 웹 회의에 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9d53-145">Office Web Apps Server makes it possible for PowerPoint slides to be presented in web conferences.</span></span> <span data-ttu-id="a9d53-146">자세한 내용은 [Office Web Apps 서버 및 Lync server 2013의 통합 구성을](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a9d53-146">For more information, see [Configuring integration with Office Web Apps Server and Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

