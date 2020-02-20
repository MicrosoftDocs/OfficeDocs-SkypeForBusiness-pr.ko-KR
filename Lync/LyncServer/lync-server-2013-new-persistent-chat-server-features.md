---
title: 'Lync Server 2013: 새 영구 채팅 서버 기능'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New Persistent Chat Server features
ms:assetid: c3ec6f33-6261-4bf5-aa31-baa8ab2a87d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412965(v=OCS.15)
ms:contentKeyID: 48185341
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6c5ad73d11ae629ec0848539b2f4bac2bc81a43e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153580"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="new-persistent-chat-server-features-in-lync-server-2013"></a><span data-ttu-id="6fe38-102">Lync Server 2013의 새 영구 채팅 서버 기능</span><span class="sxs-lookup"><span data-stu-id="6fe38-102">New Persistent Chat Server features in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6fe38-103">_**마지막으로 수정 된 항목:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="6fe38-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="6fe38-104">Lync Server 2013, 영구 채팅 서버를 사용 하면 시간이 지남에 따라 지속 되는 단체 및 토픽 기반 대화에 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fe38-104">Lync Server 2013, Persistent Chat Server enables you to participate in multiparty, topic-based conversations that persist over time.</span></span> <span data-ttu-id="6fe38-105">영구 채팅 서버는 조직에서 다음을 수행 하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fe38-105">Persistent Chat Server can help your organization do the following:</span></span>

  - <span data-ttu-id="6fe38-106">지리적으로 분산되고 업무가 연관된 팀 간의 통신을 향상시킵니다.</span><span class="sxs-lookup"><span data-stu-id="6fe38-106">Improve communication between geographically dispersed and cross-functional teams</span></span>

  - <span data-ttu-id="6fe38-107">보다 많은 구성원과 정보를 보다 많이 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fe38-107">Broaden information awareness and participation</span></span>

  - <span data-ttu-id="6fe38-108">조직 내외부에서 광범위하게 정보를 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fe38-108">Improve communication with your extended organization</span></span>

  - <span data-ttu-id="6fe38-109">효율적인 정보 공유로 정보 오버로드를 줄여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6fe38-109">Reduce information overload</span></span>

  - <span data-ttu-id="6fe38-110">정보 인식을 향상시킵니다.</span><span class="sxs-lookup"><span data-stu-id="6fe38-110">Improve information awareness</span></span>

  - <span data-ttu-id="6fe38-111">중요한 지식과 정보의 배포를 향상시킵니다.</span><span class="sxs-lookup"><span data-stu-id="6fe38-111">Increase dispersion of important knowledge and information</span></span>

<span data-ttu-id="6fe38-112">Lync Server 2013, 영구 채팅 서버는 Microsoft Office 365에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6fe38-112">Lync Server 2013, Persistent Chat Server is not available in Microsoft Office 365.</span></span> <span data-ttu-id="6fe38-113">현재 온-프레미스 Lync 2013 고객 에게만 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6fe38-113">At this time, it is available only to on-premise Lync 2013 customers.</span></span>

<span data-ttu-id="6fe38-114">Lync 2013에서는 영구 채팅 기능이 Lync 2013 클라이언트에 통합 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fe38-114">In Lync 2013, Persistent Chat functionality is integrated into the Lync 2013 client.</span></span> <span data-ttu-id="6fe38-115">따라서 사용자는 Lync 2013 클라이언트에서 인스턴트 메시징/현재 상태, 오디오/비디오, 회의 및 영구 채팅에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fe38-115">As a result, users have access to Instant Messaging/Presence, Audio/Video, Conferencing, and Persistent Chat all in the Lync 2013 client.</span></span> <span data-ttu-id="6fe38-116">Lync 2013 클라이언트에 대 한 자세한 내용은를 참조 <https://go.microsoft.com/fwlink/p/?linkid=270877>하세요.</span><span class="sxs-lookup"><span data-stu-id="6fe38-116">For more information about the Lync 2013 client, see <https://go.microsoft.com/fwlink/p/?linkid=270877>.</span></span>

