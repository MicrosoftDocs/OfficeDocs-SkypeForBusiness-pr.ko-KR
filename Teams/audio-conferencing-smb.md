---
title: 중소 기업에 맞게 오디오 회의 설정
ms.author: v-lanac
author: lanachin
manager: serdars
ms.reviewer: jonorton, tonysmit
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
- m365initiative-meetings
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
description: '휴대폰을 사용 하 여 모임에 전화 해야 하는 사용자를 위해 중소기업에서 오디오 회의를 설정 하는 방법을 알아봅니다. '
ms.openlocfilehash: 4c0d47246f8a321a91ea175e06279bfe147a634a
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/13/2020
ms.locfileid: "49031184"
---
# <a name="set-up-audio-conferencing-for-small-and-medium-businesses"></a><span data-ttu-id="9fba9-103">중소 기업에 맞게 오디오 회의 설정</span><span class="sxs-lookup"><span data-stu-id="9fba9-103">Set up Audio Conferencing for small and medium businesses</span></span>

<span data-ttu-id="9fba9-104">오디오 회의를 통해 다른 사용자는 자신의 모바일 장치 또는 컴퓨터에서 팀 앱을 사용 하는 대신 휴대폰을 사용 하 여 팀 회의에 통화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9fba9-104">With Audio Conferencing, people can call in to Teams meetings using a phone instead of using the Teams app on their mobile device or from their computer.</span></span>  

<span data-ttu-id="9fba9-105">최대 300 사용자가 있는 중소 규모의 기업 이거나 현재 오디오 회의 라이선스가 없는 경우 1 년 동안 오디오 회의를 무료로 이용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9fba9-105">If you're a small or medium-sized business with up to 300 users and you currently don’t have any Audio Conferencing licenses, you can get Audio Conferencing free for one year.</span></span> <span data-ttu-id="9fba9-106">이 무료 제안은 2020 년 10 월 1 일부 터 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9fba9-106">This free offer is available starting October 1, 2020.</span></span>

<span data-ttu-id="9fba9-107">오디오 회의 추가 기능 라이선스는 Microsoft 365 비즈니스 기본, 비즈니스 표준, 비즈니스 Premium, Enterprise E1 또는 Enterprise E3 라이선스가 있는 사용자에 게 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9fba9-107">The Audio Conferencing add-on license can be applied to users who have Microsoft 365 Business Basic, Business Standard, Business Premium, Enterprise E1, or Enterprise E3 licenses.</span></span> <span data-ttu-id="9fba9-108">자세히 알아보려면 [팀 추가 기능 라이선스](teams-add-on-licensing/microsoft-teams-add-on-licensing.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9fba9-108">To learn more, see [Teams add-on licenses](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)</span></span>

> [!NOTE]
> <span data-ttu-id="9fba9-109">Enterprise E5 나 Microsoft 365 Business Voice를 사용 하는 경우,이 라이선스에 오디오 회의가 이미 포함 되어 있기 때문에 무료 오디오 회의 혜택을 사용할 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9fba9-109">If you have Enterprise E5 or Microsoft 365 Business Voice, you won't be able to use the free Audio Conferencing offer because these licenses already include Audio Conferencing.</span></span>

<span data-ttu-id="9fba9-110">이 문서에서는 오디오 회의를 설정 하는 방법을 안내 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fba9-110">In this article, we'll walk you through how to set up Audio Conferencing.</span></span> <span data-ttu-id="9fba9-111">모임 일정을 계획하거나 주도하는 사용자들을 위해 오디오 회의를 설정하기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9fba9-111">You only need to set up Audio Conferencing for people who plan to schedule or lead meetings.</span></span> <span data-ttu-id="9fba9-112">모임에 전화를 거는 모임 참석자는 라이선스 또는 다른 설정이 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9fba9-112">Meeting attendees who call in to meetings don't need licenses or other setup.</span></span> <span data-ttu-id="9fba9-113">자세히 알아보려면 [오디오 회의](audio-conferencing-in-office-365.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9fba9-113">To learn more, see [Audio Conferencing](audio-conferencing-in-office-365.md).</span></span>

## <a name="set-up-audio-conferencing"></a><span data-ttu-id="9fba9-114">오디오 회의 설정</span><span class="sxs-lookup"><span data-stu-id="9fba9-114">Set up Audio Conferencing</span></span>

