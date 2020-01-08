---
title: 'Lync Server 2013: VideoClientEvent 테이블'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: VideoClientEvent table
ms:assetid: e8ab963b-fe1d-45b3-b9bd-66a5f44c1629
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399039(v=OCS.15)
ms:contentKeyID: 48185891
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 79b428a639cee6fb0df04cc969b529c5bbbfb2c9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983252"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="videoclientevent-table-in-lync-server-2013"></a><span data-ttu-id="5455b-102">Lync Server 2013의 VideoClientEvent 테이블</span><span class="sxs-lookup"><span data-stu-id="5455b-102">VideoClientEvent table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5455b-103">_**마지막으로 수정한 주제:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="5455b-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="5455b-104">각 레코드에는 비디오 통화의 한 끝점에 대 한 클라이언트 이벤트가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5455b-104">Each record contains client event for one endpoint in a video call.</span></span> <span data-ttu-id="5455b-105">일반적으로 한 통화에는 두 개의 레코드 (호출자 용 1 개와 피호출자 용)가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5455b-105">Usually, one call has two records, one for caller and one for callee.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5455b-106"><strong>열</strong></span><span class="sxs-lookup"><span data-stu-id="5455b-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="5455b-107"><strong>데이터 형식</strong></span><span class="sxs-lookup"><span data-stu-id="5455b-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="5455b-108"><strong>키/인덱스</strong></span><span class="sxs-lookup"><span data-stu-id="5455b-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="5455b-109"><strong>세부적인</strong></span><span class="sxs-lookup"><span data-stu-id="5455b-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5455b-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="5455b-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="5455b-111">dmtf</span><span class="sxs-lookup"><span data-stu-id="5455b-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="5455b-112">주요한</span><span class="sxs-lookup"><span data-stu-id="5455b-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="5455b-113"><a href="lync-server-2013-medialine-table.md">Lync Server 2013의 Medialine 테이블</a>에서 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="5455b-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5455b-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="5455b-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="5455b-115">int</span><span class="sxs-lookup"><span data-stu-id="5455b-115">int</span></span></p></td>
<td><p><span data-ttu-id="5455b-116">주요한</span><span class="sxs-lookup"><span data-stu-id="5455b-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="5455b-117"><a href="lync-server-2013-medialine-table.md">Lync Server 2013의 Medialine 테이블</a>에서 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="5455b-117">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5455b-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="5455b-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="5455b-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="5455b-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="5455b-120">주요한</span><span class="sxs-lookup"><span data-stu-id="5455b-120">Primary</span></span></p></td>
<td><p><span data-ttu-id="5455b-121"><a href="lync-server-2013-medialine-table.md">Lync Server 2013의 Medialine 테이블</a>에서 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="5455b-121">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5455b-122"><strong>FromCaller</strong></span><span class="sxs-lookup"><span data-stu-id="5455b-122"><strong>FromCaller</strong></span></span></p></td>
<td><p><span data-ttu-id="5455b-123">다소</span><span class="sxs-lookup"><span data-stu-id="5455b-123">bit</span></span></p></td>
<td><p><span data-ttu-id="5455b-124">주요한</span><span class="sxs-lookup"><span data-stu-id="5455b-124">Primary</span></span></p></td>
<td><p><span data-ttu-id="5455b-125">0: 피호출자의 데이터</span><span class="sxs-lookup"><span data-stu-id="5455b-125">0: Callee’s data</span></span></p>
<p><span data-ttu-id="5455b-126">1: 발신자의 데이터</span><span class="sxs-lookup"><span data-stu-id="5455b-126">1: Caller’s data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5455b-127"><strong>NetworkBandwidthLowEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="5455b-127"><strong>NetworkBandwidthLowEventRatio</strong></span></span></p></td>
<td></td>
<td><p> </p></td>
<td><p><span data-ttu-id="5455b-128">세션 백분율 \ \ \ \에 대 한 \ \ \ n 대역폭 이벤트가 ' 불량 ' 상태에 대해 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="5455b-128">Percentage of session the LowBandwidth event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="5455b-129">사용할 수 있는 대역폭이 불충분 한 음성 환경에 적합 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5455b-129">The available bandwidth is insufficient for an acceptable voice experience.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5455b-130"><strong>NetworkReceiveQualityEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="5455b-130"><strong>NetworkReceiveQualityEventRatio</strong></span></span></p></td>
<td></td>
<td><p> </p></td>
<td><p><span data-ttu-id="5455b-131">세션 백분율 ReceiveSendQuality 이벤트가 ' 잘못 된 ' 상태에 대해 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="5455b-131">Percentage of session the ReceiveSendQuality event was fired for ‘Bad’ state.</span></span></p>
<p><span data-ttu-id="5455b-132">지터 또는 패킷 손실 측면의 네트워크 품질은 심각 하며 수신 되는 오디오 품질에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5455b-132">Network quality in terms of jitter or packet loss is severe and impacts the quality of audio being received.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

