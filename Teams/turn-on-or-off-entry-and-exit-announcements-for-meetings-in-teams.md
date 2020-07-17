---
title: 팀에서 모임에 대 한 알림 입력/해제 및 종료
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: f2c7b5ea-07b6-4b77-8023-bec9596fcc32
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-apr2020
description: 관리자는 Microsoft 팀 모임에서 입력 및 종료 알림을 설정 하거나 해제 하는 방법에 대해 알아볼 수 있습니다.
ms.openlocfilehash: ae2e8936b3fe0dbac0ba0d6ad7bfad3ab2e322ef
ms.sourcegitcommit: 60b859dcb8ac727a38bf28cdb63ff762e7338af8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/30/2020
ms.locfileid: "44938557"
---
# <a name="turn-on-or-off-entry-and-exit-announcements-for-meetings-in-microsoft-teams"></a><span data-ttu-id="65f81-103">Microsoft 팀에서 모임에 대 한 시작 및 종료 알림 설정 또는 해제</span><span class="sxs-lookup"><span data-stu-id="65f81-103">Turn on or off entry and exit announcements for meetings in Microsoft Teams</span></span>

<span data-ttu-id="65f81-104">Microsoft 365 또는 Office 365에서 오디오 회의를 설정 하는 경우 오디오 회의 브리지가 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="65f81-104">When you are setting up Audio Conferencing in Microsoft 365 or Office 365, you will get an audio conferencing bridge.</span></span> <span data-ttu-id="65f81-105">회의 브리지에는 사용자가 Microsoft 팀 모임에 전화를 걸 때 사용 하는 하나 이상의 전화 번호가 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65f81-105">A conferencing bridge can contain one or more phone numbers that people will use to call in to a Microsoft Teams meeting.</span></span> 
  
<span data-ttu-id="65f81-106">회의 브리지가 휴대폰을 사용 하 여 모임에 전화를 거는 사용자에 대 한 통화에 응답 합니다.</span><span class="sxs-lookup"><span data-stu-id="65f81-106">The conferencing bridge answers a call for a user who is dialing in to a meeting using a phone.</span></span> <span data-ttu-id="65f81-107">회의 브리지는 회의 자동 전화 교환에서 음성 메시지를 사용 하 여 발신자에 응답 한 다음 설정에 따라 알림을 재생 하 고, 발신자에 게 이름을 기록 하도록 요청 하 고, PIN 보안을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65f81-107">The conferencing bridge answers the caller with voice prompts from a conferencing auto attendant, and then, depending on your settings, can play notifications, ask callers to record their name, and set up the PIN security.</span></span> <span data-ttu-id="65f81-108">PIN은 Microsoft 팀 모임 이끌이에게 제공 되며, Microsoft 팀 앱을 사용 하 여 모임을 시작할 수 없는 경우 모임을 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65f81-108">A PIN is given to a Microsoft Teams meeting organizer, and it allows them to start a meeting if they can't start the meeting using the Microsoft Teams app.</span></span> <span data-ttu-id="65f81-109">그러나 모임 시작에 PIN이 필요 하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65f81-109">You can, however, set it so that a PIN isn't required to start a meeting.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="setting-meeting-join-options"></a><span data-ttu-id="65f81-110">모임 참가 옵션 설정</span><span class="sxs-lookup"><span data-stu-id="65f81-110">Setting meeting join options</span></span>

<span data-ttu-id="65f81-111">![Microsoft Teams 로고를 나타내는 아이콘](media/teams-logo-30x30.png) **Microsoft Teams 관리 센터 사용**</span><span class="sxs-lookup"><span data-stu-id="65f81-111">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

<span data-ttu-id="65f81-112">이러한 변경 작업을 수행 하려면 관리자 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="65f81-112">You must be an admin to make these changes.</span></span>

1. <span data-ttu-id="65f81-113">의 관리 센터에 로그인  <a href="https://admin.teams.microsoft.com" target="_blank">https://admin.teams.microsoft.com</a> 합니다.</span><span class="sxs-lookup"><span data-stu-id="65f81-113">Log in to the admin center at <a href="https://admin.teams.microsoft.com" target="_blank">https://admin.teams.microsoft.com</a>.</span></span>

