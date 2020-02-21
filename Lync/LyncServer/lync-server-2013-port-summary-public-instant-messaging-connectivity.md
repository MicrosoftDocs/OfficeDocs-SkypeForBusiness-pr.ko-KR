---
title: 'Lync Server 2013: 포트 요약-공용 인스턴트 메시징 연결'
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
ms.openlocfilehash: bfc057f4d41104dcebc89003ff77eb75622ee3c1
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42183931"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="port-summary---public-instant-messaging-connectivity-in-lync-server-2013"></a><span data-ttu-id="6998a-102">포트 요약-Lync Server 2013의 공용 인스턴트 메시징 연결</span><span class="sxs-lookup"><span data-stu-id="6998a-102">Port summary - Public instant messaging connectivity in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6998a-103">_**마지막으로 수정 된 항목:** 2013-02-16_</span><span class="sxs-lookup"><span data-stu-id="6998a-103">_**Topic Last Modified:** 2013-02-16_</span></span>

<span data-ttu-id="6998a-104">공용 인스턴트 메시징 연결을 지 원하는 데 필요한 포트 및 프로토콜에 대 한 방화벽을 구성 하려면 먼저 SIP/MTLS/TCP 5061는 공용 IM 공급자에서 Lync 클라이언트에 연결 하거나 Lync에서 공용 IM 대화 상대와 연락 하는 연락처의 기능을 고려 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="6998a-104">To configure your firewall for ports and protocols necessary to support public instant messaging connectivity, first note that SIP/MTLS/TCP 5061 is bidirectional to account for the ability of contacts in the public IM provider to contact Lync clients, or for Lync to contact public IM contacts.</span></span>

<span data-ttu-id="6998a-105">Windows Live Messenger는 Lync 클라이언트와의 오디오/비디오 통신에 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6998a-105">Windows Live Messenger can participate in audio/video communications with Lync clients.</span></span> <span data-ttu-id="6998a-106">이는 외부 사용자로 Lync 클라이언트를 지원 하기 위해 일반적으로 방화벽에 포함 되는 매우 유사한 방화벽 포트 및 프로토콜 구성에 대 한 계정입니다.</span><span class="sxs-lookup"><span data-stu-id="6998a-106">This accounts for the very similar firewall port and protocol configuration that you would typically have on the firewall to support Lync clients as external users.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="6998a-107">이전 보다 Lync는 전 세계의 조직과 조직 간에 연결 하는 강력한 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="6998a-107">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="6998a-108">Windows Live Messenger와 페더레이션 하려면 Lync Standard CAL (클라이언트 액세스 라이선스) 이외의 추가 사용자/장치 라이선스가 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6998a-108">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard Client Access License (CAL).</span></span> <span data-ttu-id="6998a-109">Lync 사용자가 IM 및 음성을 사용 하 여 수백만 명의 사용자에 게 도달할 수 있도록 하는이 목록에 Skype 페더레이션이 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6998a-109">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span><BR><span data-ttu-id="6998a-110">Messenger 클라이언트 연락처와의 페더레이션은 공식적인 중국을 제외 하 고는 2013 년 3 월 15 일에 공식적으로 끝납니다.</span><span class="sxs-lookup"><span data-stu-id="6998a-110">Federation with Messenger client contacts will officially end on March 15, 2013, except for mainland China.</span></span> <span data-ttu-id="6998a-111">Skype는 이전에 Messenger를 사용한 페더레이션 사용자의 페더레이션 클라이언트가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6998a-111">Skype will become the federation client for federated users who previously used Messenger.</span></span>



</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="6998a-112">방화벽 요약 - 공용 인스턴트 메시징 연결</span><span class="sxs-lookup"><span data-stu-id="6998a-112">Firewall Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6998a-113">역할/프로토콜/TCP 또는 UDP/포트</span><span class="sxs-lookup"><span data-stu-id="6998a-113">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="6998a-114">원본 IP 주소</span><span class="sxs-lookup"><span data-stu-id="6998a-114">Source IP address</span></span></th>
<th><span data-ttu-id="6998a-115">대상 IP 주소</span><span class="sxs-lookup"><span data-stu-id="6998a-115">Destination IP address</span></span></th>
<th><span data-ttu-id="6998a-116">Notes</span><span class="sxs-lookup"><span data-stu-id="6998a-116">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6998a-117">MTLS (액세스/SIP)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="6998a-117">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="6998a-118">공용 IM 연결 파트너</span><span class="sxs-lookup"><span data-stu-id="6998a-118">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="6998a-119">에 지 서버 액세스 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6998a-119">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="6998a-120">SIP를 사용 하는 페더레이션 및 공용 IM 연결의 경우</span><span class="sxs-lookup"><span data-stu-id="6998a-120">For federated and public IM connectivity that use SIP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6998a-121">MTLS (액세스/SIP)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="6998a-121">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="6998a-122">에 지 서버 액세스 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6998a-122">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="6998a-123">공용 IM 연결 파트너</span><span class="sxs-lookup"><span data-stu-id="6998a-123">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="6998a-124">SIP를 사용 하는 페더레이션 및 공용 IM 연결의 경우</span><span class="sxs-lookup"><span data-stu-id="6998a-124">For federated and public IM connectivity that use SIP.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6998a-125">TLS (액세스/SIP)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="6998a-125">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="6998a-126">클라이언트</span><span class="sxs-lookup"><span data-stu-id="6998a-126">Clients</span></span></p></td>
<td><p><span data-ttu-id="6998a-127">에 지 서버 액세스 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6998a-127">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="6998a-128">외부 사용자 액세스에 대 한 클라이언트-서버 SIP 트래픽</span><span class="sxs-lookup"><span data-stu-id="6998a-128">Client-to-server SIP traffic for external user access.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6998a-129">A/V/RTP/TCP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="6998a-129">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="6998a-130">에 지 서버 액세스 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6998a-130">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="6998a-131">Live Messenger 클라이언트</span><span class="sxs-lookup"><span data-stu-id="6998a-131">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="6998a-132">공용 IM 연결이 구성된 경우 Windows Live Messenger와의 A/V 세션에 사용됨</span><span class="sxs-lookup"><span data-stu-id="6998a-132">Used for A/V sessions with Windows Live Messenger if public IM connectivity is configured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6998a-133">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="6998a-133">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="6998a-134">에 지 서버 액세스 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6998a-134">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="6998a-135">Live Messenger 클라이언트</span><span class="sxs-lookup"><span data-stu-id="6998a-135">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="6998a-136">Windows Live Messenger와의 공용 IM 연결에 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="6998a-136">Required for public IM connectivity with Windows Live Messenger.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6998a-137">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="6998a-137">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="6998a-138">Live Messenger 클라이언트</span><span class="sxs-lookup"><span data-stu-id="6998a-138">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="6998a-139">에 지 서버 액세스 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6998a-139">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="6998a-140">Windows Live Messenger와의 공용 IM 연결에 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="6998a-140">Required for public IM connectivity with Windows Live Messenger.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="6998a-141">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6998a-141">See Also</span></span>


[<span data-ttu-id="6998a-142">Lync Server 2013의 외부 사용자 액세스에 대 한 시나리오</span><span class="sxs-lookup"><span data-stu-id="6998a-142">Scenarios for external user access in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-external-user-access.md)  
[<span data-ttu-id="6998a-143">Lync Server 2013에 대 한 외부 A/V 방화벽 및 포트 요구 사항 확인</span><span class="sxs-lookup"><span data-stu-id="6998a-143">Determine external A/V firewall and port requirements for Lync Server 2013</span></span>](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

