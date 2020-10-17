---
title: 'Lync Server 2013: tblPrincipalAffiliations'
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
ms.openlocfilehash: ec2ef70b70ff496852a753a9e15a38f80de1509b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48523745"
---
# <a name="tblprincipalaffiliations-in-lync-server-2013"></a><span data-ttu-id="d3394-102">Lync Server 2013의 tblPrincipalAffiliations</span><span class="sxs-lookup"><span data-stu-id="d3394-102">tblPrincipalAffiliations in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d3394-103">_**마지막으로 수정 된 항목:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="d3394-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="d3394-104">tblPrincipalAffiliations active directory 컨테이너의 도메인에서 Active Directory 도메인 서비스 보안 그룹을 비롯 한 위치에 있는 구성원을 설명 하는 사용자의 소속을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3394-104">tblPrincipalAffiliations contains the principal affiliations that describe memberships in locations, including Active Directory Domain Services security groups, in Active Directory containers, in domains.</span></span>

### <a name="columns"></a><span data-ttu-id="d3394-105">단</span><span class="sxs-lookup"><span data-stu-id="d3394-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d3394-106">열</span><span class="sxs-lookup"><span data-stu-id="d3394-106">Column</span></span></th>
<th><span data-ttu-id="d3394-107">유형</span><span class="sxs-lookup"><span data-stu-id="d3394-107">Type</span></span></th>
<th><span data-ttu-id="d3394-108">설명</span><span class="sxs-lookup"><span data-stu-id="d3394-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d3394-109">principalID</span><span class="sxs-lookup"><span data-stu-id="d3394-109">principalID</span></span></p></td>
<td><p><span data-ttu-id="d3394-110">int, null이 아님</span><span class="sxs-lookup"><span data-stu-id="d3394-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="d3394-111">연관된 사용자의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="d3394-111">ID of the affiliated principal.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d3394-112">affiliationID</span><span class="sxs-lookup"><span data-stu-id="d3394-112">affiliationID</span></span></p></td>
<td><p><span data-ttu-id="d3394-113">int, null이 아님</span><span class="sxs-lookup"><span data-stu-id="d3394-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="d3394-p101">회원 정보를 나타내는 사용자의 ID입니다. 각 사용자(system-user-types 제외)에는 self-affiliation도 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3394-p101">ID of the principal representing the affiliation. Each principal (except system-user-types) has a self-affiliation as well.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d3394-116">인덱스</span><span class="sxs-lookup"><span data-stu-id="d3394-116">index</span></span></p></td>
<td><p><span data-ttu-id="d3394-117">int, null이 아님</span><span class="sxs-lookup"><span data-stu-id="d3394-117">int, not null</span></span></p></td>
<td><p><span data-ttu-id="d3394-118">인덱스.</span><span class="sxs-lookup"><span data-stu-id="d3394-118">Index.</span></span> <span data-ttu-id="d3394-119">자체 가입 값은-1이 고, 각 &lt; principalid (affiliationId 버킷) 내에서 1부터 차례로 증가 하는 다른 인스턴스에 대 한 정보입니다 &gt; .</span><span class="sxs-lookup"><span data-stu-id="d3394-119">The value for self-affiliations is -1, and for the other affiliations it increases sequentially from 1 within each &lt;principalID, affiliationId&gt; bucket.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d3394-120">updatedBy</span><span class="sxs-lookup"><span data-stu-id="d3394-120">updatedBy</span></span></p></td>
<td><p><span data-ttu-id="d3394-121">int, null이 아님</span><span class="sxs-lookup"><span data-stu-id="d3394-121">int, not null</span></span></p></td>
<td><p><span data-ttu-id="d3394-p103">최근 업데이트를 수행한 사용자입니다. 이 값은 일반적으로 Active Directory 동기화를 의미하는 1입니다.</span><span class="sxs-lookup"><span data-stu-id="d3394-p103">Principal that did the latest update. This is usually 1, which means Active Directory Sync.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="d3394-124">키</span><span class="sxs-lookup"><span data-stu-id="d3394-124">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d3394-125">단</span><span class="sxs-lookup"><span data-stu-id="d3394-125">Columns</span></span></th>
<th><span data-ttu-id="d3394-126">설명</span><span class="sxs-lookup"><span data-stu-id="d3394-126">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d3394-127">&lt;principalID, index, affiliationID&gt;</span><span class="sxs-lookup"><span data-stu-id="d3394-127">&lt;principalID, index, affiliationID&gt;</span></span></p></td>
<td><p><span data-ttu-id="d3394-128">기본 키입니다.</span><span class="sxs-lookup"><span data-stu-id="d3394-128">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d3394-129">principalID</span><span class="sxs-lookup"><span data-stu-id="d3394-129">principalID</span></span></p></td>
<td><p><span data-ttu-id="d3394-130">tblPrincipal.prinID 테이블에서 조회 기능이 있는 외래 키입니다.</span><span class="sxs-lookup"><span data-stu-id="d3394-130">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d3394-131">affiliationID</span><span class="sxs-lookup"><span data-stu-id="d3394-131">affiliationID</span></span></p></td>
<td><p><span data-ttu-id="d3394-132">tblPrincipal.prinID 테이블에서 조회 기능이 있는 외래 키입니다.</span><span class="sxs-lookup"><span data-stu-id="d3394-132">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

