---
title: 음성 정책 만들기 또는 수정 및 비즈니스용 Skype에서 PSTN 사용 레코드 구성
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: e6ff27e0-e2d1-4445-840f-08f738200c20
description: '요약: 음성 정책을 만들거나 수정하고 비즈니스용 Skype 서버 제어판을 사용하여 PSTN 사용 레코드를 구성합니다.'
ms.openlocfilehash: 3e0fe5cebfc9d46f5c21554f1e18b54799d2d1e8
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830408"
---
# <a name="create-or-modify-a-voice-policy-and-configure-pstn-usage-records-in-skype-for-business"></a><span data-ttu-id="3ebae-103">음성 정책 만들기 또는 수정 및 비즈니스용 Skype에서 PSTN 사용 레코드 구성</span><span class="sxs-lookup"><span data-stu-id="3ebae-103">Create or modify a voice policy and configure PSTN usage records in Skype for Business</span></span>

<span data-ttu-id="3ebae-104">**요약:** 음성 정책을 만들거나 수정하고 비즈니스용 Skype 서버 제어판을 사용하여 PSTN 사용 레코드를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="3ebae-104">**Summary:** Create or modify voice policies and configure PSTN usage records by using the Skype for Business Server Control Panel.</span></span>

> [!NOTE]
> <span data-ttu-id="3ebae-105">각 음성 정책에는 하나 이상의 연결된 PSTN(Public Switched Telephone Network) 사용 레코드가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ebae-105">Each voice policy must have at least one associated Public Switched Telephone Network (PSTN) usage record.</span></span> <span data-ttu-id="3ebae-106">Enterprise Voice 배포에서 사용할 수 있는 모든 PSTN 사용 레코드 목록을 보고 해당 속성을 확인한 경우 비즈니스용 Skype에서 PSTN 사용 레코드 [보기를 참조하세요.](view-pstn-usage-records.md)</span><span class="sxs-lookup"><span data-stu-id="3ebae-106">To see a listing of all PSTN usage records available in your Enterprise Voice deployment and view their properties, see [View PSTN usage records in Skype for Business](view-pstn-usage-records.md).</span></span>

### <a name="to-create-a-voice-policy"></a><span data-ttu-id="3ebae-107">음성 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3ebae-107">To create a voice policy</span></span>

1. <span data-ttu-id="3ebae-108">비즈니스용 Skype 서버 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="3ebae-108">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="3ebae-109">왼쪽 탐색 모음에서 음성 라우팅을 **클릭한** 다음 **음성 정책을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3ebae-109">In the left navigation bar, click **Voice Routing** and then click **Voice Policy**.</span></span>

3. <span data-ttu-id="3ebae-110">음성 정책 **페이지에서** 새로  고침을 클릭한 다음 새 정책의 범위를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3ebae-110">On the **Voice Policy** page, click **New** and then select a scope for the new policy:</span></span>

   - <span data-ttu-id="3ebae-111">**사이트 정책은** 사용자 정책에 할당된 사용자 또는 그룹을 제외한 전체 사이트에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="3ebae-111">**Site policy** applies to an entire site, except any users or groups that are assigned to a user policy.</span></span> <span data-ttu-id="3ebae-112">정책 범위에 대한 사이트를 선택하는 경우 사이트  선택 대화 상자에서 사이트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3ebae-112">If you select Site for a policy scope, choose the site from the **Select a Site** dialog box.</span></span> <span data-ttu-id="3ebae-113">사이트에 대한 음성 정책이 이미 만들어진 경우 사이트 선택 대화 상자에 사이트가 **나타나지** 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3ebae-113">If a voice policy has already been created for a site, the site does not appear in the **Select a Site** dialog box.</span></span>

   - <span data-ttu-id="3ebae-114">**사용자 정책은** 지정된 사용자 또는 그룹에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3ebae-114">**User policy** can be applied to specified users or groups.</span></span>

4. <span data-ttu-id="3ebae-115">음성 정책 범위가 User인 경우 이름 필드에 정책에 대한 설명적인 **이름을 입력합니다.**</span><span class="sxs-lookup"><span data-stu-id="3ebae-115">If the voice policy scope is User, enter a descriptive name for the policy in the **Name** field.</span></span>

    > [!NOTE]
    > <span data-ttu-id="3ebae-116">음성 정책 범위가 Site이면 새 **음성** 정책의 **이름** 필드에 사이트 이름이 미리 채우며 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3ebae-116">If the voice policy scope is Site, the **Name** field in **New Voice Policy** is prepopulated with the site name and cannot be changed.</span></span>

5. <span data-ttu-id="3ebae-117">(선택 사항) 음성 정책에 대한 추가 설명 정보를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="3ebae-117">(Optional) Enter additional descriptive information for the voice policy.</span></span>

