---
title: 'Lync Server 2013: 포트 요약-공용 인스턴트 메시지 연결'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Public instant messaging connectivity
ms:assetid: f46756ec-1401-4ca2-a4a4-5cd28bcfdc7f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618376(v=OCS.15)
ms:contentKeyID: 49105663
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 16430849221631d9b540f5ee51b0a07758a38b05
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725058"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---public-instant-messaging-connectivity-in-lync-server-2013"></a><span data-ttu-id="86cd7-102">포트 요약-Lync Server 2013의 공개 인스턴트 메시지 연결</span><span class="sxs-lookup"><span data-stu-id="86cd7-102">Port summary - Public instant messaging connectivity in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="86cd7-103">_**마지막으로 수정한 주제:** 2013-02-16_</span><span class="sxs-lookup"><span data-stu-id="86cd7-103">_**Topic Last Modified:** 2013-02-16_</span></span>

<span data-ttu-id="86cd7-104">공용 인스턴트 메시징 연결을 지 원하는 데 필요한 포트 및 프로토콜에 대 한 방화벽을 구성 하려면 먼저 SIP/MTLS/TCP 5061에서 Lync 클라이언트에 연락 하거나 Lync에서 공용 메신저 대화 상대에 게 연락할 수 있도록 공용 IM 공급자의 연락처 기능에 대해 양방향으로 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="86cd7-104">To configure your firewall for ports and protocols necessary to support public instant messaging connectivity, first note that SIP/MTLS/TCP 5061 is bidirectional to account for the ability of contacts in the public IM provider to contact Lync clients, or for Lync to contact public IM contacts.</span></span>

<span data-ttu-id="86cd7-105">Windows Live Messenger는 Lync 클라이언트를 사용 하 여 오디오/비디오 통신에 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86cd7-105">Windows Live Messenger can participate in audio/video communications with Lync clients.</span></span> <span data-ttu-id="86cd7-106">이는 일반적으로 방화벽에서 외부 사용자로 Lync 클라이언트를 지원 하기 위해 사용 하는 매우 유사한 방화벽 포트와 프로토콜 구성에 대 한 계정입니다.</span><span class="sxs-lookup"><span data-stu-id="86cd7-106">This accounts for the very similar firewall port and protocol configuration that you would typically have on the firewall to support Lync clients as external users.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="86cd7-107">이전 보다 훨씬 더 많은 수의 Lync는 전세계의 조직과 사용자 간에 연결 하는 강력한 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="86cd7-107">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="86cd7-108">Windows Live Messenger를 사용 하는 페더레이션에서는 Lync Standard CAL (표준 클라이언트 액세스 라이선스) 이외의 추가 사용자/장치 라이선스가 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="86cd7-108">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard Client Access License (CAL).</span></span> <span data-ttu-id="86cd7-109">Skype 페더레이션이이 목록에 추가 되어 Lync 사용자가 IM 및 음성을 사용 하 여 수백만 명의 사용자에 게 연락할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="86cd7-109">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span><BR><span data-ttu-id="86cd7-110">Messenger 클라이언트 연락처와의 페더레이션은 공식적으로 중국을 제외한 2013 년 3 월 15 일에 완료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="86cd7-110">Federation with Messenger client contacts will officially end on March 15, 2013, except for mainland China.</span></span> <span data-ttu-id="86cd7-111">Skype는 이전에 Messenger를 사용 하는 페더레이션 사용자의 페더레이션 클라이언트가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="86cd7-111">Skype will become the federation client for federated users who previously used Messenger.</span></span>



