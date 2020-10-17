---
title: 'Lync Server 2013: 외부 사용자 액세스에 대 한 배포 검사 목록'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment checklist for external user access
ms:assetid: 3f55f502-88a0-4315-8783-45a32a0b78ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425910(v=OCS.15)
ms:contentKeyID: 48183947
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 010d4437f2eb90d596ace15cc392690dba5544d6
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48522775"
---
# <a name="deployment-checklist-for-external-user-access-in-lync-server-2013"></a><span data-ttu-id="ebf23-102">Lync Server 2013의 외부 사용자 액세스에 대 한 배포 검사 목록</span><span class="sxs-lookup"><span data-stu-id="ebf23-102">Deployment checklist for external user access in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ebf23-103">_**마지막으로 수정 된 항목:** 2014-02-04_</span><span class="sxs-lookup"><span data-stu-id="ebf23-103">_**Topic Last Modified:** 2014-02-04_</span></span>

<span data-ttu-id="ebf23-104">경계 네트워크를 배포 하 고 외부 사용자에 대 한 지원을 구현 하기 전에 이미 프런트 엔드 풀 또는 Standard Edition 서버를 비롯 한 Microsoft Lync Server 2013 내부 서버를 배포 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebf23-104">Before you deploy your perimeter network and implement support for external users, you must already have deployed your Microsoft Lync Server 2013 internal servers, including a Front End pool or a Standard Edition server.</span></span> <span data-ttu-id="ebf23-105">내부 네트워크에 선택적 디렉터를 배포 하려는 경우에는에 지 서버를 배포 하기 전에이를 배포 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebf23-105">If you plan to deploy the optional Directors in your internal network, you should also deploy them prior to deploying Edge Servers.</span></span> <span data-ttu-id="ebf23-106">디렉터 배포 프로세스에 대 한 자세한 내용은 계획 설명서의 [Lync Server 2013에서 디렉터에 대 한 시나리오](lync-server-2013-scenarios-for-the-director.md) 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="ebf23-106">For details about the Director deployment process, see [Scenarios for the Director in Lync Server 2013](lync-server-2013-scenarios-for-the-director.md) in the Planning documentation.</span></span>

<span data-ttu-id="ebf23-107">Microsoft Lync Server 2013에는 내부 서버와에 지 서버를 모두 계획 하 고 배포 하는 데 도움이 되는 도구가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ebf23-107">Microsoft Lync Server 2013 includes tools to facilitate planning and deployment of both internal servers and Edge Servers.</span></span> <span data-ttu-id="ebf23-108">토폴로지를 완료한 후 결과 토폴로지 정의를 프로덕션 환경으로 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="ebf23-108">After the topology is completed, publish the resulting topology definition to your production environment.</span></span> <span data-ttu-id="ebf23-109">이렇게 하려면 **Domain Admins** 그룹 및 **RTCUniversalServerAdmins** 그룹의 구성원이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebf23-109">To do this, you must be a member of the **Domain Admins** group and the **RTCUniversalServerAdmins** group.</span></span>

  - <span data-ttu-id="ebf23-110">**계획 도구**     Office Communications Server 2007 R2에는 토폴로지 디자인을 안내 하는 데 사용할 수 있는 계획 도구와 Edge 계획 도구가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ebf23-110">**Planning Tool**   Office Communications Server 2007 R2 included a Planning Tool and an Edge Planning Tool that you could use to help guide topology design.</span></span> <span data-ttu-id="ebf23-111">Lync Server 2010에서는 이러한 두 도구를 계획 된 사용자 수, 음성 요구 사항, 외부 사용자 액세스 유형 및 페더레이션 옵션 수집과 같은 추가 기능을 제공 하는 단일 기획 도구로 결합 했습니다.</span><span class="sxs-lookup"><span data-stu-id="ebf23-111">In Lync Server 2010, these two tools were combined into a single Planning Tool that has additional features and functionality, such as collecting planned user count, voice requirements, external user access types, and federation options.</span></span> <span data-ttu-id="ebf23-112">또한 IP 주소, 부하 분산 장치 유형 및 기타 경계 네트워크 고려 사항과 같은 인프라의 네트워크 매개 변수를 계획할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ebf23-112">Additionally, you can plan your infrastructure’s network parameters, such as IP addresses, load balancer types and other perimeter network considerations.</span></span>

  - <span data-ttu-id="ebf23-113">**토폴로지 작성기**     Lync Server 2013 토폴로지 작성기를 사용 하면 토폴로지 및 구성 요소를 쉽게 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ebf23-113">**Topology Builder**   Lync Server 2013 Topology Builder helps you define your topology and components.</span></span> <span data-ttu-id="ebf23-114">Lync Server 2013를 실행 하는 서버를 배포 하려면 토폴로지 작성기가 필수적입니다.</span><span class="sxs-lookup"><span data-stu-id="ebf23-114">Topology Builder is essential to deploying servers running Lync Server 2013.</span></span> <span data-ttu-id="ebf23-115">토폴로지 작성기는 조직에서 Lync Server 2013을 실행 하는 모든 서버를 구성 하는 데 사용 되는 중앙 관리 저장소에 결과를 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebf23-115">Topology Builder publishes the results to a Central Management store that is used to configure all of the servers running Lync Server 2013 in your organization.</span></span> <span data-ttu-id="ebf23-116">토폴로지 작성기를 사용 하지 않고 서버에 Lync Server 2013을 설치할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ebf23-116">You cannot install Lync Server 2013 on servers without using Topology Builder.</span></span>

