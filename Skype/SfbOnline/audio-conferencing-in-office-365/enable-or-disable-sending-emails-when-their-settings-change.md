---
title: 비즈니스용 Skype Online에서 오디오 회의 설정이 변경될 때 전자 메일 보내기 사용 또는 비활성화
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 26ea19d3-e420-4fc1-baa3-2692d17e5e1d
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
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: '고정 변경 또는 기본 회의 번호와 같은 설정이 변경될 때 사용자에게 전자 메일을 보내는 Skype를 사용하도록 설정하거나 사용하지 않도록 설정하는 방법에 대해 자세히 알아보습니다. '
ms.openlocfilehash: 6b9e67d8c87b023409b7934a944f298487f91289
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51114254"
---
# <a name="enable-or-disable-sending-emails-when-audio-conferencing-settings-change-in-skype-for-business-online"></a><span data-ttu-id="9c4ee-103">비즈니스용 Skype Online에서 오디오 회의 설정이 변경될 때 전자 메일 보내기 사용 또는 비활성화</span><span class="sxs-lookup"><span data-stu-id="9c4ee-103">Enable or disable sending emails when Audio Conferencing settings change in Skype for Business Online</span></span>

> [!Note]
> <span data-ttu-id="9c4ee-104">Microsoft Teams에서 전자 메일 전송을 사용하도록 설정하거나 사용하지 않도록 설정하려면 Microsoft Teams에서 오디오 회의 설정이 변경될 때 전자 메일 보내기 사용 또는 사용 안 을 [참조하세요.](/MicrosoftTeams/enable-or-disable-sending-emails-when-their-settings-change-in-teams)</span><span class="sxs-lookup"><span data-stu-id="9c4ee-104">If you want to enable or disable sending emails in Microsoft Teams, see [Enable or disable sending emails when Audio Conferencing settings change in Microsoft Teams](/MicrosoftTeams/enable-or-disable-sending-emails-when-their-settings-change-in-teams).</span></span>

<span data-ttu-id="9c4ee-105">오디오 회의를 사용하도록 설정하면 사용자에게 전자 메일로 자동으로 알림이 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="9c4ee-105">Users are automatically notified by email when they are enabled for Audio Conferencing.</span></span> <span data-ttu-id="9c4ee-106">그러나 비즈니스용 Skype 사용자에게 전송되는 전자 메일의 수를 줄이지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c4ee-106">There may be times, however, when you want to reduce the number of emails that are sent to Skype for Business users.</span></span> <span data-ttu-id="9c4ee-107">이러한 경우 전자 메일 보내기 기능을 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c4ee-107">In such cases, you can disable sending email.</span></span>
  
<span data-ttu-id="9c4ee-108">전자 메일 보내기 기능을 사용하지 않도록 설정하면 사용자가 오디오 회의를 사용하도록 설정하거나 사용하지 않도록 설정한 경우, PIN이 재설정되는 경우 및 회의 ID 및 기본 회의 전화 번호가 변경될 때 전자 메일을 포함하여 오디오 회의 전자 메일이 사용자에게 전송되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9c4ee-108">If you disable sending emails, Audio Conferencing emails won't be sent to your users, including emails for when users are enabled or disabled for audio conferencing, when their PIN is reset, and when the conference ID and the default conferencing phone number changes.</span></span>
  
<span data-ttu-id="9c4ee-109">다음은 오디오 회의를 사용하도록 설정하면 사용자에게 전송된 전자 메일의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="9c4ee-109">Here is an example of the email that is sent to users when they are enabled for Audio Conferencing:</span></span>
  
![오디오 회의 전자 메일](../images/audio-conferencing-user-enabled.png)
  
## <a name="when-are-emails-being-sent-to-your-users"></a><span data-ttu-id="9c4ee-111">사용자에게 전자 메일은 언제 전송하나요?</span><span class="sxs-lookup"><span data-stu-id="9c4ee-111">When are emails being sent to your users?</span></span>

