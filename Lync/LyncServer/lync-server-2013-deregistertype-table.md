---
title: 'Lync Server 2013: DeRegisterType 테이블'
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
ms.openlocfilehash: 915a5d0a2c5c4a5f38063b56dc133d2558aa65ac
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42042175"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deregistertype-table-in-lync-server-2013"></a><span data-ttu-id="1b3d7-102">Lync Server 2013의 DeRegisterType 테이블</span><span class="sxs-lookup"><span data-stu-id="1b3d7-102">DeRegisterType table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1b3d7-103">_**마지막으로 수정 된 항목:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="1b3d7-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="1b3d7-104">DeRegisterType 테이블은 'client initiated', 'registration expired' 또는 'client stopped responding'과 같은 사용 가능한 사용자의 등록 해제 유형 목록을 저장하는 정적 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="1b3d7-104">The DeRegisterType table is a static table that stores the list of possible user de-registers types, such as ‘client initiated’, ‘registration expired’, or ‘client stopped responding.’</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1b3d7-105">열</span><span class="sxs-lookup"><span data-stu-id="1b3d7-105">Column</span></span></th>
<th><span data-ttu-id="1b3d7-106">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="1b3d7-106">Data Type</span></span></th>
<th><span data-ttu-id="1b3d7-107">키/인덱스</span><span class="sxs-lookup"><span data-stu-id="1b3d7-107">Key/Index</span></span></th>
<th><span data-ttu-id="1b3d7-108">세부 정보</span><span class="sxs-lookup"><span data-stu-id="1b3d7-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1b3d7-109"><strong>DeRegisterTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="1b3d7-109"><strong>DeRegisterTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="1b3d7-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="1b3d7-110">tinyint</span></span></p></td>
<td><p><span data-ttu-id="1b3d7-111">Primary</span><span class="sxs-lookup"><span data-stu-id="1b3d7-111">Primary</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b3d7-112"><strong>DeRegisterReason</strong></span><span class="sxs-lookup"><span data-stu-id="1b3d7-112"><strong>DeRegisterReason</strong></span></span></p></td>
<td><p><span data-ttu-id="1b3d7-113">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="1b3d7-113">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b3d7-114">허용되는 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1b3d7-114">Allowed values:</span></span></p>
<ul>
<li><p><span data-ttu-id="1b3d7-115">0 - 알 수 없음</span><span class="sxs-lookup"><span data-stu-id="1b3d7-115">0 -- Unknown</span></span></p></li>
<li><p><span data-ttu-id="1b3d7-116">1 -- 클라이언트가 등록 취소 시작</span><span class="sxs-lookup"><span data-stu-id="1b3d7-116">1 -- Client Initiated Deregistration</span></span></p></li>
<li><p><span data-ttu-id="1b3d7-117">2 -- 등록 만료</span><span class="sxs-lookup"><span data-stu-id="1b3d7-117">2 -- Registration Expired</span></span></p></li>
<li><p><span data-ttu-id="1b3d7-118">3 -- 클라이언트 작동 중단</span><span class="sxs-lookup"><span data-stu-id="1b3d7-118">3 – Client crashed</span></span></p></li>
<li><p><span data-ttu-id="1b3d7-119">4 -- 사용자 특성 변경</span><span class="sxs-lookup"><span data-stu-id="1b3d7-119">4 -- User Attributes Changed</span></span></p></li>
<li><p><span data-ttu-id="1b3d7-120">5 -- 선호 등록자 변경</span><span class="sxs-lookup"><span data-stu-id="1b3d7-120">5 – Preferred Registrar Changed</span></span></p></li>
<li><p><span data-ttu-id="1b3d7-121">6 -- 레거시 클라이언트가 서바이벌 모드임</span><span class="sxs-lookup"><span data-stu-id="1b3d7-121">6 -- Legacy Client In Survival Mode</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

