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
description: 전화 걸기 ID라고도 하는 Microsoft 365 및 Office 365 기본 발신자 ID(사용자의 할당된 전화 번호)에 대해 자세히 알아보겠습니다. 사용자의 호출자 ID를 변경하거나 차단할 수 있습니다.
ms.openlocfilehash: ff8355b9435d0a21c032ee90b442884c0319221c
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814327"
---
# <a name="set-the-caller-id-for-a-user"></a><span data-ttu-id="74ead-104">사용자의 발신자 ID 설정</span><span class="sxs-lookup"><span data-stu-id="74ead-104">Set the Caller ID for a user</span></span>
<span data-ttu-id="74ead-105">Microsoft 365 및 Office 365의 전화 시스템은 사용자의 할당된 전화 번호인 기본 발신자 ID를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="74ead-105">The Phone System in Microsoft 365 and Office 365 provides a default caller ID that is the user's assigned telephone number.</span></span> <span data-ttu-id="74ead-106">사용자의 발신자 ID(호출 라인 ID라고도 하는)를 변경하거나 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74ead-106">You can either change or block the caller ID (also called a Calling Line ID) for a user.</span></span> <span data-ttu-id="74ead-107">조직에서 발신자 ID를 사용하는 방법을 확인하여 조직에서 발신자 ID를 사용하는 방법에 대해 자세히 알 [수 있습니다.](how-can-caller-id-be-used-in-your-organization.md)</span><span class="sxs-lookup"><span data-stu-id="74ead-107">You can learn more about how to use caller ID in your organization by going [How can caller ID be used in your organization](how-can-caller-id-be-used-in-your-organization.md).</span></span>
  
> [!TIP]
> <span data-ttu-id="74ead-108">비즈니스용 Skype Online에서는 현재 수신 전화를 차단할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="74ead-108">You can't block incoming calls currently in Skype for Business Online.</span></span> 
  
<span data-ttu-id="74ead-109">변경할 수 있는 설정이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74ead-109">There are settings that you can change:</span></span>
  
> [!NOTE]
> <span data-ttu-id="74ead-110">**Lync** 또는 비즈니스용 Skype Server가 있는 온-프레미스 조직에는 해당되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="74ead-110">This **is not** for on-premises organizations with Lync or Skype for Business Server.</span></span>
  
- <span data-ttu-id="74ead-111">**발신 발신자 ID 변경** 기본적으로 전화 번호인 사용자의 발신자 ID를 다른 전화 번호로 바꿀 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74ead-111">**Change their outgoing caller ID** You can replace a user's Caller ID, which by default is their telephone number, with another phone number.</span></span> <span data-ttu-id="74ead-112">예를 들어 사용자의 발신자 ID를 해당 전화 번호에서 비즈니스의 기본 전화 번호로 변경하거나 사용자의 통화 전화 번호에서 법률 부서의 주 전화 번호로 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74ead-112">For example, you could change the user's Caller ID from their phone number to a main phone number for your business or change the user's Calling Line ID from their phone number to a main phone number for the legal department.</span></span> <span data-ttu-id="74ead-113">통화 ID 번호를 온라인 서비스 번호(무료 또는 무료)로 변경할 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="74ead-113">You can change the Calling ID number to any Online **service** number (toll or toll-free).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="74ead-114">서비스 매개 변수를  사용하려면 유효한 서비스 번호를 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="74ead-114">If you want to use the  _Service_ parameter, you must specify a valid service number.</span></span>
  
- <span data-ttu-id="74ead-115">**아웃바운드 호출자 ID 차단** 사용자의 발신 PSTN 호출에서 발신 발신자 ID가 전송되지 못하도록 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74ead-115">**Block their outbound caller ID** You can block the outgoing Caller ID from being sent on a user's outgoing PSTN calls.</span></span> <span data-ttu-id="74ead-116">이렇게 하면 전화를 거는 사람의 전화 번호가 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="74ead-116">Doing this will block their phone number from being displayed on the phone of a person being called.</span></span>
    
- <span data-ttu-id="74ead-117">**수신 발신자 ID 차단** 사용자가 들어오는 모든 PSTN 호출에서 발신자 ID를 수신하지 못하도록 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74ead-117">**Block their incoming caller ID** You can block a user from receiving Caller ID on any incoming PSTN calls.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="74ead-118">긴급 통화는 항상 사용자의 전화 번호(발신자 ID)를 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="74ead-118">Emergency calls will always send the user's telephone number (caller ID).</span></span> 
  
