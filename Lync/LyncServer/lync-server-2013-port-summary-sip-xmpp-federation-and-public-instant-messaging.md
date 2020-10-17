---
title: 포트 요약-SIP, XMPP 페더레이션 및 공용 인스턴트 메시징
description: 포트 요약-SIP, XMPP 페더레이션 및 공용 인스턴트 메시징입니다.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - SIP, XMPP federation, and public instant messaging
ms:assetid: ab05bdd6-e9b0-4b1b-9dd9-29ab88e8befe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618373(v=OCS.15)
ms:contentKeyID: 49105660
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7c58dbf7bdd56b4678d56f96a11332219bb40c17
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566361"
---
# <a name="port-summary---sip-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a><span data-ttu-id="a6588-103">포트 요약-SIP, XMPP 페더레이션 및 Lync Server 2013의 공용 인스턴트 메시징</span><span class="sxs-lookup"><span data-stu-id="a6588-103">Port summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a6588-104">_**마지막으로 수정 된 항목:** 2013-03-15_</span><span class="sxs-lookup"><span data-stu-id="a6588-104">_**Topic Last Modified:** 2013-03-15_</span></span>

<span data-ttu-id="a6588-105">Microsoft Lync Server 2013, Lync Server 2010 및 Office Communications Server와의 페더레이션에 대 한 포트, 프로토콜 및 방화벽 요구 사항은 배포 된에 지 서버의 경우와 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="a6588-105">Port, protocol and firewall requirements for federation with Microsoft Lync Server 2013, Lync Server 2010 and Office Communications Server are similar to those for the deployed Edge Server.</span></span> <span data-ttu-id="a6588-106">클라이언트는 TLS/SIP/TCP 443를 통해 액세스에 지 서비스와의 통신을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6588-106">Clients initiate communication with the Access Edge service over TLS/SIP/TCP 443.</span></span> <span data-ttu-id="a6588-107">그러나 페더레이션 파트너는 MTLS/SIP/TCP 5061을 통해 액세스에 지 서비스에 대 한 통신을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6588-107">Federated partners however, will initiate communications to the Access Edge service over MTLS/SIP/TCP 5061.</span></span>

<span data-ttu-id="a6588-108">공용 인스턴트 메시징 연결을 지 원하는 데 필요한 포트 및 프로토콜에 대 한 방화벽을 구성 하려면 먼저 SIP/MTLS/TCP 5061는 공용 IM 공급자에서 Lync 클라이언트에 연결 하거나 Lync에서 공용 IM 대화 상대와 연락 하는 연락처의 기능을 고려 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="a6588-108">To configure your firewall for ports and protocols necessary to support public instant messaging connectivity, first note that SIP/MTLS/TCP 5061 is bidirectional to account for the ability of contacts in the public IM provider to contact Lync clients, or for Lync to contact public IM contacts.</span></span>

<span data-ttu-id="a6588-109">Windows Live Messenger는 Lync 클라이언트와의 오디오/비디오 통신에 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6588-109">Windows Live Messenger can participate in audio/video communications with Lync clients.</span></span> <span data-ttu-id="a6588-110">이는 외부 사용자로 Lync 클라이언트를 지원 하기 위해 일반적으로 방화벽에 포함 되는 매우 유사한 방화벽 포트 및 프로토콜 구성에 대 한 계정입니다.</span><span class="sxs-lookup"><span data-stu-id="a6588-110">This accounts for the very similar firewall port and protocol configuration that you would typically have on the firewall to support Lync clients as external users.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="a6588-111">이전 보다 Lync는 전 세계의 조직과 조직 간에 연결 하는 강력한 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="a6588-111">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="a6588-112">Windows Live Messenger와 페더레이션 하려면 Lync Standard CAL (클라이언트 액세스 라이선스) 이외의 추가 사용자/장치 라이선스가 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a6588-112">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard Client Access License (CAL).</span></span> <span data-ttu-id="a6588-113">Lync 사용자가 IM 및 음성을 사용 하 여 수백만 명의 사용자에 게 도달할 수 있도록 하는이 목록에 Skype 페더레이션이 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6588-113">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span><BR><span data-ttu-id="a6588-114">Messenger 클라이언트 연락처와의 페더레이션은 공식적인 중국을 제외 하 고는 2013 년 3 월 15 일에 공식적으로 끝납니다.</span><span class="sxs-lookup"><span data-stu-id="a6588-114">Federation with Messenger client contacts will officially end on March 15, 2013, except for mainland China.</span></span> <span data-ttu-id="a6588-115">Skype는 이전에 Messenger를 사용한 페더레이션 사용자의 페더레이션 클라이언트가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6588-115">Skype will become the federation client for federated users who previously used Messenger.</span></span>



</div>

