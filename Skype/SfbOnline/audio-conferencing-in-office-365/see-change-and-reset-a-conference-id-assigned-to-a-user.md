---
title: 비즈니스용 Skype Online에서 사용자에 게 할당 된 전화 회의 ID 보기, 변경, 다시 설정
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 77d36233-2aab-4802-ba9c-e9a8885ea643
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
description: '비즈니스용 Skype Online에서 사용자에 게 전화 번호를 할당 하는 방법과 회의 id 매개 변수를 확인 하는 방법에 대해 알아봅니다. '
ms.openlocfilehash: caa94984b06ff73d8f14acf4727870a988298974
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2020
ms.locfileid: "44163917"
---
# <a name="view-and-reset-a-conference-id-assigned-to-a-user-in-skype-for-business-online"></a><span data-ttu-id="9f1c4-103">비즈니스용 Skype Online에서 사용자에 게 할당 된 회의 ID 보기 및 재설정</span><span class="sxs-lookup"><span data-stu-id="9f1c4-103">View and reset a conference ID assigned to a user in Skype for Business Online</span></span>

> [!Note]
> <span data-ttu-id="9f1c4-104">Microsoft 팀의 사용자 회의 Id에 대 한 자세한 내용은 [Microsoft 팀에서 사용자에 게 할당 된 회의 Id 보기 및 재설정](/MicrosoftTeams/see-change-and-reset-a-conference-id-assigned-to-a-user-in-teams)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9f1c4-104">For information about user conference IDs in Microsoft Teams, see [View and reset a conference ID assigned to a user in Microsoft Teams](/MicrosoftTeams/see-change-and-reset-a-conference-id-assigned-to-a-user-in-teams).</span></span>

<span data-ttu-id="9f1c4-105">Microsoft 365 또는 Office 365에서 오디오 회의를 위해 설정 되 고 Microsoft를 오디오 회의 공급자로 사용 하는 경우 비즈니스용 Skype 사용자에 게 자동으로 회의 ID가 할당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9f1c4-105">A conferencing ID is automatically assigned to a Skype for Business user when they are set up for Audio Conferencing in Microsoft 365 or Office 365 and use Microsoft as the audio conferencing provider.</span></span> <span data-ttu-id="9f1c4-106">모임이 예정 되 면 모임 초대에 할당 된 전화 회의 ID가 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9f1c4-106">The conference ID assigned is sent in the meeting invite when the meeting is scheduled.</span></span> <span data-ttu-id="9f1c4-107">사용자가 예약 하는 각 모임에는 고유한 전화 번호를 할당 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9f1c4-107">Each meeting that a user schedules will get assigned a unique conference ID.</span></span>

<span data-ttu-id="9f1c4-108">전화 회의 ID는 사용자에 게 자동으로 만들어지고 할당 되지만, 사용자가이를 사용 하지 않고 특정 번호로 설정 하려는 경우 또는 사용자가 자신의 전화 회의 ID를 분실 하거나 손실 하지 않았을 때가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f1c4-108">Although a conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or when your users can't remember or have lost their conference ID.</span></span> <span data-ttu-id="9f1c4-109">**비즈니스용 Skype 관리 센터** 및 Windows PowerShell을 사용 하 여 전화 회의 ID를 보고 변경 하 고 다시 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f1c4-109">You can use the **Skype for Business admin center** and Windows PowerShell to view, change, and reset their conference ID.</span></span>

