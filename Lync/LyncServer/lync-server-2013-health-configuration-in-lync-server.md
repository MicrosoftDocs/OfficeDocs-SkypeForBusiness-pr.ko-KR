---
title: 'Lync Server 2013: Lync Server의 상태 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Health configuration in Lync Server 2013
ms:assetid: c00a8c8e-c2d2-4557-8c42-211c7cc96550
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205234(v=OCS.15)
ms:contentKeyID: 48185305
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 14a4da3ec3f06dfb573ef7e9422bdd6b751db636
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733478"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="health-configuration-in-lync-server-2013"></a><span data-ttu-id="4d8e9-102">Lync Server 2013의 상태 구성</span><span class="sxs-lookup"><span data-stu-id="4d8e9-102">Health configuration in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4d8e9-103">_**마지막으로 수정한 주제:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="4d8e9-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="4d8e9-104">다양 한 웹 사이트, Microsoft 기술 자료 문서, Lync Server Resource Kit 도구 사이에서 Lync Server를 실행할 때 문제가 발생 하는 관리자는 이러한 문제를 해결 하는 방법에 대해 크게 알지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="4d8e9-104">Between various websites, Microsoft Knowledge Base articles, and Lync Server Resource Kit tools, administrators who encounter problems when running Lync Server are never far from a way to solve those problems.</span></span>

<span data-ttu-id="4d8e9-105">예를 들어 lync Server는 네트워크 중단 및 하드웨어 오류 등의 여러 가지 기능에 영향을 받을 수 있으며, 이렇게 하면 제품 자체에서 제어할 수 없기 때문에 Lync Server 2013의 문제가 발생 하지 않는다는 보장이 없습니다</span><span class="sxs-lookup"><span data-stu-id="4d8e9-105">Obviously there is no way to guarantee that you will never encounter problems with Lync Server 2013 because Lync Server can be affected by many things—like network crashes and hardware failures—that the product itself cannot control.</span></span> <span data-ttu-id="4d8e9-106">관리자는 상태 모니터링을 구현 하 여 실제 문제로 전환 하기 전에 잠재적인 문제를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d8e9-106">By implementing health monitoring, administrators can identify potential problems before they turn into actual problems.</span></span> <span data-ttu-id="4d8e9-107">예를 들어 관리자는 Lync Server 모니터링을 사용 하 여 추세와 추세을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d8e9-107">For example, administrators can use Lync Server monitoring to identify trends and tendencies.</span></span> <span data-ttu-id="4d8e9-108">예를 들어 오디오/비디오 컨퍼런스 수가 일정 하 게 증가 함에 따라서 시스템을 오버 로드 하기 전에 용량을 추가 해야 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="4d8e9-108">For example, a steady increase in the number of audio/video conferences might suggest a need to add capacity before the system becomes overloaded.</span></span>

<span data-ttu-id="4d8e9-109">비슷한 방식으로, 관리자는 지정 된 이벤트가 발생할 경우 실시간 알림을 표시 하 고 시스템을 사전에 테스트 하는 가상 트랜잭션을 실행 하도록 System Center Operations Manager를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d8e9-109">In a similar fashion, administrators can use System Center Operations Manager to do such things as issue real-time alerts when specified events occur, and to run synthetic transactions that proactively test the system.</span></span> <span data-ttu-id="4d8e9-110">Lync Server에서 사용자가 시스템에 로그인 하거나 인스턴트 메시지를 교환 하거나 PSTN (공개 통신 네트워크)에 있는 전화기로 전화 하는 등의 일반적인 작업을 성공적으로 완료할 수 있는지 확인 하기 위해 가상 트랜잭션을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d8e9-110">Synthetic transactions are used in Lync Server to verify that users are able to successfully complete common tasks such as logging on to the system, exchanging instant messages, or making calls to a phone located on the public switched telephone network (PSTN).</span></span> <span data-ttu-id="4d8e9-111">예를 들어 이러한 테스트를 정기적으로 실행 하면 Lync Server에 로그온 하는 사용자에 게 잠재적인 문제가 발생할 수 있으며, 지원 팀이 연결을 설정할 수 없는 사용자의 전화 때문에 문제를 해결할 기회가 생깁니다.</span><span class="sxs-lookup"><span data-stu-id="4d8e9-111">For example, periodically running these tests can alert you to potential problems with users logging on to Lync Server, and give you a chance to correct the problem before your support team is flooded with calls from users unable to make a connection.</span></span> <span data-ttu-id="4d8e9-112">System Center Operations Manager를 사용 하 여 이러한 가상 트랜잭션을 실행 하면 관리자가 모든 메시지에 응답 하는 것 보다 많은 작업을 수행 하지 않고도 매일 24 시간 동안 지속적으로 Lync Server의 배포를 정기적으로 모니터링할 수 있습니다. 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d8e9-112">By using System Center Operations Manager to run these synthetic transactions, administrators can routinely monitor their deployment of Lync Server continuously for 24 hours every day without having to do much of anything beyond responding to any alerts that might be issued.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4d8e9-113">Lync Server 2013의 경우 System Center Operations Manager 용 관리 팩은 Lync Server에 좋지 않은 영향을 줄 수 있는 "외부" 문제를 검색할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d8e9-113">For Lync Server 2013, the Management Pack for System Center Operations Manager is also able to detect "external" issues that can adversely affect Lync Server.</span></span> <span data-ttu-id="4d8e9-114">예를 들어 관리자는 IIS (인터넷 정보 서비스)가 오프 라인 상태 이거나 Lync Server 컴퓨터의 시스템 리소스가 지정 된 금액 이하로 떨어지면 Lync Server 컴퓨터에 하드웨어 오류가 발생 하는 경우 알림을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d8e9-114">For example, administrators can be notified if Internet Information Services (IIS) goes offline, system resources on a Lync Server computer fall below a specified amount, or a Lync Server computer experiences a hardware failure.</span></span>



