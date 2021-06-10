---
title: 통화 데이터 커넥터 | 통화 품질 대시보드 모니터링 하이브리드 분석
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: 하이브리드 시나리오에서 비즈니스용 Skype 온라인 원격 분석 도구를 사용하여 프레미스 구현을 모니터링하는 방법을 간략하게 설명합니다.
ms.openlocfilehash: 7b6076224280446b7fc52c505fe5fc3ab8d41be4
ms.sourcegitcommit: 36bc47b2b9ee0e738fa814c31accacfe816da4a3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/09/2021
ms.locfileid: "52856357"
---
# <a name="plan-call-data-connector"></a><span data-ttu-id="c8fdc-103">호출 데이터 커넥터 계획</span><span class="sxs-lookup"><span data-stu-id="c8fdc-103">Plan Call Data Connector</span></span>

## <a name="overview"></a><span data-ttu-id="c8fdc-104">개요</span><span class="sxs-lookup"><span data-stu-id="c8fdc-104">Overview</span></span>

<span data-ttu-id="c8fdc-105">이 항목에서는 Call Data Connector를 구현하기 위한 이점, 계획 고려 사항 및 비즈니스용 Skype 서버 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c8fdc-105">This topic describes benefits, planning considerations, and requirements for implementing Skype for Business Server Call Data Connector.</span></span> <span data-ttu-id="c8fdc-106">통화 데이터 커넥터 구성에 대한 자세한 내용은 [Configure Call Data Connector을 참조하십시오.](configure-call-data-connector.md)</span><span class="sxs-lookup"><span data-stu-id="c8fdc-106">For more information on configuring Call Data Connector, see [Configure Call Data Connector](configure-call-data-connector.md).</span></span>


<span data-ttu-id="c8fdc-107">통화 데이터 커넥터는 더 이상 서로 다른 On-프레미스 및 온라인 도구 집합을 사용하여 모든 사용자의 통화 품질을 모니터링할 필요가 없는 하이브리드 환경에서 통화 모니터링을 크게 간소화합니다.</span><span class="sxs-lookup"><span data-stu-id="c8fdc-107">Call Data Connector greatly simplifies call monitoring in a hybrid environment because you no longer need to use different sets of on-premises and online tools to monitor all of your users call quality.</span></span> <span data-ttu-id="c8fdc-108">사용자가 온-프레미스에 있는지 온라인에 있는지에 따라 전체 조직의 통화 품질을 온라인으로 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8fdc-108">Whether your users are homed on premises or online, you can choose to view call quality for your entire organization online.</span></span>

<span data-ttu-id="c8fdc-109">Call Data Connector를 사용하면 단일 도구 집합을 사용하여 다음 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8fdc-109">With Call Data Connector, you can perform the following tasks by using a single toolset:</span></span>

- <span data-ttu-id="c8fdc-110">온라인, Microsoft Teams, 비즈니스용 Skype 사용자 환경을 비즈니스용 Skype 서버.</span><span class="sxs-lookup"><span data-stu-id="c8fdc-110">Monitor your user experience across Microsoft Teams, Skype for Business Online, and Skype for Business Server.</span></span>

- <span data-ttu-id="c8fdc-111">네트워크에서 문제를 보고 해결합니다.</span><span class="sxs-lookup"><span data-stu-id="c8fdc-111">View and troubleshoot problems across your network.</span></span>

- <span data-ttu-id="c8fdc-112">기술 지원 팀 작업자가 책임 영역을 보고 문제를 해결할 수 있도록 Call Analytics에 대한 지원 팀 및 관리자 역할을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="c8fdc-112">Assign helpdesk and administrator roles for Call Analytics, so that you can empower helpdesk workers to view and troubleshoot their areas of responsibility.</span></span>

