---
title: 공용 영역 라이선스 전화 설정
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 12/13/2018
ms.reviewer: kponnus
ms.topic: article
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
description: '로비, 수신 공간 및 회의실에 대한 공용 영역 휴대폰을 설정하는 방법에 대해 자세히 알아보기 '
ms.openlocfilehash: bb17b21eac262c160abc3e16a4b552fb32b97d00
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117116"
---
# <a name="set-up-the-common-area-phone-license-for-microsoft-teams"></a><span data-ttu-id="92c30-103">공용 영역 전화 라이선스를 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="92c30-103">Set up the Common Area Phone license for Microsoft Teams</span></span>
> [!NOTE]
> <span data-ttu-id="92c30-104">공용 영역 전화는 음성메일을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="92c30-104">Common area phones do not support voicemail.</span></span>

<span data-ttu-id="92c30-105">일반적인 영역 전화는 일반적으로 로비 또는 전화를 걸 수 있는 다른 영역에 배치됩니다. 예를 들어 수신 영역, 로비 또는 전화 회의 전화가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92c30-105">A common area phone is typically placed in an area like a lobby or another area that is available to many people to make a call; for example, a reception area, lobby, or conference phone.</span></span> <span data-ttu-id="92c30-106">공용 영역 휴대폰은 공용 영역 라이선스에 묶인 계정으로 전화 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92c30-106">Common area phones are signed in with accounts tied to a Common Area Phone license.</span></span> <span data-ttu-id="92c30-107">또한 휴대폰에 공통 영역 사용자 환경을 하도록 TeamsIPPhone 정책을 적절하게 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="92c30-107">The TeamsIPPhone policy must also be appropriately set for the phone to have a common area user experience.</span></span>

<span data-ttu-id="92c30-108">아래 단계에서는 조직에 대한 공용 영역 휴대폰을 배포하기 위해 전화 시스템 계정을 설정하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="92c30-108">In the steps below, we'll help you set up an account for Phone System to deploy common area phones for your organization.</span></span> <span data-ttu-id="92c30-109">오디오 회의를 비롯한 보다 완전한 회의실 환경을 위해 회의실 디바이스로 전용 미팅룸 라이선스를 구입하는 것이 고려됩니다.</span><span class="sxs-lookup"><span data-stu-id="92c30-109">For a more complete meeting room experience, including audio conferencing, consider purchasing the dedicated Meeting Room license with a meeting room device.</span></span> 

