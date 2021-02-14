---
title: 오디오 회의 모임의 PIN 길이 설정
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: b86d31c6-1543-478f-b8c6-4b71e708403a
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
description: PIN의 길이 및 요구 사항에 대한 매개 변수를 알아보고 Microsoft Teams에서 모임의 길이를 설정하는 방법을 참조하세요.
ms.openlocfilehash: 7fab4d42846dd5289f3255710684b75fe6fb07bc
ms.sourcegitcommit: 1807ea5509f8efa6abba8462bce2f3646117e8bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/10/2020
ms.locfileid: "44691104"
---
# <a name="set-the-pin-length-for-audio-conferencing-meetings-in-microsoft-teams"></a><span data-ttu-id="45932-103">Microsoft Teams에서 오디오 회의 모임의 PIN 길이 설정</span><span class="sxs-lookup"><span data-stu-id="45932-103">Set the PIN length for Audio Conferencing meetings in Microsoft Teams</span></span>

<span data-ttu-id="45932-104">Microsoft Teams에 대한 오디오 회의를 설정하면 오디오 회의 브리지가 열리게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="45932-104">When you are setting up audio conferencing for Microsoft Teams, you will get an audio conferencing bridge.</span></span> <span data-ttu-id="45932-105">회의 브리지에는 하나 이상의 전화 번호가 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45932-105">A conferencing bridge can contain one or more phone numbers.</span></span> <span data-ttu-id="45932-106">설정한 전화 번호는 Microsoft Teams 앱의 모임 초대에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="45932-106">The phone number you set will be included on the meeting invites for the Microsoft Teams app.</span></span>
  
<span data-ttu-id="45932-107">오디오 회의 브리지는 전화기를 사용하여 모임에 전화를 거는 사람들의 통화에 응답합니다.</span><span class="sxs-lookup"><span data-stu-id="45932-107">The audio conferencing bridge answers a call for people who are dialing in to a meeting using a phone.</span></span> <span data-ttu-id="45932-108">자동 전화 회의에서 음성 프롬프트로 발신자에 응답한 다음 설정에 따라 알림을 재생하고 발신자 이름을 기록해 달라고 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="45932-108">It answers the caller with voice prompts from an auto attendant and then, depending on your settings, can play notifications and ask callers to record their name.</span></span> <span data-ttu-id="45932-109">**Microsoft 브리지** 설정을 사용하면 모임 알림 및 모임 참가 환경 설정을 변경하고 모임 이끌이가 사용하는 PI의 길이를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45932-109">**Microsoft bridge settings** allow you to change the settings for meeting notifications and the meeting join experience, and set the length of the PINs that are used by meeting organizers.</span></span> <span data-ttu-id="45932-110">모임 이끌이는 MICROSOFT Teams 앱을 사용하여 모임에 참가할 수 없는 경우 PI를 사용하여 모임을 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45932-110">Meeting organizers use PINs to start meetings if they can't join the meeting using the Microsoft Teams app.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="setting-the-pin-length"></a><span data-ttu-id="45932-111">PIN 길이 설정</span><span class="sxs-lookup"><span data-stu-id="45932-111">Setting the PIN length</span></span>

<span data-ttu-id="45932-112">![Microsoft Teams 로고를 나타내는 아이콘](media/teams-logo-30x30.png) **Microsoft Teams 관리 센터 사용**</span><span class="sxs-lookup"><span data-stu-id="45932-112">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="45932-113">왼쪽 탐색 모음에서 **모임** 회의  >  **브리지로 이동**</span><span class="sxs-lookup"><span data-stu-id="45932-113">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="45932-114">컨퍼런스 브리지  페이지의 맨 위에 있는 **브리지 설정을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="45932-114">At the top of the **Conference Bridges** page, click **Bridge Settings**.</span></span> 

3. <span data-ttu-id="45932-115">브리지 **설정** 창의 PIN 길이 아래에서 **PIN에** 사용할 자릿수 선택</span><span class="sxs-lookup"><span data-stu-id="45932-115">In the **Bridge settings** pane, under **PIN length**, select the number of digits you want for the PIN.</span></span>