<span data-ttu-id="c8fdc-113">통화 데이터 커넥터를 사용하면 비즈니스용 Skype 서버 다이어그램에 표시된 비즈니스용 Skype 온라인 통화 분석(CA) 및 CQD(통화 품질 대시보드) 도구를 활용할 수 있도록 통화 데이터가 클라우드 서비스에 푸시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8fdc-113">With Call Data Connector, the Skype for Business Server pushes call data to the cloud service so that you can leverage the Skype for Business Online Call Analytics (CA) and Call Quality Dashboard (CQD) tools, as shown in the following diagram:</span></span>

![SfB 클라우드 음성 사서함](../../sfbserver2019/media/call-data-connector-plan-1.png)

<span data-ttu-id="c8fdc-115">서버는 QoE(QoE) 및 CDR(통화 정보 기록) 데이터를 모두 온라인 서비스에 푸시합니다.</span><span class="sxs-lookup"><span data-stu-id="c8fdc-115">The server pushes both Quality of Experience (QoE) and Call Detail Recording (CDR) data to the online service.</span></span>

<span data-ttu-id="c8fdc-116">Call Analytics 및 CQD 도구를 사용하면 통화 품질을 모니터링하고 다음과 같이 Microsoft Teams 비즈니스용 Skype 문제를 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8fdc-116">The Call Analytics and CQD tools enable you to monitor the quality of calls and troubleshoot connection problems with Microsoft Teams and Skype for Business services as follows:</span></span>

- <span data-ttu-id="c8fdc-117">Call Analytics는 특정 통화의 품질 문제에 초점을 맞추고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8fdc-117">Call Analytics focuses on quality problems with specific calls.</span></span> <span data-ttu-id="c8fdc-118">계정의 각 사용자에 대한 통화 및 모임에 대한 자세한 비즈니스용 Skype 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8fdc-118">It shows detailed information about calls and meetings for each user in a Skype for Business account.</span></span>  <span data-ttu-id="c8fdc-119">Call Analytics를 사용하면 기술 지원 센터 운영자에게 사용 권한을 할당할 수 있습니다. 그러면 지원 센터의 나머지 센터에 액세스하지 않고도 통화를 모니터링할 비즈니스용 Skype 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8fdc-119">With Call Analytics, you can assign permissions to a helpdesk operator who can then monitor calls without having access to the rest of the Skype for Business Admin center.</span></span>

- <span data-ttu-id="c8fdc-120">통화 품질 대시보드는 조직 전체의 네트워크 성능 및 문제에 중점을 .</span><span class="sxs-lookup"><span data-stu-id="c8fdc-120">Call Quality Dashboard focuses on network performance and issues across an organization.</span></span> <span data-ttu-id="c8fdc-121">비즈니스용 Skype 네트워크 엔지니어는 이 도구를 사용하여 네트워크 성능 문제를 해결하고 최적화합니다.</span><span class="sxs-lookup"><span data-stu-id="c8fdc-121">Skype for Business administrators and network engineers use this tool to troubleshoot and optimize network performance.</span></span>

<span data-ttu-id="c8fdc-122">자세한 내용은 통화 분석 및 통화 품질 [대시보드를 참조하세요.](/SkypeForBusiness/using-call-quality-in-your-organization/difference-between-call-analytics-and-call-quality-dashboard)</span><span class="sxs-lookup"><span data-stu-id="c8fdc-122">For more information, see [Call Analytics and Call Quality Dashboard](/SkypeForBusiness/using-call-quality-in-your-organization/difference-between-call-analytics-and-call-quality-dashboard).</span></span>

<span data-ttu-id="c8fdc-123">물론 일부 통화 품질 데이터를 프레미스에 유지할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8fdc-123">Of course, you might want to keep some call quality data on premises.</span></span> <span data-ttu-id="c8fdc-124">예를 들어 사용자 지정된 보고서 및 워크플로가 있는 타사 솔루션을 사용하는 경우를 예로 들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8fdc-124">This might be the case, for example, if you are using a third-party solution with customized reports and workflows.</span></span>  <span data-ttu-id="c8fdc-125">통화 데이터 커넥터를 사용하면 다음 다이어그램과 같이 온라인 서비스에 데이터 전송을 구성하는 동시에 데이터 복사본을 사내 서버에 유지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8fdc-125">Call Data Connector allows you to configure sending data to the online service while also keeping a copy of the data on your on-premises server, as shown in the following diagram:</span></span>

