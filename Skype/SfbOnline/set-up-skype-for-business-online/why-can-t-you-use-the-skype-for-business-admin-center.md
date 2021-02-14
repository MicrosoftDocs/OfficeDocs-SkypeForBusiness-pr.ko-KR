---
title: 지금 비즈니스용 Skype Online 관리 센터를 사용할 수 없는 이유는 무엇입니까?
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
- CSH
ms.custom:
- Setup
- ms.lync.lac.TenantInMigration
description: '비즈니스용 Skype 관리 센터에서 사용할 수 있는 기능 및 사용할 수 없는 기능 및 서비스를 다른 Microsoft 데이터 센터로 마이그레이션할 때의 기타 기능에 대해 자세히 배워야 합니다. '
ms.openlocfilehash: 7258467929663c42bfb6088202511a04613db383
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2020
ms.locfileid: "44164497"
---
# <a name="why-cant-i-use-the-skype-for-business-online-admin-center-right-now"></a><span data-ttu-id="cf4ea-103">지금 비즈니스용 Skype Online 관리 센터를 사용할 수 없는 이유는 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="cf4ea-103">Why can't I use the Skype for Business Online admin center right now?</span></span>

<span data-ttu-id="cf4ea-104">작업을 완료할 수 없는 경우 좌절스러우기 때문에 여기서 일어나는 작업과 대기할 만한 이유에 대해 설명해 드릴 것입니다.</span><span class="sxs-lookup"><span data-stu-id="cf4ea-104">We know it's frustrating when you can't get your work done, so we're going to explain what's happening here and why it'll be worth the wait.</span></span> 
  
<span data-ttu-id="cf4ea-105">먼저 기술 설명은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="cf4ea-105">First, here's the technical explanation:</span></span>
  
<span data-ttu-id="cf4ea-106">비즈니스용 Skype Online 서비스(사용자 및 조직 설정)를 더 가까운 다른 Microsoft 데이터 센터로 마이그레이션하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf4ea-106">We're migrating your Skype for Business Online service (meaning your users and organizational settings) to another Microsoft datacenter that's closer to you.</span></span> <span data-ttu-id="cf4ea-107">이렇게 하면 서비스가 개선될 수 있으며 대기 시간이 줄어듭됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf4ea-107">This will improve your service and reduce latency.</span></span> 
  
