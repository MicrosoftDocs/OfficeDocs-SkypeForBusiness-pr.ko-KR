---
title: 'Lync Server 2013: 미디어 바이패스에 대한 기술 요구 사항'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Technical requirements for media bypass
ms:assetid: 6162a204-0e7c-460a-8eb2-e592c6590a8a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398435(v=OCS.15)
ms:contentKeyID: 48184321
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5f59e0c025935ca8c2cd341549cdb58a44e7dbb8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982289"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-media-bypass-in-lync-server-2013"></a><span data-ttu-id="9be2a-102">Lync Server 2013의 미디어 바이패스에 대한 기술 요구 사항</span><span class="sxs-lookup"><span data-stu-id="9be2a-102">Technical requirements for media bypass in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9be2a-103">_**마지막으로 수정한 주제:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="9be2a-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="9be2a-104">PSTN에 대 한 각 호출에 대해 중재 서버는 중재 서버를 통과 하지 않고 원본에 대 한 Lync 끝점의 미디어를 중재 서버 피어로 직접 보낼 수 있는지 여부를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9be2a-104">For each call to the PSTN, the Mediation Server determines whether media from the Lync endpoint of origin can be sent directly to a Mediation Server peer without traversing the Mediation Server.</span></span> <span data-ttu-id="9be2a-105">피어는 통신 하는 중재 서버 간 트렁크와 연결 된 인터넷 통신 서비스 공급자 (ITSP)의 PSTN 게이트웨이, IP-PBX 또는 SBC (세션 경계 컨트롤러) 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9be2a-105">The peer can be a PSTN gateway, IP-PBX, or Session Border Controller (SBC) at an Internet telephony service provider (ITSP) that is associated with the trunk between the Mediation Server where the call is routed.</span></span>

<span data-ttu-id="9be2a-106">미디어 바이패스는 다음 요구 사항이 충족 되는 경우 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9be2a-106">Media bypass can be employed when the following requirements are met:</span></span>

  - <span data-ttu-id="9be2a-107">중재 서버 피어는 미디어 바이패스에 필요한 기능을 지원 해야 하며, 가장 중요 한 이유는 여러 분기 응답 ("조기 대화" 라고 함)을 처리 하는 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="9be2a-107">A Mediation Server peer must support the necessary capabilities for media bypass, the most important being the ability to handle multiple forked responses (known as “early dialogs”).</span></span> <span data-ttu-id="9be2a-108">게이트웨이나 PBX 제조업체나 ITSP에 게 문의 하 여 게이트웨이, PBX 또는 SBC에 허용 되는 초기 대화 상자의 최대 개수에 대 한 값을 구합니다.</span><span class="sxs-lookup"><span data-stu-id="9be2a-108">Contact the manufacturer of your gateway or PBX, or your ITSP, to obtain the value for the maximum number of early dialogs that the gateway, PBX, or SBC can accept.</span></span>

  - <span data-ttu-id="9be2a-109">중재 서버 피어는 Lync 끝점에서 직접 미디어 트래픽을 수락 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9be2a-109">The Mediation Server peer must accept media traffic directly from Lync endpoints.</span></span> <span data-ttu-id="9be2a-110">대부분의 ITSPs는 SBC가 중재 서버 에서만 트래픽을 수신할 수 있도록 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9be2a-110">Many ITSPs allow their SBC to receive traffic only from the Mediation Server.</span></span> <span data-ttu-id="9be2a-111">해당 SBC가 Lync 끝점에서 직접 미디어 트래픽을 허용 하는지 확인 하려면 ITSP에 문의 하세요.</span><span class="sxs-lookup"><span data-stu-id="9be2a-111">Contact your ITSP to determine whether its SBC accepts media traffic directly from Lync endpoints.</span></span>

  - <span data-ttu-id="9be2a-112">Lync 클라이언트와 중재 서버 피어는 연결 되어 있어야 하며 대역폭 제약 조건이 없는 WAN 링크를 통해 지역에 연결 되는 네트워크 사이트 또는 동일한 네트워크 영역에 위치 하 고 있음을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="9be2a-112">Lync clients and a Mediation Server peer must be well connected, meaning that they are either located in the same network region or at network sites that connect to the region over WAN links that have no bandwidth constraints</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="9be2a-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9be2a-113">See Also</span></span>


[<span data-ttu-id="9be2a-114">Lync Server 2013의 미디어 바이패스 모드</span><span class="sxs-lookup"><span data-stu-id="9be2a-114">Media bypass modes in Lync Server 2013</span></span>](lync-server-2013-media-bypass-modes.md)  
[<span data-ttu-id="9be2a-115">Lync Server 2013의 미디어 바이패스 및 통화 허용 제어 서비스</span><span class="sxs-lookup"><span data-stu-id="9be2a-115">Media bypass and call admission control in Lync Server 2013</span></span>](lync-server-2013-media-bypass-and-call-admission-control.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

