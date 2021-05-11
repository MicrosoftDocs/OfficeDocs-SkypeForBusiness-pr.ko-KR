---
title: Microsoft Teams에서 발신자 ID 정책 관리
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: roykuntz; jens
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-voice
f1.keywords:
- CSH
ms.custom: ms.teamsadmincenter.voice.callinglineid.overview
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: 조직에서 발신자 ID 정책을 Microsoft Teams 관리하여 조직의 사용자의 발신자 ID를 변경하거나 차단하는 Teams 방법을 알아보고 있습니다.
ms.openlocfilehash: cd928af5213a1e6fa927662adaba0fefecb687d5
ms.sourcegitcommit: 83f14c4c79559ef28357ff076938e52b369fc0c7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/10/2021
ms.locfileid: "52308377"
---
# <a name="manage-caller-id-policies-in-microsoft-teams"></a><span data-ttu-id="52ed3-103">Microsoft Teams에서 발신자 ID 정책 관리</span><span class="sxs-lookup"><span data-stu-id="52ed3-103">Manage caller ID policies in Microsoft Teams</span></span>

> [!NOTE]
> <span data-ttu-id="52ed3-104">발신자 ID를 리소스 계정 전화 번호로 설정하고 통화 파티 이름을 설정하려면 PowerShell New-CsCallingLineIdentity 또는 Set-CsCallingLineIdentity PowerShell Teams 2.3.1 이상에서 PowerShell cmdlet을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="52ed3-104">To set the caller ID to a resource account phone number and to set the calling party name, use the PowerShell cmdlets New-CsCallingLineIdentity or Set-CsCallingLineIdentity in the Teams PowerShell module 2.3.1 or later.</span></span> <span data-ttu-id="52ed3-105">(이러한 옵션은 현재 관리 센터에서 Microsoft Teams 없습니다.)</span><span class="sxs-lookup"><span data-stu-id="52ed3-105">(These options are not currently available in the Microsoft Teams admin center.)</span></span> 

<span data-ttu-id="52ed3-106">기본적으로 Teams PSTN 전화로 전화를 걸면 해당 사용자의 전화 번호가 Teams 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="52ed3-106">By default, when a Teams user makes a call to a PSTN phone, the phone number of the Teams user is visible.</span></span> <span data-ttu-id="52ed3-107">마찬가지로 PSTN 호출자에서 사용자에 Teams PSTN 호출자 전화 번호가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="52ed3-107">Likewise, when a PSTN caller makes a call to a Teams user, the PSTN caller's phone number is visible.</span></span>

<span data-ttu-id="52ed3-108">관리자는 발신자 ID 정책을 사용하여 발신자 ID(호출 줄 ID라고도)를 변경하거나 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="52ed3-108">As an administrator, you can use caller ID policies to change or block the caller ID (also known as calling line ID).</span></span> <span data-ttu-id="52ed3-109">발신자 ID 정책을 사용하여 조직의 사용자에 대한 대체 전화 Teams 표시하거나, 아웃바운드 전화 번호를 차단하거나, 들어오는 번호를 표시하지 못하게 차단하거나, CNAM(호출자 이름)을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="52ed3-109">You can use caller ID policies to display an alternate phone number for Teams users in your organization, block the outbound phone number, block an incoming number from being displayed, or set the Calling Party Name (CNAM).</span></span> <span data-ttu-id="52ed3-110">예를 들어 사용자가 전화를 걸 때 사용자의 전화 번호 대신 조직의 주 전화 번호와 회사 이름을 표시하도록 발신자 ID를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="52ed3-110">For example, when a user makes a call, you can change the caller ID to display your organization's main phone number and company name instead of the user's phone number.</span></span>

<span data-ttu-id="52ed3-111">관리 센터의 **Voice**  >  **Caller ID** 정책으로 Microsoft Teams 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="52ed3-111">You manage caller ID policies by going to **Voice** > **Caller ID policies** in the Microsoft Teams admin center.</span></span> <span data-ttu-id="52ed3-112">전역(조직 전체 기본값) 정책을 사용하거나 사용자 지정 정책을 만들어 사용자에게 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="52ed3-112">You can use the global (Org-wide default) policy or create and assign custom policies.</span></span> <span data-ttu-id="52ed3-113">사용자 지정 정책을 만들고 할당하지 않으면 조직의 사용자에게 전역 정책이 자동으로 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="52ed3-113">Users in your organization will automatically get the global policy unless you create and assign a custom policy.</span></span>

## <a name="create-a-custom-caller-id-policy"></a><span data-ttu-id="52ed3-114">사용자 지정 호출자 ID 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="52ed3-114">Create a custom caller ID policy</span></span>

