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
- seo-marvel-mar2020
description: 'Microsoft 팀 모임에서 입력 및 종료 알림을 설정 하거나 해제 하는 방법에 대해 알아봅니다. '
ms.openlocfilehash: 558146853c7365a1eac9fdd2497326781889cf09
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/03/2020
ms.locfileid: "43139687"
---
# <a name="turn-on-or-off-entry-and-exit-announcements-for-meetings-in-microsoft-teams"></a><span data-ttu-id="f0b66-103">Microsoft 팀에서 모임에 대 한 시작 및 종료 알림 설정 또는 해제</span><span class="sxs-lookup"><span data-stu-id="f0b66-103">Turn on or off entry and exit announcements for meetings in Microsoft Teams</span></span>

<span data-ttu-id="f0b66-104">Office 365에서 오디오 회의를 설정 하는 경우 음성 회의 브리지가 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0b66-104">When you are setting up Audio Conferencing in Office 365, you will get an audio conferencing bridge.</span></span> <span data-ttu-id="f0b66-105">회의 브리지에는 사용자가 Microsoft 팀 모임에 전화를 걸 때 사용 하는 하나 이상의 전화 번호가 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0b66-105">A conferencing bridge can contain one or more phone numbers that people will use to call in to a Microsoft Teams meeting.</span></span> 
  
<span data-ttu-id="f0b66-106">회의 브리지가 휴대폰을 사용 하 여 모임에 전화를 거는 사용자에 대 한 통화에 응답 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0b66-106">The conferencing bridge answers a call for a user who is dialing in to a meeting using a phone.</span></span> <span data-ttu-id="f0b66-107">회의 브리지는 회의 자동 전화 교환에서 음성 메시지를 사용 하 여 발신자에 응답 한 다음 설정에 따라 알림을 재생 하 고, 발신자에 게 이름을 기록 하도록 요청 하 고, PIN 보안을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0b66-107">The conferencing bridge answers the caller with voice prompts from a conferencing auto attendant, and then, depending on your settings, can play notifications, ask callers to record their name, and set up the PIN security.</span></span> <span data-ttu-id="f0b66-108">PIN은 Microsoft 팀 모임 이끌이에게 제공 되며, Microsoft 팀 앱을 사용 하 여 모임을 시작할 수 없는 경우 모임을 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0b66-108">A PIN is given to a Microsoft Teams meeting organizer, and it allows them to start a meeting if they can't start the meeting using the Microsoft Teams app.</span></span> <span data-ttu-id="f0b66-109">그러나 모임 시작에 PIN이 필요 하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0b66-109">You can, however, set it so that a PIN isn't required to start a meeting.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="setting-meeting-join-options"></a><span data-ttu-id="f0b66-110">모임 참가 옵션 설정</span><span class="sxs-lookup"><span data-stu-id="f0b66-110">Setting meeting join options</span></span>

<span data-ttu-id="f0b66-111">![Microsoft Teams 로고를 나타내는 아이콘](media/teams-logo-30x30.png) **Microsoft Teams 관리 센터 사용**</span><span class="sxs-lookup"><span data-stu-id="f0b66-111">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="f0b66-112">왼쪽 탐색 창에서 **모임** > **회의 브리지로**이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0b66-112">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="f0b66-113">**회의 브리지** 페이지 맨 위에서 **브리지 설정을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0b66-113">At the top of the **Conference Bridges** page, click **Bridge Settings**.</span></span> 

3. <span data-ttu-id="f0b66-114">**브리지 설정** 창에서 모임 항목을 사용 하거나 사용 하지 않도록 설정 **하 고 알림을 종료**합니다.</span><span class="sxs-lookup"><span data-stu-id="f0b66-114">In the **Bridge settings** pane, enable or disable **Meeting entry and exit notifications**.</span></span> <span data-ttu-id="f0b66-115">이 옵션이 기본적으로 선택 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0b66-115">This is selected by default.</span></span> <span data-ttu-id="f0b66-116">이 확인란을 선택 취소 하면 모임에 참가 한 사용자에 게 다른 사용자가 모임에 입장 하거나 떠날 때 알림이 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f0b66-116">If you clear it, users who have already joined the meeting won't be notified when someone enters or leaves the meeting.</span></span>
    
4. <span data-ttu-id="f0b66-117">**입력/종료 알림 유형에**서 **이름 또는 전화 번호** 또는 **톤**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0b66-117">Under **Entry/exit announcement type**, select **Names or phone numbers** or **Tones**.</span></span>
    
5. <span data-ttu-id="f0b66-118">**이름 또는 전화 번호**를 선택한 경우 **전화 건 사람이 모임에 참가 하기 전에 해당 이름을 기록해 달라고 요청**하거나 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0b66-118">If you chose **Names or phone numbers**, enable or disable **Ask callers to record their name before joining the meeting**.</span></span>
    
6. <span data-ttu-id="f0b66-119">**저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f0b66-119">Click **Save**.</span></span>

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="f0b66-120">Windows PowerShell에 대 한 자세한 정보를 확인 하 고 싶으신가요?</span><span class="sxs-lookup"><span data-stu-id="f0b66-120">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="f0b66-121">Windows PowerShell은 사용자 및 허용 되지 않거나 수행할 수 있는 사용자를 관리 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0b66-121">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="f0b66-122">Windows PowerShell을 사용 하면 여러 작업을 수행할 때 일상 업무를 단순화할 수 있는 단일 관리 지점을 사용 하 여 Office 365를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0b66-122">With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="f0b66-123">Windows PowerShell을 시작 하려면 다음 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f0b66-123">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="f0b66-124">Office 365 PowerShell을 사용 해야 하는 이유</span><span class="sxs-lookup"><span data-stu-id="f0b66-124">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="f0b66-125">Windows PowerShell을 사용 하 여 Office 365를 관리 하는 가장 좋은 방법</span><span class="sxs-lookup"><span data-stu-id="f0b66-125">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="f0b66-126">Windows PowerShell에 대 한 자세한 내용은 [Microsoft 팀 PowerShell 참조](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) 에서 자세한 내용을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f0b66-126">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="f0b66-127">관련 항목</span><span class="sxs-lookup"><span data-stu-id="f0b66-127">Related topics</span></span>

[<span data-ttu-id="f0b66-128">오디오 회의 일반적인 질문</span><span class="sxs-lookup"><span data-stu-id="f0b66-128">Audio Conferencing common questions</span></span>](audio-conferencing-common-questions.md)