![SfB 클라우드 음성 사서함](../../sfbserver2019/media/call-data-connector-plan-2.png)

## <a name="requirements"></a><span data-ttu-id="c8fdc-127">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c8fdc-127">Requirements</span></span>

<span data-ttu-id="c8fdc-128">다음 요구 사항은 지원되는 토폴로지에서 비즈니스용 Skype 서버 이미 배포했다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="c8fdc-128">The following requirements assume that you already have Skype for Business Server deployed in a supported topology.</span></span>  <span data-ttu-id="c8fdc-129">토폴로지 및 지원되는 비즈니스용 Skype 서버 배포하는 비즈니스용 Skype 서버 토폴로지 [기본 정보를 참조하세요.](../../SfbServer/plan-your-deployment/topology-basics/topology-basics.md)</span><span class="sxs-lookup"><span data-stu-id="c8fdc-129">For more information about deploying Skype for Business Server and supported topologies, see [Topology Basics](../../SfbServer/plan-your-deployment/topology-basics/topology-basics.md).</span></span> <span data-ttu-id="c8fdc-130">통화 데이터 커넥터를 구성하려면 다음을 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8fdc-130">To configure Call Data Connector, you must:</span></span>

- <span data-ttu-id="c8fdc-131">하이브리드 연결을 사용하도록 설정</span><span class="sxs-lookup"><span data-stu-id="c8fdc-131">Enable Hybrid connectivity.</span></span> <span data-ttu-id="c8fdc-132">이미 배포된 비즈니스용 Skype 서버 경우 통화 데이터 커넥터를 사용하도록 설정하려는 경우, 사내 환경과 온라인 환경 간에 하이브리드 연결을 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8fdc-132">If you already have Skype for Business Server deployed and you want to enable Call Data Connector, you must ensure that you have hybrid connectivity set up between your on-premises and online environments.</span></span> <span data-ttu-id="c8fdc-133">이를 분할 도메인 구성이라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8fdc-133">This is sometimes called a split domain configuration.</span></span>

   <span data-ttu-id="c8fdc-134">자세한 내용은 비즈니스용 Skype 서버 [](plan-hybrid-connectivity.md) 및 Microsoft 365 또는 Office 365 간의 하이브리드 연결 계획 및 비즈니스용 Skype 서버 및 Microsoft 365 또는 [Office 365.](configure-hybrid-connectivity.md)</span><span class="sxs-lookup"><span data-stu-id="c8fdc-134">For more information, see [Plan hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365](plan-hybrid-connectivity.md) and [Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365](configure-hybrid-connectivity.md).</span></span>

- <span data-ttu-id="c8fdc-135">조직 또는 Microsoft 365 Office 365 인증하고 다음 역할을 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8fdc-135">Authenticate to your Microsoft 365 or Office 365 organization and ensure that you have the following roles enabled:</span></span>

  - <span data-ttu-id="c8fdc-136">비즈니스용 Skype 서버 관리자</span><span class="sxs-lookup"><span data-stu-id="c8fdc-136">Skype for Business Server Administrator</span></span>
  - <span data-ttu-id="c8fdc-137">Microsoft 365 또는 Office 365 관리자</span><span class="sxs-lookup"><span data-stu-id="c8fdc-137">Microsoft 365 or Office 365 Global Administrator</span></span>

