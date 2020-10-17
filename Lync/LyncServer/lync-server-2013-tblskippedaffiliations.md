---
title: 'Lync Server 2013: tblSkippedAffiliations'
description: 'Lync Server 2013: tblSkippedAffiliations.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblSkippedAffiliations
ms:assetid: 0b129b54-a7a8-42a6-9279-0e08410c06ec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558611(v=OCS.15)
ms:contentKeyID: 48183373
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 31746cee7302d34a1d19b3059ca1da6beab9345d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48563804"
---
# <a name="tblskippedaffiliations-in-lync-server-2013"></a><span data-ttu-id="7904f-103">Lync Server 2013의 tblSkippedAffiliations</span><span class="sxs-lookup"><span data-stu-id="7904f-103">tblSkippedAffiliations in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7904f-104">_**마지막으로 수정 된 항목:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="7904f-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="7904f-105">tblSkippedAffiliations에는 읽을 수 없는 이유 (대개 Active Directory 도메인 서비스 액세스 오류)가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7904f-105">tblSkippedAffiliations contains the affiliations that could not be read (usually due to Active Directory Domain Services access errors).</span></span>

### <a name="columns"></a><span data-ttu-id="7904f-106">단</span><span class="sxs-lookup"><span data-stu-id="7904f-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7904f-107">열</span><span class="sxs-lookup"><span data-stu-id="7904f-107">Column</span></span></th>
<th><span data-ttu-id="7904f-108">유형</span><span class="sxs-lookup"><span data-stu-id="7904f-108">Type</span></span></th>
<th><span data-ttu-id="7904f-109">설명</span><span class="sxs-lookup"><span data-stu-id="7904f-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7904f-110">Tblprincipal.prinid</span><span class="sxs-lookup"><span data-stu-id="7904f-110">prinID</span></span></p></td>
<td><p><span data-ttu-id="7904f-111">int, null이 아님</span><span class="sxs-lookup"><span data-stu-id="7904f-111">int, not null</span></span></p></td>
<td><p><span data-ttu-id="7904f-112">사용자 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="7904f-112">Principal ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7904f-113">affDescription</span><span class="sxs-lookup"><span data-stu-id="7904f-113">affDescription</span></span></p></td>
<td><p><span data-ttu-id="7904f-114">nvarchar(256), null이 아님</span><span class="sxs-lookup"><span data-stu-id="7904f-114">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="7904f-115">회원 정보를 식별하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="7904f-115">A string identifying the affiliation.</span></span></p>
<p><span data-ttu-id="7904f-116">형식: guid: {0} uri: {1} &gt; id:{2}</span><span class="sxs-lookup"><span data-stu-id="7904f-116">The format is: guid: {0} uri: {1}&gt; id: {2}</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7904f-117">updatedBy</span><span class="sxs-lookup"><span data-stu-id="7904f-117">updatedBy</span></span></p></td>
<td><p><span data-ttu-id="7904f-118">int, null이 아님</span><span class="sxs-lookup"><span data-stu-id="7904f-118">int, not null</span></span></p></td>
<td><p><span data-ttu-id="7904f-p101">이 행을 업데이트한 사용자의 ID입니다. 이러한 항목에 대해서는 Active Directory 동기화가 유일한 소스이므로 이 값은 항상 1(시스템 사용자)입니다.</span><span class="sxs-lookup"><span data-stu-id="7904f-p101">ID of the principal that updated this row. It is always 1 (system user) because Active Directory Sync is the only source for these entries.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="7904f-121">키</span><span class="sxs-lookup"><span data-stu-id="7904f-121">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7904f-122">열 (s)</span><span class="sxs-lookup"><span data-stu-id="7904f-122">Column(s)</span></span></th>
<th><span data-ttu-id="7904f-123">설명</span><span class="sxs-lookup"><span data-stu-id="7904f-123">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7904f-124">&lt;Tblprincipal.prinid, affDescription&gt;</span><span class="sxs-lookup"><span data-stu-id="7904f-124">&lt;prinID, affDescription&gt;</span></span></p></td>
<td><p><span data-ttu-id="7904f-125">기본 키입니다.</span><span class="sxs-lookup"><span data-stu-id="7904f-125">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7904f-126">Tblprincipal.prinid</span><span class="sxs-lookup"><span data-stu-id="7904f-126">prinID</span></span></p></td>
<td><p><span data-ttu-id="7904f-127">tblPrincipal.prinID 테이블에서 조회 기능이 있는 외래 키입니다.</span><span class="sxs-lookup"><span data-stu-id="7904f-127">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

