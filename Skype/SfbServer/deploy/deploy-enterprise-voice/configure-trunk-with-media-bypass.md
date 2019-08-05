---
title: 비즈니스용 Skype 서버에서 미디어 바이패스를 사용 하 여 트렁크 구성
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 99d729ea-5a4c-4ff2-a4a3-93a24368da6d
description: '요약: 비즈니스용 Skype 서버용으로 미디어 바이패스를 사용 하도록 설정 된 트렁크를 구성 합니다. 이렇게 하면 SIP 트렁크 공급자가 지 원하는 중재 서버 수를 최소화할 수 있습니다.'
ms.openlocfilehash: 29fd1d4e978306f58e99b4a75cb5255863139888
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36191364"
---
# <a name="configure-a-trunk-with-media-bypass-in-skype-for-business-server"></a><span data-ttu-id="5e0a4-104">비즈니스용 Skype 서버에서 미디어 바이패스를 사용 하 여 트렁크 구성</span><span class="sxs-lookup"><span data-stu-id="5e0a4-104">Configure a trunk with media bypass in Skype for Business Server</span></span>

<span data-ttu-id="5e0a4-105">**요약:** 비즈니스용 Skype 서버용으로 미디어 바이패스를 사용 하도록 설정 된 트렁크를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e0a4-105">**Summary:** Configure a trunk with media bypass enabled for Skype for Business Server.</span></span> <span data-ttu-id="5e0a4-106">이렇게 하면 SIP 트렁크 공급자가 지 원하는 중재 서버 수를 최소화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e0a4-106">This will let you minimize the number of Mediation Servers, presuming your SIP trunk provider supports it.</span></span>

