---
title: Lync Server 2013 직접 SIP 연결 지원
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Direct SIP connections support
ms:assetid: 2107b5b1-b619-4c10-a7db-81d0b9c7f8bf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398289(v=OCS.15)
ms:contentKeyID: 48183611
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9b987069b4b242ab91cf1b4e6a6cadf4113ed387
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762266"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="direct-sip-connections-support-in-lync-server-2013"></a><span data-ttu-id="c4cac-102">Lync Server 2013의 직접 SIP 연결 지원</span><span class="sxs-lookup"><span data-stu-id="c4cac-102">Direct SIP connections support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c4cac-103">_**마지막으로 수정한 주제:** 2012-06-29_</span><span class="sxs-lookup"><span data-stu-id="c4cac-103">_**Topic Last Modified:** 2012-06-29_</span></span>

<span data-ttu-id="c4cac-104">Lync Server 2013는 direct SIP 연결을 사용 하 여 Lync Server 2013을 다음 중 하나에 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4cac-104">Lync Server 2013 supports the use of direct SIP connections to connect Lync Server 2013 to either of the following:</span></span>

  - <span data-ttu-id="c4cac-105">IP-PBX</span><span class="sxs-lookup"><span data-stu-id="c4cac-105">An IP-PBX</span></span>

  - <span data-ttu-id="c4cac-106">PSTN 게이트웨이</span><span class="sxs-lookup"><span data-stu-id="c4cac-106">A PSTN gateway</span></span>

<span data-ttu-id="c4cac-107">Lync Server 2013 풀의 중재 서버는 전화 통신 서비스 공급자가 제공 하는 여러 게이트웨이, 세션 경계 컨트롤러 (SBCs) 또는 그에 대 한 일부 조합을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4cac-107">The Mediation Servers in a Lync Server 2013 pool can control multiple gateways, Session Border Controllers (SBCs) provided by telephony service providers, or some combination thereof.</span></span> <span data-ttu-id="c4cac-108">또한 풀의 여러 중재 서버는 단일 게이트웨이와 상호 작용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4cac-108">Additionally, multiple Mediation Servers in the pool can interact with a single gateway.</span></span>

<span data-ttu-id="c4cac-109">엔터프라이즈 전화 통신 인프라에 대 한 Microsoft 통합 커뮤니케이션 오픈 상호 운용성 프로그램을 사용 하 여 검증 된 PSTN 게이트웨이, IP-Pbx 및 SIP 트렁크 서비스를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4cac-109">You can use the Microsoft Unified Communications Open Interoperability Program for enterprise telephony infrastructure to find qualified PSTN gateways, IP-PBXs, and SIP trunking services.</span></span> <span data-ttu-id="c4cac-110">자세한 내용은에서 [http://go.microsoft.com/fwlink/p/?linkId=203309](http://go.microsoft.com/fwlink/p/?linkid=203309)Microsoft 통합 커뮤니케이션 오픈 상호 운용성 프로그램 웹 사이트를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c4cac-110">For details, see the Microsoft Unified Communications Open Interoperability Program website at [http://go.microsoft.com/fwlink/p/?linkId=203309](http://go.microsoft.com/fwlink/p/?linkid=203309).</span></span>

<span data-ttu-id="c4cac-111">직접 SIP 연결에 대 한 토폴로지 및 배포 옵션에 대 한 자세한 내용은 계획 설명서의 [Lync Server 2013에서 직접 sip 연결](lync-server-2013-direct-sip-connections.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c4cac-111">For details about the topology and deployment options for direct SIP connections, see [Direct SIP connections in Lync Server 2013](lync-server-2013-direct-sip-connections.md) in the Planning documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

