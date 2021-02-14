---
title: CQD(통화 품질 대시보드)란?
ms.author: serdars
author: SerdarSoysal
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
description: CQD(통화 품질 대시보드)에 대해 알아보고 이를 사용하여 Microsoft Teams에서 모임 및 통화 품질에 대한 보고서를 보는 방법을 배워 봐야 합니다.
ms.openlocfilehash: 9ba1956533887314a9ffa7ad994cbb4c81ffe103
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/06/2020
ms.locfileid: "46583487"
---
# <a name="what-is-call-quality-dashboard-cqd"></a><span data-ttu-id="c77ea-103">CQD(통화 품질 대시보드)란?</span><span class="sxs-lookup"><span data-stu-id="c77ea-103">What is Call Quality Dashboard (CQD)?</span></span>

<span data-ttu-id="c77ea-104">Microsoft CQD(통화 품질 대시보드) - Microsoft Teams, 비즈니스용 Skype Online 및 [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) 비즈니스용 Skype Server 2019에 대한 전체 수준에서 통화 및 모임 품질을 보여줍니다. </span><span class="sxs-lookup"><span data-stu-id="c77ea-104">The Microsoft Call Quality Dashboard (CQD) - [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) - shows call and meeting quality, at an **org-wide level**, for Microsoft Teams, Skype for Business Online, and Skype for Business Server 2019.</span></span> 

  
<span data-ttu-id="c77ea-105">최신 버전의 CQD는 거의 실시간에 [가까운(NRT)](CQD-data-and-reports.md)데이터 피드를 제공합니다. 즉, 통화가 끝나고 30분 이내에 CQD에서 호출 레코드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c77ea-105">The latest version of CQD features a [near-real-time (NRT) data feed](CQD-data-and-reports.md), which means that call records are available in CQD within 30 minutes of the end of a call.</span></span>

