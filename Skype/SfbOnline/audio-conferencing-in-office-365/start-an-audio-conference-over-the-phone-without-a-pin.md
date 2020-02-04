---
title: 비즈니스용 Skype Online에서 PIN 없이 전화를 통해 음성 회의 시작
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: d5b1f775-d7ed-4d30-853a-1d49f81e8fde
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
description: '비즈니스용 Skype 관리 센터에서 또는 PowerShell 스크립트를 사용 하 여 익명 호출자가 모임에 참가 하는 것을 허용 하거나 사용 하지 않도록 설정 하는 방법에 대해 알아봅니다. '
ms.openlocfilehash: e2cb4fc543f92bd4dc5c2a16a1fb7e10f65e0660
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41680345"
---
# <a name="start-an-audio-conference-over-the-phone-without-a-pin-in-skype-for-business-online"></a><span data-ttu-id="7649d-103">비즈니스용 Skype Online에서 PIN 없이 전화를 통해 음성 회의 시작</span><span class="sxs-lookup"><span data-stu-id="7649d-103">Start an Audio Conference over the phone without a PIN in Skype for Business Online</span></span>

> [!Note]
> <span data-ttu-id="7649d-104">Microsoft 팀에서 PIN 없이 오디오 회의를 시작 하는 방법에 대 한 자세한 내용은 [Microsoft 팀에서 pin 없이 전화로 오디오 회의 시작](/MicrosoftTeams/start-an-audio-conference-over-the-phone-without-a-pin-in-teams)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7649d-104">For information about starting an Audio Conference without a PIN in Microsoft Teams, see [Start an Audio Conference over the phone without a PIN  in Microsoft Teams](/MicrosoftTeams/start-an-audio-conference-over-the-phone-without-a-pin-in-teams).</span></span>

<span data-ttu-id="7649d-105">비즈니스용 Skype 모임 이끌이가 모임을 시작 하지 않았기 때문에 모임에 전화 접속 하는 사용자가 음악을 듣는 사람에 게이를 유지 하기 어려울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7649d-105">It might be frustrating for users who dial in to a meeting to be held in the meeting's lobby listening to music because the Skype for Business meeting organizer hasn't started the meeting.</span></span> 
  
<span data-ttu-id="7649d-106">모임 이끌이가 모임에 전화를 거는 경우 기본적으로 모임을 시작 하려면 PIN이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="7649d-106">If a meeting organizer calls in to the meeting, by default, a PIN is required to start a meeting.</span></span> <span data-ttu-id="7649d-107">다른 사용자가 모임에 전화를 걸 수 있도록 설정할 수 있으며 모임 시작을 위해 PIN을 묻지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7649d-107">You can set it up so that anyone can dial in to a meeting and not be prompted for a PIN to start the meeting.</span></span> <span data-ttu-id="7649d-108">비즈니스용 Skype 관리 센터를 사용 하 여 단일 사용자에 대해이 설정을 사용 하거나 사용 하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7649d-108">You can use the Skype for Business admin center to enable or disable this setting for a single user.</span></span>
  
<span data-ttu-id="7649d-109">다른 사용자가 비즈니스용 Skype 앱에서 모임을 시작 했다면 모임 이끌이에게는 PIN이 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7649d-109">A PIN isn't required for the meeting organizer if someone has started the meeting from the Skype for Business app.</span></span> <span data-ttu-id="7649d-110">PIN은 모임 이끌이가 휴대폰을 통해 모임에 참가 하는 경우에만 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="7649d-110">A PIN is only required when a meeting organizer joins their meeting over a phone.</span></span> <span data-ttu-id="7649d-111">모임에 대 한 PIN은 오디오 **회의** 라이선스를 할당 하 고 오디오 회의를 사용할 수 있는 경우 오디오 사용자에 게 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7649d-111">The PIN for meetings is sent to the audio user when they are assigned the **Audio Conferencing** license and are enabled for Audio Conferencing.</span></span> <span data-ttu-id="7649d-112">음성 회의 [설정이 변경 될 때 자동으로 사용자에 게 전송 되는](emails-sent-to-users-when-their-settings-change.md) [전자 메일을 사용자에 게 오디오 회의 정보](send-an-email-to-a-user-with-their-dial-in-information.md) 및 메일로 보내기를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7649d-112">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md) and [Emails that are automatically sent to users when their Audio Conferencing settings change](emails-sent-to-users-when-their-settings-change.md).</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="enable-or-disable-anonymous-callers-from-joining-a-meeting"></a><span data-ttu-id="7649d-113">익명 호출자가 모임에 참가 하지 못하도록 설정 또는 해제</span><span class="sxs-lookup"><span data-stu-id="7649d-113">Enable or disable anonymous callers from joining a meeting</span></span>
    
