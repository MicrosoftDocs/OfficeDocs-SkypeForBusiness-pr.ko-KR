---
title: 'Lync Server 2013: tblSkippedAffiliations'
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
ms.openlocfilehash: 28751281bfbc8809c2be23e3bfdb6466b85d63f7
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48536195"
---
# <a name="tblskippedaffiliations-in-lync-server-2013"></a><span data-ttu-id="ff468-102">Lync Server 2013의 tblSkippedAffiliations</span><span class="sxs-lookup"><span data-stu-id="ff468-102">tblSkippedAffiliations in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ff468-103">_**마지막으로 수정 된 항목:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="ff468-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="ff468-104">tblSkippedAffiliations에는 읽을 수 없는 이유 (대개 Active Directory 도메인 서비스 액세스 오류)가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ff468-104">tblSkippedAffiliations contains the affiliations that could not be read (usually due to Active Directory Domain Services access errors).</span></span>

### <a name="columns"></a><span data-ttu-id="ff468-105">단</span><span class="sxs-lookup"><span data-stu-id="ff468-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ff468-106">열</span><span class="sxs-lookup"><span data-stu-id="ff468-106">Column</span></span></th>
<th><span data-ttu-id="ff468-107">유형</span><span class="sxs-lookup"><span data-stu-id="ff468-107">Type</span></span></th>
<th><span data-ttu-id="ff468-108">설명</span><span class="sxs-lookup"><span data-stu-id="ff468-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ff468-109">Tblprincipal.prinid</span><span class="sxs-lookup"><span data-stu-id="ff468-109">prinID</span></span></p></td>
<td><p><span data-ttu-id="ff468-110">int, null이 아님</span><span class="sxs-lookup"><span data-stu-id="ff468-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="ff468-111">사용자 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="ff468-111">Principal ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff468-112">affDescription</span><span class="sxs-lookup"><span data-stu-id="ff468-112">affDescription</span></span></p></td>
<td><p><span data-ttu-id="ff468-113">nvarchar(256), null이 아님</span><span class="sxs-lookup"><span data-stu-id="ff468-113">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="ff468-114">회원 정보를 식별하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="ff468-114">A string identifying the affiliation.</span></span></p>
<p><span data-ttu-id="ff468-115">형식: guid: {0} uri: {1} &gt; id:{2}</span><span class="sxs-lookup"><span data-stu-id="ff468-115">The format is: guid: {0} uri: {1}&gt; id: {2}</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ff468-116">updatedBy</span><span class="sxs-lookup"><span data-stu-id="ff468-116">updatedBy</span></span></p></td>
<td><p><span data-ttu-id="ff468-117">int, null이 아님</span><span class="sxs-lookup"><span data-stu-id="ff468-117">int, not null</span></span></p></td>
<td><p><span data-ttu-id="ff468-p101">이 행을 업데이트한 사용자의 ID입니다. 이러한 항목에 대해서는 Active Directory 동기화가 유일한 소스이므로 이 값은 항상 1(시스템 사용자)입니다.</span><span class="sxs-lookup"><span data-stu-id="ff468-p101">ID of the principal that updated this row. It is always 1 (system user) because Active Directory Sync is the only source for these entries.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="ff468-120">키</span><span class="sxs-lookup"><span data-stu-id="ff468-120">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ff468-121">열 (s)</span><span class="sxs-lookup"><span data-stu-id="ff468-121">Column(s)</span></span></th>
<th><span data-ttu-id="ff468-122">설명</span><span class="sxs-lookup"><span data-stu-id="ff468-122">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ff468-123">&lt;Tblprincipal.prinid, affDescription&gt;</span><span class="sxs-lookup"><span data-stu-id="ff468-123">&lt;prinID, affDescription&gt;</span></span></p></td>
<td><p><span data-ttu-id="ff468-124">기본 키입니다.</span><span class="sxs-lookup"><span data-stu-id="ff468-124">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff468-125">Tblprincipal.prinid</span><span class="sxs-lookup"><span data-stu-id="ff468-125">prinID</span></span></p></td>
<td><p><span data-ttu-id="ff468-126">tblPrincipal.prinID 테이블에서 조회 기능이 있는 외래 키입니다.</span><span class="sxs-lookup"><span data-stu-id="ff468-126">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

