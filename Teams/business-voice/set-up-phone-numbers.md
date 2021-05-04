---
title: 전화 Microsoft 365 Business Voice 설정
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- Teams_Business_Voice
search.appverid: MET150
description: 조직의 사용자 및 서비스에 Microsoft 365 Business Voice 전화 번호를 설정하는 방법에 대해 자세히 알아보습니다.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6cec0bc8e55ef6be169de1f48a375ab40ca8ccf7
ms.sourcegitcommit: 49cdcf344c63c805bcb6365804c6f5d1393e926a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2021
ms.locfileid: "52130118"
---
# <a name="step-2-set-up-business-voice-phone-numbers"></a><span data-ttu-id="59d1b-103">2단계: 비즈니스 음성 전화 번호 설정</span><span class="sxs-lookup"><span data-stu-id="59d1b-103">Step 2: Set up Business Voice phone numbers</span></span>

<span data-ttu-id="59d1b-104">조직에서 사용자 또는 자동 참석자 를 설정하려면 먼저 해당 사용자에 대한 전화 번호를 얻게 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="59d1b-104">Before you can set up users or auto attendants in your organization, you need to get phone numbers for them.</span></span> <span data-ttu-id="59d1b-105">전화 번호에는 여러 가지 유형이 있습니다. 그러나 이 단계에서 추가해야 하는 두 가지 유형의 숫자는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="59d1b-105">There are several different types of phone numbers, however the following are the two types of numbers that you need to add in this step:</span></span>

- <span data-ttu-id="59d1b-106">**서비스 번호** 이러한 숫자는 자동 참석자, 오디오 회의 및 호출 큐에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="59d1b-106">**Service numbers** These numbers are used for auto attendants, audio conferencing, and call queues.</span></span> <span data-ttu-id="59d1b-107">이 번호는 무료 전화 또는 무료 번호일 수 있으며 동시에 많은 양의 통화를 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59d1b-107">They can be toll or toll-free numbers and can handle large amounts of calls at the same time.</span></span> <span data-ttu-id="59d1b-108">회사 전화 번호는 나중에 자동 담당자에 할당되어 있기 때문에 서비스 번호가 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="59d1b-108">Your company phone number needs to be a service number because it'll be assigned to an auto attendant in a later step.</span></span>
- <span data-ttu-id="59d1b-109">**구독자 번호** 이러한 숫자는 일반 사용자에게 사용 하여 전화를 걸고 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59d1b-109">**Subscriber numbers** These numbers are used for regular users so they can make and receive phone calls.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="59d1b-110">기존 전화 번호를 사용하려는 경우에도 회사의 주 전화선 및 사용자에게 임시 전화 번호를 만들고 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="59d1b-110">Even if you want to use your existing phone numbers, you need to create and assign temporary phone numbers to your company's main phone line and your users.</span></span> <span data-ttu-id="59d1b-111">나중에 이러한 임시 번호를 기존 전화 번호로 바꿀 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59d1b-111">You'll be able to replace these temporary numbers with your existing phone numbers in a later step.</span></span>

> [!NOTE]
> <span data-ttu-id="59d1b-112">새 전화 번호를 사용할 수 있도록 하는 데 몇 시간이 Teams.</span><span class="sxs-lookup"><span data-stu-id="59d1b-112">It may take several hours for your new phone numbers to become available in Teams.</span></span>

## <a name="set-up-a-service-number"></a><span data-ttu-id="59d1b-113">서비스 번호 설정</span><span class="sxs-lookup"><span data-stu-id="59d1b-113">Set up a service number</span></span>

<span data-ttu-id="59d1b-114">이제 설정한 서비스 번호는 회사의 주 전화 번호에 대한 이후 단계에서 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="59d1b-114">The service number you set up now will be used in a later step for your company's main phone number.</span></span>

