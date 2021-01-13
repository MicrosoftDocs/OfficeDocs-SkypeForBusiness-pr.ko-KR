---
title: 비즈니스용 Skype 서버에서 인스턴트 메시징 및 현재 상태 계획
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
ms.assetid: 70d2151e-9382-485d-ab14-758597571a74
description: '요약: 비즈니스용 Skype 서버에서 인스턴트 메시징 및 현재 상태 계획을 세우는 방법을 설명하는 정보를 제공합니다.'
ms.openlocfilehash: a29d68cc66e0ac4a70fc759283646fc3ce49cdf5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816278"
---
# <a name="plan-for-instant-messaging-and-presence-in-skype-for-business-server"></a><span data-ttu-id="beb92-103">비즈니스용 Skype 서버에서 인스턴트 메시징 및 현재 상태 계획</span><span class="sxs-lookup"><span data-stu-id="beb92-103">Plan for instant messaging and presence in Skype for Business Server</span></span>
 
<span data-ttu-id="beb92-104">**요약:** 비즈니스용 Skype 서버에서 인스턴트 메시징 및 현재 상태 계획을 세우는 방법을 배워야 합니다.</span><span class="sxs-lookup"><span data-stu-id="beb92-104">**Summary:** Learn how to plan for instant messaging and presence in Skype for Business Server.</span></span>
  
<span data-ttu-id="beb92-105">비즈니스용 Skype 서버에서 인스턴트 메시징 및 현재 상태 계획</span><span class="sxs-lookup"><span data-stu-id="beb92-105">Plan for instant messaging and presence in Skype for Business Server.</span></span> <span data-ttu-id="beb92-106">IM(오프라인 인스턴트 메시징) 사용 또는 사용 안 하도록 설정과 같은 특정 배포 옵션에 대한 자세한 내용은 비즈니스용 Skype 서버에서 인스턴트 메시징 및 현재 상태 [배포를 참조하세요.](../deploy/im-and-presence/im-and-presence.md)</span><span class="sxs-lookup"><span data-stu-id="beb92-106">To learn about specific deployment options, such as enabling or disabling Offline Instant Messaging (IM), see [Deploy instant messaging and presence in Skype for Business Server](../deploy/im-and-presence/im-and-presence.md).</span></span>
  
## <a name="plan-for-instant-messaging-and-presence-in-skype-for-business-server"></a><span data-ttu-id="beb92-107">비즈니스용 Skype 서버에서 인스턴트 메시징 및 현재 상태 계획</span><span class="sxs-lookup"><span data-stu-id="beb92-107">Plan for instant messaging and presence in Skype for Business Server</span></span>

<span data-ttu-id="beb92-108">프런트 엔드 서버는 IM(인스턴트 메시징) 및 현재 상태와 같은 핵심 비즈니스용 Skype 서버 기능을 제공하고 모든 비즈니스용 Skype 서버 배포에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="beb92-108">Front End Servers provide core Skype for Business Server functionality such as instant messaging (IM) and presence and are included in every Skype for Business Server deployment.</span></span> <span data-ttu-id="beb92-109">사용할 수 있는 두 가지 버전은 주로 대규모 조직을 위해 설계된 비즈니스용 Skype 서버 Enterprise Edition과 전체 고가용성 옵션이 필요하지 않은 소규모 하드웨어 투자를 원하는 소규모 조직을 위해 설계된 비즈니스용 Skype 서버 Standard Edition입니다.</span><span class="sxs-lookup"><span data-stu-id="beb92-109">There are two editions available: Skype for Business Server Enterprise Edition, which is designed primarily for larger organizations, and Skype for Business Server Standard Edition, which is designed primarily for smaller organizations which want a smaller hardware investment and do not require full high availability options.</span></span> <span data-ttu-id="beb92-110">두 버전 모두 IM, 현재 상태, 회의 및 회의를 비롯한 모든 비즈니스용 Skype 서버 작업을 Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="beb92-110">Both editions support all Skype for Business Server workloads including IM, presence, conferencing, and Enterprise Voice.</span></span>
  
