---
title: 사용자가 모임의 이름을 기록할 수 있도록 설정
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 1d649328-ada7-422d-a074-d6da4da36970
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
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
description: 사용자가 Microsoft Teams에서 모임에 참가할 때 자신의 이름을 기록할 수 있는지 여부를 설정하거나 사용하지 않도록 설정하는 방법을 배워야 합니다.
ms.openlocfilehash: d7cab4fca4ad3e7732704da9837522d51314061d
ms.sourcegitcommit: 1807ea5509f8efa6abba8462bce2f3646117e8bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/10/2020
ms.locfileid: "44691584"
---
# <a name="enable-users-to-record-their-name-when-they-join-a-meeting-in-microsoft-teams"></a><span data-ttu-id="4956c-103">사용자가 Microsoft Teams에서 모임에 참가할 때 자신의 이름을 기록할 수 있도록 설정</span><span class="sxs-lookup"><span data-stu-id="4956c-103">Enable users to record their name when they join a meeting in Microsoft Teams</span></span>

<span data-ttu-id="4956c-104">Microsoft 365 또는 Office 365에서 오디오 회의를 설정하는 경우 전화 번호와 오디오 회의 브리지라는 것을 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4956c-104">When you are setting up Audio Conferencing in Microsoft 365 or Office 365, you will receive phone numbers and what is called an audio conferencing bridge.</span></span> <span data-ttu-id="4956c-105">회의 브리지에는 전용 또는 공유 전화 번호일 수 있는 하나 이상의 전화 번호가 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4956c-105">A conferencing bridge can contain one or more phone numbers that can be a dedicated or shared phone number.</span></span>
  
<span data-ttu-id="4956c-106">회의 브리지는 전화기를 사용하여 모임에 전화 접속하는 사용자의 통화에 응답합니다.</span><span class="sxs-lookup"><span data-stu-id="4956c-106">The conferencing bridge answers a call for a user who is dialing in to a meeting using a phone.</span></span> <span data-ttu-id="4956c-107">회의 브리지는 자동 전화 회의에서 음성 프롬프트로 발신자에 응답한 다음 설정에 따라 알림을 재생하고 발신자 이름을 기록해 달라고 요청하고 모임 이끌이에 대한 PIN 보안을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4956c-107">The conferencing bridge answers the caller with voice prompts from an auto attendant, and then, depending on their settings, can play notifications, ask callers to record their name, and set up the PIN security for meeting organizers.</span></span> <span data-ttu-id="4956c-108">모임 이끌이가 모임을 시작할 수 있도록 PINS가 부여됩니다.</span><span class="sxs-lookup"><span data-stu-id="4956c-108">PINs are given to meeting organizers to allow them to start a meeting.</span></span> <span data-ttu-id="4956c-109">그러나 PIN이 모임을 시작할 필요는 없는 경우 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4956c-109">However, you can set it up so a PIN isn't required to start a meeting.</span></span>

  
## <a name="set-whether-callers-should-record-their-name"></a><span data-ttu-id="4956c-110">호출자 이름을 기록해야 하는지 여부 설정</span><span class="sxs-lookup"><span data-stu-id="4956c-110">Set whether callers should record their name</span></span>

<span data-ttu-id="4956c-111">![Microsoft Teams 로고를 나타내는 아이콘](media/teams-logo-30x30.png) **Microsoft Teams 관리 센터 사용**</span><span class="sxs-lookup"><span data-stu-id="4956c-111">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="4956c-112">왼쪽 탐색 모음에서 **모임** 회의  >  **브리지로 이동**</span><span class="sxs-lookup"><span data-stu-id="4956c-112">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="4956c-113">컨퍼런스 브리지  페이지의 맨 위에 있는 **브리지 설정을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="4956c-113">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="4956c-114">모임 입장 **및 종료 알림을 사용** 또는 사용하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="4956c-114">Enable or disable **Meeting entry and exit notifications**.</span></span>

4. <span data-ttu-id="4956c-115">알림을 사용하도록 설정하는  경우 **입장/퇴장** 알림 유형에서 이름 또는 전화 번호를 선택한 다음, 모임에 참가하기 전에 발신자 이름을 기록해달라고 **요청합니다.**</span><span class="sxs-lookup"><span data-stu-id="4956c-115">If enabling notifications, choose **Names or phone numbers** under **Entry/exit announcement type**, and then turn on **Ask callers to record their name before joining a meeting.**</span></span>

6. <span data-ttu-id="4956c-116">**저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="4956c-116">Click **Save**.</span></span>
    
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="4956c-117">자세한 내용은 Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="4956c-117">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="4956c-118">Windows PowerShell 관리는 사용자 및 사용자가 허용되거나 허용되지 않는 작업을 관리하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="4956c-118">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="4956c-119">이 Windows PowerShell 여러 작업을 수행할 때 일상적인 작업을 간소화할 수 있는 단일 관리 지점을 사용하여 Microsoft 365 또는 Office 365를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4956c-119">With Windows PowerShell, you can manage Microsoft 365 or Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="4956c-120">다음 항목을 Windows PowerShell 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4956c-120">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="4956c-121">Office 365 PowerShell을 사용하는 이유</span><span class="sxs-lookup"><span data-stu-id="4956c-121">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="4956c-122">Office 365를 관리하는 가장 좋은 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="4956c-122">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="4956c-123">자세한 내용은 Windows PowerShell [Microsoft Teams PowerShell 참조를](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4956c-123">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="4956c-124">관련 항목</span><span class="sxs-lookup"><span data-stu-id="4956c-124">Related topics</span></span>

[<span data-ttu-id="4956c-125">오디오 회의 시도 또는 구매</span><span class="sxs-lookup"><span data-stu-id="4956c-125">Try or purchase Audio Conferencing</span></span>](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
