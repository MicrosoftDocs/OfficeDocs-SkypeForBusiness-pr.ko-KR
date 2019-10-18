---
title: Microsoft 팀을 위한 공통 영역 전화 라이선스 설정
ms.author: lolaj
author: LolaJacobsen
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
f1keywords: None
ms.custom:
- Phone System
description: '로비, 수신 지역 및 회의실에 대 한 공통 영역 전화를 설정 하는 방법에 대해 알아봅니다. '
ms.openlocfilehash: fa25de7484d8ac70e924e750c4e7633bfc160c04
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2019
ms.locfileid: "37571596"
---
# <a name="set-up-the-common-area-phone-license-for-microsoft-teams"></a><span data-ttu-id="8b5e8-103">Microsoft 팀을 위한 공통 영역 전화 라이선스 설정</span><span class="sxs-lookup"><span data-stu-id="8b5e8-103">Set up the Common Area Phone license for Microsoft Teams</span></span>
> [!NOTE]
> <span data-ttu-id="8b5e8-104">일반 지역 전화는 보이스 메일을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8b5e8-104">Common area phones do not support voicemail.</span></span>

<span data-ttu-id="8b5e8-105">일반적으로 일반적인 지역 전화는 대기실 또는 여러 사람이 전화를 걸 수 있는 다른 영역과 같은 영역에 위치 합니다. 예를 들어 수신 영역, 대기실 또는 전화 회의 전화.</span><span class="sxs-lookup"><span data-stu-id="8b5e8-105">A common area phone is typically placed in an area like a lobby or another area which is available to many people to make a call; for example, a reception area, lobby, or conference phone.</span></span> <span data-ttu-id="8b5e8-106">일반적인 지역 전화는 사용자가 아닌 장치로 설정 되며 네트워크에 자동으로 로그인 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b5e8-106">Common area phones are set up as devices rather than users, and can automatically sign into a network.</span></span>

<span data-ttu-id="8b5e8-107">아래 단계에서는 전화 시스템의 계정을 설정 하 여 조직의 공통 영역 전화를 배포 하는 방법에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="8b5e8-107">In the steps below, we’ll help you set up an account for Phone System to deploy common area phones for your organization.</span></span> <span data-ttu-id="8b5e8-108">오디오 회의를 포함 하 여 더 완벽 한 회의실 환경을 보려면 회의실 장치를 사용 하 여 전용 회의실 라이선스를 구입 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="8b5e8-108">For a more complete meeting room experience, including audio conferencing, consider purchasing the dedicated Meeting Room license with a meeting room device.</span></span> 

