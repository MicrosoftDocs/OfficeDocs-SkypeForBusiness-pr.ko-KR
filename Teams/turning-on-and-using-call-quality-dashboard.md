---
title: 통화 품질 대시보드 켜기 및 사용
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, wlooney, gageames
ms.topic: article
ms.assetid: 553fa13c-92d2-4d5c-a3d5-41a073cb047c
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords:
- ms.lync.lac.ToolsCallQualityDashboard
- ms.teamsadmincenter.directrouting.cqd
ms.custom:
- Reporting
description: '비즈니스용 Skype Online 통화 품질 대시보드를 켜고 사용 하는 방법과 통화 품질에 대 한 요약 보고서를 참조 하세요. '
ms.openlocfilehash: eaadd80030b04d5fb10fd8f29d656fe07e24a1db
ms.sourcegitcommit: ab259764dc50bdd52efed3abb1d065ee19486946
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/13/2019
ms.locfileid: "36393496"
---
# <a name="turning-on-and-using-call-quality-dashboard-for-microsoft-teams-and-skype-for-business-online"></a><span data-ttu-id="2d604-103">Microsoft 팀 및 비즈니스용 Skype Online에 대 한 통화 품질 대시보드 켜기 및 사용</span><span class="sxs-lookup"><span data-stu-id="2d604-103">Turning on and using Call Quality Dashboard for Microsoft Teams and Skype for Business Online</span></span>

<span data-ttu-id="2d604-104">통화 품질 대시보드를 사용 하 여 통화 품질을 모니터링 하도록 Office 365 조직을 구성 하는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="2d604-104">Learn how to configure your Office 365 organization to use the Call Quality Dashboard to monitor call quality.</span></span>
  
<span data-ttu-id="2d604-105">Microsoft 팀 및 비즈니스용 Skype Online에 대 한 CQD (통화 품질 대시보드)는 Microsoft 팀과 비즈니스용 Skype 서비스를 사용 하 여 만든 통화 품질에 대 한 통찰력을 얻을 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d604-105">The Call Quality Dashboard (CQD) for Microsoft Teams and Skype for Business Online allows you to gain insights into the quality of calls made using Microsoft Teams and Skype for Business services.</span></span> <span data-ttu-id="2d604-106">이 항목에서는 데이터 수집을 시작 하기 위해 수행 해야 하는 단계에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d604-106">This topic describes the steps you'll need to complete to start collecting data.</span></span>
  
  
## <a name="latest-changes-and-updates"></a><span data-ttu-id="2d604-107">최신 변경 및 업데이트</span><span class="sxs-lookup"><span data-stu-id="2d604-107">Latest changes and updates</span></span>

<span data-ttu-id="2d604-108">CQD에 대 한 최신 변경 사항은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="2d604-108">The most recent changes to CQD are as follows:</span></span>
  
- <span data-ttu-id="2d604-109">비즈니스용 Skype Online 데이터 외에 Microsoft 팀 데이터도 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d604-109">Includes Microsoft Teams data in addition to Skype for Business Online data.</span></span>
    
- <span data-ttu-id="2d604-110">요약 보고서에는 모든 데이터, Microsoft 팀 데이터 또는 비즈니스용 Skype Online 데이터를 선택 하는 제품 필터가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d604-110">Summary reports include a product filter to select all data, Microsoft Teams data, or Skype for Business Online data.</span></span>

