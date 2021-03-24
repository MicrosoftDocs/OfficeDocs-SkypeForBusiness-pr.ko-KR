---
title: 비즈니스용 Skype 서버에서 미디어 우회를 통해 트렁크 구성
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
ms.assetid: 99d729ea-5a4c-4ff2-a4a3-93a24368da6d
description: '요약: 비즈니스용 Skype 서버에 대해 미디어 우회를 사용하도록 설정된 트렁크를 구성합니다. 이렇게 하면 SIP 트렁크 공급자가 중재 서버를 지원하고 있는 것으로 보아 중재 서버 수를 최소화할 수 있습니다.'
ms.openlocfilehash: 12f9abc49830e0af9c1934f4da56fe29be861114
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51106394"
---
# <a name="configure-a-trunk-with-media-bypass-in-skype-for-business-server"></a><span data-ttu-id="5abb9-104">비즈니스용 Skype 서버에서 미디어 우회를 통해 트렁크 구성</span><span class="sxs-lookup"><span data-stu-id="5abb9-104">Configure a trunk with media bypass in Skype for Business Server</span></span>

<span data-ttu-id="5abb9-105">**요약:** 비즈니스용 Skype 서버에 대해 미디어 우회를 사용하도록 설정된 트렁크를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="5abb9-105">**Summary:** Configure a trunk with media bypass enabled for Skype for Business Server.</span></span> <span data-ttu-id="5abb9-106">이렇게 하면 SIP 트렁크 공급자가 중재 서버를 지원하고 있는 것으로 보아 중재 서버 수를 최소화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5abb9-106">This will let you minimize the number of Mediation Servers, presuming your SIP trunk provider supports it.</span></span>

<span data-ttu-id="5abb9-107">다음 단계에 따라 미디어 우회가 사용하도록 설정된 트렁크를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="5abb9-107">Follow these steps to configure a trunk with media bypass enabled.</span></span> <span data-ttu-id="5abb9-108">미디어 우회를 사용하지 않도록 설정한 트렁크를 구성하기 위해 비즈니스용 Skype 서버에서 미디어 우회 없이 트렁크 [구성을 참조하세요.](configure-trunk-without-media-bypass.md)</span><span class="sxs-lookup"><span data-stu-id="5abb9-108">To configure a trunk with media bypass disabled, see [Configure a trunk without media bypass in Skype for Business Server](configure-trunk-without-media-bypass.md).</span></span>

<span data-ttu-id="5abb9-109">미디어 바이패스는 배포할 중재 서버 수를 최소화할 때 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="5abb9-109">Media bypass is useful when you want to minimize the number of Mediation Servers deployed.</span></span> <span data-ttu-id="5abb9-110">자세한 내용은 [비즈니스용 Skype의 미디어 우회 계획을 참조하세요.](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)</span><span class="sxs-lookup"><span data-stu-id="5abb9-110">For more information, see [Plan for media bypass in Skype for Business](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)</span></span>

<span data-ttu-id="5abb9-111">미디어 우회를 사용하도록 설정하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="5abb9-111">We strongly recommend that you enable media bypass.</span></span> <span data-ttu-id="5abb9-112">그러나 SIP 트렁크에서 미디어 우회를 사용하도록 설정하기 전에 적격 SIP 트렁크 공급자가 미디어 우회를 지원하고 시나리오를 성공적으로 사용하도록 설정하기 위한 요구 사항을 수용할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="5abb9-112">However, before you enable media bypass on a SIP trunk, confirm that your qualified SIP trunk provider supports media bypass and is able to accommodate the requirements for successfully enabling the scenario.</span></span> <span data-ttu-id="5abb9-113">특히 공급자는 조직의 내부 네트워크에 있는 서버의 IP 주소가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5abb9-113">Specifically, the provider must have the IP addresses of servers in your organization's internal network.</span></span>

> [!NOTE]
> <span data-ttu-id="5abb9-114">미디어 우회는 모든 PSTN(Public Switched Telephone Network) 게이트웨이, IP-PBX 및 SBC(Session Border Controller)와 상호 연결되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5abb9-114">Media bypass will not interoperate with every Public Switched Telephone Network (PSTN) gateway, IP-PBX, and Session Border Controller (SBC).</span></span> <span data-ttu-id="5abb9-115">Microsoft는 인증된 파트너와 함께 PSTN 게이트웨이 및 SBC 집합을 테스트했습니다.</span><span class="sxs-lookup"><span data-stu-id="5abb9-115">Microsoft has tested a set of PSTN gateways and SBCs with certified partners.</span></span> <span data-ttu-id="5abb9-116">미디어 우회는 비즈니스용 Skype 서버용 전화 통신 인프라 페이지에 나열된 제품 및 [버전에서만 지원됩니다.](../../../SfbPartnerCertification/certification/infra-gateways.md)</span><span class="sxs-lookup"><span data-stu-id="5abb9-116">Media bypass is supported only with products and versions that are listed on the [Telephony Infrastructure for Skype for Business Server](../../../SfbPartnerCertification/certification/infra-gateways.md) page.</span></span>

