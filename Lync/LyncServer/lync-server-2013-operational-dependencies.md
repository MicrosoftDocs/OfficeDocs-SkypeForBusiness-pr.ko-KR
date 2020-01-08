---
title: 'Lync Server 2013: 작업 종속성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Operational dependencies
ms:assetid: 450b6be2-7fb3-47d7-8b0b-c05faa331e14
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720559(v=OCS.15)
ms:contentKeyID: 63969597
ms.date: 05/16/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d54ef9959f48c085ad4f5f28f182b86442ebec8c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984097"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="operational-dependencies-in-lync-server-2013"></a><span data-ttu-id="c4899-102">Lync Server 2013의 운영 의존 관계</span><span class="sxs-lookup"><span data-stu-id="c4899-102">Operational dependencies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c4899-103">_**마지막으로 수정한 주제:** 2015-05-15_</span><span class="sxs-lookup"><span data-stu-id="c4899-103">_**Topic Last Modified:** 2015-05-15_</span></span>

<span data-ttu-id="c4899-104">이 문서에서 설명 하는 참조 아키텍처는 조직의 요구 사항에 맞게 크기를 조정 하는 것이 아니라 Microsoft의 모범 사례에 따라 설계 되는 Lync Server 2013 배포를 유지 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c4899-104">The Reference Architecture discussed in this document will help ensure that you have a Lync Server 2013 deployment that not only scales to the organization’s requirements but is architected as per Microsoft best practices.</span></span> <span data-ttu-id="c4899-105">Lync Server 2013 구현이 동적인 서비스 이며 엔터프라이즈의 다른 서비스와 마찬가지로 비즈니스에 높은 수준의 서비스 사용 및 서비스 품질을 유지 하기 위해서는 계속 모니터링 및 사전 관리가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4899-105">Be that as it may the Lync Server 2013 implementation is a dynamic service and like any other service in the enterprise still requires monitoring and proactive management to maintain high level of service availability and service quality to the business.</span></span>

<span data-ttu-id="c4899-106">조직의 일상 비즈니스에서 Lync Server 2013을 깊이 있게 사용할 수 있으므로 정확한 서비스 수준 관리를 통해 서비스를 관리 하는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4899-106">As Lync Server 2013 becomes deeply ingrained in the organization’s everyday business it is important that the service be managed by accurate and tangible service level management.</span></span> <span data-ttu-id="c4899-107">Lync 시스템 아키텍처는 복잡 하 고 매우 통합 될 수 있으며, 효과적인 서비스 수준 관리를 유지 관리 하 고 Lync Server 2013에 대 한 Sla를 설정 하려면 다른 플랫폼 및 서버에 대 한 시스템 종속성을 이해 하는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4899-107">The Lync system architecture can become complex and very integrated and in order to maintain effective service level management and establish SLAs for Lync Server 2013 it becomes critical to understand the system’s dependencies on other platforms and servers.</span></span> <span data-ttu-id="c4899-108">중요 한 것은 음성 및 UC 통합 응용 프로그램과 같은 비즈니스 서비스가 Lync에 의존 하는 것을 확인 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c4899-108">Equally important is to note which business services, such as voice and UC integrated applications, become dependent on Lync.</span></span>

<span data-ttu-id="c4899-109">모든 해당 종속성에 대해 설명 하는 Lync Server 2013을 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4899-109">Lync Server 2013 must be established noting all the said dependencies.</span></span> <span data-ttu-id="c4899-110">서비스 맵을 사용 하 여 Lync와 해당 종속 서비스 간의 SLA를 공식화 하 고 SLA 협상이 시작 되는 위치를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4899-110">The service map will allow you to formulate a SLA between Lync and its dependent service and provide a starting place for SLA negotiation.</span></span>

<span data-ttu-id="c4899-111">다음 표에서는 Lync 인프라에 대 한 일반적인 종속성 서비스를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c4899-111">The following table lists the typical dependency services for a Lync infrastructure.</span></span> <span data-ttu-id="c4899-112">이러한 각 기술에는 자체적인 사전 모니터링이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4899-112">Each of these technologies should have its own proactive monitoring.</span></span>

