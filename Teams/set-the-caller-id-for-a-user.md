---
title: 사용자의 발신자 ID 설정
ms.author: tonysmit
author: tonysmit
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
description: Microsoft 365 및 Office 365 기본 발신자 ID (사용자의 지정 된 전화 번호)에 대해 알아보고 전화 라인 ID 라고도 합니다. 사용자의 발신자 ID를 변경 하거나 차단할 수 있습니다.
ms.openlocfilehash: 059e92f04f3d4a5df73ed9201f1f784f2bd01f30
ms.sourcegitcommit: 1807ea5509f8efa6abba8462bce2f3646117e8bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/10/2020
ms.locfileid: "44691124"
---
# <a name="set-the-caller-id-for-a-user"></a><span data-ttu-id="803a4-104">사용자의 발신자 ID 설정</span><span class="sxs-lookup"><span data-stu-id="803a4-104">Set the Caller ID for a user</span></span>
<span data-ttu-id="803a4-105">Microsoft 365 및 Office 365의 전화 시스템은 사용자가 할당 한 전화 번호에 해당 하는 기본 발신자 ID를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="803a4-105">The Phone System in Microsoft 365 and Office 365 provides a default caller ID that is the user's assigned telephone number.</span></span> <span data-ttu-id="803a4-106">사용자의 발신자 ID (통화 라인 ID 라고도 함)를 변경 하거나 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="803a4-106">You can either change or block the caller ID (also called a Calling Line ID) for a user.</span></span> <span data-ttu-id="803a4-107">조직에서 발신자 id를 사용 하는 [방법을](how-can-caller-id-be-used-in-your-organization.md)확인 하 여 조직에서 발신자 id를 사용 하는 방법에 대해 자세히 알아볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="803a4-107">You can learn more about how to use caller ID in your organization by going [How can caller ID be used in your organization](how-can-caller-id-be-used-in-your-organization.md).</span></span>
  
> [!TIP]
> <span data-ttu-id="803a4-108">현재 비즈니스용 Skype Online에서 수신 전화를 차단할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="803a4-108">You can't block incoming calls currently in Skype for Business Online.</span></span> 
  
<span data-ttu-id="803a4-109">변경할 수 있는 설정은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="803a4-109">There are settings that you can change:</span></span>
  
> [!NOTE]
> <span data-ttu-id="803a4-110">이 **는** Lync 또는 비즈니스용 Skype Server를 사용 하는 온-프레미스 조직에는 해당 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="803a4-110">This **is not** for on-premises organizations with Lync or Skype for Business Server.</span></span>
  
- <span data-ttu-id="803a4-111">**보내는 발신자 ID 변경** 기본적으로 사용자의 발신자 ID를 다른 전화 번호로 바꿀 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="803a4-111">**Change their outgoing caller ID** You can replace a user's Caller ID, which by default is their telephone number, with another phone number.</span></span> <span data-ttu-id="803a4-112">예를 들어 사용자의 발신자 ID를 자신의 전화 번호에서 비즈니스의 기본 전화 번호로 변경 하거나 사용자의 통화 라인 ID를 자신의 전화 번호에서 법률 부서의 대표 전화 번호로 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="803a4-112">For example, you could change the user's Caller ID from their phone number to a main phone number for your business or change the user's Calling Line ID from their phone number to a main phone number for the legal department.</span></span> <span data-ttu-id="803a4-113">전화 번호를 온라인 **서비스** 번호로 변경 (유료 또는 무료 무료) 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="803a4-113">You can change the Calling ID number to any Online **service** number (toll or toll-free).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="803a4-114">_서비스_ 매개 변수를 사용 하려면 유효한 서비스 번호를 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="803a4-114">If you want to use the  _Service_ parameter, you must specify a valid service number.</span></span>
  
