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
description: PowerShell을 사용하여 연락처에 로그인하지 않은 경우에도 비즈니스용 Skype 인스턴트 메시지를 보내는 방법에 대해 자세히 알아보습니다.
ms.openlocfilehash: ec5aad56ef7557c9b7854c6844d65ff3799d1d1c
ms.sourcegitcommit: 1613e08da482ff142c990c9c9951abeb873ad964
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/09/2021
ms.locfileid: "50568758"
---
# <a name="turn-on-or-off-offline-messages-for-admins"></a><span data-ttu-id="08b5a-103">관리자의 오프라인 메시지 설정 또는 해제</span><span class="sxs-lookup"><span data-stu-id="08b5a-103">Turn on or off Offline Messages for admins</span></span>

<span data-ttu-id="08b5a-104">비즈니스용 Skype IM을 연락처에 로그인하지 않은 경우에도 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08b5a-104">You can send Skype for Business IMs to your contacts even if they aren't signed in.</span></span> <span data-ttu-id="08b5a-105">이 기능을 사용하면 연락처가 연락처에 도달하려고 시도했다는 것을 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08b5a-105">This feature lets your contacts know that you have been trying to reach them.</span></span> <span data-ttu-id="08b5a-106">메시지를 보내기 전에 누군가가 온라인이 될 때까지 기다릴 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="08b5a-106">You don't have to wait until someone is online before sending them a message.</span></span>

<span data-ttu-id="08b5a-107">오프라인 메시지의 경우 다음을 알아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="08b5a-107">For Offline messages, it's important to know:</span></span>

- <span data-ttu-id="08b5a-108">오프라인 메시지는 사용자의 사서함에 보관되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="08b5a-108">Offline messages won't be archived in the user's mailbox.</span></span>

- <span data-ttu-id="08b5a-109">오프라인 메시지는 사용자의 사서함으로 전송되고 비즈니스용 Skype에 로그인하면 사용자에게 알림을 하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="08b5a-109">Offline messages will be sent to the user's mailbox, and the user will be notified when they log in to Skype for Business.</span></span>

- <span data-ttu-id="08b5a-110">메시지 받는 사람의 상태가 방해  금지 또는 발표 금지로 설정되어 있는 경우 받는 사람의 비즈니스용 Skype 클라이언트에서 보낸 부재 중 메시지를 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="08b5a-110">If the message recipient's status is set to **Do Not Disturb** or **Presenting**, they will receive a missed message that is sent from the recipient's Skype for Business client.</span></span>

