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
description: PowerShell을 사용하여 연락처에 로그인하지 않은 경우에도 비즈니스용 Skype 인스턴트 메시지를 보내는 방법을 배워야 합니다.
ms.openlocfilehash: 12d5a6c736616cb9448dc1f75a6f67424d940d7f
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814607"
---
# <a name="turn-on-or-off-offline-messages-for-admins"></a><span data-ttu-id="07d4f-103">관리자의 오프라인 메시지 설정 또는 해제</span><span class="sxs-lookup"><span data-stu-id="07d4f-103">Turn on or off Offline Messages for admins</span></span>

<span data-ttu-id="07d4f-104">로그인하지 않은 경우에도 연락처에 비즈니스용 Skype IM을 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07d4f-104">You can send Skype for Business IMs to your contacts even if they aren't signed in.</span></span> <span data-ttu-id="07d4f-105">이 기능을 통해 연락처가 연락을 시도한 것을 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07d4f-105">This feature lets your contacts know that you have been trying to reach them.</span></span> <span data-ttu-id="07d4f-106">다른 사람이 온라인이 될 때까지 기다렸다가 메시지를 보내지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="07d4f-106">You don't have to wait until someone is online before sending them a message.</span></span>

<span data-ttu-id="07d4f-107">오프라인 메시지의 경우 다음을 알아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="07d4f-107">For Offline messages, it's important to know:</span></span>

- <span data-ttu-id="07d4f-108">오프라인 메시지는 사용자의 사서함에 보관되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="07d4f-108">Offline messages won't be archived in the user's mailbox.</span></span>

- <span data-ttu-id="07d4f-109">오프라인 메시지는 사용자의 사서함으로 전송되고 비즈니스용 Skype에 로그인하면 사용자에게 통보됩니다.</span><span class="sxs-lookup"><span data-stu-id="07d4f-109">Offline messages will be sent to the user's mailbox, and the user will be notified when they log in to Skype for Business.</span></span>

- <span data-ttu-id="07d4f-110">메시지 받는 사람의 상태가 방해  금지 또는 발표 금지로 설정된 경우 받는 사람의 비즈니스용 Skype 클라이언트에서 보낸 부재 중 메시지를 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="07d4f-110">If the message recipient's status is set to **Do Not Disturb** or **Presenting**, they will receive a missed message that is sent from the recipient's Skype for Business client.</span></span>

