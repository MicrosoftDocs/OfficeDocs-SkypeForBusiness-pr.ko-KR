---
title: CQD에 대 한 사용자 서비스
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: abd5c828-42dd-4f48-bf87-29993193cb3a
description: '요약: 통화 품질 대시보드의 리포지토리 API의 일부인 사용자 서비스에 대해 알아봅니다. 통화 품질 대시보드는 비즈니스용 Skype 서버용 도구입니다.'
ms.openlocfilehash: 6e0a6a58be98469458a8c8e7063402ff6477c35f
ms.sourcegitcommit: 208321bb45f7fb228757b9958a13f7e0bca91687
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/25/2019
ms.locfileid: "36197834"
---
# <a name="user-service-for-cqd"></a><span data-ttu-id="06728-104">CQD에 대 한 사용자 서비스</span><span class="sxs-lookup"><span data-stu-id="06728-104">User Service for CQD</span></span>
 
<span data-ttu-id="06728-105">**요약:** 통화 품질 대시보드의 리포지토리 API의 일부인 사용자 서비스에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="06728-105">**Summary:** Learn about the User Service, which is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="06728-106">통화 품질 대시보드는 비즈니스용 Skype 서버용 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="06728-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="06728-107">사용자 서비스는 통화 품질 대시보드의 리포지토리 API의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="06728-107">The User Service is part of the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="user-service"></a><span data-ttu-id="06728-108">사용자 서비스</span><span class="sxs-lookup"><span data-stu-id="06728-108">User Service</span></span>

<span data-ttu-id="06728-109">리포지토리 API는 사용자가 프로 비전 (새 사용자 계정 만들기)이 자동으로 암시적이 고 암시적인 간단한 사용자 관리 모델을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="06728-109">Repository API provides a simplified user management model where user provisioning (creating new user accounts) is automatic and implicit.</span></span> <span data-ttu-id="06728-110">사용자가 처음으로 리포지토리 API에 대 한 요청을 하면 리포지토리가 새 사용자 레코드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="06728-110">When a user make a request against Repository API for the first time, the repository creates a new User record.</span></span> 
  
<span data-ttu-id="06728-111">또한 통화 품질 대시보드는 새 사용자에 대 한 사용자 전용 항목을 자동으로 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="06728-111">Call Quality Dashboard also automatically creates a user dedicated items for the new user.</span></span> <span data-ttu-id="06728-112">새 사용자 전용 항목이 시스템 사용자 항목의 전체 복제본입니다.</span><span class="sxs-lookup"><span data-stu-id="06728-112">The new user dedicated items are complete clones of system user's items.</span></span> <span data-ttu-id="06728-113">이렇게 하면 사용자가 즉시 사용자 지정을 시작할 수 있는 고유한 보고서 복사본과 쿼리를 사용 하 여 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="06728-113">This way, users start with their own copies of Reports and Queries that they can immediately start customizing.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="06728-114">통화 품질 대시보드를 사용 하 여 사용자는 언제 든 지 전용 항목을 다시 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06728-114">Using Call Quality Dashboard, users can reset their dedicated items anytime.</span></span> 
  
 <span data-ttu-id="06728-115">**특수 사용자 Id**</span><span class="sxs-lookup"><span data-stu-id="06728-115">**Special User IDs**</span></span>
  
<span data-ttu-id="06728-116">리포지토리 API에는 정수 값이 특정 사용자를 지정 하는 데 필요한 REST API Uri가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06728-116">Repository API includes REST API URIs that expects an integer value to specify a particular user.</span></span> <span data-ttu-id="06728-117">예: `https://<portal>/QoERepositoryService/repository/user/{userId}`.</span><span class="sxs-lookup"><span data-stu-id="06728-117">Example:  `https://<portal>/QoERepositoryService/repository/user/{userId}`.</span></span> <span data-ttu-id="06728-118">여기에서 {userId}는 0, 1 등의 정수 값으로 바꿔야 합니다.</span><span class="sxs-lookup"><span data-stu-id="06728-118">Here, {userId} should be replaced by an integer value such as 0, 1, etc.</span></span>
  
<span data-ttu-id="06728-119">또한 리포지토리 API는 Uri의 {userId}에서 두 가지 특별 한 사용자 Id를 받아들입니다.</span><span class="sxs-lookup"><span data-stu-id="06728-119">Moreover, Repository API will accept two special user IDs at {userId} in URIs.</span></span>
  
-  <span data-ttu-id="06728-120">*default* -현재 API와 상호 작용 하 고 있는 사용자를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="06728-120">*default*  - represents the user who is currently interacting with the API.</span></span> <span data-ttu-id="06728-121">이렇게 하면 실제 사용자 ID 값을 추적 하지 않고 응용 프로그램이 현재 사용자의 콘텐츠에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06728-121">This allows applications to access current user's contents without keeping track of the actual user ID value.</span></span> <span data-ttu-id="06728-122">예: `https://<portal>/QoERepositoryService/repository/user/default`.</span><span class="sxs-lookup"><span data-stu-id="06728-122">Example: `https://<portal>/QoERepositoryService/repository/user/default`.</span></span>
    
-  <span data-ttu-id="06728-123">*시스템* -시스템 사용자를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="06728-123">*system*  - represents the system user.</span></span> <span data-ttu-id="06728-124">이렇게 하면 응용 프로그램에서 실제 사용자 ID 값을 몰라도 시스템 사용자의 콘텐츠에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06728-124">This allows applications to access the system user's contents without knowing the actual user ID value.</span></span> <span data-ttu-id="06728-125">예: `https://<portal>/QoERepositoryService/repository/user/system`.</span><span class="sxs-lookup"><span data-stu-id="06728-125">Example: `https://<portal>/QoERepositoryService/repository/user/system`.</span></span>
    
<span data-ttu-id="06728-126">다른 언급이 없는 한, Uri의 {userId}에서 특수 사용자 Id를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06728-126">Unless otherwise noted, the special user IDs can be used at {userId} in URIs.</span></span> 
  
<span data-ttu-id="06728-127">미삭 작업은 다음 표에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06728-127">The REST operations are included in the following table.</span></span>
  
|<span data-ttu-id="06728-128">**작업**</span><span class="sxs-lookup"><span data-stu-id="06728-128">**Operation**</span></span>|<span data-ttu-id="06728-129">**설명**</span><span class="sxs-lookup"><span data-stu-id="06728-129">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="06728-130">사용자 가져오기</span><span class="sxs-lookup"><span data-stu-id="06728-130">Get Users</span></span>](get-users.md) <br/> |<span data-ttu-id="06728-131">저장소의 사용자 목록을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="06728-131">Returns a list of users in the repository.</span></span>  <br/> |
|[<span data-ttu-id="06728-132">사용자 가져오기</span><span class="sxs-lookup"><span data-stu-id="06728-132">Get User</span></span>](get-user.md) <br/> |<span data-ttu-id="06728-133">사용자 레코드를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="06728-133">Returns a user record.</span></span>  <br/> |
   

