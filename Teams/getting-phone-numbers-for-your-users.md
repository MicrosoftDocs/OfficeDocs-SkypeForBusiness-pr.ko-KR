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
- m365initiative-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Calling Plans
description: 'Teams에 대한 기존 번호를 새로, 포트 또는 전송하는 방법 및 사용자에 대한 변경 내용을 표시하는 방법에 대해 자세히 알아보습니다. '
ms.openlocfilehash: c80f7a54af697322665c110c14aeccaf5fa4f667
ms.sourcegitcommit: 109b3869afb5ff1ca4eaf771399d7cda70a43bea
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/05/2021
ms.locfileid: "51586567"
---
# <a name="getting-phone-numbers-for-your-users"></a><span data-ttu-id="63e3c-103">사용자의 전화 번호 가져오기</span><span class="sxs-lookup"><span data-stu-id="63e3c-103">Getting phone numbers for your users</span></span>

<span data-ttu-id="63e3c-104">전화 통화를 걸고 받을 수 있도록 조직에서 사용자를 설정하려면 먼저 해당 사용자에 대한 전화 번호를 받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="63e3c-104">Before you can set up users in your organization to make and receive phone calls, you must get phone numbers for them.</span></span>
  
<span data-ttu-id="63e3c-105">사용자 번호를 얻을 수 있는 세 가지 방법이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63e3c-105">There are three ways to get user numbers:</span></span>

- <span data-ttu-id="63e3c-106">**Microsoft Teams 관리 센터를 사용하세요.**</span><span class="sxs-lookup"><span data-stu-id="63e3c-106">**Use the Microsoft Teams admin center.**</span></span> <span data-ttu-id="63e3c-107">일부 국가 및 지역의 경우 Microsoft Teams 관리 센터를 사용하여 사용자에 대한 번호를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63e3c-107">For some countries and regions, you can get numbers for your users using the Microsoft Teams admin center.</span></span> <span data-ttu-id="63e3c-108">사용자의 [새 전화 번호 보기를 참조합니다.](#get-new-phone-numbers-for-your-users)</span><span class="sxs-lookup"><span data-stu-id="63e3c-108">See [Get new phone numbers for your users](#get-new-phone-numbers-for-your-users).</span></span>

- <span data-ttu-id="63e3c-109">**기존 서비스 전화 번호 포팅하기**</span><span class="sxs-lookup"><span data-stu-id="63e3c-109">**Port your existing numbers.**</span></span> <span data-ttu-id="63e3c-110">현재 서비스 공급자 또는 휴대폰 통신사에서 기존 번호를 포트 또는 전송할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63e3c-110">You can port or transfer existing numbers from your current service provider or phone carrier.</span></span> <span data-ttu-id="63e3c-111">이 작업을 수행하는 데 도움이 되는 자세한 내용은 [Teams로 전화 번호 이전](./phone-number-calling-plans/transfer-phone-numbers-to-teams.md) 또는 [조직에 대한 전화 번호 관리](/microsoftteams/manage-phone-numbers-for-your-organization)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="63e3c-111">See [Transfer phone numbers to Teams](./phone-number-calling-plans/transfer-phone-numbers-to-teams.md) or [Manage phone numbers for your organization](/microsoftteams/manage-phone-numbers-for-your-organization) for more information to help you do this.</span></span>  
  
- <span data-ttu-id="63e3c-112">**새 전화 번호를 위한 요청 양식 사용하기**</span><span class="sxs-lookup"><span data-stu-id="63e3c-112">**Use a request form for new numbers.**</span></span> <span data-ttu-id="63e3c-113">때때로(국가 또는 지역에 따라) Microsoft Teams 관리 센터를 사용하여 새 전화 번호를 얻을 수 없는 경우도 있습니다. 또는 특정 전화 번호 또는 지역 코드가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="63e3c-113">Sometimes (depending on your country or region) you won't be able to get your new phone numbers using the Microsoft Teams Admin Center or you'll need specific phone numbers or area codes.</span></span> <span data-ttu-id="63e3c-114">자세한 내용은 [조직에서 전화번호 관리하기](/microsoftteams/manage-phone-numbers-for-your-organization)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="63e3c-114">See [Manage phone numbers for your organization](/microsoftteams/manage-phone-numbers-for-your-organization) for more information.</span></span>
  
