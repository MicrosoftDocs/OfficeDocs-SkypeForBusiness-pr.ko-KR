---
title: 'Lync Server 2013: 내부 서버용 포트 및 프로토콜'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Ports and protocols for internal servers
ms:assetid: c94063f1-e802-4a61-be90-022fc185335e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398833(v=OCS.15)
ms:contentKeyID: 48185402
ms.date: 04/06/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 026843216e433ebea120384209ed90f38be3437b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983858"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="ports-and-protocols-for-internal-servers-in-lync-server-2013"></a><span data-ttu-id="f683b-102">Lync Server 2013의 내부 서버에 대 한 포트 및 프로토콜</span><span class="sxs-lookup"><span data-stu-id="f683b-102">Ports and protocols for internal servers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f683b-103">_**마지막으로 수정한 주제:** 2016-04-06_</span><span class="sxs-lookup"><span data-stu-id="f683b-103">_**Topic Last Modified:** 2016-04-06_</span></span>

<span data-ttu-id="f683b-104">이 섹션에서는 서버, 부하 분산 장치 및 Lync Server 배포의 클라이언트에 사용 되는 포트와 프로토콜에 대해 간략하게 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="f683b-104">This section summarizes the ports and protocols used by servers, load balancers, and clients in a Lync Server deployment.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="f683b-105">1 ~ 1 통신에 참가 하는 Lync 및 Communicator 클라이언트는 종종 피어 투 피어 라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="f683b-105">Lync and Communicator clients when involved in a one to one communication, is often referred to as peer-to-peer.</span></span> <span data-ttu-id="f683b-106">기술적으로 두 클라이언트는 중앙의 IMMCU (지점 제어 단위)를 사용 하 여 일대일 대화로 통신 합니다.</span><span class="sxs-lookup"><span data-stu-id="f683b-106">Technically, the two clients are communicating in a one to one conversation, with the Instant Messaging multipoint control unit (IMMCU) in the middle.</span></span> <span data-ttu-id="f683b-107">IMMCU는 프런트 엔드 서버의 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="f683b-107">The IMMCU is a component of Front End Server.</span></span> <span data-ttu-id="f683b-108">필요한 통신 워크플로에 IMMCU를 배치 하면 프런트 엔드 서버에서 사용할 수 있는 통화 정보 기록 및 기타 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f683b-108">Placing the IMMCU in the required communication workflow allows call detail recording and other features that the Front End Server enables.</span></span> <span data-ttu-id="f683b-109">클라이언트의 동적 원본 포트에서 프런트 엔드 서버 포트 TLS/TCP/5061으로 통신 하는 것으로 간주 됩니다 (권장 전송 계층 보안을 사용 하는 경우).</span><span class="sxs-lookup"><span data-stu-id="f683b-109">Communication is from a dynamic source port on the client to the Front End Server port TLS/TCP/5061 (assuming the use of the recommended transport layer security).</span></span> <span data-ttu-id="f683b-110">Lync Server와 IMMCU가 활성 상태이 고 사용할 수 있는 경우에만 피어 투 피어 통신 및 여러 파티 IM을 디자인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f683b-110">By design, peer-to-peer communication (as well as multi-party IM) is possible only when Lync Server and the IMMCU is active and available.</span></span>



</div>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="f683b-111">포트 및 프로토콜 정보</span><span class="sxs-lookup"><span data-stu-id="f683b-111">Port and Protocol Details</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f683b-112">Lync server가 방화벽에서 필요한 포트를 여는 경우에는 서버에서 Lync Server 서비스를 시작 하기 전에 Windows 방화벽이 실행 중 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f683b-112">Windows Firewall must be running before you start the Lync Server services on a server, because that is when Lync Server opens the required ports in the firewall.</span></span>



</div>

