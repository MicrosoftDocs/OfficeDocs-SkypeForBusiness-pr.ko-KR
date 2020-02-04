---
title: 'Lync Server 2013: 미디어 보기'
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
ms.openlocfilehash: 6ad833bc84d488221d46822686077cfde2cda0ff
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765096"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="media-view-in-lync-server-2013"></a><span data-ttu-id="7cfe8-102">Lync Server 2013의 미디어 보기</span><span class="sxs-lookup"><span data-stu-id="7cfe8-102">Media view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7cfe8-103">_**마지막으로 수정한 주제:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="7cfe8-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="7cfe8-104">미디어 보기는 피어 투 피어 세션에 사용 되는 미디어 형식에 대 한 정보를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="7cfe8-104">The Media view stores information about one media type used in a peer-to-peer session.</span></span> <span data-ttu-id="7cfe8-105">하나 이상의 미디어 유형이 사용 되는 경우 한 세션은 테이블의 여러 레코드로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7cfe8-105">One session would be represented by multiple records in the table, if more than one media type is used.</span></span> <span data-ttu-id="7cfe8-106">이 보기는 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="7cfe8-106">This view was introduced in Microsoft Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7cfe8-107">미디어 보기는 세션의 미디어 기간을 계산 하는 데 사용해 서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7cfe8-107">The Media view should not be used to calculate the media duration for a session.</span></span> <span data-ttu-id="7cfe8-108">이 보기에는 세션의 미디어 교환에 대 한 신호 세부 정보가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7cfe8-108">This view contains the signaling details of media exchange in a session.</span></span> <span data-ttu-id="7cfe8-109">미디어 교환은 초대 요청에 의해 수행 되며 StartTime은 초대를 보낸 시간을 나타냅니다. 세션이 허용 된 후에만 미디어가 시작 되므로 초대 시간이 반드시 미디어 시작 시간을 의미 하는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="7cfe8-109">Media exchange is done by the INVITE request, and StartTime indicates the time that the INVITE was sent out. The invite time does not necessarily mean the media start time, because media starts only after the session is accepted.</span></span>



</div>

<span data-ttu-id="7cfe8-110">미디어 보기에는 아래 나열 된 것 외에도 [Lync Server 2013의 Sessiondetails 보기](lync-server-2013-sessiondetails-view.md) 에 모든 열이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7cfe8-110">The Media view contains all of the columns in the [SessionDetails view in Lync Server 2013](lync-server-2013-sessiondetails-view.md) in addition the ones listed below.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7cfe8-111">열</span><span class="sxs-lookup"><span data-stu-id="7cfe8-111">Column</span></span></th>
<th><span data-ttu-id="7cfe8-112">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="7cfe8-112">Data Type</span></span></th>
<th><span data-ttu-id="7cfe8-113">세부적인</span><span class="sxs-lookup"><span data-stu-id="7cfe8-113">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7cfe8-114"><strong>미디어</strong></span><span class="sxs-lookup"><span data-stu-id="7cfe8-114"><strong>Media</strong></span></span></p></td>
<td><p><span data-ttu-id="7cfe8-115">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="7cfe8-115">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="7cfe8-116">미디어 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="7cfe8-116">Media type.</span></span> <span data-ttu-id="7cfe8-117">자세한 내용은 <a href="lync-server-2013-medialist-table.md">Lync Server 2013의 Medialist 테이블</a> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7cfe8-117">See the <a href="lync-server-2013-medialist-table.md">MediaList table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7cfe8-118"><strong>MediaStartTime</strong></span><span class="sxs-lookup"><span data-stu-id="7cfe8-118"><strong>MediaStartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="7cfe8-119">dmtf</span><span class="sxs-lookup"><span data-stu-id="7cfe8-119">datetime</span></span></p></td>
<td><p><span data-ttu-id="7cfe8-120">미디어 요청이 전송 된 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="7cfe8-120">Time that a media request was sent out.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7cfe8-121"><strong>MediaEndTime</strong></span><span class="sxs-lookup"><span data-stu-id="7cfe8-121"><strong>MediaEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="7cfe8-122">dmtf</span><span class="sxs-lookup"><span data-stu-id="7cfe8-122">datetime</span></span></p></td>
<td><p><span data-ttu-id="7cfe8-123">세션 종료 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="7cfe8-123">End time of the session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

