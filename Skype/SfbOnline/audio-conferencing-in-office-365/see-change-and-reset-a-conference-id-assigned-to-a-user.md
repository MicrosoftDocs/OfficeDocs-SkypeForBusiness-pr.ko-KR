---
title: 비즈니스용 Skype Online에서 사용자에게 할당된 전화 회의 ID 보기, 변경 및 재설정
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
description: '비즈니스용 Skype Online에서 사용자에게 전화 회의 ID를 할당하는 방법과 회의 ID 매개 변수에 대해 자세히 배워야 합니다. '
ms.openlocfilehash: a8f0e64ef30e1e503a1e3b78c9823f5d115df837
ms.sourcegitcommit: b72bf3827e7145b9b6a95c84e88a7879c6e8c337
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/12/2020
ms.locfileid: "46643608"
---
# <a name="view-and-reset-a-conference-id-assigned-to-a-user-in-skype-for-business-online"></a><span data-ttu-id="f3c0f-103">비즈니스용 Skype Online에서 사용자에게 할당된 전화 회의 ID 보기 및 다시 설정</span><span class="sxs-lookup"><span data-stu-id="f3c0f-103">View and reset a conference ID assigned to a user in Skype for Business Online</span></span>

> [!Note]
> <span data-ttu-id="f3c0f-104">Microsoft Teams의 사용자 회의 ID에 대한 자세한 내용은 Microsoft Teams에서 사용자에게 할당된 회의 ID 보기 및 재설정을 [참조하세요.](/MicrosoftTeams/see-change-and-reset-a-conference-id-assigned-to-a-user-in-teams)</span><span class="sxs-lookup"><span data-stu-id="f3c0f-104">For information about user conference IDs in Microsoft Teams, see [View and reset a conference ID assigned to a user in Microsoft Teams](/MicrosoftTeams/see-change-and-reset-a-conference-id-assigned-to-a-user-in-teams).</span></span>

<span data-ttu-id="f3c0f-105">Microsoft 365 또는 Office 365에서 오디오 회의를 설정하고 Microsoft를 오디오 회의 공급자로 사용할 때 비즈니스용 Skype 사용자에게 회의 ID가 자동으로 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="f3c0f-105">A conferencing ID is automatically assigned to a Skype for Business user when they are set up for Audio Conferencing in Microsoft 365 or Office 365 and use Microsoft as the audio conferencing provider.</span></span> <span data-ttu-id="f3c0f-106">할당된 회의 ID는 모임이 예약될 때 모임 초대에 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="f3c0f-106">The conference ID assigned is sent in the meeting invite when the meeting is scheduled.</span></span> <span data-ttu-id="f3c0f-107">사용자가 예약하는 각 모임에는 고유한 회의 ID가 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="f3c0f-107">Each meeting that a user schedules will get assigned a unique conference ID.</span></span>

<span data-ttu-id="f3c0f-108">전화 회의 ID가 자동으로 만들어지며 사용자에게 할당되어도 사용자가 이 ID를 사용하지 못하고 특정 번호로 설정하거나 사용자가 전화 회의 ID를 기억하지 못하거나 분실한 경우도 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3c0f-108">Although a conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or when your users can't remember or have lost their conference ID.</span></span> <span data-ttu-id="f3c0f-109">비즈니스용 **Skype** 관리 센터 및 Windows PowerShell ID를 보고, 변경하고, 재설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3c0f-109">You can use the **Skype for Business admin center** and Windows PowerShell to view, change, and reset their conference ID.</span></span>

<span data-ttu-id="f3c0f-110">전화 회의 ID와 기본 오디오 회의 전화 번호가 포함된 전자 메일이 사용자에게 전송되거나 전화 회의 ID를 다시 설정하면 전화 회의 ID는 포함하지만 PIN은 포함하지 않는 다른 전자 메일이 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="f3c0f-110">An email will be sent to the user with the conference ID and the default audio conferencing phone numbers, or if you reset the conference ID a different email will be sent that will include the conference ID but not a PIN.</span></span> <span data-ttu-id="f3c0f-111">회의 이끌이의 PIN을 다시 설정하는 자세한 내용은 [여기를 클릭하세요.](reset-a-conference-id-for-a-user.md)</span><span class="sxs-lookup"><span data-stu-id="f3c0f-111">For more information about resetting a conference organizer's PIN, [go here](reset-a-conference-id-for-a-user.md).</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="view-and-reset-conference-ids"></a><span data-ttu-id="f3c0f-112">회의 ID 보기 및 재설정</span><span class="sxs-lookup"><span data-stu-id="f3c0f-112">View and reset conference IDs</span></span>

### <a name="to-view-the-conference-id"></a><span data-ttu-id="f3c0f-113">회의 ID를 보기 위해</span><span class="sxs-lookup"><span data-stu-id="f3c0f-113">To view the conference ID</span></span>

<span data-ttu-id="f3c0f-114">![비즈니스용 skype 로고를 나타내는 아이콘](../images/sfb-logo-30x30.png) **비즈니스용 Skype 관리 센터 사용**</span><span class="sxs-lookup"><span data-stu-id="f3c0f-114">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

