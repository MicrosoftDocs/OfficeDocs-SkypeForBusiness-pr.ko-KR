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
ms.openlocfilehash: c582ad9e21e111745dc55fd2d43feada761e58d9
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136215"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="how-persistent-chat-server-works-in-lync-server-2013"></a><span data-ttu-id="77386-102">Lync Server 2013에서 영구 채팅 서버가 작동 하는 방식</span><span class="sxs-lookup"><span data-stu-id="77386-102">How Persistent Chat Server works in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="77386-103">_**마지막으로 수정 된 항목:** 2012-11-21_</span><span class="sxs-lookup"><span data-stu-id="77386-103">_**Topic Last Modified:** 2012-11-21_</span></span>

<span data-ttu-id="77386-104">Lync Server 2013, 영구 채팅 서버를 사용 하면 시간이 지남에 따라 지속 되는 단체 및 토픽 기반 대화에 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77386-104">Lync Server 2013, Persistent Chat Server enables you to participate in multiparty, topic-based conversations that persist over time.</span></span> <span data-ttu-id="77386-105">영구 채팅 서버는 조직에서 다음을 수행 하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77386-105">Persistent Chat Server can help your organization do the following:</span></span>

  - <span data-ttu-id="77386-106">지리적으로 분산되고 업무가 연관된 팀 간의 통신을 향상시킵니다.</span><span class="sxs-lookup"><span data-stu-id="77386-106">Improve communication between geographically dispersed and cross-functional teams</span></span>

  - <span data-ttu-id="77386-107">보다 많은 구성원과 정보를 보다 많이 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77386-107">Broaden information awareness and participation</span></span>

  - <span data-ttu-id="77386-108">조직 내외부에서 광범위하게 정보를 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77386-108">Improve communication with your extended organization</span></span>

  - <span data-ttu-id="77386-109">효율적인 정보 공유로 정보 오버로드를 줄여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="77386-109">Reduce information overload</span></span>

  - <span data-ttu-id="77386-110">정보 인식을 향상시킵니다.</span><span class="sxs-lookup"><span data-stu-id="77386-110">Improve information awareness</span></span>

  - <span data-ttu-id="77386-111">중요한 지식과 정보의 배포를 향상시킵니다.</span><span class="sxs-lookup"><span data-stu-id="77386-111">Increase dispersion of important knowledge and information</span></span>

<span data-ttu-id="77386-112">선택적 역할로 Lync Server 2013를 사용 하 여 영구 채팅 서버를 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77386-112">You can deploy Persistent Chat Server as an optional role with Lync Server 2013.</span></span> <span data-ttu-id="77386-113">영구 채팅 서비스는 전용 풀에서 실행 되며 영구 채팅 서버 풀은 Lync Server 풀에 의존 하 여 메시지를 라우팅합니다.</span><span class="sxs-lookup"><span data-stu-id="77386-113">Persistent Chat services run on a dedicated pool, and a Persistent Chat Server pool depends on a Lync Server pool to route messages to it.</span></span> <span data-ttu-id="77386-114">클라이언트는 XCCOS(eXtensible Chat Communication Over SIP)를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="77386-114">Clients use eXtensible Chat Communication Over SIP (XCCOS).</span></span> <span data-ttu-id="77386-115">Lync Server 프런트 엔드 서버는 트래픽을 영구 채팅 서버 풀로 라우팅하도록 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="77386-115">The Lync Server Front End Servers are configured to route the traffic to a Persistent Chat Server pool.</span></span>

<div>

## <a name="high-level-architecture"></a><span data-ttu-id="77386-116">고급 아키텍처</span><span class="sxs-lookup"><span data-stu-id="77386-116">High-Level Architecture</span></span>

<span data-ttu-id="77386-117">다음 다이어그램에서는 영구 채팅 서버 아키텍처 및 서비스에 대 한 높은 수준의 관점을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="77386-117">The following diagrams provide high-level perspectives of the Persistent Chat Server architecture and services.</span></span>

<span data-ttu-id="77386-118">**영구 채팅 서버 고급 아키텍처**</span><span class="sxs-lookup"><span data-stu-id="77386-118">**Persistent Chat Server High-Level Architecture**</span></span>

