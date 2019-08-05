---
title: 비즈니스용 Skype 서버 2015의 영구 채팅 서버 계획
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 8/17/2015
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9e652487-a123-40c0-ae61-47fb8ecc4a20
description: '요약: 비즈니스용 Skype 서버 2015에서 영구 채팅 서버를 계획 하는 방법을 알아보려면이 항목을 참조 하세요.'
ms.openlocfilehash: 3e485f938d2bd48dad5f1b9f0baa96d7f3f537d0
ms.sourcegitcommit: d4248fefd706616bd3ccc5b510a6696303fa88e1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/02/2019
ms.locfileid: "36197909"
---
# <a name="plan-for-persistent-chat-server-in-skype-for-business-server-2015"></a><span data-ttu-id="168b4-103">비즈니스용 Skype 서버 2015의 영구 채팅 서버 계획</span><span class="sxs-lookup"><span data-stu-id="168b4-103">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="168b4-104">**요약:** 비즈니스용 Skype 서버 2015에서 영구 채팅 서버를 계획 하는 방법을 알아보려면이 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="168b4-104">**Summary:** Read this topic to learn how to plan for Persistent Chat Server in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="168b4-105">영구 채팅 서버는 조직의 여러 사용자가 시간에 따라 유지 되는 채팅방 대화에 참여할 수 있도록 하는 선택적 역할입니다.</span><span class="sxs-lookup"><span data-stu-id="168b4-105">Persistent Chat Server is an optional role that lets multiple users in your organization participate in chat room conversations that persist over time.</span></span> <span data-ttu-id="168b4-106">채팅 세션 중에는 사용자가 실시간으로 통신할 수 있지만, 각 세션의 내용 (텍스트, 링크, 파일 포함)은 영구적 이며,이는 사용자가 언제 든 지 세션의 모든 콘텐츠를 보고 검색할 수 있다는 것을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="168b4-106">Although users can communicate in real time during a chat session, the content of each session--including text, links, and files--is persistent, which means users can view and search all content of the session at any time.</span></span>
  
<span data-ttu-id="168b4-107">영구 채팅 서버는 다음을 수행 하 여 조직 내의 통신을 향상 시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="168b4-107">Persistent Chat Server can help improve communication within your organization by:</span></span>
  
- <span data-ttu-id="168b4-108">조직 전체에 걸쳐 정보 인식 및 참여 Broadening</span><span class="sxs-lookup"><span data-stu-id="168b4-108">Broadening information awareness and participation throughout the organization</span></span>
    
- <span data-ttu-id="168b4-109">효율적인 정보 공유 사용</span><span class="sxs-lookup"><span data-stu-id="168b4-109">Enabling efficient information sharing</span></span> 
    
- <span data-ttu-id="168b4-110">지리적으로 분산 된 팀과 부서간 업무 흐름도를 포함 하 여 팀 간의 의사 소통 개선</span><span class="sxs-lookup"><span data-stu-id="168b4-110">Improving communication between teams, including geographically dispersed and cross-functional teams</span></span>
    
- <span data-ttu-id="168b4-111">정보 오버 로드 줄이기</span><span class="sxs-lookup"><span data-stu-id="168b4-111">Reducing information overload</span></span>
    
- <span data-ttu-id="168b4-112">영구 채팅 준수 서비스를 선택적으로 배포 하 여 준수 규정이 팔 로우 합니다.</span><span class="sxs-lookup"><span data-stu-id="168b4-112">Following compliance regulations by optionally deploying the Persistent Chat Compliance service</span></span>

