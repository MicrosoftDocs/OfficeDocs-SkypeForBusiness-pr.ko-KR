---
title: 비즈니스용 Skype의 통화 입장 제어에 대한 구성 요소 및 토폴로지
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: MPLS 네트워크, SIP 트렁크 또는 타사 PSTN 게이트웨이 또는 PBX가 있는 경우 CAC(통화 제어)에 대한 계획 비즈니스용 Skype 서버 Enterprise Voice.
ms.openlocfilehash: 771b98e10c28248bc917bff2b8128b6258c140c5
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51109194"
---
# <a name="components-and-topologies-for-call-admission-control-in-skype-for-business"></a><span data-ttu-id="b4011-104">비즈니스용 Skype의 통화 입장 제어에 대한 구성 요소 및 토폴로지</span><span class="sxs-lookup"><span data-stu-id="b4011-104">Components and topologies for call admission control in Skype for Business</span></span>

<span data-ttu-id="b4011-105">MPLS 네트워크, SIP 트렁크 또는 타사 PSTN 게이트웨이 또는 PBX가 있는 경우 CAC(통화 제어)에 대한 계획</span><span class="sxs-lookup"><span data-stu-id="b4011-105">Planning for call admission control (CAC) if you have an MPLS network, a SIP trunk, or a third-party PSTN gateway or PBX.</span></span> <span data-ttu-id="b4011-106">비즈니스용 Skype 서버 Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="b4011-106">Applies to Skype for Business Server Enterprise Voice.</span></span>

<span data-ttu-id="b4011-107">이 섹션의 항목에서는 다양한 네트워크 토폴로지 유형으로 CAC(통화 허용 제어)를 배포할 때의 특별 고려 사항에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b4011-107">The topics in this section provide information about special considerations for deploying call admission control (CAC) with various types of network topologies.</span></span>

## <a name="call-admission-control-on-an-mpls-network"></a><span data-ttu-id="b4011-108">MPLS 네트워크의 통화 입장 제어</span><span class="sxs-lookup"><span data-stu-id="b4011-108">Call admission control on an MPLS network</span></span>

<span data-ttu-id="b4011-p103">MPLS(Multiprotocol Label Switching) 네트워크에서는 모든 사이트가 풀 메쉬로 연결됩니다. 즉, 모든 사이트가 인터넷 서비스 공급자의 MPLS 백본에 직접 연결되며 각 사이트에는 MPLS 클라우드에 대한 WAN 링크에 사용할 대역폭이 프로비전됩니다. IP 라우팅을 제어하는 네트워크 허브 또는 중앙 사이트는 없습니다. 다음 그림에서는 MPLS 기술을 기반으로 하는 간단한 네트워크를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b4011-p103">In a Multiprotocol Label Switching (MPLS) network, all sites are connected by a full-mesh. That is, all sites are connected directly to the MPLS backbone of the Internet service provider, and each site is provisioned bandwidth to be used across a WAN link to the MPLS cloud. There is no network hub or central site to control IP routing. The following figure shows a simple network based on MPLS technology.</span></span>

<span data-ttu-id="b4011-113">**예제 MPLS 네트워크**</span><span class="sxs-lookup"><span data-stu-id="b4011-113">**Example MPLS network**</span></span>

![MPLS가 있는 CAC](../../media/CAC_MPLS_1.jpg)

<span data-ttu-id="b4011-p104">MPLS 네트워크에서 CAC(통화 허용 제어)를 배포하려면 MPLS 클라우드를 나타내는 네트워크 지역을 만든 다음 각 MPLS 위성 사이트를 나타내는 네트워크 사이트를 만듭니다. 다음 그림에서는 위 그림의 예제 MPLS 네트워크를 나타내도록 네트워크 지역 및 네트워크 사이트를 구성하는 방법을 보여 줍니다. 전체 대역폭 제한 및 대역폭 세션 제한은 각 네트워크 사이트에서 MPLS 클라우드를 나타내는 네트워크 지역으로의 WAN 링크 용량을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4011-p104">To deploy call admission control (CAC) in an MPLS network, you create a network region to represent the MPLS cloud, and create a network site to represent each MPLS satellite site. The following figure illustrates how the network region and network sites should be configured to represent the example MPLS network in the previous figure. The overall bandwidth limits and bandwidth session limits are then based on the capacity of the WAN link from each network site to the network region that represents the MPLS cloud.</span></span>

