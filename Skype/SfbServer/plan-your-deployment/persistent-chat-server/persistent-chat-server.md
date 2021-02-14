---
title: 비즈니스용 Skype 서버 2015의 영구 채팅 서버 계획
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 8/17/2015
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 9e652487-a123-40c0-ae61-47fb8ecc4a20
description: '요약: 이 항목을 읽고 비즈니스용 Skype 서버 2015에서 영구 채팅 서버를 계획하는 방법을 배워 읽습니다.'
ms.openlocfilehash: 9195c149744b9aab9927f0b2a6e490442cff6573
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813668"
---
# <a name="plan-for-persistent-chat-server-in-skype-for-business-server-2015"></a><span data-ttu-id="2d5cc-103">비즈니스용 Skype 서버 2015의 영구 채팅 서버 계획</span><span class="sxs-lookup"><span data-stu-id="2d5cc-103">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="2d5cc-104">**요약:** 이 항목을 읽고 비즈니스용 Skype 서버 2015에서 영구 채팅 서버를 계획하는 방법을 배워야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d5cc-104">**Summary:** Read this topic to learn how to plan for Persistent Chat Server in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="2d5cc-105">영구 채팅 서버는 조직의 여러 사용자가 시간이 지날 때 대화방 대화에 참가할 수 있는 선택적 역할입니다.</span><span class="sxs-lookup"><span data-stu-id="2d5cc-105">Persistent Chat Server is an optional role that lets multiple users in your organization participate in chat room conversations that persist over time.</span></span> <span data-ttu-id="2d5cc-106">사용자는 채팅 세션 중에 실시간으로 통신할 수 있습니다. 텍스트, 링크 및 파일을 포함한 각 세션의 콘텐츠는 영구적이기 때문에 사용자는 세션의 모든 콘텐츠를 보고 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d5cc-106">Although users can communicate in real time during a chat session, the content of each session--including text, links, and files--is persistent, which means users can view and search all content of the session at any time.</span></span>
  
<span data-ttu-id="2d5cc-107">영구 채팅 서버는 다음을 통해 조직 내의 통신을 개선하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d5cc-107">Persistent Chat Server can help improve communication within your organization by:</span></span>
  
- <span data-ttu-id="2d5cc-108">조직 전체의 정보 인식과 참여 확대</span><span class="sxs-lookup"><span data-stu-id="2d5cc-108">Broadening information awareness and participation throughout the organization</span></span>
    
- <span data-ttu-id="2d5cc-109">효율적인 정보 공유 사용</span><span class="sxs-lookup"><span data-stu-id="2d5cc-109">Enabling efficient information sharing</span></span> 
    
- <span data-ttu-id="2d5cc-110">지리적으로 분산된 팀과 기능 간 팀을 포함하여 팀 간의 통신 개선</span><span class="sxs-lookup"><span data-stu-id="2d5cc-110">Improving communication between teams, including geographically dispersed and cross-functional teams</span></span>
    
- <span data-ttu-id="2d5cc-111">정보 오버로드 줄이기</span><span class="sxs-lookup"><span data-stu-id="2d5cc-111">Reducing information overload</span></span>
    
- <span data-ttu-id="2d5cc-112">영구 채팅 준수 서비스를 선택적으로 배포하여 준수 규정 준수 준수</span><span class="sxs-lookup"><span data-stu-id="2d5cc-112">Following compliance regulations by optionally deploying the Persistent Chat Compliance service</span></span>

> [!NOTE] 
> <span data-ttu-id="2d5cc-113">영구 채팅은 비즈니스용 Skype 서버 2015에서 사용할 수 있지만 비즈니스용 Skype 서버 2019에서 더 이상 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2d5cc-113">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="2d5cc-114">Teams에서 동일한 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d5cc-114">The same functionality is available in Teams.</span></span> <span data-ttu-id="2d5cc-115">자세한 내용은 Microsoft Teams 업그레이드 시작을 [참조하세요.](/microsoftteams/upgrade-start-here)</span><span class="sxs-lookup"><span data-stu-id="2d5cc-115">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="2d5cc-116">영구 채팅을 사용하려면 이 기능이 필요한 사용자를 Teams로 마이그레이션하거나 비즈니스용 Skype 서버 2015를 계속 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d5cc-116">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 
    
