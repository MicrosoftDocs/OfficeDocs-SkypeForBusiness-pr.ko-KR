---
title: 서비스 전화 번호 가져오기
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: mikedav, jastark, oscarr, makolomi
ms.topic: article
ms.assetid: e434aeb2-af99-40e7-981e-a474f0383734
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Phone System
description: Office 365에서 사용자의 전화 번호를 가져올 수 있을 뿐만 아니라 오디오 회의 (컨퍼런스), 자동 전화 교환, 통화 대기열 (서비스 번호 라고도 함) 등의 서비스에 대 한 유료 또는 무료 전화 번호를 검색 하 고 받을 수도 있습니다. 서비스 전화 번호는 사용자 또는 구독자 전화 번호 보다 높은 동시 통화 용량을가지고 있습니다.
ms.openlocfilehash: a8cd5582cdcbddff1a6c6375230864e569111a0e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42031052"
---
# <a name="getting-service-phone-numbers"></a><span data-ttu-id="993a5-104">서비스 전화 번호 가져오기</span><span class="sxs-lookup"><span data-stu-id="993a5-104">Getting service phone numbers</span></span>

<span data-ttu-id="993a5-105">Office 365에서 사용자의 전화 번호를 가져올 수 있을 뿐만 아니라 오디오 회의 (컨퍼런스), 자동 전화 교환, 통화 대기열 (서비스 번호 라고도 함) 등의 서비스에 대 한 유료 또는 무료 전화 번호를 검색 하 고 받을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="993a5-105">In addition to getting phone numbers for your users from Office 365, you can search and acquire toll or toll-free phone numbers for services such as audio conferencing (for conference bridges), auto attendants, and call queues (also called service numbers).</span></span> <span data-ttu-id="993a5-106">서비스 전화 번호는 사용자 또는 구독자 전화 번호 보다 높은 동시 통화 용량을가지고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="993a5-106">Service phone numbers have a higher concurrent calling capacity than user or subscriber phone numbers.</span></span> <span data-ttu-id="993a5-107">예를 들어 서비스 번호는 통화를 동시에 한 번만 처리할 수 있지만, 사용자의 전화 번호는 일부 통화를 동시에 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="993a5-107">For example, a service number can handle 100s of calls simultaneously, whereas a user's phone number can only handle a few calls simultaneously.</span></span>
  
> [!NOTE]
> <span data-ttu-id="993a5-108">무료 전화 번호를 얻으려면 먼저 Office 365 통신 크레딧을 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="993a5-108">Office 365 Communications Credits must be set up first in order to acquire toll-free numbers.</span></span> <span data-ttu-id="993a5-109">[조직의 통신 크레딧 설정을](/microsoftteams/set-up-communications-credits-for-your-organization)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="993a5-109">See [Set up Communications Credits for your organization](/microsoftteams/set-up-communications-credits-for-your-organization).</span></span> 
  
<span data-ttu-id="993a5-110">다음과 같은 두 가지 방법으로 비즈니스용 Skype 및 Microsoft 팀에서 사용할 수 있도록 서비스 번호를 가져오는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="993a5-110">You have two ways of getting service numbers so you can use them with Skype for Business and Microsoft Teams:</span></span>
  
- <span data-ttu-id="993a5-111">Office 365에서 새 번호를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="993a5-111">Get new numbers from Office 365.</span></span>
    
- <span data-ttu-id="993a5-112">서비스 공급자 또는 전화 통신 회사에서 Office 365으로 기존 번호를 이식 하거나 전송 합니다.</span><span class="sxs-lookup"><span data-stu-id="993a5-112">Port or transfer your existing numbers from your service provider or phone carrier to Office 365.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="993a5-113">서비스 번호를 전송 하는 경우에는 [Microsoft 지원](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b) 에 문의 하 여 더 높은 수준의 동시 통화 용량을 올바르게 간주 하 고 구성 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="993a5-113">When you transfer your service numbers, it is highly recommended that you contact [Microsoft support](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b) to ensure that the higher concurrent calling capacity is considered and configured correctly.</span></span>
  