<span data-ttu-id="9f1c4-110">전화 회의 ID와 기본 오디오 회의 전화 번호로 사용자에 게 전자 메일이 전송 되거나, 전화 회의 id를 다시 설정 하는 경우에는 전화 회의 ID만 포함 하 고 PIN이 아닌 다른 전자 메일을 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f1c4-110">An email will be sent to the user with the conference ID and the default audio conferencing phone numbers, or if you reset the conference ID a different email will be sent that will include the conference ID but not a PIN.</span></span> <span data-ttu-id="9f1c4-111">회의 이끌이의 PIN을 다시 설정 하는 방법에 대 한 자세한 내용은 [여기](reset-a-conference-id-for-a-user.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9f1c4-111">For more information about resetting a conference organizer's PIN, [go here](reset-a-conference-id-for-a-user.md).</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="view-and-reset-conference-ids"></a><span data-ttu-id="9f1c4-112">회의 Id 보기 및 재설정</span><span class="sxs-lookup"><span data-stu-id="9f1c4-112">View and reset conference IDs</span></span>

### <a name="to-view-the-conference-id"></a><span data-ttu-id="9f1c4-113">전화 회의 ID를 보려면</span><span class="sxs-lookup"><span data-stu-id="9f1c4-113">To view the conference ID</span></span>

<span data-ttu-id="9f1c4-114">![비즈니스용 skype 로고를 나타내는 아이콘](../images/sfb-logo-30x30.png) **비즈니스용 Skype 관리 센터 사용**</span><span class="sxs-lookup"><span data-stu-id="9f1c4-114">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

<span data-ttu-id="9f1c4-115">자신의 전화 회의 ID를 보고 사용자에 게 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f1c4-115">You can view their conference ID and send it to users.</span></span>

1. <span data-ttu-id="9f1c4-116">회사 또는 학교 계정으로 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f1c4-116">Sign in with your work or school account.</span></span>

2. <span data-ttu-id="9f1c4-117">**비즈니스용 Skype**> 관리 센터로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f1c4-117">Go to the admin center > **Skype for Business**.</span></span>

3. <span data-ttu-id="9f1c4-118">**비즈니스용 Skype 관리 센터**> 의**오디오 회의** > **사용자**의 경우, 전화 회의 ID를 필요로 하는 사용자를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f1c4-118">In the **Skype for Business admin center**> **Audio conferencing** > **Users**, select the user who needs the conference ID.</span></span>

4. <span data-ttu-id="9f1c4-119">작업 페이지에서 **전화 회의 ID**를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f1c4-119">In the Action page, look under **Conference ID**.</span></span>

    > [!TIP]
    > <span data-ttu-id="9f1c4-120">**사용자 페이지에서** 사용자를 선택한 후 **전자 메일을 통해 전화 회의 정보 보내기** 링크를 클릭 하 여 전화 회의 ID 및 오디오 전화 번호가 포함 된 전자 메일에서 모든 회의 정보를 사용자에 게 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f1c4-120">You can send all of the conferencing information to the user in an email that includes the conference ID and audio phone numbers by clicking the **Send conference info via email** link after you select the user on the **Users** page.</span></span>

<span data-ttu-id="9f1c4-121">**Windows PowerShell 사용**</span><span class="sxs-lookup"><span data-stu-id="9f1c4-121">**Using Windows PowerShell**</span></span>

<span data-ttu-id="9f1c4-122">Windows PowerShell을 사용 하 여 사용자의 전화 회의 ID를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f1c4-122">You can use Windows PowerShell to view the conference ID for a user.</span></span> <span data-ttu-id="9f1c4-123">이렇게 하려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f1c4-123">To do so, run:</span></span>

  ```powershell
  Get-CsOnlineDialInConferencingUser -Identity "Amos Marble"
  ```