1. <span data-ttu-id="59d1b-115">관리 센터 Microsoft Teams 로 이동하세요.</span><span class="sxs-lookup"><span data-stu-id="59d1b-115">Go to the Microsoft Teams Admin Center.</span></span>
2. <span data-ttu-id="59d1b-116">왼쪽 탐색에서 Voice   >  전화 번호로 이동한 다음 **추가를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="59d1b-116">In the left navigation, go to **Voice** > **Phone numbers**, and then click **Add**.</span></span>
3. <span data-ttu-id="59d1b-117">주문 이름을 입력하고 설명을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="59d1b-117">Enter a name for the order and add a description.</span></span>
4. <span data-ttu-id="59d1b-118">위치 및 수량 페이지에서 다음을 합니다.</span><span class="sxs-lookup"><span data-stu-id="59d1b-118">On the Location and quantity page, do the following:</span></span>
    1. <span data-ttu-id="59d1b-119">국가 **또는 지역에서** 국가 또는 지역을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="59d1b-119">Under **Country or region**, select a country or region.</span></span>
    2. <span data-ttu-id="59d1b-120">숫자 **형식에서** 다음 옵션 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="59d1b-120">Under **Number type**, select one of the following options:</span></span>

        - <span data-ttu-id="59d1b-121">**자동 참석자(Toll)** 일반, 비-무료 전화 번호.</span><span class="sxs-lookup"><span data-stu-id="59d1b-121">**Auto attendant (Toll)** Regular, non-toll-free, phone number.</span></span> <span data-ttu-id="59d1b-122">장거리 요금은 발신자에 청구됩니다.</span><span class="sxs-lookup"><span data-stu-id="59d1b-122">Long distance fees are charged to the caller.</span></span>
        - <span data-ttu-id="59d1b-123">**자동 참석자(무료)** 무료(미국 및 캐나다) 또는 무료 전화(영국) 전화 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="59d1b-123">**Auto attendant (Toll Free)** Toll-free (US and Canada) or freephone (UK) phone number.</span></span> <span data-ttu-id="59d1b-124">장거리 요금은 회사에 청구됩니다.</span><span class="sxs-lookup"><span data-stu-id="59d1b-124">Long distances fees are charged to your company.</span></span> <span data-ttu-id="59d1b-125">이 옵션을 선택하려면 먼저 통신 크레딧을 구입해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="59d1b-125">Before you can select this option, you need to purchase Communication Credits.</span></span> <span data-ttu-id="59d1b-126">자세한 내용은 사용하려면 구입해야 하는 [Microsoft 365 Business Voice.](what-to-buy.md)</span><span class="sxs-lookup"><span data-stu-id="59d1b-126">For more information, see [What do I need to buy to use Microsoft 365 Business Voice?](what-to-buy.md).</span></span>

    3. <span data-ttu-id="59d1b-127">**수량에서** **1 을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="59d1b-127">Under **Quantity**, select **1**.</span></span>
        > [!NOTE]
        > <span data-ttu-id="59d1b-128">이 유형의 더 많은 수를 요청할 수 있는 라이선스가 충분하지 않은 경우 비즈니스 음성 라이선스를 구입한지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="59d1b-128">If you get the message **You don't have enough licenses to request more numbers of this type**, make sure you've purchased Business Voice licenses.</span></span> <span data-ttu-id="59d1b-129">자세한 내용은 사용하려면 구입해야 하는 [Microsoft 365 Business Voice.](what-to-buy.md)</span><span class="sxs-lookup"><span data-stu-id="59d1b-129">For more information, see [What do I need to buy to use Microsoft 365 Business Voice?](what-to-buy.md).</span></span>
    4. <span data-ttu-id="59d1b-130">위치 **아래에서** 긴급 위치 설정 단계에서 만든 위치의 이름을 [입력합니다.](set-up-emergency-locations.md)</span><span class="sxs-lookup"><span data-stu-id="59d1b-130">Under **Location**, type the name of the location you created in the [Set up emergency locations](set-up-emergency-locations.md) step.</span></span>
    5. <span data-ttu-id="59d1b-131">영역 **코드에서** 영역 코드를 선택한 다음 다음을 **클릭하여** 숫자를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="59d1b-131">Under **Area code**, select an area code, and then click **Next** to select your numbers</span></span>
