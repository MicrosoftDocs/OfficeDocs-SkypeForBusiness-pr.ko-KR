---
title: 'Lync Server 2013: 포트 요약-단일 디렉터'
description: 'Lync Server 2013: 포트 요약-단일 디렉터'
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
ms.openlocfilehash: a46e394121dbc7dd6158016d39511e9487cec1ff
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566374"
---
# <a name="port-summary---single-director-in-lync-server-2013"></a><span data-ttu-id="c9fb1-103">포트 요약-Lync Server 2013의 단일 디렉터</span><span class="sxs-lookup"><span data-stu-id="c9fb1-103">Port summary - Single Director in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c9fb1-104">_**마지막으로 수정 된 항목:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="c9fb1-104">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="c9fb1-105">단일 디렉터에 대 한 방화벽 포트 요구 사항은 내부 인터페이스 또는 역방향 프록시의 내부 연결 네트워크에서 디렉터와의 통신을 설정 하는 데 사용 되는 포트로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9fb1-105">Firewall port requirements for a single Director consist of the ports that are used to establish communication with the Director from the internal interface or internal-facing network of the reverse proxy.</span></span> <span data-ttu-id="c9fb1-106">기본적으로 Microsoft Lync Server 2013은 프런트 엔드 풀 및 프런트 엔드 서버 뿐만 아니라 역방향 프록시에서 디렉터로의 포트 HTTP/TCP 8080 및 HTTPS/TCP 4443을 사용할 것으로 예상 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9fb1-106">Microsoft Lync Server 2013 by default expects ports HTTP/TCP 8080 and HTTPS/TCP 4443 to be open from the reverse proxy to the Director, as well as the Front End pool and Front End Server.</span></span> <span data-ttu-id="c9fb1-107">또한에 지 서버 내부 인터페이스에서 디렉터 및 프런트 엔드 풀 및 프런트 엔드 서버로의 SIP (session 착수 프로토콜) 통신이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9fb1-107">Additionally, there must be session initiation protocol (SIP) communication from the Edge Server internal interface to the Director and to the Front End pool and Front End Server.</span></span> <span data-ttu-id="c9fb1-108">SIP 프로토콜은에 지 서버에서 프런트 엔드 풀 및 프런트 엔드 서버로의 SIP/MTLS/TCP 5061를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9fb1-108">The SIP protocol uses SIP/MTLS/TCP 5061 from the Edge Server to the Front End pool and Front End Server.</span></span> <span data-ttu-id="c9fb1-109">디렉터, 프런트 엔드 풀 및 프런트 엔드 서버에서에 지 서버 내부 인터페이스에 대 한 SIP/MTLS/TCP 5061 통신을 허용 하는 규칙을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9fb1-109">A rule that allows SIP/MTLS/TCP 5061 communication from the Director, Front End pool and Front End Server to the Edge Server internal interface must be created as well.</span></span>

