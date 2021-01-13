---
title: 비즈니스용 Skype 서버의 토폴로지 기본
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 113e8c3f-71de-435c-bc4a-918ac7b50008
description: '요약: 비즈니스용 Skype 서버에 대한 토폴로지 선택 비즈니스용 Skype 서버의 서버 함께 사용에 대해 자세히 알아보습니다.'
ms.openlocfilehash: 9b0dbe6a74a5982c2816c022e5ea7a99ba2abf07
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831758"
---
# <a name="topology-basics-for-skype-for-business-server"></a><span data-ttu-id="44ecf-104">비즈니스용 Skype 서버의 토폴로지 기본</span><span class="sxs-lookup"><span data-stu-id="44ecf-104">Topology Basics for Skype for Business Server</span></span>

<span data-ttu-id="44ecf-105">**요약:** 비즈니스용 Skype 서버에 대한 토폴로지 선택</span><span class="sxs-lookup"><span data-stu-id="44ecf-105">**Summary:** Choose your topology for Skype for Business Server.</span></span> <span data-ttu-id="44ecf-106">비즈니스용 Skype 서버의 서버 함께 사용에 대해 자세히 알아보습니다.</span><span class="sxs-lookup"><span data-stu-id="44ecf-106">Learn about server collocation for Skype for Business Server.</span></span>

<span data-ttu-id="44ecf-107">다른 것을 준비하기 전에 비즈니스용 Skype 서버 배포에 적합한 토폴로지가 계획 중인지 알고 싶을 것입니다.</span><span class="sxs-lookup"><span data-stu-id="44ecf-107">Before preparing anything else, you'll want to know you're planning for the right topology for your deployment of Skype for Business Server.</span></span> <span data-ttu-id="44ecf-108">먼저 결정해야 할 것은 비즈니스용 Skype 서버의 프레미스 배포를 진행할지 아니면 하이브리드 배포에서 비즈니스용 Skype 서버 Online 배포와 결합할지 여부를 결정하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="44ecf-108">The first thing you need to decide is if you're going to have an on-premises deployment of Skype for Business Server, or if you're going to combine this with a Skype for Business Server Online deployment in a Hybrid deployment.</span></span> <span data-ttu-id="44ecf-109">어느 쪽이든, 여기에서는 이 문서에 대한 자세한 내용을 설명하지만 하이브리드 세부 정보는 자체 섹션에 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44ecf-109">Either way, you're going to want to read further, as we'll detail the on-premises topologies here, but the Hybrid details are documented in their own section.</span></span>

<span data-ttu-id="44ecf-110">비즈니스용 Skype 서버의 참조 토폴로지에서 몇 가지 예제 [토폴로지도 볼 수 있습니다.](reference-topologies.md)</span><span class="sxs-lookup"><span data-stu-id="44ecf-110">You can also see some example topologies in [Reference topologies for Skype for Business Server](reference-topologies.md).</span></span>

## <a name="sites"></a><span data-ttu-id="44ecf-111">사이트</span><span class="sxs-lookup"><span data-stu-id="44ecf-111">Sites</span></span>

<span data-ttu-id="44ecf-112">비즈니스용 Skype 서버에서는 네트워크에서 비즈니스용 Skype 서버 구성 요소가 포함된 사이트를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="44ecf-112">In Skype for Business Server, you define sites on your network that contain Skype for Business Server components.</span></span> <span data-ttu-id="44ecf-113">사이트는 단일 LAN(Local Area Network)이나 고속 광섬유 네트워크로 연결된 두 개의 네트워크와 같이 고속, 짧은 대기 시간 네트워크로 견고하게 연결된 컴퓨터 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="44ecf-113">A site is a set of computers that is well-connected by a high-speed, low-latency network, such as a single local area network (LAN) or two networks connected by a high-speed fiber optic network.</span></span> <span data-ttu-id="44ecf-114">비즈니스용 Skype 서버 사이트는 Active Directory 도메인 서비스 사이트 및 비즈니스용 Skype Microsoft Exchange Server 개념입니다.</span><span class="sxs-lookup"><span data-stu-id="44ecf-114">Note that Skype for Business Server sites are a separate concept from Active Directory Domain Services sites and Microsoft Exchange Server sites.</span></span> <span data-ttu-id="44ecf-115">비즈니스용 Skype 서버 사이트는 Active Directory 사이트에 해당할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="44ecf-115">Your Skype for Business Server sites do not need to correspond to your Active Directory sites.</span></span>

<span data-ttu-id="44ecf-116">비즈니스용 Skype 서버는 고가용성 및 위치 요구 사항에 따라 확장할 수 있는 하나 이상의 사이트에 대한온-프레미스 배포를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="44ecf-116">Skype for Business Server supports on-premises deployment of one or more sites that can be scaled according to your high availability and location requirements.</span></span>

<span data-ttu-id="44ecf-117">배포에는 하나 이상의 중앙 사이트(데이터 센터라고도 합니다. 데이터 센터라고도 합니다.) 배포의 각 중앙 사이트에는 Standard Edition 서버 하나 또는 하나 이상의 Enterprise Edition 프런트 엔드 풀이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44ecf-117">Your deployment will have at least one central site (also called a datacenter, this is a datacenter for all the servers located in it), and each central site in your deployment will have one Standard Edition server, or at least one Enterprise Edition Front End pool.</span></span> <span data-ttu-id="44ecf-118">아래 각 옵션의 차이점을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44ecf-118">You can see the differences in each option below:</span></span>

- <span data-ttu-id="44ecf-119">Standard Edition 서버에는 Express 데이터베이스가 SQL Server 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44ecf-119">Standard Edition server includes a collocated SQL Server Express database.</span></span>

- <span data-ttu-id="44ecf-120">Enterprise Edition 프런트 엔드 풀에는 다음이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="44ecf-120">Enterprise Edition Front End pool includes:</span></span>

  - <span data-ttu-id="44ecf-121">하나 이상의 프런트 엔드 서버(확장성에 이상적으로 3개 이상), 최대 12대의 프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="44ecf-121">One or more Front End Servers (Ideally at least three, for scalability), with a maximum of twelve.</span></span> <span data-ttu-id="44ecf-122">부하 분산은 두 개 이상의 서버에 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="44ecf-122">Load-balancing would be required for more than one server.</span></span>

  - <span data-ttu-id="44ecf-123">별도의 백 엔드 서버.</span><span class="sxs-lookup"><span data-stu-id="44ecf-123">A separate Back End Server.</span></span>

<span data-ttu-id="44ecf-124">이 섹션의 나중에 다양한 서버 역할에 대해 자세히 알아보십시오.</span><span class="sxs-lookup"><span data-stu-id="44ecf-124">You can learn more about the various server roles a little later in this section.</span></span>

<span data-ttu-id="44ecf-125">중앙 사이트 외에 중앙 사이트와 연결된 분기 사이트가 하나 이상 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44ecf-125">In addition to your central sites, you may also end up having one or more branch sites associated with your central site.</span></span> <span data-ttu-id="44ecf-126">이러한 사이트는 거의 모든 기능에 대해 중앙 사이트에 종속되어 있으므로 정확히 어떤 기능으로 구성될까요?</span><span class="sxs-lookup"><span data-stu-id="44ecf-126">They depend on the central site for almost all their functionality, so what are they made up of, exactly?</span></span>

- <span data-ttu-id="44ecf-127">SSN(Survivable Branch Appliance) - PSTN(Public Switched Telephone Network) 게이트웨이와 일부 비즈니스용 Skype 서버 기능을 결합합니다.</span><span class="sxs-lookup"><span data-stu-id="44ecf-127">Survivable Branch Appliance, which combines a public switched telephone network (PSTN) gateway, with some Skype for Business Server functionality.</span></span>

- <span data-ttu-id="44ecf-128">SSS(Survivable Branch Server)는 비즈니스용 Skype 서버 등록자 및 중재 서버 소프트웨어가 설치된 Windows Server를 실행하는 서버입니다.</span><span class="sxs-lookup"><span data-stu-id="44ecf-128">Survivable Branch Server, it's a server running Windows Server that has Skype for Business Server Registrar and Mediation Server software installed.</span></span>

