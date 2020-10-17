---
title: 'Lync Server 2013: 분기 사이트 SIP 트렁크'
description: 'Lync Server 2013: 분기 사이트 SIP 트렁크'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Branch site SIP trunking
ms:assetid: c4d9dfcd-8baa-41ea-9677-48b0e429429d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412974(v=OCS.15)
ms:contentKeyID: 48185350
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 33e408a462c21ffa6df6e6a2aee50d7b87dca1f7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569324"
---
# <a name="branch-site-sip-trunking-in-lync-server-2013"></a><span data-ttu-id="8766b-103">Lync Server 2013에서 분기 사이트 SIP 트렁크</span><span class="sxs-lookup"><span data-stu-id="8766b-103">Branch site SIP trunking in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8766b-104">_**마지막으로 수정 된 항목:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="8766b-104">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="8766b-105">경우에 따라 선택한 분기 사이트에서 분산 SIP 트렁크을 구현 해야 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8766b-105">In some cases, you may need to implement distributed SIP trunking at selected branch sites.</span></span> <span data-ttu-id="8766b-106">분기 사이트에 대해 SIP 트렁크가 필요한 지 여부를 확인 하려면 [Lync Server 2013에서 sip 트렁크를 구현 하는 방법](lync-server-2013-how-do-i-implement-sip-trunking.md)의 정보를 검토 하십시오.</span><span class="sxs-lookup"><span data-stu-id="8766b-106">To determine whether a SIP trunk is needed for a branch site, review the information in [How do I implement SIP trunking in Lync Server 2013?](lync-server-2013-how-do-i-implement-sip-trunking.md).</span></span>

<span data-ttu-id="8766b-107">분기 사이트에서 SIP 트렁크을 배포 하기 위한 지원 되는 토폴로지 옵션에 대 한 자세한 내용은 [Lync Server 2013의 분기 사이트 복구 솔루션](lync-server-2013-branch-site-resiliency-solutions.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="8766b-107">For details about the supported topology options for deploying SIP trunks in branch sites, see [Branch-site resiliency solutions in Lync Server 2013](lync-server-2013-branch-site-resiliency-solutions.md).</span></span>

<div>

## <a name="example-branch-site-sip-trunk-requirements-analysis"></a><span data-ttu-id="8766b-108">예 분기 사이트 SIP 트렁크 요구 사항 분석</span><span class="sxs-lookup"><span data-stu-id="8766b-108">Example Branch Site SIP Trunk Requirements Analysis</span></span>

<span data-ttu-id="8766b-109">분기 사이트 SIP 트렁크를 배포 하기로 결정 한 경우 사이트별 비용 분석을 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8766b-109">When you decide to deploy a branch site SIP trunk, you need to perform a site-specific cost analysis.</span></span> <span data-ttu-id="8766b-110">예를 들어 Redmond, 인천 및 뉴욕의 분기 사이트에 중앙 사이트가 있는 기업에서는 분석을 수행 하 여 뉴욕 사이트에서 로컬 서비스 공급자로 SIP 트렁크를 구현할지 여부를 결정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8766b-110">For example, an enterprise that has a central site in Redmond, Washington, and a branch site in New York, should do an analysis to determine whether to implement a SIP trunk from the New York site to a local service provider.</span></span>

<span data-ttu-id="8766b-111">뉴욕에서 분산된 SIP 트렁크가 비용 효율적인지 여부를 확인하려면 SIP 트렁크가 사용되는 DID(내선 직접 호출) 번호를 식별하고 뉴욕에서 레드몬드(425)가 아닌 지역으로 전화를 건 횟수를 분석합니다.</span><span class="sxs-lookup"><span data-stu-id="8766b-111">To determine whether a distributed SIP trunk in New York is cost-effective, identify which Direct Inward Dialing (DID) numbers will use the SIP trunk, and analyze the number of calls New York makes to areas other than Redmond (425).</span></span> <span data-ttu-id="8766b-112">중앙 사이트에서 분기 사이트를 종료 했을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8766b-112">You can have DID termination for the branch site at the central site.</span></span> <span data-ttu-id="8766b-113">예를 들어 Redmond 중앙 사이트는 뉴욕 분기 사이트에 대해 번호를 호스트 하는 경우를 들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8766b-113">For example, the Redmond central site can host DID numbers for the New York branch site.</span></span> <span data-ttu-id="8766b-114">분산 SIP 트렁크를 구현 하는 데 드는 비용이 이러한 통화 비용 보다 적은 경우 뉴욕 분기 사이트에서 SIP 트렁크를 구현 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="8766b-114">If the cost of implementing a distributed SIP trunk is less than the cost of those calls, consider implementing a SIP trunk at the New York branch site.</span></span>

</div>

<div>

## <a name="other-branch-site-sip-trunk-requirements"></a><span data-ttu-id="8766b-115">기타 분기 사이트 SIP 트렁크 요구 사항</span><span class="sxs-lookup"><span data-stu-id="8766b-115">Other Branch Site SIP Trunk Requirements</span></span>

<span data-ttu-id="8766b-116">게이트웨이 대신 SIP 트렁크를 배포 하는 중에 선택 하는 것은 각 옵션의 장거리 시외 전화 비용 간의 차이를 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="8766b-116">The choice between a deploying a SIP trunk instead of a gateway is based on the difference between the public switched telephone network (PSTN) long distance toll charges of each option.</span></span> <span data-ttu-id="8766b-117">분기 사이트 SIP 트렁크를 배포 하는 경우에는 복구 및 대역폭 요구 사항도 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8766b-117">If you deploy a branch site SIP trunk, you also need to determine your resiliency and bandwidth requirements.</span></span> <span data-ttu-id="8766b-118">분기 사이트와 중앙 사이트 간의 링크가 탄력적이 고 충분 한 대역폭이 있으면 SIP 트렁크 또는 게이트웨이를 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8766b-118">If the link between your branch site and central site is resilient and has sufficient bandwidth, you can deploy a SIP trunk or a gateway.</span></span> <span data-ttu-id="8766b-119">분기 사이트에서 Sba (survivable Branch 기기를 배포할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8766b-119">You do not need to deploy a Survivable Branch Appliance at the branch site.</span></span> <span data-ttu-id="8766b-120">분기 사이트와 중앙 사이트 간의 링크가 복원 되지 않는 경우 Sba (survivable 분기 어플라이언스를 배포 하거나 분기 사이트에 게이트웨이나 SIP 트렁크를 사용 하 여 Sba (survivable 분기 서버를 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="8766b-120">If the link between your branch site and central site is not resilient, deploy a Survivable Branch Appliance, or deploy a Survivable Branch Server with either a gateway or SIP trunk at the branch site.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

