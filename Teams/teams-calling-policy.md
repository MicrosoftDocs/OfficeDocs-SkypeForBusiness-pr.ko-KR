---
title: Microsoft 팀의 정책 호출
author: SerdarSoysal
ms.author: tonysmit
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: jastark
audience: admin
search.appverid: MET150
description: Microsoft 팀의 사용자 지정 통화 정책에 대 한 사용자를 만들고, 수정 하 고, 추가 하는 방법을 알아보고, 다양 한 통화 정책 설정을 확인 합니다.
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
<a name="calling-policies-in-microsoft-teams"></a><span data-ttu-id="7dcc3-103">Microsoft 팀의 정책 호출</span><span class="sxs-lookup"><span data-stu-id="7dcc3-103">Calling policies in Microsoft Teams</span></span>
===================================

<span data-ttu-id="7dcc3-104">Microsoft 팀에서 호출 정책은 사용자가 사용할 수 있는 통화 전달 기능을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="7dcc3-104">In Microsoft Teams, calling policies control which calling and call forwarding features are available to users.</span></span> <span data-ttu-id="7dcc3-105">호출 정책에 따라 사용자가 비공개 통화를 하거나, 착신 전환 또는 동시에 다른 사용자 또는 외부 전화 번호로 전화를 걸고, 음성 메일로 통화를 라우팅하고, 통화를 보낼 때 통화를 보내거나, 인바운드 및 아웃 바운드 통화에 대 한 위임을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7dcc3-105">Calling policies determine whether a user can make private calls, use call forwarding or simultaneous ringing to other users or external phone numbers, route calls to voicemail, send calls to call groups, use delegation for inbound and outbound calls, and so on.</span></span>

<span data-ttu-id="7dcc3-106">자동으로 생성 되는 전역 (조직 차원의 기본) 정책을 사용 하거나 사용자 지정 정책을 만들고 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7dcc3-106">You can use the global (Org-wide default) policy that's created automatically or create and assign custom policies.</span></span>

## <a name="create-a-custom-calling-policy"></a><span data-ttu-id="7dcc3-107">사용자 지정 호출 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="7dcc3-107">Create a custom calling policy</span></span>

<span data-ttu-id="7dcc3-108">사용자 지정 호출 정책을 만들려면 다음 단계를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="7dcc3-108">Follow these steps to create a custom calling policy.</span></span>

1. <span data-ttu-id="7dcc3-109">Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **음성**  >  **통화 정책**으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="7dcc3-109">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Calling policies**.</span></span>
2. <span data-ttu-id="7dcc3-110">**추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7dcc3-110">Select **Add**.</span></span>
3. <span data-ttu-id="7dcc3-111">통화 정책에 사용할 기능을 설정 하거나 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="7dcc3-111">Turn on or turn off the features that you want to use in your calling policy.</span></span>
4. <span data-ttu-id="7dcc3-112">사용자가 음성 메일로 인바운드 통화를 라우팅할 수 있는지 여부를 제어 하려면 **사용** 또는 **사용자 제어**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7dcc3-112">To control whether users can route inbound calls to voicemail, select **Enabled** or **User controlled**.</span></span> <span data-ttu-id="7dcc3-113">보이스 메일로 라우팅이 되지 않도록 하려면 **사용 안 함**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7dcc3-113">To prevent routing to voicemail, select **Disabled**.</span></span>
5. <span data-ttu-id="7dcc3-114">**저장**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7dcc3-114">Select **Save**.</span></span>

## <a name="edit-a-calling-policy"></a><span data-ttu-id="7dcc3-115">통화 정책 편집</span><span class="sxs-lookup"><span data-stu-id="7dcc3-115">Edit a calling policy</span></span>

<span data-ttu-id="7dcc3-116">기존 통화 정책을 편집 하려면 다음 단계를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="7dcc3-116">Follow these steps to edit an existing calling policy.</span></span>

1. <span data-ttu-id="7dcc3-117">Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **음성**  >  **통화 정책을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7dcc3-117">In the left navigation of the Microsoft Teams admin center, select **Voice** > **Calling policies**.</span></span>
2. <span data-ttu-id="7dcc3-118">수정할 정책 옆에 있는을 클릭 한 다음 **편집**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7dcc3-118">Click next to the policy that you want to modify, and then select **Edit**.</span></span>
3. <span data-ttu-id="7dcc3-119">원하는 변경 작업을 수행한 다음 **저장**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="7dcc3-119">Make the changes that you want, and then click **Save**.</span></span>

## <a name="assign-a-custom-calling-policy-to-users"></a><span data-ttu-id="7dcc3-120">사용자에 게 사용자 지정 호출 정책 할당</span><span class="sxs-lookup"><span data-stu-id="7dcc3-120">Assign a custom calling policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="calling-policy-settings"></a><span data-ttu-id="7dcc3-121">호출 정책 설정</span><span class="sxs-lookup"><span data-stu-id="7dcc3-121">Calling policy settings</span></span>