> [!NOTE]
> <span data-ttu-id="63e3c-115">조직의 전화 번호를 설정하는 데 도움이 필요한 경우 비즈니스 제품 지원 연락처 - 관리자 도움말 [에 문의하세요.](https://docs.microsoft.com/microsoft-365/admin/contact-support-for-business-products?view=o365-worldwide&tabs=online)</span><span class="sxs-lookup"><span data-stu-id="63e3c-115">If you need help setting up phone numbers for your organization, please [contact Support Contact for Business Products - Admin Help](https://docs.microsoft.com/microsoft-365/admin/contact-support-for-business-products?view=o365-worldwide&tabs=online).</span></span>
  
## <a name="get-new-phone-numbers-for-your-users"></a><span data-ttu-id="63e3c-116">사용자에 대한 새 전화 번호 얻기</span><span class="sxs-lookup"><span data-stu-id="63e3c-116">Get new phone numbers for your users</span></span>

<span data-ttu-id="63e3c-117">![Microsoft Teams 로고를 나타내는 아이콘](media/teams-logo-30x30.png) **Microsoft Teams 관리 센터 사용**</span><span class="sxs-lookup"><span data-stu-id="63e3c-117">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

<span data-ttu-id="63e3c-118">이러한 정책을 관리하려면 전역 관리자 또는 Teams 서비스 관리자여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="63e3c-118">You must be a Teams service admin to make these changes.</span></span> <span data-ttu-id="63e3c-119">관리 역할 및 사용 권한 가져오기에 대한 내용은 [Teams 관리자 역할 사용](./using-admin-roles.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="63e3c-119">See [Use Teams administrator roles to manage Teams](./using-admin-roles.md) to read about getting admin roles and permissions.</span></span>

1. <span data-ttu-id="63e3c-120">Microsoft Teams 관리 센터로 이동하세요.</span><span class="sxs-lookup"><span data-stu-id="63e3c-120">Go to the Microsoft Teams Admin Center.</span></span>
2. <span data-ttu-id="63e3c-121">왼쪽 탐색에서 **음성** 전화 번호로  >  이동한 다음 **추가를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="63e3c-121">In the left navigation, go to **Voice** > **Phone numbers**, and then click **Add**.</span></span>
3. <span data-ttu-id="63e3c-122">주문 이름을 입력하고 설명을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="63e3c-122">Enter a name for the order and add a description.</span></span>
4. <span data-ttu-id="63e3c-123">위치 및 수량 페이지에서 다음을 합니다.</span><span class="sxs-lookup"><span data-stu-id="63e3c-123">On the Location and quantity page, do the following:</span></span>
    1. <span data-ttu-id="63e3c-124">국가 **또는 지역에서** 국가 또는 지역을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="63e3c-124">Under **Country or region**, select a country or region.</span></span>
    2. <span data-ttu-id="63e3c-125">숫자 **형식에서** **사용자(구독자)를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="63e3c-125">Under **Number type**, select **User (subscriber)**.</span></span>
    3. <span data-ttu-id="63e3c-126">위치 **아래에서** 위치를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="63e3c-126">Under **Location**, select a location.</span></span> <span data-ttu-id="63e3c-127">새 위치를 만들어야 하는 경우 위치 추가 **를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="63e3c-127">If you need to create a new location, click **Add a location**.</span></span>
    4. <span data-ttu-id="63e3c-128">영역 **코드에서** 영역 코드를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="63e3c-128">Under **Area code**, select an area code.</span></span>
    5. <span data-ttu-id="63e3c-129">**수량에서** 조직에 대해 원하는 숫자 수를 입력한  다음 다음을 클릭하여 숫자를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="63e3c-129">Under **Quantity**, enter the number of numbers that you want for your organization, and then click **Next** to select your numbers.</span></span>
5. <span data-ttu-id="63e3c-130">원하는 숫자를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="63e3c-130">Select the numbers you want.</span></span> <span data-ttu-id="63e3c-131">전화 번호를 선택하고 주문할 수 있는 10분이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63e3c-131">You have 10 minutes to select your phone numbers and place your order.</span></span> <span data-ttu-id="63e3c-132">10분 이상이면 전화 번호가 번호 풀로 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="63e3c-132">If you take more than 10 minutes, the phone numbers will be returned to the pool of numbers.</span></span>
6. <span data-ttu-id="63e3c-133">주문할 준비가 되면 주문 을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="63e3c-133">When you're ready to place your order, click **Place order**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="63e3c-134">사용자(구독자)의 전화 번호 수는 할당한 국내  통화 계획 및/또는 국내 및 국제 통화 요금제 라이선스의 총 수와 1.1을 곱한 값과 10개 추가 전화 번호와 동일합니다. </span><span class="sxs-lookup"><span data-stu-id="63e3c-134">The number of phone numbers for users (subscribers) is equal to the total number of **Domestic Calling Plan** and/or **Domestic and International Calling Plan** licenses you have assigned multiplied by 1.1, plus 10 additional phone numbers.</span></span> <span data-ttu-id="63e3c-135">예를 들어 국내 통화 요금제 및/또는 국내 및 국제 통화 계획으로 총 50명이 있는 경우 **65개** 전화 **번호(50 x 1.1 + 10)를** 획득할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63e3c-135">For example, if you have 50 users in total with a Domestic Calling Plan and/or Domestic and International Calling Plan, you can acquire **65** phone numbers **(50 x 1.1 + 10)**.</span></span> <span data-ttu-id="63e3c-136">자세한 내용은 받을 수 있는 전화 번호 [수?를 참조하세요.](./how-many-phone-numbers-can-you-get.md)</span><span class="sxs-lookup"><span data-stu-id="63e3c-136">For details, see [How many phone numbers can you get?](./how-many-phone-numbers-can-you-get.md).</span></span> <span data-ttu-id="63e3c-137">이보다 더 많은 전화 번호를 얻게 되는 경우 비즈니스 제품 지원 연락처 [- 관리자 도움말 에 문의하세요.](/microsoft-365/admin/contact-support-for-business-products?tabs=online&view=o365-worldwide)</span><span class="sxs-lookup"><span data-stu-id="63e3c-137">If you need to get more phone numbers than this, [contact Support Contact for Business Products - Admin Help](/microsoft-365/admin/contact-support-for-business-products?tabs=online&view=o365-worldwide).</span></span>
  
## <a name="port-or-transfer-phone-numbers-from-your-service-provider-or-phone-carrier"></a><span data-ttu-id="63e3c-138">서비스 공급자 또는 휴대폰 통신사에서 전화 번호 포트 또는 전송</span><span class="sxs-lookup"><span data-stu-id="63e3c-138">Port or transfer phone numbers from your service provider or phone carrier</span></span>
  
- <span data-ttu-id="63e3c-139">사용자에게 999개 이하의 전화 번호가 필요한 경우 Microsoft Teams 관리 센터에서 이식 마법사를 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="63e3c-139">If you need 999 or fewer phone numbers for your users, use the porting wizard in the Microsoft Teams Admin Center.</span></span> <span data-ttu-id="63e3c-140">Teams로 전화 [번호 전송의 단계를 따릅니다.](./phone-number-calling-plans/transfer-phone-numbers-to-teams.md)</span><span class="sxs-lookup"><span data-stu-id="63e3c-140">Follow the steps in [Transfer phone numbers to Teams](./phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span></span> <span data-ttu-id="63e3c-141">국가 또는 지역이 포링 마법사에 나열되지 [](phone-number-calling-plans/manually-submit-port-order.md) 않은 경우 포트 순서를 수동으로 제출하거나 조직에 대한 전화 번호 관리를 참조하여 올바른 LOA(인증 편지)를 다운로드할 수 있습니다. [](/microsoftteams/manage-phone-numbers-for-your-organization)</span><span class="sxs-lookup"><span data-stu-id="63e3c-141">If your country or region isn't listed in the porting wizard, you can [manually submit a port order](phone-number-calling-plans/manually-submit-port-order.md) or see [Manage phone numbers for your organization](/microsoftteams/manage-phone-numbers-for-your-organization) to download the correct Letter of Authorization (LOA).</span></span>

- <span data-ttu-id="63e3c-142">999개 이상의 전화 번호를 포트로 포트 [](phone-number-calling-plans/manually-submit-port-order.md) 주문해야 하는 경우 [](/microsoftteams/manage-phone-numbers-for-your-organization) 수동으로 포트 주문을 제출하거나 조직의 전화 번호 관리를 참조하여 올바른 LOA(인증 편지)를 다운로드한 다음 [PSTN](manage-phone-numbers-for-your-organization/contact-pstn-service-desk.md) 서비스 데스크에 보내 모든 번호를 전송할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63e3c-142">If you need to port more than 999 phone numbers, you can [manually submit a port order](phone-number-calling-plans/manually-submit-port-order.md) or see [Manage phone numbers for your organization](/microsoftteams/manage-phone-numbers-for-your-organization) to download the correct Letter of Authorization (LOA) and then send it to [the PSTN service desk](manage-phone-numbers-for-your-organization/contact-pstn-service-desk.md) to get all your numbers transferred.</span></span>

## <a name="view-the-phone-numbers-for-your-organization"></a><span data-ttu-id="63e3c-143">조직의 전화 번호 보기</span><span class="sxs-lookup"><span data-stu-id="63e3c-143">View the phone numbers for your organization</span></span>

<span data-ttu-id="63e3c-144">![Microsoft Teams 로고를 나타내는 아이콘](media/teams-logo-30x30.png) **Microsoft Teams 관리 센터 사용**</span><span class="sxs-lookup"><span data-stu-id="63e3c-144">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

<span data-ttu-id="63e3c-145">관리 센터의 왼쪽 탐색에서 음성 전화 번호로 이동하여 위치, 번호 유형 및 상태 정보를 포함하여 조직의 번호를  >   를 본다.</span><span class="sxs-lookup"><span data-stu-id="63e3c-145">In the left navigation of the admin center, go to **Voice** > **Phone numbers** to view the numbers for your organization, including location, number type, and status information.</span></span>
  
## <a name="assign-phone-numbers-to-users"></a><span data-ttu-id="63e3c-146">사용자에게 전화번호 할당</span><span class="sxs-lookup"><span data-stu-id="63e3c-146">Assign phone numbers to users</span></span>

<span data-ttu-id="63e3c-147">전화 번호를 얻은 후 각 사용자에게 번호를 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="63e3c-147">After you get your phone numbers, you'll need to assign a number to each of your users.</span></span> <span data-ttu-id="63e3c-148">자세한 [](./assign-change-or-remove-a-phone-number-for-a-user.md) 내용은 사용자에 대한 전화 번호 할당, 변경 또는 제거를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="63e3c-148">See [Assign, change, or remove a phone number for a user](./assign-change-or-remove-a-phone-number-for-a-user.md) for more information.</span></span>

> [!NOTE]
> <span data-ttu-id="63e3c-149">이보다 더 많은 전화 번호를 얻게 되는 경우 비즈니스 제품 지원 연락처 [- 관리자 도움말 에 문의하세요.](/microsoft-365/admin/contact-support-for-business-products?tabs=online&view=o365-worldwide)</span><span class="sxs-lookup"><span data-stu-id="63e3c-149">If you need to get more phone numbers than this, [contact Support Contact for Business Products - Admin Help](/microsoft-365/admin/contact-support-for-business-products?tabs=online&view=o365-worldwide).</span></span>

## <a name="related-topics"></a><span data-ttu-id="63e3c-150">관련 항목</span><span class="sxs-lookup"><span data-stu-id="63e3c-150">Related topics</span></span>

[<span data-ttu-id="63e3c-151">전화 번호 전송 자주 묻는 질문</span><span class="sxs-lookup"><span data-stu-id="63e3c-151">Transferring phone numbers common questions</span></span>](./phone-number-calling-plans/port-order-overview.md)

[<span data-ttu-id="63e3c-152">통화 계획에 사용되는 다양한 종류의 전화 번호</span><span class="sxs-lookup"><span data-stu-id="63e3c-152">Different kinds of phone numbers used for Calling Plans</span></span>](./different-kinds-of-phone-numbers-used-for-calling-plans.md)

[<span data-ttu-id="63e3c-153">조직의 전화 번호 관리</span><span class="sxs-lookup"><span data-stu-id="63e3c-153">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="63e3c-154">긴급 통화 사용 약관</span><span class="sxs-lookup"><span data-stu-id="63e3c-154">Emergency calling terms and conditions</span></span>](./emergency-calling-terms-and-conditions.md)

<span data-ttu-id="63e3c-155">[긴급 통화 고지 레이블](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="63e3c-155">[Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>