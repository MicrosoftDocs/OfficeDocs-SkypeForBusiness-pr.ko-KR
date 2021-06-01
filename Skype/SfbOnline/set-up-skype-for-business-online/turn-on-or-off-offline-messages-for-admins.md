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
description: PowerShell을 사용하여 연락처에 비즈니스용 Skype 경우에도 인스턴트 메시지를 보내는 방법에 대해 자세히 알아보습니다.
ms.openlocfilehash: fc340cff109d33a3a5afeaf6b1b2b09ae7f6ba3b
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52239164"
---
# <a name="turn-on-or-off-offline-messages-for-admins"></a><span data-ttu-id="9c24b-103">관리자의 오프라인 메시지 설정 또는 해제</span><span class="sxs-lookup"><span data-stu-id="9c24b-103">Turn on or off Offline Messages for admins</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

<span data-ttu-id="9c24b-104">로그인하지 않은 비즈니스용 Skype 연락처에 IM을 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c24b-104">You can send Skype for Business IMs to your contacts even if they aren't signed in.</span></span> <span data-ttu-id="9c24b-105">이 기능을 사용하면 연락처가 연락처에 도달하려고 시도했다는 것을 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c24b-105">This feature lets your contacts know that you have been trying to reach them.</span></span> <span data-ttu-id="9c24b-106">메시지를 보내기 전에 누군가가 온라인이 될 때까지 기다릴 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9c24b-106">You don't have to wait until someone is online before sending them a message.</span></span>

<span data-ttu-id="9c24b-107">오프라인 메시지의 경우 다음을 알아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c24b-107">For Offline messages, it's important to know:</span></span>

- <span data-ttu-id="9c24b-108">오프라인 메시지는 사용자의 사서함에 보관되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9c24b-108">Offline messages won't be archived in the user's mailbox.</span></span>

- <span data-ttu-id="9c24b-109">오프라인 메시지는 사용자의 사서함으로 전송되고 사용자가 로그인하면 사용자에게 비즈니스용 Skype.</span><span class="sxs-lookup"><span data-stu-id="9c24b-109">Offline messages will be sent to the user's mailbox, and the user will be notified when they log in to Skype for Business.</span></span>

- <span data-ttu-id="9c24b-110">메시지 받는 사람의 상태가 방해  금지 또는 발표 금지로 설정되어 있는 경우 받는 사람의 클라이언트에서 보낸 부재 중 메시지를 비즈니스용 Skype.</span><span class="sxs-lookup"><span data-stu-id="9c24b-110">If the message recipient's status is set to **Do Not Disturb** or **Presenting**, they will receive a missed message that is sent from the recipient's Skype for Business client.</span></span>

