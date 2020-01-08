---
title: 'Lync Server 2013: tblComplianceParticipant'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblComplianceParticipant
ms:assetid: 5d7e0dea-74f7-46d1-badf-b94abc8f066d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558655(v=OCS.15)
ms:contentKeyID: 48184262
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e98b257552f728d0976df6331673f1f55d0dbdeb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979222"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblcomplianceparticipant-in-lync-server-2013"></a><span data-ttu-id="e3690-102">Lync Server 2013의 tblComplianceParticipant</span><span class="sxs-lookup"><span data-stu-id="e3690-102">tblComplianceParticipant in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e3690-103">_**마지막으로 수정한 주제:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="e3690-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="e3690-104">tblComplianceParticipant에는 채널당 현재 참가자와 서버 별로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3690-104">tblComplianceParticipant contains the current participants per channel and per server.</span></span>

### <a name="columns"></a><span data-ttu-id="e3690-105">열</span><span class="sxs-lookup"><span data-stu-id="e3690-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e3690-106">열</span><span class="sxs-lookup"><span data-stu-id="e3690-106">Column</span></span></th>
<th><span data-ttu-id="e3690-107">유형</span><span class="sxs-lookup"><span data-stu-id="e3690-107">Type</span></span></th>
<th><span data-ttu-id="e3690-108">설명</span><span class="sxs-lookup"><span data-stu-id="e3690-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e3690-109">channelUri</span><span class="sxs-lookup"><span data-stu-id="e3690-109">channelUri</span></span></p></td>
<td><p><span data-ttu-id="e3690-110">nvarchar (255), null 아님</span><span class="sxs-lookup"><span data-stu-id="e3690-110">nvarchar (255), not null</span></span></p></td>
<td><p><span data-ttu-id="e3690-111">채널 URI (Uniform Resource Identifier)입니다.</span><span class="sxs-lookup"><span data-stu-id="e3690-111">Channel Uniform Resource Identifier (URI).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3690-112">userId</span><span class="sxs-lookup"><span data-stu-id="e3690-112">userId</span></span></p></td>
<td><p><span data-ttu-id="e3690-113">int, null 아님</span><span class="sxs-lookup"><span data-stu-id="e3690-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="e3690-114">참가자의 사용자 ID (tblPrincipal 테이블에 해당)</span><span class="sxs-lookup"><span data-stu-id="e3690-114">Principal ID of the participant (corresponding to tblPrincipal.prinID table).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3690-115">에서 joinedAt</span><span class="sxs-lookup"><span data-stu-id="e3690-115">joinedAt</span></span></p></td>
<td><p><span data-ttu-id="e3690-116">bigint, null이 아님</span><span class="sxs-lookup"><span data-stu-id="e3690-116">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="e3690-117">참가 이벤트의 타임 스탬프입니다.</span><span class="sxs-lookup"><span data-stu-id="e3690-117">Time stamp of the joining event.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3690-118">partedAt</span><span class="sxs-lookup"><span data-stu-id="e3690-118">partedAt</span></span></p></td>
<td><p><span data-ttu-id="e3690-119">bigint</span><span class="sxs-lookup"><span data-stu-id="e3690-119">bigint</span></span></p></td>
<td><p><span data-ttu-id="e3690-120">참가자가 아직 참가 한 경우 Null입니다.</span><span class="sxs-lookup"><span data-stu-id="e3690-120">Null if participant is still joined.</span></span> <span data-ttu-id="e3690-121">Null이 아닌 경우 이벤트를 종료 하는 채널의 타임 스탬프입니다.</span><span class="sxs-lookup"><span data-stu-id="e3690-121">The time stamp of the channel leaving event if not null.</span></span></p>
<p><span data-ttu-id="e3690-122">이러한 항목은 모든 번역기가 이벤트를 처리할 때 결국 제거 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3690-122">These entries are eventually removed when all translators process the event.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3690-123">userUri</span><span class="sxs-lookup"><span data-stu-id="e3690-123">userUri</span></span></p></td>
<td><p><span data-ttu-id="e3690-124">nvarchar (255), null 아님</span><span class="sxs-lookup"><span data-stu-id="e3690-124">nvarchar(255), not null</span></span></p></td>
<td><p><span data-ttu-id="e3690-125">사용자 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="e3690-125">User URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3690-126">serverID</span><span class="sxs-lookup"><span data-stu-id="e3690-126">serverID</span></span></p></td>
<td><p><span data-ttu-id="e3690-127">int</span><span class="sxs-lookup"><span data-stu-id="e3690-127">int</span></span></p></td>
<td><p><span data-ttu-id="e3690-128">서버 id (tblServerIdentity 테이블에 해당)</span><span class="sxs-lookup"><span data-stu-id="e3690-128">Server identity (as in tblServerIdentity.serverID table).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3690-129">Session</span><span class="sxs-lookup"><span data-stu-id="e3690-129">sessionId</span></span></p></td>
<td><p><span data-ttu-id="e3690-130">bigint</span><span class="sxs-lookup"><span data-stu-id="e3690-130">bigint</span></span></p></td>
<td><p><span data-ttu-id="e3690-131">서버 세션.</span><span class="sxs-lookup"><span data-stu-id="e3690-131">Server session.</span></span> <span data-ttu-id="e3690-132">채팅 서비스를 시작할 때마다 생성 되는 난수입니다.</span><span class="sxs-lookup"><span data-stu-id="e3690-132">This is a random number generated each time a Chat service starts.</span></span> <span data-ttu-id="e3690-133">고아 참가자를 식별 하기 위해 세션을 구분 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3690-133">It is used to differentiate sessions for the purpose of identifying orphaned participants.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="e3690-134">키</span><span class="sxs-lookup"><span data-stu-id="e3690-134">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e3690-135">열</span><span class="sxs-lookup"><span data-stu-id="e3690-135">Column</span></span></th>
<th><span data-ttu-id="e3690-136">설명</span><span class="sxs-lookup"><span data-stu-id="e3690-136">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e3690-137">&lt;channelUri, userId, joinedAt&gt;</span><span class="sxs-lookup"><span data-stu-id="e3690-137">&lt;channelUri, userId, joinedAt&gt;</span></span></p></td>
<td><p><span data-ttu-id="e3690-138">기본 키입니다.</span><span class="sxs-lookup"><span data-stu-id="e3690-138">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

