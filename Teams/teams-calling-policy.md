---
title: Microsoft 팀의 정책 호출
author: LolaJacobsen
ms.author: tonysmit
manager: serdars
ms.date: 05/06/2019
ms.topic: conceptual
ms.service: msteams
ms.reviewer: jastark
audience: admin
search.appverid: MET150
description: Microsoft 팀의 사용자 지정 통화 정책에 대 한 사용자를 만들고, 수정 하 고, 추가 하는 방법을 알아보고, 다양 한 통화 정책 설정을 확인 합니다.
localization_priority: Normal
ms.custom:
- ms.teamsadmincenter.callingpolicies.overview
- seo-marvel-apr2020
ms.collection:
- M365-voice
f1.keywords:
- CSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: a94bf072aa4db0ba0b3f65fb5340c22ab09581e4
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/27/2020
ms.locfileid: "43914028"
---
<a name="calling-policies-in-microsoft-teams"></a><span data-ttu-id="0b12e-103">Microsoft 팀의 정책 호출</span><span class="sxs-lookup"><span data-stu-id="0b12e-103">Calling policies in Microsoft Teams</span></span>
===================================

<span data-ttu-id="0b12e-104">Microsoft 팀에서 호출 정책은 사용자가 사용할 수 있는 통화 전달 기능을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b12e-104">In Microsoft Teams, calling policies control which calling and call forwarding features are available to users.</span></span> <span data-ttu-id="0b12e-105">호출 정책에 따라 사용자가 비공개 통화를 하거나, 착신 전환 또는 동시에 다른 사용자 또는 외부 전화 번호로 전화를 걸고, 음성 메일로 통화를 라우팅하고, 통화를 보낼 때 통화를 보내거나, 인바운드 및 아웃 바운드 통화에 대 한 위임을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b12e-105">Calling policies determine whether a user can make private calls, use call forwarding or  simultaneous ringing to other users or external phone numbers, route calls to voicemail, send calls to Call Groups, use delegation for inbound and outbound calls, and so on.</span></span> <span data-ttu-id="0b12e-106">기본 전역 정책은 자동으로 만들어지지만 관리자는 사용자 지정 전화 정책을 만들고 할당할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b12e-106">A default global policy is created automatically, but admins can also create and assign custom calling policies.</span></span>

## <a name="create-a-custom-calling-policy"></a><span data-ttu-id="0b12e-107">사용자 지정 호출 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="0b12e-107">Create a custom calling policy</span></span>

<span data-ttu-id="0b12e-108">사용자 지정 호출 정책을 만들려면 다음 단계를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="0b12e-108">Follow these steps to create a custom calling policy.</span></span>

1. <span data-ttu-id="0b12e-109">Microsoft 팀 관리 센터에서 **음성** > **통화 정책을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b12e-109">In the Microsoft Teams admin center, select **Voice** > **Calling policy**.</span></span>
2. <span data-ttu-id="0b12e-110">**새 정책을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b12e-110">Select **New policy**.</span></span>
3. <span data-ttu-id="0b12e-111">통화 정책에 사용할 기능을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b12e-111">Turn on the features that you want to use in your calling policy.</span></span> <span data-ttu-id="0b12e-112">모든 선택은 기본적으로 **해제** 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b12e-112">All selections are **Off** by default.</span></span>
4. <span data-ttu-id="0b12e-113">사용자가 음성 메일로 인바운드 통화를 라우팅할 수 있는지 여부를 제어 하려면 **항상 사용** 또는 **사용자 제어**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b12e-113">To control whether users can route inbound calls to voicemail, select **Always enabled** or **User controlled**.</span></span> <span data-ttu-id="0b12e-114">음성 메일로 라우팅이 안 되는 것을 방지 하려면 **항상 사용 안 함**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b12e-114">To prevent routing to voicemail, select **Always disabled**.</span></span>
5. <span data-ttu-id="0b12e-115">**저장**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b12e-115">Select **Save**.</span></span>

