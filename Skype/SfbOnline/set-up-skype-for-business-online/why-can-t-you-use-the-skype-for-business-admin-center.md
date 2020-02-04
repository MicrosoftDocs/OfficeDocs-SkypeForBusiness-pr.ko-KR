---
title: 지금 비즈니스용 Skype Online 관리 센터를 사용할 수 없는 이유는 무엇 인가요?
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: c182d564-1674-4491-b1d9-3e0cb657d4cc
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
f1.keywords:
- ms.lync.lac.TenantInMigration
ms.custom:
- Setup
description: '비즈니스용 Skype 관리 센터 및 다른 Microsoft 데이터 센터로 서비스를 마이그레이션할 때 사용할 수 없는 기능에 대해 알아봅니다. '
ms.openlocfilehash: 3987675a5c054671be7a1d52227cf1f3161f2300
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41692733"
---
# <a name="why-cant-i-use-the-skype-for-business-online-admin-center-right-now"></a><span data-ttu-id="fd66f-103">지금 비즈니스용 Skype Online 관리 센터를 사용할 수 없는 이유는 무엇 인가요?</span><span class="sxs-lookup"><span data-stu-id="fd66f-103">Why can't I use the Skype for Business Online admin center right now?</span></span>

<span data-ttu-id="fd66f-104">작업을 완료할 수 없을 때 문제가 발생 하는 것을 알고 있으므로 여기에서 어떤 일이 발생 하 고 있는지에 대해 설명 하 고 대기 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="fd66f-104">We know it's frustrating when you can't get your work done, so we're going to explain what's happening here and why it'll be worth the wait.</span></span> 
  
<span data-ttu-id="fd66f-105">먼저 다음은 기술 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="fd66f-105">First, here's the technical explanation:</span></span>
  
<span data-ttu-id="fd66f-106">저희는 사용자와 조직 설정에 대 한 비즈니스용 Skype Online 서비스를 더 가까운 다른 Microsoft 데이터 센터로 마이그레이션 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd66f-106">We're migrating your Skype for Business Online service (meaning your users and organizational settings) to another Microsoft datacenter that's closer to you.</span></span> <span data-ttu-id="fd66f-107">이렇게 하면 서비스를 개선 하 고 대기 시간을 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd66f-107">This will improve your service and reduce latency.</span></span> 
  
