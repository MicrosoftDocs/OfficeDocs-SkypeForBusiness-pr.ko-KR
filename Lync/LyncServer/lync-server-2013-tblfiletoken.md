---
title: 'Lync Server 2013: tblFileToken'
description: 'Lync Server 2013: tblFileToken.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblFileToken
ms:assetid: 49e7dd79-1607-443c-818a-88c160e4ed06
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558646(v=OCS.15)
ms:contentKeyID: 48184073
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9c0a0465bd769cff5c23c00a98f79e2346232175
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547634"
---
# <a name="tblfiletoken-in-lync-server-2013"></a><span data-ttu-id="1a27f-103">Lync Server 2013의 tblFileToken</span><span class="sxs-lookup"><span data-stu-id="1a27f-103">tblFileToken in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1a27f-104">_**마지막으로 수정 된 항목:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="1a27f-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="1a27f-105">tblFileToken에는 파일 전송 목적의 임시 토큰이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="1a27f-105">tblFileToken contains temporary tokens for file transfer purposes.</span></span>

### <a name="columns"></a><span data-ttu-id="1a27f-106">단</span><span class="sxs-lookup"><span data-stu-id="1a27f-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1a27f-107">열</span><span class="sxs-lookup"><span data-stu-id="1a27f-107">Column</span></span></th>
<th><span data-ttu-id="1a27f-108">유형</span><span class="sxs-lookup"><span data-stu-id="1a27f-108">Type</span></span></th>
<th><span data-ttu-id="1a27f-109">설명</span><span class="sxs-lookup"><span data-stu-id="1a27f-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1a27f-110">fileToken</span><span class="sxs-lookup"><span data-stu-id="1a27f-110">fileToken</span></span></p></td>
<td><p><span data-ttu-id="1a27f-111">nvarchar(50), null이 아님</span><span class="sxs-lookup"><span data-stu-id="1a27f-111">nvarchar (50), not null</span></span></p></td>
<td><p><span data-ttu-id="1a27f-112">고유한 토큰(GUID)입니다.</span><span class="sxs-lookup"><span data-stu-id="1a27f-112">Unique token (a GUID).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a27f-113">fileTokenUserID</span><span class="sxs-lookup"><span data-stu-id="1a27f-113">fileTokenUserID</span></span></p></td>
<td><p><span data-ttu-id="1a27f-114">int, null이 아님</span><span class="sxs-lookup"><span data-stu-id="1a27f-114">int, not null</span></span></p></td>
<td><p><span data-ttu-id="1a27f-115">파일을 전송 중인 사용자의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="1a27f-115">ID of the principal that is transferring the file.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1a27f-116">fileTokenChannelID</span><span class="sxs-lookup"><span data-stu-id="1a27f-116">fileTokenChannelID</span></span></p></td>
<td><p><span data-ttu-id="1a27f-117">GUID, not null</span><span class="sxs-lookup"><span data-stu-id="1a27f-117">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="1a27f-118">대화방 노드의 GUID입니다.</span><span class="sxs-lookup"><span data-stu-id="1a27f-118">GUID of the chat room node.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a27f-119">fileTokenExpireDate</span><span class="sxs-lookup"><span data-stu-id="1a27f-119">fileTokenExpireDate</span></span></p></td>
<td><p><span data-ttu-id="1a27f-120">datetime, null이 아님</span><span class="sxs-lookup"><span data-stu-id="1a27f-120">datetime, not null</span></span></p></td>
<td><p><span data-ttu-id="1a27f-p101">만료 시간입니다. 고정되지 않은 한 토큰이 30분 후 만료됩니다(이 열의 다음 설명 참조).</span><span class="sxs-lookup"><span data-stu-id="1a27f-p101">Expiration time. (Tokens expire after 30 minutes, unless pinned (see the following descriptions in this column).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1a27f-123">fileTokenComplianceFileUrl</span><span class="sxs-lookup"><span data-stu-id="1a27f-123">fileTokenComplianceFileUrl</span></span></p></td>
<td><p><span data-ttu-id="1a27f-124">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="1a27f-124">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="1a27f-125">전송된 파일의 URL입니다(준수 서비스용).</span><span class="sxs-lookup"><span data-stu-id="1a27f-125">URL of the transferred file (for Compliance service use).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a27f-126">fileTokenComplianceThumbnailUrl</span><span class="sxs-lookup"><span data-stu-id="1a27f-126">fileTokenComplianceThumbnailUrl</span></span></p></td>
<td><p><span data-ttu-id="1a27f-127">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="1a27f-127">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="1a27f-128">전송된 파일에 대한 축소판 그림의 URL입니다(준수 서비스용).</span><span class="sxs-lookup"><span data-stu-id="1a27f-128">URL of the thumbnail for the transferred file (for Compliance service use).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1a27f-129">fileTokenComplianceTime</span><span class="sxs-lookup"><span data-stu-id="1a27f-129">fileTokenComplianceTime</span></span></p></td>
<td><p><span data-ttu-id="1a27f-130">datetime2</span><span class="sxs-lookup"><span data-stu-id="1a27f-130">datetime2</span></span></p></td>
<td><p><span data-ttu-id="1a27f-131">실제 파일 전송 작업의 타임스탬프입니다(준수 서비스용).</span><span class="sxs-lookup"><span data-stu-id="1a27f-131">Timestamp for the actual file transfer operation (for Compliance service use).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a27f-132">fileTokenComplianceIsUpload</span><span class="sxs-lookup"><span data-stu-id="1a27f-132">fileTokenComplianceIsUpload</span></span></p></td>
<td><p><span data-ttu-id="1a27f-133">비트만</span><span class="sxs-lookup"><span data-stu-id="1a27f-133">bit</span></span></p></td>
<td><p><span data-ttu-id="1a27f-134">업로드인 경우 True, 다운로드인 경우 False입니다(준수 서비스용).</span><span class="sxs-lookup"><span data-stu-id="1a27f-134">True if upload; False if download (for Compliance service use).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1a27f-135">fileTokenCompliancePinned</span><span class="sxs-lookup"><span data-stu-id="1a27f-135">fileTokenCompliancePinned</span></span></p></td>
<td><p><span data-ttu-id="1a27f-136">bit, null이 아님</span><span class="sxs-lookup"><span data-stu-id="1a27f-136">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="1a27f-p102">토큰이 고정된 경우 True입니다. 준수 서비스가 여기에서 관련 필드를 검색할 수 있을 때까지 토큰을 테이블에 유지하기 위해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="1a27f-p102">True if token is pinned. It’s used to keep the token in the table until Compliance service has a chance to retrieve the relevant fields from it.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="1a27f-139">키</span><span class="sxs-lookup"><span data-stu-id="1a27f-139">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1a27f-140">열</span><span class="sxs-lookup"><span data-stu-id="1a27f-140">Column</span></span></th>
<th><span data-ttu-id="1a27f-141">설명</span><span class="sxs-lookup"><span data-stu-id="1a27f-141">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1a27f-142">fileToken</span><span class="sxs-lookup"><span data-stu-id="1a27f-142">fileToken</span></span></p></td>
<td><p><span data-ttu-id="1a27f-143">기본 키입니다.</span><span class="sxs-lookup"><span data-stu-id="1a27f-143">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a27f-144">fileTokenChannelID</span><span class="sxs-lookup"><span data-stu-id="1a27f-144">fileTokenChannelID</span></span></p></td>
<td><p><span data-ttu-id="1a27f-145">tblNode.nodeGuid 테이블에서 조회 기능이 있는 외래 키입니다.</span><span class="sxs-lookup"><span data-stu-id="1a27f-145">Foreign key with lookup in tblNode.nodeGuid table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