<span data-ttu-id="c77ea-106">CQD에 [EUII(최종](CQD-data-and-reports.md#euii-data)사용자 식별 정보) 데이터가 포함되어 있는 경우 [Microsoft 365 전체에서 EUII와](https://docs.microsoft.com/office365/Enterprise/office-365-data-retention-deletion-and-destruction-overview)동일한 방식으로 관리됩니다.</span><span class="sxs-lookup"><span data-stu-id="c77ea-106">Wherever CQD includes [end-user identifiable information (EUII) data](CQD-data-and-reports.md#euii-data), it's managed in the same way as [EUII throughout Microsoft 365](https://docs.microsoft.com/office365/Enterprise/office-365-data-retention-deletion-and-destruction-overview).</span></span>

<span data-ttu-id="c77ea-107">CQD는 Teams 관리자, 비즈니스용 Skype 관리자 및 네트워크 엔지니어가 전체적인 수준에서 통화 및 모임 품질을 모니터링할 수 있도록 디자인됩니다.</span><span class="sxs-lookup"><span data-stu-id="c77ea-107">CQD is designed to help Teams admins, Skype for Business admins, and network engineers monitor call and meeting quality at an org-wide level.</span></span> <span data-ttu-id="c77ea-108">CQD를 사용하여 성능을 향상하도록 네트워크를 최적화할 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="c77ea-108">You'll use CQD to help you **optimize your network** to drive performance quality.</span></span> <span data-ttu-id="c77ea-109">특정 사용자에 대한 통화 및 모임 정보를 살펴봐야 하는 경우 사용자별 통화 분석과 함께 CQD 데이터를 [사용하세요.](use-call-analytics-to-troubleshoot-poor-call-quality.md)</span><span class="sxs-lookup"><span data-stu-id="c77ea-109">When you need to look into call and meeting information for a **specific user**, use CQD data in conjunction with per-user [call analytics](use-call-analytics-to-troubleshoot-poor-call-quality.md).</span></span>

<span data-ttu-id="c77ea-110">예를 들어 CQD를 사용하면 사용자당 호출 분석을 사용하여 관찰한 사용자의 낮은 통화 품질이 다른 많은 사용자에게도 영향을 주는 네트워크 문제 때문인지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c77ea-110">For example, using CQD, you can determine that a user's poor call quality (which you observed using per-user call analytics) is due to a network issue that also affects many other users.</span></span> <span data-ttu-id="c77ea-111">CQD는 개별 통화 환경과 Teams 또는 비즈니스용 Skype를 사용하여 진행된 전체 통화 품질을 캡처합니다.</span><span class="sxs-lookup"><span data-stu-id="c77ea-111">CQD captures both the individual call experience and the overall quality of calls made using Teams or Skype for Business.</span></span> <span data-ttu-id="c77ea-112">CQD를 사용할 경우 전체 패턴이 명백해질 수 있으므로 네트워크 엔지니어는 통화 품질에 대한 정보를 평가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c77ea-112">With CQD, overall patterns may become apparent, so network engineers can make informed assessments of call quality.</span></span> <span data-ttu-id="c77ea-113">CQD는 전체 통화 품질, 서버-클라이언트 스트림, 클라이언트-클라이언트 스트림 및 음성 품질 SLA에 대한 인사이트를 제공하는 통화 품질 메트릭 보고서를 [제공합니다.](https://go.microsoft.com/fwlink/p/?linkid=846252)</span><span class="sxs-lookup"><span data-stu-id="c77ea-113">CQD provides reports of call quality metrics that give you insight into overall call quality, server-client streams, client-client streams, and voice quality [SLA](https://go.microsoft.com/fwlink/p/?linkid=846252).</span></span> 
  
![통화 품질 대시보드 스크린샷](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image3.png)

<span data-ttu-id="c77ea-115">CQD에서는 사용자 건물 내에서 통화 품질 및 안정성을 분석하기 위해 Location-Enhanced 보고서를 사용할 수 있는 건물 및 엔드포인트 정보를 업로드하는 것이 가장 권장됩니다.</span><span class="sxs-lookup"><span data-stu-id="c77ea-115">In CQD, we encourage you to upload building and endpoint information, which lets you use Location-Enhanced Reports to analyze call quality and reliability within a user's building.</span></span> <span data-ttu-id="c77ea-116">데이터를 평가하여 문제가 단일 사용자에게 격리되어 있는지 또는 더 큰 사용자 세그먼트에 영향을 미치는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c77ea-116">The data can be assessed to determine if the problem is isolated to a single user or affects a larger segment of users.</span></span> <span data-ttu-id="c77ea-117">CQD에서 건물 또는 엔드포인트별 보기를 켜기 [](CQD-upload-tenant-building-data.md) 위해 관리자는 CQD 테넌트 데이터 업로드 페이지에서 건물 또는 엔드포인트 정보를 **업로드해야** 합니다.</span><span class="sxs-lookup"><span data-stu-id="c77ea-117">To turn on building or endpoint-specific views in CQD, an admin must [upload building or endpoint information](CQD-upload-tenant-building-data.md) on the CQD **Tenant Data Upload** page.</span></span>

![통화 품질 대시보드의 Location-Enhanced 스크린샷.](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image4.png)

<span data-ttu-id="c77ea-119">Teams에서 서비스 [](quality-of-experience-review-guide.md) 품질 관리를 담당하는 Teams 관리자 또는 지원 엔지니어를 위한 심층 지침을 제공하는 통화 및 모임 품질 관리 문서를 놓치지 마세요.</span><span class="sxs-lookup"><span data-stu-id="c77ea-119">Don't miss our [Manage call and meeting quality](quality-of-experience-review-guide.md) article, which offers in-depth guidance for the Teams admin or support engineer responsible for managing service quality in Teams.</span></span>

## <a name="older-version-of-cqd-cqdlynccom"></a><span data-ttu-id="c77ea-120">이전 버전의 CQD(CQD.lync.com)</span><span class="sxs-lookup"><span data-stu-id="c77ea-120">Older version of CQD (CQD.lync.com)</span></span>

<span data-ttu-id="c77ea-121">CQD의 현재 버전(이전 버전의 CQD(.)을 https://CQD.Teams.microsoft.com) https://CQD.lync.com) 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="c77ea-121">The current version of CQD (https://CQD.Teams.microsoft.com) is replacing the older version of CQD (https://CQD.lync.com).</span></span> <span data-ttu-id="c77ea-122">비즈니스용 Skype 관리 CQD.lync.com 사용할 수 있지만 2020년 7월 1일 현재 CQD의 데이터를 사용하고 있습니다. Teams.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="c77ea-122">You can still use CQD.lync.com (available from the Skype for Business admin center), but as of July 1, 2020, it's using the data from CQD.Teams.microsoft.com.</span></span> <span data-ttu-id="c77ea-123">CQD로 이동해야 CQD.lync.com 액세스 권한을 곧 해제할 예정입니다. Teams.microsoft.com 아직 수행하지 않은 경우 다시 시작해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c77ea-123">We'll turn off access to CQD.lync.com soon, so you should move to CQD.Teams.microsoft.com if you haven't already done so.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c77ea-124">2020년 7월 1일을 기점으로 이전 CQD(이전 CQD)에서 건물 또는 쿼리 데이터를 더 이상 보거나 수정할 수 CQD.lync.com.</span><span class="sxs-lookup"><span data-stu-id="c77ea-124">As of July 1, 2020, you can no longer view or modify your building or query data from the old CQD (CQD.lync.com).</span></span> <span data-ttu-id="c77ea-125">이 데이터를 아직 마이그레이션하지 않은 경우 CQD.lync.com 필요한 경우 지원 티켓을 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="c77ea-125">If you haven't already migrated this data from CQD.lync.com and still need it, log a support ticket.</span></span>

## <a name="use-power-bi-to-analyze-cqd-data"></a><span data-ttu-id="c77ea-126">Power BI를 사용하여 CQD 데이터 분석</span><span class="sxs-lookup"><span data-stu-id="c77ea-126">Use Power BI to analyze CQD data</span></span>

<span data-ttu-id="c77ea-127">2020년 1월의 새로운 사항: [CQD용 Power BI 쿼리 템플릿을 다운로드합니다.](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="c77ea-127">New in January 2020: [Download Power BI query templates for CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).</span></span> <span data-ttu-id="c77ea-128">CQD 데이터를 분석하고 보고하는 데 사용할 수 있는 사용자 지정 가능한 Power BI 템플릿</span><span class="sxs-lookup"><span data-stu-id="c77ea-128">Customizable Power BI templates you can use to analyze and report your CQD data.</span></span>

<span data-ttu-id="c77ea-129">Power [BI를 사용하여 CQD 데이터를](CQD-Power-BI-query-templates.md) 분석하여 자세히 알아보는 방법을 읽어 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="c77ea-129">Read [Use Power BI to analyze CQD data](CQD-Power-BI-query-templates.md) to learn more.</span></span>



## <a name="related-topics"></a><span data-ttu-id="c77ea-130">관련 항목</span><span class="sxs-lookup"><span data-stu-id="c77ea-130">Related topics</span></span>

[<span data-ttu-id="c77ea-131">Teams의 통화 품질 개선 및 모니터링</span><span class="sxs-lookup"><span data-stu-id="c77ea-131">Improve and monitor call quality for Teams</span></span>](monitor-call-quality-qos.md)

[<span data-ttu-id="c77ea-132">CQD(통화 품질 대시보드) 설정</span><span class="sxs-lookup"><span data-stu-id="c77ea-132">Set up Call Quality Dashboard (CQD)</span></span>](turning-on-and-using-call-quality-dashboard.md)

[<span data-ttu-id="c77ea-133">테넌트 업로드 및 데이터 구축</span><span class="sxs-lookup"><span data-stu-id="c77ea-133">Upload tenant and building data</span></span>](CQD-upload-tenant-building-data.md)

[<span data-ttu-id="c77ea-134">CQD 데이터 및 보고서</span><span class="sxs-lookup"><span data-stu-id="c77ea-134">CQD data and reports</span></span>](CQD-data-and-reports.md)

[<span data-ttu-id="c77ea-135">CQD를 사용하여 통화 및 모임 품질 관리</span><span class="sxs-lookup"><span data-stu-id="c77ea-135">Use CQD to manage call and meeting quality</span></span>](quality-of-experience-review-guide.md)

[<span data-ttu-id="c77ea-136">CQD에서 사용할 수 있는 차원 및 측정값</span><span class="sxs-lookup"><span data-stu-id="c77ea-136">Dimensions and measures available in CQD</span></span>](dimensions-and-measures-available-in-call-quality-dashboard.md)

[<span data-ttu-id="c77ea-137">CQD의 스트림 분류</span><span class="sxs-lookup"><span data-stu-id="c77ea-137">Stream Classification in CQD</span></span>](stream-classification-in-call-quality-dashboard.md)

[<span data-ttu-id="c77ea-138">Power BI를 사용하여 CQD 데이터 분석</span><span class="sxs-lookup"><span data-stu-id="c77ea-138">Use Power BI to analyze CQD data</span></span>](CQD-Power-BI-query-templates.md)


[<span data-ttu-id="c77ea-139">Teams 문제 해결</span><span class="sxs-lookup"><span data-stu-id="c77ea-139">Teams Troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)