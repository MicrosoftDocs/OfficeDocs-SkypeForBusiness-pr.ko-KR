---
title: 'Lync Server 2013: FileTransfers 테이블'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: FileTransfers table
ms:assetid: 5368e67c-d8a9-43a1-9472-a839950dedb3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398353(v=OCS.15)
ms:contentKeyID: 48184118
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: de8a3e69c670c273bcdd91ac5895c0b1f0b15d80
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743367"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="filetransfers-table-in-lync-server-2013"></a><span data-ttu-id="2cc49-102">Lync Server 2013의 FileTransfers 테이블</span><span class="sxs-lookup"><span data-stu-id="2cc49-102">FileTransfers table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2cc49-103">_**마지막으로 수정한 주제:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="2cc49-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="2cc49-104">각 레코드는 하나의 파일 전송 세션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2cc49-104">Each record represents one file transfer session.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2cc49-105">열</span><span class="sxs-lookup"><span data-stu-id="2cc49-105">Column</span></span></th>
<th><span data-ttu-id="2cc49-106">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="2cc49-106">Data Type</span></span></th>
<th><span data-ttu-id="2cc49-107">키/인덱스</span><span class="sxs-lookup"><span data-stu-id="2cc49-107">Key/Index</span></span></th>
<th><span data-ttu-id="2cc49-108">세부적인</span><span class="sxs-lookup"><span data-stu-id="2cc49-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2cc49-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="2cc49-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="2cc49-110">dmtf</span><span class="sxs-lookup"><span data-stu-id="2cc49-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="2cc49-111">기본, 외래</span><span class="sxs-lookup"><span data-stu-id="2cc49-111">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="2cc49-112">세션 요청 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="2cc49-112">Time of session request.</span></span> <span data-ttu-id="2cc49-113">세션을 고유 하 게 식별 하는 <strong>Sessionidseq</strong> 와 함께 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2cc49-113">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="2cc49-114">자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 대화 상자 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2cc49-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2cc49-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="2cc49-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="2cc49-116">int</span><span class="sxs-lookup"><span data-stu-id="2cc49-116">int</span></span></p></td>
<td><p><span data-ttu-id="2cc49-117">기본, 외래</span><span class="sxs-lookup"><span data-stu-id="2cc49-117">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="2cc49-118">세션을 식별 하는 ID 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="2cc49-118">ID number to identify the session.</span></span> <span data-ttu-id="2cc49-119">세션을 고유 하 게 식별 하는 <strong>Sessionidtime</strong> 과 함께 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2cc49-119">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="2cc49-120">자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 대화 상자 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2cc49-120">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2cc49-121"><strong>파일 이름</strong></span><span class="sxs-lookup"><span data-stu-id="2cc49-121"><strong>File Name</strong></span></span></p></td>
<td><p><span data-ttu-id="2cc49-122">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="2cc49-122">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2cc49-123">파일의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="2cc49-123">Name of the file.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2cc49-124"><strong>FileIdentity</strong></span><span class="sxs-lookup"><span data-stu-id="2cc49-124"><strong>FileIdentity</strong></span></span></p></td>
<td><p><span data-ttu-id="2cc49-125">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="2cc49-125">uniqueidentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2cc49-126">동일한 파일 이름을 포함 하는 파일 전송을 구분 하는 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="2cc49-126">Unique identifier to distinguish between file transfers involving the same file name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2cc49-127"><strong>쿠키란</strong></span><span class="sxs-lookup"><span data-stu-id="2cc49-127"><strong>Cookie</strong></span></span></p></td>
<td><p><span data-ttu-id="2cc49-128">name</span><span class="sxs-lookup"><span data-stu-id="2cc49-128">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="2cc49-129">주요한</span><span class="sxs-lookup"><span data-stu-id="2cc49-129">Primary</span></span></p></td>
<td><p><span data-ttu-id="2cc49-130">모든 추가 작업 메시지를이 항목에 연결 된 것으로 식별 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2cc49-130">Used to identify every follow-up message as being associated with this one.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2cc49-131"><strong>사항</strong></span><span class="sxs-lookup"><span data-stu-id="2cc49-131"><strong>Accept</strong></span></span></p></td>
<td><p><span data-ttu-id="2cc49-132">다소</span><span class="sxs-lookup"><span data-stu-id="2cc49-132">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2cc49-133">TRUE 또는 NULL 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2cc49-133">Can be TRUE or NULL.</span></span> <span data-ttu-id="2cc49-134">TRUE 인 경우 거부 및 취소는 NULL입니다.</span><span class="sxs-lookup"><span data-stu-id="2cc49-134">If TRUE, then Reject and Cancel will be NULL.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2cc49-135"><strong>거부</strong></span><span class="sxs-lookup"><span data-stu-id="2cc49-135"><strong>Reject</strong></span></span></p></td>
<td><p><span data-ttu-id="2cc49-136">다소</span><span class="sxs-lookup"><span data-stu-id="2cc49-136">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2cc49-137">TRUE 또는 NULL 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2cc49-137">Can be TRUE or NULL.</span></span> <span data-ttu-id="2cc49-138">TRUE 이면 Accept와 Cancel은 NULL입니다.</span><span class="sxs-lookup"><span data-stu-id="2cc49-138">If TRUE, then Accept and Cancel will be NULL.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2cc49-139"><strong>취소</strong></span><span class="sxs-lookup"><span data-stu-id="2cc49-139"><strong>Cancel</strong></span></span></p></td>
<td><p><span data-ttu-id="2cc49-140">다소</span><span class="sxs-lookup"><span data-stu-id="2cc49-140">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2cc49-141">TRUE 또는 NULL 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2cc49-141">Can be TRUE or NULL.</span></span> <span data-ttu-id="2cc49-142">TRUE 이면 Accept 및 Reject는 NULL입니다.</span><span class="sxs-lookup"><span data-stu-id="2cc49-142">If TRUE, then Accept and Reject will be NULL.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