1. <span data-ttu-id="7649d-114">**비즈니스용 Skype 관리 센터**의 왼쪽 탐색 창에서 **오디오 회의** > **사용자**로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="7649d-114">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Users**.</span></span> 
    
2. <span data-ttu-id="7649d-115">목록에서 사용자를 선택 하 고 작업 창에서 **편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="7649d-115">In the list, select the user and in the Action pane click **Edit**.</span></span> 
    
3. <span data-ttu-id="7649d-116">사용자의 속성 페이지에 있는 **모임 옵션**에서 **인증 되지 않은 발신자가 모임에서 첫 번째 사용자가 되도록 허용을 선택 하거나 선택을 취소 합니다. 그렇지 않은 경우에는 인증 된 사용자가 참가할 때까지 대기실에서 대기**합니다.</span><span class="sxs-lookup"><span data-stu-id="7649d-116">On the user's properties page, under **Meeting options**, select or clear **Allow unauthenticated callers to be the first people in a meeting. If not, then they will wait in the lobby until an authenticated user joins**.</span></span>
    
4. <span data-ttu-id="7649d-117">**저장**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="7649d-117">Click **Save**.</span></span> 


    
 <span data-ttu-id="7649d-118">**Windows Powershell 사용**</span><span class="sxs-lookup"><span data-stu-id="7649d-118">**Using Windows Powershell**</span></span>
  
