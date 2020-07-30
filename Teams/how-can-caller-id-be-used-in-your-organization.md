---
title: 조직에서 발신자 ID를 사용하는 방법
author: CarolynRowe
ms.author: crowe
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
description: 발신자 ID는 CallingLineIdentity 이라는 정책을 사용 하 여 전화 시스템 사용자에 대 한 인바운드와 아웃 바운드 호출 모두에 대해 제어할 수 있습니다.
ms.openlocfilehash: 5c20f439d156997c89ca54c2a3bf39e9c3a42ae4
ms.sourcegitcommit: ded1e92348b6c18aa31f7f67e68ced3db525977d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/28/2020
ms.locfileid: "46506201"
---
# <a name="how-can-caller-id-be-used-in-your-organization"></a><span data-ttu-id="d2c1e-103">조직에서 발신자 ID를 사용하는 방법</span><span class="sxs-lookup"><span data-stu-id="d2c1e-103">How can caller ID be used in your organization</span></span>

<span data-ttu-id="d2c1e-104">발신자 ID는 CallingLineIdentity 이라는 정책을 사용 하 여 전화 시스템 사용자에 대 한 인바운드와 아웃 바운드 호출 모두에 대해 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2c1e-104">Caller ID can be controlled for both inbound and outbound calls for Phone System users by using a policy called CallingLineIdentity.</span></span>
  
<span data-ttu-id="d2c1e-105">모든 휴대폰 시스템 사용자는 PSTN 연결에 관계 없이 발신자 ID 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2c1e-105">The caller ID functionality is available to all Phone System users regardless of PSTN connectivity:</span></span>

- <span data-ttu-id="d2c1e-106">Microsoft 통화 요금제</span><span class="sxs-lookup"><span data-stu-id="d2c1e-106">Microsoft Calling Plans</span></span> 

- <span data-ttu-id="d2c1e-107">전화 시스템 직접 라우팅</span><span class="sxs-lookup"><span data-stu-id="d2c1e-107">Phone System Direct Routing</span></span> 
  
- <span data-ttu-id="d2c1e-108">온라인 PSTN 연결</span><span class="sxs-lookup"><span data-stu-id="d2c1e-108">Online PSTN Connectivity</span></span>
    
- <span data-ttu-id="d2c1e-109">비즈니스용 Skype 클라우드 Connector Edition에서 온-프레미스 PSTN 연결 (Cloud Connector Edition 1.4.2 이상 필요)</span><span class="sxs-lookup"><span data-stu-id="d2c1e-109">On-Premises PSTN Connectivity with Skype for Business Cloud Connector Edition (requires Cloud Connector Edition 1.4.2 and beyond)</span></span>
    
- <span data-ttu-id="d2c1e-110">비즈니스용 Skype 서버에 온-프레미스 PSTN 연결 (비즈니스용 Skype Server 2015 CU5 이상 필요)</span><span class="sxs-lookup"><span data-stu-id="d2c1e-110">On-Premises PSTN Connectivity with Skype for Business Server (requires Skype for Business Server 2015 CU5 and beyond)</span></span>
    
> [!NOTE]
> <span data-ttu-id="d2c1e-111">이 정책은 비즈니스용 Skype 2015 서버에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d2c1e-111">This policy isn't available in Skype for Business 2015 Server.</span></span> 
  
## <a name="outbound-caller-id"></a><span data-ttu-id="d2c1e-112">아웃 바운드 발신자 ID</span><span class="sxs-lookup"><span data-stu-id="d2c1e-112">Outbound caller ID</span></span>

<span data-ttu-id="d2c1e-113">아웃 바운드 PSTN 발신자 ID에 사용할 수 있는 세 가지 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2c1e-113">There are three options available for outbound PSTN caller ID:</span></span>
  
- <span data-ttu-id="d2c1e-114">사용자에 게 할당 된 전화 번호입니다 (기본값).</span><span class="sxs-lookup"><span data-stu-id="d2c1e-114">The telephone number assigned to the user, which is the default.</span></span>
    
- <span data-ttu-id="d2c1e-115">통화 요금제의 *전화 번호 인벤토리에* *서비스* 및 무료 번호로 분류 된 전화 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="d2c1e-115">A telephone number that is classified as a *service* and *toll-free* number in your Calling Plans telephone number inventory.</span></span> <span data-ttu-id="d2c1e-116">일반적으로 조직 자동 전화 교환 또는 통화 대기열에 할당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2c1e-116">It is usually assigned to an organizational auto attendant or call queue.</span></span>
    
- <span data-ttu-id="d2c1e-117">익명으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2c1e-117">Set to anonymous.</span></span>
    
<span data-ttu-id="d2c1e-118">그러나 아웃 바운드 발신자 ID에 대해 이러한 유형의 전화 번호를 지정할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d2c1e-118">However, you can't assign these types of phone numbers for the outbound caller ID:</span></span>
  
