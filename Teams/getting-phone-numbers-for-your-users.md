---
title: 사용자의 전화 번호 가져오기
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: aa2ec464-3481-4bbb-8c14-e13e18093df5
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Calling Plans
description: '팀에 대해 새, 포트 또는 기존 번호를 전송 하는 방법과 사용자에 게 변경 내용을 표시 하는 방법에 대해 알아봅니다. '
ms.openlocfilehash: 51f436a3b2d462e9984fb9fc09620e7c1a77307d
ms.sourcegitcommit: 5a7e273a3636322052e4a48a5a75513cbf5abb84
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "39209204"
---
# <a name="getting-phone-numbers-for-your-users"></a><span data-ttu-id="bfcf1-103">사용자의 전화 번호 가져오기</span><span class="sxs-lookup"><span data-stu-id="bfcf1-103">Getting phone numbers for your users</span></span>

<span data-ttu-id="bfcf1-104">전화를 걸고 받을 수 있도록 조직에 사용자를 설정 하려면 먼저 전화 번호를 받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bfcf1-104">Before you can set up users in your organization to make and receive phone calls, you must get phone numbers for them.</span></span>
  
<span data-ttu-id="bfcf1-105">다음과 같은 세 가지 방법으로 사용자 번호를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfcf1-105">There are three ways to get user numbers:</span></span>

- <span data-ttu-id="bfcf1-106">**Microsoft 팀 관리 센터를 사용 합니다.**</span><span class="sxs-lookup"><span data-stu-id="bfcf1-106">**Use the Microsoft Teams admin center.**</span></span> <span data-ttu-id="bfcf1-107">일부 국가/지역의 경우 Microsoft 팀 관리 센터를 사용 하 여 사용자에 대 한 번호를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfcf1-107">For some countries/regions, you can get numbers for your users using the Microsoft Teams admin center.</span></span> <span data-ttu-id="bfcf1-108">[사용자의 새 전화 번호 받기를](#get-new-phone-numbers-for-your-users)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="bfcf1-108">See [Get new phone numbers for your users](#get-new-phone-numbers-for-your-users).</span></span>
    
- <span data-ttu-id="bfcf1-109">**기존 번호를 이식 합니다.**</span><span class="sxs-lookup"><span data-stu-id="bfcf1-109">**Port your existing numbers.**</span></span> <span data-ttu-id="bfcf1-110">현재 서비스 공급자 또는 전화 통신 회사에서 기존 번호를 이식 하거나 전송할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfcf1-110">You can port or transfer existing numbers from your current service provider or phone carrier.</span></span> <span data-ttu-id="bfcf1-111">이 작업을 수행 하는 데 도움이 되는 자세한 내용은 조직의 전화 [번호를 팀으로 전송](/microsoftteams/phone-number-calling-plans/transfer-phone-numbers-to-teams) 또는 [전화 번호 관리](/microsoftteams/manage-phone-numbers-for-your-organization) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="bfcf1-111">See [Transfer phone numbers to Teams](/microsoftteams/phone-number-calling-plans/transfer-phone-numbers-to-teams) or [Manage phone numbers for your organization](/microsoftteams/manage-phone-numbers-for-your-organization) for more information to help you do this.</span></span>  
  
- <span data-ttu-id="bfcf1-112">**새 번호에 요청 양식을 사용 합니다.**</span><span class="sxs-lookup"><span data-stu-id="bfcf1-112">**Use a request form for new numbers.**</span></span> <span data-ttu-id="bfcf1-113">때로는 (국가/지역에 따라) Microsoft 팀 관리 센터를 사용 하 여 새 전화 번호를 받을 수 없으며, 특정 전화 번호 또는 지역 코드도 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="bfcf1-113">Sometimes (depending on your country/region) you won't be able to get your new phone numbers using the Microsoft Teams admin center, or you'll need specific phone numbers or area codes.</span></span> <span data-ttu-id="bfcf1-114">그렇다면 양식을 다운로드 하 여 다시 전송 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bfcf1-114">If so, you'll need to download a form and send it back to us.</span></span> <span data-ttu-id="bfcf1-115">자세한 내용은 [조직의 전화 번호 관리](/microsoftteams/manage-phone-numbers-for-your-organization) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="bfcf1-115">See [Manage phone numbers for your organization](/microsoftteams/manage-phone-numbers-for-your-organization) for more information.</span></span>
  
