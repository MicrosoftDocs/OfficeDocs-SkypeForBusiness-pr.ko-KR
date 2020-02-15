---
title: 'Lync Server 2013: 미디어 바이패스를 위해 네트워크 사이트에 서브넷 연결'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Associate subnets with network sites for media bypass
ms:assetid: 5bc632b7-1446-470f-b332-48ea0ca4d1fd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398401(v=OCS.15)
ms:contentKeyID: 48184244
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dbe244426b6c2b7f83ef8070f995305a2a02ef31
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044780"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="associate-subnets-with-network-sites-for-media-bypass-in-lync-server-2013"></a><span data-ttu-id="64bd9-102">Lync Server 2013에서 미디어 바이패스를 위해 네트워크 사이트에 서브넷 연결</span><span class="sxs-lookup"><span data-stu-id="64bd9-102">Associate subnets with network sites for media bypass in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="64bd9-103">_**마지막으로 수정 된 항목:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="64bd9-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="64bd9-104">이 항목에서는 미디어 바이패스 전역 설정을 구성했으며 미디어 바이패스를 위한 네트워크 지역 및 네트워크 사이트를 구성했다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="64bd9-104">This topic assumes that you have configured media bypass global settings and that you have configured network region and network sites for media bypass.</span></span>



</div>

<span data-ttu-id="64bd9-p101">네트워크의 모든 서브넷은 특정 네트워크 사이트에 연결되어야 합니다. 서브넷 정보를 사용하여 끝점이 있는 네트워크 사이트를 확인하기 때문입니다. 세션의 두 당사자 위치가 모두 확인되면 미디어 바이패스에서는 처리할 미디어를 보낼 위치를 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64bd9-p101">Every subnet in your network must be associated with a specific network site. This is because subnet information is used to determine the network site on which an endpoint is located. When the locations of both parties in a session are known, media bypass can determine where to send media for processing.</span></span>

<span data-ttu-id="64bd9-108">미디어 바이패스에서 서브넷을 네트워크 사이트에 연결하기 위한 특수한 요구 사항은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="64bd9-108">Media bypass does not have any special requirements for associating subnets with network sites.</span></span> <span data-ttu-id="64bd9-109">토폴로지의 서브넷과 네트워크 사이트 간의 연결을 만들려면 [Lync Server 2013에서 서브넷과 네트워크 사이트를 연결](lync-server-2013-associate-a-subnet-with-a-network-site.md)하는 절차를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="64bd9-109">To create an association between the subnets and network sites in your topology, follow the procedures in [Associate a subnet with a network site in Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md).</span></span>

<div>

## <a name="next-steps-create-bandwidth-policy-profiles"></a><span data-ttu-id="64bd9-110">다음 단계: 대역폭 정책 프로필 만들기</span><span class="sxs-lookup"><span data-stu-id="64bd9-110">Next Steps: Create Bandwidth Policy Profiles</span></span>

<span data-ttu-id="64bd9-p103">미디어 바이패스를 위해 네트워크 사이트와 서브넷을 연결한 후에는 미디어 바이패스용으로 서브넷을 연결 상태가 양호한 항목과 그렇지 않은 항목으로 분할하는 대역폭 정책 프로필을 하나 이상 만들어야 합니다. 대역폭 제약 조건이 없는 네트워크 사이트가 포함된 네트워크 지역 내의 모든 서브넷은 연결 상태가 양호하므로 미디어 바이패스를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64bd9-p103">After you associate subnets with network sites for media bypass, you must create one or more bandwidth policy profiles that will partition subnets into those with good connectivity and those without, for the purposes of media bypass. All subnets within a network region with network sites that do not have bandwidth constraints have good connectivity, and, therefore, those subnets can use media bypass.</span></span>

<span data-ttu-id="64bd9-113">대역폭 정책 프로필을 구성 하는 절차는 [Lync Server 2013에서 대역폭 정책 프로필 만들기](lync-server-2013-create-bandwidth-policy-profiles.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="64bd9-113">For procedures to configure bandwidth policy profiles, see [Create bandwidth policy profiles in Lync Server 2013](lync-server-2013-create-bandwidth-policy-profiles.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

