---
title: 비즈니스용 Skype Online에서 사용자의 전화 회의 ID 다시 설정
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
description: '비즈니스용 Skype Online에서 사용자의 모임 전화 회의 ID를 다시 설정 하는 단계를 알아보고 모임 업데이트 및 마이그레이션 도구에 대 한 링크를 확인 하세요. '
ms.openlocfilehash: 9a1c2766da021d30feb14954d6e69b6978b64bc9
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2020
ms.locfileid: "41986493"
---
# <a name="reset-a-conference-id-for-a-user-in-skype-for-business-online"></a><span data-ttu-id="a5d57-103">비즈니스용 Skype Online에서 사용자의 전화 회의 ID 다시 설정</span><span class="sxs-lookup"><span data-stu-id="a5d57-103">Reset a conference ID for a user in Skype for Business Online</span></span>

> [!NOTE]
> <span data-ttu-id="a5d57-104">Microsoft 팀에서 전화 회의 ID를 다시 설정 하는 방법에 대 한 자세한 내용은 [Microsoft 팀에서 사용자의 전화 회의 Id 다시 설정을](/MicrosoftTeams/reset-a-conference-id-for-a-user-in-teams)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a5d57-104">For information about resetting conference ID in Microsoft Teams, see [Reset a conference ID for a user in Microsoft Teams](/MicrosoftTeams/reset-a-conference-id-for-a-user-in-teams).</span></span>

<span data-ttu-id="a5d57-105">동적 전화 회의 ID는 전화 접속 전화 번호와 함께 모임 초대 맨 아래에 포함 되며, 발신자가 모임에 전화를 걸 때 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5d57-105">A dynamic conference ID is included at the bottom of meeting invitations along with the dial-in phone numbers that can be used by callers to call in to a meeting.</span></span> <span data-ttu-id="a5d57-106">사용자가 전화 번호를 누르면 모임에 대 한 자동 전화 교환은 발신자에 게이 회의 ID를 입력 하도록 요청 하 여 모임에 참석할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5d57-106">When the user dials the phone number, the auto attendant for the meeting will ask the caller to enter this conference ID so they can attend the meeting.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a5d57-107">회의 공급자가 Microsoft 인 경우에는 사용자의 전화 회의 Id가 동적 만으로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a5d57-107">If your conferencing provider is Microsoft, your users' conference IDs are set to Dynamic Only.</span></span> <span data-ttu-id="a5d57-108">이는 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a5d57-108">This cannot be changed.</span></span> <span data-ttu-id="a5d57-109">전화 회의 Id는 오디오 회의에 사용 하도록 설정 된 비즈니스용 Skype 사용자에 대해서만 자동으로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a5d57-109">Conference IDs are automatically set only for Skype for Business users enabled for Audio Conferencing.</span></span> 

## <a name="resetting-the-conference-id-for-a-user"></a><span data-ttu-id="a5d57-110">사용자의 전화 회의 ID 다시 설정</span><span class="sxs-lookup"><span data-stu-id="a5d57-110">Resetting the conference ID for a user</span></span>
   
1. <span data-ttu-id="a5d57-111">**비즈니스용 Skype 관리 센터**에서 **오디오 회의** > **사용자**를 클릭 하 고 사용자를 선택한 다음, **전화 회의 ID** 아래의 작업 창에서 **원래 대로**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5d57-111">In the **Skype for Business admin center**, click **Audio conferencing** > **Users**, select a user, and then in the Action pane under **Conference ID** click **Reset**.</span></span>
    
2. <span data-ttu-id="a5d57-112">**전화 회의 ID 다시 설정** 창에서 **예**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5d57-112">In the **Reset conference ID?** window, click **Yes**.</span></span> <span data-ttu-id="a5d57-113">전화 회의 ID가 자동으로 만들어지고 새 전화 회의 ID를 사용 하 여 사용자에 게 전자 메일이 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a5d57-113">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span> <span data-ttu-id="a5d57-114">기본적으로 전자 메일은 사용자에 게 전송 되지만,이 기능은 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5d57-114">By default, emails are sent to users, but this can be turned off.</span></span>
    
> [!NOTE]
> <span data-ttu-id="a5d57-115">전화 회의 ID를 다시 설정 하면 새 전화 회의 ID가 포함 된 전자 메일이 사용자에 게 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a5d57-115">After you reset the conference ID, an email with the new conference ID will be sent to the user.</span></span> <span data-ttu-id="a5d57-116">이 전자 메일은 대부분의 경우 Office 365 사서함 인 기본 전자 메일 주소로 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a5d57-116">This email will be sent to the primary email address, in many cases, their Office 365 mailbox.</span></span> <span data-ttu-id="a5d57-117">전자 메일에는 새로운 회의 ID 인 기본 전화 접속 전화 번호와 비즈니스용 Skype 모임 업데이트 도구를 사용 하 여 기존 모임을 업데이트 하는 지침이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5d57-117">The email contains the new conference ID, default dial-in phone number(s) and instructions to use the Skype for Business Meeting Update Tool to update existing meetings.</span></span> 
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="what-else-should-i-know"></a><span data-ttu-id="a5d57-118">알아야 할 기타 사항</span><span class="sxs-lookup"><span data-stu-id="a5d57-118">What else should I know?</span></span>

