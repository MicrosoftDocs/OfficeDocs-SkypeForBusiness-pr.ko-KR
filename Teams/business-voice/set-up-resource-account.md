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
ms.openlocfilehash: 618f26394f2b4acc44d56b814bd31c20ffe1a370
ms.sourcegitcommit: 32e3bb588abcbeded2d885483384c06706b280eb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2021
ms.locfileid: "52282780"
---
# <a name="step-4-set-up-a-business-voice-resource-account"></a><span data-ttu-id="9443b-103">4단계: 비즈니스 음성 리소스 계정 설정</span><span class="sxs-lookup"><span data-stu-id="9443b-103">Step 4: Set up a Business Voice resource account</span></span>

<span data-ttu-id="9443b-104">리소스 계정은 특정 사용자에게 할당되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9443b-104">Resource accounts aren't assigned to any specific user.</span></span> <span data-ttu-id="9443b-105">대신 무료 가상 사용자 라이선스를 사용하는 리소스 계정은 가상 사용자 라이선스의 디바이스 및 서비스에 Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9443b-105">Instead, resource accounts, which use a free virtual user license, are used by devices and services in Microsoft 365.</span></span> <span data-ttu-id="9443b-106">이 Microsoft Teams 리소스 계정은 전화 번호가 할당된 다음 자동 참석자 및 통화 큐와 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="9443b-106">In Microsoft Teams, resource accounts are assigned phone numbers and are then associated with auto attendants and call queues.</span></span>

<span data-ttu-id="9443b-107">리소스 계정을 자동 참석자에 연결하고 큐를 호출하면 하나 이상의 무료 전화 번호를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9443b-107">By associating resource accounts to auto attendants and call queues, you can add one or more toll or toll-free phone numbers to them.</span></span> <span data-ttu-id="9443b-108">예를 들어 한 리소스 계정을 로컬 호출자에 대한 자동 참석자에 전화 번호와 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9443b-108">For example, you could associate one resource account with a toll number to an auto attendant for local callers.</span></span> <span data-ttu-id="9443b-109">장거리 통화의 경우 다른 리소스 계정을 무료 전화 번호와 동일한 자동 참석자에 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9443b-109">For long distance calls, you could associate another resource account with a toll-free number to the same auto attendant.</span></span>

<span data-ttu-id="9443b-110">이 문서의 섹션에서는 리소스 계정을 설정한 다음 전화 번호를 할당하는 방법을 보여 니다.</span><span class="sxs-lookup"><span data-stu-id="9443b-110">The sections in this article show you how to set up a resource account and then assign a phone number to it.</span></span> <span data-ttu-id="9443b-111">나중에 리소스 계정을 자동 참석자와 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="9443b-111">Later on, you'll associate the resource account with an auto attendant.</span></span>

## <a name="obtain-virtual-user-licenses"></a><span data-ttu-id="9443b-112">가상 사용자 라이선스 획득</span><span class="sxs-lookup"><span data-stu-id="9443b-112">Obtain virtual user licenses</span></span>

<span data-ttu-id="9443b-113">리소스 계정에는 자동 참석자 및 호출 큐를 사용하려면 라이선스가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="9443b-113">Resource accounts require a license in order to work with auto attendants and call queues.</span></span> <span data-ttu-id="9443b-114">가상 사용자 라이선스 - Microsoft 365 전화 시스템 *사용할 수* 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9443b-114">You can use a free *Microsoft 365 Phone System - Virtual User* license.</span></span>