## <a name="persistent-chat-server-high-level-architecture"></a><span data-ttu-id="2d5cc-117">영구 채팅 서버 고급 아키텍처</span><span class="sxs-lookup"><span data-stu-id="2d5cc-117">Persistent Chat Server high-level architecture</span></span>

<span data-ttu-id="2d5cc-118">다음 다이어그램에서는 영구 채팅 서버 아키텍처에 대한 높은 수준의 보기를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="2d5cc-118">The following diagram shows a high-level view of the Persistent Chat Server architecture.</span></span> 
  
![영구 채팅 서버 고급 아키텍처](../../media/0344f6e2-0c6d-4391-b4b3-ec31062b1576.png)
  
<span data-ttu-id="2d5cc-120">영구 채팅은 영구 채팅 서비스와 백 엔드 데이터베이스 구성 요소를 제공하는 SQL 서버 역할로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d5cc-120">Persistent Chat consists of a front-end server role that provides the Persistent Chat services as well as a back-end SQL database component.</span></span> <span data-ttu-id="2d5cc-121">프런트 엔드 및 백 엔드 구성 요소는 모두 전용 영구 채팅 풀에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d5cc-121">Both front-end and back-end components are included in a dedicated Persistent Chat pool.</span></span> <span data-ttu-id="2d5cc-122">영구 채팅 서버를 호스팅하는 각 컴퓨터에는 기존 비즈니스용 Skype 서버 2015 토폴로지 액세스 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d5cc-122">Each computer that hosts Persistent Chat Server must have access to an existing Skype for Business Server 2015 topology.</span></span> <span data-ttu-id="2d5cc-123">이 다이어그램에는 메시지를 라우팅하기 위해 비즈니스용 Skype 서버 풀 A에 종속되는 영구 채팅 서버 풀(A)이 하나 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d5cc-123">In this diagram, there is one Persistent Chat Server pool (A), which is dependent on Skype for Business Server Pool A for routing messages to it.</span></span>
  
<span data-ttu-id="2d5cc-124">각각 최대 4개의 활성 영구 채팅 서버가 최대 80K 동시 사용자를 지원하는 하나 이상의 영구 채팅 서버 풀을 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d5cc-124">You can deploy one or more Persistent Chat Server pools, each with up to four active Persistent Chat Servers supporting up to 80K concurrent users.</span></span>
  
<span data-ttu-id="2d5cc-125">비즈니스용 Skype 서버 2015는 등록을 위해 SIP(Session Initiation Protocol)를 사용하고 채팅에 XCCOS(Extensible Chat Communication Over SIP Protocol)를 사용하여 영구 채팅 서비스와 통신합니다.</span><span class="sxs-lookup"><span data-stu-id="2d5cc-125">Skype for Business Server 2015 communicates with the Persistent Chat service using the Session Initiation Protocol (SIP) for registration and the Extensible Chat Communication Over SIP protocol (XCCOS) for chat.</span></span> 
  
## <a name="persistent-chat-services"></a><span data-ttu-id="2d5cc-126">영구 채팅 서비스</span><span class="sxs-lookup"><span data-stu-id="2d5cc-126">Persistent Chat services</span></span>