<span data-ttu-id="8b5e8-109">가장 먼저 해야 할 일은 일반 CAP (지역 전화) 라이선스를 구입 하 여 인증 된 전화기를 보유 하 고 있는지 확인 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="8b5e8-109">The first things you need to do are purchase a Common Area Phone (CAP) license and make sure that you have a certified phone.</span></span> <span data-ttu-id="8b5e8-110">인증 된 휴대폰에 대 한 자세한 정보를 검색 하 고 자세한 내용을 보려면 [Microsoft 팀 장치로](https://products.office.com/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1)이동 하세요.</span><span class="sxs-lookup"><span data-stu-id="8b5e8-110">To search for and learn more about certified phones, go to [Microsoft Teams devices](https://products.office.com/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1).</span></span> 

## <a name="step-1---buy-the-licenses"></a><span data-ttu-id="8b5e8-111">1 단계-라이선스 구입</span><span class="sxs-lookup"><span data-stu-id="8b5e8-111">Step 1 - Buy the licenses</span></span>

1. <span data-ttu-id="8b5e8-112">Microsoft 365 관리 센터에서 **청구** > **구매 서비스로** 이동한 다음 **다른 요금제**를 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b5e8-112">In the Microsoft 365 admin center, go to **Billing** > **Purchase services** and then expand **Other plans**.</span></span>

    ![공통 영역 전화 타일을 보여 주는 스크린샷](media/set-up-common-area-phone-image1.png)

2. <span data-ttu-id="8b5e8-114">지금 **일반 지역 전화** > **구입**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b5e8-114">Select **Common Area Phone** > **Buy now**.</span></span>

3. <span data-ttu-id="8b5e8-115">**체크 아웃** 페이지에서 **지금 구입**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b5e8-115">On the **Checkout** page click **Buy now**.</span></span>

4. <span data-ttu-id="8b5e8-116">**추가 기능 구독** 을 확장 한 다음을 클릭 하 여 통화 요금제를 구입 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b5e8-116">Expand **Add-on subscriptions** and then click to buy a Calling Plan.</span></span> <span data-ttu-id="8b5e8-117">**국내 통화 요금제** 또는 **국내 및 국제 통화 요금제**중 하나를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b5e8-117">Choose either the **Domestic Calling Plan** or **Domestic and International Calling Plan**.</span></span>

> [!NOTE]
> <span data-ttu-id="8b5e8-118">전화 시스템 라이선스가 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8b5e8-118">You don't need a Phone System license.</span></span> <span data-ttu-id="8b5e8-119">일반 지역 전화 라이선스에 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b5e8-119">It's included with the Common Area Phone license.</span></span>

<span data-ttu-id="8b5e8-120">라이선스에 대 한 자세한 내용은 [Microsoft 팀 추가 기능 라이선스](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8b5e8-120">For more information on licenses, see [Microsoft Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>

<span data-ttu-id="8b5e8-121">일반 지역 전화 라이선스는 다음을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b5e8-121">The Common Area Phone license supports:</span></span> 


|   |  <span data-ttu-id="8b5e8-122">공통 지역 전화</span><span class="sxs-lookup"><span data-stu-id="8b5e8-122">Common Area Phone</span></span>  |
|---------|---------|
|<span data-ttu-id="8b5e8-123">비즈니스용 Skype</span><span class="sxs-lookup"><span data-stu-id="8b5e8-123">Skype for Business</span></span> |   <span data-ttu-id="8b5e8-124">&#x2714;</span><span class="sxs-lookup"><span data-stu-id="8b5e8-124">&#x2714;</span></span> |
|<span data-ttu-id="8b5e8-125">Microsoft 팀</span><span class="sxs-lookup"><span data-stu-id="8b5e8-125">Microsoft Teams</span></span> |   <span data-ttu-id="8b5e8-126">&#x2714;</span><span class="sxs-lookup"><span data-stu-id="8b5e8-126">&#x2714;</span></span> |
|<span data-ttu-id="8b5e8-127">전화 시스템</span><span class="sxs-lookup"><span data-stu-id="8b5e8-127">Phone Systems</span></span> |    <span data-ttu-id="8b5e8-128">&#x2714;</span><span class="sxs-lookup"><span data-stu-id="8b5e8-128">&#x2714;</span></span> |
|<span data-ttu-id="8b5e8-129">오디오 회의</span><span class="sxs-lookup"><span data-stu-id="8b5e8-129">Audio Conferencing</span></span> |       <span data-ttu-id="8b5e8-130">&#x2718; &sup1</span><span class="sxs-lookup"><span data-stu-id="8b5e8-130">&#x2718; &sup1;</span></span>  |
|<span data-ttu-id="8b5e8-131">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="8b5e8-131">Microsoft Intune</span></span> |        <span data-ttu-id="8b5e8-132">&#x2718; &sup2</span><span class="sxs-lookup"><span data-stu-id="8b5e8-132">&#x2718; &sup2;</span></span> |
|<span data-ttu-id="8b5e8-133">전세계 가용성</span><span class="sxs-lookup"><span data-stu-id="8b5e8-133">Worldwide Availability</span></span> |    <span data-ttu-id="8b5e8-134">&#x2714;</span><span class="sxs-lookup"><span data-stu-id="8b5e8-134">&#x2714;</span></span> |
|<span data-ttu-id="8b5e8-135">채널 가용성</span><span class="sxs-lookup"><span data-stu-id="8b5e8-135">Channel Availability</span></span> |    <span data-ttu-id="8b5e8-136">EA, EAS, CSP, GCC, EES, 웹 다이렉트</span><span class="sxs-lookup"><span data-stu-id="8b5e8-136">EA, EAS, CSP, GCC, EES, Web Direct</span></span>  |
|      |         |

<span data-ttu-id="8b5e8-137">&sup1 일반 지역 전화는 모임 이끌이가 제공 하는 전화 접속 번호를 통해 오디오 회의에 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b5e8-137">&sup1; Common Area Phones can join audio conferences via dial-in number provided by the meeting organizer</span></span>

<span data-ttu-id="8b5e8-138">&sup2 Sovereign 클라우드에서는 사용할 수 없음</span><span class="sxs-lookup"><span data-stu-id="8b5e8-138">&sup2; Not available in sovereign clouds</span></span>  



## <a name="step-2---create-a-new-user-account-for-the-phone-and-assign-the-licenses"></a><span data-ttu-id="8b5e8-139">2 단계-휴대폰에 대 한 새 사용자 계정 만들기 및 라이선스 할당</span><span class="sxs-lookup"><span data-stu-id="8b5e8-139">Step 2 - Create a new user account for the phone and assign the licenses</span></span>

1. <span data-ttu-id="8b5e8-140">Microsoft 365 관리 센터에서 사용자 > **활성 사용자** > 가 사용자를**추가** **하도록 이동**합니다.</span><span class="sxs-lookup"><span data-stu-id="8b5e8-140">In the Microsoft 365 admin center, go to **users** > **active users** > **add a user**.</span></span>

2. <span data-ttu-id="8b5e8-141">이름에 "Main"과 같은 사용자 이름을 입력 하 고 두 번째 이름에 대해 "수신"을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b5e8-141">Enter a user name like “Main" for the first name and "Reception” for the second name.</span></span>

3. <span data-ttu-id="8b5e8-142">"주요 수신"이 자동으로 생성 되지 않는 경우 표시 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b5e8-142">Enter a display name if it doesn't autogenerate one like "Main Reception."</span></span>

4. <span data-ttu-id="8b5e8-143">"MainReception" 또는 "Mainreception"와 같은 사용자 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b5e8-143">Enter a user name like "MainReception" or "Mainlobby."</span></span>

5. <span data-ttu-id="8b5e8-144">일반적인 지역 전화의 경우 암호를 수동으로 설정 하거나 모든 공통 지역 전화에 대해 같은 암호를 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="8b5e8-144">For common area phones, you might want to set a password manually or have the same password for all your common area phones.</span></span> <span data-ttu-id="8b5e8-145">또한 **이 사용자가 처음 로그인 할 때 암호를 변경 하도록 설정** 확인란의 선택을 취소 하는 방법을 고려해 야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b5e8-145">Also, you might think about clearing the **Make this user change their password when they first sign in** check box.</span></span>

6. <span data-ttu-id="8b5e8-146">사용자에 게 라이선스를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b5e8-146">Assign the licenses to the user.</span></span> <span data-ttu-id="8b5e8-147">동일한 페이지에서 **제품 라이선스**를 클릭 하 여 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b5e8-147">On the same page, click to expand **Product licenses**.</span></span> <span data-ttu-id="8b5e8-148">일반 지역 전화를 켜고 **국내 통화 요금제** 또는 **국내 및 국제 통화 요금제**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b5e8-148">Turn on the Common Area Phone and pick either a **Domestic Calling Plan** or a **Domestic and International Calling Plan**.</span></span> 

    ![라이선스 할당을 보여 주는 스크린샷](media/set-up-common-area-phone-image2.png)

<span data-ttu-id="8b5e8-150">자세한 내용은 [사용자 추가](https://docs.microsoft.com/office365/admin/add-users/add-users?redirectSourcePath=%252farticle%252f1970f7d6-03b5-442f-b385-5880b9c256ec&view=o365-worldwide)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8b5e8-150">For more information, see [Add a user](https://docs.microsoft.com/office365/admin/add-users/add-users?redirectSourcePath=%252farticle%252f1970f7d6-03b5-442f-b385-5880b9c256ec&view=o365-worldwide).</span></span>

## <a name="step-3---assign-a-phone-number-to-the-common-area-phone-user-account"></a><span data-ttu-id="8b5e8-151">3 단계-일반 지역 전화 사용자 계정에 전화 번호 지정</span><span class="sxs-lookup"><span data-stu-id="8b5e8-151">Step 3 - Assign a phone number to the Common Area Phone user account</span></span>

<span data-ttu-id="8b5e8-152">비즈니스용 Skype 관리 센터를 사용 하 여 사용자에 게 번호를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b5e8-152">Use the Skype for Business admin center to assign a number to the user.</span></span>

1. <span data-ttu-id="8b5e8-153">Microsoft 365 관리 센터에서 **관리 센터** > **팀 & Skype** > **레거시 포털**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b5e8-153">In the Microsoft 365 admin center, select **Admin centers** > **Teams & Skype** > **Legacy portal**.</span></span>

2. <span data-ttu-id="8b5e8-154">비즈니스용 Skype 관리 센터에서 **음성** > **전화 번호**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b5e8-154">In the Skype for Business admin center, select **Voice** > **Phone numbers**.</span></span>

3.  <span data-ttu-id="8b5e8-155">전화 번호 목록에서 번호를 선택 하 고 **할당**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b5e8-155">Select a number from the list of phone numbers and click **Assign**.</span></span>

4. <span data-ttu-id="8b5e8-156">**지정** 페이지의 음성 사용자 상자에 휴대폰을 사용 하는 사용자의 이름을 입력 한 다음 **음성 사용자 선택** 드롭다운 목록에서 사용자를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b5e8-156">On the **Assign** page, in the Voice user box, type the name of the user who will be using the phone, and then select the user in the **Select a voice user** drop-down list.</span></span>

5. <span data-ttu-id="8b5e8-157">여기서 긴급 주소를 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b5e8-157">While you're there you will need to add an emergency address.</span></span> <span data-ttu-id="8b5e8-158">**도시별로 검색**, **설명으로 검색**또는 드롭다운 목록에서 **위치를 기준으로 검색** 을 선택 하 고 텍스트 상자에 구/군/시, 설명 또는 위치를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b5e8-158">Choose **Search by city**, **Search by description**, or **Search by location** from the drop-down list, and then enter the city, description, or location in the text box.</span></span> <span data-ttu-id="8b5e8-159">검색 하 고 나 서 **긴급 주소 선택** 에서 바로 확인을 클릭 하 여 적절 하 게 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b5e8-159">Once you search, look under **Select emergency address** to pick the right one for you.</span></span>

6. <span data-ttu-id="8b5e8-160">**저장** 을 클릭 하면 사용자에 게 다음과 같은 모양이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8b5e8-160">Click **Save** and your user should look like this:</span></span>

   ![라이선스 할당을 보여 주는 스크린샷](media/set-up-common-area-phone-image3.png)

> [!NOTE]
> <span data-ttu-id="8b5e8-162">사용자에 게 전화 시스템 라이선스가 적용 된 경우에만 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8b5e8-162">Users will only show up if they have a Phone System license applied.</span></span> <span data-ttu-id="8b5e8-163">방금이 작업을 수행한 경우 사용자가 목록에 표시 되는 데 약간의 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b5e8-163">If you just did this, then sometimes it takes a bit for the user to show up in the list.</span></span>

<span data-ttu-id="8b5e8-164">자세한 내용은 [사용자의 전화 번호 가져오기를](/microsoftteams/getting-phone-numbers-for-your-users)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8b5e8-164">For more information, see [Getting phone numbers for your users](/microsoftteams/getting-phone-numbers-for-your-users).</span></span>

<span data-ttu-id="8b5e8-165">다른 통신 회사와 "포트"를 사용 하 여 전화 번호를 가져와 Office 365으로 양도할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b5e8-165">You can also take your phone number that you have with another carrier and "port" or transfer it over to Office 365.</span></span> <span data-ttu-id="8b5e8-166">[Office 365에 전화 번호 전송을](transfer-phone-numbers-to-office-365.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8b5e8-166">See [Transfer phone numbers to Office 365](transfer-phone-numbers-to-office-365.md).</span></span>


