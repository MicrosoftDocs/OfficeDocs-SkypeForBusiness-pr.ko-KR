---
title: 'Lync Server 2013: 향상 된 9-1-1 (E9-1-1) 및 중재 서버'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enhanced 9-1-1 (E9-1-1) and Mediation Server
ms:assetid: d231221f-5596-4a87-a463-269f5bcce65f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398903(v=OCS.15)
ms:contentKeyID: 48185448
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1620d9a4d1625335a52c474d608377bd2529425d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48526805"
---
# <a name="enhanced-9-1-1-e9-1-1-and-mediation-server-in-lync-server-2013"></a><span data-ttu-id="d5ff9-102">Lync Server 2013의 향상 된 9-1-1 (E9-1-1) 및 중재 서버</span><span class="sxs-lookup"><span data-stu-id="d5ff9-102">Enhanced 9-1-1 (E9-1-1) and Mediation Server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d5ff9-103">_**마지막으로 수정 된 항목:** 2012-09-29_</span><span class="sxs-lookup"><span data-stu-id="d5ff9-103">_**Topic Last Modified:** 2012-09-29_</span></span>

<span data-ttu-id="d5ff9-104">중재 서버는 향상 된 9-1-1 (E9-1-1) 서비스 공급자와 올바르게 상호 작용할 수 있도록 확장 된 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5ff9-104">The Mediation Server has extended capabilities so that it can correctly interact with Enhanced 9-1-1 (E9-1-1) service providers.</span></span> <span data-ttu-id="d5ff9-105">중재 서버에서는 특별 한 구성이 필요 하지 않습니다. E9-1-1 상호 작용에 필요한 SIP 확장은 기본적으로 중재 서버의 SIP 프로토콜에 포함 되어 있으며, 게이트웨이 피어와의 상호 작용 (PSTN 게이트웨이, IP-PBX 또는 인터넷 전화 통신 서비스 공급자의 SBC (E9-1-1서비스 공급자 포함))</span><span class="sxs-lookup"><span data-stu-id="d5ff9-105">No special configuration is needed on the Mediation Server; the SIP extensions required for E9-1-1 interaction are, by default, included in the Mediation Server’s SIP protocol for its interactions with a gateway peer (PSTN gateway, IP-PBX, or the SBC of an Internet Telephony Service Provider, including E9-1-1 Service Providers)</span></span>

<span data-ttu-id="d5ff9-106">E9-1-1 서비스 공급자에 대 한 SIP 트렁크를 기존 중재 서버 풀에서 종료 하거나 독립 실행형 중재 서버가 필요한 지는 E9-1-1 SBC가 중재 서버 풀과 상호 작용할 수 있는지 여부에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="d5ff9-106">Whether the SIP trunk to an E9-1-1 Service Provider can be terminated on an existing Mediation Server pool or will require stand-alone Mediation Servers will depend on whether the E9-1-1 SBC can interact with a pool of Mediation Servers.</span></span> <span data-ttu-id="d5ff9-107">자세한 내용은 [Lync Server 2013의 M:n 트렁크](lync-server-2013-m-n-trunk.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="d5ff9-107">For details, see [M:N trunk in Lync Server 2013](lync-server-2013-m-n-trunk.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

