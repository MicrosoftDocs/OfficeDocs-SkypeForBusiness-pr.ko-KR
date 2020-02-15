---
title: 'Lync Server 2013: ConferenceUris 보기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ConferenceUris view
ms:assetid: 9a3cdcea-426e-4b6b-9876-ba746a8de706
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688148(v=OCS.15)
ms:contentKeyID: 49733750
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ff28e9fcbf6ddc8b69a0b7962195854fda1151f2
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42040847"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferenceuris-view-in-lync-server-2013"></a><span data-ttu-id="b3f8b-102">Lync Server 2013의 ConferenceUris 보기</span><span class="sxs-lookup"><span data-stu-id="b3f8b-102">ConferenceUris view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b3f8b-103">_**마지막으로 수정 된 항목:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="b3f8b-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="b3f8b-104">ConfernceUris 보기에는 회의 세션에 참여한 URI에 대한 정보가 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="b3f8b-104">The ConfernceUris view stores information about the URIs that have participated in conference sessions.</span></span> <span data-ttu-id="b3f8b-105">이 보기는 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b3f8b-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b3f8b-106">열</span><span class="sxs-lookup"><span data-stu-id="b3f8b-106">Column</span></span></th>
<th><span data-ttu-id="b3f8b-107">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="b3f8b-107">Data Type</span></span></th>
<th><span data-ttu-id="b3f8b-108">세부 정보</span><span class="sxs-lookup"><span data-stu-id="b3f8b-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b3f8b-109">ConferenceUriId</span><span class="sxs-lookup"><span data-stu-id="b3f8b-109">ConferenceUriId</span></span></p></td>
<td><p><span data-ttu-id="b3f8b-110">int</span><span class="sxs-lookup"><span data-stu-id="b3f8b-110">int</span></span></p></td>
<td><p><span data-ttu-id="b3f8b-111">회의 URI를 식별하는 고유 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="b3f8b-111">Unique number identifying the conference URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b3f8b-112">ConferenceUri</span><span class="sxs-lookup"><span data-stu-id="b3f8b-112">ConferenceUri</span></span></p></td>
<td><p><span data-ttu-id="b3f8b-113">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="b3f8b-113">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="b3f8b-114">회의의 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="b3f8b-114">URI of the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b3f8b-115">ConferenceUriType</span><span class="sxs-lookup"><span data-stu-id="b3f8b-115">ConferenceUriType</span></span></p></td>
<td><p><span data-ttu-id="b3f8b-116">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b3f8b-116">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b3f8b-117">회의 URI의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="b3f8b-117">Type of conference URI.</span></span> <span data-ttu-id="b3f8b-118">자세한 내용은 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013의 UriTypes 테이블</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="b3f8b-118">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

