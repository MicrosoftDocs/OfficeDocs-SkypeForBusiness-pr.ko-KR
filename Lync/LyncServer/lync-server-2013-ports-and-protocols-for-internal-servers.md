---
title: 'Lync Server 2013: 내부 서버용 포트 및 프로토콜'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Ports and protocols for internal servers
ms:assetid: c94063f1-e802-4a61-be90-022fc185335e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398833(v=OCS.15)
ms:contentKeyID: 48185402
ms.date: 04/06/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 858ec90cf3811318cc29a902b56ac8ff31c46a22
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48513405"
---
# <a name="ports-and-protocols-for-internal-servers-in-lync-server-2013"></a><span data-ttu-id="25546-102">Lync Server 2013의 내부 서버에 대 한 포트 및 프로토콜</span><span class="sxs-lookup"><span data-stu-id="25546-102">Ports and protocols for internal servers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="25546-103">_**마지막으로 수정 된 항목:** 2016-04-06_</span><span class="sxs-lookup"><span data-stu-id="25546-103">_**Topic Last Modified:** 2016-04-06_</span></span>

<span data-ttu-id="25546-104">이 섹션에서는 Lync Server 배포의 서버, 부하 분산 장치 및 클라이언트에서 사용 되는 포트와 프로토콜에 대해 간략히 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="25546-104">This section summarizes the ports and protocols used by servers, load balancers, and clients in a Lync Server deployment.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="25546-105">Lync 및 Communicator 클라이언트는 일대일 통신에 관여 하는 경우 피어-투-피어 라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="25546-105">Lync and Communicator clients when involved in a one to one communication, is often referred to as peer-to-peer.</span></span> <span data-ttu-id="25546-106">기술적으로 두 클라이언트는 중앙에 있는 IMMCU (인스턴트 메시징 multipoint control unit)를 사용 하 여 일대일 대화로 통신 합니다.</span><span class="sxs-lookup"><span data-stu-id="25546-106">Technically, the two clients are communicating in a one to one conversation, with the Instant Messaging multipoint control unit (IMMCU) in the middle.</span></span> <span data-ttu-id="25546-107">IMMCU는 프런트 엔드 서버의 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="25546-107">The IMMCU is a component of Front End Server.</span></span> <span data-ttu-id="25546-108">필요한 통신 워크플로에 IMMCU를 배치 하면 프런트 엔드 서버에서 사용 하는 통화 정보 기록 및 기타 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25546-108">Placing the IMMCU in the required communication workflow allows call detail recording and other features that the Front End Server enables.</span></span> <span data-ttu-id="25546-109">클라이언트의 동적 원본 포트에서 프런트 엔드 서버 포트 TLS/TCP/5061 (권장 전송 계층 보안을 사용 하는 경우)으로 통신 합니다.</span><span class="sxs-lookup"><span data-stu-id="25546-109">Communication is from a dynamic source port on the client to the Front End Server port TLS/TCP/5061 (assuming the use of the recommended transport layer security).</span></span> <span data-ttu-id="25546-110">Lync Server 및 IMMCU가 활성 상태이 고 사용 가능한 경우에만 피어-투-피어 통신 및 여러 당사자 IM을 기본적으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25546-110">By design, peer-to-peer communication (as well as multi-party IM) is possible only when Lync Server and the IMMCU is active and available.</span></span>



</div>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="25546-111">포트 및 프로토콜 세부 정보</span><span class="sxs-lookup"><span data-stu-id="25546-111">Port and Protocol Details</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="25546-112">Lync server가 방화벽에서 필요한 포트를 여는 경우에는 서버에서 Lync Server 서비스를 시작 하기 전에 Windows 방화벽이 실행 중 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="25546-112">Windows Firewall must be running before you start the Lync Server services on a server, because that is when Lync Server opens the required ports in the firewall.</span></span>



</div>

