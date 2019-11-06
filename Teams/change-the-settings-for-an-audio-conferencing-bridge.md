---
title: 오디오 회의 브리지의 설정 변경
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 783fad3f-b77c-422b-b91f-7c8b0af324fb
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: ms.teamsadmincenter.audioconferencing.bridgesettings
ms.custom:
- Audio Conferencing
description: '비즈니스용 Skype 또는 Microsoft 팀 앱을 사용 하지 않을 때 모임 이끌이의 이름 및 pin을 수집 하는 데 사용 되는 회의 브리지에 대 한 설정을 변경 해야 하는 단계를 확인 하세요. '
ms.openlocfilehash: b7ac85729bafe9d27f9e33cfa22597811b8d3d0b
ms.sourcegitcommit: 15fe483079847d24869e325eead35f252da8c7dd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/06/2019
ms.locfileid: "37516955"
---
# <a name="change-the-settings-for-an-audio-conferencing-bridge"></a><span data-ttu-id="9e547-103">오디오 회의 브리지의 설정 변경</span><span class="sxs-lookup"><span data-stu-id="9e547-103">Change the settings for an Audio Conferencing bridge</span></span>

<span data-ttu-id="9e547-104">Office 365에서 오디오 회의를 설정 하는 경우 오디오 회의 브리지 라고 하는 사용자의 전화 번호를 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9e547-104">When you are setting up Audio Conferencing in Office 365, you will receive phone numbers for your users from what is called an audio conferencing bridge.</span></span> <span data-ttu-id="9e547-105">회의 브리지에는 하나 이상의 전화 번호가 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e547-105">A conferencing bridge can contain one or more phone numbers.</span></span> <span data-ttu-id="9e547-106">이러한 전화 번호는 발신자가 모임에 전화를 걸 때 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9e547-106">These phone numbers are used when callers dial in to a meeting.</span></span> <span data-ttu-id="9e547-107">전화 번호는 비즈니스용 Skype 또는 Microsoft 팀 모임 초대의 아래쪽에 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e547-107">The phone number is included at the bottom of the Skype for Business or Microsoft Teams meeting invite.</span></span>
  
<span data-ttu-id="9e547-108">회의 브리지는 전화를 걸거나 모임 자동 전화 교환을 사용 하 여 음성 메시지를 발신자에 게 메시지를 표시 하 고, 설정에 따라 알림을 재생 하 고, 발신자에 게 자신의 이름을 기록 하도록 요청 하 고, PIN 설정을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e547-108">The conferencing bridge answers a call and prompts the caller with voice prompts using a meeting auto attendant, and then, depending on your settings, it can play notifications, ask callers to record their name, and control the PIN settings.</span></span> <span data-ttu-id="9e547-109">모임이 비즈니스용 Skype 또는 Microsoft 팀 앱을 사용 하지 않는 경우 모임을 시작할 수 있도록 모임 이끌이에게 Pin이 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9e547-109">PINs are given to meeting organizers to allow them to start a meeting when they are aren't using a Skype for Business or Microsoft Teams app.</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="9e547-110">PIN은 비즈니스용 Skype 또는 Microsoft 팀 사용자가 아직 모임을 시작 하지 않은 경우 모임 이끌이에게만 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e547-110">A PIN is only required for the meeting organizer when a Skype for Business or Microsoft Teams app user hasn't already started the meeting.</span></span> <span data-ttu-id="9e547-111">모든 사용자가 모임에 전화를 거는 경우 모임 이끌이가 모임을 시작 하려면 PIN이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e547-111">If everyone is dialing in to the meeting, the PIN is required for the meeting organizer to start the meeting.</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="an-icon-showing-the-microsoft-teams-logomediateams-logo-30x30png-using-the-microsoft-teams-admin-center"></a>![Microsoft 팀 로고를 표시 하는 아이콘](media/teams-logo-30x30.png) <span data-ttu-id="9e547-113">Microsoft 팀 관리 센터 사용</span><span class="sxs-lookup"><span data-stu-id="9e547-113">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="9e547-114">왼쪽 탐색 창에서 **모임** > **회의 브리지로**이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e547-114">In the left navigation, go to **Meetings** > **Conference bridges**.</span></span> 

