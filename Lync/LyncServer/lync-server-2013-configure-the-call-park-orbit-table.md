---
title: 'Lync Server 2013: 통화 대기 궤도 테이블 구성'
description: 'Lync Server 2013: 통화 대기 궤도 테이블을 구성 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure the Call Park orbit table
ms:assetid: e5cc0c19-7b2c-48e7-a21d-cfb23c842f0f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399020(v=OCS.15)
ms:contentKeyID: 48185666
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ce9fb35c2958a426888d83d075064c88ddae4bfa
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544984"
---
# <a name="configure-the-call-park-orbit-table-in-lync-server-2013"></a><span data-ttu-id="4657e-103">Lync Server 2013의 통화 대기 궤도 테이블 구성</span><span class="sxs-lookup"><span data-stu-id="4657e-103">Configure the Call Park orbit table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4657e-104">_**마지막으로 수정 된 항목:** 2012-09-10_</span><span class="sxs-lookup"><span data-stu-id="4657e-104">_**Topic Last Modified:** 2012-09-10_</span></span>

<span data-ttu-id="4657e-105">통화 대기는 궤도에서 파킹 통화를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4657e-105">Call Park uses orbits for parking calls.</span></span> <span data-ttu-id="4657e-106">사용자가 통화를 대기 및 검색할 수 있으려면 통화 대기 궤도 테이블을 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4657e-106">Before users can park and retrieve calls, you must configure the Call Park orbit table.</span></span> <span data-ttu-id="4657e-107">조직에서 파킹 통화를 위해 예약할 내선 번호의 범위를 지정 하 고 각 범위에 대 한 핸들을 처리할 통화 대기 풀을 지정 하 여 해당 범위에 대 한 라우팅을 정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4657e-107">You need to specify the ranges of extension numbers (orbits) that your organization will reserve for parking calls and define the routing for those ranges by specifying which Call Park pool handles each range.</span></span> <span data-ttu-id="4657e-108">궤도 범위를 정의 하는 경우에는 모든 궤도를 너무 빨리 다시 사용할 수 없도록 충분 한 궤도을 확보 하는 것이 목표입니다.</span><span class="sxs-lookup"><span data-stu-id="4657e-108">When you define orbit ranges, the goal is to have enough orbits so that any one orbit is not reused too quickly, but not so many orbits that you limit the number of extensions available for users or other services.</span></span> <span data-ttu-id="4657e-109">통화 대기 응용 프로그램이 배포 된 각 Lync Server 풀에 대해 통화 대기 궤도 범위를 여러 개 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4657e-109">You can create multiple Call Park orbit ranges for each Lync Server pool where the Call Park application is deployed.</span></span> <span data-ttu-id="4657e-110">각 통화 대기 궤도 범위에는 전역적으로 고유한 이름과 고유한 내선 번호가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4657e-110">Each Call Park orbit range must have a globally unique name and a unique set of extensions.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="4657e-111">궤도 범위는 일반적으로 100 개 이하의 궤도을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="4657e-111">An orbit range typically encompasses 100 or fewer orbits.</span></span> <span data-ttu-id="4657e-112">각 범위는 범위 당 최대 1만 궤도 보다 작으며, 풀 당 5만을 초과 하는 경우를 제외 하면 훨씬 더 커질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4657e-112">Each range can be much larger, as long as it is smaller than the maximum of 10,000 orbits per range and you have fewer than 50,000 orbits per pool.</span></span> <span data-ttu-id="4657e-113">범위가 너무 작으면 궤도가 보다 빠르게 다시 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4657e-113">If a range is too small, the orbits are reused more quickly.</span></span>



</div>

<span data-ttu-id="4657e-114">사용 중인 궤도 범위에 대해 가상 내선 번호 블록 (사용자 또는 전화가 할당 되지 않은 확장명)을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4657e-114">Use blocks of virtual extensions (extensions that have no user or phone assigned to them) for your orbit ranges.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4657e-115">직접 연결 된 전화 걸기 (\*) 번호를 통화 대기 번호 표에 있는 궤도 번호로 지정 하는 것은 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4657e-115">Assigning Direct Inward Dialing (DID) numbers as orbit numbers in the Call Park orbit table is not supported.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="4657e-116">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="4657e-116">In This Section</span></span>

[<span data-ttu-id="4657e-117">Lync Server 2013에서 통화 대기 번호 범위 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="4657e-117">Create or modify a Call Park orbit range in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-call-park-orbit-range.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

