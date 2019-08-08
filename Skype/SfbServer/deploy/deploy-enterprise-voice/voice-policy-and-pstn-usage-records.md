---
title: 비즈니스용 Skype에서 음성 정책 만들기 또는 수정 및 PSTN 사용 레코드 구성
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: e6ff27e0-e2d1-4445-840f-08f738200c20
description: '요약: 비즈니스용 Skype 서버 제어판을 사용 하 여 음성 정책을 만들거나 수정 하 고 PSTN 사용 레코드를 구성 합니다.'
ms.openlocfilehash: 76ce531eab2eb88b9a62c4bc38aae1e899802084
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36240207"
---
# <a name="create-or-modify-a-voice-policy-and-configure-pstn-usage-records-in-skype-for-business"></a><span data-ttu-id="09e18-103">비즈니스용 Skype에서 음성 정책 만들기 또는 수정 및 PSTN 사용 레코드 구성</span><span class="sxs-lookup"><span data-stu-id="09e18-103">Create or modify a voice policy and configure PSTN usage records in Skype for Business</span></span>

<span data-ttu-id="09e18-104">**요약:** 비즈니스용 Skype 서버 제어판을 사용 하 여 음성 정책을 만들거나 수정 하 고 PSTN 사용 레코드를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-104">**Summary:** Create or modify voice policies and configure PSTN usage records by using the Skype for Business Server Control Panel.</span></span>

> [!NOTE]
> <span data-ttu-id="09e18-105">각 음성 정책에는 하나 이상의 연결 된 PSTN (공개 통신 네트워크) 사용 레코드가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-105">Each voice policy must have at least one associated Public Switched Telephone Network (PSTN) usage record.</span></span> <span data-ttu-id="09e18-106">엔터프라이즈 음성 배포에서 사용할 수 있는 모든 PSTN 사용 레코드 목록을 보고 해당 속성을 볼 수 있도록 [비즈니스용 Skype에서 pstn 사용 레코드 보기](view-pstn-usage-records.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="09e18-106">To see a listing of all PSTN usage records available in your Enterprise Voice deployment and view their properties, see [View PSTN usage records in Skype for Business](view-pstn-usage-records.md).</span></span>

### <a name="to-create-a-voice-policy"></a><span data-ttu-id="09e18-107">음성 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="09e18-107">To create a voice policy</span></span>

1. <span data-ttu-id="09e18-108">비즈니스용 Skype Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-108">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="09e18-109">왼쪽 탐색 모음에서 **음성 라우팅을** 클릭 한 다음 **음성 정책을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-109">In the left navigation bar, click **Voice Routing** and then click **Voice Policy**.</span></span>

3. <span data-ttu-id="09e18-110">**음성 정책** 페이지에서 **새로 만들기** 를 클릭 한 다음 새 정책에 대 한 범위를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-110">On the **Voice Policy** page, click **New** and then select a scope for the new policy:</span></span>

   - <span data-ttu-id="09e18-111">**사이트 정책은** 사용자 정책에 할당 된 사용자 또는 그룹을 제외한 전체 사이트에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-111">**Site policy** applies to an entire site, except any users or groups that are assigned to a user policy.</span></span> <span data-ttu-id="09e18-112">정책 범위에 대 한 사이트를 선택 하는 경우 **사이트 선택** 대화 상자에서 사이트를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-112">If you select Site for a policy scope, choose the site from the **Select a Site** dialog box.</span></span> <span data-ttu-id="09e18-113">사이트에 대 한 음성 정책이 이미 만들어졌으면 사이트 **선택** 대화 상자에 해당 사이트가 나타나지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-113">If a voice policy has already been created for a site, the site does not appear in the **Select a Site** dialog box.</span></span>

   - <span data-ttu-id="09e18-114">지정 된 사용자 또는 그룹에 **사용자 정책을** 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-114">**User policy** can be applied to specified users or groups.</span></span>

4. <span data-ttu-id="09e18-115">음성 정책 범위가 사용자 인 경우 **이름** 필드에 정책에 대 한 설명적인 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-115">If the voice policy scope is User, enter a descriptive name for the policy in the **Name** field.</span></span>

    > [!NOTE]
    > <span data-ttu-id="09e18-116">음성 정책 범위가 사이트인 경우 **새 음성 정책의** **이름** 필드는 사이트 이름으로 미리 채워 있으므로 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-116">If the voice policy scope is Site, the **Name** field in **New Voice Policy** is prepopulated with the site name and cannot be changed.</span></span>

5. <span data-ttu-id="09e18-117">) 음성 정책에 대 한 추가 설명 정보를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-117">(Optional) Enter additional descriptive information for the voice policy.</span></span>

