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
f1.keywords:
- NOCSH
ms.custom:
- Setup
description: 비즈니스용 Skype Online을 사용하면 추가 외부 액세스 정책을 만들 수 있습니다. 여러 조합을 사용할 수 있는 클라이언트 또는 회의 정책과 달리, 대부분의 시나리오를 다를 수 있는 세 가지 미리 정의된 외부 액세스 정책이 있습니다.
ms.openlocfilehash: 9ec8fbe2e2d1a0d0882a0115bb201021fbbc1a35
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814197"
---
# <a name="create-custom-external-access-policies"></a><span data-ttu-id="ab7c2-104">사용자 지정 외부 액세스 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="ab7c2-104">Create custom external access policies</span></span>

<span data-ttu-id="ab7c2-105">비즈니스용 Skype Online을 사용하면 추가 외부 액세스 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab7c2-105">Skype for Business Online allows you to create additional external access policies.</span></span> <span data-ttu-id="ab7c2-106">여러 조합을 사용할 수 있는 클라이언트 또는 회의 정책과 달리, 대부분의 시나리오를 다를 수 있는 세 가지 미리 정의된 외부 액세스 정책이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab7c2-106">Unlike client or conferencing policies, where you can have multiple combinations, there are three predefined external access policies that can cover most of the scenarios.</span></span> <span data-ttu-id="ab7c2-107">다음은</span><span class="sxs-lookup"><span data-stu-id="ab7c2-107">These are:</span></span>
  
- <span data-ttu-id="ab7c2-108">페더레드 또는 Skype 소비자 액세스 _없음(Tag:NoFederationAndPIC)_</span><span class="sxs-lookup"><span data-stu-id="ab7c2-108">No Federated or Skype Consumer Access (_Tag:NoFederationAndPIC_ )</span></span>
    
- <span data-ttu-id="ab7c2-109">페더리된 액세스 _전용(Tag:FederationOnly)_</span><span class="sxs-lookup"><span data-stu-id="ab7c2-109">Federated Access Only (_Tag:FederationOnly_ )</span></span>
    
- <span data-ttu-id="ab7c2-110">페더레이드 및 소비자 _액세스(FederationAndPICDefault)_</span><span class="sxs-lookup"><span data-stu-id="ab7c2-110">Federated and Consumer Access (_FederationAndPICDefault_)</span></span>
    
<span data-ttu-id="ab7c2-111">사용자 지정 외부 정책을 사용하면 위의 설정에서 다루지 않는 추가 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab7c2-111">Custom external policies allow you to create additional polices that aren't covered by the settings above.</span></span> <span data-ttu-id="ab7c2-112">정책을 만들 때 필요한 모든 매개 변수를 설정해야 하며 나중에 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ab7c2-112">When the policy was created, you would be required to set all required parameters and you couldn't alter them later.</span></span> <span data-ttu-id="ab7c2-113">새 사용자 지정 정책을 만들면 Skype 소비자 액세스 또는 공용 클라우드 오디오/비디오를 사용하지 않도록 설정하는 정책과 같은 기능을 제어할 수 있습니다. 이 기능은 미리 정의되어 있는 설정에서 다루지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ab7c2-113">Creating new custom policies allow you to control features such as Skype consumer access or a policy to disable public cloud audio/video, which is something that wasn't covered with predefined settings.</span></span> <span data-ttu-id="ab7c2-114">사용자 지정 외부 액세스 정책은 클라이언트, 이동성 및 회의 정책과 동일한 구문을 따르고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab7c2-114">Custom external access policies follow the same syntax as client, mobility, and conferencing policies.</span></span> <span data-ttu-id="ab7c2-115">이러한 설정에 대한 자세한 내용은 여기에서 찾을 수 [있습니다.](https://technet.microsoft.com/library/mt228132.aspx)</span><span class="sxs-lookup"><span data-stu-id="ab7c2-115">You can find out more about those settings [here](https://technet.microsoft.com/library/mt228132.aspx).</span></span>
  
<span data-ttu-id="ab7c2-116">이 작업을 진행하려면 사용자가 지원되는 2016 비즈니스용 Skype 앱의 지원되는 버전을 사용하고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab7c2-116">To make this work, the user must be using a supported version of 2016 Click-to-Run Skype for Business app that supports it.</span></span> <span data-ttu-id="ab7c2-117">비즈니스용 Skype 2016 Click-to-Run 클라이언트의 최소 버전은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ab7c2-117">The following minimum version of Skype for Business 2016 Click-to-Run client is required:</span></span>
  
