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
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Pin에 대해 알아야 할 내용과 비즈니스용 Skype Online에서 다시 설정 하는 방법에 대해 알아봅니다. '
ms.openlocfilehash: a00c36475059a05bb7cf3a9057920b63a09e9a43
ms.sourcegitcommit: afc7edd03f4baa1d75f9642d4dbce767fec69b00
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/07/2020
ms.locfileid: "40962696"
---
# <a name="reset-the-audio-conferencing-pin-in-skype-for-business-online"></a><span data-ttu-id="c4107-103">비즈니스용 Skype Online에서 오디오 회의 PIN 다시 설정</span><span class="sxs-lookup"><span data-stu-id="c4107-103">Reset the Audio Conferencing PIN in Skype for Business Online</span></span>

> [!Note]
> <span data-ttu-id="c4107-104">Microsoft 팀에서 오디오 회의 pin을 다시 설정 하는 방법에 대 한 자세한 내용은 [Microsoft 팀에서 오디오 회의 Pin 다시 설정을](/MicrosoftTeams/reset-the-audio-conferencing-pin-in-teams)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c4107-104">For information about resetting Audio Conferencing PINs in Microsoft Teams, see [Reset the Audio Conferencing PIN in Microsoft Teams](/MicrosoftTeams/reset-the-audio-conferencing-pin-in-teams).</span></span>

<span data-ttu-id="c4107-105">PIN은 오디오 회의를 사용 하도록 설정 된 각 비즈니스용 Skype 사용자에 대해 생성 되는 숫자로 구성 된 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="c4107-105">A PIN is a code made up of numbers that is created for each Skype for Business user who is enabled for audio conferencing.</span></span> <span data-ttu-id="c4107-106">모임 이끌이가 오디오 회의 Pin을 사용 하 여 모임 이끌이가이를 식별 하 고 휴대폰을 통해 모임을 시작 하도록 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4107-106">Audio conferencing PINs are used by meeting organizers to identify that they are the meeting organizer and allow them to start a meeting over the phone.</span></span> <span data-ttu-id="c4107-107">Skype for Business 앱을 사용 하 여 모임을 시작 하는 경우 PIN이 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c4107-107">If they use the Skype for Business app to start the meeting, a PIN isn't required.</span></span> <span data-ttu-id="c4107-108">사용자가 PIN을 잊거나 오디오 회의를 사용 하도록 설정 했을 때 전송 된 전자 메일에서 찾을 수 없는 경우 관리자가 PIN을 다시 설정 하거나 자신의 PIN을 다시 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4107-108">If users forget their PIN and they can't find it in the email that was sent to them when they were enabled for audio conferencing, an administrator can reset their PIN, or they can reset their own PIN.</span></span>
  
<span data-ttu-id="c4107-109">인증 된 사용자가 비즈니스용 Skype 앱을 사용 하 여 참가할 때 또는 주최자가 전화기를 통해 자신의 PIN으로 참가할 때 모임을 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4107-109">Meetings can be started when an authenticated user joins using the Skype for Business app or when the organizer joins with his or her PIN over the phone.</span></span> <span data-ttu-id="c4107-110">모임에서 PIN을 시작 해야 하는 경우 휴대폰을 통해 참가 하는 사용자는 대기실에 저장 되며 모임이 시작 될 때까지 보류 중인 음악을 청취 하 게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c4107-110">When a meeting requires a PIN to start, users who join over the phone will be placed in the lobby and will listen to music on hold until the meeting starts.</span></span> <span data-ttu-id="c4107-111">모임 이끌이가 휴대폰을 통해 모임을 시작 하기 위해 PIN이 필요 하지 않은 경우에는 호출자가 모임에 참가할 때 PIN을 제공 하 라는 메시지가 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c4107-111">If the organizer of a meeting doesn't require a PIN to start the meeting over the phone, then callers won't be asked to provide a PIN when they join the meeting.</span></span>
  
## <a name="reset-a-users-pin"></a><span data-ttu-id="c4107-112">사용자의 PIN 다시 설정</span><span class="sxs-lookup"><span data-stu-id="c4107-112">Reset a user's PIN</span></span>

