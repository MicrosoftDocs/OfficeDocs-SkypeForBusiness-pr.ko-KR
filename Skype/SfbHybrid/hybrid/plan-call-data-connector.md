---
title: 통화 데이터 커넥터 계획 | 통화 품질 대시보드 하이브리드 분석 모니터링
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: 비즈니스용 Skype Online 원격 분석 도구를 사용 하 여 하이브리드 시나리오에서 온-프레미스 구현을 모니터링 하는 방법에 대해 간략하게 설명 합니다.
ms.openlocfilehash: dc129ed99e1ed69e3faf5d2a7b6923f818c482eb
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36185514"
---
# <a name="plan-call-data-connector"></a><span data-ttu-id="aec5d-103">통화 데이터 커넥터 계획</span><span class="sxs-lookup"><span data-stu-id="aec5d-103">Plan Call Data Connector</span></span>

## <a name="overview"></a><span data-ttu-id="aec5d-104">개요</span><span class="sxs-lookup"><span data-stu-id="aec5d-104">Overview</span></span>

<span data-ttu-id="aec5d-105">이 항목에서는 비즈니스용 Skype Server Call Data Connector를 구현 하기 위한 이점, 계획 고려 사항, 요구 사항에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="aec5d-105">This topic describes benefits, planning considerations, and requirements for implementing Skype for Business Server Call Data Connector.</span></span> <span data-ttu-id="aec5d-106">통화 데이터 커넥터를 구성 하는 방법에 대 한 자세한 내용은 [Call Data Connector 구성을](configure-call-data-connector.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="aec5d-106">For more information on configuring Call Data Connector, see [Configure Call Data Connector](configure-call-data-connector.md).</span></span>

> [!NOTE]
> <span data-ttu-id="aec5d-107">공용 preview 릴리스에서는 통화 분석 대시보드만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aec5d-107">At public preview release, only Call Analytics dashboard is available.</span></span>

<span data-ttu-id="aec5d-108">호출 데이터 커넥터는 더 이상 다른 온-프레미스 및 온라인 도구 집합을 사용 하 여 모든 사용자 통화 품질을 모니터링할 필요가 없기 때문에 하이브리드 환경에서 호출 모니터링을 간소화 합니다.</span><span class="sxs-lookup"><span data-stu-id="aec5d-108">Call Data Connector greatly simplifies call monitoring in a hybrid environment because you no longer need to use different sets of on-premises and online tools to monitor all of your users call quality.</span></span> <span data-ttu-id="aec5d-109">사용자가 구내 또는 온라인으로 설정 되어 있는지 여부에 관계 없이 전체 조직의 통화 품질을 온라인으로 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aec5d-109">Whether your users are homed on premises or online, you can choose to view call quality for your entire organization online.</span></span>

<span data-ttu-id="aec5d-110">통화 데이터 커넥터를 사용 하 여 단일 도구 집합을 사용 하 여 다음 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aec5d-110">With Call Data Connector, you can perform the following tasks by using a single toolset:</span></span>

- <span data-ttu-id="aec5d-111">Microsoft 팀, 비즈니스용 Skype Online, 비즈니스용 Skype 서버에서 사용자 환경을 모니터링 하세요.</span><span class="sxs-lookup"><span data-stu-id="aec5d-111">Monitor your user experience across Microsoft Teams, Skype for Business Online, and Skype for Business Server.</span></span>

- <span data-ttu-id="aec5d-112">네트워크에서 문제를 보고 해결 합니다.</span><span class="sxs-lookup"><span data-stu-id="aec5d-112">View and troubleshoot problems across your network.</span></span>

- <span data-ttu-id="aec5d-113">헬프 데스크 직원의 책임 영역을 보고 문제를 해결할 수 있도록 통화 분석에 대 한 헬프데스크 및 관리자 역할을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="aec5d-113">Assign helpdesk and administrator roles for Call Analytics, so that you can empower helpdesk workers to view and troubleshoot their areas of responsibility.</span></span>

<span data-ttu-id="aec5d-114">통화 데이터 커넥터를 사용 하는 경우 비즈니스용 Skype Server는 다음 다이어그램에 표시 된 것 처럼 비즈니스용 Skype Online Call 분석 (CA) 및 CQD (비즈니스 지원) 도구를 활용할 수 있도록 클라우드 서비스에 대 한 통화 데이터를 푸시합니다.</span><span class="sxs-lookup"><span data-stu-id="aec5d-114">With Call Data Connector, the Skype for Business Server pushes call data to the cloud service so that you can leverage the Skype for Business Online Call Analytics (CA) and Call Quality Dashboard (CQD) tools, as shown in the following diagram:</span></span>

![SfB 구름 보이스 메일](../../sfbserver2019/media/call-data-connector-plan-1.png)

<span data-ttu-id="aec5d-116">서버는 체감 품질 (환경 품질) 및 CDR (통화 정보 기록) 데이터를 온라인 서비스에 푸시합니다.</span><span class="sxs-lookup"><span data-stu-id="aec5d-116">The server pushes both Quality of Experience (QoE) and Call Detail Recording (CDR) data to the online service.</span></span>

<span data-ttu-id="aec5d-117">통화 분석 및 CQD 도구를 사용 하 여 통화 품질을 모니터링 하 고 다음과 같이 Microsoft 팀 및 비즈니스용 Skype 서비스의 연결 문제를 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aec5d-117">The Call Analytics and CQD tools enable you to monitor the quality of calls and troubleshoot connection problems with Microsoft Teams and Skype for Business services as follows:</span></span>

- <span data-ttu-id="aec5d-118">통화 분석은 특정 통화에 대 한 품질 문제를 중점적으로 다룹니다.</span><span class="sxs-lookup"><span data-stu-id="aec5d-118">Call Analytics focuses on quality problems with specific calls.</span></span> <span data-ttu-id="aec5d-119">비즈니스용 Skype 계정에서 각 사용자의 통화 및 모임에 대 한 자세한 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="aec5d-119">It shows detailed information about calls and meetings for each user in a Skype for Business account.</span></span>  <span data-ttu-id="aec5d-120">통화 분석을 사용 하면 비즈니스용 Skype 관리 센터의 나머지에 대 한 액세스 권한 없이 통화를 모니터링할 수 있는 헬프데스크 운영자에 게 권한을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aec5d-120">With Call Analytics, you can assign permissions to a helpdesk operator who can then monitor calls without having access to the rest of the Skype for Business Admin center.</span></span>

- <span data-ttu-id="aec5d-121">통화 품질 대시보드는 조직의 네트워크 성능 및 문제에 중점을 둘 것입니다.</span><span class="sxs-lookup"><span data-stu-id="aec5d-121">Call Quality Dashboard focuses on network performance and issues across an organization.</span></span> <span data-ttu-id="aec5d-122">비즈니스용 Skype 관리자 및 네트워크 엔지니어는이 도구를 사용 하 여 네트워크 성능 문제를 해결 하 고 최적화 합니다.</span><span class="sxs-lookup"><span data-stu-id="aec5d-122">Skype for Business administrators and network engineers use this tool to troubleshoot and optimize network performance.</span></span>

<span data-ttu-id="aec5d-123">자세한 내용은 [통화 분석 및 통화 품질 대시보드](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/difference-between-call-analytics-and-call-quality-dashboard)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="aec5d-123">For more information, see [Call Analytics and Call Quality Dashboard](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/difference-between-call-analytics-and-call-quality-dashboard).</span></span>

<span data-ttu-id="aec5d-124">물론 일부 통화 품질 데이터는 구내에 유지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aec5d-124">Of course, you might want to keep some call quality data on premises.</span></span> <span data-ttu-id="aec5d-125">예를 들어 사용자 지정 보고서 및 워크플로와 함께 타사 솔루션을 사용 하는 경우이 문제가 나타날 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aec5d-125">This might be the case, for example, if you are using a third-party solution with customized reports and workflows.</span></span>  <span data-ttu-id="aec5d-126">통화 데이터 커넥터를 사용 하면 다음 다이어그램과 같이 온-프레미스 서버에 데이터 복사본을 유지 하면서 온라인 서비스에 대 한 데이터 전송도 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aec5d-126">Call Data Connector allows you to configure sending data to the online service while also keeping a copy of the data on your on-premises server, as shown in the following diagram:</span></span>

![SfB 구름 보이스 메일](../../sfbserver2019/media/call-data-connector-plan-2.png)

## <a name="requirements"></a><span data-ttu-id="aec5d-128">요구 사항</span><span class="sxs-lookup"><span data-stu-id="aec5d-128">Requirements</span></span>

<span data-ttu-id="aec5d-129">다음 요구 사항은 지원 되는 토폴로지에서 이미 비즈니스용 Skype 서버를 배포 하는 것으로 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="aec5d-129">The following requirements assume that you already have Skype for Business Server deployed in a supported topology.</span></span>  <span data-ttu-id="aec5d-130">비즈니스용 Skype 서버 및 지원 되는 토폴로지에 배포 하는 방법에 대 한 자세한 내용은 [토폴로지 기본 사항을](https://docs.microsoft.com/SkypeForBusiness/plan-your-deployment/topology-basics/topology-basics)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="aec5d-130">For more information about deploying Skype for Business Server and supported topologies, see [Topology Basics](https://docs.microsoft.com/SkypeForBusiness/plan-your-deployment/topology-basics/topology-basics).</span></span> <span data-ttu-id="aec5d-131">통화 데이터 커넥터를 구성 하려면 다음을 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aec5d-131">To configure Call Data Connector, you must:</span></span>

- <span data-ttu-id="aec5d-132">하이브리드 연결을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="aec5d-132">Enable Hybrid connectivity.</span></span> <span data-ttu-id="aec5d-133">비즈니스용 Skype 서버를 이미 배포 하 고 통화 데이터 커넥터를 사용 하도록 설정 하려면 온-프레미스 및 온라인 환경 간에 하이브리드 연결이 설정 되어 있는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aec5d-133">If you already have Skype for Business Server deployed and you want to enable Call Data Connector, you must ensure that you have hybrid connectivity set up between your on-premises and online environments.</span></span> <span data-ttu-id="aec5d-134">이를 도메인 분할 구성이 라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="aec5d-134">This is sometimes called a split domain configuration.</span></span>

   <span data-ttu-id="aec5d-135">자세한 내용은 비즈니스용 [Skype 서버 및 office 365 하이브리드 연결 계획](plan-hybrid-connectivity.md) 을 참조 하 고 비즈니스용 [Skype 서버와 office 365의 하이브리드 연결을 구성](configure-hybrid-connectivity.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="aec5d-135">For more information, see [Plan hybrid connectivity between Skype for Business Server and Office 365](plan-hybrid-connectivity.md) and [Configure hybrid connectivity between Skype for Business Server and Office 365](configure-hybrid-connectivity.md).</span></span>

- <span data-ttu-id="aec5d-136">Office 365 테 넌 트에 인증 하 고 다음 역할을 사용 하도록 설정 했는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="aec5d-136">Authenticate to your Office 365 tenant and ensure that you have the following roles enabled:</span></span>

  - <span data-ttu-id="aec5d-137">비즈니스용 Skype 서버 관리자</span><span class="sxs-lookup"><span data-stu-id="aec5d-137">Skype for Business Server Administrator</span></span>
  - <span data-ttu-id="aec5d-138">Office 365 전역 관리자</span><span class="sxs-lookup"><span data-stu-id="aec5d-138">Office 365 Global Administrator</span></span>

- <span data-ttu-id="aec5d-139">아직 수행 하지 않은 경우에는 [Microsoft 팀과 비즈니스용 Skype Online에 대 한 통화 품질 대시보드 켜기 및 사용](/microsoftteams/turning-on-and-using-call-quality-dashboard)에 설명 된 대로 통화 품질 대시보드를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="aec5d-139">If you have not already done so, turn on Call Quality Dashboard as described in [Turning on and using Call Quality Dashboard for Microsoft Teams and Skype for Business Online](/microsoftteams/turning-on-and-using-call-quality-dashboard).</span></span>

- <span data-ttu-id="aec5d-140">로컬 LCSCdr 및 QoEMetrics 데이터베이스를 사용 하 여 모니터링을 위해 프런트 엔드 풀을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="aec5d-140">Enable the front end pool for Monitoring, with local LCSCdr and QoEMetrics databases.</span></span> <span data-ttu-id="aec5d-141">이 없이는 Call Data Connector에 사용할 수 있는 메트릭 데이터가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="aec5d-141">Without this, Call Data Connector won't have metrics data to work with.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="aec5d-142">프런트 엔드 풀에서 모니터링을 사용할 수 없는 경우에는 Call Data Connector가 작동 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="aec5d-142">Call Data Connector will not function if Monitoring is not enabled on the front end pool.</span></span>

## <a name="comparison-of-on-premises-and-online-call-quality-dashboard-cqd-reports"></a><span data-ttu-id="aec5d-143">온-프레미스 및 온라인 통화 품질 대시보드 (CQD) 보고서 비교</span><span class="sxs-lookup"><span data-stu-id="aec5d-143">Comparison of on-premises and online Call Quality Dashboard (CQD) reports</span></span>

| <span data-ttu-id="aec5d-144">기능 보고서</span><span class="sxs-lookup"><span data-stu-id="aec5d-144">Feature reports</span></span> | <span data-ttu-id="aec5d-145">비즈니스용 Skype Online</span><span class="sxs-lookup"><span data-stu-id="aec5d-145">Skype for Business Online</span></span> | <span data-ttu-id="aec5d-146">비즈니스용 Skype 서버</span><span class="sxs-lookup"><span data-stu-id="aec5d-146">Skype for Business Server</span></span>   |
|:---------------------------|:---------------------|:---------------------|:------------------|
| <span data-ttu-id="aec5d-147">응용 프로그램 공유 메트릭</span><span class="sxs-lookup"><span data-stu-id="aec5d-147">Application sharing metric</span></span> |<span data-ttu-id="aec5d-148">'</span><span class="sxs-lookup"><span data-stu-id="aec5d-148">Yes</span></span> | <span data-ttu-id="aec5d-149">받습니다</span><span class="sxs-lookup"><span data-stu-id="aec5d-149">Limited</span></span> |
| <span data-ttu-id="aec5d-150">고객 건물 정보</span><span class="sxs-lookup"><span data-stu-id="aec5d-150">Customer building information</span></span>| <span data-ttu-id="aec5d-151">'</span><span class="sxs-lookup"><span data-stu-id="aec5d-151">Yes</span></span> | <span data-ttu-id="aec5d-152">'</span><span class="sxs-lookup"><span data-stu-id="aec5d-152">Yes</span></span> |
| <span data-ttu-id="aec5d-153">드릴 다운 분석</span><span class="sxs-lookup"><span data-stu-id="aec5d-153">Drill-down analytics</span></span> | <span data-ttu-id="aec5d-154">'</span><span class="sxs-lookup"><span data-stu-id="aec5d-154">Yes</span></span> | <span data-ttu-id="aec5d-155">아니요</span><span class="sxs-lookup"><span data-stu-id="aec5d-155">No</span></span> |
| <span data-ttu-id="aec5d-156">미디어 안정성 메트릭</span><span class="sxs-lookup"><span data-stu-id="aec5d-156">Media reliability metrics</span></span> | <span data-ttu-id="aec5d-157">'</span><span class="sxs-lookup"><span data-stu-id="aec5d-157">Yes</span></span> | <span data-ttu-id="aec5d-158">받습니다</span><span class="sxs-lookup"><span data-stu-id="aec5d-158">Limited</span></span> |
| <span data-ttu-id="aec5d-159">오래 된 보고서</span><span class="sxs-lookup"><span data-stu-id="aec5d-159">Out-of-the-box reports</span></span> | <span data-ttu-id="aec5d-160">'</span><span class="sxs-lookup"><span data-stu-id="aec5d-160">Yes</span></span> | <span data-ttu-id="aec5d-161">'</span><span class="sxs-lookup"><span data-stu-id="aec5d-161">Yes</span></span> |
| <span data-ttu-id="aec5d-162">개요 보고서</span><span class="sxs-lookup"><span data-stu-id="aec5d-162">Overview reports</span></span> | <span data-ttu-id="aec5d-163">'</span><span class="sxs-lookup"><span data-stu-id="aec5d-163">Yes</span></span> | <span data-ttu-id="aec5d-164">아니요</span><span class="sxs-lookup"><span data-stu-id="aec5d-164">No</span></span> |
| <span data-ttu-id="aec5d-165">사용자 단위 보고서</span><span class="sxs-lookup"><span data-stu-id="aec5d-165">Per user reports</span></span> | <span data-ttu-id="aec5d-166">'</span><span class="sxs-lookup"><span data-stu-id="aec5d-166">Yes</span></span> | <span data-ttu-id="aec5d-167">'</span><span class="sxs-lookup"><span data-stu-id="aec5d-167">Yes</span></span> |
| <span data-ttu-id="aec5d-168">보고서 집합 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="aec5d-168">Report set customization</span></span> <br> <span data-ttu-id="aec5d-169">(보고서 추가, 삭제, 수정)</span><span class="sxs-lookup"><span data-stu-id="aec5d-169">(add, delete, modify reports)</span></span> | <span data-ttu-id="aec5d-170">'</span><span class="sxs-lookup"><span data-stu-id="aec5d-170">Yes</span></span> | <span data-ttu-id="aec5d-171">'</span><span class="sxs-lookup"><span data-stu-id="aec5d-171">Yes</span></span> |
| <span data-ttu-id="aec5d-172">비디오 기반 화면 공유 메트릭</span><span class="sxs-lookup"><span data-stu-id="aec5d-172">Video-based screen sharing metrics</span></span> | <span data-ttu-id="aec5d-173">'</span><span class="sxs-lookup"><span data-stu-id="aec5d-173">Yes</span></span> | <span data-ttu-id="aec5d-174">아니요</span><span class="sxs-lookup"><span data-stu-id="aec5d-174">No</span></span> |
| <span data-ttu-id="aec5d-175">프로그래밍 액세스용 데이터 Api</span><span class="sxs-lookup"><span data-stu-id="aec5d-175">Data APIs for programmatic access</span></span> <br> <span data-ttu-id="aec5d-176">CQD에</span><span class="sxs-lookup"><span data-stu-id="aec5d-176">to CQD</span></span> | <span data-ttu-id="aec5d-177">아니요</span><span class="sxs-lookup"><span data-stu-id="aec5d-177">No</span></span> | <span data-ttu-id="aec5d-178">'</span><span class="sxs-lookup"><span data-stu-id="aec5d-178">Yes</span></span> |
||||