6. <span data-ttu-id="09e18-118">이 음성 정책에 대 한 각 **호출 기능** 을 사용 하거나 사용 하지 않도록 다음 확인란을 선택 하거나 선택을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-118">Select or clear the following check boxes to enable or disable each of the **Calling features** for this voice policy:</span></span>

   - <span data-ttu-id="09e18-119">**음성 메일 esc** 키를 누르면 동시 벨 울림이 구성 되 고, 전화가 꺼졌거나, 배터리 부족 상태 이거나, 범위를 벗어날 때 사용자의 휴대폰 음성 메일 시스템으로 즉시 착신 라우팅되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-119">**Voice mail escape** prevents calls from being immediately routed to the user's mobile phone voice mail system when simultaneous ringing is configured and the phone is turned off, out of battery, or out of range.</span></span>

     > [!NOTE]
     > <span data-ttu-id="09e18-120">이 기능은 비즈니스용 Skype 서버 관리 셸을 통해서만 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-120">This feature is only configurable through the Skype for Business Server Management Shell</span></span>

   - <span data-ttu-id="09e18-121">**착신 통화 전환** 기능을 통해 사용자는 다른 전화 및 클라이언트 장치로 전화를 착신 전환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-121">**Call forwarding** enables users to forward calls to other phones and client devices.</span></span> <span data-ttu-id="09e18-122">비즈니스용 Skype Server는 착신 전환에 대 한 다양 한 구성 옵션을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-122">Skype for Business Server provides a significantly wider range of configuration options for call forwarding.</span></span> <span data-ttu-id="09e18-123">예를 들어 조직에서 들어오는 통화가 PSTN에 외부적으로 착신 전환 되는 것을 허용 하지 않을 경우 관리자는 특수 음성 정책을 적용 하 여이 제한을 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-123">For example, if an organization does not want to allow incoming calls to be forwarded externally to the PSTN, an administrator can apply a special voice policy to deploy this restriction.</span></span> <span data-ttu-id="09e18-124">기본적으로 사용 하도록 설정 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-124">Enabled by default.</span></span>

   - <span data-ttu-id="09e18-125">**위임을** 통해 사용자는 다른 사용자가 대신 전화를 보내고 받을 수 있도록 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-125">**Delegation** enables users to specify other users to send and receive calls on their behalf.</span></span> <span data-ttu-id="09e18-126">비즈니스용 Skype 서버에서 대리인은 자신의 관리자에 게 들어오는 호출을 사용 하 여 모든 대리인의 동시 연결 대상을 연결 하는 동시 연결을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-126">In Skype for Business Server, a delegate can configure simultaneous ringing that enables incoming calls to his or her manager to ring all of the delegate's simultaneous ringing targets.</span></span> <span data-ttu-id="09e18-127">이렇게 하면 대리인에 게 관리자를 대상으로 하는 통화에 대 한 응답을 보다 유연 하 게 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-127">This provides the delegate with greater flexibility in responding to calls directed to the manager.</span></span> <span data-ttu-id="09e18-128">기본적으로 사용 하도록 설정 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-128">Enabled by default.</span></span>

   - <span data-ttu-id="09e18-129">**통화 전송을** 통해 사용자는 통화를 다른 사용자에 게 전송할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-129">**Call transfer** enables users to transfer calls to other users.</span></span> <span data-ttu-id="09e18-130">기본적으로 사용 하도록 설정 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-130">Enabled by default.</span></span>

   - <span data-ttu-id="09e18-131">**통화** 대기를 통해 사용자는 통화를 보류 했다가 다른 휴대폰 또는 클라이언트에서 전화를 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-131">**Call park** enables users to park calls on hold and then pick up the call from a different phone or client.</span></span> <span data-ttu-id="09e18-132">기본적으로 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-132">Disabled by default.</span></span>

   - <span data-ttu-id="09e18-133">**동시** 연결을 통해 추가 전화기 (예: 휴대 전화) 또는 기타 끝점 장치에서 수신 전화를 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-133">**Simultaneous ringing** enables incoming calls to ring on additional phones (for example, a mobile phone) or other endpoint devices.</span></span> <span data-ttu-id="09e18-134">비즈니스용 Skype Server는 동시 울림을 위한 광범위 한 구성 옵션을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-134">Skype for Business Server provides a significantly wider range of configuration options for simultaneous ringing.</span></span> <span data-ttu-id="09e18-135">기본적으로 사용 하도록 설정 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-135">Enabled by default.</span></span>

   - <span data-ttu-id="09e18-136">**팀 통화** 는 정의 된 팀의 사용자가 팀의 다른 구성원에 대 한 통화에 대답할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-136">**Team call** enables users on a defined team to answer calls for other members of the team.</span></span> <span data-ttu-id="09e18-137">기본적으로 사용 하도록 설정 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-137">Enabled by default.</span></span>

   - <span data-ttu-id="09e18-138">**Pstn re** 는 WAN이 혼잡 하거나 사용할 수 없는 경우 다른 enterprise 사용자에 게이 정책을 할당 하는 사용자가 PSTN에서 경로를 조정 하도록 하는 데의 한 통화를 가능 하 게 합니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-138">**PSTN re-route** enables calls made by users who are assigned this policy to other enterprise users to be rerouted on the PSTN if the WAN is congested or unavailable.</span></span> <span data-ttu-id="09e18-139">기본적으로 사용 하도록 설정 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-139">Enabled by default.</span></span>

   - <span data-ttu-id="09e18-140">**대역폭 정책 재정의** 를 통해 관리자는 특정 사용자에 대 한 통화 허용 제어 정책 결정을 무시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-140">**Bandwidth policy override** enables administrators to override call admission control policy decisions for a particular user.</span></span> <span data-ttu-id="09e18-141">기본적으로 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-141">Disabled by default.</span></span>

     > [!NOTE]
     > <span data-ttu-id="09e18-142">정책은 사용자에 게 들어오는 통화에 대해서만 무시 되 고 사용자가 설정한 발신 통화에는 적용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-142">The policy will be overridden only for incoming calls to the user and not for outgoing calls that are placed by the user.</span></span> <span data-ttu-id="09e18-143">세션을 설정한 후에는 대역폭 소비가 정확 하 게 기록 됩니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-143">After the session is established, the bandwidth consumption will be accurately recorded.</span></span> <span data-ttu-id="09e18-144">이 설정은 가끔씩만 사용 해야 하며 적절 한 통화 허용 제어 결정을 위해 예약 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-144">This setting should be used sparingly and should be reserved for appropriate call admission control decisions.</span></span>

   - <span data-ttu-id="09e18-145">**악의적인 통화 추적** 기능을 통해 사용자는 클라이언트 UI를 사용 하 여 악의적인 통화 (예: 위협)를 보고 하 고, 이렇게 하면 Cdrs (호출 정보 레코드)에 호출에 플래그를 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-145">**Malicious call tracing** enables users to report malicious calls (such as threats) by using the client UI, which in turn flags the calls in the Call Detail Records (CDRs).</span></span> <span data-ttu-id="09e18-146">기본적으로 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-146">Disabled by default.</span></span>

   - <span data-ttu-id="09e18-147">**약속 있음 옵션** 지정 된 음성 정책에 대 한 사용 중 옵션을 설정 하거나 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-147">**Busy options** enables or disables Busy Options for the specified voice policy.</span></span> <span data-ttu-id="09e18-148">통화 중 옵션을 사용 하면 전화의 대상 사용자가 휴대폰에 있을 때 수신 전화를 음성 메일로 라우팅하거나 거부 하는 신호를 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-148">Busy Options allows incoming calls to be routed to voice mail or rejected with a busy signal when the call's target user is on the phone.</span></span> <span data-ttu-id="09e18-149">약속 있음 옵션은 7 월 2016 누적 업데이트에 도입 된 새로운 음성 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-149">Busy Options is a new voice policy introduced in the July 2016 Cumulative Update.</span></span> <span data-ttu-id="09e18-150">이 매개 변수를 선택 하면 약속 있음/없음 옵션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-150">Checking this parameter enables Busy Options, and unchecking it disables Busy Options.</span></span> <span data-ttu-id="09e18-151">자세한 내용은 비즈니스용 [Skype 서버의 약속 있음 옵션 계획](../../plan-your-deployment/enterprise-voice-solution/busy-options.md) 및 비즈니스용 [Skype 서버용 다른 용무 중 옵션 설치 및 구성을](install-and-configure-busy-options.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="09e18-151">For more information, see [Plan for Busy Options for Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/busy-options.md) and [Install and configure Busy Options for Skype for Business Server](install-and-configure-busy-options.md).</span></span>

