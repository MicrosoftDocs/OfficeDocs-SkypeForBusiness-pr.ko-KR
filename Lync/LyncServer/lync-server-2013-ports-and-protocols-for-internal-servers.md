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
ms.openlocfilehash: 1001cce83d9b23125b177725c77715bd19a00e03
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724998"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="ports-and-protocols-for-internal-servers-in-lync-server-2013"></a><span data-ttu-id="955fb-102">Lync Server 2013의 내부 서버에 대 한 포트 및 프로토콜</span><span class="sxs-lookup"><span data-stu-id="955fb-102">Ports and protocols for internal servers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="955fb-103">_**마지막으로 수정한 주제:** 2016-04-06_</span><span class="sxs-lookup"><span data-stu-id="955fb-103">_**Topic Last Modified:** 2016-04-06_</span></span>

<span data-ttu-id="955fb-104">이 섹션에서는 서버, 부하 분산 장치 및 Lync Server 배포의 클라이언트에 사용 되는 포트와 프로토콜에 대해 간략하게 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="955fb-104">This section summarizes the ports and protocols used by servers, load balancers, and clients in a Lync Server deployment.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="955fb-105">1 ~ 1 통신에 참가 하는 Lync 및 Communicator 클라이언트는 종종 피어 투 피어 라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="955fb-105">Lync and Communicator clients when involved in a one to one communication, is often referred to as peer-to-peer.</span></span> <span data-ttu-id="955fb-106">기술적으로 두 클라이언트는 중앙의 IMMCU (지점 제어 단위)를 사용 하 여 일대일 대화로 통신 합니다.</span><span class="sxs-lookup"><span data-stu-id="955fb-106">Technically, the two clients are communicating in a one to one conversation, with the Instant Messaging multipoint control unit (IMMCU) in the middle.</span></span> <span data-ttu-id="955fb-107">IMMCU는 프런트 엔드 서버의 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="955fb-107">The IMMCU is a component of Front End Server.</span></span> <span data-ttu-id="955fb-108">필요한 통신 워크플로에 IMMCU를 배치 하면 프런트 엔드 서버에서 사용할 수 있는 통화 정보 기록 및 기타 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="955fb-108">Placing the IMMCU in the required communication workflow allows call detail recording and other features that the Front End Server enables.</span></span> <span data-ttu-id="955fb-109">클라이언트의 동적 원본 포트에서 프런트 엔드 서버 포트 TLS/TCP/5061으로 통신 하는 것으로 간주 됩니다 (권장 전송 계층 보안을 사용 하는 경우).</span><span class="sxs-lookup"><span data-stu-id="955fb-109">Communication is from a dynamic source port on the client to the Front End Server port TLS/TCP/5061 (assuming the use of the recommended transport layer security).</span></span> <span data-ttu-id="955fb-110">Lync Server와 IMMCU가 활성 상태이 고 사용할 수 있는 경우에만 피어 투 피어 통신 및 여러 파티 IM을 디자인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="955fb-110">By design, peer-to-peer communication (as well as multi-party IM) is possible only when Lync Server and the IMMCU is active and available.</span></span>



</div>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="955fb-111">포트 및 프로토콜 정보</span><span class="sxs-lookup"><span data-stu-id="955fb-111">Port and Protocol Details</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="955fb-112">Lync server가 방화벽에서 필요한 포트를 여는 경우에는 서버에서 Lync Server 서비스를 시작 하기 전에 Windows 방화벽이 실행 중 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="955fb-112">Windows Firewall must be running before you start the Lync Server services on a server, because that is when Lync Server opens the required ports in the firewall.</span></span>



</div>

