---
title: 'Lync Server 2013: Dialog 테이블'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Dialog table
ms:assetid: 4d93424f-9072-43f5-83c2-3d539e3e9ca6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398313(v=OCS.15)
ms:contentKeyID: 48184068
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d47744cf17d3459c16e382c3551b427aa45b5ce6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985662"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dialog-table-in-lync-server-2013"></a><span data-ttu-id="6e88d-102">Lync Server 2013의 Dialog 테이블</span><span class="sxs-lookup"><span data-stu-id="6e88d-102">Dialog table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6e88d-103">_**마지막으로 수정한 주제:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="6e88d-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="6e88d-104">대화 상자 테이블은 지원 테이블입니다. 각 레코드는 하나의 SIP (세션 초기화 프로토콜) 대화 상자를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="6e88d-104">The Dialog table is a supporting table; each record represents one Session Initiation Protocol (SIP) dialog.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6e88d-105"><strong>열</strong></span><span class="sxs-lookup"><span data-stu-id="6e88d-105"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="6e88d-106"><strong>데이터 형식</strong></span><span class="sxs-lookup"><span data-stu-id="6e88d-106"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="6e88d-107"><strong>키/인덱스</strong></span><span class="sxs-lookup"><span data-stu-id="6e88d-107"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="6e88d-108"><strong>세부적인</strong></span><span class="sxs-lookup"><span data-stu-id="6e88d-108"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6e88d-109"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="6e88d-109"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="6e88d-110">dmtf</span><span class="sxs-lookup"><span data-stu-id="6e88d-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="6e88d-111">주요한</span><span class="sxs-lookup"><span data-stu-id="6e88d-111">Primary</span></span></p></td>
<td><p><span data-ttu-id="6e88d-112">체감 품질 (고급 품질) 에이전트가 호출자 또는 호출 수신자 중 첫 번째 보고서를 받는 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="6e88d-112">Time when the Quality of Excellence (QoE) agent receives the first report from either caller or callee.</span></span> <span data-ttu-id="6e88d-113">세션을 고유 하 게 식별 하는 SessionSeq와 함께 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e88d-113">Used in conjunction with SessionSeq to uniquely identify a session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6e88d-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="6e88d-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="6e88d-115">int</span><span class="sxs-lookup"><span data-stu-id="6e88d-115">int</span></span></p></td>
<td><p><span data-ttu-id="6e88d-116">주요한</span><span class="sxs-lookup"><span data-stu-id="6e88d-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="6e88d-117">동일한 ConferenceDateTime 있을 때 세션을 구분 하는 시퀀스 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="6e88d-117">Sequence number to differentiate sessions when they have the same ConferenceDateTime.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6e88d-118"><strong>DialogID</strong></span><span class="sxs-lookup"><span data-stu-id="6e88d-118"><strong>DialogID</strong></span></span></p></td>
<td><p><span data-ttu-id="6e88d-119">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="6e88d-119">varchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6e88d-120">전역으로 고유한 대화 상자 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="6e88d-120">Dialog ID which is globally unique.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6e88d-121"><strong>DialogIDChecksum</strong></span><span class="sxs-lookup"><span data-stu-id="6e88d-121"><strong>DialogIDChecksum</strong></span></span></p></td>
<td><p><span data-ttu-id="6e88d-122">int</span><span class="sxs-lookup"><span data-stu-id="6e88d-122">int</span></span></p></td>
<td><p><span data-ttu-id="6e88d-123">색인</span><span class="sxs-lookup"><span data-stu-id="6e88d-123">index</span></span></p></td>
<td><p><span data-ttu-id="6e88d-124">대화 상자 ID의 체크섬입니다.</span><span class="sxs-lookup"><span data-stu-id="6e88d-124">Checksum of the Dialog ID.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