> [!NOTE] 
> <span data-ttu-id="168b4-113">영구 채팅은 비즈니스용 Skype 서버 2015에서 사용할 수 있지만, 비즈니스용 Skype Server 2019에서는 더 이상 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="168b4-113">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="168b4-114">팀 에서도 동일한 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="168b4-114">The same functionality is available in Teams.</span></span> <span data-ttu-id="168b4-115">자세한 내용은 [Microsoft 팀 업그레이드 시작](/microsoftteams/upgrade-start-here)을 참고 하세요.</span><span class="sxs-lookup"><span data-stu-id="168b4-115">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="168b4-116">영구 채팅을 사용 해야 하는 경우에는이 기능이 필요한 사용자를 팀에 마이그레이션하거나 비즈니스용 Skype 서버 2015를 계속 사용 하는 것이 선택 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="168b4-116">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 
    
## <a name="persistent-chat-server-high-level-architecture"></a><span data-ttu-id="168b4-117">영구 채팅 서버 상위 수준 아키텍처</span><span class="sxs-lookup"><span data-stu-id="168b4-117">Persistent Chat Server high-level architecture</span></span>

<span data-ttu-id="168b4-118">다음 다이어그램은 영구 채팅 서버 아키텍처의 상위 수준 보기를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="168b4-118">The following diagram shows a high-level view of the Persistent Chat Server architecture.</span></span> 
  
![영구 채팅 서버 상위 수준 아키텍처](../../media/0344f6e2-0c6d-4391-b4b3-ec31062b1576.png)
  
<span data-ttu-id="168b4-120">영구 채팅은 영구 채팅 서비스 및 백 엔드 SQL 데이터베이스 구성 요소를 제공 하는 프런트 엔드 서버 역할의 하나로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="168b4-120">Persistent Chat consists of a front-end server role that provides the Persistent Chat services as well as a back-end SQL database component.</span></span> <span data-ttu-id="168b4-121">프런트 엔드 및 백 엔드 구성 요소는 모두 전용 영구 채팅 풀에 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="168b4-121">Both front-end and back-end components are included in a dedicated Persistent Chat pool.</span></span> <span data-ttu-id="168b4-122">영구 채팅 서버를 호스트 하는 각 컴퓨터는 기존 비즈니스용 Skype 서버 2015 토폴로지에 액세스할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="168b4-122">Each computer that hosts Persistent Chat Server must have access to an existing Skype for Business Server 2015 topology.</span></span> <span data-ttu-id="168b4-123">이 다이어그램에는 메시지 라우팅에 대 한 비즈니스용 Skype 서버 풀 A에 의존 하는 영구 채팅 서버 풀 (A)이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="168b4-123">In this diagram, there is one Persistent Chat Server pool (A), which is dependent on Skype for Business Server Pool A for routing messages to it.</span></span>
  
<span data-ttu-id="168b4-124">최대 80K 동시 사용자를 지 원하는 최대 4 개의 활성 영구 채팅 서버를 사용 하 여 하나 이상의 영구 채팅 서버 풀을 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="168b4-124">You can deploy one or more Persistent Chat Server pools, each with up to four active Persistent Chat Servers supporting up to 80K concurrent users.</span></span>
  
<span data-ttu-id="168b4-125">비즈니스용 Skype 서버 2015는 SIP (세션 초기화 프로토콜)를 사용 하 여 XCCOS (SIP 프로토콜을 통한 확장 가능한 채팅 통신) 채팅에 대해 통신 합니다.</span><span class="sxs-lookup"><span data-stu-id="168b4-125">Skype for Business Server 2015 communicates with the Persistent Chat service using the Session Initiation Protocol (SIP) for registration and the Extensible Chat Communication Over SIP protocol (XCCOS) for chat.</span></span> 
  
## <a name="persistent-chat-services"></a><span data-ttu-id="168b4-126">영구 채팅 서비스</span><span class="sxs-lookup"><span data-stu-id="168b4-126">Persistent Chat services</span></span>

