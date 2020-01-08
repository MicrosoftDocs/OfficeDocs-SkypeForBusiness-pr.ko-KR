---
title: 'Lync Server 2013: 분기 사이트 복구 요구 사항'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Branch-site resiliency requirements
ms:assetid: a570922c-52bd-42d7-bd64-226578b3d110
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412772(v=OCS.15)
ms:contentKeyID: 48184984
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7ff969638f8c46abdd0ebcc8d11821a6a31b3c76
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980200"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="branch-site-resiliency-requirements-for-lync-server-2013"></a><span data-ttu-id="0ed48-102">Lync Server 2013에 대한 분기 사이트 복구 요구 사항</span><span class="sxs-lookup"><span data-stu-id="0ed48-102">Branch-site resiliency requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0ed48-103">_**마지막으로 수정한 주제:** 2014-02-25_</span><span class="sxs-lookup"><span data-stu-id="0ed48-103">_**Topic Last Modified:** 2014-02-25_</span></span>

<span data-ttu-id="0ed48-104">이 항목은 지점 사이트 복구 및 음성 메일 survivability 사용자를 준비 하는 데 도움이 되며 관련 하드웨어 및 소프트웨어 요구 사항도 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ed48-104">This topic will help you to prepare users for branch-site resiliency and voice mail survivability, and also specifies the relevant hardware and software requirements.</span></span>

<div>

## <a name="preparing-branch-users-for-branch-site-resiliency"></a><span data-ttu-id="0ed48-105">지점 사이트 복원에 대 한 분기 사용자 준비</span><span class="sxs-lookup"><span data-stu-id="0ed48-105">Preparing Branch Users for Branch-Site Resiliency</span></span>

<span data-ttu-id="0ed48-106">등록자 풀을 Survivable Branch 기기 (SBA) 또는 Survivable Branch 서버로 설정 하 여 지점 사이트 복원성에 대 한 사용자를 준비 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ed48-106">Prepare users for branch-site resiliency by setting their Registrar pool as the Survivable Branch Appliance (SBA) or Survivable Branch Server.</span></span>

<div>

## <a name="registrar-assignments-for-branch-users"></a><span data-ttu-id="0ed48-107">분기 사용자에 대 한 등록자 과제</span><span class="sxs-lookup"><span data-stu-id="0ed48-107">Registrar Assignments for Branch Users</span></span>

<span data-ttu-id="0ed48-108">어떤 지점 사이트 복원 솔루션을 선택 하 든 관계 없이 각 사용자에 게 기본 등록 기관을 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ed48-108">Regardless of which branch-site resiliency solution you choose, you will need to assign a primary Registrar to each user.</span></span> <span data-ttu-id="0ed48-109">지점 사이트 사용자는 구독자가 Survivable Branch 기기, Survivable Branch Server 또는 독립 실행형 Lync Server 2013 Standard 또는 Enterprise Edition 서버 중 어디에 있든 관계 없이 항상 지점 사이트의 등록자에 등록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ed48-109">Branch site users should always register with the Registrar at the branch site, regardless of whether that Registrar resides in the Survivable Branch Appliance, Survivable Branch Server, or stand-alone Lync Server 2013 Standard or Enterprise Edition server.</span></span> <span data-ttu-id="0ed48-110">클라이언트가 등록자 풀을 검색할 수 있도록 DNS (domain name system) 서비스 (SRV) 리소스 레코드가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ed48-110">A domain name system (DNS) service (SRV) resource record is required so that a client can discover its Registrar pool.</span></span> <span data-ttu-id="0ed48-111">Survivable Branch 기기를 사용할 수 없게 되 면 지점 사이트 클라이언트가 백업 등록자를 자동으로 검색 하 게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0ed48-111">If the Survivable Branch Appliance becomes unavailable, this is how branch site clients will automatically discover the backup Registrar.</span></span>

<span data-ttu-id="0ed48-112">지점 사이트에 DNS 서버가 없는 경우 다음과 같은 두 가지 방법으로 Survivable Branch 기기 또는 Survivable Branch 서버의 검색을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ed48-112">If a branch site does not have a DNS server, there are two alternative ways to configure discovery of the Survivable Branch Appliance or Survivable Branch Server:</span></span>

  - <span data-ttu-id="0ed48-113">Survivable Branch 기기 또는 Survivable Branch 서버의 FQDN (정규화 된 도메인 이름)을 가리키도록 지점 사이트의 동적 호스트 구성 프로토콜 (DHCP) 서버에서 DHCP option 120을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ed48-113">Configure DHCP option 120 on the branch site’s Dynamic Host Configuration Protocol (DHCP) server to point to the fully qualified domain name (FQDN) of the Survivable Branch Appliance or Survivable Branch Server.</span></span>

  - <span data-ttu-id="0ed48-114">DHCP 120 쿼리에 응답 하도록 Survivable Branch 기기 또는 Survivable Branch 서버를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ed48-114">Configure the Survivable Branch Appliance or Survivable Branch Server to respond to DHCP 120 queries.</span></span>

</div>

<div>

## <a name="voice-routing-for-branch-users"></a><span data-ttu-id="0ed48-115">지사 사용자를 위한 음성 라우팅</span><span class="sxs-lookup"><span data-stu-id="0ed48-115">Voice Routing for Branch Users</span></span>

