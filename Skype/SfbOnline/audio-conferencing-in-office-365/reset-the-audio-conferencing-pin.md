---
title: 비즈니스용 Skype Online에서 오디오 회의 PIN 다시 설정
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 67866a47-89c1-4593-8766-3a68777e2be6
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
description: 'PINS에 대해 알아야 할 일과 비즈니스용 Skype Online에서 PINS를 다시 설정하는 방법을 찾아보세요. '
ms.openlocfilehash: 21e2742653e72919df0647c0539fdb335585cc84
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2020
ms.locfileid: "44164697"
---
# <a name="reset-the-audio-conferencing-pin-in-skype-for-business-online"></a><span data-ttu-id="7d62f-103">비즈니스용 Skype Online에서 오디오 회의 PIN 다시 설정</span><span class="sxs-lookup"><span data-stu-id="7d62f-103">Reset the Audio Conferencing PIN in Skype for Business Online</span></span>

> [!Note]
> <span data-ttu-id="7d62f-104">Microsoft Teams에서 오디오 회의 PIN을 다시 설정하는 자세한 내용은 Microsoft Teams에서 오디오 회의 PIN 재설정을 [참조하세요.](/MicrosoftTeams/reset-the-audio-conferencing-pin-in-teams)</span><span class="sxs-lookup"><span data-stu-id="7d62f-104">For information about resetting Audio Conferencing PINs in Microsoft Teams, see [Reset the Audio Conferencing PIN in Microsoft Teams](/MicrosoftTeams/reset-the-audio-conferencing-pin-in-teams).</span></span>

<span data-ttu-id="7d62f-105">PIN은 오디오 회의를 사용하도록 설정된 각 비즈니스용 Skype 사용자에 대해 생성된 숫자로 된 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="7d62f-105">A PIN is a code made up of numbers that is created for each Skype for Business user who is enabled for audio conferencing.</span></span> <span data-ttu-id="7d62f-106">오디오 회의 PI는 모임 이끌이가 모임 이끌이를 식별하고 전화로 모임을 시작할 수 있도록 하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d62f-106">Audio conferencing PINs are used by meeting organizers to identify that they are the meeting organizer and allow them to start a meeting over the phone.</span></span> <span data-ttu-id="7d62f-107">비즈니스용 Skype 앱을 사용하여 모임을 시작하는 경우 PIN이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7d62f-107">If they use the Skype for Business app to start the meeting, a PIN isn't required.</span></span> <span data-ttu-id="7d62f-108">사용자가 PIN을 잊어버려 오디오 회의를 사용하도록 설정한 경우 보낸 전자 메일에서 해당 PIN을 찾을 수 없는 경우 관리자는 PIN을 재설정하거나 자신의 PIN을 재설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d62f-108">If users forget their PIN and they can't find it in the email that was sent to them when they were enabled for audio conferencing, an administrator can reset their PIN, or they can reset their own PIN.</span></span>
  
<span data-ttu-id="7d62f-109">인증된 사용자가 비즈니스용 Skype 앱을 사용하여 참가하거나 이끌이가 전화로 PIN에 참가할 때 모임을 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d62f-109">Meetings can be started when an authenticated user joins using the Skype for Business app or when the organizer joins with his or her PIN over the phone.</span></span> <span data-ttu-id="7d62f-110">모임을 시작하려면 PIN이 필요한 경우 전화를 통해 참가하는 사용자는 대기실에 배치됩니다. 모임이 시작될 때까지 대기 중 음악을 듣게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d62f-110">When a meeting requires a PIN to start, users who join over the phone will be placed in the lobby and will listen to music on hold until the meeting starts.</span></span> <span data-ttu-id="7d62f-111">모임 이끌이가 전화를 통해 모임을 시작하는 데 PIN이 필요하지 않은 경우 발신자는 모임에 참가할 때 PIN을 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d62f-111">If the organizer of a meeting doesn't require a PIN to start the meeting over the phone, then callers won't be asked to provide a PIN when they join the meeting.</span></span>
  
## <a name="reset-a-users-pin"></a><span data-ttu-id="7d62f-112">사용자의 PIN 다시 설정</span><span class="sxs-lookup"><span data-stu-id="7d62f-112">Reset a user's PIN</span></span>

1. <span data-ttu-id="7d62f-113">직장 또는 학교 계정으로 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="7d62f-113">Sign in with your work or school account.</span></span>
    