<span data-ttu-id="5abb9-117">아래에 설명된 트렁크 구성은 이 트렁크 구성에 할당된 트렁크에 적용되는 매개 변수 집합을 그룹화합니다.</span><span class="sxs-lookup"><span data-stu-id="5abb9-117">A trunk configuration as described below groups a set of parameters that are applied to trunks assigned this trunk configuration.</span></span> <span data-ttu-id="5abb9-118">특정 트렁크 구성의 범위를 전역으로(특정 사이트 또는 풀 구성을 포함하지 않는 모든 트렁크가 포함됨) 또는 사이트나 풀로 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5abb9-118">A particular trunk configuration can be scoped globally (to all trunks that do not have more specific site or pool configuration), or to a site, or to a pool.</span></span> <span data-ttu-id="5abb9-119">풀 수준 트렁크 구성은 특정 트렁크 구성의 범위를 단일 트렁크로 지정하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="5abb9-119">The pool-level trunk configuration is used to scope a specific trunk configuration to a single trunk.</span></span>

### <a name="to-configure-a-trunk-with-media-bypass"></a><span data-ttu-id="5abb9-120">미디어 우회를 통해 트렁크를 구성</span><span class="sxs-lookup"><span data-stu-id="5abb9-120">To configure a trunk with media bypass</span></span>

1. <span data-ttu-id="5abb9-121">비즈니스용 Skype 서버 제어판 열기</span><span class="sxs-lookup"><span data-stu-id="5abb9-121">Open Skype for Business Server Control Panel</span></span>

2. <span data-ttu-id="5abb9-122">왼쪽 탐색 모음에서 **음성 라우팅** 을 클릭한 다음 **트렁크 구성** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5abb9-122">In the left navigation bar, click **Voice Routing**, and then click **Trunk Configuration**.</span></span>

3. <span data-ttu-id="5abb9-123">**트렁크 구성** 페이지에서 다음 방법 중 하나를 사용하여 트렁크를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="5abb9-123">On the **Trunk Configuration** page, use one of the following methods to configure a trunk:</span></span>

   - <span data-ttu-id="5abb9-124">기존 트렁크(예: **전역** 트렁크)를 두 번 클릭하여 **트렁크 구성 편집** 대화 상자를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="5abb9-124">Double-click an existing trunk (for example, the **Global** trunk) to display the **Edit Trunk Configuration** dialog box.</span></span>

   - <span data-ttu-id="5abb9-125">**새로 만들기** 를 클릭한 다음 새 트렁크 구성의 범위를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5abb9-125">Click **New**, and then select a scope for the new trunk configuration:</span></span>

   - <span data-ttu-id="5abb9-126">**사이트 트렁크:** 사이트 선택에서 이 트렁크 구성에 대한 사이트를 선택하고 확인을 **클릭합니다.** </span><span class="sxs-lookup"><span data-stu-id="5abb9-126">**Site trunk**: Choose the site for this trunk configuration from **Select a Site**, and then click **OK**.</span></span> <span data-ttu-id="5abb9-127">트렁크 구성이 이미 만들어진 사이트는 **사이트 선택** 대화 상자에 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5abb9-127">Note that if a trunk configuration has already been created for a site, the site does not appear in **Select a Site**.</span></span> <span data-ttu-id="5abb9-128">이 트렁크 구성은 사이트의 모든 트렁크에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="5abb9-128">This trunk configuration will be applied to all trunks in the site.</span></span>

   - <span data-ttu-id="5abb9-129">**풀 트렁크:** 이 트렁크 구성이 적용되는 트렁크의 이름을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5abb9-129">**Pool trunk**: Choose the name of the trunk that this trunk configuration applies to.</span></span> <span data-ttu-id="5abb9-130">이 트렁크는 토폴로지 작성기에서 정의된 루트 트렁크 또는 추가 트렁크일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5abb9-130">This trunk can be the root trunk or any additional trunks defined in Topology Builder.</span></span> <span data-ttu-id="5abb9-131">서비스 **선택에서** 확인을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="5abb9-131">From **Select a Service**, click **OK**.</span></span> <span data-ttu-id="5abb9-132">트렁크 구성이 이미 만들어진 특정 트렁크는 **서비스 선택** 대화 상자에 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5abb9-132">Note that if a trunk configuration has already been created for a specific trunk, the trunk does not appear in **Select a Service**.</span></span>

      > [!NOTE]
      > <span data-ttu-id="5abb9-133">트렁크 구성 범위는 선택한 후에 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5abb9-133">After you select the scope of the trunk configuration, it cannot be changed.</span></span> <span data-ttu-id="5abb9-134">> 이름 필드에는 트렁크 구성의 연결된 사이트 또는 서비스의 이름이 미리 입력되어 있으며 변경할 수 없습니다. </span><span class="sxs-lookup"><span data-stu-id="5abb9-134">> The **Name** field is prepopulated with the name of the trunk configuration's associated site or service and cannot be changed.</span></span>

