---
title: Microsoft Teams의 통화 정책
author: SerdarSoysal
ms.author: tonysmit
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: jastark
audience: admin
search.appverid: MET150
description: 다양한 통화 정책 설정뿐만 아니라 Microsoft Teams의 사용자 지정 통화 정책에 사용자를 만들고, 수정하고, 추가하는 방법을 배워야 합니다.
localization_priority: Normal
ms.collection:
- M365-voice
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.callingpolicies.overview
- seo-marvel-apr2020
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 03ec48de66bc5b179b3a1d8cfe006b1789d09a33
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48581079"
---
<a name="calling-policies-in-microsoft-teams"></a><span data-ttu-id="69218-103">Microsoft Teams의 통화 정책</span><span class="sxs-lookup"><span data-stu-id="69218-103">Calling policies in Microsoft Teams</span></span>
===================================

<span data-ttu-id="69218-104">Microsoft Teams에서 통화 정책은 사용자가 사용할 수 있는 통화 및 통화 전달 기능을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="69218-104">In Microsoft Teams, calling policies control which calling and call forwarding features are available to users.</span></span> <span data-ttu-id="69218-105">통화 정책은 사용자가 개인 통화를 걸 수 있는지, 다른 사용자 또는 외부 전화 번호로 통화 전달 또는 동시 연결, 음성 메일로 통화 라우팅, 통화 그룹으로 통화 보내기, 인바운드 및 아웃바운드 통화에 대한 위임 사용 여부를 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69218-105">Calling policies determine whether a user can make private calls, use call forwarding or simultaneous ringing to other users or external phone numbers, route calls to voicemail, send calls to call groups, use delegation for inbound and outbound calls, and so on.</span></span>

<span data-ttu-id="69218-106">자동으로 만들어지거나 사용자 지정 정책을 만들고 할당하는 전역(전체 기본) 정책을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69218-106">You can use the global (Org-wide default) policy that's created automatically or create and assign custom policies.</span></span>

## <a name="create-a-custom-calling-policy"></a><span data-ttu-id="69218-107">사용자 지정 호출 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="69218-107">Create a custom calling policy</span></span>

<span data-ttu-id="69218-108">다음 단계에 따라 사용자 지정 호출 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69218-108">Follow these steps to create a custom calling policy.</span></span>

1. <span data-ttu-id="69218-109">Microsoft Teams 관리 센터의 왼쪽 탐색 모음에서 **음성** 통화  >  **정책으로 이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="69218-109">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Calling policies**.</span></span>
2. <span data-ttu-id="69218-110">**추가** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="69218-110">Select **Add**.</span></span>
3. <span data-ttu-id="69218-111">통화 정책에 사용하려는 기능을 설정하거나 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="69218-111">Turn on or turn off the features that you want to use in your calling policy.</span></span>
4. <span data-ttu-id="69218-112">사용자가 인바운드 통화를 음성으로 라우팅할 수 있는지 여부를 제어하려면 [사용] 또는 **[사용자** **제어]를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="69218-112">To control whether users can route inbound calls to voicemail, select **Enabled** or **User controlled**.</span></span> <span data-ttu-id="69218-113">음성메일로의 라우팅을 방지하려면 사용 안 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="69218-113">To prevent routing to voicemail, select **Disabled**.</span></span>
5. <span data-ttu-id="69218-114">저장을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="69218-114">Select **Save**.</span></span>

## <a name="edit-a-calling-policy"></a><span data-ttu-id="69218-115">통화 정책 편집</span><span class="sxs-lookup"><span data-stu-id="69218-115">Edit a calling policy</span></span>

<span data-ttu-id="69218-116">다음 단계에 따라 기존 호출 정책을 편집합니다.</span><span class="sxs-lookup"><span data-stu-id="69218-116">Follow these steps to edit an existing calling policy.</span></span>

1. <span data-ttu-id="69218-117">Microsoft Teams 관리 센터의 왼쪽 탐색 모음에서 음성 통화 **정책을**  >  **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="69218-117">In the left navigation of the Microsoft Teams admin center, select **Voice** > **Calling policies**.</span></span>
2. <span data-ttu-id="69218-118">수정할 정책 옆을 클릭한 다음 편집을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="69218-118">Click next to the policy that you want to modify, and then select **Edit**.</span></span>
3. <span data-ttu-id="69218-119">원하는 내용을 변경한 다음 저장을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="69218-119">Make the changes that you want, and then click **Save**.</span></span>

