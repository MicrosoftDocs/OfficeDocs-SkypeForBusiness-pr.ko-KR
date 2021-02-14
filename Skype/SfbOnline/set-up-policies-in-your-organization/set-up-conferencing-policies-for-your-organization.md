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
description: 회의는 비즈니스용 Skype Online의 중요한 부분입니다. 회의를 사용하면 사용자 그룹이 온라인으로 모여 슬라이드와 비디오를 보고, 응용 프로그램을 공유하고, 파일을 교환하고, 통신 및 공동 작업을 할 수 있습니다.
ms.openlocfilehash: f5b420b9a5f288a0c733d3dfdc7ebc45fb323f32
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814757"
---
# <a name="set-up-conferencing-policies-for-your-organization"></a><span data-ttu-id="0e6c5-103">조직의 회의 정책 설정</span><span class="sxs-lookup"><span data-stu-id="0e6c5-103">Set up conferencing policies for your organization</span></span>

<span data-ttu-id="0e6c5-104">회의는 비즈니스용 Skype Online의 중요한 부분입니다. 회의를 사용하면 사용자 그룹이 온라인으로 모여 슬라이드와 비디오를 보고, 응용 프로그램을 공유하고, 파일을 교환하고, 통신 및 공동 작업을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e6c5-104">Conferencing is an important part of Skype for Business Online: conferencing enables groups of users to come together online to view slides and video, share applications, exchange files, and otherwise communicate and collaborate.</span></span>
  
<span data-ttu-id="0e6c5-105">회의 및 회의 설정을 제어하는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="0e6c5-105">It's important for you to maintain control over conferences and conference settings.</span></span> <span data-ttu-id="0e6c5-106">경우에 따라 보안 문제가 있을 수 있습니다. 기본적으로, 비인식 사용자를 포함한 모든 사용자는 모임에 참가하고 해당 모임 중에 배포된 슬라이드 또는 유인물 중 일부를 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e6c5-106">In some cases, there might be security concerns: by default, anyone, including unauthenticated users, can participate in meetings and save any of the slides or handouts distributed during those meetings.</span></span> <span data-ttu-id="0e6c5-107">또한 경우에 따라 법적 문제가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e6c5-107">In addition, there might be occasional legal concerns.</span></span> <span data-ttu-id="0e6c5-108">예를 들어 기본적으로 모임 참가자는 공유 콘텐츠에 대한 주석을 만들 수 있습니다. 그러나 이러한 주석은 모임이 보관될 때 저장되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0e6c5-108">For example, by default ,meeting participants are allowed to make annotations on shared content; however, these annotations are not saved when the meeting is archived.</span></span> <span data-ttu-id="0e6c5-109">조직에서 모든 전자 통신의 기록을 유지해야 하는 경우 주석을 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e6c5-109">If your organization is required to keep a record of all electronic communication, you might want to disable annotations.</span></span> 
  
<span data-ttu-id="0e6c5-110">비즈니스용 Skype Online에서는 회의 정책을 사용하여 회의를 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="0e6c5-110">In Skype for Business Online, conferences are managed by using conferencing policies.</span></span> <span data-ttu-id="0e6c5-111">회의 정책은 회의에 IP 오디오 및 비디오를 포함할 수 있는지 여부부터 모임에 참가할 수 있는 최대 사용자 수에 대한 모든 것을 포함하여 회의에 사용할 수 있는 기능 및 기능을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="0e6c5-111">Conferencing policies determine the features and capabilities that can be used in a conference, including everything from whether or not the conference can include IP audio and video to the maximum number of people who can attend a meeting.</span></span> <span data-ttu-id="0e6c5-112">회의 정책은 전역 범위 또는 사용자당 범위에서 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e6c5-112">Conferencing policies can be configured at the global scope or at the per-user scope.</span></span> <span data-ttu-id="0e6c5-113">이렇게 하면 관리자가 어떤 사용자가 사용할 수 있게 될 기능을 결정해야 하는지 결정하기에 많은 유연성이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="0e6c5-113">This provides administrators with enormous flexibility when it comes to deciding which capabilities will be made available to which users.</span></span>
  
<span data-ttu-id="0e6c5-114">정책을 만들 때 정책 설정을 구성하거나 **Set-CsConferencingPolicy** cmdlet을 사용하여 기존 정책의 설정을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e6c5-114">Policy settings can be configured at the time a policy is created, or you can use the **Set-CsConferencingPolicy** cmdlet to modify the settings of an existing policy.</span></span>
  
## <a name="set-your-conferencing-policies"></a><span data-ttu-id="0e6c5-115">회의 정책 설정</span><span class="sxs-lookup"><span data-stu-id="0e6c5-115">Set your conferencing policies</span></span>

