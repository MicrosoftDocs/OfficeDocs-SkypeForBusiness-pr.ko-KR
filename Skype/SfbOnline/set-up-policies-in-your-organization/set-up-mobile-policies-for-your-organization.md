---
title: 조직의 모바일 정책 설정
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: beea47b2-7b9a-4b28-92d0-af65d80cd00f
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
description: 사용자가 휴대폰 번호 대신 직장 전화 번호를 사용하여 휴대폰으로 전화를 걸고 받을 수 있는 기능 등 모바일 장치에서 비즈니스용 Skype 앱을 사용하여 비즈니스용 Skype Online에 연결하는 방법을 설정할 수 있습니다. 모바일 정책을 사용하여 호출을 걸거나 받을 Wi-Fi 연결을 요구할 수도 있습니다.
ms.openlocfilehash: 5094a536a636300ea70a7d358e24ee5c0f511379
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814747"
---
# <a name="set-up-mobile-policies-for-your-organization"></a><span data-ttu-id="7a23a-104">조직의 모바일 정책 설정</span><span class="sxs-lookup"><span data-stu-id="7a23a-104">Set up mobile policies for your organization</span></span>

<span data-ttu-id="7a23a-105">사용자가 휴대폰 번호 대신 직장 전화 번호를 사용하여 휴대폰으로 전화를 걸고 받을 수 있는 기능 등 모바일 장치에서 비즈니스용 Skype 앱을 사용하여 비즈니스용 Skype Online에 연결하는 방법을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a23a-105">You can set up how your users connect to Skype for Business Online using the Skype for Business app on mobile devices, such as a feature that enables users to make and receive phone calls on their mobile phone by using their work phone number instead of their mobile phone number.</span></span> <span data-ttu-id="7a23a-106">모바일 정책을 사용하여 호출을 걸거나 받을 Wi-Fi 연결을 요구할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a23a-106">Mobility policies can also be used to require Wi-Fi connections when making or receiving calls.</span></span>
  
<span data-ttu-id="7a23a-107">정책을 만들 때 모바일 정책 설정을 구성하거나 **Set-CsMobilityPolicy** cmdlet을 사용하여 기존 정책의 설정을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a23a-107">Mobile policy settings can be configured at the time a policy is created, or you can use the **Set-CsMobilityPolicy** cmdlet to modify the settings of an existing policy.</span></span>
  
## <a name="set-your-mobile-policies"></a><span data-ttu-id="7a23a-108">모바일 정책 설정</span><span class="sxs-lookup"><span data-stu-id="7a23a-108">Set your mobile policies</span></span>

> [!NOTE]
> <span data-ttu-id="7a23a-109">비즈니스용 Skype Online의 모든 모바일 정책 설정에 대해 Windows PowerShell 비즈니스용 Skype 관리 **센터를** 사용할 **수 없습니다.**</span><span class="sxs-lookup"><span data-stu-id="7a23a-109">For all of the mobile policy settings in Skype for Business Online, you must use Windows PowerShell and you **can't use** the **Skype for Business admin center**.</span></span> 
  
### <a name="verify-and-start-windows-powershell"></a><span data-ttu-id="7a23a-110">확인 및 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="7a23a-110">Verify and start Windows PowerShell</span></span>