> [!NOTE]
> <span data-ttu-id="bfcf1-116">조직의 전화 번호를 설정 하는 데 도움이 필요한 경우 [PSTN 서비스 데스크에 문의할](manage-phone-numbers-for-your-organization/contact-pstn-service-desk.md)수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfcf1-116">If you need help setting up phone numbers for your organization, you can [contact the PSTN service desk](manage-phone-numbers-for-your-organization/contact-pstn-service-desk.md).</span></span>
  
## <a name="get-new-phone-numbers-for-your-users"></a><span data-ttu-id="bfcf1-117">사용자를 위한 새 전화 번호 받기</span><span class="sxs-lookup"><span data-stu-id="bfcf1-117">Get new phone numbers for your users</span></span>

<span data-ttu-id="bfcf1-118">![](media/teams-logo-30x30.png) **Microsoft 팀 관리 센터를 사용 하 여** microsoft 팀 로고를 표시 하는 아이콘</span><span class="sxs-lookup"><span data-stu-id="bfcf1-118">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>
    
1. <span data-ttu-id="bfcf1-119">왼쪽 탐색 창에서 **음성** > **전화 번호로**이동한 다음 **추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="bfcf1-119">In the left navigation, go to **Voice** > **Phone numbers**, and then click **Add**.</span></span>
2. <span data-ttu-id="bfcf1-120">주문 이름을 입력 하 고 원하는 경우 설명을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="bfcf1-120">Enter a name for the order and if you want, add a description.</span></span>
3. <span data-ttu-id="bfcf1-121">위치 및 수량 페이지에서 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="bfcf1-121">On the Location and quantity page, do the following:</span></span>
    1. <span data-ttu-id="bfcf1-122">**국가 또는 지역**에서 국가 또는 지역을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="bfcf1-122">Under **Country or region**, select a country or region.</span></span>
    1. <span data-ttu-id="bfcf1-123">**숫자 형식**에서 원하는 번호 형식을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="bfcf1-123">Under **Number type**, select the type of number that you want.</span></span>
    1. <span data-ttu-id="bfcf1-124">**위치**에서 위치를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="bfcf1-124">Under **Location**, select a location.</span></span> <span data-ttu-id="bfcf1-125">새 위치를 만들어야 할 경우 **위치 추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="bfcf1-125">If you need to create a new location, click **Add a location**.</span></span>
    1. <span data-ttu-id="bfcf1-126">**지역 번호**에서 지역 번호를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="bfcf1-126">Under **Area code**, select an area code.</span></span> 
    2. <span data-ttu-id="bfcf1-127">**수량**에서 조직에 사용할 숫자의 개수를 입력 하 고 **다음** 을 클릭 하 여 번호를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="bfcf1-127">Under **Quantity**, enter the number of numbers that you want for your organization, and then click **Next** to select your numbers.</span></span>