<span data-ttu-id="168b4-127">다음 다이어그램은 지속적인 채팅 서버 프런트 엔드 서비스와 이러한 서비스가 백 엔드 데이터베이스 구성 요소와 통신 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="168b4-127">The following diagram shows the Persistent Chat Server front-end services, and how these services communicate with the back-end database components.</span></span> <span data-ttu-id="168b4-128">프런트 엔드 구성 요소에는 영구 채팅 서비스와 준수 서비스가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="168b4-128">The front-end components include the Persistent Chat services and the Compliance service.</span></span> <span data-ttu-id="168b4-129">백 엔드 구성 요소에는 영구 채팅 저장소와 영구 채팅 준수 저장소가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="168b4-129">The back-end components include the Persistent Chat store and the Persistent Chat compliance store.</span></span>
  
![영구 채팅 서버 상위 수준 서비스](../../media/bcdbadbe-e868-4a46-8a73-36562648fdf7.png)
  
### <a name="chat-service"></a><span data-ttu-id="168b4-131">채팅 서비스</span><span class="sxs-lookup"><span data-stu-id="168b4-131">Chat service</span></span>

<span data-ttu-id="168b4-132">채널 서비스 라고도 하는 채팅 서비스는 영구 채팅 서버를 담당 하는 핵심 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="168b4-132">The Chat service, also called the Channel service, is the core service responsible for Persistent Chat Server.</span></span> <span data-ttu-id="168b4-133">채팅 서비스는 다음 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="168b4-133">The Chat service provides the following functions:</span></span>
  
- <span data-ttu-id="168b4-134">받는 메시지 수락</span><span class="sxs-lookup"><span data-stu-id="168b4-134">Accepts incoming messages</span></span>
    
- <span data-ttu-id="168b4-135">영구 채팅방 내에서 온라인 참가자를 등록 하 고 나열 합니다.</span><span class="sxs-lookup"><span data-stu-id="168b4-135">Registers and lists online participants within a Persistent Chat room</span></span>
    
- <span data-ttu-id="168b4-136">다른 채널 등록자에 게 메시지 재전송</span><span class="sxs-lookup"><span data-stu-id="168b4-136">Retransmits messages to other channel subscribers</span></span>
    
- <span data-ttu-id="168b4-137">채널 관리, 채팅방 초대, 검색 및 새 콘텐츠 알림에 대 한 논리를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="168b4-137">Implements logic for channel management, chat room invitations, search and new content notifications</span></span>
    
<span data-ttu-id="168b4-138">영구 채팅 서비스는 영구 채팅 저장소를 사용 하 여 채팅방 콘텐츠 및 기타 시스템 메타 데이터 (권한 부여 규칙 등)를 저장 하 고 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="168b4-138">The Persistent Chat service stores and accesses chat room content and other system metadata (authorization rules and so on) by using the Persistent Chat store.</span></span> <span data-ttu-id="168b4-139">서비스는 영구 채팅 파일 저장소의 채팅방에 업로드 된 파일을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="168b4-139">The service stores files that are uploaded into chat rooms in the Persistent Chat file store.</span></span>
  
### <a name="compliance-service"></a><span data-ttu-id="168b4-140">준수 서비스</span><span class="sxs-lookup"><span data-stu-id="168b4-140">Compliance service</span></span>

<span data-ttu-id="168b4-141">조직에 영구 채팅 활동을 보관 해야 하는 규정이 있는 경우 선택적 영구 채팅 준수 서비스를 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="168b4-141">If your organization has regulations that require Persistent Chat activity to be archived, you can deploy the optional Persistent Chat Compliance service.</span></span> <span data-ttu-id="168b4-142">준수 서비스는 대화방에 참가 하 고 나가는 등의 채팅 콘텐츠 및 이벤트를 지속적인 채팅 준수 파일 저장소에 보관 하는 책임을 집니다.</span><span class="sxs-lookup"><span data-stu-id="168b4-142">The Compliance service is responsible for archiving chat content and events, such as joining and leaving rooms, to the Persistent Chat Compliance file store.</span></span> <span data-ttu-id="168b4-143">준수 서비스는 영구 채팅 풀의 각 영구 채팅 서버에 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="168b4-143">The Compliance service is installed on each Persistent Chat Server in a Persistent Chat pool.</span></span> 
  
