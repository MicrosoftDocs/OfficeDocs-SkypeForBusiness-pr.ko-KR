---
title: 조직에서 발신자 ID를 사용하는 방법
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: mikedav, roykuntz
ms.topic: article
ms.assetid: 5a0bd8ba-3334-46ee-becf-1025597737f6
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
- Calling Plans
- ms.teamsadmincenter.voice.callerid.overview
description: CallingLineIdentity라는 정책을 사용하여 전화 시스템 사용자의 인바운드 및 아웃바운드 호출에 대해 호출자 ID를 제어할 수 있습니다.
ms.openlocfilehash: cd2074fec3027f1172b6ea681013f53994963cb5
ms.sourcegitcommit: 2874aec7768bb46ed4506c1a2d431841f47190bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2020
ms.locfileid: "47255451"
---
# <a name="how-can-caller-id-be-used-in-your-organization"></a><span data-ttu-id="27c4b-103">조직에서 발신자 ID를 사용하는 방법</span><span class="sxs-lookup"><span data-stu-id="27c4b-103">How can caller ID be used in your organization</span></span>

<span data-ttu-id="27c4b-104">CallingLineIdentity라는 정책을 사용하여 전화 시스템 사용자의 인바운드 및 아웃바운드 호출에 대해 호출자 ID를 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27c4b-104">Caller ID can be controlled for both inbound and outbound calls for Phone System users by using a policy called CallingLineIdentity.</span></span>
  
<span data-ttu-id="27c4b-105">호출자 ID 기능은 PSTN 연결에 관계없이 모든 전화 시스템 사용자가 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27c4b-105">The caller ID functionality is available to all Phone System users regardless of PSTN connectivity:</span></span>

- <span data-ttu-id="27c4b-106">Microsoft 통화 요금제</span><span class="sxs-lookup"><span data-stu-id="27c4b-106">Microsoft Calling Plans</span></span> 

- <span data-ttu-id="27c4b-107">전화 시스템 직접 라우팅</span><span class="sxs-lookup"><span data-stu-id="27c4b-107">Phone System Direct Routing</span></span> 
  
- <span data-ttu-id="27c4b-108">온라인 PSTN 연결</span><span class="sxs-lookup"><span data-stu-id="27c4b-108">Online PSTN Connectivity</span></span>
    
- <span data-ttu-id="27c4b-109">비즈니스용 Skype Cloud Connector Edition을 사용하여 프레미스 PSTN 연결(Cloud Connector Edition 1.4.2 이상 필요)</span><span class="sxs-lookup"><span data-stu-id="27c4b-109">On-Premises PSTN Connectivity with Skype for Business Cloud Connector Edition (requires Cloud Connector Edition 1.4.2 and beyond)</span></span>
    
- <span data-ttu-id="27c4b-110">비즈니스용 Skype Server와의 프레미스 PSTN 연결(비즈니스용 Skype Server 2015 CU5 이상 필요)</span><span class="sxs-lookup"><span data-stu-id="27c4b-110">On-Premises PSTN Connectivity with Skype for Business Server (requires Skype for Business Server 2015 CU5 and beyond)</span></span>
    
> [!NOTE]
> <span data-ttu-id="27c4b-111">이 정책은 비즈니스용 Skype 2015 서버에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="27c4b-111">This policy isn't available in Skype for Business 2015 Server.</span></span> 
  
## <a name="outbound-caller-id"></a><span data-ttu-id="27c4b-112">아웃바운드 호출자 ID</span><span class="sxs-lookup"><span data-stu-id="27c4b-112">Outbound caller ID</span></span>

<span data-ttu-id="27c4b-113">아웃바운드 PSTN 호출자 ID에 사용할 수 있는 세 가지 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27c4b-113">There are three options available for outbound PSTN caller ID:</span></span>
  
- <span data-ttu-id="27c4b-114">사용자에게 할당된 전화 번호(기본값).</span><span class="sxs-lookup"><span data-stu-id="27c4b-114">The telephone number assigned to the user, which is the default.</span></span>
    
- <span data-ttu-id="27c4b-115">통화 플랜 전화 번호  인벤토리에서 서비스 및 무료 번호로 분류되는 전화 번호입니다. </span><span class="sxs-lookup"><span data-stu-id="27c4b-115">A telephone number that is classified as a *service* and *toll-free* number in your Calling Plans telephone number inventory.</span></span> <span data-ttu-id="27c4b-116">일반적으로 조직 자동 전화 회의 또는 통화 큐에 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="27c4b-116">It is usually assigned to an organizational auto attendant or call queue.</span></span>
    
- <span data-ttu-id="27c4b-117">익명으로 설정</span><span class="sxs-lookup"><span data-stu-id="27c4b-117">Set to anonymous.</span></span>
    
<span data-ttu-id="27c4b-118">그러나 아웃바운드 발신자 ID에는 이러한 유형의 전화 번호를 할당할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="27c4b-118">However, you can't assign these types of phone numbers for the outbound caller ID:</span></span>
  