<span data-ttu-id="74ead-119">기본적으로 이러한 호출자 ID 설정은 모두 **해제되어 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="74ead-119">By default, all of these caller ID settings are **turned off**.</span></span> <span data-ttu-id="74ead-120">즉, 비즈니스용 Skype Online 사용자의 전화 번호는 해당 사용자가 PSTN 전화로 전화를 걸 때 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74ead-120">This means that the Skype for Business Online user's phone number can be seen when that user makes a call to a PSTN phone.</span></span>
  
<span data-ttu-id="74ead-121">이러한 설정 및 설정 사용 방법에 대한 자세한 내용은 조직에서 호출자 ID를 사용하는 [방법으로 이동하세요.](how-can-caller-id-be-used-in-your-organization.md)</span><span class="sxs-lookup"><span data-stu-id="74ead-121">To learn more about these settings and how you can use them, go [How can caller ID be used in your organization](how-can-caller-id-be-used-in-your-organization.md).</span></span>
  
## <a name="set-your-caller-id-policy-settings"></a><span data-ttu-id="74ead-122">호출자 ID 정책 설정 설정</span><span class="sxs-lookup"><span data-stu-id="74ead-122">Set your caller ID policy settings</span></span>

> [!NOTE]
> <span data-ttu-id="74ead-123">비즈니스용 Skype Online의 모든 발신자 ID 설정은 Windows PowerShell 비즈니스용  Skype 관리 센터를 사용할 **수 없습니다.**</span><span class="sxs-lookup"><span data-stu-id="74ead-123">For all of the Caller ID settings in Skype for Business Online, you must use Windows PowerShell and you **can't use** the **Skype for Business admin center**.</span></span> 
  
### <a name="verify-and-start-windows-powershell"></a><span data-ttu-id="74ead-124">확인 및 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="74ead-124">Verify and start Windows PowerShell</span></span>

- <span data-ttu-id="74ead-125">**버전 3.0 Windows PowerShell 실행 중인지 확인**</span><span class="sxs-lookup"><span data-stu-id="74ead-125">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
    
