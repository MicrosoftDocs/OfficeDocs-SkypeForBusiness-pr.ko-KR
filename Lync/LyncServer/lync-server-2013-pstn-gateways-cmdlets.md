---
title: 'Lync Server 2013: PSTN 게이트웨이 cmdlet'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: PSTN gateways cmdlets
ms:assetid: 6a8aa6ea-f349-4b95-b3ce-c28d2ae0a84b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg416491(v=OCS.15)
ms:contentKeyID: 48184397
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b82b4cd1a5458fac6b2d5ade712fcfeeaf120208
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724668"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="pstn-gateways-cmdlets-in-lync-server-2013"></a><span data-ttu-id="63c56-102">Lync Server 2013의 PSTN 게이트웨이 cmdlet</span><span class="sxs-lookup"><span data-stu-id="63c56-102">PSTN gateways cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="63c56-103">_**마지막으로 수정한 주제:** 2012-03-21_</span><span class="sxs-lookup"><span data-stu-id="63c56-103">_**Topic Last Modified:** 2012-03-21_</span></span>

<span data-ttu-id="63c56-104">PSTN 게이트웨이는 엔터프라이즈 음성 사용자가 PSTN 네트워크 (즉, 공개 스위치 전화 네트워크)에서 전화를 걸고 받을 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="63c56-104">PSTN gateways enable your Enterprise Voice users to make phone calls to, and receive phone calls from, people on the PSTN network (that is, the public switched telephone network).</span></span> <span data-ttu-id="63c56-105">이러한 게이트웨이는 중재 서버와 PSTN 네트워크 간의 다리 역할을 합니다.</span><span class="sxs-lookup"><span data-stu-id="63c56-105">These gateways act as a bridge between the Mediation Server and the PSTN network.</span></span>

<div>

## <a name="pstn-gateways-cmdlets"></a><span data-ttu-id="63c56-106">PSTN 게이트웨이 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="63c56-106">PSTN Gateways Cmdlets</span></span>

<span data-ttu-id="63c56-107">[테스트 CsPstnOutboundCall](https://technet.microsoft.com/en-us/library/Gg398207(v=OCS.15)) 및 [테스트-Csptopeercall](https://technet.microsoft.com/en-us/library/Gg398662(v=OCS.15)) cmdlet을 사용 하 여 사용자가 PSTN 네트워크를 통해 통화할 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="63c56-107">The [Test-CsPstnOutboundCall](https://technet.microsoft.com/en-us/library/Gg398207(v=OCS.15)) and [Test-CsPstnPeerToPeerCall](https://technet.microsoft.com/en-us/library/Gg398662(v=OCS.15)) cmdlets enable you to verify that users are able to make call over the PSTN network.</span></span>

<span data-ttu-id="63c56-108">**PSTN 게이트웨이**</span><span class="sxs-lookup"><span data-stu-id="63c56-108">**PSTN Gateways**</span></span>

  - <span></span>  
    <span data-ttu-id="63c56-109">[Set-CsPstnGateway](https://technet.microsoft.com/en-us/library/Gg398408(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="63c56-109">[Set-CsPstnGateway](https://technet.microsoft.com/en-us/library/Gg398408(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="63c56-110">[Test-CsPstnOutboundCall](https://technet.microsoft.com/en-us/library/Gg398207(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="63c56-110">[Test-CsPstnOutboundCall](https://technet.microsoft.com/en-us/library/Gg398207(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="63c56-111">[Test-CsPstnPeerToPeerCall](https://technet.microsoft.com/en-us/library/Gg398662(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="63c56-111">[Test-CsPstnPeerToPeerCall](https://technet.microsoft.com/en-us/library/Gg398662(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="63c56-112">[Set-CsMediationServer](https://technet.microsoft.com/en-us/library/Gg398213(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="63c56-112">[Set-CsMediationServer](https://technet.microsoft.com/en-us/library/Gg398213(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="63c56-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="63c56-113">See Also</span></span>


[<span data-ttu-id="63c56-114">Lync Server PowerShell 블로그</span><span class="sxs-lookup"><span data-stu-id="63c56-114">Lync Server PowerShell Blog</span></span>](http://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