<span data-ttu-id="9f1c4-124">Cmdlet에 대해 자세히 알아보려면 [get-csonlinedialinconferencinguser](https://go.microsoft.com/fwlink/?LinkId=617693 ) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9f1c4-124">See [Get-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617693 ) to learn more about the cmdlet.</span></span>


### <a name="to-reset-the-conference-id"></a><span data-ttu-id="9f1c4-125">전화 회의 ID를 다시 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="9f1c4-125">To reset the conference ID</span></span>

<span data-ttu-id="9f1c4-126">예를 들어 사용자가 잊어버린 경우 전화 회의 ID를 다시 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f1c4-126">You can reset a conference ID for a user if, for example, they forget it.</span></span>

<span data-ttu-id="9f1c4-127">![비즈니스용 skype 로고를 나타내는 아이콘](../images/sfb-logo-30x30.png) **비즈니스용 Skype 관리 센터 사용**</span><span class="sxs-lookup"><span data-stu-id="9f1c4-127">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1. <span data-ttu-id="9f1c4-128">회사 또는 학교 계정으로 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f1c4-128">Sign in with your work or school account.</span></span>

2. <span data-ttu-id="9f1c4-129">**비즈니스용 Skype**> 관리 센터로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f1c4-129">Go to the admin center > **Skype for Business**.</span></span>

3. <span data-ttu-id="9f1c4-130">**비즈니스용 Skype 관리 센터**> **오디오 회의** > **사용자**의 작업 창에 있는 **전화 회의 ID**아래에서 **원래 대로**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f1c4-130">In the **Skype for Business admin center**> **Audio conferencing** > **Users**, in the Action pane under **Conference ID**, click **Reset**.</span></span>

4. <span data-ttu-id="9f1c4-131">**전화 회의 ID 다시 설정** 창에서 **예**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f1c4-131">In the **Reset conference ID?** window, click **Yes**.</span></span> <span data-ttu-id="9f1c4-132">전화 회의 ID가 자동으로 만들어지고 새 전화 회의 ID를 사용 하 여 사용자에 게 전자 메일이 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9f1c4-132">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span>

<span data-ttu-id="9f1c4-133">**Windows PowerShell 사용**</span><span class="sxs-lookup"><span data-stu-id="9f1c4-133">**Using Windows PowerShell**</span></span>

<span data-ttu-id="9f1c4-134">Windows PowerShell을 사용 하 여 사용자의 전화 회의 ID를 다시 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f1c4-134">You can reset the conference ID for a user by using the Windows PowerShell.</span></span> <span data-ttu-id="9f1c4-135">이 작업을 수행 하려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f1c4-135">To do this, run:</span></span>

  ```PowerShell
  Set-CsOnlineDialInConferencingUser -Identity "Amos Marble" -ResetConferenceID
  ```

## <a name="what-else-should-you-know"></a><span data-ttu-id="9f1c4-136">알아야 할 기타 사항</span><span class="sxs-lookup"><span data-stu-id="9f1c4-136">What else should you know?</span></span>

   > [!IMPORTANT]
   >  <span data-ttu-id="9f1c4-137">새 전화 회의 ID가 만들어지거나 하나는 다시 설정 된 후에는 발신자가 이전 전화 회의 ID를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9f1c4-137">After a new conference ID is created or one is reset, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="9f1c4-138">사용자에 게 기존 모임 초대를 다시 예약 하 여 새 회의 ID가 초대에 추가 되었는지 알려 주어 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f1c4-138">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> <span data-ttu-id="9f1c4-139">사용자는 비즈니스용 Skype 모임 마이그레이션 도구를 사용 하 여 기존 모임을 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f1c4-139">The users can use the Skype for Business Meeting Migration Tool to update their existing meetings.</span></span> <span data-ttu-id="9f1c4-140">도구를 다운로드 하 고 설치 하 고 실행 하는 방법에 대 한 자세한 내용은 비즈니스용 [skype 및 Lync 용 모임 업데이트 도구](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), 비즈니스용 [Skype Online, 모임 마이그레이션 도구 (64 비트)](https://go.microsoft.com/fwlink/?LinkID=626047), 비즈니스용 [Skype online, 모임 마이그레이션 도구 (32 비트)](https://www.microsoft.com/download/details.aspx?id=54079)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9f1c4-140">To see how to download, install, and run the tool, see: [Meeting Update Tool for Skype for Business and Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype for Business Online, Meeting Migration Tool (64-bit)](https://go.microsoft.com/fwlink/?LinkID=626047), and  [Skype for Business Online, Meeting Migration Tool (32-bit)](https://www.microsoft.com/download/details.aspx?id=54079).</span></span>

- <span data-ttu-id="9f1c4-141">Cmdlet에 대해 자세히 알아보려면 [Set-get-csonlinedialinconferencinguser](https://go.microsoft.com/fwlink/?LinkId=617688 ) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9f1c4-141">See [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) to learn more about the cmdlet.</span></span>

- <span data-ttu-id="9f1c4-142">전화 회의 ID는 오디오 회의 브리지에 설정 된 길이의 자릿수를 충족 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f1c4-142">The conference ID must meet the length in digits set on the audio conferencing bridge.</span></span> <span data-ttu-id="9f1c4-143">전화 회의 Id에는 영문자 또는 특수 문자를 사용할 수 없습니다. 숫자만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f1c4-143">You can't use alphabetic or special characters in conference IDs; only numbers can be used.</span></span>

- <span data-ttu-id="9f1c4-144">모든 오디오 회의 사용자의 전화 회의 ID는 기본적으로 7 자리로 표시 되며 자릿수는 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9f1c4-144">The conference ID for all of your audio conferencing users will be 7 digits by default, and the number of digits can't be changed.</span></span>


## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="9f1c4-145">Windows PowerShell을 사용 하 여 관리 하는 방법을 알고 싶으세요?</span><span class="sxs-lookup"><span data-stu-id="9f1c4-145">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="9f1c4-146">Windows PowerShell이 제공 되는 경우 사용자 및 수행할 수 있는 사용자를 관리 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f1c4-146">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="9f1c4-147">Windows PowerShell을 사용 하면 여러 작업을 수행할 때 일상 업무를 단순화할 수 있는 단일 관리 지점을 사용 하 여 Microsoft 365 또는 Office 365 및 비즈니스용 Skype Online을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f1c4-147">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="9f1c4-148">Windows PowerShell을 시작 하려면 다음 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9f1c4-148">To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="9f1c4-149">Windows PowerShell 및 Lync Online 소개</span><span class="sxs-lookup"><span data-stu-id="9f1c4-149">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [<span data-ttu-id="9f1c4-150">Microsoft 365 또는 Office 365 PowerShell을 사용 해야 하는 이유</span><span class="sxs-lookup"><span data-stu-id="9f1c4-150">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)

- <span data-ttu-id="9f1c4-151">Windows PowerShell에는 한 번에 여러 사용자의 설정을 변경 하는 경우와 같이 Microsoft 365 관리 센터를 사용 하는 경우에만 속도, 단순성, 생산성 등 다양 한 이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f1c4-151">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="9f1c4-152">다음 항목에서 이러한 이점에 대해 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="9f1c4-152">Learn about these advantages in the following topics:</span></span>

  - [<span data-ttu-id="9f1c4-153">Windows PowerShell을 사용 하 여 Microsoft 365 또는 Office 365을 관리 하는 최상의 방법</span><span class="sxs-lookup"><span data-stu-id="9f1c4-153">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)

  - [<span data-ttu-id="9f1c4-154">Windows PowerShell을 사용 하 여 비즈니스용 Skype Online 관리</span><span class="sxs-lookup"><span data-stu-id="9f1c4-154">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [<span data-ttu-id="9f1c4-155">Windows PowerShell을 사용 하 여 일반적인 비즈니스용 Skype Online 관리 작업 수행</span><span class="sxs-lookup"><span data-stu-id="9f1c4-155">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a><span data-ttu-id="9f1c4-156">관련 항목</span><span class="sxs-lookup"><span data-stu-id="9f1c4-156">Related topics</span></span>

[<span data-ttu-id="9f1c4-157">Microsoft 365 또는 Office 365에서 오디오 회의 체험 또는 구매</span><span class="sxs-lookup"><span data-stu-id="9f1c4-157">Try or purchase Audio Conferencing in Microsoft 365 or Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)