<span data-ttu-id="0ed48-116">지사 사이트의 사용자를 위해 별도의 사용자 수준 Voice over 인터넷 프로토콜 (VoIP) 정책을 만드는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="0ed48-116">We recommend that you create a separate user-level Voice over Internet Protocol (VoIP) policy for users in a branch site.</span></span> <span data-ttu-id="0ed48-117">이 정책에는 Survivable Branch 기기 또는 지사 서버 게이트웨이를 사용 하는 기본 경로와 중앙 사이트의 PSTN (공개 교환 통신망) 게이트웨이로 트렁크를 사용 하는 하나 이상의 백업 경로가 포함 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ed48-117">This policy should include a primary route that uses the Survivable Branch Appliance or branch server gateway, and one or more backup routes that use a trunk with a public switched telephone network (PSTN) gateway at the central site.</span></span> <span data-ttu-id="0ed48-118">주 경로를 사용할 수 없는 경우 하나 또는 그 이상의 중앙 사이트 게이트웨이를 사용 하는 백업 경로가 대신 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0ed48-118">If the primary route is unavailable, the backup route that uses one or more central site gateways is used instead.</span></span> <span data-ttu-id="0ed48-119">이 방법은 사용자가 등록 된 위치 (지점 사이트 등록자 또는 중앙 사이트의 백업 등록자 풀)에 관계 없이 사용자의 VoIP 정책이 항상 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0ed48-119">This way, regardless of where a user is registered—on the branch site Registrar or the backup Registrar pool at the central site—the user’s VoIP policy is always in effect.</span></span> <span data-ttu-id="0ed48-120">이는 장애 조치 시나리오에 대 한 중요 한 고려 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="0ed48-120">This is an important consideration for failover scenarios.</span></span> <span data-ttu-id="0ed48-121">예를 들어 Survivable Branch 기기의 이름을 바꾸거나 중앙 사이트의 백업 등록자 풀에 연결 하도록 Survivable Branch 기기를 다시 구성 해야 하는 경우에는 분기 사이트 사용자를 해당 기간 동안 중앙 사이트로 이동 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ed48-121">For example, if you need to rename the Survivable Branch Appliance or reconfigure the Survivable Branch Appliance to connect to a backup Registrar pool at the central site, then you must move branch site users to the central site for the duration.</span></span> <span data-ttu-id="0ed48-122">(Survivable 분기 기기의 이름 바꾸기 또는 재구성에 대 한 자세한 내용은 [부록 B: 배포 설명서의 Lync Server 2013에서 Survivable Branch 어플라이언스 관리](lync-server-2013-appendix-b-managing-a-survivable-branch-appliance.md) 를 참조 하세요.) 해당 사용자가 사용자 수준 VoIP 정책 또는 사용자 수준 다이얼 플랜을 보유 하 고 있지 않은 경우, 사용자가 다른 사이트로 이동할 때 중앙 사이트의 사이트 수준 VoIP 정책 및 사이트 수준 다이얼 플랜이 사용자에 게 기본적으로 지사 사이트의 사이트 수준 VoIP 정책 및 다이얼 플랜에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0ed48-122">(For details about renaming or reconfiguring a Survivable Branch Appliance, see [Appendix B: Managing a Survivable Branch Appliance in Lync Server 2013](lync-server-2013-appendix-b-managing-a-survivable-branch-appliance.md) in the Deployment documentation.) If those users do not have user-level VoIP policies or user-level dial plans, when the users are moved to another site, the site-level VoIP policies and site-level dial plans of the central site apply to the users by default, instead of the branch site site-level VoIP policies and dial plans,.</span></span> <span data-ttu-id="0ed48-123">이 시나리오에서는 백업 등록자 풀에서 사용 되는 사이트 수준 VoIP 정책 및 사이트 수준 다이얼 플랜이 지점 사이트 사용자에 게 적용 될 수 있는 경우가 아니면 해당 통화는 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ed48-123">In this scenario, unless the site-level VoIP policies and site-level dial plans used by the backup Registrar pool can also apply to the branch site users, their calls will fail.</span></span> <span data-ttu-id="0ed48-124">예를 들어 일본에 있는 분기 사이트의 사용자가 Redmond의 중앙 사이트로 이동 하는 경우, 모든 7 자리 통화에 + 1425를 앞에 배치 하는 정규화 규칙을 사용 하는 다이얼 플랜은 해당 사용자에 대 한 통화를 적절 하 게 번역 하지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="0ed48-124">For example, if users from a branch site located in Japan are moved to a central site in Redmond, then a dial plan with normalization rules that prepend +1425 to all 7-digit calls is unlikely to appropriately translate calls for those users.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="0ed48-125">지점 백업 경로를 만들 때는 지점 사용자 정책에 두 개의 PSTN 전화 사용 레코드를 추가 하 고 각 경로에 별도의 route를 할당 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="0ed48-125">When you create a branch office backup route, we recommend that you add two PSTN phone usage records to the branch office user policy and assign separate routes to each one.</span></span> <span data-ttu-id="0ed48-126">첫 번째 또는 기본 경로는 Survivable Branch (지사) 기기 (SBA) 또는 Branch 서버와 연결 된 게이트웨이에 직접 호출 합니다. 두 번째 또는 백업 경로는 중앙 사이트의 게이트웨이로 직접 전화를 거는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="0ed48-126">The first, or primary, route would direct calls to the gateway associated with the Survivable Branch Appliance (SBA) or branch server; the second, or backup, route would direct calls to the gateway at the central site.</span></span> <span data-ttu-id="0ed48-127">통화를 전송 하는 동안 SBA 또는 branch 서버는 두 번째 사용 레코드를 시도 하기 전에 첫 번째 PSTN 사용 레코드에 할당 된 모든 경로를 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ed48-127">In directing calls, the SBA or branch server will attempt all routes assigned to the first PSTN usage record before attempting the second usage record.</span></span>



</div>

