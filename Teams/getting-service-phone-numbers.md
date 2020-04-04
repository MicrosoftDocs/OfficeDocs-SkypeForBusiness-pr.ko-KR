---
title: 서비스 전화 번호 가져오기
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: mikedav, jastark, oscarr, makolomi
ms.topic: article
ms.assetid: e434aeb2-af99-40e7-981e-a474f0383734
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Phone System
- seo-marvel-mar2020
description: 오디오 회의, 자동 전화 교환, 팀에 대 한 전화 대기열 (서비스 번호)에 대 한 새로운 전화 번호 및 포트를 확인 하거나 기존 번호를 전송 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: 9eb88d46a9e993067e7a2fc8baf9847dea5b32d7
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/03/2020
ms.locfileid: "43136718"
---
# <a name="getting-service-phone-numbers"></a><span data-ttu-id="30998-103">서비스 전화 번호 가져오기</span><span class="sxs-lookup"><span data-stu-id="30998-103">Getting service phone numbers</span></span>

<span data-ttu-id="30998-104">[사용자의 전화 번호를 받을](/microsoftteams/getting-phone-numbers-for-your-users)수 있을 뿐만 아니라 오디오 회의 (컨퍼런스), 자동 전화 교환, 통화 대기열 (서비스 번호 라고도 함) 등의 서비스에 대해 유료 또는 무료 전화 번호를 받을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30998-104">In addition to [getting phone numbers for your users](/microsoftteams/getting-phone-numbers-for-your-users), you can get toll or toll-free phone numbers for services such as Audio Conferencing (for conference bridges), auto attendants, and call queues (also called service numbers).</span></span> <span data-ttu-id="30998-105">서비스 전화 번호는 사용자 또는 구독자 전화 번호 보다 높은 동시 통화 용량을가지고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30998-105">Service phone numbers have a higher concurrent calling capacity than user or subscriber phone numbers.</span></span> <span data-ttu-id="30998-106">예를 들어 서비스 번호는 여러 개의 통화를 동시에 처리할 수 있지만, 사용자의 전화 번호는 일부 통화를 동시에 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30998-106">For example, a service number can handle hundreds of calls simultaneously, whereas a user's phone number can only handle a few calls simultaneously.</span></span>
  
> [!NOTE]
> <span data-ttu-id="30998-107">무료 전화 번호를 받으려면 먼저 통신 크레딧을 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="30998-107">You have to first set up Communications Credits before you can get toll-free numbers.</span></span> <span data-ttu-id="30998-108">자세한 내용은 [조직의 통신 크레딧 설정을](/microsoftteams/set-up-communications-credits-for-your-organization)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="30998-108">To learn more, see [Set up Communications Credits for your organization](/microsoftteams/set-up-communications-credits-for-your-organization).</span></span>
  
<span data-ttu-id="30998-109">서비스 번호는 세 가지 방법으로 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30998-109">There are three ways to get service numbers:</span></span>
  
- <span data-ttu-id="30998-110">**Microsoft 팀 관리 센터를 사용 합니다.**</span><span class="sxs-lookup"><span data-stu-id="30998-110">**Use the Microsoft Teams admin center.**</span></span> <span data-ttu-id="30998-111">일부 국가 및 지역의 경우 Microsoft 팀 관리 센터를 사용 하 여 서비스 번호를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30998-111">For some countries and regions, you can get service numbers using the Microsoft Teams admin center.</span></span> <span data-ttu-id="30998-112">[새 서비스 번호 받기를](#get-new-service-numbers)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="30998-112">See [Get new service numbers](#get-new-service-numbers).</span></span>

- <span data-ttu-id="30998-113">**기존 서비스 전화 번호 포팅하기**</span><span class="sxs-lookup"><span data-stu-id="30998-113">**Port your existing numbers.**</span></span> <span data-ttu-id="30998-114">현재 서비스 공급자 또는 전화 통신 회사에서 기존 번호를 이식 하거나 전송할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30998-114">You can port or transfer existing numbers from your current service provider or phone carrier.</span></span> <span data-ttu-id="30998-115">이 작업을 수행하는 데 도움이 되는 자세한 내용은 [Teams로 전화 번호 이전](/microsoftteams/phone-number-calling-plans/transfer-phone-numbers-to-teams) 또는 [조직에 대한 전화 번호 관리](/microsoftteams/manage-phone-numbers-for-your-organization)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="30998-115">See [Transfer phone numbers to Teams](/microsoftteams/phone-number-calling-plans/transfer-phone-numbers-to-teams) or [Manage phone numbers for your organization](/microsoftteams/manage-phone-numbers-for-your-organization) for more information to help you do this.</span></span>  
  
