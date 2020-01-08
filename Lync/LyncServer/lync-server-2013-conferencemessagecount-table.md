---
title: 'Lync Server 2013: ConferenceMessageCount 테이블'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: ConferenceMessageCount table
ms:assetid: 78569dbf-5217-42fa-ba1a-4380f56e2a3d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398590(v=OCS.15)
ms:contentKeyID: 48184570
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0d2994f02bf087ef55edff6b2153e7504f881b03
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980250"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferencemessagecount-table-in-lync-server-2013"></a><span data-ttu-id="dbd39-102">Lync Server 2013의 ConferenceMessageCount 테이블</span><span class="sxs-lookup"><span data-stu-id="dbd39-102">ConferenceMessageCount table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dbd39-103">_**마지막으로 수정한 주제:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="dbd39-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="dbd39-104">이 테이블의 각 레코드는 한 명의 IM 회의에 있는 한 명의 사용자를 나타내고 해당 사용자가 보낸 메시지 수를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="dbd39-104">Each record in this table represents one user in one IM conference and includes the number of messages sent by that user.</span></span> <span data-ttu-id="dbd39-105">각 회의는이 테이블의 여러 레코드로 표시 됩니다. 각 사용자에 대 한 레코드 하나.</span><span class="sxs-lookup"><span data-stu-id="dbd39-105">Each conference is represented by multiple records in this table; one record for each user.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dbd39-106">열</span><span class="sxs-lookup"><span data-stu-id="dbd39-106">Column</span></span></th>
<th><span data-ttu-id="dbd39-107">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="dbd39-107">Data Type</span></span></th>
<th><span data-ttu-id="dbd39-108">키/인덱스</span><span class="sxs-lookup"><span data-stu-id="dbd39-108">Key/Index</span></span></th>
<th><span data-ttu-id="dbd39-109">세부적인</span><span class="sxs-lookup"><span data-stu-id="dbd39-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dbd39-110"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="dbd39-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="dbd39-111">dmtf</span><span class="sxs-lookup"><span data-stu-id="dbd39-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="dbd39-112">기본, 외래</span><span class="sxs-lookup"><span data-stu-id="dbd39-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="dbd39-113">컨퍼런스 인스턴스 시간.</span><span class="sxs-lookup"><span data-stu-id="dbd39-113">Time of conference instance.</span></span> <span data-ttu-id="dbd39-114">회의 인스턴스를 고유 하 게 식별 하기 위해 <strong>Sessionidseq</strong> 와 함께 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dbd39-114">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="dbd39-115">자세한 내용은 <a href="lync-server-2013-conferences-table.md">Lync Server 2013의 컨퍼런스 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="dbd39-115">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbd39-116"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="dbd39-116"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="dbd39-117">int</span><span class="sxs-lookup"><span data-stu-id="dbd39-117">int</span></span></p></td>
<td><p><span data-ttu-id="dbd39-118">기본, 외래</span><span class="sxs-lookup"><span data-stu-id="dbd39-118">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="dbd39-119">회의 인스턴스를 식별 하는 ID 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="dbd39-119">ID number to identify the conference instance.</span></span> <span data-ttu-id="dbd39-120">회의 인스턴스를 고유 하 게 식별 하는 <strong>Sessionidtime</strong> 과 함께 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dbd39-120">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="dbd39-121">자세한 내용은 <a href="lync-server-2013-conferences-table.md">Lync Server 2013의 컨퍼런스 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="dbd39-121">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dbd39-122"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="dbd39-122"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="dbd39-123">int</span><span class="sxs-lookup"><span data-stu-id="dbd39-123">int</span></span></p></td>
<td><p><span data-ttu-id="dbd39-124">외부</span><span class="sxs-lookup"><span data-stu-id="dbd39-124">Foreign</span></span></p></td>
<td><p><span data-ttu-id="dbd39-125"><a href="lync-server-2013-users-table.md">Lync Server 2013의 사용자 테이블</a>에서 참조 된이 사용자를 식별 하는 고유 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="dbd39-125">Unique number identifying this user, referenced from the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbd39-126"><strong>MessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="dbd39-126"><strong>MessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="dbd39-127">smallint</span><span class="sxs-lookup"><span data-stu-id="dbd39-127">smallint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="dbd39-128">이 회의가 진행 되는 동안이 사용자가 보낸 메시지 수입니다.</span><span class="sxs-lookup"><span data-stu-id="dbd39-128">The number of messages sent by this user during this conference.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

