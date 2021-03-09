---
title: 사용자의 발신자 ID 설정
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: mikedav, roykuntz
ms.topic: article
ms.assetid: c7323490-d9b7-421a-aa76-5bd485f80583
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
- seo-marvel-mar2020
description: 전화선 ID라고도 하는 Microsoft 365 및 Office 365 기본 호출자 ID(사용자의 할당된 전화 번호)에 대해 자세히 알아보겠습니다. 사용자의 발신자 ID를 변경하거나 차단할 수 있습니다.
ms.openlocfilehash: 1cc6221c0f4ca1642cc9422ed81e0e07ae1bfc91
ms.sourcegitcommit: 1613e08da482ff142c990c9c9951abeb873ad964
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/09/2021
ms.locfileid: "50569420"
---
# <a name="set-the-caller-id-for-a-user"></a><span data-ttu-id="13cd0-104">사용자의 발신자 ID 설정</span><span class="sxs-lookup"><span data-stu-id="13cd0-104">Set the Caller ID for a user</span></span>
<span data-ttu-id="13cd0-105">Microsoft 365 및 Office 365의 전화 시스템은 사용자의 할당된 전화 번호인 기본 호출자 ID를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="13cd0-105">The Phone System in Microsoft 365 and Office 365 provides a default caller ID that is the user's assigned telephone number.</span></span> <span data-ttu-id="13cd0-106">사용자의 발신자 ID(호출 줄 ID라고도 하는)를 변경하거나 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13cd0-106">You can either change or block the caller ID (also called a Calling Line ID) for a user.</span></span> <span data-ttu-id="13cd0-107">조직에서 발신자 ID를 사용할 수 있는 방법 을 확인하여 조직에서 발신자 ID를 사용하는 방법에 대해 [자세히 알아보면 됩니다.](how-can-caller-id-be-used-in-your-organization.md)</span><span class="sxs-lookup"><span data-stu-id="13cd0-107">You can learn more about how to use caller ID in your organization by going [How can caller ID be used in your organization](how-can-caller-id-be-used-in-your-organization.md).</span></span>
  
> [!TIP]
> <span data-ttu-id="13cd0-108">현재 비즈니스용 Skype Online에서는 들어오는 통화를 차단할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="13cd0-108">You can't block incoming calls currently in Skype for Business Online.</span></span> 
  
<span data-ttu-id="13cd0-109">변경할 수 있는 설정이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13cd0-109">There are settings that you can change:</span></span>
  
> [!NOTE]
> <span data-ttu-id="13cd0-110">**Lync** 또는 비즈니스용 Skype 서버가 있는 온-프레미스 조직에는 해당되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="13cd0-110">This **is not** for on-premises organizations with Lync or Skype for Business Server.</span></span>
  
- <span data-ttu-id="13cd0-111">**발신자 ID** 변경 기본적으로 해당 전화 번호인 사용자의 발신자 ID를 다른 전화 번호로 바꿀 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13cd0-111">**Change their outgoing caller ID** You can replace a user's Caller ID, which by default is their telephone number, with another phone number.</span></span> <span data-ttu-id="13cd0-112">예를 들어 사용자의 발신자 ID를 해당 전화 번호에서 비즈니스의 주 전화 번호로 변경하거나 사용자의 전화 번호에서 법무 부서의 주 전화 번호로 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13cd0-112">For example, you could change the user's Caller ID from their phone number to a main phone number for your business or change the user's Calling Line ID from their phone number to a main phone number for the legal department.</span></span> <span data-ttu-id="13cd0-113">통화 ID 번호를 모든 **온라인** 서비스 번호(전화 또는 무료)로 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13cd0-113">You can change the Calling ID number to any Online **service** number (toll or toll-free).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="13cd0-114">서비스 매개 변수를  _사용하려면_ 유효한 서비스 번호를 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="13cd0-114">If you want to use the  _Service_ parameter, you must specify a valid service number.</span></span>
  