<span data-ttu-id="6fe38-117">이 항목에서는 새 버전의 Lync Server 2013, 영구 채팅 서버와 이전 버전 (Microsoft Lync Server 2010, 그룹 채팅) 간의 기능 변경 사항에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="6fe38-117">This topic describes feature changes between the new version of Lync Server 2013, Persistent Chat Server and the previous version (Microsoft Lync Server 2010, Group Chat), including:</span></span>

  - <span data-ttu-id="6fe38-118">Lync Server 제어판의 관리 환경을 제공 하 고 그룹 채팅 관리 도구 제거</span><span class="sxs-lookup"><span data-stu-id="6fe38-118">Provide an administrative experience in Lync Server Control Panel, and eliminate the Group Chat Admin Tool</span></span>

  - <span data-ttu-id="6fe38-119">그룹 채팅 구성 도구를 제거 하 여 영구 채팅 서버에 대 한 구성 설정을 토폴로지 작성기에 통합</span><span class="sxs-lookup"><span data-stu-id="6fe38-119">Integrate configuration settings for Persistent Chat Server into Topology Builder by eliminating the Group Chat Configuration tool</span></span>

  - <span data-ttu-id="6fe38-120">이전 버전의 영구 채팅 서버에서 쉽게 마이그레이션 및 업그레이드</span><span class="sxs-lookup"><span data-stu-id="6fe38-120">Ease migration and upgrade from previous versions of Persistent Chat Server</span></span>

  - <span data-ttu-id="6fe38-121">고가용성 및 재해 복구 솔루션 제공</span><span class="sxs-lookup"><span data-stu-id="6fe38-121">Provide high availability and disaster recovery solutions</span></span>

<span data-ttu-id="6fe38-122">최신 버전의 영구 채팅 서버에 대 한 자세한 내용은 다음 항목을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="6fe38-122">For additional details about the latest version of Persistent Chat Server, see the following:</span></span>

  - <span data-ttu-id="6fe38-123">영구 채팅 기능의 자세한 목록과 <https://go.microsoft.com/fwlink/p/?linkid=270945> 작동 방식, 그리고 영구 채팅 서버를 실행 하는 동안 사용 하는 방법에 대 한 자세한 정보를 제공 하는 영구적 채팅 도움말입니다.</span><span class="sxs-lookup"><span data-stu-id="6fe38-123">The Persistent Chat Help at <https://go.microsoft.com/fwlink/p/?linkid=270945> which provides a detailed list of Persistent Chat features, how they work, and how to use them while running Persistent Chat Server.</span></span>

  - <span data-ttu-id="6fe38-124">계획 설명서에서 [Lync Server 2013의 영구 채팅 서버 계획](lync-server-2013-planning-for-persistent-chat-server.md) lync server 2008에서 [영구 채팅 서버 배포 배포](lync-server-2013-deploying-persistent-chat-server.md) 설명서, 2013 [Lync server 2010, 그룹 채팅 또는 Office Communications server 2007 R2 그룹 채팅에서 Lync Server 2013, 영구 채팅 서버](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md) (마이그레이션 설명서) 및 작업 설명서에서 [Lync server 2013, 영구 채팅 서버 관리](managing-lync-server-2013-persistent-chat-server.md) , 모든 설정에 대 한 지침을 제공 합니다. 영구 채팅 서버</span><span class="sxs-lookup"><span data-stu-id="6fe38-124">The [Planning for Persistent Chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) in the Planning documentation, [Deploying Persistent Chat Server in Lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md) in the Deployment documentation, [Migration from Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat to Lync Server 2013, Persistent Chat Server](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md) in the Migration documentation, and [Managing Lync Server 2013, Persistent Chat Server](managing-lync-server-2013-persistent-chat-server.md) in the Operations documentation, all of which provide instructions for setting up Persistent Chat Server.</span></span>

  - <span data-ttu-id="6fe38-125">영구 채팅 서버 설명서 .msi 파일 (Windows Installer 파일)을 사용 하면 영구 채팅 서버에 대 한 포괄적인 오프 라인 설명서에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fe38-125">The Persistent Chat Server Documentation.msi file (Windows Installer file) lets users access comprehensive offline documentation about Persistent Chat Server.</span></span>

<div>

## <a name="key-topology-changes-for-persistent-chat-server"></a><span data-ttu-id="6fe38-126">영구 채팅 서버에 대 한 주요 토폴로지 변경 사항</span><span class="sxs-lookup"><span data-stu-id="6fe38-126">Key Topology Changes for Persistent Chat Server</span></span>

<span data-ttu-id="6fe38-127">영구 채팅 서버에 대 한 다음과 같은 높은 수준의 변경 사항에는 다음이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6fe38-127">The following high-level changes for Persistent Chat Server include:</span></span>

