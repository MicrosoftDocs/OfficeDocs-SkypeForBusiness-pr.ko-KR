---
title: 'Lync Server 2013: 내부 서버용 포트 및 프로토콜'
description: 'Lync Server 2013: 내부 서버용 포트 및 프로토콜'
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
ms.openlocfilehash: d7d8f12c78c5dec5caacaeb1156f4d228b7cd591
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566362"
---
# <a name="ports-and-protocols-for-internal-servers-in-lync-server-2013"></a><span data-ttu-id="fdb49-103">Lync Server 2013의 내부 서버에 대 한 포트 및 프로토콜</span><span class="sxs-lookup"><span data-stu-id="fdb49-103">Ports and protocols for internal servers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fdb49-104">_**마지막으로 수정 된 항목:** 2016-04-06_</span><span class="sxs-lookup"><span data-stu-id="fdb49-104">_**Topic Last Modified:** 2016-04-06_</span></span>

<span data-ttu-id="fdb49-105">이 섹션에서는 Lync Server 배포의 서버, 부하 분산 장치 및 클라이언트에서 사용 되는 포트와 프로토콜에 대해 간략히 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="fdb49-105">This section summarizes the ports and protocols used by servers, load balancers, and clients in a Lync Server deployment.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="fdb49-106">Lync 및 Communicator 클라이언트는 일대일 통신에 관여 하는 경우 피어-투-피어 라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="fdb49-106">Lync and Communicator clients when involved in a one to one communication, is often referred to as peer-to-peer.</span></span> <span data-ttu-id="fdb49-107">기술적으로 두 클라이언트는 중앙에 있는 IMMCU (인스턴트 메시징 multipoint control unit)를 사용 하 여 일대일 대화로 통신 합니다.</span><span class="sxs-lookup"><span data-stu-id="fdb49-107">Technically, the two clients are communicating in a one to one conversation, with the Instant Messaging multipoint control unit (IMMCU) in the middle.</span></span> <span data-ttu-id="fdb49-108">IMMCU는 프런트 엔드 서버의 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="fdb49-108">The IMMCU is a component of Front End Server.</span></span> <span data-ttu-id="fdb49-109">필요한 통신 워크플로에 IMMCU를 배치 하면 프런트 엔드 서버에서 사용 하는 통화 정보 기록 및 기타 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fdb49-109">Placing the IMMCU in the required communication workflow allows call detail recording and other features that the Front End Server enables.</span></span> <span data-ttu-id="fdb49-110">클라이언트의 동적 원본 포트에서 프런트 엔드 서버 포트 TLS/TCP/5061 (권장 전송 계층 보안을 사용 하는 경우)으로 통신 합니다.</span><span class="sxs-lookup"><span data-stu-id="fdb49-110">Communication is from a dynamic source port on the client to the Front End Server port TLS/TCP/5061 (assuming the use of the recommended transport layer security).</span></span> <span data-ttu-id="fdb49-111">Lync Server 및 IMMCU가 활성 상태이 고 사용 가능한 경우에만 피어-투-피어 통신 및 여러 당사자 IM을 기본적으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fdb49-111">By design, peer-to-peer communication (as well as multi-party IM) is possible only when Lync Server and the IMMCU is active and available.</span></span>



</div>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="fdb49-112">포트 및 프로토콜 세부 정보</span><span class="sxs-lookup"><span data-stu-id="fdb49-112">Port and Protocol Details</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="fdb49-113">Lync server가 방화벽에서 필요한 포트를 여는 경우에는 서버에서 Lync Server 서비스를 시작 하기 전에 Windows 방화벽이 실행 중 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fdb49-113">Windows Firewall must be running before you start the Lync Server services on a server, because that is when Lync Server opens the required ports in the firewall.</span></span>



</div>