<span data-ttu-id="9c24b-111">자세한 내용은 에서 오프라인 [메시징 사용을 비즈니스용 Skype.](https://support.office.com/article/ffdc6a43-71a1-40ee-bfcc-640d21324a3d)</span><span class="sxs-lookup"><span data-stu-id="9c24b-111">For more information, see [Use offline messaging in Skype for Business](https://support.office.com/article/ffdc6a43-71a1-40ee-bfcc-640d21324a3d).</span></span>

## <a name="to-get-you-started"></a><span data-ttu-id="9c24b-112">시작을 위해</span><span class="sxs-lookup"><span data-stu-id="9c24b-112">To get you started</span></span>

> [!NOTE]
> <span data-ttu-id="9c24b-113">비즈니스용 Skype 온라인 커넥터는 현재 최신 PowerShell Teams 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="9c24b-113">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span> <span data-ttu-id="9c24b-114">최신 PowerShell 공개 Teams 사용하는 경우 온라인 커넥터를 비즈니스용 Skype 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9c24b-114">If you're using the latest Teams PowerShell public release, you don't need to install the Skype for Business Online Connector.</span></span>
1. <span data-ttu-id="9c24b-115">[PowerShell Teams 설치합니다.](/microsoftteams/teams-powershell-install)</span><span class="sxs-lookup"><span data-stu-id="9c24b-115">Install the [Teams PowerShell module](/microsoftteams/teams-powershell-install).</span></span>
    
2. <span data-ttu-id="9c24b-116">명령 Windows PowerShell 프롬프트를 열고 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="9c24b-116">Open a Windows PowerShell command prompt and run the following commands:</span></span> 

   ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $userCredential = Get-Credential
   Connect-MicrosoftTeams -Credential $userCredential
   ```
<span data-ttu-id="9c24b-117">시작에 대한 자세한 Windows PowerShell 단일 커넥트 Office 365 [](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window) 모든 서비스에 대한 Windows PowerShell 을 참조하거나 에 대한 컴퓨터를 [Windows PowerShell.](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="9c24b-117">If you want more information about starting Windows PowerShell, see [Connect to all Office 365 services in a single Windows PowerShell window](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>

## <a name="turning-on-or-off-offline-im"></a><span data-ttu-id="9c24b-118">오프라인 IM 켜기 또는 끄기</span><span class="sxs-lookup"><span data-stu-id="9c24b-118">Turning on or off Offline IM</span></span>

> [!NOTE]
> <span data-ttu-id="9c24b-119">오프라인 메시지는  최신 버전의 Click-to-Run 비즈니스용 Skype 클라이언트에서만 사용할 수 있으며 이전 클릭-실행 비즈니스용 Skype 또는 \*.msi 파일을 사용하여 클라이언트를 설치하는 비즈니스용 Skype 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9c24b-119">Offline Messages are **only** available in the latest version of the Click-to-Run Skype for Business client and aren't available when an older Click-to-Run Skype for Business is used or an \*.msi file was used to install the Skype for Business client.</span></span>

<span data-ttu-id="9c24b-120">조직의 사용자에 대한 오프라인 메시지 보내기 오프라인 메시지를 사용하도록 설정하거나 사용하지 않도록 설정하려면  _EnableIMAutoArchiving을_ 또는 `True` `False` 으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="9c24b-120">To enable or disable Offline Messages send Offline Messages for users in your organization, set  _EnableIMAutoArchiving_ to `True` or `False`.</span></span> <span data-ttu-id="9c24b-121">기본적으로 이 설정은 `True` 으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="9c24b-121">By default, this is set to `True`.</span></span>

<span data-ttu-id="9c24b-122">해제하기 위해 **Set-CsClientPolicy** cmdlet을 사용하여 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="9c24b-122">To turn it off, use the **Set-CsClientPolicy** cmdlet and run:</span></span>

```PowerShell
Set-CsClientPolicy -Identity Global -EnableIMAutoArchiving $False
```

<span data-ttu-id="9c24b-123">사용자에 대한 오프라인 메시지를 보내기 위해 오프라인 메시지를 사용하도록 설정하거나 사용하지 않도록 설정하려면  _EnableIMAutoArchiving을_ 또는 `True` `False` 으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="9c24b-123">To enable or disable Offline Messages send Offline Messages for a user, set  _EnableIMAutoArchiving_ to `True` or `False`.</span></span> <span data-ttu-id="9c24b-124">기본적으로 이 설정은  `True` 으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="9c24b-124">By default, this is set to  `True`.</span></span> <span data-ttu-id="9c24b-125">기존 정책을 사용하거나 아래 예제와 같은 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c24b-125">You can use an existing policy or create one like the example below.</span></span>


  ```PowerShell
  New-CsClientPolicy -Identity OfflineIM
  Set-CsClientPolicy -Identity OfflineIM -EnableIMAutoArchiving $False
  Grant -CsClientPolicy -Identity "Tony Smith" - PolicyName OfflineIM
  ```

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="9c24b-126">자세한 정보를 Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="9c24b-126">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="9c24b-127">Windows PowerShell 모든 것은 사용자 관리와 사용자가 허용되거나 허용되지 않는 작업을 관리하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="9c24b-127">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="9c24b-128">이 Windows PowerShell 여러 작업을 수행할 때 일상적인 작업을 단순화할 수 있는 단일 관리 Microsoft 365 Office 365 비즈니스용 Skype 온라인에서 관리하거나 온라인을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c24b-128">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="9c24b-129">다음 항목을 Windows PowerShell 다음 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9c24b-129">To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="9c24b-130">Windows PowerShell 및 비즈니스용 Skype Online 소개</span><span class="sxs-lookup"><span data-stu-id="9c24b-130">An introduction to Windows PowerShell and Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

  - [<span data-ttu-id="9c24b-131">Windows PowerShell 관리하기 위해 Windows PowerShell 이유 Microsoft 365 Office 365</span><span class="sxs-lookup"><span data-stu-id="9c24b-131">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Microsoft 365 or Office 365</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

- <span data-ttu-id="9c24b-132">Windows PowerShell 많은 사용자에 대해 한 Microsoft 365 설정하는 경우와 같이 관리 센터를 사용하는 것만 사용하여 속도, 단순성 및 생산성에 많은 이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c24b-132">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="9c24b-133">다음 항목에서 이러한 이점에 대해 자세히 알아보습니다.</span><span class="sxs-lookup"><span data-stu-id="9c24b-133">Learn about these advantages in the following topics:</span></span>

  - <span data-ttu-id="9c24b-134">[사용자와 함께 Microsoft 365 또는 Office 365 가장 Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="9c24b-134">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>

  - [<span data-ttu-id="9c24b-135">온라인 Windows PowerShell 관리하기 위해 비즈니스용 Skype 사용</span><span class="sxs-lookup"><span data-stu-id="9c24b-135">Using Windows PowerShell to manage Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

  - [<span data-ttu-id="9c24b-136">일반적인 Windows PowerShell 관리 작업을 수행하는 데 비즈니스용 Skype 사용</span><span class="sxs-lookup"><span data-stu-id="9c24b-136">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

## <a name="related-topics"></a><span data-ttu-id="9c24b-137">관련 항목</span><span class="sxs-lookup"><span data-stu-id="9c24b-137">Related topics</span></span>
[<span data-ttu-id="9c24b-138">비즈니스용 Skype 온라인 설정</span><span class="sxs-lookup"><span data-stu-id="9c24b-138">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="9c24b-139">비즈니스용 Skype 사용자가 Skype 연락처를 추가하도록 허용</span><span class="sxs-lookup"><span data-stu-id="9c24b-139">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)
