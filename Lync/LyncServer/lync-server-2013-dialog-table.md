---
title: 'Lync Server 2013: Dialog 테이블'
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
ms.openlocfilehash: a4c26c719e9d7e3cd0922813896896925a9bb6f9
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48519995"
---
# <a name="dialog-table-in-lync-server-2013"></a><span data-ttu-id="1118d-102">Lync Server 2013의 Dialog 테이블</span><span class="sxs-lookup"><span data-stu-id="1118d-102">Dialog table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1118d-103">_**마지막으로 수정 된 항목:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="1118d-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="1118d-104">Dialog 테이블은 각 레코드가 하나의 SIP(Session Initiation Protocol) 대화를 나타내는 지원 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="1118d-104">The Dialog table is a supporting table; each record represents one Session Initiation Protocol (SIP) dialog.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1118d-105"><strong>열</strong></span><span class="sxs-lookup"><span data-stu-id="1118d-105"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="1118d-106"><strong>데이터 형식</strong></span><span class="sxs-lookup"><span data-stu-id="1118d-106"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="1118d-107"><strong>키/인덱스</strong></span><span class="sxs-lookup"><span data-stu-id="1118d-107"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="1118d-108"><strong>세부 정보</strong></span><span class="sxs-lookup"><span data-stu-id="1118d-108"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1118d-109"><strong>Conferencedatetime이 동일할</strong></span><span class="sxs-lookup"><span data-stu-id="1118d-109"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="1118d-110">datetime</span><span class="sxs-lookup"><span data-stu-id="1118d-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="1118d-111">Primary</span><span class="sxs-lookup"><span data-stu-id="1118d-111">Primary</span></span></p></td>
<td><p><span data-ttu-id="1118d-p101">QoE(체감 품질) 에이전트가 발신자 또는 수신자로부터 첫 번째 보고서를 받는 시간입니다. SessionSeq와 함께 세션을 고유하게 식별하기 위해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="1118d-p101">Time when the Quality of Excellence (QoE) agent receives the first report from either caller or callee. Used in conjunction with SessionSeq to uniquely identify a session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1118d-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="1118d-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="1118d-115">int</span><span class="sxs-lookup"><span data-stu-id="1118d-115">int</span></span></p></td>
<td><p><span data-ttu-id="1118d-116">Primary</span><span class="sxs-lookup"><span data-stu-id="1118d-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="1118d-117">ConferenceDateTime이 동일할 때 세션을 구분하기 위한 시퀀스 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="1118d-117">Sequence number to differentiate sessions when they have the same ConferenceDateTime.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1118d-118"><strong>DialogID</strong></span><span class="sxs-lookup"><span data-stu-id="1118d-118"><strong>DialogID</strong></span></span></p></td>
<td><p><span data-ttu-id="1118d-119">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="1118d-119">varchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1118d-120">전역으로 고유한 대화 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="1118d-120">Dialog ID which is globally unique.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1118d-121"><strong>DialogIDChecksum</strong></span><span class="sxs-lookup"><span data-stu-id="1118d-121"><strong>DialogIDChecksum</strong></span></span></p></td>
<td><p><span data-ttu-id="1118d-122">int</span><span class="sxs-lookup"><span data-stu-id="1118d-122">int</span></span></p></td>
<td><p><span data-ttu-id="1118d-123">인덱스</span><span class="sxs-lookup"><span data-stu-id="1118d-123">index</span></span></p></td>
<td><p><span data-ttu-id="1118d-124">대화 ID의 체크섬입니다.</span><span class="sxs-lookup"><span data-stu-id="1118d-124">Checksum of the Dialog ID.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

