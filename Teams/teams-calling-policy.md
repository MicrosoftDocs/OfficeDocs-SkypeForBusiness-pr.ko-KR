---
title: Microsoft 팀의 정책 호출
author: LolaJacobsen
ms.author: tonysmit
manager: serdars
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
ms.openlocfilehash: 7a67952854f608512e88786c2b49d1e2ad8dfcf9
ms.sourcegitcommit: 184f4f61a3e739a1cfa533c6d95d405d887ea25d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "44592801"
---
<a name="calling-policies-in-microsoft-teams"></a><span data-ttu-id="20f7c-103">Microsoft 팀의 정책 호출</span><span class="sxs-lookup"><span data-stu-id="20f7c-103">Calling policies in Microsoft Teams</span></span>
===================================

<span data-ttu-id="20f7c-104">Microsoft 팀에서 호출 정책은 사용자가 사용할 수 있는 통화 전달 기능을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="20f7c-104">In Microsoft Teams, calling policies control which calling and call forwarding features are available to users.</span></span> <span data-ttu-id="20f7c-105">호출 정책에 따라 사용자가 비공개 통화를 하거나, 착신 전환 또는 동시에 다른 사용자 또는 외부 전화 번호로 전화를 걸고, 음성 메일로 통화를 라우팅하고, 통화를 보낼 때 통화를 보내거나, 인바운드 및 아웃 바운드 통화에 대 한 위임을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20f7c-105">Calling policies determine whether a user can make private calls, use call forwarding or simultaneous ringing to other users or external phone numbers, route calls to voicemail, send calls to Call Groups, use delegation for inbound and outbound calls, and so on.</span></span> <span data-ttu-id="20f7c-106">기본 전역 정책은 자동으로 만들어지지만 관리자는 사용자 지정 전화 정책을 만들고 할당할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20f7c-106">A default global policy is created automatically, but admins can also create and assign custom calling policies.</span></span>

## <a name="create-a-custom-calling-policy"></a><span data-ttu-id="20f7c-107">사용자 지정 호출 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="20f7c-107">Create a custom calling policy</span></span>

<span data-ttu-id="20f7c-108">사용자 지정 호출 정책을 만들려면 다음 단계를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="20f7c-108">Follow these steps to create a custom calling policy.</span></span>

1. <span data-ttu-id="20f7c-109">Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **음성**  >  **통화 정책**으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="20f7c-109">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Calling policies**.</span></span>
2. <span data-ttu-id="20f7c-110">**추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="20f7c-110">Select **Add**.</span></span>
3. <span data-ttu-id="20f7c-111">통화 정책에 사용할 기능을 설정 하거나 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="20f7c-111">Turn on or turn off the features that you want to use in your calling policy.</span></span>
4. <span data-ttu-id="20f7c-112">사용자가 음성 메일로 인바운드 통화를 라우팅할 수 있는지 여부를 제어 하려면 **사용** 또는 **사용자 제어**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="20f7c-112">To control whether users can route inbound calls to voicemail, select **Enabled** or **User controlled**.</span></span> <span data-ttu-id="20f7c-113">보이스 메일로 라우팅이 되지 않도록 하려면 **사용 안 함**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="20f7c-113">To prevent routing to voicemail, select **Disabled**.</span></span>
5. <span data-ttu-id="20f7c-114">**저장**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="20f7c-114">Select **Save**.</span></span>

## <a name="modify-an-existing-calling-policy"></a><span data-ttu-id="20f7c-115">기존 통화 정책 수정</span><span class="sxs-lookup"><span data-stu-id="20f7c-115">Modify an existing calling policy</span></span>

<span data-ttu-id="20f7c-116">기존 통화 정책을 수정 하려면 다음 단계를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="20f7c-116">Follow these steps to modify an existing calling policy.</span></span>

1. <span data-ttu-id="20f7c-117">Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **음성**  >  **통화 정책을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="20f7c-117">In the left navigation of the Microsoft Teams admin center, select **Voice** > **Calling policies**.</span></span>
2. <span data-ttu-id="20f7c-118">수정할 정책 옆에 있는을 클릭 한 다음 **편집**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="20f7c-118">Click next to the policy that you want to modify, and then select **Edit**.</span></span>
3. <span data-ttu-id="20f7c-119">원하는 변경 작업을 수행한 다음 **저장**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="20f7c-119">Make the changes that you want, and then click **Save**.</span></span>

