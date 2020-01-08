---
title: 'Lync Server 2013: 위치 정책 범위 지정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Assigning location policy scope
ms:assetid: e4c66517-c593-4253-b900-7b4dd8bddf2f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205360(v=OCS.15)
ms:contentKeyID: 48185734
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6c44bef383690856d873d64ab6218b0f14219e73
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983819"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="assigning-location-policy-scope-in-lync-server-2013"></a><span data-ttu-id="8e7a3-102">Lync Server 2013에서 위치 정책 범위 지정</span><span class="sxs-lookup"><span data-stu-id="8e7a3-102">Assigning location policy scope in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8e7a3-103">_**마지막으로 수정한 주제:** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="8e7a3-103">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="8e7a3-104">다른 Lync Server 정책과 마찬가지로 위치 정책은 전역, 사이트 및 사용자의 여러 범위 수준에서 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e7a3-104">As with other Lync Server policies, location policies can be assigned at multiple scope levels: global, site, and user.</span></span> <span data-ttu-id="8e7a3-105">그러나 사용자 수준 위치 정책의 범위는 다른 Lync Server 정책과 약간 다르게 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e7a3-105">However, the scope of user-level location policies behaves a bit differently than with other Lync Server policies.</span></span> <span data-ttu-id="8e7a3-106">끝점 개체 (예: 사용자 및 공용 지역 전화 연락처 개체)에는 사용자 단위 위치 정책을 적용할 수 있을 뿐만 아니라 Lync Server 네트워크 사이트에도 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e7a3-106">Not only can per-user location policies be applied to endpoint objects (such as Users and Common Area Phone contact objects), they can also be applied to Lync Server network sites.</span></span> <span data-ttu-id="8e7a3-107">네트워크 사이트는 지리적 위치와 관련 된 클라이언트 서브넷의 그룹 이지만, 전체 중앙 사이트 또는 지사 사이트의 모든 서브넷 일 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8e7a3-107">Network sites are groupings of client subnets associated with a geographical location (but may not necessarily be all subnets in an entire central site or branch site).</span></span> <span data-ttu-id="8e7a3-108">네트워크 사이트의 서브넷에 연결 된 클라이언트는 해당 네트워크 사이트에 할당 된 위치 정책을 자동으로 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e7a3-108">Any clients connected to the subnets in a network site automatically pick up the location policy assigned to that network site.</span></span> <span data-ttu-id="8e7a3-109">사용자 수준 위치 정책이 사용자와 네트워크 사이트에 모두 할당 되는 경우 네트워크 사이트 기반 위치 정책은 사용자별 정책 설정 보다 우선 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e7a3-109">In cases where a user-level location policy is assigned both to a user and to a network site, the network site-based location policy overrides any per-user policy setting.</span></span>

<span data-ttu-id="8e7a3-110">각 네트워크 사이트에는 위치 정책이 할당 되며 각 정책에는 서로 다른 PSTN 용도, 알림 Uri 및 전화 회의 Uri 값이 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8e7a3-110">Each network site has a location policy assigned to it, and each policy will have different PSTN Usages, Notification URIs, and Conference URIs values assigned to it.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8e7a3-111">이 특수 정책 범위 지정 동작이 발생 하는 이유는 한 office 사이트의 풀에 속한 사용자가 다른 사이트를 방문할 때 긴급 통화를 해야 할 때 해당 네트워크 사이트에 적합 한 E9-1-1 통화 라우팅 설정이 어떤 풀이나 사이트에 관계 없이 적용 될 수 있기 때문입니다. ser이 할당 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="8e7a3-111">The reason for this special policy scoping behavior is so that when a user homed on a pool at one office site visits another site and has to make an emergency call, the E9-1-1 call routing settings appropriate to that network site will apply no matter what pool or site the user is assigned to.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

