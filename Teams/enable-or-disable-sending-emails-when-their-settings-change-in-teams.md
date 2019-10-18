---
title: Microsoft 팀에서 오디오 회의 설정이 변경 될 때 전자 메일 보내기 사용 또는 사용 안 함
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
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Pin 변경 또는 Microsoft 팀의 기본 회의 번호 변경 등의 설정이 사용자에 게 전자 메일을 보내는 것을 허용 하거나 해제 하는 방법에 대해 알아봅니다. '
ms.openlocfilehash: 906781f79f10500fc8808a579abe9707f0f736ac
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2019
ms.locfileid: "37573066"
---
# <a name="enable-or-disable-sending-emails-when-audio-conferencing-settings-change-in-microsoft-teams"></a><span data-ttu-id="04cdd-103">Microsoft 팀에서 오디오 회의 설정이 변경 될 때 전자 메일 보내기 사용 또는 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="04cdd-103">Enable or disable sending emails when Audio Conferencing settings change in Microsoft Teams</span></span>

<span data-ttu-id="04cdd-104">사용자가 오디오 회의를 사용 하도록 설정 되 면 전자 메일을 통해 자동으로 알림을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="04cdd-104">Users are automatically notified by email when they are enabled for Audio Conferencing.</span></span> <span data-ttu-id="04cdd-105">그러나 Microsoft 팀 사용자에 게 전송 되는 전자 메일 수를 줄여야 하는 경우가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04cdd-105">There may be times, however, when you want to reduce the number of emails that are sent to Microsoft Teams users.</span></span> <span data-ttu-id="04cdd-106">이러한 경우 전자 메일 보내기를 사용 하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04cdd-106">In such cases, you can disable sending email.</span></span>
  
<span data-ttu-id="04cdd-107">전자 메일 보내기를 사용 하지 않도록 설정 하는 경우 오디오 회의를 사용 하거나 사용 하지 않도록 설정 하는 경우, PIN이 다시 설정 될 때, 전화 회의 ID 및 기본 회의 전화 번호가 변경 되는 경우의 전자 메일을 포함 하 여 사용자에 게 오디오 회의 전자 메일이 전송 되지 않습니다. .</span><span class="sxs-lookup"><span data-stu-id="04cdd-107">If you disable sending emails, Audio Conferencing emails won't be sent to your users, including emails for when users are enabled or disabled for audio conferencing, when their PIN is reset, and when the conference ID and the default conferencing phone number changes.</span></span>
  
<span data-ttu-id="04cdd-108">다음은 오디오 회의를 사용 하도록 설정 했을 때 사용자에 게 전송 되는 전자 메일의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="04cdd-108">Here is an example of the email that is sent to users when they are enabled for Audio Conferencing:</span></span>
  
![오디오 회의 전자 메일 메시지의 예](media/teams-emails-sent-to-users-when-settings-change-image1.png)
  
## <a name="when-are-emails-being-sent-to-your-users"></a><span data-ttu-id="04cdd-110">사용자에 게 전자 메일이 전송 되는 경우</span><span class="sxs-lookup"><span data-stu-id="04cdd-110">When are emails being sent to your users?</span></span>

- <span data-ttu-id="04cdd-111">오디오 회의를 사용 하도록 설정 하면 조직의 사용자에 게 여러 개의 전자 메일이 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="04cdd-111">There are several emails that are sent to users in your organization after they are enabled for audio conferencing:</span></span>
    
  - <span data-ttu-id="04cdd-112">**오디오 회의** 라이선스가 할당 된 경우</span><span class="sxs-lookup"><span data-stu-id="04cdd-112">When an **Audio Conferencing** license is assigned to them.</span></span>
    
  - <span data-ttu-id="04cdd-113">사용자의 오디오 회의 PIN을 수동으로 다시 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="04cdd-113">When you manually reset the user's audio conferencing PIN.</span></span>
    
  - <span data-ttu-id="04cdd-114">수동으로 사용자의 전화 회의 ID를 다시 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="04cdd-114">When you manually reset the user's conference ID.</span></span>
    
  - <span data-ttu-id="04cdd-115">**오디오 회의** 라이선스가 해당 항목에서 제거 됩니다.</span><span class="sxs-lookup"><span data-stu-id="04cdd-115">When the **Audio Conferencing** license is removed from them.</span></span>
    
  - <span data-ttu-id="04cdd-116">사용자의 오디오 회의 공급자가 Microsoft에서 다른 공급자 또는 **없음**으로 변경 되는 경우</span><span class="sxs-lookup"><span data-stu-id="04cdd-116">When the audio conferencing provider of a user is changed from Microsoft to another provider or **None**.</span></span>
    
  - <span data-ttu-id="04cdd-117">사용자의 오디오 회의 공급자가 Microsoft로 변경 된 경우</span><span class="sxs-lookup"><span data-stu-id="04cdd-117">When the audio conferencing provider of a user is changed to Microsoft.</span></span>


