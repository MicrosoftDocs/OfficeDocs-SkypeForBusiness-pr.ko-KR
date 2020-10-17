---
title: 'Lync Server 2013: 포트 요약-확장 된 디렉터 풀, 하드웨어 부하 분산 장치'
description: 'Lync Server 2013: 포트 요약-확장 된 디렉터 풀, 하드웨어 부하 분산 장치입니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Scaled Director pool, hardware load balancer
ms:assetid: 6ae2f4ac-5b64-4e45-8253-133308f5812d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204983(v=OCS.15)
ms:contentKeyID: 48184434
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 10bfb3a3ad3a38b6cb0e46414bf22deecc71d7b5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564554"
---
# <a name="port-summary---scaled-director-pool-hardware-load-balancer-in-lync-server-2013"></a><span data-ttu-id="80524-103">Lync Server 2013의 포트 요약-확장 된 디렉터 풀, 하드웨어 부하 분산 장치</span><span class="sxs-lookup"><span data-stu-id="80524-103">Port summary - Scaled Director pool, hardware load balancer in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="80524-104">_**마지막으로 수정 된 항목:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="80524-104">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="80524-105">디렉터 풀에 대 한 방화벽 포트 요구 사항은에 지 서버의 내부 인터페이스 또는 역방향 프록시의 내부 인터페이스에서 디렉터와의 통신을 설정 하는 데 사용 되는 포트로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="80524-105">Firewall port requirements for a Director pool consist of the ports that are used to establish communication with the Director from the internal interface of the Edge Server or internal-facing interface of the reverse proxy.</span></span> <span data-ttu-id="80524-106">기본적으로 Microsoft Lync Server 2013은 프런트 엔드 풀 및 프런트 엔드 서버 뿐만 아니라 역방향 프록시에서 디렉터로의 포트 HTTP/TCP 8080 및 HTTPS/TCP 4443을 사용할 것으로 예상 합니다.</span><span class="sxs-lookup"><span data-stu-id="80524-106">Microsoft Lync Server 2013 by default expects ports HTTP/TCP 8080 and HTTPS/TCP 4443 to be open from the reverse proxy to the Director, as well as the Front End pool and Front End Server.</span></span> <span data-ttu-id="80524-107">또한에 지 서버 내부 인터페이스에서 디렉터 및 프런트 엔드 풀 및 프런트 엔드 서버로의 SIP (session 착수 프로토콜) 통신이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="80524-107">Additionally, there must be session initiation protocol (SIP) communication from the Edge Server internal interface to the Director and to the Front End pool and Front End Server.</span></span> <span data-ttu-id="80524-108">SIP 프로토콜은에 지 서버에서 프런트 엔드 풀 및 프런트 엔드 서버로의 SIP/MTLS/TCP 5061를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="80524-108">The SIP protocol uses SIP/MTLS/TCP 5061 from the Edge Server to the Front End pool and Front End Server.</span></span> <span data-ttu-id="80524-109">디렉터, 프런트 엔드 풀 및 프런트 엔드 서버에서에 지 서버 내부 인터페이스에 대 한 SIP/MTLS/TCP 5061 통신을 허용 하는 규칙을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="80524-109">A rule that allows SIP/MTLS/TCP 5061 communication from the Director, Front End pool and Front End Server to the Edge Server internal interface must be created as well.</span></span>

