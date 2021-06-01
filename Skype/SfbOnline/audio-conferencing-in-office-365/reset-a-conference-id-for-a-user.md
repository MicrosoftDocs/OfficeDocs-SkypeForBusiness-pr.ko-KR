---
title: 온라인에서 사용자에 대한 비즈니스용 Skype 다시 설정
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 6e12242c-55f7-4bf4-90d7-0f36c0326b8e
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: '온라인에서 사용자의 모임 모임 ID를 다시 설정하고 비즈니스용 Skype 업데이트 및 마이그레이션 도구에 대한 링크를 얻을 수 있는 단계에 대해 알아보십시오. '
ms.openlocfilehash: 24037de3849ae54920777636e7eb745671ae2f57
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52237774"
---
# <a name="reset-a-conference-id-for-a-user-in-skype-for-business-online"></a><span data-ttu-id="c7e4a-103">온라인에서 사용자에 대한 비즈니스용 Skype 다시 설정</span><span class="sxs-lookup"><span data-stu-id="c7e4a-103">Reset a conference ID for a user in Skype for Business Online</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!NOTE]
> <span data-ttu-id="c7e4a-104">에서 회의 ID를 다시 설정하는 Microsoft Teams 의 사용자에 대한 회의 [ID 재설정을 Microsoft Teams.](/MicrosoftTeams/reset-a-conference-id-for-a-user-in-teams)</span><span class="sxs-lookup"><span data-stu-id="c7e4a-104">For information about resetting conference ID in Microsoft Teams, see [Reset a conference ID for a user in Microsoft Teams](/MicrosoftTeams/reset-a-conference-id-for-a-user-in-teams).</span></span>

<span data-ttu-id="c7e4a-105">동적 회의 ID는 전화 접속 전화 번호와 함께 모임 초대 맨 아래에 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7e4a-105">A dynamic conference ID is included at the bottom of meeting invitations along with the dial-in phone numbers that can be used by callers to call in to a meeting.</span></span> <span data-ttu-id="c7e4a-106">사용자가 전화 번호에 전화를 걸면 모임의 자동 참석자가 전화 회의에 참석할 수 있도록 발신자에게 이 회의 ID를 입력하도록 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="c7e4a-106">When the user dials the phone number, the auto attendant for the meeting will ask the caller to enter this conference ID so they can attend the meeting.</span></span>
  
> [!NOTE]
> <span data-ttu-id="c7e4a-107">회의 공급자가 Microsoft인 경우 사용자의 회의 신분은 동적 전용으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="c7e4a-107">If your conferencing provider is Microsoft, your users' conference IDs are set to Dynamic Only.</span></span> <span data-ttu-id="c7e4a-108">변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c7e4a-108">This cannot be changed.</span></span> <span data-ttu-id="c7e4a-109">컨퍼런스 신분은 오디오 회의에 사용하도록 설정된 비즈니스용 Skype 사용자에 대해 자동으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="c7e4a-109">Conference IDs are automatically set only for Skype for Business users enabled for Audio Conferencing.</span></span> 

## <a name="resetting-the-conference-id-for-a-user"></a><span data-ttu-id="c7e4a-110">사용자에 대한 회의 ID 재설정</span><span class="sxs-lookup"><span data-stu-id="c7e4a-110">Resetting the conference ID for a user</span></span>
   
1. <span data-ttu-id="c7e4a-111">비즈니스용 Skype 관리 센터에서 오디오 회의 사용자를 클릭하고 사용자를 선택한 다음 회의 ID 아래의 작업 창에서 다시  >  설정 **을 클릭합니다.** </span><span class="sxs-lookup"><span data-stu-id="c7e4a-111">In the **Skype for Business admin center**, click **Audio conferencing** > **Users**, select a user, and then in the Action pane under **Conference ID** click **Reset**.</span></span>
    
