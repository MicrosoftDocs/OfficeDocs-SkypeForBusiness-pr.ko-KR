---
title: 비즈니스용 Skype Online에서 모임에 대 한 시작 및 종료 알림 설정 또는 해제
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: f2c7b5ea-07b6-4b77-8023-bec9596fcc32
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
description: '비즈니스용 Skype 관리 센터를 사용 하 여 비즈니스용 Skype Online 모임에서 입력 및 종료 알림을 설정 또는 해제 하는 방법에 대해 알아봅니다. '
ms.openlocfilehash: 62b3437b75e36b57bebd167f6d2e155deb31a41b
ms.sourcegitcommit: 4c041e8a7c39bd6517605ed7fc9aab18cf466596
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/18/2019
ms.locfileid: "37642573"
---
# <a name="turn-on-or-off-entry-and-exit-announcements-for-meetings-in-skype-for-business-online"></a><span data-ttu-id="0928f-103">비즈니스용 Skype Online에서 모임에 대 한 시작 및 종료 알림 설정 또는 해제</span><span class="sxs-lookup"><span data-stu-id="0928f-103">Turn on or off entry and exit announcements for meetings in Skype for Business Online</span></span>

> [!Note]
> <span data-ttu-id="0928f-104">Microsoft 팀의 입력 및 종료 알림에 대 한 자세한 내용은 [Microsoft 팀에서 모임에 대 한 시작 및 종료 알림 설정 또는 해제](/MicrosoftTeams/turn-on-or-off-entry-and-exit-announcements-for-meetings-in-teams)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0928f-104">For information about entry and exit announcements in Microsoft Teams, see [Turn on or off entry and exit announcements for meetings in Microsoft Teams](/MicrosoftTeams/turn-on-or-off-entry-and-exit-announcements-for-meetings-in-teams).</span></span>

<span data-ttu-id="0928f-105">Office 365에서 오디오 회의를 설정 하는 경우 음성 회의 브리지가 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0928f-105">When you are setting up Audio Conferencing in Office 365, you will get an audio conferencing bridge.</span></span> <span data-ttu-id="0928f-106">회의 브리지에는 다른 사용자가 비즈니스용 Skype 모임에 전화를 걸 때 사용할 수 있는 하나 이상의 전화 번호가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0928f-106">A conferencing bridge can contain one or more phone numbers that people will use to call in to a Skype for Business meeting.</span></span> 
  
<span data-ttu-id="0928f-107">회의 브리지가 휴대폰을 사용 하 여 모임에 전화를 거는 사용자에 대 한 통화에 응답 합니다.</span><span class="sxs-lookup"><span data-stu-id="0928f-107">The conferencing bridge answers a call for a user who is dialing in to a meeting using a phone.</span></span> <span data-ttu-id="0928f-108">회의 브리지는 회의 자동 전화 교환에서 음성 메시지를 사용 하 여 발신자에 응답 한 다음 설정에 따라 알림을 재생 하 고, 발신자에 게 이름을 기록 하도록 요청 하 고, PIN 보안을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0928f-108">The conferencing bridge answers the caller with voice prompts from a conferencing auto attendant, and then, depending on your settings, can play notifications, ask callers to record their name, and set up the PIN security.</span></span> <span data-ttu-id="0928f-109">Skype for business 모임 이끌이에게 PIN을 제공 하 고 비즈니스용 Skype 앱을 사용 하 여 모임을 시작할 수 없는 경우 모임을 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0928f-109">A PIN is given to a Skype for Business meeting organizer, and it allows them to start a meeting if they can't start the meeting using the Skype for Business app.</span></span> <span data-ttu-id="0928f-110">그러나 모임 시작에 PIN이 필요 하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0928f-110">You can, however, set it so that a PIN isn't required to start a meeting.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="setting-meeting-join-options"></a><span data-ttu-id="0928f-111">모임 참가 옵션 설정</span><span class="sxs-lookup"><span data-stu-id="0928f-111">Setting meeting join options</span></span>
    
1. <span data-ttu-id="0928f-112">**비즈니스용 Skype 관리 센터**의 왼쪽 탐색 창에서 **오디오 회의** > **Microsoft bridge 설정**으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="0928f-112">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
2. <span data-ttu-id="0928f-113">**모임 참가 환경**에서 **모임 입장 사용 및 종료 알림**기능을 선택 하거나 선택을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="0928f-113">Under **Meeting join experience**, select or clear **Enable meeting entry and exit notifications to be turned on**.</span></span> <span data-ttu-id="0928f-114">이 옵션이 기본적으로 선택 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0928f-114">This is selected by default.</span></span> <span data-ttu-id="0928f-115">이 확인란을 선택 취소 하면 모임에 참가 한 사용자에 게 다른 사용자가 모임에 입장 하거나 떠날 때 알림이 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0928f-115">If you clear it, users who have already joined the meeting won't be notified when someone enters or leaves the meeting.</span></span>
    
