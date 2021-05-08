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
description: 회의는 온라인에서 비즈니스용 Skype 중요한 부분입니다. 회의를 사용하면 사용자 그룹이 온라인으로 모여 슬라이드와 비디오를 보고, 애플리케이션을 공유하고, 파일을 교환하고, 그렇지 않으면 통신 및 공동 작업을 할 수 있습니다.
ms.openlocfilehash: 84037d571bf6f9dc3451793678a6d1b650492bd9
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52240080"
---
# <a name="set-up-conferencing-policies-for-your-organization"></a><span data-ttu-id="3f99d-103">조직의 회의 정책 설정</span><span class="sxs-lookup"><span data-stu-id="3f99d-103">Set up conferencing policies for your organization</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

<span data-ttu-id="3f99d-104">회의는 온라인에서 비즈니스용 Skype 중요한 부분입니다. 회의를 사용하면 사용자 그룹이 온라인으로 모여 슬라이드와 비디오를 보고, 애플리케이션을 공유하고, 파일을 교환하고, 그렇지 않으면 통신 및 공동 작업을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f99d-104">Conferencing is an important part of Skype for Business Online: conferencing enables groups of users to come together online to view slides and video, share applications, exchange files, and otherwise communicate and collaborate.</span></span>
  
<span data-ttu-id="3f99d-105">회의 및 회의 설정을 제어하는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="3f99d-105">It's important for you to maintain control over conferences and conference settings.</span></span> <span data-ttu-id="3f99d-106">경우에 따라 보안 문제가 있을 수 있습니다. 기본적으로 비인가 사용자를 포함하여 모든 사용자가 모임에 참가하고 해당 모임 중에 배포된 슬라이드 또는 유인물 중 일부를 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f99d-106">In some cases, there might be security concerns: by default, anyone, including unauthenticated users, can participate in meetings and save any of the slides or handouts distributed during those meetings.</span></span> <span data-ttu-id="3f99d-107">또한 법적 문제가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f99d-107">In addition, there might be occasional legal concerns.</span></span> <span data-ttu-id="3f99d-108">예를 들어 기본적으로 모임 참가자는 공유 콘텐츠에 대한 주석을 만들 수 있습니다. 그러나 이러한 주석은 모임이 보관될 때 저장되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3f99d-108">For example, by default ,meeting participants are allowed to make annotations on shared content; however, these annotations are not saved when the meeting is archived.</span></span> <span data-ttu-id="3f99d-109">조직에서 모든 전자 통신의 레코드를 유지해야 하는 경우 주석을 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f99d-109">If your organization is required to keep a record of all electronic communication, you might want to disable annotations.</span></span> 
  
<span data-ttu-id="3f99d-110">온라인 비즈니스용 Skype 회의 정책을 사용하여 회의를 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="3f99d-110">In Skype for Business Online, conferences are managed by using conferencing policies.</span></span> <span data-ttu-id="3f99d-111">회의 정책은 회의에 IP 오디오 및 비디오를 포함할 수 있는지 여부부터 모임에 참석할 수 있는 최대 사용자 수에 대한 모든 것을 포함하여 회의에서 사용할 수 있는 기능 및 기능을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="3f99d-111">Conferencing policies determine the features and capabilities that can be used in a conference, including everything from whether or not the conference can include IP audio and video to the maximum number of people who can attend a meeting.</span></span> <span data-ttu-id="3f99d-112">회의 정책은 전역 범위 또는 사용자당 범위에서 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f99d-112">Conferencing policies can be configured at the global scope or at the per-user scope.</span></span> <span data-ttu-id="3f99d-113">이렇게 하면 관리자가 어떤 사용자가 사용할 수 있게 될 기능을 결정해야 하는지 결정하기 위해 많은 유연성을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="3f99d-113">This provides administrators with enormous flexibility when it comes to deciding which capabilities will be made available to which users.</span></span>
  
<span data-ttu-id="3f99d-114">정책을 만들 때 정책 설정을 구성하거나 **Set-CsConferencingPolicy** cmdlet을 사용하여 기존 정책의 설정을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f99d-114">Policy settings can be configured at the time a policy is created, or you can use the **Set-CsConferencingPolicy** cmdlet to modify the settings of an existing policy.</span></span>
  
