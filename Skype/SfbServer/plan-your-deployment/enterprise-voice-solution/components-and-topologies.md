---
title: 비즈니스용 Skype의 통화 허용 제어에 대 한 구성 요소 및 토폴로지
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 0beec6be-2431-4255-a3d2-512dd030e66a
description: MPLS 네트워크, SIP 트렁크 또는 타사 PSTN 게이트웨이 또는 PBX를 사용 하는 경우에는 호출 허용 제어 (CAC) 계획을 수립 합니다. 비즈니스용 Skype Server Enterprise Voice에 적용 됩니다.
ms.openlocfilehash: 7fcbc3e8c7fc7b4139fd9c83718db59af099f47f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803118"
---
# <a name="components-and-topologies-for-call-admission-control-in-skype-for-business"></a><span data-ttu-id="778a7-104">비즈니스용 Skype의 통화 허용 제어에 대 한 구성 요소 및 토폴로지</span><span class="sxs-lookup"><span data-stu-id="778a7-104">Components and topologies for call admission control in Skype for Business</span></span>

<span data-ttu-id="778a7-105">MPLS 네트워크, SIP 트렁크 또는 타사 PSTN 게이트웨이 또는 PBX를 사용 하는 경우에는 호출 허용 제어 (CAC) 계획을 수립 합니다.</span><span class="sxs-lookup"><span data-stu-id="778a7-105">Planning for call admission control (CAC) if you have an MPLS network, a SIP trunk, or a third-party PSTN gateway or PBX.</span></span> <span data-ttu-id="778a7-106">비즈니스용 Skype Server Enterprise Voice에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="778a7-106">Applies to Skype for Business Server Enterprise Voice.</span></span>

<span data-ttu-id="778a7-107">이 섹션의 항목은 다양 한 유형의 네트워크 토폴로지에 대해 CAC (call 허용 제어) 배포에 대 한 특별 고려 사항에 대 한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="778a7-107">The topics in this section provide information about special considerations for deploying call admission control (CAC) with various types of network topologies.</span></span>

## <a name="call-admission-control-on-an-mpls-network"></a><span data-ttu-id="778a7-108">MPLS 네트워크의 통화 허용 제어</span><span class="sxs-lookup"><span data-stu-id="778a7-108">Call admission control on an MPLS network</span></span>

<span data-ttu-id="778a7-109">멀티 프로토콜 레이블 전환 (MPLS) 네트워크에서 모든 사이트는 풀 메시로 연결 됩니다.</span><span class="sxs-lookup"><span data-stu-id="778a7-109">In a Multiprotocol Label Switching (MPLS) network, all sites are connected by a full-mesh.</span></span> <span data-ttu-id="778a7-110">즉, 모든 사이트가 인터넷 서비스 공급자의 MPLS 백본으로 직접 연결 되며, 각 사이트는 MPLS 클라우드의 WAN 링크에서 사용할 수 있도록 프로 비전 된 대역폭을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="778a7-110">That is, all sites are connected directly to the MPLS backbone of the Internet service provider, and each site is provisioned bandwidth to be used across a WAN link to the MPLS cloud.</span></span> <span data-ttu-id="778a7-111">IP 라우팅을 제어 하는 네트워크 허브나 중앙 사이트는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="778a7-111">There is no network hub or central site to control IP routing.</span></span> <span data-ttu-id="778a7-112">다음 그림은 MPLS 기술을 기반으로 하는 간단한 네트워크를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="778a7-112">The following figure shows a simple network based on MPLS technology.</span></span>

<span data-ttu-id="778a7-113">**예제 MPLS 네트워크**</span><span class="sxs-lookup"><span data-stu-id="778a7-113">**Example MPLS network**</span></span>

![MPLS를 사용하는 CAC](../../media/CAC_MPLS_1.jpg)