- <span data-ttu-id="30998-116">**새 전화 번호를 위한 요청 양식 사용하기**</span><span class="sxs-lookup"><span data-stu-id="30998-116">**Use a request form for new numbers.**</span></span> <span data-ttu-id="30998-117">또는 국가 또는 지역에 따라 Microsoft 팀 관리 센터를 사용 하 여 새 전화 번호를 받을 수 없거나, 특정 전화 번호 또는 지역 코드가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="30998-117">Sometimes (depending on your country or region) you won't be able to get your new phone numbers using the Microsoft Teams admin center, or you'll need specific phone numbers or area codes.</span></span> <span data-ttu-id="30998-118">그렇다면 양식을 다운로드 하 여 다시 전송 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="30998-118">If so, you'll need to download a form and send it back to us.</span></span> <span data-ttu-id="30998-119">자세한 내용은 [조직에서 전화번호 관리하기](/microsoftteams/manage-phone-numbers-for-your-organization)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="30998-119">See [Manage phone numbers for your organization](/microsoftteams/manage-phone-numbers-for-your-organization) for more information.</span></span>
  
> [!NOTE]
> <span data-ttu-id="30998-120">특정 번호에 대 한 높은 동시 통화 용량을 얻을 수 있도록 서비스 번호가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="30998-120">Service numbers are needed so you can get a higher concurrent call capacity for a specific number.</span></span> <span data-ttu-id="30998-121">번호로 전송 하는 경우 [PSTN 서비스 데스크에 연락](manage-phone-numbers-for-your-organization/contact-pstn-service-desk.md) 하 여 전송 하는 서비스 번호가 높은 동시 통화 용량을가지고 있는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30998-121">When you're transferring the number over to us, you can [contact the PSTN service desk](manage-phone-numbers-for-your-organization/contact-pstn-service-desk.md) to make sure the service number you're transferring has a high concurrent call capacity.</span></span>
  
## <a name="get-new-service-numbers"></a><span data-ttu-id="30998-122">새 서비스 번호 가져오기</span><span class="sxs-lookup"><span data-stu-id="30998-122">Get new service numbers</span></span>

<span data-ttu-id="30998-123">![Microsoft Teams 로고를 나타내는 아이콘](media/teams-logo-30x30.png) **Microsoft Teams 관리 센터 사용**</span><span class="sxs-lookup"><span data-stu-id="30998-123">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="30998-124">왼쪽 탐색 창에서 **음성** > **전화 번호로**이동한 다음 **추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="30998-124">In the left navigation, go to **Voice** > **Phone numbers**, and then click **Add**.</span></span>
2. <span data-ttu-id="30998-125">주문 이름을 입력 하 고 원하는 경우 설명을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="30998-125">Enter a name for the order and if you want, add a description.</span></span>
3. <span data-ttu-id="30998-126">위치 및 수량 페이지에서 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="30998-126">On the Location and quantity page, do the following:</span></span>
    1. <span data-ttu-id="30998-127">**국가 또는 지역**에서 국가 또는 지역을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="30998-127">Under **Country or region**, select a country or region.</span></span>
    1. <span data-ttu-id="30998-128">**숫자 형식**에서 원하는 서비스 번호 유형을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="30998-128">Under **Number type**, select the type of service number that you want.</span></span>
    1. <span data-ttu-id="30998-129">**위치**에서 위치를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="30998-129">Under **Location**, select a location.</span></span> <span data-ttu-id="30998-130">새 위치를 만들어야 할 경우 **위치 추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="30998-130">If you need to create a new location, click **Add a location**.</span></span>
    1. <span data-ttu-id="30998-131">**지역 번호**에서 지역 번호를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="30998-131">Under **Area code**, select an area code.</span></span> 
    2. <span data-ttu-id="30998-132">**수량**에서 조직에 사용할 숫자의 개수를 입력 하 고 **다음** 을 클릭 하 여 번호를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="30998-132">Under **Quantity**, enter the number of numbers that you want for your organization, and then click **Next** to select your numbers.</span></span>
4. <span data-ttu-id="30998-133">원하는 숫자를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="30998-133">Select the numbers you want.</span></span> <span data-ttu-id="30998-134">전화 번호를 선택 하 고 주문을 하는 데 10 분이 걸립니다.</span><span class="sxs-lookup"><span data-stu-id="30998-134">You have 10 minutes to select your phone numbers and place your order.</span></span> <span data-ttu-id="30998-135">10 분 이상 소요 되는 경우 전화 번호는 숫자의 풀로 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="30998-135">If you take more than 10 minutes, the phone numbers will be returned to the pool of numbers.</span></span>
5. <span data-ttu-id="30998-136">주문을 추가할 준비가 되 면 **주문을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="30998-136">When you're ready to place your order, click **Place order**.</span></span>

## <a name="port-or-transfer-existing-service-numbers"></a><span data-ttu-id="30998-137">기존 서비스 번호 포트 또는 전송</span><span class="sxs-lookup"><span data-stu-id="30998-137">Port or transfer existing service numbers</span></span>

<span data-ttu-id="30998-138">전화 번호를 현재 서비스 공급자 또는 통신 회사에서 팀으로 이전 하기 위해 Microsoft 팀 관리 센터의 포팅 마법사를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30998-138">To transfer your phone numbers from your current service provider or carrier to Teams, you can use the porting wizard in the Microsoft Teams admin center.</span></span> <span data-ttu-id="30998-139">[전화 번호를 팀에 게 전송](/microsoftteams/phone-number-calling-plans/transfer-phone-numbers-to-teams)의 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="30998-139">Follow the steps in [Transfer phone numbers to Teams](/microsoftteams/phone-number-calling-plans/transfer-phone-numbers-to-teams).</span></span>