4. <span data-ttu-id="5abb9-135">지원되는 최대 초기 **대화 상자에서 값을 지정합니다.**</span><span class="sxs-lookup"><span data-stu-id="5abb9-135">Specify a value in **Maximum early dialogs supported**.</span></span> <span data-ttu-id="5abb9-136">PSTN(Public Switched Telephone Network) 게이트웨이, IP-PBX 또는 ITSP SBC(Session Border Controller)가 INVITE에 수신하여 중재 서버로 보낼 수 있는 최대 포크 응답 수입니다.</span><span class="sxs-lookup"><span data-stu-id="5abb9-136">This is the maximum number of forked responses a public switched telephone network (PSTN) gateway, IP-PBX, or ITSP Session Border Controller (SBC) can receive to an INVITE that it sent to the Mediation Server.</span></span> <span data-ttu-id="5abb9-137">기본값은 20입니다.</span><span class="sxs-lookup"><span data-stu-id="5abb9-137">The default value is 20.</span></span>

    > [!NOTE]
    > <span data-ttu-id="5abb9-138">이 값을 변경하기 전에 서비스 공급자나 장치 제조업체에 시스템 용량에 대한 자세한 내용을 문의하십시오.</span><span class="sxs-lookup"><span data-stu-id="5abb9-138">Before you change this value, consult your service provider or equipment manufacturer for details about the capabilities of your system.</span></span>

5. <span data-ttu-id="5abb9-139">다음 **암호화 지원 수준** 옵션 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5abb9-139">Select one of the following **Encryption support level** options:</span></span>

   - <span data-ttu-id="5abb9-140">**필수**: SRTP(Secure Real-Time Transport Protocol) 암호화를 사용하여 중재 서버와 게이트웨이 또는 PBX(Private Branch Exchange) 간의 트래픽을 보호해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5abb9-140">**Required**: Secure real-time transport protocol (SRTP) encryption must be used to help protect traffic between the Mediation Server and the gateway or private branch exchange (PBX).</span></span>

   - <span data-ttu-id="5abb9-141">**선택**: 서비스 공급자 또는 OEM에서 지원하는 경우 SRTP 암호화를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5abb9-141">**Optional**: SRTP encryption will be used if the service provider or equipment manufacturer supports it.</span></span>

   - <span data-ttu-id="5abb9-142">**지원되지 않음**: 서비스 공급자 또는 OEM에서 지원하지 않으므로 SRTP 암호화를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5abb9-142">**Not Supported**: SRTP encryption is not supported by the service provider or equipment manufacturer and therefore will not be used.</span></span>

6. <span data-ttu-id="5abb9-143">트렁크 피어가 처리하도록 미디어가 중재 서버를 바이패스하도록 하려면 **미디어 바이패스 사용** 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5abb9-143">Select the **Enable media bypass** check box if you want media to bypass the Mediation Server for processing by the trunk peer.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="5abb9-144">미디어 바이패스가 올바르게 작동하려면 PSTN 게이트웨이, IP-PBX 또는 ITSP 세션 경계 컨트롤러가 특정 기능을 지원해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5abb9-144">For media bypass to work successfully, the PSTN gateway, IP-PBX, or ITSP Session Border Controller must support certain capabilities.</span></span> <span data-ttu-id="5abb9-145">자세한 내용은 [비즈니스용 Skype의 미디어 우회 계획을 참조하세요.](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)</span><span class="sxs-lookup"><span data-stu-id="5abb9-145">For details, see [Plan for media bypass in Skype for Business](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).</span></span>

7. <span data-ttu-id="5abb9-p113">알려진 미디어 종료 지점(예: 미디어 종료 IP가 신호 종료 IP와 같은 PSTN 게이트웨이)이 있는 경우 **중앙 집중식 미디어 처리** 확인란을 선택합니다. 트렁크에 알려진 미디어 종료 지점이 없는 경우에는 이 확인란의 선택을 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="5abb9-p113">Select the **Centralized media processing** check box if there is a well-known media termination point (for example, a PSTN gateway where the media termination has the same IP as the signaling termination). Clear this check box if the trunk does not have a well-known media termination point.</span></span>