7. <span data-ttu-id="09e18-152">이 음성 정책에 대 한 PSTN 사용 레코드를 연결 하 고 구성 하려면 다음 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-152">To associate and configure PSTN usage records for this voice policy, do any of the following:</span></span>

   - <span data-ttu-id="09e18-153">엔터프라이즈 음성 배포에서 사용할 수 있는 모든 PSTN 사용 레코드 목록에서 하나 이상의 레코드를 선택 하려면 **선택을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-153">To choose one or more records from a list of all PSTN usage records available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="09e18-154">이 음성 정책에 연결 하려는 레코드를 강조 표시 한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-154">Highlight the records that you want to associate with this voice policy, and then click **OK**.</span></span>

   - <span data-ttu-id="09e18-155">이 음성 정책에서 PSTN 사용 레코드를 제거 하려면 해당 레코드를 강조 표시 하 고 **제거**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-155">To remove a PSTN usage record from this voice policy, highlight the record and click **Remove**.</span></span>

   - <span data-ttu-id="09e18-156">새 PSTN 사용 레코드를 정의 하 고이를이 음성 정책에 연결 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-156">To define a new PSTN usage record and associate it with this voice policy, do the following:</span></span>

     <span data-ttu-id="09e18-157">에서.</span><span class="sxs-lookup"><span data-stu-id="09e18-157">a.</span></span> <span data-ttu-id="09e18-158">**새로 만들기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-158">Click **New**.</span></span>

     <span data-ttu-id="09e18-159">b.</span><span class="sxs-lookup"><span data-stu-id="09e18-159">b.</span></span> <span data-ttu-id="09e18-160">**이름** 필드에 레코드에 대 한 고유한 설명적인 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-160">In the **Name** field, enter a unique descriptive name for the record.</span></span> <span data-ttu-id="09e18-161">예를 들어, 레드먼드에 거주 하는 정규 직원을 위해 PSTN 사용 레코드 namedRedmond를 만들고 임시 직원에 게 다른 namedRedmondTemps를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-161">For example, you may want to create a PSTN usage record namedRedmond for full-time employees located in Redmond, and another namedRedmondTemps for temporary employees.</span></span>

     > [!NOTE]
     > <span data-ttu-id="09e18-162">PSTN 사용 레코드 이름은 엔터프라이즈 음성 배포 내에서 고유 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-162">The PSTN usage record name must be unique within the Enterprise Voice deployment.</span></span> <span data-ttu-id="09e18-163">레코드가 저장 된 후에는 **이름** 필드를 편집할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-163">After the record is saved, the **Name** field cannot be edited.</span></span>

     <span data-ttu-id="09e18-164">c.</span><span class="sxs-lookup"><span data-stu-id="09e18-164">c.</span></span> <span data-ttu-id="09e18-165">다음 방법 중 하나를 사용 하 여이 PSTN 사용 레코드에 대 한 경로를 연결 하 고 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-165">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>

   - <span data-ttu-id="09e18-166">엔터프라이즈 음성 배포의 모든 사용 가능한 경로 목록에서 하나 이상의 경로를 선택 하려면 **선택을**클릭 하 고이 PSTN 사용 레코드와 연결할 경로를 강조 표시 한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-166">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes that you want to associate with this PSTN usage record, and then click **OK**.</span></span>

   - <span data-ttu-id="09e18-167">PSTN 사용 레코드에서 경로를 제거 하려면 해당 경로를 강조 표시 한 다음 **제거**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-167">To remove a route from the PSTN usage record, highlight the route, and then click **Remove**.</span></span>

   - <span data-ttu-id="09e18-168">새 경로를 정의 하 고이 PSTN 사용 레코드와 연결 하려면 **새로 만들기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-168">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="09e18-169">자세한 내용은 [비즈니스용 Skype에서 음성 경로 만들기 또는 수정을](create-or-modify-a-voice-route.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="09e18-169">For details, see [Create or modify a voice route in Skype for Business](create-or-modify-a-voice-route.md).</span></span>

   - <span data-ttu-id="09e18-170">이 PSTN 사용 레코드와 이미 연결 된 경로를 편집 하려면 해당 경로를 강조 표시 하 고 **세부 정보 표시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-170">To edit a route that is already associated with this PSTN usage record, highlight the route and click **Show details**.</span></span>

     <span data-ttu-id="09e18-171">a.</span><span class="sxs-lookup"><span data-stu-id="09e18-171">d.</span></span> <span data-ttu-id="09e18-172">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-172">Click **OK**.</span></span>

   - <span data-ttu-id="09e18-173">이 음성 정책에 이미 연결 된 PSTN 사용 레코드를 편집 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-173">To edit a PSTN usage record that is already associated with this voice policy, do the following:</span></span>

     <span data-ttu-id="09e18-174">에서.</span><span class="sxs-lookup"><span data-stu-id="09e18-174">a.</span></span> <span data-ttu-id="09e18-175">편집 하려는 PSTN 사용 레코드를 강조 표시 한 다음 **세부 정보 표시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-175">Highlight the PSTN usage record that you want to edit, and then click **Show details**.</span></span>

     <span data-ttu-id="09e18-176">b.</span><span class="sxs-lookup"><span data-stu-id="09e18-176">b.</span></span> <span data-ttu-id="09e18-177">다음 방법 중 하나를 사용 하 여이 PSTN 사용 레코드에 대 한 경로를 연결 하 고 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-177">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>

   - <span data-ttu-id="09e18-178">엔터프라이즈 음성 배포의 모든 사용 가능한 경로 목록에서 하나 이상의 경로를 선택 하려면 **선택을**클릭 하 고이 PSTN 사용 레코드와 연결할 경로를 강조 표시 한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-178">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes you want to associate with this PSTN usage record, and then click **OK**.</span></span>

   - <span data-ttu-id="09e18-179">이 PSTN 사용 레코드에서 경로를 제거 하려면 해당 경로를 강조 표시 한 다음 **제거**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-179">To remove a route from this PSTN usage record, highlight the route, and then click **Remove**.</span></span>

   - <span data-ttu-id="09e18-180">새 경로를 정의 하 고이 PSTN 사용 레코드와 연결 하려면 **새로 만들기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-180">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="09e18-181">자세한 내용은 [비즈니스용 Skype에서 음성 경로 만들기 또는 수정을](create-or-modify-a-voice-route.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="09e18-181">For details, see [Create or modify a voice route in Skype for Business](create-or-modify-a-voice-route.md).</span></span>

   - <span data-ttu-id="09e18-182">이 PSTN 사용 레코드와 이미 연결 된 경로를 편집 하려면 경로를 강조 표시 하 고 **세부 정보**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-182">To edit a route that is already associated with this PSTN usage record, highlight the route and lick **Show details**.</span></span>

     <span data-ttu-id="09e18-183">c.</span><span class="sxs-lookup"><span data-stu-id="09e18-183">c.</span></span> <span data-ttu-id="09e18-184">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-184">Click **OK**.</span></span>

8. <span data-ttu-id="09e18-185">최적의 성능을 위해 PSTN 사용 레코드를 정렬 합니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-185">Arrange the PSTN usage records for optimum performance.</span></span> <span data-ttu-id="09e18-186">목록에서 레코드의 위치를 변경 하려면 레코드 이름을 강조 표시 하 고 위쪽 또는 아래쪽 화살표를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-186">To change a record's position in the list, highlight the record name and click the up or down arrow.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="09e18-187">PSTN 사용 레코드가 음성 정책에 나열 되는 순서는 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-187">The order in which PSTN usage records are listed in the voice policy is significant.</span></span> <span data-ttu-id="09e18-188">비즈니스용 Skype 서버는 목록을 위에서 아래로 트래버스 합니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-188">Skype for Business Server traverses the list from the top down.</span></span> <span data-ttu-id="09e18-189">RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup 등의 사용 빈도 별로 목록을 구성 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-189">We recommend that you organize the list by frequency of use, for example: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup.</span></span>

