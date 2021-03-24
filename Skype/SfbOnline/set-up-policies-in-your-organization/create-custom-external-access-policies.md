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
description: 비즈니스용 Skype Online을 사용하면 추가 외부 액세스 정책을 만들 수 있습니다. 여러 조합을 사용할 수 있는 클라이언트 또는 회의 정책과 달리, 대부분의 시나리오를 다를 수 있는 미리 정의된 세 가지 외부 액세스 정책이 있습니다.
ms.openlocfilehash: 3e5e8cf1c464b1011a49b06b2d1958246d332c91
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51100614"
---
# <a name="create-custom-external-access-policies"></a><span data-ttu-id="b554d-104">사용자 지정 외부 액세스 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="b554d-104">Create custom external access policies</span></span>

<span data-ttu-id="b554d-105">비즈니스용 Skype Online을 사용하면 추가 외부 액세스 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b554d-105">Skype for Business Online allows you to create additional external access policies.</span></span> <span data-ttu-id="b554d-106">여러 조합을 사용할 수 있는 클라이언트 또는 회의 정책과 달리, 대부분의 시나리오를 다를 수 있는 미리 정의된 세 가지 외부 액세스 정책이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b554d-106">Unlike client or conferencing policies, where you can have multiple combinations, there are three predefined external access policies that can cover most of the scenarios.</span></span> <span data-ttu-id="b554d-107">다음은 다음 사항일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b554d-107">These are:</span></span>
  
- <span data-ttu-id="b554d-108">페더리드 또는 Skype 소비자 액세스 _없음(Tag:NoFederationAndPIC)_</span><span class="sxs-lookup"><span data-stu-id="b554d-108">No Federated or Skype Consumer Access (_Tag:NoFederationAndPIC_ )</span></span>
    
- <span data-ttu-id="b554d-109">페더리드 액세스 _전용(Tag:FederationOnly)_</span><span class="sxs-lookup"><span data-stu-id="b554d-109">Federated Access Only (_Tag:FederationOnly_ )</span></span>
    
- <span data-ttu-id="b554d-110">페더레이드 및 소비자 _액세스(페더리게이트AndPICDefault)_</span><span class="sxs-lookup"><span data-stu-id="b554d-110">Federated and Consumer Access (_FederationAndPICDefault_)</span></span>
    
<span data-ttu-id="b554d-111">사용자 지정 외부 정책을 사용하면 위의 설정에서 다루지 않는 추가 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b554d-111">Custom external policies allow you to create additional polices that aren't covered by the settings above.</span></span> <span data-ttu-id="b554d-112">정책을 만들 때 필요한 모든 매개 변수를 설정해야 하며 나중에 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b554d-112">When the policy was created, you would be required to set all required parameters and you couldn't alter them later.</span></span> <span data-ttu-id="b554d-113">새 사용자 지정 정책을 만들면 Skype 소비자 액세스 또는 공용 클라우드 오디오/비디오를 사용하지 않도록 설정하는 정책과 같은 기능을 제어할 수 있습니다. 이는 미리 정의된 설정으로 다루지 않은 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b554d-113">Creating new custom policies allow you to control features such as Skype consumer access or a policy to disable public cloud audio/video, which is something that wasn't covered with predefined settings.</span></span> <span data-ttu-id="b554d-114">사용자 지정 외부 액세스 정책은 클라이언트, 이동성 및 회의 정책과 동일한 구문을 따르고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b554d-114">Custom external access policies follow the same syntax as client, mobility, and conferencing policies.</span></span> <span data-ttu-id="b554d-115">이러한 설정에 대한 자세한 내용은 여기를 [클릭하세요.](/previous-versions//mt228132(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="b554d-115">You can find out more about those settings [here](/previous-versions//mt228132(v=technet.10)).</span></span>
  
<span data-ttu-id="b554d-116">이 작업을 실행하려면 사용자가 지원되는 2016년 비즈니스용 Skype 앱의 지원되는 버전을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b554d-116">To make this work, the user must be using a supported version of 2016 Click-to-Run Skype for Business app that supports it.</span></span> <span data-ttu-id="b554d-117">비즈니스용 Skype 2016 Click-to-Run 클라이언트의 최소 버전이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="b554d-117">The following minimum version of Skype for Business 2016 Click-to-Run client is required:</span></span>
  
