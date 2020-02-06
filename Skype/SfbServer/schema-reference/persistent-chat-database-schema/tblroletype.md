---
title: tblRoleType
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 1eac3a54-656a-40ac-b771-edfc64d6e34b
description: tblRoleType는 역할 유형 및 연결 된 사용 권한 집합을 포함 하는 정적 조회 테이블입니다.
ms.openlocfilehash: 888628c1aca01e90694ed946569a81b1b7394b95
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812906"
---
# <a name="tblroletype"></a><span data-ttu-id="4d9ef-103">tblRoleType</span><span class="sxs-lookup"><span data-stu-id="4d9ef-103">tblRoleType</span></span>
 
<span data-ttu-id="4d9ef-104">tblRoleType는 역할 유형 및 연결 된 사용 권한 집합을 포함 하는 정적 조회 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="4d9ef-104">tblRoleType is a static lookup table with role types and their associated permission sets.</span></span>
  
<span data-ttu-id="4d9ef-105">**열**</span><span class="sxs-lookup"><span data-stu-id="4d9ef-105">**Columns**</span></span>

|<span data-ttu-id="4d9ef-106">**열**</span><span class="sxs-lookup"><span data-stu-id="4d9ef-106">**Column**</span></span>|<span data-ttu-id="4d9ef-107">**유형**</span><span class="sxs-lookup"><span data-stu-id="4d9ef-107">**Type**</span></span>|<span data-ttu-id="4d9ef-108">**설명**</span><span class="sxs-lookup"><span data-stu-id="4d9ef-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="4d9ef-109">rtypeID</span><span class="sxs-lookup"><span data-stu-id="4d9ef-109">rtypeID</span></span>  <br/> |<span data-ttu-id="4d9ef-110">int, null 아님</span><span class="sxs-lookup"><span data-stu-id="4d9ef-110">int, not null</span></span>  <br/> |<span data-ttu-id="4d9ef-111">역할 유형 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="4d9ef-111">Role type ID.</span></span>  <br/> |
|<span data-ttu-id="4d9ef-112">rtypeDesc</span><span class="sxs-lookup"><span data-stu-id="4d9ef-112">rtypeDesc</span></span>  <br/> |<span data-ttu-id="4d9ef-113">nvarchar (256), null 아님</span><span class="sxs-lookup"><span data-stu-id="4d9ef-113">nvarchar (256), not null</span></span>  <br/> | <span data-ttu-id="4d9ef-114">역할 유형 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="4d9ef-114">Role type description.</span></span> <span data-ttu-id="4d9ef-115">사용할 수 있는 역할은 네 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d9ef-115">There are four available roles:</span></span> <br/>  <span data-ttu-id="4d9ef-116">회원: 채팅방 구성원</span><span class="sxs-lookup"><span data-stu-id="4d9ef-116">Member: Chat room member</span></span> <br/>  <span data-ttu-id="4d9ef-117">관리자: 채팅방 관리자</span><span class="sxs-lookup"><span data-stu-id="4d9ef-117">Manager: Chat room manager</span></span> <br/>  <span data-ttu-id="4d9ef-118">않지만: auditorium 채팅방의 발표자</span><span class="sxs-lookup"><span data-stu-id="4d9ef-118">Voiced: Presenter for an auditorium chat room</span></span> <br/>  <span data-ttu-id="4d9ef-119">작성자: 채팅방을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d9ef-119">Creator: Can create chat rooms</span></span> <br/> |
|<span data-ttu-id="4d9ef-120">rtypeAllowedPermSet</span><span class="sxs-lookup"><span data-stu-id="4d9ef-120">rtypeAllowedPermSet</span></span>  <br/> |<span data-ttu-id="4d9ef-121">bigint, null이 아님</span><span class="sxs-lookup"><span data-stu-id="4d9ef-121">bigint, not null</span></span>  <br/> | <span data-ttu-id="4d9ef-122">역할에 대 한 사용 권한 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="4d9ef-122">Permission set for the role.</span></span> <span data-ttu-id="4d9ef-123">사용 되는 비트는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4d9ef-123">The used bits are:</span></span> <br/>  <span data-ttu-id="4d9ef-124">2: 역할이 노드를 관리할 수 있는 경우 True입니다.</span><span class="sxs-lookup"><span data-stu-id="4d9ef-124">2: True if the role can manage nodes.</span></span> <br/>  <span data-ttu-id="4d9ef-125">4: 역할이 자식 노드를 만들 수 있는 경우 True입니다.</span><span class="sxs-lookup"><span data-stu-id="4d9ef-125">4: True if the role can create children nodes.</span></span> <br/>  <span data-ttu-id="4d9ef-126">7: 역할이 채팅방에 참가할 수 있으면 True이 고, 그렇지 않은 경우에는 범주에 있는 채팅방을 어린이에 게 보세요.</span><span class="sxs-lookup"><span data-stu-id="4d9ef-126">7: True if the role can join a chat room (or children chat rooms of a category).</span></span> <br/>  <span data-ttu-id="4d9ef-127">8: 역할이 채팅방에서 채팅을 할 수 있으면 True이 고, 그렇지 않은 경우에는 범주의 채팅방을 어린이에 게 보세요.</span><span class="sxs-lookup"><span data-stu-id="4d9ef-127">8: True if the role can chat in a chat room (or in children chat rooms of a category).</span></span> <br/>  <span data-ttu-id="4d9ef-128">10: 채팅방에 참가 하지 않은 경우에도 역할이 채팅 기록을 읽을 수 있는 경우 True입니다.</span><span class="sxs-lookup"><span data-stu-id="4d9ef-128">10: True if the role can read chat history even when not joined to a chat room.</span></span> <br/>  <span data-ttu-id="4d9ef-129">11: 역할이 채팅방을 볼 수 있으면 True입니다.</span><span class="sxs-lookup"><span data-stu-id="4d9ef-129">11: True if the role can see the chat room.</span></span> <span data-ttu-id="4d9ef-130">(범위 및 표시 유형 등의 요인에 따라 구체화 됩니다.)</span><span class="sxs-lookup"><span data-stu-id="4d9ef-130">(This is further refined by factors such as scope and visibility.)</span></span> <br/>  <span data-ttu-id="4d9ef-131">12: 역할이 auditorium 채팅방에서 채팅을 할 수 있는 경우 True입니다.</span><span class="sxs-lookup"><span data-stu-id="4d9ef-131">12: True if the role can chat in an auditorium chat room.</span></span> <br/>  <span data-ttu-id="4d9ef-132">13: 역할이 노드를 볼 때 표시 규칙을 무시할 수 있는 경우 True입니다.</span><span class="sxs-lookup"><span data-stu-id="4d9ef-132">13: True if the role can bypass visibility rules when viewing nodes.</span></span> <br/> |
   
<span data-ttu-id="4d9ef-133">**키**</span><span class="sxs-lookup"><span data-stu-id="4d9ef-133">**Key**</span></span>

|<span data-ttu-id="4d9ef-134">**열**</span><span class="sxs-lookup"><span data-stu-id="4d9ef-134">**Column**</span></span>|<span data-ttu-id="4d9ef-135">**설명**</span><span class="sxs-lookup"><span data-stu-id="4d9ef-135">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="4d9ef-136">rtypeID</span><span class="sxs-lookup"><span data-stu-id="4d9ef-136">rtypeID</span></span>  <br/> |<span data-ttu-id="4d9ef-137">기본 키입니다.</span><span class="sxs-lookup"><span data-stu-id="4d9ef-137">Primary key.</span></span>  <br/> |
   

