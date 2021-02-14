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
description: 비즈니스용 Skype 사용자가 기본 제공 비즈니스용 Skype 앱 피드백 도구를 사용하여 사용자가 문제를 보고하고 자신의 경험에 대한 피드백을 Microsoft에 직접 제공할 수 있습니다.
ms.openlocfilehash: 3b91bc88c20450b7c0d9c5705bceec53af5f9edb
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814187"
---
# <a name="turn-on-or-off-skype-for-business-client-feedback-reporting"></a><span data-ttu-id="30985-103">비즈니스용 Skype 클라이언트 피드백 보고 설정 또는 해제</span><span class="sxs-lookup"><span data-stu-id="30985-103">Turn on or off Skype for Business client feedback reporting</span></span>

<span data-ttu-id="30985-104">비즈니스용 Skype Online 사용자가 기본 제공 비즈니스용 Skype 앱 피드백 도구를 사용하여 사용자가 문제를 보고하고 자신의 경험에 대한 피드백을 Microsoft에 직접 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30985-104">You can enable your Skype for Business Online users to use the built-in Skype for Business app feedback tool to let users report issues and provide feedback directly to Microsoft about their experience.</span></span> 
  
![비즈니스용 Skype 클라이언트 보고.](../images/eac13837-04d9-4da1-8e80-54612cf6650d.png)
  
<span data-ttu-id="30985-106">이 도구를 사용하면 사용자가 디바이스의 앱에서 로그를 복사하여 Microsoft가 발생할 수 있는 문제를 더 잘 조사하고 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30985-106">Using this tool, a user can copy the logs from the app on their device to help Microsoft better investigate and troubleshoot problems that they might have.</span></span> 
  
![비즈니스용 Skype 클라이언트 보고.](../images/2dfb5603-1d69-41fc-a43e-91a3379acbe0.png)
  
<span data-ttu-id="30985-108">또한  _EnableOnlineFeedbackScreenshot_ 설정을 사용하여 사용자가 자신의 디바이스 스크린샷을 피드백의 일부로 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30985-108">You can also use the  _EnableOnlineFeedbackScreenshot_ setting so users can include a screenshot of their device as a part of their feedback.</span></span>
  
![비즈니스용 Skype 클라이언트 보고 양식입니다.](../images/d859578d-8116-4d4b-a08f-c0cae28b8b76.png)
  
> [!IMPORTANT]
> <span data-ttu-id="30985-110">앱의 피드백 도구에서 수집한 로그는 문제가 조사되는 동안 최대 90일 동안 미국에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="30985-110">The logs collected by the app's feedback tool will be stored for up to a maximum of 90 days in the United States while the issue is being investigated.</span></span> <span data-ttu-id="30985-111">이 때문에 조직의 데이터 보호 정책을 위반하는 경우 이 피드백 도구를 사용하도록 설정하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="30985-111">Because of this, please don't enable this feedback tool if this violates your organization's data protection policy.</span></span> 
  
## <a name="verify-and-start-windows-powershell"></a><span data-ttu-id="30985-112">확인 및 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="30985-112">Verify and start Windows PowerShell</span></span>

- <span data-ttu-id="30985-113">**버전 3.0 Windows PowerShell 실행 중인지 확인**</span><span class="sxs-lookup"><span data-stu-id="30985-113">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
    
