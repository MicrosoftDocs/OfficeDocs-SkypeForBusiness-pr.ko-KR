---
title: 비즈니스용 Skype Online에서 PIN 없이 전화로 오디오 회의 시작
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
description: '비즈니스용 Skype 관리 센터에서 모임에 참가하거나 PowerShell 스크립트를 사용하여 익명 발신자에 가입하지 않도록 설정하거나 사용하지 않도록 설정하는 방법을 배워야 합니다. '
ms.openlocfilehash: f02d458450f07b64f3daf4d23b1c56aa2bb846a3
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2020
ms.locfileid: "44163877"
---
# <a name="start-an-audio-conference-over-the-phone-without-a-pin-in-skype-for-business-online"></a><span data-ttu-id="e1993-103">비즈니스용 Skype Online에서 PIN 없이 전화로 오디오 회의 시작</span><span class="sxs-lookup"><span data-stu-id="e1993-103">Start an Audio Conference over the phone without a PIN in Skype for Business Online</span></span>

> [!Note]
> <span data-ttu-id="e1993-104">Microsoft Teams에서 PIN 없이 오디오 회의를 시작하는 자세한 내용은 Microsoft Teams에서 PIN 없이 전화로 오디오 회의 시작을 [참조하세요.](/MicrosoftTeams/start-an-audio-conference-over-the-phone-without-a-pin-in-teams)</span><span class="sxs-lookup"><span data-stu-id="e1993-104">For information about starting an Audio Conference without a PIN in Microsoft Teams, see [Start an Audio Conference over the phone without a PIN  in Microsoft Teams](/MicrosoftTeams/start-an-audio-conference-over-the-phone-without-a-pin-in-teams).</span></span>

<span data-ttu-id="e1993-105">비즈니스용 Skype 모임 이끌이가 모임을 시작하지 않은 경우 모임에 전화 접속하는 사용자가 모임의 대기실에서 음악을 듣는 데 문제가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1993-105">It might be frustrating for users who dial in to a meeting to be held in the meeting's lobby listening to music because the Skype for Business meeting organizer hasn't started the meeting.</span></span> 
  
<span data-ttu-id="e1993-106">모임 이끌이가 모임에 전화를 걸면 기본적으로 모임을 시작하는 데 PIN이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="e1993-106">If a meeting organizer calls in to the meeting, by default, a PIN is required to start a meeting.</span></span> <span data-ttu-id="e1993-107">누구나 모임에 전화 접속할 수 있도록 설정할 수 있으며 PIN을 사용하여 모임을 시작할지 묻는 메시지가 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e1993-107">You can set it up so that anyone can dial in to a meeting and not be prompted for a PIN to start the meeting.</span></span> <span data-ttu-id="e1993-108">비즈니스용 Skype 관리 센터를 사용하여 단일 사용자에 대해 이 설정을 설정하거나 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1993-108">You can use the Skype for Business admin center to enable or disable this setting for a single user.</span></span>
  
<span data-ttu-id="e1993-109">누군가가 비즈니스용 Skype 앱에서 모임을 시작한 경우 모임 이끌이에게 PIN이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e1993-109">A PIN isn't required for the meeting organizer if someone has started the meeting from the Skype for Business app.</span></span> <span data-ttu-id="e1993-110">PIN은 모임 이끌이가 전화를 통해 모임에 참가할 때만 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="e1993-110">A PIN is only required when a meeting organizer joins their meeting over a phone.</span></span> <span data-ttu-id="e1993-111">모임에 대한 PIN은 오디오 회의 라이선스가 할당되어 오디오 회의를 사용하도록 설정되면 오디오 사용자에게 전송됩니다. </span><span class="sxs-lookup"><span data-stu-id="e1993-111">The PIN for meetings is sent to the audio user when they are assigned the **Audio Conferencing** license and are enabled for Audio Conferencing.</span></span> <span data-ttu-id="e1993-112">오디오 [회의](send-an-email-to-a-user-with-their-dial-in-information.md) 설정이 변경될 때 사용자에게 자동으로 전송되는 오디오 회의 정보와 전자 메일이 있는 전자 메일 보내기를 [참조하세요.](emails-sent-to-users-when-their-settings-change.md)</span><span class="sxs-lookup"><span data-stu-id="e1993-112">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md) and [Emails that are automatically sent to users when their Audio Conferencing settings change](emails-sent-to-users-when-their-settings-change.md).</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="enable-or-disable-anonymous-callers-from-joining-a-meeting"></a><span data-ttu-id="e1993-113">익명 발신자 모임에 참가하지 않도록 설정 또는 해제</span><span class="sxs-lookup"><span data-stu-id="e1993-113">Enable or disable anonymous callers from joining a meeting</span></span>
    