<span data-ttu-id="beb92-p103">IM(인스턴트 메시징)은 사용자가 텍스트 기반 메시지를 사용하여 컴퓨터에서 실시간으로 다른 사용자와 통신할 수 있도록 합니다. 양방향 및 단체 IM 세션이 모두 지원됩니다. 양방향 IM 대화의 참가자는 언제든지 대화에 세 번째 참가자를 추가할 수 있습니다. 이 경우 대화 창이 회의 기능을 지원하도록 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="beb92-p103">Instant messaging (IM) enables your users to communicate with each other in real time on their computers using text-based messages. Both two-party and multiparty IM sessions are supported. A participant in a two-party IM conversation can add a third participant to the conversation at any time. When this happens, the Conversation window changes to support conferencing features.</span></span>
  
<span data-ttu-id="beb92-115">현재 상태는 네트워크의 다른 사용자 상태에 대한 정보를 사용자에게 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="beb92-115">Presence provides information to users about the status of others on the network.</span></span> <span data-ttu-id="beb92-116">사용자의 현재 상태는 다른 사용자가 사용자에게 연락할지 여부와 메신저, 전화 또는 전자 메일을 사용할지 여부를 결정하는 데 도움이 되는 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="beb92-116">A user's presence status provides information to help others decide whether they should try to contact the user and whether to use instant messaging, phone, or email.</span></span> <span data-ttu-id="beb92-117">현재 상태는 가능한 경우 인스턴트 통신을 촉진하는 동시에, 사용자가 회의 중인지 또는 부재 중인지에 대한 정보를 제공하여 인스턴트 통신을 사용할 수 없다는 것도 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="beb92-117">Presence encourages instant communication when possible, but it also provides information about whether a user is in a meeting or out of the office, indicating that instant communication is not possible.</span></span> <span data-ttu-id="beb92-118">이 현재 상태는 비즈니스용 Skype 및 Microsoft Outlook 메시징 및 공동 작업 클라이언트, Microsoft SharePoint 기술 및 기타 현재 상태 인식 응용 프로그램에서 현재 상태 아이콘으로 Microsoft Office.</span><span class="sxs-lookup"><span data-stu-id="beb92-118">This presence status is displayed as a presence icon in Skype for Business and other presence-aware applications, including the Microsoft Outlook messaging and collaboration client, Microsoft SharePoint technologies, and Microsoft Office.</span></span> <span data-ttu-id="beb92-119">현재 상태 아이콘은 사용자의 현재 가용성 및 통신 의사를 나타내는 아이콘입니다.</span><span class="sxs-lookup"><span data-stu-id="beb92-119">The presence icon represents the user's current availability and willingness to communicate.</span></span> 
  
### <a name="technical-requirements"></a><span data-ttu-id="beb92-120">기술 요구 사항</span><span class="sxs-lookup"><span data-stu-id="beb92-120">Technical requirements</span></span>

<span data-ttu-id="beb92-121">IM(인스턴트 메시징) 및 현재 상태는 항상 Enterprise Edition 프런트 엔드 풀 및 Standard Edition 서버에서 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="beb92-121">Instant messaging (IM) and presence always run on Enterprise Edition Front End pools and Standard Edition servers.</span></span> <span data-ttu-id="beb92-122">지원되는 하드웨어, 운영 체제 및 데이터베이스 소프트웨어에 대한 자세한 내용은 인증  [게이트웨이,](../../SfbPartnerCertification/certification/infra-gateways.md)비즈니스용  [Skype 2015](requirements-for-your-environment/requirements-for-your-environment.md)환경에 대한 요구 사항 및 비즈니스용 [Skype 서버 2019의](../../SfBServer2019/plan/system-requirements.md)인프라 요구 사항을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="beb92-122">For information on supported hardware, operating systems, and database software, see  [Certified Gateways](../../SfbPartnerCertification/certification/infra-gateways.md),  [Requirements for your Skype for Business 2015 environment](requirements-for-your-environment/requirements-for-your-environment.md), and [Infrastructure requirements for Skype for Business Server 2019](../../SfBServer2019/plan/system-requirements.md).</span></span>
  
