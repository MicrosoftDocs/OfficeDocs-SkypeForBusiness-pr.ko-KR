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
description: 비즈니스용 Skype Online에서는 기존 회의 정책 설정의 일부로 P2P(Point to Point) 파일 전송을 제어할 수 있습니다. 그러나 사용자가 동일한 조직 내에 있는 사용자 또는 다른 조직의 페더링된 사용자에게 파일을 전송하는지 여부에 따라 사용자에 대한 파일 전송을 허용하거나 차단합니다. 아래 단계에 따라 페더러드 조직 또는 파트너와의 P2P 파일 전송을 차단할 수 있습니다.
ms.openlocfilehash: 150fb02daa1dcd7486a5bb495c7fd74f8d4736a1
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814637"
---
# <a name="block-point-to-point-file-transfers"></a><span data-ttu-id="eb772-105">점 대 점 파일 전송 차단</span><span class="sxs-lookup"><span data-stu-id="eb772-105">Block Point-to-Point file transfers</span></span>

<span data-ttu-id="eb772-106">비즈니스용 Skype Online에서는 기존 회의 정책 설정의 일부로 P2P(Point to Point) 파일 전송을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb772-106">In Skype for Business Online, you have ability to control Point-to-Point (P2P) file transfers as part of existing conferencing policy settings.</span></span> <span data-ttu-id="eb772-107">그러나 사용자가 동일한 조직 내에 있는 사용자 또는 다른 조직의 페더링된 사용자에게 파일을 전송하는지 여부에 따라 사용자에 대한 파일 전송을 허용하거나 차단합니다.</span><span class="sxs-lookup"><span data-stu-id="eb772-107">However, this allows or blocks file transfers for users whether or not they are transferring files to a user who is within the same organization or to a federated user from another organization.</span></span> <span data-ttu-id="eb772-108">아래 단계에 따라 페더러드 조직 또는 파트너와의 P2P 파일 전송을 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb772-108">Following the steps below, you can block P2P file transfers with federated organizations or partners.</span></span>
  
 <span data-ttu-id="eb772-109">매우 일반적인 시나리오는 내부 사용자가 P2P 파일 전송을 사용하지만 페더러드 파트너와의 파일 전송을 차단하려는 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="eb772-109">A very common scenario is when you want to allow internal users to use P2P file transfer but block file transfer with federated partners.</span></span> <span data-ttu-id="eb772-110">이 시나리오에서는 다음을 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb772-110">For this scenario, you would need to do:</span></span>
  
- <span data-ttu-id="eb772-111">조직의 사용자에게 P2P 파일 전송이 _활성화된(EnableP2PFileTransfer가_ _True로_ 설정) 회의 정책을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="eb772-111">Assign a conferencing policy with P2P file transfer enabled (_EnableP2PFileTransfer_ set to _True_) to users in your organization.</span></span>
    
- <span data-ttu-id="eb772-112">외부 P2P 파일 _전송(EnableP2PFileTransfer가_ _False로_ 설정)을 차단하도록 설정된 전역 외부 사용자 통신 정책을 만들고 조직의 사용자에게 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="eb772-112">Create a global external user communication policy set to block external P2P file transfers (_EnableP2PFileTransfer_ set to _False_) and assign it to a user in your organization.</span></span> 
    
