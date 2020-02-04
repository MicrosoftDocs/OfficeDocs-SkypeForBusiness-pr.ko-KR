---
title: 'Lync Server 2013: E9에서 사용자 사용-1-1'
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
ms.openlocfilehash: 86d5032defc7322e96662dcfe6357bd30c598e45
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735608"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-users-for-e9-1-1-in-lync-server-2013"></a><span data-ttu-id="82479-102">Lync Server 2013에서 E9에 대해 사용자 설정-1-1</span><span class="sxs-lookup"><span data-stu-id="82479-102">Enabling users for E9-1-1 in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="82479-103">_**마지막으로 수정한 주제:** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="82479-103">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="82479-104">클라이언트 등록 중에 Lync Server는 위치 정책을 사용 하 여 Enterprise Voice 사용이 가능한 사용자의 E9-1-1 속성을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="82479-104">During client registration, Lync Server uses a location policy to configure the E9-1-1 properties for Enterprise Voice-enabled users.</span></span> <span data-ttu-id="82479-105">이 정책에는 E9-1-1이 구현 되는 방법을 정의 하는 설정이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82479-105">This policy contains the settings that define how E9-1-1 is implemented.</span></span> <span data-ttu-id="82479-106">예를 들어 위치 정책에는 긴급 전화 접속 문자열, 위치 정보 서비스에서 자동으로 위치를 제공 하지 않는 경우 사용자가 수동으로 위치를 입력 해야 하는지 여부 등의 정보가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="82479-106">For example, the location policy contains information such as the emergency dial string, and whether or not a user is required to manually enter a location if the Location Information service does not automatically provide one.</span></span> <span data-ttu-id="82479-107">위치 정책에 대 한 전체 정의는 [Lync Server 2013의 위치 정책 정의](lync-server-2013-defining-the-location-policy.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="82479-107">For a complete definition of a location policy, see [Defining the location policy for Lync Server 2013](lync-server-2013-defining-the-location-policy.md).</span></span>

<span data-ttu-id="82479-108">Lync Server는 위치 정책을 서브넷에 기반 하 여 클라이언트에 게 할당 하거나, 전역, 사이트별 또는 사용자 단위 정책을 기반으로 하는 사용자에 게 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82479-108">Lync Server can assign a location policy to clients based on subnet, or to users based on a global, per-site, or per-user policy.</span></span> <span data-ttu-id="82479-109">사용자를 설정 하는 방법을 결정 하려면 먼저 다음 질문에 대답 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="82479-109">To help decide how you will enable users, you should first answer the following questions.</span></span>

  - <span data-ttu-id="82479-110">**모든 사용자를 설정 하거나 엔터프라이즈의 특정 지리적 영역에 대 한 지원을 제한할 계획 입니까?**</span><span class="sxs-lookup"><span data-stu-id="82479-110">**Do you plan to enable all users, or limit support to specific geographic areas of the enterprise?**</span></span>  
    <span data-ttu-id="82479-111">전역 위치 정책을 사용 하 여 엔터프라이즈의 모든 사용자에 게 위치를 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82479-111">You can assign a location to all users in your enterprise by using a global location policy.</span></span> <span data-ttu-id="82479-112">그러나 위치 정책을 Lync Server 네트워크 사이트에 할당 한 다음 사이트에 서브넷을 추가 하 여 E9-1-1 지원을 엔터프라이즈 내에서 선택 된 위치로 제한 하 고 각 사이트 별로 E9-1 라우팅 동작을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82479-112">However, by assigning a location policy to a Lync Server network site and then adding subnets to the site, you can limit E9-1-1 support to selected locations within the enterprise and specify E9-1-1 routing behavior on a per-site basis.</span></span>

<!-- end list -->

  - <span data-ttu-id="82479-113">**사용자 정책을 통해 개별 사용자를 사용할 계획 입니까?**</span><span class="sxs-lookup"><span data-stu-id="82479-113">**Do you plan to enable individual users through a user policy?**</span></span>  
    <span data-ttu-id="82479-114">E9-1-1 지원을 사용자 지정 하려는 경우 특정 사용자 또는 공용 지역 전화 연락처 개체에 위치 정책을 직접 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82479-114">You can assign location policies directly to specific users or common area phone contact objects if you want to customize their E9-1-1 support.</span></span>

<!-- end list -->

  - <span data-ttu-id="82479-115">**클라이언트가 네트워크 외부에서 로밍 하거나 정의 되지 않은 서브넷에서 연결 하는 경우 E9-1-1에 대해 클라이언트를 계속 사용할 수 있게 하려면**</span><span class="sxs-lookup"><span data-stu-id="82479-115">**When clients roam outside the network or connect from an undefined subnet, should the clients still be enabled for E9-1-1?**</span></span>  
    <span data-ttu-id="82479-116">사용자에 게 전역, 사이트 또는 사용자 단위 위치 정책을 할당 한 경우에는 클라이언트가 정의 된 서브넷 내에 없거나 위치 정보 서비스에 위치를 찾을 수 없는 경우 수동으로 클라이언트에 위치를 입력 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="82479-116">If users are assigned a global, site, or per-user location policy, they can be required to manually enter a location into the client if the client is not located within a defined subnet or no location has been found by the Location Information service.</span></span> <span data-ttu-id="82479-117">자세한 내용은 [Lync Server 2013에서 수동으로 위치를 가져오기 위한 사용자 환경 정의](lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="82479-117">For details, see [Defining the user experience for manually acquiring a location in Lync Server 2013](lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

