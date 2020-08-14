---
title: Microsoft 팀에서 사용자에 대 한 전화 회의 ID 다시 설정
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
description: Microsoft 팀에서 사용자의 모임 전화 회의 ID를 다시 설정 하는 단계와 모임 업데이트 및 마이그레이션 도구에 대 한 링크를 확인 하는 방법에 대해 알아보세요.
ms.openlocfilehash: 52b547fee5bf027bcef21914e3ba3aa79b0e4e08
ms.sourcegitcommit: 7a9c63ee790108eaa61950ce28ae8027311039d9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/13/2020
ms.locfileid: "46662128"
---
# <a name="reset-a-conference-id-for-a-user-in-microsoft-teams"></a><span data-ttu-id="a9e73-103">Microsoft 팀에서 사용자에 대 한 전화 회의 ID 다시 설정</span><span class="sxs-lookup"><span data-stu-id="a9e73-103">Reset a conference ID for a user in Microsoft Teams</span></span>

<span data-ttu-id="a9e73-104">동적 전화 회의 ID는 전화 접속 전화 번호와 함께 모임 초대 맨 아래에 포함 되며, 발신자가 모임에 전화를 걸 때 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9e73-104">A dynamic conference ID is included at the bottom of meeting invitations along with the dial-in phone numbers that can be used by callers to call in to a meeting.</span></span> <span data-ttu-id="a9e73-105">사용자가 전화 번호를 누르면 모임에 대 한 자동 전화 교환은 발신자에 게이 회의 ID를 입력 하도록 요청 하 여 모임에 참석할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9e73-105">When the user dials the phone number, the auto attendant for the meeting will ask the caller to enter this conference ID so they can attend the meeting.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a9e73-106">전화 회의 Id는 자동으로 생성 되며, 사용자에 대 한 오디오 회의를 사용 하도록 설정 하는 경우에는 7-9 자리에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a9e73-106">Conference IDs are generated automatically, will be between 7-9 digits, and are set when you enable Audio Conferencing for a user.</span></span> <span data-ttu-id="a9e73-107">**정적 회의 Id는 지원 되지 않습니다.**</span><span class="sxs-lookup"><span data-stu-id="a9e73-107">**Static conference IDs aren't supported.**</span></span> 

## <a name="resetting-the-conference-id-for-a-user"></a><span data-ttu-id="a9e73-108">사용자의 전화 회의 ID 다시 설정</span><span class="sxs-lookup"><span data-stu-id="a9e73-108">Resetting the conference ID for a user</span></span>

<span data-ttu-id="a9e73-109">![Microsoft Teams 로고를 나타내는 아이콘](media/teams-logo-30x30.png) **Microsoft Teams 관리 센터 사용**</span><span class="sxs-lookup"><span data-stu-id="a9e73-109">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="a9e73-110">왼쪽 탐색 창에서 **사용자**를 클릭 한 다음 사용 가능한 사용자 목록에서 사용자를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9e73-110">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="a9e73-111">**편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9e73-111">Click **Edit**.</span></span>

3. <span data-ttu-id="a9e73-112">**오디오 회의** 에서 **전화 회의 ID 재설정**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9e73-112">Under **Audio Conferencing** click **Reset conference ID**.</span></span>

