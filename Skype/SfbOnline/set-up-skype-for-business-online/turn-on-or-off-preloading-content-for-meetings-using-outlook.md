---
title: 모임을 위해 콘텐츠를 미리 로드할 수 있도록 설정 또는 끄기 Outlook
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: d217d422-f7e9-433d-ad24-bf41751f65ca
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
description: '파일 또는 첨부 파일을 사용하여 비즈니스용 Skype 모임에 대해 미리 로드된 콘텐츠를 켜거나 끄는 Outlook 참조하세요. '
ms.openlocfilehash: b6ff40e34c6459a75d0b79a8d750902a3457e00d
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52239111"
---
# <a name="turn-on-or-off-allowing-content-to-be-preloaded-for-meetings-using-outlook"></a><span data-ttu-id="46603-103">모임을 위해 콘텐츠를 미리 로드할 수 있도록 설정 또는 끄기 Outlook</span><span class="sxs-lookup"><span data-stu-id="46603-103">Turn on or off allowing content to be preloaded for meetings using Outlook</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

<span data-ttu-id="46603-104">사용자는 온라인 모임에 대한 모임 초대에 Outlook 콘텐츠, 파일 또는 첨부 파일을 비즈니스용 Skype 수 있지만 켜거나 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46603-104">Users can preload content, files, or attachments that are attached to an Outlook meeting invitation to a Skype for Business Online meeting, but you can it turn on or off.</span></span> <span data-ttu-id="46603-105">기본적으로 온라인을 사용하는 모든 조직에 대해 비즈니스용 Skype 설정되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46603-105">It's turned on by default for all organizations that are using Skype for Business Online.</span></span> <span data-ttu-id="46603-106">모임에 대한 첨부 파일을 [미리 로드하는 비즈니스용 Skype 참조합니다.](https://support.office.com/article/fd3d9f9d-b448-4754-b813-02e49393f251)</span><span class="sxs-lookup"><span data-stu-id="46603-106">See how to [Preload attachments for a Skype for Business meeting](https://support.office.com/article/fd3d9f9d-b448-4754-b813-02e49393f251).</span></span>
  
> [!NOTE]
> <span data-ttu-id="46603-107">현재 _MaxContentStorageMB_ 및 _MaxUploadFileMB의_ 온라인 값을 설정하거나 보기 위해 비즈니스용 Skype 온라인에서 사용할 수 있는 cmdlet은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="46603-107">Currently, there are no cmdlets available in Skype for Business Online for setting or viewing online values for  _MaxContentStorageMB_ and _MaxUploadFileMB_.</span></span> <span data-ttu-id="46603-108">이러한 구성은 프레미스 배포에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46603-108">They are only available for on-premises deployments.</span></span> <span data-ttu-id="46603-109">연결된 콘텐츠가  _MaxUploadFileSizeMB를_ 초과하거나 _MaxContentStorageMB_ 제한에 도달하는 경우 콘텐츠가 모임에 업로드되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="46603-109">It's important to know that content won't be uploaded to a meeting if the attached content exceeds the  _MaxUploadFileSizeMB_ or if the _MaxContentStorageMB_ limit is reached.</span></span>
  
## <a name="to-get-you-started"></a><span data-ttu-id="46603-110">시작을 위해</span><span class="sxs-lookup"><span data-stu-id="46603-110">To get you started</span></span>

## <a name="start-windows-powershell"></a><span data-ttu-id="46603-111">시작 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="46603-111">Start Windows PowerShell</span></span>

> [!NOTE]
> <span data-ttu-id="46603-112">비즈니스용 Skype 온라인 커넥터는 현재 최신 PowerShell Teams 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="46603-112">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span> <span data-ttu-id="46603-113">최신 PowerShell 공개 Teams 사용하는 경우 온라인 커넥터를 비즈니스용 Skype 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="46603-113">If you're using the latest Teams PowerShell public release, you don't need to install the Skype for Business Online Connector.</span></span>
1. <span data-ttu-id="46603-114">[PowerShell Teams 설치합니다.](/microsoftteams/teams-powershell-install)</span><span class="sxs-lookup"><span data-stu-id="46603-114">Install the [Teams PowerShell module](/microsoftteams/teams-powershell-install).</span></span>
    
