---
title: Microsoft 팀 앱 사용 보고서
author: LolaJacobsen
ms.author: lolaj
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
description: Microsoft 팀 관리 센터에서 팀 앱 사용 현황 보고서를 사용 하는 방법에 대해 알아봅니다.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 1a5d5c1bdb5b5bbe58ecdb90721ce24bd0081a65
ms.sourcegitcommit: a73df97a06ea860bfaf5387e0acbf3c724697e14
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/26/2020
ms.locfileid: "44902364"
---
# <a name="microsoft-teams-app-usage-report"></a><span data-ttu-id="75298-103">Microsoft 팀 앱 사용 보고서</span><span class="sxs-lookup"><span data-stu-id="75298-103">Microsoft Teams app usage report</span></span>

<span data-ttu-id="75298-104">Microsoft 팀 관리 센터의 팀 앱 사용 보고서에서는 팀에서 사용 중인 앱에 대 한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="75298-104">The Teams app usage report in the Microsoft Teams admin center provides you with information about which apps users are using in Teams.</span></span>  

## <a name="view-the-app-usage-report"></a><span data-ttu-id="75298-105">앱 사용 현황 보고서 보기</span><span class="sxs-lookup"><span data-stu-id="75298-105">View the App Usage report</span></span>

1.  <span data-ttu-id="75298-106">관리 센터의 왼쪽 탐색 창에서 <https://teams.admin.microsoft.com> **분석 & 보고서** \> **사용 현황 보고서**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="75298-106">In the left navigation of the admin center at <https://teams.admin.microsoft.com>, click **Analytics & reports** \> **Usage reports**.</span></span> <span data-ttu-id="75298-107">보고서 **보기** 탭의 **보고서**에서 **앱 사용**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="75298-107">On the **View reports** tab, under **Report**, select **Apps Usage**.</span></span>

     :::image type="content" source="media/app-usage-report1.png" alt-text="사용 현황 보고서 메뉴 항목의 스크린샷":::

2.  <span data-ttu-id="75298-109">**날짜 범위**아래에서 범위를 선택 하 고 **보고서 실행**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="75298-109">Under **Date range**, select a range, and then click **Run report**.</span></span>

      :::image type="content" source="media/app-usage-report2.png" alt-text="앱 사용 현황 보고서 스크린샷":::

## <a name="interpret-the-report"></a><span data-ttu-id="75298-111">보고서 해석</span><span class="sxs-lookup"><span data-stu-id="75298-111">Interpret the report</span></span>