<span data-ttu-id="2d5cc-127">다음 다이어그램에는 영구 채팅 서버 프런트 엔드 서비스와 이러한 서비스가 백 엔드 데이터베이스 구성 요소와 통신하는 방식이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d5cc-127">The following diagram shows the Persistent Chat Server front-end services, and how these services communicate with the back-end database components.</span></span> <span data-ttu-id="2d5cc-128">프런트 엔드 구성 요소에는 영구 채팅 서비스 및 준수 서비스가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d5cc-128">The front-end components include the Persistent Chat services and the Compliance service.</span></span> <span data-ttu-id="2d5cc-129">백 엔드 구성 요소에는 영구 채팅 저장소 및 영구 채팅 준수 저장소가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d5cc-129">The back-end components include the Persistent Chat store and the Persistent Chat compliance store.</span></span>
  
![영구 채팅 서버 고급 서비스](../../media/bcdbadbe-e868-4a46-8a73-36562648fdf7.png)
  
### <a name="chat-service"></a><span data-ttu-id="2d5cc-131">채팅 서비스</span><span class="sxs-lookup"><span data-stu-id="2d5cc-131">Chat service</span></span>

<span data-ttu-id="2d5cc-132">채널 서비스라고도 하는 채팅 서비스는 영구 채팅 서버를 담당하는 핵심 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="2d5cc-132">The Chat service, also called the Channel service, is the core service responsible for Persistent Chat Server.</span></span> <span data-ttu-id="2d5cc-133">채팅 서비스는 다음과 같은 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2d5cc-133">The Chat service provides the following functions:</span></span>
  
- <span data-ttu-id="2d5cc-134">수신 메시지를 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="2d5cc-134">Accepts incoming messages</span></span>
    
- <span data-ttu-id="2d5cc-135">영구 채팅방 내의 온라인 참가자 등록 및 나열</span><span class="sxs-lookup"><span data-stu-id="2d5cc-135">Registers and lists online participants within a Persistent Chat room</span></span>
    
- <span data-ttu-id="2d5cc-136">다른 채널 구독자에게 메시지를 재전송합니다.</span><span class="sxs-lookup"><span data-stu-id="2d5cc-136">Retransmits messages to other channel subscribers</span></span>
    
- <span data-ttu-id="2d5cc-137">채널 관리, 채팅방 초대, 검색 및 새 콘텐츠 알림 논리 구현</span><span class="sxs-lookup"><span data-stu-id="2d5cc-137">Implements logic for channel management, chat room invitations, search and new content notifications</span></span>
    
<span data-ttu-id="2d5cc-138">영구 채팅 서비스는 영구 채팅 저장소를 사용하여 채팅방 콘텐츠 및 기타 시스템 메타데이터(권한 부여 규칙 등)를 저장하고 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="2d5cc-138">The Persistent Chat service stores and accesses chat room content and other system metadata (authorization rules and so on) by using the Persistent Chat store.</span></span> <span data-ttu-id="2d5cc-139">이 서비스는 채팅방에 업로드된 파일을 영구 채팅 파일 저장소에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="2d5cc-139">The service stores files that are uploaded into chat rooms in the Persistent Chat file store.</span></span>
  
### <a name="compliance-service"></a><span data-ttu-id="2d5cc-140">Compliance Service</span><span class="sxs-lookup"><span data-stu-id="2d5cc-140">Compliance service</span></span>

<span data-ttu-id="2d5cc-141">조직에 영구 채팅 활동을 보관해야 하는 규정이 있는 경우 선택적 영구 채팅 준수 서비스를 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d5cc-141">If your organization has regulations that require Persistent Chat activity to be archived, you can deploy the optional Persistent Chat Compliance service.</span></span> <span data-ttu-id="2d5cc-142">준수 서비스는 채팅 콘텐츠 및 이벤트(예: 채팅방 참가 및 나가기)를 영구 채팅 준수 파일 저장소에 보관합니다.</span><span class="sxs-lookup"><span data-stu-id="2d5cc-142">The Compliance service is responsible for archiving chat content and events, such as joining and leaving rooms, to the Persistent Chat Compliance file store.</span></span> <span data-ttu-id="2d5cc-143">준수 서비스는 영구 채팅 풀의 각 영구 채팅 서버에 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d5cc-143">The Compliance service is installed on each Persistent Chat Server in a Persistent Chat pool.</span></span> 
  