- <span data-ttu-id="d2c1e-119">통화 요금제 전화 번호 인벤토리에서 *사용자* 로 분류 된 모든 전화 번호</span><span class="sxs-lookup"><span data-stu-id="d2c1e-119">Any phone numbers that are classified as a  *user*  in your Calling Plans telephone number inventory</span></span>
    
- <span data-ttu-id="d2c1e-120">비즈니스용 Skype Server 온-프레미스 전화 번호</span><span class="sxs-lookup"><span data-stu-id="d2c1e-120">A Skype for Business Server on-premises phone number</span></span>
    
<span data-ttu-id="d2c1e-121">아웃 바운드 발신자 ID를 설정 하려면 [사용자의 발신자 Id 설정을](/microsoftteams/set-the-caller-id-for-a-user)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d2c1e-121">To set the outbound caller ID, see [Set the Caller ID for a user](/microsoftteams/set-the-caller-id-for-a-user).</span></span>
  
### <a name="end-user-control-of-outbound-caller-id"></a><span data-ttu-id="d2c1e-122">아웃 바운드 발신자 ID의 최종 사용자 제어</span><span class="sxs-lookup"><span data-stu-id="d2c1e-122">End user control of outbound caller ID</span></span>

<span data-ttu-id="d2c1e-123">EnableUserOverride 특성을 사용 하면 단일 또는 여러 사용자가 자신의 발신자 ID 설정을 **익명**으로 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2c1e-123">The EnableUserOverride attribute enables single or multiple users to change their caller ID setting to **Anonymous**.</span></span> <span data-ttu-id="d2c1e-124">이는 CallingLineIdentity 정책이 LineURI 또는 대체의 Callingidin매개 변수를 사용 하 여 구성 된 경우에만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2c1e-124">This only applies when a CallingLineIdentity policy is configured with a CallingIDSubstitute parameter of either LineURI or Substitute.</span></span> <span data-ttu-id="d2c1e-125">EnableUserOverride의 기본값은 False입니다.</span><span class="sxs-lookup"><span data-stu-id="d2c1e-125">The default value of EnableUserOverride is False.</span></span>
  
<span data-ttu-id="d2c1e-126">최종 사용자는 비즈니스용 Skype 데스크톱 클라이언트의 **설정** 탭을 사용 하 여 발신자 ID를 **익명** 으로 설정 하 고, **최종 사용자 호출** (관리자가 사용 하도록 설정한 경우)을 선택한 다음 **모든 통화에 대해 내 전화 번호 및 프로필 정보 숨기기**를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2c1e-126">Your end users can set their caller ID to **Anonymous** by using the **Settings** tab in the Skype for Business desktop client, select **Calls an End User** (if enabled by admin), and then select **Hide my phone number and profile information for all calls**.</span></span> <span data-ttu-id="d2c1e-127">팀에서 사용자는 오른쪽 위 모서리에 있는 프로필 사진으로 이동 하 고 **설정**  >  **통화**를 선택한 다음 **발신자 ID**에서 **전화 번호 숨기기 및 모든 통화에 대 한 프로필 정보**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2c1e-127">In Teams, users can go to their profile picture in the upper-right corner, select **Settings** > **Calls**,  and then under **Caller ID**, select **Hide my phone number and profile information for all calls**.</span></span>
  
