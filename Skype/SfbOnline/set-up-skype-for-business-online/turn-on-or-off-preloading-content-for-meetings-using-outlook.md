---
title: Outlook을 사용 하 여 모임에 대 한 콘텐츠 미리 로드 허용 설정 또는 해제
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
description: 'Outlook 모임 초대에서 파일이 나 첨부 파일을 사용 하 여 비즈니스용 Skype 모임에서 미리 로드 된 콘텐츠를 설정 하거나 해제 하는 방법을 알아봅니다. '
ms.openlocfilehash: 66373c3609584efb34d54ef4ad9331af608b5a81
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41706303"
---
# <a name="turn-on-or-off-allowing-content-to-be-preloaded-for-meetings-using-outlook"></a><span data-ttu-id="3a8a8-103">Outlook을 사용 하 여 모임에 대 한 콘텐츠 미리 로드 허용 설정 또는 해제</span><span class="sxs-lookup"><span data-stu-id="3a8a8-103">Turn on or off allowing content to be preloaded for meetings using Outlook</span></span>

<span data-ttu-id="3a8a8-104">사용자는 비즈니스용 Skype Online 모임에 Outlook 모임 초대에 연결 된 콘텐츠, 파일 또는 첨부 파일을 미리 로드할 수 있지만, 설정 하거나 해제할 수는 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a8a8-104">Users can preload content, files, or attachments that are attached to an Outlook meeting invitation to a Skype for Business Online meeting, but you can it turn on or off.</span></span> <span data-ttu-id="3a8a8-105">비즈니스용 Skype Online을 사용 하는 모든 조직에서 기본적으로 설정 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a8a8-105">It's turned on by default for all organizations that are using Skype for Business Online.</span></span> <span data-ttu-id="3a8a8-106">[비즈니스용 Skype 모임에 대 한 첨부 파일을 미리 로드](https://support.office.com/article/fd3d9f9d-b448-4754-b813-02e49393f251)하는 방법에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="3a8a8-106">See how to [Preload attachments for a Skype for Business meeting](https://support.office.com/article/fd3d9f9d-b448-4754-b813-02e49393f251).</span></span>
  
> [!NOTE]
> <span data-ttu-id="3a8a8-107">현재는 비즈니스용 Skype Online에서 _Maxcontentstoragemb_ 및 _MaxUploadFileMB_의 온라인 값을 설정 하거나 볼 수 있는 cmdlet이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3a8a8-107">Currently, there are no cmdlets available in Skype for Business Online for setting or viewing online values for  _MaxContentStorageMB_ and _MaxUploadFileMB_.</span></span> <span data-ttu-id="3a8a8-108">온-프레미스 배포에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a8a8-108">They are only available for on-premises deployments.</span></span> <span data-ttu-id="3a8a8-109">첨부 된 콘텐츠가 _MaxUploadFileSizeMB_ 를 초과 하거나 _Maxcontentstoragemb_ 제한에 도달 하는 경우 콘텐츠가 모임에 업로드 되지 않는다는 것을 알아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a8a8-109">It's important to know that content won't be uploaded to a meeting if the attached content exceeds the  _MaxUploadFileSizeMB_ or if the _MaxContentStorageMB_ limit is reached.</span></span>
  
## <a name="to-get-you-started"></a><span data-ttu-id="3a8a8-110">시작 하기</span><span class="sxs-lookup"><span data-stu-id="3a8a8-110">To get you started</span></span>

### 

 <span data-ttu-id="3a8a8-111">**Windows PowerShell 버전 3.0 이상을 실행 하 고 있는지 확인**</span><span class="sxs-lookup"><span data-stu-id="3a8a8-111">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
  
1. <span data-ttu-id="3a8a8-112">버전 3.0 이상을 실행 하 고 있는지 확인 하려면 **시작 메뉴** > 에서**Windows PowerShell**을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a8a8-112">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="3a8a8-113">**Windows PowerShell** 창에서 _Get-Host_ 를 입력 하 여 버전을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a8a8-113">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="3a8a8-114">버전 3.0 이상이 없는 경우 Windows PowerShell 업데이트를 다운로드 하 여 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a8a8-114">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell.</span></span> <span data-ttu-id="3a8a8-115">Windows [Management 프레임 워크 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) 를 참조 하 여 windows PowerShell을 버전 4.0로 다운로드 하 고 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a8a8-115">See [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0.</span></span> <span data-ttu-id="3a8a8-116">메시지가 표시 되 면 컴퓨터를 다시 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a8a8-116">Restart your computer when you are prompted.</span></span>
    
4. <span data-ttu-id="3a8a8-117">비즈니스용 skype Online에 연결 되는 원격 Windows PowerShell 세션을 만들 수 있는 비즈니스용 Skype Online 용 Windows PowerShell 모듈을 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a8a8-117">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span> <span data-ttu-id="3a8a8-118">이 모듈은 64 비트 컴퓨터 에서만 지원 되며 비즈니스용 [Skype Online 용 Windows PowerShell 모듈](https://go.microsoft.com/fwlink/?LinkId=294688)의 Microsoft 다운로드 센터에서 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a8a8-118">This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688).</span></span> <span data-ttu-id="3a8a8-119">메시지가 표시 되 면 컴퓨터를 다시 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a8a8-119">Restart your computer if you are prompted.</span></span>
    