## <a name="assign-a-custom-calling-policy-to-users"></a><span data-ttu-id="20f7c-120">사용자에 게 사용자 지정 호출 정책 할당</span><span class="sxs-lookup"><span data-stu-id="20f7c-120">Assign a custom calling policy to users</span></span>

<span data-ttu-id="20f7c-121">한 사용자에 게 정책을 할당 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="20f7c-121">To assign a policy to one user:</span></span>

1. <span data-ttu-id="20f7c-122">Microsoft Teams 관리 센터의 왼쪽 탐색 창에서 **사용자**로 이동한 후 해당 사용자를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="20f7c-122">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="20f7c-123">사용자 이름의 왼쪽을 클릭하여 사용자를 선택한 후 **설정 편집**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="20f7c-123">Select the user by clicking to the left of the user name, and then click **Edit settings**.</span></span>
3. <span data-ttu-id="20f7c-124">**호출 정책**에서 할당할 호출 정책을 선택한 다음 **적용**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="20f7c-124">Under **Calling policy**, select the calling policy you want to assign, and then click **Apply**.</span></span>

<span data-ttu-id="20f7c-125">한 번에 여러 사용자에게 정책을 할당하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="20f7c-125">To assign a policy to multiple users at a time:</span></span>

1. <span data-ttu-id="20f7c-126">Microsoft Teams 관리 센터의 왼쪽 탐색에서 **사용자**로 이동한 다음, 사용자를 검색하거나 보기를 필터링하여 원하는 사용자를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="20f7c-126">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then search for the users or filter the view to show the users you want.</span></span>
2. <span data-ttu-id="20f7c-127">**&#x2713;**(확인 표시) 열에서 사용자를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="20f7c-127">In the **&#x2713;** (check mark) column, select the users.</span></span> <span data-ttu-id="20f7c-128">모든 사용자를 선택하려면 표 맨 위에서 &#x2713;(확인 표시)를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="20f7c-128">To select all users, click the &#x2713; (check mark) at the top of the table.</span></span>
3. <span data-ttu-id="20f7c-129">**설정 편집**을 클릭하고 원하는 대로 변경한 다음, **적용**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="20f7c-129">Click **Edit settings**, make the changes that you want, and then click **Apply**.</span></span>  

<span data-ttu-id="20f7c-130">또는 다음을 수행할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20f7c-130">Or, you can also do the following:</span></span>

1. <span data-ttu-id="20f7c-131">Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **음성**  >  **통화 정책**으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="20f7c-131">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Calling policies**.</span></span>
2. <span data-ttu-id="20f7c-132">정책 이름의 왼쪽을 클릭하여 정책을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="20f7c-132">Select the policy by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="20f7c-133">**사용자 관리**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="20f7c-133">Select **Manage users**.</span></span>
4. <span data-ttu-id="20f7c-134">**사용자 관리** 창에서 표시 이름 또는 사용자 이름으로 사용자를 검색하고 이름을 선택한 다음, **추가**를 선택하세요.</span><span class="sxs-lookup"><span data-stu-id="20f7c-134">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="20f7c-135">추가할 각 사용자에 대해 이 단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="20f7c-135">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="20f7c-136">사용자 추가를 마쳤으면 **저장**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="20f7c-136">After you finish adding users, select **Save**.</span></span>

## <a name="calling-policy-settings"></a><span data-ttu-id="20f7c-137">호출 정책 설정</span><span class="sxs-lookup"><span data-stu-id="20f7c-137">Calling policy settings</span></span>

<span data-ttu-id="20f7c-138">다음은 호출 정책에 대해 구성할 수 있는 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="20f7c-138">Here's the settings that you can configure for calling policies.</span></span>

### <a name="make-private-calls"></a><span data-ttu-id="20f7c-139">개인 전화 걸기</span><span class="sxs-lookup"><span data-stu-id="20f7c-139">Make private calls</span></span>

<span data-ttu-id="20f7c-140">이 설정은 팀의 모든 통화 기능을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="20f7c-140">This setting controls all calling capabilities in Teams.</span></span> <span data-ttu-id="20f7c-141">이 기능을 해제 하 여 팀의 모든 통화를 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="20f7c-141">Turn this off to turn off all calling functionality in Teams.</span></span>

