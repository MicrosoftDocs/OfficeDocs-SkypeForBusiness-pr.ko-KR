---
title: 비즈니스용 Skype Online에서 오디오 회의 설정이 변경 될 때 전자 메일 보내기 사용 또는 사용 안 함
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
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Pin 변경 또는 기본 회의 번호 변경 등의 설정이 사용자에 게 전자 메일을 보내는 것을 허용 하거나 해제 하는 방법에 대해 알아봅니다. '
ms.openlocfilehash: d4947012e98c45e108a2cc8d9f84bb4f16a24d3c
ms.sourcegitcommit: afc7edd03f4baa1d75f9642d4dbce767fec69b00
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/07/2020
ms.locfileid: "40962716"
---
# <a name="enable-or-disable-sending-emails-when-audio-conferencing-settings-change-in-skype-for-business-online"></a><span data-ttu-id="344ae-103">비즈니스용 Skype Online에서 오디오 회의 설정이 변경 될 때 전자 메일 보내기 사용 또는 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="344ae-103">Enable or disable sending emails when Audio Conferencing settings change in Skype for Business Online</span></span>

> [!Note]
> <span data-ttu-id="344ae-104">Microsoft 팀에서 전자 메일 보내기를 사용 하거나 사용 하지 않도록 설정 하려면 [Microsoft 팀에서 오디오 회의 설정이 변경 될 때 전자 메일 보내기 사용 또는 사용 안 함을](/MicrosoftTeams/enable-or-disable-sending-emails-when-their-settings-change-in-teams)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="344ae-104">If you want to enable or disable sending emails in Microsoft Teams, see [Enable or disable sending emails when Audio Conferencing settings change in Microsoft Teams](/MicrosoftTeams/enable-or-disable-sending-emails-when-their-settings-change-in-teams).</span></span>

<span data-ttu-id="344ae-105">사용자가 오디오 회의를 사용 하도록 설정 되 면 전자 메일을 통해 자동으로 알림을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="344ae-105">Users are automatically notified by email when they are enabled for Audio Conferencing.</span></span> <span data-ttu-id="344ae-106">그러나 비즈니스용 Skype 사용자에 게 전송 되는 전자 메일 수를 줄여야 하는 경우가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="344ae-106">There may be times, however, when you want to reduce the number of emails that are sent to Skype for Business users.</span></span> <span data-ttu-id="344ae-107">이러한 경우 전자 메일 보내기를 사용 하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="344ae-107">In such cases, you can disable sending email.</span></span>
  
<span data-ttu-id="344ae-108">전자 메일 보내기를 사용 하지 않도록 설정 하는 경우 오디오 회의를 사용 하거나 사용 하지 않도록 설정 하는 경우, PIN이 다시 설정 될 때, 전화 회의 ID 및 기본 회의 전화 번호가 변경 되는 경우의 전자 메일을 포함 하 여 사용자에 게 오디오 회의 전자 메일이 전송 되지 않습니다. .</span><span class="sxs-lookup"><span data-stu-id="344ae-108">If you disable sending emails, Audio Conferencing emails won't be sent to your users, including emails for when users are enabled or disabled for audio conferencing, when their PIN is reset, and when the conference ID and the default conferencing phone number changes.</span></span>
  
<span data-ttu-id="344ae-109">다음은 오디오 회의를 사용 하도록 설정 했을 때 사용자에 게 전송 되는 전자 메일의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="344ae-109">Here is an example of the email that is sent to users when they are enabled for Audio Conferencing:</span></span>
  
![오디오 회의 전자 메일](../images/audio-conferencing-user-enabled.png)
  
## <a name="when-are-emails-being-sent-to-your-users"></a><span data-ttu-id="344ae-111">사용자에 게 전자 메일이 전송 되는 경우</span><span class="sxs-lookup"><span data-stu-id="344ae-111">When are emails being sent to your users?</span></span>

- <span data-ttu-id="344ae-112">오디오 회의를 사용 하도록 설정 하면 조직의 사용자에 게 여러 개의 전자 메일이 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="344ae-112">There are several emails that are sent to users in your organization after they are enabled for audio conferencing:</span></span>
    
  - <span data-ttu-id="344ae-113">**오디오 회의** 라이선스가 할당 된 경우</span><span class="sxs-lookup"><span data-stu-id="344ae-113">When an **Audio Conferencing** license is assigned to them.</span></span>
    
  - <span data-ttu-id="344ae-114">사용자의 오디오 회의 PIN을 수동으로 다시 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="344ae-114">When you manually reset the user's audio conferencing PIN.</span></span>
    
  - <span data-ttu-id="344ae-115">수동으로 사용자의 전화 회의 ID를 다시 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="344ae-115">When you manually reset the user's conference ID.</span></span>
    
  - <span data-ttu-id="344ae-116">**오디오 회의** 라이선스가 해당 항목에서 제거 됩니다.</span><span class="sxs-lookup"><span data-stu-id="344ae-116">When the **Audio Conferencing** license is removed from them.</span></span>
    
  - <span data-ttu-id="344ae-117">사용자의 오디오 회의 공급자가 Microsoft에서 다른 공급자 또는 **없음**으로 변경 되는 경우</span><span class="sxs-lookup"><span data-stu-id="344ae-117">When the audio conferencing provider of a user is changed from Microsoft to another provider or **None**.</span></span>
    
  - <span data-ttu-id="344ae-118">사용자의 오디오 회의 공급자가 Microsoft로 변경 된 경우</span><span class="sxs-lookup"><span data-stu-id="344ae-118">When the audio conferencing provider of a user is changed to Microsoft.</span></span>