<span data-ttu-id="eb772-113">이러한 설정에 대한 자세한 내용은 여기에서 찾을 수 [있습니다.](https://technet.microsoft.com/library/mt228132.aspx)</span><span class="sxs-lookup"><span data-stu-id="eb772-113">You can find out more about those settings [here](https://technet.microsoft.com/library/mt228132.aspx).</span></span>
  
<span data-ttu-id="eb772-114">조직 외부의 페더러드 사용자가 정책이 적용된 사용자에게 파일을 보내고자 하면 전송 실패 **오류가** 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="eb772-114">If a federated user outside your organization tries to send a file to a user where the policy has been applied, they will receive a **Transfer Failed** error.</span></span> <span data-ttu-id="eb772-115">사용자가 파일을 보내면 파일 전송이 해제된 **오류가** 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="eb772-115">And if a user tries to send a file, they will receive a **File transfer is turned off** error.</span></span>
  
<span data-ttu-id="eb772-116">이 작업을 진행하려면 사용자가 지원되는 2016 비즈니스용 Skype 앱의 지원되는 버전을 사용하고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb772-116">To make this work, the user must be using a supported version of a 2016 Click-to-Run Skype for Business app that supports it.</span></span> <span data-ttu-id="eb772-117">비즈니스용 Skype 2016 Click-to-Run 클라이언트의 최소 버전은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="eb772-117">The following minimum version of Skype for Business 2016 Click-to-Run client is required:</span></span>
  
|<span data-ttu-id="eb772-118">**유형**</span><span class="sxs-lookup"><span data-stu-id="eb772-118">**Type**</span></span>|<span data-ttu-id="eb772-119">**릴리스 날짜**</span><span class="sxs-lookup"><span data-stu-id="eb772-119">**Release date**</span></span>|<span data-ttu-id="eb772-120">**버전**</span><span class="sxs-lookup"><span data-stu-id="eb772-120">**Version**</span></span>|<span data-ttu-id="eb772-121">**빌드**</span><span class="sxs-lookup"><span data-stu-id="eb772-121">**Build**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="eb772-122">현재 채널의 첫 번째 릴리스</span><span class="sxs-lookup"><span data-stu-id="eb772-122">First Release for Current Channel</span></span>  <br/> |<span data-ttu-id="eb772-123">11/17/2016</span><span class="sxs-lookup"><span data-stu-id="eb772-123">11/17/2016</span></span>  <br/> |<span data-ttu-id="eb772-124">16.0.7571.2006</span><span class="sxs-lookup"><span data-stu-id="eb772-124">16.0.7571.2006</span></span>  <br/> |<span data-ttu-id="eb772-125">버전 1611(빌드 7571.2006)</span><span class="sxs-lookup"><span data-stu-id="eb772-125">Version 1611 (Build 7571.2006)</span></span>  <br/> |
|<span data-ttu-id="eb772-126">현재 채널</span><span class="sxs-lookup"><span data-stu-id="eb772-126">Current Channel</span></span>  <br/> |<span data-ttu-id="eb772-127">12/6/2016</span><span class="sxs-lookup"><span data-stu-id="eb772-127">12/6/2016</span></span>  <br/> |<span data-ttu-id="eb772-128">16.0.7571.2072</span><span class="sxs-lookup"><span data-stu-id="eb772-128">16.0.7571.2072</span></span>  <br/> |<span data-ttu-id="eb772-129">버전 1611(빌드 7571.2072)</span><span class="sxs-lookup"><span data-stu-id="eb772-129">Version 1611 (Build 7571.2072)</span></span>  <br/> |
|<span data-ttu-id="eb772-130">지연 채널</span><span class="sxs-lookup"><span data-stu-id="eb772-130">Deferred Channel</span></span>  <br/> |<span data-ttu-id="eb772-131">2/22/2017</span><span class="sxs-lookup"><span data-stu-id="eb772-131">2/22/2017</span></span>  <br/> |<span data-ttu-id="eb772-132">16.0.7369.2118</span><span class="sxs-lookup"><span data-stu-id="eb772-132">16.0.7369.2118</span></span>  <br/> |<span data-ttu-id="eb772-133">버전 1609(빌드 7369.2118)</span><span class="sxs-lookup"><span data-stu-id="eb772-133">Version 1609 (Build 7369.2118)</span></span>  <br/> |
   
> [!CAUTION]
> <span data-ttu-id="eb772-134">이전 버전의 비즈니스용 Skype Windows 앱 또는 Mac 클라이언트를 사용하는 사용자는 여전히 파일을 전송할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb772-134">Users that are using older versions of Skype for Business Windows apps or Mac clients will still be able to transfer files.</span></span> 
  
## <a name="verify-and-start-windows-powershell"></a><span data-ttu-id="eb772-135">확인 및 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="eb772-135">Verify and start Windows PowerShell</span></span>

- <span data-ttu-id="eb772-136">**버전 3.0 Windows PowerShell 실행 중인지 확인**</span><span class="sxs-lookup"><span data-stu-id="eb772-136">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
    
    1. <span data-ttu-id="eb772-137">버전 3.0 이상을 실행하고 있는지 확인: 시작 메뉴를  >  Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="eb772-137">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
        
    2. <span data-ttu-id="eb772-138">웹 창에 _Get-Host를_ 입력하여 **Windows PowerShell** 확인</span><span class="sxs-lookup"><span data-stu-id="eb772-138">Check the version by typing _Get-Host_ in the **Windows PowerShell** window.</span></span>
        
    3. <span data-ttu-id="eb772-139">버전 3.0 이상이 없는 경우 업데이트를 다운로드하여 설치해야 Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="eb772-139">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell.</span></span> <span data-ttu-id="eb772-140">버전 [Windows Management Framework 4.0으로](https://go.microsoft.com/fwlink/?LinkId=716845) Windows PowerShell 다운로드하고 업데이트하려면 4.0을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="eb772-140">See [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0.</span></span> <span data-ttu-id="eb772-141">메시지가 표시될 때 컴퓨터를 다시 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="eb772-141">Restart your computer when you are prompted.</span></span>
        
    4. <span data-ttu-id="eb772-142">또한 비즈니스용 Skype Online에 연결하는 원격 Windows PowerShell 세션을 만들 수 있는 Teams용 Windows PowerShell 모듈을 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb772-142">You will also need to install the Windows PowerShell module for Teams that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span> 
    
    <span data-ttu-id="eb772-143">자세한 내용은 단일 창에서 모든 [Microsoft 365 또는 Office 365 서비스에 Windows PowerShell 참조합니다.](https://technet.microsoft.com/library/dn568015.aspx)</span><span class="sxs-lookup"><span data-stu-id="eb772-143">If you need to know more, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx).</span></span>
    
- <span data-ttu-id="eb772-144">**세션 Windows PowerShell 시작**</span><span class="sxs-lookup"><span data-stu-id="eb772-144">**Start a Windows PowerShell session**</span></span>
    
    1. <span data-ttu-id="eb772-145">시작 **메뉴에서**  >  **Windows PowerShell.**</span><span class="sxs-lookup"><span data-stu-id="eb772-145">From the **Start Menu** > **Windows PowerShell**.</span></span>
        
    2. <span data-ttu-id="eb772-146">다음 **Windows PowerShell** 실행하여 Microsoft 365 또는 Office 365에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="eb772-146">In the **Windows PowerShell** window, connect to your Microsoft 365 or Office 365 by running:</span></span>
    
        > [!NOTE]
        > <span data-ttu-id="eb772-147">비즈니스용 Skype Online Connector는 현재 최신 Teams PowerShell 모듈의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="eb772-147">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span>
        >
        > <span data-ttu-id="eb772-148">최신 [Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/)공개 릴리스를 사용하는 경우 비즈니스용 Skype Online Connector를 설치할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="eb772-148">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

       ```PowerShell      
        Import-Module -Name MicrosoftTeams
        $credential = Get-Credential
        $session = New-CsOnlineSession -Credential $credential
        Import-PSSession $session
       ```

   <span data-ttu-id="eb772-149">Windows PowerShell 시작에 대한 자세한 내용은 단일 Windows PowerShell 창에서 모든 [Microsoft 365 또는 Office 365](https://technet.microsoft.com/library/dn568015.aspx) 서비스에 연결 또는 [Windows PowerShell.](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="eb772-149">If you want more information about starting Windows PowerShell, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
    
## <a name="disable-p2p-file-transfers-for-your-organization"></a><span data-ttu-id="eb772-150">조직의 P2P 파일 전송 사용 안</span><span class="sxs-lookup"><span data-stu-id="eb772-150">Disable P2P file transfers for your organization</span></span>

<span data-ttu-id="eb772-151">기본적으로 _EnableP2PFileTransfer는_ 조직의 전역 정책에서 사용하도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="eb772-151">By default, _EnableP2PFileTransfer_ is enabled on the organization's global policy.</span></span> <span data-ttu-id="eb772-152">만들 때 사용자에게 _BposSAllModality 정책이 할당되었습니다._</span><span class="sxs-lookup"><span data-stu-id="eb772-152">When it was created, your users were assigned the _BposSAllModality_ policy.</span></span>
  
<span data-ttu-id="eb772-153">조직 내부에서 P2P 전송을 허용하지만 다른 조직으로의 외부 파일 전송을 차단하려면 전역 수준에서 변경하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="eb772-153">To allow P2P transfers for inside your organization but block external file transfers to another organization, you just need to change it at a global level.</span></span> <span data-ttu-id="eb772-154">이를 위해 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="eb772-154">To do that, run:</span></span>
    
  ```PowerShell
  Set-CsExternalUserCommunicationPolicy -EnableP2PFileTransfer $False
  ```

## <a name="disable-p2p-file-transfers-for-a-user"></a><span data-ttu-id="eb772-155">사용자에 대한 P2P 파일 전송 사용 안 하도록 설정</span><span class="sxs-lookup"><span data-stu-id="eb772-155">Disable P2P file transfers for a user</span></span>

<span data-ttu-id="eb772-156">새 정책을 만들고 해당 사용자에게 부여하여 사용자에게 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb772-156">You can apply this to a user by creating a new policy and granting it to that user.</span></span> <span data-ttu-id="eb772-157">이를 위해 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="eb772-157">To do that, run:</span></span> 

```powershell
New-CsExternalUserCommunicationPolicy -Identity BlockExternalFT -EnableP2PFileTransfer $False
```

```powershell
Grant-CsExternalUserCommunicationPolicy -PolicyName BlockExternalFT -Identity amosm@contoso.com
```

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="eb772-158">자세한 내용은 Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="eb772-158">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="eb772-159">Windows PowerShell 관리는 사용자 및 사용자가 허용되거나 허용되지 않는 작업을 관리하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="eb772-159">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="eb772-160">이 Windows PowerShell 여러 작업을 수행할 때 일상적인 작업을 간소화할 수 있는 단일 관리 지점을 사용하여 Microsoft 365 또는 Office 365 및 비즈니스용 Skype Online을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb772-160">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="eb772-161">다음 항목을 Windows PowerShell 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="eb772-161">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="eb772-162">Windows PowerShell 및 Lync Online 소개</span><span class="sxs-lookup"><span data-stu-id="eb772-162">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="eb772-163">Microsoft 365 또는 Office 365 PowerShell을 사용하는 이유</span><span class="sxs-lookup"><span data-stu-id="eb772-163">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="eb772-164">Windows PowerShell Microsoft 365 관리 센터를 사용하는 경우와 같이 여러 사용자에 대해 한 번씩 설정을 변경하는 경우와 같이 속도, 단순성 및 생산성에 많은 이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb772-164">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="eb772-165">다음 항목에서 이러한 이점에 대해 자세히 배워야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb772-165">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="eb772-166">Microsoft 365 또는 Office 365를 관리하는 가장 좋은 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="eb772-166">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="eb772-167">비즈니스 Windows PowerShell 사용하여 비즈니스용 Skype Online 관리</span><span class="sxs-lookup"><span data-stu-id="eb772-167">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="eb772-168">비즈니스용 Windows PowerShell Skype Online 관리 작업을 수행하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb772-168">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="eb772-169">관련 항목</span><span class="sxs-lookup"><span data-stu-id="eb772-169">Related topics</span></span>
[<span data-ttu-id="eb772-170">사용자 지정 외부 액세스 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="eb772-170">Create custom external access policies</span></span>](create-custom-external-access-policies.md)

[<span data-ttu-id="eb772-171">조직의 클라이언트 정책 설정</span><span class="sxs-lookup"><span data-stu-id="eb772-171">Set up client policies for your organization</span></span>](set-up-client-policies-for-your-organization.md)

[<span data-ttu-id="eb772-172">조직에서 회의 정책 설정</span><span class="sxs-lookup"><span data-stu-id="eb772-172">Set up conferencing policies in your organization</span></span>](set-up-conferencing-policies-for-your-organization.md)

  
 