<span data-ttu-id="77386-119">![영구 채팅 서버 아키텍처](images/JJ683096.5db6f36f-4461-4d87-ba77-463b7ffe609b(OCS.15).jpg "영구 채팅 서버 아키텍처")</span><span class="sxs-lookup"><span data-stu-id="77386-119">![Persistent Chat Server architecture.](images/JJ683096.5db6f36f-4461-4d87-ba77-463b7ffe609b(OCS.15).jpg "Persistent Chat Server architecture.")</span></span>

<span data-ttu-id="77386-120">**영구 채팅 서버 고급 서비스**</span><span class="sxs-lookup"><span data-stu-id="77386-120">**Persistent Chat Server High-Level Services**</span></span>

<span data-ttu-id="77386-121">![영구 채팅 서버 구성 요소](images/JJ683096.b6d743aa-3a86-4081-aaef-4fe3257db4e7(OCS.15).jpg "영구 채팅 서버 구성 요소")</span><span class="sxs-lookup"><span data-stu-id="77386-121">![Persistent Chat Server components.](images/JJ683096.b6d743aa-3a86-4081-aaef-4fe3257db4e7(OCS.15).jpg "Persistent Chat Server components.")</span></span>

<span data-ttu-id="77386-122">영구 채팅 서버 프런트 엔드 서버에서 실행 되는 서비스는 두 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77386-122">Two services run on the Persistent Chat Server Front End Servers:</span></span>

  - <span data-ttu-id="77386-123">영구 채팅(채널)</span><span class="sxs-lookup"><span data-stu-id="77386-123">Persistent Chat (Channel)</span></span>

  - <span data-ttu-id="77386-124">규정 준수</span><span class="sxs-lookup"><span data-stu-id="77386-124">Compliance</span></span>

<div>

## <a name="persistent-chat-channel-service"></a><span data-ttu-id="77386-125">영구 채팅(채널) 서비스</span><span class="sxs-lookup"><span data-stu-id="77386-125">Persistent Chat (Channel) Service</span></span>

<span data-ttu-id="77386-126">영구 채팅 (채널) 서비스는 영구 채팅 서버를 담당 하는 핵심 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="77386-126">The Persistent Chat (Channel) service is the core service responsible for Persistent Chat Server.</span></span> <span data-ttu-id="77386-127">이 서비스는 다음과 같은 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="77386-127">This service provides the following functions:</span></span>

  - <span data-ttu-id="77386-128">수신 메시지를 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="77386-128">Accepts incoming messages</span></span>

  - <span data-ttu-id="77386-129">영구 대화방 내에서 온라인 참가자 등록 및 목록 만들기</span><span class="sxs-lookup"><span data-stu-id="77386-129">Registers and lists online participants within a Persistent Chat room</span></span>

  - <span data-ttu-id="77386-130">다른 채널 구독자에게 메시지를 재전송합니다.</span><span class="sxs-lookup"><span data-stu-id="77386-130">Retransmits messages to other channel subscribers</span></span>

  - <span data-ttu-id="77386-131">채널 관리, 채팅방 초대, 검색 및 새 콘텐츠 알림을 위한 논리를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="77386-131">Implements logic for channel management, chat room invitation, search, and new content notifications</span></span>

<span data-ttu-id="77386-132">영구 채팅 (채널) 서비스는 영구 채팅 저장소를 사용 하 여 대화방 콘텐츠 및 기타 시스템 메타 데이터 (권한 부여 규칙 등)를 저장 하 고 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="77386-132">The Persistent Chat (Channel) service stores and accesses chat room content and other system metadata (authorization rules, and so on) by using the Persistent Chat Store.</span></span> <span data-ttu-id="77386-133">이 서비스는 대화방에 업로드 되는 파일을 영구 채팅 파일 저장소에 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="77386-133">This service stores files that are uploaded into chat rooms in the Persistent Chat File Store.</span></span>

</div>

<div>

## <a name="compliance-service"></a><span data-ttu-id="77386-134">준수 서비스</span><span class="sxs-lookup"><span data-stu-id="77386-134">Compliance Service</span></span>

