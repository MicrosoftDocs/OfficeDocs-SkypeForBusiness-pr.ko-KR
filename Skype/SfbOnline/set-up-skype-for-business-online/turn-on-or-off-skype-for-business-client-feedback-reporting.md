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
description: 사용자가 기본 제공 비즈니스용 Skype 앱 피드백 도구를 사용할 수 있도록 비즈니스용 Skype 사용자들이 문제를 보고하고 사용자 경험에 대한 피드백을 Microsoft에 직접 제공할 수 있도록 설정할 수 있습니다.
ms.openlocfilehash: 151ba9ee82c95f088f5c7fc87de3a06ce609ab01
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52239101"
---
# <a name="turn-on-or-off-skype-for-business-client-feedback-reporting"></a><span data-ttu-id="5bf01-103">비즈니스용 Skype 클라이언트 피드백 보고 설정 또는 해제</span><span class="sxs-lookup"><span data-stu-id="5bf01-103">Turn on or off Skype for Business client feedback reporting</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

<span data-ttu-id="5bf01-104">기본 제공 비즈니스용 Skype 앱 피드백 도구를 사용할 수 있도록 비즈니스용 Skype 사용자들이 문제를 보고하고 Microsoft에 자신의 경험에 대한 피드백을 직접 제공할 수 있도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5bf01-104">You can enable your Skype for Business Online users to use the built-in Skype for Business app feedback tool to let users report issues and provide feedback directly to Microsoft about their experience.</span></span> 
  
![피드백 제공 아이콘](../images/eac13837-04d9-4da1-8e80-54612cf6650d.png)
  
<span data-ttu-id="5bf01-106">이 도구를 사용하면 사용자가 디바이스의 앱에서 로그를 복사하여 Microsoft에서 발생할 수 있는 문제를 더 잘 조사하고 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5bf01-106">Using this tool, a user can copy the logs from the app on their device to help Microsoft better investigate and troubleshoot problems that they might have.</span></span> 
  
![아이콘을 사용하여 설정 보고](../images/2dfb5603-1d69-41fc-a43e-91a3379acbe0.png)
  
<span data-ttu-id="5bf01-108">사용자가 피드백의 일부로 디바이스 스크린샷을 포함할 수 있도록  _EnableOnlineFeedbackScreenshot_ 설정을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5bf01-108">You can also use the  _EnableOnlineFeedbackScreenshot_ setting so users can include a screenshot of their device as a part of their feedback.</span></span>
  
![비즈니스용 Skype 보고 양식입니다.](../images/d859578d-8116-4d4b-a08f-c0cae28b8b76.png)
  
> [!IMPORTANT]
> <span data-ttu-id="5bf01-110">앱의 피드백 도구에서 수집한 로그는 문제가 조사되는 동안 미국에서 최대 90일 동안 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="5bf01-110">The logs collected by the app's feedback tool will be stored for up to a maximum of 90 days in the United States while the issue is being investigated.</span></span> <span data-ttu-id="5bf01-111">이 때문에 조직의 데이터 보호 정책을 위반하는 경우 이 피드백 도구를 사용하도록 설정하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5bf01-111">Because of this, please don't enable this feedback tool if this violates your organization's data protection policy.</span></span> 
  
## <a name="start-windows-powershell"></a><span data-ttu-id="5bf01-112">시작 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="5bf01-112">Start Windows PowerShell</span></span>

> [!NOTE]
> <span data-ttu-id="5bf01-113">비즈니스용 Skype 온라인 커넥터는 현재 최신 PowerShell Teams 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="5bf01-113">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span> <span data-ttu-id="5bf01-114">최신 PowerShell 공개 Teams 사용하는 경우 온라인 커넥터를 비즈니스용 Skype 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5bf01-114">If you're using the latest Teams PowerShell public release, you don't need to install the Skype for Business Online Connector.</span></span>
1. <span data-ttu-id="5bf01-115">[PowerShell Teams 설치합니다.](/microsoftteams/teams-powershell-install)</span><span class="sxs-lookup"><span data-stu-id="5bf01-115">Install the [Teams PowerShell module](/microsoftteams/teams-powershell-install).</span></span>
    