<span data-ttu-id="778a7-115">MPLS 네트워크에 CAC (call 허용 제어)를 배포 하려면 MPLS 클라우드를 나타내는 네트워크 영역을 만들고 각 MPLS 위성 사이트를 나타내는 네트워크 사이트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="778a7-115">To deploy call admission control (CAC) in an MPLS network, you create a network region to represent the MPLS cloud, and create a network site to represent each MPLS satellite site.</span></span> <span data-ttu-id="778a7-116">다음 그림에서는 네트워크 지역과 네트워크 사이트를 구성 하 여 이전 그림의 예제 MPLS 네트워크를 표시 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="778a7-116">The following figure illustrates how the network region and network sites should be configured to represent the example MPLS network in the previous figure.</span></span> <span data-ttu-id="778a7-117">각 네트워크 사이트에서 MPLS 클라우드를 나타내는 네트워크 지역으로의 WAN 링크 용량을 기준으로 전체 대역폭 한도와 대역폭 세션 한도가 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="778a7-117">The overall bandwidth limits and bandwidth session limits are then based on the capacity of the WAN link from each network site to the network region that represents the MPLS cloud.</span></span>

<span data-ttu-id="778a7-118">**MPLS 네트워크에 대 한 네트워크 지역 및 네트워크 사이트**</span><span class="sxs-lookup"><span data-stu-id="778a7-118">**Network region and network sites for an MPLS network**</span></span>

![MPLS를 사용하는 CAC(통화 허용 제어) 다이어그램](../../media/CAC_MPLS_2.jpg)

## <a name="call-admission-control-on-a-sip-trunk"></a><span data-ttu-id="778a7-120">SIP 트렁크에 대한 통화 허용 제어 서비스</span><span class="sxs-lookup"><span data-stu-id="778a7-120">Call admission control on a SIP trunk</span></span>

<span data-ttu-id="778a7-121">SIP 트렁크에 CAC (call 허용 제어)를 배포 하려면 네트워크 사이트를 만들어 인터넷 통신 서비스 공급자 (ITSP)를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="778a7-121">To deploy call admission control (CAC) on a SIP trunk, you create a network site to represent the Internet telephony service provider (ITSP).</span></span> <span data-ttu-id="778a7-122">SIP 트렁크에 대역폭 정책 값을 적용 하려면 엔터프라이즈의 네트워크 사이트와 ITSP를 나타내기 위해 만드는 네트워크 사이트 간에 사이트 간 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="778a7-122">To apply bandwidth policy values on the SIP trunk, you create an inter-site policy between the network site in your enterprise and the network site that you create to represent the ITSP.</span></span>

<span data-ttu-id="778a7-123">다음 그림에서는 SIP 트렁크에 대 한 CAC 배포의 예를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="778a7-123">The following figure shows an example CAC deployment on a SIP trunk.</span></span>

<span data-ttu-id="778a7-124">**SIP 트렁크의 CAC 구성**</span><span class="sxs-lookup"><span data-stu-id="778a7-124">**CAC configuration on a SIP trunk**</span></span>

![통화 허용 제어 SIP 트렁크 다이어그램](../../media/CAC_SIP_trunk_1.jpg)

<span data-ttu-id="778a7-126">SIP 트렁크에서 CAC를 구성 하려면 CAC 배포 중에 다음 작업을 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="778a7-126">To configure CAC on a SIP trunk, you will have to perform the following tasks during CAC deployment:</span></span>