9. <span data-ttu-id="09e18-190">이 음성 정책에서 통화 전환 및 동시 연결에 대 한 PSTN 사용 레코드를 연결 하 고 구성 하려면 다음 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-190">To associate and configure PSTN usage records for call forwarding and simultaneous ringing in this voice policy, do any of the following:</span></span>

   - <span data-ttu-id="09e18-191">착신 전환 및 동시 연결에 같은 PSTN 사용 레코드를이 음성 정책으로 사용 하려면 드롭다운 메뉴에서 **통화 PSTN 사용을 사용해 경로** 옵션을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-191">To use the same PSTN usage records for call forwarding and simultaneous ringing as this voice policy, select the option **Route using the call PSTN usages** from the drop-down menu.</span></span>

   - <span data-ttu-id="09e18-192">착신 전환 및 비즈니스용 Skype 사용자에 대해서만 동시 연결을 허용 하려면 드롭다운 메뉴에서 비즈니스용 **skype 사용자에 대 한 경로만 하** 는 옵션을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-192">To allow call forwarding and simultaneous ringing to internal Skype for Business users only, select the option **Route to internal Skype for Business users only** from the drop-down menu.</span></span> <span data-ttu-id="09e18-193">통화는 외부 PSTN 번호로 착신 전환 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-193">Calls will not be forwarded to external PSTN numbers.</span></span>

   - <span data-ttu-id="09e18-194">이 음성 정책에 사용 되는 것 보다 착신 전환 및 동시 연결에 대해 다른 PSTN 사용 레코드를 지정 하려면 드롭다운 메뉴에서 **사용자 지정 PSTN 용도를 사용 하 여 경로** 옵션을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-194">To specify different PSTN usage records for call forwarding and simultaneous ringing than used for this voice policy, select the option **Route using custom PSTN usages** from the drop-down menu.</span></span> <span data-ttu-id="09e18-195">이 옵션은 기존 PSTN 사용 레코드를 선택 하거나, 착신 전환 및 동시 연결을 위해 특별히 새 PSTN 사용 레코드를 만드는 컨트롤을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-195">This option displays a control to select existing PSTN usage records or create new PSTN usage records specifically for call forwarding and simultaneous ringing.</span></span>

   - <span data-ttu-id="09e18-196">통화 전환 및 동시 연결에 대 한 PSTN 사용 레코드 목록에서 하나 이상의 레코드를 선택 하려면 **선택을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-196">To choose one or more records from a list of PSTN usage records for call forwarding and simultaneous ringing, click **Select**.</span></span> <span data-ttu-id="09e18-197">이 착신 전환 및 동시 연결 정책과 연결할 레코드를 강조 표시 한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-197">Highlight the records that you want to associate with this call forwarding and simultaneous ringing policy, and then click **OK**.</span></span>

   - <span data-ttu-id="09e18-198">이 착신 전환 및 동시 연결 정책에서 PSTN 사용 레코드를 제거 하려면 해당 레코드를 강조 표시 하 고 **제거**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-198">To remove a PSTN usage record from this call forwarding and simultaneous ringing policy, highlight the record and click **Remove**.</span></span>

   - <span data-ttu-id="09e18-199">새 PSTN 사용 레코드를 정의 하 고이를 착신 전환 및 동시 연결 정책과 연관 시키려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-199">To define a new PSTN usage record and associate it with this call forwarding and simultaneous ringing policy, do the following:</span></span>

     <span data-ttu-id="09e18-200">에서.</span><span class="sxs-lookup"><span data-stu-id="09e18-200">a.</span></span> <span data-ttu-id="09e18-201">**새로 만들기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-201">Click **New**.</span></span>

     <span data-ttu-id="09e18-202">b.</span><span class="sxs-lookup"><span data-stu-id="09e18-202">b.</span></span> <span data-ttu-id="09e18-203">**이름** 필드에 레코드에 대 한 고유한 설명적인 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-203">In the **Name** field, enter a unique descriptive name for the record.</span></span>

     > [!NOTE]
     > <span data-ttu-id="09e18-204">PSTN 사용 레코드 이름은 엔터프라이즈 음성 배포 내에서 고유 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-204">The PSTN usage record name must be unique within the Enterprise Voice deployment.</span></span> <span data-ttu-id="09e18-205">레코드가 저장 된 후에는 **이름** 필드를 편집할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-205">After the record is saved, the **Name** field cannot be edited.</span></span>

     <span data-ttu-id="09e18-206">c.</span><span class="sxs-lookup"><span data-stu-id="09e18-206">c.</span></span> <span data-ttu-id="09e18-207">다음 방법 중 하나를 사용 하 여이 PSTN 사용 레코드에 대 한 경로를 연결 하 고 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-207">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>

   - <span data-ttu-id="09e18-208">엔터프라이즈 음성 배포의 모든 사용 가능한 경로 목록에서 하나 이상의 경로를 선택 하려면 **선택을**클릭 하 고이 PSTN 사용 레코드와 연결할 경로를 강조 표시 한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-208">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes that you want to associate with this PSTN usage record, and then click **OK**.</span></span>

   - <span data-ttu-id="09e18-209">PSTN 사용 레코드에서 경로를 제거 하려면 경로를 강조 표시 하 고 **제거**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-209">To remove a route from the PSTN usage record, highlight the route and click **Remove**.</span></span>

   - <span data-ttu-id="09e18-210">새 경로를 정의 하 고이 PSTN 사용 레코드와 연결 하려면 **새로 만들기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-210">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="09e18-211">자세한 내용은 [비즈니스용 Skype에서 음성 경로 만들기 또는 수정을](create-or-modify-a-voice-route.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="09e18-211">For details, see [Create or modify a voice route in Skype for Business](create-or-modify-a-voice-route.md).</span></span>

   - <span data-ttu-id="09e18-212">이 PSTN 사용 레코드와 이미 연결 된 경로를 편집 하려면 해당 경로를 강조 표시 하 고 **세부 정보 표시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-212">To edit a route that is already associated with this PSTN usage record, highlight the route and click **Show details**.</span></span>

     <span data-ttu-id="09e18-213">a.</span><span class="sxs-lookup"><span data-stu-id="09e18-213">d.</span></span> <span data-ttu-id="09e18-214">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-214">Click **OK**.</span></span>

   - <span data-ttu-id="09e18-215">이 음성 정책에 이미 연결 된 PSTN 사용 레코드를 편집 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-215">To edit a PSTN usage record that is already associated with this voice policy, do the following:</span></span>

     <span data-ttu-id="09e18-216">에서.</span><span class="sxs-lookup"><span data-stu-id="09e18-216">a.</span></span> <span data-ttu-id="09e18-217">편집 하려는 PSTN 사용 레코드를 강조 표시 하 고 **세부 정보 표시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-217">Highlight the PSTN usage record you want to edit and click **Show details**.</span></span>

     <span data-ttu-id="09e18-218">b.</span><span class="sxs-lookup"><span data-stu-id="09e18-218">b.</span></span> <span data-ttu-id="09e18-219">다음 방법 중 하나를 사용 하 여이 PSTN 사용 레코드에 대 한 경로를 연결 하 고 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-219">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>

   - <span data-ttu-id="09e18-220">엔터프라이즈 음성 배포의 모든 사용 가능한 경로 목록에서 하나 이상의 경로를 선택 하려면 **선택을**클릭 하 고이 PSTN 사용 레코드와 연결할 경로를 강조 표시 한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-220">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes that you want to associate with this PSTN usage record, and then click **OK**.</span></span>

   - <span data-ttu-id="09e18-221">이 PSTN 사용 레코드에서 경로를 제거 하려면 경로를 강조 표시 하 고 **제거**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-221">To remove a route from this PSTN usage record, highlight the route and click **Remove**.</span></span>

   - <span data-ttu-id="09e18-222">새 경로를 정의 하 고이 PSTN 사용 레코드와 연결 하려면 **새로 만들기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-222">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="09e18-223">자세한 내용은 [비즈니스용 Skype에서 음성 경로 만들기 또는 수정을](create-or-modify-a-voice-route.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="09e18-223">For details, see [Create or modify a voice route in Skype for Business](create-or-modify-a-voice-route.md).</span></span>

   - <span data-ttu-id="09e18-224">이 PSTN 사용 레코드와 이미 연결 된 경로를 편집 하려면 해당 경로를 강조 표시 하 고 **세부 정보 표시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-224">To edit a route that is already associated with this PSTN usage record, highlight the route and click **Show details**.</span></span>

     <span data-ttu-id="09e18-225">c.</span><span class="sxs-lookup"><span data-stu-id="09e18-225">c.</span></span> <span data-ttu-id="09e18-226">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-226">Click **OK**.</span></span>

10. <span data-ttu-id="09e18-227">) 번호를 입력 하 여 음성 정책을 테스트 하 고 **이동을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-227">(Optional) Enter a number to test the voice policy and click **Go**.</span></span> <span data-ttu-id="09e18-228">테스트 결과가 **테스트를 위해 번역 된 번호**아래에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-228">The test results are displayed under **Translated number to test**.</span></span>

11. <span data-ttu-id="09e18-229">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-229">Click **OK**.</span></span>

