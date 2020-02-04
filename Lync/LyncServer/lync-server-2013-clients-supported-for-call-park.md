---
title: 'Lync Server 2013: 통화 대기에 지원되는 클라이언트'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Clients supported for Call Park
ms:assetid: c236d2ba-9d83-418c-9cbc-92541f115fb0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412958(v=OCS.15)
ms:contentKeyID: 48185320
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 52304a0241425a3b88c7f9419afa57f3d768fbb0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756462"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="clients-supported-for-call-park-in-lync-server-2013"></a><span data-ttu-id="669bd-102">Lync Server 2013의 통화 대기에 지원되는 클라이언트</span><span class="sxs-lookup"><span data-stu-id="669bd-102">Clients supported for Call Park in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="669bd-103">_**마지막으로 수정한 주제:** 2012-09-13_</span><span class="sxs-lookup"><span data-stu-id="669bd-103">_**Topic Last Modified:** 2012-09-13_</span></span>

<span data-ttu-id="669bd-104">이 섹션에서는 통화를 파킹 하는 데 사용할 수 있는 클라이언트와 파킹 된 호출을 검색 하는 데 사용할 수 있는 클라이언트를 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="669bd-104">This section identifies the clients that can be used to park calls and the clients that can be used to retrieve parked calls.</span></span>

<div>

## <a name="clients-supported-for-parking-calls"></a><span data-ttu-id="669bd-105">파킹 통화에 지원 되는 클라이언트</span><span class="sxs-lookup"><span data-stu-id="669bd-105">Clients Supported for Parking Calls</span></span>

<span data-ttu-id="669bd-106">모든 IP, PBX (사설 브랜치 교환), PSTN (공개 전환 전화 네트워크) 또는 휴대 전화는 파킹 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="669bd-106">Calls from any IP, private branch exchange (PBX), public switched telephone network (PSTN), or mobile phone can be parked.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="669bd-107">오디오 통화만 파킹 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="669bd-107">Only audio calls can be parked.</span></span> <span data-ttu-id="669bd-108">인스턴트 메시지와 회의는 파킹 될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="669bd-108">Instant messages and conferences cannot be parked.</span></span>



</div>

<span data-ttu-id="669bd-109">다음 클라이언트는 통화 공원를 사용 하 여 통화를 대기 시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="669bd-109">The following clients can use Call Park to park calls:</span></span>

  - <span data-ttu-id="669bd-110">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="669bd-110">Lync 2013</span></span>

  - <span data-ttu-id="669bd-111">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="669bd-111">Lync 2010</span></span>

  - <span data-ttu-id="669bd-112">Lync 2010 수행자</span><span class="sxs-lookup"><span data-stu-id="669bd-112">Lync 2010 Attendant</span></span>

  - <span data-ttu-id="669bd-113">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="669bd-113">Lync Phone Edition</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="669bd-114">휴대 전화는 통화 대기를 사용 하 여 통화를 대기 시킬 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="669bd-114">Mobile phones cannot use Call Park to park calls.</span></span>



</div>

</div>

<div>

## <a name="clients-supported-for-retrieving-calls"></a><span data-ttu-id="669bd-115">통화 검색에 지원 되는 클라이언트</span><span class="sxs-lookup"><span data-stu-id="669bd-115">Clients Supported for Retrieving Calls</span></span>

<span data-ttu-id="669bd-116">궤도 범위는 가상 확장 블록 (할당 된 사용자 또는 전화기 없이 확장)으로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="669bd-116">Orbit ranges are configured as blocks of virtual extensions (extensions without an assigned user or phone).</span></span> <span data-ttu-id="669bd-117">Orbits를 가상 확장으로 구성 하는 경우 휴대 전화 및 PSTN 전화는 파킹 된 전화를 검색할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="669bd-117">When you configure orbits as virtual extensions, mobile phones and PSTN phones cannot retrieve parked calls.</span></span>

<span data-ttu-id="669bd-118">페더레이션 사용자는 파킹 된 전화를 검색할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="669bd-118">Federated users cannot retrieve parked calls.</span></span>

<span data-ttu-id="669bd-119">다음 클라이언트는 통화 공원에서 파킹 된 통화를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="669bd-119">The following clients can retrieve calls that are parked on Call Park:</span></span>

  - <span data-ttu-id="669bd-120">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="669bd-120">Lync 2013</span></span>

  - <span data-ttu-id="669bd-121">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="669bd-121">Lync 2010</span></span>

  - <span data-ttu-id="669bd-122">Lync 2010 수행자</span><span class="sxs-lookup"><span data-stu-id="669bd-122">Lync 2010 Attendant</span></span>

  - <span data-ttu-id="669bd-123">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="669bd-123">Lync Phone Edition</span></span>

  - <span data-ttu-id="669bd-124">IP 공통 영역 전화</span><span class="sxs-lookup"><span data-stu-id="669bd-124">IP common area phones</span></span>

  - <span data-ttu-id="669bd-125">일반 영역 전화 및 PBX (사설 지사 교환) 전화를 포함 하 여 Lync Server 2013 인프라에 연결 된 비 IP 전화</span><span class="sxs-lookup"><span data-stu-id="669bd-125">Non-IP phones that are connected to the Lync Server 2013 infrastructure, including common area phones and private branch exchange (PBX) phones</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

