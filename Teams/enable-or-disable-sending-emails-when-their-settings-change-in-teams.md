---
title: 오디오 회의 설정이 변경될 때 전자 메일 옵션
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 26ea19d3-e420-4fc1-baa3-2692d17e5e1d
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
description: '핀이 변경되거나 기본 회의 번호가 변경될 Skype 사용자에게 전자 메일을 보내지 않도록 설정하거나 사용하지 않도록 설정하는 Microsoft Teams. '
ms.openlocfilehash: e1bb6df0a443f01ed3c9bc70d03eedc05f217ce4
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51092706"
---
# <a name="enable-or-disable-sending-emails-when-audio-conferencing-settings-change-in-microsoft-teams"></a><span data-ttu-id="2590d-103">오디오 회의 설정이 변경될 때 전자 메일 보내기 사용 또는 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2590d-103">Enable or disable sending emails when Audio Conferencing settings change in Microsoft Teams</span></span>

<span data-ttu-id="2590d-104">오디오 회의를 사용하도록 설정하면 사용자에게 전자 메일로 자동으로 알림이 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="2590d-104">Users are automatically notified by email when they are enabled for Audio Conferencing.</span></span> <span data-ttu-id="2590d-105">그러나 사용자에게 전송되는 전자 메일의 수를 줄이지 않을 Microsoft Teams 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2590d-105">There may be times, however, when you want to reduce the number of emails that are sent to Microsoft Teams users.</span></span> <span data-ttu-id="2590d-106">이러한 경우 전자 메일 보내기 기능을 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2590d-106">In such cases, you can disable sending email.</span></span>
  
<span data-ttu-id="2590d-107">전자 메일 보내기 기능을 사용하지 않도록 설정하면 사용자가 오디오 회의를 사용하도록 설정하거나 사용하지 않도록 설정한 경우, PIN이 재설정되는 경우 및 회의 ID 및 기본 회의 전화 번호가 변경될 때 전자 메일을 포함하여 오디오 회의 전자 메일이 사용자에게 전송되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2590d-107">If you disable sending emails, Audio Conferencing emails won't be sent to your users, including emails for when users are enabled or disabled for audio conferencing, when their PIN is reset, and when the conference ID and the default conferencing phone number changes.</span></span>
  
<span data-ttu-id="2590d-108">다음은 오디오 회의를 사용하도록 설정하면 사용자에게 전송된 전자 메일의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="2590d-108">Here is an example of the email that is sent to users when they are enabled for Audio Conferencing:</span></span>
  
![오디오 회의 전자 메일 메시지의 예](media/teams-emails-sent-to-users-when-settings-change-image1.png)
  
## <a name="when-are-emails-being-sent-to-your-users"></a><span data-ttu-id="2590d-110">사용자에게 전자 메일은 언제 전송하나요?</span><span class="sxs-lookup"><span data-stu-id="2590d-110">When are emails being sent to your users?</span></span>

- <span data-ttu-id="2590d-111">오디오 회의를 사용하도록 설정한 후 조직의 사용자에게 전송된 여러 전자 메일이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2590d-111">There are several emails that are sent to users in your organization after they are enabled for audio conferencing:</span></span>
    
  - <span data-ttu-id="2590d-112">오디오 **회의** 라이선스가 할당되는 경우.</span><span class="sxs-lookup"><span data-stu-id="2590d-112">When an **Audio Conferencing** license is assigned to them.</span></span>
    
  - <span data-ttu-id="2590d-113">사용자의 오디오 회의 PIN을 수동으로 다시 설정하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2590d-113">When you manually reset the user's audio conferencing PIN.</span></span>
    
  - <span data-ttu-id="2590d-114">사용자의 회의 ID를 수동으로 다시 설정하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2590d-114">When you manually reset the user's conference ID.</span></span>
    
  - <span data-ttu-id="2590d-115">오디오 **회의** 라이선스가 해당 라이선스에서 제거되면</span><span class="sxs-lookup"><span data-stu-id="2590d-115">When the **Audio Conferencing** license is removed from them.</span></span>
    
  - <span data-ttu-id="2590d-116">사용자의 오디오 회의 공급자가 Microsoft에서 다른 공급자 또는 **없음으로** 변경된 경우</span><span class="sxs-lookup"><span data-stu-id="2590d-116">When the audio conferencing provider of a user is changed from Microsoft to another provider or **None**.</span></span>
    
  - <span data-ttu-id="2590d-117">사용자의 오디오 회의 공급자가 Microsoft로 변경된 경우</span><span class="sxs-lookup"><span data-stu-id="2590d-117">When the audio conferencing provider of a user is changed to Microsoft.</span></span>