12. <span data-ttu-id="09e18-230">**음성 정책** 페이지에서 **커밋을**클릭 한 다음 **모두 커밋을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-230">On the **Voice Policy** page, click **Commit**, and then click **Commit all**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="09e18-231">음성 정책을 만들거나 수정할 때마다 **모두 커밋** 명령을 실행 하 여 구성 변경 내용을 게시 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-231">Any time you create or modify a voice policy, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="09e18-232">자세한 내용은 운영 설명서의 비즈니스용 [Skype에서 음성 라우팅 구성에 보류 중인 변경 내용 게시](voice-route-config-changes.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="09e18-232">For details, see [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation.</span></span>

13. <span data-ttu-id="09e18-233">) 보이스 메일 감지는 전화가 사용자의 휴대폰 음성 메일로 바로 응답 하 고 휴대폰 음성 메일로 전화를 끊습니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-233">(Optional) Voicemail Escape detects that a call was immediately answered by the user's mobile phone voice mail, and disconnects the call to the mobile phone voice mail.</span></span> <span data-ttu-id="09e18-234">이렇게 하면 사용자가 전화를 받을 수 있도록 사용자가 다른 끝점을 계속 해 서 전화를 걸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-234">This allows the call to continue to ring on the user's other endpoints giving the user the opportunity to answer the call.</span></span> <span data-ttu-id="09e18-235">음성 메일 정책을 구성 하는 방법에 대 한 자세한 내용은 [비즈니스용 Skype에서 음성 메일 Esc 구성을](configure-voice-mail-escape.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="09e18-235">For details on how to configure a voice mail policy, see [Configure voice mail escape in Skype for Business](configure-voice-mail-escape.md).</span></span>

### <a name="to-modify-a-voice-policy"></a><span data-ttu-id="09e18-236">음성 정책 수정</span><span class="sxs-lookup"><span data-stu-id="09e18-236">To modify a voice policy</span></span>

1. <span data-ttu-id="09e18-237">비즈니스용 Skype Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-237">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="09e18-238">왼쪽 탐색 모음에서 **음성 라우팅을**클릭 한 다음 **음성 정책을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-238">In the left navigation bar, click **Voice Routing**, and then click **Voice Policy**.</span></span>

3. <span data-ttu-id="09e18-239">**음성 정책** 페이지에서 음성 정책 이름을 두 번 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-239">On the **Voice Policy** page, double-click a voice policy name.</span></span>

    > [!NOTE]
    > <span data-ttu-id="09e18-240">음성 정책을 만들 때 범위와 이름이 설정 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-240">The scope and name were set when the voice policy was created.</span></span> <span data-ttu-id="09e18-241">변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-241">They cannot be changed.</span></span>

4. <span data-ttu-id="09e18-242">) **음성 정책 편집**에서 음성 정책에 대 한 추가 설명 정보를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-242">(Optional) In **Edit Voice Policy**, enter additional descriptive information for the voice policy.</span></span>

5. <span data-ttu-id="09e18-243">각 **통화 기능**을 사용 하거나 사용 하지 않도록 설정 하려면 다음 확인란을 선택 하거나 선택을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-243">Select or clear the following check boxes to enable or disable each of the **Calling features**:</span></span>

   - <span data-ttu-id="09e18-244">**음성 메일 esc** 키를 누르면 동시 벨 울림이 구성 되 고, 전화가 꺼졌거나, 배터리 부족 상태 이거나, 범위를 벗어날 때 사용자의 휴대폰 음성 메일 시스템으로 즉시 착신 라우팅되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-244">**Voice mail escape** prevents calls from being immediately routed to the user's mobile phone voice mail system when simultaneous ringing is configured and the phone is turned off, out of battery, or out of range.</span></span>

     > [!NOTE]
     > <span data-ttu-id="09e18-245">이 기능은 비즈니스용 Skype 서버 관리 셸을 통해서만 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-245">This feature is only configurable through the Skype for Business Server Management Shell</span></span>

   - <span data-ttu-id="09e18-246">**착신 통화 전환** 기능을 통해 사용자는 다른 전화 및 클라이언트 장치로 전화를 착신 전환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-246">**Call forwarding** enables users to forward calls to other phones and client devices.</span></span> <span data-ttu-id="09e18-247">비즈니스용 Skype Server는 착신 전환에 대 한 다양 한 구성 옵션을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-247">Skype for Business Server provides a significantly wider range of configuration options for call forwarding.</span></span> <span data-ttu-id="09e18-248">예를 들어 조직에서 들어오는 통화가 PSTN에 외부적으로 착신 전환 되는 것을 허용 하지 않을 경우 관리자는 특수 음성 정책을 적용 하 여이 제한을 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-248">For example, if an organization does not want to allow incoming calls to be forwarded externally to the PSTN, an administrator can apply a special voice policy to deploy this restriction.</span></span> <span data-ttu-id="09e18-249">기본적으로 사용 하도록 설정 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-249">Enabled by default.</span></span>

   - <span data-ttu-id="09e18-250">**위임을** 통해 사용자는 다른 사용자가 대신 전화를 보내고 받을 수 있도록 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-250">**Delegation** enables users to specify other users to send and receive calls on their behalf.</span></span> <span data-ttu-id="09e18-251">비즈니스용 Skype 서버에서 대리인은 자신의 관리자에 게 들어오는 호출을 사용 하 여 모든 대리인의 동시 연결 대상을 연결 하는 동시 연결을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-251">In Skype for Business Server, a delegate can configure simultaneous ringing that enables incoming calls to his or her manager to ring all of the delegate's simultaneous ringing targets.</span></span> <span data-ttu-id="09e18-252">이렇게 하면 대리인에 게 관리자를 대상으로 하는 통화에 대 한 응답을 보다 유연 하 게 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-252">This provides the delegate with greater flexibility in responding to calls directed to the manager.</span></span> <span data-ttu-id="09e18-253">기본적으로 사용 하도록 설정 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-253">Enabled by default.</span></span>

   - <span data-ttu-id="09e18-254">**통화 전송을** 통해 사용자는 통화를 다른 사용자에 게 전송할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-254">**Call transfer** enables users to transfer calls to other users.</span></span> <span data-ttu-id="09e18-255">기본적으로 사용 하도록 설정 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-255">Enabled by default.</span></span>

   - <span data-ttu-id="09e18-256">**통화** 대기 전화를 통해 사용자는 통화를 보류 했다가 다른 휴대폰 또는 클라이언트에서 전화를 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-256">**Call park** enables users to park calls on hold, and then pick up the call from a different phone or client.</span></span> <span data-ttu-id="09e18-257">기본적으로 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-257">Disabled by default.</span></span>

   - <span data-ttu-id="09e18-258">**동시** 연결을 통해 추가 전화기 (예: 휴대 전화) 또는 기타 끝점 장치에서 수신 전화를 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-258">**Simultaneous ringing** enables incoming calls to ring on additional phones (for example, a mobile phone) or other endpoint devices.</span></span> <span data-ttu-id="09e18-259">비즈니스용 Skype Server는 동시 울림을 위한 광범위 한 구성 옵션을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-259">Skype for Business Server provides a significantly wider range of configuration options for simultaneous ringing.</span></span> <span data-ttu-id="09e18-260">기본적으로 사용 하도록 설정 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-260">Enabled by default.</span></span>

   - <span data-ttu-id="09e18-261">**팀 통화** 는 정의 된 팀의 사용자가 팀의 다른 구성원에 대 한 통화에 대답할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-261">**Team call** enables users on a defined team to answer calls for other members of the team.</span></span> <span data-ttu-id="09e18-262">기본적으로 사용 하도록 설정 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-262">Enabled by default.</span></span>

   - <span data-ttu-id="09e18-263">**Pstn re** 는 WAN이 혼잡 하거나 사용할 수 없는 경우 다른 enterprise 사용자에 게이 정책을 할당 하는 사용자가 PSTN에서 경로를 조정 하도록 하는 데의 한 통화를 가능 하 게 합니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-263">**PSTN re-route** enables calls made by users who are assigned this policy to other enterprise users to be rerouted on the PSTN if the WAN is congested or unavailable.</span></span> <span data-ttu-id="09e18-264">기본적으로 사용 하도록 설정 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-264">Enabled by default.</span></span>

   - <span data-ttu-id="09e18-265">**대역폭 정책 재정의** 를 통해 관리자는 특정 사용자에 대 한 CAC 정책 결정을 무시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-265">**Bandwidth policy override** enables administrators to override CAC policy decisions for a particular user.</span></span> <span data-ttu-id="09e18-266">기본적으로 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-266">Disabled by default.</span></span>

     > [!NOTE]
     > <span data-ttu-id="09e18-267">정책은 사용자에 게 들어오는 통화에 대해서만 무시 되 고 사용자가 설정한 발신 통화에는 적용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-267">The policy will be overridden only for incoming calls to the user and not for outgoing calls that are placed by the user.</span></span> <span data-ttu-id="09e18-268">세션을 설정한 후에는 대역폭 소비가 정확 하 게 기록 됩니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-268">After the session is established, the bandwidth consumption will be accurately recorded.</span></span> <span data-ttu-id="09e18-269">이 설정은 가끔씩만 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-269">This setting should be used sparingly.</span></span>

   - <span data-ttu-id="09e18-270">**악의적인 통화 추적** 기능을 통해 사용자는 클라이언트 UI를 사용 하 여 악의적인 통화 (예: 위협)를 보고 하 고, 이렇게 하면 cdrs에서 호출에 플래그를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-270">**Malicious call tracing** enables users to report malicious calls (such as threats) using the client UI, which in turn flags the calls in the CDRs.</span></span> <span data-ttu-id="09e18-271">기본적으로 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-271">Disabled by default.</span></span>