## <a name="set-your-conferencing-policies"></a><span data-ttu-id="3f99d-115">회의 정책 설정</span><span class="sxs-lookup"><span data-stu-id="3f99d-115">Set your conferencing policies</span></span>

> [!NOTE]
> <span data-ttu-id="3f99d-116">온라인에서 모든 회의 정책 비즈니스용 Skype 경우 Windows PowerShell 관리 센터를 사용할 수 **비즈니스용 Skype 없습니다.** </span><span class="sxs-lookup"><span data-stu-id="3f99d-116">For all of the conferencing policy settings in Skype for Business Online, you must use Windows PowerShell and you **can't use** the **Skype for Business admin center**.</span></span> 

### <a name="start-windows-powershell"></a><span data-ttu-id="3f99d-117">시작 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="3f99d-117">Start Windows PowerShell</span></span>

 > [!Note]
> <span data-ttu-id="3f99d-118">비즈니스용 Skype 온라인 커넥터는 현재 최신 PowerShell Teams 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="3f99d-118">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span> <span data-ttu-id="3f99d-119">최신 PowerShell 공개 Teams 사용하는 경우 온라인 커넥터를 비즈니스용 Skype 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3f99d-119">If you're using the latest Teams PowerShell public release, you don't need to install the Skype for Business Online Connector.</span></span>
1. <span data-ttu-id="3f99d-120">[PowerShell Teams 설치합니다.](/microsoftteams/teams-powershell-install)</span><span class="sxs-lookup"><span data-stu-id="3f99d-120">Install the [Teams PowerShell module](/microsoftteams/teams-powershell-install).</span></span>
    
2. <span data-ttu-id="3f99d-121">명령 Windows PowerShell 프롬프트를 열고 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="3f99d-121">Open a Windows PowerShell command prompt and run the following commands:</span></span> 

   ```powershell
   # When using Teams PowerShell Module 
   
   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```
   <span data-ttu-id="3f99d-122">시작에 대한 자세한 Windows PowerShell 을 참조하세요커넥트 Microsoft 365 Office 365 단일 창에서 모든 Windows PowerShell 또는 [Windows PowerShell.](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md) [](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window)</span><span class="sxs-lookup"><span data-stu-id="3f99d-122">If you want more information about starting Windows PowerShell, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
      
### <a name="block-file-transfers-and-desktop-sharing-during-meetings"></a><span data-ttu-id="3f99d-123">모임 중에 파일 전송 및 데스크톱 공유 차단</span><span class="sxs-lookup"><span data-stu-id="3f99d-123">Block file transfers and desktop sharing during meetings</span></span>

- <span data-ttu-id="3f99d-124">이러한 설정에 대한 새 정책을 만들하려면 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="3f99d-124">To create a new policy for these settings, run:</span></span>
   
   ```powershell
   New-CsConferencingPolicy -Identity DesktopConferencingPolicy -EnableAppDesktopSharing None  $true -EnableFileTransfer $false
   ```
   <span data-ttu-id="3f99d-125">[New-CsConferencingPolicy](/powershell/module/skype/New-CsConferencingPolicy) cmdlet을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="3f99d-125">See more on the [New-CsConferencingPolicy](/powershell/module/skype/New-CsConferencingPolicy) cmdlet.</span></span>
    
- <span data-ttu-id="3f99d-126">조직의 모든 사용자에게 만든 새 정책을 부여하기 위해 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="3f99d-126">To grant the new policy you created to all users in your organization, run:</span></span>
   
   ```powershell
   Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName DesktopConferencingPolicy
   ```
   <span data-ttu-id="3f99d-127">[Grant-CsConferencingPolicy](/powershell/module/skype/Grant-CsConferencingPolicy) cmdlet을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="3f99d-127">See more on the [Grant-CsConferencingPolicy](/powershell/module/skype/Grant-CsConferencingPolicy) cmdlet.</span></span>
    
  <span data-ttu-id="3f99d-128">정책을 이미 만든 경우 [Set-CsConferencingPolicy](/powershell/module/skype/Set-CsConferencingPolicy) cmdlet을 사용하여 기존 정책을 변경한 다음[Grant-CsConferencingPolicy](/powershell/module/skype/Grant-CsConferencingPolicy) cmdlet을 사용하여 사용자에게 설정을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f99d-128">If you have already created a policy, you can use the [Set-CsConferencingPolicy](/powershell/module/skype/Set-CsConferencingPolicy) cmdlet to make changes to the existing policy, and then use the[Grant-CsConferencingPolicy](/powershell/module/skype/Grant-CsConferencingPolicy) cmdlet to apply the settings to your users.</span></span>
  