<span data-ttu-id="f683b-113">Edge 구성 요소의 방화벽 구성에 대 한 자세한 내용은 [Lync Server 2013에 대 한 외부 A/V 방화벽 및 포트 요구 사항 결정](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f683b-113">For details about firewall configuration for edge components, see [Determine external A/V firewall and port requirements for Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md).</span></span>

<span data-ttu-id="f683b-114">다음 표에는 각 내부 서버 역할에 열려 있어야 하는 포트가 나열 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f683b-114">The following table lists the ports that need to be open on each internal server role.</span></span>

### <a name="required-server-ports-by-server-role"></a><span data-ttu-id="f683b-115">필요한 서버 포트 (서버 역할별)</span><span class="sxs-lookup"><span data-stu-id="f683b-115">Required Server Ports (by Server Role)</span></span>

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
<th><span data-ttu-id="f683b-116">서버 역할</span><span class="sxs-lookup"><span data-stu-id="f683b-116">Server role</span></span></th>
<th><span data-ttu-id="f683b-117">서비스 이름</span><span class="sxs-lookup"><span data-stu-id="f683b-117">Service name</span></span></th>
<th><span data-ttu-id="f683b-118">포트</span><span class="sxs-lookup"><span data-stu-id="f683b-118">Port</span></span></th>
<th><span data-ttu-id="f683b-119">프로토콜별</span><span class="sxs-lookup"><span data-stu-id="f683b-119">Protocol</span></span></th>
<th><span data-ttu-id="f683b-120">상속자</span><span class="sxs-lookup"><span data-stu-id="f683b-120">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f683b-121">모든 서버</span><span class="sxs-lookup"><span data-stu-id="f683b-121">All Servers</span></span></p></td>
<td><p><span data-ttu-id="f683b-122">SQL 브라우저</span><span class="sxs-lookup"><span data-stu-id="f683b-122">SQL Browser</span></span></p></td>
<td><p><span data-ttu-id="f683b-123">1434</span><span class="sxs-lookup"><span data-stu-id="f683b-123">1434</span></span></p></td>
<td><p><span data-ttu-id="f683b-124">UDP</span><span class="sxs-lookup"><span data-stu-id="f683b-124">UDP</span></span></p></td>
<td><p><span data-ttu-id="f683b-125">중앙 관리 저장소 데이터베이스의 복제 된 로컬 복사본에 대 한 SQL 브라우저입니다.</span><span class="sxs-lookup"><span data-stu-id="f683b-125">SQL Browser for the local replicated copy of the Central Management Store database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f683b-126">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="f683b-126">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="f683b-127">Lync Server 프런트 엔드 서비스</span><span class="sxs-lookup"><span data-stu-id="f683b-127">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="f683b-128">5060</span><span class="sxs-lookup"><span data-stu-id="f683b-128">5060</span></span></p></td>
<td><p><span data-ttu-id="f683b-129">NET.TCP</span><span class="sxs-lookup"><span data-stu-id="f683b-129">TCP</span></span></p></td>
<td><p><span data-ttu-id="f683b-130">필요에 따라 원격 통화 제어 서버와 같은 신뢰할 수 있는 서비스에 대 한 고정 경로에 대 한 표준 버전 서버 및 프런트 엔드 서버에서 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f683b-130">Optionally used by Standard Edition servers and Front End Servers for static routes to trusted services, such as remote call control servers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f683b-131">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="f683b-131">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="f683b-132">Lync Server 프런트 엔드 서비스</span><span class="sxs-lookup"><span data-stu-id="f683b-132">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="f683b-133">5061</span><span class="sxs-lookup"><span data-stu-id="f683b-133">5061</span></span></p></td>
<td><p><span data-ttu-id="f683b-134">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="f683b-134">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="f683b-135">서버와 클라이언트 (MTLS) 간의 SIP 통신 및 프런트 엔드 서버와 조정 서버 (MTLS) 간의 SIP 통신에 대 한 모든 내부 SIP 통신에 대 한 표준 버전 서버 및 프런트 엔드 풀에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f683b-135">Used by Standard Edition servers and Front End pools for all internal SIP communications between servers (MTLS), for SIP communications between Server and Client (TLS) and for SIP communications between Front End Servers and Mediation Servers (MTLS).</span></span> <span data-ttu-id="f683b-136">모니터링 서버와 통신 하는 데도 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f683b-136">Also used for communications with Monitoring Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f683b-137">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="f683b-137">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="f683b-138">Lync Server 프런트 엔드 서비스</span><span class="sxs-lookup"><span data-stu-id="f683b-138">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="f683b-139">444</span><span class="sxs-lookup"><span data-stu-id="f683b-139">444</span></span></p></td>
<td><p><span data-ttu-id="f683b-140">HTTPS</span><span class="sxs-lookup"><span data-stu-id="f683b-140">HTTPS</span></span></p>
<p><span data-ttu-id="f683b-141">NET.TCP</span><span class="sxs-lookup"><span data-stu-id="f683b-141">TCP</span></span></p></td>
<td><p><span data-ttu-id="f683b-142">포커스 (회의 상태를 관리 하는 Lync Server 구성 요소)와 개별 서버 간의 HTTPS 통신에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f683b-142">Used for HTTPS communication between the Focus (the Lync Server component that manages conference state) and the individual servers.</span></span></p>
<p><span data-ttu-id="f683b-143">이 포트는 Survivable Branch 기기 및 프런트 엔드 서버 간의 TCP 통신에도 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f683b-143">This port is also used for TCP communication between Survivable Branch Appliances and Front End Servers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f683b-144">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="f683b-144">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="f683b-145">Lync Server 프런트 엔드 서비스</span><span class="sxs-lookup"><span data-stu-id="f683b-145">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="f683b-146">135</span><span class="sxs-lookup"><span data-stu-id="f683b-146">135</span></span></p></td>
<td><p><span data-ttu-id="f683b-147">DCOM 및 RPC (원격 프로시저 호출)</span><span class="sxs-lookup"><span data-stu-id="f683b-147">DCOM and remote procedure call (RPC)</span></span></p></td>
<td><p><span data-ttu-id="f683b-148">사용자 이동, 사용자 복제기 동기화, 주소록 동기화 등의 DCOM 기반 작업에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f683b-148">Used for DCOM based operations such as Moving Users, User Replicator Synchronization, and Address Book Synchronization.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f683b-149">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="f683b-149">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="f683b-150">Lync Server 메신저 회의 서비스</span><span class="sxs-lookup"><span data-stu-id="f683b-150">Lync Server IM Conferencing service</span></span></p></td>
<td><p><span data-ttu-id="f683b-151">5062</span><span class="sxs-lookup"><span data-stu-id="f683b-151">5062</span></span></p></td>
<td><p><span data-ttu-id="f683b-152">NET.TCP</span><span class="sxs-lookup"><span data-stu-id="f683b-152">TCP</span></span></p></td>
<td><p><span data-ttu-id="f683b-153">인스턴트 메시징 (IM) 회의에 들어오는 SIP 요청에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f683b-153">Used for incoming SIP requests for instant messaging (IM) conferencing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f683b-154">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="f683b-154">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="f683b-155">Lync Server 웹 회의 서비스</span><span class="sxs-lookup"><span data-stu-id="f683b-155">Lync Server Web Conferencing service</span></span></p></td>
<td><p><span data-ttu-id="f683b-156">8057</span><span class="sxs-lookup"><span data-stu-id="f683b-156">8057</span></span></p></td>
<td><p><span data-ttu-id="f683b-157">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="f683b-157">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="f683b-158">클라이언트의 PSOM (영구 공유 개체 모델) 연결을 수신 대기 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f683b-158">Used to listen for Persistent Shared Object Model (PSOM) connections from client.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f683b-159">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="f683b-159">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="f683b-160">Lync Server 웹 회의 호환성 서비스</span><span class="sxs-lookup"><span data-stu-id="f683b-160">Lync Server Web Conferencing Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="f683b-161">8058</span><span class="sxs-lookup"><span data-stu-id="f683b-161">8058</span></span></p></td>
<td><p><span data-ttu-id="f683b-162">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="f683b-162">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="f683b-163">Live Meeting 클라이언트 및 이전 버전의 Lync Server에서 영구 공유 개체 모델 (PSOM) 연결을 수신 대기 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f683b-163">Used to listen for Persistent Shared Object Model (PSOM) connections from the Live Meeting client and previous versions of Lync Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f683b-164">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="f683b-164">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="f683b-165">Lync Server 오디오/비디오 회의 서비스</span><span class="sxs-lookup"><span data-stu-id="f683b-165">Lync Server Audio/Video Conferencing service</span></span></p></td>
<td><p><span data-ttu-id="f683b-166">5063</span><span class="sxs-lookup"><span data-stu-id="f683b-166">5063</span></span></p></td>
<td><p><span data-ttu-id="f683b-167">NET.TCP</span><span class="sxs-lookup"><span data-stu-id="f683b-167">TCP</span></span></p></td>
<td><p><span data-ttu-id="f683b-168">오디오/비디오 (A/V) 회의에 대 한 들어오는 SIP 요청에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f683b-168">Used for incoming SIP requests for audio/video (A/V) conferencing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f683b-169">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="f683b-169">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="f683b-170">Lync Server 오디오/비디오 회의 서비스</span><span class="sxs-lookup"><span data-stu-id="f683b-170">Lync Server Audio/Video Conferencing service</span></span></p></td>
<td><p><span data-ttu-id="f683b-171">57501-65535</span><span class="sxs-lookup"><span data-stu-id="f683b-171">57501-65535</span></span></p></td>
<td><p><span data-ttu-id="f683b-172">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="f683b-172">TCP/UDP</span></span></p></td>
<td><p><span data-ttu-id="f683b-173">비디오 회의에 사용 되는 미디어 포트 범위</span><span class="sxs-lookup"><span data-stu-id="f683b-173">Media port range used for video conferencing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f683b-174">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="f683b-174">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="f683b-175">Lync Server 웹 호환성 서비스</span><span class="sxs-lookup"><span data-stu-id="f683b-175">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="f683b-176">80</span><span class="sxs-lookup"><span data-stu-id="f683b-176">80</span></span></p></td>
<td><p><span data-ttu-id="f683b-177">HTTP</span><span class="sxs-lookup"><span data-stu-id="f683b-177">HTTP</span></span></p></td>
<td><p><span data-ttu-id="f683b-178">HTTPS를 사용 하지 않을 때 프런트 엔드 서버에서 웹 팜 Fqdn (IIS 웹 구성 요소에 사용 되는 Url)으로 통신 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f683b-178">Used for communication from Front End Servers to the web farm FQDNs (the URLs used by IIS web components) when HTTPS is not used.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f683b-179">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="f683b-179">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="f683b-180">Lync Server 웹 호환성 서비스</span><span class="sxs-lookup"><span data-stu-id="f683b-180">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="f683b-181">443</span><span class="sxs-lookup"><span data-stu-id="f683b-181">443</span></span></p></td>
<td><p><span data-ttu-id="f683b-182">HTTPS</span><span class="sxs-lookup"><span data-stu-id="f683b-182">HTTPS</span></span></p></td>
<td><p><span data-ttu-id="f683b-183">프런트 엔드 서버에서 웹 팜 Fqdn으로 통신 하는 데 사용 됩니다 (IIS 웹 구성 요소에 사용 되는 Url).</span><span class="sxs-lookup"><span data-stu-id="f683b-183">Used for communication from Front End Servers to the web farm FQDNs (the URLs used by IIS web components).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f683b-184">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="f683b-184">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="f683b-185">Lync Server 웹 호환성 서비스</span><span class="sxs-lookup"><span data-stu-id="f683b-185">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="f683b-186">8080</span><span class="sxs-lookup"><span data-stu-id="f683b-186">8080</span></span></p></td>
<td><p><span data-ttu-id="f683b-187">TCP 및 HTTP</span><span class="sxs-lookup"><span data-stu-id="f683b-187">TCP and HTTP</span></span></p></td>
<td><p><span data-ttu-id="f683b-188">외부 액세스를 위한 웹 구성 요소에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f683b-188">Used by web components for external access.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f683b-189">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="f683b-189">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="f683b-190">웹 서버 구성 요소</span><span class="sxs-lookup"><span data-stu-id="f683b-190">Web server component</span></span></p></td>
<td><p><span data-ttu-id="f683b-191">4443</span><span class="sxs-lookup"><span data-stu-id="f683b-191">4443</span></span></p></td>
<td><p><span data-ttu-id="f683b-192">HTTPS</span><span class="sxs-lookup"><span data-stu-id="f683b-192">HTTPS</span></span></p></td>
<td><p><span data-ttu-id="f683b-193">자동 검색 로그인을 위한 HTTPS (역방향 프록시) 및 HTTPS 프런트 엔드 풀 간 통신</span><span class="sxs-lookup"><span data-stu-id="f683b-193">HTTPS (from Reverse Proxy) and HTTPS Front End inter-pool communications for Autodiscover sign-in.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f683b-194">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="f683b-194">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="f683b-195">웹 서버 구성 요소</span><span class="sxs-lookup"><span data-stu-id="f683b-195">Web server component</span></span></p></td>
<td><p><span data-ttu-id="f683b-196">8060</span><span class="sxs-lookup"><span data-stu-id="f683b-196">8060</span></span></p></td>
<td><p><span data-ttu-id="f683b-197">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="f683b-197">TCP (MTLS)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f683b-198">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="f683b-198">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="f683b-199">웹 서버 구성 요소</span><span class="sxs-lookup"><span data-stu-id="f683b-199">Web server component</span></span></p></td>
<td><p><span data-ttu-id="f683b-200">8061</span><span class="sxs-lookup"><span data-stu-id="f683b-200">8061</span></span></p></td>
<td><p><span data-ttu-id="f683b-201">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="f683b-201">TCP (MTLS)</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f683b-202">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="f683b-202">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="f683b-203">Mobility Services 구성 요소</span><span class="sxs-lookup"><span data-stu-id="f683b-203">Mobility Services component</span></span></p></td>
<td><p><span data-ttu-id="f683b-204">5086</span><span class="sxs-lookup"><span data-stu-id="f683b-204">5086</span></span></p></td>
<td><p><span data-ttu-id="f683b-205">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="f683b-205">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="f683b-206">모바일 서비스 내부 프로세스에서 사용 하는 SIP 포트</span><span class="sxs-lookup"><span data-stu-id="f683b-206">SIP port used by Mobility Services internal processes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f683b-207">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="f683b-207">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="f683b-208">Mobility Services 구성 요소</span><span class="sxs-lookup"><span data-stu-id="f683b-208">Mobility Services component</span></span></p></td>
<td><p><span data-ttu-id="f683b-209">5087</span><span class="sxs-lookup"><span data-stu-id="f683b-209">5087</span></span></p></td>
<td><p><span data-ttu-id="f683b-210">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="f683b-210">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="f683b-211">모바일 서비스 내부 프로세스에서 사용 하는 SIP 포트</span><span class="sxs-lookup"><span data-stu-id="f683b-211">SIP port used by Mobility Services internal processes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f683b-212">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="f683b-212">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="f683b-213">Mobility Services 구성 요소</span><span class="sxs-lookup"><span data-stu-id="f683b-213">Mobility Services component</span></span></p></td>
<td><p><span data-ttu-id="f683b-214">443</span><span class="sxs-lookup"><span data-stu-id="f683b-214">443</span></span></p></td>
<td><p><span data-ttu-id="f683b-215">HTTPS</span><span class="sxs-lookup"><span data-stu-id="f683b-215">HTTPS</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f683b-216">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="f683b-216">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="f683b-217">Lync Server 회의 수행자 서비스 (전화 접속 회의)</span><span class="sxs-lookup"><span data-stu-id="f683b-217">Lync Server Conferencing Attendant service (dial-in conferencing)</span></span></p></td>
<td><p><span data-ttu-id="f683b-218">5064</span><span class="sxs-lookup"><span data-stu-id="f683b-218">5064</span></span></p></td>
<td><p><span data-ttu-id="f683b-219">NET.TCP</span><span class="sxs-lookup"><span data-stu-id="f683b-219">TCP</span></span></p></td>
<td><p><span data-ttu-id="f683b-220">전화 접속 회의에 대 한 수신 SIP 요청에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f683b-220">Used for incoming SIP requests for dial-in conferencing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f683b-221">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="f683b-221">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="f683b-222">Lync Server 회의 수행자 서비스 (전화 접속 회의)</span><span class="sxs-lookup"><span data-stu-id="f683b-222">Lync Server Conferencing Attendant service (dial-in conferencing)</span></span></p></td>
<td><p><span data-ttu-id="f683b-223">5072</span><span class="sxs-lookup"><span data-stu-id="f683b-223">5072</span></span></p></td>
<td><p><span data-ttu-id="f683b-224">NET.TCP</span><span class="sxs-lookup"><span data-stu-id="f683b-224">TCP</span></span></p></td>
<td><p><span data-ttu-id="f683b-225">전화 교환의 수신 SIP 요청에 사용 됨 (회의에 전화 걸기).</span><span class="sxs-lookup"><span data-stu-id="f683b-225">Used for incoming SIP requests for Attendant (dial in conferencing).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f683b-226">Collocated 중재 서버도 실행 하는 프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="f683b-226">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="f683b-227">Lync Server 중재 서비스</span><span class="sxs-lookup"><span data-stu-id="f683b-227">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="f683b-228">5070</span><span class="sxs-lookup"><span data-stu-id="f683b-228">5070</span></span></p></td>
<td><p><span data-ttu-id="f683b-229">NET.TCP</span><span class="sxs-lookup"><span data-stu-id="f683b-229">TCP</span></span></p></td>
<td><p><span data-ttu-id="f683b-230">프런트 엔드 서버에서 중재 서버로 들어오는 요청에 대 한 조정 서버에서 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f683b-230">Used by the Mediation Server for incoming requests from the Front End Server to the Mediation Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f683b-231">Collocated 중재 서버도 실행 하는 프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="f683b-231">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="f683b-232">Lync Server 중재 서비스</span><span class="sxs-lookup"><span data-stu-id="f683b-232">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="f683b-233">5067</span><span class="sxs-lookup"><span data-stu-id="f683b-233">5067</span></span></p></td>
<td><p><span data-ttu-id="f683b-234">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="f683b-234">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="f683b-235">PSTN 게이트웨이에서 중재 서버로 들어오는 SIP 요청에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f683b-235">Used for incoming SIP requests from the PSTN gateway to the Mediation Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f683b-236">Collocated 중재 서버도 실행 하는 프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="f683b-236">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="f683b-237">Lync Server 중재 서비스</span><span class="sxs-lookup"><span data-stu-id="f683b-237">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="f683b-238">5068</span><span class="sxs-lookup"><span data-stu-id="f683b-238">5068</span></span></p></td>
<td><p><span data-ttu-id="f683b-239">NET.TCP</span><span class="sxs-lookup"><span data-stu-id="f683b-239">TCP</span></span></p></td>
<td><p><span data-ttu-id="f683b-240">PSTN 게이트웨이에서 중재 서버로 들어오는 SIP 요청에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f683b-240">Used for incoming SIP requests from the PSTN gateway to the Mediation Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f683b-241">Collocated 중재 서버도 실행 하는 프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="f683b-241">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="f683b-242">Lync Server 중재 서비스</span><span class="sxs-lookup"><span data-stu-id="f683b-242">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="f683b-243">5081</span><span class="sxs-lookup"><span data-stu-id="f683b-243">5081</span></span></p></td>
<td><p><span data-ttu-id="f683b-244">NET.TCP</span><span class="sxs-lookup"><span data-stu-id="f683b-244">TCP</span></span></p></td>
<td><p><span data-ttu-id="f683b-245">중재 서버에서 PSTN 게이트웨이로 보내는 SIP 요청에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f683b-245">Used for outgoing SIP requests from the Mediation Server to the PSTN gateway.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f683b-246">Collocated 중재 서버도 실행 하는 프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="f683b-246">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="f683b-247">Lync Server 중재 서비스</span><span class="sxs-lookup"><span data-stu-id="f683b-247">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="f683b-248">5082</span><span class="sxs-lookup"><span data-stu-id="f683b-248">5082</span></span></p></td>
<td><p><span data-ttu-id="f683b-249">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="f683b-249">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="f683b-250">중재 서버에서 PSTN 게이트웨이로 보내는 SIP 요청에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f683b-250">Used for outgoing SIP requests from the Mediation Server to the PSTN gateway.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f683b-251">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="f683b-251">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="f683b-252">Lync Server 응용 프로그램 공유 서비스</span><span class="sxs-lookup"><span data-stu-id="f683b-252">Lync Server Application Sharing service</span></span></p></td>
<td><p><span data-ttu-id="f683b-253">5065</span><span class="sxs-lookup"><span data-stu-id="f683b-253">5065</span></span></p></td>
<td><p><span data-ttu-id="f683b-254">NET.TCP</span><span class="sxs-lookup"><span data-stu-id="f683b-254">TCP</span></span></p></td>
<td><p><span data-ttu-id="f683b-255">응용 프로그램 공유에 대 한 수신 SIP 수신 요청에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f683b-255">Used for incoming SIP listening requests for application sharing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f683b-256">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="f683b-256">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="f683b-257">Lync Server 응용 프로그램 공유 서비스</span><span class="sxs-lookup"><span data-stu-id="f683b-257">Lync Server Application Sharing service</span></span></p></td>
<td><p><span data-ttu-id="f683b-258">49152-65535</span><span class="sxs-lookup"><span data-stu-id="f683b-258">49152-65535</span></span></p></td>
<td><p><span data-ttu-id="f683b-259">NET.TCP</span><span class="sxs-lookup"><span data-stu-id="f683b-259">TCP</span></span></p></td>
<td><p><span data-ttu-id="f683b-260">응용 프로그램 공유에 사용 되는 미디어 포트 범위입니다.</span><span class="sxs-lookup"><span data-stu-id="f683b-260">Media port range used for application sharing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f683b-261">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="f683b-261">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="f683b-262">Lync 서버 회의 알림 서비스</span><span class="sxs-lookup"><span data-stu-id="f683b-262">Lync Server Conferencing Announcement service</span></span></p></td>
<td><p><span data-ttu-id="f683b-263">5073</span><span class="sxs-lookup"><span data-stu-id="f683b-263">5073</span></span></p></td>
<td><p><span data-ttu-id="f683b-264">NET.TCP</span><span class="sxs-lookup"><span data-stu-id="f683b-264">TCP</span></span></p></td>
<td><p><span data-ttu-id="f683b-265">Lync Server 회의 알림 서비스에 대 한 들어오는 SIP 요청에 사용 됩니다 (즉, 전화 접속 회의의 경우).</span><span class="sxs-lookup"><span data-stu-id="f683b-265">Used for incoming SIP requests for the Lync Server Conferencing Announcement service (that is, for dial-in conferencing).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f683b-266">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="f683b-266">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="f683b-267">Lync Server 통화 공원 서비스</span><span class="sxs-lookup"><span data-stu-id="f683b-267">Lync Server Call Park service</span></span></p></td>
<td><p><span data-ttu-id="f683b-268">5075</span><span class="sxs-lookup"><span data-stu-id="f683b-268">5075</span></span></p></td>
<td><p><span data-ttu-id="f683b-269">NET.TCP</span><span class="sxs-lookup"><span data-stu-id="f683b-269">TCP</span></span></p></td>
<td><p><span data-ttu-id="f683b-270">통화 공원 응용 프로그램에 대 한 수신 SIP 요청에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f683b-270">Used for incoming SIP requests for the Call Park application.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f683b-271">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="f683b-271">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="f683b-272">Lync Server 오디오 테스트 서비스</span><span class="sxs-lookup"><span data-stu-id="f683b-272">Lync Server Audio Test service</span></span></p></td>
<td><p><span data-ttu-id="f683b-273">5076</span><span class="sxs-lookup"><span data-stu-id="f683b-273">5076</span></span></p></td>
<td><p><span data-ttu-id="f683b-274">NET.TCP</span><span class="sxs-lookup"><span data-stu-id="f683b-274">TCP</span></span></p></td>
<td><p><span data-ttu-id="f683b-275">오디오 테스트 서비스에 대 한 들어오는 SIP 요청에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f683b-275">Used for incoming SIP requests for the Audio Test service.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f683b-276">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="f683b-276">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="f683b-277">해당 없음</span><span class="sxs-lookup"><span data-stu-id="f683b-277">Not applicable</span></span></p></td>
<td><p><span data-ttu-id="f683b-278">5066</span><span class="sxs-lookup"><span data-stu-id="f683b-278">5066</span></span></p></td>
<td><p><span data-ttu-id="f683b-279">NET.TCP</span><span class="sxs-lookup"><span data-stu-id="f683b-279">TCP</span></span></p></td>
<td><p><span data-ttu-id="f683b-280">아웃 바운드 향상 9-1-1 (E9-1-1) 게이트웨이에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f683b-280">Used for outbound Enhanced 9-1-1 (E9-1-1) gateway.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f683b-281">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="f683b-281">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="f683b-282">Lync Server 응답 그룹 서비스</span><span class="sxs-lookup"><span data-stu-id="f683b-282">Lync Server Response Group service</span></span></p></td>
<td><p><span data-ttu-id="f683b-283">5071</span><span class="sxs-lookup"><span data-stu-id="f683b-283">5071</span></span></p></td>
<td><p><span data-ttu-id="f683b-284">NET.TCP</span><span class="sxs-lookup"><span data-stu-id="f683b-284">TCP</span></span></p></td>
<td><p><span data-ttu-id="f683b-285">응답 그룹 응용 프로그램에 대 한 들어오는 SIP 요청에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f683b-285">Used for incoming SIP requests for the Response Group application.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f683b-286">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="f683b-286">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="f683b-287">Lync Server 응답 그룹 서비스</span><span class="sxs-lookup"><span data-stu-id="f683b-287">Lync Server Response Group service</span></span></p></td>
<td><p><span data-ttu-id="f683b-288">8404</span><span class="sxs-lookup"><span data-stu-id="f683b-288">8404</span></span></p></td>
<td><p><span data-ttu-id="f683b-289">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="f683b-289">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="f683b-290">응답 그룹 응용 프로그램에 대 한 들어오는 SIP 요청에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f683b-290">Used for incoming SIP requests for the Response Group application.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f683b-291">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="f683b-291">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="f683b-292">Lync Server 대역폭 정책 서비스</span><span class="sxs-lookup"><span data-stu-id="f683b-292">Lync Server Bandwidth Policy Service</span></span></p></td>
<td><p><span data-ttu-id="f683b-293">5080</span><span class="sxs-lookup"><span data-stu-id="f683b-293">5080</span></span></p></td>
<td><p><span data-ttu-id="f683b-294">NET.TCP</span><span class="sxs-lookup"><span data-stu-id="f683b-294">TCP</span></span></p></td>
<td><p><span data-ttu-id="f683b-295">대역폭 정책 서비스에 의해 통화 허용 제어에 사용 됩니다 (A/V Edge TURN 트래픽).</span><span class="sxs-lookup"><span data-stu-id="f683b-295">Used for call admission control by the Bandwidth Policy service for A/V Edge TURN traffic.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f683b-296">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="f683b-296">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="f683b-297">Lync Server 대역폭 정책 서비스</span><span class="sxs-lookup"><span data-stu-id="f683b-297">Lync Server Bandwidth Policy Service</span></span></p></td>
<td><p><span data-ttu-id="f683b-298">448</span><span class="sxs-lookup"><span data-stu-id="f683b-298">448</span></span></p></td>
<td><p><span data-ttu-id="f683b-299">NET.TCP</span><span class="sxs-lookup"><span data-stu-id="f683b-299">TCP</span></span></p></td>
<td><p><span data-ttu-id="f683b-300">Lync Server 대역폭 정책 서비스에의 한 통화 허용 제어에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f683b-300">Used for call admission control by the Lync Server Bandwidth Policy Service.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f683b-301">중앙 관리 저장소가 상주 하는 프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="f683b-301">Front End Servers where the Central Management store resides</span></span></p></td>
<td><p><span data-ttu-id="f683b-302">Lync Server 마스터 복제기 에이전트 서비스</span><span class="sxs-lookup"><span data-stu-id="f683b-302">Lync Server Master Replicator Agent service</span></span></p></td>
<td><p><span data-ttu-id="f683b-303">445</span><span class="sxs-lookup"><span data-stu-id="f683b-303">445</span></span></p></td>
<td><p><span data-ttu-id="f683b-304">NET.TCP</span><span class="sxs-lookup"><span data-stu-id="f683b-304">TCP</span></span></p></td>
<td><p><span data-ttu-id="f683b-305">중앙 관리 저장소의 구성 데이터를 Lync Server를 실행 하는 서버에 푸시하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f683b-305">Used to push configuration data from the Central Management store to servers running Lync Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f683b-306">모든 서버</span><span class="sxs-lookup"><span data-stu-id="f683b-306">All Servers</span></span></p></td>
<td><p><span data-ttu-id="f683b-307">SQL 브라우저</span><span class="sxs-lookup"><span data-stu-id="f683b-307">SQL Browser</span></span></p></td>
<td><p><span data-ttu-id="f683b-308">1434</span><span class="sxs-lookup"><span data-stu-id="f683b-308">1434</span></span></p></td>
<td><p><span data-ttu-id="f683b-309">UDP</span><span class="sxs-lookup"><span data-stu-id="f683b-309">UDP</span></span></p></td>
<td><p><span data-ttu-id="f683b-310">로컬 SQL Server 인스턴스에서 중앙 관리 저장소 데이터의 로컬 복제 복사본에 대 한 SQL 브라우저</span><span class="sxs-lookup"><span data-stu-id="f683b-310">SQL Browser for local replicated copy of Central Management store data in local SQL Server instance</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f683b-311">모든 내부 서버</span><span class="sxs-lookup"><span data-stu-id="f683b-311">All internal servers</span></span></p></td>
<td><p><span data-ttu-id="f683b-312">다양 한</span><span class="sxs-lookup"><span data-stu-id="f683b-312">Various</span></span></p></td>
<td><p><span data-ttu-id="f683b-313">49152-57500</span><span class="sxs-lookup"><span data-stu-id="f683b-313">49152-57500</span></span></p></td>
<td><p><span data-ttu-id="f683b-314">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="f683b-314">TCP/UDP</span></span></p></td>
<td><p><span data-ttu-id="f683b-315">모든 내부 서버에서 오디오 회의에 사용 되는 미디어 포트 범위</span><span class="sxs-lookup"><span data-stu-id="f683b-315">Media port range used for audio conferencing on all internal servers.</span></span> <span data-ttu-id="f683b-316">오디오를 종료 하는 모든 서버 (Lync Server 회의 수행자 서비스, Lync server 회의 알림 서비스, lync Server 오디오/비디오 회의 서비스의 경우) 및 중재 서버에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f683b-316">Used by all servers that terminate audio: Front End Servers (for Lync Server Conferencing Attendant service, Lync Server Conferencing Announcement service, and Lync Server Audio/Video Conferencing service), and Mediation Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f683b-317">Office Web Apps 서버</span><span class="sxs-lookup"><span data-stu-id="f683b-317">Office Web Apps Servers</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f683b-318">443</span><span class="sxs-lookup"><span data-stu-id="f683b-318">443</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f683b-319">Lync Server 2013에서 Office Web Apps 서버에 연결 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f683b-319">Used by Lync Server 2013 to connect to Office Web Apps Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f683b-320">이사</span><span class="sxs-lookup"><span data-stu-id="f683b-320">Directors</span></span></p></td>
<td><p><span data-ttu-id="f683b-321">Lync Server 프런트 엔드 서비스</span><span class="sxs-lookup"><span data-stu-id="f683b-321">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="f683b-322">5060</span><span class="sxs-lookup"><span data-stu-id="f683b-322">5060</span></span></p></td>
<td><p><span data-ttu-id="f683b-323">NET.TCP</span><span class="sxs-lookup"><span data-stu-id="f683b-323">TCP</span></span></p></td>
<td><p><span data-ttu-id="f683b-324">필요에 따라 원격 통화 제어 서버와 같은 신뢰할 수 있는 서비스에 대 한 고정 경로에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f683b-324">Optionally used for static routes to trusted services, such as remote call control servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f683b-325">이사</span><span class="sxs-lookup"><span data-stu-id="f683b-325">Directors</span></span></p></td>
<td><p><span data-ttu-id="f683b-326">Lync Server 프런트 엔드 서비스</span><span class="sxs-lookup"><span data-stu-id="f683b-326">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="f683b-327">444</span><span class="sxs-lookup"><span data-stu-id="f683b-327">444</span></span></p></td>
<td><p><span data-ttu-id="f683b-328">HTTPS</span><span class="sxs-lookup"><span data-stu-id="f683b-328">HTTPS</span></span></p>
<p><span data-ttu-id="f683b-329">NET.TCP</span><span class="sxs-lookup"><span data-stu-id="f683b-329">TCP</span></span></p></td>
<td><p><span data-ttu-id="f683b-330">프론트 엔드 및 디렉터 간의 서버 간 통신.</span><span class="sxs-lookup"><span data-stu-id="f683b-330">Inter-server communication between Front End and Director.</span></span> <span data-ttu-id="f683b-331">또한 클라이언트 인증서가 프런트 엔드 서버로 게시 되거나 클라이언트 인증서가 이미 게시 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="f683b-331">Additionally, client certificate publish (to Front End Servers) or validate if the client certificate has already been published.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f683b-332">이사</span><span class="sxs-lookup"><span data-stu-id="f683b-332">Directors</span></span></p></td>
<td><p><span data-ttu-id="f683b-333">Lync Server 웹 호환성 서비스</span><span class="sxs-lookup"><span data-stu-id="f683b-333">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="f683b-334">80</span><span class="sxs-lookup"><span data-stu-id="f683b-334">80</span></span></p></td>
<td><p><span data-ttu-id="f683b-335">NET.TCP</span><span class="sxs-lookup"><span data-stu-id="f683b-335">TCP</span></span></p></td>
<td><p><span data-ttu-id="f683b-336">디렉터에서 웹 팜 Fqdn으로 초기 통신 하는 데 사용 됩니다 (IIS 웹 구성 요소에 사용 되는 Url).</span><span class="sxs-lookup"><span data-stu-id="f683b-336">Used for initial communication from Directors to the web farm FQDNs (the URLs used by IIS web components).</span></span> <span data-ttu-id="f683b-337">정상 작업에서 포트 443 및 프로토콜 유형 TCP를 사용 하 여 HTTPS 트래픽으로 전환 합니다.</span><span class="sxs-lookup"><span data-stu-id="f683b-337">In normal operation, will switch to HTTPS traffic, using port 443 and protocol type TCP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f683b-338">이사</span><span class="sxs-lookup"><span data-stu-id="f683b-338">Directors</span></span></p></td>
<td><p><span data-ttu-id="f683b-339">Lync Server 웹 호환성 서비스</span><span class="sxs-lookup"><span data-stu-id="f683b-339">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="f683b-340">443</span><span class="sxs-lookup"><span data-stu-id="f683b-340">443</span></span></p></td>
<td><p><span data-ttu-id="f683b-341">HTTPS</span><span class="sxs-lookup"><span data-stu-id="f683b-341">HTTPS</span></span></p></td>
<td><p><span data-ttu-id="f683b-342">디렉터에서 웹 팜 Fqdn으로 통신 하는 데 사용 됩니다 (IIS 웹 구성 요소에 사용 되는 Url).</span><span class="sxs-lookup"><span data-stu-id="f683b-342">Used for communication from Directors to the web farm FQDNs (the URLs used by IIS web components).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f683b-343">이사</span><span class="sxs-lookup"><span data-stu-id="f683b-343">Directors</span></span></p></td>
<td><p><span data-ttu-id="f683b-344">Lync Server 프런트 엔드 서비스</span><span class="sxs-lookup"><span data-stu-id="f683b-344">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="f683b-345">5061</span><span class="sxs-lookup"><span data-stu-id="f683b-345">5061</span></span></p></td>
<td><p><span data-ttu-id="f683b-346">NET.TCP</span><span class="sxs-lookup"><span data-stu-id="f683b-346">TCP</span></span></p></td>
<td><p><span data-ttu-id="f683b-347">서버 간 내부 통신 및 클라이언트 연결에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f683b-347">Used for internal communications between servers and for client connections.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f683b-348">중재 서버</span><span class="sxs-lookup"><span data-stu-id="f683b-348">Mediation Servers</span></span></p></td>
<td><p><span data-ttu-id="f683b-349">Lync Server 중재 서비스</span><span class="sxs-lookup"><span data-stu-id="f683b-349">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="f683b-350">5070</span><span class="sxs-lookup"><span data-stu-id="f683b-350">5070</span></span></p></td>
<td><p><span data-ttu-id="f683b-351">NET.TCP</span><span class="sxs-lookup"><span data-stu-id="f683b-351">TCP</span></span></p></td>
<td><p><span data-ttu-id="f683b-352">프런트 엔드 서버에서 들어오는 요청에 대해 조정 서버에서 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f683b-352">Used by the Mediation Server for incoming requests from the Front End Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f683b-353">중재 서버</span><span class="sxs-lookup"><span data-stu-id="f683b-353">Mediation Servers</span></span></p></td>
<td><p><span data-ttu-id="f683b-354">Lync Server 중재 서비스</span><span class="sxs-lookup"><span data-stu-id="f683b-354">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="f683b-355">5067</span><span class="sxs-lookup"><span data-stu-id="f683b-355">5067</span></span></p></td>
<td><p><span data-ttu-id="f683b-356">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="f683b-356">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="f683b-357">PSTN 게이트웨이에서 들어오는 SIP 요청에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f683b-357">Used for incoming SIP requests from the PSTN gateway.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f683b-358">중재 서버</span><span class="sxs-lookup"><span data-stu-id="f683b-358">Mediation Servers</span></span></p></td>
<td><p><span data-ttu-id="f683b-359">Lync Server 중재 서비스</span><span class="sxs-lookup"><span data-stu-id="f683b-359">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="f683b-360">5068</span><span class="sxs-lookup"><span data-stu-id="f683b-360">5068</span></span></p></td>
<td><p><span data-ttu-id="f683b-361">NET.TCP</span><span class="sxs-lookup"><span data-stu-id="f683b-361">TCP</span></span></p></td>
<td><p><span data-ttu-id="f683b-362">PSTN 게이트웨이에서 들어오는 SIP 요청에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f683b-362">Used for incoming SIP requests from the PSTN gateway.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f683b-363">중재 서버</span><span class="sxs-lookup"><span data-stu-id="f683b-363">Mediation Servers</span></span></p></td>
<td><p><span data-ttu-id="f683b-364">Lync Server 중재 서비스</span><span class="sxs-lookup"><span data-stu-id="f683b-364">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="f683b-365">5070</span><span class="sxs-lookup"><span data-stu-id="f683b-365">5070</span></span></p></td>
<td><p><span data-ttu-id="f683b-366">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="f683b-366">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="f683b-367">프런트 엔드 서버의 SIP 요청에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f683b-367">Used for SIP requests from the Front End Servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f683b-368">영구 채팅 프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="f683b-368">Persistent Chat Front End Server</span></span></p></td>
<td><p><span data-ttu-id="f683b-369">영구 채팅 SIP</span><span class="sxs-lookup"><span data-stu-id="f683b-369">Persistent Chat SIP</span></span></p></td>
<td><p><span data-ttu-id="f683b-370">5041</span><span class="sxs-lookup"><span data-stu-id="f683b-370">5041</span></span></p></td>
<td><p><span data-ttu-id="f683b-371">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="f683b-371">TCP (MTLS)</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f683b-372">영구 채팅 프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="f683b-372">Persistent Chat Front End Server</span></span></p></td>
<td><p><span data-ttu-id="f683b-373">WCF (Windows Communication Foundation) 영구 채팅</span><span class="sxs-lookup"><span data-stu-id="f683b-373">Persistent Chat Windows Communication Foundation (WCF)</span></span></p></td>
<td><p><span data-ttu-id="f683b-374">881</span><span class="sxs-lookup"><span data-stu-id="f683b-374">881</span></span></p></td>
<td><p><span data-ttu-id="f683b-375">TCP (TLS) 및 TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="f683b-375">TCP (TLS) and TCP (MTLS)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f683b-376">영구 채팅 프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="f683b-376">Persistent Chat Front End Server</span></span></p></td>
<td><p><span data-ttu-id="f683b-377">영구 채팅 파일 전송 서비스</span><span class="sxs-lookup"><span data-stu-id="f683b-377">Persistent Chat File Transfer Service</span></span></p></td>
<td><p><span data-ttu-id="f683b-378">443</span><span class="sxs-lookup"><span data-stu-id="f683b-378">443</span></span></p></td>
<td><p><span data-ttu-id="f683b-379">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="f683b-379">TCP (TLS)</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="f683b-380">일부 원격 통화 제어 시나리오는 프런트 엔드 서버 또는 디렉터와 PBX 간의 TCP 연결이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="f683b-380">Some remote call control scenarios require a TCP connection between the Front End Server or Director and the PBX.</span></span> <span data-ttu-id="f683b-381">Lync Server는 더 이상 TCP 포트 5060를 사용 하지 않지만 원격 통화 제어 배포 중에는 RCC 회선 서버 FQDN을 프런트 엔드 서버 또는 디렉터가 PBX 시스템에 연결 하는 데 사용할 TCP 포트와 연결 하는 신뢰할 수 있는 서버 구성을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f683b-381">Although Lync Server no longer uses TCP port 5060, during remote call control deployment you create a trusted server configuration, which associates the RCC Line Server FQDN with the TCP port that the Front End Server or Director will use to connect to the PBX system.</span></span> <span data-ttu-id="f683b-382">자세한 내용은 Lync Server 관리 셸 설명서의 <STRONG>CsTrustedApplicationComputer</STRONG> cmdlet을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f683b-382">For details, see the <STRONG>CsTrustedApplicationComputer</STRONG> cmdlet in the Lync Server Management Shell documentation.</span></span>



</div>

<span data-ttu-id="f683b-383">DNS 부하 분산이 아닌 하드웨어 로드 균형 조정만 사용 하는 풀의 경우 다음 표에는 하드웨어 로드 균형 조정기를 여는 데 필요한 포트가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f683b-383">For your pools that use only hardware load balancing (not DNS load balancing), the following table shows the ports that need to open the hardware load balancers.</span></span>

### <a name="hardware-load-balancer-ports-if-using-only-hardware-load-balancing"></a><span data-ttu-id="f683b-384">하드웨어 부하 분산만 사용 하는 경우 하드웨어 부하 분산 장치 포트</span><span class="sxs-lookup"><span data-stu-id="f683b-384">Hardware Load Balancer Ports if Using Only Hardware Load Balancing</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f683b-385">부하 분산 장치</span><span class="sxs-lookup"><span data-stu-id="f683b-385">Load Balancer</span></span></th>
<th><span data-ttu-id="f683b-386">포트</span><span class="sxs-lookup"><span data-stu-id="f683b-386">Port</span></span></th>
<th><span data-ttu-id="f683b-387">프로토콜별</span><span class="sxs-lookup"><span data-stu-id="f683b-387">Protocol</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f683b-388">프런트 엔드 서버 부하 분산 장치</span><span class="sxs-lookup"><span data-stu-id="f683b-388">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="f683b-389">5061</span><span class="sxs-lookup"><span data-stu-id="f683b-389">5061</span></span></p></td>
<td><p><span data-ttu-id="f683b-390">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="f683b-390">TCP (TLS)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f683b-391">프런트 엔드 서버 부하 분산 장치</span><span class="sxs-lookup"><span data-stu-id="f683b-391">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="f683b-392">444</span><span class="sxs-lookup"><span data-stu-id="f683b-392">444</span></span></p></td>
<td><p><span data-ttu-id="f683b-393">HTTPS</span><span class="sxs-lookup"><span data-stu-id="f683b-393">HTTPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f683b-394">프런트 엔드 서버 부하 분산 장치</span><span class="sxs-lookup"><span data-stu-id="f683b-394">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="f683b-395">135</span><span class="sxs-lookup"><span data-stu-id="f683b-395">135</span></span></p></td>
<td><p><span data-ttu-id="f683b-396">DCOM 및 RPC (원격 프로시저 호출)</span><span class="sxs-lookup"><span data-stu-id="f683b-396">DCOM and remote procedure call (RPC)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f683b-397">프런트 엔드 서버 부하 분산 장치</span><span class="sxs-lookup"><span data-stu-id="f683b-397">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="f683b-398">80</span><span class="sxs-lookup"><span data-stu-id="f683b-398">80</span></span></p></td>
<td><p><span data-ttu-id="f683b-399">HTTP</span><span class="sxs-lookup"><span data-stu-id="f683b-399">HTTP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f683b-400">프런트 엔드 서버 부하 분산 장치</span><span class="sxs-lookup"><span data-stu-id="f683b-400">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="f683b-401">8080</span><span class="sxs-lookup"><span data-stu-id="f683b-401">8080</span></span></p></td>
<td><p><span data-ttu-id="f683b-402">TCP-프런트 엔드 서버에서 루트 인증서의 클라이언트 및 장치 검색-NTLM으로 인증 된 클라이언트 및 장치</span><span class="sxs-lookup"><span data-stu-id="f683b-402">TCP - Client and device retrieval of root certificate from Front End Server – clients and devices authenticated by NTLM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f683b-403">프런트 엔드 서버 부하 분산 장치</span><span class="sxs-lookup"><span data-stu-id="f683b-403">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="f683b-404">443</span><span class="sxs-lookup"><span data-stu-id="f683b-404">443</span></span></p></td>
<td><p><span data-ttu-id="f683b-405">HTTPS</span><span class="sxs-lookup"><span data-stu-id="f683b-405">HTTPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f683b-406">프런트 엔드 서버 부하 분산 장치</span><span class="sxs-lookup"><span data-stu-id="f683b-406">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="f683b-407">4443</span><span class="sxs-lookup"><span data-stu-id="f683b-407">4443</span></span></p></td>
<td><p><span data-ttu-id="f683b-408">HTTPS (역방향 프록시)</span><span class="sxs-lookup"><span data-stu-id="f683b-408">HTTPS (from reverse proxy)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f683b-409">프런트 엔드 서버 부하 분산 장치</span><span class="sxs-lookup"><span data-stu-id="f683b-409">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="f683b-410">5072</span><span class="sxs-lookup"><span data-stu-id="f683b-410">5072</span></span></p></td>
<td><p><span data-ttu-id="f683b-411">NET.TCP</span><span class="sxs-lookup"><span data-stu-id="f683b-411">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f683b-412">프런트 엔드 서버 부하 분산 장치</span><span class="sxs-lookup"><span data-stu-id="f683b-412">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="f683b-413">5073</span><span class="sxs-lookup"><span data-stu-id="f683b-413">5073</span></span></p></td>
<td><p><span data-ttu-id="f683b-414">NET.TCP</span><span class="sxs-lookup"><span data-stu-id="f683b-414">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f683b-415">프런트 엔드 서버 부하 분산 장치</span><span class="sxs-lookup"><span data-stu-id="f683b-415">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="f683b-416">5075</span><span class="sxs-lookup"><span data-stu-id="f683b-416">5075</span></span></p></td>
<td><p><span data-ttu-id="f683b-417">NET.TCP</span><span class="sxs-lookup"><span data-stu-id="f683b-417">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f683b-418">프런트 엔드 서버 부하 분산 장치</span><span class="sxs-lookup"><span data-stu-id="f683b-418">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="f683b-419">5076</span><span class="sxs-lookup"><span data-stu-id="f683b-419">5076</span></span></p></td>
<td><p><span data-ttu-id="f683b-420">NET.TCP</span><span class="sxs-lookup"><span data-stu-id="f683b-420">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f683b-421">프런트 엔드 서버 부하 분산 장치</span><span class="sxs-lookup"><span data-stu-id="f683b-421">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="f683b-422">5071</span><span class="sxs-lookup"><span data-stu-id="f683b-422">5071</span></span></p></td>
<td><p><span data-ttu-id="f683b-423">NET.TCP</span><span class="sxs-lookup"><span data-stu-id="f683b-423">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f683b-424">프런트 엔드 서버 부하 분산 장치</span><span class="sxs-lookup"><span data-stu-id="f683b-424">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="f683b-425">5080</span><span class="sxs-lookup"><span data-stu-id="f683b-425">5080</span></span></p></td>
<td><p><span data-ttu-id="f683b-426">NET.TCP</span><span class="sxs-lookup"><span data-stu-id="f683b-426">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f683b-427">프런트 엔드 서버 부하 분산 장치</span><span class="sxs-lookup"><span data-stu-id="f683b-427">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="f683b-428">448</span><span class="sxs-lookup"><span data-stu-id="f683b-428">448</span></span></p></td>
<td><p><span data-ttu-id="f683b-429">NET.TCP</span><span class="sxs-lookup"><span data-stu-id="f683b-429">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f683b-430">중재 서버 부하 분산 장치</span><span class="sxs-lookup"><span data-stu-id="f683b-430">Mediation Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="f683b-431">5070</span><span class="sxs-lookup"><span data-stu-id="f683b-431">5070</span></span></p></td>
<td><p><span data-ttu-id="f683b-432">NET.TCP</span><span class="sxs-lookup"><span data-stu-id="f683b-432">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f683b-433">프런트 엔드 서버 부하 분산 장치 (풀에서 중재 서버도 실행 되는 경우)</span><span class="sxs-lookup"><span data-stu-id="f683b-433">Front End Server load balancer (if the pool also runs Mediation Server)</span></span></p></td>
<td><p><span data-ttu-id="f683b-434">5070</span><span class="sxs-lookup"><span data-stu-id="f683b-434">5070</span></span></p></td>
<td><p><span data-ttu-id="f683b-435">NET.TCP</span><span class="sxs-lookup"><span data-stu-id="f683b-435">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f683b-436">디렉터 부하 분산 장치</span><span class="sxs-lookup"><span data-stu-id="f683b-436">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="f683b-437">443</span><span class="sxs-lookup"><span data-stu-id="f683b-437">443</span></span></p></td>
<td><p><span data-ttu-id="f683b-438">HTTPS</span><span class="sxs-lookup"><span data-stu-id="f683b-438">HTTPS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f683b-439">디렉터 부하 분산 장치</span><span class="sxs-lookup"><span data-stu-id="f683b-439">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="f683b-440">444</span><span class="sxs-lookup"><span data-stu-id="f683b-440">444</span></span></p></td>
<td><p><span data-ttu-id="f683b-441">HTTPS</span><span class="sxs-lookup"><span data-stu-id="f683b-441">HTTPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f683b-442">디렉터 부하 분산 장치</span><span class="sxs-lookup"><span data-stu-id="f683b-442">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="f683b-443">5061</span><span class="sxs-lookup"><span data-stu-id="f683b-443">5061</span></span></p></td>
<td><p><span data-ttu-id="f683b-444">NET.TCP</span><span class="sxs-lookup"><span data-stu-id="f683b-444">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f683b-445">디렉터 부하 분산 장치</span><span class="sxs-lookup"><span data-stu-id="f683b-445">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="f683b-446">4443</span><span class="sxs-lookup"><span data-stu-id="f683b-446">4443</span></span></p></td>
<td><p><span data-ttu-id="f683b-447">HTTPS (역방향 프록시)</span><span class="sxs-lookup"><span data-stu-id="f683b-447">HTTPS (from reverse proxy)</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="f683b-448">DNS 부하 분산을 사용 하는 프런트 엔드 풀 및 디렉터 풀에도 하드웨어 부하 분산 장치를 배포 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f683b-448">Your Front End pools and Director pools that use DNS load balancing also must have a hardware load balancer deployed.</span></span> <span data-ttu-id="f683b-449">다음 표에는 이러한 하드웨어 부하 분산 장치에서 열려 있어야 하는 포트가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f683b-449">The following table shows the ports that need to be open on these hardware load balancers.</span></span>

### <a name="hardware-load-balancer-ports-if-using-dns-load-balancing"></a><span data-ttu-id="f683b-450">DNS 부하 분산을 사용 하는 경우 하드웨어 부하 분산 장치 포트</span><span class="sxs-lookup"><span data-stu-id="f683b-450">Hardware Load Balancer Ports if Using DNS Load Balancing</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f683b-451">부하 분산 장치</span><span class="sxs-lookup"><span data-stu-id="f683b-451">Load Balancer</span></span></th>
<th><span data-ttu-id="f683b-452">포트</span><span class="sxs-lookup"><span data-stu-id="f683b-452">Port</span></span></th>
<th><span data-ttu-id="f683b-453">프로토콜별</span><span class="sxs-lookup"><span data-stu-id="f683b-453">Protocol</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f683b-454">프런트 엔드 서버 부하 분산 장치</span><span class="sxs-lookup"><span data-stu-id="f683b-454">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="f683b-455">80</span><span class="sxs-lookup"><span data-stu-id="f683b-455">80</span></span></p></td>
<td><p><span data-ttu-id="f683b-456">HTTP</span><span class="sxs-lookup"><span data-stu-id="f683b-456">HTTP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f683b-457">프런트 엔드 서버 부하 분산 장치</span><span class="sxs-lookup"><span data-stu-id="f683b-457">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="f683b-458">443</span><span class="sxs-lookup"><span data-stu-id="f683b-458">443</span></span></p></td>
<td><p><span data-ttu-id="f683b-459">HTTPS</span><span class="sxs-lookup"><span data-stu-id="f683b-459">HTTPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f683b-460">프런트 엔드 서버 부하 분산 장치</span><span class="sxs-lookup"><span data-stu-id="f683b-460">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="f683b-461">8080</span><span class="sxs-lookup"><span data-stu-id="f683b-461">8080</span></span></p></td>
<td><p><span data-ttu-id="f683b-462">TCP-프런트 엔드 서버에서 루트 인증서의 클라이언트 및 장치 검색-NTLM으로 인증 된 클라이언트 및 장치</span><span class="sxs-lookup"><span data-stu-id="f683b-462">TCP - Client and device retrieval of root certificate from Front End Server – clients and devices authenticated by NTLM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f683b-463">프런트 엔드 서버 부하 분산 장치</span><span class="sxs-lookup"><span data-stu-id="f683b-463">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="f683b-464">4443</span><span class="sxs-lookup"><span data-stu-id="f683b-464">4443</span></span></p></td>
<td><p><span data-ttu-id="f683b-465">HTTPS (역방향 프록시)</span><span class="sxs-lookup"><span data-stu-id="f683b-465">HTTPS (from reverse proxy)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f683b-466">디렉터 부하 분산 장치</span><span class="sxs-lookup"><span data-stu-id="f683b-466">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="f683b-467">443</span><span class="sxs-lookup"><span data-stu-id="f683b-467">443</span></span></p></td>
<td><p><span data-ttu-id="f683b-468">HTTPS</span><span class="sxs-lookup"><span data-stu-id="f683b-468">HTTPS</span></span></p></td>
</tr>
<tr class="even">
<td> </td>
<td> </td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f683b-469">디렉터 부하 분산 장치</span><span class="sxs-lookup"><span data-stu-id="f683b-469">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="f683b-470">4443</span><span class="sxs-lookup"><span data-stu-id="f683b-470">4443</span></span></p></td>
<td><p><span data-ttu-id="f683b-471">HTTPS (역방향 프록시)</span><span class="sxs-lookup"><span data-stu-id="f683b-471">HTTPS (from reverse proxy)</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="required-client-ports"></a><span data-ttu-id="f683b-472">필수 클라이언트 포트</span><span class="sxs-lookup"><span data-stu-id="f683b-472">Required Client Ports</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f683b-473">요소가</span><span class="sxs-lookup"><span data-stu-id="f683b-473">Component</span></span></th>
<th><span data-ttu-id="f683b-474">포트</span><span class="sxs-lookup"><span data-stu-id="f683b-474">Port</span></span></th>
<th><span data-ttu-id="f683b-475">프로토콜별</span><span class="sxs-lookup"><span data-stu-id="f683b-475">Protocol</span></span></th>
<th><span data-ttu-id="f683b-476">상속자</span><span class="sxs-lookup"><span data-stu-id="f683b-476">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f683b-477">클라이언트</span><span class="sxs-lookup"><span data-stu-id="f683b-477">Clients</span></span></p></td>
<td><p><span data-ttu-id="f683b-478">67/68</span><span class="sxs-lookup"><span data-stu-id="f683b-478">67/68</span></span></p></td>
<td><p><span data-ttu-id="f683b-479">서버의</span><span class="sxs-lookup"><span data-stu-id="f683b-479">DHCP</span></span></p></td>
<td><p><span data-ttu-id="f683b-480">Lync Server에서 등록자 FQDN을 찾는 데 사용 됩니다 (즉, DNS SRV에 장애가 발생 하 여 수동 설정이 구성 되지 않은 경우).</span><span class="sxs-lookup"><span data-stu-id="f683b-480">Used by Lync Server to find the Registrar FQDN (that is, if DNS SRV fails and manual settings are not configured).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f683b-481">클라이언트</span><span class="sxs-lookup"><span data-stu-id="f683b-481">Clients</span></span></p></td>
<td><p><span data-ttu-id="f683b-482">443</span><span class="sxs-lookup"><span data-stu-id="f683b-482">443</span></span></p></td>
<td><p><span data-ttu-id="f683b-483">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="f683b-483">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="f683b-484">외부 사용자 액세스를 위한 클라이언트 대 서버 SIP 트래픽에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f683b-484">Used for client-to-server SIP traffic for external user access.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f683b-485">클라이언트</span><span class="sxs-lookup"><span data-stu-id="f683b-485">Clients</span></span></p></td>
<td><p><span data-ttu-id="f683b-486">443</span><span class="sxs-lookup"><span data-stu-id="f683b-486">443</span></span></p></td>
<td><p><span data-ttu-id="f683b-487">TCP (PSOM/TLS)</span><span class="sxs-lookup"><span data-stu-id="f683b-487">TCP (PSOM/TLS)</span></span></p></td>
<td><p><span data-ttu-id="f683b-488">웹 회의 세션에 대 한 외부 사용자 액세스에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f683b-488">Used for external user access to web conferencing sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f683b-489">클라이언트</span><span class="sxs-lookup"><span data-stu-id="f683b-489">Clients</span></span></p></td>
<td><p><span data-ttu-id="f683b-490">443</span><span class="sxs-lookup"><span data-stu-id="f683b-490">443</span></span></p></td>
<td><p><span data-ttu-id="f683b-491">TCP (STUN/MSTURN)</span><span class="sxs-lookup"><span data-stu-id="f683b-491">TCP (STUN/MSTURN)</span></span></p></td>
<td><p><span data-ttu-id="f683b-492">A/V 세션 및 미디어 (TCP)에 대 한 외부 사용자 액세스에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f683b-492">Used for external user access to A/V sessions and media (TCP)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f683b-493">클라이언트</span><span class="sxs-lookup"><span data-stu-id="f683b-493">Clients</span></span></p></td>
<td><p><span data-ttu-id="f683b-494">3478</span><span class="sxs-lookup"><span data-stu-id="f683b-494">3478</span></span></p></td>
<td><p><span data-ttu-id="f683b-495">UDP (STUN/MSTURN)</span><span class="sxs-lookup"><span data-stu-id="f683b-495">UDP (STUN/MSTURN)</span></span></p></td>
<td><p><span data-ttu-id="f683b-496">A/V 세션 및 미디어 (UDP)에 대 한 외부 사용자 액세스에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f683b-496">Used for external user access to A/V sessions and media (UDP)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f683b-497">클라이언트</span><span class="sxs-lookup"><span data-stu-id="f683b-497">Clients</span></span></p></td>
<td><p><span data-ttu-id="f683b-498">5061</span><span class="sxs-lookup"><span data-stu-id="f683b-498">5061</span></span></p></td>
<td><p><span data-ttu-id="f683b-499">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="f683b-499">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="f683b-500">외부 사용자 액세스를 위한 클라이언트 대 서버 SIP 트래픽에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f683b-500">Used for client-to-server SIP traffic for external user access.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f683b-501">클라이언트</span><span class="sxs-lookup"><span data-stu-id="f683b-501">Clients</span></span></p></td>
<td><p><span data-ttu-id="f683b-502">6891-6901</span><span class="sxs-lookup"><span data-stu-id="f683b-502">6891-6901</span></span></p></td>
<td><p><span data-ttu-id="f683b-503">NET.TCP</span><span class="sxs-lookup"><span data-stu-id="f683b-503">TCP</span></span></p></td>
<td><p><span data-ttu-id="f683b-504">Lync 클라이언트와 이전 클라이언트 간의 파일 전송 (Microsoft Office Communications Server 2007 R2, Microsoft Office Communications Server 2007 및 Live Communications Server 2005의 클라이언트)에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f683b-504">Used for file transfer between Lync clients and previous clients (clients of Microsoft Office Communications Server 2007 R2, Microsoft Office Communications Server 2007, and Live Communications Server 2005).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f683b-505">클라이언트</span><span class="sxs-lookup"><span data-stu-id="f683b-505">Clients</span></span></p></td>
<td><p><span data-ttu-id="f683b-506">1024-65535 \*</span><span class="sxs-lookup"><span data-stu-id="f683b-506">1024-65535 \*</span></span></p></td>
<td><p><span data-ttu-id="f683b-507">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="f683b-507">TCP/UDP</span></span></p></td>
<td><p><span data-ttu-id="f683b-508">오디오 포트 범위 (최소 20 개의 포트가 필요 함)</span><span class="sxs-lookup"><span data-stu-id="f683b-508">Audio port range (minimum of 20 ports required)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f683b-509">클라이언트</span><span class="sxs-lookup"><span data-stu-id="f683b-509">Clients</span></span></p></td>
<td><p><span data-ttu-id="f683b-510">1024-65535 \*</span><span class="sxs-lookup"><span data-stu-id="f683b-510">1024-65535 \*</span></span></p></td>
<td><p><span data-ttu-id="f683b-511">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="f683b-511">TCP/UDP</span></span></p></td>
<td><p><span data-ttu-id="f683b-512">비디오 포트 범위 (최소 20 개 포트 필요).</span><span class="sxs-lookup"><span data-stu-id="f683b-512">Video port range (minimum of 20 ports required).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f683b-513">클라이언트</span><span class="sxs-lookup"><span data-stu-id="f683b-513">Clients</span></span></p></td>
<td><p><span data-ttu-id="f683b-514">1024-65535 \*</span><span class="sxs-lookup"><span data-stu-id="f683b-514">1024-65535 \*</span></span></p></td>
<td><p><span data-ttu-id="f683b-515">NET.TCP</span><span class="sxs-lookup"><span data-stu-id="f683b-515">TCP</span></span></p></td>
<td><p><span data-ttu-id="f683b-516">피어 투 피어 파일 전송 (회의 파일 전송의 경우 클라이언트는 PSOM 사용).</span><span class="sxs-lookup"><span data-stu-id="f683b-516">Peer-to-peer file transfer (for conferencing file transfer, clients use PSOM).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f683b-517">클라이언트</span><span class="sxs-lookup"><span data-stu-id="f683b-517">Clients</span></span></p></td>
<td><p><span data-ttu-id="f683b-518">1024-65535 \*</span><span class="sxs-lookup"><span data-stu-id="f683b-518">1024-65535 \*</span></span></p></td>
<td><p><span data-ttu-id="f683b-519">NET.TCP</span><span class="sxs-lookup"><span data-stu-id="f683b-519">TCP</span></span></p></td>
<td><p><span data-ttu-id="f683b-520">응용 프로그램 공유</span><span class="sxs-lookup"><span data-stu-id="f683b-520">Application sharing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f683b-521">Aastra 6721ip 공용 지역 전화</span><span class="sxs-lookup"><span data-stu-id="f683b-521">Aastra 6721ip common area phone</span></span></p>
<p><span data-ttu-id="f683b-522">Aastra 6725ip 일반 전화기</span><span class="sxs-lookup"><span data-stu-id="f683b-522">Aastra 6725ip desk phone</span></span></p>
<p><span data-ttu-id="f683b-523">HP 4110 IP 전화 (공통 지역 전화)</span><span class="sxs-lookup"><span data-stu-id="f683b-523">HP 4110 IP Phone (common area phone)</span></span></p>
<p><span data-ttu-id="f683b-524">HP 4120 IP 전화기 (일반 전화기)</span><span class="sxs-lookup"><span data-stu-id="f683b-524">HP 4120 IP Phone (desk phone)</span></span></p>
<p><span data-ttu-id="f683b-525">Polycom CX500 IP 일반 지역 전화</span><span class="sxs-lookup"><span data-stu-id="f683b-525">Polycom CX500 IP common area phone</span></span></p>
<p><span data-ttu-id="f683b-526">Polycom CX600 IP 일반 전화기</span><span class="sxs-lookup"><span data-stu-id="f683b-526">Polycom CX600 IP desk phone</span></span></p>
<p><span data-ttu-id="f683b-527">Polycom CX700 IP 일반 전화기</span><span class="sxs-lookup"><span data-stu-id="f683b-527">Polycom CX700 IP desk phone</span></span></p>
<p><span data-ttu-id="f683b-528">Polycom CX3000 IP 컨퍼런스 전화</span><span class="sxs-lookup"><span data-stu-id="f683b-528">Polycom CX3000 IP conference phone</span></span></p></td>
<td><p><span data-ttu-id="f683b-529">67/68</span><span class="sxs-lookup"><span data-stu-id="f683b-529">67/68</span></span></p></td>
<td><p><span data-ttu-id="f683b-530">서버의</span><span class="sxs-lookup"><span data-stu-id="f683b-530">DHCP</span></span></p></td>
<td><p><span data-ttu-id="f683b-531">나열 된 디바이스에서 Lync Server 인증서, 프로비저닝 FQDN 및 등록자 FQDN을 찾는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f683b-531">Used by the listed devices to find the Lync Server certificate, provisioning FQDN, and Registrar FQDN.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="f683b-532">**\*** 이러한 미디어 형식에 대 한 특정 포트를 구성 하려면 CsConferencingConfiguration cmdlet (ClientMediaPortRangeEnabled, ClientMediaPort 및 ClientMediaPortRange parameters)을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f683b-532">**\*** To configure specific ports for these media types, use the CsConferencingConfiguration cmdlet (ClientMediaPortRangeEnabled, ClientMediaPort, and ClientMediaPortRange parameters).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f683b-533">Lync 클라이언트에 대 한 프로그램 설정에서는 클라이언트 컴퓨터에서 필요한 운영 체제 방화벽 예외를 자동으로 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f683b-533">The set programs for Lync clients automatically create the required operating-system firewall exceptions on the client computer.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="f683b-534">외부 사용자 액세스에 사용 되는 포트는 클라이언트가 조직의 방화벽을 통과 해야 하는 모든 시나리오 (예: 다른 조직에서 호스팅하는 외부 통신 또는 모임)에 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="f683b-534">The ports that are used for external user access are required for any scenario in which the client must traverse the organization’s firewall (for example, any external communications or meetings hosted by other organizations).</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