- <span data-ttu-id="13cd0-115">**아웃바운드 호출자 ID 차단** 사용자의 발신 PSTN 호출에서 발신 호출자 ID가 전송되지 못하도록 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13cd0-115">**Block their outbound caller ID** You can block the outgoing Caller ID from being sent on a user's outgoing PSTN calls.</span></span> <span data-ttu-id="13cd0-116">이렇게 하면 전화 번호가 호출되는 사람의 휴대폰에 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="13cd0-116">Doing this will block their phone number from being displayed on the phone of a person being called.</span></span>
    
- <span data-ttu-id="13cd0-117">**들어오는 발신자 ID 차단** 사용자가 들어오는 PSTN 호출에서 발신자 ID를 수신하지 못하도록 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13cd0-117">**Block their incoming caller ID** You can block a user from receiving Caller ID on any incoming PSTN calls.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="13cd0-118">긴급 통화는 항상 사용자의 전화 번호(발신자 ID)를 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="13cd0-118">Emergency calls will always send the user's telephone number (caller ID).</span></span> 
  
<span data-ttu-id="13cd0-119">기본적으로 이러한 발신자 ID 설정은 모두 **해제됩니다.**</span><span class="sxs-lookup"><span data-stu-id="13cd0-119">By default, all of these caller ID settings are **turned off**.</span></span> <span data-ttu-id="13cd0-120">즉, 해당 사용자가 PSTN 전화로 전화를 걸 때 비즈니스용 Skype Online 사용자의 전화 번호를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13cd0-120">This means that the Skype for Business Online user's phone number can be seen when that user makes a call to a PSTN phone.</span></span>
  
<span data-ttu-id="13cd0-121">이러한 설정 및 해당 설정을 사용하는 방법에 대한 자세한 내용은 조직에서 발신자 ID를 사용할 수 있는 [방법 을 이동하세요.](how-can-caller-id-be-used-in-your-organization.md)</span><span class="sxs-lookup"><span data-stu-id="13cd0-121">To learn more about these settings and how you can use them, go [How can caller ID be used in your organization](how-can-caller-id-be-used-in-your-organization.md).</span></span>
  
## <a name="set-your-caller-id-policy-settings"></a><span data-ttu-id="13cd0-122">발신자 ID 정책 설정 설정</span><span class="sxs-lookup"><span data-stu-id="13cd0-122">Set your caller ID policy settings</span></span>

> [!NOTE]
> <span data-ttu-id="13cd0-123">비즈니스용 Skype Online의 모든 발신자 ID 설정의 경우 비즈니스용  Skype Windows PowerShell 사용할 **수 없습니다.**</span><span class="sxs-lookup"><span data-stu-id="13cd0-123">For all of the Caller ID settings in Skype for Business Online, you must use Windows PowerShell and you **can't use** the **Skype for Business admin center**.</span></span> 
  
### <a name="start-powershell"></a><span data-ttu-id="13cd0-124">PowerShell 시작</span><span class="sxs-lookup"><span data-stu-id="13cd0-124">Start PowerShell</span></span>

- <span data-ttu-id="13cd0-125">명령 Windows PowerShell 프롬프트를 열고 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="13cd0-125">Open a Windows PowerShell command prompt and run the following commands:</span></span>

```powershell
  # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
```
    
### <a name="see-all-of-the-caller-id-policy-settings-in-your-organization"></a><span data-ttu-id="13cd0-126">조직의 모든 발신자 ID 정책 설정 보기</span><span class="sxs-lookup"><span data-stu-id="13cd0-126">See all of the caller ID policy settings in your organization</span></span>