### <a name="block-recording-of-conferences-and-prevent-anonymous-meeting-participants"></a><span data-ttu-id="3f99d-129">회의 기록 차단 및 익명 모임 참가자 방지</span><span class="sxs-lookup"><span data-stu-id="3f99d-129">Block recording of conferences and prevent anonymous meeting participants</span></span>

- <span data-ttu-id="3f99d-130">이러한 설정에 대한 새 정책을 만들하려면 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="3f99d-130">To create a new policy for these settings, run:</span></span> 
   
   ```powershell
   New-CsConferencingPolicy -Identity ConferencingPolicy -AllowAnonymousParticipantsInMeetings  $false -AllowConferenceRecording $false
   ```
   <span data-ttu-id="3f99d-131">[New-CsConferencingPolicy](/powershell/module/skype/New-CsConferencingPolicy) cmdlet을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="3f99d-131">See more on the [New-CsConferencingPolicy](/powershell/module/skype/New-CsConferencingPolicy) cmdlet.</span></span>
    
- <span data-ttu-id="3f99d-132">Amos Marble에 만든 새 정책을 부여하기 위해 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="3f99d-132">To grant the new policy you created to Amos Marble, run:</span></span>
   
   ```powershell
    Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName ConferencingPolicy
   ```
   <span data-ttu-id="3f99d-133">[Grant-CsConferencingPolicy](/powershell/module/skype/Grant-CsConferencingPolicy) cmdlet을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="3f99d-133">See more on the [Grant-CsConferencingPolicy](/powershell/module/skype/Grant-CsConferencingPolicy) cmdlet.</span></span>
    
<span data-ttu-id="3f99d-134">정책을 이미 만든 경우 [Set-CsConferencingPolicy](/powershell/module/skype/Set-CsConferencingPolicy) cmdlet을 사용하여 기존 정책을 변경한 다음 [Grant-CsConferencingPolicy](/powershell/module/skype/Grant-CsConferencingPolicy) cmdlet을 사용하여 사용자에게 설정을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f99d-134">If you have already created a policy, you can use the [Set-CsConferencingPolicy](/powershell/module/skype/Set-CsConferencingPolicy) cmdlet to make changes to the existing policy, and then use the [Grant-CsConferencingPolicy](/powershell/module/skype/Grant-CsConferencingPolicy) cmdlet to apply the settings to your users.</span></span>
  
### <a name="block-anonymous-participants-from-recording-meetings-and-external-users-from-saving-meeting-content"></a><span data-ttu-id="3f99d-135">익명 참가자가 모임을 기록하지 않습니다. 외부 사용자가 모임 콘텐츠를 저장하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3f99d-135">Block anonymous participants from recording meetings and external users from saving meeting content</span></span>

- <span data-ttu-id="3f99d-136">이러한 설정에 대한 새 정책을 만들하려면 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="3f99d-136">To create a new policy for these settings, run:</span></span>  
   
   ```powershell
   New-CsConferencingPolicy -Identity BlockedConferencingPolicy  -AllowExternalUsersToRecordMeeting  $false -AllowExternalUsersToSaveContent $false 
   ```
   <span data-ttu-id="3f99d-137">[New-CsConferencingPolicy](/powershell/module/skype/New-CsConferencingPolicy) cmdlet을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="3f99d-137">See more on the [New-CsConferencingPolicy](/powershell/module/skype/New-CsConferencingPolicy) cmdlet.</span></span>
    
- <span data-ttu-id="3f99d-138">조직의 모든 사용자에게 만든 새 정책을 부여하기 위해 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="3f99d-138">To grant the new policy you created to all of the users in your organization, run:</span></span>
    
 
   ```powershell
   Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName BlockedConferencingPolicy
   ```