<span data-ttu-id="7dcc3-122">다음은 호출 정책에 대해 구성할 수 있는 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="7dcc3-122">Here's the settings that you can configure for calling policies.</span></span>

### <a name="make-private-calls"></a><span data-ttu-id="7dcc3-123">개인 전화 걸기</span><span class="sxs-lookup"><span data-stu-id="7dcc3-123">Make private calls</span></span>

<span data-ttu-id="7dcc3-124">이 설정은 팀의 모든 통화 기능을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="7dcc3-124">This setting controls all calling capabilities in Teams.</span></span> <span data-ttu-id="7dcc3-125">이 기능을 해제 하 여 팀의 모든 통화를 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="7dcc3-125">Turn this off to turn off all calling functionality in Teams.</span></span>

### <a name="call-forwarding-and-simultaneous-ringing-to-people-in-your-organization"></a><span data-ttu-id="7dcc3-126">조직 내 사용자에 게 착신 전환 및 동시 연결</span><span class="sxs-lookup"><span data-stu-id="7dcc3-126">Call forwarding and simultaneous ringing to people in your organization</span></span>

<span data-ttu-id="7dcc3-127">이 설정은 수신 전화를 다른 사용자에 게 전달 하거나 동시에 다른 사람에 게 연결할 수 있는지 여부를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="7dcc3-127">This setting controls whether incoming calls can be forwarded to other users or can ring another person at the same time.</span></span> 

### <a name="call-forwarding-and-simultaneous-ringing-to-external-phone-numbers"></a><span data-ttu-id="7dcc3-128">착신 전환 및 외부 전화 번호로의 동시 벨 울림</span><span class="sxs-lookup"><span data-stu-id="7dcc3-128">Call forwarding and simultaneous ringing to external phone numbers</span></span>

<span data-ttu-id="7dcc3-129">이 설정은 수신 전화를 외부 번호로 착신 전환할 수 있는지 여부 또는 동시에 외부 번호를 연결 하는 것을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="7dcc3-129">This setting controls whether incoming calls can be forwarded to an external number or can ring an external number at the same time.</span></span>

### <a name="voicemail-is-available-for-routing-inbound-calls"></a><span data-ttu-id="7dcc3-130">음성 메일을 통해 인바운드 전화를 라우팅할 수 있음</span><span class="sxs-lookup"><span data-stu-id="7dcc3-130">Voicemail is available for routing inbound calls</span></span>

<span data-ttu-id="7dcc3-131">이 설정은 인바운드 전화를 음성 메일로 보낼 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="7dcc3-131">This setting enables inbound calls to be sent to voicemail.</span></span> <span data-ttu-id="7dcc3-132">유효한 옵션은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="7dcc3-132">Valid options are:</span></span>

- <span data-ttu-id="7dcc3-133">**사용 하도록 설정** 음성 메일은 항상 인바운드 통화에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7dcc3-133">**Enabled** Voicemail is always available for inbound calls.</span></span>
- <span data-ttu-id="7dcc3-134">**사용 안 함**  음성 메일을 인바운드 전화에 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7dcc3-134">**Disabled**  Voicemail is not available for inbound calls.</span></span>
- <span data-ttu-id="7dcc3-135">**사용자 제어** 사용자는 보이스 메일을 사용할 수 있도록 할지 여부를 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7dcc3-135">**User controlled** Users can determine whether they want voicemail to be available.</span></span>

### <a name="inbound-calls-can-be-routed-to-call-groups"></a><span data-ttu-id="7dcc3-136">호출 그룹에 대 한 인바운드 통화 라우팅 가능</span><span class="sxs-lookup"><span data-stu-id="7dcc3-136">Inbound calls can be routed to call groups</span></span> 

> [!Include [feature preview](includes/preview-feature.md)]

<span data-ttu-id="7dcc3-137">이 설정은 걸려오는 전화를 통화 그룹에 착신 전환할 수 있는지 여부를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="7dcc3-137">This setting controls whether incoming calls can be forwarded to a call group.</span></span>

### <a name="allow-delegation-for-inbound-and-outbound-calls"></a><span data-ttu-id="7dcc3-138">인바운드 및 아웃 바운드 통화에 대 한 위임 허용</span><span class="sxs-lookup"><span data-stu-id="7dcc3-138">Allow delegation for inbound and outbound calls</span></span>

> [!Include [feature preview](includes/preview-feature.md)]