### <a name="typical-dependency-services"></a><span data-ttu-id="c4899-113">일반적인 종속성 서비스</span><span class="sxs-lookup"><span data-stu-id="c4899-113">Typical dependency services</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c4899-114">종속성 서비스</span><span class="sxs-lookup"><span data-stu-id="c4899-114">Dependency Service</span></span></th>
<th></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c4899-115">운영 체제</span><span class="sxs-lookup"><span data-stu-id="c4899-115">Operating systems</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4899-116">서버 하드웨어</span><span class="sxs-lookup"><span data-stu-id="c4899-116">Server Hardware</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4899-117">Active Directory</span><span class="sxs-lookup"><span data-stu-id="c4899-117">Active Directory</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4899-118">공개 키 인프라</span><span class="sxs-lookup"><span data-stu-id="c4899-118">Public Key Infrastructure</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4899-119">도메인 이름 지정 서비스</span><span class="sxs-lookup"><span data-stu-id="c4899-119">Domain Naming Service</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4899-120">데이터베이스 서비스</span><span class="sxs-lookup"><span data-stu-id="c4899-120">Database Services</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4899-121">저장소 서비스</span><span class="sxs-lookup"><span data-stu-id="c4899-121">Storage Services</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4899-122">시스템 관리 – 모니터링 및 배포</span><span class="sxs-lookup"><span data-stu-id="c4899-122">System Management – Monitoring and distribution</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4899-123">보안 서비스-바이러스 백신</span><span class="sxs-lookup"><span data-stu-id="c4899-123">Security Services - Antivirus</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4899-124">네트워크 인프라-인터넷</span><span class="sxs-lookup"><span data-stu-id="c4899-124">Network Infrastructure - Internet</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4899-125">네트워크 인프라 – 내부용 (LAN/WAN)</span><span class="sxs-lookup"><span data-stu-id="c4899-125">Network Infrastructure – Internal (LAN/WAN)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4899-126">전화 통신 인프라 – IP PBX 및 게이트웨이</span><span class="sxs-lookup"><span data-stu-id="c4899-126">Telephony Infrastructure – IP-PBX and Gateways</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4899-127">클라우드 서비스</span><span class="sxs-lookup"><span data-stu-id="c4899-127">Cloud Services</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


<span data-ttu-id="c4899-128">이는 MOF에 규정 된 변경, 사고, 릴리스 관리 등의 기본 서비스 수준 관리 기능을 operationally 하는 것으로 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4899-128">It is assumed that the organization is operationally mature in exercising basic service level management functions such as change, incident and release management as prescribed by the MOF.</span></span> <span data-ttu-id="c4899-129">Lync 솔루션은 이러한 기능을 통해 채택 하 고 동일한 운영 관리 프로세스를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="c4899-129">The Lync solution should be adopted by these functions and become subject to the same operational management processes.</span></span>

<span data-ttu-id="c4899-130">위의 정보를 작성 하면 이제 기업에서 Lync 서비스에 영향을 미칠 수 있는 사항에 대 한 이해가 더욱 향상 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c4899-130">Building on the information obtained above we now have a greater understanding of what can impact the Lync service in the enterprise.</span></span> <span data-ttu-id="c4899-131">Lync Server 2013 서비스 가용성 및 품질을 보장 하기 위해 다음 모니터링 도구는 참조 아키텍처 배포와 함께 제공 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4899-131">To help ensure Lync Server 2013 service availability and quality, the following monitoring tools must accompany the reference architecture deployment:</span></span>

