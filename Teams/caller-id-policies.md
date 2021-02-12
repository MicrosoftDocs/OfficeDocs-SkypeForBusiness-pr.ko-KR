---
title: Microsoft Teams에서 발신자 ID 정책 관리
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: jastark
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
description: Microsoft Teams에서 발신자 ID 정책을 사용하여 조직의 Teams 사용자의 발신자 ID를 변경하거나 차단하는 방법을 배워야 합니다.
ms.openlocfilehash: c3eabc5a9e906fd514ce92864e08cad5015f6670
ms.sourcegitcommit: 2874aec7768bb46ed4506c1a2d431841f47190bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2020
ms.locfileid: "47255531"
---
# <a name="manage-caller-id-policies-in-microsoft-teams"></a><span data-ttu-id="826b5-103">Microsoft Teams에서 발신자 ID 정책 관리</span><span class="sxs-lookup"><span data-stu-id="826b5-103">Manage caller ID policies in Microsoft Teams</span></span>

>[!INCLUDE [new-feature-teams-admin-center](includes/new-feature-teams-admin-center.md)]

<span data-ttu-id="826b5-104">관리자는 Microsoft Teams에서 발신자 ID 정책을 사용하여 발신자 ID(호출 라인 ID라고도 하는 호출자 ID)를 변경하거나 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="826b5-104">As an admin, you can use caller ID policies in Microsoft Teams to change or block the caller ID (also known as calling line ID).</span></span> <span data-ttu-id="826b5-105">기본적으로 Teams 사용자의 전화 번호는 사용자가 PSTN 전화로 전화를 걸 때 볼 수 있으며, Teams 사용자로 전화를 걸 때 PSTN 발신자 전화 번호를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="826b5-105">By default, the phone number of Teams users can be seen when they make a call to a PSTN phone and the phone number of PSTN callers can be seen when they call a Teams user.</span></span> <span data-ttu-id="826b5-106">발신자 ID 정책을 사용하여 조직의 Teams 사용자의 대체 전화 번호를 표시하거나 들어오는 번호가 표시되지 못하게 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="826b5-106">You can use caller ID policies to display an alternate phone number for Teams users in your organization or block an incoming number from being displayed.</span></span>

<span data-ttu-id="826b5-107">예를 들어 사용자가 전화를 걸 때 발신자 ID를 변경하여 사용자의 전화 번호 대신 조직의 기본 전화 번호를 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="826b5-107">For example, when users make a call, you can change the caller ID to display your organization's main phone number instead of users' phone numbers.</span></span>

<span data-ttu-id="826b5-108">Microsoft Teams 관리 센터에서 **음성** 발신자 ID 정책으로 진행하여 발신자 ID 정책을  >   관리합니다.</span><span class="sxs-lookup"><span data-stu-id="826b5-108">You manage caller ID policies by going to **Voice** > **Caller ID policies** in the Microsoft Teams admin center.</span></span> <span data-ttu-id="826b5-109">전역(조직 전체 기본값) 정책을 사용하거나 사용자 지정 정책을 만들어 사용자에게 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="826b5-109">You can use the global (Org-wide default) policy or create and assign custom policies.</span></span> <span data-ttu-id="826b5-110">사용자 지정 정책을 만들고 할당하지 않으면 조직의 사용자에게 전역 정책이 자동으로 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="826b5-110">Users in your organization will automatically get the global policy unless you create and assign a custom policy.</span></span>

## <a name="create-a-custom-caller-id-policy"></a><span data-ttu-id="826b5-111">사용자 지정 호출자 ID 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="826b5-111">Create a custom caller ID policy</span></span>