## <a name="modify-an-existing-calling-policy"></a><span data-ttu-id="0b12e-116">기존 통화 정책 수정</span><span class="sxs-lookup"><span data-stu-id="0b12e-116">Modify an existing calling policy</span></span>

<span data-ttu-id="0b12e-117">기존 통화 정책을 수정 하려면 다음 단계를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="0b12e-117">Follow these steps to modify an existing calling policy.</span></span>

1. <span data-ttu-id="0b12e-118">Microsoft 팀 관리 센터에서 **음성** > **통화 정책을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b12e-118">In the Microsoft Teams admin center, select **Voice** > **Calling policy**.</span></span>
2. <span data-ttu-id="0b12e-119">수정할 정책 옆에 있는을 클릭 한 다음 **편집**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b12e-119">Click next to the policy that you want to modify, and then select **Edit**.</span></span>
3. <span data-ttu-id="0b12e-120">통화 정책에 사용할 기능을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b12e-120">Turn on the features that you want to use in your calling policy.</span></span> <span data-ttu-id="0b12e-121">모든 선택은 기본적으로 **해제** 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b12e-121">All selections are **Off** by default.</span></span>
4. <span data-ttu-id="0b12e-122">사용자가 음성 메일로 인바운드 통화를 라우팅할 수 있는지 여부를 제어 하려면 **항상 사용** 또는 **사용자 제어**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b12e-122">To control whether users can route inbound calls to voicemail, select **Always enabled** or **User controlled**.</span></span> <span data-ttu-id="0b12e-123">음성 메일로 라우팅이 안 되는 것을 방지 하려면 **항상 사용 안 함**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b12e-123">To prevent routing to voicemail, select **Always disabled**.</span></span>
5. <span data-ttu-id="0b12e-124">**저장**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b12e-124">Select **Save**.</span></span>

## <a name="assign-a-calling-policy-to-a-user"></a><span data-ttu-id="0b12e-125">사용자에 게 호출 정책 할당</span><span class="sxs-lookup"><span data-stu-id="0b12e-125">Assign a calling policy to a user</span></span>

<span data-ttu-id="0b12e-126">사용자에 게 사용자 지정 호출 정책을 할당 하려면 다음 단계를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="0b12e-126">Follow these steps to assign a custom calling policy to a user.</span></span>

1. <span data-ttu-id="0b12e-127">Microsoft 팀 관리 센터에서 **음성** > **통화 정책을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b12e-127">In the Microsoft Teams admin center, select **Voice** > **Calling policy**.</span></span>
2. <span data-ttu-id="0b12e-128">정책 이름 옆에 있는을 클릭 하 여 선택 하 고 **사용자 관리**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b12e-128">Click next to the policy name to select it, and then select **Manage users**.</span></span>
3. <span data-ttu-id="0b12e-129">**사용자 관리** 창에서 사용자 이름을 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b12e-129">In the **Manage users** pane, search for the user's name.</span></span> <span data-ttu-id="0b12e-130">(3 개 이상의 문자를 입력 해야 합니다.)</span><span class="sxs-lookup"><span data-stu-id="0b12e-130">(You must enter at least three characters.)</span></span>
4. <span data-ttu-id="0b12e-131">사용자 이름을 선택한 다음 **추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b12e-131">Select the user's name, and then select **Add**.</span></span>
5. <span data-ttu-id="0b12e-132">**저장**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b12e-132">Select **Save**.</span></span>

## <a name="calling-policy-settings"></a><span data-ttu-id="0b12e-133">호출 정책 설정</span><span class="sxs-lookup"><span data-stu-id="0b12e-133">Calling policy settings</span></span>

<span data-ttu-id="0b12e-134">사용자 지정 호출 정책을 만들려면 다음 설정을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b12e-134">Use the following settings to create a custom calling policy.</span></span>

### <a name="user-can-make-private-calls"></a><span data-ttu-id="0b12e-135">사용자가 비공개 통화를 할 수 있음</span><span class="sxs-lookup"><span data-stu-id="0b12e-135">User can make private calls</span></span>