<span data-ttu-id="3f99d-139">[Grant-CsConferencingPolicy](/powershell/module/skype/Grant-CsConferencingPolicy) cmdlet을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="3f99d-139">See more on the [Grant-CsConferencingPolicy](/powershell/module/skype/Grant-CsConferencingPolicy) cmdlet.</span></span>
    
<span data-ttu-id="3f99d-140">정책을 이미 만든 경우 [Set-CsConferencingPolicy](/powershell/module/skype/Set-CsConferencingPolicy) cmdlet을 사용하여 기존 정책을 변경한 다음[Grant-CsConferencingPolicy](/powershell/module/skype/Grant-CsConferencingPolicy) cmdlet을 사용하여 사용자에게 설정을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f99d-140">If you have already created a policy, you can use the [Set-CsConferencingPolicy](/powershell/module/skype/Set-CsConferencingPolicy) cmdlet to make changes to the existing policy, and then use the[Grant-CsConferencingPolicy](/powershell/module/skype/Grant-CsConferencingPolicy) cmdlet to apply the settings to your users.</span></span>
  
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="3f99d-141">자세한 정보를 Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="3f99d-141">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="3f99d-142">Windows PowerShell 모든 것은 사용자 관리와 사용자가 허용되거나 허용되지 않는 작업을 관리하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="3f99d-142">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="3f99d-143">이 Windows PowerShell 여러 작업을 수행할 때 일상적인 작업을 단순화할 수 있는 단일 관리 Microsoft 365 Office 365 비즈니스용 Skype 온라인에서 관리하거나 온라인을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f99d-143">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="3f99d-144">다음 항목을 Windows PowerShell 다음 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3f99d-144">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="3f99d-145">Windows PowerShell 및 비즈니스용 Skype Online 소개</span><span class="sxs-lookup"><span data-stu-id="3f99d-145">An introduction to Windows PowerShell and Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="3f99d-146">Windows PowerShell 관리하기 위해 Windows PowerShell 이유 Microsoft 365 Office 365</span><span class="sxs-lookup"><span data-stu-id="3f99d-146">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Microsoft 365 or Office 365</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
- <span data-ttu-id="3f99d-147">Windows PowerShell 많은 사용자에 대해 한 Microsoft 365 설정하는 경우와 같이 관리 센터를 사용하는 것만 사용하여 속도, 단순성 및 생산성에 많은 이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f99d-147">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="3f99d-148">다음 항목에서 이러한 이점에 대해 자세히 알아보습니다.</span><span class="sxs-lookup"><span data-stu-id="3f99d-148">Learn about these advantages in the following topics:</span></span>
    
  - <span data-ttu-id="3f99d-149">[사용자와 함께 Microsoft 365 또는 Office 365 가장 Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="3f99d-149">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
  - [<span data-ttu-id="3f99d-150">온라인 Windows PowerShell 관리하기 위해 비즈니스용 Skype 사용</span><span class="sxs-lookup"><span data-stu-id="3f99d-150">Using Windows PowerShell to manage Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="3f99d-151">일반적인 Windows PowerShell 관리 작업을 수행하는 데 비즈니스용 Skype 사용</span><span class="sxs-lookup"><span data-stu-id="3f99d-151">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

## <a name="related-topics"></a><span data-ttu-id="3f99d-152">관련 주제</span><span class="sxs-lookup"><span data-stu-id="3f99d-152">Related topics</span></span>
[<span data-ttu-id="3f99d-153">사용자 지정 외부 액세스 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="3f99d-153">Create custom external access policies</span></span>](create-custom-external-access-policies.md)

[<span data-ttu-id="3f99d-154">지점 및 지점 파일 전송 차단</span><span class="sxs-lookup"><span data-stu-id="3f99d-154">Block point-to-point file transfers</span></span>](block-point-to-point-file-transfers.md)

[<span data-ttu-id="3f99d-155">조직의 클라이언트 정책 설정</span><span class="sxs-lookup"><span data-stu-id="3f99d-155">Set up client policies for your organization</span></span>](set-up-client-policies-for-your-organization.md)

  
