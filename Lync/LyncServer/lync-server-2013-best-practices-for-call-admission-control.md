---
title: 'Lync Server 2013: 통화 허용 제어 서비스 모범 사례'
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
ms.openlocfilehash: 0d8f75c546b2307de8f55504c2c6ebaab5c48f7c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741678"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="best-practices-for-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="26cab-102">Lync Server 2013의 통화 허용 제어 서비스 모범 사례</span><span class="sxs-lookup"><span data-stu-id="26cab-102">Best practices for call admission control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="26cab-103">_**마지막으로 수정한 주제:** 2012-09-22_</span><span class="sxs-lookup"><span data-stu-id="26cab-103">_**Topic Last Modified:** 2012-09-22_</span></span>

<span data-ttu-id="26cab-104">성능을 개선 하 고 배포를 쉽게 하려면 통화 허용 컨트롤을 배포할 때 다음과 같은 모범 사례를 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="26cab-104">To enhance performance and facilitate deployment, apply the following best practices when you deploy call admission control:</span></span>

  - <span data-ttu-id="26cab-105">현재 및 예상 미디어 트래픽에 대 한 Wan이 적절 하 게 프로 비전 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="26cab-105">Ensure that WANs are adequately provisioned for current and anticipated media traffic.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="26cab-106">대역폭 제한에 대 한 버퍼의 비율을 조정 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="26cab-106">We recommend that you factor in a buffer to your bandwidth limits.</span></span> <span data-ttu-id="26cab-107">사용 되는 총 대역폭에 영향을 주는 경합 상태와 같은 시나리오가 있으며 대역폭 한도가 초과 된 경우에 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26cab-107">There are scenarios such as race conditions that affect the total bandwidth used and can result in situations where the bandwidth limit is exceeded.</span></span> <span data-ttu-id="26cab-108">예를 들어 미디어 트래픽이 대역폭 제한에 근접 하는 동안 두 개의 호출을 시작 하려고 하면 다른 하나는 먼저 시작 하도록 관리 되므로 거부 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26cab-108">For example, if two calls try to start while media traffic is approaching a bandwidth limit, one of them may be denied because the other managed to start first.</span></span>

    
    </div>

  - <span data-ttu-id="26cab-109">최적의 CAC 설정을 선택 하 고 네트워크 사용량 변경으로 CAC 설정을 업데이트할 수 있도록 네트워크 사용량 및 통화 정보 레코드를 모니터링 합니다.</span><span class="sxs-lookup"><span data-stu-id="26cab-109">Monitor network usage and call detail records so that you can choose optimal CAC settings and update CAC settings as network usage changes.</span></span>

  - <span data-ttu-id="26cab-110">CAC 대역폭 정책을 사용 하 여 QoS 설정을 보완 하세요.</span><span class="sxs-lookup"><span data-stu-id="26cab-110">Use CAC bandwidth policies to complement QoS settings.</span></span>

  - <span data-ttu-id="26cab-111">차단 된 통화를 PSTN으로 다시 라우팅하도록 하려면 PSTN 기능 및 용량을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="26cab-111">If you want to re-route blocked calls onto the PSTN, verify PSTN functionality and capacity.</span></span> <span data-ttu-id="26cab-112">자세한 내용은 [Lync Server 2013의 아웃 바운드 음성 라우팅 계획](lync-server-2013-planning-outbound-voice-routing.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="26cab-112">For details, see [Planning outbound voice routing in Lync Server 2013](lync-server-2013-planning-outbound-voice-routing.md).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="26cab-113">용량은 잠재적인 PSTN 다시 라우팅을 지원 하기 위해 여는 데 필요한 포트 수를 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="26cab-113">Capacity refers to the number of ports you need to open to support potential PSTN re-routing.</span></span>

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