4. <span data-ttu-id="bfcf1-128">원하는 숫자를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="bfcf1-128">Select the numbers you want.</span></span> <span data-ttu-id="bfcf1-129">전화 번호를 선택 하 고 주문을 하는 데 10 분이 걸립니다.</span><span class="sxs-lookup"><span data-stu-id="bfcf1-129">You have 10 minutes to select your phone numbers and place your order.</span></span> <span data-ttu-id="bfcf1-130">10 분 이상 소요 되는 경우 전화 번호는 숫자의 풀로 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bfcf1-130">If you take more than 10 minutes, the phone numbers will be returned to the pool of numbers.</span></span>
5. <span data-ttu-id="bfcf1-131">주문을 추가할 준비가 되 면 **주문을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="bfcf1-131">When you're ready to place your order, click **Place order**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="bfcf1-132">사용자 (구독자)의 전화 번호 수는 귀하에 게 지정한 **국내 통화 요금제** 및/또는 **국내 및 국제 통화 요금제** 라이선스의 총 수에 1.1, 추가 전화 번호는 10 개를 곱한 값입니다.</span><span class="sxs-lookup"><span data-stu-id="bfcf1-132">The number of phone numbers for users (subscribers) is equal to the total number of **Domestic Calling Plan** and/or **Domestic and International Calling Plan** licenses you have assigned multiplied by 1.1, plus 10 additional phone numbers.</span></span> <span data-ttu-id="bfcf1-133">예를 들어 국내 통화 요금제 및/또는 국내 및 국제 통화 요금제에 50 사용자가 있는 경우 **65** 전화 번호 **(50 x 1.1 + 10)** 를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfcf1-133">For example, if you have 50 users in total with a Domestic Calling Plan and/or Domestic and International Calling Plan, you can acquire **65** phone numbers **(50 x 1.1 + 10)**.</span></span> <span data-ttu-id="bfcf1-134">자세한 내용은 [받을 수 있는 전화 번호 수](/microsoftteams/how-many-phone-numbers-can-you-get)를 확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="bfcf1-134">For details, see [How many phone numbers can you get?](/microsoftteams/how-many-phone-numbers-can-you-get).</span></span> <span data-ttu-id="bfcf1-135">이 보다 더 많은 전화 번호를 받으려면 [PSTN 서비스 데스크에 문의 하세요](manage-phone-numbers-for-your-organization/contact-pstn-service-desk.md).</span><span class="sxs-lookup"><span data-stu-id="bfcf1-135">If you need to get more phone numbers than this, [contact the PSTN service desk](manage-phone-numbers-for-your-organization/contact-pstn-service-desk.md).</span></span>
  
   <span data-ttu-id="bfcf1-136">**서비스 공급자 또는 전화 통신 회사의 전화 번호를 이식 하거나 전송 합니다.**</span><span class="sxs-lookup"><span data-stu-id="bfcf1-136">**Port or transfer phone numbers from your service provider or phone carrier**</span></span>
  
- <span data-ttu-id="bfcf1-137">사용자에 게 999 이하의 전화 번호가 필요한 경우 Microsoft 팀 관리 센터에서 레거시 포털을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfcf1-137">If you need 999 or fewer phone numbers for your users, you can use the legacy portal in the Microsoft Teams admin center.</span></span> <span data-ttu-id="bfcf1-138">전화 [번호를 팀](/microsoftteams/phone-number-calling-plans/transfer-phone-numbers-to-teams) 에 게 전송의 단계에 따라 전화 번호를 팀에 게 전송 합니다.</span><span class="sxs-lookup"><span data-stu-id="bfcf1-138">Follow the steps in [Transfer phone numbers to Teams](/microsoftteams/phone-number-calling-plans/transfer-phone-numbers-to-teams) to transfer your phone numbers to Teams.</span></span>
    