### <a name="web-services"></a><span data-ttu-id="168b4-144">웹 서비스</span><span class="sxs-lookup"><span data-stu-id="168b4-144">Web services</span></span>

<span data-ttu-id="168b4-145">영구 채팅 웹 서비스는 비즈니스용 Skype 프런트 엔드 서버에서 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="168b4-145">The Persistent Chat web services run on the Skype for Business Front End Servers.</span></span> <span data-ttu-id="168b4-146">웹 서비스는 IIS (인터넷 정보 서비스)에 종속 되며 웹 구성 요소로 구현 됩니다.</span><span class="sxs-lookup"><span data-stu-id="168b4-146">The web services depend on Internet Information Services (IIS), and are implemented as web components:</span></span>
  
- <span data-ttu-id="168b4-147">파일 업로드 및 다운로드를 위한 영구 채팅 웹 서비스는 채팅방에서 파일을 게시 하 고 검색 하는 역할을 합니다.</span><span class="sxs-lookup"><span data-stu-id="168b4-147">Persistent Chat web services for file upload and download are responsible for posting and retrieving files from chat rooms.</span></span>
    
- <span data-ttu-id="168b4-148">채팅방 관리를 위한 영구 채팅 웹 서비스는 사용자에 게 채팅방을 관리 하 고 새 채팅방을 만들 수 있는 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="168b4-148">Persistent Chat web services for chat room management are responsible for providing users the ability to manage their chat rooms, and create new chat rooms.</span></span>
    
## <a name="defining-requirements-for-your-organization"></a><span data-ttu-id="168b4-149">조직의 요구 사항 정의</span><span class="sxs-lookup"><span data-stu-id="168b4-149">Defining requirements for your organization</span></span>

<span data-ttu-id="168b4-150">영구 채팅 서버를 배포 하기로 결정 한 경우 조직의 비즈니스 요구 사항을 결정 한 다음 비즈니스 요구를 지원 하기 위해 토폴로지, 인프라, 기술 요구 사항을 정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="168b4-150">If you decide to deploy Persistent Chat Server, you'll need to determine your organization's business requirements, then define the topology, infrastructure, and technical requirements to support your business needs.</span></span> <span data-ttu-id="168b4-151">배포를 최적화 하려면 다음 질문에 답변해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="168b4-151">To optimize your deployment, you'll need to answer the following questions:</span></span>
  
- <span data-ttu-id="168b4-152">이전 버전의 그룹 채팅 서버나 영구 채팅 서버의 이전 버전에서 마이그레이션하는 경우 또는 처음으로 영구 채팅 서버를 배포 하는 경우</span><span class="sxs-lookup"><span data-stu-id="168b4-152">Are you migrating from a previous version of Group Chat Server, or a previous version of Persistent Chat Server, or are you deploying Persistent Chat Server for the first time?</span></span>
    
- <span data-ttu-id="168b4-153">영구 채팅 서버는 누가 사용할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="168b4-153">Who can use Persistent Chat Server?</span></span> <span data-ttu-id="168b4-154">전역, 사이트 또는 사용자 수준에서 사용자 액세스를 결정 하는 영구 채팅 정책을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="168b4-154">You specify Persistent Chat policies to determine user access at the global, site, or user level.</span></span>
    
- <span data-ttu-id="168b4-155">영구 채팅 서버에 액세스 해야 하는 사용자의 수는 몇 명 인가요?</span><span class="sxs-lookup"><span data-stu-id="168b4-155">How many users will require access to Persistent Chat Server?</span></span> <span data-ttu-id="168b4-156">영구 채팅 서버는 15만에서 제공 하는 사용자 (정책에 따라 설정) 및 최대 8만 동시 사용자를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="168b4-156">Persistent Chat Server supports 150,000 provisioned users (enabled by policy), and a maximum of 80,000 concurrent users.</span></span> <span data-ttu-id="168b4-157">단일 영구 채팅 서버는 2만 연결 된 사용자를 지원할 수 있으며, 단일 영구 채팅 서버 풀에는 동시에 연결 된 총 8만의 활성 서버를 최대 4 개까지 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="168b4-157">A single Persistent Chat Server can support 20,000 connected users, and a single Persistent Chat Server pool can have up to 4 active servers for a total of 80,000 concurrently connected users.</span></span>
    