- <span data-ttu-id="7649d-119">다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="7649d-119">Run the following:</span></span> 
    
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -AllowPSTNOnlyMeetingsByDefault $true | $false
  ```

## <a name="what-else-should-you-know"></a><span data-ttu-id="7649d-120">알아야 할 기타 사항</span><span class="sxs-lookup"><span data-stu-id="7649d-120">What else should you know?</span></span>

- <span data-ttu-id="7649d-121">PIN을 다시 설정 하려면 [오디오 회의 PIN 다시 설정을](reset-the-audio-conferencing-pin.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7649d-121">If you want to reset the PIN, see [Reset the Audio Conferencing PIN](reset-the-audio-conferencing-pin.md).</span></span>
    
- <span data-ttu-id="7649d-122">익명 액세스 또는 모임을 시작 하기 위해 PIN이 필요 하지 않은 경우 사용 하지 않도록 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7649d-122">If anonymous access, or not requiring a PIN to start a meeting, is disabled:</span></span>
    
  - <span data-ttu-id="7649d-123">모임이 시작 되지 않은 경우 (모임에 아무도 없음) 다음을 수행 하는 경우 호출자에 게 해당 사람이 이끌이 인지 묻는 메시지가 표시 됩니다. 예, pin을 입력 하 라는 메시지가 표시 되 면, 모임이 시작 되 고 사용자가 모임에 참가 합니다.</span><span class="sxs-lookup"><span data-stu-id="7649d-123">If the meeting hasn't started (there's no one in the meeting yet): A caller will be prompted if he's the organizer; if he says yes, he'll be prompted for his PIN, and after he inputs the PIN, the meeting will start and the user will join the meeting.</span></span>
    
  - <span data-ttu-id="7649d-124">모임이 이미 시작 된 경우 (다른 사람이 이미 모임에 참가 한 경우): 주최자가 이끌이이 고 PIN을 입력 하 라는 메시지가 표시 되지 않으면 발신자에 게 메시지가 표시 되지 않습니다. 모임이 이미 시작 되었으며 호출자가 참가 하 게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7649d-124">If the meeting already started (someone else is already in the meeting): A caller won't be prompted if he's the organizer and he'll never be prompted for the PIN; the meeting is already started, and the caller will join it.</span></span>
    
- <span data-ttu-id="7649d-125">익명 액세스 또는 모임을 시작 하기 위해 PIN이 필요 하지 않은 경우 다음을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="7649d-125">If anonymous access, or not requiring a PIN to start a meeting, is enabled:</span></span>
    
  - <span data-ttu-id="7649d-126">모임이 시작 되지 않은 경우 (모임에 아무도 없음) 다음을 수행 하 라는 메시지가 표시 되지 않습니다. 주최자는 이끌이이 고 PIN을 입력 하 라는 메시지가 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7649d-126">If the meeting hasn't started (there's no one in the meeting yet): A caller won't be prompted if she's the organizer, and she'll never be prompted for the PIN.</span></span> <span data-ttu-id="7649d-127">이끌이의 설정이 off로 설정 되어 있으므로 모임이 시작 되 고 익명 발신자가 모임에 참가 합니다.</span><span class="sxs-lookup"><span data-stu-id="7649d-127">Because the setting of the organizer is set to off, the meeting will start and the anonymous callers will join the meeting.</span></span>
    
  - <span data-ttu-id="7649d-128">모임이 이미 시작 된 경우 (다른 사람이 이미 모임에 속해 있는 경우), 발신자에 게 메시지가 표시 되지 않으며, PIN을 입력 하 라는 메시지가 표시 되지 않으며, 모임이 이미 시작 되어 발신자가 참여 하 게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7649d-128">If the meeting already started (someone else is already in the meeting): A caller won't be prompted if she's the organizer, and she'll never be prompted for the PIN,;the meeting is already started, and the caller will join it.</span></span>
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="7649d-129">Windows PowerShell을 사용 하 여 관리 하는 방법을 알고 싶으세요?</span><span class="sxs-lookup"><span data-stu-id="7649d-129">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="7649d-130">여러 사용자에 대해 시간을 절약 하거나이 작업을 자동화 하려면 [get-csonlinedialinconferencinguser](https://go.microsoft.com/fwlink/?LinkId=617688 ) cmdlet을 사용 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7649d-130">To save time or automate this for more than one user, you can use the [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) cmdlet.</span></span>
    
- <span data-ttu-id="7649d-131">Windows PowerShell을 사용할 때 비즈니스용 Skype Online은 사용자 관리와 사용자가 허용 하거나 허용 하지 않는 작업에 대 한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="7649d-131">When it comes to Windows PowerShell, Skype for Business Online is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="7649d-132">Windows PowerShell을 사용 하면 여러 작업을 수행할 때 일상 업무를 단순화할 수 있는 단일 관리 지점을 사용 하 여 Office 365를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7649d-132">With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="7649d-133">Windows PowerShell을 시작 하려면 다음 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7649d-133">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="7649d-134">Office 365 PowerShell을 사용 해야 하는 이유</span><span class="sxs-lookup"><span data-stu-id="7649d-134">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="7649d-135">Windows PowerShell을 사용 하 여 Office 365를 관리 하는 가장 좋은 방법</span><span class="sxs-lookup"><span data-stu-id="7649d-135">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="7649d-136">Windows PowerShell에는 한 번에 여러 사용자의 설정을 변경 하는 경우와 같이 Microsoft 365 관리 센터를 사용 하는 경우에만 속도, 단순성, 생산성 등 다양 한 이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7649d-136">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center, such as when you are making settings changes for many users at one time.</span></span> <span data-ttu-id="7649d-137">다음 항목에서 이러한 이점에 대해 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="7649d-137">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="7649d-138">Windows PowerShell 및 Lync Online 소개</span><span class="sxs-lookup"><span data-stu-id="7649d-138">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [<span data-ttu-id="7649d-139">Windows PowerShell을 사용 하 여 비즈니스용 Skype Online 관리</span><span class="sxs-lookup"><span data-stu-id="7649d-139">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="7649d-140">Windows PowerShell을 사용 하 여 일반적인 비즈니스용 Skype Online 관리 작업 수행</span><span class="sxs-lookup"><span data-stu-id="7649d-140">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="7649d-141">비즈니스용 Skype Online 용 Windows PowerShell 모듈을 사용 하면 비즈니스용 Skype Online에 연결 하는 원격 Windows PowerShell 세션을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7649d-141">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span> <span data-ttu-id="7649d-142">이 모듈은 64 비트 컴퓨터 에서만 지원 되며 비즈니스용 [Skype Online 용 Windows PowerShell 모듈](https://go.microsoft.com/fwlink/?LinkId=294688) 의 Microsoft 다운로드 센터에서 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7649d-142">This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="7649d-143">관련 주제</span><span class="sxs-lookup"><span data-stu-id="7649d-143">Related topics</span></span>

[<span data-ttu-id="7649d-144">Office 365에서 오디오 회의 체험 또는 구매</span><span class="sxs-lookup"><span data-stu-id="7649d-144">Try or purchase Audio Conferencing in Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
