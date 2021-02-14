---
title: 사용자가 비즈니스용 Skype Online에서 모임에 참가할 때 자신의 이름을 기록할 수 있도록 설정
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
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 사용자가 비즈니스용 Skype Online에서 모임에 참가할 때 자신의 이름을 기록할 수 있는지 여부를 설정하거나 사용하지 않도록 설정하는 방법을 배워야 합니다.
ms.openlocfilehash: d6bb98c2d3c6b12479aea4fbdfdc717491c9893e
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2020
ms.locfileid: "44164157"
---
# <a name="enable-users-to-record-their-name-when-they-join-a-meeting-in-skype-for-business-online"></a><span data-ttu-id="22aaf-103">사용자가 비즈니스용 Skype Online에서 모임에 참가할 때 자신의 이름을 기록할 수 있도록 설정</span><span class="sxs-lookup"><span data-stu-id="22aaf-103">Enable users to record their name when they join a meeting in Skype for Business Online</span></span>

> [!Note]
> <span data-ttu-id="22aaf-104">사용자가 Teams에서 자신의 이름을 기록할 수 있도록 허용하려면 사용자가 Microsoft Teams에서 모임에 참가할 때 자신의 이름을 기록할 수 있도록 허용을 [참조합니다.](/MicrosoftTeams/enable-users-to-record-their-name-when-they-join-a-meeting-in-teams)</span><span class="sxs-lookup"><span data-stu-id="22aaf-104">If you want to allow users to record their names in Teams, see [Enable users to record their name when they join a meeting in Microsoft Teams](/MicrosoftTeams/enable-users-to-record-their-name-when-they-join-a-meeting-in-teams).</span></span>

<span data-ttu-id="22aaf-105">Microsoft 365 또는 Office 365에서 오디오 회의를 설정하는 경우 전화 번호와 오디오 회의 브리지라는 것을 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="22aaf-105">When you are setting up Audio Conferencing in Microsoft 365 or Office 365, you will receive phone numbers and what is called an audio conferencing bridge.</span></span> <span data-ttu-id="22aaf-106">회의 브리지에는 전용 또는 공유 전화 번호일 수 있는 하나 이상의 전화 번호가 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22aaf-106">A conferencing bridge can contain one or more phone numbers that can be a dedicated or shared phone number.</span></span>
  
<span data-ttu-id="22aaf-107">회의 브리지는 전화기를 사용하여 모임에 전화 접속하는 사용자의 통화에 응답합니다.</span><span class="sxs-lookup"><span data-stu-id="22aaf-107">The conferencing bridge answers a call for a user who is dialing in to a meeting using a phone.</span></span> <span data-ttu-id="22aaf-108">회의 브리지는 자동 전화 회의에서 음성 프롬프트로 발신자에 응답한 다음 설정에 따라 알림을 재생하고 발신자 이름을 기록해 달라고 요청하고 모임 이끌이에 대한 PIN 보안을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22aaf-108">The conferencing bridge answers the caller with voice prompts from an auto attendant, and then, depending on their settings, can play notifications, ask callers to record their name, and set up the PIN security for meeting organizers.</span></span> <span data-ttu-id="22aaf-109">모임 이끌이가 모임을 시작할 수 있도록 PINS가 부여됩니다.</span><span class="sxs-lookup"><span data-stu-id="22aaf-109">PINs are given to meeting organizers to allow them to start a meeting.</span></span> <span data-ttu-id="22aaf-110">그러나 PIN이 모임을 시작할 필요는 없는 경우 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22aaf-110">However, you can set it up so a PIN isn't required to start a meeting.</span></span>

## <a name="set-whether-callers-should-record-their-name"></a><span data-ttu-id="22aaf-111">호출자 이름을 기록해야 하는지 여부 설정</span><span class="sxs-lookup"><span data-stu-id="22aaf-111">Set whether callers should record their name</span></span>
    