<span data-ttu-id="f3c0f-115">자신의 회의 ID를 보고 사용자에게 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3c0f-115">You can view their conference ID and send it to users.</span></span>

1. <span data-ttu-id="f3c0f-116">직장 또는 학교 계정으로 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="f3c0f-116">Sign in with your work or school account.</span></span>

2. <span data-ttu-id="f3c0f-117">비즈니스용 Skype의 > **관리 센터로 이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="f3c0f-117">Go to the admin center > **Skype for Business**.</span></span>

3. <span data-ttu-id="f3c0f-118">비즈니스용 **Skype 관리 센터** 오디오 회의 사용자에서 전화 회의 >    >  ID가 필요한 사용자를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f3c0f-118">In the **Skype for Business admin center**> **Audio conferencing** > **Users**, select the user who needs the conference ID.</span></span>

4. <span data-ttu-id="f3c0f-119">작업 페이지에서 회의 **ID를 살펴 봐야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="f3c0f-119">In the Action page, look under **Conference ID**.</span></span>

    > [!TIP]
    > <span data-ttu-id="f3c0f-120">사용자 페이지에서 사용자를 선택한 후 전자 메일 링크를 통해 전화 회의 정보 보내기 링크를 클릭하여  전화 회의 ID 및 오디오 전화 번호가 포함된 전자 메일로 사용자에게 모든 회의 정보를 보낼 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="f3c0f-120">You can send all of the conferencing information to the user in an email that includes the conference ID and audio phone numbers by clicking the **Send conference info via email** link after you select the user on the **Users** page.</span></span>

<span data-ttu-id="f3c0f-121">**다음 Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="f3c0f-121">**Using Windows PowerShell**</span></span>

<span data-ttu-id="f3c0f-122">사용자에 대한 Windows PowerShell ID를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3c0f-122">You can use Windows PowerShell to view the conference ID for a user.</span></span> <span data-ttu-id="f3c0f-123">이렇게 하여 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="f3c0f-123">To do so, run:</span></span>

  ```powershell
  Get-CsOnlineDialInConferencingUser -Identity "Amos Marble"
  ```

