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
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- ms.teamsadmincenter.audioconferencing.bridgesettings
- seo-marvel-mar2020
description: 진입 및 종료 알림을 포함하여 오디오 회의 브리지 설정을 변경하고, 이름 또는 전화 번호, 음색을 재생하고, 발신자에 이름을 기록하라는 프롬프트를 선택합니다.
ms.openlocfilehash: 7609ac7639012eb29d6d6cab4b482c1502d27c51
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51102645"
---
# <a name="change-the-settings-for-an-audio-conferencing-bridge"></a><span data-ttu-id="9c7a3-103">오디오 회의 브리지의 설정 변경</span><span class="sxs-lookup"><span data-stu-id="9c7a3-103">Change the settings for an Audio Conferencing bridge</span></span>

<span data-ttu-id="9c7a3-104">오디오 회의 또는 Microsoft 365 Office 365 설정하면 오디오 회의 브리지라는 사용자에 대한 전화 번호가 수신됩니다.</span><span class="sxs-lookup"><span data-stu-id="9c7a3-104">When you are setting up Audio Conferencing in Microsoft 365 or Office 365, you will receive phone numbers for your users from what is called an audio conferencing bridge.</span></span> <span data-ttu-id="9c7a3-105">회의 브리지에는 하나 이상의 전화 번호가 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c7a3-105">A conferencing bridge can contain one or more phone numbers.</span></span> <span data-ttu-id="9c7a3-106">이러한 전화 번호는 발신자들이 모임에 전화 접속할 때 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="9c7a3-106">These phone numbers are used when callers dial in to a meeting.</span></span> <span data-ttu-id="9c7a3-107">전화 번호는 모임 초대의 비즈니스용 Skype Microsoft Teams 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="9c7a3-107">The phone number is included at the bottom of the Skype for Business or Microsoft Teams meeting invite.</span></span>
  
<span data-ttu-id="9c7a3-108">회의 브리지는 통화에 응답하고 모임 자동 참석을 사용하여 음성 프롬프트를 발신자에게 묻는 메시지를 표시한 다음, 설정에 따라 알림을 재생하고 발신자들에게 이름을 기록하고 PIN 설정을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c7a3-108">The conferencing bridge answers a call and prompts the caller with voice prompts using a meeting auto attendant, and then, depending on your settings, it can play notifications, ask callers to record their name, and control the PIN settings.</span></span> <span data-ttu-id="9c7a3-109">PINS는 모임 이끌이가 앱을 사용하지 않을 때 모임을 시작할 비즈니스용 Skype Microsoft Teams 부여됩니다.</span><span class="sxs-lookup"><span data-stu-id="9c7a3-109">PINs are given to meeting organizers to allow them to start a meeting when they are aren't using a Skype for Business or Microsoft Teams app.</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="9c7a3-110">PIN은 앱 사용자가 모임을 비즈니스용 Skype Microsoft Teams 경우 모임 이끌이에게만 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="9c7a3-110">A PIN is only required for the meeting organizer when a Skype for Business or Microsoft Teams app user hasn't already started the meeting.</span></span> <span data-ttu-id="9c7a3-111">모든 사용자가 모임에 전화 접속하는 경우 모임 이끌이가 모임을 시작하려면 PIN이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="9c7a3-111">If everyone is dialing in to the meeting, the PIN is required for the meeting organizer to start the meeting.</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="an-icon-showing-the-microsoft-teams-logo-using-the-microsoft-teams-admin-center"></a>![Microsoft Teams 로고를 보여주는 아이콘](media/teams-logo-30x30.png) <span data-ttu-id="9c7a3-113">Microsoft Teams 관리 센터 사용</span><span class="sxs-lookup"><span data-stu-id="9c7a3-113">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="9c7a3-114">왼쪽 탐색에서 모임 회의  >  **브리지로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="9c7a3-114">In the left navigation, go to **Meetings** > **Conference bridges**.</span></span> 

