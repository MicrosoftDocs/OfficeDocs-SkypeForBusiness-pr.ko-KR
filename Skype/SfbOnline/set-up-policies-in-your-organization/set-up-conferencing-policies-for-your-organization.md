---
title: 조직의 회의 정책 설정
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 9957722b-b542-49ad-8ec8-5569df7fb08b
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Setup
description: 회의는 비즈니스용 Skype Online의 중요 한 부분입니다. 사용자 그룹을 온라인으로 연결 하 여 슬라이드 및 비디오를 보고, 응용 프로그램을 공유 하 고, 파일을 교환 하 고, 다른 방법으로 통신 및 공동 작업할 수 있습니다.
ms.openlocfilehash: 20bb000cfe4cf2056877db07423b1c7791249b03
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2020
ms.locfileid: "44164467"
---
# <a name="set-up-conferencing-policies-for-your-organization"></a><span data-ttu-id="1ee47-103">조직의 회의 정책 설정</span><span class="sxs-lookup"><span data-stu-id="1ee47-103">Set up conferencing policies for your organization</span></span>

<span data-ttu-id="1ee47-104">회의는 비즈니스용 Skype Online의 중요 한 부분입니다. 사용자 그룹을 온라인으로 연결 하 여 슬라이드 및 비디오를 보고, 응용 프로그램을 공유 하 고, 파일을 교환 하 고, 다른 방법으로 통신 및 공동 작업할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ee47-104">Conferencing is an important part of Skype for Business Online: conferencing enables groups of users to come together online to view slides and video, share applications, exchange files, and otherwise communicate and collaborate.</span></span>
  
<span data-ttu-id="1ee47-105">회의 및 컨퍼런스 설정에 대 한 제어를 유지 관리 하는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ee47-105">It's important for you to maintain control over conferences and conference settings.</span></span> <span data-ttu-id="1ee47-106">경우에 따라 보안 문제가 있을 수 있습니다. 기본적으로 인증 되지 않은 사용자를 포함 하 여 모든 사용자가 모임에 참가 하 고 해당 모임 중에 배포 된 슬라이드나 유인물을 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ee47-106">In some cases, there might be security concerns: by default, anyone, including unauthenticated users, can participate in meetings and save any of the slides or handouts distributed during those meetings.</span></span> <span data-ttu-id="1ee47-107">또한 법적 관심사가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ee47-107">In addition, there might be occasional legal concerns.</span></span> <span data-ttu-id="1ee47-108">예를 들어 모임 참가자는 기본적으로 공유 콘텐츠에 주석을 만들 수 있습니다. 그러나 모임이 보관 될 때 이러한 주석은 저장 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1ee47-108">For example, by default ,meeting participants are allowed to make annotations on shared content; however, these annotations are not saved when the meeting is archived.</span></span> <span data-ttu-id="1ee47-109">조직에서 모든 전자 통신 기록을 유지 해야 하는 경우에는 주석을 사용 하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ee47-109">If your organization is required to keep a record of all electronic communication, you might want to disable annotations.</span></span> 
  
<span data-ttu-id="1ee47-110">비즈니스용 Skype Online에서 컨퍼런스는 회의 정책을 사용 하 여 관리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1ee47-110">In Skype for Business Online, conferences are managed by using conferencing policies.</span></span> <span data-ttu-id="1ee47-111">회의 정책은 회의에 참석할 수 있는 최대 사용자 수에 대 한 IP 오디오 및 비디오를 모임에 포함할 수 있는지 여부에 상관 없이, 회의에 사용할 수 있는 기능을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ee47-111">Conferencing policies determine the features and capabilities that can be used in a conference, including everything from whether or not the conference can include IP audio and video to the maximum number of people who can attend a meeting.</span></span> <span data-ttu-id="1ee47-112">회의 정책은 전역 범위 또는 사용자별 범위에서 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ee47-112">Conferencing policies can be configured at the global scope or at the per-user scope.</span></span> <span data-ttu-id="1ee47-113">이렇게 하면 관리자가 사용자에 게 제공 될 기능을 결정 하는 데 상당한 유연성을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ee47-113">This provides administrators with enormous flexibility when it comes to deciding which capabilities will be made available to which users.</span></span>
  
