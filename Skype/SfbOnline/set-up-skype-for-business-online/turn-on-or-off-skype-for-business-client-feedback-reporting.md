---
title: 비즈니스용 Skype 클라이언트 피드백 보고 설정 또는 해제
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 35562b48-1da1-4081-8a3a-033d0f1986b2
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
description: 비즈니스용 Skype 사용자에 게 기본 제공 비즈니스용 Skype 앱 피드백 도구를 사용 하 여 사용자에 게 문제를 보고 하 고 Microsoft에 직접 의견을 제공할 수 있도록 하는 것이 좋습니다.
ms.openlocfilehash: 04dc6ddcb82e40bef2a0aa6a6197566d9dd8a374
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2020
ms.locfileid: "44164547"
---
# <a name="turn-on-or-off-skype-for-business-client-feedback-reporting"></a><span data-ttu-id="ab31b-103">비즈니스용 Skype 클라이언트 피드백 보고 설정 또는 해제</span><span class="sxs-lookup"><span data-stu-id="ab31b-103">Turn on or off Skype for Business client feedback reporting</span></span>

<span data-ttu-id="ab31b-104">비즈니스용 Skype Online 사용자에 게 기본 제공 비즈니스용 Skype 앱 피드백 도구를 사용 하 여 사용자에 게 문제를 보고 하 고 Microsoft에 직접 의견을 제공할 수 있도록 하는 기능을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab31b-104">You can enable your Skype for Business Online users to use the built-in Skype for Business app feedback tool to let users report issues and provide feedback directly to Microsoft about their experience.</span></span> 
  
![비즈니스용 Skype 클라이언트 보고.](../images/eac13837-04d9-4da1-8e80-54612cf6650d.png)
  
<span data-ttu-id="ab31b-106">이 도구를 사용 하면 사용자가 장치에서 앱의 로그를 복사 하 여 Microsoft가 발생할 수 있는 문제를 보다 효율적으로 조사 하 고 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab31b-106">Using this tool, a user can copy the logs from the app on their device to help Microsoft better investigate and troubleshoot problems that they might have.</span></span> 
  
![비즈니스용 Skype 클라이언트 보고.](../images/2dfb5603-1d69-41fc-a43e-91a3379acbe0.png)
  
<span data-ttu-id="ab31b-108">_EnableOnlineFeedbackScreenshot_ 설정을 사용 하 여 사용자가 자신의 피드백의 일부로 디바이스의 스크린샷을 포함할 수 있도록 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab31b-108">You can also use the  _EnableOnlineFeedbackScreenshot_ setting so users can include a screenshot of their device as a part of their feedback.</span></span>
  
![비즈니스용 Skype 클라이언트 보고 양식](../images/d859578d-8116-4d4b-a08f-c0cae28b8b76.png)
  
> [!IMPORTANT]
> <span data-ttu-id="ab31b-110">앱의 피드백 도구를 통해 수집 된 로그는 문제를 조사 하는 동안 최대 90 일 동안 해당 지역에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ab31b-110">The logs collected by the app's feedback tool will be stored for up to a maximum of 90 days in the United States while the issue is being investigated.</span></span> <span data-ttu-id="ab31b-111">이 때문에 조직의 데이터 보호 정책에 위배 되는 경우이 피드백 도구를 사용 하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="ab31b-111">Because of this, please don't enable this feedback tool if this violates your organization's data protection policy.</span></span> 
  
## <a name="verify-and-start-windows-powershell"></a><span data-ttu-id="ab31b-112">Windows PowerShell 확인 및 시작</span><span class="sxs-lookup"><span data-stu-id="ab31b-112">Verify and start Windows PowerShell</span></span>

- <span data-ttu-id="ab31b-113">**Windows PowerShell 버전 3.0 이상을 실행 하 고 있는지 확인**</span><span class="sxs-lookup"><span data-stu-id="ab31b-113">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
    
1. <span data-ttu-id="ab31b-114">버전 3.0 이상을 실행 하 고 있는지 확인 하려면 **시작 메뉴** > 에서**Windows PowerShell**을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab31b-114">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="ab31b-115">**Windows PowerShell** 창에서 _Get-Host_ 를 입력 하 여 버전을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab31b-115">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="ab31b-116">버전 3.0 이상이 없는 경우 Windows PowerShell 업데이트를 다운로드 하 여 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab31b-116">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell.</span></span> <span data-ttu-id="ab31b-117">Windows [Management 프레임 워크 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) 를 참조 하 여 windows PowerShell을 버전 4.0로 다운로드 하 고 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab31b-117">See [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0.</span></span> <span data-ttu-id="ab31b-118">메시지가 표시 되 면 컴퓨터를 다시 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab31b-118">Restart your computer when you are prompted.</span></span>
    
4. <span data-ttu-id="ab31b-119">비즈니스용 skype Online에 연결 되는 원격 Windows PowerShell 세션을 만들 수 있는 비즈니스용 Skype Online 용 Windows PowerShell 모듈을 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab31b-119">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span> <span data-ttu-id="ab31b-120">이 모듈은 64 비트 컴퓨터 에서만 지원 되며 비즈니스용 [Skype Online 용 Windows PowerShell 모듈](https://go.microsoft.com/fwlink/?LinkId=294688)의 Microsoft 다운로드 센터에서 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab31b-120">This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688).</span></span> <span data-ttu-id="ab31b-121">메시지가 표시 되 면 컴퓨터를 다시 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab31b-121">Restart your computer if you are prompted.</span></span>
    