<span data-ttu-id="f3c0f-124">cmdlet에 대한 자세한 내용은 [Get-CsOnlineDialInConferencingUser를](https://go.microsoft.com/fwlink/?LinkId=617693 ) 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="f3c0f-124">See [Get-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617693 ) to learn more about the cmdlet.</span></span>


### <a name="to-reset-the-conference-id"></a><span data-ttu-id="f3c0f-125">회의 ID를 다시 설정</span><span class="sxs-lookup"><span data-stu-id="f3c0f-125">To reset the conference ID</span></span>

<span data-ttu-id="f3c0f-126">예를 들어 사용자가 잊어버렸다면 사용자의 회의 ID를 다시 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3c0f-126">You can reset a conference ID for a user if, for example, they forget it.</span></span>

<span data-ttu-id="f3c0f-127">![비즈니스용 skype 로고를 나타내는 아이콘](../images/sfb-logo-30x30.png) **비즈니스용 Skype 관리 센터 사용**</span><span class="sxs-lookup"><span data-stu-id="f3c0f-127">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1. <span data-ttu-id="f3c0f-128">직장 또는 학교 계정으로 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="f3c0f-128">Sign in with your work or school account.</span></span>

2. <span data-ttu-id="f3c0f-129">비즈니스용 Skype의 > **관리 센터로 이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="f3c0f-129">Go to the admin center > **Skype for Business**.</span></span>

3. <span data-ttu-id="f3c0f-130">비즈니스용 Skype 관리 **센터** 오디오 회의 사용자의 작업 창에서 전화 회의 ID 아래에 >    >   **있는**[다시 설정]을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="f3c0f-130">In the **Skype for Business admin center**> **Audio conferencing** > **Users**, in the Action pane under **Conference ID**, click **Reset**.</span></span>

4. <span data-ttu-id="f3c0f-131">회의 **ID 재설정 창에서** **예를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="f3c0f-131">In the **Reset conference ID?** window, click **Yes**.</span></span> <span data-ttu-id="f3c0f-132">회의 ID가 자동으로 만들어지며 새 회의 ID가 있는 전자 메일이 사용자에게 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="f3c0f-132">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span>

<span data-ttu-id="f3c0f-133">**다음 Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="f3c0f-133">**Using Windows PowerShell**</span></span>

<span data-ttu-id="f3c0f-134">사용자에 대한 회의 ID는 다음을 사용하여 다시 설정할 Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f3c0f-134">You can reset the conference ID for a user by using the Windows PowerShell.</span></span> <span data-ttu-id="f3c0f-135">이를 위해 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="f3c0f-135">To do this, run:</span></span>

  ```PowerShell
  Set-CsOnlineDialInConferencingUser -Identity "Amos Marble" -ResetConferenceID
  ```

## <a name="what-else-should-you-know"></a><span data-ttu-id="f3c0f-136">알아야 할 다른 것은 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="f3c0f-136">What else should you know?</span></span>

   > [!IMPORTANT]
   >  <span data-ttu-id="f3c0f-137">새 전화 회의 ID가 만들어지거나 다시 설정되면 발신자에 의해 이전 전화 회의 ID를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f3c0f-137">After a new conference ID is created or one is reset, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="f3c0f-138">새 회의 ID가 초대에 추가될 수 있도록 사용자에게 기존 모임 초대를 다시 계획할지 알려야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3c0f-138">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> <span data-ttu-id="f3c0f-139">사용자는 비즈니스용 Skype 모임 마이그레이션 도구를 사용하여 기존 모임을 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3c0f-139">The users can use the Skype for Business Meeting Migration Tool to update their existing meetings.</span></span> <span data-ttu-id="f3c0f-140">도구를 다운로드, 설치 및 실행하려면 비즈니스용 Skype 및 [Lync용](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)모임 업데이트 도구, 비즈니스용 Skype Online, 모임 마이그레이션 도구(64비트) 및 비즈니스용 Skype Online 모임 마이그레이션 [](https://go.microsoft.com/fwlink/?LinkID=626047) [도구(32비트)를](https://www.microsoft.com/download/details.aspx?id=54079)참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f3c0f-140">To see how to download, install, and run the tool, see: [Meeting Update Tool for Skype for Business and Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype for Business Online, Meeting Migration Tool (64-bit)](https://go.microsoft.com/fwlink/?LinkID=626047), and  [Skype for Business Online, Meeting Migration Tool (32-bit)](https://www.microsoft.com/download/details.aspx?id=54079).</span></span>

- <span data-ttu-id="f3c0f-141">cmdlet에 대한 자세한 내용은 [Set-CsOnlineDialInConferencingUser를](https://go.microsoft.com/fwlink/?LinkId=617688 ) 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="f3c0f-141">See [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) to learn more about the cmdlet.</span></span>

- <span data-ttu-id="f3c0f-142">회의 ID는 오디오 회의 브리지에 설정된 자릿수 길이를 충족해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3c0f-142">The conference ID must meet the length in digits set on the audio conferencing bridge.</span></span> <span data-ttu-id="f3c0f-143">회의 신분증에는 사전 또는 특수 문자를 사용할 수 없습니다. 숫자만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3c0f-143">You can't use alphabetic or special characters in conference IDs; only numbers can be used.</span></span>

- <span data-ttu-id="f3c0f-144">모든 오디오 회의 사용자의 전화 회의 ID는 기본적으로 9자리로 설정되어 있으며, 자릿수는 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f3c0f-144">The conference ID for all of your audio conferencing users will be 9 digits by default, and the number of digits can't be changed.</span></span>


## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="f3c0f-145">사용자 계정으로 관리하는 방법을 알고 Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="f3c0f-145">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="f3c0f-146">이 경우 Windows PowerShell 관리에 대한 모든 것 및 사용자가 허용되거나 허용되지 않는 작업을 관리하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="f3c0f-146">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="f3c0f-147">이 Windows PowerShell 여러 작업을 수행할 때 일상적인 작업을 간소화할 수 있는 단일 관리 지점을 사용하여 Microsoft 365 또는 Office 365 및 비즈니스용 Skype Online을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3c0f-147">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="f3c0f-148">다음 항목을 Windows PowerShell 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f3c0f-148">To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="f3c0f-149">Windows PowerShell 및 Lync Online 소개</span><span class="sxs-lookup"><span data-stu-id="f3c0f-149">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [<span data-ttu-id="f3c0f-150">Microsoft 365 또는 Office 365 PowerShell을 사용하는 이유</span><span class="sxs-lookup"><span data-stu-id="f3c0f-150">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)

- <span data-ttu-id="f3c0f-151">Windows PowerShell Microsoft 365 관리 센터를 사용하는 경우와 같이 여러 사용자에 대해 한 번씩 설정을 변경하는 경우와 같이 속도, 단순성 및 생산성에 많은 이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3c0f-151">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="f3c0f-152">다음 항목에서 이러한 이점에 대해 자세히 배워야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3c0f-152">Learn about these advantages in the following topics:</span></span>

  - [<span data-ttu-id="f3c0f-153">Microsoft 365 또는 Office 365를 관리하는 가장 좋은 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f3c0f-153">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)

  - [<span data-ttu-id="f3c0f-154">비즈니스 Windows PowerShell 사용하여 비즈니스용 Skype Online 관리</span><span class="sxs-lookup"><span data-stu-id="f3c0f-154">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [<span data-ttu-id="f3c0f-155">비즈니스용 Windows PowerShell Skype Online 관리 작업을 수행하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3c0f-155">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a><span data-ttu-id="f3c0f-156">관련 항목</span><span class="sxs-lookup"><span data-stu-id="f3c0f-156">Related topics</span></span>

[<span data-ttu-id="f3c0f-157">Microsoft 365 또는 Office 365에서 오디오 회의 시도 또는 구매</span><span class="sxs-lookup"><span data-stu-id="f3c0f-157">Try or purchase Audio Conferencing in Microsoft 365 or Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)

