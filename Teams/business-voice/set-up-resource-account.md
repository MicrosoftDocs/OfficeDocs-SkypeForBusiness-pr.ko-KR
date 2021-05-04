---
title: 리소스 계정 Microsoft 365 Business Voice 설정
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
description: 자동 참석자에 사용할 Microsoft 365 Business Voice 리소스 계정을 설정하는 방법에 대해 자세히 알아보습니다.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 76e91a650e9e72c21a39d292e32fe5ff8ecbf80b
ms.sourcegitcommit: 49cdcf344c63c805bcb6365804c6f5d1393e926a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2021
ms.locfileid: "52130439"
---
# <a name="step-4-set-up-a-business-voice-resource-account"></a><span data-ttu-id="7ee47-103">4단계: 비즈니스 음성 리소스 계정 설정</span><span class="sxs-lookup"><span data-stu-id="7ee47-103">Step 4: Set up a Business Voice resource account</span></span>

<span data-ttu-id="7ee47-104">Microsoft Teams 각 자동 참석자 또는 호출 큐에 대한 리소스 계정이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="7ee47-104">In Microsoft Teams, a resource account is required for each auto attendant or call queue.</span></span> <span data-ttu-id="7ee47-105">리소스 계정에 서비스 전화 번호가 할당될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ee47-105">Resource accounts may also be assigned service telephone numbers.</span></span> <span data-ttu-id="7ee47-106">자동 참석자 및 통화 큐에 전화 번호를 할당하여 외부의 Teams 전화 큐에 도달할 수 있도록 하는 방식입니다.</span><span class="sxs-lookup"><span data-stu-id="7ee47-106">This is how you assign phone numbers to auto attendants and call queues allowing callers from outside Teams to reach the auto attendant or call queue.</span></span>

## <a name="obtain-virtual-user-licenses"></a><span data-ttu-id="7ee47-107">가상 사용자 라이선스 획득</span><span class="sxs-lookup"><span data-stu-id="7ee47-107">Obtain virtual user licenses</span></span>

<span data-ttu-id="7ee47-108">리소스 계정에는 자동 참석자 및 호출 큐를 사용하려면 라이선스가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="7ee47-108">Resource accounts require a license in order to work with auto attendants and call queues.</span></span> <span data-ttu-id="7ee47-109">가상 사용자 라이선스 - Microsoft 365 전화 시스템 *사용할 수* 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ee47-109">You can use a free *Microsoft 365 Phone System - Virtual User* license.</span></span>

1. <span data-ttu-id="7ee47-110">Microsoft 365 관리 센터에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="7ee47-110">Sign in to the Microsoft 365 admin center.</span></span>
2. <span data-ttu-id="7ee47-111">청구 **구매**  >  **서비스**  >  **추가 기능으로 이동하여** 모든 추가 기능 제품  >  **보기**</span><span class="sxs-lookup"><span data-stu-id="7ee47-111">Go to **Billing** > **Purchase services** > **Add-ons** > **See all Add-ons products**</span></span>
3. <span data-ttu-id="7ee47-112">끝까지 스크롤하여 가상 Microsoft 365 전화 시스템 **라이선스를 찾습니다.**</span><span class="sxs-lookup"><span data-stu-id="7ee47-112">Scroll to the end to find the **Microsoft 365 Phone System – Virtual User** license.</span></span> <span data-ttu-id="7ee47-113">세부 **정보를 선택한** 다음 **을 구입합니다.**</span><span class="sxs-lookup"><span data-stu-id="7ee47-113">Select **Details**, then **Buy**.</span></span>
4. <span data-ttu-id="7ee47-114">라이선스 구매 페이지에서 원하는 가상 사용자 라이선스 수를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7ee47-114">On the license purchase page, select the number of virtual user licenses you want.</span></span> <span data-ttu-id="7ee47-115">설정할 각 자동 참석자 및 통화 큐에 대해 하나의 가상 라이선스가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="7ee47-115">You need one virtual license for each auto attendant and call queue you plan to set up.</span></span> <span data-ttu-id="7ee47-116">더 많은 라이선스를 바로 구매하지 않고도 향후 더 많은 자동 참석자 및 통화 큐를 쉽게 설정할 수 있도록 5개 이상의 라이선스를 선택하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="7ee47-116">We recommend selecting at least five licenses so you can easily set up more auto attendants and call queues in the future without having to purchase more licenses right away.</span></span>
5. <span data-ttu-id="7ee47-117">라이선스가 없는 모든 사용자에게 자동으로 할당 **선택을 선택하지 않습니다.**</span><span class="sxs-lookup"><span data-stu-id="7ee47-117">Uncheck **Automatically assign to all of your users with no licenses**.</span></span>
6. <span data-ttu-id="7ee47-118">지금 **체크 아웃을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="7ee47-118">Select **Check out now**.</span></span>
7. <span data-ttu-id="7ee47-119">주문을 확인하고 다음 **,** 다음을 선택한 다음 **순서를 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="7ee47-119">Confirm your order, select **Next**, and then **Place order**.</span></span>

> [!NOTE]
> <span data-ttu-id="7ee47-120">비용이 0이라도  라이선스를 구입해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ee47-120">Keep in mind you must still  **Buy** the license even though it has a cost of zero.</span></span>

## <a name="create-a-resource-account"></a><span data-ttu-id="7ee47-121">리소스 계정 만들기</span><span class="sxs-lookup"><span data-stu-id="7ee47-121">Create a resource account</span></span>