- <span data-ttu-id="27c4b-119">통화 요금제 전화 번호  인벤토리에서 사용자로 분류된 모든 전화 번호</span><span class="sxs-lookup"><span data-stu-id="27c4b-119">Any phone numbers that are classified as a  *user*  in your Calling Plans telephone number inventory</span></span>
    
- <span data-ttu-id="27c4b-120">비즈니스용 Skype Server-프레미스 전화 번호</span><span class="sxs-lookup"><span data-stu-id="27c4b-120">A Skype for Business Server on-premises phone number</span></span>
    
<span data-ttu-id="27c4b-121">아웃바운드 호출자 ID를 설정하는 경우 사용자의 [호출자 ID를 참조합니다.](/microsoftteams/set-the-caller-id-for-a-user)</span><span class="sxs-lookup"><span data-stu-id="27c4b-121">To set the outbound caller ID, see [Set the Caller ID for a user](/microsoftteams/set-the-caller-id-for-a-user).</span></span>
  
### <a name="end-user-control-of-outbound-caller-id"></a><span data-ttu-id="27c4b-122">아웃바운드 호출자 ID의 최종 사용자 제어</span><span class="sxs-lookup"><span data-stu-id="27c4b-122">End user control of outbound caller ID</span></span>

<span data-ttu-id="27c4b-123">EnableUserOverride 특성을 사용하면 단일 또는 여러 사용자가 호출자 ID 설정을 익명으로 변경할 수 **있습니다.**</span><span class="sxs-lookup"><span data-stu-id="27c4b-123">The EnableUserOverride attribute enables single or multiple users to change their caller ID setting to **Anonymous**.</span></span> <span data-ttu-id="27c4b-124">이는 LineURI 또는 Substitute의 CallingIDSubstitute 매개 변수로 CallingLineIdentity 정책이 구성된 경우만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="27c4b-124">This only applies when a CallingLineIdentity policy is configured with a CallingIDSubstitute parameter of either LineURI or Substitute.</span></span> <span data-ttu-id="27c4b-125">EnableUserOverride의 기본값은 False입니다.</span><span class="sxs-lookup"><span data-stu-id="27c4b-125">The default value of EnableUserOverride is False.</span></span>
  
<span data-ttu-id="27c4b-126">최종 사용자는 비즈니스용 Skype 데스크톱 클라이언트의  설정 탭을 사용하여 발신자  ID를 익명으로 설정하고, 최종 사용자(관리자가 사용하도록 설정한 경우)를 선택한 다음, 모든 통화에 대해 내 전화 번호 및 프로필 정보 숨기기를 선택할 수 **있습니다.** </span><span class="sxs-lookup"><span data-stu-id="27c4b-126">Your end users can set their caller ID to **Anonymous** by using the **Settings** tab in the Skype for Business desktop client, select **Calls an End User** (if enabled by admin), and then select **Hide my phone number and profile information for all calls**.</span></span> <span data-ttu-id="27c4b-127">Teams에서 사용자는 오른쪽 위 모서리에 있는 프로필 사진으로 이동하여 통화 설정을 선택한 다음 발신자 ID 아래에서 모든 통화에 대한 내 전화 번호 및 프로필 정보 숨기기를 선택할  >   **수 있습니다.** </span><span class="sxs-lookup"><span data-stu-id="27c4b-127">In Teams, users can go to their profile picture in the upper-right corner, select **Settings** > **Calls**,  and then under **Caller ID**, select **Hide my phone number and profile information for all calls**.</span></span>
  
