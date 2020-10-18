---
title: 'Lync Server 2013: tblAdminLock'
description: 'Lync Server 2013: tblAdminLock'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblAdminLock
ms:assetid: 785a43c0-6892-474c-821c-fa9cdbeb99d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558665(v=OCS.15)
ms:contentKeyID: 48184560
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c3313826b2c0d578c515fb25f83e713b8978ae63
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573714"
---
# <a name="tbladminlock-in-lync-server-2013"></a><span data-ttu-id="260fc-103">Lync Server 2013의 tblAdminLock</span><span class="sxs-lookup"><span data-stu-id="260fc-103">tblAdminLock in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="260fc-104">_**마지막으로 수정 된 항목:** 2012-06-25_</span><span class="sxs-lookup"><span data-stu-id="260fc-104">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="260fc-105">tblAdminLock은 일부 관리자 명령을 실행하는 데 필요한 관리자 잠금을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="260fc-105">tblAdminLock contains the administrator lock that is needed to run some administrator commands.</span></span>

### <a name="columns"></a><span data-ttu-id="260fc-106">단</span><span class="sxs-lookup"><span data-stu-id="260fc-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="260fc-107">열</span><span class="sxs-lookup"><span data-stu-id="260fc-107">Column</span></span></th>
<th><span data-ttu-id="260fc-108">유형</span><span class="sxs-lookup"><span data-stu-id="260fc-108">Type</span></span></th>
<th><span data-ttu-id="260fc-109">설명</span><span class="sxs-lookup"><span data-stu-id="260fc-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="260fc-110">lockExpiresTime</span><span class="sxs-lookup"><span data-stu-id="260fc-110">lockExpiresTime</span></span></p></td>
<td><p><span data-ttu-id="260fc-111">datetime, null이 아님</span><span class="sxs-lookup"><span data-stu-id="260fc-111">datetime, not null</span></span></p></td>
<td><p><span data-ttu-id="260fc-p101">잠금 만료 날짜 및 시간입니다. 소유자는 이 값을 주기적으로 연장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="260fc-p101">Lock expiration date and time. The owner can extend this value periodically.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="260fc-114">lockServerID</span><span class="sxs-lookup"><span data-stu-id="260fc-114">lockServerID</span></span></p></td>
<td><p><span data-ttu-id="260fc-115">int, null이 아님</span><span class="sxs-lookup"><span data-stu-id="260fc-115">int, not null</span></span></p></td>
<td><p><span data-ttu-id="260fc-116">잠금을 소유하는 서버의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="260fc-116">ID of the server that owns the lock.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="260fc-117">lockActorID</span><span class="sxs-lookup"><span data-stu-id="260fc-117">lockActorID</span></span></p></td>
<td><p><span data-ttu-id="260fc-118">int, null이 아님</span><span class="sxs-lookup"><span data-stu-id="260fc-118">int, not null</span></span></p></td>
<td><p><span data-ttu-id="260fc-119">잠금을 소유하는 사용자의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="260fc-119">ID of the principal that owns the lock.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