<span data-ttu-id="6fe38-128">영구 채팅 서버는 이제 서버 역할입니다.</span><span class="sxs-lookup"><span data-stu-id="6fe38-128">Persistent Chat Server is now a server role.</span></span> <span data-ttu-id="6fe38-129">Microsoft Lync Server 2010에서 그룹 채팅 서버는 Microsoft Lync Server 2010에 대 한 타사 트러스트 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="6fe38-129">In Microsoft Lync Server 2010, Group Chat Server was a third-party trusted application for Microsoft Lync Server 2010.</span></span> <span data-ttu-id="6fe38-130">토폴로지 작성기를 사용 하 여 Lync Server 2013 토폴로지에 영구 채팅을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fe38-130">Persistent Chat can be added to your Lync Server 2013 topology by using Topology Builder.</span></span> <span data-ttu-id="6fe38-131">Lync Server 2013에서는 다음과 같은 세 가지 새 서버 역할을 사용 하 여 영구 채팅 서버 기능을 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="6fe38-131">In Lync Server 2013, Persistent Chat Server functionality is implemented by using three new server roles:</span></span>

  - <span data-ttu-id="6fe38-132">**PersistentChatService:** 영구 채팅에 대 한 프런트 엔드 역할입니다.</span><span class="sxs-lookup"><span data-stu-id="6fe38-132">**PersistentChatService:** This is the front end role for Persistent Chat.</span></span> <span data-ttu-id="6fe38-133">Standard Edition 배포에서 영구 채팅 서버 서비스 역할은 다른 Lync Server 역할과 마찬가지로 부트스트래퍼가 배포 하는 Standard Edition 서버에 배치 된 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6fe38-133">In Standard Edition deployments, Persistent Chat Server Service Role is collocated on the Standard Edition server deployed by Bootstrapper, like any other Lync Server role.</span></span> <span data-ttu-id="6fe38-134">Enterprise Edition 배포에서 영구 채팅 서비스 역할은 다른 Lync Server 역할과 마찬가지로 부트스트래퍼에 의해 독립 실행형 컴퓨터에 배포 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6fe38-134">In Enterprise Edition deployments, Persistent Chat Service Role is deployed on stand-alone computers by Bootstrapper, like any other Lync Server role.</span></span>

  - <span data-ttu-id="6fe38-135">**PersistentChatStore:** 모든 채팅 콘텐츠가 저장 되는 영구 채팅 콘텐츠 데이터베이스에 해당 하는 백 엔드 서버입니다.</span><span class="sxs-lookup"><span data-stu-id="6fe38-135">**PersistentChatStore:** Back End Server that corresponds to the Persistent Chat content database, where all the chat content is stored.</span></span>

  - <span data-ttu-id="6fe38-136">**PersistentChatComplianceStore:** 모든 준수 이벤트가 저장 되는 영구 채팅 준수 데이터베이스에 해당 하는 백 엔드 서버 역할입니다.</span><span class="sxs-lookup"><span data-stu-id="6fe38-136">**PersistentChatComplianceStore:** Back End Server role that corresponds to the Persistent Chat Compliance database, where all compliance events are stored.</span></span>

<span data-ttu-id="6fe38-137">이러한 영구 채팅 서버 역할은 선택적 이며, 포괄적인 영구 채팅 서버 기능을 원하는 고객 에게만 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6fe38-137">These Persistent Chat Server roles are optional, and are installed only by customers who want comprehensive Persistent Chat Server functionality.</span></span> <span data-ttu-id="6fe38-138">**PersistentChatComplianceStore** 역할은 영구 채팅 준수를 배포 하도록 선택한 경우에만 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="6fe38-138">The **PersistentChatComplianceStore** role is needed only if you choose to deploy Persistent Chat Compliance.</span></span>

<span data-ttu-id="6fe38-139">**PersistentChatService** 역할은 다음과 같은 두 가지 서비스를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="6fe38-139">The **PersistentChatService** role runs two services:</span></span>

  - <span data-ttu-id="6fe38-140">영구 채팅 서비스</span><span class="sxs-lookup"><span data-stu-id="6fe38-140">Persistent Chat service</span></span>

  - <span data-ttu-id="6fe38-141">영구 채팅 준수 서비스</span><span class="sxs-lookup"><span data-stu-id="6fe38-141">Persistent Chat Compliance service</span></span>

<span data-ttu-id="6fe38-142">이러한 서비스가 각 영구 채팅 서버에서 실행 되도록 하면 다중 서버 영구 채팅 서버 풀에서 이러한 서비스에 고가용성이 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6fe38-142">Having these services run on each Persistent Chat Server provides high availability for these services in a multiserver Persistent Chat Server pool.</span></span>

