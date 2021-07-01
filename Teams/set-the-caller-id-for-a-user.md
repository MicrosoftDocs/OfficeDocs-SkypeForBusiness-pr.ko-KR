---
title: 사용자의 발신자 ID 설정
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: jens, roykuntz
ms.topic: article
ms.assetid: c7323490-d9b7-421a-aa76-5bd485f80583
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business Online
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Calling Plans
- seo-marvel-mar2020
description: 호출 Microsoft 365 Office 365 기본 호출자 ID(사용자의 할당된 전화 번호)에 대해 자세히 알아보겠습니다. 사용자의 발신자 ID를 변경하거나 차단할 수 있습니다.
ms.openlocfilehash: 20b80bbc96f46d6b1a2766eea367132b9e0b1418
ms.sourcegitcommit: b39bd1de0219a9e3a3b0c97fc485c9578ddb643c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2021
ms.locfileid: "53230605"
---
# <a name="set-the-caller-id-for-a-user"></a><span data-ttu-id="770ff-104">사용자의 발신자 ID 설정</span><span class="sxs-lookup"><span data-stu-id="770ff-104">Set the Caller ID for a user</span></span>

<span data-ttu-id="770ff-105">전화 시스템 Microsoft 365 사용자의 할당된 전화 번호인 기본 호출자 ID를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="770ff-105">Phone System in Microsoft 365 provides a default caller ID that is the user's assigned telephone number.</span></span> <span data-ttu-id="770ff-106">사용자의 발신자 ID(호출 줄 ID라고도 하는)를 변경하거나 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="770ff-106">You can either change or block the caller ID (also called a Calling Line ID) for a user.</span></span> <span data-ttu-id="770ff-107">조직에서 발신자 ID를 사용할 수 있는 방법 을 확인하여 조직에서 발신자 ID를 사용하는 방법에 대해 [자세히 알아보면 됩니다.](how-can-caller-id-be-used-in-your-organization.md)</span><span class="sxs-lookup"><span data-stu-id="770ff-107">You can learn more about how to use caller ID in your organization by going [How can caller ID be used in your organization](how-can-caller-id-be-used-in-your-organization.md).</span></span>
  
<span data-ttu-id="770ff-108">기본적으로 다음 호출자 ID 설정이 **해제됩니다.**</span><span class="sxs-lookup"><span data-stu-id="770ff-108">By default, the following caller ID settings are **turned off**.</span></span> <span data-ttu-id="770ff-109">즉, 해당 사용자가 PSTN Teams 전화를 걸 때 사용자의 전화 번호를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="770ff-109">This means that the Teams user's phone number can be seen when that user makes a call to a PSTN phone.</span></span> <span data-ttu-id="770ff-110">다음과 같이 이러한 설정을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="770ff-110">You can change these settings as follows:</span></span>
  
- <span data-ttu-id="770ff-111">**발신 발신자 ID** 기본적으로 해당 전화 번호인 사용자의 발신자 ID를 다른 전화 번호로 바꿀 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="770ff-111">**Outgoing caller ID** You can replace a user's Caller ID, which by default is their telephone number, with another phone number.</span></span> <span data-ttu-id="770ff-112">예를 들어 사용자의 발신자 ID를 해당 전화 번호에서 비즈니스의 주 전화 번호로 변경하거나 사용자의 전화 번호에서 법무 부서의 주 전화 번호로 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="770ff-112">For example, you could change the user's Caller ID from their phone number to a main phone number for your business or change the user's Calling Line ID from their phone number to a main phone number for the legal department.</span></span> <span data-ttu-id="770ff-113">통화 ID 번호를 모든 온라인 서비스 번호로 변경할 수 있습니다(전화 또는 무료).</span><span class="sxs-lookup"><span data-stu-id="770ff-113">You can change the Calling ID number to any online service number (toll or toll-free).</span></span> <span data-ttu-id="770ff-114">전화 걸기 ID 번호를 전화 큐 또는 통화 큐에서 사용하는 리소스 계정에 할당된 직접 라우팅을 통해 자동 전화 교환 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="770ff-114">You can also change the Calling ID number to an on-premises phone number through Direct Routing that is assigned to a resource account used by an Auto Attendant or Call Queue.</span></span>
    
  > [!NOTE]
  > <span data-ttu-id="770ff-115">서비스 매개 변수를 *사용하려면* 유효한 서비스 번호를 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="770ff-115">If you want to use the *Service* parameter, you must specify a valid service number.</span></span>
  > <span data-ttu-id="770ff-116">드롭다운에 표시되지 않는 경우 리소스 계정 번호에 PowerShell cmdlet을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="770ff-116">You need to use the PowerShell cmdlets for Resource account number if not visible in drop down.</span></span>
  