### <a name="enabling-communication-with-external-users"></a><span data-ttu-id="beb92-123">외부 사용자와의 통신 사용</span><span class="sxs-lookup"><span data-stu-id="beb92-123">Enabling communication with external users</span></span>

<span data-ttu-id="beb92-124">사용자가 외부 사용자와 통신할 수 있도록 하여 비즈니스용 Skype 서버에 대한 투자 이익을 크게 증가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="beb92-124">You can greatly increase the benefits of your investment in Skype for Business Server by enabling your users to communicate with external users.</span></span> <span data-ttu-id="beb92-125">외부 사용자에는 다음이 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="beb92-125">External users can include:</span></span>
  
- <span data-ttu-id="beb92-126">원격 사용자: 방화벽 외부에서 랩톱 또는 기타 비즈니스용 Skype 서버 장치를 사용하는 조직의 사용자</span><span class="sxs-lookup"><span data-stu-id="beb92-126">Remote users: Your organization's own users, when they are working outside your firewalls and are using their laptops or other Skype for Business Server devices.</span></span>
    
- <span data-ttu-id="beb92-127">페더타 사용자: 비즈니스용 Skype 서버를 실행하기도 하는 회사에서 작업하는 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="beb92-127">Federated users: Users from companies you work with who also run Skype for Business Server.</span></span> <span data-ttu-id="beb92-128">조직의 사용자가 이러한 사용자에게 쉽게 연결할 수 있도록 하려면 이러한 회사와 페더레이션 관계를 만들면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="beb92-128">To enable your users to easily contact these users, you create federated relationships with these companies.</span></span> 
    
- <span data-ttu-id="beb92-129">Skype 사용자: 비즈니스용 Skype 사용자는 IM, 음성 및 비디오를 사용하여 Skype에서 수억 명의 사용자에게 도달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="beb92-129">Skype users: Skype for Business users can reach the hundreds of millions of users on Skype with IM, voice and video.</span></span>
    
> [!NOTE]
> <span data-ttu-id="beb92-130">AOL, Yahoo 및 Google Talk는 더 이상 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="beb92-130">AOL, Yahoo, and Google Talk are no longer supported.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="beb92-131">이러한 시나리오 중 일부 또는 전체를 사용하도록 설정하려면 에지 서버를 배포하여 비즈니스용 Skype 서버 배포와 외부 사용자 간의 보안 통신을 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="beb92-131">To enable any or all of these scenarios, you need to deploy an Edge Server to help enable secure communications between your Skype for Business Server deployment and external users.</span></span> <span data-ttu-id="beb92-132">조직의 원격 사용자와 페더타 조직의 사용자는 서로의 현재 상태와 IM을 사용하여 통신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="beb92-132">Your organization's remote users and users at federated organizations will be able to see each other's presence and communicate using IM.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="beb92-133">XMPP(Extensible Messaging and Presence Protocol)는 UCCP(Unified Capabilities Collaboration Platform) JITC(Joint Interoperability Test Command) 인증 시나리오에서만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="beb92-133">Extensible Messaging and Presence Protocol (XMPP) is only supported for Unified Capabilities Collaboration Platform (UCCP) Joint Interoperability Test Command (JITC) certification scenarios.</span></span> 
  
### <a name="archiving-im-content"></a><span data-ttu-id="beb92-134">IM 콘텐츠 보관</span><span class="sxs-lookup"><span data-stu-id="beb92-134">Archiving IM content</span></span>