<span data-ttu-id="7dcc3-139">이 설정을 사용 하면 들어오는 권한이 있는 사용자를 대신 하 여 대리인에 게 아웃 바운드 호출을 수행할 수 있도록 하는 인바운드 호출이 대리인에 게 전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7dcc3-139">This setting enables inbound calls to be routed to delegates, allowing delegates to make outbound calls on behalf of the users for whom they have delegated permissions.</span></span> <span data-ttu-id="7dcc3-140">자세한 내용은 [대리인과 전화 회선 공유](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7dcc3-140">For more information, see [Share a phone line with a delegate](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8).</span></span>

### <a name="prevent-toll-bypass-and-send-calls-through-the-pstn"></a><span data-ttu-id="7dcc3-141">PSTN을 통한 무료 바이패스 및 전송 통화 방지</span><span class="sxs-lookup"><span data-stu-id="7dcc3-141">Prevent toll bypass and send calls through the PSTN</span></span> 

<span data-ttu-id="7dcc3-142">이로 설정 하면 PSTN을 통해 **전화를 보내고** , 네트워크를 통해 tolls를 우회 하는 대신 요금을 부과 합니다.</span><span class="sxs-lookup"><span data-stu-id="7dcc3-142">Setting this to **On** will send calls through the PSTN and incur charges rather than sending them through the network and bypassing the tolls.</span></span>

### <a name="busy-on-busy-is-available-while-in-a-call"></a><span data-ttu-id="7dcc3-143">통화 중에도 다른 용무 중 통화를 이용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7dcc3-143">Busy on Busy is available while in a call</span></span>

<span data-ttu-id="7dcc3-144">다른 용무 중 (약속 있음 옵션)은 사용자가 이미 통화 중이거나 회의에 있거나 통화 대기 상태에 있을 때 수신 통화가 처리 되는 방식을 구성할 수 있는 새로운 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="7dcc3-144">Busy on Busy (Busy Options) is a new setting that lets you configure how incoming calls are handled when a user is already in a call or conference or has a call placed on hold.</span></span> <span data-ttu-id="7dcc3-145">통화 중 신호를 사용 하 여 신규 또는 수신 전화를 거부할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7dcc3-145">New or incoming calls can be rejected with a busy signal.</span></span> <span data-ttu-id="7dcc3-146">테 넌 트 수준 또는 사용자 수준에서 약속 있음/없음 옵션을 사용 하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7dcc3-146">You can enable busy options at the tenant level or at the user level.</span></span> <span data-ttu-id="7dcc3-147">약속 있음/없음 옵션이 구성 되는 방법에 관계 없이 통화 또는 컨퍼런스 사용자 또는 통화 중 전화를 사용 하는 경우에는 새 통화 또는 회의를 시작 하는 것을 막을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7dcc3-147">Regardless of how their busy options are configured, users in a call or conference or those with a call on hold are not prevented from initiating new calls or conferences.</span></span> <span data-ttu-id="7dcc3-148">이 설정은 기본적으로 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7dcc3-148">This setting is disabled by default.</span></span>

### <a name="allow-web-pstn-calling"></a><span data-ttu-id="7dcc3-149">웹 PSTN 통화 허용</span><span class="sxs-lookup"><span data-stu-id="7dcc3-149">Allow web PSTN calling</span></span>

<span data-ttu-id="7dcc3-150">이 설정은 사용자가 팀 웹 클라이언트를 사용 하 여 PSTN 번호를 호출할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="7dcc3-150">This setting enables users to call PSTN numbers using the Teams web client.</span></span>

### <a name="allow-music-on-hold"></a><span data-ttu-id="7dcc3-151">보류 중인 음악 허용</span><span class="sxs-lookup"><span data-stu-id="7dcc3-151">Allow music on hold</span></span>

<span data-ttu-id="7dcc3-152">이 설정을 사용 하면 PSTN 호출자가 보류 상태일 때 보류 중인 음악을 켜거나 끌 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7dcc3-152">This setting allows you to turn on or turn off music on hold when a PSTN caller is placed on hold.</span></span> <span data-ttu-id="7dcc3-153">기본적으로 설정 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7dcc3-153">It's turned on by default.</span></span> <span data-ttu-id="7dcc3-154">이 설정은 통화 공원 및 상사 대리인 기능에는 적용 되지 않으며 현재 PowerShell을 통해서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7dcc3-154">This setting doesn't apply to call park and boss delegate features, and is currently only available via PowerShell.</span></span>

## <a name="related-topics"></a><span data-ttu-id="7dcc3-155">관련 주제</span><span class="sxs-lookup"><span data-stu-id="7dcc3-155">Related topics</span></span>

[<span data-ttu-id="7dcc3-156">Set-CSTeamsCallingPolicy</span><span class="sxs-lookup"><span data-stu-id="7dcc3-156">Set-CSTeamsCallingPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps)

[<span data-ttu-id="7dcc3-157">팀에서 사용자에 게 정책 할당</span><span class="sxs-lookup"><span data-stu-id="7dcc3-157">Assign policies to your users in Teams</span></span>](assign-policies.md)
