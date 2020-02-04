---
title: 'Lync Server 2013: tblRoleType'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblRoleType
ms:assetid: 1eac3a54-656a-40ac-b771-edfc64d6e34b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558623(v=OCS.15)
ms:contentKeyID: 48183577
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ba6b5041453b0965fafc12ada2be62ec42316f89
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731188"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblroletype-in-lync-server-2013"></a><span data-ttu-id="ac67e-102">Lync Server 2013의 tblRoleType</span><span class="sxs-lookup"><span data-stu-id="ac67e-102">tblRoleType in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ac67e-103">_**마지막으로 수정한 주제:** 2012-06-25_</span><span class="sxs-lookup"><span data-stu-id="ac67e-103">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="ac67e-104">tblRoleType는 역할 유형 및 연결 된 사용 권한 집합을 포함 하는 정적 조회 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="ac67e-104">tblRoleType is a static lookup table with role types and their associated permission sets.</span></span>

### <a name="columns"></a><span data-ttu-id="ac67e-105">열</span><span class="sxs-lookup"><span data-stu-id="ac67e-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ac67e-106">열</span><span class="sxs-lookup"><span data-stu-id="ac67e-106">Column</span></span></th>
<th><span data-ttu-id="ac67e-107">유형</span><span class="sxs-lookup"><span data-stu-id="ac67e-107">Type</span></span></th>
<th><span data-ttu-id="ac67e-108">설명</span><span class="sxs-lookup"><span data-stu-id="ac67e-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ac67e-109">rtypeID</span><span class="sxs-lookup"><span data-stu-id="ac67e-109">rtypeID</span></span></p></td>
<td><p><span data-ttu-id="ac67e-110">int, null 아님</span><span class="sxs-lookup"><span data-stu-id="ac67e-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="ac67e-111">역할 유형 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="ac67e-111">Role type ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ac67e-112">rtypeDesc</span><span class="sxs-lookup"><span data-stu-id="ac67e-112">rtypeDesc</span></span></p></td>
<td><p><span data-ttu-id="ac67e-113">nvarchar (256), null 아님</span><span class="sxs-lookup"><span data-stu-id="ac67e-113">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="ac67e-114">역할 유형 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="ac67e-114">Role type description.</span></span> <span data-ttu-id="ac67e-115">사용할 수 있는 역할은 네 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac67e-115">There are four available roles:</span></span></p>
<ul>
<li><p><span data-ttu-id="ac67e-116">회원: 채팅방 구성원</span><span class="sxs-lookup"><span data-stu-id="ac67e-116">Member: Chat room member</span></span></p></li>
<li><p><span data-ttu-id="ac67e-117">관리자: 채팅방 관리자</span><span class="sxs-lookup"><span data-stu-id="ac67e-117">Manager: Chat room manager</span></span></p></li>
<li><p><span data-ttu-id="ac67e-118">않지만: auditorium 채팅방의 발표자</span><span class="sxs-lookup"><span data-stu-id="ac67e-118">Voiced: Presenter for an auditorium chat room</span></span></p></li>
<li><p><span data-ttu-id="ac67e-119">작성자: 채팅방을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac67e-119">Creator: Can create chat rooms</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ac67e-120">rtypeAllowedPermSet</span><span class="sxs-lookup"><span data-stu-id="ac67e-120">rtypeAllowedPermSet</span></span></p></td>
<td><p><span data-ttu-id="ac67e-121">bigint, null이 아님</span><span class="sxs-lookup"><span data-stu-id="ac67e-121">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="ac67e-122">역할에 대 한 사용 권한 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="ac67e-122">Permission set for the role.</span></span> <span data-ttu-id="ac67e-123">사용 되는 비트는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ac67e-123">The used bits are:</span></span></p>
<ul>
<li><p><span data-ttu-id="ac67e-124">2: 역할이 노드를 관리할 수 있는 경우 True입니다.</span><span class="sxs-lookup"><span data-stu-id="ac67e-124">2: True if the role can manage nodes.</span></span></p></li>
<li><p><span data-ttu-id="ac67e-125">4: 역할이 자식 노드를 만들 수 있는 경우 True입니다.</span><span class="sxs-lookup"><span data-stu-id="ac67e-125">4: True if the role can create children nodes.</span></span></p></li>
<li><p><span data-ttu-id="ac67e-126">7: 역할이 채팅방에 참가할 수 있으면 True이 고, 그렇지 않은 경우에는 범주에 있는 채팅방을 어린이에 게 보세요.</span><span class="sxs-lookup"><span data-stu-id="ac67e-126">7: True if the role can join a chat room (or children chat rooms of a category).</span></span></p></li>
<li><p><span data-ttu-id="ac67e-127">8: 역할이 채팅방에서 채팅을 할 수 있으면 True이 고, 그렇지 않은 경우에는 범주의 채팅방을 어린이에 게 보세요.</span><span class="sxs-lookup"><span data-stu-id="ac67e-127">8: True if the role can chat in a chat room (or in children chat rooms of a category).</span></span></p></li>
<li><p><span data-ttu-id="ac67e-128">10: 채팅방에 참가 하지 않은 경우에도 역할이 채팅 기록을 읽을 수 있는 경우 True입니다.</span><span class="sxs-lookup"><span data-stu-id="ac67e-128">10: True if the role can read chat history even when not joined to a chat room.</span></span></p></li>
<li><p><span data-ttu-id="ac67e-129">11: 역할이 채팅방을 볼 수 있으면 True입니다.</span><span class="sxs-lookup"><span data-stu-id="ac67e-129">11: True if the role can see the chat room.</span></span> <span data-ttu-id="ac67e-130">(범위 및 표시 유형 등의 요인에 따라 구체화 됩니다.)</span><span class="sxs-lookup"><span data-stu-id="ac67e-130">(This is further refined by factors such as scope and visibility.)</span></span></p></li>
<li><p><span data-ttu-id="ac67e-131">12: 역할이 auditorium 채팅방에서 채팅을 할 수 있는 경우 True입니다.</span><span class="sxs-lookup"><span data-stu-id="ac67e-131">12: True if the role can chat in an auditorium chat room.</span></span></p></li>
<li><p><span data-ttu-id="ac67e-132">13: 역할이 노드를 볼 때 표시 규칙을 무시할 수 있는 경우 True입니다.</span><span class="sxs-lookup"><span data-stu-id="ac67e-132">13: True if the role can bypass visibility rules when viewing nodes.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="ac67e-133">키</span><span class="sxs-lookup"><span data-stu-id="ac67e-133">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ac67e-134">열</span><span class="sxs-lookup"><span data-stu-id="ac67e-134">Column</span></span></th>
<th><span data-ttu-id="ac67e-135">설명</span><span class="sxs-lookup"><span data-stu-id="ac67e-135">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ac67e-136">rtypeID</span><span class="sxs-lookup"><span data-stu-id="ac67e-136">rtypeID</span></span></p></td>
<td><p><span data-ttu-id="ac67e-137">기본 키입니다.</span><span class="sxs-lookup"><span data-stu-id="ac67e-137">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

