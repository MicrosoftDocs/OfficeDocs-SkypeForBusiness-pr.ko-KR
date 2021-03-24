---
title: 비즈니스용 Skype 서버에서 미디어 우회 없이 트렁크 구성
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
ms.assetid: 3422e93e-7bd2-4470-968c-dc38345b18ca
description: '요약: 비즈니스용 Skype 서버에 대해 미디어 우회를 사용하도록 설정하지 않은 트렁크를 구성합니다.'
ms.openlocfilehash: ff1c34e36906c8b9f5c88495e3c24239f572184a
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51106384"
---
# <a name="configure-a-trunk-without-media-bypass-in-skype-for-business-server"></a><span data-ttu-id="d9b52-103">비즈니스용 Skype 서버에서 미디어 우회 없이 트렁크 구성</span><span class="sxs-lookup"><span data-stu-id="d9b52-103">Configure a trunk without media bypass in Skype for Business Server</span></span>

<span data-ttu-id="d9b52-104">**요약:** 비즈니스용 Skype 서버에 대해 미디어 우회를 사용하도록 설정하지 않고 트렁크를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="d9b52-104">**Summary:** Configure a trunk without media bypass enabled for Skype for Business Server.</span></span>

<span data-ttu-id="d9b52-105">미디어 바이패스가 비활성화된 트렁크를 구성하려면 다음 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="d9b52-105">If you want to configure a trunk with media bypass disabled, follow these steps.</span></span> <span data-ttu-id="d9b52-106">미디어 우회를 사용하도록 설정한 트렁크를 구성하려는 경우 비즈니스용 Skype 서버에서 미디어 우회를 사용하는 트렁크 [구성을 참조하세요.](configure-trunk-with-media-bypass.md)</span><span class="sxs-lookup"><span data-stu-id="d9b52-106">If you want to configure a trunk with media bypass enabled, see [Configure a trunk with media bypass in Skype for Business Server](configure-trunk-with-media-bypass.md).</span></span>

<span data-ttu-id="d9b52-p102">트렁크 구성은 아래에 설명된 것처럼 해당 트렁크 구성에 할당된 트렁크에 적용되는 매개 변수 집합을 그룹화합니다. 특정 트렁크 구성의 범위를 전역으로(특정 사이트 또는 풀 구성을 포함하지 않는 모든 트렁크가 포함됨) 또는 사이트나 풀로 지정할 수 있습니다. 풀 수준 트렁크 구성은 특정 트렁크 구성의 범위를 단일 트렁크로 지정하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9b52-p102">A trunk configuration, as described below, groups a set of parameters that are applied to trunks assigned this trunk configuration. A particular trunk configuration can be scoped globally (to all trunks that do not have more specific site or pool configuration), or to a site, or to a pool. The pool-level trunk configuration is used to scope a specific trunk configuration to a single trunk.</span></span>

### <a name="to-configure-a-trunk-without-media-bypass"></a><span data-ttu-id="d9b52-110">미디어 바이패스를 사용하지 않는 트렁크를 구성하려면</span><span class="sxs-lookup"><span data-stu-id="d9b52-110">To configure a trunk without media bypass</span></span>

1. <span data-ttu-id="d9b52-111">비즈니스용 Skype 서버 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="d9b52-111">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="d9b52-112">왼쪽 탐색 모음에서 **음성 라우팅** 을 클릭한 다음 **트렁크 구성** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d9b52-112">In the left navigation bar, click **Voice Routing**, and then click **Trunk Configuration**.</span></span>

