---
title: 비즈니스용 Skype Online에서 오디오 회의 모임에 대 한 PIN 길이 설정
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: b86d31c6-1543-478f-b8c6-4b71e708403a
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
description: PIN의 길이 및 요구 사항에 대 한 매개 변수를 알아보고 비즈니스용 Skype에서 모임의 길이를 설정 하는 방법을 알아봅니다.
ms.openlocfilehash: 9e1be77b18c5b416d220ce5d7432562888ce5752
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2020
ms.locfileid: "44164537"
---
# <a name="set-the-pin-length-for-audio-conferencing-meetings-in-skype-for-business-online"></a><span data-ttu-id="83768-103">비즈니스용 Skype Online에서 오디오 회의 모임에 대 한 PIN 길이 설정</span><span class="sxs-lookup"><span data-stu-id="83768-103">Set the PIN length for Audio Conferencing meetings in Skype for Business Online</span></span>


> [!NOTE]
> <span data-ttu-id="83768-104">Microsoft 팀에서 PIN 길이를 설정 하는 방법에 대 한 자세한 내용은 [Microsoft 팀에서 오디오 회의 모임에 대 한 pin 길이](/en-us/MicrosoftTeams/Set-the-PIN-length-for-Audio-Conferencing-meetings-in-teams)설정을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="83768-104">For information about setting the PIN length in Microsoft Teams, see [Set the PIN length for Audio Conferencing meetings in Microsoft Teams](/en-us/MicrosoftTeams/Set-the-PIN-length-for-Audio-Conferencing-meetings-in-teams).</span></span>

<span data-ttu-id="83768-105">비즈니스용 Skype에 대 한 오디오 회의를 설정 하는 경우 오디오 회의 브리지가 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="83768-105">When you are setting up audio conferencing for Skype for Business, you will get an audio conferencing bridge.</span></span> <span data-ttu-id="83768-106">회의 브리지에는 하나 이상의 전화 번호가 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83768-106">A conferencing bridge can contain one or more phone numbers.</span></span> <span data-ttu-id="83768-107">설정한 전화 번호는 비즈니스용 Skype 앱에 대 한 모임 초대에 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="83768-107">The phone number you set will be included on the meeting invites for the Skype for Business app.</span></span>
  
<span data-ttu-id="83768-108">오디오 회의 브리지는 전화기를 사용하여 모임에 전화를 거는 사람들의 통화에 응답합니다.</span><span class="sxs-lookup"><span data-stu-id="83768-108">The audio conferencing bridge answers a call for people who are dialing in to a meeting using a phone.</span></span> <span data-ttu-id="83768-109">자동 전화 교환에서 음성 메시지가 표시 된 호출자에 게 응답 한 다음 설정에 따라 알림을 재생 하 고 호출자에 게 해당 이름을 기록 하도록 요청할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83768-109">It answers the caller with voice prompts from an auto attendant and then, depending on your settings, can play notifications and ask callers to record their name.</span></span> <span data-ttu-id="83768-110">**Microsoft bridge 설정을** 사용 하 여 모임 알림과 모임 참가 환경에 대 한 설정을 변경 하 고 모임 이끌이가 사용 하는 핀 길이를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83768-110">**Microsoft bridge settings** allow you to change the settings for meeting notifications and the meeting join experience, and set the length of the PINs that are used by meeting organizers.</span></span> <span data-ttu-id="83768-111">모임 이끌이는 비즈니스용 Skype 앱을 사용 하 여 모임에 참가할 수 없는 경우 모임을 시작 하기 위해 Pin을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="83768-111">Meeting organizers use PINs to start meetings if they can't join the meeting using the Skype for Business app.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="setting-the-pin-length"></a><span data-ttu-id="83768-112">PIN 길이 설정</span><span class="sxs-lookup"><span data-stu-id="83768-112">Setting the PIN length</span></span>
 
1. <span data-ttu-id="83768-113">**비즈니스용 Skype 관리 센터**의 왼쪽 탐색 창에서 **오디오 회의** > **Microsoft bridge 설정**으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="83768-113">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
2. <span data-ttu-id="83768-114">**보안** > **pin 길이**에서 PIN에 대해 원하는 자릿수를 선택한 다음 **저장**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="83768-114">Under **Security** > **PIN length**, select the number of digits you want for the PIN, and then click **Save**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="83768-115">PIN이 전화 회의 ID와 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="83768-115">A PIN is different from a conference ID.</span></span> <span data-ttu-id="83768-116">회의 Id는 발신자가 모임에 참가할 때 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="83768-116">Conference IDs are used by callers when they join the meeting.</span></span> <span data-ttu-id="83768-117">회의를 식별 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="83768-117">They are used to identify the meeting.</span></span> <span data-ttu-id="83768-118">PIN은 모임 이끌이로 서 호출자를 인증 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="83768-118">The PIN is used to authenticate a caller as the meeting organizer.</span></span> 

## <a name="want-to-know-more-about-pin-settings"></a><span data-ttu-id="83768-119">PIN 설정에 대 한 자세한 내용을 확인 하 고 싶으신가요?</span><span class="sxs-lookup"><span data-stu-id="83768-119">Want to know more about PIN settings?</span></span>

