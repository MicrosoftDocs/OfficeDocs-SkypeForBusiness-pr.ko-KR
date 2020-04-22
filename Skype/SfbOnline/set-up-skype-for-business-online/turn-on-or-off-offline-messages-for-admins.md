---
title: 관리자의 오프라인 메시지 설정 또는 해제
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 8967a77f-caa2-4680-aa22-8faa32c716e4
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
description: 연락처가 PowerShell을 사용 하 여 로그인 하지 않은 경우에도 비즈니스용 Skype 인스턴트 메시지를 보내는 방법에 대해 알아봅니다.
ms.openlocfilehash: 03e92118fd915582030b5259654664121ca96c50
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "43777143"
---
# <a name="turn-on-or-off-offline-messages-for-admins"></a><span data-ttu-id="e8fc4-103">관리자의 오프라인 메시지 설정 또는 해제</span><span class="sxs-lookup"><span data-stu-id="e8fc4-103">Turn on or off Offline Messages for admins</span></span>

<span data-ttu-id="e8fc4-104">로그인 하지 않은 경우에도 비즈니스용 Skype Im을 대화 상대에 게 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8fc4-104">You can send Skype for Business IMs to your contacts even if they aren't signed in.</span></span> <span data-ttu-id="e8fc4-105">이 기능을 통해 귀하의 연락처에 게 연락을 시도 하 고 있음을 알릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8fc4-105">This feature lets your contacts know that you have been trying to reach them.</span></span> <span data-ttu-id="e8fc4-106">메시지를 보내기 전에 다른 사람이 온라인 상태가 될 때까지 기다릴 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e8fc4-106">You don't have to wait until someone is online before sending them a message.</span></span>

<span data-ttu-id="e8fc4-107">오프 라인 메시지의 경우 다음 사항에 유의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8fc4-107">For Offline messages, it's important to know:</span></span>

- <span data-ttu-id="e8fc4-108">오프 라인 메시지는 사용자의 사서함에 보관 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e8fc4-108">Offline messages won't be archived in the user's mailbox.</span></span>

- <span data-ttu-id="e8fc4-109">오프 라인 메시지는 사용자의 사서함으로 보내지며 사용자는 비즈니스용 Skype에 로그인 할 때 알림을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="e8fc4-109">Offline messages will be sent to the user's mailbox, and the user will be notified when they log in to Skype for Business.</span></span>

- <span data-ttu-id="e8fc4-110">메시지 받는 사람의 상태가 방해 금지 또는 표시로 설정 **되 면 받는**사람의 비즈니스용 Skype 클라이언트에서 보낸 부재 **중** 메시지가 수신 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e8fc4-110">If the message recipient's status is set to **Do Not Disturb** or **Presenting**, they will receive a missed message that is sent from the recipient's Skype for Business client.</span></span>

