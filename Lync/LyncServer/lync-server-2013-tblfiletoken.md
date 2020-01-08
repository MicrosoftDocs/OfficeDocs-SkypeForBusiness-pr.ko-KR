---
title: 'Lync Server 2013: tblFileToken'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblFileToken
ms:assetid: 49e7dd79-1607-443c-818a-88c160e4ed06
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558646(v=OCS.15)
ms:contentKeyID: 48184073
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9146c168e62bd0602a76cd77ab678c84ba5e44da
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983056"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblfiletoken-in-lync-server-2013"></a><span data-ttu-id="2c998-102">Lync Server 2013의 tblFileToken</span><span class="sxs-lookup"><span data-stu-id="2c998-102">tblFileToken in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2c998-103">_**마지막으로 수정한 주제:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="2c998-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="2c998-104">tblFileToken에는 파일 전송 목적에 대 한 임시 토큰이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c998-104">tblFileToken contains temporary tokens for file transfer purposes.</span></span>

### <a name="columns"></a><span data-ttu-id="2c998-105">열</span><span class="sxs-lookup"><span data-stu-id="2c998-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2c998-106">열</span><span class="sxs-lookup"><span data-stu-id="2c998-106">Column</span></span></th>
<th><span data-ttu-id="2c998-107">유형</span><span class="sxs-lookup"><span data-stu-id="2c998-107">Type</span></span></th>
<th><span data-ttu-id="2c998-108">설명</span><span class="sxs-lookup"><span data-stu-id="2c998-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2c998-109">fileToken</span><span class="sxs-lookup"><span data-stu-id="2c998-109">fileToken</span></span></p></td>
<td><p><span data-ttu-id="2c998-110">nvarchar (50), null 아님</span><span class="sxs-lookup"><span data-stu-id="2c998-110">nvarchar (50), not null</span></span></p></td>
<td><p><span data-ttu-id="2c998-111">고유 토큰 (GUID).</span><span class="sxs-lookup"><span data-stu-id="2c998-111">Unique token (a GUID).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2c998-112">fileTokenUserID</span><span class="sxs-lookup"><span data-stu-id="2c998-112">fileTokenUserID</span></span></p></td>
<td><p><span data-ttu-id="2c998-113">int, null 아님</span><span class="sxs-lookup"><span data-stu-id="2c998-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="2c998-114">파일을 전송 하는 주체의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="2c998-114">ID of the principal that is transferring the file.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2c998-115">fileTokenChannelID</span><span class="sxs-lookup"><span data-stu-id="2c998-115">fileTokenChannelID</span></span></p></td>
<td><p><span data-ttu-id="2c998-116">GUID (null 아님)</span><span class="sxs-lookup"><span data-stu-id="2c998-116">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="2c998-117">채팅방 노드의 GUID입니다.</span><span class="sxs-lookup"><span data-stu-id="2c998-117">GUID of the chat room node.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2c998-118">fileTokenExpireDate</span><span class="sxs-lookup"><span data-stu-id="2c998-118">fileTokenExpireDate</span></span></p></td>
<td><p><span data-ttu-id="2c998-119">datetime, null 아님</span><span class="sxs-lookup"><span data-stu-id="2c998-119">datetime, not null</span></span></p></td>
<td><p><span data-ttu-id="2c998-120">만료 시간.</span><span class="sxs-lookup"><span data-stu-id="2c998-120">Expiration time.</span></span> <span data-ttu-id="2c998-121">(고정 되지 않는 한 30 분 후에 토큰이 만료 됩니다 (이 칼럼의 다음 설명 참조).</span><span class="sxs-lookup"><span data-stu-id="2c998-121">(Tokens expire after 30 minutes, unless pinned (see the following descriptions in this column).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2c998-122">fileTokenComplianceFileUrl</span><span class="sxs-lookup"><span data-stu-id="2c998-122">fileTokenComplianceFileUrl</span></span></p></td>
<td><p><span data-ttu-id="2c998-123">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="2c998-123">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="2c998-124">전송 된 파일의 URL입니다 (준수 서비스 사용).</span><span class="sxs-lookup"><span data-stu-id="2c998-124">URL of the transferred file (for Compliance service use).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2c998-125">fileTokenComplianceThumbnailUrl</span><span class="sxs-lookup"><span data-stu-id="2c998-125">fileTokenComplianceThumbnailUrl</span></span></p></td>
<td><p><span data-ttu-id="2c998-126">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="2c998-126">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="2c998-127">전송 된 파일의 축소판 그림 URL입니다 (준수 서비스 사용).</span><span class="sxs-lookup"><span data-stu-id="2c998-127">URL of the thumbnail for the transferred file (for Compliance service use).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2c998-128">fileTokenComplianceTime</span><span class="sxs-lookup"><span data-stu-id="2c998-128">fileTokenComplianceTime</span></span></p></td>
<td><p><span data-ttu-id="2c998-129">datetime2</span><span class="sxs-lookup"><span data-stu-id="2c998-129">datetime2</span></span></p></td>
<td><p><span data-ttu-id="2c998-130">실제 파일 전송 작업 (준수 서비스 사용)에 대 한 타임 스탬프입니다.</span><span class="sxs-lookup"><span data-stu-id="2c998-130">Timestamp for the actual file transfer operation (for Compliance service use).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2c998-131">fileTokenComplianceIsUpload</span><span class="sxs-lookup"><span data-stu-id="2c998-131">fileTokenComplianceIsUpload</span></span></p></td>
<td><p><span data-ttu-id="2c998-132">다소</span><span class="sxs-lookup"><span data-stu-id="2c998-132">bit</span></span></p></td>
<td><p><span data-ttu-id="2c998-133">업로드 하는 경우 True False 인 경우 (준수 서비스 사용)</span><span class="sxs-lookup"><span data-stu-id="2c998-133">True if upload; False if download (for Compliance service use).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2c998-134">fileTokenCompliancePinned</span><span class="sxs-lookup"><span data-stu-id="2c998-134">fileTokenCompliancePinned</span></span></p></td>
<td><p><span data-ttu-id="2c998-135">bit, null이 아님</span><span class="sxs-lookup"><span data-stu-id="2c998-135">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="2c998-136">토큰이 고정 되어 있으면 True입니다.</span><span class="sxs-lookup"><span data-stu-id="2c998-136">True if token is pinned.</span></span> <span data-ttu-id="2c998-137">준수 서비스에서 관련 필드를 검색할 기회가 생길 때까지 테이블에 토큰을 유지 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c998-137">It’s used to keep the token in the table until Compliance service has a chance to retrieve the relevant fields from it.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="2c998-138">핵심</span><span class="sxs-lookup"><span data-stu-id="2c998-138">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2c998-139">열</span><span class="sxs-lookup"><span data-stu-id="2c998-139">Column</span></span></th>
<th><span data-ttu-id="2c998-140">설명</span><span class="sxs-lookup"><span data-stu-id="2c998-140">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2c998-141">fileToken</span><span class="sxs-lookup"><span data-stu-id="2c998-141">fileToken</span></span></p></td>
<td><p><span data-ttu-id="2c998-142">기본 키입니다.</span><span class="sxs-lookup"><span data-stu-id="2c998-142">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2c998-143">fileTokenChannelID</span><span class="sxs-lookup"><span data-stu-id="2c998-143">fileTokenChannelID</span></span></p></td>
<td><p><span data-ttu-id="2c998-144">TblNode. nodeGuid 테이블에 조회를 포함 하는 외래 키입니다.</span><span class="sxs-lookup"><span data-stu-id="2c998-144">Foreign key with lookup in tblNode.nodeGuid table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

