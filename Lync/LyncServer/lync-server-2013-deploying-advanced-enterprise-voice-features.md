---
title: 'Lync Server 2013: 고급 Enterprise Voice 기능 배포'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying advanced Enterprise Voice features
ms:assetid: 286d9c0b-9442-448f-a6e5-95b3034278fe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425753(v=OCS.15)
ms:contentKeyID: 48183675
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7446a84823d23c64c44e01ec1d7879a71c1e81b1
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154430"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploying-advanced-enterprise-voice-features-in-lync-server-2013"></a><span data-ttu-id="7667a-102">Lync Server 2013에서 고급 Enterprise Voice 기능 배포</span><span class="sxs-lookup"><span data-stu-id="7667a-102">Deploying advanced Enterprise Voice features in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7667a-103">_**마지막으로 수정 된 항목:** 2012-09-22_</span><span class="sxs-lookup"><span data-stu-id="7667a-103">_**Topic Last Modified:** 2012-09-22_</span></span>

<span data-ttu-id="7667a-104">조직에 대해 기본 Enterprise Voice 기능을 구성한 후에는 이 섹션의 절차에 따라 원하는 경우 하나 이상의 고급 Enterprise Voice 기능을 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7667a-104">After you have configured basic Enterprise Voice functionality for your organization, you can optionally deploy one or more advanced Enterprise Voice features by following the procedures in this section.</span></span>

<span data-ttu-id="7667a-105">고급 Enterprise Voice 기능에 대 한 자세한 내용은 [Lync Server 2013 설명서 계획](lync-server-2013-planning.md) 의 다음 섹션을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="7667a-105">For details about the advanced Enterprise Voice features, see the following sections of the [Planning for Lync Server 2013](lync-server-2013-planning.md) documentation:</span></span>

  - [<span data-ttu-id="7667a-106">Lync Server 2013의 통화 허용 제어 계획</span><span class="sxs-lookup"><span data-stu-id="7667a-106">Planning for call admission control in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-admission-control.md)

  - [<span data-ttu-id="7667a-107">Lync Server 2013의 응급 서비스 계획 (E9-1-1)</span><span class="sxs-lookup"><span data-stu-id="7667a-107">Planning for emergency services (E9-1-1) in Lync Server 2013</span></span>](lync-server-2013-planning-for-emergency-services-e9-1-1.md)

  - [<span data-ttu-id="7667a-108">Lync Server 2013의 미디어 바이패스 계획</span><span class="sxs-lookup"><span data-stu-id="7667a-108">Planning for media bypass in Lync Server 2013</span></span>](lync-server-2013-planning-for-media-bypass.md)

<div>

## <a name="in-this-section"></a><span data-ttu-id="7667a-109">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="7667a-109">In This Section</span></span>

  - [<span data-ttu-id="7667a-110">Lync Server 2013의 네트워크 지역, 사이트 및 서브넷 정보</span><span class="sxs-lookup"><span data-stu-id="7667a-110">About network regions, sites, and subnets in Lync Server 2013</span></span>](lync-server-2013-about-network-regions-sites-and-subnets.md)

  - [<span data-ttu-id="7667a-111">Lync Server 2013에서 네트워크 지역 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="7667a-111">Create or modify a network region in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-network-region.md)

  - [<span data-ttu-id="7667a-112">Lync Server 2013에서 네트워크 사이트 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="7667a-112">Create or modify a network site in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-network-site.md)

  - [<span data-ttu-id="7667a-113">Lync Server 2013에서 서브넷을 네트워크 사이트에 연결</span><span class="sxs-lookup"><span data-stu-id="7667a-113">Associate a subnet with a network site in Lync Server 2013</span></span>](lync-server-2013-associate-a-subnet-with-a-network-site.md)

  - [<span data-ttu-id="7667a-114">Lync Server 2013에서 통화 허용 제어 구성</span><span class="sxs-lookup"><span data-stu-id="7667a-114">Configure call admission control in Lync Server 2013</span></span>](lync-server-2013-configure-call-admission-control.md)

  - [<span data-ttu-id="7667a-115">Lync Server 2013에서 향상 된 9-1-1 구성</span><span class="sxs-lookup"><span data-stu-id="7667a-115">Configure Enhanced 9-1-1 in Lync Server 2013</span></span>](lync-server-2013-configure-enhanced-9-1-1.md)

  - [<span data-ttu-id="7667a-116">Lync Server 2013에서 미디어 바이패스 구성</span><span class="sxs-lookup"><span data-stu-id="7667a-116">Configure media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-media-bypass.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