- <span data-ttu-id="770ff-117">**아웃바운드 호출자 ID를 차단합니다.**</span><span class="sxs-lookup"><span data-stu-id="770ff-117">**Block outbound caller ID.**</span></span> <span data-ttu-id="770ff-118">사용자의 발신 PSTN 호출에서 발신 호출자 ID가 전송되지 못하도록 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="770ff-118">You can block the outgoing Caller ID from being sent on a user's outgoing PSTN calls.</span></span> <span data-ttu-id="770ff-119">이렇게 하면 전화 번호가 호출되는 사람의 휴대폰에 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="770ff-119">Doing this will block their phone number from being displayed on the phone of a person being called.</span></span>
    
- <span data-ttu-id="770ff-120">**들어오는 발신자 ID를 차단합니다.**</span><span class="sxs-lookup"><span data-stu-id="770ff-120">**Block incoming caller ID.**</span></span> <span data-ttu-id="770ff-121">사용자가 들어오는 PSTN 호출에서 발신자 ID를 수신하지 못하도록 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="770ff-121">You can block a user from receiving Caller ID on any incoming PSTN calls.</span></span>

- <span data-ttu-id="770ff-122">**CNAM(호출 파티 이름)을 설정합니다.**</span><span class="sxs-lookup"><span data-stu-id="770ff-122">**Set Calling Party Name (CNAM).**</span></span> <span data-ttu-id="770ff-123">사용자의 Microsoft Teams 아웃바운드 PSTN 호출에 CNAM을 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="770ff-123">For your Microsoft Teams users you can send a CNAM on outbound PSTN calls.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="770ff-124">긴급 통화는 항상 사용자의 전화 번호(발신자 ID)를 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="770ff-124">Emergency calls will always send the user's telephone number (caller ID).</span></span> 
  

  
<span data-ttu-id="770ff-125">이러한 설정 및 해당 설정을 사용하는 방법에 대한 자세한 내용은 조직에서 발신자 ID를 사용할 수 있는 [방법을 참조하세요.](how-can-caller-id-be-used-in-your-organization.md)</span><span class="sxs-lookup"><span data-stu-id="770ff-125">To learn more about these settings and how you can use them, see [How can caller ID be used in your organization](how-can-caller-id-be-used-in-your-organization.md).</span></span>
  
## <a name="set-your-caller-id-policy-settings"></a><span data-ttu-id="770ff-126">발신자 ID 정책 설정 설정</span><span class="sxs-lookup"><span data-stu-id="770ff-126">Set your caller ID policy settings</span></span>

> [!NOTE]
> <span data-ttu-id="770ff-127">발신자 ID를 리소스 계정 전화 번호로 설정하고 통화 파티 이름을 설정하려면 PowerShell New-CsCallingLineIdentity 또는 Set-CsCallingLineIdentity PowerShell Teams 2.3.1 이상에서 PowerShell cmdlet을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="770ff-127">To set the caller ID to a resource account phone number and to set the calling party name, use the PowerShell cmdlets New-CsCallingLineIdentity or Set-CsCallingLineIdentity in the Teams PowerShell module 2.3.1 or later.</span></span> <span data-ttu-id="770ff-128">(이러한 옵션은 현재 관리 센터에서 Microsoft Teams 없습니다.)</span><span class="sxs-lookup"><span data-stu-id="770ff-128">(These options are not currently available in the Microsoft Teams admin center.)</span></span> 

<span data-ttu-id="770ff-129">명령 Windows PowerShell 프롬프트를 열고 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="770ff-129">Open a Windows PowerShell command prompt and run the following commands:</span></span>

```PowerShell
# When using Teams PowerShell Module

Import-Module MicrosoftTeams
$credential = Get-Credential
Connect-MicrosoftTeams -Credential $credential
``` 

### <a name="view-create-and-apply-policy-settings"></a><span data-ttu-id="770ff-130">정책 설정 보기, 만들기 및 적용</span><span class="sxs-lookup"><span data-stu-id="770ff-130">View, create, and apply policy settings</span></span>

1. <span data-ttu-id="770ff-131">조직의 모든 호출자 ID 정책 설정을 확인하려면 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="770ff-131">To view all of the caller ID policy settings in your organization, run:</span></span>

     ```PowerShell
     Get-CsCallingLineIdentity |fl
     ```
   <span data-ttu-id="770ff-132">자세한 내용은 [Get-CsCallingLineIdentity 를 참조하세요.](/powershell/module/skype/Get-CsCallingLineIdentity)</span><span class="sxs-lookup"><span data-stu-id="770ff-132">For more information, see [Get-CsCallingLineIdentity](/powershell/module/skype/Get-CsCallingLineIdentity).</span></span>
    
