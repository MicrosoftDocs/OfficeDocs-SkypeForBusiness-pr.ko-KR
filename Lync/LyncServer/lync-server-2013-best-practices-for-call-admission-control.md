---
title: 'Lync Server 2013: 통화 허용 제어에 대 한 모범 사례'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Best practices for call admission control
ms:assetid: 97173cca-8175-4ae2-a247-eb7ef809da93
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398770(v=OCS.15)
ms:contentKeyID: 48184913
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: be270859304236b0704bc8cc9e1bc29f3e80fcb9
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48514825"
---
# <a name="best-practices-for-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="226f5-102">Lync Server 2013의 통화 허용 제어에 대 한 모범 사례</span><span class="sxs-lookup"><span data-stu-id="226f5-102">Best practices for call admission control in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="226f5-103">_**마지막으로 수정 된 항목:** 2012-09-22_</span><span class="sxs-lookup"><span data-stu-id="226f5-103">_**Topic Last Modified:** 2012-09-22_</span></span>

<span data-ttu-id="226f5-104">성능을 향상시키고 배포를 용이하게 하려면 통화 허용 제어 배포 시 다음과 같은 유용한 정보를 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="226f5-104">To enhance performance and facilitate deployment, apply the following best practices when you deploy call admission control:</span></span>

  - <span data-ttu-id="226f5-105">현재 및 예상 미디어 트래픽에 대해 WAN이 적절하게 프로비전되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="226f5-105">Ensure that WANs are adequately provisioned for current and anticipated media traffic.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="226f5-p101">대역폭 제한에 대해 버퍼를 고려하는 것이 좋습니다. 사용되는 총 대역폭에 영향을 주고 대역폭 제한이 초과되는 상황을 초래할 수 있는 경합 상태와 같은 시나리오가 있습니다. 예를 들어 두 통화가 미디어 트래픽이 대역폭 제한에 근접하는 동안 시작되려고 하는 경우 한 통화가 먼저 시작되기 때문에 다른 한 통화가 거부될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="226f5-p101">We recommend that you factor in a buffer to your bandwidth limits. There are scenarios such as race conditions that affect the total bandwidth used and can result in situations where the bandwidth limit is exceeded. For example, if two calls try to start while media traffic is approaching a bandwidth limit, one of them may be denied because the other managed to start first.</span></span>

    
    </div>

  - <span data-ttu-id="226f5-109">최적의 CAC 설정을 선택하고 네트워크 사용량이 변경됨에 따라 CAC 설정을 업데이트할 수 있도록 네트워크 사용량 및 통화 정보 기록을 모니터링합니다.</span><span class="sxs-lookup"><span data-stu-id="226f5-109">Monitor network usage and call detail records so that you can choose optimal CAC settings and update CAC settings as network usage changes.</span></span>

  - <span data-ttu-id="226f5-110">CAC 대역폭 정책을 사용하여 QoS 설정을 보완합니다.</span><span class="sxs-lookup"><span data-stu-id="226f5-110">Use CAC bandwidth policies to complement QoS settings.</span></span>

  - <span data-ttu-id="226f5-111">차단된 통화를 PSTN으로 다시 라우팅하려면 PSTN 기능 및 용량을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="226f5-111">If you want to re-route blocked calls onto the PSTN, verify PSTN functionality and capacity.</span></span> <span data-ttu-id="226f5-112">자세한 내용은 [Lync Server 2013에서 아웃 바운드 음성 라우팅 계획](lync-server-2013-planning-outbound-voice-routing.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="226f5-112">For details, see [Planning outbound voice routing in Lync Server 2013](lync-server-2013-planning-outbound-voice-routing.md).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="226f5-113">용량은 잠재적 PSTN 재라우팅을 지원하기 위해 열어야 하는 포트 수를 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="226f5-113">Capacity refers to the number of ports you need to open to support potential PSTN re-routing.</span></span>

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