<span data-ttu-id="e8fc4-111">자세한 내용은 [비즈니스용 Skype에서 오프 라인 메시지 사용](https://support.office.com/article/ffdc6a43-71a1-40ee-bfcc-640d21324a3d)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e8fc4-111">For more information, see [Use offline messaging in Skype for Business](https://support.office.com/article/ffdc6a43-71a1-40ee-bfcc-640d21324a3d).</span></span>

## <a name="to-get-you-started"></a><span data-ttu-id="e8fc4-112">시작 하기</span><span class="sxs-lookup"><span data-stu-id="e8fc4-112">To get you started</span></span>

## #

 <span data-ttu-id="e8fc4-113">**Windows PowerShell 버전 3.0 이상을 실행 하 고 있는지 확인**</span><span class="sxs-lookup"><span data-stu-id="e8fc4-113">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>

1. <span data-ttu-id="e8fc4-114">버전 3.0 이상을 실행 하 고 있는지 확인 하려면 **시작 메뉴** > 에서**Windows PowerShell**을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8fc4-114">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>

2. <span data-ttu-id="e8fc4-115">**Windows PowerShell** 창에서 _Get-Host_ 를 입력 하 여 버전을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8fc4-115">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>

3. <span data-ttu-id="e8fc4-116">버전 3.0 이상이 없는 경우 Windows PowerShell 업데이트를 다운로드 하 여 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8fc4-116">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell.</span></span> <span data-ttu-id="e8fc4-117">Windows [Management 프레임 워크 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) 를 참조 하 여 windows PowerShell을 버전 4.0로 다운로드 하 고 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8fc4-117">See [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0.</span></span> <span data-ttu-id="e8fc4-118">메시지가 표시 되 면 컴퓨터를 다시 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8fc4-118">Restart your computer when you are prompted.</span></span>

4. <span data-ttu-id="e8fc4-119">비즈니스용 skype Online에 연결 되는 원격 Windows PowerShell 세션을 만들 수 있는 비즈니스용 Skype Online 용 Windows PowerShell 모듈을 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8fc4-119">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span> <span data-ttu-id="e8fc4-120">이 모듈은 64 비트 컴퓨터 에서만 지원 되며 비즈니스용 [Skype Online 용 Windows PowerShell 모듈](https://go.microsoft.com/fwlink/?LinkId=294688)의 Microsoft 다운로드 센터에서 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8fc4-120">This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688).</span></span> <span data-ttu-id="e8fc4-121">메시지가 표시 되 면 컴퓨터를 다시 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8fc4-121">Restart your computer if you are prompted.</span></span>

<span data-ttu-id="e8fc4-122">자세한 정보를 알고 싶은 경우 [모든 Office 365 서비스에 단일 Windows PowerShell 창으로 연결](https://technet.microsoft.com/library/dn568015.aspx)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e8fc4-122">If you need to know more, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx).</span></span>

## #

 <span data-ttu-id="e8fc4-123">**Windows PowerShell 세션 시작**</span><span class="sxs-lookup"><span data-stu-id="e8fc4-123">**Start a Windows PowerShell session**</span></span>

1. <span data-ttu-id="e8fc4-124">**시작 메뉴** > 에서**Windows PowerShell**을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8fc4-124">From the **Start Menu** > **Windows PowerShell**.</span></span>

2. <span data-ttu-id="e8fc4-125">**Windows PowerShell** 창에서 다음을 실행 하 여 Microsoft 365 또는 Office 365에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8fc4-125">In the **Windows PowerShell** window, connect to your Microsoft 365 or Office 365 by running:</span></span>

    > [!NOTE]
    > <span data-ttu-id="e8fc4-126">비즈니스용 Skype Online Windows PowerShell 모듈을 처음 사용 하는 경우에만 **Import-Module** 명령을 실행 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e8fc4-126">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>

>
  ```PowerShell
  Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
  $credential = Get-Credential
  $session = New-CsOnlineSession -Credential $credential
  Import-PSSession $session
  ```

<span data-ttu-id="e8fc4-127">Windows PowerShell을 시작 하는 방법에 대 한 자세한 내용은 [단일 Windows powershell 창에서 모든 Office 365 서비스에 연결](https://technet.microsoft.com/library/dn568015.aspx) 또는 [Windows Powershell 용 컴퓨터 설정을](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e8fc4-127">If you want more information about starting Windows PowerShell, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>

## <a name="turning-on-or-off-offline-im"></a><span data-ttu-id="e8fc4-128">오프 라인 메신저 대화 설정 또는 해제</span><span class="sxs-lookup"><span data-stu-id="e8fc4-128">Turning on or off Offline IM</span></span>

> [!NOTE]
> <span data-ttu-id="e8fc4-129">오프 라인 메시지는 최신 버전의 간편 실행 비즈니스용 Skype 클라이언트 **에서만** 사용할 수 있으며, 이전에 실행 중인 비즈니스용 skype를 사용 하는 경우에는 사용할 수 없으며 비즈니스용 skype 클라이언트를 설치 하는 데 \* .msi 파일이 사용 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e8fc4-129">Offline Messages are **only** available in the latest version of the Click-to-Run Skype for Business client and aren't available when an older Click-to-Run Skype for Business is used or an \*.msi file was used to install the Skype for Business client.</span></span>

<span data-ttu-id="e8fc4-130">오프 라인 메시지를 설정 하거나 해제 하려면 조직의 사용자에 게 오프 라인 메시지를 _EnableIMAutoArchiving_ 보내려면 EnableIMAutoArchiving `True` 를 `False`또는으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8fc4-130">To enable or disable Offline Messages send Offline Messages for users in your organization, set  _EnableIMAutoArchiving_ to `True` or `False`.</span></span> <span data-ttu-id="e8fc4-131">기본적으로이로 `True`설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e8fc4-131">By default, this is set to `True`.</span></span>

<span data-ttu-id="e8fc4-132">이 기능을 해제 하려면 **Set-CsClientPolicy** cmdlet을 사용 하 여 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8fc4-132">To turn it off, use the **Set-CsClientPolicy** cmdlet and run:</span></span>

```PowerShell
Set-CsClientPolicy -Identity Global -EnableIMAutoArchiving $False
```

<span data-ttu-id="e8fc4-133">오프 라인 메시지를 설정 하거나 해제 하려면 사용자에 게 오프 라인 메시지 _EnableIMAutoArchiving_ 를 보내려면 `True` EnableIMAutoArchiving `False`를 또는으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8fc4-133">To enable or disable Offline Messages send Offline Messages for a user, set  _EnableIMAutoArchiving_ to `True` or `False`.</span></span> <span data-ttu-id="e8fc4-134">기본적으로이로 `True`설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e8fc4-134">By default, this is set to  `True`.</span></span> <span data-ttu-id="e8fc4-135">기존 정책을 사용 하거나 아래 예제와 같은 항목을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8fc4-135">You can use an existing policy or create one like the example below.</span></span>


  ```PowerShell
  New-CsClientPolicy -Identity OfflineIM
  Set-CsClientPolicy -Identity OfflineIM -EnableIMAutoArchiving $False
  Grant -CsClientPolicy -Identity "Tony Smith" - PolicyName OfflineIM
  ```

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="e8fc4-136">Windows PowerShell에 대 한 자세한 정보를 확인 하 고 싶으신가요?</span><span class="sxs-lookup"><span data-stu-id="e8fc4-136">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="e8fc4-137">Windows PowerShell은 사용자 및 허용 되지 않거나 수행할 수 있는 사용자를 관리 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8fc4-137">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="e8fc4-138">Windows PowerShell을 사용 하면 여러 작업을 수행할 때 일상 업무를 단순화할 수 있는 단일 관리 지점을 사용 하 여 Office 365 및 비즈니스용 Skype Online을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8fc4-138">With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="e8fc4-139">Windows PowerShell을 시작 하려면 다음 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e8fc4-139">To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="e8fc4-140">Windows PowerShell 및 Lync Online 소개</span><span class="sxs-lookup"><span data-stu-id="e8fc4-140">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [<span data-ttu-id="e8fc4-141">Windows PowerShell을 사용 하 여 Office 365를 관리 하는 데 필요한 여섯 가지 이유</span><span class="sxs-lookup"><span data-stu-id="e8fc4-141">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Office 365</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)

- <span data-ttu-id="e8fc4-142">Windows PowerShell에는 한 번에 여러 사용자의 설정을 변경 하는 경우와 같이 Microsoft 365 관리 센터를 사용 하는 경우에만 속도, 단순성, 생산성 등 다양 한 이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8fc4-142">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="e8fc4-143">다음 항목에서 이러한 이점에 대해 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="e8fc4-143">Learn about these advantages in the following topics:</span></span>

  - [<span data-ttu-id="e8fc4-144">Windows PowerShell을 사용 하 여 Office 365를 관리 하는 가장 좋은 방법</span><span class="sxs-lookup"><span data-stu-id="e8fc4-144">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)

  - [<span data-ttu-id="e8fc4-145">Windows PowerShell을 사용 하 여 비즈니스용 Skype Online 관리</span><span class="sxs-lookup"><span data-stu-id="e8fc4-145">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [<span data-ttu-id="e8fc4-146">Windows PowerShell을 사용 하 여 일반적인 비즈니스용 Skype Online 관리 작업 수행</span><span class="sxs-lookup"><span data-stu-id="e8fc4-146">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a><span data-ttu-id="e8fc4-147">관련 항목</span><span class="sxs-lookup"><span data-stu-id="e8fc4-147">Related topics</span></span>
[<span data-ttu-id="e8fc4-148">비즈니스용 Skype 온라인 설정</span><span class="sxs-lookup"><span data-stu-id="e8fc4-148">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="e8fc4-149">비즈니스용 Skype 사용자가 Skype 연락처를 추가하도록 허용</span><span class="sxs-lookup"><span data-stu-id="e8fc4-149">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)