2. <span data-ttu-id="770ff-133">조직에 대한 새 호출자 ID 정책을 만들 경우 New-CsCallingIdentity cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="770ff-133">To create a new caller ID policy for your organization, use the New-CsCallingIdentity cmdlet:</span></span>
    
     ```PowerShell
     New-CsCallingLineIdentity  -Identity Anonymous -Description "Anonymous policy" -CallingIDSubstitute Anonymous -EnableUserOverride $false
     ```
    <span data-ttu-id="770ff-134">모든 경우 "서비스 번호" 필드에는 초기 "+"가 포함되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="770ff-134">In all cases, the "Service Number" field should not include an initial "+".</span></span>

   <span data-ttu-id="770ff-135">자세한 내용은 [New-CsCallingLineIdentity 를 참조하세요.](/powershell/module/skype/New-CsCallingLineIdentity)</span><span class="sxs-lookup"><span data-stu-id="770ff-135">For more information, see [New-CsCallingLineIdentity](/powershell/module/skype/New-CsCallingLineIdentity).</span></span>
    
3. <span data-ttu-id="770ff-136">Grant-CsCallingIdentity cmdlet을 사용하여 만든 새 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="770ff-136">Apply the new policy you created by using the Grant-CsCallingIdentity cmdlet.</span></span> <span data-ttu-id="770ff-137">예를 들어 다음 예제에서는 사용자 Amos Marble에 새 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="770ff-137">For example, the following example applies the new policy to user Amos Marble.</span></span>
    
     ```PowerShell
      Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName Anonymous
     ```
   <span data-ttu-id="770ff-138">자세한 내용은 [Grant-CsCallingLineIdentity](/powershell/module/skype/Grant-CsCallingLineIdentity) cmdlet을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="770ff-138">For more information, see [Grant-CsCallingLineIdentity](/powershell/module/skype/Grant-CsCallingLineIdentity) cmdlet.</span></span>
    

4. <span data-ttu-id="770ff-139">들어오는 호출자 ID를 차단하려는 경우 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="770ff-139">If you want to block the incoming caller ID, run:</span></span>
    
   ```PowerShell
   Set-CsCallingLineIdentity  -Identity "Block Incoming" -BlockIncomingPstnCallerID $true
   ``` 

   <span data-ttu-id="770ff-140">자세한 내용은 [Set-CsCallingLineIdentity 를 참조하세요.](/powershell/module/skype/Set-CsCallingLineIdentity)</span><span class="sxs-lookup"><span data-stu-id="770ff-140">For more information, see [Set-CsCallingLineIdentity](/powershell/module/skype/Set-CsCallingLineIdentity).</span></span>
    
5. <span data-ttu-id="770ff-141">조직에서 사용자에게 만든 정책 설정을 적용하기 위해 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="770ff-141">To apply the policy setting you created to a user in your organization, run:</span></span>
    
   ```PowerShell
   Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName "Block Incoming"
   ```
   <span data-ttu-id="770ff-142">자세한 내용은 [Grant-CsCallingLineIdentity 를 참조하세요.](/powershell/module/skype/Grant-CsCallingLineIdentity)</span><span class="sxs-lookup"><span data-stu-id="770ff-142">For more information, see [Grant-CsCallingLineIdentity](/powershell/module/skype/Grant-CsCallingLineIdentity).</span></span>

6. <span data-ttu-id="770ff-143">호출자 ID를 지정된 리소스 계정의 전화 번호로 설정하고 호출자 이름을 Contoso로 설정하는 새 호출자 ID 정책을 만들면 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="770ff-143">To create a new Caller ID policy that sets the Caller ID to the phone number of the specified resource account and sets the Calling party name to Contoso:</span></span>

   ```PowerShell
   $ObjId = (Get-CsOnlineApplicationInstance -Identity dkcq@contoso.com).ObjectId
   New-CsCallingLineIdentity  -Identity DKCQ -CallingIDSubstitute Resource -EnableUserOverride $false -ResourceAccount $ObjId -CompanyName "Contoso"
   ```

<span data-ttu-id="770ff-144">정책을 이미 만든 경우 [Set-CsCallingLineIdentity](/powershell/module/skype/Set-CsCallingLineIdentity) cmdlet을 사용하여 기존 정책을 변경한 다음 [Grant-CsCallingLineIdentity](/powershell/module/skype/Grant-CsCallingLineIdentity) cmdlet을 사용하여 사용자에게 설정을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="770ff-144">If you have already created a policy, you can use the [Set-CsCallingLineIdentity](/powershell/module/skype/Set-CsCallingLineIdentity) cmdlet to make changes to the existing policy, and then use the [Grant-CsCallingLineIdentity](/powershell/module/skype/Grant-CsCallingLineIdentity) cmdlet to apply the settings to your users.</span></span>
    
