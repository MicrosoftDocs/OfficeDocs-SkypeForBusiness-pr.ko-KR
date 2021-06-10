---
title: Microsoft Teams 앱 사용 보고서
author: SerdarSoysal
ms.author: serdars
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: v-quhur
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
description: 관리 센터에서 Teams 앱 사용 보고서를 사용하는 Microsoft Teams 대해 자세히 알아보습니다.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 29e51e91cdc42000350a48dd0d83225e7791aea6
ms.sourcegitcommit: d62e6cefceebe481eb207c59872f1aa67f0fc528
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2021
ms.locfileid: "50460598"
---
# <a name="microsoft-teams-app-usage-report"></a><span data-ttu-id="1e21b-103">Microsoft Teams 앱 사용 보고서</span><span class="sxs-lookup"><span data-stu-id="1e21b-103">Microsoft Teams app usage report</span></span>

<span data-ttu-id="1e21b-104">Teams 관리 센터의 Microsoft Teams 앱 사용 현황 보고서는 사용자가 Teams.</span><span class="sxs-lookup"><span data-stu-id="1e21b-104">The Teams app usage report in the Microsoft Teams admin center provides you with information about which apps users are using in Teams.</span></span>  

## <a name="view-the-app-usage-report"></a><span data-ttu-id="1e21b-105">앱 사용 보고서 보기</span><span class="sxs-lookup"><span data-stu-id="1e21b-105">View the App Usage report</span></span>

1.  <span data-ttu-id="1e21b-106">관리 센터의 왼쪽 탐색에서 분석 & <https://admin.teams.microsoft.com> **보고서** \> **를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="1e21b-106">In the left navigation of the admin center at <https://admin.teams.microsoft.com>, click **Analytics & reports** \> **Usage reports**.</span></span> <span data-ttu-id="1e21b-107">보고서 보기 **탭의** **보고서에서** **앱 사용 을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="1e21b-107">On the **View reports** tab, under **Report**, select **Apps Usage**.</span></span>

     :::image type="content" source="media/app-usage-report1.png" alt-text="사용 현황 보고서 메뉴 항목 스크린샷":::

2.  <span data-ttu-id="1e21b-109">**날짜 범위에서** 범위를 선택한 다음 보고서 실행 **을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="1e21b-109">Under **Date range**, select a range, and then click **Run report**.</span></span>

      :::image type="content" source="media/app-usage-report2.png" alt-text="앱 사용 보고서 스크린샷":::

## <a name="interpret-the-report"></a><span data-ttu-id="1e21b-111">보고서 해석</span><span class="sxs-lookup"><span data-stu-id="1e21b-111">Interpret the report</span></span>

|<span data-ttu-id="1e21b-112">콜아웃</span><span class="sxs-lookup"><span data-stu-id="1e21b-112">Callout</span></span> |<span data-ttu-id="1e21b-113">설명</span><span class="sxs-lookup"><span data-stu-id="1e21b-113">Description</span></span>  |
|--------|-------------|
|<span data-ttu-id="1e21b-114">**1**</span><span class="sxs-lookup"><span data-stu-id="1e21b-114">**1**</span></span>   |<span data-ttu-id="1e21b-115">앱 Teams 최근 7일, 30일 또는 90일 동안의 추세를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e21b-115">The Teams Apps usage report can be viewed for trends over the last 7, 30 or 90 days.</span></span> |
|<span data-ttu-id="1e21b-116">**2**</span><span class="sxs-lookup"><span data-stu-id="1e21b-116">**2**</span></span>   |<span data-ttu-id="1e21b-117">각 보고서에는 보고서가 생성된 날짜가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e21b-117">Each report has a date for when the report was generated.</span></span> <span data-ttu-id="1e21b-118">보고서는 일반적으로 앱이 열리기 전의 24시간 대기 시간을 반영합니다.</span><span class="sxs-lookup"><span data-stu-id="1e21b-118">The reports usually reflect a 24-hour latency from the time an app was opened.</span></span> <br><br>![날짜 범위를 보여주는 앱 사용 보고서 스크린샷](media/app-usage-report3.png)|
|<span data-ttu-id="1e21b-120">**3**</span><span class="sxs-lookup"><span data-stu-id="1e21b-120">**3**</span></span>    | <ul><li><span data-ttu-id="1e21b-121">차트의 X 축은 특정 보고서에 대해 선택한 날짜 범위입니다.</span><span class="sxs-lookup"><span data-stu-id="1e21b-121">The X axis on the charts is the selected date range for the specific report.</span></span></li><li><span data-ttu-id="1e21b-122">Y축은 차트에서 마우스를 쥐고 있는 주어진 날의 사용자 수로, 해당 사용자가 앱을 적어도 한 번 열고, 이렇게 하면 활성 사용자로 간주하고 마우스를 마우스로 마우스로 마우스를 놓는 총 합계로 누적됩니다.</span><span class="sxs-lookup"><span data-stu-id="1e21b-122">The Y axis is the number of users who for the given day hovered over in chart, those users have opened an app at least once and by doing so are considered an Active User and accrue towards the total seen on mouse hover over.</span></span></li></ul>|
|<span data-ttu-id="1e21b-123">**4**</span><span class="sxs-lookup"><span data-stu-id="1e21b-123">**4**</span></span>   |<span data-ttu-id="1e21b-124">해당 날짜에 앱 사용량을 나타내는 점 위에 마우스를 대고 해당 날짜에 해당 앱의 총 활성 사용자의 인스턴스 수를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e21b-124">Hover over the dot representing an Apps Usage on a given date to see the number of instances of that App’s Total Active Users on that given date.</span></span>  |
|<span data-ttu-id="1e21b-125">**5**</span><span class="sxs-lookup"><span data-stu-id="1e21b-125">**5**</span></span>   |<span data-ttu-id="1e21b-126">모든 앱이 포함되지만 필터 아이콘을 선택하여 추가 필터를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e21b-126">All Apps will be included but by choosing the Filter icon, additional filters are available.</span></span>  |
|<span data-ttu-id="1e21b-127">**6**</span><span class="sxs-lookup"><span data-stu-id="1e21b-127">**6**</span></span>   |<span data-ttu-id="1e21b-128">이 표에서는 앱 이름으로 활성 사용자 및 팀을 분석할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e21b-128">The table gives you a breakdown of active users and teams by App name.</span></span><br><ul><li><span data-ttu-id="1e21b-129">**앱 이름은** 앱에 사용되는 앱의 표시 Teams.</span><span class="sxs-lookup"><span data-stu-id="1e21b-129">**App name** is the display name of the app used in Teams.</span></span></li><li><span data-ttu-id="1e21b-130">**활성 사용자는** 지정된 기간 동안 앱을 한 번 이상 연 사용자 수입니다.</span><span class="sxs-lookup"><span data-stu-id="1e21b-130">**Active users** is the number of users who opened the app at least once during the specified time period.</span></span></li><li><span data-ttu-id="1e21b-131">**앱 형식은** "Microsoft" 또는 "타사"의 정적 값입니다.</span><span class="sxs-lookup"><span data-stu-id="1e21b-131">**App type** is a static value of either “Microsoft” or “Third Party”.</span></span></li><li><span data-ttu-id="1e21b-132">**활성 팀은** 팀의 구성원 중 하나 이상과 지정된 기간 동안 앱을 연 팀의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="1e21b-132">**Active teams** is the number of teams who have opened the App by at least one member of the team and during the specified time periods.</span></span></li><li><span data-ttu-id="1e21b-133">**Publisher** 앱의 소프트웨어 게시자입니다.</span><span class="sxs-lookup"><span data-stu-id="1e21b-133">**Publisher** is the software publisher of the app.</span></span></li><li><span data-ttu-id="1e21b-134">**버전은** 앱 게시자의 소프트웨어 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="1e21b-134">**Version** is the software version of the app, from the app publisher.</span></span></li></ul><span data-ttu-id="1e21b-135"><b> 참고 :</b> 현재 '활성 사용자' 및 '활성 팀'은 채널에서만 사용되는 앱에 대해 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="1e21b-135"><b> Note :</b> Currently, 'Active users' and 'Active teams' are calculated for apps used in channels only.</span></span>     