<span data-ttu-id="5e0a4-107">미디어 바이패스를 사용 하도록 설정 된 트렁크를 구성 하려면 다음 단계를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="5e0a4-107">Follow these steps to configure a trunk with media bypass enabled.</span></span> <span data-ttu-id="5e0a4-108">미디어 바이패스를 사용 하지 않도록 설정 된 트렁크를 구성 하려면 비즈니스용 [Skype 서버에서 미디어 바이패스 없이 트렁크 구성을](configure-trunk-without-media-bypass.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5e0a4-108">To configure a trunk with media bypass disabled, see [Configure a trunk without media bypass in Skype for Business Server](configure-trunk-without-media-bypass.md).</span></span>

<span data-ttu-id="5e0a4-109">미디어 바이패스는 배포 된 중재 서버 수를 최소화 하려는 경우에 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e0a4-109">Media bypass is useful when you want to minimize the number of Mediation Servers deployed.</span></span> <span data-ttu-id="5e0a4-110">자세한 내용은 [비즈니스용 Skype의 미디어 바이패스 계획](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5e0a4-110">For more information, see [Plan for media bypass in Skype for Business](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)</span></span>

<span data-ttu-id="5e0a4-111">미디어 바이패스를 사용 하도록 설정 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="5e0a4-111">We strongly recommend that you enable media bypass.</span></span> <span data-ttu-id="5e0a4-112">그러나 SIP 트렁크에서 미디어 바이패스를 사용 하도록 설정 하기 전에, 자격 있는 SIP 트렁크 공급자가 미디어 바이패스를 지원 하 고 시나리오를 성공적으로 사용 하는 데 필요한 요구 사항을 수용할 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e0a4-112">However, before you enable media bypass on a SIP trunk, confirm that your qualified SIP trunk provider supports media bypass and is able to accommodate the requirements for successfully enabling the scenario.</span></span> <span data-ttu-id="5e0a4-113">특히 공급자는 조직의 내부 네트워크에 있는 서버의 IP 주소를가지고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e0a4-113">Specifically, the provider must have the IP addresses of servers in your organization's internal network.</span></span>

> [!NOTE]
> <span data-ttu-id="5e0a4-114">미디어 바이패스는 모든 공공 교환 통신 네트워크 (PSTN) 게이트웨이, IP-PBX 및 세션 경계 컨트롤러 (SBC)와 상호 작용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5e0a4-114">Media bypass will not interoperate with every Public Switched Telephone Network (PSTN) gateway, IP-PBX, and Session Border Controller (SBC).</span></span> <span data-ttu-id="5e0a4-115">Microsoft는 인증 된 파트너와 함께 PSTN 게이트웨이 및 SBCs 집합을 테스트 했습니다.</span><span class="sxs-lookup"><span data-stu-id="5e0a4-115">Microsoft has tested a set of PSTN gateways and SBCs with certified partners.</span></span> <span data-ttu-id="5e0a4-116">미디어 바이패스는 [비즈니스용 Skype Server 용 전화 통신 인프라](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways) 페이지에 나열 된 제품 및 버전 에서만 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5e0a4-116">Media bypass is supported only with products and versions that are listed on the [Telephony Infrastructure for Skype for Business Server](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways) page.</span></span>

<span data-ttu-id="5e0a4-117">아래 설명 된 바와 같이 트렁크 구성은이 트렁크 구성을 할당 한 trunks에 적용 되는 매개 변수 집합을 그룹화 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e0a4-117">A trunk configuration as described below groups a set of parameters that are applied to trunks assigned this trunk configuration.</span></span> <span data-ttu-id="5e0a4-118">특정 트렁크 구성에는 전역 (특정 사이트 또는 풀 구성이 없는 모든 trunks) 또는 사이트 또는 풀에 대해 범위를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e0a4-118">A particular trunk configuration can be scoped globally (to all trunks that do not have more specific site or pool configuration), or to a site, or to a pool.</span></span> <span data-ttu-id="5e0a4-119">풀 수준의 트렁크 구성은 특정 트렁크 구성의 범위를 단일 트렁크로 지정 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5e0a4-119">The pool-level trunk configuration is used to scope a specific trunk configuration to a single trunk.</span></span>

### <a name="to-configure-a-trunk-with-media-bypass"></a><span data-ttu-id="5e0a4-120">미디어 바이패스를 사용 하 여 트렁크 구성</span><span class="sxs-lookup"><span data-stu-id="5e0a4-120">To configure a trunk with media bypass</span></span>

1. <span data-ttu-id="5e0a4-121">비즈니스용 Skype Server 제어판 열기</span><span class="sxs-lookup"><span data-stu-id="5e0a4-121">Open Skype for Business Server Control Panel</span></span>

2. <span data-ttu-id="5e0a4-122">왼쪽 탐색 모음에서 **음성 라우팅을**클릭 한 다음 **트렁크 구성을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e0a4-122">In the left navigation bar, click **Voice Routing**, and then click **Trunk Configuration**.</span></span>

3. <span data-ttu-id="5e0a4-123">**트렁크 구성** 페이지에서 다음 방법 중 하나를 사용 하 여 트렁크를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e0a4-123">On the **Trunk Configuration** page, use one of the following methods to configure a trunk:</span></span>

   - <span data-ttu-id="5e0a4-124">기존 트렁크 (예: **전역** 트렁크)를 두 번 클릭 하 여 **트렁크 구성 편집** 대화 상자를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e0a4-124">Double-click an existing trunk (for example, the **Global** trunk) to display the **Edit Trunk Configuration** dialog box.</span></span>

   - <span data-ttu-id="5e0a4-125">**새로 만들기**를 클릭 한 다음 새 트렁크 구성의 범위를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e0a4-125">Click **New**, and then select a scope for the new trunk configuration:</span></span>

   - <span data-ttu-id="5e0a4-126">**사이트 트렁크**: **사이트 선택**에서이 트렁크 구성에 대 한 사이트를 선택 하 고 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e0a4-126">**Site trunk**: Choose the site for this trunk configuration from **Select a Site**, and then click **OK**.</span></span> <span data-ttu-id="5e0a4-127">사이트에 트렁크 구성을 이미 만든 경우 사이트 **선택**에 해당 사이트가 나타나지 않는다는 점에 유의 하세요.</span><span class="sxs-lookup"><span data-stu-id="5e0a4-127">Note that if a trunk configuration has already been created for a site, the site does not appear in **Select a Site**.</span></span> <span data-ttu-id="5e0a4-128">이 트렁크 구성은 사이트의 모든 trunks에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5e0a4-128">This trunk configuration will be applied to all trunks in the site.</span></span>

   - <span data-ttu-id="5e0a4-129">**풀 트렁크**:이 트렁크 구성이 적용 되는 트렁크의 이름을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e0a4-129">**Pool trunk**: Choose the name of the trunk that this trunk configuration applies to.</span></span> <span data-ttu-id="5e0a4-130">이 트렁크는 루트 트렁크 또는 토폴로지 작성기에 정의 된 추가 trunks 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e0a4-130">This trunk can be the root trunk or any additional trunks defined in Topology Builder.</span></span> <span data-ttu-id="5e0a4-131">**서비스 선택**에서 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e0a4-131">From **Select a Service**, click **OK**.</span></span> <span data-ttu-id="5e0a4-132">트렁크 구성은 특정 트렁크에 대해 이미 만든 경우 **서비스 선택**에 트렁크가 표시 되지 않는다는 점에 유의 하세요.</span><span class="sxs-lookup"><span data-stu-id="5e0a4-132">Note that if a trunk configuration has already been created for a specific trunk, the trunk does not appear in **Select a Service**.</span></span>

      > [!NOTE]
      > <span data-ttu-id="5e0a4-133">트렁크 구성의 범위를 선택한 후에는 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5e0a4-133">After you select the scope of the trunk configuration, it cannot be changed.</span></span> <span data-ttu-id="5e0a4-134">> **이름** 필드가 트렁크 구성의 연결 된 사이트 또는 서비스의 이름으로 미리 채워져 있으므로 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5e0a4-134">> The **Name** field is prepopulated with the name of the trunk configuration's associated site or service and cannot be changed.</span></span>

4. <span data-ttu-id="5e0a4-135">**최대 초기 대화 상자에서 지원 되**는 값을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e0a4-135">Specify a value in **Maximum early dialogs supported**.</span></span> <span data-ttu-id="5e0a4-136">이는 분기 응답의 최대 수입니다. PSTN (공개 통신 네트워크) 게이트웨이, IP-PBX 또는 ITSP 세션 경계 컨트롤러 (SBC)는 중재 서버에 보낸 초대에 대해 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e0a4-136">This is the maximum number of forked responses a public switched telephone network (PSTN) gateway, IP-PBX, or ITSP Session Border Controller (SBC) can receive to an INVITE that it sent to the Mediation Server.</span></span> <span data-ttu-id="5e0a4-137">기본값은 20입니다.</span><span class="sxs-lookup"><span data-stu-id="5e0a4-137">The default value is 20.</span></span>

    > [!NOTE]
    > <span data-ttu-id="5e0a4-138">이 값을 변경 하기 전에 서비스 공급자나 장비 제조업체에 문의 하 여 시스템의 기능에 대 한 세부 정보를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e0a4-138">Before you change this value, consult your service provider or equipment manufacturer for details about the capabilities of your system.</span></span>

5. <span data-ttu-id="5e0a4-139">다음 **암호화 지원 수준** 옵션 중 하나를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e0a4-139">Select one of the following **Encryption support level** options:</span></span>

   - <span data-ttu-id="5e0a4-140">**필수**: 중재 서버와 게이트웨이 또는 개인 분기 교환 (PBX) 간의 트래픽을 보호 하려면 보안 실시간 전송 프로토콜 (SRTP) 암호화를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e0a4-140">**Required**: Secure real-time transport protocol (SRTP) encryption must be used to help protect traffic between the Mediation Server and the gateway or private branch exchange (PBX).</span></span>

   - <span data-ttu-id="5e0a4-141">**선택 사항**: 서비스 공급자 또는 장비 제조업체가 SRTP 암호화를 지 원하는 경우 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5e0a4-141">**Optional**: SRTP encryption will be used if the service provider or equipment manufacturer supports it.</span></span>

   - <span data-ttu-id="5e0a4-142">**지원 되지 않음**: SRTP 암호화는 서비스 공급자 또는 장비 제조업체에서 지원 하지 않으므로 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5e0a4-142">**Not Supported**: SRTP encryption is not supported by the service provider or equipment manufacturer and therefore will not be used.</span></span>

6. <span data-ttu-id="5e0a4-143">미디어를 사용 하 여 트렁크 피어가 처리 하기 위해 중재 서버를 우회 하 게 하려면 **미디어 무시 사용** 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e0a4-143">Select the **Enable media bypass** check box if you want media to bypass the Mediation Server for processing by the trunk peer.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="5e0a4-144">Media bypass이 제대로 작동 하려면 PSTN 게이트웨이, IP-PBX 또는 ITSP 세션 경계 컨트롤러가 특정 기능을 지원 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e0a4-144">For media bypass to work successfully, the PSTN gateway, IP-PBX, or ITSP Session Border Controller must support certain capabilities.</span></span> <span data-ttu-id="5e0a4-145">자세한 내용은 [비즈니스용 Skype의 미디어 바이패스 계획](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5e0a4-145">For details, see [Plan for media bypass in Skype for Business](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).</span></span>

7. <span data-ttu-id="5e0a4-146">적절 하 게 알려진 미디어 종료 지점 (예: 미디어 종료의 IP와 신호 종료와 동일한 IP를 가진 PSTN 게이트웨이)이 있는 경우 **중앙 집중화 된 미디어 처리** 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e0a4-146">Select the **Centralized media processing** check box if there is a well-known media termination point (for example, a PSTN gateway where the media termination has the same IP as the signaling termination).</span></span> <span data-ttu-id="5e0a4-147">트렁크에 잘 알려진 미디어 종료 지점이 없는 경우이 확인란의 선택을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e0a4-147">Clear this check box if the trunk does not have a well-known media termination point.</span></span>

8. <span data-ttu-id="5e0a4-148">트렁크 피어가 조정 서버의 SIP 수신 요청을 지원 하면 **게이트웨이를 참조로 보내기를 사용** 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e0a4-148">If the trunk peer supports receiving SIP REFER requests from the Mediation Server, select the **Enable sending refer to the gateway** check box.</span></span>

    > [!NOTE]
    > <span data-ttu-id="5e0a4-149">**미디어 무시 사용** 옵션을 선택 하 고이 옵션을 사용 하지 않도록 설정 하면 추가 설정이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e0a4-149">If you disable this option while the **Enable media bypass** option is selected, additional settings are required.</span></span> <span data-ttu-id="5e0a4-150">트렁크 피어가 SIP 받기를 지원 하지 않는 경우 중재 서버의 요청을 참조 하 고 미디어 바이패스를 사용 하도록 설정 하는 경우 **set-cstrunkconfiguration** cmdlet을 실행 하 여 RTCP에 대 한 적절 한 조건을 지원 하기 위해 활성 및 보유 통화를 비활성화 해야 합니다. 미디어 바이패스.</span><span class="sxs-lookup"><span data-stu-id="5e0a4-150">If the trunk peer does not support receiving SIP REFER requests from the Mediation Server and media bypass is enabled, you must also run the **Set-CsTrunkConfiguration** cmdlet to disable RTCP for active and held calls in order to support proper conditions for media bypass.</span></span> <span data-ttu-id="5e0a4-151">또는 **타사 통화 제어를 사용 하 여 사용** 을 선택할 수 있으며,이 경우 게이트웨이는 SIP 참조 요청을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5e0a4-151">Alternatively, you can select **Enable refer using third-party-call control** if you want transferred calls to be media bypassed, and the gateway does not support SIP REFER requests.</span></span>

9. <span data-ttu-id="5e0a4-152">) 트렁크 간 라우팅을 사용 하도록 설정 하려면 PSTN 사용 레코드를이 트렁크 구성에 연결 하 고 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e0a4-152">(Optional) To enable inter-trunk routing, associate and configure PSTN usage records to this trunk configuration.</span></span> <span data-ttu-id="5e0a4-153">이 트렁크 구성에 연결 된 PSTN 사용은 비즈니스용 Skype 서버 끝점에서 시작 되지 않는 트렁크를 통해 들어오는 모든 통화에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5e0a4-153">The PSTN usages associated to this trunk configuration will be applied for all incoming calls through the trunk that is not originating from a Skype for Business Server endpoint.</span></span> <span data-ttu-id="5e0a4-154">트렁크 구성에 연결 된 PSTN 사용 레코드를 관리 하려면 다음 방법 중 하나를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e0a4-154">To manage PSTN usage records associated to a trunk configuration, use one of the following methods:</span></span>

   - <span data-ttu-id="5e0a4-155">엔터프라이즈 음성 배포에서 사용할 수 있는 모든 PSTN 사용 레코드 목록에서 하나 이상의 레코드를 선택 하려면 **선택을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e0a4-155">To select one or more records from a list of all PSTN usage records available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="5e0a4-156">이 트렁크 구성과 연결 하려는 레코드를 강조 표시 한 다음 **확인을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e0a4-156">Highlight the records you want to associate with this trunk configuration and then click **OK**.</span></span>

   - <span data-ttu-id="5e0a4-157">이 트렁크 구성에서 PSTN 사용 레코드를 제거 하려면 해당 레코드를 선택 하 고 **제거**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e0a4-157">To remove a PSTN usage record from this trunk configuration, select the record and click **Remove**.</span></span>

   - <span data-ttu-id="5e0a4-158">새 PSTN 사용 레코드를 정의 하 고이를이 트렁크 구성에 연결 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e0a4-158">To define a new PSTN usage record and associate it with this trunk configuration, do the following:</span></span>

     <span data-ttu-id="5e0a4-159">에서.</span><span class="sxs-lookup"><span data-stu-id="5e0a4-159">a.</span></span> <span data-ttu-id="5e0a4-160">**새로 만들기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e0a4-160">Click **New**.</span></span>

     <span data-ttu-id="5e0a4-161">b.</span><span class="sxs-lookup"><span data-stu-id="5e0a4-161">b.</span></span> <span data-ttu-id="5e0a4-162">**이름** 필드에서 고유한 레코드의 설명적인 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e0a4-162">In the **Name** field, specify a descriptive name for the record that is unique.</span></span>

     > [!NOTE]
     > <span data-ttu-id="5e0a4-163">PSTN 사용 레코드 이름은 엔터프라이즈 음성 배포 내에서 고유 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e0a4-163">The PSTN usage record name must be unique within the Enterprise Voice deployment.</span></span> <span data-ttu-id="5e0a4-164">레코드가 저장 된 후에는 **이름** 필드를 편집할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5e0a4-164">After the record is saved, the **Name** field cannot be edited.</span></span>

     <span data-ttu-id="5e0a4-165">c.</span><span class="sxs-lookup"><span data-stu-id="5e0a4-165">c.</span></span> <span data-ttu-id="5e0a4-166">다음 방법 중 하나를 사용 하 여이 PSTN 사용 레코드에 대 한 경로를 연결 하 고 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e0a4-166">Use one of the following methods to associate and configure routes for this PSTN usage record:</span></span>

     - <span data-ttu-id="5e0a4-167">엔터프라이즈 음성 배포에서 사용할 수 있는 모든 경로 목록에 있는 경로를 하나 이상 선택 하려면 **선택을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e0a4-167">To select one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="5e0a4-168">이 PSTN 사용 레코드와 연결 하려는 경로를 강조 표시 하 고 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e0a4-168">Highlight the routes you want to associate with this PSTN usage record, and click **OK**.</span></span>

     - <span data-ttu-id="5e0a4-169">PSTN 사용 레코드에서 경로를 제거 하려면 해당 경로를 선택 하 고 **제거**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e0a4-169">To remove a route from the PSTN usage record, select the route, and click **Remove**.</span></span>

   - <span data-ttu-id="5e0a4-170">새 경로를 정의 하 고이 PSTN 사용 레코드에 연결 하려면 **새로 만들기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e0a4-170">To define a new route and associate it to this PSTN usage record, click **New**.</span></span> <span data-ttu-id="5e0a4-171">자세한 내용은 [비즈니스용 Skype에서 음성 경로 만들기 또는 수정을](create-or-modify-a-voice-route.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5e0a4-171">For details, see [Create or modify a voice route in Skype for Business](create-or-modify-a-voice-route.md).</span></span>

     - <span data-ttu-id="5e0a4-172">이 PSTN 사용 레코드와 연결 된 경로를 편집 하려면 해당 경로를 선택 하 고 **세부 정보 표시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e0a4-172">To edit a route that is associated with this PSTN usage record, select the route, and click **Show details**.</span></span>

     <span data-ttu-id="5e0a4-173">a.</span><span class="sxs-lookup"><span data-stu-id="5e0a4-173">d.</span></span> <span data-ttu-id="5e0a4-174">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5e0a4-174">Click **OK**.</span></span>

     - <span data-ttu-id="5e0a4-175">이 트렁크 구성과 이미 연결 된 PSTN 사용 레코드를 편집 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e0a4-175">To edit a PSTN usage record that is already associated with this trunk configuration, do the following:</span></span>

       <span data-ttu-id="5e0a4-176">에서.</span><span class="sxs-lookup"><span data-stu-id="5e0a4-176">a.</span></span> <span data-ttu-id="5e0a4-177">편집 하려는 PSTN 사용 레코드를 선택 하 고 **세부 정보 표시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e0a4-177">Select the PSTN usage record you want to edit, and click **Show details**.</span></span>

       <span data-ttu-id="5e0a4-178">b.</span><span class="sxs-lookup"><span data-stu-id="5e0a4-178">b.</span></span> <span data-ttu-id="5e0a4-179">다음 방법 중 하나를 사용 하 여이 PSTN 사용 레코드에 대 한 경로를 연결 하 고 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e0a4-179">Use one of the following methods to associate and configure routes for this PSTN usage record:</span></span>

   - <span data-ttu-id="5e0a4-180">엔터프라이즈 음성 배포에서 사용할 수 있는 모든 경로 목록에 있는 경로를 하나 이상 선택 하려면 **선택을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e0a4-180">To select one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="5e0a4-181">이 PSTN 사용 레코드와 연결 하려는 경로를 강조 표시 하 고 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e0a4-181">Highlight the routes you want to associate with this PSTN usage record, and click **OK**.</span></span>

   - <span data-ttu-id="5e0a4-182">PSTN 사용 레코드에서 경로를 제거 하려면 해당 경로를 선택 하 고 **제거**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e0a4-182">To remove a route from the PSTN usage record, select the route, and click **Remove**.</span></span>

   - <span data-ttu-id="5e0a4-183">새 경로를 정의 하 고이 PSTN 사용 레코드에 연결 하려면 **새로 만들기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e0a4-183">To define a new route and associate it to this PSTN usage record, click **New**.</span></span> <span data-ttu-id="5e0a4-184">자세한 내용은 [비즈니스용 Skype에서 음성 경로 만들기 또는 수정을](create-or-modify-a-voice-route.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5e0a4-184">For details, see [Create or modify a voice route in Skype for Business](create-or-modify-a-voice-route.md).</span></span>

   - <span data-ttu-id="5e0a4-185">이 PSTN 사용 레코드와 연결 된 경로를 편집 하려면 해당 경로를 선택 하 고 **세부 정보 표시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e0a4-185">To edit a route that is associated with this PSTN usage record, select the route, and click **Show details**.</span></span>

     <span data-ttu-id="5e0a4-186">c.</span><span class="sxs-lookup"><span data-stu-id="5e0a4-186">c.</span></span> <span data-ttu-id="5e0a4-187">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5e0a4-187">Click **OK**.</span></span>

     > [!IMPORTANT]
     > <span data-ttu-id="5e0a4-188">구성 중인 트렁크에 연결 된 중재 서버 피어에 따라 PSTN 사용 레코드를 연결 하는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e0a4-188">It is important to associate PSTN usage records according to the Mediation Server peer that is associated to the trunk being configured.</span></span> <span data-ttu-id="5e0a4-189">중재 서버 피어가 PSTN 게이트웨이 또는 SBC (세션 경계 컨트롤러) 인 경우 트렁크 구성이 PSTN 대상 또는 Skype를 통해 연결 된 다른 다운스트림 시스템으로 경로 하는 PSTN 사용 레코드와 연결 되어 있지 않은 것이 좋습니다. 비즈니스 서버용</span><span class="sxs-lookup"><span data-stu-id="5e0a4-189">If the Mediation Server peer is a PSTN gateway or a Session Border Controller (SBC), it is strongly recommended that the trunk configuration is not associated to a PSTN usage record that routes to a PSTN destination or any other downstream systems connected via Skype for Business Server.</span></span>

10. <span data-ttu-id="5e0a4-190">최적의 성능을 위해 PSTN 사용 레코드를 정렬 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e0a4-190">Arrange the PSTN usage records for optimum performance.</span></span> <span data-ttu-id="5e0a4-191">목록에서 레코드의 위치를 변경 하려면 PSTN 사용 레코드를 선택 하 고 위쪽 또는 아래 화살표를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e0a4-191">To change a record's position in the list, select the PSTN usage record, and click the up or down arrows.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="5e0a4-192">트렁크 구성에서 PSTN 사용 레코드가 나열 되는 순서는 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e0a4-192">The order in which PSTN usage records are listed in the trunk configuration is significant.</span></span> <span data-ttu-id="5e0a4-193">비즈니스용 Skype 서버에서 목록을 위에서 아래로 트래버스 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e0a4-193">Skype for Business Server traverses the list from top to down.</span></span>

11. <span data-ttu-id="5e0a4-194">NAT (네트워크 주소 변환) 또는 방화벽 및 Latching를 지 원하는 SBC 뒤에 있는 클라이언트에 대 한 미디어를 우회 하도록 설정 하려면 **RTP Latching** 를 선택 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e0a4-194">**Enable RTP Latching** should be selected to enable bypass media for clients behind a network address translation (NAT) or firewall and an SBC that supports latching.</span></span>

12. <span data-ttu-id="5e0a4-195">통화 기록 정보를 중재 서버의 게이트웨이 피어로 보낼 수 있도록 하려면 **착신 전환 사용 기록을** 선택 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e0a4-195">**Enable forward call history** should be selected to enable sending of call history information to the gateway peer of the Mediation Server.</span></span>

13. <span data-ttu-id="5e0a4-196">**착신 전환 사용-설정 됨-** 지정 된 id 데이터를 사용 하 여 p-어설션된-ID (pai) 호출 보낸 사람 정보를 중재 서버 쪽 및 게이트웨이 쪽 간에 전달 하 고 (반대의 경우 반대 방향으로),이를 발표할 때 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e0a4-196">**Enable forward P-Asserted-Identity data** should be selected to enable the P-Asserted-Identity (PAI) call originator information to be forwarded between the Mediation Server side and gateway side (and vice versa), when present.</span></span>

14. <span data-ttu-id="5e0a4-197">빠른 장애 조치 (failover)를 사용 하도록 설정 하려면 **아웃 바운드 라우팅 장애 조치 타이머** 를 선택 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e0a4-197">**Enable outbound routing failover timer** should be selected to enable fast failover.</span></span> <span data-ttu-id="5e0a4-198">이 트렁크와 연결 된 게이트웨이는 아웃 바운드 통화를 처리 하는 10 초 내에 알림을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e0a4-198">The gateway associated with this trunk can give notification within 10 seconds that it is processing an outbound call.</span></span> <span data-ttu-id="5e0a4-199">중재 서버에서이 알림을 받지 못하는 경우 다른 트렁크로의 경로 전환 문제가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e0a4-199">Rerouting to another trunk will occur if this notification is not received by the Mediation Server.</span></span> <span data-ttu-id="5e0a4-200">대기 시간이 응답 시간을 지연 시키거나 게이트웨이가 응답 하는 데 10 초 넘게 걸릴 수 있는 네트워크에서는 빠른 장애 조치를 사용 하지 않도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e0a4-200">On networks where latency may delay the response time or the gateway takes longer than 10 seconds to respond, the fast failover should be disabled.</span></span>

15. <span data-ttu-id="5e0a4-201">) 트렁크 용 **전화 번호 번역 규칙** 을 연결 하 고 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e0a4-201">(Optional) Associate and configure **calling number translation rules** for the trunk.</span></span> <span data-ttu-id="5e0a4-202">이러한 번역 규칙은 발신 전화에 대 한 통화 번호에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5e0a4-202">These translation rules apply to the calling number for outbound calls</span></span>

    - <span data-ttu-id="5e0a4-203">엔터프라이즈 음성 배포에서 사용할 수 있는 모든 번역 규칙 목록에서 하나 이상의 규칙을 선택 하려면 **선택을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e0a4-203">To choose one or more rules from a list of all translation rules that are available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="5e0a4-204">**번역 규칙 선택**에서 트렁크와 연결 하려는 규칙을 클릭 한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e0a4-204">In **Select Translation Rules**, click the rules that you want to associate with the trunk, and then click **OK**.</span></span>

    - <span data-ttu-id="5e0a4-205">새 번역 규칙을 정의 하 고 트렁크에 연결 하려면 **새로 만들기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e0a4-205">To define a new translation rule and associate it with the trunk, click **New**.</span></span> <span data-ttu-id="5e0a4-206">번역 규칙에 대 한 자세한 내용은 [비즈니스용 Skype 서버에서 번역 규칙](../../plan-your-deployment/enterprise-voice-solution/translation-rules.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5e0a4-206">For details about translation rules, see [Translation rules in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/translation-rules.md).</span></span>

    - <span data-ttu-id="5e0a4-207">트렁크에 이미 연결 된 번역 규칙을 편집 하려면 규칙 이름을 클릭 한 다음 **세부 정보 표시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e0a4-207">To edit a translation rule that is already associated with the trunk, click the rule name, and then click **Show details**.</span></span>

    - <span data-ttu-id="5e0a4-208">기존 번역 규칙을 복사 하 여 새 규칙을 정의 하는 출발점으로 사용 하려면 규칙 이름을 클릭 하 고 **복사**를 클릭 한 다음 **붙여넣기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e0a4-208">To copy an existing translation rule to use as a starting point for defining a new rule, click the rule name and click **Copy**, and then click **Paste**.</span></span>

    - <span data-ttu-id="5e0a4-209">트렁크에서 번역 규칙을 제거 하려면 규칙 이름을 강조 표시 하 고 **제거**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e0a4-209">To remove a translation rule from the trunk, highlight the rule name and click **Remove**.</span></span>

    > [!CAUTION]
    > <span data-ttu-id="5e0a4-210">두 규칙이 충돌할 수 있으므로 연결 된 트렁크 피어에서 번역 규칙을 구성한 경우에는 번역 규칙과 트렁크를 연결 하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="5e0a4-210">Do not associate translation rules with a trunk if you have configured translation rules on the associated trunk peer, because the two rules might conflict.</span></span>