</div>

<span data-ttu-id="4d8e9-115">Lync Server 2013의 상태 구성은 System Center Operations Manager 및 Lync Server 관리 팩 사용을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d8e9-115">Health configuration in Lync Server 2013 is built around System Center Operations Manager and the use of Lync Server Management Packs.</span></span> <span data-ttu-id="4d8e9-116">이러한 관리 팩에는 다음과 같은 여러 가지 새로운 기능과 향상 된 기능이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d8e9-116">These Management Packs include a number of new features and enhancements, including:</span></span>

  - <span data-ttu-id="4d8e9-117">**모든 위치의 시나리오 가용성.**</span><span class="sxs-lookup"><span data-stu-id="4d8e9-117">**Scenario availability from any location.**</span></span> <span data-ttu-id="4d8e9-118">Lync Server 2010 관리 팩에는 가상 트랜잭션으로 최종 사용자 시나리오 가용성을 모니터링 하는 개념이 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="4d8e9-118">The Lync Server 2010 Management Pack introduced the concept of monitoring end user scenario availability with synthetic transactions.</span></span> <span data-ttu-id="4d8e9-119">Lync Server 2013에서 이러한 에이전트는 더 많은 가상 트랜잭션을 사용 하며 엔터프라이즈 내의 다양 한 위치, 기업 외부의 원격 지리적 위치, 지사 기기 및 Lync Server 2010에서 실행할 수 있습니다. 레거시 Edge 배포에 적용 범위를 추가 하는 배포</span><span class="sxs-lookup"><span data-stu-id="4d8e9-119">In Lync Server 2013, these agents have more synthetic transactions and can be run from a variety of locations inside the enterprise, from remote geographic locations outside of the enterprise, against branch office appliances and against Lync Server 2010 deployments to add coverage to legacy Edge deployments.</span></span>

  - <span data-ttu-id="4d8e9-120">**가상 트랜잭션 로그.**</span><span class="sxs-lookup"><span data-stu-id="4d8e9-120">**Synthetic transaction logs.**</span></span> <span data-ttu-id="4d8e9-121">가상 트랜잭션이 실패 하는 경우, 관리자는 HTML 로그에 액세스 하 여 실패 한 내용을 확인 하는 데 도움을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4d8e9-121">When a synthetic transaction fails, administrators have access to HTML logs to help determine what failed.</span></span> <span data-ttu-id="4d8e9-122">여기에는 실패 한 작업, 각 작업의 대기 시간, 테스트를 실행 하는 데 사용 된 명령줄 및 발생 한 오류에 대 한 이해가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4d8e9-122">This includes understanding which action failed, the latency of each action, the command-line used to run the test, and the error that was encountered.</span></span>

  - <span data-ttu-id="4d8e9-123">**향상 된 통화 안정성 범위.**</span><span class="sxs-lookup"><span data-stu-id="4d8e9-123">**Increased call reliability coverage.**</span></span> <span data-ttu-id="4d8e9-124">Lync Server 2010 관리 팩은 호출 안정성 경고를 도입 하 여 최종 사용자의 오디오 통화에 영향을 주는 심각한 연결 문제를 감지 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d8e9-124">The Lync Server 2010 Management Pack introduced call reliability alerting to detect severe connectivity issues that affect the audio calls of end users.</span></span> <span data-ttu-id="4d8e9-125">Lync Server 2013 관리 팩은 피어 투 피어 인스턴트 메시징 (IM) 및 기타 기본 회의 기능에 대 한 적용 범위를 추가 하 여 노이즈를 줄이면서 검사 범위를 최대화 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d8e9-125">The Lync Server 2013 Management Packs add coverage for peer-to-peer instant messaging (IM) and other basic conferencing features to maximize coverage while reducing noise.</span></span>

  - <span data-ttu-id="4d8e9-126">**종속성 모니터링.**</span><span class="sxs-lookup"><span data-stu-id="4d8e9-126">**Dependency monitoring.**</span></span> <span data-ttu-id="4d8e9-127">Lync Server 시나리오는 IIS (오프 라인 상태), 제한 된 CPU 및 메모리 리소스, 디스크 문제 등 다양 한 외부 요인으로 인해 실패할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d8e9-127">Lync Server scenarios can fail due to a variety of external factors such as IIS being offline, limited CPU and memory resources, and disk issues.</span></span> <span data-ttu-id="4d8e9-128">새 관리 팩은 관리자가 영향을 인식 하도록 몇 가지 중요 한 종속성을 검사 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d8e9-128">The new management packs check several critical dependencies to ensure administrators are aware of their impact.</span></span>

  - <span data-ttu-id="4d8e9-129">**향상 된 보고.**</span><span class="sxs-lookup"><span data-stu-id="4d8e9-129">**Enhanced reporting.**</span></span> <span data-ttu-id="4d8e9-130">관리자가 시나리오 가용성을 예측 하 고, 용량을 계획 하 고, 문제가 발생 하는 구성 요소를 확인 하는 데 도움이 되는 보고서 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="4d8e9-130">A set of reports to help administrators estimate scenario availability, plan for capacity, and see which components are experiencing the most issues.</span></span>