<span data-ttu-id="77386-135">준수 서비스는 영구 채팅 서버의 선택적 구성 요소 이며 채팅 콘텐츠 및 이벤트를 영구 채팅 준수 저장소에 보관 하는 일을 담당 합니다.</span><span class="sxs-lookup"><span data-stu-id="77386-135">The Compliance service is an optional component of Persistent Chat Server and is responsible for archiving chat content and events to the Persistent Chat Compliance Store.</span></span> <span data-ttu-id="77386-136">조직에 영구 채팅 작업을 보관 해야 하는 규정이 있으면 선택적 영구 채팅 준수 서비스를 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77386-136">If your organization has regulations that require Persistent Chat activity to be archived, you can deploy the optional Persistent Chat Compliance service.</span></span> <span data-ttu-id="77386-137">준수 서비스는 영구 채팅 풀의 각 영구 채팅 서버에 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="77386-137">The Compliance service is installed on each Persistent Chat Server in a Persistent Chat pool.</span></span> <span data-ttu-id="77386-138">영구 채팅 서버 규정은 구성 된 경우 대화방 참가/탈퇴, 메시지 게시 및 읽기와 같은 사용자 활동을 기록 합니다.</span><span class="sxs-lookup"><span data-stu-id="77386-138">When configured, Persistent Chat Server compliance records user activity such as joining and leaving rooms, and posting and reading of messages.</span></span> <span data-ttu-id="77386-139">준수 서비스는 영구 채팅 준수 파일 저장소에 보관 해야 하는 파일을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="77386-139">The Compliance service stores files that need to be archived in the Persistent Chat Compliance File Store.</span></span>

</div>

<div>

## <a name="persistent-chat-web-services"></a><span data-ttu-id="77386-140">영구 채팅 웹 서비스</span><span class="sxs-lookup"><span data-stu-id="77386-140">Persistent Chat Web Services</span></span>

<span data-ttu-id="77386-141">Lync Server 프런트 엔드 서버에서 IIS (인터넷 정보 서비스)에 의존 하는 두 서비스를 실행 하며 웹 구성 요소로 구현 됩니다.</span><span class="sxs-lookup"><span data-stu-id="77386-141">On the Lync Server Front End Servers, two services run that depend on Internet Information Services (IIS), and are implemented as web components:</span></span>

  - <span data-ttu-id="77386-142">**파일 업로드/다운로드를 위한 영구 채팅 웹 서비스** 채팅방에서 파일을 게시 하 고 검색 하는 일을 담당 합니다.</span><span class="sxs-lookup"><span data-stu-id="77386-142">**Persistent Chat Web Services for File Upload/Download** Responsible for posting and retrieving files from chat rooms.</span></span>

  - <span data-ttu-id="77386-143">**채팅방 관리를 위한 영구 채팅 웹 서비스** 사용자에 게 대화방을 관리 하는 기능을 제공 하 고 새 채팅방을 만들 책임이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77386-143">**Persistent Chat Web Services for Chat Room Management** Responsible for providing users the ability to manage their chat rooms, and create new chat rooms.</span></span>

</div>

</div>

<div>

## <a name="how-do-i-start-using-persistent-chat-server"></a><span data-ttu-id="77386-144">영구 채팅 서버를 사용 하려면 어떻게 해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="77386-144">How Do I Start Using Persistent Chat Server?</span></span>

<span data-ttu-id="77386-145">영구 채팅 서버는 Lync Server 2013 인프라 내의 선택적 서버 역할입니다.</span><span class="sxs-lookup"><span data-stu-id="77386-145">Persistent Chat Server is an optional server role within the Lync Server 2013 infrastructure.</span></span> <span data-ttu-id="77386-146">영구 채팅 서버 역할을 설치 하는 경우 관리자가 정책을 통해 사용 하도록 설정한 모든 사용자가 Lync 2013 클라이언트와 영구 채팅을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77386-146">If you install the Persistent Chat Server role, any users who have been enabled through policy by an administrator can use Persistent Chat with the Lync 2013 client.</span></span>

