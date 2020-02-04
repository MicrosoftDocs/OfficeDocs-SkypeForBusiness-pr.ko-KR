---
title: Lync Server 2013 서버 역할
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Server roles
ms:assetid: 7137fc06-fca2-4e5f-9db5-10c7c29a788c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398536(v=OCS.15)
ms:contentKeyID: 48184456
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b22115bf137c388fd6cd15103ac882056affa4f6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764856"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="server-roles-in-lync-server-2013"></a><span data-ttu-id="db6a2-102">Lync Server 2013의 서버 역할</span><span class="sxs-lookup"><span data-stu-id="db6a2-102">Server roles in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="db6a2-103">_**마지막으로 수정한 주제:** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="db6a2-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="db6a2-104">Lync Server를 실행 하는 각 서버는 하나 이상의 *서버 역할*을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="db6a2-104">Each server running Lync Server runs one or more *server roles*.</span></span> <span data-ttu-id="db6a2-105">서버 역할은 해당 서버에서 제공 하는 Lync Server 기능을 정의한 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="db6a2-105">A server role is a defined set of Lync Server functionalities provided by that server.</span></span> <span data-ttu-id="db6a2-106">네트워크에서 사용 가능한 모든 서버 역할을 배포할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="db6a2-106">You do not need to deploy all available server roles in your network.</span></span> <span data-ttu-id="db6a2-107">원하는 기능이 포함 된 서버 역할만 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="db6a2-107">Install only the server roles that contain the functionality that you want.</span></span>

<span data-ttu-id="db6a2-108">Lync Server의 서버 역할에 익숙하지 않은 경우에도 계획 도구를 사용 하 여 원하는 기능에 따라 배포 해야 하는 서버에 대 한 최상의 솔루션을 안내할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="db6a2-108">Even if you are not familiar with server roles in Lync Server, the Planning Tool can guide you to the best solution for the servers that you need to deploy, based on the features that you want.</span></span> <span data-ttu-id="db6a2-109">이 섹션에서는 서버 역할 및 제공 하는 일반 기능에 대 한 간략 한 개요를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="db6a2-109">This section provides a brief overview of the server roles and the general features that they provide:</span></span>

  - <span data-ttu-id="db6a2-110">Standard Edition 서버</span><span class="sxs-lookup"><span data-stu-id="db6a2-110">Standard Edition Server</span></span>

  - <span data-ttu-id="db6a2-111">프런트 엔드 서버 및 백 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="db6a2-111">Front End Server and Back End Server</span></span>

  - <span data-ttu-id="db6a2-112">Edge 서버</span><span class="sxs-lookup"><span data-stu-id="db6a2-112">Edge Server</span></span>

  - <span data-ttu-id="db6a2-113">중재 서버</span><span class="sxs-lookup"><span data-stu-id="db6a2-113">Mediation Server</span></span>

  - <span data-ttu-id="db6a2-114">Director</span><span class="sxs-lookup"><span data-stu-id="db6a2-114">Director</span></span>

  - <span data-ttu-id="db6a2-115">영구 채팅 프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="db6a2-115">Persistent Chat Front End Server</span></span>

  - <span data-ttu-id="db6a2-116">영구 채팅 저장소 (영구 채팅 백 엔드 서버)</span><span class="sxs-lookup"><span data-stu-id="db6a2-116">Persistent Chat Store (Persistent Chat Back End Server)</span></span>

  - <span data-ttu-id="db6a2-117">영구 채팅 준수 스토어 (영구 채팅 준수 백 엔드 서버)</span><span class="sxs-lookup"><span data-stu-id="db6a2-117">Persistent Chat Compliance Store (Persistent Chat Compliance Back End Server)</span></span>

