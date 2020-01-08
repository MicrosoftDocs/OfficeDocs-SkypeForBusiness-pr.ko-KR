---
title: 'Lync Server 2013: 새 영구 채팅 서버 기능'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: New Persistent Chat Server features
ms:assetid: c3ec6f33-6261-4bf5-aa31-baa8ab2a87d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412965(v=OCS.15)
ms:contentKeyID: 48185341
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e6d5cd0b8197b64abfc0761dfb333f338b507ff7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984360"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-persistent-chat-server-features-in-lync-server-2013"></a><span data-ttu-id="cef4a-102">Lync Server 2013의 새 영구 채팅 서버 기능</span><span class="sxs-lookup"><span data-stu-id="cef4a-102">New Persistent Chat Server features in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cef4a-103">_**마지막으로 수정한 주제:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="cef4a-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="cef4a-104">Lync Server 2013, 영구 채팅 서버를 사용 하면 시간에 따라 유지 되는 단체의 토픽 기반 대화에 참여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cef4a-104">Lync Server 2013, Persistent Chat Server enables you to participate in multiparty, topic-based conversations that persist over time.</span></span> <span data-ttu-id="cef4a-105">영구 채팅 서버는 조직에서 다음을 수행할 수 있도록 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="cef4a-105">Persistent Chat Server can help your organization do the following:</span></span>

  - <span data-ttu-id="cef4a-106">지리적으로 분산 된 팀과 부서간 업무 흐름도 간의 의사 소통 개선</span><span class="sxs-lookup"><span data-stu-id="cef4a-106">Improve communication between geographically dispersed and cross-functional teams</span></span>

  - <span data-ttu-id="cef4a-107">정보 인식 및 참가</span><span class="sxs-lookup"><span data-stu-id="cef4a-107">Broaden information awareness and participation</span></span>

  - <span data-ttu-id="cef4a-108">확장 된 조직과의 통신 개선</span><span class="sxs-lookup"><span data-stu-id="cef4a-108">Improve communication with your extended organization</span></span>

  - <span data-ttu-id="cef4a-109">정보 오버 로드 줄이기</span><span class="sxs-lookup"><span data-stu-id="cef4a-109">Reduce information overload</span></span>

  - <span data-ttu-id="cef4a-110">정보 인식 향상</span><span class="sxs-lookup"><span data-stu-id="cef4a-110">Improve information awareness</span></span>

  - <span data-ttu-id="cef4a-111">중요 한 지식 및 정보의 dispersion 증가</span><span class="sxs-lookup"><span data-stu-id="cef4a-111">Increase dispersion of important knowledge and information</span></span>

<span data-ttu-id="cef4a-112">Lync Server 2013, 영구 채팅 서버는 Microsoft Office 365에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cef4a-112">Lync Server 2013, Persistent Chat Server is not available in Microsoft Office 365.</span></span> <span data-ttu-id="cef4a-113">현재 온-프레미스 Lync 2013 고객 에게만 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cef4a-113">At this time, it is available only to on-premise Lync 2013 customers.</span></span>

<span data-ttu-id="cef4a-114">Lync 2013에서 영구 채팅 기능이 Lync 2013 클라이언트에 통합 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="cef4a-114">In Lync 2013, Persistent Chat functionality is integrated into the Lync 2013 client.</span></span> <span data-ttu-id="cef4a-115">따라서 사용자는 Lync 2013 클라이언트에서 인스턴트 메시징/현재 상태, 오디오/비디오, 회의 및 영구 채팅에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cef4a-115">As a result, users have access to Instant Messaging/Presence, Audio/Video, Conferencing, and Persistent Chat all in the Lync 2013 client.</span></span> <span data-ttu-id="cef4a-116">Lync 2013 클라이언트에 대 한 자세한 내용은을 참조 <http://go.microsoft.com/fwlink/p/?linkid=270877>하세요.</span><span class="sxs-lookup"><span data-stu-id="cef4a-116">For more information about the Lync 2013 client, see <http://go.microsoft.com/fwlink/p/?linkid=270877>.</span></span>

