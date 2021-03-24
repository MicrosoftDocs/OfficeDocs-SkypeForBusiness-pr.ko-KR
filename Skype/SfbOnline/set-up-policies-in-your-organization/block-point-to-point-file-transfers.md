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
description: 비즈니스용 Skype Online에서는 기존 회의 정책 설정의 일부로 P2P(Point-to-Point) 파일 전송을 제어할 수 있습니다. 그러나 이 기능을 사용하면 파일을 동일한 조직 내에 있는 사용자 또는 다른 조직의 페더리드 사용자로 파일을 전송하는지 여부에 따라 사용자에 대한 파일 전송을 허용하거나 차단할 수 있습니다. 아래 단계에 따라 페더리드 조직 또는 파트너를 사용하여 P2P 파일 전송을 차단할 수 있습니다.
ms.openlocfilehash: e2a0bb2f250f89433c09566197df7a56efa7f64f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51100624"
---
# <a name="block-point-to-point-file-transfers"></a><span data-ttu-id="cbc4f-105">점 대 점 파일 전송 차단</span><span class="sxs-lookup"><span data-stu-id="cbc4f-105">Block Point-to-Point file transfers</span></span>

<span data-ttu-id="cbc4f-106">비즈니스용 Skype Online에서는 기존 회의 정책 설정의 일부로 P2P(Point-to-Point) 파일 전송을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cbc4f-106">In Skype for Business Online, you have ability to control Point-to-Point (P2P) file transfers as part of existing conferencing policy settings.</span></span> <span data-ttu-id="cbc4f-107">그러나 이 기능을 사용하면 파일을 동일한 조직 내에 있는 사용자 또는 다른 조직의 페더리드 사용자로 파일을 전송하는지 여부에 따라 사용자에 대한 파일 전송을 허용하거나 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cbc4f-107">However, this allows or blocks file transfers for users whether or not they are transferring files to a user who is within the same organization or to a federated user from another organization.</span></span> <span data-ttu-id="cbc4f-108">아래 단계에 따라 페더리드 조직 또는 파트너를 사용하여 P2P 파일 전송을 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cbc4f-108">Following the steps below, you can block P2P file transfers with federated organizations or partners.</span></span>
  
 <span data-ttu-id="cbc4f-109">매우 일반적인 시나리오는 내부 사용자가 P2P 파일 전송을 사용할 수 있도록 허용하지만 페더리드 파트너를 사용하여 파일 전송을 차단하려는 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="cbc4f-109">A very common scenario is when you want to allow internal users to use P2P file transfer but block file transfer with federated partners.</span></span> <span data-ttu-id="cbc4f-110">이 시나리오에서는 다음을 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cbc4f-110">For this scenario, you would need to do:</span></span>
  
- <span data-ttu-id="cbc4f-111">P2P 파일 전송을 사용하도록 설정된 회의 정책을 _할당합니다(EnableP2PFileTransfer를_ _True로_ 설정) 조직의 사용자에게 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="cbc4f-111">Assign a conferencing policy with P2P file transfer enabled (_EnableP2PFileTransfer_ set to _True_) to users in your organization.</span></span>
    
- <span data-ttu-id="cbc4f-112">외부 P2P 파일 전송을 차단하도록 글로벌 외부 사용자 통신 정책 집합을 _만들고(EnableP2PFileTransfer를_ _False로_ 설정) 조직 내 사용자에게 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="cbc4f-112">Create a global external user communication policy set to block external P2P file transfers (_EnableP2PFileTransfer_ set to _False_) and assign it to a user in your organization.</span></span> 
    