- <span data-ttu-id="9c4ee-112">오디오 회의를 사용하도록 설정한 후 조직의 사용자에게 전송된 여러 전자 메일이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c4ee-112">There are several emails that are sent to users in your organization after they are enabled for audio conferencing:</span></span>
    
  - <span data-ttu-id="9c4ee-113">오디오 **회의** 라이선스가 할당되는 경우.</span><span class="sxs-lookup"><span data-stu-id="9c4ee-113">When an **Audio Conferencing** license is assigned to them.</span></span>
    
  - <span data-ttu-id="9c4ee-114">사용자의 오디오 회의 PIN을 수동으로 다시 설정하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9c4ee-114">When you manually reset the user's audio conferencing PIN.</span></span>
    
  - <span data-ttu-id="9c4ee-115">사용자의 회의 ID를 수동으로 다시 설정하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9c4ee-115">When you manually reset the user's conference ID.</span></span>
    
  - <span data-ttu-id="9c4ee-116">오디오 **회의** 라이선스가 해당 라이선스에서 제거되면</span><span class="sxs-lookup"><span data-stu-id="9c4ee-116">When the **Audio Conferencing** license is removed from them.</span></span>
    
  - <span data-ttu-id="9c4ee-117">사용자의 오디오 회의 공급자가 Microsoft에서 다른 공급자 또는 **없음으로** 변경된 경우</span><span class="sxs-lookup"><span data-stu-id="9c4ee-117">When the audio conferencing provider of a user is changed from Microsoft to another provider or **None**.</span></span>
    
  - <span data-ttu-id="9c4ee-118">사용자의 오디오 회의 공급자가 Microsoft로 변경된 경우</span><span class="sxs-lookup"><span data-stu-id="9c4ee-118">When the audio conferencing provider of a user is changed to Microsoft.</span></span>


## <a name="enable-or-disable-email-from-being-sent-to-users"></a><span data-ttu-id="9c4ee-119">사용자에게 전자 메일이 전송되지 않도록 설정하거나 사용하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="9c4ee-119">Enable or disable email from being sent to users</span></span>

<span data-ttu-id="9c4ee-120">비즈니스용 Skype 관리 센터 또는 Windows PowerShell 사용자에게 보낸 전자 메일을 사용하도록 설정하거나 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c4ee-120">You can use the Skype for Business admin center or Windows PowerShell to enable or disable email sent to users.</span></span>

 
<span data-ttu-id="9c4ee-121">![비즈니스용 skype 로고를 나타내는 아이콘](../images/sfb-logo-30x30.png) **비즈니스용 Skype 관리 센터 사용**</span><span class="sxs-lookup"><span data-stu-id="9c4ee-121">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>
    
1. <span data-ttu-id="9c4ee-122">비즈니스용 Skype 관리 **센터의** 왼쪽 탐색에서 오디오 회의 **를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="9c4ee-122">In the **Skype for Business admin center**, in the left navigation, click **Audio conferencing**.</span></span>
    
2. <span data-ttu-id="9c4ee-123">Microsoft **브리지 설정 페이지에서** 오디오 회의 설정이 변경될 경우 사용자에게 자동으로 전자 메일 보내기 를 선택하거나 선택 **취소합니다.**</span><span class="sxs-lookup"><span data-stu-id="9c4ee-123">On the **Microsoft bridge settings** page, select or clear the **Automatically send emails to users if their audio conferencing settings change**.</span></span>
    