<span data-ttu-id="9fba9-115">오디오 회의를 설정 하면 모임 초대에 사용할 수 있도록 전화 번호가 자동으로 회의 브리지에 할당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9fba9-115">When you set up Audio Conferencing, a phone number is automatically assigned to your conferencing bridge so that it can be used in meeting invitations.</span></span> <span data-ttu-id="9fba9-116">회의 브리지의 기본 번호로 할당 된 전화 번호는 조직의 국가 또는 지역에서 1로 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9fba9-116">The phone number that's assigned as the default number of your conferencing bridge will be one from the country or region of your organization.</span></span> <span data-ttu-id="9fba9-117">이 전화번호는 시외 전화 번호 이며 장거리 요금이 부과 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9fba9-117">This phone number is a toll number, in which long-distance charges may apply.</span></span>

> [!NOTE]
> <span data-ttu-id="9fba9-118">무료 번호를 사용할 수도 있으며,이 경우 몇 가지 추가 단계가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fba9-118">You can also use a toll-free number, which requires a few additional steps.</span></span> <span data-ttu-id="9fba9-119">회의 브리지의 전화 번호에 대 한 자세한 내용은이 문서의 뒷부분에 나오는 [오디오 회의 전화 번호](#audio-conferencing-phone-numbers) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9fba9-119">To learn more about phone numbers for your conferencing bridge, see [Audio Conferencing phone numbers](#audio-conferencing-phone-numbers) later in this article.</span></span>

### <a name="step-1-get-audio-conferencing-licenses"></a><span data-ttu-id="9fba9-120">1 단계: 오디오 회의 라이선스 가져오기</span><span class="sxs-lookup"><span data-stu-id="9fba9-120">Step 1: Get Audio Conferencing licenses</span></span>

<span data-ttu-id="9fba9-121">모임을 담당할 각 사용자에 대 한 오디오 회의 라이선스를 하나 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="9fba9-121">Get one Audio Conferencing license for each person who will lead meetings.</span></span> <span data-ttu-id="9fba9-122">Microsoft 365 관리 센터를 사용 하 여이 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fba9-122">Use the Microsoft 365 admin center to do this.</span></span>

1. <span data-ttu-id="9fba9-123">Microsoft 365 관리 센터에서 **청구**  >  **구매 서비스로** 이동한 다음 페이지 맨 아래에 있는 **추가 기능** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fba9-123">In the Microsoft 365 admin center, go to **Billing** > **Purchase services** , and then at the bottom of the page, select **Add-ons**.</span></span>
2. <span data-ttu-id="9fba9-124">**Microsoft 365 오디오 회의 채택 프로 모션**  >  **정보** 를 선택한 다음 **지금 가져오기를** 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fba9-124">Select **Microsoft 365 Audio Conferencing Adoption Promo** > **Details** , and then select **Get now**.</span></span>
3. <span data-ttu-id="9fba9-125">모임 이끌이에게 필요한 라이선스 수를 입력 하 고 주문을 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fba9-125">Enter the number of licenses you need for your meeting organizers, and then complete your order.</span></span>

    :::image type="content" source="media/audio-conferencing-smb-add.png" alt-text="오디오 회의 채택 프로 모션 라이선스 스크린샷":::

    > [!NOTE]
    > <span data-ttu-id="9fba9-127">이 라이선스가 없는 모든 사용자에 게 자동으로 오디오 회의 라이선스를 할당할지 여부에 따라 **라이선스가 없는 모든 사용자에 게 자동으로 할당** 을 취소 하거나 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fba9-127">Clear or select the **Automatically assign to all of your users with no licenses** , depending on whether you want to automatically assign an Audio Conferencing license to all users who don't have this license.</span></span>

### <a name="step-2-assign-an-audio-conferencing-license-to-users-who-lead-meetings"></a><span data-ttu-id="9fba9-128">2 단계: 모임 리더를 담당할 사용자에 게 오디오 회의 라이선스 할당</span><span class="sxs-lookup"><span data-stu-id="9fba9-128">Step 2: Assign an Audio Conferencing license to users who lead meetings</span></span>

<span data-ttu-id="9fba9-129">모임을 받을 각 사용자에 게 라이선스를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fba9-129">Assign a license to each person who will lead meetings.</span></span> <span data-ttu-id="9fba9-130">Microsoft 365 관리 센터를 사용 하 여이 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fba9-130">Use the Microsoft 365 admin center to do this.</span></span>

#### <a name="assign-a-license-to-one-user"></a><span data-ttu-id="9fba9-131">한 명의 사용자에 게 라이선스 할당</span><span class="sxs-lookup"><span data-stu-id="9fba9-131">Assign a license to one user</span></span>

1. <span data-ttu-id="9fba9-132">Microsoft 365 관리 센터에서 **사용자**  >  **활성 사용자** 로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fba9-132">In the Microsoft 365 admin center, go to **Users** > **Active users**.</span></span>  
2. <span data-ttu-id="9fba9-133">라이선스를 할당 하려는 사용자의 행을 선택 하 고 창에서 **라이선스 및 앱** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fba9-133">Select the row of the user you want to assign the license to, and then in the pane, select **Licenses and Apps**.</span></span>
3. <span data-ttu-id="9fba9-134">**Microsoft 365 오디오 회의** 확인란을 선택 하 고 **변경 내용 저장** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fba9-134">Select the **Microsoft 365 Audio Conferencing** check box, and then select **Save changes**.</span></span>

#### <a name="assign-a-license-to-multiple-users"></a><span data-ttu-id="9fba9-135">여러 사용자에 게 라이선스 할당</span><span class="sxs-lookup"><span data-stu-id="9fba9-135">Assign a license to multiple users</span></span>

1. <span data-ttu-id="9fba9-136">Microsoft 365 관리 센터에서 **사용자**  >  **활성 사용자** 로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fba9-136">In the Microsoft 365 admin center, go to **Users** > **Active users**.</span></span>  
2. <span data-ttu-id="9fba9-137">라이선스를 할당 하려는 사용자 옆에 있는 원을 선택한 다음 **제품 라이선스 관리** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fba9-137">Select the circles next to the users you want to assign the license to, and then select **Manage product licenses**.</span></span>
3. <span data-ttu-id="9fba9-138">**제품 라이선스 관리** 창에서 **추가 할당** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fba9-138">In the **Manage product licenses** pane, select **Assign more**.</span></span>
4. <span data-ttu-id="9fba9-139">**Microsoft 365 오디오 회의** 확인란을 선택 하 고 **변경 내용 저장** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fba9-139">Select the **Microsoft 365 Audio Conferencing** check box, and then select **Save changes**.</span></span>  

## <a name="schedule-teams-meetings-in-outlook"></a><span data-ttu-id="9fba9-140">Outlook에서 팀 모임 예약</span><span class="sxs-lookup"><span data-stu-id="9fba9-140">Schedule Teams meetings in Outlook</span></span>

<span data-ttu-id="9fba9-141">이제 모임 이끌이가 Outlook에서 모임을 예약할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9fba9-141">Your meeting organizers can now schedule meetings in Outlook.</span></span> <span data-ttu-id="9fba9-142">Outlook에서 **일정** 으로 이동한 다음 **새 팀 모임** 단추를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fba9-142">In Outlook, go to **Calendar** , and then select the **New Teams meeting** button.</span></span> <span data-ttu-id="9fba9-143">모임 전화 접속 번호와 전화 회의 ID가 모임 참석자에 게 전송 되는 모임 초대에 자동으로 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9fba9-143">The meeting dial-in numbers and the conference ID are automatically added to the meeting invitation that's sent to meeting attendees.</span></span> <span data-ttu-id="9fba9-144">자세한 내용은 [Outlook에서 팀 모임 예약](https://support.microsoft.com/office/schedule-a-teams-meeting-from-outlook-883cc15c-580f-441a-92ea-0992c00a9b0f)을 참고 하세요.</span><span class="sxs-lookup"><span data-stu-id="9fba9-144">To learn more, see [Schedule a Teams meeting in Outlook](https://support.microsoft.com/office/schedule-a-teams-meeting-from-outlook-883cc15c-580f-441a-92ea-0992c00a9b0f).</span></span>

> [!NOTE]
> <span data-ttu-id="9fba9-145">원하는 경우, 모임 초대를 사용자 지정 하 여 회사 로고, 지원 웹사이트에 대 한 링크, 법적 고 지 사항, 텍스트 전용 바닥글을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9fba9-145">If you want, you can customize meeting invitations to add your company logo, links to your support website and legal disclaimer, and a text-only footer.</span></span> <span data-ttu-id="9fba9-146">자세히 알아보려면 [모임 초대 사용자 지정](meeting-settings-in-teams.md#customize-meeting-invitations)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9fba9-146">To learn more, see [Customize meeting invitations](meeting-settings-in-teams.md#customize-meeting-invitations).</span></span>

## <a name="audio-conferencing-phone-numbers"></a><span data-ttu-id="9fba9-147">오디오 회의 전화 번호</span><span class="sxs-lookup"><span data-stu-id="9fba9-147">Audio Conferencing phone numbers</span></span>

<span data-ttu-id="9fba9-148">회의 브리지에 사용할 수 있는 두 가지 유형의 숫자가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9fba9-148">There are two types of numbers that you can use for your conferencing bridge.</span></span> <span data-ttu-id="9fba9-149">**공유 번호** (이 문서 앞부분의 [오디오 회의 섹션 설정](#set-up-audio-conferencing) ) 또는 **전용 번호** 를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9fba9-149">You can use either **shared numbers** (as in the [Set up Audio Conferencing](#set-up-audio-conferencing) section earlier in this article) or **dedicated numbers**.</span></span> <span data-ttu-id="9fba9-150">각에 대 한 자세한 내용은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="9fba9-150">Here's more information about each.</span></span>

### <a name="shared-numbers"></a><span data-ttu-id="9fba9-151">공유 번호</span><span class="sxs-lookup"><span data-stu-id="9fba9-151">Shared numbers</span></span>

<span data-ttu-id="9fba9-152">공유 번호는 모든 조직에서 공유 하는 숫자입니다.</span><span class="sxs-lookup"><span data-stu-id="9fba9-152">A shared number is a number that's shared across all organizations.</span></span> <span data-ttu-id="9fba9-153">공유 번호는 유료 번호로, 오디오 회의를 설정할 때 자동으로 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9fba9-153">Shared numbers are toll numbers and are automatically assigned when you set up Audio Conferencing.</span></span>

<span data-ttu-id="9fba9-154">회의 브리지에 할당 된 기본 번호를 보려면 Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **모임**  >  **회의 브리지로** 이동한 다음 가장 가까운 위치에 대 한 번호를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="9fba9-154">To see the default number that's assigned to your conferencing bridge, in the left navigation of the Microsoft Teams admin center, go to **Meetings** > **Conference bridges** , and then find the number for the location that's nearest to you.</span></span>

### <a name="dedicated-numbers"></a><span data-ttu-id="9fba9-155">전용 번호</span><span class="sxs-lookup"><span data-stu-id="9fba9-155">Dedicated numbers</span></span>

<span data-ttu-id="9fba9-156">전용 번호는 사용자만 사용할 수 있는 숫자입니다.</span><span class="sxs-lookup"><span data-stu-id="9fba9-156">A dedicated number is a number that's available only to your users.</span></span> <span data-ttu-id="9fba9-157">전용 번호는 유료 번호 이거나 무료 전화 번호 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9fba9-157">A dedicated number can be a toll number or a toll-free number.</span></span> <span data-ttu-id="9fba9-158">전용 번호를 사용 하려면 먼저 번호를 받고 회의 브리지에 할당 한 다음 모임을 담당할 각 사용자에 게 번호를 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fba9-158">To use a dedicated number, you'll have to first get the number, assign it to your conferencing bridge, and then assign the number to each person who will lead meetings.</span></span>

<span data-ttu-id="9fba9-159">전용 번호를 얻을 수 있는 몇 가지 방법이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9fba9-159">There are a couple ways to get a dedicated number.</span></span> <span data-ttu-id="9fba9-160">Microsoft에서 번호를 가져오거나 현재 서비스 공급자에서 Microsoft로 기존 번호를 전송 (포트) 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9fba9-160">You can get a number from Microsoft or transfer (port) an existing number from your current service provider to Microsoft.</span></span> <span data-ttu-id="9fba9-161">이 작업을 수행 하는 방법에 대해 자세히 알아보려면 [서비스 번호 가져오기를](getting-service-phone-numbers.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9fba9-161">To learn more about how to do this, see [Getting service numbers](getting-service-phone-numbers.md).</span></span>

<span data-ttu-id="9fba9-162">무료 번호를 사용 하는 경우 먼저 모임을 담당할 각 사용자에 게 통신 크레딧 라이선스를 할당 해야 한다는 점에 유의 하세요.</span><span class="sxs-lookup"><span data-stu-id="9fba9-162">Keep in mind that if you use a toll-free number, you have to first assign a Communications Credits license to each person who will lead meetings.</span></span> <span data-ttu-id="9fba9-163">자세한 내용은 [조직의 통신 크레딧 설정을](set-up-communications-credits-for-your-organization.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9fba9-163">To learn more, see [Set up Communications Credits for your organization](set-up-communications-credits-for-your-organization.md).</span></span>

<span data-ttu-id="9fba9-164">번호를 받은 후에는 회의 브리지에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fba9-164">After you have your number, assign it to your conference bridge.</span></span> <span data-ttu-id="9fba9-165">Microsoft 팀 관리 센터를 사용 하 여이 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fba9-165">Use the Microsoft Teams admin center to do this.</span></span>

1. <span data-ttu-id="9fba9-166">Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **모임**  >  **회의 브리지로** 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fba9-166">In the left navigation of the Microsoft Teams admin center, go to **Meetings** > **Conference bridges**.</span></span>
2. <span data-ttu-id="9fba9-167">**추가** 를 선택한 다음 **유료 번호** 또는 무료 **전화 번호** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fba9-167">Select **Add** , and then select **Toll number** or **Toll-free number**.</span></span>
3. <span data-ttu-id="9fba9-168">**전화 번호 추가** 창에서 번호를 선택 하 고 **적용** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fba9-168">In the **Add phone number** pane, select the number, and then select **Apply**.</span></span>

<span data-ttu-id="9fba9-169">그런 다음 모임을 담당할 각 사용자에 게 번호를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fba9-169">Then, assign the number to each person who will lead meetings.</span></span> <span data-ttu-id="9fba9-170">Microsoft 팀 관리 센터를 사용 하 여이 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fba9-170">Use the Microsoft Teams admin center to do this.</span></span>

1. <span data-ttu-id="9fba9-171">Microsoft 팀 관리 센터의 왼쪽 탐색 창 **에서 사용자를 선택 하** 고 사용자의 표시 이름을 클릭 한 다음 **편집** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fba9-171">In the left navigation of the Microsoft Teams admin center, select **Users** , click the display name of the user, and select **Edit**.</span></span>
2. <span data-ttu-id="9fba9-172">**오디오 회의** 옆에 있는 **편집** 을 선택 하 고 **오디오 회의** 창의 **유료 전화 번호** 또는 무료 **전화** 번호 목록에서 숫자를 선택한 다음 **적용** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fba9-172">Select **Edit** next to **Audio Conferencing** , and then in the **Audio Conferencing** pane, select a number in the **Toll number** or **Toll-free** number lists, and then select **Apply**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="9fba9-173">관련 주제</span><span class="sxs-lookup"><span data-stu-id="9fba9-173">Related topics</span></span>

- [<span data-ttu-id="9fba9-174">오디오 회의</span><span class="sxs-lookup"><span data-stu-id="9fba9-174">Audio Conferencing</span></span>](audio-conferencing-in-office-365.md)
- [<span data-ttu-id="9fba9-175">팀에 대 한 오디오 회의 설정</span><span class="sxs-lookup"><span data-stu-id="9fba9-175">Set up Audio Conferencing for Teams</span></span>](set-up-audio-conferencing-in-teams.md)
- [<span data-ttu-id="9fba9-176">오디오 회의의 전화 번호</span><span class="sxs-lookup"><span data-stu-id="9fba9-176">Phone numbers for Audio Conferencing</span></span>](phone-numbers-for-audio-conferencing-in-teams.md)
- [<span data-ttu-id="9fba9-177">오디오 회의 일반적인 질문</span><span class="sxs-lookup"><span data-stu-id="9fba9-177">Audio Conferencing common questions</span></span>](audio-conferencing-common-questions.md)
- [<span data-ttu-id="9fba9-178">서비스 번호 가져오기</span><span class="sxs-lookup"><span data-stu-id="9fba9-178">Getting service numbers</span></span>](getting-service-phone-numbers.md)
- [<span data-ttu-id="9fba9-179">팀 추가 기능 라이선스</span><span class="sxs-lookup"><span data-stu-id="9fba9-179">Teams add-on licenses</span></span>](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
- [<span data-ttu-id="9fba9-180">사용자에 게 라이선스 할당</span><span class="sxs-lookup"><span data-stu-id="9fba9-180">Assign licenses to users</span></span>](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)