1. <span data-ttu-id="c4107-113">회사 또는 학교 계정으로 Office 365에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4107-113">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="c4107-114">**비즈니스용 Skype**> 관리 센터로 이동 하 고 왼쪽 탐색 창에서 **오디오 회의**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4107-114">Go to the admin center > **Skype for Business**, and in the left navigation, click **Audio conferencing**.</span></span>
    
3. <span data-ttu-id="c4107-115">**사용자**를 클릭 하 고 PIN을 다시 설정 하려는 사용자를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4107-115">Click on **Users**, select the user that you want to reset the PIN for.</span></span>
    
4. <span data-ttu-id="c4107-116">작업 창의 **핀**에서 **원래 대로**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4107-116">In the Action pane, under **PIN**, click **Reset**.</span></span>
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
   
## <a name="have-a-user-reset-his-or-her-own-pin"></a><span data-ttu-id="c4107-117">사용자가 자신의 PIN을 재설정 하도록 설정</span><span class="sxs-lookup"><span data-stu-id="c4107-117">Have a user reset his or her own PIN</span></span>

<span data-ttu-id="c4107-118">사용자는 **전화 접속 회의** 페이지의 **pin 다시 설정** 옵션을 사용 하 여 pin을 다시 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4107-118">A user can reset a PIN by using the **Reset PIN** option on the **Dial-in Conferencing** page.</span></span> <span data-ttu-id="c4107-119">이 페이지는 다음 세 가지 방법 중 하나로 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4107-119">This page can be accessed in one of three ways:</span></span>

