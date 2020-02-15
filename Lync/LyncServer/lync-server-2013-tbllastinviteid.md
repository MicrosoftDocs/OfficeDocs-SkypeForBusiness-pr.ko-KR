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
ms.openlocfilehash: b58f43c696a6218d0dd9b670615cc0f73b0b7ae3
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42024729"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tbllastinviteid-in-lync-server-2013"></a><span data-ttu-id="2414f-102">Lync Server 2013의 tblLastInviteId</span><span class="sxs-lookup"><span data-stu-id="2414f-102">tblLastInviteId in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2414f-103">_**마지막으로 수정 된 항목:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="2414f-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="2414f-104">tblLastInviteId에는 각 사용자에 대해 생성(및 tblPrincipalInvites 테이블에서 사용)된 마지막 초대 ID가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="2414f-104">tblLastInviteId contains the last invite ID that was generated (and used in the tblPrincipalInvites table) for each user.</span></span>

### <a name="columns"></a><span data-ttu-id="2414f-105">단</span><span class="sxs-lookup"><span data-stu-id="2414f-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2414f-106">열</span><span class="sxs-lookup"><span data-stu-id="2414f-106">Column</span></span></th>
<th><span data-ttu-id="2414f-107">형식</span><span class="sxs-lookup"><span data-stu-id="2414f-107">Type</span></span></th>
<th><span data-ttu-id="2414f-108">설명</span><span class="sxs-lookup"><span data-stu-id="2414f-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2414f-109">Tblprincipal.prinid</span><span class="sxs-lookup"><span data-stu-id="2414f-109">prinID</span></span></p></td>
<td><p><span data-ttu-id="2414f-110">int, null이 아님</span><span class="sxs-lookup"><span data-stu-id="2414f-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="2414f-111">사용자 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="2414f-111">Principal ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2414f-112">lastInviteID</span><span class="sxs-lookup"><span data-stu-id="2414f-112">lastInviteID</span></span></p></td>
<td><p><span data-ttu-id="2414f-113">int, null이 아님</span><span class="sxs-lookup"><span data-stu-id="2414f-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="2414f-114">마지막으로 초대 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="2414f-114">Last used invite ID.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="2414f-115">키</span><span class="sxs-lookup"><span data-stu-id="2414f-115">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2414f-116">열</span><span class="sxs-lookup"><span data-stu-id="2414f-116">Column</span></span></th>
<th><span data-ttu-id="2414f-117">설명</span><span class="sxs-lookup"><span data-stu-id="2414f-117">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2414f-118">Tblprincipal.prinid</span><span class="sxs-lookup"><span data-stu-id="2414f-118">prinID</span></span></p></td>
<td><p><span data-ttu-id="2414f-119">기본 키입니다.</span><span class="sxs-lookup"><span data-stu-id="2414f-119">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2414f-120">Tblprincipal.prinid</span><span class="sxs-lookup"><span data-stu-id="2414f-120">prinID</span></span></p></td>
<td><p><span data-ttu-id="2414f-121">tblPrincipal.prinID 테이블에서 조회 기능이 있는 외래 키입니다.</span><span class="sxs-lookup"><span data-stu-id="2414f-121">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="2414f-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2414f-122">See Also</span></span>


[<span data-ttu-id="2414f-123">Lync Server 2013의 tblPrincipalInvites</span><span class="sxs-lookup"><span data-stu-id="2414f-123">tblPrincipalInvites in Lync Server 2013</span></span>](lync-server-2013-tblprincipalinvites.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

