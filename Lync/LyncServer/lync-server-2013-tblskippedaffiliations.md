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
ms.openlocfilehash: 510f9559091395665019dad699f346f26e81b1ab
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731198"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblskippedaffiliations-in-lync-server-2013"></a><span data-ttu-id="bf3f7-102">Lync Server 2013의 tblSkippedAffiliations</span><span class="sxs-lookup"><span data-stu-id="bf3f7-102">tblSkippedAffiliations in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bf3f7-103">_**마지막으로 수정한 주제:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="bf3f7-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="bf3f7-104">tblSkippedAffiliations에는 읽을 수 없는 소속 (일반적으로 Active Directory 도메인 서비스 액세스 오류로 인해)이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bf3f7-104">tblSkippedAffiliations contains the affiliations that could not be read (usually due to Active Directory Domain Services access errors).</span></span>

### <a name="columns"></a><span data-ttu-id="bf3f7-105">열</span><span class="sxs-lookup"><span data-stu-id="bf3f7-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bf3f7-106">열</span><span class="sxs-lookup"><span data-stu-id="bf3f7-106">Column</span></span></th>
<th><span data-ttu-id="bf3f7-107">유형</span><span class="sxs-lookup"><span data-stu-id="bf3f7-107">Type</span></span></th>
<th><span data-ttu-id="bf3f7-108">설명</span><span class="sxs-lookup"><span data-stu-id="bf3f7-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bf3f7-109">prinID</span><span class="sxs-lookup"><span data-stu-id="bf3f7-109">prinID</span></span></p></td>
<td><p><span data-ttu-id="bf3f7-110">int, null 아님</span><span class="sxs-lookup"><span data-stu-id="bf3f7-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="bf3f7-111">Principal ID.</span><span class="sxs-lookup"><span data-stu-id="bf3f7-111">Principal ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bf3f7-112">affDescription</span><span class="sxs-lookup"><span data-stu-id="bf3f7-112">affDescription</span></span></p></td>
<td><p><span data-ttu-id="bf3f7-113">nvarchar (256), null 아님</span><span class="sxs-lookup"><span data-stu-id="bf3f7-113">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="bf3f7-114">소속을 식별 하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="bf3f7-114">A string identifying the affiliation.</span></span></p>
<p><span data-ttu-id="bf3f7-115">형식: guid: {0} uri: {1} &gt; id:{2}</span><span class="sxs-lookup"><span data-stu-id="bf3f7-115">The format is: guid: {0} uri: {1}&gt; id: {2}</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bf3f7-116">updatedBy</span><span class="sxs-lookup"><span data-stu-id="bf3f7-116">updatedBy</span></span></p></td>
<td><p><span data-ttu-id="bf3f7-117">int, null 아님</span><span class="sxs-lookup"><span data-stu-id="bf3f7-117">int, not null</span></span></p></td>
<td><p><span data-ttu-id="bf3f7-118">이 행을 업데이트 한 사용자의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="bf3f7-118">ID of the principal that updated this row.</span></span> <span data-ttu-id="bf3f7-119">Active Directory 동기화가 이러한 항목에 대 한 유일한 원본 이므로 항상 1 (시스템 사용자)입니다.</span><span class="sxs-lookup"><span data-stu-id="bf3f7-119">It is always 1 (system user) because Active Directory Sync is the only source for these entries.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="bf3f7-120">핵심</span><span class="sxs-lookup"><span data-stu-id="bf3f7-120">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bf3f7-121">개 열</span><span class="sxs-lookup"><span data-stu-id="bf3f7-121">Column(s)</span></span></th>
<th><span data-ttu-id="bf3f7-122">설명</span><span class="sxs-lookup"><span data-stu-id="bf3f7-122">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bf3f7-123">&lt;prinID, affDescription&gt;</span><span class="sxs-lookup"><span data-stu-id="bf3f7-123">&lt;prinID, affDescription&gt;</span></span></p></td>
<td><p><span data-ttu-id="bf3f7-124">기본 키입니다.</span><span class="sxs-lookup"><span data-stu-id="bf3f7-124">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bf3f7-125">prinID</span><span class="sxs-lookup"><span data-stu-id="bf3f7-125">prinID</span></span></p></td>
<td><p><span data-ttu-id="bf3f7-126">TblPrincipal 테이블에 조회를 포함 하는 외래 키입니다.</span><span class="sxs-lookup"><span data-stu-id="bf3f7-126">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

