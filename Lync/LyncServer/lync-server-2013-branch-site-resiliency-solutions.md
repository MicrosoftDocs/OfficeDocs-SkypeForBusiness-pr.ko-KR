---
title: 'Lync Server 2013: 분기 사이트 복구 솔루션'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Branch-site resiliency solutions
ms:assetid: 1700f99b-709c-4e47-88eb-c0a5490e26e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398234(v=OCS.15)
ms:contentKeyID: 48183517
ms.date: 12/11/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ce14328aed7ae4769d2f2aff18edb9c6135fe025
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983789"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="branch-site-resiliency-solutions-in-lync-server-2013"></a><span data-ttu-id="af30c-102">Lync Server 2013의 분기 사이트 복구 솔루션</span><span class="sxs-lookup"><span data-stu-id="af30c-102">Branch-site resiliency solutions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="af30c-103">_**마지막으로 수정한 주제:** 2014-12-10_</span><span class="sxs-lookup"><span data-stu-id="af30c-103">_**Topic Last Modified:** 2014-12-10_</span></span>

<span data-ttu-id="af30c-104">조직에 지점 사이트 복원을 제공 하는 것은 명백한 장점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af30c-104">There are obvious advantages to providing branch-site resiliency to your organization.</span></span> <span data-ttu-id="af30c-105">특히 중앙 사이트에 대 한 연결이 끊어지면 지점 사이트 사용자는 계속 해 서 엔터프라이즈 음성 서비스와 음성 메일을 받을 수 있습니다 (음성 메일 다시 라우팅 설정을 구성 하는 경우 자세한 내용은 [Lync Server 2013에 대 한 지점 사이트 복구 요구 사항](lync-server-2013-branch-site-resiliency-requirements.md)참조).</span><span class="sxs-lookup"><span data-stu-id="af30c-105">Specifically, if you lose the connection to the central site, branch site users will continue to have Enterprise Voice service and voice mail (if you configure voice mail rerouting settings; for details, see [Branch-site resiliency requirements for Lync Server 2013](lync-server-2013-branch-site-resiliency-requirements.md)).</span></span> <span data-ttu-id="af30c-106">그러나 사용자가 25 명 미만인 사이트의 경우 복원 솔루션은 투자 수익률을 충분히 제공 하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af30c-106">However, for sites with fewer than 25 users, a resiliency solution may not provide a sufficient return on investment.</span></span>

<span data-ttu-id="af30c-107">지점 사이트 탄력성을 제공 하기로 결정 한 경우 세 가지 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af30c-107">If you decide to provide branch-site resiliency, you have three options.</span></span> <span data-ttu-id="af30c-108">다음 표에서는 조직에 가장 적합 한 옵션을 결정 하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af30c-108">The following table can help you determine the best option for your organization.</span></span>

<div>