16. <span data-ttu-id="5e0a4-211">) 트렁크에 대해 전화 **번호 번역 규칙** 을 연결 하 고 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e0a4-211">(Optional) Associate and configure **called number translation rules** for the trunk.</span></span> <span data-ttu-id="5e0a4-212">번역 규칙은 발신 통화 시 호출 되는 번호에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5e0a4-212">The translation rules apply to the called number in an outbound call.</span></span>

    - <span data-ttu-id="5e0a4-213">엔터프라이즈 음성 배포에서 사용할 수 있는 모든 번역 규칙 목록에서 하나 이상의 규칙을 선택 하려면 **선택을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e0a4-213">To choose one or more rules from a list of all translation rules that are available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="5e0a4-214">**번역 규칙 선택**에서 트렁크와 연결 하려는 규칙을 클릭 한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e0a4-214">In **Select Translation Rules**, click the rules that you want to associate with the trunk, and then click **OK**.</span></span>

    - <span data-ttu-id="5e0a4-215">새 번역 규칙을 정의 하 고 트렁크에 연결 하려면 **새로 만들기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e0a4-215">To define a new translation rule and associate it with the trunk, click **New**.</span></span> <span data-ttu-id="5e0a4-216">번역 규칙에 대 한 자세한 내용은 [비즈니스용 Skype 서버에서 번역 규칙](../../plan-your-deployment/enterprise-voice-solution/translation-rules.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5e0a4-216">For details about translation rules, see [Translation rules in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/translation-rules.md).</span></span>

    - <span data-ttu-id="5e0a4-217">트렁크에 이미 연결 된 번역 규칙을 편집 하려면 규칙 이름을 클릭 한 다음 **세부 정보 표시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e0a4-217">To edit a translation rule that is already associated with the trunk, click the rule name, and then click **Show details**.</span></span>

    - <span data-ttu-id="5e0a4-218">기존 번역 규칙을 복사 하 여 새 규칙을 정의 하는 출발점으로 사용 하려면 규칙 이름을 클릭 하 고 **복사**를 클릭 한 다음 **붙여넣기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e0a4-218">To copy an existing translation rule to use as a starting point for defining a new rule, click the rule name and click **Copy**, and then click **Paste**.</span></span>

    - <span data-ttu-id="5e0a4-219">트렁크에서 번역 규칙을 제거 하려면 규칙 이름을 강조 표시 하 고 **제거**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e0a4-219">To remove a translation rule from the trunk, highlight the rule name and click **Remove**.</span></span>

    > [!CAUTION]
    > <span data-ttu-id="5e0a4-220">두 규칙이 충돌할 수 있으므로 연결 된 트렁크 피어에서 번역 규칙을 구성한 경우에는 번역 규칙과 트렁크를 연결 하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="5e0a4-220">Do not associate translation rules with a trunk if you have configured translation rules on the associated trunk peer, because the two rules might conflict.</span></span>

