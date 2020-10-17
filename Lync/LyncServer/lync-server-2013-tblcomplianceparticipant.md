---
title: 'Lync Server 2013: tblComplianceParticipant'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblComplianceParticipant
ms:assetid: 5d7e0dea-74f7-46d1-badf-b94abc8f066d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558655(v=OCS.15)
ms:contentKeyID: 48184262
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0d6ce992f7a36bd5ce731f26dcb5dbfac0e2acae
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48509435"
---
# <a name="tblcomplianceparticipant-in-lync-server-2013"></a><span data-ttu-id="04a2d-102">Lync Server 2013의 tblComplianceParticipant</span><span class="sxs-lookup"><span data-stu-id="04a2d-102">tblComplianceParticipant in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="04a2d-103">_**마지막으로 수정 된 항목:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="04a2d-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="04a2d-104">tblComplianceParticipant에는 채널 및 서버별 현재 참가자가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="04a2d-104">tblComplianceParticipant contains the current participants per channel and per server.</span></span>

### <a name="columns"></a><span data-ttu-id="04a2d-105">단</span><span class="sxs-lookup"><span data-stu-id="04a2d-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="04a2d-106">열</span><span class="sxs-lookup"><span data-stu-id="04a2d-106">Column</span></span></th>
<th><span data-ttu-id="04a2d-107">유형</span><span class="sxs-lookup"><span data-stu-id="04a2d-107">Type</span></span></th>
<th><span data-ttu-id="04a2d-108">설명</span><span class="sxs-lookup"><span data-stu-id="04a2d-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="04a2d-109">channelUri</span><span class="sxs-lookup"><span data-stu-id="04a2d-109">channelUri</span></span></p></td>
<td><p><span data-ttu-id="04a2d-110">nvarchar(255), null이 아님</span><span class="sxs-lookup"><span data-stu-id="04a2d-110">nvarchar (255), not null</span></span></p></td>
<td><p><span data-ttu-id="04a2d-111">채널 URI(Uniform Resource Identifier)입니다.</span><span class="sxs-lookup"><span data-stu-id="04a2d-111">Channel Uniform Resource Identifier (URI).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="04a2d-112">userId</span><span class="sxs-lookup"><span data-stu-id="04a2d-112">userId</span></span></p></td>
<td><p><span data-ttu-id="04a2d-113">int, null이 아님</span><span class="sxs-lookup"><span data-stu-id="04a2d-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="04a2d-114">참가자의 계정 ID(tblPrincipal.prinID 테이블에 해당됨)입니다.</span><span class="sxs-lookup"><span data-stu-id="04a2d-114">Principal ID of the participant (corresponding to tblPrincipal.prinID table).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="04a2d-115">에서 joinedAt</span><span class="sxs-lookup"><span data-stu-id="04a2d-115">joinedAt</span></span></p></td>
<td><p><span data-ttu-id="04a2d-116">bigint, null이 아님</span><span class="sxs-lookup"><span data-stu-id="04a2d-116">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="04a2d-117">참가 이벤트의 타임스탬프입니다.</span><span class="sxs-lookup"><span data-stu-id="04a2d-117">Time stamp of the joining event.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="04a2d-118">partedAt</span><span class="sxs-lookup"><span data-stu-id="04a2d-118">partedAt</span></span></p></td>
<td><p><span data-ttu-id="04a2d-119">bigint</span><span class="sxs-lookup"><span data-stu-id="04a2d-119">bigint</span></span></p></td>
<td><p><span data-ttu-id="04a2d-p101">참가자가 아직 참가된 상태이면 Null입니다. Null이 아닌 경우 채널 나가기 이벤트의 타임스탬프입니다.</span><span class="sxs-lookup"><span data-stu-id="04a2d-p101">Null if participant is still joined. The time stamp of the channel leaving event if not null.</span></span></p>
<p><span data-ttu-id="04a2d-122">모든 변환기에서 이벤트를 처리하면 이러한 항목이 결국 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="04a2d-122">These entries are eventually removed when all translators process the event.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="04a2d-123">변수와 useruri</span><span class="sxs-lookup"><span data-stu-id="04a2d-123">userUri</span></span></p></td>
<td><p><span data-ttu-id="04a2d-124">nvarchar(255), null이 아님</span><span class="sxs-lookup"><span data-stu-id="04a2d-124">nvarchar(255), not null</span></span></p></td>
<td><p><span data-ttu-id="04a2d-125">사용자 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="04a2d-125">User URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="04a2d-126">serverID</span><span class="sxs-lookup"><span data-stu-id="04a2d-126">serverID</span></span></p></td>
<td><p><span data-ttu-id="04a2d-127">int</span><span class="sxs-lookup"><span data-stu-id="04a2d-127">int</span></span></p></td>
<td><p><span data-ttu-id="04a2d-128">서버 ID(tblServerIdentity.serverID 테이블에 해당됨)입니다.</span><span class="sxs-lookup"><span data-stu-id="04a2d-128">Server identity (as in tblServerIdentity.serverID table).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="04a2d-129">Id</span><span class="sxs-lookup"><span data-stu-id="04a2d-129">sessionId</span></span></p></td>
<td><p><span data-ttu-id="04a2d-130">bigint</span><span class="sxs-lookup"><span data-stu-id="04a2d-130">bigint</span></span></p></td>
<td><p><span data-ttu-id="04a2d-p102">서버 세션입니다. 이 값은 채팅 서비스가 시작할 때마다 생성되는 임의의 숫자입니다. 고립된 참가자를 식별하기 위한 목적으로 세션을 구분하기 위해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="04a2d-p102">Server session. This is a random number generated each time a Chat service starts. It is used to differentiate sessions for the purpose of identifying orphaned participants.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="04a2d-134">키</span><span class="sxs-lookup"><span data-stu-id="04a2d-134">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="04a2d-135">열</span><span class="sxs-lookup"><span data-stu-id="04a2d-135">Column</span></span></th>
<th><span data-ttu-id="04a2d-136">설명</span><span class="sxs-lookup"><span data-stu-id="04a2d-136">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="04a2d-137">&lt;channelUri, userId, joinedAt&gt;</span><span class="sxs-lookup"><span data-stu-id="04a2d-137">&lt;channelUri, userId, joinedAt&gt;</span></span></p></td>
<td><p><span data-ttu-id="04a2d-138">기본 키입니다.</span><span class="sxs-lookup"><span data-stu-id="04a2d-138">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