- <span data-ttu-id="168b4-158">범위, 윤리적인 경계 및 액세스를 제어 하는 방법을 선택 하세요.</span><span class="sxs-lookup"><span data-stu-id="168b4-158">How do you want to control scopes, ethical boundaries, and access?</span></span> <span data-ttu-id="168b4-159">범주를 정의 하 여 이러한 경계를 분리 하 고 각 범주에서 만든 채팅방에 허용 되는 사람을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="168b4-159">You can define categories to segregate these boundaries, and choose who is allowed to be in rooms that are created in each of these categories.</span></span>
    
- <span data-ttu-id="168b4-160">방을 만들 수 있는 사용자를 제어 하는 방법을 선택 하세요.</span><span class="sxs-lookup"><span data-stu-id="168b4-160">How do you want to control who can create rooms?</span></span> <span data-ttu-id="168b4-161">회의실을 만들 수 있는 작성자를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="168b4-161">You can define creators who can create rooms.</span></span> <span data-ttu-id="168b4-162">작성자는 다른 구성원을 채팅방 관리자로 지정 하 여 채팅방을 지속적으로 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="168b4-162">Creators can assign other members as chat room managers for ongoing management of the rooms.</span></span>
    
- <span data-ttu-id="168b4-163">채팅방을 만들려는 방법을 선택 하세요.</span><span class="sxs-lookup"><span data-stu-id="168b4-163">How do you want to create rooms?</span></span> <span data-ttu-id="168b4-164">영구 채팅 서버는 회의실을 만들고 관리 하기 위한 웹 기반 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="168b4-164">Persistent Chat Server provides a web-based feature for creating and managing rooms.</span></span> <span data-ttu-id="168b4-165">이는 비즈니스용 Skype 클라이언트에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="168b4-165">This can be launched from the Skype for Business client.</span></span> <span data-ttu-id="168b4-166">비즈니스 요구 사항 및 워크플로를 구현 하는 고객 솔루션을 정의 하 고 사용자를 사용자 지정 솔루션으로 보내도록 영구 채팅 서버를 구성 하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="168b4-166">You can choose to define a customer solution that implements your business requirements and workflows, and configures Persistent Chat Server to direct users to your custom solution.</span></span>
    
- <span data-ttu-id="168b4-167">프로 비전 할 추가 기능의 종류</span><span class="sxs-lookup"><span data-stu-id="168b4-167">What kind of add-ins do you want to provision?</span></span> <span data-ttu-id="168b4-168">추가 기능을 통해 비즈니스용 Skype 클라이언트의 확장성 창을 활용 하 여 채팅방과 관련 된 컨텍스트를 제공 함으로써 채팅방의 경험을 향상 시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="168b4-168">Add-ins enhance the in-room experience by leveraging the extensibility pane in the Skype for Business client to provide context that is relevant to the room.</span></span> <span data-ttu-id="168b4-169">가장 유용 하 게 사용할 수 있는 일반 추가 기능 (예: 회사 웹 사이트, 내부 공동 작업 문서 등)을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="168b4-169">You can choose what general add-ins might be most useful (for example, your company website, internal collaboration documents, and so on).</span></span> <span data-ttu-id="168b4-170">채팅방 관리자는 등록 된 추가 기능 중 하나를 선택 하 여 원하는 경우 해당 채팅방과 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="168b4-170">Chat room managers can choose one of the registered add-ins and associate it with their rooms, if desired.</span></span> 
    