4. <span data-ttu-id="45932-116">**저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="45932-116">Click **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="45932-117">PIN은 회의 ID와 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="45932-117">A PIN is different from a conference ID.</span></span> <span data-ttu-id="45932-118">전화 회의 신분은 발신자들이 모임에 참가할 때 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="45932-118">Conference IDs are used by callers when they join the meeting.</span></span> <span data-ttu-id="45932-119">모임을 식별하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="45932-119">They are used to identify the meeting.</span></span> <span data-ttu-id="45932-120">PIN은 발신자가 모임 이끌이로 인증하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="45932-120">The PIN is used to authenticate a caller as the meeting organizer.</span></span> 

## <a name="want-to-know-more-about-pin-settings"></a><span data-ttu-id="45932-121">PIN 설정에 대해 더 알고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="45932-121">Want to know more about PIN settings?</span></span>

- <span data-ttu-id="45932-122">PINS는 4자리에서 12자리까지 사용할 수 있습니다. 기본값은 5입니다.</span><span class="sxs-lookup"><span data-stu-id="45932-122">PINs can be from 4 to 12 digits; the default is 5.</span></span> <span data-ttu-id="45932-123">숫자는 PINS를 만들 때만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="45932-123">Numbers are only used when creating PINs.</span></span> <span data-ttu-id="45932-124">문자와 특수 문자는 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="45932-124">Letters and special characters aren't used.</span></span>
    
- <span data-ttu-id="45932-125">PIN은 Microsoft Teams 사용자가 아직 모임을 시작하지 않은 경우 모임 이끌이에게만 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="45932-125">A PIN is only required for the meeting organizer when a Microsoft Teams user hasn't already started the meeting.</span></span> <span data-ttu-id="45932-126">모든 사용자가 모임에 전화 접속하는 경우 모임 이끌이가 모임을 시작하려면 PIN이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="45932-126">If everyone is dialing in to the meeting, then the PIN is required for the meeting organizer to start the meeting.</span></span>
    
- <span data-ttu-id="45932-127">PIN 보안 설정은 Microsoft 브리지와 연결된 모든 전화 번호에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="45932-127">PIN security settings are applied to all of the phone numbers that are associated with a Microsoft bridge.</span></span> <span data-ttu-id="45932-128">해당 브리지와 연결된 전화 번호를 사용하는 모든 모임에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="45932-128">They will be applied to all meetings that use the phone numbers associated with a given bridge.</span></span> 
    
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="45932-129">자세한 내용은 Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="45932-129">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="45932-130">Windows PowerShell 관리는 사용자 및 사용자가 허용되거나 허용되지 않는 작업을 관리하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="45932-130">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="45932-131">이 Windows PowerShell 여러 작업을 수행할 때 일상적인 작업을 간소화할 수 있는 단일 관리 지점을 사용하여 Microsoft 365 또는 Office 365를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45932-131">With Windows PowerShell, you can manage Microsoft 365 or Office 365 by using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="45932-132">다음 항목을 Windows PowerShell 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="45932-132">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="45932-133">Office 365 PowerShell을 사용하는 이유</span><span class="sxs-lookup"><span data-stu-id="45932-133">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="45932-134">Microsoft 365 또는 Office 365를 관리하는 가장 좋은 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="45932-134">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="45932-135">자세한 내용은 Windows PowerShell [Microsoft Teams PowerShell 참조를](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="45932-135">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
  
## <a name="related-topics"></a><span data-ttu-id="45932-136">관련 항목</span><span class="sxs-lookup"><span data-stu-id="45932-136">Related topics</span></span>

[<span data-ttu-id="45932-137">Microsoft 365 또는 Office 365에서 오디오 회의 시도 또는 구매</span><span class="sxs-lookup"><span data-stu-id="45932-137">Try or purchase Audio Conferencing in Microsoft 365 or Office 365</span></span>](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