6. <span data-ttu-id="09e18-272">이 음성 정책에 대 한 PSTN 사용 레코드를 연결 하 고 구성 하려면 다음 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-272">To associate and configure PSTN usage records for this voice policy, do any of the following:</span></span>

   - <span data-ttu-id="09e18-273">엔터프라이즈 음성 배포에서 사용할 수 있는 모든 PSTN 사용 레코드 목록에서 하나 이상의 레코드를 선택 하려면 **선택을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-273">To choose one or more records from a list of all PSTN usage records available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="09e18-274">이 음성 정책에 연결 하려는 레코드를 강조 표시 한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-274">Highlight the records that you want to associate with this voice policy, and then click **OK**.</span></span>

   - <span data-ttu-id="09e18-275">이 음성 정책에서 PSTN 사용 레코드를 제거 하려면 해당 레코드를 강조 표시 하 고 **제거**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-275">To remove a PSTN usage record from this voice policy, highlight the record and click **Remove**.</span></span>

   - <span data-ttu-id="09e18-276">새 PSTN 사용 레코드를 정의 하 고이를이 음성 정책에 연결 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-276">To define a new PSTN usage record and associate it with this voice policy, do the following:</span></span>

     <span data-ttu-id="09e18-277">에서.</span><span class="sxs-lookup"><span data-stu-id="09e18-277">a.</span></span> <span data-ttu-id="09e18-278">**새로 만들기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-278">Click **New**.</span></span>

     <span data-ttu-id="09e18-279">b.</span><span class="sxs-lookup"><span data-stu-id="09e18-279">b.</span></span> <span data-ttu-id="09e18-280">**이름** 필드에 레코드에 대 한 고유한 설명적인 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-280">In the **Name** field, enter a unique descriptive name for the record.</span></span> <span data-ttu-id="09e18-281">예를 들어, 레드먼드에 거주 하는 정규 직원을 위해 PSTN 사용 레코드 namedRedmond를 만들고 임시 직원에 대 한 다른 레코드 namedRedmondTemps를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-281">For example, you may want to create a PSTN usage record namedRedmond for full-time employees located in Redmond, and another record namedRedmondTemps for temporary employees.</span></span>

     > [!NOTE]
     > <span data-ttu-id="09e18-282">PSTN 사용 레코드 이름은 엔터프라이즈 음성 배포 내에서 고유 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-282">The PSTN usage record name must be unique within the Enterprise Voice deployment.</span></span> <span data-ttu-id="09e18-283">레코드가 저장 된 후에는 **이름** 필드를 편집할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-283">After the record is saved, the **Name** field cannot be edited.</span></span>

     <span data-ttu-id="09e18-284">c.</span><span class="sxs-lookup"><span data-stu-id="09e18-284">c.</span></span> <span data-ttu-id="09e18-285">다음 방법 중 하나를 사용 하 여이 PSTN 사용 레코드에 대 한 경로를 연결 하 고 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-285">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>

   - <span data-ttu-id="09e18-286">엔터프라이즈 음성 배포의 모든 사용 가능한 경로 목록에서 하나 이상의 경로를 선택 하려면 **선택을**클릭 하 고이 PSTN 사용 레코드와 연결할 경로를 강조 표시 한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-286">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes that you want to associate with this PSTN usage record, and then click **OK**.</span></span>

   - <span data-ttu-id="09e18-287">PSTN 사용 레코드에서 경로를 제거 하려면 경로를 강조 표시 하 고 **제거**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-287">To remove a route from the PSTN usage record, highlight the route and click **Remove**.</span></span>

   - <span data-ttu-id="09e18-288">새 경로를 정의 하 고이 PSTN 사용 레코드와 연결 하려면 **새로 만들기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-288">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="09e18-289">자세한 내용은 [비즈니스용 Skype에서 음성 경로 만들기 또는 수정을](create-or-modify-a-voice-route.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="09e18-289">For details, see [Create or modify a voice route in Skype for Business](create-or-modify-a-voice-route.md).</span></span>

   - <span data-ttu-id="09e18-290">이 PSTN 사용 레코드와 이미 연결 된 경로를 편집 하려면 해당 경로를 강조 표시 하 고 **세부 정보 표시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-290">To edit a route that is already associated with this PSTN usage record, highlight the route and click **Show details**.</span></span>

     <span data-ttu-id="09e18-291">a.</span><span class="sxs-lookup"><span data-stu-id="09e18-291">d.</span></span> <span data-ttu-id="09e18-292">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-292">Click **OK**.</span></span>

   - <span data-ttu-id="09e18-293">이 음성 정책에 이미 연결 된 PSTN 사용 레코드를 편집 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-293">To edit a PSTN usage record that is already associated with this voice policy, do the following:</span></span>

     <span data-ttu-id="09e18-294">에서.</span><span class="sxs-lookup"><span data-stu-id="09e18-294">a.</span></span> <span data-ttu-id="09e18-295">편집 하려는 PSTN 사용 레코드를 강조 표시 하 고 **세부 정보 표시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-295">Highlight the PSTN usage record that you want to edit and click **Show details**.</span></span>

     <span data-ttu-id="09e18-296">b.</span><span class="sxs-lookup"><span data-stu-id="09e18-296">b.</span></span> <span data-ttu-id="09e18-297">다음 방법 중 하나를 사용 하 여이 PSTN 사용 레코드에 대 한 경로를 연결 하 고 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-297">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>

   - <span data-ttu-id="09e18-298">엔터프라이즈 음성 배포의 모든 사용 가능한 경로 목록에서 하나 이상의 경로를 선택 하려면 **선택을**클릭 하 고이 PSTN 사용 레코드와 연결할 경로를 강조 표시 한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-298">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes that you want to associate with this PSTN usage record, and then click **OK**.</span></span>

   - <span data-ttu-id="09e18-299">이 PSTN 사용 레코드에서 경로를 제거 하려면 경로를 강조 표시 하 고 **제거**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-299">To remove a route from this PSTN usage record, highlight the route and click **Remove**.</span></span>

   - <span data-ttu-id="09e18-300">새 경로를 정의 하 고이 PSTN 사용 레코드와 연결 하려면 **새로 만들기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-300">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="09e18-301">자세한 내용은 [비즈니스용 Skype에서 음성 경로 만들기 또는 수정을](create-or-modify-a-voice-route.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="09e18-301">For details, see [Create or modify a voice route in Skype for Business](create-or-modify-a-voice-route.md).</span></span>

   - <span data-ttu-id="09e18-302">이 PSTN 사용 레코드와 이미 연결 된 경로를 편집 하려면 해당 경로를 강조 표시 하 고 **세부 정보 표시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-302">To edit a route that is already associated with this PSTN usage record, highlight the route and click **Show details**.</span></span>

     <span data-ttu-id="09e18-303">c.</span><span class="sxs-lookup"><span data-stu-id="09e18-303">c.</span></span> <span data-ttu-id="09e18-304">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-304">Click **OK**.</span></span>