2. <span data-ttu-id="46603-115">명령 Windows PowerShell 프롬프트를 열고 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="46603-115">Open a Windows PowerShell command prompt and run the following commands:</span></span> 

   ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $userCredential = Get-Credential
   Connect-MicrosoftTeams -Credential $userCredential
   ```

<span data-ttu-id="46603-116">시작에 대한 자세한 Windows PowerShell 을 참조하세요커넥트 Microsoft 365 Office 365 단일 창에서 모든 Windows PowerShell 또는 [Windows PowerShell.](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md) [](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window)</span><span class="sxs-lookup"><span data-stu-id="46603-116">If you want more information about starting Windows PowerShell, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
  
## <a name="turning-it-on-or-off"></a><span data-ttu-id="46603-117">켜기 또는 끄기</span><span class="sxs-lookup"><span data-stu-id="46603-117">Turning it on or off</span></span>

<span data-ttu-id="46603-118">온라인 모임을 Outlook 초대에 연결된 콘텐츠를 비즈니스용 Skype 기본적으로 켜져 있지만 조직의 사용자가 해당 모임에서 콘텐츠를 미리 로드하지 못하게 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46603-118">Being able to preload content attached to an Outlook meeting invitation to Skype for Business Online meetings is turned on by default, but you may need to prevent users in your organization from preloading content in their meetings.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="46603-119">이 설정은 전체 조직에 대해 켜거나 끄기만 할 수 있습니다. 단일 사용자에 대해 켜거나 해제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="46603-119">This setting can only be turned on or off for your entire organization; you can't turn it on or off for a single user.</span></span> 
  
 <span data-ttu-id="46603-120">**이 기능을 해제하기 위해 Windows PowerShell 열고 다음을 합니다.**</span><span class="sxs-lookup"><span data-stu-id="46603-120">**To turn it off, open Windows PowerShell and do the following:**</span></span>
  
```PowerShell
Grant-CsGraphPolicy -PolicyName GraphDisabled 
```

 <span data-ttu-id="46603-121">**다시 설정하려는 경우 다음을 Windows PowerShell 열고 다음을 합니다.**</span><span class="sxs-lookup"><span data-stu-id="46603-121">**If you want to turn it back on, open Windows PowerShell and do the following:**</span></span>
  
```PowerShell
Grant-CsGraphPolicy -PolicyName GraphEnabled 
```

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="46603-122">자세한 정보를 Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="46603-122">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="46603-123">Windows PowerShell 모든 것은 사용자 관리와 사용자가 허용되거나 허용되지 않는 작업을 관리하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="46603-123">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="46603-124">이 Windows PowerShell 여러 작업을 수행할 때 일상적인 작업을 단순화할 수 있는 단일 관리 Microsoft 365 Office 365 비즈니스용 Skype 온라인에서 관리하거나 온라인을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46603-124">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="46603-125">다음 항목을 Windows PowerShell 다음 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="46603-125">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="46603-126">Windows PowerShell 및 비즈니스용 Skype Online 소개</span><span class="sxs-lookup"><span data-stu-id="46603-126">An introduction to Windows PowerShell and Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="46603-127">Windows PowerShell 관리하기 위해 Windows PowerShell 이유 Microsoft 365 Office 365</span><span class="sxs-lookup"><span data-stu-id="46603-127">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Microsoft 365 or Office 365</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
- <span data-ttu-id="46603-128">Windows PowerShell 많은 사용자에 대해 한 Microsoft 365 설정하는 경우와 같이 관리 센터를 사용하는 것만 사용하여 속도, 단순성 및 생산성에 많은 이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46603-128">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="46603-129">다음 항목에서 이러한 이점에 대해 자세히 알아보습니다.</span><span class="sxs-lookup"><span data-stu-id="46603-129">Learn about these advantages in the following topics:</span></span>
    
  - <span data-ttu-id="46603-130">[사용자와 함께 Microsoft 365 또는 Office 365 가장 Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="46603-130">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
  - [<span data-ttu-id="46603-131">온라인 Windows PowerShell 관리하기 위해 비즈니스용 Skype 사용</span><span class="sxs-lookup"><span data-stu-id="46603-131">Using Windows PowerShell to manage Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="46603-132">일반적인 Windows PowerShell 관리 작업을 수행하는 데 비즈니스용 Skype 사용</span><span class="sxs-lookup"><span data-stu-id="46603-132">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
## <a name="related-topics"></a><span data-ttu-id="46603-133">관련 주제</span><span class="sxs-lookup"><span data-stu-id="46603-133">Related topics</span></span>
[<span data-ttu-id="46603-134">비즈니스용 Skype 온라인 설정</span><span class="sxs-lookup"><span data-stu-id="46603-134">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="46603-135">비즈니스용 Skype 사용자가 Skype 연락처를 추가하도록 허용</span><span class="sxs-lookup"><span data-stu-id="46603-135">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

  
