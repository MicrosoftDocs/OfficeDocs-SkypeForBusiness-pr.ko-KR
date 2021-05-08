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
description: Outlook 웹(Outlook Web App)에서 Microsoft 365 Office 365 탐색 모음에서 비즈니스용 Skype 웹 클라이언트를 제공합니다. 이 기본 클라이언트는 관리자가 해당 웹 사이트 및 웹 사이트에 대해 베니티 URL을 구성하지 않은 Microsoft 365 사용할 Office 365. 사용자의 계정이 온라인에 있으며 허영 URL이 없는 한 조직에 일부 사용자 계정이 있는 경우에도 환경을 볼 수 있습니다. 온-프레미스에 사용자 계정이 있는 사용자 계정(베니티 URL이 있는지 여부)이나 Microsoft에서 관리되는 사용자는 웹앱에서 Lync Outlook 표시됩니다.
ms.openlocfilehash: aa6f82f6647db1816c630486bee0d415d05b3b77
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52239573"
---
# <a name="skype-for-business-online-support-in-outlook-on-the-web"></a><span data-ttu-id="1f70e-106">웹용 Outlook에서 비즈니스용 Skype Online 지원</span><span class="sxs-lookup"><span data-stu-id="1f70e-106">Skype for Business Online support in Outlook on the web</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

<span data-ttu-id="1f70e-107">Outlook 웹(Outlook Web App)에서 Microsoft 365 Office 365 탐색 모음에서 비즈니스용 Skype 웹 클라이언트를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="1f70e-107">Outlook on the web (Outlook Web App) in Microsoft 365 or Office 365 offers a basic Skype for Business web client from the navigation bar.</span></span> <span data-ttu-id="1f70e-108">이 기본 클라이언트는 관리자가 해당 웹 사이트 및 웹 사이트에 대해 베니티 URL을 구성하지 않은 Microsoft 365 사용할 Office 365.</span><span class="sxs-lookup"><span data-stu-id="1f70e-108">This basic client is available for Online users whose admin hasn't configured a vanity URL for their Microsoft 365 and Office 365.</span></span> <span data-ttu-id="1f70e-109">사용자의 계정이 온라인에 있으며 허영 URL이 없는 한 조직에 일부 사용자 계정이 있는 경우에도 환경을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f70e-109">As long as the user's account is online and doesn't have a vanity URL, they will still see the experience even if their organization has some user accounts that are homed on-premises.</span></span> <span data-ttu-id="1f70e-110">온-프레미스에 사용자 계정이 있는 사용자 계정(베니티 URL이 있는지 여부)이나 Microsoft에서 관리되는 사용자는 웹앱에서 Lync Outlook 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="1f70e-110">Users who have user accounts on-premises (whether they have a vanity URL or not) or are managed by Microsoft will see the Lync experience in the Outlook web app.</span></span>
  
<span data-ttu-id="1f70e-111">다음 표에서는 사용할 수 있는 다양한 설정과 사용되는 웹 클라이언트를 요약합니다.</span><span class="sxs-lookup"><span data-stu-id="1f70e-111">The following table summarizes the different setups that you may have and the web client that is used.</span></span>
  