- <span data-ttu-id="168b4-171">어떤 종류의 고가용성 및 재해 복구 요구 사항이 있나요?</span><span class="sxs-lookup"><span data-stu-id="168b4-171">What kind of high availability and disaster recovery requirements do you have?</span></span> <span data-ttu-id="168b4-172">영구 채팅 서버는 고가용성을 위해 SQL Server 미러링 및 SQL Server 클러스터링을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="168b4-172">Persistent Chat Server supports SQL Server mirroring and SQL Server clustering for high availability.</span></span> <span data-ttu-id="168b4-173">재난 복구의 경우 영구 채팅 서버는 SQL Server 로그 전달을 사용 하는 스트레치 된 풀에서 최대 8 대의 서버 (4 개의 활성 및 4 대기)를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="168b4-173">For disaster recovery, Persistent Chat Server supports up to 8 servers (4 active and 4 standby) in a stretched pool with SQL Server log shipping.</span></span> 
    
- <span data-ttu-id="168b4-174">규정 요구 사항이 있나요?</span><span class="sxs-lookup"><span data-stu-id="168b4-174">Are there regulatory requirements?</span></span> <span data-ttu-id="168b4-175">회사가 해당 국가에 데이터를 보관 해야 하는 국가나 지역에 있는 경우에는 각 지역에 대해 지역별로 여러 영구 채팅 서버 풀을 배포 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="168b4-175">If your company is in a country or region where data needs to be kept within the country, you may need to deploy multiple Persistent Chat Server pools, each local to a specific geography.</span></span> <span data-ttu-id="168b4-176">룸, 범주 또는 추가 기능은 풀에 걸쳐 있지 않으며, 하나의 영구 채팅 서버 풀에만 속합니다.</span><span class="sxs-lookup"><span data-stu-id="168b4-176">A room, category, or add-in does not span pools--it belongs to only one Persistent Chat Server pool.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="168b4-177">여러 영구 채팅 서버 풀을 사용 하는 것이 더 이상 제공 되지 않습니다 (모든 영구 채팅 서버 풀에는 8만 동시 사용자만 있을 수 있음).</span><span class="sxs-lookup"><span data-stu-id="168b4-177">Having multiple Persistent Chat Server pools does not give you more scale (you can still have only 80,000 concurrent users across all your Persistent Chat Server pools).</span></span> <span data-ttu-id="168b4-178">여러 영구 채팅 서버 풀을 지 원하는 주요 이유는 규정 관련 사항을 지원 하기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="168b4-178">The primary reason for supporting multiple Persistent Chat Server pools is to support regulatory concerns.</span></span> 
  
## <a name="for-more-information"></a><span data-ttu-id="168b4-179">자세한 내용은</span><span class="sxs-lookup"><span data-stu-id="168b4-179">For more information</span></span>

<span data-ttu-id="168b4-180">영구 채팅 서버를 설치 하 고 구성 하는 방법에 대 한 자세한 내용은 다음 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="168b4-180">For more information about installing and configuring Persistent Chat Server, see the following topics:</span></span>
  
- <span data-ttu-id="168b4-181">영구 채팅 서버를 배포 하는 방법에 대 한 자세한 내용은 비즈니스용 [Skype 서버 2015에서 영구 채팅 서버 배포](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="168b4-181">For details about how to deploy Persistent Chat Server, see [Deploy Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md).</span></span> 
    
- <span data-ttu-id="168b4-182">영구 채팅 서버 배포에서 설정을 구성 하는 방법에 대 한 자세한 내용은 비즈니스용 [Skype 서버 2015에서 영구 채팅 서버 관리](../../manage/persistent-chat/persistent-chat.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="168b4-182">For details about how to configure settings on your Persistent Chat Server deployment, see [Manage Persistent Chat Server in Skype for Business Server 2015](../../manage/persistent-chat/persistent-chat.md).</span></span>
    