<span data-ttu-id="3a8a8-120">자세한 정보를 알고 싶은 경우 [모든 Office 365 서비스에 단일 Windows PowerShell 창으로 연결](https://technet.microsoft.com/library/dn568015.aspx)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3a8a8-120">If you need to know more, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx).</span></span>
  
### 

 <span data-ttu-id="3a8a8-121">**Windows PowerShell 세션 시작**</span><span class="sxs-lookup"><span data-stu-id="3a8a8-121">**Start a Windows PowerShell session**</span></span>
  
1. <span data-ttu-id="3a8a8-122">**시작 메뉴** > 에서**Windows PowerShell**을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a8a8-122">From the **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="3a8a8-123">**Windows PowerShell** 창에서 다음을 실행 하 여 Office 365 조직에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a8a8-123">In the **Windows PowerShell** window, connect to your Office 365 organization by running:</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="3a8a8-124">비즈니스용 Skype Online Windows PowerShell 모듈을 처음 사용 하는 경우에만 **Import-Module** 명령을 실행 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3a8a8-124">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>
  
```PowerShell
Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
$credential = Get-Credential
$session = New-CsOnlineSession -Credential $credential
Import-PSSession $session
```

<span data-ttu-id="3a8a8-125">Windows PowerShell을 시작 하는 방법에 대 한 자세한 내용은 [단일 Windows powershell 창에서 모든 Office 365 서비스에 연결](https://technet.microsoft.com/library/dn568015.aspx) 또는 [Windows Powershell 용 컴퓨터 설정을](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3a8a8-125">If you want more information about starting Windows PowerShell, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
  
## <a name="turning-it-on-or-off"></a><span data-ttu-id="3a8a8-126">설정 또는 해제</span><span class="sxs-lookup"><span data-stu-id="3a8a8-126">Turning it on or off</span></span>

<span data-ttu-id="3a8a8-127">Outlook 모임 초대에 첨부 된 콘텐츠를 비즈니스용 Skype Online 모임에 미리 로드할 수 있지만, 조직의 사용자가 모임에서 콘텐츠를 미리 로드 하지 못하도록 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a8a8-127">Being able to preload content attached to an Outlook meeting invitation to Skype for Business Online meetings is turned on by default, but you may need to prevent users in your organization from preloading content in their meetings.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="3a8a8-128">이 설정은 조직 전체에 대해 설정 하거나 해제할 수 있습니다. 단일 사용자에 대해이 기능을 설정 하거나 해제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3a8a8-128">This setting can only be turned on or off for your entire organization; you can't turn it on or off for a single user.</span></span> 
  
 <span data-ttu-id="3a8a8-129">**해제 하려면 Windows PowerShell을 열고 다음을 수행 합니다.**</span><span class="sxs-lookup"><span data-stu-id="3a8a8-129">**To turn it off, open Windows PowerShell and do the following:**</span></span>
  
```PowerShell
Grant-CsGraphPolicy -PolicyName GraphDisabled 
```

 <span data-ttu-id="3a8a8-130">**다시 설정 하려면 Windows PowerShell을 열고 다음을 수행 합니다.**</span><span class="sxs-lookup"><span data-stu-id="3a8a8-130">**If you want to turn it back on, open Windows PowerShell and do the following:**</span></span>
  
```PowerShell
Grant-CsGraphPolicy -PolicyName GraphEnabled 
```

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="3a8a8-131">Windows PowerShell에 대 한 자세한 정보를 확인 하 고 싶으신가요?</span><span class="sxs-lookup"><span data-stu-id="3a8a8-131">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="3a8a8-132">Windows PowerShell은 사용자 및 허용 되지 않거나 수행할 수 있는 사용자를 관리 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a8a8-132">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="3a8a8-133">Windows PowerShell을 사용 하면 여러 작업을 수행할 때 일상 업무를 단순화할 수 있는 단일 관리 지점을 사용 하 여 Office 365 및 비즈니스용 Skype Online을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a8a8-133">With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="3a8a8-134">Windows PowerShell을 시작 하려면 다음 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3a8a8-134">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="3a8a8-135">Windows PowerShell 및 Lync Online 소개</span><span class="sxs-lookup"><span data-stu-id="3a8a8-135">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="3a8a8-136">Windows PowerShell을 사용 하 여 Office 365를 관리 하는 데 필요한 여섯 가지 이유</span><span class="sxs-lookup"><span data-stu-id="3a8a8-136">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Office 365</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="3a8a8-137">Windows PowerShell에는 한 번에 여러 사용자의 설정을 변경 하는 경우와 같이 Microsoft 365 관리 센터를 사용 하는 경우에만 속도, 단순성, 생산성 등 다양 한 이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a8a8-137">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="3a8a8-138">다음 항목에서 이러한 이점에 대해 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="3a8a8-138">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="3a8a8-139">Windows PowerShell을 사용 하 여 Office 365를 관리 하는 가장 좋은 방법</span><span class="sxs-lookup"><span data-stu-id="3a8a8-139">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="3a8a8-140">Windows PowerShell을 사용 하 여 비즈니스용 Skype Online 관리</span><span class="sxs-lookup"><span data-stu-id="3a8a8-140">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="3a8a8-141">Windows PowerShell을 사용 하 여 일반적인 비즈니스용 Skype Online 관리 작업 수행</span><span class="sxs-lookup"><span data-stu-id="3a8a8-141">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="3a8a8-142">관련 주제</span><span class="sxs-lookup"><span data-stu-id="3a8a8-142">Related topics</span></span>
[<span data-ttu-id="3a8a8-143">비즈니스용 Skype 온라인 설정</span><span class="sxs-lookup"><span data-stu-id="3a8a8-143">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="3a8a8-144">비즈니스용 Skype 사용자가 Skype 연락처를 추가하도록 허용</span><span class="sxs-lookup"><span data-stu-id="3a8a8-144">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

  
 