|<span data-ttu-id="b554d-118">**유형**</span><span class="sxs-lookup"><span data-stu-id="b554d-118">**Type**</span></span>|<span data-ttu-id="b554d-119">**릴리스 날짜**</span><span class="sxs-lookup"><span data-stu-id="b554d-119">**Release date**</span></span>|<span data-ttu-id="b554d-120">**버전**</span><span class="sxs-lookup"><span data-stu-id="b554d-120">**Version**</span></span>|<span data-ttu-id="b554d-121">**빌드**</span><span class="sxs-lookup"><span data-stu-id="b554d-121">**Build**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="b554d-122">현재 채널에 대한 첫 번째 릴리스</span><span class="sxs-lookup"><span data-stu-id="b554d-122">First Release for Current Channel</span></span>  <br/> |<span data-ttu-id="b554d-123">11/17/2016</span><span class="sxs-lookup"><span data-stu-id="b554d-123">11/17/2016</span></span>  <br/> |<span data-ttu-id="b554d-124">16.0.7571.2006</span><span class="sxs-lookup"><span data-stu-id="b554d-124">16.0.7571.2006</span></span>  <br/> |<span data-ttu-id="b554d-125">버전 1611(빌드 7571.2006)</span><span class="sxs-lookup"><span data-stu-id="b554d-125">Version 1611 (Build 7571.2006)</span></span>  <br/> |
|<span data-ttu-id="b554d-126">현재 채널</span><span class="sxs-lookup"><span data-stu-id="b554d-126">Current Channel</span></span>  <br/> |<span data-ttu-id="b554d-127">12/6/2016</span><span class="sxs-lookup"><span data-stu-id="b554d-127">12/6/2016</span></span>  <br/> |<span data-ttu-id="b554d-128">16.0.7571.2072</span><span class="sxs-lookup"><span data-stu-id="b554d-128">16.0.7571.2072</span></span>  <br/> |<span data-ttu-id="b554d-129">버전 1611(빌드 7571.2072)</span><span class="sxs-lookup"><span data-stu-id="b554d-129">Version 1611 (Build 7571.2072)</span></span>  <br/> |
|<span data-ttu-id="b554d-130">지연 채널</span><span class="sxs-lookup"><span data-stu-id="b554d-130">Deferred Channel</span></span>  <br/> |<span data-ttu-id="b554d-131">2/22/2017</span><span class="sxs-lookup"><span data-stu-id="b554d-131">2/22/2017</span></span>  <br/> |<span data-ttu-id="b554d-132">16.0.7369.2118</span><span class="sxs-lookup"><span data-stu-id="b554d-132">16.0.7369.2118</span></span>  <br/> |<span data-ttu-id="b554d-133">버전 1609(빌드 7369.2118)</span><span class="sxs-lookup"><span data-stu-id="b554d-133">Version 1609 (Build 7369.2118)</span></span>  <br/> |
   
> [!CAUTION]
> <span data-ttu-id="b554d-134">이전 버전의 비즈니스용 Skype Windows 앱 또는 Mac 클라이언트를 사용하는 사용자는 여전히 파일을 전송할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b554d-134">Users who are using older versions of Skype for Business Windows apps or Mac clients will still be able to transfer files.</span></span> 
  
## <a name="start-windows-powershell"></a><span data-ttu-id="b554d-135">시작 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b554d-135">Start Windows PowerShell</span></span>

> [!NOTE]
> <span data-ttu-id="b554d-136">비즈니스용 Skype Online 커넥터는 현재 최신 Teams PowerShell 모듈의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="b554d-136">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span> <span data-ttu-id="b554d-137">최신 Teams PowerShell 공개 릴리스를 사용하는 경우 비즈니스용 Skype Online 커넥터를 설치할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b554d-137">If you're using the latest Teams PowerShell public release, you don't need to install the Skype for Business Online Connector.</span></span>
1. <span data-ttu-id="b554d-138">Teams [PowerShell 모듈을 설치합니다.](/microsoftteams/teams-powershell-install)</span><span class="sxs-lookup"><span data-stu-id="b554d-138">Install the [Teams PowerShell module](/microsoftteams/teams-powershell-install).</span></span>
    