1. <span data-ttu-id="826b5-112">Microsoft Teams 관리 센터의 왼쪽 탐색 모음에서 **음성** 발신자  >  **ID 정책으로 이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="826b5-112">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Caller ID policies**.</span></span>
2. <span data-ttu-id="826b5-113">**추가** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="826b5-113">Click **Add**.</span></span> <br>
<span data-ttu-id="826b5-114">![관리 센터의 새 발신자 ID 정책 페이지의 스크린샷](media/caller-id-policies-add-policy.png)</span><span class="sxs-lookup"><span data-stu-id="826b5-114">![Screenshot of new caller ID policy page in the admin center](media/caller-id-policies-add-policy.png)</span></span>
3. <span data-ttu-id="826b5-115">정책의 이름과 설명을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="826b5-115">Enter a name and description for the policy.</span></span>
4. <span data-ttu-id="826b5-116">여기에서 원하는 설정을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="826b5-116">From here, choose the settings that you want:</span></span>

    - <span data-ttu-id="826b5-117">**수신 발신자 ID** 차단: 수신 호출의 발신자 ID가 표시되지 못하게 차단하기 위해 이 설정을 켜야 합니다.</span><span class="sxs-lookup"><span data-stu-id="826b5-117">**Block incoming caller ID**: Turn on this setting to block the caller ID of incoming calls from being displayed.</span></span>
    - <span data-ttu-id="826b5-118">**호출자 ID** 정책 다시 적용: 사용자가 발신자 번호 표시와 관련하여 정책의 설정을 다시 설정할 수 있도록 이 설정을 켜야 합니다.</span><span class="sxs-lookup"><span data-stu-id="826b5-118">**Override the caller ID policy**: Turn on this setting to let users override the settings in the policy regarding displaying their number to callees or not.</span></span> <span data-ttu-id="826b5-119">즉, 사용자가 발신자 ID를 표시할지 여부를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="826b5-119">This means that users can choose whether to display their caller ID.</span></span> <span data-ttu-id="826b5-120">자세한 내용은 아웃바운드 호출자 ID의 최종 [사용자 제어를 참조하세요.](https://docs.microsoft.com/microsoftteams/how-can-caller-id-be-used-in-your-organization#end-user-control-of-outbound-caller-id)</span><span class="sxs-lookup"><span data-stu-id="826b5-120">For more information, see [End user control of outbound caller ID](https://docs.microsoft.com/microsoftteams/how-can-caller-id-be-used-in-your-organization#end-user-control-of-outbound-caller-id).</span></span>
    - <span data-ttu-id="826b5-121">**호출자 ID를**: 다음 중 하나를 선택하여 사용자에게 표시될 호출자 ID를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="826b5-121">**Replace the caller ID with**: Set the caller ID to be displayed for users by selecting one of the following:</span></span>

        - <span data-ttu-id="826b5-122">**사용자 번호:** 사용자의 번호를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="826b5-122">**User's number**: Displays the user's number.</span></span> 
        - <span data-ttu-id="826b5-123">**서비스 번호:** 발신자 ID로 표시할 서비스 전화 번호를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="826b5-123">**Service number**: Lets you set a service phone number to display as the caller ID.</span></span>
        - <span data-ttu-id="826b5-124">**익명:** 호출자 ID를 익명으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="826b5-124">**Anonymous**: Displays the caller ID as Anonymous.</span></span>

    - <span data-ttu-id="826b5-125">**호출자 ID를** 이 서비스 번호로 바꾸기: 사용자의 호출자 ID를 바꿀 서비스 번호를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="826b5-125">**Replace the caller ID with this service number**: Choose a service number to replace the caller ID of users.</span></span> <span data-ttu-id="826b5-126">호출자 ID를 으로 바꾸기에서 서비스 번호를 선택한 경우 이 **옵션을 사용할 수 있습니다.** </span><span class="sxs-lookup"><span data-stu-id="826b5-126">This option is available if you selected **Service number** in **Replace the caller ID with**.</span></span>

5. <span data-ttu-id="826b5-127">**저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="826b5-127">Click **Save**.</span></span>

## <a name="edit-a-caller-id-policy"></a><span data-ttu-id="826b5-128">호출자 ID 정책 편집</span><span class="sxs-lookup"><span data-stu-id="826b5-128">Edit a caller ID policy</span></span>

<span data-ttu-id="826b5-129">전역 정책 또는 만드는 모든 사용자 지정 정책을 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="826b5-129">You can edit the global policy or any custom policies that you create.</span></span> 

1. <span data-ttu-id="826b5-130">Microsoft Teams 관리 센터의 왼쪽 탐색 모음에서 **음성** 발신자  >  **ID 정책으로 이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="826b5-130">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Caller ID policies**.</span></span>
2. <span data-ttu-id="826b5-131">정책 이름 왼쪽을 클릭하여 정책을 선택한 다음 **편집** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="826b5-131">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="826b5-132">원하는 설정을 변경한 다음 저장을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="826b5-132">Change the settings that you want, and then click **Save**.</span></span>

## <a name="assign-a-custom-caller-id-policy-to-users"></a><span data-ttu-id="826b5-133">사용자에게 사용자 지정 호출자 ID 정책 할당</span><span class="sxs-lookup"><span data-stu-id="826b5-133">Assign a custom caller ID policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="related-topics"></a><span data-ttu-id="826b5-134">관련 항목</span><span class="sxs-lookup"><span data-stu-id="826b5-134">Related topics</span></span>

[<span data-ttu-id="826b5-135">New-CsCallingLineIdentity</span><span class="sxs-lookup"><span data-stu-id="826b5-135">New-CsCallingLineIdentity</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cscallinglineidentity?view=skype-ps)

[<span data-ttu-id="826b5-136">Teams에서 사용자에게 정책 할당</span><span class="sxs-lookup"><span data-stu-id="826b5-136">Assign policies to your users in Teams</span></span>](assign-policies.md)
