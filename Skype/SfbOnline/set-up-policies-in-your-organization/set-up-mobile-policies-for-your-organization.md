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
description: 사용자가 휴대 전화 번호 대신 회사 전화 번호를 사용 하 여 휴대폰으로 전화를 걸고 받을 수 있는 기능 등 모바일 장치에서 비즈니스용 skype Online에 연결 하는 방법을 설정할 수 있습니다. 이동성 정책은 전화를 걸거나 받을 때 Wi-fi 연결이 필요한 경우에도 사용할 수 있습니다.
ms.openlocfilehash: ac8f94cb7203b3b0ee4698969db0b76cb1e31a49
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "43776263"
---
# <a name="set-up-mobile-policies-for-your-organization"></a><span data-ttu-id="2b6e5-104">조직의 모바일 정책 설정</span><span class="sxs-lookup"><span data-stu-id="2b6e5-104">Set up mobile policies for your organization</span></span>

<span data-ttu-id="2b6e5-105">사용자가 휴대 전화 번호 대신 회사 전화 번호를 사용 하 여 휴대폰으로 전화를 걸고 받을 수 있는 기능 등 모바일 장치에서 비즈니스용 skype Online에 연결 하는 방법을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b6e5-105">You can set up how your users connect to Skype for Business Online using the Skype for Business app on mobile devices, such as a feature that enables users to make and receive phone calls on their mobile phone by using their work phone number instead of their mobile phone number.</span></span> <span data-ttu-id="2b6e5-106">이동성 정책은 전화를 걸거나 받을 때 Wi-fi 연결이 필요한 경우에도 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b6e5-106">Mobility policies can also be used to require Wi-Fi connections when making or receiving calls.</span></span>
  
<span data-ttu-id="2b6e5-107">정책을 만들 때 모바일 정책 설정을 구성 하거나, **Set-CsMobilityPolicy** cmdlet을 사용 하 여 기존 정책의 설정을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b6e5-107">Mobile policy settings can be configured at the time a policy is created, or you can use the **Set-CsMobilityPolicy** cmdlet to modify the settings of an existing policy.</span></span>
  
## <a name="set-your-mobile-policies"></a><span data-ttu-id="2b6e5-108">모바일 정책 설정</span><span class="sxs-lookup"><span data-stu-id="2b6e5-108">Set your mobile policies</span></span>

> [!NOTE]
> <span data-ttu-id="2b6e5-109">비즈니스용 Skype Online의 모든 모바일 정책 설정에 대해 Windows PowerShell을 사용 해야 하며 **비즈니스용 skype 관리 센터**를 **사용할 수 없습니다** .</span><span class="sxs-lookup"><span data-stu-id="2b6e5-109">For all of the mobile policy settings in Skype for Business Online, you must use Windows PowerShell and you **can't use** the **Skype for Business admin center**.</span></span> 
  
### <a name="verify-and-start-windows-powershell"></a><span data-ttu-id="2b6e5-110">Windows PowerShell 확인 및 시작</span><span class="sxs-lookup"><span data-stu-id="2b6e5-110">Verify and start Windows PowerShell</span></span>