1. <span data-ttu-id="e1993-114">비즈니스용 Skype 관리 **센터의** 왼쪽 탐색 모음에서 오디오 회의 **사용자로**  >  **이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="e1993-114">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Users**.</span></span> 
    
2. <span data-ttu-id="e1993-115">목록에서 사용자를 선택하고 작업 창에서 편집을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="e1993-115">In the list, select the user and in the Action pane click **Edit**.</span></span> 
    
3. <span data-ttu-id="e1993-116">사용자의 속성 페이지의 모임 옵션에서 모임에서 첫 번째 사람이 될 수 있도록 허용을 선택하거나 선택  **취소합니다. 그렇지 않은 경우 인증된** 사용자가 참가할 때까지 대기실에서 대기합니다.</span><span class="sxs-lookup"><span data-stu-id="e1993-116">On the user's properties page, under **Meeting options**, select or clear **Allow unauthenticated callers to be the first people in a meeting. If not, then they will wait in the lobby until an authenticated user joins**.</span></span>
    
4. <span data-ttu-id="e1993-117">**저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e1993-117">Click **Save**.</span></span> 


    
 <span data-ttu-id="e1993-118">**Windows Powershell 사용**</span><span class="sxs-lookup"><span data-stu-id="e1993-118">**Using Windows Powershell**</span></span>
  