2. <span data-ttu-id="9c7a3-115">컨퍼런스 브리지  페이지의 맨 위에 있는 브리지 설정을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="9c7a3-115">At the top of the **Conference bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="9c7a3-116">브리지 **설정 창에서** 다음을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9c7a3-116">In the **Bridge settings** pane, select:</span></span> 
   - <span data-ttu-id="9c7a3-117">**모임 항목 및 종료 알림** 이 기능을 해제하면 모임에 이미 참가한 사용자는 다른 사용자가 모임에 참가하거나 나가는 경우 알림을 들을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9c7a3-117">**Meeting entry and exit notifications** If you turn this off, users who have already joined the meeting won't be notified when someone enters or leaves the meeting.</span></span>
    
     <span data-ttu-id="9c7a3-118">모임 항목 **및** 종료 알림을 켜면 다음 옵션을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c7a3-118">When you turn on **Meeting entry and exit notifications**, you can select these options:</span></span>
    
   - <span data-ttu-id="9c7a3-119">**이름 또는 전화 번호** 사용자가 모임에 전화 접속하면 참가할 때 해당 전화 번호가 재생됩니다.</span><span class="sxs-lookup"><span data-stu-id="9c7a3-119">**Names or phone numbers** When users dial in to a meeting, their phone number will be played when they join it.</span></span>
    
   - <span data-ttu-id="9c7a3-120">**톤** 사용자가 모임에 전화 접속하면 모임에 참가할 때 오디오 톤이 재생됩니다.</span><span class="sxs-lookup"><span data-stu-id="9c7a3-120">**Tones** When users dial in to a meeting, an audio tone will be played when they join it.</span></span>
      
   - <span data-ttu-id="9c7a3-121">모임에 참가하기 전에 발신자들에게 이름을 **기록해달라고 요청합니다.** 이 기능을 해제하면 호출자는 모임에 참가하기 전에 이름을 기록할지 묻는 요청이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9c7a3-121">**Ask callers to record their name before joining the meeting** If you turn this off, callers won't be asked to record their name before they join a meeting.</span></span>

4. <span data-ttu-id="9c7a3-122">모임에 대한 PIN 길이를 설정하려면 PIN 길이 목록에서 PIN에 대해 원하는 숫자 수를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="9c7a3-122">To set the PIN length for meetings, select the number of digits you want for the PIN in the **PIN length** list.</span></span>

5. <span data-ttu-id="9c7a3-123">사용자에게 전자 메일을 보낼지 여부를 지정하려면 오디오 회의 구성이 변경될 경우 사용자에게 자동으로 전자 메일 보내기 를 사용하도록 설정하거나 사용하지 **않도록 설정합니다.**</span><span class="sxs-lookup"><span data-stu-id="9c7a3-123">To specify whether to send email to your users, enable or disable **Automatically send emails to users if their audio conferencing configuration changes**.</span></span>
    <span data-ttu-id="9c7a3-124">자세한 [](emails-sent-to-users-when-their-settings-change-in-teams.md) 내용은 오디오 회의 설정이 사용자에 Microsoft Teams 설정이 변경될 때 [](/SkypeForBusiness/audio-conferencing-in-office-365/emails-sent-to-users-when-their-settings-change) 사용자에게 자동으로 전송되는 전자 비즈니스용 Skype 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9c7a3-124">See [Emails automatically sent to users when their Audio Conferencing settings change in Microsoft Teams](emails-sent-to-users-when-their-settings-change-in-teams.md) or [Emails sent to users when their settings change in Skype for Business Online](/SkypeForBusiness/audio-conferencing-in-office-365/emails-sent-to-users-when-their-settings-change) for more information.</span></span>
 
