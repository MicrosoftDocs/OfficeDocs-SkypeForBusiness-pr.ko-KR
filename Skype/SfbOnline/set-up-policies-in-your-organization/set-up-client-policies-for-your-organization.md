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
f1keywords: None
ms.custom:
- Setup
description: 클라이언트 정책은 사용자에 게 제공 되는 비즈니스용 Skype Online의 기능을 결정 하는 데 도움이 됩니다. 예를 들어, 다른 사용자에 게이 권한을 거부 하면서 파일을 전송할 권한을 일부 사용자에 게 부여할 수 있습니다.
ms.openlocfilehash: c765f26aa1fe6ac1f041773a8aedb0ff48b52db8
ms.sourcegitcommit: 4c041e8a7c39bd6517605ed7fc9aab18cf466596
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/18/2019
ms.locfileid: "37642387"
---
# <a name="set-up-client-policies-for-your-organization"></a><span data-ttu-id="6c4c4-103">조직의 클라이언트 정책 설정</span><span class="sxs-lookup"><span data-stu-id="6c4c4-103">Set up client policies for your organization</span></span>

<span data-ttu-id="6c4c4-104">클라이언트 정책은 사용자에 게 제공 되는 비즈니스용 Skype Online의 기능을 결정 하는 데 도움이 됩니다. 예를 들어, 다른 사용자에 게이 권한을 거부 하면서 파일을 전송할 권한을 일부 사용자에 게 부여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c4c4-104">Client policies help determine the features of Skype for Business Online that are made available to users; for example, you might give some users the right to transfer files while denying this right to other users.</span></span>
  
<span data-ttu-id="6c4c4-105">정책을 만들 때 클라이언트 정책 설정을 구성 하거나, **Set CsClientPolicy** cmdlet을 사용 하 여 기존 정책의 설정을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c4c4-105">Client policy settings can be configured at the time a policy is created, or you can use the **Set-CsClientPolicy** cmdlet to modify the settings of an existing policy.</span></span>
  
## <a name="set-your-client-policies"></a><span data-ttu-id="6c4c4-106">클라이언트 정책 설정</span><span class="sxs-lookup"><span data-stu-id="6c4c4-106">Set your client policies</span></span>

> [!NOTE]
> <span data-ttu-id="6c4c4-107">비즈니스용 Skype Online의 모든 클라이언트 정책 설정에 대해 Windows PowerShell을 사용 해야 하며 **비즈니스용 skype 관리 센터**를 **사용할 수 없습니다** .</span><span class="sxs-lookup"><span data-stu-id="6c4c4-107">For all of the client policy settings in Skype for Business Online, you must use Windows PowerShell and you **can't use** the **Skype for Business admin center**.</span></span> 
  
### <a name="verify-and-start-windows-powershell"></a><span data-ttu-id="6c4c4-108">Windows PowerShell 확인 및 시작</span><span class="sxs-lookup"><span data-stu-id="6c4c4-108">Verify and start Windows PowerShell</span></span>

- <span data-ttu-id="6c4c4-109">**Windows PowerShell 버전 3.0 이상을 실행 하 고 있는지 확인**</span><span class="sxs-lookup"><span data-stu-id="6c4c4-109">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
    
