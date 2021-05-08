---
title: 온라인에서 모임에 대한 항목 및 종료 비즈니스용 Skype 켜기
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
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: '관리 센터를 사용하여 비즈니스용 Skype 온라인 모임에서 공지 사항을 켜거나 종료하는 비즈니스용 Skype 방법에 대해 자세히 알아보습니다. '
ms.openlocfilehash: f097563ca8dce47277a44573f2af66ed7f1539dd
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52237574"
---
# <a name="turn-on-or-off-entry-and-exit-announcements-for-meetings-in-skype-for-business-online"></a><span data-ttu-id="96c08-103">온라인에서 모임에 대한 항목 및 종료 비즈니스용 Skype 켜기</span><span class="sxs-lookup"><span data-stu-id="96c08-103">Turn on or off entry and exit announcements for meetings in Skype for Business Online</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!Note]
> <span data-ttu-id="96c08-104">의 입장 및 종료 Microsoft Teams 대한 자세한 내용은 에서 모임에 대한 항목 및 종료 Microsoft Teams 를 [Microsoft Teams 참조하세요.](/MicrosoftTeams/turn-on-or-off-entry-and-exit-announcements-for-meetings-in-teams)</span><span class="sxs-lookup"><span data-stu-id="96c08-104">For information about entry and exit announcements in Microsoft Teams, see [Turn on or off entry and exit announcements for meetings in Microsoft Teams](/MicrosoftTeams/turn-on-or-off-entry-and-exit-announcements-for-meetings-in-teams).</span></span>

<span data-ttu-id="96c08-105">오디오 회의를 Microsoft 365 또는 Office 365 경우 오디오 회의 브리지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96c08-105">When you are setting up Audio Conferencing in Microsoft 365 or Office 365, you will get an audio conferencing bridge.</span></span> <span data-ttu-id="96c08-106">회의 브리지에는 사용자들이 모임에 전화하는 데 사용할 하나 이상의 전화 비즈니스용 Skype 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96c08-106">A conferencing bridge can contain one or more phone numbers that people will use to call in to a Skype for Business meeting.</span></span> 
  
<span data-ttu-id="96c08-107">회의 브리지는 전화를 사용하여 모임에 전화 접속하는 사용자에 대한 호출에 응답합니다.</span><span class="sxs-lookup"><span data-stu-id="96c08-107">The conferencing bridge answers a call for a user who is dialing in to a meeting using a phone.</span></span> <span data-ttu-id="96c08-108">회의 브리지는 회의 자동 참석자로부터 음성 프롬프트를 사용하여 발신자에 응답한 다음 설정에 따라 알림을 재생하고 발신자들에게 이름을 기록할 것을 요청하고 PIN 보안을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96c08-108">The conferencing bridge answers the caller with voice prompts from a conferencing auto attendant, and then, depending on your settings, can play notifications, ask callers to record their name, and set up the PIN security.</span></span> <span data-ttu-id="96c08-109">PIN은 비즈니스용 Skype 모임 이끌이에게 주어지며, 모임 이끌이가 앱을 사용하여 모임을 시작할 수 없는 비즈니스용 Skype 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96c08-109">A PIN is given to a Skype for Business meeting organizer, and it allows them to start a meeting if they can't start the meeting using the Skype for Business app.</span></span> <span data-ttu-id="96c08-110">그러나 PIN이 모임을 시작하는 데 필요하지 않은지 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96c08-110">You can, however, set it so that a PIN isn't required to start a meeting.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="setting-meeting-join-options"></a><span data-ttu-id="96c08-111">모임 조인 옵션 설정</span><span class="sxs-lookup"><span data-stu-id="96c08-111">Setting meeting join options</span></span>
    
1. <span data-ttu-id="96c08-112">관리 **비즈니스용 Skype** 왼쪽 탐색에서 오디오 회의 Microsoft 브리지 설정으로   >  **이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="96c08-112">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
2. <span data-ttu-id="96c08-113">모임 **참가 환경 아래에서** 을 사용하도록 설정한 모임 항목 및 종료 알림 사용 을 **선택하거나 선택 취소합니다.**</span><span class="sxs-lookup"><span data-stu-id="96c08-113">Under **Meeting join experience**, select or clear **Enable meeting entry and exit notifications to be turned on**.</span></span> <span data-ttu-id="96c08-114">기본적으로 선택됩니다.</span><span class="sxs-lookup"><span data-stu-id="96c08-114">This is selected by default.</span></span> <span data-ttu-id="96c08-115">모임을 지우면 모임에 이미 참가한 사용자에게 다른 사용자가 모임에 참가하거나 나가는 경우 알림을 들을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="96c08-115">If you clear it, users who have already joined the meeting won't be notified when someone enters or leaves the meeting.</span></span>
    