||||
|:-----|:-----|:-----|
|<span data-ttu-id="1f70e-112">**사용자 계정이 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="1f70e-112">**User account is located**</span></span> <br/> |<span data-ttu-id="1f70e-113">**Vanity URL이 구성되거나 전용 조직이 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="1f70e-113">**Vanity URL is configured or there is a dedicated organization**</span></span> <br/> |<span data-ttu-id="1f70e-114">**비즈니스용 Skype 또는 Lync 환경?**</span><span class="sxs-lookup"><span data-stu-id="1f70e-114">**Skype for Business or Lync Experience?**</span></span> <br/> |
|<span data-ttu-id="1f70e-115">온라인</span><span class="sxs-lookup"><span data-stu-id="1f70e-115">Online</span></span>  <br/> |<span data-ttu-id="1f70e-116">아니요</span><span class="sxs-lookup"><span data-stu-id="1f70e-116">No</span></span>  <br/> |<span data-ttu-id="1f70e-117">비즈니스용 Skype 웹 환경</span><span class="sxs-lookup"><span data-stu-id="1f70e-117">Skype for Business web experience</span></span>  <br/> |
|<span data-ttu-id="1f70e-118">온라인</span><span class="sxs-lookup"><span data-stu-id="1f70e-118">Online</span></span>  <br/> |<span data-ttu-id="1f70e-119">예</span><span class="sxs-lookup"><span data-stu-id="1f70e-119">Yes</span></span>  <br/> |<span data-ttu-id="1f70e-120">Lync 웹 환경</span><span class="sxs-lookup"><span data-stu-id="1f70e-120">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="1f70e-121">하이브리드하지만 홈온라인</span><span class="sxs-lookup"><span data-stu-id="1f70e-121">Hybrid but homed online</span></span>  <br/> |<span data-ttu-id="1f70e-122">아니요</span><span class="sxs-lookup"><span data-stu-id="1f70e-122">No</span></span>  <br/> |<span data-ttu-id="1f70e-123">비즈니스용 Skype 웹 환경</span><span class="sxs-lookup"><span data-stu-id="1f70e-123">Skype for Business web experience</span></span>  <br/> |
|<span data-ttu-id="1f70e-124">하이브리드하지만 홈온라인</span><span class="sxs-lookup"><span data-stu-id="1f70e-124">Hybrid but homed online</span></span>  <br/> |<span data-ttu-id="1f70e-125">예</span><span class="sxs-lookup"><span data-stu-id="1f70e-125">Yes</span></span>  <br/> |<span data-ttu-id="1f70e-126">Lync 웹 환경</span><span class="sxs-lookup"><span data-stu-id="1f70e-126">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="1f70e-127">하이브리드하지만 프레미스에 홈</span><span class="sxs-lookup"><span data-stu-id="1f70e-127">Hybrid but homed on prem</span></span>  <br/> |<span data-ttu-id="1f70e-128">아니요</span><span class="sxs-lookup"><span data-stu-id="1f70e-128">No</span></span>  <br/> |<span data-ttu-id="1f70e-129">Lync 웹 환경</span><span class="sxs-lookup"><span data-stu-id="1f70e-129">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="1f70e-130">하이브리드하지만 프레미스에 홈</span><span class="sxs-lookup"><span data-stu-id="1f70e-130">Hybrid but homed on prem</span></span>  <br/> |<span data-ttu-id="1f70e-131">예</span><span class="sxs-lookup"><span data-stu-id="1f70e-131">Yes</span></span>  <br/> |<span data-ttu-id="1f70e-132">Lync 웹 환경</span><span class="sxs-lookup"><span data-stu-id="1f70e-132">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="1f70e-133">퓨어 on prem</span><span class="sxs-lookup"><span data-stu-id="1f70e-133">Pure on prem</span></span>  <br/> |<span data-ttu-id="1f70e-134">아니요</span><span class="sxs-lookup"><span data-stu-id="1f70e-134">No</span></span>  <br/> |<span data-ttu-id="1f70e-135">Lync 웹 환경</span><span class="sxs-lookup"><span data-stu-id="1f70e-135">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="1f70e-136">퓨어 on prem</span><span class="sxs-lookup"><span data-stu-id="1f70e-136">Pure on prem</span></span>  <br/> |<span data-ttu-id="1f70e-137">예</span><span class="sxs-lookup"><span data-stu-id="1f70e-137">Yes</span></span>  <br/> |<span data-ttu-id="1f70e-138">Lync 웹 환경</span><span class="sxs-lookup"><span data-stu-id="1f70e-138">Lync web experience</span></span>  <br/> |
   

## <a name="related-topics"></a><span data-ttu-id="1f70e-139">관련 주제</span><span class="sxs-lookup"><span data-stu-id="1f70e-139">Related topics</span></span>
[<span data-ttu-id="1f70e-140">비즈니스용 Skype 온라인 설정</span><span class="sxs-lookup"><span data-stu-id="1f70e-140">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="1f70e-141">비즈니스용 Skype 사용자가 Skype 연락처를 추가하도록 허용</span><span class="sxs-lookup"><span data-stu-id="1f70e-141">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

  
 