2. <span data-ttu-id="9e547-115">**회의 브리지** 페이지 맨 위에서 **브리지 설정을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e547-115">At the top of the **Conference bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="9e547-116">**브리지 설정** 창에서 다음을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e547-116">In the **Bridge settings** pane, select:</span></span> 
   - <span data-ttu-id="9e547-117">**모임 입력 및 종료 알림** 이 기능을 해제 하면 모임에 참가 한 사용자는 다른 사용자가 모임을 시작 하거나 떠날 때 알림을 받을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9e547-117">**Meeting entry and exit notifications** If you turn this off, users who have already joined the meeting won't be notified when someone enters or leaves the meeting.</span></span>
    
     <span data-ttu-id="9e547-118">모임 입장을 켜고 **알림을 종료**하면 다음 옵션을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e547-118">When you turn on **Meeting entry and exit notifications**, you can select these options:</span></span>
    
   - <span data-ttu-id="9e547-119">**이름 또는 전화 번호** 사용자가 모임에 전화를 걸 때 전화 번호는 참가할 때 재생 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9e547-119">**Names or phone numbers** When users dial in to a meeting, their phone number will be played when they join it.</span></span>
    
   - <span data-ttu-id="9e547-120">**톤** 사용자가 모임에 전화를 걸 때 오디오 신호음이 참가할 때 재생 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9e547-120">**Tones** When users dial in to a meeting, an audio tone will be played when they join it.</span></span>
      
   - <span data-ttu-id="9e547-121">**모임에 참가 하기 전에 호출자에 게 자신의 이름을 기록 하도록 요청** 이 기능을 해제 하면 호출자가 모임에 참가 하기 전에 해당 이름을 기록 하 라는 메시지가 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9e547-121">**Ask callers to record their name before joining the meeting** If you turn this off, callers won't be asked to record their name before they join a meeting.</span></span>

4. <span data-ttu-id="9e547-122">모임의 PIN 길이를 설정 하려면 **pin 길이** 목록에서 원하는 pin의 자릿수를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e547-122">To set the PIN length for meetings, select the number of digits you want for the PIN in the **PIN length** list.</span></span>

5. <span data-ttu-id="9e547-123">사용자에 게 전자 메일을 보낼지 여부를 지정 하려면 **오디오 회의 구성이 변경 되는 경우 자동으로 전자 메일을 사용자에 게 보내기를**설정 하거나 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e547-123">To specify whether to send email to your users, enable or disable **Automatically send emails to users if their audio conferencing configuration changes**.</span></span>
    <span data-ttu-id="9e547-124">자세한 내용은 [비즈니스용 Skype Online에서 설정이 변경 될 때 사용자에 게 전송](/SkypeForBusiness/audio-conferencing-in-office-365/emails-sent-to-users-when-their-settings-change) 되 [는 Microsoft 팀 또는 전자 메일에서 오디오 회의 설정이 변경 될 때 사용자에 게 자동으로 전송 되는 전자 메일을](emails-sent-to-users-when-their-settings-change-in-teams.md) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9e547-124">See [Emails automatically sent to users when their Audio Conferencing settings change in Microsoft Teams](emails-sent-to-users-when-their-settings-change-in-teams.md) or [Emails sent to users when their settings change in Skype for Business Online](/SkypeForBusiness/audio-conferencing-in-office-365/emails-sent-to-users-when-their-settings-change) for more information.</span></span>
 
6. <span data-ttu-id="9e547-125">**저장**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e547-125">Click **Save**.</span></span> 


## <a name="an-icon-showing-the-skype-for-business-logomediasfb-logo-30x30png--using-the-skype-for-business-admin-center"></a>![비즈니스용 Skype 로고를 표시 하는 아이콘](media/sfb-logo-30x30.png)  <span data-ttu-id="9e547-127">비즈니스용 Skype 관리 센터 사용</span><span class="sxs-lookup"><span data-stu-id="9e547-127">Using the Skype for Business admin center</span></span>

 <span data-ttu-id="9e547-128">**발신자가 모임에 참가 하는 경우의 모임 환경 설정**</span><span class="sxs-lookup"><span data-stu-id="9e547-128">**Set up the meeting experience when callers join a meeting**</span></span>
    
