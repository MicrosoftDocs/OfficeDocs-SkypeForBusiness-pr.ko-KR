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
ms.openlocfilehash: 4998db2c00699e766b664caf79fa271af0395a6d
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42215284"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="providing-pstn-connectivity-at-a-branch-site-in-lync-server-2013"></a><span data-ttu-id="cec5e-102">Lync Server 2013의 분기 사이트에서 PSTN 연결 제공</span><span class="sxs-lookup"><span data-stu-id="cec5e-102">Providing PSTN connectivity at a branch site in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cec5e-103">_**마지막으로 수정 된 항목:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="cec5e-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="cec5e-104">Microsoft Lync Server 2013, 계획 도구를 사용 하 여 분기 사이트를 토폴로지에 추가 하 고 분기 사이트에서 음성 인프라를 설정 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="cec5e-104">We recommend using the Microsoft Lync Server 2013, Planning Tool to add branch sites to your topology and to set up your voice infrastructure in branch sites.</span></span>

<span data-ttu-id="cec5e-105">계획 도구를 사용 하지 않는 경우이 섹션의 항목에 나와 있는 절차를 사용 하 여 분기 사이트를 추가한 다음, IP/공공 전화망 (PSTN) 게이트웨이를 정의 하거나 미디어 바이패스를 포함 하거나 제외 하 여 SIP 트렁크를 구성 하 여 음성 인프라를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="cec5e-105">If you are not using the Planning Tool, use the procedures in the topics in this section—first, to add the branch sites, and then, to set up your voice infrastructure by defining the IP/public switched telephone network (PSTN) gateway and/or by configuring the SIP trunk (with or without media bypass).</span></span> <span data-ttu-id="cec5e-106">PBX(Private Branch Exchange)를 분기 사이트에 연결하여 이러한 작업을 수행할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cec5e-106">Connecting a private branch exchange (PBX) to the branch site is another option.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="cec5e-107">분기 사이트 복구를 제공 하려면 분기 사이트에서 Sba (survivable Branch 기기, Sba (survivable 분기 서버 또는 Standard Edition 서버를 배포 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cec5e-107">If you want to provide branch-site resiliency, you must deploy a Survivable Branch Appliance, a Survivable Branch Server, or Standard Edition server at the branch site.</span></span> <span data-ttu-id="cec5e-108">자세한 내용은 배포 설명서에서 <A href="lync-server-2013-deploying-a-survivable-branch-appliance-or-server.md">Lync server 2013을 사용 하 여 a Sba (survivable Branch 기기 또는 Server</A> To The <A href="lync-server-2013-deploying-lync-server.md">lync server 2013</A>을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="cec5e-108">For details, see <A href="lync-server-2013-deploying-a-survivable-branch-appliance-or-server.md">Deploying a Survivable Branch Appliance or Server with Lync Server 2013</A> or <A href="lync-server-2013-deploying-lync-server.md">Deploying Lync Server 2013</A>, as appropriate, in the Deployment documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="cec5e-109">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="cec5e-109">In This Section</span></span>

  - [<span data-ttu-id="cec5e-110">Lync Server 2013에서 토폴로지에 분기 사이트 추가</span><span class="sxs-lookup"><span data-stu-id="cec5e-110">Add branch sites to your topology in Lync Server 2013</span></span>](lync-server-2013-add-branch-sites-to-your-topology.md)

  - [<span data-ttu-id="cec5e-111">Lync Server 2013에서 분기 사이트에 대 한 PSTN 게이트웨이 정의</span><span class="sxs-lookup"><span data-stu-id="cec5e-111">Define a PSTN gateway for a branch site in Lync Server 2013</span></span>](lync-server-2013-define-a-pstn-gateway-for-a-branch-site.md)

  - [<span data-ttu-id="cec5e-112">Lync Server 2013의 미디어 바이패스로 트렁크 구성</span><span class="sxs-lookup"><span data-stu-id="cec5e-112">Configure a trunk with media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-with-media-bypass.md)

  - [<span data-ttu-id="cec5e-113">Lync Server 2013에서 미디어 바이패스 없이 트렁크 구성</span><span class="sxs-lookup"><span data-stu-id="cec5e-113">Configure a trunk without media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-without-media-bypass.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="cec5e-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cec5e-114">See Also</span></span>


[<span data-ttu-id="cec5e-115">Lync Server 2013의 미디어 바이패스 계획</span><span class="sxs-lookup"><span data-stu-id="cec5e-115">Planning for media bypass in Lync Server 2013</span></span>](lync-server-2013-planning-for-media-bypass.md)  
[<span data-ttu-id="cec5e-116">Lync Server 2013의 PSTN 연결 계획</span><span class="sxs-lookup"><span data-stu-id="cec5e-116">Planning for PSTN connectivity in Lync Server 2013</span></span>](lync-server-2013-planning-for-pstn-connectivity.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

