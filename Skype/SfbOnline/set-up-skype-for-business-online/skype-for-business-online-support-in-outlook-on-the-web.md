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
description: Microsoft 365 또는 Office 365의 웹용 Outlook(Outlook Web App)은 탐색 모음에서 기본 비즈니스용 Skype 웹 클라이언트를 제공합니다. 이 기본 클라이언트는 관리자가 Microsoft 365 및 Office 365에 대해 베니티 URL을 구성하지 않은 온라인 사용자에게 제공됩니다. 사용자의 계정이 온라인에 있으며 베니티 URL이 없는 한 조직에 일부 사용자 계정이 있는 경우에도 환경이 계속 표시됩니다. 온-프레미스에 사용자 계정이 있는 경우(베니티 URL이 있는지 여부와 무관) Microsoft에서 관리하는 사용자는 Outlook 웹앱에서 Lync 환경을 볼 수 있습니다.
ms.openlocfilehash: ab426bdaf0261dcfb3375934eb1e5a6f5bd6df79
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2020
ms.locfileid: "44164113"
---
# <a name="skype-for-business-online-support-in-outlook-on-the-web"></a><span data-ttu-id="9289f-106">웹용 Outlook에서 비즈니스용 Skype Online 지원</span><span class="sxs-lookup"><span data-stu-id="9289f-106">Skype for Business Online support in Outlook on the web</span></span>

<span data-ttu-id="9289f-107">Microsoft 365 또는 Office 365의 웹용 Outlook(Outlook Web App)은 탐색 모음에서 기본 비즈니스용 Skype 웹 클라이언트를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9289f-107">Outlook on the web (Outlook Web App) in Microsoft 365 or Office 365 offers a basic Skype for Business web client from the navigation bar.</span></span> <span data-ttu-id="9289f-108">이 기본 클라이언트는 관리자가 Microsoft 365 및 Office 365에 대해 베니티 URL을 구성하지 않은 온라인 사용자에게 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="9289f-108">This basic client is available for Online users whose admin hasn't configured a vanity URL for their Microsoft 365 and Office 365.</span></span> <span data-ttu-id="9289f-109">사용자의 계정이 온라인에 있으며 베니티 URL이 없는 한 조직에 일부 사용자 계정이 있는 경우에도 환경이 계속 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9289f-109">As long as the user's account is online and doesn't have a vanity URL, they will still see the experience even if their organization has some user accounts that are homed on-premises.</span></span> <span data-ttu-id="9289f-110">온-프레미스에 사용자 계정이 있는 경우(베니티 URL이 있는지 여부와 무관) Microsoft에서 관리하는 사용자는 Outlook 웹앱에서 Lync 환경을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9289f-110">Users who have user accounts on-premises (whether they have a vanity URL or not) or are managed by Microsoft will see the Lync experience in the Outlook web app.</span></span>
  
<span data-ttu-id="9289f-111">다음 표에서는 사용할 수 있는 다양한 설정과 사용되는 웹 클라이언트를 요약합니다.</span><span class="sxs-lookup"><span data-stu-id="9289f-111">The following table summarizes the different setups that you may have and the web client that is used.</span></span>
  
