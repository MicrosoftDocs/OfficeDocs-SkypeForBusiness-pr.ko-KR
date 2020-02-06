---
title: 비즈니스용 Skype 서버 통계 관리자에 대한 계획
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: f0ec68e1-de01-4a92-b67d-703149b05caf
description: '요약: 비즈니스용 Skype 서버용 통계 관리자에 대 한 자세한 내용은이 항목을 참조 하세요.'
ms.openlocfilehash: 0bf7a5366047a0f4435a98cd8bca75eeb3ebc8d7
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816237"
---
# <a name="plan-for-statistics-manager-for-skype-for-business-server"></a><span data-ttu-id="f380f-103">비즈니스용 Skype 서버 통계 관리자에 대한 계획</span><span class="sxs-lookup"><span data-stu-id="f380f-103">Plan for Statistics Manager for Skype for Business Server</span></span>

<span data-ttu-id="f380f-104">**요약:** 비즈니스용 Skype 서버용 통계 관리자에 대 한 자세한 내용은이 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f380f-104">**Summary:** Read this topic to learn about Statistics Manager for Skype for Business Server.</span></span>

 <span data-ttu-id="f380f-105">비즈니스용 Skype Server의 통계 관리자는 비즈니스용 Skype 서버 상태 및 성능 데이터를 실시간으로 볼 수 있는 강력한 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="f380f-105">Statistics Manager for Skype for Business Server is a powerful tool that allows you to view Skype for Business Server health and performance data in real time.</span></span> <span data-ttu-id="f380f-106">여러 서버에서 성능 데이터를 몇 초 마다 폴링하거나 통계 관리자 웹 사이트에서 즉시 결과를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f380f-106">You can poll performance data across hundreds of servers every few seconds, and view the results instantly on the Statistics Manager Website.</span></span>

<span data-ttu-id="f380f-107">통계 관리자를 사용 하 여 진행 중인 성능 문제를 식별 하 고, 환경에 대 한 계획 된 변경 결과를 확인 하 고, 중단 된 문제 해결을 추적할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f380f-107">You can use Statistics Manager to identify ongoing performance issues, view the results of a planned change to your environment, track resolution of outages, and much more.</span></span> <span data-ttu-id="f380f-108">이 상자 밖의 통계 관리자는 KHI (키 상태 표시기) 임계값으로 구성 되며, 배포의 고유한 요구에 맞게 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f380f-108">Out of the box, Statistics Manager is configured with Key Health Indicator (KHI) thresholds, and can be customized to suit your deployment's unique needs.</span></span>