1. <span data-ttu-id="74ead-126">버전 3.0 이상을 실행하고 있는지 확인: 시작 메뉴를  >  Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="74ead-126">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="74ead-127">웹 창에  _Get-Host를_ 입력하여 **Windows PowerShell** 확인</span><span class="sxs-lookup"><span data-stu-id="74ead-127">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="74ead-128">버전 3.0 이상이 없는 경우 업데이트를 다운로드하여 설치해야 Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="74ead-128">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell.</span></span> <span data-ttu-id="74ead-129">버전 [Windows Management Framework 4.0으로](https://go.microsoft.com/fwlink/?LinkId=716845) Windows PowerShell 다운로드하고 업데이트하려면 4.0을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="74ead-129">See [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0.</span></span> <span data-ttu-id="74ead-130">메시지가 표시될 때 컴퓨터를 다시 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="74ead-130">Restart your computer when you are prompted.</span></span>
    
4. <span data-ttu-id="74ead-131">또한 비즈니스용 Skype Online에 Windows PowerShell 원격 Windows PowerShell 세션을 만들 수 있는 비즈니스용 Skype Online용 Windows PowerShell 모듈을 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="74ead-131">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span> <span data-ttu-id="74ead-132">64비트 컴퓨터에서만 지원되는 이 모듈은 비즈니스용 Skype Online용 Windows PowerShell 모듈의 Microsoft 다운로드 센터에서 다운로드할 [수 있습니다.](https://go.microsoft.com/fwlink/?LinkId=294688)</span><span class="sxs-lookup"><span data-stu-id="74ead-132">This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688).</span></span> <span data-ttu-id="74ead-133">메시지가 표시될 경우 컴퓨터를 다시 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="74ead-133">Restart your computer if you are prompted.</span></span>
    
    <span data-ttu-id="74ead-134">자세한 내용은 단일 창에서 모든 [Microsoft 365 또는 Office 365 서비스에 Windows PowerShell 참조합니다.](https://technet.microsoft.com/library/dn568015.aspx)</span><span class="sxs-lookup"><span data-stu-id="74ead-134">If you need to know more, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx).</span></span>
    
- <span data-ttu-id="74ead-135">**세션 Windows PowerShell 시작**</span><span class="sxs-lookup"><span data-stu-id="74ead-135">**Start a Windows PowerShell session**</span></span>
    
1. <span data-ttu-id="74ead-136">시작 **메뉴에서**  >  **Windows PowerShell.**</span><span class="sxs-lookup"><span data-stu-id="74ead-136">From the **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="74ead-137">다음 **Windows PowerShell** 실행하여 Microsoft 365 또는 Office 365에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="74ead-137">In the **Windows PowerShell** window, connect to your Microsoft 365 or Office 365 by running:</span></span>
    
   > [!NOTE]
   >
   > <span data-ttu-id="74ead-138">비즈니스용 Skype Online 커넥터는 현재 최신 Teams PowerShell 모듈의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="74ead-138">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span>
   > <span data-ttu-id="74ead-139">최신 [Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/)공개 릴리스를 사용하는 경우 비즈니스용 Skype Online Connector를 설치할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="74ead-139">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>
   ```PowerShell
    Import-Module -Name MicrosoftTeams
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
   ```

<span data-ttu-id="74ead-140">Windows PowerShell 시작에 대한 자세한 내용은 단일 Windows PowerShell 창에서 모든 [Microsoft 365 또는 Office 365](https://technet.microsoft.com/library/dn568015.aspx) 서비스에 연결 또는 [Windows PowerShell.](/skypeforbusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="74ead-140">If you want more information about starting Windows PowerShell, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx) or [Set up your computer for Windows PowerShell](/skypeforbusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>
    
### <a name="see-all-of-the-caller-id-policy-settings-in-your-organization"></a><span data-ttu-id="74ead-141">조직의 모든 호출자 ID 정책 설정 보기</span><span class="sxs-lookup"><span data-stu-id="74ead-141">See all of the caller ID policy settings in your organization</span></span>

- <span data-ttu-id="74ead-142">조직의 모든 호출자 ID 정책 설정을 확인하려면 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="74ead-142">To view all of the caller ID policy settings in your organization, run:</span></span>

  ```PowerShell
  Get-CsCallingLineIdentity |fl
  ```
  <span data-ttu-id="74ead-143">[Get-CsCallingLineIdentity에](https://technet.microsoft.com/library/mt793856.aspx)대한 추가 예제 및 세부 정보를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="74ead-143">See more examples and details for [Get-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793856.aspx).</span></span>
    
### <a name="create-a-new-caller-id-policy-for-your-organization"></a><span data-ttu-id="74ead-144">조직에 대한 새 호출자 ID 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="74ead-144">Create a new caller ID policy for your organization</span></span>


- <span data-ttu-id="74ead-145">호출자 ID를 익명으로 설정하는 새 호출자 ID 정책을 만들면 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="74ead-145">To create a new caller ID policy that sets the caller ID to anonymous, run:</span></span>
    
  ```PowerShell
  New-CsCallingLineIdentity  -Identity Anonymous -Description "Anonymous policy" -CallingIDSubstitute Anonymous -EnableUserOverride $false
  ```
  > [!NOTE]  
  > <span data-ttu-id="74ead-146">모든 경우에 "서비스 번호" 필드에는 초기 "+"가 포함되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="74ead-146">In all cases, the "Service Number" field should not include an initial "+".</span></span>

  <span data-ttu-id="74ead-147">[New-CsCallingLineIdentity에](https://technet.microsoft.com/library/mt793855.aspx)대한 추가 예제 및 세부 정보를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="74ead-147">See more examples and details for [New-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793855.aspx).</span></span>
    
- <span data-ttu-id="74ead-148">Amos Marble에 만든 새 정책을 적용하기 위해 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="74ead-148">To apply the new policy you created to Amos Marble, run:</span></span>
    
  ```PowerShell
   Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName Anonymous
  ```
  <span data-ttu-id="74ead-149">[Grant-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793857.aspx) cmdlet에 대한 자세한 내용은 다음을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="74ead-149">See more on the [Grant-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793857.aspx) cmdlet.</span></span>
    
<span data-ttu-id="74ead-150">이미 정책을 만든 경우 [Set-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793854.aspx) cmdlet을 사용하여 기존 정책을 변경한 다음 [Grant-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793857.aspx) cmdlet을 사용하여 사용자에게 설정을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74ead-150">If you have already created a policy, you can use the [Set-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793854.aspx) cmdlet to make changes to the existing policy, and then use the [Grant-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793857.aspx) cmdlet to apply the settings to your users.</span></span>
  
### <a name="set-it-so-the-incoming-caller-id-is-blocked"></a><span data-ttu-id="74ead-151">수신 발신자 ID가 차단되지 있도록 설정</span><span class="sxs-lookup"><span data-stu-id="74ead-151">Set it so the incoming caller ID is blocked</span></span>

- <span data-ttu-id="74ead-152">들어오는 호출자 ID를 차단하기 위해 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="74ead-152">To block the incoming caller ID, run:</span></span>
    
  ```PowerShell
  Set-CsCallingLineIdentity  -Identity "Block Incoming" -BlockIncomingPstnCallerID $true -EnableUserOverride $true
  ```
  <span data-ttu-id="74ead-153">[Set-CsCallingLineIdentity에](https://technet.microsoft.com/library/mt793854.aspx)대한 추가 예제 및 세부 정보를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="74ead-153">See more examples and details for [Set-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793854.aspx).</span></span>
    
- <span data-ttu-id="74ead-154">만든 정책 설정을 조직의 사용자에게 적용하기 위해 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="74ead-154">To apply the policy setting you created to a user in your organization, run:</span></span>
    
  ```PowerShell
  Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName "Block Incoming"
  ```
    <span data-ttu-id="74ead-155">[Grant-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793857.aspx) cmdlet에 대한 자세한 내용은 다음을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="74ead-155">See more on the [Grant-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793857.aspx) cmdlet.</span></span>
    
### <a name="remove-a-caller-id-policy"></a><span data-ttu-id="74ead-156">호출자 ID 정책 제거</span><span class="sxs-lookup"><span data-stu-id="74ead-156">Remove a caller ID policy</span></span>

<span data-ttu-id="74ead-157">조직에서 정책을 제거하려면 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="74ead-157">To remove a policy from your organization, run:</span></span>
  
```PowerShell
Remove-CsCallingLineIdentity -Identity "My Caller ID Policy"
```
<span data-ttu-id="74ead-158">사용자로부터 정책을 제거하려면 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="74ead-158">To remove a policy from a user, run:</span></span>
  
```PowerShell
Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName $null
```
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="74ead-159">자세한 내용은 Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="74ead-159">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="74ead-160">Windows PowerShell 관리는 사용자 및 사용자가 허용되거나 허용되지 않는 작업을 관리하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="74ead-160">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="74ead-161">이 Windows PowerShell 여러 작업을 수행할 때 일상적인 작업을 간소화할 수 있는 단일 관리 지점을 사용하여 Microsoft 365 또는 Office 365 및 비즈니스용 Skype Online을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74ead-161">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="74ead-162">다음 항목을 Windows PowerShell 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="74ead-162">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="74ead-163">Windows PowerShell 및 Lync Online 소개</span><span class="sxs-lookup"><span data-stu-id="74ead-163">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="74ead-164">Microsoft 365 또는 Office 365를 관리하기 위해 Windows PowerShell 사용할 수 있는 6 가지 이유</span><span class="sxs-lookup"><span data-stu-id="74ead-164">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Microsoft 365 or Office 365</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="74ead-165">Windows PowerShell Microsoft 365 관리 센터를 사용하는 경우와 같이 여러 사용자에 대해 한 번씩 설정을 변경하는 경우와 같이 속도, 단순성 및 생산성에 많은 이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74ead-165">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="74ead-166">다음 항목에서 이러한 이점에 대해 자세히 배워야 합니다.</span><span class="sxs-lookup"><span data-stu-id="74ead-166">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="74ead-167">Microsoft 365 또는 Office 365를 관리하는 가장 좋은 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="74ead-167">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="74ead-168">비즈니스 Windows PowerShell 사용하여 비즈니스용 Skype Online 관리</span><span class="sxs-lookup"><span data-stu-id="74ead-168">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="74ead-169">비즈니스용 Windows PowerShell Skype Online 관리 작업을 수행하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74ead-169">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
  
 ## <a name="related-topics"></a><span data-ttu-id="74ead-170">관련 항목</span><span class="sxs-lookup"><span data-stu-id="74ead-170">Related topics</span></span>
[<span data-ttu-id="74ead-171">전화 번호 전송 자주 묻는 질문</span><span class="sxs-lookup"><span data-stu-id="74ead-171">Transferring phone numbers common questions</span></span>](/microsoftteams/transferring-phone-numbers-common-questions)

[<span data-ttu-id="74ead-172">통화 요금제에 사용되는 다양한 종류의 전화 번호</span><span class="sxs-lookup"><span data-stu-id="74ead-172">Different kinds of phone numbers used for Calling Plans</span></span>](/microsoftteams/different-kinds-of-phone-numbers-used-for-calling-plans)

[<span data-ttu-id="74ead-173">조직의 전화 번호 관리</span><span class="sxs-lookup"><span data-stu-id="74ead-173">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="74ead-174">전화 회선 ID 및 발신자 이름에 대한 자세한 정보</span><span class="sxs-lookup"><span data-stu-id="74ead-174">More about Calling Line ID and Calling Party Name</span></span>](/skypeforbusiness/what-are-calling-plans-in-office-365/more-about-calling-line-ID-and-calling-party-name)

[<span data-ttu-id="74ead-175">긴급 통화 사용 약관</span><span class="sxs-lookup"><span data-stu-id="74ead-175">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)

<span data-ttu-id="74ead-176">[비즈니스용 Skype Online: 긴급 통화 고지 사항 레이블](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="74ead-176">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>
 
