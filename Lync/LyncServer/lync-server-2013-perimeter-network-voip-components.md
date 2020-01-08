---
title: 'Lync Server 2013: 경계 네트워크 VoIP 구성 요소'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Perimeter network VoIP components
ms:assetid: 74230008-695d-436a-90b9-9cd060c70f7b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398559(v=OCS.15)
ms:contentKeyID: 48184514
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 605cee3c683ea9b22998de6c218978954907ca52
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982899"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="perimeter-network-voip-components-for-lync-server-2013"></a><span data-ttu-id="39cc3-102">Lync Server 2013에 대한 경계 네트워크 VoIP 구성 요소</span><span class="sxs-lookup"><span data-stu-id="39cc3-102">Perimeter network VoIP components for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="39cc3-103">_**마지막으로 수정한 주제:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="39cc3-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="39cc3-104">개인 또는 컨퍼런스 통화에 통합 커뮤니케이션 클라이언트를 사용 하는 외부 발신자는 Edge 서버에서 동료와 음성 통신을 진행 합니다.</span><span class="sxs-lookup"><span data-stu-id="39cc3-104">Outside callers who use unified communications clients for individual or conference calls rely on Edge Server for voice communication with coworkers.</span></span>

<span data-ttu-id="39cc3-105">Edge 서버에서 액세스에 지 서비스는 조직의 방화벽 외부에 있는 Lync 사용자의 통화에 대 한 SIP 신호를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="39cc3-105">On an Edge Server, the Access Edge service provides SIP signaling for calls from Lync users who are outside your organization’s firewall.</span></span> <span data-ttu-id="39cc3-106">A/V Edge 서비스는 NAT와 방화벽의 미디어 이동을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="39cc3-106">The A/V Edge service enables media traversal of NAT and firewalls.</span></span> <span data-ttu-id="39cc3-107">회사 방화벽 외부에서 통합 커뮤니케이션 (UC) 클라이언트를 사용 하는 발신자는 개인 및 전화 회의 둘 다에 대 한 A/V에 지 서비스에 의존 합니다.</span><span class="sxs-lookup"><span data-stu-id="39cc3-107">A caller who uses a unified communications (UC) client from outside the corporate firewall relies on the A/V Edge service for both individual and conference calls.</span></span>

<span data-ttu-id="39cc3-108">A/V 인증 서비스는 A/v에 대 한 인증 서비스를 제공 하는 collocated와 함께 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="39cc3-108">The A/V Authentication service is collocated with, and provides authentication services for, the A/V Edge service.</span></span> <span data-ttu-id="39cc3-109">A/V Edge 서비스에 연결 하려고 하는 외부 사용자는 해당 통화를 통과할 수 있도록 A/V 인증 서비스에서 제공 하는 인증 토큰이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="39cc3-109">Outside users who attempt to connect to the A/V Edge service require an authentication token that is provided by the A/V Authentication Service before their calls can go through.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