<span data-ttu-id="07d4f-111">자세한 내용은 비즈니스용 [Skype에서 오프라인 메시지 사용을 참조하세요.](https://support.office.com/article/ffdc6a43-71a1-40ee-bfcc-640d21324a3d)</span><span class="sxs-lookup"><span data-stu-id="07d4f-111">For more information, see [Use offline messaging in Skype for Business](https://support.office.com/article/ffdc6a43-71a1-40ee-bfcc-640d21324a3d).</span></span>

## <a name="to-get-you-started"></a><span data-ttu-id="07d4f-112">시작</span><span class="sxs-lookup"><span data-stu-id="07d4f-112">To get you started</span></span>

## #

 <span data-ttu-id="07d4f-113">**버전 3.0 Windows PowerShell 실행 중인지 확인**</span><span class="sxs-lookup"><span data-stu-id="07d4f-113">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>

1. <span data-ttu-id="07d4f-114">버전 3.0 이상을 실행하고 있는지 확인: 시작 메뉴를  >  Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="07d4f-114">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>

2. <span data-ttu-id="07d4f-115">웹 창에  _Get-Host를_ 입력하여 **Windows PowerShell** 확인</span><span class="sxs-lookup"><span data-stu-id="07d4f-115">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>

3. <span data-ttu-id="07d4f-116">버전 3.0 이상이 없는 경우 업데이트를 다운로드하여 설치해야 Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="07d4f-116">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell.</span></span> <span data-ttu-id="07d4f-117">버전 [Windows Management Framework 4.0으로](https://go.microsoft.com/fwlink/?LinkId=716845) Windows PowerShell 다운로드하고 업데이트하려면 4.0을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="07d4f-117">See [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0.</span></span> <span data-ttu-id="07d4f-118">메시지가 표시될 때 컴퓨터를 다시 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07d4f-118">Restart your computer when you are prompted.</span></span>

4. <span data-ttu-id="07d4f-119">또한 비즈니스용 Skype Online에 연결하는 원격 Windows PowerShell 세션을 만들 수 있는 Teams용 Windows PowerShell 모듈을 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="07d4f-119">You will also need to install the Windows PowerShell module for Teams that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span>

<span data-ttu-id="07d4f-120">자세한 내용은 단일 365 창에서 모든 [Office 365 서비스에 Windows PowerShell 참조합니다.](https://technet.microsoft.com/library/dn568015.aspx)</span><span class="sxs-lookup"><span data-stu-id="07d4f-120">If you need to know more, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx).</span></span>

## #

 <span data-ttu-id="07d4f-121">**세션 Windows PowerShell 시작**</span><span class="sxs-lookup"><span data-stu-id="07d4f-121">**Start a Windows PowerShell session**</span></span>

1. <span data-ttu-id="07d4f-122">시작 **메뉴에서**  >  **Windows PowerShell.**</span><span class="sxs-lookup"><span data-stu-id="07d4f-122">From the **Start Menu** > **Windows PowerShell**.</span></span>

2. <span data-ttu-id="07d4f-123">다음 **Windows PowerShell** 실행하여 Microsoft 365 또는 Office 365에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="07d4f-123">In the **Windows PowerShell** window, connect to your Microsoft 365 or Office 365 by running:</span></span>

   > [!NOTE]
   > <span data-ttu-id="07d4f-124">비즈니스용 Skype Online Connector는 현재 최신 Teams PowerShell 모듈의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="07d4f-124">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span>
   >
   > <span data-ttu-id="07d4f-125">최신 [Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/)공개 릴리스를 사용하는 경우 비즈니스용 Skype Online Connector를 설치할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="07d4f-125">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

  ```PowerShell
  Import-Module -Name MicrosoftTeams
  $credential = Get-Credential
  $session = New-CsOnlineSession -Credential $credential
  Import-PSSession $session
  ```

<span data-ttu-id="07d4f-126">시작에 대한 자세한 내용은 단일 Windows PowerShell 창에서 모든 [Office 365](https://technet.microsoft.com/library/dn568015.aspx) 서비스에 연결 또는 Windows PowerShell 컴퓨터를 설정하여 [Windows PowerShell.](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="07d4f-126">If you want more information about starting Windows PowerShell, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>

## <a name="turning-on-or-off-offline-im"></a><span data-ttu-id="07d4f-127">오프라인 IM 켜기 또는 끄기</span><span class="sxs-lookup"><span data-stu-id="07d4f-127">Turning on or off Offline IM</span></span>

> [!NOTE]
> <span data-ttu-id="07d4f-128">오프라인 **메시지는** 비즈니스용 Skype 클라이언트의 최신 버전에서만 사용할 수 있으며, 이전의 비즈니스용 Click-to-Run Skype를 사용 중이거나 비즈니스용 Skype 클라이언트를 설치하는 데 \*.msi 파일을 사용한 경우 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="07d4f-128">Offline Messages are **only** available in the latest version of the Click-to-Run Skype for Business client and aren't available when an older Click-to-Run Skype for Business is used or an \*.msi file was used to install the Skype for Business client.</span></span>

<span data-ttu-id="07d4f-129">조직의 사용자에 대해 오프라인 메시지 보내기 사용 또는 사용 안 하도록 설정하려면 _EnableIMAutoArchiving을_ `True` 설정하거나 `False`</span><span class="sxs-lookup"><span data-stu-id="07d4f-129">To enable or disable Offline Messages send Offline Messages for users in your organization, set  _EnableIMAutoArchiving_ to `True` or `False`.</span></span> <span data-ttu-id="07d4f-130">기본적으로 이 설정은 `True` .로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="07d4f-130">By default, this is set to `True`.</span></span>

<span data-ttu-id="07d4f-131">끄기 위해 **Set-CsClientPolicy** cmdlet을 사용하여 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="07d4f-131">To turn it off, use the **Set-CsClientPolicy** cmdlet and run:</span></span>

```PowerShell
Set-CsClientPolicy -Identity Global -EnableIMAutoArchiving $False
```

<span data-ttu-id="07d4f-132">사용자에 대해 오프라인 메시지 보내기 사용 또는 사용 안 하도록 설정하려면 _EnableIMAutoArchiving을_ `True` 설정하거나 `False`</span><span class="sxs-lookup"><span data-stu-id="07d4f-132">To enable or disable Offline Messages send Offline Messages for a user, set  _EnableIMAutoArchiving_ to `True` or `False`.</span></span> <span data-ttu-id="07d4f-133">기본적으로 이 설정은  `True` .로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="07d4f-133">By default, this is set to  `True`.</span></span> <span data-ttu-id="07d4f-134">기존 정책을 사용하거나 아래 예제와 같은 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07d4f-134">You can use an existing policy or create one like the example below.</span></span>


  ```PowerShell
  New-CsClientPolicy -Identity OfflineIM
  Set-CsClientPolicy -Identity OfflineIM -EnableIMAutoArchiving $False
  Grant -CsClientPolicy -Identity "Tony Smith" - PolicyName OfflineIM
  ```

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="07d4f-135">자세한 내용은 Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="07d4f-135">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="07d4f-136">Windows PowerShell 관리는 사용자 및 사용자가 허용되거나 허용되지 않는 작업을 관리하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="07d4f-136">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="07d4f-137">이 Windows PowerShell 여러 작업을 수행할 때 일상적인 작업을 간소화할 수 있는 단일 관리 지점을 사용하여 Microsoft 365 또는 Office 365 및 비즈니스용 Skype Online을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07d4f-137">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="07d4f-138">다음 항목을 Windows PowerShell 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="07d4f-138">To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="07d4f-139">Windows PowerShell 및 Lync Online 소개</span><span class="sxs-lookup"><span data-stu-id="07d4f-139">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [<span data-ttu-id="07d4f-140">Microsoft 365 또는 Office 365를 관리하기 위해 Windows PowerShell 사용할 수 있는 6 가지 이유</span><span class="sxs-lookup"><span data-stu-id="07d4f-140">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Microsoft 365 or Office 365</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)

- <span data-ttu-id="07d4f-141">Windows PowerShell Microsoft 365 관리 센터를 사용하는 경우와 같이 여러 사용자에 대해 한 번씩 설정을 변경하는 경우와 같이 속도, 단순성 및 생산성에 많은 이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07d4f-141">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="07d4f-142">다음 항목에서 이러한 이점에 대해 자세히 배워야 합니다.</span><span class="sxs-lookup"><span data-stu-id="07d4f-142">Learn about these advantages in the following topics:</span></span>

  - [<span data-ttu-id="07d4f-143">Microsoft 365 또는 Office 365를 관리하는 가장 좋은 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="07d4f-143">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)

  - [<span data-ttu-id="07d4f-144">비즈니스 Windows PowerShell 사용하여 비즈니스용 Skype Online 관리</span><span class="sxs-lookup"><span data-stu-id="07d4f-144">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [<span data-ttu-id="07d4f-145">비즈니스용 Windows PowerShell Skype Online 관리 작업을 수행하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07d4f-145">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a><span data-ttu-id="07d4f-146">관련 항목</span><span class="sxs-lookup"><span data-stu-id="07d4f-146">Related topics</span></span>
[<span data-ttu-id="07d4f-147">비즈니스용 Skype 온라인 설정</span><span class="sxs-lookup"><span data-stu-id="07d4f-147">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="07d4f-148">비즈니스용 Skype 사용자가 Skype 연락처를 추가하도록 허용</span><span class="sxs-lookup"><span data-stu-id="07d4f-148">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)