8. <span data-ttu-id="5abb9-148">트렁크 피어가 중재 서버에서 SIP REFER 요청 수신을 지원하는  경우 게이트웨이 참조 보내기 사용 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5abb9-148">If the trunk peer supports receiving SIP REFER requests from the Mediation Server, select the **Enable sending refer to the gateway** check box.</span></span>

    > [!NOTE]
    > <span data-ttu-id="5abb9-149">**미디어 바이패스 사용** 옵션을 선택한 상태에서 이 옵션을 사용하지 않도록 설정하면 추가 설정이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="5abb9-149">If you disable this option while the **Enable media bypass** option is selected, additional settings are required.</span></span> <span data-ttu-id="5abb9-150">트렁크 피어가 중재 서버로부터의 SIP REFER 요청 수신을 지원하지 않는데 미디어 바이패스를 사용하는 경우 미디어 바이패스에 대한 적절한 조건을 지원하기 위해 **Set-CsTrunkConfiguration** cmdlet도 실행하여 활성 및 대기 중인 통화에 대해 RTCP를 사용하지 않도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5abb9-150">If the trunk peer does not support receiving SIP REFER requests from the Mediation Server and media bypass is enabled, you must also run the **Set-CsTrunkConfiguration** cmdlet to disable RTCP for active and held calls in order to support proper conditions for media bypass.</span></span> <span data-ttu-id="5abb9-151">또는 전송된 통화를 미디어를 무시하고 게이트웨이가 SIP REFER 요청을 지원하지 않는 경우 타사 통화 제어를 사용하여 참조 사용을 선택할 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="5abb9-151">Alternatively, you can select **Enable refer using third-party-call control** if you want transferred calls to be media bypassed, and the gateway does not support SIP REFER requests.</span></span>

