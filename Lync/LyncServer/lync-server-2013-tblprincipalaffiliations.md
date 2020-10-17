---
title: 'Lync Server 2013: tblPrincipalAffiliations'
description: 'Lync Server 2013: tblPrincipalAffiliations'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblPrincipalAffiliations
ms:assetid: 45fd8484-5837-44d2-85bb-45c83546607c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558642(v=OCS.15)
ms:contentKeyID: 48183993
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 01c373147a58300e64f22e60e989a777c59b2653
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547484"
---
# <a name="tblprincipalaffiliations-in-lync-server-2013"></a><span data-ttu-id="39e7e-103">Lync Server 2013의 tblPrincipalAffiliations</span><span class="sxs-lookup"><span data-stu-id="39e7e-103">tblPrincipalAffiliations in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="39e7e-104">_**마지막으로 수정 된 항목:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="39e7e-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="39e7e-105">tblPrincipalAffiliations active directory 컨테이너의 도메인에서 Active Directory 도메인 서비스 보안 그룹을 비롯 한 위치에 있는 구성원을 설명 하는 사용자의 소속을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="39e7e-105">tblPrincipalAffiliations contains the principal affiliations that describe memberships in locations, including Active Directory Domain Services security groups, in Active Directory containers, in domains.</span></span>

### <a name="columns"></a><span data-ttu-id="39e7e-106">단</span><span class="sxs-lookup"><span data-stu-id="39e7e-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="39e7e-107">열</span><span class="sxs-lookup"><span data-stu-id="39e7e-107">Column</span></span></th>
<th><span data-ttu-id="39e7e-108">유형</span><span class="sxs-lookup"><span data-stu-id="39e7e-108">Type</span></span></th>
<th><span data-ttu-id="39e7e-109">설명</span><span class="sxs-lookup"><span data-stu-id="39e7e-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="39e7e-110">principalID</span><span class="sxs-lookup"><span data-stu-id="39e7e-110">principalID</span></span></p></td>
<td><p><span data-ttu-id="39e7e-111">int, null이 아님</span><span class="sxs-lookup"><span data-stu-id="39e7e-111">int, not null</span></span></p></td>
<td><p><span data-ttu-id="39e7e-112">연관된 사용자의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="39e7e-112">ID of the affiliated principal.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="39e7e-113">affiliationID</span><span class="sxs-lookup"><span data-stu-id="39e7e-113">affiliationID</span></span></p></td>
<td><p><span data-ttu-id="39e7e-114">int, null이 아님</span><span class="sxs-lookup"><span data-stu-id="39e7e-114">int, not null</span></span></p></td>
<td><p><span data-ttu-id="39e7e-p101">회원 정보를 나타내는 사용자의 ID입니다. 각 사용자(system-user-types 제외)에는 self-affiliation도 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="39e7e-p101">ID of the principal representing the affiliation. Each principal (except system-user-types) has a self-affiliation as well.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="39e7e-117">인덱스</span><span class="sxs-lookup"><span data-stu-id="39e7e-117">index</span></span></p></td>
<td><p><span data-ttu-id="39e7e-118">int, null이 아님</span><span class="sxs-lookup"><span data-stu-id="39e7e-118">int, not null</span></span></p></td>
<td><p><span data-ttu-id="39e7e-119">인덱스.</span><span class="sxs-lookup"><span data-stu-id="39e7e-119">Index.</span></span> <span data-ttu-id="39e7e-120">자체 가입 값은-1이 고, 각 &lt; principalid (affiliationId 버킷) 내에서 1부터 차례로 증가 하는 다른 인스턴스에 대 한 정보입니다 &gt; .</span><span class="sxs-lookup"><span data-stu-id="39e7e-120">The value for self-affiliations is -1, and for the other affiliations it increases sequentially from 1 within each &lt;principalID, affiliationId&gt; bucket.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="39e7e-121">updatedBy</span><span class="sxs-lookup"><span data-stu-id="39e7e-121">updatedBy</span></span></p></td>
<td><p><span data-ttu-id="39e7e-122">int, null이 아님</span><span class="sxs-lookup"><span data-stu-id="39e7e-122">int, not null</span></span></p></td>
<td><p><span data-ttu-id="39e7e-p103">최근 업데이트를 수행한 사용자입니다. 이 값은 일반적으로 Active Directory 동기화를 의미하는 1입니다.</span><span class="sxs-lookup"><span data-stu-id="39e7e-p103">Principal that did the latest update. This is usually 1, which means Active Directory Sync.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="39e7e-125">키</span><span class="sxs-lookup"><span data-stu-id="39e7e-125">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="39e7e-126">단</span><span class="sxs-lookup"><span data-stu-id="39e7e-126">Columns</span></span></th>
<th><span data-ttu-id="39e7e-127">설명</span><span class="sxs-lookup"><span data-stu-id="39e7e-127">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="39e7e-128">&lt;principalID, index, affiliationID&gt;</span><span class="sxs-lookup"><span data-stu-id="39e7e-128">&lt;principalID, index, affiliationID&gt;</span></span></p></td>
<td><p><span data-ttu-id="39e7e-129">기본 키입니다.</span><span class="sxs-lookup"><span data-stu-id="39e7e-129">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="39e7e-130">principalID</span><span class="sxs-lookup"><span data-stu-id="39e7e-130">principalID</span></span></p></td>
<td><p><span data-ttu-id="39e7e-131">tblPrincipal.prinID 테이블에서 조회 기능이 있는 외래 키입니다.</span><span class="sxs-lookup"><span data-stu-id="39e7e-131">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="39e7e-132">affiliationID</span><span class="sxs-lookup"><span data-stu-id="39e7e-132">affiliationID</span></span></p></td>
<td><p><span data-ttu-id="39e7e-133">tblPrincipal.prinID 테이블에서 조회 기능이 있는 외래 키입니다.</span><span class="sxs-lookup"><span data-stu-id="39e7e-133">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