3. <span data-ttu-id="d9b52-113">**트렁크 구성** 페이지에서 다음 방법 중 하나를 사용하여 트렁크를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="d9b52-113">On the **Trunk Configuration** page, use one of the following methods to configure a trunk:</span></span>

   - <span data-ttu-id="d9b52-114">기존 트렁크(예: **전역** 트렁크)를 두 번 클릭하여 **트렁크 구성 편집** 대화 상자를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="d9b52-114">Double-click an existing trunk (for example, the **Global** trunk) to display the **Edit Trunk Configuration** dialog box.</span></span>

   - <span data-ttu-id="d9b52-115">**새로 만들기** 를 클릭한 다음 새 트렁크 구성의 범위를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d9b52-115">Click **New**, and then select a scope for the new trunk configuration:</span></span>

   - <span data-ttu-id="d9b52-116">**사이트 트렁크:** 사이트 선택에서 이 트렁크 구성에 사용할 사이트를 선택하고 확인을 **클릭합니다.** </span><span class="sxs-lookup"><span data-stu-id="d9b52-116">**Site trunk**: Choose the site for this trunk configuration in **Select a Site**, and then click **OK**.</span></span> <span data-ttu-id="d9b52-117">트렁크 구성이 이미 만들어진 사이트는 **사이트 선택** 대화 상자에 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d9b52-117">Note that if a trunk configuration has already been created for a site, the site does not appear in **Select a Site**.</span></span> <span data-ttu-id="d9b52-118">이 트렁크 구성은 사이트의 모든 트렁크에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9b52-118">This trunk configuration will be applied to all trunks in the site.</span></span>

   - <span data-ttu-id="d9b52-119">**풀 트렁크**: **서비스 선택** 대화 상자에서 이 트렁크 구성을 적용할 트렁크의 이름을 선택하고 **확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d9b52-119">**Pool trunk**: Choose the name of the trunk that this trunk configuration applies to in **Select a Service** and click **OK**.</span></span> <span data-ttu-id="d9b52-120">이 트렁크는 루트 트렁크 또는 토폴로지 작성기에서 정의된 추가 트렁크일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9b52-120">This trunk can be the root trunk, or any additional trunks defined in Topology Builder.</span></span> <span data-ttu-id="d9b52-121">트렁크 구성이 이미 만들어진 특정 트렁크는 **서비스 선택** 대화 상자에 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d9b52-121">Note that if a trunk configuration has already been created for a specific trunk, the trunk does not appear in **Select a Service**.</span></span>

     > [!NOTE]
     > <span data-ttu-id="d9b52-122">트렁크 구성 범위는 선택한 후에 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d9b52-122">After you select the scope of the trunk configuration, it cannot be changed.</span></span> <span data-ttu-id="d9b52-123">> 이름 **필드에는** 트렁크 구성의 연결된 사이트 또는 서비스의 이름이 미리 채워지며 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d9b52-123">> The **Name** field is pre-populated with the name of the trunk configuration's associated site or service and cannot be changed.</span></span>

4. <span data-ttu-id="d9b52-124">다음 **암호화 지원 수준** 옵션 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d9b52-124">Select one of the following **Encryption support level** options:</span></span>

   - <span data-ttu-id="d9b52-125">**필수:** SRTP(Secure Realtime Transport Protocol) 암호화를 사용하여 중재 서버와 게이트웨이 또는 PBX(Private Branch eXchange) 간의 트래픽을 보호해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9b52-125">**Required**: Secure Realtime Transport Protocol (SRTP) encryption must be used to help protect traffic between the Mediation Server and the gateway or Private Branch eXchange (PBX).</span></span>

   - <span data-ttu-id="d9b52-126">**선택**: 서비스 공급자 또는 OEM에서 지원하는 경우 SRTP 암호화를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d9b52-126">**Optional**: SRTP encryption will be used if the service provider or equipment manufacturer supports it.</span></span>

   - <span data-ttu-id="d9b52-127">**지원되지 않음**: 서비스 공급자 또는 OEM에서 지원하지 않으므로 SRTP 암호화를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d9b52-127">**Not Supported**: SRTP encryption is not supported by the service provider or equipment manufacturer and therefore will not be used.</span></span>

5. <span data-ttu-id="d9b52-128">**미디어 바이패스 사용** 확인란의 선택이 취소되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="d9b52-128">Be sure that the **Enable media bypass** check box is cleared.</span></span>

6. <span data-ttu-id="d9b52-129">알려진  미디어 종료 지점(예: 미디어 종료가 신호 종료 IP와 동일한 PSTN(Public Switched Telephone Network) 게이트웨이)이 있는 경우 중앙 집중식 미디어 처리 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d9b52-129">Select the **Centralized media processing** check box if there is a well-known media termination point (for example, a Public Switched Telephone Network (PSTN) gateway where the media termination has the same IP as the signaling termination).</span></span> <span data-ttu-id="d9b52-130">트렁크에 알려진 미디어 종료 지점이 없는 경우에는 이 확인란의 선택을 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="d9b52-130">Clear this check box if the trunk does not have a well-known media termination point.</span></span>