<span data-ttu-id="6fe38-143">또한 영구 채팅방에서 파일 업로드 및 다운로드를 지원 하기 위해 영구 채팅 서버에는 웹 서비스가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fe38-143">Additionally, to support the file upload and download in Persistent Chat rooms, Persistent Chat Server includes a web service.</span></span> <span data-ttu-id="6fe38-144">이전에는이 서비스를 필수 구성 요소로 설치 하기 위해 영구 채팅 서버, 프런트 엔드 서버 및 필요한 IIS (인터넷 정보 서비스)에 배치 된 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="6fe38-144">Previously, this service was collocated on the Persistent Chat Server, Front End Server and required Internet Information Services (IIS) to be installed as a prerequisite.</span></span> <span data-ttu-id="6fe38-145">Lync Server 2013 영구 채팅 서버에서 파일 업로드/다운로드 웹 서비스는 Lync Server 2013 프런트 엔드 서버와 배치 된 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6fe38-145">In Lync Server 2013 Persistent Chat Server, the File Upload/Download web service is collocated with the Lync Server 2013 Front End Server.</span></span> <span data-ttu-id="6fe38-146">부작용으로, IIS (인터넷 정보 서비스)가 더 이상 영구 채팅 서버에 대 한 필수 구성 요소가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="6fe38-146">As a side effect, Internet Information Services (IIS) is no longer a prerequisite for Persistent Chat Server.</span></span> <span data-ttu-id="6fe38-147">파일 업로드/다운로드 웹 서비스는 IIS (인터넷 정보 서비스) 관리자에서 **atl-persistentchat** 로 식별 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6fe38-147">The File Upload/Download web service is identified as **PersistentChat** in the Internet Information Services (IIS) Manager.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="6fe38-148"><STRONG>PersistentChatService</STRONG> 역할은 해당 프런트 엔드 서버가 Standard Edition&nbsp;&nbsp;프런트 엔드 서버인 경우에만 Lync server 2013 프런트 엔드 서버와 동일한 서버에서 실행 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fe38-148">The <STRONG>PersistentChatService</STRONG> role can run on the same server as a Lync Server 2013&nbsp;Front End Server only if that Front End Server is a Standard Edition&nbsp;Front End Server.</span></span> <span data-ttu-id="6fe38-149"><STRONG>PersistentChatService</STRONG> 역할은 Lync server 2013&nbsp;프런트 엔드 서버와 독립적으로 실행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6fe38-149">The <STRONG>PersistentChatService</STRONG> role cannot run independently of a Lync Server 2013&nbsp;Front End Server.</span></span> <span data-ttu-id="6fe38-150">Lync Server 2013 배포의 컨텍스트에서만 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fe38-150">It can be installed only in the context of a Lync Server 2013 deployment.</span></span>



</div>

<span data-ttu-id="6fe38-151">영구 채팅 서버에서는 조회 서비스가 제거 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="6fe38-151">In Persistent Chat Server, Lookup service has been eliminated.</span></span> <span data-ttu-id="6fe38-152">Lync Server 2010, 그룹 채팅에서 조회 서비스는 모든 그룹 채팅 서버 프런트 엔드 서버에서 실행 되 고 채널 서버 중 하나로 라우팅을 수행 했습니다.</span><span class="sxs-lookup"><span data-stu-id="6fe38-152">In Lync Server 2010, Group Chat, the Lookup service ran on every Group Chat Server Front End Server, and performed routing to one of the Channel Servers.</span></span> <span data-ttu-id="6fe38-153">Lync Server 2013에서는 각 영구 채팅 서버 풀을 적절 한 영구 채팅 서버 풀로 식별 하 고 라우트 하기 위해 Lync Server 프런트 엔드 서버에서 사용 하는 연락처 개체로 표시 되는 연락처 개체를 사용 하 여 라우팅에 의존 합니다. 풀에서 영구 채팅 서버를 실행 하는 컴퓨터 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="6fe38-153">Lync Server 2013 relies on routing by using contact objects, where each Persistent Chat Server pool is represented by a contact object that is used by the Lync Server Front End Servers to identify and route requests to an appropriate Persistent Chat Server pool, and to one of the computers running Persistent Chat Server in the pool.</span></span>