6. <span data-ttu-id="3ebae-118">이 음성 정책에 대해 각 통화 기능을  사용하도록 설정하거나 사용하지 않도록 설정하려면 다음 확인란을 선택하거나 선택을 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="3ebae-118">Select or clear the following check boxes to enable or disable each of the **Calling features** for this voice policy:</span></span>

   - <span data-ttu-id="3ebae-119">음성 메일 이스케이프를 통해 동시 벨 울림이 구성되고 전화가 꺼지거나, 배터리가 부족하거나, 범위가 벗어났을 때 통화가 사용자의 휴대폰 음성 메일 시스템으로 즉시 라우팅되지 **않습니다.**</span><span class="sxs-lookup"><span data-stu-id="3ebae-119">**Voice mail escape** prevents calls from being immediately routed to the user's mobile phone voice mail system when simultaneous ringing is configured and the phone is turned off, out of battery, or out of range.</span></span>

     > [!NOTE]
     > <span data-ttu-id="3ebae-120">이 기능은 비즈니스용 Skype 서버 관리 셸을 통해서만 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3ebae-120">This feature is only configurable through the Skype for Business Server Management Shell</span></span>

   - <span data-ttu-id="3ebae-121">**착신 전환** - 통화를 다른 전화 및 클라이언트 장치로 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3ebae-121">**Call forwarding** enables users to forward calls to other phones and client devices.</span></span> <span data-ttu-id="3ebae-122">비즈니스용 Skype 서버는 통화 전달을 위한 훨씬 광범위한 구성 옵션을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="3ebae-122">Skype for Business Server provides a significantly wider range of configuration options for call forwarding.</span></span> <span data-ttu-id="3ebae-123">예를 들어 조직에서 수신 전화가 PSTN 외부로 전달되는 것을 허용하지 않을 경우 관리자는 특수 음성 정책을 적용하여 이 제한을 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3ebae-123">For example, if an organization does not want to allow incoming calls to be forwarded externally to the PSTN, an administrator can apply a special voice policy to deploy this restriction.</span></span> <span data-ttu-id="3ebae-124">이 확인란은 기본적으로 선택됩니다.</span><span class="sxs-lookup"><span data-stu-id="3ebae-124">Enabled by default.</span></span>

   - <span data-ttu-id="3ebae-125">**위임** - 자신을 대신해 전화를 걸거나 받을 다른 사용자를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3ebae-125">**Delegation** enables users to specify other users to send and receive calls on their behalf.</span></span> <span data-ttu-id="3ebae-126">비즈니스용 Skype 서버에서 대리인은 자신의 관리자에게 걸려오는 전화가 대리인의 동시 벨 울림 대상을 모두 울리도록 하는 동시 벨 울림을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3ebae-126">In Skype for Business Server, a delegate can configure simultaneous ringing that enables incoming calls to his or her manager to ring all of the delegate's simultaneous ringing targets.</span></span> <span data-ttu-id="3ebae-127">이렇게 하면 대리인이 관리자에게 연결한 통화에 보다 유연하게 응답할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3ebae-127">This provides the delegate with greater flexibility in responding to calls directed to the manager.</span></span> <span data-ttu-id="3ebae-128">이 확인란은 기본적으로 선택됩니다.</span><span class="sxs-lookup"><span data-stu-id="3ebae-128">Enabled by default.</span></span>

   - <span data-ttu-id="3ebae-129">**통화 전송** - 통화를 다른 사람에게 전송할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3ebae-129">**Call transfer** enables users to transfer calls to other users.</span></span> <span data-ttu-id="3ebae-130">이 확인란은 기본적으로 선택됩니다.</span><span class="sxs-lookup"><span data-stu-id="3ebae-130">Enabled by default.</span></span>

   - <span data-ttu-id="3ebae-131">**통화 파크를** 사용하면 통화를 보류한 다음 다른 전화 또는 클라이언트에서 통화를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3ebae-131">**Call park** enables users to park calls on hold and then pick up the call from a different phone or client.</span></span> <span data-ttu-id="3ebae-132">이 확인란은 기본적으로 선택 취소됩니다.</span><span class="sxs-lookup"><span data-stu-id="3ebae-132">Disabled by default.</span></span>

   - <span data-ttu-id="3ebae-133">**동시 전화 울림을** 사용하면 수신 전화가 추가 전화(예: 휴대폰) 또는 다른 끝점 장치에서 벨이 울리게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3ebae-133">**Simultaneous ringing** enables incoming calls to ring on additional phones (for example, a mobile phone) or other endpoint devices.</span></span> <span data-ttu-id="3ebae-134">비즈니스용 Skype 서버는 동시 벨 울림을 위한 훨씬 광범위한 구성 옵션을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="3ebae-134">Skype for Business Server provides a significantly wider range of configuration options for simultaneous ringing.</span></span> <span data-ttu-id="3ebae-135">이 확인란은 기본적으로 선택됩니다.</span><span class="sxs-lookup"><span data-stu-id="3ebae-135">Enabled by default.</span></span>

   - <span data-ttu-id="3ebae-136">**팀 호출** - 정의된 팀의 사용자가 팀의 다른 구성원에 대한 통화에 응답할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3ebae-136">**Team call** enables users on a defined team to answer calls for other members of the team.</span></span> <span data-ttu-id="3ebae-137">이 확인란은 기본적으로 선택됩니다.</span><span class="sxs-lookup"><span data-stu-id="3ebae-137">Enabled by default.</span></span>

   - <span data-ttu-id="3ebae-138">**PSTN 다시** 라우팅을 사용하면 이 정책이 할당된 사용자가 다른 엔터프라이즈 사용자에게 걸린 통화가 WAN이 정전되거나 사용할 수 없는 경우 PSTN에서 다시 라우팅될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3ebae-138">**PSTN re-route** enables calls made by users who are assigned this policy to other enterprise users to be rerouted on the PSTN if the WAN is congested or unavailable.</span></span> <span data-ttu-id="3ebae-139">이 확인란은 기본적으로 선택됩니다.</span><span class="sxs-lookup"><span data-stu-id="3ebae-139">Enabled by default.</span></span>

   - <span data-ttu-id="3ebae-140">**대역폭 정책 무시** 는 관리자가 특정 사용자의 통화 허용 제어 정책 결정을 무시하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="3ebae-140">**Bandwidth policy override** enables administrators to override call admission control policy decisions for a particular user.</span></span> <span data-ttu-id="3ebae-141">이 확인란은 기본적으로 선택 취소됩니다.</span><span class="sxs-lookup"><span data-stu-id="3ebae-141">Disabled by default.</span></span>

     > [!NOTE]
     > <span data-ttu-id="3ebae-142">사용자에 대한 수신 전화에만 정책이 다시 지정되고 사용자가 걸은 호출에 대해 정책이 다시 지정되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3ebae-142">The policy will be overridden only for incoming calls to the user and not for outgoing calls that are placed by the user.</span></span> <span data-ttu-id="3ebae-143">세션이 설정되면 대역폭 소비가 정확하게 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="3ebae-143">After the session is established, the bandwidth consumption will be accurately recorded.</span></span> <span data-ttu-id="3ebae-144">이 설정은 적게 사용하며 적절한 통화 제어 결정에 예약해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ebae-144">This setting should be used sparingly and should be reserved for appropriate call admission control decisions.</span></span>

   - <span data-ttu-id="3ebae-145">**악의적인 통화** 추적을 사용하면 클라이언트 UI를 사용하여 악성 통화(예: 위협)를 보고할 수 있습니다. 이 경우 CDRS(통화 정보 기록)의 통화에 플래그가 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="3ebae-145">**Malicious call tracing** enables users to report malicious calls (such as threats) by using the client UI, which in turn flags the calls in the Call Detail Records (CDRs).</span></span> <span data-ttu-id="3ebae-146">이 확인란은 기본적으로 선택 취소됩니다.</span><span class="sxs-lookup"><span data-stu-id="3ebae-146">Disabled by default.</span></span>

   - <span data-ttu-id="3ebae-147">**사용 중 옵션은** 지정된 음성 정책에 대해 다른 사용자 지정 옵션을 활성화하거나 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3ebae-147">**Busy options** enables or disables Busy Options for the specified voice policy.</span></span> <span data-ttu-id="3ebae-148">통화 중 옵션을 사용하면 통화의 대상 사용자가 전화에 있을 때 수신 전화를 음성 메일로 라우팅하거나 통화 중 신호로 거부할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3ebae-148">Busy Options allows incoming calls to be routed to voice mail or rejected with a busy signal when the call's target user is on the phone.</span></span> <span data-ttu-id="3ebae-149">다른 사용 중 옵션은 2016년 7월 누적 업데이트에 도입된 새로운 음성 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="3ebae-149">Busy Options is a new voice policy introduced in the July 2016 Cumulative Update.</span></span> <span data-ttu-id="3ebae-150">이 매개 변수를 확인하면 다른 사용자가 다른용 옵션을 사용할 수 있으며, 이 매개 변수를 선택하지 않은 경우 다른 사용자가 다른용 옵션을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3ebae-150">Checking this parameter enables Busy Options, and unchecking it disables Busy Options.</span></span> <span data-ttu-id="3ebae-151">자세한 내용은 비즈니스용 Skype 서버의 다른 [업무용 옵션](../../plan-your-deployment/enterprise-voice-solution/busy-options.md) 계획 및 비즈니스용 Skype 서버에 대한 사용 중 옵션 설치 [및 구성을 참조하세요.](install-and-configure-busy-options.md)</span><span class="sxs-lookup"><span data-stu-id="3ebae-151">For more information, see [Plan for Busy Options for Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/busy-options.md) and [Install and configure Busy Options for Skype for Business Server](install-and-configure-busy-options.md).</span></span>

