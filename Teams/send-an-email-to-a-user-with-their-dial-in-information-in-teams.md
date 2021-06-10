---
title: 사용자에게 오디오 회의 정보 전자 메일 보내기
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 7440d3e2-1b49-4258-bd2c-79e9072f8c8d
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-apr2020
description: 오디오 회의 정보를 통해 사용자에게 전자 메일을 보내는 방법에 대해 Microsoft Teams.
ms.openlocfilehash: 8cc0e549d502a2c7a8d8052ebe496a82e36b6648
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117216"
---
# <a name="send-an-email-to-a-user-with-their-audio-conferencing-information-in-microsoft-teams"></a><span data-ttu-id="3da80-103">오디오 회의 정보를 통해 사용자에게 전자 메일을 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3da80-103">Send an email to a user with their Audio Conferencing information in Microsoft Teams</span></span>

<span data-ttu-id="3da80-104">경우에 Microsoft Teams 사용자가 오디오 회의 정보를 보내야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3da80-104">Sometimes Microsoft Teams users may need you to send them their Audio Conferencing information.</span></span> <span data-ttu-id="3da80-105">사용자의 속성 아래에서  전자 메일을 통해 회의 정보 보내기 를 클릭하여 이 작업을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3da80-105">You can do this by clicking **Send conference info via email** under the properties for a user.</span></span> <span data-ttu-id="3da80-106">이 전자 메일을 보낼 때 다음을 포함하여 모든 오디오 회의 정보가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3da80-106">When you send this email, it will contain all of the audio conferencing information, including:</span></span>
  
- <span data-ttu-id="3da80-107">사용자의 전화 회의 전화 또는 전화 접속 전화 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="3da80-107">The conference phone or dial-in phone number for the user.</span></span>
    
- <span data-ttu-id="3da80-108">사용자의 회의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="3da80-108">The user's conference ID.</span></span>
    
   
<span data-ttu-id="3da80-109">다음은 전송된 전자 메일의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="3da80-109">Here is an example of the email that is sent:</span></span>
  
![전화 접속 회의 전자 메일 메시지의 예](media/teams-send-email-to-user-with-audio-conferencing-image1.png)

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a><span data-ttu-id="3da80-111">사용자에게 오디오 회의 정보가 있는 전자 메일 보내기</span><span class="sxs-lookup"><span data-stu-id="3da80-111">Send an email with audio conferencing information to a user</span></span>

### <a name="an-icon-showing-the-microsoft-teams-logo-using-the-microsoft-teams-admin-center"></a>![Microsoft Teams 로고를 보여주는 아이콘](media/teams-logo-30x30.png) <span data-ttu-id="3da80-113">Microsoft Teams 관리 센터 사용</span><span class="sxs-lookup"><span data-stu-id="3da80-113">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="3da80-114">왼쪽 탐색에서 **사용자** 를 클릭한 다음 사용 가능한 사용자 목록에서 사용자를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3da80-114">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="3da80-115">페이지 맨 위에 있는 편집을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3da80-115">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="3da80-116">오디오 **회의에서** 전자 메일로 **회의 정보 보내기 를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3da80-116">Under **Audio Conferencing**, click **Send conference info in email**.</span></span>


## <a name="what-else-should-you-know-about-this-email"></a><span data-ttu-id="3da80-117">이 전자 메일에 대해 알아야 할 다른 것은 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="3da80-117">What else should you know about this email?</span></span>

- <span data-ttu-id="3da80-118">오디오 회의를 사용하도록 설정한 후 조직의 사용자에게 전송된 여러 전자 메일이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3da80-118">There are several emails that are sent to users in your organization after they are enabled for audio conferencing:</span></span>
    
  - <span data-ttu-id="3da80-119">오디오 **회의** 라이선스가 할당되는 경우.</span><span class="sxs-lookup"><span data-stu-id="3da80-119">When an **Audio Conferencing** license is assigned to them.</span></span>
    
  - <span data-ttu-id="3da80-120">사용자의 오디오 회의 PIN을 수동으로 다시 설정하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3da80-120">When you manually reset the user's audio conferencing PIN.</span></span>
    
  - <span data-ttu-id="3da80-121">사용자의 회의 ID를 수동으로 다시 설정하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3da80-121">When you manually reset the user's conference ID.</span></span>
    
  - <span data-ttu-id="3da80-122">오디오 **회의** 라이선스가 제거되면</span><span class="sxs-lookup"><span data-stu-id="3da80-122">When an **Audio Conferencing** license is removed from them.</span></span>
    
  - <span data-ttu-id="3da80-123">사용자에 대한 오디오 회의 공급자가 Microsoft에서 다른 공급자 또는 **없음으로** 변경된 경우</span><span class="sxs-lookup"><span data-stu-id="3da80-123">When the audio conferencing provider for a user is changed from Microsoft to another provider or **None**.</span></span>
    
  - <span data-ttu-id="3da80-124">사용자에 대한 오디오 회의 공급자가 Microsoft로 변경된 경우</span><span class="sxs-lookup"><span data-stu-id="3da80-124">When the audio conferencing provider for a user is changed to Microsoft.</span></span>
  
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="3da80-125">자세한 정보를 Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="3da80-125">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="3da80-126">Windows PowerShell 모든 것은 사용자 관리와 사용자가 허용되거나 허용되지 않는 작업을 관리하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="3da80-126">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="3da80-127">이 Windows PowerShell 여러 작업을 수행할 때 일상적인 작업을 단순화할 수 Microsoft 365 Office 365 관리 지점을 사용하여 관리 또는 관리 작업을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3da80-127">With Windows PowerShell, you can manage Microsoft 365 or Office 365 by using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="3da80-128">다음 항목을 Windows PowerShell 다음 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3da80-128">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="3da80-129">PowerShell을 Office 365 이유</span><span class="sxs-lookup"><span data-stu-id="3da80-129">Why you need to use Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - <span data-ttu-id="3da80-130">[사용자와 함께 Microsoft 365 또는 Office 365 가장 Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="3da80-130">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
<span data-ttu-id="3da80-131">자세한 내용은 Windows PowerShell [PowerShell](/powershell/module/teams/?view=teams-ps) Microsoft Teams 참조를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3da80-131">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
  
## <a name="related-topics"></a><span data-ttu-id="3da80-132">관련 항목</span><span class="sxs-lookup"><span data-stu-id="3da80-132">Related topics</span></span>

[<span data-ttu-id="3da80-133">오디오 회의를 시도하거나 Microsoft 365 또는 Office 365</span><span class="sxs-lookup"><span data-stu-id="3da80-133">Try or purchase Audio Conferencing in Microsoft 365 or Office 365</span></span>](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)