<span data-ttu-id="cef4a-117">이 항목에서는 다음을 포함 하 여 Lync Server 2013, 영구 채팅 서버 및 이전 버전 (Microsoft Lync Server 2010, 그룹 채팅)의 새 버전 간 기능 변경 사항에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="cef4a-117">This topic describes feature changes between the new version of Lync Server 2013, Persistent Chat Server and the previous version (Microsoft Lync Server 2010, Group Chat), including:</span></span>

  - <span data-ttu-id="cef4a-118">Lync Server 제어판에서 관리 환경을 제공 하 고 그룹 채팅 관리 도구 제거</span><span class="sxs-lookup"><span data-stu-id="cef4a-118">Provide an administrative experience in Lync Server Control Panel, and eliminate the Group Chat Admin Tool</span></span>

  - <span data-ttu-id="cef4a-119">그룹 채팅 구성 도구를 제거 하 여 영구 채팅 서버의 구성 설정을 토폴로지 작성기에 통합</span><span class="sxs-lookup"><span data-stu-id="cef4a-119">Integrate configuration settings for Persistent Chat Server into Topology Builder by eliminating the Group Chat Configuration tool</span></span>

  - <span data-ttu-id="cef4a-120">이전 버전의 영구 채팅 서버에서 쉽게 마이그레이션 및 업그레이드</span><span class="sxs-lookup"><span data-stu-id="cef4a-120">Ease migration and upgrade from previous versions of Persistent Chat Server</span></span>

  - <span data-ttu-id="cef4a-121">고가용성 및 재해 복구 솔루션 제공</span><span class="sxs-lookup"><span data-stu-id="cef4a-121">Provide high availability and disaster recovery solutions</span></span>

<span data-ttu-id="cef4a-122">최신 버전의 영구 채팅 서버에 대 한 자세한 내용은 다음을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="cef4a-122">For additional details about the latest version of Persistent Chat Server, see the following:</span></span>

  - <span data-ttu-id="cef4a-123">영구 채팅 기능에 대 <http://go.microsoft.com/fwlink/p/?linkid=270945> 한 자세한 목록과 작동 방식, 영구 채팅 서버를 실행 하는 동안 사용 하는 방법 등을 제공 하는 영구 채팅 도움말입니다.</span><span class="sxs-lookup"><span data-stu-id="cef4a-123">The Persistent Chat Help at <http://go.microsoft.com/fwlink/p/?linkid=270945> which provides a detailed list of Persistent Chat features, how they work, and how to use them while running Persistent Chat Server.</span></span>

  - <span data-ttu-id="cef4a-124">[Lync server 2013의 영구 채팅 서버 계획에 대 한 자세한](lync-server-2013-planning-for-persistent-chat-server.md) 내용은 다음 문서를 참조 하세요. [lync Server 2013에서 영구 채팅 서버 배포](lync-server-2013-deploying-persistent-chat-server.md) 배포 설명서의 [Lync server 2010, 그룹 채팅 또는 Office Communications server 2007 R2 그룹 채팅, lync Server](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md) 에 대 한 영구 채팅 서버, 운영 설명서에서 지속적인 채팅 서버로의 관리, [설정](managing-lync-server-2013-persistent-chat-server.md) 2013에 대 한 지침을 제공 하는 모든 정보 2013 영구 채팅 서버.</span><span class="sxs-lookup"><span data-stu-id="cef4a-124">The [Planning for Persistent Chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) in the Planning documentation, [Deploying Persistent Chat Server in Lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md) in the Deployment documentation, [Migration from Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat to Lync Server 2013, Persistent Chat Server](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md) in the Migration documentation, and [Managing Lync Server 2013, Persistent Chat Server](managing-lync-server-2013-persistent-chat-server.md) in the Operations documentation, all of which provide instructions for setting up Persistent Chat Server.</span></span>

  - <span data-ttu-id="cef4a-125">영구 채팅 서버 문서 .msi 파일 (Windows Installer 파일)을 통해 사용자는 영구 채팅 서버에 대 한 종합적인 오프 라인 설명서에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cef4a-125">The Persistent Chat Server Documentation.msi file (Windows Installer file) lets users access comprehensive offline documentation about Persistent Chat Server.</span></span>

<div>

## <a name="key-topology-changes-for-persistent-chat-server"></a><span data-ttu-id="cef4a-126">영구 채팅 서버의 키 토폴로지 변경 사항</span><span class="sxs-lookup"><span data-stu-id="cef4a-126">Key Topology Changes for Persistent Chat Server</span></span>

<span data-ttu-id="cef4a-127">영구 채팅 서버에 대 한 다음과 같은 상위 수준의 변경 사항에는 다음이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cef4a-127">The following high-level changes for Persistent Chat Server include:</span></span>

