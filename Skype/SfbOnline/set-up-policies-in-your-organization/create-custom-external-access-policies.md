---
title: 사용자 지정 외부 액세스 정책 만들기
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 89cbd278-5480-473c-8cd9-04e07e5f9e0b
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
description: 비즈니스용 Skype Online을 통해 추가 외부 액세스 정책을 만들 수 있습니다. 여러 조합을 사용할 수 있는 클라이언트나 회의 정책과는 달리, 미리 정의 된 세 가지 외부 액세스 정책이 있으며 대부분의 시나리오를 포함할 수 있습니다.
ms.openlocfilehash: 7f3edac77af8d9948ef7118c0f94b1ec9c3ae6c1
ms.sourcegitcommit: 4c041e8a7c39bd6517605ed7fc9aab18cf466596
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/18/2019
ms.locfileid: "37642146"
---
# <a name="create-custom-external-access-policies"></a><span data-ttu-id="0e7d7-104">사용자 지정 외부 액세스 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="0e7d7-104">Create custom external access policies</span></span>

<span data-ttu-id="0e7d7-105">비즈니스용 Skype Online을 통해 추가 외부 액세스 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e7d7-105">Skype for Business Online allows you to create additional external access policies.</span></span> <span data-ttu-id="0e7d7-106">여러 조합을 사용할 수 있는 클라이언트나 회의 정책과는 달리, 미리 정의 된 세 가지 외부 액세스 정책이 있으며 대부분의 시나리오를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e7d7-106">Unlike client or conferencing policies, where you can have multiple combinations, there are three predefined external access policies that can cover most of the scenarios.</span></span> <span data-ttu-id="0e7d7-107">다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="0e7d7-107">These are:</span></span>
  
- <span data-ttu-id="0e7d7-108">페더레이션 또는 Skype 소비자 액세스 없음 (_태그: NoFederationAndPIC_ )</span><span class="sxs-lookup"><span data-stu-id="0e7d7-108">No Federated or Skype Consumer Access (_Tag:NoFederationAndPIC_ )</span></span>
    
- <span data-ttu-id="0e7d7-109">페더레이션 액세스만 (_Tag: FederationOnly_ )</span><span class="sxs-lookup"><span data-stu-id="0e7d7-109">Federated Access Only (_Tag:FederationOnly_ )</span></span>
    
- <span data-ttu-id="0e7d7-110">페더레이션 및 소비자 액세스 (_FederationAndPICDefault_)</span><span class="sxs-lookup"><span data-stu-id="0e7d7-110">Federated and Consumer Access (_FederationAndPICDefault_)</span></span>
    