1. <span data-ttu-id="9e547-129">**비즈니스용 Skype 관리 센터**의 왼쪽 탐색 창에서 **오디오 회의** > **Microsoft bridge 설정**으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e547-129">In the **Skype for Business admin center**, in the left navigation go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
2. <span data-ttu-id="9e547-130">**Microsoft 브리지 설정** 페이지의 **모임 참가 환경**에서 다음을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e547-130">On the **Microsoft bridge settings** page, under **Meeting join experience**, select:</span></span>
    
   - <span data-ttu-id="9e547-131">**모임 입력 및 종료 알림이 설정 되도록 설정** 이 옵션이 기본적으로 선택 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e547-131">**Enable meeting entry and exit notifications to be turned on** This is selected by default.</span></span> <span data-ttu-id="9e547-132">확인란의 선택을 취소 하면 모임에 이미 참가 한 사용자에 게 다른 사용자가 모임에 입장 하거나 떠날 때 알림이 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9e547-132">If you clear the check box, users who have already joined the meeting won't be notified when someone enters or leaves the meeting.</span></span>
    
   - <span data-ttu-id="9e547-133">**모임 시작 및 종료 알림 사용을**선택 하 여 설정 하는 경우 **입력/종료 알림 형식** 목록에서 다음 옵션을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e547-133">When you select **Enable meeting entry and exit notifications to be turned on**, you can select these options from the **Entry/exit announcement type** list:</span></span>
    
   - <span data-ttu-id="9e547-134">**이름 또는 전화 번호** 사용자가 모임에 전화를 걸 때 전화 번호는 참가할 때 재생 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9e547-134">**Names or phone numbers** When users dial in to a meeting, their phone number will be played when they join it.</span></span>
    
   - <span data-ttu-id="9e547-135">**톤** 사용자가 모임에 전화를 걸 때 오디오 신호음이 참가할 때 재생 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9e547-135">**Tones** When users dial in to a meeting, an audio tone will be played when they join it.</span></span>
  
   - <span data-ttu-id="9e547-136">**모임에 참가 하기 전에 호출자에 게 자신의 이름을 기록 하도록 요청** 이 옵션이 기본적으로 선택 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e547-136">**Ask callers to record their name before joining the meeting** This is selected by default.</span></span> <span data-ttu-id="9e547-137">확인란의 선택을 취소 한 경우에는 호출자가 모임에 참가 하기 전에 해당 이름을 기록해 야 한다는 메시지가 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9e547-137">If you clear the check box, callers won't be asked to record their name before they join a meeting.</span></span>
    
3. <span data-ttu-id="9e547-138">변경 작업을 수행한 후 **저장**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e547-138">After you make your changes, click **Save**.</span></span>
    
<span data-ttu-id="9e547-139">**모임의 PIN 길이 설정**</span><span class="sxs-lookup"><span data-stu-id="9e547-139">**Set the PIN length for meetings**</span></span>
  
1. <span data-ttu-id="9e547-140">회사 또는 학교 계정으로 Office 365에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e547-140">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="9e547-141">**Microsoft 365 관리 센터** > **비즈니스용 Skype**로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e547-141">Go to the **Microsoft 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="9e547-142">**비즈니스용 Skype 관리 센터**의 왼쪽 탐색 창에서 **오디오 회의** > **Microsoft bridge 설정**으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e547-142">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
4. <span data-ttu-id="9e547-143">**Microsoft 브리지 설정** 페이지의 **보안**에서 **PIN 길이** 목록에 원하는 pin의 자릿수를 입력 한 다음 **저장**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e547-143">On the **Microsoft bridge settings** page, under **Security**, enter the number of digits you want for the PIN in the **PIN length** list, and then click **Save**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="9e547-144">PIN은 4 ~ 12 자리 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e547-144">The PIN must be between 4 and 12 digits.</span></span> 
  
<span data-ttu-id="9e547-145">**사용자에 게 전자 메일을 보낼지 여부 선택**</span><span class="sxs-lookup"><span data-stu-id="9e547-145">**Select whether to send email to your users**</span></span>
  