5. <span data-ttu-id="59d1b-132">원하는 숫자를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="59d1b-132">Select the number you want.</span></span> <span data-ttu-id="59d1b-133">전화 번호를 선택하고 주문할 수 있는 10분이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59d1b-133">You have 10 minutes to select your phone number and place your order.</span></span> <span data-ttu-id="59d1b-134">10분 이상이면 전화 번호가 번호 풀로 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="59d1b-134">If you take more than 10 minutes, the phone number will be returned to the pool of numbers.</span></span>
6. <span data-ttu-id="59d1b-135">주문할 준비가 됐을 때 주문 장소를 **클릭한** 다음 **마쳤습니다.**</span><span class="sxs-lookup"><span data-stu-id="59d1b-135">When you're ready to place your order, click **Place order**, and then **Finish**</span></span>

## <a name="set-up-phone-numbers-for-your-users"></a><span data-ttu-id="59d1b-136">사용자에 대한 전화 번호 설정</span><span class="sxs-lookup"><span data-stu-id="59d1b-136">Set up phone numbers for your users</span></span>

1. <span data-ttu-id="59d1b-137">관리 센터 Microsoft Teams 로 이동하세요.</span><span class="sxs-lookup"><span data-stu-id="59d1b-137">Go to the Microsoft Teams Admin Center.</span></span>
2. <span data-ttu-id="59d1b-138">왼쪽 탐색에서 Voice   >  전화 번호로 이동한 다음 **추가를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="59d1b-138">In the left navigation, go to **Voice** > **Phone numbers**, and then click **Add**.</span></span>
3. <span data-ttu-id="59d1b-139">주문 이름을 입력하고 설명을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="59d1b-139">Enter a name for the order and add a description.</span></span>
4. <span data-ttu-id="59d1b-140">위치 및 수량 페이지에서 다음을 합니다.</span><span class="sxs-lookup"><span data-stu-id="59d1b-140">On the Location and quantity page, do the following:</span></span>

    1. <span data-ttu-id="59d1b-141">국가 **또는 지역에서** 국가 또는 지역을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="59d1b-141">Under **Country or region**, select a country or region.</span></span>
    2. <span data-ttu-id="59d1b-142">숫자 **형식에서** **사용자(구독자)를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="59d1b-142">Under **Number type**, select **User (subscriber)**.</span></span>
    3. <span data-ttu-id="59d1b-143">수량 **아래에서** 조직에 대해 원하는 숫자 수를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="59d1b-143">Under **Quantity**, enter the number of numbers that you want for your organization.</span></span>
    4. <span data-ttu-id="59d1b-144">위치 **아래에서** 위치를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="59d1b-144">Under **Location**, select a location.</span></span> <span data-ttu-id="59d1b-145">긴급 위치 설정 단계에서 추가한 응급 [](set-up-emergency-locations.md) 위치를 선택하거나 다른 사무실 또는 홈 오피스에 대한 새 위치를 만들어야 하는 경우 위치 추가를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="59d1b-145">You can select either the emergency location you added in the [Set up emergency locations](set-up-emergency-locations.md) step, or if you need to create a new location for another office or a home office, click **Add a location**.</span></span>
    5. <span data-ttu-id="59d1b-146">영역 **코드에서** 영역 코드를 선택한 다음 다음을 **클릭하여** 숫자를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="59d1b-146">Under **Area code**, select an area code, and then click **Next** to select your numbers.</span></span>
5. <span data-ttu-id="59d1b-147">원하는 숫자를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="59d1b-147">Select the numbers you want.</span></span> <span data-ttu-id="59d1b-148">전화 번호를 선택하고 주문할 수 있는 10분이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59d1b-148">You have 10 minutes to select your phone numbers and place your order.</span></span> <span data-ttu-id="59d1b-149">10분 이상이면 전화 번호가 번호 풀로 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="59d1b-149">If you take more than 10 minutes, the phone numbers will be returned to the pool of numbers.</span></span>
6. <span data-ttu-id="59d1b-150">주문할 준비가 됐을 때 주문 장소를 **클릭한** 다음 을 **마쳤습니다.**</span><span class="sxs-lookup"><span data-stu-id="59d1b-150">When you're ready to place your order, click **Place order**, and then **Finish**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="59d1b-151">다음 단계: 사용자에게 라이선스 Teams 할당</span><span class="sxs-lookup"><span data-stu-id="59d1b-151">Next step: Assign licenses to Teams users</span></span>](set-up-licenses.md)
