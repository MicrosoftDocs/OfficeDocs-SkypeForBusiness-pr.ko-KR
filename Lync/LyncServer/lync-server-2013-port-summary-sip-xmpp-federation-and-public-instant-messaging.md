---
title: 포트 요약-SIP, XMPP 페더레이션 및 공용 인스턴트 메시징
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
ms.openlocfilehash: e8fd24bab9596f12060c87937d98cc2a57d0c887
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42183711"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="port-summary---sip-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a><span data-ttu-id="814b9-102">포트 요약-SIP, XMPP 페더레이션 및 Lync Server 2013의 공용 인스턴트 메시징</span><span class="sxs-lookup"><span data-stu-id="814b9-102">Port summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="814b9-103">_**마지막으로 수정 된 항목:** 2013-03-15_</span><span class="sxs-lookup"><span data-stu-id="814b9-103">_**Topic Last Modified:** 2013-03-15_</span></span>

<span data-ttu-id="814b9-104">Microsoft Lync Server 2013, Lync Server 2010 및 Office Communications Server와의 페더레이션에 대 한 포트, 프로토콜 및 방화벽 요구 사항은 배포 된에 지 서버의 경우와 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="814b9-104">Port, protocol and firewall requirements for federation with Microsoft Lync Server 2013, Lync Server 2010 and Office Communications Server are similar to those for the deployed Edge Server.</span></span> <span data-ttu-id="814b9-105">클라이언트는 TLS/SIP/TCP 443를 통해 액세스에 지 서비스와의 통신을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="814b9-105">Clients initiate communication with the Access Edge service over TLS/SIP/TCP 443.</span></span> <span data-ttu-id="814b9-106">그러나 페더레이션 파트너는 MTLS/SIP/TCP 5061을 통해 액세스에 지 서비스에 대 한 통신을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="814b9-106">Federated partners however, will initiate communications to the Access Edge service over MTLS/SIP/TCP 5061.</span></span>

<span data-ttu-id="814b9-107">공용 인스턴트 메시징 연결을 지 원하는 데 필요한 포트 및 프로토콜에 대 한 방화벽을 구성 하려면 먼저 SIP/MTLS/TCP 5061는 공용 IM 공급자에서 Lync 클라이언트에 연결 하거나 Lync에서 공용 IM 대화 상대와 연락 하는 연락처의 기능을 고려 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="814b9-107">To configure your firewall for ports and protocols necessary to support public instant messaging connectivity, first note that SIP/MTLS/TCP 5061 is bidirectional to account for the ability of contacts in the public IM provider to contact Lync clients, or for Lync to contact public IM contacts.</span></span>

<span data-ttu-id="814b9-108">Windows Live Messenger는 Lync 클라이언트와의 오디오/비디오 통신에 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="814b9-108">Windows Live Messenger can participate in audio/video communications with Lync clients.</span></span> <span data-ttu-id="814b9-109">이는 외부 사용자로 Lync 클라이언트를 지원 하기 위해 일반적으로 방화벽에 포함 되는 매우 유사한 방화벽 포트 및 프로토콜 구성에 대 한 계정입니다.</span><span class="sxs-lookup"><span data-stu-id="814b9-109">This accounts for the very similar firewall port and protocol configuration that you would typically have on the firewall to support Lync clients as external users.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="814b9-110">이전 보다 Lync는 전 세계의 조직과 조직 간에 연결 하는 강력한 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="814b9-110">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="814b9-111">Windows Live Messenger와 페더레이션 하려면 Lync Standard CAL (클라이언트 액세스 라이선스) 이외의 추가 사용자/장치 라이선스가 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="814b9-111">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard Client Access License (CAL).</span></span> <span data-ttu-id="814b9-112">Lync 사용자가 IM 및 음성을 사용 하 여 수백만 명의 사용자에 게 도달할 수 있도록 하는이 목록에 Skype 페더레이션이 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="814b9-112">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span><BR><span data-ttu-id="814b9-113">Messenger 클라이언트 연락처와의 페더레이션은 공식적인 중국을 제외 하 고는 2013 년 3 월 15 일에 공식적으로 끝납니다.</span><span class="sxs-lookup"><span data-stu-id="814b9-113">Federation with Messenger client contacts will officially end on March 15, 2013, except for mainland China.</span></span> <span data-ttu-id="814b9-114">Skype는 이전에 Messenger를 사용한 페더레이션 사용자의 페더레이션 클라이언트가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="814b9-114">Skype will become the federation client for federated users who previously used Messenger.</span></span>



</div>

