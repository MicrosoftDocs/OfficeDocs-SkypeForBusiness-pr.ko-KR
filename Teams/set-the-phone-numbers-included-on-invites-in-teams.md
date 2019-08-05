---
title: Microsoft 팀의 초대에 포함 된 전화 번호 설정
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 32954439-d365-4125-872f-b37466ecb035
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: '호출자가 Microsoft 팀 모임에 참가 하는 데 사용할 기본 전화 번호를 만드는 단계를 가져옵니다. '
ms.openlocfilehash: 92f5d2d0773444e3e167ed4c4e944ecd0eeb95a1
ms.sourcegitcommit: 30995da65ff6a9b33534c3818833cf0ae1952ab9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/22/2019
ms.locfileid: "36183449"
---
# <a name="set-the-phone-numbers-included-on-invites-in-microsoft-teams"></a><span data-ttu-id="a41ed-103">Microsoft 팀의 초대에 포함 된 전화 번호 설정</span><span class="sxs-lookup"><span data-stu-id="a41ed-103">Set the phone numbers included on invites in Microsoft Teams</span></span>

<span data-ttu-id="a41ed-104">Office 365의 오디오 회의를 통해 조직의 사용자가 Microsoft 팀 모임을 만든 다음 사용자가 휴대폰을 사용 하 여 해당 모임에 전화를 걸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a41ed-104">Audio Conferencing in Office 365 enables users in your organization to create Microsoft Teams meetings, and then allow users to dial in to those meetings using a phone.</span></span>
  
<span data-ttu-id="a41ed-105">회의 브리지는 조직의 전화 접속 전화 번호 집합을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a41ed-105">A conferencing bridge gives you a set of dial-in phone numbers for your organization.</span></span> <span data-ttu-id="a41ed-106">이 모든 항목은 모임 이끌이가 만든 모임에 참가 하는 데 사용할 수 있지만 모임 초대에 포함 될 모임을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a41ed-106">All of them can be used to join the meetings that a meeting organizer has created, but you can select which ones will be included on their meeting invites.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a41ed-107">모임 주최자에 대 한 모임 초대에는 최대 1 명의 유료 전화 번호와 한 명 이상의 무료 전화번호가 있을 수 있지만, 모임 참가에 사용할 수 있는 모든 전화 접속 전화 번호의 전체 목록을 여는 링크가 각 모임 초대의 맨 아래에 있는 링크 이기도 합니다.</span><span class="sxs-lookup"><span data-stu-id="a41ed-107">There can be a maximum of one toll and one toll-free phone number on the meeting invite for a meeting organizer, but there is also a link located at the bottom of each meeting invite that opens the full list of all dial-in phone numbers that can be used to join a meeting.</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="initial-assignment-of-phone-numbers-that-are-included-in-the-meeting-invites-for-new-users"></a><span data-ttu-id="a41ed-108">새 사용자를 위해 모임 초대에 포함 된 전화 번호의 초기 할당</span><span class="sxs-lookup"><span data-stu-id="a41ed-108">Initial assignment of phone numbers that are included in the meeting invites for new users</span></span>

<span data-ttu-id="a41ed-109">오디오 회의에 사용 하도록 설정 된 사용자의 모임 초대에 포함 되는 전화 번호는 기본 회의 유료 전화 번호 및 기본 회의 무료 전화 번호 사용자 설정에 따라 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a41ed-109">The phone numbers that get included in the meeting invites of users enabled for Audio Conferencing are defined by the default conferencing toll phone number and the default conferencing toll-free phone number user's settings.</span></span> <span data-ttu-id="a41ed-110">각 설정은 지정 된 사용자의 모임 초대에 포함 될 유료 및 무료 번호를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a41ed-110">Each setting specifies which toll and toll-free number will be included in the meeting invite of a given user.</span></span> <span data-ttu-id="a41ed-111">위에서 언급 한 것 처럼 각 모임 초대에는 하나의 유료 번호와 추가 무료 번호, 그리고 특정 모임에 참가 하는 데 사용할 수 있는 모든 전화 접속 전화 번호의 전체 목록을 여는 링크가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a41ed-111">As noted above, each meeting invite contains one toll number, one optional toll-free number and a link that opens the full list of all dial-in phone numbers that can be used to join a given meeting.</span></span>

<span data-ttu-id="a41ed-112">새 사용자의 경우 기본 회의 유료 전화 번호는 사용자가 오디오 회의 서비스를 사용할 수 있는 경우 사용자의 Office 365 프로필에 설정 된 국가를 기준으로 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a41ed-112">For a new user, the default conferencing toll numbers is assigned based on the country that is set in the Office 365 profile of the user when the user is enabled for the Audio Conferencing service.</span></span> <span data-ttu-id="a41ed-113">사용자의 국가와 일치 하는 유료 전화 번호가 있는 경우 해당 번호는 사용자의 기본 유료 번호로 자동으로 할당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a41ed-113">If there is a toll number in the conference bridge that matches the country of the user, that number will be automatically assigned as the default toll number of the user.</span></span> <span data-ttu-id="a41ed-114">전화 회의 브리지의 기본 유료 번호로 정의 된 번호가 사용자의 기본 유료 번호로 할당 되지 않는 경우에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a41ed-114">If there isn't one, the number that is defined as the default toll number of the conference bridge will be assigned as the default toll number of the user.</span></span>  

