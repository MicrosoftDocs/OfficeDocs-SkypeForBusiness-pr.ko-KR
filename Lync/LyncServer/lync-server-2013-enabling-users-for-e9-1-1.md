---
title: 'Lync Server 2013: 사용자가 E9-1-1을 사용 하도록 설정'
description: 'Lync Server 2013: 사용자가 E9-1-1을 사용 하도록 설정 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling users for E9-1-1
ms:assetid: 3cc64f5b-492e-4c47-9713-3c376f2aad02
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425892(v=OCS.15)
ms:contentKeyID: 48183884
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6ba29406dc0d7a1140c83a1a9d271afca5d6b0c7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546444"
---
# <a name="enabling-users-for-e9-1-1-in-lync-server-2013"></a><span data-ttu-id="e2add-103">Lync Server 2013에서 E9-1-1에 대해 사용자를 사용 하도록 설정</span><span class="sxs-lookup"><span data-stu-id="e2add-103">Enabling users for E9-1-1 in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e2add-104">_**마지막으로 수정 된 항목:** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="e2add-104">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="e2add-105">클라이언트 등록 중에 Lync Server는 위치 정책을 사용 하 여 Enterprise Voice 사용이 가능한 사용자에 대 한 E9-1-1 속성을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2add-105">During client registration, Lync Server uses a location policy to configure the E9-1-1 properties for Enterprise Voice-enabled users.</span></span> <span data-ttu-id="e2add-106">이 정책에는 E9-1-1 구현 방법을 정의하는 설정이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="e2add-106">This policy contains the settings that define how E9-1-1 is implemented.</span></span> <span data-ttu-id="e2add-107">예를 들어 위치 정책에는 비상 다이얼 문자열과 같은 정보가 포함 되 고, 위치 정보 서비스가 자동으로이를 제공 하지 않는 경우에는 위치를 수동으로 입력 해야 하는지 여부</span><span class="sxs-lookup"><span data-stu-id="e2add-107">For example, the location policy contains information such as the emergency dial string, and whether or not a user is required to manually enter a location if the Location Information service does not automatically provide one.</span></span> <span data-ttu-id="e2add-108">위치 정책에 대 한 자세한 정의는 [Lync Server 2013에 대 한 위치 정책 정의](lync-server-2013-defining-the-location-policy.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="e2add-108">For a complete definition of a location policy, see [Defining the location policy for Lync Server 2013](lync-server-2013-defining-the-location-policy.md).</span></span>

<span data-ttu-id="e2add-109">Lync Server에서는 위치 정책을 서브넷을 기반으로 하는 클라이언트에 할당 하거나 전역, 사이트별 또는 사용자별 정책을 기반으로 사용자에 게 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2add-109">Lync Server can assign a location policy to clients based on subnet, or to users based on a global, per-site, or per-user policy.</span></span> <span data-ttu-id="e2add-110">사용자를 설정하는 방법을 결정하기 위해서는 먼저 다음과 같은 질문을 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2add-110">To help decide how you will enable users, you should first answer the following questions.</span></span>

  - <span data-ttu-id="e2add-111">**모든 사용자를 설정하시겠습니까? 아니면 해당 기업의 특정 영역으로만 지원을 제한하시겠습니까?**</span><span class="sxs-lookup"><span data-stu-id="e2add-111">**Do you plan to enable all users, or limit support to specific geographic areas of the enterprise?**</span></span>  
    <span data-ttu-id="e2add-112">전역 위치 정책을 사용하여 기업 내 모든 사용자에게 위치를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2add-112">You can assign a location to all users in your enterprise by using a global location policy.</span></span> <span data-ttu-id="e2add-113">그러나 위치 정책을 Lync Server 네트워크 사이트에 할당 한 다음 사이트에 서브넷을 추가 하 여 E9-1-1 지원을 엔터프라이즈 내의 선택한 위치로 제한 하 고 사이트별로 E9-1-1 라우팅 동작을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2add-113">However, by assigning a location policy to a Lync Server network site and then adding subnets to the site, you can limit E9-1-1 support to selected locations within the enterprise and specify E9-1-1 routing behavior on a per-site basis.</span></span>

<!-- end list -->

  - <span data-ttu-id="e2add-114">**사용자 정책을 통해 개별 사용자를 설정할 계획이 있습니까?**</span><span class="sxs-lookup"><span data-stu-id="e2add-114">**Do you plan to enable individual users through a user policy?**</span></span>  
    <span data-ttu-id="e2add-115">E9-1-1 지원을 사용자 지정하려는 경우 특정 사용자 또는 공통 영역 전화 연락처 개체에 직접 위치 정책을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2add-115">You can assign location policies directly to specific users or common area phone contact objects if you want to customize their E9-1-1 support.</span></span>

<!-- end list -->

  - <span data-ttu-id="e2add-116">**클라이언트가 네트워크 외부에서 로밍하거나 정의되지 않은 서브넷에서 연결할 경우에도 해당 클라이언트에 대해 E9-1-1을 설정해야 합니까?**</span><span class="sxs-lookup"><span data-stu-id="e2add-116">**When clients roam outside the network or connect from an undefined subnet, should the clients still be enabled for E9-1-1?**</span></span>  
    <span data-ttu-id="e2add-117">사용자에 게 전역, 사이트 또는 사용자별 위치 정책이 할당 된 경우 클라이언트가 정의 된 서브넷 내에 없거나 위치 정보 서비스에서 위치를 찾지 못한 경우 클라이언트에 위치를 수동으로 입력 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2add-117">If users are assigned a global, site, or per-user location policy, they can be required to manually enter a location into the client if the client is not located within a defined subnet or no location has been found by the Location Information service.</span></span> <span data-ttu-id="e2add-118">자세한 내용은 [Lync Server 2013에서 위치를 수동으로 가져오기 위한 사용자 환경 정의](lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="e2add-118">For details, see [Defining the user experience for manually acquiring a location in Lync Server 2013](lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