## <a name="enable-or-disable-email-from-being-sent-to-users"></a><span data-ttu-id="344ae-119">사용자에 게 전자 메일을 보낼 수 있도록 설정 또는 해제</span><span class="sxs-lookup"><span data-stu-id="344ae-119">Enable or disable email from being sent to users</span></span>

<span data-ttu-id="344ae-120">비즈니스용 Skype 관리 센터 또는 Windows PowerShell을 사용 하 여 사용자에 게 전송 되는 전자 메일을 사용 하거나 사용 하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="344ae-120">You can use the Skype for Business admin center or Windows PowerShell to enable or disable email sent to users.</span></span>

 
<span data-ttu-id="344ae-121">![비즈니스용 skype](../images/sfb-logo-30x30.png) **관리 센터를 사용 하 여** 비즈니스용 skype 로고를 표시 하는 아이콘</span><span class="sxs-lookup"><span data-stu-id="344ae-121">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>
    
1. <span data-ttu-id="344ae-122">**비즈니스용 Skype 관리 센터**의 왼쪽 탐색 창에서 **오디오 회의**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="344ae-122">In the **Skype for Business admin center**, in the left navigation, click **Audio conferencing**.</span></span>
    
2. <span data-ttu-id="344ae-123">**Microsoft 브리지 설정** 페이지에서 **오디오 회의 설정이 변경 된 경우 사용자에 게 자동으로 전자 메일 보내기**를 선택 하거나 선택을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="344ae-123">On the **Microsoft bridge settings** page, select or clear the **Automatically send emails to users if their audio conferencing settings change**.</span></span>
    
3. <span data-ttu-id="344ae-124">**저장**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="344ae-124">Click **Save**.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="344ae-125">**오디오 회의** > **사용자**로 이동한 다음 사용자를 선택 하 고 **전자 메일을 통해 회의 정보 보내기를**클릭 하 여 오디오 회의 설정을 사용 하 여 사용자에 게 전자 메일을 보낼 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="344ae-125">You can also send email to a user with the audio conferencing settings by going to **Audio conferencing** > **Users**, selecting the user, and clicking **Send conference info via email**.</span></span>  <span data-ttu-id="344ae-126">이렇게 하면 PIN이 아닌 전화 회의 ID 및 전화 번호만 포함 된 전자 메일이 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="344ae-126">If you do this, an email will be sent that only includes conference ID and conference phone number, but not the PIN.</span></span>  <span data-ttu-id="344ae-127">자세한 내용은 [오디오 회의 정보를 사용 하 여 사용자에 게 전자 메일 보내기를](send-an-email-to-a-user-with-their-dial-in-information.md) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="344ae-127">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md) for more information.</span></span>
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

<span data-ttu-id="344ae-128">**Windows PowerShell 사용**</span><span class="sxs-lookup"><span data-stu-id="344ae-128">**Using Windows PowerShell**</span></span>
  
