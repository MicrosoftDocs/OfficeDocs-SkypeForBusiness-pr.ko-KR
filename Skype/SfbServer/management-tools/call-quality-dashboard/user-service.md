---
title: CQD용 사용자 서비스
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: abd5c828-42dd-4f48-bf87-29993193cb3a
description: '요약: 통화 품질 대시보드에 대한 리포지토리 API의 일부인 사용자 서비스에 대해 자세히 알아보습니다. 통화 품질 대시보드는 비즈니스용 Skype 서버용 도구입니다.'
ms.openlocfilehash: d9f4b771a1bf5efeece4f8fb87195d8567f0426e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49803078"
---
# <a name="user-service-for-cqd"></a><span data-ttu-id="6f9bd-104">CQD용 사용자 서비스</span><span class="sxs-lookup"><span data-stu-id="6f9bd-104">User Service for CQD</span></span>
 
<span data-ttu-id="6f9bd-105">**요약:** 통화 품질 대시보드에 대한 리포지토리 API의 일부인 사용자 서비스에 대해 자세히 알아보습니다.</span><span class="sxs-lookup"><span data-stu-id="6f9bd-105">**Summary:** Learn about the User Service, which is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="6f9bd-106">통화 품질 대시보드는 비즈니스용 Skype 서버용 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="6f9bd-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="6f9bd-107">사용자 서비스는 통화 품질 대시보드에 대한 리포지토리 API의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="6f9bd-107">The User Service is part of the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="user-service"></a><span data-ttu-id="6f9bd-108">사용자 서비스</span><span class="sxs-lookup"><span data-stu-id="6f9bd-108">User Service</span></span>

<span data-ttu-id="6f9bd-109">리포지토리 API는 사용자 프로비전(새 사용자 계정 만들기)이 자동으로 암시적으로 수행되는 간소화된 사용자 관리 모델을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6f9bd-109">Repository API provides a simplified user management model where user provisioning (creating new user accounts) is automatic and implicit.</span></span> <span data-ttu-id="6f9bd-110">사용자가 리포지토리 API에 대해 처음으로 요청을 하면 리포지토리에서 새 사용자 레코드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6f9bd-110">When a user make a request against Repository API for the first time, the repository creates a new User record.</span></span> 
  
<span data-ttu-id="6f9bd-111">통화 품질 대시보드에서는 새 사용자에 대한 사용자 전용 항목도 자동으로 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6f9bd-111">Call Quality Dashboard also automatically creates a user dedicated items for the new user.</span></span> <span data-ttu-id="6f9bd-112">새 사용자 전용 항목은 시스템 사용자 항목의 완전한 복제본입니다.</span><span class="sxs-lookup"><span data-stu-id="6f9bd-112">The new user dedicated items are complete clones of system user's items.</span></span> <span data-ttu-id="6f9bd-113">이렇게 하면 사용자가 직접 사용자 지정을 시작할 수 있는 보고서 및 쿼리의 복사본으로 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f9bd-113">This way, users start with their own copies of Reports and Queries that they can immediately start customizing.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="6f9bd-114">통화 품질 대시보드를 사용하여 사용자는 언제든지 전용 항목을 다시 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f9bd-114">Using Call Quality Dashboard, users can reset their dedicated items anytime.</span></span> 
  
 <span data-ttu-id="6f9bd-115">**특수 사용자 ID**</span><span class="sxs-lookup"><span data-stu-id="6f9bd-115">**Special User IDs**</span></span>
  
<span data-ttu-id="6f9bd-116">리포지토리 API에는 특정 사용자를 지정하는 정수 값이 필요한 REST API URIS가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f9bd-116">Repository API includes REST API URIs that expects an integer value to specify a particular user.</span></span> <span data-ttu-id="6f9bd-117">예:  `https://<portal>/QoERepositoryService/repository/user/{userId}` .</span><span class="sxs-lookup"><span data-stu-id="6f9bd-117">Example:  `https://<portal>/QoERepositoryService/repository/user/{userId}`.</span></span> <span data-ttu-id="6f9bd-118">여기서 {userId}는 0, 1 등의 정수 값으로 대체해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f9bd-118">Here, {userId} should be replaced by an integer value such as 0, 1, etc.</span></span>
  
<span data-ttu-id="6f9bd-119">또한 리포지토리 API는 URIS의 {userId}에 두 개의 특수 사용자 ID를 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="6f9bd-119">Moreover, Repository API will accept two special user IDs at {userId} in URIs.</span></span>
  
-  <span data-ttu-id="6f9bd-120">*default*  - 현재 API와 상호 작용하고 있는 사용자를 나타내는 경우</span><span class="sxs-lookup"><span data-stu-id="6f9bd-120">*default*  - represents the user who is currently interacting with the API.</span></span> <span data-ttu-id="6f9bd-121">이렇게 하면 응용 프로그램에서 실제 사용자 ID 값을 추적하지 않고 현재 사용자의 콘텐츠에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f9bd-121">This allows applications to access current user's contents without keeping track of the actual user ID value.</span></span> <span data-ttu-id="6f9bd-122">예: `https://<portal>/QoERepositoryService/repository/user/default` .</span><span class="sxs-lookup"><span data-stu-id="6f9bd-122">Example: `https://<portal>/QoERepositoryService/repository/user/default`.</span></span>
    
-  <span data-ttu-id="6f9bd-123">*system*  - 시스템 사용자를 나타 내는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="6f9bd-123">*system*  - represents the system user.</span></span> <span data-ttu-id="6f9bd-124">이렇게 하면 응용 프로그램에서 실제 사용자 ID 값을 모르고 시스템 사용자 콘텐츠에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f9bd-124">This allows applications to access the system user's contents without knowing the actual user ID value.</span></span> <span data-ttu-id="6f9bd-125">예: `https://<portal>/QoERepositoryService/repository/user/system` .</span><span class="sxs-lookup"><span data-stu-id="6f9bd-125">Example: `https://<portal>/QoERepositoryService/repository/user/system`.</span></span>
    
<span data-ttu-id="6f9bd-126">달리 명시되지 않은 경우 URIS의 {userId}에서 특수 사용자 ID를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f9bd-126">Unless otherwise noted, the special user IDs can be used at {userId} in URIs.</span></span> 
  
<span data-ttu-id="6f9bd-127">REST 작업은 다음 표에 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f9bd-127">The REST operations are included in the following table.</span></span>
  
|<span data-ttu-id="6f9bd-128">**작업**</span><span class="sxs-lookup"><span data-stu-id="6f9bd-128">**Operation**</span></span>|<span data-ttu-id="6f9bd-129">**설명**</span><span class="sxs-lookup"><span data-stu-id="6f9bd-129">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="6f9bd-130">사용자 가져오기</span><span class="sxs-lookup"><span data-stu-id="6f9bd-130">Get Users</span></span>](get-users.md) <br/> |<span data-ttu-id="6f9bd-131">리포지토리에 있는 사용자 목록을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="6f9bd-131">Returns a list of users in the repository.</span></span>  <br/> |
|[<span data-ttu-id="6f9bd-132">사용자 가져오기</span><span class="sxs-lookup"><span data-stu-id="6f9bd-132">Get User</span></span>](get-user.md) <br/> |<span data-ttu-id="6f9bd-133">사용자 레코드를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="6f9bd-133">Returns a user record.</span></span>  <br/> |
   