3. <span data-ttu-id="0928f-116">**입력/종료 알림 유형에**서 **이름 또는 전화 번호** 또는 **톤**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0928f-116">Under **Entry/exit announcement type**, select **Names or phone numbers** or **Tones**.</span></span>
    
4. <span data-ttu-id="0928f-117">**모임에 참가 하기 전에 전화 건 사람에 게 이름을 기록 하도록 요청 합니다를**선택 하거나 선택 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="0928f-117">Check or uncheck **Ask callers to record their name before joining the meeting**.</span></span>
    
5. <span data-ttu-id="0928f-118">변경 작업을 수행한 후 **저장**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="0928f-118">After you make your changes, click **Save**.</span></span>
    

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="0928f-119">Windows PowerShell을 사용 하 여 관리 하는 방법을 알고 싶으세요?</span><span class="sxs-lookup"><span data-stu-id="0928f-119">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="0928f-120">시간을 절약 하거나이 작업을 자동화 하려면 [Set-사용](https://docs.microsoft.com/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) cmdlet을 사용 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0928f-120">To save time or automate this, you can use the [Set-CsOnlineDialInConferencingTenantSettings](https://docs.microsoft.com/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) cmdlet.</span></span>
    
- <span data-ttu-id="0928f-121">Windows PowerShell을 사용할 때 비즈니스용 Skype Online은 사용자 관리와 사용자가 허용 하거나 허용 하지 않는 작업에 대 한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="0928f-121">When it comes to Windows PowerShell, Skype for Business Online is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="0928f-122">Windows PowerShell을 사용 하면 여러 작업을 수행할 때 일상 업무를 단순화할 수 있는 단일 관리 지점을 사용 하 여 Office 365를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0928f-122">With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="0928f-123">Windows PowerShell을 시작 하려면 다음 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0928f-123">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="0928f-124">Office 365 PowerShell을 사용 해야 하는 이유</span><span class="sxs-lookup"><span data-stu-id="0928f-124">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="0928f-125">Windows PowerShell을 사용 하 여 Office 365를 관리 하는 가장 좋은 방법</span><span class="sxs-lookup"><span data-stu-id="0928f-125">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="0928f-126">Windows PowerShell에는 한 번에 여러 사용자에 게 설정을 변경 하는 경우와 같이 Microsoft 365 관리 센터를 사용 하는 경우에만 속도, 단순성, 생산성 등 다양 한 이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0928f-126">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making settings changes for many users at one time.</span></span> <span data-ttu-id="0928f-127">다음 항목에서 이러한 이점에 대해 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="0928f-127">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="0928f-128">Windows PowerShell 및 Lync Online 소개</span><span class="sxs-lookup"><span data-stu-id="0928f-128">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="0928f-129">Windows PowerShell을 사용 하 여 비즈니스용 Skype Online 관리</span><span class="sxs-lookup"><span data-stu-id="0928f-129">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="0928f-130">Windows PowerShell을 사용 하 여 일반적인 비즈니스용 Skype Online 관리 작업 수행</span><span class="sxs-lookup"><span data-stu-id="0928f-130">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="0928f-131">비즈니스용 Skype Online 용 Windows PowerShell 모듈을 사용 하면 비즈니스용 Skype Online에 연결 하는 원격 Windows PowerShell 세션을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0928f-131">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span> <span data-ttu-id="0928f-132">이 모듈은 64 비트 컴퓨터 에서만 지원 되며 비즈니스용 [Skype Online 용 Windows PowerShell 모듈](https://go.microsoft.com/fwlink/?LinkId=294688) 의 Microsoft 다운로드 센터에서 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0928f-132">This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="0928f-133">관련 항목</span><span class="sxs-lookup"><span data-stu-id="0928f-133">Related topics</span></span>

[<span data-ttu-id="0928f-134">오디오 회의 일반적인 질문</span><span class="sxs-lookup"><span data-stu-id="0928f-134">Audio Conferencing common questions</span></span>](/MicrosoftTeams/audio-conferencing-common-questions)