</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="86cd7-112">방화벽 요약-공용 인스턴트 메시지 연결</span><span class="sxs-lookup"><span data-stu-id="86cd7-112">Firewall Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="86cd7-113">역할/프로토콜/TCP 또는 UDP/포트</span><span class="sxs-lookup"><span data-stu-id="86cd7-113">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="86cd7-114">원본 IP 주소</span><span class="sxs-lookup"><span data-stu-id="86cd7-114">Source IP address</span></span></th>
<th><span data-ttu-id="86cd7-115">대상 IP 주소</span><span class="sxs-lookup"><span data-stu-id="86cd7-115">Destination IP address</span></span></th>
<th><span data-ttu-id="86cd7-116">상속자</span><span class="sxs-lookup"><span data-stu-id="86cd7-116">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="86cd7-117">MTLS (액세스/SIP)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="86cd7-117">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="86cd7-118">공용 IM 연결 파트너</span><span class="sxs-lookup"><span data-stu-id="86cd7-118">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="86cd7-119">Edge 서버 액세스 인터페이스</span><span class="sxs-lookup"><span data-stu-id="86cd7-119">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="86cd7-120">SIP를 사용 하는 페더레이션 및 공용 인스턴트 메시지 연결</span><span class="sxs-lookup"><span data-stu-id="86cd7-120">For federated and public IM connectivity that use SIP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86cd7-121">MTLS (액세스/SIP)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="86cd7-121">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="86cd7-122">Edge 서버 액세스 인터페이스</span><span class="sxs-lookup"><span data-stu-id="86cd7-122">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="86cd7-123">공용 IM 연결 파트너</span><span class="sxs-lookup"><span data-stu-id="86cd7-123">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="86cd7-124">SIP를 사용 하는 페더레이션 및 공용 인스턴트 메시지 연결</span><span class="sxs-lookup"><span data-stu-id="86cd7-124">For federated and public IM connectivity that use SIP.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86cd7-125">TLS (액세스/SIP)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="86cd7-125">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="86cd7-126">클라이언트</span><span class="sxs-lookup"><span data-stu-id="86cd7-126">Clients</span></span></p></td>
<td><p><span data-ttu-id="86cd7-127">Edge 서버 액세스 인터페이스</span><span class="sxs-lookup"><span data-stu-id="86cd7-127">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="86cd7-128">외부 사용자 액세스를 위한 클라이언트 대 서버 SIP 트래픽.</span><span class="sxs-lookup"><span data-stu-id="86cd7-128">Client-to-server SIP traffic for external user access.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86cd7-129">A/V/RTP/TCP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="86cd7-129">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="86cd7-130">Edge 서버 액세스 인터페이스</span><span class="sxs-lookup"><span data-stu-id="86cd7-130">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="86cd7-131">실시간 메신저 클라이언트</span><span class="sxs-lookup"><span data-stu-id="86cd7-131">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="86cd7-132">공용 메신저 연결이 구성 되어 있는 경우 Windows Live Messenger를 사용 하 여 A/V 세션에 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="86cd7-132">Used for A/V sessions with Windows Live Messenger if public IM connectivity is configured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86cd7-133">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="86cd7-133">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="86cd7-134">Edge 서버 액세스 인터페이스</span><span class="sxs-lookup"><span data-stu-id="86cd7-134">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="86cd7-135">실시간 메신저 클라이언트</span><span class="sxs-lookup"><span data-stu-id="86cd7-135">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="86cd7-136">Windows Live Messenger를 사용 하는 공용 메신저 연결에 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="86cd7-136">Required for public IM connectivity with Windows Live Messenger.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86cd7-137">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="86cd7-137">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="86cd7-138">실시간 메신저 클라이언트</span><span class="sxs-lookup"><span data-stu-id="86cd7-138">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="86cd7-139">Edge 서버 액세스 인터페이스</span><span class="sxs-lookup"><span data-stu-id="86cd7-139">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="86cd7-140">Windows Live Messenger를 사용 하는 공용 메신저 연결에 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="86cd7-140">Required for public IM connectivity with Windows Live Messenger.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="86cd7-141">참고 항목</span><span class="sxs-lookup"><span data-stu-id="86cd7-141">See Also</span></span>


[<span data-ttu-id="86cd7-142">Lync Server 2013의 외부 사용자 액세스에 대한 시나리오</span><span class="sxs-lookup"><span data-stu-id="86cd7-142">Scenarios for external user access in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-external-user-access.md)  
[<span data-ttu-id="86cd7-143">Lync Server 2013에 대한 외부 A/V 방화벽 및 포트 요구 사항 확인</span><span class="sxs-lookup"><span data-stu-id="86cd7-143">Determine external A/V firewall and port requirements for Lync Server 2013</span></span>](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

