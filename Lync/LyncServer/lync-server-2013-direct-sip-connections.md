---
title: 'Lync Server 2013: 직접 SIP 연결'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Direct SIP connections
ms:assetid: 0a37737d-9628-4e36-b27b-c134fa5a3882
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398151(v=OCS.15)
ms:contentKeyID: 48183357
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 49bfb60eebc6ef8fd271e43f747a4516b2e359d3
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213394"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="direct-sip-connections-in-lync-server-2013"></a><span data-ttu-id="c4872-102">Lync Server 2013의 직접 SIP 연결</span><span class="sxs-lookup"><span data-stu-id="c4872-102">Direct SIP connections in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c4872-103">_**마지막으로 수정 된 항목:** 2012-08-13_</span><span class="sxs-lookup"><span data-stu-id="c4872-103">_**Topic Last Modified:** 2012-08-13_</span></span>

<span data-ttu-id="c4872-104">*직접 SIP 연결* 을 사용 하 여 Lync Server를 다음 중 하나에 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4872-104">You can use *direct SIP connections* to connect Lync Server to either of the following:</span></span>

  - <span data-ttu-id="c4872-105">IP-PBX (자세한 내용은 [Lync Server 2013의 DIRECT SIP 배포 옵션](lync-server-2013-direct-sip-deployment-options.md)참조).</span><span class="sxs-lookup"><span data-stu-id="c4872-105">An IP-PBX (for details, see [Direct SIP deployment options in Lync Server 2013](lync-server-2013-direct-sip-deployment-options.md)).</span></span>

  - <span data-ttu-id="c4872-106">PSTN 게이트웨이 (자세한 내용은 [Lync Server 2013의 PSTN 게이트웨이 배포 옵션](lync-server-2013-pstn-gateway-deployment-options.md)참조).</span><span class="sxs-lookup"><span data-stu-id="c4872-106">A PSTN gateway (for details, see [PSTN gateway deployment options in Lync Server 2013](lync-server-2013-pstn-gateway-deployment-options.md)).</span></span>

<span data-ttu-id="c4872-107">직접 SIP 연결을 구현하려면 기본적으로 SIP 트렁크를 구현할 때와 동일한 배포 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="c4872-107">To implement a direct SIP connection, you follow essentially the same deployment steps as you would to implement a SIP trunk.</span></span> <span data-ttu-id="c4872-108">두 경우 모두 중재 서버의 외부 인터페이스를 사용 하 여 연결을 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4872-108">In both cases, you implement the connection by using the external interface of a Mediation Server.</span></span> <span data-ttu-id="c4872-109">단, SIP 트렁크는 ITSP 게이트웨이와 같은 외부 엔터티에 연결하고 직접 SIP 연결은 IP-PBX, 공중 전화망(PSTN) 게이트웨이 등 로컬 네트워크의 내부 엔터티에 연결한다는 점이 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="c4872-109">The only difference is that you connect SIP trunks to an external entity, such as an ITSP gateway, and you connect direct SIP connections to an internal entity within your local network, such as an IP-PBX or a public switched telephone network (PSTN) gateway.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="c4872-110">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="c4872-110">In This Section</span></span>

  - [<span data-ttu-id="c4872-111">Lync Server 2013의 직접 SIP 배포 옵션</span><span class="sxs-lookup"><span data-stu-id="c4872-111">Direct SIP deployment options in Lync Server 2013</span></span>](lync-server-2013-direct-sip-deployment-options.md)

  - [<span data-ttu-id="c4872-112">Lync Server 2013의 PSTN 게이트웨이 배포 옵션</span><span class="sxs-lookup"><span data-stu-id="c4872-112">PSTN gateway deployment options in Lync Server 2013</span></span>](lync-server-2013-pstn-gateway-deployment-options.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

