---
title: 사용자가 모임 이름을 녹음/녹화할 수 있도록 설정
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
description: 사용자가 Microsoft 팀에서 모임에 참가할 때 이름을 기록할 수 있는지 여부를 사용 하거나 사용 하지 않도록 설정 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: d7cab4fca4ad3e7732704da9837522d51314061d
ms.sourcegitcommit: 1807ea5509f8efa6abba8462bce2f3646117e8bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/10/2020
ms.locfileid: "44691584"
---
# <a name="enable-users-to-record-their-name-when-they-join-a-meeting-in-microsoft-teams"></a><span data-ttu-id="e2687-103">사용자가 Microsoft 팀에서 모임에 참가할 때 이름을 기록할 수 있도록 설정</span><span class="sxs-lookup"><span data-stu-id="e2687-103">Enable users to record their name when they join a meeting in Microsoft Teams</span></span>

<span data-ttu-id="e2687-104">Microsoft 365 또는 Office 365에서 오디오 회의를 설정 하는 경우 전화 번호를 받고 오디오 회의 브리지 라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2687-104">When you are setting up Audio Conferencing in Microsoft 365 or Office 365, you will receive phone numbers and what is called an audio conferencing bridge.</span></span> <span data-ttu-id="e2687-105">회의 브리지에는 전용 또는 공유 전화 번호로 사용할 수 있는 하나 이상의 전화 번호가 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2687-105">A conferencing bridge can contain one or more phone numbers that can be a dedicated or shared phone number.</span></span>
  
<span data-ttu-id="e2687-106">회의 브리지가 휴대폰을 사용 하 여 모임에 전화를 거는 사용자에 대 한 통화에 응답 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2687-106">The conferencing bridge answers a call for a user who is dialing in to a meeting using a phone.</span></span> <span data-ttu-id="e2687-107">회의 브리지는 자동 전화 교환의 음성 프롬프트를 사용 하 여 발신자에 응답 한 다음 설정에 따라 알림을 재생 하 고, 발신자에 게 자신의 이름을 기록 하도록 요청 하 고, 모임 이끌이에게 대 한 PIN 보안을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2687-107">The conferencing bridge answers the caller with voice prompts from an auto attendant, and then, depending on their settings, can play notifications, ask callers to record their name, and set up the PIN security for meeting organizers.</span></span> <span data-ttu-id="e2687-108">모임을 시작 하는 데 사용할 수 있도록 모임 이끌이가 Pin을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2687-108">PINs are given to meeting organizers to allow them to start a meeting.</span></span> <span data-ttu-id="e2687-109">그러나 모임을 시작 하는 데 PIN이 필요 하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2687-109">However, you can set it up so a PIN isn't required to start a meeting.</span></span>

  
## <a name="set-whether-callers-should-record-their-name"></a><span data-ttu-id="e2687-110">호출자가 자신의 이름을 기록해 야 하는지 여부 설정</span><span class="sxs-lookup"><span data-stu-id="e2687-110">Set whether callers should record their name</span></span>

<span data-ttu-id="e2687-111">![Microsoft Teams 로고를 나타내는 아이콘](media/teams-logo-30x30.png) **Microsoft Teams 관리 센터 사용**</span><span class="sxs-lookup"><span data-stu-id="e2687-111">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="e2687-112">왼쪽 탐색 창에서 **모임**  >  **회의 브리지로**이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2687-112">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="e2687-113">**회의 브리지** 페이지 맨 위에서 **브리지 설정을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2687-113">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="e2687-114">모임 항목을 사용 하거나 사용 하지 않도록 설정 **하 고 알림을 종료**합니다.</span><span class="sxs-lookup"><span data-stu-id="e2687-114">Enable or disable **Meeting entry and exit notifications**.</span></span>

4. <span data-ttu-id="e2687-115">알림을 사용 하도록 설정 하는 경우 **시작/종료 알림 유형에**서 **이름 또는 전화 번호** 를 선택한 다음 **발신자에 게 모임에 참가 하기 전에 자신의 이름을 기록해 야 합니다.** 를 켭니다.</span><span class="sxs-lookup"><span data-stu-id="e2687-115">If enabling notifications, choose **Names or phone numbers** under **Entry/exit announcement type**, and then turn on **Ask callers to record their name before joining a meeting.**</span></span>

6. <span data-ttu-id="e2687-116">**저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e2687-116">Click **Save**.</span></span>
    
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="e2687-117">Windows PowerShell에 대 한 자세한 정보를 확인 하 고 싶으신가요?</span><span class="sxs-lookup"><span data-stu-id="e2687-117">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="e2687-118">Windows PowerShell은 사용자 및 허용 되지 않거나 수행할 수 있는 사용자를 관리 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2687-118">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="e2687-119">Windows PowerShell을 사용 하면 여러 작업을 수행할 때 일상 업무를 단순화할 수 있는 단일 관리 지점을 사용 하 여 Microsoft 365 또는 Office 365를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2687-119">With Windows PowerShell, you can manage Microsoft 365 or Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="e2687-120">Windows PowerShell을 시작 하려면 다음 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e2687-120">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="e2687-121">Office 365 PowerShell을 사용 해야 하는 이유</span><span class="sxs-lookup"><span data-stu-id="e2687-121">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="e2687-122">Windows PowerShell을 사용 하 여 Office 365를 관리 하는 가장 좋은 방법</span><span class="sxs-lookup"><span data-stu-id="e2687-122">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="e2687-123">Windows PowerShell에 대 한 자세한 내용은 [Microsoft 팀 PowerShell 참조](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) 에서 자세한 내용을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e2687-123">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="e2687-124">관련 항목</span><span class="sxs-lookup"><span data-stu-id="e2687-124">Related topics</span></span>

[<span data-ttu-id="e2687-125">오디오 회의 체험 또는 구매</span><span class="sxs-lookup"><span data-stu-id="e2687-125">Try or purchase Audio Conferencing</span></span>](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
