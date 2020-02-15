---
title: 'Lync Server 2013: tblComplianceData'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblComplianceData
ms:assetid: 05b28f9b-4aba-4b69-ba8d-2ceeb6cbfaac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558606(v=OCS.15)
ms:contentKeyID: 48183308
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 03f5a65b11c610849c5b9d031f24d236dcbcf332
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048509"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblcompliancedata-in-lync-server-2013"></a><span data-ttu-id="87caf-102">Lync Server 2013의 tblComplianceData</span><span class="sxs-lookup"><span data-stu-id="87caf-102">tblComplianceData in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="87caf-103">_**마지막으로 수정 된 항목:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="87caf-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="87caf-104">tblComplianceData에는 준수 어댑터에서 아직 처리되지 않은 준수 이벤트가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="87caf-104">tblComplianceData contains the compliance events that have not been processed by the compliance adapter yet.</span></span>

### <a name="columns"></a><span data-ttu-id="87caf-105">단</span><span class="sxs-lookup"><span data-stu-id="87caf-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="87caf-106">열</span><span class="sxs-lookup"><span data-stu-id="87caf-106">Column</span></span></th>
<th><span data-ttu-id="87caf-107">형식</span><span class="sxs-lookup"><span data-stu-id="87caf-107">Type</span></span></th>
<th><span data-ttu-id="87caf-108">설명</span><span class="sxs-lookup"><span data-stu-id="87caf-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="87caf-109">Tblcompliancedata.cmpleventid</span><span class="sxs-lookup"><span data-stu-id="87caf-109">cmplEventID</span></span></p></td>
<td><p><span data-ttu-id="87caf-110">bigint, null이 아님</span><span class="sxs-lookup"><span data-stu-id="87caf-110">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="87caf-111">이벤트 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="87caf-111">Event ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="87caf-112">entryDate</span><span class="sxs-lookup"><span data-stu-id="87caf-112">entryDate</span></span></p></td>
<td><p><span data-ttu-id="87caf-113">smalldatetime, null이 아님</span><span class="sxs-lookup"><span data-stu-id="87caf-113">smalldatetime, not null</span></span></p></td>
<td><p><span data-ttu-id="87caf-114">삽입 시간(cmplType=9의 경우에는 항목이 단순히 자리 표시자이므로 오랜 시간 후일 수 있음)</span><span class="sxs-lookup"><span data-stu-id="87caf-114">Time of insertion (may be far in the future for cmplType=9 because the entry is just a placeholder in that case).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="87caf-115">cmplType</span><span class="sxs-lookup"><span data-stu-id="87caf-115">cmplType</span></span></p></td>
<td><p><span data-ttu-id="87caf-116">int, null이 아님</span><span class="sxs-lookup"><span data-stu-id="87caf-116">int, not null</span></span></p></td>
<td><p><span data-ttu-id="87caf-117">준수 이벤트 유형:</span><span class="sxs-lookup"><span data-stu-id="87caf-117">Type of compliance event:</span></span></p>
<ul>
<li><p><span data-ttu-id="87caf-118">1: 채팅</span><span class="sxs-lookup"><span data-stu-id="87caf-118">1: Chat</span></span></p></li>
<li><p><span data-ttu-id="87caf-119">2: 백채트</span><span class="sxs-lookup"><span data-stu-id="87caf-119">2: Backchat</span></span></p></li>
<li><p><span data-ttu-id="87caf-120">3: 파일 다운로드</span><span class="sxs-lookup"><span data-stu-id="87caf-120">3: File download</span></span></p></li>
<li><p><span data-ttu-id="87caf-121">4: 파일 업로드</span><span class="sxs-lookup"><span data-stu-id="87caf-121">4: File upload</span></span></p></li>
<li><p><span data-ttu-id="87caf-122">9: 임시 파일 전송</span><span class="sxs-lookup"><span data-stu-id="87caf-122">9: Provisional file transfer</span></span></p></li>
<li><p><span data-ttu-id="87caf-123">10: 채팅 삭제(바꾸기 포함)</span><span class="sxs-lookup"><span data-stu-id="87caf-123">10: Chat deletion (with replace)</span></span></p></li>
<li><p><span data-ttu-id="87caf-124">11: 채팅 삭제</span><span class="sxs-lookup"><span data-stu-id="87caf-124">11: Chat purging</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="87caf-125">cmplTime</span><span class="sxs-lookup"><span data-stu-id="87caf-125">cmplTime</span></span></p></td>
<td><p><span data-ttu-id="87caf-126">bigint, null이 아님</span><span class="sxs-lookup"><span data-stu-id="87caf-126">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="87caf-127">이벤트의 타임스탬프입니다.</span><span class="sxs-lookup"><span data-stu-id="87caf-127">Time stamp for the event.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="87caf-128">cmplChannelUri</span><span class="sxs-lookup"><span data-stu-id="87caf-128">cmplChannelUri</span></span></p></td>
<td><p><span data-ttu-id="87caf-129">nvarchar(255), null이 아님</span><span class="sxs-lookup"><span data-stu-id="87caf-129">nvarchar (255), not null</span></span></p></td>
<td><p><span data-ttu-id="87caf-130">채널 URI(Uniform Resource Identifier)입니다.</span><span class="sxs-lookup"><span data-stu-id="87caf-130">Channel Uniform Resource Identifier (URI).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="87caf-131">cmplChatID</span><span class="sxs-lookup"><span data-stu-id="87caf-131">cmplChatID</span></span></p></td>
<td><p><span data-ttu-id="87caf-132">bigint</span><span class="sxs-lookup"><span data-stu-id="87caf-132">bigint</span></span></p></td>
<td><p><span data-ttu-id="87caf-133">채팅 ID(tblChat.chatId 테이블에 해당됨)</span><span class="sxs-lookup"><span data-stu-id="87caf-133">Chat ID (corresponding to tblChat.chatId table).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="87caf-134">cmplUserID</span><span class="sxs-lookup"><span data-stu-id="87caf-134">cmplUserID</span></span></p></td>
<td><p><span data-ttu-id="87caf-135">int, null이 아님</span><span class="sxs-lookup"><span data-stu-id="87caf-135">int, not null</span></span></p></td>
<td><p><span data-ttu-id="87caf-136">게시자의 사용자 ID(tblPrincipal.prinID 테이블에 해당됨)</span><span class="sxs-lookup"><span data-stu-id="87caf-136">Principal ID of the poster (corresponding to tblPrincipal.prinID table).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="87caf-137">cmplUserUri</span><span class="sxs-lookup"><span data-stu-id="87caf-137">cmplUserUri</span></span></p></td>
<td><p><span data-ttu-id="87caf-138">nvarchar(255), null이 아님</span><span class="sxs-lookup"><span data-stu-id="87caf-138">nvarchar (255), not null</span></span></p></td>
<td><p><span data-ttu-id="87caf-139">사용자 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="87caf-139">User URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="87caf-140">cmplMessage</span><span class="sxs-lookup"><span data-stu-id="87caf-140">cmplMessage</span></span></p></td>
<td><p><span data-ttu-id="87caf-141">nvarchar(max)</span><span class="sxs-lookup"><span data-stu-id="87caf-141">nvarchar (max)</span></span></p></td>
<td><p><span data-ttu-id="87caf-142">메시지(인코딩은 cmplType에 따라 다름)</span><span class="sxs-lookup"><span data-stu-id="87caf-142">Message (encoding depends on cmplType).</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="87caf-143">키</span><span class="sxs-lookup"><span data-stu-id="87caf-143">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="87caf-144">열</span><span class="sxs-lookup"><span data-stu-id="87caf-144">Column</span></span></th>
<th><span data-ttu-id="87caf-145">설명</span><span class="sxs-lookup"><span data-stu-id="87caf-145">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="87caf-146">Tblcompliancedata.cmpleventid</span><span class="sxs-lookup"><span data-stu-id="87caf-146">cmplEventID</span></span></p></td>
<td><p><span data-ttu-id="87caf-147">기본 키입니다.</span><span class="sxs-lookup"><span data-stu-id="87caf-147">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

