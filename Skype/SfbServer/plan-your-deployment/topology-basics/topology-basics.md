---
title: 비즈니스용 Skype 서버에 대 한 토폴로지 기본 사항
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 113e8c3f-71de-435c-bc4a-918ac7b50008
description: '요약: 비즈니스용 Skype 서버용 토폴로지를 선택 합니다. 비즈니스용 Skype 서버의 서버 위치에 대해 알아보세요.'
ms.openlocfilehash: 00154c754292fd960942f0f0da7f95bb6b5b1c19
ms.sourcegitcommit: da87a3c4c781223ab7de2fb539bb0796dc27ea9e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/23/2019
ms.locfileid: "36198006"
---
# <a name="topology-basics-for-skype-for-business-server"></a><span data-ttu-id="393d8-104">비즈니스용 Skype 서버에 대 한 토폴로지 기본 사항</span><span class="sxs-lookup"><span data-stu-id="393d8-104">Topology Basics for Skype for Business Server</span></span>

<span data-ttu-id="393d8-105">**요약:** 비즈니스용 Skype 서버에 대 한 토폴로지를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="393d8-105">**Summary:** Choose your topology for Skype for Business Server.</span></span> <span data-ttu-id="393d8-106">비즈니스용 Skype 서버의 서버 위치에 대해 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="393d8-106">Learn about server collocation for Skype for Business Server.</span></span>

<span data-ttu-id="393d8-107">다른 항목을 준비 하기 전에 비즈니스용 Skype Server 배포에 적합 한 토폴로지를 계획 하 고 있는지 알아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="393d8-107">Before preparing anything else, you'll want to know you're planning for the right topology for your deployment of Skype for Business Server.</span></span> <span data-ttu-id="393d8-108">가장 먼저 비즈니스용 Skype 서버에 대 한 온-프레미스 배포를 사용 하 고 있거나 하이브리드 배포에서이를 비즈니스용 Skype 서버 온라인 배포로 결합 하는 경우를 고려해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="393d8-108">The first thing you need to decide is if you're going to have an on-premises deployment of Skype for Business Server, or if you're going to combine this with a Skype for Business Server Online deployment in a Hybrid deployment.</span></span> <span data-ttu-id="393d8-109">어느 경우 든 여기에서 온-프레미스 토폴로지에 대해 자세히 설명 하지만 하이브리드 세부 정보는 자체 섹션에 설명 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="393d8-109">Either way, you're going to want to read further, as we'll detail the on-premises topologies here, but the Hybrid details are documented in their own section.</span></span>

<span data-ttu-id="393d8-110">[비즈니스용 Skype 서버용 참조 토폴로지에서](reference-topologies.md)몇 가지 예제 토폴로지를 볼 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="393d8-110">You can also see some example topologies in [Reference topologies for Skype for Business Server](reference-topologies.md).</span></span>

## <a name="sites"></a><span data-ttu-id="393d8-111">사이트</span><span class="sxs-lookup"><span data-stu-id="393d8-111">Sites</span></span>

<span data-ttu-id="393d8-112">비즈니스용 Skype 서버에서 비즈니스용 Skype 서버 구성 요소를 포함 하는 네트워크 사이트를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="393d8-112">In Skype for Business Server, you define sites on your network that contain Skype for Business Server components.</span></span> <span data-ttu-id="393d8-113">사이트는 단일 LAN 또는 고속 광섬유 네트워크로 연결 된 두 대의 네트워크와 같이 고속의 짧은 대기 네트워크로 연결 된 컴퓨터 집합입니다 .이 (가) 있습니다.</span><span class="sxs-lookup"><span data-stu-id="393d8-113">A site is a set of computers that is well-connected by a high-speed, low-latency network, such as a single local area network (LAN) or two networks connected by a high-speed fiber optic network.</span></span> <span data-ttu-id="393d8-114">비즈니스용 Skype 서버 사이트는 Active Directory 도메인 서비스 사이트 및 Microsoft Exchange Server 사이트와는 별개의 개념입니다.</span><span class="sxs-lookup"><span data-stu-id="393d8-114">Note that Skype for Business Server sites are a separate concept from Active Directory Domain Services sites and Microsoft Exchange Server sites.</span></span> <span data-ttu-id="393d8-115">비즈니스용 Skype 서버 사이트는 Active Directory 사이트와 일치할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="393d8-115">Your Skype for Business Server sites do not need to correspond to your Active Directory sites.</span></span>

<span data-ttu-id="393d8-116">비즈니스용 Skype 서버는 고가용성 및 위치 요구 사항에 따라 크기를 조정할 수 있는 하나 이상의 사이트에 대 한 온-프레미스 배포를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="393d8-116">Skype for Business Server supports on-premises deployment of one or more sites that can be scaled according to your high availability and location requirements.</span></span>

<span data-ttu-id="393d8-117">배포에는 적어도 하나 이상의 중앙 사이트 (데이터 센터 라고도 함)가 있으며, 배포의 각 중앙 사이트에는 표준 버전 서버나 하나 이상의 Enterprise Edition 프런트 엔드 풀이 하나 이상 있습니다.</span><span class="sxs-lookup"><span data-stu-id="393d8-117">Your deployment will have at least one central site (also called a datacenter, this is a datacenter for all the servers located in it), and each central site in your deployment will have one Standard Edition server, or at least one Enterprise Edition Front End pool.</span></span> <span data-ttu-id="393d8-118">아래 각 옵션의 차이점을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="393d8-118">You can see the differences in each option below:</span></span>

- <span data-ttu-id="393d8-119">스탠더드 버전 서버에는 collocated SQL Server Express 데이터베이스가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="393d8-119">Standard Edition server includes a collocated SQL Server Express database.</span></span>

- <span data-ttu-id="393d8-120">Enterprise Edition 프런트 엔드 풀에는 다음이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="393d8-120">Enterprise Edition Front End pool includes:</span></span>

  - <span data-ttu-id="393d8-121">하나 이상의 프런트 엔드 서버 (확장성에 가장 적합 한 3 개 이상), 최대 12 개.</span><span class="sxs-lookup"><span data-stu-id="393d8-121">One or more Front End Servers (Ideally at least three, for scalability), with a maximum of twelve.</span></span> <span data-ttu-id="393d8-122">로드 밸런싱는 여러 서버에 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="393d8-122">Load-balancing would be required for more than one server.</span></span>

  - <span data-ttu-id="393d8-123">별도의 백 엔드 서버.</span><span class="sxs-lookup"><span data-stu-id="393d8-123">A separate Back End Server.</span></span>

<span data-ttu-id="393d8-124">이 섹션의 뒷부분에서 다양 한 서버 역할에 대해 자세히 알아볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="393d8-124">You can learn more about the various server roles a little later in this section.</span></span>

<span data-ttu-id="393d8-125">중앙 사이트 외에도 중앙 사이트와 연결 된 하나 이상의 지점 사이트가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="393d8-125">In addition to your central sites, you may also end up having one or more branch sites associated with your central site.</span></span> <span data-ttu-id="393d8-126">이러한 기능은 대부분의 기능을 중앙 사이트에 따라 달라 지므로, 정확히 어떻게 구성 되는지는 무엇 인가요?</span><span class="sxs-lookup"><span data-stu-id="393d8-126">They depend on the central site for almost all their functionality, so what are they made up of, exactly?</span></span>

- <span data-ttu-id="393d8-127">Survivable 지사-PSTN (공개 교환 전화 네트워크) 게이트웨이를 비즈니스용 Skype 서버 기능과 결합 합니다.</span><span class="sxs-lookup"><span data-stu-id="393d8-127">Survivable Branch Appliance, which combines a public switched telephone network (PSTN) gateway, with some Skype for Business Server functionality.</span></span>

- <span data-ttu-id="393d8-128">Survivable Branch 서버는 비즈니스용 Skype Server 등록자와 중재 서버 소프트웨어를 설치 하는 Windows Server를 실행 하는 서버입니다.</span><span class="sxs-lookup"><span data-stu-id="393d8-128">Survivable Branch Server, it's a server running Windows Server that has Skype for Business Server Registrar and Mediation Server software installed.</span></span>

