---
title: 'Lync Server 2013: DeRegisterType 테이블'
description: 'Lync Server 2013: DeRegisterType 테이블'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DeRegisterType table
ms:assetid: 09148118-6209-4fd7-a494-99118689a245
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398142(v=OCS.15)
ms:contentKeyID: 48183346
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: afad63c2abeba3e91565e07dac75d0ac6c96ca3a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555354"
---
# <a name="deregistertype-table-in-lync-server-2013"></a><span data-ttu-id="eb316-103">Lync Server 2013의 DeRegisterType 테이블</span><span class="sxs-lookup"><span data-stu-id="eb316-103">DeRegisterType table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eb316-104">_**마지막으로 수정 된 항목:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="eb316-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="eb316-105">DeRegisterType 테이블은 'client initiated', 'registration expired' 또는 'client stopped responding'과 같은 사용 가능한 사용자의 등록 해제 유형 목록을 저장하는 정적 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="eb316-105">The DeRegisterType table is a static table that stores the list of possible user de-registers types, such as ‘client initiated’, ‘registration expired’, or ‘client stopped responding.’</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="eb316-106">열</span><span class="sxs-lookup"><span data-stu-id="eb316-106">Column</span></span></th>
<th><span data-ttu-id="eb316-107">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="eb316-107">Data Type</span></span></th>
<th><span data-ttu-id="eb316-108">키/인덱스</span><span class="sxs-lookup"><span data-stu-id="eb316-108">Key/Index</span></span></th>
<th><span data-ttu-id="eb316-109">세부 정보</span><span class="sxs-lookup"><span data-stu-id="eb316-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="eb316-110"><strong>DeRegisterTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="eb316-110"><strong>DeRegisterTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="eb316-111">tinyint</span><span class="sxs-lookup"><span data-stu-id="eb316-111">tinyint</span></span></p></td>
<td><p><span data-ttu-id="eb316-112">Primary</span><span class="sxs-lookup"><span data-stu-id="eb316-112">Primary</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eb316-113"><strong>DeRegisterReason</strong></span><span class="sxs-lookup"><span data-stu-id="eb316-113"><strong>DeRegisterReason</strong></span></span></p></td>
<td><p><span data-ttu-id="eb316-114">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="eb316-114">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="eb316-115">허용되는 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="eb316-115">Allowed values:</span></span></p>
<ul>
<li><p><span data-ttu-id="eb316-116">0 - 알 수 없음</span><span class="sxs-lookup"><span data-stu-id="eb316-116">0 -- Unknown</span></span></p></li>
<li><p><span data-ttu-id="eb316-117">1 -- 클라이언트가 등록 취소 시작</span><span class="sxs-lookup"><span data-stu-id="eb316-117">1 -- Client Initiated Deregistration</span></span></p></li>
<li><p><span data-ttu-id="eb316-118">2 -- 등록 만료</span><span class="sxs-lookup"><span data-stu-id="eb316-118">2 -- Registration Expired</span></span></p></li>
<li><p><span data-ttu-id="eb316-119">3 -- 클라이언트 작동 중단</span><span class="sxs-lookup"><span data-stu-id="eb316-119">3 – Client crashed</span></span></p></li>
<li><p><span data-ttu-id="eb316-120">4 -- 사용자 특성 변경</span><span class="sxs-lookup"><span data-stu-id="eb316-120">4 -- User Attributes Changed</span></span></p></li>
<li><p><span data-ttu-id="eb316-121">5 -- 선호 등록자 변경</span><span class="sxs-lookup"><span data-stu-id="eb316-121">5 – Preferred Registrar Changed</span></span></p></li>
<li><p><span data-ttu-id="eb316-122">6 -- 레거시 클라이언트가 서바이벌 모드임</span><span class="sxs-lookup"><span data-stu-id="eb316-122">6 -- Legacy Client In Survival Mode</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

