---
title: 'Lync Server 2013: 미디어 보기'
description: 'Lync Server 2013: 미디어 보기입니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Media view
ms:assetid: 1a7b2e59-082e-4188-98ae-48ae9bd3494a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687981(v=OCS.15)
ms:contentKeyID: 49733570
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 74643986b12a30b1055a46a37febf90eeb70c514
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558014"
---
# <a name="media-view-in-lync-server-2013"></a><span data-ttu-id="b8c0d-103">Lync Server 2013의 미디어 보기</span><span class="sxs-lookup"><span data-stu-id="b8c0d-103">Media view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b8c0d-104">_**마지막으로 수정 된 항목:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="b8c0d-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="b8c0d-105">Media 보기에는 피어 투 피어 세션에 사용되는 단일 미디어 유형에 대한 정보가 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8c0d-105">The Media view stores information about one media type used in a peer-to-peer session.</span></span> <span data-ttu-id="b8c0d-106">둘 이상의 미디어 유형이 사용된 경우 하나의 세션이 테이블에 여러 레코드로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8c0d-106">One session would be represented by multiple records in the table, if more than one media type is used.</span></span> <span data-ttu-id="b8c0d-107">이 보기는 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b8c0d-107">This view was introduced in Microsoft Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b8c0d-p102">Media 보기를 사용하여 세션의 미디어 기간을 계산해서는 안 됩니다. 이 보기에는 세션에 포함된 미디어 교환의 신호 세부 정보가 포함됩니다. 미디어 교환은 INVITE 요청에 의해 수행되며 StartTime은 INVITE가 전송된 시간을 나타냅니다. 미디어는 세션이 수락된 후에만 시작되므로 초대 시간이 반드시 미디어 시작 시간인 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="b8c0d-p102">The Media view should not be used to calculate the media duration for a session. This view contains the signaling details of media exchange in a session. Media exchange is done by the INVITE request, and StartTime indicates the time that the INVITE was sent out. The invite time does not necessarily mean the media start time, because media starts only after the session is accepted.</span></span>



</div>

<span data-ttu-id="b8c0d-111">미디어 보기에는 아래 나열 된 것 외에도 [Lync Server 2013의 Sessiondetails view](lync-server-2013-sessiondetails-view.md) 의 모든 열이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8c0d-111">The Media view contains all of the columns in the [SessionDetails view in Lync Server 2013](lync-server-2013-sessiondetails-view.md) in addition the ones listed below.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b8c0d-112">열</span><span class="sxs-lookup"><span data-stu-id="b8c0d-112">Column</span></span></th>
<th><span data-ttu-id="b8c0d-113">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="b8c0d-113">Data Type</span></span></th>
<th><span data-ttu-id="b8c0d-114">세부 정보</span><span class="sxs-lookup"><span data-stu-id="b8c0d-114">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b8c0d-115"><strong>미디어</strong></span><span class="sxs-lookup"><span data-stu-id="b8c0d-115"><strong>Media</strong></span></span></p></td>
<td><p><span data-ttu-id="b8c0d-116">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b8c0d-116">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b8c0d-117">미디어 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="b8c0d-117">Media type.</span></span> <span data-ttu-id="b8c0d-118">자세한 내용은 <a href="lync-server-2013-medialist-table.md">Lync Server 2013에서 Medialist 테이블</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="b8c0d-118">See the <a href="lync-server-2013-medialist-table.md">MediaList table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b8c0d-119"><strong>MediaStartTime</strong></span><span class="sxs-lookup"><span data-stu-id="b8c0d-119"><strong>MediaStartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="b8c0d-120">datetime</span><span class="sxs-lookup"><span data-stu-id="b8c0d-120">datetime</span></span></p></td>
<td><p><span data-ttu-id="b8c0d-121">미디어 요청을 보낸 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="b8c0d-121">Time that a media request was sent out.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b8c0d-122"><strong>MediaEndTime</strong></span><span class="sxs-lookup"><span data-stu-id="b8c0d-122"><strong>MediaEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="b8c0d-123">datetime</span><span class="sxs-lookup"><span data-stu-id="b8c0d-123">datetime</span></span></p></td>
<td><p><span data-ttu-id="b8c0d-124">세션 종료 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="b8c0d-124">End time of the session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

