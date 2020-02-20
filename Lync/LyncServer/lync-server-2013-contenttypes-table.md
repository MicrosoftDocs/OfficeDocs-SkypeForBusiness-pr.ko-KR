---
title: 'Lync Server 2013: ContentTypes 테이블'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ContentTypes table
ms:assetid: e3e38035-457c-4173-bdb9-d53a7420eba2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399007(v=OCS.15)
ms:contentKeyID: 48185723
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c068d0e6d72980175aa1123ece05c40bbe72239b
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154050"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="contenttypes-table-in-lync-server-2013"></a><span data-ttu-id="6a146-102">Lync Server 2013의 ContentTypes 테이블</span><span class="sxs-lookup"><span data-stu-id="6a146-102">ContentTypes table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6a146-103">_**마지막으로 수정 된 항목:** 2010-11-07_</span><span class="sxs-lookup"><span data-stu-id="6a146-103">_**Topic Last Modified:** 2010-11-07_</span></span>

<span data-ttu-id="6a146-p101">ContentTypes 테이블은 피어-투-피어 세션 및 회의 세션에 사용되는 콘텐츠 유형 목록을 저장하는 지원 테이블입니다. 테이블의 각 레코드는 하나의 콘텐츠 유형을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="6a146-p101">The ContentTypes table is a supporting table that stores a list of the content types used in both peer-to-peer sessions and conference sessions. Each record in the table represents one content type.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6a146-106">열</span><span class="sxs-lookup"><span data-stu-id="6a146-106">Column</span></span></th>
<th><span data-ttu-id="6a146-107">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="6a146-107">Data Type</span></span></th>
<th><span data-ttu-id="6a146-108">키/인덱스</span><span class="sxs-lookup"><span data-stu-id="6a146-108">Key/Index</span></span></th>
<th><span data-ttu-id="6a146-109">세부 정보</span><span class="sxs-lookup"><span data-stu-id="6a146-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6a146-110"><strong>ContentTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="6a146-110"><strong>ContentTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="6a146-111">int</span><span class="sxs-lookup"><span data-stu-id="6a146-111">int</span></span></p></td>
<td><p><span data-ttu-id="6a146-112">Primary</span><span class="sxs-lookup"><span data-stu-id="6a146-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="6a146-113">콘텐츠 유형을 식별하는 고유 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="6a146-113">Unique number identifying the content type.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6a146-114"><strong>ContentType</strong></span><span class="sxs-lookup"><span data-stu-id="6a146-114"><strong>ContentType</strong></span></span></p></td>
<td><p><span data-ttu-id="6a146-115">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="6a146-115">nvarchar(256)</span></span></p></td>
<td> </td>
<td><p><span data-ttu-id="6a146-116">콘텐츠 유형 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="6a146-116">Content type name.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

