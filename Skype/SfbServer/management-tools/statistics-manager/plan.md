---
title: 비즈니스용 Skype 서버 통계 관리자에 대한 계획
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: f0ec68e1-de01-4a92-b67d-703149b05caf
description: '요약: 이 항목을 읽고 비즈니스용 Skype 서버 통계 관리자에 대해 자세히 알아보습니다.'
ms.openlocfilehash: cdc536abcbd1bd98c4a3c7ce974247a716865582
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821828"
---
# <a name="plan-for-statistics-manager-for-skype-for-business-server"></a><span data-ttu-id="38e13-103">비즈니스용 Skype 서버 통계 관리자에 대한 계획</span><span class="sxs-lookup"><span data-stu-id="38e13-103">Plan for Statistics Manager for Skype for Business Server</span></span>

<span data-ttu-id="38e13-104">**요약:** 이 항목을 읽고 비즈니스용 Skype 서버 통계 관리자에 대해 자세히 알아보습니다.</span><span class="sxs-lookup"><span data-stu-id="38e13-104">**Summary:** Read this topic to learn about Statistics Manager for Skype for Business Server.</span></span>

 <span data-ttu-id="38e13-105">비즈니스용 Skype 서버 통계 관리자는 비즈니스용 Skype 서버 상태 및 성능 데이터를 실시간으로 볼 수 있는 강력한 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="38e13-105">Statistics Manager for Skype for Business Server is a powerful tool that allows you to view Skype for Business Server health and performance data in real time.</span></span> <span data-ttu-id="38e13-106">몇 초마다 수백 대의 서버로 성능 데이터를 폴링하고 통계 관리자 웹 사이트에서 결과를 즉시 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38e13-106">You can poll performance data across hundreds of servers every few seconds, and view the results instantly on the Statistics Manager Website.</span></span>

<span data-ttu-id="38e13-107">Statistics Manager를 사용하여 지속적인 성능 문제를 식별하고, 환경의 계획된 변경 결과를 보고, 정전 해결을 추적하는 등 다양한 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38e13-107">You can use Statistics Manager to identify ongoing performance issues, view the results of a planned change to your environment, track resolution of outages, and much more.</span></span> <span data-ttu-id="38e13-108">통계 관리자는 KHI(Key Health Indicator) 임계값으로 구성됩니다. 통계 관리자는 배포의 고유한 요구 사항에 맞게 사용자 지정될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38e13-108">Out of the box, Statistics Manager is configured with Key Health Indicator (KHI) thresholds, and can be customized to suit your deployment's unique needs.</span></span>

<span data-ttu-id="38e13-109">단일 서버가 모든 서버 쪽 Statistics Manager 구성 요소를 호스팅하는 모든 프레미스 배포에서 Statistics Manager를 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38e13-109">You can deploy Statistics Manager in an on-premises deployment in which a single server hosts all of the server-side Statistics Manager components.</span></span> <span data-ttu-id="38e13-110">통계 관리자 배포에 대한 자세한 내용은 비즈니스용 Skype 서버 통계 관리자 [배포를 참조하세요.](deploy.md)</span><span class="sxs-lookup"><span data-stu-id="38e13-110">For more information about deploying Statistics Manager, see [Deploy Statistics Manager for Skype for Business Server](deploy.md).</span></span> <span data-ttu-id="38e13-111">통계 관리자의 기존 배포가 있지만 아직 릴리스 2.0으로 업그레이드하지 않은 경우 비즈니스용 [Skype](upgrade.md)서버용 릴리스 [2.0](plan.md#BKMK_WhatsNew) 및 업그레이드 통계 관리자의 새로운 정보를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="38e13-111">If you already have an existing deployment of Statistics Manager, but you have not yet upgraded to Release 2.0, see [What's new in Release 2.0](plan.md#BKMK_WhatsNew) and [Upgrade Statistics Manager for Skype for Business Server](upgrade.md).</span></span>

<span data-ttu-id="38e13-112">이 항목에는 다음 섹션이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38e13-112">This topic contains the following sections:</span></span>

