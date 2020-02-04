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
ms.openlocfilehash: 3976b98fddc96ad08f3de4413bf8f38ec3525496
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764154"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblprincipalaffiliations-in-lync-server-2013"></a><span data-ttu-id="1e241-102">Lync Server 2013의 tblPrincipalAffiliations</span><span class="sxs-lookup"><span data-stu-id="1e241-102">tblPrincipalAffiliations in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1e241-103">_**마지막으로 수정한 주제:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="1e241-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="1e241-104">tblPrincipalAffiliations active directory 컨테이너에서 Active Directory 도메인 서비스 보안 그룹을 포함 한 위치의 구성원 자격을 도메인에 설명 하는 주요 소속을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e241-104">tblPrincipalAffiliations contains the principal affiliations that describe memberships in locations, including Active Directory Domain Services security groups, in Active Directory containers, in domains.</span></span>

### <a name="columns"></a><span data-ttu-id="1e241-105">열</span><span class="sxs-lookup"><span data-stu-id="1e241-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1e241-106">열</span><span class="sxs-lookup"><span data-stu-id="1e241-106">Column</span></span></th>
<th><span data-ttu-id="1e241-107">유형</span><span class="sxs-lookup"><span data-stu-id="1e241-107">Type</span></span></th>
<th><span data-ttu-id="1e241-108">설명</span><span class="sxs-lookup"><span data-stu-id="1e241-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1e241-109">principalID</span><span class="sxs-lookup"><span data-stu-id="1e241-109">principalID</span></span></p></td>
<td><p><span data-ttu-id="1e241-110">int, null 아님</span><span class="sxs-lookup"><span data-stu-id="1e241-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="1e241-111">관련 된 사용자의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="1e241-111">ID of the affiliated principal.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1e241-112">affiliationID</span><span class="sxs-lookup"><span data-stu-id="1e241-112">affiliationID</span></span></p></td>
<td><p><span data-ttu-id="1e241-113">int, null 아님</span><span class="sxs-lookup"><span data-stu-id="1e241-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="1e241-114">소속을 나타내는 주체의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="1e241-114">ID of the principal representing the affiliation.</span></span> <span data-ttu-id="1e241-115">각 주도자 (시스템-사용자 유형 제외)에는 자기 관련 된 것도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e241-115">Each principal (except system-user-types) has a self-affiliation as well.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1e241-116">색인</span><span class="sxs-lookup"><span data-stu-id="1e241-116">index</span></span></p></td>
<td><p><span data-ttu-id="1e241-117">int, null 아님</span><span class="sxs-lookup"><span data-stu-id="1e241-117">int, not null</span></span></p></td>
<td><p><span data-ttu-id="1e241-118">색인.</span><span class="sxs-lookup"><span data-stu-id="1e241-118">Index.</span></span> <span data-ttu-id="1e241-119">자기 소속에 대 한 값은-1 이며, 다른 소속은 각 &lt;principalid, affiliationId&gt; 버킷에 있는 1에서 순차적으로 증가 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e241-119">The value for self-affiliations is -1, and for the other affiliations it increases sequentially from 1 within each &lt;principalID, affiliationId&gt; bucket.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1e241-120">updatedBy</span><span class="sxs-lookup"><span data-stu-id="1e241-120">updatedBy</span></span></p></td>
<td><p><span data-ttu-id="1e241-121">int, null 아님</span><span class="sxs-lookup"><span data-stu-id="1e241-121">int, not null</span></span></p></td>
<td><p><span data-ttu-id="1e241-122">최신 업데이트를 수행한 보안 주체입니다.</span><span class="sxs-lookup"><span data-stu-id="1e241-122">Principal that did the latest update.</span></span> <span data-ttu-id="1e241-123">이는 일반적으로 Active Directory 동기화를 의미 하는 1입니다.</span><span class="sxs-lookup"><span data-stu-id="1e241-123">This is usually 1, which means Active Directory Sync.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="1e241-124">핵심</span><span class="sxs-lookup"><span data-stu-id="1e241-124">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1e241-125">열</span><span class="sxs-lookup"><span data-stu-id="1e241-125">Columns</span></span></th>
<th><span data-ttu-id="1e241-126">설명</span><span class="sxs-lookup"><span data-stu-id="1e241-126">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1e241-127">&lt;principalID, index, affiliationID&gt;</span><span class="sxs-lookup"><span data-stu-id="1e241-127">&lt;principalID, index, affiliationID&gt;</span></span></p></td>
<td><p><span data-ttu-id="1e241-128">기본 키입니다.</span><span class="sxs-lookup"><span data-stu-id="1e241-128">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1e241-129">principalID</span><span class="sxs-lookup"><span data-stu-id="1e241-129">principalID</span></span></p></td>
<td><p><span data-ttu-id="1e241-130">TblPrincipal 테이블에 조회를 포함 하는 외래 키입니다.</span><span class="sxs-lookup"><span data-stu-id="1e241-130">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1e241-131">affiliationID</span><span class="sxs-lookup"><span data-stu-id="1e241-131">affiliationID</span></span></p></td>
<td><p><span data-ttu-id="1e241-132">TblPrincipal 테이블에 조회를 포함 하는 외래 키입니다.</span><span class="sxs-lookup"><span data-stu-id="1e241-132">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

