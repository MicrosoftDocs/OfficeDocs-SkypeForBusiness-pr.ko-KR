---
title: 'Lync Server 2013: 포트 요약 - DNS 및 HLB 부하 분산됨'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Port summary - DNS and HLB load balanced
ms:assetid: b07c37e4-820e-46ee-a678-1da95d1b87af
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205179(v=OCS.15)
ms:contentKeyID: 48185149
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5bd2a276f9495d314d2a8d4588f027df08978b94
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982322"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---dns-and-hlb-load-balanced-in-lync-server-2013"></a><span data-ttu-id="3e97b-102">Lync Server 2013의 포트 요약 - DNS 및 HLB 부하 분산됨</span><span class="sxs-lookup"><span data-stu-id="3e97b-102">Port summary - DNS and HLB load balanced in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3e97b-103">_**마지막으로 수정한 주제:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="3e97b-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="3e97b-104">단일 디렉터에 대 한 방화벽 포트 요구 사항은 내부 인터페이스 또는 리버스 프록시의 내부 네트워크에서 디렉터와의 통신을 설정 하는 데 사용 되는 포트로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e97b-104">Firewall port requirements for a single Director consist of the ports that are used to establish communication with the Director from the internal interface or internal-facing network of the reverse proxy.</span></span> <span data-ttu-id="3e97b-105">Microsoft Lync Server 2013에는 기본적으로 역방향 프록시, 디렉터에 대 한 HTTP/TCP 8080 및 HTTPS/TCP 4443가 프런트 엔드 풀 및 프런트 엔드 서버와 함께 열려 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e97b-105">Microsoft Lync Server 2013 by default expects ports HTTP/TCP 8080 and HTTPS/TCP 4443 to be open from the reverse proxy to the Director, as well as the Front End pool and Front End Server.</span></span> <span data-ttu-id="3e97b-106">또한 Edge Server 내부 인터페이스에서 디렉터 및 프런트 엔드 풀 및 프런트 엔드 서버로의 SIP (세션 초기화 프로토콜) 통신이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e97b-106">Additionally, there must be session initiation protocol (SIP) communication from the Edge Server internal interface to the Director and to the Front End pool and Front End Server.</span></span> <span data-ttu-id="3e97b-107">SIP 프로토콜은 Edge 서버에서 프런트 엔드 풀 및 프런트 엔드 서버로 SIP/MTLS/TCP 5061를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e97b-107">The SIP protocol uses SIP/MTLS/TCP 5061 from the Edge Server to the Front End pool and Front End Server.</span></span> <span data-ttu-id="3e97b-108">SIP/MTLS/TCP 5061 통신을 디렉터, 프런트 엔드 풀 및 프런트 엔드 서버와 Edge 서버 내부 인터페이스와 함께 만들어야 하는 규칙입니다.</span><span class="sxs-lookup"><span data-stu-id="3e97b-108">A rule that allows SIP/MTLS/TCP 5061 communication from the Director, Front End pool and Front End Server to the Edge Server internal interface must be created as well.</span></span>