<span data-ttu-id="6fe38-154">Lync Server 2013에는 준수 서비스 수정 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fe38-154">In Lync Server 2013, there are Compliance service modifications:</span></span>

  - <span data-ttu-id="6fe38-155">Lync Server 2010에서는 준수 서비스가 독립 실행형 (배치 된) 및 단일 서버 에서만 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6fe38-155">In Lync Server 2010, the Compliance service ran stand-alone (non-collocated), and only on a single server.</span></span> <span data-ttu-id="6fe38-156">이제 준수 서비스는 영구 채팅 서비스와 함께 모든 영구 채팅 서버 프런트 엔드 서버에서 실행 되며, 따라서 다중 서버 영구 채팅 서버 풀에서 고가용성을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="6fe38-156">The Compliance service now runs on all the Persistent Chat Server Front End Servers, alongside the Persistent Chat service, and thereby provides high availability in a multiserver Persistent Chat Server pool.</span></span> <span data-ttu-id="6fe38-157">준수 데이터베이스에서 데이터를 추출 하 고 다른 시스템 중 하나 (XML 파일, Exchange 호스팅 보관 함 등)로 단일 준수 어댑터를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fe38-157">A single compliance adapter can be configured to extract data from the compliance database and into one of the other systems (XML file, Exchange-hosted archives, and so on).</span></span> <span data-ttu-id="6fe38-158">영구 채팅 서버에는 XML 어댑터가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6fe38-158">Persistent Chat Server includes an XML adapter.</span></span>

  - <span data-ttu-id="6fe38-159">영구 채팅 서비스와 각 영구 채팅 서버 프런트 엔드 서버의 준수 서비스에서 공유 되는 메시지 큐 (MSMQ 라고도 함) 큐는 이제 두 서비스에 의해서만 공유 되는 개인 큐입니다.</span><span class="sxs-lookup"><span data-stu-id="6fe38-159">The Message Queuing (also known as MSMQ) queue that is shared by the Persistent Chat service and the Compliance service on each Persistent Chat Server Front End Server is now a private queue shared only by the two services.</span></span> <span data-ttu-id="6fe38-160">모든 준수 서비스가 동일한 준수 백 엔드 데이터베이스에 기록 합니다.</span><span class="sxs-lookup"><span data-stu-id="6fe38-160">All compliance services write to the same Compliance Back End database.</span></span> <span data-ttu-id="6fe38-161">또한 어댑터의 인스턴스에 데이터를 전송 하기 위해 해당 데이터베이스에서 모두 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="6fe38-161">They also all read from that database, for the purpose of sending the data to their instance of the adapter.</span></span> <span data-ttu-id="6fe38-162">준수 백 엔드 서버는 새 백 엔드 서버 역할로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6fe38-162">The Compliance Back End Server is represented as a new Back End Server role.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="6fe38-163">이전 버전과 마찬가지로 모든 준수 데이터는 한 번만 처리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6fe38-163">As in previous versions, all compliance data is processed only once.</span></span> <span data-ttu-id="6fe38-164">데이터는 다양 한 Lync Server 2013, 영구 채팅 서버 컴퓨터에서 실행 되는 준수 서비스에 의해 호출 되는 모든 어댑터 인스턴스에서 처리 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fe38-164">The data may be processed by any of the adapter instances invoked by the compliance service running on the various Lync Server 2013, Persistent Chat Server computers.</span></span> <span data-ttu-id="6fe38-165">영구 채팅 서버에서 어댑터 인스턴스 중 하나를 통해 데이터를 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fe38-165">In Persistent Chat Server, any one of the adapter instances could process the data.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6fe38-166">메시지 큐를 설치 하는 방법에 대 한 자세한 내용은 배포 설명서의 <A href="lync-server-2013-install-operating-systems-and-prerequisite-software-on-servers.md">서버에 Lync Server 2013의 운영 체제 및 필수 구성 요소 소프트웨어 설치</A> 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="6fe38-166">For information about installing Message Queuing, see <A href="lync-server-2013-install-operating-systems-and-prerequisite-software-on-servers.md">Install operating systems and prerequisite software on servers for Lync Server 2013</A> in the Deployment documentation.</span></span>

    
    </div>

<span data-ttu-id="6fe38-167">Lync Server 2013에서는 고가용성 및 재해 복구를 모두 개선할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fe38-167">In Lync Server 2013, there are improvements in both high availability and disaster recovery:</span></span>

  - <span data-ttu-id="6fe38-168">고가용성 향상: SQL Server 미러링은 데이터 센터 (현장)에서 영구 채팅 서버 콘텐츠 데이터베이스 및 영구 채팅 준수 데이터베이스에 대 한 고가용성을 제공 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6fe38-168">High availability improvements: SQL Server mirroring is used to provide high availability for the Persistent Chat Server content database and Persistent Chat compliance database within a data center (in-site).</span></span>

  - <span data-ttu-id="6fe38-169">향상 된 재해 복구 기능: 영구 채팅 서버는 단일 영구 채팅 서버 풀을 두 사이트, 즉 토폴로지의 단일 논리 풀에서 실제로 풀의 서버와 물리적으로 늘릴 수 있도록 하는 스트레치 된 풀 아키텍처를 지원 합니다. 두 사이트에 위치)</span><span class="sxs-lookup"><span data-stu-id="6fe38-169">Disaster recovery improvements: Persistent Chat Server supports a stretched pool architecture that enables a single Persistent Chat Server pool to be stretched across two sites (that is, a single logical pool in the topology, with servers in the pool physically located across two sites).</span></span> <span data-ttu-id="6fe38-170">사이트 간 재해 복구를 위해 SQL Server 로그 전달이 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6fe38-170">SQL Server Log Shipping is used for cross-site disaster recovery.</span></span>