<span data-ttu-id="0e7d7-111">사용자 지정 외부 정책을 사용 하 여 위의 설정에서 다루지 않는 추가 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e7d7-111">Custom external policies allow you to create additional polices that aren't covered by the settings above.</span></span> <span data-ttu-id="0e7d7-112">정책을 만들면 필요한 모든 매개 변수를 설정 해야 하며 나중에 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0e7d7-112">When the policy was created, you would be required to set all required parameters and you couldn't alter them later.</span></span> <span data-ttu-id="0e7d7-113">새 사용자 지정 정책을 만들면 Skype 소비자 액세스 또는 정책 등의 기능을 제어 하 여 미리 정의 된 설정으로 검사 되지 않은 공용 클라우드 오디오/비디오를 사용 하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e7d7-113">Creating new custom policies allow you to control features such as Skype consumer access or a policy to disable public cloud audio/video, which is something that wasn't covered with predefined settings.</span></span> <span data-ttu-id="0e7d7-114">사용자 지정 외부 액세스 정책은 클라이언트, 이동성, 회의 정책과 동일한 구문을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="0e7d7-114">Custom external access policies follow the same syntax as client, mobility, and conferencing policies.</span></span> <span data-ttu-id="0e7d7-115">이러한 설정에 대 한 자세한 내용은 [여기](https://technet.microsoft.com/en-us/library/mt228132.aspx)에서 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e7d7-115">You can find out more about those settings [here](https://technet.microsoft.com/en-us/library/mt228132.aspx).</span></span>
  
<span data-ttu-id="0e7d7-116">이 작업을 수행 하려면 사용자가 지원 되는 버전의 2016 간편 실행 비즈니스용 Skype 앱을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0e7d7-116">To make this work, the user must be using a supported version of 2016 Click-to-Run Skype for Business app that supports it.</span></span> <span data-ttu-id="0e7d7-117">다음의 최소 버전의 비즈니스용 Skype 2016 간편 실행 클라이언트를 선택 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0e7d7-117">The following minimum version of Skype for Business 2016 Click-to-Run client is required:</span></span>
  
|<span data-ttu-id="0e7d7-118">**유형**</span><span class="sxs-lookup"><span data-stu-id="0e7d7-118">**Type**</span></span>|<span data-ttu-id="0e7d7-119">**릴리스 날짜**</span><span class="sxs-lookup"><span data-stu-id="0e7d7-119">**Release date**</span></span>|<span data-ttu-id="0e7d7-120">**버전**</span><span class="sxs-lookup"><span data-stu-id="0e7d7-120">**Version**</span></span>|<span data-ttu-id="0e7d7-121">**빌드한**</span><span class="sxs-lookup"><span data-stu-id="0e7d7-121">**Build**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="0e7d7-122">현재 채널의 첫 번째 릴리스</span><span class="sxs-lookup"><span data-stu-id="0e7d7-122">First Release for Current Channel</span></span>  <br/> |<span data-ttu-id="0e7d7-123">11/17/2016</span><span class="sxs-lookup"><span data-stu-id="0e7d7-123">11/17/2016</span></span>  <br/> |<span data-ttu-id="0e7d7-124">16.0.7571.2006</span><span class="sxs-lookup"><span data-stu-id="0e7d7-124">16.0.7571.2006</span></span>  <br/> |<span data-ttu-id="0e7d7-125">버전 1611 (빌드 7571.2006)</span><span class="sxs-lookup"><span data-stu-id="0e7d7-125">Version 1611 (Build 7571.2006)</span></span>  <br/> |
|<span data-ttu-id="0e7d7-126">현재 채널</span><span class="sxs-lookup"><span data-stu-id="0e7d7-126">Current Channel</span></span>  <br/> |<span data-ttu-id="0e7d7-127">12/6/2016</span><span class="sxs-lookup"><span data-stu-id="0e7d7-127">12/6/2016</span></span>  <br/> |<span data-ttu-id="0e7d7-128">16.0.7571.2072</span><span class="sxs-lookup"><span data-stu-id="0e7d7-128">16.0.7571.2072</span></span>  <br/> |<span data-ttu-id="0e7d7-129">버전 1611 (빌드 7571.2072)</span><span class="sxs-lookup"><span data-stu-id="0e7d7-129">Version 1611 (Build 7571.2072)</span></span>  <br/> |
|<span data-ttu-id="0e7d7-130">지연 채널</span><span class="sxs-lookup"><span data-stu-id="0e7d7-130">Deferred Channel</span></span>  <br/> |<span data-ttu-id="0e7d7-131">2/22/2017</span><span class="sxs-lookup"><span data-stu-id="0e7d7-131">2/22/2017</span></span>  <br/> |<span data-ttu-id="0e7d7-132">16.0.7369.2118</span><span class="sxs-lookup"><span data-stu-id="0e7d7-132">16.0.7369.2118</span></span>  <br/> |<span data-ttu-id="0e7d7-133">버전 1609 (빌드 7369.2118)</span><span class="sxs-lookup"><span data-stu-id="0e7d7-133">Version 1609 (Build 7369.2118)</span></span>  <br/> |
   
> [!CAUTION]
> <span data-ttu-id="0e7d7-134">이전 버전의 비즈니스용 Skype Windows 앱 또는 Mac 클라이언트를 사용 하는 사용자는 계속 파일을 전송할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e7d7-134">Users who are using older versions of Skype for Business Windows apps or Mac clients will still be able to transfer files.</span></span> 
  
## <a name="verify-and-start-windows-powershell"></a><span data-ttu-id="0e7d7-135">Windows PowerShell 확인 및 시작</span><span class="sxs-lookup"><span data-stu-id="0e7d7-135">Verify and start Windows PowerShell</span></span>

- <span data-ttu-id="0e7d7-136">**Windows PowerShell 버전 3.0 이상을 실행 하 고 있는지 확인**</span><span class="sxs-lookup"><span data-stu-id="0e7d7-136">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
    
1. <span data-ttu-id="0e7d7-137">버전 3.0 이상을 실행 하 고 있는지 확인 하려면 **시작 메뉴** > 에서**Windows PowerShell**을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="0e7d7-137">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="0e7d7-138">**Windows PowerShell** 창에서 _Get-Host_ 를 입력 하 여 버전을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="0e7d7-138">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="0e7d7-139">버전 3.0 이상이 없는 경우 Windows PowerShell 업데이트를 다운로드 하 여 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0e7d7-139">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell.</span></span> <span data-ttu-id="0e7d7-140">Windows [Management 프레임 워크 4.0](https://www.microsoft.com/en-us/download/details.aspx?id=40855) 를 참조 하 여 windows PowerShell을 버전 4.0로 다운로드 하 고 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="0e7d7-140">See [Windows Management Framework 4.0](https://www.microsoft.com/en-us/download/details.aspx?id=40855) to download and update Windows PowerShell to version 4.0.</span></span> <span data-ttu-id="0e7d7-141">메시지가 표시 되 면 컴퓨터를 다시 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="0e7d7-141">Restart your computer when you are prompted.</span></span>
    
4. <span data-ttu-id="0e7d7-142">비즈니스용 skype Online에 연결 되는 원격 Windows PowerShell 세션을 만들 수 있는 비즈니스용 Skype Online 용 Windows PowerShell 모듈을 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0e7d7-142">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span> <span data-ttu-id="0e7d7-143">이 모듈은 64 비트 컴퓨터 에서만 지원 되며 비즈니스용 [Skype Online 용 Windows PowerShell 모듈](https://go.microsoft.com/fwlink/?LinkId=294688)의 Microsoft 다운로드 센터에서 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e7d7-143">This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688).</span></span> <span data-ttu-id="0e7d7-144">메시지가 표시 되 면 컴퓨터를 다시 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="0e7d7-144">Restart your computer if you are prompted.</span></span>
    
    <span data-ttu-id="0e7d7-145">자세한 정보를 알고 싶은 경우 [모든 Office 365 서비스에 단일 Windows PowerShell 창으로 연결](https://technet.microsoft.com/EN-US/library/dn568015.aspx)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0e7d7-145">If you need to know more, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span></span>
    
- <span data-ttu-id="0e7d7-146">**Windows PowerShell 세션 시작**</span><span class="sxs-lookup"><span data-stu-id="0e7d7-146">**Start a Windows PowerShell session**</span></span>
    
1. <span data-ttu-id="0e7d7-147">**시작 메뉴** > 에서**Windows PowerShell**을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="0e7d7-147">From the **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="0e7d7-148">**Windows PowerShell** 창에서 다음을 실행 하 여 Office 365 조직에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="0e7d7-148">In the **Windows PowerShell** window, connect to your Office 365 organization by running:</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="0e7d7-149">비즈니스용 Skype Online Windows PowerShell 모듈을 처음 사용 하는 경우에만 **Import-Module** 명령을 실행 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0e7d7-149">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>

   ```      
    Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
   ```

   <span data-ttu-id="0e7d7-150">Windows PowerShell을 시작 하는 방법에 대 한 자세한 내용은 [단일 Windows powershell 창에서 모든 Office 365 서비스에 연결](https://technet.microsoft.com/EN-US/library/dn568015.aspx) 또는 [Windows Powershell 용 컴퓨터 설정을](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0e7d7-150">If you want more information about starting Windows PowerShell, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
    
## <a name="create-a-custom-external-access-policy-for-a-user"></a><span data-ttu-id="0e7d7-151">사용자를 위한 사용자 지정 외부 액세스 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="0e7d7-151">Create a custom external access policy for a user</span></span>

<span data-ttu-id="0e7d7-152">이 작업을 수행 하려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="0e7d7-152">To do this, run:</span></span>
  
> 
>   ```
>   New-CsExternalAccessPolicy -Identity BlockSkypeVideo -EnablePublicCloudAccess $True -EnablePublicCloudAudioVideoAccess $False -EnableFederationAccess $True -EnableOutsideAccess $True
>   ```
> 
> 
>   ```
>   Grant-CsExternalAccessPolicy -PolicyName BlockSkypeVideo -Identity amosm@contoso.com
>   ```

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="0e7d7-153">Windows PowerShell에 대 한 자세한 정보를 확인 하 고 싶으신가요?</span><span class="sxs-lookup"><span data-stu-id="0e7d7-153">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="0e7d7-154">Windows PowerShell은 사용자 및 허용 되지 않거나 수행할 수 있는 사용자를 관리 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="0e7d7-154">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="0e7d7-155">Windows PowerShell을 사용 하면 여러 작업을 수행할 때 일상 업무를 단순화할 수 있는 단일 관리 지점을 사용 하 여 Office 365 및 비즈니스용 Skype Online을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e7d7-155">With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="0e7d7-156">Windows PowerShell을 시작 하려면 다음 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0e7d7-156">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="0e7d7-157">Windows PowerShell 및 Lync Online 소개</span><span class="sxs-lookup"><span data-stu-id="0e7d7-157">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="0e7d7-158">Office 365 PowerShell을 사용 해야 하는 이유</span><span class="sxs-lookup"><span data-stu-id="0e7d7-158">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="0e7d7-159">Windows PowerShell에는 한 번에 여러 사용자의 설정을 변경 하는 경우와 같이 Microsoft 365 관리 센터를 사용 하는 경우에만 속도, 단순성, 생산성 등 다양 한 이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e7d7-159">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="0e7d7-160">다음 항목에서 이러한 이점에 대해 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="0e7d7-160">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="0e7d7-161">Windows PowerShell을 사용 하 여 Office 365를 관리 하는 가장 좋은 방법</span><span class="sxs-lookup"><span data-stu-id="0e7d7-161">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="0e7d7-162">Windows PowerShell을 사용 하 여 비즈니스용 Skype Online 관리</span><span class="sxs-lookup"><span data-stu-id="0e7d7-162">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="0e7d7-163">Windows PowerShell을 사용 하 여 일반적인 비즈니스용 Skype Online 관리 작업 수행</span><span class="sxs-lookup"><span data-stu-id="0e7d7-163">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="0e7d7-164">관련 항목</span><span class="sxs-lookup"><span data-stu-id="0e7d7-164">Related topics</span></span>
[<span data-ttu-id="0e7d7-165">점 대 점 파일 전송 차단</span><span class="sxs-lookup"><span data-stu-id="0e7d7-165">Block point-to-point file transfers</span></span>](block-point-to-point-file-transfers.md)

[<span data-ttu-id="0e7d7-166">조직의 클라이언트 정책 설정</span><span class="sxs-lookup"><span data-stu-id="0e7d7-166">Set up client policies for your organization</span></span>](set-up-client-policies-for-your-organization.md)

[<span data-ttu-id="0e7d7-167">조직에서 회의 정책 설정</span><span class="sxs-lookup"><span data-stu-id="0e7d7-167">Set up conferencing policies in your organization</span></span>](set-up-conferencing-policies-for-your-organization.md)

  
 
