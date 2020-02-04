---
title: 소규모 조직을 위한 Lync Server 2013 참조 토폴로지
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
ms.openlocfilehash: 7e0171d9678d5d890cf4ecb81f6de25f9b558b05
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746868"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="reference-topology-for-lync-server-2013-in-small-organizations"></a><span data-ttu-id="389ac-102">소규모 조직의 Lync Server 2013에 대 한 참조 토폴로지</span><span class="sxs-lookup"><span data-stu-id="389ac-102">Reference topology for Lync Server 2013 in small organizations</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="389ac-103">_**마지막으로 수정한 주제:** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="389ac-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="389ac-104">소규모 조직의 참조 토폴로지에는 Lync Server를 실행 하는 서버 3 대만 배포 하 여 강력 하 고 사용 가능한 솔루션을 배포 하는 방법이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="389ac-104">The reference topology for small organizations shows how you can deploy a robust, highly available solution by deploying only three servers running Lync Server.</span></span>

<span data-ttu-id="389ac-105">**소규모 조직을 위한 참조 토폴로지**</span><span class="sxs-lookup"><span data-stu-id="389ac-105">**Reference topology for small organizations**</span></span>

<span data-ttu-id="389ac-106">![세 개의 서버를 배포하는 참조 토폴로지 다이어그램](images/Gg398095.25196d0d-dd07-451b-83ba-94c0ddf59030(OCS.15).jpg "세 개의 서버를 배포하는 참조 토폴로지 다이어그램")</span><span class="sxs-lookup"><span data-stu-id="389ac-106">![Reference topology deploying three servers diagram](images/Gg398095.25196d0d-dd07-451b-83ba-94c0ddf59030(OCS.15).jpg "Reference topology deploying three servers diagram")</span></span>

  - <span data-ttu-id="389ac-107">\*\*\*\*    이 조직에 배포 된 Standard Edition server 쌍의 중앙 사이트에서 4000 사용자가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="389ac-107">**Pair of Standard Edition Servers Deployed**    This organization has 4,000 users at their central site.</span></span> <span data-ttu-id="389ac-108">조직은 두 개의 표준 버전 서버를 배포 하 고 함께 사용 하 여 고가용성 및 재해 복구를 가능 하 게 합니다.</span><span class="sxs-lookup"><span data-stu-id="389ac-108">The organization has deployed two Standard Edition servers and paired them together to enable high availability and disaster recovery.</span></span> <span data-ttu-id="389ac-109">각 서버 홈에는 2000 사용자가 있지만, 모든 사용자에 대 한 정보는 두 서버 간에 동기화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="389ac-109">Each server homes 2,000 users, but information about all users is synchronized between the two servers.</span></span> <span data-ttu-id="389ac-110">그 중 하나가 발생 하는 경우 관리자는 다른 서버에서 해당 사용자에 게 서비스를 제공할 수 있으므로 사용자에 게 최소한의 장애가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="389ac-110">If one goes down, an administrator can fail over those users to be served by the other server, with a minimum of disruption to users.</span></span> <span data-ttu-id="389ac-111">Lync Server 2013의 고가용성 및 재해 복구 기능에 대 한 자세한 내용은 [Lync server 2013의 고가용성 및 재해 복구 계획](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="389ac-111">For more information about high availability and disaster recovery features in Lync Server 2013, see [Planning for high availability and disaster recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span></span>

  - <span data-ttu-id="389ac-112">**Edge 서버 배포를 권장 합니다.**    내부 인스턴트 메시지, 현재 상태, 회의에는 Edge 서버를 배포 하는 것이 필요 하지 않지만, 소규모 배포의 경우에도이 방법을 권장 합니다.</span><span class="sxs-lookup"><span data-stu-id="389ac-112">**Edge Server deployment is recommended.**   Although deploying an Edge Server is not required for internal IM, presence and conferencing, we recommend it even for small deployments.</span></span> <span data-ttu-id="389ac-113">현재 조직의 방화벽 외부에 있는 사용자에 게 서비스를 제공 하는 Edge 서버를 배포 하 여 Lync 서버 투자를 최대화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="389ac-113">You can maximize your Lync Server investment by deploying an Edge Server to provide service to users currently outside your organization’s firewalls.</span></span> <span data-ttu-id="389ac-114">이러한 혜택에는 다음이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="389ac-114">The benefits include the following:</span></span>
    
      - <span data-ttu-id="389ac-115">조직의 자체 사용자가 집에서 작업 중이거나 여행 중일 때 Lync Server 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="389ac-115">Your organization’s own users can use Lync Server functionality, if they are working from home or are out on the road.</span></span>
    
      - <span data-ttu-id="389ac-116">사용자는 외부 사용자를 초대 하 여 모임에 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="389ac-116">Your users can invite outside users to participate in meetings.</span></span>
    
      - <span data-ttu-id="389ac-117">Lync Server도 함께 사용 하는 파트너, 공급 업체 또는 고객 조직이 있는 경우 해당 조직과 *페더레이션 관계* 를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="389ac-117">If you have a partner, vendor or customer organization that also uses Lync Server, you can form a *federated relationship* with that organization.</span></span> <span data-ttu-id="389ac-118">그러면 Lync Server 배포에서 해당 페더레이션된 조직의 사용자를 인식 하 여 더 나은 공동 작업을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="389ac-118">Your Lync Server deployment would then recognize users from that federated organization, leading to better collaboration.</span></span>
    
      - <span data-ttu-id="389ac-119">사용자는 Windows Live, AOL, Yahoo\!, Google 대화 등의 일부 또는 전부를 포함 하 여 공용 IM 서비스 사용자와 인스턴트 메시지를 교환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="389ac-119">Your users can exchange instant messages with users of public IM services, including any or all of the following: Windows Live, AOL, Yahoo\!, and Google Talk.</span></span> <span data-ttu-id="389ac-120">이러한 서비스를 사용 하는 공용 IM 연결에는 별도의 라이선스가 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="389ac-120">A separate license might be required for public IM connectivity with these services.</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <UL>
        > <LI>
        > <P><span data-ttu-id="389ac-121">2012 년 9 월 1 일부 터, Microsoft Lync 공용 IM 연결 사용자 구독 라이선스 ("PIC USL")는 신규 또는 갱신 계약에 대해 더 이상 구매할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="389ac-121">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="389ac-122">활성 라이선스가 있는 고객은 계속 Yahoo!에 페더레이션 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="389ac-122">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="389ac-123">서비스 종료 날짜가 될 때까지 메신저를 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="389ac-123">Messenger until the service shut down date.</span></span> <span data-ttu-id="389ac-124">AOL 및 Yahoo!에 대 한 6 월 2014의 기간 종료 날짜</span><span class="sxs-lookup"><span data-stu-id="389ac-124">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="389ac-125">님이 발표 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="389ac-125">has been announced.</span></span> <span data-ttu-id="389ac-126">자세한 내용은 <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013에서 공개 인스턴트 메신저 연결 지원을</A>참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="389ac-126">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
        > <LI>
        > <P><span data-ttu-id="389ac-127">PIC USL은 Lync Server 또는 Office Communications Server와 Yahoo!에 페더레이션 하는 데 필요한 사용자별 사용자 단위 구독 라이선스입니다.</span><span class="sxs-lookup"><span data-stu-id="389ac-127">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="389ac-128">받으려면.</span><span class="sxs-lookup"><span data-stu-id="389ac-128">Messenger.</span></span> <span data-ttu-id="389ac-129">이 서비스를 제공 하는 Microsoft의 기능은 기본 계약 인 Yahoo!에 대 한 지원을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="389ac-129">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
        > <LI>
        > <P><span data-ttu-id="389ac-130">이전 보다 훨씬 더 많은 수의 Lync는 전세계의 조직과 사용자 간에 연결 하는 강력한 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="389ac-130">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="389ac-131">Windows Live Messenger를 사용 하는 페더레이션에서는 Lync 표준 CAL 외에 추가 사용자/장치 라이선스가 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="389ac-131">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="389ac-132">Skype 페더레이션이이 목록에 추가 되어 Lync 사용자가 IM 및 음성을 사용 하 여 수백만 명의 사용자에 게 연락할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="389ac-132">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>

        
        </div>

  - <span data-ttu-id="389ac-133">**지점 사이트 survivability.**    이 조직은 Lync Server의 엔터프라이즈 음성 기능 파일럿 프로그램을 실행 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="389ac-133">**Branch site survivability.**   This organization is running a pilot program of the Enterprise Voice feature of Lync Server.</span></span> <span data-ttu-id="389ac-134">일부 사용자는 Lync Server를 유일한 음성 솔루션으로 사용 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="389ac-134">Some users are using Lync Server as their sole voice solution.</span></span> <span data-ttu-id="389ac-135">이러한 음성 파일럿 사용자 중 일부는 지점 사이트에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="389ac-135">Some of these Voice pilot users are located at the branch site.</span></span> <span data-ttu-id="389ac-136">지점 사이트에 중앙 사이트에 대 한 안정적인 WAN (광역 네트워크) 링크가 없으므로 Survivable Branch 기기를 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="389ac-136">The branch site does not have a reliable wide area network (WAN) link to the central site, so a Survivable Branch Appliance is deployed there.</span></span> <span data-ttu-id="389ac-137">이 배포를 통해 WAN 링크가 다운 되는 경우 지사 사이트의 사용자가 계속 해 서 전화를 걸고 받을 수 있습니다 (둘 다 조직 및 PSTN 통화 내에서 전화를 걸고), 음성 메일 기능을 사용 하 고, 2 개의 메신저 대화 (IM)와 통신 합니다.</span><span class="sxs-lookup"><span data-stu-id="389ac-137">With this deployed, if the WAN link goes down, users at the branch site can still make and receive calls (both calls within the organization and PSTN calls), have voice mail functionality, and communicate with two-party instant messaging (IM).</span></span> <span data-ttu-id="389ac-138">또한 WAN 링크를 사용할 수 없는 경우에도 사용자가 인증할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="389ac-138">Users can also be authenticated when the WAN link is unavailable as well.</span></span>

  - <span data-ttu-id="389ac-139">**Exchange UM 배포**</span><span class="sxs-lookup"><span data-stu-id="389ac-139">**Exchange UM deployment.**</span></span> <span data-ttu-id="389ac-140">이 참조 토폴로지에는 Lync Server가 아닌 Microsoft Exchange Server를 실행 하는 UM (Exchange 통합 메시징) 서버가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="389ac-140">This reference topology includes an Exchange Unified Messaging (UM) Server, which runs Microsoft Exchange Server, not Lync Server.</span></span>
    
    <span data-ttu-id="389ac-141">Exchange UM에 대 한 자세한 내용은 계획 설명서의 lync server 2013에서 lync Server 2013 및 [호스트 된 Exchange 통합 메시징 통합](lync-server-2013-hosted-exchange-unified-messaging-integration.md) 의 [exchange 통합 메시징 통합 계획](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="389ac-141">For details about Exchange UM, see [Planning for Exchange Unified Messaging integration in Lync Server 2013](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) and [Hosted Exchange Unified Messaging integration in Lync Server 2013](lync-server-2013-hosted-exchange-unified-messaging-integration.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="389ac-142">**Office Web Apps 서버.**</span><span class="sxs-lookup"><span data-stu-id="389ac-142">**Office Web Apps Server.**</span></span> <span data-ttu-id="389ac-143">웹 회의를 사용 하는 모든 조직에서 Office Web Apps 서버 또는 Office Web Apps 서버 팜을 배포 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="389ac-143">We recommend deploying an Office Web Apps Server or Office Web Apps Server farm in every organization that uses web conferencing.</span></span> <span data-ttu-id="389ac-144">Office Web Apps Server를 통해 PowerPoint 슬라이드를 웹 회의에 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="389ac-144">Office Web Apps Server makes it possible for PowerPoint slides to be presented in web conferences.</span></span> <span data-ttu-id="389ac-145">자세한 내용은 [Office Web Apps 서버 및 Lync server 2013의 통합 구성을](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="389ac-145">For more information, see [Configuring integration with Office Web Apps Server and Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