1. <span data-ttu-id="30985-114">버전 3.0 이상을 실행하고 있는지 확인: 시작 메뉴를  >  Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="30985-114">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="30985-115">웹 창에  _Get-Host를_ 입력하여 **Windows PowerShell** 확인</span><span class="sxs-lookup"><span data-stu-id="30985-115">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="30985-116">버전 3.0 이상이 없는 경우 업데이트를 다운로드하여 설치해야 Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="30985-116">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell.</span></span> <span data-ttu-id="30985-117">버전 [Windows Management Framework 4.0으로](https://go.microsoft.com/fwlink/?LinkId=716845) Windows PowerShell 다운로드하고 업데이트하려면 4.0을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="30985-117">See [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0.</span></span> <span data-ttu-id="30985-118">메시지가 표시될 때 컴퓨터를 다시 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="30985-118">Restart your computer when you are prompted.</span></span>
    
4. <span data-ttu-id="30985-119">또한 비즈니스용 Skype Online에 연결하는 원격 Windows PowerShell 세션을 만들 수 있는 Teams용 Windows PowerShell 모듈을 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="30985-119">You will also need to install the Windows PowerShell module for Teams that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span> 
    
<span data-ttu-id="30985-120">자세한 내용은 단일 창에서 모든 [Microsoft 365 또는 Office 365 서비스에 Windows PowerShell 참조합니다.](https://technet.microsoft.com/library/dn568015.aspx)</span><span class="sxs-lookup"><span data-stu-id="30985-120">If you need to know more, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx).</span></span>
    
- <span data-ttu-id="30985-121">**세션 Windows PowerShell 시작**</span><span class="sxs-lookup"><span data-stu-id="30985-121">**Start a Windows PowerShell session**</span></span>
    
1. <span data-ttu-id="30985-122">시작 **메뉴에서**  >  **Windows PowerShell.**</span><span class="sxs-lookup"><span data-stu-id="30985-122">From the **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="30985-123">다음 **Windows PowerShell** 실행하여 Microsoft 365 또는 Office 365에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="30985-123">In the **Windows PowerShell** window, connect to your Microsoft 365 or Office 365 by running:</span></span>
    
  > [!NOTE]
  > <span data-ttu-id="30985-124">비즈니스용 Skype Online Connector는 현재 최신 Teams PowerShell 모듈의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="30985-124">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span>
  >
  > <span data-ttu-id="30985-125">최신 [Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/)공개 릴리스를 사용하는 경우 비즈니스용 Skype Online Connector를 설치할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="30985-125">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>
 
   ```PowerShell
   Import-Module -Name MicrosoftTeams
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
   ```
   <span data-ttu-id="30985-126">Windows PowerShell 시작에 대한 자세한 내용은 단일 Windows PowerShell 창에서 모든 [Microsoft 365 또는 Office 365](https://technet.microsoft.com/library/dn568015.aspx) 서비스에 연결 또는[Windows PowerShell.](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="30985-126">If you want more information about starting Windows PowerShell, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx) or[Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
    
## <a name="turn-on-client-app-feedback-reporting-for-all-the-users-in-your-organization"></a><span data-ttu-id="30985-127">조직의 모든 사용자에 대해 클라이언트 앱 피드백 보고 켜기</span><span class="sxs-lookup"><span data-stu-id="30985-127">Turn on client app feedback reporting for all the users in your organization</span></span>

<span data-ttu-id="30985-128">조직의 사용자에 대한 피드백 보고를 사용하도록 설정하고 디바이스 스크린샷을 제출할 수 있도록 허용하려면 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="30985-128">To enable feedback reporting for users in your organization and allow them to submit device screen shots, run:</span></span>
 
  ```PowerShell
  Set-CsClientPolicy -Identity EnableOnlineFeedback -EnableOnlineFeedback $true -EnableOnlineFeedbackScreenshots $true
  ```
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="30985-129">자세한 내용은 Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="30985-129">Want to know more about Windows PowerShell?</span></span>
- <span data-ttu-id="30985-130">Windows PowerShell 관리는 사용자 및 사용자가 허용되거나 허용되지 않는 작업을 관리하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="30985-130">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="30985-131">이 Windows PowerShell 여러 작업을 수행할 때 일상적인 작업을 간소화할 수 있는 단일 관리 지점을 사용하여 Microsoft 365 또는 Office 365 및 비즈니스용 Skype Online을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30985-131">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="30985-132">다음 항목을 Windows PowerShell 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="30985-132">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="30985-133">Windows PowerShell 및 Lync Online 소개</span><span class="sxs-lookup"><span data-stu-id="30985-133">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="30985-134">Microsoft 365 또는 Office 365를 관리하기 위해 Windows PowerShell 사용할 수 있는 6 가지 이유</span><span class="sxs-lookup"><span data-stu-id="30985-134">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Microsoft 365 or Office 365</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="30985-135">Windows PowerShell Microsoft 365 관리 센터를 사용하는 경우와 같이 여러 사용자에 대해 한 번씩 설정을 변경하는 경우와 같이 속도, 단순성 및 생산성에 많은 이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30985-135">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="30985-136">다음 항목에서 이러한 이점에 대해 자세히 배워야 합니다.</span><span class="sxs-lookup"><span data-stu-id="30985-136">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="30985-137">Microsoft 365 또는 Office 365를 관리하는 가장 좋은 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="30985-137">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="30985-138">비즈니스 Windows PowerShell 사용하여 비즈니스용 Skype Online 관리</span><span class="sxs-lookup"><span data-stu-id="30985-138">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="30985-139">비즈니스용 Windows PowerShell Skype Online 관리 작업을 수행하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30985-139">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a><span data-ttu-id="30985-140">관련 항목</span><span class="sxs-lookup"><span data-stu-id="30985-140">Related topics</span></span>
[<span data-ttu-id="30985-141">비즈니스용 Skype 온라인 설정</span><span class="sxs-lookup"><span data-stu-id="30985-141">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="30985-142">비즈니스용 Skype 사용자가 Skype 연락처를 추가하도록 허용</span><span class="sxs-lookup"><span data-stu-id="30985-142">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

  
 