> [!NOTE]
> <span data-ttu-id="0e6c5-116">비즈니스용 Skype Online의 모든 회의 정책 설정에 대해 Windows PowerShell 비즈니스용 Skype  관리 센터를 사용할 **수 없습니다.**</span><span class="sxs-lookup"><span data-stu-id="0e6c5-116">For all of the conferencing policy settings in Skype for Business Online, you must use Windows PowerShell and you **can't use** the **Skype for Business admin center**.</span></span> 
  
### <a name="verify-and-start-windows-powershell"></a><span data-ttu-id="0e6c5-117">확인 및 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="0e6c5-117">Verify and start Windows PowerShell</span></span>

- <span data-ttu-id="0e6c5-118">**버전 3.0 Windows PowerShell 실행 중인지 확인**</span><span class="sxs-lookup"><span data-stu-id="0e6c5-118">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
    
    1. <span data-ttu-id="0e6c5-119">버전 3.0 이상을 실행하고 있는지 확인: 시작 메뉴를  >  Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0e6c5-119">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
        
    2. <span data-ttu-id="0e6c5-120">웹 창에  _Get-Host를_ 입력하여 **Windows PowerShell** 확인</span><span class="sxs-lookup"><span data-stu-id="0e6c5-120">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
        
    3. <span data-ttu-id="0e6c5-121">버전 3.0 이상이 없는 경우 업데이트를 다운로드하여 설치해야 Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0e6c5-121">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell.</span></span> <span data-ttu-id="0e6c5-122">버전 [Windows Management Framework 4.0으로](https://go.microsoft.com/fwlink/?LinkId=716845) Windows PowerShell 다운로드하고 업데이트하려면 4.0을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="0e6c5-122">See [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0.</span></span> <span data-ttu-id="0e6c5-123">메시지가 표시될 때 컴퓨터를 다시 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="0e6c5-123">Restart your computer when you are prompted.</span></span>
        
    4. <span data-ttu-id="0e6c5-124">또한 비즈니스용 Skype Online에 연결하는 원격 Windows PowerShell 세션을 만들 수 있는 Teams용 Windows PowerShell 모듈을 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0e6c5-124">You will also need to install the Windows PowerShell module for Teams that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span>
    
    <span data-ttu-id="0e6c5-125">자세한 내용은 단일 창에서 모든 [Microsoft 365 또는 Office 365 서비스에 Windows PowerShell 참조합니다.](https://technet.microsoft.com/library/dn568015.aspx)</span><span class="sxs-lookup"><span data-stu-id="0e6c5-125">If you need to know more, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx).</span></span>
    
- <span data-ttu-id="0e6c5-126">**세션 Windows PowerShell 시작**</span><span class="sxs-lookup"><span data-stu-id="0e6c5-126">**Start a Windows PowerShell session**</span></span>
    
    1. <span data-ttu-id="0e6c5-127">시작 **메뉴에서**  >  **Windows PowerShell.**</span><span class="sxs-lookup"><span data-stu-id="0e6c5-127">From the **Start Menu** > **Windows PowerShell**.</span></span>
        
    2. <span data-ttu-id="0e6c5-128">다음 **Windows PowerShell** 실행하여 Microsoft 365 또는 Office 365에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="0e6c5-128">In the **Windows PowerShell** window, connect to your Microsoft 365 or Office 365 by running:</span></span>
        
     > [!NOTE]
     > <span data-ttu-id="0e6c5-129">비즈니스용 Skype Online Connector는 현재 최신 Teams PowerShell 모듈의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="0e6c5-129">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span>
     >
     > <span data-ttu-id="0e6c5-130">최신 [Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/)공개 릴리스를 사용하는 경우 비즈니스용 Skype Online Connector를 설치할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0e6c5-130">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

       ```PowerShell      
        Import-Module -Name MicrosoftTeams
        $credential = Get-Credential
        $session = New-CsOnlineSession -Credential $credential
        Import-PSSession $session
       ```

   <span data-ttu-id="0e6c5-131">Windows PowerShell 시작에 대한 자세한 내용은 단일 Windows PowerShell 창에서 모든 [Microsoft 365 또는 Office 365](https://technet.microsoft.com/library/dn568015.aspx) 서비스에 연결 또는 [Windows PowerShell.](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="0e6c5-131">If you want more information about starting Windows PowerShell, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
    
### <a name="block-file-transfers-and-desktop-sharing-during-meetings"></a><span data-ttu-id="0e6c5-132">모임 중에 파일 전송 및 데스크톱 공유 차단</span><span class="sxs-lookup"><span data-stu-id="0e6c5-132">Block file transfers and desktop sharing during meetings</span></span>

- <span data-ttu-id="0e6c5-133">이러한 설정에 대한 새 정책을 만들하려면 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="0e6c5-133">To create a new policy for these settings, run:</span></span>
   
   ```powershell
   New-CsConferencingPolicy -Identity DesktopConferencingPolicy -EnableAppDesktopSharing None  $true -EnableFileTransfer $false
   ```
   <span data-ttu-id="0e6c5-134">[New-CsConferencingPolicy](https://technet.microsoft.com/library/mt779148.aspx) cmdlet에 대한 자세한 내용은 다음을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="0e6c5-134">See more on the [New-CsConferencingPolicy](https://technet.microsoft.com/library/mt779148.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="0e6c5-135">만든 새 정책을 조직의 모든 사용자에게 부여하기 위해 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="0e6c5-135">To grant the new policy you created to all users in your organization, run:</span></span>
   
   ```powershell
   Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName DesktopConferencingPolicy
   ```
   <span data-ttu-id="0e6c5-136">[Grant-CsConferencingPolicy](https://technet.microsoft.com/library/mt779156.aspx) cmdlet에 대한 자세한 내용은 다음을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="0e6c5-136">See more on the [Grant-CsConferencingPolicy](https://technet.microsoft.com/library/mt779156.aspx) cmdlet.</span></span>
    
  <span data-ttu-id="0e6c5-137">이미 정책을 만든 경우 [Set-CsConferencingPolicy](https://technet.microsoft.com/library/mt779157.aspx) cmdlet을 사용하여 기존 정책을 변경한 다음[Grant-CsConferencingPolicy](https://technet.microsoft.com/library/mt779156.aspx) cmdlet을 사용하여 사용자에게 설정을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e6c5-137">If you have already created a policy, you can use the [Set-CsConferencingPolicy](https://technet.microsoft.com/library/mt779157.aspx) cmdlet to make changes to the existing policy, and then use the[Grant-CsConferencingPolicy](https://technet.microsoft.com/library/mt779156.aspx) cmdlet to apply the settings to your users.</span></span>
  
### <a name="block-recording-of-conferences-and-prevent-anonymous-meeting-participants"></a><span data-ttu-id="0e6c5-138">회의 기록 차단 및 익명 모임 참가자 방지</span><span class="sxs-lookup"><span data-stu-id="0e6c5-138">Block recording of conferences and prevent anonymous meeting participants</span></span>

- <span data-ttu-id="0e6c5-139">이러한 설정에 대한 새 정책을 만들하려면 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="0e6c5-139">To create a new policy for these settings, run:</span></span> 
   
   ```powershell
   New-CsConferencingPolicy -Identity ConferencingPolicy -AllowAnonymousParticipantsInMeetings  $false -AllowConferenceRecording $false
   ```
   <span data-ttu-id="0e6c5-140">[New-CsConferencingPolicy](https://technet.microsoft.com/library/mt779148.aspx) cmdlet에 대한 자세한 내용은 다음을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="0e6c5-140">See more on the [New-CsConferencingPolicy](https://technet.microsoft.com/library/mt779148.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="0e6c5-141">Amos Marble에 만든 새 정책을 부여하기 위해 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="0e6c5-141">To grant the new policy you created to Amos Marble, run:</span></span>
   
   ```powershell
    Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName ConferencingPolicy
   ```
   <span data-ttu-id="0e6c5-142">[Grant-CsConferencingPolicy](https://technet.microsoft.com/library/mt779156.aspx) cmdlet에 대한 자세한 내용은 다음을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="0e6c5-142">See more on the [Grant-CsConferencingPolicy](https://technet.microsoft.com/library/mt779156.aspx) cmdlet.</span></span>
    
<span data-ttu-id="0e6c5-143">이미 정책을 만든 경우 [Set-CsConferencingPolicy](https://technet.microsoft.com/library/mt779157.aspx) cmdlet을 사용하여 기존 정책을 변경한 다음 [Grant-CsConferencingPolicy](https://technet.microsoft.com/library/mt779156.aspx) cmdlet을 사용하여 사용자에게 설정을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e6c5-143">If you have already created a policy, you can use the [Set-CsConferencingPolicy](https://technet.microsoft.com/library/mt779157.aspx) cmdlet to make changes to the existing policy, and then use the [Grant-CsConferencingPolicy](https://technet.microsoft.com/library/mt779156.aspx) cmdlet to apply the settings to your users.</span></span>
  
### <a name="block-anonymous-participants-from-recording-meetings-and-external-users-from-saving-meeting-content"></a><span data-ttu-id="0e6c5-144">익명 참가자가 모임을 녹음/녹화하지 않습니다. 외부 사용자가 모임 콘텐츠를 저장하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0e6c5-144">Block anonymous participants from recording meetings and external users from saving meeting content</span></span>

- <span data-ttu-id="0e6c5-145">이러한 설정에 대한 새 정책을 만들하려면 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="0e6c5-145">To create a new policy for these settings, run:</span></span>  
   
   ```powershell
   New-CsConferencingPolicy -Identity BlockedConferencingPolicy  -AllowExternalUsersToRecordMeeting  $false -AllowExternalUsersToSaveContent $false 
   ```
   <span data-ttu-id="0e6c5-146">[New-CsConferencingPolicy](https://technet.microsoft.com/library/mt779148.aspx) cmdlet에 대한 자세한 내용은 다음을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="0e6c5-146">See more on the [New-CsConferencingPolicy](https://technet.microsoft.com/library/mt779148.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="0e6c5-147">만든 새 정책을 조직의 모든 사용자에게 부여하기 위해 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="0e6c5-147">To grant the new policy you created to all of the users in your organization, run:</span></span>
    
 
   ```powershell
   Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName BlockedConferencingPolicy
   ```

<span data-ttu-id="0e6c5-148">[Grant-CsConferencingPolicy](https://technet.microsoft.com/library/mt779156.aspx) cmdlet에 대한 자세한 내용은 다음을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="0e6c5-148">See more on the [Grant-CsConferencingPolicy](https://technet.microsoft.com/library/mt779156.aspx) cmdlet.</span></span>
    
<span data-ttu-id="0e6c5-149">이미 정책을 만든 경우 [Set-CsConferencingPolicy](https://technet.microsoft.com/library/mt779157.aspx) cmdlet을 사용하여 기존 정책을 변경한 다음[Grant-CsConferencingPolicy](https://technet.microsoft.com/library/mt779156.aspx) cmdlet을 사용하여 사용자에게 설정을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e6c5-149">If you have already created a policy, you can use the [Set-CsConferencingPolicy](https://technet.microsoft.com/library/mt779157.aspx) cmdlet to make changes to the existing policy, and then use the[Grant-CsConferencingPolicy](https://technet.microsoft.com/library/mt779156.aspx) cmdlet to apply the settings to your users.</span></span>
  
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="0e6c5-150">자세한 내용은 Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="0e6c5-150">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="0e6c5-151">Windows PowerShell 관리는 사용자 및 사용자가 허용되거나 허용되지 않는 작업을 관리하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="0e6c5-151">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="0e6c5-152">이 Windows PowerShell 여러 작업을 수행할 때 일상적인 작업을 간소화할 수 있는 단일 관리 지점을 사용하여 Microsoft 365 또는 Office 365 및 비즈니스용 Skype Online을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e6c5-152">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="0e6c5-153">다음 항목을 Windows PowerShell 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0e6c5-153">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="0e6c5-154">Windows PowerShell 및 Lync Online 소개</span><span class="sxs-lookup"><span data-stu-id="0e6c5-154">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="0e6c5-155">Microsoft 365 또는 Office 365를 관리하기 위해 Windows PowerShell 사용할 수 있는 6 가지 이유</span><span class="sxs-lookup"><span data-stu-id="0e6c5-155">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Microsoft 365 or Office 365</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="0e6c5-156">Windows PowerShell Microsoft 365 관리 센터를 사용하는 경우와 같이 여러 사용자에 대해 한 번씩 설정을 변경하는 경우와 같이 속도, 단순성 및 생산성에 많은 이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e6c5-156">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="0e6c5-157">다음 항목에서 이러한 이점에 대해 자세히 배워야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0e6c5-157">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="0e6c5-158">Microsoft 365 또는 Office 365를 관리하는 가장 좋은 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="0e6c5-158">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="0e6c5-159">비즈니스 Windows PowerShell 사용하여 비즈니스용 Skype Online 관리</span><span class="sxs-lookup"><span data-stu-id="0e6c5-159">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="0e6c5-160">비즈니스용 Windows PowerShell Skype Online 관리 작업을 수행하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e6c5-160">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a><span data-ttu-id="0e6c5-161">관련 항목</span><span class="sxs-lookup"><span data-stu-id="0e6c5-161">Related topics</span></span>
[<span data-ttu-id="0e6c5-162">사용자 지정 외부 액세스 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="0e6c5-162">Create custom external access policies</span></span>](create-custom-external-access-policies.md)

[<span data-ttu-id="0e6c5-163">지점 및 지점 및 지점 파일 전송 차단</span><span class="sxs-lookup"><span data-stu-id="0e6c5-163">Block point-to-point file transfers</span></span>](block-point-to-point-file-transfers.md)

[<span data-ttu-id="0e6c5-164">조직의 클라이언트 정책 설정</span><span class="sxs-lookup"><span data-stu-id="0e6c5-164">Set up client policies for your organization</span></span>](set-up-client-policies-for-your-organization.md)

  
 
