---
title: 초대에 포함할 전화 번호 설정
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
description: 다음 단계에 따라 발신자들이 모임에 참가할 수 있는 기본 전화 번호를 Microsoft Teams 있습니다.
ms.openlocfilehash: 476075ccf5e261695564b78ec084605af9e6898c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117176"
---
# <a name="set-the-phone-numbers-included-on-invites-in-microsoft-teams"></a><span data-ttu-id="fed8e-103">초대에 포함된 전화 번호를 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="fed8e-103">Set the phone numbers included on invites in Microsoft Teams</span></span>

<span data-ttu-id="fed8e-104">조직에서 Microsoft 365 Office 365 오디오 회의를 사용하면 조직의 사용자가 Microsoft Teams 모임을 만든 다음 사용자가 전화를 사용하여 해당 모임에 전화를 걸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fed8e-104">Audio Conferencing in Microsoft 365 and Office 365 enables users in your organization to create Microsoft Teams meetings, and then allow users to dial in to those meetings using a phone.</span></span>
  
<span data-ttu-id="fed8e-105">회의 브리지는 조직에 대한 전화 접속 전화 번호 집합을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="fed8e-105">A conferencing bridge gives you a set of dial-in phone numbers for your organization.</span></span> <span data-ttu-id="fed8e-106">모두 모임 이끌이가 만든 모임에 참가하는 데 사용할 수 있지만 모임 초대에 포함될 모임을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fed8e-106">All of them can be used to join the meetings that a meeting organizer has created, but you can select which ones will be included on their meeting invites.</span></span>
  
> [!NOTE]
> <span data-ttu-id="fed8e-107">모임 이끌이에 대한 모임 초대에는 최대 1개의 전화 번호와 무료 전화 번호가 있을 수 있지만, 각 모임 초대의 아래쪽에 모임에 참가하는 데 사용할 수 있는 모든 전화 접속 전화 번호의 전체 목록을 여는 링크도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fed8e-107">There can be a maximum of one toll and one toll-free phone number on the meeting invite for a meeting organizer, but there is also a link located at the bottom of each meeting invite that opens the full list of all dial-in phone numbers that can be used to join a meeting.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="initial-assignment-of-phone-numbers-that-are-included-in-the-meeting-invites-for-new-users"></a><span data-ttu-id="fed8e-108">새 사용자를 위한 모임 초대에 포함된 전화 번호의 초기 할당</span><span class="sxs-lookup"><span data-stu-id="fed8e-108">Initial assignment of phone numbers that are included in the meeting invites for new users</span></span>

<span data-ttu-id="fed8e-109">오디오 회의에 사용하도록 설정된 사용자의 모임 초대에 포함된 전화 번호는 기본 회의 요금 전화 번호 및 기본 회의 무료 전화 번호 사용자 설정에 의해 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="fed8e-109">The phone numbers that get included in the meeting invites of users enabled for Audio Conferencing are defined by the default conferencing toll phone number and the default conferencing toll-free phone number user's settings.</span></span> <span data-ttu-id="fed8e-110">각 설정은 지정한 사용자의 모임 초대에 포함될 요금 및 무료 번호를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="fed8e-110">Each setting specifies which toll and toll-free number will be included in the meeting invite of a given user.</span></span> <span data-ttu-id="fed8e-111">위에서 설명한 대로 각 모임 초대에는 하나의 전화 번호, 하나의 선택적 무료 전화 번호 및 특정 모임에 참가하는 데 사용할 수 있는 모든 전화 접속 전화 번호의 전체 목록을 여는 링크가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fed8e-111">As noted above, each meeting invite contains one toll number, one optional toll-free number and a link that opens the full list of all dial-in phone numbers that can be used to join a given meeting.</span></span>

<span data-ttu-id="fed8e-112">새 사용자의 경우 사용자가 오디오 회의 서비스에 대해 사용하도록 설정되어 있는 경우 사용자의 Microsoft 365 관리 센터에 설정된 사용 현황 위치를 기반으로 기본 회의 전화 번호가 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="fed8e-112">For a new user, the default conferencing toll numbers is assigned based on the Usage Location that is set in the Microsoft 365 administration center of the user when the user is enabled for the Audio Conferencing service.</span></span> <span data-ttu-id="fed8e-113">사용자의 국가와 일치하는 전화 회의 브리지에 전화 번호가 있는 경우 해당 번호는 사용자의 기본 전화 번호로 자동으로 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="fed8e-113">If there is a toll number in the conference bridge that matches the country of the user, that number will be automatically assigned as the default toll number of the user.</span></span> <span data-ttu-id="fed8e-114">전화 회의 브리지의 기본 전화 번호로 정의된 번호는 사용자의 기본 전화 번호로 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="fed8e-114">If there isn't one, the number that is defined as the default toll number of the conference bridge will be assigned as the default toll number of the user.</span></span>  

