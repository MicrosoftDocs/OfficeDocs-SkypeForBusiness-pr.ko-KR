---
title: 사용자에 게 오디오 회의 정보를 전자 메일로 보내기
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
description: Microsoft 팀의 오디오 회의 정보를 사용 하 여 사용자에 게 전자 메일을 보내는 방법에 대해 알아봅니다.
ms.openlocfilehash: d1cab63d9e89bb62254a838de708c022ef0b0993
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/27/2020
ms.locfileid: "43905610"
---
# <a name="send-an-email-to-a-user-with-their-audio-conferencing-information-in-microsoft-teams"></a><span data-ttu-id="81104-103">Microsoft 팀의 오디오 회의 정보를 사용 하 여 사용자에 게 전자 메일 보내기</span><span class="sxs-lookup"><span data-stu-id="81104-103">Send an email to a user with their Audio Conferencing information in Microsoft Teams</span></span>

<span data-ttu-id="81104-104">때로는 Microsoft 팀 사용자가 자신의 오디오 회의 정보를 보내야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81104-104">Sometimes Microsoft Teams users may need you to send them their Audio Conferencing information.</span></span> <span data-ttu-id="81104-105">이 작업은 사용자의 속성 아래에서 **전자 메일을 통해 회의 정보 보내기를** 클릭 하 여 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81104-105">You can do this by clicking **Send conference info via email** under the properties for a user.</span></span> <span data-ttu-id="81104-106">이 전자 메일을 보낼 때 다음을 비롯 한 모든 오디오 회의 정보가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="81104-106">When you send this email, it will contain all of the audio conferencing information, including:</span></span>
  
- <span data-ttu-id="81104-107">사용자의 컨퍼런스 전화 또는 전화 접속 전화 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="81104-107">The conference phone or dial-in phone number for the user.</span></span>
    
- <span data-ttu-id="81104-108">사용자의 전화 회의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="81104-108">The user's conference ID.</span></span>
    
   
<span data-ttu-id="81104-109">다음은 전송 되는 전자 메일의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="81104-109">Here is an example of the email that is sent:</span></span>
  
![전화 접속 회의 전자 메일 메시지의 예](media/teams-send-email-to-user-with-audio-conferencing-image1.png)

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a><span data-ttu-id="81104-111">오디오 회의 정보를 사용 하 여 사용자에 게 전자 메일 보내기</span><span class="sxs-lookup"><span data-stu-id="81104-111">Send an email with audio conferencing information to a user</span></span>

### <a name="an-icon-showing-the-microsoft-teams-logo-using-the-microsoft-teams-admin-center"></a>![Microsoft Teams 로고를 보여주는 아이콘](media/teams-logo-30x30.png) <span data-ttu-id="81104-113">Microsoft Teams 관리 센터 사용</span><span class="sxs-lookup"><span data-stu-id="81104-113">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="81104-114">왼쪽 탐색 창에서 **사용자**를 클릭 한 다음 사용 가능한 사용자 목록에서 사용자를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="81104-114">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="81104-115">페이지 맨 위에서 **편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="81104-115">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="81104-116">**오디오 회의**에서 **전자 메일로 회의 정보 보내기를**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="81104-116">Under **Audio Conferencing**, click **Send conference info in email**.</span></span>


## <a name="what-else-should-you-know-about-this-email"></a><span data-ttu-id="81104-117">이 전자 메일에 대해 알아야 할 기타 사항</span><span class="sxs-lookup"><span data-stu-id="81104-117">What else should you know about this email?</span></span>

- <span data-ttu-id="81104-118">오디오 회의를 사용 하도록 설정 하면 조직의 사용자에 게 여러 개의 전자 메일이 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="81104-118">There are several emails that are sent to users in your organization after they are enabled for audio conferencing:</span></span>
    
  - <span data-ttu-id="81104-119">**오디오 회의** 라이선스가 할당 된 경우</span><span class="sxs-lookup"><span data-stu-id="81104-119">When an **Audio Conferencing** license is assigned to them.</span></span>
    
  - <span data-ttu-id="81104-120">사용자의 오디오 회의 PIN을 수동으로 다시 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="81104-120">When you manually reset the user's audio conferencing PIN.</span></span>
    
  - <span data-ttu-id="81104-121">수동으로 사용자의 전화 회의 ID를 다시 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="81104-121">When you manually reset the user's conference ID.</span></span>
    
  - <span data-ttu-id="81104-122">**오디오 회의** 라이선스가 제거 된 경우</span><span class="sxs-lookup"><span data-stu-id="81104-122">When an **Audio Conferencing** license is removed from them.</span></span>
    
  - <span data-ttu-id="81104-123">사용자의 오디오 회의 공급자가 Microsoft에서 다른 공급자 또는 **없음**으로 변경 되는 경우</span><span class="sxs-lookup"><span data-stu-id="81104-123">When the audio conferencing provider for a user is changed from Microsoft to another provider or **None**.</span></span>
    
  - <span data-ttu-id="81104-124">사용자의 오디오 회의 공급자가 Microsoft로 변경 된 경우</span><span class="sxs-lookup"><span data-stu-id="81104-124">When the audio conferencing provider for a user is changed to Microsoft.</span></span>
  
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="81104-125">Windows PowerShell에 대 한 자세한 정보를 확인 하 고 싶으신가요?</span><span class="sxs-lookup"><span data-stu-id="81104-125">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="81104-126">Windows PowerShell은 사용자 및 허용 되지 않거나 수행할 수 있는 사용자를 관리 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="81104-126">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="81104-127">Windows PowerShell을 사용 하면 여러 작업을 수행할 때 일상 업무를 단순화할 수 있는 단일 관리 지점을 사용 하 여 Office 365를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81104-127">With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="81104-128">Windows PowerShell을 시작 하려면 다음 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="81104-128">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="81104-129">Office 365 PowerShell을 사용 해야 하는 이유</span><span class="sxs-lookup"><span data-stu-id="81104-129">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="81104-130">Windows PowerShell을 사용 하 여 Office 365를 관리 하는 가장 좋은 방법</span><span class="sxs-lookup"><span data-stu-id="81104-130">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="81104-131">Windows PowerShell에 대 한 자세한 내용은 [Microsoft 팀 PowerShell 참조](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) 에서 자세한 내용을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="81104-131">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
  
## <a name="related-topics"></a><span data-ttu-id="81104-132">관련 항목</span><span class="sxs-lookup"><span data-stu-id="81104-132">Related topics</span></span>

[<span data-ttu-id="81104-133">Office 365에서 오디오 회의 체험 또는 구매</span><span class="sxs-lookup"><span data-stu-id="81104-133">Try or purchase Audio Conferencing in Office 365</span></span>](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