|<span data-ttu-id="ab7c2-118">**유형**</span><span class="sxs-lookup"><span data-stu-id="ab7c2-118">**Type**</span></span>|<span data-ttu-id="ab7c2-119">**릴리스 날짜**</span><span class="sxs-lookup"><span data-stu-id="ab7c2-119">**Release date**</span></span>|<span data-ttu-id="ab7c2-120">**버전**</span><span class="sxs-lookup"><span data-stu-id="ab7c2-120">**Version**</span></span>|<span data-ttu-id="ab7c2-121">**빌드**</span><span class="sxs-lookup"><span data-stu-id="ab7c2-121">**Build**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="ab7c2-122">현재 채널의 첫 번째 릴리스</span><span class="sxs-lookup"><span data-stu-id="ab7c2-122">First Release for Current Channel</span></span>  <br/> |<span data-ttu-id="ab7c2-123">11/17/2016</span><span class="sxs-lookup"><span data-stu-id="ab7c2-123">11/17/2016</span></span>  <br/> |<span data-ttu-id="ab7c2-124">16.0.7571.2006</span><span class="sxs-lookup"><span data-stu-id="ab7c2-124">16.0.7571.2006</span></span>  <br/> |<span data-ttu-id="ab7c2-125">버전 1611(빌드 7571.2006)</span><span class="sxs-lookup"><span data-stu-id="ab7c2-125">Version 1611 (Build 7571.2006)</span></span>  <br/> |
|<span data-ttu-id="ab7c2-126">현재 채널</span><span class="sxs-lookup"><span data-stu-id="ab7c2-126">Current Channel</span></span>  <br/> |<span data-ttu-id="ab7c2-127">12/6/2016</span><span class="sxs-lookup"><span data-stu-id="ab7c2-127">12/6/2016</span></span>  <br/> |<span data-ttu-id="ab7c2-128">16.0.7571.2072</span><span class="sxs-lookup"><span data-stu-id="ab7c2-128">16.0.7571.2072</span></span>  <br/> |<span data-ttu-id="ab7c2-129">버전 1611(빌드 7571.2072)</span><span class="sxs-lookup"><span data-stu-id="ab7c2-129">Version 1611 (Build 7571.2072)</span></span>  <br/> |
|<span data-ttu-id="ab7c2-130">지연 채널</span><span class="sxs-lookup"><span data-stu-id="ab7c2-130">Deferred Channel</span></span>  <br/> |<span data-ttu-id="ab7c2-131">2/22/2017</span><span class="sxs-lookup"><span data-stu-id="ab7c2-131">2/22/2017</span></span>  <br/> |<span data-ttu-id="ab7c2-132">16.0.7369.2118</span><span class="sxs-lookup"><span data-stu-id="ab7c2-132">16.0.7369.2118</span></span>  <br/> |<span data-ttu-id="ab7c2-133">버전 1609(빌드 7369.2118)</span><span class="sxs-lookup"><span data-stu-id="ab7c2-133">Version 1609 (Build 7369.2118)</span></span>  <br/> |
   
> [!CAUTION]
> <span data-ttu-id="ab7c2-134">이전 버전의 비즈니스용 Skype Windows 앱 또는 Mac 클라이언트를 사용하는 사용자는 여전히 파일을 전송할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab7c2-134">Users who are using older versions of Skype for Business Windows apps or Mac clients will still be able to transfer files.</span></span> 
  
## <a name="verify-and-start-windows-powershell"></a><span data-ttu-id="ab7c2-135">확인 및 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ab7c2-135">Verify and start Windows PowerShell</span></span>

- <span data-ttu-id="ab7c2-136">**버전 3.0 Windows PowerShell 실행 중인지 확인**</span><span class="sxs-lookup"><span data-stu-id="ab7c2-136">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
    
