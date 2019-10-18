---
title: Microsoft 팀에서 오디오 회의 모임에 대 한 PIN 길이 설정
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
f1keywords: None
ms.custom:
- Audio Conferencing
description: PIN의 길이 및 요구 사항에 대 한 매개 변수를 알아보고 Microsoft 팀에서 모임의 길이를 설정 하는 방법을 살펴봅니다.
ms.openlocfilehash: 50c6ffe31e673dc7573ebb27f0eeb2ca78a30918
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2019
ms.locfileid: "37571274"
---
# <a name="set-the-pin-length-for-audio-conferencing-meetings-in-microsoft-teams"></a><span data-ttu-id="9b26e-103">Microsoft 팀에서 오디오 회의 모임에 대 한 PIN 길이 설정</span><span class="sxs-lookup"><span data-stu-id="9b26e-103">Set the PIN length for Audio Conferencing meetings in Microsoft Teams</span></span>

<span data-ttu-id="9b26e-104">Microsoft 팀에 대 한 오디오 회의를 설정 하는 경우 오디오 회의 브리지가 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b26e-104">When you are setting up audio conferencing for Microsoft Teams, you will get an audio conferencing bridge.</span></span> <span data-ttu-id="9b26e-105">회의 브리지에는 하나 이상의 전화 번호가 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b26e-105">A conferencing bridge can contain one or more phone numbers.</span></span> <span data-ttu-id="9b26e-106">설정한 전화 번호는 Microsoft 팀 앱에 대 한 모임 초대에 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b26e-106">The phone number you set will be included on the meeting invites for the Microsoft Teams app.</span></span>
  
<span data-ttu-id="9b26e-107">오디오 회의 브리지가 휴대폰을 사용 하 여 모임에 전화를 거는 사람들을 위한 통화에 응답 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b26e-107">The audio conferencing bridge answers a call for people who are dialing in to a meeting using a phone.</span></span> <span data-ttu-id="9b26e-108">자동 전화 교환에서 음성 메시지가 표시 된 호출자에 게 응답 한 다음 설정에 따라 알림을 재생 하 고 호출자에 게 해당 이름을 기록 하도록 요청할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b26e-108">It answers the caller with voice prompts from an auto attendant and then, depending on your settings, can play notifications and ask callers to record their name.</span></span> <span data-ttu-id="9b26e-109">**Microsoft bridge 설정을** 사용 하 여 모임 알림과 모임 참가 환경에 대 한 설정을 변경 하 고 모임 이끌이가 사용 하는 핀 길이를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b26e-109">**Microsoft bridge settings** allow you to change the settings for meeting notifications and the meeting join experience, and set the length of the PINs that are used by meeting organizers.</span></span> <span data-ttu-id="9b26e-110">모임 이끌이는 Pin을 사용 하 여 Microsoft 팀 앱을 사용 하 여 모임에 참가할 수 없는 경우 모임을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b26e-110">Meeting organizers use PINs to start meetings if they can't join the meeting using the Microsoft Teams app.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="setting-the-pin-length"></a><span data-ttu-id="9b26e-111">PIN 길이 설정</span><span class="sxs-lookup"><span data-stu-id="9b26e-111">Setting the PIN length</span></span>

<span data-ttu-id="9b26e-112">![](media/teams-logo-30x30.png) **Microsoft 팀 관리 센터를 사용 하 여** microsoft 팀 로고를 표시 하는 아이콘</span><span class="sxs-lookup"><span data-stu-id="9b26e-112">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="9b26e-113">왼쪽 탐색 창에서 **모임** > **회의 브리지로**이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b26e-113">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="9b26e-114">**회의 브리지** 페이지 맨 위에서 **브리지 설정을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b26e-114">At the top of the **Conference Bridges** page, click **Bridge Settings**.</span></span> 

3. <span data-ttu-id="9b26e-115">**브리지 설정** 창의 **pin 길이**에서 원하는 PIN의 자릿수를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b26e-115">In the **Bridge settings** pane, under **PIN length**, select the number of digits you want for the PIN.</span></span>

