---
title: 조직의 클라이언트 정책 설정
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 0326b19f-4fd1-4b74-8791-df4c09a964b9
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
description: 클라이언트 정책은 사용자가 사용할 수 있도록 비즈니스용 Skype Online의 기능을 결정하는 데 도움이 됩니다. 예를 들어 일부 사용자에게 다른 사용자에게 이 권리가 거부되는 동안 파일을 전송할 수 있는 권리가 주어도 됩니다.
ms.openlocfilehash: 3706e6b4fafe15aa8b799170001af61b837968da
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51100534"
---
# <a name="set-up-client-policies-for-your-organization"></a><span data-ttu-id="208a7-103">조직의 클라이언트 정책 설정</span><span class="sxs-lookup"><span data-stu-id="208a7-103">Set up client policies for your organization</span></span>

<span data-ttu-id="208a7-104">클라이언트 정책은 사용자가 사용할 수 있도록 비즈니스용 Skype Online의 기능을 결정하는 데 도움이 됩니다. 예를 들어 일부 사용자에게 다른 사용자에게 이 권리가 거부되는 동안 파일을 전송할 수 있는 권리가 주어도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="208a7-104">Client policies help determine the features of Skype for Business Online that are made available to users; for example, you might give some users the right to transfer files while denying this right to other users.</span></span>
  
<span data-ttu-id="208a7-105">정책을 만들 때 클라이언트 정책 설정을 구성하거나 **Set-CsClientPolicy** cmdlet을 사용하여 기존 정책의 설정을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="208a7-105">Client policy settings can be configured at the time a policy is created, or you can use the **Set-CsClientPolicy** cmdlet to modify the settings of an existing policy.</span></span>
  
## <a name="set-your-client-policies"></a><span data-ttu-id="208a7-106">클라이언트 정책 설정</span><span class="sxs-lookup"><span data-stu-id="208a7-106">Set your client policies</span></span>

> [!NOTE]
> <span data-ttu-id="208a7-107">비즈니스용 Skype Online의 모든 클라이언트 정책 설정의 경우 비즈니스용  Skype Windows PowerShell 비즈니스용 Skype 관리 센터를 사용할 **수 없습니다.**</span><span class="sxs-lookup"><span data-stu-id="208a7-107">For all of the client policy settings in Skype for Business Online, you must use Windows PowerShell and you **can't use** the **Skype for Business admin center**.</span></span> 
  
### <a name="start-windows-powershell"></a><span data-ttu-id="208a7-108">시작 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="208a7-108">Start Windows PowerShell</span></span>

> [!NOTE]
> <span data-ttu-id="208a7-109">비즈니스용 Skype Online 커넥터는 현재 최신 Teams PowerShell 모듈의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="208a7-109">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span> <span data-ttu-id="208a7-110">최신 Teams PowerShell 공개 릴리스를 사용하는 경우 비즈니스용 Skype Online 커넥터를 설치할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="208a7-110">If you're using the latest Teams PowerShell public release, you don't need to install the Skype for Business Online Connector.</span></span>
1. <span data-ttu-id="208a7-111">Teams [PowerShell 모듈을 설치합니다.](/microsoftteams/teams-powershell-install)</span><span class="sxs-lookup"><span data-stu-id="208a7-111">Install the [Teams PowerShell module](/microsoftteams/teams-powershell-install).</span></span>
    