- <span data-ttu-id="e1993-119">다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="e1993-119">Run the following:</span></span> 
    
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -AllowPSTNOnlyMeetingsByDefault $true | $false
  ```

## <a name="what-else-should-you-know"></a><span data-ttu-id="e1993-120">알아야 할 다른 것은 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="e1993-120">What else should you know?</span></span>

- <span data-ttu-id="e1993-121">PIN을 다시 설정하려는 경우 오디오 회의 PIN 재설정을 [참조합니다.](reset-the-audio-conferencing-pin.md)</span><span class="sxs-lookup"><span data-stu-id="e1993-121">If you want to reset the PIN, see [Reset the Audio Conferencing PIN](reset-the-audio-conferencing-pin.md).</span></span>
    
- <span data-ttu-id="e1993-122">익명 액세스 또는 모임 시작에 PIN을 요구하지 않는 경우 다음을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e1993-122">If anonymous access, or not requiring a PIN to start a meeting, is disabled:</span></span>
    
  - <span data-ttu-id="e1993-123">모임이 시작되지 않은 경우(아직 모임에 참석하지 않은 경우): 발신자가 이끌이인 경우 발신자가 묻는 메시지가 표시됨 그렇다면 PIN을 입력하라는 메시지가 표시될 것입니다. PIN을 입력하면 모임이 시작하고 사용자가 모임에 참가합니다.</span><span class="sxs-lookup"><span data-stu-id="e1993-123">If the meeting hasn't started (there's no one in the meeting yet): A caller will be prompted if he's the organizer; if he says yes, he'll be prompted for his PIN, and after he inputs the PIN, the meeting will start and the user will join the meeting.</span></span>
    
  - <span data-ttu-id="e1993-124">모임이 이미 시작된 경우(다른 사람이 이미 모임에 있는 경우): 발신자가 이끌이인 경우 발신자에 대한 메시지가 표시되지 않습니다. PIN을 묻는 메시지가 표시되지 않습니다. 모임이 이미 시작되어 발신자도 모임에 참가합니다.</span><span class="sxs-lookup"><span data-stu-id="e1993-124">If the meeting already started (someone else is already in the meeting): A caller won't be prompted if he's the organizer and he'll never be prompted for the PIN; the meeting is already started, and the caller will join it.</span></span>
    
- <span data-ttu-id="e1993-125">익명 액세스 또는 모임 시작에 PIN이 필요 없는 경우 다음을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="e1993-125">If anonymous access, or not requiring a PIN to start a meeting, is enabled:</span></span>
    
  - <span data-ttu-id="e1993-126">모임이 시작되지 않은 경우(아직 모임에 다른 사용자가 없음): 발신자가 이끌이인 경우 발신자에 대한 메시지가 표시되지 않고 PIN을 묻는 메시지가 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e1993-126">If the meeting hasn't started (there's no one in the meeting yet): A caller won't be prompted if she's the organizer, and she'll never be prompted for the PIN.</span></span> <span data-ttu-id="e1993-127">이끌이 설정이 해제되어 있기 때문에 모임이 시작되어 익명 발신자가 모임에 참가합니다.</span><span class="sxs-lookup"><span data-stu-id="e1993-127">Because the setting of the organizer is set to off, the meeting will start and the anonymous callers will join the meeting.</span></span>
    
  - <span data-ttu-id="e1993-128">모임이 이미 시작된 경우(다른 사람이 이미 모임에 있는 경우): 발신자가 이끌이인 경우 발신자에 대한 메시지가 표시되지 않습니다. PIN을 묻는 메시지가 표시되지 않습니다. 모임이 이미 시작되어 발신자가 모임에 참가합니다.</span><span class="sxs-lookup"><span data-stu-id="e1993-128">If the meeting already started (someone else is already in the meeting): A caller won't be prompted if she's the organizer, and she'll never be prompted for the PIN,;the meeting is already started, and the caller will join it.</span></span>
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="e1993-129">사용자 계정으로 관리하는 방법을 알고 Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="e1993-129">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="e1993-130">시간을 절약하거나 여러 사용자에 대해 이 작업을 자동화하기 위해 [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) cmdlet을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1993-130">To save time or automate this for more than one user, you can use the [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) cmdlet.</span></span>
    
- <span data-ttu-id="e1993-131">비즈니스용 Windows PowerShell Skype Online은 사용자와 사용자가 허용되거나 허용되지 않는 작업을 관리하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="e1993-131">When it comes to Windows PowerShell, Skype for Business Online is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="e1993-132">이 Windows PowerShell 여러 작업을 수행할 때 일상적인 작업을 간소화할 수 있는 단일 관리 지점을 사용하여 Microsoft 365 또는 Office 365를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1993-132">With Windows PowerShell, you can manage Microsoft 365 or Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="e1993-133">다음 항목을 Windows PowerShell 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e1993-133">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="e1993-134">Microsoft 365 또는 Office 365 PowerShell을 사용하는 이유</span><span class="sxs-lookup"><span data-stu-id="e1993-134">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="e1993-135">Microsoft 365 또는 Office 365를 관리하는 가장 좋은 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e1993-135">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="e1993-136">Windows PowerShell Microsoft 365 관리 센터를 사용하는 것 이상으로 속도, 단순성 및 생산성에 많은 이점이 있습니다. 예를 들어 한 번으로 많은 사용자에 대해 설정을 변경할 때도 그렇습니다.</span><span class="sxs-lookup"><span data-stu-id="e1993-136">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center, such as when you are making settings changes for many users at one time.</span></span> <span data-ttu-id="e1993-137">다음 항목에서 이러한 이점에 대해 자세히 배워야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1993-137">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="e1993-138">Windows PowerShell 및 Lync Online 소개</span><span class="sxs-lookup"><span data-stu-id="e1993-138">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [<span data-ttu-id="e1993-139">비즈니스 Windows PowerShell 사용하여 비즈니스용 Skype Online 관리</span><span class="sxs-lookup"><span data-stu-id="e1993-139">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="e1993-140">비즈니스용 Windows PowerShell Skype Online 관리 작업을 수행하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1993-140">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="e1993-141">비즈니스 Windows PowerShell용 Skype Online 모듈을 사용하면 비즈니스용 Skype Online에 Windows PowerShell 원격 세션을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1993-141">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span> <span data-ttu-id="e1993-142">64비트 컴퓨터에서만 지원되는 이 모듈은 비즈니스용 Skype Online용 Windows PowerShell 모듈의 Microsoft 다운로드 센터에서 [다운로드할 수 있습니다.](https://go.microsoft.com/fwlink/?LinkId=294688)</span><span class="sxs-lookup"><span data-stu-id="e1993-142">This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="e1993-143">관련 항목</span><span class="sxs-lookup"><span data-stu-id="e1993-143">Related topics</span></span>

[<span data-ttu-id="e1993-144">Microsoft 365 또는 Office 365에서 오디오 회의 시도 또는 구매</span><span class="sxs-lookup"><span data-stu-id="e1993-144">Try or purchase Audio Conferencing in Microsoft 365 or Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