3. <span data-ttu-id="96c08-116">**진입/종료 공지 유형에서** 이름 **또는 전화** 번호 또는 **톤을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="96c08-116">Under **Entry/exit announcement type**, select **Names or phone numbers** or **Tones**.</span></span>
    
4. <span data-ttu-id="96c08-117">모임에 참가하기 전에 발신자에 이름을 기록할지 확인하거나 **선택을 선택하지 않습니다.**</span><span class="sxs-lookup"><span data-stu-id="96c08-117">Check or uncheck **Ask callers to record their name before joining the meeting**.</span></span>
    
5. <span data-ttu-id="96c08-118">변경한 후 저장을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="96c08-118">After you make your changes, click **Save**.</span></span>
    

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="96c08-119">사용자와 함께 관리하는 방법을 알고 Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="96c08-119">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="96c08-120">시간을 절약하거나 자동화하기 위해 [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) cmdlet을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96c08-120">To save time or automate this, you can use the [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) cmdlet.</span></span>
    
- <span data-ttu-id="96c08-121">이 경우 Windows PowerShell 온라인에서 비즈니스용 Skype 사용자 관리와 사용자가 허용되거나 허용되지 않는 작업을 모두 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96c08-121">When it comes to Windows PowerShell, Skype for Business Online is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="96c08-122">이 Windows PowerShell 여러 작업을 수행할 때 일상적인 작업을 단순화할 수 Microsoft 365 Office 365 관리 지점을 사용하여 관리 또는 관리 작업을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96c08-122">With Windows PowerShell, you can manage Microsoft 365 or Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="96c08-123">다음 항목을 Windows PowerShell 다음 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="96c08-123">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="96c08-124">PowerShell 또는 Microsoft 365 Office 365 이유</span><span class="sxs-lookup"><span data-stu-id="96c08-124">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - <span data-ttu-id="96c08-125">[사용자와 함께 Microsoft 365 또는 Office 365 가장 Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="96c08-125">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
- <span data-ttu-id="96c08-126">Windows PowerShell 많은 사용자에 대한 설정을 한 Microsoft 365 경우와 같이 관리 센터를 사용하는 것만 사용하여 속도, 단순성 및 생산성에 많은 이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96c08-126">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making settings changes for many users at one time.</span></span> <span data-ttu-id="96c08-127">다음 항목에서 이러한 이점에 대해 자세히 알아보습니다.</span><span class="sxs-lookup"><span data-stu-id="96c08-127">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="96c08-128">Windows PowerShell 및 비즈니스용 Skype Online 소개</span><span class="sxs-lookup"><span data-stu-id="96c08-128">An introduction to Windows PowerShell and Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="96c08-129">온라인 Windows PowerShell 관리하기 위해 비즈니스용 Skype 사용</span><span class="sxs-lookup"><span data-stu-id="96c08-129">Using Windows PowerShell to manage Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="96c08-130">일반적인 Windows PowerShell 관리 작업을 수행하는 데 비즈니스용 Skype 사용</span><span class="sxs-lookup"><span data-stu-id="96c08-130">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    > [!NOTE]
    > <span data-ttu-id="96c08-131">Windows PowerShell 온라인용 비즈니스용 Skype 모듈을 사용하면 온라인에 연결하는 원격 Windows PowerShell 세션을 만들 비즈니스용 Skype 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96c08-131">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span> <span data-ttu-id="96c08-132">64비트 컴퓨터에서만 지원되는 이 모듈은 온라인용 Microsoft 다운로드 센터에서 Windows PowerShell 다운로드할 [비즈니스용 Skype 있습니다.](https://go.microsoft.com/fwlink/?LinkId=294688)</span><span class="sxs-lookup"><span data-stu-id="96c08-132">This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="96c08-133">관련 항목</span><span class="sxs-lookup"><span data-stu-id="96c08-133">Related topics</span></span>

[<span data-ttu-id="96c08-134">오디오 회의 일반적인 질문</span><span class="sxs-lookup"><span data-stu-id="96c08-134">Audio Conferencing common questions</span></span>](/MicrosoftTeams/audio-conferencing-common-questions)