<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="af30c-109">...</span><span class="sxs-lookup"><span data-stu-id="af30c-109">If you…</span></span></th>
<th><span data-ttu-id="af30c-110">다음을 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="af30c-110">We recommend that you use a…</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="af30c-111">지사 사이트에서 25 명에서 1000 사용자 간 호스팅, 투자 수익률이 전체 배포를 지원 하지 않거나, 지역 관리 지원을 사용할 수 없는 경우</span><span class="sxs-lookup"><span data-stu-id="af30c-111">Host between 25 and 1000 users at your branch site, and if the return on investment does not support a full deployment or where local administrative support is unavailable</span></span></p></td>
<td><p><span data-ttu-id="af30c-112">Survivable 분기 기기</span><span class="sxs-lookup"><span data-stu-id="af30c-112">Survivable Branch Appliance</span></span></p>
<p><span data-ttu-id="af30c-113">Survivable Branch 기기는 Windows Server 2008 R2에서 실행 되는 Lync Server 등록자와 중재 서버가 있는 업계 표준 블레이드 서버입니다.</span><span class="sxs-lookup"><span data-stu-id="af30c-113">The Survivable Branch Appliance is an industry-standard blade server with a Lync Server Registrar and Mediation Server running on Windows Server 2008 R2.</span></span> <span data-ttu-id="af30c-114">Survivable Branch 기기에는 PSTN (공용 전환 전화 네트워크) 게이트웨이도 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af30c-114">The Survivable Branch Appliance also contains a public switched telephone network (PSTN) gateway.</span></span> <span data-ttu-id="af30c-115">정식 타사 장치 (Survivable Branch 기기 (SBA) 검증/인증 프로그램)는 WAN 장애가 발생 했을 때 지속적인 PSTN 연결을 제공 하지만,이 접근 방법은 중앙 사이트의 프런트 엔드 서버에 종속 되어 있기 때문에 복원 현재 상태와 회의를 제공 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="af30c-115">Qualified third-party devices (developed by Microsoft partners in the Survivable Branch Appliance (SBA) qualification/certification program) provide a continuous PSTN connection in the event of WAN failure, but this approach does not provide resilient presence and conferencing because these features depend on Front End Servers at the central site.</span></span></p>
<p><span data-ttu-id="af30c-116">Survivable Branch 기기에 대 한 자세한 내용은 &quot;이 항목의&quot; 뒷부분에 나오는 Survivable branch 기기 세부 정보를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="af30c-116">For details about Survivable Branch Appliances, see &quot;Survivable Branch Appliance Details,&quot; later in this topic.</span></span></p>
<p><span data-ttu-id="af30c-117"><strong>참고:</strong> Survivable Branch 기기에도 SIP 트렁크를 사용 하기로 결정 한 경우, Survivable Branch 기기 공급 업체에 문의 하 여 조직에 가장 적합 한 서비스 공급자에 대해 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="af30c-117"><strong>Note:</strong> If you decide to also use a SIP trunk with your Survivable Branch Appliance, contact your Survivable Branch Appliance vendor to learn about which service provider is best for your organization.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="af30c-118">지점 사이트의 1000 및 2000 사용자 간 호스팅, 복원성 WAN 연결이 부족 하 고, 교육 된 Lync Server 관리자를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af30c-118">Host between 1000 and 2000 users at your branch site, lack a resilient WAN connection, and have trained Lync Server administrators available</span></span></p></td>
<td><p><span data-ttu-id="af30c-119">Survivable Branch 서버 또는 두 개의 Survivable Branch 기기.</span><span class="sxs-lookup"><span data-stu-id="af30c-119">Survivable Branch Server or two Survivable Branch Appliances.</span></span></p>
<p><span data-ttu-id="af30c-120">Survivable Branch 서버는 Lync Server 등록자와 중재 서버 소프트웨어가 설치 되어 있는 Windows Server 모임에서 지정 된 하드웨어 요구 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="af30c-120">The Survivable Branch Server is a Windows Server meeting specified hardware requirements that has Lync Server Registrar and Mediation Server software installed on it.</span></span> <span data-ttu-id="af30c-121">전화 서비스 공급자에 게 PSTN 게이트웨이나 SIP 트렁크에 연결 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="af30c-121">It must connect to either a PSTN gateway or a SIP trunk to a telephone service provider.</span></span></p>
<p><span data-ttu-id="af30c-122">Survivable Branch 서버에 대 한 자세한 내용은 &quot;이 항목의 뒷부분에&quot; 나오는 Survivable branch 서버 세부 정보를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="af30c-122">For details about Survivable Branch Servers, see &quot;Survivable Branch Server Details,&quot; later in this topic.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="af30c-123">최대 5000 사용자를 위한 음성 기능 외에도 현재 상태 및 회의 기능이 필요 하 고 교육 된 Lync Server 관리자를 사용할 수 있는 경우</span><span class="sxs-lookup"><span data-stu-id="af30c-123">If you require presence and conferencing features in addition to voice features for up to 5000 users, and have trained Lync Server administrators available</span></span></p></td>
<td><p><span data-ttu-id="af30c-124">지점 사이트가 아닌 표준 버전 서버를 사용 하 여 중앙 사이트로 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="af30c-124">Deploy as a central site with a Standard Edition server rather than as a branch site.</span></span></p>
<p><span data-ttu-id="af30c-125">전체 규모 Lync Server 배포는 WAN 장애가 발생 하는 경우 지속적인 PSTN 연결 및 탄성 현재 상태 및 회의를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="af30c-125">A full-scale Lync Server deployment provides a continuous PSTN connection and resilient presence and conferencing in the event of WAN failure.</span></span></p>
<p><span data-ttu-id="af30c-126">이 솔루션을 준비 하는 방법에 대 한 자세한 내용은 <a href="lync-server-2013-planning-for-your-organization.md">Lync server 2013에 대 한 조직 계획</a>, lync server <a href="lync-server-2013-determining-your-system-requirements.md">2013의 시스템 요구 사항 결정</a>, <a href="lync-server-2013-determining-your-infrastructure-requirements.md">lync server 2013의 인프라 요구 사항</a>결정, 기타 관련 섹션을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="af30c-126">For details about preparing for this solution, see <a href="lync-server-2013-planning-for-your-organization.md">Organization planning for Lync Server 2013</a>, <a href="lync-server-2013-determining-your-system-requirements.md">Determining your system requirements for Lync Server 2013</a>, <a href="lync-server-2013-determining-your-infrastructure-requirements.md">Determining your infrastructure requirements for Lync Server 2013</a>, and other relevant sections of the Planning documentation.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="resiliency-topologies"></a><span data-ttu-id="af30c-127">복원 토폴로지</span><span class="sxs-lookup"><span data-stu-id="af30c-127">Resiliency Topologies</span></span>