<span data-ttu-id="b4011-118">**MPLS 네트워크의 네트워크 지역 및 네트워크 사이트**</span><span class="sxs-lookup"><span data-stu-id="b4011-118">**Network region and network sites for an MPLS network**</span></span>

![MPLS 다이어그램을 사용하는 CAC(통화 입장 제어)](../../media/CAC_MPLS_2.jpg)

## <a name="call-admission-control-on-a-sip-trunk"></a><span data-ttu-id="b4011-120">SIP 트렁크의 통화 입장 제어</span><span class="sxs-lookup"><span data-stu-id="b4011-120">Call admission control on a SIP trunk</span></span>

<span data-ttu-id="b4011-p105">SIP 트렁크에 CAC(통화 허용 제어)를 배포하려면 ITSP(인터넷 전화 통신 서비스 공급자)를 나타내는 네트워크 사이트를 만듭니다. SIP 트렁크에 대역폭 정책 값을 적용하려면 엔터프라이즈의 네트워크 사이트와 ITSP를 나타내기 위해 만든 네트워크 사이트 간의 사이트 간 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b4011-p105">To deploy call admission control (CAC) on a SIP trunk, you create a network site to represent the Internet telephony service provider (ITSP). To apply bandwidth policy values on the SIP trunk, you create an inter-site policy between the network site in your enterprise and the network site that you create to represent the ITSP.</span></span>

<span data-ttu-id="b4011-123">다음 그림에서는 SIP 트렁크에 대한 예제 CAC 배포를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b4011-123">The following figure shows an example CAC deployment on a SIP trunk.</span></span>

<span data-ttu-id="b4011-124">**SIP 트렁크에 대한 CAC 구성**</span><span class="sxs-lookup"><span data-stu-id="b4011-124">**CAC configuration on a SIP trunk**</span></span>

![통화 입장 제어 SIP 트렁크 다이어그램](../../media/CAC_SIP_trunk_1.jpg)

<span data-ttu-id="b4011-126">SIP 트렁크에 CAC를 구성하려면 CAC 배포 중에 다음 작업을 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4011-126">To configure CAC on a SIP trunk, you will have to perform the following tasks during CAC deployment:</span></span>

1. <span data-ttu-id="b4011-127">ITSP를 나타내는 네트워크 사이트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b4011-127">Create a network site to represent the ITSP.</span></span> <span data-ttu-id="b4011-128">네트워크 사이트를 적절한 네트워크 지역에 연결하고 이 네트워크 사이트에 오디오 및 비디오 대역폭으로 0을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="b4011-128">Associate the network site to an appropriate network region, and allocate bandwidth of zero for audio and video for this network site.</span></span> <span data-ttu-id="b4011-129">자세한 내용은 배포 설명서의 [Configure Network Sites for CAC](/previous-versions/office/lync-server-2013/lync-server-2013-configure-network-sites-for-cac)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="b4011-129">For details, see [Configure Network Sites for CAC](/previous-versions/office/lync-server-2013/lync-server-2013-configure-network-sites-for-cac) in the Deployment documentation.</span></span>

    > [!NOTE]
    > <span data-ttu-id="b4011-130">ITSP에 대해서는 이 네트워크 사이트 구성이 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b4011-130">For the ITSP, this network site configuration is not functional.</span></span> <span data-ttu-id="b4011-131">대역폭 정책 값은 2단계에서 실제로 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b4011-131">Bandwidth policy values are actually applied in step 2.</span></span>