<span data-ttu-id="1ee47-114">정책을 만들 때 정책 설정을 구성 하거나, **Set-CsConferencingPolicy** cmdlet을 사용 하 여 기존 정책의 설정을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ee47-114">Policy settings can be configured at the time a policy is created, or you can use the **Set-CsConferencingPolicy** cmdlet to modify the settings of an existing policy.</span></span>
  
## <a name="set-your-conferencing-policies"></a><span data-ttu-id="1ee47-115">회의 정책 설정</span><span class="sxs-lookup"><span data-stu-id="1ee47-115">Set your conferencing policies</span></span>

> [!NOTE]
> <span data-ttu-id="1ee47-116">비즈니스용 Skype Online의 모든 회의 정책 설정에 대해 Windows PowerShell을 사용 해야 하며 **비즈니스용 skype 관리 센터**를 **사용할 수 없습니다** .</span><span class="sxs-lookup"><span data-stu-id="1ee47-116">For all of the conferencing policy settings in Skype for Business Online, you must use Windows PowerShell and you **can't use** the **Skype for Business admin center**.</span></span> 
  
### <a name="verify-and-start-windows-powershell"></a><span data-ttu-id="1ee47-117">Windows PowerShell 확인 및 시작</span><span class="sxs-lookup"><span data-stu-id="1ee47-117">Verify and start Windows PowerShell</span></span>