<span data-ttu-id="0ed48-128">지점 게이트웨이 또는 Survivable Branch 기기 사이트의 Windows 구성 요소 (예: Survivable Branch 기기 또는 분기)를 사용할 수 없는 경우 지점 사이트 사용자에 게 들어오는 인바운드 호출이 해당 사용자에 게 연결 되도록 하려면 다음을 수행 합니다. 유지 관리를 위해 게이트웨이가 종료 된 경우), 게이트웨이에서 장애 조치 경로를 만들거나 (또는 직접 안쪽 전화 접속 (시작) 공급자와 함께 작업) 수신 전화를 중앙 사이트의 백업 등록자 풀로 리디렉션합니다.</span><span class="sxs-lookup"><span data-stu-id="0ed48-128">To help ensure that inbound calls to branch site users will reach those users when the branch gateway or the Windows component of the Survivable Branch Appliance site is unavailable (which would happen, for example, if the Survivable Branch Appliance or branch gateway were down for maintenance), create a failover route on the gateway (or work with your Direct Inward Dialing (DID) provider) to redirect incoming calls to the backup Registrar pool at the central site.</span></span> <span data-ttu-id="0ed48-129">여기서는 WAN 링크를 통해 호출이 지사 사용자에 게 전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0ed48-129">From there, the calls will be routed over the WAN link to branch users.</span></span> <span data-ttu-id="0ed48-130">경로는 PSTN 게이트웨이 또는 기타 트렁크 피어의 허용 된 전화 번호 형식에 맞게 숫자를 변환 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ed48-130">Be sure that the route translates numbers to comply with the PSTN gateway or other trunk peer’s accepted phone number formats.</span></span> <span data-ttu-id="0ed48-131">장애 조치 경로를 만드는 방법에 대 한 자세한 내용은 [Lync Server 2013에서 장애 조치 경로 구성을](lync-server-2013-configuring-a-failover-route.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0ed48-131">For details about creating a failover route, see [Configuring a failover route in Lync Server 2013](lync-server-2013-configuring-a-failover-route.md).</span></span> <span data-ttu-id="0ed48-132">또한 지사 사이트에서 게이트웨이와 연결 된 트렁크에 대 한 서비스 수준 다이얼 플랜을 만들어 걸려오는 전화를 표준화 하세요.</span><span class="sxs-lookup"><span data-stu-id="0ed48-132">Also create service-level dial plans for the trunk associated with the gateway at the branch site to normalize incoming calls.</span></span> <span data-ttu-id="0ed48-133">지점 사이트에 두 개의 Survivable Branch 기기가 있는 경우 각각에 대해 별도의 서비스 수준 계획이 필요한 경우가 아니면 사이트 수준 다이얼 플랜을 둘 다에 대해 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ed48-133">If you have two Survivable Branch Appliances at a branch site, you can create a site-level dial plan for both unless a separate service-level plan for each is necessary.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0ed48-134">현재 상태, 회의 또는 장애 조치를 위해 중앙 사이트를 사용 하는 지점 사이트 사용자의 중앙 사이트 리소스 소모량을 고려 하려면 사용자가 중앙 사이트에 등록 된 것 처럼 각 지점 사이트 사용자를 고려 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="0ed48-134">To account for the consumption of central site resources by any branch site users that rely on the central site for presence, conferencing, or failover, we recommend that you consider each branch site user as if the user were registered with the central site.</span></span> <span data-ttu-id="0ed48-135">현재 Survivable Branch 기기를 사용 하 여 등록 된 사용자를 포함 하 여 지점 사이트 사용자 수에는 제한이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0ed48-135">There are currently no limits on the number of branch site users, including users registered with a Survivable Branch Appliance.</span></span>



</div>

<span data-ttu-id="0ed48-136">또한 사용자 수준 다이얼 플랜 및 음성 정책을 만든 다음 지점 사이트 사용자에 게 할당 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="0ed48-136">We also recommend that you create a user-level dial plan and voice policy, and then assign it to branch site users.</span></span> <span data-ttu-id="0ed48-137">자세한 내용은 [Lync server 2013에서 다이얼 플랜 만들기](lync-server-2013-create-a-dial-plan.md) 를 참조 하 고 배포 설명서의 [lync server 2013에서 분기 사용자를 위한 VoIP 라우팅 정책을 만듭니다](lync-server-2013-create-the-voip-routing-policy-for-branch-users.md) .</span><span class="sxs-lookup"><span data-stu-id="0ed48-137">For details, see [Create a dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md) and [Create the VoIP routing policy for branch users in Lync Server 2013](lync-server-2013-create-the-voip-routing-policy-for-branch-users.md) in the Deployment documentation.</span></span>

<div>

## <a name="routing-extension-numbers"></a><span data-ttu-id="0ed48-138">라우팅 내선 번호</span><span class="sxs-lookup"><span data-stu-id="0ed48-138">Routing Extension Numbers</span></span>

<span data-ttu-id="0ed48-139">지사 사이트 사용자를 위한 다이얼 플랜 및 음성 정책을 준비 하는 경우 msRTCSIP line (또는 Line URI) 특성에 사용 되는 문자열 및 숫자 형식과 일치 하는 정규화 규칙 및 번역 규칙을 포함 하 여 분기 간에 Lync 2013를 사용할 수 있도록 해야 합니다. WAN 링크를 사용할 수 없기 때문에 사이트 사용자와 중앙 사이트 사용자는 특히 PSTN을 통해 착신 전환 해야 하는 경우 제대로 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="0ed48-139">When preparing dial plans and voice policies for branch site users, be sure to include normalization rules and translation rules that match the strings and number format used in the msRTCSIP-line (or Line URI) attribute, so that Lync 2013 calls enabled between branch site users and central site users will be routed correctly—particularly when calls must be rerouted over the PSTN because the WAN link is unavailable.</span></span> <span data-ttu-id="0ed48-140">또한 전화 번호 대신 내선 번호를 포함 하는 전화 번호에 대 한 특별 한 고려 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ed48-140">Additionally, there are special considerations for dialed numbers that include extension numbers, rather just phone numbers.</span></span>

<span data-ttu-id="0ed48-141">내선 번호를 포함 하는 줄 Uri와 일치 하는 정규화 규칙 및 번역 규칙으로, 전체 전자 164 개의 전화 번호에 대해 독점적으로 또는 그 외에 추가 요구 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ed48-141">Normalization rules and translations rules that match Line URIs that contain an extension number, whether exclusively or in addition to a full E.164 phone number, have additional requirements.</span></span> <span data-ttu-id="0ed48-142">이 섹션에서는 줄 Uri에 대 한 호출을 내선 번호로 라우팅하는 몇 가지 예제 시나리오에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ed48-142">This section describes several example scenarios to route calls for Line URIs with an extension number.</span></span>

<span data-ttu-id="0ed48-143">조직에 개별 사용자에 대해 구성 된 직접적인 내부 다이얼 (\*) 전화 번호가 없고 각 사용자의 회선 URI가 내선 번호로 *만* 구성 되어 있는 경우 내부 사용자는 내선 번호로만 전화를 걸어 다른 사람에 게 전화를 걸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ed48-143">If your organization does not have Direct Inward Dial (DID) phone numbers configured for individual users and the Line URI of each user is configured with *only* an extension number, internal users can call one another by dialing only an extension number.</span></span> <span data-ttu-id="0ed48-144">그러나, 확장 번호와 일치 하는 지점 사이트 사용자에 게 중앙 사이트 사용자에 게 적용할 수 있는 정규화 규칙을 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ed48-144">However, you must configure normalization rules that can apply to calls from a branch site user to a central site user, that match the extension numbers.</span></span>

<span data-ttu-id="0ed48-145">지점 사이트와 중앙 사이트 간의 WAN 연결을 사용할 수 있는 경우 지사 사이트 사용자에 게 중앙 사이트 사용자에 게 전화를 거는 경우, 통화가 PSTN을 통해 라우팅되지 않기 때문에 일치 하는 정규화 규칙으로 해당 번호를 번역 하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0ed48-145">In a scenario where the WAN link between a branch site and a central site is available, calls from branch site users to central site users do not require the matching normalization rule to translate the number because the call is not routed over the PSTN.</span></span> <span data-ttu-id="0ed48-146">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="0ed48-146">For example:</span></span>


<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0ed48-147">규칙 이름</span><span class="sxs-lookup"><span data-stu-id="0ed48-147">Rule name</span></span></th>
<th><span data-ttu-id="0ed48-148">설명</span><span class="sxs-lookup"><span data-stu-id="0ed48-148">Description</span></span></th>
<th><span data-ttu-id="0ed48-149">번호 패턴</span><span class="sxs-lookup"><span data-stu-id="0ed48-149">Number pattern</span></span></th>
<th><span data-ttu-id="0ed48-150">변환용</span><span class="sxs-lookup"><span data-stu-id="0ed48-150">Translation</span></span></th>
<th><span data-ttu-id="0ed48-151">예</span><span class="sxs-lookup"><span data-stu-id="0ed48-151">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0ed48-152">5digitExtensions</span><span class="sxs-lookup"><span data-stu-id="0ed48-152">5digitExtensions</span></span></p></td>
<td><p><span data-ttu-id="0ed48-153">다섯 자리 숫자를 변환 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0ed48-153">Does not translate 5-digit numbers</span></span></p></td>
<td><p><span data-ttu-id="0ed48-154">^ (\d{5}) $</span><span class="sxs-lookup"><span data-stu-id="0ed48-154">^(\d{5})$</span></span></p></td>
<td><p><span data-ttu-id="0ed48-155">$1</span><span class="sxs-lookup"><span data-stu-id="0ed48-155">$1</span></span></p></td>
<td><p><span data-ttu-id="0ed48-156">10001가 번역 되지 않음</span><span class="sxs-lookup"><span data-stu-id="0ed48-156">10001 is not translated</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="0ed48-157">또한 지사 사이트와 중앙 사이트 간 WAN 연결을 사용할 수 없고 지점 사이트의 호출을 PSTN을 통해 라우팅해야 하는 경우와 같이 특정 시나리오에 대 한 내선 번호를 반드시 수용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ed48-157">You must also accommodate extension numbers for specific scenarios, such as when the WAN link between a branch site and central site is unavailable and a call from a branch site must be routed over the PSTN.</span></span> <span data-ttu-id="0ed48-158">WAN을 중단 하는 동안 중앙 사이트 사용자의 내선 번호로 전화를 걸어 중앙 사이트 사용자를 호출 하는 경우 중앙 사이트 사용자의 전체 전화 번호를 추가 하는 아웃 바운드 변환 규칙이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ed48-158">During a WAN outage, if a branch site user calls a central site user only by dialing the central site user’s extension, you must have an outbound translation rule that adds the central site user’s full phone number.</span></span> <span data-ttu-id="0ed48-159">사용자의 회선 URI에 조직의 전체 전화 번호와 사용자 고유의 사용자 고유 내선 번호가 포함 되어 있는 경우, 대신 조직의 전체 전화 번호를 추가 하는 아웃 바운드 번역 규칙이 있어야 합니다. .</span><span class="sxs-lookup"><span data-stu-id="0ed48-159">If a user’s Line URI contains your organization’s full phone number and the user’s unique extension number instead of a full phone number that is unique to the user, then you must have an outbound translation rule that adds your organization’s full phone number instead.</span></span> <span data-ttu-id="0ed48-160">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="0ed48-160">For example:</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0ed48-161">설명</span><span class="sxs-lookup"><span data-stu-id="0ed48-161">Description</span></span></th>
<th><span data-ttu-id="0ed48-162">일치 패턴</span><span class="sxs-lookup"><span data-stu-id="0ed48-162">Matching pattern</span></span></th>
<th><span data-ttu-id="0ed48-163">변환용</span><span class="sxs-lookup"><span data-stu-id="0ed48-163">Translation</span></span></th>
<th><span data-ttu-id="0ed48-164">예</span><span class="sxs-lookup"><span data-stu-id="0ed48-164">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0ed48-165">다섯 자리 숫자를 사용자의 전화 번호 및 확장명으로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ed48-165">Translates 5-digit numbers to a user’s phone number and extension</span></span></p></td>
<td><p><span data-ttu-id="0ed48-166">^ (\d{5}) $</span><span class="sxs-lookup"><span data-stu-id="0ed48-166">^(\d{5})$</span></span></p></td>
<td><p><span data-ttu-id="0ed48-167">+ 14255550123; ext = $1</span><span class="sxs-lookup"><span data-stu-id="0ed48-167">+14255550123;ext=$1</span></span></p></td>
<td><p><span data-ttu-id="0ed48-168">10001는 + 14255550123, ext = 10001로 변환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0ed48-168">10001 is translated to +14255550123;ext=10001</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0ed48-169">다섯 자리 숫자를 조직의 전화번호와 사용자의 내선 번호로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ed48-169">Translates 5-digit numbers to your organization’s phone number and a user’s extension</span></span></p></td>
<td><p><span data-ttu-id="0ed48-170">^ (\d{5}) $</span><span class="sxs-lookup"><span data-stu-id="0ed48-170">^(\d{5})$</span></span></p></td>
<td><p><span data-ttu-id="0ed48-171">+ 14255550100; ext = $1</span><span class="sxs-lookup"><span data-stu-id="0ed48-171">+14255550100;ext=$1</span></span></p></td>
<td><p><span data-ttu-id="0ed48-172">10001는 + 14255550100, ext = 10001로 변환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0ed48-172">10001 is translated to +14255550100;ext=10001</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="0ed48-173">이 시나리오에서는 PSTN으로 경로 전환 처리 하는 트렁크 피어가 내선 번호를 지원 하지 않는 경우 아웃 바운드 변환 규칙도 내선 번호를 제거 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ed48-173">In this scenario, if the trunk peer that handles rerouting to the PSTN does not support extension numbers, then the outbound translation rule must also remove the extension number.</span></span> <span data-ttu-id="0ed48-174">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="0ed48-174">For example:</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0ed48-175">설명</span><span class="sxs-lookup"><span data-stu-id="0ed48-175">Description</span></span></th>
<th><span data-ttu-id="0ed48-176">일치 패턴</span><span class="sxs-lookup"><span data-stu-id="0ed48-176">Matching pattern</span></span></th>
<th><span data-ttu-id="0ed48-177">변환용</span><span class="sxs-lookup"><span data-stu-id="0ed48-177">Translation</span></span></th>
<th><span data-ttu-id="0ed48-178">예</span><span class="sxs-lookup"><span data-stu-id="0ed48-178">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0ed48-179">확장명을 사용 하 여 전화 번호에서 확장명 제거</span><span class="sxs-lookup"><span data-stu-id="0ed48-179">Removes extension from phone numbers with extensions</span></span></p></td>
<td><p><span data-ttu-id="0ed48-180">^\+(\d *); ext = (\d*) $</span><span class="sxs-lookup"><span data-stu-id="0ed48-180">^\+(\d *);ext=(\d*)$</span></span></p></td>
<td><p><span data-ttu-id="0ed48-181">+ $1</span><span class="sxs-lookup"><span data-stu-id="0ed48-181">+$1</span></span></p></td>
<td><p><span data-ttu-id="0ed48-182">+ 14255550123; ext = 10001는 + 14255550123로 변환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0ed48-182">+14255550123;ext=10001 is translated to +14255550123</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="0ed48-183">WAN 링크를 사용할 수 있는지 여부, 조직에 개별 사용자에 대해 구성 된 번호가 없고 사용자의 회선 URI에 조직의 전화 번호와 사용자의 고유 내선 번호가 포함 되어 있는 경우 다음을 구성 해야 합니다. 조직의 전화 번호 줄 URI (지점 사이트의 트렁크 피어 또는 PSTN 게이트웨이에서 도달할 수 있는 번호).</span><span class="sxs-lookup"><span data-stu-id="0ed48-183">Whether or not a WAN link is available, if your organization does not have DID numbers configured for individual users and the Line URI for a user contains your organization’s phone number and the user’s unique extension number, then you must configure your organization’s phone number Line URI with a number that is reachable by the trunk peer or PSTN gateway at the branch site.</span></span> <span data-ttu-id="0ed48-184">또한 해당 번호로 라우팅할 전화에 고유한 확장명을 포함 하도록 조직의 전화 번호 줄 URI를 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ed48-184">You must also configure your organization’s phone number Line URI to include its own unique extension for calls to be routed to that number.</span></span>

<span data-ttu-id="0ed48-185">사이트 간 WAN 연결을 사용할 수 없는 경우 중앙 사이트 사용자에서 지사 사이트 사용자에 게 전화를 거는 방법에 대 한 자세한 내용은이 항목의 뒷부분에 나오는 "음성 메일 Survivability 준비"를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0ed48-185">For details about calls from a central site user to a branch site user when the WAN link between the sites is unavailable, see "Preparing for Voice Mail Survivability" later in this topic.</span></span> <span data-ttu-id="0ed48-186">다른 샘플 규칙을 비롯 한 다이얼 플랜 및 정규화 규칙에 대 한 자세한 내용은 계획 설명서의 [Lync server 2013에서 다이얼 플랜 및 정규화 규칙](lync-server-2013-dial-plans-and-normalization-rules.md) 을 참조 하 고 배포 설명서의 [lync server 2013에서 다이얼 플랜 구성](lync-server-2013-configuring-dial-plans.md) 을 참고 하세요.</span><span class="sxs-lookup"><span data-stu-id="0ed48-186">For details about dial plans and normalization rules, including other sample rules, see [Dial plans and normalization rules in Lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md) in the Planning documentation and [Configuring dial plans in Lync Server 2013](lync-server-2013-configuring-dial-plans.md) in the Deployment documentation.</span></span> <span data-ttu-id="0ed48-187">아웃 바운드 번역 규칙에 대 한 자세한 내용은 계획 설명서의 [Lync server 2013에서 번역 규칙](lync-server-2013-translation-rules.md) 을 참조 하 고, 배포 설명서의 [lync server 2013에서 번역 규칙을 정의](lync-server-2013-defining-translation-rules.md) 하세요.</span><span class="sxs-lookup"><span data-stu-id="0ed48-187">For details about outbound translation rules, see [Translation rules in Lync Server 2013](lync-server-2013-translation-rules.md) in the Planning documentation and [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>

</div>

</div>

</div>

<div>

## <a name="preparing-for-voice-mail-survivability"></a><span data-ttu-id="0ed48-188">음성 메일 Survivability 준비</span><span class="sxs-lookup"><span data-stu-id="0ed48-188">Preparing for Voice Mail Survivability</span></span>

<span data-ttu-id="0ed48-189">Exchange UM (통합 메시징)은 일반적으로 지점 사이트가 아니라 중앙 사이트에만 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0ed48-189">Exchange Unified Messaging (UM) is usually installed only at a central site and not at branch sites.</span></span> <span data-ttu-id="0ed48-190">지사 사이트와 중앙 사이트 간의 WAN 연결을 사용할 수 없는 경우에도 발신자는 음성 메일 메시지를 남길 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ed48-190">A caller should be able to leave a voice mail message, even if the WAN link between branch site and central site is unavailable.</span></span> <span data-ttu-id="0ed48-191">따라서 지사 사이트 사용자를 위해 음성 메일을 제공 하는 Exchange UM 자동 전화 교환 전화 번호에 대 한 회선 URI를 구성 하는 경우 음성 정책, 다이얼 플랜 및 해당 음성 메일에 적용 되는 정규화 규칙 외에 특별 한 고려 사항이 필요 합니다. 숫자로.</span><span class="sxs-lookup"><span data-stu-id="0ed48-191">As a result, configuring the Line URI for the Exchange UM Auto Attendant phone number that provides voice mail for branch site users requires special considerations, in addition to the voice policy, dial plan, and normalization rules applicable to that voice mail number.</span></span>

<span data-ttu-id="0ed48-192">Survivable branch 기기 (SBAs) 및 Survivable Branch 서버는 WAN을 중단 하는 동안 분기 사용자를 위해 음성 메일 survivability을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ed48-192">Survivable Branch Appliances (SBAs) and Survivable Branch Servers provide voice mail survivability for branch users during a WAN outage.</span></span> <span data-ttu-id="0ed48-193">특히 Survivable Branch 기기 또는 Survivable Branch 서버를 사용 하는 경우 WAN을 사용할 수 없게 되 면 SBA 또는 Survivable Branch 서버는 PSTN을 통해 중앙 사이트의 Exchange UM에 대 한 응답 하지 않은 통화를 다시 라우팅합니다.</span><span class="sxs-lookup"><span data-stu-id="0ed48-193">Specifically, if you are using a Survivable Branch Appliance or Survivable Branch Server and the WAN becomes unavailable, the SBA or Survivable Branch Server reroutes unanswered calls over the PSTN to Exchange UM at the central site.</span></span> <span data-ttu-id="0ed48-194">SBA 또는 Survivable Branch 서버를 사용 하는 경우 사용자는 WAN을 중단 하는 동안 PSTN을 통해 음성 메일 메시지를 검색할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ed48-194">With a SBA or Survivable Branch Server, users can also retrieve voice mail messages through the PSTN during a WAN outage.</span></span> <span data-ttu-id="0ed48-195">마지막으로 WAN이 중단 되는 동안 Survivable Branch 기기 또는 Survivable Branch 서버는 부재 중 통화 알림을 큐에 대기 시키고 WAN이 복원 되 면 Exchange UM 서버에 업로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ed48-195">Finally, during a WAN outage the Survivable Branch Appliance or Survivable Branch Server queues missed-call notifications and then uploads them to the Exchange UM server when the WAN is restored.</span></span> <span data-ttu-id="0ed48-196">음성 메일 전환에 탄력적으로 대처할 수 있도록 하려면 중앙 사이트 풀의 FQDN에 대 한 항목과 Edge 서버 FQDN에 대 한 항목을 Survivable Branch 서버의 hosts 파일에 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ed48-196">To help ensure that voice mail rerouting is resilient, be sure that you add an entry for the central site pool’s FQDN and an entry for the Edge Server FQDN to the hosts file on the Survivable Branch Server.</span></span> <span data-ttu-id="0ed48-197">그렇지 않으면 지점 사이트에 DNS 서버가 없을 경우 DNS 확인에 시간이 초과 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ed48-197">Otherwise, DNS resolution can time out if you do not have a DNS server at the branch site.</span></span>

<span data-ttu-id="0ed48-198">지사 사이트 사용자를 위해 음성 메일 survivability에 대해 다음 구성을 권장 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ed48-198">We recommend the following configurations for voice mail survivability for branch site users:</span></span>

  - <span data-ttu-id="0ed48-199">Microsoft Exchange 관리자가 메시지를 수락 하도록 Exchange UM 자동 전화 교환 (AA)을 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ed48-199">An Microsoft Exchange administrator should configure Exchange UM Auto Attendant (AA) to accept messages only.</span></span> <span data-ttu-id="0ed48-200">이 구성은 사용자에 게 전송 또는 교환원에 게 이전 하는 등의 다른 모든 일반 기능을 사용 하지 않도록 설정 하 고, AA가 메시지를 허용 하도록 제한 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ed48-200">This configuration disables all other generic functionality, such as transfer to a user or transfer to an operator, and limits the AA to only accepting messages.</span></span> <span data-ttu-id="0ed48-201">또는 Exchange 관리자가 일반 AA 또는 AA 사용자 지정을 사용 하 여 통화를 교환원에 게 라우팅할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ed48-201">Alternatively, the Exchange administrator can use a generic AA or an AA customized to route the call to an operator.</span></span>

  - <span data-ttu-id="0ed48-202">Lync Server 관리자는 AA 전화 번호를 사용 하 여 Survivable Branch 기기 또는 branch 서버에 대 한 음성 메일 다시 라우팅 설정의 **exchange um 자동 전화 교환** 번호로 해당 전화 번호를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ed48-202">The Lync Server administrator should take the AA phone number and use that phone number as the **exchange um auto attendant** number in the voice mail rerouting settings for the Survivable Branch Appliance or branch server.</span></span>

  - <span data-ttu-id="0ed48-203">Lync Server 관리자는 Exchange UM 구독자 액세스 전화 번호를 받고이 번호를 Survivable Branch 기기 또는 Survivable Branch 서버에 대 한 음성 메일 다시 라우팅 설정의 **구독자 액세스** 번호로 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ed48-203">The Lync Server administrator should get the Exchange UM subscriber access phone number and use that number as the **subscriber access** number in the voice mail rerouting settings for the Survivable Branch Appliance or Survivable Branch Server.</span></span>

  - <span data-ttu-id="0ed48-204">Lync Server 관리자는 하나의 다이얼 플랜이 WAN을 중단 하는 동안 음성 메일에 액세스 해야 하는 모든 분기 사용자와 연결 되도록 Exchange UM을 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ed48-204">The Lync Server administrator should configure Exchange UM so that only one dial plan is associated with all branch users who need access to voice mail during a WAN outage.</span></span>

  - <span data-ttu-id="0ed48-205">WAN 링크를 사용할 수 없는 경우 지사 사이트 사용자에 게 전화를 거는 것은 사용자의 Exchange UM (통합 메시징) 음성 사서함으로 라우팅되지만, 통화에 적용 된 음성 정책에는 고유한 음성 메일 전화 번호가 지정 되어 있으며 확장명을 포함 하지 않는 경우에만 가능 합니다. 숫자로.</span><span class="sxs-lookup"><span data-stu-id="0ed48-205">When the WAN link is unavailable, calls to branch site users can be routed to the user’s Exchange Unified Messaging (UM) voice mailbox, but only if the voice policy applied to the call specifies a voice mail phone number that is unique and does not include an extension number.</span></span>

</div>

<div>

## <a name="hardware-and-software-requirements-for-branch-site-resiliency"></a><span data-ttu-id="0ed48-206">지점 사이트 복구를 위한 하드웨어 및 소프트웨어 요구 사항</span><span class="sxs-lookup"><span data-stu-id="0ed48-206">Hardware and Software Requirements for Branch-Site Resiliency</span></span>

<span data-ttu-id="0ed48-207">하드웨어 및 소프트웨어 요구 사항은 복원 솔루션에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="0ed48-207">The hardware and software requirements vary, depending on your resiliency solution.</span></span>

<div>

## <a name="requirements-for-survivable-branch-appliances"></a><span data-ttu-id="0ed48-208">Survivable 분기 기기에 대 한 요구 사항</span><span class="sxs-lookup"><span data-stu-id="0ed48-208">Requirements for Survivable Branch Appliances</span></span>

<span data-ttu-id="0ed48-209">필수 하드웨어 및 소프트웨어는 Survivable Branch 기기에 기본 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0ed48-209">Required hardware and software is built into the Survivable Branch Appliance.</span></span> <span data-ttu-id="0ed48-210">그러나 각 지점 사이트에서 클라이언트 IP 주소를 얻을 수 있도록 DHCP 서버를 배포 하는 것이 좋습니다. 그렇지 않으면 DHCP 임대가 만료 될 때 클라이언트는 IP 연결을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0ed48-210">However, we also recommend that each branch site deploy a DHCP server to obtain client IP addresses; otherwise, when the DHCP lease expires, clients will not have IP connectivity.</span></span>

<span data-ttu-id="0ed48-211">중앙 사이트에만 엔터프라이즈 DNS 서버가 있는 경우 지점 사이트 사용자는 WAN을 중단 하는 동안 연결할 수 없으며 DNS SRV (서비스 (SRV) 리소스 레코드)를 사용 하는 Lync Server 검색에 실패 하 게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0ed48-211">If the enterprise DNS servers are located only in central sites, branch site users will be unable to connect to them during a WAN outage, and therefore Lync Server discovery that uses DNS SRV (service (SRV) resource record) will fail.</span></span> <span data-ttu-id="0ed48-212">WAN을 중단 하는 동안 메시지가 다시 라우팅하도록 하려면 DNS 레코드가 지점 사이트에 캐시 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ed48-212">To assure prompt rerouting during a WAN outage, DNS records must be cached at the branch site.</span></span> <span data-ttu-id="0ed48-213">지사 라우터가이를 지 원하는 경우 DNS 캐싱 기능을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ed48-213">If the branch router supports it, turn on DNS caching.</span></span> <span data-ttu-id="0ed48-214">또는 지점에 DNS 서버를 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ed48-214">Or, you can deploy a DNS server at the branch.</span></span> <span data-ttu-id="0ed48-215">이는 독립 실행형 서버 이거나 DNS 기능을 지 원하는 Survivable Branch 기기의 버전 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ed48-215">This can be a stand-alone server or a version of the Survivable Branch Appliance that supports DNS capabilities.</span></span> <span data-ttu-id="0ed48-216">자세한 내용은 Survivable Branch 기기 공급자에 게 문의 하세요.</span><span class="sxs-lookup"><span data-stu-id="0ed48-216">For details, contact your Survivable Branch Appliance provider.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0ed48-217">지점 사이트에서 도메인 컨트롤러를 가질 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0ed48-217">It is not necessary to have a domain controller at a branch site.</span></span> <span data-ttu-id="0ed48-218">Survivable Branch 기기는 로그인 할 때 클라이언트의 인증서 요청에 대 한 응답으로 클라이언트를 보내는 특수 인증서를 사용 하 여 클라이언트를 인증 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ed48-218">The Survivable Branch Appliance authenticates clients by using a special certificate that it sends the client in response to the client’s certificate request when it signs in.</span></span>



</div>

<span data-ttu-id="0ed48-219">Lync 클라이언트는 DHCP 옵션 120 (SIP 등록자 옵션)을 사용 하 여 Lync 서버를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ed48-219">Lync clients can discover the Lync Server by using DHCP Option 120 (SIP Registrar Option).</span></span> <span data-ttu-id="0ed48-220">이 작업은 다음 두 가지 방법 중 하나로 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ed48-220">This can be configured in one of two ways:</span></span>

  - <span data-ttu-id="0ed48-221">지점 사이트에서 DHCP 서버를 구성 하 여 Survivable Branch 기기 또는 Survivable Branch 서버에서 등록자의 FQDN을 반환 하는 DHCP 120 쿼리에 회신 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ed48-221">Configure the DHCP server at the branch site to reply to DHCP 120 queries, which return the FQDN of the Registrar on the Survivable Branch Appliance or Survivable Branch Server.</span></span>

  - <span data-ttu-id="0ed48-222">Lync Server DHCP를 켭니다.</span><span class="sxs-lookup"><span data-stu-id="0ed48-222">Turn on Lync Server DHCP.</span></span> <span data-ttu-id="0ed48-223">이 기능이 설정 되어 있는 경우 Lync Server 등록자는 DHCP 옵션 120 쿼리에 응답 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ed48-223">When this is turned on, the Lync Server Registrar responds to DHCP Option 120 queries.</span></span> <span data-ttu-id="0ed48-224">레지스트라는 DHCP 옵션 120이 아닌 모든 DHCP 쿼리에 응답 하지 않는다는 점에 유의 하세요.</span><span class="sxs-lookup"><span data-stu-id="0ed48-224">Note that the Registrar does not respond to any DHCP queries other than DHCP Options 120.</span></span>

<span data-ttu-id="0ed48-225">또한 서브넷이 여러 개인 대규모 분기 사이트의 경우 dhcp 릴레이 에이전트를 dhcp 서버 (구성 1) 또는 레지스트라 (구성 2)로 dhcp 옵션 120 쿼리를 전달 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ed48-225">Additionally, for larger branch sites that have multiple subnets, DHCP relay agents should be enabled to forward DHCP Option 120 queries to the DHCP Server (configuration 1) or to the Registrar (configuration 2).</span></span>

<span data-ttu-id="0ed48-226">마지막으로, 지사 사이트 사용자는 엔터프라이즈 음성에 대해 구성 하 고 적절 한 통합 커뮤니케이션 끝점을 사용 하 여 프로 비전 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ed48-226">Finally, branch site users must be configured for Enterprise Voice and provisioned with an appropriate unified communications endpoint.</span></span>

</div>

<div>

## <a name="requirements-for-survivable-branch-servers"></a><span data-ttu-id="0ed48-227">Survivable 분기 서버 요구 사항</span><span class="sxs-lookup"><span data-stu-id="0ed48-227">Requirements for Survivable Branch Servers</span></span>

<span data-ttu-id="0ed48-228">Survivable 분기 서버에 대 한 요구 사항은 프런트 엔드 서버의 요구 사항과 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ed48-228">The requirements for Survivable Branch Servers are the same as the requirements for a Front End Server.</span></span> <span data-ttu-id="0ed48-229">자세한 내용은 계획 설명서의 [Lync server 2013에 대 한 서버 하드웨어 플랫폼](lync-server-2013-server-hardware-platforms.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0ed48-229">For details, see [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md) in the Planning documentation.</span></span>

</div>

<div>

## <a name="requirements-for-full-scale-lync-server-branch-site-deployments"></a><span data-ttu-id="0ed48-230">전체 규모 Lync Server 지사 사이트 배포에 대 한 요구 사항</span><span class="sxs-lookup"><span data-stu-id="0ed48-230">Requirements for Full-Scale Lync Server Branch-Site Deployments</span></span>

<span data-ttu-id="0ed48-231">자세한 내용은 계획 설명서에서 [Lync Server 2013의 인프라 요구 사항 확인](lync-server-2013-determining-your-infrastructure-requirements.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0ed48-231">For details, see [Determining your infrastructure requirements for Lync Server 2013](lync-server-2013-determining-your-infrastructure-requirements.md) in the Planning documentation.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