### <a name="call-forwarding-and-simultaneous-ringing-to-people-in-your-organization"></a><span data-ttu-id="20f7c-142">조직 내 사용자에 게 착신 전환 및 동시 연결</span><span class="sxs-lookup"><span data-stu-id="20f7c-142">Call forwarding and simultaneous ringing to people in your organization</span></span>

<span data-ttu-id="20f7c-143">이 설정은 수신 전화를 다른 사용자에 게 전달 하거나 동시에 다른 사람에 게 연결할 수 있는지 여부를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="20f7c-143">This setting controls whether incoming calls can be forwarded to other users or can ring another person at the same time.</span></span> 

### <a name="call-forwarding-and-simultaneous-ringing-to-external-phone-numbers"></a><span data-ttu-id="20f7c-144">착신 전환 및 외부 전화 번호로의 동시 벨 울림</span><span class="sxs-lookup"><span data-stu-id="20f7c-144">Call forwarding and simultaneous ringing to external phone numbers</span></span>

<span data-ttu-id="20f7c-145">이 설정은 수신 전화를 외부 번호로 착신 전환할 수 있는지 여부 또는 동시에 외부 번호를 연결 하는 것을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="20f7c-145">This setting controls whether incoming calls can be forwarded to an external number or can ring an external number at the same time.</span></span>

### <a name="voicemail-is-available-for-routing-inbound-calls"></a><span data-ttu-id="20f7c-146">음성 메일을 통해 인바운드 전화를 라우팅할 수 있음</span><span class="sxs-lookup"><span data-stu-id="20f7c-146">Voicemail is available for routing inbound calls</span></span>

<span data-ttu-id="20f7c-147">이 설정은 인바운드 전화를 음성 메일로 보낼 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="20f7c-147">This setting enables inbound calls to be sent to voicemail.</span></span> <span data-ttu-id="20f7c-148">유효한 옵션은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="20f7c-148">Valid options are:</span></span>

- <span data-ttu-id="20f7c-149">**사용 하도록 설정** 음성 메일은 항상 인바운드 통화에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20f7c-149">**Enabled** Voicemail is always available for inbound calls.</span></span> 
- <span data-ttu-id="20f7c-150">**사용 안 함**  음성 메일을 인바운드 전화에 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="20f7c-150">**Disabled**  Voicemail is not available for inbound calls.</span></span> 
- <span data-ttu-id="20f7c-151">**사용자 제어** 사용자는 보이스 메일을 사용할 수 있도록 할지 여부를 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20f7c-151">**User controlled** Users can determine whether they want voicemail to be available.</span></span>

### <a name="inbound-calls-can-be-routed-to-call-groups"></a><span data-ttu-id="20f7c-152">호출 그룹에 대 한 인바운드 통화 라우팅 가능</span><span class="sxs-lookup"><span data-stu-id="20f7c-152">Inbound calls can be routed to call groups</span></span> 

> [!Include [feature preview](includes/preview-feature.md)]

<span data-ttu-id="20f7c-153">이 설정은 걸려오는 전화를 통화 그룹에 착신 전환할 수 있는지 여부를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="20f7c-153">This setting controls whether incoming calls can be forwarded to a call group.</span></span>

### <a name="allow-delegation-for-inbound-and-outbound-calls"></a><span data-ttu-id="20f7c-154">인바운드 및 아웃 바운드 통화에 대 한 위임 허용</span><span class="sxs-lookup"><span data-stu-id="20f7c-154">Allow delegation for inbound and outbound calls</span></span>

> [!Include [feature preview](includes/preview-feature.md)]