6. <span data-ttu-id="9c7a3-125">**저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9c7a3-125">Click **Save**.</span></span> 

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="9c7a3-126">사용자와 함께 관리하는 방법을 알고 Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="9c7a3-126">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="9c7a3-127">시간을 절약하거나 이 프로세스를 자동화하기 위해 [Set-CsDialinConferencingBridge](/powershell/module/skype/Set-CsOnlineDialInConferencingBridge) cmdlet을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c7a3-127">To save time or automate this process, you can use the [Set-CsDialinConferencingBridge](/powershell/module/skype/Set-CsOnlineDialInConferencingBridge) cmdlet.</span></span>
    
- <span data-ttu-id="9c7a3-128">Windows PowerShell 모든 것은 사용자 관리와 사용자가 허용되거나 허용되지 않는 작업을 관리하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="9c7a3-128">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="9c7a3-129">이 Windows PowerShell 여러 작업을 수행할 때 일상적인 작업을 단순화할 수 Microsoft 365 Office 365 관리 지점을 사용하여 관리 또는 관리 작업을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c7a3-129">With Windows PowerShell, you can manage Microsoft 365 or Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="9c7a3-130">다음 항목을 Windows PowerShell 다음 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9c7a3-130">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="9c7a3-131">PowerShell을 Office 365 이유</span><span class="sxs-lookup"><span data-stu-id="9c7a3-131">Why you need to use Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - <span data-ttu-id="9c7a3-132">[사용자와 함께 Microsoft 365 또는 Office 365 가장 Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="9c7a3-132">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
- <span data-ttu-id="9c7a3-133">Windows PowerShell 많은 사용자에 대한 설정을 한 Microsoft 365 경우와 같이 관리 센터를 사용하는 것만 사용하는 것 이상으로 속도, 단순성 및 생산성에 많은 이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c7a3-133">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center, such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="9c7a3-134">다음 항목에서 이러한 이점에 대해 자세히 알아보습니다.</span><span class="sxs-lookup"><span data-stu-id="9c7a3-134">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="9c7a3-135">Windows PowerShell 및 비즈니스용 Skype Online 소개</span><span class="sxs-lookup"><span data-stu-id="9c7a3-135">An introduction to Windows PowerShell and Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
  - [<span data-ttu-id="9c7a3-136">온라인 Windows PowerShell 관리하기 위해 비즈니스용 Skype 사용</span><span class="sxs-lookup"><span data-stu-id="9c7a3-136">Using Windows PowerShell to manage Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
  - [<span data-ttu-id="9c7a3-137">일반적인 Windows PowerShell 관리 작업을 수행하는 데 비즈니스용 Skype 사용</span><span class="sxs-lookup"><span data-stu-id="9c7a3-137">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
    > [!NOTE]
    > <span data-ttu-id="9c7a3-138">Windows PowerShell 온라인용 비즈니스용 Skype 모듈을 사용하면 온라인에 연결하는 원격 Windows PowerShell 세션을 만들 비즈니스용 Skype 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c7a3-138">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span> <span data-ttu-id="9c7a3-139">64비트 컴퓨터에서만 지원되는 이 모듈은 온라인용 Microsoft 다운로드 센터에서 Windows PowerShell 다운로드할 [비즈니스용 Skype 있습니다.](https://go.microsoft.com/fwlink/?LinkId=294688)</span><span class="sxs-lookup"><span data-stu-id="9c7a3-139">This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="9c7a3-140">관련 항목</span><span class="sxs-lookup"><span data-stu-id="9c7a3-140">Related topics</span></span>

[<span data-ttu-id="9c7a3-141">Microsoft Teams용 오디오 회의 설정하기</span><span class="sxs-lookup"><span data-stu-id="9c7a3-141">Set up Audio Conferencing for Microsoft Teams</span></span>](set-up-audio-conferencing-in-teams.md)

[<span data-ttu-id="9c7a3-142">온라인용 오디오 회의 비즈니스용 Skype 설정</span><span class="sxs-lookup"><span data-stu-id="9c7a3-142">Set up Audio Conferencing for Skype for Business Online</span></span>](/skypeforbusiness/audio-conferencing-in-office-365/set-up-audio-conferencing)