---
title: 'Lync Server 2013: tblComplianceData'
description: 'Lync Server 2013: tblComplianceData.'
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
ms.openlocfilehash: 3c597d67054303de2753182b37419f68051d3af8
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568104"
---
# <a name="tblcompliancedata-in-lync-server-2013"></a><span data-ttu-id="931e8-103">Lync Server 2013의 tblComplianceData</span><span class="sxs-lookup"><span data-stu-id="931e8-103">tblComplianceData in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="931e8-104">_**마지막으로 수정 된 항목:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="931e8-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="931e8-105">tblComplianceData에는 준수 어댑터에서 아직 처리되지 않은 준수 이벤트가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="931e8-105">tblComplianceData contains the compliance events that have not been processed by the compliance adapter yet.</span></span>

### <a name="columns"></a><span data-ttu-id="931e8-106">단</span><span class="sxs-lookup"><span data-stu-id="931e8-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="931e8-107">열</span><span class="sxs-lookup"><span data-stu-id="931e8-107">Column</span></span></th>
<th><span data-ttu-id="931e8-108">유형</span><span class="sxs-lookup"><span data-stu-id="931e8-108">Type</span></span></th>
<th><span data-ttu-id="931e8-109">설명</span><span class="sxs-lookup"><span data-stu-id="931e8-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="931e8-110">Tblcompliancedata.cmpleventid</span><span class="sxs-lookup"><span data-stu-id="931e8-110">cmplEventID</span></span></p></td>
<td><p><span data-ttu-id="931e8-111">bigint, null이 아님</span><span class="sxs-lookup"><span data-stu-id="931e8-111">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="931e8-112">이벤트 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="931e8-112">Event ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="931e8-113">entryDate</span><span class="sxs-lookup"><span data-stu-id="931e8-113">entryDate</span></span></p></td>
<td><p><span data-ttu-id="931e8-114">smalldatetime, null이 아님</span><span class="sxs-lookup"><span data-stu-id="931e8-114">smalldatetime, not null</span></span></p></td>
<td><p><span data-ttu-id="931e8-115">삽입 시간(cmplType=9의 경우에는 항목이 단순히 자리 표시자이므로 오랜 시간 후일 수 있음)</span><span class="sxs-lookup"><span data-stu-id="931e8-115">Time of insertion (may be far in the future for cmplType=9 because the entry is just a placeholder in that case).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="931e8-116">cmplType</span><span class="sxs-lookup"><span data-stu-id="931e8-116">cmplType</span></span></p></td>
<td><p><span data-ttu-id="931e8-117">int, null이 아님</span><span class="sxs-lookup"><span data-stu-id="931e8-117">int, not null</span></span></p></td>
<td><p><span data-ttu-id="931e8-118">준수 이벤트 유형:</span><span class="sxs-lookup"><span data-stu-id="931e8-118">Type of compliance event:</span></span></p>
<ul>
<li><p><span data-ttu-id="931e8-119">1: 채팅</span><span class="sxs-lookup"><span data-stu-id="931e8-119">1: Chat</span></span></p></li>
<li><p><span data-ttu-id="931e8-120">2: 백채트</span><span class="sxs-lookup"><span data-stu-id="931e8-120">2: Backchat</span></span></p></li>
<li><p><span data-ttu-id="931e8-121">3: 파일 다운로드</span><span class="sxs-lookup"><span data-stu-id="931e8-121">3: File download</span></span></p></li>
<li><p><span data-ttu-id="931e8-122">4: 파일 업로드</span><span class="sxs-lookup"><span data-stu-id="931e8-122">4: File upload</span></span></p></li>
<li><p><span data-ttu-id="931e8-123">9: 임시 파일 전송</span><span class="sxs-lookup"><span data-stu-id="931e8-123">9: Provisional file transfer</span></span></p></li>
<li><p><span data-ttu-id="931e8-124">10: 채팅 삭제(바꾸기 포함)</span><span class="sxs-lookup"><span data-stu-id="931e8-124">10: Chat deletion (with replace)</span></span></p></li>
<li><p><span data-ttu-id="931e8-125">11: 채팅 삭제</span><span class="sxs-lookup"><span data-stu-id="931e8-125">11: Chat purging</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="931e8-126">cmplTime</span><span class="sxs-lookup"><span data-stu-id="931e8-126">cmplTime</span></span></p></td>
<td><p><span data-ttu-id="931e8-127">bigint, null이 아님</span><span class="sxs-lookup"><span data-stu-id="931e8-127">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="931e8-128">이벤트의 타임스탬프입니다.</span><span class="sxs-lookup"><span data-stu-id="931e8-128">Time stamp for the event.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="931e8-129">cmplChannelUri</span><span class="sxs-lookup"><span data-stu-id="931e8-129">cmplChannelUri</span></span></p></td>
<td><p><span data-ttu-id="931e8-130">nvarchar(255), null이 아님</span><span class="sxs-lookup"><span data-stu-id="931e8-130">nvarchar (255), not null</span></span></p></td>
<td><p><span data-ttu-id="931e8-131">채널 URI(Uniform Resource Identifier)입니다.</span><span class="sxs-lookup"><span data-stu-id="931e8-131">Channel Uniform Resource Identifier (URI).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="931e8-132">cmplChatID</span><span class="sxs-lookup"><span data-stu-id="931e8-132">cmplChatID</span></span></p></td>
<td><p><span data-ttu-id="931e8-133">bigint</span><span class="sxs-lookup"><span data-stu-id="931e8-133">bigint</span></span></p></td>
<td><p><span data-ttu-id="931e8-134">채팅 ID(tblChat.chatId 테이블에 해당됨)</span><span class="sxs-lookup"><span data-stu-id="931e8-134">Chat ID (corresponding to tblChat.chatId table).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="931e8-135">cmplUserID</span><span class="sxs-lookup"><span data-stu-id="931e8-135">cmplUserID</span></span></p></td>
<td><p><span data-ttu-id="931e8-136">int, null이 아님</span><span class="sxs-lookup"><span data-stu-id="931e8-136">int, not null</span></span></p></td>
<td><p><span data-ttu-id="931e8-137">게시자의 사용자 ID(tblPrincipal.prinID 테이블에 해당됨)</span><span class="sxs-lookup"><span data-stu-id="931e8-137">Principal ID of the poster (corresponding to tblPrincipal.prinID table).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="931e8-138">cmplUserUri</span><span class="sxs-lookup"><span data-stu-id="931e8-138">cmplUserUri</span></span></p></td>
<td><p><span data-ttu-id="931e8-139">nvarchar(255), null이 아님</span><span class="sxs-lookup"><span data-stu-id="931e8-139">nvarchar (255), not null</span></span></p></td>
<td><p><span data-ttu-id="931e8-140">사용자 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="931e8-140">User URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="931e8-141">cmplMessage</span><span class="sxs-lookup"><span data-stu-id="931e8-141">cmplMessage</span></span></p></td>
<td><p><span data-ttu-id="931e8-142">nvarchar(max)</span><span class="sxs-lookup"><span data-stu-id="931e8-142">nvarchar (max)</span></span></p></td>
<td><p><span data-ttu-id="931e8-143">메시지(인코딩은 cmplType에 따라 다름)</span><span class="sxs-lookup"><span data-stu-id="931e8-143">Message (encoding depends on cmplType).</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="931e8-144">키</span><span class="sxs-lookup"><span data-stu-id="931e8-144">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="931e8-145">열</span><span class="sxs-lookup"><span data-stu-id="931e8-145">Column</span></span></th>
<th><span data-ttu-id="931e8-146">설명</span><span class="sxs-lookup"><span data-stu-id="931e8-146">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="931e8-147">Tblcompliancedata.cmpleventid</span><span class="sxs-lookup"><span data-stu-id="931e8-147">cmplEventID</span></span></p></td>
<td><p><span data-ttu-id="931e8-148">기본 키입니다.</span><span class="sxs-lookup"><span data-stu-id="931e8-148">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

