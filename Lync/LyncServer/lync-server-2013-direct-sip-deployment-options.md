---
title: 'Lync Server 2013: 직접 SIP 배포 옵션'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Direct SIP deployment options
ms:assetid: 84691944-03f2-4a89-9f2b-1ab3d7f388cc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398672(v=OCS.15)
ms:contentKeyID: 48184692
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7aaecb9bd7b5fc4f144236f83f85f9e1e192784f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48529115"
---
# <a name="direct-sip-deployment-options-in-lync-server-2013"></a><span data-ttu-id="15c2b-102">Lync Server 2013의 직접 SIP 배포 옵션</span><span class="sxs-lookup"><span data-stu-id="15c2b-102">Direct SIP deployment options in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="15c2b-103">_**마지막으로 수정 된 항목:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="15c2b-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="15c2b-104">이 항목에서는 직접 SIP 연결을 배포 하기 위한 예제 토폴로지를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="15c2b-104">This topic provides example topologies for deploying direct SIP connections.</span></span>

<div id="sectionSection0" class="section">

<span id="BKMK_CommunicationsServerStand_Alone"></span>

<div>

## <a name="lync-server-stand-alone"></a><span data-ttu-id="15c2b-105">Lync Server Stand-Alone</span><span class="sxs-lookup"><span data-stu-id="15c2b-105">Lync Server Stand-Alone</span></span>

<span data-ttu-id="15c2b-106">조직에서이 섹션에 설명 된 배포 중 하나를 사용 하는 경우 Lync Server 2013를 조직의 일부 또는 전체에 대 한 유일한 전화 통신 솔루션으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15c2b-106">If your organization uses one of the deployments described in this section, you can use Lync Server 2013 as the sole telephony solution for part or all of an organization.</span></span> <span data-ttu-id="15c2b-107">이 섹션에서는 다음 배포에 대해 자세히 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="15c2b-107">This section describes the following deployments in detail:</span></span>

  - <span data-ttu-id="15c2b-108">**증분 배포:** 이 옵션은 기존 PBX (private branch exchange) 인프라가 있고 조직 내의 더 작은 그룹 또는 팀에 엔터프라이즈 음성을 점진적으로 도입 하려는 경우를 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="15c2b-108">**Incremental deployment:** This option assumes that you have an existing private branch exchange (PBX) infrastructure and you intend to introduce Enterprise Voice incrementally to smaller groups or teams within your organization.</span></span>

  - <span data-ttu-id="15c2b-109">**Lync Server VoIP 전용 배포:** 이 옵션은 기존 전화 통신 인프라가 없는 사이트에서 Enterprise Voice를 배포 한다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="15c2b-109">**Lync Server VoIP-only deployment:** this option assumes that you are considering deploying Enterprise Voice at a site that does not have a traditional telephony infrastructure.</span></span>

<div>

## <a name="incremental-deployment"></a><span data-ttu-id="15c2b-110">증분 배포</span><span class="sxs-lookup"><span data-stu-id="15c2b-110">Incremental Deployment</span></span>

<span data-ttu-id="15c2b-111">증분 배포에서 Lync Server 2013은 개별 팀 또는 부서에 대 한 유일한 전화 통신 솔루션 이지만 조직의 나머지 사용자는 계속 해 서 PBX를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="15c2b-111">In incremental deployment, Lync Server 2013 is the sole telephony solution for individual teams or departments, while the rest of the users in an organization continue to use a PBX.</span></span> <span data-ttu-id="15c2b-112">이 증분 배포 전략은 제어 되는 파일럿 프로그램을 통해 기업에 IP 전화 통신을 도입 하는 한 가지 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="15c2b-112">This incremental deployment strategy provides one way to introduce IP telephony into your enterprise through controlled pilot programs.</span></span> <span data-ttu-id="15c2b-113">Microsoft 통합 통신에서 제공 하는 통신 요구 사항이 가장 적합 한 작업 그룹은 Enterprise Voice로 이동 되 고 다른 사용자는 기존 PBX에 남아 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15c2b-113">Workgroups whose communication needs are best served by Microsoft Unified Communications are moved to Enterprise Voice, while other users remain on the existing PBX.</span></span> <span data-ttu-id="15c2b-114">필요한 경우 추가 작업 그룹을 Enterprise Voice로 마이그레이션할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15c2b-114">Additional workgroups can be migrated to Enterprise Voice, as needed.</span></span>

