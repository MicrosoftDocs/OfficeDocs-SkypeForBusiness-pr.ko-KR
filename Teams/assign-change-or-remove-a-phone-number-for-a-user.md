---
title: 사용자의 전화 번호 할당, 변경 또는 제거
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: 91089761-cb87-4119-885b-3713840dd9f7
ms.tgt.pltfrm: cloud
audience: admin
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Calling Plans
description: 외부 기업 및 클라이언트가 전화를 걸 수 있도록 Teams 사용자에 대한 회사 전화 번호를 할당, 변경 또는 제거하는 방법에 대해 자세히 알아보습니다.
ms.openlocfilehash: 4f40049b3856f24d3ae5ddd3999be7213817bcdc
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120820"
---
# <a name="assign-change-or-remove-a-phone-number-for-a-user-calling-plans"></a><span data-ttu-id="ef2be-103">사용자에 대한 전화 번호 할당, 변경 또는 제거(계획 호출)</span><span class="sxs-lookup"><span data-stu-id="ef2be-103">Assign, change, or remove a phone number for a user (Calling Plans)</span></span>

<span data-ttu-id="ef2be-104">통화 계획을 설정할 때 사용자에게 전화 번호를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="ef2be-104">When you set up Calling Plans, you assign phone numbers to your users.</span></span> <span data-ttu-id="ef2be-105">Microsoft Teams에서 사용자가 호출을 클릭하면 할당한 전화 번호가 **나열됩니다.**</span><span class="sxs-lookup"><span data-stu-id="ef2be-105">In Microsoft Teams, the phone number that you assign is listed when a user clicks **Calls**.</span></span> <span data-ttu-id="ef2be-106">직접 라우팅 시나리오에서 사용자로부터 전화 번호를 할당, 변경 또는 제거하는 방법에 대한 지침은 직접 라우팅, 음성 및 음성메일에 대해 사용자 사용 을 [참조하세요.](./direct-routing-enable-users.md)</span><span class="sxs-lookup"><span data-stu-id="ef2be-106">For instructions about assigning, changing, or removing a phone number from a user in a Direct Routing scenario, see [Enable users for Direct Routing, voice, and voicemail](./direct-routing-enable-users.md).</span></span>

![Teams에 표시되는 사용자의 전화 번호입니다.](media/teams-phone-number.png)

<span data-ttu-id="ef2be-108">사용자가 전화를 걸고 받을 수 있도록 사용자를 설정하는 경우 먼저 Microsoft Teams 관리 센터를 사용하여 전화 번호를 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef2be-108">When you're setting up users so they can make and receive phone calls, you must first use the Microsoft Teams admin center and assign a phone number.</span></span> <span data-ttu-id="ef2be-109">필요한 경우 전화 번호를 변경하거나 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ef2be-109">You can change or remove the phone number if you need to.</span></span>
  