2. <span data-ttu-id="b554d-139">명령 Windows PowerShell 프롬프트를 열고 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="b554d-139">Open a Windows PowerShell command prompt and run the following commands:</span></span> 
 ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```
   
   <span data-ttu-id="b554d-140">시작에 대한 자세한 Windows PowerShell 단일 창에서 모든 [Microsoft 365 또는 Office 365](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window) 서비스에 연결하거나 Windows PowerShell 에 대한 컴퓨터를 [Windows PowerShell.](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="b554d-140">If you want more information about starting Windows PowerShell, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
   
## <a name="create-a-custom-external-access-policy-for-a-user"></a><span data-ttu-id="b554d-141">사용자에 대한 사용자 지정 외부 액세스 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="b554d-141">Create a custom external access policy for a user</span></span>

<span data-ttu-id="b554d-142">이렇게 하여 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="b554d-142">To do this, run:</span></span>
  
 
```powershell
New-CsExternalAccessPolicy -Identity BlockSkypeVideo -EnablePublicCloudAccess $True -EnablePublicCloudAudioVideoAccess $False -EnableFederationAccess $True -EnableOutsideAccess $True
```


```powershell
Grant-CsExternalAccessPolicy -PolicyName BlockSkypeVideo -Identity amosm@contoso.com
```

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="b554d-143">자세한 정보를 Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="b554d-143">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="b554d-144">Windows PowerShell 모든 것은 사용자 관리와 사용자가 허용되거나 허용되지 않는 작업을 관리하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b554d-144">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="b554d-145">이 Windows PowerShell 여러 작업을 수행할 때 일상적인 작업을 단순화할 수 있는 단일 관리 지점을 사용하여 Microsoft 365 또는 Office 365 및 비즈니스용 Skype Online을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b554d-145">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="b554d-146">다음 항목을 Windows PowerShell 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b554d-146">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="b554d-147">Windows PowerShell 및 비즈니스용 Skype Online 소개</span><span class="sxs-lookup"><span data-stu-id="b554d-147">An introduction to Windows PowerShell and Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="b554d-148">Microsoft 365 또는 Office 365 PowerShell을 사용해야 하는 이유</span><span class="sxs-lookup"><span data-stu-id="b554d-148">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
- <span data-ttu-id="b554d-149">Windows PowerShell 사용자에 대한 설정을 한 번씩 변경하는 경우와 같이 Microsoft 365 관리 센터를 사용하는 경우와 같이 Microsoft 365 관리 센터를 사용하는 것 이상으로 속도, 단순성 및 생산성에 많은 이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b554d-149">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="b554d-150">다음 항목에서 이러한 이점에 대해 자세히 알아보습니다.</span><span class="sxs-lookup"><span data-stu-id="b554d-150">Learn about these advantages in the following topics:</span></span>
    
  - <span data-ttu-id="b554d-151">[Microsoft 365 또는 Office 365를 관리하는 가장 좋은 Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="b554d-151">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
  - [<span data-ttu-id="b554d-152">비즈니스용 skype Windows PowerShell 관리하기 위해 사용</span><span class="sxs-lookup"><span data-stu-id="b554d-152">Using Windows PowerShell to manage Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="b554d-153">비즈니스용 Windows PowerShell Skype 온라인 관리 작업을 수행하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b554d-153">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
## <a name="related-topics"></a><span data-ttu-id="b554d-154">관련 항목</span><span class="sxs-lookup"><span data-stu-id="b554d-154">Related topics</span></span>
[<span data-ttu-id="b554d-155">지점 및 지점 파일 전송 차단</span><span class="sxs-lookup"><span data-stu-id="b554d-155">Block point-to-point file transfers</span></span>](block-point-to-point-file-transfers.md)

[<span data-ttu-id="b554d-156">조직의 클라이언트 정책 설정</span><span class="sxs-lookup"><span data-stu-id="b554d-156">Set up client policies for your organization</span></span>](set-up-client-policies-for-your-organization.md)

[<span data-ttu-id="b554d-157">조직에서 회의 정책 설정</span><span class="sxs-lookup"><span data-stu-id="b554d-157">Set up conferencing policies in your organization</span></span>](set-up-conferencing-policies-for-your-organization.md)

  
