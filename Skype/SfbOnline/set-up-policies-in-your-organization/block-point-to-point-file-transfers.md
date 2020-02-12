---
title: 점 대 점 파일 전송 차단
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 9adf9859-de5b-461e-92ea-b6ce4dd2f7c1
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
description: 비즈니스용 Skype Online에서는 기존 회의 정책 설정의 일부로 서 지점간 (P2P) 파일 전송을 제어할 수 있습니다. 그러나이 방법을 사용 하면 사용자가 같은 조직 내에 있거나 다른 조직의 페더레이션 사용자에 게 파일을 전송 하는지 여부에 관계 없이 파일 전송을 허용 하거나 차단할 수 있습니다. 아래 단계에 따라 페더레이션된 조직이 나 파트너와의 P2P 파일 전송을 차단할 수 있습니다.
ms.openlocfilehash: 7983ae72cd3b06a21fd4947883a3043d2506b92e
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/11/2020
ms.locfileid: "41887967"
---
# <a name="block-point-to-point-file-transfers"></a><span data-ttu-id="9ccd2-105">점 대 점 파일 전송 차단</span><span class="sxs-lookup"><span data-stu-id="9ccd2-105">Block Point-to-Point file transfers</span></span>

<span data-ttu-id="9ccd2-106">비즈니스용 Skype Online에서는 기존 회의 정책 설정의 일부로 서 지점간 (P2P) 파일 전송을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ccd2-106">In Skype for Business Online, you have ability to control Point-to-Point (P2P) file transfers as part of existing conferencing policy settings.</span></span> <span data-ttu-id="9ccd2-107">그러나이 방법을 사용 하면 사용자가 같은 조직 내에 있거나 다른 조직의 페더레이션 사용자에 게 파일을 전송 하는지 여부에 관계 없이 파일 전송을 허용 하거나 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ccd2-107">However, this allows or blocks file transfers for users whether or not they are transferring files to a user who is within the same organization or to a federated user from another organization.</span></span> <span data-ttu-id="9ccd2-108">아래 단계에 따라 페더레이션된 조직이 나 파트너와의 P2P 파일 전송을 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ccd2-108">Following the steps below, you can block P2P file transfers with federated organizations or partners.</span></span>
  
 <span data-ttu-id="9ccd2-109">일반적으로 내부 사용자는 P2P 파일 전송을 사용할 수 있지만 페더레이션 파트너와 파일 전송을 차단 하는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ccd2-109">A very common scenario is when you want to allow internal users to use P2P file transfer but block file transfer with federated partners.</span></span> <span data-ttu-id="9ccd2-110">이 시나리오에서는 다음을 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ccd2-110">For this scenario, you would need to do:</span></span>
  
- <span data-ttu-id="9ccd2-111">P2P 파일 전송 기능을 사용 하는 회의 정책 (_EnableP2PFileTransfer_ 설정 _)을_조직의 사용자에 게 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ccd2-111">Assign a conferencing policy with P2P file transfer enabled (_EnableP2PFileTransfer_ set to _True_) to users in your organization.</span></span>
    
- <span data-ttu-id="9ccd2-112">전역 외부 사용자 통신 정책 만들기 (_EnableP2PFileTransfer_ 를 _False_로 설정)로 차단 하 고 조직의 사용자에 게 해당 파일을 할당 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ccd2-112">Create a global external user communication policy set to block external P2P file transfers (_EnableP2PFileTransfer_ set to _False_) and assign it to a user in your organization.</span></span> 
    