<span data-ttu-id="beb92-135">비즈니스용 Skype 서버는 조직이 규정 준수 규정을 따라야 하는 경우 사용할 수 있는 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="beb92-135">Skype for Business Server provides features you can use if your organization must follow compliance regulations.</span></span> <span data-ttu-id="beb92-136">보관을 사용하여 조직의 모든 사용자 또는 지정한 특정 사용자에 대한 IM 메시지 콘텐츠를 보관할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="beb92-136">You can use Archiving to archive the content of IM messages for all users in your organization or for only certain users that you specify.</span></span> <span data-ttu-id="beb92-137">자세한 내용은 비즈니스용 Skype 서버의 보관 [계획을 참조하세요.](archiving/archiving.md)</span><span class="sxs-lookup"><span data-stu-id="beb92-137">For details, see [Plan for archiving in Skype for Business Server](archiving/archiving.md).</span></span> 
  
<span data-ttu-id="beb92-138">또한 Microsoft Exchange Server 2013을 배포한 경우 Exchange 데이터의 보관을 비즈니스용 Skype 서버 데이터의 보관과 통합하고 단일 도구를 사용하여 두 유형의 보관된 데이터를 모두 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="beb92-138">If you also have Microsoft Exchange Server 2013 deployed, you can integrate the archiving of Exchange data with the archiving of Skype for Business Server data, and use a single tool to search both types of archived data.</span></span> <span data-ttu-id="beb92-139">자세한 내용은 보관을 사용하도록 비즈니스용 Skype 서버 [Exchange Server 참조하세요.](../deploy/integrate-with-exchange-server/use-exchange-archiving.md)</span><span class="sxs-lookup"><span data-stu-id="beb92-139">For more information, see [Configure Skype for Business Server to use Exchange Server archiving](../deploy/integrate-with-exchange-server/use-exchange-archiving.md).</span></span>
  
### <a name="topologies-and-components"></a><span data-ttu-id="beb92-140">토폴로지 및 구성 요소</span><span class="sxs-lookup"><span data-stu-id="beb92-140">Topologies and components</span></span>

<span data-ttu-id="beb92-141">IM(인스턴트 메시징) 및 현재 상태의 구성 요소는 다음뿐입니다.</span><span class="sxs-lookup"><span data-stu-id="beb92-141">The only components required for instant messaging (IM) and presence are:</span></span>
  
- <span data-ttu-id="beb92-142">조직의 프런트 엔드 서버(풀) 또는 Standard Edition 서버</span><span class="sxs-lookup"><span data-stu-id="beb92-142">Your organization's Front End servers (known as a pool) or a Standard Edition server.</span></span> <span data-ttu-id="beb92-143">IM 및 현재 상태 기능은 이러한 서버에서 항상 사용하도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="beb92-143">IM and presence capabilities are always enabled on these servers.</span></span> <span data-ttu-id="beb92-144">프런트 엔드 풀 토폴로지 및 관리에 대한 자세한 내용은 프런트 엔드 풀 고가용성 [및 관리를 참조하십시오.](high-availability-and-disaster-recovery/high-availability.md)</span><span class="sxs-lookup"><span data-stu-id="beb92-144">For more information on Front End pool topologies and management, see [Front End Pool high availability and management](high-availability-and-disaster-recovery/high-availability.md).</span></span>
    
- <span data-ttu-id="beb92-145">Enterprise Edition 프런트 엔드 풀이 있는 경우 부하가 있는 경우</span><span class="sxs-lookup"><span data-stu-id="beb92-145">A load balancer, if you have an Enterprise Edition Front End pool.</span></span>
    
### <a name="supported-collocation"></a><span data-ttu-id="beb92-146">지원되는Ococation</span><span class="sxs-lookup"><span data-stu-id="beb92-146">Supported collocation</span></span>

<span data-ttu-id="beb92-147">여러 역할이 설치된 단일 서버 또는 서버 그룹이 함께 있는 것으로 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="beb92-147">Collocation is defined as having a single server, or group of servers, with multiple roles installed.</span></span> <span data-ttu-id="beb92-148">설명에 대한 자세한 내용은 비즈니스용 [Skype 서버의 토폴로지 기본 사항을 참조하세요.](topology-basics/topology-basics.md)</span><span class="sxs-lookup"><span data-stu-id="beb92-148">For details on collocation, see [Topology Basics for Skype for Business Server](topology-basics/topology-basics.md).</span></span> 
  