9. <span data-ttu-id="5abb9-152">원하는 경우 트렁크 간 라우팅을 사용하도록 설정하려면 PSTN 사용 레코드를 이 트렁크 구성에 연결하고 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="5abb9-152">(Optional) To enable inter-trunk routing, associate and configure PSTN usage records to this trunk configuration.</span></span> <span data-ttu-id="5abb9-153">이 트렁크 구성에 연결된 PSTN 사용은 비즈니스용 Skype 서버 끝점에서 시작되지 않는 트렁크를 통해 들어오는 모든 호출에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="5abb9-153">The PSTN usages associated to this trunk configuration will be applied for all incoming calls through the trunk that is not originating from a Skype for Business Server endpoint.</span></span> <span data-ttu-id="5abb9-154">트렁크 구성에 연결된 PSTN 사용 레코드를 관리하려면 다음 방법 중 하나를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5abb9-154">To manage PSTN usage records associated to a trunk configuration, use one of the following methods:</span></span>

   - <span data-ttu-id="5abb9-155">Enterprise Voice 배포에서 사용할 수 있는 모든 PSTN 사용 레코드 목록에서 하나 이상의 레코드를 선택하려면 선택을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="5abb9-155">To select one or more records from a list of all PSTN usage records available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="5abb9-156">이 트렁크 구성과 연결할 레코드를 강조 표시하고 **확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5abb9-156">Highlight the records you want to associate with this trunk configuration and then click **OK**.</span></span>

   - <span data-ttu-id="5abb9-157">이 트렁크 구성에서 PSTN 사용 레코드를 제거하려면 레코드를 강조 표시하고 **제거** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5abb9-157">To remove a PSTN usage record from this trunk configuration, select the record and click **Remove**.</span></span>

   - <span data-ttu-id="5abb9-158">새 PSTN 사용 레코드를 정의하고 이 트렁크 구성과 연결하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="5abb9-158">To define a new PSTN usage record and associate it with this trunk configuration, do the following:</span></span>

     <span data-ttu-id="5abb9-159">a.</span><span class="sxs-lookup"><span data-stu-id="5abb9-159">a.</span></span> <span data-ttu-id="5abb9-160">**새로 만들기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5abb9-160">Click **New**.</span></span>

     <span data-ttu-id="5abb9-161">b.</span><span class="sxs-lookup"><span data-stu-id="5abb9-161">b.</span></span> <span data-ttu-id="5abb9-162">**이름** 필드에서 레코드를 설명하는 고유한 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5abb9-162">In the **Name** field, specify a descriptive name for the record that is unique.</span></span>

     > [!NOTE]
     > <span data-ttu-id="5abb9-163">PSTN 사용 레코드 이름은 배포 Enterprise Voice 고유해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5abb9-163">The PSTN usage record name must be unique within the Enterprise Voice deployment.</span></span> <span data-ttu-id="5abb9-164">레코드를 저장한 후에는 **이름** 필드를 편집할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5abb9-164">After the record is saved, the **Name** field cannot be edited.</span></span>

     <span data-ttu-id="5abb9-165">c.</span><span class="sxs-lookup"><span data-stu-id="5abb9-165">c.</span></span> <span data-ttu-id="5abb9-166">다음 방법 중 하나를 사용하여 이 PSTN 사용 레코드에 대한 경로를 구성하고 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="5abb9-166">Use one of the following methods to associate and configure routes for this PSTN usage record:</span></span>

     - <span data-ttu-id="5abb9-167">Enterprise Voice 배포에서 사용 가능한 모든 경로 목록에서 하나 이상의 경로를 선택하려면 선택을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="5abb9-167">To select one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="5abb9-168">이 PSTN 사용 레코드와 연결할 경로를 강조 표시한 다음 **확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5abb9-168">Highlight the routes you want to associate with this PSTN usage record, and click **OK**.</span></span>

     - <span data-ttu-id="5abb9-169">PSTN 사용 레코드에서 경로를 제거하려면 경로를 선택하고 **제거** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5abb9-169">To remove a route from the PSTN usage record, select the route, and click **Remove**.</span></span>

   - <span data-ttu-id="5abb9-170">새 경로를 정의하고 이 PSTN 사용 레코드와 연결하려면 **새로 만들기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5abb9-170">To define a new route and associate it to this PSTN usage record, click **New**.</span></span> <span data-ttu-id="5abb9-171">자세한 내용은 비즈니스용 Skype에서 음성 경로 만들기 또는 [수정을 참조하세요.](create-or-modify-a-voice-route.md)</span><span class="sxs-lookup"><span data-stu-id="5abb9-171">For details, see [Create or modify a voice route in Skype for Business](create-or-modify-a-voice-route.md).</span></span>

     - <span data-ttu-id="5abb9-172">이 PSTN 사용 레코드에 연결된 경로를 편집하려면 경로를 선택하고 **자세한 정보 표시** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5abb9-172">To edit a route that is associated with this PSTN usage record, select the route, and click **Show details**.</span></span>

     <span data-ttu-id="5abb9-173">d.</span><span class="sxs-lookup"><span data-stu-id="5abb9-173">d.</span></span> <span data-ttu-id="5abb9-174">**확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5abb9-174">Click **OK**.</span></span>

     - <span data-ttu-id="5abb9-175">이 트렁크 구성에 이미 연결된 PSTN 사용 레코드를 편집하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="5abb9-175">To edit a PSTN usage record that is already associated with this trunk configuration, do the following:</span></span>

       <span data-ttu-id="5abb9-176">a.</span><span class="sxs-lookup"><span data-stu-id="5abb9-176">a.</span></span> <span data-ttu-id="5abb9-177">편집할 PSTN 사용 레코드를 선택하고 **자세한 정보 표시** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5abb9-177">Select the PSTN usage record you want to edit, and click **Show details**.</span></span>

       <span data-ttu-id="5abb9-178">b.</span><span class="sxs-lookup"><span data-stu-id="5abb9-178">b.</span></span> <span data-ttu-id="5abb9-179">다음 방법 중 하나를 사용하여 이 PSTN 사용 레코드에 대한 경로를 구성하고 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="5abb9-179">Use one of the following methods to associate and configure routes for this PSTN usage record:</span></span>

   - <span data-ttu-id="5abb9-180">Enterprise Voice 배포에서 사용 가능한 모든 경로 목록에서 하나 이상의 경로를 선택하려면 선택을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="5abb9-180">To select one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="5abb9-181">이 PSTN 사용 레코드와 연결할 경로를 강조 표시한 다음 **확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5abb9-181">Highlight the routes you want to associate with this PSTN usage record, and click **OK**.</span></span>

   - <span data-ttu-id="5abb9-182">PSTN 사용 레코드에서 경로를 제거하려면 경로를 선택하고 **제거** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5abb9-182">To remove a route from the PSTN usage record, select the route, and click **Remove**.</span></span>

   - <span data-ttu-id="5abb9-183">새 경로를 정의하고 이 PSTN 사용 레코드와 연결하려면 **새로 만들기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5abb9-183">To define a new route and associate it to this PSTN usage record, click **New**.</span></span> <span data-ttu-id="5abb9-184">자세한 내용은 비즈니스용 Skype에서 음성 경로 만들기 또는 [수정을 참조하세요.](create-or-modify-a-voice-route.md)</span><span class="sxs-lookup"><span data-stu-id="5abb9-184">For details, see [Create or modify a voice route in Skype for Business](create-or-modify-a-voice-route.md).</span></span>

   - <span data-ttu-id="5abb9-185">이 PSTN 사용 레코드에 연결된 경로를 편집하려면 경로를 선택하고 **자세한 정보 표시** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5abb9-185">To edit a route that is associated with this PSTN usage record, select the route, and click **Show details**.</span></span>

     <span data-ttu-id="5abb9-186">c.</span><span class="sxs-lookup"><span data-stu-id="5abb9-186">c.</span></span> <span data-ttu-id="5abb9-187">**확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5abb9-187">Click **OK**.</span></span>

     > [!IMPORTANT]
     > <span data-ttu-id="5abb9-188">구성되는 트렁크와 연결된 중재 서버 피어에 따라 PSTN 사용 레코드를 연결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5abb9-188">It is important to associate PSTN usage records according to the Mediation Server peer that is associated to the trunk being configured.</span></span> <span data-ttu-id="5abb9-189">중재 서버 피어가 PSTN 게이트웨이 또는 SBC(Session Border Controller)인 경우 트렁크 구성이 PSTN 대상 또는 비즈니스용 Skype 서버를 통해 연결된 다른 다운스트림 시스템으로 라우팅되는 PSTN 사용 레코드에 연결되지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="5abb9-189">If the Mediation Server peer is a PSTN gateway or a Session Border Controller (SBC), it is strongly recommended that the trunk configuration is not associated to a PSTN usage record that routes to a PSTN destination or any other downstream systems connected via Skype for Business Server.</span></span>