17. <span data-ttu-id="5e0a4-221">트렁크의 번역 규칙이 올바른 순서로 정렬 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e0a4-221">Make sure that the trunk's translation rules are arranged in the correct order.</span></span> <span data-ttu-id="5e0a4-222">목록에서 규칙의 위치를 변경 하려면 규칙 이름을 강조 표시 한 다음 위쪽 또는 아래쪽 화살표를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e0a4-222">To change a rule's position in the list, highlight the rule name and then click the up or down arrow.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="5e0a4-223">비즈니스용 Skype Server는 번역 규칙 목록을 위에서 아래로 이동 하 고, 전화 번호와 일치 하는 첫 번째 규칙을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e0a4-223">Skype for Business Server traverses the translation rule list from the top down and uses the first rule that matches the dialed number.</span></span> <span data-ttu-id="5e0a4-224">전화를 거는 번호가 두 개 이상의 번역 규칙과 일치 하도록 트렁크를 구성 하는 경우 더 제한적인 규칙이 덜 제한적인 규칙 보다 먼저 정렬 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e0a4-224">If you configure a trunk so that a dialed number can match more than one translation rule, be sure that the more restrictive rules are sorted above the less restrictive rules.</span></span> <span data-ttu-id="5e0a4-225">예를 들어 11 자리 숫자와 일치 하는 번역 규칙과 + 1425으로 시작 하는 11 자리 숫자만 일치 하는 번역 규칙을 포함 한 경우 11 자리 숫자와 일치 하는 규칙이 보다 제한적으로 정렬 되어 있는지 확인 해야 합니다. \*\* 노트.</span><span class="sxs-lookup"><span data-stu-id="5e0a4-225">For example, if you have included a translation rule that matches any 11-digit number and a translation rule that matches only 11-digit numbers that start with +1425, be sure that the rule that matches any 11-digit number is sorted  *below*  the more restrictive rule.</span></span>