- <span data-ttu-id="a5d57-119">작업 창에서 사용자의 **전자 메일을 통해 전화 회의 정보 보내기를** 클릭 하 여 사용자에 게 모든 회의 정보를 전자 메일로 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5d57-119">You can send all of the conferencing information to the user in an email that includes the conference ID and dial-in phone numbers by clicking **Send conference info via email** for the user in the Action pane.</span></span> <span data-ttu-id="a5d57-120">PIN은 전송 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a5d57-120">It doesn't send the PIN.</span></span>
    
- <span data-ttu-id="a5d57-121">전화 회의 ID에는 7 자리 숫자가 포함 되며 비즈니스용 Skype 관리 센터에서 또는 Windows PowerShell을 사용 하 여 길이를 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a5d57-121">A conference ID will contain 7 digits, and you can't change its length in the Skype for Business admin center or by using Windows PowerShell.</span></span>
    
- <span data-ttu-id="a5d57-122">다시 설정한 후에는 **전화 회의 id**아래에 나열 된 새 전화 회의 id를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5d57-122">After it has been reset, you can see the new conference ID listed under **Conference ID**.</span></span>
    
- <span data-ttu-id="a5d57-123">오디오 회의에 대 한 사용자의 전화 회의 ID는 **사용자** 페이지에서 사용자를 선택 하면 **오디오 회의** 아래에 있는 작업 창의 아래쪽에 표시 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5d57-123">The conference ID for a user for audio conferencing can be viewed at the bottom of the Action pane under **Audio conferencing** when you select the user on the **Users** page.</span></span>
    
- <span data-ttu-id="a5d57-124">새 전화 회의 ID를 만든 후에는 발신자가 이전 회의 ID를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a5d57-124">After a new conference ID is created, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="a5d57-125">사용자에 게 기존 모임 초대를 다시 예약 하 여 새 회의 ID가 초대에 추가 되었는지 알려 주어 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5d57-125">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> <span data-ttu-id="a5d57-126">사용자는 비즈니스용 Skype 모임 도구를 사용 하 여 기존 모임을 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5d57-126">The users can use Skype for Business Meeting Tool to update their existing meetings.</span></span> <span data-ttu-id="a5d57-127">비즈니스용 Skype 모임 업데이트 도구를 다운로드 하 고 설치 하 고 실행 하는 방법에 대 한 자세한 내용은 다음을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a5d57-127">To see how to download, install, and run the Skype for Business Meeting Update Tool, see:</span></span>
    
  - [<span data-ttu-id="a5d57-128">비즈니스용 Skype 및 Lync 용 모임 업데이트 도구</span><span class="sxs-lookup"><span data-stu-id="a5d57-128">Meeting Update Tool for Skype for Business and Lync</span></span>](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)
    
  - [<span data-ttu-id="a5d57-129">비즈니스용 Skype Online, 모임 마이그레이션 도구 (64 비트)</span><span class="sxs-lookup"><span data-stu-id="a5d57-129">Skype for Business Online, Meeting Migration Tool (64-bit)</span></span>](https://go.microsoft.com/fwlink/?LinkID=626047)
    
  - [<span data-ttu-id="a5d57-130">비즈니스용 Skype Online, 모임 마이그레이션 도구 (32 비트)</span><span class="sxs-lookup"><span data-stu-id="a5d57-130">Skype for Business Online, Meeting Migration Tool (32-bit)</span></span>](https://www.microsoft.com/download/details.aspx?id=54079)
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="a5d57-131">Windows PowerShell을 사용 하 여 관리 하는 방법을 알고 싶으세요?</span><span class="sxs-lookup"><span data-stu-id="a5d57-131">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="a5d57-132">Windows PowerShell이 제공 되는 경우 사용자 및 수행할 수 있는 사용자를 관리 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5d57-132">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="a5d57-133">Windows PowerShell을 사용 하면 여러 작업을 수행할 때 일상 업무를 단순화할 수 있는 단일 관리 지점을 사용 하 여 Office 365 및 비즈니스용 Skype Online을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5d57-133">With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="a5d57-134">Windows PowerShell을 시작 하려면 다음 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a5d57-134">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="a5d57-135">Windows PowerShell 및 Lync Online 소개</span><span class="sxs-lookup"><span data-stu-id="a5d57-135">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="a5d57-136">Office 365 PowerShell을 사용 해야 하는 이유</span><span class="sxs-lookup"><span data-stu-id="a5d57-136">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="a5d57-137">Windows PowerShell에는 한 번에 여러 사용자의 설정을 변경 하는 경우와 같이 Microsoft 365 관리 센터를 사용 하는 경우에만 속도, 단순성, 생산성 등 다양 한 이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5d57-137">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="a5d57-138">다음 항목에서 이러한 이점에 대해 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="a5d57-138">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="a5d57-139">Windows PowerShell을 사용 하 여 Office 365를 관리 하는 가장 좋은 방법</span><span class="sxs-lookup"><span data-stu-id="a5d57-139">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="a5d57-140">Windows PowerShell을 사용 하 여 비즈니스용 Skype Online 관리</span><span class="sxs-lookup"><span data-stu-id="a5d57-140">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="a5d57-141">Windows PowerShell을 사용 하 여 일반적인 비즈니스용 Skype Online 관리 작업 수행</span><span class="sxs-lookup"><span data-stu-id="a5d57-141">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="a5d57-142">관련 항목</span><span class="sxs-lookup"><span data-stu-id="a5d57-142">Related topics</span></span>

[<span data-ttu-id="a5d57-143">오디오 회의 PIN 재설정</span><span class="sxs-lookup"><span data-stu-id="a5d57-143">Reset the Audio Conferencing PIN</span></span>](reset-the-audio-conferencing-pin.md)
