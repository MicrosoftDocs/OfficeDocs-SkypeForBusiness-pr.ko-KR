---
title: CQD (통화 품질 대시보드) 란?
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, siunies, gageames
ms.topic: article
ms.assetid: 553fa13c-92d2-4d5c-a3d5-41a073cb047c
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Reporting
- ms.lync.lac.ToolsCallQualityDashboard
- seo-marvel-apr2020
description: 통화 품질 대시보드 (CQD) 및이를 사용 하 여 Microsoft 팀의 모임 및 통화 품질에 대 한 보고서를 확인 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: b7830d60139991b7ccc18679af798c74430e8ed1
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/09/2020
ms.locfileid: "45088246"
---
# <a name="what-is-call-quality-dashboard-cqd"></a><span data-ttu-id="5beed-103">CQD (통화 품질 대시보드) 란?</span><span class="sxs-lookup"><span data-stu-id="5beed-103">What is Call Quality Dashboard (CQD)?</span></span>

<span data-ttu-id="5beed-104">Microsoft 통화 품질 대시보드 (CQD)는 [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) **조직 전체 수준**, Microsoft 팀의 skype Online, 비즈니스용 skype 서버 2019 등의 통화 및 모임 품질이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5beed-104">The Microsoft Call Quality Dashboard (CQD) - [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) - shows call and meeting quality, at an **org-wide level**, for Microsoft Teams, Skype for Business Online, and Skype for Business Server 2019.</span></span> 

  
<span data-ttu-id="5beed-105">최신 버전의 CQD는 [실시간 (NRT) 데이터 피드](CQD-data-and-reports.md)기능을 의미 하며,이는 통화를 종료 한 30 분 내에 CQD에서 통화 기록을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5beed-105">The latest version of CQD features a [near-real-time (NRT) data feed](CQD-data-and-reports.md), which means that call records are available in CQD within 30 minutes of the end of a call.</span></span>