<span data-ttu-id="fdb49-114">에 지 구성 요소의 방화벽 구성에 대 한 자세한 내용은 [Lync Server 2013에 대 한 외부 A/V 방화벽 및 포트 요구 사항 확인](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="fdb49-114">For details about firewall configuration for edge components, see [Determine external A/V firewall and port requirements for Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md).</span></span>

<span data-ttu-id="fdb49-115">다음 표에는 각 내부 서버 역할에서 열어야 하는 포트가 나열되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fdb49-115">The following table lists the ports that need to be open on each internal server role.</span></span>

### <a name="required-server-ports-by-server-role"></a><span data-ttu-id="fdb49-116">필요한 서버 포트(서버 역할별)</span><span class="sxs-lookup"><span data-stu-id="fdb49-116">Required Server Ports (by Server Role)</span></span>

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
<th><span data-ttu-id="fdb49-117">서버 역할</span><span class="sxs-lookup"><span data-stu-id="fdb49-117">Server role</span></span></th>
<th><span data-ttu-id="fdb49-118">서비스 이름</span><span class="sxs-lookup"><span data-stu-id="fdb49-118">Service name</span></span></th>
<th><span data-ttu-id="fdb49-119">포트</span><span class="sxs-lookup"><span data-stu-id="fdb49-119">Port</span></span></th>
<th><span data-ttu-id="fdb49-120">Protocol(프로토콜)</span><span class="sxs-lookup"><span data-stu-id="fdb49-120">Protocol</span></span></th>
<th><span data-ttu-id="fdb49-121">참고</span><span class="sxs-lookup"><span data-stu-id="fdb49-121">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fdb49-122">모든 서버</span><span class="sxs-lookup"><span data-stu-id="fdb49-122">All Servers</span></span></p></td>
<td><p><span data-ttu-id="fdb49-123">SQL Browser</span><span class="sxs-lookup"><span data-stu-id="fdb49-123">SQL Browser</span></span></p></td>
<td><p><span data-ttu-id="fdb49-124">1434</span><span class="sxs-lookup"><span data-stu-id="fdb49-124">1434</span></span></p></td>
<td><p><span data-ttu-id="fdb49-125">P</span><span class="sxs-lookup"><span data-stu-id="fdb49-125">UDP</span></span></p></td>
<td><p><span data-ttu-id="fdb49-126">중앙 관리 저장소 데이터베이스의 복제 된 로컬 복사본에 대 한 SQL 브라우저입니다.</span><span class="sxs-lookup"><span data-stu-id="fdb49-126">SQL Browser for the local replicated copy of the Central Management Store database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fdb49-127">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="fdb49-127">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="fdb49-128">Lync Server Front-End 서비스</span><span class="sxs-lookup"><span data-stu-id="fdb49-128">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="fdb49-129">5060</span><span class="sxs-lookup"><span data-stu-id="fdb49-129">5060</span></span></p></td>
<td><p><span data-ttu-id="fdb49-130">TCP</span><span class="sxs-lookup"><span data-stu-id="fdb49-130">TCP</span></span></p></td>
<td><p><span data-ttu-id="fdb49-131">필요에 따라 Standard Edition Server 및 프런트 엔드 서버에서 원격 호출 제어 서버와 같은 트러스트된 서비스에 대한 고정 경로에 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="fdb49-131">Optionally used by Standard Edition servers and Front End Servers for static routes to trusted services, such as remote call control servers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fdb49-132">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="fdb49-132">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="fdb49-133">Lync Server Front-End 서비스</span><span class="sxs-lookup"><span data-stu-id="fdb49-133">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="fdb49-134">5061</span><span class="sxs-lookup"><span data-stu-id="fdb49-134">5061</span></span></p></td>
<td><p><span data-ttu-id="fdb49-135">TCP(TLS)</span><span class="sxs-lookup"><span data-stu-id="fdb49-135">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="fdb49-p102">Standard Edition Server 및 프런트 엔드 풀에서 서버 간 모든 내부 SIP 통신(MTLS), 서버와 클라이언트 간 SIP 통신(TLS) 및 프런트 엔드 서버와 중재 서버 간 SIP 통신(MTLS)에 사용됩니다. 또한 모니터링 서버와의 통신에도 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="fdb49-p102">Used by Standard Edition servers and Front End pools for all internal SIP communications between servers (MTLS), for SIP communications between Server and Client (TLS) and for SIP communications between Front End Servers and Mediation Servers (MTLS). Also used for communications with Monitoring Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fdb49-138">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="fdb49-138">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="fdb49-139">Lync Server Front-End 서비스</span><span class="sxs-lookup"><span data-stu-id="fdb49-139">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="fdb49-140">444</span><span class="sxs-lookup"><span data-stu-id="fdb49-140">444</span></span></p></td>
<td><p><span data-ttu-id="fdb49-141">H</span><span class="sxs-lookup"><span data-stu-id="fdb49-141">HTTPS</span></span></p>
<p><span data-ttu-id="fdb49-142">TCP</span><span class="sxs-lookup"><span data-stu-id="fdb49-142">TCP</span></span></p></td>
<td><p><span data-ttu-id="fdb49-143">포커스 (회의 상태를 관리 하는 Lync Server 구성 요소)와 개별 서버 간의 HTTPS 통신에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fdb49-143">Used for HTTPS communication between the Focus (the Lync Server component that manages conference state) and the individual servers.</span></span></p>
<p><span data-ttu-id="fdb49-144">이 포트는 Sba (survivable 분기 기기와 프런트 엔드 서버 간의 TCP 통신에도 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fdb49-144">This port is also used for TCP communication between Survivable Branch Appliances and Front End Servers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fdb49-145">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="fdb49-145">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="fdb49-146">Lync Server Front-End 서비스</span><span class="sxs-lookup"><span data-stu-id="fdb49-146">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="fdb49-147">135</span><span class="sxs-lookup"><span data-stu-id="fdb49-147">135</span></span></p></td>
<td><p><span data-ttu-id="fdb49-148">DCOM 및 RPC(원격 프로시저 호출)</span><span class="sxs-lookup"><span data-stu-id="fdb49-148">DCOM and remote procedure call (RPC)</span></span></p></td>
<td><p><span data-ttu-id="fdb49-149">사용자 이동, User Replicator 동기화 및 주소록 동기화와 같은 DCOM 기반 작업에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="fdb49-149">Used for DCOM based operations such as Moving Users, User Replicator Synchronization, and Address Book Synchronization.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fdb49-150">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="fdb49-150">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="fdb49-151">Lync Server IM 회의 서비스</span><span class="sxs-lookup"><span data-stu-id="fdb49-151">Lync Server IM Conferencing service</span></span></p></td>
<td><p><span data-ttu-id="fdb49-152">5062</span><span class="sxs-lookup"><span data-stu-id="fdb49-152">5062</span></span></p></td>
<td><p><span data-ttu-id="fdb49-153">TCP</span><span class="sxs-lookup"><span data-stu-id="fdb49-153">TCP</span></span></p></td>
<td><p><span data-ttu-id="fdb49-154">IM(인스턴트 메시징) 회의의 받는 SIP 요청에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="fdb49-154">Used for incoming SIP requests for instant messaging (IM) conferencing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fdb49-155">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="fdb49-155">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="fdb49-156">Lync Server 웹 회의 서비스</span><span class="sxs-lookup"><span data-stu-id="fdb49-156">Lync Server Web Conferencing service</span></span></p></td>
<td><p><span data-ttu-id="fdb49-157">8057</span><span class="sxs-lookup"><span data-stu-id="fdb49-157">8057</span></span></p></td>
<td><p><span data-ttu-id="fdb49-158">TCP(TLS)</span><span class="sxs-lookup"><span data-stu-id="fdb49-158">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="fdb49-159">클라이언트에서 PSOM(영구적 공유 개체 모델) 연결을 수신 대기하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="fdb49-159">Used to listen for Persistent Shared Object Model (PSOM) connections from client.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fdb49-160">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="fdb49-160">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="fdb49-161">Lync Server 웹 회의 호환성 서비스</span><span class="sxs-lookup"><span data-stu-id="fdb49-161">Lync Server Web Conferencing Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="fdb49-162">8058</span><span class="sxs-lookup"><span data-stu-id="fdb49-162">8058</span></span></p></td>
<td><p><span data-ttu-id="fdb49-163">TCP(TLS)</span><span class="sxs-lookup"><span data-stu-id="fdb49-163">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="fdb49-164">Live Meeting 클라이언트 및 이전 버전의 Lync Server에서 PSOM (영구 공유 개체 모델) 연결을 수신 대기 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fdb49-164">Used to listen for Persistent Shared Object Model (PSOM) connections from the Live Meeting client and previous versions of Lync Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fdb49-165">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="fdb49-165">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="fdb49-166">Lync Server 오디오/비디오 회의 서비스</span><span class="sxs-lookup"><span data-stu-id="fdb49-166">Lync Server Audio/Video Conferencing service</span></span></p></td>
<td><p><span data-ttu-id="fdb49-167">5063</span><span class="sxs-lookup"><span data-stu-id="fdb49-167">5063</span></span></p></td>
<td><p><span data-ttu-id="fdb49-168">TCP</span><span class="sxs-lookup"><span data-stu-id="fdb49-168">TCP</span></span></p></td>
<td><p><span data-ttu-id="fdb49-169">A/V(오디오/비디오) 회의의 받는 SIP 요청에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="fdb49-169">Used for incoming SIP requests for audio/video (A/V) conferencing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fdb49-170">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="fdb49-170">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="fdb49-171">Lync Server 오디오/비디오 회의 서비스</span><span class="sxs-lookup"><span data-stu-id="fdb49-171">Lync Server Audio/Video Conferencing service</span></span></p></td>
<td><p><span data-ttu-id="fdb49-172">57501-65535</span><span class="sxs-lookup"><span data-stu-id="fdb49-172">57501-65535</span></span></p></td>
<td><p><span data-ttu-id="fdb49-173">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="fdb49-173">TCP/UDP</span></span></p></td>
<td><p><span data-ttu-id="fdb49-174">비디오 회의에 사용되는 미디어 포트 범위입니다.</span><span class="sxs-lookup"><span data-stu-id="fdb49-174">Media port range used for video conferencing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fdb49-175">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="fdb49-175">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="fdb49-176">Lync Server 웹 호환성 서비스</span><span class="sxs-lookup"><span data-stu-id="fdb49-176">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="fdb49-177">80</span><span class="sxs-lookup"><span data-stu-id="fdb49-177">80</span></span></p></td>
<td><p><span data-ttu-id="fdb49-178">HTTP</span><span class="sxs-lookup"><span data-stu-id="fdb49-178">HTTP</span></span></p></td>
<td><p><span data-ttu-id="fdb49-179">HTTPS가 사용되지 않을 경우 프런트 엔드 서버에서 웹 팜 FQDN(IIS 웹 구성 요소에서 사용하는 URL)으로의 통신에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="fdb49-179">Used for communication from Front End Servers to the web farm FQDNs (the URLs used by IIS web components) when HTTPS is not used.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fdb49-180">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="fdb49-180">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="fdb49-181">Lync Server 웹 호환성 서비스</span><span class="sxs-lookup"><span data-stu-id="fdb49-181">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="fdb49-182">443</span><span class="sxs-lookup"><span data-stu-id="fdb49-182">443</span></span></p></td>
<td><p><span data-ttu-id="fdb49-183">H</span><span class="sxs-lookup"><span data-stu-id="fdb49-183">HTTPS</span></span></p></td>
<td><p><span data-ttu-id="fdb49-184">프런트 엔드 서버에서 웹 팜 FQDN(IIS 웹 구성 요소에서 사용하는 URL)으로의 통신에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="fdb49-184">Used for communication from Front End Servers to the web farm FQDNs (the URLs used by IIS web components).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fdb49-185">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="fdb49-185">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="fdb49-186">Lync Server 웹 호환성 서비스</span><span class="sxs-lookup"><span data-stu-id="fdb49-186">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="fdb49-187">8080</span><span class="sxs-lookup"><span data-stu-id="fdb49-187">8080</span></span></p></td>
<td><p><span data-ttu-id="fdb49-188">TCP 및 HTTP</span><span class="sxs-lookup"><span data-stu-id="fdb49-188">TCP and HTTP</span></span></p></td>
<td><p><span data-ttu-id="fdb49-189">외부 액세스용 웹 구성 요소에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fdb49-189">Used by web components for external access.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fdb49-190">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="fdb49-190">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="fdb49-191">웹 서버 구성 요소</span><span class="sxs-lookup"><span data-stu-id="fdb49-191">Web server component</span></span></p></td>
<td><p><span data-ttu-id="fdb49-192">4443</span><span class="sxs-lookup"><span data-stu-id="fdb49-192">4443</span></span></p></td>
<td><p><span data-ttu-id="fdb49-193">H</span><span class="sxs-lookup"><span data-stu-id="fdb49-193">HTTPS</span></span></p></td>
<td><p><span data-ttu-id="fdb49-194">자동 검색 로그인에 대 한 HTTPS (역방향 프록시) 및 HTTPS 프런트 엔드 풀 간 통신</span><span class="sxs-lookup"><span data-stu-id="fdb49-194">HTTPS (from Reverse Proxy) and HTTPS Front End inter-pool communications for Autodiscover sign-in.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fdb49-195">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="fdb49-195">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="fdb49-196">웹 서버 구성 요소</span><span class="sxs-lookup"><span data-stu-id="fdb49-196">Web server component</span></span></p></td>
<td><p><span data-ttu-id="fdb49-197">8060</span><span class="sxs-lookup"><span data-stu-id="fdb49-197">8060</span></span></p></td>
<td><p><span data-ttu-id="fdb49-198">TCP(MTLS)</span><span class="sxs-lookup"><span data-stu-id="fdb49-198">TCP (MTLS)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fdb49-199">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="fdb49-199">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="fdb49-200">웹 서버 구성 요소</span><span class="sxs-lookup"><span data-stu-id="fdb49-200">Web server component</span></span></p></td>
<td><p><span data-ttu-id="fdb49-201">8061</span><span class="sxs-lookup"><span data-stu-id="fdb49-201">8061</span></span></p></td>
<td><p><span data-ttu-id="fdb49-202">TCP(MTLS)</span><span class="sxs-lookup"><span data-stu-id="fdb49-202">TCP (MTLS)</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fdb49-203">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="fdb49-203">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="fdb49-204">Mobility Services 구성 요소</span><span class="sxs-lookup"><span data-stu-id="fdb49-204">Mobility Services component</span></span></p></td>
<td><p><span data-ttu-id="fdb49-205">5086</span><span class="sxs-lookup"><span data-stu-id="fdb49-205">5086</span></span></p></td>
<td><p><span data-ttu-id="fdb49-206">TCP(MTLS)</span><span class="sxs-lookup"><span data-stu-id="fdb49-206">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="fdb49-207">모바일 서비스 내부 프로세스에서 사용 하는 SIP 포트</span><span class="sxs-lookup"><span data-stu-id="fdb49-207">SIP port used by Mobility Services internal processes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fdb49-208">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="fdb49-208">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="fdb49-209">Mobility Services 구성 요소</span><span class="sxs-lookup"><span data-stu-id="fdb49-209">Mobility Services component</span></span></p></td>
<td><p><span data-ttu-id="fdb49-210">5087</span><span class="sxs-lookup"><span data-stu-id="fdb49-210">5087</span></span></p></td>
<td><p><span data-ttu-id="fdb49-211">TCP(MTLS)</span><span class="sxs-lookup"><span data-stu-id="fdb49-211">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="fdb49-212">모바일 서비스 내부 프로세스에서 사용 하는 SIP 포트</span><span class="sxs-lookup"><span data-stu-id="fdb49-212">SIP port used by Mobility Services internal processes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fdb49-213">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="fdb49-213">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="fdb49-214">Mobility Services 구성 요소</span><span class="sxs-lookup"><span data-stu-id="fdb49-214">Mobility Services component</span></span></p></td>
<td><p><span data-ttu-id="fdb49-215">443</span><span class="sxs-lookup"><span data-stu-id="fdb49-215">443</span></span></p></td>
<td><p><span data-ttu-id="fdb49-216">H</span><span class="sxs-lookup"><span data-stu-id="fdb49-216">HTTPS</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fdb49-217">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="fdb49-217">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="fdb49-218">Lync Server 회의 수행자 서비스 (전화 접속 회의)</span><span class="sxs-lookup"><span data-stu-id="fdb49-218">Lync Server Conferencing Attendant service (dial-in conferencing)</span></span></p></td>
<td><p><span data-ttu-id="fdb49-219">5064</span><span class="sxs-lookup"><span data-stu-id="fdb49-219">5064</span></span></p></td>
<td><p><span data-ttu-id="fdb49-220">TCP</span><span class="sxs-lookup"><span data-stu-id="fdb49-220">TCP</span></span></p></td>
<td><p><span data-ttu-id="fdb49-221">전화 접속 회의의 받는 SIP 요청에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="fdb49-221">Used for incoming SIP requests for dial-in conferencing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fdb49-222">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="fdb49-222">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="fdb49-223">Lync Server 회의 수행자 서비스 (전화 접속 회의)</span><span class="sxs-lookup"><span data-stu-id="fdb49-223">Lync Server Conferencing Attendant service (dial-in conferencing)</span></span></p></td>
<td><p><span data-ttu-id="fdb49-224">5072</span><span class="sxs-lookup"><span data-stu-id="fdb49-224">5072</span></span></p></td>
<td><p><span data-ttu-id="fdb49-225">TCP</span><span class="sxs-lookup"><span data-stu-id="fdb49-225">TCP</span></span></p></td>
<td><p><span data-ttu-id="fdb49-226">받는 전화 회의에 대 한 들어오는 SIP 요청에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fdb49-226">Used for incoming SIP requests for Attendant (dial in conferencing).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fdb49-227">배치된 중재 서버를 실행하는 프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="fdb49-227">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="fdb49-228">Lync Server 중재 서비스</span><span class="sxs-lookup"><span data-stu-id="fdb49-228">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="fdb49-229">5070</span><span class="sxs-lookup"><span data-stu-id="fdb49-229">5070</span></span></p></td>
<td><p><span data-ttu-id="fdb49-230">TCP</span><span class="sxs-lookup"><span data-stu-id="fdb49-230">TCP</span></span></p></td>
<td><p><span data-ttu-id="fdb49-231">중재 서버에서 프런트 엔드 서버에서 중재 서버로의 받는 요청에 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="fdb49-231">Used by the Mediation Server for incoming requests from the Front End Server to the Mediation Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fdb49-232">배치된 중재 서버를 실행하는 프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="fdb49-232">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="fdb49-233">Lync Server 중재 서비스</span><span class="sxs-lookup"><span data-stu-id="fdb49-233">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="fdb49-234">5067</span><span class="sxs-lookup"><span data-stu-id="fdb49-234">5067</span></span></p></td>
<td><p><span data-ttu-id="fdb49-235">TCP(TLS)</span><span class="sxs-lookup"><span data-stu-id="fdb49-235">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="fdb49-236">PSTN 게이트웨이에서 중재 서버로의 받는 SIP 요청에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="fdb49-236">Used for incoming SIP requests from the PSTN gateway to the Mediation Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fdb49-237">배치된 중재 서버를 실행하는 프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="fdb49-237">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="fdb49-238">Lync Server 중재 서비스</span><span class="sxs-lookup"><span data-stu-id="fdb49-238">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="fdb49-239">5068</span><span class="sxs-lookup"><span data-stu-id="fdb49-239">5068</span></span></p></td>
<td><p><span data-ttu-id="fdb49-240">TCP</span><span class="sxs-lookup"><span data-stu-id="fdb49-240">TCP</span></span></p></td>
<td><p><span data-ttu-id="fdb49-241">PSTN 게이트웨이에서 중재 서버로의 받는 SIP 요청에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="fdb49-241">Used for incoming SIP requests from the PSTN gateway to the Mediation Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fdb49-242">배치된 중재 서버를 실행하는 프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="fdb49-242">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="fdb49-243">Lync Server 중재 서비스</span><span class="sxs-lookup"><span data-stu-id="fdb49-243">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="fdb49-244">5081</span><span class="sxs-lookup"><span data-stu-id="fdb49-244">5081</span></span></p></td>
<td><p><span data-ttu-id="fdb49-245">TCP</span><span class="sxs-lookup"><span data-stu-id="fdb49-245">TCP</span></span></p></td>
<td><p><span data-ttu-id="fdb49-246">중재 서버에서 PSTN 게이트웨이로의 보내는 SIP 요청에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="fdb49-246">Used for outgoing SIP requests from the Mediation Server to the PSTN gateway.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fdb49-247">배치된 중재 서버를 실행하는 프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="fdb49-247">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="fdb49-248">Lync Server 중재 서비스</span><span class="sxs-lookup"><span data-stu-id="fdb49-248">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="fdb49-249">5082</span><span class="sxs-lookup"><span data-stu-id="fdb49-249">5082</span></span></p></td>
<td><p><span data-ttu-id="fdb49-250">TCP(TLS)</span><span class="sxs-lookup"><span data-stu-id="fdb49-250">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="fdb49-251">중재 서버에서 PSTN 게이트웨이로의 보내는 SIP 요청에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="fdb49-251">Used for outgoing SIP requests from the Mediation Server to the PSTN gateway.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fdb49-252">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="fdb49-252">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="fdb49-253">Lync Server 응용 프로그램 공유 서비스</span><span class="sxs-lookup"><span data-stu-id="fdb49-253">Lync Server Application Sharing service</span></span></p></td>
<td><p><span data-ttu-id="fdb49-254">5065</span><span class="sxs-lookup"><span data-stu-id="fdb49-254">5065</span></span></p></td>
<td><p><span data-ttu-id="fdb49-255">TCP</span><span class="sxs-lookup"><span data-stu-id="fdb49-255">TCP</span></span></p></td>
<td><p><span data-ttu-id="fdb49-256">응용 프로그램 공유의 받는 SIP 수신 대기 요청에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="fdb49-256">Used for incoming SIP listening requests for application sharing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fdb49-257">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="fdb49-257">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="fdb49-258">Lync Server 응용 프로그램 공유 서비스</span><span class="sxs-lookup"><span data-stu-id="fdb49-258">Lync Server Application Sharing service</span></span></p></td>
<td><p><span data-ttu-id="fdb49-259">49152-65535</span><span class="sxs-lookup"><span data-stu-id="fdb49-259">49152-65535</span></span></p></td>
<td><p><span data-ttu-id="fdb49-260">TCP</span><span class="sxs-lookup"><span data-stu-id="fdb49-260">TCP</span></span></p></td>
<td><p><span data-ttu-id="fdb49-261">응용 프로그램 공유에 사용되는 미디어 포트 범위입니다.</span><span class="sxs-lookup"><span data-stu-id="fdb49-261">Media port range used for application sharing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fdb49-262">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="fdb49-262">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="fdb49-263">Lync Server 회의 알림 서비스</span><span class="sxs-lookup"><span data-stu-id="fdb49-263">Lync Server Conferencing Announcement service</span></span></p></td>
<td><p><span data-ttu-id="fdb49-264">5073</span><span class="sxs-lookup"><span data-stu-id="fdb49-264">5073</span></span></p></td>
<td><p><span data-ttu-id="fdb49-265">TCP</span><span class="sxs-lookup"><span data-stu-id="fdb49-265">TCP</span></span></p></td>
<td><p><span data-ttu-id="fdb49-266">Lync Server 회의 알림 서비스에 대 한 들어오는 SIP 요청에 사용 됩니다 (전화 접속 회의의 경우).</span><span class="sxs-lookup"><span data-stu-id="fdb49-266">Used for incoming SIP requests for the Lync Server Conferencing Announcement service (that is, for dial-in conferencing).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fdb49-267">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="fdb49-267">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="fdb49-268">Lync Server 통화 대기 서비스</span><span class="sxs-lookup"><span data-stu-id="fdb49-268">Lync Server Call Park service</span></span></p></td>
<td><p><span data-ttu-id="fdb49-269">5075</span><span class="sxs-lookup"><span data-stu-id="fdb49-269">5075</span></span></p></td>
<td><p><span data-ttu-id="fdb49-270">TCP</span><span class="sxs-lookup"><span data-stu-id="fdb49-270">TCP</span></span></p></td>
<td><p><span data-ttu-id="fdb49-271">통화 대기 응용 프로그램의 받는 SIP 요청에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="fdb49-271">Used for incoming SIP requests for the Call Park application.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fdb49-272">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="fdb49-272">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="fdb49-273">Lync Server Audio 테스트 서비스</span><span class="sxs-lookup"><span data-stu-id="fdb49-273">Lync Server Audio Test service</span></span></p></td>
<td><p><span data-ttu-id="fdb49-274">5076</span><span class="sxs-lookup"><span data-stu-id="fdb49-274">5076</span></span></p></td>
<td><p><span data-ttu-id="fdb49-275">TCP</span><span class="sxs-lookup"><span data-stu-id="fdb49-275">TCP</span></span></p></td>
<td><p><span data-ttu-id="fdb49-276">오디오 테스트 서비스의 받는 SIP 요청에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="fdb49-276">Used for incoming SIP requests for the Audio Test service.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fdb49-277">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="fdb49-277">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="fdb49-278">해당 없음</span><span class="sxs-lookup"><span data-stu-id="fdb49-278">Not applicable</span></span></p></td>
<td><p><span data-ttu-id="fdb49-279">5066</span><span class="sxs-lookup"><span data-stu-id="fdb49-279">5066</span></span></p></td>
<td><p><span data-ttu-id="fdb49-280">TCP</span><span class="sxs-lookup"><span data-stu-id="fdb49-280">TCP</span></span></p></td>
<td><p><span data-ttu-id="fdb49-281">아웃바운드 E9-1-1(Enhanced 9-1-1) 게이트웨이에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="fdb49-281">Used for outbound Enhanced 9-1-1 (E9-1-1) gateway.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fdb49-282">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="fdb49-282">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="fdb49-283">Lync Server 응답 그룹 서비스</span><span class="sxs-lookup"><span data-stu-id="fdb49-283">Lync Server Response Group service</span></span></p></td>
<td><p><span data-ttu-id="fdb49-284">5071</span><span class="sxs-lookup"><span data-stu-id="fdb49-284">5071</span></span></p></td>
<td><p><span data-ttu-id="fdb49-285">TCP</span><span class="sxs-lookup"><span data-stu-id="fdb49-285">TCP</span></span></p></td>
<td><p><span data-ttu-id="fdb49-286">응답 그룹 응용 프로그램의 받는 SIP 요청에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="fdb49-286">Used for incoming SIP requests for the Response Group application.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fdb49-287">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="fdb49-287">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="fdb49-288">Lync Server 응답 그룹 서비스</span><span class="sxs-lookup"><span data-stu-id="fdb49-288">Lync Server Response Group service</span></span></p></td>
<td><p><span data-ttu-id="fdb49-289">8404</span><span class="sxs-lookup"><span data-stu-id="fdb49-289">8404</span></span></p></td>
<td><p><span data-ttu-id="fdb49-290">TCP(MTLS)</span><span class="sxs-lookup"><span data-stu-id="fdb49-290">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="fdb49-291">응답 그룹 응용 프로그램의 받는 SIP 요청에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="fdb49-291">Used for incoming SIP requests for the Response Group application.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fdb49-292">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="fdb49-292">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="fdb49-293">Lync Server 대역폭 정책 서비스</span><span class="sxs-lookup"><span data-stu-id="fdb49-293">Lync Server Bandwidth Policy Service</span></span></p></td>
<td><p><span data-ttu-id="fdb49-294">5080</span><span class="sxs-lookup"><span data-stu-id="fdb49-294">5080</span></span></p></td>
<td><p><span data-ttu-id="fdb49-295">TCP</span><span class="sxs-lookup"><span data-stu-id="fdb49-295">TCP</span></span></p></td>
<td><p><span data-ttu-id="fdb49-296">A/V 에지 TURN 트래픽에 대한 대역폭 정책 서비스의 통화 허용 제어에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="fdb49-296">Used for call admission control by the Bandwidth Policy service for A/V Edge TURN traffic.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fdb49-297">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="fdb49-297">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="fdb49-298">Lync Server 대역폭 정책 서비스</span><span class="sxs-lookup"><span data-stu-id="fdb49-298">Lync Server Bandwidth Policy Service</span></span></p></td>
<td><p><span data-ttu-id="fdb49-299">448</span><span class="sxs-lookup"><span data-stu-id="fdb49-299">448</span></span></p></td>
<td><p><span data-ttu-id="fdb49-300">TCP</span><span class="sxs-lookup"><span data-stu-id="fdb49-300">TCP</span></span></p></td>
<td><p><span data-ttu-id="fdb49-301">Lync Server 대역폭 정책 서비스의 통화 허용 제어에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fdb49-301">Used for call admission control by the Lync Server Bandwidth Policy Service.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fdb49-302">중앙 관리 저장소가 상주 하는 프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="fdb49-302">Front End Servers where the Central Management store resides</span></span></p></td>
<td><p><span data-ttu-id="fdb49-303">Lync Server Master Replicator 에이전트 서비스</span><span class="sxs-lookup"><span data-stu-id="fdb49-303">Lync Server Master Replicator Agent service</span></span></p></td>
<td><p><span data-ttu-id="fdb49-304">445</span><span class="sxs-lookup"><span data-stu-id="fdb49-304">445</span></span></p></td>
<td><p><span data-ttu-id="fdb49-305">TCP</span><span class="sxs-lookup"><span data-stu-id="fdb49-305">TCP</span></span></p></td>
<td><p><span data-ttu-id="fdb49-306">중앙 관리 저장소의 구성 데이터를 Lync Server를 실행 하는 서버로 밀어 넣는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fdb49-306">Used to push configuration data from the Central Management store to servers running Lync Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fdb49-307">모든 서버</span><span class="sxs-lookup"><span data-stu-id="fdb49-307">All Servers</span></span></p></td>
<td><p><span data-ttu-id="fdb49-308">SQL Browser</span><span class="sxs-lookup"><span data-stu-id="fdb49-308">SQL Browser</span></span></p></td>
<td><p><span data-ttu-id="fdb49-309">1434</span><span class="sxs-lookup"><span data-stu-id="fdb49-309">1434</span></span></p></td>
<td><p><span data-ttu-id="fdb49-310">P</span><span class="sxs-lookup"><span data-stu-id="fdb49-310">UDP</span></span></p></td>
<td><p><span data-ttu-id="fdb49-311">로컬 SQL Server 인스턴스에 중앙 관리 저장소 데이터의 로컬 복제 복사본에 대 한 SQL 브라우저</span><span class="sxs-lookup"><span data-stu-id="fdb49-311">SQL Browser for local replicated copy of Central Management store data in local SQL Server instance</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fdb49-312">모든 내부 서버</span><span class="sxs-lookup"><span data-stu-id="fdb49-312">All internal servers</span></span></p></td>
<td><p><span data-ttu-id="fdb49-313">다양 한</span><span class="sxs-lookup"><span data-stu-id="fdb49-313">Various</span></span></p></td>
<td><p><span data-ttu-id="fdb49-314">49152-57500</span><span class="sxs-lookup"><span data-stu-id="fdb49-314">49152-57500</span></span></p></td>
<td><p><span data-ttu-id="fdb49-315">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="fdb49-315">TCP/UDP</span></span></p></td>
<td><p><span data-ttu-id="fdb49-316">모든 내부 서버의 오디오 회의에 사용되는 미디어 포트 범위입니다.</span><span class="sxs-lookup"><span data-stu-id="fdb49-316">Media port range used for audio conferencing on all internal servers.</span></span> <span data-ttu-id="fdb49-317">오디오를 종료 하는 모든 서버에서 사용: 프런트 엔드 서버 (Lync Server 회의 수행자 서비스, Lync Server 회의 알림 서비스 및 Lync Server 오디오/비디오 회의 서비스) 및 중재 서버</span><span class="sxs-lookup"><span data-stu-id="fdb49-317">Used by all servers that terminate audio: Front End Servers (for Lync Server Conferencing Attendant service, Lync Server Conferencing Announcement service, and Lync Server Audio/Video Conferencing service), and Mediation Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fdb49-318">Office Web Apps 서버</span><span class="sxs-lookup"><span data-stu-id="fdb49-318">Office Web Apps Servers</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fdb49-319">443</span><span class="sxs-lookup"><span data-stu-id="fdb49-319">443</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fdb49-320">Lync Server 2013에서 Office Web Apps 서버에 연결 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fdb49-320">Used by Lync Server 2013 to connect to Office Web Apps Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fdb49-321">디렉터</span><span class="sxs-lookup"><span data-stu-id="fdb49-321">Directors</span></span></p></td>
<td><p><span data-ttu-id="fdb49-322">Lync Server Front-End 서비스</span><span class="sxs-lookup"><span data-stu-id="fdb49-322">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="fdb49-323">5060</span><span class="sxs-lookup"><span data-stu-id="fdb49-323">5060</span></span></p></td>
<td><p><span data-ttu-id="fdb49-324">TCP</span><span class="sxs-lookup"><span data-stu-id="fdb49-324">TCP</span></span></p></td>
<td><p><span data-ttu-id="fdb49-325">필요에 따라 원격 통화 제어 서버와 같은 트러스트된 서비스에 대한 고정 경로에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="fdb49-325">Optionally used for static routes to trusted services, such as remote call control servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fdb49-326">디렉터</span><span class="sxs-lookup"><span data-stu-id="fdb49-326">Directors</span></span></p></td>
<td><p><span data-ttu-id="fdb49-327">Lync Server Front-End 서비스</span><span class="sxs-lookup"><span data-stu-id="fdb49-327">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="fdb49-328">444</span><span class="sxs-lookup"><span data-stu-id="fdb49-328">444</span></span></p></td>
<td><p><span data-ttu-id="fdb49-329">H</span><span class="sxs-lookup"><span data-stu-id="fdb49-329">HTTPS</span></span></p>
<p><span data-ttu-id="fdb49-330">TCP</span><span class="sxs-lookup"><span data-stu-id="fdb49-330">TCP</span></span></p></td>
<td><p><span data-ttu-id="fdb49-331">프런트 엔드 및 디렉터 간의 서버 간 통신.</span><span class="sxs-lookup"><span data-stu-id="fdb49-331">Inter-server communication between Front End and Director.</span></span> <span data-ttu-id="fdb49-332">또한 클라이언트 인증서가 프런트 엔드 서버로 게시 되거나 클라이언트 인증서가 이미 게시 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="fdb49-332">Additionally, client certificate publish (to Front End Servers) or validate if the client certificate has already been published.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fdb49-333">디렉터</span><span class="sxs-lookup"><span data-stu-id="fdb49-333">Directors</span></span></p></td>
<td><p><span data-ttu-id="fdb49-334">Lync Server 웹 호환성 서비스</span><span class="sxs-lookup"><span data-stu-id="fdb49-334">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="fdb49-335">80</span><span class="sxs-lookup"><span data-stu-id="fdb49-335">80</span></span></p></td>
<td><p><span data-ttu-id="fdb49-336">TCP</span><span class="sxs-lookup"><span data-stu-id="fdb49-336">TCP</span></span></p></td>
<td><p><span data-ttu-id="fdb49-p105">디렉터에서 웹 팜 FQDN(IIS 웹 구성 요소에서 사용하는 URL)으로의 초기 통신에 사용됩니다. 정상 작동의 경우 포트 443 및 TCP 프로토콜 유형을 사용하여 HTTPS 트래픽으로 전환됩니다.</span><span class="sxs-lookup"><span data-stu-id="fdb49-p105">Used for initial communication from Directors to the web farm FQDNs (the URLs used by IIS web components). In normal operation, will switch to HTTPS traffic, using port 443 and protocol type TCP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fdb49-339">디렉터</span><span class="sxs-lookup"><span data-stu-id="fdb49-339">Directors</span></span></p></td>
<td><p><span data-ttu-id="fdb49-340">Lync Server 웹 호환성 서비스</span><span class="sxs-lookup"><span data-stu-id="fdb49-340">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="fdb49-341">443</span><span class="sxs-lookup"><span data-stu-id="fdb49-341">443</span></span></p></td>
<td><p><span data-ttu-id="fdb49-342">H</span><span class="sxs-lookup"><span data-stu-id="fdb49-342">HTTPS</span></span></p></td>
<td><p><span data-ttu-id="fdb49-343">디렉터에서 웹 팜 FQDN(IIS 웹 구성 요소에서 사용하는 URL)으로의 통신에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="fdb49-343">Used for communication from Directors to the web farm FQDNs (the URLs used by IIS web components).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fdb49-344">디렉터</span><span class="sxs-lookup"><span data-stu-id="fdb49-344">Directors</span></span></p></td>
<td><p><span data-ttu-id="fdb49-345">Lync Server Front-End 서비스</span><span class="sxs-lookup"><span data-stu-id="fdb49-345">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="fdb49-346">5061</span><span class="sxs-lookup"><span data-stu-id="fdb49-346">5061</span></span></p></td>
<td><p><span data-ttu-id="fdb49-347">TCP</span><span class="sxs-lookup"><span data-stu-id="fdb49-347">TCP</span></span></p></td>
<td><p><span data-ttu-id="fdb49-348">서버 간 내부 통신과 클라이언트 연결에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="fdb49-348">Used for internal communications between servers and for client connections.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fdb49-349">중재 서버</span><span class="sxs-lookup"><span data-stu-id="fdb49-349">Mediation Servers</span></span></p></td>
<td><p><span data-ttu-id="fdb49-350">Lync Server 중재 서비스</span><span class="sxs-lookup"><span data-stu-id="fdb49-350">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="fdb49-351">5070</span><span class="sxs-lookup"><span data-stu-id="fdb49-351">5070</span></span></p></td>
<td><p><span data-ttu-id="fdb49-352">TCP</span><span class="sxs-lookup"><span data-stu-id="fdb49-352">TCP</span></span></p></td>
<td><p><span data-ttu-id="fdb49-353">중재 서버가 프런트 엔드 서버에서 받는 요청에 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="fdb49-353">Used by the Mediation Server for incoming requests from the Front End Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fdb49-354">중재 서버</span><span class="sxs-lookup"><span data-stu-id="fdb49-354">Mediation Servers</span></span></p></td>
<td><p><span data-ttu-id="fdb49-355">Lync Server 중재 서비스</span><span class="sxs-lookup"><span data-stu-id="fdb49-355">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="fdb49-356">5067</span><span class="sxs-lookup"><span data-stu-id="fdb49-356">5067</span></span></p></td>
<td><p><span data-ttu-id="fdb49-357">TCP(TLS)</span><span class="sxs-lookup"><span data-stu-id="fdb49-357">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="fdb49-358">PSTN 게이트웨이에서 받는 SIP 요청에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="fdb49-358">Used for incoming SIP requests from the PSTN gateway.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fdb49-359">중재 서버</span><span class="sxs-lookup"><span data-stu-id="fdb49-359">Mediation Servers</span></span></p></td>
<td><p><span data-ttu-id="fdb49-360">Lync Server 중재 서비스</span><span class="sxs-lookup"><span data-stu-id="fdb49-360">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="fdb49-361">5068</span><span class="sxs-lookup"><span data-stu-id="fdb49-361">5068</span></span></p></td>
<td><p><span data-ttu-id="fdb49-362">TCP</span><span class="sxs-lookup"><span data-stu-id="fdb49-362">TCP</span></span></p></td>
<td><p><span data-ttu-id="fdb49-363">PSTN 게이트웨이에서 받는 SIP 요청에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="fdb49-363">Used for incoming SIP requests from the PSTN gateway.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fdb49-364">중재 서버</span><span class="sxs-lookup"><span data-stu-id="fdb49-364">Mediation Servers</span></span></p></td>
<td><p><span data-ttu-id="fdb49-365">Lync Server 중재 서비스</span><span class="sxs-lookup"><span data-stu-id="fdb49-365">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="fdb49-366">5070</span><span class="sxs-lookup"><span data-stu-id="fdb49-366">5070</span></span></p></td>
<td><p><span data-ttu-id="fdb49-367">TCP(MTLS)</span><span class="sxs-lookup"><span data-stu-id="fdb49-367">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="fdb49-368">프런트 엔드 서버의 SIP 요청에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="fdb49-368">Used for SIP requests from the Front End Servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fdb49-369">영구 채팅 프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="fdb49-369">Persistent Chat Front End Server</span></span></p></td>
<td><p><span data-ttu-id="fdb49-370">영구 채팅 SIP</span><span class="sxs-lookup"><span data-stu-id="fdb49-370">Persistent Chat SIP</span></span></p></td>
<td><p><span data-ttu-id="fdb49-371">5041</span><span class="sxs-lookup"><span data-stu-id="fdb49-371">5041</span></span></p></td>
<td><p><span data-ttu-id="fdb49-372">TCP(MTLS)</span><span class="sxs-lookup"><span data-stu-id="fdb49-372">TCP (MTLS)</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fdb49-373">영구 채팅 프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="fdb49-373">Persistent Chat Front End Server</span></span></p></td>
<td><p><span data-ttu-id="fdb49-374">영구 채팅 WCF (Windows Communication Foundation)</span><span class="sxs-lookup"><span data-stu-id="fdb49-374">Persistent Chat Windows Communication Foundation (WCF)</span></span></p></td>
<td><p><span data-ttu-id="fdb49-375">881</span><span class="sxs-lookup"><span data-stu-id="fdb49-375">881</span></span></p></td>
<td><p><span data-ttu-id="fdb49-376">TCP (TLS) 및 TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="fdb49-376">TCP (TLS) and TCP (MTLS)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fdb49-377">영구 채팅 프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="fdb49-377">Persistent Chat Front End Server</span></span></p></td>
<td><p><span data-ttu-id="fdb49-378">영구 채팅 파일 전송 서비스</span><span class="sxs-lookup"><span data-stu-id="fdb49-378">Persistent Chat File Transfer Service</span></span></p></td>
<td><p><span data-ttu-id="fdb49-379">443</span><span class="sxs-lookup"><span data-stu-id="fdb49-379">443</span></span></p></td>
<td><p><span data-ttu-id="fdb49-380">TCP(TLS)</span><span class="sxs-lookup"><span data-stu-id="fdb49-380">TCP (TLS)</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="fdb49-381">일부 원격 통화 제어 시나리오의 경우 프런트 엔드 서버 또는 디렉터 및 PBX 간 TCP 연결이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="fdb49-381">Some remote call control scenarios require a TCP connection between the Front End Server or Director and the PBX.</span></span> <span data-ttu-id="fdb49-382">Lync Server에서는 더 이상 TCP 포트 5060을 사용 하지 않지만 원격 통화 제어 배포 중에는 RCC Line Server FQDN을 프런트 엔드 서버 또는 디렉터가 PBX 시스템에 연결 하는 데 사용할 TCP 포트와 연결 하는 신뢰할 수 있는 서버 구성을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="fdb49-382">Although Lync Server no longer uses TCP port 5060, during remote call control deployment you create a trusted server configuration, which associates the RCC Line Server FQDN with the TCP port that the Front End Server or Director will use to connect to the PBX system.</span></span> <span data-ttu-id="fdb49-383">자세한 내용은 Lync Server 관리 셸 설명서에서 <STRONG>CsTrustedApplicationComputer</STRONG> cmdlet을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="fdb49-383">For details, see the <STRONG>CsTrustedApplicationComputer</STRONG> cmdlet in the Lync Server Management Shell documentation.</span></span>



</div>

<span data-ttu-id="fdb49-384">다음 표에서는 하드웨어 부하 분산만 사용하는 풀(DNS 부하 분산 사용 안 함)의 경우 하드웨어 부하 분산 장치를 열어야 하는 포트를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="fdb49-384">For your pools that use only hardware load balancing (not DNS load balancing), the following table shows the ports that need to open the hardware load balancers.</span></span>

### <a name="hardware-load-balancer-ports-if-using-only-hardware-load-balancing"></a><span data-ttu-id="fdb49-385">하드웨어 부하 분산만 사용하는 경우 하드웨어 부하 분산 장치 포트</span><span class="sxs-lookup"><span data-stu-id="fdb49-385">Hardware Load Balancer Ports if Using Only Hardware Load Balancing</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fdb49-386">부하 분산 장치</span><span class="sxs-lookup"><span data-stu-id="fdb49-386">Load Balancer</span></span></th>
<th><span data-ttu-id="fdb49-387">포트</span><span class="sxs-lookup"><span data-stu-id="fdb49-387">Port</span></span></th>
<th><span data-ttu-id="fdb49-388">Protocol(프로토콜)</span><span class="sxs-lookup"><span data-stu-id="fdb49-388">Protocol</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fdb49-389">프런트 엔드 서버 부하 분산 장치</span><span class="sxs-lookup"><span data-stu-id="fdb49-389">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="fdb49-390">5061</span><span class="sxs-lookup"><span data-stu-id="fdb49-390">5061</span></span></p></td>
<td><p><span data-ttu-id="fdb49-391">TCP(TLS)</span><span class="sxs-lookup"><span data-stu-id="fdb49-391">TCP (TLS)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fdb49-392">프런트 엔드 서버 부하 분산 장치</span><span class="sxs-lookup"><span data-stu-id="fdb49-392">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="fdb49-393">444</span><span class="sxs-lookup"><span data-stu-id="fdb49-393">444</span></span></p></td>
<td><p><span data-ttu-id="fdb49-394">H</span><span class="sxs-lookup"><span data-stu-id="fdb49-394">HTTPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fdb49-395">프런트 엔드 서버 부하 분산 장치</span><span class="sxs-lookup"><span data-stu-id="fdb49-395">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="fdb49-396">135</span><span class="sxs-lookup"><span data-stu-id="fdb49-396">135</span></span></p></td>
<td><p><span data-ttu-id="fdb49-397">DCOM 및 RPC(원격 프로시저 호출)</span><span class="sxs-lookup"><span data-stu-id="fdb49-397">DCOM and remote procedure call (RPC)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fdb49-398">프런트 엔드 서버 부하 분산 장치</span><span class="sxs-lookup"><span data-stu-id="fdb49-398">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="fdb49-399">80</span><span class="sxs-lookup"><span data-stu-id="fdb49-399">80</span></span></p></td>
<td><p><span data-ttu-id="fdb49-400">HTTP</span><span class="sxs-lookup"><span data-stu-id="fdb49-400">HTTP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fdb49-401">프런트 엔드 서버 부하 분산 장치</span><span class="sxs-lookup"><span data-stu-id="fdb49-401">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="fdb49-402">8080</span><span class="sxs-lookup"><span data-stu-id="fdb49-402">8080</span></span></p></td>
<td><p><span data-ttu-id="fdb49-403">TCP - 프런트 엔드 서버에서 루트 인증서의 클라이언트 및 장치 검색 - 클라이언트 및 장치는 NTLM으로 인증됩니다.</span><span class="sxs-lookup"><span data-stu-id="fdb49-403">TCP - Client and device retrieval of root certificate from Front End Server – clients and devices authenticated by NTLM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fdb49-404">프런트 엔드 서버 부하 분산 장치</span><span class="sxs-lookup"><span data-stu-id="fdb49-404">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="fdb49-405">443</span><span class="sxs-lookup"><span data-stu-id="fdb49-405">443</span></span></p></td>
<td><p><span data-ttu-id="fdb49-406">H</span><span class="sxs-lookup"><span data-stu-id="fdb49-406">HTTPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fdb49-407">프런트 엔드 서버 부하 분산 장치</span><span class="sxs-lookup"><span data-stu-id="fdb49-407">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="fdb49-408">4443</span><span class="sxs-lookup"><span data-stu-id="fdb49-408">4443</span></span></p></td>
<td><p><span data-ttu-id="fdb49-409">HTTPS(역방향 프록시)</span><span class="sxs-lookup"><span data-stu-id="fdb49-409">HTTPS (from reverse proxy)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fdb49-410">프런트 엔드 서버 부하 분산 장치</span><span class="sxs-lookup"><span data-stu-id="fdb49-410">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="fdb49-411">5072</span><span class="sxs-lookup"><span data-stu-id="fdb49-411">5072</span></span></p></td>
<td><p><span data-ttu-id="fdb49-412">TCP</span><span class="sxs-lookup"><span data-stu-id="fdb49-412">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fdb49-413">프런트 엔드 서버 부하 분산 장치</span><span class="sxs-lookup"><span data-stu-id="fdb49-413">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="fdb49-414">5073</span><span class="sxs-lookup"><span data-stu-id="fdb49-414">5073</span></span></p></td>
<td><p><span data-ttu-id="fdb49-415">TCP</span><span class="sxs-lookup"><span data-stu-id="fdb49-415">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fdb49-416">프런트 엔드 서버 부하 분산 장치</span><span class="sxs-lookup"><span data-stu-id="fdb49-416">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="fdb49-417">5075</span><span class="sxs-lookup"><span data-stu-id="fdb49-417">5075</span></span></p></td>
<td><p><span data-ttu-id="fdb49-418">TCP</span><span class="sxs-lookup"><span data-stu-id="fdb49-418">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fdb49-419">프런트 엔드 서버 부하 분산 장치</span><span class="sxs-lookup"><span data-stu-id="fdb49-419">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="fdb49-420">5076</span><span class="sxs-lookup"><span data-stu-id="fdb49-420">5076</span></span></p></td>
<td><p><span data-ttu-id="fdb49-421">TCP</span><span class="sxs-lookup"><span data-stu-id="fdb49-421">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fdb49-422">프런트 엔드 서버 부하 분산 장치</span><span class="sxs-lookup"><span data-stu-id="fdb49-422">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="fdb49-423">5071</span><span class="sxs-lookup"><span data-stu-id="fdb49-423">5071</span></span></p></td>
<td><p><span data-ttu-id="fdb49-424">TCP</span><span class="sxs-lookup"><span data-stu-id="fdb49-424">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fdb49-425">프런트 엔드 서버 부하 분산 장치</span><span class="sxs-lookup"><span data-stu-id="fdb49-425">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="fdb49-426">5080</span><span class="sxs-lookup"><span data-stu-id="fdb49-426">5080</span></span></p></td>
<td><p><span data-ttu-id="fdb49-427">TCP</span><span class="sxs-lookup"><span data-stu-id="fdb49-427">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fdb49-428">프런트 엔드 서버 부하 분산 장치</span><span class="sxs-lookup"><span data-stu-id="fdb49-428">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="fdb49-429">448</span><span class="sxs-lookup"><span data-stu-id="fdb49-429">448</span></span></p></td>
<td><p><span data-ttu-id="fdb49-430">TCP</span><span class="sxs-lookup"><span data-stu-id="fdb49-430">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fdb49-431">중재 서버 부하 분산 장치</span><span class="sxs-lookup"><span data-stu-id="fdb49-431">Mediation Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="fdb49-432">5070</span><span class="sxs-lookup"><span data-stu-id="fdb49-432">5070</span></span></p></td>
<td><p><span data-ttu-id="fdb49-433">TCP</span><span class="sxs-lookup"><span data-stu-id="fdb49-433">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fdb49-434">프런트 엔드 서버 부하 분산 장치 (풀에서 중재 서버도 실행 되는 경우)</span><span class="sxs-lookup"><span data-stu-id="fdb49-434">Front End Server load balancer (if the pool also runs Mediation Server)</span></span></p></td>
<td><p><span data-ttu-id="fdb49-435">5070</span><span class="sxs-lookup"><span data-stu-id="fdb49-435">5070</span></span></p></td>
<td><p><span data-ttu-id="fdb49-436">TCP</span><span class="sxs-lookup"><span data-stu-id="fdb49-436">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fdb49-437">디렉터 부하 분산 장치</span><span class="sxs-lookup"><span data-stu-id="fdb49-437">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="fdb49-438">443</span><span class="sxs-lookup"><span data-stu-id="fdb49-438">443</span></span></p></td>
<td><p><span data-ttu-id="fdb49-439">H</span><span class="sxs-lookup"><span data-stu-id="fdb49-439">HTTPS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fdb49-440">디렉터 부하 분산 장치</span><span class="sxs-lookup"><span data-stu-id="fdb49-440">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="fdb49-441">444</span><span class="sxs-lookup"><span data-stu-id="fdb49-441">444</span></span></p></td>
<td><p><span data-ttu-id="fdb49-442">H</span><span class="sxs-lookup"><span data-stu-id="fdb49-442">HTTPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fdb49-443">디렉터 부하 분산 장치</span><span class="sxs-lookup"><span data-stu-id="fdb49-443">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="fdb49-444">5061</span><span class="sxs-lookup"><span data-stu-id="fdb49-444">5061</span></span></p></td>
<td><p><span data-ttu-id="fdb49-445">TCP</span><span class="sxs-lookup"><span data-stu-id="fdb49-445">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fdb49-446">디렉터 부하 분산 장치</span><span class="sxs-lookup"><span data-stu-id="fdb49-446">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="fdb49-447">4443</span><span class="sxs-lookup"><span data-stu-id="fdb49-447">4443</span></span></p></td>
<td><p><span data-ttu-id="fdb49-448">HTTPS(역방향 프록시)</span><span class="sxs-lookup"><span data-stu-id="fdb49-448">HTTPS (from reverse proxy)</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="fdb49-p107">DNS 부하 분산을 사용하는 프런트 엔드 풀 및 디렉터 풀에는 하드웨어 부하 분산 장치도 배포되어 있어야 합니다. 다음 표에서는 이러한 하드웨어 부하 분산 장치에서 열어야 하는 포트를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="fdb49-p107">Your Front End pools and Director pools that use DNS load balancing also must have a hardware load balancer deployed. The following table shows the ports that need to be open on these hardware load balancers.</span></span>

### <a name="hardware-load-balancer-ports-if-using-dns-load-balancing"></a><span data-ttu-id="fdb49-451">DNS 부하 분산을 사용하는 경우 하드웨어 부하 분산 장치 포트</span><span class="sxs-lookup"><span data-stu-id="fdb49-451">Hardware Load Balancer Ports if Using DNS Load Balancing</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fdb49-452">부하 분산 장치</span><span class="sxs-lookup"><span data-stu-id="fdb49-452">Load Balancer</span></span></th>
<th><span data-ttu-id="fdb49-453">포트</span><span class="sxs-lookup"><span data-stu-id="fdb49-453">Port</span></span></th>
<th><span data-ttu-id="fdb49-454">Protocol(프로토콜)</span><span class="sxs-lookup"><span data-stu-id="fdb49-454">Protocol</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fdb49-455">프런트 엔드 서버 부하 분산 장치</span><span class="sxs-lookup"><span data-stu-id="fdb49-455">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="fdb49-456">80</span><span class="sxs-lookup"><span data-stu-id="fdb49-456">80</span></span></p></td>
<td><p><span data-ttu-id="fdb49-457">HTTP</span><span class="sxs-lookup"><span data-stu-id="fdb49-457">HTTP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fdb49-458">프런트 엔드 서버 부하 분산 장치</span><span class="sxs-lookup"><span data-stu-id="fdb49-458">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="fdb49-459">443</span><span class="sxs-lookup"><span data-stu-id="fdb49-459">443</span></span></p></td>
<td><p><span data-ttu-id="fdb49-460">H</span><span class="sxs-lookup"><span data-stu-id="fdb49-460">HTTPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fdb49-461">프런트 엔드 서버 부하 분산 장치</span><span class="sxs-lookup"><span data-stu-id="fdb49-461">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="fdb49-462">8080</span><span class="sxs-lookup"><span data-stu-id="fdb49-462">8080</span></span></p></td>
<td><p><span data-ttu-id="fdb49-463">TCP - 프런트 엔드 서버에서 루트 인증서의 클라이언트 및 장치 검색 - 클라이언트 및 장치는 NTLM으로 인증됩니다.</span><span class="sxs-lookup"><span data-stu-id="fdb49-463">TCP - Client and device retrieval of root certificate from Front End Server – clients and devices authenticated by NTLM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fdb49-464">프런트 엔드 서버 부하 분산 장치</span><span class="sxs-lookup"><span data-stu-id="fdb49-464">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="fdb49-465">4443</span><span class="sxs-lookup"><span data-stu-id="fdb49-465">4443</span></span></p></td>
<td><p><span data-ttu-id="fdb49-466">HTTPS(역방향 프록시)</span><span class="sxs-lookup"><span data-stu-id="fdb49-466">HTTPS (from reverse proxy)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fdb49-467">디렉터 부하 분산 장치</span><span class="sxs-lookup"><span data-stu-id="fdb49-467">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="fdb49-468">443</span><span class="sxs-lookup"><span data-stu-id="fdb49-468">443</span></span></p></td>
<td><p><span data-ttu-id="fdb49-469">H</span><span class="sxs-lookup"><span data-stu-id="fdb49-469">HTTPS</span></span></p></td>
</tr>
<tr class="even">
<td> </td>
<td> </td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fdb49-470">디렉터 부하 분산 장치</span><span class="sxs-lookup"><span data-stu-id="fdb49-470">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="fdb49-471">4443</span><span class="sxs-lookup"><span data-stu-id="fdb49-471">4443</span></span></p></td>
<td><p><span data-ttu-id="fdb49-472">HTTPS(역방향 프록시)</span><span class="sxs-lookup"><span data-stu-id="fdb49-472">HTTPS (from reverse proxy)</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="required-client-ports"></a><span data-ttu-id="fdb49-473">필요한 클라이언트 포트</span><span class="sxs-lookup"><span data-stu-id="fdb49-473">Required Client Ports</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fdb49-474">구성 요소</span><span class="sxs-lookup"><span data-stu-id="fdb49-474">Component</span></span></th>
<th><span data-ttu-id="fdb49-475">포트</span><span class="sxs-lookup"><span data-stu-id="fdb49-475">Port</span></span></th>
<th><span data-ttu-id="fdb49-476">Protocol(프로토콜)</span><span class="sxs-lookup"><span data-stu-id="fdb49-476">Protocol</span></span></th>
<th><span data-ttu-id="fdb49-477">참고</span><span class="sxs-lookup"><span data-stu-id="fdb49-477">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fdb49-478">클라이언트</span><span class="sxs-lookup"><span data-stu-id="fdb49-478">Clients</span></span></p></td>
<td><p><span data-ttu-id="fdb49-479">67/68</span><span class="sxs-lookup"><span data-stu-id="fdb49-479">67/68</span></span></p></td>
<td><p><span data-ttu-id="fdb49-480">서버의</span><span class="sxs-lookup"><span data-stu-id="fdb49-480">DHCP</span></span></p></td>
<td><p><span data-ttu-id="fdb49-481">Lync Server에서 등록자 FQDN을 찾는 데 사용 됩니다 (즉, DNS SRV에 오류가 발생 하 여 수동 설정이 구성 되지 않은 경우).</span><span class="sxs-lookup"><span data-stu-id="fdb49-481">Used by Lync Server to find the Registrar FQDN (that is, if DNS SRV fails and manual settings are not configured).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fdb49-482">클라이언트</span><span class="sxs-lookup"><span data-stu-id="fdb49-482">Clients</span></span></p></td>
<td><p><span data-ttu-id="fdb49-483">443</span><span class="sxs-lookup"><span data-stu-id="fdb49-483">443</span></span></p></td>
<td><p><span data-ttu-id="fdb49-484">TCP(TLS)</span><span class="sxs-lookup"><span data-stu-id="fdb49-484">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="fdb49-485">외부 사용자 액세스의 클라이언트-서버 SIP 트래픽에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="fdb49-485">Used for client-to-server SIP traffic for external user access.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fdb49-486">클라이언트</span><span class="sxs-lookup"><span data-stu-id="fdb49-486">Clients</span></span></p></td>
<td><p><span data-ttu-id="fdb49-487">443</span><span class="sxs-lookup"><span data-stu-id="fdb49-487">443</span></span></p></td>
<td><p><span data-ttu-id="fdb49-488">TCP(PSOM/TLS)</span><span class="sxs-lookup"><span data-stu-id="fdb49-488">TCP (PSOM/TLS)</span></span></p></td>
<td><p><span data-ttu-id="fdb49-489">웹 회의 세션에 대한 외부 사용자 액세스에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="fdb49-489">Used for external user access to web conferencing sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fdb49-490">클라이언트</span><span class="sxs-lookup"><span data-stu-id="fdb49-490">Clients</span></span></p></td>
<td><p><span data-ttu-id="fdb49-491">443</span><span class="sxs-lookup"><span data-stu-id="fdb49-491">443</span></span></p></td>
<td><p><span data-ttu-id="fdb49-492">TCP(STUN/MSTURN)</span><span class="sxs-lookup"><span data-stu-id="fdb49-492">TCP (STUN/MSTURN)</span></span></p></td>
<td><p><span data-ttu-id="fdb49-493">A/V 세션 및 미디어(TCP)에 대한 외부 사용자 액세스에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="fdb49-493">Used for external user access to A/V sessions and media (TCP)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fdb49-494">클라이언트</span><span class="sxs-lookup"><span data-stu-id="fdb49-494">Clients</span></span></p></td>
<td><p><span data-ttu-id="fdb49-495">3478</span><span class="sxs-lookup"><span data-stu-id="fdb49-495">3478</span></span></p></td>
<td><p><span data-ttu-id="fdb49-496">UDP(STUN/MSTURN)</span><span class="sxs-lookup"><span data-stu-id="fdb49-496">UDP (STUN/MSTURN)</span></span></p></td>
<td><p><span data-ttu-id="fdb49-497">A/V 세션 및 미디어에 대 한 외부 사용자 액세스 (UDP)에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fdb49-497">Used for external user access to A/V sessions and media (UDP)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fdb49-498">클라이언트</span><span class="sxs-lookup"><span data-stu-id="fdb49-498">Clients</span></span></p></td>
<td><p><span data-ttu-id="fdb49-499">5061</span><span class="sxs-lookup"><span data-stu-id="fdb49-499">5061</span></span></p></td>
<td><p><span data-ttu-id="fdb49-500">TCP(MTLS)</span><span class="sxs-lookup"><span data-stu-id="fdb49-500">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="fdb49-501">외부 사용자 액세스의 클라이언트-서버 SIP 트래픽에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="fdb49-501">Used for client-to-server SIP traffic for external user access.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fdb49-502">클라이언트</span><span class="sxs-lookup"><span data-stu-id="fdb49-502">Clients</span></span></p></td>
<td><p><span data-ttu-id="fdb49-503">6891-6901</span><span class="sxs-lookup"><span data-stu-id="fdb49-503">6891-6901</span></span></p></td>
<td><p><span data-ttu-id="fdb49-504">TCP</span><span class="sxs-lookup"><span data-stu-id="fdb49-504">TCP</span></span></p></td>
<td><p><span data-ttu-id="fdb49-505">Lync 클라이언트와 이전 클라이언트 (Microsoft Office Communications Server 2007 R2, Microsoft Office Communications Server 2007 및 Live Communications Server 2005의 클라이언트) 간의 파일 전송에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fdb49-505">Used for file transfer between Lync clients and previous clients (clients of Microsoft Office Communications Server 2007 R2, Microsoft Office Communications Server 2007, and Live Communications Server 2005).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fdb49-506">클라이언트</span><span class="sxs-lookup"><span data-stu-id="fdb49-506">Clients</span></span></p></td>
<td><p><span data-ttu-id="fdb49-507">1024-65535 \*</span><span class="sxs-lookup"><span data-stu-id="fdb49-507">1024-65535 \*</span></span></p></td>
<td><p><span data-ttu-id="fdb49-508">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="fdb49-508">TCP/UDP</span></span></p></td>
<td><p><span data-ttu-id="fdb49-509">오디오 포트 범위(최소 20개 포트 필요)</span><span class="sxs-lookup"><span data-stu-id="fdb49-509">Audio port range (minimum of 20 ports required)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fdb49-510">클라이언트</span><span class="sxs-lookup"><span data-stu-id="fdb49-510">Clients</span></span></p></td>
<td><p><span data-ttu-id="fdb49-511">1024-65535 \*</span><span class="sxs-lookup"><span data-stu-id="fdb49-511">1024-65535 \*</span></span></p></td>
<td><p><span data-ttu-id="fdb49-512">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="fdb49-512">TCP/UDP</span></span></p></td>
<td><p><span data-ttu-id="fdb49-513">비디오 포트 범위(최소 20개 포트 필요)</span><span class="sxs-lookup"><span data-stu-id="fdb49-513">Video port range (minimum of 20 ports required).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fdb49-514">클라이언트</span><span class="sxs-lookup"><span data-stu-id="fdb49-514">Clients</span></span></p></td>
<td><p><span data-ttu-id="fdb49-515">1024-65535 \*</span><span class="sxs-lookup"><span data-stu-id="fdb49-515">1024-65535 \*</span></span></p></td>
<td><p><span data-ttu-id="fdb49-516">TCP</span><span class="sxs-lookup"><span data-stu-id="fdb49-516">TCP</span></span></p></td>
<td><p><span data-ttu-id="fdb49-517">피어 투 피어 파일 전송(회의 파일 전송의 경우 클라이언트가 PSOM 사용).</span><span class="sxs-lookup"><span data-stu-id="fdb49-517">Peer-to-peer file transfer (for conferencing file transfer, clients use PSOM).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fdb49-518">클라이언트</span><span class="sxs-lookup"><span data-stu-id="fdb49-518">Clients</span></span></p></td>
<td><p><span data-ttu-id="fdb49-519">1024-65535 \*</span><span class="sxs-lookup"><span data-stu-id="fdb49-519">1024-65535 \*</span></span></p></td>
<td><p><span data-ttu-id="fdb49-520">TCP</span><span class="sxs-lookup"><span data-stu-id="fdb49-520">TCP</span></span></p></td>
<td><p><span data-ttu-id="fdb49-521">응용 프로그램 공유</span><span class="sxs-lookup"><span data-stu-id="fdb49-521">Application sharing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fdb49-522">Aastra 6721ip 공통 영역 전화</span><span class="sxs-lookup"><span data-stu-id="fdb49-522">Aastra 6721ip common area phone</span></span></p>
<p><span data-ttu-id="fdb49-523">Aastra 6725ip 일반 전화기</span><span class="sxs-lookup"><span data-stu-id="fdb49-523">Aastra 6725ip desk phone</span></span></p>
<p><span data-ttu-id="fdb49-524">HP 4110 IP 전화(공통 영역 전화)</span><span class="sxs-lookup"><span data-stu-id="fdb49-524">HP 4110 IP Phone (common area phone)</span></span></p>
<p><span data-ttu-id="fdb49-525">HP 4120 IP 전화(일반 전화기)</span><span class="sxs-lookup"><span data-stu-id="fdb49-525">HP 4120 IP Phone (desk phone)</span></span></p>
<p><span data-ttu-id="fdb49-526">Polycom CX500 IP 공통 영역 전화</span><span class="sxs-lookup"><span data-stu-id="fdb49-526">Polycom CX500 IP common area phone</span></span></p>
<p><span data-ttu-id="fdb49-527">Polycom CX600 IP 일반 전화기</span><span class="sxs-lookup"><span data-stu-id="fdb49-527">Polycom CX600 IP desk phone</span></span></p>
<p><span data-ttu-id="fdb49-528">Polycom CX700 IP 일반 전화기</span><span class="sxs-lookup"><span data-stu-id="fdb49-528">Polycom CX700 IP desk phone</span></span></p>
<p><span data-ttu-id="fdb49-529">Polycom CX3000 IP 회의 전화</span><span class="sxs-lookup"><span data-stu-id="fdb49-529">Polycom CX3000 IP conference phone</span></span></p></td>
<td><p><span data-ttu-id="fdb49-530">67/68</span><span class="sxs-lookup"><span data-stu-id="fdb49-530">67/68</span></span></p></td>
<td><p><span data-ttu-id="fdb49-531">서버의</span><span class="sxs-lookup"><span data-stu-id="fdb49-531">DHCP</span></span></p></td>
<td><p><span data-ttu-id="fdb49-532">나열 된 장치에서 Lync Server 인증서, 프로 비전 FQDN 및 등록자 FQDN을 찾는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fdb49-532">Used by the listed devices to find the Lync Server certificate, provisioning FQDN, and Registrar FQDN.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="fdb49-533">**\*** 이러한 미디어 유형에 대 한 특정 포트를 구성 하려면 Get-csconferencingconfiguration cmdlet (ClientMediaPortRangeEnabled, ClientMediaPort 및 ClientMediaPortRange 매개 변수)을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="fdb49-533">**\*** To configure specific ports for these media types, use the CsConferencingConfiguration cmdlet (ClientMediaPortRangeEnabled, ClientMediaPort, and ClientMediaPortRange parameters).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="fdb49-534">Lync 클라이언트에 대 한 프로그램 설정에서는 클라이언트 컴퓨터에 필요한 운영 체제 방화벽 예외를 자동으로 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="fdb49-534">The set programs for Lync clients automatically create the required operating-system firewall exceptions on the client computer.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="fdb49-535">외부 사용자 액세스를 위해 사용되는 포트는 클라이언트가 조직의 방화벽을 통과해야 하는 모든 시나리오에 필요합니다(예: 외부 통신 또는 다른 조직에서 호스트되는 모임).</span><span class="sxs-lookup"><span data-stu-id="fdb49-535">The ports that are used for external user access are required for any scenario in which the client must traverse the organization’s firewall (for example, any external communications or meetings hosted by other organizations).</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