## <a name="get-new-service-numbers"></a><span data-ttu-id="993a5-114">새 서비스 번호 가져오기</span><span class="sxs-lookup"><span data-stu-id="993a5-114">Get new service numbers</span></span>

<span data-ttu-id="993a5-115">![비즈니스용 skype](media/sfb-logo-30x30.png) **관리 센터를 사용 하 여** 비즈니스용 skype 로고를 표시 하는 아이콘</span><span class="sxs-lookup"><span data-stu-id="993a5-115">![An icon showing the Skype for Business logo](media/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1. <span data-ttu-id="993a5-116">회사 또는 학교 계정으로 Office 365에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="993a5-116">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="993a5-117">**관리 센터** > **팀 및 skype** > **skype 레거시 관리자로**이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="993a5-117">Go to the **Admin center** > **Teams and Skype** > **Skype Legacy Admin**.</span></span>
    
3. <span data-ttu-id="993a5-118">왼쪽 탐색 창에서 **음성** > **전화 번호로** > 이동한 다음 새**번호를 추가**하 고 **새 서비스 번호**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="993a5-118">In the left navigation go to **Voice** > **Phone numbers** > **Add new number**, and then click **New service numbers**.</span></span>
    
    > [!IMPORTANT] 
    > <span data-ttu-id="993a5-119">비즈니스용 Skype 관리 센터의 왼쪽 탐색 창에서 **음성** 옵션을 보려면 먼저 하나 이상의 **Enterprise E5 라이선스**, 하나의 **전화 시스템** 추가 기능 라이선스 또는 하나의 **오디오 회의** 추가 기능 라이선스를 구입 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="993a5-119">For you to see the **Voice** option in the left navigation in the Skype for Business admin center, you must first buy at least one **Enterprise E5 license**, one **Phone System** add-on license, or one **Audio Conferencing** add-on license.</span></span>
    
4. <span data-ttu-id="993a5-120">**새 서비스 번호 추가** 페이지에서 다음을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="993a5-120">On the **Add new service numbers** page, choose the following:</span></span>
    
   - <span data-ttu-id="993a5-121">**국가/지역**</span><span class="sxs-lookup"><span data-stu-id="993a5-121">**Country/Region**</span></span>
    
   - <span data-ttu-id="993a5-122">**주/지역**</span><span class="sxs-lookup"><span data-stu-id="993a5-122">**State/Region**</span></span>
    
   - <span data-ttu-id="993a5-123">**곳**</span><span class="sxs-lookup"><span data-stu-id="993a5-123">**City**</span></span>
    
5. <span data-ttu-id="993a5-124">**수량**에서 조직에 사용할 전화 번호 수를 입력 하 고 **추가** 를 클릭 하 여 예약을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="993a5-124">Under **Quantity**, enter the number of phone numbers that you want for your organization and click **Add** to create a reservation.</span></span> <span data-ttu-id="993a5-125">전화 번호를 선택 하는 데 10 분이 소요 됩니다. 10 분 이상 소요 되는 경우 전화번호는 전화 번호 풀로 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="993a5-125">You have 10 minutes to select your phone numbers; if you take more than 10 minutes, the phone numbers will be returned to the pool of phone numbers.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="993a5-126">사용할 **수 있는 총 서비스 번호**옆에 나열 된 라이선스 수를 기준으로 하는 전화 번호의 수를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="993a5-126">You can see the number of phone numbers, which is based on the number of licenses, listed next to **Total Service numbers your can acquire**.</span></span> <span data-ttu-id="993a5-127">자세한 내용은 [받을 수 있는 전화 번호 수](/microsoftteams/how-many-phone-numbers-can-you-get) 를 확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="993a5-127">For details, see [How many phone numbers can you get?](/microsoftteams/how-many-phone-numbers-can-you-get)</span></span>
  
6. <span data-ttu-id="993a5-128">**숫자 표시** 를 클릭 하 여 전체 전화 번호 목록을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="993a5-128">You can click **Show numbers** to see the full list of phone numbers.</span></span> <span data-ttu-id="993a5-129">이 기능은 목록에서 특정 전화 번호를 선택 하지 않으려는 경우에 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="993a5-129">This is helpful if you don't want to select a specific phone number in the list.</span></span>
    
7. <span data-ttu-id="993a5-130">원하는 전화 번호를 선택한 다음 **번호 받기를**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="993a5-130">Select the phone numbers you want, and then click **Acquire numbers**.</span></span>
    
### <a name="assign-service-numbers"></a><span data-ttu-id="993a5-131">서비스 번호 할당</span><span class="sxs-lookup"><span data-stu-id="993a5-131">Assign service numbers</span></span>

<span data-ttu-id="993a5-132">서비스 번호를 찾았으면 오디오 회의 브리지에 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="993a5-132">Once you have your service numbers, they can then be assigned to an audio conferencing bridge.</span></span> <span data-ttu-id="993a5-133">이렇게 하려면 [오디오 회의 브리지에서 무료 또는 유료 번호 변경을](/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="993a5-133">To do this, see [Change the toll or toll free numbers on your Audio Conferencing bridge](/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge).</span></span>
  
### <a name="port-or-transfer-existing-service-numbers"></a><span data-ttu-id="993a5-134">기존 서비스 번호 포트 또는 전송</span><span class="sxs-lookup"><span data-stu-id="993a5-134">Port or transfer existing service numbers</span></span>

<span data-ttu-id="993a5-135">현재 서비스 공급자 또는 통신 회사에서 서비스 번호를 전송 하려면 Microsoft에 수동으로 포트 순서를 제출 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="993a5-135">If you want to transfer service numbers from your current service provider or carrier, you need to manually submit a port order to Microsoft.</span></span> <span data-ttu-id="993a5-136">각 서비스 번호 유형 (유료 및 무료)에 대해 별도의 포트 주문을 제출 하 여 승인 문자 (LOA)를 사용 하 여 전송 하 게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="993a5-136">You have to submit separate port orders for each type of service number (toll vs. toll-free) that you will be transferring using a Letter of Authorization (LOA).</span></span> <span data-ttu-id="993a5-137">인증 문자 (LOA)에서 올바른 서비스 번호 유형을 선택 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="993a5-137">In the Letter of Authorization (LOA), you must select the correct type of service number.</span></span> <span data-ttu-id="993a5-138">Microsoft support에 문의 하는 경우*사용자 또는 구독자 번호가 아닌*서비스 번호를 전송 하 고 있는지, 아니면 동시 호출 용량이 통화 볼륨을 처리 하는 데 충분 하지 않을 수 있다는 것을 지정 하십시오.</span><span class="sxs-lookup"><span data-stu-id="993a5-138">When contacting Microsoft support, please make sure you specify that you are transferring a service number (*and not a user or subscriber number*), or the concurrent calling capacity may not be enough to handle call volumes.</span></span> <span data-ttu-id="993a5-139">전화 번호를 전송 하거나 전화 번호를 사용 하 여 다른 작업을 수행 하려는 경우 [조직의 전화 번호 관리](/microsoftteams/manage-phone-numbers-for-your-organization)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="993a5-139">If you want to transfer phone numbers or do other things with your phone numbers, see [Manage phone numbers for your organization](/microsoftteams/manage-phone-numbers-for-your-organization).</span></span>

> [!NOTE]
> <span data-ttu-id="993a5-140">이 보다 더 많은 전화 번호를 사용 해야 하는 경우 [비즈니스 제품에 대 한 고객 지원에 문의-관리자 도움말](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="993a5-140">If you need to get more telephone numbers than this, please [contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span></span> 
  
## <a name="related-topics"></a><span data-ttu-id="993a5-141">관련 항목</span><span class="sxs-lookup"><span data-stu-id="993a5-141">Related topics</span></span>
[<span data-ttu-id="993a5-142">Office 365에서 전화 시스템을 사용 하 여 얻을 수 있는 기능</span><span class="sxs-lookup"><span data-stu-id="993a5-142">Here's what you get with Phone System in Office 365</span></span>](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[<span data-ttu-id="993a5-143">오디오 회의 및 통화 요금제 국가 및 지역 가용성</span><span class="sxs-lookup"><span data-stu-id="993a5-143">Country and region availability for Audio Conferencing and Calling Plans</span></span>](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

  
 