---
title: 'Lync Server 2013: 통화 대기에 지원 되는 클라이언트'
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
ms.openlocfilehash: 74e9231c99754f0916d1ddf94ba36d1dce81fb1f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48499265"
---
# <a name="clients-supported-for-call-park-in-lync-server-2013"></a><span data-ttu-id="2cdd7-102">Lync Server 2013의 통화 대기에 지원 되는 클라이언트</span><span class="sxs-lookup"><span data-stu-id="2cdd7-102">Clients supported for Call Park in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2cdd7-103">_**마지막으로 수정 된 항목:** 2012-09-13_</span><span class="sxs-lookup"><span data-stu-id="2cdd7-103">_**Topic Last Modified:** 2012-09-13_</span></span>

<span data-ttu-id="2cdd7-104">이 섹션에서는 통화를 대기로 설정하는 데 사용할 수 있는 클라이언트 및 대기 중인 통화를 재개하는 데 사용할 수 있는 클라이언트를 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="2cdd7-104">This section identifies the clients that can be used to park calls and the clients that can be used to retrieve parked calls.</span></span>

<div>

## <a name="clients-supported-for-parking-calls"></a><span data-ttu-id="2cdd7-105">통화를 대기로 설정하는 데 지원되는 클라이언트</span><span class="sxs-lookup"><span data-stu-id="2cdd7-105">Clients Supported for Parking Calls</span></span>

<span data-ttu-id="2cdd7-106">모든 IP, PBX(Private Branch Exchange), PSTN(공중 전화망) 또는 휴대폰의 통화를 대기로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2cdd7-106">Calls from any IP, private branch exchange (PBX), public switched telephone network (PSTN), or mobile phone can be parked.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2cdd7-p101">오디오 통화만 대기로 설정할 수 있습니다. 인스턴트 메시지 및 회의는 대기로 설정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2cdd7-p101">Only audio calls can be parked. Instant messages and conferences cannot be parked.</span></span>



</div>

<span data-ttu-id="2cdd7-109">다음 클라이언트는 통화 대기를 사용 하 여 통화를 대기 시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2cdd7-109">The following clients can use Call Park to park calls:</span></span>

  - <span data-ttu-id="2cdd7-110">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="2cdd7-110">Lync 2013</span></span>

  - <span data-ttu-id="2cdd7-111">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="2cdd7-111">Lync 2010</span></span>

  - <span data-ttu-id="2cdd7-112">Lync 2010 Attendant</span><span class="sxs-lookup"><span data-stu-id="2cdd7-112">Lync 2010 Attendant</span></span>

  - <span data-ttu-id="2cdd7-113">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="2cdd7-113">Lync Phone Edition</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2cdd7-114">휴대폰에서는 통화 대기를 사용 하 여 통화를 대기 시킬 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2cdd7-114">Mobile phones cannot use Call Park to park calls.</span></span>



</div>

</div>

<div>

## <a name="clients-supported-for-retrieving-calls"></a><span data-ttu-id="2cdd7-115">통화를 재개하는 데 지원되는 클라이언트</span><span class="sxs-lookup"><span data-stu-id="2cdd7-115">Clients Supported for Retrieving Calls</span></span>

<span data-ttu-id="2cdd7-p102">파킹된 통화 번호 범위는 가상 내선 번호(사용자나 전화가 할당되지 않은 내선 번호) 블록으로 구성됩니다. 파킹된 통화 번호를 가상 내선 번호로 구성하면 휴대폰 및 PSTN 전화에서 대기로 설정된 통화를 재개할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2cdd7-p102">Orbit ranges are configured as blocks of virtual extensions (extensions without an assigned user or phone). When you configure orbits as virtual extensions, mobile phones and PSTN phones cannot retrieve parked calls.</span></span>

<span data-ttu-id="2cdd7-118">페더레이션 사용자는 대기로 설정된 통화를 재개할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2cdd7-118">Federated users cannot retrieve parked calls.</span></span>

<span data-ttu-id="2cdd7-119">다음 클라이언트는 통화 대기에서 파킹 된 통화를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2cdd7-119">The following clients can retrieve calls that are parked on Call Park:</span></span>

  - <span data-ttu-id="2cdd7-120">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="2cdd7-120">Lync 2013</span></span>

  - <span data-ttu-id="2cdd7-121">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="2cdd7-121">Lync 2010</span></span>

  - <span data-ttu-id="2cdd7-122">Lync 2010 Attendant</span><span class="sxs-lookup"><span data-stu-id="2cdd7-122">Lync 2010 Attendant</span></span>

  - <span data-ttu-id="2cdd7-123">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="2cdd7-123">Lync Phone Edition</span></span>

  - <span data-ttu-id="2cdd7-124">IP 공통 영역 전화</span><span class="sxs-lookup"><span data-stu-id="2cdd7-124">IP common area phones</span></span>

  - <span data-ttu-id="2cdd7-125">공통 영역 전화 및 PBX (private branch exchange) 전화를 비롯 하 여 Lync Server 2013 인프라에 연결 된 비 IP 전화</span><span class="sxs-lookup"><span data-stu-id="2cdd7-125">Non-IP phones that are connected to the Lync Server 2013 infrastructure, including common area phones and private branch exchange (PBX) phones</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