7. <span data-ttu-id="3ebae-152">이 음성 정책에 대해 PSTN 사용 레코드를 연결하고 구성하기 위해 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="3ebae-152">To associate and configure PSTN usage records for this voice policy, do any of the following:</span></span>

   - <span data-ttu-id="3ebae-153">사용자 지정 배포에서 사용할 수 있는 모든 PSTN 사용 레코드 목록에서 하나 Enterprise Voice 선택을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3ebae-153">To choose one or more records from a list of all PSTN usage records available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="3ebae-154">이 음성 정책과 연결하려는 레코드를 강조 표시하고 확인을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3ebae-154">Highlight the records that you want to associate with this voice policy, and then click **OK**.</span></span>

   - <span data-ttu-id="3ebae-155">이 음성 정책에서 PSTN 사용 레코드를 제거하려면 레코드를 강조 표시하고 제거를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3ebae-155">To remove a PSTN usage record from this voice policy, highlight the record and click **Remove**.</span></span>

   - <span data-ttu-id="3ebae-156">새 PSTN 사용 레코드를 정의하고 이 음성 정책에 연결하기 위해 다음을 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ebae-156">To define a new PSTN usage record and associate it with this voice policy, do the following:</span></span>

     <span data-ttu-id="3ebae-157">a.</span><span class="sxs-lookup"><span data-stu-id="3ebae-157">a.</span></span> <span data-ttu-id="3ebae-158">**새로 만들기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3ebae-158">Click **New**.</span></span>

     <span data-ttu-id="3ebae-159">b.</span><span class="sxs-lookup"><span data-stu-id="3ebae-159">b.</span></span> <span data-ttu-id="3ebae-160">Name **필드에** 레코드에 대한 고유한 설명 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="3ebae-160">In the **Name** field, enter a unique descriptive name for the record.</span></span> <span data-ttu-id="3ebae-161">예를 들어 Redmond에 있는 정규 직원에 대해Redmond라는 PSTN 사용 레코드를 만들고 임시 직원에 대해 다른 명명된RedmondTemps를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3ebae-161">For example, you may want to create a PSTN usage record namedRedmond for full-time employees located in Redmond, and another namedRedmondTemps for temporary employees.</span></span>

     > [!NOTE]
     > <span data-ttu-id="3ebae-162">PSTN 사용 레코드 이름은 PSTN 배포 내에서 고유해야 Enterprise Voice 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ebae-162">The PSTN usage record name must be unique within the Enterprise Voice deployment.</span></span> <span data-ttu-id="3ebae-163">레코드를 저장한 후에는 **이름** 필드를 편집할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3ebae-163">After the record is saved, the **Name** field cannot be edited.</span></span>

     <span data-ttu-id="3ebae-164">c.</span><span class="sxs-lookup"><span data-stu-id="3ebae-164">c.</span></span> <span data-ttu-id="3ebae-165">다음 방법 중 한 가지를 사용하여 이 PSTN 사용 레코드에 대한 경로를 연결하고 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="3ebae-165">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>

   - <span data-ttu-id="3ebae-166">Enterprise Voice 배포에서 사용 가능한 모든 경로 목록에서 하나 이상의 경로를 선택하려면 선택을 클릭하고 이 PSTN 사용 레코드와 연결하려는 경로를 강조 표시한 다음 **확인을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3ebae-166">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes that you want to associate with this PSTN usage record, and then click **OK**.</span></span>

   - <span data-ttu-id="3ebae-167">PSTN 사용 레코드에서 경로를 제거하려면 경로를 강조 표시하고 제거를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3ebae-167">To remove a route from the PSTN usage record, highlight the route, and then click **Remove**.</span></span>

   - <span data-ttu-id="3ebae-168">새 경로를 정의하고 이 PSTN 사용 레코드와 연결하려면 새로 고치기 를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3ebae-168">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="3ebae-169">자세한 내용은 비즈니스용 Skype에서 음성 경로 만들기 [또는 수정을 참조하세요.](create-or-modify-a-voice-route.md)</span><span class="sxs-lookup"><span data-stu-id="3ebae-169">For details, see [Create or modify a voice route in Skype for Business](create-or-modify-a-voice-route.md).</span></span>

   - <span data-ttu-id="3ebae-170">이 PSTN 사용 레코드와 이미 연결된 경로를 편집하려면 경로를 강조 표시하고 세부 정보 **표시를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3ebae-170">To edit a route that is already associated with this PSTN usage record, highlight the route and click **Show details**.</span></span>

     <span data-ttu-id="3ebae-171">d.</span><span class="sxs-lookup"><span data-stu-id="3ebae-171">d.</span></span> <span data-ttu-id="3ebae-172">**확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3ebae-172">Click **OK**.</span></span>

   - <span data-ttu-id="3ebae-173">이 음성 정책과 이미 연결된 PSTN 사용 레코드를 편집하려면 다음을 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ebae-173">To edit a PSTN usage record that is already associated with this voice policy, do the following:</span></span>

     <span data-ttu-id="3ebae-174">a.</span><span class="sxs-lookup"><span data-stu-id="3ebae-174">a.</span></span> <span data-ttu-id="3ebae-175">편집할 PSTN 사용 레코드를 강조 표시한 다음 세부 정보 **표시를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3ebae-175">Highlight the PSTN usage record that you want to edit, and then click **Show details**.</span></span>

     <span data-ttu-id="3ebae-176">b.</span><span class="sxs-lookup"><span data-stu-id="3ebae-176">b.</span></span> <span data-ttu-id="3ebae-177">다음 방법 중 한 가지를 사용하여 이 PSTN 사용 레코드에 대한 경로를 연결하고 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="3ebae-177">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>

   - <span data-ttu-id="3ebae-178">Enterprise Voice 배포에서 사용 가능한 모든 경로 목록에서 하나 이상의 경로를 선택하려면 선택을 클릭하고 이 PSTN 사용 레코드와 연결하려는 경로를 강조 표시한 다음 **확인을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3ebae-178">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes you want to associate with this PSTN usage record, and then click **OK**.</span></span>

   - <span data-ttu-id="3ebae-179">이 PSTN 사용 레코드에서 경로를 제거하려면 경로를 강조 표시한 다음 제거를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3ebae-179">To remove a route from this PSTN usage record, highlight the route, and then click **Remove**.</span></span>

   - <span data-ttu-id="3ebae-180">새 경로를 정의하고 이 PSTN 사용 레코드와 연결하려면 새로 고치기 를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3ebae-180">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="3ebae-181">자세한 내용은 비즈니스용 Skype에서 음성 경로 만들기 [또는 수정을 참조하세요.](create-or-modify-a-voice-route.md)</span><span class="sxs-lookup"><span data-stu-id="3ebae-181">For details, see [Create or modify a voice route in Skype for Business](create-or-modify-a-voice-route.md).</span></span>

   - <span data-ttu-id="3ebae-182">이 PSTN 사용 레코드와 이미 연결된 경로를 편집하려면 경로를 강조 표시하고 세부 정보 **표시를 랙합니다.**</span><span class="sxs-lookup"><span data-stu-id="3ebae-182">To edit a route that is already associated with this PSTN usage record, highlight the route and lick **Show details**.</span></span>

     <span data-ttu-id="3ebae-183">c.</span><span class="sxs-lookup"><span data-stu-id="3ebae-183">c.</span></span> <span data-ttu-id="3ebae-184">**확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3ebae-184">Click **OK**.</span></span>

8. <span data-ttu-id="3ebae-185">최적의 성능을 유지하도록 PSTN 사용 레코드를 정렬합니다.</span><span class="sxs-lookup"><span data-stu-id="3ebae-185">Arrange the PSTN usage records for optimum performance.</span></span> <span data-ttu-id="3ebae-186">목록에서 레코드의 위치를 변경하려면 레코드 이름을 강조 표시하고 위쪽 또는 아래쪽 화살표를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3ebae-186">To change a record's position in the list, highlight the record name and click the up or down arrow.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="3ebae-187">음성 정책에 PSTN 사용 레코드가 나열되는 순서가 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="3ebae-187">The order in which PSTN usage records are listed in the voice policy is significant.</span></span> <span data-ttu-id="3ebae-188">비즈니스용 Skype 서버가 목록을 맨 아래에서 트래버스합니다.</span><span class="sxs-lookup"><span data-stu-id="3ebae-188">Skype for Business Server traverses the list from the top down.</span></span> <span data-ttu-id="3ebae-189">목록을 사용 빈도별로 구성하는 것이 좋습니다(예: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup).</span><span class="sxs-lookup"><span data-stu-id="3ebae-189">We recommend that you organize the list by frequency of use, for example: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup.</span></span>