<span data-ttu-id="f380f-109">단일 서버가 모든 서버 쪽 통계 관리자 구성 요소를 호스트 하는 온-프레미스 배포에서 통계 관리자를 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f380f-109">You can deploy Statistics Manager in an on-premises deployment in which a single server hosts all of the server-side Statistics Manager components.</span></span> <span data-ttu-id="f380f-110">통계 관리자 배포에 대 한 자세한 내용은 비즈니스용 [Skype 서버에 대 한 통계 관리자 배포](deploy.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f380f-110">For more information about deploying Statistics Manager, see [Deploy Statistics Manager for Skype for Business Server](deploy.md).</span></span> <span data-ttu-id="f380f-111">이미 통계 관리자 배포를 보유 하 고 있지만 릴리스 2.0으로 업그레이드 하지 않은 경우 비즈니스용 Skype 서버용 릴리스 2.0 및 [업그레이드 통계 관리자](upgrade.md) [의 새로운 기능](plan.md#BKMK_WhatsNew) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f380f-111">If you already have an existing deployment of Statistics Manager, but you have not yet upgraded to Release 2.0, see [What's new in Release 2.0](plan.md#BKMK_WhatsNew) and [Upgrade Statistics Manager for Skype for Business Server](upgrade.md).</span></span>

<span data-ttu-id="f380f-112">이 항목에서는 다음 섹션을 다룹니다.</span><span class="sxs-lookup"><span data-stu-id="f380f-112">This topic contains the following sections:</span></span>

- [<span data-ttu-id="f380f-113">기능 및 기능</span><span class="sxs-lookup"><span data-stu-id="f380f-113">Features and capabilities</span></span>](plan.md#BKMK_Features)

- [<span data-ttu-id="f380f-114">릴리스 2.0의 새로운 기능</span><span class="sxs-lookup"><span data-stu-id="f380f-114">What's new in Release 2.0</span></span>](plan.md#BKMK_WhatsNew)

- [<span data-ttu-id="f380f-115">구성</span><span class="sxs-lookup"><span data-stu-id="f380f-115">Components</span></span>](plan.md#BKMK_Components)

- [<span data-ttu-id="f380f-116">온-프레미스 배포</span><span class="sxs-lookup"><span data-stu-id="f380f-116">On-premises deployment</span></span>](plan.md#BKMK_DeploymentOptions)

- [<span data-ttu-id="f380f-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f380f-117">Requirements</span></span>](plan.md#BKMK_Requirements)

- [<span data-ttu-id="f380f-118">보안 고려 사항</span><span class="sxs-lookup"><span data-stu-id="f380f-118">Security considerations</span></span>](plan.md#BKMK_Security)

## <a name="features-and-capabilities"></a><span data-ttu-id="f380f-119">기능 및 기능</span><span class="sxs-lookup"><span data-stu-id="f380f-119">Features and capabilities</span></span>
<span data-ttu-id="f380f-120"><a name="BKMK_Features"> </a></span><span class="sxs-lookup"><span data-stu-id="f380f-120"><a name="BKMK_Features"> </a></span></span>

<span data-ttu-id="f380f-121">통계 관리자는 다음 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f380f-121">Statistics Manager allows you to:</span></span>

- <span data-ttu-id="f380f-122">실시간으로 모든 서버의 원시 데이터를 볼 때</span><span class="sxs-lookup"><span data-stu-id="f380f-122">View raw data for all servers in real time.</span></span> <span data-ttu-id="f380f-123">(데이터는 매우 높은 속도로 샘플링 되며 웹 사이트에는 1 초 이내에 전송 됩니다.)</span><span class="sxs-lookup"><span data-stu-id="f380f-123">(Data is sampled at a very high rate and sent to the website in less than one second.)</span></span>

- <span data-ttu-id="f380f-124">특정 역할에 대해 집계 된 데이터를 봅니다. 예를 들어 프런트 엔드 서버, 중재 서버, Edge 서버 등입니다.</span><span class="sxs-lookup"><span data-stu-id="f380f-124">View data that is aggregated for a specific role; for example, Front End Server, Mediation Server, Edge Server, and so on.</span></span>

- <span data-ttu-id="f380f-125">드릴 다운을 클릭 하 여 특정 사이트, 사이트 내의 특정 풀, 그리고 풀 내의 특정 서버에 대 한 데이터를 봅니다.</span><span class="sxs-lookup"><span data-stu-id="f380f-125">Drill down to view data for specific sites, specific pools within the site, and then specific servers within the pool.</span></span>

- <span data-ttu-id="f380f-126">선택 된 카운터가 기본적으로 표시 되도록 사용자 지정 차트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f380f-126">Create custom charts so that chosen counters are shown by default.</span></span>

- <span data-ttu-id="f380f-127">X 축과 y 축 모두 또는 x 축을 기준으로 확대/축소 및 팬</span><span class="sxs-lookup"><span data-stu-id="f380f-127">Zoom and pan on both the x- and y- axes or on the x-axis only.</span></span>

- <span data-ttu-id="f380f-128">날짜 범위 또는 시점을 사용 하 여 데이터를 필터링 합니다.</span><span class="sxs-lookup"><span data-stu-id="f380f-128">Use date ranges or points in time to filter data.</span></span>

- <span data-ttu-id="f380f-129">설정 된 키 상태 표시기 (KHIs)를 기준으로 서버 성능을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="f380f-129">View server performance based on established key health indicators (KHIs).</span></span> <span data-ttu-id="f380f-130">KHIs는 정상 범위가 정의 된 성능 카운터의 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f380f-130">KHIs represent a collection of performance counters with a defined healthy range.</span></span>

- <span data-ttu-id="f380f-131">각 카운터에 대 한 자세한 메트릭을 봅니다.</span><span class="sxs-lookup"><span data-stu-id="f380f-131">View detailed metrics for each counter.</span></span>

- <span data-ttu-id="f380f-132">여러 모집단 또는 서버에 걸친 데이터를 비교 합니다.</span><span class="sxs-lookup"><span data-stu-id="f380f-132">Compare data across multiple populations or servers.</span></span>

- <span data-ttu-id="f380f-133">현재 데이터를 대시보드 서비스에 보고 하지 않는 에이전트를 식별 하는 알 수 없는 카운터 보고서를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="f380f-133">View latent counter reports to identify agents that are not reporting current data to the dashboard service.</span></span>

- <span data-ttu-id="f380f-134">차트 데이터의 특정 인스턴스를 파일에 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="f380f-134">Save a particular instance of chart data to a file.</span></span>

- <span data-ttu-id="f380f-135">업데이트를 포함 하 여 실시간으로 KHIs.</span><span class="sxs-lookup"><span data-stu-id="f380f-135">View KHIs in real time, including updates.</span></span> <span data-ttu-id="f380f-136">기록 보기를 사용 하도록 설정 하면 새 오류만 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f380f-136">If the history view is enabled, only new failures are shown.</span></span>

  - <span data-ttu-id="f380f-137">한 번에 모든 KHIs</span><span class="sxs-lookup"><span data-stu-id="f380f-137">View all KHIs at one time</span></span>

  - <span data-ttu-id="f380f-138">서버 별로 KHIs (가로 보기)</span><span class="sxs-lookup"><span data-stu-id="f380f-138">View KHIs by server (Landscape view)</span></span>

  - <span data-ttu-id="f380f-139">KHI 정의 보기</span><span class="sxs-lookup"><span data-stu-id="f380f-139">View KHI definitions</span></span>

## <a name="whats-new-in-release-20"></a><span data-ttu-id="f380f-140">릴리스 2.0의 새로운 기능</span><span class="sxs-lookup"><span data-stu-id="f380f-140">What's new in Release 2.0</span></span>
<span data-ttu-id="f380f-141"><a name="BKMK_WhatsNew"> </a></span><span class="sxs-lookup"><span data-stu-id="f380f-141"><a name="BKMK_WhatsNew"> </a></span></span>

<span data-ttu-id="f380f-142">다음은 릴리스 2.0의 새로운 기능에 대 한 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="f380f-142">The following describes what's new in Release 2.0.</span></span> <span data-ttu-id="f380f-143">기존 통계 관리자 배포가 있지만 아직 업그레이드 하지 않은 경우 비즈니스용 [Skype 서버용 업데이트 통계 관리자](upgrade.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f380f-143">If you have an existing deployment of Statistics Manager and you've not yet upgraded, see [Upgrade Statistics Manager for Skype for Business Server](upgrade.md).</span></span>

- <span data-ttu-id="f380f-144">Edge 미디어, 패브릭 상태, 풀 장애 조치 및 등록 시나리오에 대 한 시나리오 보기가 추가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f380f-144">Scenario views have been added for Edge Media, Fabric Health, Pool Failover and Registration scenarios.</span></span>

- <span data-ttu-id="f380f-145">SQL server, 더 많은 비즈니스용 Skype 사용 카운터 등의 여러 가지 새로운 카운터가 추가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f380f-145">Many new counters have been added for SQL servers, more Skype for Business usage counters, and so on.</span></span>

- <span data-ttu-id="f380f-146">통계 관리자 에이전트에 대 한 감시자 노드 통합-에이전트가 감시자 노드에 설치 되어 있는 경우에는 통계가 통계 관리자에 대 한 카운터로 서의 가상 트랜잭션 통계를 보고 합니다.</span><span class="sxs-lookup"><span data-stu-id="f380f-146">Watcher node integration for the Statistics Manager Agent - if the Agent is installed on a watcher node, it will report synthetic transaction statistics as counters back to Statistics Manager.</span></span>

- <span data-ttu-id="f380f-147">다양 한 안정성 및 성능 향상.</span><span class="sxs-lookup"><span data-stu-id="f380f-147">Numerous reliability and performance improvements.</span></span>

<span data-ttu-id="f380f-148">실행 중인 통계 관리자 웹 사이트의 버전을 확인 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="f380f-148">To verify the version of the Statistics Manager Website you are running:</span></span>

- <span data-ttu-id="f380f-149">파일 탐색기에서 (기본 디렉터리) Files\Skype Business Server StatsMan에 대 한 C:\Program WebSite\bin</span><span class="sxs-lookup"><span data-stu-id="f380f-149">In File Explorer, open (default directory) C:\Program Files\Skype for Business Server StatsMan WebSite\bin</span></span>

- <span data-ttu-id="f380f-150">StatsManHubWebSite를 마우스 오른쪽 단추로 클릭 하 고 속성 보기</span><span class="sxs-lookup"><span data-stu-id="f380f-150">Right click on StatsManHubWebSite.dll and view its properties</span></span>

- <span data-ttu-id="f380f-151">제품 버전이 설명 세부 정보에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f380f-151">The product version will be shown in the Description details.</span></span>

## <a name="components"></a><span data-ttu-id="f380f-152">구성</span><span class="sxs-lookup"><span data-stu-id="f380f-152">Components</span></span>
<span data-ttu-id="f380f-153"><a name="BKMK_Components"> </a></span><span class="sxs-lookup"><span data-stu-id="f380f-153"><a name="BKMK_Components"> </a></span></span>

<span data-ttu-id="f380f-154">통계 관리자는 다음 구성 요소로 구성 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f380f-154">Statistics Manager consists of the following components:</span></span>

- <span data-ttu-id="f380f-155">**에이전트.**</span><span class="sxs-lookup"><span data-stu-id="f380f-155">**Agent.**</span></span> <span data-ttu-id="f380f-156">모니터링 되는 각 서버에서 실행 되는 경량 에이전트</span><span class="sxs-lookup"><span data-stu-id="f380f-156">A lightweight agent that runs on each monitored server.</span></span> <span data-ttu-id="f380f-157">에이전트는 로컬 집계를 사용 하 여 성능 카운터에 대해 구성 가능한 높은 속도 폴링을 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f380f-157">The Agent allows configurable high rate polling of performance counters with local aggregation.</span></span>

- <span data-ttu-id="f380f-158">**수신기.**</span><span class="sxs-lookup"><span data-stu-id="f380f-158">**Listener.**</span></span> <span data-ttu-id="f380f-159">모든 에이전트에서 데이터를 수신 하는 서버 쪽 API를 통해 모집단 간에 데이터를 집계 합니다.</span><span class="sxs-lookup"><span data-stu-id="f380f-159">The server side API that receives data from all Agents, and aggregates data across populations.</span></span>

- <span data-ttu-id="f380f-160">**허브.**</span><span class="sxs-lookup"><span data-stu-id="f380f-160">**Hub.**</span></span> <span data-ttu-id="f380f-161">시스템에 대 한 클라이언트 API 역할을 하며 웹 서버에서 실행 되며 웹 사이트를 통해 연결 된 클라이언트에 실시간 데이터 업데이트를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="f380f-161">Serves as the client API for the system, runs on the web server(s), and provides real-time data updates to clients connected via the website.</span></span> <span data-ttu-id="f380f-162">(허브는 웹 사이트 msi의 일부로 자동으로 설치 됩니다.)</span><span class="sxs-lookup"><span data-stu-id="f380f-162">(The Hub is automatically installed as part of the Website msi.)</span></span>

- <span data-ttu-id="f380f-163">**웹 사이트.**</span><span class="sxs-lookup"><span data-stu-id="f380f-163">**Website.**</span></span> <span data-ttu-id="f380f-164">시스템에서 사용할 수 있는 모든 기능을 함께 가져오는 사용자 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="f380f-164">A user interface that pulls together all the features available in the system.</span></span>

<span data-ttu-id="f380f-165">또한, 통계 관리자에는 메모리 내 캐싱에 개방형 원본 데이터 구조 서버인 **Redis**이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="f380f-165">In addition, Statistics Manager requires **Redis**, an open-sourced data structure server for in-memory caching.</span></span> <span data-ttu-id="f380f-166">Redis를 다운로드 하는 방법에 대 한 자세한 내용은 [통계 관리자 배포](deploy.md#BKMK_Deploy) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f380f-166">For more information about downloading Redis, see [Deploy Statistics Manager](deploy.md#BKMK_Deploy) .</span></span>

## <a name="on-premises-deployment"></a><span data-ttu-id="f380f-167">온-프레미스 배포</span><span class="sxs-lookup"><span data-stu-id="f380f-167">On-premises deployment</span></span>
<span data-ttu-id="f380f-168"><a name="BKMK_DeploymentOptions"> </a></span><span class="sxs-lookup"><span data-stu-id="f380f-168"><a name="BKMK_DeploymentOptions"> </a></span></span>

<span data-ttu-id="f380f-169">온-프레미스 배포의 경우 단일 서버가 모든 서버 쪽 통계 관리자 구성 요소를 호스팅합니다.</span><span class="sxs-lookup"><span data-stu-id="f380f-169">In an on-premises deployment, a single server hosts all of the server-side Statistics Manager components.</span></span>

<span data-ttu-id="f380f-170">다음 다이어그램에서는 통계 관리자 웹 사이트, 허브, 수신기 및 Redis 캐싱 시스템이 단일 컴퓨터에서 호스팅되는 온-프레미스 배포를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f380f-170">The following diagram shows an on-premises deployment, in which the Statistics Manager Website, Hub, Listener, and Redis caching system are hosted on a single machine.</span></span> <span data-ttu-id="f380f-171">통계 관리자는 세 개의 비즈니스용 Skype 서버를 모니터링 하 고 있으며, 각각은 단일 에이전트가 데이터를 수신기로 전송 합니다.</span><span class="sxs-lookup"><span data-stu-id="f380f-171">Statistics Manager is monitoring three Skype for Business servers, each of which have a single Agent transmitting data to the Listener.</span></span> <span data-ttu-id="f380f-172">사용자가 단일 웹 사이트에 연결 하 여 통계 관리자가 집계 한 모든 데이터를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f380f-172">Users connect to a single Website to view all data aggregated by Statistics Manager:</span></span>

![통계 관리자 온-프레미스 배포](../../media/c7c9d0b5-a70b-4d8c-aec4-0128a29b90b6.png)

## <a name="requirements"></a><span data-ttu-id="f380f-174">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f380f-174">Requirements</span></span>
<span data-ttu-id="f380f-175"><a name="BKMK_Requirements"> </a></span><span class="sxs-lookup"><span data-stu-id="f380f-175"><a name="BKMK_Requirements"> </a></span></span>

<span data-ttu-id="f380f-176">통계 관리자를 배포 하기 전에 다음 소프트웨어, 네트워킹 및 하드웨어 요구 사항을 고려해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f380f-176">You will need to consider the following software, networking, and hardware requirements before you deploy Statistics Manager.</span></span>

### <a name="software-requirements"></a><span data-ttu-id="f380f-177">소프트웨어 요구 사항</span><span class="sxs-lookup"><span data-stu-id="f380f-177">Software requirements</span></span>

- <span data-ttu-id="f380f-178">Windows Server 2016 및 2019</span><span class="sxs-lookup"><span data-stu-id="f380f-178">Windows Server 2016 and 2019</span></span>

- <span data-ttu-id="f380f-179">IIS (자동으로 설치 됨)</span><span class="sxs-lookup"><span data-stu-id="f380f-179">IIS (automatically installed)</span></span>

- <span data-ttu-id="f380f-180">Redis</span><span class="sxs-lookup"><span data-stu-id="f380f-180">Redis</span></span>

- <span data-ttu-id="f380f-181">통계 관리자 서비스 (자동 설치 됨)</span><span class="sxs-lookup"><span data-stu-id="f380f-181">Statistics Manager services (automatically installed)</span></span>

- <span data-ttu-id="f380f-182">PSExec-원격 에이전트 배포에 필요</span><span class="sxs-lookup"><span data-stu-id="f380f-182">PSExec - Required to do remote agent deployment</span></span>

- <span data-ttu-id="f380f-183">.NET 4.5 (2012 R2에 포함)-에이전트 및 서버 쪽 구성 요소에 필요</span><span class="sxs-lookup"><span data-stu-id="f380f-183">.NET 4.5 (included with 2012 R2) - Required for agents and server-side components</span></span>
- <span data-ttu-id="f380f-184">[비즈니스용 Skype Server, 실시간 통계 관리자 다운로드 (64 비트)](https://www.microsoft.com/en-in/download/details.aspx?id=57518)</span><span class="sxs-lookup"><span data-stu-id="f380f-184">Download the [Skype for Business Server, Real-Time Statistics Manager (64-bit)](https://www.microsoft.com/en-in/download/details.aspx?id=57518)</span></span>

### <a name="networking-requirements"></a><span data-ttu-id="f380f-185">네트워킹 요구 사항</span><span class="sxs-lookup"><span data-stu-id="f380f-185">Networking requirements</span></span>


|<span data-ttu-id="f380f-186">**호스팅 서버**</span><span class="sxs-lookup"><span data-stu-id="f380f-186">**Hosting server**</span></span>|<span data-ttu-id="f380f-187">**기록해**</span><span class="sxs-lookup"><span data-stu-id="f380f-187">**Agents**</span></span>|<span data-ttu-id="f380f-188">**수신기**</span><span class="sxs-lookup"><span data-stu-id="f380f-188">**Listener**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="f380f-189">최소 기가 비트 전이중 네트워킹.</span><span class="sxs-lookup"><span data-stu-id="f380f-189">Minimum gigabit full duplex networking.</span></span>  <br/> |<span data-ttu-id="f380f-190">수신기와 통신 하는 아웃 바운드 TCP 포트 8443 (사용자 지정 가능 포트 번호).</span><span class="sxs-lookup"><span data-stu-id="f380f-190">Outbound TCP port 8443 (customizable port number) to communicate with the Listener.</span></span>  <br/> |<span data-ttu-id="f380f-191">수신기 포트는 모든 서버에서 동일 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f380f-191">The Listener port must be the same on all servers.</span></span>  <br/> |
|<span data-ttu-id="f380f-192">웹 사이트를 호스팅하기 위해 인바운드 TCP 포트 80 또는 443이 열려 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f380f-192">Inbound TCP port 80 or 443 open to host the website.</span></span>  <br/> |||
|<span data-ttu-id="f380f-193">에이전트와 통신 하는 데 사용할 인바운드 TCP 포트 8443 (사용자 지정 가능 포트 번호).</span><span class="sxs-lookup"><span data-stu-id="f380f-193">Inbound TCP port 8443 (customizable port number) for the agents to communicate with it.</span></span>  <br/> |||

<span data-ttu-id="f380f-194">설치 하는 동안 수신기 및 웹 사이트에 대 한 방화벽 포트가 자동으로 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="f380f-194">During installation, firewall ports for the Listener and the Website are automatically created.</span></span> <span data-ttu-id="f380f-195">에이전트의 경우 설치는 기본적으로 아웃 바운드 TCP 연결을 허용 한다고 간주 합니다.</span><span class="sxs-lookup"><span data-stu-id="f380f-195">For the Agents, the installation assumes that outbound TCP connections are allowed by default.</span></span>

### <a name="hardware-requirements"></a><span data-ttu-id="f380f-196">하드웨어 요구 사항</span><span class="sxs-lookup"><span data-stu-id="f380f-196">Hardware requirements</span></span>

<span data-ttu-id="f380f-197">단일 서버가 모든 서버 쪽 통계 관리자 구성 요소를 호스트 하는 온-프레미스 배포의 경우, RAM이 16gb이 고 CPU가 4 개 있는 서버는 평균적으로 초당 150 샘플에 대해 지원할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f380f-197">In an on-premises deployment, in which a single server hosts all of the server-side Statistics Manager components, a server with 16 GB of RAM and 4 CPU's should be able to support about 150 samples per second on average.</span></span> <span data-ttu-id="f380f-198">지원할 수 있는 카운터/에이전트 수를 확인 하려면 다음 계산을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f380f-198">To determine how many counters/agents you can support, use the following calculation:</span></span>

<span data-ttu-id="f380f-199">100 서버 \*80 카운터 \* 1 초 당 각 상담원/60 초 = ~ 133 샘플의 분당 샘플 수.</span><span class="sxs-lookup"><span data-stu-id="f380f-199">100 servers \*80 counters \* 1 sample per minute from each agent / 60 seconds = ~ 133 samples per second.</span></span>

## <a name="security-considerations"></a><span data-ttu-id="f380f-200">보안 고려 사항</span><span class="sxs-lookup"><span data-stu-id="f380f-200">Security considerations</span></span>
<span data-ttu-id="f380f-201"><a name="BKMK_Security"> </a></span><span class="sxs-lookup"><span data-stu-id="f380f-201"><a name="BKMK_Security"> </a></span></span>

<span data-ttu-id="f380f-202">서버 간의 모든 트래픽이 암호화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f380f-202">All traffic between servers is encrypted.</span></span>

- <span data-ttu-id="f380f-203">암호화 된 HTTPS 트래픽은 포트 8443 (기본적으로)를 통해 에이전트에서 수신기 서버로 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f380f-203">Encrypted HTTPS traffic will be sent over port 8443 (by default) from the Agent to the Listener server.</span></span>

- <span data-ttu-id="f380f-204">에이전트는 수신기 서버가 예상 받는 사람 인지 확인 하기 위해 서버의 SSL 지문을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="f380f-204">The Agent will verify the SSL thumbprint on the server to ensure the Listener server is the expected recipient.</span></span> <span data-ttu-id="f380f-205">에이전트는 체인 확인 대신 인증서 지문 확인을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f380f-205">Note that the Agent uses certificate thumbprint verification (instead of chain verification).</span></span> <span data-ttu-id="f380f-206">자체 서명 된 인증서를 사용할 수 있기 때문에 전체 인증서 유효성 검사를 수행 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f380f-206">It will not do full certificate validation because it is possible to use self-signed certificates.</span></span>

- <span data-ttu-id="f380f-207">에이전트를 만족 하는 경우 수신기가 인증 되 고 나면 에이전트는 수신기에 의해 확인 되는 암호를 제시 합니다.</span><span class="sxs-lookup"><span data-stu-id="f380f-207">After the Agent is satisfied the Listener is authentic, a password will be presented by the Agent which is then verified by the Listener.</span></span>

- <span data-ttu-id="f380f-208">에이전트는 수신기에 대 한 연결을 통해 성능 데이터를 전송 하기 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="f380f-208">The Agent begins transmitting performance data over the connection to the Listener.</span></span>

## <a name="for-more-information"></a><span data-ttu-id="f380f-209">자세한 내용은</span><span class="sxs-lookup"><span data-stu-id="f380f-209">For more information</span></span>
<span data-ttu-id="f380f-210"><a name="BKMK_Security"> </a></span><span class="sxs-lookup"><span data-stu-id="f380f-210"><a name="BKMK_Security"> </a></span></span>

<span data-ttu-id="f380f-211">자세한 내용은 다음을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f380f-211">For more information, see the following:</span></span>

- [<span data-ttu-id="f380f-212">비즈니스용 Skype 서버 통계 관리자 배포</span><span class="sxs-lookup"><span data-stu-id="f380f-212">Deploy Statistics Manager for Skype for Business Server</span></span>](deploy.md)

- [<span data-ttu-id="f380f-213">비즈니스용 Skype 서버 통계 관리자 업그레이드</span><span class="sxs-lookup"><span data-stu-id="f380f-213">Upgrade Statistics Manager for Skype for Business Server</span></span>](upgrade.md)

- [<span data-ttu-id="f380f-214">비즈니스용 Skype 서버 통계 관리자 문제 해결</span><span class="sxs-lookup"><span data-stu-id="f380f-214">Troubleshoot Statistics Manager for Skype for Business Server</span></span>](troubleshoot.md)