||||
|:-----|:-----|:-----|
|<span data-ttu-id="d2c1e-128">**Windows**</span><span class="sxs-lookup"><span data-stu-id="d2c1e-128">**Windows**</span></span> <br/> |<span data-ttu-id="d2c1e-129">**버전**</span><span class="sxs-lookup"><span data-stu-id="d2c1e-129">**Version**</span></span> <br/> |<span data-ttu-id="d2c1e-130">**지원**</span><span class="sxs-lookup"><span data-stu-id="d2c1e-130">**Supported**</span></span> <br/> |
|<span data-ttu-id="d2c1e-131">간편 실행</span><span class="sxs-lookup"><span data-stu-id="d2c1e-131">Click-to-Run</span></span>  <br/> |<span data-ttu-id="d2c1e-132">12 월 6 일에 릴리스된 현재 채널 2016-버전 1611 (빌드 7571.2072)</span><span class="sxs-lookup"><span data-stu-id="d2c1e-132">Current Channel released on December 6, 2016 - version 1611 (Build 7571.2072)</span></span>  <br/> |<span data-ttu-id="d2c1e-133">예</span><span class="sxs-lookup"><span data-stu-id="d2c1e-133">Yes</span></span>  <br/> |
|<span data-ttu-id="d2c1e-134">간편 실행</span><span class="sxs-lookup"><span data-stu-id="d2c1e-134">Click-to-Run</span></span>  <br/> |<span data-ttu-id="d2c1e-135">2 월 22 일에 릴리스된 지연 채널의 첫 번째 릴리스 2017-버전 1701 (빌드 7766.2060)</span><span class="sxs-lookup"><span data-stu-id="d2c1e-135">First Release for Deferred Channel released on February 22, 2017 - Version 1701 (Build 7766.2060)</span></span>  <br/> |<span data-ttu-id="d2c1e-136">예</span><span class="sxs-lookup"><span data-stu-id="d2c1e-136">Yes</span></span>  <br/> |
|<span data-ttu-id="d2c1e-137">간편 실행</span><span class="sxs-lookup"><span data-stu-id="d2c1e-137">Click-to-Run</span></span>  <br/> |<span data-ttu-id="d2c1e-138">6 월 13 일에 릴리스된 지연 채널 2017-버전 1701 (빌드 7766.2092)</span><span class="sxs-lookup"><span data-stu-id="d2c1e-138">Deferred Channel released on June 13, 2017 - Version 1701 (Build 7766.2092)</span></span>  <br/> |<span data-ttu-id="d2c1e-139">예</span><span class="sxs-lookup"><span data-stu-id="d2c1e-139">Yes</span></span>  <br/> |
|<span data-ttu-id="d2c1e-140">MSI</span><span class="sxs-lookup"><span data-stu-id="d2c1e-140">MSI</span></span>  <br/> |<span data-ttu-id="d2c1e-141">비즈니스용 Skype</span><span class="sxs-lookup"><span data-stu-id="d2c1e-141">Skype for Business</span></span>  <br/> |<span data-ttu-id="d2c1e-142">아니요</span><span class="sxs-lookup"><span data-stu-id="d2c1e-142">No</span></span>  <br/> |
|<span data-ttu-id="d2c1e-143">Mac</span><span class="sxs-lookup"><span data-stu-id="d2c1e-143">Mac</span></span>  <br/> |<span data-ttu-id="d2c1e-144">비즈니스용 Skype</span><span class="sxs-lookup"><span data-stu-id="d2c1e-144">Skype for Business</span></span>  <br/> |<span data-ttu-id="d2c1e-145">아니요</span><span class="sxs-lookup"><span data-stu-id="d2c1e-145">No</span></span>  <br/> |
   
## <a name="inbound-caller-id"></a><span data-ttu-id="d2c1e-146">인바운드 발신자 ID</span><span class="sxs-lookup"><span data-stu-id="d2c1e-146">Inbound caller ID</span></span>

<span data-ttu-id="d2c1e-147">숫자가 Azure AD의 사용자와 연결 된 경우 전화 시스템에 외부 전화 번호의 ID가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2c1e-147">Phone System will show called ID for an external phone number if the number is associated with a user in Azure AD.</span></span> <span data-ttu-id="d2c1e-148">전화 번호가 Azure AD에 없으면 telco 제공 된 표시 이름이 표시 됩니다 (사용 가능한 경우).</span><span class="sxs-lookup"><span data-stu-id="d2c1e-148">If the phone number is not in Azure AD, the telco-provided display name will be shown if it is available.</span></span>

<span data-ttu-id="d2c1e-149">BlockIncomingCallerID 특성을 사용 하면 들어오는 PSTN 호출에 대 한 발신자 ID를 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2c1e-149">The BlockIncomingCallerID attribute allows for blocking the caller ID on incoming PSTN calls.</span></span> <span data-ttu-id="d2c1e-150">이 특성을 설정할 수 있지만 사용자 설정 페이지에서는 최종 사용자가 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d2c1e-150">You can set this attribute, but it isn't available to your end users on the user settings page.</span></span> <span data-ttu-id="d2c1e-151">현재는 온라인 PSTN 연결 에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2c1e-151">And it is currently available only with Online PSTN connectivity.</span></span>
  
<span data-ttu-id="d2c1e-152">아웃 바운드 발신자 ID를 설정 하려면 [사용자의 발신자 Id 설정을](/microsoftteams/set-the-caller-id-for-a-user)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d2c1e-152">To set the outbound caller ID, see [Set the Caller ID for a user](/microsoftteams/set-the-caller-id-for-a-user).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="d2c1e-153">관련 항목</span><span class="sxs-lookup"><span data-stu-id="d2c1e-153">Related topics</span></span>
[<span data-ttu-id="d2c1e-154">전화 번호 전송 자주 묻는 질문</span><span class="sxs-lookup"><span data-stu-id="d2c1e-154">Transferring phone numbers common questions</span></span>](/microsoftteams/transferring-phone-numbers-common-questions)

[<span data-ttu-id="d2c1e-155">통화 요금제에 사용 되는 다른 종류의 전화 번호</span><span class="sxs-lookup"><span data-stu-id="d2c1e-155">Different kinds of phone numbers used for Calling Plans</span></span>](/microsoftteams/different-kinds-of-phone-numbers-used-for-calling-plans)

[<span data-ttu-id="d2c1e-156">조직의 전화 번호 관리</span><span class="sxs-lookup"><span data-stu-id="d2c1e-156">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="d2c1e-157">긴급 통화 사용 약관</span><span class="sxs-lookup"><span data-stu-id="d2c1e-157">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)

<span data-ttu-id="d2c1e-158">[비즈니스용 Skype Online: 비상 전화 부인 레이블](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="d2c1e-158">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>

  
 
