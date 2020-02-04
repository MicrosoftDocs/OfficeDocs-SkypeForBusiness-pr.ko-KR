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
ms.openlocfilehash: 48516f307a084d30fde06a03548119e0ada34d6a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731508"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblcompliancedata-in-lync-server-2013"></a><span data-ttu-id="e017a-102">Lync Server 2013의 tblComplianceData</span><span class="sxs-lookup"><span data-stu-id="e017a-102">tblComplianceData in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e017a-103">_**마지막으로 수정한 주제:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="e017a-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="e017a-104">tblComplianceData에는 규정 준수 어댑터에서 아직 처리 하지 않은 준수 이벤트가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e017a-104">tblComplianceData contains the compliance events that have not been processed by the compliance adapter yet.</span></span>

### <a name="columns"></a><span data-ttu-id="e017a-105">열</span><span class="sxs-lookup"><span data-stu-id="e017a-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e017a-106">열</span><span class="sxs-lookup"><span data-stu-id="e017a-106">Column</span></span></th>
<th><span data-ttu-id="e017a-107">유형</span><span class="sxs-lookup"><span data-stu-id="e017a-107">Type</span></span></th>
<th><span data-ttu-id="e017a-108">설명</span><span class="sxs-lookup"><span data-stu-id="e017a-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e017a-109">cmplEventID</span><span class="sxs-lookup"><span data-stu-id="e017a-109">cmplEventID</span></span></p></td>
<td><p><span data-ttu-id="e017a-110">bigint, null이 아님</span><span class="sxs-lookup"><span data-stu-id="e017a-110">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="e017a-111">이벤트 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="e017a-111">Event ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e017a-112">entryDate</span><span class="sxs-lookup"><span data-stu-id="e017a-112">entryDate</span></span></p></td>
<td><p><span data-ttu-id="e017a-113">smalldatetime, null이 아님</span><span class="sxs-lookup"><span data-stu-id="e017a-113">smalldatetime, not null</span></span></p></td>
<td><p><span data-ttu-id="e017a-114">삽입 시간 (이 경우에는 항목이 자리 표시자 일 수 있으므로 cmplType = 9의 미래입니다).</span><span class="sxs-lookup"><span data-stu-id="e017a-114">Time of insertion (may be far in the future for cmplType=9 because the entry is just a placeholder in that case).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e017a-115">cmplType</span><span class="sxs-lookup"><span data-stu-id="e017a-115">cmplType</span></span></p></td>
<td><p><span data-ttu-id="e017a-116">int, null 아님</span><span class="sxs-lookup"><span data-stu-id="e017a-116">int, not null</span></span></p></td>
<td><p><span data-ttu-id="e017a-117">준수 이벤트 유형:</span><span class="sxs-lookup"><span data-stu-id="e017a-117">Type of compliance event:</span></span></p>
<ul>
<li><p><span data-ttu-id="e017a-118">1: 채팅</span><span class="sxs-lookup"><span data-stu-id="e017a-118">1: Chat</span></span></p></li>
<li><p><span data-ttu-id="e017a-119">2: 백 채팅</span><span class="sxs-lookup"><span data-stu-id="e017a-119">2: Backchat</span></span></p></li>
<li><p><span data-ttu-id="e017a-120">3: 파일 다운로드</span><span class="sxs-lookup"><span data-stu-id="e017a-120">3: File download</span></span></p></li>
<li><p><span data-ttu-id="e017a-121">4: 파일 업로드</span><span class="sxs-lookup"><span data-stu-id="e017a-121">4: File upload</span></span></p></li>
<li><p><span data-ttu-id="e017a-122">9: Provisional 파일 전송</span><span class="sxs-lookup"><span data-stu-id="e017a-122">9: Provisional file transfer</span></span></p></li>
<li><p><span data-ttu-id="e017a-123">10: 채팅 삭제 (바꾸기 사용)</span><span class="sxs-lookup"><span data-stu-id="e017a-123">10: Chat deletion (with replace)</span></span></p></li>
<li><p><span data-ttu-id="e017a-124">11: 채팅 제거</span><span class="sxs-lookup"><span data-stu-id="e017a-124">11: Chat purging</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e017a-125">cmplTime</span><span class="sxs-lookup"><span data-stu-id="e017a-125">cmplTime</span></span></p></td>
<td><p><span data-ttu-id="e017a-126">bigint, null이 아님</span><span class="sxs-lookup"><span data-stu-id="e017a-126">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="e017a-127">이벤트에 대 한 타임 스탬프입니다.</span><span class="sxs-lookup"><span data-stu-id="e017a-127">Time stamp for the event.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e017a-128">cmplChannelUri</span><span class="sxs-lookup"><span data-stu-id="e017a-128">cmplChannelUri</span></span></p></td>
<td><p><span data-ttu-id="e017a-129">nvarchar (255), null 아님</span><span class="sxs-lookup"><span data-stu-id="e017a-129">nvarchar (255), not null</span></span></p></td>
<td><p><span data-ttu-id="e017a-130">채널 URI (Uniform Resource Identifier)입니다.</span><span class="sxs-lookup"><span data-stu-id="e017a-130">Channel Uniform Resource Identifier (URI).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e017a-131">cmplChatID</span><span class="sxs-lookup"><span data-stu-id="e017a-131">cmplChatID</span></span></p></td>
<td><p><span data-ttu-id="e017a-132">bigint</span><span class="sxs-lookup"><span data-stu-id="e017a-132">bigint</span></span></p></td>
<td><p><span data-ttu-id="e017a-133">채팅 ID (chatId 테이블에 해당).</span><span class="sxs-lookup"><span data-stu-id="e017a-133">Chat ID (corresponding to tblChat.chatId table).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e017a-134">cmplUserID</span><span class="sxs-lookup"><span data-stu-id="e017a-134">cmplUserID</span></span></p></td>
<td><p><span data-ttu-id="e017a-135">int, null 아님</span><span class="sxs-lookup"><span data-stu-id="e017a-135">int, not null</span></span></p></td>
<td><p><span data-ttu-id="e017a-136">포스터의 Principal ID (tblPrincipal 테이블에 해당)</span><span class="sxs-lookup"><span data-stu-id="e017a-136">Principal ID of the poster (corresponding to tblPrincipal.prinID table).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e017a-137">cmplUserUri</span><span class="sxs-lookup"><span data-stu-id="e017a-137">cmplUserUri</span></span></p></td>
<td><p><span data-ttu-id="e017a-138">nvarchar (255), null 아님</span><span class="sxs-lookup"><span data-stu-id="e017a-138">nvarchar (255), not null</span></span></p></td>
<td><p><span data-ttu-id="e017a-139">사용자 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="e017a-139">User URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e017a-140">cmplMessage</span><span class="sxs-lookup"><span data-stu-id="e017a-140">cmplMessage</span></span></p></td>
<td><p><span data-ttu-id="e017a-141">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="e017a-141">nvarchar (max)</span></span></p></td>
<td><p><span data-ttu-id="e017a-142">메시지 (인코딩은 cmplType에 따라 다름)</span><span class="sxs-lookup"><span data-stu-id="e017a-142">Message (encoding depends on cmplType).</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="e017a-143">키</span><span class="sxs-lookup"><span data-stu-id="e017a-143">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e017a-144">열</span><span class="sxs-lookup"><span data-stu-id="e017a-144">Column</span></span></th>
<th><span data-ttu-id="e017a-145">설명</span><span class="sxs-lookup"><span data-stu-id="e017a-145">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e017a-146">cmplEventID</span><span class="sxs-lookup"><span data-stu-id="e017a-146">cmplEventID</span></span></p></td>
<td><p><span data-ttu-id="e017a-147">기본 키입니다.</span><span class="sxs-lookup"><span data-stu-id="e017a-147">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

