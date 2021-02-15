---
title: tblRoleType
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 1eac3a54-656a-40ac-b771-edfc64d6e34b
description: tblRoleType은 역할 유형 및 연관된 권한 집합이 있는 정적 조회 테이블입니다.
ms.openlocfilehash: c440463d822b908a89c84eb9c85b70e9daf442be
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831528"
---
# <a name="tblroletype"></a><span data-ttu-id="5e341-103">tblRoleType</span><span class="sxs-lookup"><span data-stu-id="5e341-103">tblRoleType</span></span>
 
<span data-ttu-id="5e341-104">tblRoleType은 역할 유형 및 연관된 권한 집합이 있는 정적 조회 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="5e341-104">tblRoleType is a static lookup table with role types and their associated permission sets.</span></span>
  
<span data-ttu-id="5e341-105">**열**</span><span class="sxs-lookup"><span data-stu-id="5e341-105">**Columns**</span></span>

|<span data-ttu-id="5e341-106">**열**</span><span class="sxs-lookup"><span data-stu-id="5e341-106">**Column**</span></span>|<span data-ttu-id="5e341-107">**유형**</span><span class="sxs-lookup"><span data-stu-id="5e341-107">**Type**</span></span>|<span data-ttu-id="5e341-108">**설명**</span><span class="sxs-lookup"><span data-stu-id="5e341-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="5e341-109">rtypeID</span><span class="sxs-lookup"><span data-stu-id="5e341-109">rtypeID</span></span>  <br/> |<span data-ttu-id="5e341-110">int, null이 아님</span><span class="sxs-lookup"><span data-stu-id="5e341-110">int, not null</span></span>  <br/> |<span data-ttu-id="5e341-111">역할 유형 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="5e341-111">Role type ID.</span></span>  <br/> |
|<span data-ttu-id="5e341-112">rtypeDesc</span><span class="sxs-lookup"><span data-stu-id="5e341-112">rtypeDesc</span></span>  <br/> |<span data-ttu-id="5e341-113">nvarchar(256), null이 아님</span><span class="sxs-lookup"><span data-stu-id="5e341-113">nvarchar (256), not null</span></span>  <br/> | <span data-ttu-id="5e341-p101">역할 유형 설명입니다. 다음 네 가지 역할을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e341-p101">Role type description. There are four available roles:</span></span> <br/>  <span data-ttu-id="5e341-116">구성원: 대화방 구성원</span><span class="sxs-lookup"><span data-stu-id="5e341-116">Member: Chat room member</span></span> <br/>  <span data-ttu-id="5e341-117">관리자: 대화방 관리자</span><span class="sxs-lookup"><span data-stu-id="5e341-117">Manager: Chat room manager</span></span> <br/>  <span data-ttu-id="5e341-118">음성: 강당 대화방의 발표자</span><span class="sxs-lookup"><span data-stu-id="5e341-118">Voiced: Presenter for an auditorium chat room</span></span> <br/>  <span data-ttu-id="5e341-119">작성자: 채팅방을 만들 수 있음</span><span class="sxs-lookup"><span data-stu-id="5e341-119">Creator: Can create chat rooms</span></span> <br/> |
|<span data-ttu-id="5e341-120">rtypeAllowedPermSet</span><span class="sxs-lookup"><span data-stu-id="5e341-120">rtypeAllowedPermSet</span></span>  <br/> |<span data-ttu-id="5e341-121">bigint, null이 아님</span><span class="sxs-lookup"><span data-stu-id="5e341-121">bigint, not null</span></span>  <br/> | <span data-ttu-id="5e341-p102">역할에 대해 설정된 권한입니다. 사용되는 비트는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="5e341-p102">Permission set for the role. The used bits are:</span></span> <br/>  <span data-ttu-id="5e341-124">2: 역할이 노드를 관리할 수 있는 경우 True입니다.</span><span class="sxs-lookup"><span data-stu-id="5e341-124">2: True if the role can manage nodes.</span></span> <br/>  <span data-ttu-id="5e341-125">4: 역할이 자식 노드를 만들 수 있는 경우 True입니다.</span><span class="sxs-lookup"><span data-stu-id="5e341-125">4: True if the role can create children nodes.</span></span> <br/>  <span data-ttu-id="5e341-126">7: 역할이 대화방(또는 특정 범주의 자식 대화방)에 참가할 수 있는 경우 True입니다.</span><span class="sxs-lookup"><span data-stu-id="5e341-126">7: True if the role can join a chat room (or children chat rooms of a category).</span></span> <br/>  <span data-ttu-id="5e341-127">8: 역할이 대화방(또는 특정 범주의 자식 대화방)에서 채팅할 수 있는 경우 True입니다.</span><span class="sxs-lookup"><span data-stu-id="5e341-127">8: True if the role can chat in a chat room (or in children chat rooms of a category).</span></span> <br/>  <span data-ttu-id="5e341-128">10: 역할이 대화방에 참가하지 않은 경우에도 채팅 기록을 읽을 수 있는 경우 True입니다.</span><span class="sxs-lookup"><span data-stu-id="5e341-128">10: True if the role can read chat history even when not joined to a chat room.</span></span> <br/>  <span data-ttu-id="5e341-p103">11: 역할이 대화방을 볼 수 있는 경우 True입니다. 이 설정은 범위 및 표시 여부와 같은 요소로 세분화됩니다.</span><span class="sxs-lookup"><span data-stu-id="5e341-p103">11: True if the role can see the chat room. (This is further refined by factors such as scope and visibility.)</span></span> <br/>  <span data-ttu-id="5e341-131">12: 역할이 강당 대화방에서 채팅할 수 있는 경우 True입니다.</span><span class="sxs-lookup"><span data-stu-id="5e341-131">12: True if the role can chat in an auditorium chat room.</span></span> <br/>  <span data-ttu-id="5e341-132">13: 역할이 노드를 볼 때 표시 여부 규칙을 바이패스할 수 있는 경우 True입니다.</span><span class="sxs-lookup"><span data-stu-id="5e341-132">13: True if the role can bypass visibility rules when viewing nodes.</span></span> <br/> |
   
<span data-ttu-id="5e341-133">**키**</span><span class="sxs-lookup"><span data-stu-id="5e341-133">**Key**</span></span>

|<span data-ttu-id="5e341-134">**열**</span><span class="sxs-lookup"><span data-stu-id="5e341-134">**Column**</span></span>|<span data-ttu-id="5e341-135">**설명**</span><span class="sxs-lookup"><span data-stu-id="5e341-135">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="5e341-136">rtypeID</span><span class="sxs-lookup"><span data-stu-id="5e341-136">rtypeID</span></span>  <br/> |<span data-ttu-id="5e341-137">기본 키입니다.</span><span class="sxs-lookup"><span data-stu-id="5e341-137">Primary key.</span></span>  <br/> |
   