<span data-ttu-id="6fe38-171">고가용성 및 재해 복구에 대 한 자세한 내용은 배포 설명서의 " [Lync server 2013에서 고가용성 및 재해 복구를 위한 영구 채팅 서버 구성](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md) "을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="6fe38-171">For more information about high availability and disaster recovery, see [Configuring Persistent Chat Server for high availability and disaster recovery in Lync Server 2013](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md) in the Deployment documentation.</span></span>

</div>

<div>

## <a name="key-administration-and-management-changes-for-persistent-chat-server"></a><span data-ttu-id="6fe38-172">영구 채팅 서버에 대 한 주요 관리 및 관리 변경 사항</span><span class="sxs-lookup"><span data-stu-id="6fe38-172">Key Administration and Management Changes for Persistent Chat Server</span></span>

<span data-ttu-id="6fe38-173">Lync Server 2013에서는 다음을 제공 하 여 영구 채팅 서버를 보다 쉽게 관리 하 고 관리할 수 있게 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="6fe38-173">Lync Server 2013 has made it easier to administer and manage Persistent Chat Server by providing:</span></span>

  - <span data-ttu-id="6fe38-174">통합 관리 및 관리</span><span class="sxs-lookup"><span data-stu-id="6fe38-174">Unified administration and management.</span></span> <span data-ttu-id="6fe38-175">Lync Server 2013에서는 Lync 관리자에 게 이미 익숙한 도구를 사용 하 여 영구 채팅 서버를 보다 쉽게 관리 하 고 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fe38-175">Lync Server 2013 makes it easier to manage and administer Persistent Chat Server by using tools that are already familiar to Lync administrators.</span></span> <span data-ttu-id="6fe38-176">영구 채팅 서버에는 Lync Server 제어판과 통합 되어 이전 버전의 그룹 채팅 서버 사용자 인터페이스와 관련 된 성능 문제를 해결 하는 관리 사용자 인터페이스 환경이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fe38-176">Persistent Chat Server includes an administrative user interface experience that is integrated with the Lync Server Control Panel, which addresses performance issues with the previous versions of the Group Chat Server user interface.</span></span> <span data-ttu-id="6fe38-177">또한 영구 채팅 서버에는 영구 채팅 서버 범주를 관리 하 고 관리 하는 Windows PowerShell cmdlet 모음, 영구 채팅 서버 대화방 (채팅방 삭제 및 더 이상 사용 되지 않는 콘텐츠 제거) 및 추가 기능이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fe38-177">Also, Persistent Chat Server includes a collection of Windows PowerShell cmdlets to administer and manage Persistent Chat Server categories, Persistent Chat Server rooms (including deleting rooms and purging obsolete content), and add-ins.</span></span>

  - <span data-ttu-id="6fe38-178">간소화 된 관리 모델</span><span class="sxs-lookup"><span data-stu-id="6fe38-178">Simplified administration model.</span></span> <span data-ttu-id="6fe38-179">Lync Server 2013는 다음과 같은 주요 고객 요구 사항을 해결 하 여 영구 채팅 서버 모델을 변경 하 고 단순화 했습니다.</span><span class="sxs-lookup"><span data-stu-id="6fe38-179">Lync Server 2013 has changed and simplified the Persistent Chat Server model by addressing the following key customer requirements:</span></span>
    
      - <span data-ttu-id="6fe38-180">범위 및 범주에 대 한 중첩 된 복잡 한 계층 구조를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="6fe38-180">Remove the complex nested hierarchies of scopes and categories.</span></span>
    
      - <span data-ttu-id="6fe38-181">영구 채팅 서버로 마이그레이션할 현재 MindAlign 고객에 대해 거부 목록 및 허용 목록 (범위)을 정의할 수 있도록 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="6fe38-181">Support to define deny lists as well as allowed lists (scopes) for current MindAlign customers who are planning to migrate to Persistent Chat Server.</span></span>

</div>

<div>

## <a name="whats-different-about-user-roles-from-previous-group-chat-server-versions"></a><span data-ttu-id="6fe38-182">이전 그룹 채팅 서버 버전의 사용자 역할에 대 한 달라진 점은 무엇 인가요?</span><span class="sxs-lookup"><span data-stu-id="6fe38-182">What’s Different about User Roles from Previous Group Chat Server Versions?</span></span>

