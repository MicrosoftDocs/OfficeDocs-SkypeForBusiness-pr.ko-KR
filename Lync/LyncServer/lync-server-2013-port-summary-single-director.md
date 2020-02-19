---
title: 'Lync Server 2013: 포트 요약-단일 디렉터'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Single Director
ms:assetid: 079c1414-723f-4499-b7d4-a0d7121c1626
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204648(v=OCS.15)
ms:contentKeyID: 48183322
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8515785f66101df3af0d7d35de565ba344e2b91a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42139179"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="port-summary---single-director-in-lync-server-2013"></a><span data-ttu-id="fdd04-102">포트 요약-Lync Server 2013의 단일 디렉터</span><span class="sxs-lookup"><span data-stu-id="fdd04-102">Port summary - Single Director in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fdd04-103">_**마지막으로 수정 된 항목:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="fdd04-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="fdd04-104">단일 디렉터에 대 한 방화벽 포트 요구 사항은 내부 인터페이스 또는 역방향 프록시의 내부 연결 네트워크에서 디렉터와의 통신을 설정 하는 데 사용 되는 포트로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fdd04-104">Firewall port requirements for a single Director consist of the ports that are used to establish communication with the Director from the internal interface or internal-facing network of the reverse proxy.</span></span> <span data-ttu-id="fdd04-105">기본적으로 Microsoft Lync Server 2013은 프런트 엔드 풀 및 프런트 엔드 서버 뿐만 아니라 역방향 프록시에서 디렉터로의 포트 HTTP/TCP 8080 및 HTTPS/TCP 4443을 사용할 것으로 예상 합니다.</span><span class="sxs-lookup"><span data-stu-id="fdd04-105">Microsoft Lync Server 2013 by default expects ports HTTP/TCP 8080 and HTTPS/TCP 4443 to be open from the reverse proxy to the Director, as well as the Front End pool and Front End Server.</span></span> <span data-ttu-id="fdd04-106">또한에 지 서버 내부 인터페이스에서 디렉터 및 프런트 엔드 풀 및 프런트 엔드 서버로의 SIP (session 착수 프로토콜) 통신이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fdd04-106">Additionally, there must be session initiation protocol (SIP) communication from the Edge Server internal interface to the Director and to the Front End pool and Front End Server.</span></span> <span data-ttu-id="fdd04-107">SIP 프로토콜은에 지 서버에서 프런트 엔드 풀 및 프런트 엔드 서버로의 SIP/MTLS/TCP 5061를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="fdd04-107">The SIP protocol uses SIP/MTLS/TCP 5061 from the Edge Server to the Front End pool and Front End Server.</span></span> <span data-ttu-id="fdd04-108">디렉터, 프런트 엔드 풀 및 프런트 엔드 서버에서에 지 서버 내부 인터페이스에 대 한 SIP/MTLS/TCP 5061 통신을 허용 하는 규칙을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fdd04-108">A rule that allows SIP/MTLS/TCP 5061 communication from the Director, Front End pool and Front End Server to the Edge Server internal interface must be created as well.</span></span>