||||
|:-----|:-----|:-----|
|<span data-ttu-id="27c4b-128">**Windows**</span><span class="sxs-lookup"><span data-stu-id="27c4b-128">**Windows**</span></span> <br/> |<span data-ttu-id="27c4b-129">**버전**</span><span class="sxs-lookup"><span data-stu-id="27c4b-129">**Version**</span></span> <br/> |<span data-ttu-id="27c4b-130">**지원**</span><span class="sxs-lookup"><span data-stu-id="27c4b-130">**Supported**</span></span> <br/> |
|<span data-ttu-id="27c4b-131">Click-to-Run</span><span class="sxs-lookup"><span data-stu-id="27c4b-131">Click-to-Run</span></span>  <br/> |<span data-ttu-id="27c4b-132">2016년 12월 6일 릴리스된 현재 채널 - 버전 1611(빌드 7571.2072)</span><span class="sxs-lookup"><span data-stu-id="27c4b-132">Current Channel released on December 6, 2016 - version 1611 (Build 7571.2072)</span></span>  <br/> |<span data-ttu-id="27c4b-133">예</span><span class="sxs-lookup"><span data-stu-id="27c4b-133">Yes</span></span>  <br/> |
|<span data-ttu-id="27c4b-134">Click-to-Run</span><span class="sxs-lookup"><span data-stu-id="27c4b-134">Click-to-Run</span></span>  <br/> |<span data-ttu-id="27c4b-135">2017년 2월 22일 릴리스된 지연 채널의 첫 번째 릴리스 - 버전 1701(빌드 7766.2060)</span><span class="sxs-lookup"><span data-stu-id="27c4b-135">First Release for Deferred Channel released on February 22, 2017 - Version 1701 (Build 7766.2060)</span></span>  <br/> |<span data-ttu-id="27c4b-136">예</span><span class="sxs-lookup"><span data-stu-id="27c4b-136">Yes</span></span>  <br/> |
|<span data-ttu-id="27c4b-137">Click-to-Run</span><span class="sxs-lookup"><span data-stu-id="27c4b-137">Click-to-Run</span></span>  <br/> |<span data-ttu-id="27c4b-138">2017년 6월 13일 릴리스된 지연 채널 - 버전 1701(빌드 7766.2092)</span><span class="sxs-lookup"><span data-stu-id="27c4b-138">Deferred Channel released on June 13, 2017 - Version 1701 (Build 7766.2092)</span></span>  <br/> |<span data-ttu-id="27c4b-139">예</span><span class="sxs-lookup"><span data-stu-id="27c4b-139">Yes</span></span>  <br/> |
|<span data-ttu-id="27c4b-140">MSI</span><span class="sxs-lookup"><span data-stu-id="27c4b-140">MSI</span></span>  <br/> |<span data-ttu-id="27c4b-141">비즈니스용 Skype</span><span class="sxs-lookup"><span data-stu-id="27c4b-141">Skype for Business</span></span>  <br/> |<span data-ttu-id="27c4b-142">아니요</span><span class="sxs-lookup"><span data-stu-id="27c4b-142">No</span></span>  <br/> |
|<span data-ttu-id="27c4b-143">Mac</span><span class="sxs-lookup"><span data-stu-id="27c4b-143">Mac</span></span>  <br/> |<span data-ttu-id="27c4b-144">비즈니스용 Skype</span><span class="sxs-lookup"><span data-stu-id="27c4b-144">Skype for Business</span></span>  <br/> |<span data-ttu-id="27c4b-145">아니요</span><span class="sxs-lookup"><span data-stu-id="27c4b-145">No</span></span>  <br/> |
   
## <a name="inbound-caller-id"></a><span data-ttu-id="27c4b-146">인바운드 호출자 ID</span><span class="sxs-lookup"><span data-stu-id="27c4b-146">Inbound caller ID</span></span>

<span data-ttu-id="27c4b-147">전화 번호가 Azure AD의 사용자와 연결된 경우 전화 시스템에서 외부 전화 번호에 대해 호출된 ID를 보여 주게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="27c4b-147">Phone System will show called ID for an external phone number if the number is associated with a user in Azure AD.</span></span> <span data-ttu-id="27c4b-148">전화 번호가 Azure AD에 없는 경우 사용할 수 있는 경우 텔코에서 제공하는 표시 이름이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="27c4b-148">If the phone number is not in Azure AD, the telco-provided display name will be shown if it is available.</span></span>

<span data-ttu-id="27c4b-149">BlockIncomingCallerID 특성은 들어오는 PSTN 호출에서 호출자 ID를 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27c4b-149">The BlockIncomingCallerID attribute allows for blocking the caller ID on incoming PSTN calls.</span></span> <span data-ttu-id="27c4b-150">이 특성을 설정할 수 있지만 사용자 설정 페이지에서 최종 사용자가 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="27c4b-150">You can set this attribute, but it isn't available to your end users on the user settings page.</span></span> <span data-ttu-id="27c4b-151">또한 현재 온라인 PSTN 연결에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27c4b-151">And it is currently available only with Online PSTN connectivity.</span></span>
  
<span data-ttu-id="27c4b-152">아웃바운드 호출자 ID를 설정하는 경우 사용자의 [호출자 ID를 참조합니다.](/microsoftteams/set-the-caller-id-for-a-user)</span><span class="sxs-lookup"><span data-stu-id="27c4b-152">To set the outbound caller ID, see [Set the Caller ID for a user](/microsoftteams/set-the-caller-id-for-a-user).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="27c4b-153">관련 항목</span><span class="sxs-lookup"><span data-stu-id="27c4b-153">Related topics</span></span>
[<span data-ttu-id="27c4b-154">전화 번호 전송 자주 묻는 질문</span><span class="sxs-lookup"><span data-stu-id="27c4b-154">Transferring phone numbers common questions</span></span>](/microsoftteams/transferring-phone-numbers-common-questions)

[<span data-ttu-id="27c4b-155">통화 요금제에 사용되는 다양한 종류의 전화 번호</span><span class="sxs-lookup"><span data-stu-id="27c4b-155">Different kinds of phone numbers used for Calling Plans</span></span>](/microsoftteams/different-kinds-of-phone-numbers-used-for-calling-plans)

[<span data-ttu-id="27c4b-156">조직의 전화 번호 관리</span><span class="sxs-lookup"><span data-stu-id="27c4b-156">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="27c4b-157">긴급 통화 사용 약관</span><span class="sxs-lookup"><span data-stu-id="27c4b-157">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)

<span data-ttu-id="27c4b-158">[비즈니스용 Skype Online: 긴급 통화 고지 사항 레이블](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="27c4b-158">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>

  
 
