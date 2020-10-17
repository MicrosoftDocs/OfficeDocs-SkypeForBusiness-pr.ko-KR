---
title: 'Lync Server 2013: 통화 대기에 지원 되는 클라이언트'
description: 'Lync Server 2013: 통화 대기에 지원 되는 클라이언트'
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
ms.openlocfilehash: a923f0e62c246a12b811628d578ab571f4f13e36
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543494"
---
# <a name="clients-supported-for-call-park-in-lync-server-2013"></a><span data-ttu-id="66b5a-103">Lync Server 2013의 통화 대기에 지원 되는 클라이언트</span><span class="sxs-lookup"><span data-stu-id="66b5a-103">Clients supported for Call Park in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="66b5a-104">_**마지막으로 수정 된 항목:** 2012-09-13_</span><span class="sxs-lookup"><span data-stu-id="66b5a-104">_**Topic Last Modified:** 2012-09-13_</span></span>

<span data-ttu-id="66b5a-105">이 섹션에서는 통화를 대기로 설정하는 데 사용할 수 있는 클라이언트 및 대기 중인 통화를 재개하는 데 사용할 수 있는 클라이언트를 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="66b5a-105">This section identifies the clients that can be used to park calls and the clients that can be used to retrieve parked calls.</span></span>

<div>

## <a name="clients-supported-for-parking-calls"></a><span data-ttu-id="66b5a-106">통화를 대기로 설정하는 데 지원되는 클라이언트</span><span class="sxs-lookup"><span data-stu-id="66b5a-106">Clients Supported for Parking Calls</span></span>

<span data-ttu-id="66b5a-107">모든 IP, PBX(Private Branch Exchange), PSTN(공중 전화망) 또는 휴대폰의 통화를 대기로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66b5a-107">Calls from any IP, private branch exchange (PBX), public switched telephone network (PSTN), or mobile phone can be parked.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="66b5a-p101">오디오 통화만 대기로 설정할 수 있습니다. 인스턴트 메시지 및 회의는 대기로 설정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="66b5a-p101">Only audio calls can be parked. Instant messages and conferences cannot be parked.</span></span>



</div>

<span data-ttu-id="66b5a-110">다음 클라이언트는 통화 대기를 사용 하 여 통화를 대기 시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66b5a-110">The following clients can use Call Park to park calls:</span></span>

  - <span data-ttu-id="66b5a-111">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="66b5a-111">Lync 2013</span></span>

  - <span data-ttu-id="66b5a-112">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="66b5a-112">Lync 2010</span></span>

  - <span data-ttu-id="66b5a-113">Lync 2010 Attendant</span><span class="sxs-lookup"><span data-stu-id="66b5a-113">Lync 2010 Attendant</span></span>

  - <span data-ttu-id="66b5a-114">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="66b5a-114">Lync Phone Edition</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="66b5a-115">휴대폰에서는 통화 대기를 사용 하 여 통화를 대기 시킬 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="66b5a-115">Mobile phones cannot use Call Park to park calls.</span></span>



</div>

</div>

<div>

## <a name="clients-supported-for-retrieving-calls"></a><span data-ttu-id="66b5a-116">통화를 재개하는 데 지원되는 클라이언트</span><span class="sxs-lookup"><span data-stu-id="66b5a-116">Clients Supported for Retrieving Calls</span></span>

<span data-ttu-id="66b5a-p102">파킹된 통화 번호 범위는 가상 내선 번호(사용자나 전화가 할당되지 않은 내선 번호) 블록으로 구성됩니다. 파킹된 통화 번호를 가상 내선 번호로 구성하면 휴대폰 및 PSTN 전화에서 대기로 설정된 통화를 재개할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="66b5a-p102">Orbit ranges are configured as blocks of virtual extensions (extensions without an assigned user or phone). When you configure orbits as virtual extensions, mobile phones and PSTN phones cannot retrieve parked calls.</span></span>

<span data-ttu-id="66b5a-119">페더레이션 사용자는 대기로 설정된 통화를 재개할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="66b5a-119">Federated users cannot retrieve parked calls.</span></span>

<span data-ttu-id="66b5a-120">다음 클라이언트는 통화 대기에서 파킹 된 통화를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66b5a-120">The following clients can retrieve calls that are parked on Call Park:</span></span>

  - <span data-ttu-id="66b5a-121">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="66b5a-121">Lync 2013</span></span>

  - <span data-ttu-id="66b5a-122">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="66b5a-122">Lync 2010</span></span>

  - <span data-ttu-id="66b5a-123">Lync 2010 Attendant</span><span class="sxs-lookup"><span data-stu-id="66b5a-123">Lync 2010 Attendant</span></span>

  - <span data-ttu-id="66b5a-124">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="66b5a-124">Lync Phone Edition</span></span>

  - <span data-ttu-id="66b5a-125">IP 공통 영역 전화</span><span class="sxs-lookup"><span data-stu-id="66b5a-125">IP common area phones</span></span>

  - <span data-ttu-id="66b5a-126">공통 영역 전화 및 PBX (private branch exchange) 전화를 비롯 하 여 Lync Server 2013 인프라에 연결 된 비 IP 전화</span><span class="sxs-lookup"><span data-stu-id="66b5a-126">Non-IP phones that are connected to the Lync Server 2013 infrastructure, including common area phones and private branch exchange (PBX) phones</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

