---
title: 'Lync Server 2013: DeRegisterType 테이블'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: DeRegisterType table
ms:assetid: 09148118-6209-4fd7-a494-99118689a245
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398142(v=OCS.15)
ms:contentKeyID: 48183346
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 97d25ded1a281df0774644cd0d69f5e12d9c85a7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983246"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deregistertype-table-in-lync-server-2013"></a><span data-ttu-id="95472-102">Lync Server 2013의 DeRegisterType 테이블</span><span class="sxs-lookup"><span data-stu-id="95472-102">DeRegisterType table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="95472-103">_**마지막으로 수정한 주제:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="95472-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="95472-104">DeRegisterType 테이블은 ' 클라이언트 시작 ', ' 등록 만료 ' 또는 ' 클라이언트가 응답을 중지 했습니다. ' 등 사용 가능한 사용자의 등록 취소 형식 목록을 저장 하는 정적 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="95472-104">The DeRegisterType table is a static table that stores the list of possible user de-registers types, such as ‘client initiated’, ‘registration expired’, or ‘client stopped responding.’</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="95472-105">열</span><span class="sxs-lookup"><span data-stu-id="95472-105">Column</span></span></th>
<th><span data-ttu-id="95472-106">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="95472-106">Data Type</span></span></th>
<th><span data-ttu-id="95472-107">키/인덱스</span><span class="sxs-lookup"><span data-stu-id="95472-107">Key/Index</span></span></th>
<th><span data-ttu-id="95472-108">세부적인</span><span class="sxs-lookup"><span data-stu-id="95472-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="95472-109"><strong>DeRegisterTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="95472-109"><strong>DeRegisterTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="95472-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="95472-110">tinyint</span></span></p></td>
<td><p><span data-ttu-id="95472-111">주요한</span><span class="sxs-lookup"><span data-stu-id="95472-111">Primary</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95472-112"><strong>DeRegisterReason</strong></span><span class="sxs-lookup"><span data-stu-id="95472-112"><strong>DeRegisterReason</strong></span></span></p></td>
<td><p><span data-ttu-id="95472-113">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="95472-113">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="95472-114">허용 되는 값:</span><span class="sxs-lookup"><span data-stu-id="95472-114">Allowed values:</span></span></p>
<ul>
<li><p><span data-ttu-id="95472-115">0--알 수 없음</span><span class="sxs-lookup"><span data-stu-id="95472-115">0 -- Unknown</span></span></p></li>
<li><p><span data-ttu-id="95472-116">1--클라이언트에서 초기화 된 등록 취소</span><span class="sxs-lookup"><span data-stu-id="95472-116">1 -- Client Initiated Deregistration</span></span></p></li>
<li><p><span data-ttu-id="95472-117">2--등록이 만료 됨</span><span class="sxs-lookup"><span data-stu-id="95472-117">2 -- Registration Expired</span></span></p></li>
<li><p><span data-ttu-id="95472-118">3-클라이언트가 충돌 합니다.</span><span class="sxs-lookup"><span data-stu-id="95472-118">3 – Client crashed</span></span></p></li>
<li><p><span data-ttu-id="95472-119">4--사용자 특성이 변경 됨</span><span class="sxs-lookup"><span data-stu-id="95472-119">4 -- User Attributes Changed</span></span></p></li>
<li><p><span data-ttu-id="95472-120">5-기본 등록 기관 변경</span><span class="sxs-lookup"><span data-stu-id="95472-120">5 – Preferred Registrar Changed</span></span></p></li>
<li><p><span data-ttu-id="95472-121">6--생존 모드의 레거시 클라이언트</span><span class="sxs-lookup"><span data-stu-id="95472-121">6 -- Legacy Client In Survival Mode</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

