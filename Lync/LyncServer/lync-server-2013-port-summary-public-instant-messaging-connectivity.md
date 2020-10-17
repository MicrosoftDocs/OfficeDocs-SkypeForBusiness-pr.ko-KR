---
title: 'Lync Server 2013: 포트 요약-공용 인스턴트 메시징 연결'
description: 'Lync Server 2013: 포트 요약-공용 인스턴트 메시징 연결'
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
ms.openlocfilehash: 4137b5f92e043dc15dc9aa1f0b9593b4d9f7c2ca
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543064"
---
# <a name="port-summary---public-instant-messaging-connectivity-in-lync-server-2013"></a><span data-ttu-id="9490f-103">포트 요약-Lync Server 2013의 공용 인스턴트 메시징 연결</span><span class="sxs-lookup"><span data-stu-id="9490f-103">Port summary - Public instant messaging connectivity in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9490f-104">_**마지막으로 수정 된 항목:** 2013-02-16_</span><span class="sxs-lookup"><span data-stu-id="9490f-104">_**Topic Last Modified:** 2013-02-16_</span></span>

<span data-ttu-id="9490f-105">공용 인스턴트 메시징 연결을 지 원하는 데 필요한 포트 및 프로토콜에 대 한 방화벽을 구성 하려면 먼저 SIP/MTLS/TCP 5061는 공용 IM 공급자에서 Lync 클라이언트에 연결 하거나 Lync에서 공용 IM 대화 상대와 연락 하는 연락처의 기능을 고려 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="9490f-105">To configure your firewall for ports and protocols necessary to support public instant messaging connectivity, first note that SIP/MTLS/TCP 5061 is bidirectional to account for the ability of contacts in the public IM provider to contact Lync clients, or for Lync to contact public IM contacts.</span></span>

<span data-ttu-id="9490f-106">Windows Live Messenger는 Lync 클라이언트와의 오디오/비디오 통신에 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9490f-106">Windows Live Messenger can participate in audio/video communications with Lync clients.</span></span> <span data-ttu-id="9490f-107">이는 외부 사용자로 Lync 클라이언트를 지원 하기 위해 일반적으로 방화벽에 포함 되는 매우 유사한 방화벽 포트 및 프로토콜 구성에 대 한 계정입니다.</span><span class="sxs-lookup"><span data-stu-id="9490f-107">This accounts for the very similar firewall port and protocol configuration that you would typically have on the firewall to support Lync clients as external users.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="9490f-108">이전 보다 Lync는 전 세계의 조직과 조직 간에 연결 하는 강력한 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="9490f-108">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="9490f-109">Windows Live Messenger와 페더레이션 하려면 Lync Standard CAL (클라이언트 액세스 라이선스) 이외의 추가 사용자/장치 라이선스가 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9490f-109">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard Client Access License (CAL).</span></span> <span data-ttu-id="9490f-110">Lync 사용자가 IM 및 음성을 사용 하 여 수백만 명의 사용자에 게 도달할 수 있도록 하는이 목록에 Skype 페더레이션이 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9490f-110">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span><BR><span data-ttu-id="9490f-111">Messenger 클라이언트 연락처와의 페더레이션은 공식적인 중국을 제외 하 고는 2013 년 3 월 15 일에 공식적으로 끝납니다.</span><span class="sxs-lookup"><span data-stu-id="9490f-111">Federation with Messenger client contacts will officially end on March 15, 2013, except for mainland China.</span></span> <span data-ttu-id="9490f-112">Skype는 이전에 Messenger를 사용한 페더레이션 사용자의 페더레이션 클라이언트가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9490f-112">Skype will become the federation client for federated users who previously used Messenger.</span></span>