2. <span data-ttu-id="7d62f-114">비즈니스용 Skype의 관리 > 왼쪽 탐색 모음에서 오디오 **회의를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="7d62f-114">Go to the admin center > **Skype for Business**, and in the left navigation, click **Audio conferencing**.</span></span>
    
3. <span data-ttu-id="7d62f-115">사용자를 **클릭하고** PIN을 다시 설정할 사용자를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7d62f-115">Click on **Users**, select the user that you want to reset the PIN for.</span></span>
    
4. <span data-ttu-id="7d62f-116">작업 창의 PIN **아래에서** 재설정을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="7d62f-116">In the Action pane, under **PIN**, click **Reset**.</span></span>
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
   
## <a name="have-a-user-reset-his-or-her-own-pin"></a><span data-ttu-id="7d62f-117">사용자가 자신의 PIN을 다시 설정하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d62f-117">Have a user reset his or her own PIN</span></span>

<span data-ttu-id="7d62f-118">사용자는 전화 접속 회의 페이지에서 PIN 재설정 옵션을 사용하여 **PIN을** 재설정할 **수** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d62f-118">A user can reset a PIN by using the **Reset PIN** option on the **Dial-in Conferencing** page.</span></span> <span data-ttu-id="7d62f-119">이 페이지는 다음 세 가지 방법 중 하나에서 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d62f-119">This page can be accessed in one of three ways:</span></span>

