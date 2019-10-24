---
title: 비즈니스용 Skype Online에서 모임에 참가할 때 사용자가 자신의 이름을 녹화할 수 있도록 설정
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 1d649328-ada7-422d-a074-d6da4da36970
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
description: 비즈니스용 Skype Online에서 모임에 참가할 때 사용자가 자신의 이름을 기록할 수 있는지 여부에 대해 알아봅니다.
ms.openlocfilehash: 19fad95c0775663db799a59da159ed145aedda6b
ms.sourcegitcommit: 4c041e8a7c39bd6517605ed7fc9aab18cf466596
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/18/2019
ms.locfileid: "37642614"
---
# <a name="enable-users-to-record-their-name-when-they-join-a-meeting-in-skype-for-business-online"></a><span data-ttu-id="1b41d-103">비즈니스용 Skype Online에서 모임에 참가할 때 사용자가 자신의 이름을 녹화할 수 있도록 설정</span><span class="sxs-lookup"><span data-stu-id="1b41d-103">Enable users to record their name when they join a meeting in Skype for Business Online</span></span>

> [!Note]
> <span data-ttu-id="1b41d-104">사용자가 팀에 자신의 이름을 기록할 수 있도록 하려면 [Microsoft 팀에서 모임에 참가할 때 사용자 이름을 기록할 수 있도록](/MicrosoftTeams/enable-users-to-record-their-name-when-they-join-a-meeting-in-teams)합니다 .를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1b41d-104">If you want to allow users to record their names in Teams, see [Enable users to record their name when they join a meeting in Microsoft Teams](/MicrosoftTeams/enable-users-to-record-their-name-when-they-join-a-meeting-in-teams).</span></span>

<span data-ttu-id="1b41d-105">Office 365에서 오디오 회의를 설정 하는 경우 전화 번호를 받고 오디오 회의 브리지 라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b41d-105">When you are setting up Audio Conferencing in Office 365, you will receive phone numbers and what is called an audio conferencing bridge.</span></span> <span data-ttu-id="1b41d-106">회의 브리지에는 전용 또는 공유 전화 번호로 사용할 수 있는 하나 이상의 전화 번호가 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1b41d-106">A conferencing bridge can contain one or more phone numbers that can be a dedicated or shared phone number.</span></span>
  
<span data-ttu-id="1b41d-107">회의 브리지가 휴대폰을 사용 하 여 모임에 전화를 거는 사용자에 대 한 통화에 응답 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b41d-107">The conferencing bridge answers a call for a user who is dialing in to a meeting using a phone.</span></span> <span data-ttu-id="1b41d-108">회의 브리지는 자동 전화 교환의 음성 프롬프트를 사용 하 여 발신자에 응답 한 다음 설정에 따라 알림을 재생 하 고, 발신자에 게 자신의 이름을 기록 하도록 요청 하 고, 모임 이끌이에게 대 한 PIN 보안을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1b41d-108">The conferencing bridge answers the caller with voice prompts from an auto attendant, and then, depending on their settings, can play notifications, ask callers to record their name, and set up the PIN security for meeting organizers.</span></span> <span data-ttu-id="1b41d-109">모임을 시작 하는 데 사용할 수 있도록 모임 이끌이가 Pin을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b41d-109">PINs are given to meeting organizers to allow them to start a meeting.</span></span> <span data-ttu-id="1b41d-110">그러나 모임을 시작 하는 데 PIN이 필요 하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1b41d-110">However, you can set it up so a PIN isn't required to start a meeting.</span></span>

## <a name="set-whether-callers-should-record-their-name"></a><span data-ttu-id="1b41d-111">호출자가 자신의 이름을 기록해 야 하는지 여부 설정</span><span class="sxs-lookup"><span data-stu-id="1b41d-111">Set whether callers should record their name</span></span>
    