<span data-ttu-id="fd66f-108">자세한 기술 정보는 [데이터 이동 중 및 이후를]( https://go.microsoft.com/fwlink/?LinkId=526418)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="fd66f-108">For more technical details, see [During and after your data move]( https://go.microsoft.com/fwlink/?LinkId=526418).</span></span>
  
## <a name="ok-so-what-does-that-mean"></a><span data-ttu-id="fd66f-109">그 의미는 무엇 인가요?</span><span class="sxs-lookup"><span data-stu-id="fd66f-109">OK, so what does that mean?</span></span>

<span data-ttu-id="fd66f-110">먼저 몇 가지 조건을 분석 하겠습니다.</span><span class="sxs-lookup"><span data-stu-id="fd66f-110">First, let's break down a few terms.</span></span>
  
- <span data-ttu-id="fd66f-111">**데이터 센터** 파일 및 전자 메일 메시지와 같이 Office 365 조직의 정보가 저장 되는 실제 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="fd66f-111">**Data center** This is the physical location where the information from your Office 365 organization is stored, such as your files and email messages.</span></span> <span data-ttu-id="fd66f-112">Office 365 데이터 센터에 대 한 자세한 내용을 확인 하려면[이 문서를 참조](https://www.microsoft.com/online/legal/v2/?docid=25)하세요.</span><span class="sxs-lookup"><span data-stu-id="fd66f-112">If you really want to dig in to what Office 365 datacenters are, check out[this article](https://www.microsoft.com/online/legal/v2/?docid=25).</span></span>
    
- <span data-ttu-id="fd66f-113">**마이그레이션** 이는 "이동"과 거의 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd66f-113">**Migrating** This is pretty much the same as "moving."</span></span> <span data-ttu-id="fd66f-114">이 경우에는 한 데이터 센터의 비즈니스용 Skype Online 사용자 및 설정을 사용자에 게 더 가까이 배치 하 여 서비스를 개선 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="fd66f-114">In this case, it means we're moving your Skype for Business Online users and settings from one datacenter to another that's closer to you to improve your service.</span></span>
    
- <span data-ttu-id="fd66f-115">**대기 시간** Microsoft 365 관리 센터에 액세스 하 고 설정을 변경한 다음 해당 변경 내용을 저장 하는 데 걸리는 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="fd66f-115">**Latency** This is amount of time it takes you to access the Microsoft 365 admin center, make a settings change, and then save those changes.</span></span>
    
- <span data-ttu-id="fd66f-116">**상관 관계 ID** 방금 보낸 메시지에이를 표시 했을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd66f-116">**Correlation ID** You might have seen this listed in the message you just came from.</span></span> <span data-ttu-id="fd66f-117">이 정보는 Microsoft 지원 엔지니어가 오류 문제를 해결 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd66f-117">This information is used by Microsoft support engineers to help you troubleshoot an error.</span></span> <span data-ttu-id="fd66f-118">Microsoft 지원에 문의 하는 경우 상관 관계 ID를 요청 하는 메시지가 표시 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd66f-118">If you contact Microsoft support, you might be asked for the Correlation ID.</span></span>
    
<span data-ttu-id="fd66f-119">즉, 모든 비즈니스용 Skype Online 사용자와 서비스 설정을 더 가까운 다른 위치로 이동 하는 과정을 진행 하 고 있는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="fd66f-119">So what this all means is we're in the process of moving all your Skype for Business Online users and service settings to another location that's closer to you.</span></span> <span data-ttu-id="fd66f-120">더 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="fd66f-120">The closer the better.</span></span> <span data-ttu-id="fd66f-121">좋은 소식은이 짧은 시간이 지난 후 비즈니스용 Skype Online 서비스가 개선 된다는 점입니다.</span><span class="sxs-lookup"><span data-stu-id="fd66f-121">The good news is that after this short period of time, your Skype for Business Online service will improve.</span></span>
  
![Office 365의 서비스 마이그레이션](../images/77502071-36fe-4833-a5ff-3b9ca7676542.png)
  
## <a name="what-skype-for-business-online-features-will-still-work"></a><span data-ttu-id="fd66f-123">비즈니스용 Skype Online 기능은 어떤 기능을 사용할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="fd66f-123">What Skype for Business Online features will still work?</span></span>

<span data-ttu-id="fd66f-124">비즈니스용 Skype Online 관리 센터에 액세스할 수는 없지만 마이그레이션 중에는 다음과 같은 비즈니스용 Skype Online 기능이 계속 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd66f-124">Although you won't be able to access the Skype for Business Online admin center, the following Skype for Business Online features will still work during the migration:</span></span>
  
- <span data-ttu-id="fd66f-125">온라인 모임</span><span class="sxs-lookup"><span data-stu-id="fd66f-125">Online meetings</span></span>
    
- <span data-ttu-id="fd66f-126">현재 상태 정보</span><span class="sxs-lookup"><span data-stu-id="fd66f-126">Presence information</span></span>
    
## <a name="can-i-get-other-work-done"></a><span data-ttu-id="fd66f-127">다른 작업을 수행할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="fd66f-127">Can I get other work done?</span></span>

<span data-ttu-id="fd66f-128">해야.</span><span class="sxs-lookup"><span data-stu-id="fd66f-128">Sure.</span></span> <span data-ttu-id="fd66f-129">비즈니스용 Skype Online 서비스를 마이그레이션하는 동안에도 Office 365 (예: Office 365 및 Exchange 관리 센터)의 다른 관리 센터를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd66f-129">While we're migrating your Skype for Business Online service, you can still use the other admin centers in Office 365 (for example, the Office 365 and Exchange admin centers).</span></span> <span data-ttu-id="fd66f-130">그러나 비즈니스용 Skype Online 관리 센터와 함께 마이그레이션 중에 비즈니스용 Skype Online 원격 PowerShell cmdlet을 사용할 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd66f-130">However, along with the Skype for Business Online admin center, you won't be able to use the Skype for Business Online Remote PowerShell cmdlets during the migration.</span></span> 
  
## <a name="related-topics"></a><span data-ttu-id="fd66f-131">관련 주제</span><span class="sxs-lookup"><span data-stu-id="fd66f-131">Related topics</span></span>
[<span data-ttu-id="fd66f-132">비즈니스용 Skype 온라인 설정</span><span class="sxs-lookup"><span data-stu-id="fd66f-132">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="fd66f-133">비즈니스용 Skype 사용자가 Skype 연락처를 추가하도록 허용</span><span class="sxs-lookup"><span data-stu-id="fd66f-133">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

  
 