1. <span data-ttu-id="9e547-146">회사 또는 학교 계정으로 Office 365에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e547-146">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="9e547-147">**Microsoft 365 관리 센터** > **비즈니스용 Skype**로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e547-147">Go to the **Microsoft 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="9e547-148">**비즈니스용 Skype 관리 센터**의 왼쪽 탐색 창에서 **오디오 회의** > **Microsoft bridge 설정**으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e547-148">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
4. <span data-ttu-id="9e547-149">**Microsoft 브리지 설정** 페이지에서 **전화 접속 정보가 변경 된 경우 자동으로 전자 메일을 사용자에 게 보내기를**선택 하거나 선택을 취소 한 다음 **저장**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e547-149">On the **Microsoft bridge settings** page, select or clear **Automatically send emails to users if their dial-in information changes**, and then click **Save**.</span></span>
    
    <span data-ttu-id="9e547-150">자세한 내용은 [비즈니스용 Skype Online에서 설정이 변경 될 때 사용자에 게 전송](/SkypeForBusiness/audio-conferencing-in-office-365/emails-sent-to-users-when-their-settings-change) 되 [는 Microsoft 팀 또는 전자 메일에서 오디오 회의 설정이 변경 될 때 사용자에 게 자동으로 전송 되는 전자 메일을](emails-sent-to-users-when-their-settings-change-in-teams.md) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9e547-150">See [Emails automatically sent to users when their Audio Conferencing settings change in Microsoft Teams](emails-sent-to-users-when-their-settings-change-in-teams.md) or [Emails sent to users when their settings change in Skype for Business Online](/SkypeForBusiness/audio-conferencing-in-office-365/emails-sent-to-users-when-their-settings-change) for more information.</span></span>
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="9e547-151">Windows PowerShell을 사용 하 여 관리 하는 방법을 알고 싶으세요?</span><span class="sxs-lookup"><span data-stu-id="9e547-151">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="9e547-152">시간을 절약 하거나이 프로세스를 자동화 하려면 [Set-CsDialinConferencingBridge](https://go.microsoft.com/fwlink/?LinkId=617686) cmdlet을 사용 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9e547-152">To save time or automate this process, you can use the [Set-CsDialinConferencingBridge](https://go.microsoft.com/fwlink/?LinkId=617686) cmdlet.</span></span>
    
- <span data-ttu-id="9e547-153">Windows PowerShell은 사용자 및 허용 되지 않거나 수행할 수 있는 사용자를 관리 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e547-153">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="9e547-154">Windows PowerShell을 사용 하면 여러 작업을 수행할 때 일상 업무를 단순화할 수 있는 단일 관리 지점을 사용 하 여 Office 365를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e547-154">With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="9e547-155">Windows PowerShell을 시작 하려면 다음 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9e547-155">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="9e547-156">Office 365 PowerShell을 사용 해야 하는 이유</span><span class="sxs-lookup"><span data-stu-id="9e547-156">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="9e547-157">Windows PowerShell을 사용 하 여 Office 365를 관리 하는 가장 좋은 방법</span><span class="sxs-lookup"><span data-stu-id="9e547-157">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="9e547-158">Windows PowerShell에는 한 번에 여러 사용자의 설정을 변경 하는 경우와 같이 Microsoft 365 관리 센터를 사용 하는 경우에만 속도, 단순성, 생산성 등 다양 한 이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e547-158">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center, such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="9e547-159">다음 항목에서 이러한 이점에 대해 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="9e547-159">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="9e547-160">Windows PowerShell 및 Lync Online 소개</span><span class="sxs-lookup"><span data-stu-id="9e547-160">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="9e547-161">Windows PowerShell을 사용 하 여 비즈니스용 Skype Online 관리</span><span class="sxs-lookup"><span data-stu-id="9e547-161">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="9e547-162">Windows PowerShell을 사용 하 여 일반적인 비즈니스용 Skype Online 관리 작업 수행</span><span class="sxs-lookup"><span data-stu-id="9e547-162">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="9e547-163">비즈니스용 Skype Online 용 Windows PowerShell 모듈을 사용 하면 비즈니스용 Skype Online에 연결 하는 원격 Windows PowerShell 세션을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e547-163">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span> <span data-ttu-id="9e547-164">이 모듈은 64 비트 컴퓨터 에서만 지원 되며 비즈니스용 [Skype Online 용 Windows PowerShell 모듈](https://go.microsoft.com/fwlink/?LinkId=294688) 의 Microsoft 다운로드 센터에서 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e547-164">This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="9e547-165">관련 주제</span><span class="sxs-lookup"><span data-stu-id="9e547-165">Related topics</span></span>

[<span data-ttu-id="9e547-166">Microsoft 팀을 위한 오디오 회의 설정</span><span class="sxs-lookup"><span data-stu-id="9e547-166">Set up Audio Conferencing for Microsoft Teams</span></span>](set-up-audio-conferencing-in-teams.md)

[<span data-ttu-id="9e547-167">비즈니스용 Skype Online에 대 한 오디오 회의 설정</span><span class="sxs-lookup"><span data-stu-id="9e547-167">Set up Audio Conferencing for Skype for Business Online</span></span>](/skypeforbusiness/audio-conferencing-in-office-365/set-up-audio-conferencing)