> [!NOTE]
> <span data-ttu-id="9443b-115">비즈니스 음성 평가판 기간에 등록한 경우 다음 단계를 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9443b-115">You should only need to perform the following steps if you've signed up for a Business Voice trial period.</span></span> <span data-ttu-id="9443b-116">Business Voice 라이선스를 구입한 경우 가상 라이선스가 계정에 이미 적용되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9443b-116">If you purchased Business Voice licenses, virtual licenses should already be applied to your account.</span></span> 
>
> <span data-ttu-id="9443b-117">가상 라이선스가 이미 있는지 확인하려면 전역 Microsoft 365 계정을 사용하여 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="9443b-117">To see if you already have virtual licenses, log into Microsoft 365 using an account with Global admin permissions.</span></span> <span data-ttu-id="9443b-118">그런 다음 청구 > [로 이동합니다.](https://admin.microsoft.com/Adminportal/Home#/subscriptions)</span><span class="sxs-lookup"><span data-stu-id="9443b-118">Then go to Billing > [Your products](https://admin.microsoft.com/Adminportal/Home#/subscriptions).</span></span> <span data-ttu-id="9443b-119">가상 라이선스가 있는 경우 가상 사용자 Microsoft 365 전화 시스템 **표시됩니다.**</span><span class="sxs-lookup"><span data-stu-id="9443b-119">If you have virtual licenses, they'll appear as **Microsoft 365 Phone System - Virtual User**.</span></span>

1. <span data-ttu-id="9443b-120">Microsoft 365 관리자 센터를 열고 전역 관리자인 사용자와 로그인합니다(일반적으로 등록하는 데 사용한 Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9443b-120">Open the Microsoft 365 admin center and log in with a user that is a Global admin (this is usually the account you used to sign up for Microsoft 365).</span></span>
2. <span data-ttu-id="9443b-121">왼쪽 탐색 창에서 청구 <a href="https://admin.microsoft.com/Adminportal/Home#/catalog" target="_blank">   > </a>구매 서비스 추가 기능으로 이동하여 모든 추가 기능 제품  >    >  **보기 를 참조합니다.**</span><span class="sxs-lookup"><span data-stu-id="9443b-121">In the left navigation pane, go to <a href="https://admin.microsoft.com/Adminportal/Home#/catalog" target="_blank">**Billing** > **Purchase services**</a> > **Add-ons** > **See all Add-ons products**.</span></span>
3. <span data-ttu-id="9443b-122">끝까지 스크롤하여 가상 Microsoft 365 전화 시스템 **라이선스를 찾습니다.**</span><span class="sxs-lookup"><span data-stu-id="9443b-122">Scroll to the end to find the **Microsoft 365 Phone System – Virtual User** license.</span></span> <span data-ttu-id="9443b-123">세부 **정보를 선택한** 다음 **을 구입합니다.**</span><span class="sxs-lookup"><span data-stu-id="9443b-123">Select **Details**, then **Buy**.</span></span>
4. <span data-ttu-id="9443b-124">라이선스 구매 페이지에서 원하는 가상 사용자 라이선스 수를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9443b-124">On the license purchase page, select the number of virtual user licenses you want.</span></span> <span data-ttu-id="9443b-125">설정할 각 자동 참석자 및 통화 큐에 대해 하나의 가상 라이선스가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="9443b-125">You need one virtual license for each auto attendant and call queue you plan to set up.</span></span> <span data-ttu-id="9443b-126">더 많은 라이선스를 바로 구매하지 않고도 향후 더 많은 자동 참석자 및 통화 큐를 쉽게 설정할 수 있도록 5개 이상의 라이선스를 선택하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="9443b-126">We recommend selecting at least five licenses so you can easily set up more auto attendants and call queues in the future without having to purchase more licenses right away.</span></span>
5. <span data-ttu-id="9443b-127">라이선스가 없는 모든 사용자에게 자동으로 할당 **선택을 선택하지 않습니다.**</span><span class="sxs-lookup"><span data-stu-id="9443b-127">Uncheck **Automatically assign to all of your users with no licenses**.</span></span>
6. <span data-ttu-id="9443b-128">지금 **체크 아웃을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="9443b-128">Select **Check out now**.</span></span>
7. <span data-ttu-id="9443b-129">주문을 확인하고 다음 **,** 다음을 선택한 다음 **순서를 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="9443b-129">Confirm your order, select **Next**, and then **Place order**.</span></span>

> [!NOTE]
> <span data-ttu-id="9443b-130">비용이 0이라도  라이선스를 구입해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9443b-130">Keep in mind you must still  **Buy** the license even though it has a cost of zero.</span></span>

## <a name="create-a-resource-account"></a><span data-ttu-id="9443b-131">리소스 계정 만들기</span><span class="sxs-lookup"><span data-stu-id="9443b-131">Create a resource account</span></span>

<span data-ttu-id="9443b-132">가상 사용자 Microsoft 365 전화 시스템 *받은* 후 리소스 계정을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9443b-132">After you've received your *Microsoft 365 Phone System - Virtual User* license, you can create your resource account.</span></span>

![리소스 계정 사용자 인터페이스 추가 스크린샷](../media/resource-account-add.png)

1. <span data-ttu-id="9443b-134">Microsoft Teams 관리자 센터를 열고 전역 관리자인 사용자와 로그인합니다(일반적으로 등록하는 데 사용한 계정 Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9443b-134">Open the Microsoft Teams admin center and log in with a user that is a Global admin (this is usually the account you used to sign up for Microsoft 365).</span></span>
2. <span data-ttu-id="9443b-135">왼쪽 탐색 창에서 <a href="https://admin.teams.microsoft.com/company-wide-settings/resource-accounts" target="_blank"> **Org-wide 설정**  >  **리소스 계정으로 이동합니다.**</a></span><span class="sxs-lookup"><span data-stu-id="9443b-135">In the left navigation pane, go to <a href="https://admin.teams.microsoft.com/company-wide-settings/resource-accounts" target="_blank">**Org-wide settings** > **Resource accounts**</a>.</span></span>
3. <span data-ttu-id="9443b-136">**추가** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9443b-136">Select **Add**.</span></span>
4. <span data-ttu-id="9443b-137">리소스 계정 **추가 창에서** 표시 **이름** 및 사용자 이름 을 **입력합니다.**</span><span class="sxs-lookup"><span data-stu-id="9443b-137">In the **Add resource account** pane, fill out **Display name**, and then **Username**.</span></span> <span data-ttu-id="9443b-138">리소스 계정의 목적을 설명하기 위해 "기본 줄 자동 참석자"처럼 설명이 있는 표시 이름을 선택하세요.</span><span class="sxs-lookup"><span data-stu-id="9443b-138">Choose a descriptive display name such as "Main line auto attendant" to describe the purpose of the resource account.</span></span>
5. <span data-ttu-id="9443b-139">리소스 **계정 유형에서** **자동 참석 을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="9443b-139">In **Resource account type**, select **Auto attendant**.</span></span>
6. <span data-ttu-id="9443b-140">**저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9443b-140">Select **Save**.</span></span>

![리소스 계정 목록 스크린샷](../media/resource-accounts-auto-attendant-only-page.png)

## <a name="assign-a-license"></a><span data-ttu-id="9443b-142">라이선스 할당</span><span class="sxs-lookup"><span data-stu-id="9443b-142">Assign a license</span></span>

<span data-ttu-id="9443b-143">리소스 계정을 만든 후 가상 사용자 *Microsoft 365 전화 시스템* 라이선스 또는 전화 시스템 *할당해야* 합니다.</span><span class="sxs-lookup"><span data-stu-id="9443b-143">After you've created your resource account, you need to assign a *Microsoft 365 Phone System - Virtual User* license or *Phone System* license.</span></span>

![관리 센터에서 라이선스 사용자 인터페이스 할당 Microsoft 365 스크린샷](../media/resource-account-assign-virtual-user-license.png)

1. <span data-ttu-id="9443b-145">Microsoft 365 관리자 센터를 열고 전역 관리자인 사용자와 로그인합니다(일반적으로 등록하는 데 사용한 Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9443b-145">Open the Microsoft 365 admin center and log in with a user that is a Global admin (this is usually the account you used to sign up for Microsoft 365).</span></span>
1. <span data-ttu-id="9443b-146">왼쪽 탐색 창에서 사용자 활성 <a href="https://admin.microsoft.com/Adminportal/Home#/users" target="_blank"> **사용자로**  >  **이동합니다.**</a></span><span class="sxs-lookup"><span data-stu-id="9443b-146">In the left navigation pane, go to <a href="https://admin.microsoft.com/Adminportal/Home#/users" target="_blank">**Users** > **Active users**</a>.</span></span>
1. <span data-ttu-id="9443b-147">리소스 계정을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9443b-147">Select your resource account.</span></span>
1. <span data-ttu-id="9443b-148">라이선스 **및** 앱 탭의 라이선스에서 가상 **Microsoft 365 전화 시스템 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="9443b-148">On the **Licenses and Apps** tab, under **Licenses**, select **Microsoft 365 Phone System - Virtual User**.</span></span>
1. <span data-ttu-id="9443b-149">변경 **내용 저장을** 선택한 다음 **닫기 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="9443b-149">Select **Save changes** and then **Close**.</span></span>

## <a name="assign-a-service-number"></a><span data-ttu-id="9443b-150">서비스 번호 할당</span><span class="sxs-lookup"><span data-stu-id="9443b-150">Assign a service number</span></span>

![서비스 번호 사용자 인터페이스 할당 스크린샷](../media/resource-account-assign-phone-number.png)

1. <span data-ttu-id="9443b-152">Microsoft Teams 관리자 센터를 열고 전역 관리자인 사용자와 로그인합니다(일반적으로 등록하는 데 사용한 계정 Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9443b-152">Open the Microsoft Teams admin center and log in with a user that is a Global admin (this is usually the account you used to sign up for Microsoft 365).</span></span>
1. <span data-ttu-id="9443b-153">왼쪽 탐색 창에서 <a href="https://admin.teams.microsoft.com/company-wide-settings/resource-accounts" target="_blank"> **Org-wide 설정**  >  **리소스 계정으로 이동합니다.**</a></span><span class="sxs-lookup"><span data-stu-id="9443b-153">In the left navigation pane, go to <a href="https://admin.teams.microsoft.com/company-wide-settings/resource-accounts" target="_blank">**Org-wide settings** > **Resource accounts**</a>.</span></span>
1. <span data-ttu-id="9443b-154">방금 만든 리소스 계정을 선택한 다음 **할당/할당을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="9443b-154">Select the resource account you just created, and then click **Assign/unassign**.</span></span>
1. <span data-ttu-id="9443b-155">숫자 **전화 드롭다운에서** Online 을 **선택하세요.**</span><span class="sxs-lookup"><span data-stu-id="9443b-155">In the **Phone number type** dropdown, choose **Online**.</span></span>
1. <span data-ttu-id="9443b-156">할당된 전화 번호 **상자에서** 사용할 번호를 검색하고 추가를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="9443b-156">In the **Assigned phone number** box, search for the number you want to use and click **Add**.</span></span> <span data-ttu-id="9443b-157">국가 코드(예: **+1** 250 555 0012)를 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9443b-157">Be sure to include the country code (for example, **+1** 250 555 0012)</span></span>
1. <span data-ttu-id="9443b-158">**저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9443b-158">Click **Save**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="9443b-159">다음 단계: 사용자에게 전화 번호 할당</span><span class="sxs-lookup"><span data-stu-id="9443b-159">Next step: Assign phone numbers to your users</span></span>](set-up-assign-numbers.md)