7. <span data-ttu-id="d9b52-131">트렁크 피어가 중재 서버에서 SIP REFER 요청 수신을 지원하는  경우 게이트웨이 참조 보내기 사용 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d9b52-131">If the trunk peer supports receiving SIP REFER requests from the Mediation Server, select the **Enable sending refer to the gateway** check box.</span></span>

8. <span data-ttu-id="d9b52-132">원하는 경우 트렁크 간 라우팅을 사용하도록 설정하려면 PSTN 사용 레코드를 이 트렁크 구성에 연결하고 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="d9b52-132">(Optional) To enable inter-trunk routing, associate and configure PSTN usage records to this trunk configuration.</span></span> <span data-ttu-id="d9b52-133">이 트렁크 구성에 연결된 PSTN 사용은 비즈니스용 Skype 서버 끝점에서 시작되지 않는 트렁크를 통해 들어오는 모든 호출에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9b52-133">The PSTN usages associated to this trunk configuration will be applied for all incoming calls through the trunk that is not originating from a Skype for Business Server endpoint.</span></span> <span data-ttu-id="d9b52-134">트렁크 구성에 연결된 PSTN 사용 레코드를 관리하려면 다음 방법 중 하나를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d9b52-134">To manage PSTN usage records associated to a trunk configuration, use one of the following methods:</span></span>

   - <span data-ttu-id="d9b52-135">Enterprise Voice 배포에서 사용할 수 있는 모든 PSTN 사용 레코드 목록에서 하나 이상의 레코드를 선택하려면 선택을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="d9b52-135">To select one or more records from a list of all PSTN usage records available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="d9b52-136">이 트렁크 구성과 연결할 레코드를 강조 표시하고 **확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d9b52-136">Highlight the records you want to associate with this trunk configuration and then click **OK**.</span></span>

   - <span data-ttu-id="d9b52-137">이 트렁크 구성에서 PSTN 사용 레코드를 제거하려면 레코드를 강조 표시하고 **제거** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d9b52-137">To remove a PSTN usage record from this trunk configuration, select the record and click **Remove**.</span></span>

   - <span data-ttu-id="d9b52-138">새 PSTN 사용 레코드를 정의하고 이 트렁크 구성과 연결하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="d9b52-138">To define a new PSTN usage record and associate it with this trunk configuration, do the following:</span></span>

     <span data-ttu-id="d9b52-139">a.</span><span class="sxs-lookup"><span data-stu-id="d9b52-139">a.</span></span> <span data-ttu-id="d9b52-140">**새로 만들기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d9b52-140">Click **New**.</span></span>

     <span data-ttu-id="d9b52-141">b.</span><span class="sxs-lookup"><span data-stu-id="d9b52-141">b.</span></span> <span data-ttu-id="d9b52-142">**이름** 필드에서 레코드를 설명하는 고유한 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d9b52-142">In the **Name** field, specify a descriptive name for the record that is unique.</span></span>

     > [!NOTE]
     > <span data-ttu-id="d9b52-143">PSTN 사용 레코드 이름은 배포 Enterprise Voice 고유해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9b52-143">The PSTN usage record name must be unique within the Enterprise Voice deployment.</span></span> <span data-ttu-id="d9b52-144">레코드를 저장한 후에는 **이름** 필드를 편집할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d9b52-144">After the record is saved, the **Name** field cannot be edited.</span></span>

     <span data-ttu-id="d9b52-145">c.</span><span class="sxs-lookup"><span data-stu-id="d9b52-145">c.</span></span> <span data-ttu-id="d9b52-146">다음 방법 중 하나를 사용하여 이 PSTN 사용 레코드에 대한 경로를 구성하고 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="d9b52-146">Use one of the following methods to associate and configure routes for this PSTN usage record:</span></span>

     - <span data-ttu-id="d9b52-147">Enterprise Voice 배포에서 사용 가능한 모든 경로 목록에서 하나 이상의 경로를 선택하려면 선택을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="d9b52-147">To select one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="d9b52-148">이 PSTN 사용 레코드와 연결할 경로를 강조 표시한 다음 **확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d9b52-148">Highlight the routes you want to associate with this PSTN usage record, and click **OK**.</span></span>

     - <span data-ttu-id="d9b52-149">PSTN 사용 레코드에서 경로를 제거하려면 경로를 선택하고 **제거** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d9b52-149">To remove a route from the PSTN usage record, select the route, and click **Remove**.</span></span>

     - <span data-ttu-id="d9b52-150">새 경로를 정의하고 이 PSTN 사용 레코드와 연결하려면 **새로 만들기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d9b52-150">To define a new route and associate it to this PSTN usage record, click **New**.</span></span> <span data-ttu-id="d9b52-151">자세한 내용은 비즈니스용 Skype에서 음성 경로 만들기 또는 [수정을 참조하세요.](create-or-modify-a-voice-route.md)</span><span class="sxs-lookup"><span data-stu-id="d9b52-151">For details, see [Create or modify a voice route in Skype for Business](create-or-modify-a-voice-route.md).</span></span>

     - <span data-ttu-id="d9b52-152">이 PSTN 사용 레코드에 연결된 경로를 편집하려면 경로를 선택하고 **자세한 정보 표시** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d9b52-152">To edit a route that is associated with this PSTN usage record, select the route, and click **Show details**.</span></span>

     <span data-ttu-id="d9b52-153">d.</span><span class="sxs-lookup"><span data-stu-id="d9b52-153">d.</span></span> <span data-ttu-id="d9b52-154">**확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d9b52-154">Click **OK**.</span></span>

   - <span data-ttu-id="d9b52-155">이 트렁크 구성에 이미 연결된 PSTN 사용 레코드를 편집하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="d9b52-155">To edit a PSTN usage record that is already associated with this trunk configuration, do the following:</span></span>

     <span data-ttu-id="d9b52-156">a.</span><span class="sxs-lookup"><span data-stu-id="d9b52-156">a.</span></span> <span data-ttu-id="d9b52-157">편집할 PSTN 사용 레코드를 선택하고 **자세한 정보 표시** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d9b52-157">Select the PSTN usage record you want to edit, and click **Show details**.</span></span>

     <span data-ttu-id="d9b52-158">b.</span><span class="sxs-lookup"><span data-stu-id="d9b52-158">b.</span></span> <span data-ttu-id="d9b52-159">다음 방법 중 하나를 사용하여 이 PSTN 사용 레코드에 대한 경로를 구성하고 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="d9b52-159">Use one of the following methods to associate and configure routes for this PSTN usage record:</span></span>

     - <span data-ttu-id="d9b52-160">Enterprise Voice 배포에서 사용 가능한 모든 경로 목록에서 하나 이상의 경로를 선택하려면 선택을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="d9b52-160">To select one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="d9b52-161">이 PSTN 사용 레코드와 연결할 경로를 강조 표시한 다음 **확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d9b52-161">Highlight the routes you want to associate with this PSTN usage record, and click **OK**.</span></span>

     - <span data-ttu-id="d9b52-162">PSTN 사용 레코드에서 경로를 제거하려면 경로를 선택하고 **제거** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d9b52-162">To remove a route from the PSTN usage record, select the route, and click **Remove**.</span></span>

     - <span data-ttu-id="d9b52-163">새 경로를 정의하고 이 PSTN 사용 레코드와 연결하려면 **새로 만들기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d9b52-163">To define a new route and associate it to this PSTN usage record, click **New**.</span></span> <span data-ttu-id="d9b52-164">자세한 내용은 비즈니스용 Skype에서 음성 경로 만들기 또는 [수정을 참조하세요.](create-or-modify-a-voice-route.md)</span><span class="sxs-lookup"><span data-stu-id="d9b52-164">For details, see [Create or modify a voice route in Skype for Business](create-or-modify-a-voice-route.md).</span></span>

     - <span data-ttu-id="d9b52-165">이 PSTN 사용 레코드에 연결된 경로를 편집하려면 경로를 선택하고 **자세한 정보 표시** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d9b52-165">To edit a route that is associated with this PSTN usage record, select the route, and click **Show details**.</span></span>

     <span data-ttu-id="d9b52-166">c.</span><span class="sxs-lookup"><span data-stu-id="d9b52-166">c.</span></span> <span data-ttu-id="d9b52-167">**확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d9b52-167">Click **OK**.</span></span>

     > [!IMPORTANT]
     > <span data-ttu-id="d9b52-168">구성되는 트렁크와 연결된 중재 서버 피어에 따라 PSTN 사용 레코드를 연결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9b52-168">It is important to associate PSTN usage records according to the Mediation Server peer that is associated to the trunk being configured.</span></span> <span data-ttu-id="d9b52-169">중재 서버 피어가 PSTN 게이트웨이 또는 SBC(Session Border Controller)인 경우 트렁크 구성이 PSTN 대상 또는 비즈니스용 Skype 서버를 통해 연결된 다른 다운스트림 시스템으로 라우팅되는 PSTN 사용 레코드에 연결되지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="d9b52-169">If the Mediation Server peer is a PSTN gateway or a Session Border Controller (SBC), it is strongly recommended that the trunk configuration is not associated to a PSTN usage record that routes to a PSTN destination or any other downstream systems connected via Skype for Business Server.</span></span>