## <a name="enable-or-disable-email-from-being-sent-to-users"></a><span data-ttu-id="04cdd-118">사용자에 게 전자 메일을 보낼 수 있도록 설정 또는 해제</span><span class="sxs-lookup"><span data-stu-id="04cdd-118">Enable or disable email from being sent to users</span></span>

<span data-ttu-id="04cdd-119">Microsoft 팀 또는 Windows PowerShell을 사용 하 여 사용자에 게 전송 되는 전자 메일을 사용 하거나 사용 하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04cdd-119">You can use Microsoft Teams or Windows PowerShell to enable or disable email sent to users.</span></span>

<span data-ttu-id="04cdd-120">![](media/teams-logo-30x30.png) **Microsoft 팀 관리 센터를 사용 하 여** microsoft 팀 로고를 표시 하는 아이콘</span><span class="sxs-lookup"><span data-stu-id="04cdd-120">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="04cdd-121">왼쪽 탐색 창에서 **모임** > **회의 브리지로**이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="04cdd-121">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="04cdd-122">**회의 브리지** 페이지 맨 위에서 **브리지 설정을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="04cdd-122">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="04cdd-123">**브리지 설정** 창에서 **전화 접속 설정이 변경 되는 경우 자동으로 사용자에 게 전자 메일 보내기**사용 또는 사용 안 함을 설정 하거나 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="04cdd-123">In the **Bridge settings** pane, enable or disable **Automatically send emails to users if their dial-in settings change**.</span></span>

4. <span data-ttu-id="04cdd-124">**저장**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="04cdd-124">Click **Save**.</span></span>

  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

<span data-ttu-id="04cdd-125">**Windows PowerShell 사용**</span><span class="sxs-lookup"><span data-stu-id="04cdd-125">**Using Windows PowerShell**</span></span>
  
<span data-ttu-id="04cdd-126">자세한 내용은 [Microsoft 팀 PowerShell 참조](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="04cdd-126">See the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>

    
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="04cdd-127">Windows PowerShell에 대 한 자세한 정보를 확인 하 고 싶으신가요?</span><span class="sxs-lookup"><span data-stu-id="04cdd-127">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="04cdd-128">Windows PowerShell은 사용자 및 허용 되지 않거나 수행할 수 있는 사용자를 관리 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="04cdd-128">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="04cdd-129">Windows PowerShell을 사용 하면 여러 작업을 수행할 때 일상 업무를 단순화할 수 있는 단일 관리 지점을 사용 하 여 Office 365를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04cdd-129">With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="04cdd-130">Windows PowerShell을 시작 하려면 다음 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="04cdd-130">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="04cdd-131">Office 365 PowerShell을 사용 해야 하는 이유</span><span class="sxs-lookup"><span data-stu-id="04cdd-131">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="04cdd-132">Windows PowerShell을 사용 하 여 Office 365를 관리 하는 가장 좋은 방법</span><span class="sxs-lookup"><span data-stu-id="04cdd-132">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="04cdd-133">Windows PowerShell에 대 한 자세한 내용은 [Microsoft 팀 PowerShell 참조](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) 에서 자세한 내용을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="04cdd-133">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
  
## <a name="related-topics"></a><span data-ttu-id="04cdd-134">관련 항목</span><span class="sxs-lookup"><span data-stu-id="04cdd-134">Related topics</span></span>

[<span data-ttu-id="04cdd-135">오디오 회의 설정이 변경 될 때 사용자에 게 전송 되는 전자 메일</span><span class="sxs-lookup"><span data-stu-id="04cdd-135">Emails sent to users when their Audio Conferencing settings change</span></span>](emails-sent-to-users-when-their-settings-change-in-teams.md)

[<span data-ttu-id="04cdd-136">오디오 회의 정보를 사용 하 여 사용자에 게 전자 메일 보내기</span><span class="sxs-lookup"><span data-stu-id="04cdd-136">Send an email to a user with their Audio Conferencing information</span></span>](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)