<span data-ttu-id="cf4ea-108">자세한 기술 정보는 데이터 이동 [중 및 이후를 참조합니다.]( https://go.microsoft.com/fwlink/?LinkId=526418)</span><span class="sxs-lookup"><span data-stu-id="cf4ea-108">For more technical details, see [During and after your data move]( https://go.microsoft.com/fwlink/?LinkId=526418).</span></span>
  
## <a name="ok-so-what-does-that-mean"></a><span data-ttu-id="cf4ea-109">무슨 의미인가요?</span><span class="sxs-lookup"><span data-stu-id="cf4ea-109">OK, so what does that mean?</span></span>

<span data-ttu-id="cf4ea-110">먼저 몇 가지 용어를 세분화해보죠.</span><span class="sxs-lookup"><span data-stu-id="cf4ea-110">First, let's break down a few terms.</span></span>
  
- <span data-ttu-id="cf4ea-111">**데이터 센터** 파일 및 전자 메일 메시지와 같이 Microsoft 365 또는 Office 365의 정보가 저장되는 실제 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="cf4ea-111">**Data center** This is the physical location where the information from your Microsoft 365 or Office 365 is stored, such as your files and email messages.</span></span> <span data-ttu-id="cf4ea-112">Microsoft 365 및 Office 365 데이터 센터를 실제로 확인하려는 경우 이 문서를[확인해 주세요.](https://www.microsoft.com/online/legal/v2/?docid=25)</span><span class="sxs-lookup"><span data-stu-id="cf4ea-112">If you really want to dig in to what Microsoft 365 and Office 365 datacenters are, check out[this article](https://www.microsoft.com/online/legal/v2/?docid=25).</span></span>
    
- <span data-ttu-id="cf4ea-113">**마이그레이션** 이는 "이동"과 거의 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="cf4ea-113">**Migrating** This is pretty much the same as "moving."</span></span> <span data-ttu-id="cf4ea-114">이 경우 서비스를 개선하기 위해 비즈니스용 Skype Online 사용자 및 설정을 한 데이터 센터에서 다른 데이터 센터로 이동하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="cf4ea-114">In this case, it means we're moving your Skype for Business Online users and settings from one datacenter to another that's closer to you to improve your service.</span></span>
    
- <span data-ttu-id="cf4ea-115">**대기 시간** Microsoft 365 관리 센터에 액세스하고 설정을 변경한 다음 변경 내용을 저장하는 데 걸리는 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="cf4ea-115">**Latency** This is amount of time it takes you to access the Microsoft 365 admin center, make a settings change, and then save those changes.</span></span>
    
- <span data-ttu-id="cf4ea-116">**상관 관계 ID** 방금 보낸 메시지에 이 목록이 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf4ea-116">**Correlation ID** You might have seen this listed in the message you just came from.</span></span> <span data-ttu-id="cf4ea-117">이 정보는 Microsoft 지원 엔지니어가 오류를 해결하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf4ea-117">This information is used by Microsoft support engineers to help you troubleshoot an error.</span></span> <span data-ttu-id="cf4ea-118">Microsoft 지원에 문의하는 경우 상관 관계 ID를 묻는 요청이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf4ea-118">If you contact Microsoft support, you might be asked for the Correlation ID.</span></span>
    
<span data-ttu-id="cf4ea-119">따라서 비즈니스용 Skype Online 사용자 및 서비스 설정을 가장 가까운 다른 위치로 이동하는 중입니다.</span><span class="sxs-lookup"><span data-stu-id="cf4ea-119">So what this all means is we're in the process of moving all your Skype for Business Online users and service settings to another location that's closer to you.</span></span> <span data-ttu-id="cf4ea-120">더 가깝을수록 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="cf4ea-120">The closer the better.</span></span> <span data-ttu-id="cf4ea-121">이 짧은 기간 후에 비즈니스용 Skype Online 서비스가 개선될 것입니다.</span><span class="sxs-lookup"><span data-stu-id="cf4ea-121">The good news is that after this short period of time, your Skype for Business Online service will improve.</span></span>
  
![Microsoft 365 또는 Office 365에서 서비스 마이그레이션](../images/77502071-36fe-4833-a5ff-3b9ca7676542.png)
  
## <a name="what-skype-for-business-online-features-will-still-work"></a><span data-ttu-id="cf4ea-123">어떤 비즈니스용 Skype Online 기능이 계속 작동하나요?</span><span class="sxs-lookup"><span data-stu-id="cf4ea-123">What Skype for Business Online features will still work?</span></span>

<span data-ttu-id="cf4ea-124">비즈니스용 Skype Online 관리 센터에 액세스할 수 없는 경우 마이그레이션 중에도 다음과 같은 비즈니스용 Skype Online 기능이 계속 작동됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf4ea-124">Although you won't be able to access the Skype for Business Online admin center, the following Skype for Business Online features will still work during the migration:</span></span>
  
- <span data-ttu-id="cf4ea-125">온라인 모임</span><span class="sxs-lookup"><span data-stu-id="cf4ea-125">Online meetings</span></span>
    
- <span data-ttu-id="cf4ea-126">현재 상태 정보</span><span class="sxs-lookup"><span data-stu-id="cf4ea-126">Presence information</span></span>
    
## <a name="can-i-get-other-work-done"></a><span data-ttu-id="cf4ea-127">다른 작업을 완료할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="cf4ea-127">Can I get other work done?</span></span>

<span data-ttu-id="cf4ea-128">물론입니다.</span><span class="sxs-lookup"><span data-stu-id="cf4ea-128">Sure.</span></span> <span data-ttu-id="cf4ea-129">비즈니스용 Skype Online 서비스를 마이그레이션하는 동안 Microsoft 365의 다른 관리 센터(예: Microsoft 365 및 Exchange 관리 센터)를 계속 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf4ea-129">While we're migrating your Skype for Business Online service, you can still use the other admin centers in Microsoft 365 (for example, the Microsoft 365 and Exchange admin centers).</span></span> <span data-ttu-id="cf4ea-130">그러나 비즈니스용 Skype Online 관리 센터와 함께 마이그레이션하는 동안 비즈니스용 Skype Online 원격 PowerShell cmdlet을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cf4ea-130">However, along with the Skype for Business Online admin center, you won't be able to use the Skype for Business Online Remote PowerShell cmdlets during the migration.</span></span> 
  
## <a name="related-topics"></a><span data-ttu-id="cf4ea-131">관련 항목</span><span class="sxs-lookup"><span data-stu-id="cf4ea-131">Related topics</span></span>
[<span data-ttu-id="cf4ea-132">비즈니스용 Skype 온라인 설정</span><span class="sxs-lookup"><span data-stu-id="cf4ea-132">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="cf4ea-133">비즈니스용 Skype 사용자가 Skype 연락처를 추가하도록 허용</span><span class="sxs-lookup"><span data-stu-id="cf4ea-133">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

  
 
