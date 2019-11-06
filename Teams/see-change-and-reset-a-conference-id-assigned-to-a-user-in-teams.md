---
title: Microsoft 팀에서 사용자에 게 할당 된 전화 회의 ID 보기, 변경, 다시 설정
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 77d36233-2aab-4802-ba9c-e9a8885ea643
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Microsoft 팀의 사용자에 게 전화 회의 ID를 할당 하는 방법과 전화 회의 ID의 매개 변수를 지정 하는 방법에 대해 알아봅니다. '
ms.openlocfilehash: d134a3664a6cee588d08f3d1a33bc6018d97a1fa
ms.sourcegitcommit: 15fe483079847d24869e325eead35f252da8c7dd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/06/2019
ms.locfileid: "37571340"
---
# <a name="view-and-reset-a-conference-id-assigned-to-a-user-in-microsoft-teams"></a><span data-ttu-id="1859a-103">Microsoft 팀에서 사용자에 게 할당 된 회의 ID 보기 및 다시 설정</span><span class="sxs-lookup"><span data-stu-id="1859a-103">View and reset a conference ID assigned to a user in Microsoft Teams</span></span>

<span data-ttu-id="1859a-104">전화 회의 ID가 Office 365에서 오디오 회의를 위해 설정 되 고 Microsoft를 오디오 회의 공급자로 사용 하는 경우 Microsoft 팀 사용자에 게 자동으로 할당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1859a-104">A conferencing ID is automatically assigned to a Microsoft Teams user when they are set up for Audio Conferencing in Office 365 and use Microsoft as the audio conferencing provider.</span></span> <span data-ttu-id="1859a-105">모임이 예정 되 면 모임 초대에 할당 된 전화 회의 ID가 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1859a-105">The conference ID assigned is sent in the meeting invite when the meeting is scheduled.</span></span> <span data-ttu-id="1859a-106">사용자가 예약 하는 각 모임에는 고유한 전화 번호를 할당 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1859a-106">Each meeting that a user schedules will get assigned a unique conference ID.</span></span> 
  
<span data-ttu-id="1859a-107">전화 회의 ID는 사용자에 게 자동으로 만들어지고 할당 되지만, 사용자가이를 사용 하지 않고 특정 번호로 설정 하려는 경우 또는 사용자가 자신의 전화 회의 ID를 분실 하거나 손실 하지 않았을 때가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1859a-107">Although a conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or when your users can't remember or have lost their conference ID.</span></span> <span data-ttu-id="1859a-108">Microsoft 팀 관리 센터 또는 Windows PowerShell을 사용 하 여 전화 회의 ID를 보고 변경 하 고 다시 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1859a-108">You can use Microsoft Teams admin center or Windows PowerShell to view, change, and reset their conference ID.</span></span>
  
<span data-ttu-id="1859a-109">전화 회의 ID와 기본 오디오 회의 전화 번호로 사용자에 게 전자 메일이 전송 되거나, 전화 회의 id를 다시 설정 하는 경우에는 전화 회의 ID만 포함 하 고 PIN이 아닌 다른 전자 메일을 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1859a-109">An email will be sent to the user with the conference ID and the default audio conferencing phone numbers, or if you reset the conference ID a different email will be sent that will include the conference ID but not a PIN.</span></span> <span data-ttu-id="1859a-110">회의 이끌이의 PIN을 다시 설정 하는 방법에 대 한 자세한 내용은 [여기](reset-a-conference-id-for-a-user-in-teams.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1859a-110">For more information about resetting a conference organizer's PIN, [go here](reset-a-conference-id-for-a-user-in-teams.md).</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="view-and-reset-conference-ids"></a><span data-ttu-id="1859a-111">회의 Id 보기 및 재설정</span><span class="sxs-lookup"><span data-stu-id="1859a-111">View and reset conference IDs</span></span>

### <a name="to-view-the-conference-id"></a><span data-ttu-id="1859a-112">전화 회의 ID를 보려면</span><span class="sxs-lookup"><span data-stu-id="1859a-112">To view the conference ID</span></span>

<span data-ttu-id="1859a-113">![](media/teams-logo-30x30.png) **Microsoft 팀 관리 센터를 사용 하 여** microsoft 팀 로고를 표시 하는 아이콘</span><span class="sxs-lookup"><span data-stu-id="1859a-113">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="1859a-114">왼쪽 탐색 창에서 **사용자**를 클릭 한 다음 사용 가능한 사용자 목록에서 사용자를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1859a-114">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="1859a-115">페이지 맨 위에서 **편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1859a-115">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="1859a-116">**오디오 회의**에서 **전화 회의 ID**를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="1859a-116">Under **Audio Conferencing**, look under **Conference ID**.</span></span>

    > [!TIP]
    > <span data-ttu-id="1859a-117">**전자 메일로 회의 정보 보내기** 링크를 클릭 하 여 전화 회의 ID 및 오디오 전화 번호가 포함 된 전자 메일로 모든 회의 정보를 사용자에 게 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1859a-117">You can send all of the conferencing information to the user in an email that includes the conference ID and audio phone numbers by clicking the **Send conference info in email** link.</span></span>
  