2. <span data-ttu-id="208a7-112">명령 Windows PowerShell 프롬프트를 열고 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="208a7-112">Open a Windows PowerShell command prompt and run the following commands:</span></span> 

    ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```
   <span data-ttu-id="208a7-113">시작에 대한 자세한 Windows PowerShell 단일 창에서 모든 [Microsoft 365 또는 Office 365](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window) 서비스에 연결하거나 Windows PowerShell 에 대한 컴퓨터를 [Windows PowerShell.](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="208a7-113">If you want more information about starting Windows PowerShell, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
 
### <a name="disable-emoticons-and-presence-notifications-and-prevent-saving-of-ims"></a><span data-ttu-id="208a7-114">이모티콘 및 현재 상태 알림을 사용하지 않도록 설정하고 IM 저장을 방지합니다.</span><span class="sxs-lookup"><span data-stu-id="208a7-114">Disable emoticons and presence notifications and prevent saving of IMs</span></span>

- <span data-ttu-id="208a7-115">이러한 설정에 대한 새 정책을 만들하려면 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="208a7-115">To create a new policy for these settings, run:</span></span>
    
 
   ```powershell
   New-CsClientPolicy -Identity ClientPolicy -DisableEmoticons $true -DisablePresenceNote -$true -DisableSavingIM $true
   ```

  <span data-ttu-id="208a7-116">[New-CsClientPolicy](/powershell/module/skype/New-CsClientPolicy) cmdlet을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="208a7-116">See more on the [New-CsClientPolicy](/powershell/module/skype/New-CsClientPolicy) cmdlet.</span></span>
    
- <span data-ttu-id="208a7-117">조직의 모든 사용자에게 만든 새 정책을 부여하기 위해 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="208a7-117">To grant the new policy you created to all of the users in your organization, run:</span></span>
    
 
   ```powershell
   Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName ClientPolicy
   ```

  <span data-ttu-id="208a7-118">[Grant-CsClientPolicy](/powershell/module/skype/Grant-CsClientPolicy) cmdlet을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="208a7-118">See more on the [Grant-CsClientPolicy](/powershell/module/skype/Grant-CsClientPolicy) cmdlet.</span></span>
    
<span data-ttu-id="208a7-119">정책을 이미 만든 경우 [Set-CsClientPolicy](/powershell/module/skype/Set-CsClientPolicy) cmdlet을 사용하여 기존 정책을 변경한 다음 [Grant-CsClientPolicy](/powershell/module/skype/Grant-CsClientPolicy) cmdlet을 사용하여 사용자에게 설정을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="208a7-119">If you have already created a policy, you can use the [Set-CsClientPolicy](/powershell/module/skype/Set-CsClientPolicy) cmdlet to make changes to the existing policy, and then use the [Grant-CsClientPolicy](/powershell/module/skype/Grant-CsClientPolicy) cmdlet to apply the settings to your users.</span></span>
  
### <a name="enable-urls-or-hyperlinks-to-be-clickable-in-ims"></a><span data-ttu-id="208a7-120">URL 또는 하이퍼링크를 IM에서 클릭할 수 있도록 설정</span><span class="sxs-lookup"><span data-stu-id="208a7-120">Enable URLs or hyperlinks to be clickable in IMs</span></span>

- <span data-ttu-id="208a7-121">이러한 설정에 대한 새 정책을 만들하려면 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="208a7-121">To create a new policy for these settings, run:</span></span>
    
 
   ```powershell
   New-CsClientPolicy -Identity URLClientPolicy -EnableURL $true
   ```

  <span data-ttu-id="208a7-122">[New-CsClientPolicy](/powershell/module/skype/New-CsClientPolicy) cmdlet을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="208a7-122">See more on the [New-CsClientPolicy](/powershell/module/skype/New-CsClientPolicy) cmdlet.</span></span>
    
- <span data-ttu-id="208a7-123">조직의 모든 사용자에게 만든 새 정책을 부여하기 위해 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="208a7-123">To grant the new policy you created to all of the users in your organization, run:</span></span>
    
 
   ```powershell
   Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName URLClientPolicy
   ```

  <span data-ttu-id="208a7-124">[Grant-CsClientPolicy](/powershell/module/skype/Grant-CsClientPolicy) cmdlet을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="208a7-124">See more on the [Grant-CsClientPolicy](/powershell/module/skype/Grant-CsClientPolicy) cmdlet.</span></span>
    
<span data-ttu-id="208a7-125">정책을 이미 만든 경우 [Set-CsClientPolicy](/powershell/module/skype/Set-CsClientPolicy) cmdlet을 사용하여 기존 정책을 변경한 다음 [Grant-CsClientPolicy](/powershell/module/skype/Grant-CsClientPolicy) cmdlet을 사용하여 사용자에게 설정을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="208a7-125">If you have already created a policy, you can use the [Set-CsClientPolicy](/powershell/module/skype/Set-CsClientPolicy) cmdlet to make changes to the existing policy, and then use the [Grant-CsClientPolicy](/powershell/module/skype/Grant-CsClientPolicy) cmdlet to apply the settings to your users.</span></span>
  
### <a name="prevent-showing-recent-contacts"></a><span data-ttu-id="208a7-126">최근 연락처 표시 방지</span><span class="sxs-lookup"><span data-stu-id="208a7-126">Prevent showing recent contacts</span></span>

- <span data-ttu-id="208a7-127">이러한 설정에 대한 새 정책을 만들하려면 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="208a7-127">To create a new policy for these settings, run:</span></span>
   
   ```powershell
   New-CsClientPolicy -Identity ContactsClientPolicy -ShowRecentContacts $false 
   ```

  <span data-ttu-id="208a7-128">[New-CsClientPolicy](/powershell/module/skype/New-CsClientPolicy) cmdlet을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="208a7-128">See more on the [New-CsClientPolicy](/powershell/module/skype/New-CsClientPolicy) cmdlet.</span></span>
    
- <span data-ttu-id="208a7-129">Amos Marble에 만든 새 정책을 부여하기 위해 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="208a7-129">To grant the new policy you created to Amos Marble, run:</span></span>
   
   ```powershell
   Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName ContactsClientPolicy
   ```

  <span data-ttu-id="208a7-130">[Grant-CsClientPolicy](/powershell/module/skype/Grant-CsClientPolicy) cmdlet을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="208a7-130">See more on the [Grant-CsClientPolicy](/powershell/module/skype/Grant-CsClientPolicy) cmdlet.</span></span>
    
  <span data-ttu-id="208a7-131">정책을 이미 만든 경우 [Set-CsClientPolicy](/powershell/module/skype/Set-CsClientPolicy) cmdlet을 사용하여 기존 정책을 변경한 다음 [Grant-CsClientPolicy](/powershell/module/skype/Grant-CsClientPolicy) cmdlet을 사용하여 사용자에게 설정을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="208a7-131">If you have already created a policy, you can use the [Set-CsClientPolicy](/powershell/module/skype/Set-CsClientPolicy) cmdlet to make changes to the existing policy, and then use the [Grant-CsClientPolicy](/powershell/module/skype/Grant-CsClientPolicy) cmdlet to apply the settings to your users.</span></span>
  
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="208a7-132">자세한 정보를 Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="208a7-132">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="208a7-133">Windows PowerShell 모든 것은 사용자 관리와 사용자가 허용되거나 허용되지 않는 작업을 관리하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="208a7-133">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="208a7-134">이 Windows PowerShell 여러 작업을 수행할 때 일상적인 작업을 단순화할 수 있는 단일 관리 지점을 사용하여 Microsoft 365 또는 Office 365 및 비즈니스용 Skype Online을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="208a7-134">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="208a7-135">다음 항목을 Windows PowerShell 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="208a7-135">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="208a7-136">Windows PowerShell 및 비즈니스용 Skype Online 소개</span><span class="sxs-lookup"><span data-stu-id="208a7-136">An introduction to Windows PowerShell and Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="208a7-137">Microsoft 365 또는 Office 365를 Windows PowerShell 사용하려는 6 가지 이유</span><span class="sxs-lookup"><span data-stu-id="208a7-137">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Microsoft 365 or Office 365</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
- <span data-ttu-id="208a7-138">Windows PowerShell 사용자에 대한 설정을 한 번씩 변경하는 경우와 같이 Microsoft 365 관리 센터를 사용하는 경우와 같이 Microsoft 365 관리 센터를 사용하는 것 이상으로 속도, 단순성 및 생산성에 많은 이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="208a7-138">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="208a7-139">다음 항목에서 이러한 이점에 대해 자세히 알아보습니다.</span><span class="sxs-lookup"><span data-stu-id="208a7-139">Learn about these advantages in the following topics:</span></span>
    
  - <span data-ttu-id="208a7-140">[Microsoft 365 또는 Office 365를 관리하는 가장 좋은 Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="208a7-140">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
  - [<span data-ttu-id="208a7-141">비즈니스용 skype Windows PowerShell 관리하기 위해 사용</span><span class="sxs-lookup"><span data-stu-id="208a7-141">Using Windows PowerShell to manage Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="208a7-142">비즈니스용 Windows PowerShell Skype 온라인 관리 작업을 수행하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="208a7-142">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
## <a name="related-topics"></a><span data-ttu-id="208a7-143">관련 항목</span><span class="sxs-lookup"><span data-stu-id="208a7-143">Related topics</span></span>
[<span data-ttu-id="208a7-144">사용자 지정 외부 액세스 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="208a7-144">Create custom external access policies</span></span>](create-custom-external-access-policies.md)

[<span data-ttu-id="208a7-145">지점 및 지점 파일 전송 차단</span><span class="sxs-lookup"><span data-stu-id="208a7-145">Block point-to-point file transfers</span></span>](block-point-to-point-file-transfers.md)

[<span data-ttu-id="208a7-146">조직에서 회의 정책 설정</span><span class="sxs-lookup"><span data-stu-id="208a7-146">Set up conferencing policies in your organization</span></span>](set-up-conferencing-policies-for-your-organization.md)

  
