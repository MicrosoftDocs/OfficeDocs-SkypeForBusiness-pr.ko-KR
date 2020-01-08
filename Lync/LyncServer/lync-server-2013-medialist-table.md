---
title: 'Lync Server 2013: MediaList 테이블'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: MediaList table
ms:assetid: 1f440590-c1bc-483e-b7bc-6cc763847768
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398279(v=OCS.15)
ms:contentKeyID: 48183579
ms.date: 07/12/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f4fa53ff1ce4ce419a4e7a29124593c7b01006a3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978711"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="medialist-table-in-lync-server-2013"></a><span data-ttu-id="0424f-102">Lync Server 2013의 MediaList 테이블</span><span class="sxs-lookup"><span data-stu-id="0424f-102">MediaList table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0424f-103">_**마지막으로 수정한 주제:** 2016-07-12_</span><span class="sxs-lookup"><span data-stu-id="0424f-103">_**Topic Last Modified:** 2016-07-12_</span></span>

<span data-ttu-id="0424f-104">MediaList 테이블은 다양 한 미디어 유형의 목록을 저장 하는 정적 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="0424f-104">The MediaList table is a static table that stores the list of various media types.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0424f-105">열</span><span class="sxs-lookup"><span data-stu-id="0424f-105">Column</span></span></th>
<th><span data-ttu-id="0424f-106">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="0424f-106">Data Type</span></span></th>
<th><span data-ttu-id="0424f-107">키/인덱스</span><span class="sxs-lookup"><span data-stu-id="0424f-107">Key/Index</span></span></th>
<th><span data-ttu-id="0424f-108">세부적인</span><span class="sxs-lookup"><span data-stu-id="0424f-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0424f-109"><strong>MediaId</strong></span><span class="sxs-lookup"><span data-stu-id="0424f-109"><strong>MediaId</strong></span></span></p></td>
<td><p><span data-ttu-id="0424f-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="0424f-110">tinyint</span></span></p></td>
<td><p><span data-ttu-id="0424f-111">주요한</span><span class="sxs-lookup"><span data-stu-id="0424f-111">Primary</span></span></p></td>
<td><p><span data-ttu-id="0424f-112">값: 1-7</span><span class="sxs-lookup"><span data-stu-id="0424f-112">Values: 1-7</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0424f-113"><strong>미디어</strong></span><span class="sxs-lookup"><span data-stu-id="0424f-113"><strong>Media</strong></span></span></p></td>
<td><p><span data-ttu-id="0424f-114">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="0424f-114">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0424f-115">MediaID 및 Media 값의 정적 매핑:</span><span class="sxs-lookup"><span data-stu-id="0424f-115">Static mapping of MediaID and Media values:</span></span></p>
<ul>
<li><p><span data-ttu-id="0424f-116">1 – 메신저 대화</span><span class="sxs-lookup"><span data-stu-id="0424f-116">1 – IM</span></span></p></li>
<li><p><span data-ttu-id="0424f-117">2-파일 전송</span><span class="sxs-lookup"><span data-stu-id="0424f-117">2 – File Transfer</span></span></p></li>
<li><p><span data-ttu-id="0424f-118">3-원격 지원</span><span class="sxs-lookup"><span data-stu-id="0424f-118">3 – Remote Assistance</span></span></p></li>
<li><p><span data-ttu-id="0424f-119">4-응용 프로그램 공유</span><span class="sxs-lookup"><span data-stu-id="0424f-119">4 – Application Sharing</span></span></p></li>
<li><p><span data-ttu-id="0424f-120">5-오디오</span><span class="sxs-lookup"><span data-stu-id="0424f-120">5 – Audio</span></span></p></li>
<li><p><span data-ttu-id="0424f-121">6 – 영상</span><span class="sxs-lookup"><span data-stu-id="0424f-121">6 – Video</span></span></p></li>
<li><p><span data-ttu-id="0424f-122">7 – 앱 초대</span><span class="sxs-lookup"><span data-stu-id="0424f-122">7 – App Invite</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


<span data-ttu-id="0424f-123">LcsCDR에서 MediaTypes의 값에 대 한 형식 지정을 확인 하려는 경우 다음 조인 조각을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0424f-123">If you are trying to determine the modality type for the values in LcsCDR.SessionDetailsView.MediaTypes, then you need to use the following Join snippet:</span></span>

    LEFT JOIN on Media.MediaId = MediaList.MediaId

</div>

<span> </span>

</div>

</div>

</div>