|<span data-ttu-id="75298-112">호출</span><span class="sxs-lookup"><span data-stu-id="75298-112">Callout</span></span> |<span data-ttu-id="75298-113">설명</span><span class="sxs-lookup"><span data-stu-id="75298-113">Description</span></span>  |
|--------|-------------|
|<span data-ttu-id="75298-114">**1**</span><span class="sxs-lookup"><span data-stu-id="75298-114">**1**</span></span>   |<span data-ttu-id="75298-115">팀 앱 사용 보고서는 지난 7, 30 또는 90 일 동안의 추세에 대해 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75298-115">The Teams Apps usage report can be viewed for trends over the last 7, 30 or 90 days.</span></span> |
|<span data-ttu-id="75298-116">**2**</span><span class="sxs-lookup"><span data-stu-id="75298-116">**2**</span></span>   |<span data-ttu-id="75298-117">각 보고서에는 보고서가 생성 된 날짜를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="75298-117">Each report has a date for when the report was generated.</span></span> <span data-ttu-id="75298-118">일반적으로이 보고서는 앱을 연 시점부터 24 시간 대기 시간을 반영 합니다.</span><span class="sxs-lookup"><span data-stu-id="75298-118">The reports usually reflect a 24-hour latency from the time an app was opened.</span></span> <br><br>![날짜 범위가 표시 된 앱 사용 현황 보고서의 스크린샷](media/app-usage-report3.png)|
|<span data-ttu-id="75298-120">**3**</span><span class="sxs-lookup"><span data-stu-id="75298-120">**3**</span></span>    | <ul><li><span data-ttu-id="75298-121">차트의 X 축은 특정 보고서에 대해 선택 된 날짜 범위입니다.</span><span class="sxs-lookup"><span data-stu-id="75298-121">The X axis on the charts is the selected date range for the specific report.</span></span></li><li><span data-ttu-id="75298-122">Y 축은 차트에서 가리킨 날짜에 대 한 사용자 수 이며, 해당 사용자가 앱을 적어도 한 번만 연 다음 활성 사용자로 간주 하 고 마우스를 올려 놓은 총 부분을 향해 처리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="75298-122">The Y axis is the number of users who for the given day hovered over in chart, those users have opened an app at least once and by doing so are considered an Active User and accrue towards the total seen on mouse hover over.</span></span></li></ul>|
|<span data-ttu-id="75298-123">**4(tcp/ipv4)**</span><span class="sxs-lookup"><span data-stu-id="75298-123">**4**</span></span>   |<span data-ttu-id="75298-124">지정 된 날짜의 앱 사용을 나타내는 점을 마우스로 가리켜 해당 앱의 총 활성 사용자 인스턴스 수를 해당 날짜에 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="75298-124">Hover over the dot representing an Apps Usage on a given date to see the number of instances of that App’s Total Active Users on that given date.</span></span>  |
|<span data-ttu-id="75298-125">**5mb**</span><span class="sxs-lookup"><span data-stu-id="75298-125">**5**</span></span>   |<span data-ttu-id="75298-126">모든 앱이 포함 되지만 필터 아이콘을 선택 하면 추가 필터를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75298-126">All Apps will be included but by choosing the Filter icon, additional filters are available.</span></span>  |
|<span data-ttu-id="75298-127">**26**</span><span class="sxs-lookup"><span data-stu-id="75298-127">**6**</span></span>   |<span data-ttu-id="75298-128">표에서는 활성 사용자와 팀을 분석 하 여 앱 이름을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="75298-128">The table gives you a breakdown of active users and teams by App name.</span></span><br><ul><li><span data-ttu-id="75298-129">**앱 이름은** 팀에 사용 되는 앱의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="75298-129">**App name** is the display name of the app used in Teams.</span></span></li><li><span data-ttu-id="75298-130">**활성 사용자** 는 지정 된 기간 동안 적어도 한 번 앱을 연 사용자의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="75298-130">**Active users** is the number of users who opened the app at least once during the specified time period.</span></span></li><li><span data-ttu-id="75298-131">**앱 유형은** "Microsoft" 또는 "타사"의 정적 값입니다.</span><span class="sxs-lookup"><span data-stu-id="75298-131">**App type** is a static value of either “Microsoft” or “Third Party”.</span></span></li><li><span data-ttu-id="75298-132">**활성 팀** 은 팀의 구성원 한 명 이상과 지정 된 기간 동안 앱을 연 팀의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="75298-132">**Active teams** is the number of teams who have opened the App by at least one member of the team and during the specified time periods.</span></span></li><li><span data-ttu-id="75298-133">**Publisher** 는 앱의 소프트웨어 게시자입니다.</span><span class="sxs-lookup"><span data-stu-id="75298-133">**Publisher** is the software publisher of the app.</span></span></li><li><span data-ttu-id="75298-134">**버전** 은 앱 게시자에서 앱의 소프트웨어 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="75298-134">**Version** is the software version of the app, from the app publisher.</span></span></li></ul><br><span data-ttu-id="75298-135">![앱 사용 현황 보고서 스크린샷](media/app-usage-report4.png)</span><span class="sxs-lookup"><span data-stu-id="75298-135">![Screenshot of an Apps Usage report](media/app-usage-report4.png)</span></span>  |
|<span data-ttu-id="75298-136">**7**</span><span class="sxs-lookup"><span data-stu-id="75298-136">**7**</span></span>  |<span data-ttu-id="75298-137">**열 편집** 을 선택 하 여 테이블에 열을 추가 하거나 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="75298-137">Select **Edit columns** to add or remove columns in the table.</span></span><br><br><span data-ttu-id="75298-138">![열 편집 페이지의 스크린샷](media/app-usage-report5.png)</span><span class="sxs-lookup"><span data-stu-id="75298-138">![Screenshot of the Edit columns page](media/app-usage-report5.png)</span></span>  |
|<span data-ttu-id="75298-139">**20cm(8**</span><span class="sxs-lookup"><span data-stu-id="75298-139">**8**</span></span>  |<span data-ttu-id="75298-140">오프 라인 분석을 위해 보고서를 CSV 파일로 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75298-140">You can export the report to a CSV file for offline analysis.</span></span> <span data-ttu-id="75298-141">**Excel로 내보내기를**클릭 한 다음 **다운로드** 탭에서 **다운로드** 를 클릭 하 여 준비 된 보고서를 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="75298-141">Click **Export to Excel**, and then on the **Downloads** tab, click **Download** to download the report when it's ready.</span></span><br><span data-ttu-id="75298-142">![다운로드 페이지 스크린샷](media/app-usage-report7.png)</span><span class="sxs-lookup"><span data-stu-id="75298-142">![Screenshot of Downloads page](media/app-usage-report7.png)</span></span>  |
|<span data-ttu-id="75298-143">**되었는지**</span><span class="sxs-lookup"><span data-stu-id="75298-143">**9**</span></span>   |<span data-ttu-id="75298-144">Excel에서 보고서를 볼 때 앱 ID를 나타내는 **Id** 열이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="75298-144">When you view the report in Excel, you'll also see an **Id** column, which represents the app ID.</span></span> <span data-ttu-id="75298-145">팀 ID는 일반적으로 영숫자 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="75298-145">A team ID is typically an alphanumeric string.</span></span> <span data-ttu-id="75298-146">**Id** 열에 \* \* \n \* \* \* \*가 표시 되는 경우 사용자가 삭제 될 정보를 요청 했음을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="75298-146">If the **Id** column shows as \*\*\n\*\*\*\*, this means that a user requested their information to be deleted.</span></span><br><span data-ttu-id="75298-147">![다운로드 한 Excel 보고서 스크린샷](media/app-usage-report8.png)</span><span class="sxs-lookup"><span data-stu-id="75298-147">![Screenshot of the downloaded Excel report](media/app-usage-report8.png)</span></span>  |

## <a name="related-topics"></a><span data-ttu-id="75298-148">관련 항목</span><span class="sxs-lookup"><span data-stu-id="75298-148">Related topics</span></span>

- [<span data-ttu-id="75298-149">팀 분석 및 보고</span><span class="sxs-lookup"><span data-stu-id="75298-149">Teams analytics and reporting</span></span>](teams-reporting-reference.md)