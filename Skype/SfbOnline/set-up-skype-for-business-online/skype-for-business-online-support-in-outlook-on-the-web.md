---
title: 웹용 Outlook에서 비즈니스용 Skype Online 지원
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 305984ec-3da8-4509-bb2b-6643dcf2cb7d
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Setup
description: Office 365의 웹용 outlook (Outlook Web App)은 탐색 모음에서 기본적인 비즈니스용 Skype 웹 클라이언트를 제공 합니다. 관리자가 Microsoft 365 또는 Office 365에 대 한 vanity URL을 구성 하지 않은 온라인 사용자는이 기본 클라이언트를 사용할 수 있습니다. 사용자 계정이 온라인 상태이 고 vanity URL이 없는 한, 조직에는 온-프레미스 사용자 계정이 있는 경우에도 계속 해 서 환경이 표시 됩니다. 온-프레미스 (vanity URL이 있는지 여부) 또는 Microsoft에서 관리 하는 사용자 계정이 있는 사용자는 Outlook web app에서 Lync 환경을 볼 수 있습니다.
ms.openlocfilehash: 9ea26932db8551992ab441263e55548646039c7e
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "43777173"
---
# <a name="skype-for-business-online-support-in-outlook-on-the-web"></a><span data-ttu-id="e3353-106">웹용 Outlook에서 비즈니스용 Skype Online 지원</span><span class="sxs-lookup"><span data-stu-id="e3353-106">Skype for Business Online support in Outlook on the web</span></span>

<span data-ttu-id="e3353-107">Office 365의 웹용 outlook (Outlook Web App)은 탐색 모음에서 기본적인 비즈니스용 Skype 웹 클라이언트를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3353-107">Outlook on the web (Outlook Web App) in Office 365 offers a basic Skype for Business web client from the navigation bar.</span></span> <span data-ttu-id="e3353-108">관리자가 Microsoft 365 또는 Office 365에 대 한 vanity URL을 구성 하지 않은 온라인 사용자는이 기본 클라이언트를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3353-108">This basic client is available for Online users whose admin hasn't configured a vanity URL for their Microsoft 365 or Office 365.</span></span> <span data-ttu-id="e3353-109">사용자 계정이 온라인 상태이 고 vanity URL이 없는 한, 조직에는 온-프레미스 사용자 계정이 있는 경우에도 계속 해 서 환경이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3353-109">As long as the user's account is online and doesn't have a vanity URL, they will still see the experience even if their organization has some user accounts that are homed on-premises.</span></span> <span data-ttu-id="e3353-110">온-프레미스 (vanity URL이 있는지 여부) 또는 Microsoft에서 관리 하는 사용자 계정이 있는 사용자는 Outlook web app에서 Lync 환경을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3353-110">Users who have user accounts on-premises (whether they have a vanity URL or not) or are managed by Microsoft will see the Lync experience in the Outlook web app.</span></span>
  
<span data-ttu-id="e3353-111">다음 표에는 사용할 수 있는 다양 한 설치 및 사용 되는 웹 클라이언트가 요약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3353-111">The following table summarizes the different setups that you may have and the web client that is used.</span></span>
  