9. <span data-ttu-id="3ebae-190">이 음성 정책에서 통화 전달 및 동시 전화 울림에 대해 PSTN 사용 레코드를 연결하고 구성하기 위해 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="3ebae-190">To associate and configure PSTN usage records for call forwarding and simultaneous ringing in this voice policy, do any of the following:</span></span>

   - <span data-ttu-id="3ebae-191">이 음성 정책과 동일한 PSTN 사용 레코드를 이 음성 정책과 동일한 PSTN 사용 레코드를 사용하려면 드롭다운 메뉴에서 **통화 PSTN** 사용을 사용하여 경로 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3ebae-191">To use the same PSTN usage records for call forwarding and simultaneous ringing as this voice policy, select the option **Route using the call PSTN usages** from the drop-down menu.</span></span>

   - <span data-ttu-id="3ebae-192">내부 비즈니스용 Skype 사용자에게만 통화 전달 및 동시 전화 울림을 허용하려면 드롭다운 메뉴에서만 내부 비즈니스용 **Skype** 사용자로 라우팅 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3ebae-192">To allow call forwarding and simultaneous ringing to internal Skype for Business users only, select the option **Route to internal Skype for Business users only** from the drop-down menu.</span></span> <span data-ttu-id="3ebae-193">통화가 외부 PSTN 번호로 전달되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3ebae-193">Calls will not be forwarded to external PSTN numbers.</span></span>

   - <span data-ttu-id="3ebae-194">이 음성 정책에 사용되는 것보다 통화 전달 및 동시 전화 울림에 대해 다른 PSTN 사용 레코드를 지정하려면 드롭다운 메뉴에서 사용자 지정 **PSTN** 사용을 사용하여 경로 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3ebae-194">To specify different PSTN usage records for call forwarding and simultaneous ringing than used for this voice policy, select the option **Route using custom PSTN usages** from the drop-down menu.</span></span> <span data-ttu-id="3ebae-195">이 옵션은 기존 PSTN 사용 레코드를 선택하거나 통화 전달 및 동시 전화 걸기 전용으로 새 PSTN 사용 레코드를 만드는 컨트롤을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="3ebae-195">This option displays a control to select existing PSTN usage records or create new PSTN usage records specifically for call forwarding and simultaneous ringing.</span></span>

   - <span data-ttu-id="3ebae-196">통화 전달 및 동시 전화 울림에 대한 PSTN 사용 레코드 목록에서 하나 이상의 레코드를 선택하려면 선택을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3ebae-196">To choose one or more records from a list of PSTN usage records for call forwarding and simultaneous ringing, click **Select**.</span></span> <span data-ttu-id="3ebae-197">이 통화 전달 및 동시 전화 울림 정책과 연결하려는 레코드를 강조 표시하고 확인을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3ebae-197">Highlight the records that you want to associate with this call forwarding and simultaneous ringing policy, and then click **OK**.</span></span>

   - <span data-ttu-id="3ebae-198">이 통화 전달 및 동시 전화 울림 정책에서 PSTN 사용 레코드를 제거하려면 레코드를 강조 표시하고 제거를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3ebae-198">To remove a PSTN usage record from this call forwarding and simultaneous ringing policy, highlight the record and click **Remove**.</span></span>

   - <span data-ttu-id="3ebae-199">새 PSTN 사용 레코드를 정의하고 이 통화 전달 및 동시 전화 울림 정책에 연결하기 위해 다음을 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ebae-199">To define a new PSTN usage record and associate it with this call forwarding and simultaneous ringing policy, do the following:</span></span>

     <span data-ttu-id="3ebae-200">a.</span><span class="sxs-lookup"><span data-stu-id="3ebae-200">a.</span></span> <span data-ttu-id="3ebae-201">**새로 만들기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3ebae-201">Click **New**.</span></span>

     <span data-ttu-id="3ebae-202">b.</span><span class="sxs-lookup"><span data-stu-id="3ebae-202">b.</span></span> <span data-ttu-id="3ebae-203">Name **필드에** 레코드에 대한 고유한 설명 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="3ebae-203">In the **Name** field, enter a unique descriptive name for the record.</span></span>

     > [!NOTE]
     > <span data-ttu-id="3ebae-204">PSTN 사용 레코드 이름은 PSTN 배포 내에서 고유해야 Enterprise Voice 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ebae-204">The PSTN usage record name must be unique within the Enterprise Voice deployment.</span></span> <span data-ttu-id="3ebae-205">레코드를 저장한 후에는 **이름** 필드를 편집할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3ebae-205">After the record is saved, the **Name** field cannot be edited.</span></span>

     <span data-ttu-id="3ebae-206">c.</span><span class="sxs-lookup"><span data-stu-id="3ebae-206">c.</span></span> <span data-ttu-id="3ebae-207">다음 방법 중 한 가지를 사용하여 이 PSTN 사용 레코드에 대한 경로를 연결하고 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="3ebae-207">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>

   - <span data-ttu-id="3ebae-208">Enterprise Voice 배포에서 사용 가능한 모든 경로 목록에서 하나 이상의 경로를 선택하려면 선택을 클릭하고 이 PSTN 사용 레코드와 연결하려는 경로를 강조 표시한 다음 **확인을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3ebae-208">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes that you want to associate with this PSTN usage record, and then click **OK**.</span></span>

   - <span data-ttu-id="3ebae-209">PSTN 사용 레코드에서 경로를 제거하려면 경로를 강조 표시하고 제거를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3ebae-209">To remove a route from the PSTN usage record, highlight the route and click **Remove**.</span></span>

   - <span data-ttu-id="3ebae-210">새 경로를 정의하고 이 PSTN 사용 레코드와 연결하려면 새로 고치기 를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3ebae-210">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="3ebae-211">자세한 내용은 비즈니스용 Skype에서 음성 경로 만들기 [또는 수정을 참조하세요.](create-or-modify-a-voice-route.md)</span><span class="sxs-lookup"><span data-stu-id="3ebae-211">For details, see [Create or modify a voice route in Skype for Business](create-or-modify-a-voice-route.md).</span></span>

   - <span data-ttu-id="3ebae-212">이 PSTN 사용 레코드와 이미 연결된 경로를 편집하려면 경로를 강조 표시하고 세부 정보 **표시를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3ebae-212">To edit a route that is already associated with this PSTN usage record, highlight the route and click **Show details**.</span></span>

     <span data-ttu-id="3ebae-213">d.</span><span class="sxs-lookup"><span data-stu-id="3ebae-213">d.</span></span> <span data-ttu-id="3ebae-214">**확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3ebae-214">Click **OK**.</span></span>

   - <span data-ttu-id="3ebae-215">이 음성 정책과 이미 연결된 PSTN 사용 레코드를 편집하려면 다음을 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ebae-215">To edit a PSTN usage record that is already associated with this voice policy, do the following:</span></span>

     <span data-ttu-id="3ebae-216">a.</span><span class="sxs-lookup"><span data-stu-id="3ebae-216">a.</span></span> <span data-ttu-id="3ebae-217">편집할 PSTN 사용 레코드를 강조 표시하고 세부 정보 **표시를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3ebae-217">Highlight the PSTN usage record you want to edit and click **Show details**.</span></span>

     <span data-ttu-id="3ebae-218">b.</span><span class="sxs-lookup"><span data-stu-id="3ebae-218">b.</span></span> <span data-ttu-id="3ebae-219">다음 방법 중 한 가지를 사용하여 이 PSTN 사용 레코드에 대한 경로를 연결하고 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="3ebae-219">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>

   - <span data-ttu-id="3ebae-220">Enterprise Voice 배포에서 사용 가능한 모든 경로 목록에서 하나 이상의 경로를 선택하려면 선택을 클릭하고 이 PSTN 사용 레코드와 연결하려는 경로를 강조 표시한 다음 **확인을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3ebae-220">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes that you want to associate with this PSTN usage record, and then click **OK**.</span></span>

   - <span data-ttu-id="3ebae-221">이 PSTN 사용 레코드에서 경로를 제거하려면 경로를 강조 표시하고 제거를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3ebae-221">To remove a route from this PSTN usage record, highlight the route and click **Remove**.</span></span>

   - <span data-ttu-id="3ebae-222">새 경로를 정의하고 이 PSTN 사용 레코드와 연결하려면 새로 고치기 를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3ebae-222">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="3ebae-223">자세한 내용은 비즈니스용 Skype에서 음성 경로 만들기 [또는 수정을 참조하세요.](create-or-modify-a-voice-route.md)</span><span class="sxs-lookup"><span data-stu-id="3ebae-223">For details, see [Create or modify a voice route in Skype for Business](create-or-modify-a-voice-route.md).</span></span>

   - <span data-ttu-id="3ebae-224">이 PSTN 사용 레코드와 이미 연결된 경로를 편집하려면 경로를 강조 표시하고 세부 정보 **표시를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3ebae-224">To edit a route that is already associated with this PSTN usage record, highlight the route and click **Show details**.</span></span>

     <span data-ttu-id="3ebae-225">c.</span><span class="sxs-lookup"><span data-stu-id="3ebae-225">c.</span></span> <span data-ttu-id="3ebae-226">**확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3ebae-226">Click **OK**.</span></span>

10. <span data-ttu-id="3ebae-227">(선택 사항) 음성 정책을 테스트할 번호를 입력하고 이동을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3ebae-227">(Optional) Enter a number to test the voice policy and click **Go**.</span></span> <span data-ttu-id="3ebae-228">테스트 결과는 테스트할 **번역된 번호 아래에 표시됩니다.**</span><span class="sxs-lookup"><span data-stu-id="3ebae-228">The test results are displayed under **Translated number to test**.</span></span>

11. <span data-ttu-id="3ebae-229">**확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3ebae-229">Click **OK**.</span></span>