4. <span data-ttu-id="9b26e-116">**저장**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b26e-116">Click **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="9b26e-117">PIN이 전화 회의 ID와 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="9b26e-117">A PIN is different from a conference ID.</span></span> <span data-ttu-id="9b26e-118">회의 Id는 발신자가 모임에 참가할 때 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b26e-118">Conference IDs are used by callers when they join the meeting.</span></span> <span data-ttu-id="9b26e-119">회의를 식별 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b26e-119">They are used to identify the meeting.</span></span> <span data-ttu-id="9b26e-120">PIN은 모임 이끌이로 서 호출자를 인증 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b26e-120">The PIN is used to authenticate a caller as the meeting organizer.</span></span> 

## <a name="want-to-know-more-about-pin-settings"></a><span data-ttu-id="9b26e-121">PIN 설정에 대 한 자세한 내용을 확인 하 고 싶으신가요?</span><span class="sxs-lookup"><span data-stu-id="9b26e-121">Want to know more about PIN settings?</span></span>

- <span data-ttu-id="9b26e-122">Pin의 자릿수는 4 ~ 12 자리입니다. 기본값은 5입니다.</span><span class="sxs-lookup"><span data-stu-id="9b26e-122">PINs can be from 4 to 12 digits; the default is 5.</span></span> <span data-ttu-id="9b26e-123">숫자는 핀을 만들 때만 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b26e-123">Numbers are only used when creating PINs.</span></span> <span data-ttu-id="9b26e-124">문자 및 특수 문자는 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9b26e-124">Letters and special characters aren't used.</span></span>
    
- <span data-ttu-id="9b26e-125">PIN은 Microsoft 팀 사용자가 모임을 아직 시작 하지 않은 경우 모임 이끌이에게만 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b26e-125">A PIN is only required for the meeting organizer when a Microsoft Teams user hasn't already started the meeting.</span></span> <span data-ttu-id="9b26e-126">모든 사용자가 모임에 전화를 거는 경우 모임 이끌이가 모임을 시작 하려면 PIN이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b26e-126">If everyone is dialing in to the meeting, then the PIN is required for the meeting organizer to start the meeting.</span></span>
    
- <span data-ttu-id="9b26e-127">PIN 보안 설정은 Microsoft bridge와 연결 된 모든 전화 번호에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b26e-127">PIN security settings are applied to all of the phone numbers that are associated with a Microsoft bridge.</span></span> <span data-ttu-id="9b26e-128">해당 브리지에 연결 된 전화 번호를 사용 하는 모든 모임에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b26e-128">They will be applied to all meetings that use the phone numbers associated with a given bridge.</span></span> 
    
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="9b26e-129">Windows PowerShell에 대 한 자세한 정보를 확인 하 고 싶으신가요?</span><span class="sxs-lookup"><span data-stu-id="9b26e-129">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="9b26e-130">Windows PowerShell은 사용자 및 허용 되지 않거나 수행할 수 있는 사용자를 관리 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b26e-130">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="9b26e-131">Windows PowerShell을 사용 하면 여러 작업을 수행할 때 일상 업무를 단순화할 수 있는 단일 관리 지점을 사용 하 여 Office 365를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b26e-131">With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="9b26e-132">Windows PowerShell을 시작 하려면 다음 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9b26e-132">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="9b26e-133">Office 365 PowerShell을 사용 해야 하는 이유</span><span class="sxs-lookup"><span data-stu-id="9b26e-133">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="9b26e-134">Windows PowerShell을 사용 하 여 Office 365를 관리 하는 가장 좋은 방법</span><span class="sxs-lookup"><span data-stu-id="9b26e-134">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="9b26e-135">Windows PowerShell에 대 한 자세한 내용은 [Microsoft 팀 PowerShell 참조](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) 에서 자세한 내용을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9b26e-135">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
  
## <a name="related-topics"></a><span data-ttu-id="9b26e-136">관련 항목</span><span class="sxs-lookup"><span data-stu-id="9b26e-136">Related topics</span></span>

[<span data-ttu-id="9b26e-137">Office 365에서 오디오 회의 체험 또는 구매</span><span class="sxs-lookup"><span data-stu-id="9b26e-137">Try or purchase Audio Conferencing in Office 365</span></span>](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