- <span data-ttu-id="393d8-129">독립형 PSTN 게이트웨이 (Survivable Branch 기기의 일부가 아님).</span><span class="sxs-lookup"><span data-stu-id="393d8-129">Stand-alone PSTN gateway (which isn't part of the Survivable Branch Appliance).</span></span>

- <span data-ttu-id="393d8-130">독립 실행형 중재 서버 또는 독립 실행형 중재 서버 풀 (Survivable Branch 기기를 사용 하 여이 역할을 collocate 하지 않으려는 경우)</span><span class="sxs-lookup"><span data-stu-id="393d8-130">Stand-alone Mediation Server or stand-alone Mediation Server pool (if you don't want to collocate this role with the Survivable Branch Appliance).</span></span>

## <a name="whats-in-a-skype-for-business-server-site"></a><span data-ttu-id="393d8-131">비즈니스용 Skype 서버 사이트에는 무엇이 있나요?</span><span class="sxs-lookup"><span data-stu-id="393d8-131">What's in a Skype for Business Server site?</span></span>

<span data-ttu-id="393d8-132">중앙 사이트에 대 한 자세한 내용을 보려면 다음을 수행 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="393d8-132">To get into more detail, a central site can also have:</span></span>

- <span data-ttu-id="393d8-133">여러 프런트 엔드 풀, 동일한 도메인 또는 다른 도메인에 설치 (프런트 엔드 풀의 모든 프런트 엔드 서버를 풀의 백 엔드 서버와 함께 사용 하는 것이 같은 도메인에 있어야 함)을 계획 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="393d8-133">Multiple Front End pools, in the same domain or different domains (remember in planning that all the Front End Servers in a Front End pool, along with the Back End Servers for the pool, do have to be in the same domain).</span></span>

- <span data-ttu-id="393d8-134">여러 스탠더드 버전 서버.</span><span class="sxs-lookup"><span data-stu-id="393d8-134">Multiple Standard Edition servers.</span></span>

- <span data-ttu-id="393d8-135">Office web Apps 서버-비즈니스용 Skype 서버의 Office Web Apps에서 PowerPoint 프레젠테이션 공유 및 렌더링을 위해 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="393d8-135">Office Web Apps Server, which is used with Office Web Apps in Skype for Business Server for sharing and rendering of PowerPoint presentations.</span></span>

- <span data-ttu-id="393d8-136">Edge 서버나 Edge 풀 (경계 네트워크)</span><span class="sxs-lookup"><span data-stu-id="393d8-136">Edge Server or Edge pool (in a perimeter network).</span></span> <span data-ttu-id="393d8-137">배포에 페더레이션 파트너, 공용 IM 연결, 확장할 수 있는 메시징 및 현재 상태 프로토콜 (XMPP) 게이트웨이 및 원격 사용자 액세스를 지원 하려는 경우 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="393d8-137">Needed if you want your deployment to support federated partners, public IM connectivity, extensible messaging and presence protocol (XMPP) gateway, and remote user access.</span></span> <span data-ttu-id="393d8-138">자세한 내용은 Edge 서버 계획 설명서에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="393d8-138">More details can be found in the Edge Server Planning documentation.</span></span>

- <span data-ttu-id="393d8-139">영구 채팅 서버.</span><span class="sxs-lookup"><span data-stu-id="393d8-139">Persistent Chat Server.</span></span> <span data-ttu-id="393d8-140">사용자가 시간에 따라 유지 되는 항목 기반 대화에 참여할 수 있도록 하려는 경우 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="393d8-140">Useful if you want users to be able to take part in multiparty, topic-based conversations that persist over time.</span></span> <span data-ttu-id="393d8-141">영구 채팅 서버 계획 항목에 대 한 자세한 내용은 다음을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="393d8-141">There's more information at the Planning for Persistent Chat Server topic.</span></span>

- <span data-ttu-id="393d8-142">모니터.</span><span class="sxs-lookup"><span data-stu-id="393d8-142">Monitoring.</span></span> <span data-ttu-id="393d8-143">배포에서 엔터프라이즈 음성과 A/V 회의에 대 한 오디오/비디오 (A/V)의 데이터 수집 (체감 품질) 및 CDR (통화 정보 기록)을 지 원하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="393d8-143">Used to support data collection for audio/video (A/V) Quality of Experience (QoE) and call detail recording (CDR) for Enterprise Voice and A/V conferences in your deployment.</span></span> <span data-ttu-id="393d8-144">모니터링 계획 항목에서 자세히 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="393d8-144">We discuss it in detail at the Planning for Monitoring topic.</span></span>

- <span data-ttu-id="393d8-145">이사 또는 감독 풀.</span><span class="sxs-lookup"><span data-stu-id="393d8-145">Director or Director pool.</span></span> <span data-ttu-id="393d8-146">필요 하지는 않지만 복원을 개선 하 고 비즈니스용 Skype 사용자 요청을 사용자의 홈 풀로 리디렉션하는 기능을 사용 하려는 경우 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="393d8-146">Not required, but useful if you want to improve resiliency and enable redirection of Skype for Business user requests to the user's home pool.</span></span> <span data-ttu-id="393d8-147">디렉터를 배포 하려는 경우 풀 당 최대 10 개를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="393d8-147">If you want to deploy Directors, a maximum of 10 per pool is supported.</span></span> <span data-ttu-id="393d8-148">이 내용이 필요한 경우 디렉터 계획 항목에서 계속 읽어 보세요.</span><span class="sxs-lookup"><span data-stu-id="393d8-148">If this is something you need, definitely continue reading at the Planning for Directors topic.</span></span>

- <span data-ttu-id="393d8-149">역방향 프록시.</span><span class="sxs-lookup"><span data-stu-id="393d8-149">Reverse proxy.</span></span> <span data-ttu-id="393d8-150">이는 비즈니스용 Skype 서버 구성 요소가 아니지만, 모바일 트래픽을 지원 하려는 경우에는 이동 통신을 지 원하는 경우 원격 사용자가 주소록을 사용 하 여 모임에 참가 하는 등의 작업을 수행 하는 것이 좋습니다. 환경에 포함 하려는 경우</span><span class="sxs-lookup"><span data-stu-id="393d8-150">This isn't a Skype for Business Server component, but if you want to support the sharing of web content for federated users, if you intend to support Mobility traffic, if your remote users want to use the address book, join meetings, and so on, this is something you'll want to have in your environment.</span></span> <span data-ttu-id="393d8-151">사용할 준비가 되 면 자세한 정보를 확인할 수 있는 리버스 프록시 서버 항목 설정이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="393d8-151">There's a Setting up Reverse proxy server topic you can check out for more details, when you're ready.</span></span>

<span data-ttu-id="393d8-152">이 서버의 collocation에 대 한 추가 정보는 아래에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="393d8-152">Additional information on collocation for these servers can be found below.</span></span>

<span data-ttu-id="393d8-153">중앙 사이트에 배포 된 모든 프런트 엔드 풀 및 Standard Edition 서버는 배포 되었다고 가정 하 여 다음을 공유 합니다.</span><span class="sxs-lookup"><span data-stu-id="393d8-153">All the Front End pools and Standard Edition servers deployed at your central site share the following, assuming you've deployed them:</span></span>

||||
|:-----|:-----|:-----|
|<span data-ttu-id="393d8-154">이사 또는 이사 은행</span><span class="sxs-lookup"><span data-stu-id="393d8-154">Director or Director pool</span></span>  <br/> |<span data-ttu-id="393d8-155">독립 실행형 중재 서버 또는 중재 서버 풀</span><span class="sxs-lookup"><span data-stu-id="393d8-155">Stand-alone Mediation Server or Mediation Server pool</span></span>  <br/> |<span data-ttu-id="393d8-156">Office Web Apps 서버</span><span class="sxs-lookup"><span data-stu-id="393d8-156">Office Web Apps Server</span></span>  <br/> |
|<span data-ttu-id="393d8-157">Edge 서버 또는 Edge 풀</span><span class="sxs-lookup"><span data-stu-id="393d8-157">Edge Server or Edge pool</span></span>  <br/> |<span data-ttu-id="393d8-158">영구 채팅 서버 또는 영구 채팅 서버 풀</span><span class="sxs-lookup"><span data-stu-id="393d8-158">Persistent Chat Server or Persistent Chat Server pool</span></span>  <br/> |<span data-ttu-id="393d8-159">모니터</span><span class="sxs-lookup"><span data-stu-id="393d8-159">Monitoring</span></span>  <br/> |

<span data-ttu-id="393d8-160">이 목록에 있는 Exchange UM (통합 메시징) 서버는 어디에 있나요?</span><span class="sxs-lookup"><span data-stu-id="393d8-160">Where is Exchange Unified Messaging (UM) Server in this list?</span></span> <span data-ttu-id="393d8-161">이것은 Exchange UM과 통합 하려는 경우 비즈니스용 Skype 서버에서 사용할 수 있지만, 비즈니스용 Skype Server 사이트의 구성 요소가 아닌 경우 여기에서 언급 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="393d8-161">Well, you can certainly use it with Skype for Business Server if you want to integrate with Exchange UM, but it's not a component of the Skype for Business Server site, so we're not mentioning it here.</span></span>

<span data-ttu-id="393d8-162">여러 중앙 사이트를 보유 하 고 있는 경우 중앙 사이트에서 배포 하는 경우 다음과 같은 서버와 역할을 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="393d8-162">You may be planning to have multiple central site, and if that's so, they can share the following servers and roles, if they're deployed on your central site:</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="393d8-163">독립 실행형 중재 서버 또는 중재 서버 풀</span><span class="sxs-lookup"><span data-stu-id="393d8-163">Stand-alone Mediation Server or Mediation Server pool</span></span>  <br/> |<span data-ttu-id="393d8-164">Edge 서버 또는 Edge 풀</span><span class="sxs-lookup"><span data-stu-id="393d8-164">Edge Server or Edge pool</span></span>  <br/> |
|<span data-ttu-id="393d8-165">영구 채팅 서버 또는 영구 채팅 서버 풀</span><span class="sxs-lookup"><span data-stu-id="393d8-165">Persistent Chat Server or Persistent Chat Server pool</span></span>  <br/> |<span data-ttu-id="393d8-166">모니터</span><span class="sxs-lookup"><span data-stu-id="393d8-166">Monitoring</span></span>  <br/> |

<span data-ttu-id="393d8-167">마지막 목록 처럼 여기에 Exchange UM 서버를 포함 하지 않는 이유는 비즈니스용 Skype Server 배포의 일부가 아니지만 여기에서 같은 범주로 나눌 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="393d8-167">Just like the last list, we aren't including the Exchange UM Server here because it's not part of the Skype for Business Server deployment, but it falls into the same category here, too.</span></span>

<span data-ttu-id="393d8-168">물론 몇 가지 다른 구성 요소와 옵션으로 배포를 진행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="393d8-168">There are some other components and options that go into deployments, of course.</span></span>

|||||
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="393d8-169">들</span><span class="sxs-lookup"><span data-stu-id="393d8-169">Firewalls</span></span>  <br/> |<span data-ttu-id="393d8-170">PSTN 게이트웨이 (Enterprise Voice를 배포 하는 경우)</span><span class="sxs-lookup"><span data-stu-id="393d8-170">PSTN gateways (if you deploy Enterprise Voice</span></span>  <br/> |<span data-ttu-id="393d8-171">Exchange UM 서버 (Exchange UM과 통합 하려는 경우)</span><span class="sxs-lookup"><span data-stu-id="393d8-171">Exchange UM Server (if you want to integrate with Exchange UM)</span></span>  <br/> |<span data-ttu-id="393d8-172">DNS 부하 분산</span><span class="sxs-lookup"><span data-stu-id="393d8-172">DNS load balancing</span></span>  <br/> |
|<span data-ttu-id="393d8-173">하드웨어 부하 분산 장치</span><span class="sxs-lookup"><span data-stu-id="393d8-173">Hardware load balancers</span></span>  <br/> |<span data-ttu-id="393d8-174">SQL Server 데이터베이스</span><span class="sxs-lookup"><span data-stu-id="393d8-174">SQL Server databases</span></span>  <br/> |<span data-ttu-id="393d8-175">파일 공유</span><span class="sxs-lookup"><span data-stu-id="393d8-175">File shares</span></span>  <br/> ||

## <a name="server-roles"></a><span data-ttu-id="393d8-176">서버 역할</span><span class="sxs-lookup"><span data-stu-id="393d8-176">Server roles</span></span>

<span data-ttu-id="393d8-177">비즈니스용 Skype Server를 실행 하는 각 서버는 하나 이상의 서버 역할을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="393d8-177">Each server running Skype for Business Server runs one or more server roles.</span></span> <span data-ttu-id="393d8-178">서버 역할은 해당 서버에서 제공 하는 비즈니스용 Skype 서버 기능의 정의 된 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="393d8-178">A server role is a defined set of Skype for Business Server functionalities provided by that server.</span></span> <span data-ttu-id="393d8-179">네트워크에서 사용 가능한 모든 서버 역할을 배포할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="393d8-179">You don't need to deploy all available server roles in your network.</span></span> <span data-ttu-id="393d8-180">원하는 기능이 포함 된 서버 역할만 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="393d8-180">Install only the server roles that contain the functionality that you want.</span></span>

<span data-ttu-id="393d8-181">대부분의 서버 역할에서 확장성 및 고가용성을 위해 동일한 서버 역할을 실행 하는 여러 서버의 풀을 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="393d8-181">For most server roles, for scalability and high availability you can deploy pools of multiple servers all running the same server role.</span></span> <span data-ttu-id="393d8-182">풀의 각 서버는 동일한 서버 역할 또는 역할을 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="393d8-182">Each server in a pool must run an identical server role or roles.</span></span> <span data-ttu-id="393d8-183">비즈니스용 Skype 서버에서 대부분의 풀 유형에 대해 부하 분산 장치를 배포 하 여 풀의 다양 한 서버 간에 트래픽을 분산 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="393d8-183">For most types of pools in Skype for Business Server, you must deploy a load balancer to spread traffic between the various servers in the pool.</span></span> <span data-ttu-id="393d8-184">비즈니스용 Skype 서버는 DNS (Domain Name System) 로드 균형 조정과 하드웨어 부하 분산 장치를 모두 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="393d8-184">Skype for Business Server supports both Domain Name System (DNS) load balancing and hardware load balancers.</span></span>

### <a name="front-end-server-and-back-end-server"></a><span data-ttu-id="393d8-185">프런트 엔드 서버 및 백 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="393d8-185">Front End Server and Back End Server</span></span>

<span data-ttu-id="393d8-186">비즈니스용 Skype Server Enterprise Edition에서 프런트 엔드 서버는 핵심 서버 역할을 하 고, 다양 한 비즈니스용 Skype 서버 기능을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="393d8-186">In Skype for Business Server Enterprise Edition, the Front End Server is the core server role, and runs many basic Skype for Business Server functions.</span></span> <span data-ttu-id="393d8-187">프런트 엔드 서버는 백 엔드 서버와 함께 비즈니스용 Skype Server Enterprise Edition 배포에 있어야 하는 유일한 서버 역할입니다.</span><span class="sxs-lookup"><span data-stu-id="393d8-187">The Front End Server, along with the Back End Servers, are the only server roles required to be in any Skype for Business Server Enterprise Edition deployment.</span></span>

<span data-ttu-id="393d8-188">프런트 엔드 풀은 동일 하 게 구성 된 프런트 엔드 서버 집합으로, 공통 사용자 그룹에 대 한 서비스를 제공 하기 위해 함께 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="393d8-188">A Front End pool is a set of Front End Servers, configured identically, that work together to provide services for a common group of users.</span></span> <span data-ttu-id="393d8-189">동일한 역할을 실행 하는 여러 서버의 풀은 확장성 및 장애 조치 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="393d8-189">A pool of multiple servers running the same role provides scalability and failover capability.</span></span>

<span data-ttu-id="393d8-190">프런트 엔드 서버에는 다음이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="393d8-190">The Front End Server includes the following:</span></span>

- <span data-ttu-id="393d8-191">사용자 인증 및 등록.</span><span class="sxs-lookup"><span data-stu-id="393d8-191">User authentication and registration.</span></span>

- <span data-ttu-id="393d8-192">현재 상태 정보 및 대화 상대 카드 교환.</span><span class="sxs-lookup"><span data-stu-id="393d8-192">Presence information and contact card exchange.</span></span>

- <span data-ttu-id="393d8-193">주소록 서비스 및 메일 그룹 확장</span><span class="sxs-lookup"><span data-stu-id="393d8-193">Address book services and distribution list expansion.</span></span>

- <span data-ttu-id="393d8-194">메신저 대화 회의를 비롯 한 IM 기능.</span><span class="sxs-lookup"><span data-stu-id="393d8-194">IM functionality, including multiparty IM conferences.</span></span>

- <span data-ttu-id="393d8-195">웹 회의, PSTN 전화 접속 회의 및 A/V 회의 (배포 된 경우)</span><span class="sxs-lookup"><span data-stu-id="393d8-195">Web conferencing, PSTN Dial-in conferencing and A/V conferencing (if deployed).</span></span>

- <span data-ttu-id="393d8-196">비즈니스용 Skype 서버에 포함 된 응용 프로그램 (예: 회의 수행자 및 응답 그룹 응용 프로그램)과 타사 응용 프로그램 호스팅</span><span class="sxs-lookup"><span data-stu-id="393d8-196">Application hosting, for both applications included with Skype for Business Server (for example, Conferencing Attendant and Response Group application), and third-party applications.</span></span>

- <span data-ttu-id="393d8-197">선택적으로 모니터링을 통해 CDRs (호출 정보 레코드)와 Cer (통화 오류 레코드) 형식으로 사용 정보를 수집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="393d8-197">Optionally, Monitoring, to collect usage information in the form of call detail records (CDRs) and call error records (CERs).</span></span> <span data-ttu-id="393d8-198">이 정보는 엔터프라이즈 음성 통화와 A/V 회의에 대 한 네트워크를 통과 하는 미디어 (오디오 및 비디오)의 품질에 대 한 메트릭을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="393d8-198">This information provides metrics about the quality of the media (audio and video) traversing your network for both Enterprise Voice calls and A/V conferences.</span></span>

- <span data-ttu-id="393d8-199">웹 구성 요소를 사용 하 여 web scheduler 및 join 시작 관리자와 같은 지원 되는 웹 기반 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="393d8-199">Web components to supported web-based tasks such as web scheduler and join launcher.</span></span>

- <span data-ttu-id="393d8-200">필요에 따라 보관할 수 있으며, 규정 준수를 위해 IM 통신 및 모임 콘텐츠를 보관 합니다.</span><span class="sxs-lookup"><span data-stu-id="393d8-200">Optionally, Archiving, to archive IM communications and meeting content for compliance reasons.</span></span> <span data-ttu-id="393d8-201">자세한 내용은 계획 설명서의 [보관 계획](https://technet.microsoft.com/library/898b83c1-007b-43be-9484-08fe49c10951.aspx) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="393d8-201">For details, see [Planning for Archiving](https://technet.microsoft.com/library/898b83c1-007b-43be-9484-08fe49c10951.aspx) in the Planning documentation.</span></span>

    <span data-ttu-id="393d8-202">Lync Server 2010 및 이전 버전에서 모니터링 및 보관은 프런트 엔드 서버에서 collocated 아닌 별도의 서버 역할 이었습니다.</span><span class="sxs-lookup"><span data-stu-id="393d8-202">In Lync Server 2010 and prior versions, Monitoring and Archiving were separate server roles, not collocated on Front End Server.</span></span>

- <span data-ttu-id="393d8-203">선택적으로 영구 채팅을 사용 하는 경우, 파일 업로드/다운로드에 대 한 채팅방 관리 및 영구 채팅 웹 서비스에 대 한 지속적인 채팅 웹 서비스.</span><span class="sxs-lookup"><span data-stu-id="393d8-203">Optionally, if Persistent chat is enabled, Persistent Chat Web Services for Chat Room Management and Persistent Chat Web Services for File Upload/Download.</span></span>

<span data-ttu-id="393d8-204">프런트 엔드 풀은 사용자 및 컨퍼런스 데이터에 대 한 기본 저장소 이기도 합니다.</span><span class="sxs-lookup"><span data-stu-id="393d8-204">Front End Pools are also the primary store for user and conference data.</span></span> <span data-ttu-id="393d8-205">각 사용자에 대 한 정보는 풀의 세 프런트 엔드 서버 간에 복제 되 고 백 엔드 서버에서 백업 됩니다.</span><span class="sxs-lookup"><span data-stu-id="393d8-205">Information about each user is replicated among three Front End Servers in the pool, and backed up on the Back End Servers.</span></span>

<span data-ttu-id="393d8-206">또한 배포의 한 프런트 엔드 서버는 비즈니스용 Skype Server를 실행 하는 모든 서버에 기본 구성 데이터를 관리 하 고 배포 하는 중앙 관리 서버를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="393d8-206">Additionally, one Front End Server in the deployment also runs the Central Management Server, which manages and deploys basic configuration data to all servers running Skype for Business Server.</span></span> <span data-ttu-id="393d8-207">중앙 관리 서버는 또한 Lync Server 관리 셸 및 파일 전송 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="393d8-207">The Central Management Server also provides Lync Server Management Shell and file transfer capabilities.</span></span>

<span data-ttu-id="393d8-208">백 엔드 서버는 프런트 엔드 풀에 대 한 데이터베이스 서비스를 제공 하는 Microsoft SQL Server를 실행 하는 데이터베이스 서버입니다.</span><span class="sxs-lookup"><span data-stu-id="393d8-208">The Back End Servers are database servers running Microsoft SQL Server that provide the database services for the Front End pool.</span></span> <span data-ttu-id="393d8-209">백 엔드 서버는 풀의 사용자 및 회의 데이터에 대 한 백업 저장소 역할을 하며 응답 그룹 데이터베이스와 같은 다른 데이터베이스의 주요 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="393d8-209">The Back End Servers serve as backup stores for the pool's user and conference data, and are the primary stores for other databases such as the Response Group database.</span></span> <span data-ttu-id="393d8-210">단일 백 엔드 서버를 사용할 수 있지만, [비즈니스용 Skype server에서 백 엔드 서버의 가용성이 높기](../high-availability-and-disaster-recovery/back-end-server.md) 때문에 장애 조치 (failover)를 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="393d8-210">You can have a single Back End Server, but [Back End Server high availability in Skype for Business Server](../high-availability-and-disaster-recovery/back-end-server.md) is recommended for failover.</span></span> <span data-ttu-id="393d8-211">백 엔드 서버는 비즈니스용 Skype 서버 소프트웨어를 실행 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="393d8-211">Back End Servers do not run any Skype for Business Server software.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="393d8-212">다른 데이터베이스와 함께 비즈니스용 Skype 서버 데이터베이스를 collocating 하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="393d8-212">We do not recommend collocating Skype for Business Server databases with other databases.</span></span> <span data-ttu-id="393d8-213">이렇게 하면 가용성과 성능이 영향을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="393d8-213">If you do so, availability and performance may be affected.</span></span>

> [!NOTE]
> <span data-ttu-id="393d8-214">SQL 미러링은 비즈니스용 Skype 서버 2015에서 사용할 수 있지만, 비즈니스용 Skype Server 2019에서는 더 이상 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="393d8-214">SQL Mirroring is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="393d8-215">AlwaysOn 가용성 그룹,이 어 장애 조치 (Failover) 클러스터 인스턴스 (FCI) 및 SQL 장애 조치 (failover) 클러스터링 방법은 비즈니스용 Skype 서버 2019에서 선호 됩니다.</span><span class="sxs-lookup"><span data-stu-id="393d8-215">The  AlwaysOn Availability Groups, AlwaysOn Failover Cluster Instances (FCI), and SQL failover clustering methods are preferred with Skype for Business Server 2019.</span></span>

<span data-ttu-id="393d8-216">백 엔드 서버 데이터베이스에 저장 되는 정보에는 현재 상태 정보, 사용자의 연락처 목록, 회의 데이터 (모든 최신 컨퍼런스 상태에 대 한 영구 데이터 포함), 컨퍼런스 일정 데이터 등이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="393d8-216">Information stored in the Back End Server databases includes presence information, users' Contacts lists, conferencing data, including persistent data about the state of all current conferences, and conference scheduling data.</span></span>

### <a name="edge-server"></a><span data-ttu-id="393d8-217">Edge 서버</span><span class="sxs-lookup"><span data-stu-id="393d8-217">Edge Server</span></span>

<span data-ttu-id="393d8-218">Edge Server를 통해 사용자는 조직의 방화벽 외부의 사용자와 통신 하 고 공동 작업할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="393d8-218">Edge Server enables your users to communicate and collaborate with users outside the organization's firewalls.</span></span> <span data-ttu-id="393d8-219">이러한 외부 사용자는 현재 오프 사이트를 사용 하 고 있는 조직의 고유한 사용자, 페더레이션 파트너 조직의 사용자, 비즈니스용 Skype 서버 배포에 호스트 된 회의에 참여 하도록 초대 받은 외부 사용자를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="393d8-219">These external users can include the organization's own users who are currently working offsite, users from federated partner organizations, and outside users who have been invited to join conferences hosted on your Skype for Business Server deployment.</span></span>

<span data-ttu-id="393d8-220">Edge Server를 배포 하면 모바일 장치에서 Lync 기능을 지 원하는 이동성 서비스도 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="393d8-220">Deploying Edge Server also enables mobility services, which supports Lync functionality on mobile devices.</span></span> <span data-ttu-id="393d8-221">사용자는 지원 되는 Apple iOS, Android, Windows Phone 또는 Nokia 모바일 장치를 사용 하 여 인스턴트 메시지 보내기 및 받기, 연락처 보기, 현재 상태 보기 등의 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="393d8-221">Users can use supported Apple iOS, Android, Windows Phone, or Nokia mobile devices to perform activities such as sending and receiving instant messages, viewing contacts, and viewing presence.</span></span> <span data-ttu-id="393d8-222">또한 모바일 장치는 클릭 하 여 회의에 참가 하 고, 회사, 단일 전화 접속, 음성 메일 및 부재 중 통화를 통해 전화를 걸 수 있는 몇 가지 엔터프라이즈 음성 기능을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="393d8-222">In addition, mobile devices support some Enterprise Voice features, such as click to join a conference, Call via Work, single number reach, voice mail, and missed calls.</span></span> <span data-ttu-id="393d8-223">또한 모바일 기능은 백그라운드에서 실행 되는 응용 프로그램을 지원 하지 않는 모바일 장치에 대 한 푸시 알림을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="393d8-223">The mobility feature also supports push notifications for mobile devices that do not support applications running in the background.</span></span> <span data-ttu-id="393d8-224">푸시 알림은 모바일 응용 프로그램이 비활성 상태일 때 발생 하는 이벤트에 대 한 모바일 장치에 전송 되는 알림입니다.</span><span class="sxs-lookup"><span data-stu-id="393d8-224">A push notification is a notification that is sent to a mobile device about an event that occurs while a mobile application is inactive.</span></span>

<span data-ttu-id="393d8-225">또한 Edge 서버에는 프런트 엔드 서버에 XMPP 게이트웨이를 포함 하는 완전 통합 된 확장 가능 메시지 및 현재 상태 프로토콜 (XMPP) 프록시가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="393d8-225">Edge Servers also include a fully-integrated Extensible Messaging and Presence Protocol (XMPP) proxy, with an XMPP gateway included on Front End Servers.</span></span> <span data-ttu-id="393d8-226">Skype for Business 서버 사용자가 인스턴트 메시지 및 현재 상태를 위해 XMPP 기반 파트너에서 연락처를 추가할 수 있도록 이러한 XMPP 구성 요소를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="393d8-226">You can configure these XMPP components to enable your Skype for Business Server users to add contacts from XMPP-based partners for instant messaging and presence.</span></span>

> [!NOTE]
> <span data-ttu-id="393d8-227">XMPP 게이트웨이 및 프록시는 비즈니스용 Skype 서버 2015에서 사용할 수 있지만, 비즈니스용 Skype Server 2019에서는 더 이상 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="393d8-227">XMPP Gateways and proxies are available in Skype for Business Server 2015 but are no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="393d8-228">자세한 내용은 [XMPP 페더레이션 마이그레이션을](../../../SfBServer2019/migration/migrating-xmpp-federation.md) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="393d8-228">See [Migrating XMPP federation](../../../SfBServer2019/migration/migrating-xmpp-federation.md) for more information.</span></span>

### <a name="mediation-server"></a><span data-ttu-id="393d8-229">중재 서버</span><span class="sxs-lookup"><span data-stu-id="393d8-229">Mediation Server</span></span>

<span data-ttu-id="393d8-230">중재 서버는 Enterprise Voice를 구현 하 고, 작업 및 전화 접속 회의를 통해 전화를 하는 데 필요한 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="393d8-230">Mediation Server is a necessary component for implementing Enterprise Voice, Call Via Work, and dial-in conferencing.</span></span> <span data-ttu-id="393d8-231">중재 서버는 신호를 번역 하 고, 일부 구성에서는 내부 Skype for Business Server 인프라와 PSTN (공개 교환 네트워크) 게이트웨이, IP-PBX 또는 SIP (세션 시작 프로토콜) 트렁크 간의 미디어를 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="393d8-231">Mediation Server translates signaling, and, in some configurations, media between your internal Skype for Business Server infrastructure and a public switched telephone network (PSTN) gateway, IP-PBX, or a Session Initiation Protocol (SIP) trunk.</span></span> <span data-ttu-id="393d8-232">프런트 엔드 서버와 동일한 서버에서 중재 서버 collocated을 실행 하거나 독립 실행형 중재 서버 풀로 분리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="393d8-232">You can run Mediation Server collocated on the same server as Front End Server, or separated into a stand-alone Mediation Server pool.</span></span>

<span data-ttu-id="393d8-233">자세한 내용은 [비즈니스용 Skype 서버에서 중재 서버 구성 요소](../../plan-your-deployment/enterprise-voice-solution/mediation-server.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="393d8-233">For details, see [Mediation Server component in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/mediation-server.md).</span></span>

### <a name="video-interop-server"></a><span data-ttu-id="393d8-234">비디오 Interop 서버</span><span class="sxs-lookup"><span data-stu-id="393d8-234">Video Interop Server</span></span>

<span data-ttu-id="393d8-235">비디오 Interop 서버는 비즈니스용 Skype 서버 2015의 새로운 역할입니다.</span><span class="sxs-lookup"><span data-stu-id="393d8-235">Video Interop Server is a new role as of Skype for Business Server 2015.</span></span> <span data-ttu-id="393d8-236">이를 통해 Skype for Business Server 배포를 특정 타사 VTC (비디오 Teleconferencing System) 솔루션과 통합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="393d8-236">It enables you to integrate your Skype for Business Server deployment with certain third-party VTC (Video Teleconferencing System) solutions.</span></span> <span data-ttu-id="393d8-237">VIS는 타사의 원격 회의 시스템 및 비즈니스용 Skype 서버 배포 간에 중개 역할을 합니다.</span><span class="sxs-lookup"><span data-stu-id="393d8-237">A VIS acts as an intermediary between a 3rd party teleconference system and a Skype for Business Server deployment.</span></span> <span data-ttu-id="393d8-238">이번 릴리스의 경우 VIS는 Cisco/Tandberg 영상 시스템과의 상호 운용성에 중점을 두었습니다.</span><span class="sxs-lookup"><span data-stu-id="393d8-238">For this release, VIS is focused on interoperability with Cisco/Tandberg video systems.</span></span>

<span data-ttu-id="393d8-239">자세한 내용은 비즈니스용 [Skype 서버에서 비디오 Interop 서버 계획](../../plan-your-deployment/video-interop-server.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="393d8-239">For details, see [Plan for Video Interop Server in Skype for Business Server](../../plan-your-deployment/video-interop-server.md).</span></span>

### <a name="director"></a><span data-ttu-id="393d8-240">Director</span><span class="sxs-lookup"><span data-stu-id="393d8-240">Director</span></span>

<span data-ttu-id="393d8-241">디렉터는 비즈니스용 Skype Server 사용자 요청을 인증할 수 있지만, 사용자 계정이 나 현재 상태 또는 회의 서비스는 제공 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="393d8-241">Directors can authenticate Skype for Business Server user requests, but they do not home user accounts or provide presence or conferencing services.</span></span> <span data-ttu-id="393d8-242">디렉터는 외부 사용자 액세스를 가능 하 게 하는 배포의 보안을 강화 하는 데 매우 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="393d8-242">Directors are most useful to enhance security in deployments that enable external user access.</span></span> <span data-ttu-id="393d8-243">디렉터는 내부 서버에 보내기 전에 요청을 인증할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="393d8-243">The Director can authenticate requests before sending them on to internal servers.</span></span> <span data-ttu-id="393d8-244">서비스 거부 공격을 하는 경우 공격이 디렉터로 종료 되 고 프런트 엔드 서버에 도달 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="393d8-244">In the case of a denial-of-service attack, the attack ends with the Director and does not reach the Front End servers.</span></span>

### <a name="persistent-chat-server-roles"></a><span data-ttu-id="393d8-245">영구 채팅 서버 역할</span><span class="sxs-lookup"><span data-stu-id="393d8-245">Persistent Chat Server Roles</span></span>

> [!NOTE]
> <span data-ttu-id="393d8-246">영구 채팅은 비즈니스용 Skype 서버 2015에서 사용할 수 있지만, 비즈니스용 Skype Server 2019에서는 더 이상 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="393d8-246">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="393d8-247">팀 에서도 동일한 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="393d8-247">The same functionality is available in Teams.</span></span> <span data-ttu-id="393d8-248">자세한 내용은 [Microsoft 팀 업그레이드 시작](/microsoftteams/upgrade-start-here)을 참고 하세요.</span><span class="sxs-lookup"><span data-stu-id="393d8-248">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="393d8-249">영구 채팅을 사용 해야 하는 경우에는이 기능이 필요한 사용자를 팀에 마이그레이션하거나 비즈니스용 Skype 서버 2015를 계속 사용 하는 것이 선택 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="393d8-249">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span>

<span data-ttu-id="393d8-250">영구 채팅을 통해 사용자는 시간에 따라 유지 되는 단체의 주제 기반 대화에 참여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="393d8-250">Persistent chat enables users to participate in multiparty, topic-based conversations that persist over time.</span></span> <span data-ttu-id="393d8-251">영구 채팅 프런트 엔드 서버는 영구 채팅 서비스를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="393d8-251">The Persistent Chat Front End Server runs the persistent chat service.</span></span> <span data-ttu-id="393d8-252">영구 채팅 백 엔드 서버에는 채팅 기록 데이터와 범주 및 채팅방에 대 한 정보가 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="393d8-252">The Persistent Chat Back End Server stores the chat history data, and information about categories and chat rooms.</span></span> <span data-ttu-id="393d8-253">선택적 영구 채팅 준수 백 엔드 서버는 준수 목적에 대 한 채팅 콘텐츠 및 준수 이벤트를 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="393d8-253">The optional Persistent Chat Compliance Back End Server can store the chat content and compliance events for the purpose of compliance.</span></span>

<span data-ttu-id="393d8-254">비즈니스용 Skype Server Standard Edition을 실행 하는 서버는 동일한 서버에서 영구 채팅 collocated를 실행할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="393d8-254">Servers running Skype for Business Server Standard Edition can also run Persistent chat collocated on the same server.</span></span> <span data-ttu-id="393d8-255">Enterprise Edition 프런트 엔드 서버를 사용 하는 경우 영구 채팅 프론트엔드 서버를 collocate 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="393d8-255">You cannot collocate the Persistent Chat Front End Server with Enterprise Edition Front End Server.</span></span>

<span data-ttu-id="393d8-256">자세한 내용은 비즈니스용 [Skype 서버 2015의 영구 채팅 서버 계획](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="393d8-256">For details, see [Plan for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md).</span></span>

## <a name="high-availability-and-disaster-recovery-support"></a><span data-ttu-id="393d8-257">고가용성 및 재해 복구 지원</span><span class="sxs-lookup"><span data-stu-id="393d8-257">High availability and disaster recovery support</span></span>

<span data-ttu-id="393d8-258">비즈니스용 Skype 서버는 풀링을 통해 서버 중복성으로 고가용성을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="393d8-258">Skype for Business Server provides high availability by server redundancy via pooling.</span></span> <span data-ttu-id="393d8-259">특정 서버 역할을 실행 하는 서버에 오류가 발생 하는 경우 동일한 역할을 실행 하는 풀의 다른 서버에서 해당 서버의 로드를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="393d8-259">If a server running a certain server role fails, the other servers in the pool running the same role take the load of that server.</span></span> <span data-ttu-id="393d8-260">이는 프런트 엔드 서버, Edge 서버, 중재 서버 및 디렉터에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="393d8-260">This applies to Front End Servers, Edge Servers, Mediation Servers, and Directors.</span></span>

<span data-ttu-id="393d8-261">또한 비즈니스용 Skype 서버는 풀 페어링을 사용 하도록 설정 하 여 재해 복구 조치를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="393d8-261">Skype for Business Server also provides disaster recovery measures by enabling pool pairing.</span></span> <span data-ttu-id="393d8-262">이 토폴로지를 배포 하는 경우 별도의 데이터 센터에 있는 쌍의 각 풀과 별도의 지역 영역에 프런트 엔드 풀 쌍을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="393d8-262">If you deploy this topology, you will designate pairs of Front End pools, with each pool in a pair located in a separate data center, and in a separate geographical area.</span></span> <span data-ttu-id="393d8-263">풀 또는 사이트의 작동이 중단 되 면 해당 풀의 사용자가 쌍의 다른 풀을 사용 하도록 리디렉션 하 여 서비스 중단을 최소화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="393d8-263">If one pool or site goes down, you can redirect the users of that pool to use the other pool in the pair, with minimal interruption of service.</span></span>

<span data-ttu-id="393d8-264">비즈니스용 Skype 서버는 또한 백 엔드 서버의 고가용성에 대 한 여러 옵션을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="393d8-264">Skype for Business Server also supports several options for Back End Server high availability.</span></span> <span data-ttu-id="393d8-265">여기에는 다음이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="393d8-265">These include the following:</span></span>

- <span data-ttu-id="393d8-266">데이터베이스 미러링</span><span class="sxs-lookup"><span data-stu-id="393d8-266">Database mirroring</span></span>

- <span data-ttu-id="393d8-267">AlwaysOn 가용성 그룹</span><span class="sxs-lookup"><span data-stu-id="393d8-267">AlwaysOn Availability Groups</span></span>

- <span data-ttu-id="393d8-268">FCI (Failover) 클러스터 인스턴스 (AlwaysOn)</span><span class="sxs-lookup"><span data-stu-id="393d8-268">AlwaysOn Failover Cluster Instances (FCI)</span></span>

- <span data-ttu-id="393d8-269">SQL 장애 조치 클러스터링</span><span class="sxs-lookup"><span data-stu-id="393d8-269">SQL failover clustering</span></span>

<span data-ttu-id="393d8-270">풀 페어링 및 백 엔드 서버 고가용성에 대 한 자세한 내용은 비즈니스용 [Skype 서버에서 고가용성 및 재해 복구 계획](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="393d8-270">For details about pool pairing and Back End Server high availability, see [Plan for high availability and disaster recovery in Skype for Business Server](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span></span>

## <a name="server-collocation-in-skype-for-business-server"></a><span data-ttu-id="393d8-271">비즈니스용 Skype 서버의 서버 collocation</span><span class="sxs-lookup"><span data-stu-id="393d8-271">Server collocation in Skype for Business Server</span></span>

<span data-ttu-id="393d8-272">Collocate 용어를 이미 사용 했지만,이는 무엇을 의미 하나요?</span><span class="sxs-lookup"><span data-stu-id="393d8-272">We've used the term collocate already, but what does this mean?</span></span> <span data-ttu-id="393d8-273">비즈니스용 Skype Server를 사용 하 여 동일한 서버에서 일부 서버 역할 및 기능을 찾을 수 있습니다 (예를 들어, 사용자의 위치나 다른 서버에서), 시작할 때 혼동을 받을 수 있지만 스탠더드 버전 또는 Enterprise Edition Server를 수행 중인지 여부 배포 (각 사용자 마다 고유한 규칙이 사용 됩니다.)</span><span class="sxs-lookup"><span data-stu-id="393d8-273">Skype for Business Server allows you to locate some server roles and features on the same server, which is collocation, or on different servers, but it can be confusing when you're starting out, and whether you're doing a Standard Edition or Enterprise Edition server deployment (they each come with their own rules).</span></span> <span data-ttu-id="393d8-274">계획 수립에 도움을 드릴 수 있도록 표준 버전 서버 배포 및 Enterprise Edition 프런트 엔드 풀 배포에 서버 위치를 포함 합니다 (대부분의 경우이 정보는 동일 하 고 다른 위치는 구체적으로 호출 됨).</span><span class="sxs-lookup"><span data-stu-id="393d8-274">To help with your planning, we're including server collocation in Standard Edition server deployments and Enterprise Edition Front End pool deployments (in most cases this information is identical, and where it's different, it's called out specifically).</span></span>

### <a name="collocation-of-server-roles"></a><span data-ttu-id="393d8-275">서버 역할의 콜론 위치</span><span class="sxs-lookup"><span data-stu-id="393d8-275">Collocation of server roles</span></span>

<span data-ttu-id="393d8-276">스탠더드 버전 서버에는 다음과 같은 역할 collocated (추가 구성이 필요 함) Enterprise Edition 프런트 엔드 풀에서이 역할을 collocated 하거나 별도의 서버에 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="393d8-276">The Standard Edition server has the following role collocated (additional configuration is required though), while in the Enterprise Edition Front End pool, this role can be collocated, or deployed to a separate server:</span></span>

- <span data-ttu-id="393d8-277">중재</span><span class="sxs-lookup"><span data-stu-id="393d8-277">Mediation</span></span>

<span data-ttu-id="393d8-278">이러한 서버 역할은 각각 별도의 서버에 배포 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="393d8-278">These server roles must each be deployed on a separate server:</span></span>

- <span data-ttu-id="393d8-279">Director</span><span class="sxs-lookup"><span data-stu-id="393d8-279">Director</span></span>

- <span data-ttu-id="393d8-280">쪽</span><span class="sxs-lookup"><span data-stu-id="393d8-280">Edge</span></span>

- <span data-ttu-id="393d8-281">비디오 Interop 서버</span><span class="sxs-lookup"><span data-stu-id="393d8-281">Video Interop Server</span></span>

- <span data-ttu-id="393d8-282">Office Web Apps</span><span class="sxs-lookup"><span data-stu-id="393d8-282">Office Web Apps</span></span>

### <a name="databases"></a><span data-ttu-id="393d8-283">Databases</span><span class="sxs-lookup"><span data-stu-id="393d8-283">Databases</span></span>

<span data-ttu-id="393d8-284">이 영역은 표준 버전 서버 배포와 엔터프라이즈 버전 서버 풀 배포 간의 실질적인 차이점을 포함 하 고 있으며, 두 개의 섹션을 포함 하 고 있으며, 두 가지 추가 규칙에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="393d8-284">This is the area with real differences between Standard Edition server deployments and Enterprise Edition server pool deployments, so we'll have two sections below, followed by some additional rules for both.</span></span>

#### <a name="standard"></a><span data-ttu-id="393d8-285">표준이</span><span class="sxs-lookup"><span data-stu-id="393d8-285">Standard</span></span>

<span data-ttu-id="393d8-286">SQL Server Express는 스탠더드 버전 서버에서 collocated 이동할 수 없으므로 매우 간단 합니다.</span><span class="sxs-lookup"><span data-stu-id="393d8-286">Since SQL Server Express is collocated on the Standard Edition server, and can't be moved, this is pretty straightforward.</span></span> <span data-ttu-id="393d8-287">또한 Standard Edition server에 영구 채팅 서버를 배포 하는 경우, 표준 버전 서버 에서도 영구 채팅 및 지속적인 채팅 준수 데이터베이스를 collocate 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="393d8-287">Furthermore, if you deploy Persistent Chat Server on a Standard Edition server, you're also able to collocate the Persistent Chat and the Persistent Chat compliance database on the Standard Edition server too, but you don't have to.</span></span>

> [!NOTE]
> <span data-ttu-id="393d8-288">영구 채팅은 비즈니스용 Skype 서버 2015에서 사용할 수 있지만, 비즈니스용 Skype Server 2019에서는 더 이상 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="393d8-288">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="393d8-289">팀 에서도 동일한 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="393d8-289">The same functionality is available in Teams.</span></span> <span data-ttu-id="393d8-290">자세한 내용은 [Microsoft 팀 업그레이드 시작](/microsoftteams/upgrade-start-here)을 참고 하세요.</span><span class="sxs-lookup"><span data-stu-id="393d8-290">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="393d8-291">영구 채팅을 사용 해야 하는 경우에는이 기능이 필요한 사용자를 팀에 마이그레이션하거나 비즈니스용 Skype 서버 2015를 계속 사용 하는 것이 선택 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="393d8-291">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span>

<span data-ttu-id="393d8-292">이는 스탠더드 버전 서버에서는 collocated 수 있지만, 다음과 같은 단일 데이터베이스 서버에 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="393d8-292">These can't be collocated on the Standard Edition server, but can go on a single database server of their own:</span></span>

- <span data-ttu-id="393d8-293">모니터링 데이터베이스</span><span class="sxs-lookup"><span data-stu-id="393d8-293">Monitoring database</span></span>

- <span data-ttu-id="393d8-294">보관 데이터베이스</span><span class="sxs-lookup"><span data-stu-id="393d8-294">Archiving database</span></span>

- <span data-ttu-id="393d8-295">Enterprise Edition 프런트 엔드 풀의 백 엔드 데이터베이스</span><span class="sxs-lookup"><span data-stu-id="393d8-295">Any back-end database for an Enterprise Edition Front End pool</span></span>

#### <a name="enterprise"></a><span data-ttu-id="393d8-296">Enterprise</span><span class="sxs-lookup"><span data-stu-id="393d8-296">Enterprise</span></span>

<span data-ttu-id="393d8-297">다음 데이터베이스는 동일한 백 엔드 SQL Server에서 collocated 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="393d8-297">The following databases can be collocated on the same back end SQL Server:</span></span>

- <span data-ttu-id="393d8-298">백 엔드 데이터베이스</span><span class="sxs-lookup"><span data-stu-id="393d8-298">Back End database</span></span>

- <span data-ttu-id="393d8-299">모니터링 데이터베이스</span><span class="sxs-lookup"><span data-stu-id="393d8-299">Monitoring database</span></span>

- <span data-ttu-id="393d8-300">보관 데이터베이스</span><span class="sxs-lookup"><span data-stu-id="393d8-300">Archiving database</span></span>

- <span data-ttu-id="393d8-301">영구 채팅 데이터베이스</span><span class="sxs-lookup"><span data-stu-id="393d8-301">Persistent Chat database</span></span>

- <span data-ttu-id="393d8-302">영구 채팅 준수 데이터베이스</span><span class="sxs-lookup"><span data-stu-id="393d8-302">Persistent Chat compliance database</span></span>

#### <a name="both"></a><span data-ttu-id="393d8-303">양방향</span><span class="sxs-lookup"><span data-stu-id="393d8-303">Both</span></span>

<span data-ttu-id="393d8-304">이제 단일 SQL 인스턴스의 비즈니스용 Skype 서버 데이터베이스를 collocating 하거나 같은 SQL Server 데이터베이스의 여러 SQL 인스턴스에서 다음 몇 가지 추가 규칙을 준수 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="393d8-304">Now, there are some additional rules to follow when collocating Skype for Business Server databases in a single SQL instance, or in multiple SQL instances in the same SQL Server database:</span></span>

- <span data-ttu-id="393d8-305">각 SQL 인스턴스에는 Enterprise Edition 프런트 엔드 풀, 단일 모니터링 데이터베이스, 단일 보관 데이터베이스, 단일 영구 채팅 데이터베이스 및 단일 영구 채팅 준수 데이터베이스에 대 한 단일 백 엔드 데이터베이스만 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="393d8-305">Each SQL instance can only contain a single back end database for an Enterprise Edition Front End pool, a single Monitoring database, a single Archiving database, a single Persistent Chat database, and a single Persistent Chat compliance database.</span></span>

- <span data-ttu-id="393d8-306">데이터베이스 서버는 두 개 이상의 Enterprise Edition 프런트 엔드 풀, 보관을 실행 하는 서버, 모니터링을 실행 하는 서버 1 개, 단일 영구 채팅 데이터베이스, 단일 영구 채팅 준수 데이터베이스 등을 지원할 수 있지만, 각각의 기능 중 하나가 지원 됩니다. 데이터베이스에서 SQL Server의 동일한 인스턴스를 사용 하는지 아니면 SQL Server의 인스턴스가 서로 다른 지에 관계 없이</span><span class="sxs-lookup"><span data-stu-id="393d8-306">The database server can't support more than one Enterprise Edition Front End pool, one server running Archiving, one server running Monitoring, a single Persistent Chat database, and a single Persistent Chat compliance database, but it can support one of each, regardless of whether the databases use the same instance of SQL Server or separate instances of SQL Server.</span></span>

    > [!NOTE]
    > <span data-ttu-id="393d8-307">영구 채팅은 비즈니스용 Skype 서버 2015에서 사용할 수 있지만, 비즈니스용 Skype Server 2019에서는 더 이상 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="393d8-307">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="393d8-308">팀 에서도 동일한 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="393d8-308">The same functionality is available in Teams.</span></span> <span data-ttu-id="393d8-309">자세한 내용은 [Microsoft 팀 업그레이드 시작](/microsoftteams/upgrade-start-here)을 참고 하세요.</span><span class="sxs-lookup"><span data-stu-id="393d8-309">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="393d8-310">영구 채팅을 사용 해야 하는 경우에는이 기능이 필요한 사용자를 팀에 마이그레이션하거나 비즈니스용 Skype 서버 2015를 계속 사용 하는 것이 선택 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="393d8-310">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span>

### <a name="file-shares"></a><span data-ttu-id="393d8-311">파일 공유</span><span class="sxs-lookup"><span data-stu-id="393d8-311">File shares</span></span>

<span data-ttu-id="393d8-312">파일 공유는 별도의 서버에 있을 수도 있고 다음 중 하나 또는 모두와 동일한 서버에서 collocate 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="393d8-312">The file share can be on a separate server, or you can collocate it on the same server as any or all of the following:</span></span>

- <span data-ttu-id="393d8-313">엔터프라이즈 에디션 프런트 엔드 풀의 백 엔드 서버를 포함 하는 데이터베이스 서버</span><span class="sxs-lookup"><span data-stu-id="393d8-313">Database server, including the Back End Server of an Enterprise Edition Front End pool</span></span>

- <span data-ttu-id="393d8-314">모니터링 데이터베이스</span><span class="sxs-lookup"><span data-stu-id="393d8-314">Monitoring database</span></span>

- <span data-ttu-id="393d8-315">보관 데이터베이스</span><span class="sxs-lookup"><span data-stu-id="393d8-315">Archiving database</span></span>

- <span data-ttu-id="393d8-316">영구 채팅 데이터베이스</span><span class="sxs-lookup"><span data-stu-id="393d8-316">Persistent Chat database</span></span>

- <span data-ttu-id="393d8-317">영구 채팅 준수 데이터베이스</span><span class="sxs-lookup"><span data-stu-id="393d8-317">Persistent Chat compliance database</span></span>

> [!CAUTION]
> <span data-ttu-id="393d8-318">이러한 서버에서 파일 공유를 collocate 수 있지만,이를 추천 하지 않는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="393d8-318">Note that while you can collocate the file share on these servers, it's vital to note that we don't recommend it.</span></span> <span data-ttu-id="393d8-319">다른 서버 역할을 사용 하 여 파일 공유를 collocating 하는 경우 정기적으로 디스크 공간 및 성능 문제를 모니터링 하 고 있는지 확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="393d8-319">If you're collocating the file share with any other server role, please make sure you're monitoring for disk space and performance issues on a regular basis.</span></span>

### <a name="keep-in-mind"></a><span data-ttu-id="393d8-320">기억 하기</span><span class="sxs-lookup"><span data-stu-id="393d8-320">Keep in mind</span></span>

- <span data-ttu-id="393d8-321">Skype for Business Server 구성 요소가 아닌 역 프록시 서버는 collocate 수 없으며, 토폴로지에도 해당 되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="393d8-321">You can't collocate a reverse proxy server, which isn't a Skype for Business Server component, and may not even be in your topology.</span></span> <span data-ttu-id="393d8-322">다른 많은 작업 중에 페더레이션 사용자의 웹 콘텐츠 공유를 지원 하려면 리버스 프록시가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="393d8-322">You'll need a reverse proxy if you want to support sharing of web content for federated users, among many other things.</span></span> <span data-ttu-id="393d8-323">필요한 경우 다른 응용 프로그램에서 사용 중인 조직에 이미 있는 기존 역방향 프록시 서버를 구성 하 여 비즈니스용 Skype 서버에 대 한 리버스 프록시 지원을 구현 하세요.</span><span class="sxs-lookup"><span data-stu-id="393d8-323">If you need to, go ahead and implement reverse proxy support for Skype for Business Server by configuring an existing reverse proxy server that's already in your organization that's being used by other applications.</span></span>

- <span data-ttu-id="393d8-324">비즈니스용 Skype 서버 역할을 사용 하 여 Exchange UM 구성 요소 또는 SharePoint Server 구성 요소를 collocate 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="393d8-324">You can't collocate any Exchange UM component or SharePoint Server component with any Skype for Business Server role.</span></span>

## <a name="see-also"></a><span data-ttu-id="393d8-325">참고 항목</span><span class="sxs-lookup"><span data-stu-id="393d8-325">See also</span></span>

[<span data-ttu-id="393d8-326">비즈니스용 Skype 서버에 대 한 참조 토폴로지</span><span class="sxs-lookup"><span data-stu-id="393d8-326">Reference topologies for Skype for Business Server</span></span>](reference-topologies.md)
