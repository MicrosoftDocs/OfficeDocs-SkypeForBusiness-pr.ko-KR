---
title: 'Lync Server 2013: 통화 허용 제어 관리'
description: 'Lync Server 2013: 통화 허용 제어를 관리 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing call admission control
ms:assetid: b0bd4783-6f47-408d-b010-2e30f9bc1770
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721851(v=OCS.15)
ms:contentKeyID: 49733784
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0a1c01bff6d1dce48dea314b6704cc0f5ff7d6b2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48549464"
---
# <a name="managing-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="57bbc-103">Lync Server 2013의 통화 허용 제어 관리</span><span class="sxs-lookup"><span data-stu-id="57bbc-103">Managing call admission control in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="57bbc-104">_**마지막으로 수정 된 항목:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="57bbc-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="57bbc-105">CAC(통화 허용 제어)는 사용 가능한 네트워크 대역폭에 따라 음성 또는 화상 통화와 같은 실시간 통신 세션을 설정하도록 허용할지 여부를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="57bbc-105">Call admission control (CAC) determines, based on available network bandwidth, whether to allow real-time communications sessions such as voice or video calls to be established.</span></span> <span data-ttu-id="57bbc-106">다음 절차에 따라 Lync Server 2013 환경에 대해 서로 다른 CAC 기능을 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="57bbc-106">Use the following procedures to manage different CAC features for your Lync Server 2013 environment.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="57bbc-107">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="57bbc-107">In This Section</span></span>

  - [<span data-ttu-id="57bbc-108">Lync Server 2013에서 통화 허용 제어 사용</span><span class="sxs-lookup"><span data-stu-id="57bbc-108">Enabling call admission control in Lync Server 2013</span></span>](lync-server-2013-enabling-call-admission-control.md)

  - [<span data-ttu-id="57bbc-109">Lync Server 2013에서 네트워크 대역폭 정책 프로필 관리</span><span class="sxs-lookup"><span data-stu-id="57bbc-109">Managing network bandwidth policy profiles in Lync Server 2013</span></span>](lync-server-2013-managing-network-bandwidth-policy-profiles.md)

  - [<span data-ttu-id="57bbc-110">Lync Server 2013의 네트워크 지역</span><span class="sxs-lookup"><span data-stu-id="57bbc-110">Network regions in Lync Server 2013</span></span>](lync-server-2013-network-regions.md)

  - [<span data-ttu-id="57bbc-111">Lync Server 2013의 네트워크 지역 경로</span><span class="sxs-lookup"><span data-stu-id="57bbc-111">Network region routes in Lync Server 2013</span></span>](lync-server-2013-network-region-routes.md)

  - [<span data-ttu-id="57bbc-112">Lync Server 2013의 사이트에 대 한 통화 허용 제어</span><span class="sxs-lookup"><span data-stu-id="57bbc-112">Call admission control for sites in Lync Server 2013</span></span>](lync-server-2013-call-admission-control-for-sites.md)

  - [<span data-ttu-id="57bbc-113">Lync Server 2013에서 미디어 바이패스 사용 및 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="57bbc-113">Enabling and disabling media bypass in Lync Server 2013</span></span>](lync-server-2013-enabling-and-disabling-media-bypass.md)

  - [<span data-ttu-id="57bbc-114">Lync Server 2013에서 네트워크 지역 연결</span><span class="sxs-lookup"><span data-stu-id="57bbc-114">Linking network regions in Lync Server 2013</span></span>](lync-server-2013-linking-network-regions.md)

  - [<span data-ttu-id="57bbc-115">Lync Server 2013에서 네트워크 서브넷 관리</span><span class="sxs-lookup"><span data-stu-id="57bbc-115">Managing network subnets in Lync Server 2013</span></span>](lync-server-2013-managing-network-subnets.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="57bbc-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="57bbc-116">See Also</span></span>


[<span data-ttu-id="57bbc-117">Lync Server 2013의 통화 허용 제어 개요</span><span class="sxs-lookup"><span data-stu-id="57bbc-117">Overview of call admission control in Lync Server 2013</span></span>](lync-server-2013-overview-of-call-admission-control.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