9. <span data-ttu-id="d9b52-170">최적의 성능을 유지하도록 PSTN 사용 레코드를 정렬합니다.</span><span class="sxs-lookup"><span data-stu-id="d9b52-170">Arrange the PSTN usage records for optimum performance.</span></span> <span data-ttu-id="d9b52-171">목록에서 레코드의 위치를 변경하려면 PSTN 사용 레코드를 선택하고 위쪽 또는 아래쪽 화살표를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d9b52-171">To change a record's position in the list, select the PSTN usage record, and click the up or down arrows.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="d9b52-172">PSTN 사용 레코드가 트렁크 구성에서 나열되는 순서가 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="d9b52-172">The order in which PSTN usage records are listed in the trunk configuration is significant.</span></span> <span data-ttu-id="d9b52-173">비즈니스용 Skype 서버는 목록을 위쪽에서 아래로 트래버스합니다.</span><span class="sxs-lookup"><span data-stu-id="d9b52-173">Skype for Business Server traverses the list from top to down.</span></span>

10. <span data-ttu-id="d9b52-174">NAT 또는 방화벽 뒤의 클라이언트와 래치를 지원하는 SBC에 대해 미디어 바이패스를 사용하도록 설정하려면 **RTP 래치 사용** 을 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9b52-174">**Enable RTP Latching** should be selected to enable bypass media for clients behind a NAT or firewall and an SBC that supports latching.</span></span>