1. <span data-ttu-id="52ed3-115">관리 센터의 왼쪽 Microsoft Teams **음성** 호출자 ID 정책으로  >  **이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="52ed3-115">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Caller ID policies**.</span></span>
2. <span data-ttu-id="52ed3-116">**추가** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="52ed3-116">Click **Add**.</span></span> <br>
<span data-ttu-id="52ed3-117">![관리 센터의 새 발신자 ID 정책 페이지의 스크린샷](media/caller-id-policies-add-policy.png)</span><span class="sxs-lookup"><span data-stu-id="52ed3-117">![Screenshot of new caller ID policy page in the admin center](media/caller-id-policies-add-policy.png)</span></span>
3. <span data-ttu-id="52ed3-118">정책의 이름과 설명을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="52ed3-118">Enter a name and description for the policy.</span></span>
4. <span data-ttu-id="52ed3-119">여기에서 원하는 설정을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="52ed3-119">From here, choose the settings that you want:</span></span>

    - <span data-ttu-id="52ed3-120">**들어오는 발신자 ID** 차단 : 이 설정을 켜서 들어오는 호출의 발신자 ID가 표시되지 못하게 차단합니다.</span><span class="sxs-lookup"><span data-stu-id="52ed3-120">**Block incoming caller ID**: Turn on this setting to block the caller ID of incoming calls from being displayed.</span></span>
    - <span data-ttu-id="52ed3-121">**발신자 ID** 정책 다시 적용: 사용자가 발신자에 해당 번호를 표시하는지와 관련한 정책의 설정을 다시 변경할 수 있도록 이 설정을 켜기.</span><span class="sxs-lookup"><span data-stu-id="52ed3-121">**Override the caller ID policy**: Turn on this setting to let users override the settings in the policy regarding displaying their number to callees or not.</span></span> <span data-ttu-id="52ed3-122">즉, 사용자가 발신자 ID를 표시할지 여부를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="52ed3-122">This means that users can choose whether to display their caller ID.</span></span> <span data-ttu-id="52ed3-123">자세한 내용은 아웃바운드 호출자 ID의 최종 사용자 [제어를 참조하세요.](./how-can-caller-id-be-used-in-your-organization.md#end-user-control-of-outbound-caller-id)</span><span class="sxs-lookup"><span data-stu-id="52ed3-123">For more information, see [End user control of outbound caller ID](./how-can-caller-id-be-used-in-your-organization.md#end-user-control-of-outbound-caller-id).</span></span>
    - <span data-ttu-id="52ed3-124">**발신자 ID를**: 다음 중 하나를 선택하여 사용자에게 표시될 발신자 ID를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="52ed3-124">**Replace the caller ID with**: Set the caller ID to be displayed for users by selecting one of the following:</span></span>

        - <span data-ttu-id="52ed3-125">**사용자 번호**: 사용자의 번호를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="52ed3-125">**User's number**: Displays the user's number.</span></span> 
        - <span data-ttu-id="52ed3-126">**서비스 번호**: 발신자 ID로 표시할 서비스 전화 번호를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="52ed3-126">**Service number**: Lets you set a service phone number to display as the caller ID.</span></span>
        - <span data-ttu-id="52ed3-127">**익명**: 호출자 ID를 익명으로 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="52ed3-127">**Anonymous**: Displays the caller ID as Anonymous.</span></span>

    - <span data-ttu-id="52ed3-128">**발신자 ID를** 이 서비스 번호로 바꾸기 : 사용자의 발신자 ID를 바꾸기 위해 서비스 번호를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="52ed3-128">**Replace the caller ID with this service number**: Choose a service number to replace the caller ID of users.</span></span> <span data-ttu-id="52ed3-129">이 옵션은 호출자  ID를 로 바꾸기에서 서비스 번호를 **선택한 경우 사용할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="52ed3-129">This option is available if you selected **Service number** in **Replace the caller ID with**.</span></span>

5. <span data-ttu-id="52ed3-130">**저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="52ed3-130">Click **Save**.</span></span>

## <a name="edit-a-caller-id-policy"></a><span data-ttu-id="52ed3-131">발신자 ID 정책 편집</span><span class="sxs-lookup"><span data-stu-id="52ed3-131">Edit a caller ID policy</span></span>

<span data-ttu-id="52ed3-132">전역 정책 또는 만든 사용자 지정 정책을 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="52ed3-132">You can edit the global policy or any custom policies that you create.</span></span> 

1. <span data-ttu-id="52ed3-133">관리 센터의 왼쪽 Microsoft Teams **음성** 호출자 ID 정책으로  >  **이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="52ed3-133">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Caller ID policies**.</span></span>
2. <span data-ttu-id="52ed3-134">정책 이름 왼쪽을 클릭하여 정책을 선택한 다음 **편집** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="52ed3-134">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="52ed3-135">원하는 설정을 변경한 다음 저장을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="52ed3-135">Change the settings that you want, and then click **Save**.</span></span>

## <a name="assign-a-custom-caller-id-policy-to-users"></a><span data-ttu-id="52ed3-136">사용자에게 사용자 지정 발신자 ID 정책 할당</span><span class="sxs-lookup"><span data-stu-id="52ed3-136">Assign a custom caller ID policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="related-topics"></a><span data-ttu-id="52ed3-137">관련 항목</span><span class="sxs-lookup"><span data-stu-id="52ed3-137">Related topics</span></span>

[<span data-ttu-id="52ed3-138">New-CsCallingLineIdentity</span><span class="sxs-lookup"><span data-stu-id="52ed3-138">New-CsCallingLineIdentity</span></span>](/powershell/module/skype/new-cscallinglineidentity?view=skype-ps)

[<span data-ttu-id="52ed3-139">Set-CsCallingLineIdentity</span><span class="sxs-lookup"><span data-stu-id="52ed3-139">Set-CsCallingLineIdentity</span></span>](/powershell/module/skype/set-cscallinglineidentity?view=skype-ps)

[<span data-ttu-id="52ed3-140">Teams에서 사용자에게 정책 할당</span><span class="sxs-lookup"><span data-stu-id="52ed3-140">Assign policies to your users in Teams</span></span>](assign-policies.md)