2. <span data-ttu-id="c7e4a-112">회의 **ID 재설정 창에서** 예 **를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="c7e4a-112">In the **Reset conference ID?** window, click **Yes**.</span></span> <span data-ttu-id="c7e4a-113">회의 ID가 자동으로 생성되고 새 회의 ID가 있는 사용자에게 전자 메일이 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="c7e4a-113">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span> <span data-ttu-id="c7e4a-114">기본적으로 전자 메일은 사용자에게 전송되지만 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7e4a-114">By default, emails are sent to users, but this can be turned off.</span></span>
    
> [!NOTE]
> <span data-ttu-id="c7e4a-115">회의 ID를 다시 설정하면 새 회의 ID가 있는 전자 메일이 사용자에게 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="c7e4a-115">After you reset the conference ID, an email with the new conference ID will be sent to the user.</span></span> <span data-ttu-id="c7e4a-116">이 전자 메일은 기본 전자 메일 주소로 전송됩니다. 대부분의 경우 해당 전자 메일 Microsoft 365 Office 365 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7e4a-116">This email will be sent to the primary email address, in many cases, their Microsoft 365 or Office 365 mailbox.</span></span> <span data-ttu-id="c7e4a-117">전자 메일에는 새 회의 ID, 기본 전화 접속 전화 번호 및 모임 업데이트 도구를 사용하여 기존 모임을 비즈니스용 Skype 지침이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7e4a-117">The email contains the new conference ID, default dial-in phone number(s) and instructions to use the Skype for Business Meeting Update Tool to update existing meetings.</span></span> 
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="what-else-should-i-know"></a><span data-ttu-id="c7e4a-118">다른 무엇을 알아야 하나요?</span><span class="sxs-lookup"><span data-stu-id="c7e4a-118">What else should I know?</span></span>

- <span data-ttu-id="c7e4a-119">작업 창의 사용자에 대한 전자 메일을 통해 회의 정보 보내기를 클릭하여 회의 ID 및 전화  접속 전화 번호가 포함된 전자 메일에서 사용자에게 모든 회의 정보를 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7e4a-119">You can send all of the conferencing information to the user in an email that includes the conference ID and dial-in phone numbers by clicking **Send conference info via email** for the user in the Action pane.</span></span> <span data-ttu-id="c7e4a-120">PIN을 보내지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c7e4a-120">It doesn't send the PIN.</span></span>
    
- <span data-ttu-id="c7e4a-121">회의 ID에는 7자리 숫자가 포함되어 있으며 관리 센터에서 또는 비즈니스용 Skype 사용하여 해당 길이를 변경할 수 Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c7e4a-121">A conference ID will contain 7 digits, and you can't change its length in the Skype for Business admin center or by using Windows PowerShell.</span></span>
    
- <span data-ttu-id="c7e4a-122">다시 설정한 후 회의 ID 에 나열된 새 회의 **ID를 볼 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="c7e4a-122">After it has been reset, you can see the new conference ID listed under **Conference ID**.</span></span>
    
- <span data-ttu-id="c7e4a-123">오디오 회의용 사용자의 회의 ID는 사용자 페이지에서 사용자를 선택할 때 오디오 회의  아래 작업 창 아래쪽에서 볼 **수** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7e4a-123">The conference ID for a user for audio conferencing can be viewed at the bottom of the Action pane under **Audio conferencing** when you select the user on the **Users** page.</span></span>
    