11. <span data-ttu-id="d9b52-175">**통화 기록 정보를** 중재 서버의 게이트웨이 피어로 보낼 수 있도록 설정하려면 전달 통화 기록 사용이 선택되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9b52-175">**Enable forward call history** should be selected to enable sending of call history information to the gateway peer of the Mediation Server.</span></span>

12. <span data-ttu-id="d9b52-176">PAI 통화 발신자 정보를 중재 서버 쪽과 게이트웨이 쪽(또는 그 반대의 경우) 간에 전달할 수 있도록 설정하려면 **P-Asserted-Identity** 데이터를 전달하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9b52-176">**Enable forward P-Asserted-Identity data** should be selected to enable PAI call originator information to be forwarded between the Mediation Server side and gateway side (and vice versa), when present.</span></span>

13. <span data-ttu-id="d9b52-177">빠른 장애 조치(failover)를 사용하도록 설정하려면 **아웃바운드 라우팅 장애 조치(failover) 타이머 사용** 을 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9b52-177">**Enable outbound routing failover timer** should be selected to enable fast failover.</span></span> <span data-ttu-id="d9b52-178">이 트렁크와 연결된 게이트웨이는 아웃바운드 통화를 처리하는 10초 이내에 알림을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9b52-178">The gateway associated with this trunk can give notification within 10 seconds that it is processing an outbound call.</span></span> <span data-ttu-id="d9b52-179">중재 서버에서 이 알림을 받지 못하면 다른 트렁크로 다시 로우트됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9b52-179">Rerouting to another trunk will occur if this notification is not received by the Mediation Server.</span></span> <span data-ttu-id="d9b52-180">대기 시간으로 인해 응답 시간이 지연되거나 게이트웨이가 응답하는 데 10초보다 오래 걸리는 네트워크에서는 빠른 장애 조치(failover)를 사용하지 않도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9b52-180">On networks where latency may delay the response time or the gateway takes longer than 10 seconds to respond, the fast failover should be disabled.</span></span>