<span data-ttu-id="cef4a-128">영구 채팅 서버는 이제 서버 역할입니다.</span><span class="sxs-lookup"><span data-stu-id="cef4a-128">Persistent Chat Server is now a server role.</span></span> <span data-ttu-id="cef4a-129">Microsoft Lync Server 2010에서 그룹 채팅 서버는 Microsoft Lync Server 2010 용 타사 신뢰할 수 있는 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="cef4a-129">In Microsoft Lync Server 2010, Group Chat Server was a third-party trusted application for Microsoft Lync Server 2010.</span></span> <span data-ttu-id="cef4a-130">토폴로지 작성기를 사용 하 여 Lync Server 2013 토폴로지에 영구 채팅을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cef4a-130">Persistent Chat can be added to your Lync Server 2013 topology by using Topology Builder.</span></span> <span data-ttu-id="cef4a-131">Lync Server 2013에서 영구 채팅 서버 기능은 다음과 같은 세 가지 새로운 서버 역할을 사용 하 여 구현 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cef4a-131">In Lync Server 2013, Persistent Chat Server functionality is implemented by using three new server roles:</span></span>

  - <span data-ttu-id="cef4a-132">**PersistentChatService:** 영구 채팅에 대 한 프런트 엔드 역할입니다.</span><span class="sxs-lookup"><span data-stu-id="cef4a-132">**PersistentChatService:** This is the front end role for Persistent Chat.</span></span> <span data-ttu-id="cef4a-133">Standard Edition 배포에서 영구 채팅 서버 서비스 역할은 다른 Lync Server 역할과 같이 부트스트래퍼가 배포 하는 스탠더드 버전 서버에 collocated 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cef4a-133">In Standard Edition deployments, Persistent Chat Server Service Role is collocated on the Standard Edition server deployed by Bootstrapper, like any other Lync Server role.</span></span> <span data-ttu-id="cef4a-134">Enterprise Edition 배포에서 영구 채팅 서비스 역할은 다른 Lync Server 역할과 같은 부트스트래퍼를 통해 독립 실행형 컴퓨터에 배포 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cef4a-134">In Enterprise Edition deployments, Persistent Chat Service Role is deployed on stand-alone computers by Bootstrapper, like any other Lync Server role.</span></span>

  - <span data-ttu-id="cef4a-135">**PersistentChatStore:** 모든 채팅 콘텐츠가 저장 되는 영구 채팅 콘텐츠 데이터베이스에 해당 하는 백 엔드 서버입니다.</span><span class="sxs-lookup"><span data-stu-id="cef4a-135">**PersistentChatStore:** Back End Server that corresponds to the Persistent Chat content database, where all the chat content is stored.</span></span>

  - <span data-ttu-id="cef4a-136">**PersistentChatComplianceStore:** 모든 규정 준수 이벤트가 저장 되는 영구 채팅 준수 데이터베이스에 해당 하는 백 엔드 서버 역할입니다.</span><span class="sxs-lookup"><span data-stu-id="cef4a-136">**PersistentChatComplianceStore:** Back End Server role that corresponds to the Persistent Chat Compliance database, where all compliance events are stored.</span></span>

<span data-ttu-id="cef4a-137">이러한 영구 채팅 서버 역할은 선택 사항이 며, 종합적인 영구 채팅 서버 기능을 원하는 고객 에게만 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cef4a-137">These Persistent Chat Server roles are optional, and are installed only by customers who want comprehensive Persistent Chat Server functionality.</span></span> <span data-ttu-id="cef4a-138">**PersistentChatComplianceStore** 역할은 영구 채팅 준수를 배포 하기로 선택 하는 경우에만 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="cef4a-138">The **PersistentChatComplianceStore** role is needed only if you choose to deploy Persistent Chat Compliance.</span></span>

<span data-ttu-id="cef4a-139">**PersistentChatService** 역할은 다음 두 가지 서비스를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="cef4a-139">The **PersistentChatService** role runs two services:</span></span>

  - <span data-ttu-id="cef4a-140">영구 채팅 서비스</span><span class="sxs-lookup"><span data-stu-id="cef4a-140">Persistent Chat service</span></span>

  - <span data-ttu-id="cef4a-141">영구 채팅 준수 서비스</span><span class="sxs-lookup"><span data-stu-id="cef4a-141">Persistent Chat Compliance service</span></span>

<span data-ttu-id="cef4a-142">이러한 서비스는 각 영구 채팅 서버에서 실행 되도록 하는 것이 다중 서버 영구 채팅 서버 풀에서 높은 가용성을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="cef4a-142">Having these services run on each Persistent Chat Server provides high availability for these services in a multiserver Persistent Chat Server pool.</span></span>

