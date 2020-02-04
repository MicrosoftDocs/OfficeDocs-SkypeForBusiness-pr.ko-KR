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
ms.openlocfilehash: 4cf7ba9c9fb267e8c65c3ba672850c04eb95a459
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740568"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="contenttypes-table-in-lync-server-2013"></a><span data-ttu-id="1b336-102">Lync Server 2013의 ContentTypes 테이블</span><span class="sxs-lookup"><span data-stu-id="1b336-102">ContentTypes table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1b336-103">_**마지막으로 수정한 주제:** 2010-11-07_</span><span class="sxs-lookup"><span data-stu-id="1b336-103">_**Topic Last Modified:** 2010-11-07_</span></span>

<span data-ttu-id="1b336-104">ContentTypes 테이블은 피어 투 피어 세션과 회의 세션에 사용 되는 콘텐츠 형식의 목록을 저장 하는 지원 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="1b336-104">The ContentTypes table is a supporting table that stores a list of the content types used in both peer-to-peer sessions and conference sessions.</span></span> <span data-ttu-id="1b336-105">테이블의 각 레코드는 한 가지 콘텐츠 형식을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="1b336-105">Each record in the table represents one content type.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1b336-106">열</span><span class="sxs-lookup"><span data-stu-id="1b336-106">Column</span></span></th>
<th><span data-ttu-id="1b336-107">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="1b336-107">Data Type</span></span></th>
<th><span data-ttu-id="1b336-108">키/인덱스</span><span class="sxs-lookup"><span data-stu-id="1b336-108">Key/Index</span></span></th>
<th><span data-ttu-id="1b336-109">세부적인</span><span class="sxs-lookup"><span data-stu-id="1b336-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1b336-110"><strong>ContentTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="1b336-110"><strong>ContentTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="1b336-111">int</span><span class="sxs-lookup"><span data-stu-id="1b336-111">int</span></span></p></td>
<td><p><span data-ttu-id="1b336-112">주요한</span><span class="sxs-lookup"><span data-stu-id="1b336-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="1b336-113">콘텐츠 형식을 식별 하는 고유 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="1b336-113">Unique number identifying the content type.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b336-114"><strong>ContentType</strong></span><span class="sxs-lookup"><span data-stu-id="1b336-114"><strong>ContentType</strong></span></span></p></td>
<td><p><span data-ttu-id="1b336-115">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="1b336-115">nvarchar(256)</span></span></p></td>
<td> </td>
<td><p><span data-ttu-id="1b336-116">콘텐츠 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="1b336-116">Content type name.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

