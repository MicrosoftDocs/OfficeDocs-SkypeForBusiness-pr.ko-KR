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
description: 사용자가 휴대폰 번호가 아닌 직장 전화 번호를 사용하여 휴대폰에서 전화를 걸고 비즈니스용 Skype 수 있는 기능 등 모바일 장치에서 비즈니스용 Skype 온라인에 연결하는 방법을 설정할 수 있습니다. 이동성 정책을 사용하여 전화를 걸거나 받을 Wi-Fi 연결해야 할 수도 있습니다.
ms.openlocfilehash: e29a02bddcb9ace29ebd059f8cbc42c5a85c3f12
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52240070"
---
# <a name="set-up-mobile-policies-for-your-organization"></a><span data-ttu-id="eff27-104">조직의 모바일 정책 설정</span><span class="sxs-lookup"><span data-stu-id="eff27-104">Set up mobile policies for your organization</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

<span data-ttu-id="eff27-105">사용자가 휴대폰 번호가 아닌 직장 전화 번호를 사용하여 휴대폰에서 전화를 걸고 비즈니스용 Skype 수 있는 기능 등 모바일 장치에서 비즈니스용 Skype 온라인에 연결하는 방법을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eff27-105">You can set up how your users connect to Skype for Business Online using the Skype for Business app on mobile devices, such as a feature that enables users to make and receive phone calls on their mobile phone by using their work phone number instead of their mobile phone number.</span></span> <span data-ttu-id="eff27-106">이동성 정책을 사용하여 전화를 걸거나 받을 Wi-Fi 연결해야 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eff27-106">Mobility policies can also be used to require Wi-Fi connections when making or receiving calls.</span></span>
  
<span data-ttu-id="eff27-107">정책을 만들 때 모바일 정책 설정을 구성하거나 **Set-CsMobilityPolicy** cmdlet을 사용하여 기존 정책의 설정을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eff27-107">Mobile policy settings can be configured at the time a policy is created, or you can use the **Set-CsMobilityPolicy** cmdlet to modify the settings of an existing policy.</span></span>
  
## <a name="set-your-mobile-policies"></a><span data-ttu-id="eff27-108">모바일 정책 설정</span><span class="sxs-lookup"><span data-stu-id="eff27-108">Set your mobile policies</span></span>

> [!NOTE]
> <span data-ttu-id="eff27-109">온라인의 모든 모바일 정책 설정의 경우 비즈니스용 Skype 사용해야 Windows PowerShell 관리  센터를 사용할 **수 비즈니스용 Skype 없습니다.**</span><span class="sxs-lookup"><span data-stu-id="eff27-109">For all of the mobile policy settings in Skype for Business Online, you must use Windows PowerShell and you **can't use** the **Skype for Business admin center**.</span></span> 
  
### <a name="start-windows-powershell"></a><span data-ttu-id="eff27-110">시작 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="eff27-110">Start Windows PowerShell</span></span>

> [!NOTE]
> <span data-ttu-id="eff27-111">비즈니스용 Skype 온라인 커넥터는 현재 최신 PowerShell Teams 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="eff27-111">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span> <span data-ttu-id="eff27-112">최신 PowerShell 공개 Teams 사용하는 경우 온라인 커넥터를 비즈니스용 Skype 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="eff27-112">If you're using the latest Teams PowerShell public release, you don't need to install the Skype for Business Online Connector.</span></span>
1. <span data-ttu-id="eff27-113">[PowerShell Teams 설치합니다.](/microsoftteams/teams-powershell-install)</span><span class="sxs-lookup"><span data-stu-id="eff27-113">Install the [Teams PowerShell module](/microsoftteams/teams-powershell-install).</span></span>
    