<span data-ttu-id="814b9-115">에 지 서버에 배포 된 XMPP (extensible messaging and 거점 protocol) 프록시에 대해 정의 된 포트 및 프로토콜은 XMPP 페더레이션 파트너에서에 지 서버로의 통신을 허용 하 고,에 지 서버에서 XMPP로의 통신도 가능 합니다. 페더레이션 파트너</span><span class="sxs-lookup"><span data-stu-id="814b9-115">The ports and protocols defined for the extensible messaging and presence protocol (XMPP) proxy deployed on the Edge Server allow communications from the XMPP federated partner to the Edge Server, and also allows communication from your Edge Server to the XMPP federated partner.</span></span> <span data-ttu-id="814b9-116">또한 프런트 엔드 서버 또는 프런트 엔드 풀에서에 지 서버 또는에 지 풀에 대 한 내부 연결 방화벽에서 규칙이 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="814b9-116">A rule is also defined on the internal-facing firewall from the Front End Server or Front End pool to the Edge Server or Edge pool.</span></span>

<div>

## <a name="firewall-summary---sip-federation"></a><span data-ttu-id="814b9-117">방화벽 요약-SIP 페더레이션</span><span class="sxs-lookup"><span data-stu-id="814b9-117">Firewall Summary - SIP Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="814b9-118">역할/프로토콜/TCP 또는 UDP/포트</span><span class="sxs-lookup"><span data-stu-id="814b9-118">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="814b9-119">원본 IP 주소</span><span class="sxs-lookup"><span data-stu-id="814b9-119">Source IP address</span></span></th>
<th><span data-ttu-id="814b9-120">대상 IP 주소</span><span class="sxs-lookup"><span data-stu-id="814b9-120">Destination IP address</span></span></th>
<th><span data-ttu-id="814b9-121">Notes</span><span class="sxs-lookup"><span data-stu-id="814b9-121">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="814b9-122">MTLS (액세스/SIP)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="814b9-122">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="814b9-123">액세스 에지 서비스 공용 IP 주소</span><span class="sxs-lookup"><span data-stu-id="814b9-123">Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="814b9-124">모두</span><span class="sxs-lookup"><span data-stu-id="814b9-124">Any</span></span></p></td>
<td><p><span data-ttu-id="814b9-125">SIP를 사용한 페더레이션 및 공용 IM 연결용</span><span class="sxs-lookup"><span data-stu-id="814b9-125">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="814b9-126">방화벽 요약 - 공용 인스턴트 메시징 연결</span><span class="sxs-lookup"><span data-stu-id="814b9-126">Firewall Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="814b9-127">역할/프로토콜/TCP 또는 UDP/포트</span><span class="sxs-lookup"><span data-stu-id="814b9-127">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="814b9-128">원본 IP 주소</span><span class="sxs-lookup"><span data-stu-id="814b9-128">Source IP address</span></span></th>
<th><span data-ttu-id="814b9-129">대상 IP 주소</span><span class="sxs-lookup"><span data-stu-id="814b9-129">Destination IP address</span></span></th>
<th><span data-ttu-id="814b9-130">Notes</span><span class="sxs-lookup"><span data-stu-id="814b9-130">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="814b9-131">MTLS (액세스/SIP)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="814b9-131">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="814b9-132">공용 IM 연결 파트너</span><span class="sxs-lookup"><span data-stu-id="814b9-132">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="814b9-133">에 지 서버 액세스 인터페이스</span><span class="sxs-lookup"><span data-stu-id="814b9-133">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="814b9-134">SIP를 사용 하는 페더레이션 및 공용 IM 연결의 경우</span><span class="sxs-lookup"><span data-stu-id="814b9-134">For federated and public IM connectivity that use SIP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="814b9-135">MTLS (액세스/SIP)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="814b9-135">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="814b9-136">에 지 서버 액세스 인터페이스</span><span class="sxs-lookup"><span data-stu-id="814b9-136">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="814b9-137">공용 IM 연결 파트너</span><span class="sxs-lookup"><span data-stu-id="814b9-137">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="814b9-138">SIP를 사용 하는 페더레이션 및 공용 IM 연결의 경우</span><span class="sxs-lookup"><span data-stu-id="814b9-138">For federated and public IM connectivity that use SIP.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="814b9-139">TLS (액세스/SIP)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="814b9-139">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="814b9-140">클라이언트</span><span class="sxs-lookup"><span data-stu-id="814b9-140">Clients</span></span></p></td>
<td><p><span data-ttu-id="814b9-141">에 지 서버 액세스 인터페이스</span><span class="sxs-lookup"><span data-stu-id="814b9-141">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="814b9-142">외부 사용자 액세스에 대 한 클라이언트-서버 SIP 트래픽</span><span class="sxs-lookup"><span data-stu-id="814b9-142">Client-to-server SIP traffic for external user access.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="814b9-143">A/V/RTP/TCP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="814b9-143">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="814b9-144">에 지 서버 액세스 인터페이스</span><span class="sxs-lookup"><span data-stu-id="814b9-144">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="814b9-145">Live Messenger 클라이언트</span><span class="sxs-lookup"><span data-stu-id="814b9-145">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="814b9-146">공용 IM 연결이 구성된 경우 Windows Live Messenger와의 A/V 세션에 사용됨</span><span class="sxs-lookup"><span data-stu-id="814b9-146">Used for A/V sessions with Windows Live Messenger if public IM connectivity is configured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="814b9-147">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="814b9-147">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="814b9-148">에 지 서버 액세스 인터페이스</span><span class="sxs-lookup"><span data-stu-id="814b9-148">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="814b9-149">Live Messenger 클라이언트</span><span class="sxs-lookup"><span data-stu-id="814b9-149">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="814b9-150">Windows Live Messenger와의 공용 IM 연결에 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="814b9-150">Required for public IM connectivity with Windows Live Messenger.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="814b9-151">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="814b9-151">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="814b9-152">Live Messenger 클라이언트</span><span class="sxs-lookup"><span data-stu-id="814b9-152">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="814b9-153">에 지 서버 액세스 인터페이스</span><span class="sxs-lookup"><span data-stu-id="814b9-153">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="814b9-154">Windows Live Messenger와의 공용 IM 연결에 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="814b9-154">Required for public IM connectivity with Windows Live Messenger.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary---extensible-messaging-and-presence-protocol-xmpp"></a><span data-ttu-id="814b9-155">방화벽 요약-XMPP (Extensible Messaging and 현재 상태 프로토콜)</span><span class="sxs-lookup"><span data-stu-id="814b9-155">Firewall Summary - Extensible Messaging and Presence Protocol (XMPP)</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="814b9-156">프로토콜/TCP 또는 UDP/포트</span><span class="sxs-lookup"><span data-stu-id="814b9-156">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="814b9-157">원본(IP 주소)</span><span class="sxs-lookup"><span data-stu-id="814b9-157">Source (IP address)</span></span></th>
<th><span data-ttu-id="814b9-158">대상(IP 주소)</span><span class="sxs-lookup"><span data-stu-id="814b9-158">Destination (IP address)</span></span></th>
<th><span data-ttu-id="814b9-159">설명</span><span class="sxs-lookup"><span data-stu-id="814b9-159">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="814b9-160">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="814b9-160">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="814b9-161">모두</span><span class="sxs-lookup"><span data-stu-id="814b9-161">Any</span></span></p></td>
<td><p><span data-ttu-id="814b9-162">액세스에 지 서비스 인터페이스 IP 주소</span><span class="sxs-lookup"><span data-stu-id="814b9-162">Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="814b9-163">XMPP용 표준 서버 간 통신 포트입니다.</span><span class="sxs-lookup"><span data-stu-id="814b9-163">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="814b9-164">페더레이션 XMPP 파트너의에 지 서버 XMPP 프록시에 대 한 통신을 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="814b9-164">Allows communication to the Edge Server XMPP proxy from federated XMPP partners</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="814b9-165">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="814b9-165">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="814b9-166">액세스에 지 서비스 인터페이스 IP 주소</span><span class="sxs-lookup"><span data-stu-id="814b9-166">Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="814b9-167">모두</span><span class="sxs-lookup"><span data-stu-id="814b9-167">Any</span></span></p></td>
<td><p><span data-ttu-id="814b9-168">XMPP용 표준 서버 간 통신 포트입니다.</span><span class="sxs-lookup"><span data-stu-id="814b9-168">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="814b9-169">에 지 서버 XMPP 프록시에서 페더레이션 XMPP 파트너와의 통신을 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="814b9-169">Allows communication from the Edge Server XMPP proxy to federated XMPP partners</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="814b9-170">XMPP/MTLS/23456</span><span class="sxs-lookup"><span data-stu-id="814b9-170">XMPP/MTLS/23456</span></span></p></td>
<td><p><span data-ttu-id="814b9-171">모두</span><span class="sxs-lookup"><span data-stu-id="814b9-171">Any</span></span></p></td>
<td><p><span data-ttu-id="814b9-172">내부에 지 서버 인터페이스 IP</span><span class="sxs-lookup"><span data-stu-id="814b9-172">Internal Edge Server Interface IP</span></span></p></td>
<td><p><span data-ttu-id="814b9-173">프런트 엔드 서버 또는 프런트 엔드 풀의 XMPP 게이트웨이에서에 지 서버에 대 한 내부 XMPP 트래픽</span><span class="sxs-lookup"><span data-stu-id="814b9-173">Internal XMPP traffic from the XMPP Gateway on the Front End Server or Front End pool to the Edge Server</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="814b9-174">참고 항목</span><span class="sxs-lookup"><span data-stu-id="814b9-174">See Also</span></span>


[<span data-ttu-id="814b9-175">Lync Server 2013의 외부 사용자 액세스에 대 한 시나리오</span><span class="sxs-lookup"><span data-stu-id="814b9-175">Scenarios for external user access in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-external-user-access.md)  
[<span data-ttu-id="814b9-176">Lync Server 2013에 대 한 외부 A/V 방화벽 및 포트 요구 사항 확인</span><span class="sxs-lookup"><span data-stu-id="814b9-176">Determine external A/V firewall and port requirements for Lync Server 2013</span></span>](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)  


[<span data-ttu-id="814b9-177">Lync Server 2013에서 XMPP 페더레이션 파트너 관리</span><span class="sxs-lookup"><span data-stu-id="814b9-177">Manage XMPP federated partners in Lync Server 2013</span></span>](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