2. <span data-ttu-id="65f81-114">왼쪽 탐색 창에서 **모임**  >  **회의 브리지로**이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="65f81-114">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

3. <span data-ttu-id="65f81-115">**회의 브리지** 페이지 맨 위에서 **브리지 설정을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="65f81-115">At the top of the **Conference Bridges** page, click **Bridge Settings**.</span></span> 

4. <span data-ttu-id="65f81-116">**브리지 설정** 창에서 모임 항목을 사용 하거나 사용 하지 않도록 설정 **하 고 알림을 종료**합니다.</span><span class="sxs-lookup"><span data-stu-id="65f81-116">In the **Bridge settings** pane, enable or disable **Meeting entry and exit notifications**.</span></span> <span data-ttu-id="65f81-117">이 옵션이 기본적으로 선택 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65f81-117">This is selected by default.</span></span> <span data-ttu-id="65f81-118">이 확인란을 선택 취소 하면 모임에 참가 한 사용자에 게 다른 사용자가 모임에 입장 하거나 떠날 때 알림이 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="65f81-118">If you clear it, users who have already joined the meeting won't be notified when someone enters or leaves the meeting.</span></span>
    
5. <span data-ttu-id="65f81-119">**입력/종료 알림 유형에**서 **이름 또는 전화 번호** 또는 **톤**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="65f81-119">Under **Entry/exit announcement type**, select **Names or phone numbers** or **Tones**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="65f81-120">기본적으로 외부 참가자는 전화를 건 참가자의 전화 번호를 볼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="65f81-120">By default, external participants can't see the phone numbers of dialed-in participants.</span></span> <span data-ttu-id="65f81-121">이러한 전화 번호의 프라이버시를 유지하려면 **입장/종료** **알림** 유형에 대해 톤을 선택하십시오(이로 인해 Teams가 번호를 읽을 수 없음).</span><span class="sxs-lookup"><span data-stu-id="65f81-121">If you want to maintain the privacy of these phone numbers, select **Tones** for **Entry/exit announcement type** (this prevents the numbers from being read out by Teams).</span></span>
    
6. <span data-ttu-id="65f81-122">**이름 또는 전화 번호**를 선택한 경우 **전화 건 사람이 모임에 참가 하기 전에 해당 이름을 기록해 달라고 요청**하거나 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="65f81-122">If you chose **Names or phone numbers**, enable or disable **Ask callers to record their name before joining the meeting**.</span></span>
    
7. <span data-ttu-id="65f81-123">**저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="65f81-123">Click **Save**.</span></span>

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="65f81-124">Windows PowerShell에 대 한 자세한 정보를 확인 하 고 싶으신가요?</span><span class="sxs-lookup"><span data-stu-id="65f81-124">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="65f81-125">Windows PowerShell은 사용자 및 허용 되지 않거나 수행할 수 있는 사용자를 관리 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="65f81-125">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="65f81-126">Windows PowerShell을 사용 하면 여러 작업을 수행할 때 일상 업무를 단순화할 수 있는 단일 관리 지점을 사용 하 여 Microsoft 365 또는 Office 365를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65f81-126">With Windows PowerShell, you can manage Microsoft 365 or Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="65f81-127">Windows PowerShell을 시작 하려면 다음 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="65f81-127">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="65f81-128">Microsoft 365 또는 Office 365 PowerShell을 사용 해야 하는 이유</span><span class="sxs-lookup"><span data-stu-id="65f81-128">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="65f81-129">Windows PowerShell을 사용 하 여 Microsoft 365 또는 Office 365을 관리 하는 최상의 방법</span><span class="sxs-lookup"><span data-stu-id="65f81-129">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="65f81-130">Windows PowerShell에 대 한 자세한 내용은 [Microsoft 팀 PowerShell 참조](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) 에서 자세한 내용을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="65f81-130">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="65f81-131">관련 항목</span><span class="sxs-lookup"><span data-stu-id="65f81-131">Related topics</span></span>

[<span data-ttu-id="65f81-132">오디오 회의 일반적인 질문</span><span class="sxs-lookup"><span data-stu-id="65f81-132">Audio Conferencing common questions</span></span>](audio-conferencing-common-questions.md)