### <a name="web-services"></a><span data-ttu-id="2d5cc-144">웹 서비스</span><span class="sxs-lookup"><span data-stu-id="2d5cc-144">Web services</span></span>

<span data-ttu-id="2d5cc-145">영구 채팅 웹 서비스는 비즈니스용 Skype 프런트 엔드 서버에서 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d5cc-145">The Persistent Chat web services run on the Skype for Business Front End Servers.</span></span> <span data-ttu-id="2d5cc-146">웹 서비스는 IIS(인터넷 정보 서비스)에 의존하며 웹 구성 요소로 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d5cc-146">The web services depend on Internet Information Services (IIS), and are implemented as web components:</span></span>
  
- <span data-ttu-id="2d5cc-147">파일 업로드 및 다운로드를 위한 영구 채팅 웹 서비스는 채팅방에서 파일을 게시하고 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="2d5cc-147">Persistent Chat web services for file upload and download are responsible for posting and retrieving files from chat rooms.</span></span>
    
- <span data-ttu-id="2d5cc-148">채팅방 관리를 위한 영구 채팅 웹 서비스는 사용자에게 대화방을 관리하고 새 채팅방을 만드는 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2d5cc-148">Persistent Chat web services for chat room management are responsible for providing users the ability to manage their chat rooms, and create new chat rooms.</span></span>
    
## <a name="defining-requirements-for-your-organization"></a><span data-ttu-id="2d5cc-149">조직의 요구 사항 정의</span><span class="sxs-lookup"><span data-stu-id="2d5cc-149">Defining requirements for your organization</span></span>

<span data-ttu-id="2d5cc-150">영구 채팅 서버를 배포하기로 결정한 경우 조직의 비즈니스 요구 사항을 확인한 다음 비즈니스 요구 사항을 지원하기 위한 토폴로지, 인프라 및 기술 요구 사항을 정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d5cc-150">If you decide to deploy Persistent Chat Server, you'll need to determine your organization's business requirements, then define the topology, infrastructure, and technical requirements to support your business needs.</span></span> <span data-ttu-id="2d5cc-151">배포를 최적화하려면 다음 질문에 대답해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d5cc-151">To optimize your deployment, you'll need to answer the following questions:</span></span>
  
- <span data-ttu-id="2d5cc-152">이전 버전의 그룹 채팅 서버 또는 이전 버전의 영구 채팅 서버에서 마이그레이션하거나 영구 채팅 서버를 처음으로 배포하고 있습니까?</span><span class="sxs-lookup"><span data-stu-id="2d5cc-152">Are you migrating from a previous version of Group Chat Server, or a previous version of Persistent Chat Server, or are you deploying Persistent Chat Server for the first time?</span></span>
    
- <span data-ttu-id="2d5cc-153">영구 채팅 서버를 사용할 수 있는 사람</span><span class="sxs-lookup"><span data-stu-id="2d5cc-153">Who can use Persistent Chat Server?</span></span> <span data-ttu-id="2d5cc-154">영구 채팅 정책을 지정하여 전역, 사이트 또는 사용자 수준에서 사용자 액세스를 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d5cc-154">You specify Persistent Chat policies to determine user access at the global, site, or user level.</span></span>
    
- <span data-ttu-id="2d5cc-155">영구 채팅 서버에 액세스해야 하는 사용자의 수</span><span class="sxs-lookup"><span data-stu-id="2d5cc-155">How many users will require access to Persistent Chat Server?</span></span> <span data-ttu-id="2d5cc-156">영구 채팅 서버는 프로비전된 사용자 150,000명(정책에서 사용하도록 설정)과 최대 80,000명 동시 사용자를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="2d5cc-156">Persistent Chat Server supports 150,000 provisioned users (enabled by policy), and a maximum of 80,000 concurrent users.</span></span> <span data-ttu-id="2d5cc-157">단일 영구 채팅 서버는 20,000명의 연결된 사용자를 지원할 수 있으며, 단일 영구 채팅 서버 풀에는 최대 4대의 활성 서버가 있으며 총 80,000명이 동시 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d5cc-157">A single Persistent Chat Server can support 20,000 connected users, and a single Persistent Chat Server pool can have up to 4 active servers for a total of 80,000 concurrently connected users.</span></span>
    