12. <span data-ttu-id="3ebae-230">음성 정책 **페이지에서** 커밋을 클릭한 다음 모두  **커밋을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3ebae-230">On the **Voice Policy** page, click **Commit**, and then click **Commit all**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="3ebae-231">음성 정책을 만들거나 수정할 때 구성 변경을 게시하려면 모두 커밋 명령을 실행해야 합니다. </span><span class="sxs-lookup"><span data-stu-id="3ebae-231">Any time you create or modify a voice policy, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="3ebae-232">자세한 내용은 작업 설명서에서 비즈니스용 [Skype의](voice-route-config-changes.md) 음성 라우팅 구성에 보류 중인 변경 내용 게시를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="3ebae-232">For details, see [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation.</span></span>

13. <span data-ttu-id="3ebae-233">(선택 사항) 음성 메일 이스케이프는 사용자의 휴대폰 음성 메일에 의해 통화가 즉시 수신된 것을 감지하고 휴대폰 음성 메일에 대한 통화 연결을 끊습니다.</span><span class="sxs-lookup"><span data-stu-id="3ebae-233">(Optional) Voicemail Escape detects that a call was immediately answered by the user's mobile phone voice mail, and disconnects the call to the mobile phone voice mail.</span></span> <span data-ttu-id="3ebae-234">이렇게 하면 통화가 사용자의 다른 끝점에서 계속 울리면 사용자에게 통화에 응답할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3ebae-234">This allows the call to continue to ring on the user's other endpoints giving the user the opportunity to answer the call.</span></span> <span data-ttu-id="3ebae-235">음성 메일 정책을 구성하는 방법에 대한 자세한 내용은 비즈니스용 Skype에서 음성 [메일 이스케이프 구성을 참조하세요.](configure-voice-mail-escape.md)</span><span class="sxs-lookup"><span data-stu-id="3ebae-235">For details on how to configure a voice mail policy, see [Configure voice mail escape in Skype for Business](configure-voice-mail-escape.md).</span></span>

### <a name="to-modify-a-voice-policy"></a><span data-ttu-id="3ebae-236">음성 정책을 수정하려면</span><span class="sxs-lookup"><span data-stu-id="3ebae-236">To modify a voice policy</span></span>

1. <span data-ttu-id="3ebae-237">비즈니스용 Skype 서버 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="3ebae-237">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="3ebae-238">왼쪽 탐색 모음에서 **음성** 라우팅을 클릭한 다음 **음성 정책을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3ebae-238">In the left navigation bar, click **Voice Routing**, and then click **Voice Policy**.</span></span>

3. <span data-ttu-id="3ebae-239">음성 정책 **페이지에서** 음성 정책 이름을 두 번 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3ebae-239">On the **Voice Policy** page, double-click a voice policy name.</span></span>

    > [!NOTE]
    > <span data-ttu-id="3ebae-240">범위와 이름은 음성 정책을 만들 때 설정되었습니다.</span><span class="sxs-lookup"><span data-stu-id="3ebae-240">The scope and name were set when the voice policy was created.</span></span> <span data-ttu-id="3ebae-241">이러한 설정은 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3ebae-241">They cannot be changed.</span></span>

4. <span data-ttu-id="3ebae-242">(선택 사항) 음성 **정책 편집에서** 음성 정책에 대한 추가 설명 정보를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="3ebae-242">(Optional) In **Edit Voice Policy**, enter additional descriptive information for the voice policy.</span></span>

5. <span data-ttu-id="3ebae-243">각 통화 기능을 사용하도록 설정하거나 사용하지 않도록 설정하려면 다음 확인란을 **선택하거나 선택을 취소합니다.**</span><span class="sxs-lookup"><span data-stu-id="3ebae-243">Select or clear the following check boxes to enable or disable each of the **Calling features**:</span></span>

   - <span data-ttu-id="3ebae-244">음성 메일 이스케이프를 통해 동시 벨 울림이 구성되고 전화가 꺼지거나, 배터리가 부족하거나, 범위가 벗어났을 때 통화가 사용자의 휴대폰 음성 메일 시스템으로 즉시 라우팅되지 **않습니다.**</span><span class="sxs-lookup"><span data-stu-id="3ebae-244">**Voice mail escape** prevents calls from being immediately routed to the user's mobile phone voice mail system when simultaneous ringing is configured and the phone is turned off, out of battery, or out of range.</span></span>

     > [!NOTE]
     > <span data-ttu-id="3ebae-245">이 기능은 비즈니스용 Skype 서버 관리 셸을 통해서만 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3ebae-245">This feature is only configurable through the Skype for Business Server Management Shell</span></span>

   - <span data-ttu-id="3ebae-246">**착신 전환** - 통화를 다른 전화 및 클라이언트 장치로 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3ebae-246">**Call forwarding** enables users to forward calls to other phones and client devices.</span></span> <span data-ttu-id="3ebae-247">비즈니스용 Skype 서버는 통화 전달을 위한 훨씬 광범위한 구성 옵션을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="3ebae-247">Skype for Business Server provides a significantly wider range of configuration options for call forwarding.</span></span> <span data-ttu-id="3ebae-248">예를 들어 조직에서 수신 전화가 PSTN 외부로 전달되는 것을 허용하지 않을 경우 관리자는 특수 음성 정책을 적용하여 이 제한을 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3ebae-248">For example, if an organization does not want to allow incoming calls to be forwarded externally to the PSTN, an administrator can apply a special voice policy to deploy this restriction.</span></span> <span data-ttu-id="3ebae-249">이 확인란은 기본적으로 선택됩니다.</span><span class="sxs-lookup"><span data-stu-id="3ebae-249">Enabled by default.</span></span>

   - <span data-ttu-id="3ebae-250">**위임** - 자신을 대신해 전화를 걸거나 받을 다른 사용자를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3ebae-250">**Delegation** enables users to specify other users to send and receive calls on their behalf.</span></span> <span data-ttu-id="3ebae-251">비즈니스용 Skype 서버에서 대리인은 자신의 관리자에게 걸려오는 전화가 대리인의 동시 벨 울림 대상을 모두 울리도록 하는 동시 벨 울림을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3ebae-251">In Skype for Business Server, a delegate can configure simultaneous ringing that enables incoming calls to his or her manager to ring all of the delegate's simultaneous ringing targets.</span></span> <span data-ttu-id="3ebae-252">이렇게 하면 대리인이 관리자에게 연결한 통화에 보다 유연하게 응답할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3ebae-252">This provides the delegate with greater flexibility in responding to calls directed to the manager.</span></span> <span data-ttu-id="3ebae-253">이 확인란은 기본적으로 선택됩니다.</span><span class="sxs-lookup"><span data-stu-id="3ebae-253">Enabled by default.</span></span>

   - <span data-ttu-id="3ebae-254">**통화 전송** - 통화를 다른 사람에게 전송할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3ebae-254">**Call transfer** enables users to transfer calls to other users.</span></span> <span data-ttu-id="3ebae-255">이 확인란은 기본적으로 선택됩니다.</span><span class="sxs-lookup"><span data-stu-id="3ebae-255">Enabled by default.</span></span>

   - <span data-ttu-id="3ebae-256">**통화 파크를** 사용하면 통화를 보류한 다음 다른 전화 또는 클라이언트에서 통화를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3ebae-256">**Call park** enables users to park calls on hold, and then pick up the call from a different phone or client.</span></span> <span data-ttu-id="3ebae-257">이 확인란은 기본적으로 선택 취소됩니다.</span><span class="sxs-lookup"><span data-stu-id="3ebae-257">Disabled by default.</span></span>

   - <span data-ttu-id="3ebae-258">**동시 전화 울림을** 사용하면 수신 전화가 추가 전화(예: 휴대폰) 또는 다른 끝점 장치에서 벨이 울리게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3ebae-258">**Simultaneous ringing** enables incoming calls to ring on additional phones (for example, a mobile phone) or other endpoint devices.</span></span> <span data-ttu-id="3ebae-259">비즈니스용 Skype 서버는 동시 벨 울림을 위한 훨씬 광범위한 구성 옵션을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="3ebae-259">Skype for Business Server provides a significantly wider range of configuration options for simultaneous ringing.</span></span> <span data-ttu-id="3ebae-260">이 확인란은 기본적으로 선택됩니다.</span><span class="sxs-lookup"><span data-stu-id="3ebae-260">Enabled by default.</span></span>

   - <span data-ttu-id="3ebae-261">**팀 호출** - 정의된 팀의 사용자가 팀의 다른 구성원에 대한 통화에 응답할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3ebae-261">**Team call** enables users on a defined team to answer calls for other members of the team.</span></span> <span data-ttu-id="3ebae-262">이 확인란은 기본적으로 선택됩니다.</span><span class="sxs-lookup"><span data-stu-id="3ebae-262">Enabled by default.</span></span>

   - <span data-ttu-id="3ebae-263">**PSTN 다시** 라우팅을 사용하면 이 정책이 할당된 사용자가 다른 엔터프라이즈 사용자에게 걸린 통화가 WAN이 정전되거나 사용할 수 없는 경우 PSTN에서 다시 라우팅될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3ebae-263">**PSTN re-route** enables calls made by users who are assigned this policy to other enterprise users to be rerouted on the PSTN if the WAN is congested or unavailable.</span></span> <span data-ttu-id="3ebae-264">이 확인란은 기본적으로 선택됩니다.</span><span class="sxs-lookup"><span data-stu-id="3ebae-264">Enabled by default.</span></span>

   - <span data-ttu-id="3ebae-265">**대역폭 정책은** 관리자가 특정 사용자에 대한 CAC 정책 결정을 의회할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ebae-265">**Bandwidth policy override** enables administrators to override CAC policy decisions for a particular user.</span></span> <span data-ttu-id="3ebae-266">이 확인란은 기본적으로 선택 취소됩니다.</span><span class="sxs-lookup"><span data-stu-id="3ebae-266">Disabled by default.</span></span>

     > [!NOTE]
     > <span data-ttu-id="3ebae-267">사용자에 대한 수신 전화에만 정책이 다시 지정되고 사용자가 걸은 호출에 대해 정책이 다시 지정되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3ebae-267">The policy will be overridden only for incoming calls to the user and not for outgoing calls that are placed by the user.</span></span> <span data-ttu-id="3ebae-268">세션이 설정되면 대역폭 소비가 정확하게 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="3ebae-268">After the session is established, the bandwidth consumption will be accurately recorded.</span></span> <span data-ttu-id="3ebae-269">이 설정은 가급적 사용하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="3ebae-269">This setting should be used sparingly.</span></span>

   - <span data-ttu-id="3ebae-270">**악의적인 통화 추적을** 사용하면 클라이언트 UI를 사용하여 악의적인 통화(예: 위협)를 보고할 수 있습니다. 이 경우 CDRS의 통화에 플래그가 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="3ebae-270">**Malicious call tracing** enables users to report malicious calls (such as threats) using the client UI, which in turn flags the calls in the CDRs.</span></span> <span data-ttu-id="3ebae-271">이 확인란은 기본적으로 선택 취소됩니다.</span><span class="sxs-lookup"><span data-stu-id="3ebae-271">Disabled by default.</span></span>

