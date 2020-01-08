---
title: 'Lync Server 2013: 새로운 트렁크 기능'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: New trunk feature
ms:assetid: 9b398bc8-2760-4218-b1a4-89b9694b1171
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688152(v=OCS.15)
ms:contentKeyID: 49733755
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 18296a9d1da060c9faaf8d4c765c38403a9cb224
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984661"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-trunk-feature-in-lync-server-2013"></a><span data-ttu-id="45a4d-102">Lync Server 2013의 새로운 트렁크 기능</span><span class="sxs-lookup"><span data-stu-id="45a4d-102">New trunk feature in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="45a4d-103">_**마지막으로 수정한 주제:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="45a4d-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="45a4d-104">Microsoft Lync Server 2013에서 중재 서버와 게이트웨이 간의 여러 trunks를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45a4d-104">In Microsoft Lync Server 2013, multiple trunks between a Mediation Server and a gateway can be defined.</span></span> <span data-ttu-id="45a4d-105">Microsoft Lync Server 2010는 중재 서버와 PSTN 게이트웨이 간의 단일 트렁크에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45a4d-105">Microsoft Lync Server 2010 only allowed for a single trunk between a Mediation Server and a PSTN gateway.</span></span> <span data-ttu-id="45a4d-106">이 기능은 추가 trunks을 정의 하는 유연성을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="45a4d-106">This feature provides the flexibility to define additional trunks.</span></span> <span data-ttu-id="45a4d-107">트렁크는 중재 서버 FQDN과 수신 포트, PSTN 게이트웨이 FQDN 및 수신 대기 포트 간의 논리적 연결입니다.</span><span class="sxs-lookup"><span data-stu-id="45a4d-107">A trunk is a logical association between a Mediation Server FQDN and listening port and a PSTN gateway FQDN and listening port.</span></span> <span data-ttu-id="45a4d-108">이 새로운 접근 권한 값을 통해 여러 중재 서버를 사용 하 여 동일한 PSTN 게이트웨이로 통화를 라우팅할 수 있는 복구를 위해 다양 한 연결 정책을 사용 하는 여러 trunks를 사용할 수 있는 PBX 상호 운용성에 대 한 트렁크의 간편한 사용을 가능 하 게 합니다. IP PBX와 중재 서버, 그리고 서로 다른 사이트의 중재 서버에 동일한 통신 회사 FQDN이 참조 하는 반송파에 대 한 SIP trunks 있는 SIP 트렁크 구성에 적합 합니다.</span><span class="sxs-lookup"><span data-stu-id="45a4d-108">This new capability allows for easy trunk definition for resiliency (where multiple Mediation Servers can be used to route calls to the same PSTN Gateway), for PBX interoperability, where multiple trunks with different associated policies can be used between and IP-PBX and a Mediation Server, and for SIP trunk configurations where Mediation Servers at different sites have SIP trunks to the carrier referenced by the same carrier FQDN.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="45a4d-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="45a4d-109">See Also</span></span>


[<span data-ttu-id="45a4d-110">Lync Server 2013의 새 Enterprise Voice 기능</span><span class="sxs-lookup"><span data-stu-id="45a4d-110">New Enterprise Voice features in Lync Server 2013</span></span>](lync-server-2013-new-enterprise-voice-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