10. <span data-ttu-id="5abb9-190">최적의 성능을 유지하도록 PSTN 사용 레코드를 정렬합니다.</span><span class="sxs-lookup"><span data-stu-id="5abb9-190">Arrange the PSTN usage records for optimum performance.</span></span> <span data-ttu-id="5abb9-191">목록에서 레코드의 위치를 변경하려면 PSTN 사용 레코드를 선택하고 위쪽 또는 아래쪽 화살표를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5abb9-191">To change a record's position in the list, select the PSTN usage record, and click the up or down arrows.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="5abb9-192">PSTN 사용 레코드가 트렁크 구성에서 나열되는 순서가 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="5abb9-192">The order in which PSTN usage records are listed in the trunk configuration is significant.</span></span> <span data-ttu-id="5abb9-193">비즈니스용 Skype 서버는 목록을 위쪽에서 아래로 트래버스합니다.</span><span class="sxs-lookup"><span data-stu-id="5abb9-193">Skype for Business Server traverses the list from top to down.</span></span>

11. <span data-ttu-id="5abb9-194">NAT(Network Address Translation) 또는 방화벽 뒤에 있는 클라이언트와 래치 기능을 지원하는 SBC에 대해 미디어를 우회하도록 설정하려면 **RTP 래치** 사용이 선택되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5abb9-194">**Enable RTP Latching** should be selected to enable bypass media for clients behind a network address translation (NAT) or firewall and an SBC that supports latching.</span></span>

12. <span data-ttu-id="5abb9-195">**통화 기록 정보를** 중재 서버의 게이트웨이 피어로 보낼 수 있도록 설정하려면 전달 통화 기록 사용이 선택되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5abb9-195">**Enable forward call history** should be selected to enable sending of call history information to the gateway peer of the Mediation Server.</span></span>

13. <span data-ttu-id="5abb9-196">**PAI(P-Asserted-Identity)** 통화 발신자 정보를 중재 서버 쪽과 게이트웨이 쪽(또는 그 반대의 경우) 간에 전달할 수 있도록 설정하려면 P-Asserted-Identity 데이터를 전달하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5abb9-196">**Enable forward P-Asserted-Identity data** should be selected to enable the P-Asserted-Identity (PAI) call originator information to be forwarded between the Mediation Server side and gateway side (and vice versa), when present.</span></span>

14. <span data-ttu-id="5abb9-197">빠른 장애 조치(failover)를 사용하도록 설정하려면 **아웃바운드 라우팅 장애 조치(failover) 타이머 사용** 을 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5abb9-197">**Enable outbound routing failover timer** should be selected to enable fast failover.</span></span> <span data-ttu-id="5abb9-198">이 트렁크와 연결된 게이트웨이는 아웃바운드 통화를 처리하는 10초 이내에 알림을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5abb9-198">The gateway associated with this trunk can give notification within 10 seconds that it is processing an outbound call.</span></span> <span data-ttu-id="5abb9-199">중재 서버에서 이 알림을 받지 못하면 다른 트렁크로 다시 로우트됩니다.</span><span class="sxs-lookup"><span data-stu-id="5abb9-199">Rerouting to another trunk will occur if this notification is not received by the Mediation Server.</span></span> <span data-ttu-id="5abb9-200">대기 시간으로 인해 응답 시간이 지연되거나 게이트웨이가 응답하는 데 10초보다 오래 걸리는 네트워크에서는 빠른 장애 조치(failover)를 사용하지 않도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5abb9-200">On networks where latency may delay the response time or the gateway takes longer than 10 seconds to respond, the fast failover should be disabled.</span></span>

