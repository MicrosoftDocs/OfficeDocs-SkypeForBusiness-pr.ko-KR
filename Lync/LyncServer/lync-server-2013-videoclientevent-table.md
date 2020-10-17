---
title: 'Lync Server 2013: VideoClientEvent 테이블'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: VideoClientEvent table
ms:assetid: e8ab963b-fe1d-45b3-b9bd-66a5f44c1629
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399039(v=OCS.15)
ms:contentKeyID: 48185891
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9282af929757a4703f40537cb94d50761b1ac422
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48527585"
---
# <a name="videoclientevent-table-in-lync-server-2013"></a><span data-ttu-id="d83e4-102">Lync Server 2013의 VideoClientEvent 테이블</span><span class="sxs-lookup"><span data-stu-id="d83e4-102">VideoClientEvent table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d83e4-103">_**마지막으로 수정 된 항목:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="d83e4-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="d83e4-104">각 레코드에는 비디오 통화의 한 끝점에 대 한 클라이언트 이벤트가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d83e4-104">Each record contains client event for one endpoint in a video call.</span></span> <span data-ttu-id="d83e4-105">일반적으로 한 통화에는 발신자 용 레코드와 수신자를 위한 레코드가 각각 하나씩 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d83e4-105">Usually, one call has two records, one for caller and one for callee.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d83e4-106"><strong>열</strong></span><span class="sxs-lookup"><span data-stu-id="d83e4-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="d83e4-107"><strong>데이터 형식</strong></span><span class="sxs-lookup"><span data-stu-id="d83e4-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="d83e4-108"><strong>키/인덱스</strong></span><span class="sxs-lookup"><span data-stu-id="d83e4-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="d83e4-109"><strong>세부 정보</strong></span><span class="sxs-lookup"><span data-stu-id="d83e4-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d83e4-110"><strong>Conferencedatetime이 동일할</strong></span><span class="sxs-lookup"><span data-stu-id="d83e4-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="d83e4-111">datetime</span><span class="sxs-lookup"><span data-stu-id="d83e4-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="d83e4-112">Primary</span><span class="sxs-lookup"><span data-stu-id="d83e4-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="d83e4-113"><a href="lync-server-2013-medialine-table.md">Lync Server 2013의 Medialofftable</a>에서 참조 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d83e4-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d83e4-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="d83e4-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="d83e4-115">int</span><span class="sxs-lookup"><span data-stu-id="d83e4-115">int</span></span></p></td>
<td><p><span data-ttu-id="d83e4-116">Primary</span><span class="sxs-lookup"><span data-stu-id="d83e4-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="d83e4-117"><a href="lync-server-2013-medialine-table.md">Lync Server 2013의 Medialofftable</a>에서 참조 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d83e4-117">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d83e4-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="d83e4-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="d83e4-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="d83e4-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="d83e4-120">Primary</span><span class="sxs-lookup"><span data-stu-id="d83e4-120">Primary</span></span></p></td>
<td><p><span data-ttu-id="d83e4-121"><a href="lync-server-2013-medialine-table.md">Lync Server 2013의 Medialofftable</a>에서 참조 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d83e4-121">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d83e4-122"><strong>FromCaller</strong></span><span class="sxs-lookup"><span data-stu-id="d83e4-122"><strong>FromCaller</strong></span></span></p></td>
<td><p><span data-ttu-id="d83e4-123">비트만</span><span class="sxs-lookup"><span data-stu-id="d83e4-123">bit</span></span></p></td>
<td><p><span data-ttu-id="d83e4-124">Primary</span><span class="sxs-lookup"><span data-stu-id="d83e4-124">Primary</span></span></p></td>
<td><p><span data-ttu-id="d83e4-125">0: 수신자 데이터</span><span class="sxs-lookup"><span data-stu-id="d83e4-125">0: Callee’s data</span></span></p>
<p><span data-ttu-id="d83e4-126">1: 발신자 데이터</span><span class="sxs-lookup"><span data-stu-id="d83e4-126">1: Caller’s data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d83e4-127"><strong>NetworkBandwidthLowEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="d83e4-127"><strong>NetworkBandwidthLowEventRatio</strong></span></span></p></td>
<td></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d83e4-128">세션 완료율 \ 대역폭 이벤트가 ' 불량 ' 상태에 대해 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="d83e4-128">Percentage of session the LowBandwidth event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="d83e4-129">사용 가능한 대역폭이 충분 하지 않은 음성 환경에 적합 합니다.</span><span class="sxs-lookup"><span data-stu-id="d83e4-129">The available bandwidth is insufficient for an acceptable voice experience.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d83e4-130"><strong>NetworkReceiveQualityEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="d83e4-130"><strong>NetworkReceiveQualityEventRatio</strong></span></span></p></td>
<td></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d83e4-131">세션 백분율 상태로 receivesendquality 이벤트가 ' 잘못 된 ' 상태에 대해 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="d83e4-131">Percentage of session the ReceiveSendQuality event was fired for ‘Bad’ state.</span></span></p>
<p><span data-ttu-id="d83e4-132">지터 또는 패킷 손실 측면의 네트워크 품질이 심각 하 고 수신 중인 오디오 품질에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d83e4-132">Network quality in terms of jitter or packet loss is severe and impacts the quality of audio being received.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