1. <span data-ttu-id="ab7c2-137">버전 3.0 이상을 실행하고 있는지 확인: 시작 메뉴를  >  Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ab7c2-137">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="ab7c2-138">웹 창에  _Get-Host를_ 입력하여 **Windows PowerShell** 확인</span><span class="sxs-lookup"><span data-stu-id="ab7c2-138">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="ab7c2-139">버전 3.0 이상이 없는 경우 업데이트를 다운로드하여 설치해야 Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ab7c2-139">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell.</span></span> <span data-ttu-id="ab7c2-140">버전 [Windows Management Framework 4.0으로](https://www.microsoft.com/download/details.aspx?id=40855) Windows PowerShell 다운로드하고 업데이트하려면 4.0을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="ab7c2-140">See [Windows Management Framework 4.0](https://www.microsoft.com/download/details.aspx?id=40855) to download and update Windows PowerShell to version 4.0.</span></span> <span data-ttu-id="ab7c2-141">메시지가 표시될 때 컴퓨터를 다시 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="ab7c2-141">Restart your computer when you are prompted.</span></span>
    
4. <span data-ttu-id="ab7c2-142">또한 비즈니스용 Skype Online에 연결하는 원격 Windows PowerShell 세션을 만들 수 있는 Teams용 Windows PowerShell 모듈을 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab7c2-142">You will also need to install the Windows PowerShell module for Teams that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span>
    
    <span data-ttu-id="ab7c2-143">자세한 내용은 단일 창에서 모든 [Microsoft 365 또는 Office 365 서비스에 Windows PowerShell 참조합니다.](https://technet.microsoft.com/library/dn568015.aspx)</span><span class="sxs-lookup"><span data-stu-id="ab7c2-143">If you need to know more, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx).</span></span>
    
- <span data-ttu-id="ab7c2-144">**세션 Windows PowerShell 시작**</span><span class="sxs-lookup"><span data-stu-id="ab7c2-144">**Start a Windows PowerShell session**</span></span>
    
1. <span data-ttu-id="ab7c2-145">시작 **메뉴에서**  >  **Windows PowerShell.**</span><span class="sxs-lookup"><span data-stu-id="ab7c2-145">From the **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="ab7c2-146">다음 **Windows PowerShell** 실행하여 Microsoft 365 또는 Office 365에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="ab7c2-146">In the **Windows PowerShell** window, connect to your Microsoft 365 or Office 365 by running:</span></span>
    
  > [!NOTE]
  > <span data-ttu-id="ab7c2-147">비즈니스용 Skype Online 커넥터는 현재 최신 Teams PowerShell 모듈의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="ab7c2-147">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span>
  >
  > <span data-ttu-id="ab7c2-148">최신 [Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/)공개 릴리스를 사용하는 경우 비즈니스용 Skype Online Connector를 설치할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ab7c2-148">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business  Online Connector.</span></span>

   ```PowerShell      
    Import-Module -Name MicrosoftTeams
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
   ```

   <span data-ttu-id="ab7c2-149">Windows PowerShell 시작에 대한 자세한 내용은 단일 Windows PowerShell 창에서 모든 [Microsoft 365 또는 Office 365](https://technet.microsoft.com/library/dn568015.aspx) 서비스에 연결 또는 [Windows PowerShell.](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="ab7c2-149">If you want more information about starting Windows PowerShell, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
    
## <a name="create-a-custom-external-access-policy-for-a-user"></a><span data-ttu-id="ab7c2-150">사용자에 대한 사용자 지정 외부 액세스 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="ab7c2-150">Create a custom external access policy for a user</span></span>

<span data-ttu-id="ab7c2-151">이를 위해 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="ab7c2-151">To do this, run:</span></span>
  
 
```powershell
New-CsExternalAccessPolicy -Identity BlockSkypeVideo -EnablePublicCloudAccess $True -EnablePublicCloudAudioVideoAccess $False -EnableFederationAccess $True -EnableOutsideAccess $True
```


```powershell
Grant-CsExternalAccessPolicy -PolicyName BlockSkypeVideo -Identity amosm@contoso.com
```

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="ab7c2-152">자세한 내용은 Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="ab7c2-152">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="ab7c2-153">Windows PowerShell 관리는 사용자 및 사용자가 허용되거나 허용되지 않는 작업을 관리하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ab7c2-153">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="ab7c2-154">이 Windows PowerShell 여러 작업을 수행할 때 일상적인 작업을 간소화할 수 있는 단일 관리 지점을 사용하여 Microsoft 365 또는 Office 365 및 비즈니스용 Skype Online을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab7c2-154">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="ab7c2-155">다음 항목을 Windows PowerShell 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ab7c2-155">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="ab7c2-156">Windows PowerShell 및 Lync Online 소개</span><span class="sxs-lookup"><span data-stu-id="ab7c2-156">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="ab7c2-157">Microsoft 365 또는 Office 365 PowerShell을 사용하는 이유</span><span class="sxs-lookup"><span data-stu-id="ab7c2-157">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="ab7c2-158">Windows PowerShell Microsoft 365 관리 센터를 사용하는 경우와 같이 여러 사용자에 대해 한 번씩 설정을 변경하는 경우와 같이 속도, 단순성 및 생산성에 많은 이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab7c2-158">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="ab7c2-159">다음 항목에서 이러한 이점에 대해 자세히 배워야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab7c2-159">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="ab7c2-160">Microsoft 365 또는 Office 365를 관리하는 가장 좋은 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ab7c2-160">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="ab7c2-161">비즈니스 Windows PowerShell 사용하여 비즈니스용 Skype Online 관리</span><span class="sxs-lookup"><span data-stu-id="ab7c2-161">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="ab7c2-162">비즈니스용 Windows PowerShell Skype Online 관리 작업을 수행하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab7c2-162">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="ab7c2-163">관련 항목</span><span class="sxs-lookup"><span data-stu-id="ab7c2-163">Related topics</span></span>
[<span data-ttu-id="ab7c2-164">지점 및 지점 및 지점 파일 전송 차단</span><span class="sxs-lookup"><span data-stu-id="ab7c2-164">Block point-to-point file transfers</span></span>](block-point-to-point-file-transfers.md)

[<span data-ttu-id="ab7c2-165">조직의 클라이언트 정책 설정</span><span class="sxs-lookup"><span data-stu-id="ab7c2-165">Set up client policies for your organization</span></span>](set-up-client-policies-for-your-organization.md)

[<span data-ttu-id="ab7c2-166">조직에서 회의 정책 설정</span><span class="sxs-lookup"><span data-stu-id="ab7c2-166">Set up conferencing policies in your organization</span></span>](set-up-conferencing-policies-for-your-organization.md)

  
 
