---
title: 'Lync Server 2013: tblFileToken'
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
ms.openlocfilehash: 839086521c6e9054d1759943134b305c8205f59f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42025719"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblfiletoken-in-lync-server-2013"></a><span data-ttu-id="5d663-102">Lync Server 2013의 tblFileToken</span><span class="sxs-lookup"><span data-stu-id="5d663-102">tblFileToken in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5d663-103">_**마지막으로 수정 된 항목:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="5d663-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="5d663-104">tblFileToken에는 파일 전송 목적의 임시 토큰이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d663-104">tblFileToken contains temporary tokens for file transfer purposes.</span></span>

### <a name="columns"></a><span data-ttu-id="5d663-105">단</span><span class="sxs-lookup"><span data-stu-id="5d663-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5d663-106">열</span><span class="sxs-lookup"><span data-stu-id="5d663-106">Column</span></span></th>
<th><span data-ttu-id="5d663-107">형식</span><span class="sxs-lookup"><span data-stu-id="5d663-107">Type</span></span></th>
<th><span data-ttu-id="5d663-108">설명</span><span class="sxs-lookup"><span data-stu-id="5d663-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5d663-109">fileToken</span><span class="sxs-lookup"><span data-stu-id="5d663-109">fileToken</span></span></p></td>
<td><p><span data-ttu-id="5d663-110">nvarchar(50), null이 아님</span><span class="sxs-lookup"><span data-stu-id="5d663-110">nvarchar (50), not null</span></span></p></td>
<td><p><span data-ttu-id="5d663-111">고유한 토큰(GUID)입니다.</span><span class="sxs-lookup"><span data-stu-id="5d663-111">Unique token (a GUID).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d663-112">fileTokenUserID</span><span class="sxs-lookup"><span data-stu-id="5d663-112">fileTokenUserID</span></span></p></td>
<td><p><span data-ttu-id="5d663-113">int, null이 아님</span><span class="sxs-lookup"><span data-stu-id="5d663-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="5d663-114">파일을 전송 중인 사용자의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="5d663-114">ID of the principal that is transferring the file.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d663-115">fileTokenChannelID</span><span class="sxs-lookup"><span data-stu-id="5d663-115">fileTokenChannelID</span></span></p></td>
<td><p><span data-ttu-id="5d663-116">GUID, not null</span><span class="sxs-lookup"><span data-stu-id="5d663-116">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="5d663-117">대화방 노드의 GUID입니다.</span><span class="sxs-lookup"><span data-stu-id="5d663-117">GUID of the chat room node.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d663-118">fileTokenExpireDate</span><span class="sxs-lookup"><span data-stu-id="5d663-118">fileTokenExpireDate</span></span></p></td>
<td><p><span data-ttu-id="5d663-119">datetime, null이 아님</span><span class="sxs-lookup"><span data-stu-id="5d663-119">datetime, not null</span></span></p></td>
<td><p><span data-ttu-id="5d663-p101">만료 시간입니다. 고정되지 않은 한 토큰이 30분 후 만료됩니다(이 열의 다음 설명 참조).</span><span class="sxs-lookup"><span data-stu-id="5d663-p101">Expiration time. (Tokens expire after 30 minutes, unless pinned (see the following descriptions in this column).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d663-122">fileTokenComplianceFileUrl</span><span class="sxs-lookup"><span data-stu-id="5d663-122">fileTokenComplianceFileUrl</span></span></p></td>
<td><p><span data-ttu-id="5d663-123">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="5d663-123">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5d663-124">전송된 파일의 URL입니다(준수 서비스용).</span><span class="sxs-lookup"><span data-stu-id="5d663-124">URL of the transferred file (for Compliance service use).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d663-125">fileTokenComplianceThumbnailUrl</span><span class="sxs-lookup"><span data-stu-id="5d663-125">fileTokenComplianceThumbnailUrl</span></span></p></td>
<td><p><span data-ttu-id="5d663-126">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="5d663-126">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5d663-127">전송된 파일에 대한 축소판 그림의 URL입니다(준수 서비스용).</span><span class="sxs-lookup"><span data-stu-id="5d663-127">URL of the thumbnail for the transferred file (for Compliance service use).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d663-128">fileTokenComplianceTime</span><span class="sxs-lookup"><span data-stu-id="5d663-128">fileTokenComplianceTime</span></span></p></td>
<td><p><span data-ttu-id="5d663-129">datetime2</span><span class="sxs-lookup"><span data-stu-id="5d663-129">datetime2</span></span></p></td>
<td><p><span data-ttu-id="5d663-130">실제 파일 전송 작업의 타임스탬프입니다(준수 서비스용).</span><span class="sxs-lookup"><span data-stu-id="5d663-130">Timestamp for the actual file transfer operation (for Compliance service use).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d663-131">fileTokenComplianceIsUpload</span><span class="sxs-lookup"><span data-stu-id="5d663-131">fileTokenComplianceIsUpload</span></span></p></td>
<td><p><span data-ttu-id="5d663-132">비트만</span><span class="sxs-lookup"><span data-stu-id="5d663-132">bit</span></span></p></td>
<td><p><span data-ttu-id="5d663-133">업로드인 경우 True, 다운로드인 경우 False입니다(준수 서비스용).</span><span class="sxs-lookup"><span data-stu-id="5d663-133">True if upload; False if download (for Compliance service use).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d663-134">fileTokenCompliancePinned</span><span class="sxs-lookup"><span data-stu-id="5d663-134">fileTokenCompliancePinned</span></span></p></td>
<td><p><span data-ttu-id="5d663-135">bit, null이 아님</span><span class="sxs-lookup"><span data-stu-id="5d663-135">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="5d663-p102">토큰이 고정된 경우 True입니다. 준수 서비스가 여기에서 관련 필드를 검색할 수 있을 때까지 토큰을 테이블에 유지하기 위해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d663-p102">True if token is pinned. It’s used to keep the token in the table until Compliance service has a chance to retrieve the relevant fields from it.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="5d663-138">키</span><span class="sxs-lookup"><span data-stu-id="5d663-138">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5d663-139">열</span><span class="sxs-lookup"><span data-stu-id="5d663-139">Column</span></span></th>
<th><span data-ttu-id="5d663-140">설명</span><span class="sxs-lookup"><span data-stu-id="5d663-140">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5d663-141">fileToken</span><span class="sxs-lookup"><span data-stu-id="5d663-141">fileToken</span></span></p></td>
<td><p><span data-ttu-id="5d663-142">기본 키입니다.</span><span class="sxs-lookup"><span data-stu-id="5d663-142">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d663-143">fileTokenChannelID</span><span class="sxs-lookup"><span data-stu-id="5d663-143">fileTokenChannelID</span></span></p></td>
<td><p><span data-ttu-id="5d663-144">tblNode.nodeGuid 테이블에서 조회 기능이 있는 외래 키입니다.</span><span class="sxs-lookup"><span data-stu-id="5d663-144">Foreign key with lookup in tblNode.nodeGuid table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