<br><span data-ttu-id="1e21b-136">![앱 사용 보고서 ](media/app-usage-report4.png)  스크린샷 **| | 7 |**  열 **편집을 선택하여** 표에 열을 추가하거나 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="1e21b-136">![Screenshot of an Apps Usage report](media/app-usage-report4.png)  | |**7**  |Select **Edit columns** to add or remove columns in the table.</span></span><br><br><span data-ttu-id="1e21b-137">![열 편집 페이지의 ](media/app-usage-report5.png)  스크린샷 **| | 8 |**  오프라인 분석을 위해 보고서를 CSV 파일로 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e21b-137">![Screenshot of the Edit columns page](media/app-usage-report5.png)  | |**8**  |You can export the report to a CSV file for offline analysis.</span></span> <span data-ttu-id="1e21b-138">내보내기를 **Excel** 클릭한 다음 다운로드  탭에서 다운로드를  클릭하여 준비가되면 보고서를 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="1e21b-138">Click **Export to Excel**, and then on the **Downloads** tab, click **Download** to download the report when it's ready.</span></span><br><span data-ttu-id="1e21b-139">![다운로드 페이지 ](media/app-usage-report7.png) 스크린샷 **| | 9 |** 보고서에서 보고서를 Excel 앱 **ID를** 나타내는 ID 열도 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="1e21b-139">![Screenshot of Downloads page](media/app-usage-report7.png)  | |**9**   |When you view the report in Excel, you'll also see an **Id** column, which represents the app ID.</span></span> <span data-ttu-id="1e21b-140">팀 ID는 일반적으로 영수 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="1e21b-140">A team ID is typically an alphanumeric string.</span></span> <span data-ttu-id="1e21b-141">Id **열에** \*\*\n\*\*\*\*로 표시되면 사용자가 해당 정보를 삭제하도록 요청한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="1e21b-141">If the **Id** column shows as \*\*\n\*\*\*\*, this means that a user requested their information to be deleted.</span></span><br><span data-ttu-id="1e21b-142">![다운로드한 보고서의 Excel 스크린샷](media/app-usage-report8.png)  |</span><span class="sxs-lookup"><span data-stu-id="1e21b-142">![Screenshot of the downloaded Excel report](media/app-usage-report8.png)  |</span></span>

## <a name="related-topics"></a><span data-ttu-id="1e21b-143">관련 항목</span><span class="sxs-lookup"><span data-stu-id="1e21b-143">Related topics</span></span>

- [<span data-ttu-id="1e21b-144">Teams 분석 및 보고</span><span class="sxs-lookup"><span data-stu-id="1e21b-144">Teams analytics and reporting</span></span>](teams-reporting-reference.md)