* <span data-ttu-id="c4107-120">브라우저에서으로 이동 [https://mysettings.lync.com/pstncalling](https://mysettings.lync.com/pstncalling)합니다.</span><span class="sxs-lookup"><span data-stu-id="c4107-120">In a browser, go to [https://mysettings.lync.com/pstncalling](https://mysettings.lync.com/pstncalling).</span></span>
* <span data-ttu-id="c4107-121">비즈니스용 Skype에서 **옵션**옆에 있는 **메뉴 표시** 화살표를 클릭 한 다음 **도구** > **전화 접속 회의 설정을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4107-121">In Skype for Business, click the **Show Menu** arrow next to **Options**, and then click **Tools** > **Dial-in Conference Settings**.</span></span>
* <span data-ttu-id="c4107-122">비즈니스용 Skype에서 **옵션**을 클릭 하 고 왼쪽 메뉴의 착신 **전환을** 클릭 한 다음 **기타 통화 설정** 섹션에서 **온라인 설정 편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4107-122">In Skype for Business, click **Options**, click **Call Forwarding** in the left menu, and then in the **More Call Settings** section, click **Edit settings online**.</span></span> 

## <a name="what-else-should-you-know-about-pins"></a><span data-ttu-id="c4107-123">핀에 대해 알아야 할 기타 사항</span><span class="sxs-lookup"><span data-stu-id="c4107-123">What else should you know about PINs?</span></span>

- <span data-ttu-id="c4107-124">Pin을 다시 설정 하면 PIN이 한 번만 관리자 에게만 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c4107-124">For security purposes, the PIN is only shown to an administrator on one time, when the PIN is reset.</span></span> <span data-ttu-id="c4107-125">관리자가 PIN을 다시 설정한 후에는 **비즈니스용 Skype 관리 센터** 에 \* \* \* \* \* \* \* \* \* \* \*로 표시 되는 Pin이 Windows PowerShell에서 CsCsOnlineDialInConfencingUser를 사용할 때 그 결과를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4107-125">After the PIN is reset by an administrator, the PIN will be listed as \*\*\*\*\*\*\*\*\*\*\* in the **Skype for Business admin center** and in the results when they use Get-CsCsOnlineDialInConfencingUser in Windows PowerShell.</span></span>
    
- <span data-ttu-id="c4107-126">사용자에 게 전자 메일을 자동으로 보내는 기능은 기본적으로 사용 되며, 사용자는 오디오 회의를 사용 하도록 설정 하거나 PIN을 다시 설정한 경우 PIN이 포함 된 전자 메일을 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c4107-126">Automatically sending emails to users is enabled by default, and users will receive an email with their PIN when they're enabled for audio conferencing or when the PIN is reset.</span></span> <span data-ttu-id="c4107-127">그러나 자동으로 전자 메일 보내기를 사용 하지 않도록 설정한 경우 PIN 다시 설정 이메일이 사용자에 게 전송 되지 않으므로 PIN 정보를 사용자에 게 수동으로 보내야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4107-127">But if you have disabled automatically sending emails, a PIN reset email won't be sent to a user and you will have to manually send the PIN information to the user.</span></span>
    
- <span data-ttu-id="c4107-128">모임이 시작 되 면 대기실에 있는 모든 사용자가 자동으로 참가 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4107-128">When a meeting starts, all of the users in the lobby will automatically join it.</span></span> <span data-ttu-id="c4107-129">예를 들어 두 명의 참가자가 모임에 참가 하 려 할 때 해당 사용자는 대기실에 저장 되 고 보류 중인 음악을 수신 대기 하 고 모임 이끌이가 휴대폰을 통해 해당 PIN을 사용 하 여 참가할 때 모임이 시작 되 고 로비의 참가자가 참가 하 게 됩니다.  모임.</span><span class="sxs-lookup"><span data-stu-id="c4107-129">For example, if two participants try to join a meeting before it has been started, they will be put in the lobby and will listen to music on hold, and when the meeting organizer joins using his PIN via phone, the meeting will start and the participants in the lobby will join the meeting.</span></span>
    
- <span data-ttu-id="c4107-130">기본 설정은 익명 호출자가 모임을 시작 하도록 허용 하지 않는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c4107-130">The default setting is to not allow a meeting to be started by anonymous callers.</span></span>
    
- <span data-ttu-id="c4107-131">오디오 회의에 대 한 사용자를 활성화 하면 기본적으로 회의 정보와 PIN이 포함 된 전자 메일이 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c4107-131">When you enable a user for audio conferencing, by default they are sent emails that include conferencing information and their PIN.</span></span> <span data-ttu-id="c4107-132">PIN을 다시 설정 하면 사용자에 게 설정 된 기본 SMTP 주소 (별칭)로 새 PIN이 사용자에 게 전송 되므로 사용자에 게 Office 365 사서함이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4107-132">The user must have an Office 365 mailbox, because when a PIN is reset, a new PIN will be sent to the user in email to their primary SMTP address (alias) that is set for the user.</span></span>
    
- <span data-ttu-id="c4107-133">오디오 회의를 설정할 때 조직의 핀에 필요한 자릿수를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4107-133">When you set up audio conferencing, you set the digits that are required for the PINs in your organization.</span></span> <span data-ttu-id="c4107-134">Pin은 4 ~ 12 자리로 지정할 수 있으며 기본값은 5입니다.</span><span class="sxs-lookup"><span data-stu-id="c4107-134">PINs can be from 4 to 12 digits - the default is 5.</span></span> <span data-ttu-id="c4107-135">PIN 길이 설정을 변경 하면 새로 생성 된 핀에만 설정이 적용 되 고 오디오 회의에 사용 하도록 설정 된 기존 사용자의 PIN 설정에는 적용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c4107-135">If you change the PIN length setting, the setting is only applied on newly generated PINs and isn't applied to the PIN setting for existing users that are enabled for audio conferencing.</span></span> <span data-ttu-id="c4107-136">[오디오 회의 모임에 대 한 PIN 길이 설정을](Set-the-PIN-length-for-Audio-Conferencing-meetings.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c4107-136">See [Set the length of the PIN for Audio Conferencing meetings](Set-the-PIN-length-for-Audio-Conferencing-meetings.md).</span></span>
    
- <span data-ttu-id="c4107-137">기본적으로 전자 메일은 사용자의 Office 365 기본 SMTP 주소로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c4107-137">The email by default will be set to the Office 365 primary SMTP address of the user.</span></span> <span data-ttu-id="c4107-138">전자 메일을 Hotmail 또는 MSN 전자 메일 주소와 같은 비 Office 365 주소로 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4107-138">You can send an email to a non-Office 365 address such as a Hotmail or MSN email address.</span></span> <span data-ttu-id="c4107-139">Windows PowerShell을 사용 하 여 기본 전자 메일 주소를 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4107-139">You can override the default email address by using Windows PowerShell.</span></span> <span data-ttu-id="c4107-140">이 기능은 사용자에 게 Office 365의 Exchange 사서함이 없는 경우에 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4107-140">This is useful if the users don't have an Exchange mailbox in Office 365.</span></span>
    
- <span data-ttu-id="c4107-141">전자 메일이 전송 되는 기본 사용자 주소를 재정의 하려면 테 넌 트 관리자가 다음 cmdlet을 사용할 수 있습니다. Get-csonlinedialinconferencinguser-amos. e-ResetLeaderPIN-SendEmail-SendEmailToAddress "u@hotmail.com".</span><span class="sxs-lookup"><span data-stu-id="c4107-141">To override the default user address where the email is sent, the tenant admin can use the following cmdlet: Set-CsOnlineDialInConferencingUser -amos.marble -ResetLeaderPIN -SendEmail -SendEmailToAddress "u@hotmail.com".</span></span> <span data-ttu-id="c4107-142">SendEmail 매개 변수는 사용자의 전자 메일 주소를 재정의 하는 데 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4107-142">The SendEmail parameter is required to override the email address of the user.</span></span>
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="c4107-143">Windows PowerShell을 사용 하 여 관리 하는 방법을 알고 싶으세요?</span><span class="sxs-lookup"><span data-stu-id="c4107-143">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="c4107-144">시간을 절약 하거나이 작업을 자동화 하려면 [Set-get-csonlinedialinconferencinguser](https://go.microsoft.com/fwlink/?LinkId=617688 ) cmdlet을 사용 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c4107-144">To save time or automate this, you can use the [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) cmdlet.</span></span>
    
- <span data-ttu-id="c4107-145">다음을 실행 하 여 Amos 대리석에 대 한 PIN을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4107-145">You can set the PIN for Amos Marble by running:</span></span>
    
  ```PowerShell
  Set-CsOnlineDialInConferencingUser -id amos.marble@contoso.com -ResetLeaderPIN
  ```

- <span data-ttu-id="c4107-146">Windows PowerShell은 사용자 및 허용 되지 않거나 수행할 수 있는 사용자를 관리 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4107-146">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="c4107-147">Windows PowerShell을 사용 하면 여러 작업을 수행할 때 일상 업무를 단순화할 수 있는 단일 관리 지점을 사용 하 여 Office 365를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4107-147">With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="c4107-148">Windows PowerShell을 시작 하려면 다음 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c4107-148">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="c4107-149">Office 365 PowerShell을 사용 해야 하는 이유</span><span class="sxs-lookup"><span data-stu-id="c4107-149">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="c4107-150">Windows PowerShell을 사용 하 여 Office 365를 관리 하는 가장 좋은 방법</span><span class="sxs-lookup"><span data-stu-id="c4107-150">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="c4107-151">Windows PowerShell에는 한 번에 여러 사용자의 설정을 변경 하는 경우와 같이 Microsoft 365 관리 센터를 사용 하는 경우에만 속도, 단순성, 생산성 등 다양 한 이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4107-151">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center, such as when you are making settings changes for many users at one time.</span></span> <span data-ttu-id="c4107-152">다음 항목에서 이러한 이점에 대해 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="c4107-152">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="c4107-153">Windows PowerShell 및 Lync Online 소개</span><span class="sxs-lookup"><span data-stu-id="c4107-153">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [<span data-ttu-id="c4107-154">Windows PowerShell을 사용 하 여 비즈니스용 Skype Online 관리</span><span class="sxs-lookup"><span data-stu-id="c4107-154">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="c4107-155">Windows PowerShell을 사용 하 여 일반적인 비즈니스용 Skype Online 관리 작업 수행</span><span class="sxs-lookup"><span data-stu-id="c4107-155">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="c4107-156">비즈니스용 Skype Online 용 Windows PowerShell 모듈을 사용 하면 비즈니스용 Skype Online에 연결 하는 원격 Windows PowerShell 세션을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4107-156">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span> <span data-ttu-id="c4107-157">이 모듈은 64 비트 컴퓨터 에서만 지원 되며 비즈니스용 [Skype Online 용 Windows PowerShell 모듈](https://go.microsoft.com/fwlink/?LinkId=294688) 의 Microsoft 다운로드 센터에서 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4107-157">This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="c4107-158">관련 항목</span><span class="sxs-lookup"><span data-stu-id="c4107-158">Related topics</span></span>

[<span data-ttu-id="c4107-159">사용자의 회의 ID 다시 설정</span><span class="sxs-lookup"><span data-stu-id="c4107-159">Reset a conference ID for a user</span></span>](reset-a-conference-id-for-a-user.md)
