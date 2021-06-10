---
title: 모임에 대한 입장 및 종료 공지를 켜거나 Teams
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
description: 관리자는 모임에서 입장 및 종료 공지 사항을 켜거나 끄는 방법에 대해 Microsoft Teams 수 있습니다.
ms.openlocfilehash: 6be1c6dc86d8088b5ddb54b2141a10172ba13cc5
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51121336"
---
# <a name="turn-on-or-off-entry-and-exit-announcements-for-meetings-in-microsoft-teams"></a><span data-ttu-id="e2404-103">모임에 대한 입장 및 종료 공지를 켜거나 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e2404-103">Turn on or off entry and exit announcements for meetings in Microsoft Teams</span></span>

<span data-ttu-id="e2404-104">오디오 회의를 Microsoft 365 또는 Office 365 경우 오디오 회의 브리지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2404-104">When you are setting up Audio Conferencing in Microsoft 365 or Office 365, you will get an audio conferencing bridge.</span></span> <span data-ttu-id="e2404-105">회의 브리지에는 사람들이 모임에 전화하는 데 사용할 하나 이상의 전화 Microsoft Teams 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2404-105">A conferencing bridge can contain one or more phone numbers that people will use to call in to a Microsoft Teams meeting.</span></span>
  
<span data-ttu-id="e2404-106">회의 브리지는 전화를 사용하여 모임에 전화 접속하는 사용자에 대한 호출에 응답합니다.</span><span class="sxs-lookup"><span data-stu-id="e2404-106">The conferencing bridge answers a call for a user who is dialing in to a meeting using a phone.</span></span> <span data-ttu-id="e2404-107">회의 브리지는 회의 자동 참석자로부터 음성 프롬프트를 사용하여 발신자에 응답한 다음 설정에 따라 알림을 재생하고 발신자들에게 이름을 기록할 것을 요청하고 PIN 보안을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2404-107">The conferencing bridge answers the caller with voice prompts from a conferencing auto attendant, and then, depending on your settings, can play notifications, ask callers to record their name, and set up the PIN security.</span></span> <span data-ttu-id="e2404-108">PIN은 Microsoft Teams 모임 이끌이에게 주어지며, 모임을 시작할 수 없는 경우 모임을 시작할 수 Microsoft Teams 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2404-108">A PIN is given to a Microsoft Teams meeting organizer, and it allows them to start a meeting if they can't start the meeting using the Microsoft Teams app.</span></span> <span data-ttu-id="e2404-109">그러나 PIN이 모임을 시작하는 데 필요하지 않은지 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2404-109">You can, however, set it so that a PIN isn't required to start a meeting.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="setting-meeting-join-options"></a><span data-ttu-id="e2404-110">모임 조인 옵션 설정</span><span class="sxs-lookup"><span data-stu-id="e2404-110">Setting meeting join options</span></span>

<span data-ttu-id="e2404-111">![Microsoft Teams 로고를 나타내는 아이콘](media/teams-logo-30x30.png) **Microsoft Teams 관리 센터 사용**</span><span class="sxs-lookup"><span data-stu-id="e2404-111">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

<span data-ttu-id="e2404-112">이러한 정책을 관리하려면 전역 관리자 또는 Teams 서비스 관리자여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2404-112">You must be a Teams service admin to make these changes.</span></span> <span data-ttu-id="e2404-113">관리 역할 및 사용 권한 가져오기에 대한 내용은 [Teams 관리자 역할 사용](./using-admin-roles.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e2404-113">See [Use Teams administrator roles to manage Teams](./using-admin-roles.md) to read about getting admin roles and permissions.</span></span>

1. <span data-ttu-id="e2404-114">관리 센터에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="e2404-114">Log in to the admin center.</span></span>

2. <span data-ttu-id="e2404-115">왼쪽 탐색에서 모임 회의  >  **브리지로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="e2404-115">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span>

3. <span data-ttu-id="e2404-116">컨퍼런스 브리지  페이지의 맨 위에 있는 브리지 **설정.**</span><span class="sxs-lookup"><span data-stu-id="e2404-116">At the top of the **Conference Bridges** page, click **Bridge Settings**.</span></span>

