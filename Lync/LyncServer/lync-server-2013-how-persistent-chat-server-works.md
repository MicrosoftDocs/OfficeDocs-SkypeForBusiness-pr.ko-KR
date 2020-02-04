---
title: 'Lync Server 2013: 영구 채팅 서버 작동 방식'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: How Persistent Chat Server works
ms:assetid: 3d04e9a1-3f0c-458e-bcbe-d27c8c464276
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ683096(v=OCS.15)
ms:contentKeyID: 49684643
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 692f9a40bc2c0fd885fc251a4a792d480a69c57d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722398"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="how-persistent-chat-server-works-in-lync-server-2013"></a><span data-ttu-id="b8c18-102">Lync Server 2013에서 영구 채팅 서버가 작동 하는 방식</span><span class="sxs-lookup"><span data-stu-id="b8c18-102">How Persistent Chat Server works in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b8c18-103">_**마지막으로 수정한 주제:** 2012-11-21_</span><span class="sxs-lookup"><span data-stu-id="b8c18-103">_**Topic Last Modified:** 2012-11-21_</span></span>

<span data-ttu-id="b8c18-104">Lync Server 2013, 영구 채팅 서버를 사용 하면 시간에 따라 유지 되는 단체의 토픽 기반 대화에 참여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8c18-104">Lync Server 2013, Persistent Chat Server enables you to participate in multiparty, topic-based conversations that persist over time.</span></span> <span data-ttu-id="b8c18-105">영구 채팅 서버는 조직에서 다음을 수행할 수 있도록 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8c18-105">Persistent Chat Server can help your organization do the following:</span></span>

  - <span data-ttu-id="b8c18-106">지리적으로 분산 된 팀과 부서간 업무 흐름도 간의 의사 소통 개선</span><span class="sxs-lookup"><span data-stu-id="b8c18-106">Improve communication between geographically dispersed and cross-functional teams</span></span>

  - <span data-ttu-id="b8c18-107">정보 인식 및 참가</span><span class="sxs-lookup"><span data-stu-id="b8c18-107">Broaden information awareness and participation</span></span>

  - <span data-ttu-id="b8c18-108">확장 된 조직과의 통신 개선</span><span class="sxs-lookup"><span data-stu-id="b8c18-108">Improve communication with your extended organization</span></span>

  - <span data-ttu-id="b8c18-109">정보 오버 로드 줄이기</span><span class="sxs-lookup"><span data-stu-id="b8c18-109">Reduce information overload</span></span>

  - <span data-ttu-id="b8c18-110">정보 인식 향상</span><span class="sxs-lookup"><span data-stu-id="b8c18-110">Improve information awareness</span></span>

  - <span data-ttu-id="b8c18-111">중요 한 지식 및 정보의 dispersion 증가</span><span class="sxs-lookup"><span data-stu-id="b8c18-111">Increase dispersion of important knowledge and information</span></span>

<span data-ttu-id="b8c18-112">Lync Server 2013에서 영구 채팅 서버를 선택적 역할로 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8c18-112">You can deploy Persistent Chat Server as an optional role with Lync Server 2013.</span></span> <span data-ttu-id="b8c18-113">영구 채팅 서비스는 전용 풀에서 실행 되며 영구 채팅 서버 풀은 메시지를 라우팅하는 Lync Server 풀에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="b8c18-113">Persistent Chat services run on a dedicated pool, and a Persistent Chat Server pool depends on a Lync Server pool to route messages to it.</span></span> <span data-ttu-id="b8c18-114">클라이언트는 SIP (XCCOS)를 통해 확장 가능한 채팅 통신을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8c18-114">Clients use eXtensible Chat Communication Over SIP (XCCOS).</span></span> <span data-ttu-id="b8c18-115">Lync Server 프런트 엔드 서버는 트래픽을 영구 채팅 서버 풀로 라우팅하도록 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8c18-115">The Lync Server Front End Servers are configured to route the traffic to a Persistent Chat Server pool.</span></span>

<div>

## <a name="high-level-architecture"></a><span data-ttu-id="b8c18-116">상위 수준 아키텍처</span><span class="sxs-lookup"><span data-stu-id="b8c18-116">High-Level Architecture</span></span>