7. <span data-ttu-id="09e18-305">최적의 성능을 위해 PSTN 사용 레코드를 정렬 합니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-305">Arrange the PSTN usage records for optimum performance.</span></span> <span data-ttu-id="09e18-306">목록에서 레코드의 위치를 변경 하려면 레코드 이름을 강조 표시 하 고 위쪽 또는 아래쪽 화살표를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-306">To change a record's position in the list, highlight the record name and click the up or down arrow.</span></span>

    > [!NOTE]
    > <span data-ttu-id="09e18-307">PSTN 사용 레코드가 음성 정책에 나열 되는 순서는 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-307">The order in which PSTN usage records are listed in the voice policy is significant.</span></span> <span data-ttu-id="09e18-308">비즈니스용 Skype 서버는 목록을 위에서 아래로 트래버스 합니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-308">Skype for Business Server traverses the list from the top down.</span></span> <span data-ttu-id="09e18-309">RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup 등의 사용 빈도 별로 목록을 구성 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-309">We recommend that you organize the list by frequency of use, for example: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup.</span></span>

8. <span data-ttu-id="09e18-310">이 음성 정책에서 통화 전환 및 동시 연결에 대 한 PSTN 사용 레코드를 연결 하 고 구성 하려면 다음 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-310">To associate and configure PSTN usage records for call forwarding and simultaneous ringing in this voice policy, do any of the following:</span></span>

   - <span data-ttu-id="09e18-311">착신 전환 및 동시 연결에 같은 PSTN 사용 레코드를이 음성 정책으로 사용 하려면 드롭다운 메뉴에서 **통화 PSTN 사용을 사용해 경로** 옵션을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-311">To use the same PSTN usage records for call forwarding and simultaneous ringing as this voice policy, select the option **Route using the call PSTN usages** from the drop-down menu.</span></span>

   - <span data-ttu-id="09e18-312">착신 전환을 허용 하 고 비즈니스용 Skype 사용자 에게만 동시에 연결 하려면 드롭다운 메뉴에서 비즈니스용 **skype 사용자에 대 한 경로만** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-312">To allow call forwarding and simultaneous ringing to internal Skype for Business users only, select **Route to internal Skype for Business users only** from the drop-down menu.</span></span> <span data-ttu-id="09e18-313">통화는 외부 PSTN 번호로 착신 전환 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-313">Calls will not be forwarded to external PSTN numbers.</span></span>

   - <span data-ttu-id="09e18-314">이 음성 정책에 사용 되는 통화 전환 및 동시 연결에 대해 다른 PSTN 사용 레코드를 지정 하려면 드롭다운 메뉴에서 **사용자 지정 PSTN 용도를 사용 하 여 경로** 옵션을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-314">To specify different PSTN usage records for call forwarding and simultaneous ringing than those used for this voice policy, select the option **Route using custom PSTN usages** from the drop-down menu.</span></span> <span data-ttu-id="09e18-315">이 옵션은 기존 PSTN 사용 레코드를 선택 하거나, 특히 착신 전환 및 동시 연결을 위해 새로운 PSTN 사용 레코드를 만드는 컨트롤을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-315">This option displays a control to select existing PSTN usage records or to create new PSTN usage records, specifically for call forwarding and simultaneous ringing.</span></span>

   - <span data-ttu-id="09e18-316">통화 전환 및 동시 연결에 대 한 PSTN 사용 레코드 목록에서 하나 이상의 레코드를 선택 하려면 **선택을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-316">To choose one or more records from a list of PSTN usage records for call forwarding and simultaneous ringing, click **Select**.</span></span> <span data-ttu-id="09e18-317">이 착신 전환 및 동시 연결 정책과 연결할 레코드를 강조 표시 한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-317">Highlight the records that you want to associate with this call forwarding and simultaneous ringing policy, and then click **OK**.</span></span>

   - <span data-ttu-id="09e18-318">이 착신 전환 및 동시 연결 정책에서 PSTN 사용 레코드를 제거 하려면 해당 레코드를 강조 표시 하 고 **제거**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-318">To remove a PSTN usage record from this call forwarding and simultaneous ringing policy, highlight the record and click **Remove**.</span></span>

   - <span data-ttu-id="09e18-319">새 PSTN 사용 레코드를 정의 하 고이를 착신 전환 및 동시 연결 정책과 연관 시키려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-319">To define a new PSTN usage record and associate it with this call forwarding and simultaneous ringing policy, do the following:</span></span>

     <span data-ttu-id="09e18-320">에서.</span><span class="sxs-lookup"><span data-stu-id="09e18-320">a.</span></span> <span data-ttu-id="09e18-321">**새로 만들기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-321">Click **New**.</span></span>

     <span data-ttu-id="09e18-322">b.</span><span class="sxs-lookup"><span data-stu-id="09e18-322">b.</span></span> <span data-ttu-id="09e18-323">**이름** 필드에 레코드에 대 한 고유한 설명적인 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-323">In the **Name** field, enter a unique descriptive name for the record.</span></span>

     > [!NOTE]
     > <span data-ttu-id="09e18-324">PSTN 사용 레코드 이름은 엔터프라이즈 음성 배포 내에서 고유 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-324">The PSTN usage record name must be unique within the Enterprise Voice deployment.</span></span> <span data-ttu-id="09e18-325">레코드가 저장 된 후에는 **이름** 필드를 편집할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-325">After the record is saved, the **Name** field cannot be edited.</span></span>

     <span data-ttu-id="09e18-326">c.</span><span class="sxs-lookup"><span data-stu-id="09e18-326">c.</span></span> <span data-ttu-id="09e18-327">다음 방법 중 하나를 사용 하 여이 PSTN 사용 레코드에 대 한 경로를 연결 하 고 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-327">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>

   - <span data-ttu-id="09e18-328">엔터프라이즈 음성 배포의 모든 사용 가능한 경로 목록에서 하나 이상의 경로를 선택 하려면 **선택을**클릭 하 고이 PSTN 사용 레코드와 연결할 경로를 강조 표시 한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-328">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes that you want to associate with this PSTN usage record, and then click **OK**.</span></span>

   - <span data-ttu-id="09e18-329">PSTN 사용 레코드에서 경로를 제거 하려면 경로를 강조 표시 하 고 **제거**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-329">To remove a route from the PSTN usage record, highlight the route and click **Remove**.</span></span>

   - <span data-ttu-id="09e18-330">새 경로를 정의 하 고이 PSTN 사용 레코드와 연결 하려면 **새로 만들기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-330">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="09e18-331">자세한 내용은 [비즈니스용 Skype에서 음성 경로 만들기 또는 수정을](create-or-modify-a-voice-route.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="09e18-331">For details, see [Create or modify a voice route in Skype for Business](create-or-modify-a-voice-route.md).</span></span>

   - <span data-ttu-id="09e18-332">이 PSTN 사용 레코드와 이미 연결 된 경로를 편집 하려면 해당 경로를 강조 표시 한 다음 **세부 정보 표시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-332">To edit a route that is already associated with this PSTN usage record, highlight the route, and then click **Show details**.</span></span> <span data-ttu-id="09e18-333">자세한 내용은 [음성 경로 수정을](https://technet.microsoft.com/library/afc562cc-8807-489b-8850-dbbe1c1ab9f5.aspx)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="09e18-333">For details, see [Modify a Voice Route](https://technet.microsoft.com/library/afc562cc-8807-489b-8850-dbbe1c1ab9f5.aspx).</span></span>

     <span data-ttu-id="09e18-334">a.</span><span class="sxs-lookup"><span data-stu-id="09e18-334">d.</span></span> <span data-ttu-id="09e18-335">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-335">Click **OK**.</span></span>

   - <span data-ttu-id="09e18-336">이 음성 정책에 이미 연결 된 PSTN 사용 레코드를 편집 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-336">To edit a PSTN usage record that is already associated with this voice policy, do the following:</span></span>

     <span data-ttu-id="09e18-337">에서.</span><span class="sxs-lookup"><span data-stu-id="09e18-337">a.</span></span> <span data-ttu-id="09e18-338">편집 하려는 PSTN 사용 레코드를 강조 표시 하 고 **세부 정보 표시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-338">Highlight the PSTN usage record that you want to edit and click **Show details**.</span></span>

     <span data-ttu-id="09e18-339">b.</span><span class="sxs-lookup"><span data-stu-id="09e18-339">b.</span></span> <span data-ttu-id="09e18-340">다음 방법 중 하나를 사용 하 여이 PSTN 사용 레코드에 대 한 경로를 연결 하 고 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-340">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>

     - <span data-ttu-id="09e18-341">엔터프라이즈 음성 배포의 모든 사용 가능한 경로 목록에서 하나 이상의 경로를 선택 하려면 **선택을**클릭 하 고이 PSTN 사용 레코드와 연결할 경로를 강조 표시 한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-341">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes you want to associate with this PSTN usage record, and then click **OK**.</span></span>

     - <span data-ttu-id="09e18-342">이 PSTN 사용 레코드에서 경로를 제거 하려면 경로를 강조 표시 하 고 **제거**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-342">To remove a route from this PSTN usage record, highlight the route and click **Remove**.</span></span>

     - <span data-ttu-id="09e18-343">새 경로를 정의 하 고이 PSTN 사용 레코드와 연결 하려면 **새로 만들기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-343">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="09e18-344">자세한 내용은 [비즈니스용 Skype에서 음성 경로 만들기 또는 수정을](create-or-modify-a-voice-route.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="09e18-344">For details, see [Create or modify a voice route in Skype for Business](create-or-modify-a-voice-route.md).</span></span>

     - <span data-ttu-id="09e18-345">이 PSTN 사용 레코드와 이미 연결 된 경로를 편집 하려면 해당 경로를 강조 표시 하 고 **세부 정보 표시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-345">To edit a route that is already associated with this PSTN usage record, highlight the route and click **Show details**.</span></span> <span data-ttu-id="09e18-346">자세한 내용은 [음성 경로 수정을](https://technet.microsoft.com/library/afc562cc-8807-489b-8850-dbbe1c1ab9f5.aspx)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="09e18-346">For details, see [Modify a Voice Route](https://technet.microsoft.com/library/afc562cc-8807-489b-8850-dbbe1c1ab9f5.aspx).</span></span>

     <span data-ttu-id="09e18-347">c.</span><span class="sxs-lookup"><span data-stu-id="09e18-347">c.</span></span> <span data-ttu-id="09e18-348">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-348">Click **OK**.</span></span>