1. <span data-ttu-id="778a7-127">ITSP를 나타내는 네트워크 사이트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="778a7-127">Create a network site to represent the ITSP.</span></span> <span data-ttu-id="778a7-128">네트워크 사이트를 적절 한 네트워크 영역에 연결 하 고이 네트워크 사이트의 오디오 및 비디오에 대 한 대역폭을 0으로 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="778a7-128">Associate the network site to an appropriate network region, and allocate bandwidth of zero for audio and video for this network site.</span></span> <span data-ttu-id="778a7-129">자세한 내용은 배포 설명서에서 [CAC에 대 한 네트워크 사이트 구성을](https://technet.microsoft.com/library/afcea38f-5789-45ec-97af-c6e38364950c.aspx) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="778a7-129">For details, see [Configure Network Sites for CAC](https://technet.microsoft.com/library/afcea38f-5789-45ec-97af-c6e38364950c.aspx) in the Deployment documentation.</span></span>

    > [!NOTE]
    > <span data-ttu-id="778a7-130">ITSP의 경우이 네트워크 사이트 구성은 작동 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="778a7-130">For the ITSP, this network site configuration is not functional.</span></span> <span data-ttu-id="778a7-131">대역폭 정책 값은 2 단계에서 실제로 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="778a7-131">Bandwidth policy values are actually applied in step 2.</span></span>

2. <span data-ttu-id="778a7-132">1 단계에서 만든 사이트의 관련 매개 변수 값을 사용 하 여 SIP 트렁크에 대 한 사이트 간 링크를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="778a7-132">Create an inter-site link for the SIP trunk using the relevant parameter values for the site you created in step 1.</span></span> <span data-ttu-id="778a7-133">예를 들어 엔터프라이즈의 네트워크 사이트 이름을 NetworkSiteID1 매개 변수 값으로 사용 하 고 ITSP 네트워크 사이트의 NetworkSiteID2 매개 변수 값으로 사용할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="778a7-133">For example, use the name of the network site in your enterprise as the value of the NetworkSiteID1 parameter, and the ITSP network site as the value of the NetworkSiteID2 parameter.</span></span> <span data-ttu-id="778a7-134">자세한 내용은 배포 설명서 및 [새 CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/new-csnetworkintersitepolicy?view=skype-ps)의 비즈니스용 [Skype 서버에서 네트워크 사이트 간 정책 만들기](../../deploy/deploy-enterprise-voice/create-network-intersite-policies.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="778a7-134">For details, see [Create network intersite policies in Skype for Business Server](../../deploy/deploy-enterprise-voice/create-network-intersite-policies.md) in the Deployment documentation, and [New-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/new-csnetworkintersitepolicy?view=skype-ps).</span></span>

3. <span data-ttu-id="778a7-135">ITSP에서 SCB (세션 경계 컨트롤러) 미디어 종료 지점의 IP 주소를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="778a7-135">Get the IP address of the Session Border Controller's (SCB) Media Termination Point from your ITSP.</span></span> <span data-ttu-id="778a7-136">ITSP를 나타내는 네트워크 사이트에 32의 서브넷 마스크를 사용 하 여 해당 IP 주소를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="778a7-136">Add that IP address with a subnet mask of 32 to the network site that represents the ITSP.</span></span> <span data-ttu-id="778a7-137">자세한 내용은 [네트워크 사이트와 서브넷 연결](https://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="778a7-137">For details, see [Associate a Subnet with a Network Site](https://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx).</span></span>

## <a name="call-admission-control-with-a-third-party-pstn-gateway-or-pbx"></a><span data-ttu-id="778a7-138">타사 PSTN 게이트웨이 또는 PBX에 대한 통화 허용 제어 서비스</span><span class="sxs-lookup"><span data-stu-id="778a7-138">Call admission control with a third-party PSTN gateway or PBX</span></span>

<span data-ttu-id="778a7-139">이 항목에서는 중재 서버의 게이트웨이 인터페이스와 타사의 PSTN (공개 교환 통신 네트워크) 게이트웨이 또는 PBX (개인 분기 교환) 간의 링크에 CAC (call 허용 제어)를 배포 하는 방법의 예를 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="778a7-139">This topic describes examples of how call admission control (CAC) can be deployed on the link between the Mediation Server's gateway interface and a third-party public switched telephone network (PSTN) gateway or private branch exchange (PBX).</span></span>

### <a name="case-1-cac-between-the-mediation-server-and-a-pstn-gateway"></a><span data-ttu-id="778a7-140">사례 1: 중재 서버와 PSTN 게이트웨이 간의 CAC</span><span class="sxs-lookup"><span data-stu-id="778a7-140">Case 1: CAC between the Mediation Server and a PSTN gateway</span></span>

<span data-ttu-id="778a7-141">CAC는 중재 서버의 게이트웨이 인터페이스에서 타사 PBX 또는 PSTN 게이트웨이로의 WAN 링크에 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="778a7-141">CAC can be deployed on the WAN link from the Mediation Server's gateway interface to a third-party PBX or PSTN gateway.</span></span>

<span data-ttu-id="778a7-142">**사례 1: 중재 서버와 PSTN 게이트웨이 간의 CAC**</span><span class="sxs-lookup"><span data-stu-id="778a7-142">**Case 1: CAC between the Mediation Server and a PSTN gateway**</span></span>

![사례 1: 중재 서버 PSTN 게이트웨이 간의 CAC](../../media/CAC_gateways_1.jpg)

<span data-ttu-id="778a7-144">이 예제에서는 중재 서버와 PSTN 게이트웨이 간에 CAC가 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="778a7-144">In this example, CAC is applied between the Mediation Server and a PSTN gateway.</span></span> <span data-ttu-id="778a7-145">네트워크 사이트 1의 비즈니스용 Skype 클라이언트 사용자가 네트워크 사이트 2의 PSTN 게이트웨이를 통해 PSTN 통화를 하는 경우 미디어는 WAN 링크를 통해 흐릅니다.</span><span class="sxs-lookup"><span data-stu-id="778a7-145">If a Skype for Business client user at Network Site 1 places a PSTN call through the PSTN gateway in Network Site 2, the media flows through the WAN link.</span></span> <span data-ttu-id="778a7-146">따라서 각 PSTN 세션에 대해 다음 두 가지 CAC 검사를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="778a7-146">Therefore, two CAC checks are performed for each PSTN session:</span></span>

- <span data-ttu-id="778a7-147">비즈니스용 Skype 클라이언트 응용 프로그램과 중재 서버 간</span><span class="sxs-lookup"><span data-stu-id="778a7-147">Between the Skype for Business client application and the Mediation Server</span></span>

- <span data-ttu-id="778a7-148">중재 서버와 PSTN 게이트웨이 간의 관계</span><span class="sxs-lookup"><span data-stu-id="778a7-148">Between the Mediation Server and the PSTN gateway</span></span>

<span data-ttu-id="778a7-149">이는 네트워크 사이트 1의 클라이언트로 들어오는 PSTN 통화와 네트워크 사이트 1의 클라이언트 응용 프로그램에서 보내는 PSTN 통화에 대해 모두 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="778a7-149">This works for both incoming PSTN calls to a client in Network Site 1, and for outgoing PSTN calls originating from a client application in Network Site 1.</span></span>

> [!NOTE]
> <span data-ttu-id="778a7-150">PSTN 게이트웨이가 속한 IP 서브넷이 구성 되어 있고 네트워크 사이트 2에 연결 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="778a7-150">Make sure that the IP subnet that the PSTN gateway belongs to is configured and associated with Network Site 2.</span></span>

> [!NOTE]
> <span data-ttu-id="778a7-151">중재 서버의 두 인터페이스가 속한 IP 서브넷이 네트워크 사이트 1에 구성 되 고 연결 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="778a7-151">Make sure that the IP subnet that both interfaces of the Mediation Server belong to is configured and associated with Network Site 1.</span></span>

> [!NOTE]
> <span data-ttu-id="778a7-152">자세한 내용은 [네트워크 사이트와 서브넷 연결](https://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="778a7-152">For details, see [Associate a Subnet with a Network Site](https://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx).</span></span>

### <a name="case-2-cac-between-the-mediation-server-and-a-third-party-pbx-with-media-termination-point"></a><span data-ttu-id="778a7-153">사례 2: 중재 서버와 미디어 종료 지점이 있는 타사 PBX 간의 CAC</span><span class="sxs-lookup"><span data-stu-id="778a7-153">Case 2: CAC between the Mediation Server and a third-party PBX with Media Termination Point</span></span>

<span data-ttu-id="778a7-154">이 구성은 사례 1과 유사 합니다.</span><span class="sxs-lookup"><span data-stu-id="778a7-154">This configuration is similar to Case 1.</span></span> <span data-ttu-id="778a7-155">두 경우 모두 중재 서버는 WAN 링크의 반대편에 있는 장치가 미디어를 종료 하는 것을 인식 하 고 MTP (미디어 종료 지점)를 사용 하는 PSTN 게이트웨이 또는 PBX의 IP 주소는 조정 서버에서 다음 홉으로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="778a7-155">In both the cases, the Mediation Server knows what device terminates media at the opposite end of the WAN link, and the IP address of the PSTN gateway or PBX with Media Termination Point (MTP) is configured on the Mediation Server as the next hop.</span></span>

<span data-ttu-id="778a7-156">**사례 2: 중재 서버와 MTP를 사용 하 여 타사 PBX 간의 CAC**</span><span class="sxs-lookup"><span data-stu-id="778a7-156">**Case 2: CAC between the Mediation Server and a third-party PBX with MTP**</span></span>

![사례 2: 중재 서버 PBX(MTP 포함) 간의 CAC](../../media/CAC_gateways_2.jpg)

<span data-ttu-id="778a7-158">이 예제에서는 중재 서버와 PBX/MTP 사이에 CAC가 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="778a7-158">In this example, CAC is applied between the Mediation Server and the PBX/MTP.</span></span> <span data-ttu-id="778a7-159">네트워크 사이트 1에 있는 비즈니스용 Skype 클라이언트 사용자가 네트워크 사이트 2에 있는 PBX/MTP를 통해 PSTN 통화를 하는 경우 미디어는 WAN 링크를 통해 흐릅니다.</span><span class="sxs-lookup"><span data-stu-id="778a7-159">If a Skype for Business client user at the Network Site 1 places a PSTN call through the PBX/MTP located in Network Site 2, the media flows through the WAN link.</span></span> <span data-ttu-id="778a7-160">따라서 각 PSTN 세션에 대해 다음 두 CAC 검사를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="778a7-160">Therefore, for each PSTN session two CAC checks are performed:</span></span>

- <span data-ttu-id="778a7-161">비즈니스용 Skype 클라이언트 응용 프로그램과 중재 서버 간</span><span class="sxs-lookup"><span data-stu-id="778a7-161">Between the Skype for Business client application and the Mediation Server</span></span>

- <span data-ttu-id="778a7-162">중재 서버와 PBX/MTP 사이</span><span class="sxs-lookup"><span data-stu-id="778a7-162">Between the Mediation Server and the PBX/MTP</span></span>

<span data-ttu-id="778a7-163">네트워크 사이트 1의 클라이언트로 들어오는 PSTN 통화와 네트워크 사이트 1의 클라이언트에서 보내는 PSTN 통화를 모두 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="778a7-163">This works for both incoming PSTN calls to a client in Network Site 1, and outgoing PSTN calls originating from a client in Network Site 1.</span></span>

> [!NOTE]
> <span data-ttu-id="778a7-164">MTP가 속해 있는 IP 서브넷이 구성 되어 있고 네트워크 사이트 2에 연결 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="778a7-164">Make sure that the IP subnet that the MTP belongs to is configured and associated with Network Site 2.</span></span>

> [!NOTE]
> <span data-ttu-id="778a7-165">중재 서버의 두 인터페이스가 속한 IP 서브넷이 네트워크 사이트 1에 구성 되 고 연결 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="778a7-165">Make sure that the IP subnet that both interfaces of the Mediation Server belong to is configured and associated with Network Site 1.</span></span>

> [!NOTE]
> <span data-ttu-id="778a7-166">자세한 내용은 [네트워크 사이트와 서브넷 연결](https://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="778a7-166">For details, see [Associate a Subnet with a Network Site](https://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx).</span></span>

### <a name="case-3-cac-between-the-mediation-server-and-a-third-party-pbx-without-a-media-termination-point"></a><span data-ttu-id="778a7-167">사례 3: 중재 서버와 미디어 종료 지점이 없는 타사 PBX 간의 CAC</span><span class="sxs-lookup"><span data-stu-id="778a7-167">Case 3: CAC between the Mediation Server and a third-party PBX without a Media Termination Point</span></span>

<span data-ttu-id="778a7-168">사례 3은 처음 두 경우와 약간 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="778a7-168">Case 3 is slightly different from the first two cases.</span></span> <span data-ttu-id="778a7-169">타사 PBX에 MTP가 없는 경우, 타사 PBX로 보내는 세션 요청에 대해 중재 서버는 PBX 경계에서 미디어가 종료 되는 위치를 알 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="778a7-169">If there is no MTP on the third-party PBX, for an outgoing session request to the third-party PBX the Mediation Server does not know where media will terminate in the PBX boundary.</span></span> <span data-ttu-id="778a7-170">이 경우 미디어는 중재 서버와 타사 끝점 디바이스 간에 직접 흐릅니다.</span><span class="sxs-lookup"><span data-stu-id="778a7-170">In this case, the media flows directly between the Mediation Server and the third-party endpoint device.</span></span>

<span data-ttu-id="778a7-171">**사례 3: 중재 서버와 MTP 없이 타사 PBX 간의 CAC**</span><span class="sxs-lookup"><span data-stu-id="778a7-171">**Case 3: CAC between the Mediation Server and a third-party PBX without MTP**</span></span>

![사례 3: 중재 서버 PBX(MTP 미포함) 간의 CAC](../../media/CAC_gateways_3.jpg)

<span data-ttu-id="778a7-173">이 예제에서는 네트워크 사이트 1의 비즈니스용 Skype 클라이언트 사용자가 PBX를 통해 사용자에 게 전화를 거는 경우 중재 서버는 프록시 레그 에서만 CAC 확인을 수행할 수 있습니다 (비즈니스용 Skype 클라이언트 응용 프로그램과 중재 서버 간).</span><span class="sxs-lookup"><span data-stu-id="778a7-173">In this example, if a Skype for Business client user at Network Site 1 places a call to a user through the PBX, the Mediation Server is able to perform CAC checks only on the proxy leg (between the Skype for Business client application and Mediation Server).</span></span> <span data-ttu-id="778a7-174">중재 서버는 세션을 요청 하는 동안 끝점 장치에 대 한 정보를 포함 하지 않으므로 호출 설정 전에 중재 서버와 타사 끝점 간의 WAN 링크에서 CAC 검사를 수행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="778a7-174">Because the Mediation Server does not have information about the endpoint device while the session is being requested, CAC checks cannot be performed on the WAN link (between the Mediation Server and the third-party endpoint) prior to call establishment.</span></span> <span data-ttu-id="778a7-175">그러나 세션이 설정 된 후에는 중재 서버에서 트렁크에 사용 되는 대역폭에 대 한 계정을 쉽게 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="778a7-175">After the session is established, however, the Mediation Server facilitates in accounting for the bandwidth used on the trunk.</span></span>

<span data-ttu-id="778a7-176">타사 끝점에서 시작 되는 통화의 경우 해당 끝점 장치에 대 한 정보는 세션 요청 시 사용할 수 있으며 CAC 검사는 중재 서버의 양쪽에서 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="778a7-176">For calls that originate from the third-party endpoint, the information about that endpoint device is available at the time of session request and CAC check can be performed on both the sides of the Mediation Server.</span></span>

> [!NOTE]
> <span data-ttu-id="778a7-177">끝점 디바이스가 속한 IP 서브넷이 네트워크 사이트 2와 연결 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="778a7-177">Make sure that the IP subnet that the endpoint devices belong to is configured and associated with Network Site 2.</span></span>

> [!NOTE]
> <span data-ttu-id="778a7-178">중재 서버의 두 인터페이스가 속한 IP 서브넷이 네트워크 사이트 1에 구성 되 고 연결 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="778a7-178">Make sure that the IP subnet that both interfaces of the Mediation Server belong to is configured and associated with Network Site 1.</span></span>

> [!NOTE]
> <span data-ttu-id="778a7-179">자세한 내용은 [네트워크 사이트와 서브넷 연결](https://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="778a7-179">For details, see [Associate a Subnet with a Network Site](https://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx).</span></span>