15. <span data-ttu-id="5abb9-201">원하는 경우 트렁크에 대해 **호출 번호 변환 규칙** 을 연결 및 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="5abb9-201">(Optional) Associate and configure **calling number translation rules** for the trunk.</span></span> <span data-ttu-id="5abb9-202">이러한 변환 규칙은 아웃바운드 통화의 호출 번호에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="5abb9-202">These translation rules apply to the calling number for outbound calls</span></span>

    - <span data-ttu-id="5abb9-203">Enterprise Voice 배포에서 사용할 수 있는 모든 변환 규칙 목록에서 하나 이상의 규칙을 선택하려면 선택을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="5abb9-203">To choose one or more rules from a list of all translation rules that are available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="5abb9-204">**변환 규칙 선택** 에서 트렁크와 연결할 규칙을 클릭한 다음 **확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5abb9-204">In **Select Translation Rules**, click the rules that you want to associate with the trunk, and then click **OK**.</span></span>

    - <span data-ttu-id="5abb9-205">새 변환 규칙을 정의하고 트렁크와 연결하려면 **새로 만들기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5abb9-205">To define a new translation rule and associate it with the trunk, click **New**.</span></span> <span data-ttu-id="5abb9-206">변환 규칙에 대한 자세한 내용은 비즈니스용 [Skype 서버의 변환 규칙을 참조하세요.](../../plan-your-deployment/enterprise-voice-solution/translation-rules.md)</span><span class="sxs-lookup"><span data-stu-id="5abb9-206">For details about translation rules, see [Translation rules in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/translation-rules.md).</span></span>

    - <span data-ttu-id="5abb9-207">트렁크와 이미 연결된 변환 규칙을 편집하려면 규칙 이름을 클릭한 다음 **자세한 정보 표시** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5abb9-207">To edit a translation rule that is already associated with the trunk, click the rule name, and then click **Show details**.</span></span>

    - <span data-ttu-id="5abb9-208">기존 변환 규칙을 복사하여 새 규칙을 정의하는 시작 시점으로 사용하려면 규칙 이름을 클릭하고 **복사** 를 클릭한 다음 **붙여넣기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5abb9-208">To copy an existing translation rule to use as a starting point for defining a new rule, click the rule name and click **Copy**, and then click **Paste**.</span></span>

    - <span data-ttu-id="5abb9-209">트렁크에서 변환 규칙을 제거하려면 규칙 이름을 강조 표시하고 **제거** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5abb9-209">To remove a translation rule from the trunk, highlight the rule name and click **Remove**.</span></span>

    > [!CAUTION]
    > <span data-ttu-id="5abb9-210">연결된 트렁크 피어에서 변환 규칙을 구성한 경우에는 두 규칙이 충돌할 수 있으므로 변환 규칙을 트렁크와 연결하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="5abb9-210">Do not associate translation rules with a trunk if you have configured translation rules on the associated trunk peer, because the two rules might conflict.</span></span>

16. <span data-ttu-id="5abb9-p136">원하는 경우 트렁크에 대해 **호출된 번호 변환 규칙** 을 연결 및 구성합니다. 변환 규칙은 아웃바운드 통화의 호출된 번호에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="5abb9-p136">(Optional) Associate and configure **called number translation rules** for the trunk. The translation rules apply to the called number in an outbound call.</span></span>

    - <span data-ttu-id="5abb9-213">Enterprise Voice 배포에서 사용할 수 있는 모든 변환 규칙 목록에서 하나 이상의 규칙을 선택하려면 선택을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="5abb9-213">To choose one or more rules from a list of all translation rules that are available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="5abb9-214">**변환 규칙 선택** 에서 트렁크와 연결할 규칙을 클릭한 다음 **확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5abb9-214">In **Select Translation Rules**, click the rules that you want to associate with the trunk, and then click **OK**.</span></span>

    - <span data-ttu-id="5abb9-215">새 변환 규칙을 정의하고 트렁크와 연결하려면 **새로 만들기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5abb9-215">To define a new translation rule and associate it with the trunk, click **New**.</span></span> <span data-ttu-id="5abb9-216">변환 규칙에 대한 자세한 내용은 비즈니스용 [Skype 서버의 변환 규칙을 참조하세요.](../../plan-your-deployment/enterprise-voice-solution/translation-rules.md)</span><span class="sxs-lookup"><span data-stu-id="5abb9-216">For details about translation rules, see [Translation rules in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/translation-rules.md).</span></span>

    - <span data-ttu-id="5abb9-217">트렁크와 이미 연결된 변환 규칙을 편집하려면 규칙 이름을 클릭한 다음 **자세한 정보 표시** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5abb9-217">To edit a translation rule that is already associated with the trunk, click the rule name, and then click **Show details**.</span></span>

    - <span data-ttu-id="5abb9-218">기존 변환 규칙을 복사하여 새 규칙을 정의하는 시작 시점으로 사용하려면 규칙 이름을 클릭하고 **복사** 를 클릭한 다음 **붙여넣기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5abb9-218">To copy an existing translation rule to use as a starting point for defining a new rule, click the rule name and click **Copy**, and then click **Paste**.</span></span>

    - <span data-ttu-id="5abb9-219">트렁크에서 변환 규칙을 제거하려면 규칙 이름을 강조 표시하고 **제거** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5abb9-219">To remove a translation rule from the trunk, highlight the rule name and click **Remove**.</span></span>

    > [!CAUTION]
    > <span data-ttu-id="5abb9-220">연결된 트렁크 피어에서 변환 규칙을 구성한 경우에는 두 규칙이 충돌할 수 있으므로 변환 규칙을 트렁크와 연결하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="5abb9-220">Do not associate translation rules with a trunk if you have configured translation rules on the associated trunk peer, because the two rules might conflict.</span></span>

