---
title: 'Lync Server 2013: tblPrincipalMemberDifference'
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
ms.openlocfilehash: baaf336013ec09b17b8e688889fdf27aa29ef644
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764144"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblprincipalmemberdifference-in-lync-server-2013"></a><span data-ttu-id="14d0d-102">Lync Server 2013의 tblPrincipalMemberDifference</span><span class="sxs-lookup"><span data-stu-id="14d0d-102">tblPrincipalMemberDifference in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="14d0d-103">_**마지막으로 수정한 주제:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="14d0d-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="14d0d-104">tblPrincipalMemberDifference에는 이후 Active Directory 도메인 서비스 동기화 단계에서 아직 처리 하지 않은 그룹 구성원 변경 (구성원을 추가 및 제거 함)이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="14d0d-104">tblPrincipalMemberDifference contains group membership changes (both added and removed members) that have not yet been processed by the later Active Directory Domain Services Sync steps.</span></span>

### <a name="columns"></a><span data-ttu-id="14d0d-105">열</span><span class="sxs-lookup"><span data-stu-id="14d0d-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="14d0d-106">열</span><span class="sxs-lookup"><span data-stu-id="14d0d-106">Column</span></span></th>
<th><span data-ttu-id="14d0d-107">유형</span><span class="sxs-lookup"><span data-stu-id="14d0d-107">Type</span></span></th>
<th><span data-ttu-id="14d0d-108">설명</span><span class="sxs-lookup"><span data-stu-id="14d0d-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="14d0d-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="14d0d-109">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="14d0d-110">GUID (null 아님)</span><span class="sxs-lookup"><span data-stu-id="14d0d-110">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="14d0d-111">변경 된 그룹의 Principal GUID입니다.</span><span class="sxs-lookup"><span data-stu-id="14d0d-111">Principal GUID of the group that changed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14d0d-112">memberADPath</span><span class="sxs-lookup"><span data-stu-id="14d0d-112">memberADPath</span></span></p></td>
<td><p><span data-ttu-id="14d0d-113">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="14d0d-113">nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="14d0d-114">구성원의 고유 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="14d0d-114">Distinguished name of the member.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="14d0d-115">memberRemoved 됨</span><span class="sxs-lookup"><span data-stu-id="14d0d-115">memberRemoved</span></span></p></td>
<td><p><span data-ttu-id="14d0d-116">bit, null이 아님</span><span class="sxs-lookup"><span data-stu-id="14d0d-116">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="14d0d-117">구성원이 추가 된 경우 False입니다.</span><span class="sxs-lookup"><span data-stu-id="14d0d-117">False if the member was added.</span></span> <span data-ttu-id="14d0d-118">구성원이 제거 된 경우 True입니다.</span><span class="sxs-lookup"><span data-stu-id="14d0d-118">True if the member was removed.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="14d0d-119">키</span><span class="sxs-lookup"><span data-stu-id="14d0d-119">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="14d0d-120">열</span><span class="sxs-lookup"><span data-stu-id="14d0d-120">Column</span></span></th>
<th><span data-ttu-id="14d0d-121">설명</span><span class="sxs-lookup"><span data-stu-id="14d0d-121">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="14d0d-122">&lt;prinGuid, memberADPath&gt;</span><span class="sxs-lookup"><span data-stu-id="14d0d-122">&lt;prinGuid, memberADPath&gt;</span></span></p></td>
<td><p><span data-ttu-id="14d0d-123">기본 키입니다.</span><span class="sxs-lookup"><span data-stu-id="14d0d-123">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