<span data-ttu-id="db6a2-118">대부분의 서버 역할에서 확장성 및 고가용성을 위해 동일한 서버 역할을 실행 하는 여러 서버의 *풀* 을 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="db6a2-118">For most server roles, for scalability and high availability you can deploy *pools* of multiple servers all running the same server role.</span></span> <span data-ttu-id="db6a2-119">풀의 각 서버는 동일한 서버 역할 또는 역할을 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="db6a2-119">Each server in a pool must run an identical server role or roles.</span></span> <span data-ttu-id="db6a2-120">Lync Server의 대부분의 풀 유형에 대해 부하 분산 장치를 배포 하 여 풀의 다양 한 서버 간에 트래픽을 분산 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="db6a2-120">For most types of pools in Lync Server, you must deploy a load balancer to spread traffic between the various servers in the pool.</span></span> <span data-ttu-id="db6a2-121">Lync Server는 DNS (Domain Name System) 부하 분산 및 하드웨어 부하 분산 장치를 모두 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="db6a2-121">Lync Server supports both Domain Name System (DNS) load balancing and hardware load balancers.</span></span>

<div>

## <a name="standard-edition-server"></a><span data-ttu-id="db6a2-122">Standard Edition 서버</span><span class="sxs-lookup"><span data-stu-id="db6a2-122">Standard Edition Server</span></span>

<span data-ttu-id="db6a2-123">스탠더드 버전 서버는 소규모 조직을 위해 디자인 되었으며 대규모 조직의 경우 파일럿 프로젝트에 적합 합니다.</span><span class="sxs-lookup"><span data-stu-id="db6a2-123">The Standard Edition server is designed for small organizations, and for pilot projects of large organizations.</span></span> <span data-ttu-id="db6a2-124">이를 통해 단일 서버에서 실행 하는 데 필요한 데이터베이스를 비롯 한 다양 한 Lync Server 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="db6a2-124">It enables many of the features of Lync Server, including the necessary databases, to run on a single server.</span></span> <span data-ttu-id="db6a2-125">이렇게 하면 저렴 한 비용으로 Lync Server 기능을 사용할 수 있지만, 진정한 고가용성 솔루션은 제공 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="db6a2-125">This enables you to have Lync Server functionality for a lower cost, but does not provide a true high-availability solution.</span></span>

<span data-ttu-id="db6a2-126">Standard Edition server를 사용 하면 인스턴트 메시지 (IM), 현재 상태, 회의 및 엔터프라이즈 음성을 모두 하나의 서버에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="db6a2-126">Standard Edition server enables you to use instant messaging (IM), presence, conferencing, and Enterprise Voice, all running on one server.</span></span>

<span data-ttu-id="db6a2-127">고가용성 솔루션의 경우 Lync Server Enterprise Edition을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="db6a2-127">For a high-availability solution, use Lync Server Enterprise Edition.</span></span>

</div>

<div>

## <a name="front-end-server-and-back-end-server"></a><span data-ttu-id="db6a2-128">프런트 엔드 서버 및 백 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="db6a2-128">Front End Server and Back End Server</span></span>

<span data-ttu-id="db6a2-129">Lync Server Enterprise Edition에서 프런트 엔드 서버는 핵심 서버 역할을 하 고 다양 한 기본 Lync Server 함수를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="db6a2-129">In Lync Server Enterprise Edition, the Front End Server is the core server role, and runs many basic Lync Server functions.</span></span> <span data-ttu-id="db6a2-130">프런트 엔드 서버는 백 엔드 서버와 함께 Lync Server Enterprise Edition 배포에 있어야 하는 유일한 서버 역할입니다.</span><span class="sxs-lookup"><span data-stu-id="db6a2-130">The Front End Server, along with the Back End Servers, are the only server roles required to be in any Lync Server Enterprise Edition deployment.</span></span>

<span data-ttu-id="db6a2-131">*프런트 엔드 풀* 은 동일 하 게 구성 된 프런트 엔드 서버 집합으로, 공통 사용자 그룹에 대 한 서비스를 제공 하기 위해 함께 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="db6a2-131">A *Front End pool* is a set of Front End Servers, configured identically, that work together to provide services for a common group of users.</span></span> <span data-ttu-id="db6a2-132">동일한 역할을 실행 하는 여러 서버의 풀은 확장성 및 장애 조치 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="db6a2-132">A pool of multiple servers running the same role provides scalability and failover capability.</span></span>