<span data-ttu-id="a6588-116">에 지 서버에 배포 된 XMPP (extensible messaging and 거점 protocol) 프록시에 대해 정의 된 포트 및 프로토콜은 XMPP 페더레이션 파트너에서에 지 서버로의 통신을 허용 하 고,에 지 서버에서 XMPP 페더레이션 파트너와의 통신도 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6588-116">The ports and protocols defined for the extensible messaging and presence protocol (XMPP) proxy deployed on the Edge Server allow communications from the XMPP federated partner to the Edge Server, and also allows communication from your Edge Server to the XMPP federated partner.</span></span> <span data-ttu-id="a6588-117">또한 프런트 엔드 서버 또는 프런트 엔드 풀에서에 지 서버 또는에 지 풀에 대 한 내부 연결 방화벽에서 규칙이 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6588-117">A rule is also defined on the internal-facing firewall from the Front End Server or Front End pool to the Edge Server or Edge pool.</span></span>

<div>

## <a name="firewall-summary---sip-federation"></a><span data-ttu-id="a6588-118">방화벽 요약-SIP 페더레이션</span><span class="sxs-lookup"><span data-stu-id="a6588-118">Firewall Summary - SIP Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a6588-119">역할/프로토콜/TCP 또는 UDP/포트</span><span class="sxs-lookup"><span data-stu-id="a6588-119">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="a6588-120">원본 IP 주소</span><span class="sxs-lookup"><span data-stu-id="a6588-120">Source IP address</span></span></th>
<th><span data-ttu-id="a6588-121">대상 IP 주소</span><span class="sxs-lookup"><span data-stu-id="a6588-121">Destination IP address</span></span></th>
<th><span data-ttu-id="a6588-122">참고</span><span class="sxs-lookup"><span data-stu-id="a6588-122">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a6588-123">MTLS (액세스/SIP)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="a6588-123">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="a6588-124">액세스 에지 서비스 공용 IP 주소</span><span class="sxs-lookup"><span data-stu-id="a6588-124">Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="a6588-125">모두</span><span class="sxs-lookup"><span data-stu-id="a6588-125">Any</span></span></p></td>
<td><p><span data-ttu-id="a6588-126">SIP를 사용한 페더레이션 및 공용 IM 연결용</span><span class="sxs-lookup"><span data-stu-id="a6588-126">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="a6588-127">방화벽 요약 - 공용 인스턴트 메시징 연결</span><span class="sxs-lookup"><span data-stu-id="a6588-127">Firewall Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a6588-128">역할/프로토콜/TCP 또는 UDP/포트</span><span class="sxs-lookup"><span data-stu-id="a6588-128">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="a6588-129">원본 IP 주소</span><span class="sxs-lookup"><span data-stu-id="a6588-129">Source IP address</span></span></th>
<th><span data-ttu-id="a6588-130">대상 IP 주소</span><span class="sxs-lookup"><span data-stu-id="a6588-130">Destination IP address</span></span></th>
<th><span data-ttu-id="a6588-131">참고</span><span class="sxs-lookup"><span data-stu-id="a6588-131">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a6588-132">MTLS (액세스/SIP)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="a6588-132">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="a6588-133">공용 IM 연결 파트너</span><span class="sxs-lookup"><span data-stu-id="a6588-133">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="a6588-134">에 지 서버 액세스 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a6588-134">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="a6588-135">SIP를 사용 하는 페더레이션 및 공용 IM 연결의 경우</span><span class="sxs-lookup"><span data-stu-id="a6588-135">For federated and public IM connectivity that use SIP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a6588-136">MTLS (액세스/SIP)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="a6588-136">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="a6588-137">에 지 서버 액세스 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a6588-137">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="a6588-138">공용 IM 연결 파트너</span><span class="sxs-lookup"><span data-stu-id="a6588-138">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="a6588-139">SIP를 사용 하는 페더레이션 및 공용 IM 연결의 경우</span><span class="sxs-lookup"><span data-stu-id="a6588-139">For federated and public IM connectivity that use SIP.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a6588-140">TLS (액세스/SIP)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="a6588-140">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="a6588-141">클라이언트</span><span class="sxs-lookup"><span data-stu-id="a6588-141">Clients</span></span></p></td>
<td><p><span data-ttu-id="a6588-142">에 지 서버 액세스 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a6588-142">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="a6588-143">외부 사용자 액세스에 대 한 클라이언트-서버 SIP 트래픽</span><span class="sxs-lookup"><span data-stu-id="a6588-143">Client-to-server SIP traffic for external user access.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a6588-144">A/V/RTP/TCP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="a6588-144">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="a6588-145">에 지 서버 액세스 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a6588-145">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="a6588-146">Live Messenger 클라이언트</span><span class="sxs-lookup"><span data-stu-id="a6588-146">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="a6588-147">공용 IM 연결이 구성된 경우 Windows Live Messenger와의 A/V 세션에 사용됨</span><span class="sxs-lookup"><span data-stu-id="a6588-147">Used for A/V sessions with Windows Live Messenger if public IM connectivity is configured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a6588-148">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="a6588-148">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="a6588-149">에 지 서버 액세스 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a6588-149">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="a6588-150">Live Messenger 클라이언트</span><span class="sxs-lookup"><span data-stu-id="a6588-150">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="a6588-151">Windows Live Messenger와의 공용 IM 연결에 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6588-151">Required for public IM connectivity with Windows Live Messenger.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a6588-152">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="a6588-152">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="a6588-153">Live Messenger 클라이언트</span><span class="sxs-lookup"><span data-stu-id="a6588-153">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="a6588-154">에 지 서버 액세스 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a6588-154">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="a6588-155">Windows Live Messenger와의 공용 IM 연결에 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6588-155">Required for public IM connectivity with Windows Live Messenger.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary---extensible-messaging-and-presence-protocol-xmpp"></a><span data-ttu-id="a6588-156">방화벽 요약-XMPP (Extensible Messaging and 현재 상태 프로토콜)</span><span class="sxs-lookup"><span data-stu-id="a6588-156">Firewall Summary - Extensible Messaging and Presence Protocol (XMPP)</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a6588-157">프로토콜/TCP 또는 UDP/포트</span><span class="sxs-lookup"><span data-stu-id="a6588-157">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="a6588-158">원본(IP 주소)</span><span class="sxs-lookup"><span data-stu-id="a6588-158">Source (IP address)</span></span></th>
<th><span data-ttu-id="a6588-159">대상(IP 주소)</span><span class="sxs-lookup"><span data-stu-id="a6588-159">Destination (IP address)</span></span></th>
<th><span data-ttu-id="a6588-160">설명</span><span class="sxs-lookup"><span data-stu-id="a6588-160">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a6588-161">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="a6588-161">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="a6588-162">모두</span><span class="sxs-lookup"><span data-stu-id="a6588-162">Any</span></span></p></td>
<td><p><span data-ttu-id="a6588-163">액세스에 지 서비스 인터페이스 IP 주소</span><span class="sxs-lookup"><span data-stu-id="a6588-163">Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="a6588-164">XMPP용 표준 서버 간 통신 포트입니다.</span><span class="sxs-lookup"><span data-stu-id="a6588-164">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="a6588-165">페더레이션 XMPP 파트너의에 지 서버 XMPP 프록시에 대 한 통신을 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6588-165">Allows communication to the Edge Server XMPP proxy from federated XMPP partners</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a6588-166">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="a6588-166">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="a6588-167">액세스에 지 서비스 인터페이스 IP 주소</span><span class="sxs-lookup"><span data-stu-id="a6588-167">Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="a6588-168">모두</span><span class="sxs-lookup"><span data-stu-id="a6588-168">Any</span></span></p></td>
<td><p><span data-ttu-id="a6588-169">XMPP용 표준 서버 간 통신 포트입니다.</span><span class="sxs-lookup"><span data-stu-id="a6588-169">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="a6588-170">에 지 서버 XMPP 프록시에서 페더레이션 XMPP 파트너와의 통신을 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6588-170">Allows communication from the Edge Server XMPP proxy to federated XMPP partners</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a6588-171">XMPP/MTLS/23456</span><span class="sxs-lookup"><span data-stu-id="a6588-171">XMPP/MTLS/23456</span></span></p></td>
<td><p><span data-ttu-id="a6588-172">모두</span><span class="sxs-lookup"><span data-stu-id="a6588-172">Any</span></span></p></td>
<td><p><span data-ttu-id="a6588-173">내부에 지 서버 인터페이스 IP</span><span class="sxs-lookup"><span data-stu-id="a6588-173">Internal Edge Server Interface IP</span></span></p></td>
<td><p><span data-ttu-id="a6588-174">프런트 엔드 서버 또는 프런트 엔드 풀의 XMPP 게이트웨이에서에 지 서버에 대 한 내부 XMPP 트래픽</span><span class="sxs-lookup"><span data-stu-id="a6588-174">Internal XMPP traffic from the XMPP Gateway on the Front End Server or Front End pool to the Edge Server</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a6588-175">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a6588-175">See Also</span></span>


[<span data-ttu-id="a6588-176">Lync Server 2013의 외부 사용자 액세스에 대 한 시나리오</span><span class="sxs-lookup"><span data-stu-id="a6588-176">Scenarios for external user access in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-external-user-access.md)  
[<span data-ttu-id="a6588-177">Lync Server 2013에 대 한 외부 A/V 방화벽 및 포트 요구 사항 확인</span><span class="sxs-lookup"><span data-stu-id="a6588-177">Determine external A/V firewall and port requirements for Lync Server 2013</span></span>](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)  


[<span data-ttu-id="a6588-178">Lync Server 2013에서 XMPP 페더레이션 파트너 관리</span><span class="sxs-lookup"><span data-stu-id="a6588-178">Manage XMPP federated partners in Lync Server 2013</span></span>](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