<span data-ttu-id="20f7c-155">이 설정을 사용 하면 들어오는 권한이 있는 사용자를 대신 하 여 대리인에 게 아웃 바운드 호출을 수행할 수 있도록 하는 인바운드 호출이 대리인에 게 전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="20f7c-155">This setting enables inbound calls to be routed to delegates, allowing delegates to make outbound calls on behalf of the users for whom they have delegated permissions.</span></span> <span data-ttu-id="20f7c-156">자세한 내용은 [대리인과 전화 회선 공유](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="20f7c-156">For more information, see [Share a phone line with a delegate](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8).</span></span>

### <a name="prevent-toll-bypass-and-send-calls-through-the-pstn"></a><span data-ttu-id="20f7c-157">PSTN을 통한 무료 바이패스 및 전송 통화 방지</span><span class="sxs-lookup"><span data-stu-id="20f7c-157">Prevent toll bypass and send calls through the PSTN</span></span> 

<span data-ttu-id="20f7c-158">이로 설정 하면 PSTN을 통해 **전화를 보내고** , 네트워크를 통해 tolls를 우회 하는 대신 요금을 부과 합니다.</span><span class="sxs-lookup"><span data-stu-id="20f7c-158">Setting this to **On** will send calls through the PSTN and incur charges rather than sending them through the network and bypassing the tolls.</span></span>

### <a name="busy-on-busy-is-available-while-in-a-call"></a><span data-ttu-id="20f7c-159">통화 중에도 다른 용무 중 통화를 이용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20f7c-159">Busy on Busy is available while in a call</span></span>

<span data-ttu-id="20f7c-160">다른 용무 중 (약속 있음 옵션)은 사용자가 이미 통화 중이거나 회의에 있거나 통화 대기 상태에 있을 때 수신 통화가 처리 되는 방식을 구성할 수 있는 새로운 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="20f7c-160">Busy on Busy (Busy Options) is a new setting that lets you configure how incoming calls are handled when a user is already in a call or conference or has a call placed on hold.</span></span> <span data-ttu-id="20f7c-161">통화 중 신호를 사용 하 여 신규 또는 수신 전화를 거부할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20f7c-161">New or incoming calls can be rejected with a busy signal.</span></span> <span data-ttu-id="20f7c-162">테 넌 트 수준 또는 사용자 수준에서 약속 있음/없음 옵션을 사용 하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20f7c-162">You can enable busy options at the tenant level or at the user level.</span></span> <span data-ttu-id="20f7c-163">약속 있음/없음 옵션이 구성 되는 방법에 관계 없이 통화 또는 컨퍼런스 사용자 또는 통화 중 전화를 사용 하는 경우에는 새 통화 또는 회의를 시작 하는 것을 막을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="20f7c-163">Regardless of how their busy options are configured, users in a call or conference or those with a call on hold are not prevented from initiating new calls or conferences.</span></span> <span data-ttu-id="20f7c-164">이 설정은 기본적으로 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="20f7c-164">This setting is disabled by default.</span></span>

### <a name="allow-web-pstn-calling"></a><span data-ttu-id="20f7c-165">웹 PSTN 통화 허용</span><span class="sxs-lookup"><span data-stu-id="20f7c-165">Allow web PSTN calling</span></span>

<span data-ttu-id="20f7c-166">이 설정은 사용자가 팀 웹 클라이언트를 사용 하 여 PSTN 번호를 호출할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="20f7c-166">This setting enables users to call PSTN numbers using the Teams web client.</span></span>

### <a name="allow-music-on-hold"></a><span data-ttu-id="20f7c-167">보류 중인 음악 허용</span><span class="sxs-lookup"><span data-stu-id="20f7c-167">Allow music on hold</span></span>

<span data-ttu-id="20f7c-168">이 설정을 사용 하면 PSTN 호출자가 보류 상태일 때 보류 중인 음악을 켜거나 끌 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20f7c-168">This setting allows you to turn on or turn off music on hold when a PSTN caller is placed on hold.</span></span> <span data-ttu-id="20f7c-169">기본적으로 설정 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20f7c-169">It's turned on by default.</span></span> <span data-ttu-id="20f7c-170">이 설정은 통화 공원 및 상사 대리인 기능에는 적용 되지 않으며 현재 PowerShell을 통해서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20f7c-170">This setting doesn't apply to call park and boss delegate features, and is currently only available via PowerShell.</span></span>

## <a name="see-also"></a><span data-ttu-id="20f7c-171">참고 항목</span><span class="sxs-lookup"><span data-stu-id="20f7c-171">See also</span></span>

[<span data-ttu-id="20f7c-172">Set-CSTeamsCallingPolicy</span><span class="sxs-lookup"><span data-stu-id="20f7c-172">Set-CSTeamsCallingPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps)