6. <span data-ttu-id="3ebae-272">이 음성 정책에 대해 PSTN 사용 레코드를 연결하고 구성하기 위해 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="3ebae-272">To associate and configure PSTN usage records for this voice policy, do any of the following:</span></span>

   - <span data-ttu-id="3ebae-273">사용자 지정 배포에서 사용할 수 있는 모든 PSTN 사용 레코드 목록에서 하나 Enterprise Voice 선택을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3ebae-273">To choose one or more records from a list of all PSTN usage records available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="3ebae-274">이 음성 정책과 연결하려는 레코드를 강조 표시하고 확인을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3ebae-274">Highlight the records that you want to associate with this voice policy, and then click **OK**.</span></span>

   - <span data-ttu-id="3ebae-275">이 음성 정책에서 PSTN 사용 레코드를 제거하려면 레코드를 강조 표시하고 제거를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3ebae-275">To remove a PSTN usage record from this voice policy, highlight the record and click **Remove**.</span></span>

   - <span data-ttu-id="3ebae-276">새 PSTN 사용 레코드를 정의하고 이 음성 정책에 연결하기 위해 다음을 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ebae-276">To define a new PSTN usage record and associate it with this voice policy, do the following:</span></span>

     <span data-ttu-id="3ebae-277">a.</span><span class="sxs-lookup"><span data-stu-id="3ebae-277">a.</span></span> <span data-ttu-id="3ebae-278">**새로 만들기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3ebae-278">Click **New**.</span></span>

     <span data-ttu-id="3ebae-279">b.</span><span class="sxs-lookup"><span data-stu-id="3ebae-279">b.</span></span> <span data-ttu-id="3ebae-280">Name **필드에** 레코드에 대한 고유한 설명 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="3ebae-280">In the **Name** field, enter a unique descriptive name for the record.</span></span> <span data-ttu-id="3ebae-281">예를 들어 Redmond에 있는 정규 직원에 대해Redmond라는 PSTN 사용 레코드를 만들고 임시 직원용RedmondTemps라는 다른 레코드를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3ebae-281">For example, you may want to create a PSTN usage record namedRedmond for full-time employees located in Redmond, and another record namedRedmondTemps for temporary employees.</span></span>

     > [!NOTE]
     > <span data-ttu-id="3ebae-282">PSTN 사용 레코드 이름은 PSTN 배포 내에서 고유해야 Enterprise Voice 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ebae-282">The PSTN usage record name must be unique within the Enterprise Voice deployment.</span></span> <span data-ttu-id="3ebae-283">레코드를 저장한 후에는 **이름** 필드를 편집할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3ebae-283">After the record is saved, the **Name** field cannot be edited.</span></span>

     <span data-ttu-id="3ebae-284">c.</span><span class="sxs-lookup"><span data-stu-id="3ebae-284">c.</span></span> <span data-ttu-id="3ebae-285">다음 방법 중 한 가지를 사용하여 이 PSTN 사용 레코드에 대한 경로를 연결하고 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="3ebae-285">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>

   - <span data-ttu-id="3ebae-286">Enterprise Voice 배포에서 사용 가능한 모든 경로 목록에서 하나 이상의 경로를 선택하려면 선택을 클릭하고 이 PSTN 사용 레코드와 연결하려는 경로를 강조 표시한 다음 **확인을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3ebae-286">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes that you want to associate with this PSTN usage record, and then click **OK**.</span></span>

   - <span data-ttu-id="3ebae-287">PSTN 사용 레코드에서 경로를 제거하려면 경로를 강조 표시하고 제거를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3ebae-287">To remove a route from the PSTN usage record, highlight the route and click **Remove**.</span></span>

   - <span data-ttu-id="3ebae-288">새 경로를 정의하고 이 PSTN 사용 레코드와 연결하려면 새로 고치기 를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3ebae-288">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="3ebae-289">자세한 내용은 비즈니스용 Skype에서 음성 경로 만들기 [또는 수정을 참조하세요.](create-or-modify-a-voice-route.md)</span><span class="sxs-lookup"><span data-stu-id="3ebae-289">For details, see [Create or modify a voice route in Skype for Business](create-or-modify-a-voice-route.md).</span></span>

   - <span data-ttu-id="3ebae-290">이 PSTN 사용 레코드와 이미 연결된 경로를 편집하려면 경로를 강조 표시하고 세부 정보 **표시를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3ebae-290">To edit a route that is already associated with this PSTN usage record, highlight the route and click **Show details**.</span></span>

     <span data-ttu-id="3ebae-291">d.</span><span class="sxs-lookup"><span data-stu-id="3ebae-291">d.</span></span> <span data-ttu-id="3ebae-292">**확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3ebae-292">Click **OK**.</span></span>

   - <span data-ttu-id="3ebae-293">이 음성 정책과 이미 연결된 PSTN 사용 레코드를 편집하려면 다음을 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ebae-293">To edit a PSTN usage record that is already associated with this voice policy, do the following:</span></span>

     <span data-ttu-id="3ebae-294">a.</span><span class="sxs-lookup"><span data-stu-id="3ebae-294">a.</span></span> <span data-ttu-id="3ebae-295">편집할 PSTN 사용 레코드를 강조 표시하고 세부 정보 **표시를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3ebae-295">Highlight the PSTN usage record that you want to edit and click **Show details**.</span></span>

     <span data-ttu-id="3ebae-296">b.</span><span class="sxs-lookup"><span data-stu-id="3ebae-296">b.</span></span> <span data-ttu-id="3ebae-297">다음 방법 중 한 가지를 사용하여 이 PSTN 사용 레코드에 대한 경로를 연결하고 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="3ebae-297">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>

   - <span data-ttu-id="3ebae-298">Enterprise Voice 배포에서 사용 가능한 모든 경로 목록에서 하나 이상의 경로를 선택하려면 선택을 클릭하고 이 PSTN 사용 레코드와 연결하려는 경로를 강조 표시한 다음 **확인을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3ebae-298">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes that you want to associate with this PSTN usage record, and then click **OK**.</span></span>

   - <span data-ttu-id="3ebae-299">이 PSTN 사용 레코드에서 경로를 제거하려면 경로를 강조 표시하고 제거를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3ebae-299">To remove a route from this PSTN usage record, highlight the route and click **Remove**.</span></span>

   - <span data-ttu-id="3ebae-300">새 경로를 정의하고 이 PSTN 사용 레코드와 연결하려면 새로 고치기 를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3ebae-300">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="3ebae-301">자세한 내용은 비즈니스용 Skype에서 음성 경로 만들기 [또는 수정을 참조하세요.](create-or-modify-a-voice-route.md)</span><span class="sxs-lookup"><span data-stu-id="3ebae-301">For details, see [Create or modify a voice route in Skype for Business](create-or-modify-a-voice-route.md).</span></span>

   - <span data-ttu-id="3ebae-302">이 PSTN 사용 레코드와 이미 연결된 경로를 편집하려면 경로를 강조 표시하고 세부 정보 **표시를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3ebae-302">To edit a route that is already associated with this PSTN usage record, highlight the route and click **Show details**.</span></span>

     <span data-ttu-id="3ebae-303">c.</span><span class="sxs-lookup"><span data-stu-id="3ebae-303">c.</span></span> <span data-ttu-id="3ebae-304">**확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3ebae-304">Click **OK**.</span></span>