### <a name="director-ports-and-protocols-for-firewall-definitions"></a><span data-ttu-id="80524-110">방화벽 정의를 위한 디렉터 포트 및 프로토콜</span><span class="sxs-lookup"><span data-stu-id="80524-110">Director Ports and Protocols for Firewall Definitions</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="80524-111">역할/프로토콜/TCP 또는 UDP/포트</span><span class="sxs-lookup"><span data-stu-id="80524-111">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="80524-112">원본 IP 주소</span><span class="sxs-lookup"><span data-stu-id="80524-112">Source IP address</span></span></th>
<th><span data-ttu-id="80524-113">대상 IP 주소</span><span class="sxs-lookup"><span data-stu-id="80524-113">Destination IP address</span></span></th>
<th><span data-ttu-id="80524-114">참고</span><span class="sxs-lookup"><span data-stu-id="80524-114">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="80524-115">HTTP/TCP 8080</span><span class="sxs-lookup"><span data-stu-id="80524-115">HTTP/TCP 8080</span></span></p></td>
<td><p><span data-ttu-id="80524-116">역방향 프록시 내부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="80524-116">Reverse proxy internal interface</span></span></p></td>
<td><p><span data-ttu-id="80524-117">디렉터 하드웨어 부하 분산 장치 VIP</span><span class="sxs-lookup"><span data-stu-id="80524-117">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="80524-118">역방향 프록시의 외부 쪽에서 처음 수신 되는 통신은 디렉터 HLB VIP 및 프런트 엔드 서버 웹 서비스로 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="80524-118">Initially received by the external side of the reverse proxy, the communication is sent on to the Director HLB VIP and Front End Servers web services</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80524-119">HTTPS/TCP 4443</span><span class="sxs-lookup"><span data-stu-id="80524-119">HTTPS/TCP 4443</span></span></p></td>
<td><p><span data-ttu-id="80524-120">역방향 프록시 내부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="80524-120">Reverse proxy internal interface</span></span></p></td>
<td><p><span data-ttu-id="80524-121">디렉터 하드웨어 부하 분산 장치 VIP</span><span class="sxs-lookup"><span data-stu-id="80524-121">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="80524-122">역방향 프록시의 외부 쪽에서 처음 수신 되는 통신은 디렉터 HLB VIP 및 프런트 엔드 서버 웹 서비스로 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="80524-122">Initially received by the external side of the reverse proxy, the communication is sent on to the Director HLB VIP and Front End Servers web services</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80524-123">HTTPS/TCP 444</span><span class="sxs-lookup"><span data-stu-id="80524-123">HTTPS/TCP 444</span></span></p></td>
<td><p><span data-ttu-id="80524-124">Director</span><span class="sxs-lookup"><span data-stu-id="80524-124">Director</span></span></p></td>
<td><p><span data-ttu-id="80524-125">프런트 엔드 서버 또는 프런트 엔드 풀</span><span class="sxs-lookup"><span data-stu-id="80524-125">Front End Server or Front End pool</span></span></p></td>
<td><p><span data-ttu-id="80524-126">디렉터 HLB VIP와 프런트 엔드 서버 간의 서버 간 통신</span><span class="sxs-lookup"><span data-stu-id="80524-126">Inter-server communication between the Director HLB VIP and the Front End Servers</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80524-127">HTTP/TCP 80</span><span class="sxs-lookup"><span data-stu-id="80524-127">HTTP/TCP 80</span></span></p></td>
<td><p><span data-ttu-id="80524-128">내부 클라이언트</span><span class="sxs-lookup"><span data-stu-id="80524-128">Internal Clients</span></span></p></td>
<td><p><span data-ttu-id="80524-129">디렉터 하드웨어 부하 분산 장치 VIP</span><span class="sxs-lookup"><span data-stu-id="80524-129">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="80524-130">디렉터는 내부 및 외부 클라이언트에 대해 웹 서비스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="80524-130">The Director provides web services to internal as well as external clients.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80524-131">HTTPS/TCP 443</span><span class="sxs-lookup"><span data-stu-id="80524-131">HTTPS/TCP 443</span></span></p></td>
<td><p><span data-ttu-id="80524-132">내부 클라이언트</span><span class="sxs-lookup"><span data-stu-id="80524-132">Internal Clients</span></span></p></td>
<td><p><span data-ttu-id="80524-133">디렉터 하드웨어 부하 분산 장치 VIP</span><span class="sxs-lookup"><span data-stu-id="80524-133">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="80524-134">디렉터는 내부 및 외부 클라이언트에 대해 웹 서비스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="80524-134">The Director provides web services to internal as well as external clients.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80524-135">SIP/MTLS/TCP 5061</span><span class="sxs-lookup"><span data-stu-id="80524-135">SIP/MTLS/TCP 5061</span></span></p></td>
<td><p><span data-ttu-id="80524-136">에 지 서버 내부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="80524-136">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="80524-137">디렉터 하드웨어 부하 분산 장치 VIP</span><span class="sxs-lookup"><span data-stu-id="80524-137">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="80524-138">에 지 서버에서 디렉터 및 프런트 엔드 서버로의 SIP 통신</span><span class="sxs-lookup"><span data-stu-id="80524-138">SIP communication from the Edge Server to the Director, and Front End Servers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80524-139">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="80524-139">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="80524-140">모두</span><span class="sxs-lookup"><span data-stu-id="80524-140">Any</span></span></p></td>
<td><p><span data-ttu-id="80524-141">Director</span><span class="sxs-lookup"><span data-stu-id="80524-141">Director</span></span></p></td>
<td><p><span data-ttu-id="80524-142">중앙 로깅 서비스 컨트롤러 (ClsController.exe) 또는 에이전트 (ClsAgent.exe) 명령 및 로그 수집</span><span class="sxs-lookup"><span data-stu-id="80524-142">Centralized Logging Service controller (ClsController.exe) or agent (ClsAgent.exe)commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80524-143">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="80524-143">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="80524-144">모두</span><span class="sxs-lookup"><span data-stu-id="80524-144">Any</span></span></p></td>
<td><p><span data-ttu-id="80524-145">Director</span><span class="sxs-lookup"><span data-stu-id="80524-145">Director</span></span></p></td>
<td><p><span data-ttu-id="80524-146">중앙 로깅 서비스 컨트롤러 (ClsController.exe) 또는 에이전트 (ClsAgent.exe) 명령 및 로그 수집</span><span class="sxs-lookup"><span data-stu-id="80524-146">Centralized Logging Service controller (ClsController.exe) or agent (ClsAgent.exe)commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80524-147">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="80524-147">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="80524-148">모두</span><span class="sxs-lookup"><span data-stu-id="80524-148">Any</span></span></p></td>
<td><p><span data-ttu-id="80524-149">Director</span><span class="sxs-lookup"><span data-stu-id="80524-149">Director</span></span></p></td>
<td><p><span data-ttu-id="80524-150">중앙 로깅 서비스 컨트롤러 (ClsController.exe) 또는 에이전트 (ClsAgent.exe) 명령 및 로그 수집</span><span class="sxs-lookup"><span data-stu-id="80524-150">Centralized Logging Service controller (ClsController.exe) or agent (ClsAgent.exe)commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