||||
|:-----|:-----|:-----|
|<span data-ttu-id="e3353-112">**사용자 계정이 있는 경우**</span><span class="sxs-lookup"><span data-stu-id="e3353-112">**User account is located**</span></span> <br/> |<span data-ttu-id="e3353-113">**Vanity URL이 구성 되었거나 전용 조직이 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="e3353-113">**Vanity URL is configured or there is a dedicated organization**</span></span> <br/> |<span data-ttu-id="e3353-114">**비즈니스용 Skype 또는 Lync 환경**</span><span class="sxs-lookup"><span data-stu-id="e3353-114">**Skype for Business or Lync Experience?**</span></span> <br/> |
|<span data-ttu-id="e3353-115">온라인</span><span class="sxs-lookup"><span data-stu-id="e3353-115">Online</span></span>  <br/> |<span data-ttu-id="e3353-116">아니요</span><span class="sxs-lookup"><span data-stu-id="e3353-116">No</span></span>  <br/> |<span data-ttu-id="e3353-117">비즈니스용 Skype 웹 환경</span><span class="sxs-lookup"><span data-stu-id="e3353-117">Skype for Business web experience</span></span>  <br/> |
|<span data-ttu-id="e3353-118">온라인</span><span class="sxs-lookup"><span data-stu-id="e3353-118">Online</span></span>  <br/> |<span data-ttu-id="e3353-119">예</span><span class="sxs-lookup"><span data-stu-id="e3353-119">Yes</span></span>  <br/> |<span data-ttu-id="e3353-120">Lync 웹 환경</span><span class="sxs-lookup"><span data-stu-id="e3353-120">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="e3353-121">하이브리드 이지만 홈 온라인</span><span class="sxs-lookup"><span data-stu-id="e3353-121">Hybrid but homed online</span></span>  <br/> |<span data-ttu-id="e3353-122">아니요</span><span class="sxs-lookup"><span data-stu-id="e3353-122">No</span></span>  <br/> |<span data-ttu-id="e3353-123">비즈니스용 Skype 웹 환경</span><span class="sxs-lookup"><span data-stu-id="e3353-123">Skype for Business web experience</span></span>  <br/> |
|<span data-ttu-id="e3353-124">하이브리드 이지만 홈 온라인</span><span class="sxs-lookup"><span data-stu-id="e3353-124">Hybrid but homed online</span></span>  <br/> |<span data-ttu-id="e3353-125">예</span><span class="sxs-lookup"><span data-stu-id="e3353-125">Yes</span></span>  <br/> |<span data-ttu-id="e3353-126">Lync 웹 환경</span><span class="sxs-lookup"><span data-stu-id="e3353-126">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="e3353-127">하이브리드 이지만 프레미스에 있는 홈</span><span class="sxs-lookup"><span data-stu-id="e3353-127">Hybrid but homed on prem</span></span>  <br/> |<span data-ttu-id="e3353-128">아니요</span><span class="sxs-lookup"><span data-stu-id="e3353-128">No</span></span>  <br/> |<span data-ttu-id="e3353-129">Lync 웹 환경</span><span class="sxs-lookup"><span data-stu-id="e3353-129">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="e3353-130">하이브리드 이지만 프레미스에 있는 홈</span><span class="sxs-lookup"><span data-stu-id="e3353-130">Hybrid but homed on prem</span></span>  <br/> |<span data-ttu-id="e3353-131">예</span><span class="sxs-lookup"><span data-stu-id="e3353-131">Yes</span></span>  <br/> |<span data-ttu-id="e3353-132">Lync 웹 환경</span><span class="sxs-lookup"><span data-stu-id="e3353-132">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="e3353-133">순수 프레미스</span><span class="sxs-lookup"><span data-stu-id="e3353-133">Pure on prem</span></span>  <br/> |<span data-ttu-id="e3353-134">아니요</span><span class="sxs-lookup"><span data-stu-id="e3353-134">No</span></span>  <br/> |<span data-ttu-id="e3353-135">Lync 웹 환경</span><span class="sxs-lookup"><span data-stu-id="e3353-135">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="e3353-136">순수 프레미스</span><span class="sxs-lookup"><span data-stu-id="e3353-136">Pure on prem</span></span>  <br/> |<span data-ttu-id="e3353-137">예</span><span class="sxs-lookup"><span data-stu-id="e3353-137">Yes</span></span>  <br/> |<span data-ttu-id="e3353-138">Lync 웹 환경</span><span class="sxs-lookup"><span data-stu-id="e3353-138">Lync web experience</span></span>  <br/> |
   

## <a name="related-topics"></a><span data-ttu-id="e3353-139">관련 항목</span><span class="sxs-lookup"><span data-stu-id="e3353-139">Related topics</span></span>
[<span data-ttu-id="e3353-140">비즈니스용 Skype 온라인 설정</span><span class="sxs-lookup"><span data-stu-id="e3353-140">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="e3353-141">비즈니스용 Skype 사용자가 Skype 연락처를 추가하도록 허용</span><span class="sxs-lookup"><span data-stu-id="e3353-141">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

  
 
