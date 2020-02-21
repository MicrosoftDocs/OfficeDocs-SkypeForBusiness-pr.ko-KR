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
ms.openlocfilehash: 42f40265cf7b8fff7fd6cbf3d4f67a2fb9f558fa
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42208795"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="ports-and-protocols-for-internal-servers-in-lync-server-2013"></a><span data-ttu-id="aba70-102">Lync Server 2013의 내부 서버에 대 한 포트 및 프로토콜</span><span class="sxs-lookup"><span data-stu-id="aba70-102">Ports and protocols for internal servers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="aba70-103">_**마지막으로 수정 된 항목:** 2016-04-06_</span><span class="sxs-lookup"><span data-stu-id="aba70-103">_**Topic Last Modified:** 2016-04-06_</span></span>

<span data-ttu-id="aba70-104">이 섹션에서는 Lync Server 배포의 서버, 부하 분산 장치 및 클라이언트에서 사용 되는 포트와 프로토콜에 대해 간략히 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="aba70-104">This section summarizes the ports and protocols used by servers, load balancers, and clients in a Lync Server deployment.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="aba70-105">Lync 및 Communicator 클라이언트는 일대일 통신에 관여 하는 경우 피어-투-피어 라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="aba70-105">Lync and Communicator clients when involved in a one to one communication, is often referred to as peer-to-peer.</span></span> <span data-ttu-id="aba70-106">기술적으로 두 클라이언트는 중앙에 있는 IMMCU (인스턴트 메시징 multipoint control unit)를 사용 하 여 일대일 대화로 통신 합니다.</span><span class="sxs-lookup"><span data-stu-id="aba70-106">Technically, the two clients are communicating in a one to one conversation, with the Instant Messaging multipoint control unit (IMMCU) in the middle.</span></span> <span data-ttu-id="aba70-107">IMMCU는 프런트 엔드 서버의 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="aba70-107">The IMMCU is a component of Front End Server.</span></span> <span data-ttu-id="aba70-108">필요한 통신 워크플로에 IMMCU를 배치 하면 프런트 엔드 서버에서 사용 하는 통화 정보 기록 및 기타 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aba70-108">Placing the IMMCU in the required communication workflow allows call detail recording and other features that the Front End Server enables.</span></span> <span data-ttu-id="aba70-109">클라이언트의 동적 원본 포트에서 프런트 엔드 서버 포트 TLS/TCP/5061 (권장 전송 계층 보안을 사용 하는 경우)으로 통신 합니다.</span><span class="sxs-lookup"><span data-stu-id="aba70-109">Communication is from a dynamic source port on the client to the Front End Server port TLS/TCP/5061 (assuming the use of the recommended transport layer security).</span></span> <span data-ttu-id="aba70-110">Lync Server 및 IMMCU가 활성 상태이 고 사용 가능한 경우에만 피어-투-피어 통신 및 여러 당사자 IM을 기본적으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aba70-110">By design, peer-to-peer communication (as well as multi-party IM) is possible only when Lync Server and the IMMCU is active and available.</span></span>



</div>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="aba70-111">포트 및 프로토콜 세부 정보</span><span class="sxs-lookup"><span data-stu-id="aba70-111">Port and Protocol Details</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="aba70-112">Lync server가 방화벽에서 필요한 포트를 여는 경우에는 서버에서 Lync Server 서비스를 시작 하기 전에 Windows 방화벽이 실행 중 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aba70-112">Windows Firewall must be running before you start the Lync Server services on a server, because that is when Lync Server opens the required ports in the firewall.</span></span>



</div>