- <span data-ttu-id="7a23a-111">**버전 3.0 Windows PowerShell 실행 중인지 확인**</span><span class="sxs-lookup"><span data-stu-id="7a23a-111">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
    
    1. <span data-ttu-id="7a23a-112">버전 3.0 이상을 실행하고 있는지 확인: 시작 메뉴를  >  Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7a23a-112">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
        
    2. <span data-ttu-id="7a23a-113">웹 창에  _Get-Host를_ 입력하여 **Windows PowerShell** 확인</span><span class="sxs-lookup"><span data-stu-id="7a23a-113">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
        
    3. <span data-ttu-id="7a23a-114">버전 3.0 이상이 없는 경우 업데이트를 다운로드하여 설치해야 Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7a23a-114">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell.</span></span> <span data-ttu-id="7a23a-115">버전 [Windows Management Framework 4.0으로](https://go.microsoft.com/fwlink/?LinkId=716845) Windows PowerShell 다운로드하고 업데이트하려면 4.0을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="7a23a-115">See [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0.</span></span> <span data-ttu-id="7a23a-116">메시지가 표시될 때 컴퓨터를 다시 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="7a23a-116">Restart your computer when you are prompted.</span></span>
        
    4. <span data-ttu-id="7a23a-117">또한 비즈니스용 Skype Online에 연결하는 원격 Windows PowerShell 세션을 만들 수 있는 Teams용 Windows PowerShell 모듈을 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a23a-117">You will also need to install the Windows PowerShell module for Teams that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span>
    
    <span data-ttu-id="7a23a-118">자세한 내용은 단일 창에서 모든 [Microsoft 365 또는 Office 365 서비스에 Windows PowerShell 참조합니다.](https://technet.microsoft.com/library/dn568015.aspx)</span><span class="sxs-lookup"><span data-stu-id="7a23a-118">If you need to know more, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx).</span></span>
    
- <span data-ttu-id="7a23a-119">**세션 Windows PowerShell 시작**</span><span class="sxs-lookup"><span data-stu-id="7a23a-119">**Start a Windows PowerShell session**</span></span>
    
    1. <span data-ttu-id="7a23a-120">시작 **메뉴에서**  >  **Windows PowerShell.**</span><span class="sxs-lookup"><span data-stu-id="7a23a-120">From the **Start Menu** > **Windows PowerShell**.</span></span>
        
    2. <span data-ttu-id="7a23a-121">다음 **Windows PowerShell** 실행하여 Microsoft 365 또는 Office 365에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="7a23a-121">In the **Windows PowerShell** window, connect to your Microsoft 365 or Office 365 by running:</span></span>
        
       > [!NOTE]
       > <span data-ttu-id="7a23a-122">비즈니스용 Skype Online Connector는 현재 최신 Teams PowerShell 모듈의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="7a23a-122">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span>
       >
       > <span data-ttu-id="7a23a-123">최신 [Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/)공개 릴리스를 사용하는 경우 비즈니스용 Skype Online Connector를 설치할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7a23a-123">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

       ```PowerShell      
        Import-Module -Name MicrosoftTeams
        $credential = Get-Credential
        $session = New-CsOnlineSession -Credential $credential
        Import-PSSession $session
       ```

   <span data-ttu-id="7a23a-124">Windows PowerShell 시작에 대한 자세한 내용은 단일 Windows PowerShell 창에서 모든 [Microsoft 365 또는 Office 365](https://technet.microsoft.com/library/dn568015.aspx) 서비스에 연결 또는 [Windows PowerShell.](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="7a23a-124">If you want more information about starting Windows PowerShell, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>

### <a name="require-a-wifi-connection-for-video-for-a-user"></a><span data-ttu-id="7a23a-125">사용자의 비디오에 WiFi 연결 필요</span><span class="sxs-lookup"><span data-stu-id="7a23a-125">Require a WiFi connection for video for a user</span></span>

- <span data-ttu-id="7a23a-126">이러한 설정에 대한 새 정책을 만들하려면 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="7a23a-126">To create a new policy for these settings, run:</span></span>
   
   ```powershell
   New-CsMobilityPolicy -Identity MobilityPolicy -RequireWIFIForIPVideo $true
   ```
   <span data-ttu-id="7a23a-127">[New-CsMobilityPolicy](https://technet.microsoft.com/library/mt779150.aspx) cmdlet에 대한 자세한 내용은 다음을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="7a23a-127">See more on the [New-CsMobilityPolicy](https://technet.microsoft.com/library/mt779150.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="7a23a-128">만든 새 정책을 조직의 모든 사용자에게 부여하기 위해 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="7a23a-128">To grant the new policy you created to all of the users in your organization, run:</span></span>
   
   ```powershell
   Grant-CsMobilityPolicy -Identity"amos.marble@contoso.com" -PolicyName MobilityPolicy
   ```
   <span data-ttu-id="7a23a-129">[Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) cmdlet에 대한 자세한 내용은 다음을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="7a23a-129">See more on the [Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) cmdlet.</span></span>
    
  <span data-ttu-id="7a23a-130">이미 정책을 만든 경우 [Set-CsMobilityPolicy](https://technet.microsoft.com/library/mt779147.aspx) cmdlet을 사용하여 기존 정책을 변경한 다음[Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) cmdlet을 사용하여 사용자에게 설정을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a23a-130">If you have already created a policy, you can use the [Set-CsMobilityPolicy](https://technet.microsoft.com/library/mt779147.aspx) cmdlet to make changes to the existing policy, and then use the[Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) cmdlet to apply the setting to your users.</span></span>
  
### <a name="prevent-a-user-from-using-the-skype-for-business-app"></a><span data-ttu-id="7a23a-131">사용자가 비즈니스용 Skype 앱을 사용하지 못하도록 방지</span><span class="sxs-lookup"><span data-stu-id="7a23a-131">Prevent a user from using the Skype for Business app</span></span>

- <span data-ttu-id="7a23a-132">이러한 설정에 대한 새 정책을 만들하려면 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="7a23a-132">To create a new policy for these settings, run:</span></span>
  ```PowerShell
  New-CsMobilityPolicy -Identity NoAppClientPolicy -EnableMobility $false 
  ```
  <span data-ttu-id="7a23a-133">[New-CsMobilityPolicy](https://technet.microsoft.com/library/mt779150.aspx) cmdlet에 대한 자세한 내용은 다음을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="7a23a-133">See more on the [New-CsMobilityPolicy](https://technet.microsoft.com/library/mt779150.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="7a23a-134">Amos Marble에 만든 새 정책을 부여하기 위해 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="7a23a-134">To grant the new policy you created to Amos Marble, run:</span></span>  
   
   ```powershell
   Grant-CsMobilityPolicy -Identity "amos.marble@contoso.com"-PolicyName NoAppClientPolicy
   ```
   <span data-ttu-id="7a23a-135">[Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) cmdlet에 대한 자세한 내용은 다음을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="7a23a-135">See more on the [Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) cmdlet.</span></span>
    
  <span data-ttu-id="7a23a-136">이미 정책을 만든 경우 [Set-CsMobilityPolicy](https://technet.microsoft.com/library/mt779147.aspx) cmdlet을 사용하여 기존 정책을 변경한 다음 [Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) cmdlet을 사용하여 사용자에게 설정을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a23a-136">If you have already created a policy, you can use the [Set-CsMobilityPolicy](https://technet.microsoft.com/library/mt779147.aspx) cmdlet to make changes to the existing policy, and then use the [Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) cmdlet to apply the setting to your users.</span></span>
  
### <a name="prevent-a-user-from-making-voice-over-ip-calls-using-a-mobile-device"></a><span data-ttu-id="7a23a-137">사용자가 모바일 장치를 사용하여 IP 통화를 통해 음성을 걸지 못하도록 방지</span><span class="sxs-lookup"><span data-stu-id="7a23a-137">Prevent a user from making voice over IP calls using a mobile device</span></span>

- <span data-ttu-id="7a23a-138">이러한 설정에 대한 새 정책을 만들하려면 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="7a23a-138">To create a new policy for these settings, run:</span></span>
   
   ```powershell
   New-CsMobilityPolicy -Identity VoIPClientPolicy -EnableIPAudioVideo  $false
   ```
   <span data-ttu-id="7a23a-139">[New-CsMobilityPolicy](https://technet.microsoft.com/library/mt779150.aspx) cmdlet에 대한 자세한 내용은 다음을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="7a23a-139">See more on the [New-CsMobilityPolicy](https://technet.microsoft.com/library/mt779150.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="7a23a-140">만든 새 정책을 조직의 모든 사용자에게 부여하기 위해 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="7a23a-140">To grant the new policy you created to all of the users in your organization, run:</span></span>
   
   ```powershell
   Grant-CsMobilityPolicy -Identity "amos.marble@contoso.com" -PolicyName VoIPClientPolicy
   ```

  <span data-ttu-id="7a23a-141">[Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) cmdlet에 대한 자세한 내용은 다음을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="7a23a-141">See more on the [Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) cmdlet.</span></span>
    
<span data-ttu-id="7a23a-142">이미 정책을 만든 경우 [Set-CsMobilityPolicy](https://technet.microsoft.com/library/mt779147.aspx) cmdlet을 사용하여 기존 정책을 변경한 다음[Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) cmdlet을 사용하여 사용자에게 설정을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a23a-142">If you have already created a policy, you can use the [Set-CsMobilityPolicy](https://technet.microsoft.com/library/mt779147.aspx) cmdlet to make changes to the existing policy, and then use the[Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) cmdlet to apply the setting to your users.</span></span>
  
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="7a23a-143">자세한 내용은 Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="7a23a-143">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="7a23a-144">Windows PowerShell 관리는 사용자 및 사용자가 허용되거나 허용되지 않는 작업을 관리하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="7a23a-144">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="7a23a-145">이 Windows PowerShell 여러 작업을 수행할 때 일상적인 작업을 간소화할 수 있는 단일 관리 지점을 사용하여 Microsoft 365 또는 Office 365 및 비즈니스용 Skype Online을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a23a-145">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="7a23a-146">다음 항목을 Windows PowerShell 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7a23a-146">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="7a23a-147">Windows PowerShell 및 Lync Online 소개</span><span class="sxs-lookup"><span data-stu-id="7a23a-147">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="7a23a-148">Microsoft 365 또는 Office 365를 관리하기 위해 Windows PowerShell 사용할 수 있는 6 가지 이유</span><span class="sxs-lookup"><span data-stu-id="7a23a-148">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Microsoft 365 or Office 365</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="7a23a-149">Windows PowerShell Microsoft 365 관리 센터를 사용하는 경우와 같이 여러 사용자에 대해 한 번씩 설정을 변경하는 경우와 같이 속도, 단순성 및 생산성에 많은 이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a23a-149">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="7a23a-150">다음 항목에서 이러한 이점에 대해 자세히 배워야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a23a-150">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="7a23a-151">Microsoft 365 또는 Office 365를 관리하는 가장 좋은 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="7a23a-151">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="7a23a-152">비즈니스 Windows PowerShell 사용하여 비즈니스용 Skype Online 관리</span><span class="sxs-lookup"><span data-stu-id="7a23a-152">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="7a23a-153">비즈니스용 Windows PowerShell Skype Online 관리 작업을 수행하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a23a-153">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="7a23a-154">관련 항목</span><span class="sxs-lookup"><span data-stu-id="7a23a-154">Related topics</span></span>
[<span data-ttu-id="7a23a-155">사용자 지정 외부 액세스 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="7a23a-155">Create custom external access policies</span></span>](create-custom-external-access-policies.md)

[<span data-ttu-id="7a23a-156">지점 및 지점 및 지점 파일 전송 차단</span><span class="sxs-lookup"><span data-stu-id="7a23a-156">Block point-to-point file transfers</span></span>](block-point-to-point-file-transfers.md)

[<span data-ttu-id="7a23a-157">조직의 클라이언트 정책 설정</span><span class="sxs-lookup"><span data-stu-id="7a23a-157">Set up client policies for your organization</span></span>](set-up-client-policies-for-your-organization.md)

[<span data-ttu-id="7a23a-158">조직에서 회의 정책 설정</span><span class="sxs-lookup"><span data-stu-id="7a23a-158">Set up conferencing policies in your organization</span></span>](set-up-conferencing-policies-for-your-organization.md)

  
 