<span data-ttu-id="af30c-128">다음 그림은 지점 사이트 탄력성에 대해 권장 되는 토폴로지를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="af30c-128">The following figure shows the recommended topologies for branch-site resiliency.</span></span>

<span data-ttu-id="af30c-129">**지점 사이트 복구 옵션**</span><span class="sxs-lookup"><span data-stu-id="af30c-129">**Branch site resiliency options**</span></span>

<span data-ttu-id="af30c-130">![음성 분기 복원 옵션](images/Gg398234.47eecd19-08ae-4d82-acbe-61f0de760306(OCS.15).jpg "음성 분기 복원") 옵션</span><span class="sxs-lookup"><span data-stu-id="af30c-130">![Voice Branch Resiliency Options](images/Gg398234.47eecd19-08ae-4d82-acbe-61f0de760306(OCS.15).jpg "Voice Branch Resiliency Options")</span></span>

</div>

<div>

## <a name="survivable-branch-appliance-details"></a><span data-ttu-id="af30c-131">Survivable Branch 기기 세부 정보</span><span class="sxs-lookup"><span data-stu-id="af30c-131">Survivable Branch Appliance Details</span></span>

<span data-ttu-id="af30c-132">Lync Server Survivable Branch 기기는 다음 구성 요소를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="af30c-132">The Lync Server Survivable Branch Appliance includes the following components:</span></span>

  - <span data-ttu-id="af30c-133">사용자 인증, 등록 및 통화 라우팅과 같은 등록 기관</span><span class="sxs-lookup"><span data-stu-id="af30c-133">A Registrar for user authentication, registration and call routing</span></span>

  - <span data-ttu-id="af30c-134">레지스트라와 PSTN 게이트웨이 간의 신호를 처리 하기 위한 중재 서버</span><span class="sxs-lookup"><span data-stu-id="af30c-134">A Mediation Server for handling signaling between the Registrar and a PSTN gateway</span></span>

  - <span data-ttu-id="af30c-135">WAN이 중단 되는 경우 PSTN에 대 한 대체 전송으로 호출을 라우팅하는 PSTN 게이트웨이</span><span class="sxs-lookup"><span data-stu-id="af30c-135">A PSTN gateway for routing calls to the PSTN as a fallback transport in the event of a WAN outage</span></span>

  - <span data-ttu-id="af30c-136">로컬 사용자 데이터 저장소에 대 한 SQL Server Express</span><span class="sxs-lookup"><span data-stu-id="af30c-136">SQL Server Express for local user data storage</span></span>

<span data-ttu-id="af30c-137">Survivable Branch 기기에는 PSTN trunks, 아날로그 포트, 이더넷 어댑터도 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="af30c-137">The Survivable Branch Appliance also includes PSTN trunks, analog ports, and an Ethernet adapter.</span></span>

