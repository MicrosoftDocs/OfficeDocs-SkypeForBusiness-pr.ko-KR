---
title: 휴대폰에서 PIN 없이 오디오 회의를 Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: d5b1f775-d7ed-4d30-853a-1d49f81e8fde
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: '익명 호출자들이 관리자 센터에서 모임에 참가하지 않도록 설정하거나 사용하지 않도록 설정하는 Teams 대해 자세히 알아보습니다. '
ms.openlocfilehash: 520bf720a01a686a103748cdbbf26cb8426e94f2
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51116966"
---
# <a name="start-an-audio-conference-over-the-phone-without-a-pin-in-microsoft-teams"></a><span data-ttu-id="babc8-103">휴대폰에서 PIN 없이 오디오 회의를 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="babc8-103">Start an Audio Conference over the phone without a PIN in Microsoft Teams</span></span>

<span data-ttu-id="babc8-104">모임 이끌이가 모임을 시작하지 않은 경우 모임의 로비에서 음악이 들리는 모임에 Microsoft Teams 사용자가 좌절할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="babc8-104">It might be frustrating for users who dial in to a meeting to be held in the meeting's lobby listening to music because the Microsoft Teams meeting organizer hasn't started the meeting.</span></span> 
  
<span data-ttu-id="babc8-105">모임 이끌이가 모임에 호출하는 경우 기본적으로 모임을 시작하려면 PIN이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="babc8-105">If a meeting organizer calls in to the meeting, by default, a PIN is required to start a meeting.</span></span> <span data-ttu-id="babc8-106">누구나 모임에 전화 접속할 수 있으며 PIN이 모임을 시작하라는 메시지가 표시되지 않을 수 있도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="babc8-106">You can set it up so that anyone can dial in to a meeting and not be prompted for a PIN to start the meeting.</span></span> <span data-ttu-id="babc8-107">관리 센터를 사용하여 단일 사용자에 대해 이 설정을 사용하도록 설정하거나 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="babc8-107">You can use the admin center to enable or disable this setting for a single user.</span></span>
  
<span data-ttu-id="babc8-108">다른 사용자가 앱에서 모임을 시작한 경우 모임 이끌이에 PIN이 Microsoft Teams 없습니다.</span><span class="sxs-lookup"><span data-stu-id="babc8-108">A PIN isn't required for the meeting organizer if someone has started the meeting from the Microsoft Teams app.</span></span> <span data-ttu-id="babc8-109">PIN은 모임 이끌이가 휴대폰을 통해 모임에 참가할 때만 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="babc8-109">A PIN is only required when a meeting organizer joins their meeting over a phone.</span></span> <span data-ttu-id="babc8-110">모임에 대한 PIN은 오디오 회의 라이선스가 할당되어 오디오 회의에 사용할 수 있는 경우 오디오 사용자에게 전송됩니다. </span><span class="sxs-lookup"><span data-stu-id="babc8-110">The PIN for meetings is sent to the audio user when they are assigned the **Audio Conferencing** license and are enabled for Audio Conferencing.</span></span> <span data-ttu-id="babc8-111">오디오 [회의](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md) 설정이 변경될 때 사용자에게 자동으로 전송되는 오디오 회의 정보 및 전자 메일이 있는 사용자에게 전자 메일 보내기 를 [참조하세요.](emails-sent-to-users-when-their-settings-change-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="babc8-111">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md) and [Emails that are automatically sent to users when their Audio Conferencing settings change](emails-sent-to-users-when-their-settings-change-in-teams.md).</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="enable-or-disable-anonymous-callers-from-joining-a-meeting"></a><span data-ttu-id="babc8-112">익명 호출자 모임에 참가하지 않도록 설정하거나 사용하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="babc8-112">Enable or disable anonymous callers from joining a meeting</span></span>

<span data-ttu-id="babc8-113">![Microsoft Teams 로고를 나타내는 아이콘](media/teams-logo-30x30.png) **Microsoft Teams 관리 센터 사용**</span><span class="sxs-lookup"><span data-stu-id="babc8-113">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="babc8-114">왼쪽 탐색에서 사용자 를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="babc8-114">In the left navigation, click **Users**.</span></span> 

2. <span data-ttu-id="babc8-115">목록에서 사용자를 선택한 다음 페이지 맨 위에 **있는** 편집을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="babc8-115">Select a user in the list, and then click **Edit** at the top of the page.</span></span> 

3. <span data-ttu-id="babc8-116">오디오 **회의** 옆에 있는 편집을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="babc8-116">Next to **Audio Conferencing**, click **Edit**.</span></span>

4. <span data-ttu-id="babc8-117">오디오 **회의** 창에서 전화 접속 호출을 사용하도록 설정하거나 사용하지 않도록 설정하면 모임의 첫 번째 사용자가 될 **수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="babc8-117">In the **Audio Conferencing** pane, enable or disable **Dial-in callers can be the first person in a meeting**.</span></span>
    
4. <span data-ttu-id="babc8-118">적용 **을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="babc8-118">Click **Apply**.</span></span> 

<span data-ttu-id="babc8-119">**Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="babc8-119">**Using Windows PowerShell**</span></span>
  
<span data-ttu-id="babc8-120">자세한 [내용은 Microsoft Teams PowerShell 참조를](/powershell/module/teams/?view=teams-ps) 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="babc8-120">See the [Microsoft Teams PowerShell reference](/powershell/module/teams/?view=teams-ps) for more information.</span></span>