<span data-ttu-id="9ccd2-113">이러한 설정에 대 한 자세한 내용은 [여기](https://technet.microsoft.com/library/mt228132.aspx)에서 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ccd2-113">You can find out more about those settings [here](https://technet.microsoft.com/library/mt228132.aspx).</span></span>
  
<span data-ttu-id="9ccd2-114">조직 외부의 페더레이션 사용자가 정책이 적용 된 사용자에 게 파일을 보내려고 하면 **전송 실패** 오류가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ccd2-114">If a federated user outside your organization tries to send a file to a user where the policy has been applied, they will receive a **Transfer Failed** error.</span></span> <span data-ttu-id="9ccd2-115">사용자가 파일을 보내려고 하면 **파일 전송이 해제** 오류 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ccd2-115">And if a user tries to send a file, they will receive a **File transfer is turned off** error.</span></span>
  
<span data-ttu-id="9ccd2-116">이 작업을 수행 하려면 사용자가 지원 되는 버전의 2016 간편 실행 비즈니스용 Skype 앱을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ccd2-116">To make this work, the user must be using a supported version of a 2016 Click-to-Run Skype for Business app that supports it.</span></span> <span data-ttu-id="9ccd2-117">다음의 최소 버전의 비즈니스용 Skype 2016 간편 실행 클라이언트를 선택 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ccd2-117">The following minimum version of Skype for Business 2016 Click-to-Run client is required:</span></span>
  
|<span data-ttu-id="9ccd2-118">**유형**</span><span class="sxs-lookup"><span data-stu-id="9ccd2-118">**Type**</span></span>|<span data-ttu-id="9ccd2-119">**릴리스 날짜**</span><span class="sxs-lookup"><span data-stu-id="9ccd2-119">**Release date**</span></span>|<span data-ttu-id="9ccd2-120">**버전**</span><span class="sxs-lookup"><span data-stu-id="9ccd2-120">**Version**</span></span>|<span data-ttu-id="9ccd2-121">**빌드한**</span><span class="sxs-lookup"><span data-stu-id="9ccd2-121">**Build**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="9ccd2-122">현재 채널의 첫 번째 릴리스</span><span class="sxs-lookup"><span data-stu-id="9ccd2-122">First Release for Current Channel</span></span>  <br/> |<span data-ttu-id="9ccd2-123">11/17/2016</span><span class="sxs-lookup"><span data-stu-id="9ccd2-123">11/17/2016</span></span>  <br/> |<span data-ttu-id="9ccd2-124">16.0.7571.2006</span><span class="sxs-lookup"><span data-stu-id="9ccd2-124">16.0.7571.2006</span></span>  <br/> |<span data-ttu-id="9ccd2-125">버전 1611 (빌드 7571.2006)</span><span class="sxs-lookup"><span data-stu-id="9ccd2-125">Version 1611 (Build 7571.2006)</span></span>  <br/> |
|<span data-ttu-id="9ccd2-126">현재 채널</span><span class="sxs-lookup"><span data-stu-id="9ccd2-126">Current Channel</span></span>  <br/> |<span data-ttu-id="9ccd2-127">12/6/2016</span><span class="sxs-lookup"><span data-stu-id="9ccd2-127">12/6/2016</span></span>  <br/> |<span data-ttu-id="9ccd2-128">16.0.7571.2072</span><span class="sxs-lookup"><span data-stu-id="9ccd2-128">16.0.7571.2072</span></span>  <br/> |<span data-ttu-id="9ccd2-129">버전 1611 (빌드 7571.2072)</span><span class="sxs-lookup"><span data-stu-id="9ccd2-129">Version 1611 (Build 7571.2072)</span></span>  <br/> |
|<span data-ttu-id="9ccd2-130">지연 채널</span><span class="sxs-lookup"><span data-stu-id="9ccd2-130">Deferred Channel</span></span>  <br/> |<span data-ttu-id="9ccd2-131">2/22/2017</span><span class="sxs-lookup"><span data-stu-id="9ccd2-131">2/22/2017</span></span>  <br/> |<span data-ttu-id="9ccd2-132">16.0.7369.2118</span><span class="sxs-lookup"><span data-stu-id="9ccd2-132">16.0.7369.2118</span></span>  <br/> |<span data-ttu-id="9ccd2-133">버전 1609 (빌드 7369.2118)</span><span class="sxs-lookup"><span data-stu-id="9ccd2-133">Version 1609 (Build 7369.2118)</span></span>  <br/> |
   
> [!CAUTION]
> <span data-ttu-id="9ccd2-134">이전 버전의 비즈니스용 Skype Windows 앱 또는 Mac 클라이언트를 사용 하는 사용자는 계속 파일을 전송할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ccd2-134">Users that are using older versions of Skype for Business Windows apps or Mac clients will still be able to transfer files.</span></span> 
  
## <a name="verify-and-start-windows-powershell"></a><span data-ttu-id="9ccd2-135">Windows PowerShell 확인 및 시작</span><span class="sxs-lookup"><span data-stu-id="9ccd2-135">Verify and start Windows PowerShell</span></span>

- <span data-ttu-id="9ccd2-136">**Windows PowerShell 버전 3.0 이상을 실행 하 고 있는지 확인**</span><span class="sxs-lookup"><span data-stu-id="9ccd2-136">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
    
    1. <span data-ttu-id="9ccd2-137">버전 3.0 이상을 실행 하 고 있는지 확인 하려면 **시작 메뉴** > 에서**Windows PowerShell**을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ccd2-137">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
        
    2. <span data-ttu-id="9ccd2-138">**Windows PowerShell** 창에서 _Get-Host_ 를 입력 하 여 버전을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ccd2-138">Check the version by typing _Get-Host_ in the **Windows PowerShell** window.</span></span>
        
    3. <span data-ttu-id="9ccd2-139">버전 3.0 이상이 없는 경우 Windows PowerShell 업데이트를 다운로드 하 여 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ccd2-139">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell.</span></span> <span data-ttu-id="9ccd2-140">Windows [Management 프레임 워크 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) 를 참조 하 여 windows PowerShell을 버전 4.0로 다운로드 하 고 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ccd2-140">See [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0.</span></span> <span data-ttu-id="9ccd2-141">메시지가 표시 되 면 컴퓨터를 다시 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ccd2-141">Restart your computer when you are prompted.</span></span>
        
    4. <span data-ttu-id="9ccd2-142">비즈니스용 skype Online에 연결 되는 원격 Windows PowerShell 세션을 만들 수 있는 비즈니스용 Skype Online 용 Windows PowerShell 모듈을 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ccd2-142">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span> <span data-ttu-id="9ccd2-143">이 모듈은 64 비트 컴퓨터 에서만 지원 되며 비즈니스용 [Skype Online 용 Windows PowerShell 모듈](https://go.microsoft.com/fwlink/?LinkId=294688)의 Microsoft 다운로드 센터에서 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ccd2-143">This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688).</span></span> <span data-ttu-id="9ccd2-144">메시지가 표시 되 면 컴퓨터를 다시 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ccd2-144">Restart your computer if you are prompted.</span></span>
    
    <span data-ttu-id="9ccd2-145">자세한 정보를 알고 싶은 경우 [모든 Office 365 서비스에 단일 Windows PowerShell 창으로 연결](https://technet.microsoft.com/library/dn568015.aspx)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9ccd2-145">If you need to know more, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx).</span></span>
    
- <span data-ttu-id="9ccd2-146">**Windows PowerShell 세션 시작**</span><span class="sxs-lookup"><span data-stu-id="9ccd2-146">**Start a Windows PowerShell session**</span></span>
    
    1. <span data-ttu-id="9ccd2-147">**시작 메뉴** > 에서**Windows PowerShell**을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ccd2-147">From the **Start Menu** > **Windows PowerShell**.</span></span>
        
    2. <span data-ttu-id="9ccd2-148">**Windows PowerShell** 창에서 다음을 실행 하 여 Office 365 조직에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ccd2-148">In the **Windows PowerShell** window, connect to your Office 365 organization by running:</span></span>
    
        > [!NOTE]
        > <span data-ttu-id="9ccd2-149">비즈니스용 Skype Online Windows PowerShell 모듈을 처음 사용 하는 경우에만 **Import-Module** 명령을 실행 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ccd2-149">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>

       ```PowerShell      
        Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
        $credential = Get-Credential
        $session = New-CsOnlineSession -Credential $credential
        Import-PSSession $session
       ```

   <span data-ttu-id="9ccd2-150">Windows PowerShell을 시작 하는 방법에 대 한 자세한 내용은 [단일 Windows powershell 창에서 모든 Office 365 서비스에 연결](https://technet.microsoft.com/library/dn568015.aspx) 또는 [Windows Powershell 용 컴퓨터 설정을](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9ccd2-150">If you want more information about starting Windows PowerShell, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
    
## <a name="disable-p2p-file-transfers-for-your-organization"></a><span data-ttu-id="9ccd2-151">조직에서 P2P 파일 전송을 사용 하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="9ccd2-151">Disable P2P file transfers for your organization</span></span>

<span data-ttu-id="9ccd2-152">기본적으로 _EnableP2PFileTransfer_ 는 조직의 글로벌 정책에 따라 사용 하도록 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ccd2-152">By default, _EnableP2PFileTransfer_ is enabled on the organization's global policy.</span></span> <span data-ttu-id="9ccd2-153">이 파일을 만든 후에는 사용자에 게 _BposSAllModality_ 정책이 할당 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9ccd2-153">When it was created, your users were assigned the _BposSAllModality_ policy.</span></span>
  
<span data-ttu-id="9ccd2-154">조직 내부에 대 한 P2P 전송을 허용 하지만 다른 조직에 대 한 외부 파일 전송을 차단 하는 경우 전역 수준 에서만 변경 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ccd2-154">To allow P2P transfers for inside your organization but block external file transfers to another organization, you just need to change it at a global level.</span></span> <span data-ttu-id="9ccd2-155">이 작업을 수행 하려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ccd2-155">To do that, run:</span></span>
    
  ```PowerShell
  Set-CsExternalUserCommunicationPolicy -EnableP2PFileTransfer $False
  ```

## <a name="disable-p2p-file-transfers-for-a-user"></a><span data-ttu-id="9ccd2-156">사용자에 대해 P2P 파일 전송을 사용 하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="9ccd2-156">Disable P2P file transfers for a user</span></span>

<span data-ttu-id="9ccd2-157">새 정책을 만들고 해당 사용자에 게 부여 하 여 사용자에 게 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ccd2-157">You can apply this to a user by creating a new policy and granting it to that user.</span></span> <span data-ttu-id="9ccd2-158">이 작업을 수행 하려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ccd2-158">To do that, run:</span></span> 

```powershell
New-CsExternalUserCommunicationPolicy -Identity BlockExternalFT -EnableP2PFileTransfer $False
```

```powershell
Grant-CsExternalUserCommunicationPolicy -PolicyName BlockExternalFT -Identity amosm@contoso.com
```

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="9ccd2-159">Windows PowerShell에 대 한 자세한 정보를 확인 하 고 싶으신가요?</span><span class="sxs-lookup"><span data-stu-id="9ccd2-159">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="9ccd2-160">Windows PowerShell은 사용자 및 허용 되지 않거나 수행할 수 있는 사용자를 관리 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ccd2-160">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="9ccd2-161">Windows PowerShell을 사용 하면 여러 작업을 수행할 때 일상 업무를 단순화할 수 있는 단일 관리 지점을 사용 하 여 Office 365 및 비즈니스용 Skype Online을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ccd2-161">With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="9ccd2-162">Windows PowerShell을 시작 하려면 다음 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9ccd2-162">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="9ccd2-163">Windows PowerShell 및 Lync Online 소개</span><span class="sxs-lookup"><span data-stu-id="9ccd2-163">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="9ccd2-164">Office 365 PowerShell을 사용 해야 하는 이유</span><span class="sxs-lookup"><span data-stu-id="9ccd2-164">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="9ccd2-165">Windows PowerShell에는 한 번에 여러 사용자의 설정을 변경 하는 경우와 같이 Microsoft 365 관리 센터를 사용 하는 경우에만 속도, 단순성, 생산성 등 다양 한 이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ccd2-165">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="9ccd2-166">다음 항목에서 이러한 이점에 대해 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="9ccd2-166">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="9ccd2-167">Windows PowerShell을 사용 하 여 Office 365를 관리 하는 가장 좋은 방법</span><span class="sxs-lookup"><span data-stu-id="9ccd2-167">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="9ccd2-168">Windows PowerShell을 사용 하 여 비즈니스용 Skype Online 관리</span><span class="sxs-lookup"><span data-stu-id="9ccd2-168">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="9ccd2-169">Windows PowerShell을 사용 하 여 일반적인 비즈니스용 Skype Online 관리 작업 수행</span><span class="sxs-lookup"><span data-stu-id="9ccd2-169">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="9ccd2-170">관련 항목</span><span class="sxs-lookup"><span data-stu-id="9ccd2-170">Related topics</span></span>
[<span data-ttu-id="9ccd2-171">사용자 지정 외부 액세스 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="9ccd2-171">Create custom external access policies</span></span>](create-custom-external-access-policies.md)

[<span data-ttu-id="9ccd2-172">조직의 클라이언트 정책 설정</span><span class="sxs-lookup"><span data-stu-id="9ccd2-172">Set up client policies for your organization</span></span>](set-up-client-policies-for-your-organization.md)

[<span data-ttu-id="9ccd2-173">조직에서 회의 정책 설정</span><span class="sxs-lookup"><span data-stu-id="9ccd2-173">Set up conferencing policies in your organization</span></span>](set-up-conferencing-policies-for-your-organization.md)

  
 