- <span data-ttu-id="c8fdc-138">아직 수행하지 않은 경우 통화 품질 대시보드 켜기 및 사용에 설명된 바와 같이 통화 품질 대시보드를 Microsoft Teams [비즈니스용 Skype 을 선택합니다.](/microsoftteams/turning-on-and-using-call-quality-dashboard)</span><span class="sxs-lookup"><span data-stu-id="c8fdc-138">If you have not already done so, turn on Call Quality Dashboard as described in [Turning on and using Call Quality Dashboard for Microsoft Teams and Skype for Business Online](/microsoftteams/turning-on-and-using-call-quality-dashboard).</span></span>

- <span data-ttu-id="c8fdc-139">로컬 LCSCdr 및 QoEMetrics 데이터베이스를 사용하여 모니터링에 프런트 엔드 풀을 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8fdc-139">Enable the front end pool for Monitoring, with local LCSCdr and QoEMetrics databases.</span></span> <span data-ttu-id="c8fdc-140">이렇게 하지 않으면 Call Data Connector에 사용할 메트릭 데이터가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c8fdc-140">Without this, Call Data Connector won't have metrics data to work with.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c8fdc-141">프런트 엔드 풀에서 모니터링을 사용하도록 설정하지 않은 경우 통화 데이터 커넥터가 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c8fdc-141">Call Data Connector will not function if Monitoring is not enabled on the front end pool.</span></span>

- <span data-ttu-id="c8fdc-142">서버 대 서버 인증을 [올바르게 구성했습니다.](../../SfbServer/manage/authentication/server-to-server-and-partner-applications.md)</span><span class="sxs-lookup"><span data-stu-id="c8fdc-142">Properly configured [server-to-server authentication](../../SfbServer/manage/authentication/server-to-server-and-partner-applications.md).</span></span> 

## <a name="comparison-of-on-premises-and-online-call-quality-dashboard-cqd-reports"></a><span data-ttu-id="c8fdc-143">프레미스 및 온라인 CQD(통화 품질 대시보드) 보고서 비교</span><span class="sxs-lookup"><span data-stu-id="c8fdc-143">Comparison of on-premises and online Call Quality Dashboard (CQD) reports</span></span>

