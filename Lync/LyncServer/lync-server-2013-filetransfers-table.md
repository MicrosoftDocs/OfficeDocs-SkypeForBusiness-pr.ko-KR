---
title: 'Lync Server 2013: FileTransfers 테이블'
description: 'Lync Server 2013: FileTransfers 테이블'
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
ms.openlocfilehash: ccde45fa3743a809499273676d567846ef292ecc
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573364"
---
# <a name="filetransfers-table-in-lync-server-2013"></a><span data-ttu-id="af6b3-103">Lync Server 2013의 FileTransfers 테이블</span><span class="sxs-lookup"><span data-stu-id="af6b3-103">FileTransfers table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="af6b3-104">_**마지막으로 수정 된 항목:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="af6b3-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="af6b3-105">각 레코드는 하나의 파일 전송 세션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="af6b3-105">Each record represents one file transfer session.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="af6b3-106">열</span><span class="sxs-lookup"><span data-stu-id="af6b3-106">Column</span></span></th>
<th><span data-ttu-id="af6b3-107">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="af6b3-107">Data Type</span></span></th>
<th><span data-ttu-id="af6b3-108">키/인덱스</span><span class="sxs-lookup"><span data-stu-id="af6b3-108">Key/Index</span></span></th>
<th><span data-ttu-id="af6b3-109">세부 정보</span><span class="sxs-lookup"><span data-stu-id="af6b3-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="af6b3-110"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="af6b3-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="af6b3-111">datetime</span><span class="sxs-lookup"><span data-stu-id="af6b3-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="af6b3-112">Primary, Foreign</span><span class="sxs-lookup"><span data-stu-id="af6b3-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="af6b3-113">세션 요청 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="af6b3-113">Time of session request.</span></span> <span data-ttu-id="af6b3-114"><strong>SessionIdSeq</strong>와 함께 세션을 고유하게 식별하기 위해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="af6b3-114">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="af6b3-115">자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 Dialogs 표</a> 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="af6b3-115">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="af6b3-116"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="af6b3-116"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="af6b3-117">int</span><span class="sxs-lookup"><span data-stu-id="af6b3-117">int</span></span></p></td>
<td><p><span data-ttu-id="af6b3-118">Primary, Foreign</span><span class="sxs-lookup"><span data-stu-id="af6b3-118">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="af6b3-119">세션을 식별하기 위한 ID 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="af6b3-119">ID number to identify the session.</span></span> <span data-ttu-id="af6b3-120"><strong>SessionIdTime</strong>과 함께 세션을 고유하게 식별하기 위해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="af6b3-120">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="af6b3-121">자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 Dialogs 표</a> 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="af6b3-121">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="af6b3-122"><strong>File Name</strong></span><span class="sxs-lookup"><span data-stu-id="af6b3-122"><strong>File Name</strong></span></span></p></td>
<td><p><span data-ttu-id="af6b3-123">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="af6b3-123">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="af6b3-124">파일의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="af6b3-124">Name of the file.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="af6b3-125"><strong>FileIdentity</strong></span><span class="sxs-lookup"><span data-stu-id="af6b3-125"><strong>FileIdentity</strong></span></span></p></td>
<td><p><span data-ttu-id="af6b3-126">고유</span><span class="sxs-lookup"><span data-stu-id="af6b3-126">uniqueidentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="af6b3-127">동일한 파일 이름을 포함하는 각 전송 작업을 구분하기 위한 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="af6b3-127">Unique identifier to distinguish between file transfers involving the same file name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="af6b3-128"><strong>쿠키나</strong></span><span class="sxs-lookup"><span data-stu-id="af6b3-128"><strong>Cookie</strong></span></span></p></td>
<td><p><span data-ttu-id="af6b3-129">name</span><span class="sxs-lookup"><span data-stu-id="af6b3-129">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="af6b3-130">Primary</span><span class="sxs-lookup"><span data-stu-id="af6b3-130">Primary</span></span></p></td>
<td><p><span data-ttu-id="af6b3-131">이 항목과 연결 중인 모든 후속 작업 메시지를 식별하기 위해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="af6b3-131">Used to identify every follow-up message as being associated with this one.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="af6b3-132"><strong>수락</strong></span><span class="sxs-lookup"><span data-stu-id="af6b3-132"><strong>Accept</strong></span></span></p></td>
<td><p><span data-ttu-id="af6b3-133">비트만</span><span class="sxs-lookup"><span data-stu-id="af6b3-133">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="af6b3-p103">TRUE 또는 NULL일 수 있습니다. TRUE인 경우 Reject 및 Cancel이 NULL이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="af6b3-p103">Can be TRUE or NULL. If TRUE, then Reject and Cancel will be NULL.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="af6b3-136"><strong>거부</strong></span><span class="sxs-lookup"><span data-stu-id="af6b3-136"><strong>Reject</strong></span></span></p></td>
<td><p><span data-ttu-id="af6b3-137">비트만</span><span class="sxs-lookup"><span data-stu-id="af6b3-137">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="af6b3-p104">TRUE 또는 NULL일 수 있습니다. TRUE인 경우 Accept 및 Cancel이 NULL이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="af6b3-p104">Can be TRUE or NULL. If TRUE, then Accept and Cancel will be NULL.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="af6b3-140"><strong>취소</strong></span><span class="sxs-lookup"><span data-stu-id="af6b3-140"><strong>Cancel</strong></span></span></p></td>
<td><p><span data-ttu-id="af6b3-141">비트만</span><span class="sxs-lookup"><span data-stu-id="af6b3-141">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="af6b3-p105">TRUE 또는 NULL일 수 있습니다. TRUE인 경우 Accept 및 Reject가 NULL이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="af6b3-p105">Can be TRUE or NULL. If TRUE, then Accept and Reject will be NULL.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