1. <span data-ttu-id="1b41d-112">**비즈니스용 Skype 관리 센터**의 왼쪽 탐색 창에서 **오디오 회의** > **Microsoft bridge 설정**으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b41d-112">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
2. <span data-ttu-id="1b41d-113">**모임 참가 환경**에서 **모임 입장 설정 및 종료 알림**설정 확인란을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1b41d-113">Under **Meeting join experience**, see the check box labeled **Enable meeting entry and exit notifications to be turned on**.</span></span>
    
   - <span data-ttu-id="1b41d-114">**선택 됨** 전화 건 사람이 모임에 진입 하기 전에 이름을 기록해 야 한다는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1b41d-114">**Selected** Callers will be asked to record their name before they enter the meeting.</span></span> <span data-ttu-id="1b41d-115">이 옵션이 기본적으로 선택 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1b41d-115">This is selected by default.</span></span>
    
   - <span data-ttu-id="1b41d-116">**선택 취소** 전화 건 사람이 모임에 진입 하기 전에 자신의 이름을 기록해 야 한다는 메시지가 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1b41d-116">**Cleared** Callers won't be asked to record their name before they enter the meeting.</span></span>
    
3. <span data-ttu-id="1b41d-117">변경 작업을 수행한 후 **저장**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b41d-117">After you make your changes, click **Save**.</span></span>
    
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="1b41d-118">Windows PowerShell을 사용 하 여 관리 하는 방법을 알고 싶으세요?</span><span class="sxs-lookup"><span data-stu-id="1b41d-118">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="1b41d-119">시간을 절약 하거나이 작업을 자동화 하려면 [Set-사용](https://go.microsoft.com/fwlink/?LinkId=715757) cmdlet을 사용 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1b41d-119">To save time or automate this, you can use the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757) cmdlet.</span></span>
    
- <span data-ttu-id="1b41d-120">Windows PowerShell은 사용자 관리와 사용자가 수행할 수 있는 작업에 대 한 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="1b41d-120">Windows PowerShell is all about managing users and what users are allowed to do.</span></span> <span data-ttu-id="1b41d-121">Windows PowerShell을 사용 하면 여러 작업을 수행할 때 일상 업무를 단순화할 수 있는 단일 관리 지점을 사용 하 여 Office 365를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1b41d-121">With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="1b41d-122">Windows PowerShell을 시작 하려면 다음 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1b41d-122">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="1b41d-123">Office 365 PowerShell을 사용 해야 하는 이유</span><span class="sxs-lookup"><span data-stu-id="1b41d-123">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="1b41d-124">Windows PowerShell을 사용 하 여 Office 365를 관리 하는 가장 좋은 방법</span><span class="sxs-lookup"><span data-stu-id="1b41d-124">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="1b41d-125">Windows PowerShell에는 한 번에 여러 사용자의 설정을 변경 하는 경우와 같이 Microsoft 365 관리 센터를 사용 하는 경우에만 속도, 단순성, 생산성 등 다양 한 이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1b41d-125">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center, such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="1b41d-126">다음 항목에서 이러한 이점에 대해 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="1b41d-126">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="1b41d-127">Windows PowerShell 및 Lync Online 소개</span><span class="sxs-lookup"><span data-stu-id="1b41d-127">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="1b41d-128">Windows PowerShell을 사용 하 여 비즈니스용 Skype Online 관리</span><span class="sxs-lookup"><span data-stu-id="1b41d-128">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="1b41d-129">Windows PowerShell을 사용 하 여 일반적인 비즈니스용 Skype Online 관리 작업 수행</span><span class="sxs-lookup"><span data-stu-id="1b41d-129">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="1b41d-130">비즈니스용 Skype Online 용 Windows PowerShell 모듈을 사용 하면 비즈니스용 Skype Online에 연결 하는 원격 Windows PowerShell 세션을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1b41d-130">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span> <span data-ttu-id="1b41d-131">이 모듈은 64 비트 컴퓨터 에서만 지원 되며 비즈니스용 [Skype Online 용 Windows PowerShell 모듈](https://go.microsoft.com/fwlink/?LinkId=294688) 의 Microsoft 다운로드 센터에서 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1b41d-131">This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="1b41d-132">관련 항목</span><span class="sxs-lookup"><span data-stu-id="1b41d-132">Related topics</span></span>

[<span data-ttu-id="1b41d-133">Office 365에서 오디오 회의 체험 또는 구매</span><span class="sxs-lookup"><span data-stu-id="1b41d-133">Try or purchase Audio Conferencing in Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