### <a name="monitoring-tools"></a><span data-ttu-id="c4899-132">모니터링 도구</span><span class="sxs-lookup"><span data-stu-id="c4899-132">Monitoring tools</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c4899-133">요소가</span><span class="sxs-lookup"><span data-stu-id="c4899-133">Component</span></span></th>
<th><span data-ttu-id="c4899-134">설명</span><span class="sxs-lookup"><span data-stu-id="c4899-134">Description</span></span></th>
<th><span data-ttu-id="c4899-135">해당 사이트</span><span class="sxs-lookup"><span data-stu-id="c4899-135">Applicable Site</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c4899-136">Lync Server 2013 모니터링 서버</span><span class="sxs-lookup"><span data-stu-id="c4899-136">Lync Server 2013 Monitoring Server</span></span></p></td>
<td><p><span data-ttu-id="c4899-137">중앙 사이트별로 하나 이상의 Lync Server 2013 모니터링 서버 역할을 배포 하 고 환경 품질 (체감 품질) 보고 팩을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4899-137">Deploy at least one Lync Server 2013 Monitoring Server role per Central site and configure Quality of Experience (QoE) Reporting Pack.</span></span></p>
<p><span data-ttu-id="c4899-138">자세한 내용은 Lync Server 2013 배포 설명서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c4899-138">Refer to the Lync Server 2013 Deployment documentation for further details:</span></span></p>
<p><span data-ttu-id="c4899-139"><a href="lync-server-2013-deploying-monitoring.md">Lync Server 2013에서 모니터링 배포</a></span><span class="sxs-lookup"><span data-stu-id="c4899-139"><a href="lync-server-2013-deploying-monitoring.md">Deploying monitoring in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="c4899-140">중앙 사이트</span><span class="sxs-lookup"><span data-stu-id="c4899-140">Central sites</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="c4899-141">각 풀을 모니터링 서버 역할의 가장 가까운 인스턴스로 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4899-141">Tether each pool to its nearest instance of the Monitoring Server role.</span></span></p></td>
<td><p><span data-ttu-id="c4899-142">중앙 사이트</span><span class="sxs-lookup"><span data-stu-id="c4899-142">Central sites</span></span></p>
<p><span data-ttu-id="c4899-143">지점 사이트</span><span class="sxs-lookup"><span data-stu-id="c4899-143">Branch sites</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4899-144">System Center Operations Manager 2012</span><span class="sxs-lookup"><span data-stu-id="c4899-144">System Center Operations Manager 2012</span></span></p></td>
<td><p><span data-ttu-id="c4899-145">Microsoft Lync Server 2013 관리 팩 (MP)이 있는 System Center Operations Manager 2012.</span><span class="sxs-lookup"><span data-stu-id="c4899-145">System Center Operations Manager 2012 with the Microsoft Lync Server 2013 Management Pack (MP) imported.</span></span></p>
<p><span data-ttu-id="c4899-146">관리 팩은 기존 이벤트 로그 및 성능 카운터 기반 계측을 구현 하는 것은 물론 Lync Server 2013에서 새로 사용할 수 있는 계측 기능을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4899-146">The Management Pack implements traditional Event Log and Performance counter based instrumentation is utilized as well as enabling newly available instrumentation in Lync Server 2013.</span></span></p></td>
<td><p><span data-ttu-id="c4899-147">중앙 사이트</span><span class="sxs-lookup"><span data-stu-id="c4899-147">Central sites</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="c4899-148">모니터링 해야 하는 역할 및 구성 요소 검색에 대 한 중앙 검색이 중앙 관리 데이터베이스에 게시 된 토폴로지 문서를 읽는 중앙 검색 스크립트를 기반으로 자동으로 완료 되는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4899-148">Make sure that Central Discovery to discovery of roles and components that need to be monitored are automatically completed based on a central discovery script that reads the topology document published in Central Management Database.</span></span></p></td>
<td><p><span data-ttu-id="c4899-149">중앙 사이트</span><span class="sxs-lookup"><span data-stu-id="c4899-149">Central Site</span></span></p>
<p><span data-ttu-id="c4899-150">지점 사이트</span><span class="sxs-lookup"><span data-stu-id="c4899-150">Branch Site</span></span></p>
<p><span data-ttu-id="c4899-151">Edge 사이트</span><span class="sxs-lookup"><span data-stu-id="c4899-151">Edge Site</span></span></p></td>
</tr>
<tr class="odd">
<td></td>
<td><p><span data-ttu-id="c4899-152">Lync Server를 실행 하는 모든 배포 서버에 시스템 센터 Operations Manager 2007 에이전트를 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4899-152">Deploy System Centre Operations Manager 2007 agents to all deployed servers running Lync Server.</span></span></p></td>
<td><p><span data-ttu-id="c4899-153">중앙 사이트</span><span class="sxs-lookup"><span data-stu-id="c4899-153">Central Site</span></span></p>
<p><span data-ttu-id="c4899-154">지점 사이트</span><span class="sxs-lookup"><span data-stu-id="c4899-154">Branch Site</span></span></p>
<p><span data-ttu-id="c4899-155">Edge 사이트</span><span class="sxs-lookup"><span data-stu-id="c4899-155">Edge Site</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="c4899-156">알림을 위해 우선 순위가 지정 된 경고가 구성 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4899-156">Make sure Prioritized Alerts are configured for notification:</span></span></p>
<p><span data-ttu-id="c4899-157">우선 순위가 높은 알림</span><span class="sxs-lookup"><span data-stu-id="c4899-157">High Priority Alerts</span></span></p>
<p><span data-ttu-id="c4899-158">보통 우선 순위 알림</span><span class="sxs-lookup"><span data-stu-id="c4899-158">Medium Priority Alerts</span></span></p>
<p><span data-ttu-id="c4899-159">다른 알림.</span><span class="sxs-lookup"><span data-stu-id="c4899-159">Other Alerts.</span></span></p></td>
<td><p><span data-ttu-id="c4899-160">중앙 사이트</span><span class="sxs-lookup"><span data-stu-id="c4899-160">Central Site</span></span></p>
<p><span data-ttu-id="c4899-161">지점 사이트</span><span class="sxs-lookup"><span data-stu-id="c4899-161">Branch Site</span></span></p>
<p><span data-ttu-id="c4899-162">Edge 사이트</span><span class="sxs-lookup"><span data-stu-id="c4899-162">Edge Site</span></span></p></td>
</tr>
<tr class="odd">
<td></td>
<td><p><span data-ttu-id="c4899-163">배포에 대 한 포트 모니터링을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4899-163">Configure Port monitoring for your deployment.</span></span></p></td>
<td><p><span data-ttu-id="c4899-164">중앙 사이트</span><span class="sxs-lookup"><span data-stu-id="c4899-164">Central Site</span></span></p>
<p><span data-ttu-id="c4899-165">지점 사이트</span><span class="sxs-lookup"><span data-stu-id="c4899-165">Branch Site</span></span></p>
<p><span data-ttu-id="c4899-166">Edge 사이트</span><span class="sxs-lookup"><span data-stu-id="c4899-166">Edge Site</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="c4899-167">배포에 대 한 URL 모니터링 구성</span><span class="sxs-lookup"><span data-stu-id="c4899-167">Configure URL monitoring for your deployment</span></span></p></td>
<td><p><span data-ttu-id="c4899-168">중앙 사이트</span><span class="sxs-lookup"><span data-stu-id="c4899-168">Central Site</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4899-169">Lync 및 System Center Operations Manager 통합</span><span class="sxs-lookup"><span data-stu-id="c4899-169">Lync and System Center Operations Manager integration</span></span></p></td>
<td><p><span data-ttu-id="c4899-170">통화 안정성 및 미디어 품질 MonitoringCall 안정성 및 미디어 품질 모니터링 모니터링 서버 컴퓨터를 감시자 노드로 사용 하 여 Lync Server의 통화 안정성 및 미디어 품질을 모니터링 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4899-170">Deploy Call Reliability and Media Quality MonitoringCall reliability and media quality monitoring use the Monitoring Server computer as their watcher node to monitor call reliability and media quality of Lync Server.</span></span> <span data-ttu-id="c4899-171">이러한 두 가지 기능은 모두 모니터링 서버 데이터베이스를 쿼리하여 분석을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4899-171">Both of these features query the Monitoring Server databases to do analysis.</span></span></p></td>
<td><p><span data-ttu-id="c4899-172">중앙 사이트</span><span class="sxs-lookup"><span data-stu-id="c4899-172">Central Site</span></span></p>
<p><span data-ttu-id="c4899-173">지점 사이트</span><span class="sxs-lookup"><span data-stu-id="c4899-173">Branch Site</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="c4899-174">미디어 품질 경고 임계값이 정확 하 게 구성 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4899-174">Ensure Media Quality warning thresholds are accurately configured.</span></span> <span data-ttu-id="c4899-175">다음 표에는 코덱의 최대 네트워크 의미 성적 점수가 표시 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4899-175">The following table indicates the maximum Network Mean Opinion Scores by Codec.</span></span> <span data-ttu-id="c4899-176">프로덕션에서 이러한 점수는 설정 된 기간 동안 모니터링 되어야 하며, 허용 되는 임계값은 조직별 NMOS 성적을 기준으로 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4899-176">In production these scores should be monitored for a set period and acceptable thresholds must be established based on the organization specific NMOS scores.</span></span></p></td>
<td><p><span data-ttu-id="c4899-177">중앙 사이트</span><span class="sxs-lookup"><span data-stu-id="c4899-177">Central Site</span></span></p>
<p><span data-ttu-id="c4899-178">지점 사이트</span><span class="sxs-lookup"><span data-stu-id="c4899-178">Branch Site</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4899-179">Lync Server 2013 가상 트랜잭션 감시자</span><span class="sxs-lookup"><span data-stu-id="c4899-179">Lync Server 2013 Synthetic Transaction Watcher</span></span></p></td>
<td><p><span data-ttu-id="c4899-180">가상 트랜잭션 감시자가 되도록 전용 Lync 서버를 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4899-180">Deploy a dedicated Lync Server to be a synthetic transaction watcher.</span></span></p>
<p><span data-ttu-id="c4899-181">종합 트랜잭션은 미리 정의 된 간격으로 관리 팩에 의해 자동으로 트리거되는 Lync Server 2013 Windows PowerShell cmdlet입니다.</span><span class="sxs-lookup"><span data-stu-id="c4899-181">Synthetic transactions are Lync Server 2013 Windows PowerShell cmdlets that are automatically triggered by the management pack on a predefined interval.</span></span> <span data-ttu-id="c4899-182">이는 각 풀에 대 한 STs의 검색 및 실행을 담당 하는 관리자 지정 서버인 가상 트랜잭션 감시자 노드에서 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c4899-182">These are executed on a synthetic transaction watcher node which is an administrator designated server responsible for discovery and execution of STs for each pool.</span></span></p>
<p><span data-ttu-id="c4899-183">기존 Microsoft Lync Server 2013 서버를 가상 트랜잭션 감시자 노드로 사용 하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="c4899-183">We do not recommend that you use an existing Microsoft Lync Server 2013 server as a synthetic transaction watcher node.</span></span> <span data-ttu-id="c4899-184">STs 실행에 대 한 CPU/메모리 사용량 요구 사항 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="c4899-184">This is due to the high CPU/memory usage requirements for running STs.</span></span> <span data-ttu-id="c4899-185">가상 트랜잭션 감시자 노드에 새 서버 컴퓨터 (또는 가상 서버)를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4899-185">Use a new server computer (or a virtual server) for the synthetic transaction watcher node.</span></span></p></td>
<td><p><span data-ttu-id="c4899-186">중앙 사이트</span><span class="sxs-lookup"><span data-stu-id="c4899-186">Central Site</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="c4899-187">종합 트랜잭션 감시자 노드 배포</span><span class="sxs-lookup"><span data-stu-id="c4899-187">Deploying synthetic transactions watcher node.</span></span></p>
<p><span data-ttu-id="c4899-188">문서의 MonitoringCS_withSCOM .docx 문서 연결 문서 탭을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c4899-188">Refer to the MonitoringCS_withSCOM.docx document from UCTAP connect documentation.</span></span></p></td>
<td><p><span data-ttu-id="c4899-189">중앙 사이트</span><span class="sxs-lookup"><span data-stu-id="c4899-189">Central Site</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="maximum-network-mos-scores-per-codec"></a><span data-ttu-id="c4899-190">코덱 당 최대 네트워크 SPECIALIST 점수</span><span class="sxs-lookup"><span data-stu-id="c4899-190">Maximum Network MOS scores per codec</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c4899-191">시나리오</span><span class="sxs-lookup"><span data-stu-id="c4899-191">Scenario</span></span></th>
<th><span data-ttu-id="c4899-192">코덱이나</span><span class="sxs-lookup"><span data-stu-id="c4899-192">Codec</span></span></th>
<th><span data-ttu-id="c4899-193">Max NMOS</span><span class="sxs-lookup"><span data-stu-id="c4899-193">Max NMOS</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c4899-194">UC-UC 통화</span><span class="sxs-lookup"><span data-stu-id="c4899-194">UC-UC call</span></span></p></td>
<td><p><span data-ttu-id="c4899-195">RTAudio WB</span><span class="sxs-lookup"><span data-stu-id="c4899-195">RTAudio WB</span></span></p></td>
<td><p><span data-ttu-id="c4899-196">4.10</span><span class="sxs-lookup"><span data-stu-id="c4899-196">4.10</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4899-197">UC-UC 통화</span><span class="sxs-lookup"><span data-stu-id="c4899-197">UC-UC call</span></span></p></td>
<td><p><span data-ttu-id="c4899-198">RTAudio NB</span><span class="sxs-lookup"><span data-stu-id="c4899-198">RTAudio NB</span></span></p></td>
<td><p><span data-ttu-id="c4899-199">2.95</span><span class="sxs-lookup"><span data-stu-id="c4899-199">2.95</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4899-200">컨퍼런스 통화</span><span class="sxs-lookup"><span data-stu-id="c4899-200">Conference call</span></span></p></td>
<td><p><span data-ttu-id="c4899-201">사이렌</span><span class="sxs-lookup"><span data-stu-id="c4899-201">Siren</span></span></p></td>
<td><p><span data-ttu-id="c4899-202">3.72</span><span class="sxs-lookup"><span data-stu-id="c4899-202">3.72</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4899-203">UC-PSTN 통화</span><span class="sxs-lookup"><span data-stu-id="c4899-203">UC-PSTN call</span></span></p></td>
<td><p><span data-ttu-id="c4899-204">RTAudio NB</span><span class="sxs-lookup"><span data-stu-id="c4899-204">RTAudio NB</span></span></p></td>
<td><p><span data-ttu-id="c4899-205">2.95</span><span class="sxs-lookup"><span data-stu-id="c4899-205">2.95</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4899-206">UC-PSTN 통화</span><span class="sxs-lookup"><span data-stu-id="c4899-206">UC-PSTN call</span></span></p></td>
<td><p><span data-ttu-id="c4899-207">G-711</span><span class="sxs-lookup"><span data-stu-id="c4899-207">G-711</span></span></p></td>
<td><p><span data-ttu-id="c4899-208">3.61</span><span class="sxs-lookup"><span data-stu-id="c4899-208">3.61</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="c4899-209">이전 pro 활성 모니터링 작업을 진행 하는 동안에는 Lync RA 작업 가이드에 정의 된 대로 매일, 매주, 매월의 중앙, 주 및 지사 사이트에 대 한 유지 관리 작업을 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4899-209">Over and above the previous pro-active monitoring activities, maintenance tasks should be executed for Central, Edge and Branch sites on a recurring daily, weekly and monthly basis as defined in the Lync RA Operations Guide.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

