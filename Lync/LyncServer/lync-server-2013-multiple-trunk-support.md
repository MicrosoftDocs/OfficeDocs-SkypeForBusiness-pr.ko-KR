---
title: 'Lync Server 2013: 여러 트렁크 지원'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Multiple trunk support
ms:assetid: a1309c09-ad9a-4c54-9650-4e3f5b2a4a00
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205127(v=OCS.15)
ms:contentKeyID: 48184948
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9d13ca1a28fd28a6d280ddf3a18e57e09376e668
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765959"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="multiple-trunk-support-in-lync-server-2013"></a><span data-ttu-id="21d4e-102">Lync Server 2013의 여러 트렁크 지원</span><span class="sxs-lookup"><span data-stu-id="21d4e-102">Multiple trunk support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="21d4e-103">_**마지막으로 수정한 주제:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="21d4e-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="21d4e-104">Lync Server 2013 기능은 게이트웨이와 중재 서버 간에 여러 연결을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="21d4e-104">Lync Server 2013 functionality supports multiple associations between gateways and Mediation Servers.</span></span> <span data-ttu-id="21d4e-105">이러한 연결은 중재 서버 풀과 PSTN (공개 교환 통신 네트워크) 게이트웨이, SBC (세션 경계 컨트롤러) 또는 IP-PBX 간의 논리적 연결 인 트렁크를 정의 하 여 이루어집니다.</span><span class="sxs-lookup"><span data-stu-id="21d4e-105">These associations are made by defining a trunk, which is a logical association between a Mediation Server pool and a public switched telephone network (PSTN) gateway, Session Border Controller (SBC), or IP-PBX.</span></span> <span data-ttu-id="21d4e-106">토폴로지 작성기를 사용 하 여 게이트웨이를 중재 서버와 연결 합니다 (즉, trunks).</span><span class="sxs-lookup"><span data-stu-id="21d4e-106">Use the Topology Builder to associate gateways with Mediation Servers (that is, trunks).</span></span>

  - <span data-ttu-id="21d4e-107">Lync Server 2013에서 트렁크를 할당 하거나 제거 하려면 먼저 토폴로지 작성기에서 트렁크를 정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="21d4e-107">To assign or remove a trunk in Lync Server 2013, you must first define a trunk in Topology Builder.</span></span> <span data-ttu-id="21d4e-108">트렁크는 다음 연결로 구성 됩니다. 중재 서버 FQDN (정규화 된 도메인 이름), 중재 서버 수신 포트, 게이트웨이 FQDN 및 게이트웨이 수신 대기 포트.</span><span class="sxs-lookup"><span data-stu-id="21d4e-108">A trunk consists of the following association: Mediation Server fully qualified domain name (FQDN), the Mediation Server listening port, the gateway FQDN, and the gateway listening port.</span></span>

  - <span data-ttu-id="21d4e-109">여러 trunks를 구성 하려면 동일한 게이트웨이와 중재 서버 간에 여러 연결을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21d4e-109">To configure multiple trunks, you can create multiple associations between the same gateway and the Mediation Server.</span></span> <span data-ttu-id="21d4e-110">이렇게 하면 PBX (개인 브랜치 교환) interoperational 시나리오에서 특히 유용한 엔터프라이즈 음성 인프라에 대 한 추가 탄력성을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="21d4e-110">This provides additional resiliency to the Enterprise Voice infrastructure, which is especially useful in private branch exchange (PBX) interoperational scenarios.</span></span>

<span data-ttu-id="21d4e-111">트렁크가 정의 되 면 경로에 연결 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="21d4e-111">When a trunk is defined, it must be associated to a route.</span></span> <span data-ttu-id="21d4e-112">트렁크를 경로에 연결 하려면 토폴로지 작성기에서 트렁크에 대 한 간단한 이름을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="21d4e-112">To associate a trunk to a route, you define a simple name for the trunk in Topology Builder.</span></span> <span data-ttu-id="21d4e-113">이 간단한 이름은 Lync Server 제어판에서 트렁크 이름으로 사용 되며, trunks는 경로와 연결 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21d4e-113">This simple name is used as the trunk name in the Lync Server Control Panel, where trunks can be associated with routes.</span></span> <span data-ttu-id="21d4e-114">간단한 트렁크 이름은 Lync Server 관리 셸에서 게이트웨이 이름으로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="21d4e-114">The simple trunk name is used as the gateway name from the Lync Server Management Shell.</span></span>

    New-CsVoiceRoute -Identity <RouteId> -NumberPattern <String> -PstnUsages @{add="<UsageString>"} -PstnGatewayList @{add="<TrunkSimpleName>"}

<span data-ttu-id="21d4e-115">관리자는 중재 서버와 연결 된 기본 트렁크를 선택 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="21d4e-115">The administrator must select a default trunk associated with a Mediation Server.</span></span> <span data-ttu-id="21d4e-116">토폴로지 작성기에서 연결 된 중재 서버를 마우스 오른쪽 단추로 클릭 한 다음 **속성**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="21d4e-116">From the Topology Builder, right-click the associated Mediation Server, and then click **Properties**.</span></span> <span data-ttu-id="21d4e-117">중재 서버의 기본 게이트웨이를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="21d4e-117">Specify the default gateway for the Mediation Server.</span></span>

<span data-ttu-id="21d4e-118">다음 다이어그램에서는 각 중재 서버 및 게이트웨이에 대해 정의 된 여러 trunks를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="21d4e-118">The following diagram illustrates the multiple trunks that are defined for each Mediation Server and gateway.</span></span>

<span data-ttu-id="21d4e-119">**M-N 트렁크 라우팅**</span><span class="sxs-lookup"><span data-stu-id="21d4e-119">**M-N Trunk Routing**</span></span>

<span data-ttu-id="21d4e-120">![여러 트렁크 할당.](images/JJ205127.c61cd9a7-d8d9-4e02-83b9-ab62519a48c4(OCS.15).jpg "여러 트렁크 할당.")</span><span class="sxs-lookup"><span data-stu-id="21d4e-120">![Multiple trunk assignments.](images/JJ205127.c61cd9a7-d8d9-4e02-83b9-ab62519a48c4(OCS.15).jpg "Multiple trunk assignments.")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