<span data-ttu-id="cef4a-143">또한 영구 채팅방에서 파일 업로드 및 다운로드를 지원 하기 위해 지속적인 채팅 서버에는 웹 서비스가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cef4a-143">Additionally, to support the file upload and download in Persistent Chat rooms, Persistent Chat Server includes a web service.</span></span> <span data-ttu-id="cef4a-144">이전에이 서비스는 영구 채팅 서버, 프런트 엔드 서버, 필요한 IIS (인터넷 정보 서비스)를 필수 구성 요소로 설치 하는 collocated 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="cef4a-144">Previously, this service was collocated on the Persistent Chat Server, Front End Server and required Internet Information Services (IIS) to be installed as a prerequisite.</span></span> <span data-ttu-id="cef4a-145">Lync Server 2013 영구 채팅 서버에서는 Lync Server 2013 프런트 엔드 서버를 사용 하 여 파일 업로드/다운로드 웹 서비스를 collocated 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cef4a-145">In Lync Server 2013 Persistent Chat Server, the File Upload/Download web service is collocated with the Lync Server 2013 Front End Server.</span></span> <span data-ttu-id="cef4a-146">부작용으로 서, IIS (인터넷 정보 서비스)는 더 이상 영구 채팅 서버의 선행 조건이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="cef4a-146">As a side effect, Internet Information Services (IIS) is no longer a prerequisite for Persistent Chat Server.</span></span> <span data-ttu-id="cef4a-147">파일 업로드/다운로드 웹 서비스는 IIS (인터넷 정보 서비스) 관리자에서 **PersistentChat** 로 식별 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cef4a-147">The File Upload/Download web service is identified as **PersistentChat** in the Internet Information Services (IIS) Manager.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="cef4a-148"><STRONG>PersistentChatService</STRONG> 역할은 Lync server 2013&nbsp;프런트 엔드 서버와 동일한 서버에서 실행할 수 있습니다 (해당 프런트 엔드 서버가 표준 Edition&nbsp;프런트 엔드 서버인 경우에만 해당).</span><span class="sxs-lookup"><span data-stu-id="cef4a-148">The <STRONG>PersistentChatService</STRONG> role can run on the same server as a Lync Server 2013&nbsp;Front End Server only if that Front End Server is a Standard Edition&nbsp;Front End Server.</span></span> <span data-ttu-id="cef4a-149"><STRONG>PersistentChatService</STRONG> 역할은 Lync server 2013&nbsp;프런트 엔드 서버와 독립적으로 실행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cef4a-149">The <STRONG>PersistentChatService</STRONG> role cannot run independently of a Lync Server 2013&nbsp;Front End Server.</span></span> <span data-ttu-id="cef4a-150">Lync Server 2013 배포의 컨텍스트에서만 설치 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cef4a-150">It can be installed only in the context of a Lync Server 2013 deployment.</span></span>



</div>

<span data-ttu-id="cef4a-151">영구 채팅 서버에서 조회 서비스는 제거 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="cef4a-151">In Persistent Chat Server, Lookup service has been eliminated.</span></span> <span data-ttu-id="cef4a-152">Lync Server 2010의 그룹 채팅에서 조회 서비스는 모든 그룹 채팅 서버 프런트 엔드 서버에서 실행 되며 채널 서버 중 하나로 라우팅을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="cef4a-152">In Lync Server 2010, Group Chat, the Lookup service ran on every Group Chat Server Front End Server, and performed routing to one of the Channel Servers.</span></span> <span data-ttu-id="cef4a-153">Lync Server 2013는 연락처 개체를 사용 하 여 라우팅에 의존 하며, 각 영구 채팅 서버 풀이 Lync Server 프런트 엔드 서버에서 해당 영구 채팅 서버 풀로 요청을 식별 하 고 라우팅하는 데 사용 되는 contact 개체로 표시 됩니다. 풀에서 영구 채팅 서버를 실행 하는 컴퓨터 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="cef4a-153">Lync Server 2013 relies on routing by using contact objects, where each Persistent Chat Server pool is represented by a contact object that is used by the Lync Server Front End Servers to identify and route requests to an appropriate Persistent Chat Server pool, and to one of the computers running Persistent Chat Server in the pool.</span></span>

