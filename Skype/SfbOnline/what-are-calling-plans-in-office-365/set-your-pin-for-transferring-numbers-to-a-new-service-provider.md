---
title: 새 서비스 공급자로 번호 전송에 대 한 PIN 설정
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz
ms.topic: article
ms.assetid: f1defa5b-e49c-4d8c-a5f8-3f736201af5e
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Calling Plans
description: 비즈니스용 Skype Online에서 다른 전화 서비스 공급자 또는 통신 회사에 전화 번호를 전송 하거나 이식 하려면 PIN을 수동으로 설정 해야 합니다. PIN을 설정한 후에는 전화 번호를 이식 하도록 요청할 때이를 포함 해야 합니다.
ms.openlocfilehash: 7faad94822e6392d66c44dd67cb461abf69e47dd
ms.sourcegitcommit: 75b2cd0d2d39c50dc1e1513860841e2ae3f84324
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/28/2019
ms.locfileid: "37642469"
---
# <a name="set-your-pin-for-transferring-numbers-to-a-new-service-provider"></a><span data-ttu-id="465cc-104">새 서비스 공급자로 번호 전송에 대 한 PIN 설정</span><span class="sxs-lookup"><span data-stu-id="465cc-104">Set your PIN for transferring numbers to a new service provider</span></span>

<span data-ttu-id="465cc-105">비즈니스용 Skype Online에서 다른 전화 서비스 공급자 또는 통신 회사에 전화 번호를 전송 하거나 *이식* 하려면 PIN을 수동으로 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="465cc-105">To transfer or  *port out*  phone numbers from Skype for Business Online to another telephone service provider or carrier, you will need to manually set a PIN.</span></span> <span data-ttu-id="465cc-106">PIN을 설정한 후에는 전화 번호를 이식 하도록 요청할 때이를 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="465cc-106">After you set the PIN, you need to include it when you request to port a phone number out.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="465cc-107">포트 아웃 PIN은 미국 내 조직에만 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="465cc-107">A port out PIN is only used for organizations in the United States.</span></span> 
  
<span data-ttu-id="465cc-108">전화 번호 전송 및 포팅에 대 한 자세한 내용은 [Office 365에 전화 번호 전송을](/microsoftteams/transfer-phone-numbers-to-office-365) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="465cc-108">See [Transfer phone numbers to Office 365](/microsoftteams/transfer-phone-numbers-to-office-365) for more information about transferring and porting in/out phone numbers.</span></span>
  
<span data-ttu-id="465cc-109">이 PIN에 대해 알아야 할 구체적인 정보는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="465cc-109">Here is some specific information about this PIN you should know:</span></span>
  
- <span data-ttu-id="465cc-110">PIN이 설정 되지 않은 경우 비즈니스용 Skype Online에서 전화 번호를 전송 하거나 포트 아웃할 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="465cc-110">If a PIN isn't set, you won't be able to transfer or port out phone numbers from Skype for Business Online.</span></span>
    
- <span data-ttu-id="465cc-111">6-10 자리 숫자를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="465cc-111">It can contain 6-10 digits (numbers).</span></span>
    
- <span data-ttu-id="465cc-112">문자 또는 특수 문자를 포함할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="465cc-112">It can't contain letters or special characters.</span></span>
    
- <span data-ttu-id="465cc-113">기본 PIN은 비어 있지만, 입력 하는 경우에는 제거 하거나 다시 공백으로 설정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="465cc-113">The default PIN is blank, but if you put one in, you can't remove or set it back to blank.</span></span>
    
- <span data-ttu-id="465cc-114">PIN을 추가한 후 업데이트 하거나 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="465cc-114">You can update or change the PIN after you put one in.</span></span>
    
## <a name="set-up-your-pin"></a><span data-ttu-id="465cc-115">PIN 설정</span><span class="sxs-lookup"><span data-stu-id="465cc-115">Set up your PIN</span></span>

<span data-ttu-id="465cc-116">![비즈니스용 skype](../images/sfb-logo-30x30.png) **관리 센터를 사용 하 여** 비즈니스용 skype 로고를 표시 하는 아이콘</span><span class="sxs-lookup"><span data-stu-id="465cc-116">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1. <span data-ttu-id="465cc-117">회사 또는 학교 계정으로 Office 365에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="465cc-117">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="465cc-118">**Microsoft 팀 관리 센터** > **레거시 포털로**이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="465cc-118">Go to the **Microsoft Teams admin center** > **Legacy portal**.</span></span>
    
3. <span data-ttu-id="465cc-119">왼쪽 탐색 창에서 **음성** > **포트 주문을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="465cc-119">In the left navigation, choose **Voice** > **Port orders**.</span></span>
    
4. <span data-ttu-id="465cc-120">다른 서비스 통신 회사에 번호를 전송 또는 이식 하는 데 사용 되는 **PIN 설정을 클릭 하 고 관리** 합니다.</span><span class="sxs-lookup"><span data-stu-id="465cc-120">Click **Set up and manage the PIN** that is used for transferring or porting numbers to another service carrier.</span></span>
    
5. <span data-ttu-id="465cc-121">**포트 아웃 핀 설정 또는 변경** 패널에서 PIN을 입력 하 고 **저장**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="465cc-121">In the **Set or change your port out PIN** panel, enter your PIN and click **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="465cc-122">이 보다 더 많은 전화 번호를 받으려면 [비즈니스 제품에 대 한 고객 지원에 문의-관리자 도움말](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="465cc-122">If you need to get more telephone numbers than this, please [contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="465cc-123">관련 항목</span><span class="sxs-lookup"><span data-stu-id="465cc-123">Related topics</span></span>
[<span data-ttu-id="465cc-124">전화 번호 전송 일반적인 질문</span><span class="sxs-lookup"><span data-stu-id="465cc-124">Transferring phone numbers common questions</span></span>](/microsoftteams/transferring-phone-numbers-common-questions)

[<span data-ttu-id="465cc-125">통화 요금제에 사용 되는 다른 종류의 전화 번호</span><span class="sxs-lookup"><span data-stu-id="465cc-125">Different kinds of phone numbers used for Calling Plans</span></span>](/microsoftteams/different-kinds-of-phone-numbers-used-for-calling-plans)

[<span data-ttu-id="465cc-126">조직의 전화 번호 관리</span><span class="sxs-lookup"><span data-stu-id="465cc-126">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="465cc-127">비상 통화 약관</span><span class="sxs-lookup"><span data-stu-id="465cc-127">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)

<span data-ttu-id="465cc-128">[비즈니스용 Skype Online: 비상 전화 부인 레이블](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="465cc-128">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>

  
 
  