<span data-ttu-id="af30c-138">중앙 사이트에 대 한 지점 사이트의 WAN 연결을 사용할 수 없게 되 면 내부 지점 사용자는 계속 해 서 Survivable Branch 기기 등록 기관에 등록 하 고 Survivable Branch 기기 연결을 사용 하 여 중단 없는 음성 서비스를 얻을 수 있습니다. PSTN에 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af30c-138">If the branch site’s WAN connection to a central site becomes unavailable, internal branch users continue to be registered with the Survivable Branch Appliance Registrar and obtain uninterrupted voice service by using the Survivable Branch Appliance connection to the PSTN.</span></span> <span data-ttu-id="af30c-139">지사 사이트에 대 한 WAN 연결을 사용할 수 없는 경우 홈 또는 다른 원격 위치에서 연결 하는 지점 사이트 사용자는 중앙 사이트의 레지스트라 서버에 등록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af30c-139">Branch site users who connect from home or other remote locations will be able to register with a Registrar server at a central site if the WAN link to the branch site is unavailable.</span></span> <span data-ttu-id="af30c-140">이러한 사용자는 전체 통합 커뮤니케이션 기능을 사용할 수 있으며,이는 지점 사이트에 대 한 인바운드 호출이 음성 메일로 이동 한다는 한 가지 예외를 발생 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="af30c-140">These users will have full unified communications functionality, with the one exception that inbound calls to the branch site will go to voice mail.</span></span> <span data-ttu-id="af30c-141">WAN 연결을 사용할 수 있게 되 면 전체 기능을 지사 사이트 사용자에 게 복원 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="af30c-141">When the WAN connection becomes available, full functionality should be restored to branch site users.</span></span> <span data-ttu-id="af30c-142">Survivable Branch 기기 또는 서비스 복원에 대 한 장애 조치는 IT 관리자의 존재를 요구 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="af30c-142">Neither the failover to the Survivable Branch Appliance nor the restoration of service requires the presence of an IT administrator.</span></span>

<span data-ttu-id="af30c-143">Lync Server는 지점 사이트에서 최대 2 개의 Survivable Branch 기기를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="af30c-143">Lync Server supports up to two Survivable Branch Appliance at a branch site.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="af30c-144">Lync Server Survivable Branch 기기에 속한 사용자는 새 채팅방을 만들거나 기존 채팅방에 대 한 채팅방 카드를 볼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="af30c-144">Users who are homed on a Lync Server Survivable Branch Appliance are unable to create new Chat Rooms or view the Room Card for existing rooms.</span></span>



</div>

<div>

## <a name="survivable-branch-appliance-deployment-overview"></a><span data-ttu-id="af30c-145">Survivable Branch 기기 배포 개요</span><span class="sxs-lookup"><span data-stu-id="af30c-145">Survivable Branch Appliance Deployment Overview</span></span>

<span data-ttu-id="af30c-146">Survivable Branch 기기는 Microsoft와 파트너 관계를 사용 하 여 원래 장비 제조업체에서 제조 하 고 부가 가치 소매 업체에 의해 배포 됩니다.</span><span class="sxs-lookup"><span data-stu-id="af30c-146">The Survivable Branch Appliance is manufactured by original equipment manufacturers in partnership with Microsoft and deployed on their behalf by value-added retailers.</span></span> <span data-ttu-id="af30c-147">이 배포는 Lync Server가 중앙 사이트에 배포 되 고, 지점 사이트에 대 한 WAN 연결이 있으며, 지사 사이트 사용자가 엔터프라이즈 음성을 사용할 수 있는 경우에만 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="af30c-147">This deployment should occur only after Lync Server has been deployed at the central site, a WAN connection to the branch site is in place, and branch site users are enabled for Enterprise Voice.</span></span>