- <span data-ttu-id="2d5cc-158">범위, 교신 차단 영역 및 액세스는 어떻게 제어하겠습니까?</span><span class="sxs-lookup"><span data-stu-id="2d5cc-158">How do you want to control scopes, ethical boundaries, and access?</span></span> <span data-ttu-id="2d5cc-159">범주를 정의하여 이러한 경계를 구분하고 각 범주에서 만들어진 방에 있을 수 있는 사용자도 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d5cc-159">You can define categories to segregate these boundaries, and choose who is allowed to be in rooms that are created in each of these categories.</span></span>
    
- <span data-ttu-id="2d5cc-160">방을 만들 수 있는 사용자는 어떻게 제어합니까?</span><span class="sxs-lookup"><span data-stu-id="2d5cc-160">How do you want to control who can create rooms?</span></span> <span data-ttu-id="2d5cc-161">방을 만들 수 있는 작성자를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d5cc-161">You can define creators who can create rooms.</span></span> <span data-ttu-id="2d5cc-162">작성자는 다른 구성원을 채팅방의 지속적인 관리를 위해 채팅방 관리자로 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d5cc-162">Creators can assign other members as chat room managers for ongoing management of the rooms.</span></span>
    
- <span data-ttu-id="2d5cc-163">방을 어떻게 만들겠습니까?</span><span class="sxs-lookup"><span data-stu-id="2d5cc-163">How do you want to create rooms?</span></span> <span data-ttu-id="2d5cc-164">영구 채팅 서버는 채팅방을 만들고 관리하기 위한 웹 기반 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2d5cc-164">Persistent Chat Server provides a web-based feature for creating and managing rooms.</span></span> <span data-ttu-id="2d5cc-165">이 설정은 비즈니스용 Skype 클라이언트에서 시작될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d5cc-165">This can be launched from the Skype for Business client.</span></span> <span data-ttu-id="2d5cc-166">비즈니스 요구 사항 및 워크플로를 구현하는 고객 솔루션을 정의하고 사용자를 사용자 지정 솔루션으로 연결하도록 영구 채팅 서버를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d5cc-166">You can choose to define a customer solution that implements your business requirements and workflows, and configures Persistent Chat Server to direct users to your custom solution.</span></span>
    
- <span data-ttu-id="2d5cc-167">프로비전하려는 추가 기능은 어떤 종류입니까?</span><span class="sxs-lookup"><span data-stu-id="2d5cc-167">What kind of add-ins do you want to provision?</span></span> <span data-ttu-id="2d5cc-168">추가 기능에서는 비즈니스용 Skype 클라이언트의 확장성 창을 활용하여 방과 관련된 컨텍스트를 제공하면 방 내 환경을 개선할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d5cc-168">Add-ins enhance the in-room experience by leveraging the extensibility pane in the Skype for Business client to provide context that is relevant to the room.</span></span> <span data-ttu-id="2d5cc-169">가장 유용할 수 있는 일반적인 추가 기능을 선택할 수 있습니다(예: 회사 웹 사이트,내부 공동 작업 문서 등).</span><span class="sxs-lookup"><span data-stu-id="2d5cc-169">You can choose what general add-ins might be most useful (for example, your company website, internal collaboration documents, and so on).</span></span> <span data-ttu-id="2d5cc-170">채팅방 관리자는 필요에 따라 등록된 추가 기능 중 하나를 선택해서 이를 자신의 방과 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d5cc-170">Chat room managers can choose one of the registered add-ins and associate it with their rooms, if desired.</span></span> 
    
