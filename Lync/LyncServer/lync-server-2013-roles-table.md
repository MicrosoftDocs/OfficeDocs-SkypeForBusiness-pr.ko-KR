---
title: 'Lync Server 2013: Roles 테이블'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Roles table
ms:assetid: e8eb8a10-26b5-488b-bc8c-f9ef93f98bdb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399043(v=OCS.15)
ms:contentKeyID: 48185893
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 251b266d18be3b472f4a22a635d134f6fe3dc77e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732968"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="roles-table-in-lync-server-2013"></a><span data-ttu-id="08bfd-102">Lync Server 2013의 Roles 테이블</span><span class="sxs-lookup"><span data-stu-id="08bfd-102">Roles table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="08bfd-103">_**마지막으로 수정한 주제:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="08bfd-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="08bfd-104">역할 테이블은 가능한 컨퍼런스 역할 목록 (예: 참석자 및 발표자)을 저장 하는 정적 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="08bfd-104">The Roles table is a static table that stores the list of possible conference roles, such as attendee and presenter.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="08bfd-105">열</span><span class="sxs-lookup"><span data-stu-id="08bfd-105">Column</span></span></th>
<th><span data-ttu-id="08bfd-106">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="08bfd-106">Data Type</span></span></th>
<th><span data-ttu-id="08bfd-107">키/인덱스</span><span class="sxs-lookup"><span data-stu-id="08bfd-107">Key/Index</span></span></th>
<th><span data-ttu-id="08bfd-108">세부적인</span><span class="sxs-lookup"><span data-stu-id="08bfd-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="08bfd-109"><strong>RoleId</strong></span><span class="sxs-lookup"><span data-stu-id="08bfd-109"><strong>RoleId</strong></span></span></p></td>
<td><p><span data-ttu-id="08bfd-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="08bfd-110">tinyint</span></span></p></td>
<td><p><span data-ttu-id="08bfd-111">주요한</span><span class="sxs-lookup"><span data-stu-id="08bfd-111">Primary</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="08bfd-112"><strong>역할인</strong></span><span class="sxs-lookup"><span data-stu-id="08bfd-112"><strong>Role</strong></span></span></p></td>
<td><p><span data-ttu-id="08bfd-113">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="08bfd-113">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="08bfd-114">허용 되는 값:</span><span class="sxs-lookup"><span data-stu-id="08bfd-114">Allowed values:</span></span></p>
<ul>
<li><p><span data-ttu-id="08bfd-115">0-알 수 없음</span><span class="sxs-lookup"><span data-stu-id="08bfd-115">0 - Unknown</span></span></p></li>
<li><p><span data-ttu-id="08bfd-116">1-발표자</span><span class="sxs-lookup"><span data-stu-id="08bfd-116">1 - Presenter</span></span></p></li>
<li><p><span data-ttu-id="08bfd-117">2-참석자</span><span class="sxs-lookup"><span data-stu-id="08bfd-117">2 - Attendee</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