<span data-ttu-id="15c2b-115">통신 요구 사항이 공통 되 고 중앙 집중식 관리에 도움이 되는 사용자 그룹을 명확 하 게 정의 해야 하는 경우에는 증분 옵션을 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="15c2b-115">The incremental option is recommended if you have clearly defined user groups that have communication requirements in common and that lend themselves to centralized management.</span></span> <span data-ttu-id="15c2b-116">또한이 옵션은 장거리 비용 절약이 중요할 수 있는 국내 지역에 흩어져 있는 팀 이나 부서가 있는 경우에도 효과적입니다.</span><span class="sxs-lookup"><span data-stu-id="15c2b-116">This option is also effective if you have teams or departments that are spread over wide geographic areas, where the savings in long-distance charges can be significant.</span></span> <span data-ttu-id="15c2b-117">실제로이 옵션은 구성원이 전 세계에 분산 될 수 있는 가상 팀을 만드는 데 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="15c2b-117">In fact, this option is useful for creating virtual teams whose members may be scattered across the globe.</span></span> <span data-ttu-id="15c2b-118">비즈니스 요구 사항 변화에 대 한 신속한 대응을 위해 이러한 팀을 만들거나 수정 하거나 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15c2b-118">You can create, modify, or disband such teams in rapid response to shifting business requirements.</span></span>

<span data-ttu-id="15c2b-119">다음 그림에서는 PBX 뒤에 Enterprise Voice를 배포 하기 위한 일반 토폴로지를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="15c2b-119">The following figure shows the generic topology for deployment of Enterprise Voice behind a PBX.</span></span> <span data-ttu-id="15c2b-120">다음은 증분 배포에 권장 되는 토폴로지입니다.</span><span class="sxs-lookup"><span data-stu-id="15c2b-120">This is the recommended topology for incremental deployment.</span></span>

<span data-ttu-id="15c2b-121">**증분 배포 옵션**</span><span class="sxs-lookup"><span data-stu-id="15c2b-121">**Incremental deployment option**</span></span>

<span data-ttu-id="15c2b-122">![부서별 마이그레이션 옵션 다이어그램](images/Gg398672.e951ecf4-7cd2-425a-9106-76977492d682(OCS.15).jpg "부서별 마이그레이션 옵션 다이어그램")</span><span class="sxs-lookup"><span data-stu-id="15c2b-122">![Departmental Migration Option diagram](images/Gg398672.e951ecf4-7cd2-425a-9106-76977492d682(OCS.15).jpg "Departmental Migration Option diagram")</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="15c2b-123">Lync Server 배포를 인증 된 직접 SIP 파트너에 연결 하는 경우 중재 서버와 PBX 사이에 PSTN (공중 전화망) 게이트웨이가 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="15c2b-123">If you are connecting your Lync Server deployment to a certified Direct SIP partner, a public switched telephone network (PSTN) gateway between the Mediation Server and the PBX is not required.</span></span> <span data-ttu-id="15c2b-124">인증 된 직접 SIP 파트너 목록은에서 Microsoft 통합 커뮤니케이션 오픈 상호 운용성 프로그램 웹 사이트를 참조 하세요 <A href="https://go.microsoft.com/fwlink/p/?linkid=203309">https://go.microsoft.com/fwlink/p/?linkId=203309</A> .</span><span class="sxs-lookup"><span data-stu-id="15c2b-124">For a list of certified Direct SIP partners, see the Microsoft Unified Communications Open Interoperability Program website at <A href="https://go.microsoft.com/fwlink/p/?linkid=203309">https://go.microsoft.com/fwlink/p/?linkId=203309</A>.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="15c2b-125">이 그림에 표시 된 미디어 경로는 미디어 바이패스 사용 (권장 구성)입니다.</span><span class="sxs-lookup"><span data-stu-id="15c2b-125">The media path shown in this figure has media bypass enabled (the recommended configuration).</span></span> <span data-ttu-id="15c2b-126">미디어 바이패스를 사용 하지 않도록 설정한 경우 미디어 경로가 중재 서버를 통해 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="15c2b-126">If you opt to disable media bypass, the media path is routed through the Mediation Server.</span></span>



</div>

<span data-ttu-id="15c2b-127">이 토폴로지에서는 선택한 부서나 작업 그룹이 Enterprise Voice를 사용 하도록 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="15c2b-127">In this topology, selected departments or workgroups are enabled for Enterprise Voice.</span></span> <span data-ttu-id="15c2b-128">PSTN 게이트웨이는 VoIP (Voice over Internet Protocol) 사용이 가능한 작업 그룹을 PBX에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="15c2b-128">A PSTN gateway links the Voice over Internet Protocol (VoIP)-enabled workgroup to the PBX.</span></span> <span data-ttu-id="15c2b-129">원격 작업자를 포함 하 여 Enterprise Voice를 사용할 수 있도록 설정 된 사용자는 IP 네트워크를 통해 통신 합니다.</span><span class="sxs-lookup"><span data-stu-id="15c2b-129">Users who are enabled for Enterprise Voice, including remote workers, communicate across the IP network.</span></span> <span data-ttu-id="15c2b-130">Enterprise voice 사용자가 PSTN으로 통화 하거나 Enterprise Voice를 사용 하도록 설정 하지 않은 동료에 게 해당 PSTN 게이트웨이로 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="15c2b-130">Calls by Enterprise Voice users to the PSTN and to coworkers who are not enabled for Enterprise Voice are routed to the appropriate PSTN gateway.</span></span> <span data-ttu-id="15c2b-131">PBX 시스템에 있는 동료 또는 PSTN의 발신자가 보낸 통화는 PSTN 게이트웨이로 라우팅되며이는 라우팅을 위해 Lync Server에 호출을 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="15c2b-131">Calls from colleagues who are still on the PBX system, or from callers on the PSTN, are routed to the PSTN gateway, which forwards the calls to Lync Server for routing.</span></span>