<span data-ttu-id="6fe38-183">Lync Server 2010, 그룹 채팅에는 사용자 관리자 역할, 대화방 관리자 역할 및 추가 기능을 관리할 수 있는 Lync Server 관리자 역할이 있었습니다. 영구 채팅 서버는 단순히 영구 채팅 관리자 역할 (다른 Lync와 비슷함)을 제공 합니다. 서버 RBAC (역할 기반 액세스 제어) 역할)</span><span class="sxs-lookup"><span data-stu-id="6fe38-183">Lync Server 2010, Group Chat had a user administrator role, a chat room administrator role and a Lync Server administrator role that could manage add-ins. Persistent Chat Server simply provides a Persistent Chat Administrator role (which is similar to other Lync Server role-based access control (RBAC) roles).</span></span> <span data-ttu-id="6fe38-184">이 RBAC 역할의 구성원 인 사람은 대화방, 추가 기능 및 범주를 관리 하 고 (따라서 이러한 범주에 대 한 사용자 액세스 권한 획득) 영구 채팅 서버 풀을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fe38-184">Anyone who is a member of this RBAC role can manage chat rooms, add-ins, and categories (and therefore gain user access for these categories), and configuration of the Persistent Chat Server pool.</span></span>

</div>

<div>

## <a name="whats-different-about-chat-room-categories-from-previous-group-chat-server-versions"></a><span data-ttu-id="6fe38-185">이전 그룹 채팅 서버 버전의 채팅방 범주에는 어떤 차이가 있나요?</span><span class="sxs-lookup"><span data-stu-id="6fe38-185">What’s Different about Chat Room Categories from Previous Group Chat Server Versions?</span></span>

<span data-ttu-id="6fe38-186">채팅방 범주는 더 이상 중첩 될 수 없으며 루트 범주는 더 이상 수정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6fe38-186">Chat room categories can no longer be nested, and the root category can no longer be modified.</span></span> <span data-ttu-id="6fe38-187">AllowedMembers/DeniedMembers는 이전 그룹 채팅 서버 버전에서 사용 되는 범위를 구성 합니다 (거부 목록 지정은 지원 하지 않음).</span><span class="sxs-lookup"><span data-stu-id="6fe38-187">AllowedMembers/DeniedMembers comprise what a scope used to be in legacy Group Chat Server versions (except that it didn’t support specifying a Denied list).</span></span> <span data-ttu-id="6fe38-188">중첩 된 범주가 없기 때문에 범위를 더 이상 재정의할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6fe38-188">Scopes can no longer be overridden, because there are no nested categories.</span></span> <span data-ttu-id="6fe38-189">Lync Server 2013의 영구 채팅 관리자는 채팅방 범주를 만들고 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fe38-189">A Persistent Chat Administrator in Lync Server 2013 can create and manage chat room categories.</span></span> <span data-ttu-id="6fe38-190">대화방 범주를 만들고 관리 하는 과정에서 영구 채팅 관리자는 특정 범주의 대화방에 대 한 구성원/작성자가 될 수 있는 보안 주체 (Active Directory 그룹/컨테이너/사용자)를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fe38-190">As part of creating and managing chat room categories, a Persistent Chat Administrator can configure principals (Active Directory groups/containers/users) that have access to be members/creators of chat rooms of a particular category.</span></span> <span data-ttu-id="6fe38-191">영구 채팅 관리자는 DeniedMembers을 범주에 추가할 수도 있으며, 이러한 항목은 허용 목록에 대 한 명시적 제외가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6fe38-191">A Persistent Chat Administrator can also add DeniedMembers to a category, and these become explicit exclusions to the allowed list.</span></span> <span data-ttu-id="6fe38-192">DeniedMembers는 AllowedMembers에 포함된 항목을 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="6fe38-192">DeniedMembers override what’s in AllowedMembers.</span></span>

</div>

<div>

## <a name="whats-different-about-chat-room-properties-from-previous-group-chat-server-versions"></a><span data-ttu-id="6fe38-193">이전 그룹 채팅 서버 버전의 대화방 속성에 대 한 다양 한 정보</span><span class="sxs-lookup"><span data-stu-id="6fe38-193">What’s Different about Chat Room Properties from Previous Group Chat Server Versions?</span></span>

<span data-ttu-id="6fe38-194">Lync Server 2013, 영구 채팅 서버에는 열려 있는 대화방의 새로운 개념이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fe38-194">A new concept of open chat rooms exists in Lync Server 2013, Persistent Chat Server.</span></span> <span data-ttu-id="6fe38-195">허용 된 모든 구성원은 단독 구성원 자격 없이 대화방에 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fe38-195">All allowed members can join the chat room, without exclusive membership.</span></span>