<span data-ttu-id="25546-113">에 지 구성 요소의 방화벽 구성에 대 한 자세한 내용은 [Lync Server 2013에 대 한 외부 A/V 방화벽 및 포트 요구 사항 확인](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="25546-113">For details about firewall configuration for edge components, see [Determine external A/V firewall and port requirements for Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md).</span></span>

<span data-ttu-id="25546-114">다음 표에는 각 내부 서버 역할에서 열어야 하는 포트가 나열되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25546-114">The following table lists the ports that need to be open on each internal server role.</span></span>

### <a name="required-server-ports-by-server-role"></a><span data-ttu-id="25546-115">필요한 서버 포트(서버 역할별)</span><span class="sxs-lookup"><span data-stu-id="25546-115">Required Server Ports (by Server Role)</span></span>

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="25546-116">서버 역할</span><span class="sxs-lookup"><span data-stu-id="25546-116">Server role</span></span></th>
<th><span data-ttu-id="25546-117">서비스 이름</span><span class="sxs-lookup"><span data-stu-id="25546-117">Service name</span></span></th>
<th><span data-ttu-id="25546-118">포트</span><span class="sxs-lookup"><span data-stu-id="25546-118">Port</span></span></th>
<th><span data-ttu-id="25546-119">Protocol(프로토콜)</span><span class="sxs-lookup"><span data-stu-id="25546-119">Protocol</span></span></th>
<th><span data-ttu-id="25546-120">참고</span><span class="sxs-lookup"><span data-stu-id="25546-120">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="25546-121">모든 서버</span><span class="sxs-lookup"><span data-stu-id="25546-121">All Servers</span></span></p></td>
<td><p><span data-ttu-id="25546-122">SQL Browser</span><span class="sxs-lookup"><span data-stu-id="25546-122">SQL Browser</span></span></p></td>
<td><p><span data-ttu-id="25546-123">1434</span><span class="sxs-lookup"><span data-stu-id="25546-123">1434</span></span></p></td>
<td><p><span data-ttu-id="25546-124">P</span><span class="sxs-lookup"><span data-stu-id="25546-124">UDP</span></span></p></td>
<td><p><span data-ttu-id="25546-125">중앙 관리 저장소 데이터베이스의 복제 된 로컬 복사본에 대 한 SQL 브라우저입니다.</span><span class="sxs-lookup"><span data-stu-id="25546-125">SQL Browser for the local replicated copy of the Central Management Store database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25546-126">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="25546-126">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="25546-127">Lync Server Front-End 서비스</span><span class="sxs-lookup"><span data-stu-id="25546-127">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="25546-128">5060</span><span class="sxs-lookup"><span data-stu-id="25546-128">5060</span></span></p></td>
<td><p><span data-ttu-id="25546-129">TCP</span><span class="sxs-lookup"><span data-stu-id="25546-129">TCP</span></span></p></td>
<td><p><span data-ttu-id="25546-130">필요에 따라 Standard Edition Server 및 프런트 엔드 서버에서 원격 호출 제어 서버와 같은 트러스트된 서비스에 대한 고정 경로에 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="25546-130">Optionally used by Standard Edition servers and Front End Servers for static routes to trusted services, such as remote call control servers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="25546-131">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="25546-131">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="25546-132">Lync Server Front-End 서비스</span><span class="sxs-lookup"><span data-stu-id="25546-132">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="25546-133">5061</span><span class="sxs-lookup"><span data-stu-id="25546-133">5061</span></span></p></td>
<td><p><span data-ttu-id="25546-134">TCP(TLS)</span><span class="sxs-lookup"><span data-stu-id="25546-134">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="25546-p102">Standard Edition Server 및 프런트 엔드 풀에서 서버 간 모든 내부 SIP 통신(MTLS), 서버와 클라이언트 간 SIP 통신(TLS) 및 프런트 엔드 서버와 중재 서버 간 SIP 통신(MTLS)에 사용됩니다. 또한 모니터링 서버와의 통신에도 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="25546-p102">Used by Standard Edition servers and Front End pools for all internal SIP communications between servers (MTLS), for SIP communications between Server and Client (TLS) and for SIP communications between Front End Servers and Mediation Servers (MTLS). Also used for communications with Monitoring Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25546-137">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="25546-137">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="25546-138">Lync Server Front-End 서비스</span><span class="sxs-lookup"><span data-stu-id="25546-138">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="25546-139">444</span><span class="sxs-lookup"><span data-stu-id="25546-139">444</span></span></p></td>
<td><p><span data-ttu-id="25546-140">H</span><span class="sxs-lookup"><span data-stu-id="25546-140">HTTPS</span></span></p>
<p><span data-ttu-id="25546-141">TCP</span><span class="sxs-lookup"><span data-stu-id="25546-141">TCP</span></span></p></td>
<td><p><span data-ttu-id="25546-142">포커스 (회의 상태를 관리 하는 Lync Server 구성 요소)와 개별 서버 간의 HTTPS 통신에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="25546-142">Used for HTTPS communication between the Focus (the Lync Server component that manages conference state) and the individual servers.</span></span></p>
<p><span data-ttu-id="25546-143">이 포트는 Sba (survivable 분기 기기와 프런트 엔드 서버 간의 TCP 통신에도 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="25546-143">This port is also used for TCP communication between Survivable Branch Appliances and Front End Servers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="25546-144">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="25546-144">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="25546-145">Lync Server Front-End 서비스</span><span class="sxs-lookup"><span data-stu-id="25546-145">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="25546-146">135</span><span class="sxs-lookup"><span data-stu-id="25546-146">135</span></span></p></td>
<td><p><span data-ttu-id="25546-147">DCOM 및 RPC(원격 프로시저 호출)</span><span class="sxs-lookup"><span data-stu-id="25546-147">DCOM and remote procedure call (RPC)</span></span></p></td>
<td><p><span data-ttu-id="25546-148">사용자 이동, User Replicator 동기화 및 주소록 동기화와 같은 DCOM 기반 작업에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="25546-148">Used for DCOM based operations such as Moving Users, User Replicator Synchronization, and Address Book Synchronization.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25546-149">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="25546-149">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="25546-150">Lync Server IM 회의 서비스</span><span class="sxs-lookup"><span data-stu-id="25546-150">Lync Server IM Conferencing service</span></span></p></td>
<td><p><span data-ttu-id="25546-151">5062</span><span class="sxs-lookup"><span data-stu-id="25546-151">5062</span></span></p></td>
<td><p><span data-ttu-id="25546-152">TCP</span><span class="sxs-lookup"><span data-stu-id="25546-152">TCP</span></span></p></td>
<td><p><span data-ttu-id="25546-153">IM(인스턴트 메시징) 회의의 받는 SIP 요청에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="25546-153">Used for incoming SIP requests for instant messaging (IM) conferencing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="25546-154">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="25546-154">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="25546-155">Lync Server 웹 회의 서비스</span><span class="sxs-lookup"><span data-stu-id="25546-155">Lync Server Web Conferencing service</span></span></p></td>
<td><p><span data-ttu-id="25546-156">8057</span><span class="sxs-lookup"><span data-stu-id="25546-156">8057</span></span></p></td>
<td><p><span data-ttu-id="25546-157">TCP(TLS)</span><span class="sxs-lookup"><span data-stu-id="25546-157">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="25546-158">클라이언트에서 PSOM(영구적 공유 개체 모델) 연결을 수신 대기하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="25546-158">Used to listen for Persistent Shared Object Model (PSOM) connections from client.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25546-159">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="25546-159">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="25546-160">Lync Server 웹 회의 호환성 서비스</span><span class="sxs-lookup"><span data-stu-id="25546-160">Lync Server Web Conferencing Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="25546-161">8058</span><span class="sxs-lookup"><span data-stu-id="25546-161">8058</span></span></p></td>
<td><p><span data-ttu-id="25546-162">TCP(TLS)</span><span class="sxs-lookup"><span data-stu-id="25546-162">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="25546-163">Live Meeting 클라이언트 및 이전 버전의 Lync Server에서 PSOM (영구 공유 개체 모델) 연결을 수신 대기 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="25546-163">Used to listen for Persistent Shared Object Model (PSOM) connections from the Live Meeting client and previous versions of Lync Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="25546-164">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="25546-164">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="25546-165">Lync Server 오디오/비디오 회의 서비스</span><span class="sxs-lookup"><span data-stu-id="25546-165">Lync Server Audio/Video Conferencing service</span></span></p></td>
<td><p><span data-ttu-id="25546-166">5063</span><span class="sxs-lookup"><span data-stu-id="25546-166">5063</span></span></p></td>
<td><p><span data-ttu-id="25546-167">TCP</span><span class="sxs-lookup"><span data-stu-id="25546-167">TCP</span></span></p></td>
<td><p><span data-ttu-id="25546-168">A/V(오디오/비디오) 회의의 받는 SIP 요청에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="25546-168">Used for incoming SIP requests for audio/video (A/V) conferencing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25546-169">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="25546-169">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="25546-170">Lync Server 오디오/비디오 회의 서비스</span><span class="sxs-lookup"><span data-stu-id="25546-170">Lync Server Audio/Video Conferencing service</span></span></p></td>
<td><p><span data-ttu-id="25546-171">57501-65535</span><span class="sxs-lookup"><span data-stu-id="25546-171">57501-65535</span></span></p></td>
<td><p><span data-ttu-id="25546-172">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="25546-172">TCP/UDP</span></span></p></td>
<td><p><span data-ttu-id="25546-173">비디오 회의에 사용되는 미디어 포트 범위입니다.</span><span class="sxs-lookup"><span data-stu-id="25546-173">Media port range used for video conferencing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="25546-174">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="25546-174">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="25546-175">Lync Server 웹 호환성 서비스</span><span class="sxs-lookup"><span data-stu-id="25546-175">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="25546-176">80</span><span class="sxs-lookup"><span data-stu-id="25546-176">80</span></span></p></td>
<td><p><span data-ttu-id="25546-177">HTTP</span><span class="sxs-lookup"><span data-stu-id="25546-177">HTTP</span></span></p></td>
<td><p><span data-ttu-id="25546-178">HTTPS가 사용되지 않을 경우 프런트 엔드 서버에서 웹 팜 FQDN(IIS 웹 구성 요소에서 사용하는 URL)으로의 통신에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="25546-178">Used for communication from Front End Servers to the web farm FQDNs (the URLs used by IIS web components) when HTTPS is not used.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25546-179">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="25546-179">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="25546-180">Lync Server 웹 호환성 서비스</span><span class="sxs-lookup"><span data-stu-id="25546-180">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="25546-181">443</span><span class="sxs-lookup"><span data-stu-id="25546-181">443</span></span></p></td>
<td><p><span data-ttu-id="25546-182">H</span><span class="sxs-lookup"><span data-stu-id="25546-182">HTTPS</span></span></p></td>
<td><p><span data-ttu-id="25546-183">프런트 엔드 서버에서 웹 팜 FQDN(IIS 웹 구성 요소에서 사용하는 URL)으로의 통신에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="25546-183">Used for communication from Front End Servers to the web farm FQDNs (the URLs used by IIS web components).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="25546-184">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="25546-184">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="25546-185">Lync Server 웹 호환성 서비스</span><span class="sxs-lookup"><span data-stu-id="25546-185">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="25546-186">8080</span><span class="sxs-lookup"><span data-stu-id="25546-186">8080</span></span></p></td>
<td><p><span data-ttu-id="25546-187">TCP 및 HTTP</span><span class="sxs-lookup"><span data-stu-id="25546-187">TCP and HTTP</span></span></p></td>
<td><p><span data-ttu-id="25546-188">외부 액세스용 웹 구성 요소에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="25546-188">Used by web components for external access.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25546-189">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="25546-189">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="25546-190">웹 서버 구성 요소</span><span class="sxs-lookup"><span data-stu-id="25546-190">Web server component</span></span></p></td>
<td><p><span data-ttu-id="25546-191">4443</span><span class="sxs-lookup"><span data-stu-id="25546-191">4443</span></span></p></td>
<td><p><span data-ttu-id="25546-192">H</span><span class="sxs-lookup"><span data-stu-id="25546-192">HTTPS</span></span></p></td>
<td><p><span data-ttu-id="25546-193">자동 검색 로그인에 대 한 HTTPS (역방향 프록시) 및 HTTPS 프런트 엔드 풀 간 통신</span><span class="sxs-lookup"><span data-stu-id="25546-193">HTTPS (from Reverse Proxy) and HTTPS Front End inter-pool communications for Autodiscover sign-in.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="25546-194">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="25546-194">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="25546-195">웹 서버 구성 요소</span><span class="sxs-lookup"><span data-stu-id="25546-195">Web server component</span></span></p></td>
<td><p><span data-ttu-id="25546-196">8060</span><span class="sxs-lookup"><span data-stu-id="25546-196">8060</span></span></p></td>
<td><p><span data-ttu-id="25546-197">TCP(MTLS)</span><span class="sxs-lookup"><span data-stu-id="25546-197">TCP (MTLS)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25546-198">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="25546-198">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="25546-199">웹 서버 구성 요소</span><span class="sxs-lookup"><span data-stu-id="25546-199">Web server component</span></span></p></td>
<td><p><span data-ttu-id="25546-200">8061</span><span class="sxs-lookup"><span data-stu-id="25546-200">8061</span></span></p></td>
<td><p><span data-ttu-id="25546-201">TCP(MTLS)</span><span class="sxs-lookup"><span data-stu-id="25546-201">TCP (MTLS)</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="25546-202">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="25546-202">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="25546-203">Mobility Services 구성 요소</span><span class="sxs-lookup"><span data-stu-id="25546-203">Mobility Services component</span></span></p></td>
<td><p><span data-ttu-id="25546-204">5086</span><span class="sxs-lookup"><span data-stu-id="25546-204">5086</span></span></p></td>
<td><p><span data-ttu-id="25546-205">TCP(MTLS)</span><span class="sxs-lookup"><span data-stu-id="25546-205">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="25546-206">모바일 서비스 내부 프로세스에서 사용 하는 SIP 포트</span><span class="sxs-lookup"><span data-stu-id="25546-206">SIP port used by Mobility Services internal processes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25546-207">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="25546-207">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="25546-208">Mobility Services 구성 요소</span><span class="sxs-lookup"><span data-stu-id="25546-208">Mobility Services component</span></span></p></td>
<td><p><span data-ttu-id="25546-209">5087</span><span class="sxs-lookup"><span data-stu-id="25546-209">5087</span></span></p></td>
<td><p><span data-ttu-id="25546-210">TCP(MTLS)</span><span class="sxs-lookup"><span data-stu-id="25546-210">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="25546-211">모바일 서비스 내부 프로세스에서 사용 하는 SIP 포트</span><span class="sxs-lookup"><span data-stu-id="25546-211">SIP port used by Mobility Services internal processes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="25546-212">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="25546-212">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="25546-213">Mobility Services 구성 요소</span><span class="sxs-lookup"><span data-stu-id="25546-213">Mobility Services component</span></span></p></td>
<td><p><span data-ttu-id="25546-214">443</span><span class="sxs-lookup"><span data-stu-id="25546-214">443</span></span></p></td>
<td><p><span data-ttu-id="25546-215">H</span><span class="sxs-lookup"><span data-stu-id="25546-215">HTTPS</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25546-216">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="25546-216">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="25546-217">Lync Server 회의 수행자 서비스 (전화 접속 회의)</span><span class="sxs-lookup"><span data-stu-id="25546-217">Lync Server Conferencing Attendant service (dial-in conferencing)</span></span></p></td>
<td><p><span data-ttu-id="25546-218">5064</span><span class="sxs-lookup"><span data-stu-id="25546-218">5064</span></span></p></td>
<td><p><span data-ttu-id="25546-219">TCP</span><span class="sxs-lookup"><span data-stu-id="25546-219">TCP</span></span></p></td>
<td><p><span data-ttu-id="25546-220">전화 접속 회의의 받는 SIP 요청에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="25546-220">Used for incoming SIP requests for dial-in conferencing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="25546-221">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="25546-221">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="25546-222">Lync Server 회의 수행자 서비스 (전화 접속 회의)</span><span class="sxs-lookup"><span data-stu-id="25546-222">Lync Server Conferencing Attendant service (dial-in conferencing)</span></span></p></td>
<td><p><span data-ttu-id="25546-223">5072</span><span class="sxs-lookup"><span data-stu-id="25546-223">5072</span></span></p></td>
<td><p><span data-ttu-id="25546-224">TCP</span><span class="sxs-lookup"><span data-stu-id="25546-224">TCP</span></span></p></td>
<td><p><span data-ttu-id="25546-225">받는 전화 회의에 대 한 들어오는 SIP 요청에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="25546-225">Used for incoming SIP requests for Attendant (dial in conferencing).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25546-226">배치된 중재 서버를 실행하는 프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="25546-226">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="25546-227">Lync Server 중재 서비스</span><span class="sxs-lookup"><span data-stu-id="25546-227">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="25546-228">5070</span><span class="sxs-lookup"><span data-stu-id="25546-228">5070</span></span></p></td>
<td><p><span data-ttu-id="25546-229">TCP</span><span class="sxs-lookup"><span data-stu-id="25546-229">TCP</span></span></p></td>
<td><p><span data-ttu-id="25546-230">중재 서버에서 프런트 엔드 서버에서 중재 서버로의 받는 요청에 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="25546-230">Used by the Mediation Server for incoming requests from the Front End Server to the Mediation Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="25546-231">배치된 중재 서버를 실행하는 프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="25546-231">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="25546-232">Lync Server 중재 서비스</span><span class="sxs-lookup"><span data-stu-id="25546-232">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="25546-233">5067</span><span class="sxs-lookup"><span data-stu-id="25546-233">5067</span></span></p></td>
<td><p><span data-ttu-id="25546-234">TCP(TLS)</span><span class="sxs-lookup"><span data-stu-id="25546-234">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="25546-235">PSTN 게이트웨이에서 중재 서버로의 받는 SIP 요청에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="25546-235">Used for incoming SIP requests from the PSTN gateway to the Mediation Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25546-236">배치된 중재 서버를 실행하는 프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="25546-236">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="25546-237">Lync Server 중재 서비스</span><span class="sxs-lookup"><span data-stu-id="25546-237">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="25546-238">5068</span><span class="sxs-lookup"><span data-stu-id="25546-238">5068</span></span></p></td>
<td><p><span data-ttu-id="25546-239">TCP</span><span class="sxs-lookup"><span data-stu-id="25546-239">TCP</span></span></p></td>
<td><p><span data-ttu-id="25546-240">PSTN 게이트웨이에서 중재 서버로의 받는 SIP 요청에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="25546-240">Used for incoming SIP requests from the PSTN gateway to the Mediation Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="25546-241">배치된 중재 서버를 실행하는 프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="25546-241">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="25546-242">Lync Server 중재 서비스</span><span class="sxs-lookup"><span data-stu-id="25546-242">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="25546-243">5081</span><span class="sxs-lookup"><span data-stu-id="25546-243">5081</span></span></p></td>
<td><p><span data-ttu-id="25546-244">TCP</span><span class="sxs-lookup"><span data-stu-id="25546-244">TCP</span></span></p></td>
<td><p><span data-ttu-id="25546-245">중재 서버에서 PSTN 게이트웨이로의 보내는 SIP 요청에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="25546-245">Used for outgoing SIP requests from the Mediation Server to the PSTN gateway.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25546-246">배치된 중재 서버를 실행하는 프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="25546-246">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="25546-247">Lync Server 중재 서비스</span><span class="sxs-lookup"><span data-stu-id="25546-247">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="25546-248">5082</span><span class="sxs-lookup"><span data-stu-id="25546-248">5082</span></span></p></td>
<td><p><span data-ttu-id="25546-249">TCP(TLS)</span><span class="sxs-lookup"><span data-stu-id="25546-249">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="25546-250">중재 서버에서 PSTN 게이트웨이로의 보내는 SIP 요청에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="25546-250">Used for outgoing SIP requests from the Mediation Server to the PSTN gateway.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="25546-251">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="25546-251">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="25546-252">Lync Server 응용 프로그램 공유 서비스</span><span class="sxs-lookup"><span data-stu-id="25546-252">Lync Server Application Sharing service</span></span></p></td>
<td><p><span data-ttu-id="25546-253">5065</span><span class="sxs-lookup"><span data-stu-id="25546-253">5065</span></span></p></td>
<td><p><span data-ttu-id="25546-254">TCP</span><span class="sxs-lookup"><span data-stu-id="25546-254">TCP</span></span></p></td>
<td><p><span data-ttu-id="25546-255">응용 프로그램 공유의 받는 SIP 수신 대기 요청에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="25546-255">Used for incoming SIP listening requests for application sharing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25546-256">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="25546-256">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="25546-257">Lync Server 응용 프로그램 공유 서비스</span><span class="sxs-lookup"><span data-stu-id="25546-257">Lync Server Application Sharing service</span></span></p></td>
<td><p><span data-ttu-id="25546-258">49152-65535</span><span class="sxs-lookup"><span data-stu-id="25546-258">49152-65535</span></span></p></td>
<td><p><span data-ttu-id="25546-259">TCP</span><span class="sxs-lookup"><span data-stu-id="25546-259">TCP</span></span></p></td>
<td><p><span data-ttu-id="25546-260">응용 프로그램 공유에 사용되는 미디어 포트 범위입니다.</span><span class="sxs-lookup"><span data-stu-id="25546-260">Media port range used for application sharing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="25546-261">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="25546-261">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="25546-262">Lync Server 회의 알림 서비스</span><span class="sxs-lookup"><span data-stu-id="25546-262">Lync Server Conferencing Announcement service</span></span></p></td>
<td><p><span data-ttu-id="25546-263">5073</span><span class="sxs-lookup"><span data-stu-id="25546-263">5073</span></span></p></td>
<td><p><span data-ttu-id="25546-264">TCP</span><span class="sxs-lookup"><span data-stu-id="25546-264">TCP</span></span></p></td>
<td><p><span data-ttu-id="25546-265">Lync Server 회의 알림 서비스에 대 한 들어오는 SIP 요청에 사용 됩니다 (전화 접속 회의의 경우).</span><span class="sxs-lookup"><span data-stu-id="25546-265">Used for incoming SIP requests for the Lync Server Conferencing Announcement service (that is, for dial-in conferencing).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25546-266">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="25546-266">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="25546-267">Lync Server 통화 대기 서비스</span><span class="sxs-lookup"><span data-stu-id="25546-267">Lync Server Call Park service</span></span></p></td>
<td><p><span data-ttu-id="25546-268">5075</span><span class="sxs-lookup"><span data-stu-id="25546-268">5075</span></span></p></td>
<td><p><span data-ttu-id="25546-269">TCP</span><span class="sxs-lookup"><span data-stu-id="25546-269">TCP</span></span></p></td>
<td><p><span data-ttu-id="25546-270">통화 대기 응용 프로그램의 받는 SIP 요청에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="25546-270">Used for incoming SIP requests for the Call Park application.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="25546-271">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="25546-271">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="25546-272">Lync Server Audio 테스트 서비스</span><span class="sxs-lookup"><span data-stu-id="25546-272">Lync Server Audio Test service</span></span></p></td>
<td><p><span data-ttu-id="25546-273">5076</span><span class="sxs-lookup"><span data-stu-id="25546-273">5076</span></span></p></td>
<td><p><span data-ttu-id="25546-274">TCP</span><span class="sxs-lookup"><span data-stu-id="25546-274">TCP</span></span></p></td>
<td><p><span data-ttu-id="25546-275">오디오 테스트 서비스의 받는 SIP 요청에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="25546-275">Used for incoming SIP requests for the Audio Test service.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25546-276">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="25546-276">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="25546-277">해당 없음</span><span class="sxs-lookup"><span data-stu-id="25546-277">Not applicable</span></span></p></td>
<td><p><span data-ttu-id="25546-278">5066</span><span class="sxs-lookup"><span data-stu-id="25546-278">5066</span></span></p></td>
<td><p><span data-ttu-id="25546-279">TCP</span><span class="sxs-lookup"><span data-stu-id="25546-279">TCP</span></span></p></td>
<td><p><span data-ttu-id="25546-280">아웃바운드 E9-1-1(Enhanced 9-1-1) 게이트웨이에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="25546-280">Used for outbound Enhanced 9-1-1 (E9-1-1) gateway.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="25546-281">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="25546-281">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="25546-282">Lync Server 응답 그룹 서비스</span><span class="sxs-lookup"><span data-stu-id="25546-282">Lync Server Response Group service</span></span></p></td>
<td><p><span data-ttu-id="25546-283">5071</span><span class="sxs-lookup"><span data-stu-id="25546-283">5071</span></span></p></td>
<td><p><span data-ttu-id="25546-284">TCP</span><span class="sxs-lookup"><span data-stu-id="25546-284">TCP</span></span></p></td>
<td><p><span data-ttu-id="25546-285">응답 그룹 응용 프로그램의 받는 SIP 요청에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="25546-285">Used for incoming SIP requests for the Response Group application.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25546-286">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="25546-286">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="25546-287">Lync Server 응답 그룹 서비스</span><span class="sxs-lookup"><span data-stu-id="25546-287">Lync Server Response Group service</span></span></p></td>
<td><p><span data-ttu-id="25546-288">8404</span><span class="sxs-lookup"><span data-stu-id="25546-288">8404</span></span></p></td>
<td><p><span data-ttu-id="25546-289">TCP(MTLS)</span><span class="sxs-lookup"><span data-stu-id="25546-289">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="25546-290">응답 그룹 응용 프로그램의 받는 SIP 요청에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="25546-290">Used for incoming SIP requests for the Response Group application.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="25546-291">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="25546-291">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="25546-292">Lync Server 대역폭 정책 서비스</span><span class="sxs-lookup"><span data-stu-id="25546-292">Lync Server Bandwidth Policy Service</span></span></p></td>
<td><p><span data-ttu-id="25546-293">5080</span><span class="sxs-lookup"><span data-stu-id="25546-293">5080</span></span></p></td>
<td><p><span data-ttu-id="25546-294">TCP</span><span class="sxs-lookup"><span data-stu-id="25546-294">TCP</span></span></p></td>
<td><p><span data-ttu-id="25546-295">A/V 에지 TURN 트래픽에 대한 대역폭 정책 서비스의 통화 허용 제어에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="25546-295">Used for call admission control by the Bandwidth Policy service for A/V Edge TURN traffic.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25546-296">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="25546-296">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="25546-297">Lync Server 대역폭 정책 서비스</span><span class="sxs-lookup"><span data-stu-id="25546-297">Lync Server Bandwidth Policy Service</span></span></p></td>
<td><p><span data-ttu-id="25546-298">448</span><span class="sxs-lookup"><span data-stu-id="25546-298">448</span></span></p></td>
<td><p><span data-ttu-id="25546-299">TCP</span><span class="sxs-lookup"><span data-stu-id="25546-299">TCP</span></span></p></td>
<td><p><span data-ttu-id="25546-300">Lync Server 대역폭 정책 서비스의 통화 허용 제어에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="25546-300">Used for call admission control by the Lync Server Bandwidth Policy Service.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="25546-301">중앙 관리 저장소가 상주 하는 프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="25546-301">Front End Servers where the Central Management store resides</span></span></p></td>
<td><p><span data-ttu-id="25546-302">Lync Server Master Replicator 에이전트 서비스</span><span class="sxs-lookup"><span data-stu-id="25546-302">Lync Server Master Replicator Agent service</span></span></p></td>
<td><p><span data-ttu-id="25546-303">445</span><span class="sxs-lookup"><span data-stu-id="25546-303">445</span></span></p></td>
<td><p><span data-ttu-id="25546-304">TCP</span><span class="sxs-lookup"><span data-stu-id="25546-304">TCP</span></span></p></td>
<td><p><span data-ttu-id="25546-305">중앙 관리 저장소의 구성 데이터를 Lync Server를 실행 하는 서버로 밀어 넣는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="25546-305">Used to push configuration data from the Central Management store to servers running Lync Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25546-306">모든 서버</span><span class="sxs-lookup"><span data-stu-id="25546-306">All Servers</span></span></p></td>
<td><p><span data-ttu-id="25546-307">SQL Browser</span><span class="sxs-lookup"><span data-stu-id="25546-307">SQL Browser</span></span></p></td>
<td><p><span data-ttu-id="25546-308">1434</span><span class="sxs-lookup"><span data-stu-id="25546-308">1434</span></span></p></td>
<td><p><span data-ttu-id="25546-309">P</span><span class="sxs-lookup"><span data-stu-id="25546-309">UDP</span></span></p></td>
<td><p><span data-ttu-id="25546-310">로컬 SQL Server 인스턴스에 중앙 관리 저장소 데이터의 로컬 복제 복사본에 대 한 SQL 브라우저</span><span class="sxs-lookup"><span data-stu-id="25546-310">SQL Browser for local replicated copy of Central Management store data in local SQL Server instance</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="25546-311">모든 내부 서버</span><span class="sxs-lookup"><span data-stu-id="25546-311">All internal servers</span></span></p></td>
<td><p><span data-ttu-id="25546-312">다양 한</span><span class="sxs-lookup"><span data-stu-id="25546-312">Various</span></span></p></td>
<td><p><span data-ttu-id="25546-313">49152-57500</span><span class="sxs-lookup"><span data-stu-id="25546-313">49152-57500</span></span></p></td>
<td><p><span data-ttu-id="25546-314">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="25546-314">TCP/UDP</span></span></p></td>
<td><p><span data-ttu-id="25546-315">모든 내부 서버의 오디오 회의에 사용되는 미디어 포트 범위입니다.</span><span class="sxs-lookup"><span data-stu-id="25546-315">Media port range used for audio conferencing on all internal servers.</span></span> <span data-ttu-id="25546-316">오디오를 종료 하는 모든 서버에서 사용: 프런트 엔드 서버 (Lync Server 회의 수행자 서비스, Lync Server 회의 알림 서비스 및 Lync Server 오디오/비디오 회의 서비스) 및 중재 서버</span><span class="sxs-lookup"><span data-stu-id="25546-316">Used by all servers that terminate audio: Front End Servers (for Lync Server Conferencing Attendant service, Lync Server Conferencing Announcement service, and Lync Server Audio/Video Conferencing service), and Mediation Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25546-317">Office Web Apps 서버</span><span class="sxs-lookup"><span data-stu-id="25546-317">Office Web Apps Servers</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="25546-318">443</span><span class="sxs-lookup"><span data-stu-id="25546-318">443</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="25546-319">Lync Server 2013에서 Office Web Apps 서버에 연결 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="25546-319">Used by Lync Server 2013 to connect to Office Web Apps Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="25546-320">디렉터</span><span class="sxs-lookup"><span data-stu-id="25546-320">Directors</span></span></p></td>
<td><p><span data-ttu-id="25546-321">Lync Server Front-End 서비스</span><span class="sxs-lookup"><span data-stu-id="25546-321">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="25546-322">5060</span><span class="sxs-lookup"><span data-stu-id="25546-322">5060</span></span></p></td>
<td><p><span data-ttu-id="25546-323">TCP</span><span class="sxs-lookup"><span data-stu-id="25546-323">TCP</span></span></p></td>
<td><p><span data-ttu-id="25546-324">필요에 따라 원격 통화 제어 서버와 같은 트러스트된 서비스에 대한 고정 경로에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="25546-324">Optionally used for static routes to trusted services, such as remote call control servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25546-325">디렉터</span><span class="sxs-lookup"><span data-stu-id="25546-325">Directors</span></span></p></td>
<td><p><span data-ttu-id="25546-326">Lync Server Front-End 서비스</span><span class="sxs-lookup"><span data-stu-id="25546-326">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="25546-327">444</span><span class="sxs-lookup"><span data-stu-id="25546-327">444</span></span></p></td>
<td><p><span data-ttu-id="25546-328">H</span><span class="sxs-lookup"><span data-stu-id="25546-328">HTTPS</span></span></p>
<p><span data-ttu-id="25546-329">TCP</span><span class="sxs-lookup"><span data-stu-id="25546-329">TCP</span></span></p></td>
<td><p><span data-ttu-id="25546-330">프런트 엔드 및 디렉터 간의 서버 간 통신.</span><span class="sxs-lookup"><span data-stu-id="25546-330">Inter-server communication between Front End and Director.</span></span> <span data-ttu-id="25546-331">또한 클라이언트 인증서가 프런트 엔드 서버로 게시 되거나 클라이언트 인증서가 이미 게시 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="25546-331">Additionally, client certificate publish (to Front End Servers) or validate if the client certificate has already been published.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="25546-332">디렉터</span><span class="sxs-lookup"><span data-stu-id="25546-332">Directors</span></span></p></td>
<td><p><span data-ttu-id="25546-333">Lync Server 웹 호환성 서비스</span><span class="sxs-lookup"><span data-stu-id="25546-333">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="25546-334">80</span><span class="sxs-lookup"><span data-stu-id="25546-334">80</span></span></p></td>
<td><p><span data-ttu-id="25546-335">TCP</span><span class="sxs-lookup"><span data-stu-id="25546-335">TCP</span></span></p></td>
<td><p><span data-ttu-id="25546-p105">디렉터에서 웹 팜 FQDN(IIS 웹 구성 요소에서 사용하는 URL)으로의 초기 통신에 사용됩니다. 정상 작동의 경우 포트 443 및 TCP 프로토콜 유형을 사용하여 HTTPS 트래픽으로 전환됩니다.</span><span class="sxs-lookup"><span data-stu-id="25546-p105">Used for initial communication from Directors to the web farm FQDNs (the URLs used by IIS web components). In normal operation, will switch to HTTPS traffic, using port 443 and protocol type TCP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25546-338">디렉터</span><span class="sxs-lookup"><span data-stu-id="25546-338">Directors</span></span></p></td>
<td><p><span data-ttu-id="25546-339">Lync Server 웹 호환성 서비스</span><span class="sxs-lookup"><span data-stu-id="25546-339">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="25546-340">443</span><span class="sxs-lookup"><span data-stu-id="25546-340">443</span></span></p></td>
<td><p><span data-ttu-id="25546-341">H</span><span class="sxs-lookup"><span data-stu-id="25546-341">HTTPS</span></span></p></td>
<td><p><span data-ttu-id="25546-342">디렉터에서 웹 팜 FQDN(IIS 웹 구성 요소에서 사용하는 URL)으로의 통신에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="25546-342">Used for communication from Directors to the web farm FQDNs (the URLs used by IIS web components).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="25546-343">디렉터</span><span class="sxs-lookup"><span data-stu-id="25546-343">Directors</span></span></p></td>
<td><p><span data-ttu-id="25546-344">Lync Server Front-End 서비스</span><span class="sxs-lookup"><span data-stu-id="25546-344">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="25546-345">5061</span><span class="sxs-lookup"><span data-stu-id="25546-345">5061</span></span></p></td>
<td><p><span data-ttu-id="25546-346">TCP</span><span class="sxs-lookup"><span data-stu-id="25546-346">TCP</span></span></p></td>
<td><p><span data-ttu-id="25546-347">서버 간 내부 통신과 클라이언트 연결에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="25546-347">Used for internal communications between servers and for client connections.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25546-348">중재 서버</span><span class="sxs-lookup"><span data-stu-id="25546-348">Mediation Servers</span></span></p></td>
<td><p><span data-ttu-id="25546-349">Lync Server 중재 서비스</span><span class="sxs-lookup"><span data-stu-id="25546-349">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="25546-350">5070</span><span class="sxs-lookup"><span data-stu-id="25546-350">5070</span></span></p></td>
<td><p><span data-ttu-id="25546-351">TCP</span><span class="sxs-lookup"><span data-stu-id="25546-351">TCP</span></span></p></td>
<td><p><span data-ttu-id="25546-352">중재 서버가 프런트 엔드 서버에서 받는 요청에 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="25546-352">Used by the Mediation Server for incoming requests from the Front End Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="25546-353">중재 서버</span><span class="sxs-lookup"><span data-stu-id="25546-353">Mediation Servers</span></span></p></td>
<td><p><span data-ttu-id="25546-354">Lync Server 중재 서비스</span><span class="sxs-lookup"><span data-stu-id="25546-354">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="25546-355">5067</span><span class="sxs-lookup"><span data-stu-id="25546-355">5067</span></span></p></td>
<td><p><span data-ttu-id="25546-356">TCP(TLS)</span><span class="sxs-lookup"><span data-stu-id="25546-356">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="25546-357">PSTN 게이트웨이에서 받는 SIP 요청에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="25546-357">Used for incoming SIP requests from the PSTN gateway.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25546-358">중재 서버</span><span class="sxs-lookup"><span data-stu-id="25546-358">Mediation Servers</span></span></p></td>
<td><p><span data-ttu-id="25546-359">Lync Server 중재 서비스</span><span class="sxs-lookup"><span data-stu-id="25546-359">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="25546-360">5068</span><span class="sxs-lookup"><span data-stu-id="25546-360">5068</span></span></p></td>
<td><p><span data-ttu-id="25546-361">TCP</span><span class="sxs-lookup"><span data-stu-id="25546-361">TCP</span></span></p></td>
<td><p><span data-ttu-id="25546-362">PSTN 게이트웨이에서 받는 SIP 요청에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="25546-362">Used for incoming SIP requests from the PSTN gateway.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="25546-363">중재 서버</span><span class="sxs-lookup"><span data-stu-id="25546-363">Mediation Servers</span></span></p></td>
<td><p><span data-ttu-id="25546-364">Lync Server 중재 서비스</span><span class="sxs-lookup"><span data-stu-id="25546-364">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="25546-365">5070</span><span class="sxs-lookup"><span data-stu-id="25546-365">5070</span></span></p></td>
<td><p><span data-ttu-id="25546-366">TCP(MTLS)</span><span class="sxs-lookup"><span data-stu-id="25546-366">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="25546-367">프런트 엔드 서버의 SIP 요청에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="25546-367">Used for SIP requests from the Front End Servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25546-368">영구 채팅 프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="25546-368">Persistent Chat Front End Server</span></span></p></td>
<td><p><span data-ttu-id="25546-369">영구 채팅 SIP</span><span class="sxs-lookup"><span data-stu-id="25546-369">Persistent Chat SIP</span></span></p></td>
<td><p><span data-ttu-id="25546-370">5041</span><span class="sxs-lookup"><span data-stu-id="25546-370">5041</span></span></p></td>
<td><p><span data-ttu-id="25546-371">TCP(MTLS)</span><span class="sxs-lookup"><span data-stu-id="25546-371">TCP (MTLS)</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="25546-372">영구 채팅 프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="25546-372">Persistent Chat Front End Server</span></span></p></td>
<td><p><span data-ttu-id="25546-373">영구 채팅 WCF (Windows Communication Foundation)</span><span class="sxs-lookup"><span data-stu-id="25546-373">Persistent Chat Windows Communication Foundation (WCF)</span></span></p></td>
<td><p><span data-ttu-id="25546-374">881</span><span class="sxs-lookup"><span data-stu-id="25546-374">881</span></span></p></td>
<td><p><span data-ttu-id="25546-375">TCP (TLS) 및 TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="25546-375">TCP (TLS) and TCP (MTLS)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25546-376">영구 채팅 프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="25546-376">Persistent Chat Front End Server</span></span></p></td>
<td><p><span data-ttu-id="25546-377">영구 채팅 파일 전송 서비스</span><span class="sxs-lookup"><span data-stu-id="25546-377">Persistent Chat File Transfer Service</span></span></p></td>
<td><p><span data-ttu-id="25546-378">443</span><span class="sxs-lookup"><span data-stu-id="25546-378">443</span></span></p></td>
<td><p><span data-ttu-id="25546-379">TCP(TLS)</span><span class="sxs-lookup"><span data-stu-id="25546-379">TCP (TLS)</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="25546-380">일부 원격 통화 제어 시나리오의 경우 프런트 엔드 서버 또는 디렉터 및 PBX 간 TCP 연결이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="25546-380">Some remote call control scenarios require a TCP connection between the Front End Server or Director and the PBX.</span></span> <span data-ttu-id="25546-381">Lync Server에서는 더 이상 TCP 포트 5060을 사용 하지 않지만 원격 통화 제어 배포 중에는 RCC Line Server FQDN을 프런트 엔드 서버 또는 디렉터가 PBX 시스템에 연결 하는 데 사용할 TCP 포트와 연결 하는 신뢰할 수 있는 서버 구성을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="25546-381">Although Lync Server no longer uses TCP port 5060, during remote call control deployment you create a trusted server configuration, which associates the RCC Line Server FQDN with the TCP port that the Front End Server or Director will use to connect to the PBX system.</span></span> <span data-ttu-id="25546-382">자세한 내용은 Lync Server 관리 셸 설명서에서 <STRONG>CsTrustedApplicationComputer</STRONG> cmdlet을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="25546-382">For details, see the <STRONG>CsTrustedApplicationComputer</STRONG> cmdlet in the Lync Server Management Shell documentation.</span></span>



</div>

<span data-ttu-id="25546-383">다음 표에서는 하드웨어 부하 분산만 사용하는 풀(DNS 부하 분산 사용 안 함)의 경우 하드웨어 부하 분산 장치를 열어야 하는 포트를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="25546-383">For your pools that use only hardware load balancing (not DNS load balancing), the following table shows the ports that need to open the hardware load balancers.</span></span>

### <a name="hardware-load-balancer-ports-if-using-only-hardware-load-balancing"></a><span data-ttu-id="25546-384">하드웨어 부하 분산만 사용하는 경우 하드웨어 부하 분산 장치 포트</span><span class="sxs-lookup"><span data-stu-id="25546-384">Hardware Load Balancer Ports if Using Only Hardware Load Balancing</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="25546-385">부하 분산 장치</span><span class="sxs-lookup"><span data-stu-id="25546-385">Load Balancer</span></span></th>
<th><span data-ttu-id="25546-386">포트</span><span class="sxs-lookup"><span data-stu-id="25546-386">Port</span></span></th>
<th><span data-ttu-id="25546-387">Protocol(프로토콜)</span><span class="sxs-lookup"><span data-stu-id="25546-387">Protocol</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="25546-388">프런트 엔드 서버 부하 분산 장치</span><span class="sxs-lookup"><span data-stu-id="25546-388">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="25546-389">5061</span><span class="sxs-lookup"><span data-stu-id="25546-389">5061</span></span></p></td>
<td><p><span data-ttu-id="25546-390">TCP(TLS)</span><span class="sxs-lookup"><span data-stu-id="25546-390">TCP (TLS)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25546-391">프런트 엔드 서버 부하 분산 장치</span><span class="sxs-lookup"><span data-stu-id="25546-391">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="25546-392">444</span><span class="sxs-lookup"><span data-stu-id="25546-392">444</span></span></p></td>
<td><p><span data-ttu-id="25546-393">H</span><span class="sxs-lookup"><span data-stu-id="25546-393">HTTPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="25546-394">프런트 엔드 서버 부하 분산 장치</span><span class="sxs-lookup"><span data-stu-id="25546-394">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="25546-395">135</span><span class="sxs-lookup"><span data-stu-id="25546-395">135</span></span></p></td>
<td><p><span data-ttu-id="25546-396">DCOM 및 RPC(원격 프로시저 호출)</span><span class="sxs-lookup"><span data-stu-id="25546-396">DCOM and remote procedure call (RPC)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25546-397">프런트 엔드 서버 부하 분산 장치</span><span class="sxs-lookup"><span data-stu-id="25546-397">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="25546-398">80</span><span class="sxs-lookup"><span data-stu-id="25546-398">80</span></span></p></td>
<td><p><span data-ttu-id="25546-399">HTTP</span><span class="sxs-lookup"><span data-stu-id="25546-399">HTTP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="25546-400">프런트 엔드 서버 부하 분산 장치</span><span class="sxs-lookup"><span data-stu-id="25546-400">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="25546-401">8080</span><span class="sxs-lookup"><span data-stu-id="25546-401">8080</span></span></p></td>
<td><p><span data-ttu-id="25546-402">TCP - 프런트 엔드 서버에서 루트 인증서의 클라이언트 및 장치 검색 - 클라이언트 및 장치는 NTLM으로 인증됩니다.</span><span class="sxs-lookup"><span data-stu-id="25546-402">TCP - Client and device retrieval of root certificate from Front End Server – clients and devices authenticated by NTLM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25546-403">프런트 엔드 서버 부하 분산 장치</span><span class="sxs-lookup"><span data-stu-id="25546-403">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="25546-404">443</span><span class="sxs-lookup"><span data-stu-id="25546-404">443</span></span></p></td>
<td><p><span data-ttu-id="25546-405">H</span><span class="sxs-lookup"><span data-stu-id="25546-405">HTTPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="25546-406">프런트 엔드 서버 부하 분산 장치</span><span class="sxs-lookup"><span data-stu-id="25546-406">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="25546-407">4443</span><span class="sxs-lookup"><span data-stu-id="25546-407">4443</span></span></p></td>
<td><p><span data-ttu-id="25546-408">HTTPS(역방향 프록시)</span><span class="sxs-lookup"><span data-stu-id="25546-408">HTTPS (from reverse proxy)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25546-409">프런트 엔드 서버 부하 분산 장치</span><span class="sxs-lookup"><span data-stu-id="25546-409">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="25546-410">5072</span><span class="sxs-lookup"><span data-stu-id="25546-410">5072</span></span></p></td>
<td><p><span data-ttu-id="25546-411">TCP</span><span class="sxs-lookup"><span data-stu-id="25546-411">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="25546-412">프런트 엔드 서버 부하 분산 장치</span><span class="sxs-lookup"><span data-stu-id="25546-412">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="25546-413">5073</span><span class="sxs-lookup"><span data-stu-id="25546-413">5073</span></span></p></td>
<td><p><span data-ttu-id="25546-414">TCP</span><span class="sxs-lookup"><span data-stu-id="25546-414">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25546-415">프런트 엔드 서버 부하 분산 장치</span><span class="sxs-lookup"><span data-stu-id="25546-415">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="25546-416">5075</span><span class="sxs-lookup"><span data-stu-id="25546-416">5075</span></span></p></td>
<td><p><span data-ttu-id="25546-417">TCP</span><span class="sxs-lookup"><span data-stu-id="25546-417">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="25546-418">프런트 엔드 서버 부하 분산 장치</span><span class="sxs-lookup"><span data-stu-id="25546-418">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="25546-419">5076</span><span class="sxs-lookup"><span data-stu-id="25546-419">5076</span></span></p></td>
<td><p><span data-ttu-id="25546-420">TCP</span><span class="sxs-lookup"><span data-stu-id="25546-420">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25546-421">프런트 엔드 서버 부하 분산 장치</span><span class="sxs-lookup"><span data-stu-id="25546-421">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="25546-422">5071</span><span class="sxs-lookup"><span data-stu-id="25546-422">5071</span></span></p></td>
<td><p><span data-ttu-id="25546-423">TCP</span><span class="sxs-lookup"><span data-stu-id="25546-423">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="25546-424">프런트 엔드 서버 부하 분산 장치</span><span class="sxs-lookup"><span data-stu-id="25546-424">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="25546-425">5080</span><span class="sxs-lookup"><span data-stu-id="25546-425">5080</span></span></p></td>
<td><p><span data-ttu-id="25546-426">TCP</span><span class="sxs-lookup"><span data-stu-id="25546-426">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25546-427">프런트 엔드 서버 부하 분산 장치</span><span class="sxs-lookup"><span data-stu-id="25546-427">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="25546-428">448</span><span class="sxs-lookup"><span data-stu-id="25546-428">448</span></span></p></td>
<td><p><span data-ttu-id="25546-429">TCP</span><span class="sxs-lookup"><span data-stu-id="25546-429">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="25546-430">중재 서버 부하 분산 장치</span><span class="sxs-lookup"><span data-stu-id="25546-430">Mediation Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="25546-431">5070</span><span class="sxs-lookup"><span data-stu-id="25546-431">5070</span></span></p></td>
<td><p><span data-ttu-id="25546-432">TCP</span><span class="sxs-lookup"><span data-stu-id="25546-432">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25546-433">프런트 엔드 서버 부하 분산 장치 (풀에서 중재 서버도 실행 되는 경우)</span><span class="sxs-lookup"><span data-stu-id="25546-433">Front End Server load balancer (if the pool also runs Mediation Server)</span></span></p></td>
<td><p><span data-ttu-id="25546-434">5070</span><span class="sxs-lookup"><span data-stu-id="25546-434">5070</span></span></p></td>
<td><p><span data-ttu-id="25546-435">TCP</span><span class="sxs-lookup"><span data-stu-id="25546-435">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="25546-436">디렉터 부하 분산 장치</span><span class="sxs-lookup"><span data-stu-id="25546-436">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="25546-437">443</span><span class="sxs-lookup"><span data-stu-id="25546-437">443</span></span></p></td>
<td><p><span data-ttu-id="25546-438">H</span><span class="sxs-lookup"><span data-stu-id="25546-438">HTTPS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25546-439">디렉터 부하 분산 장치</span><span class="sxs-lookup"><span data-stu-id="25546-439">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="25546-440">444</span><span class="sxs-lookup"><span data-stu-id="25546-440">444</span></span></p></td>
<td><p><span data-ttu-id="25546-441">H</span><span class="sxs-lookup"><span data-stu-id="25546-441">HTTPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="25546-442">디렉터 부하 분산 장치</span><span class="sxs-lookup"><span data-stu-id="25546-442">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="25546-443">5061</span><span class="sxs-lookup"><span data-stu-id="25546-443">5061</span></span></p></td>
<td><p><span data-ttu-id="25546-444">TCP</span><span class="sxs-lookup"><span data-stu-id="25546-444">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25546-445">디렉터 부하 분산 장치</span><span class="sxs-lookup"><span data-stu-id="25546-445">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="25546-446">4443</span><span class="sxs-lookup"><span data-stu-id="25546-446">4443</span></span></p></td>
<td><p><span data-ttu-id="25546-447">HTTPS(역방향 프록시)</span><span class="sxs-lookup"><span data-stu-id="25546-447">HTTPS (from reverse proxy)</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="25546-p107">DNS 부하 분산을 사용하는 프런트 엔드 풀 및 디렉터 풀에는 하드웨어 부하 분산 장치도 배포되어 있어야 합니다. 다음 표에서는 이러한 하드웨어 부하 분산 장치에서 열어야 하는 포트를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="25546-p107">Your Front End pools and Director pools that use DNS load balancing also must have a hardware load balancer deployed. The following table shows the ports that need to be open on these hardware load balancers.</span></span>

### <a name="hardware-load-balancer-ports-if-using-dns-load-balancing"></a><span data-ttu-id="25546-450">DNS 부하 분산을 사용하는 경우 하드웨어 부하 분산 장치 포트</span><span class="sxs-lookup"><span data-stu-id="25546-450">Hardware Load Balancer Ports if Using DNS Load Balancing</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="25546-451">부하 분산 장치</span><span class="sxs-lookup"><span data-stu-id="25546-451">Load Balancer</span></span></th>
<th><span data-ttu-id="25546-452">포트</span><span class="sxs-lookup"><span data-stu-id="25546-452">Port</span></span></th>
<th><span data-ttu-id="25546-453">Protocol(프로토콜)</span><span class="sxs-lookup"><span data-stu-id="25546-453">Protocol</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="25546-454">프런트 엔드 서버 부하 분산 장치</span><span class="sxs-lookup"><span data-stu-id="25546-454">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="25546-455">80</span><span class="sxs-lookup"><span data-stu-id="25546-455">80</span></span></p></td>
<td><p><span data-ttu-id="25546-456">HTTP</span><span class="sxs-lookup"><span data-stu-id="25546-456">HTTP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25546-457">프런트 엔드 서버 부하 분산 장치</span><span class="sxs-lookup"><span data-stu-id="25546-457">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="25546-458">443</span><span class="sxs-lookup"><span data-stu-id="25546-458">443</span></span></p></td>
<td><p><span data-ttu-id="25546-459">H</span><span class="sxs-lookup"><span data-stu-id="25546-459">HTTPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="25546-460">프런트 엔드 서버 부하 분산 장치</span><span class="sxs-lookup"><span data-stu-id="25546-460">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="25546-461">8080</span><span class="sxs-lookup"><span data-stu-id="25546-461">8080</span></span></p></td>
<td><p><span data-ttu-id="25546-462">TCP - 프런트 엔드 서버에서 루트 인증서의 클라이언트 및 장치 검색 - 클라이언트 및 장치는 NTLM으로 인증됩니다.</span><span class="sxs-lookup"><span data-stu-id="25546-462">TCP - Client and device retrieval of root certificate from Front End Server – clients and devices authenticated by NTLM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25546-463">프런트 엔드 서버 부하 분산 장치</span><span class="sxs-lookup"><span data-stu-id="25546-463">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="25546-464">4443</span><span class="sxs-lookup"><span data-stu-id="25546-464">4443</span></span></p></td>
<td><p><span data-ttu-id="25546-465">HTTPS(역방향 프록시)</span><span class="sxs-lookup"><span data-stu-id="25546-465">HTTPS (from reverse proxy)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="25546-466">디렉터 부하 분산 장치</span><span class="sxs-lookup"><span data-stu-id="25546-466">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="25546-467">443</span><span class="sxs-lookup"><span data-stu-id="25546-467">443</span></span></p></td>
<td><p><span data-ttu-id="25546-468">H</span><span class="sxs-lookup"><span data-stu-id="25546-468">HTTPS</span></span></p></td>
</tr>
<tr class="even">
<td> </td>
<td> </td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="25546-469">디렉터 부하 분산 장치</span><span class="sxs-lookup"><span data-stu-id="25546-469">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="25546-470">4443</span><span class="sxs-lookup"><span data-stu-id="25546-470">4443</span></span></p></td>
<td><p><span data-ttu-id="25546-471">HTTPS(역방향 프록시)</span><span class="sxs-lookup"><span data-stu-id="25546-471">HTTPS (from reverse proxy)</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="required-client-ports"></a><span data-ttu-id="25546-472">필요한 클라이언트 포트</span><span class="sxs-lookup"><span data-stu-id="25546-472">Required Client Ports</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="25546-473">구성 요소</span><span class="sxs-lookup"><span data-stu-id="25546-473">Component</span></span></th>
<th><span data-ttu-id="25546-474">포트</span><span class="sxs-lookup"><span data-stu-id="25546-474">Port</span></span></th>
<th><span data-ttu-id="25546-475">Protocol(프로토콜)</span><span class="sxs-lookup"><span data-stu-id="25546-475">Protocol</span></span></th>
<th><span data-ttu-id="25546-476">참고</span><span class="sxs-lookup"><span data-stu-id="25546-476">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="25546-477">클라이언트</span><span class="sxs-lookup"><span data-stu-id="25546-477">Clients</span></span></p></td>
<td><p><span data-ttu-id="25546-478">67/68</span><span class="sxs-lookup"><span data-stu-id="25546-478">67/68</span></span></p></td>
<td><p><span data-ttu-id="25546-479">서버의</span><span class="sxs-lookup"><span data-stu-id="25546-479">DHCP</span></span></p></td>
<td><p><span data-ttu-id="25546-480">Lync Server에서 등록자 FQDN을 찾는 데 사용 됩니다 (즉, DNS SRV에 오류가 발생 하 여 수동 설정이 구성 되지 않은 경우).</span><span class="sxs-lookup"><span data-stu-id="25546-480">Used by Lync Server to find the Registrar FQDN (that is, if DNS SRV fails and manual settings are not configured).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25546-481">클라이언트</span><span class="sxs-lookup"><span data-stu-id="25546-481">Clients</span></span></p></td>
<td><p><span data-ttu-id="25546-482">443</span><span class="sxs-lookup"><span data-stu-id="25546-482">443</span></span></p></td>
<td><p><span data-ttu-id="25546-483">TCP(TLS)</span><span class="sxs-lookup"><span data-stu-id="25546-483">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="25546-484">외부 사용자 액세스의 클라이언트-서버 SIP 트래픽에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="25546-484">Used for client-to-server SIP traffic for external user access.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="25546-485">클라이언트</span><span class="sxs-lookup"><span data-stu-id="25546-485">Clients</span></span></p></td>
<td><p><span data-ttu-id="25546-486">443</span><span class="sxs-lookup"><span data-stu-id="25546-486">443</span></span></p></td>
<td><p><span data-ttu-id="25546-487">TCP(PSOM/TLS)</span><span class="sxs-lookup"><span data-stu-id="25546-487">TCP (PSOM/TLS)</span></span></p></td>
<td><p><span data-ttu-id="25546-488">웹 회의 세션에 대한 외부 사용자 액세스에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="25546-488">Used for external user access to web conferencing sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25546-489">클라이언트</span><span class="sxs-lookup"><span data-stu-id="25546-489">Clients</span></span></p></td>
<td><p><span data-ttu-id="25546-490">443</span><span class="sxs-lookup"><span data-stu-id="25546-490">443</span></span></p></td>
<td><p><span data-ttu-id="25546-491">TCP(STUN/MSTURN)</span><span class="sxs-lookup"><span data-stu-id="25546-491">TCP (STUN/MSTURN)</span></span></p></td>
<td><p><span data-ttu-id="25546-492">A/V 세션 및 미디어(TCP)에 대한 외부 사용자 액세스에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="25546-492">Used for external user access to A/V sessions and media (TCP)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="25546-493">클라이언트</span><span class="sxs-lookup"><span data-stu-id="25546-493">Clients</span></span></p></td>
<td><p><span data-ttu-id="25546-494">3478</span><span class="sxs-lookup"><span data-stu-id="25546-494">3478</span></span></p></td>
<td><p><span data-ttu-id="25546-495">UDP(STUN/MSTURN)</span><span class="sxs-lookup"><span data-stu-id="25546-495">UDP (STUN/MSTURN)</span></span></p></td>
<td><p><span data-ttu-id="25546-496">A/V 세션 및 미디어에 대 한 외부 사용자 액세스 (UDP)에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="25546-496">Used for external user access to A/V sessions and media (UDP)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25546-497">클라이언트</span><span class="sxs-lookup"><span data-stu-id="25546-497">Clients</span></span></p></td>
<td><p><span data-ttu-id="25546-498">5061</span><span class="sxs-lookup"><span data-stu-id="25546-498">5061</span></span></p></td>
<td><p><span data-ttu-id="25546-499">TCP(MTLS)</span><span class="sxs-lookup"><span data-stu-id="25546-499">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="25546-500">외부 사용자 액세스의 클라이언트-서버 SIP 트래픽에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="25546-500">Used for client-to-server SIP traffic for external user access.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="25546-501">클라이언트</span><span class="sxs-lookup"><span data-stu-id="25546-501">Clients</span></span></p></td>
<td><p><span data-ttu-id="25546-502">6891-6901</span><span class="sxs-lookup"><span data-stu-id="25546-502">6891-6901</span></span></p></td>
<td><p><span data-ttu-id="25546-503">TCP</span><span class="sxs-lookup"><span data-stu-id="25546-503">TCP</span></span></p></td>
<td><p><span data-ttu-id="25546-504">Lync 클라이언트와 이전 클라이언트 (Microsoft Office Communications Server 2007 R2, Microsoft Office Communications Server 2007 및 Live Communications Server 2005의 클라이언트) 간의 파일 전송에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="25546-504">Used for file transfer between Lync clients and previous clients (clients of Microsoft Office Communications Server 2007 R2, Microsoft Office Communications Server 2007, and Live Communications Server 2005).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25546-505">클라이언트</span><span class="sxs-lookup"><span data-stu-id="25546-505">Clients</span></span></p></td>
<td><p><span data-ttu-id="25546-506">1024-65535 \*</span><span class="sxs-lookup"><span data-stu-id="25546-506">1024-65535 \*</span></span></p></td>
<td><p><span data-ttu-id="25546-507">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="25546-507">TCP/UDP</span></span></p></td>
<td><p><span data-ttu-id="25546-508">오디오 포트 범위(최소 20개 포트 필요)</span><span class="sxs-lookup"><span data-stu-id="25546-508">Audio port range (minimum of 20 ports required)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="25546-509">클라이언트</span><span class="sxs-lookup"><span data-stu-id="25546-509">Clients</span></span></p></td>
<td><p><span data-ttu-id="25546-510">1024-65535 \*</span><span class="sxs-lookup"><span data-stu-id="25546-510">1024-65535 \*</span></span></p></td>
<td><p><span data-ttu-id="25546-511">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="25546-511">TCP/UDP</span></span></p></td>
<td><p><span data-ttu-id="25546-512">비디오 포트 범위(최소 20개 포트 필요)</span><span class="sxs-lookup"><span data-stu-id="25546-512">Video port range (minimum of 20 ports required).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25546-513">클라이언트</span><span class="sxs-lookup"><span data-stu-id="25546-513">Clients</span></span></p></td>
<td><p><span data-ttu-id="25546-514">1024-65535 \*</span><span class="sxs-lookup"><span data-stu-id="25546-514">1024-65535 \*</span></span></p></td>
<td><p><span data-ttu-id="25546-515">TCP</span><span class="sxs-lookup"><span data-stu-id="25546-515">TCP</span></span></p></td>
<td><p><span data-ttu-id="25546-516">피어 투 피어 파일 전송(회의 파일 전송의 경우 클라이언트가 PSOM 사용).</span><span class="sxs-lookup"><span data-stu-id="25546-516">Peer-to-peer file transfer (for conferencing file transfer, clients use PSOM).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="25546-517">클라이언트</span><span class="sxs-lookup"><span data-stu-id="25546-517">Clients</span></span></p></td>
<td><p><span data-ttu-id="25546-518">1024-65535 \*</span><span class="sxs-lookup"><span data-stu-id="25546-518">1024-65535 \*</span></span></p></td>
<td><p><span data-ttu-id="25546-519">TCP</span><span class="sxs-lookup"><span data-stu-id="25546-519">TCP</span></span></p></td>
<td><p><span data-ttu-id="25546-520">응용 프로그램 공유</span><span class="sxs-lookup"><span data-stu-id="25546-520">Application sharing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25546-521">Aastra 6721ip 공통 영역 전화</span><span class="sxs-lookup"><span data-stu-id="25546-521">Aastra 6721ip common area phone</span></span></p>
<p><span data-ttu-id="25546-522">Aastra 6725ip 일반 전화기</span><span class="sxs-lookup"><span data-stu-id="25546-522">Aastra 6725ip desk phone</span></span></p>
<p><span data-ttu-id="25546-523">HP 4110 IP 전화(공통 영역 전화)</span><span class="sxs-lookup"><span data-stu-id="25546-523">HP 4110 IP Phone (common area phone)</span></span></p>
<p><span data-ttu-id="25546-524">HP 4120 IP 전화(일반 전화기)</span><span class="sxs-lookup"><span data-stu-id="25546-524">HP 4120 IP Phone (desk phone)</span></span></p>
<p><span data-ttu-id="25546-525">Polycom CX500 IP 공통 영역 전화</span><span class="sxs-lookup"><span data-stu-id="25546-525">Polycom CX500 IP common area phone</span></span></p>
<p><span data-ttu-id="25546-526">Polycom CX600 IP 일반 전화기</span><span class="sxs-lookup"><span data-stu-id="25546-526">Polycom CX600 IP desk phone</span></span></p>
<p><span data-ttu-id="25546-527">Polycom CX700 IP 일반 전화기</span><span class="sxs-lookup"><span data-stu-id="25546-527">Polycom CX700 IP desk phone</span></span></p>
<p><span data-ttu-id="25546-528">Polycom CX3000 IP 회의 전화</span><span class="sxs-lookup"><span data-stu-id="25546-528">Polycom CX3000 IP conference phone</span></span></p></td>
<td><p><span data-ttu-id="25546-529">67/68</span><span class="sxs-lookup"><span data-stu-id="25546-529">67/68</span></span></p></td>
<td><p><span data-ttu-id="25546-530">서버의</span><span class="sxs-lookup"><span data-stu-id="25546-530">DHCP</span></span></p></td>
<td><p><span data-ttu-id="25546-531">나열 된 장치에서 Lync Server 인증서, 프로 비전 FQDN 및 등록자 FQDN을 찾는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="25546-531">Used by the listed devices to find the Lync Server certificate, provisioning FQDN, and Registrar FQDN.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="25546-532">**\*** 이러한 미디어 유형에 대 한 특정 포트를 구성 하려면 Get-csconferencingconfiguration cmdlet (ClientMediaPortRangeEnabled, ClientMediaPort 및 ClientMediaPortRange 매개 변수)을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="25546-532">**\*** To configure specific ports for these media types, use the CsConferencingConfiguration cmdlet (ClientMediaPortRangeEnabled, ClientMediaPort, and ClientMediaPortRange parameters).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="25546-533">Lync 클라이언트에 대 한 프로그램 설정에서는 클라이언트 컴퓨터에 필요한 운영 체제 방화벽 예외를 자동으로 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="25546-533">The set programs for Lync clients automatically create the required operating-system firewall exceptions on the client computer.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="25546-534">외부 사용자 액세스를 위해 사용되는 포트는 클라이언트가 조직의 방화벽을 통과해야 하는 모든 시나리오에 필요합니다(예: 외부 통신 또는 다른 조직에서 호스트되는 모임).</span><span class="sxs-lookup"><span data-stu-id="25546-534">The ports that are used for external user access are required for any scenario in which the client must traverse the organization’s firewall (for example, any external communications or meetings hosted by other organizations).</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