<span data-ttu-id="ef2be-110">Teams에서 통화 요금제와 비용에 대한 자세한 내용은 [Teams 추가 기능 라이선스 를 참조합니다.](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)</span><span class="sxs-lookup"><span data-stu-id="ef2be-110">To learn how to get Calling Plans in Teams and how much they cost, see [Teams add-on licensing](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="ef2be-111">사용자가 라이선스가 할당되어 있는지를 보는 한 가지 방법은 Microsoft Teams 관리 센터로 > **있습니다.**</span><span class="sxs-lookup"><span data-stu-id="ef2be-111">One way to see whether a user has a license assigned is by going to the Microsoft Teams admin center > **Users**.</span></span> <span data-ttu-id="ef2be-112">라이선스가 할당된 경우 페이지에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ef2be-112">If a license is assigned, it will be indicated on the page.</span></span>  <span data-ttu-id="ef2be-113">Microsoft 365 관리 센터를 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ef2be-113">You can also use the Microsoft 365 admin center.</span></span>
  
## <a name="assign-a-phone-number-to-a-user"></a><span data-ttu-id="ef2be-114">사용자에게 전화 번호 할당</span><span class="sxs-lookup"><span data-stu-id="ef2be-114">Assign a phone number to a user</span></span>
 
<span data-ttu-id="ef2be-115">![Microsoft Teams 로고를 나타내는 아이콘](media/teams-logo-30x30.png) **Microsoft Teams 관리 센터 사용**</span><span class="sxs-lookup"><span data-stu-id="ef2be-115">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>
    
1. <span data-ttu-id="ef2be-116">왼쪽 탐색에서 **음성**  >  **전화 번호 를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="ef2be-116">In the left navigation, click **Voice** > **Phone numbers**.</span></span>
2. <span data-ttu-id="ef2be-117">전화 번호 **페이지에서** 목록에서 부호 없는 번호를 선택한 다음 **편집을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="ef2be-117">On the **Phone numbers** page, select an unassigned number in the list, and then click **Edit**.</span></span>  
3. <span data-ttu-id="ef2be-118">편집 **창의** 에 할당된 **에서** 표시 이름 또는 사용자 이름으로 사용자를 검색한 다음 **할당을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="ef2be-118">In the **Edit** pane, under **Assigned to**, search for the user by display name or user name, and then click **Assign**.</span></span>
4. <span data-ttu-id="ef2be-119">관련 긴급 위치를 할당하거나 변경하려면 긴급 위치 **아래에서** 위치를 검색한 다음 위치를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ef2be-119">To assign or change the associated emergency location, under **Emergency location**, search for and then select the location.</span></span>
5. <span data-ttu-id="ef2be-120">전화 번호 정보가 있는 사용자에게 전자 메일을 보낼지 여부에 따라 전화 번호 정보가 있는 전자 메일 사용자를 끄거나 **끄거나 끄기**</span><span class="sxs-lookup"><span data-stu-id="ef2be-120">Depending on whether you want to send an email to the user with their phone number information, turn off or turn on **Email user with telephone number information**.</span></span> <span data-ttu-id="ef2be-121">기본적으로 이 설정은 설정되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ef2be-121">By default, this is on.</span></span> 
6. <span data-ttu-id="ef2be-122">**저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ef2be-122">Click **Save**.</span></span>

<span data-ttu-id="ef2be-123">PowerShell 예제는 [Set-CsOnlineVoiceUser 를 참조합니다.](/powershell/module/skype/set-csonlinevoiceuser?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="ef2be-123">For a PowerShell example, see [Set-CsOnlineVoiceUser](/powershell/module/skype/set-csonlinevoiceuser?view=skype-ps).</span></span>

    > [!NOTE]
    > Because of the latency between Microsoft 365 or Office 365 and Teams, it can take up to 24 hours for users to be enabled. If the phone number isn't assigned correctly after 24 hours, [contact support for business products - Admin Help](/microsoft-365/admin/contact-support-for-business-products). We're here to help!

  
## <a name="change-a-phone-number-for-a-user"></a><span data-ttu-id="ef2be-124">사용자의 전화 번호 변경</span><span class="sxs-lookup"><span data-stu-id="ef2be-124">Change a phone number for a user</span></span>
 
<span data-ttu-id="ef2be-125">![Microsoft Teams 로고를 나타내는 아이콘](media/teams-logo-30x30.png) **Microsoft Teams 관리 센터 사용**</span><span class="sxs-lookup"><span data-stu-id="ef2be-125">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>
    
1. <span data-ttu-id="ef2be-126">왼쪽 탐색에서 사용자를 클릭하고 원하는 사용자를 찾아 두 번 클릭한 다음, 계정을 클릭한 다음 일반 정보에서 사용자에게 할당된 전화 번호를 메모합니다. </span><span class="sxs-lookup"><span data-stu-id="ef2be-126">In the left navigation, click **Users**, locate and double-click the user you want, click **Account**, and then under **General information**, make a note of the phone number that's assigned to the user.</span></span>
2. <span data-ttu-id="ef2be-127">왼쪽 탐색에서 **음성**  >  **전화 번호 를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="ef2be-127">In the left navigation, click **Voice** > **Phone numbers**.</span></span>
3. <span data-ttu-id="ef2be-128">전화 번호 **페이지에서** 1단계에서 식별한 번호를 선택한 다음 편집을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="ef2be-128">On the **Phone numbers** page, select the number that you identified in step 1, and then click **Edit**.</span></span>  
4. <span data-ttu-id="ef2be-129">편집 **창의** 할당된 **에서** **X를** 클릭하여 사용자를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="ef2be-129">In the **Edit** pane, under **Assigned to**, click the **X** to remove the user.</span></span>
5. <span data-ttu-id="ef2be-130">**저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ef2be-130">Click **Save**.</span></span>
6. <span data-ttu-id="ef2be-131">전화 번호 **페이지에서** 목록에서 부호 없는 번호를 선택한 다음 **편집을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="ef2be-131">On the **Phone numbers** page, select an unassigned number in the list, and then click **Edit**.</span></span>  
7. <span data-ttu-id="ef2be-132">편집 **창의** 에 할당된 **에서** 표시 이름 또는 사용자 이름으로 사용자를 검색한 다음 **할당을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="ef2be-132">In the **Edit** pane, under **Assigned to**, search for the user by display name or user name, and then click **Assign**.</span></span>
8. <span data-ttu-id="ef2be-133">관련 긴급 위치를 할당하거나 변경하려면 긴급 위치 **아래에서** 위치를 검색한 다음 위치를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ef2be-133">To assign or change the associated emergency location, under **Emergency location**, search for and then select the location.</span></span>
9. <span data-ttu-id="ef2be-134">**저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ef2be-134">Click **Save**.</span></span>

<span data-ttu-id="ef2be-135">PowerShell 예제는 [Set-CsOnlineVoiceUser 를 참조합니다.](/powershell/module/skype/set-csonlinevoiceuser?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="ef2be-135">For a PowerShell example, please see [Set-CsOnlineVoiceUser](/powershell/module/skype/set-csonlinevoiceuser?view=skype-ps).</span></span>

## <a name="remove-a-phone-number-from-a-user"></a><span data-ttu-id="ef2be-136">사용자에서 전화 번호 제거</span><span class="sxs-lookup"><span data-stu-id="ef2be-136">Remove a phone number from a user</span></span>
 
<span data-ttu-id="ef2be-137">![Microsoft Teams 로고를 나타내는 아이콘](media/teams-logo-30x30.png) **Microsoft Teams 관리 센터 사용**</span><span class="sxs-lookup"><span data-stu-id="ef2be-137">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="ef2be-138">왼쪽 탐색에서 사용자를 클릭하고 원하는 사용자를 찾아 두 번 클릭한 다음, 계정을 클릭한 다음 일반 정보에서 사용자에게 할당된 전화 번호를 메모합니다. </span><span class="sxs-lookup"><span data-stu-id="ef2be-138">In the left navigation, click **Users**, locate and double-click the user you want, click **Account**, and then under **General information**, make a note of the phone number that's assigned to the user.</span></span>
2. <span data-ttu-id="ef2be-139">왼쪽 탐색에서 **음성**  >  **전화 번호 를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="ef2be-139">In the left navigation, click **Voice** > **Phone numbers**.</span></span>
3. <span data-ttu-id="ef2be-140">전화 번호 **페이지에서** 2단계에서 식별한 번호를 선택한 다음 **편집을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="ef2be-140">On the **Phone numbers** page, select the number that you identified in step 2, and then click **Edit**.</span></span>  
4. <span data-ttu-id="ef2be-141">편집 **창의** 할당된 **에서** **X를** 클릭하여 사용자를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="ef2be-141">In the **Edit** pane, under **Assigned to**, click the **X** to remove the user.</span></span>
5. <span data-ttu-id="ef2be-142">**저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ef2be-142">Click **Save**.</span></span>

<span data-ttu-id="ef2be-143">PowerShell 예제는 [Set-CsOnlineVoiceUser 를 참조합니다.](/powershell/module/skype/set-csonlinevoiceuser?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="ef2be-143">For a PowerShell example, please see [Set-CsOnlineVoiceUser](/powershell/module/skype/set-csonlinevoiceuser?view=skype-ps).</span></span>

## <a name="related-topics"></a><span data-ttu-id="ef2be-144">관련 항목</span><span class="sxs-lookup"><span data-stu-id="ef2be-144">Related topics</span></span>

[<span data-ttu-id="ef2be-145">주소 유효성 검사란?</span><span class="sxs-lookup"><span data-stu-id="ef2be-145">What is address validation?</span></span>](/skypeforbusiness/what-are-calling-plans-in-office-365/what-is-address-validation)

[<span data-ttu-id="ef2be-146">조직의 전화 번호 관리</span><span class="sxs-lookup"><span data-stu-id="ef2be-146">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="ef2be-147">긴급 통화 사용 약관</span><span class="sxs-lookup"><span data-stu-id="ef2be-147">Emergency calling terms and conditions</span></span>](./emergency-calling-terms-and-conditions.md)

<span data-ttu-id="ef2be-148">[긴급 통화 고지 레이블](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="ef2be-148">[Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>

[<span data-ttu-id="ef2be-149">Set-CsOnlineVoiceUser</span><span class="sxs-lookup"><span data-stu-id="ef2be-149">Set-CsOnlineVoiceUser</span></span>](/powershell/module/skype/set-csonlinevoiceuser?view=skype-ps)

[<span data-ttu-id="ef2be-150">Microsoft 365 요금제 호출</span><span class="sxs-lookup"><span data-stu-id="ef2be-150">Calling Plans for Microsoft 365</span></span>](./calling-plans-for-office-365.md)