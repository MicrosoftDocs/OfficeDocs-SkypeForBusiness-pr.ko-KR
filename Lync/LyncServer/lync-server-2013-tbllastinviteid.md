---
title: 'Lync Server 2013: tblLastInviteId'
description: 'Lync Server 2013: tblLastInviteId.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblLastInviteId
ms:assetid: 222b3508-5963-4ddc-b4f3-e8412767e61b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558625(v=OCS.15)
ms:contentKeyID: 48183608
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e5a13cfc7edc29ea20c95f7f4d587b0cfb84eb73
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547544"
---
# <a name="tbllastinviteid-in-lync-server-2013"></a><span data-ttu-id="b4fee-103">Lync Server 2013의 tblLastInviteId</span><span class="sxs-lookup"><span data-stu-id="b4fee-103">tblLastInviteId in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b4fee-104">_**마지막으로 수정 된 항목:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="b4fee-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="b4fee-105">tblLastInviteId에는 각 사용자에 대해 생성(및 tblPrincipalInvites 테이블에서 사용)된 마지막 초대 ID가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="b4fee-105">tblLastInviteId contains the last invite ID that was generated (and used in the tblPrincipalInvites table) for each user.</span></span>

### <a name="columns"></a><span data-ttu-id="b4fee-106">단</span><span class="sxs-lookup"><span data-stu-id="b4fee-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b4fee-107">열</span><span class="sxs-lookup"><span data-stu-id="b4fee-107">Column</span></span></th>
<th><span data-ttu-id="b4fee-108">유형</span><span class="sxs-lookup"><span data-stu-id="b4fee-108">Type</span></span></th>
<th><span data-ttu-id="b4fee-109">설명</span><span class="sxs-lookup"><span data-stu-id="b4fee-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b4fee-110">Tblprincipal.prinid</span><span class="sxs-lookup"><span data-stu-id="b4fee-110">prinID</span></span></p></td>
<td><p><span data-ttu-id="b4fee-111">int, null이 아님</span><span class="sxs-lookup"><span data-stu-id="b4fee-111">int, not null</span></span></p></td>
<td><p><span data-ttu-id="b4fee-112">사용자 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="b4fee-112">Principal ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b4fee-113">lastInviteID</span><span class="sxs-lookup"><span data-stu-id="b4fee-113">lastInviteID</span></span></p></td>
<td><p><span data-ttu-id="b4fee-114">int, null이 아님</span><span class="sxs-lookup"><span data-stu-id="b4fee-114">int, not null</span></span></p></td>
<td><p><span data-ttu-id="b4fee-115">마지막으로 초대 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="b4fee-115">Last used invite ID.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="b4fee-116">키</span><span class="sxs-lookup"><span data-stu-id="b4fee-116">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b4fee-117">열</span><span class="sxs-lookup"><span data-stu-id="b4fee-117">Column</span></span></th>
<th><span data-ttu-id="b4fee-118">설명</span><span class="sxs-lookup"><span data-stu-id="b4fee-118">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b4fee-119">Tblprincipal.prinid</span><span class="sxs-lookup"><span data-stu-id="b4fee-119">prinID</span></span></p></td>
<td><p><span data-ttu-id="b4fee-120">기본 키입니다.</span><span class="sxs-lookup"><span data-stu-id="b4fee-120">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b4fee-121">Tblprincipal.prinid</span><span class="sxs-lookup"><span data-stu-id="b4fee-121">prinID</span></span></p></td>
<td><p><span data-ttu-id="b4fee-122">tblPrincipal.prinID 테이블에서 조회 기능이 있는 외래 키입니다.</span><span class="sxs-lookup"><span data-stu-id="b4fee-122">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="b4fee-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b4fee-123">See Also</span></span>


[<span data-ttu-id="b4fee-124">Lync Server 2013의 tblPrincipalInvites</span><span class="sxs-lookup"><span data-stu-id="b4fee-124">tblPrincipalInvites in Lync Server 2013</span></span>](lync-server-2013-tblprincipalinvites.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