<span data-ttu-id="b8c18-117">다음 다이어그램은 영구 채팅 서버 아키텍처 및 서비스의 상위 수준 큐브 뷰를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8c18-117">The following diagrams provide high-level perspectives of the Persistent Chat Server architecture and services.</span></span>

<span data-ttu-id="b8c18-118">**영구 채팅 서버 상위 수준 아키텍처**</span><span class="sxs-lookup"><span data-stu-id="b8c18-118">**Persistent Chat Server High-Level Architecture**</span></span>

<span data-ttu-id="b8c18-119">![영구 채팅 서버 아키텍처.](images/JJ683096.5db6f36f-4461-4d87-ba77-463b7ffe609b(OCS.15).jpg "영구 채팅 서버 아키텍처.")</span><span class="sxs-lookup"><span data-stu-id="b8c18-119">![Persistent Chat Server architecture.](images/JJ683096.5db6f36f-4461-4d87-ba77-463b7ffe609b(OCS.15).jpg "Persistent Chat Server architecture.")</span></span>

<span data-ttu-id="b8c18-120">**영구 채팅 서버 상위 수준 서비스**</span><span class="sxs-lookup"><span data-stu-id="b8c18-120">**Persistent Chat Server High-Level Services**</span></span>

<span data-ttu-id="b8c18-121">![영구 채팅 서버 구성 요소.](images/JJ683096.b6d743aa-3a86-4081-aaef-4fe3257db4e7(OCS.15).jpg "영구 채팅 서버 구성 요소.")</span><span class="sxs-lookup"><span data-stu-id="b8c18-121">![Persistent Chat Server components.](images/JJ683096.b6d743aa-3a86-4081-aaef-4fe3257db4e7(OCS.15).jpg "Persistent Chat Server components.")</span></span>

<span data-ttu-id="b8c18-122">영구 채팅 서버 프런트 엔드 서버에서 실행 되는 서비스에는 다음 두 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8c18-122">Two services run on the Persistent Chat Server Front End Servers:</span></span>

  - <span data-ttu-id="b8c18-123">영구 채팅 (채널)</span><span class="sxs-lookup"><span data-stu-id="b8c18-123">Persistent Chat (Channel)</span></span>

  - <span data-ttu-id="b8c18-124">충족</span><span class="sxs-lookup"><span data-stu-id="b8c18-124">Compliance</span></span>

<div>

## <a name="persistent-chat-channel-service"></a><span data-ttu-id="b8c18-125">영구 채팅 (채널) 서비스</span><span class="sxs-lookup"><span data-stu-id="b8c18-125">Persistent Chat (Channel) Service</span></span>

<span data-ttu-id="b8c18-126">영구 채팅 (채널) 서비스는 영구 채팅 서버를 담당 하는 핵심 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="b8c18-126">The Persistent Chat (Channel) service is the core service responsible for Persistent Chat Server.</span></span> <span data-ttu-id="b8c18-127">이 서비스는 다음 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8c18-127">This service provides the following functions:</span></span>

  - <span data-ttu-id="b8c18-128">받는 메시지 수락</span><span class="sxs-lookup"><span data-stu-id="b8c18-128">Accepts incoming messages</span></span>

  - <span data-ttu-id="b8c18-129">영구 채팅방 내에서 온라인 참가자를 등록 하 고 나열 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8c18-129">Registers and lists online participants within a Persistent Chat room</span></span>

  - <span data-ttu-id="b8c18-130">다른 채널 등록자에 게 메시지 재전송</span><span class="sxs-lookup"><span data-stu-id="b8c18-130">Retransmits messages to other channel subscribers</span></span>

  - <span data-ttu-id="b8c18-131">채널 관리, 채팅방 초대, 검색, 새 콘텐츠 알림에 대 한 논리를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8c18-131">Implements logic for channel management, chat room invitation, search, and new content notifications</span></span>

