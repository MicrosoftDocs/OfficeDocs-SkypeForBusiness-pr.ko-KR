---
title: 사용자의 회의 ID 보기, 변경 및 재설정
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
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-apr2020
description: Microsoft Teams에서 사용자에게 회의 ID를 할당하는 방법과 회의 ID 매개 변수를 지정해야 하는 방법을 배워야 합니다.
ms.openlocfilehash: 4f24fb85479e6a52c8b2658b7a8a41beb0e1c6ad
ms.sourcegitcommit: 1807ea5509f8efa6abba8462bce2f3646117e8bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/10/2020
ms.locfileid: "44691154"
---
# <a name="view-and-reset-a-conference-id-assigned-to-a-user-in-microsoft-teams"></a><span data-ttu-id="78b43-103">Microsoft Teams에서 사용자에게 할당된 회의 ID 보기 및 다시 설정</span><span class="sxs-lookup"><span data-stu-id="78b43-103">View and reset a conference ID assigned to a user in Microsoft Teams</span></span>

<span data-ttu-id="78b43-104">Microsoft 365 또는 Office 365에서 오디오 회의를 설정하고 Microsoft를 오디오 회의 공급자로 사용할 때 회의 ID가 Microsoft Teams 사용자에게 자동으로 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="78b43-104">A conferencing ID is automatically assigned to a Microsoft Teams user when they are set up for Audio Conferencing in Microsoft 365 or Office 365 and use Microsoft as the audio conferencing provider.</span></span> <span data-ttu-id="78b43-105">할당된 회의 ID는 모임이 예약될 때 모임 초대에 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="78b43-105">The conference ID assigned is sent in the meeting invite when the meeting is scheduled.</span></span> <span data-ttu-id="78b43-106">사용자가 예약하는 각 모임에는 고유한 회의 ID가 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="78b43-106">Each meeting that a user schedules will get assigned a unique conference ID.</span></span> 
  
<span data-ttu-id="78b43-107">전화 회의 ID가 자동으로 만들어지며 사용자에게 할당되어도 사용자가 이 ID를 사용하지 못하고 특정 번호로 설정하거나 사용자가 전화 회의 ID를 기억하지 못하거나 분실한 경우도 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78b43-107">Although a conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or when your users can't remember or have lost their conference ID.</span></span> <span data-ttu-id="78b43-108">Microsoft Teams 관리 센터 또는 Windows PowerShell ID를 보고, 변경하고, 재설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78b43-108">You can use Microsoft Teams admin center or Windows PowerShell to view, change, and reset their conference ID.</span></span>
  
<span data-ttu-id="78b43-109">전화 회의 ID와 기본 오디오 회의 전화 번호가 포함된 전자 메일이 사용자에게 전송되거나 전화 회의 ID를 다시 설정하면 전화 회의 ID는 포함하지만 PIN은 포함하지 않는 다른 전자 메일이 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="78b43-109">An email will be sent to the user with the conference ID and the default audio conferencing phone numbers, or if you reset the conference ID a different email will be sent that will include the conference ID but not a PIN.</span></span> <span data-ttu-id="78b43-110">회의 [이끌이의](reset-a-conference-id-for-a-user-in-teams.md) PIN을 다시 설정하는 방법에 대한 자세한 내용은 Microsoft Teams에서 사용자의 회의 ID 재설정을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="78b43-110">See [Reset a conference ID for a user in Microsoft Teams](reset-a-conference-id-for-a-user-in-teams.md) for more information about how to reset a conference organizer's PIN.</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="view-and-reset-conference-ids"></a><span data-ttu-id="78b43-111">회의 ID 보기 및 재설정</span><span class="sxs-lookup"><span data-stu-id="78b43-111">View and reset conference IDs</span></span>

### <a name="to-view-the-conference-id"></a><span data-ttu-id="78b43-112">회의 ID를 보기 위해</span><span class="sxs-lookup"><span data-stu-id="78b43-112">To view the conference ID</span></span>

<span data-ttu-id="78b43-113">![Microsoft Teams 로고를 나타내는 아이콘](media/teams-logo-30x30.png) **Microsoft Teams 관리 센터 사용**</span><span class="sxs-lookup"><span data-stu-id="78b43-113">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="78b43-114">왼쪽 탐색 모음에서 **[사용자]를** 클릭한 다음 사용 가능한 사용자 목록에서 사용자를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="78b43-114">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="78b43-115">페이지 맨 위에 있는 편집을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="78b43-115">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="78b43-116">오디오 **회의 아래에서** 회의 **ID를 살펴 봐야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="78b43-116">Under **Audio Conferencing**, look under **Conference ID**.</span></span>

    > [!TIP]
    > <span data-ttu-id="78b43-117">전자 메일 링크에서 전화 회의 정보 보내기를 클릭하여 전화 회의 ID 및 오디오 전화 번호가 포함된 전자 메일로 사용자에게 모든 회의 정보를 **보낼 수** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78b43-117">You can send all of the conferencing information to the user in an email that includes the conference ID and audio phone numbers by clicking the **Send conference info in email** link.</span></span>
  
