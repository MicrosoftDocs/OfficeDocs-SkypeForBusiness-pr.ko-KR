---
title: Outlook을 사용하여 모임에 콘텐츠를 미리 로드할 수 있도록 설정 또는 해제
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
description: 'Outlook 모임 초대에서 파일 또는 첨부 파일을 사용하여 비즈니스용 Skype 모임에 대해 미리 로드된 콘텐츠를 켜거나 끄는 방법을 참조하세요. '
ms.openlocfilehash: 7a59edb72b72cb42661cdf0e2cb350d7617a47bf
ms.sourcegitcommit: 1613e08da482ff142c990c9c9951abeb873ad964
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/09/2021
ms.locfileid: "50568904"
---
# <a name="turn-on-or-off-allowing-content-to-be-preloaded-for-meetings-using-outlook"></a><span data-ttu-id="3c216-103">Outlook을 사용하여 모임에 콘텐츠를 미리 로드할 수 있도록 설정 또는 해제</span><span class="sxs-lookup"><span data-stu-id="3c216-103">Turn on or off allowing content to be preloaded for meetings using Outlook</span></span>

<span data-ttu-id="3c216-104">사용자는 Outlook 모임 초대에 첨부된 콘텐츠, 파일 또는 첨부 파일을 비즈니스용 Skype 온라인 모임에 미리 로드할 수 있지만 켜거나 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c216-104">Users can preload content, files, or attachments that are attached to an Outlook meeting invitation to a Skype for Business Online meeting, but you can it turn on or off.</span></span> <span data-ttu-id="3c216-105">비즈니스용 Skype Online을 사용하는 모든 조직에 대해 기본적으로 켜져 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c216-105">It's turned on by default for all organizations that are using Skype for Business Online.</span></span> <span data-ttu-id="3c216-106">비즈니스용 Skype 모임에 대한 첨부 파일을 [미리 로드하는 방법을 참조하세요.](https://support.office.com/article/fd3d9f9d-b448-4754-b813-02e49393f251)</span><span class="sxs-lookup"><span data-stu-id="3c216-106">See how to [Preload attachments for a Skype for Business meeting](https://support.office.com/article/fd3d9f9d-b448-4754-b813-02e49393f251).</span></span>
  
> [!NOTE]
> <span data-ttu-id="3c216-107">현재 비즈니스용 Skype Online에는  _MaxContentStorageMB_ 및 _MaxUploadFileMB의_ 온라인 값을 설정하거나 보기 위해 사용할 수 있는 cmdlet이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3c216-107">Currently, there are no cmdlets available in Skype for Business Online for setting or viewing online values for  _MaxContentStorageMB_ and _MaxUploadFileMB_.</span></span> <span data-ttu-id="3c216-108">이러한 구성은 프레미스 배포에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c216-108">They are only available for on-premises deployments.</span></span> <span data-ttu-id="3c216-109">연결된 콘텐츠가  _MaxUploadFileSizeMB를_ 초과하거나 _MaxContentStorageMB_ 제한에 도달하는 경우 콘텐츠가 모임에 업로드되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3c216-109">It's important to know that content won't be uploaded to a meeting if the attached content exceeds the  _MaxUploadFileSizeMB_ or if the _MaxContentStorageMB_ limit is reached.</span></span>
  
## <a name="to-get-you-started"></a><span data-ttu-id="3c216-110">시작을 위해</span><span class="sxs-lookup"><span data-stu-id="3c216-110">To get you started</span></span>

## <a name="start-windows-powershell"></a><span data-ttu-id="3c216-111">시작 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="3c216-111">Start Windows PowerShell</span></span>