- <span data-ttu-id="803a4-115">**아웃 바운드 발신자 ID 차단** 사용자의 발신 PSTN 호출에서 보내는 발신자 ID를 보내는 것을 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="803a4-115">**Block their outbound caller ID** You can block the outgoing Caller ID from being sent on a user's outgoing PSTN calls.</span></span> <span data-ttu-id="803a4-116">이렇게 하면 전화 번호가 호출 되는 사람의 전화에 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="803a4-116">Doing this will block their phone number from being displayed on the phone of a person being called.</span></span>
    
- <span data-ttu-id="803a4-117">**받는 발신자 ID 차단** 사용자가 들어오는 PSTN 호출에 대해 발신자 ID를 받지 못하도록 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="803a4-117">**Block their incoming caller ID** You can block a user from receiving Caller ID on any incoming PSTN calls.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="803a4-118">비상 전화는 항상 사용자의 전화 번호 (발신자 ID)를 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="803a4-118">Emergency calls will always send the user's telephone number (caller ID).</span></span> 
  
<span data-ttu-id="803a4-119">기본적으로 이러한 모든 발신자 ID 설정이 **해제**됩니다.</span><span class="sxs-lookup"><span data-stu-id="803a4-119">By default, all of these caller ID settings are **turned off**.</span></span> <span data-ttu-id="803a4-120">이는 사용자가 PSTN 전화기로 전화를 걸 때 비즈니스용 Skype Online 사용자의 전화 번호가 표시 될 수 있음을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="803a4-120">This means that the Skype for Business Online user's phone number can be seen when that user makes a call to a PSTN phone.</span></span>
  
<span data-ttu-id="803a4-121">이러한 설정과 이러한 설정을 사용 하는 방법에 대 한 자세한 내용은 [조직에서 발신자 ID를 사용](how-can-caller-id-be-used-in-your-organization.md)하는 방법을 참고 하세요.</span><span class="sxs-lookup"><span data-stu-id="803a4-121">To learn more about these settings and how you can use them, go [How can caller ID be used in your organization](how-can-caller-id-be-used-in-your-organization.md).</span></span>
  
## <a name="set-your-caller-id-policy-settings"></a><span data-ttu-id="803a4-122">발신자 ID 정책 설정</span><span class="sxs-lookup"><span data-stu-id="803a4-122">Set your caller ID policy settings</span></span>

> [!NOTE]
> <span data-ttu-id="803a4-123">비즈니스용 Skype Online의 모든 발신자 ID 설정에 대해 Windows PowerShell을 사용 해야 하며 **비즈니스용 skype 관리 센터**를 **사용할 수 없습니다** .</span><span class="sxs-lookup"><span data-stu-id="803a4-123">For all of the Caller ID settings in Skype for Business Online, you must use Windows PowerShell and you **can't use** the **Skype for Business admin center**.</span></span> 
  
### <a name="verify-and-start-windows-powershell"></a><span data-ttu-id="803a4-124">Windows PowerShell 확인 및 시작</span><span class="sxs-lookup"><span data-stu-id="803a4-124">Verify and start Windows PowerShell</span></span>

- <span data-ttu-id="803a4-125">**Windows PowerShell 버전 3.0 이상을 실행 하 고 있는지 확인**</span><span class="sxs-lookup"><span data-stu-id="803a4-125">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
    