1. <span data-ttu-id="22aaf-112">비즈니스용 Skype 관리 **센터의** 왼쪽 탐색 모음에서 **오디오** 회의 Microsoft 브리지  >  **설정으로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="22aaf-112">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
2. <span data-ttu-id="22aaf-113">모임 **참가 환경 아래에서** 모임 입장 및 퇴장 알림 설정이 켜져 있는 확인란을 **참조하세요.**</span><span class="sxs-lookup"><span data-stu-id="22aaf-113">Under **Meeting join experience**, see the check box labeled **Enable meeting entry and exit notifications to be turned on**.</span></span>
    
   - <span data-ttu-id="22aaf-114">**선택** 발신자는 모임에 입장하기 전에 이름을 기록할지 묻는 요청이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="22aaf-114">**Selected** Callers will be asked to record their name before they enter the meeting.</span></span> <span data-ttu-id="22aaf-115">기본적으로 선택되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22aaf-115">This is selected by default.</span></span>
    
   - <span data-ttu-id="22aaf-116">**지우기** 발신자는 모임에 입장하기 전에 이름을 기록할지 묻는 요청이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="22aaf-116">**Cleared** Callers won't be asked to record their name before they enter the meeting.</span></span>
    
3. <span data-ttu-id="22aaf-117">변경한 후 저장을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="22aaf-117">After you make your changes, click **Save**.</span></span>
    
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="22aaf-118">사용자 계정으로 관리하는 방법을 알고 Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="22aaf-118">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="22aaf-119">시간을 절약하거나 이 작업을 자동화하기 위해 [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757) cmdlet을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22aaf-119">To save time or automate this, you can use the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757) cmdlet.</span></span>
    
- <span data-ttu-id="22aaf-120">Windows PowerShell 관리는 사용자 및 사용자가 허용하는 작업을 관리하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="22aaf-120">Windows PowerShell is all about managing users and what users are allowed to do.</span></span> <span data-ttu-id="22aaf-121">이 Windows PowerShell 여러 작업을 수행할 때 일상적인 작업을 간소화할 수 있는 단일 관리 지점을 사용하여 Microsoft 365 또는 Office 365를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22aaf-121">With Windows PowerShell, you can manage Microsoft 365 or Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="22aaf-122">다음 항목을 Windows PowerShell 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="22aaf-122">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="22aaf-123">Microsoft 365 또는 Office 365 PowerShell을 사용하는 이유</span><span class="sxs-lookup"><span data-stu-id="22aaf-123">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="22aaf-124">Microsoft 365 또는 Office 365를 관리하는 가장 좋은 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="22aaf-124">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="22aaf-125">Windows PowerShell Microsoft 365 관리 센터를 사용하는 것 이상으로 속도, 단순성 및 생산성에 많은 이점이 있습니다. 예를 들어 한 번으로 많은 사용자를 위한 설정을 변경할 때도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22aaf-125">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center, such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="22aaf-126">다음 항목에서 이러한 이점에 대해 자세히 배워야 합니다.</span><span class="sxs-lookup"><span data-stu-id="22aaf-126">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="22aaf-127">Windows PowerShell 및 Lync Online 소개</span><span class="sxs-lookup"><span data-stu-id="22aaf-127">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="22aaf-128">비즈니스 Windows PowerShell 사용하여 비즈니스용 Skype Online 관리</span><span class="sxs-lookup"><span data-stu-id="22aaf-128">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="22aaf-129">비즈니스용 Windows PowerShell Skype Online 관리 작업을 수행하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22aaf-129">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="22aaf-130">비즈니스 Windows PowerShell용 Skype Online 모듈을 사용하면 비즈니스용 Skype Online에 Windows PowerShell 원격 세션을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22aaf-130">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span> <span data-ttu-id="22aaf-131">64비트 컴퓨터에서만 지원되는 이 모듈은 비즈니스용 [Skype Online용](https://go.microsoft.com/fwlink/?LinkId=294688) Windows PowerShell 모듈의 Microsoft 다운로드 센터에서 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22aaf-131">This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="22aaf-132">관련 항목</span><span class="sxs-lookup"><span data-stu-id="22aaf-132">Related topics</span></span>

[<span data-ttu-id="22aaf-133">Microsoft 365 또는 Office 365에서 오디오 회의 시도 또는 구매</span><span class="sxs-lookup"><span data-stu-id="22aaf-133">Try or purchase Audio Conferencing in Microsoft 365 or Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