## <a name="assign-a-custom-calling-policy-to-users"></a><span data-ttu-id="69218-120">사용자에게 사용자 지정 호출 정책 할당</span><span class="sxs-lookup"><span data-stu-id="69218-120">Assign a custom calling policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="calling-policy-settings"></a><span data-ttu-id="69218-121">정책 설정 호출</span><span class="sxs-lookup"><span data-stu-id="69218-121">Calling policy settings</span></span>

<span data-ttu-id="69218-122">다음은 호출 정책에 대해 구성할 수 있는 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="69218-122">Here's the settings that you can configure for calling policies.</span></span>

### <a name="make-private-calls"></a><span data-ttu-id="69218-123">개인 전화 걸기</span><span class="sxs-lookup"><span data-stu-id="69218-123">Make private calls</span></span>

<span data-ttu-id="69218-124">이 설정은 Teams의 모든 통화 기능을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="69218-124">This setting controls all calling capabilities in Teams.</span></span> <span data-ttu-id="69218-125">이 기능을 해제하여 Teams의 모든 통화 기능을 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="69218-125">Turn this off to turn off all calling functionality in Teams.</span></span>

### <a name="call-forwarding-and-simultaneous-ringing-to-people-in-your-organization"></a><span data-ttu-id="69218-126">조직의 사용자에 대한 전달 및 동시 통화</span><span class="sxs-lookup"><span data-stu-id="69218-126">Call forwarding and simultaneous ringing to people in your organization</span></span>

<span data-ttu-id="69218-127">이 설정은 수신 전화를 다른 사용자에게 전달할 수 있는지 아니면 동시에 다른 사용자에게 전화를 걸 수 있는지 여부를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="69218-127">This setting controls whether incoming calls can be forwarded to other users or can ring another person at the same time.</span></span> 

### <a name="call-forwarding-and-simultaneous-ringing-to-external-phone-numbers"></a><span data-ttu-id="69218-128">외부 전화 번호로의 통화 전달 및 동시 연결</span><span class="sxs-lookup"><span data-stu-id="69218-128">Call forwarding and simultaneous ringing to external phone numbers</span></span>

<span data-ttu-id="69218-129">이 설정은 들어오는 호출을 외부 번호로 전달할 수 있는지 아니면 외부 번호에 동시에 연결될 수 있는지를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="69218-129">This setting controls whether incoming calls can be forwarded to an external number or can ring an external number at the same time.</span></span>

### <a name="voicemail-is-available-for-routing-inbound-calls"></a><span data-ttu-id="69218-130">음성메일은 인바운드 통화 라우팅에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69218-130">Voicemail is available for routing inbound calls</span></span>

<span data-ttu-id="69218-131">이 설정을 사용하면 인바운드 통화를 음성 메일로 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69218-131">This setting enables inbound calls to be sent to voicemail.</span></span> <span data-ttu-id="69218-132">유효한 옵션은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="69218-132">Valid options are:</span></span>

- <span data-ttu-id="69218-133">**사용** 음성메일은 인바운드 통화에 항상 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69218-133">**Enabled** Voicemail is always available for inbound calls.</span></span>
- <span data-ttu-id="69218-134">**사용 안**  음성메일은 인바운드 통화에 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="69218-134">**Disabled**  Voicemail is not available for inbound calls.</span></span>
- <span data-ttu-id="69218-135">**사용자가 제어** 사용자는 음성메일을 사용할 수 있는지 여부를 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69218-135">**User controlled** Users can determine whether they want voicemail to be available.</span></span>

### <a name="inbound-calls-can-be-routed-to-call-groups"></a><span data-ttu-id="69218-136">인바운드 호출을 호출 그룹으로 라우팅할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69218-136">Inbound calls can be routed to call groups</span></span> 

> [!Include [feature preview](includes/preview-feature.md)]

<span data-ttu-id="69218-137">이 설정은 수신 전화를 호출 그룹으로 전달할 수 있는지 여부를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="69218-137">This setting controls whether incoming calls can be forwarded to a call group.</span></span>

### <a name="allow-delegation-for-inbound-and-outbound-calls"></a><span data-ttu-id="69218-138">인바운드 및 아웃바운드 호출에 대한 위임 허용</span><span class="sxs-lookup"><span data-stu-id="69218-138">Allow delegation for inbound and outbound calls</span></span>

> [!Include [feature preview](includes/preview-feature.md)]