### <a name="single-director-ports-and-protocols-for-firewall-definitions"></a><span data-ttu-id="fdd04-109">방화벽 정의를 위한 단일 디렉터 포트 및 프로토콜</span><span class="sxs-lookup"><span data-stu-id="fdd04-109">Single Director Ports and Protocols for Firewall Definitions</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fdd04-110">역할/프로토콜/TCP 또는 UDP/포트</span><span class="sxs-lookup"><span data-stu-id="fdd04-110">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="fdd04-111">원본 IP 주소</span><span class="sxs-lookup"><span data-stu-id="fdd04-111">Source IP address</span></span></th>
<th><span data-ttu-id="fdd04-112">대상 IP 주소</span><span class="sxs-lookup"><span data-stu-id="fdd04-112">Destination IP address</span></span></th>
<th><span data-ttu-id="fdd04-113">Notes</span><span class="sxs-lookup"><span data-stu-id="fdd04-113">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fdd04-114">HTTP/TCP 8080</span><span class="sxs-lookup"><span data-stu-id="fdd04-114">HTTP/TCP 8080</span></span></p></td>
<td><p><span data-ttu-id="fdd04-115">역방향 프록시 내부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fdd04-115">Reverse proxy internal interface</span></span></p></td>
<td><p><span data-ttu-id="fdd04-116">영화</span><span class="sxs-lookup"><span data-stu-id="fdd04-116">Director</span></span></p></td>
<td><p><span data-ttu-id="fdd04-117">역방향 프록시의 외부 쪽에서 처음 수신 되는 통신은 디렉터 및 프런트 엔드 서버 웹 서비스로 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fdd04-117">Initially received by the external side of the reverse proxy, the communication is sent on to the Director and Front End Server web services</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fdd04-118">HTTPS/TCP 4443</span><span class="sxs-lookup"><span data-stu-id="fdd04-118">HTTPS/TCP 4443</span></span></p></td>
<td><p><span data-ttu-id="fdd04-119">역방향 프록시 내부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fdd04-119">Reverse proxy internal interface</span></span></p></td>
<td><p><span data-ttu-id="fdd04-120">영화</span><span class="sxs-lookup"><span data-stu-id="fdd04-120">Director</span></span></p></td>
<td><p><span data-ttu-id="fdd04-121">역방향 프록시의 외부 쪽에서 처음 수신 되는 통신은 디렉터 및 프런트 엔드 서버 웹 서비스로 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fdd04-121">Initially received by the external side of the reverse proxy, the communication is sent on to the Director and Front End Server web services</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fdd04-122">HTTPS/TCP 444</span><span class="sxs-lookup"><span data-stu-id="fdd04-122">HTTPS/TCP 444</span></span></p></td>
<td><p><span data-ttu-id="fdd04-123">영화</span><span class="sxs-lookup"><span data-stu-id="fdd04-123">Director</span></span></p></td>
<td><p><span data-ttu-id="fdd04-124">프런트 엔드 서버 또는 프런트 엔드 풀</span><span class="sxs-lookup"><span data-stu-id="fdd04-124">Front End server or Front End pool</span></span></p></td>
<td><p><span data-ttu-id="fdd04-125">디렉터와 프런트 엔드 서버 간의 서버 간 통신</span><span class="sxs-lookup"><span data-stu-id="fdd04-125">Inter-server communication between the Director and the Front End Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fdd04-126">HTTP/TCP 80</span><span class="sxs-lookup"><span data-stu-id="fdd04-126">HTTP/TCP 80</span></span></p></td>
<td><p><span data-ttu-id="fdd04-127">내부 클라이언트</span><span class="sxs-lookup"><span data-stu-id="fdd04-127">Internal Clients</span></span></p></td>
<td><p><span data-ttu-id="fdd04-128">디렉터 웹 서비스</span><span class="sxs-lookup"><span data-stu-id="fdd04-128">Director web services</span></span></p></td>
<td><p><span data-ttu-id="fdd04-129">디렉터는 내부 및 외부 클라이언트에 대해 웹 서비스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="fdd04-129">The Director provides web services to internal and external clients.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fdd04-130">HTTPS/TCP 443</span><span class="sxs-lookup"><span data-stu-id="fdd04-130">HTTPS/TCP 443</span></span></p></td>
<td><p><span data-ttu-id="fdd04-131">내부 클라이언트</span><span class="sxs-lookup"><span data-stu-id="fdd04-131">Internal Clients</span></span></p></td>
<td><p><span data-ttu-id="fdd04-132">디렉터 웹 서비스</span><span class="sxs-lookup"><span data-stu-id="fdd04-132">Director web services</span></span></p></td>
<td><p><span data-ttu-id="fdd04-133">디렉터는 내부 및 외부 클라이언트에 대해 웹 서비스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="fdd04-133">The Director provides web services to internal and external clients.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fdd04-134">SIP/MTLS/TCP 5061</span><span class="sxs-lookup"><span data-stu-id="fdd04-134">SIP/MTLS/TCP 5061</span></span></p></td>
<td><p><span data-ttu-id="fdd04-135">에 지 서버 내부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fdd04-135">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="fdd04-136">영화</span><span class="sxs-lookup"><span data-stu-id="fdd04-136">Director</span></span></p></td>
<td><p><span data-ttu-id="fdd04-137">에 지 서버에서 디렉터 및 프런트 엔드 서버로의 SIP 통신</span><span class="sxs-lookup"><span data-stu-id="fdd04-137">SIP communication from the Edge Server to the Director, and the Front End Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fdd04-138">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="fdd04-138">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="fdd04-139">모두</span><span class="sxs-lookup"><span data-stu-id="fdd04-139">Any</span></span></p></td>
<td><p><span data-ttu-id="fdd04-140">에 지 서버 내부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fdd04-140">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="fdd04-141">중앙화된 로깅 서비스 컨트롤러(ClsController.exe) 또는 에이전트(ClasAgent.exe) 명령 또는 로그 수집</span><span class="sxs-lookup"><span data-stu-id="fdd04-141">Centralized Logging Service controller (ClsController.exe) or agent (ClasAgent.exe)commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fdd04-142">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="fdd04-142">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="fdd04-143">모두</span><span class="sxs-lookup"><span data-stu-id="fdd04-143">Any</span></span></p></td>
<td><p><span data-ttu-id="fdd04-144">에 지 서버 내부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fdd04-144">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="fdd04-145">중앙화된 로깅 서비스 컨트롤러(ClsController.exe) 또는 에이전트(ClasAgent.exe) 명령 또는 로그 수집</span><span class="sxs-lookup"><span data-stu-id="fdd04-145">Centralized Logging Service controller (ClsController.exe) or agent (ClasAgent.exe)commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fdd04-146">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="fdd04-146">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="fdd04-147">모두</span><span class="sxs-lookup"><span data-stu-id="fdd04-147">Any</span></span></p></td>
<td><p><span data-ttu-id="fdd04-148">에 지 서버 내부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fdd04-148">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="fdd04-149">중앙화된 로깅 서비스 컨트롤러(ClsController.exe) 또는 에이전트(ClasAgent.exe) 명령 또는 로그 수집</span><span class="sxs-lookup"><span data-stu-id="fdd04-149">Centralized Logging Service controller (ClsController.exe) or agent (ClasAgent.exe)commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

