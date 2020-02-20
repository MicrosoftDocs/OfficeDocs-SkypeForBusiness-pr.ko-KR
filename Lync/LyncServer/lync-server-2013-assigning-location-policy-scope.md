---
title: 'Lync Server 2013: 위치 정책 범위 할당'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assigning location policy scope
ms:assetid: e4c66517-c593-4253-b900-7b4dd8bddf2f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205360(v=OCS.15)
ms:contentKeyID: 48185734
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 844f940c3e817dd5002a5caa6e0ec6fa17b93733
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149247"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="assigning-location-policy-scope-in-lync-server-2013"></a><span data-ttu-id="d9869-102">Lync Server 2013에서 위치 정책 범위 할당</span><span class="sxs-lookup"><span data-stu-id="d9869-102">Assigning location policy scope in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d9869-103">_**마지막으로 수정 된 항목:** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="d9869-103">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="d9869-104">다른 Lync Server 정책과 마찬가지로 위치 정책은 전역, 사이트 및 사용자의 여러 범위 수준에서 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9869-104">As with other Lync Server policies, location policies can be assigned at multiple scope levels: global, site, and user.</span></span> <span data-ttu-id="d9869-105">그러나 사용자 수준 위치 정책의 범위는 다른 Lync Server 정책과 약간 다르게 동작 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9869-105">However, the scope of user-level location policies behaves a bit differently than with other Lync Server policies.</span></span> <span data-ttu-id="d9869-106">사용자 또는 공통 영역 전화 연락처 개체와 같은 끝점 개체에는 사용자별 위치 정책을 적용 하는 것 뿐만 아니라 Lync Server 네트워크 사이트에도 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9869-106">Not only can per-user location policies be applied to endpoint objects (such as Users and Common Area Phone contact objects), they can also be applied to Lync Server network sites.</span></span> <span data-ttu-id="d9869-107">네트워크 사이트는 지리적 위치와 연결 된 클라이언트 서브넷의 그룹으로, 전체 중앙 사이트 또는 분기 사이트의 모든 서브넷 일 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d9869-107">Network sites are groupings of client subnets associated with a geographical location (but may not necessarily be all subnets in an entire central site or branch site).</span></span> <span data-ttu-id="d9869-108">네트워크 사이트의 서브넷에 연결 된 클라이언트는 자동으로 해당 네트워크 사이트에 할당 되는 위치 정책을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9869-108">Any clients connected to the subnets in a network site automatically pick up the location policy assigned to that network site.</span></span> <span data-ttu-id="d9869-109">사용자 수준 위치 정책이 사용자와 네트워크 사이트에 모두 할당 되는 경우 네트워크 사이트 기반 위치 정책이 사용자별 정책 설정 보다 우선 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9869-109">In cases where a user-level location policy is assigned both to a user and to a network site, the network site-based location policy overrides any per-user policy setting.</span></span>

<span data-ttu-id="d9869-110">각 네트워크 사이트에는 위치 정책이 할당되어 있으며 각 정책에는 서로 다른 PSTN 사용, 알림 URI 및 회의 URI 값이 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9869-110">Each network site has a location policy assigned to it, and each policy will have different PSTN Usages, Notification URIs, and Conference URIs values assigned to it.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d9869-111">이러한 특수 정책 범위 지정 동작이 발생 하는 이유는 한 office 사이트의 풀에 있는 사용자가 다른 사이트를 방문 하 여 긴급 통화를 해야 하는 경우 해당 네트워크 사이트에 적합 한 E9-1-1 통화 라우팅 설정이 어떤 풀 또는 사이트에 든 관계 없이 적용 되도록 하는 것입니다. ser이 할당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9869-111">The reason for this special policy scoping behavior is so that when a user homed on a pool at one office site visits another site and has to make an emergency call, the E9-1-1 call routing settings appropriate to that network site will apply no matter what pool or site the user is assigned to.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