4. <span data-ttu-id="e2404-117">Bridge **설정 창에서** 모임 항목 및 종료 알림을 사용하도록 설정하거나 **사용하지 않도록 설정합니다.**</span><span class="sxs-lookup"><span data-stu-id="e2404-117">In the **Bridge settings** pane, enable or disable **Meeting entry and exit notifications**.</span></span> <span data-ttu-id="e2404-118">기본적으로 선택됩니다.</span><span class="sxs-lookup"><span data-stu-id="e2404-118">This is selected by default.</span></span> <span data-ttu-id="e2404-119">모임을 지우면 모임에 이미 참가한 사용자에게 다른 사용자가 모임에 참가하거나 나가는 경우 알림을 들을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e2404-119">If you clear it, users who have already joined the meeting won't be notified when someone enters or leaves the meeting.</span></span>

5. <span data-ttu-id="e2404-120">**진입/종료 공지 유형에서** 이름 **또는 전화** 번호 또는 **톤을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="e2404-120">Under **Entry/exit announcement type**, select **Names or phone numbers** or **Tones**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="e2404-121">기본적으로 외부 참가자는 전화 접속 참가자의 전화 번호를 볼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e2404-121">By default, external participants can't see the phone numbers of dialed-in participants.</span></span> <span data-ttu-id="e2404-122">이러한 전화 번호의 프라이버시를 유지하려면 **입장/종료** **알림** 유형에 대해 톤을 선택하십시오(이로 인해 Teams가 번호를 읽을 수 없음).</span><span class="sxs-lookup"><span data-stu-id="e2404-122">If you want to maintain the privacy of these phone numbers, select **Tones** for **Entry/exit announcement type** (this prevents the numbers from being read out by Teams).</span></span>

6. <span data-ttu-id="e2404-123">이름 또는 전화 **번호를 선택한** 경우 모임에 참가하기 전에 발신자 요청에 자신의 이름을 기록하도록 설정하거나 사용하지 **않도록 설정합니다.**</span><span class="sxs-lookup"><span data-stu-id="e2404-123">If you chose **Names or phone numbers**, enable or disable **Ask callers to record their name before joining the meeting**.</span></span>

7. <span data-ttu-id="e2404-124">**저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e2404-124">Click **Save**.</span></span>

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="e2404-125">자세한 정보를 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e2404-125">Want to know more about Windows PowerShell</span></span>

<span data-ttu-id="e2404-126">Windows PowerShell 모든 것은 사용자 관리와 사용자가 허용되거나 허용되지 않는 작업을 관리하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="e2404-126">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="e2404-127">이 Windows PowerShell 여러 작업을 수행할 때 일상적인 작업을 단순화할 수 Microsoft 365 Office 365 관리 지점을 사용하여 관리 또는 관리 작업을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2404-127">With Windows PowerShell, you can manage Microsoft 365 or Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="e2404-128">다음 항목을 Windows PowerShell 다음 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e2404-128">To get started with Windows PowerShell, see these topics:</span></span>

- [<span data-ttu-id="e2404-129">PowerShell 또는 Microsoft 365 Office 365 이유</span><span class="sxs-lookup"><span data-stu-id="e2404-129">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

- <span data-ttu-id="e2404-130">[사용자와 함께 Microsoft 365 또는 Office 365 가장 Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="e2404-130">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>

<span data-ttu-id="e2404-131">자세한 내용은 Windows PowerShell [PowerShell](/powershell/module/teams/?view=teams-ps) Microsoft Teams 참조를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e2404-131">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="e2404-132">관련 항목</span><span class="sxs-lookup"><span data-stu-id="e2404-132">Related topics</span></span>

[<span data-ttu-id="e2404-133">오디오 회의 일반적인 질문</span><span class="sxs-lookup"><span data-stu-id="e2404-133">Audio Conferencing common questions</span></span>](audio-conferencing-common-questions.md)