- <span data-ttu-id="2b6e5-111">**Windows PowerShell 버전 3.0 이상을 실행 하 고 있는지 확인**</span><span class="sxs-lookup"><span data-stu-id="2b6e5-111">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
    
    1. <span data-ttu-id="2b6e5-112">버전 3.0 이상을 실행 하 고 있는지 확인 하려면 **시작 메뉴** > 에서**Windows PowerShell**을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b6e5-112">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
        
    2. <span data-ttu-id="2b6e5-113">**Windows PowerShell** 창에서 _Get-Host_ 를 입력 하 여 버전을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b6e5-113">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
        
    3. <span data-ttu-id="2b6e5-114">버전 3.0 이상이 없는 경우 Windows PowerShell 업데이트를 다운로드 하 여 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b6e5-114">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell.</span></span> <span data-ttu-id="2b6e5-115">Windows [Management 프레임 워크 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) 를 참조 하 여 windows PowerShell을 버전 4.0로 다운로드 하 고 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b6e5-115">See [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0.</span></span> <span data-ttu-id="2b6e5-116">메시지가 표시 되 면 컴퓨터를 다시 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b6e5-116">Restart your computer when you are prompted.</span></span>
        
    4. <span data-ttu-id="2b6e5-117">비즈니스용 skype Online에 연결 되는 원격 Windows PowerShell 세션을 만들 수 있는 비즈니스용 Skype Online 용 Windows PowerShell 모듈을 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b6e5-117">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span> <span data-ttu-id="2b6e5-118">이 모듈은 64 비트 컴퓨터 에서만 지원 되며 비즈니스용 [Skype Online 용 Windows PowerShell 모듈](https://go.microsoft.com/fwlink/?LinkId=294688)의 Microsoft 다운로드 센터에서 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b6e5-118">This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688).</span></span> <span data-ttu-id="2b6e5-119">메시지가 표시 되 면 컴퓨터를 다시 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b6e5-119">Restart your computer if you are prompted.</span></span>
    
    <span data-ttu-id="2b6e5-120">자세한 정보를 알고 싶은 경우 [모든 Office 365 서비스에 단일 Windows PowerShell 창으로 연결](https://technet.microsoft.com/library/dn568015.aspx)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2b6e5-120">If you need to know more, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx).</span></span>
    
- <span data-ttu-id="2b6e5-121">**Windows PowerShell 세션 시작**</span><span class="sxs-lookup"><span data-stu-id="2b6e5-121">**Start a Windows PowerShell session**</span></span>
    
    1. <span data-ttu-id="2b6e5-122">**시작 메뉴** > 에서**Windows PowerShell**을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b6e5-122">From the **Start Menu** > **Windows PowerShell**.</span></span>
        
    2. <span data-ttu-id="2b6e5-123">**Windows PowerShell** 창에서 다음을 실행 하 여 Microsoft 365 또는 Office 365에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b6e5-123">In the **Windows PowerShell** window, connect to your Microsoft 365 or Office 365 by running:</span></span>
        
        > [!NOTE]
        > <span data-ttu-id="2b6e5-124">비즈니스용 Skype Online Windows PowerShell 모듈을 처음 사용 하는 경우에만 **Import-Module** 명령을 실행 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b6e5-124">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>

       ```PowerShell      
        Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
        $credential = Get-Credential
        $session = New-CsOnlineSession -Credential $credential
        Import-PSSession $session
       ```

   <span data-ttu-id="2b6e5-125">Windows PowerShell을 시작 하는 방법에 대 한 자세한 내용은 [단일 Windows powershell 창에서 모든 Office 365 서비스에 연결](https://technet.microsoft.com/library/dn568015.aspx) 또는 [Windows Powershell 용 컴퓨터 설정을](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2b6e5-125">If you want more information about starting Windows PowerShell, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>

### <a name="require-a-wifi-connection-for-video-for-a-user"></a><span data-ttu-id="2b6e5-126">사용자의 비디오에 대 한 WiFi 연결 필요</span><span class="sxs-lookup"><span data-stu-id="2b6e5-126">Require a WiFi connection for video for a user</span></span>

- <span data-ttu-id="2b6e5-127">이러한 설정에 대 한 새 정책을 만들려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b6e5-127">To create a new policy for these settings, run:</span></span>
   
   ```powershell
   New-CsMobilityPolicy -Identity MobilityPolicy -RequireWIFIForIPVideo $true
   ```
   <span data-ttu-id="2b6e5-128">[새로운 CsMobilityPolicy](https://technet.microsoft.com/library/mt779150.aspx) cmdlet에 대 한 자세한 내용을 확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="2b6e5-128">See more on the [New-CsMobilityPolicy](https://technet.microsoft.com/library/mt779150.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="2b6e5-129">만든 새 정책을 조직의 모든 사용자에 게 부여 하려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b6e5-129">To grant the new policy you created to all of the users in your organization, run:</span></span>
   
   ```powershell
   Grant-CsMobilityPolicy -Identity"amos.marble@contoso.com" -PolicyName MobilityPolicy
   ```
   <span data-ttu-id="2b6e5-130">[CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) cmdlet에 대 한 자세한 내용을 확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="2b6e5-130">See more on the [Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) cmdlet.</span></span>
    
  <span data-ttu-id="2b6e5-131">이미 정책을 만든 경우 [CsMobilityPolicy](https://technet.microsoft.com/library/mt779147.aspx) cmdlet을 사용 하 여 기존 정책을 변경한 다음[부여-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) cmdlet을 사용 하 여 사용자에 게 해당 설정을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b6e5-131">If you have already created a policy, you can use the [Set-CsMobilityPolicy](https://technet.microsoft.com/library/mt779147.aspx) cmdlet to make changes to the existing policy, and then use the[Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) cmdlet to apply the setting to your users.</span></span>
  
### <a name="prevent-a-user-from-using-the-skype-for-business-app"></a><span data-ttu-id="2b6e5-132">사용자가 비즈니스용 Skype 앱을 사용 하지 못하도록 방지</span><span class="sxs-lookup"><span data-stu-id="2b6e5-132">Prevent a user from using the Skype for Business app</span></span>

- <span data-ttu-id="2b6e5-133">이러한 설정에 대 한 새 정책을 만들려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b6e5-133">To create a new policy for these settings, run:</span></span>
  ```PowerShell
  New-CsMobilityPolicy -Identity NoAppClientPolicy -EnableMobility $false 
  ```
  <span data-ttu-id="2b6e5-134">[새로운 CsMobilityPolicy](https://technet.microsoft.com/library/mt779150.aspx) cmdlet에 대 한 자세한 내용을 확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="2b6e5-134">See more on the [New-CsMobilityPolicy](https://technet.microsoft.com/library/mt779150.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="2b6e5-135">만든 새 정책을 Amos 대리석에 부여 하려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b6e5-135">To grant the new policy you created to Amos Marble, run:</span></span>  
   
   ```powershell
   Grant-CsMobilityPolicy -Identity "amos.marble@contoso.com"-PolicyName NoAppClientPolicy
   ```
   <span data-ttu-id="2b6e5-136">[CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) cmdlet에 대 한 자세한 내용을 확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="2b6e5-136">See more on the [Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) cmdlet.</span></span>
    
  <span data-ttu-id="2b6e5-137">이미 정책을 만든 경우 [CsMobilityPolicy](https://technet.microsoft.com/library/mt779147.aspx) cmdlet을 사용 하 여 기존 정책을 변경한 다음 [부여-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) cmdlet을 사용 하 여 사용자에 게 해당 설정을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b6e5-137">If you have already created a policy, you can use the [Set-CsMobilityPolicy](https://technet.microsoft.com/library/mt779147.aspx) cmdlet to make changes to the existing policy, and then use the [Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) cmdlet to apply the setting to your users.</span></span>
  
### <a name="prevent-a-user-from-making-voice-over-ip-calls-using-a-mobile-device"></a><span data-ttu-id="2b6e5-138">사용자가 모바일 장치를 사용 하 여 IP 통화를 할 수 없도록 설정</span><span class="sxs-lookup"><span data-stu-id="2b6e5-138">Prevent a user from making voice over IP calls using a mobile device</span></span>

- <span data-ttu-id="2b6e5-139">이러한 설정에 대 한 새 정책을 만들려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b6e5-139">To create a new policy for these settings, run:</span></span>
   
   ```powershell
   New-CsMobilityPolicy -Identity VoIPClientPolicy -EnableIPAudioVideo  $false
   ```
   <span data-ttu-id="2b6e5-140">[새로운 CsMobilityPolicy](https://technet.microsoft.com/library/mt779150.aspx) cmdlet에 대 한 자세한 내용을 확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="2b6e5-140">See more on the [New-CsMobilityPolicy](https://technet.microsoft.com/library/mt779150.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="2b6e5-141">만든 새 정책을 조직의 모든 사용자에 게 부여 하려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b6e5-141">To grant the new policy you created to all of the users in your organization, run:</span></span>
   
   ```powershell
   Grant-CsMobilityPolicy -Identity "amos.marble@contoso.com" -PolicyName VoIPClientPolicy
   ```

  <span data-ttu-id="2b6e5-142">[CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) cmdlet에 대 한 자세한 내용을 확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="2b6e5-142">See more on the [Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) cmdlet.</span></span>
    
<span data-ttu-id="2b6e5-143">이미 정책을 만든 경우 [CsMobilityPolicy](https://technet.microsoft.com/library/mt779147.aspx) cmdlet을 사용 하 여 기존 정책을 변경한 다음[부여-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) cmdlet을 사용 하 여 사용자에 게 해당 설정을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b6e5-143">If you have already created a policy, you can use the [Set-CsMobilityPolicy](https://technet.microsoft.com/library/mt779147.aspx) cmdlet to make changes to the existing policy, and then use the[Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) cmdlet to apply the setting to your users.</span></span>
  
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="2b6e5-144">Windows PowerShell에 대 한 자세한 정보를 확인 하 고 싶으신가요?</span><span class="sxs-lookup"><span data-stu-id="2b6e5-144">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="2b6e5-145">Windows PowerShell은 사용자 및 허용 되지 않거나 수행할 수 있는 사용자를 관리 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b6e5-145">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="2b6e5-146">Windows PowerShell을 사용 하면 여러 작업을 수행할 때 일상 업무를 단순화할 수 있는 단일 관리 지점을 사용 하 여 Office 365 및 비즈니스용 Skype Online을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b6e5-146">With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="2b6e5-147">Windows PowerShell을 시작 하려면 다음 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2b6e5-147">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="2b6e5-148">Windows PowerShell 및 Lync Online 소개</span><span class="sxs-lookup"><span data-stu-id="2b6e5-148">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="2b6e5-149">Windows PowerShell을 사용 하 여 Office 365를 관리 하는 데 필요한 여섯 가지 이유</span><span class="sxs-lookup"><span data-stu-id="2b6e5-149">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Office 365</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="2b6e5-150">Windows PowerShell에는 한 번에 여러 사용자의 설정을 변경 하는 경우와 같이 Microsoft 365 관리 센터를 사용 하는 경우에만 속도, 단순성, 생산성 등 다양 한 이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b6e5-150">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="2b6e5-151">다음 항목에서 이러한 이점에 대해 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="2b6e5-151">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="2b6e5-152">Windows PowerShell을 사용 하 여 Office 365를 관리 하는 가장 좋은 방법</span><span class="sxs-lookup"><span data-stu-id="2b6e5-152">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="2b6e5-153">Windows PowerShell을 사용 하 여 비즈니스용 Skype Online 관리</span><span class="sxs-lookup"><span data-stu-id="2b6e5-153">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="2b6e5-154">Windows PowerShell을 사용 하 여 일반적인 비즈니스용 Skype Online 관리 작업 수행</span><span class="sxs-lookup"><span data-stu-id="2b6e5-154">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="2b6e5-155">관련 항목</span><span class="sxs-lookup"><span data-stu-id="2b6e5-155">Related topics</span></span>
[<span data-ttu-id="2b6e5-156">사용자 지정 외부 액세스 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="2b6e5-156">Create custom external access policies</span></span>](create-custom-external-access-policies.md)

[<span data-ttu-id="2b6e5-157">점 대 점 파일 전송 차단</span><span class="sxs-lookup"><span data-stu-id="2b6e5-157">Block point-to-point file transfers</span></span>](block-point-to-point-file-transfers.md)

[<span data-ttu-id="2b6e5-158">조직의 클라이언트 정책 설정</span><span class="sxs-lookup"><span data-stu-id="2b6e5-158">Set up client policies for your organization</span></span>](set-up-client-policies-for-your-organization.md)

[<span data-ttu-id="2b6e5-159">조직에서 회의 정책 설정</span><span class="sxs-lookup"><span data-stu-id="2b6e5-159">Set up conferencing policies in your organization</span></span>](set-up-conferencing-policies-for-your-organization.md)

  
 