## <a name="what-else-should-you-know"></a><span data-ttu-id="babc8-121">또 어떤 것을 알아야 하나요?</span><span class="sxs-lookup"><span data-stu-id="babc8-121">What else should you know?</span></span>

- <span data-ttu-id="babc8-122">PIN을 다시 설정하려는 경우 오디오 회의 [PIN 재설정을 참조합니다.](reset-the-audio-conferencing-pin-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="babc8-122">If you want to reset the PIN, see [Reset the Audio Conferencing PIN](reset-the-audio-conferencing-pin-in-teams.md).</span></span>
    
- <span data-ttu-id="babc8-123">익명 액세스 또는 모임 시작에 PIN이 필요 없는 경우 다음을 사용하지 않도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="babc8-123">If anonymous access, or not requiring a PIN to start a meeting, is disabled:</span></span>
    
  - <span data-ttu-id="babc8-124">모임이 시작되지 않은 경우(모임에 아직 아무도 없습니다. 이끌이인 경우 발신자가 묻는 메시지가 표시됨). 예를 말하면 PIN에 대한 메시지가 표시될 것이고 PIN을 입력하면 모임이 시작하고 사용자가 모임에 참가합니다.</span><span class="sxs-lookup"><span data-stu-id="babc8-124">If the meeting hasn't started (there's no one in the meeting yet): A caller will be prompted if he's the organizer; if he says yes, he'll be prompted for his PIN, and after he inputs the PIN, the meeting will start and the user will join the meeting.</span></span>
    
  - <span data-ttu-id="babc8-125">모임이 이미 시작된 경우(다른 사람이 모임에 이미 있는 경우): 주최자인 경우 발신자가 묻는 메시지가 표시되지 않습니다. PIN에 대한 메시지가 표시되지 않습니다. 모임이 이미 시작되어 호출자는 모임에 참가합니다.</span><span class="sxs-lookup"><span data-stu-id="babc8-125">If the meeting already started (someone else is already in the meeting): A caller won't be prompted if he's the organizer and he'll never be prompted for the PIN; the meeting is already started, and the caller will join it.</span></span>
    
- <span data-ttu-id="babc8-126">익명 액세스 또는 모임 시작에 PIN이 필요 없는 경우 다음을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="babc8-126">If anonymous access, or not requiring a PIN to start a meeting, is enabled:</span></span>
    
  - <span data-ttu-id="babc8-127">모임을 시작하지 않은 경우(아직 모임에 참석하지 않은 경우): 주최자인 경우 발신자가 묻는 메시지가 표시되지 않고 PIN에 대한 메시지가 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="babc8-127">If the meeting hasn't started (there's no one in the meeting yet): A caller won't be prompted if she's the organizer, and she'll never be prompted for the PIN.</span></span> <span data-ttu-id="babc8-128">이끌이의 설정이 해제로 설정되어 있기 때문에 모임이 시작되어 익명 호출자가 모임에 참가합니다.</span><span class="sxs-lookup"><span data-stu-id="babc8-128">Because the setting of the organizer is set to off, the meeting will start and the anonymous callers will join the meeting.</span></span>
    
  - <span data-ttu-id="babc8-129">모임이 이미 시작된 경우(다른 사람이 모임에 이미 있는 경우): 주최자인 경우 발신자가 묻는 메시지가 표시되지 않습니다. PIN에 대한 메시지가 표시되지 않습니다. 모임이 이미 시작되어 발신자가 참가합니다.</span><span class="sxs-lookup"><span data-stu-id="babc8-129">If the meeting already started (someone else is already in the meeting): A caller won't be prompted if she's the organizer, and she'll never be prompted for the PIN,;the meeting is already started, and the caller will join it.</span></span>
    
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="babc8-130">자세한 정보를 Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="babc8-130">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="babc8-131">Windows PowerShell 모든 것은 사용자 관리와 사용자가 허용되거나 허용되지 않는 작업을 관리하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="babc8-131">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="babc8-132">이 Windows PowerShell 여러 작업을 수행할 때 일상적인 작업을 단순화할 수 Microsoft 365 Office 365 관리 지점을 사용하여 관리 또는 관리 작업을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="babc8-132">With Windows PowerShell, you can manage Microsoft 365 or Office 365 by using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="babc8-133">다음 항목을 Windows PowerShell 다음 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="babc8-133">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="babc8-134">PowerShell을 Office 365 이유</span><span class="sxs-lookup"><span data-stu-id="babc8-134">Why you need to use Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - <span data-ttu-id="babc8-135">[사용자와 함께 Microsoft 365 또는 Office 365 가장 Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="babc8-135">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
<span data-ttu-id="babc8-136">자세한 내용은 Windows PowerShell [PowerShell](/powershell/module/teams/?view=teams-ps) Microsoft Teams 참조를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="babc8-136">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="babc8-137">관련 항목</span><span class="sxs-lookup"><span data-stu-id="babc8-137">Related topics</span></span>

[<span data-ttu-id="babc8-138">오디오 회의를 시도하거나 Microsoft 365 또는 Office 365</span><span class="sxs-lookup"><span data-stu-id="babc8-138">Try or purchase Audio Conferencing in Microsoft 365 or Office 365</span></span>](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)