### <a name="single-director-ports-and-protocols-for-firewall-definitions"></a><span data-ttu-id="c9fb1-110">방화벽 정의를 위한 단일 디렉터 포트 및 프로토콜</span><span class="sxs-lookup"><span data-stu-id="c9fb1-110">Single Director Ports and Protocols for Firewall Definitions</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c9fb1-111">역할/프로토콜/TCP 또는 UDP/포트</span><span class="sxs-lookup"><span data-stu-id="c9fb1-111">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="c9fb1-112">원본 IP 주소</span><span class="sxs-lookup"><span data-stu-id="c9fb1-112">Source IP address</span></span></th>
<th><span data-ttu-id="c9fb1-113">대상 IP 주소</span><span class="sxs-lookup"><span data-stu-id="c9fb1-113">Destination IP address</span></span></th>
<th><span data-ttu-id="c9fb1-114">참고</span><span class="sxs-lookup"><span data-stu-id="c9fb1-114">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c9fb1-115">HTTP/TCP 8080</span><span class="sxs-lookup"><span data-stu-id="c9fb1-115">HTTP/TCP 8080</span></span></p></td>
<td><p><span data-ttu-id="c9fb1-116">역방향 프록시 내부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c9fb1-116">Reverse proxy internal interface</span></span></p></td>
<td><p><span data-ttu-id="c9fb1-117">Director</span><span class="sxs-lookup"><span data-stu-id="c9fb1-117">Director</span></span></p></td>
<td><p><span data-ttu-id="c9fb1-118">역방향 프록시의 외부 쪽에서 처음 수신 되는 통신은 디렉터 및 프런트 엔드 서버 웹 서비스로 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9fb1-118">Initially received by the external side of the reverse proxy, the communication is sent on to the Director and Front End Server web services</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c9fb1-119">HTTPS/TCP 4443</span><span class="sxs-lookup"><span data-stu-id="c9fb1-119">HTTPS/TCP 4443</span></span></p></td>
<td><p><span data-ttu-id="c9fb1-120">역방향 프록시 내부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c9fb1-120">Reverse proxy internal interface</span></span></p></td>
<td><p><span data-ttu-id="c9fb1-121">Director</span><span class="sxs-lookup"><span data-stu-id="c9fb1-121">Director</span></span></p></td>
<td><p><span data-ttu-id="c9fb1-122">역방향 프록시의 외부 쪽에서 처음 수신 되는 통신은 디렉터 및 프런트 엔드 서버 웹 서비스로 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9fb1-122">Initially received by the external side of the reverse proxy, the communication is sent on to the Director and Front End Server web services</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c9fb1-123">HTTPS/TCP 444</span><span class="sxs-lookup"><span data-stu-id="c9fb1-123">HTTPS/TCP 444</span></span></p></td>
<td><p><span data-ttu-id="c9fb1-124">Director</span><span class="sxs-lookup"><span data-stu-id="c9fb1-124">Director</span></span></p></td>
<td><p><span data-ttu-id="c9fb1-125">프런트 엔드 서버 또는 프런트 엔드 풀</span><span class="sxs-lookup"><span data-stu-id="c9fb1-125">Front End server or Front End pool</span></span></p></td>
<td><p><span data-ttu-id="c9fb1-126">디렉터와 프런트 엔드 서버 간의 서버 간 통신</span><span class="sxs-lookup"><span data-stu-id="c9fb1-126">Inter-server communication between the Director and the Front End Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c9fb1-127">HTTP/TCP 80</span><span class="sxs-lookup"><span data-stu-id="c9fb1-127">HTTP/TCP 80</span></span></p></td>
<td><p><span data-ttu-id="c9fb1-128">내부 클라이언트</span><span class="sxs-lookup"><span data-stu-id="c9fb1-128">Internal Clients</span></span></p></td>
<td><p><span data-ttu-id="c9fb1-129">디렉터 웹 서비스</span><span class="sxs-lookup"><span data-stu-id="c9fb1-129">Director web services</span></span></p></td>
<td><p><span data-ttu-id="c9fb1-130">디렉터는 내부 및 외부 클라이언트에 대해 웹 서비스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9fb1-130">The Director provides web services to internal and external clients.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c9fb1-131">HTTPS/TCP 443</span><span class="sxs-lookup"><span data-stu-id="c9fb1-131">HTTPS/TCP 443</span></span></p></td>
<td><p><span data-ttu-id="c9fb1-132">내부 클라이언트</span><span class="sxs-lookup"><span data-stu-id="c9fb1-132">Internal Clients</span></span></p></td>
<td><p><span data-ttu-id="c9fb1-133">디렉터 웹 서비스</span><span class="sxs-lookup"><span data-stu-id="c9fb1-133">Director web services</span></span></p></td>
<td><p><span data-ttu-id="c9fb1-134">디렉터는 내부 및 외부 클라이언트에 대해 웹 서비스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9fb1-134">The Director provides web services to internal and external clients.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c9fb1-135">SIP/MTLS/TCP 5061</span><span class="sxs-lookup"><span data-stu-id="c9fb1-135">SIP/MTLS/TCP 5061</span></span></p></td>
<td><p><span data-ttu-id="c9fb1-136">에 지 서버 내부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c9fb1-136">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="c9fb1-137">Director</span><span class="sxs-lookup"><span data-stu-id="c9fb1-137">Director</span></span></p></td>
<td><p><span data-ttu-id="c9fb1-138">에 지 서버에서 디렉터 및 프런트 엔드 서버로의 SIP 통신</span><span class="sxs-lookup"><span data-stu-id="c9fb1-138">SIP communication from the Edge Server to the Director, and the Front End Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c9fb1-139">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="c9fb1-139">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="c9fb1-140">모두</span><span class="sxs-lookup"><span data-stu-id="c9fb1-140">Any</span></span></p></td>
<td><p><span data-ttu-id="c9fb1-141">에 지 서버 내부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c9fb1-141">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="c9fb1-142">중앙화된 로깅 서비스 컨트롤러(ClsController.exe) 또는 에이전트(ClasAgent.exe) 명령 또는 로그 수집</span><span class="sxs-lookup"><span data-stu-id="c9fb1-142">Centralized Logging Service controller (ClsController.exe) or agent (ClasAgent.exe)commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c9fb1-143">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="c9fb1-143">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="c9fb1-144">모두</span><span class="sxs-lookup"><span data-stu-id="c9fb1-144">Any</span></span></p></td>
<td><p><span data-ttu-id="c9fb1-145">에 지 서버 내부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c9fb1-145">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="c9fb1-146">중앙화된 로깅 서비스 컨트롤러(ClsController.exe) 또는 에이전트(ClasAgent.exe) 명령 또는 로그 수집</span><span class="sxs-lookup"><span data-stu-id="c9fb1-146">Centralized Logging Service controller (ClsController.exe) or agent (ClasAgent.exe)commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c9fb1-147">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="c9fb1-147">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="c9fb1-148">모두</span><span class="sxs-lookup"><span data-stu-id="c9fb1-148">Any</span></span></p></td>
<td><p><span data-ttu-id="c9fb1-149">에 지 서버 내부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c9fb1-149">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="c9fb1-150">중앙화된 로깅 서비스 컨트롤러(ClsController.exe) 또는 에이전트(ClasAgent.exe) 명령 또는 로그 수집</span><span class="sxs-lookup"><span data-stu-id="c9fb1-150">Centralized Logging Service controller (ClsController.exe) or agent (ClasAgent.exe)commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