<span data-ttu-id="5beed-106">모든 CQD에는 [EUII (최종 사용자 식별 가능 정보) 데이터가](CQD-data-and-reports.md#euii-data)포함 되며, [Microsoft 365의 EUII](https://docs.microsoft.com/office365/Enterprise/office-365-data-retention-deletion-and-destruction-overview)와 같은 방식으로 관리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5beed-106">Wherever CQD includes [end-user identifiable information (EUII) data](CQD-data-and-reports.md#euii-data), it's managed in the same way as [EUII throughout Microsoft 365](https://docs.microsoft.com/office365/Enterprise/office-365-data-retention-deletion-and-destruction-overview).</span></span>

<span data-ttu-id="5beed-107">CQD는 팀 관리자, 비즈니스용 Skype 관리자, 네트워크 엔지니어가 조직 차원의 수준에서 통화와 모임 품질을 모니터링 하도록 설계 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="5beed-107">CQD is designed to help Teams admins, Skype for Business admins, and network engineers monitor call and meeting quality at an org-wide level.</span></span> <span data-ttu-id="5beed-108">CQD를 사용 하 여 성능 품질을 드라이브에 맞게 **네트워크를 최적화할** 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5beed-108">You'll use CQD to help you **optimize your network** to drive performance quality.</span></span> <span data-ttu-id="5beed-109">**특정 사용자**에 대 한 통화 및 모임 정보를 확인 해야 하는 경우 CQD 데이터를 사용자별 [통화 분석](use-call-analytics-to-troubleshoot-poor-call-quality.md)을 통해 함께 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5beed-109">When you need to look into call and meeting information for a **specific user**, use CQD data in conjunction with per-user [call analytics](use-call-analytics-to-troubleshoot-poor-call-quality.md).</span></span>

<span data-ttu-id="5beed-110">예를 들어 CQD를 사용 하는 경우 사용자의 잘못 된 통화 품질 (사용자 단위 통화 분석 사용)이 다른 많은 사용자에 게 영향을 미치는 네트워크 문제로 인해 발생 하는 것을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5beed-110">For example, using CQD, you can determine that a user's poor call quality (which you observed using per-user call analytics) is due to a network issue that also affects many other users.</span></span> <span data-ttu-id="5beed-111">CQD는 개별 통화 환경과 팀 또는 비즈니스용 Skype를 사용 하 여 생성 되는 전체 통화 품질을 모두 캡처합니다.</span><span class="sxs-lookup"><span data-stu-id="5beed-111">CQD captures both the individual call experience and the overall quality of calls made using Teams or Skype for Business.</span></span> <span data-ttu-id="5beed-112">CQD를 사용 하면 전체 패턴이 명확 하 게 나타날 수 있으므로 네트워크 엔지니어가 통화 품질 평가를 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5beed-112">With CQD, overall patterns may become apparent, so network engineers can make informed assessments of call quality.</span></span> <span data-ttu-id="5beed-113">CQD는 전체 통화 품질, 서버 클라이언트 스트림, 클라이언트-클라이언트 스트림, 음성 품질 [SLA](https://go.microsoft.com/fwlink/p/?linkid=846252)에 대 한 정보를 제공 하는 통화 품질 메트릭의 보고서를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="5beed-113">CQD provides reports of call quality metrics that give you insight into overall call quality, server-client streams, client-client streams, and voice quality [SLA](https://go.microsoft.com/fwlink/p/?linkid=846252).</span></span> 
  
![통화 품질 대시보드의 스크린샷](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image3.png)

<span data-ttu-id="5beed-115">CQD에는 빌드 및 끝점 정보를 업로드 하는 것이 좋습니다 .이를 통해 위치 향상 보고서를 사용 하 여 사용자의 빌드 내에서 통화 품질과 안정성을 분석할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5beed-115">In CQD, we encourage you to upload building and endpoint information, which lets you use Location-Enhanced Reports to analyze call quality and reliability within a user's building.</span></span> <span data-ttu-id="5beed-116">데이터를 평가 하 여 문제가 단일 사용자에 게 격리 되었는지 또는 대규모 사용자 세그먼트에 영향을 미치는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5beed-116">The data can be assessed to determine if the problem is isolated to a single user or affects a larger segment of users.</span></span> <span data-ttu-id="5beed-117">CQD에서 빌드 또는 끝점 관련 보기를 설정 하려면 관리자가 CQD **테 넌 트 데이터 업로드** 페이지에서 [빌드 또는 끝점 정보를 업로드](CQD-upload-tenant-building-data.md) 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5beed-117">To turn on building or endpoint-specific views in CQD, an admin must [upload building or endpoint information](CQD-upload-tenant-building-data.md) on the CQD **Tenant Data Upload** page.</span></span>

![통화 품질 대시보드의 위치 향상 보고서 스크린샷.](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image4.png)

<span data-ttu-id="5beed-119">팀에서 서비스 품질 관리를 담당 하는 팀 관리자 또는 지원 엔지니어에 대 한 자세한 지침을 제공 하는 [관리 통화 및 모임 품질](quality-of-experience-review-guide.md) 문서를 놓치지 마세요.</span><span class="sxs-lookup"><span data-stu-id="5beed-119">Don't miss our [Manage call and meeting quality](quality-of-experience-review-guide.md) article, which offers in-depth guidance for the Teams admin or support engineer responsible for managing service quality in Teams.</span></span>

## <a name="older-version-of-cqd-cqdlynccom"></a><span data-ttu-id="5beed-120">이전 버전의 CQD (CQD.lync.com)</span><span class="sxs-lookup"><span data-stu-id="5beed-120">Older version of CQD (CQD.lync.com)</span></span>

<span data-ttu-id="5beed-121">현재 버전의 CQD (의 https://CQD.Teams.microsoft.com) 이전 버전을 대체 하 고 https://CQD.lync.com) 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5beed-121">The current version of CQD (https://CQD.Teams.microsoft.com) is replacing the older version of CQD (https://CQD.lync.com).</span></span> <span data-ttu-id="5beed-122">CQD.lync.com (비즈니스용 Skype 관리 센터에서 사용 가능)를 계속 사용할 수 있지만, 2020 년 7 월 1 일부 터는 CQD의 데이터를 사용 하 고 있습니다. Teams.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="5beed-122">You can still use CQD.lync.com (available from the Skype for Business admin center), but as of July 1, 2020, it's using the data from CQD.Teams.microsoft.com.</span></span> <span data-ttu-id="5beed-123">CQD.lync.com에 대 한 액세스가 곧 해제 되므로 CQD로 이동 해야 합니다. 아직 수행 하지 않은 경우 Teams.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="5beed-123">We'll turn off access to CQD.lync.com soon, so you should move to CQD.Teams.microsoft.com if you haven't already done so.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5beed-124">2020 년 7 월 1 일 현재 이전 CQD (CQD.lync.com)에서 더 이상 건물 또는 쿼리 데이터를 보거나 수정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5beed-124">As of July 1, 2020, you can no longer view or modify your building or query data from the old CQD (CQD.lync.com).</span></span> <span data-ttu-id="5beed-125">CQD.lync.com에서이 데이터를 아직 마이그레이션하지 않은 경우에도 지원 티켓을 기록 합니다.</span><span class="sxs-lookup"><span data-stu-id="5beed-125">If you haven't already migrated this data from CQD.lync.com and still need it, log a support ticket.</span></span>

## <a name="use-power-bi-to-analyze-cqd-data"></a><span data-ttu-id="5beed-126">Power BI를 사용 하 여 CQD 데이터 분석</span><span class="sxs-lookup"><span data-stu-id="5beed-126">Use Power BI to analyze CQD data</span></span>

<span data-ttu-id="5beed-127">T e 2020의 새로운 [기능: CQD 용 POWER BI 쿼리 서식 파일을 다운로드](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)합니다.</span><span class="sxs-lookup"><span data-stu-id="5beed-127">New in January 2020: [Download Power BI query templates for CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).</span></span> <span data-ttu-id="5beed-128">CQD 데이터를 분석 하 고 보고 하는 데 사용할 수 있는 사용자 지정 가능한 Power BI 서식 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="5beed-128">Customizable Power BI templates you can use to analyze and report your CQD data.</span></span>

<span data-ttu-id="5beed-129">자세한 내용은 [POWER BI를 사용 하 여 CQD 데이터 분석을](CQD-Power-BI-query-templates.md) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5beed-129">Read [Use Power BI to analyze CQD data](CQD-Power-BI-query-templates.md) to learn more.</span></span>



## <a name="related-topics"></a><span data-ttu-id="5beed-130">관련 항목</span><span class="sxs-lookup"><span data-stu-id="5beed-130">Related topics</span></span>

[<span data-ttu-id="5beed-131">팀의 통화 품질 개선 및 모니터링</span><span class="sxs-lookup"><span data-stu-id="5beed-131">Improve and monitor call quality for Teams</span></span>](monitor-call-quality-qos.md)

[<span data-ttu-id="5beed-132">CQD (통화 품질 대시보드) 설정</span><span class="sxs-lookup"><span data-stu-id="5beed-132">Set up Call Quality Dashboard (CQD)</span></span>](turning-on-and-using-call-quality-dashboard.md)

[<span data-ttu-id="5beed-133">테 넌 트 업로드 및 데이터 빌드</span><span class="sxs-lookup"><span data-stu-id="5beed-133">Upload tenant and building data</span></span>](CQD-upload-tenant-building-data.md)

[<span data-ttu-id="5beed-134">CQD 데이터 및 보고서</span><span class="sxs-lookup"><span data-stu-id="5beed-134">CQD data and reports</span></span>](CQD-data-and-reports.md)

[<span data-ttu-id="5beed-135">CQD를 사용 하 여 통화 및 모임 품질 관리</span><span class="sxs-lookup"><span data-stu-id="5beed-135">Use CQD to manage call and meeting quality</span></span>](quality-of-experience-review-guide.md)

[<span data-ttu-id="5beed-136">CQD에서 사용할 수 있는 차원과 측정값</span><span class="sxs-lookup"><span data-stu-id="5beed-136">Dimensions and measures available in CQD</span></span>](dimensions-and-measures-available-in-call-quality-dashboard.md)

[<span data-ttu-id="5beed-137">CQD의 스트림 분류</span><span class="sxs-lookup"><span data-stu-id="5beed-137">Stream Classification in CQD</span></span>](stream-classification-in-call-quality-dashboard.md)

[<span data-ttu-id="5beed-138">Power BI를 사용 하 여 CQD 데이터 분석</span><span class="sxs-lookup"><span data-stu-id="5beed-138">Use Power BI to analyze CQD data</span></span>](CQD-Power-BI-query-templates.md)


[<span data-ttu-id="5beed-139">Teams 문제 해결</span><span class="sxs-lookup"><span data-stu-id="5beed-139">Teams Troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)