14. <span data-ttu-id="d9b52-181">원하는 경우 트렁크에 대해 **호출 번호 변환 규칙** 을 연결 및 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="d9b52-181">(Optional) Associate and configure **calling number translation rules** for the trunk.</span></span> <span data-ttu-id="d9b52-182">이러한 변환 규칙은 아웃바운드 통화의 호출 번호에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9b52-182">These translation rules apply to the calling number for outbound calls</span></span>

    - <span data-ttu-id="d9b52-183">Enterprise Voice 배포에서 사용할 수 있는 모든 변환 규칙 목록에서 하나 이상의 규칙을 선택하려면 선택을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="d9b52-183">To choose one or more rules from a list of all translation rules that are available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="d9b52-184">**변환 규칙 선택** 에서 트렁크와 연결할 규칙을 클릭한 다음 **확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d9b52-184">In **Select Translation Rules**, click the rules that you want to associate with the trunk, and then click **OK**.</span></span>

    - <span data-ttu-id="d9b52-185">새 변환 규칙을 정의하고 트렁크와 연결하려면 **새로 만들기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d9b52-185">To define a new translation rule and associate it with the trunk, click **New**.</span></span> <span data-ttu-id="d9b52-186">변환 규칙에 대한 자세한 내용은 비즈니스용 [Skype 서버의 변환 규칙을 참조하세요.](../../plan-your-deployment/enterprise-voice-solution/translation-rules.md)</span><span class="sxs-lookup"><span data-stu-id="d9b52-186">For details about translation rules, see [Translation rules in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/translation-rules.md).</span></span>

    - <span data-ttu-id="d9b52-187">트렁크와 이미 연결된 변환 규칙을 편집하려면 규칙 이름을 클릭한 다음 **자세한 정보 표시** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d9b52-187">To edit a translation rule that is already associated with the trunk, click the rule name, and then click **Show details**.</span></span>

    - <span data-ttu-id="d9b52-188">기존 변환 규칙을 복사하여 새 규칙을 정의하는 시작 시점으로 사용하려면 규칙 이름을 클릭하고 **복사** 를 클릭한 다음 **붙여넣기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d9b52-188">To copy an existing translation rule to use as a starting point for defining a new rule, click the rule name and click **Copy**, and then click **Paste**.</span></span>

    - <span data-ttu-id="d9b52-189">트렁크에서 변환 규칙을 제거하려면 규칙 이름을 강조 표시하고 **제거** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d9b52-189">To remove a translation rule from the trunk, highlight the rule name and click **Remove**.</span></span>

      > [!CAUTION]
      > <span data-ttu-id="d9b52-190">연결된 트렁크 피어에서 변환 규칙을 구성한 경우에는 두 규칙이 충돌할 수 있으므로 변환 규칙을 트렁크와 연결하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="d9b52-190">Do not associate translation rules with a trunk if you have configured translation rules on the associated trunk peer, because the two rules might conflict.</span></span>

15. <span data-ttu-id="d9b52-p128">원하는 경우 트렁크에 대해 **호출된 번호 변환 규칙** 을 연결 및 구성합니다. 변환 규칙은 아웃바운드 통화의 호출된 번호에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9b52-p128">(Optional) Associate and configure **called number translation rules** for the trunk. The translation rules apply to the called number in an outbound call.</span></span>

    - <span data-ttu-id="d9b52-193">Enterprise Voice 배포에서 사용할 수 있는 모든 변환 규칙 목록에서 하나 이상의 규칙을 선택하려면 선택을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="d9b52-193">To choose one or more rules from a list of all translation rules that are available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="d9b52-194">**변환 규칙 선택** 에서 트렁크와 연결할 규칙을 클릭한 다음 **확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d9b52-194">In **Select Translation Rules**, click the rules that you want to associate with the trunk, and then click **OK**.</span></span>

    - <span data-ttu-id="d9b52-195">새 변환 규칙을 정의하고 트렁크와 연결하려면 **새로 만들기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d9b52-195">To define a new translation rule and associate it with the trunk, click **New**.</span></span> <span data-ttu-id="d9b52-196">변환 규칙에 대한 자세한 내용은 비즈니스용 [Skype 서버의 변환 규칙을 참조하세요.](../../plan-your-deployment/enterprise-voice-solution/translation-rules.md)</span><span class="sxs-lookup"><span data-stu-id="d9b52-196">For details about translation rules, see [Translation rules in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/translation-rules.md).</span></span>

    - <span data-ttu-id="d9b52-197">트렁크와 이미 연결된 변환 규칙을 편집하려면 규칙 이름을 클릭한 다음 **자세한 정보 표시** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d9b52-197">To edit a translation rule that is already associated with the trunk, click the rule name, and then click **Show details**.</span></span>

    - <span data-ttu-id="d9b52-198">기존 변환 규칙을 복사하여 새 규칙을 정의하는 시작 시점으로 사용하려면 규칙 이름을 클릭하고 **복사** 를 클릭한 다음 **붙여넣기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d9b52-198">To copy an existing translation rule to use as a starting point for defining a new rule, click the rule name and click **Copy**, and then click **Paste**.</span></span>

    - <span data-ttu-id="d9b52-199">트렁크에서 변환 규칙을 제거하려면 규칙 이름을 강조 표시하고 **제거** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d9b52-199">To remove a translation rule from the trunk, highlight the rule name and click **Remove**.</span></span>

      > [!CAUTION]
      > <span data-ttu-id="d9b52-200">연결된 트렁크 피어에서 변환 규칙을 구성한 경우에는 두 규칙이 충돌할 수 있으므로 변환 규칙을 트렁크와 연결하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="d9b52-200">Do not associate translation rules with a trunk if you have configured translation rules on the associated trunk peer, because the two rules might conflict.</span></span>