- <span data-ttu-id="1ee47-118">**Windows PowerShell 버전 3.0 이상을 실행 하 고 있는지 확인**</span><span class="sxs-lookup"><span data-stu-id="1ee47-118">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
    
    1. <span data-ttu-id="1ee47-119">버전 3.0 이상을 실행 하 고 있는지 확인 하려면 **시작 메뉴** > 에서**Windows PowerShell**을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ee47-119">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
        
    2. <span data-ttu-id="1ee47-120">**Windows PowerShell** 창에서 _Get-Host_ 를 입력 하 여 버전을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ee47-120">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
        
    3. <span data-ttu-id="1ee47-121">버전 3.0 이상이 없는 경우 Windows PowerShell 업데이트를 다운로드 하 여 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ee47-121">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell.</span></span> <span data-ttu-id="1ee47-122">Windows [Management 프레임 워크 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) 를 참조 하 여 windows PowerShell을 버전 4.0로 다운로드 하 고 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ee47-122">See [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0.</span></span> <span data-ttu-id="1ee47-123">메시지가 표시 되 면 컴퓨터를 다시 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ee47-123">Restart your computer when you are prompted.</span></span>
        
    4. <span data-ttu-id="1ee47-124">비즈니스용 skype Online에 연결 되는 원격 Windows PowerShell 세션을 만들 수 있는 비즈니스용 Skype Online 용 Windows PowerShell 모듈을 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ee47-124">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span> <span data-ttu-id="1ee47-125">이 모듈은 64 비트 컴퓨터 에서만 지원 되며 비즈니스용 [Skype Online 용 Windows PowerShell 모듈](https://go.microsoft.com/fwlink/?LinkId=294688)의 Microsoft 다운로드 센터에서 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ee47-125">This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688).</span></span> <span data-ttu-id="1ee47-126">메시지가 표시 되 면 컴퓨터를 다시 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ee47-126">Restart your computer if you are prompted.</span></span>
    
    <span data-ttu-id="1ee47-127">자세한 정보를 알고 싶은 경우에 [는 단일 Windows PowerShell 창에서 모든 Microsoft 365 또는 Office 365 서비스에 연결](https://technet.microsoft.com/library/dn568015.aspx)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1ee47-127">If you need to know more, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx).</span></span>
    
- <span data-ttu-id="1ee47-128">**Windows PowerShell 세션 시작**</span><span class="sxs-lookup"><span data-stu-id="1ee47-128">**Start a Windows PowerShell session**</span></span>
    
    1. <span data-ttu-id="1ee47-129">**시작 메뉴** > 에서**Windows PowerShell**을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ee47-129">From the **Start Menu** > **Windows PowerShell**.</span></span>
        
    2. <span data-ttu-id="1ee47-130">**Windows PowerShell** 창에서 다음을 실행 하 여 Microsoft 365 또는 Office 365에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ee47-130">In the **Windows PowerShell** window, connect to your Microsoft 365 or Office 365 by running:</span></span>
        
        > [!NOTE]
        > <span data-ttu-id="1ee47-131">비즈니스용 Skype Online Windows PowerShell 모듈을 처음 사용 하는 경우에만 **Import-Module** 명령을 실행 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1ee47-131">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>

       ```PowerShell      
        Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
        $credential = Get-Credential
        $session = New-CsOnlineSession -Credential $credential
        Import-PSSession $session
       ```

   <span data-ttu-id="1ee47-132">Windows PowerShell을 시작 하는 방법에 대 한 자세한 내용은 [단일 Windows powershell 창에서 모든 Microsoft 365 또는 Office 365 서비스에 연결](https://technet.microsoft.com/library/dn568015.aspx) 또는 [windows Powershell 용 컴퓨터 설정을](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1ee47-132">If you want more information about starting Windows PowerShell, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
    
### <a name="block-file-transfers-and-desktop-sharing-during-meetings"></a><span data-ttu-id="1ee47-133">모임 중 파일 전송 및 데스크톱 공유 차단</span><span class="sxs-lookup"><span data-stu-id="1ee47-133">Block file transfers and desktop sharing during meetings</span></span>

- <span data-ttu-id="1ee47-134">이러한 설정에 대 한 새 정책을 만들려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ee47-134">To create a new policy for these settings, run:</span></span>
   
   ```powershell
   New-CsConferencingPolicy -Identity DesktopConferencingPolicy -EnableAppDesktopSharing None  $true -EnableFileTransfer $false
   ```
   <span data-ttu-id="1ee47-135">[새로운 CsConferencingPolicy](https://technet.microsoft.com/library/mt779148.aspx) cmdlet에 대 한 자세한 내용을 확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="1ee47-135">See more on the [New-CsConferencingPolicy](https://technet.microsoft.com/library/mt779148.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="1ee47-136">만든 새 정책을 조직의 모든 사용자에 게 부여 하려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ee47-136">To grant the new policy you created to all users in your organization, run:</span></span>
   
   ```powershell
   Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName DesktopConferencingPolicy
   ```
   <span data-ttu-id="1ee47-137">[CsConferencingPolicy](https://technet.microsoft.com/library/mt779156.aspx) cmdlet에 대 한 자세한 내용을 확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="1ee47-137">See more on the [Grant-CsConferencingPolicy](https://technet.microsoft.com/library/mt779156.aspx) cmdlet.</span></span>
    
  <span data-ttu-id="1ee47-138">이미 정책을 만든 경우 [CsConferencingPolicy](https://technet.microsoft.com/library/mt779157.aspx) cmdlet을 사용 하 여 기존 정책을 변경한 다음[부여-CsConferencingPolicy](https://technet.microsoft.com/library/mt779156.aspx) cmdlet을 사용 하 여 사용자에 게 설정을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ee47-138">If you have already created a policy, you can use the [Set-CsConferencingPolicy](https://technet.microsoft.com/library/mt779157.aspx) cmdlet to make changes to the existing policy, and then use the[Grant-CsConferencingPolicy](https://technet.microsoft.com/library/mt779156.aspx) cmdlet to apply the settings to your users.</span></span>
  
### <a name="block-recording-of-conferences-and-prevent-anonymous-meeting-participants"></a><span data-ttu-id="1ee47-139">회의 기록을 차단 하 고 익명 모임 참가자 방지</span><span class="sxs-lookup"><span data-stu-id="1ee47-139">Block recording of conferences and prevent anonymous meeting participants</span></span>

- <span data-ttu-id="1ee47-140">이러한 설정에 대 한 새 정책을 만들려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ee47-140">To create a new policy for these settings, run:</span></span> 
   
   ```powershell
   New-CsConferencingPolicy -Identity ConferencingPolicy -AllowAnonymousParticipantsInMeetings  $false -AllowConferenceRecording $false
   ```
   <span data-ttu-id="1ee47-141">[새로운 CsConferencingPolicy](https://technet.microsoft.com/library/mt779148.aspx) cmdlet에 대 한 자세한 내용을 확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="1ee47-141">See more on the [New-CsConferencingPolicy](https://technet.microsoft.com/library/mt779148.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="1ee47-142">만든 새 정책을 Amos 대리석에 부여 하려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ee47-142">To grant the new policy you created to Amos Marble, run:</span></span>
   
   ```powershell
    Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName ConferencingPolicy
   ```
   <span data-ttu-id="1ee47-143">[CsConferencingPolicy](https://technet.microsoft.com/library/mt779156.aspx) cmdlet에 대 한 자세한 내용을 확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="1ee47-143">See more on the [Grant-CsConferencingPolicy](https://technet.microsoft.com/library/mt779156.aspx) cmdlet.</span></span>
    
<span data-ttu-id="1ee47-144">이미 정책을 만든 경우 [CsConferencingPolicy](https://technet.microsoft.com/library/mt779157.aspx) cmdlet을 사용 하 여 기존 정책을 변경한 다음 [부여-CsConferencingPolicy](https://technet.microsoft.com/library/mt779156.aspx) cmdlet을 사용 하 여 사용자에 게 설정을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ee47-144">If you have already created a policy, you can use the [Set-CsConferencingPolicy](https://technet.microsoft.com/library/mt779157.aspx) cmdlet to make changes to the existing policy, and then use the [Grant-CsConferencingPolicy](https://technet.microsoft.com/library/mt779156.aspx) cmdlet to apply the settings to your users.</span></span>
  
### <a name="block-anonymous-participants-from-recording-meetings-and-external-users-from-saving-meeting-content"></a><span data-ttu-id="1ee47-145">모임 콘텐츠를 저장 하지 못하도록 익명 참가자가 모임 및 외부 사용자 기록 차단</span><span class="sxs-lookup"><span data-stu-id="1ee47-145">Block anonymous participants from recording meetings and external users from saving meeting content</span></span>

- <span data-ttu-id="1ee47-146">이러한 설정에 대 한 새 정책을 만들려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ee47-146">To create a new policy for these settings, run:</span></span>  
   
   ```powershell
   New-CsConferencingPolicy -Identity BlockedConferencingPolicy  -AllowExternalUsersToRecordMeeting  $false -AllowExternalUsersToSaveContent $false 
   ```
   <span data-ttu-id="1ee47-147">[새로운 CsConferencingPolicy](https://technet.microsoft.com/library/mt779148.aspx) cmdlet에 대 한 자세한 내용을 확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="1ee47-147">See more on the [New-CsConferencingPolicy](https://technet.microsoft.com/library/mt779148.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="1ee47-148">만든 새 정책을 조직의 모든 사용자에 게 부여 하려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ee47-148">To grant the new policy you created to all of the users in your organization, run:</span></span>
    
 
   ```powershell
   Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName BlockedConferencingPolicy
   ```

<span data-ttu-id="1ee47-149">[CsConferencingPolicy](https://technet.microsoft.com/library/mt779156.aspx) cmdlet에 대 한 자세한 내용을 확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="1ee47-149">See more on the [Grant-CsConferencingPolicy](https://technet.microsoft.com/library/mt779156.aspx) cmdlet.</span></span>
    
<span data-ttu-id="1ee47-150">이미 정책을 만든 경우 [CsConferencingPolicy](https://technet.microsoft.com/library/mt779157.aspx) cmdlet을 사용 하 여 기존 정책을 변경한 다음[부여-CsConferencingPolicy](https://technet.microsoft.com/library/mt779156.aspx) cmdlet을 사용 하 여 사용자에 게 설정을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ee47-150">If you have already created a policy, you can use the [Set-CsConferencingPolicy](https://technet.microsoft.com/library/mt779157.aspx) cmdlet to make changes to the existing policy, and then use the[Grant-CsConferencingPolicy](https://technet.microsoft.com/library/mt779156.aspx) cmdlet to apply the settings to your users.</span></span>
  
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="1ee47-151">Windows PowerShell에 대 한 자세한 정보를 확인 하 고 싶으신가요?</span><span class="sxs-lookup"><span data-stu-id="1ee47-151">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="1ee47-152">Windows PowerShell은 사용자 및 허용 되지 않거나 수행할 수 있는 사용자를 관리 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ee47-152">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="1ee47-153">Windows PowerShell을 사용 하면 여러 작업을 수행할 때 일상 업무를 단순화할 수 있는 단일 관리 지점을 사용 하 여 Microsoft 365 또는 Office 365 및 비즈니스용 Skype Online을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ee47-153">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="1ee47-154">Windows PowerShell을 시작 하려면 다음 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1ee47-154">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="1ee47-155">Windows PowerShell 및 Lync Online 소개</span><span class="sxs-lookup"><span data-stu-id="1ee47-155">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="1ee47-156">Windows PowerShell을 사용 하 여 Microsoft 365 또는 Office 365을 관리 해야 하는 여섯 가지 이유</span><span class="sxs-lookup"><span data-stu-id="1ee47-156">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Microsoft 365 or Office 365</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="1ee47-157">Windows PowerShell에는 한 번에 여러 사용자의 설정을 변경 하는 경우와 같이 Microsoft 365 관리 센터를 사용 하는 경우에만 속도, 단순성, 생산성 등 다양 한 이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ee47-157">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="1ee47-158">다음 항목에서 이러한 이점에 대해 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="1ee47-158">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="1ee47-159">Windows PowerShell을 사용 하 여 Microsoft 365 또는 Office 365을 관리 하는 최상의 방법</span><span class="sxs-lookup"><span data-stu-id="1ee47-159">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="1ee47-160">Windows PowerShell을 사용 하 여 비즈니스용 Skype Online 관리</span><span class="sxs-lookup"><span data-stu-id="1ee47-160">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="1ee47-161">Windows PowerShell을 사용 하 여 일반적인 비즈니스용 Skype Online 관리 작업 수행</span><span class="sxs-lookup"><span data-stu-id="1ee47-161">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a><span data-ttu-id="1ee47-162">관련 항목</span><span class="sxs-lookup"><span data-stu-id="1ee47-162">Related topics</span></span>
[<span data-ttu-id="1ee47-163">사용자 지정 외부 액세스 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="1ee47-163">Create custom external access policies</span></span>](create-custom-external-access-policies.md)

[<span data-ttu-id="1ee47-164">점 대 점 파일 전송 차단</span><span class="sxs-lookup"><span data-stu-id="1ee47-164">Block point-to-point file transfers</span></span>](block-point-to-point-file-transfers.md)

[<span data-ttu-id="1ee47-165">조직의 클라이언트 정책 설정</span><span class="sxs-lookup"><span data-stu-id="1ee47-165">Set up client policies for your organization</span></span>](set-up-client-policies-for-your-organization.md)

  
 