<span data-ttu-id="08b5a-111">자세한 내용은 [비즈니스용 Skype에서 오프라인 메시징 사용을 참조하세요.](https://support.office.com/article/ffdc6a43-71a1-40ee-bfcc-640d21324a3d)</span><span class="sxs-lookup"><span data-stu-id="08b5a-111">For more information, see [Use offline messaging in Skype for Business](https://support.office.com/article/ffdc6a43-71a1-40ee-bfcc-640d21324a3d).</span></span>

## <a name="to-get-you-started"></a><span data-ttu-id="08b5a-112">시작을 위해</span><span class="sxs-lookup"><span data-stu-id="08b5a-112">To get you started</span></span>

> [!NOTE]
> <span data-ttu-id="08b5a-113">비즈니스용 Skype Online 커넥터는 현재 최신 Teams PowerShell 모듈의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="08b5a-113">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span> <span data-ttu-id="08b5a-114">최신 Teams PowerShell 공개 릴리스를 사용하는 경우 비즈니스용 Skype Online 커넥터를 설치할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="08b5a-114">If you're using the latest Teams PowerShell public release, you don't need to install the Skype for Business Online Connector.</span></span>
1. <span data-ttu-id="08b5a-115">Teams [PowerShell 모듈을 설치합니다.](https://docs.microsoft.com/microsoftteams/teams-powershell-install)</span><span class="sxs-lookup"><span data-stu-id="08b5a-115">Install the [Teams PowerShell module](https://docs.microsoft.com/microsoftteams/teams-powershell-install).</span></span>
    
2. <span data-ttu-id="08b5a-116">명령 Windows PowerShell 프롬프트를 열고 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="08b5a-116">Open a Windows PowerShell command prompt and run the following commands:</span></span> 

   ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $userCredential = Get-Credential
   Connect-MicrosoftTeams -Credential $userCredential
   ```
<span data-ttu-id="08b5a-117">시작에 대한 자세한 Windows PowerShell 단일 창에서 모든 [Office 365](https://technet.microsoft.com/library/dn568015.aspx) 서비스에 연결하거나 Windows PowerShell 에 대해 컴퓨터를 [Windows PowerShell.](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="08b5a-117">If you want more information about starting Windows PowerShell, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>

## <a name="turning-on-or-off-offline-im"></a><span data-ttu-id="08b5a-118">오프라인 IM 켜기 또는 끄기</span><span class="sxs-lookup"><span data-stu-id="08b5a-118">Turning on or off Offline IM</span></span>

> [!NOTE]
> <span data-ttu-id="08b5a-119">오프라인 **메시지는** 비즈니스용 Skype 클라이언트의 최신 버전에서만 사용할 수 있으며 이전 비즈니스용 Skype를 사용하거나 비즈니스용 Skype 클라이언트를 설치하는 데 \*.msi 파일을 사용하는 경우 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="08b5a-119">Offline Messages are **only** available in the latest version of the Click-to-Run Skype for Business client and aren't available when an older Click-to-Run Skype for Business is used or an \*.msi file was used to install the Skype for Business client.</span></span>

<span data-ttu-id="08b5a-120">조직의 사용자에 대한 오프라인 메시지 보내기 오프라인 메시지를 사용하도록 설정하거나 사용하지 않도록 설정하려면  _EnableIMAutoArchiving을_ 또는 `True` `False` 으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="08b5a-120">To enable or disable Offline Messages send Offline Messages for users in your organization, set  _EnableIMAutoArchiving_ to `True` or `False`.</span></span> <span data-ttu-id="08b5a-121">기본적으로 이 설정은 `True` 으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="08b5a-121">By default, this is set to `True`.</span></span>

<span data-ttu-id="08b5a-122">해제하기 위해 **Set-CsClientPolicy** cmdlet을 사용하여 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="08b5a-122">To turn it off, use the **Set-CsClientPolicy** cmdlet and run:</span></span>

```PowerShell
Set-CsClientPolicy -Identity Global -EnableIMAutoArchiving $False
```

<span data-ttu-id="08b5a-123">사용자에 대한 오프라인 메시지를 보내기 위해 오프라인 메시지를 사용하도록 설정하거나 사용하지 않도록 설정하려면  _EnableIMAutoArchiving을_ 또는 `True` `False` 으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="08b5a-123">To enable or disable Offline Messages send Offline Messages for a user, set  _EnableIMAutoArchiving_ to `True` or `False`.</span></span> <span data-ttu-id="08b5a-124">기본적으로 이 설정은  `True` 으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="08b5a-124">By default, this is set to  `True`.</span></span> <span data-ttu-id="08b5a-125">기존 정책을 사용하거나 아래 예제와 같은 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08b5a-125">You can use an existing policy or create one like the example below.</span></span>


  ```PowerShell
  New-CsClientPolicy -Identity OfflineIM
  Set-CsClientPolicy -Identity OfflineIM -EnableIMAutoArchiving $False
  Grant -CsClientPolicy -Identity "Tony Smith" - PolicyName OfflineIM
  ```

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="08b5a-126">자세한 정보를 Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="08b5a-126">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="08b5a-127">Windows PowerShell 모든 것은 사용자 관리와 사용자가 허용되거나 허용되지 않는 작업을 관리하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="08b5a-127">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="08b5a-128">이 Windows PowerShell 여러 작업을 수행할 때 일상적인 작업을 단순화할 수 있는 단일 관리 지점을 사용하여 Microsoft 365 또는 Office 365 및 비즈니스용 Skype Online을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08b5a-128">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="08b5a-129">다음 항목을 Windows PowerShell 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="08b5a-129">To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="08b5a-130">Windows PowerShell 및 비즈니스용 Skype Online 소개</span><span class="sxs-lookup"><span data-stu-id="08b5a-130">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [<span data-ttu-id="08b5a-131">Microsoft 365 또는 Office 365를 Windows PowerShell 사용하려는 6 가지 이유</span><span class="sxs-lookup"><span data-stu-id="08b5a-131">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Microsoft 365 or Office 365</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)

- <span data-ttu-id="08b5a-132">Windows PowerShell 사용자에 대한 설정을 한 번씩 변경하는 경우와 같이 Microsoft 365 관리 센터를 사용하는 경우와 같이 Microsoft 365 관리 센터를 사용하는 것 이상으로 속도, 단순성 및 생산성에 많은 이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08b5a-132">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="08b5a-133">다음 항목에서 이러한 이점에 대해 자세히 알아보습니다.</span><span class="sxs-lookup"><span data-stu-id="08b5a-133">Learn about these advantages in the following topics:</span></span>

  - [<span data-ttu-id="08b5a-134">Microsoft 365 또는 Office 365를 관리하는 가장 좋은 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="08b5a-134">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)

  - [<span data-ttu-id="08b5a-135">비즈니스용 skype Windows PowerShell 관리하기 위해 사용</span><span class="sxs-lookup"><span data-stu-id="08b5a-135">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [<span data-ttu-id="08b5a-136">비즈니스용 Windows PowerShell Skype 온라인 관리 작업을 수행하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08b5a-136">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a><span data-ttu-id="08b5a-137">관련 항목</span><span class="sxs-lookup"><span data-stu-id="08b5a-137">Related topics</span></span>
[<span data-ttu-id="08b5a-138">비즈니스용 Skype 온라인 설정</span><span class="sxs-lookup"><span data-stu-id="08b5a-138">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="08b5a-139">비즈니스용 Skype 사용자가 Skype 연락처를 추가하도록 허용</span><span class="sxs-lookup"><span data-stu-id="08b5a-139">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)