<span data-ttu-id="0b12e-136">이 설정은 팀의 모든 통화 기능을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b12e-136">This setting controls all calling capabilities in Teams.</span></span> <span data-ttu-id="0b12e-137">이 기능을 해제 하 여 팀의 모든 통화를 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b12e-137">Turn this off to turn off all calling functionality in Teams.</span></span>

### <a name="call-forwarding-and-simultaneous-ringing-to-other-users"></a><span data-ttu-id="0b12e-138">착신 전환 및 다른 사용자에 게 동시 신호음 울림</span><span class="sxs-lookup"><span data-stu-id="0b12e-138">Call forwarding and simultaneous ringing to other users</span></span>

<span data-ttu-id="0b12e-139">이 설정은 수신 전화를 다른 사용자에 게 전달 하거나 동시에 다른 사람에 게 연결할 수 있는지 여부를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b12e-139">This setting controls whether incoming calls can be forwarded to other users or can ring another person at the same time.</span></span> 

### <a name="call-forwarding-and-simultaneous-ringing-to-external-phone-numbers"></a><span data-ttu-id="0b12e-140">착신 전환 및 외부 전화 번호로의 동시 벨 울림</span><span class="sxs-lookup"><span data-stu-id="0b12e-140">Call forwarding and simultaneous ringing to external phone numbers</span></span>

<span data-ttu-id="0b12e-141">이 설정은 수신 전화를 외부 번호로 착신 전환할 수 있는지 여부 또는 동시에 외부 번호를 연결 하는 것을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b12e-141">This setting controls whether incoming calls can be forwarded to an external number or can ring an external number at the same time.</span></span>

### <a name="voicemail-is-available-for-routing-inbound-calls-to-users"></a><span data-ttu-id="0b12e-142">음성 메일을 사용 하 여 사용자에 게 들어오는 인바운드 전화 라우팅</span><span class="sxs-lookup"><span data-stu-id="0b12e-142">Voicemail is available for routing inbound calls to users</span></span>

<span data-ttu-id="0b12e-143">이 설정은 인바운드 전화를 음성 메일로 보낼 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b12e-143">This setting enables inbound calls to be sent to voicemail.</span></span> <span data-ttu-id="0b12e-144">유효한 옵션은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="0b12e-144">Valid options are:</span></span>

   - <span data-ttu-id="0b12e-145">**항상 사용** 음성 메일은 항상 인바운드 통화에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b12e-145">**Always enabled** Voicemail is always available for inbound calls.</span></span> 
   - <span data-ttu-id="0b12e-146">**항상 사용 안 함**  음성 메일을 인바운드 전화에 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0b12e-146">**Always disabled**  Voicemail is not available for inbound calls.</span></span> 
   - <span data-ttu-id="0b12e-147">**사용자 제어**</span><span class="sxs-lookup"><span data-stu-id="0b12e-147">**User controlled**.</span></span> <span data-ttu-id="0b12e-148">사용자는 보이스 메일을 사용할 수 있도록 할지 여부를 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b12e-148">Users can determine whether they want voicemail to be available.</span></span>

### <a name="inbound-calls-can-be-routed-to-call-groups"></a><span data-ttu-id="0b12e-149">호출 그룹에 대 한 인바운드 통화 라우팅 가능</span><span class="sxs-lookup"><span data-stu-id="0b12e-149">Inbound calls can be routed to call groups</span></span> 

> [!Include [feature preview](includes/preview-feature.md)]

<span data-ttu-id="0b12e-150">이 설정은 걸려오는 전화를 통화 그룹에 착신 전환할 수 있는지 여부를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b12e-150">This setting controls whether incoming calls can be forwarded to a call group.</span></span>

### <a name="allow-delegation-for-inbound-and-outbound-calls"></a><span data-ttu-id="0b12e-151">인바운드 및 아웃 바운드 통화에 대 한 위임 허용</span><span class="sxs-lookup"><span data-stu-id="0b12e-151">Allow delegation for inbound and outbound calls</span></span>

> [!Include [feature preview](includes/preview-feature.md)]