2. <span data-ttu-id="b4011-132">1단계에서 만든 사이트에 대한 관련 매개 변수 값을 사용하여 SIP 트렁크에 대한 사이트 간 링크를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b4011-132">Create an inter-site link for the SIP trunk using the relevant parameter values for the site you created in step 1.</span></span> <span data-ttu-id="b4011-133">예를 들어 엔터프라이즈의 네트워크 사이트 이름을 NetworkSiteID1 매개 변수 값으로 사용하고 ITSP 네트워크 사이트를 NetworkSiteID2 매개 변수 값으로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b4011-133">For example, use the name of the network site in your enterprise as the value of the NetworkSiteID1 parameter, and the ITSP network site as the value of the NetworkSiteID2 parameter.</span></span> <span data-ttu-id="b4011-134">자세한 내용은 배포 설명서에서 [Create network intersite policies in Skype for Business Server](../../deploy/deploy-enterprise-voice/create-network-intersite-policies.md) 및 [New-CsNetworkInterSitePolicy를 참조하십시오.](/powershell/module/skype/new-csnetworkintersitepolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="b4011-134">For details, see [Create network intersite policies in Skype for Business Server](../../deploy/deploy-enterprise-voice/create-network-intersite-policies.md) in the Deployment documentation, and [New-CsNetworkInterSitePolicy](/powershell/module/skype/new-csnetworkintersitepolicy?view=skype-ps).</span></span>

3. <span data-ttu-id="b4011-135">ITSP에서 SCB(Session Border Controller)의 미디어 종료 지점의 IP 주소를 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="b4011-135">Get the IP address of the Session Border Controller's (SCB) Media Termination Point from your ITSP.</span></span> <span data-ttu-id="b4011-136">해당 IP 주소(서브넷 마스크 32 포함)를 ITSP를 나타내는 네트워크 사이트에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="b4011-136">Add that IP address with a subnet mask of 32 to the network site that represents the ITSP.</span></span> <span data-ttu-id="b4011-137">자세한 내용은 [Associate a Subnet with a Network Site](/previous-versions/office/lync-server-2013/lync-server-2013-associate-a-subnet-with-a-network-site)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="b4011-137">For details, see [Associate a Subnet with a Network Site](/previous-versions/office/lync-server-2013/lync-server-2013-associate-a-subnet-with-a-network-site).</span></span>

## <a name="call-admission-control-with-a-third-party-pstn-gateway-or-pbx"></a><span data-ttu-id="b4011-138">타사 PSTN 게이트웨이 또는 PBX를 사용하여 통화할 수 있는 제어</span><span class="sxs-lookup"><span data-stu-id="b4011-138">Call admission control with a third-party PSTN gateway or PBX</span></span>

<span data-ttu-id="b4011-139">이 항목에서는 중재 서버의 게이트웨이 인터페이스와 타사 PSTN(Public Switched Telephone Network) 게이트웨이 또는 PBX(Private Branch Exchange) 간의 링크에 CAC(통화 제어)를 배포할 수 있는 방법의 예를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b4011-139">This topic describes examples of how call admission control (CAC) can be deployed on the link between the Mediation Server's gateway interface and a third-party public switched telephone network (PSTN) gateway or private branch exchange (PBX).</span></span>

### <a name="case-1-cac-between-the-mediation-server-and-a-pstn-gateway"></a><span data-ttu-id="b4011-140">사례 1: 중재 서버와 PSTN 게이트웨이 간의 CAC</span><span class="sxs-lookup"><span data-stu-id="b4011-140">Case 1: CAC between the Mediation Server and a PSTN gateway</span></span>

<span data-ttu-id="b4011-141">CAC는 중재 서버의 게이트웨이 인터페이스에서 타사 PBX 또는 PSTN 게이트웨이로의 WAN 링크에 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4011-141">CAC can be deployed on the WAN link from the Mediation Server's gateway interface to a third-party PBX or PSTN gateway.</span></span>

<span data-ttu-id="b4011-142">**사례 1: 중재 서버와 PSTN 게이트웨이 간의 CAC**</span><span class="sxs-lookup"><span data-stu-id="b4011-142">**Case 1: CAC between the Mediation Server and a PSTN gateway**</span></span>

![사례 1: 중재 서버 PSTN 게이트웨이 간의 CAC](../../media/CAC_gateways_1.jpg)

<span data-ttu-id="b4011-144">이 예에서 CAC는 중재 서버와 PSTN 게이트웨이 간에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b4011-144">In this example, CAC is applied between the Mediation Server and a PSTN gateway.</span></span> <span data-ttu-id="b4011-145">네트워크 사이트 1의 비즈니스용 Skype 클라이언트 사용자가 네트워크 사이트 2의 PSTN 게이트웨이를 통해 PSTN 통화를 걸면 미디어가 WAN 링크를 통해 흐르게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b4011-145">If a Skype for Business client user at Network Site 1 places a PSTN call through the PSTN gateway in Network Site 2, the media flows through the WAN link.</span></span> <span data-ttu-id="b4011-146">따라서 각 PSTN 세션에 대해 두 번의 CAC 확인이 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="b4011-146">Therefore, two CAC checks are performed for each PSTN session:</span></span>

- <span data-ttu-id="b4011-147">비즈니스용 Skype 클라이언트 응용 프로그램과 중재 서버 간</span><span class="sxs-lookup"><span data-stu-id="b4011-147">Between the Skype for Business client application and the Mediation Server</span></span>

- <span data-ttu-id="b4011-148">중재 서버와 PSTN 게이트웨이 간</span><span class="sxs-lookup"><span data-stu-id="b4011-148">Between the Mediation Server and the PSTN gateway</span></span>

<span data-ttu-id="b4011-149">이 작업은 네트워크 사이트 1의 클라이언트로 걸려 오는 수신 PSTN 전화와 네트워크 사이트 1의 클라이언트 응용 프로그램에서 거는 발신 PSTN 전화 모두에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b4011-149">This works for both incoming PSTN calls to a client in Network Site 1, and for outgoing PSTN calls originating from a client application in Network Site 1.</span></span>

> [!NOTE]
> <span data-ttu-id="b4011-150">PSTN 게이트웨이가 속한 IP 서브넷이 구성되고 네트워크 사이트 2와 연결되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="b4011-150">Make sure that the IP subnet that the PSTN gateway belongs to is configured and associated with Network Site 2.</span></span>

> [!NOTE]
> <span data-ttu-id="b4011-151">중재 서버의 두 인터페이스가 속한 IP 서브넷이 구성되고 네트워크 사이트 1과 연결되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="b4011-151">Make sure that the IP subnet that both interfaces of the Mediation Server belong to is configured and associated with Network Site 1.</span></span>

> [!NOTE]
> <span data-ttu-id="b4011-152">자세한 내용은 [Associate a Subnet with a Network Site](/previous-versions/office/lync-server-2013/lync-server-2013-associate-a-subnet-with-a-network-site)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="b4011-152">For details, see [Associate a Subnet with a Network Site](/previous-versions/office/lync-server-2013/lync-server-2013-associate-a-subnet-with-a-network-site).</span></span>

### <a name="case-2-cac-between-the-mediation-server-and-a-third-party-pbx-with-media-termination-point"></a><span data-ttu-id="b4011-153">사례 2: 중재 서버와 미디어 종료 지점이 있는 타사 PBX 간의 CAC</span><span class="sxs-lookup"><span data-stu-id="b4011-153">Case 2: CAC between the Mediation Server and a third-party PBX with Media Termination Point</span></span>

<span data-ttu-id="b4011-p111">이 구성은 사례 1과 유사합니다. 두 사례 모두 중재 서버에서 장치가 WAN 링크의 반대쪽 끝에서 미디어를 종료함을 인식하며, MTP(미디어 종료 지점)가 있는 PBX 또는 PSTN 게이트웨이의 IP 주소가 중재 서버에 다음 홉으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="b4011-p111">This configuration is similar to Case 1. In both the cases, the Mediation Server knows what device terminates media at the opposite end of the WAN link, and the IP address of the PSTN gateway or PBX with Media Termination Point (MTP) is configured on the Mediation Server as the next hop.</span></span>

<span data-ttu-id="b4011-156">**사례 2: 중재 서버와 MTP가 있는 타사 PBX 간의 CAC**</span><span class="sxs-lookup"><span data-stu-id="b4011-156">**Case 2: CAC between the Mediation Server and a third-party PBX with MTP**</span></span>

![사례 2: MTP를 통해 중재 서버 PBX 간의 CAC](../../media/CAC_gateways_2.jpg)

<span data-ttu-id="b4011-158">이 예에서 CAC는 중재 서버와 PBX/MTP 간에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b4011-158">In this example, CAC is applied between the Mediation Server and the PBX/MTP.</span></span> <span data-ttu-id="b4011-159">네트워크 사이트 1의 비즈니스용 Skype 클라이언트 사용자가 네트워크 사이트 2에 있는 PBX/MTP를 통해 PSTN 통화를 걸면 미디어가 WAN 링크를 통해 흐르게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b4011-159">If a Skype for Business client user at the Network Site 1 places a PSTN call through the PBX/MTP located in Network Site 2, the media flows through the WAN link.</span></span> <span data-ttu-id="b4011-160">따라서 각 PSTN 세션에 대해 두 번의 CAC 확인이 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="b4011-160">Therefore, for each PSTN session two CAC checks are performed:</span></span>

- <span data-ttu-id="b4011-161">비즈니스용 Skype 클라이언트 응용 프로그램과 중재 서버 간</span><span class="sxs-lookup"><span data-stu-id="b4011-161">Between the Skype for Business client application and the Mediation Server</span></span>

- <span data-ttu-id="b4011-162">중재 서버와 PBX/MTP 간</span><span class="sxs-lookup"><span data-stu-id="b4011-162">Between the Mediation Server and the PBX/MTP</span></span>

<span data-ttu-id="b4011-163">이 작업은 네트워크 사이트 1의 클라이언트로 걸려 오는 수신 PSTN 전화와 네트워크 사이트 1의 클라이언트에서 거는 발신 PSTN 전화 모두에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b4011-163">This works for both incoming PSTN calls to a client in Network Site 1, and outgoing PSTN calls originating from a client in Network Site 1.</span></span>

> [!NOTE]
> <span data-ttu-id="b4011-164">MTP가 속한 IP 서브넷이 구성되고 네트워크 사이트 2와 연결되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="b4011-164">Make sure that the IP subnet that the MTP belongs to is configured and associated with Network Site 2.</span></span>

> [!NOTE]
> <span data-ttu-id="b4011-165">중재 서버의 두 인터페이스가 속한 IP 서브넷이 구성되고 네트워크 사이트 1과 연결되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="b4011-165">Make sure that the IP subnet that both interfaces of the Mediation Server belong to is configured and associated with Network Site 1.</span></span>

> [!NOTE]
> <span data-ttu-id="b4011-166">자세한 내용은 [Associate a Subnet with a Network Site](/previous-versions/office/lync-server-2013/lync-server-2013-associate-a-subnet-with-a-network-site)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="b4011-166">For details, see [Associate a Subnet with a Network Site](/previous-versions/office/lync-server-2013/lync-server-2013-associate-a-subnet-with-a-network-site).</span></span>

### <a name="case-3-cac-between-the-mediation-server-and-a-third-party-pbx-without-a-media-termination-point"></a><span data-ttu-id="b4011-167">사례 3: 중재 서버와 미디어 종료 지점이 없는 타사 PBX 간의 CAC</span><span class="sxs-lookup"><span data-stu-id="b4011-167">Case 3: CAC between the Mediation Server and a third-party PBX without a Media Termination Point</span></span>

<span data-ttu-id="b4011-p113">사례 3은 처음 두 사례와 약간 다릅니다. 타사 PBX에 MTP가 없는 경우 타사 PBX에 대한 발신 세션 요청에 대해 중재 서버에서 미디어가 종료되는 PBX 경계 내 위치를 알지 못합니다. 이 경우 미디어가 중재 서버와 타사 끝점 장치 간에 직접 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="b4011-p113">Case 3 is slightly different from the first two cases. If there is no MTP on the third-party PBX, for an outgoing session request to the third-party PBX the Mediation Server does not know where media will terminate in the PBX boundary. In this case, the media flows directly between the Mediation Server and the third-party endpoint device.</span></span>

<span data-ttu-id="b4011-171">**사례 3: 중재 서버와 MTP가 없는 타사 PBX 간의 CAC**</span><span class="sxs-lookup"><span data-stu-id="b4011-171">**Case 3: CAC between the Mediation Server and a third-party PBX without MTP**</span></span>

![사례 3: 중재 서버 PBX MTP 없음 간의 CAC](../../media/CAC_gateways_3.jpg)

<span data-ttu-id="b4011-173">이 예에서 네트워크 사이트 1의 비즈니스용 Skype 클라이언트 사용자가 PBX를 통해 사용자에게 전화를 걸면 중재 서버는 프록시 레그(비즈니스용 Skype 클라이언트 응용 프로그램과 중재 서버 간)에서만 CAC 확인을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4011-173">In this example, if a Skype for Business client user at Network Site 1 places a call to a user through the PBX, the Mediation Server is able to perform CAC checks only on the proxy leg (between the Skype for Business client application and Mediation Server).</span></span> <span data-ttu-id="b4011-174">세션이 요청되는 동안 중재 서버에 끝점 장치에 대한 정보가 없으므로 통화가 연결되기 전에 WAN 링크(중재 서버와 타사 끝점 간)에서 CAC 확인을 수행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b4011-174">Because the Mediation Server does not have information about the endpoint device while the session is being requested, CAC checks cannot be performed on the WAN link (between the Mediation Server and the third-party endpoint) prior to call establishment.</span></span> <span data-ttu-id="b4011-175">그러나 세션이 설정된 후에는 중재 서버가 트렁크에서 사용되는 대역폭 관리를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="b4011-175">After the session is established, however, the Mediation Server facilitates in accounting for the bandwidth used on the trunk.</span></span>

<span data-ttu-id="b4011-176">타사 끝점에서 발신된 전화의 경우에는 세션 요청 시 해당 끝점 장치에 대한 정보를 사용할 수 있으므로 중재 서버의 양쪽에서 CAC 확인을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4011-176">For calls that originate from the third-party endpoint, the information about that endpoint device is available at the time of session request and CAC check can be performed on both the sides of the Mediation Server.</span></span>

> [!NOTE]
> <span data-ttu-id="b4011-177">끝점 장치가 속한 IP 서브넷이 구성되고 네트워크 사이트 2와 연결되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="b4011-177">Make sure that the IP subnet that the endpoint devices belong to is configured and associated with Network Site 2.</span></span>

> [!NOTE]
> <span data-ttu-id="b4011-178">중재 서버의 두 인터페이스가 속한 IP 서브넷이 구성되고 네트워크 사이트 1과 연결되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="b4011-178">Make sure that the IP subnet that both interfaces of the Mediation Server belong to is configured and associated with Network Site 1.</span></span>

> [!NOTE]
> <span data-ttu-id="b4011-179">자세한 내용은 [Associate a Subnet with a Network Site](/previous-versions/office/lync-server-2013/lync-server-2013-associate-a-subnet-with-a-network-site)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="b4011-179">For details, see [Associate a Subnet with a Network Site](/previous-versions/office/lync-server-2013/lync-server-2013-associate-a-subnet-with-a-network-site).</span></span>