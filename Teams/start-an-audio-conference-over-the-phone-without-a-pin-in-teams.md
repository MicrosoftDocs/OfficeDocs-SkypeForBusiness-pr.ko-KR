---
title: 팀에서 PIN을 사용 하지 않고 휴대폰으로 오디오 회의 시작
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
description: '팀 관리 센터에서 익명 호출자가 모임에 참가 하지 않도록 설정 하는 방법에 대해 알아봅니다. '
ms.openlocfilehash: e6e3244a3b2135023d80b9b0df925cc5293244f6
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/03/2020
ms.locfileid: "43140831"
---
# <a name="start-an-audio-conference-over-the-phone-without-a-pin-in-microsoft-teams"></a><span data-ttu-id="196c0-103">Microsoft 팀에서 PIN을 사용 하지 않고 전화로 오디오 회의 시작</span><span class="sxs-lookup"><span data-stu-id="196c0-103">Start an Audio Conference over the phone without a PIN in Microsoft Teams</span></span>

<span data-ttu-id="196c0-104">Microsoft 팀 모임 이끌이가 모임을 시작 하지 않았기 때문에 모임에 전화 접속 하는 사용자가 음악에 대 한 모임 로비에 보관 되는 것은 어려울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="196c0-104">It might be frustrating for users who dial in to a meeting to be held in the meeting's lobby listening to music because the Microsoft Teams meeting organizer hasn't started the meeting.</span></span> 
  
<span data-ttu-id="196c0-105">모임 이끌이가 모임에 전화를 거는 경우 기본적으로 모임을 시작 하려면 PIN이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="196c0-105">If a meeting organizer calls in to the meeting, by default, a PIN is required to start a meeting.</span></span> <span data-ttu-id="196c0-106">다른 사용자가 모임에 전화를 걸 수 있도록 설정할 수 있으며 모임 시작을 위해 PIN을 묻지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="196c0-106">You can set it up so that anyone can dial in to a meeting and not be prompted for a PIN to start the meeting.</span></span> <span data-ttu-id="196c0-107">관리 센터를 사용 하 여 단일 사용자에 대해이 설정을 사용 하거나 사용 하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="196c0-107">You can use the admin center to enable or disable this setting for a single user.</span></span>
  
<span data-ttu-id="196c0-108">다른 사용자가 Microsoft 팀 앱에서 모임을 시작 했다면 모임 이끌이에게는 PIN이 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="196c0-108">A PIN isn't required for the meeting organizer if someone has started the meeting from the Microsoft Teams app.</span></span> <span data-ttu-id="196c0-109">PIN은 모임 이끌이가 휴대폰을 통해 모임에 참가 하는 경우에만 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="196c0-109">A PIN is only required when a meeting organizer joins their meeting over a phone.</span></span> <span data-ttu-id="196c0-110">모임에 대 한 PIN은 오디오 **회의** 라이선스를 할당 하 고 오디오 회의를 사용할 수 있는 경우 오디오 사용자에 게 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="196c0-110">The PIN for meetings is sent to the audio user when they are assigned the **Audio Conferencing** license and are enabled for Audio Conferencing.</span></span> <span data-ttu-id="196c0-111">음성 회의 [설정이 변경 될 때 자동으로 사용자에 게 전송 되는](emails-sent-to-users-when-their-settings-change-in-teams.md) [전자 메일을 사용자에 게 오디오 회의 정보](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md) 및 메일로 보내기를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="196c0-111">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md) and [Emails that are automatically sent to users when their Audio Conferencing settings change](emails-sent-to-users-when-their-settings-change-in-teams.md).</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="enable-or-disable-anonymous-callers-from-joining-a-meeting"></a><span data-ttu-id="196c0-112">익명 호출자가 모임에 참가 하지 못하도록 설정 또는 해제</span><span class="sxs-lookup"><span data-stu-id="196c0-112">Enable or disable anonymous callers from joining a meeting</span></span>

<span data-ttu-id="196c0-113">![Microsoft Teams 로고를 나타내는 아이콘](media/teams-logo-30x30.png) **Microsoft Teams 관리 센터 사용**</span><span class="sxs-lookup"><span data-stu-id="196c0-113">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="196c0-114">왼쪽 탐색 창에서 **사용자**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="196c0-114">In the left navigation, click **Users**.</span></span> 

2. <span data-ttu-id="196c0-115">목록에서 사용자를 선택한 다음, 페이지 맨 위에 있는 **편집** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="196c0-115">Select a user in the list, and then click **Edit** at the top of the page.</span></span> 

3. <span data-ttu-id="196c0-116">**오디오 회의**옆에 있는 **편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="196c0-116">Next to **Audio Conferencing**, click **Edit**.</span></span>

4. <span data-ttu-id="196c0-117">**오디오 회의** 창에서 전화 접속 발신자를 사용 하거나 사용 하지 않도록 설정 하는 **것이 모임에서 첫 번째 사용자가 될 수 있습니다**.</span><span class="sxs-lookup"><span data-stu-id="196c0-117">In the **Audio Conferencing** pane, enable or disable **Dial-in callers can be the first person in a meeting**.</span></span>
    
4. <span data-ttu-id="196c0-118">**적용**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="196c0-118">Click **Apply**.</span></span> 

<span data-ttu-id="196c0-119">**Windows PowerShell 사용**</span><span class="sxs-lookup"><span data-stu-id="196c0-119">**Using Windows PowerShell**</span></span>
  