<span data-ttu-id="af30c-148">이러한 단계에 대 한 자세한 내용은 배포 설명서에서 [Lync Server 2013를 사용 하 여 Survivable Branch 기기 또는 서버 배포](lync-server-2013-deploying-a-survivable-branch-appliance-or-server.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="af30c-148">For details about these phases, see [Deploying a Survivable Branch Appliance or Server with Lync Server 2013](lync-server-2013-deploying-a-survivable-branch-appliance-or-server.md) in the Deployment documentation.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="af30c-149">단계의</span><span class="sxs-lookup"><span data-stu-id="af30c-149">Phase</span></span></th>
<th><span data-ttu-id="af30c-150">방법은</span><span class="sxs-lookup"><span data-stu-id="af30c-150">Steps</span></span></th>
<th><span data-ttu-id="af30c-151">사용자 권한</span><span class="sxs-lookup"><span data-stu-id="af30c-151">User Rights</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="af30c-152">Survivable Branch 기기에 대 한 Active Directory 도메인 서비스 설정</span><span class="sxs-lookup"><span data-stu-id="af30c-152">Set up Active Directory Domain Services for the Survivable Branch Appliance</span></span></p></td>
<td><p><span data-ttu-id="af30c-153"><strong>중앙 사이트:</strong></span><span class="sxs-lookup"><span data-stu-id="af30c-153"><strong>At the central site:</strong></span></span></p>
<ol>
<li><p><span data-ttu-id="af30c-154">지점 사이트에서 Survivable Branch 기기를 설치 하 고 활성화 하는 기술자에 대 한 도메인 사용자 계정 (또는 엔터프라이즈 id)을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="af30c-154">Create a domain user account (or enterprise identity) for the technician who will install and activate the Survivable Branch Appliance at the branch site.</span></span></p></li>
<li><p><span data-ttu-id="af30c-155">Active Directory 도메인 서비스의 Survivable Branch 기기에 대해 해당 FQDN (정규화 된 도메인 이름)을 사용 하 여 컴퓨터 계정을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="af30c-155">Create a computer account (with the applicable fully qualified domain name (FQDN)) for Survivable Branch Appliance in Active Directory Domain Services.</span></span></p></li>
<li><p><span data-ttu-id="af30c-156">토폴로지 작성기에서 Survivable Branch 기기를 만들고 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="af30c-156">In Topology Builder, create and publish the Survivable Branch Appliance.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="af30c-157">기술자 사용자 계정은 RTCUniversalSBATechnicians의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="af30c-157">The technician user account must be a member of RTCUniversalSBATechnicians.</span></span> <span data-ttu-id="af30c-158">Survivable Branch 기기는 토폴로지 작성기를 사용할 때 자동으로 일어나는 RTCSBAUniversalServices 그룹에 속해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="af30c-158">The Survivable Branch Appliance must belong to the RTCSBAUniversalServices group, which happens automatically when you use Topology Builder.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="af30c-159">Survivable Branch 기기를 설치 하 고 정품 인증 합니다.</span><span class="sxs-lookup"><span data-stu-id="af30c-159">Install, and activate the Survivable Branch Appliance.</span></span></p></td>
<td><p><span data-ttu-id="af30c-160"><strong>지점 사이트에서 다음을 수행 합니다.</strong></span><span class="sxs-lookup"><span data-stu-id="af30c-160"><strong>At the branch site:</strong></span></span></p>
<ol>
<li><p><span data-ttu-id="af30c-161">Survivable Branch 기기를 이더넷 포트 및 PSTN 포트에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="af30c-161">Connect the Survivable Branch Appliance to an Ethernet port and PSTN port.</span></span></p></li>
<li><p><span data-ttu-id="af30c-162">Survivable Branch 기기를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="af30c-162">Start the Survivable Branch Appliance.</span></span></p></li>
<li><p><span data-ttu-id="af30c-163">중앙 사이트에서 Survivable Branch 기기에 대해 만든 도메인 사용자 계정을 사용 하 여 Survivable Branch 기기를 도메인에 참가 합니다.</span><span class="sxs-lookup"><span data-stu-id="af30c-163">Join the Survivable Branch Appliance to the domain, using the domain user account created for the Survivable Branch Appliance at the central site.</span></span> <span data-ttu-id="af30c-164">FQDN과 IP 주소를 컴퓨터 계정에서 만든 FQDN과 일치 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="af30c-164">Set the FQDN and IP address to match the FQDN created in the computer account.</span></span></p></li>
<li><p><span data-ttu-id="af30c-165">OEM 사용자 인터페이스를 사용 하 여 Survivable Branch 기기를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="af30c-165">Configure the Survivable Branch Appliance using the OEM user interface.</span></span></p></li>
<li><p><span data-ttu-id="af30c-166">PSTN 연결을 테스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="af30c-166">Test PSTN connectivity.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="af30c-167">기술자 사용자 계정은 RTCUniversalSBATechnicians의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="af30c-167">The technician user account must be a member of RTCUniversalSBATechnicians.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<div>

## <a name="survivable-branch-server-details"></a><span data-ttu-id="af30c-168">Survivable Branch 서버 세부 정보</span><span class="sxs-lookup"><span data-stu-id="af30c-168">Survivable Branch Server Details</span></span>

<span data-ttu-id="af30c-169">토폴로지 작성기에서 지점 사이트를 만들고 해당 사이트에 Survivable Branch 서버를 추가한 다음 역할을 설치 하려는 컴퓨터에서 Lync Server 배포 마법사를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="af30c-169">In Topology Builder create the branch site, add the Survivable Branch Server to that site, and then run the Lync Server Deployment Wizard on the computer where you want to install the role.</span></span>

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="af30c-170">참고 항목</span><span class="sxs-lookup"><span data-stu-id="af30c-170">See Also</span></span>


[<span data-ttu-id="af30c-171">Lync Server 2013 배포</span><span class="sxs-lookup"><span data-stu-id="af30c-171">Deploying Lync Server 2013</span></span>](lync-server-2013-deploying-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