<span data-ttu-id="aba70-113">에 지 구성 요소의 방화벽 구성에 대 한 자세한 내용은 [Lync Server 2013에 대 한 외부 A/V 방화벽 및 포트 요구 사항 확인](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="aba70-113">For details about firewall configuration for edge components, see [Determine external A/V firewall and port requirements for Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md).</span></span>

<span data-ttu-id="aba70-114">다음 표에는 각 내부 서버 역할에서 열어야 하는 포트가 나열되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aba70-114">The following table lists the ports that need to be open on each internal server role.</span></span>

### <a name="required-server-ports-by-server-role"></a><span data-ttu-id="aba70-115">필요한 서버 포트(서버 역할별)</span><span class="sxs-lookup"><span data-stu-id="aba70-115">Required Server Ports (by Server Role)</span></span>

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
<th><span data-ttu-id="aba70-116">서버 역할</span><span class="sxs-lookup"><span data-stu-id="aba70-116">Server role</span></span></th>
<th><span data-ttu-id="aba70-117">서비스 이름</span><span class="sxs-lookup"><span data-stu-id="aba70-117">Service name</span></span></th>
<th><span data-ttu-id="aba70-118">포트</span><span class="sxs-lookup"><span data-stu-id="aba70-118">Port</span></span></th>
<th><span data-ttu-id="aba70-119">프로토콜로</span><span class="sxs-lookup"><span data-stu-id="aba70-119">Protocol</span></span></th>
<th><span data-ttu-id="aba70-120">Notes</span><span class="sxs-lookup"><span data-stu-id="aba70-120">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="aba70-121">모든 서버</span><span class="sxs-lookup"><span data-stu-id="aba70-121">All Servers</span></span></p></td>
<td><p><span data-ttu-id="aba70-122">SQL Browser</span><span class="sxs-lookup"><span data-stu-id="aba70-122">SQL Browser</span></span></p></td>
<td><p><span data-ttu-id="aba70-123">1434</span><span class="sxs-lookup"><span data-stu-id="aba70-123">1434</span></span></p></td>
<td><p><span data-ttu-id="aba70-124">P</span><span class="sxs-lookup"><span data-stu-id="aba70-124">UDP</span></span></p></td>
<td><p><span data-ttu-id="aba70-125">중앙 관리 저장소 데이터베이스의 복제 된 로컬 복사본에 대 한 SQL 브라우저입니다.</span><span class="sxs-lookup"><span data-stu-id="aba70-125">SQL Browser for the local replicated copy of the Central Management Store database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aba70-126">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="aba70-126">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="aba70-127">Lync Server 프런트 엔드 서비스</span><span class="sxs-lookup"><span data-stu-id="aba70-127">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="aba70-128">5060</span><span class="sxs-lookup"><span data-stu-id="aba70-128">5060</span></span></p></td>
<td><p><span data-ttu-id="aba70-129">TCP</span><span class="sxs-lookup"><span data-stu-id="aba70-129">TCP</span></span></p></td>
<td><p><span data-ttu-id="aba70-130">필요에 따라 Standard Edition Server 및 프런트 엔드 서버에서 원격 호출 제어 서버와 같은 트러스트된 서비스에 대한 고정 경로에 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="aba70-130">Optionally used by Standard Edition servers and Front End Servers for static routes to trusted services, such as remote call control servers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aba70-131">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="aba70-131">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="aba70-132">Lync Server 프런트 엔드 서비스</span><span class="sxs-lookup"><span data-stu-id="aba70-132">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="aba70-133">5061</span><span class="sxs-lookup"><span data-stu-id="aba70-133">5061</span></span></p></td>
<td><p><span data-ttu-id="aba70-134">TCP(TLS)</span><span class="sxs-lookup"><span data-stu-id="aba70-134">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="aba70-p102">Standard Edition Server 및 프런트 엔드 풀에서 서버 간 모든 내부 SIP 통신(MTLS), 서버와 클라이언트 간 SIP 통신(TLS) 및 프런트 엔드 서버와 중재 서버 간 SIP 통신(MTLS)에 사용됩니다. 또한 모니터링 서버와의 통신에도 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="aba70-p102">Used by Standard Edition servers and Front End pools for all internal SIP communications between servers (MTLS), for SIP communications between Server and Client (TLS) and for SIP communications between Front End Servers and Mediation Servers (MTLS). Also used for communications with Monitoring Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aba70-137">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="aba70-137">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="aba70-138">Lync Server 프런트 엔드 서비스</span><span class="sxs-lookup"><span data-stu-id="aba70-138">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="aba70-139">444</span><span class="sxs-lookup"><span data-stu-id="aba70-139">444</span></span></p></td>
<td><p><span data-ttu-id="aba70-140">H</span><span class="sxs-lookup"><span data-stu-id="aba70-140">HTTPS</span></span></p>
<p><span data-ttu-id="aba70-141">TCP</span><span class="sxs-lookup"><span data-stu-id="aba70-141">TCP</span></span></p></td>
<td><p><span data-ttu-id="aba70-142">포커스 (회의 상태를 관리 하는 Lync Server 구성 요소)와 개별 서버 간의 HTTPS 통신에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="aba70-142">Used for HTTPS communication between the Focus (the Lync Server component that manages conference state) and the individual servers.</span></span></p>
<p><span data-ttu-id="aba70-143">이 포트는 Sba (survivable 분기 기기와 프런트 엔드 서버 간의 TCP 통신에도 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="aba70-143">This port is also used for TCP communication between Survivable Branch Appliances and Front End Servers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aba70-144">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="aba70-144">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="aba70-145">Lync Server 프런트 엔드 서비스</span><span class="sxs-lookup"><span data-stu-id="aba70-145">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="aba70-146">135</span><span class="sxs-lookup"><span data-stu-id="aba70-146">135</span></span></p></td>
<td><p><span data-ttu-id="aba70-147">DCOM 및 RPC(원격 프로시저 호출)</span><span class="sxs-lookup"><span data-stu-id="aba70-147">DCOM and remote procedure call (RPC)</span></span></p></td>
<td><p><span data-ttu-id="aba70-148">사용자 이동, User Replicator 동기화 및 주소록 동기화와 같은 DCOM 기반 작업에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="aba70-148">Used for DCOM based operations such as Moving Users, User Replicator Synchronization, and Address Book Synchronization.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aba70-149">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="aba70-149">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="aba70-150">Lync Server IM 회의 서비스</span><span class="sxs-lookup"><span data-stu-id="aba70-150">Lync Server IM Conferencing service</span></span></p></td>
<td><p><span data-ttu-id="aba70-151">5062</span><span class="sxs-lookup"><span data-stu-id="aba70-151">5062</span></span></p></td>
<td><p><span data-ttu-id="aba70-152">TCP</span><span class="sxs-lookup"><span data-stu-id="aba70-152">TCP</span></span></p></td>
<td><p><span data-ttu-id="aba70-153">IM(인스턴트 메시징) 회의의 받는 SIP 요청에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="aba70-153">Used for incoming SIP requests for instant messaging (IM) conferencing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aba70-154">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="aba70-154">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="aba70-155">Lync Server 웹 회의 서비스</span><span class="sxs-lookup"><span data-stu-id="aba70-155">Lync Server Web Conferencing service</span></span></p></td>
<td><p><span data-ttu-id="aba70-156">8057</span><span class="sxs-lookup"><span data-stu-id="aba70-156">8057</span></span></p></td>
<td><p><span data-ttu-id="aba70-157">TCP(TLS)</span><span class="sxs-lookup"><span data-stu-id="aba70-157">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="aba70-158">클라이언트에서 PSOM(영구적 공유 개체 모델) 연결을 수신 대기하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="aba70-158">Used to listen for Persistent Shared Object Model (PSOM) connections from client.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aba70-159">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="aba70-159">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="aba70-160">Lync Server 웹 회의 호환성 서비스</span><span class="sxs-lookup"><span data-stu-id="aba70-160">Lync Server Web Conferencing Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="aba70-161">8058</span><span class="sxs-lookup"><span data-stu-id="aba70-161">8058</span></span></p></td>
<td><p><span data-ttu-id="aba70-162">TCP(TLS)</span><span class="sxs-lookup"><span data-stu-id="aba70-162">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="aba70-163">Live Meeting 클라이언트 및 이전 버전의 Lync Server에서 PSOM (영구 공유 개체 모델) 연결을 수신 대기 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="aba70-163">Used to listen for Persistent Shared Object Model (PSOM) connections from the Live Meeting client and previous versions of Lync Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aba70-164">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="aba70-164">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="aba70-165">Lync Server 오디오/비디오 회의 서비스</span><span class="sxs-lookup"><span data-stu-id="aba70-165">Lync Server Audio/Video Conferencing service</span></span></p></td>
<td><p><span data-ttu-id="aba70-166">5063</span><span class="sxs-lookup"><span data-stu-id="aba70-166">5063</span></span></p></td>
<td><p><span data-ttu-id="aba70-167">TCP</span><span class="sxs-lookup"><span data-stu-id="aba70-167">TCP</span></span></p></td>
<td><p><span data-ttu-id="aba70-168">A/V(오디오/비디오) 회의의 받는 SIP 요청에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="aba70-168">Used for incoming SIP requests for audio/video (A/V) conferencing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aba70-169">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="aba70-169">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="aba70-170">Lync Server 오디오/비디오 회의 서비스</span><span class="sxs-lookup"><span data-stu-id="aba70-170">Lync Server Audio/Video Conferencing service</span></span></p></td>
<td><p><span data-ttu-id="aba70-171">57501-65535</span><span class="sxs-lookup"><span data-stu-id="aba70-171">57501-65535</span></span></p></td>
<td><p><span data-ttu-id="aba70-172">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="aba70-172">TCP/UDP</span></span></p></td>
<td><p><span data-ttu-id="aba70-173">비디오 회의에 사용되는 미디어 포트 범위입니다.</span><span class="sxs-lookup"><span data-stu-id="aba70-173">Media port range used for video conferencing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aba70-174">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="aba70-174">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="aba70-175">Lync Server 웹 호환성 서비스</span><span class="sxs-lookup"><span data-stu-id="aba70-175">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="aba70-176">80</span><span class="sxs-lookup"><span data-stu-id="aba70-176">80</span></span></p></td>
<td><p><span data-ttu-id="aba70-177">HTTP</span><span class="sxs-lookup"><span data-stu-id="aba70-177">HTTP</span></span></p></td>
<td><p><span data-ttu-id="aba70-178">HTTPS가 사용되지 않을 경우 프런트 엔드 서버에서 웹 팜 FQDN(IIS 웹 구성 요소에서 사용하는 URL)으로의 통신에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="aba70-178">Used for communication from Front End Servers to the web farm FQDNs (the URLs used by IIS web components) when HTTPS is not used.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aba70-179">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="aba70-179">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="aba70-180">Lync Server 웹 호환성 서비스</span><span class="sxs-lookup"><span data-stu-id="aba70-180">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="aba70-181">443</span><span class="sxs-lookup"><span data-stu-id="aba70-181">443</span></span></p></td>
<td><p><span data-ttu-id="aba70-182">H</span><span class="sxs-lookup"><span data-stu-id="aba70-182">HTTPS</span></span></p></td>
<td><p><span data-ttu-id="aba70-183">프런트 엔드 서버에서 웹 팜 FQDN(IIS 웹 구성 요소에서 사용하는 URL)으로의 통신에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="aba70-183">Used for communication from Front End Servers to the web farm FQDNs (the URLs used by IIS web components).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aba70-184">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="aba70-184">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="aba70-185">Lync Server 웹 호환성 서비스</span><span class="sxs-lookup"><span data-stu-id="aba70-185">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="aba70-186">8080</span><span class="sxs-lookup"><span data-stu-id="aba70-186">8080</span></span></p></td>
<td><p><span data-ttu-id="aba70-187">TCP 및 HTTP</span><span class="sxs-lookup"><span data-stu-id="aba70-187">TCP and HTTP</span></span></p></td>
<td><p><span data-ttu-id="aba70-188">외부 액세스용 웹 구성 요소에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="aba70-188">Used by web components for external access.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aba70-189">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="aba70-189">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="aba70-190">웹 서버 구성 요소</span><span class="sxs-lookup"><span data-stu-id="aba70-190">Web server component</span></span></p></td>
<td><p><span data-ttu-id="aba70-191">4443</span><span class="sxs-lookup"><span data-stu-id="aba70-191">4443</span></span></p></td>
<td><p><span data-ttu-id="aba70-192">H</span><span class="sxs-lookup"><span data-stu-id="aba70-192">HTTPS</span></span></p></td>
<td><p><span data-ttu-id="aba70-193">자동 검색 로그인에 대 한 HTTPS (역방향 프록시) 및 HTTPS 프런트 엔드 풀 간 통신</span><span class="sxs-lookup"><span data-stu-id="aba70-193">HTTPS (from Reverse Proxy) and HTTPS Front End inter-pool communications for Autodiscover sign-in.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aba70-194">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="aba70-194">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="aba70-195">웹 서버 구성 요소</span><span class="sxs-lookup"><span data-stu-id="aba70-195">Web server component</span></span></p></td>
<td><p><span data-ttu-id="aba70-196">8060</span><span class="sxs-lookup"><span data-stu-id="aba70-196">8060</span></span></p></td>
<td><p><span data-ttu-id="aba70-197">TCP(MTLS)</span><span class="sxs-lookup"><span data-stu-id="aba70-197">TCP (MTLS)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aba70-198">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="aba70-198">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="aba70-199">웹 서버 구성 요소</span><span class="sxs-lookup"><span data-stu-id="aba70-199">Web server component</span></span></p></td>
<td><p><span data-ttu-id="aba70-200">8061</span><span class="sxs-lookup"><span data-stu-id="aba70-200">8061</span></span></p></td>
<td><p><span data-ttu-id="aba70-201">TCP(MTLS)</span><span class="sxs-lookup"><span data-stu-id="aba70-201">TCP (MTLS)</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aba70-202">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="aba70-202">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="aba70-203">Mobility Services 구성 요소</span><span class="sxs-lookup"><span data-stu-id="aba70-203">Mobility Services component</span></span></p></td>
<td><p><span data-ttu-id="aba70-204">5086</span><span class="sxs-lookup"><span data-stu-id="aba70-204">5086</span></span></p></td>
<td><p><span data-ttu-id="aba70-205">TCP(MTLS)</span><span class="sxs-lookup"><span data-stu-id="aba70-205">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="aba70-206">모바일 서비스 내부 프로세스에서 사용 하는 SIP 포트</span><span class="sxs-lookup"><span data-stu-id="aba70-206">SIP port used by Mobility Services internal processes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aba70-207">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="aba70-207">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="aba70-208">Mobility Services 구성 요소</span><span class="sxs-lookup"><span data-stu-id="aba70-208">Mobility Services component</span></span></p></td>
<td><p><span data-ttu-id="aba70-209">5087</span><span class="sxs-lookup"><span data-stu-id="aba70-209">5087</span></span></p></td>
<td><p><span data-ttu-id="aba70-210">TCP(MTLS)</span><span class="sxs-lookup"><span data-stu-id="aba70-210">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="aba70-211">모바일 서비스 내부 프로세스에서 사용 하는 SIP 포트</span><span class="sxs-lookup"><span data-stu-id="aba70-211">SIP port used by Mobility Services internal processes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aba70-212">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="aba70-212">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="aba70-213">Mobility Services 구성 요소</span><span class="sxs-lookup"><span data-stu-id="aba70-213">Mobility Services component</span></span></p></td>
<td><p><span data-ttu-id="aba70-214">443</span><span class="sxs-lookup"><span data-stu-id="aba70-214">443</span></span></p></td>
<td><p><span data-ttu-id="aba70-215">H</span><span class="sxs-lookup"><span data-stu-id="aba70-215">HTTPS</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aba70-216">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="aba70-216">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="aba70-217">Lync Server 회의 수행자 서비스 (전화 접속 회의)</span><span class="sxs-lookup"><span data-stu-id="aba70-217">Lync Server Conferencing Attendant service (dial-in conferencing)</span></span></p></td>
<td><p><span data-ttu-id="aba70-218">5064</span><span class="sxs-lookup"><span data-stu-id="aba70-218">5064</span></span></p></td>
<td><p><span data-ttu-id="aba70-219">TCP</span><span class="sxs-lookup"><span data-stu-id="aba70-219">TCP</span></span></p></td>
<td><p><span data-ttu-id="aba70-220">전화 접속 회의의 받는 SIP 요청에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="aba70-220">Used for incoming SIP requests for dial-in conferencing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aba70-221">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="aba70-221">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="aba70-222">Lync Server 회의 수행자 서비스 (전화 접속 회의)</span><span class="sxs-lookup"><span data-stu-id="aba70-222">Lync Server Conferencing Attendant service (dial-in conferencing)</span></span></p></td>
<td><p><span data-ttu-id="aba70-223">5072</span><span class="sxs-lookup"><span data-stu-id="aba70-223">5072</span></span></p></td>
<td><p><span data-ttu-id="aba70-224">TCP</span><span class="sxs-lookup"><span data-stu-id="aba70-224">TCP</span></span></p></td>
<td><p><span data-ttu-id="aba70-225">받는 전화 회의에 대 한 들어오는 SIP 요청에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="aba70-225">Used for incoming SIP requests for Attendant (dial in conferencing).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aba70-226">배치된 중재 서버를 실행하는 프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="aba70-226">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="aba70-227">Lync Server 중재 서비스</span><span class="sxs-lookup"><span data-stu-id="aba70-227">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="aba70-228">5070</span><span class="sxs-lookup"><span data-stu-id="aba70-228">5070</span></span></p></td>
<td><p><span data-ttu-id="aba70-229">TCP</span><span class="sxs-lookup"><span data-stu-id="aba70-229">TCP</span></span></p></td>
<td><p><span data-ttu-id="aba70-230">중재 서버에서 프런트 엔드 서버에서 중재 서버로의 받는 요청에 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="aba70-230">Used by the Mediation Server for incoming requests from the Front End Server to the Mediation Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aba70-231">배치된 중재 서버를 실행하는 프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="aba70-231">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="aba70-232">Lync Server 중재 서비스</span><span class="sxs-lookup"><span data-stu-id="aba70-232">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="aba70-233">5067</span><span class="sxs-lookup"><span data-stu-id="aba70-233">5067</span></span></p></td>
<td><p><span data-ttu-id="aba70-234">TCP(TLS)</span><span class="sxs-lookup"><span data-stu-id="aba70-234">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="aba70-235">PSTN 게이트웨이에서 중재 서버로의 받는 SIP 요청에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="aba70-235">Used for incoming SIP requests from the PSTN gateway to the Mediation Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aba70-236">배치된 중재 서버를 실행하는 프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="aba70-236">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="aba70-237">Lync Server 중재 서비스</span><span class="sxs-lookup"><span data-stu-id="aba70-237">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="aba70-238">5068</span><span class="sxs-lookup"><span data-stu-id="aba70-238">5068</span></span></p></td>
<td><p><span data-ttu-id="aba70-239">TCP</span><span class="sxs-lookup"><span data-stu-id="aba70-239">TCP</span></span></p></td>
<td><p><span data-ttu-id="aba70-240">PSTN 게이트웨이에서 중재 서버로의 받는 SIP 요청에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="aba70-240">Used for incoming SIP requests from the PSTN gateway to the Mediation Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aba70-241">배치된 중재 서버를 실행하는 프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="aba70-241">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="aba70-242">Lync Server 중재 서비스</span><span class="sxs-lookup"><span data-stu-id="aba70-242">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="aba70-243">5081</span><span class="sxs-lookup"><span data-stu-id="aba70-243">5081</span></span></p></td>
<td><p><span data-ttu-id="aba70-244">TCP</span><span class="sxs-lookup"><span data-stu-id="aba70-244">TCP</span></span></p></td>
<td><p><span data-ttu-id="aba70-245">중재 서버에서 PSTN 게이트웨이로의 보내는 SIP 요청에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="aba70-245">Used for outgoing SIP requests from the Mediation Server to the PSTN gateway.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aba70-246">배치된 중재 서버를 실행하는 프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="aba70-246">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="aba70-247">Lync Server 중재 서비스</span><span class="sxs-lookup"><span data-stu-id="aba70-247">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="aba70-248">5082</span><span class="sxs-lookup"><span data-stu-id="aba70-248">5082</span></span></p></td>
<td><p><span data-ttu-id="aba70-249">TCP(TLS)</span><span class="sxs-lookup"><span data-stu-id="aba70-249">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="aba70-250">중재 서버에서 PSTN 게이트웨이로의 보내는 SIP 요청에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="aba70-250">Used for outgoing SIP requests from the Mediation Server to the PSTN gateway.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aba70-251">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="aba70-251">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="aba70-252">Lync Server 응용 프로그램 공유 서비스</span><span class="sxs-lookup"><span data-stu-id="aba70-252">Lync Server Application Sharing service</span></span></p></td>
<td><p><span data-ttu-id="aba70-253">5065</span><span class="sxs-lookup"><span data-stu-id="aba70-253">5065</span></span></p></td>
<td><p><span data-ttu-id="aba70-254">TCP</span><span class="sxs-lookup"><span data-stu-id="aba70-254">TCP</span></span></p></td>
<td><p><span data-ttu-id="aba70-255">응용 프로그램 공유의 받는 SIP 수신 대기 요청에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="aba70-255">Used for incoming SIP listening requests for application sharing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aba70-256">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="aba70-256">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="aba70-257">Lync Server 응용 프로그램 공유 서비스</span><span class="sxs-lookup"><span data-stu-id="aba70-257">Lync Server Application Sharing service</span></span></p></td>
<td><p><span data-ttu-id="aba70-258">49152-65535</span><span class="sxs-lookup"><span data-stu-id="aba70-258">49152-65535</span></span></p></td>
<td><p><span data-ttu-id="aba70-259">TCP</span><span class="sxs-lookup"><span data-stu-id="aba70-259">TCP</span></span></p></td>
<td><p><span data-ttu-id="aba70-260">응용 프로그램 공유에 사용되는 미디어 포트 범위입니다.</span><span class="sxs-lookup"><span data-stu-id="aba70-260">Media port range used for application sharing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aba70-261">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="aba70-261">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="aba70-262">Lync Server 회의 알림 서비스</span><span class="sxs-lookup"><span data-stu-id="aba70-262">Lync Server Conferencing Announcement service</span></span></p></td>
<td><p><span data-ttu-id="aba70-263">5073</span><span class="sxs-lookup"><span data-stu-id="aba70-263">5073</span></span></p></td>
<td><p><span data-ttu-id="aba70-264">TCP</span><span class="sxs-lookup"><span data-stu-id="aba70-264">TCP</span></span></p></td>
<td><p><span data-ttu-id="aba70-265">Lync Server 회의 알림 서비스에 대 한 들어오는 SIP 요청에 사용 됩니다 (전화 접속 회의의 경우).</span><span class="sxs-lookup"><span data-stu-id="aba70-265">Used for incoming SIP requests for the Lync Server Conferencing Announcement service (that is, for dial-in conferencing).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aba70-266">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="aba70-266">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="aba70-267">Lync Server 통화 대기 서비스</span><span class="sxs-lookup"><span data-stu-id="aba70-267">Lync Server Call Park service</span></span></p></td>
<td><p><span data-ttu-id="aba70-268">5075</span><span class="sxs-lookup"><span data-stu-id="aba70-268">5075</span></span></p></td>
<td><p><span data-ttu-id="aba70-269">TCP</span><span class="sxs-lookup"><span data-stu-id="aba70-269">TCP</span></span></p></td>
<td><p><span data-ttu-id="aba70-270">통화 대기 응용 프로그램의 받는 SIP 요청에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="aba70-270">Used for incoming SIP requests for the Call Park application.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aba70-271">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="aba70-271">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="aba70-272">Lync Server Audio 테스트 서비스</span><span class="sxs-lookup"><span data-stu-id="aba70-272">Lync Server Audio Test service</span></span></p></td>
<td><p><span data-ttu-id="aba70-273">5076</span><span class="sxs-lookup"><span data-stu-id="aba70-273">5076</span></span></p></td>
<td><p><span data-ttu-id="aba70-274">TCP</span><span class="sxs-lookup"><span data-stu-id="aba70-274">TCP</span></span></p></td>
<td><p><span data-ttu-id="aba70-275">오디오 테스트 서비스의 받는 SIP 요청에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="aba70-275">Used for incoming SIP requests for the Audio Test service.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aba70-276">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="aba70-276">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="aba70-277">해당 없음</span><span class="sxs-lookup"><span data-stu-id="aba70-277">Not applicable</span></span></p></td>
<td><p><span data-ttu-id="aba70-278">5066</span><span class="sxs-lookup"><span data-stu-id="aba70-278">5066</span></span></p></td>
<td><p><span data-ttu-id="aba70-279">TCP</span><span class="sxs-lookup"><span data-stu-id="aba70-279">TCP</span></span></p></td>
<td><p><span data-ttu-id="aba70-280">아웃바운드 E9-1-1(Enhanced 9-1-1) 게이트웨이에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="aba70-280">Used for outbound Enhanced 9-1-1 (E9-1-1) gateway.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aba70-281">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="aba70-281">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="aba70-282">Lync Server 응답 그룹 서비스</span><span class="sxs-lookup"><span data-stu-id="aba70-282">Lync Server Response Group service</span></span></p></td>
<td><p><span data-ttu-id="aba70-283">5071</span><span class="sxs-lookup"><span data-stu-id="aba70-283">5071</span></span></p></td>
<td><p><span data-ttu-id="aba70-284">TCP</span><span class="sxs-lookup"><span data-stu-id="aba70-284">TCP</span></span></p></td>
<td><p><span data-ttu-id="aba70-285">응답 그룹 응용 프로그램의 받는 SIP 요청에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="aba70-285">Used for incoming SIP requests for the Response Group application.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aba70-286">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="aba70-286">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="aba70-287">Lync Server 응답 그룹 서비스</span><span class="sxs-lookup"><span data-stu-id="aba70-287">Lync Server Response Group service</span></span></p></td>
<td><p><span data-ttu-id="aba70-288">8404</span><span class="sxs-lookup"><span data-stu-id="aba70-288">8404</span></span></p></td>
<td><p><span data-ttu-id="aba70-289">TCP(MTLS)</span><span class="sxs-lookup"><span data-stu-id="aba70-289">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="aba70-290">응답 그룹 응용 프로그램의 받는 SIP 요청에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="aba70-290">Used for incoming SIP requests for the Response Group application.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aba70-291">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="aba70-291">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="aba70-292">Lync Server 대역폭 정책 서비스</span><span class="sxs-lookup"><span data-stu-id="aba70-292">Lync Server Bandwidth Policy Service</span></span></p></td>
<td><p><span data-ttu-id="aba70-293">5080</span><span class="sxs-lookup"><span data-stu-id="aba70-293">5080</span></span></p></td>
<td><p><span data-ttu-id="aba70-294">TCP</span><span class="sxs-lookup"><span data-stu-id="aba70-294">TCP</span></span></p></td>
<td><p><span data-ttu-id="aba70-295">A/V 에지 TURN 트래픽에 대한 대역폭 정책 서비스의 통화 허용 제어에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="aba70-295">Used for call admission control by the Bandwidth Policy service for A/V Edge TURN traffic.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aba70-296">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="aba70-296">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="aba70-297">Lync Server 대역폭 정책 서비스</span><span class="sxs-lookup"><span data-stu-id="aba70-297">Lync Server Bandwidth Policy Service</span></span></p></td>
<td><p><span data-ttu-id="aba70-298">448</span><span class="sxs-lookup"><span data-stu-id="aba70-298">448</span></span></p></td>
<td><p><span data-ttu-id="aba70-299">TCP</span><span class="sxs-lookup"><span data-stu-id="aba70-299">TCP</span></span></p></td>
<td><p><span data-ttu-id="aba70-300">Lync Server 대역폭 정책 서비스의 통화 허용 제어에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="aba70-300">Used for call admission control by the Lync Server Bandwidth Policy Service.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aba70-301">중앙 관리 저장소가 상주 하는 프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="aba70-301">Front End Servers where the Central Management store resides</span></span></p></td>
<td><p><span data-ttu-id="aba70-302">Lync Server Master Replicator 에이전트 서비스</span><span class="sxs-lookup"><span data-stu-id="aba70-302">Lync Server Master Replicator Agent service</span></span></p></td>
<td><p><span data-ttu-id="aba70-303">445</span><span class="sxs-lookup"><span data-stu-id="aba70-303">445</span></span></p></td>
<td><p><span data-ttu-id="aba70-304">TCP</span><span class="sxs-lookup"><span data-stu-id="aba70-304">TCP</span></span></p></td>
<td><p><span data-ttu-id="aba70-305">중앙 관리 저장소의 구성 데이터를 Lync Server를 실행 하는 서버로 밀어 넣는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="aba70-305">Used to push configuration data from the Central Management store to servers running Lync Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aba70-306">모든 서버</span><span class="sxs-lookup"><span data-stu-id="aba70-306">All Servers</span></span></p></td>
<td><p><span data-ttu-id="aba70-307">SQL Browser</span><span class="sxs-lookup"><span data-stu-id="aba70-307">SQL Browser</span></span></p></td>
<td><p><span data-ttu-id="aba70-308">1434</span><span class="sxs-lookup"><span data-stu-id="aba70-308">1434</span></span></p></td>
<td><p><span data-ttu-id="aba70-309">P</span><span class="sxs-lookup"><span data-stu-id="aba70-309">UDP</span></span></p></td>
<td><p><span data-ttu-id="aba70-310">로컬 SQL Server 인스턴스에 중앙 관리 저장소 데이터의 로컬 복제 복사본에 대 한 SQL 브라우저</span><span class="sxs-lookup"><span data-stu-id="aba70-310">SQL Browser for local replicated copy of Central Management store data in local SQL Server instance</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aba70-311">모든 내부 서버</span><span class="sxs-lookup"><span data-stu-id="aba70-311">All internal servers</span></span></p></td>
<td><p><span data-ttu-id="aba70-312">다양 한</span><span class="sxs-lookup"><span data-stu-id="aba70-312">Various</span></span></p></td>
<td><p><span data-ttu-id="aba70-313">49152-57500</span><span class="sxs-lookup"><span data-stu-id="aba70-313">49152-57500</span></span></p></td>
<td><p><span data-ttu-id="aba70-314">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="aba70-314">TCP/UDP</span></span></p></td>
<td><p><span data-ttu-id="aba70-315">모든 내부 서버의 오디오 회의에 사용되는 미디어 포트 범위입니다.</span><span class="sxs-lookup"><span data-stu-id="aba70-315">Media port range used for audio conferencing on all internal servers.</span></span> <span data-ttu-id="aba70-316">오디오를 종료 하는 모든 서버에서 사용: 프런트 엔드 서버 (Lync Server 회의 수행자 서비스, Lync Server 회의 알림 서비스 및 Lync Server 오디오/비디오 회의 서비스) 및 중재 서버</span><span class="sxs-lookup"><span data-stu-id="aba70-316">Used by all servers that terminate audio: Front End Servers (for Lync Server Conferencing Attendant service, Lync Server Conferencing Announcement service, and Lync Server Audio/Video Conferencing service), and Mediation Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aba70-317">Office Web Apps 서버</span><span class="sxs-lookup"><span data-stu-id="aba70-317">Office Web Apps Servers</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="aba70-318">443</span><span class="sxs-lookup"><span data-stu-id="aba70-318">443</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="aba70-319">Lync Server 2013에서 Office Web Apps 서버에 연결 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="aba70-319">Used by Lync Server 2013 to connect to Office Web Apps Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aba70-320">디렉터</span><span class="sxs-lookup"><span data-stu-id="aba70-320">Directors</span></span></p></td>
<td><p><span data-ttu-id="aba70-321">Lync Server 프런트 엔드 서비스</span><span class="sxs-lookup"><span data-stu-id="aba70-321">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="aba70-322">5060</span><span class="sxs-lookup"><span data-stu-id="aba70-322">5060</span></span></p></td>
<td><p><span data-ttu-id="aba70-323">TCP</span><span class="sxs-lookup"><span data-stu-id="aba70-323">TCP</span></span></p></td>
<td><p><span data-ttu-id="aba70-324">필요에 따라 원격 통화 제어 서버와 같은 트러스트된 서비스에 대한 고정 경로에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="aba70-324">Optionally used for static routes to trusted services, such as remote call control servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aba70-325">디렉터</span><span class="sxs-lookup"><span data-stu-id="aba70-325">Directors</span></span></p></td>
<td><p><span data-ttu-id="aba70-326">Lync Server 프런트 엔드 서비스</span><span class="sxs-lookup"><span data-stu-id="aba70-326">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="aba70-327">444</span><span class="sxs-lookup"><span data-stu-id="aba70-327">444</span></span></p></td>
<td><p><span data-ttu-id="aba70-328">H</span><span class="sxs-lookup"><span data-stu-id="aba70-328">HTTPS</span></span></p>
<p><span data-ttu-id="aba70-329">TCP</span><span class="sxs-lookup"><span data-stu-id="aba70-329">TCP</span></span></p></td>
<td><p><span data-ttu-id="aba70-330">프런트 엔드 및 디렉터 간의 서버 간 통신.</span><span class="sxs-lookup"><span data-stu-id="aba70-330">Inter-server communication between Front End and Director.</span></span> <span data-ttu-id="aba70-331">또한 클라이언트 인증서가 프런트 엔드 서버로 게시 되거나 클라이언트 인증서가 이미 게시 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="aba70-331">Additionally, client certificate publish (to Front End Servers) or validate if the client certificate has already been published.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aba70-332">디렉터</span><span class="sxs-lookup"><span data-stu-id="aba70-332">Directors</span></span></p></td>
<td><p><span data-ttu-id="aba70-333">Lync Server 웹 호환성 서비스</span><span class="sxs-lookup"><span data-stu-id="aba70-333">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="aba70-334">80</span><span class="sxs-lookup"><span data-stu-id="aba70-334">80</span></span></p></td>
<td><p><span data-ttu-id="aba70-335">TCP</span><span class="sxs-lookup"><span data-stu-id="aba70-335">TCP</span></span></p></td>
<td><p><span data-ttu-id="aba70-p105">디렉터에서 웹 팜 FQDN(IIS 웹 구성 요소에서 사용하는 URL)으로의 초기 통신에 사용됩니다. 정상 작동의 경우 포트 443 및 TCP 프로토콜 유형을 사용하여 HTTPS 트래픽으로 전환됩니다.</span><span class="sxs-lookup"><span data-stu-id="aba70-p105">Used for initial communication from Directors to the web farm FQDNs (the URLs used by IIS web components). In normal operation, will switch to HTTPS traffic, using port 443 and protocol type TCP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aba70-338">디렉터</span><span class="sxs-lookup"><span data-stu-id="aba70-338">Directors</span></span></p></td>
<td><p><span data-ttu-id="aba70-339">Lync Server 웹 호환성 서비스</span><span class="sxs-lookup"><span data-stu-id="aba70-339">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="aba70-340">443</span><span class="sxs-lookup"><span data-stu-id="aba70-340">443</span></span></p></td>
<td><p><span data-ttu-id="aba70-341">H</span><span class="sxs-lookup"><span data-stu-id="aba70-341">HTTPS</span></span></p></td>
<td><p><span data-ttu-id="aba70-342">디렉터에서 웹 팜 FQDN(IIS 웹 구성 요소에서 사용하는 URL)으로의 통신에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="aba70-342">Used for communication from Directors to the web farm FQDNs (the URLs used by IIS web components).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aba70-343">디렉터</span><span class="sxs-lookup"><span data-stu-id="aba70-343">Directors</span></span></p></td>
<td><p><span data-ttu-id="aba70-344">Lync Server 프런트 엔드 서비스</span><span class="sxs-lookup"><span data-stu-id="aba70-344">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="aba70-345">5061</span><span class="sxs-lookup"><span data-stu-id="aba70-345">5061</span></span></p></td>
<td><p><span data-ttu-id="aba70-346">TCP</span><span class="sxs-lookup"><span data-stu-id="aba70-346">TCP</span></span></p></td>
<td><p><span data-ttu-id="aba70-347">서버 간 내부 통신과 클라이언트 연결에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="aba70-347">Used for internal communications between servers and for client connections.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aba70-348">중재 서버</span><span class="sxs-lookup"><span data-stu-id="aba70-348">Mediation Servers</span></span></p></td>
<td><p><span data-ttu-id="aba70-349">Lync Server 중재 서비스</span><span class="sxs-lookup"><span data-stu-id="aba70-349">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="aba70-350">5070</span><span class="sxs-lookup"><span data-stu-id="aba70-350">5070</span></span></p></td>
<td><p><span data-ttu-id="aba70-351">TCP</span><span class="sxs-lookup"><span data-stu-id="aba70-351">TCP</span></span></p></td>
<td><p><span data-ttu-id="aba70-352">중재 서버가 프런트 엔드 서버에서 받는 요청에 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="aba70-352">Used by the Mediation Server for incoming requests from the Front End Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aba70-353">중재 서버</span><span class="sxs-lookup"><span data-stu-id="aba70-353">Mediation Servers</span></span></p></td>
<td><p><span data-ttu-id="aba70-354">Lync Server 중재 서비스</span><span class="sxs-lookup"><span data-stu-id="aba70-354">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="aba70-355">5067</span><span class="sxs-lookup"><span data-stu-id="aba70-355">5067</span></span></p></td>
<td><p><span data-ttu-id="aba70-356">TCP(TLS)</span><span class="sxs-lookup"><span data-stu-id="aba70-356">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="aba70-357">PSTN 게이트웨이에서 받는 SIP 요청에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="aba70-357">Used for incoming SIP requests from the PSTN gateway.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aba70-358">중재 서버</span><span class="sxs-lookup"><span data-stu-id="aba70-358">Mediation Servers</span></span></p></td>
<td><p><span data-ttu-id="aba70-359">Lync Server 중재 서비스</span><span class="sxs-lookup"><span data-stu-id="aba70-359">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="aba70-360">5068</span><span class="sxs-lookup"><span data-stu-id="aba70-360">5068</span></span></p></td>
<td><p><span data-ttu-id="aba70-361">TCP</span><span class="sxs-lookup"><span data-stu-id="aba70-361">TCP</span></span></p></td>
<td><p><span data-ttu-id="aba70-362">PSTN 게이트웨이에서 받는 SIP 요청에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="aba70-362">Used for incoming SIP requests from the PSTN gateway.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aba70-363">중재 서버</span><span class="sxs-lookup"><span data-stu-id="aba70-363">Mediation Servers</span></span></p></td>
<td><p><span data-ttu-id="aba70-364">Lync Server 중재 서비스</span><span class="sxs-lookup"><span data-stu-id="aba70-364">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="aba70-365">5070</span><span class="sxs-lookup"><span data-stu-id="aba70-365">5070</span></span></p></td>
<td><p><span data-ttu-id="aba70-366">TCP(MTLS)</span><span class="sxs-lookup"><span data-stu-id="aba70-366">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="aba70-367">프런트 엔드 서버의 SIP 요청에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="aba70-367">Used for SIP requests from the Front End Servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aba70-368">영구 채팅 프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="aba70-368">Persistent Chat Front End Server</span></span></p></td>
<td><p><span data-ttu-id="aba70-369">영구 채팅 SIP</span><span class="sxs-lookup"><span data-stu-id="aba70-369">Persistent Chat SIP</span></span></p></td>
<td><p><span data-ttu-id="aba70-370">5041</span><span class="sxs-lookup"><span data-stu-id="aba70-370">5041</span></span></p></td>
<td><p><span data-ttu-id="aba70-371">TCP(MTLS)</span><span class="sxs-lookup"><span data-stu-id="aba70-371">TCP (MTLS)</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aba70-372">영구 채팅 프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="aba70-372">Persistent Chat Front End Server</span></span></p></td>
<td><p><span data-ttu-id="aba70-373">영구 채팅 WCF (Windows Communication Foundation)</span><span class="sxs-lookup"><span data-stu-id="aba70-373">Persistent Chat Windows Communication Foundation (WCF)</span></span></p></td>
<td><p><span data-ttu-id="aba70-374">881</span><span class="sxs-lookup"><span data-stu-id="aba70-374">881</span></span></p></td>
<td><p><span data-ttu-id="aba70-375">TCP (TLS) 및 TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="aba70-375">TCP (TLS) and TCP (MTLS)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aba70-376">영구 채팅 프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="aba70-376">Persistent Chat Front End Server</span></span></p></td>
<td><p><span data-ttu-id="aba70-377">영구 채팅 파일 전송 서비스</span><span class="sxs-lookup"><span data-stu-id="aba70-377">Persistent Chat File Transfer Service</span></span></p></td>
<td><p><span data-ttu-id="aba70-378">443</span><span class="sxs-lookup"><span data-stu-id="aba70-378">443</span></span></p></td>
<td><p><span data-ttu-id="aba70-379">TCP(TLS)</span><span class="sxs-lookup"><span data-stu-id="aba70-379">TCP (TLS)</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="aba70-380">일부 원격 통화 제어 시나리오의 경우 프런트 엔드 서버 또는 디렉터 및 PBX 간 TCP 연결이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="aba70-380">Some remote call control scenarios require a TCP connection between the Front End Server or Director and the PBX.</span></span> <span data-ttu-id="aba70-381">Lync Server에서는 더 이상 TCP 포트 5060을 사용 하지 않지만 원격 통화 제어 배포 중에는 RCC Line Server FQDN을 프런트 엔드 서버 또는 디렉터가 PBX 시스템에 연결 하는 데 사용할 TCP 포트와 연결 하는 신뢰할 수 있는 서버 구성을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="aba70-381">Although Lync Server no longer uses TCP port 5060, during remote call control deployment you create a trusted server configuration, which associates the RCC Line Server FQDN with the TCP port that the Front End Server or Director will use to connect to the PBX system.</span></span> <span data-ttu-id="aba70-382">자세한 내용은 Lync Server 관리 셸 설명서에서 <STRONG>CsTrustedApplicationComputer</STRONG> cmdlet을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="aba70-382">For details, see the <STRONG>CsTrustedApplicationComputer</STRONG> cmdlet in the Lync Server Management Shell documentation.</span></span>



</div>

<span data-ttu-id="aba70-383">다음 표에서는 하드웨어 부하 분산만 사용하는 풀(DNS 부하 분산 사용 안 함)의 경우 하드웨어 부하 분산 장치를 열어야 하는 포트를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="aba70-383">For your pools that use only hardware load balancing (not DNS load balancing), the following table shows the ports that need to open the hardware load balancers.</span></span>

### <a name="hardware-load-balancer-ports-if-using-only-hardware-load-balancing"></a><span data-ttu-id="aba70-384">하드웨어 부하 분산만 사용하는 경우 하드웨어 부하 분산 장치 포트</span><span class="sxs-lookup"><span data-stu-id="aba70-384">Hardware Load Balancer Ports if Using Only Hardware Load Balancing</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="aba70-385">부하 분산 장치</span><span class="sxs-lookup"><span data-stu-id="aba70-385">Load Balancer</span></span></th>
<th><span data-ttu-id="aba70-386">포트</span><span class="sxs-lookup"><span data-stu-id="aba70-386">Port</span></span></th>
<th><span data-ttu-id="aba70-387">프로토콜로</span><span class="sxs-lookup"><span data-stu-id="aba70-387">Protocol</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="aba70-388">프런트 엔드 서버 부하 분산 장치</span><span class="sxs-lookup"><span data-stu-id="aba70-388">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="aba70-389">5061</span><span class="sxs-lookup"><span data-stu-id="aba70-389">5061</span></span></p></td>
<td><p><span data-ttu-id="aba70-390">TCP(TLS)</span><span class="sxs-lookup"><span data-stu-id="aba70-390">TCP (TLS)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aba70-391">프런트 엔드 서버 부하 분산 장치</span><span class="sxs-lookup"><span data-stu-id="aba70-391">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="aba70-392">444</span><span class="sxs-lookup"><span data-stu-id="aba70-392">444</span></span></p></td>
<td><p><span data-ttu-id="aba70-393">H</span><span class="sxs-lookup"><span data-stu-id="aba70-393">HTTPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aba70-394">프런트 엔드 서버 부하 분산 장치</span><span class="sxs-lookup"><span data-stu-id="aba70-394">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="aba70-395">135</span><span class="sxs-lookup"><span data-stu-id="aba70-395">135</span></span></p></td>
<td><p><span data-ttu-id="aba70-396">DCOM 및 RPC(원격 프로시저 호출)</span><span class="sxs-lookup"><span data-stu-id="aba70-396">DCOM and remote procedure call (RPC)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aba70-397">프런트 엔드 서버 부하 분산 장치</span><span class="sxs-lookup"><span data-stu-id="aba70-397">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="aba70-398">80</span><span class="sxs-lookup"><span data-stu-id="aba70-398">80</span></span></p></td>
<td><p><span data-ttu-id="aba70-399">HTTP</span><span class="sxs-lookup"><span data-stu-id="aba70-399">HTTP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aba70-400">프런트 엔드 서버 부하 분산 장치</span><span class="sxs-lookup"><span data-stu-id="aba70-400">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="aba70-401">8080</span><span class="sxs-lookup"><span data-stu-id="aba70-401">8080</span></span></p></td>
<td><p><span data-ttu-id="aba70-402">TCP - 프런트 엔드 서버에서 루트 인증서의 클라이언트 및 장치 검색 - 클라이언트 및 장치는 NTLM으로 인증됩니다.</span><span class="sxs-lookup"><span data-stu-id="aba70-402">TCP - Client and device retrieval of root certificate from Front End Server – clients and devices authenticated by NTLM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aba70-403">프런트 엔드 서버 부하 분산 장치</span><span class="sxs-lookup"><span data-stu-id="aba70-403">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="aba70-404">443</span><span class="sxs-lookup"><span data-stu-id="aba70-404">443</span></span></p></td>
<td><p><span data-ttu-id="aba70-405">H</span><span class="sxs-lookup"><span data-stu-id="aba70-405">HTTPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aba70-406">프런트 엔드 서버 부하 분산 장치</span><span class="sxs-lookup"><span data-stu-id="aba70-406">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="aba70-407">4443</span><span class="sxs-lookup"><span data-stu-id="aba70-407">4443</span></span></p></td>
<td><p><span data-ttu-id="aba70-408">HTTPS(역방향 프록시)</span><span class="sxs-lookup"><span data-stu-id="aba70-408">HTTPS (from reverse proxy)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aba70-409">프런트 엔드 서버 부하 분산 장치</span><span class="sxs-lookup"><span data-stu-id="aba70-409">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="aba70-410">5072</span><span class="sxs-lookup"><span data-stu-id="aba70-410">5072</span></span></p></td>
<td><p><span data-ttu-id="aba70-411">TCP</span><span class="sxs-lookup"><span data-stu-id="aba70-411">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aba70-412">프런트 엔드 서버 부하 분산 장치</span><span class="sxs-lookup"><span data-stu-id="aba70-412">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="aba70-413">5073</span><span class="sxs-lookup"><span data-stu-id="aba70-413">5073</span></span></p></td>
<td><p><span data-ttu-id="aba70-414">TCP</span><span class="sxs-lookup"><span data-stu-id="aba70-414">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aba70-415">프런트 엔드 서버 부하 분산 장치</span><span class="sxs-lookup"><span data-stu-id="aba70-415">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="aba70-416">5075</span><span class="sxs-lookup"><span data-stu-id="aba70-416">5075</span></span></p></td>
<td><p><span data-ttu-id="aba70-417">TCP</span><span class="sxs-lookup"><span data-stu-id="aba70-417">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aba70-418">프런트 엔드 서버 부하 분산 장치</span><span class="sxs-lookup"><span data-stu-id="aba70-418">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="aba70-419">5076</span><span class="sxs-lookup"><span data-stu-id="aba70-419">5076</span></span></p></td>
<td><p><span data-ttu-id="aba70-420">TCP</span><span class="sxs-lookup"><span data-stu-id="aba70-420">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aba70-421">프런트 엔드 서버 부하 분산 장치</span><span class="sxs-lookup"><span data-stu-id="aba70-421">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="aba70-422">5071</span><span class="sxs-lookup"><span data-stu-id="aba70-422">5071</span></span></p></td>
<td><p><span data-ttu-id="aba70-423">TCP</span><span class="sxs-lookup"><span data-stu-id="aba70-423">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aba70-424">프런트 엔드 서버 부하 분산 장치</span><span class="sxs-lookup"><span data-stu-id="aba70-424">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="aba70-425">5080</span><span class="sxs-lookup"><span data-stu-id="aba70-425">5080</span></span></p></td>
<td><p><span data-ttu-id="aba70-426">TCP</span><span class="sxs-lookup"><span data-stu-id="aba70-426">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aba70-427">프런트 엔드 서버 부하 분산 장치</span><span class="sxs-lookup"><span data-stu-id="aba70-427">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="aba70-428">448</span><span class="sxs-lookup"><span data-stu-id="aba70-428">448</span></span></p></td>
<td><p><span data-ttu-id="aba70-429">TCP</span><span class="sxs-lookup"><span data-stu-id="aba70-429">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aba70-430">중재 서버 부하 분산 장치</span><span class="sxs-lookup"><span data-stu-id="aba70-430">Mediation Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="aba70-431">5070</span><span class="sxs-lookup"><span data-stu-id="aba70-431">5070</span></span></p></td>
<td><p><span data-ttu-id="aba70-432">TCP</span><span class="sxs-lookup"><span data-stu-id="aba70-432">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aba70-433">프런트 엔드 서버 부하 분산 장치 (풀에서 중재 서버도 실행 되는 경우)</span><span class="sxs-lookup"><span data-stu-id="aba70-433">Front End Server load balancer (if the pool also runs Mediation Server)</span></span></p></td>
<td><p><span data-ttu-id="aba70-434">5070</span><span class="sxs-lookup"><span data-stu-id="aba70-434">5070</span></span></p></td>
<td><p><span data-ttu-id="aba70-435">TCP</span><span class="sxs-lookup"><span data-stu-id="aba70-435">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aba70-436">디렉터 부하 분산 장치</span><span class="sxs-lookup"><span data-stu-id="aba70-436">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="aba70-437">443</span><span class="sxs-lookup"><span data-stu-id="aba70-437">443</span></span></p></td>
<td><p><span data-ttu-id="aba70-438">H</span><span class="sxs-lookup"><span data-stu-id="aba70-438">HTTPS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aba70-439">디렉터 부하 분산 장치</span><span class="sxs-lookup"><span data-stu-id="aba70-439">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="aba70-440">444</span><span class="sxs-lookup"><span data-stu-id="aba70-440">444</span></span></p></td>
<td><p><span data-ttu-id="aba70-441">H</span><span class="sxs-lookup"><span data-stu-id="aba70-441">HTTPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aba70-442">디렉터 부하 분산 장치</span><span class="sxs-lookup"><span data-stu-id="aba70-442">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="aba70-443">5061</span><span class="sxs-lookup"><span data-stu-id="aba70-443">5061</span></span></p></td>
<td><p><span data-ttu-id="aba70-444">TCP</span><span class="sxs-lookup"><span data-stu-id="aba70-444">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aba70-445">디렉터 부하 분산 장치</span><span class="sxs-lookup"><span data-stu-id="aba70-445">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="aba70-446">4443</span><span class="sxs-lookup"><span data-stu-id="aba70-446">4443</span></span></p></td>
<td><p><span data-ttu-id="aba70-447">HTTPS(역방향 프록시)</span><span class="sxs-lookup"><span data-stu-id="aba70-447">HTTPS (from reverse proxy)</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="aba70-p107">DNS 부하 분산을 사용하는 프런트 엔드 풀 및 디렉터 풀에는 하드웨어 부하 분산 장치도 배포되어 있어야 합니다. 다음 표에서는 이러한 하드웨어 부하 분산 장치에서 열어야 하는 포트를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="aba70-p107">Your Front End pools and Director pools that use DNS load balancing also must have a hardware load balancer deployed. The following table shows the ports that need to be open on these hardware load balancers.</span></span>

### <a name="hardware-load-balancer-ports-if-using-dns-load-balancing"></a><span data-ttu-id="aba70-450">DNS 부하 분산을 사용하는 경우 하드웨어 부하 분산 장치 포트</span><span class="sxs-lookup"><span data-stu-id="aba70-450">Hardware Load Balancer Ports if Using DNS Load Balancing</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="aba70-451">부하 분산 장치</span><span class="sxs-lookup"><span data-stu-id="aba70-451">Load Balancer</span></span></th>
<th><span data-ttu-id="aba70-452">포트</span><span class="sxs-lookup"><span data-stu-id="aba70-452">Port</span></span></th>
<th><span data-ttu-id="aba70-453">프로토콜로</span><span class="sxs-lookup"><span data-stu-id="aba70-453">Protocol</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="aba70-454">프런트 엔드 서버 부하 분산 장치</span><span class="sxs-lookup"><span data-stu-id="aba70-454">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="aba70-455">80</span><span class="sxs-lookup"><span data-stu-id="aba70-455">80</span></span></p></td>
<td><p><span data-ttu-id="aba70-456">HTTP</span><span class="sxs-lookup"><span data-stu-id="aba70-456">HTTP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aba70-457">프런트 엔드 서버 부하 분산 장치</span><span class="sxs-lookup"><span data-stu-id="aba70-457">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="aba70-458">443</span><span class="sxs-lookup"><span data-stu-id="aba70-458">443</span></span></p></td>
<td><p><span data-ttu-id="aba70-459">H</span><span class="sxs-lookup"><span data-stu-id="aba70-459">HTTPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aba70-460">프런트 엔드 서버 부하 분산 장치</span><span class="sxs-lookup"><span data-stu-id="aba70-460">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="aba70-461">8080</span><span class="sxs-lookup"><span data-stu-id="aba70-461">8080</span></span></p></td>
<td><p><span data-ttu-id="aba70-462">TCP - 프런트 엔드 서버에서 루트 인증서의 클라이언트 및 장치 검색 - 클라이언트 및 장치는 NTLM으로 인증됩니다.</span><span class="sxs-lookup"><span data-stu-id="aba70-462">TCP - Client and device retrieval of root certificate from Front End Server – clients and devices authenticated by NTLM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aba70-463">프런트 엔드 서버 부하 분산 장치</span><span class="sxs-lookup"><span data-stu-id="aba70-463">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="aba70-464">4443</span><span class="sxs-lookup"><span data-stu-id="aba70-464">4443</span></span></p></td>
<td><p><span data-ttu-id="aba70-465">HTTPS(역방향 프록시)</span><span class="sxs-lookup"><span data-stu-id="aba70-465">HTTPS (from reverse proxy)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aba70-466">디렉터 부하 분산 장치</span><span class="sxs-lookup"><span data-stu-id="aba70-466">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="aba70-467">443</span><span class="sxs-lookup"><span data-stu-id="aba70-467">443</span></span></p></td>
<td><p><span data-ttu-id="aba70-468">H</span><span class="sxs-lookup"><span data-stu-id="aba70-468">HTTPS</span></span></p></td>
</tr>
<tr class="even">
<td> </td>
<td> </td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aba70-469">디렉터 부하 분산 장치</span><span class="sxs-lookup"><span data-stu-id="aba70-469">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="aba70-470">4443</span><span class="sxs-lookup"><span data-stu-id="aba70-470">4443</span></span></p></td>
<td><p><span data-ttu-id="aba70-471">HTTPS(역방향 프록시)</span><span class="sxs-lookup"><span data-stu-id="aba70-471">HTTPS (from reverse proxy)</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="required-client-ports"></a><span data-ttu-id="aba70-472">필요한 클라이언트 포트</span><span class="sxs-lookup"><span data-stu-id="aba70-472">Required Client Ports</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="aba70-473">구성 요소</span><span class="sxs-lookup"><span data-stu-id="aba70-473">Component</span></span></th>
<th><span data-ttu-id="aba70-474">포트</span><span class="sxs-lookup"><span data-stu-id="aba70-474">Port</span></span></th>
<th><span data-ttu-id="aba70-475">프로토콜로</span><span class="sxs-lookup"><span data-stu-id="aba70-475">Protocol</span></span></th>
<th><span data-ttu-id="aba70-476">Notes</span><span class="sxs-lookup"><span data-stu-id="aba70-476">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="aba70-477">클라이언트</span><span class="sxs-lookup"><span data-stu-id="aba70-477">Clients</span></span></p></td>
<td><p><span data-ttu-id="aba70-478">67/68</span><span class="sxs-lookup"><span data-stu-id="aba70-478">67/68</span></span></p></td>
<td><p><span data-ttu-id="aba70-479">서버의</span><span class="sxs-lookup"><span data-stu-id="aba70-479">DHCP</span></span></p></td>
<td><p><span data-ttu-id="aba70-480">Lync Server에서 등록자 FQDN을 찾는 데 사용 됩니다 (즉, DNS SRV에 오류가 발생 하 여 수동 설정이 구성 되지 않은 경우).</span><span class="sxs-lookup"><span data-stu-id="aba70-480">Used by Lync Server to find the Registrar FQDN (that is, if DNS SRV fails and manual settings are not configured).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aba70-481">클라이언트</span><span class="sxs-lookup"><span data-stu-id="aba70-481">Clients</span></span></p></td>
<td><p><span data-ttu-id="aba70-482">443</span><span class="sxs-lookup"><span data-stu-id="aba70-482">443</span></span></p></td>
<td><p><span data-ttu-id="aba70-483">TCP(TLS)</span><span class="sxs-lookup"><span data-stu-id="aba70-483">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="aba70-484">외부 사용자 액세스의 클라이언트-서버 SIP 트래픽에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="aba70-484">Used for client-to-server SIP traffic for external user access.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aba70-485">클라이언트</span><span class="sxs-lookup"><span data-stu-id="aba70-485">Clients</span></span></p></td>
<td><p><span data-ttu-id="aba70-486">443</span><span class="sxs-lookup"><span data-stu-id="aba70-486">443</span></span></p></td>
<td><p><span data-ttu-id="aba70-487">TCP(PSOM/TLS)</span><span class="sxs-lookup"><span data-stu-id="aba70-487">TCP (PSOM/TLS)</span></span></p></td>
<td><p><span data-ttu-id="aba70-488">웹 회의 세션에 대한 외부 사용자 액세스에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="aba70-488">Used for external user access to web conferencing sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aba70-489">클라이언트</span><span class="sxs-lookup"><span data-stu-id="aba70-489">Clients</span></span></p></td>
<td><p><span data-ttu-id="aba70-490">443</span><span class="sxs-lookup"><span data-stu-id="aba70-490">443</span></span></p></td>
<td><p><span data-ttu-id="aba70-491">TCP(STUN/MSTURN)</span><span class="sxs-lookup"><span data-stu-id="aba70-491">TCP (STUN/MSTURN)</span></span></p></td>
<td><p><span data-ttu-id="aba70-492">A/V 세션 및 미디어(TCP)에 대한 외부 사용자 액세스에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="aba70-492">Used for external user access to A/V sessions and media (TCP)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aba70-493">클라이언트</span><span class="sxs-lookup"><span data-stu-id="aba70-493">Clients</span></span></p></td>
<td><p><span data-ttu-id="aba70-494">3478</span><span class="sxs-lookup"><span data-stu-id="aba70-494">3478</span></span></p></td>
<td><p><span data-ttu-id="aba70-495">UDP(STUN/MSTURN)</span><span class="sxs-lookup"><span data-stu-id="aba70-495">UDP (STUN/MSTURN)</span></span></p></td>
<td><p><span data-ttu-id="aba70-496">A/V 세션 및 미디어에 대 한 외부 사용자 액세스 (UDP)에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="aba70-496">Used for external user access to A/V sessions and media (UDP)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aba70-497">클라이언트</span><span class="sxs-lookup"><span data-stu-id="aba70-497">Clients</span></span></p></td>
<td><p><span data-ttu-id="aba70-498">5061</span><span class="sxs-lookup"><span data-stu-id="aba70-498">5061</span></span></p></td>
<td><p><span data-ttu-id="aba70-499">TCP(MTLS)</span><span class="sxs-lookup"><span data-stu-id="aba70-499">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="aba70-500">외부 사용자 액세스의 클라이언트-서버 SIP 트래픽에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="aba70-500">Used for client-to-server SIP traffic for external user access.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aba70-501">클라이언트</span><span class="sxs-lookup"><span data-stu-id="aba70-501">Clients</span></span></p></td>
<td><p><span data-ttu-id="aba70-502">6891-6901</span><span class="sxs-lookup"><span data-stu-id="aba70-502">6891-6901</span></span></p></td>
<td><p><span data-ttu-id="aba70-503">TCP</span><span class="sxs-lookup"><span data-stu-id="aba70-503">TCP</span></span></p></td>
<td><p><span data-ttu-id="aba70-504">Lync 클라이언트와 이전 클라이언트 (Microsoft Office Communications Server 2007 R2, Microsoft Office Communications Server 2007 및 Live Communications Server 2005의 클라이언트) 간의 파일 전송에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="aba70-504">Used for file transfer between Lync clients and previous clients (clients of Microsoft Office Communications Server 2007 R2, Microsoft Office Communications Server 2007, and Live Communications Server 2005).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aba70-505">클라이언트</span><span class="sxs-lookup"><span data-stu-id="aba70-505">Clients</span></span></p></td>
<td><p><span data-ttu-id="aba70-506">1024-65535 \*</span><span class="sxs-lookup"><span data-stu-id="aba70-506">1024-65535 \*</span></span></p></td>
<td><p><span data-ttu-id="aba70-507">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="aba70-507">TCP/UDP</span></span></p></td>
<td><p><span data-ttu-id="aba70-508">오디오 포트 범위(최소 20개 포트 필요)</span><span class="sxs-lookup"><span data-stu-id="aba70-508">Audio port range (minimum of 20 ports required)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aba70-509">클라이언트</span><span class="sxs-lookup"><span data-stu-id="aba70-509">Clients</span></span></p></td>
<td><p><span data-ttu-id="aba70-510">1024-65535 \*</span><span class="sxs-lookup"><span data-stu-id="aba70-510">1024-65535 \*</span></span></p></td>
<td><p><span data-ttu-id="aba70-511">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="aba70-511">TCP/UDP</span></span></p></td>
<td><p><span data-ttu-id="aba70-512">비디오 포트 범위(최소 20개 포트 필요)</span><span class="sxs-lookup"><span data-stu-id="aba70-512">Video port range (minimum of 20 ports required).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aba70-513">클라이언트</span><span class="sxs-lookup"><span data-stu-id="aba70-513">Clients</span></span></p></td>
<td><p><span data-ttu-id="aba70-514">1024-65535 \*</span><span class="sxs-lookup"><span data-stu-id="aba70-514">1024-65535 \*</span></span></p></td>
<td><p><span data-ttu-id="aba70-515">TCP</span><span class="sxs-lookup"><span data-stu-id="aba70-515">TCP</span></span></p></td>
<td><p><span data-ttu-id="aba70-516">피어 투 피어 파일 전송(회의 파일 전송의 경우 클라이언트가 PSOM 사용).</span><span class="sxs-lookup"><span data-stu-id="aba70-516">Peer-to-peer file transfer (for conferencing file transfer, clients use PSOM).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aba70-517">클라이언트</span><span class="sxs-lookup"><span data-stu-id="aba70-517">Clients</span></span></p></td>
<td><p><span data-ttu-id="aba70-518">1024-65535 \*</span><span class="sxs-lookup"><span data-stu-id="aba70-518">1024-65535 \*</span></span></p></td>
<td><p><span data-ttu-id="aba70-519">TCP</span><span class="sxs-lookup"><span data-stu-id="aba70-519">TCP</span></span></p></td>
<td><p><span data-ttu-id="aba70-520">응용 프로그램 공유</span><span class="sxs-lookup"><span data-stu-id="aba70-520">Application sharing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aba70-521">Aastra 6721ip 공통 영역 전화</span><span class="sxs-lookup"><span data-stu-id="aba70-521">Aastra 6721ip common area phone</span></span></p>
<p><span data-ttu-id="aba70-522">Aastra 6725ip 일반 전화기</span><span class="sxs-lookup"><span data-stu-id="aba70-522">Aastra 6725ip desk phone</span></span></p>
<p><span data-ttu-id="aba70-523">HP 4110 IP 전화(공통 영역 전화)</span><span class="sxs-lookup"><span data-stu-id="aba70-523">HP 4110 IP Phone (common area phone)</span></span></p>
<p><span data-ttu-id="aba70-524">HP 4120 IP 전화(일반 전화기)</span><span class="sxs-lookup"><span data-stu-id="aba70-524">HP 4120 IP Phone (desk phone)</span></span></p>
<p><span data-ttu-id="aba70-525">Polycom CX500 IP 공통 영역 전화</span><span class="sxs-lookup"><span data-stu-id="aba70-525">Polycom CX500 IP common area phone</span></span></p>
<p><span data-ttu-id="aba70-526">Polycom CX600 IP 일반 전화기</span><span class="sxs-lookup"><span data-stu-id="aba70-526">Polycom CX600 IP desk phone</span></span></p>
<p><span data-ttu-id="aba70-527">Polycom CX700 IP 일반 전화기</span><span class="sxs-lookup"><span data-stu-id="aba70-527">Polycom CX700 IP desk phone</span></span></p>
<p><span data-ttu-id="aba70-528">Polycom CX3000 IP 회의 전화</span><span class="sxs-lookup"><span data-stu-id="aba70-528">Polycom CX3000 IP conference phone</span></span></p></td>
<td><p><span data-ttu-id="aba70-529">67/68</span><span class="sxs-lookup"><span data-stu-id="aba70-529">67/68</span></span></p></td>
<td><p><span data-ttu-id="aba70-530">서버의</span><span class="sxs-lookup"><span data-stu-id="aba70-530">DHCP</span></span></p></td>
<td><p><span data-ttu-id="aba70-531">나열 된 장치에서 Lync Server 인증서, 프로 비전 FQDN 및 등록자 FQDN을 찾는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="aba70-531">Used by the listed devices to find the Lync Server certificate, provisioning FQDN, and Registrar FQDN.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="aba70-532">**\*** 이러한 미디어 유형에 대 한 특정 포트를 구성 하려면 Get-csconferencingconfiguration cmdlet (ClientMediaPortRangeEnabled, ClientMediaPort 및 ClientMediaPortRange 매개 변수)을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="aba70-532">**\*** To configure specific ports for these media types, use the CsConferencingConfiguration cmdlet (ClientMediaPortRangeEnabled, ClientMediaPort, and ClientMediaPortRange parameters).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="aba70-533">Lync 클라이언트에 대 한 프로그램 설정에서는 클라이언트 컴퓨터에 필요한 운영 체제 방화벽 예외를 자동으로 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="aba70-533">The set programs for Lync clients automatically create the required operating-system firewall exceptions on the client computer.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="aba70-534">외부 사용자 액세스를 위해 사용되는 포트는 클라이언트가 조직의 방화벽을 통과해야 하는 모든 시나리오에 필요합니다(예: 외부 통신 또는 다른 조직에서 호스트되는 모임).</span><span class="sxs-lookup"><span data-stu-id="aba70-534">The ports that are used for external user access are required for any scenario in which the client must traverse the organization’s firewall (for example, any external communications or meetings hosted by other organizations).</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

