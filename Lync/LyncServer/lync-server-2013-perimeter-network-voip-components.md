---
title: 'Lync Server 2013: 경계 네트워크 VoIP 구성 요소'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Perimeter network VoIP components
ms:assetid: 74230008-695d-436a-90b9-9cd060c70f7b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398559(v=OCS.15)
ms:contentKeyID: 48184514
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d93962357e276d8d4eb69813386bd845cad5acb1
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42215654"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="perimeter-network-voip-components-for-lync-server-2013"></a><span data-ttu-id="121df-102">Lync Server 2013에 대 한 경계 네트워크 VoIP 구성 요소</span><span class="sxs-lookup"><span data-stu-id="121df-102">Perimeter network VoIP components for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="121df-103">_**마지막으로 수정 된 항목:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="121df-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="121df-104">개별 또는 전화 회의에 통합 커뮤니케이션 클라이언트를 사용 하는 외부 발신자는에 지 서버에 연결 하 여 동료와 음성 통신을 합니다.</span><span class="sxs-lookup"><span data-stu-id="121df-104">Outside callers who use unified communications clients for individual or conference calls rely on Edge Server for voice communication with coworkers.</span></span>

<span data-ttu-id="121df-105">에 지 서버에서 액세스에 지 서비스는 조직의 방화벽 외부에 있는 Lync 사용자의 통화에 대 한 SIP 신호를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="121df-105">On an Edge Server, the Access Edge service provides SIP signaling for calls from Lync users who are outside your organization’s firewall.</span></span> <span data-ttu-id="121df-106">A/V 에지 서비스를 사용하면 미디어가 NAT 및 방화벽을 트래버스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="121df-106">The A/V Edge service enables media traversal of NAT and firewalls.</span></span> <span data-ttu-id="121df-107">회사 방화벽 외부에서 UC(통합 통신) 클라이언트를 사용하는 발신자는 개인적인 통화와 전화 회의 모두에 A/V 에지 서비스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="121df-107">A caller who uses a unified communications (UC) client from outside the corporate firewall relies on the A/V Edge service for both individual and conference calls.</span></span>

<span data-ttu-id="121df-p102">A/V 에지 서비스와 함께 A/V 인증 서비스가 배치되어 인증 서비스를 제공합니다. A/V 에지 서비스에 연결하려는 외부 사용자는 A/V 인증 서비스에서 제공한 인증 토큰이 있어야 통화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="121df-p102">The A/V Authentication service is collocated with, and provides authentication services for, the A/V Edge service. Outside users who attempt to connect to the A/V Edge service require an authentication token that is provided by the A/V Authentication Service before their calls can go through.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