<span data-ttu-id="7ee47-122">가상 사용자 Microsoft 365 전화 시스템 *받은* 후 리소스 계정을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ee47-122">After you've received your *Microsoft 365 Phone System - Virtual User* license, you can create your resource account.</span></span>

![리소스 계정 사용자 인터페이스 추가 스크린샷](../media/resource-account-add.png)

1. <span data-ttu-id="7ee47-124">Teams 관리 센터에서 **Org-wide** 설정을 확장한 다음 리소스 계정을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="7ee47-124">In the Teams admin center, expand **Org-wide settings**, and then click **Resource accounts**.</span></span>
2. <span data-ttu-id="7ee47-125">**추가** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7ee47-125">Select **Add**.</span></span>
3. <span data-ttu-id="7ee47-126">리소스 계정 **추가 창에서** 표시 **이름** 및 사용자 이름 을 **입력합니다.**</span><span class="sxs-lookup"><span data-stu-id="7ee47-126">In the **Add resource account** pane, fill out **Display name**, and then **Username**.</span></span> <span data-ttu-id="7ee47-127">리소스 계정의 목적을 설명하기 위해 "기본 줄 자동 참석자"처럼 설명이 있는 표시 이름을 선택하세요.</span><span class="sxs-lookup"><span data-stu-id="7ee47-127">Choose a descriptive display name such as "Main line auto attendant" to describe the purpose of the resource account.</span></span>
4. <span data-ttu-id="7ee47-128">리소스 **계정 유형에서** **자동 참석 을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="7ee47-128">In **Resource account type**, select **Auto attendant**.</span></span>
5. <span data-ttu-id="7ee47-129">**저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7ee47-129">Select **Save**.</span></span>

![리소스 계정 목록 스크린샷](../media/resource-accounts-page.png)

## <a name="assign-a-license"></a><span data-ttu-id="7ee47-131">라이선스 할당</span><span class="sxs-lookup"><span data-stu-id="7ee47-131">Assign a license</span></span>

<span data-ttu-id="7ee47-132">리소스 계정을 만든 후 가상 사용자 *Microsoft 365 전화 시스템* 라이선스 또는 전화 시스템 *할당해야* 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ee47-132">After you've created your resource account, you need to assign a *Microsoft 365 Phone System - Virtual User* license or *Phone System* license.</span></span>

![관리 센터에서 라이선스 사용자 인터페이스 할당 Microsoft 365 스크린샷](../media/resource-account-assign-virtual-user-license.png)

1. <span data-ttu-id="7ee47-134">관리 Microsoft 365 사용자 활성 **사용자로**  >  **이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="7ee47-134">In the Microsoft 365 admin center, go to **Users** > **Active users**.</span></span>
2. <span data-ttu-id="7ee47-135">리소스 계정을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7ee47-135">Select your resource account.</span></span>
1. <span data-ttu-id="7ee47-136">라이선스 **및** 앱 탭의 라이선스에서 가상 **Microsoft 365 전화 시스템 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="7ee47-136">On the **Licenses and Apps** tab, under **Licenses**, select **Microsoft 365 Phone System - Virtual User**.</span></span>
1. <span data-ttu-id="7ee47-137">변경 **내용 저장을** 선택한 다음 **닫기 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="7ee47-137">Select **Save changes** and then **Close**.</span></span>

## <a name="assign-a-service-number"></a><span data-ttu-id="7ee47-138">서비스 번호 할당</span><span class="sxs-lookup"><span data-stu-id="7ee47-138">Assign a service number</span></span>

![서비스 번호 사용자 인터페이스 할당 스크린샷](../media/resource-account-assign-phone-number.png)

1. <span data-ttu-id="7ee47-140">Teams 관리 센터에서 **Org-wide 설정으로** 이동한 다음 **리소스 계정으로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="7ee47-140">In the Teams admin center, go to **Org-wide settings** and then **Resource accounts**.</span></span> 
1. <span data-ttu-id="7ee47-141">방금 만든 리소스 계정을 선택한 다음 **할당/할당을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="7ee47-141">Select the resource account you just created, and then click **Assign/unassign**.</span></span>
1. <span data-ttu-id="7ee47-142">숫자 **전화 드롭다운에서** Online 을 **선택하세요.**</span><span class="sxs-lookup"><span data-stu-id="7ee47-142">In the **Phone number type** dropdown, choose **Online**.</span></span>
1. <span data-ttu-id="7ee47-143">할당된 전화 번호 **상자에서** 사용할 번호를 검색하고 추가를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="7ee47-143">In the **Assigned phone number** box, search for the number you want to use and click **Add**.</span></span> <span data-ttu-id="7ee47-144">국가 코드(예: **+1** 250 555 0012)를 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ee47-144">Be sure to include the country code (for example, **+1** 250 555 0012)</span></span>
1. <span data-ttu-id="7ee47-145">**저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7ee47-145">Click **Save**.</span></span>
    > [!NOTE]
    > <span data-ttu-id="7ee47-146">번호를 추가할 자동 참석자가 이미 선택되어 있기 때문에 **할당에서** 자동 참석자를 선택할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7ee47-146">You don't need to select an auto attendant under **Assign to** because the auto attendant you want to add the number to is already selected.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="7ee47-147">다음 단계: 사용자에게 전화 번호 할당</span><span class="sxs-lookup"><span data-stu-id="7ee47-147">Next step: Assign phone numbers to your users</span></span>](set-up-assign-numbers.md)