<span data-ttu-id="b8c18-132">영구 채팅 (채널) 서비스는 영구 채팅 저장소를 사용 하 여 채팅방 콘텐츠 및 기타 시스템 메타 데이터 (권한 부여 규칙 등)를 저장 하 고 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8c18-132">The Persistent Chat (Channel) service stores and accesses chat room content and other system metadata (authorization rules, and so on) by using the Persistent Chat Store.</span></span> <span data-ttu-id="b8c18-133">이 서비스는 영구 채팅 파일 저장소의 채팅방에 업로드 된 파일을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8c18-133">This service stores files that are uploaded into chat rooms in the Persistent Chat File Store.</span></span>

</div>

<div>

## <a name="compliance-service"></a><span data-ttu-id="b8c18-134">준수 서비스</span><span class="sxs-lookup"><span data-stu-id="b8c18-134">Compliance Service</span></span>

<span data-ttu-id="b8c18-135">준수 서비스는 영구 채팅 서버의 선택적 구성 요소 이며, 영구적 채팅 준수 저장소에 채팅 콘텐츠 및 이벤트를 보관 하는 책임을 집니다.</span><span class="sxs-lookup"><span data-stu-id="b8c18-135">The Compliance service is an optional component of Persistent Chat Server and is responsible for archiving chat content and events to the Persistent Chat Compliance Store.</span></span> <span data-ttu-id="b8c18-136">조직에 영구 채팅 활동을 보관 해야 하는 규정이 있는 경우 선택적 영구 채팅 준수 서비스를 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8c18-136">If your organization has regulations that require Persistent Chat activity to be archived, you can deploy the optional Persistent Chat Compliance service.</span></span> <span data-ttu-id="b8c18-137">준수 서비스는 영구 채팅 풀의 각 영구 채팅 서버에 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8c18-137">The Compliance service is installed on each Persistent Chat Server in a Persistent Chat pool.</span></span> <span data-ttu-id="b8c18-138">이 구성을 사용 하는 경우 영구 채팅 서버 준수는 채팅방 참가 및 종료와 같은 사용자 활동을 기록 하 고 메시지를 게시 하 고 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="b8c18-138">When configured, Persistent Chat Server compliance records user activity such as joining and leaving rooms, and posting and reading of messages.</span></span> <span data-ttu-id="b8c18-139">준수 서비스는 영구 채팅 준수 파일 저장소에 보관 되어야 하는 파일을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8c18-139">The Compliance service stores files that need to be archived in the Persistent Chat Compliance File Store.</span></span>

</div>

<div>

## <a name="persistent-chat-web-services"></a><span data-ttu-id="b8c18-140">영구 채팅 웹 서비스</span><span class="sxs-lookup"><span data-stu-id="b8c18-140">Persistent Chat Web Services</span></span>

<span data-ttu-id="b8c18-141">Lync Server 프런트 엔드 서버에는 IIS (인터넷 정보 서비스)에 종속 되 고 웹 구성 요소로 구현 되는 두 가지 서비스가 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8c18-141">On the Lync Server Front End Servers, two services run that depend on Internet Information Services (IIS), and are implemented as web components:</span></span>

  - <span data-ttu-id="b8c18-142">**파일 업로드/다운로드를 위한 영구 채팅 웹 서비스** 채팅방에서 파일을 게시 하 고 검색 하는 책임을 집니다.</span><span class="sxs-lookup"><span data-stu-id="b8c18-142">**Persistent Chat Web Services for File Upload/Download** Responsible for posting and retrieving files from chat rooms.</span></span>

  - <span data-ttu-id="b8c18-143">**채팅방 관리를 위한 영구 채팅 웹 서비스** 사용자에 게 채팅방을 관리 하 고 새 채팅방을 만들 수 있는 기능을 제공할 책임이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8c18-143">**Persistent Chat Web Services for Chat Room Management** Responsible for providing users the ability to manage their chat rooms, and create new chat rooms.</span></span>

</div>

</div>

<div>

## <a name="how-do-i-start-using-persistent-chat-server"></a><span data-ttu-id="b8c18-144">영구 채팅 서버 사용을 시작 하려면 어떻게 하나요?</span><span class="sxs-lookup"><span data-stu-id="b8c18-144">How Do I Start Using Persistent Chat Server?</span></span>