1. <span data-ttu-id="6c4c4-110">버전 3.0 이상을 실행 하 고 있는지 확인 하려면 **시작 메뉴** > 에서**Windows PowerShell**을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c4c4-110">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="6c4c4-111">**Windows PowerShell** 창에서 _Get-Host_ 를 입력 하 여 버전을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c4c4-111">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="6c4c4-112">버전 3.0 이상이 없는 경우 Windows PowerShell 업데이트를 다운로드 하 여 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c4c4-112">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell.</span></span> <span data-ttu-id="6c4c4-113">Windows [Management 프레임 워크 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) 를 참조 하 여 windows PowerShell을 버전 4.0로 다운로드 하 고 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c4c4-113">See [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0.</span></span> <span data-ttu-id="6c4c4-114">메시지가 표시 되 면 컴퓨터를 다시 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c4c4-114">Restart your computer when you are prompted.</span></span>
    
4. <span data-ttu-id="6c4c4-115">비즈니스용 skype Online에 연결 되는 원격 Windows PowerShell 세션을 만들 수 있는 비즈니스용 Skype Online 용 Windows PowerShell 모듈을 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c4c4-115">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span> <span data-ttu-id="6c4c4-116">이 모듈은 64 비트 컴퓨터 에서만 지원 되며 비즈니스용 [Skype Online 용 Windows PowerShell 모듈](https://go.microsoft.com/fwlink/?LinkId=294688)의 Microsoft 다운로드 센터에서 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c4c4-116">This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688).</span></span> <span data-ttu-id="6c4c4-117">메시지가 표시 되 면 컴퓨터를 다시 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c4c4-117">Restart your computer if you are prompted.</span></span>
    
    <span data-ttu-id="6c4c4-118">자세한 정보를 알고 싶은 경우 [모든 Office 365 서비스에 단일 Windows PowerShell 창으로 연결](https://technet.microsoft.com/EN-US/library/dn568015.aspx)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6c4c4-118">If you need to know more, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span></span>
    
- <span data-ttu-id="6c4c4-119">**Windows PowerShell 세션 시작**</span><span class="sxs-lookup"><span data-stu-id="6c4c4-119">**Start a Windows PowerShell session**</span></span>
    
1. <span data-ttu-id="6c4c4-120">**시작 메뉴** > 에서**Windows PowerShell**을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c4c4-120">From the **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="6c4c4-121">**Windows PowerShell** 창에서 다음을 실행 하 여 Office 365 조직에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c4c4-121">In the **Windows PowerShell** window, connect to your Office 365 organization by running:</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="6c4c4-122">비즈니스용 Skype Online Windows PowerShell 모듈을 처음 사용 하는 경우에만 **Import-Module** 명령을 실행 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c4c4-122">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>

   ```      
    Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
   ```

   <span data-ttu-id="6c4c4-123">Windows PowerShell을 시작 하는 방법에 대 한 자세한 내용은 [단일 Windows powershell 창에서 모든 Office 365 서비스에 연결](https://technet.microsoft.com/EN-US/library/dn568015.aspx) 또는 [Windows Powershell 용 컴퓨터 설정을](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6c4c4-123">If you want more information about starting Windows PowerShell, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
    
### <a name="disable-emoticons-and-presence-notifications-and-prevent-saving-of-ims"></a><span data-ttu-id="6c4c4-124">이모티콘 및 현재 상태 알림을 사용 하지 않도록 설정 하 고 메신저 저장 방지</span><span class="sxs-lookup"><span data-stu-id="6c4c4-124">Disable emoticons and presence notifications and prevent saving of IMs</span></span>

- <span data-ttu-id="6c4c4-125">이러한 설정에 대 한 새 정책을 만들려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c4c4-125">To create a new policy for these settings, run:</span></span>
    
> 
>   ```
>   New-CsClientPolicy -Identity ClientPolicy -DisableEmoticons $true -DisablePresenceNote -$true -DisableSavingIM $true
>   ```

  <span data-ttu-id="6c4c4-126">[새로운 CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779155.aspx) cmdlet에 대 한 자세한 내용을 확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="6c4c4-126">See more on the [New-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779155.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="6c4c4-127">만든 새 정책을 조직의 모든 사용자에 게 부여 하려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c4c4-127">To grant the new policy you created to all of the users in your organization, run:</span></span>
    
> 
>   ```
>   Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName ClientPolicy
>   ```

  <span data-ttu-id="6c4c4-128">[부여-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx) cmdlet에 대 한 자세한 정보를 확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="6c4c4-128">See more on the [Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx) cmdlet.</span></span>
    
<span data-ttu-id="6c4c4-129">정책을 이미 만든 경우에는 [Set-csclientpolicy](https://technet.microsoft.com/en-us/library/mt779153.aspx) cmdlet을 사용 하 여 기존 정책을 변경한 다음 사용자에 게 설정을 적용할 수 있도록 [허용-csclientpolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx) cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c4c4-129">If you have already created a policy, you can use the [Set-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779153.aspx) cmdlet to make changes to the existing policy, and then use the [Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx) cmdlet to apply the settings to your users.</span></span>
  
### <a name="enable-urls-or-hyperlinks-to-be-clickable-in-ims"></a><span data-ttu-id="6c4c4-130">IMs에서 Url 또는 하이퍼링크를 클릭할 수 있도록 설정</span><span class="sxs-lookup"><span data-stu-id="6c4c4-130">Enable URLs or hyperlinks to be clickable in IMs</span></span>

- <span data-ttu-id="6c4c4-131">이러한 설정에 대 한 새 정책을 만들려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c4c4-131">To create a new policy for these settings, run:</span></span>
    
> 
>   ```
>   New-CsClientPolicy -Identity URLClientPolicy -EnableURL $true
>   ```

  <span data-ttu-id="6c4c4-132">[새로운 CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779155.aspx) cmdlet에 대 한 자세한 내용을 확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="6c4c4-132">See more on the [New-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779155.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="6c4c4-133">만든 새 정책을 조직의 모든 사용자에 게 부여 하려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c4c4-133">To grant the new policy you created to all of the users in your organization, run:</span></span>
    
> 
>   ```
>   Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName URLClientPolicy
>   ```

  <span data-ttu-id="6c4c4-134">[부여-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx) cmdlet에 대 한 자세한 정보를 확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="6c4c4-134">See more on the [Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx) cmdlet.</span></span>
    
<span data-ttu-id="6c4c4-135">정책을 이미 만든 경우에는 [Set-csclientpolicy](https://technet.microsoft.com/en-us/library/mt779153.aspx) cmdlet을 사용 하 여 기존 정책을 변경한 다음 사용자에 게 설정을 적용할 수 있도록 [허용-csclientpolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx) cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c4c4-135">If you have already created a policy, you can use the [Set-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779153.aspx) cmdlet to make changes to the existing policy, and then use the [Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx) cmdlet to apply the settings to your users.</span></span>
  
### <a name="prevent-showing-recent-contacts"></a><span data-ttu-id="6c4c4-136">최근 대화 상대 표시 방지</span><span class="sxs-lookup"><span data-stu-id="6c4c4-136">Prevent showing recent contacts</span></span>

- <span data-ttu-id="6c4c4-137">이러한 설정에 대 한 새 정책을 만들려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c4c4-137">To create a new policy for these settings, run:</span></span>
  > 
  > ```
  > New-CsClientPolicy -Identity ContactsClientPolicy -ShowRecentContacts $false 
  > ```

  <span data-ttu-id="6c4c4-138">[새로운 CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779155.aspx) cmdlet에 대 한 자세한 내용을 확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="6c4c4-138">See more on the [New-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779155.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="6c4c4-139">만든 새 정책을 Amos 대리석에 부여 하려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c4c4-139">To grant the new policy you created to Amos Marble, run:</span></span>
  > 
  > ```
  > Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName ContactsClientPolicy
  > ```

  <span data-ttu-id="6c4c4-140">[부여-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx) cmdlet에 대 한 자세한 정보를 확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="6c4c4-140">See more on the [Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx) cmdlet.</span></span>
    
  <span data-ttu-id="6c4c4-141">정책을 이미 만든 경우에는 [Set-csclientpolicy](https://technet.microsoft.com/en-us/library/mt779153.aspx) cmdlet을 사용 하 여 기존 정책을 변경한 다음 사용자에 게 설정을 적용할 수 있도록 [허용-csclientpolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx) cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c4c4-141">If you have already created a policy, you can use the [Set-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779153.aspx) cmdlet to make changes to the existing policy, and then use the [Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx) cmdlet to apply the settings to your users.</span></span>
  
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="6c4c4-142">Windows PowerShell에 대 한 자세한 정보를 확인 하 고 싶으신가요?</span><span class="sxs-lookup"><span data-stu-id="6c4c4-142">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="6c4c4-143">Windows PowerShell은 사용자 및 허용 되지 않거나 수행할 수 있는 사용자를 관리 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c4c4-143">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="6c4c4-144">Windows PowerShell을 사용 하면 여러 작업을 수행할 때 일상 업무를 단순화할 수 있는 단일 관리 지점을 사용 하 여 Office 365 및 비즈니스용 Skype Online을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c4c4-144">With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="6c4c4-145">Windows PowerShell을 시작 하려면 다음 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6c4c4-145">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="6c4c4-146">Windows PowerShell 및 Lync Online 소개</span><span class="sxs-lookup"><span data-stu-id="6c4c4-146">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="6c4c4-147">Windows PowerShell을 사용 하 여 Office 365를 관리 하는 데 필요한 여섯 가지 이유</span><span class="sxs-lookup"><span data-stu-id="6c4c4-147">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Office 365</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="6c4c4-148">Windows PowerShell에는 한 번에 여러 사용자의 설정을 변경 하는 경우와 같이 Microsoft 365 관리 센터를 사용 하는 경우에만 속도, 단순성, 생산성 등 다양 한 이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c4c4-148">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="6c4c4-149">다음 항목에서 이러한 이점에 대해 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="6c4c4-149">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="6c4c4-150">Windows PowerShell을 사용 하 여 Office 365를 관리 하는 가장 좋은 방법</span><span class="sxs-lookup"><span data-stu-id="6c4c4-150">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="6c4c4-151">Windows PowerShell을 사용 하 여 비즈니스용 Skype Online 관리</span><span class="sxs-lookup"><span data-stu-id="6c4c4-151">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="6c4c4-152">Windows PowerShell을 사용 하 여 일반적인 비즈니스용 Skype Online 관리 작업 수행</span><span class="sxs-lookup"><span data-stu-id="6c4c4-152">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="6c4c4-153">관련 항목</span><span class="sxs-lookup"><span data-stu-id="6c4c4-153">Related topics</span></span>
[<span data-ttu-id="6c4c4-154">사용자 지정 외부 액세스 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="6c4c4-154">Create custom external access policies</span></span>](create-custom-external-access-policies.md)

[<span data-ttu-id="6c4c4-155">점 대 점 파일 전송 차단</span><span class="sxs-lookup"><span data-stu-id="6c4c4-155">Block point-to-point file transfers</span></span>](block-point-to-point-file-transfers.md)

[<span data-ttu-id="6c4c4-156">조직에서 회의 정책 설정</span><span class="sxs-lookup"><span data-stu-id="6c4c4-156">Set up conferencing policies in your organization</span></span>](set-up-conferencing-policies-for-your-organization.md)

  
 