- <span data-ttu-id="c7e4a-124">새 회의 ID를 만든 후 이전 회의 ID는 발신자에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c7e4a-124">After a new conference ID is created, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="c7e4a-125">새 회의 ID가 초대에 추가될 수 있도록 기존 모임 초대를 다시 계획할 수 있도록 사용자에게 알려야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7e4a-125">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> <span data-ttu-id="c7e4a-126">사용자는 모임 도구를 사용하여 비즈니스용 Skype 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7e4a-126">The users can use Skype for Business Meeting Tool to update their existing meetings.</span></span> <span data-ttu-id="c7e4a-127">모임 업데이트 도구를 다운로드, 설치 및 비즈니스용 Skype 방법을 참조하려면 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c7e4a-127">To see how to download, install, and run the Skype for Business Meeting Update Tool, see:</span></span>
    
  - [<span data-ttu-id="c7e4a-128">모임 업데이트 도구 비즈니스용 Skype 및 Lync</span><span class="sxs-lookup"><span data-stu-id="c7e4a-128">Meeting Update Tool for Skype for Business and Lync</span></span>](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)
    
  - [<span data-ttu-id="c7e4a-129">비즈니스용 Skype 온라인, 모임 마이그레이션 도구(64비트)</span><span class="sxs-lookup"><span data-stu-id="c7e4a-129">Skype for Business Online, Meeting Migration Tool (64-bit)</span></span>](https://go.microsoft.com/fwlink/?LinkID=626047)
    
  - [<span data-ttu-id="c7e4a-130">비즈니스용 Skype 온라인, 모임 마이그레이션 도구(32비트)</span><span class="sxs-lookup"><span data-stu-id="c7e4a-130">Skype for Business Online, Meeting Migration Tool (32-bit)</span></span>](https://www.microsoft.com/download/details.aspx?id=54079)
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="c7e4a-131">사용자와 함께 관리하는 방법을 알고 Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="c7e4a-131">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="c7e4a-132">사용자 관리에 Windows PowerShell 사용자가 허용되거나 허용되지 않는 작업을 모두 관리하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c7e4a-132">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="c7e4a-133">이 Windows PowerShell 여러 작업을 수행할 때 일상적인 작업을 단순화할 수 있는 단일 관리 Microsoft 365 Office 365 비즈니스용 Skype 온라인에서 관리하거나 온라인을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7e4a-133">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="c7e4a-134">다음 항목을 Windows PowerShell 다음 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c7e4a-134">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="c7e4a-135">Windows PowerShell 및 비즈니스용 Skype Online 소개</span><span class="sxs-lookup"><span data-stu-id="c7e4a-135">An introduction to Windows PowerShell and Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="c7e4a-136">PowerShell 또는 Microsoft 365 Office 365 이유</span><span class="sxs-lookup"><span data-stu-id="c7e4a-136">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
 
- <span data-ttu-id="c7e4a-137">Windows PowerShell 많은 사용자에 대해 한 Microsoft 365 설정하는 경우와 같이 관리 센터를 사용하는 것만 사용하여 속도, 단순성 및 생산성에 많은 이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7e4a-137">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="c7e4a-138">다음 항목에서 이러한 이점에 대해 자세히 알아보습니다.</span><span class="sxs-lookup"><span data-stu-id="c7e4a-138">Learn about these advantages in the following topics:</span></span>
    
  - <span data-ttu-id="c7e4a-139">[사용자와 함께 Microsoft 365 또는 Office 365 가장 Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="c7e4a-139">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
  - [<span data-ttu-id="c7e4a-140">온라인 Windows PowerShell 관리하기 위해 비즈니스용 Skype 사용</span><span class="sxs-lookup"><span data-stu-id="c7e4a-140">Using Windows PowerShell to manage Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="c7e4a-141">일반적인 Windows PowerShell 관리 작업을 수행하는 데 비즈니스용 Skype 사용</span><span class="sxs-lookup"><span data-stu-id="c7e4a-141">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
## <a name="related-topics"></a><span data-ttu-id="c7e4a-142">관련 항목</span><span class="sxs-lookup"><span data-stu-id="c7e4a-142">Related topics</span></span>

[<span data-ttu-id="c7e4a-143">오디오 회의 PIN 재설정</span><span class="sxs-lookup"><span data-stu-id="c7e4a-143">Reset the Audio Conferencing PIN</span></span>](reset-the-audio-conferencing-pin.md)