<span data-ttu-id="955fb-113">Edge 구성 요소의 방화벽 구성에 대 한 자세한 내용은 [Lync Server 2013에 대 한 외부 A/V 방화벽 및 포트 요구 사항 결정](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="955fb-113">For details about firewall configuration for edge components, see [Determine external A/V firewall and port requirements for Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md).</span></span>

<span data-ttu-id="955fb-114">다음 표에는 각 내부 서버 역할에 열려 있어야 하는 포트가 나열 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="955fb-114">The following table lists the ports that need to be open on each internal server role.</span></span>

### <a name="required-server-ports-by-server-role"></a><span data-ttu-id="955fb-115">필요한 서버 포트 (서버 역할별)</span><span class="sxs-lookup"><span data-stu-id="955fb-115">Required Server Ports (by Server Role)</span></span>

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
<th><span data-ttu-id="955fb-116">서버 역할</span><span class="sxs-lookup"><span data-stu-id="955fb-116">Server role</span></span></th>
<th><span data-ttu-id="955fb-117">서비스 이름</span><span class="sxs-lookup"><span data-stu-id="955fb-117">Service name</span></span></th>
<th><span data-ttu-id="955fb-118">포트</span><span class="sxs-lookup"><span data-stu-id="955fb-118">Port</span></span></th>
<th><span data-ttu-id="955fb-119">프로토콜별</span><span class="sxs-lookup"><span data-stu-id="955fb-119">Protocol</span></span></th>
<th><span data-ttu-id="955fb-120">상속자</span><span class="sxs-lookup"><span data-stu-id="955fb-120">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="955fb-121">모든 서버</span><span class="sxs-lookup"><span data-stu-id="955fb-121">All Servers</span></span></p></td>
<td><p><span data-ttu-id="955fb-122">SQL 브라우저</span><span class="sxs-lookup"><span data-stu-id="955fb-122">SQL Browser</span></span></p></td>
<td><p><span data-ttu-id="955fb-123">1434</span><span class="sxs-lookup"><span data-stu-id="955fb-123">1434</span></span></p></td>
<td><p><span data-ttu-id="955fb-124">UDP</span><span class="sxs-lookup"><span data-stu-id="955fb-124">UDP</span></span></p></td>
<td><p><span data-ttu-id="955fb-125">중앙 관리 저장소 데이터베이스의 복제 된 로컬 복사본에 대 한 SQL 브라우저입니다.</span><span class="sxs-lookup"><span data-stu-id="955fb-125">SQL Browser for the local replicated copy of the Central Management Store database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="955fb-126">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="955fb-126">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="955fb-127">Lync Server 프런트 엔드 서비스</span><span class="sxs-lookup"><span data-stu-id="955fb-127">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="955fb-128">5060</span><span class="sxs-lookup"><span data-stu-id="955fb-128">5060</span></span></p></td>
<td><p><span data-ttu-id="955fb-129">NET.TCP</span><span class="sxs-lookup"><span data-stu-id="955fb-129">TCP</span></span></p></td>
<td><p><span data-ttu-id="955fb-130">필요에 따라 원격 통화 제어 서버와 같은 신뢰할 수 있는 서비스에 대 한 고정 경로에 대 한 표준 버전 서버 및 프런트 엔드 서버에서 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="955fb-130">Optionally used by Standard Edition servers and Front End Servers for static routes to trusted services, such as remote call control servers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="955fb-131">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="955fb-131">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="955fb-132">Lync Server 프런트 엔드 서비스</span><span class="sxs-lookup"><span data-stu-id="955fb-132">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="955fb-133">5061</span><span class="sxs-lookup"><span data-stu-id="955fb-133">5061</span></span></p></td>
<td><p><span data-ttu-id="955fb-134">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="955fb-134">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="955fb-135">서버와 클라이언트 (MTLS) 간의 SIP 통신 및 프런트 엔드 서버와 조정 서버 (MTLS) 간의 SIP 통신에 대 한 모든 내부 SIP 통신에 대 한 표준 버전 서버 및 프런트 엔드 풀에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="955fb-135">Used by Standard Edition servers and Front End pools for all internal SIP communications between servers (MTLS), for SIP communications between Server and Client (TLS) and for SIP communications between Front End Servers and Mediation Servers (MTLS).</span></span> <span data-ttu-id="955fb-136">모니터링 서버와 통신 하는 데도 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="955fb-136">Also used for communications with Monitoring Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="955fb-137">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="955fb-137">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="955fb-138">Lync Server 프런트 엔드 서비스</span><span class="sxs-lookup"><span data-stu-id="955fb-138">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="955fb-139">444</span><span class="sxs-lookup"><span data-stu-id="955fb-139">444</span></span></p></td>
<td><p><span data-ttu-id="955fb-140">HTTPS</span><span class="sxs-lookup"><span data-stu-id="955fb-140">HTTPS</span></span></p>
<p><span data-ttu-id="955fb-141">NET.TCP</span><span class="sxs-lookup"><span data-stu-id="955fb-141">TCP</span></span></p></td>
<td><p><span data-ttu-id="955fb-142">포커스 (회의 상태를 관리 하는 Lync Server 구성 요소)와 개별 서버 간의 HTTPS 통신에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="955fb-142">Used for HTTPS communication between the Focus (the Lync Server component that manages conference state) and the individual servers.</span></span></p>
<p><span data-ttu-id="955fb-143">이 포트는 Survivable Branch 기기 및 프런트 엔드 서버 간의 TCP 통신에도 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="955fb-143">This port is also used for TCP communication between Survivable Branch Appliances and Front End Servers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="955fb-144">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="955fb-144">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="955fb-145">Lync Server 프런트 엔드 서비스</span><span class="sxs-lookup"><span data-stu-id="955fb-145">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="955fb-146">135</span><span class="sxs-lookup"><span data-stu-id="955fb-146">135</span></span></p></td>
<td><p><span data-ttu-id="955fb-147">DCOM 및 RPC (원격 프로시저 호출)</span><span class="sxs-lookup"><span data-stu-id="955fb-147">DCOM and remote procedure call (RPC)</span></span></p></td>
<td><p><span data-ttu-id="955fb-148">사용자 이동, 사용자 복제기 동기화, 주소록 동기화 등의 DCOM 기반 작업에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="955fb-148">Used for DCOM based operations such as Moving Users, User Replicator Synchronization, and Address Book Synchronization.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="955fb-149">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="955fb-149">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="955fb-150">Lync Server 메신저 회의 서비스</span><span class="sxs-lookup"><span data-stu-id="955fb-150">Lync Server IM Conferencing service</span></span></p></td>
<td><p><span data-ttu-id="955fb-151">5062</span><span class="sxs-lookup"><span data-stu-id="955fb-151">5062</span></span></p></td>
<td><p><span data-ttu-id="955fb-152">NET.TCP</span><span class="sxs-lookup"><span data-stu-id="955fb-152">TCP</span></span></p></td>
<td><p><span data-ttu-id="955fb-153">인스턴트 메시징 (IM) 회의에 들어오는 SIP 요청에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="955fb-153">Used for incoming SIP requests for instant messaging (IM) conferencing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="955fb-154">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="955fb-154">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="955fb-155">Lync Server 웹 회의 서비스</span><span class="sxs-lookup"><span data-stu-id="955fb-155">Lync Server Web Conferencing service</span></span></p></td>
<td><p><span data-ttu-id="955fb-156">8057</span><span class="sxs-lookup"><span data-stu-id="955fb-156">8057</span></span></p></td>
<td><p><span data-ttu-id="955fb-157">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="955fb-157">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="955fb-158">클라이언트의 PSOM (영구 공유 개체 모델) 연결을 수신 대기 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="955fb-158">Used to listen for Persistent Shared Object Model (PSOM) connections from client.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="955fb-159">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="955fb-159">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="955fb-160">Lync Server 웹 회의 호환성 서비스</span><span class="sxs-lookup"><span data-stu-id="955fb-160">Lync Server Web Conferencing Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="955fb-161">8058</span><span class="sxs-lookup"><span data-stu-id="955fb-161">8058</span></span></p></td>
<td><p><span data-ttu-id="955fb-162">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="955fb-162">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="955fb-163">Live Meeting 클라이언트 및 이전 버전의 Lync Server에서 영구 공유 개체 모델 (PSOM) 연결을 수신 대기 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="955fb-163">Used to listen for Persistent Shared Object Model (PSOM) connections from the Live Meeting client and previous versions of Lync Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="955fb-164">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="955fb-164">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="955fb-165">Lync Server 오디오/비디오 회의 서비스</span><span class="sxs-lookup"><span data-stu-id="955fb-165">Lync Server Audio/Video Conferencing service</span></span></p></td>
<td><p><span data-ttu-id="955fb-166">5063</span><span class="sxs-lookup"><span data-stu-id="955fb-166">5063</span></span></p></td>
<td><p><span data-ttu-id="955fb-167">NET.TCP</span><span class="sxs-lookup"><span data-stu-id="955fb-167">TCP</span></span></p></td>
<td><p><span data-ttu-id="955fb-168">오디오/비디오 (A/V) 회의에 대 한 들어오는 SIP 요청에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="955fb-168">Used for incoming SIP requests for audio/video (A/V) conferencing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="955fb-169">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="955fb-169">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="955fb-170">Lync Server 오디오/비디오 회의 서비스</span><span class="sxs-lookup"><span data-stu-id="955fb-170">Lync Server Audio/Video Conferencing service</span></span></p></td>
<td><p><span data-ttu-id="955fb-171">57501-65535</span><span class="sxs-lookup"><span data-stu-id="955fb-171">57501-65535</span></span></p></td>
<td><p><span data-ttu-id="955fb-172">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="955fb-172">TCP/UDP</span></span></p></td>
<td><p><span data-ttu-id="955fb-173">비디오 회의에 사용 되는 미디어 포트 범위</span><span class="sxs-lookup"><span data-stu-id="955fb-173">Media port range used for video conferencing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="955fb-174">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="955fb-174">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="955fb-175">Lync Server 웹 호환성 서비스</span><span class="sxs-lookup"><span data-stu-id="955fb-175">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="955fb-176">80</span><span class="sxs-lookup"><span data-stu-id="955fb-176">80</span></span></p></td>
<td><p><span data-ttu-id="955fb-177">HTTP</span><span class="sxs-lookup"><span data-stu-id="955fb-177">HTTP</span></span></p></td>
<td><p><span data-ttu-id="955fb-178">HTTPS를 사용 하지 않을 때 프런트 엔드 서버에서 웹 팜 Fqdn (IIS 웹 구성 요소에 사용 되는 Url)으로 통신 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="955fb-178">Used for communication from Front End Servers to the web farm FQDNs (the URLs used by IIS web components) when HTTPS is not used.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="955fb-179">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="955fb-179">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="955fb-180">Lync Server 웹 호환성 서비스</span><span class="sxs-lookup"><span data-stu-id="955fb-180">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="955fb-181">443</span><span class="sxs-lookup"><span data-stu-id="955fb-181">443</span></span></p></td>
<td><p><span data-ttu-id="955fb-182">HTTPS</span><span class="sxs-lookup"><span data-stu-id="955fb-182">HTTPS</span></span></p></td>
<td><p><span data-ttu-id="955fb-183">프런트 엔드 서버에서 웹 팜 Fqdn으로 통신 하는 데 사용 됩니다 (IIS 웹 구성 요소에 사용 되는 Url).</span><span class="sxs-lookup"><span data-stu-id="955fb-183">Used for communication from Front End Servers to the web farm FQDNs (the URLs used by IIS web components).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="955fb-184">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="955fb-184">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="955fb-185">Lync Server 웹 호환성 서비스</span><span class="sxs-lookup"><span data-stu-id="955fb-185">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="955fb-186">8080</span><span class="sxs-lookup"><span data-stu-id="955fb-186">8080</span></span></p></td>
<td><p><span data-ttu-id="955fb-187">TCP 및 HTTP</span><span class="sxs-lookup"><span data-stu-id="955fb-187">TCP and HTTP</span></span></p></td>
<td><p><span data-ttu-id="955fb-188">외부 액세스를 위한 웹 구성 요소에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="955fb-188">Used by web components for external access.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="955fb-189">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="955fb-189">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="955fb-190">웹 서버 구성 요소</span><span class="sxs-lookup"><span data-stu-id="955fb-190">Web server component</span></span></p></td>
<td><p><span data-ttu-id="955fb-191">4443</span><span class="sxs-lookup"><span data-stu-id="955fb-191">4443</span></span></p></td>
<td><p><span data-ttu-id="955fb-192">HTTPS</span><span class="sxs-lookup"><span data-stu-id="955fb-192">HTTPS</span></span></p></td>
<td><p><span data-ttu-id="955fb-193">자동 검색 로그인을 위한 HTTPS (역방향 프록시) 및 HTTPS 프런트 엔드 풀 간 통신</span><span class="sxs-lookup"><span data-stu-id="955fb-193">HTTPS (from Reverse Proxy) and HTTPS Front End inter-pool communications for Autodiscover sign-in.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="955fb-194">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="955fb-194">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="955fb-195">웹 서버 구성 요소</span><span class="sxs-lookup"><span data-stu-id="955fb-195">Web server component</span></span></p></td>
<td><p><span data-ttu-id="955fb-196">8060</span><span class="sxs-lookup"><span data-stu-id="955fb-196">8060</span></span></p></td>
<td><p><span data-ttu-id="955fb-197">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="955fb-197">TCP (MTLS)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="955fb-198">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="955fb-198">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="955fb-199">웹 서버 구성 요소</span><span class="sxs-lookup"><span data-stu-id="955fb-199">Web server component</span></span></p></td>
<td><p><span data-ttu-id="955fb-200">8061</span><span class="sxs-lookup"><span data-stu-id="955fb-200">8061</span></span></p></td>
<td><p><span data-ttu-id="955fb-201">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="955fb-201">TCP (MTLS)</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="955fb-202">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="955fb-202">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="955fb-203">Mobility Services 구성 요소</span><span class="sxs-lookup"><span data-stu-id="955fb-203">Mobility Services component</span></span></p></td>
<td><p><span data-ttu-id="955fb-204">5086</span><span class="sxs-lookup"><span data-stu-id="955fb-204">5086</span></span></p></td>
<td><p><span data-ttu-id="955fb-205">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="955fb-205">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="955fb-206">모바일 서비스 내부 프로세스에서 사용 하는 SIP 포트</span><span class="sxs-lookup"><span data-stu-id="955fb-206">SIP port used by Mobility Services internal processes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="955fb-207">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="955fb-207">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="955fb-208">Mobility Services 구성 요소</span><span class="sxs-lookup"><span data-stu-id="955fb-208">Mobility Services component</span></span></p></td>
<td><p><span data-ttu-id="955fb-209">5087</span><span class="sxs-lookup"><span data-stu-id="955fb-209">5087</span></span></p></td>
<td><p><span data-ttu-id="955fb-210">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="955fb-210">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="955fb-211">모바일 서비스 내부 프로세스에서 사용 하는 SIP 포트</span><span class="sxs-lookup"><span data-stu-id="955fb-211">SIP port used by Mobility Services internal processes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="955fb-212">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="955fb-212">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="955fb-213">Mobility Services 구성 요소</span><span class="sxs-lookup"><span data-stu-id="955fb-213">Mobility Services component</span></span></p></td>
<td><p><span data-ttu-id="955fb-214">443</span><span class="sxs-lookup"><span data-stu-id="955fb-214">443</span></span></p></td>
<td><p><span data-ttu-id="955fb-215">HTTPS</span><span class="sxs-lookup"><span data-stu-id="955fb-215">HTTPS</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="955fb-216">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="955fb-216">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="955fb-217">Lync Server 회의 수행자 서비스 (전화 접속 회의)</span><span class="sxs-lookup"><span data-stu-id="955fb-217">Lync Server Conferencing Attendant service (dial-in conferencing)</span></span></p></td>
<td><p><span data-ttu-id="955fb-218">5064</span><span class="sxs-lookup"><span data-stu-id="955fb-218">5064</span></span></p></td>
<td><p><span data-ttu-id="955fb-219">NET.TCP</span><span class="sxs-lookup"><span data-stu-id="955fb-219">TCP</span></span></p></td>
<td><p><span data-ttu-id="955fb-220">전화 접속 회의에 대 한 수신 SIP 요청에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="955fb-220">Used for incoming SIP requests for dial-in conferencing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="955fb-221">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="955fb-221">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="955fb-222">Lync Server 회의 수행자 서비스 (전화 접속 회의)</span><span class="sxs-lookup"><span data-stu-id="955fb-222">Lync Server Conferencing Attendant service (dial-in conferencing)</span></span></p></td>
<td><p><span data-ttu-id="955fb-223">5072</span><span class="sxs-lookup"><span data-stu-id="955fb-223">5072</span></span></p></td>
<td><p><span data-ttu-id="955fb-224">NET.TCP</span><span class="sxs-lookup"><span data-stu-id="955fb-224">TCP</span></span></p></td>
<td><p><span data-ttu-id="955fb-225">전화 교환의 수신 SIP 요청에 사용 됨 (회의에 전화 걸기).</span><span class="sxs-lookup"><span data-stu-id="955fb-225">Used for incoming SIP requests for Attendant (dial in conferencing).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="955fb-226">Collocated 중재 서버도 실행 하는 프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="955fb-226">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="955fb-227">Lync Server 중재 서비스</span><span class="sxs-lookup"><span data-stu-id="955fb-227">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="955fb-228">5070</span><span class="sxs-lookup"><span data-stu-id="955fb-228">5070</span></span></p></td>
<td><p><span data-ttu-id="955fb-229">NET.TCP</span><span class="sxs-lookup"><span data-stu-id="955fb-229">TCP</span></span></p></td>
<td><p><span data-ttu-id="955fb-230">프런트 엔드 서버에서 중재 서버로 들어오는 요청에 대 한 조정 서버에서 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="955fb-230">Used by the Mediation Server for incoming requests from the Front End Server to the Mediation Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="955fb-231">Collocated 중재 서버도 실행 하는 프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="955fb-231">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="955fb-232">Lync Server 중재 서비스</span><span class="sxs-lookup"><span data-stu-id="955fb-232">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="955fb-233">5067</span><span class="sxs-lookup"><span data-stu-id="955fb-233">5067</span></span></p></td>
<td><p><span data-ttu-id="955fb-234">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="955fb-234">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="955fb-235">PSTN 게이트웨이에서 중재 서버로 들어오는 SIP 요청에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="955fb-235">Used for incoming SIP requests from the PSTN gateway to the Mediation Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="955fb-236">Collocated 중재 서버도 실행 하는 프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="955fb-236">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="955fb-237">Lync Server 중재 서비스</span><span class="sxs-lookup"><span data-stu-id="955fb-237">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="955fb-238">5068</span><span class="sxs-lookup"><span data-stu-id="955fb-238">5068</span></span></p></td>
<td><p><span data-ttu-id="955fb-239">NET.TCP</span><span class="sxs-lookup"><span data-stu-id="955fb-239">TCP</span></span></p></td>
<td><p><span data-ttu-id="955fb-240">PSTN 게이트웨이에서 중재 서버로 들어오는 SIP 요청에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="955fb-240">Used for incoming SIP requests from the PSTN gateway to the Mediation Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="955fb-241">Collocated 중재 서버도 실행 하는 프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="955fb-241">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="955fb-242">Lync Server 중재 서비스</span><span class="sxs-lookup"><span data-stu-id="955fb-242">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="955fb-243">5081</span><span class="sxs-lookup"><span data-stu-id="955fb-243">5081</span></span></p></td>
<td><p><span data-ttu-id="955fb-244">NET.TCP</span><span class="sxs-lookup"><span data-stu-id="955fb-244">TCP</span></span></p></td>
<td><p><span data-ttu-id="955fb-245">중재 서버에서 PSTN 게이트웨이로 보내는 SIP 요청에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="955fb-245">Used for outgoing SIP requests from the Mediation Server to the PSTN gateway.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="955fb-246">Collocated 중재 서버도 실행 하는 프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="955fb-246">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="955fb-247">Lync Server 중재 서비스</span><span class="sxs-lookup"><span data-stu-id="955fb-247">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="955fb-248">5082</span><span class="sxs-lookup"><span data-stu-id="955fb-248">5082</span></span></p></td>
<td><p><span data-ttu-id="955fb-249">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="955fb-249">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="955fb-250">중재 서버에서 PSTN 게이트웨이로 보내는 SIP 요청에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="955fb-250">Used for outgoing SIP requests from the Mediation Server to the PSTN gateway.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="955fb-251">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="955fb-251">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="955fb-252">Lync Server 응용 프로그램 공유 서비스</span><span class="sxs-lookup"><span data-stu-id="955fb-252">Lync Server Application Sharing service</span></span></p></td>
<td><p><span data-ttu-id="955fb-253">5065</span><span class="sxs-lookup"><span data-stu-id="955fb-253">5065</span></span></p></td>
<td><p><span data-ttu-id="955fb-254">NET.TCP</span><span class="sxs-lookup"><span data-stu-id="955fb-254">TCP</span></span></p></td>
<td><p><span data-ttu-id="955fb-255">응용 프로그램 공유에 대 한 수신 SIP 수신 요청에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="955fb-255">Used for incoming SIP listening requests for application sharing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="955fb-256">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="955fb-256">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="955fb-257">Lync Server 응용 프로그램 공유 서비스</span><span class="sxs-lookup"><span data-stu-id="955fb-257">Lync Server Application Sharing service</span></span></p></td>
<td><p><span data-ttu-id="955fb-258">49152-65535</span><span class="sxs-lookup"><span data-stu-id="955fb-258">49152-65535</span></span></p></td>
<td><p><span data-ttu-id="955fb-259">NET.TCP</span><span class="sxs-lookup"><span data-stu-id="955fb-259">TCP</span></span></p></td>
<td><p><span data-ttu-id="955fb-260">응용 프로그램 공유에 사용 되는 미디어 포트 범위입니다.</span><span class="sxs-lookup"><span data-stu-id="955fb-260">Media port range used for application sharing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="955fb-261">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="955fb-261">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="955fb-262">Lync 서버 회의 알림 서비스</span><span class="sxs-lookup"><span data-stu-id="955fb-262">Lync Server Conferencing Announcement service</span></span></p></td>
<td><p><span data-ttu-id="955fb-263">5073</span><span class="sxs-lookup"><span data-stu-id="955fb-263">5073</span></span></p></td>
<td><p><span data-ttu-id="955fb-264">NET.TCP</span><span class="sxs-lookup"><span data-stu-id="955fb-264">TCP</span></span></p></td>
<td><p><span data-ttu-id="955fb-265">Lync Server 회의 알림 서비스에 대 한 들어오는 SIP 요청에 사용 됩니다 (즉, 전화 접속 회의의 경우).</span><span class="sxs-lookup"><span data-stu-id="955fb-265">Used for incoming SIP requests for the Lync Server Conferencing Announcement service (that is, for dial-in conferencing).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="955fb-266">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="955fb-266">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="955fb-267">Lync Server 통화 공원 서비스</span><span class="sxs-lookup"><span data-stu-id="955fb-267">Lync Server Call Park service</span></span></p></td>
<td><p><span data-ttu-id="955fb-268">5075</span><span class="sxs-lookup"><span data-stu-id="955fb-268">5075</span></span></p></td>
<td><p><span data-ttu-id="955fb-269">NET.TCP</span><span class="sxs-lookup"><span data-stu-id="955fb-269">TCP</span></span></p></td>
<td><p><span data-ttu-id="955fb-270">통화 공원 응용 프로그램에 대 한 수신 SIP 요청에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="955fb-270">Used for incoming SIP requests for the Call Park application.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="955fb-271">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="955fb-271">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="955fb-272">Lync Server 오디오 테스트 서비스</span><span class="sxs-lookup"><span data-stu-id="955fb-272">Lync Server Audio Test service</span></span></p></td>
<td><p><span data-ttu-id="955fb-273">5076</span><span class="sxs-lookup"><span data-stu-id="955fb-273">5076</span></span></p></td>
<td><p><span data-ttu-id="955fb-274">NET.TCP</span><span class="sxs-lookup"><span data-stu-id="955fb-274">TCP</span></span></p></td>
<td><p><span data-ttu-id="955fb-275">오디오 테스트 서비스에 대 한 들어오는 SIP 요청에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="955fb-275">Used for incoming SIP requests for the Audio Test service.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="955fb-276">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="955fb-276">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="955fb-277">해당 없음</span><span class="sxs-lookup"><span data-stu-id="955fb-277">Not applicable</span></span></p></td>
<td><p><span data-ttu-id="955fb-278">5066</span><span class="sxs-lookup"><span data-stu-id="955fb-278">5066</span></span></p></td>
<td><p><span data-ttu-id="955fb-279">NET.TCP</span><span class="sxs-lookup"><span data-stu-id="955fb-279">TCP</span></span></p></td>
<td><p><span data-ttu-id="955fb-280">아웃 바운드 향상 9-1-1 (E9-1-1) 게이트웨이에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="955fb-280">Used for outbound Enhanced 9-1-1 (E9-1-1) gateway.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="955fb-281">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="955fb-281">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="955fb-282">Lync Server 응답 그룹 서비스</span><span class="sxs-lookup"><span data-stu-id="955fb-282">Lync Server Response Group service</span></span></p></td>
<td><p><span data-ttu-id="955fb-283">5071</span><span class="sxs-lookup"><span data-stu-id="955fb-283">5071</span></span></p></td>
<td><p><span data-ttu-id="955fb-284">NET.TCP</span><span class="sxs-lookup"><span data-stu-id="955fb-284">TCP</span></span></p></td>
<td><p><span data-ttu-id="955fb-285">응답 그룹 응용 프로그램에 대 한 들어오는 SIP 요청에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="955fb-285">Used for incoming SIP requests for the Response Group application.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="955fb-286">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="955fb-286">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="955fb-287">Lync Server 응답 그룹 서비스</span><span class="sxs-lookup"><span data-stu-id="955fb-287">Lync Server Response Group service</span></span></p></td>
<td><p><span data-ttu-id="955fb-288">8404</span><span class="sxs-lookup"><span data-stu-id="955fb-288">8404</span></span></p></td>
<td><p><span data-ttu-id="955fb-289">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="955fb-289">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="955fb-290">응답 그룹 응용 프로그램에 대 한 들어오는 SIP 요청에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="955fb-290">Used for incoming SIP requests for the Response Group application.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="955fb-291">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="955fb-291">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="955fb-292">Lync Server 대역폭 정책 서비스</span><span class="sxs-lookup"><span data-stu-id="955fb-292">Lync Server Bandwidth Policy Service</span></span></p></td>
<td><p><span data-ttu-id="955fb-293">5080</span><span class="sxs-lookup"><span data-stu-id="955fb-293">5080</span></span></p></td>
<td><p><span data-ttu-id="955fb-294">NET.TCP</span><span class="sxs-lookup"><span data-stu-id="955fb-294">TCP</span></span></p></td>
<td><p><span data-ttu-id="955fb-295">대역폭 정책 서비스에 의해 통화 허용 제어에 사용 됩니다 (A/V Edge TURN 트래픽).</span><span class="sxs-lookup"><span data-stu-id="955fb-295">Used for call admission control by the Bandwidth Policy service for A/V Edge TURN traffic.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="955fb-296">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="955fb-296">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="955fb-297">Lync Server 대역폭 정책 서비스</span><span class="sxs-lookup"><span data-stu-id="955fb-297">Lync Server Bandwidth Policy Service</span></span></p></td>
<td><p><span data-ttu-id="955fb-298">448</span><span class="sxs-lookup"><span data-stu-id="955fb-298">448</span></span></p></td>
<td><p><span data-ttu-id="955fb-299">NET.TCP</span><span class="sxs-lookup"><span data-stu-id="955fb-299">TCP</span></span></p></td>
<td><p><span data-ttu-id="955fb-300">Lync Server 대역폭 정책 서비스에의 한 통화 허용 제어에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="955fb-300">Used for call admission control by the Lync Server Bandwidth Policy Service.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="955fb-301">중앙 관리 저장소가 상주 하는 프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="955fb-301">Front End Servers where the Central Management store resides</span></span></p></td>
<td><p><span data-ttu-id="955fb-302">Lync Server 마스터 복제기 에이전트 서비스</span><span class="sxs-lookup"><span data-stu-id="955fb-302">Lync Server Master Replicator Agent service</span></span></p></td>
<td><p><span data-ttu-id="955fb-303">445</span><span class="sxs-lookup"><span data-stu-id="955fb-303">445</span></span></p></td>
<td><p><span data-ttu-id="955fb-304">NET.TCP</span><span class="sxs-lookup"><span data-stu-id="955fb-304">TCP</span></span></p></td>
<td><p><span data-ttu-id="955fb-305">중앙 관리 저장소의 구성 데이터를 Lync Server를 실행 하는 서버에 푸시하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="955fb-305">Used to push configuration data from the Central Management store to servers running Lync Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="955fb-306">모든 서버</span><span class="sxs-lookup"><span data-stu-id="955fb-306">All Servers</span></span></p></td>
<td><p><span data-ttu-id="955fb-307">SQL 브라우저</span><span class="sxs-lookup"><span data-stu-id="955fb-307">SQL Browser</span></span></p></td>
<td><p><span data-ttu-id="955fb-308">1434</span><span class="sxs-lookup"><span data-stu-id="955fb-308">1434</span></span></p></td>
<td><p><span data-ttu-id="955fb-309">UDP</span><span class="sxs-lookup"><span data-stu-id="955fb-309">UDP</span></span></p></td>
<td><p><span data-ttu-id="955fb-310">로컬 SQL Server 인스턴스에서 중앙 관리 저장소 데이터의 로컬 복제 복사본에 대 한 SQL 브라우저</span><span class="sxs-lookup"><span data-stu-id="955fb-310">SQL Browser for local replicated copy of Central Management store data in local SQL Server instance</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="955fb-311">모든 내부 서버</span><span class="sxs-lookup"><span data-stu-id="955fb-311">All internal servers</span></span></p></td>
<td><p><span data-ttu-id="955fb-312">다양 한</span><span class="sxs-lookup"><span data-stu-id="955fb-312">Various</span></span></p></td>
<td><p><span data-ttu-id="955fb-313">49152-57500</span><span class="sxs-lookup"><span data-stu-id="955fb-313">49152-57500</span></span></p></td>
<td><p><span data-ttu-id="955fb-314">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="955fb-314">TCP/UDP</span></span></p></td>
<td><p><span data-ttu-id="955fb-315">모든 내부 서버에서 오디오 회의에 사용 되는 미디어 포트 범위</span><span class="sxs-lookup"><span data-stu-id="955fb-315">Media port range used for audio conferencing on all internal servers.</span></span> <span data-ttu-id="955fb-316">오디오를 종료 하는 모든 서버 (Lync Server 회의 수행자 서비스, Lync server 회의 알림 서비스, lync Server 오디오/비디오 회의 서비스의 경우) 및 중재 서버에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="955fb-316">Used by all servers that terminate audio: Front End Servers (for Lync Server Conferencing Attendant service, Lync Server Conferencing Announcement service, and Lync Server Audio/Video Conferencing service), and Mediation Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="955fb-317">Office Web Apps 서버</span><span class="sxs-lookup"><span data-stu-id="955fb-317">Office Web Apps Servers</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="955fb-318">443</span><span class="sxs-lookup"><span data-stu-id="955fb-318">443</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="955fb-319">Lync Server 2013에서 Office Web Apps 서버에 연결 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="955fb-319">Used by Lync Server 2013 to connect to Office Web Apps Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="955fb-320">이사</span><span class="sxs-lookup"><span data-stu-id="955fb-320">Directors</span></span></p></td>
<td><p><span data-ttu-id="955fb-321">Lync Server 프런트 엔드 서비스</span><span class="sxs-lookup"><span data-stu-id="955fb-321">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="955fb-322">5060</span><span class="sxs-lookup"><span data-stu-id="955fb-322">5060</span></span></p></td>
<td><p><span data-ttu-id="955fb-323">NET.TCP</span><span class="sxs-lookup"><span data-stu-id="955fb-323">TCP</span></span></p></td>
<td><p><span data-ttu-id="955fb-324">필요에 따라 원격 통화 제어 서버와 같은 신뢰할 수 있는 서비스에 대 한 고정 경로에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="955fb-324">Optionally used for static routes to trusted services, such as remote call control servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="955fb-325">이사</span><span class="sxs-lookup"><span data-stu-id="955fb-325">Directors</span></span></p></td>
<td><p><span data-ttu-id="955fb-326">Lync Server 프런트 엔드 서비스</span><span class="sxs-lookup"><span data-stu-id="955fb-326">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="955fb-327">444</span><span class="sxs-lookup"><span data-stu-id="955fb-327">444</span></span></p></td>
<td><p><span data-ttu-id="955fb-328">HTTPS</span><span class="sxs-lookup"><span data-stu-id="955fb-328">HTTPS</span></span></p>
<p><span data-ttu-id="955fb-329">NET.TCP</span><span class="sxs-lookup"><span data-stu-id="955fb-329">TCP</span></span></p></td>
<td><p><span data-ttu-id="955fb-330">프론트 엔드 및 디렉터 간의 서버 간 통신.</span><span class="sxs-lookup"><span data-stu-id="955fb-330">Inter-server communication between Front End and Director.</span></span> <span data-ttu-id="955fb-331">또한 클라이언트 인증서가 프런트 엔드 서버로 게시 되거나 클라이언트 인증서가 이미 게시 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="955fb-331">Additionally, client certificate publish (to Front End Servers) or validate if the client certificate has already been published.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="955fb-332">이사</span><span class="sxs-lookup"><span data-stu-id="955fb-332">Directors</span></span></p></td>
<td><p><span data-ttu-id="955fb-333">Lync Server 웹 호환성 서비스</span><span class="sxs-lookup"><span data-stu-id="955fb-333">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="955fb-334">80</span><span class="sxs-lookup"><span data-stu-id="955fb-334">80</span></span></p></td>
<td><p><span data-ttu-id="955fb-335">NET.TCP</span><span class="sxs-lookup"><span data-stu-id="955fb-335">TCP</span></span></p></td>
<td><p><span data-ttu-id="955fb-336">디렉터에서 웹 팜 Fqdn으로 초기 통신 하는 데 사용 됩니다 (IIS 웹 구성 요소에 사용 되는 Url).</span><span class="sxs-lookup"><span data-stu-id="955fb-336">Used for initial communication from Directors to the web farm FQDNs (the URLs used by IIS web components).</span></span> <span data-ttu-id="955fb-337">정상 작업에서 포트 443 및 프로토콜 유형 TCP를 사용 하 여 HTTPS 트래픽으로 전환 합니다.</span><span class="sxs-lookup"><span data-stu-id="955fb-337">In normal operation, will switch to HTTPS traffic, using port 443 and protocol type TCP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="955fb-338">이사</span><span class="sxs-lookup"><span data-stu-id="955fb-338">Directors</span></span></p></td>
<td><p><span data-ttu-id="955fb-339">Lync Server 웹 호환성 서비스</span><span class="sxs-lookup"><span data-stu-id="955fb-339">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="955fb-340">443</span><span class="sxs-lookup"><span data-stu-id="955fb-340">443</span></span></p></td>
<td><p><span data-ttu-id="955fb-341">HTTPS</span><span class="sxs-lookup"><span data-stu-id="955fb-341">HTTPS</span></span></p></td>
<td><p><span data-ttu-id="955fb-342">디렉터에서 웹 팜 Fqdn으로 통신 하는 데 사용 됩니다 (IIS 웹 구성 요소에 사용 되는 Url).</span><span class="sxs-lookup"><span data-stu-id="955fb-342">Used for communication from Directors to the web farm FQDNs (the URLs used by IIS web components).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="955fb-343">이사</span><span class="sxs-lookup"><span data-stu-id="955fb-343">Directors</span></span></p></td>
<td><p><span data-ttu-id="955fb-344">Lync Server 프런트 엔드 서비스</span><span class="sxs-lookup"><span data-stu-id="955fb-344">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="955fb-345">5061</span><span class="sxs-lookup"><span data-stu-id="955fb-345">5061</span></span></p></td>
<td><p><span data-ttu-id="955fb-346">NET.TCP</span><span class="sxs-lookup"><span data-stu-id="955fb-346">TCP</span></span></p></td>
<td><p><span data-ttu-id="955fb-347">서버 간 내부 통신 및 클라이언트 연결에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="955fb-347">Used for internal communications between servers and for client connections.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="955fb-348">중재 서버</span><span class="sxs-lookup"><span data-stu-id="955fb-348">Mediation Servers</span></span></p></td>
<td><p><span data-ttu-id="955fb-349">Lync Server 중재 서비스</span><span class="sxs-lookup"><span data-stu-id="955fb-349">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="955fb-350">5070</span><span class="sxs-lookup"><span data-stu-id="955fb-350">5070</span></span></p></td>
<td><p><span data-ttu-id="955fb-351">NET.TCP</span><span class="sxs-lookup"><span data-stu-id="955fb-351">TCP</span></span></p></td>
<td><p><span data-ttu-id="955fb-352">프런트 엔드 서버에서 들어오는 요청에 대해 조정 서버에서 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="955fb-352">Used by the Mediation Server for incoming requests from the Front End Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="955fb-353">중재 서버</span><span class="sxs-lookup"><span data-stu-id="955fb-353">Mediation Servers</span></span></p></td>
<td><p><span data-ttu-id="955fb-354">Lync Server 중재 서비스</span><span class="sxs-lookup"><span data-stu-id="955fb-354">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="955fb-355">5067</span><span class="sxs-lookup"><span data-stu-id="955fb-355">5067</span></span></p></td>
<td><p><span data-ttu-id="955fb-356">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="955fb-356">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="955fb-357">PSTN 게이트웨이에서 들어오는 SIP 요청에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="955fb-357">Used for incoming SIP requests from the PSTN gateway.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="955fb-358">중재 서버</span><span class="sxs-lookup"><span data-stu-id="955fb-358">Mediation Servers</span></span></p></td>
<td><p><span data-ttu-id="955fb-359">Lync Server 중재 서비스</span><span class="sxs-lookup"><span data-stu-id="955fb-359">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="955fb-360">5068</span><span class="sxs-lookup"><span data-stu-id="955fb-360">5068</span></span></p></td>
<td><p><span data-ttu-id="955fb-361">NET.TCP</span><span class="sxs-lookup"><span data-stu-id="955fb-361">TCP</span></span></p></td>
<td><p><span data-ttu-id="955fb-362">PSTN 게이트웨이에서 들어오는 SIP 요청에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="955fb-362">Used for incoming SIP requests from the PSTN gateway.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="955fb-363">중재 서버</span><span class="sxs-lookup"><span data-stu-id="955fb-363">Mediation Servers</span></span></p></td>
<td><p><span data-ttu-id="955fb-364">Lync Server 중재 서비스</span><span class="sxs-lookup"><span data-stu-id="955fb-364">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="955fb-365">5070</span><span class="sxs-lookup"><span data-stu-id="955fb-365">5070</span></span></p></td>
<td><p><span data-ttu-id="955fb-366">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="955fb-366">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="955fb-367">프런트 엔드 서버의 SIP 요청에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="955fb-367">Used for SIP requests from the Front End Servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="955fb-368">영구 채팅 프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="955fb-368">Persistent Chat Front End Server</span></span></p></td>
<td><p><span data-ttu-id="955fb-369">영구 채팅 SIP</span><span class="sxs-lookup"><span data-stu-id="955fb-369">Persistent Chat SIP</span></span></p></td>
<td><p><span data-ttu-id="955fb-370">5041</span><span class="sxs-lookup"><span data-stu-id="955fb-370">5041</span></span></p></td>
<td><p><span data-ttu-id="955fb-371">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="955fb-371">TCP (MTLS)</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="955fb-372">영구 채팅 프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="955fb-372">Persistent Chat Front End Server</span></span></p></td>
<td><p><span data-ttu-id="955fb-373">WCF (Windows Communication Foundation) 영구 채팅</span><span class="sxs-lookup"><span data-stu-id="955fb-373">Persistent Chat Windows Communication Foundation (WCF)</span></span></p></td>
<td><p><span data-ttu-id="955fb-374">881</span><span class="sxs-lookup"><span data-stu-id="955fb-374">881</span></span></p></td>
<td><p><span data-ttu-id="955fb-375">TCP (TLS) 및 TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="955fb-375">TCP (TLS) and TCP (MTLS)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="955fb-376">영구 채팅 프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="955fb-376">Persistent Chat Front End Server</span></span></p></td>
<td><p><span data-ttu-id="955fb-377">영구 채팅 파일 전송 서비스</span><span class="sxs-lookup"><span data-stu-id="955fb-377">Persistent Chat File Transfer Service</span></span></p></td>
<td><p><span data-ttu-id="955fb-378">443</span><span class="sxs-lookup"><span data-stu-id="955fb-378">443</span></span></p></td>
<td><p><span data-ttu-id="955fb-379">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="955fb-379">TCP (TLS)</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="955fb-380">일부 원격 통화 제어 시나리오는 프런트 엔드 서버 또는 디렉터와 PBX 간의 TCP 연결이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="955fb-380">Some remote call control scenarios require a TCP connection between the Front End Server or Director and the PBX.</span></span> <span data-ttu-id="955fb-381">Lync Server는 더 이상 TCP 포트 5060를 사용 하지 않지만 원격 통화 제어 배포 중에는 RCC 회선 서버 FQDN을 프런트 엔드 서버 또는 디렉터가 PBX 시스템에 연결 하는 데 사용할 TCP 포트와 연결 하는 신뢰할 수 있는 서버 구성을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="955fb-381">Although Lync Server no longer uses TCP port 5060, during remote call control deployment you create a trusted server configuration, which associates the RCC Line Server FQDN with the TCP port that the Front End Server or Director will use to connect to the PBX system.</span></span> <span data-ttu-id="955fb-382">자세한 내용은 Lync Server 관리 셸 설명서의 <STRONG>CsTrustedApplicationComputer</STRONG> cmdlet을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="955fb-382">For details, see the <STRONG>CsTrustedApplicationComputer</STRONG> cmdlet in the Lync Server Management Shell documentation.</span></span>



</div>

<span data-ttu-id="955fb-383">DNS 부하 분산이 아닌 하드웨어 로드 균형 조정만 사용 하는 풀의 경우 다음 표에는 하드웨어 로드 균형 조정기를 여는 데 필요한 포트가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="955fb-383">For your pools that use only hardware load balancing (not DNS load balancing), the following table shows the ports that need to open the hardware load balancers.</span></span>

### <a name="hardware-load-balancer-ports-if-using-only-hardware-load-balancing"></a><span data-ttu-id="955fb-384">하드웨어 부하 분산만 사용 하는 경우 하드웨어 부하 분산 장치 포트</span><span class="sxs-lookup"><span data-stu-id="955fb-384">Hardware Load Balancer Ports if Using Only Hardware Load Balancing</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="955fb-385">부하 분산 장치</span><span class="sxs-lookup"><span data-stu-id="955fb-385">Load Balancer</span></span></th>
<th><span data-ttu-id="955fb-386">포트</span><span class="sxs-lookup"><span data-stu-id="955fb-386">Port</span></span></th>
<th><span data-ttu-id="955fb-387">프로토콜별</span><span class="sxs-lookup"><span data-stu-id="955fb-387">Protocol</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="955fb-388">프런트 엔드 서버 부하 분산 장치</span><span class="sxs-lookup"><span data-stu-id="955fb-388">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="955fb-389">5061</span><span class="sxs-lookup"><span data-stu-id="955fb-389">5061</span></span></p></td>
<td><p><span data-ttu-id="955fb-390">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="955fb-390">TCP (TLS)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="955fb-391">프런트 엔드 서버 부하 분산 장치</span><span class="sxs-lookup"><span data-stu-id="955fb-391">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="955fb-392">444</span><span class="sxs-lookup"><span data-stu-id="955fb-392">444</span></span></p></td>
<td><p><span data-ttu-id="955fb-393">HTTPS</span><span class="sxs-lookup"><span data-stu-id="955fb-393">HTTPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="955fb-394">프런트 엔드 서버 부하 분산 장치</span><span class="sxs-lookup"><span data-stu-id="955fb-394">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="955fb-395">135</span><span class="sxs-lookup"><span data-stu-id="955fb-395">135</span></span></p></td>
<td><p><span data-ttu-id="955fb-396">DCOM 및 RPC (원격 프로시저 호출)</span><span class="sxs-lookup"><span data-stu-id="955fb-396">DCOM and remote procedure call (RPC)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="955fb-397">프런트 엔드 서버 부하 분산 장치</span><span class="sxs-lookup"><span data-stu-id="955fb-397">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="955fb-398">80</span><span class="sxs-lookup"><span data-stu-id="955fb-398">80</span></span></p></td>
<td><p><span data-ttu-id="955fb-399">HTTP</span><span class="sxs-lookup"><span data-stu-id="955fb-399">HTTP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="955fb-400">프런트 엔드 서버 부하 분산 장치</span><span class="sxs-lookup"><span data-stu-id="955fb-400">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="955fb-401">8080</span><span class="sxs-lookup"><span data-stu-id="955fb-401">8080</span></span></p></td>
<td><p><span data-ttu-id="955fb-402">TCP-프런트 엔드 서버에서 루트 인증서의 클라이언트 및 장치 검색-NTLM으로 인증 된 클라이언트 및 장치</span><span class="sxs-lookup"><span data-stu-id="955fb-402">TCP - Client and device retrieval of root certificate from Front End Server – clients and devices authenticated by NTLM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="955fb-403">프런트 엔드 서버 부하 분산 장치</span><span class="sxs-lookup"><span data-stu-id="955fb-403">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="955fb-404">443</span><span class="sxs-lookup"><span data-stu-id="955fb-404">443</span></span></p></td>
<td><p><span data-ttu-id="955fb-405">HTTPS</span><span class="sxs-lookup"><span data-stu-id="955fb-405">HTTPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="955fb-406">프런트 엔드 서버 부하 분산 장치</span><span class="sxs-lookup"><span data-stu-id="955fb-406">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="955fb-407">4443</span><span class="sxs-lookup"><span data-stu-id="955fb-407">4443</span></span></p></td>
<td><p><span data-ttu-id="955fb-408">HTTPS (역방향 프록시)</span><span class="sxs-lookup"><span data-stu-id="955fb-408">HTTPS (from reverse proxy)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="955fb-409">프런트 엔드 서버 부하 분산 장치</span><span class="sxs-lookup"><span data-stu-id="955fb-409">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="955fb-410">5072</span><span class="sxs-lookup"><span data-stu-id="955fb-410">5072</span></span></p></td>
<td><p><span data-ttu-id="955fb-411">NET.TCP</span><span class="sxs-lookup"><span data-stu-id="955fb-411">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="955fb-412">프런트 엔드 서버 부하 분산 장치</span><span class="sxs-lookup"><span data-stu-id="955fb-412">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="955fb-413">5073</span><span class="sxs-lookup"><span data-stu-id="955fb-413">5073</span></span></p></td>
<td><p><span data-ttu-id="955fb-414">NET.TCP</span><span class="sxs-lookup"><span data-stu-id="955fb-414">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="955fb-415">프런트 엔드 서버 부하 분산 장치</span><span class="sxs-lookup"><span data-stu-id="955fb-415">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="955fb-416">5075</span><span class="sxs-lookup"><span data-stu-id="955fb-416">5075</span></span></p></td>
<td><p><span data-ttu-id="955fb-417">NET.TCP</span><span class="sxs-lookup"><span data-stu-id="955fb-417">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="955fb-418">프런트 엔드 서버 부하 분산 장치</span><span class="sxs-lookup"><span data-stu-id="955fb-418">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="955fb-419">5076</span><span class="sxs-lookup"><span data-stu-id="955fb-419">5076</span></span></p></td>
<td><p><span data-ttu-id="955fb-420">NET.TCP</span><span class="sxs-lookup"><span data-stu-id="955fb-420">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="955fb-421">프런트 엔드 서버 부하 분산 장치</span><span class="sxs-lookup"><span data-stu-id="955fb-421">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="955fb-422">5071</span><span class="sxs-lookup"><span data-stu-id="955fb-422">5071</span></span></p></td>
<td><p><span data-ttu-id="955fb-423">NET.TCP</span><span class="sxs-lookup"><span data-stu-id="955fb-423">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="955fb-424">프런트 엔드 서버 부하 분산 장치</span><span class="sxs-lookup"><span data-stu-id="955fb-424">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="955fb-425">5080</span><span class="sxs-lookup"><span data-stu-id="955fb-425">5080</span></span></p></td>
<td><p><span data-ttu-id="955fb-426">NET.TCP</span><span class="sxs-lookup"><span data-stu-id="955fb-426">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="955fb-427">프런트 엔드 서버 부하 분산 장치</span><span class="sxs-lookup"><span data-stu-id="955fb-427">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="955fb-428">448</span><span class="sxs-lookup"><span data-stu-id="955fb-428">448</span></span></p></td>
<td><p><span data-ttu-id="955fb-429">NET.TCP</span><span class="sxs-lookup"><span data-stu-id="955fb-429">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="955fb-430">중재 서버 부하 분산 장치</span><span class="sxs-lookup"><span data-stu-id="955fb-430">Mediation Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="955fb-431">5070</span><span class="sxs-lookup"><span data-stu-id="955fb-431">5070</span></span></p></td>
<td><p><span data-ttu-id="955fb-432">NET.TCP</span><span class="sxs-lookup"><span data-stu-id="955fb-432">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="955fb-433">프런트 엔드 서버 부하 분산 장치 (풀에서 중재 서버도 실행 되는 경우)</span><span class="sxs-lookup"><span data-stu-id="955fb-433">Front End Server load balancer (if the pool also runs Mediation Server)</span></span></p></td>
<td><p><span data-ttu-id="955fb-434">5070</span><span class="sxs-lookup"><span data-stu-id="955fb-434">5070</span></span></p></td>
<td><p><span data-ttu-id="955fb-435">NET.TCP</span><span class="sxs-lookup"><span data-stu-id="955fb-435">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="955fb-436">디렉터 부하 분산 장치</span><span class="sxs-lookup"><span data-stu-id="955fb-436">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="955fb-437">443</span><span class="sxs-lookup"><span data-stu-id="955fb-437">443</span></span></p></td>
<td><p><span data-ttu-id="955fb-438">HTTPS</span><span class="sxs-lookup"><span data-stu-id="955fb-438">HTTPS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="955fb-439">디렉터 부하 분산 장치</span><span class="sxs-lookup"><span data-stu-id="955fb-439">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="955fb-440">444</span><span class="sxs-lookup"><span data-stu-id="955fb-440">444</span></span></p></td>
<td><p><span data-ttu-id="955fb-441">HTTPS</span><span class="sxs-lookup"><span data-stu-id="955fb-441">HTTPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="955fb-442">디렉터 부하 분산 장치</span><span class="sxs-lookup"><span data-stu-id="955fb-442">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="955fb-443">5061</span><span class="sxs-lookup"><span data-stu-id="955fb-443">5061</span></span></p></td>
<td><p><span data-ttu-id="955fb-444">NET.TCP</span><span class="sxs-lookup"><span data-stu-id="955fb-444">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="955fb-445">디렉터 부하 분산 장치</span><span class="sxs-lookup"><span data-stu-id="955fb-445">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="955fb-446">4443</span><span class="sxs-lookup"><span data-stu-id="955fb-446">4443</span></span></p></td>
<td><p><span data-ttu-id="955fb-447">HTTPS (역방향 프록시)</span><span class="sxs-lookup"><span data-stu-id="955fb-447">HTTPS (from reverse proxy)</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="955fb-448">DNS 부하 분산을 사용 하는 프런트 엔드 풀 및 디렉터 풀에도 하드웨어 부하 분산 장치를 배포 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="955fb-448">Your Front End pools and Director pools that use DNS load balancing also must have a hardware load balancer deployed.</span></span> <span data-ttu-id="955fb-449">다음 표에는 이러한 하드웨어 부하 분산 장치에서 열려 있어야 하는 포트가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="955fb-449">The following table shows the ports that need to be open on these hardware load balancers.</span></span>

### <a name="hardware-load-balancer-ports-if-using-dns-load-balancing"></a><span data-ttu-id="955fb-450">DNS 부하 분산을 사용 하는 경우 하드웨어 부하 분산 장치 포트</span><span class="sxs-lookup"><span data-stu-id="955fb-450">Hardware Load Balancer Ports if Using DNS Load Balancing</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="955fb-451">부하 분산 장치</span><span class="sxs-lookup"><span data-stu-id="955fb-451">Load Balancer</span></span></th>
<th><span data-ttu-id="955fb-452">포트</span><span class="sxs-lookup"><span data-stu-id="955fb-452">Port</span></span></th>
<th><span data-ttu-id="955fb-453">프로토콜별</span><span class="sxs-lookup"><span data-stu-id="955fb-453">Protocol</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="955fb-454">프런트 엔드 서버 부하 분산 장치</span><span class="sxs-lookup"><span data-stu-id="955fb-454">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="955fb-455">80</span><span class="sxs-lookup"><span data-stu-id="955fb-455">80</span></span></p></td>
<td><p><span data-ttu-id="955fb-456">HTTP</span><span class="sxs-lookup"><span data-stu-id="955fb-456">HTTP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="955fb-457">프런트 엔드 서버 부하 분산 장치</span><span class="sxs-lookup"><span data-stu-id="955fb-457">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="955fb-458">443</span><span class="sxs-lookup"><span data-stu-id="955fb-458">443</span></span></p></td>
<td><p><span data-ttu-id="955fb-459">HTTPS</span><span class="sxs-lookup"><span data-stu-id="955fb-459">HTTPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="955fb-460">프런트 엔드 서버 부하 분산 장치</span><span class="sxs-lookup"><span data-stu-id="955fb-460">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="955fb-461">8080</span><span class="sxs-lookup"><span data-stu-id="955fb-461">8080</span></span></p></td>
<td><p><span data-ttu-id="955fb-462">TCP-프런트 엔드 서버에서 루트 인증서의 클라이언트 및 장치 검색-NTLM으로 인증 된 클라이언트 및 장치</span><span class="sxs-lookup"><span data-stu-id="955fb-462">TCP - Client and device retrieval of root certificate from Front End Server – clients and devices authenticated by NTLM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="955fb-463">프런트 엔드 서버 부하 분산 장치</span><span class="sxs-lookup"><span data-stu-id="955fb-463">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="955fb-464">4443</span><span class="sxs-lookup"><span data-stu-id="955fb-464">4443</span></span></p></td>
<td><p><span data-ttu-id="955fb-465">HTTPS (역방향 프록시)</span><span class="sxs-lookup"><span data-stu-id="955fb-465">HTTPS (from reverse proxy)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="955fb-466">디렉터 부하 분산 장치</span><span class="sxs-lookup"><span data-stu-id="955fb-466">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="955fb-467">443</span><span class="sxs-lookup"><span data-stu-id="955fb-467">443</span></span></p></td>
<td><p><span data-ttu-id="955fb-468">HTTPS</span><span class="sxs-lookup"><span data-stu-id="955fb-468">HTTPS</span></span></p></td>
</tr>
<tr class="even">
<td> </td>
<td> </td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="955fb-469">디렉터 부하 분산 장치</span><span class="sxs-lookup"><span data-stu-id="955fb-469">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="955fb-470">4443</span><span class="sxs-lookup"><span data-stu-id="955fb-470">4443</span></span></p></td>
<td><p><span data-ttu-id="955fb-471">HTTPS (역방향 프록시)</span><span class="sxs-lookup"><span data-stu-id="955fb-471">HTTPS (from reverse proxy)</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="required-client-ports"></a><span data-ttu-id="955fb-472">필수 클라이언트 포트</span><span class="sxs-lookup"><span data-stu-id="955fb-472">Required Client Ports</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="955fb-473">요소가</span><span class="sxs-lookup"><span data-stu-id="955fb-473">Component</span></span></th>
<th><span data-ttu-id="955fb-474">포트</span><span class="sxs-lookup"><span data-stu-id="955fb-474">Port</span></span></th>
<th><span data-ttu-id="955fb-475">프로토콜별</span><span class="sxs-lookup"><span data-stu-id="955fb-475">Protocol</span></span></th>
<th><span data-ttu-id="955fb-476">상속자</span><span class="sxs-lookup"><span data-stu-id="955fb-476">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="955fb-477">클라이언트</span><span class="sxs-lookup"><span data-stu-id="955fb-477">Clients</span></span></p></td>
<td><p><span data-ttu-id="955fb-478">67/68</span><span class="sxs-lookup"><span data-stu-id="955fb-478">67/68</span></span></p></td>
<td><p><span data-ttu-id="955fb-479">서버의</span><span class="sxs-lookup"><span data-stu-id="955fb-479">DHCP</span></span></p></td>
<td><p><span data-ttu-id="955fb-480">Lync Server에서 등록자 FQDN을 찾는 데 사용 됩니다 (즉, DNS SRV에 장애가 발생 하 여 수동 설정이 구성 되지 않은 경우).</span><span class="sxs-lookup"><span data-stu-id="955fb-480">Used by Lync Server to find the Registrar FQDN (that is, if DNS SRV fails and manual settings are not configured).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="955fb-481">클라이언트</span><span class="sxs-lookup"><span data-stu-id="955fb-481">Clients</span></span></p></td>
<td><p><span data-ttu-id="955fb-482">443</span><span class="sxs-lookup"><span data-stu-id="955fb-482">443</span></span></p></td>
<td><p><span data-ttu-id="955fb-483">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="955fb-483">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="955fb-484">외부 사용자 액세스를 위한 클라이언트 대 서버 SIP 트래픽에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="955fb-484">Used for client-to-server SIP traffic for external user access.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="955fb-485">클라이언트</span><span class="sxs-lookup"><span data-stu-id="955fb-485">Clients</span></span></p></td>
<td><p><span data-ttu-id="955fb-486">443</span><span class="sxs-lookup"><span data-stu-id="955fb-486">443</span></span></p></td>
<td><p><span data-ttu-id="955fb-487">TCP (PSOM/TLS)</span><span class="sxs-lookup"><span data-stu-id="955fb-487">TCP (PSOM/TLS)</span></span></p></td>
<td><p><span data-ttu-id="955fb-488">웹 회의 세션에 대 한 외부 사용자 액세스에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="955fb-488">Used for external user access to web conferencing sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="955fb-489">클라이언트</span><span class="sxs-lookup"><span data-stu-id="955fb-489">Clients</span></span></p></td>
<td><p><span data-ttu-id="955fb-490">443</span><span class="sxs-lookup"><span data-stu-id="955fb-490">443</span></span></p></td>
<td><p><span data-ttu-id="955fb-491">TCP (STUN/MSTURN)</span><span class="sxs-lookup"><span data-stu-id="955fb-491">TCP (STUN/MSTURN)</span></span></p></td>
<td><p><span data-ttu-id="955fb-492">A/V 세션 및 미디어 (TCP)에 대 한 외부 사용자 액세스에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="955fb-492">Used for external user access to A/V sessions and media (TCP)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="955fb-493">클라이언트</span><span class="sxs-lookup"><span data-stu-id="955fb-493">Clients</span></span></p></td>
<td><p><span data-ttu-id="955fb-494">3478</span><span class="sxs-lookup"><span data-stu-id="955fb-494">3478</span></span></p></td>
<td><p><span data-ttu-id="955fb-495">UDP (STUN/MSTURN)</span><span class="sxs-lookup"><span data-stu-id="955fb-495">UDP (STUN/MSTURN)</span></span></p></td>
<td><p><span data-ttu-id="955fb-496">A/V 세션 및 미디어 (UDP)에 대 한 외부 사용자 액세스에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="955fb-496">Used for external user access to A/V sessions and media (UDP)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="955fb-497">클라이언트</span><span class="sxs-lookup"><span data-stu-id="955fb-497">Clients</span></span></p></td>
<td><p><span data-ttu-id="955fb-498">5061</span><span class="sxs-lookup"><span data-stu-id="955fb-498">5061</span></span></p></td>
<td><p><span data-ttu-id="955fb-499">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="955fb-499">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="955fb-500">외부 사용자 액세스를 위한 클라이언트 대 서버 SIP 트래픽에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="955fb-500">Used for client-to-server SIP traffic for external user access.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="955fb-501">클라이언트</span><span class="sxs-lookup"><span data-stu-id="955fb-501">Clients</span></span></p></td>
<td><p><span data-ttu-id="955fb-502">6891-6901</span><span class="sxs-lookup"><span data-stu-id="955fb-502">6891-6901</span></span></p></td>
<td><p><span data-ttu-id="955fb-503">NET.TCP</span><span class="sxs-lookup"><span data-stu-id="955fb-503">TCP</span></span></p></td>
<td><p><span data-ttu-id="955fb-504">Lync 클라이언트와 이전 클라이언트 간의 파일 전송 (Microsoft Office Communications Server 2007 R2, Microsoft Office Communications Server 2007 및 Live Communications Server 2005의 클라이언트)에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="955fb-504">Used for file transfer between Lync clients and previous clients (clients of Microsoft Office Communications Server 2007 R2, Microsoft Office Communications Server 2007, and Live Communications Server 2005).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="955fb-505">클라이언트</span><span class="sxs-lookup"><span data-stu-id="955fb-505">Clients</span></span></p></td>
<td><p><span data-ttu-id="955fb-506">1024-65535 \*</span><span class="sxs-lookup"><span data-stu-id="955fb-506">1024-65535 \*</span></span></p></td>
<td><p><span data-ttu-id="955fb-507">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="955fb-507">TCP/UDP</span></span></p></td>
<td><p><span data-ttu-id="955fb-508">오디오 포트 범위 (최소 20 개의 포트가 필요 함)</span><span class="sxs-lookup"><span data-stu-id="955fb-508">Audio port range (minimum of 20 ports required)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="955fb-509">클라이언트</span><span class="sxs-lookup"><span data-stu-id="955fb-509">Clients</span></span></p></td>
<td><p><span data-ttu-id="955fb-510">1024-65535 \*</span><span class="sxs-lookup"><span data-stu-id="955fb-510">1024-65535 \*</span></span></p></td>
<td><p><span data-ttu-id="955fb-511">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="955fb-511">TCP/UDP</span></span></p></td>
<td><p><span data-ttu-id="955fb-512">비디오 포트 범위 (최소 20 개 포트 필요).</span><span class="sxs-lookup"><span data-stu-id="955fb-512">Video port range (minimum of 20 ports required).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="955fb-513">클라이언트</span><span class="sxs-lookup"><span data-stu-id="955fb-513">Clients</span></span></p></td>
<td><p><span data-ttu-id="955fb-514">1024-65535 \*</span><span class="sxs-lookup"><span data-stu-id="955fb-514">1024-65535 \*</span></span></p></td>
<td><p><span data-ttu-id="955fb-515">NET.TCP</span><span class="sxs-lookup"><span data-stu-id="955fb-515">TCP</span></span></p></td>
<td><p><span data-ttu-id="955fb-516">피어 투 피어 파일 전송 (회의 파일 전송의 경우 클라이언트는 PSOM 사용).</span><span class="sxs-lookup"><span data-stu-id="955fb-516">Peer-to-peer file transfer (for conferencing file transfer, clients use PSOM).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="955fb-517">클라이언트</span><span class="sxs-lookup"><span data-stu-id="955fb-517">Clients</span></span></p></td>
<td><p><span data-ttu-id="955fb-518">1024-65535 \*</span><span class="sxs-lookup"><span data-stu-id="955fb-518">1024-65535 \*</span></span></p></td>
<td><p><span data-ttu-id="955fb-519">NET.TCP</span><span class="sxs-lookup"><span data-stu-id="955fb-519">TCP</span></span></p></td>
<td><p><span data-ttu-id="955fb-520">응용 프로그램 공유</span><span class="sxs-lookup"><span data-stu-id="955fb-520">Application sharing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="955fb-521">Aastra 6721ip 공용 지역 전화</span><span class="sxs-lookup"><span data-stu-id="955fb-521">Aastra 6721ip common area phone</span></span></p>
<p><span data-ttu-id="955fb-522">Aastra 6725ip 일반 전화기</span><span class="sxs-lookup"><span data-stu-id="955fb-522">Aastra 6725ip desk phone</span></span></p>
<p><span data-ttu-id="955fb-523">HP 4110 IP 전화 (공통 지역 전화)</span><span class="sxs-lookup"><span data-stu-id="955fb-523">HP 4110 IP Phone (common area phone)</span></span></p>
<p><span data-ttu-id="955fb-524">HP 4120 IP 전화기 (일반 전화기)</span><span class="sxs-lookup"><span data-stu-id="955fb-524">HP 4120 IP Phone (desk phone)</span></span></p>
<p><span data-ttu-id="955fb-525">Polycom CX500 IP 일반 지역 전화</span><span class="sxs-lookup"><span data-stu-id="955fb-525">Polycom CX500 IP common area phone</span></span></p>
<p><span data-ttu-id="955fb-526">Polycom CX600 IP 일반 전화기</span><span class="sxs-lookup"><span data-stu-id="955fb-526">Polycom CX600 IP desk phone</span></span></p>
<p><span data-ttu-id="955fb-527">Polycom CX700 IP 일반 전화기</span><span class="sxs-lookup"><span data-stu-id="955fb-527">Polycom CX700 IP desk phone</span></span></p>
<p><span data-ttu-id="955fb-528">Polycom CX3000 IP 컨퍼런스 전화</span><span class="sxs-lookup"><span data-stu-id="955fb-528">Polycom CX3000 IP conference phone</span></span></p></td>
<td><p><span data-ttu-id="955fb-529">67/68</span><span class="sxs-lookup"><span data-stu-id="955fb-529">67/68</span></span></p></td>
<td><p><span data-ttu-id="955fb-530">서버의</span><span class="sxs-lookup"><span data-stu-id="955fb-530">DHCP</span></span></p></td>
<td><p><span data-ttu-id="955fb-531">나열 된 디바이스에서 Lync Server 인증서, 프로비저닝 FQDN 및 등록자 FQDN을 찾는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="955fb-531">Used by the listed devices to find the Lync Server certificate, provisioning FQDN, and Registrar FQDN.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="955fb-532">**\*** 이러한 미디어 형식에 대 한 특정 포트를 구성 하려면 CsConferencingConfiguration cmdlet (ClientMediaPortRangeEnabled, ClientMediaPort 및 ClientMediaPortRange parameters)을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="955fb-532">**\*** To configure specific ports for these media types, use the CsConferencingConfiguration cmdlet (ClientMediaPortRangeEnabled, ClientMediaPort, and ClientMediaPortRange parameters).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="955fb-533">Lync 클라이언트에 대 한 프로그램 설정에서는 클라이언트 컴퓨터에서 필요한 운영 체제 방화벽 예외를 자동으로 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="955fb-533">The set programs for Lync clients automatically create the required operating-system firewall exceptions on the client computer.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="955fb-534">외부 사용자 액세스에 사용 되는 포트는 클라이언트가 조직의 방화벽을 통과 해야 하는 모든 시나리오 (예: 다른 조직에서 호스팅하는 외부 통신 또는 모임)에 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="955fb-534">The ports that are used for external user access are required for any scenario in which the client must traverse the organization’s firewall (for example, any external communications or meetings hosted by other organizations).</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