2. <span data-ttu-id="eff27-114">명령 Windows PowerShell 프롬프트를 열고 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="eff27-114">Open a Windows PowerShell command prompt and run the following commands:</span></span> 

   ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```
   <span data-ttu-id="eff27-115">시작에 대한 자세한 Windows PowerShell 을 참조하세요커넥트 Microsoft 365 Office 365 단일 창에서 모든 Windows PowerShell 또는 [Windows PowerShell.](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md) [](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window)</span><span class="sxs-lookup"><span data-stu-id="eff27-115">If you want more information about starting Windows PowerShell, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
   
### <a name="require-a-wifi-connection-for-video-for-a-user"></a><span data-ttu-id="eff27-116">사용자에 대한 비디오에 WiFi 연결 필요</span><span class="sxs-lookup"><span data-stu-id="eff27-116">Require a WiFi connection for video for a user</span></span>

- <span data-ttu-id="eff27-117">이러한 설정에 대한 새 정책을 만들하려면 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="eff27-117">To create a new policy for these settings, run:</span></span>
   
   ```powershell
   New-CsMobilityPolicy -Identity MobilityPolicy -RequireWIFIForIPVideo $true
   ```
   <span data-ttu-id="eff27-118">[New-CsMobilityPolicy](/powershell/module/skype/New-CsMobilityPolicy) cmdlet을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="eff27-118">See more on the [New-CsMobilityPolicy](/powershell/module/skype/New-CsMobilityPolicy) cmdlet.</span></span>
    
- <span data-ttu-id="eff27-119">조직의 모든 사용자에게 만든 새 정책을 부여하기 위해 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="eff27-119">To grant the new policy you created to all of the users in your organization, run:</span></span>
   
   ```powershell
   Grant-CsMobilityPolicy -Identity"amos.marble@contoso.com" -PolicyName MobilityPolicy
   ```
   <span data-ttu-id="eff27-120">[Grant-CsMobilityPolicy](/powershell/module/skype/Grant-CsMobilityPolicy) cmdlet을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="eff27-120">See more on the [Grant-CsMobilityPolicy](/powershell/module/skype/Grant-CsMobilityPolicy) cmdlet.</span></span>
    
  <span data-ttu-id="eff27-121">정책을 이미 만든 경우 [Set-CsMobilityPolicy](/powershell/module/skype/Set-CsMobilityPolicy) cmdlet을 사용하여 기존 정책을 변경한 다음[Grant-CsMobilityPolicy](/powershell/module/skype/Grant-CsMobilityPolicy) cmdlet을 사용하여 사용자에게 설정을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eff27-121">If you have already created a policy, you can use the [Set-CsMobilityPolicy](/powershell/module/skype/Set-CsMobilityPolicy) cmdlet to make changes to the existing policy, and then use the[Grant-CsMobilityPolicy](/powershell/module/skype/Grant-CsMobilityPolicy) cmdlet to apply the setting to your users.</span></span>
  
### <a name="prevent-a-user-from-using-the-skype-for-business-app"></a><span data-ttu-id="eff27-122">사용자가 앱 사용 비즈니스용 Skype 방지</span><span class="sxs-lookup"><span data-stu-id="eff27-122">Prevent a user from using the Skype for Business app</span></span>

- <span data-ttu-id="eff27-123">이러한 설정에 대한 새 정책을 만들하려면 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="eff27-123">To create a new policy for these settings, run:</span></span>
  ```PowerShell
  New-CsMobilityPolicy -Identity NoAppClientPolicy -EnableMobility $false 
  ```
  <span data-ttu-id="eff27-124">[New-CsMobilityPolicy](/powershell/module/skype/New-CsMobilityPolicy) cmdlet을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="eff27-124">See more on the [New-CsMobilityPolicy](/powershell/module/skype/New-CsMobilityPolicy) cmdlet.</span></span>
    
- <span data-ttu-id="eff27-125">Amos Marble에 만든 새 정책을 부여하기 위해 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="eff27-125">To grant the new policy you created to Amos Marble, run:</span></span>  
   
   ```powershell
   Grant-CsMobilityPolicy -Identity "amos.marble@contoso.com"-PolicyName NoAppClientPolicy
   ```
   <span data-ttu-id="eff27-126">[Grant-CsMobilityPolicy](/powershell/module/skype/Grant-CsMobilityPolicy) cmdlet을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="eff27-126">See more on the [Grant-CsMobilityPolicy](/powershell/module/skype/Grant-CsMobilityPolicy) cmdlet.</span></span>
    
  <span data-ttu-id="eff27-127">정책을 이미 만든 경우 [Set-CsMobilityPolicy](/powershell/module/skype/Set-CsMobilityPolicy) cmdlet을 사용하여 기존 정책을 변경한 다음 [Grant-CsMobilityPolicy](/powershell/module/skype/Grant-CsMobilityPolicy) cmdlet을 사용하여 사용자에게 설정을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eff27-127">If you have already created a policy, you can use the [Set-CsMobilityPolicy](/powershell/module/skype/Set-CsMobilityPolicy) cmdlet to make changes to the existing policy, and then use the [Grant-CsMobilityPolicy](/powershell/module/skype/Grant-CsMobilityPolicy) cmdlet to apply the setting to your users.</span></span>
  
### <a name="prevent-a-user-from-making-voice-over-ip-calls-using-a-mobile-device"></a><span data-ttu-id="eff27-128">사용자가 모바일 디바이스를 사용하여 IP 통화를 통해 음성 통화를 할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="eff27-128">Prevent a user from making voice over IP calls using a mobile device</span></span>

- <span data-ttu-id="eff27-129">이러한 설정에 대한 새 정책을 만들하려면 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="eff27-129">To create a new policy for these settings, run:</span></span>
   
   ```powershell
   New-CsMobilityPolicy -Identity VoIPClientPolicy -EnableIPAudioVideo  $false
   ```
   <span data-ttu-id="eff27-130">[New-CsMobilityPolicy](/powershell/module/skype/New-CsMobilityPolicy) cmdlet을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="eff27-130">See more on the [New-CsMobilityPolicy](/powershell/module/skype/New-CsMobilityPolicy) cmdlet.</span></span>
    
- <span data-ttu-id="eff27-131">조직의 모든 사용자에게 만든 새 정책을 부여하기 위해 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="eff27-131">To grant the new policy you created to all of the users in your organization, run:</span></span>
   
   ```powershell
   Grant-CsMobilityPolicy -Identity "amos.marble@contoso.com" -PolicyName VoIPClientPolicy
   ```

  <span data-ttu-id="eff27-132">[Grant-CsMobilityPolicy](/powershell/module/skype/Grant-CsMobilityPolicy) cmdlet을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="eff27-132">See more on the [Grant-CsMobilityPolicy](/powershell/module/skype/Grant-CsMobilityPolicy) cmdlet.</span></span>
    
<span data-ttu-id="eff27-133">정책을 이미 만든 경우 [Set-CsMobilityPolicy](/powershell/module/skype/Set-CsMobilityPolicy) cmdlet을 사용하여 기존 정책을 변경한 다음[Grant-CsMobilityPolicy](/powershell/module/skype/Grant-CsMobilityPolicy) cmdlet을 사용하여 사용자에게 설정을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eff27-133">If you have already created a policy, you can use the [Set-CsMobilityPolicy](/powershell/module/skype/Set-CsMobilityPolicy) cmdlet to make changes to the existing policy, and then use the[Grant-CsMobilityPolicy](/powershell/module/skype/Grant-CsMobilityPolicy) cmdlet to apply the setting to your users.</span></span>
  
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="eff27-134">자세한 정보를 Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="eff27-134">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="eff27-135">Windows PowerShell 모든 것은 사용자 관리와 사용자가 허용되거나 허용되지 않는 작업을 관리하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="eff27-135">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="eff27-136">이 Windows PowerShell 여러 작업을 수행할 때 일상적인 작업을 단순화할 수 있는 단일 관리 Microsoft 365 Office 365 비즈니스용 Skype 온라인에서 관리하거나 온라인을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eff27-136">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="eff27-137">다음 항목을 Windows PowerShell 다음 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="eff27-137">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="eff27-138">Windows PowerShell 및 비즈니스용 Skype Online 소개</span><span class="sxs-lookup"><span data-stu-id="eff27-138">An introduction to Windows PowerShell and Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="eff27-139">Windows PowerShell 관리하기 위해 Windows PowerShell 이유 Microsoft 365 Office 365</span><span class="sxs-lookup"><span data-stu-id="eff27-139">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Microsoft 365 or Office 365</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
- <span data-ttu-id="eff27-140">Windows PowerShell 많은 사용자에 대해 한 Microsoft 365 설정하는 경우와 같이 관리 센터를 사용하는 것만 사용하여 속도, 단순성 및 생산성에 많은 이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eff27-140">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="eff27-141">다음 항목에서 이러한 이점에 대해 자세히 알아보습니다.</span><span class="sxs-lookup"><span data-stu-id="eff27-141">Learn about these advantages in the following topics:</span></span>
    
  - <span data-ttu-id="eff27-142">[사용자와 함께 Microsoft 365 또는 Office 365 가장 Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="eff27-142">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
  - [<span data-ttu-id="eff27-143">온라인 Windows PowerShell 관리하기 위해 비즈니스용 Skype 사용</span><span class="sxs-lookup"><span data-stu-id="eff27-143">Using Windows PowerShell to manage Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="eff27-144">일반적인 Windows PowerShell 관리 작업을 수행하는 데 비즈니스용 Skype 사용</span><span class="sxs-lookup"><span data-stu-id="eff27-144">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
## <a name="related-topics"></a><span data-ttu-id="eff27-145">관련 주제</span><span class="sxs-lookup"><span data-stu-id="eff27-145">Related topics</span></span>
[<span data-ttu-id="eff27-146">사용자 지정 외부 액세스 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="eff27-146">Create custom external access policies</span></span>](create-custom-external-access-policies.md)

[<span data-ttu-id="eff27-147">지점 및 지점 파일 전송 차단</span><span class="sxs-lookup"><span data-stu-id="eff27-147">Block point-to-point file transfers</span></span>](block-point-to-point-file-transfers.md)

[<span data-ttu-id="eff27-148">조직의 클라이언트 정책 설정</span><span class="sxs-lookup"><span data-stu-id="eff27-148">Set up client policies for your organization</span></span>](set-up-client-policies-for-your-organization.md)

[<span data-ttu-id="eff27-149">조직에서 회의 정책 설정</span><span class="sxs-lookup"><span data-stu-id="eff27-149">Set up conferencing policies in your organization</span></span>](set-up-conferencing-policies-for-your-organization.md)

  