<span data-ttu-id="cbc4f-113">이러한 설정에 대한 자세한 내용은 여기를 [클릭하세요.](/previous-versions//mt228132(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="cbc4f-113">You can find out more about those settings [here](/previous-versions//mt228132(v=technet.10)).</span></span>
  
<span data-ttu-id="cbc4f-114">조직 외부의 페더리드 사용자가 정책이 적용된 사용자에게 파일을 보내고자 하면 전송 실패 오류가 **발생합니다.**</span><span class="sxs-lookup"><span data-stu-id="cbc4f-114">If a federated user outside your organization tries to send a file to a user where the policy has been applied, they will receive a **Transfer Failed** error.</span></span> <span data-ttu-id="cbc4f-115">사용자가 파일을 보내면 파일 전송이 **꺼져** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cbc4f-115">And if a user tries to send a file, they will receive a **File transfer is turned off** error.</span></span>
  
<span data-ttu-id="cbc4f-116">이 작업을 실행하려면 사용자가 지원되는 2016년 비즈니스용 Skype 앱의 지원되는 버전을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cbc4f-116">To make this work, the user must be using a supported version of a 2016 Click-to-Run Skype for Business app that supports it.</span></span> <span data-ttu-id="cbc4f-117">비즈니스용 Skype 2016 Click-to-Run 클라이언트의 최소 버전이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="cbc4f-117">The following minimum version of Skype for Business 2016 Click-to-Run client is required:</span></span>
  
|<span data-ttu-id="cbc4f-118">**유형**</span><span class="sxs-lookup"><span data-stu-id="cbc4f-118">**Type**</span></span>|<span data-ttu-id="cbc4f-119">**릴리스 날짜**</span><span class="sxs-lookup"><span data-stu-id="cbc4f-119">**Release date**</span></span>|<span data-ttu-id="cbc4f-120">**버전**</span><span class="sxs-lookup"><span data-stu-id="cbc4f-120">**Version**</span></span>|<span data-ttu-id="cbc4f-121">**빌드**</span><span class="sxs-lookup"><span data-stu-id="cbc4f-121">**Build**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="cbc4f-122">현재 채널에 대한 첫 번째 릴리스</span><span class="sxs-lookup"><span data-stu-id="cbc4f-122">First Release for Current Channel</span></span>  <br/> |<span data-ttu-id="cbc4f-123">11/17/2016</span><span class="sxs-lookup"><span data-stu-id="cbc4f-123">11/17/2016</span></span>  <br/> |<span data-ttu-id="cbc4f-124">16.0.7571.2006</span><span class="sxs-lookup"><span data-stu-id="cbc4f-124">16.0.7571.2006</span></span>  <br/> |<span data-ttu-id="cbc4f-125">버전 1611(빌드 7571.2006)</span><span class="sxs-lookup"><span data-stu-id="cbc4f-125">Version 1611 (Build 7571.2006)</span></span>  <br/> |
|<span data-ttu-id="cbc4f-126">현재 채널</span><span class="sxs-lookup"><span data-stu-id="cbc4f-126">Current Channel</span></span>  <br/> |<span data-ttu-id="cbc4f-127">12/6/2016</span><span class="sxs-lookup"><span data-stu-id="cbc4f-127">12/6/2016</span></span>  <br/> |<span data-ttu-id="cbc4f-128">16.0.7571.2072</span><span class="sxs-lookup"><span data-stu-id="cbc4f-128">16.0.7571.2072</span></span>  <br/> |<span data-ttu-id="cbc4f-129">버전 1611(빌드 7571.2072)</span><span class="sxs-lookup"><span data-stu-id="cbc4f-129">Version 1611 (Build 7571.2072)</span></span>  <br/> |
|<span data-ttu-id="cbc4f-130">지연 채널</span><span class="sxs-lookup"><span data-stu-id="cbc4f-130">Deferred Channel</span></span>  <br/> |<span data-ttu-id="cbc4f-131">2/22/2017</span><span class="sxs-lookup"><span data-stu-id="cbc4f-131">2/22/2017</span></span>  <br/> |<span data-ttu-id="cbc4f-132">16.0.7369.2118</span><span class="sxs-lookup"><span data-stu-id="cbc4f-132">16.0.7369.2118</span></span>  <br/> |<span data-ttu-id="cbc4f-133">버전 1609(빌드 7369.2118)</span><span class="sxs-lookup"><span data-stu-id="cbc4f-133">Version 1609 (Build 7369.2118)</span></span>  <br/> |
   
> [!CAUTION]
> <span data-ttu-id="cbc4f-134">이전 버전의 비즈니스용 Skype Windows 앱 또는 Mac 클라이언트를 사용하는 사용자는 여전히 파일을 전송할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cbc4f-134">Users that are using older versions of Skype for Business Windows apps or Mac clients will still be able to transfer files.</span></span> 
  
## <a name="start-windows-powershell"></a><span data-ttu-id="cbc4f-135">시작 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="cbc4f-135">Start Windows PowerShell</span></span>

> [!NOTE]
> <span data-ttu-id="cbc4f-136">비즈니스용 Skype Online 커넥터는 현재 최신 Teams PowerShell 모듈의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="cbc4f-136">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span> <span data-ttu-id="cbc4f-137">최신 Teams PowerShell 공개 릴리스를 사용하는 경우 비즈니스용 Skype Online 커넥터를 설치할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cbc4f-137">If you're using the latest Teams PowerShell public release, you don't need to install the Skype for Business Online Connector.</span></span>
1. <span data-ttu-id="cbc4f-138">Teams [PowerShell 모듈을 설치합니다.](/microsoftteams/teams-powershell-install)</span><span class="sxs-lookup"><span data-stu-id="cbc4f-138">Install the [Teams PowerShell module](/microsoftteams/teams-powershell-install).</span></span>
    
2. <span data-ttu-id="cbc4f-139">명령 Windows PowerShell 프롬프트를 열고 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="cbc4f-139">Open a Windows PowerShell command prompt and run the following commands:</span></span> 

    ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```
   
   <span data-ttu-id="cbc4f-140">시작에 대한 자세한 Windows PowerShell 단일 창에서 모든 [Microsoft 365 또는 Office 365](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window) 서비스에 연결하거나 Windows PowerShell 에 대한 컴퓨터를 [Windows PowerShell.](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="cbc4f-140">If you want more information about starting Windows PowerShell, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
    
## <a name="disable-p2p-file-transfers-for-your-organization"></a><span data-ttu-id="cbc4f-141">조직의 P2P 파일 전송을 사용하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="cbc4f-141">Disable P2P file transfers for your organization</span></span>

<span data-ttu-id="cbc4f-142">기본적으로 조직의 전역 정책에서 _EnableP2PFileTransfer를_ 사용하도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="cbc4f-142">By default, _EnableP2PFileTransfer_ is enabled on the organization's global policy.</span></span> <span data-ttu-id="cbc4f-143">이 정책을 만들 때 사용자에게 _BposSAllModality 정책이 할당되었습니다._</span><span class="sxs-lookup"><span data-stu-id="cbc4f-143">When it was created, your users were assigned the _BposSAllModality_ policy.</span></span>
  
<span data-ttu-id="cbc4f-144">조직 내에서 P2P 전송을 허용하지만 다른 조직으로의 외부 파일 전송을 차단하려면 전역 수준에서만 변경해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cbc4f-144">To allow P2P transfers for inside your organization but block external file transfers to another organization, you just need to change it at a global level.</span></span> <span data-ttu-id="cbc4f-145">이를 위해 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="cbc4f-145">To do that, run:</span></span>
    
  ```PowerShell
  Set-CsExternalUserCommunicationPolicy -EnableP2PFileTransfer $False
  ```

## <a name="disable-p2p-file-transfers-for-a-user"></a><span data-ttu-id="cbc4f-146">사용자에 대한 P2P 파일 전송 사용 안 하도록 설정</span><span class="sxs-lookup"><span data-stu-id="cbc4f-146">Disable P2P file transfers for a user</span></span>

<span data-ttu-id="cbc4f-147">새 정책을 만들고 해당 사용자에게 부여하여 사용자에게 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cbc4f-147">You can apply this to a user by creating a new policy and granting it to that user.</span></span> <span data-ttu-id="cbc4f-148">이를 위해 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="cbc4f-148">To do that, run:</span></span> 

```powershell
New-CsExternalUserCommunicationPolicy -Identity BlockExternalFT -EnableP2PFileTransfer $False
```

```powershell
Grant-CsExternalUserCommunicationPolicy -PolicyName BlockExternalFT -Identity amosm@contoso.com
```

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="cbc4f-149">자세한 정보를 Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="cbc4f-149">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="cbc4f-150">Windows PowerShell 모든 것은 사용자 관리와 사용자가 허용되거나 허용되지 않는 작업을 관리하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="cbc4f-150">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="cbc4f-151">이 Windows PowerShell 여러 작업을 수행할 때 일상적인 작업을 단순화할 수 있는 단일 관리 지점을 사용하여 Microsoft 365 또는 Office 365 및 비즈니스용 Skype Online을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cbc4f-151">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="cbc4f-152">다음 항목을 Windows PowerShell 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cbc4f-152">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="cbc4f-153">Windows PowerShell 및 비즈니스용 Skype Online 소개</span><span class="sxs-lookup"><span data-stu-id="cbc4f-153">An introduction to Windows PowerShell and Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="cbc4f-154">Microsoft 365 또는 Office 365 PowerShell을 사용해야 하는 이유</span><span class="sxs-lookup"><span data-stu-id="cbc4f-154">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
- <span data-ttu-id="cbc4f-155">Windows PowerShell 사용자에 대한 설정을 한 번씩 변경하는 경우와 같이 Microsoft 365 관리 센터를 사용하는 경우와 같이 Microsoft 365 관리 센터를 사용하는 것 이상으로 속도, 단순성 및 생산성에 많은 이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cbc4f-155">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="cbc4f-156">다음 항목에서 이러한 이점에 대해 자세히 알아보습니다.</span><span class="sxs-lookup"><span data-stu-id="cbc4f-156">Learn about these advantages in the following topics:</span></span>
    
  - <span data-ttu-id="cbc4f-157">[Microsoft 365 또는 Office 365를 관리하는 가장 좋은 Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="cbc4f-157">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
  - [<span data-ttu-id="cbc4f-158">비즈니스용 skype Windows PowerShell 관리하기 위해 사용</span><span class="sxs-lookup"><span data-stu-id="cbc4f-158">Using Windows PowerShell to manage Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="cbc4f-159">비즈니스용 Windows PowerShell Skype 온라인 관리 작업을 수행하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cbc4f-159">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
## <a name="related-topics"></a><span data-ttu-id="cbc4f-160">관련 항목</span><span class="sxs-lookup"><span data-stu-id="cbc4f-160">Related topics</span></span>
[<span data-ttu-id="cbc4f-161">사용자 지정 외부 액세스 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="cbc4f-161">Create custom external access policies</span></span>](create-custom-external-access-policies.md)

[<span data-ttu-id="cbc4f-162">조직의 클라이언트 정책 설정</span><span class="sxs-lookup"><span data-stu-id="cbc4f-162">Set up client policies for your organization</span></span>](set-up-client-policies-for-your-organization.md)

[<span data-ttu-id="cbc4f-163">조직에서 회의 정책 설정</span><span class="sxs-lookup"><span data-stu-id="cbc4f-163">Set up conferencing policies in your organization</span></span>](set-up-conferencing-policies-for-your-organization.md)

  