- <span data-ttu-id="44ecf-129">독립 실행형 PSTN 게이트웨이(Survivable Branch Appliance에 참여하지 않는 게이트웨이).</span><span class="sxs-lookup"><span data-stu-id="44ecf-129">Stand-alone PSTN gateway (which isn't part of the Survivable Branch Appliance).</span></span>

- <span data-ttu-id="44ecf-130">독립 실행형 중재 서버 또는 독립 실행형 중재 서버 풀(이 역할을 Survivable Branch Appliance와 함께 사용하려는 경우)</span><span class="sxs-lookup"><span data-stu-id="44ecf-130">Stand-alone Mediation Server or stand-alone Mediation Server pool (if you don't want to collocate this role with the Survivable Branch Appliance).</span></span>

## <a name="whats-in-a-skype-for-business-server-site"></a><span data-ttu-id="44ecf-131">비즈니스용 Skype 서버 사이트에는 무엇이 있나요?</span><span class="sxs-lookup"><span data-stu-id="44ecf-131">What's in a Skype for Business Server site?</span></span>

<span data-ttu-id="44ecf-132">좀 더 자세히 설명하기 위해 중앙 사이트에는 다음을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44ecf-132">To get into more detail, a central site can also have:</span></span>

- <span data-ttu-id="44ecf-133">동일한 도메인 또는 다른 도메인에 있는 여러 프런트 엔드 풀(풀의 백 엔드 서버와 함께 프런트 엔드 풀의 모든 프런트 엔드 서버가 동일한 도메인에 있을 수 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="44ecf-133">Multiple Front End pools, in the same domain or different domains (remember in planning that all the Front End Servers in a Front End pool, along with the Back End Servers for the pool, do have to be in the same domain).</span></span>

- <span data-ttu-id="44ecf-134">여러 Standard Edition 서버</span><span class="sxs-lookup"><span data-stu-id="44ecf-134">Multiple Standard Edition servers.</span></span>

- <span data-ttu-id="44ecf-135">Office Web Apps 서버 - 비즈니스용 Skype 서버의 Office Web Apps와 함께 PowerPoint 프레젠테이션을 공유하고 렌더링하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="44ecf-135">Office Web Apps Server, which is used with Office Web Apps in Skype for Business Server for sharing and rendering of PowerPoint presentations.</span></span>

- <span data-ttu-id="44ecf-136">경계 네트워크의 에지 서버 또는 에지 풀</span><span class="sxs-lookup"><span data-stu-id="44ecf-136">Edge Server or Edge pool (in a perimeter network).</span></span> <span data-ttu-id="44ecf-137">배포에서 페더타 파트너, 공용 IM 연결, XMPP(Extensible Messaging and Presence Protocol) 게이트웨이 및 원격 사용자 액세스를 지원하도록 하려는 경우 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="44ecf-137">Needed if you want your deployment to support federated partners, public IM connectivity, extensible messaging and presence protocol (XMPP) gateway, and remote user access.</span></span> <span data-ttu-id="44ecf-138">자세한 내용은 에지 서버 계획 설명서에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44ecf-138">More details can be found in the Edge Server Planning documentation.</span></span>

- <span data-ttu-id="44ecf-139">영구 채팅 서버.</span><span class="sxs-lookup"><span data-stu-id="44ecf-139">Persistent Chat Server.</span></span> <span data-ttu-id="44ecf-140">사용자가 시간이 지날 때 주제 기반의 여러 대화에 참여할 수 있도록 하려는 경우 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="44ecf-140">Useful if you want users to be able to take part in multiparty, topic-based conversations that persist over time.</span></span> <span data-ttu-id="44ecf-141">영구 채팅 서버 계획 항목에는 자세한 정보가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44ecf-141">There's more information at the Planning for Persistent Chat Server topic.</span></span>

- <span data-ttu-id="44ecf-142">모니터링.</span><span class="sxs-lookup"><span data-stu-id="44ecf-142">Monitoring.</span></span> <span data-ttu-id="44ecf-143">배포의 A/V(오디오/비디오) QoE(QoE) 및 CDR(통화 정보 기록)에 대한 데이터 수집을 지원하는 Enterprise Voice 및 A/V 회의에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="44ecf-143">Used to support data collection for audio/video (A/V) Quality of Experience (QoE) and call detail recording (CDR) for Enterprise Voice and A/V conferences in your deployment.</span></span> <span data-ttu-id="44ecf-144">모니터링 계획 항목에서 자세히 논의합니다.</span><span class="sxs-lookup"><span data-stu-id="44ecf-144">We discuss it in detail at the Planning for Monitoring topic.</span></span>

- <span data-ttu-id="44ecf-145">Director 또는 Director 풀.</span><span class="sxs-lookup"><span data-stu-id="44ecf-145">Director or Director pool.</span></span> <span data-ttu-id="44ecf-146">필수는 아니며, 사용자의 홈 풀로의 비즈니스용 Skype 사용자 요청 리디렉션을 사용하도록 설정하려는 경우 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="44ecf-146">Not required, but useful if you want to improve resiliency and enable redirection of Skype for Business user requests to the user's home pool.</span></span> <span data-ttu-id="44ecf-147">Director를 배포하려는 경우 풀당 최대 10개가 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="44ecf-147">If you want to deploy Directors, a maximum of 10 per pool is supported.</span></span> <span data-ttu-id="44ecf-148">필요한 경우 반드시 Director 계획 항목에서 계속 읽어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="44ecf-148">If this is something you need, definitely continue reading at the Planning for Directors topic.</span></span>

- <span data-ttu-id="44ecf-149">역방향 프록시.</span><span class="sxs-lookup"><span data-stu-id="44ecf-149">Reverse proxy.</span></span> <span data-ttu-id="44ecf-150">이 구성 요소는 비즈니스용 Skype 서버 구성 요소가 아니며, 페더링된 사용자에 대한 웹 콘텐츠 공유를 지원하려는 경우 모바일 트래픽을 지원하려는 경우 원격 사용자가 주소 책을 사용하고 모임에 참가하는 등 환경에서 이 기능을 사용하려는 경우 이 구성 요소를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44ecf-150">This isn't a Skype for Business Server component, but if you want to support the sharing of web content for federated users, if you intend to support Mobility traffic, if your remote users want to use the address book, join meetings, and so on, this is something you'll want to have in your environment.</span></span> <span data-ttu-id="44ecf-151">준비가 된 경우 자세한 내용을 확인할 수 있는 역방향 프록시 서버 설정 항목도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44ecf-151">There's a Setting up Reverse proxy server topic you can check out for more details, when you're ready.</span></span>

<span data-ttu-id="44ecf-152">이러한 서버의 설치에 대한 추가 정보는 아래에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44ecf-152">Additional information on collocation for these servers can be found below.</span></span>

<span data-ttu-id="44ecf-153">중앙 사이트에 배포된 모든 프런트 엔드 풀 및 Standard Edition 서버는 배포했다고 하여 다음을 공유합니다.</span><span class="sxs-lookup"><span data-stu-id="44ecf-153">All the Front End pools and Standard Edition servers deployed at your central site share the following, assuming you've deployed them:</span></span>

||||
|:-----|:-----|:-----|
|<span data-ttu-id="44ecf-154">디렉터 또는 디렉터 풀</span><span class="sxs-lookup"><span data-stu-id="44ecf-154">Director or Director pool</span></span>  <br/> |<span data-ttu-id="44ecf-155">독립 실행형 중재 서버 또는 중재 서버 풀</span><span class="sxs-lookup"><span data-stu-id="44ecf-155">Stand-alone Mediation Server or Mediation Server pool</span></span>  <br/> |<span data-ttu-id="44ecf-156">Office Web Apps 서버</span><span class="sxs-lookup"><span data-stu-id="44ecf-156">Office Web Apps Server</span></span>  <br/> |
|<span data-ttu-id="44ecf-157">에지 서버 또는 에지 풀</span><span class="sxs-lookup"><span data-stu-id="44ecf-157">Edge Server or Edge pool</span></span>  <br/> |<span data-ttu-id="44ecf-158">영구 채팅 서버 또는 영구 채팅 서버 풀</span><span class="sxs-lookup"><span data-stu-id="44ecf-158">Persistent Chat Server or Persistent Chat Server pool</span></span>  <br/> |<span data-ttu-id="44ecf-159">모니터링</span><span class="sxs-lookup"><span data-stu-id="44ecf-159">Monitoring</span></span>  <br/> |

<span data-ttu-id="44ecf-160">이 목록에서 Exchange UM(통합 메시징) 서버는 어디에 있나요?</span><span class="sxs-lookup"><span data-stu-id="44ecf-160">Where is Exchange Unified Messaging (UM) Server in this list?</span></span> <span data-ttu-id="44ecf-161">Exchange UM과 통합하려는 경우 비즈니스용 Skype 서버와 확실히 사용할 수 있지만 비즈니스용 Skype 서버 사이트의 구성 요소는 아니기 때문에 여기에서는 언급하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="44ecf-161">Well, you can certainly use it with Skype for Business Server if you want to integrate with Exchange UM, but it's not a component of the Skype for Business Server site, so we're not mentioning it here.</span></span>

<span data-ttu-id="44ecf-162">중앙 사이트가 여러 개인 경우 중앙 사이트에 배포된 경우 다음 서버 및 역할을 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44ecf-162">You may be planning to have multiple central site, and if that's so, they can share the following servers and roles, if they're deployed on your central site:</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="44ecf-163">독립 실행형 중재 서버 또는 중재 서버 풀</span><span class="sxs-lookup"><span data-stu-id="44ecf-163">Stand-alone Mediation Server or Mediation Server pool</span></span>  <br/> |<span data-ttu-id="44ecf-164">에지 서버 또는 에지 풀</span><span class="sxs-lookup"><span data-stu-id="44ecf-164">Edge Server or Edge pool</span></span>  <br/> |
|<span data-ttu-id="44ecf-165">영구 채팅 서버 또는 영구 채팅 서버 풀</span><span class="sxs-lookup"><span data-stu-id="44ecf-165">Persistent Chat Server or Persistent Chat Server pool</span></span>  <br/> |<span data-ttu-id="44ecf-166">모니터링</span><span class="sxs-lookup"><span data-stu-id="44ecf-166">Monitoring</span></span>  <br/> |

<span data-ttu-id="44ecf-167">마지막 목록과 마찬가지로 Exchange UM 서버는 비즈니스용 Skype 서버 배포에 속하지 않지만 여기서도 동일한 범주에 속하기 때문에 여기에 Exchange UM 서버를 포함하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="44ecf-167">Just like the last list, we aren't including the Exchange UM Server here because it's not part of the Skype for Business Server deployment, but it falls into the same category here, too.</span></span>

<span data-ttu-id="44ecf-168">물론 배포에 포함되는 몇 가지 다른 구성 요소와 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44ecf-168">There are some other components and options that go into deployments, of course.</span></span>

|||||
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="44ecf-169">방화벽</span><span class="sxs-lookup"><span data-stu-id="44ecf-169">Firewalls</span></span>  <br/> |<span data-ttu-id="44ecf-170">PSTN 게이트웨이(PSTN 게이트웨이를 배포하는 Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="44ecf-170">PSTN gateways (if you deploy Enterprise Voice</span></span>  <br/> |<span data-ttu-id="44ecf-171">Exchange UM Server(Exchange UM과 통합하려는 경우)</span><span class="sxs-lookup"><span data-stu-id="44ecf-171">Exchange UM Server (if you want to integrate with Exchange UM)</span></span>  <br/> |<span data-ttu-id="44ecf-172">DNS 부하 분산</span><span class="sxs-lookup"><span data-stu-id="44ecf-172">DNS load balancing</span></span>  <br/> |
|<span data-ttu-id="44ecf-173">하드웨어 부하 분산 장치</span><span class="sxs-lookup"><span data-stu-id="44ecf-173">Hardware load balancers</span></span>  <br/> |<span data-ttu-id="44ecf-174">SQL Server 데이터베이스</span><span class="sxs-lookup"><span data-stu-id="44ecf-174">SQL Server databases</span></span>  <br/> |<span data-ttu-id="44ecf-175">파일 공유</span><span class="sxs-lookup"><span data-stu-id="44ecf-175">File shares</span></span>  <br/> ||

## <a name="server-roles"></a><span data-ttu-id="44ecf-176">서버 역할</span><span class="sxs-lookup"><span data-stu-id="44ecf-176">Server roles</span></span>

<span data-ttu-id="44ecf-177">비즈니스용 Skype 서버를 실행하는 각 서버는 하나 이상의 서버 역할을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="44ecf-177">Each server running Skype for Business Server runs one or more server roles.</span></span> <span data-ttu-id="44ecf-178">서버 역할은 해당 서버에서 제공하는 정의된 비즈니스용 Skype 서버 기능 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="44ecf-178">A server role is a defined set of Skype for Business Server functionalities provided by that server.</span></span> <span data-ttu-id="44ecf-179">네트워크에서 사용 가능한 모든 서버 역할을 배포할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="44ecf-179">You don't need to deploy all available server roles in your network.</span></span> <span data-ttu-id="44ecf-180">필요한 기능이 포함된 서버 역할만 설치하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="44ecf-180">Install only the server roles that contain the functionality that you want.</span></span>

<span data-ttu-id="44ecf-181">대부분의 서버 역할은 확장성 및 고가용성을 위해 모두 같은 서버 역할을 실행하는 여러 서버 풀을 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44ecf-181">For most server roles, for scalability and high availability you can deploy pools of multiple servers all running the same server role.</span></span> <span data-ttu-id="44ecf-182">풀의 각 서버는 동일한 서버 역할을 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="44ecf-182">Each server in a pool must run an identical server role or roles.</span></span> <span data-ttu-id="44ecf-183">비즈니스용 Skype 서버의 대부분의 풀 유형의 경우 풀의 여러 서버 간에 트래픽을 분산하기 위해 부하 분산을 배포해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="44ecf-183">For most types of pools in Skype for Business Server, you must deploy a load balancer to spread traffic between the various servers in the pool.</span></span> <span data-ttu-id="44ecf-184">비즈니스용 Skype 서버는 DNS(Domain Name System) 부하 분산과 하드웨어 부하 분산을 모두 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="44ecf-184">Skype for Business Server supports both Domain Name System (DNS) load balancing and hardware load balancers.</span></span>

### <a name="front-end-server-and-back-end-server"></a><span data-ttu-id="44ecf-185">프런트 엔드 서버 및 백 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="44ecf-185">Front End Server and Back End Server</span></span>

<span data-ttu-id="44ecf-186">비즈니스용 Skype 서버 Enterprise Edition에서 프런트 엔드 서버는 핵심 서버 역할로, 여러 가지 기본 비즈니스용 Skype 서버 기능을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="44ecf-186">In Skype for Business Server Enterprise Edition, the Front End Server is the core server role, and runs many basic Skype for Business Server functions.</span></span> <span data-ttu-id="44ecf-187">프런트 엔드 서버는 백 엔드 서버와 함께 비즈니스용 Skype 서버 Enterprise Edition 배포에 필요한 유일한 서버 역할입니다.</span><span class="sxs-lookup"><span data-stu-id="44ecf-187">The Front End Server, along with the Back End Servers, are the only server roles required to be in any Skype for Business Server Enterprise Edition deployment.</span></span>

<span data-ttu-id="44ecf-188">프런트 엔드 풀은 동일하게 구성된 프런트 엔드 서버 집합으로서, 이러한 서버가 함께 일반 사용자 그룹에 대한 서비스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="44ecf-188">A Front End pool is a set of Front End Servers, configured identically, that work together to provide services for a common group of users.</span></span> <span data-ttu-id="44ecf-189">동일 역할을 실행하는 여러 서버로 구성된 풀은 확장성 및 장애 조치(Failover) 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="44ecf-189">A pool of multiple servers running the same role provides scalability and failover capability.</span></span>

<span data-ttu-id="44ecf-190">프런트 엔드 서버에는 다음과 같은 항목이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="44ecf-190">The Front End Server includes the following:</span></span>

- <span data-ttu-id="44ecf-191">사용자 인증 및 등록.</span><span class="sxs-lookup"><span data-stu-id="44ecf-191">User authentication and registration.</span></span>

- <span data-ttu-id="44ecf-192">현재 상태 정보 및 연락처 카드 교환.</span><span class="sxs-lookup"><span data-stu-id="44ecf-192">Presence information and contact card exchange.</span></span>

- <span data-ttu-id="44ecf-193">주소부 서비스 및 메일 목록 확장.</span><span class="sxs-lookup"><span data-stu-id="44ecf-193">Address book services and distribution list expansion.</span></span>

- <span data-ttu-id="44ecf-194">IM 기능(다중 사용자 IM 회의 포함)</span><span class="sxs-lookup"><span data-stu-id="44ecf-194">IM functionality, including multiparty IM conferences.</span></span>

- <span data-ttu-id="44ecf-195">웹 회의, PSTN 전화 접속 회의 및 A/V 회의(배포된 경우)</span><span class="sxs-lookup"><span data-stu-id="44ecf-195">Web conferencing, PSTN Dial-in conferencing and A/V conferencing (if deployed).</span></span>

- <span data-ttu-id="44ecf-196">비즈니스용 Skype 서버에 포함된 응용 프로그램(예: 회의 전화자 및 응답 그룹 응용 프로그램) 및 타사 응용 프로그램 모두에 대한 응용 프로그램 호스팅</span><span class="sxs-lookup"><span data-stu-id="44ecf-196">Application hosting, for both applications included with Skype for Business Server (for example, Conferencing Attendant and Response Group application), and third-party applications.</span></span>

- <span data-ttu-id="44ecf-197">CDR(통화 정보 기록) 및 CER(통화 오류 기록)의 형식으로 사용 정보를 수집하는 모니터링(선택 사항).</span><span class="sxs-lookup"><span data-stu-id="44ecf-197">Optionally, Monitoring, to collect usage information in the form of call detail records (CDRs) and call error records (CERs).</span></span> <span data-ttu-id="44ecf-198">이 정보는 통화 및 A/V 회의에 대해 네트워크를 트래버스하는 미디어(오디오 Enterprise Voice)의 품질에 대한 메트릭을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="44ecf-198">This information provides metrics about the quality of the media (audio and video) traversing your network for both Enterprise Voice calls and A/V conferences.</span></span>

- <span data-ttu-id="44ecf-199">웹 스케줄러 및 참가 시작 관리자와 같은 지원되는 웹 기반 작업에 대한 웹 구성 요소</span><span class="sxs-lookup"><span data-stu-id="44ecf-199">Web components to supported web-based tasks such as web scheduler and join launcher.</span></span>

- <span data-ttu-id="44ecf-200">준수 목적의 IM 통신 및 모임 콘텐츠에 대한 보관(선택 사항).</span><span class="sxs-lookup"><span data-stu-id="44ecf-200">Optionally, Archiving, to archive IM communications and meeting content for compliance reasons.</span></span> <span data-ttu-id="44ecf-201">자세한 내용은 계획 설명서에서 [Planning for Archiving](https://technet.microsoft.com/library/898b83c1-007b-43be-9484-08fe49c10951.aspx)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="44ecf-201">For details, see [Planning for Archiving](https://technet.microsoft.com/library/898b83c1-007b-43be-9484-08fe49c10951.aspx) in the Planning documentation.</span></span>

    <span data-ttu-id="44ecf-202">Lync Server 2010 및 이전 버전에서는 모니터링 및 보관이 별도의 서버 역할이 났지만 프런트 엔드 서버에는 함께 제공되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="44ecf-202">In Lync Server 2010 and prior versions, Monitoring and Archiving were separate server roles, not collocated on Front End Server.</span></span>

- <span data-ttu-id="44ecf-203">영구 채팅이 사용하도록 설정된 경우 채팅방 관리를 위한 영구 채팅 웹 서비스 및 파일 업로드/다운로드를 위한 영구 채팅 웹 서비스(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="44ecf-203">Optionally, if Persistent chat is enabled, Persistent Chat Web Services for Chat Room Management and Persistent Chat Web Services for File Upload/Download.</span></span>

<span data-ttu-id="44ecf-p120">프런트 엔드 풀은 사용자 및 회의 데이터의 기본 저장소로도 사용됩니다. 각 사용자에 대한 정보는 풀에 있는 3개의 프런트 엔드 서버 간에 복제되고 백 엔드 서버에서 백업됩니다.</span><span class="sxs-lookup"><span data-stu-id="44ecf-p120">Front End Pools are also the primary store for user and conference data. Information about each user is replicated among three Front End Servers in the pool, and backed up on the Back End Servers.</span></span>

<span data-ttu-id="44ecf-206">또한 배포의 한 프런트 엔드 서버가 중앙 관리 서버를 실행하여 비즈니스용 Skype 서버를 실행하는 모든 서버에 기본 구성 데이터를 관리하고 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="44ecf-206">Additionally, one Front End Server in the deployment also runs the Central Management Server, which manages and deploys basic configuration data to all servers running Skype for Business Server.</span></span> <span data-ttu-id="44ecf-207">또한 중앙 관리 서버는 Lync Server 관리 셸 및 파일 전송 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="44ecf-207">The Central Management Server also provides Lync Server Management Shell and file transfer capabilities.</span></span>

<span data-ttu-id="44ecf-208">백 엔드 서버는 프런트 엔드 풀에 Microsoft SQL Server 서비스를 제공하는 데이터베이스 서버를 실행하는 데이터베이스 서버입니다.</span><span class="sxs-lookup"><span data-stu-id="44ecf-208">The Back End Servers are database servers running Microsoft SQL Server that provide the database services for the Front End pool.</span></span> <span data-ttu-id="44ecf-209">백 엔드 서버는 풀의 사용자 및 회의 데이터에 대한 백업 저장소 역할을 하며 응답 그룹 데이터베이스와 같은 다른 데이터베이스에 대한 기본 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="44ecf-209">The Back End Servers serve as backup stores for the pool's user and conference data, and are the primary stores for other databases such as the Response Group database.</span></span> <span data-ttu-id="44ecf-210">단일 백 엔드 서버를 사용할 수 있지만, 비즈니스용 [Skype](../high-availability-and-disaster-recovery/back-end-server.md) 서버의 백 엔드 서버 고가용성은 장애 조치(failover)에 권장됩니다.</span><span class="sxs-lookup"><span data-stu-id="44ecf-210">You can have a single Back End Server, but [Back End Server high availability in Skype for Business Server](../high-availability-and-disaster-recovery/back-end-server.md) is recommended for failover.</span></span> <span data-ttu-id="44ecf-211">백 엔드 서버는 비즈니스용 Skype 서버 소프트웨어를 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="44ecf-211">Back End Servers do not run any Skype for Business Server software.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="44ecf-212">비즈니스용 Skype 서버 데이터베이스를 다른 데이터베이스와 함께 두지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="44ecf-212">We do not recommend collocating Skype for Business Server databases with other databases.</span></span> <span data-ttu-id="44ecf-213">그렇지 않으면 가용성 및 성능에 영향을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44ecf-213">If you do so, availability and performance may be affected.</span></span>

> [!NOTE]
> <span data-ttu-id="44ecf-214">SQL 미러링은 비즈니스용 Skype 서버에서 사용할 수 있지만 비즈니스용 Skype 서버 2019에서 더 이상 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="44ecf-214">SQL Mirroring is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="44ecf-215">AlwaysOn 가용성 그룹, AlwaysOn FCI(장애 조치(failover) 클러스터 인스턴스) 및 SQL 장애 조치(failover) 클러스터링 방법은 비즈니스용 Skype 서버 2019에서 선호됩니다.</span><span class="sxs-lookup"><span data-stu-id="44ecf-215">The  AlwaysOn Availability Groups, AlwaysOn Failover Cluster Instances (FCI), and SQL failover clustering methods are preferred with Skype for Business Server 2019.</span></span>

<span data-ttu-id="44ecf-216">백 엔드 서버 데이터베이스에 저장되는 정보에는 현재 상태 정보, 사용자의 대화 상대 목록, 모든 현재 전화 회의의 상태에 대한 영구 데이터를 비롯한 회의 데이터 및 전화 회의 일정 데이터가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="44ecf-216">Information stored in the Back End Server databases includes presence information, users' Contacts lists, conferencing data, including persistent data about the state of all current conferences, and conference scheduling data.</span></span>

### <a name="edge-server"></a><span data-ttu-id="44ecf-217">에지 서버</span><span class="sxs-lookup"><span data-stu-id="44ecf-217">Edge Server</span></span>

<span data-ttu-id="44ecf-218">에지 서버를 사용하면 사용자가 조직의 방화벽 외부에 있는 사용자와 통신하고 공동 작업을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44ecf-218">Edge Server enables your users to communicate and collaborate with users outside the organization's firewalls.</span></span> <span data-ttu-id="44ecf-219">이러한 외부 사용자에는 현재 오프사이트에서 작업 중인 조직의 사용자, 페더러티 파트너 조직의 사용자 및 비즈니스용 Skype 서버 배포에서 호스팅되는 회의에 참가할 수 있도록 초대된 외부 사용자가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="44ecf-219">These external users can include the organization's own users who are currently working offsite, users from federated partner organizations, and outside users who have been invited to join conferences hosted on your Skype for Business Server deployment.</span></span>

<span data-ttu-id="44ecf-220">에지 서버를 배포하면 모바일 장치에서 Lync 기능을 지원하는 모바일 서비스도 사용하도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="44ecf-220">Deploying Edge Server also enables mobility services, which supports Lync functionality on mobile devices.</span></span> <span data-ttu-id="44ecf-221">사용자는 지원된느 Apple iOS, Android, Windows Phone 또는 Nokia 모바일 장치를 사용해서 인스턴트 메시지 전송 및 수신, 연락처 보기 및 현재 상태 보기와 같은 활동을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44ecf-221">Users can use supported Apple iOS, Android, Windows Phone, or Nokia mobile devices to perform activities such as sending and receiving instant messages, viewing contacts, and viewing presence.</span></span> <span data-ttu-id="44ecf-222">또한 모바일 장치에서는 클릭하여 회의 참가, 회사번호로 전화, 단일 번호 연결, 음성 메일, 부재 중 통화 등의 일부 Enterprise Voice 기능도 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="44ecf-222">In addition, mobile devices support some Enterprise Voice features, such as click to join a conference, Call via Work, single number reach, voice mail, and missed calls.</span></span> <span data-ttu-id="44ecf-223">모바일 기능에는 또한 백그라운드에서 실행 중인 응용 프로그램을 지원하지 않는 모바일 장치를 위한 푸시 알림도 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="44ecf-223">The mobility feature also supports push notifications for mobile devices that do not support applications running in the background.</span></span> <span data-ttu-id="44ecf-224">푸시 알림은 해당 모바일 응용 프로그램이 비활성 상태일 때 발생한 이벤트에 대해 모바일 장치에 전송되는 알림입니다.</span><span class="sxs-lookup"><span data-stu-id="44ecf-224">A push notification is a notification that is sent to a mobile device about an event that occurs while a mobile application is inactive.</span></span>

<span data-ttu-id="44ecf-225">에지 서버에는 또한 프런트 엔드 서버에 포함된 XMPP 게이트웨이를 포함하는 완전히 통합된 XMPP(Extensible Messaging and Presence Protocol) 프록시가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="44ecf-225">Edge Servers also include a fully-integrated Extensible Messaging and Presence Protocol (XMPP) proxy, with an XMPP gateway included on Front End Servers.</span></span> <span data-ttu-id="44ecf-226">비즈니스용 Skype 서버 사용자가 인스턴트 메시징 및 현재 상태의 XMPP 기반 파트너의 연락처를 추가할 수 있도록 이러한 XMPP 구성 요소를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44ecf-226">You can configure these XMPP components to enable your Skype for Business Server users to add contacts from XMPP-based partners for instant messaging and presence.</span></span>

> [!NOTE]
> <span data-ttu-id="44ecf-227">XMPP 게이트웨이 및 XMPP 게이트웨이는 비즈니스용 Skype 서버 2015에서 사용할 수 있지만 비즈니스용 Skype 서버 2019에서 더 이상 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="44ecf-227">XMPP Gateways and proxies are available in Skype for Business Server 2015 but are no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="44ecf-228">자세한 [내용은 XMPP 페더링 마이그레이션을](../../../SfBServer2019/migration/migrating-xmpp-federation.md) 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="44ecf-228">See [Migrating XMPP federation](../../../SfBServer2019/migration/migrating-xmpp-federation.md) for more information.</span></span>

### <a name="mediation-server"></a><span data-ttu-id="44ecf-229">중재 서버</span><span class="sxs-lookup"><span data-stu-id="44ecf-229">Mediation Server</span></span>

<span data-ttu-id="44ecf-230">중재 서버는 Enterprise Voice, 직장 전화 및 전화 접속 회의를 구현하는 데 필요한 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="44ecf-230">Mediation Server is a necessary component for implementing Enterprise Voice, Call Via Work, and dial-in conferencing.</span></span> <span data-ttu-id="44ecf-231">중재 서버는 내부 비즈니스용 Skype 서버 인프라와 PSTN(Public Switched Telephone Network) 게이트웨이, IP-PBX 또는 SIP(Session Initiation Protocol) 트렁크 간의 신호 및 일부 구성의 미디어를 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="44ecf-231">Mediation Server translates signaling, and, in some configurations, media between your internal Skype for Business Server infrastructure and a public switched telephone network (PSTN) gateway, IP-PBX, or a Session Initiation Protocol (SIP) trunk.</span></span> <span data-ttu-id="44ecf-232">중재 서버는 프런트 엔드 서버와 동일한 서버에 함께 배치하여 실행하거나 독립 실행형 중재 서버 풀에 별도로 배치한 상태로 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44ecf-232">You can run Mediation Server collocated on the same server as Front End Server, or separated into a stand-alone Mediation Server pool.</span></span>

<span data-ttu-id="44ecf-233">자세한 내용은 비즈니스용 Skype 서버의 중재 서버 구성 요소를 [참조하세요.](../../plan-your-deployment/enterprise-voice-solution/mediation-server.md)</span><span class="sxs-lookup"><span data-stu-id="44ecf-233">For details, see [Mediation Server component in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/mediation-server.md).</span></span>

### <a name="video-interop-server"></a><span data-ttu-id="44ecf-234">비디오 Interop 서버</span><span class="sxs-lookup"><span data-stu-id="44ecf-234">Video Interop Server</span></span>

<span data-ttu-id="44ecf-235">Video Interop Server는 비즈니스용 Skype 서버 2015의 새로운 역할입니다.</span><span class="sxs-lookup"><span data-stu-id="44ecf-235">Video Interop Server is a new role as of Skype for Business Server 2015.</span></span> <span data-ttu-id="44ecf-236">비즈니스용 Skype 서버 배포를 특정 타사 VTC(Video Teleconferencing System) 솔루션과 통합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44ecf-236">It enables you to integrate your Skype for Business Server deployment with certain third-party VTC (Video Teleconferencing System) solutions.</span></span> <span data-ttu-id="44ecf-237">VIS는 제3자 전화 회의 시스템과 비즈니스용 Skype 서버 배포 간의 중간 역할을 합니다.</span><span class="sxs-lookup"><span data-stu-id="44ecf-237">A VIS acts as an intermediary between a 3rd party teleconference system and a Skype for Business Server deployment.</span></span> <span data-ttu-id="44ecf-238">이 릴리스의 경우 VIS는 Cisco/Tandberg 비디오 시스템과의 상호 운영에 중점을 두고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44ecf-238">For this release, VIS is focused on interoperability with Cisco/Tandberg video systems.</span></span>

<span data-ttu-id="44ecf-239">자세한 내용은 비즈니스용 [Skype 서버의 비디오 Interop 서버 계획(Plan for Video Interop Server)을 참조하세요.](../../plan-your-deployment/video-interop-server.md)</span><span class="sxs-lookup"><span data-stu-id="44ecf-239">For details, see [Plan for Video Interop Server in Skype for Business Server](../../plan-your-deployment/video-interop-server.md).</span></span>

### <a name="director"></a><span data-ttu-id="44ecf-240">이사</span><span class="sxs-lookup"><span data-stu-id="44ecf-240">Director</span></span>

<span data-ttu-id="44ecf-241">이사는 비즈니스용 Skype 서버 사용자 요청을 인증할 수 있지만 사용자 계정을 홈으로 두거나 현재 상태 또는 회의 서비스를 제공하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="44ecf-241">Directors can authenticate Skype for Business Server user requests, but they do not home user accounts or provide presence or conferencing services.</span></span> <span data-ttu-id="44ecf-242">디렉터는 외부 사용자 액세스를 지원하는 배포에서 보안을 효과적으로 향상시켜줍니다.</span><span class="sxs-lookup"><span data-stu-id="44ecf-242">Directors are most useful to enhance security in deployments that enable external user access.</span></span> <span data-ttu-id="44ecf-243">디렉터는 요청을 내부 서버로 전송하기 전에 요청에 대한 인증을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44ecf-243">The Director can authenticate requests before sending them on to internal servers.</span></span> <span data-ttu-id="44ecf-244">서비스 거부 공격이 있더라도 공격이 디렉터에서 끝나고 프런트 엔드 서버에 도달하지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="44ecf-244">In the case of a denial-of-service attack, the attack ends with the Director and does not reach the Front End servers.</span></span>

### <a name="persistent-chat-server-roles"></a><span data-ttu-id="44ecf-245">영구 채팅 서버 역할</span><span class="sxs-lookup"><span data-stu-id="44ecf-245">Persistent Chat Server Roles</span></span>

> [!NOTE]
> <span data-ttu-id="44ecf-246">영구 채팅은 비즈니스용 Skype 서버 2015에서 사용할 수 있지만 비즈니스용 Skype 서버 2019에서 더 이상 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="44ecf-246">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="44ecf-247">Teams에서 동일한 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44ecf-247">The same functionality is available in Teams.</span></span> <span data-ttu-id="44ecf-248">자세한 내용은 Microsoft Teams 업그레이드 시작을 [참조하세요.](/microsoftteams/upgrade-start-here)</span><span class="sxs-lookup"><span data-stu-id="44ecf-248">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="44ecf-249">영구 채팅을 사용하려면 이 기능이 필요한 사용자를 Teams로 마이그레이션하거나 비즈니스용 Skype 서버 2015를 계속 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44ecf-249">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span>

<span data-ttu-id="44ecf-p133">영구 채팅을 통해 사용자는 장기간 지속되는 주제 기반의 단체 대화에 참가할 수 있습니다. 영구 채팅 프런트 엔드 서버는 영구 채팅 서비스를 실행합니다. 영구 채팅 백 엔드 서버는 채팅 기록 데이터와 범주 및 채팅방에 대한 정보를 저장합니다. 영구 채팅 준수 백 엔드 서버(선택 사항)는 준수 목적으로 채팅 콘텐츠 및 준수 이벤트를 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44ecf-p133">Persistent chat enables users to participate in multiparty, topic-based conversations that persist over time. The Persistent Chat Front End Server runs the persistent chat service. The Persistent Chat Back End Server stores the chat history data, and information about categories and chat rooms. The optional Persistent Chat Compliance Back End Server can store the chat content and compliance events for the purpose of compliance.</span></span>

<span data-ttu-id="44ecf-254">비즈니스용 Skype 서버 Standard Edition을 실행하는 서버도 동일한 서버에 함께 있는 영구 채팅을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44ecf-254">Servers running Skype for Business Server Standard Edition can also run Persistent chat collocated on the same server.</span></span> <span data-ttu-id="44ecf-255">영구 채팅 프런트 엔드 서버를 Enterprise Edition 프런트 엔드 서버와 함께 함께 사용할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="44ecf-255">You cannot collocate the Persistent Chat Front End Server with Enterprise Edition Front End Server.</span></span>

<span data-ttu-id="44ecf-256">자세한 내용은 비즈니스용 Skype 서버 [2015의 영구 채팅 서버 계획(Plan for Persistent Chat Server)을 참조하세요.](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)</span><span class="sxs-lookup"><span data-stu-id="44ecf-256">For details, see [Plan for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md).</span></span>

## <a name="high-availability-and-disaster-recovery-support"></a><span data-ttu-id="44ecf-257">고가용성 및 재해 복구 지원</span><span class="sxs-lookup"><span data-stu-id="44ecf-257">High availability and disaster recovery support</span></span>

<span data-ttu-id="44ecf-258">비즈니스용 Skype 서버는 풀링을 통해 서버 중복성으로 고가용성을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="44ecf-258">Skype for Business Server provides high availability by server redundancy via pooling.</span></span> <span data-ttu-id="44ecf-259">특정 서버 역할을 실행하는 서버에서 오류가 발생하면 같은 역할을 실행하는 풀의 다른 서버가 해당 서버의 부하를 대신 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="44ecf-259">If a server running a certain server role fails, the other servers in the pool running the same role take the load of that server.</span></span> <span data-ttu-id="44ecf-260">이는 프런트 엔드 서버, 에지 서버, 중재 서버 및 디렉터에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="44ecf-260">This applies to Front End Servers, Edge Servers, Mediation Servers, and Directors.</span></span>

<span data-ttu-id="44ecf-261">비즈니스용 Skype 서버는 풀 페어링을 사용하도록 설정하여 재해 복구 조치도 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="44ecf-261">Skype for Business Server also provides disaster recovery measures by enabling pool pairing.</span></span> <span data-ttu-id="44ecf-262">이 토폴로지 배포 시 각 풀이 별도의 데이터 센터 및 별도의 지리적 영역에 있는 쌍으로 프런트 엔드 풀 쌍을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="44ecf-262">If you deploy this topology, you will designate pairs of Front End pools, with each pool in a pair located in a separate data center, and in a separate geographical area.</span></span> <span data-ttu-id="44ecf-263">한 풀 또는 사이트가 다운되는 경우 서비스 중단을 최소화하면서 해당 풀의 사용자가 쌍의 다른 풀을 사용하게 리디렉션할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44ecf-263">If one pool or site goes down, you can redirect the users of that pool to use the other pool in the pair, with minimal interruption of service.</span></span>

<span data-ttu-id="44ecf-264">비즈니스용 Skype 서버는 백 엔드 서버 고가용성을 위한 여러 옵션도 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="44ecf-264">Skype for Business Server also supports several options for Back End Server high availability.</span></span> <span data-ttu-id="44ecf-265">이러한 경계 및 제한은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="44ecf-265">These include the following:</span></span>

- <span data-ttu-id="44ecf-266">데이터베이스 미러링</span><span class="sxs-lookup"><span data-stu-id="44ecf-266">Database mirroring</span></span>

- <span data-ttu-id="44ecf-267">AlwaysOn 가용성 그룹</span><span class="sxs-lookup"><span data-stu-id="44ecf-267">AlwaysOn Availability Groups</span></span>

- <span data-ttu-id="44ecf-268">AlwaysOn FCI(장애 조치(Failover) 클러스터 인스턴스)</span><span class="sxs-lookup"><span data-stu-id="44ecf-268">AlwaysOn Failover Cluster Instances (FCI)</span></span>

- <span data-ttu-id="44ecf-269">SQL 클러스터링</span><span class="sxs-lookup"><span data-stu-id="44ecf-269">SQL failover clustering</span></span>

<span data-ttu-id="44ecf-270">풀 페어링 및 백 엔드 서버 고가용성에 대한 자세한 내용은 비즈니스용 Skype 서버의 고가용성 및 재해 복구 [계획을 참조하세요.](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)</span><span class="sxs-lookup"><span data-stu-id="44ecf-270">For details about pool pairing and Back End Server high availability, see [Plan for high availability and disaster recovery in Skype for Business Server](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span></span>

## <a name="server-collocation-in-skype-for-business-server"></a><span data-ttu-id="44ecf-271">비즈니스용 Skype 서버의 서버 함께 사용</span><span class="sxs-lookup"><span data-stu-id="44ecf-271">Server collocation in Skype for Business Server</span></span>

<span data-ttu-id="44ecf-272">용어를 이미 함께 사용했지만 이 용어는 무엇을 의미하나요?</span><span class="sxs-lookup"><span data-stu-id="44ecf-272">We've used the term collocate already, but what does this mean?</span></span> <span data-ttu-id="44ecf-273">비즈니스용 Skype 서버를 사용하면 동일한 서버(배치된 서버 또는 다른 서버)에서 일부 서버 역할 및 기능을 찾을 수 있지만 시작할 때와 Standard Edition 또는 Enterprise Edition 서버 배포를 수행하고 있는지(각각 자체 규칙과 함께 제공) 혼동될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44ecf-273">Skype for Business Server allows you to locate some server roles and features on the same server, which is collocation, or on different servers, but it can be confusing when you're starting out, and whether you're doing a Standard Edition or Enterprise Edition server deployment (they each come with their own rules).</span></span> <span data-ttu-id="44ecf-274">계획을 지원하기 위해 Standard Edition 서버 배포 및 Enterprise Edition 프런트 엔드 풀 배포에 서버 배치를 포함했습니다(대부분의 경우 이 정보는 동일하며 서로 다른 경우 특별히 호출).</span><span class="sxs-lookup"><span data-stu-id="44ecf-274">To help with your planning, we're including server collocation in Standard Edition server deployments and Enterprise Edition Front End pool deployments (in most cases this information is identical, and where it's different, it's called out specifically).</span></span>

### <a name="collocation-of-server-roles"></a><span data-ttu-id="44ecf-275">서버 역할의 함께 사용</span><span class="sxs-lookup"><span data-stu-id="44ecf-275">Collocation of server roles</span></span>

<span data-ttu-id="44ecf-276">Standard Edition 서버에는 다음과 같은 역할이 배치되어 있으며(추가 구성은 필요한 경우), Enterprise Edition 프런트 엔드 풀에서는 이 역할을 별도의 서버에 배치하거나 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44ecf-276">The Standard Edition server has the following role collocated (additional configuration is required though), while in the Enterprise Edition Front End pool, this role can be collocated, or deployed to a separate server:</span></span>

- <span data-ttu-id="44ecf-277">중재</span><span class="sxs-lookup"><span data-stu-id="44ecf-277">Mediation</span></span>

<span data-ttu-id="44ecf-278">이러한 서버 역할은 각각 별도의 서버에 배포해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="44ecf-278">These server roles must each be deployed on a separate server:</span></span>

- <span data-ttu-id="44ecf-279">이사</span><span class="sxs-lookup"><span data-stu-id="44ecf-279">Director</span></span>

- <span data-ttu-id="44ecf-280">Edge</span><span class="sxs-lookup"><span data-stu-id="44ecf-280">Edge</span></span>

- <span data-ttu-id="44ecf-281">비디오 Interop 서버</span><span class="sxs-lookup"><span data-stu-id="44ecf-281">Video Interop Server</span></span>

- <span data-ttu-id="44ecf-282">Office Web Apps</span><span class="sxs-lookup"><span data-stu-id="44ecf-282">Office Web Apps</span></span>

### <a name="databases"></a><span data-ttu-id="44ecf-283">데이터베이스</span><span class="sxs-lookup"><span data-stu-id="44ecf-283">Databases</span></span>

<span data-ttu-id="44ecf-284">Standard Edition 서버 배포와 Enterprise Edition 서버 풀 배포 간에 실제 차이점이 있는 영역으로, 아래 두 섹션과 두 가지에 대한 몇 가지 추가 규칙이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44ecf-284">This is the area with real differences between Standard Edition server deployments and Enterprise Edition server pool deployments, so we'll have two sections below, followed by some additional rules for both.</span></span>

#### <a name="standard"></a><span data-ttu-id="44ecf-285">Standard</span><span class="sxs-lookup"><span data-stu-id="44ecf-285">Standard</span></span>

<span data-ttu-id="44ecf-286">SQL Server Express는 Standard Edition 서버에 함께 함께 설치되어 있으며 이동할 수 없는 매우 간단합니다.</span><span class="sxs-lookup"><span data-stu-id="44ecf-286">Since SQL Server Express is collocated on the Standard Edition server, and can't be moved, this is pretty straightforward.</span></span> <span data-ttu-id="44ecf-287">또한 Standard Edition 서버에 영구 채팅 서버를 배포하는 경우 Standard Edition 서버에 영구 채팅 및 영구 채팅 준수 데이터베이스도 함께 배치할 수 있지만, 이렇게 하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="44ecf-287">Furthermore, if you deploy Persistent Chat Server on a Standard Edition server, you're also able to collocate the Persistent Chat and the Persistent Chat compliance database on the Standard Edition server too, but you don't have to.</span></span>

> [!NOTE]
> <span data-ttu-id="44ecf-288">영구 채팅은 비즈니스용 Skype 서버 2015에서 사용할 수 있지만 비즈니스용 Skype 서버 2019에서 더 이상 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="44ecf-288">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="44ecf-289">Teams에서 동일한 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44ecf-289">The same functionality is available in Teams.</span></span> <span data-ttu-id="44ecf-290">자세한 내용은 Microsoft Teams 업그레이드 시작을 [참조하세요.](/microsoftteams/upgrade-start-here)</span><span class="sxs-lookup"><span data-stu-id="44ecf-290">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="44ecf-291">영구 채팅을 사용하려면 이 기능이 필요한 사용자를 Teams로 마이그레이션하거나 비즈니스용 Skype 서버 2015를 계속 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44ecf-291">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span>

<span data-ttu-id="44ecf-292">Standard Edition 서버에는 이러한 서버를 함께 사용할 수 없지만 자체 데이터베이스 서버 하나에 함께 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44ecf-292">These can't be collocated on the Standard Edition server, but can go on a single database server of their own:</span></span>

- <span data-ttu-id="44ecf-293">모니터링 데이터베이스</span><span class="sxs-lookup"><span data-stu-id="44ecf-293">Monitoring database</span></span>

- <span data-ttu-id="44ecf-294">보관 데이터베이스</span><span class="sxs-lookup"><span data-stu-id="44ecf-294">Archiving database</span></span>

- <span data-ttu-id="44ecf-295">Enterprise Edition 프런트 엔드 풀의 모든 백 엔드 데이터베이스</span><span class="sxs-lookup"><span data-stu-id="44ecf-295">Any back-end database for an Enterprise Edition Front End pool</span></span>

#### <a name="enterprise"></a><span data-ttu-id="44ecf-296">Enterprise</span><span class="sxs-lookup"><span data-stu-id="44ecf-296">Enterprise</span></span>

<span data-ttu-id="44ecf-297">다음 데이터베이스는 동일한 백 엔드 에 함께 SQL Server.</span><span class="sxs-lookup"><span data-stu-id="44ecf-297">The following databases can be collocated on the same back end SQL Server:</span></span>

- <span data-ttu-id="44ecf-298">백 엔드 데이터베이스</span><span class="sxs-lookup"><span data-stu-id="44ecf-298">Back End database</span></span>

- <span data-ttu-id="44ecf-299">모니터링 데이터베이스</span><span class="sxs-lookup"><span data-stu-id="44ecf-299">Monitoring database</span></span>

- <span data-ttu-id="44ecf-300">보관 데이터베이스</span><span class="sxs-lookup"><span data-stu-id="44ecf-300">Archiving database</span></span>

- <span data-ttu-id="44ecf-301">영구 채팅 데이터베이스</span><span class="sxs-lookup"><span data-stu-id="44ecf-301">Persistent Chat database</span></span>

- <span data-ttu-id="44ecf-302">영구 채팅 준수 데이터베이스</span><span class="sxs-lookup"><span data-stu-id="44ecf-302">Persistent Chat compliance database</span></span>

#### <a name="both"></a><span data-ttu-id="44ecf-303">둘 다</span><span class="sxs-lookup"><span data-stu-id="44ecf-303">Both</span></span>

<span data-ttu-id="44ecf-304">이제 비즈니스용 Skype 서버 데이터베이스를 단일 SQL 인스턴스에 또는 동일한 SQL 데이터베이스의 여러 SQL 인스턴스에 함께 사용할 때 따라야 할 몇 가지 추가 규칙이 SQL Server 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44ecf-304">Now, there are some additional rules to follow when collocating Skype for Business Server databases in a single SQL instance, or in multiple SQL instances in the same SQL Server database:</span></span>

- <span data-ttu-id="44ecf-305">각 SQL 인스턴스에는 Enterprise Edition 프런트 엔드 풀에 대한 단일 백 엔드 데이터베이스, 단일 모니터링 데이터베이스, 단일 보관 데이터베이스, 단일 영구 채팅 데이터베이스 및 단일 영구 채팅 준수 데이터베이스만 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44ecf-305">Each SQL instance can only contain a single back end database for an Enterprise Edition Front End pool, a single Monitoring database, a single Archiving database, a single Persistent Chat database, and a single Persistent Chat compliance database.</span></span>

- <span data-ttu-id="44ecf-306">데이터베이스 서버는 두 개 이상의 Enterprise Edition 프런트 엔드 풀, 보관을 실행하는 서버 1개, 모니터링을 실행하는 서버 한 대, 영구 채팅 데이터베이스 하나 및 단일 영구 채팅 준수 데이터베이스를 지원할 수 없지만 데이터베이스가 동일한 SQL Server 인스턴스를 사용하는지 아니면 별도의 서버 인스턴스를 사용하는지 여부에 관계없이 각 데이터베이스에서 지원할 수 SQL Server.</span><span class="sxs-lookup"><span data-stu-id="44ecf-306">The database server can't support more than one Enterprise Edition Front End pool, one server running Archiving, one server running Monitoring, a single Persistent Chat database, and a single Persistent Chat compliance database, but it can support one of each, regardless of whether the databases use the same instance of SQL Server or separate instances of SQL Server.</span></span>

    > [!NOTE]
    > <span data-ttu-id="44ecf-307">영구 채팅은 비즈니스용 Skype 서버 2015에서 사용할 수 있지만 비즈니스용 Skype 서버 2019에서 더 이상 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="44ecf-307">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="44ecf-308">Teams에서 동일한 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44ecf-308">The same functionality is available in Teams.</span></span> <span data-ttu-id="44ecf-309">자세한 내용은 Microsoft Teams 업그레이드 시작을 [참조하세요.](/microsoftteams/upgrade-start-here)</span><span class="sxs-lookup"><span data-stu-id="44ecf-309">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="44ecf-310">영구 채팅을 사용하려면 이 기능이 필요한 사용자를 Teams로 마이그레이션하거나 비즈니스용 Skype 서버 2015를 계속 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44ecf-310">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span>

### <a name="file-shares"></a><span data-ttu-id="44ecf-311">파일 공유</span><span class="sxs-lookup"><span data-stu-id="44ecf-311">File shares</span></span>

<span data-ttu-id="44ecf-312">파일 공유는 별도의 서버에 있을 수도 있습니다. 또는 다음 중 한 가지 또는 전체와 동일한 서버에 함께 함께 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44ecf-312">The file share can be on a separate server, or you can collocate it on the same server as any or all of the following:</span></span>

- <span data-ttu-id="44ecf-313">Enterprise Edition 프런트 엔드 풀의 백 엔드 서버를 포함하는 데이터베이스 서버</span><span class="sxs-lookup"><span data-stu-id="44ecf-313">Database server, including the Back End Server of an Enterprise Edition Front End pool</span></span>

- <span data-ttu-id="44ecf-314">모니터링 데이터베이스</span><span class="sxs-lookup"><span data-stu-id="44ecf-314">Monitoring database</span></span>

- <span data-ttu-id="44ecf-315">보관 데이터베이스</span><span class="sxs-lookup"><span data-stu-id="44ecf-315">Archiving database</span></span>

- <span data-ttu-id="44ecf-316">영구 채팅 데이터베이스</span><span class="sxs-lookup"><span data-stu-id="44ecf-316">Persistent Chat database</span></span>

- <span data-ttu-id="44ecf-317">영구 채팅 준수 데이터베이스</span><span class="sxs-lookup"><span data-stu-id="44ecf-317">Persistent Chat compliance database</span></span>

> [!CAUTION]
> <span data-ttu-id="44ecf-318">이러한 서버에 파일 공유를 함께 사용할 수 있는 경우 권장되지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="44ecf-318">Note that while you can collocate the file share on these servers, it's vital to note that we don't recommend it.</span></span> <span data-ttu-id="44ecf-319">파일 공유를 다른 서버 역할과 함께 설치하는 경우 정기적으로 디스크 공간 및 성능 문제를 모니터링하고 있는지 확인하시기 바랍니다.</span><span class="sxs-lookup"><span data-stu-id="44ecf-319">If you're collocating the file share with any other server role, please make sure you're monitoring for disk space and performance issues on a regular basis.</span></span>

### <a name="keep-in-mind"></a><span data-ttu-id="44ecf-320">유의할 사항</span><span class="sxs-lookup"><span data-stu-id="44ecf-320">Keep in mind</span></span>

- <span data-ttu-id="44ecf-321">비즈니스용 Skype 서버 구성 요소가 아니며 토폴로지에는 없는 역방향 프록시 서버를 함께 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="44ecf-321">You can't collocate a reverse proxy server, which isn't a Skype for Business Server component, and may not even be in your topology.</span></span> <span data-ttu-id="44ecf-322">페더링 사용자에 대한 웹 콘텐츠 공유를 지원하려는 경우 특히, 역방향 프록시가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="44ecf-322">You'll need a reverse proxy if you want to support sharing of web content for federated users, among many other things.</span></span> <span data-ttu-id="44ecf-323">필요한 경우 다른 응용 프로그램에서 사용하고 있는 조직에 이미 있는 기존 역방향 프록시 서버를 구성하여 비즈니스용 Skype 서버에 대한 역방향 프록시 지원을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="44ecf-323">If you need to, go ahead and implement reverse proxy support for Skype for Business Server by configuring an existing reverse proxy server that's already in your organization that's being used by other applications.</span></span>

- <span data-ttu-id="44ecf-324">Exchange UM 구성 요소 또는 SharePoint Server 구성 요소를 비즈니스용 Skype 서버 역할과 함께 함께 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="44ecf-324">You can't collocate any Exchange UM component or SharePoint Server component with any Skype for Business Server role.</span></span>

## <a name="see-also"></a><span data-ttu-id="44ecf-325">참고 항목</span><span class="sxs-lookup"><span data-stu-id="44ecf-325">See also</span></span>

[<span data-ttu-id="44ecf-326">비즈니스용 Skype 서버에 대한 참조 토폴로지</span><span class="sxs-lookup"><span data-stu-id="44ecf-326">Reference topologies for Skype for Business Server</span></span>](reference-topologies.md)
