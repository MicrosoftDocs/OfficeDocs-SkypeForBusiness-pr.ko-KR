---
title: 'Lync Server 2013: 분기 사이트 복구 솔루션'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Branch-site resiliency solutions
ms:assetid: 1700f99b-709c-4e47-88eb-c0a5490e26e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398234(v=OCS.15)
ms:contentKeyID: 48183517
ms.date: 12/11/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a72d07e1ccdae6c433de92057e6e9414fff20153
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42150887"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="branch-site-resiliency-solutions-in-lync-server-2013"></a><span data-ttu-id="0d854-102">Lync Server 2013의 분기 사이트 복구 솔루션</span><span class="sxs-lookup"><span data-stu-id="0d854-102">Branch-site resiliency solutions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0d854-103">_**마지막으로 수정 된 항목:** 2014-12-10_</span><span class="sxs-lookup"><span data-stu-id="0d854-103">_**Topic Last Modified:** 2014-12-10_</span></span>

<span data-ttu-id="0d854-104">조직에 분기 사이트 복구 기능을 제공 하면 분명 한 이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d854-104">There are obvious advantages to providing branch-site resiliency to your organization.</span></span> <span data-ttu-id="0d854-105">특히 중앙 사이트에 대 한 연결이 끊어지면 분기 사이트 사용자에 게 엔터프라이즈 음성 서비스 및 음성 메일이 계속 해 서 표시 됩니다 (음성 메일 다시 라우팅 설정을 구성 하는 경우 자세한 내용은 [Lync Server 2013에 대 한 분기 사이트 복구 요구 사항](lync-server-2013-branch-site-resiliency-requirements.md)참조).</span><span class="sxs-lookup"><span data-stu-id="0d854-105">Specifically, if you lose the connection to the central site, branch site users will continue to have Enterprise Voice service and voice mail (if you configure voice mail rerouting settings; for details, see [Branch-site resiliency requirements for Lync Server 2013](lync-server-2013-branch-site-resiliency-requirements.md)).</span></span> <span data-ttu-id="0d854-106">그러나 사용자가 25 명 미만인 사이트의 경우 복구 솔루션은 투자 수익률을 충분히 제공 하지 못할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d854-106">However, for sites with fewer than 25 users, a resiliency solution may not provide a sufficient return on investment.</span></span>

<span data-ttu-id="0d854-p102">분기 사이트 탄성을 제공하려는 경우 세 가지 방법 중 하나를 사용할 수 있습니다. 다음 표를 사용하면 조직에 가장 적합한 옵션을 선택하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d854-p102">If you decide to provide branch-site resiliency, you have three options. The following table can help you determine the best option for your organization.</span></span>

<div>