<span data-ttu-id="77386-147">영구 채팅 서버를 배포 하 고 사용자가 정책에 따라 기능을 활용할 수 있도록 하는 방법에 대 한 자세한 내용은 [Lync server 2013에서 영구 채팅 서버 배포](lync-server-2013-deploying-persistent-chat-server.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="77386-147">For details about how to deploy Persistent Chat Server and enable users to leverage the capabilities by policy, see [Deploying Persistent Chat Server in Lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md).</span></span>

<span data-ttu-id="77386-148">영구 채팅 서버 배포에 대 한 설정을 구성 하는 방법에 대 한 자세한 내용은 [Lync server 2013의 영구 채팅 서버 배포](lync-server-2013-deploying-persistent-chat-server.md) 및 [lync Server 2013, 영구 채팅 서버 관리](managing-lync-server-2013-persistent-chat-server.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="77386-148">For details about how to configure settings on your Persistent Chat Server deployment, see [Deploying Persistent Chat Server in Lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md) and [Managing Lync Server 2013, Persistent Chat Server](managing-lync-server-2013-persistent-chat-server.md).</span></span>

<span data-ttu-id="77386-149">Lync 2013 클라이언트에서 영구 채팅 기능을 활용할 수 있도록 정책을 통해 사용자를 설정 하는 방법에 대 한 자세한 내용은 [Lync server 2013의 영구 채팅 서버 배포](lync-server-2013-deploying-persistent-chat-server.md) 및 [lync Server 2013, 영구 채팅 서버 관리](managing-lync-server-2013-persistent-chat-server.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="77386-149">For details about how to enable users by policy such that they can leverage Persistent Chat functionality in Lync 2013 client, see [Deploying Persistent Chat Server in Lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md) and [Managing Lync Server 2013, Persistent Chat Server](managing-lync-server-2013-persistent-chat-server.md).</span></span>

<span data-ttu-id="77386-150">영구 채팅 준수를 배포한 경우 규정 준수 설정을 구성 하는 방법에 대 한 자세한 내용은 [Lync Server 2013, 영구 채팅 서버 관리](managing-lync-server-2013-persistent-chat-server.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="77386-150">If you deployed Persistent Chat compliance, see [Managing Lync Server 2013, Persistent Chat Server](managing-lync-server-2013-persistent-chat-server.md) for details about how to configure settings for compliance.</span></span>

</div>

<div>

## <a name="persistent-chat-call-flows"></a><span data-ttu-id="77386-151">영구 채팅 호출 흐름</span><span class="sxs-lookup"><span data-stu-id="77386-151">Persistent Chat Call Flows</span></span>

<span data-ttu-id="77386-152">영구 채팅 클라이언트는 XCCOS을 사용 하 여 영구 채팅 서비스와 통신 합니다.</span><span class="sxs-lookup"><span data-stu-id="77386-152">The Persistent Chat client communicates with the Persistent Chat service by using XCCOS.</span></span> <span data-ttu-id="77386-153">다음 시퀀스에서는 로그인 프로세스와 일반적인 방 구독 및 메시지 게시 시나리오에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="77386-153">The following sequences describe the sign-in process and a typical room subscription and message post scenario.</span></span>

<div>

## <a name="sign-in"></a><span data-ttu-id="77386-154">로그인</span><span class="sxs-lookup"><span data-stu-id="77386-154">Sign-in</span></span>

<span data-ttu-id="77386-155">다음 통화 흐름 다이어그램 및 단계에서는 로그인 프로세스에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="77386-155">The following call flow diagram and steps describe the sign-in process.</span></span>

<span data-ttu-id="77386-156">**영구 채팅 클라이언트 로그인 통화 흐름**</span><span class="sxs-lookup"><span data-stu-id="77386-156">**Persistent Chat Client Sign-in Call Flow**</span></span>

<span data-ttu-id="77386-157">![영구 채팅 서버 통화 흐름 다이어그램](images/JJ683096.9b3b3c61-caca-42b6-853c-6a09e6ff5c44(OCS.15).jpg "영구 채팅 서버 통화 흐름 다이어그램")</span><span class="sxs-lookup"><span data-stu-id="77386-157">![Persistent Chat Server call flow diagram.](images/JJ683096.9b3b3c61-caca-42b6-853c-6a09e6ff5c44(OCS.15).jpg "Persistent Chat Server call flow diagram.")</span></span>

1.  <span data-ttu-id="77386-158">영구 채팅 클라이언트는 먼저 SIP 구독을 보내 대역내 프로 비전 문서를 서버에서 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="77386-158">The Persistent Chat client first sends a SIP SUBSCRIBE to retrieve the in-band provisioning document from the server.</span></span> <span data-ttu-id="77386-159">이 문서는 영구 채팅 서버 풀의 SIP Uri 목록 및 사용자에 대해 영구 채트를 사용 하거나 사용 하지 않도록 설정할지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="77386-159">This document indicates if Persistent Chat is enabled or disabled for the user and the list of SIP URIs for the Persistent Chat Server pool.</span></span>

2.  <span data-ttu-id="77386-160">영구 채팅 클라이언트에서 이전 단계에서 얻은 영구 채팅 서버의 SIP URI로 SIP 초대 메시지를 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="77386-160">The Persistent Chat client sends a SIP INVITE message to the SIP URI of the Persistent Chat Server that it obtained in the previous step.</span></span> <span data-ttu-id="77386-161">초대 시퀀스에는 200 OK와 ACK가 오고, 영구 채팅 클라이언트는 이제 영구 채팅 서버 끝점을 사용 하 여 SIP 세션을 열었습니다.</span><span class="sxs-lookup"><span data-stu-id="77386-161">The INVITE sequence is followed by 200 OK and ACK, and the Persistent Chat client has now opened a SIP session with a Persistent Chat Server endpoint.</span></span> <span data-ttu-id="77386-162">따라서 영구 채팅 클라이언트는 동작을 수행 하도록 서버를 요청 하는 채팅 메시지 또는 명령이 포함 된 SIP INFO 메시지를 보내 영구 채팅 서버와 통신 합니다.</span><span class="sxs-lookup"><span data-stu-id="77386-162">Consequently, the Persistent Chat client communicates with Persistent Chat Server by sending SIP INFO messages that contain either chat messages or commands requesting the server to take an action.</span></span> <span data-ttu-id="77386-163">이러한 모든 메시지는 200 OK 또는 503 Service Unavailable(즉, 서버 부하가 심한 경우) 메시지로 응답됩니다.</span><span class="sxs-lookup"><span data-stu-id="77386-163">All of these messages are acknowledged with either 200 OK or 503 Service Unavailable (that is, in the event of heavy server load).</span></span> <span data-ttu-id="77386-164">클라이언트에 503 응답이 수신되면 메시지를 재시도합니다.</span><span class="sxs-lookup"><span data-stu-id="77386-164">If the client receives a 503 response, it will retry the message.</span></span> <span data-ttu-id="77386-165">(이 예에는 503 응답은 포함 되지 않습니다.) 서버에서 메시지 또는 명령을 수락 하 고 200 OK를 보내면 별도의 SIP 정보 메시지 형식으로 클라이언트에 대 한 응답을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="77386-165">(This example does not include a 503 response.) If the server accepts the message or command and sends 200 OK, it provides a response to the client in the form of a separate SIP INFO message.</span></span> <span data-ttu-id="77386-166">이 응답에는 원래 명령에 대한 참조가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="77386-166">This response includes a reference to the originating command.</span></span>

3.  <span data-ttu-id="77386-167">영구 채팅 클라이언트는 XCCOS **getserverinfo** 명령이 포함 된 SIP INFO 메시지를 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="77386-167">The Persistent Chat client sends a SIP INFO message that contains the XCCOS **getserverinfo** command.</span></span> <span data-ttu-id="77386-168">영구 채팅 서버는 영구 채팅 서비스 구성에 대 한 정보가 포함 된 새로운 SIP 정보 메시지를 사용 하 여 회신 합니다.</span><span class="sxs-lookup"><span data-stu-id="77386-168">Persistent Chat Server replies with a new SIP INFO message that contains information about the Persistent Chat service configuration.</span></span>

4.  <span data-ttu-id="77386-169">영구 채팅 클라이언트는 XCCOS **getassociations** 명령을 포함 하는 SIP INFO 메시지를 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="77386-169">The Persistent Chat client sends a SIP INFO message that contains the XCCOS **getassociations** command.</span></span> <span data-ttu-id="77386-170">영구 채팅 서버가 사용자가 구성원 인 대화방 목록을 포함 하는 새 SIP 정보 메시지를 사용 하 여 회신 합니다.</span><span class="sxs-lookup"><span data-stu-id="77386-170">Persistent Chat Server replies with a new SIP INFO message that contains the list of rooms of which the user is a member.</span></span> <span data-ttu-id="77386-171">영구 채팅 클라이언트에서 명령을 반복 하 여 사용자가 관리자 인 대화방 목록을 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="77386-171">The Persistent Chat client repeats the command to retrieve the list of rooms of which the user is a manager.</span></span>

5.  <span data-ttu-id="77386-172">영구 채팅 클라이언트는 "현재 상태" 문서에서 팔 로우 한 대화방 목록을 가져오고, 각 팔 로우 하는 대화방은 "roomSetting" 범주로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="77386-172">The Persistent Chat client gets the list of followed rooms from the "presence" document, where each followed room is represented by a "roomSetting" category.</span></span> <span data-ttu-id="77386-173">모든 팔 로우 된 대화방은 대화방 Uri 목록을 포함 하는 XCCOS **bjoin** 명령을 포함 하는 단일 SIP 정보 메시지에 의해 조인 됩니다.</span><span class="sxs-lookup"><span data-stu-id="77386-173">All followed rooms are joined by a single SIP INFO message that contains the XCCOS **bjoin** command that contains the list of room URIs.</span></span> <span data-ttu-id="77386-174">팔 로우 대화방 목록이 서버에 보관 되기 때문에 컴퓨터의 모든 클라이언트는 지정 된 사용자 URI에 대해 같은 팔 로우 대화방 목록을 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="77386-174">Because the list of followed rooms is kept on the server, any client on any computer has the same list of followed rooms for the specified user URI.</span></span> <span data-ttu-id="77386-175">또한 영구 채팅 클라이언트는 로컬 컴퓨터 레지스트리의 열린 대화방 목록 (사용자가이 옵션을 사용 하도록 설정한 경우)을 유지 하 고 각 대화방에 대 한 XCCOS **join** 명령이 포함 된 SIP INFO 메시지를 전송 하 여 로그인 시 이러한 각 채팅방에 참가 합니다.</span><span class="sxs-lookup"><span data-stu-id="77386-175">The Persistent Chat client also keeps the list of opened rooms (if this option is enabled by the user) in the local computer registry, and joins each of these rooms at sign-in by sending a SIP INFO message that contains the XCCOS **join** command for each opened room.</span></span> <span data-ttu-id="77386-176">이 목록은 레지스트리에 보관 되므로 서로 다른 컴퓨터에서 실행 되는 두 개의 영구 채팅 클라이언트 마다 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77386-176">Because this list is kept in the registry, it can be different on two Persistent Chat clients running on different computers.</span></span>

6.  <span data-ttu-id="77386-177">연결 된 각 대화방에 대해 영구 채팅 클라이언트는 XCCOS **bccontext** 명령이 포함 된 SIP INFO 메시지를 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="77386-177">For each room joined, the Persistent Chat client sends a SIP INFO message that contains the XCCOS **bccontext** command.</span></span> <span data-ttu-id="77386-178">영구 채팅 서버가 대화방에 최신 채팅 메시지를 포함 하는 새 SIP 정보 메시지를 사용 하 여 회신 합니다.</span><span class="sxs-lookup"><span data-stu-id="77386-178">Persistent Chat Server replies with a new SIP INFO message that contains the most recent chat message in the room.</span></span>

7.  <span data-ttu-id="77386-179">영구 채팅 클라이언트는 XCCOS **getinv** (즉, 초대 받기) 명령을 포함 하는 SIP INFO 메시지를 보내 클라이언트가 아직 확인 되지 않은 새 대화방 초대를 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="77386-179">The Persistent Chat client sends a SIP INFO message that contains a XCCOS **getinv** (that is, get invitation) command to request any new room invitations that the client has not yet seen.</span></span> <span data-ttu-id="77386-180">별도의 SIP 정보 메시지에서 영구 채팅 서버는 이러한 대화방의 목록을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="77386-180">In a separate SIP INFO message, Persistent Chat Server returns a list of those rooms.</span></span>

</div>

<div>

## <a name="subscribe-to-a-room-and-post-a-message"></a><span data-ttu-id="77386-181">방 구독 및 메시지 게시</span><span class="sxs-lookup"><span data-stu-id="77386-181">Subscribe to a Room and Post a Message</span></span>

<span data-ttu-id="77386-182">다음 통화 흐름 다이어그램 및 단계에서는 일반적인 대화방 구독 및 메시지 게시 시나리오에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="77386-182">The following call flow diagram and steps describe a typical room subscription and message post scenario.</span></span>

<span data-ttu-id="77386-183">**영구 채팅 클라이언트 대화방 구독 및 메시지 게시 호출 흐름**</span><span class="sxs-lookup"><span data-stu-id="77386-183">**Persistent Chat Client Room Subscription and Message Posting Call Flow**</span></span>

<span data-ttu-id="77386-184">![대화방 구독 및 메시지 게시 시나리오](images/JJ683096.2d3c417e-c91b-42bd-964e-285b72bb2e44(OCS.15).jpg "대화방 구독 및 메시지 게시 시나리오")</span><span class="sxs-lookup"><span data-stu-id="77386-184">![Room subscription and message post scenario.](images/JJ683096.2d3c417e-c91b-42bd-964e-285b72bb2e44(OCS.15).jpg "Room subscription and message post scenario.")</span></span>

1.  <span data-ttu-id="77386-185">영구 채팅 클라이언트에서 User1이 **대화방 가입**을 클릭 하 고 **검색**을 클릭 한 후에 검색 조건을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="77386-185">From the Persistent Chat client, User1 clicks **Join a Chat Room**, clicks **Search**, and then enters some search criteria.</span></span> <span data-ttu-id="77386-186">영구 채팅 클라이언트는 검색 조건과 함께 XCCOS **chansrch** (대화방 검색) 명령이 포함 된 SIP 정보 메시지를 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="77386-186">The Persistent Chat client sends a SIP INFO message that contains the XCCOS **chansrch** (room search) command, along with the search criteria.</span></span> <span data-ttu-id="77386-187">영구 채팅 서버 백 엔드 데이터베이스를 쿼리하고 검색 조건을 충족 하는 사용 가능한 대화방 목록이 포함 된 새 SIP 정보 메시지에 회신 합니다.</span><span class="sxs-lookup"><span data-stu-id="77386-187">Persistent Chat Server queries the back-end database and replies in a new SIP INFO message that contains a list of available rooms that meet the search criteria.</span></span>

2.  <span data-ttu-id="77386-188">User1이 참가하려는 채팅방을 선택한 후 **이 방 팔로우**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="77386-188">User1 selects the chat room that he or she wants to join, and then clicks **Follow this room**.</span></span> <span data-ttu-id="77386-189">영구 채팅 클라이언트가 영구 채팅 서버 전송 XCCOS **join** 명령 및 사용자가 선택한 대화방의 대화방 ID가 포함 된 SIP 정보 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="77386-189">The Persistent Chat client sends Persistent Chat Server a SIP INFO message that contains the XCCOS **join** command and the room ID of the chat room that the user selected.</span></span> <span data-ttu-id="77386-190">영구 채팅 서버는 프로 비전 데이터를 포함 하는 SIP INFO 메시지와 함께 회신 합니다.</span><span class="sxs-lookup"><span data-stu-id="77386-190">Persistent Chat Server replies with a SIP INFO message that contains the provisioning data.</span></span>

3.  <span data-ttu-id="77386-191">영구 채팅 클라이언트가 영구 채팅 서버 전송 XCCOS **bccontext** (backchat context) 명령이 포함 된 SIP 정보 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="77386-191">The Persistent Chat client sends Persistent Chat Server a SIP INFO message that contains the XCCOS **bccontext** (backchat context) command.</span></span> <span data-ttu-id="77386-192">영구 채팅 서버는 채팅 기록을 검색 하 고 별도의 SIP 정보 메시지로 영구 채팅 클라이언트에 게 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="77386-192">Persistent Chat Server retrieves the chat history, and returns it to the Persistent Chat client in a separate SIP INFO message.</span></span> <span data-ttu-id="77386-193">이때 사용자가 방에 들어가고 참가할 준비가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="77386-193">At this point, the user enters the chat room and is ready to participate.</span></span>

4.  <span data-ttu-id="77386-194">User1이 새 메시지를 입력한 후 **보내기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="77386-194">User1 enters a new message, and then clicks **Send**.</span></span> <span data-ttu-id="77386-195">영구 채팅 클라이언트가 SIP 정보 XCCOS **grpchat** 명령의 대화방에 메시지를 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="77386-195">The Persistent Chat client posts the message to the chat room in a SIP INFO XCCOS **grpchat** command.</span></span> <span data-ttu-id="77386-196">영구 채팅 서버에이 새 메시지의 복사본이 영구 채팅 백 엔드 데이터베이스에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="77386-196">Persistent Chat Server stores a copy of this new message in the Persistent Chat back-end database.</span></span>

5.  <span data-ttu-id="77386-197">영구 채팅 서버는 이미 대화방에 들어간 SIP 정보 XCCOS **grpchat** 메시지의 별도 복사본을 사용자 2에 게 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="77386-197">Persistent Chat Server sends a separate copy of the SIP INFO XCCOS **grpchat** message to User2, who has already entered the chat room.</span></span>

</div>

</div>

<div>

## <a name="persistent-chat-compliance-call-flows"></a><span data-ttu-id="77386-198">영구 채팅 준수 호출 흐름</span><span class="sxs-lookup"><span data-stu-id="77386-198">Persistent Chat Compliance Call Flows</span></span>

<span data-ttu-id="77386-199">영구 채팅 서버는 메시지 큐 (MSMQ 라고도 함)와 준수 데이터를 처리 하기 위한 추가 준수 데이터베이스 (mgccomp)를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="77386-199">Persistent Chat Server uses Message Queuing (also known as MSMQ) and an additional compliance database (mgccomp) to process compliance data.</span></span> <span data-ttu-id="77386-200">준수 이벤트를 처리하는 방법에 대한 예로 다음 이벤트 시퀀스에서는 메시지 게시 이벤트가 처리되는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="77386-200">As an example of how compliance events are processed, the following sequence of events describes how a message post event is processed.</span></span>

1.  <span data-ttu-id="77386-201">사용자가 메시지를 방에 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="77386-201">A user posts a message to a room.</span></span>

2.  <span data-ttu-id="77386-202">영구 채팅 서버는 이벤트와 관련 된 정보를 개인 메시지 큐 큐에 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="77386-202">Persistent Chat Server places information pertaining to the event in a private Message Queuing queue.</span></span>

3.  <span data-ttu-id="77386-203">영구 채팅 준수 서버가 큐에서이 이벤트를 읽고 나중에 처리 하기 위해 mgccomp 데이터베이스에 배치 합니다.</span><span class="sxs-lookup"><span data-stu-id="77386-203">Persistent Chat Compliance server reads this event from the queue, and places it into the mgccomp database for processing later.</span></span>

4.  <span data-ttu-id="77386-204">영구 채팅 준수 서버가 주기적으로 데이터베이스에서 이벤트 집합을 처리 하 고이를 영구 채팅 준수 어댑터로 보내 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="77386-204">Periodically, the Persistent Chat Compliance server processes a set of events in the database, and sends them to the Persistent Chat Compliance adapter for processing.</span></span>

5.  <span data-ttu-id="77386-205">어댑터가 데이터를 성공적으로 처리 하면 영구 채팅 준수 서버가 mgccomp 데이터베이스에서 이벤트를 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="77386-205">If the adapter successfully processes the data, Persistent Chat Compliance server deletes the events from the mgccomp database.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