<span data-ttu-id="db6a2-133">프런트 엔드 서버에는 다음이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="db6a2-133">The Front End Server includes the following:</span></span>

  - <span data-ttu-id="db6a2-134">사용자 인증 및 등록</span><span class="sxs-lookup"><span data-stu-id="db6a2-134">User authentication and registration</span></span>

  - <span data-ttu-id="db6a2-135">현재 상태 정보 및 대화 상대 카드 교환</span><span class="sxs-lookup"><span data-stu-id="db6a2-135">Presence information and contact card exchange</span></span>

  - <span data-ttu-id="db6a2-136">주소록 서비스 및 메일 그룹 확장</span><span class="sxs-lookup"><span data-stu-id="db6a2-136">Address book services and distribution list expansion</span></span>

  - <span data-ttu-id="db6a2-137">메신저 대화 회의를 비롯 한 IM 기능</span><span class="sxs-lookup"><span data-stu-id="db6a2-137">IM functionality, including multiparty IM conferences</span></span>

  - <span data-ttu-id="db6a2-138">웹 회의, PSTN 전화 접속 회의 및 A/V 회의 (배포 된 경우)</span><span class="sxs-lookup"><span data-stu-id="db6a2-138">Web conferencing, PSTN Dial-in conferencing and A/V conferencing (if deployed)</span></span>

  - <span data-ttu-id="db6a2-139">Lync Server에 포함 된 응용 프로그램 (예: 회의 수행자 및 응답 그룹 응용 프로그램) 및 타사 응용 프로그램 호스팅</span><span class="sxs-lookup"><span data-stu-id="db6a2-139">Application hosting, for both applications included with Lync Server (for example, Conferencing Attendant and Response Group application), and third-party applications</span></span>

  - <span data-ttu-id="db6a2-140">선택적으로 모니터링을 통해 CDRs (호출 정보 레코드)와 Cer (통화 오류 레코드) 형식으로 사용 정보를 수집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="db6a2-140">Optionally, Monitoring, to collect usage information in the form of call detail records (CDRs) and call error records (CERs).</span></span> <span data-ttu-id="db6a2-141">이 정보는 엔터프라이즈 음성 통화와 A/V 회의에 대 한 네트워크를 통과 하는 미디어 (오디오 및 비디오)의 품질에 대 한 메트릭을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="db6a2-141">This information provides metrics about the quality of the media (audio and video) traversing your network for both Enterprise Voice calls and A/V conferences.</span></span>

  - <span data-ttu-id="db6a2-142">웹 구성 요소를 사용 하 여 web scheduler 및 join 시작 관리자와 같은 지원 되는 웹 기반 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="db6a2-142">Web components to supported web-based tasks such as web scheduler and join launcher.</span></span>

  - <span data-ttu-id="db6a2-143">필요에 따라 보관할 수 있으며, 규정 준수를 위해 IM 통신 및 모임 콘텐츠를 보관 합니다.</span><span class="sxs-lookup"><span data-stu-id="db6a2-143">Optionally, Archiving, to archive IM communications and meeting content for compliance reasons.</span></span> <span data-ttu-id="db6a2-144">자세한 내용은 계획 설명서의 [Lync Server 2013에서 보관 계획](lync-server-2013-planning-for-archiving.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="db6a2-144">For details, see [Planning for Archiving in Lync Server 2013](lync-server-2013-planning-for-archiving.md) in the Planning documentation.</span></span>
    
    <span data-ttu-id="db6a2-145">Lync Server 2010 및 이전 버전에서 모니터링 및 보관은 프런트 엔드 서버에서 collocated 아닌 별도의 서버 역할 이었습니다.</span><span class="sxs-lookup"><span data-stu-id="db6a2-145">In Lync Server 2010 and prior versions, Monitoring and Archiving were separate server roles, not collocated on Front End Server.</span></span>

  - <span data-ttu-id="db6a2-146">선택적으로 영구 채팅을 사용 하는 경우, 파일 업로드/다운로드에 대 한 채팅방 관리 및 영구 채팅 웹 서비스에 대 한 지속적인 채팅 웹 서비스.</span><span class="sxs-lookup"><span data-stu-id="db6a2-146">Optionally, if Persistent chat is enabled, Persistent Chat Web Services for Chat Room Management and Persistent Chat Web Services for File Upload/Download.</span></span>

<span data-ttu-id="db6a2-147">프런트 엔드 풀은 사용자 및 컨퍼런스 데이터에 대 한 기본 저장소 이기도 합니다.</span><span class="sxs-lookup"><span data-stu-id="db6a2-147">Front End Pools are also the primary store for user and conference data.</span></span> <span data-ttu-id="db6a2-148">각 사용자에 대 한 정보는 풀의 세 프런트 엔드 서버 간에 복제 되 고 백 엔드 서버에서 백업 됩니다.</span><span class="sxs-lookup"><span data-stu-id="db6a2-148">Information about each user is replicated among three Front End Servers in the pool, and backed up on the Back End Servers.</span></span>

<span data-ttu-id="db6a2-149">또한 배포의 프런트 엔드 풀 하나는 Lync Server를 실행 하는 모든 서버에 대 한 기본 구성 데이터를 관리 하 고 배포 하는 *중앙 관리 서버*도 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="db6a2-149">Additionally, one Front End pool in the deployment also runs the *Central Management Server*, which manages and deploys basic configuration data to all servers running Lync Server.</span></span> <span data-ttu-id="db6a2-150">중앙 관리 서버는 또한 Lync Server 관리 셸 및 파일 전송 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="db6a2-150">The Central Management Server also provides Lync Server Management Shell and file transfer capabilities.</span></span>

<span data-ttu-id="db6a2-151">백 엔드 서버는 프런트 엔드 풀에 대 한 데이터베이스 서비스를 제공 하는 Microsoft SQL Server를 실행 하는 데이터베이스 서버입니다.</span><span class="sxs-lookup"><span data-stu-id="db6a2-151">The Back End Servers are database servers running Microsoft SQL Server that provide the database services for the Front End pool.</span></span> <span data-ttu-id="db6a2-152">백 엔드 서버는 풀의 사용자 및 회의 데이터에 대 한 백업 저장소 역할을 하며 응답 그룹 데이터베이스와 같은 다른 데이터베이스의 주요 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="db6a2-152">The Back End Servers serve as backup stores for the pool’s user and conference data, and are the primary stores for other databases such as the Response Group database.</span></span> <span data-ttu-id="db6a2-153">단일 백 엔드 서버를 사용할 수 있지만, SQL Server 미러링을 사용 하는 솔루션에는 장애 조치에 권장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="db6a2-153">You can have a single Back End Server, but a solution that uses SQL Server mirroring is recommended for failover.</span></span> <span data-ttu-id="db6a2-154">백 엔드 서버는 Lync Server 소프트웨어를 실행 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="db6a2-154">Back End Servers do not run any Lync Server software.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="db6a2-155">다른 데이터베이스에서 Lync Server 데이터베이스를 collocating 하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="db6a2-155">We do not recommend collocating Lync Server databases with other databases.</span></span> <span data-ttu-id="db6a2-156">이렇게 하면 가용성과 성능이 영향을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="db6a2-156">If you do so, availability and performance may be affected.</span></span>



</div>

<span data-ttu-id="db6a2-157">백 엔드 서버 데이터베이스에 저장 되는 정보에는 현재 상태 정보, 사용자의 연락처 목록, 회의 데이터 (모든 최신 컨퍼런스 상태에 대 한 영구 데이터 포함), 컨퍼런스 일정 데이터 등이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="db6a2-157">Information stored in the Back End Server databases includes presence information, users' Contacts lists, conferencing data, including persistent data about the state of all current conferences, and conference scheduling data.</span></span>

</div>

<div>

## <a name="edge-server"></a><span data-ttu-id="db6a2-158">Edge 서버</span><span class="sxs-lookup"><span data-stu-id="db6a2-158">Edge Server</span></span>

<span data-ttu-id="db6a2-159">Edge Server를 통해 사용자는 조직의 방화벽 외부의 사용자와 통신 하 고 공동 작업할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="db6a2-159">Edge Server enables your users to communicate and collaborate with users outside the organization’s firewalls.</span></span> <span data-ttu-id="db6a2-160">이러한 외부 사용자는 현재 오프 사이트를 사용 중인 조직의 고유한 사용자, 페더레이션 파트너 조직의 사용자, Lync Server 배포에 호스팅되는 회의에 참여 하도록 초대 받은 외부 사용자를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="db6a2-160">These external users can include the organization’s own users who are currently working offsite, users from federated partner organizations, and outside users who have been invited to join conferences hosted on your Lync Server deployment.</span></span> <span data-ttu-id="db6a2-161">또한 Edge 서버는 Windows Live, AOL, Yahoo\!, Google 대화를 포함 하 여 공용 IM 연결 서비스에 대 한 연결을 가능 하 게 합니다.</span><span class="sxs-lookup"><span data-stu-id="db6a2-161">Edge Server also enables connectivity to public IM connectivity services, including Windows Live, AOL, Yahoo\!, and Google Talk.</span></span>

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="db6a2-162">2012 년 9 월 1 일부 터, Microsoft Lync 공용 IM 연결 사용자 구독 라이선스 ("PIC USL")는 신규 또는 갱신 계약에 대해 더 이상 구매할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="db6a2-162">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="db6a2-163">활성 라이선스가 있는 고객은 계속 Yahoo!에 페더레이션 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="db6a2-163">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="db6a2-164">서비스 종료 날짜가 될 때까지 메신저를 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="db6a2-164">Messenger until the service shut down date.</span></span> <span data-ttu-id="db6a2-165">AOL 및 Yahoo!에 대 한 6 월 2014의 기간 종료 날짜</span><span class="sxs-lookup"><span data-stu-id="db6a2-165">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="db6a2-166">님이 발표 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="db6a2-166">has been announced.</span></span> <span data-ttu-id="db6a2-167">자세한 내용은 <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013에서 공개 인스턴트 메신저 연결 지원을</A>참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="db6a2-167">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="db6a2-168">PIC USL은 Lync Server 또는 Office Communications Server와 Yahoo!에 페더레이션 하는 데 필요한 사용자별 사용자 단위 구독 라이선스입니다.</span><span class="sxs-lookup"><span data-stu-id="db6a2-168">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="db6a2-169">받으려면.</span><span class="sxs-lookup"><span data-stu-id="db6a2-169">Messenger.</span></span> <span data-ttu-id="db6a2-170">이 서비스를 제공 하는 Microsoft의 기능은 기본 계약 인 Yahoo!에 대 한 지원을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="db6a2-170">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
> <LI>
> <P><span data-ttu-id="db6a2-171">이전 보다 훨씬 더 많은 수의 Lync는 전세계의 조직과 사용자 간에 연결 하는 강력한 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="db6a2-171">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="db6a2-172">Windows Live Messenger를 사용 하는 페더레이션에서는 Lync 표준 CAL 외에 추가 사용자/장치 라이선스가 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="db6a2-172">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="db6a2-173">Skype 페더레이션이이 목록에 추가 되어 Lync 사용자가 IM 및 음성을 사용 하 여 수백만 명의 사용자에 게 연락할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="db6a2-173">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>



</div>

<span data-ttu-id="db6a2-174">Edge Server를 배포 하면 모바일 장치에서 Lync 기능을 지 원하는 이동성 서비스도 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="db6a2-174">Deploying Edge Server also enables mobility services, which supports Lync functionality on mobile devices.</span></span> <span data-ttu-id="db6a2-175">사용자는 지원 되는 Apple iOS, Android, Windows Phone 또는 Nokia 모바일 장치를 사용 하 여 인스턴트 메시지 보내기 및 받기, 연락처 보기, 현재 상태 보기 등의 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="db6a2-175">Users can use supported Apple iOS, Android, Windows Phone, or Nokia mobile devices to perform activities such as sending and receiving instant messages, viewing contacts, and viewing presence.</span></span> <span data-ttu-id="db6a2-176">또한 모바일 장치는 클릭 하 여 회의에 참가 하 고, 회사, 단일 전화 접속, 음성 메일 및 부재 중 통화를 통해 전화를 걸 수 있는 몇 가지 엔터프라이즈 음성 기능을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="db6a2-176">In addition, mobile devices support some Enterprise Voice features, such as click to join a conference, Call via Work, single number reach, voice mail, and missed calls.</span></span> <span data-ttu-id="db6a2-177">또한 모바일 기능은 백그라운드에서 실행 되는 응용 프로그램을 지원 하지 않는 모바일 장치에 대 한 *푸시 알림을* 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="db6a2-177">The mobility feature also supports *push notifications* for mobile devices that do not support applications running in the background.</span></span> <span data-ttu-id="db6a2-178">푸시 알림은 모바일 응용 프로그램이 비활성 상태일 때 발생 하는 이벤트에 대 한 모바일 장치에 전송 되는 알림입니다.</span><span class="sxs-lookup"><span data-stu-id="db6a2-178">A push notification is a notification that is sent to a mobile device about an event that occurs while a mobile application is inactive.</span></span>

<span data-ttu-id="db6a2-179">또한 Edge 서버에는 프런트 엔드 서버에 XMPP 게이트웨이를 포함 하는 완전 통합 된 확장 가능 메시지 및 현재 상태 프로토콜 (XMPP) 프록시가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="db6a2-179">Edge Servers also include a fully-integrated Extensible Messaging and Presence Protocol (XMPP) proxy, with an XMPP gateway included on Front End Servers.</span></span> <span data-ttu-id="db6a2-180">이 XMPP 구성 요소를 구성 하 여 Lync Server 2013 사용자가 XMPP 기반 파트너 (예: Google 대화 가능)에서 인스턴트 메시지 및 현재 상태에 대 한 연락처를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="db6a2-180">You can configure these XMPP components to enable your Lync Server 2013 users to add contacts from XMPP-based partners (such as Google Talk) for instant messaging and presence.</span></span>

<span data-ttu-id="db6a2-181">자세한 내용은 계획 설명서의 [Lync Server 2013에서 외부 사용자 액세스 계획](lync-server-2013-planning-for-external-user-access.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="db6a2-181">For details, see [Planning for external user access in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md) in the Planning documentation.</span></span>

</div>

<div>

## <a name="mediation-server"></a><span data-ttu-id="db6a2-182">중재 서버</span><span class="sxs-lookup"><span data-stu-id="db6a2-182">Mediation Server</span></span>

<span data-ttu-id="db6a2-183">중재 서버는 엔터프라이즈 음성 및 전화 접속 회의를 구현 하는 데 필요한 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="db6a2-183">Mediation Server is a necessary component for implementing Enterprise Voice and dial-in conferencing.</span></span> <span data-ttu-id="db6a2-184">중재 서버는 신호를 번역 하 고, 일부 구성에서는 내부 Lync Server 인프라와 PSTN (공개 교환 통신 네트워크) 게이트웨이, IP-PBX 또는 SIP (세션 시작 프로토콜) 트렁크 간의 미디어를 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="db6a2-184">Mediation Server translates signaling, and, in some configurations, media between your internal Lync Server infrastructure and a public switched telephone network (PSTN) gateway, IP-PBX, or a Session Initiation Protocol (SIP) trunk.</span></span> <span data-ttu-id="db6a2-185">프런트 엔드 서버와 동일한 서버에서 중재 서버 collocated을 실행 하거나 독립 실행형 중재 서버 풀로 분리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="db6a2-185">You can run Mediation Server collocated on the same server as Front End Server, or separated into a stand-alone Mediation Server pool.</span></span>

<span data-ttu-id="db6a2-186">자세한 내용은 계획 설명서의 [Lync server 2013에서 중재 서버 구성 요소](lync-server-2013-mediation-server-component.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="db6a2-186">For details, see [Mediation Server component in Lync Server 2013](lync-server-2013-mediation-server-component.md) in the Planning documentation.</span></span>

</div>

<div>

## <a name="director"></a><span data-ttu-id="db6a2-187">Director</span><span class="sxs-lookup"><span data-stu-id="db6a2-187">Director</span></span>

<span data-ttu-id="db6a2-188">디렉터는 Lync Server 사용자 요청을 인증할 수 있지만, 사용자 계정이 나 현재 상태 또는 회의 서비스는 제공 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="db6a2-188">Directors can authenticate Lync Server user requests, but they do not home user accounts or provide presence or conferencing services.</span></span> <span data-ttu-id="db6a2-189">디렉터는 외부 사용자 액세스를 가능 하 게 하는 배포의 보안을 강화 하는 데 매우 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="db6a2-189">Directors are most useful to enhance security in deployments that enable external user access.</span></span> <span data-ttu-id="db6a2-190">디렉터는 내부 서버에 보내기 전에 요청을 인증할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="db6a2-190">The Director can authenticate requests before sending them on to internal servers.</span></span> <span data-ttu-id="db6a2-191">서비스 거부 공격을 하는 경우 공격이 디렉터로 종료 되 고 프런트 엔드 서버에 도달 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="db6a2-191">In the case of a denial-of-service attack, the attack ends with the Director and does not reach the Front End servers.</span></span> <span data-ttu-id="db6a2-192">자세한 내용은 계획 설명서의 [Lync Server 2013에서 디렉터에 대 한 시나리오](lync-server-2013-scenarios-for-the-director.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="db6a2-192">For details, see [Scenarios for the Director in Lync Server 2013](lync-server-2013-scenarios-for-the-director.md) in the Planning documentation.</span></span>

</div>

<div>

## <a name="persistent-chat-server-roles"></a><span data-ttu-id="db6a2-193">영구 채팅 서버 역할</span><span class="sxs-lookup"><span data-stu-id="db6a2-193">Persistent Chat Server Roles</span></span>

<span data-ttu-id="db6a2-194">영구 채팅을 통해 사용자는 시간에 따라 유지 되는 단체의 주제 기반 대화에 참여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="db6a2-194">Persistent chat enables users to participate in multiparty, topic-based conversations that persist over time.</span></span> <span data-ttu-id="db6a2-195">영구 채팅 프런트 엔드 서버는 영구 채팅 서비스를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="db6a2-195">The Persistent Chat Front End Server runs the persistent chat service.</span></span> <span data-ttu-id="db6a2-196">영구 채팅 백 엔드 서버에는 채팅 기록 데이터와 범주 및 채팅방에 대 한 정보가 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="db6a2-196">The Persistent Chat Back End Server stores the chat history data, and information about categories and chat rooms.</span></span> <span data-ttu-id="db6a2-197">선택적 영구 채팅 준수 백 엔드 서버는 준수 목적에 대 한 채팅 콘텐츠 및 준수 이벤트를 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="db6a2-197">The optional Persistent Chat Compliance Back End Server can store the chat content and compliance events for the purpose of compliance.</span></span>

<span data-ttu-id="db6a2-198">Lync Server Standard Edition을 실행 하는 서버는 동일한 서버에서 영구 채팅 collocated 실행할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="db6a2-198">Servers running Lync Server Standard Edition can also run Persistent chat collocated on the same server.</span></span> <span data-ttu-id="db6a2-199">Enterprise Edition 프런트 엔드 서버를 사용 하는 경우 영구 채팅 프론트엔드 서버를 collocate 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="db6a2-199">You cannot collocate the Persistent Chat Front End Server with Enterprise Edition Front End Server.</span></span>

<span data-ttu-id="db6a2-200">자세한 내용은 [Lync server 2013의 영구 채팅 서버 계획](lync-server-2013-planning-for-persistent-chat-server.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="db6a2-200">For details, see [Planning for Persistent Chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="db6a2-201">참고 항목</span><span class="sxs-lookup"><span data-stu-id="db6a2-201">See Also</span></span>


[<span data-ttu-id="db6a2-202">Lync Server 2013의 중재 서버 구성 요소</span><span class="sxs-lookup"><span data-stu-id="db6a2-202">Mediation Server component in Lync Server 2013</span></span>](lync-server-2013-mediation-server-component.md)  


[<span data-ttu-id="db6a2-203">Lync Server 2013의 보관 계획</span><span class="sxs-lookup"><span data-stu-id="db6a2-203">Planning for Archiving in Lync Server 2013</span></span>](lync-server-2013-planning-for-archiving.md)  
[<span data-ttu-id="db6a2-204">Lync Server 2013의 외부 사용자 액세스 계획</span><span class="sxs-lookup"><span data-stu-id="db6a2-204">Planning for external user access in Lync Server 2013</span></span>](lync-server-2013-planning-for-external-user-access.md)  
[<span data-ttu-id="db6a2-205">Lync Server 2013의 디렉터 시나리오</span><span class="sxs-lookup"><span data-stu-id="db6a2-205">Scenarios for the Director in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-the-director.md)  
[<span data-ttu-id="db6a2-206">Lync Server 2013의 영구 채팅 서버 계획</span><span class="sxs-lookup"><span data-stu-id="db6a2-206">Planning for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-planning-for-persistent-chat-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

