---
title: 'Lync Server 2013: Dialog 테이블'
description: 'Lync Server 2013: Dialog 테이블'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Dialog table
ms:assetid: 4d93424f-9072-43f5-83c2-3d539e3e9ca6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398313(v=OCS.15)
ms:contentKeyID: 48184068
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7ae93b8ca9f1146b7dc164803f27cbeeadc66777
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559724"
---
# <a name="dialog-table-in-lync-server-2013"></a><span data-ttu-id="ba4ed-103">Lync Server 2013의 Dialog 테이블</span><span class="sxs-lookup"><span data-stu-id="ba4ed-103">Dialog table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ba4ed-104">_**마지막으로 수정 된 항목:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="ba4ed-104">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="ba4ed-105">Dialog 테이블은 각 레코드가 하나의 SIP(Session Initiation Protocol) 대화를 나타내는 지원 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="ba4ed-105">The Dialog table is a supporting table; each record represents one Session Initiation Protocol (SIP) dialog.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ba4ed-106"><strong>열</strong></span><span class="sxs-lookup"><span data-stu-id="ba4ed-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="ba4ed-107"><strong>데이터 형식</strong></span><span class="sxs-lookup"><span data-stu-id="ba4ed-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="ba4ed-108"><strong>키/인덱스</strong></span><span class="sxs-lookup"><span data-stu-id="ba4ed-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="ba4ed-109"><strong>세부 정보</strong></span><span class="sxs-lookup"><span data-stu-id="ba4ed-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ba4ed-110"><strong>Conferencedatetime이 동일할</strong></span><span class="sxs-lookup"><span data-stu-id="ba4ed-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="ba4ed-111">datetime</span><span class="sxs-lookup"><span data-stu-id="ba4ed-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="ba4ed-112">Primary</span><span class="sxs-lookup"><span data-stu-id="ba4ed-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="ba4ed-p101">QoE(체감 품질) 에이전트가 발신자 또는 수신자로부터 첫 번째 보고서를 받는 시간입니다. SessionSeq와 함께 세션을 고유하게 식별하기 위해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ba4ed-p101">Time when the Quality of Excellence (QoE) agent receives the first report from either caller or callee. Used in conjunction with SessionSeq to uniquely identify a session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba4ed-115"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="ba4ed-115"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="ba4ed-116">int</span><span class="sxs-lookup"><span data-stu-id="ba4ed-116">int</span></span></p></td>
<td><p><span data-ttu-id="ba4ed-117">Primary</span><span class="sxs-lookup"><span data-stu-id="ba4ed-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="ba4ed-118">ConferenceDateTime이 동일할 때 세션을 구분하기 위한 시퀀스 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="ba4ed-118">Sequence number to differentiate sessions when they have the same ConferenceDateTime.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba4ed-119"><strong>DialogID</strong></span><span class="sxs-lookup"><span data-stu-id="ba4ed-119"><strong>DialogID</strong></span></span></p></td>
<td><p><span data-ttu-id="ba4ed-120">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="ba4ed-120">varchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ba4ed-121">전역으로 고유한 대화 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="ba4ed-121">Dialog ID which is globally unique.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba4ed-122"><strong>DialogIDChecksum</strong></span><span class="sxs-lookup"><span data-stu-id="ba4ed-122"><strong>DialogIDChecksum</strong></span></span></p></td>
<td><p><span data-ttu-id="ba4ed-123">int</span><span class="sxs-lookup"><span data-stu-id="ba4ed-123">int</span></span></p></td>
<td><p><span data-ttu-id="ba4ed-124">인덱스</span><span class="sxs-lookup"><span data-stu-id="ba4ed-124">index</span></span></p></td>
<td><p><span data-ttu-id="ba4ed-125">대화 ID의 체크섬입니다.</span><span class="sxs-lookup"><span data-stu-id="ba4ed-125">Checksum of the Dialog ID.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