<span data-ttu-id="15c2b-132">Enterprise Voice를 기존 PBX 인프라에 연결 하는 데 사용할 수 있는 두 가지 권장 구성 (PBX 앞에 PBX 및 Enterprise Voice 뒤에 Enterprise voice)이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15c2b-132">There are two recommended configurations for connecting Enterprise Voice to an existing PBX infrastructure for interoperability: Enterprise Voice behind the PBX and Enterprise Voice in front of the PBX.</span></span>

<div>

## <a name="enterprise-voice-behind-the-pbx"></a><span data-ttu-id="15c2b-133">PBX 뒤의 Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="15c2b-133">Enterprise Voice Behind the PBX</span></span>

<span data-ttu-id="15c2b-134">Enterprise Voice가 PBX 뒤에 배포 되 면 PSTN 으로부터의 모든 전화가 PBX에 도착 하 여 Enterprise Voice 사용자에 게 통화를 PSTN 게이트웨이로 라우팅하고, pbx 사용자를 PBX로 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="15c2b-134">When Enterprise Voice is deployed behind the PBX, all calls from the PSTN arrive at the PBX, which routes calls to Enterprise Voice users to a PSTN gateway, and calls to PBX users to the PBX.</span></span>

</div>

<div>

## <a name="enterprise-voice-in-front-of-the-pbx"></a><span data-ttu-id="15c2b-135">PBX 앞의 Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="15c2b-135">Enterprise Voice in Front of the PBX</span></span>

<span data-ttu-id="15c2b-136">Enterprise Voice가 PBX 앞에 배포 되 면 모든 전화가 PSTN 게이트웨이에서 도착 하 여 Enterprise Voice 사용자에 대 한 통화를 Lync Server로 라우팅하고 pbx 사용자에 대 한 통화를 PBX에 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="15c2b-136">When Enterprise Voice is deployed in front of the PBX, all calls arrive at the PSTN gateway, which routes calls for Enterprise Voice users to Lync Server and calls for PBX users to the PBX.</span></span> <span data-ttu-id="15c2b-137">Enterprise Voice 및 PBX 사용자에 게 서 PSTN에 대 한 통화는 IP 네트워크를 통해 가장 비용 효율적인 PSTN 게이트웨이로 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="15c2b-137">Calls to the PSTN from both Enterprise Voice and PBX users are routed over the IP network to the most cost-efficient PSTN gateway.</span></span> <span data-ttu-id="15c2b-138">다음 표에서는이 구성의 장점과 단점을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="15c2b-138">The following table shows the advantages and disadvantages of this configuration.</span></span>

### <a name="advantages-and-disadvantages-of-deploying-enterprise-voice-in-front-of-pbx"></a><span data-ttu-id="15c2b-139">PBX 앞에 Enterprise Voice를 배포 하는 경우의 장점과 단점</span><span class="sxs-lookup"><span data-stu-id="15c2b-139">Advantages and Disadvantages of Deploying Enterprise Voice in Front of PBX</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="15c2b-140">장점</span><span class="sxs-lookup"><span data-stu-id="15c2b-140">Advantages</span></span></th>
<th><span data-ttu-id="15c2b-141">단점</span><span class="sxs-lookup"><span data-stu-id="15c2b-141">Disadvantages</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="15c2b-142">PBX는 여전히 Enterprise Voice를 사용 하도록 설정 되지 않은 사용자를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="15c2b-142">PBX still serves users not enabled for Enterprise Voice.</span></span></p></td>
<td><p><span data-ttu-id="15c2b-143">기존 게이트웨이가 원하는 기능이 나 용량을 지원 하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15c2b-143">Existing gateways may not support the features or capacity that you want.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15c2b-144">PBX는 이전의 모든 장치를 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="15c2b-144">PBX handles all earlier devices.</span></span></p></td>
<td><p><span data-ttu-id="15c2b-145">게이트웨이에서 PBX로 및 게이트웨이에서 중재 서버로의 트렁크가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="15c2b-145">Requires a trunk from gateway to the PBX and from the gateway to the Mediation Server.</span></span> <span data-ttu-id="15c2b-146">서비스 공급자 로부터 더 많은 트렁크 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15c2b-146">You may need more trunks from the service provider.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15c2b-147">Enterprise Voice 사용자는 동일한 전화 번호를 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="15c2b-147">Enterprise Voice users keep the same phone numbers.</span></span></p></td>
<td><p> </p></td>
</tr>
</tbody>
</table>


