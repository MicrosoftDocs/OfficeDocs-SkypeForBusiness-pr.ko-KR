---
title: 'Lync Server 2013: tblLastInviteId'
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
ms.openlocfilehash: 40b77e2ccf7e689160e6072bdcfa7896bb3439d9
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142074"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tbllastinviteid-in-lync-server-2013"></a><span data-ttu-id="711d2-102">Lync Server 2013의 tblLastInviteId</span><span class="sxs-lookup"><span data-stu-id="711d2-102">tblLastInviteId in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="711d2-103">_**마지막으로 수정 된 항목:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="711d2-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="711d2-104">tblLastInviteId에는 각 사용자에 대해 생성(및 tblPrincipalInvites 테이블에서 사용)된 마지막 초대 ID가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="711d2-104">tblLastInviteId contains the last invite ID that was generated (and used in the tblPrincipalInvites table) for each user.</span></span>

### <a name="columns"></a><span data-ttu-id="711d2-105">단</span><span class="sxs-lookup"><span data-stu-id="711d2-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="711d2-106">열</span><span class="sxs-lookup"><span data-stu-id="711d2-106">Column</span></span></th>
<th><span data-ttu-id="711d2-107">형식</span><span class="sxs-lookup"><span data-stu-id="711d2-107">Type</span></span></th>
<th><span data-ttu-id="711d2-108">설명</span><span class="sxs-lookup"><span data-stu-id="711d2-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="711d2-109">Tblprincipal.prinid</span><span class="sxs-lookup"><span data-stu-id="711d2-109">prinID</span></span></p></td>
<td><p><span data-ttu-id="711d2-110">int, null이 아님</span><span class="sxs-lookup"><span data-stu-id="711d2-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="711d2-111">사용자 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="711d2-111">Principal ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="711d2-112">lastInviteID</span><span class="sxs-lookup"><span data-stu-id="711d2-112">lastInviteID</span></span></p></td>
<td><p><span data-ttu-id="711d2-113">int, null이 아님</span><span class="sxs-lookup"><span data-stu-id="711d2-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="711d2-114">마지막으로 초대 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="711d2-114">Last used invite ID.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="711d2-115">키</span><span class="sxs-lookup"><span data-stu-id="711d2-115">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="711d2-116">열</span><span class="sxs-lookup"><span data-stu-id="711d2-116">Column</span></span></th>
<th><span data-ttu-id="711d2-117">설명</span><span class="sxs-lookup"><span data-stu-id="711d2-117">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="711d2-118">Tblprincipal.prinid</span><span class="sxs-lookup"><span data-stu-id="711d2-118">prinID</span></span></p></td>
<td><p><span data-ttu-id="711d2-119">기본 키입니다.</span><span class="sxs-lookup"><span data-stu-id="711d2-119">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="711d2-120">Tblprincipal.prinid</span><span class="sxs-lookup"><span data-stu-id="711d2-120">prinID</span></span></p></td>
<td><p><span data-ttu-id="711d2-121">tblPrincipal.prinID 테이블에서 조회 기능이 있는 외래 키입니다.</span><span class="sxs-lookup"><span data-stu-id="711d2-121">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="711d2-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="711d2-122">See Also</span></span>


[<span data-ttu-id="711d2-123">Lync Server 2013의 tblPrincipalInvites</span><span class="sxs-lookup"><span data-stu-id="711d2-123">tblPrincipalInvites in Lync Server 2013</span></span>](lync-server-2013-tblprincipalinvites.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