<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0d854-109">상황</span><span class="sxs-lookup"><span data-stu-id="0d854-109">If you…</span></span></th>
<th><span data-ttu-id="0d854-110">권장 방법</span><span class="sxs-lookup"><span data-stu-id="0d854-110">We recommend that you use a…</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0d854-111">분기 사이트에서 25~1000명의 사용자를 호스팅하려는 경우(ROI(투자 수익률)가 전체 배포를 지원하지 않거나 로컬 관리 지원을 사용할 수 없음)</span><span class="sxs-lookup"><span data-stu-id="0d854-111">Host between 25 and 1000 users at your branch site, and if the return on investment does not support a full deployment or where local administrative support is unavailable</span></span></p></td>
<td><p><span data-ttu-id="0d854-112">Survivable Branch Appliance</span><span class="sxs-lookup"><span data-stu-id="0d854-112">Survivable Branch Appliance</span></span></p>
<p><span data-ttu-id="0d854-113">Sba (survivable 분기 어플라이언스는 Windows Server 2008 r 2에서 Lync Server 등록자 및 중재 서버가 실행 되는 업계 표준 블레이드 서버입니다.</span><span class="sxs-lookup"><span data-stu-id="0d854-113">The Survivable Branch Appliance is an industry-standard blade server with a Lync Server Registrar and Mediation Server running on Windows Server 2008 R2.</span></span> <span data-ttu-id="0d854-114">Sba (survivable 분기 기기에는 PSTN (공중 전화망) 게이트웨이도 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d854-114">The Survivable Branch Appliance also contains a public switched telephone network (PSTN) gateway.</span></span> <span data-ttu-id="0d854-115">SBA(Survivable Branch Appliance) 자격 검증/인증 프로그램에서 Microsoft 파트너가 개발한 적격 타사 장치는 WAN 오류 시에도 지속적인 PSTN 연결을 제공하지만, 이러한 기능은 중앙 사이트의 프런트 엔드 서버를 기반으로 하기 때문에 이 접근 방식이 탄력적인 현재 상태 및 회의 기능을 제공하지는 못합니다.</span><span class="sxs-lookup"><span data-stu-id="0d854-115">Qualified third-party devices (developed by Microsoft partners in the Survivable Branch Appliance (SBA) qualification/certification program) provide a continuous PSTN connection in the event of WAN failure, but this approach does not provide resilient presence and conferencing because these features depend on Front End Servers at the central site.</span></span></p>
<p><span data-ttu-id="0d854-116">Sba (survivable 분기 기기에 대 한 자세한 내용은 &quot;이 항목의 뒷부분에&quot; 나오는 sba (survivable branch 어플라이언스 details를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="0d854-116">For details about Survivable Branch Appliances, see &quot;Survivable Branch Appliance Details,&quot; later in this topic.</span></span></p>
<p><span data-ttu-id="0d854-117"><strong>참고:</strong> Sba (survivable Branch 기기와 함께 SIP 트렁크를 사용 하기로 결정 한 경우에는 Sba (survivable Branch 어플라이언스 공급 업체에 문의 하 여 조직에 가장 적합 한 서비스 공급자를 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="0d854-117"><strong>Note:</strong> If you decide to also use a SIP trunk with your Survivable Branch Appliance, contact your Survivable Branch Appliance vendor to learn about which service provider is best for your organization.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0d854-118">분기 사이트에서 1000와 2000 사용자 간의 호스트, 복원 가능한 WAN 연결이 부족 한 경우 교육 된 Lync Server 관리자를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d854-118">Host between 1000 and 2000 users at your branch site, lack a resilient WAN connection, and have trained Lync Server administrators available</span></span></p></td>
<td><p><span data-ttu-id="0d854-119">Sba (survivable 분기 서버 또는 두 개의 Sba (survivable Branch 기기</span><span class="sxs-lookup"><span data-stu-id="0d854-119">Survivable Branch Server or two Survivable Branch Appliances.</span></span></p>
<p><span data-ttu-id="0d854-120">Sba (survivable Branch Server는 Lync Server 등록자 및 중재 서버 소프트웨어가 설치 되어 있는 Windows Server 회의 지정 하드웨어 요구 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="0d854-120">The Survivable Branch Server is a Windows Server meeting specified hardware requirements that has Lync Server Registrar and Mediation Server software installed on it.</span></span> <span data-ttu-id="0d854-121">이 서버는 전화 서비스 공급자에 대한 SIP 트렁크 또는 PSTN 게이트웨이에 연결되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d854-121">It must connect to either a PSTN gateway or a SIP trunk to a telephone service provider.</span></span></p>
<p><span data-ttu-id="0d854-122">Sba (survivable 분기 서버에 대 한 자세한 내용은 &quot;이 항목의 뒷부분에&quot; 나오는 sba (survivable branch Server details를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="0d854-122">For details about Survivable Branch Servers, see &quot;Survivable Branch Server Details,&quot; later in this topic.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0d854-123">최대 5000 명의 사용자에 대 한 음성 기능 외에도 현재 상태 및 회의 기능이 필요 하 고 교육 된 Lync Server 관리자를 사용할 수 있는 경우</span><span class="sxs-lookup"><span data-stu-id="0d854-123">If you require presence and conferencing features in addition to voice features for up to 5000 users, and have trained Lync Server administrators available</span></span></p></td>
<td><p><span data-ttu-id="0d854-124">Standard Edition 서버를 분기 사이트가 아니라 중앙 사이트로 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="0d854-124">Deploy as a central site with a Standard Edition server rather than as a branch site.</span></span></p>
<p><span data-ttu-id="0d854-125">전체 수평 Lync Server 배포는 WAN 오류가 발생 하는 경우 지속적인 PSTN 연결 및 탄성 현재 상태 및 회의를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d854-125">A full-scale Lync Server deployment provides a continuous PSTN connection and resilient presence and conferencing in the event of WAN failure.</span></span></p>
<p><span data-ttu-id="0d854-126">이 솔루션을 준비 하는 방법에 대 한 자세한 내용은 <a href="lync-server-2013-planning-for-your-organization.md">Lync server 2013의 조직 계획</a>, lync server 2013에 대 한 <a href="lync-server-2013-determining-your-system-requirements.md">시스템 요구 사항 결정</a>, <a href="lync-server-2013-determining-your-infrastructure-requirements.md">lync server 2013의 인프라 요구 사항 결정</a>, 계획 설명서의 기타 관련 섹션을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="0d854-126">For details about preparing for this solution, see <a href="lync-server-2013-planning-for-your-organization.md">Organization planning for Lync Server 2013</a>, <a href="lync-server-2013-determining-your-system-requirements.md">Determining your system requirements for Lync Server 2013</a>, <a href="lync-server-2013-determining-your-infrastructure-requirements.md">Determining your infrastructure requirements for Lync Server 2013</a>, and other relevant sections of the Planning documentation.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="resiliency-topologies"></a><span data-ttu-id="0d854-127">복구 토폴로지</span><span class="sxs-lookup"><span data-stu-id="0d854-127">Resiliency Topologies</span></span>

<span data-ttu-id="0d854-128">다음 그림에서는 분기 사이트 복구를 지원하는 권장 토폴로지를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0d854-128">The following figure shows the recommended topologies for branch-site resiliency.</span></span>

<span data-ttu-id="0d854-129">**분기 사이트 복구 옵션**</span><span class="sxs-lookup"><span data-stu-id="0d854-129">**Branch site resiliency options**</span></span>

<span data-ttu-id="0d854-130">![음성 분기 복구 옵션](images/Gg398234.47eecd19-08ae-4d82-acbe-61f0de760306(OCS.15).jpg "음성 분기 복구 옵션")</span><span class="sxs-lookup"><span data-stu-id="0d854-130">![Voice Branch Resiliency Options](images/Gg398234.47eecd19-08ae-4d82-acbe-61f0de760306(OCS.15).jpg "Voice Branch Resiliency Options")</span></span>

</div>

<div>

## <a name="survivable-branch-appliance-details"></a><span data-ttu-id="0d854-131">SBA(Survivable Branch Appliance) 세부 정보</span><span class="sxs-lookup"><span data-stu-id="0d854-131">Survivable Branch Appliance Details</span></span>

<span data-ttu-id="0d854-132">Lync Server Sba (survivable Branch 기기에는 다음과 같은 구성 요소가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d854-132">The Lync Server Survivable Branch Appliance includes the following components:</span></span>

  - <span data-ttu-id="0d854-133">사용자 인증, 등록 및 통화 라우팅을 수행하는 등록자</span><span class="sxs-lookup"><span data-stu-id="0d854-133">A Registrar for user authentication, registration and call routing</span></span>

  - <span data-ttu-id="0d854-134">등록자와 PSTN 게이트웨이 간의 신호를 처리하는 중재 서버</span><span class="sxs-lookup"><span data-stu-id="0d854-134">A Mediation Server for handling signaling between the Registrar and a PSTN gateway</span></span>

  - <span data-ttu-id="0d854-135">WAN 중단 시 PSTN 통화를 대체 전송으로 라우팅하는 PSTN 게이트웨이</span><span class="sxs-lookup"><span data-stu-id="0d854-135">A PSTN gateway for routing calls to the PSTN as a fallback transport in the event of a WAN outage</span></span>

  - <span data-ttu-id="0d854-136">로컬 사용자 데이터를 저장하는 SQL Server Express</span><span class="sxs-lookup"><span data-stu-id="0d854-136">SQL Server Express for local user data storage</span></span>

<span data-ttu-id="0d854-137">또한 Sba (survivable Branch 기기에는 PSTN 트렁크, 아날로그 포트 및 이더넷 어댑터만 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0d854-137">The Survivable Branch Appliance also includes PSTN trunks, analog ports, and an Ethernet adapter.</span></span>

<span data-ttu-id="0d854-138">중앙 사이트에 대 한 분기 사이트의 WAN 연결을 사용할 수 없는 경우 내부 분기 사용자는 Sba (survivable Branch 기기 등록자를 사용 하 여 계속 등록 하 고 Sba (survivable Branch 기기 연결을 통해 중단 되지 않은 음성 서비스를 얻습니다. PSTN으로 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d854-138">If the branch site’s WAN connection to a central site becomes unavailable, internal branch users continue to be registered with the Survivable Branch Appliance Registrar and obtain uninterrupted voice service by using the Survivable Branch Appliance connection to the PSTN.</span></span> <span data-ttu-id="0d854-139">홈 또는 다른 원격 위치에서 연결하는 분기 사이트 사용자는 분기 사이트의 WAN 링크를 사용할 수 없어도 중앙 사이트의 등록자 서버에 등록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d854-139">Branch site users who connect from home or other remote locations will be able to register with a Registrar server at a central site if the WAN link to the branch site is unavailable.</span></span> <span data-ttu-id="0d854-140">이러한 사용자는 분기 사이트로의 인바운드 통화가 음성 메일로 이동하는 것을 제외하고는 전체 통합 통신 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d854-140">These users will have full unified communications functionality, with the one exception that inbound calls to the branch site will go to voice mail.</span></span> <span data-ttu-id="0d854-141">WAN 연결이 복구되면 분기 사이트 사용자를 위한 전체 기능이 복원됩니다.</span><span class="sxs-lookup"><span data-stu-id="0d854-141">When the WAN connection becomes available, full functionality should be restored to branch site users.</span></span> <span data-ttu-id="0d854-142">Sba (survivable 분기 어플라이언스 또는 서비스 복원에 대 한 장애 조치 (failover)를 수행 하려면 IT 관리자가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d854-142">Neither the failover to the Survivable Branch Appliance nor the restoration of service requires the presence of an IT administrator.</span></span>

<span data-ttu-id="0d854-143">Lync Server는 분기 사이트에서 최대 2 개의 Sba (survivable 분기 기기를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d854-143">Lync Server supports up to two Survivable Branch Appliance at a branch site.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0d854-144">Lync Server Sba (survivable Branch 기기에 속한 사용자는 새 채팅방을 만들거나 기존 채팅방에 대 한 대화방 카드를 볼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0d854-144">Users who are homed on a Lync Server Survivable Branch Appliance are unable to create new Chat Rooms or view the Room Card for existing rooms.</span></span>



</div>

<div>

## <a name="survivable-branch-appliance-deployment-overview"></a><span data-ttu-id="0d854-145">SBA(Survivable Branch Appliance) 배포 개요</span><span class="sxs-lookup"><span data-stu-id="0d854-145">Survivable Branch Appliance Deployment Overview</span></span>

<span data-ttu-id="0d854-146">Sba (survivable 분기 어플라이언스는 Microsoft와의 파트너 관계를 설정 하는 원래 장비 제조업체에서 제조 되었으며, 부가 가치 소매 업체를 대신 하 여 배포 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0d854-146">The Survivable Branch Appliance is manufactured by original equipment manufacturers in partnership with Microsoft and deployed on their behalf by value-added retailers.</span></span> <span data-ttu-id="0d854-147">이 배포는 Lync Server가 중앙 사이트에 배포 되 고, 분기 사이트에 대 한 WAN 연결이 설정 되 고, 분기 사이트 사용자가 Enterprise Voice를 사용할 수 있는 경우에만 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d854-147">This deployment should occur only after Lync Server has been deployed at the central site, a WAN connection to the branch site is in place, and branch site users are enabled for Enterprise Voice.</span></span>

<span data-ttu-id="0d854-148">이러한 단계에 대 한 자세한 내용은 배포 설명서에서 [a Lync Server 2013을 사용 하 여 a Sba (survivable Branch 어플라이언스 또는 Server 배포](lync-server-2013-deploying-a-survivable-branch-appliance-or-server.md) 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="0d854-148">For details about these phases, see [Deploying a Survivable Branch Appliance or Server with Lync Server 2013](lync-server-2013-deploying-a-survivable-branch-appliance-or-server.md) in the Deployment documentation.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0d854-149">단계</span><span class="sxs-lookup"><span data-stu-id="0d854-149">Phase</span></span></th>
<th><span data-ttu-id="0d854-150">단계</span><span class="sxs-lookup"><span data-stu-id="0d854-150">Steps</span></span></th>
<th><span data-ttu-id="0d854-151">사용자 권한</span><span class="sxs-lookup"><span data-stu-id="0d854-151">User Rights</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0d854-152">Sba (survivable 분기 기기에 대 한 Active Directory 도메인 서비스 설정</span><span class="sxs-lookup"><span data-stu-id="0d854-152">Set up Active Directory Domain Services for the Survivable Branch Appliance</span></span></p></td>
<td><p><span data-ttu-id="0d854-153"><strong>중앙 사이트에서 다음을 수행합니다.</strong></span><span class="sxs-lookup"><span data-stu-id="0d854-153"><strong>At the central site:</strong></span></span></p>
<ol>
<li><p><span data-ttu-id="0d854-154">분기 사이트에서 Sba (survivable Branch 기기를 설치 및 활성화 하는 기술자에 대 한 도메인 사용자 계정 (또는 엔터프라이즈 id)을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0d854-154">Create a domain user account (or enterprise identity) for the technician who will install and activate the Survivable Branch Appliance at the branch site.</span></span></p></li>
<li><p><span data-ttu-id="0d854-155">Active Directory 도메인 서비스에서 Sba (survivable Branch 기기에 대해 해당 FQDN (정규화 된 도메인 이름)을 사용 하 여 컴퓨터 계정을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0d854-155">Create a computer account (with the applicable fully qualified domain name (FQDN)) for Survivable Branch Appliance in Active Directory Domain Services.</span></span></p></li>
<li><p><span data-ttu-id="0d854-156">토폴로지 작성기에서 Sba (survivable 분기 기기를 만들고 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d854-156">In Topology Builder, create and publish the Survivable Branch Appliance.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="0d854-157">기술자 사용자 계정은 RTCUniversalSBATechnicians의 구성원이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d854-157">The technician user account must be a member of RTCUniversalSBATechnicians.</span></span> <span data-ttu-id="0d854-158">Sba (survivable 분기 어플라이언스는 RTCSBAUniversalServices 그룹에 속해야 하며 토폴로지 작성기를 사용할 때 자동으로 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0d854-158">The Survivable Branch Appliance must belong to the RTCSBAUniversalServices group, which happens automatically when you use Topology Builder.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0d854-159">Sba (survivable Branch 기기를 설치 하 고 정품 인증 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d854-159">Install, and activate the Survivable Branch Appliance.</span></span></p></td>
<td><p><span data-ttu-id="0d854-160"><strong>분기 사이트에서 다음을 수행합니다.</strong></span><span class="sxs-lookup"><span data-stu-id="0d854-160"><strong>At the branch site:</strong></span></span></p>
<ol>
<li><p><span data-ttu-id="0d854-161">Sba (survivable Branch 기기를 이더넷 포트 및 PSTN 포트에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d854-161">Connect the Survivable Branch Appliance to an Ethernet port and PSTN port.</span></span></p></li>
<li><p><span data-ttu-id="0d854-162">Sba (survivable Branch 기기를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d854-162">Start the Survivable Branch Appliance.</span></span></p></li>
<li><p><span data-ttu-id="0d854-163">중앙 사이트에서 Sba (survivable Branch 기기에 대해 만든 도메인 사용자 계정을 사용 하 여 Sba (survivable Branch 기기를 도메인에 참가 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="0d854-163">Join the Survivable Branch Appliance to the domain, using the domain user account created for the Survivable Branch Appliance at the central site.</span></span> <span data-ttu-id="0d854-164">FQDN 및 IP 주소를 컴퓨터 계정에 만든 FQDN과 일치하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="0d854-164">Set the FQDN and IP address to match the FQDN created in the computer account.</span></span></p></li>
<li><p><span data-ttu-id="0d854-165">OEM 사용자 인터페이스를 사용 하 여 Sba (survivable Branch 기기를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d854-165">Configure the Survivable Branch Appliance using the OEM user interface.</span></span></p></li>
<li><p><span data-ttu-id="0d854-166">PSTN 연결을 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="0d854-166">Test PSTN connectivity.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="0d854-167">기술자 사용자 계정은 RTCUniversalSBATechnicians의 구성원이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d854-167">The technician user account must be a member of RTCUniversalSBATechnicians.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<div>

## <a name="survivable-branch-server-details"></a><span data-ttu-id="0d854-168">지속 가능 분기 서버 세부 정보</span><span class="sxs-lookup"><span data-stu-id="0d854-168">Survivable Branch Server Details</span></span>

<span data-ttu-id="0d854-169">토폴로지 작성기에서 분기 사이트를 만들고 해당 사이트에 Sba (survivable 분기 서버를 추가한 다음 역할을 설치 하려는 컴퓨터에서 Lync Server 배포 마법사를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d854-169">In Topology Builder create the branch site, add the Survivable Branch Server to that site, and then run the Lync Server Deployment Wizard on the computer where you want to install the role.</span></span>

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="0d854-170">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0d854-170">See Also</span></span>


[<span data-ttu-id="0d854-171">Lync Server 2013 배포</span><span class="sxs-lookup"><span data-stu-id="0d854-171">Deploying Lync Server 2013</span></span>](lync-server-2013-deploying-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