## <a name="enable-or-disable-email-from-being-sent-to-users"></a><span data-ttu-id="2590d-118">사용자에게 전자 메일이 전송되지 않도록 설정하거나 사용하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="2590d-118">Enable or disable email from being sent to users</span></span>

<span data-ttu-id="2590d-119">사용자가 보낸 전자 Microsoft Teams Windows PowerShell 사용하도록 설정하거나 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2590d-119">You can use Microsoft Teams or Windows PowerShell to enable or disable email sent to users.</span></span>

<span data-ttu-id="2590d-120">![Microsoft Teams 로고를 나타내는 아이콘](media/teams-logo-30x30.png) **Microsoft Teams 관리 센터 사용**</span><span class="sxs-lookup"><span data-stu-id="2590d-120">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="2590d-121">왼쪽 탐색에서 모임 회의  >  **브리지로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="2590d-121">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="2590d-122">컨퍼런스 브리지  페이지의 맨 위에 있는 브리지 설정을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="2590d-122">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="2590d-123">브리지 **설정 창에서** 전화 접속 설정이 변경될 경우 사용자에게 자동으로 전자 메일 보내기를 사용하도록 설정하거나 **사용하지 않도록 설정합니다.**</span><span class="sxs-lookup"><span data-stu-id="2590d-123">In the **Bridge settings** pane, enable or disable **Automatically send emails to users if their dial-in settings change**.</span></span>

4. <span data-ttu-id="2590d-124">**저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="2590d-124">Click **Save**.</span></span>

  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

<span data-ttu-id="2590d-125">**Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="2590d-125">**Using Windows PowerShell**</span></span>
  
<span data-ttu-id="2590d-126">자세한 [내용은 Microsoft Teams PowerShell 참조를](/powershell/module/teams/?view=teams-ps) 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2590d-126">See the [Microsoft Teams PowerShell reference](/powershell/module/teams/?view=teams-ps) for more information.</span></span>

    
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="2590d-127">자세한 정보를 Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="2590d-127">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="2590d-128">Windows PowerShell 모든 것은 사용자 관리와 사용자가 허용되거나 허용되지 않는 작업을 관리하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="2590d-128">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="2590d-129">이 Windows PowerShell 여러 작업을 수행할 때 일상적인 작업을 단순화할 수 Microsoft 365 Office 365 관리 지점을 사용하여 관리 또는 관리 작업을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2590d-129">With Windows PowerShell, you can manage Microsoft 365 or Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="2590d-130">다음 항목을 Windows PowerShell 다음 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2590d-130">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="2590d-131">PowerShell을 Office 365 이유</span><span class="sxs-lookup"><span data-stu-id="2590d-131">Why you need to use Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - <span data-ttu-id="2590d-132">[데이터를 사용하여 Office 365 관리하는 가장 Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="2590d-132">[Best ways to manage Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
<span data-ttu-id="2590d-133">자세한 내용은 Windows PowerShell [PowerShell](/powershell/module/teams/?view=teams-ps) Microsoft Teams 참조를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2590d-133">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
  
## <a name="related-topics"></a><span data-ttu-id="2590d-134">관련 항목</span><span class="sxs-lookup"><span data-stu-id="2590d-134">Related topics</span></span>

[<span data-ttu-id="2590d-135">오디오 회의 설정이 변경될 때 사용자에게 전송된 전자 메일</span><span class="sxs-lookup"><span data-stu-id="2590d-135">Emails sent to users when their Audio Conferencing settings change</span></span>](emails-sent-to-users-when-their-settings-change-in-teams.md)

[<span data-ttu-id="2590d-136">오디오 회의 정보를 사용하여 사용자에게 전자 메일 보내기</span><span class="sxs-lookup"><span data-stu-id="2590d-136">Send an email to a user with their Audio Conferencing information</span></span>](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)