2. <span data-ttu-id="a9e73-113">**전화 회의 ID 다시 설정** 창에서 **원래 대로**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9e73-113">In the **Reset conference ID** window, click **Reset**.</span></span> <span data-ttu-id="a9e73-114">전화 회의 ID가 자동으로 만들어지고 새 전화 회의 ID를 사용 하 여 사용자에 게 전자 메일이 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a9e73-114">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span> <span data-ttu-id="a9e73-115">기본적으로 전자 메일은 사용자에 게 전송 되지만,이 기능은 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9e73-115">By default, emails are sent to users, but this can be turned off.</span></span>   

    
> [!NOTE]
> <span data-ttu-id="a9e73-116">전화 회의 ID를 다시 설정 하면 새 전화 회의 ID가 포함 된 전자 메일이 사용자에 게 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a9e73-116">After you reset the conference ID, an email with the new conference ID will be sent to the user.</span></span> <span data-ttu-id="a9e73-117">이 전자 메일은 대부분의 경우 Microsoft 365 또는 Office 365 사서함에 기본 전자 메일 주소로 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a9e73-117">This email will be sent to the primary email address, in many cases, their Microsoft 365 or Office 365 mailbox.</span></span> <span data-ttu-id="a9e73-118">전자 메일에는 새로운 전화 회의 ID, 기본 전화 접속 전화 번호 및 기존 모임 업데이트에 대 한 지침이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9e73-118">The email contains the new conference ID, default dial-in phone number(s) and instructions for updating existing meetings.</span></span> 
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="what-else-should-i-know"></a><span data-ttu-id="a9e73-119">알아야 할 기타 사항</span><span class="sxs-lookup"><span data-stu-id="a9e73-119">What else should I know?</span></span>

- <span data-ttu-id="a9e73-120">**오디오 회의** 섹션의 사용자에 대 한 **전자 메일에서 회의 정보 보내기를** 클릭 하 여 전화 회의 ID를 포함 하는 전자 메일에서 모든 회의 정보를 사용자에 게 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9e73-120">You can send all of the conferencing information to the user in an email that includes the conference ID and dial-in phone numbers by clicking **Send conference info in email** for the user in the **Audio Conferencing** section.</span></span> <span data-ttu-id="a9e73-121">PIN은 전송 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a9e73-121">It doesn't send the PIN.</span></span>
    
- <span data-ttu-id="a9e73-122">7-9 자리 회의 ID는 팀 서비스에 의해 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a9e73-122">A 7- 9 digit conference ID is created by the Teams service.</span></span> <span data-ttu-id="a9e73-123">길이는 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a9e73-123">You can't change its length.</span></span>
    
- <span data-ttu-id="a9e73-124">다시 설정한 후에는 **전화 회의 id**아래에 나열 된 새 전화 회의 id를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9e73-124">After it has been reset, you can see the new conference ID listed under **Conference ID**.</span></span>
    
- <span data-ttu-id="a9e73-125">새 전화 회의 ID를 만든 후에는 발신자가 이전 회의 ID를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a9e73-125">After a new conference ID is created, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="a9e73-126">사용자에 게 기존 모임 초대를 다시 예약 하 여 새 회의 ID가 초대에 추가 되었는지 알려 주어 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9e73-126">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> 

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="a9e73-127">Windows PowerShell에 대 한 자세한 정보를 확인 하 고 싶으신가요?</span><span class="sxs-lookup"><span data-stu-id="a9e73-127">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="a9e73-128">Windows PowerShell은 사용자 및 허용 되지 않거나 수행할 수 있는 사용자를 관리 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9e73-128">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="a9e73-129">Windows PowerShell을 사용 하면 여러 작업을 수행할 때 일상 업무를 단순화할 수 있는 단일 관리 지점을 사용 하 여 Microsoft 365 또는 Office 365를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9e73-129">With Windows PowerShell, you can manage Microsoft 365 or Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="a9e73-130">Windows PowerShell을 시작 하려면 다음 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a9e73-130">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="a9e73-131">Office 365 PowerShell을 사용 해야 하는 이유</span><span class="sxs-lookup"><span data-stu-id="a9e73-131">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="a9e73-132">Windows PowerShell을 사용 하 여 Microsoft 365 또는 Office 365을 관리 하는 최상의 방법</span><span class="sxs-lookup"><span data-stu-id="a9e73-132">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="a9e73-133">Windows PowerShell에 대 한 자세한 내용은 [Microsoft 팀 PowerShell 참조](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) 에서 자세한 내용을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a9e73-133">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="a9e73-134">관련 항목</span><span class="sxs-lookup"><span data-stu-id="a9e73-134">Related topics</span></span>

[<span data-ttu-id="a9e73-135">오디오 회의 PIN 재설정</span><span class="sxs-lookup"><span data-stu-id="a9e73-135">Reset the Audio Conferencing PIN</span></span>](reset-the-audio-conferencing-pin-in-teams.md)