||||
|:-----|:-----|:-----|
|<span data-ttu-id="9289f-112">**사용자 계정이 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="9289f-112">**User account is located**</span></span> <br/> |<span data-ttu-id="9289f-113">**베니티 URL이 구성되거나 전용 조직이 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="9289f-113">**Vanity URL is configured or there is a dedicated organization**</span></span> <br/> |<span data-ttu-id="9289f-114">**비즈니스용 Skype 또는 Lync 환경이 있나요?**</span><span class="sxs-lookup"><span data-stu-id="9289f-114">**Skype for Business or Lync Experience?**</span></span> <br/> |
|<span data-ttu-id="9289f-115">온라인</span><span class="sxs-lookup"><span data-stu-id="9289f-115">Online</span></span>  <br/> |<span data-ttu-id="9289f-116">아니요</span><span class="sxs-lookup"><span data-stu-id="9289f-116">No</span></span>  <br/> |<span data-ttu-id="9289f-117">비즈니스용 Skype 웹 환경</span><span class="sxs-lookup"><span data-stu-id="9289f-117">Skype for Business web experience</span></span>  <br/> |
|<span data-ttu-id="9289f-118">온라인</span><span class="sxs-lookup"><span data-stu-id="9289f-118">Online</span></span>  <br/> |<span data-ttu-id="9289f-119">예</span><span class="sxs-lookup"><span data-stu-id="9289f-119">Yes</span></span>  <br/> |<span data-ttu-id="9289f-120">Lync 웹 환경</span><span class="sxs-lookup"><span data-stu-id="9289f-120">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="9289f-121">하이브리드이지만 온라인에 홈</span><span class="sxs-lookup"><span data-stu-id="9289f-121">Hybrid but homed online</span></span>  <br/> |<span data-ttu-id="9289f-122">아니요</span><span class="sxs-lookup"><span data-stu-id="9289f-122">No</span></span>  <br/> |<span data-ttu-id="9289f-123">비즈니스용 Skype 웹 환경</span><span class="sxs-lookup"><span data-stu-id="9289f-123">Skype for Business web experience</span></span>  <br/> |
|<span data-ttu-id="9289f-124">하이브리드이지만 온라인에 홈</span><span class="sxs-lookup"><span data-stu-id="9289f-124">Hybrid but homed online</span></span>  <br/> |<span data-ttu-id="9289f-125">예</span><span class="sxs-lookup"><span data-stu-id="9289f-125">Yes</span></span>  <br/> |<span data-ttu-id="9289f-126">Lync 웹 환경</span><span class="sxs-lookup"><span data-stu-id="9289f-126">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="9289f-127">하이브리드이지만 프레미스에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9289f-127">Hybrid but homed on prem</span></span>  <br/> |<span data-ttu-id="9289f-128">아니요</span><span class="sxs-lookup"><span data-stu-id="9289f-128">No</span></span>  <br/> |<span data-ttu-id="9289f-129">Lync 웹 환경</span><span class="sxs-lookup"><span data-stu-id="9289f-129">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="9289f-130">하이브리드이지만 프레미스에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9289f-130">Hybrid but homed on prem</span></span>  <br/> |<span data-ttu-id="9289f-131">예</span><span class="sxs-lookup"><span data-stu-id="9289f-131">Yes</span></span>  <br/> |<span data-ttu-id="9289f-132">Lync 웹 환경</span><span class="sxs-lookup"><span data-stu-id="9289f-132">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="9289f-133">프레미스에서 순수</span><span class="sxs-lookup"><span data-stu-id="9289f-133">Pure on prem</span></span>  <br/> |<span data-ttu-id="9289f-134">아니요</span><span class="sxs-lookup"><span data-stu-id="9289f-134">No</span></span>  <br/> |<span data-ttu-id="9289f-135">Lync 웹 환경</span><span class="sxs-lookup"><span data-stu-id="9289f-135">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="9289f-136">프레미스에서 순수</span><span class="sxs-lookup"><span data-stu-id="9289f-136">Pure on prem</span></span>  <br/> |<span data-ttu-id="9289f-137">예</span><span class="sxs-lookup"><span data-stu-id="9289f-137">Yes</span></span>  <br/> |<span data-ttu-id="9289f-138">Lync 웹 환경</span><span class="sxs-lookup"><span data-stu-id="9289f-138">Lync web experience</span></span>  <br/> |
   

## <a name="related-topics"></a><span data-ttu-id="9289f-139">관련 항목</span><span class="sxs-lookup"><span data-stu-id="9289f-139">Related topics</span></span>
[<span data-ttu-id="9289f-140">비즈니스용 Skype 온라인 설정</span><span class="sxs-lookup"><span data-stu-id="9289f-140">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="9289f-141">비즈니스용 Skype 사용자가 Skype 연락처를 추가하도록 허용</span><span class="sxs-lookup"><span data-stu-id="9289f-141">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

  
 