* <span data-ttu-id="7d62f-120">브라우저에서 [https://mysettings.lync.com/pstncalling](https://mysettings.lync.com/pstncalling) .</span><span class="sxs-lookup"><span data-stu-id="7d62f-120">In a browser, go to [https://mysettings.lync.com/pstncalling](https://mysettings.lync.com/pstncalling).</span></span>
* <span data-ttu-id="7d62f-121">비즈니스용 Skype에서 옵션  옆에 있는 표시 메뉴 화살표를 클릭한 다음 도구 전화 접속 회의   >  **설정을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="7d62f-121">In Skype for Business, click the **Show Menu** arrow next to **Options**, and then click **Tools** > **Dial-in Conference Settings**.</span></span>
* <span data-ttu-id="7d62f-122">비즈니스용 Skype에서 옵션을 클릭하고 **왼쪽** 메뉴에서 통화 전달을 클릭한 다음 더 많은 통화 설정 **섹션에서** 온라인 설정  **편집을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="7d62f-122">In Skype for Business, click **Options**, click **Call Forwarding** in the left menu, and then in the **More Call Settings** section, click **Edit settings online**.</span></span> 

## <a name="what-else-should-you-know-about-pins"></a><span data-ttu-id="7d62f-123">PINS에 대해 알아야 할 다른 것은 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="7d62f-123">What else should you know about PINs?</span></span>

- <span data-ttu-id="7d62f-124">보안을 위해 PIN이 다시 설정되면 한 번만 관리자에게 PIN이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d62f-124">For security purposes, the PIN is only shown to an administrator on one time, when the PIN is reset.</span></span> <span data-ttu-id="7d62f-125">관리자가 PIN을 다시 설정한 후 PIN은 비즈니스용 Skype 관리 센터 및 비즈니스용 **Skype** 관리 센터에 \*\*\*\*\*\*\*로 표시되어 Get-CsCsOnlineDialInConfencingUser 결과에 Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7d62f-125">After the PIN is reset by an administrator, the PIN will be listed as \*\*\*\*\*\*\*\*\*\*\* in the **Skype for Business admin center** and in the results when they use Get-CsCsOnlineDialInConfencingUser in Windows PowerShell.</span></span>
    
- <span data-ttu-id="7d62f-126">사용자에게 자동으로 전자 메일을 보내는 것은 기본적으로 사용하도록 설정되며, 사용자가 오디오 회의를 사용하도록 설정하거나 PIN이 다시 설정되면 해당 PIN이 있는 전자 메일을 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d62f-126">Automatically sending emails to users is enabled by default, and users will receive an email with their PIN when they're enabled for audio conferencing or when the PIN is reset.</span></span> <span data-ttu-id="7d62f-127">하지만 전자 메일 자동 전송을 사용하지 않도록 설정한 경우 사용자에게 PIN 재설정 전자 메일이 전송되지 않고 PIN 정보를 사용자에게 수동으로 보내야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d62f-127">But if you have disabled automatically sending emails, a PIN reset email won't be sent to a user and you will have to manually send the PIN information to the user.</span></span>
    
- <span data-ttu-id="7d62f-128">모임이 시작되면 로비의 모든 사용자가 자동으로 참가합니다.</span><span class="sxs-lookup"><span data-stu-id="7d62f-128">When a meeting starts, all of the users in the lobby will automatically join it.</span></span> <span data-ttu-id="7d62f-129">예를 들어 두 참가자가 시작되기 전에 모임에 참가하려고 하면 대기실에 배치되고 대기 중 음악이 들리며, 모임 이끌이가 전화를 통해 PIN을 사용하여 참가하면 모임이 시작되고 로비의 참가자가 모임에 참가합니다.</span><span class="sxs-lookup"><span data-stu-id="7d62f-129">For example, if two participants try to join a meeting before it has been started, they will be put in the lobby and will listen to music on hold, and when the meeting organizer joins using his PIN via phone, the meeting will start and the participants in the lobby will join the meeting.</span></span>
    
- <span data-ttu-id="7d62f-130">기본 설정은 익명 발신자에 의해 모임을 시작하도록 허용하지 않는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="7d62f-130">The default setting is to not allow a meeting to be started by anonymous callers.</span></span>
    
- <span data-ttu-id="7d62f-131">사용자가 오디오 회의를 사용하도록 설정하면 기본적으로 회의 정보와 PIN이 포함된 전자 메일이 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d62f-131">When you enable a user for audio conferencing, by default they are sent emails that include conferencing information and their PIN.</span></span> <span data-ttu-id="7d62f-132">PIN이 재설정되면 사용자에게 설정된 기본 SMTP 주소(별칭)로 전자 메일로 새 PIN이 사용자에게 보내지기 때문에 Microsoft 365 또는 Office 365 사서함이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d62f-132">The user must have a Microsoft 365 or Office 365 mailbox, because when a PIN is reset, a new PIN will be sent to the user in email to their primary SMTP address (alias) that is set for the user.</span></span>
    
- <span data-ttu-id="7d62f-133">오디오 회의를 설정할 때 조직의 PI에 필요한 숫자를 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d62f-133">When you set up audio conferencing, you set the digits that are required for the PINs in your organization.</span></span> <span data-ttu-id="7d62f-134">PINS는 4~12자리 숫자일 수 있습니다. 기본값은 5입니다.</span><span class="sxs-lookup"><span data-stu-id="7d62f-134">PINs can be from 4 to 12 digits - the default is 5.</span></span> <span data-ttu-id="7d62f-135">PIN 길이 설정을 변경하는 경우 설정은 새로 생성된 PIN에만 적용되고 오디오 회의에 사용할 수 있는 기존 사용자의 PIN 설정에는 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7d62f-135">If you change the PIN length setting, the setting is only applied on newly generated PINs and isn't applied to the PIN setting for existing users that are enabled for audio conferencing.</span></span> <span data-ttu-id="7d62f-136">오디오 회의 모임의 PIN 길이 설정을 [참조합니다.](Set-the-PIN-length-for-Audio-Conferencing-meetings.md)</span><span class="sxs-lookup"><span data-stu-id="7d62f-136">See [Set the length of the PIN for Audio Conferencing meetings](Set-the-PIN-length-for-Audio-Conferencing-meetings.md).</span></span>
    
- <span data-ttu-id="7d62f-137">기본적으로 전자 메일은 사용자의 Microsoft 365 또는 Office 365 기본 SMTP 주소로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d62f-137">The email by default will be set to the Microsoft 365 or Office 365 primary SMTP address of the user.</span></span> <span data-ttu-id="7d62f-138">Hotmail 또는 MSN 전자 메일 주소와 같은 비 Microsoft 365 또는 비 Office 365 주소로 전자 메일을 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d62f-138">You can send an email to a non-Microsoft 365 or non-Office 365 address, such as a Hotmail or MSN email address.</span></span> <span data-ttu-id="7d62f-139">다음을 사용하여 기본 전자 메일 주소를 Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7d62f-139">You can override the default email address by using Windows PowerShell.</span></span> <span data-ttu-id="7d62f-140">이 기능은 사용자에게 Microsoft 365 또는 Office 365에 Exchange 사서함이 없는 경우 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="7d62f-140">This is useful if the users don't have an Exchange mailbox in Microsoft 365 or Office 365.</span></span>
    
- <span data-ttu-id="7d62f-141">전자 메일이 전송되는 기본 사용자 주소를 다시 지정하려면 테넌트 관리자는 Set-CsOnlineDialInConferencingUser -amos.marble -ResetLeaderPIN -SendEmail -SendEmailToAddress "u@hotmail.com" cmdlet을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d62f-141">To override the default user address where the email is sent, the tenant admin can use the following cmdlet: Set-CsOnlineDialInConferencingUser -amos.marble -ResetLeaderPIN -SendEmail -SendEmailToAddress "u@hotmail.com".</span></span> <span data-ttu-id="7d62f-142">SendEmail 매개 변수는 사용자의 전자 메일 주소를 다시 정의하는 데 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="7d62f-142">The SendEmail parameter is required to override the email address of the user.</span></span>
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="7d62f-143">사용자 계정으로 관리하는 방법을 알고 Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="7d62f-143">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="7d62f-144">시간을 절약하거나 이 작업을 자동화하기 위해 [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) cmdlet을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d62f-144">To save time or automate this, you can use the [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) cmdlet.</span></span>
    
- <span data-ttu-id="7d62f-145">다음을 실행하여 Amos Marble에 대한 PIN을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d62f-145">You can set the PIN for Amos Marble by running:</span></span>
    
  ```PowerShell
  Set-CsOnlineDialInConferencingUser -id amos.marble@contoso.com -ResetLeaderPIN
  ```

- <span data-ttu-id="7d62f-146">Windows PowerShell 관리는 사용자 및 사용자가 허용되거나 허용되지 않는 작업을 관리하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="7d62f-146">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="7d62f-147">이 Windows PowerShell 여러 작업을 수행할 때 일상적인 작업을 간소화할 수 있는 단일 관리 지점을 사용하여 Microsoft 365 또는 Office 365를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d62f-147">With Windows PowerShell, you can manage Microsoft 365 or Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="7d62f-148">다음 항목을 Windows PowerShell 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7d62f-148">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="7d62f-149">Microsoft 365 또는 Office 365 PowerShell을 사용하는 이유</span><span class="sxs-lookup"><span data-stu-id="7d62f-149">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="7d62f-150">Microsoft 365 또는 Office 365를 관리하는 가장 좋은 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="7d62f-150">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="7d62f-151">Windows PowerShell Microsoft 365 관리 센터를 사용하는 것 이상으로 속도, 단순성 및 생산성에 많은 이점이 있습니다. 예를 들어 한 번으로 많은 사용자에 대해 설정을 변경할 때도 그렇습니다.</span><span class="sxs-lookup"><span data-stu-id="7d62f-151">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center, such as when you are making settings changes for many users at one time.</span></span> <span data-ttu-id="7d62f-152">다음 항목에서 이러한 이점에 대해 자세히 배워야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d62f-152">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="7d62f-153">Windows PowerShell 및 Lync Online 소개</span><span class="sxs-lookup"><span data-stu-id="7d62f-153">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [<span data-ttu-id="7d62f-154">비즈니스 Windows PowerShell 사용하여 비즈니스용 Skype Online 관리</span><span class="sxs-lookup"><span data-stu-id="7d62f-154">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="7d62f-155">비즈니스용 Windows PowerShell Skype Online 관리 작업을 수행하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d62f-155">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="7d62f-156">비즈니스 Windows PowerShell용 Skype Online 모듈을 사용하면 비즈니스용 Skype Online에 Windows PowerShell 원격 세션을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d62f-156">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span> <span data-ttu-id="7d62f-157">64비트 컴퓨터에서만 지원되는 이 모듈은 비즈니스용 [Skype Online용](https://go.microsoft.com/fwlink/?LinkId=294688) Windows PowerShell 모듈의 Microsoft 다운로드 센터에서 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d62f-157">This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="7d62f-158">관련 항목</span><span class="sxs-lookup"><span data-stu-id="7d62f-158">Related topics</span></span>

[<span data-ttu-id="7d62f-159">사용자의 회의 ID 다시 설정</span><span class="sxs-lookup"><span data-stu-id="7d62f-159">Reset a conference ID for a user</span></span>](reset-a-conference-id-for-a-user.md)