- <span data-ttu-id="83768-120">Pin의 자릿수는 4 ~ 12 자리입니다. 기본값은 5입니다.</span><span class="sxs-lookup"><span data-stu-id="83768-120">PINs can be from 4 to 12 digits; the default is 5.</span></span> <span data-ttu-id="83768-121">숫자는 핀을 만들 때만 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="83768-121">Numbers are only used when creating PINs.</span></span> <span data-ttu-id="83768-122">문자 및 특수 문자는 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="83768-122">Letters and special characters aren't used.</span></span>
    
- <span data-ttu-id="83768-123">PIN은 비즈니스용 Skype 사용자가 아직 모임을 시작 하지 않은 경우 모임 이끌이에게만 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="83768-123">A PIN is only required for the meeting organizer when a Skype for Business user hasn't already started the meeting.</span></span> <span data-ttu-id="83768-124">모든 사용자가 모임에 전화를 거는 경우 모임 이끌이가 모임을 시작 하려면 PIN이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="83768-124">If everyone is dialing in to the meeting, then the PIN is required for the meeting organizer to start the meeting.</span></span>
    
- <span data-ttu-id="83768-125">PIN 보안 설정은 Microsoft bridge와 연결 된 모든 전화 번호에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="83768-125">PIN security settings are applied to all of the phone numbers that are associated with a Microsoft bridge.</span></span> <span data-ttu-id="83768-126">해당 브리지에 연결 된 전화 번호를 사용 하는 모든 모임에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="83768-126">They will be applied to all meetings that use the phone numbers associated with a given bridge.</span></span> 
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="83768-127">Windows PowerShell을 사용 하 여 관리 하는 방법을 알고 싶으세요?</span><span class="sxs-lookup"><span data-stu-id="83768-127">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="83768-128">시간을 절약 하거나이 작업을 자동화 하려면 [Set-사용](https://go.microsoft.com/fwlink/?LinkId=715757) cmdlet을 사용 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="83768-128">To save time or automate this, you can use the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757) cmdlet.</span></span>
    
- <span data-ttu-id="83768-129">PIN의 숫자를 8로 설정 하려면 다음을 실행 합니다.`Set-CsOnlineDialInConferencingTenantSettings -PinLength 8`</span><span class="sxs-lookup"><span data-stu-id="83768-129">To set the number of digits in the PIN to 8:  `Set-CsOnlineDialInConferencingTenantSettings -PinLength 8`</span></span>
    
- <span data-ttu-id="83768-130">Windows PowerShell은 사용자 및 허용 되지 않거나 수행할 수 있는 사용자를 관리 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="83768-130">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="83768-131">Windows PowerShell을 사용 하면 여러 작업을 수행할 때 일상 업무를 단순화할 수 있는 단일 관리 지점을 사용 하 여 Microsoft 365 또는 Office 365를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83768-131">With Windows PowerShell, you can manage Microsoft 365 or Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="83768-132">Windows PowerShell을 시작 하려면 다음 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="83768-132">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="83768-133">Microsoft 365 또는 Office 365 PowerShell을 사용 해야 하는 이유</span><span class="sxs-lookup"><span data-stu-id="83768-133">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="83768-134">Windows PowerShell을 사용 하 여 Microsoft 365 또는 Office 365을 관리 하는 최상의 방법</span><span class="sxs-lookup"><span data-stu-id="83768-134">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="83768-135">Windows PowerShell에는 한 번에 여러 사용자의 설정을 변경 하는 경우와 같이 Microsoft 365 관리 센터를 사용 하는 경우에만 속도, 단순성, 생산성 등 다양 한 이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83768-135">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center, such as when you are making settings changes for many users at one time.</span></span> <span data-ttu-id="83768-136">다음 항목에서 이러한 이점에 대해 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="83768-136">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="83768-137">Windows PowerShell 및 Lync Online 소개</span><span class="sxs-lookup"><span data-stu-id="83768-137">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="83768-138">Windows PowerShell을 사용 하 여 비즈니스용 Skype Online 관리</span><span class="sxs-lookup"><span data-stu-id="83768-138">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
    [<span data-ttu-id="83768-139">Windows PowerShell을 사용 하 여 비즈니스용 Skype Online 관리</span><span class="sxs-lookup"><span data-stu-id="83768-139">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="83768-140">Windows PowerShell을 사용 하 여 일반적인 비즈니스용 Skype Online 관리 작업 수행</span><span class="sxs-lookup"><span data-stu-id="83768-140">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="83768-141">비즈니스용 Skype Online 용 Windows PowerShell 모듈을 사용 하면 비즈니스용 Skype Online에 연결 하는 원격 Windows PowerShell 세션을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83768-141">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span> <span data-ttu-id="83768-142">이 모듈은 64 비트 컴퓨터 에서만 지원 되며 비즈니스용 [Skype Online 용 Windows PowerShell 모듈](https://go.microsoft.com/fwlink/?LinkId=294688) 의 Microsoft 다운로드 센터에서 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83768-142">This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="see-also"></a><span data-ttu-id="83768-143">참고 항목</span><span class="sxs-lookup"><span data-stu-id="83768-143">See also</span></span>

[<span data-ttu-id="83768-144">Microsoft 365 또는 Office 365에서 오디오 회의 체험 또는 구매</span><span class="sxs-lookup"><span data-stu-id="83768-144">Try or purchase Audio Conferencing in Microsoft 365 or Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