</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="9490f-113">방화벽 요약 - 공용 인스턴트 메시징 연결</span><span class="sxs-lookup"><span data-stu-id="9490f-113">Firewall Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9490f-114">역할/프로토콜/TCP 또는 UDP/포트</span><span class="sxs-lookup"><span data-stu-id="9490f-114">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="9490f-115">원본 IP 주소</span><span class="sxs-lookup"><span data-stu-id="9490f-115">Source IP address</span></span></th>
<th><span data-ttu-id="9490f-116">대상 IP 주소</span><span class="sxs-lookup"><span data-stu-id="9490f-116">Destination IP address</span></span></th>
<th><span data-ttu-id="9490f-117">참고</span><span class="sxs-lookup"><span data-stu-id="9490f-117">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9490f-118">MTLS (액세스/SIP)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="9490f-118">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="9490f-119">공용 IM 연결 파트너</span><span class="sxs-lookup"><span data-stu-id="9490f-119">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="9490f-120">에 지 서버 액세스 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9490f-120">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="9490f-121">SIP를 사용 하는 페더레이션 및 공용 IM 연결의 경우</span><span class="sxs-lookup"><span data-stu-id="9490f-121">For federated and public IM connectivity that use SIP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9490f-122">MTLS (액세스/SIP)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="9490f-122">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="9490f-123">에 지 서버 액세스 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9490f-123">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="9490f-124">공용 IM 연결 파트너</span><span class="sxs-lookup"><span data-stu-id="9490f-124">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="9490f-125">SIP를 사용 하는 페더레이션 및 공용 IM 연결의 경우</span><span class="sxs-lookup"><span data-stu-id="9490f-125">For federated and public IM connectivity that use SIP.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9490f-126">TLS (액세스/SIP)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="9490f-126">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="9490f-127">클라이언트</span><span class="sxs-lookup"><span data-stu-id="9490f-127">Clients</span></span></p></td>
<td><p><span data-ttu-id="9490f-128">에 지 서버 액세스 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9490f-128">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="9490f-129">외부 사용자 액세스에 대 한 클라이언트-서버 SIP 트래픽</span><span class="sxs-lookup"><span data-stu-id="9490f-129">Client-to-server SIP traffic for external user access.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9490f-130">A/V/RTP/TCP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="9490f-130">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="9490f-131">에 지 서버 액세스 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9490f-131">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="9490f-132">Live Messenger 클라이언트</span><span class="sxs-lookup"><span data-stu-id="9490f-132">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="9490f-133">공용 IM 연결이 구성된 경우 Windows Live Messenger와의 A/V 세션에 사용됨</span><span class="sxs-lookup"><span data-stu-id="9490f-133">Used for A/V sessions with Windows Live Messenger if public IM connectivity is configured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9490f-134">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="9490f-134">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="9490f-135">에 지 서버 액세스 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9490f-135">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="9490f-136">Live Messenger 클라이언트</span><span class="sxs-lookup"><span data-stu-id="9490f-136">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="9490f-137">Windows Live Messenger와의 공용 IM 연결에 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="9490f-137">Required for public IM connectivity with Windows Live Messenger.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9490f-138">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="9490f-138">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="9490f-139">Live Messenger 클라이언트</span><span class="sxs-lookup"><span data-stu-id="9490f-139">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="9490f-140">에 지 서버 액세스 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9490f-140">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="9490f-141">Windows Live Messenger와의 공용 IM 연결에 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="9490f-141">Required for public IM connectivity with Windows Live Messenger.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="9490f-142">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9490f-142">See Also</span></span>


[<span data-ttu-id="9490f-143">Lync Server 2013의 외부 사용자 액세스에 대 한 시나리오</span><span class="sxs-lookup"><span data-stu-id="9490f-143">Scenarios for external user access in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-external-user-access.md)  
[<span data-ttu-id="9490f-144">Lync Server 2013에 대 한 외부 A/V 방화벽 및 포트 요구 사항 확인</span><span class="sxs-lookup"><span data-stu-id="9490f-144">Determine external A/V firewall and port requirements for Lync Server 2013</span></span>](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

