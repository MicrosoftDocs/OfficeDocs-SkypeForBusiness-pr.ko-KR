---
title: Microsoft Teams에서 사용자의 회의 ID 다시 설정
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 6e12242c-55f7-4bf4-90d7-0f36c0326b8e
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
- seo-marvel-mar2020
description: Microsoft Teams에서 사용자의 모임 회의 ID를 다시 설정하는 단계를 알아보고 모임 업데이트 및 마이그레이션 도구에 대한 링크를 얻습니다.
ms.openlocfilehash: 52b547fee5bf027bcef21914e3ba3aa79b0e4e08
ms.sourcegitcommit: 7a9c63ee790108eaa61950ce28ae8027311039d9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/13/2020
ms.locfileid: "46662128"
---
# <a name="reset-a-conference-id-for-a-user-in-microsoft-teams"></a><span data-ttu-id="55720-103">Microsoft Teams에서 사용자의 회의 ID 다시 설정</span><span class="sxs-lookup"><span data-stu-id="55720-103">Reset a conference ID for a user in Microsoft Teams</span></span>

<span data-ttu-id="55720-104">동적 전화 회의 ID는 발신자에서 모임에 전화 접속하는 데 사용할 수 있는 전화 접속 전화 번호와 함께 모임 초대의 아래쪽에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="55720-104">A dynamic conference ID is included at the bottom of meeting invitations along with the dial-in phone numbers that can be used by callers to call in to a meeting.</span></span> <span data-ttu-id="55720-105">사용자가 전화 번호로 전화를 걸면 모임의 자동 전화 접속자가 발신자가 이 전화 회의 ID를 입력하도록 요청하여 모임에 참석할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55720-105">When the user dials the phone number, the auto attendant for the meeting will ask the caller to enter this conference ID so they can attend the meeting.</span></span>
  
> [!NOTE]
> <span data-ttu-id="55720-106">회의 ID는 자동으로 생성되고, 7-9자리 사이가 되며, 사용자에 대해 오디오 회의를 사용하도록 설정하면 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="55720-106">Conference IDs are generated automatically, will be between 7-9 digits, and are set when you enable Audio Conferencing for a user.</span></span> <span data-ttu-id="55720-107">**정적 회의 신분은 지원되지 않습니다.**</span><span class="sxs-lookup"><span data-stu-id="55720-107">**Static conference IDs aren't supported.**</span></span> 

## <a name="resetting-the-conference-id-for-a-user"></a><span data-ttu-id="55720-108">사용자의 회의 ID 다시 설정</span><span class="sxs-lookup"><span data-stu-id="55720-108">Resetting the conference ID for a user</span></span>

<span data-ttu-id="55720-109">![Microsoft Teams 로고를 나타내는 아이콘](media/teams-logo-30x30.png) **Microsoft Teams 관리 센터 사용**</span><span class="sxs-lookup"><span data-stu-id="55720-109">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="55720-110">왼쪽 탐색 모음에서 **[사용자]를** 클릭한 다음 사용 가능한 사용자 목록에서 사용자를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="55720-110">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="55720-111">편집을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="55720-111">Click **Edit**.</span></span>

3. <span data-ttu-id="55720-112">오디오 **회의에서** 회의 **ID 재설정을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="55720-112">Under **Audio Conferencing** click **Reset conference ID**.</span></span>

2. <span data-ttu-id="55720-113">다시 설정 **회의 ID 창에서** 재설정을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="55720-113">In the **Reset conference ID** window, click **Reset**.</span></span> <span data-ttu-id="55720-114">회의 ID가 자동으로 만들어지며 새 회의 ID가 있는 전자 메일이 사용자에게 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="55720-114">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span> <span data-ttu-id="55720-115">기본적으로 전자 메일은 사용자에게 전송되지만 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55720-115">By default, emails are sent to users, but this can be turned off.</span></span>   

    
> [!NOTE]
> <span data-ttu-id="55720-116">회의 ID를 다시 설정하면 새 회의 ID가 있는 전자 메일이 사용자에게 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="55720-116">After you reset the conference ID, an email with the new conference ID will be sent to the user.</span></span> <span data-ttu-id="55720-117">이 전자 메일은 대부분의 경우 Microsoft 365 또는 Office 365 사서함의 기본 전자 메일 주소로 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="55720-117">This email will be sent to the primary email address, in many cases, their Microsoft 365 or Office 365 mailbox.</span></span> <span data-ttu-id="55720-118">전자 메일에는 새 전화 회의 ID, 기본 전화 접속 전화 번호 및 기존 모임 업데이트 지침이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55720-118">The email contains the new conference ID, default dial-in phone number(s) and instructions for updating existing meetings.</span></span> 
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="what-else-should-i-know"></a><span data-ttu-id="55720-119">알아야 할 다른 것은 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="55720-119">What else should I know?</span></span>

- <span data-ttu-id="55720-120">**오디오** 회의 섹션에서 사용자의 전자 메일로 전화 회의 정보 보내기를 클릭하여 전화 회의 ID 및  전화 접속 전화 번호가 포함된 전자 메일로 모든 회의 정보를 사용자에게 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55720-120">You can send all of the conferencing information to the user in an email that includes the conference ID and dial-in phone numbers by clicking **Send conference info in email** for the user in the **Audio Conferencing** section.</span></span> <span data-ttu-id="55720-121">PIN은 보내지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="55720-121">It doesn't send the PIN.</span></span>
    
- <span data-ttu-id="55720-122">Teams 서비스에 의해 7-9자리 회의 ID가 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="55720-122">A 7- 9 digit conference ID is created by the Teams service.</span></span> <span data-ttu-id="55720-123">길이는 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="55720-123">You can't change its length.</span></span>
    
- <span data-ttu-id="55720-124">다시 설정되면 회의 ID 아래에 나열된 새 회의 **ID를 볼 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="55720-124">After it has been reset, you can see the new conference ID listed under **Conference ID**.</span></span>
    
- <span data-ttu-id="55720-125">새 전화 회의 ID가 생성되면 발신자에 의해 이전 전화 회의 ID를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="55720-125">After a new conference ID is created, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="55720-126">새 회의 ID가 초대에 추가될 수 있도록 사용자에게 기존 모임 초대를 다시 계획할지 알려야 합니다.</span><span class="sxs-lookup"><span data-stu-id="55720-126">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> 

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="55720-127">자세한 내용은 Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="55720-127">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="55720-128">Windows PowerShell 관리는 사용자 및 사용자가 허용되거나 허용되지 않는 작업을 관리하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="55720-128">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="55720-129">이 Windows PowerShell 여러 작업을 수행할 때 일상적인 작업을 간소화할 수 있는 단일 관리 지점을 사용하여 Microsoft 365 또는 Office 365를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55720-129">With Windows PowerShell, you can manage Microsoft 365 or Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="55720-130">다음 항목을 Windows PowerShell 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="55720-130">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="55720-131">Office 365 PowerShell을 사용하는 이유</span><span class="sxs-lookup"><span data-stu-id="55720-131">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="55720-132">Microsoft 365 또는 Office 365를 관리하는 가장 좋은 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="55720-132">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="55720-133">자세한 내용은 Windows PowerShell [Microsoft Teams PowerShell 참조를](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="55720-133">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="55720-134">관련 항목</span><span class="sxs-lookup"><span data-stu-id="55720-134">Related topics</span></span>

[<span data-ttu-id="55720-135">오디오 회의 PIN 재설정</span><span class="sxs-lookup"><span data-stu-id="55720-135">Reset the Audio Conferencing PIN</span></span>](reset-the-audio-conferencing-pin-in-teams.md)