7. <span data-ttu-id="3ebae-305">최적의 성능을 유지하도록 PSTN 사용 레코드를 정렬합니다.</span><span class="sxs-lookup"><span data-stu-id="3ebae-305">Arrange the PSTN usage records for optimum performance.</span></span> <span data-ttu-id="3ebae-306">목록에서 레코드의 위치를 변경하려면 레코드 이름을 강조 표시하고 위쪽 또는 아래쪽 화살표를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3ebae-306">To change a record's position in the list, highlight the record name and click the up or down arrow.</span></span>

    > [!NOTE]
    > <span data-ttu-id="3ebae-307">음성 정책에 PSTN 사용 레코드가 나열되는 순서가 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="3ebae-307">The order in which PSTN usage records are listed in the voice policy is significant.</span></span> <span data-ttu-id="3ebae-308">비즈니스용 Skype 서버가 목록을 맨 아래에서 트래버스합니다.</span><span class="sxs-lookup"><span data-stu-id="3ebae-308">Skype for Business Server traverses the list from the top down.</span></span> <span data-ttu-id="3ebae-309">목록을 사용 빈도별로 구성하는 것이 좋습니다(예: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup).</span><span class="sxs-lookup"><span data-stu-id="3ebae-309">We recommend that you organize the list by frequency of use, for example: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup.</span></span>

8. <span data-ttu-id="3ebae-310">이 음성 정책에서 통화 전달 및 동시 전화 울림에 대해 PSTN 사용 레코드를 연결하고 구성하기 위해 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="3ebae-310">To associate and configure PSTN usage records for call forwarding and simultaneous ringing in this voice policy, do any of the following:</span></span>

   - <span data-ttu-id="3ebae-311">이 음성 정책과 동일한 PSTN 사용 레코드를 이 음성 정책과 동일한 PSTN 사용 레코드를 사용하려면 드롭다운 메뉴에서 **통화 PSTN** 사용을 사용하여 경로 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3ebae-311">To use the same PSTN usage records for call forwarding and simultaneous ringing as this voice policy, select the option **Route using the call PSTN usages** from the drop-down menu.</span></span>

   - <span data-ttu-id="3ebae-312">내부 비즈니스용 Skype 사용자에게만 통화 전달 및 동시 전화 울림을 허용하려면 드롭다운 메뉴에서만 내부 비즈니스용 **Skype** 사용자로 경로를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3ebae-312">To allow call forwarding and simultaneous ringing to internal Skype for Business users only, select **Route to internal Skype for Business users only** from the drop-down menu.</span></span> <span data-ttu-id="3ebae-313">통화가 외부 PSTN 번호로 전달되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3ebae-313">Calls will not be forwarded to external PSTN numbers.</span></span>

   - <span data-ttu-id="3ebae-314">통화 전달 및 동시 전화 울림에 대해 이 음성 정책에 사용된 PSTN 사용 레코드와 다른 PSTN 사용 레코드를 지정하려면 드롭다운 메뉴에서 사용자 지정 **PSTN** 사용을 사용하여 경로 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3ebae-314">To specify different PSTN usage records for call forwarding and simultaneous ringing than those used for this voice policy, select the option **Route using custom PSTN usages** from the drop-down menu.</span></span> <span data-ttu-id="3ebae-315">이 옵션은 기존 PSTN 사용 레코드를 선택하거나 특히 통화 전달 및 동시 전화 울림을 위한 새 PSTN 사용 레코드를 만드는 컨트롤을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="3ebae-315">This option displays a control to select existing PSTN usage records or to create new PSTN usage records, specifically for call forwarding and simultaneous ringing.</span></span>

   - <span data-ttu-id="3ebae-316">통화 전달 및 동시 전화 울림에 대한 PSTN 사용 레코드 목록에서 하나 이상의 레코드를 선택하려면 선택을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3ebae-316">To choose one or more records from a list of PSTN usage records for call forwarding and simultaneous ringing, click **Select**.</span></span> <span data-ttu-id="3ebae-317">이 통화 전달 및 동시 전화 울림 정책과 연결하려는 레코드를 강조 표시하고 확인을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3ebae-317">Highlight the records that you want to associate with this call forwarding and simultaneous ringing policy, and then click **OK**.</span></span>

   - <span data-ttu-id="3ebae-318">이 통화 전달 및 동시 전화 울림 정책에서 PSTN 사용 레코드를 제거하려면 레코드를 강조 표시하고 제거를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3ebae-318">To remove a PSTN usage record from this call forwarding and simultaneous ringing policy, highlight the record and click **Remove**.</span></span>

   - <span data-ttu-id="3ebae-319">새 PSTN 사용 레코드를 정의하고 이 통화 전달 및 동시 전화 울림 정책에 연결하기 위해 다음을 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ebae-319">To define a new PSTN usage record and associate it with this call forwarding and simultaneous ringing policy, do the following:</span></span>

     <span data-ttu-id="3ebae-320">a.</span><span class="sxs-lookup"><span data-stu-id="3ebae-320">a.</span></span> <span data-ttu-id="3ebae-321">**새로 만들기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3ebae-321">Click **New**.</span></span>

     <span data-ttu-id="3ebae-322">b.</span><span class="sxs-lookup"><span data-stu-id="3ebae-322">b.</span></span> <span data-ttu-id="3ebae-323">Name **필드에** 레코드에 대한 고유한 설명 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="3ebae-323">In the **Name** field, enter a unique descriptive name for the record.</span></span>

     > [!NOTE]
     > <span data-ttu-id="3ebae-324">PSTN 사용 레코드 이름은 PSTN 배포 내에서 고유해야 Enterprise Voice 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ebae-324">The PSTN usage record name must be unique within the Enterprise Voice deployment.</span></span> <span data-ttu-id="3ebae-325">레코드를 저장한 후에는 **이름** 필드를 편집할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3ebae-325">After the record is saved, the **Name** field cannot be edited.</span></span>

     <span data-ttu-id="3ebae-326">c.</span><span class="sxs-lookup"><span data-stu-id="3ebae-326">c.</span></span> <span data-ttu-id="3ebae-327">다음 방법 중 한 가지를 사용하여 이 PSTN 사용 레코드에 대한 경로를 연결하고 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="3ebae-327">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>

   - <span data-ttu-id="3ebae-328">Enterprise Voice 배포에서 사용 가능한 모든 경로 목록에서 하나 이상의 경로를 선택하려면 선택을 클릭하고 이 PSTN 사용 레코드와 연결하려는 경로를 강조 표시한 다음 **확인을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3ebae-328">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes that you want to associate with this PSTN usage record, and then click **OK**.</span></span>

   - <span data-ttu-id="3ebae-329">PSTN 사용 레코드에서 경로를 제거하려면 경로를 강조 표시하고 제거를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3ebae-329">To remove a route from the PSTN usage record, highlight the route and click **Remove**.</span></span>

   - <span data-ttu-id="3ebae-330">새 경로를 정의하고 이 PSTN 사용 레코드와 연결하려면 새로 고치기 를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3ebae-330">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="3ebae-331">자세한 내용은 비즈니스용 Skype에서 음성 경로 만들기 [또는 수정을 참조하세요.](create-or-modify-a-voice-route.md)</span><span class="sxs-lookup"><span data-stu-id="3ebae-331">For details, see [Create or modify a voice route in Skype for Business](create-or-modify-a-voice-route.md).</span></span>

   - <span data-ttu-id="3ebae-332">이 PSTN 사용 레코드와 이미 연결된 경로를 편집하려면 경로를 강조 표시한 다음 세부 정보 **표시를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3ebae-332">To edit a route that is already associated with this PSTN usage record, highlight the route, and then click **Show details**.</span></span> <span data-ttu-id="3ebae-333">자세한 내용은 [Modify a Voice Route](https://technet.microsoft.com/library/afc562cc-8807-489b-8850-dbbe1c1ab9f5.aspx)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="3ebae-333">For details, see [Modify a Voice Route](https://technet.microsoft.com/library/afc562cc-8807-489b-8850-dbbe1c1ab9f5.aspx).</span></span>

     <span data-ttu-id="3ebae-334">d.</span><span class="sxs-lookup"><span data-stu-id="3ebae-334">d.</span></span> <span data-ttu-id="3ebae-335">**확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3ebae-335">Click **OK**.</span></span>

   - <span data-ttu-id="3ebae-336">이 음성 정책과 이미 연결된 PSTN 사용 레코드를 편집하려면 다음을 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ebae-336">To edit a PSTN usage record that is already associated with this voice policy, do the following:</span></span>

     <span data-ttu-id="3ebae-337">a.</span><span class="sxs-lookup"><span data-stu-id="3ebae-337">a.</span></span> <span data-ttu-id="3ebae-338">편집할 PSTN 사용 레코드를 강조 표시하고 세부 정보 **표시를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3ebae-338">Highlight the PSTN usage record that you want to edit and click **Show details**.</span></span>

     <span data-ttu-id="3ebae-339">b.</span><span class="sxs-lookup"><span data-stu-id="3ebae-339">b.</span></span> <span data-ttu-id="3ebae-340">다음 방법 중 한 가지를 사용하여 이 PSTN 사용 레코드에 대한 경로를 연결하고 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="3ebae-340">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>

     - <span data-ttu-id="3ebae-341">Enterprise Voice 배포에서 사용 가능한 모든 경로 목록에서 하나 이상의 경로를 선택하려면 선택을 클릭하고 이 PSTN 사용 레코드와 연결하려는 경로를 강조 표시한 다음 **확인을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3ebae-341">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes you want to associate with this PSTN usage record, and then click **OK**.</span></span>

     - <span data-ttu-id="3ebae-342">이 PSTN 사용 레코드에서 경로를 제거하려면 경로를 강조 표시하고 제거를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3ebae-342">To remove a route from this PSTN usage record, highlight the route and click **Remove**.</span></span>

     - <span data-ttu-id="3ebae-343">새 경로를 정의하고 이 PSTN 사용 레코드와 연결하려면 새로 고치기 를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3ebae-343">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="3ebae-344">자세한 내용은 비즈니스용 Skype에서 음성 경로 만들기 [또는 수정을 참조하세요.](create-or-modify-a-voice-route.md)</span><span class="sxs-lookup"><span data-stu-id="3ebae-344">For details, see [Create or modify a voice route in Skype for Business](create-or-modify-a-voice-route.md).</span></span>

     - <span data-ttu-id="3ebae-345">이 PSTN 사용 레코드와 이미 연결된 경로를 편집하려면 경로를 강조 표시하고 세부 정보 **표시를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3ebae-345">To edit a route that is already associated with this PSTN usage record, highlight the route and click **Show details**.</span></span> <span data-ttu-id="3ebae-346">자세한 내용은 [Modify a Voice Route](https://technet.microsoft.com/library/afc562cc-8807-489b-8850-dbbe1c1ab9f5.aspx)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="3ebae-346">For details, see [Modify a Voice Route](https://technet.microsoft.com/library/afc562cc-8807-489b-8850-dbbe1c1ab9f5.aspx).</span></span>

     <span data-ttu-id="3ebae-347">c.</span><span class="sxs-lookup"><span data-stu-id="3ebae-347">c.</span></span> <span data-ttu-id="3ebae-348">**확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3ebae-348">Click **OK**.</span></span>

