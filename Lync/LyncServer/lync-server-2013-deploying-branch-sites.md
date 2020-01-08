---
title: 'Lync Server 2013: 분기 사이트 배포'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploying branch sites
ms:assetid: 1475dee0-66ae-4ee5-b6f1-7409b4bbff45
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398217(v=OCS.15)
ms:contentKeyID: 48183483
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6c96a8c99b6f80e7e70f3129e502d33b93a73f42
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982054"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-branch-sites-in-lync-server-2013"></a><span data-ttu-id="6d8f1-102">Lync Server 2013에서 분기 사이트 배포</span><span class="sxs-lookup"><span data-stu-id="6d8f1-102">Deploying branch sites in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6d8f1-103">_**마지막으로 수정한 주제:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="6d8f1-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="6d8f1-104">지점 사이트 사용자는 지점 사이트가 연결 된 중앙 사이트의 서버에서 Lync Server 2013 기능을 최대한 활용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d8f1-104">Branch site users get most of their Lync Server 2013 functionality from the server at the central site that the branch site is associated with.</span></span> <span data-ttu-id="6d8f1-105">각 지점 사이트는 정확히 하나의 중앙 사이트와 연결 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d8f1-105">Each branch site is associated with exactly one central site.</span></span> <span data-ttu-id="6d8f1-106">PSTN (공개 교환 전화 네트워크)에 대 한 전화를 제공 하기 위해 지점 사이트에는 다음이 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d8f1-106">To provide calls to and from the public switched telephone network (PSTN), a branch site might contain any of the following:</span></span>

  - <span data-ttu-id="6d8f1-107">PSTN 게이트웨이를 비롯 하 여 Meditation 서버</span><span class="sxs-lookup"><span data-stu-id="6d8f1-107">A PSTN gateway and possibly a Meditation Server</span></span>

  - <span data-ttu-id="6d8f1-108">SIP 트렁크</span><span class="sxs-lookup"><span data-stu-id="6d8f1-108">A SIP trunk</span></span>

  - <span data-ttu-id="6d8f1-109">PBX (사설 branch exchange)가 있는 기존 음성 인프라</span><span class="sxs-lookup"><span data-stu-id="6d8f1-109">An existing voice infrastructure with a private branch exchange (PBX)</span></span>

  - <span data-ttu-id="6d8f1-110">Survivable 분기 기기</span><span class="sxs-lookup"><span data-stu-id="6d8f1-110">A Survivable Branch Appliance</span></span>

  - <span data-ttu-id="6d8f1-111">Survivable Branch 서버</span><span class="sxs-lookup"><span data-stu-id="6d8f1-111">A Survivable Branch Server</span></span>

<span data-ttu-id="6d8f1-112">Survivable Branch 기기 또는 Survivable Branch 서버를 사용 하는 분기 사이트는 이러한 솔루션 중 하나가 없는 지점 사이트 보다 광역 네트워크 또는 중앙 사이트 장애가 있는 시간에 더욱 탄력적으로 대처할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d8f1-112">Branch sites with a Survivable Branch Appliance or a Survivable Branch Server are more resilient in times of wide-area network or central site failures than branch sites without one of these solutions.</span></span> <span data-ttu-id="6d8f1-113">예를 들어 Survivable Branch 기기 또는 Survivable Branch 서버가 배포 된 사이트에서 사용자는 지점 사이트를 중앙 사이트에 연결 하는 네트워크가 작동 하지 않는 경우에도 계속 PSTN 통화를 설정 하 고 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d8f1-113">For example, in a site with a Survivable Branch Appliance or a Survivable Branch Server deployed, users can still make and receive PSTN calls if the network connecting the branch site to the central site is down.</span></span> <span data-ttu-id="6d8f1-114">지점 사이트에 대 한 복원을 수행 하는 또 다른 방법은 PSTN 게이트웨이나 전체 규모의 Lync Server 배포를 사용 하 여 SIP 트렁크를 수행 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="6d8f1-114">Another way to achieve branch-site resiliency is by using a PSTN gateway or a SIP trunk with a full-scale Lync Server deployment at the branch site.</span></span>

<span data-ttu-id="6d8f1-115">필수 구성 요소 및 기타 계획 고려 사항을 포함 하 여 조직에 적합 한 지점 사이트 배포에 대 한 자세한 내용은 [Lync server 2013의 PSTN 연결 계획](lync-server-2013-planning-for-pstn-connectivity.md) 및 [lync Server 2013에서 계획 설명서의 지점 사이트 음성 복구 계획](lync-server-2013-planning-for-branch-site-voice-resiliency.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6d8f1-115">For details about which branch site deployment is right for your organization, including prerequisites and other planning considerations, see [Planning for PSTN connectivity in Lync Server 2013](lync-server-2013-planning-for-pstn-connectivity.md) and [Planning for branch-site voice resiliency in Lync Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md) in the Planning documentation.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="6d8f1-116">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="6d8f1-116">In This Section</span></span>

  - [<span data-ttu-id="6d8f1-117">Lync Server 2013의 분기 사이트에서 PSTN 연결 제공</span><span class="sxs-lookup"><span data-stu-id="6d8f1-117">Providing PSTN connectivity at a branch site in Lync Server 2013</span></span>](lync-server-2013-providing-pstn-connectivity-at-a-branch-site.md)

  - [<span data-ttu-id="6d8f1-118">Lync Server 2013을 통해 SBA(Survivable Branch Appliance) 또는 지속 가능 분기 서버 배포</span><span class="sxs-lookup"><span data-stu-id="6d8f1-118">Deploying a Survivable Branch Appliance or Server with Lync Server 2013</span></span>](lync-server-2013-deploying-a-survivable-branch-appliance-or-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