17. <span data-ttu-id="5abb9-221">트렁크의 변환 규칙이 올바른 순서로 정렬된지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="5abb9-221">Make sure that the trunk's translation rules are arranged in the correct order.</span></span> <span data-ttu-id="5abb9-222">목록에서 규칙의 위치를 변경하려면 규칙 이름을 강조 표시한 다음 위쪽 또는 아래쪽 화살표를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5abb9-222">To change a rule's position in the list, highlight the rule name and then click the up or down arrow.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="5abb9-223">비즈니스용 Skype 서버는 위부터 변환 규칙 목록을 트래버스하고 전화 걸기 번호와 일치하는 첫 번째 규칙을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5abb9-223">Skype for Business Server traverses the translation rule list from the top down and uses the first rule that matches the dialed number.</span></span> <span data-ttu-id="5abb9-224">전화를 건 번호가 둘 이상의 변환 규칙과 일치할 수 있도록 트렁크를 구성하는 경우에는 제약이 많은 규칙이 제약이 적은 규칙보다 위에 정렬되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5abb9-224">If you configure a trunk so that a dialed number can match more than one translation rule, be sure that the more restrictive rules are sorted above the less restrictive rules.</span></span> <span data-ttu-id="5abb9-225">예를 들어 11자리 번호와 일치하는 변환 규칙과 +1425로 시작하는 11자리 번호만 일치하는 변환 규칙을 포함한 경우 11자리 번호와 일치하는 규칙이 보다 제한적인 규칙 아래에 정렬해야 합니다. </span><span class="sxs-lookup"><span data-stu-id="5abb9-225">For example, if you have included a translation rule that matches any 11-digit number and a translation rule that matches only 11-digit numbers that start with +1425, be sure that the rule that matches any 11-digit number is sorted  *below*  the more restrictive rule.</span></span>

18. <span data-ttu-id="5abb9-226">트렁크 구성을 마쳤으면 **확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5abb9-226">When you are finished configuring the trunk, click **OK**.</span></span>

19. <span data-ttu-id="5abb9-227">**트렁크 구성** 페이지에서 **커밋** 을 클릭하고 **모두 커밋** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5abb9-227">On the **Trunk Configuration** page, click **Commit**, and then click **Commit all**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="5abb9-228">트렁크 구성을 만들거나 수정할 때는 항상 **모두 커밋** 명령을 실행하여 구성 변경 내용을 게시해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5abb9-228">Whenever you create or modify a trunk configuration, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="5abb9-229">자세한 내용은 작업 설명서에서 [Publish pending changes to the voice routing configuration in Skype for Business를](voice-route-config-changes.md) 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="5abb9-229">For details, see [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation.</span></span>

<span data-ttu-id="5abb9-230">트렁크를 구성한 후 배포 설명서의 [Deploy media bypass in Skype for Business Server에](deploy-media-bypass.md) 설명된 바와 같이 전역 미디어 우회 옵션 중 선택하여 미디어 우회를 계속 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="5abb9-230">After you have configured the trunk, continue configuring media bypass by choosing between global media bypass options, as described in [Deploy media bypass in Skype for Business Server](deploy-media-bypass.md) in the Deployment documentation.</span></span>
## <a name="see-also"></a><span data-ttu-id="5abb9-231">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5abb9-231">See also</span></span>

[<span data-ttu-id="5abb9-232">비즈니스용 Skype 서버에서 미디어 우회 없이 트렁크 구성</span><span class="sxs-lookup"><span data-stu-id="5abb9-232">Configure a trunk without media bypass in Skype for Business Server</span></span>](configure-trunk-without-media-bypass.md)

[<span data-ttu-id="5abb9-233">비즈니스용 Skype 서버에서 미디어 우회 배포</span><span class="sxs-lookup"><span data-stu-id="5abb9-233">Deploy media bypass in Skype for Business Server</span></span>](deploy-media-bypass.md)

[<span data-ttu-id="5abb9-234">변환 규칙 정의</span><span class="sxs-lookup"><span data-stu-id="5abb9-234">Defining Translation Rules</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-defining-translation-rules)

[<span data-ttu-id="5abb9-235">미디어 우회 구성</span><span class="sxs-lookup"><span data-stu-id="5abb9-235">Configure Media Bypass</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-configure-media-bypass)