- <span data-ttu-id="2d604-111">비디오 및 VBSS 스트림 품질 분류 논리가 업데이트 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="2d604-111">Video and VBSS stream quality classification logic has been updated.</span></span> <span data-ttu-id="2d604-112">최신 분류자 정의에 대 한 [통화 품질 대시보드의 스트림 분류](stream-classification-in-call-quality-dashboard.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2d604-112">Refer to [Stream Classification in Call Quality Dashboard](stream-classification-in-call-quality-dashboard.md) for the latest classifier definitions.</span></span>

<span data-ttu-id="2d604-113">[통화 품질 대시보드에서 사용할 수 있는 차원 및 측정값](dimensions-and-measures-available-in-call-quality-dashboard.md)목록은이 문서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2d604-113">Refer to this article for a list of [Dimensions and measures available in Call Quality Dashboard](dimensions-and-measures-available-in-call-quality-dashboard.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="2d604-114">대시보드의 업데이트 및 변경에 대 한 정보는 **좋은 뉴스** 의 링크를 클릭 하 여 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d604-114">Information about updates and changes to the dashboard can be found by clicking the link in the **Good news!**</span></span> <span data-ttu-id="2d604-115">배너가 대시보드에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d604-115">banner when it is displayed on the dashboard.</span></span>
  
## <a name="activate-microsoft-call-quality-dashboard-cqd-summary-reports"></a><span data-ttu-id="2d604-116">CQD (Microsoft 통화 품질 대시보드) 요약 보고서 활성화</span><span class="sxs-lookup"><span data-stu-id="2d604-116">Activate Microsoft Call Quality Dashboard (CQD) Summary Reports</span></span>

<span data-ttu-id="2d604-117">CQD 사용을 시작 하려면 먼저 Office 365 조직에 대해 정품 인증을 받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d604-117">Before you can start using the CQD, you'll need to activate it for your Office 365 organization.</span></span>

<span data-ttu-id="2d604-118">![](media/teams-logo-30x30.png) **Microsoft 팀 관리 센터를 사용 하 여** microsoft 팀 로고를 표시 하는 아이콘</span><span class="sxs-lookup"><span data-stu-id="2d604-118">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>
 
1. <span data-ttu-id="2d604-119">Microsoft 팀 서비스 관리자 계정을 사용 하 여 Office 365 조직에 로그인 한 다음 **관리** 타일을 선택 하 여 관리 센터를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="2d604-119">Sign in to your Office 365 organization using Microsoft Teams service admin account, and then select the **Admin** tile to open the Admin center.</span></span>
    
2. <span data-ttu-id="2d604-120">왼쪽 창의 **관리 센터**에서 microsoft 팀을 선택 하 \*\*\*\* 여 microsoft 팀 관리 센터를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="2d604-120">In the left pane, under **Admin centers**, select **Microsoft Teams** to open the Microsoft Teams admin center.</span></span>
    
3. <span data-ttu-id="2d604-121">Microsoft 팀 관리 센터의 왼쪽 창에서 **통화 품질 대시보드** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d604-121">In the Microsoft Teams admin center, select **Call quality dashboard** in the left pane.</span></span>
    
  
4. <span data-ttu-id="2d604-122">열리는 페이지에서 전역 관리자 계정 또는 Microsoft 팀 서비스 관리자 계정으로 로그인 한 다음 메시지가 표시 되 면 계정에 대 한 자격 증명을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d604-122">On the page that opens, sign in with your Global Administrator account or Microsoft Teams Service Admin account, and then provide the credentials for the account when prompted.</span></span>
    
     ![자격 증명 프롬프트를 보여 주는 스크린샷](media/ac4c1699-d8c1-4bda-af30-0fec35b5fd22.png)
  
<span data-ttu-id="2d604-124">로그인 한 후에는 CQD가 사용자가 데이터를 수집 하 고 처리 하기 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d604-124">After you sign in, once activated, the CQD will begin collecting and processing data.</span></span>  
> [!NOTE]
> <span data-ttu-id="2d604-125">보고서에 의미 있는 결과를 표시 하기에 충분 한 데이터를 처리 하는 데 몇 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d604-125">It may take a couple of hours to process enough data to display meaningful results in the reports.</span></span> 

<span data-ttu-id="2d604-126">![비즈니스용 skype](media/sfb-logo-30x30.png) **관리 센터를 사용 하 여** 비즈니스용 skype 로고를 표시 하는 아이콘</span><span class="sxs-lookup"><span data-stu-id="2d604-126">![An icon showing the Skype for Business logo](media/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>
 
1. <span data-ttu-id="2d604-127">관리자 계정을 사용 하 여 Office 365 조직에 로그인 한 다음 관리 타일을 선택 \*\*\*\* 하 여 관리 센터를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="2d604-127">Sign in to your Office 365 organization using an admin account, and then select the **Admin** tile to open the Admin center.</span></span>
    
2. <span data-ttu-id="2d604-128">왼쪽 창의 **관리 센터**에서 비즈니스용 **skype** 를 선택 하 여 비즈니스용 skype 관리 센터를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="2d604-128">In the left pane, under **Admin centers**, select **Skype for Business** to open the Skype for Business admin center.</span></span>
    
3. <span data-ttu-id="2d604-129">비즈니스용 Skype 관리 센터의 왼쪽 창에서 **도구** 를 선택한 다음 비즈니스용 **Skype Online 통화 품질 대시보드**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d604-129">In the Skype for Business admin center, select **Tools** in the left pane, and then select **Skype for Business Online Call Quality Dashboard**.</span></span>
    
     ![통화 품질 대시보드 선택을 보여주는 스크린샷](media/6cc7f80f-b8e2-4a9b-aab8-ac871d07a261.png)
  
4. <span data-ttu-id="2d604-131">열리는 페이지에서 전역 관리자 계정으로 로그인 한 다음 메시지가 표시 되 면 계정에 대 한 자격 증명을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d604-131">On the page that opens, sign in with your Global Administrator account, and then provide the credentials for the account when prompted.</span></span>
    
     ![자격 증명 프롬프트를 보여 주는 스크린샷](media/ac4c1699-d8c1-4bda-af30-0fec35b5fd22.png)
  
<span data-ttu-id="2d604-133">로그인 한 후에는 CQD가 사용자가 데이터를 수집 하 고 처리 하기 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d604-133">After you sign in, once activated, the CQD will begin collecting and processing data.</span></span>


  
## <a name="features-of-the-call-quality-dashboard-for-microsoft-teams-and-skype-for-business-online"></a><span data-ttu-id="2d604-134">Microsoft 팀 및 비즈니스용 Skype Online에 대 한 통화 품질 대시보드의 기능</span><span class="sxs-lookup"><span data-stu-id="2d604-134">Features of the Call Quality Dashboard for Microsoft Teams and Skype for Business Online</span></span> 
<span data-ttu-id="2d604-135"><a name="BKMKFeaturesOfTheCQD"> </a></span><span class="sxs-lookup"><span data-stu-id="2d604-135"></span></span>

<span data-ttu-id="2d604-136">CQD 요약 보고서는 자세한 보고서에 대해 계획 된 기능의 하위 집합을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d604-136">CQD Summary Reports provide a subset of the features planned for Detailed Reports.</span></span> <span data-ttu-id="2d604-137">두 버전 간의 차이점은 다음과 같이 요약할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d604-137">The differences between the two editions are summarized here:</span></span>
  
|<span data-ttu-id="2d604-138">**요소**</span><span class="sxs-lookup"><span data-stu-id="2d604-138">**Feature**</span></span>|<span data-ttu-id="2d604-139">**요약 보고서**</span><span class="sxs-lookup"><span data-stu-id="2d604-139">**Summary Reports**</span></span>|<span data-ttu-id="2d604-140">**자세한 보고서**</span><span class="sxs-lookup"><span data-stu-id="2d604-140">**Detailed Reports**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="2d604-141">응용 프로그램 공유 메트릭</span><span class="sxs-lookup"><span data-stu-id="2d604-141">Application sharing metric</span></span>  <br/> |<span data-ttu-id="2d604-142">아니요</span><span class="sxs-lookup"><span data-stu-id="2d604-142">No</span></span>  <br/> |<span data-ttu-id="2d604-143">'</span><span class="sxs-lookup"><span data-stu-id="2d604-143">Yes</span></span>  <br/> |
|<span data-ttu-id="2d604-144">고객 건물 정보 지원</span><span class="sxs-lookup"><span data-stu-id="2d604-144">Customer building information support</span></span>  <br/> |<span data-ttu-id="2d604-145">'</span><span class="sxs-lookup"><span data-stu-id="2d604-145">Yes</span></span>  <br/> |<span data-ttu-id="2d604-146">'</span><span class="sxs-lookup"><span data-stu-id="2d604-146">Yes</span></span>  <br/> |
|<span data-ttu-id="2d604-147">고객 끝점 정보 지원</span><span class="sxs-lookup"><span data-stu-id="2d604-147">Customer endpoint information support</span></span>  <br/> |<span data-ttu-id="2d604-148">Cqd.teams.microsoft.com 에서만</span><span class="sxs-lookup"><span data-stu-id="2d604-148">Only in cqd.teams.microsoft.com</span></span>  <br/> |<span data-ttu-id="2d604-149">Cqd.teams.microsoft.com 에서만</span><span class="sxs-lookup"><span data-stu-id="2d604-149">Only in cqd.teams.microsoft.com</span></span>  <br/> |
|<span data-ttu-id="2d604-150">드릴 다운 분석 지원</span><span class="sxs-lookup"><span data-stu-id="2d604-150">Drill-down analysis support</span></span>  <br/> |<span data-ttu-id="2d604-151">아니요</span><span class="sxs-lookup"><span data-stu-id="2d604-151">No</span></span>  <br/> |<span data-ttu-id="2d604-152">'</span><span class="sxs-lookup"><span data-stu-id="2d604-152">Yes</span></span>  <br/> |
|<span data-ttu-id="2d604-153">미디어 안정성 메트릭</span><span class="sxs-lookup"><span data-stu-id="2d604-153">Media reliability metrics</span></span>  <br/> |<span data-ttu-id="2d604-154">아니요</span><span class="sxs-lookup"><span data-stu-id="2d604-154">No</span></span>  <br/> |<span data-ttu-id="2d604-155">'</span><span class="sxs-lookup"><span data-stu-id="2d604-155">Yes</span></span>  <br/> |
|<span data-ttu-id="2d604-156">오래 된 보고서</span><span class="sxs-lookup"><span data-stu-id="2d604-156">Out-of-the-box reports</span></span>  <br/> |<span data-ttu-id="2d604-157">'</span><span class="sxs-lookup"><span data-stu-id="2d604-157">Yes</span></span>  <br/> |<span data-ttu-id="2d604-158">'</span><span class="sxs-lookup"><span data-stu-id="2d604-158">Yes</span></span>  <br/> |
|<span data-ttu-id="2d604-159">개요 보고서</span><span class="sxs-lookup"><span data-stu-id="2d604-159">Overview reports</span></span>  <br/> |<span data-ttu-id="2d604-160">'</span><span class="sxs-lookup"><span data-stu-id="2d604-160">Yes</span></span>  <br/> |<span data-ttu-id="2d604-161">'</span><span class="sxs-lookup"><span data-stu-id="2d604-161">Yes</span></span>  <br/> |
|<span data-ttu-id="2d604-162">사용자 단위 보고서 집합</span><span class="sxs-lookup"><span data-stu-id="2d604-162">Per-user report set</span></span>  <br/> |<span data-ttu-id="2d604-163">아니요</span><span class="sxs-lookup"><span data-stu-id="2d604-163">No</span></span>  <br/> |<span data-ttu-id="2d604-164">'</span><span class="sxs-lookup"><span data-stu-id="2d604-164">Yes</span></span>  <br/> |
|<span data-ttu-id="2d604-165">보고서 집합 사용자 지정 (보고서 추가, 삭제, 수정)</span><span class="sxs-lookup"><span data-stu-id="2d604-165">Report set customization (add, delete, modify reports)</span></span>  <br/> |<span data-ttu-id="2d604-166">아니요</span><span class="sxs-lookup"><span data-stu-id="2d604-166">No</span></span>  <br/> |<span data-ttu-id="2d604-167">'</span><span class="sxs-lookup"><span data-stu-id="2d604-167">Yes</span></span>  <br/> |
|<span data-ttu-id="2d604-168">비디오 기반 화면 공유 메트릭</span><span class="sxs-lookup"><span data-stu-id="2d604-168">Video-based screen sharing metrics</span></span>  <br/> |<span data-ttu-id="2d604-169">아니요</span><span class="sxs-lookup"><span data-stu-id="2d604-169">No</span></span>  <br/> |<span data-ttu-id="2d604-170">'</span><span class="sxs-lookup"><span data-stu-id="2d604-170">Yes</span></span>  <br/> |
|<span data-ttu-id="2d604-171">비디오 메트릭</span><span class="sxs-lookup"><span data-stu-id="2d604-171">Video metrics</span></span>  <br/> |<span data-ttu-id="2d604-172">아니요</span><span class="sxs-lookup"><span data-stu-id="2d604-172">No</span></span>  <br/> |<span data-ttu-id="2d604-173">'</span><span class="sxs-lookup"><span data-stu-id="2d604-173">Yes</span></span>  <br/> |
|<span data-ttu-id="2d604-174">사용할 수 있는 데이터 양</span><span class="sxs-lookup"><span data-stu-id="2d604-174">Amount of data available</span></span>  <br/> |<span data-ttu-id="2d604-175">지난 6 개월</span><span class="sxs-lookup"><span data-stu-id="2d604-175">Last 6 months</span></span>  <br/> |<span data-ttu-id="2d604-176">지난 6 개월</span><span class="sxs-lookup"><span data-stu-id="2d604-176">Last 6 months</span></span>  <br/> |
|<span data-ttu-id="2d604-177">Microsoft 팀 데이터</span><span class="sxs-lookup"><span data-stu-id="2d604-177">Microsoft Teams data</span></span>  <br/> |<span data-ttu-id="2d604-178">'</span><span class="sxs-lookup"><span data-stu-id="2d604-178">Yes</span></span>  <br/> |<span data-ttu-id="2d604-179">'</span><span class="sxs-lookup"><span data-stu-id="2d604-179">Yes</span></span>  <br/> |
   
### <a name="out-of-the-box-reports"></a><span data-ttu-id="2d604-180">오래 된 보고서</span><span class="sxs-lookup"><span data-stu-id="2d604-180">Out-of-the-box reports</span></span>

<span data-ttu-id="2d604-181">CQD의 두 가지 버전 모두 새로운 보고서를 만들 필요 없이 품질 메트릭을 제공 하는 데 사용할 수 있는 경험 치를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d604-181">Both editions of CQD provide an out-of-the-box experience, giving you call quality metrics without the need to create any new reports.</span></span> <span data-ttu-id="2d604-182">백 엔드에서 데이터가 처리 되 면 보고서에 통화 품질 데이터를 표시 하는 것을 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d604-182">Once data is processed in the back-end, you can start seeing call quality data in the reports.</span></span>
  
### <a name="overview-reports"></a><span data-ttu-id="2d604-183">개요 보고서</span><span class="sxs-lookup"><span data-stu-id="2d604-183">Overview reports</span></span>

<span data-ttu-id="2d604-184">CQD의 두 버전 모두 전체 통화 품질 정보에 대 한 상위 수준의 진입점을 제공 하지만 요약 보고서에 표시 되는 정보는 자세한 보고서와 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="2d604-184">Both editions of the CQD provide a high-level entry point to the overall call quality information, but the way information is presented in Summary Reports is different from that of Detailed Reports.</span></span>
  
<span data-ttu-id="2d604-185">요약 보고서는 사용자가 전체 통화 품질 상태 및 추세를 빠르게 찾아보고 이해할 수 있는 간단한 탭 페이지 보고서 보기를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d604-185">Summary Reports provide a simplified tabbed page report view that enables users to quickly browse and understand the overall call quality status and trends.</span></span>
  
<span data-ttu-id="2d604-186">네 개의 탭에는 다음이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d604-186">The four tabs include:</span></span>
  
- <span data-ttu-id="2d604-187">**전체 통화 품질** -서버 클라이언트 스트림 및 클라이언트-클라이언트 스트림의 집계 인 모든 스트림에 대 한 정보를 제공 하며, 개별 서버 클라이언트 및 클라이언트-클라이언트 스트림은 월 단위 및 일일 추세 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="2d604-187">**Overall Call Quality** - provides information about all streams, which is an aggregation of Server-Client streams and Client-Client streams, as well as separate Server-Client and Client-Client streams, in the form of monthly and daily trends.</span></span>
    
- <span data-ttu-id="2d604-188">**서버-클라이언트** -서버 및 클라이언트 끝점 간 스트림에 대 한 추가 세부 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d604-188">**Server - Client** - provides additional details for the streams between Server and Client endpoints.</span></span>
    
- <span data-ttu-id="2d604-189">**클라이언트-클라이언트** -두 클라이언트 끝점 간 스트림에 대 한 추가 세부 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d604-189">**Client - Client** - provides additional details for the streams between two Client endpoints.</span></span>
    
- <span data-ttu-id="2d604-190">**음성 품질 SLA** -비즈니스용 Skype Online 보이스 품질 sla에 포함 된 통화에 대 한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d604-190">**Voice Quality SLA** - provides information about calls that are included in the Skype for Business Online Voice Quality SLA.</span></span>
    
### <a name="overall-call-quality-tab"></a><span data-ttu-id="2d604-191">전체 통화 음질 탭</span><span class="sxs-lookup"><span data-stu-id="2d604-191">Overall Call Quality tab</span></span>

<span data-ttu-id="2d604-192">이 탭의 데이터를 사용 하 여 스트림 개수와 낮은 백분율을 확인 하 여 통화 품질 상태 및 추세를 평가 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d604-192">Use the data on this tab to evaluate call quality status and trends by looking at the stream counts and poor percentages.</span></span> <span data-ttu-id="2d604-193">오른쪽 위 모서리에 있는 범례는 이러한 메트릭을 나타내는 색 및 시각적 요소를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2d604-193">The legend in the upper-right corner shows which color and visual elements represent these metrics.</span></span>
  
![통화 품질 탭을 보여 주는 스크린샷](media/c8d183b1-6592-49b0-a81d-35cc0568d5f0.png)
  
<span data-ttu-id="2d604-195">스트림은 세 가지 그룹 (좋음, 나쁨, 미분류)으로 분류 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d604-195">Streams are classified in three groups: Good, Poor, and Unclassified.</span></span> <span data-ttu-id="2d604-196">또한 총 분류 스트림 개수에 *좋지* 않은 스트림의 비율을 제공 하는 *불량%* 값이 계산 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d604-196">There are also calculated  *Poor %*  values that give you the ratio of streams classified as *Poor*  to the total classified stream count.</span></span> <span data-ttu-id="2d604-197">*불량% = 불량 스트림/(불량 스트림 + 양호한 스트림) \* 100* 때문에 *분류* 되지 않은 \*\* 여러 스트림의 현재 상태에 따라 영향을 받지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2d604-197">Since *Poor % = Poor streams/ (Poor streams+ Good streams) \* 100*  , this makes the *Poor %*  unaffected by the presence with multiple *Unclassified*  streams.</span></span> <span data-ttu-id="2d604-198">스트림 분류에 사용 되는 항목에 대 한 자세한 내용은 [통화 품질 대시보드의 스트림 분류](stream-classification-in-call-quality-dashboard.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2d604-198">For what is used for classifying a stream as poor or good, refer to [Stream Classification in Call Quality Dashboard](stream-classification-in-call-quality-dashboard.md).</span></span>
  
<span data-ttu-id="2d604-199">왼쪽의 배율을 사용 하 여 스트림 개수 값을 측정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d604-199">Use the scale on the left to measure the stream count values.</span></span>
  
![스트림 개수 값을 보여 주는 스크린샷](media/850bd25d-d9b2-4df4-8ca6-526a528897c2.png)
  
<span data-ttu-id="2d604-201">오른쪽의 배율을 사용 하 여 불량% 값을 측정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d604-201">Use the scale on the right to measure the Poor % values.</span></span>
  
![불량% 값을 보여 주는 스크린샷](media/29795f71-ca96-4763-a76c-b4bb7c0e5828.png)
  
<span data-ttu-id="2d604-203">막대 위로 마우스를 가져가면 실제 숫자 값을 구할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d604-203">You can also obtain the actual numerical values by hovering the mouse over a bar.</span></span>
  
> [!NOTE]
> <span data-ttu-id="2d604-204">다음 예제는 매우 작은 샘플 데이터 집합에서 가져온 것 이며, 실제 배포에 대해 값이 사실적이 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2d604-204">The following example is from a very small sample data set, and the values aren't realistic for an actual deployment.</span></span> 
  
![마우스를 사용 하 여 데이터에 액세스할 때 표시 되는 스크린샷](media/8724b016-1a50-4d19-b48a-3b1aae4eb895.png)
  
<span data-ttu-id="2d604-206">전체 스트림 볼륨은 계산 된 낮은 백분율이 얼마나 적절 한지 결정 하는 데 중요 한 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="2d604-206">The overall stream volume is an important factor in determining how relevant the calculated Poor percentages are.</span></span> <span data-ttu-id="2d604-207">전체 스트림의 볼륨이 작을수록 낮은 신뢰 값이 신고 된 것으로 보고 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d604-207">The smaller the volume of overall streams, the less reliable the reported Poor percentage values are.</span></span>
  
### <a name="server-client-tab-and-client-client-tabs"></a><span data-ttu-id="2d604-208">서버-클라이언트 탭 및 클라이언트 클라이언트 탭</span><span class="sxs-lookup"><span data-stu-id="2d604-208">Server-Client tab and Client-Client tabs</span></span>

<span data-ttu-id="2d604-209">이러한 두 탭은 끝점 간 시나리오에서 발생 한 스트림에 대 한 추가 세부 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d604-209">These two tabs provide additional details for the streams that took place in their endpoint-to-endpoint scenarios.</span></span> <span data-ttu-id="2d604-210">서버 클라이언트 탭에는 네 개의 축소할 수 있는 섹션이 있으며, 여기에는 미디어 스트림이 흐르는 네 가지 시나리오가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d604-210">The Server-Client tab has four collapsible sections, representing four scenarios under which media streams would flow.</span></span>
  
- <span data-ttu-id="2d604-211">유선 내부</span><span class="sxs-lookup"><span data-stu-id="2d604-211">Wired Inside</span></span>
    
- <span data-ttu-id="2d604-212">유선 외부</span><span class="sxs-lookup"><span data-stu-id="2d604-212">Wired Outside</span></span>
    
- <span data-ttu-id="2d604-213">Wifi 내부</span><span class="sxs-lookup"><span data-stu-id="2d604-213">Wifi Inside</span></span>
    
- <span data-ttu-id="2d604-214">Wifi 외부</span><span class="sxs-lookup"><span data-stu-id="2d604-214">Wifi Outside</span></span>

<span data-ttu-id="2d604-215">마찬가지로, 클라이언트-클라이언트 탭에는 다음과 같은 5 개의 축소 가능 섹션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d604-215">Similarly, the Client-Client tab has five collapsible sections:</span></span>

- <span data-ttu-id="2d604-216">유선 내부 유선 내부</span><span class="sxs-lookup"><span data-stu-id="2d604-216">Wired Inside - Wired Inside</span></span>

- <span data-ttu-id="2d604-217">유선 내부 유선 외부</span><span class="sxs-lookup"><span data-stu-id="2d604-217">Wired Inside - Wired Outside</span></span>

- <span data-ttu-id="2d604-218">유선 외부-유선 외부</span><span class="sxs-lookup"><span data-stu-id="2d604-218">Wired Outside - Wired Outside</span></span>

- <span data-ttu-id="2d604-219">유선 내부-Wifi 내부</span><span class="sxs-lookup"><span data-stu-id="2d604-219">Wired Inside - Wifi Inside</span></span>

- <span data-ttu-id="2d604-220">유선 내장-Wifi 외부</span><span class="sxs-lookup"><span data-stu-id="2d604-220">Wired Inside - Wifi Outside</span></span>
    
    
#### <a name="inside-test"></a><span data-ttu-id="2d604-221">내부 테스트</span><span class="sxs-lookup"><span data-stu-id="2d604-221">Inside Test</span></span>

<span data-ttu-id="2d604-222">처리 하는 동안 CQD 백 엔드는 스트림을 빌드 정보 (있는 경우)를 사용 하 여 *내부* 또는 *외부로* 분류 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d604-222">During processing, the CQD back-end classifies a stream as  *Inside*  or *Outside*  using Building information, if it exists.</span></span> <span data-ttu-id="2d604-223">각 스트림의 끝점은 서브넷 주소와 연결 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d604-223">Endpoints of each stream are associated with a subnet address.</span></span> <span data-ttu-id="2d604-224">서브넷이 업로드 된 빌드 정보에서 InsideCorp로 표시 된 서브넷 목록에 있는 경우 *내부*로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d604-224">If the subnet is in the list of the subnets marked InsideCorp in the uploaded Building information, then it is considered *Inside*.</span></span> <span data-ttu-id="2d604-225">빌드 정보를 아직 업로드 하지 않은 경우 테스트 중에는 항상 스트림이 *바깥쪽*으로 분류 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d604-225">If Building information has not yet been uploaded, then Inside Test will always classify the streams as *Outside*.</span></span> <span data-ttu-id="2d604-226">서버 클라이언트 시나리오 테스트 내부에서는 클라이언트 끝점만 고려 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d604-226">Please note that Inside Test for Server-Client scenario only considers the client endpoint.</span></span> <span data-ttu-id="2d604-227">서버는 항상 사용자의 관점에서 벗어나므로이는 테스트에서 고려 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2d604-227">Because servers are always outside from a user's perspective, this isn't accounted for in the test.</span></span>
  
#### <a name="wired-vs-wifi"></a><span data-ttu-id="2d604-228">유선 및 wifi</span><span class="sxs-lookup"><span data-stu-id="2d604-228">Wired vs. wifi</span></span>

<span data-ttu-id="2d604-229">이름에서 알 수 있듯이이는 클라이언트 연결 유형에 따른 분류 기준입니다.</span><span class="sxs-lookup"><span data-stu-id="2d604-229">As the names indicate, this is a classification criteria based on the type of client connections.</span></span> <span data-ttu-id="2d604-230">마찬가지로, 서버는 항상 유선 이며 계산에 포함 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2d604-230">Again, server is always wired and it isn't included in the calculation.</span></span>
  
> [!NOTE]
> <span data-ttu-id="2d604-231">두 끝점 중 하나가 Wifi 네트워크에 연결 되어 있는 경우 스트림이 제공 되 면 CQD에서 Wifi로 분류 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d604-231">Given a stream, if one of the two endpoints is connected to a Wifi network, then it is classified as Wifi in CQD.</span></span> 
  
## <a name="selecting-product-data-to-see-in-reports"></a><span data-ttu-id="2d604-232">보고서에 표시할 제품 데이터 선택</span><span class="sxs-lookup"><span data-stu-id="2d604-232">Selecting product data to see in reports</span></span>
<a name="BKMKProductFilter"></a>

<span data-ttu-id="2d604-233">요약 및 위치 향상 보고서에서 **제품 필터** 드롭다운을 사용 하 여 모든 제품 데이터, Microsoft 팀 데이터만 표시 하거나 비즈니스용 Skype Online 데이터만 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d604-233">In the Summary and Location Enhanced Reports, you can use the **Product Filter** drop-down to show all product data, only Microsoft Teams data, or only Skype for Business Online data.</span></span>
  
![제품 필터 컨트롤 옵션을 보여 주는 스크린샷](media/206ad818-0f72-4c8e-b25e-3cc8fcfbef05.png)
  
<span data-ttu-id="2d604-235">자세한 보고서에서 **팀** 차원을 사용 하 여 보고서를 정의 하는 과정에서 Microsoft 팀 또는 비즈니스용 Skype Online 데이터에 데이터를 필터링 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d604-235">In Detailed reports, you can use the **Is Teams** dimension to filter the data to Microsoft Teams or Skype for Business Online data as part of defining the report.</span></span>
  
## <a name="upload-tenant-data-information"></a><span data-ttu-id="2d604-236">테 넌 트 데이터 정보 업로드</span><span class="sxs-lookup"><span data-stu-id="2d604-236">Upload Tenant Data information</span></span>
<a name="BKMKTenantDataInformationUpload"></a>

<span data-ttu-id="2d604-237">CQD 요약 보고서 대시보드의 오른쪽 위 모서리에 있는 설정 메뉴에서 **테 넌 트 데이터 업로드** 를 선택 하 여 액세스 하는 **테 넌 트 데이터 업로드** 페이지가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d604-237">The CQD Summary Reports dashboard includes a **Tenant Data Upload** page, accessed by selecting **Tenant Data Upload** from the settings menu in the top-right corner.</span></span> <span data-ttu-id="2d604-238">이 페이지는 관리자가 IP 주소 및 지리 정보 매핑과 각 무선 AP와 MAC 주소 매핑, 끝점을 끝점 만들기/모델/유형 등으로 매핑하는 등 자신의 정보를 업로드 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d604-238">This page is used for admins to upload their own information, such as mapping of IP address and geographical information, mapping each wireless AP and its MAC address, mapping of Endpoint to Endpoint Make/Model/Type, etc.</span></span>
  
![통화 품질 대시보드를 보여주는 스크린샷](media/839c9ab4-0246-46c9-8402-aafd83a0bc63.png)
  
1. <span data-ttu-id="2d604-240">**테 넌 트 데이터 업로드** 페이지에서 드롭다운 메뉴를 사용 하 여 업로드할 데이터 파일 형식을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d604-240">On the **Tenant Data Upload** page, use the drop-down menu to choose a data file type for uploading.</span></span> <span data-ttu-id="2d604-241">파일 데이터 형식은 파일의 콘텐츠를 나타냅니다 (예: "빌드"는 IP 주소와 건물의 매핑을 의미 하 고 다른 지리 정보는 "끝점"은 끝점 이름과 끝점 이름에 대 한 매핑/모델/유형 ...을 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d604-241">The file data type denotes the content of the file (for example, "Building" refers to mapping of IP address and building as well as other geographical information, “Endpoint” refers to mapping of Endpoint Name to Endpoint Make/Model/Type…</span></span> <span data-ttu-id="2d604-242">정보).</span><span class="sxs-lookup"><span data-stu-id="2d604-242">information).</span></span> <span data-ttu-id="2d604-243">현재 cqd.teams.microsoft.com (미리 보기 단계에서는 공식적으로 사용할 수 없음)에 대 한 "빌드" 및 "끝점" 데이터 형식을 업로드 하는 기능이 지원 되며, cqd.lync.com에서는 업로드 "빌딩" 데이터 형식만 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d604-243">Currently we support uploading “Building” and “Endpoint” data types for cqd.teams.microsoft.com (in preview stage and not officially available yet), cqd.lync.com only supports uploading "Building" data type.</span></span> <span data-ttu-id="2d604-244">이후 릴리스에서 추가 되는 데이터 형식은 몇 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d604-244">A few more data types will be added with subsequent releases.</span></span>
    
2. <span data-ttu-id="2d604-245">파일 데이터 형식을 선택한 후 **찾아보기를** 클릭 하 여 데이터 파일을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d604-245">After selecting the file data type, click **Browse** to choose a data file.</span></span>
    
   - <span data-ttu-id="2d604-246">데이터 파일은 tsv (탭으로 구분 된 값) 파일 또는 .csv (쉼표 구분 값) 파일 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d604-246">The data file must be a .tsv (Tab-separated values) file or a .csv (Comma-separated value) file.</span></span> <span data-ttu-id="2d604-247">.Csv 파일을 사용 하는 경우 쉼표를 포함 하는 모든 필드를 따옴표로 둘러싸야 하거나 쉼표를 제거 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d604-247">If using a .csv file, any field that contains a comma must be surrounded by quotes or have the comma removed.</span></span> <span data-ttu-id="2d604-248">예를 들어 건물 이름이 .csv 파일에 있는 경우 "회사"로 입력 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d604-248">For example, if your building name is NY,NY, in the .csv file it should be entered as "NY,NY".</span></span>
    
   - <span data-ttu-id="2d604-249">데이터 파일의 크기는 50MB 보다 커야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d604-249">The data file must be no larger than 50MB in size.</span></span>

   - <span data-ttu-id="2d604-250">Cqd.teams.microsoft.com에 업로드 된 파일에는 쿼리 성능을 빠르게 유지 하기 위해 100만의 행 한도가 확장 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d604-250">Files uploaded to cqd.teams.microsoft.com have an expanded row limit of 1,000,000 in order to keep query performance fast.</span></span> <span data-ttu-id="2d604-251">우리는 cqd.lync.com에도 제한을 부과 하도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d604-251">We may impose that limit on cqd.lync.com as well.</span></span>
    
   - <span data-ttu-id="2d604-252">각 데이터 파일의 경우 파일의 각 열이이 항목의 뒷부분에서 설명 하는 미리 정의 된 데이터 형식과 일치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d604-252">For each data file, each column in the file must match a predefined data type, discussed later in this topic.</span></span>
    
3. <span data-ttu-id="2d604-253">데이터 파일을 선택한 후 **시작 날짜** 를 지정 하 고 필요에 따라 **끝 날짜를 지정**합니다.</span><span class="sxs-lookup"><span data-stu-id="2d604-253">After selecting a data file, specify **Start date** and, optionally, **Specify an end date**.</span></span>
    
4. <span data-ttu-id="2d604-254">**시작 날짜**를 선택한 후 **업로드** 를 선택 하 여 파일을 cqd 서버에 업로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d604-254">After selecting **Start date**, select **Upload** to upload the file to the CQD server.</span></span>
    
    <span data-ttu-id="2d604-255">파일을 업로드 하기 전에 먼저 유효성을 검사 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d604-255">Before the file is uploaded, it is first validated.</span></span> <span data-ttu-id="2d604-256">유효성 검사가 완료 되 면 Azure blob에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d604-256">Once validated, it is stored in an Azure blob.</span></span> <span data-ttu-id="2d604-257">유효성 검사에 실패 하거나 파일이 Azure blob에 저장 되지 않는 경우에는 파일에 대 한 수정을 요청 하는 오류 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d604-257">If validation fails or the file fails to be stored in an Azure blob, an error message is displayed requesting a correction to the file.</span></span> <span data-ttu-id="2d604-258">다음 이미지는 데이터 파일의 열 수가 올바르지 않은 경우 발생 하는 오류를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2d604-258">The following image shows an error occurring when the number of columns in the data file is incorrect.</span></span>
    
     ![업로드 유효성 검사 오류를 보여 주는 스크린샷](media/22716a32-3d3d-4870-983c-46089e8b212a.png)
  
5. <span data-ttu-id="2d604-260">유효성 검사 중에 오류가 발생 하지 않으면 파일 업로드가 성공적으로 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d604-260">If no errors occur during validation, the file upload will succeed.</span></span> <span data-ttu-id="2d604-261">그런 다음 업로드 된 데이터 파일을 해당 페이지의 맨 아래에 있는 현재 테 넌 트에 대해 업로드 된 모든 파일의 전체 목록을 보여 주는 **My 업로드** 테이블에서 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d604-261">You can then see the uploaded data file in the **My uploads** table, which shows the full list of all uploaded files for the current tenant at the bottom of that page.</span></span>
    
    <span data-ttu-id="2d604-262">각 레코드에는 업로드 한 테 넌 트 데이터 파일 (파일 형식, 마지막 업데이트 시간, 기간, 설명, 제거 아이콘, 다운로드 아이콘)이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d604-262">Each record shows one uploaded tenant data file, with file type, last update time, time period, description, a remove icon, and a download icon.</span></span> <span data-ttu-id="2d604-263">파일을 제거 하려면 표에서 휴지통 아이콘을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d604-263">To remove a file, select the trash bin icon in the table.</span></span> <span data-ttu-id="2d604-264">파일을 다운로드 하려면 표의 **다운로드** 열에서 다운로드 아이콘을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d604-264">To download a file, select the download icon in the **Download** column of the table.</span></span>
    
     ![내 업로드 테이블을 보여 주는 스크린샷](media/4168a883-bbea-461a-80b1-42eedf2e7732.png)

6. <span data-ttu-id="2d604-266">여러 빌드 데이터 파일 또는 여러 끝점 데이터 파일을 사용 하도록 선택 하면 일부 보고서의 작업 속도가 느려집니다.</span><span class="sxs-lookup"><span data-stu-id="2d604-266">Note that if you choose to use multiple building data files or multiple endpoint data files, the operation speed of some reports will be slower.</span></span>

### <a name="tenant-data-file-format-and-structure"></a><span data-ttu-id="2d604-267">테 넌 트 데이터 파일 형식 및 구조</span><span class="sxs-lookup"><span data-stu-id="2d604-267">Tenant data file format and structure</span></span>
<span data-ttu-id="2d604-268"><a name="BKMKTenantDataFile"> </a></span><span class="sxs-lookup"><span data-stu-id="2d604-268"></span></span>

### <a name="building-data-file"></a><span data-ttu-id="2d604-269">데이터 파일 작성</span><span class="sxs-lookup"><span data-stu-id="2d604-269">Building data file</span></span>
<span data-ttu-id="2d604-270">CQD는 먼저 네트워크 + NetworkRange 열을 확장 하 여 서브넷 열을 파생 한 다음 서브넷 열을 호출 레코드의 첫 번째 서브넷/두 번째 서브넷 열에 조인 하 여 건물/구/국가/지역을 표시 하는 데이터 파일 작성을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d604-270">CQD uses Building data file by first deriving the Subnet column from expanding the Network+NetworkRange column, then joining the Subnet column to the call record’s First Subnet/Second Subnet column to show Building/City/Country/Region…</span></span> <span data-ttu-id="2d604-271">방법.</span><span class="sxs-lookup"><span data-stu-id="2d604-271">information.</span></span> <span data-ttu-id="2d604-272">업로드 하는 데이터 파일의 형식은 업로드 하기 전에 유효성 검사를 통과 하기 위해 다음을 충족 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d604-272">The format of the data file you upload must meet the following to pass the validation check before uploading.</span></span>
  
- <span data-ttu-id="2d604-273">파일은 각 행에서 열을 탭으로 구분 하는 tsv 파일 이거나 각 열이 쉼표로 구분 된 .csv 파일 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d604-273">The file must be either a .tsv file, which means, in each row, columns are separated by a TAB, or a .csv file with each column separated by a comma.</span></span>
    
- <span data-ttu-id="2d604-274">데이터 파일의 내용에 표 머리글이 포함 되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2d604-274">The content of the data file doesn't include table headers.</span></span> <span data-ttu-id="2d604-275">즉, 데이터 파일의 첫 줄은 "네트워크" 등의 헤더가 아닌 실제 데이터 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d604-275">That means the first line of the data file should be real data, not headers like "Network," etc.</span></span>
    
- <span data-ttu-id="2d604-276">각 열에 대해 데이터 형식은 문자열, 숫자 또는 Bool만 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d604-276">For each column, the data type can only be String, Number, or Bool.</span></span> <span data-ttu-id="2d604-277">Number 인 경우 값은 숫자 값 이어야 합니다. Bool 인 경우에는 값이 0 또는 1 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d604-277">If it is Number, the value must be a numeric value; if it is Bool, the value must be either 0 or 1.</span></span>
    
- <span data-ttu-id="2d604-278">각 열에 대해 데이터 형식이 문자열이 면 데이터는 비어 있을 수 있지만 적절 한 구분 기호 (예: 탭 또는 쉼표)로 구분 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d604-278">For each column, if the data type is string, the data can be empty (but still must be separated by an appropriate delimiter (i.e., a tab or comma).</span></span> <span data-ttu-id="2d604-279">이렇게 하면 해당 필드에 빈 문자열 값이 할당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d604-279">This just assigns that field an empty string value.</span></span>
    
- <span data-ttu-id="2d604-280">각 행에는 14 개의 열이 있고, 각 열은 다음과 같은 데이터 형식 이어야 하 고 열은 다음 표에 나열 된 순서 대로 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d604-280">There must be 14 columns for each row, each column must have the following data type, and the columns must be in the order listed in the following table:</span></span>
    
|<span data-ttu-id="2d604-281">**열 이름**</span><span class="sxs-lookup"><span data-stu-id="2d604-281">**Column Name**</span></span>|<span data-ttu-id="2d604-282">**데이터 형식**</span><span class="sxs-lookup"><span data-stu-id="2d604-282">**Data type**</span></span>|<span data-ttu-id="2d604-283">**예**</span><span class="sxs-lookup"><span data-stu-id="2d604-283">**Example**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="2d604-284">사설망</span><span class="sxs-lookup"><span data-stu-id="2d604-284">Network</span></span>  <br/> |<span data-ttu-id="2d604-285">문자열</span><span class="sxs-lookup"><span data-stu-id="2d604-285">String</span></span>  <br/> |<span data-ttu-id="2d604-286">192.168.1.0</span><span class="sxs-lookup"><span data-stu-id="2d604-286">192.168.1.0</span></span>  <br/> |
|<span data-ttu-id="2d604-287">NetworkName</span><span class="sxs-lookup"><span data-stu-id="2d604-287">NetworkName</span></span>  <br/> |<span data-ttu-id="2d604-288">문자열</span><span class="sxs-lookup"><span data-stu-id="2d604-288">String</span></span>  <br/> |<span data-ttu-id="2d604-289">미국/시애틀/시애틀-해상-1</span><span class="sxs-lookup"><span data-stu-id="2d604-289">USA/Seattle/SEATTLE-SEA-1</span></span>  <br/> |
|<span data-ttu-id="2d604-290">네트워크 범위</span><span class="sxs-lookup"><span data-stu-id="2d604-290">NetworkRange</span></span>  <br/> |<span data-ttu-id="2d604-291">숫자로</span><span class="sxs-lookup"><span data-stu-id="2d604-291">Number</span></span>  <br/> |<span data-ttu-id="2d604-292">kbps</span><span class="sxs-lookup"><span data-stu-id="2d604-292">26</span></span>  <br/> |
|<span data-ttu-id="2d604-293">BuildingName</span><span class="sxs-lookup"><span data-stu-id="2d604-293">BuildingName</span></span>  <br/> |<span data-ttu-id="2d604-294">문자열</span><span class="sxs-lookup"><span data-stu-id="2d604-294">String</span></span>  <br/> |<span data-ttu-id="2d604-295">시애틀-해상-1</span><span class="sxs-lookup"><span data-stu-id="2d604-295">SEATTLE-SEA-1</span></span>  <br/> |
|<span data-ttu-id="2d604-296">소유자 배송 유형</span><span class="sxs-lookup"><span data-stu-id="2d604-296">OwnershipType</span></span>  <br/> |<span data-ttu-id="2d604-297">문자열</span><span class="sxs-lookup"><span data-stu-id="2d604-297">String</span></span>  <br/> |<span data-ttu-id="2d604-298">Contoso.com</span><span class="sxs-lookup"><span data-stu-id="2d604-298">Contoso</span></span>  <br/> |
|<span data-ttu-id="2d604-299">BuildingType</span><span class="sxs-lookup"><span data-stu-id="2d604-299">BuildingType</span></span>  <br/> |<span data-ttu-id="2d604-300">문자열</span><span class="sxs-lookup"><span data-stu-id="2d604-300">String</span></span>  <br/> |<span data-ttu-id="2d604-301">IT 종료</span><span class="sxs-lookup"><span data-stu-id="2d604-301">IT Termination</span></span>  <br/> |
|<span data-ttu-id="2d604-302">BuildingOfficeType</span><span class="sxs-lookup"><span data-stu-id="2d604-302">BuildingOfficeType</span></span>  <br/> |<span data-ttu-id="2d604-303">문자열</span><span class="sxs-lookup"><span data-stu-id="2d604-303">String</span></span>  <br/> |<span data-ttu-id="2d604-304">공정</span><span class="sxs-lookup"><span data-stu-id="2d604-304">Engineering</span></span>  <br/> |
|<span data-ttu-id="2d604-305">곳</span><span class="sxs-lookup"><span data-stu-id="2d604-305">City</span></span>  <br/> |<span data-ttu-id="2d604-306">문자열</span><span class="sxs-lookup"><span data-stu-id="2d604-306">String</span></span>  <br/> |<span data-ttu-id="2d604-307">시애틀</span><span class="sxs-lookup"><span data-stu-id="2d604-307">Seattle</span></span>  <br/> |
|<span data-ttu-id="2d604-308">ZipCode</span><span class="sxs-lookup"><span data-stu-id="2d604-308">ZipCode</span></span>  <br/> |<span data-ttu-id="2d604-309">문자열</span><span class="sxs-lookup"><span data-stu-id="2d604-309">String</span></span>  <br/> |<span data-ttu-id="2d604-310">98001</span><span class="sxs-lookup"><span data-stu-id="2d604-310">98001</span></span>  <br/> |
|<span data-ttu-id="2d604-311">명칭</span><span class="sxs-lookup"><span data-stu-id="2d604-311">Country</span></span>  <br/> |<span data-ttu-id="2d604-312">문자열</span><span class="sxs-lookup"><span data-stu-id="2d604-312">String</span></span>  <br/> |<span data-ttu-id="2d604-313">보세요</span><span class="sxs-lookup"><span data-stu-id="2d604-313">US</span></span>  <br/> |
|<span data-ttu-id="2d604-314">상태</span><span class="sxs-lookup"><span data-stu-id="2d604-314">State</span></span>  <br/> |<span data-ttu-id="2d604-315">문자열</span><span class="sxs-lookup"><span data-stu-id="2d604-315">String</span></span>  <br/> |<span data-ttu-id="2d604-316">WA</span><span class="sxs-lookup"><span data-stu-id="2d604-316">WA</span></span>  <br/> |
|<span data-ttu-id="2d604-317">영역인</span><span class="sxs-lookup"><span data-stu-id="2d604-317">Region</span></span>  <br/> |<span data-ttu-id="2d604-318">문자열</span><span class="sxs-lookup"><span data-stu-id="2d604-318">String</span></span>  <br/> |<span data-ttu-id="2d604-319">MSUS</span><span class="sxs-lookup"><span data-stu-id="2d604-319">MSUS</span></span>  <br/> |
|<span data-ttu-id="2d604-320">InsideCorp</span><span class="sxs-lookup"><span data-stu-id="2d604-320">InsideCorp</span></span>  <br/> |<span data-ttu-id="2d604-321">부울</span><span class="sxs-lookup"><span data-stu-id="2d604-321">Bool</span></span>  <br/> |<span data-ttu-id="2d604-322">raid-1</span><span class="sxs-lookup"><span data-stu-id="2d604-322">1</span></span>  <br/> |
|<span data-ttu-id="2d604-323">ExpressRoute</span><span class="sxs-lookup"><span data-stu-id="2d604-323">ExpressRoute</span></span>  <br/> |<span data-ttu-id="2d604-324">부울</span><span class="sxs-lookup"><span data-stu-id="2d604-324">Bool</span></span>  <br/> |<span data-ttu-id="2d604-325">0</span><span class="sxs-lookup"><span data-stu-id="2d604-325">0</span></span>  <br/> |
   
> [!IMPORTANT]
> <span data-ttu-id="2d604-326">네트워크 범위를 사용 하 여 수퍼 네트 (단일 라우팅 접두사가 있는 여러 서브넷의 조합)를 표현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d604-326">The network range can be used to represent a supernet (combination of several subnets with a single routing prefix).</span></span> <span data-ttu-id="2d604-327">모든 새 건물 업로드가 겹치는 범위에 대해 확인 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d604-327">All new building uploads will be checked for any overlapping ranges.</span></span> <span data-ttu-id="2d604-328">문서 파일을 이전에 업로드 한 경우에는 현재 파일을 다운로드 한 후 다시 업로드 하 여 겹치는 내용을 식별 하 고 문제를 해결 한 후 다시 업로드 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d604-328">If you have previously uploaded a building file, you should download the current file and re-upload it to identify any overlaps and fix the issue before uploading again.</span></span> <span data-ttu-id="2d604-329">이전에 업로드 한 파일의 겹치기로 인해 보고서의 건물에 대해 잘못 된 서브넷 매핑이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d604-329">Any overlap in previously uploaded files may result in the wrong mappings of subnets to buildings in the reports.</span></span> <span data-ttu-id="2d604-330">특정 VPN 구현에서는 서브넷 정보가 정확 하 게 보고 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2d604-330">Certain VPN implementations do not accurately report the subnet information.</span></span> <span data-ttu-id="2d604-331">VPN 서브넷을 건물 파일에 추가할 때 서브넷에 대 한 하나의 항목이 아닌 별도의 32 비트 네트워크로 VPN 서브넷의 각 주소에 대해 개별 항목이 추가 되는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="2d604-331">It is recommended that when adding a VPN subnet to the building file, instead of one entry for the subnet, separate entries are added for each address in the VPN subnet as a separate 32-bit network.</span></span> <span data-ttu-id="2d604-332">각 행은 동일한 빌드 메타 데이터를 가질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d604-332">Each row can have the same building metadata.</span></span> <span data-ttu-id="2d604-333">예를 들어 172.16.18.0/24에 대 한 한 행이 아닌 256 행이 172.16.18.0/32 및 172.16.18.255/32 (포함) 사이에 있는 각 주소에 대해 한 행이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d604-333">For example, instead of one row for 172.16.18.0/24, you should have 256 rows, with one row for each address between 172.16.18.0/32 and 172.16.18.255/32, inclusive.</span></span> 

### <a name="endpoint-data-file"></a><span data-ttu-id="2d604-334">끝점 데이터 파일</span><span class="sxs-lookup"><span data-stu-id="2d604-334">Endpoint data file</span></span>
<span data-ttu-id="2d604-335">CQD는 EndpointName 열을 호출 레코드의 첫 번째 클라이언트 끝점 이름/초 클라이언트 끝점 이름 열에 가입 하 여 끝점 형식/모델/형식 정보를 표시 하는 방식으로 끝점 데이터 파일을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d604-335">CQD uses Endpoint data file by joining its EndpointName column to the call record’s First Client Endpoint Name/Second Client Endpoint Name column to show Endpoint Make/Model/Type information.</span></span> <span data-ttu-id="2d604-336">업로드 하는 데이터 파일의 형식은 업로드 하기 전에 유효성 검사를 통과 하기 위해 다음을 충족 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d604-336">The format of the data file you upload must meet the following to pass the validation check before uploading.</span></span>

- <span data-ttu-id="2d604-337">파일은 각 행에서 열을 탭으로 구분 하는 tsv 파일 이거나 각 열이 쉼표로 구분 된 .csv 파일 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d604-337">The file must be either a .tsv file, which means, in each row, columns are separated by a TAB, or a .csv file with each column separated by a comma.</span></span>

- <span data-ttu-id="2d604-338">데이터 파일의 내용에 표 머리글이 포함 되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2d604-338">The content of the data file doesn't include table headers.</span></span> <span data-ttu-id="2d604-339">즉, 데이터 파일의 첫 줄은 "EndpointName" 등과 같은 헤더가 아닌 실제 데이터 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d604-339">That means the first line of the data file should be real data, not headers like "EndpointName," etc.</span></span>

- <span data-ttu-id="2d604-340">각 열에 대해 데이터 형식에는 문자열만 사용할 수 있으며 최대 허용 길이인 64 자를 넘지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d604-340">For each column, the data type can only be String and it should have no more than 64 chars, which is maximum allowed length.</span></span>

- <span data-ttu-id="2d604-341">각 열에 대해 데이터는 비어 있을 수 있지만 적절 한 구분 기호 (예: 탭 또는 쉼표)로 구분 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d604-341">For each column, the data can be empty (but still must be separated by an appropriate delimiter (i.e., a tab or comma).</span></span> <span data-ttu-id="2d604-342">이렇게 하면 해당 필드에 빈 문자열 값이 할당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d604-342">This just assigns that field an empty string value.</span></span>

- <span data-ttu-id="2d604-343">각 행에 대해 7 개의 열이 있어야 하 고 열은 다음 표에 나열 된 순서 대로 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d604-343">There must be 7 columns for each row and the columns must be in the order listed in the following table.</span></span>

- <span data-ttu-id="2d604-344">EndpointName는 고유 해야 하며, 그렇지 않으면 잘못 된 조인을 초래 하는 중복 행 때문에 업로드가 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d604-344">EndpointName must be unique otherwise upload will fail due to duplicate row as it will cause incorrect joining.</span></span>

-  <span data-ttu-id="2d604-345">EndpointLabel1, EndpointLabel2, EndpointLable3는 사용자가 지정할 수 있는 레이블의 빈 문자열 또는 사용자가 "IT 부서가 2018 노트북", "자산 태그 5678" 등을 사용 하는 것을 선호 합니다. 이유로.</span><span class="sxs-lookup"><span data-stu-id="2d604-345">EndpointLabel1, EndpointLabel2, EndpointLable3 are user customizable labels, they can be empty strings or value users prefer such as “IT Department designated 2018 Laptop”, “Asset Tag 5678” …etc.</span></span>

|<span data-ttu-id="2d604-346">**열 이름**</span><span class="sxs-lookup"><span data-stu-id="2d604-346">**Column Name**</span></span>|<span data-ttu-id="2d604-347">**데이터 형식**</span><span class="sxs-lookup"><span data-stu-id="2d604-347">**Data type**</span></span>|<span data-ttu-id="2d604-348">**예**</span><span class="sxs-lookup"><span data-stu-id="2d604-348">**Example**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="2d604-349">EndpointName</span><span class="sxs-lookup"><span data-stu-id="2d604-349">EndpointName</span></span>  <br/> |<span data-ttu-id="2d604-350">문자열</span><span class="sxs-lookup"><span data-stu-id="2d604-350">String</span></span>  <br/> |<span data-ttu-id="2d604-351">1409W3534</span><span class="sxs-lookup"><span data-stu-id="2d604-351">1409W3534</span></span>  <br/> |
|<span data-ttu-id="2d604-352">EndpointMake</span><span class="sxs-lookup"><span data-stu-id="2d604-352">EndpointMake</span></span>  <br/> |<span data-ttu-id="2d604-353">문자열</span><span class="sxs-lookup"><span data-stu-id="2d604-353">String</span></span>  <br/> |<span data-ttu-id="2d604-354">Fabrikam i n c</span><span class="sxs-lookup"><span data-stu-id="2d604-354">Fabrikam Inc</span></span>  <br/> |
|<span data-ttu-id="2d604-355">EndpointModel</span><span class="sxs-lookup"><span data-stu-id="2d604-355">EndpointModel</span></span>  <br/> |<span data-ttu-id="2d604-356">문자열</span><span class="sxs-lookup"><span data-stu-id="2d604-356">String</span></span>  <br/> |<span data-ttu-id="2d604-357">Fabrikam 모델 123</span><span class="sxs-lookup"><span data-stu-id="2d604-357">Fabrikam Model 123</span></span>  <br/> |
|<span data-ttu-id="2d604-358">EndpointType</span><span class="sxs-lookup"><span data-stu-id="2d604-358">EndpointType</span></span>   <br/> |<span data-ttu-id="2d604-359">문자열</span><span class="sxs-lookup"><span data-stu-id="2d604-359">String</span></span>  <br/> |<span data-ttu-id="2d604-360">컴퓨터가</span><span class="sxs-lookup"><span data-stu-id="2d604-360">Laptop</span></span>  <br/> |
|<span data-ttu-id="2d604-361">EndpointLabel1</span><span class="sxs-lookup"><span data-stu-id="2d604-361">EndpointLabel1</span></span>  <br/> |<span data-ttu-id="2d604-362">문자열</span><span class="sxs-lookup"><span data-stu-id="2d604-362">String</span></span>  <br/> |<span data-ttu-id="2d604-363">2018 노트북 지정</span><span class="sxs-lookup"><span data-stu-id="2d604-363">IT designated 2018 Laptop</span></span>  <br/> |
|<span data-ttu-id="2d604-364">EndpointLabel2</span><span class="sxs-lookup"><span data-stu-id="2d604-364">EndpointLabel2</span></span>  <br/> |<span data-ttu-id="2d604-365">문자열</span><span class="sxs-lookup"><span data-stu-id="2d604-365">String</span></span>  <br/> |<span data-ttu-id="2d604-366">자산 태그 5678</span><span class="sxs-lookup"><span data-stu-id="2d604-366">Asset Tag 5678</span></span>  <br/> |
|<span data-ttu-id="2d604-367">EndpointLabel3</span><span class="sxs-lookup"><span data-stu-id="2d604-367">EndpointLabel3</span></span>  <br/> |<span data-ttu-id="2d604-368">문자열</span><span class="sxs-lookup"><span data-stu-id="2d604-368">String</span></span>  <br/> |<span data-ttu-id="2d604-369">2018 구입</span><span class="sxs-lookup"><span data-stu-id="2d604-369">Purchase 2018</span></span>   <br/> |


## <a name="selecting-media-type-in-detailed-reports"></a><span data-ttu-id="2d604-370">자세한 보고서에서 미디어 유형 선택</span><span class="sxs-lookup"><span data-stu-id="2d604-370">Selecting media type in detailed reports</span></span>
<a name="BKMKMediaType"></a>

<span data-ttu-id="2d604-371">자세한 보고서는 오디오, 비디오, 응용 프로그램 공유 및 비디오 기반 화면 공유 미디어 형식에 대 한 품질 및 미디어 신뢰성을 확인 하는 것을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d604-371">The detailed reports support looking at quality and media reliability for audio, video, application sharing, and video-based screen-sharing media types.</span></span> <span data-ttu-id="2d604-372">단일 미디어 유형과 관련 된 차원, 측정값 및 필터에는 "오디오", "비디오", "AppSharing" 또는 접두사로 "VBSS"가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d604-372">Dimensions, measures, and filters that are specific to a single media type have "Audio", "Video", "AppSharing", or "VBSS" as a prefix.</span></span>
  
![통화 품질 대시보드 크기를 보여주는 스크린샷](media/ae132202-d6dc-43bd-b8b3-ea9c24c519e8.png)
  
<span data-ttu-id="2d604-374">단일 미디어 유형의 차원과 측정값을 보려면 새 MediaType 차원 및 필터가 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d604-374">If you want to view the dimensions and measures for a single media type, the new MediaType dimension and filter may be required.</span></span> <span data-ttu-id="2d604-375">예를 들어 여러 미디어 유형에 서 총 세션 수를 보여 주는 보고서를 만들려면 MediaType dimension을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d604-375">For example, to have a report that shows the total session counts across different media types, include the MediaType dimension.</span></span>
  
![통화 품질 대시보드의 총 스트림 수를 보여주는 스크린샷](media/21d5d0dc-2321-415e-8ef2-cea06165601c.png)

## <a name="related-topics"></a><span data-ttu-id="2d604-377">관련 항목</span><span class="sxs-lookup"><span data-stu-id="2d604-377">Related topics</span></span>
[<span data-ttu-id="2d604-378">비즈니스용 Skype 통화 분석 설정</span><span class="sxs-lookup"><span data-stu-id="2d604-378">Set up Skype for Business Call Analytics</span></span>](set-up-call-analytics.md)

[<span data-ttu-id="2d604-379">통화 분석을 사용 하 여 통화 품질 저하 문제 해결</span><span class="sxs-lookup"><span data-stu-id="2d604-379">Use Call Analytics to troubleshoot poor  call quality</span></span>](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[<span data-ttu-id="2d604-380">통화 분석 및 통화 품질 대시보드</span><span class="sxs-lookup"><span data-stu-id="2d604-380">Call Analytics and Call Quality Dashboard</span></span>](difference-between-call-analytics-and-call-quality-dashboard.md)

  
 
