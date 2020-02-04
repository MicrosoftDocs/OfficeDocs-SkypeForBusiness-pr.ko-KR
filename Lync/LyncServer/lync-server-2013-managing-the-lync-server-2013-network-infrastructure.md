---
title: 'Lync Server 2013: Lync Server 2013 네트워크 인프라 관리'
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
ms.openlocfilehash: c8663c5837b118bc35c889dac34196a05a76dd63
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727758"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-the-lync-server-2013-network-infrastructure"></a><span data-ttu-id="88cbf-102">Lync Server 2013 네트워크 인프라 관리</span><span class="sxs-lookup"><span data-stu-id="88cbf-102">Managing the Lync Server 2013 network infrastructure</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="88cbf-103">_**마지막으로 수정한 주제:** 2014-02-11_</span><span class="sxs-lookup"><span data-stu-id="88cbf-103">_**Topic Last Modified:** 2014-02-11_</span></span>

<span data-ttu-id="88cbf-104">Microsoft Lync Server 2013에는 CAC (통화 허용 제어) 및 미디어 바이패스에 대 한 지원이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="88cbf-104">Microsoft Lync Server 2013 includes support for call admission control (CAC) and media bypass.</span></span> <span data-ttu-id="88cbf-105">이러한 기능을 구현 하려면 지역, 사이트, 서브넷 등의 네트워크를 구성 하 여 오디오 및 비디오 전송을 제한 해야 하는 상황에서 대역폭을 관리할 수 있도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="88cbf-105">To implement these features you must configure a network of regions, sites, subnets, and so on that will allow you to manage bandwidth in situations where audio and video transmissions need to be restricted.</span></span> <span data-ttu-id="88cbf-106">QoS (서비스 품질) 네트워킹 기술을 사용 하 여 오디오 및 비디오 통신을 위한 최적의 최종 사용자 환경을 제공 하는 데 도움이 될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88cbf-106">You can also use the Quality of Service (QoS) networking technology to help provide an optimal end-user experience for audio and video communications.</span></span>

<span data-ttu-id="88cbf-107">Lync Server 제어판을 사용 하 여 CAC, 미디어 바이패스 및 QoS를 설정 하 고 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88cbf-107">You can use the Lync Server Control Panel to set up and manage CAC, media bypass, and QoS.</span></span> <span data-ttu-id="88cbf-108">다음 항목에서는이 작업을 수행 하는 단계를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="88cbf-108">The following topics provide steps for how to do this.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="88cbf-109">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="88cbf-109">In This Section</span></span>

  - [<span data-ttu-id="88cbf-110">Lync Server 2013에서 QoS (서비스 품질) 관리</span><span class="sxs-lookup"><span data-stu-id="88cbf-110">Managing Quality of Service (QoS) in Lync Server 2013</span></span>](lync-server-2013-managing-quality-of-service-qos.md)

  - [<span data-ttu-id="88cbf-111">Lync Server 2013에서 통화 허용 제어 관리</span><span class="sxs-lookup"><span data-stu-id="88cbf-111">Managing call admission control in Lync Server 2013</span></span>](lync-server-2013-managing-call-admission-control.md)

  - [<span data-ttu-id="88cbf-112">Lync Server 2013 네트워크 인터페이스</span><span class="sxs-lookup"><span data-stu-id="88cbf-112">Lync Server 2013 network interfaces</span></span>](lync-server-2013-lync-server-network-interfaces.md)

  - [<span data-ttu-id="88cbf-113">서버 유지 관리를 위해 Lync Server 2013에 대 한 새로운 연결 방지</span><span class="sxs-lookup"><span data-stu-id="88cbf-113">Prevent new connections to Lync Server 2013 for server maintenance</span></span>](lync-server-2013-prevent-new-connections-to-lync-server-for-server-maintenance.md)

  - [<span data-ttu-id="88cbf-114">Lync Server 2013의 lync 통화 품질 방법론</span><span class="sxs-lookup"><span data-stu-id="88cbf-114">Lync Call Quality Methodology in Lync Server 2013</span></span>](lync-server-2013-poster-lync-call-quality-methodology.md)

  - [<span data-ttu-id="88cbf-115">Lync Server 2013의 주요 상태 표시기</span><span class="sxs-lookup"><span data-stu-id="88cbf-115">Key Health Indicators in Lync Server 2013</span></span>](lync-server-2013-poster-key-health-indicators.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