1. <span data-ttu-id="803a4-126">버전 3.0 이상을 실행 하 고 있는지 확인 하려면 **시작 메뉴**에서  >  **Windows PowerShell**을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="803a4-126">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="803a4-127">**Windows PowerShell** 창에서 _Get-Host_ 를 입력 하 여 버전을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="803a4-127">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="803a4-128">버전 3.0 이상이 없는 경우 Windows PowerShell 업데이트를 다운로드 하 여 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="803a4-128">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell.</span></span> <span data-ttu-id="803a4-129">Windows [Management 프레임 워크 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) 를 참조 하 여 windows PowerShell을 버전 4.0로 다운로드 하 고 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="803a4-129">See [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0.</span></span> <span data-ttu-id="803a4-130">메시지가 표시 되 면 컴퓨터를 다시 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="803a4-130">Restart your computer when you are prompted.</span></span>
    
4. <span data-ttu-id="803a4-131">비즈니스용 skype Online에 연결 되는 원격 Windows PowerShell 세션을 만들 수 있는 비즈니스용 Skype Online 용 Windows PowerShell 모듈을 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="803a4-131">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span> <span data-ttu-id="803a4-132">이 모듈은 64 비트 컴퓨터 에서만 지원 되며 비즈니스용 [Skype Online 용 Windows PowerShell 모듈](https://go.microsoft.com/fwlink/?LinkId=294688)의 Microsoft 다운로드 센터에서 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="803a4-132">This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688).</span></span> <span data-ttu-id="803a4-133">메시지가 표시 되 면 컴퓨터를 다시 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="803a4-133">Restart your computer if you are prompted.</span></span>
    
    <span data-ttu-id="803a4-134">자세한 정보를 알고 싶은 경우에 [는 단일 Windows PowerShell 창에서 모든 Microsoft 365 또는 Office 365 서비스에 연결](https://technet.microsoft.com/library/dn568015.aspx)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="803a4-134">If you need to know more, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx).</span></span>
    
- <span data-ttu-id="803a4-135">**Windows PowerShell 세션 시작**</span><span class="sxs-lookup"><span data-stu-id="803a4-135">**Start a Windows PowerShell session**</span></span>
    
1. <span data-ttu-id="803a4-136">**시작 메뉴**에서  >  **Windows PowerShell**을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="803a4-136">From the **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="803a4-137">**Windows PowerShell** 창에서 다음을 실행 하 여 Microsoft 365 또는 Office 365에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="803a4-137">In the **Windows PowerShell** window, connect to your Microsoft 365 or Office 365 by running:</span></span>
    
   > [!NOTE]
   > <span data-ttu-id="803a4-138">비즈니스용 Skype Online Windows PowerShell 모듈을 처음 사용 하는 경우에만 **Import-Module** 명령을 실행 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="803a4-138">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>
   > 
   ```PowerShell
    Import-Module -Name SkypeOnlineConnector
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
   ```

<span data-ttu-id="803a4-139">Windows PowerShell을 시작 하는 방법에 대 한 자세한 내용은 [단일 Windows powershell 창에서 모든 Microsoft 365 또는 Office 365 서비스에 연결](https://technet.microsoft.com/library/dn568015.aspx) 또는 [windows Powershell 용 컴퓨터 설정을](/skypeforbusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="803a4-139">If you want more information about starting Windows PowerShell, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx) or [Set up your computer for Windows PowerShell](/skypeforbusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>
    
### <a name="see-all-of-the-caller-id-policy-settings-in-your-organization"></a><span data-ttu-id="803a4-140">조직의 모든 발신자 ID 정책 설정 보기</span><span class="sxs-lookup"><span data-stu-id="803a4-140">See all of the caller ID policy settings in your organization</span></span>

- <span data-ttu-id="803a4-141">조직의 모든 발신자 ID 정책 설정을 보려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="803a4-141">To view all of the caller ID policy settings in your organization, run:</span></span>

  ```PowerShell
  Get-CsCallingLineIdentity |fl
  ```
  <span data-ttu-id="803a4-142">[CsCallingLineIdentity](https://technet.microsoft.com/library/mt793856.aspx)에 대 한 추가 예제 및 세부 정보를 확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="803a4-142">See more examples and details for [Get-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793856.aspx).</span></span>
    
### <a name="create-a-new-caller-id-policy-for-your-organization"></a><span data-ttu-id="803a4-143">조직에 대 한 새 발신자 ID 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="803a4-143">Create a new caller ID policy for your organization</span></span>


- <span data-ttu-id="803a4-144">발신자 ID를 익명으로 설정 하는 새 발신자 ID 정책을 만들려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="803a4-144">To create a new caller ID policy that sets the caller ID to anonymous, run:</span></span>
    
  ```PowerShell
  New-CsCallingLineIdentity  -Identity Anonymous -Description "Anonymous policy" -CallingIDSubstitute Anonymous -EnableUserOverride $false
  ```
  > [!NOTE]  
  > <span data-ttu-id="803a4-145">모든 경우에 "서비스 번호" 필드에는 초기 "+"가 포함 되어서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="803a4-145">In all cases, the "Service Number" field should not include an initial "+".</span></span>

  <span data-ttu-id="803a4-146">[새로운 CsCallingLineIdentity](https://technet.microsoft.com/library/mt793855.aspx)에 대 한 추가 예제 및 세부 정보를 확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="803a4-146">See more examples and details for [New-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793855.aspx).</span></span>
    
- <span data-ttu-id="803a4-147">만든 새 정책을 Amos 대리석에 적용 하려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="803a4-147">To apply the new policy you created to Amos Marble, run:</span></span>
    
  ```PowerShell
   Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName Anonymous
  ```
  <span data-ttu-id="803a4-148">[CsCallingLineIdentity](https://technet.microsoft.com/library/mt793857.aspx) cmdlet에 대 한 자세한 내용을 확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="803a4-148">See more on the [Grant-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793857.aspx) cmdlet.</span></span>
    
<span data-ttu-id="803a4-149">이미 정책을 만든 경우 [CsCallingLineIdentity](https://technet.microsoft.com/library/mt793854.aspx) cmdlet을 사용 하 여 기존 정책을 변경한 다음 [부여-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793857.aspx) cmdlet을 사용 하 여 사용자에 게 설정을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="803a4-149">If you have already created a policy, you can use the [Set-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793854.aspx) cmdlet to make changes to the existing policy, and then use the [Grant-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793857.aspx) cmdlet to apply the settings to your users.</span></span>
  
### <a name="set-it-so-the-incoming-caller-id-is-blocked"></a><span data-ttu-id="803a4-150">들어오는 발신자 ID가 차단 되도록 설정</span><span class="sxs-lookup"><span data-stu-id="803a4-150">Set it so the incoming caller ID is blocked</span></span>

- <span data-ttu-id="803a4-151">들어오는 발신자 ID를 차단 하려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="803a4-151">To block the incoming caller ID, run:</span></span>
    
  ```PowerShell
  Set-CsCallingLineIdentity  -Identity "Block Incoming" -BlockIncomingPstnCallerID $true -EnableUserOverride $true
  ```
  <span data-ttu-id="803a4-152">[CsCallingLineIdentity](https://technet.microsoft.com/library/mt793854.aspx)에 대 한 추가 예제 및 세부 정보를 확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="803a4-152">See more examples and details for [Set-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793854.aspx).</span></span>
    
- <span data-ttu-id="803a4-153">조직의 사용자에 게 만든 정책 설정을 적용 하려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="803a4-153">To apply the policy setting you created to a user in your organization, run:</span></span>
    
  ```PowerShell
  Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName "Block Incoming"
  ```
    <span data-ttu-id="803a4-154">[CsCallingLineIdentity](https://technet.microsoft.com/library/mt793857.aspx) cmdlet에 대 한 자세한 내용을 확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="803a4-154">See more on the [Grant-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793857.aspx) cmdlet.</span></span>
    
### <a name="remove-a-caller-id-policy"></a><span data-ttu-id="803a4-155">발신자 ID 정책 제거</span><span class="sxs-lookup"><span data-stu-id="803a4-155">Remove a caller ID policy</span></span>

<span data-ttu-id="803a4-156">조직에서 정책을 제거 하려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="803a4-156">To remove a policy from your organization, run:</span></span>
  
```PowerShell
Remove-CsCallingLineIdentity -Identity "My Caller ID Policy"
```
<span data-ttu-id="803a4-157">사용자에서 정책을 제거 하려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="803a4-157">To remove a policy from a user, run:</span></span>
  
```PowerShell
Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName $null
```
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="803a4-158">Windows PowerShell에 대 한 자세한 정보를 확인 하 고 싶으신가요?</span><span class="sxs-lookup"><span data-stu-id="803a4-158">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="803a4-159">Windows PowerShell은 사용자 및 허용 되지 않거나 수행할 수 있는 사용자를 관리 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="803a4-159">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="803a4-160">Windows PowerShell을 사용 하면 여러 작업을 수행할 때 일상 업무를 단순화할 수 있는 단일 관리 지점을 사용 하 여 Microsoft 365 또는 Office 365 및 비즈니스용 Skype Online을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="803a4-160">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="803a4-161">Windows PowerShell을 시작 하려면 다음 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="803a4-161">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="803a4-162">Windows PowerShell 및 Lync Online 소개</span><span class="sxs-lookup"><span data-stu-id="803a4-162">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="803a4-163">Windows PowerShell을 사용 하 여 Microsoft 365 또는 Office 365을 관리 해야 하는 여섯 가지 이유</span><span class="sxs-lookup"><span data-stu-id="803a4-163">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Microsoft 365 or Office 365</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="803a4-164">Windows PowerShell에는 한 번에 여러 사용자의 설정을 변경 하는 경우와 같이 Microsoft 365 관리 센터를 사용 하는 경우에만 속도, 단순성, 생산성 등 다양 한 이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="803a4-164">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="803a4-165">다음 항목에서 이러한 이점에 대해 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="803a4-165">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="803a4-166">Windows PowerShell을 사용 하 여 Microsoft 365 또는 Office 365을 관리 하는 최상의 방법</span><span class="sxs-lookup"><span data-stu-id="803a4-166">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="803a4-167">Windows PowerShell을 사용 하 여 비즈니스용 Skype Online 관리</span><span class="sxs-lookup"><span data-stu-id="803a4-167">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="803a4-168">Windows PowerShell을 사용 하 여 일반적인 비즈니스용 Skype Online 관리 작업 수행</span><span class="sxs-lookup"><span data-stu-id="803a4-168">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
  
 ## <a name="related-topics"></a><span data-ttu-id="803a4-169">관련 항목</span><span class="sxs-lookup"><span data-stu-id="803a4-169">Related topics</span></span>
[<span data-ttu-id="803a4-170">전화 번호 전송 자주 묻는 질문</span><span class="sxs-lookup"><span data-stu-id="803a4-170">Transferring phone numbers common questions</span></span>](/microsoftteams/transferring-phone-numbers-common-questions)

[<span data-ttu-id="803a4-171">통화 요금제에 사용 되는 다른 종류의 전화 번호</span><span class="sxs-lookup"><span data-stu-id="803a4-171">Different kinds of phone numbers used for Calling Plans</span></span>](/microsoftteams/different-kinds-of-phone-numbers-used-for-calling-plans)

[<span data-ttu-id="803a4-172">조직의 전화 번호 관리</span><span class="sxs-lookup"><span data-stu-id="803a4-172">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="803a4-173">전화 회선 ID 및 발신자 이름에 대한 자세한 정보</span><span class="sxs-lookup"><span data-stu-id="803a4-173">More about Calling Line ID and Calling Party Name</span></span>](/skypeforbusiness/what-are-calling-plans-in-office-365/more-about-calling-line-ID-and-calling-party-name)

[<span data-ttu-id="803a4-174">긴급 통화 사용 약관</span><span class="sxs-lookup"><span data-stu-id="803a4-174">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)

<span data-ttu-id="803a4-175">[비즈니스용 Skype Online: 비상 전화 부인 레이블](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="803a4-175">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>
 