<span data-ttu-id="b8c18-145">영구 채팅 서버는 Lync Server 2013 인프라 내의 선택적 서버 역할입니다.</span><span class="sxs-lookup"><span data-stu-id="b8c18-145">Persistent Chat Server is an optional server role within the Lync Server 2013 infrastructure.</span></span> <span data-ttu-id="b8c18-146">영구 채팅 서버 역할을 설치 하는 경우 관리자가 정책을 통해 설정한 모든 사용자가 Lync 2013 클라이언트와 영구 채팅을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8c18-146">If you install the Persistent Chat Server role, any users who have been enabled through policy by an administrator can use Persistent Chat with the Lync 2013 client.</span></span>

<span data-ttu-id="b8c18-147">영구 채팅 서버를 배포 하 고 사용자가 정책에 따라 기능을 활용할 수 있도록 하는 방법에 대 한 자세한 내용은 [Lync server 2013에서 영구 채팅 서버 배포](lync-server-2013-deploying-persistent-chat-server.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b8c18-147">For details about how to deploy Persistent Chat Server and enable users to leverage the capabilities by policy, see [Deploying Persistent Chat Server in Lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md).</span></span>

<span data-ttu-id="b8c18-148">영구 채팅 서버 배포에서 설정을 구성 하는 방법에 대 한 자세한 내용은 [Lync server 2013에서 영구 채팅 서버 배포](lync-server-2013-deploying-persistent-chat-server.md) 및 [lync Server 2013, 영구 채팅 서버 관리](managing-lync-server-2013-persistent-chat-server.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b8c18-148">For details about how to configure settings on your Persistent Chat Server deployment, see [Deploying Persistent Chat Server in Lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md) and [Managing Lync Server 2013, Persistent Chat Server](managing-lync-server-2013-persistent-chat-server.md).</span></span>

<span data-ttu-id="b8c18-149">Lync 2013 클라이언트에서 영구 채팅 기능을 활용할 수 있도록 정책에서 사용자를 설정 하는 방법에 대 한 자세한 내용은 [Lync server 2013에서 영구 채팅 서버 배포](lync-server-2013-deploying-persistent-chat-server.md) 및 [lync Server 2013, 영구 채팅 서버 관리](managing-lync-server-2013-persistent-chat-server.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b8c18-149">For details about how to enable users by policy such that they can leverage Persistent Chat functionality in Lync 2013 client, see [Deploying Persistent Chat Server in Lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md) and [Managing Lync Server 2013, Persistent Chat Server](managing-lync-server-2013-persistent-chat-server.md).</span></span>

<span data-ttu-id="b8c18-150">영구 채팅 준수를 배포한 경우 준수를 위해 설정을 구성 하는 방법에 대 한 자세한 내용은 [Lync server 2013, 영구 채팅 서버 관리](managing-lync-server-2013-persistent-chat-server.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b8c18-150">If you deployed Persistent Chat compliance, see [Managing Lync Server 2013, Persistent Chat Server](managing-lync-server-2013-persistent-chat-server.md) for details about how to configure settings for compliance.</span></span>

</div>

<div>

## <a name="persistent-chat-call-flows"></a><span data-ttu-id="b8c18-151">영구 채팅 통화 흐름</span><span class="sxs-lookup"><span data-stu-id="b8c18-151">Persistent Chat Call Flows</span></span>

<span data-ttu-id="b8c18-152">영구 채팅 클라이언트는 XCCOS를 사용 하 여 영구 채팅 서비스와 통신 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8c18-152">The Persistent Chat client communicates with the Persistent Chat service by using XCCOS.</span></span> <span data-ttu-id="b8c18-153">다음 순서는 로그인 프로세스와 일반적인 대화방 구독 및 메시지 게시 시나리오를 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8c18-153">The following sequences describe the sign-in process and a typical room subscription and message post scenario.</span></span>

<div>

## <a name="sign-in"></a><span data-ttu-id="b8c18-154">로그인</span><span class="sxs-lookup"><span data-stu-id="b8c18-154">Sign-in</span></span>

<span data-ttu-id="b8c18-155">다음의 호출 흐름 다이어그램 및 단계에서 로그인 프로세스를 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8c18-155">The following call flow diagram and steps describe the sign-in process.</span></span>

<span data-ttu-id="b8c18-156">**영구 채팅 클라이언트 로그인 통화 흐름**</span><span class="sxs-lookup"><span data-stu-id="b8c18-156">**Persistent Chat Client Sign-in Call Flow**</span></span>

<span data-ttu-id="b8c18-157">![영구 채팅 서버 통화 흐름 다이어그램.](images/JJ683096.9b3b3c61-caca-42b6-853c-6a09e6ff5c44(OCS.15).jpg "영구 채팅 서버 통화 흐름 다이어그램.")</span><span class="sxs-lookup"><span data-stu-id="b8c18-157">![Persistent Chat Server call flow diagram.](images/JJ683096.9b3b3c61-caca-42b6-853c-6a09e6ff5c44(OCS.15).jpg "Persistent Chat Server call flow diagram.")</span></span>

1.  <span data-ttu-id="b8c18-158">영구 채팅 클라이언트는 먼저 서버에서 대역내 프로비저닝 문서를 검색 하기 위해 SIP 구독을 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="b8c18-158">The Persistent Chat client first sends a SIP SUBSCRIBE to retrieve the in-band provisioning document from the server.</span></span> <span data-ttu-id="b8c18-159">이 문서는 영구 채팅을 사용 하거나 사용 하지 않도록 설정 하 고 영구 채팅 서버 풀의 SIP Uri 목록에 대해 알려줍니다.</span><span class="sxs-lookup"><span data-stu-id="b8c18-159">This document indicates if Persistent Chat is enabled or disabled for the user and the list of SIP URIs for the Persistent Chat Server pool.</span></span>

2.  <span data-ttu-id="b8c18-160">영구 채팅 클라이언트는 이전 단계에서 받은 영구 채팅 서버의 SIP URI로 SIP 초대 메시지를 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="b8c18-160">The Persistent Chat client sends a SIP INVITE message to the SIP URI of the Persistent Chat Server that it obtained in the previous step.</span></span> <span data-ttu-id="b8c18-161">초대 순서에는 200 OK와 ACK가 나타나고 영구 채팅 클라이언트는 이제 영구 채팅 서버 끝점을 사용 하 여 SIP 세션을 열었습니다.</span><span class="sxs-lookup"><span data-stu-id="b8c18-161">The INVITE sequence is followed by 200 OK and ACK, and the Persistent Chat client has now opened a SIP session with a Persistent Chat Server endpoint.</span></span> <span data-ttu-id="b8c18-162">따라서 영구 채팅 클라이언트는 동작을 수행 하도록 서버를 요청 하는 채팅 메시지 또는 명령이 포함 된 SIP 정보 메시지를 전송 하 여 영구 채팅 서버와 통신 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8c18-162">Consequently, the Persistent Chat client communicates with Persistent Chat Server by sending SIP INFO messages that contain either chat messages or commands requesting the server to take an action.</span></span> <span data-ttu-id="b8c18-163">이러한 모든 메시지는 200 OK 또는 503 서비스를 사용할 수 없음 (즉, 서버 로드가 많은 경우)으로 승인 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8c18-163">All of these messages are acknowledged with either 200 OK or 503 Service Unavailable (that is, in the event of heavy server load).</span></span> <span data-ttu-id="b8c18-164">클라이언트가 503 응답을 수신 하는 경우에는 메시지를 다시 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8c18-164">If the client receives a 503 response, it will retry the message.</span></span> <span data-ttu-id="b8c18-165">이 예제에는 503 응답이 포함 되어 있지 않습니다. 서버에서 메시지 또는 명령을 수락 하 고 200 OK를 보내면 별도의 SIP 정보 메시지 형식으로 클라이언트에 대 한 응답을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8c18-165">(This example does not include a 503 response.) If the server accepts the message or command and sends 200 OK, it provides a response to the client in the form of a separate SIP INFO message.</span></span> <span data-ttu-id="b8c18-166">이 응답에는 원래 명령에 대 한 참조가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8c18-166">This response includes a reference to the originating command.</span></span>

3.  <span data-ttu-id="b8c18-167">영구 채팅 클라이언트는 XCCOS **getserverinfo** 명령이 포함 된 SIP 정보 메시지를 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="b8c18-167">The Persistent Chat client sends a SIP INFO message that contains the XCCOS **getserverinfo** command.</span></span> <span data-ttu-id="b8c18-168">영구 채팅 서버는 영구 채팅 서비스 구성에 대 한 정보를 포함 하는 새로운 SIP 정보 메시지를 사용 하 여 회신 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8c18-168">Persistent Chat Server replies with a new SIP INFO message that contains information about the Persistent Chat service configuration.</span></span>

4.  <span data-ttu-id="b8c18-169">영구 채팅 클라이언트는 XCCOS **getassociations** 명령을 포함 하는 SIP 정보 메시지를 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="b8c18-169">The Persistent Chat client sends a SIP INFO message that contains the XCCOS **getassociations** command.</span></span> <span data-ttu-id="b8c18-170">영구 채팅 서버는 사용자가 구성원으로 속해 있는 채팅방 목록을 포함 하는 새로운 SIP 정보 메시지를 사용 하 여 회신 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8c18-170">Persistent Chat Server replies with a new SIP INFO message that contains the list of rooms of which the user is a member.</span></span> <span data-ttu-id="b8c18-171">영구 채팅 클라이언트는 명령을 반복 하 여 사용자가 관리자로 속해 있는 채팅방 목록을 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8c18-171">The Persistent Chat client repeats the command to retrieve the list of rooms of which the user is a manager.</span></span>

5.  <span data-ttu-id="b8c18-172">영구 채팅 클라이언트는 "현재 상태" 문서에서 팔 로우 하는 채팅방 목록을 가져오며,이는 팔 로우 하는 각 채팅방이 "roomSetting" 범주로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8c18-172">The Persistent Chat client gets the list of followed rooms from the "presence" document, where each followed room is represented by a "roomSetting" category.</span></span> <span data-ttu-id="b8c18-173">팔 로우 하는 모든 채팅방은 대화방 uri 목록을 포함 하는 XCCOS **참여해 보세요** 명령을 포함 하는 단일 SIP 정보 메시지로 연결 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8c18-173">All followed rooms are joined by a single SIP INFO message that contains the XCCOS **bjoin** command that contains the list of room URIs.</span></span> <span data-ttu-id="b8c18-174">팔 로우 채팅방 목록이 서버에 저장 되므로 컴퓨터의 모든 클라이언트에는 지정 된 사용자 URI에 대해 팔 로우 하는 채팅방의 목록이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8c18-174">Because the list of followed rooms is kept on the server, any client on any computer has the same list of followed rooms for the specified user URI.</span></span> <span data-ttu-id="b8c18-175">또한 영구 채팅 클라이언트는 사용자가이 옵션을 사용 하도록 설정 된 경우 열려 있는 룸의 목록을 유지 하 고, 각 룸에 대 한 XCCOS **join** 명령이 포함 된 SIP 정보 메시지를 전송 하 여 로그인 할 때 각 채팅방에 참가 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8c18-175">The Persistent Chat client also keeps the list of opened rooms (if this option is enabled by the user) in the local computer registry, and joins each of these rooms at sign-in by sending a SIP INFO message that contains the XCCOS **join** command for each opened room.</span></span> <span data-ttu-id="b8c18-176">이 목록은 레지스트리에 유지 되므로 다른 컴퓨터에서 실행 되는 두 개의 영구 채팅 클라이언트에 따라 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8c18-176">Because this list is kept in the registry, it can be different on two Persistent Chat clients running on different computers.</span></span>

6.  <span data-ttu-id="b8c18-177">연결 된 각 채팅방에 대해 영구 채팅 클라이언트는 XCCOS **bccontext** 명령이 포함 된 SIP INFO 메시지를 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="b8c18-177">For each room joined, the Persistent Chat client sends a SIP INFO message that contains the XCCOS **bccontext** command.</span></span> <span data-ttu-id="b8c18-178">영구 채팅 서버는 채팅방에 최신 채팅 메시지가 포함 된 새로운 SIP 정보 메시지를 사용 하 여 회신 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8c18-178">Persistent Chat Server replies with a new SIP INFO message that contains the most recent chat message in the room.</span></span>

7.  <span data-ttu-id="b8c18-179">영구 채팅 클라이언트는 XCCOS **getinv** (즉, 초대 받기) 명령이 포함 된 SIP 정보 메시지를 보내 클라이언트가 아직 표시 하지 않은 새 채팅방 초대를 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8c18-179">The Persistent Chat client sends a SIP INFO message that contains a XCCOS **getinv** (that is, get invitation) command to request any new room invitations that the client has not yet seen.</span></span> <span data-ttu-id="b8c18-180">별도의 SIP 정보 메시지에서 영구 채팅 서버는 해당 룸의 목록을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8c18-180">In a separate SIP INFO message, Persistent Chat Server returns a list of those rooms.</span></span>

</div>

<div>

## <a name="subscribe-to-a-room-and-post-a-message"></a><span data-ttu-id="b8c18-181">채팅방에 가입 하 고 메시지 게시</span><span class="sxs-lookup"><span data-stu-id="b8c18-181">Subscribe to a Room and Post a Message</span></span>

<span data-ttu-id="b8c18-182">다음의 호출 흐름 다이어그램 및 단계에서는 일반적인 회의실 구독 및 메시지 게시 시나리오에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8c18-182">The following call flow diagram and steps describe a typical room subscription and message post scenario.</span></span>

<span data-ttu-id="b8c18-183">**영구 채팅 클라이언트 공간 구독 및 메시지 게시 통화 흐름**</span><span class="sxs-lookup"><span data-stu-id="b8c18-183">**Persistent Chat Client Room Subscription and Message Posting Call Flow**</span></span>

<span data-ttu-id="b8c18-184">![방 구독 및 메시지 게시 시나리오.](images/JJ683096.2d3c417e-c91b-42bd-964e-285b72bb2e44(OCS.15).jpg "방 구독 및 메시지 게시 시나리오.")</span><span class="sxs-lookup"><span data-stu-id="b8c18-184">![Room subscription and message post scenario.](images/JJ683096.2d3c417e-c91b-42bd-964e-285b72bb2e44(OCS.15).jpg "Room subscription and message post scenario.")</span></span>

1.  <span data-ttu-id="b8c18-185">영구 채팅 클라이언트에서 User1이 채팅방 **참가**를 클릭 하 고 **검색**을 클릭 한 다음 몇 가지 검색 조건을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8c18-185">From the Persistent Chat client, User1 clicks **Join a Chat Room**, clicks **Search**, and then enters some search criteria.</span></span> <span data-ttu-id="b8c18-186">영구 채팅 클라이언트는 검색 조건과 함께 XCCOS **chansrch** (room 검색) 명령이 포함 된 SIP 정보 메시지를 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="b8c18-186">The Persistent Chat client sends a SIP INFO message that contains the XCCOS **chansrch** (room search) command, along with the search criteria.</span></span> <span data-ttu-id="b8c18-187">영구 채팅 서버 백 엔드 데이터베이스를 쿼리하고 검색 조건을 충족 하는 사용 가능한 회의실 목록이 포함 된 새 SIP 정보 메시지에 회신 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8c18-187">Persistent Chat Server queries the back-end database and replies in a new SIP INFO message that contains a list of available rooms that meet the search criteria.</span></span>

2.  <span data-ttu-id="b8c18-188">User1이 자신이 참가 하려는 채팅방을 선택한 다음 **이 채팅방 팔 로우**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8c18-188">User1 selects the chat room that he or she wants to join, and then clicks **Follow this room**.</span></span> <span data-ttu-id="b8c18-189">영구 채팅 클라이언트는 XCCOS **join** 명령 및 사용자가 선택한 채팅방의 룸 ID가 포함 된 SIP INFO 메시지를 영구 채팅 서버에 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="b8c18-189">The Persistent Chat client sends Persistent Chat Server a SIP INFO message that contains the XCCOS **join** command and the room ID of the chat room that the user selected.</span></span> <span data-ttu-id="b8c18-190">영구 채팅 서버는 프로 비전 데이터를 포함 하는 SIP INFO 메시지와 함께 회신 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8c18-190">Persistent Chat Server replies with a SIP INFO message that contains the provisioning data.</span></span>

3.  <span data-ttu-id="b8c18-191">영구 채팅 클라이언트는 XCCOS **bccontext** (backchat context) 명령이 포함 된 SIP 정보 메시지를 영구 채팅 서버에 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="b8c18-191">The Persistent Chat client sends Persistent Chat Server a SIP INFO message that contains the XCCOS **bccontext** (backchat context) command.</span></span> <span data-ttu-id="b8c18-192">영구 채팅 서버 채팅 기록을 검색 하 고 별도의 SIP 정보 메시지에 있는 영구 채팅 클라이언트로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8c18-192">Persistent Chat Server retrieves the chat history, and returns it to the Persistent Chat client in a separate SIP INFO message.</span></span> <span data-ttu-id="b8c18-193">이 시점에서 사용자가 채팅방을 입력 하 고 참여할 준비가 된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b8c18-193">At this point, the user enters the chat room and is ready to participate.</span></span>

4.  <span data-ttu-id="b8c18-194">User1이 새 메시지를 입력 한 다음 **보내기를**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8c18-194">User1 enters a new message, and then clicks **Send**.</span></span> <span data-ttu-id="b8c18-195">영구 채팅 클라이언트가 SIP INFO XCCOS **grpchat** 명령으로 메시지를 채팅방에 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8c18-195">The Persistent Chat client posts the message to the chat room in a SIP INFO XCCOS **grpchat** command.</span></span> <span data-ttu-id="b8c18-196">영구 채팅 서버는 영구 채팅 백 엔드 데이터베이스에이 새 메시지의 복사본을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8c18-196">Persistent Chat Server stores a copy of this new message in the Persistent Chat back-end database.</span></span>

5.  <span data-ttu-id="b8c18-197">영구 채팅 서버는 이미 채팅방을 입력 한 **grpchat** 메시지의 별도 복사본을 XCCOS에 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="b8c18-197">Persistent Chat Server sends a separate copy of the SIP INFO XCCOS **grpchat** message to User2, who has already entered the chat room.</span></span>

</div>

</div>

<div>

## <a name="persistent-chat-compliance-call-flows"></a><span data-ttu-id="b8c18-198">영구 채팅 준수 통화 흐름</span><span class="sxs-lookup"><span data-stu-id="b8c18-198">Persistent Chat Compliance Call Flows</span></span>

<span data-ttu-id="b8c18-199">영구 채팅 서버는 메시지 대기열 (MSMQ 라고도 함) 및 준수 데이터를 처리 하는 추가 준수 데이터베이스 (mgccomp)를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8c18-199">Persistent Chat Server uses Message Queuing (also known as MSMQ) and an additional compliance database (mgccomp) to process compliance data.</span></span> <span data-ttu-id="b8c18-200">규정 준수 이벤트가 처리 되는 방법의 예로, 다음 이벤트 순서에 따라 메시지 게시 이벤트가 처리 되는 방법이 설명 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8c18-200">As an example of how compliance events are processed, the following sequence of events describes how a message post event is processed.</span></span>

1.  <span data-ttu-id="b8c18-201">사용자가 채팅방에 메시지를 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8c18-201">A user posts a message to a room.</span></span>

2.  <span data-ttu-id="b8c18-202">영구 채팅 서버는 개인 메시지 대기열 대기열에 이벤트와 관련 된 정보를 배치 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8c18-202">Persistent Chat Server places information pertaining to the event in a private Message Queuing queue.</span></span>

3.  <span data-ttu-id="b8c18-203">영구 채팅 준수 서버는 큐에서이 이벤트를 읽고 나중에 처리 하기 위해 mgccomp 데이터베이스에 배치 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8c18-203">Persistent Chat Compliance server reads this event from the queue, and places it into the mgccomp database for processing later.</span></span>

4.  <span data-ttu-id="b8c18-204">영구 채팅 준수 서버는 정기적으로 데이터베이스의 이벤트 집합을 처리 하 고이를 지속적인 채팅 준수 어댑터로 전송 하 여 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8c18-204">Periodically, the Persistent Chat Compliance server processes a set of events in the database, and sends them to the Persistent Chat Compliance adapter for processing.</span></span>

5.  <span data-ttu-id="b8c18-205">어댑터가 데이터를 성공적으로 처리 하는 경우 영구 채팅 준수 서버가 mgccomp 데이터베이스에서 이벤트를 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8c18-205">If the adapter successfully processes the data, Persistent Chat Compliance server deletes the events from the mgccomp database.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