> [!NOTE]
> <span data-ttu-id="3c216-112">비즈니스용 Skype Online 커넥터는 현재 최신 Teams PowerShell 모듈의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="3c216-112">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span> <span data-ttu-id="3c216-113">최신 Teams PowerShell 공개 릴리스를 사용하는 경우 비즈니스용 Skype Online 커넥터를 설치할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3c216-113">If you're using the latest Teams PowerShell public release, you don't need to install the Skype for Business Online Connector.</span></span>
1. <span data-ttu-id="3c216-114">Teams [PowerShell 모듈을 설치합니다.](https://docs.microsoft.com/microsoftteams/teams-powershell-install)</span><span class="sxs-lookup"><span data-stu-id="3c216-114">Install the [Teams PowerShell module](https://docs.microsoft.com/microsoftteams/teams-powershell-install).</span></span>
    
2. <span data-ttu-id="3c216-115">명령 Windows PowerShell 프롬프트를 열고 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="3c216-115">Open a Windows PowerShell command prompt and run the following commands:</span></span> 

   ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $userCredential = Get-Credential
   Connect-MicrosoftTeams -Credential $userCredential
   ```

<span data-ttu-id="3c216-116">시작에 대한 자세한 Windows PowerShell 단일 창에서 모든 [Microsoft 365 또는 Office 365](https://technet.microsoft.com/library/dn568015.aspx) 서비스에 연결하거나 Windows PowerShell 에 대한 컴퓨터를 [Windows PowerShell.](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="3c216-116">If you want more information about starting Windows PowerShell, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
  
## <a name="turning-it-on-or-off"></a><span data-ttu-id="3c216-117">켜기 또는 끄기</span><span class="sxs-lookup"><span data-stu-id="3c216-117">Turning it on or off</span></span>

<span data-ttu-id="3c216-118">Outlook 모임 초대에 연결된 콘텐츠를 비즈니스용 Skype Online 모임에 미리 로드할 수 있는 것은 기본적으로 켜져 있지만 조직의 사용자가 모임에서 콘텐츠를 미리 로드하지 못하게 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c216-118">Being able to preload content attached to an Outlook meeting invitation to Skype for Business Online meetings is turned on by default, but you may need to prevent users in your organization from preloading content in their meetings.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="3c216-119">이 설정은 전체 조직에 대해 켜거나 끄기만 할 수 있습니다. 단일 사용자에 대해 켜거나 해제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3c216-119">This setting can only be turned on or off for your entire organization; you can't turn it on or off for a single user.</span></span> 
  
 <span data-ttu-id="3c216-120">**이 기능을 해제하기 위해 Windows PowerShell 열고 다음을 합니다.**</span><span class="sxs-lookup"><span data-stu-id="3c216-120">**To turn it off, open Windows PowerShell and do the following:**</span></span>
  
```PowerShell
Grant-CsGraphPolicy -PolicyName GraphDisabled 
```

 <span data-ttu-id="3c216-121">**다시 설정하려는 경우 다음을 Windows PowerShell 열고 다음을 합니다.**</span><span class="sxs-lookup"><span data-stu-id="3c216-121">**If you want to turn it back on, open Windows PowerShell and do the following:**</span></span>
  
```PowerShell
Grant-CsGraphPolicy -PolicyName GraphEnabled 
```

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="3c216-122">자세한 정보를 Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="3c216-122">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="3c216-123">Windows PowerShell 모든 것은 사용자 관리와 사용자가 허용되거나 허용되지 않는 작업을 관리하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="3c216-123">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="3c216-124">이 Windows PowerShell 여러 작업을 수행할 때 일상적인 작업을 단순화할 수 있는 단일 관리 지점을 사용하여 Microsoft 365 또는 Office 365 및 비즈니스용 Skype Online을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c216-124">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="3c216-125">다음 항목을 Windows PowerShell 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3c216-125">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="3c216-126">Windows PowerShell 및 비즈니스용 Skype Online 소개</span><span class="sxs-lookup"><span data-stu-id="3c216-126">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="3c216-127">Microsoft 365 또는 Office 365를 Windows PowerShell 사용하려는 6 가지 이유</span><span class="sxs-lookup"><span data-stu-id="3c216-127">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Microsoft 365 or Office 365</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="3c216-128">Windows PowerShell 사용자에 대한 설정을 한 번씩 변경하는 경우와 같이 Microsoft 365 관리 센터를 사용하는 경우와 같이 Microsoft 365 관리 센터를 사용하는 것 이상으로 속도, 단순성 및 생산성에 많은 이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c216-128">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="3c216-129">다음 항목에서 이러한 이점에 대해 자세히 알아보습니다.</span><span class="sxs-lookup"><span data-stu-id="3c216-129">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="3c216-130">Microsoft 365 또는 Office 365를 관리하는 가장 좋은 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="3c216-130">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="3c216-131">비즈니스용 skype Windows PowerShell 관리하기 위해 사용</span><span class="sxs-lookup"><span data-stu-id="3c216-131">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="3c216-132">비즈니스용 Windows PowerShell Skype 온라인 관리 작업을 수행하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c216-132">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="3c216-133">관련 항목</span><span class="sxs-lookup"><span data-stu-id="3c216-133">Related topics</span></span>
[<span data-ttu-id="3c216-134">비즈니스용 Skype 온라인 설정</span><span class="sxs-lookup"><span data-stu-id="3c216-134">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="3c216-135">비즈니스용 Skype 사용자가 Skype 연락처를 추가하도록 허용</span><span class="sxs-lookup"><span data-stu-id="3c216-135">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

  
 