<span data-ttu-id="78b43-118">**다음 Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="78b43-118">**Using Windows PowerShell**</span></span>

<span data-ttu-id="78b43-119">자세한 내용은 [Microsoft Teams PowerShell 참조를](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="78b43-119">See the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
  
### <a name="to-reset-the-conference-id"></a><span data-ttu-id="78b43-120">회의 ID를 다시 설정</span><span class="sxs-lookup"><span data-stu-id="78b43-120">To reset the conference ID</span></span>

<span data-ttu-id="78b43-121">예를 들어 사용자가 잊어버렸다면 사용자의 회의 ID를 다시 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78b43-121">You can reset a conference ID for a user if, for example, they forget it.</span></span>
  
<span data-ttu-id="78b43-122">![Microsoft Teams 로고를 나타내는 아이콘](media/teams-logo-30x30.png) **Microsoft Teams 관리 센터 사용**</span><span class="sxs-lookup"><span data-stu-id="78b43-122">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="78b43-123">왼쪽 탐색 모음에서 **[사용자]를** 클릭한 다음 사용 가능한 사용자 목록에서 사용자를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="78b43-123">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="78b43-124">페이지 맨 위에 있는 편집을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="78b43-124">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="78b43-125">오디오 **회의에서** 회의 ID **재설정을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="78b43-125">Under **Audio Conferencing**, click **Reset conference ID**.</span></span>

4. <span data-ttu-id="78b43-126">다시 설정 **회의 ID 창에서** 재설정을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="78b43-126">In the **Reset conference ID** window, click **Reset**.</span></span> <span data-ttu-id="78b43-127">회의 ID가 자동으로 만들어지며 새 회의 ID가 있는 전자 메일이 사용자에게 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="78b43-127">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span>
  
<span data-ttu-id="78b43-128">**다음 Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="78b43-128">**Using Windows PowerShell**</span></span>

<span data-ttu-id="78b43-129">자세한 내용은 [Microsoft Teams PowerShell 참조를](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="78b43-129">See the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>


## <a name="what-else-should-you-know"></a><span data-ttu-id="78b43-130">알아야 할 다른 것은 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="78b43-130">What else should you know?</span></span>

   > [!IMPORTANT]
   >  <span data-ttu-id="78b43-131">새 전화 회의 ID가 만들어지거나 다시 설정되면 발신자에 의해 이전 전화 회의 ID를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="78b43-131">After a new conference ID is created or one is reset, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="78b43-132">새 회의 ID가 초대에 추가될 수 있도록 사용자에게 기존 모임 초대를 다시 계획할지 알려야 합니다.</span><span class="sxs-lookup"><span data-stu-id="78b43-132">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> 
  
    
- <span data-ttu-id="78b43-133">회의 ID는 오디오 회의 브리지에 설정된 자릿수 길이를 충족해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="78b43-133">The conference ID must meet the length in digits set on the audio conferencing bridge.</span></span> <span data-ttu-id="78b43-134">회의 신분증에는 사전 또는 특수 문자를 사용할 수 없습니다. 숫자만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78b43-134">You can't use alphabetic or special characters in conference IDs; only numbers can be used.</span></span>
   
    
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="78b43-135">자세한 내용은 Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="78b43-135">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="78b43-136">Windows PowerShell 관리는 사용자 및 사용자가 허용되거나 허용되지 않는 작업을 관리하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="78b43-136">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="78b43-137">이 Windows PowerShell 여러 작업을 수행할 때 일상적인 작업을 간소화할 수 있는 단일 관리 지점을 사용하여 Microsoft 365 또는 Office 365를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78b43-137">With Windows PowerShell, you can manage Microsoft 365 or Office 365 by using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="78b43-138">다음 항목을 Windows PowerShell 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="78b43-138">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="78b43-139">Office 365 PowerShell을 사용하는 이유</span><span class="sxs-lookup"><span data-stu-id="78b43-139">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="78b43-140">Microsoft 365 또는 Office 365를 관리하는 가장 좋은 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="78b43-140">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="78b43-141">자세한 내용은 Windows PowerShell [Microsoft Teams PowerShell 참조를](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="78b43-141">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="78b43-142">관련 항목</span><span class="sxs-lookup"><span data-stu-id="78b43-142">Related topics</span></span>

[<span data-ttu-id="78b43-143">Microsoft 365 또는 Office 365에서 오디오 회의 시도 또는 구매</span><span class="sxs-lookup"><span data-stu-id="78b43-143">Try or purchase Audio Conferencing in Microsoft 365 or Office 365</span></span>](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