<span data-ttu-id="cef4a-154">Lync Server 2013에는 준수 서비스 수정 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cef4a-154">In Lync Server 2013, there are Compliance service modifications:</span></span>

  - <span data-ttu-id="cef4a-155">Lync Server 2010에서 준수 서비스는 독립 실행형 (비 collocated) 및 단일 서버 에서만 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cef4a-155">In Lync Server 2010, the Compliance service ran stand-alone (non-collocated), and only on a single server.</span></span> <span data-ttu-id="cef4a-156">이제 준수 서비스는 영구 채팅 서비스와 함께 모든 영구 채팅 서버 프런트 엔드 서버에서 실행 되며,이를 통해 다중 서버 영구 채팅 서버 풀에서 높은 가용성을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="cef4a-156">The Compliance service now runs on all the Persistent Chat Server Front End Servers, alongside the Persistent Chat service, and thereby provides high availability in a multiserver Persistent Chat Server pool.</span></span> <span data-ttu-id="cef4a-157">규정 준수 데이터베이스에서 데이터를 추출 하 고 다른 시스템 중 하나 (XML 파일, Exchange에서 호스트 된 아카이브 등)로 단일 준수 어댑터를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cef4a-157">A single compliance adapter can be configured to extract data from the compliance database and into one of the other systems (XML file, Exchange-hosted archives, and so on).</span></span> <span data-ttu-id="cef4a-158">영구 채팅 서버에는 XML 어댑터가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cef4a-158">Persistent Chat Server includes an XML adapter.</span></span>

  - <span data-ttu-id="cef4a-159">영구 채팅 서비스 및 각 영구 채팅 서버 프런트 엔드 서버에서 공유 되는 메시지 큐 (MSMQ 라고도 함) 큐는 이제 두 서비스 에서만 공유 하는 개인 큐입니다.</span><span class="sxs-lookup"><span data-stu-id="cef4a-159">The Message Queuing (also known as MSMQ) queue that is shared by the Persistent Chat service and the Compliance service on each Persistent Chat Server Front End Server is now a private queue shared only by the two services.</span></span> <span data-ttu-id="cef4a-160">모든 준수 서비스는 동일한 준수 백 엔드 데이터베이스에 기록 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cef4a-160">All compliance services write to the same Compliance Back End database.</span></span> <span data-ttu-id="cef4a-161">또한 해당 데이터베이스에서 모두 읽었으며 해당 사용자의 어댑터 인스턴스에 데이터를 보내는 목적으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cef4a-161">They also all read from that database, for the purpose of sending the data to their instance of the adapter.</span></span> <span data-ttu-id="cef4a-162">규정 준수 백 엔드 서버는 새 백 엔드 서버 역할로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cef4a-162">The Compliance Back End Server is represented as a new Back End Server role.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="cef4a-163">이전 버전과 마찬가지로 모든 준수 데이터는 한 번만 처리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cef4a-163">As in previous versions, all compliance data is processed only once.</span></span> <span data-ttu-id="cef4a-164">다양 한 Lync Server 2013, 영구 채팅 서버 컴퓨터에서 실행 되는 규정 준수 서비스에서 호출한 어댑터 인스턴스가 데이터를 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cef4a-164">The data may be processed by any of the adapter instances invoked by the compliance service running on the various Lync Server 2013, Persistent Chat Server computers.</span></span> <span data-ttu-id="cef4a-165">영구 채팅 서버에서 어댑터 인스턴스 중 하나가 데이터를 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cef4a-165">In Persistent Chat Server, any one of the adapter instances could process the data.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="cef4a-166">메시지 큐 설치에 대 한 자세한 내용은 배포 설명서의 <A href="lync-server-2013-install-operating-systems-and-prerequisite-software-on-servers.md">Lync Server 2013 서버에 운영 체제 및 필수 구성 요소 소프트웨어 설치</A> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="cef4a-166">For information about installing Message Queuing, see <A href="lync-server-2013-install-operating-systems-and-prerequisite-software-on-servers.md">Install operating systems and prerequisite software on servers for Lync Server 2013</A> in the Deployment documentation.</span></span>

    
    </div>

<span data-ttu-id="cef4a-167">Lync Server 2013에는 고가용성 및 재해 복구가 모두 개선 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="cef4a-167">In Lync Server 2013, there are improvements in both high availability and disaster recovery:</span></span>

  - <span data-ttu-id="cef4a-168">고가용성 개선: SQL Server 미러링은 데이터 센터 내에서 영구 채팅 서버 콘텐츠 데이터베이스와 영구 채팅 준수 데이터베이스에 높은 가용성을 제공 하는 데 사용 됩니다 (사이트 내).</span><span class="sxs-lookup"><span data-stu-id="cef4a-168">High availability improvements: SQL Server mirroring is used to provide high availability for the Persistent Chat Server content database and Persistent Chat compliance database within a data center (in-site).</span></span>

  - <span data-ttu-id="cef4a-169">재해 복구 개선 사항: 영구 채팅 서버는 두 사이트 (즉, 토폴로지에 있는 단일 논리 풀)에서 단일 영구 채팅 서버 풀을 물리적으로 확장 가능 하 게 하는 스트레치 된 풀 아키텍처를 지원 합니다. 두 사이트에 위치 함).</span><span class="sxs-lookup"><span data-stu-id="cef4a-169">Disaster recovery improvements: Persistent Chat Server supports a stretched pool architecture that enables a single Persistent Chat Server pool to be stretched across two sites (that is, a single logical pool in the topology, with servers in the pool physically located across two sites).</span></span> <span data-ttu-id="cef4a-170">사이트 간 재난 복구에 사용 되는 SQL Server 로그 전달.</span><span class="sxs-lookup"><span data-stu-id="cef4a-170">SQL Server Log Shipping is used for cross-site disaster recovery.</span></span>