9. <span data-ttu-id="3ebae-349">(선택 사항) 음성 정책을 테스트할 번호를 입력하고 이동을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3ebae-349">(Optional) Enter a number to test the voice policy and click **Go**.</span></span> <span data-ttu-id="3ebae-350">테스트 결과는 테스트할 **번역된 번호 아래에 표시됩니다.**</span><span class="sxs-lookup"><span data-stu-id="3ebae-350">The test results are displayed under **Translated number to test**.</span></span>

10. <span data-ttu-id="3ebae-351">**확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3ebae-351">Click **OK**.</span></span>

11. <span data-ttu-id="3ebae-352">음성 정책 **페이지에서** 커밋을 클릭한 다음 모두  **커밋을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3ebae-352">On the **Voice Policy** page, click **Commit**, and then click **Commit all**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="3ebae-353">음성 정책을 만들거나 수정할 때마다 모든 커밋 명령을 실행하여 구성 변경을 게시해야 합니다. </span><span class="sxs-lookup"><span data-stu-id="3ebae-353">Whenever you create or modify a voice policy, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="3ebae-354">자세한 내용은 작업 설명서에서 비즈니스용 [Skype의](voice-route-config-changes.md) 음성 라우팅 구성에 보류 중인 변경 내용 게시를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="3ebae-354">For details, see [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation.</span></span>

12. <span data-ttu-id="3ebae-355">(선택 사항) 음성 메일 이스케이프는 사용자의 휴대폰 음성 메일에 의해 통화가 즉시 수신된 것을 감지하고 휴대폰 음성 메일에 대한 통화 연결을 끊습니다.</span><span class="sxs-lookup"><span data-stu-id="3ebae-355">(Optional) Voicemail Escape detects that a call was immediately answered by the user's mobile phone voice mail, and disconnects the call to the mobile phone voice mail.</span></span> <span data-ttu-id="3ebae-356">이렇게 하면 통화가 사용자의 다른 끝점에서 계속 울리면 사용자에게 통화에 응답할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3ebae-356">This allows the call to continue to ring on the user's other endpoints giving the user the opportunity to answer the call.</span></span> <span data-ttu-id="3ebae-357">음성 메일 정책을 구성하는 방법에 대한 자세한 내용은 비즈니스용 Skype에서 음성 [메일 이스케이프 구성을 참조하세요.](configure-voice-mail-escape.md)</span><span class="sxs-lookup"><span data-stu-id="3ebae-357">For details about how to configure a voice mail policy, see [Configure voice mail escape in Skype for Business](configure-voice-mail-escape.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="3ebae-358">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3ebae-358">See also</span></span>

[<span data-ttu-id="3ebae-359">비즈니스용 Skype에서 PSTN 사용 레코드 보기</span><span class="sxs-lookup"><span data-stu-id="3ebae-359">View PSTN usage records in Skype for Business</span></span>](view-pstn-usage-records.md)

[<span data-ttu-id="3ebae-360">비즈니스용 Skype에서 음성 경로 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="3ebae-360">Create or modify a voice route in Skype for Business</span></span>](create-or-modify-a-voice-route.md)

[<span data-ttu-id="3ebae-361">비즈니스용 Skype에서 음성 라우팅 구성에 보류 중인 변경 내용 게시</span><span class="sxs-lookup"><span data-stu-id="3ebae-361">Publish pending changes to the voice routing configuration in Skype for Business</span></span>](voice-route-config-changes.md)

[<span data-ttu-id="3ebae-362">비즈니스용 Skype에서 음성 메일 이스케이프 구성</span><span class="sxs-lookup"><span data-stu-id="3ebae-362">Configure voice mail escape in Skype for Business</span></span>](configure-voice-mail-escape.md)