<span data-ttu-id="30998-140">사용자의 국가 또는 지역이 포팅 마법사에 나열 되어 있지 않은 경우 [수동으로 포트 순서를 제출](phone-number-calling-plans/manually-submit-port-order.md) 하거나 [조직의 전화 번호 관리](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)로 이동 하 여 사용자의 국가 또는 지역을 선택한 다음 승인 문자 (LOA)를 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30998-140">If your country or region isn't listed in the porting wizard, you can [manually submit a port order](phone-number-calling-plans/manually-submit-port-order.md) or go to [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md), select your country or region, and then download a Letter of Authorization (LOA).</span></span> <span data-ttu-id="30998-141">LOA를 사용 하 여 전송할 각 서비스 번호 유형 (예: 유료 및 무료)에 대해 별도의 포트 주문을 제출 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="30998-141">You'll have to submit separate port orders for each type of service number (for example, toll vs. toll-free) that you'll be transferring by using an LOA.</span></span> <span data-ttu-id="30998-142">LOA에서 올바른 유형의 서비스 번호를 선택 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="30998-142">In the LOA, you must select the correct type of service number.</span></span> <span data-ttu-id="30998-143">사용자 또는 구독자 번호가 아닌 서비스 번호를 전송 하 고 있는지 확인 하 고, 동시 호출 용량이 통화 볼륨을 처리 하기에 충분 하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30998-143">Make sure you specify that you're transferring a service number (and not a user or subscriber number), or the concurrent calling capacity may not be enough to handle call volumes.</span></span>  

> [!NOTE]
> <span data-ttu-id="30998-144">이 보다 더 많은 전화 번호를 받으려면 [PSTN 서비스 데스크에 문의 하세요](manage-phone-numbers-for-your-organization/contact-pstn-service-desk.md).</span><span class="sxs-lookup"><span data-stu-id="30998-144">If you need to get more phone numbers than this, [contact the PSTN service desk](manage-phone-numbers-for-your-organization/contact-pstn-service-desk.md).</span></span>

## <a name="view-the-phone-numbers-for-your-organization"></a><span data-ttu-id="30998-145">조직의 전화 번호 보기</span><span class="sxs-lookup"><span data-stu-id="30998-145">View the phone numbers for your organization</span></span>

<span data-ttu-id="30998-146">![Microsoft Teams 로고를 나타내는 아이콘](media/teams-logo-30x30.png) **Microsoft Teams 관리 센터 사용**</span><span class="sxs-lookup"><span data-stu-id="30998-146">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span> 

<span data-ttu-id="30998-147">왼쪽 탐색 창에서 **음성** > **전화 번호로** 이동 하 여 위치, 번호 형식, 상태 정보를 비롯 한 조직의 번호를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="30998-147">In the left navigation, go to **Voice** > **Phone numbers** to view the numbers for your organization, including location, number type, and status information.</span></span>

## <a name="assign-service-phone-numbers"></a><span data-ttu-id="30998-148">서비스 전화 번호 할당</span><span class="sxs-lookup"><span data-stu-id="30998-148">Assign service phone numbers</span></span>

<span data-ttu-id="30998-149">서비스 번호를 받은 후 각 번호를 오디오 회의 브리지에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="30998-149">After you get your service numbers, assign each number to an Audio Conferencing bridge.</span></span> <span data-ttu-id="30998-150">[오디오 회의 브리지에서 유료 또는 무료 전화 번호 변경을](/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="30998-150">See [Change the toll or toll free numbers on your Audio Conferencing bridge](/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge).</span></span>

## <a name="related-topics"></a><span data-ttu-id="30998-151">관련 항목</span><span class="sxs-lookup"><span data-stu-id="30998-151">Related topics</span></span>

[<span data-ttu-id="30998-152">다음은 전화 시스템 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="30998-152">Here's what you get with Phone System</span></span>](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[<span data-ttu-id="30998-153">전화 번호 전송 자주 묻는 질문</span><span class="sxs-lookup"><span data-stu-id="30998-153">Transferring phone numbers common questions</span></span>](/microsoftteams/transferring-phone-numbers-common-questions)

[<span data-ttu-id="30998-154">통화 요금제에 사용 되는 다른 종류의 전화 번호</span><span class="sxs-lookup"><span data-stu-id="30998-154">Different kinds of phone numbers used for Calling Plans</span></span>](/microsoftteams/different-kinds-of-phone-numbers-used-for-calling-plans)

[<span data-ttu-id="30998-155">조직의 전화 번호 관리</span><span class="sxs-lookup"><span data-stu-id="30998-155">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="30998-156">오디오 회의 및 통화 플랜의 국가 및 지역 가용성</span><span class="sxs-lookup"><span data-stu-id="30998-156">Country and region availability for Audio Conferencing and Calling Plans</span></span>](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)