- [<span data-ttu-id="38e13-113">특징 및 기능</span><span class="sxs-lookup"><span data-stu-id="38e13-113">Features and capabilities</span></span>](plan.md#BKMK_Features)

- [<span data-ttu-id="38e13-114">릴리스 2.0의 새로운</span><span class="sxs-lookup"><span data-stu-id="38e13-114">What's new in Release 2.0</span></span>](plan.md#BKMK_WhatsNew)

- [<span data-ttu-id="38e13-115">구성 요소</span><span class="sxs-lookup"><span data-stu-id="38e13-115">Components</span></span>](plan.md#BKMK_Components)

- [<span data-ttu-id="38e13-116">On-premises deployment</span><span class="sxs-lookup"><span data-stu-id="38e13-116">On-premises deployment</span></span>](plan.md#BKMK_DeploymentOptions)

- [<span data-ttu-id="38e13-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="38e13-117">Requirements</span></span>](plan.md#BKMK_Requirements)

- [<span data-ttu-id="38e13-118">보안 고려 사항</span><span class="sxs-lookup"><span data-stu-id="38e13-118">Security considerations</span></span>](plan.md#BKMK_Security)

## <a name="features-and-capabilities"></a><span data-ttu-id="38e13-119">특징 및 기능</span><span class="sxs-lookup"><span data-stu-id="38e13-119">Features and capabilities</span></span>
<span data-ttu-id="38e13-120"><a name="BKMK_Features"> </a></span><span class="sxs-lookup"><span data-stu-id="38e13-120"><a name="BKMK_Features"> </a></span></span>

<span data-ttu-id="38e13-121">통계 관리자를 사용하여 다음을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38e13-121">Statistics Manager allows you to:</span></span>

- <span data-ttu-id="38e13-122">실시간으로 모든 서버의 원시 데이터를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38e13-122">View raw data for all servers in real time.</span></span> <span data-ttu-id="38e13-123">데이터가 매우 높은 속도로 샘플링된 후 1초 미만으로 웹 사이트로 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="38e13-123">(Data is sampled at a very high rate and sent to the website in less than one second.)</span></span>

- <span data-ttu-id="38e13-124">특정 역할에 대해 집계된 데이터를 본다. 예를 들어 프런트 엔드 서버, 중재 서버, 에지 서버 등입니다.</span><span class="sxs-lookup"><span data-stu-id="38e13-124">View data that is aggregated for a specific role; for example, Front End Server, Mediation Server, Edge Server, and so on.</span></span>

- <span data-ttu-id="38e13-125">드릴다운하여 특정 사이트, 사이트 내의 특정 풀 및 풀 내의 특정 서버에 대한 데이터를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38e13-125">Drill down to view data for specific sites, specific pools within the site, and then specific servers within the pool.</span></span>

- <span data-ttu-id="38e13-126">기본적으로 선택한 카운터가 표시 있도록 사용자 지정 차트를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38e13-126">Create custom charts so that chosen counters are shown by default.</span></span>

- <span data-ttu-id="38e13-127">x 축과 y 축을 모두 확대/축소하고 이동하거나 x 축에서만 확대/축소합니다.</span><span class="sxs-lookup"><span data-stu-id="38e13-127">Zoom and pan on both the x- and y- axes or on the x-axis only.</span></span>

- <span data-ttu-id="38e13-128">날짜 범위 또는 포인트를 사용하여 데이터를 필터링합니다.</span><span class="sxs-lookup"><span data-stu-id="38e13-128">Use date ranges or points in time to filter data.</span></span>

- <span data-ttu-id="38e13-129">KHIS(핵심 상태 표시기)를 기반으로 서버 성능을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38e13-129">View server performance based on established key health indicators (KHIs).</span></span> <span data-ttu-id="38e13-130">KHIS는 정의된 정상 범위의 성능 카운터 모음을 나타내며,</span><span class="sxs-lookup"><span data-stu-id="38e13-130">KHIs represent a collection of performance counters with a defined healthy range.</span></span>

- <span data-ttu-id="38e13-131">각 카운터에 대한 자세한 메트릭을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="38e13-131">View detailed metrics for each counter.</span></span>

- <span data-ttu-id="38e13-132">여러 인구 또는 서버의 데이터를 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="38e13-132">Compare data across multiple populations or servers.</span></span>

- <span data-ttu-id="38e13-133">대시보드 서비스에 현재 데이터를 보고하지 않는 에이전트를 식별할 수 있는 카운터 보고서를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38e13-133">View latent counter reports to identify agents that are not reporting current data to the dashboard service.</span></span>

- <span data-ttu-id="38e13-134">차트 데이터의 특정 인스턴스를 파일에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="38e13-134">Save a particular instance of chart data to a file.</span></span>

- <span data-ttu-id="38e13-135">업데이트를 포함하여 실시간으로 KHIS를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="38e13-135">View KHIs in real time, including updates.</span></span> <span data-ttu-id="38e13-136">사용 기록 보기를 사용하도록 설정하면 새 오류만 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="38e13-136">If the history view is enabled, only new failures are shown.</span></span>

  - <span data-ttu-id="38e13-137">한 번에 모든 KHIS 보기</span><span class="sxs-lookup"><span data-stu-id="38e13-137">View all KHIs at one time</span></span>

  - <span data-ttu-id="38e13-138">서버당 KHIS 보기(가로 보기)</span><span class="sxs-lookup"><span data-stu-id="38e13-138">View KHIs by server (Landscape view)</span></span>

  - <span data-ttu-id="38e13-139">KHI 정의 보기</span><span class="sxs-lookup"><span data-stu-id="38e13-139">View KHI definitions</span></span>

## <a name="whats-new-in-release-20"></a><span data-ttu-id="38e13-140">릴리스 2.0의 새로운</span><span class="sxs-lookup"><span data-stu-id="38e13-140">What's new in Release 2.0</span></span>
<span data-ttu-id="38e13-141"><a name="BKMK_WhatsNew"> </a></span><span class="sxs-lookup"><span data-stu-id="38e13-141"><a name="BKMK_WhatsNew"> </a></span></span>

<span data-ttu-id="38e13-142">다음은 릴리스 2.0의 새로운 버전에 대해 설명하는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="38e13-142">The following describes what's new in Release 2.0.</span></span> <span data-ttu-id="38e13-143">통계 관리자의 기존 배포가 있으며 아직 업그레이드되지 않은 경우 비즈니스용 Skype 서버의 업그레이드 통계 관리자를 [참조하세요.](upgrade.md)</span><span class="sxs-lookup"><span data-stu-id="38e13-143">If you have an existing deployment of Statistics Manager and you've not yet upgraded, see [Upgrade Statistics Manager for Skype for Business Server](upgrade.md).</span></span>

- <span data-ttu-id="38e13-144">에지 미디어, 패브릭 상태, 풀 장애 조치(Failover) 및 등록 시나리오에 대한 시나리오 보기가 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="38e13-144">Scenario views have been added for Edge Media, Fabric Health, Pool Failover and Registration scenarios.</span></span>

- <span data-ttu-id="38e13-145">여러 새 카운터가 SQL, 비즈니스용 Skype 사용 카운터 등 여러 가지가 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="38e13-145">Many new counters have been added for SQL servers, more Skype for Business usage counters, and so on.</span></span>

- <span data-ttu-id="38e13-146">통계 관리자 에이전트에 대한 감시자 노드 통합 - 에이전트가 감시자 노드에 설치된 경우 가상 트랜잭션 통계를 카운터로 통계 관리자에 다시 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="38e13-146">Watcher node integration for the Statistics Manager Agent - if the Agent is installed on a watcher node, it will report synthetic transaction statistics as counters back to Statistics Manager.</span></span>

- <span data-ttu-id="38e13-147">다양한 안정성 및 성능 향상.</span><span class="sxs-lookup"><span data-stu-id="38e13-147">Numerous reliability and performance improvements.</span></span>

<span data-ttu-id="38e13-148">실행 중인 Statistics Manager 웹 사이트의 버전을 확인하기 위해 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="38e13-148">To verify the version of the Statistics Manager Website you are running:</span></span>

- <span data-ttu-id="38e13-149">파일 탐색기에서 열기(기본 디렉터리) C:\Program Files\Skype for Business Server StatsMan WebSite\bin</span><span class="sxs-lookup"><span data-stu-id="38e13-149">In File Explorer, open (default directory) C:\Program Files\Skype for Business Server StatsMan WebSite\bin</span></span>

- <span data-ttu-id="38e13-150">마우스 오른쪽 단추를 StatsManHubWebSite.dll 속성 보기</span><span class="sxs-lookup"><span data-stu-id="38e13-150">Right click on StatsManHubWebSite.dll and view its properties</span></span>

- <span data-ttu-id="38e13-151">제품 버전이 설명 세부 정보에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="38e13-151">The product version will be shown in the Description details.</span></span>

## <a name="components"></a><span data-ttu-id="38e13-152">구성 요소</span><span class="sxs-lookup"><span data-stu-id="38e13-152">Components</span></span>
<span data-ttu-id="38e13-153"><a name="BKMK_Components"> </a></span><span class="sxs-lookup"><span data-stu-id="38e13-153"><a name="BKMK_Components"> </a></span></span>

<span data-ttu-id="38e13-154">통계 관리자는 다음 구성 요소로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="38e13-154">Statistics Manager consists of the following components:</span></span>

- <span data-ttu-id="38e13-155">**에이전트.**</span><span class="sxs-lookup"><span data-stu-id="38e13-155">**Agent.**</span></span> <span data-ttu-id="38e13-156">모니터링되는 각 서버에서 실행되는 경량 에이전트입니다.</span><span class="sxs-lookup"><span data-stu-id="38e13-156">A lightweight agent that runs on each monitored server.</span></span> <span data-ttu-id="38e13-157">에이전트는 로컬 집계를 사용하여 구성 가능한 높은 속도의 성능 카운터 폴링을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="38e13-157">The Agent allows configurable high rate polling of performance counters with local aggregation.</span></span>

- <span data-ttu-id="38e13-158">**수신기.**</span><span class="sxs-lookup"><span data-stu-id="38e13-158">**Listener.**</span></span> <span data-ttu-id="38e13-159">모든 에이전트에서 데이터를 받고 모집단에서 데이터를 집계하는 서버 쪽 API입니다.</span><span class="sxs-lookup"><span data-stu-id="38e13-159">The server side API that receives data from all Agents, and aggregates data across populations.</span></span>

- <span data-ttu-id="38e13-160">**허브.**</span><span class="sxs-lookup"><span data-stu-id="38e13-160">**Hub.**</span></span> <span data-ttu-id="38e13-161">시스템의 클라이언트 API 역할을 하며, 웹 서버에서 실행되고, 웹 사이트를 통해 연결된 클라이언트에 대한 실시간 데이터 업데이트를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="38e13-161">Serves as the client API for the system, runs on the web server(s), and provides real-time data updates to clients connected via the website.</span></span> <span data-ttu-id="38e13-162">(허브는 웹 사이트 msi의 일부로 자동으로 설치됩니다.)</span><span class="sxs-lookup"><span data-stu-id="38e13-162">(The Hub is automatically installed as part of the Website msi.)</span></span>

- <span data-ttu-id="38e13-163">**웹 사이트.**</span><span class="sxs-lookup"><span data-stu-id="38e13-163">**Website.**</span></span> <span data-ttu-id="38e13-164">시스템에서 사용할 수 있는 모든 기능을 함께 끌어오는 사용자 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="38e13-164">A user interface that pulls together all the features available in the system.</span></span>

<span data-ttu-id="38e13-165">또한 통계 관리자에는 메모리 내 캐싱을 위한 오픈 소스 데이터 구조 서버인 **Redis가** 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="38e13-165">In addition, Statistics Manager requires **Redis**, an open-sourced data structure server for in-memory caching.</span></span> <span data-ttu-id="38e13-166">Redis 다운로드에 대한 자세한 내용은 통계 관리자 [배포를 참조하십시오.](deploy.md#BKMK_Deploy)</span><span class="sxs-lookup"><span data-stu-id="38e13-166">For more information about downloading Redis, see [Deploy Statistics Manager](deploy.md#BKMK_Deploy) .</span></span>

## <a name="on-premises-deployment"></a><span data-ttu-id="38e13-167">On-premises deployment</span><span class="sxs-lookup"><span data-stu-id="38e13-167">On-premises deployment</span></span>
<span data-ttu-id="38e13-168"><a name="BKMK_DeploymentOptions"> </a></span><span class="sxs-lookup"><span data-stu-id="38e13-168"><a name="BKMK_DeploymentOptions"> </a></span></span>

<span data-ttu-id="38e13-169">On-premises 배포에서는 단일 서버가 모든 서버 쪽 Statistics Manager 구성 요소를 호스팅합니다.</span><span class="sxs-lookup"><span data-stu-id="38e13-169">In an on-premises deployment, a single server hosts all of the server-side Statistics Manager components.</span></span>

<span data-ttu-id="38e13-170">다음 다이어그램은 Statistics Manager 웹 사이트, 허브, 수신기 및 Redis 캐싱 시스템이 단일 시스템에서 호스팅되는,프레미스 배포를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="38e13-170">The following diagram shows an on-premises deployment, in which the Statistics Manager Website, Hub, Listener, and Redis caching system are hosted on a single machine.</span></span> <span data-ttu-id="38e13-171">통계 관리자는 3개의 비즈니스용 Skype 서버를 모니터링하고 있습니다. 각 서버는 수신기로 데이터를 전송하는 단일 에이전트가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38e13-171">Statistics Manager is monitoring three Skype for Business servers, each of which have a single Agent transmitting data to the Listener.</span></span> <span data-ttu-id="38e13-172">사용자는 단일 웹 사이트에 연결하여 Statistics Manager로 집계된 모든 데이터를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38e13-172">Users connect to a single Website to view all data aggregated by Statistics Manager:</span></span>

![Stats Manager On-premises 배포](../../media/c7c9d0b5-a70b-4d8c-aec4-0128a29b90b6.png)

## <a name="requirements"></a><span data-ttu-id="38e13-174">요구 사항</span><span class="sxs-lookup"><span data-stu-id="38e13-174">Requirements</span></span>
<span data-ttu-id="38e13-175"><a name="BKMK_Requirements"> </a></span><span class="sxs-lookup"><span data-stu-id="38e13-175"><a name="BKMK_Requirements"> </a></span></span>

<span data-ttu-id="38e13-176">Statistics Manager를 배포하기 전에 다음 소프트웨어, 네트워킹 및 하드웨어 요구 사항을 고려해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="38e13-176">You will need to consider the following software, networking, and hardware requirements before you deploy Statistics Manager.</span></span>

### <a name="software-requirements"></a><span data-ttu-id="38e13-177">소프트웨어 요구 사항</span><span class="sxs-lookup"><span data-stu-id="38e13-177">Software requirements</span></span>

- <span data-ttu-id="38e13-178">Windows Server 2016 및 2019</span><span class="sxs-lookup"><span data-stu-id="38e13-178">Windows Server 2016 and 2019</span></span>

- <span data-ttu-id="38e13-179">IIS(자동으로 설치)</span><span class="sxs-lookup"><span data-stu-id="38e13-179">IIS (automatically installed)</span></span>

- <span data-ttu-id="38e13-180">Redis</span><span class="sxs-lookup"><span data-stu-id="38e13-180">Redis</span></span>

- <span data-ttu-id="38e13-181">Statistics Manager 서비스(자동으로 설치)</span><span class="sxs-lookup"><span data-stu-id="38e13-181">Statistics Manager services (automatically installed)</span></span>

- <span data-ttu-id="38e13-182">PSExec - 원격 에이전트 배포를 위해 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="38e13-182">PSExec - Required to do remote agent deployment</span></span>

- <span data-ttu-id="38e13-183">.NET 4.5(2012 R2에 포함) - 에이전트 및 서버 쪽 구성 요소에 필요</span><span class="sxs-lookup"><span data-stu-id="38e13-183">.NET 4.5 (included with 2012 R2) - Required for agents and server-side components</span></span>
- <span data-ttu-id="38e13-184">비즈니스용 Skype 서버, Real-Time [통계 관리자(64비트) 다운로드](https://www.microsoft.com/en-in/download/details.aspx?id=57518)</span><span class="sxs-lookup"><span data-stu-id="38e13-184">Download the [Skype for Business Server, Real-Time Statistics Manager (64-bit)](https://www.microsoft.com/en-in/download/details.aspx?id=57518)</span></span>

### <a name="networking-requirements"></a><span data-ttu-id="38e13-185">네트워킹 요구 사항</span><span class="sxs-lookup"><span data-stu-id="38e13-185">Networking requirements</span></span>


|<span data-ttu-id="38e13-186">**호스팅 서버**</span><span class="sxs-lookup"><span data-stu-id="38e13-186">**Hosting server**</span></span>|<span data-ttu-id="38e13-187">**Agents**</span><span class="sxs-lookup"><span data-stu-id="38e13-187">**Agents**</span></span>|<span data-ttu-id="38e13-188">**수신기**</span><span class="sxs-lookup"><span data-stu-id="38e13-188">**Listener**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="38e13-189">최소 기가비트 전체 이면 네트워킹.</span><span class="sxs-lookup"><span data-stu-id="38e13-189">Minimum gigabit full duplex networking.</span></span>  <br/> |<span data-ttu-id="38e13-190">수신기와 통신할 아웃바운드 TCP 포트 8443(사용자 지정 가능한 포트 번호)입니다.</span><span class="sxs-lookup"><span data-stu-id="38e13-190">Outbound TCP port 8443 (customizable port number) to communicate with the Listener.</span></span>  <br/> |<span data-ttu-id="38e13-191">수신기 포트는 모든 서버에서 동일해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="38e13-191">The Listener port must be the same on all servers.</span></span>  <br/> |
|<span data-ttu-id="38e13-192">인바운드 TCP 포트 80 또는 443이 열려 웹 사이트를 호스트합니다.</span><span class="sxs-lookup"><span data-stu-id="38e13-192">Inbound TCP port 80 or 443 open to host the website.</span></span>  <br/> |||
|<span data-ttu-id="38e13-193">에이전트가 통신할 인바운드 TCP 포트 8443(사용자 지정 가능한 포트 번호)입니다.</span><span class="sxs-lookup"><span data-stu-id="38e13-193">Inbound TCP port 8443 (customizable port number) for the agents to communicate with it.</span></span>  <br/> |||

<span data-ttu-id="38e13-194">설치하는 동안 수신기 및 웹 사이트에 대한 방화벽 포트가 자동으로 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="38e13-194">During installation, firewall ports for the Listener and the Website are automatically created.</span></span> <span data-ttu-id="38e13-195">에이전트의 경우 설치에서는 기본적으로 아웃바운드 TCP 연결이 허용된다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="38e13-195">For the Agents, the installation assumes that outbound TCP connections are allowed by default.</span></span>

### <a name="hardware-requirements"></a><span data-ttu-id="38e13-196">하드웨어 요구 사항</span><span class="sxs-lookup"><span data-stu-id="38e13-196">Hardware requirements</span></span>

<span data-ttu-id="38e13-197">단일 서버가 모든 서버 쪽 Statistics Manager 구성 요소를 호스팅하는 프레미스 배포에서는 RAM이 16GB, CPU가 4개인 서버는 평균적으로 초당 약 150개의 샘플을 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38e13-197">In an on-premises deployment, in which a single server hosts all of the server-side Statistics Manager components, a server with 16 GB of RAM and 4 CPU's should be able to support about 150 samples per second on average.</span></span> <span data-ttu-id="38e13-198">지원할 수 있는 카운터/에이전트 수를 결정하기 위해 다음 계산을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="38e13-198">To determine how many counters/agents you can support, use the following calculation:</span></span>

<span data-ttu-id="38e13-199">100개의 서버 카운터 80개(각 에이전트의 분당 샘플 \* \* 1개/ 60초 = 초당 샘플 133개)</span><span class="sxs-lookup"><span data-stu-id="38e13-199">100 servers \*80 counters \* 1 sample per minute from each agent / 60 seconds = ~ 133 samples per second.</span></span>

## <a name="security-considerations"></a><span data-ttu-id="38e13-200">보안 고려 사항</span><span class="sxs-lookup"><span data-stu-id="38e13-200">Security considerations</span></span>
<span data-ttu-id="38e13-201"><a name="BKMK_Security"> </a></span><span class="sxs-lookup"><span data-stu-id="38e13-201"><a name="BKMK_Security"> </a></span></span>

<span data-ttu-id="38e13-202">서버 간의 모든 트래픽이 암호화됩니다.</span><span class="sxs-lookup"><span data-stu-id="38e13-202">All traffic between servers is encrypted.</span></span>

- <span data-ttu-id="38e13-203">암호화된 HTTPS 트래픽은 기본적으로 에이전트에서 수신기 서버로 포트 8443을 통해 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="38e13-203">Encrypted HTTPS traffic will be sent over port 8443 (by default) from the Agent to the Listener server.</span></span>

- <span data-ttu-id="38e13-204">에이전트는 서버의 SSL 지문을 확인하여 수신기 서버가 예상되는 받는 사람임이 확인됩니다.</span><span class="sxs-lookup"><span data-stu-id="38e13-204">The Agent will verify the SSL thumbprint on the server to ensure the Listener server is the expected recipient.</span></span> <span data-ttu-id="38e13-205">에이전트는 체인 확인 대신 인증서 지문 확인을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="38e13-205">Note that the Agent uses certificate thumbprint verification (instead of chain verification).</span></span> <span data-ttu-id="38e13-206">자체 서명된 인증서를 사용할 수 있기 때문에 전체 인증서 유효성 검사를 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="38e13-206">It will not do full certificate validation because it is possible to use self-signed certificates.</span></span>

- <span data-ttu-id="38e13-207">에이전트가 수신기 인증에 만족하면 에이전트가 암호를 제공하면 수신기에서 암호를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38e13-207">After the Agent is satisfied the Listener is authentic, a password will be presented by the Agent which is then verified by the Listener.</span></span>

- <span data-ttu-id="38e13-208">에이전트가 연결을 통해 수신기로 성능 데이터 전송을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="38e13-208">The Agent begins transmitting performance data over the connection to the Listener.</span></span>

## <a name="for-more-information"></a><span data-ttu-id="38e13-209">자세한 내용</span><span class="sxs-lookup"><span data-stu-id="38e13-209">For more information</span></span>
<span data-ttu-id="38e13-210"><a name="BKMK_Security"> </a></span><span class="sxs-lookup"><span data-stu-id="38e13-210"><a name="BKMK_Security"> </a></span></span>

<span data-ttu-id="38e13-211">자세한 내용은 다음 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="38e13-211">For more information, see the following:</span></span>

- [<span data-ttu-id="38e13-212">비즈니스용 Skype 서버 통계 관리자 배포</span><span class="sxs-lookup"><span data-stu-id="38e13-212">Deploy Statistics Manager for Skype for Business Server</span></span>](deploy.md)

- [<span data-ttu-id="38e13-213">비즈니스용 Skype 서버 통계 관리자 업그레이드</span><span class="sxs-lookup"><span data-stu-id="38e13-213">Upgrade Statistics Manager for Skype for Business Server</span></span>](upgrade.md)

- [<span data-ttu-id="38e13-214">비즈니스용 Skype 서버 통계 관리자 문제 해결</span><span class="sxs-lookup"><span data-stu-id="38e13-214">Troubleshoot Statistics Manager for Skype for Business Server</span></span>](troubleshoot.md)