<span data-ttu-id="0b12e-152">이 설정을 사용 하면 들어오는 권한이 있는 사용자를 대신 하 여 대리인에 게 아웃 바운드 호출을 수행할 수 있도록 하는 인바운드 호출이 대리인에 게 전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b12e-152">This setting enables inbound calls to be routed to delegates, allowing delegates to make outbound calls on behalf of the users for whom they have delegated permissions.</span></span> <span data-ttu-id="0b12e-153">자세한 내용은 [대리인과 전화 회선 공유](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0b12e-153">For more information, see [Share a phone line with a delegate](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8).</span></span>


### <a name="prevent-toll-bypass-and-send-calls-through-the-pstn"></a><span data-ttu-id="0b12e-154">PSTN을 통한 무료 바이패스 및 전송 통화 방지</span><span class="sxs-lookup"><span data-stu-id="0b12e-154">Prevent toll bypass and send calls through the PSTN</span></span> 

<span data-ttu-id="0b12e-155">이로 설정 하면 PSTN을 통해 **전화를 보내고** , 네트워크를 통해 tolls를 우회 하는 대신 요금을 부과 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b12e-155">Setting this to **On** will send calls through the PSTN and incur charges rather than sending them through the network and bypassing the tolls.</span></span>

### <a name="busy-on-busy-is-available-while-in-a-call"></a><span data-ttu-id="0b12e-156">통화 중에도 다른 용무 중 통화를 이용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b12e-156">Busy on Busy is available while in a call</span></span>

<span data-ttu-id="0b12e-157">다른 용무 중 (다른 용무 중 옵션))은 사용자가 이미 통화 중이거나 회의에 있거나 통화 대기 상태에 있을 때 수신 통화가 처리 되는 방식을 구성할 수 있는 팀 정책에 대 한 새로운 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="0b12e-157">Busy on Busy (Busy Options)) is a new setting in Teams calling policies that lets you configure how incoming calls are handled when a user is already in a call or conference or has a call placed on hold.</span></span> <span data-ttu-id="0b12e-158">통화 중 신호를 사용 하 여 신규 또는 수신 전화를 거부할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b12e-158">New or incoming calls can be rejected with a busy signal.</span></span> <span data-ttu-id="0b12e-159">테 넌 트 수준 또는 사용자 수준에서 약속 있음/없음 옵션을 사용 하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b12e-159">You can enable busy options at the tenant level or at the user level.</span></span> <span data-ttu-id="0b12e-160">약속 있음/없음 옵션이 구성 되는 방법에 관계 없이 통화 또는 컨퍼런스 사용자 또는 통화 중 전화를 사용 하는 경우에는 새 통화 또는 회의를 시작 하는 것을 막을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0b12e-160">Regardless of how their busy options are configured, users in a call or conference or those with a call on hold are not prevented from initiating new calls or conferences.</span></span> <span data-ttu-id="0b12e-161">이 설정은 기본적으로 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0b12e-161">This setting is disabled by default.</span></span>

### <a name="allow-music-on-hold"></a><span data-ttu-id="0b12e-162">보류 중인 음악 허용</span><span class="sxs-lookup"><span data-stu-id="0b12e-162">Allow music on hold</span></span>

<span data-ttu-id="0b12e-163">이 설정을 사용 하면 PSTN 호출자가 보류 상태일 때 보류 중인 음악을 켜거나 끌 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b12e-163">This settings allows you to turn on or turn off music on hold when a PSTN caller is placed on hold.</span></span> <span data-ttu-id="0b12e-164">이 기능은 기본적으로 설정 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b12e-164">It is turned on by default.</span></span> <span data-ttu-id="0b12e-165">이 설정은 통화 공원 및 상사 대리인 기능에는 적용 되지 않으며, 현재 powershell을 통해서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b12e-165">This setting does not apply to call park and boss delegate features, and is only available via powershell currently.</span></span> 

## <a name="see-also"></a><span data-ttu-id="0b12e-166">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0b12e-166">See also</span></span>

[<span data-ttu-id="0b12e-167">Set-CSTeamsCallingPolicy</span><span class="sxs-lookup"><span data-stu-id="0b12e-167">Set-CSTeamsCallingPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps)