<span data-ttu-id="cef4a-171">고가용성 및 장애 복구에 대 한 자세한 내용은 배포 설명서의 [Lync Server 2013에서 고가용성 및 재해 복구용으로 영구 채팅 서버 구성을](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="cef4a-171">For more information about high availability and disaster recovery, see [Configuring Persistent Chat Server for high availability and disaster recovery in Lync Server 2013](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md) in the Deployment documentation.</span></span>

</div>

<div>

## <a name="key-administration-and-management-changes-for-persistent-chat-server"></a><span data-ttu-id="cef4a-172">영구 채팅 서버의 주요 관리 및 관리 변경 사항</span><span class="sxs-lookup"><span data-stu-id="cef4a-172">Key Administration and Management Changes for Persistent Chat Server</span></span>

<span data-ttu-id="cef4a-173">Lync Server 2013을 통해 다음을 제공 하 여 영구 채팅 서버를 더욱 쉽게 관리 하 고 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cef4a-173">Lync Server 2013 has made it easier to administer and manage Persistent Chat Server by providing:</span></span>

  - <span data-ttu-id="cef4a-174">통합 된 관리 및 관리.</span><span class="sxs-lookup"><span data-stu-id="cef4a-174">Unified administration and management.</span></span> <span data-ttu-id="cef4a-175">Lync Server 2013을 통해 Lync 관리자에 게 이미 익숙한 도구를 사용 하 여 영구 채팅 서버를 쉽게 관리 하 고 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cef4a-175">Lync Server 2013 makes it easier to manage and administer Persistent Chat Server by using tools that are already familiar to Lync administrators.</span></span> <span data-ttu-id="cef4a-176">영구 채팅 서버에는 Lync Server 제어판과 통합 된 관리 사용자 인터페이스 환경이 포함 되어 있어 이전 버전의 그룹 채팅 서버 사용자 인터페이스에 대 한 성능 문제를 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cef4a-176">Persistent Chat Server includes an administrative user interface experience that is integrated with the Lync Server Control Panel, which addresses performance issues with the previous versions of the Group Chat Server user interface.</span></span> <span data-ttu-id="cef4a-177">또한 영구 채팅 서버에는 영구 채팅 서버 범주를 관리 하 고 관리 하는 Windows PowerShell cmdlet 모음, 채팅방 삭제 및 오래 된 콘텐츠 제거를 비롯 한 추가 기능이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cef4a-177">Also, Persistent Chat Server includes a collection of Windows PowerShell cmdlets to administer and manage Persistent Chat Server categories, Persistent Chat Server rooms (including deleting rooms and purging obsolete content), and add-ins.</span></span>

  - <span data-ttu-id="cef4a-178">간단한 관리 모델</span><span class="sxs-lookup"><span data-stu-id="cef4a-178">Simplified administration model.</span></span> <span data-ttu-id="cef4a-179">Lync Server 2013에서 다음 주요 고객 요구 사항을 해결 하 여 영구 채팅 서버 모델을 변경 하 고 단순화 했습니다.</span><span class="sxs-lookup"><span data-stu-id="cef4a-179">Lync Server 2013 has changed and simplified the Persistent Chat Server model by addressing the following key customer requirements:</span></span>
    
      - <span data-ttu-id="cef4a-180">범위 및 범주에 대 한 복잡 하 게 중첩 된 계층 구조를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="cef4a-180">Remove the complex nested hierarchies of scopes and categories.</span></span>
    
      - <span data-ttu-id="cef4a-181">영구 채팅 서버로 마이그레이션하도록 계획 중인 현재 MindAlign 고객에 대해 거부 목록 및 허용 목록 (범위)을 정의 하는 지원.</span><span class="sxs-lookup"><span data-stu-id="cef4a-181">Support to define deny lists as well as allowed lists (scopes) for current MindAlign customers who are planning to migrate to Persistent Chat Server.</span></span>

</div>

<div>

## <a name="whats-different-about-user-roles-from-previous-group-chat-server-versions"></a><span data-ttu-id="cef4a-182">이전 그룹 채팅 서버 버전과의 사용자 역할에 대 한 차이점은 무엇 인가요?</span><span class="sxs-lookup"><span data-stu-id="cef4a-182">What’s Different about User Roles from Previous Group Chat Server Versions?</span></span>

<span data-ttu-id="cef4a-183">Lync Server 2010의 그룹 채팅에는 사용자 관리자 역할이 있으며, 채팅방 관리자 역할 및 추가 기능을 관리할 수 있는 Lync Server 관리자 역할이 있습니다. 영구 채팅 서버는 단순히 영구 채팅 관리자 역할을 제공 합니다 (다른 Lync와 유사). 서버 역할 기반 액세스 제어 (RBAC) 역할.</span><span class="sxs-lookup"><span data-stu-id="cef4a-183">Lync Server 2010, Group Chat had a user administrator role, a chat room administrator role and a Lync Server administrator role that could manage add-ins. Persistent Chat Server simply provides a Persistent Chat Administrator role (which is similar to other Lync Server role-based access control (RBAC) roles).</span></span> <span data-ttu-id="cef4a-184">이 RBAC 역할의 구성원 인 사용자는 채팅방, 추가 기능, 범주를 관리 하 고 (따라서 이러한 범주에 대 한 사용자 액세스 권한 획득) 영구 채팅 서버 풀을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cef4a-184">Anyone who is a member of this RBAC role can manage chat rooms, add-ins, and categories (and therefore gain user access for these categories), and configuration of the Persistent Chat Server pool.</span></span>

</div>

<div>

## <a name="whats-different-about-chat-room-categories-from-previous-group-chat-server-versions"></a><span data-ttu-id="cef4a-185">이전 그룹 채팅 서버 버전의 채팅방 범주에 대 한 차이점은 무엇 인가요?</span><span class="sxs-lookup"><span data-stu-id="cef4a-185">What’s Different about Chat Room Categories from Previous Group Chat Server Versions?</span></span>

<span data-ttu-id="cef4a-186">채팅방 범주는 더 이상 중첩할 수 없으며 루트 범주는 더 이상 수정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cef4a-186">Chat room categories can no longer be nested, and the root category can no longer be modified.</span></span> <span data-ttu-id="cef4a-187">AllowedMembers/DeniedMembers는 레거시 그룹 채팅 서버 버전에 사용 되는 범위를 구성 합니다 (거부 목록 지정을 지원 하지 않는다는 점만 제외).</span><span class="sxs-lookup"><span data-stu-id="cef4a-187">AllowedMembers/DeniedMembers comprise what a scope used to be in legacy Group Chat Server versions (except that it didn’t support specifying a Denied list).</span></span> <span data-ttu-id="cef4a-188">중첩 범주가 없기 때문에 범위를 더 이상 재정의할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cef4a-188">Scopes can no longer be overridden, because there are no nested categories.</span></span> <span data-ttu-id="cef4a-189">Lync Server 2013의 영구 채팅 관리자는 채팅방 범주를 만들고 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cef4a-189">A Persistent Chat Administrator in Lync Server 2013 can create and manage chat room categories.</span></span> <span data-ttu-id="cef4a-190">채팅방 범주를 만들고 관리 하는 과정에서 영구 채팅 관리자는 특정 범주에 대 한 채팅방의 구성원/작성자로 액세스할 수 있는 사용자 (Active Directory 그룹/컨테이너/사용자)를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cef4a-190">As part of creating and managing chat room categories, a Persistent Chat Administrator can configure principals (Active Directory groups/containers/users) that have access to be members/creators of chat rooms of a particular category.</span></span> <span data-ttu-id="cef4a-191">영구 채팅 관리자는 범주에 DeniedMembers를 추가할 수 있으며, 허용 목록에 대 한 명시적 제외가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cef4a-191">A Persistent Chat Administrator can also add DeniedMembers to a category, and these become explicit exclusions to the allowed list.</span></span> <span data-ttu-id="cef4a-192">DeniedMembers는 AllowedMembers에 포함된 항목에 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="cef4a-192">DeniedMembers override what’s in AllowedMembers.</span></span>

</div>

<div>

## <a name="whats-different-about-chat-room-properties-from-previous-group-chat-server-versions"></a><span data-ttu-id="cef4a-193">이전 그룹 채팅 서버 버전의 채팅방 속성에 대 한 차이점은 무엇 인가요?</span><span class="sxs-lookup"><span data-stu-id="cef4a-193">What’s Different about Chat Room Properties from Previous Group Chat Server Versions?</span></span>

<span data-ttu-id="cef4a-194">Lync Server 2013, 영구 채팅 서버에 열려 있는 채팅방의 새로운 개념이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cef4a-194">A new concept of open chat rooms exists in Lync Server 2013, Persistent Chat Server.</span></span> <span data-ttu-id="cef4a-195">허용 된 모든 구성원은 독점 구성원 없이 채팅방에 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cef4a-195">All allowed members can join the chat room, without exclusive membership.</span></span>

<span data-ttu-id="cef4a-196">이전 버전의 영구 채팅 서버에 포함 된 다음 채팅방 속성이 제거 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="cef4a-196">The following chat room properties that were included in previous versions of Persistent Chat Server have been eliminated:</span></span>

  - <span data-ttu-id="cef4a-197">주제: 이제 채팅방에 대 한 설명만 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cef4a-197">Topic: A Room now only has a Description.</span></span>

  - <span data-ttu-id="cef4a-198">새 구성원 목록 만들기: 영구 채팅 서버에서 모든 채팅방은 빈 구성원으로 시작 되며 허용 된 회원에 게 equaling 구성원 자격을 최대화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cef4a-198">Create New Member list: In Persistent Chat Server, all chat rooms start with empty membership (and can maximize to a membership equaling the Allowed Members).</span></span>

  - <span data-ttu-id="cef4a-199">파일 업로드: 파일 업로드/다운로드가 허용 되는지 여부를 제어 하기 위해 채팅방 별로 설정 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cef4a-199">File Upload: Used to be a setting per chat room to control whether file upload/downloads were allowed.</span></span> <span data-ttu-id="cef4a-200">이제 범주 수준만 설정 하 고 해당 범주의 모든 채팅방에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cef4a-200">This is now set only the category level and applies to all rooms in that category.</span></span>

  - <span data-ttu-id="cef4a-201">채팅 기록: 채팅 기록의 사용 가능 여부를 제어 하기 위해 채팅방 별로 설정 하는 데 사용 되지만, 이제 범주 수준 에서만 설정 되 고 해당 범주의 모든 채팅방에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cef4a-201">Chat History: Used to be a setting per chat room to control if Chat History was enabled, but is now set only at the category level and applies to all rooms in that category.</span></span>

  - <span data-ttu-id="cef4a-202">초대: 룸은 항상 범주에 대 한 초대 설정을 상속 합니다. 또는 룸에서 기능을 끌 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cef4a-202">Invites: A room always inherits the Invites setting for the category; or it can be turned off on the room.</span></span> <span data-ttu-id="cef4a-203">범주가 이전에 초대를 해제 하도록 설정 된 경우에는 채팅방이 초대를 켤 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cef4a-203">A room cannot turn on Invites if the category was previously set to Invites off.</span></span>

</div>

<div>

## <a name="whats-different-about-policies-from-previous-group-chat-server-versions"></a><span data-ttu-id="cef4a-204">이전 그룹 채팅 서버 버전의 정책에 대 한 차이점은 무엇 인가요?</span><span class="sxs-lookup"><span data-stu-id="cef4a-204">What’s Different about Policies from Previous Group Chat Server Versions?</span></span>

<span data-ttu-id="cef4a-205">영구 채팅 서버에는 사용자/풀/사이트/전역 설정에 따라 영구 채팅을 사용 하는 새로운 Lync 정책이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cef4a-205">Persistent Chat Server has a new Lync policy enabled with Persistent Chat, per user/pool/site/global settings.</span></span> <span data-ttu-id="cef4a-206">Lync 2013 클라이언트에서는 영구 채팅을 위해 정책에 따라 설정 되는 사용자 (직접 또는 풀/사이트/전역 설정)에 대해서만 영구 채팅 환경을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cef4a-206">In the Lync 2013 client, the Persistent Chat environment is available only for users who are enabled by policy for Persistent Chat (either directly or through the pool/site/global setting).</span></span>

<span data-ttu-id="cef4a-207">이전 버전의 그룹 채팅 서버에는 Lync Server 정책에 통합 된 정책이 없었습니다.</span><span class="sxs-lookup"><span data-stu-id="cef4a-207">Previous versions of Group Chat Server did not have any policies integrated into the Lync Server policies.</span></span> <span data-ttu-id="cef4a-208">사용자 당 및 범주/방에 따라 사용자에 게 **파일 업로드** 기능을 사용 하 여 사용자를 사용자 관리자 또는 채팅방 관리자로 설정 하거나 파일을 업로드 하는 사용자의 기능을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cef4a-208">On a per user and per category/room basis, by using the **Can Upload Files** per user feature, you could make the user a User administrator, a chat room administrator, or configure the user’s ability to upload files.</span></span> <span data-ttu-id="cef4a-209">영구 채팅 서버 **파일 업로드** 기능은 범주 당 한 가지입니다.</span><span class="sxs-lookup"><span data-stu-id="cef4a-209">The Persistent Chat Server **File Upload** feature is just per category.</span></span>

</div>

<div>

## <a name="logging"></a><span data-ttu-id="cef4a-210">로깅하</span><span class="sxs-lookup"><span data-stu-id="cef4a-210">Logging</span></span>

<span data-ttu-id="cef4a-211">영구 채팅 서버 및 System Center Operations Manager에 대 한 로깅은 Lync Server 2013 추적 로깅에 통합 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cef4a-211">Logging for Persistent Chat Server and System Center Operations Manager is integrated into the Lync Server 2013 trace logging.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="cef4a-212">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cef4a-212">See Also</span></span>


[<span data-ttu-id="cef4a-213">Lync Server 2013의 영구 채팅 서버 계획</span><span class="sxs-lookup"><span data-stu-id="cef4a-213">Planning for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-planning-for-persistent-chat-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