- <span data-ttu-id="344ae-129">전자 메일 보내기를 사용 하지 않으려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="344ae-129">Run the following to disable sending emails:</span></span> 
    
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSetting -AutomaticallySendEmailsToUsers $false
  ```

    <span data-ttu-id="344ae-130">이 cmdlet에 대 한 도움말은 [Set-사용](https://go.microsoft.com/fwlink/?LinkId=715757)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="344ae-130">For help with this cmdlet, see [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757).</span></span>
    
## <a name="what-else-should-you-know"></a><span data-ttu-id="344ae-131">알아야 할 기타 사항</span><span class="sxs-lookup"><span data-stu-id="344ae-131">What else should you know?</span></span>

- <span data-ttu-id="344ae-132">자동 전자 메일을 사용 하지 않도록 설정한 경우 비즈니스용 Skype 관리 센터를 사용 하 여 전화 회의 ID 및 전화번호를 포함 하는 전자 메일을 수동으로 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="344ae-132">When automatic emails are disabled, you can still manually trigger sending an email with the conference ID and phone number using the Skype for Business admin center.</span></span> <span data-ttu-id="344ae-133">그러나이 작업을 수행 하는 경우에는 PIN이 포함 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="344ae-133">However, if you do this, the PIN won't be included.</span></span> <span data-ttu-id="344ae-134">오디오 회의 PIN을 다시 설정 하 고 전자 메일을 보낼 수 없도록 설정 하려면 다른 방식으로 사용자에 게 보내야 합니다.</span><span class="sxs-lookup"><span data-stu-id="344ae-134">If you want to reset the audio conferencing PIN and sending emails is disabled, you will need to send it to the user in another way.</span></span>
    
- <span data-ttu-id="344ae-135">비즈니스용 Skype 관리 센터 또는 Windows PowerShell을 사용 하 여 사용자에 게 전자 메일을 보낼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="344ae-135">Sending email to your users can be disabled using the Skype for Business admin center or the Windows PowerShell.</span></span>
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="344ae-136">Windows PowerShell을 사용 하 여 관리 하는 방법을 알고 싶으세요?</span><span class="sxs-lookup"><span data-stu-id="344ae-136">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="344ae-137">이러한 cmdlet을 사용 하 여 시간을 절약 하거나이를 자동화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="344ae-137">You can use these cmdlets to save time or automate this.</span></span>
    
  - [<span data-ttu-id="344ae-138">Get-사용</span><span class="sxs-lookup"><span data-stu-id="344ae-138">Get-CsOnlineDialInConferencingTenantSettings</span></span>](https://go.microsoft.com/fwlink/?LinkId=715760)
    
  - [<span data-ttu-id="344ae-139">제거-사용</span><span class="sxs-lookup"><span data-stu-id="344ae-139">Remove-CsOnlineDialInConferencingTenantSettings</span></span>](https://go.microsoft.com/fwlink/?LinkId=715759)
    
  - [<span data-ttu-id="344ae-140">Get-CsOnlineDialinConferencingTenantConfiguration</span><span class="sxs-lookup"><span data-stu-id="344ae-140">Get-CsOnlineDialinConferencingTenantConfiguration</span></span>](https://go.microsoft.com/fwlink/?LinkId=715758)
    
  - [<span data-ttu-id="344ae-141">Get-사용</span><span class="sxs-lookup"><span data-stu-id="344ae-141">Get-CsOnlineDialInConferencingTenantSettings</span></span>](https://go.microsoft.com/fwlink/?LinkId=715760)
    
- <span data-ttu-id="344ae-142">Windows PowerShell은 사용자 및 허용 되지 않거나 수행할 수 있는 사용자를 관리 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="344ae-142">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="344ae-143">Windows PowerShell을 사용 하면 여러 작업을 수행할 때 일상 업무를 단순화할 수 있는 단일 관리 지점을 사용 하 여 Office 365를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="344ae-143">With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="344ae-144">Windows PowerShell을 시작 하려면 다음 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="344ae-144">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="344ae-145">Office 365 PowerShell을 사용 해야 하는 이유</span><span class="sxs-lookup"><span data-stu-id="344ae-145">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="344ae-146">Windows PowerShell을 사용 하 여 Office 365를 관리 하는 가장 좋은 방법</span><span class="sxs-lookup"><span data-stu-id="344ae-146">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="344ae-147">Windows PowerShell에는 한 번에 여러 사용자의 설정을 변경 하는 경우와 같이 Microsoft 365 관리 센터를 사용 하는 경우에만 속도, 단순성, 생산성 등 다양 한 이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="344ae-147">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center, such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="344ae-148">다음 항목에서 이러한 이점에 대해 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="344ae-148">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="344ae-149">Windows PowerShell 및 Lync Online 소개</span><span class="sxs-lookup"><span data-stu-id="344ae-149">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="344ae-150">Windows PowerShell을 사용 하 여 비즈니스용 Skype Online 관리</span><span class="sxs-lookup"><span data-stu-id="344ae-150">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="344ae-151">Windows PowerShell을 사용 하 여 일반적인 비즈니스용 Skype Online 관리 작업 수행</span><span class="sxs-lookup"><span data-stu-id="344ae-151">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="344ae-152">비즈니스용 Skype Online 용 Windows PowerShell 모듈을 사용 하면 비즈니스용 Skype Online에 연결 하는 원격 Windows PowerShell 세션을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="344ae-152">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span> <span data-ttu-id="344ae-153">이 모듈은 64 비트 컴퓨터 에서만 지원 되며 비즈니스용 [Skype Online 용 Windows PowerShell 모듈](https://go.microsoft.com/fwlink/?LinkId=294688) 의 Microsoft 다운로드 센터에서 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="344ae-153">This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="344ae-154">관련 항목</span><span class="sxs-lookup"><span data-stu-id="344ae-154">Related topics</span></span>

[<span data-ttu-id="344ae-155">오디오 회의 설정이 변경 될 때 사용자에 게 전송 되는 전자 메일</span><span class="sxs-lookup"><span data-stu-id="344ae-155">Emails sent to users when their Audio Conferencing settings change</span></span>](emails-sent-to-users-when-their-settings-change.md)

[<span data-ttu-id="344ae-156">오디오 회의 정보를 사용하여 사용자에게 전자 메일 보내기</span><span class="sxs-lookup"><span data-stu-id="344ae-156">Send an email to a user with their Audio Conferencing information</span></span>](send-an-email-to-a-user-with-their-dial-in-information.md)