<span data-ttu-id="ab31b-122">자세한 정보를 알고 싶은 경우에 [는 단일 Windows PowerShell 창에서 모든 Microsoft 365 또는 Office 365 서비스에 연결](https://technet.microsoft.com/library/dn568015.aspx)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ab31b-122">If you need to know more, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx).</span></span>
    
- <span data-ttu-id="ab31b-123">**Windows PowerShell 세션 시작**</span><span class="sxs-lookup"><span data-stu-id="ab31b-123">**Start a Windows PowerShell session**</span></span>
    
1. <span data-ttu-id="ab31b-124">**시작 메뉴** > 에서**Windows PowerShell**을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab31b-124">From the **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="ab31b-125">**Windows PowerShell** 창에서 다음을 실행 하 여 Microsoft 365 또는 Office 365에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab31b-125">In the **Windows PowerShell** window, connect to your Microsoft 365 or Office 365 by running:</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="ab31b-126">비즈니스용 Skype Online Windows PowerShell 모듈을 처음 사용 하는 경우에만 **Import-Module** 명령을 실행 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ab31b-126">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>
 
   ```PowerShell
    Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
   ```
   <span data-ttu-id="ab31b-127">Windows PowerShell을 시작 하는 방법에 대 한 자세한 내용은 [단일 Windows powershell 창에서 모든 Microsoft 365 또는 Office 365 서비스에 연결](https://technet.microsoft.com/library/dn568015.aspx) 또는[windows Powershell 용 컴퓨터 설정을](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ab31b-127">If you want more information about starting Windows PowerShell, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx) or[Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
    
## <a name="turn-on-client-app-feedback-reporting-for-all-the-users-in-your-organization"></a><span data-ttu-id="ab31b-128">조직의 모든 사용자에 대 한 클라이언트 앱 피드백 보고 설정</span><span class="sxs-lookup"><span data-stu-id="ab31b-128">Turn on client app feedback reporting for all the users in your organization</span></span>

<span data-ttu-id="ab31b-129">조직의 사용자에 대 한 피드백 보고 기능을 사용 하도록 설정 하 고 장치 스크린샷 제출 하도록 허용 하려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab31b-129">To enable feedback reporting for users in your organization and allow them to submit device screen shots, run:</span></span>
 
  ```PowerShell
  Set-CsClientPolicy -Identity EnableOnlineFeedback -EnableOnlineFeedback $true -EnableOnlineFeedbackScreenshots $true
  ```
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="ab31b-130">Windows PowerShell에 대 한 자세한 정보를 확인 하 고 싶으신가요?</span><span class="sxs-lookup"><span data-stu-id="ab31b-130">Want to know more about Windows PowerShell?</span></span>
- <span data-ttu-id="ab31b-131">Windows PowerShell은 사용자 및 허용 되지 않거나 수행할 수 있는 사용자를 관리 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab31b-131">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="ab31b-132">Windows PowerShell을 사용 하면 여러 작업을 수행할 때 일상 업무를 단순화할 수 있는 단일 관리 지점을 사용 하 여 Microsoft 365 또는 Office 365 및 비즈니스용 Skype Online을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab31b-132">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="ab31b-133">Windows PowerShell을 시작 하려면 다음 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ab31b-133">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="ab31b-134">Windows PowerShell 및 Lync Online 소개</span><span class="sxs-lookup"><span data-stu-id="ab31b-134">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="ab31b-135">Windows PowerShell을 사용 하 여 Microsoft 365 또는 Office 365을 관리 해야 하는 여섯 가지 이유</span><span class="sxs-lookup"><span data-stu-id="ab31b-135">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Microsoft 365 or Office 365</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="ab31b-136">Windows PowerShell에는 한 번에 여러 사용자의 설정을 변경 하는 경우와 같이 Microsoft 365 관리 센터를 사용 하는 경우에만 속도, 단순성, 생산성 등 다양 한 이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab31b-136">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="ab31b-137">다음 항목에서 이러한 이점에 대해 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="ab31b-137">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="ab31b-138">Windows PowerShell을 사용 하 여 Microsoft 365 또는 Office 365을 관리 하는 최상의 방법</span><span class="sxs-lookup"><span data-stu-id="ab31b-138">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="ab31b-139">Windows PowerShell을 사용 하 여 비즈니스용 Skype Online 관리</span><span class="sxs-lookup"><span data-stu-id="ab31b-139">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="ab31b-140">Windows PowerShell을 사용 하 여 일반적인 비즈니스용 Skype Online 관리 작업 수행</span><span class="sxs-lookup"><span data-stu-id="ab31b-140">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a><span data-ttu-id="ab31b-141">관련 항목</span><span class="sxs-lookup"><span data-stu-id="ab31b-141">Related topics</span></span>
[<span data-ttu-id="ab31b-142">비즈니스용 Skype 온라인 설정</span><span class="sxs-lookup"><span data-stu-id="ab31b-142">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="ab31b-143">비즈니스용 Skype 사용자가 Skype 연락처를 추가하도록 허용</span><span class="sxs-lookup"><span data-stu-id="ab31b-143">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

  
 