<span data-ttu-id="4d8e9-131">관리 팩에는 Lync Server 배포 상태에 대 한 실시간 가시성을 감지 하 고 진단 하는 데 도움이 되는 다양 한 기능이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d8e9-131">The Management Packs also include a variety of features to help detect and diagnose provide real-time visibility into the health your Lync Server deployment.</span></span> <span data-ttu-id="4d8e9-132">이러한 기능은 다음 표에 나열 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d8e9-132">These features are listed in the following table.</span></span>

### <a name="management-pack-features"></a><span data-ttu-id="4d8e9-133">관리 팩 기능</span><span class="sxs-lookup"><span data-stu-id="4d8e9-133">Management Pack Features</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4d8e9-134">기능</span><span class="sxs-lookup"><span data-stu-id="4d8e9-134">Feature</span></span></th>
<th><span data-ttu-id="4d8e9-135">설명</span><span class="sxs-lookup"><span data-stu-id="4d8e9-135">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4d8e9-136">가상 트랜잭션</span><span class="sxs-lookup"><span data-stu-id="4d8e9-136">Synthetic Transactions</span></span></p></td>
<td><p><span data-ttu-id="4d8e9-137">다양 한 위치에서 실행할 수 있는 Windows PowerShell cmdlet을 사용 하 여 로그인, 현재 상태, 메신저 대화, 회의 등의 최종 사용자 시나리오가 최종 사용자에 게 즉시 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4d8e9-137">Windows PowerShell cmdlets that can be run from various locations to ensure that end user scenarios such as sign-in, presence, IM, and conferencing are readily available to end users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4d8e9-138">호출 안정성 알림</span><span class="sxs-lookup"><span data-stu-id="4d8e9-138">Call Reliability Alerts</span></span></p></td>
<td><p><span data-ttu-id="4d8e9-139">CDR (통화 정보 레코드)에 대 한 데이터베이스 쿼리</span><span class="sxs-lookup"><span data-stu-id="4d8e9-139">Database queries for Call Detail Records (CDR).</span></span> <span data-ttu-id="4d8e9-140">이 레코드는 최종 사용자가 통화에 연결할 수 있는지 여부 또는 통화가 종료 된 이유를 반영 하도록 프런트 엔드 서버에서 기록 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4d8e9-140">These records are written by Front End Servers to reflect whether end users were able to connect to a call or why a call was terminated.</span></span> <span data-ttu-id="4d8e9-141">이러한 쿼리는 다양 한 최종 사용자가 피어 투 피어 통화 또는 기본 회의 기능에 대 한 연결 문제가 발생 하는 경우를 나타내는 경고를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d8e9-141">These queries result in alerts that indicate when a wide range of end users are experiencing connectivity issues for peer-to-peer calls or basic conferencing functionality.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4d8e9-142">미디어 품질 알림</span><span class="sxs-lookup"><span data-stu-id="4d8e9-142">Media Quality Alerts</span></span></p></td>
<td><p><span data-ttu-id="4d8e9-143">각 호출이 끝날 때 클라이언트가 게시 한 체감 품질 (환경 품질) 보고서를 보고 하는 데이터베이스 쿼리</span><span class="sxs-lookup"><span data-stu-id="4d8e9-143">Database queries that look at Quality of Experience (QoE) reports published by clients at the end of each call.</span></span> <span data-ttu-id="4d8e9-144">이러한 쿼리는 사용자가 통화와 회의 중에 잘못 된 미디어 품질을 발생 시킬 수 있는 시나리오를 정확 하 게 알려 주는 경고를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d8e9-144">These queries result in alerts that pinpoint scenarios where users are likely to be experiencing poor media quality during calls and conferences.</span></span> <span data-ttu-id="4d8e9-145">이 데이터는 패킷 대기 시간, 손실, 통화 음질에 직접 참가 하는 것으로 알려진 메트릭과 같은 주요 메트릭에 따라 작성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4d8e9-145">The data is built upon key metrics such as packet latency and loss, metrics that are known to directly contribute to call quality.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4d8e9-146">구성 요소 상태</span><span class="sxs-lookup"><span data-stu-id="4d8e9-146">Component Health</span></span></p></td>
<td><p><span data-ttu-id="4d8e9-147">개별 서버 구성 요소는 이벤트 로그 및 성능 카운터를 사용 하 여 알림을 발생 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="4d8e9-147">Individual server components raise alerts by using event logs and performance counters.</span></span> <span data-ttu-id="4d8e9-148">이러한 경고는 하나 이상의 최종 사용자 시나리오에 심각한 영향을 줄 수 있는 오류 조건을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="4d8e9-148">These alerts indicate failure conditions that can severely impact one or more end user scenarios.</span></span> <span data-ttu-id="4d8e9-149">이러한 알림은 실행 되지 않는 서비스, 높은 오류율 속도, 높은 메시지 대기 시간 또는 연결 문제를 포함 하 여 다양 한 오류 조건을 표시할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d8e9-149">These alerts can also indicate a variety of other failure conditions, including services not running, high failure rates, high message latency, or connectivity issues.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4d8e9-150">종속성 상태</span><span class="sxs-lookup"><span data-stu-id="4d8e9-150">Dependency Health</span></span></p></td>
<td><p><span data-ttu-id="4d8e9-151">다양 한 외부 이유로 실패가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d8e9-151">Failures can occur for a variety of external reasons.</span></span> <span data-ttu-id="4d8e9-152">이제 관리 팩은 IIS 가용성, 서버와 프로세스의 CPU 및 메모리 사용, 디스크 메트릭의 등 심각한 문제를 나타내는 중요 한 외부 종속성에 대 한 데이터를 모니터링 하 고 수집 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d8e9-152">The management packs now monitor and collect data for some of the critical external dependencies that might indicate severe issues, including IIS availability, CPU and memory usage of servers and processes, and disk metrics.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="4d8e9-153">시스템에서 발급 하는 알림은 다음과 같은 세 가지 일반 범주로 분류 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d8e9-153">The alerts issued by the system have been classified into three general categories:</span></span>

  - <span data-ttu-id="4d8e9-154">**우선 순위가 높은 알림**</span><span class="sxs-lookup"><span data-stu-id="4d8e9-154">**High-priority Alerts.**</span></span> <span data-ttu-id="4d8e9-155">이러한 알림은 대규모 사용자 그룹에 대 한 서비스 중단을 발생 시키는 조건을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="4d8e9-155">These alerts indicate conditions that will cause service outages for large groups of users.</span></span> <span data-ttu-id="4d8e9-156">예를 들어 Lync Server 2013에는 고가용성 기능이 기본적으로 제공 되므로 단일 컴퓨터의 구성 요소 오류는 우선 순위가 높은 알림이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="4d8e9-156">For example, a component failure on a single machine is not a high-priority alert because Lync Server 2013 has built-in high availability features.</span></span> <span data-ttu-id="4d8e9-157">그 대신 우선 순위가 높은 알림은 "야간 모드의 관리자를 종료 하는 데 매우 심각한" 문제를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d8e9-157">Instead, high-priority alerts represent problems serious enough “to wake up administrators at night.”</span></span> <span data-ttu-id="4d8e9-158">통합 된 트랜잭션 및 오프 라인 서비스 (예: 오디오/비디오 회의)가 중단 하는 경우 우선 순위가 높은 알림으로 인식 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4d8e9-158">Outages detected by synthetic transactions and offline services (for example, audio/video conferencing) qualify as high-priority alerts.</span></span>

  - <span data-ttu-id="4d8e9-159">**보통 우선 순위의 알림.**</span><span class="sxs-lookup"><span data-stu-id="4d8e9-159">**Medium-priority alerts.**.</span></span> <span data-ttu-id="4d8e9-160">이러한 알림은 사용자의 하위 집합에 영향을 주거나 통화 품질 저하를 표시 하는 조건을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="4d8e9-160">These alerts indicate conditions that affect a subset of users or indicate call quality degradation.</span></span> <span data-ttu-id="4d8e9-161">여기에는 구성 요소 오류, 통화 대기 시간 설정, 통화 중 저하 된 오디오 음질 등의 문제가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4d8e9-161">That includes problems such as component failures, latency in call establishment, or degraded audio quality in call.</span></span> <span data-ttu-id="4d8e9-162">이 범주의 알림은 상태를 저장 하 고 문제의 현재 상태를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="4d8e9-162">Alerts in this category are stateful and indicate the current status of the issue.</span></span> <span data-ttu-id="4d8e9-163">예를 들어 통화 성립 시간이 알림 임계값을 초과 한다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d8e9-163">For example, suppose your call establishment times exceed the alert threshold.</span></span> <span data-ttu-id="4d8e9-164">통화 설정 시간이 일반으로 반환 되는 경우 System Center Operations Manager에서 이러한 알림이 자동으로 해결 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4d8e9-164">If call establishment times return to normal, these alerts will be auto-resolved in System Center Operations Manager.</span></span> <span data-ttu-id="4d8e9-165">이러한 알림은 관리자가 같은 영업일에 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d8e9-165">The expectation for these alerts is that an administrator will look at them on the same business day.</span></span>

  - <span data-ttu-id="4d8e9-166">**다른 알림.**</span><span class="sxs-lookup"><span data-stu-id="4d8e9-166">**Other alerts.**</span></span> <span data-ttu-id="4d8e9-167">이는 특정 사용자 또는 사용자의 하위 집합에 영향을 줄 수 있는 구성 요소의 알림입니다.</span><span class="sxs-lookup"><span data-stu-id="4d8e9-167">These are alerts from components that might affect a specific user or subset of users.</span></span> <span data-ttu-id="4d8e9-168">예를 들어 주소록 서비스에서 지정 된 사용자의 Active Directory 항목을 구문 분석할 수 없는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d8e9-168">For example, perhaps the Address Book service could not parse the Active Directory entry of a given user.</span></span> <span data-ttu-id="4d8e9-169">이러한 알림은 관리자가 사용할 수 있는 시간에 도달 하는 것이 가장 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="4d8e9-169">The expectation for these alerts is that administrators will get to them when they have time available.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="4d8e9-170">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="4d8e9-170">In This Section</span></span>

  - [<span data-ttu-id="4d8e9-171">Lync Server 2013에서 System Center Operations Manager와 작동 하도록 구성</span><span class="sxs-lookup"><span data-stu-id="4d8e9-171">Configuring Lync Server 2013 to work with System Center Operations Manager</span></span>](lync-server-2013-configuring-lync-server-to-work-with-system-center-operations-manager.md)

  - [<span data-ttu-id="4d8e9-172">Lync Server 2013에서 종합 거래에 대 한 풍부한 로깅 사용</span><span class="sxs-lookup"><span data-stu-id="4d8e9-172">Using rich logging for synthetic transactions in Lync Server 2013</span></span>](lync-server-2013-using-rich-logging-for-synthetic-transactions.md)

  - [<span data-ttu-id="4d8e9-173">Lync Server 2013의 System Center Operations Manager 데이터베이스로 Microsoft SQL Server 2008 R2를 사용 하는 경우</span><span class="sxs-lookup"><span data-stu-id="4d8e9-173">Using Microsoft SQL Server 2008 R2 as your System Center Operations Manager database for Lync Server 2013</span></span>](lync-server-2013-using-microsoft-sql-server-2008-r2-as-your-system-center-operations-manager-database.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