<span data-ttu-id="6fe38-196">이전 버전의 영구 채팅 서버에 포함 된 다음과 같은 대화방 속성이 제거 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="6fe38-196">The following chat room properties that were included in previous versions of Persistent Chat Server have been eliminated:</span></span>

  - <span data-ttu-id="6fe38-197">항목: 이제 대화방에 설명이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fe38-197">Topic: A Room now only has a Description.</span></span>

  - <span data-ttu-id="6fe38-198">새 구성원 목록 만들기: 영구 채팅 서버에서 모든 대화방은 빈 구성원으로 시작 되며 허용 되는 구성원에 게 equaling 멤버 자격을 최대화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fe38-198">Create New Member list: In Persistent Chat Server, all chat rooms start with empty membership (and can maximize to a membership equaling the Allowed Members).</span></span>

  - <span data-ttu-id="6fe38-199">파일 업로드: 대화방 당 설정으로 파일 업로드/다운로드가 허용 되는지 여부를 제어 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6fe38-199">File Upload: Used to be a setting per chat room to control whether file upload/downloads were allowed.</span></span> <span data-ttu-id="6fe38-200">이제 범주 수준만 설정 되며 해당 범주의 모든 채팅방에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6fe38-200">This is now set only the category level and applies to all rooms in that category.</span></span>

  - <span data-ttu-id="6fe38-201">채팅 기록: 채팅 기록이 사용 하도록 설정 된 경우이를 제어할 수 있도록 대화방 별로 설정 하는 데 사용 되지만 이제 범주 수준 에서만 설정 되며 해당 범주의 모든 채팅방에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6fe38-201">Chat History: Used to be a setting per chat room to control if Chat History was enabled, but is now set only at the category level and applies to all rooms in that category.</span></span>

  - <span data-ttu-id="6fe38-202">초대: 룸은 항상 범주에 대 한 초대 설정을 상속 합니다. 또는 대화방에서 기능을 끌 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fe38-202">Invites: A room always inherits the Invites setting for the category; or it can be turned off on the room.</span></span> <span data-ttu-id="6fe38-203">범주가 이전에 초대로 설정 된 경우에는 대화방에서 초대를 켤 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6fe38-203">A room cannot turn on Invites if the category was previously set to Invites off.</span></span>

</div>

<div>

## <a name="whats-different-about-policies-from-previous-group-chat-server-versions"></a><span data-ttu-id="6fe38-204">이전 그룹 채팅 서버 버전의 정책에는 어떤 차이가 있나요?</span><span class="sxs-lookup"><span data-stu-id="6fe38-204">What’s Different about Policies from Previous Group Chat Server Versions?</span></span>

<span data-ttu-id="6fe38-205">영구 채팅 서버에는 사용자/풀/사이트/전역 설정에 따라 영구 채팅을 사용 하 여 새로운 Lync 정책이 사용 하도록 설정 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fe38-205">Persistent Chat Server has a new Lync policy enabled with Persistent Chat, per user/pool/site/global settings.</span></span> <span data-ttu-id="6fe38-206">Lync 2013 클라이언트에서 영구 채팅 환경은 영구 채팅에 대 한 정책에 따라 직접 또는 풀/사이트/전역 설정을 통해 사용 하도록 설정 된 사용자만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fe38-206">In the Lync 2013 client, the Persistent Chat environment is available only for users who are enabled by policy for Persistent Chat (either directly or through the pool/site/global setting).</span></span>

<span data-ttu-id="6fe38-207">이전 버전의 그룹 채팅 서버에는 Lync Server 정책에 통합 된 정책이 없었습니다.</span><span class="sxs-lookup"><span data-stu-id="6fe38-207">Previous versions of Group Chat Server did not have any policies integrated into the Lync Server policies.</span></span> <span data-ttu-id="6fe38-208">사용자별 및 범주별/대화방 별로 사용자 당 **파일 업로드** 기능을 사용 하 여 사용자를 사용자 관리자로 지정 하거나, 대화방 관리자로 만들거나, 파일을 업로드 하는 사용자 기능을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fe38-208">On a per user and per category/room basis, by using the **Can Upload Files** per user feature, you could make the user a User administrator, a chat room administrator, or configure the user’s ability to upload files.</span></span> <span data-ttu-id="6fe38-209">영구 채팅 서버 **파일 업로드** 기능은 범주별로만 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6fe38-209">The Persistent Chat Server **File Upload** feature is just per category.</span></span>

</div>

<div>

## <a name="logging"></a><span data-ttu-id="6fe38-210">기록을</span><span class="sxs-lookup"><span data-stu-id="6fe38-210">Logging</span></span>

<span data-ttu-id="6fe38-211">영구 채팅 서버 및 System Center Operations Manager에 대 한 로깅은 Lync Server 2013 추적 로깅에 통합 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fe38-211">Logging for Persistent Chat Server and System Center Operations Manager is integrated into the Lync Server 2013 trace logging.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="6fe38-212">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6fe38-212">See Also</span></span>


[<span data-ttu-id="6fe38-213">Lync Server 2013의 영구 채팅 서버 계획</span><span class="sxs-lookup"><span data-stu-id="6fe38-213">Planning for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-planning-for-persistent-chat-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