- <span data-ttu-id="13cd0-127">조직의 모든 호출자 ID 정책 설정을 확인하려면 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="13cd0-127">To view all of the caller ID policy settings in your organization, run:</span></span>

  ```PowerShell
  Get-CsCallingLineIdentity |fl
  ```
  <span data-ttu-id="13cd0-128">[Get-CsCallingLineIdentity에](https://technet.microsoft.com/library/mt793856.aspx)대한 자세한 예제 및 세부 정보를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="13cd0-128">See more examples and details for [Get-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793856.aspx).</span></span>
    
### <a name="create-a-new-caller-id-policy-for-your-organization"></a><span data-ttu-id="13cd0-129">조직에 대한 새 발신자 ID 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="13cd0-129">Create a new caller ID policy for your organization</span></span>


- <span data-ttu-id="13cd0-130">호출자 ID를 익명으로 설정하는 새 호출자 ID 정책을 만들 경우 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="13cd0-130">To create a new caller ID policy that sets the caller ID to anonymous, run:</span></span>
    
  ```PowerShell
  New-CsCallingLineIdentity  -Identity Anonymous -Description "Anonymous policy" -CallingIDSubstitute Anonymous -EnableUserOverride $false
  ```
  > [!NOTE]  
  > <span data-ttu-id="13cd0-131">모든 경우 "서비스 번호" 필드에는 초기 "+"가 포함되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="13cd0-131">In all cases, the "Service Number" field should not include an initial "+".</span></span>

  <span data-ttu-id="13cd0-132">[New-CsCallingLineIdentity에](https://technet.microsoft.com/library/mt793855.aspx)대한 자세한 예제 및 세부 정보를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="13cd0-132">See more examples and details for [New-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793855.aspx).</span></span>
    
- <span data-ttu-id="13cd0-133">Amos Marble에 만든 새 정책을 적용하기 위해 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="13cd0-133">To apply the new policy you created to Amos Marble, run:</span></span>
    
  ```PowerShell
   Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName Anonymous
  ```
  <span data-ttu-id="13cd0-134">[Grant-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793857.aspx) cmdlet을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="13cd0-134">See more on the [Grant-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793857.aspx) cmdlet.</span></span>
    
<span data-ttu-id="13cd0-135">정책을 이미 만든 경우 [Set-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793854.aspx) cmdlet을 사용하여 기존 정책을 변경한 다음 [Grant-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793857.aspx) cmdlet을 사용하여 사용자에게 설정을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13cd0-135">If you have already created a policy, you can use the [Set-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793854.aspx) cmdlet to make changes to the existing policy, and then use the [Grant-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793857.aspx) cmdlet to apply the settings to your users.</span></span>
  
### <a name="set-it-so-the-incoming-caller-id-is-blocked"></a><span data-ttu-id="13cd0-136">들어오는 발신자 ID가 차단되지 있도록 설정</span><span class="sxs-lookup"><span data-stu-id="13cd0-136">Set it so the incoming caller ID is blocked</span></span>

- <span data-ttu-id="13cd0-137">들어오는 호출자 ID를 차단하기 위해 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="13cd0-137">To block the incoming caller ID, run:</span></span>
    
  ```PowerShell
  Set-CsCallingLineIdentity  -Identity "Block Incoming" -BlockIncomingPstnCallerID $true -EnableUserOverride $true
  ```
  <span data-ttu-id="13cd0-138">[Set-CsCallingLineIdentity에](https://technet.microsoft.com/library/mt793854.aspx)대한 자세한 예제 및 세부 정보를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="13cd0-138">See more examples and details for [Set-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793854.aspx).</span></span>
    
- <span data-ttu-id="13cd0-139">조직에서 사용자에게 만든 정책 설정을 적용하기 위해 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="13cd0-139">To apply the policy setting you created to a user in your organization, run:</span></span>
    
  ```PowerShell
  Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName "Block Incoming"
  ```
    <span data-ttu-id="13cd0-140">[Grant-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793857.aspx) cmdlet을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="13cd0-140">See more on the [Grant-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793857.aspx) cmdlet.</span></span>
    
### <a name="remove-a-caller-id-policy"></a><span data-ttu-id="13cd0-141">호출자 ID 정책 제거</span><span class="sxs-lookup"><span data-stu-id="13cd0-141">Remove a caller ID policy</span></span>

<span data-ttu-id="13cd0-142">조직에서 정책을 제거하려면 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="13cd0-142">To remove a policy from your organization, run:</span></span>
  
```PowerShell
Remove-CsCallingLineIdentity -Identity "My Caller ID Policy"
```
<span data-ttu-id="13cd0-143">사용자에서 정책을 제거하려면 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="13cd0-143">To remove a policy from a user, run:</span></span>
  
```PowerShell
Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName $null
```
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="13cd0-144">자세한 정보를 Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="13cd0-144">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="13cd0-145">Windows PowerShell 모든 것은 사용자 관리와 사용자가 허용되거나 허용되지 않는 작업을 관리하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="13cd0-145">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="13cd0-146">이 Windows PowerShell 여러 작업을 수행할 때 일상적인 작업을 단순화할 수 있는 단일 관리 지점을 사용하여 Microsoft 365 또는 Office 365 및 비즈니스용 Skype Online을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13cd0-146">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="13cd0-147">다음 항목을 Windows PowerShell 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="13cd0-147">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="13cd0-148">Windows PowerShell 및 비즈니스용 Skype Online 소개</span><span class="sxs-lookup"><span data-stu-id="13cd0-148">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="13cd0-149">Microsoft 365 또는 Office 365를 Windows PowerShell 사용하려는 6 가지 이유</span><span class="sxs-lookup"><span data-stu-id="13cd0-149">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Microsoft 365 or Office 365</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="13cd0-150">Windows PowerShell 사용자에 대한 설정을 한 번씩 변경하는 경우와 같이 Microsoft 365 관리 센터를 사용하는 경우와 같이 Microsoft 365 관리 센터를 사용하는 것 이상으로 속도, 단순성 및 생산성에 많은 이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13cd0-150">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="13cd0-151">다음 항목에서 이러한 이점에 대해 자세히 알아보습니다.</span><span class="sxs-lookup"><span data-stu-id="13cd0-151">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="13cd0-152">Microsoft 365 또는 Office 365를 관리하는 가장 좋은 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="13cd0-152">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="13cd0-153">비즈니스용 skype Windows PowerShell 관리하기 위해 사용</span><span class="sxs-lookup"><span data-stu-id="13cd0-153">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="13cd0-154">비즈니스용 Windows PowerShell Skype 온라인 관리 작업을 수행하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13cd0-154">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
  
 ## <a name="related-topics"></a><span data-ttu-id="13cd0-155">관련 항목</span><span class="sxs-lookup"><span data-stu-id="13cd0-155">Related topics</span></span>
[<span data-ttu-id="13cd0-156">전화 번호 전송 자주 묻는 질문</span><span class="sxs-lookup"><span data-stu-id="13cd0-156">Transferring phone numbers common questions</span></span>](/microsoftteams/transferring-phone-numbers-common-questions)

[<span data-ttu-id="13cd0-157">통화 계획에 사용되는 다양한 종류의 전화 번호</span><span class="sxs-lookup"><span data-stu-id="13cd0-157">Different kinds of phone numbers used for Calling Plans</span></span>](/microsoftteams/different-kinds-of-phone-numbers-used-for-calling-plans)

[<span data-ttu-id="13cd0-158">조직의 전화 번호 관리</span><span class="sxs-lookup"><span data-stu-id="13cd0-158">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="13cd0-159">전화 회선 ID 및 발신자 이름에 대한 자세한 정보</span><span class="sxs-lookup"><span data-stu-id="13cd0-159">More about Calling Line ID and Calling Party Name</span></span>](/skypeforbusiness/what-are-calling-plans-in-office-365/more-about-calling-line-ID-and-calling-party-name)

[<span data-ttu-id="13cd0-160">긴급 통화 사용 약관</span><span class="sxs-lookup"><span data-stu-id="13cd0-160">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)

<span data-ttu-id="13cd0-161">[비즈니스용 Skype Online: 긴급 통화 고지 사항 레이블](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="13cd0-161">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>
 
