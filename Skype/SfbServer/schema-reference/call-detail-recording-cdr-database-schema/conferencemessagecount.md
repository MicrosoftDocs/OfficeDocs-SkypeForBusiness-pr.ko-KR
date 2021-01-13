---
title: 비즈니스용 Skype 서버의 ConferenceMessageCount 테이블
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
ms.assetid: 78569dbf-5217-42fa-ba1a-4380f56e2a3d
description: 이 표의 각 레코드는 한 IM 회의에서 한 사용자를 나타내며 해당 사용자가 보낸 메시지 수를 포함합니다. 각 회의는 이 표의 여러 레코드로 표시됩니다. 각 사용자에 대해 하나의 레코드.
ms.openlocfilehash: b931b45915fc12fb01ea36f81bee62f36914e903
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813278"
---
# <a name="conferencemessagecount-table-in-skype-for-business-server-2015"></a><span data-ttu-id="e618e-104">비즈니스용 Skype 서버의 ConferenceMessageCount 테이블</span><span class="sxs-lookup"><span data-stu-id="e618e-104">ConferenceMessageCount table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="e618e-105">이 표의 각 레코드는 한 IM 회의에서 한 사용자를 나타내며 해당 사용자가 보낸 메시지 수를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="e618e-105">Each record in this table represents one user in one IM conference and includes the number of messages sent by that user.</span></span> <span data-ttu-id="e618e-106">각 회의는 이 표의 여러 레코드로 표시됩니다. 각 사용자에 대한 하나의 레코드.</span><span class="sxs-lookup"><span data-stu-id="e618e-106">Each conference is represented by multiple records in this table; one record for each user.</span></span>
  
|<span data-ttu-id="e618e-107">**열**</span><span class="sxs-lookup"><span data-stu-id="e618e-107">**Column**</span></span>|<span data-ttu-id="e618e-108">**데이터 형식**</span><span class="sxs-lookup"><span data-stu-id="e618e-108">**Data Type**</span></span>|<span data-ttu-id="e618e-109">**키/인덱스**</span><span class="sxs-lookup"><span data-stu-id="e618e-109">**Key/Index**</span></span>|<span data-ttu-id="e618e-110">**세부 정보**</span><span class="sxs-lookup"><span data-stu-id="e618e-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e618e-111">**SessionIdTime**</span><span class="sxs-lookup"><span data-stu-id="e618e-111">**SessionIdTime**</span></span> <br/> |<span data-ttu-id="e618e-112">datetime</span><span class="sxs-lookup"><span data-stu-id="e618e-112">datetime</span></span>  <br/> |<span data-ttu-id="e618e-113">Primary, Foreign</span><span class="sxs-lookup"><span data-stu-id="e618e-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="e618e-114">회의 인스턴스의 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="e618e-114">Time of conference instance.</span></span> <span data-ttu-id="e618e-115">**SessionIdSeq와** 함께 회의 인스턴스를 고유하게 식별하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="e618e-115">Used in conjunction with **SessionIdSeq** to uniquely identify a conference instance.</span></span> <span data-ttu-id="e618e-116">자세한 내용은 [비즈니스용 Skype 서버 2015의 Conferences](conferences.md) 테이블을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e618e-116">See the [Conferences table in Skype for Business Server 2015](conferences.md) for more information.</span></span> <br/> |
|<span data-ttu-id="e618e-117">**SessionIdSeq**</span><span class="sxs-lookup"><span data-stu-id="e618e-117">**SessionIdSeq**</span></span> <br/> |<span data-ttu-id="e618e-118">int</span><span class="sxs-lookup"><span data-stu-id="e618e-118">int</span></span>  <br/> |<span data-ttu-id="e618e-119">Primary, Foreign</span><span class="sxs-lookup"><span data-stu-id="e618e-119">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="e618e-120">회의 인스턴스를 식별하기 위한 ID 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="e618e-120">ID number to identify the conference instance.</span></span> <span data-ttu-id="e618e-121">**SessionIdTime과** 함께 회의 인스턴스를 고유하게 식별하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="e618e-121">Used in conjunction with **SessionIdTime** to uniquely identify a conference instance.</span></span> <span data-ttu-id="e618e-122">자세한 내용은 [비즈니스용 Skype 서버 2015의 Conferences](conferences.md) 테이블을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e618e-122">See the [Conferences table in Skype for Business Server 2015](conferences.md) for more information.</span></span> <br/> |
|<span data-ttu-id="e618e-123">**UserId**</span><span class="sxs-lookup"><span data-stu-id="e618e-123">**UserId**</span></span> <br/> |<span data-ttu-id="e618e-124">int</span><span class="sxs-lookup"><span data-stu-id="e618e-124">int</span></span>  <br/> |<span data-ttu-id="e618e-125">외계인</span><span class="sxs-lookup"><span data-stu-id="e618e-125">Foreign</span></span>  <br/> |<span data-ttu-id="e618e-126">Users 테이블에서 참조되는 이 사용자를 식별하는 [고유 번호입니다.](users.md)</span><span class="sxs-lookup"><span data-stu-id="e618e-126">Unique number identifying this user, referenced from the [Users table](users.md).</span></span>  <br/> |
|<span data-ttu-id="e618e-127">**MessageCount**</span><span class="sxs-lookup"><span data-stu-id="e618e-127">**MessageCount**</span></span> <br/> |<span data-ttu-id="e618e-128">smallint</span><span class="sxs-lookup"><span data-stu-id="e618e-128">smallint</span></span>  <br/> | <br/> |<span data-ttu-id="e618e-129">이 회의 중에 이 사용자가 보낸 메시지 수입니다.</span><span class="sxs-lookup"><span data-stu-id="e618e-129">The number of messages sent by this user during this conference.</span></span>  <br/> |
   