2. <span data-ttu-id="5bf01-116">명령 Windows PowerShell 프롬프트를 열고 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="5bf01-116">Open a Windows PowerShell command prompt and run the following commands:</span></span> 

   ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $userCredential = Get-Credential
   Connect-MicrosoftTeams -Credential $userCredential
   ```
   <span data-ttu-id="5bf01-117">시작에 대한 자세한 Windows PowerShell 을 참조하세요커넥트 Microsoft 365 Office 365 단일 창에서 모든 Windows PowerShell 또는 [Windows PowerShell.](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md) [](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window)</span><span class="sxs-lookup"><span data-stu-id="5bf01-117">If you want more information about starting Windows PowerShell, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
   
## <a name="turn-on-client-app-feedback-reporting-for-all-the-users-in-your-organization"></a><span data-ttu-id="5bf01-118">조직의 모든 사용자에 대한 클라이언트 앱 피드백 보고 설정</span><span class="sxs-lookup"><span data-stu-id="5bf01-118">Turn on client app feedback reporting for all the users in your organization</span></span>

<span data-ttu-id="5bf01-119">조직의 사용자에 대한 피드백 보고를 사용하도록 설정하고 디바이스 스크린샷을 제출할 수 있도록 허용하려면 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="5bf01-119">To enable feedback reporting for users in your organization and allow them to submit device screenshots, run:</span></span>
 
  ```PowerShell
  Set-CsClientPolicy -Identity EnableOnlineFeedback -EnableOnlineFeedback $true -EnableOnlineFeedbackScreenshots $true
  ```
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="5bf01-120">자세한 정보를 Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="5bf01-120">Want to know more about Windows PowerShell?</span></span>
- <span data-ttu-id="5bf01-121">Windows PowerShell 모든 것은 사용자 관리와 사용자가 허용되거나 허용되지 않는 작업을 관리하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="5bf01-121">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="5bf01-122">이 Windows PowerShell 여러 작업을 수행할 때 일상적인 작업을 단순화할 수 있는 단일 관리 Microsoft 365 Office 365 비즈니스용 Skype 온라인에서 관리하거나 온라인을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5bf01-122">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="5bf01-123">다음 항목을 Windows PowerShell 다음 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5bf01-123">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="5bf01-124">Windows PowerShell 및 비즈니스용 Skype Online 소개</span><span class="sxs-lookup"><span data-stu-id="5bf01-124">An introduction to Windows PowerShell and Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="5bf01-125">Windows PowerShell 관리하기 위해 Windows PowerShell 이유 Microsoft 365 Office 365</span><span class="sxs-lookup"><span data-stu-id="5bf01-125">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Microsoft 365 or Office 365</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
- <span data-ttu-id="5bf01-126">Windows PowerShell 많은 사용자에 대해 한 Microsoft 365 설정하는 경우와 같이 관리 센터를 사용하는 것만 사용하여 속도, 단순성 및 생산성에 많은 이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5bf01-126">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="5bf01-127">다음 항목에서 이러한 이점에 대해 자세히 알아보습니다.</span><span class="sxs-lookup"><span data-stu-id="5bf01-127">Learn about these advantages in the following topics:</span></span>
    
  - <span data-ttu-id="5bf01-128">[사용자와 함께 Microsoft 365 또는 Office 365 가장 Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="5bf01-128">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
  - [<span data-ttu-id="5bf01-129">온라인 Windows PowerShell 관리하기 위해 비즈니스용 Skype 사용</span><span class="sxs-lookup"><span data-stu-id="5bf01-129">Using Windows PowerShell to manage Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="5bf01-130">일반적인 Windows PowerShell 관리 작업을 수행하는 데 비즈니스용 Skype 사용</span><span class="sxs-lookup"><span data-stu-id="5bf01-130">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

## <a name="related-topics"></a><span data-ttu-id="5bf01-131">관련 항목</span><span class="sxs-lookup"><span data-stu-id="5bf01-131">Related topics</span></span>
[<span data-ttu-id="5bf01-132">비즈니스용 Skype 온라인 설정</span><span class="sxs-lookup"><span data-stu-id="5bf01-132">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="5bf01-133">비즈니스용 Skype 사용자가 Skype 연락처를 추가하도록 허용</span><span class="sxs-lookup"><span data-stu-id="5bf01-133">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

  
