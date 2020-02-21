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
ms.openlocfilehash: 721932aa2929930b3da742355a46c5e2066c5c83
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42195131"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblroletype-in-lync-server-2013"></a><span data-ttu-id="dc02c-102">Lync Server 2013의 tblRoleType</span><span class="sxs-lookup"><span data-stu-id="dc02c-102">tblRoleType in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dc02c-103">_**마지막으로 수정 된 항목:** 2012-06-25_</span><span class="sxs-lookup"><span data-stu-id="dc02c-103">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="dc02c-104">tblRoleType은 역할 유형 및 연관된 권한 집합이 있는 정적 조회 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="dc02c-104">tblRoleType is a static lookup table with role types and their associated permission sets.</span></span>

### <a name="columns"></a><span data-ttu-id="dc02c-105">단</span><span class="sxs-lookup"><span data-stu-id="dc02c-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dc02c-106">열</span><span class="sxs-lookup"><span data-stu-id="dc02c-106">Column</span></span></th>
<th><span data-ttu-id="dc02c-107">형식</span><span class="sxs-lookup"><span data-stu-id="dc02c-107">Type</span></span></th>
<th><span data-ttu-id="dc02c-108">설명</span><span class="sxs-lookup"><span data-stu-id="dc02c-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dc02c-109">Tblroletype.rtypeid</span><span class="sxs-lookup"><span data-stu-id="dc02c-109">rtypeID</span></span></p></td>
<td><p><span data-ttu-id="dc02c-110">int, null이 아님</span><span class="sxs-lookup"><span data-stu-id="dc02c-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="dc02c-111">역할 유형 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="dc02c-111">Role type ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dc02c-112">rtypeDesc</span><span class="sxs-lookup"><span data-stu-id="dc02c-112">rtypeDesc</span></span></p></td>
<td><p><span data-ttu-id="dc02c-113">nvarchar(256), null이 아님</span><span class="sxs-lookup"><span data-stu-id="dc02c-113">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="dc02c-p101">역할 유형 설명입니다. 다음 네 가지 역할을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc02c-p101">Role type description. There are four available roles:</span></span></p>
<ul>
<li><p><span data-ttu-id="dc02c-116">구성원: 대화방 구성원</span><span class="sxs-lookup"><span data-stu-id="dc02c-116">Member: Chat room member</span></span></p></li>
<li><p><span data-ttu-id="dc02c-117">관리자: 대화방 관리자</span><span class="sxs-lookup"><span data-stu-id="dc02c-117">Manager: Chat room manager</span></span></p></li>
<li><p><span data-ttu-id="dc02c-118">음성: 강당 대화방의 발표자</span><span class="sxs-lookup"><span data-stu-id="dc02c-118">Voiced: Presenter for an auditorium chat room</span></span></p></li>
<li><p><span data-ttu-id="dc02c-119">작성자: 채팅방을 만들 수 있음</span><span class="sxs-lookup"><span data-stu-id="dc02c-119">Creator: Can create chat rooms</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dc02c-120">rtypeAllowedPermSet</span><span class="sxs-lookup"><span data-stu-id="dc02c-120">rtypeAllowedPermSet</span></span></p></td>
<td><p><span data-ttu-id="dc02c-121">bigint, null이 아님</span><span class="sxs-lookup"><span data-stu-id="dc02c-121">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="dc02c-p102">역할에 대해 설정된 권한입니다. 사용되는 비트는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="dc02c-p102">Permission set for the role. The used bits are:</span></span></p>
<ul>
<li><p><span data-ttu-id="dc02c-124">2: 역할이 노드를 관리할 수 있는 경우 True입니다.</span><span class="sxs-lookup"><span data-stu-id="dc02c-124">2: True if the role can manage nodes.</span></span></p></li>
<li><p><span data-ttu-id="dc02c-125">4: 역할이 자식 노드를 만들 수 있는 경우 True입니다.</span><span class="sxs-lookup"><span data-stu-id="dc02c-125">4: True if the role can create children nodes.</span></span></p></li>
<li><p><span data-ttu-id="dc02c-126">7: 역할이 대화방(또는 특정 범주의 자식 대화방)에 참가할 수 있는 경우 True입니다.</span><span class="sxs-lookup"><span data-stu-id="dc02c-126">7: True if the role can join a chat room (or children chat rooms of a category).</span></span></p></li>
<li><p><span data-ttu-id="dc02c-127">8: 역할이 대화방(또는 특정 범주의 자식 대화방)에서 채팅할 수 있는 경우 True입니다.</span><span class="sxs-lookup"><span data-stu-id="dc02c-127">8: True if the role can chat in a chat room (or in children chat rooms of a category).</span></span></p></li>
<li><p><span data-ttu-id="dc02c-128">10: 역할이 대화방에 참가하지 않은 경우에도 채팅 기록을 읽을 수 있는 경우 True입니다.</span><span class="sxs-lookup"><span data-stu-id="dc02c-128">10: True if the role can read chat history even when not joined to a chat room.</span></span></p></li>
<li><p><span data-ttu-id="dc02c-p103">11: 역할이 대화방을 볼 수 있는 경우 True입니다. 이 설정은 범위 및 표시 여부와 같은 요소로 세분화됩니다.</span><span class="sxs-lookup"><span data-stu-id="dc02c-p103">11: True if the role can see the chat room. (This is further refined by factors such as scope and visibility.)</span></span></p></li>
<li><p><span data-ttu-id="dc02c-131">12: 역할이 강당 대화방에서 채팅할 수 있는 경우 True입니다.</span><span class="sxs-lookup"><span data-stu-id="dc02c-131">12: True if the role can chat in an auditorium chat room.</span></span></p></li>
<li><p><span data-ttu-id="dc02c-132">13: 역할이 노드를 볼 때 표시 여부 규칙을 바이패스할 수 있는 경우 True입니다.</span><span class="sxs-lookup"><span data-stu-id="dc02c-132">13: True if the role can bypass visibility rules when viewing nodes.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="dc02c-133">키</span><span class="sxs-lookup"><span data-stu-id="dc02c-133">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dc02c-134">열</span><span class="sxs-lookup"><span data-stu-id="dc02c-134">Column</span></span></th>
<th><span data-ttu-id="dc02c-135">설명</span><span class="sxs-lookup"><span data-stu-id="dc02c-135">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dc02c-136">Tblroletype.rtypeid</span><span class="sxs-lookup"><span data-stu-id="dc02c-136">rtypeID</span></span></p></td>
<td><p><span data-ttu-id="dc02c-137">기본 키입니다.</span><span class="sxs-lookup"><span data-stu-id="dc02c-137">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

