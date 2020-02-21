---
title: 'Lync Server 2013: tblPrincipalMembers'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblPrincipalMembers
ms:assetid: 9a3e24cf-6ef7-4b82-99fc-50ba41800b6f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615022(v=OCS.15)
ms:contentKeyID: 48184965
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ba78067f076169a808129d83c8d4202e183a3a8f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42214424"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblprincipalmembers-in-lync-server-2013"></a><span data-ttu-id="36749-102">Lync Server 2013의 tblPrincipalMembers</span><span class="sxs-lookup"><span data-stu-id="36749-102">tblPrincipalMembers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="36749-103">_**마지막으로 수정 된 항목:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="36749-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="36749-104">tblPrincipalMembers에는 사용자 구성원 자격이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="36749-104">tblPrincipalMembers contains principal memberships.</span></span>

### <a name="columns"></a><span data-ttu-id="36749-105">단</span><span class="sxs-lookup"><span data-stu-id="36749-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="36749-106">열</span><span class="sxs-lookup"><span data-stu-id="36749-106">Column</span></span></th>
<th><span data-ttu-id="36749-107">형식</span><span class="sxs-lookup"><span data-stu-id="36749-107">Type</span></span></th>
<th><span data-ttu-id="36749-108">설명</span><span class="sxs-lookup"><span data-stu-id="36749-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="36749-109">Tblprincipal.prinid</span><span class="sxs-lookup"><span data-stu-id="36749-109">prinID</span></span></p></td>
<td><p><span data-ttu-id="36749-110">int, null이 아님</span><span class="sxs-lookup"><span data-stu-id="36749-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="36749-111">사용자 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="36749-111">Principal ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="36749-112">memberADPath</span><span class="sxs-lookup"><span data-stu-id="36749-112">memberADPath</span></span></p></td>
<td><p><span data-ttu-id="36749-113">nvarchar(384), null이 아님</span><span class="sxs-lookup"><span data-stu-id="36749-113">nvarchar (384), not null</span></span></p></td>
<td><p><span data-ttu-id="36749-p101">구성원의 고유 이름입니다. 구성원은 tblPrincipal 테이블의 사용자일 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="36749-p101">Distinguished name of a member. A member does not have to be a principal (in tblPrincipal table).</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="36749-116">키</span><span class="sxs-lookup"><span data-stu-id="36749-116">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="36749-117">열</span><span class="sxs-lookup"><span data-stu-id="36749-117">Column</span></span></th>
<th><span data-ttu-id="36749-118">설명</span><span class="sxs-lookup"><span data-stu-id="36749-118">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="36749-119">&lt;Tblprincipal.prinid, memberADPath&gt;</span><span class="sxs-lookup"><span data-stu-id="36749-119">&lt;prinID, memberADPath&gt;</span></span></p></td>
<td><p><span data-ttu-id="36749-120">기본 키입니다.</span><span class="sxs-lookup"><span data-stu-id="36749-120">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="36749-121">Tblprincipal.prinid</span><span class="sxs-lookup"><span data-stu-id="36749-121">prinID</span></span></p></td>
<td><p><span data-ttu-id="36749-122">tblPrincipal.prinID에서 조회 기능이 있는 외래 키입니다.</span><span class="sxs-lookup"><span data-stu-id="36749-122">Foreign key with lookup in tblPrincipal.prinID.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