<span data-ttu-id="69218-139">이 설정을 사용하면 인바운드 호출을 대리인으로 라우팅할 수 있어 대리인이 위임된 권한을 부여한 사용자를 대신하여 아웃바운드 호출을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69218-139">This setting enables inbound calls to be routed to delegates, allowing delegates to make outbound calls on behalf of the users for whom they have delegated permissions.</span></span> <span data-ttu-id="69218-140">자세한 내용은 [대리인과 전화선 공유를 참조하세요.](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)</span><span class="sxs-lookup"><span data-stu-id="69218-140">For more information, see [Share a phone line with a delegate](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8).</span></span>

### <a name="prevent-toll-bypass-and-send-calls-through-the-pstn"></a><span data-ttu-id="69218-141">PSTN을 통해 수신 우회 및 통화 보내기 방지</span><span class="sxs-lookup"><span data-stu-id="69218-141">Prevent toll bypass and send calls through the PSTN</span></span> 

<span data-ttu-id="69218-142">이를 **On으로 설정하면** PSTN을 통해 통화를 보내고 네트워크를 통해 통화를 보내고 요금을 우회하는 대신 요금이 부과됩니다.</span><span class="sxs-lookup"><span data-stu-id="69218-142">Setting this to **On** will send calls through the PSTN and incur charges rather than sending them through the network and bypassing the tolls.</span></span>

### <a name="busy-on-busy-is-available-while-in-a-call"></a><span data-ttu-id="69218-143">통화 중 사용 중 사용 가능</span><span class="sxs-lookup"><span data-stu-id="69218-143">Busy on Busy is available while in a call</span></span>

<span data-ttu-id="69218-144">사용 중(사용 중 옵션)은 사용자가 이미 통화 또는 회의에 참석 중이거나 통화가 보류 중일 때 수신 전화가 처리되는 방법을 구성할 수 있는 새로운 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="69218-144">Busy on Busy (Busy Options) is a new setting that lets you configure how incoming calls are handled when a user is already in a call or conference or has a call placed on hold.</span></span> <span data-ttu-id="69218-145">새 호출 또는 들어오는 호출은 사용 중 신호로 거부될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69218-145">New or incoming calls can be rejected with a busy signal.</span></span> <span data-ttu-id="69218-146">테넌트 수준 또는 사용자 수준에서 사용 중 옵션을 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69218-146">You can enable busy options at the tenant level or at the user level.</span></span> <span data-ttu-id="69218-147">사용 중 옵션을 구성하는 방법에 관계없이 통화 또는 회의에 참여하는 사용자나 통화가 보류된 사용자는 새 통화나 회의를 시작할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="69218-147">Regardless of how their busy options are configured, users in a call or conference or those with a call on hold are not prevented from initiating new calls or conferences.</span></span> <span data-ttu-id="69218-148">이 설정은 기본적으로 사용하지 않도록 설정되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69218-148">This setting is disabled by default.</span></span>

### <a name="allow-web-pstn-calling"></a><span data-ttu-id="69218-149">웹 PSTN 통화 허용</span><span class="sxs-lookup"><span data-stu-id="69218-149">Allow web PSTN calling</span></span>

<span data-ttu-id="69218-150">이 설정을 사용하면 사용자가 Teams 웹 클라이언트를 사용하여 PSTN 번호로 전화를 걸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69218-150">This setting enables users to call PSTN numbers using the Teams web client.</span></span>

### <a name="allow-music-on-hold"></a><span data-ttu-id="69218-151">보류 중 음악 허용</span><span class="sxs-lookup"><span data-stu-id="69218-151">Allow music on hold</span></span>

<span data-ttu-id="69218-152">이 설정을 사용하면 PSTN 호출자에 보류된 경우 음악 보류를 켜거나 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69218-152">This setting allows you to turn on or turn off music on hold when a PSTN caller is placed on hold.</span></span> <span data-ttu-id="69218-153">기본적으로 켜져 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69218-153">It's turned on by default.</span></span> <span data-ttu-id="69218-154">이 설정은 통화 공원 및 상사 대리인 기능에는 적용되지 않습니다. 현재 PowerShell을 통해서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69218-154">This setting doesn't apply to call park and boss delegate features, and is currently only available via PowerShell.</span></span>

## <a name="related-topics"></a><span data-ttu-id="69218-155">관련 항목</span><span class="sxs-lookup"><span data-stu-id="69218-155">Related topics</span></span>

[<span data-ttu-id="69218-156">Set-CSTeamsCallingPolicy</span><span class="sxs-lookup"><span data-stu-id="69218-156">Set-CSTeamsCallingPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps)

[<span data-ttu-id="69218-157">Teams에서 사용자에게 정책 할당</span><span class="sxs-lookup"><span data-stu-id="69218-157">Assign policies to your users in Teams</span></span>](assign-policies.md)