<span data-ttu-id="a41ed-115">사용자가 오디오 회의 서비스를 사용할 수 있게 되 면 사용자의 기본 유료 및 무료 전화 번호를 언제 든 지 초기 값으로 테 넌 트 관리자가 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a41ed-115">Once the user is enabled for the Audio Conferencing service, the default toll and toll-free phone numbers of the user can be changed by the tenant administrator from their initial values at any moment.</span></span>

## <a name="set-or-change-the-default-audio-conferencing-phone-number-for-a-meeting-organizer-or-user"></a><span data-ttu-id="a41ed-116">모임 이끌이 또는 사용자의 기본 오디오 회의 전화 번호 설정 또는 변경</span><span class="sxs-lookup"><span data-stu-id="a41ed-116">Set or change the default audio conferencing phone number for a meeting organizer or user</span></span>

<span data-ttu-id="a41ed-117">![](media/teams-logo-30x30.png) **Microsoft 팀 관리 센터를 사용 하 여** microsoft 팀 로고를 표시 하는 아이콘</span><span class="sxs-lookup"><span data-stu-id="a41ed-117">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="a41ed-118">왼쪽 탐색 창에서 **사용자**를 클릭 한 다음 사용 가능한 사용자 목록에서 사용자를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a41ed-118">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

    ![Microsoft 팀 관리 센터에서 사용자 선택을 표시 합니다.](media/teams-set-phone-numbers-on-invites-image1.png)

2. <span data-ttu-id="a41ed-120">페이지 맨 위에서 **편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a41ed-120">At the top of the page, click **Edit**.</span></span>

    ![Microsoft 팀 관리 센터에서 편집 클릭](media/teams-set-phone-numbers-on-invites-image2.png)

3. <span data-ttu-id="a41ed-122">**오디오 회의**옆에 있는 **편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a41ed-122">Next to **Audio Conferencing**, click **Edit**.</span></span> 
    
    ![오디오 회의 옆에 있는 편집 클릭](media/teams-set-phone-numbers-on-invites-image3.png)

4. <span data-ttu-id="a41ed-124">**유료** 번호 또는 **수신자 부담 번호** 필드를 사용 하 여 사용자의 번호를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="a41ed-124">Use the **Toll number** or **Toll-free number** fields to enter the numbers for the user.</span></span>


> [!IMPORTANT]
> <span data-ttu-id="a41ed-125">사용자의 오디오 회의 설정을 변경 하는 경우에는 되풀이 및 향후 Microsoft 팀 모임을 업데이트 하 고 참석자에 게 보내야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a41ed-125">When you change a user's audio conferencing settings, recurring and future Microsoft Teams meetings must be updated and sent to attendees.</span></span> 

## <a name="want-to-use-windows-powershell"></a><span data-ttu-id="a41ed-126">Windows PowerShell을 사용 하 고 싶으신가요?</span><span class="sxs-lookup"><span data-stu-id="a41ed-126">Want to use Windows PowerShell?</span></span>

<span data-ttu-id="a41ed-127">Windows PowerShell은 사용자 및 허용 되지 않거나 수행할 수 있는 사용자를 관리 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="a41ed-127">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="a41ed-128">Windows PowerShell을 사용 하면 여러 작업을 수행할 때 일상 업무를 단순화할 수 있는 단일 관리 지점을 사용 하 여 Office 365를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a41ed-128">With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="a41ed-129">Windows PowerShell을 시작 하려면 다음 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a41ed-129">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="a41ed-130">Office 365 PowerShell을 사용 해야 하는 이유</span><span class="sxs-lookup"><span data-stu-id="a41ed-130">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="a41ed-131">Windows PowerShell을 사용 하 여 Office 365를 관리 하는 가장 좋은 방법</span><span class="sxs-lookup"><span data-stu-id="a41ed-131">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="a41ed-132">Windows PowerShell에 대 한 자세한 내용은 [Microsoft 팀 PowerShell 참조](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) 에서 자세한 내용을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a41ed-132">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span> 
  
    
## <a name="related-topics"></a><span data-ttu-id="a41ed-133">관련 항목</span><span class="sxs-lookup"><span data-stu-id="a41ed-133">Related topics</span></span>

[<span data-ttu-id="a41ed-134">Office 365에서 오디오 회의 체험 또는 구매</span><span class="sxs-lookup"><span data-stu-id="a41ed-134">Try or purchase Audio Conferencing in Office 365</span></span>](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)

[<span data-ttu-id="a41ed-135">오디오 회의 브리지에서 전화 번호 변경</span><span class="sxs-lookup"><span data-stu-id="a41ed-135">Change the phone numbers on your Audio Conferencing bridge</span></span>](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)