<span data-ttu-id="fed8e-115">사용자가 오디오 회의 서비스에 사용하도록 설정되면 사용자의 기본 전화 번호 및 무료 전화 번호를 테넌트 관리자가 초기 값에서 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fed8e-115">Once the user is enabled for the Audio Conferencing service, the default toll and toll-free phone numbers of the user can be changed by the tenant administrator from their initial values at any moment.</span></span>

## <a name="set-or-change-the-default-audio-conferencing-phone-number-for-a-meeting-organizer-or-user"></a><span data-ttu-id="fed8e-116">모임 이끌이 또는 사용자의 기본 오디오 회의 전화 번호 설정 또는 변경</span><span class="sxs-lookup"><span data-stu-id="fed8e-116">Set or change the default audio conferencing phone number for a meeting organizer or user</span></span>

<span data-ttu-id="fed8e-117">![Microsoft Teams 로고를 나타내는 아이콘](media/teams-logo-30x30.png) **Microsoft Teams 관리 센터 사용**</span><span class="sxs-lookup"><span data-stu-id="fed8e-117">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

<span data-ttu-id="fed8e-118">이러한 정책을 관리하려면 전역 관리자 또는 Teams 서비스 관리자여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fed8e-118">You must be a Teams service admin to make these changes.</span></span> <span data-ttu-id="fed8e-119">관리 역할 및 사용 권한 가져오기에 대한 내용은 [Teams 관리자 역할 사용](./using-admin-roles.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fed8e-119">See [Use Teams administrator roles to manage Teams](./using-admin-roles.md) to read about getting admin roles and permissions.</span></span>

1. <span data-ttu-id="fed8e-120">관리 센터에 Microsoft Teams 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="fed8e-120">Log in to the Microsoft Teams admin center.</span></span>

2. <span data-ttu-id="fed8e-121">왼쪽 탐색에서 사용자 를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="fed8e-121">In the left navigation, click **Users**.</span></span>

    ![관리 센터에서 사용자 Microsoft Teams 표시](media/Admin-users.png)

3. <span data-ttu-id="fed8e-123">사용 가능한 사용자 목록에서 사용자 이름을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="fed8e-123">Click the user name from the list of available users.</span></span>

4. <span data-ttu-id="fed8e-124">오디오 **회의** 옆에 있는 편집을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="fed8e-124">Next to **Audio Conferencing**, click **Edit**.</span></span>

    ![오디오 회의 옆의 편집을 클릭합니다.](media/teams-set-phone-numbers-on-invites-image3.png)

5. <span data-ttu-id="fed8e-126">전화 번호 **또는**  무료 번호 필드를 사용하여 사용자에 대한 번호를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="fed8e-126">Use the **Toll number** or **Toll-free number** fields to enter the numbers for the user.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fed8e-127">사용자의 오디오 회의 설정을 변경하면 모임을 다시 Microsoft Teams 모임을 업데이트하고 참석자에게 보내야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fed8e-127">When you change a user's audio conferencing settings, recurring and future Microsoft Teams meetings must be updated and sent to attendees.</span></span>

## <a name="want-to-use-windows-powershell"></a><span data-ttu-id="fed8e-128">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="fed8e-128">Want to use Windows PowerShell</span></span>

<span data-ttu-id="fed8e-129">Windows PowerShell 모든 것은 사용자 관리와 사용자가 허용되거나 허용되지 않는 작업을 관리하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="fed8e-129">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="fed8e-130">이 Windows PowerShell 여러 작업을 수행할 때 일상적인 작업을 단순화할 수 Microsoft 365 Office 365 관리 지점을 사용하여 관리 또는 관리 작업을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fed8e-130">With Windows PowerShell, you can manage Microsoft 365 or Office 365 by using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="fed8e-131">다음 항목을 Windows PowerShell 다음 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fed8e-131">To get started with Windows PowerShell, see these topics:</span></span>

- [<span data-ttu-id="fed8e-132">PowerShell을 Office 365 이유</span><span class="sxs-lookup"><span data-stu-id="fed8e-132">Why you need to use Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

- <span data-ttu-id="fed8e-133">[사용자와 함께 Microsoft 365 또는 Office 365 가장 Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="fed8e-133">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>

<span data-ttu-id="fed8e-134">자세한 내용은 Windows PowerShell [PowerShell](/powershell/module/teams/?view=teams-ps) Microsoft Teams 참조를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fed8e-134">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="fed8e-135">관련 항목</span><span class="sxs-lookup"><span data-stu-id="fed8e-135">Related topics</span></span>

[<span data-ttu-id="fed8e-136">오디오 회의를 시도하거나 Microsoft 365 또는 Office 365</span><span class="sxs-lookup"><span data-stu-id="fed8e-136">Try or purchase Audio Conferencing in Microsoft 365 or Office 365</span></span>](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)

[<span data-ttu-id="fed8e-137">오디오 회의 브리지에서 전화 번호 변경</span><span class="sxs-lookup"><span data-stu-id="fed8e-137">Change the phone numbers on your Audio Conferencing bridge</span></span>](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)