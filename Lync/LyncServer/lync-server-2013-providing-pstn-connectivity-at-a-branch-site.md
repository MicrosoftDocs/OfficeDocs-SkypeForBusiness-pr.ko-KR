---
title: 'Lync Server 2013: 분기 사이트에서 PSTN 연결 제공'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Providing PSTN connectivity at a branch site
ms:assetid: d78d76fb-2dd1-42cb-b25a-bfaff9650a70
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398945(v=OCS.15)
ms:contentKeyID: 48185633
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5dfc039b0b1cd2995d0a658f1c1c78e0941d405d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724778"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="providing-pstn-connectivity-at-a-branch-site-in-lync-server-2013"></a><span data-ttu-id="70319-102">Lync Server 2013의 분기 사이트에서 PSTN 연결 제공</span><span class="sxs-lookup"><span data-stu-id="70319-102">Providing PSTN connectivity at a branch site in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="70319-103">_**마지막으로 수정한 주제:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="70319-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="70319-104">Microsoft Lync Server 2013, 계획 도구를 사용 하 여 토폴로지에 분기 사이트를 추가 하 고 지점 사이트에서 음성 인프라를 설정 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="70319-104">We recommend using the Microsoft Lync Server 2013, Planning Tool to add branch sites to your topology and to set up your voice infrastructure in branch sites.</span></span>

<span data-ttu-id="70319-105">계획 도구를 사용 하 고 있지 않은 경우에는 먼저이 섹션의 항목에 있는 절차를 사용 하 여 지점 사이트를 추가한 다음 IP/공공 전환 전화 네트워크 (PSTN) 게이트웨이를 정의 하 고 미디어 바이패스를 사용 하거나 제외 하 여 SIP 트렁크를 구성 하 여 음성 인프라를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="70319-105">If you are not using the Planning Tool, use the procedures in the topics in this section—first, to add the branch sites, and then, to set up your voice infrastructure by defining the IP/public switched telephone network (PSTN) gateway and/or by configuring the SIP trunk (with or without media bypass).</span></span> <span data-ttu-id="70319-106">지점 사이트에 PBX (개인 분기 교환)를 연결 하는 것도 또 다른 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="70319-106">Connecting a private branch exchange (PBX) to the branch site is another option.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="70319-107">지점 사이트 복구를 제공 하려는 경우 지점 사이트에서 Survivable Branch 기기, Survivable Branch Server 또는 Standard Edition Server를 배포 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="70319-107">If you want to provide branch-site resiliency, you must deploy a Survivable Branch Appliance, a Survivable Branch Server, or Standard Edition server at the branch site.</span></span> <span data-ttu-id="70319-108">자세한 내용은 배포 설명서에서 <A href="lync-server-2013-deploying-a-survivable-branch-appliance-or-server.md">Lync server 2013을 사용 하 여 Survivable Branch 기기 또는 서버를</A> 배포 하 여 적절 하 게 <A href="lync-server-2013-deploying-lync-server.md">lync server 2013</A>를 배포 하세요.</span><span class="sxs-lookup"><span data-stu-id="70319-108">For details, see <A href="lync-server-2013-deploying-a-survivable-branch-appliance-or-server.md">Deploying a Survivable Branch Appliance or Server with Lync Server 2013</A> or <A href="lync-server-2013-deploying-lync-server.md">Deploying Lync Server 2013</A>, as appropriate, in the Deployment documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="70319-109">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="70319-109">In This Section</span></span>

  - [<span data-ttu-id="70319-110">Lync Server 2013에서 토폴로지에 분기 사이트 추가</span><span class="sxs-lookup"><span data-stu-id="70319-110">Add branch sites to your topology in Lync Server 2013</span></span>](lync-server-2013-add-branch-sites-to-your-topology.md)

  - [<span data-ttu-id="70319-111">Lync Server 2013에서 분기 사이트에 대한 PSTN 게이트웨이 정의</span><span class="sxs-lookup"><span data-stu-id="70319-111">Define a PSTN gateway for a branch site in Lync Server 2013</span></span>](lync-server-2013-define-a-pstn-gateway-for-a-branch-site.md)

  - [<span data-ttu-id="70319-112">Lync Server 2013에서 미디어 바이패스를 사용 하 여 트렁크 구성</span><span class="sxs-lookup"><span data-stu-id="70319-112">Configure a trunk with media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-with-media-bypass.md)

  - [<span data-ttu-id="70319-113">Lync Server 2013에서 미디어 바이패스 없이 트렁크 구성</span><span class="sxs-lookup"><span data-stu-id="70319-113">Configure a trunk without media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-without-media-bypass.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="70319-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="70319-114">See Also</span></span>


[<span data-ttu-id="70319-115">Lync Server 2013의 미디어 바이패스 계획</span><span class="sxs-lookup"><span data-stu-id="70319-115">Planning for media bypass in Lync Server 2013</span></span>](lync-server-2013-planning-for-media-bypass.md)  
[<span data-ttu-id="70319-116">Lync Server 2013의 PSTN 연결 계획</span><span class="sxs-lookup"><span data-stu-id="70319-116">Planning for PSTN connectivity in Lync Server 2013</span></span>](lync-server-2013-planning-for-pstn-connectivity.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