<span data-ttu-id="1859a-118">**Windows PowerShell 사용**</span><span class="sxs-lookup"><span data-stu-id="1859a-118">**Using Windows PowerShell**</span></span>

<span data-ttu-id="1859a-119">자세한 내용은 [Microsoft 팀 PowerShell 참조](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1859a-119">See the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
  
### <a name="to-reset-the-conference-id"></a><span data-ttu-id="1859a-120">전화 회의 ID를 다시 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="1859a-120">To reset the conference ID</span></span>

<span data-ttu-id="1859a-121">예를 들어 사용자가 잊어버린 경우 전화 회의 ID를 다시 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1859a-121">You can reset a conference ID for a user if, for example, they forget it.</span></span>
  
<span data-ttu-id="1859a-122">![](media/teams-logo-30x30.png) **Microsoft 팀 관리 센터를 사용 하 여** microsoft 팀 로고를 표시 하는 아이콘</span><span class="sxs-lookup"><span data-stu-id="1859a-122">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="1859a-123">왼쪽 탐색 창에서 **사용자**를 클릭 한 다음 사용 가능한 사용자 목록에서 사용자를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1859a-123">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="1859a-124">페이지 맨 위에서 **편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1859a-124">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="1859a-125">**오디오 회의**에서 **전화 회의 ID 재설정**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1859a-125">Under **Audio Conferencing**, click **Reset conference ID**.</span></span>

4. <span data-ttu-id="1859a-126">**전화 회의 ID 다시 설정** 창에서 **원래 대로**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1859a-126">In the **Reset conference ID** window, click **Reset**.</span></span> <span data-ttu-id="1859a-127">전화 회의 ID가 자동으로 만들어지고 새 전화 회의 ID를 사용 하 여 사용자에 게 전자 메일이 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1859a-127">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span>
  
<span data-ttu-id="1859a-128">**Windows PowerShell 사용**</span><span class="sxs-lookup"><span data-stu-id="1859a-128">**Using Windows PowerShell**</span></span>

<span data-ttu-id="1859a-129">자세한 내용은 [Microsoft 팀 PowerShell 참조](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1859a-129">See the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>


## <a name="what-else-should-you-know"></a><span data-ttu-id="1859a-130">알아야 할 기타 사항</span><span class="sxs-lookup"><span data-stu-id="1859a-130">What else should you know?</span></span>

   > [!IMPORTANT]
   >  <span data-ttu-id="1859a-131">새 전화 회의 ID가 만들어지거나 하나는 다시 설정 된 후에는 발신자가 이전 전화 회의 ID를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1859a-131">After a new conference ID is created or one is reset, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="1859a-132">사용자에 게 기존 모임 초대를 다시 예약 하 여 새 회의 ID가 초대에 추가 되었는지 알려 주어 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1859a-132">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> 
  
    
- <span data-ttu-id="1859a-133">전화 회의 ID는 오디오 회의 브리지에 설정 된 길이의 자릿수를 충족 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1859a-133">The conference ID must meet the length in digits set on the audio conferencing bridge.</span></span> <span data-ttu-id="1859a-134">전화 회의 Id에는 영문자 또는 특수 문자를 사용할 수 없습니다. 숫자만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1859a-134">You can't use alphabetic or special characters in conference IDs; only numbers can be used.</span></span>
   
    
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="1859a-135">Windows PowerShell에 대 한 자세한 정보를 확인 하 고 싶으신가요?</span><span class="sxs-lookup"><span data-stu-id="1859a-135">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="1859a-136">Windows PowerShell은 사용자 및 허용 되지 않거나 수행할 수 있는 사용자를 관리 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="1859a-136">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="1859a-137">Windows PowerShell을 사용 하면 여러 작업을 수행할 때 일상 업무를 단순화할 수 있는 단일 관리 지점을 사용 하 여 Office 365를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1859a-137">With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="1859a-138">Windows PowerShell을 시작 하려면 다음 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1859a-138">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="1859a-139">Office 365 PowerShell을 사용 해야 하는 이유</span><span class="sxs-lookup"><span data-stu-id="1859a-139">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="1859a-140">Windows PowerShell을 사용 하 여 Office 365를 관리 하는 가장 좋은 방법</span><span class="sxs-lookup"><span data-stu-id="1859a-140">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="1859a-141">Windows PowerShell에 대 한 자세한 내용은 [Microsoft 팀 PowerShell 참조](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) 에서 자세한 내용을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1859a-141">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="1859a-142">관련 주제</span><span class="sxs-lookup"><span data-stu-id="1859a-142">Related topics</span></span>

[<span data-ttu-id="1859a-143">Office 365에서 오디오 회의 체험 또는 구매</span><span class="sxs-lookup"><span data-stu-id="1859a-143">Try or purchase Audio Conferencing in Office 365</span></span>](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)

