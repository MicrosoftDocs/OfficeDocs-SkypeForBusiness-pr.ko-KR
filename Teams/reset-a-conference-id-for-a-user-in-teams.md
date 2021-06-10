---
title: 사용자에 대한 회의 ID를 Microsoft Teams
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
description: 사용자의 모임 모임 ID를 Microsoft Teams 단계에 대해 알아보고 모임 업데이트 및 마이그레이션 도구에 대한 링크를 얻습니다.
ms.openlocfilehash: edccab5da883c1707ade75519e96615ed3524bf3
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117646"
---
# <a name="reset-a-conference-id-for-a-user-in-microsoft-teams"></a><span data-ttu-id="7e301-103">사용자에 대한 회의 ID를 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7e301-103">Reset a conference ID for a user in Microsoft Teams</span></span>

<span data-ttu-id="7e301-104">동적 회의 ID는 전화 접속 전화 번호와 함께 모임 초대 맨 아래에 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e301-104">A dynamic conference ID is included at the bottom of meeting invitations along with the dial-in phone numbers that can be used by callers to call in to a meeting.</span></span> <span data-ttu-id="7e301-105">사용자가 전화 번호에 전화를 걸면 모임의 자동 참석자가 전화 회의에 참석할 수 있도록 발신자에게 이 회의 ID를 입력하도록 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="7e301-105">When the user dials the phone number, the auto attendant for the meeting will ask the caller to enter this conference ID so they can attend the meeting.</span></span>
  
> [!NOTE]
> <span data-ttu-id="7e301-106">회의 ID는 자동으로 생성되고, 7-9자리 사이로 설정되며, 사용자에 대해 오디오 회의를 사용하도록 설정할 때 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="7e301-106">Conference IDs are generated automatically, will be between 7-9 digits, and are set when you enable Audio Conferencing for a user.</span></span> <span data-ttu-id="7e301-107">**정적 회의 신분은 지원되지 않습니다.**</span><span class="sxs-lookup"><span data-stu-id="7e301-107">**Static conference IDs aren't supported.**</span></span> 

## <a name="resetting-the-conference-id-for-a-user"></a><span data-ttu-id="7e301-108">사용자에 대한 회의 ID 재설정</span><span class="sxs-lookup"><span data-stu-id="7e301-108">Resetting the conference ID for a user</span></span>

<span data-ttu-id="7e301-109">![Microsoft Teams 로고를 나타내는 아이콘](media/teams-logo-30x30.png) **Microsoft Teams 관리 센터 사용**</span><span class="sxs-lookup"><span data-stu-id="7e301-109">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="7e301-110">왼쪽 탐색에서 **사용자** 를 클릭한 다음 사용 가능한 사용자 목록에서 사용자를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7e301-110">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="7e301-111">편집을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="7e301-111">Click **Edit**.</span></span>

3. <span data-ttu-id="7e301-112">오디오 **회의에서** 회의 **ID 재설정을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="7e301-112">Under **Audio Conferencing** click **Reset conference ID**.</span></span>

2. <span data-ttu-id="7e301-113">회의 **ID 재설정 창에서** 다시 설정 **을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="7e301-113">In the **Reset conference ID** window, click **Reset**.</span></span> <span data-ttu-id="7e301-114">회의 ID가 자동으로 생성되고 새 회의 ID가 있는 사용자에게 전자 메일이 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="7e301-114">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span> <span data-ttu-id="7e301-115">기본적으로 전자 메일은 사용자에게 전송되지만 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e301-115">By default, emails are sent to users, but this can be turned off.</span></span>   

    
> [!NOTE]
> <span data-ttu-id="7e301-116">회의 ID를 다시 설정하면 새 회의 ID가 있는 전자 메일이 사용자에게 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="7e301-116">After you reset the conference ID, an email with the new conference ID will be sent to the user.</span></span> <span data-ttu-id="7e301-117">이 전자 메일은 기본 전자 메일 주소로 전송됩니다. 대부분의 경우 해당 전자 메일 Microsoft 365 Office 365 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e301-117">This email will be sent to the primary email address, in many cases, their Microsoft 365 or Office 365 mailbox.</span></span> <span data-ttu-id="7e301-118">전자 메일에는 새 회의 ID, 기본 전화 접속 전화 번호 및 기존 모임 업데이트 지침이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e301-118">The email contains the new conference ID, default dial-in phone number(s) and instructions for updating existing meetings.</span></span> 
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="what-else-should-i-know"></a><span data-ttu-id="7e301-119">다른 무엇을 알아야 하나요?</span><span class="sxs-lookup"><span data-stu-id="7e301-119">What else should I know?</span></span>

- <span data-ttu-id="7e301-120">오디오 회의 섹션에서 사용자에 대한 전자 메일로 회의 정보 보내기를 클릭하여 회의 ID 및  전화 접속 전화 번호가 포함된 전자 메일에서 모든 회의 정보를 사용자에게 보낼 **수** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e301-120">You can send all of the conferencing information to the user in an email that includes the conference ID and dial-in phone numbers by clicking **Send conference info in email** for the user in the **Audio Conferencing** section.</span></span> <span data-ttu-id="7e301-121">PIN을 보내지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7e301-121">It doesn't send the PIN.</span></span>
    
- <span data-ttu-id="7e301-122">7-9자리 회의 ID는 Teams 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="7e301-122">A 7- 9 digit conference ID is created by the Teams service.</span></span> <span data-ttu-id="7e301-123">길이는 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7e301-123">You can't change its length.</span></span>
    
- <span data-ttu-id="7e301-124">다시 설정한 후 회의 ID 에 나열된 새 회의 **ID를 볼 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="7e301-124">After it has been reset, you can see the new conference ID listed under **Conference ID**.</span></span>
    
- <span data-ttu-id="7e301-125">새 회의 ID를 만든 후 이전 회의 ID는 발신자에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7e301-125">After a new conference ID is created, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="7e301-126">새 회의 ID가 초대에 추가될 수 있도록 기존 모임 초대를 다시 계획할 수 있도록 사용자에게 알려야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e301-126">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> 

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="7e301-127">자세한 정보를 Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="7e301-127">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="7e301-128">Windows PowerShell 모든 것은 사용자 관리와 사용자가 허용되거나 허용되지 않는 작업을 관리하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="7e301-128">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="7e301-129">이 Windows PowerShell 여러 작업을 수행할 때 일상적인 작업을 단순화할 수 Microsoft 365 Office 365 관리 지점을 사용하여 관리 또는 관리 작업을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e301-129">With Windows PowerShell, you can manage Microsoft 365 or Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="7e301-130">다음 항목을 Windows PowerShell 다음 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7e301-130">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="7e301-131">PowerShell을 Office 365 이유</span><span class="sxs-lookup"><span data-stu-id="7e301-131">Why you need to use Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - <span data-ttu-id="7e301-132">[사용자와 함께 Microsoft 365 또는 Office 365 가장 Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="7e301-132">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
<span data-ttu-id="7e301-133">자세한 내용은 Windows PowerShell [PowerShell](/powershell/module/teams/?view=teams-ps) Microsoft Teams 참조를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7e301-133">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="7e301-134">관련 항목</span><span class="sxs-lookup"><span data-stu-id="7e301-134">Related topics</span></span>

[<span data-ttu-id="7e301-135">오디오 회의 PIN 재설정</span><span class="sxs-lookup"><span data-stu-id="7e301-135">Reset the Audio Conferencing PIN</span></span>](reset-the-audio-conferencing-pin-in-teams.md)