<span data-ttu-id="196c0-120">자세한 내용은 [Microsoft 팀 PowerShell 참조](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="196c0-120">See the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>

## <a name="what-else-should-you-know"></a><span data-ttu-id="196c0-121">알아야 할 기타 사항</span><span class="sxs-lookup"><span data-stu-id="196c0-121">What else should you know?</span></span>

- <span data-ttu-id="196c0-122">PIN을 다시 설정 하려면 [오디오 회의 PIN 다시 설정을](reset-the-audio-conferencing-pin-in-teams.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="196c0-122">If you want to reset the PIN, see [Reset the Audio Conferencing PIN](reset-the-audio-conferencing-pin-in-teams.md).</span></span>
    
- <span data-ttu-id="196c0-123">익명 액세스 또는 모임을 시작 하기 위해 PIN이 필요 하지 않은 경우 사용 하지 않도록 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="196c0-123">If anonymous access, or not requiring a PIN to start a meeting, is disabled:</span></span>
    
  - <span data-ttu-id="196c0-124">모임이 시작 되지 않은 경우 (모임에 아무도 없음) 다음을 수행 하는 경우 호출자에 게 해당 사람이 이끌이 인지 묻는 메시지가 표시 됩니다. 예, pin을 입력 하 라는 메시지가 표시 되 면, 모임이 시작 되 고 사용자가 모임에 참가 합니다.</span><span class="sxs-lookup"><span data-stu-id="196c0-124">If the meeting hasn't started (there's no one in the meeting yet): A caller will be prompted if he's the organizer; if he says yes, he'll be prompted for his PIN, and after he inputs the PIN, the meeting will start and the user will join the meeting.</span></span>
    
  - <span data-ttu-id="196c0-125">모임이 이미 시작 된 경우 (다른 사람이 이미 모임에 참가 한 경우): 주최자가 이끌이이 고 PIN을 입력 하 라는 메시지가 표시 되지 않으면 발신자에 게 메시지가 표시 되지 않습니다. 모임이 이미 시작 되었으며 호출자가 참가 하 게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="196c0-125">If the meeting already started (someone else is already in the meeting): A caller won't be prompted if he's the organizer and he'll never be prompted for the PIN; the meeting is already started, and the caller will join it.</span></span>
    
- <span data-ttu-id="196c0-126">익명 액세스 또는 모임을 시작 하기 위해 PIN이 필요 하지 않은 경우 다음을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="196c0-126">If anonymous access, or not requiring a PIN to start a meeting, is enabled:</span></span>
    
  - <span data-ttu-id="196c0-127">모임이 시작 되지 않은 경우 (모임에 아무도 없음) 다음을 수행 하 라는 메시지가 표시 되지 않습니다. 주최자는 이끌이이 고 PIN을 입력 하 라는 메시지가 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="196c0-127">If the meeting hasn't started (there's no one in the meeting yet): A caller won't be prompted if she's the organizer, and she'll never be prompted for the PIN.</span></span> <span data-ttu-id="196c0-128">이끌이의 설정이 off로 설정 되어 있으므로 모임이 시작 되 고 익명 발신자가 모임에 참가 합니다.</span><span class="sxs-lookup"><span data-stu-id="196c0-128">Because the setting of the organizer is set to off, the meeting will start and the anonymous callers will join the meeting.</span></span>
    
  - <span data-ttu-id="196c0-129">모임이 이미 시작 된 경우 (다른 사람이 이미 모임에 속해 있는 경우), 발신자에 게 메시지가 표시 되지 않으며, PIN을 입력 하 라는 메시지가 표시 되지 않으며, 모임이 이미 시작 되어 발신자가 참여 하 게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="196c0-129">If the meeting already started (someone else is already in the meeting): A caller won't be prompted if she's the organizer, and she'll never be prompted for the PIN,;the meeting is already started, and the caller will join it.</span></span>
    
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="196c0-130">Windows PowerShell에 대 한 자세한 정보를 확인 하 고 싶으신가요?</span><span class="sxs-lookup"><span data-stu-id="196c0-130">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="196c0-131">Windows PowerShell은 사용자 및 허용 되지 않거나 수행할 수 있는 사용자를 관리 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="196c0-131">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="196c0-132">Windows PowerShell을 사용 하면 여러 작업을 수행할 때 일상 업무를 단순화할 수 있는 단일 관리 지점을 사용 하 여 Office 365를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="196c0-132">With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="196c0-133">Windows PowerShell을 시작 하려면 다음 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="196c0-133">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="196c0-134">Office 365 PowerShell을 사용 해야 하는 이유</span><span class="sxs-lookup"><span data-stu-id="196c0-134">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="196c0-135">Windows PowerShell을 사용 하 여 Office 365를 관리 하는 가장 좋은 방법</span><span class="sxs-lookup"><span data-stu-id="196c0-135">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="196c0-136">Windows PowerShell에 대 한 자세한 내용은 [Microsoft 팀 PowerShell 참조](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) 에서 자세한 내용을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="196c0-136">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="196c0-137">관련 항목</span><span class="sxs-lookup"><span data-stu-id="196c0-137">Related topics</span></span>

[<span data-ttu-id="196c0-138">Office 365에서 오디오 회의 체험 또는 구매</span><span class="sxs-lookup"><span data-stu-id="196c0-138">Try or purchase Audio Conferencing in Office 365</span></span>](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