- <span data-ttu-id="bfcf1-139">999 개 이상의 전화 번호를 이식 해야 하는 경우 [Service Manager에서 서비스 요청 관리](https://docs.microsoft.com/system-center/scsm/service-requests) 를 참조 하 여 포트 주문 서비스 요청 또는 주문을 제출 하 여 Office 365로 이식 된 모든 전화 번호를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="bfcf1-139">If you need to port more than 999 phone numbers, see [Manage service requests in Service Manager](https://docs.microsoft.com/system-center/scsm/service-requests) to submit a port order service request or order to get all of these phone numbers ported over to Office 365.</span></span>
    
## <a name="show-phone-numbers-for-your-organization"></a><span data-ttu-id="bfcf1-140">조직의 전화 번호 표시</span><span class="sxs-lookup"><span data-stu-id="bfcf1-140">Show phone numbers for your organization</span></span>

<span data-ttu-id="bfcf1-141">![](media/teams-logo-30x30.png) **Microsoft 팀 관리 센터를 사용 하 여** microsoft 팀 로고를 표시 하는 아이콘</span><span class="sxs-lookup"><span data-stu-id="bfcf1-141">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span> 

<span data-ttu-id="bfcf1-142">왼쪽 탐색 창에서 **음성** > **전화 번호로** 이동 하 여 위치, 번호 형식, 상태 정보를 비롯 한 조직의 번호를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="bfcf1-142">In the left navigation, go to **Voice** > **Phone numbers** to view the numbers for your organization, including location, number type, and status information.</span></span>
  
## <a name="what-else-do-you-need-to-know-about-users-phone-numbers"></a><span data-ttu-id="bfcf1-143">사용자의 전화 번호에 대해 알아야 할 기타 사항</span><span class="sxs-lookup"><span data-stu-id="bfcf1-143">What else do you need to know about users' phone numbers?</span></span>
    
- <span data-ttu-id="bfcf1-144">전화 번호를 받은 후에는 각 사용자에 게 번호를 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bfcf1-144">After you get your phone numbers, you'll need to assign a number to each of your users.</span></span> <span data-ttu-id="bfcf1-145">[사용자의 전화 번호 지정, 변경 또는 제거를](/microsoftteams/assign-change-or-remove-a-phone-number-for-a-user)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="bfcf1-145">See [Assign, change, or remove a phone number for a user](/microsoftteams/assign-change-or-remove-a-phone-number-for-a-user).</span></span>
    
- <span data-ttu-id="bfcf1-146">Microsoft 팀 관리 센터의 **전화 번호** 페이지를 사용 하 여 **전화 번호** 열에 사용 가능한 전화 번호 목록을 표시 하 고, **상태** 열에 전화 번호가 할당 되었는지 확인 하 고, **위치** 열에서 전화 번호의 위치를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfcf1-146">You can use the **Phone numbers** page in the Microsoft Teams admin center to see the list of available phone numbers in the **Phone number** column, see whether the phone number has been assigned in the **Status** column, and see the location for the phone number in the **Location** column.</span></span> 

> [!NOTE]
> <span data-ttu-id="bfcf1-147">이 보다 더 많은 전화 번호를 받으려면 [PSTN 서비스 데스크에 문의 하세요](manage-phone-numbers-for-your-organization/contact-pstn-service-desk.md).</span><span class="sxs-lookup"><span data-stu-id="bfcf1-147">If you need to get more phone numbers than this, [contact the PSTN service desk](manage-phone-numbers-for-your-organization/contact-pstn-service-desk.md).</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="bfcf1-148">관련 항목</span><span class="sxs-lookup"><span data-stu-id="bfcf1-148">Related topics</span></span>

[<span data-ttu-id="bfcf1-149">전화 번호 전송 자주 묻는 질문</span><span class="sxs-lookup"><span data-stu-id="bfcf1-149">Transferring phone numbers common questions</span></span>](/microsoftteams/transferring-phone-numbers-common-questions)

[<span data-ttu-id="bfcf1-150">통화 요금제에 사용 되는 다른 종류의 전화 번호</span><span class="sxs-lookup"><span data-stu-id="bfcf1-150">Different kinds of phone numbers used for Calling Plans</span></span>](/microsoftteams/different-kinds-of-phone-numbers-used-for-calling-plans)

<span data-ttu-id="bfcf1-151">[Manage phone numbers for your organization](/microsoftteams/manage-phone-numbers-for-your-organization)(조직의 전화 번호 관리)</span><span class="sxs-lookup"><span data-stu-id="bfcf1-151">[Manage phone numbers for your organization](/microsoftteams/manage-phone-numbers-for-your-organization)</span></span>

[<span data-ttu-id="bfcf1-152">긴급 통화 사용 약관</span><span class="sxs-lookup"><span data-stu-id="bfcf1-152">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)

<span data-ttu-id="bfcf1-153">[비상 전화 고 지 사항 레이블](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="bfcf1-153">[Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>