9. <span data-ttu-id="09e18-349">) 번호를 입력 하 여 음성 정책을 테스트 하 고 **이동을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-349">(Optional) Enter a number to test the voice policy and click **Go**.</span></span> <span data-ttu-id="09e18-350">테스트 결과가 **테스트를 위해 번역 된 번호**아래에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-350">The test results are displayed under **Translated number to test**.</span></span>

10. <span data-ttu-id="09e18-351">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-351">Click **OK**.</span></span>

11. <span data-ttu-id="09e18-352">**음성 정책** 페이지에서 **커밋을**클릭 한 다음 **모두 커밋을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-352">On the **Voice Policy** page, click **Commit**, and then click **Commit all**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="09e18-353">음성 정책을 만들거나 수정할 때마다 **모두 커밋** 명령을 실행 하 여 구성 변경 내용을 게시 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-353">Whenever you create or modify a voice policy, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="09e18-354">자세한 내용은 운영 설명서의 비즈니스용 [Skype에서 음성 라우팅 구성에 보류 중인 변경 내용 게시](voice-route-config-changes.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="09e18-354">For details, see [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation.</span></span>

12. <span data-ttu-id="09e18-355">) 보이스 메일 감지는 전화가 사용자의 휴대폰 음성 메일로 바로 응답 하 고 휴대폰 음성 메일로 전화를 끊습니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-355">(Optional) Voicemail Escape detects that a call was immediately answered by the user's mobile phone voice mail, and disconnects the call to the mobile phone voice mail.</span></span> <span data-ttu-id="09e18-356">이렇게 하면 사용자가 전화를 받을 수 있도록 사용자가 다른 끝점을 계속 해 서 전화를 걸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09e18-356">This allows the call to continue to ring on the user's other endpoints giving the user the opportunity to answer the call.</span></span> <span data-ttu-id="09e18-357">음성 메일 정책을 구성 하는 방법에 대 한 자세한 내용은 [비즈니스용 Skype에서 음성 메일 Esc 구성을](configure-voice-mail-escape.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="09e18-357">For details about how to configure a voice mail policy, see [Configure voice mail escape in Skype for Business](configure-voice-mail-escape.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="09e18-358">참고 항목</span><span class="sxs-lookup"><span data-stu-id="09e18-358">See also</span></span>

[<span data-ttu-id="09e18-359">비즈니스용 Skype에서 PSTN 사용 레코드 보기</span><span class="sxs-lookup"><span data-stu-id="09e18-359">View PSTN usage records in Skype for Business</span></span>](view-pstn-usage-records.md)

[<span data-ttu-id="09e18-360">비즈니스용 Skype에서 음성 경로 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="09e18-360">Create or modify a voice route in Skype for Business</span></span>](create-or-modify-a-voice-route.md)

[<span data-ttu-id="09e18-361">비즈니스용 Skype에서 음성 라우팅 구성에 보류 중인 변경 내용 게시</span><span class="sxs-lookup"><span data-stu-id="09e18-361">Publish pending changes to the voice routing configuration in Skype for Business</span></span>](voice-route-config-changes.md)

[<span data-ttu-id="09e18-362">비즈니스용 Skype에서 음성 메일 esc 구성</span><span class="sxs-lookup"><span data-stu-id="09e18-362">Configure voice mail escape in Skype for Business</span></span>](configure-voice-mail-escape.md)

