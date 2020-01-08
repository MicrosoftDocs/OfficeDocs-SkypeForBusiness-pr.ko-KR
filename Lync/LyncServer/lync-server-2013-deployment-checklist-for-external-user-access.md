---
title: 'Lync Server 2013: 외부 사용자 액세스를 위한 배포 검사 목록'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deployment checklist for external user access
ms:assetid: 3f55f502-88a0-4315-8783-45a32a0b78ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425910(v=OCS.15)
ms:contentKeyID: 48183947
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0c8831e8bd94040095fabd9fb335113b62b5287b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978091"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-external-user-access-in-lync-server-2013"></a><span data-ttu-id="d7fb0-102">Lync Server 2013의 외부 사용자 액세스를 위한 배포 검사 목록</span><span class="sxs-lookup"><span data-stu-id="d7fb0-102">Deployment checklist for external user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d7fb0-103">_**마지막으로 수정한 주제:** 2014-02-04_</span><span class="sxs-lookup"><span data-stu-id="d7fb0-103">_**Topic Last Modified:** 2014-02-04_</span></span>

<span data-ttu-id="d7fb0-104">경계 네트워크를 배포 하 고 외부 사용자에 대 한 지원을 구현 하기 전에 먼저 프런트 엔드 풀 또는 Standard Edition 서버를 포함 하 여 Microsoft Lync Server 2013 내부 서버를 배포 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7fb0-104">Before you deploy your perimeter network and implement support for external users, you must already have deployed your Microsoft Lync Server 2013 internal servers, including a Front End pool or a Standard Edition server.</span></span> <span data-ttu-id="d7fb0-105">내부 네트워크에 선택 디렉터를 배포 하려는 경우에는 Edge 서버를 배포 하기 전에 해당 감독도 배포 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7fb0-105">If you plan to deploy the optional Directors in your internal network, you should also deploy them prior to deploying Edge Servers.</span></span> <span data-ttu-id="d7fb0-106">디렉터 배포 프로세스에 대 한 자세한 내용은 계획 설명서의 [Lync Server 2013에서 디렉터에 대 한 시나리오](lync-server-2013-scenarios-for-the-director.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d7fb0-106">For details about the Director deployment process, see [Scenarios for the Director in Lync Server 2013](lync-server-2013-scenarios-for-the-director.md) in the Planning documentation.</span></span>

<span data-ttu-id="d7fb0-107">Microsoft Lync Server 2013에는 내부 서버와 Edge 서버를 쉽게 계획 하 고 배포할 수 있는 도구가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7fb0-107">Microsoft Lync Server 2013 includes tools to facilitate planning and deployment of both internal servers and Edge Servers.</span></span> <span data-ttu-id="d7fb0-108">토폴로지가 완료 되 면 결과 토폴로지 정의를 프로덕션 환경에 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7fb0-108">After the topology is completed, publish the resulting topology definition to your production environment.</span></span> <span data-ttu-id="d7fb0-109">이렇게 하려면 **Domain Admins** 그룹 및 **RTCUniversalServerAdmins** 그룹의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7fb0-109">To do this, you must be a member of the **Domain Admins** group and the **RTCUniversalServerAdmins** group.</span></span>

  - <span data-ttu-id="d7fb0-110">**계획 도구**   Office Communications Server 2007 R2에는 토폴로지 디자인을 안내 하는 데 사용할 수 있는 계획 도구와 Edge 계획 도구가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7fb0-110">**Planning Tool**   Office Communications Server 2007 R2 included a Planning Tool and an Edge Planning Tool that you could use to help guide topology design.</span></span> <span data-ttu-id="d7fb0-111">Lync Server 2010에서 이러한 두 가지 도구는 계획 된 사용자 수, 음성 요구 사항, 외부 사용자 액세스 형식, 페더레이션 옵션 수집 등의 추가 기능 및 기능을 제공 하는 단일 계획 도구로 결합 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d7fb0-111">In Lync Server 2010, these two tools were combined into a single Planning Tool that has additional features and functionality, such as collecting planned user count, voice requirements, external user access types, and federation options.</span></span> <span data-ttu-id="d7fb0-112">또한 IP 주소, 부하 분산 장치 유형 및 기타 경계 네트워크 고려 사항 등 인프라의 네트워크 매개 변수를 계획할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7fb0-112">Additionally, you can plan your infrastructure’s network parameters, such as IP addresses, load balancer types and other perimeter network considerations.</span></span>

  - <span data-ttu-id="d7fb0-113">**토폴로지 작성기**   Lync Server 2013 토폴로지 작성기를 사용 하 여 토폴로지와 구성 요소를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7fb0-113">**Topology Builder**   Lync Server 2013 Topology Builder helps you define your topology and components.</span></span> <span data-ttu-id="d7fb0-114">토폴로지 작성기는 Lync Server 2013를 실행 하는 서버를 배포 하는 데 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7fb0-114">Topology Builder is essential to deploying servers running Lync Server 2013.</span></span> <span data-ttu-id="d7fb0-115">토폴로지 작성기는 조직에서 Lync Server 2013을 실행 하는 모든 서버를 구성 하는 데 사용 되는 중앙 관리 저장소에 결과를 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7fb0-115">Topology Builder publishes the results to a Central Management store that is used to configure all of the servers running Lync Server 2013 in your organization.</span></span> <span data-ttu-id="d7fb0-116">토폴로지 작성기를 사용 하지 않고 서버에 Lync Server 2013을 설치할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d7fb0-116">You cannot install Lync Server 2013 on servers without using Topology Builder.</span></span>

<span data-ttu-id="d7fb0-117">Edge 토폴로지를 정의 하기 위한 토폴로지 작성기 실행을 비롯 하 여 계획 프로세스 중에 edge 토폴로지를 디자인 한 경우 해당 결과를 사용 하 여 Edge 서버 배포를 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7fb0-117">If you designed your edge topology during your planning process, including running Topology Builder to define your edge topology, you can use those results to start your Edge Server deployment.</span></span> <span data-ttu-id="d7fb0-118">앞에 edge 토폴로지 빌드가 완료 되지 않았거나 이전에 지정한 정보를 변경 하려는 경우에는 다른 배포 단계를 진행 하기 전에 토폴로지 작성기 실행을 완료 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7fb0-118">If you did not finish building your edge topology earlier or you want to change the information you previously specified, you must finish running Topology Builder before proceeding with other deployment steps.</span></span> <span data-ttu-id="d7fb0-119">토폴로지를 빌드하는 방법에 대 한 자세한 내용은 [Lync Server 2013에서 외부 사용자 액세스에 대 한 시나리오](lync-server-2013-scenarios-for-external-user-access.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d7fb0-119">For details about how to build your topology, see [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).</span></span>

<span data-ttu-id="d7fb0-120">계획 도구 및 토폴로지 작성기에 대 한 자세한 내용은 계획 문서에서 [Lync Server 2013에 대 한 계획 프로세스 시작](lync-server-2013-beginning-the-planning-process.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d7fb0-120">For details about the Planning Tool and Topology Builder, see [Beginning the planning process for Lync Server 2013](lync-server-2013-beginning-the-planning-process.md) in the Planning documentation.</span></span>

<span data-ttu-id="d7fb0-121">다음 표에서는 Edge 서버 배포 프로세스에 대해 간략하게 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7fb0-121">The following table provides an overview of the Edge Server deployment process.</span></span> <span data-ttu-id="d7fb0-122">외부 사용자 액세스를 배포 하기 전에 수행 해야 하는 계획 결정을 검토 하려면 [Lync Server 2013에서 외부 사용자 액세스 시나리오](lync-server-2013-scenarios-for-external-user-access.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d7fb0-122">To review the planning decisions that must be made before deploying external user access, see [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="d7fb0-123">다음 표의 정보는 새 배포에 대해 중점적으로 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7fb0-123">The information in the following table focuses on a new deployment.</span></span> <span data-ttu-id="d7fb0-124">Lync Server 2010, Office Communications Server 2007 R2 또는 Office Communications Server 2007 환경에 Edge 서버를 배포한 경우 Lync Server 2013로 마이그레이션하는 방법에 대 한 자세한 내용은 <A href="migration.md">마이그레이션을</A> 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d7fb0-124">If you have deployed Edge Servers in a Lync Server 2010, Office Communications Server 2007 R2 or Office Communications Server 2007 environment, see the <A href="migration.md">Migration</A> for details about migrating to Lync Server 2013.</span></span> <span data-ttu-id="d7fb0-125">Office communications server 2007, Live Communications Server 2005 및 Live Communications Server 2003을 포함 하 여 Office Communications Server 2007 R2 이전의 모든 버전에서 마이그레이션이 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d7fb0-125">Migration is not supported from any version prior to Office Communications Server 2007 R2, including Office Communications Server 2007, Live Communications Server 2005, and Live Communications Server 2003.</span></span>



</div>

<span data-ttu-id="d7fb0-126">Edge 서버 성능 및 보안을 개선 하 고 배포를 용이 하 게 하려면 경계 네트워크 및 Edge 서버를 배포할 때 다음과 같은 모범 사례를 적용 하세요.</span><span class="sxs-lookup"><span data-stu-id="d7fb0-126">To enhance Edge Server performance and security, and to facilitate deployment, apply the following best practices when you deploy your perimeter network and Edge Servers:</span></span>

  - <span data-ttu-id="d7fb0-127">조직 내에서 Lync Server 2013의 작동을 테스트 하 고 확인 한 후에만 Edge 서버를 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7fb0-127">Deploy Edge Servers only after you have tested and verified operation of Lync Server 2013 inside your organization.</span></span>

  - <span data-ttu-id="d7fb0-128">도메인이 아닌 작업 그룹에 Edge 서버를 배포 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="d7fb0-128">We recommend that you deploy Edge Servers in a workgroup rather than a domain.</span></span> <span data-ttu-id="d7fb0-129">이렇게 하면 설치를 간소화 하 고 주변 네트워크의 AD DS (Active Directory 도메인 서비스)를 유지할 수가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7fb0-129">Doing so simplifies installation and keeps Active Directory Domain Services (AD DS) out of the perimeter network.</span></span> <span data-ttu-id="d7fb0-130">주변 네트워크에서 AD DS를 찾으면 심각한 보안 위험을 일으킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7fb0-130">Locating AD DS in the perimeter network can present a significant security risk.</span></span>

  - <span data-ttu-id="d7fb0-131">경계 네트워크에 있는 도메인에 대 한 Edge 서버 참가는 지원 되지만 권장 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d7fb0-131">Joining an Edge Server to a domain located entirely in the perimeter network is supported but not recommended.</span></span> <span data-ttu-id="d7fb0-132">Edge 서버는 내부 도메인의 일부인 신뢰할 수 있는 네트워크 경계를 위반 하며,이는 인터넷이 가장 신뢰 되 고 주변 네트워크는 인터넷 보다 신뢰 하 고 내부 네트워크는 가장 신뢰 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d7fb0-132">An Edge Server as part of the internal domain violates trusted network boundaries, where the Internet is least trusted, perimeter network is more trusted than the Internet, and the internal network is most trusted.</span></span> <span data-ttu-id="d7fb0-133">Edge 서버는 도메인의 구성원으로 서 가장 신뢰할 수 있는 네트워크의 일부 이며 신뢰할 수 있는 네트워크 (경계)에 위치 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7fb0-133">An Edge server as a member of the domain is automatically a part of the most trusted network, but resides in a less trusted network (the perimeter).</span></span>

<div>

## <a name="deployment-process-for-edge-servers"></a><span data-ttu-id="d7fb0-134">Edge 서버의 배포 프로세스</span><span class="sxs-lookup"><span data-stu-id="d7fb0-134">Deployment Process for Edge Servers</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d7fb0-135">단계의</span><span class="sxs-lookup"><span data-stu-id="d7fb0-135">Phase</span></span></th>
<th><span data-ttu-id="d7fb0-136">방법은</span><span class="sxs-lookup"><span data-stu-id="d7fb0-136">Steps</span></span></th>
<th><span data-ttu-id="d7fb0-137">필요한</span><span class="sxs-lookup"><span data-stu-id="d7fb0-137">Permissions</span></span></th>
<th><span data-ttu-id="d7fb0-138">설명서</span><span class="sxs-lookup"><span data-stu-id="d7fb0-138">Documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d7fb0-139">적절 한 가장자리 토폴로지를 만들고 적절 한 구성 요소를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7fb0-139">Create the appropriate edge topology and determine the appropriate components.</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="d7fb0-140">토폴로지 작성기를 실행 하 여 Edge 서버 설정을 구성 하 고 토폴로지를 만들고 게시 한 다음 Lync Server Management Shell을 사용 하 여 토폴로지 구성 파일을 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="d7fb0-140">Run Topology Builder to configure Edge Server settings and create and publish the topology, and then use Lync Server Management Shell to export the topology configuration file.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="d7fb0-141"><strong>Domain admins</strong> 그룹 및 <strong>RTCUniversalServerAdmins</strong> 또는 <strong>csadmins</strong> 그룹</span><span class="sxs-lookup"><span data-stu-id="d7fb0-141"><strong>Domain Admins</strong> group and <strong>RTCUniversalServerAdmins</strong> or <strong>CsAdmins</strong> group</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="d7fb0-142">로컬 users 그룹의 구성원 인 계정을 사용 하 여 토폴로지를 정의할 수 있지만 토폴로지를 게시 하려면 <STRONG>Domain Admins</STRONG> 그룹 및 <STRONG>RTCUniversalServerAdmins</STRONG> 그룹의 구성원 인 계정이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7fb0-142">You can define a topology using an account that is a member of the local users group, but publishing a topology requires an account that is a member of the <STRONG>Domain Admins</STRONG> group and the <STRONG>RTCUniversalServerAdmins</STRONG> group.</span></span>


</div></td>
<td><p><span data-ttu-id="d7fb0-143">배포 설명서의 <a href="lync-server-2013-building-an-edge-and-director-topology.md">Lync Server 2013에서 edge 및 디렉터 토폴로지 빌드</a></span><span class="sxs-lookup"><span data-stu-id="d7fb0-143"><a href="lync-server-2013-building-an-edge-and-director-topology.md">Building an edge and Director topology in Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7fb0-144">설치 준비.</span><span class="sxs-lookup"><span data-stu-id="d7fb0-144">Prepare for setup.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="d7fb0-145">시스템 필수 조건이 충족 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7fb0-145">Ensure that system prerequisites are met.</span></span></p></li>
<li><p><span data-ttu-id="d7fb0-146">각 Edge 서버의 내부 및 공용 네트워크 인터페이스 모두에 대해 IP 주소 (IPv4 및 IPv6 (사용 되는 경우)를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7fb0-146">Configure IP addresses (IPv4 and IPv6, if used) for both internal and public facing network interfaces on each Edge Server.</span></span></p></li>
<li><p><span data-ttu-id="d7fb0-147">컴퓨터의 DNS 접미사를 Edge 서버로 배포할 수 있도록 구성 하는 것을 포함 하 여 내부 및 외부 DNS 레코드 (IPv4 및 IPv6 용 호스트 A 및 AAAA)를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7fb0-147">Configure internal and external DNS records (host A and AAAA for IPv4 and IPv6), including configuring the DNS suffix on the computer to be deployed as an Edge Server.</span></span></p></li>
<li><p><span data-ttu-id="d7fb0-148">) 공용 인증서를 만들고 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7fb0-148">(Optional) Create and install public certificates.</span></span> <span data-ttu-id="d7fb0-149">인증서를 획득 하는 데 필요한 시간은 인증서를 발급 하는 CA (인증 기관)에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="d7fb0-149">The time required to obtain certificates depends on which certification authority (CA) issues the certificate.</span></span> <span data-ttu-id="d7fb0-150">이 단계를 수행 하지 않는 경우에는 Edge Server 설치 중에 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7fb0-150">If you do not perform this step at this point, you must do it during Edge Server installation.</span></span> <span data-ttu-id="d7fb0-151">Edge 서버 서비스는 인증서를 얻고 설치할 때까지 시작할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d7fb0-151">The Edge Server services cannot be started until certificates are obtained and installed.</span></span></p></li>
<li><p><span data-ttu-id="d7fb0-152">배포에서 Windows Live, AOL 또는 Yahoo!와의 통신을 지 원하는 경우 공용 IM 연결에 대 한 지원을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7fb0-152">Provision support for public IM connectivity, if your deployment is to support communications with Windows Live, AOL, or Yahoo!</span></span> <span data-ttu-id="d7fb0-153">사용자.</span><span class="sxs-lookup"><span data-stu-id="d7fb0-153">users.</span></span></p>
<div>

> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="d7fb0-154">2012 년 9 월 1 일부 터, Microsoft Lync 공용 IM 연결 사용자 구독 라이선스 ("PIC USL")는 신규 또는 갱신 계약에 대해 더 이상 구매할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d7fb0-154">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="d7fb0-155">활성 라이선스가 있는 고객은 계속 Yahoo!에 페더레이션 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7fb0-155">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="d7fb0-156">서비스 종료 날짜가 될 때까지 메신저를 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7fb0-156">Messenger until the service shut down date.</span></span> <span data-ttu-id="d7fb0-157">AOL 및 Yahoo!에 대 한 6 월 2014의 기간 종료 날짜</span><span class="sxs-lookup"><span data-stu-id="d7fb0-157">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="d7fb0-158">님이 발표 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d7fb0-158">has been announced.</span></span> <span data-ttu-id="d7fb0-159">자세한 내용은 <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013에서 공개 인스턴트 메신저 연결 지원을</A>참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d7fb0-159">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="d7fb0-160">PIC USL은 Lync Server 또는 Office Communications Server와 Yahoo!에 페더레이션 하는 데 필요한 사용자별 사용자 단위 구독 라이선스입니다.</span><span class="sxs-lookup"><span data-stu-id="d7fb0-160">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="d7fb0-161">받으려면.</span><span class="sxs-lookup"><span data-stu-id="d7fb0-161">Messenger.</span></span> <span data-ttu-id="d7fb0-162">이 서비스를 제공 하는 Microsoft의 기능은 기본 계약 인 Yahoo!에 대 한 지원을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7fb0-162">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
> <LI>
> <P><span data-ttu-id="d7fb0-163">이전 보다 훨씬 더 많은 수의 Lync는 전세계의 조직과 사용자 간에 연결 하는 강력한 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="d7fb0-163">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="d7fb0-164">Windows Live Messenger를 사용 하는 페더레이션에서는 Lync 표준 CAL 외에 추가 사용자/장치 라이선스가 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d7fb0-164">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="d7fb0-165">Skype 페더레이션이이 목록에 추가 되어 Lync 사용자가 IM 및 음성을 사용 하 여 수백만 명의 사용자에 게 연락할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7fb0-165">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>


</div></li>
<li><p><span data-ttu-id="d7fb0-166">배포에 사용 하는 경우 Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 파트너에 대해 XMPP 및 페더레이션 지원에 대 한 지원을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7fb0-166">Provision support for XMPP and federation support for Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 partners, if your deployment will use these</span></span></p></li>
<li><p><span data-ttu-id="d7fb0-167">방화벽을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7fb0-167">Configure firewalls.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="d7fb0-168">조직에 맞게</span><span class="sxs-lookup"><span data-stu-id="d7fb0-168">As appropriate to your organization</span></span></p></td>
<td><p><span data-ttu-id="d7fb0-169">배포 설명서의 <a href="lync-server-2013-preparing-for-installation-of-servers-in-the-perimeter-network.md">Lync Server 2013 경계 네트워크에서 서버 설치 준비</a></span><span class="sxs-lookup"><span data-stu-id="d7fb0-169"><a href="lync-server-2013-preparing-for-installation-of-servers-in-the-perimeter-network.md">Preparing for installation of servers in the perimeter network for Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7fb0-170">역방향 프록시를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7fb0-170">Set up reverse proxy.</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="d7fb0-171">경계 네트워크에서 역방향 프록시 (예: Microsoft Forefront 위협 관리 게이트웨이 2010 또는 Microsoft 인터넷 보안 및 가속 (ISA) 서버)를 설정 하 고 필요한 공개 인증서를 얻고 다음을 구성 합니다. 리버스 프록시 서버의 웹 게시 규칙</span><span class="sxs-lookup"><span data-stu-id="d7fb0-171">Set up the reverse proxy (for example, for Microsoft Forefront Threat Management Gateway 2010 or Microsoft Internet Security and Acceleration (ISA) Server with Service Pack 1) in the perimeter network, obtain the necessary public certificates, and configure the web publishing rules on the reverse proxy server.</span></span></p>
<p><span data-ttu-id="d7fb0-172">이동성을 계획 하 고 프런트 엔드 풀 또는 Standard Edition 서버에 모바일 서비스를 배포 하는 경우 모바일 서비스에 대 한 리버스 프록시를 준비 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7fb0-172">Prepare the reverse proxy for Mobility services if you have planned for Mobility and are deploying the Mobility services on the Front End pool or Standard Edition server.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="d7fb0-173"><strong>관리자</strong> 그룹 또는 리버스 프록시 관리자</span><span class="sxs-lookup"><span data-stu-id="d7fb0-173"><strong>Administrators</strong> group or Reverse Proxy administrator</span></span></p></td>
<td><p><span data-ttu-id="d7fb0-174">배포 설명서에서 <a href="lync-server-2013-setting-up-reverse-proxy-servers.md">Lync Server 2013에 대 한 역방향 프록시 서버 설정</a></span><span class="sxs-lookup"><span data-stu-id="d7fb0-174"><a href="lync-server-2013-setting-up-reverse-proxy-servers.md">Setting up reverse proxy servers for Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7fb0-175">디렉터를 설정 합니다 (선택 사항).</span><span class="sxs-lookup"><span data-stu-id="d7fb0-175">Setup a Director (optional).</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="d7fb0-176">) 내부 네트워크에 하나 이상의 디렉터를 설치 하 고 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7fb0-176">(Optional) Install and configure one or more Directors in the internal network.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="d7fb0-177"><strong>관리자</strong> 그룹</span><span class="sxs-lookup"><span data-stu-id="d7fb0-177"><strong>Administrators</strong> group</span></span></p></td>
<td><p><span data-ttu-id="d7fb0-178">배포 설명서의 <a href="lync-server-2013-setting-up-the-director.md">Lync Server 2013에서 디렉터 설정</a></span><span class="sxs-lookup"><span data-stu-id="d7fb0-178"><a href="lync-server-2013-setting-up-the-director.md">Setting up the Director in Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7fb0-179">Edge 서버를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7fb0-179">Set up Edge Servers.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="d7fb0-180">필수 구성 요소 소프트웨어를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7fb0-180">Install prerequisite software.</span></span></p></li>
<li><p><span data-ttu-id="d7fb0-181">내보낸 토폴로지 구성 파일을 각 Edge 서버로 전송 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7fb0-181">Transport the exported topology configuration file to each Edge Server.</span></span></p></li>
<li><p><span data-ttu-id="d7fb0-182">각 Edge 서버에 Lync Server 2013 소프트웨어를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7fb0-182">Install the Lync Server 2013 software on each Edge Server.</span></span></p></li>
<li><p><span data-ttu-id="d7fb0-183">Edge 서버를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7fb0-183">Configure the Edge Servers.</span></span></p></li>
<li><p><span data-ttu-id="d7fb0-184">각 Edge 서버에 대 한 인증서를 요청 하 고 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7fb0-184">Request and install certificates for each Edge Server.</span></span></p></li>
<li><p><span data-ttu-id="d7fb0-185">Edge 서버 서비스를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7fb0-185">Start the Edge Server services.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="d7fb0-186"><strong>관리자</strong> 그룹</span><span class="sxs-lookup"><span data-stu-id="d7fb0-186"><strong>Administrators</strong> group</span></span></p></td>
<td><p><span data-ttu-id="d7fb0-187">배포 설명서의 <a href="lync-server-2013-setting-up-edge-servers.md">Lync Server 2013에서 Edge 서버 설정</a></span><span class="sxs-lookup"><span data-stu-id="d7fb0-187"><a href="lync-server-2013-setting-up-edge-servers.md">Setting up Edge Servers in Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7fb0-188">외부 사용자 액세스를 위한 배포를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7fb0-188">Configure deployment for external user access.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="d7fb0-189">Lync Server 제어판을 사용 하 여 다음에 대 한 지원을 구성 합니다 (해당 하는 경우).</span><span class="sxs-lookup"><span data-stu-id="d7fb0-189">Use the Lync Server Control Panel to configure support for each of the following (as applicable):</span></span></p>
<ul>
<li><p><span data-ttu-id="d7fb0-190">미디어 릴레이</span><span class="sxs-lookup"><span data-stu-id="d7fb0-190">Media relay</span></span></p></li>
<li><p><span data-ttu-id="d7fb0-191">페더레이션 경로</span><span class="sxs-lookup"><span data-stu-id="d7fb0-191">Federation route</span></span></p></li>
<li><p><span data-ttu-id="d7fb0-192">원격 사용자 액세스</span><span class="sxs-lookup"><span data-stu-id="d7fb0-192">Remote user access</span></span></p></li>
<li><p><span data-ttu-id="d7fb0-193">Lync Server, Office Communications Server 및 Live Communications Server의 페더레이션</span><span class="sxs-lookup"><span data-stu-id="d7fb0-193">Federation with Lync Server, Office Communications Server and Live Communications Server</span></span></p></li>
<li><p><span data-ttu-id="d7fb0-194">공용 메신저 연결</span><span class="sxs-lookup"><span data-stu-id="d7fb0-194">Public IM connectivity</span></span></p></li>
<li><p><span data-ttu-id="d7fb0-195">XMPP 페더레이션</span><span class="sxs-lookup"><span data-stu-id="d7fb0-195">XMPP federation</span></span></p></li>
<li><p><span data-ttu-id="d7fb0-196">익명 사용자</span><span class="sxs-lookup"><span data-stu-id="d7fb0-196">Anonymous users</span></span></p></li>
</ul></li>
<li><p><span data-ttu-id="d7fb0-197">원격 사용자 액세스, 페더레이션, 공용 IM 연결, XMPP 및 익명 사용자 지원 (해당 되는 경우)에 대 한 사용자 계정 구성</span><span class="sxs-lookup"><span data-stu-id="d7fb0-197">Configure user accounts for remote user access, federation, public IM connectivity, XMPP and anonymous user support (as applicable)</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="d7fb0-198"><strong>Csadministrator</strong> 역할에 할당 된 <strong>RTCUniversalServerAdmins</strong> group 또는 사용자 계정</span><span class="sxs-lookup"><span data-stu-id="d7fb0-198"><strong>RTCUniversalServerAdmins</strong> group or user account that is assigned to the <strong>CSAdministrator</strong> role</span></span></p></td>
<td><p><span data-ttu-id="d7fb0-199">배포 설명서의 <a href="lync-server-2013-configuring-support-for-external-user-access.md">Lync Server 2013에서 외부 사용자 액세스에 대 한 지원 구성</a></span><span class="sxs-lookup"><span data-stu-id="d7fb0-199"><a href="lync-server-2013-configuring-support-for-external-user-access.md">Configuring support for external user access in Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7fb0-200">Edge 서버 구성을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7fb0-200">Verify your Edge Server configuration.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="d7fb0-201">내부 서버에서 구성 데이터의 복제 및 서버 연결을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7fb0-201">Verify server connectivity and replication of configuration data from internal servers.</span></span></p></li>
<li><p><span data-ttu-id="d7fb0-202">원격 사용자, 페더레이션 도메인의 사용자, 공용 IM 사용자, 익명 사용자를 비롯 한 외부 사용자가 배포에 적절 하 게 연결할 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7fb0-202">Verify that external users can connect, including remote users, users in federated domains, public IM users, and anonymous users, as appropriate to your deployment.</span></span></p></li>
<li><p><span data-ttu-id="d7fb0-203">Lync Server 원격 연결 분석기를 사용 하 여 구성 및 통신 확인<a href="https://www.testocsconnectivity.com" class="uri">https://www.testocsconnectivity.com</a></span><span class="sxs-lookup"><span data-stu-id="d7fb0-203">Verify configuration and communication using the Lync Server Remote Connectivity Analyzer <a href="https://www.testocsconnectivity.com" class="uri">https://www.testocsconnectivity.com</a></span></span></p></li>
<li><p><span data-ttu-id="d7fb0-204">구성 및 통신 문제 해결</span><span class="sxs-lookup"><span data-stu-id="d7fb0-204">Troubleshoot configuration and communication difficulties</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="d7fb0-205"><strong>Csadministrator</strong> 역할에 할당 된 복제, <strong>RTCUniversalServerAdmins</strong> group 또는 사용자 계정 확인</span><span class="sxs-lookup"><span data-stu-id="d7fb0-205">For verification of replication, <strong>RTCUniversalServerAdmins</strong> group or user account that is assigned to the <strong>CSAdministrator</strong> role</span></span></p>
<p><span data-ttu-id="d7fb0-206">사용자 연결 확인을 위해 지원 되는 각 외부 사용자 액세스 유형에 대 한 사용자</span><span class="sxs-lookup"><span data-stu-id="d7fb0-206">For verification of user connectivity, a user for each type of external user access that you support</span></span></p>
<p><span data-ttu-id="d7fb0-207">원격 사용자</span><span class="sxs-lookup"><span data-stu-id="d7fb0-207">Remote users</span></span></p></td>
<td><p><span data-ttu-id="d7fb0-208">배포 설명서의 <a href="lync-server-2013-verifying-your-edge-deployment.md">Lync Server 2013에서 edge 배포 확인</a></span><span class="sxs-lookup"><span data-stu-id="d7fb0-208"><a href="lync-server-2013-verifying-your-edge-deployment.md">Verifying your edge deployment in Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