| <span data-ttu-id="c8fdc-144">기능 보고서</span><span class="sxs-lookup"><span data-stu-id="c8fdc-144">Feature reports</span></span> | <span data-ttu-id="c8fdc-145">비즈니스용 Skype 온라인</span><span class="sxs-lookup"><span data-stu-id="c8fdc-145">Skype for Business Online</span></span> | <span data-ttu-id="c8fdc-146">비즈니스용 Skype 서버</span><span class="sxs-lookup"><span data-stu-id="c8fdc-146">Skype for Business Server</span></span>   |
|:---------------------------|:---------------------|:---------------------|:------------------|
| <span data-ttu-id="c8fdc-147">응용 프로그램 공유 메트릭</span><span class="sxs-lookup"><span data-stu-id="c8fdc-147">Application sharing metric</span></span> |<span data-ttu-id="c8fdc-148">예</span><span class="sxs-lookup"><span data-stu-id="c8fdc-148">Yes</span></span> | <span data-ttu-id="c8fdc-149">제한</span><span class="sxs-lookup"><span data-stu-id="c8fdc-149">Limited</span></span> |
| <span data-ttu-id="c8fdc-150">고객 구축 정보</span><span class="sxs-lookup"><span data-stu-id="c8fdc-150">Customer building information</span></span>| <span data-ttu-id="c8fdc-151">예</span><span class="sxs-lookup"><span data-stu-id="c8fdc-151">Yes</span></span> | <span data-ttu-id="c8fdc-152">예</span><span class="sxs-lookup"><span data-stu-id="c8fdc-152">Yes</span></span> |
| <span data-ttu-id="c8fdc-153">드릴다운 분석</span><span class="sxs-lookup"><span data-stu-id="c8fdc-153">Drill-down analytics</span></span> | <span data-ttu-id="c8fdc-154">예</span><span class="sxs-lookup"><span data-stu-id="c8fdc-154">Yes</span></span> | <span data-ttu-id="c8fdc-155">아니요</span><span class="sxs-lookup"><span data-stu-id="c8fdc-155">No</span></span> |
| <span data-ttu-id="c8fdc-156">미디어 안정성 메트릭</span><span class="sxs-lookup"><span data-stu-id="c8fdc-156">Media reliability metrics</span></span> | <span data-ttu-id="c8fdc-157">예</span><span class="sxs-lookup"><span data-stu-id="c8fdc-157">Yes</span></span> | <span data-ttu-id="c8fdc-158">제한</span><span class="sxs-lookup"><span data-stu-id="c8fdc-158">Limited</span></span> |
| <span data-ttu-id="c8fdc-159">Out-of-the-box reports</span><span class="sxs-lookup"><span data-stu-id="c8fdc-159">Out-of-the-box reports</span></span> | <span data-ttu-id="c8fdc-160">예</span><span class="sxs-lookup"><span data-stu-id="c8fdc-160">Yes</span></span> | <span data-ttu-id="c8fdc-161">예</span><span class="sxs-lookup"><span data-stu-id="c8fdc-161">Yes</span></span> |
| <span data-ttu-id="c8fdc-162">개요 보고서</span><span class="sxs-lookup"><span data-stu-id="c8fdc-162">Overview reports</span></span> | <span data-ttu-id="c8fdc-163">예</span><span class="sxs-lookup"><span data-stu-id="c8fdc-163">Yes</span></span> | <span data-ttu-id="c8fdc-164">아니요</span><span class="sxs-lookup"><span data-stu-id="c8fdc-164">No</span></span> |
| <span data-ttu-id="c8fdc-165">사용자당 보고서</span><span class="sxs-lookup"><span data-stu-id="c8fdc-165">Per user reports</span></span> | <span data-ttu-id="c8fdc-166">예</span><span class="sxs-lookup"><span data-stu-id="c8fdc-166">Yes</span></span> | <span data-ttu-id="c8fdc-167">예</span><span class="sxs-lookup"><span data-stu-id="c8fdc-167">Yes</span></span> |
| <span data-ttu-id="c8fdc-168">보고서 집합 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="c8fdc-168">Report set customization</span></span> <br> <span data-ttu-id="c8fdc-169">(보고서 추가, 삭제, 수정)</span><span class="sxs-lookup"><span data-stu-id="c8fdc-169">(add, delete, modify reports)</span></span> | <span data-ttu-id="c8fdc-170">예</span><span class="sxs-lookup"><span data-stu-id="c8fdc-170">Yes</span></span> | <span data-ttu-id="c8fdc-171">예</span><span class="sxs-lookup"><span data-stu-id="c8fdc-171">Yes</span></span> |
| <span data-ttu-id="c8fdc-172">비디오 기반 화면 공유 메트릭</span><span class="sxs-lookup"><span data-stu-id="c8fdc-172">Video-based screen sharing metrics</span></span> | <span data-ttu-id="c8fdc-173">예</span><span class="sxs-lookup"><span data-stu-id="c8fdc-173">Yes</span></span> | <span data-ttu-id="c8fdc-174">아니요</span><span class="sxs-lookup"><span data-stu-id="c8fdc-174">No</span></span> |
| <span data-ttu-id="c8fdc-175">프로그래밍식 액세스를 위한 데이터 API</span><span class="sxs-lookup"><span data-stu-id="c8fdc-175">Data APIs for programmatic access</span></span> <br> <span data-ttu-id="c8fdc-176">를 CQD로</span><span class="sxs-lookup"><span data-stu-id="c8fdc-176">to CQD</span></span> | <span data-ttu-id="c8fdc-177">아니요</span><span class="sxs-lookup"><span data-stu-id="c8fdc-177">No</span></span> | <span data-ttu-id="c8fdc-178">예</span><span class="sxs-lookup"><span data-stu-id="c8fdc-178">Yes</span></span> |
||||