</div>

</div>

<div>

## <a name="lync-server-voip-only-deployment"></a><span data-ttu-id="15c2b-148">Lync Server VoIP-Only 배포</span><span class="sxs-lookup"><span data-stu-id="15c2b-148">Lync Server VoIP-Only Deployment</span></span>

<span data-ttu-id="15c2b-149">Enterprise Voice는 새로운 기업과 기존 비즈니스를 위한 새로운 office 사이트를 제공 하며, PBX 통합에 대 한 걱정 없이 전체 기능을 갖춘 VoIP 솔루션을 구현 하거나, IP PBX 인프라의 실질적인 배포 및 유지 관리 비용을 지불 하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="15c2b-149">Enterprise Voice provides new businesses, and also new office sites for existing businesses, with the opportunity to implement a full-featured VoIP solution without having to worry about PBX integration or incurring the substantial deployment and maintenance costs of an IP-PBX infrastructure.</span></span> <span data-ttu-id="15c2b-150">이 솔루션은 사이트 및 원격 작업자를 모두 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="15c2b-150">This solution supports both on-site and remote workers.</span></span>

<span data-ttu-id="15c2b-151">이 배포에서는 모든 통화가 IP 네트워크를 통해 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="15c2b-151">In this deployment, all calls are routed over the IP network.</span></span> <span data-ttu-id="15c2b-152">PSTN 통화는 적절 한 PSTN 게이트웨이로 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="15c2b-152">Calls to the PSTN are routed to the appropriate PSTN gateway.</span></span> <span data-ttu-id="15c2b-153">Lync 2013 또는 Lync Phone Edition은 softphone 역할을 합니다.</span><span class="sxs-lookup"><span data-stu-id="15c2b-153">Lync 2013 or Lync Phone Edition serves as a softphone.</span></span> <span data-ttu-id="15c2b-154">사용자가 제어할 PBX 전화가 없기 때문에 원격 통화 제어를 사용할 수 없으며 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="15c2b-154">Remote call control is unavailable and unnecessary because there are no PBX phones for users to control.</span></span> <span data-ttu-id="15c2b-155">음성 메일 및 자동 전화 교환 서비스는 Exchange UM (통합 메시징)의 선택적 배포를 통해 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="15c2b-155">Voice mail and auto-attendant services are available through the optional deployment of Exchange Unified Messaging (UM).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="15c2b-156">Lync Server 2013을 지 원하는 데 필요한 네트워크 인프라 외에, VoIP 전용 배포는 소규모의 자격 있는 게이트웨이를 사용 하 여 팩스 컴퓨터 및 아날로그 장치를 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15c2b-156">In addition to the network infrastructure that is required to support Lync Server 2013, a VoIP-only deployment can use a small, qualified gateway to support fax machines and analog devices.</span></span>



</div>

<span data-ttu-id="15c2b-157">다음 그림에서는 VoIP 전용 배포의 일반적인 토폴로지를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="15c2b-157">The following figure shows a typical topology for a VoIP-only deployment.</span></span>

<span data-ttu-id="15c2b-158">**VoIP 전용 배포 옵션**</span><span class="sxs-lookup"><span data-stu-id="15c2b-158">**VoIP-only deployment option**</span></span>

<span data-ttu-id="15c2b-159">![Greenfidle 배포 옵션](images/Gg398672.820dc5fe-0e20-431b-ae4e-fefdf2221d3b(OCS.15).jpg "Greenfidle 배포 옵션")</span><span class="sxs-lookup"><span data-stu-id="15c2b-159">![Greenfidle deployment option](images/Gg398672.820dc5fe-0e20-431b-ae4e-fefdf2221d3b(OCS.15).jpg "Greenfidle deployment option")</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="15c2b-160">이 그림에 표시 된 미디어 경로는 미디어 바이패스 사용 (권장 구성)입니다.</span><span class="sxs-lookup"><span data-stu-id="15c2b-160">The media path shown in this figure has media bypass enabled (the recommended configuration).</span></span> <span data-ttu-id="15c2b-161">미디어 바이패스를 사용 하지 않도록 설정한 경우 미디어 경로가 중재 서버를 통해 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="15c2b-161">If you opt to disable media bypass, the media path is routed through the Mediation Server.</span></span>



</div>

</div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

