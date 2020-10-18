---
title: 'Lync Server 2013: tblPrincipalMemberDifference'
description: 'Lync Server 2013: tblPrincipalMemberDifference'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblPrincipalMemberDifference
ms:assetid: 0b94f555-6888-4fe0-a048-4660a2513276
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558612(v=OCS.15)
ms:contentKeyID: 48183379
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ce7c770a6fed02dc27d2493816fae58943d391a6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573224"
---
# <a name="tblprincipalmemberdifference-in-lync-server-2013"></a><span data-ttu-id="44002-103">Lync Server 2013의 tblPrincipalMemberDifference</span><span class="sxs-lookup"><span data-stu-id="44002-103">tblPrincipalMemberDifference in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="44002-104">_**마지막으로 수정 된 항목:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="44002-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="44002-105">tblPrincipalMemberDifference에는 이후 Active Directory 도메인 서비스 동기화 단계에서 아직 처리 되지 않은 그룹 구성원 자격 변경 내용 (추가 및 제거 된 구성원 모두)이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="44002-105">tblPrincipalMemberDifference contains group membership changes (both added and removed members) that have not yet been processed by the later Active Directory Domain Services Sync steps.</span></span>

### <a name="columns"></a><span data-ttu-id="44002-106">단</span><span class="sxs-lookup"><span data-stu-id="44002-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="44002-107">열</span><span class="sxs-lookup"><span data-stu-id="44002-107">Column</span></span></th>
<th><span data-ttu-id="44002-108">유형</span><span class="sxs-lookup"><span data-stu-id="44002-108">Type</span></span></th>
<th><span data-ttu-id="44002-109">설명</span><span class="sxs-lookup"><span data-stu-id="44002-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="44002-110">Principal.pringuid</span><span class="sxs-lookup"><span data-stu-id="44002-110">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="44002-111">GUID, null이 아님</span><span class="sxs-lookup"><span data-stu-id="44002-111">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="44002-112">변경된 그룹의 사용자 GUID입니다.</span><span class="sxs-lookup"><span data-stu-id="44002-112">Principal GUID of the group that changed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="44002-113">memberADPath</span><span class="sxs-lookup"><span data-stu-id="44002-113">memberADPath</span></span></p></td>
<td><p><span data-ttu-id="44002-114">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="44002-114">nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="44002-115">구성원의 고유 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="44002-115">Distinguished name of the member.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="44002-116">memberRemoved 됨</span><span class="sxs-lookup"><span data-stu-id="44002-116">memberRemoved</span></span></p></td>
<td><p><span data-ttu-id="44002-117">bit, null이 아님</span><span class="sxs-lookup"><span data-stu-id="44002-117">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="44002-p101">구성원이 추가된 경우 False입니다. 구성원이 제거된 경우 True입니다.</span><span class="sxs-lookup"><span data-stu-id="44002-p101">False if the member was added. True if the member was removed.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="44002-120">키</span><span class="sxs-lookup"><span data-stu-id="44002-120">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="44002-121">열</span><span class="sxs-lookup"><span data-stu-id="44002-121">Column</span></span></th>
<th><span data-ttu-id="44002-122">설명</span><span class="sxs-lookup"><span data-stu-id="44002-122">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="44002-123">&lt;Principal.pringuid, memberADPath&gt;</span><span class="sxs-lookup"><span data-stu-id="44002-123">&lt;prinGuid, memberADPath&gt;</span></span></p></td>
<td><p><span data-ttu-id="44002-124">기본 키입니다.</span><span class="sxs-lookup"><span data-stu-id="44002-124">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