### <a name="remove-a-policy-setting"></a><span data-ttu-id="770ff-145">정책 설정 제거</span><span class="sxs-lookup"><span data-stu-id="770ff-145">Remove a policy setting</span></span>

<span data-ttu-id="770ff-146">조직에서 정책을 제거하려면 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="770ff-146">To remove a policy from your organization, run:</span></span>
  
```PowerShell
Remove-CsCallingLineIdentity -Identity "My Caller ID Policy"
```
<span data-ttu-id="770ff-147">사용자에서 정책을 제거하려면 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="770ff-147">To remove a policy from a user, run:</span></span>
  
```PowerShell
Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName $null
```
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="770ff-148">자세한 정보를 Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="770ff-148">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="770ff-149">Windows PowerShell 모든 것은 사용자 관리와 사용자가 허용되거나 허용되지 않는 작업을 관리하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="770ff-149">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="770ff-150">이 Windows PowerShell 사용하면 관리 Microsoft 365 단순화할 수 있는 단일 관리 지점을 사용하여 관리 작업을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="770ff-150">With Windows PowerShell, you can manage Microsoft 365 using a single point of administration that can simplify your daily work.</span></span> <span data-ttu-id="770ff-151">다음 항목을 Windows PowerShell 다음 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="770ff-151">To get started with Windows PowerShell, see these topics:</span></span>
    
- [<span data-ttu-id="770ff-152">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="770ff-152">An introduction to Windows PowerShell</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
- [<span data-ttu-id="770ff-153">를 사용하여 Windows PowerShell 관리하려는 6 가지 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="770ff-153">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Microsoft 365</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
- <span data-ttu-id="770ff-154">Windows PowerShell 많은 사용자에 대해 설정을 한 Microsoft 365 관리 센터 설정하는 경우와 같이 데이터만 사용하여 속도, 단순성 및 생산성에 많은 이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="770ff-154">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="770ff-155">다음 항목에서 이러한 이점에 대해 자세히 알아보습니다.</span><span class="sxs-lookup"><span data-stu-id="770ff-155">Learn about these advantages in the following topics:</span></span>
    
- <span data-ttu-id="770ff-156">[데이터를 사용하여 Microsoft 365 가장 Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="770ff-156">[Best ways to manage Microsoft 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
- [<span data-ttu-id="770ff-157">온라인 Windows PowerShell 관리하기 위해 비즈니스용 Skype 사용</span><span class="sxs-lookup"><span data-stu-id="770ff-157">Using Windows PowerShell to manage Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
- [<span data-ttu-id="770ff-158">일반적인 Windows PowerShell 관리 작업을 수행하는 데 비즈니스용 Skype 사용</span><span class="sxs-lookup"><span data-stu-id="770ff-158">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
  
 ## <a name="related-topics"></a><span data-ttu-id="770ff-159">관련 항목</span><span class="sxs-lookup"><span data-stu-id="770ff-159">Related topics</span></span>
[<span data-ttu-id="770ff-160">전화 번호 전송 자주 묻는 질문</span><span class="sxs-lookup"><span data-stu-id="770ff-160">Transferring phone numbers common questions</span></span>](./phone-number-calling-plans/port-order-overview.md)

[<span data-ttu-id="770ff-161">통화 계획에 사용되는 다양한 종류의 전화 번호</span><span class="sxs-lookup"><span data-stu-id="770ff-161">Different kinds of phone numbers used for Calling Plans</span></span>](./different-kinds-of-phone-numbers-used-for-calling-plans.md)

[<span data-ttu-id="770ff-162">조직의 전화 번호 관리</span><span class="sxs-lookup"><span data-stu-id="770ff-162">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="770ff-163">전화 회선 ID 및 발신자 이름에 대한 자세한 정보</span><span class="sxs-lookup"><span data-stu-id="770ff-163">More about Calling Line ID and Calling Party Name</span></span>](/skypeforbusiness/what-are-calling-plans-in-office-365/more-about-calling-line-ID-and-calling-party-name)

[<span data-ttu-id="770ff-164">긴급 통화 사용 약관</span><span class="sxs-lookup"><span data-stu-id="770ff-164">Emergency calling terms and conditions</span></span>](./emergency-calling-terms-and-conditions.md)

<span data-ttu-id="770ff-165">[비즈니스용 Skype 온라인: 긴급 통화 고지 사항 레이블](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="770ff-165">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>