3. <span data-ttu-id="9c4ee-124">**저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9c4ee-124">Click **Save**.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="9c4ee-125">오디오 회의 사용자로 이동하고 사용자를 선택하고 전자 메일을 통해 회의 정보 보내기 를 클릭하여 오디오 회의 설정을 사용하여 사용자에게 전자 메일을  >  보낼 **수도 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="9c4ee-125">You can also send email to a user with the audio conferencing settings by going to **Audio conferencing** > **Users**, selecting the user, and clicking **Send conference info via email**.</span></span>  <span data-ttu-id="9c4ee-126">이렇게 하면 전화 회의 ID 및 전화 회의 전화 번호만 포함하지만 PIN이 아닌 전자 메일이 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="9c4ee-126">If you do this, an email will be sent that only includes conference ID and conference phone number, but not the PIN.</span></span>  <span data-ttu-id="9c4ee-127">자세한 [내용은](send-an-email-to-a-user-with-their-dial-in-information.md) 오디오 회의 정보를 통해 사용자에게 전자 메일 보내기 를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9c4ee-127">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md) for more information.</span></span>
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

<span data-ttu-id="9c4ee-128">**Using Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="9c4ee-128">**Using Windows PowerShell**</span></span>
  
- <span data-ttu-id="9c4ee-129">다음을 실행하여 전자 메일 전송을 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="9c4ee-129">Run the following to disable sending emails:</span></span> 
    
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSetting -AutomaticallySendEmailsToUsers $false
  ```

    <span data-ttu-id="9c4ee-130">이 cmdlet에 대한 도움말은 [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/Set-CsOnlineDialInConferencingTenantSettings)를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="9c4ee-130">For help with this cmdlet, see [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/Set-CsOnlineDialInConferencingTenantSettings).</span></span>
    
## <a name="what-else-should-you-know"></a><span data-ttu-id="9c4ee-131">또 어떤 것을 알아야 하나요?</span><span class="sxs-lookup"><span data-stu-id="9c4ee-131">What else should you know?</span></span>

- <span data-ttu-id="9c4ee-132">자동 전자 메일을 사용하지 않도록 설정하면 비즈니스용 Skype 관리 센터를 사용하여 전화 회의 ID 및 전화 번호로 전자 메일 보내기를 수동으로 트리거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c4ee-132">When automatic emails are disabled, you can still manually trigger sending an email with the conference ID and phone number using the Skype for Business admin center.</span></span> <span data-ttu-id="9c4ee-133">그러나 이렇게 하는 경우 PIN은 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9c4ee-133">However, if you do this, the PIN won't be included.</span></span> <span data-ttu-id="9c4ee-134">오디오 회의 PIN을 다시 설정하고 전자 메일을 보내지 않도록 설정하려는 경우 다른 방법으로 사용자에게 보내야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c4ee-134">If you want to reset the audio conferencing PIN and sending emails is disabled, you will need to send it to the user in another way.</span></span>
    
- <span data-ttu-id="9c4ee-135">비즈니스용 Skype 관리 센터 또는 사용자 센터를 사용하여 사용자에게 전자 메일을 보내지 않도록 설정할 Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9c4ee-135">Sending email to your users can be disabled using the Skype for Business admin center or the Windows PowerShell.</span></span>
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="9c4ee-136">사용자와 함께 관리하는 방법을 알고 Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9c4ee-136">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="9c4ee-137">이러한 cmdlet을 사용하여 시간을 절약하거나 자동화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c4ee-137">You can use these cmdlets to save time or automate this.</span></span>
    
  - [<span data-ttu-id="9c4ee-138">Get-CsOnlineDialInConferencingTenantSettings</span><span class="sxs-lookup"><span data-stu-id="9c4ee-138">Get-CsOnlineDialInConferencingTenantSettings</span></span>](/powershell/module/skype/Get-CsOnlineDialInConferencingTenantSettings)
    
  - [<span data-ttu-id="9c4ee-139">Remove-CsOnlineDialInConferencingTenantSettings</span><span class="sxs-lookup"><span data-stu-id="9c4ee-139">Remove-CsOnlineDialInConferencingTenantSettings</span></span>](/powershell/module/skype/Remove-CsOnlineDialInConferencingTenantSettings)
    
  - [<span data-ttu-id="9c4ee-140">Get-CsOnlineDialinConferencingTenantConfiguration</span><span class="sxs-lookup"><span data-stu-id="9c4ee-140">Get-CsOnlineDialinConferencingTenantConfiguration</span></span>](/powershell/module/skype/Get-CsOnlineDialinConferencingTenantConfiguration)
    
  - [<span data-ttu-id="9c4ee-141">Get-CsOnlineDialInConferencingTenantSettings</span><span class="sxs-lookup"><span data-stu-id="9c4ee-141">Get-CsOnlineDialInConferencingTenantSettings</span></span>](/powershell/module/skype/Get-CsOnlineDialInConferencingTenantSettings)
    
- <span data-ttu-id="9c4ee-142">Windows PowerShell 모든 것은 사용자 관리와 사용자가 허용되거나 허용되지 않는 작업을 관리하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="9c4ee-142">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="9c4ee-143">이 Windows PowerShell 여러 작업을 수행할 때 일상적인 작업을 단순화할 수 있는 단일 관리 지점을 사용하여 Microsoft 365 또는 Office 365를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c4ee-143">With Windows PowerShell, you can manage Microsoft 365 or Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="9c4ee-144">다음 항목을 Windows PowerShell 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9c4ee-144">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="9c4ee-145">Microsoft 365 또는 Office 365 PowerShell을 사용해야 하는 이유</span><span class="sxs-lookup"><span data-stu-id="9c4ee-145">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - <span data-ttu-id="9c4ee-146">[Microsoft 365 또는 Office 365를 관리하는 가장 좋은 Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="9c4ee-146">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
- <span data-ttu-id="9c4ee-147">Windows PowerShell 많은 사용자에 대해 한 번씩 설정을 변경하는 경우와 같이 Microsoft 365 관리 센터를 사용하는 경우와 같이 속도, 단순성 및 생산성에 많은 이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c4ee-147">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center, such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="9c4ee-148">다음 항목에서 이러한 이점에 대해 자세히 알아보습니다.</span><span class="sxs-lookup"><span data-stu-id="9c4ee-148">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="9c4ee-149">Windows PowerShell 및 비즈니스용 Skype Online 소개</span><span class="sxs-lookup"><span data-stu-id="9c4ee-149">An introduction to Windows PowerShell and Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="9c4ee-150">비즈니스용 skype Windows PowerShell 관리하기 위해 사용</span><span class="sxs-lookup"><span data-stu-id="9c4ee-150">Using Windows PowerShell to manage Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="9c4ee-151">비즈니스용 Windows PowerShell Skype 온라인 관리 작업을 수행하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c4ee-151">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    > [!NOTE]
    > <span data-ttu-id="9c4ee-152">비즈니스용 skype Windows PowerShell 모듈을 사용하면 비즈니스용 Skype Online에 Windows PowerShell 원격 세션을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c4ee-152">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span> <span data-ttu-id="9c4ee-153">64비트 컴퓨터에서만 지원되는 이 모듈은 비즈니스용 Skype 온라인용 Windows PowerShell Microsoft 다운로드 센터에서 다운로드할 [수 있습니다.](https://go.microsoft.com/fwlink/?LinkId=294688)</span><span class="sxs-lookup"><span data-stu-id="9c4ee-153">This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="9c4ee-154">관련 항목</span><span class="sxs-lookup"><span data-stu-id="9c4ee-154">Related topics</span></span>

[<span data-ttu-id="9c4ee-155">오디오 회의 설정이 변경될 때 사용자에게 전송된 전자 메일</span><span class="sxs-lookup"><span data-stu-id="9c4ee-155">Emails sent to users when their Audio Conferencing settings change</span></span>](emails-sent-to-users-when-their-settings-change.md)

[<span data-ttu-id="9c4ee-156">오디오 회의 정보를 사용하여 사용자에게 전자 메일 보내기</span><span class="sxs-lookup"><span data-stu-id="9c4ee-156">Send an email to a user with their Audio Conferencing information</span></span>](send-an-email-to-a-user-with-their-dial-in-information.md)