16. <span data-ttu-id="d9b52-201">트렁크의 변환 규칙이 올바른 순서로 정렬된지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="d9b52-201">Make sure that the trunk's translation rules are arranged in the correct order.</span></span> <span data-ttu-id="d9b52-202">목록에서 규칙의 위치를 변경하려면 규칙 이름을 강조 표시한 다음 위쪽 또는 아래쪽 화살표를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d9b52-202">To change a rule's position in the list, highlight the rule name, and then click the up or down arrow.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="d9b52-203">비즈니스용 Skype 서버는 위부터 변환 규칙 목록을 트래버스하고 전화 걸기 번호와 일치하는 첫 번째 규칙을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9b52-203">Skype for Business Server traverses the translation rule list from the top down and uses the first rule that matches the dialed number.</span></span> <span data-ttu-id="d9b52-204">전화를 건 번호가 둘 이상의 변환 규칙과 일치할 수 있도록 트렁크를 구성하는 경우에는 제약이 많은 규칙이 제약이 적은 규칙보다 위에 정렬되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9b52-204">If you configure a trunk so that a dialed number can match more than one translation rule, be sure that the more restrictive rules are sorted above the less restrictive rules.</span></span> <span data-ttu-id="d9b52-205">예를 들어 11자리 번호와 일치하는 변환 규칙과 +1425로 시작하는 11자리 번호만 일치하는 변환 규칙을 포함한 경우 11자리 번호와 일치하는 규칙이 보다 제한적인 규칙 아래에 정렬해야 합니다. </span><span class="sxs-lookup"><span data-stu-id="d9b52-205">For example, if you have included a translation rule that matches any 11-digit number and a translation rule that matches only 11-digit numbers that start with +1425, be sure that the rule that matches any 11-digit number is sorted  *below*  the more restrictive rule.</span></span>

17. <span data-ttu-id="d9b52-206">트렁크 구성을 마쳤으면 **확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d9b52-206">When you are finished configuring the trunk, click **OK**.</span></span>

18. <span data-ttu-id="d9b52-207">**트렁크 구성** 페이지에서 **커밋** 을 클릭하고 **모두 커밋** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d9b52-207">On the **Trunk Configuration** page, click **Commit**, and then click **Commit all**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d9b52-208">트렁크 구성을 만들거나 수정할 때는 항상 **모두 커밋** 명령을 실행하여 구성 변경 내용을 게시해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9b52-208">Whenever you create or modify a trunk configuration, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="d9b52-209">자세한 내용은 작업 설명서에서 [Publish pending changes to the voice routing configuration in Skype for Business를](voice-route-config-changes.md) 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="d9b52-209">For details, see [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation.</span></span>

## <a name="see-also"></a><span data-ttu-id="d9b52-210">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d9b52-210">See also</span></span>

[<span data-ttu-id="d9b52-211">비즈니스용 Skype 서버에서 미디어 우회를 통해 트렁크 구성</span><span class="sxs-lookup"><span data-stu-id="d9b52-211">Configure a trunk with media bypass in Skype for Business Server</span></span>](configure-trunk-with-media-bypass.md)

[<span data-ttu-id="d9b52-212">변환 규칙 정의</span><span class="sxs-lookup"><span data-stu-id="d9b52-212">Defining Translation Rules</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-defining-translation-rules)