<span data-ttu-id="92c30-110">먼저 CAP(Common Area 전화) 라이선스를 구입하고 인증된 휴대폰이 있는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="92c30-110">First, you need to purchase a Common Area Phone (CAP) license and make sure that you have a certified phone.</span></span> <span data-ttu-id="92c30-111">인증된 휴대폰을 검색하고 자세히 알아보시고자 하는 경우 을 Microsoft Teams [으로 이동합니다.](https://products.office.com/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1)</span><span class="sxs-lookup"><span data-stu-id="92c30-111">To search for and learn more about certified phones, go to [Microsoft Teams devices](https://products.office.com/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1).</span></span> 

## <a name="step-1---buy-the-licenses"></a><span data-ttu-id="92c30-112">1단계 - 라이선스 구매</span><span class="sxs-lookup"><span data-stu-id="92c30-112">Step 1 - Buy the licenses</span></span>

1. <span data-ttu-id="92c30-113">Microsoft 365 관리 센터에서 청구 구매 서비스로 이동한 다음 다른 요금제  >   **를 확장합니다.**</span><span class="sxs-lookup"><span data-stu-id="92c30-113">In the Microsoft 365 admin center, go to **Billing** > **Purchase services** and then expand **Other plans**.</span></span>

    ![공용 영역 타일을 보여 전화 스크린샷](media/set-up-common-area-phone-image1.png)

2. <span data-ttu-id="92c30-115">지금 **구입에서 전화**  >  **영역을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="92c30-115">Select **Common Area Phone** > **Buy now**.</span></span>

3. <span data-ttu-id="92c30-116">체크 아웃 페이지에서 지금 **구입을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="92c30-116">On the Checkout page, click **Buy now**.</span></span>

4. <span data-ttu-id="92c30-117">추가 **기능 구독을 확장한** 다음 클릭하고 통화 요금제 구입을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="92c30-117">Expand **Add-on subscriptions** and then click to buy a Calling Plan.</span></span> <span data-ttu-id="92c30-118">국내 통화  계획 또는 국내 및 국제 통화 계획 **중 하나를 선택 합니다.**</span><span class="sxs-lookup"><span data-stu-id="92c30-118">Choose either the **Domestic Calling Plan** or **Domestic and International Calling Plan**.</span></span>

> [!NOTE]
> <span data-ttu-id="92c30-119">시스템 직접 Microsoft 전화 사용하는 경우 통화 계획 라이선스가 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="92c30-119">If you are using Microsoft Phone System Direct Routing, you do not need a Calling Plan license.</span></span>

> [!NOTE]
> <span data-ttu-id="92c30-120">라이선스를 추가할 필요가 전화 시스템 없습니다.</span><span class="sxs-lookup"><span data-stu-id="92c30-120">You don't need to add a Phone System license.</span></span> <span data-ttu-id="92c30-121">공용 영역 라이선스에 전화 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92c30-121">It's included with the Common Area Phone license.</span></span>

<span data-ttu-id="92c30-122">라이선스에 대한 자세한 내용은 추가 Microsoft Teams 라이선스를 [참조하세요.](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)</span><span class="sxs-lookup"><span data-stu-id="92c30-122">For more information on licenses, see [Microsoft Teams add-on licensing](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>

<span data-ttu-id="92c30-123">공용 영역 전화 라이선스는 다음을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="92c30-123">The Common Area Phone license supports:</span></span> 


|   |  <span data-ttu-id="92c30-124">공용 영역 전화</span><span class="sxs-lookup"><span data-stu-id="92c30-124">Common Area Phone</span></span>  |
|---------|---------|
|<span data-ttu-id="92c30-125">비즈니스용 Skype</span><span class="sxs-lookup"><span data-stu-id="92c30-125">Skype for Business</span></span> |   <span data-ttu-id="92c30-126">&#x2714;</span><span class="sxs-lookup"><span data-stu-id="92c30-126">&#x2714;</span></span> |
|<span data-ttu-id="92c30-127">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="92c30-127">Microsoft Teams</span></span> |   <span data-ttu-id="92c30-128">&#x2714;</span><span class="sxs-lookup"><span data-stu-id="92c30-128">&#x2714;</span></span> |
|<span data-ttu-id="92c30-129">전화 시스템</span><span class="sxs-lookup"><span data-stu-id="92c30-129">Phone System</span></span> |    <span data-ttu-id="92c30-130">&#x2714;</span><span class="sxs-lookup"><span data-stu-id="92c30-130">&#x2714;</span></span> |
|<span data-ttu-id="92c30-131">오디오 회의</span><span class="sxs-lookup"><span data-stu-id="92c30-131">Audio Conferencing</span></span> |       <span data-ttu-id="92c30-132">&#x2718; &sup1;</span><span class="sxs-lookup"><span data-stu-id="92c30-132">&#x2718; &sup1;</span></span>  |
|<span data-ttu-id="92c30-133">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="92c30-133">Microsoft Intune</span></span> |    <span data-ttu-id="92c30-134">&#x2718;</span><span class="sxs-lookup"><span data-stu-id="92c30-134">&#x2718;</span></span> |
|<span data-ttu-id="92c30-135">전 세계 가용성</span><span class="sxs-lookup"><span data-stu-id="92c30-135">Worldwide Availability</span></span> |       <span data-ttu-id="92c30-136">&#x2718; &sup2;</span><span class="sxs-lookup"><span data-stu-id="92c30-136">&#x2718; &sup2;</span></span>  |
|<span data-ttu-id="92c30-137">채널 가용성</span><span class="sxs-lookup"><span data-stu-id="92c30-137">Channel Availability</span></span> |    <span data-ttu-id="92c30-138">EA, EAS, CSP, GCC, EES, Web Direct</span><span class="sxs-lookup"><span data-stu-id="92c30-138">EA, EAS, CSP, GCC, EES, Web Direct</span></span>  |
|      |         |

<span data-ttu-id="92c30-139">&sup1; 공통 영역 전화는 모임 이끌이가 제공하는 전화 접속 번호를 통해 오디오 회의에 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92c30-139">&sup1; Common Area Phones can join audio conferences via dial-in number provided by the meeting organizer</span></span>

<span data-ttu-id="92c30-140">&sup2; sovereign 클라우드에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="92c30-140">&sup2; Not available in sovereign clouds</span></span>  



## <a name="step-2---create-a-new-user-account-for-the-phone-and-assign-the-licenses"></a><span data-ttu-id="92c30-141">2단계 - 휴대폰에 대한 새 사용자 계정 만들기 및 라이선스 할당</span><span class="sxs-lookup"><span data-stu-id="92c30-141">Step 2 - Create a new user account for the phone and assign the licenses</span></span>

1. <span data-ttu-id="92c30-142">관리 Microsoft 365 활성 사용자로 이동하여 사용자를  >    >  **추가합니다.**</span><span class="sxs-lookup"><span data-stu-id="92c30-142">In the Microsoft 365 admin center, go to **users** > **active users** > **add a user**.</span></span>

2. <span data-ttu-id="92c30-143">이름의 "Main"과 같은 사용자 이름과 두 번째 이름의 "수신"을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="92c30-143">Enter a user name like "Main" for the first name and "Reception" for the second name.</span></span>

3. <span data-ttu-id="92c30-144">"Main Reception"처럼 자동으로 자생하지 않는 경우 표시 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="92c30-144">Enter a display name if it doesn't autogenerate one like "Main Reception."</span></span>

4. <span data-ttu-id="92c30-145">"MainReception" 또는 "Mainlobby"같은 사용자 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="92c30-145">Enter a user name like "MainReception" or "Mainlobby."</span></span>

5. <span data-ttu-id="92c30-146">공용 영역 휴대폰의 경우 암호를 수동으로 설정하거나 모든 공통 영역 휴대폰에 대해 동일한 암호를 설정해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92c30-146">For common area phones, you might want to set a password manually or have the same password for all your common area phones.</span></span> <span data-ttu-id="92c30-147">또한 이 사용자가 처음 로그인할 때 암호를 변경하도록 확인란을 **지우는 것이** 생각할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92c30-147">Also, you might think about clearing the **Make this user change their password when they first sign in** check box.</span></span>

6. <span data-ttu-id="92c30-148">사용자에게 라이선스를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="92c30-148">Assign the licenses to the user.</span></span> <span data-ttu-id="92c30-149">동일한 페이지에서 제품 **라이선스를 확장하려면 를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="92c30-149">On the same page, click to expand **Product licenses**.</span></span> <span data-ttu-id="92c30-150">공용 지역을 켜고 전화 국내 통화  계획 또는 국내 및 국제 전화 요금제 중 하나를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="92c30-150">Turn on the Common Area Phone and pick either a **Domestic Calling Plan** or a **Domestic and International Calling Plan**.</span></span> 

    ![라이선스 할당을 보여주는 스크린샷](media/set-up-common-area-phone-image2.png)

> [!NOTE]
> <span data-ttu-id="92c30-152">시스템 직접 Microsoft 전화 사용하는 경우 통화 계획 라이선스를 할당할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="92c30-152">If you are using Microsoft Phone System Direct Routing, you do not need to assign a Calling Plan license.</span></span>

<span data-ttu-id="92c30-153">자세한 내용은 사용자에게 [라이선스 할당을 참조하세요.](/microsoft-365/admin/manage/assign-licenses-to-users)</span><span class="sxs-lookup"><span data-stu-id="92c30-153">For more information, see [Assign licenses to users](/microsoft-365/admin/manage/assign-licenses-to-users).</span></span>

## <a name="step-3---assign-a-phone-number-to-the-common-area-phone-user-account"></a><span data-ttu-id="92c30-154">3단계 - 공용 영역 사용자 계정에 전화 전화 할당</span><span class="sxs-lookup"><span data-stu-id="92c30-154">Step 3 - Assign a phone number to the Common Area Phone user account</span></span>

<span data-ttu-id="92c30-155">관리자 Teams 관리 센터를 사용하여 사용자에게 번호를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="92c30-155">Use the Teams admin center to assign a number to the user.</span></span>

1. <span data-ttu-id="92c30-156">관리 Teams 에서 **Voice**  >  **전화 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="92c30-156">In the Teams admin center, select **Voice** > **Phone numbers**.</span></span>

3.    <span data-ttu-id="92c30-157">전화 번호 목록에서 숫자를 선택하고 **할당을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="92c30-157">Select a number from the list of phone numbers and click **Assign**.</span></span>

4. <span data-ttu-id="92c30-158">할당 **페이지에서** 음성 사용자 상자에 전화를 사용할 사용자의 이름을 입력한 다음 음성 사용자 드롭다운  목록에서 사용자를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="92c30-158">On the **Assign** page, in the Voice user box, type the name of the user who will be using the phone, and then select the user in the **Select a voice user** drop-down list.</span></span>

5. <span data-ttu-id="92c30-159">다음으로 긴급 주소를 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="92c30-159">Next, you need to add an emergency address.</span></span> <span data-ttu-id="92c30-160">도시로 **검색,** 설명 검색  **또는** 드롭다운 목록에서 위치 검색을 선택한 다음, 텍스트 상자에 도시, 설명 또는 위치를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="92c30-160">Choose **Search by city**, **Search by description**, or **Search by location** from the drop-down list, and then enter the city, description, or location in the text box.</span></span> <span data-ttu-id="92c30-161">검색하면 긴급 주소  선택 아래에서 적합한 주소를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="92c30-161">Once you search, look under **Select emergency address** to pick the right one for you.</span></span>

6. <span data-ttu-id="92c30-162">**저장을** 클릭하고 사용자는 다음과 같이 봐야 합니다.</span><span class="sxs-lookup"><span data-stu-id="92c30-162">Click **Save** and your user should look like this:</span></span>

   ![라이선스 할당을 보여주는 스크린샷](media/set-up-common-area-phone-image3.png)

> [!NOTE]
> <span data-ttu-id="92c30-164">사용자는 라이선스가 적용된 전화 시스템 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="92c30-164">Users will only show up if they have a Phone System license applied.</span></span> <span data-ttu-id="92c30-165">방금 이 경우 사용자가 목록에 표시하는 데 약간의 시간이 걸리는 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92c30-165">If you just did this, then sometimes it takes a bit for the user to show up in the list.</span></span>

<span data-ttu-id="92c30-166">자세한 내용은 사용자의 전화 [번호 보기를 참조하세요.](getting-phone-numbers-for-your-users.md)</span><span class="sxs-lookup"><span data-stu-id="92c30-166">For more information, see [Getting phone numbers for your users](getting-phone-numbers-for-your-users.md).</span></span>

<span data-ttu-id="92c30-167">다른 통신사 및 "포트"에 있는 전화 번호를 찍거나 전화 번호를 Microsoft 365 또는 Office 365.</span><span class="sxs-lookup"><span data-stu-id="92c30-167">You can also take your phone number that you have with another carrier and "port" or transfer it over to Microsoft 365 or Office 365.</span></span> <span data-ttu-id="92c30-168">전화 번호 전송을 [Teams.](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)</span><span class="sxs-lookup"><span data-stu-id="92c30-168">See [Transfer phone numbers to Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span></span>