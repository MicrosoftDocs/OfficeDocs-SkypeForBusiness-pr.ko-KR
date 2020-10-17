---
title: 'Lync Server 2013: Lync Server 2013 네트워크 인프라 관리'
description: 'Lync Server 2013: Lync Server 2013 네트워크 인프라 관리'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing the Lync Server 2013 network infrastructure
ms:assetid: cb13456a-8f66-4595-be21-8887f30ad4eb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182585(v=OCS.15)
ms:contentKeyID: 48185638
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ab1b5c6fe52374b012063ac26640e9bb25496ad7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564104"
---
# <a name="managing-the-lync-server-2013-network-infrastructure"></a><span data-ttu-id="b5ecf-103">Lync Server 2013 네트워크 인프라 관리</span><span class="sxs-lookup"><span data-stu-id="b5ecf-103">Managing the Lync Server 2013 network infrastructure</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b5ecf-104">_**마지막으로 수정 된 항목:** 2014-02-11_</span><span class="sxs-lookup"><span data-stu-id="b5ecf-104">_**Topic Last Modified:** 2014-02-11_</span></span>

<span data-ttu-id="b5ecf-105">Microsoft Lync Server 2013에는 CAC (통화 허용 제어) 및 미디어 바이패스에 대 한 지원이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5ecf-105">Microsoft Lync Server 2013 includes support for call admission control (CAC) and media bypass.</span></span> <span data-ttu-id="b5ecf-106">이러한 기능을 구현하려면 오디오 및 비디오 전송을 제한해야 하는 상황에서 대역폭을 관리할 수 있는 지역, 사이트, 서브넷 등에 대한 네트워크를 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5ecf-106">To implement these features you must configure a network of regions, sites, subnets, and so on that will allow you to manage bandwidth in situations where audio and video transmissions need to be restricted.</span></span> <span data-ttu-id="b5ecf-107">또한 QoS(서비스 품질) 네트워크 기술을 사용하여 최종 사용자에게 오디오 및 비디오 통신에 대해 최적의 환경을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5ecf-107">You can also use the Quality of Service (QoS) networking technology to help provide an optimal end-user experience for audio and video communications.</span></span>

<span data-ttu-id="b5ecf-108">Lync Server 제어판을 사용 하 여 CAC, 미디어 바이패스 및 QoS를 설정 하 고 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5ecf-108">You can use the Lync Server Control Panel to set up and manage CAC, media bypass, and QoS.</span></span> <span data-ttu-id="b5ecf-109">다음 항목에서는 이 작업을 수행하는 방법에 대한 단계를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b5ecf-109">The following topics provide steps for how to do this.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="b5ecf-110">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="b5ecf-110">In This Section</span></span>

  - [<span data-ttu-id="b5ecf-111">Lync Server 2013에서 QoS (서비스 품질) 관리</span><span class="sxs-lookup"><span data-stu-id="b5ecf-111">Managing Quality of Service (QoS) in Lync Server 2013</span></span>](lync-server-2013-managing-quality-of-service-qos.md)

  - [<span data-ttu-id="b5ecf-112">Lync Server 2013의 통화 허용 제어 관리</span><span class="sxs-lookup"><span data-stu-id="b5ecf-112">Managing call admission control in Lync Server 2013</span></span>](lync-server-2013-managing-call-admission-control.md)

  - [<span data-ttu-id="b5ecf-113">Lync Server 2013 네트워크 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b5ecf-113">Lync Server 2013 network interfaces</span></span>](lync-server-2013-lync-server-network-interfaces.md)

  - [<span data-ttu-id="b5ecf-114">서버 유지 관리를 위해 Lync Server 2013에 대 한 새 연결 차단</span><span class="sxs-lookup"><span data-stu-id="b5ecf-114">Prevent new connections to Lync Server 2013 for server maintenance</span></span>](lync-server-2013-prevent-new-connections-to-lync-server-for-server-maintenance.md)

  - [<span data-ttu-id="b5ecf-115">Lync Server 2013의 lync 통화 품질 방법론</span><span class="sxs-lookup"><span data-stu-id="b5ecf-115">Lync Call Quality Methodology in Lync Server 2013</span></span>](lync-server-2013-poster-lync-call-quality-methodology.md)

  - [<span data-ttu-id="b5ecf-116">Lync Server 2013의 주요 상태 지표</span><span class="sxs-lookup"><span data-stu-id="b5ecf-116">Key Health Indicators in Lync Server 2013</span></span>](lync-server-2013-poster-key-health-indicators.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