### <a name="single-director-ports-and-protocols-for-firewall-definitions"></a><span data-ttu-id="3e97b-109">방화벽 정의에 대 한 단일 디렉터 포트 및 프로토콜</span><span class="sxs-lookup"><span data-stu-id="3e97b-109">Single Director Ports and Protocols for Firewall Definitions</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3e97b-110">역할/프로토콜/TCP 또는 UDP/포트</span><span class="sxs-lookup"><span data-stu-id="3e97b-110">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="3e97b-111">원본 IP 주소</span><span class="sxs-lookup"><span data-stu-id="3e97b-111">Source IP address</span></span></th>
<th><span data-ttu-id="3e97b-112">대상 IP 주소</span><span class="sxs-lookup"><span data-stu-id="3e97b-112">Destination IP address</span></span></th>
<th><span data-ttu-id="3e97b-113">상속자</span><span class="sxs-lookup"><span data-stu-id="3e97b-113">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3e97b-114">HTTP/TCP 8080</span><span class="sxs-lookup"><span data-stu-id="3e97b-114">HTTP/TCP 8080</span></span></p></td>
<td><p><span data-ttu-id="3e97b-115">리버스 프록시 내부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3e97b-115">Reverse proxy internal interface</span></span></p></td>
<td><p><span data-ttu-id="3e97b-116">하드웨어 부하 분산 장치 VIP 감독</span><span class="sxs-lookup"><span data-stu-id="3e97b-116">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="3e97b-117">처음에 리버스 프록시의 외부에 의해 수신 된 통신은 디렉터 HLB VIP 및 프런트 엔드 서버 웹 서비스로 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e97b-117">Initially received by the external side of the reverse proxy, the communication is sent on to the Director HLB VIP and Front End Server web services.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e97b-118">HTTPS/TCP 4443</span><span class="sxs-lookup"><span data-stu-id="3e97b-118">HTTPS/TCP 4443</span></span></p></td>
<td><p><span data-ttu-id="3e97b-119">리버스 프록시 내부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3e97b-119">Reverse proxy internal interface</span></span></p></td>
<td><p><span data-ttu-id="3e97b-120">하드웨어 부하 분산 장치 VIP 감독</span><span class="sxs-lookup"><span data-stu-id="3e97b-120">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="3e97b-121">처음에 리버스 프록시의 외부에 의해 수신 된 통신은 디렉터 HLB VIP 및 프런트 엔드 서버 웹 서비스로 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e97b-121">Initially received by the external side of the reverse proxy, the communication is sent on to the Director HLB VIP and Front End Server web services.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e97b-122">HTTPS/TCP 444</span><span class="sxs-lookup"><span data-stu-id="3e97b-122">HTTPS/TCP 444</span></span></p></td>
<td><p><span data-ttu-id="3e97b-123">Director</span><span class="sxs-lookup"><span data-stu-id="3e97b-123">Director</span></span></p></td>
<td><p><span data-ttu-id="3e97b-124">프런트 엔드 풀 또는 프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="3e97b-124">Front End pool or Front End Server</span></span></p></td>
<td><p><span data-ttu-id="3e97b-125">디렉터 HLB VIP와 프런트 엔드 서버 또는 프런트 엔드 서버 간의 서버 간 통신</span><span class="sxs-lookup"><span data-stu-id="3e97b-125">Inter-server communication between the Director HLB VIP and the Front End Server or Front End Servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e97b-126">HTTP/TCP 80</span><span class="sxs-lookup"><span data-stu-id="3e97b-126">HTTP/TCP 80</span></span></p></td>
<td><p><span data-ttu-id="3e97b-127">내부 클라이언트</span><span class="sxs-lookup"><span data-stu-id="3e97b-127">Internal Clients</span></span></p></td>
<td><p><span data-ttu-id="3e97b-128">하드웨어 부하 분산 장치 VIP 감독</span><span class="sxs-lookup"><span data-stu-id="3e97b-128">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="3e97b-129">디렉터는 내부 및 외부 클라이언트에 웹 서비스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e97b-129">The Director provides web services to internal as well as external clients.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e97b-130">HTTPS/TCP 443</span><span class="sxs-lookup"><span data-stu-id="3e97b-130">HTTPS/TCP 443</span></span></p></td>
<td><p><span data-ttu-id="3e97b-131">내부 클라이언트</span><span class="sxs-lookup"><span data-stu-id="3e97b-131">Internal Clients</span></span></p></td>
<td><p><span data-ttu-id="3e97b-132">하드웨어 부하 분산 장치 VIP 감독</span><span class="sxs-lookup"><span data-stu-id="3e97b-132">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="3e97b-133">디렉터는 내부 및 외부 클라이언트에 웹 서비스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e97b-133">The Director provides web services to internal as well as external clients.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e97b-134">SIP/MTLS/TCP 5061</span><span class="sxs-lookup"><span data-stu-id="3e97b-134">SIP/MTLS/TCP 5061</span></span></p></td>
<td><p><span data-ttu-id="3e97b-135">Edge 서버 내부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3e97b-135">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="3e97b-136">Director</span><span class="sxs-lookup"><span data-stu-id="3e97b-136">Director</span></span></p></td>
<td><p><span data-ttu-id="3e97b-137">Edge 서버에서 디렉터 및 프런트 엔드 서버와의 SIP 통신</span><span class="sxs-lookup"><span data-stu-id="3e97b-137">SIP communication from the Edge Server to the Director, as well as the Front End Servers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e97b-138">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="3e97b-138">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="3e97b-139">이상</span><span class="sxs-lookup"><span data-stu-id="3e97b-139">Any</span></span></p></td>
<td><p><span data-ttu-id="3e97b-140">Director</span><span class="sxs-lookup"><span data-stu-id="3e97b-140">Director</span></span></p></td>
<td><p><span data-ttu-id="3e97b-141">중앙 로깅 서비스 컨트롤러 (ClsController) 또는 에이전트 (Clscontroller .exe) 명령 및 로그 수집</span><span class="sxs-lookup"><span data-stu-id="3e97b-141">Centralized Logging Service controller (ClsController.exe) or agent (ClsAgent.exe)commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e97b-142">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="3e97b-142">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="3e97b-143">이상</span><span class="sxs-lookup"><span data-stu-id="3e97b-143">Any</span></span></p></td>
<td><p><span data-ttu-id="3e97b-144">Director</span><span class="sxs-lookup"><span data-stu-id="3e97b-144">Director</span></span></p></td>
<td><p><span data-ttu-id="3e97b-145">중앙 로깅 서비스 컨트롤러 (ClsController) 또는 에이전트 (Clscontroller .exe) 명령 및 로그 수집</span><span class="sxs-lookup"><span data-stu-id="3e97b-145">Centralized Logging Service controller (ClsController.exe) or agent (ClsAgent.exe)commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e97b-146">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="3e97b-146">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="3e97b-147">이상</span><span class="sxs-lookup"><span data-stu-id="3e97b-147">Any</span></span></p></td>
<td><p><span data-ttu-id="3e97b-148">Director</span><span class="sxs-lookup"><span data-stu-id="3e97b-148">Director</span></span></p></td>
<td><p><span data-ttu-id="3e97b-149">중앙 로깅 서비스 컨트롤러 (ClsController) 또는 에이전트 (Clscontroller .exe) 명령 및 로그 수집</span><span class="sxs-lookup"><span data-stu-id="3e97b-149">Centralized Logging Service controller (ClsController.exe) or agent (ClsAgent.exe)commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