18. <span data-ttu-id="5e0a4-226">트렁크 구성을 마쳤으면 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e0a4-226">When you are finished configuring the trunk, click **OK**.</span></span>

19. <span data-ttu-id="5e0a4-227">**트렁크 구성** 페이지에서 **커밋을**클릭 한 다음 **모두 커밋을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e0a4-227">On the **Trunk Configuration** page, click **Commit**, and then click **Commit all**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="5e0a4-228">트렁크 구성을 만들거나 수정할 때마다 **모두 커밋** 명령을 실행 하 여 구성 변경 내용을 게시 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e0a4-228">Whenever you create or modify a trunk configuration, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="5e0a4-229">자세한 내용은 운영 설명서의 비즈니스용 [Skype에서 음성 라우팅 구성에 보류 중인 변경 내용 게시](voice-route-config-changes.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5e0a4-229">For details, see [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation.</span></span>

<span data-ttu-id="5e0a4-230">트렁크를 구성한 후에는 배포 설명서의 [비즈니스용 Skype 서버에서 미디어 건너뛰기](deploy-media-bypass.md) 에 설명 된 바와 같이 글로벌 미디어 건너뛰기 옵션 중 하나를 선택 하 여 미디어 바이패스 구성을 계속 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e0a4-230">After you have configured the trunk, continue configuring media bypass by choosing between global media bypass options, as described in [Deploy media bypass in Skype for Business Server](deploy-media-bypass.md) in the Deployment documentation.</span></span>
## <a name="see-also"></a><span data-ttu-id="5e0a4-231">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5e0a4-231">See also</span></span>

[<span data-ttu-id="5e0a4-232">비즈니스용 Skype 서버에서 미디어 바이패스 없이 트렁크 구성</span><span class="sxs-lookup"><span data-stu-id="5e0a4-232">Configure a trunk without media bypass in Skype for Business Server</span></span>](configure-trunk-without-media-bypass.md)

[<span data-ttu-id="5e0a4-233">비즈니스용 Skype 서버에서 미디어 바이패스 배포</span><span class="sxs-lookup"><span data-stu-id="5e0a4-233">Deploy media bypass in Skype for Business Server</span></span>](deploy-media-bypass.md)

[<span data-ttu-id="5e0a4-234">번역 규칙 정의</span><span class="sxs-lookup"><span data-stu-id="5e0a4-234">Defining Translation Rules</span></span>](https://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx)

[<span data-ttu-id="5e0a4-235">미디어 바이패스 구성</span><span class="sxs-lookup"><span data-stu-id="5e0a4-235">Configure Media Bypass</span></span>](https://technet.microsoft.com/library/f50a7a13-c6a0-48f1-bee1-e45fa2b2f9b8.aspx)