- <span data-ttu-id="2d5cc-171">고가용성 및 재해 복구 요구 사항은 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="2d5cc-171">What kind of high availability and disaster recovery requirements do you have?</span></span> <span data-ttu-id="2d5cc-172">영구 채팅 서버는 고가용성을 SQL Server 미러링 및 SQL Server 클러스터링을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="2d5cc-172">Persistent Chat Server supports SQL Server mirroring and SQL Server clustering for high availability.</span></span> <span data-ttu-id="2d5cc-173">재해 복구를 위해 영구 채팅 서버는 로그 전달이 지원되는 확장된 풀에서 최대 8대의 서버(활성 SQL Server 지원)</span><span class="sxs-lookup"><span data-stu-id="2d5cc-173">For disaster recovery, Persistent Chat Server supports up to 8 servers (4 active and 4 standby) in a stretched pool with SQL Server log shipping.</span></span> 
    
- <span data-ttu-id="2d5cc-174">규정 요구 사항이 있습니까?</span><span class="sxs-lookup"><span data-stu-id="2d5cc-174">Are there regulatory requirements?</span></span> <span data-ttu-id="2d5cc-175">회사가 데이터를 국가 내에 유지해야 하는 국가 또는 지역에 있는 경우 각 로컬의 여러 영구 채팅 서버 풀을 특정 지역에 배포해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d5cc-175">If your company is in a country or region where data needs to be kept within the country, you may need to deploy multiple Persistent Chat Server pools, each local to a specific geography.</span></span> <span data-ttu-id="2d5cc-176">채팅방, 범주 또는 추가 기능을 풀에 걸쳐 있지 않고 하나의 영구 채팅 서버 풀에만 속합니다.</span><span class="sxs-lookup"><span data-stu-id="2d5cc-176">A room, category, or add-in does not span pools--it belongs to only one Persistent Chat Server pool.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="2d5cc-177">영구 채팅 서버 풀이 여러 개이면 확장을 더 많이 할 수 없습니다(모든 영구 채팅 서버 풀에서 동시 사용자 수가 80,000명만 있을 수 있습니다).</span><span class="sxs-lookup"><span data-stu-id="2d5cc-177">Having multiple Persistent Chat Server pools does not give you more scale (you can still have only 80,000 concurrent users across all your Persistent Chat Server pools).</span></span> <span data-ttu-id="2d5cc-178">여러 영구 채팅 서버 풀을 지원하는 주된 이유는 규제 관련 사항을 지원하기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="2d5cc-178">The primary reason for supporting multiple Persistent Chat Server pools is to support regulatory concerns.</span></span> 
  
## <a name="for-more-information"></a><span data-ttu-id="2d5cc-179">자세한 내용</span><span class="sxs-lookup"><span data-stu-id="2d5cc-179">For more information</span></span>

<span data-ttu-id="2d5cc-180">영구 채팅 서버 설치 및 구성에 대한 자세한 내용은 다음 항목을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="2d5cc-180">For more information about installing and configuring Persistent Chat Server, see the following topics:</span></span>
  
- <span data-ttu-id="2d5cc-181">영구 채팅 서버를 배포하는 방법에 대한 자세한 내용은 비즈니스용 Skype 서버 [2015에서 영구](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md)채팅 서버 배포를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2d5cc-181">For details about how to deploy Persistent Chat Server, see [Deploy Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md).</span></span> 
    
- <span data-ttu-id="2d5cc-182">영구 채팅 서버 배포에서 설정을 구성하는 방법에 대한 자세한 내용은 비즈니스용 Skype 서버 [2015에서](../../manage/persistent-chat/persistent-chat.md)영구 채팅 서버 관리를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2d5cc-182">For details about how to configure settings on your Persistent Chat Server deployment, see [Manage Persistent Chat Server in Skype for Business Server 2015](../../manage/persistent-chat/persistent-chat.md).</span></span>
    