<span data-ttu-id="ebf23-117">에 지 토폴로지를 정의 하기 위해 토폴로지 작성기를 실행 하는 것을 포함 하 여 계획 프로세스 중에에 지 토폴로지를 디자인 한 경우 이러한 결과를 사용 하 여에 지 서버 배포를 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ebf23-117">If you designed your edge topology during your planning process, including running Topology Builder to define your edge topology, you can use those results to start your Edge Server deployment.</span></span> <span data-ttu-id="ebf23-118">이전에에 지 토폴로지의 작성을 완료 하지 않았거나 이전에 지정한 정보를 변경 하려는 경우에는 다른 배포 단계를 진행 하기 전에 토폴로지 작성기 실행을 완료 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebf23-118">If you did not finish building your edge topology earlier or you want to change the information you previously specified, you must finish running Topology Builder before proceeding with other deployment steps.</span></span> <span data-ttu-id="ebf23-119">토폴로지를 작성 하는 방법에 대 한 자세한 내용은 [Lync Server 2013의 외부 사용자 액세스 시나리오](lync-server-2013-scenarios-for-external-user-access.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ebf23-119">For details about how to build your topology, see [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).</span></span>

<span data-ttu-id="ebf23-120">계획 도구 및 토폴로지 작성기에 대 한 자세한 내용은 계획 설명서에서 [Lync Server 2013에 대 한 계획 프로세스 시작](lync-server-2013-beginning-the-planning-process.md) 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="ebf23-120">For details about the Planning Tool and Topology Builder, see [Beginning the planning process for Lync Server 2013](lync-server-2013-beginning-the-planning-process.md) in the Planning documentation.</span></span>

<span data-ttu-id="ebf23-121">다음 표에는 에지 서버 배포 프로세스에 대한 개요가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ebf23-121">The following table provides an overview of the Edge Server deployment process.</span></span> <span data-ttu-id="ebf23-122">외부 사용자 액세스를 배포 하기 전에 수행 해야 하는 계획 결정을 검토 하려면 [Lync Server 2013에서 외부 사용자 액세스 시나리오](lync-server-2013-scenarios-for-external-user-access.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ebf23-122">To review the planning decisions that must be made before deploying external user access, see [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="ebf23-123">다음 표에서는 새 배포를 중심으로 관련 정보를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ebf23-123">The information in the following table focuses on a new deployment.</span></span> <span data-ttu-id="ebf23-124">Lync Server 2010, Office Communications Server 2007 R2 또는 Office Communications Server 2007 환경에에 지 서버를 배포한 경우 Lync Server 2013로 마이그레이션하는 방법에 대 한 자세한 내용은 <A href="migration.md">마이그레이션을</A> 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="ebf23-124">If you have deployed Edge Servers in a Lync Server 2010, Office Communications Server 2007 R2 or Office Communications Server 2007 environment, see the <A href="migration.md">Migration</A> for details about migrating to Lync Server 2013.</span></span> <span data-ttu-id="ebf23-125">Office Communications Server 2007, Live Communications Server 2005 및 Live Communications Server 2003를 포함 하 여 Office Communications Server 2007 R2 이전 버전에서는 마이그레이션이 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ebf23-125">Migration is not supported from any version prior to Office Communications Server 2007 R2, including Office Communications Server 2007, Live Communications Server 2005, and Live Communications Server 2003.</span></span>



</div>

<span data-ttu-id="ebf23-126">에지 서버 성능과 보안을 향상시키고 배포를 용이하게 하려면 경계 네트워크 및 에지 서버를 배포할 때 다음의 모범 사례를 적용하십시오.</span><span class="sxs-lookup"><span data-stu-id="ebf23-126">To enhance Edge Server performance and security, and to facilitate deployment, apply the following best practices when you deploy your perimeter network and Edge Servers:</span></span>

  - <span data-ttu-id="ebf23-127">조직 내에서 Lync Server 2013의 작동을 테스트 하 고 확인 한 후에만에 지 서버를 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebf23-127">Deploy Edge Servers only after you have tested and verified operation of Lync Server 2013 inside your organization.</span></span>

  - <span data-ttu-id="ebf23-p108">도메인이 아닌 작업 그룹에서 에지 서버를 배포하는 것이 좋습니다. 이렇게 하면 설치가 간단해지고 AD DS(Active Directory 도메인 서비스)가 경계 네트워크에 포함되지 않습니다. AD DS를 경계 네트워크 내에 배치하면 상당한 보안 위험이 초래될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ebf23-p108">We recommend that you deploy Edge Servers in a workgroup rather than a domain. Doing so simplifies installation and keeps Active Directory Domain Services (AD DS) out of the perimeter network. Locating AD DS in the perimeter network can present a significant security risk.</span></span>

  - <span data-ttu-id="ebf23-p109">완전히 경계 네트워크에 있는 도메인에 에지 서버를 가입시킬 수는 있지만 권장되지 않습니다. 내부 도메인의 일부인 에지 서버가 신뢰할 수 있는 네트워크 경계를 위반하게 됩니다. 인터넷은 신뢰 수준이 가장 낮고, 경계 네트워크는 인터넷보다 신뢰 수준이 높으며, 내부 네트워크는 신뢰 수준이 가장 높습니다. 도메인의 구성원인 에지 서버는 자동적으로 가장 신뢰할 수 있는 네트워크의 일부가 되지만 신뢰 수준이 낮은 네트워크(경계 네트워크)에 존재하기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="ebf23-p109">Joining an Edge Server to a domain located entirely in the perimeter network is supported but not recommended. An Edge Server as part of the internal domain violates trusted network boundaries, where the Internet is least trusted, perimeter network is more trusted than the Internet, and the internal network is most trusted. An Edge server as a member of the domain is automatically a part of the most trusted network, but resides in a less trusted network (the perimeter).</span></span>

<div>

## <a name="deployment-process-for-edge-servers"></a><span data-ttu-id="ebf23-134">에지 서버 배포 프로세스</span><span class="sxs-lookup"><span data-stu-id="ebf23-134">Deployment Process for Edge Servers</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ebf23-135">단계</span><span class="sxs-lookup"><span data-stu-id="ebf23-135">Phase</span></span></th>
<th><span data-ttu-id="ebf23-136">단계</span><span class="sxs-lookup"><span data-stu-id="ebf23-136">Steps</span></span></th>
<th><span data-ttu-id="ebf23-137">권한</span><span class="sxs-lookup"><span data-stu-id="ebf23-137">Permissions</span></span></th>
<th><span data-ttu-id="ebf23-138">설명서</span><span class="sxs-lookup"><span data-stu-id="ebf23-138">Documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ebf23-139">적절한 에지 토폴로지를 만들고 해당 구성 요소 확인</span><span class="sxs-lookup"><span data-stu-id="ebf23-139">Create the appropriate edge topology and determine the appropriate components.</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="ebf23-140">토폴로지 작성기를 실행 하 여 Edge Server 설정을 구성 하 고 토폴로지를 만들고 게시 한 다음 Lync Server 관리 셸을 사용 하 여 토폴로지 구성 파일을 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="ebf23-140">Run Topology Builder to configure Edge Server settings and create and publish the topology, and then use Lync Server Management Shell to export the topology configuration file.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="ebf23-141"><strong>Domain Admins</strong> 그룹 및 <strong>RTCUniversalServerAdmins</strong> 또는 <strong>csadmins</strong> 그룹</span><span class="sxs-lookup"><span data-stu-id="ebf23-141"><strong>Domain Admins</strong> group and <strong>RTCUniversalServerAdmins</strong> or <strong>CsAdmins</strong> group</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="ebf23-142">로컬 사용자 그룹의 구성원인 계정을 사용하여 토폴로지를 정의할 수 있지만 토폴로지를 게시하려면 <STRONG>Domain Admins</STRONG> 그룹 및 <STRONG>RTCUniversalServerAdmins</STRONG> 그룹의 구성원인 계정이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="ebf23-142">You can define a topology using an account that is a member of the local users group, but publishing a topology requires an account that is a member of the <STRONG>Domain Admins</STRONG> group and the <STRONG>RTCUniversalServerAdmins</STRONG> group.</span></span>


</div></td>
<td><p><span data-ttu-id="ebf23-143">배포 설명서의 <a href="lync-server-2013-building-an-edge-and-director-topology.md">Lync Server 2013에서에 지 및 디렉터 토폴로지 구축</a></span><span class="sxs-lookup"><span data-stu-id="ebf23-143"><a href="lync-server-2013-building-an-edge-and-director-topology.md">Building an edge and Director topology in Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ebf23-144">설치 준비</span><span class="sxs-lookup"><span data-stu-id="ebf23-144">Prepare for setup.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="ebf23-145">시스템 필수 구성 요소를 충족하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="ebf23-145">Ensure that system prerequisites are met.</span></span></p></li>
<li><p><span data-ttu-id="ebf23-146">각 에지 서버에서 내부 인터페이스와 공용 네트워크 인터페이스에 대한 IP 주소(IPv4 및 IPv6)를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="ebf23-146">Configure IP addresses (IPv4 and IPv6, if used) for both internal and public facing network interfaces on each Edge Server.</span></span></p></li>
<li><p><span data-ttu-id="ebf23-147">에지 서버로 배포할 컴퓨터에 대한 DNS 접미사 구성을 포함하여 내부 및 외부 DNS 레코드(IPv4 및 IPv6의 경우 호스트 A 및 AAAA)를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="ebf23-147">Configure internal and external DNS records (host A and AAAA for IPv4 and IPv6), including configuring the DNS suffix on the computer to be deployed as an Edge Server.</span></span></p></li>
<li><p><span data-ttu-id="ebf23-p110">(선택 사항) 공용 인증서를 만들고 설치합니다. 인증서를 얻는 데 소용되는 시간은 인증서를 발급하는 CA(인증 기관)에 따라 다릅니다. 지금 이 단계를 수행하지 않은 경우 에지 서버 설치 시 이 단계를 수행해야 합니다. 인증서를 얻고 설치할 때까지 에지 서버 서비스를 시작할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ebf23-p110">(Optional) Create and install public certificates. The time required to obtain certificates depends on which certification authority (CA) issues the certificate. If you do not perform this step at this point, you must do it during Edge Server installation. The Edge Server services cannot be started until certificates are obtained and installed.</span></span></p></li>
<li><p><span data-ttu-id="ebf23-p111">Windows Live, AOL 또는 Yahoo! 사용자와의 통신을 지원하려면 공용 IM 연결에 대한 지원을 프로비전합니다.</span><span class="sxs-lookup"><span data-stu-id="ebf23-p111">Provision support for public IM connectivity, if your deployment is to support communications with Windows Live, AOL, or Yahoo! users.</span></span></p>
<div>

> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="ebf23-154">2012 년 9 월 1 일, Microsoft Lync 공용 IM 연결 사용자 구독 라이선스 ("PIC USL")를 신규 또는 갱신 동의를 위해 더 이상 구매할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ebf23-154">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="ebf23-155">활성 라이선스를 사용 하는 고객은 Yahoo!에 계속 페더레이션 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ebf23-155">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="ebf23-156">서비스 종료 날짜까지 메신저</span><span class="sxs-lookup"><span data-stu-id="ebf23-156">Messenger until the service shut down date.</span></span> <span data-ttu-id="ebf23-157">AOL 및 Yahoo!의 6 월 2014 일 종료 날짜</span><span class="sxs-lookup"><span data-stu-id="ebf23-157">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="ebf23-158">이 발표 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ebf23-158">has been announced.</span></span> <span data-ttu-id="ebf23-159">자세한 내용은 <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013에서 공용 인스턴트 메신저 연결에 대 한 지원을</A>참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ebf23-159">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="ebf23-160">PIC USL은 Lync Server 또는 Office Communications Server와 Yahoo!을 페더레이션 하는 데 필요한 사용자별 구독 라이선스입니다.</span><span class="sxs-lookup"><span data-stu-id="ebf23-160">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="ebf23-161">메신저로.</span><span class="sxs-lookup"><span data-stu-id="ebf23-161">Messenger.</span></span> <span data-ttu-id="ebf23-162">이 서비스를 제공 하는 Microsoft의 기능은 기본 규약에 따라 세로 맞춤에 사용 되는 Yahoo!에 대 한 지원을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ebf23-162">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
> <LI>
> <P><span data-ttu-id="ebf23-163">이전 보다 Lync는 전 세계의 조직과 조직 간에 연결 하는 강력한 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="ebf23-163">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="ebf23-164">Windows Live Messenger와 페더레이션 하려면 Lync Standard CAL 외에 추가 사용자/장치 라이선스가 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ebf23-164">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="ebf23-165">Lync 사용자가 IM 및 음성을 사용 하 여 수백만 명의 사용자에 게 도달할 수 있도록 하는이 목록에 Skype 페더레이션이 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ebf23-165">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>


</div></li>
<li><p><span data-ttu-id="ebf23-166">배포에 사용 되는 경우 Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 파트너에 대 한 XMPP 및 페더레이션 지원을 프로 비전 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebf23-166">Provision support for XMPP and federation support for Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 partners, if your deployment will use these</span></span></p></li>
<li><p><span data-ttu-id="ebf23-167">방화벽을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="ebf23-167">Configure firewalls.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="ebf23-168">조직에 적절한 권한</span><span class="sxs-lookup"><span data-stu-id="ebf23-168">As appropriate to your organization</span></span></p></td>
<td><p><span data-ttu-id="ebf23-169">배포 설명서의 <a href="lync-server-2013-preparing-for-installation-of-servers-in-the-perimeter-network.md">경계 네트워크에서 Lync Server 2013에 대 한 서버 설치 준비</a></span><span class="sxs-lookup"><span data-stu-id="ebf23-169"><a href="lync-server-2013-preparing-for-installation-of-servers-in-the-perimeter-network.md">Preparing for installation of servers in the perimeter network for Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ebf23-170">역방향 프록시 설정</span><span class="sxs-lookup"><span data-stu-id="ebf23-170">Set up reverse proxy.</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="ebf23-171">경계 네트워크에 역방향 프록시 (예: Microsoft Forefront Threat Management Gateway 2010 또는 Microsoft Internet Security and 가속도 (ISA) Server 서비스 팩 1)를 설정 하 고, 필요한 공용 인증서를 획득 하 고, 역방향 프록시 서버에서 웹 게시 규칙을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebf23-171">Set up the reverse proxy (for example, for Microsoft Forefront Threat Management Gateway 2010 or Microsoft Internet Security and Acceleration (ISA) Server with Service Pack 1) in the perimeter network, obtain the necessary public certificates, and configure the web publishing rules on the reverse proxy server.</span></span></p>
<p><span data-ttu-id="ebf23-172">이동성을 계획하고 Mobility Service를 프런트 엔드 풀 또는 Standard Edition 서버에 배포 중인 경우 Mobility Service에 대한 역방향 프록시를 준비합니다.</span><span class="sxs-lookup"><span data-stu-id="ebf23-172">Prepare the reverse proxy for Mobility services if you have planned for Mobility and are deploying the Mobility services on the Front End pool or Standard Edition server.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="ebf23-173"><strong>Administrators</strong> 그룹 또는 역방향 프록시 관리자</span><span class="sxs-lookup"><span data-stu-id="ebf23-173"><strong>Administrators</strong> group or Reverse Proxy administrator</span></span></p></td>
<td><p><span data-ttu-id="ebf23-174">배포 설명서에서 <a href="lync-server-2013-setting-up-reverse-proxy-servers.md">Lync Server 2013에 대 한 역방향 프록시 서버 설정</a></span><span class="sxs-lookup"><span data-stu-id="ebf23-174"><a href="lync-server-2013-setting-up-reverse-proxy-servers.md">Setting up reverse proxy servers for Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ebf23-175">디렉터를 설치합니다(선택 사항).</span><span class="sxs-lookup"><span data-stu-id="ebf23-175">Setup a Director (optional).</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="ebf23-176">(선택 사항) 내부 네트워크에 하나 이상의 디렉터를 설치 및 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="ebf23-176">(Optional) Install and configure one or more Directors in the internal network.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="ebf23-177"><strong>Administrators</strong> 그룹</span><span class="sxs-lookup"><span data-stu-id="ebf23-177"><strong>Administrators</strong> group</span></span></p></td>
<td><p><span data-ttu-id="ebf23-178">배포 설명서의 <a href="lync-server-2013-setting-up-the-director.md">Lync Server 2013에서 디렉터 설정</a></span><span class="sxs-lookup"><span data-stu-id="ebf23-178"><a href="lync-server-2013-setting-up-the-director.md">Setting up the Director in Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ebf23-179">에지 서버 설정</span><span class="sxs-lookup"><span data-stu-id="ebf23-179">Set up Edge Servers.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="ebf23-180">필수 소프트웨어를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="ebf23-180">Install prerequisite software.</span></span></p></li>
<li><p><span data-ttu-id="ebf23-181">내보낸 토폴로지 구성 파일을 각 에지 서버로 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="ebf23-181">Transport the exported topology configuration file to each Edge Server.</span></span></p></li>
<li><p><span data-ttu-id="ebf23-182">각에 지 서버에 Lync Server 2013 소프트웨어를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebf23-182">Install the Lync Server 2013 software on each Edge Server.</span></span></p></li>
<li><p><span data-ttu-id="ebf23-183">에지 서버를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="ebf23-183">Configure the Edge Servers.</span></span></p></li>
<li><p><span data-ttu-id="ebf23-184">각 에지 서버에 대한 인증서를 요청하고 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="ebf23-184">Request and install certificates for each Edge Server.</span></span></p></li>
<li><p><span data-ttu-id="ebf23-185">에지 서버 서비스를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="ebf23-185">Start the Edge Server services.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="ebf23-186"><strong>Administrators</strong> 그룹</span><span class="sxs-lookup"><span data-stu-id="ebf23-186"><strong>Administrators</strong> group</span></span></p></td>
<td><p><span data-ttu-id="ebf23-187">배포 설명서의 <a href="lync-server-2013-setting-up-edge-servers.md">Lync Server 2013에서에 지 서버 설정</a></span><span class="sxs-lookup"><span data-stu-id="ebf23-187"><a href="lync-server-2013-setting-up-edge-servers.md">Setting up Edge Servers in Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ebf23-188">외부 사용자 액세스에 대한 배포를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="ebf23-188">Configure deployment for external user access.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="ebf23-189">Lync Server 제어판을 사용 하 여 다음 각 사항에 대 한 지원을 구성 합니다 (해당 하는 경우).</span><span class="sxs-lookup"><span data-stu-id="ebf23-189">Use the Lync Server Control Panel to configure support for each of the following (as applicable):</span></span></p>
<ul>
<li><p><span data-ttu-id="ebf23-190">미디어 중계</span><span class="sxs-lookup"><span data-stu-id="ebf23-190">Media relay</span></span></p></li>
<li><p><span data-ttu-id="ebf23-191">페더레이션 경로</span><span class="sxs-lookup"><span data-stu-id="ebf23-191">Federation route</span></span></p></li>
<li><p><span data-ttu-id="ebf23-192">원격 사용자 액세스</span><span class="sxs-lookup"><span data-stu-id="ebf23-192">Remote user access</span></span></p></li>
<li><p><span data-ttu-id="ebf23-193">Lync Server, Office Communications Server 및 Live Communications Server와의 페더레이션</span><span class="sxs-lookup"><span data-stu-id="ebf23-193">Federation with Lync Server, Office Communications Server and Live Communications Server</span></span></p></li>
<li><p><span data-ttu-id="ebf23-194">공용 IM 연결</span><span class="sxs-lookup"><span data-stu-id="ebf23-194">Public IM connectivity</span></span></p></li>
<li><p><span data-ttu-id="ebf23-195">XMPP 페더레이션</span><span class="sxs-lookup"><span data-stu-id="ebf23-195">XMPP federation</span></span></p></li>
<li><p><span data-ttu-id="ebf23-196">익명 사용자</span><span class="sxs-lookup"><span data-stu-id="ebf23-196">Anonymous users</span></span></p></li>
</ul></li>
<li><p><span data-ttu-id="ebf23-197">원격 사용자 액세스, 페더레이션, 공용 IM 연결, XMPP 및 익명 사용자 지원을 구성합니다(적용 가능한 경우).</span><span class="sxs-lookup"><span data-stu-id="ebf23-197">Configure user accounts for remote user access, federation, public IM connectivity, XMPP and anonymous user support (as applicable)</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="ebf23-198"><strong>RTCUniversalServerAdmins</strong> 그룹 또는 <strong>CSAdministrator</strong> 역할에 지정된 사용자 계정</span><span class="sxs-lookup"><span data-stu-id="ebf23-198"><strong>RTCUniversalServerAdmins</strong> group or user account that is assigned to the <strong>CSAdministrator</strong> role</span></span></p></td>
<td><p><span data-ttu-id="ebf23-199">배포 설명서의 <a href="lync-server-2013-configuring-support-for-external-user-access.md">Lync Server 2013에서 외부 사용자 액세스에 대 한 지원 구성</a></span><span class="sxs-lookup"><span data-stu-id="ebf23-199"><a href="lync-server-2013-configuring-support-for-external-user-access.md">Configuring support for external user access in Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ebf23-200">에지 서버 구성 확인</span><span class="sxs-lookup"><span data-stu-id="ebf23-200">Verify your Edge Server configuration.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="ebf23-201">서버 연결 및 내부 서버의 구성 데이터 복제를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="ebf23-201">Verify server connectivity and replication of configuration data from internal servers.</span></span></p></li>
<li><p><span data-ttu-id="ebf23-202">원격 사용자, 페더레이션 도메인의 사용자, 공용 IM 사용자 및 익명 사용자를 포함하여 배포에 해당되는 외부 사용자가 연결할 수 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="ebf23-202">Verify that external users can connect, including remote users, users in federated domains, public IM users, and anonymous users, as appropriate to your deployment.</span></span></p></li>
<li><p><span data-ttu-id="ebf23-203">Lync Server 원격 연결 분석기를 사용 하 여 구성 및 통신 확인 <a href="https://www.testocsconnectivity.com" class="uri">https://www.testocsconnectivity.com</a></span><span class="sxs-lookup"><span data-stu-id="ebf23-203">Verify configuration and communication using the Lync Server Remote Connectivity Analyzer <a href="https://www.testocsconnectivity.com" class="uri">https://www.testocsconnectivity.com</a></span></span></p></li>
<li><p><span data-ttu-id="ebf23-204">구성 및 통신 문제를 해결합니다.</span><span class="sxs-lookup"><span data-stu-id="ebf23-204">Troubleshoot configuration and communication difficulties</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="ebf23-205">복제 확인의 경우 <strong>RTCUniversalServerAdmins</strong> 그룹 또는 <strong>CSAdministrator</strong> 역할에 지정된 사용자 계정</span><span class="sxs-lookup"><span data-stu-id="ebf23-205">For verification of replication, <strong>RTCUniversalServerAdmins</strong> group or user account that is assigned to the <strong>CSAdministrator</strong> role</span></span></p>
<p><span data-ttu-id="ebf23-206">사용자 연결 확인의 경우 지원할 각 외부 사용자 액세스 유형의 사용자</span><span class="sxs-lookup"><span data-stu-id="ebf23-206">For verification of user connectivity, a user for each type of external user access that you support</span></span></p>
<p><span data-ttu-id="ebf23-207">원격 사용자</span><span class="sxs-lookup"><span data-stu-id="ebf23-207">Remote users</span></span></p></td>
<td><p><span data-ttu-id="ebf23-208">배포 설명서의 <a href="lync-server-2013-verifying-your-edge-deployment.md">Lync Server 2013에서에 지 배포 확인</a></span><span class="sxs-lookup"><span data-stu-id="ebf23-208"><a href="lync-server-2013-verifying-your-edge-deployment.md">Verifying your edge deployment in Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

