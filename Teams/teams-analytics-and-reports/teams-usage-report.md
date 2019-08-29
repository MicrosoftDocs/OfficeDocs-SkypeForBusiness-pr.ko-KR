---
title: Microsoft 팀 사용 보고서
author: LanaChin
ms.author: v-lanac
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: svemu
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
description: Microsoft 팀 관리 센터에서 팀 사용 보고서를 사용 하 여 조직의 팀 활동에 대 한 개요를 확인 하는 방법에 대해 알아봅니다.
appliesto:
- Microsoft Teams
ms.openlocfilehash: d530ba8009cd113354a511b61589b409958ec276
ms.sourcegitcommit: a5cde2df1aceed9d919ef53281dd0d75f1f5e183
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/29/2019
ms.locfileid: "36667121"
---
# <a name="microsoft-teams-usage-report"></a><span data-ttu-id="59cc6-103">Microsoft 팀 사용 보고서</span><span class="sxs-lookup"><span data-stu-id="59cc6-103">Microsoft Teams usage report</span></span>

<span data-ttu-id="59cc6-104">Microsoft 팀 관리 센터의 팀 사용 보고서에서는 활성 사용자 및 채널 수를 비롯 한 팀의 사용 현황 작업에 대 한 개요를 제공 하므로 조직에서 팀을 사용 하 여 통신 하는 사용자 수를 빠르게 확인할 수 있습니다. 사람들과.</span><span class="sxs-lookup"><span data-stu-id="59cc6-104">The Teams usage report in the Microsoft Teams admin center gives you an overview of the usage activity in Teams, including the number of active users and channels, so you can quickly see how many users across your organization are using Teams to communicate and collaborate.</span></span> <span data-ttu-id="59cc6-105">각 팀의 활성 사용자 및 채널, 게스트 및 메시지 수를 비롯 한 팀의 사용 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59cc6-105">You can view usage information for  teams, including the number of active users and channels, guests, and messages in each team.</span></span>

## <a name="view-the-report"></a><span data-ttu-id="59cc6-106">보고서 보기</span><span class="sxs-lookup"><span data-stu-id="59cc6-106">View the report</span></span>

1. <span data-ttu-id="59cc6-107">Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **분석 & 보고서**를 클릭 한 다음 **보고서**에서 **팀 사용량**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="59cc6-107">In the left navigation of the Microsoft Teams admin center, click **Analytics & reports**, and then under **Report**, select **Teams usage**.</span></span>
2. <span data-ttu-id="59cc6-108">**날짜 범위**아래에서 범위를 선택 하 고 **보고서 실행**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="59cc6-108">Under **Date range**, select a range, and then click **Run report**.</span></span>

<span data-ttu-id="59cc6-109">![팀 관리 센터에서 설명선이 포함 된 팀 사용 보고서 스크린샷] (../media/teams-reports-teams-usage-with-callouts.png "팀 관리 센터에서 설명선이 포함 된 팀 사용 보고서 스크린샷")</span><span class="sxs-lookup"><span data-stu-id="59cc6-109">![Screen shot of the Teams usage report in the Teams admin center with callouts](../media/teams-reports-teams-usage-with-callouts.png "Screen shot of the Teams usage report in the Teams admin center with callouts")</span></span>

## <a name="interpret-the-report"></a><span data-ttu-id="59cc6-110">보고서 해석</span><span class="sxs-lookup"><span data-stu-id="59cc6-110">Interpret the report</span></span>

|<span data-ttu-id="59cc6-111">호출</span><span class="sxs-lookup"><span data-stu-id="59cc6-111">Callout</span></span> |<span data-ttu-id="59cc6-112">설명</span><span class="sxs-lookup"><span data-stu-id="59cc6-112">Description</span></span>  |
|--------|-------------|
|<span data-ttu-id="59cc6-113">**raid-1**</span><span class="sxs-lookup"><span data-stu-id="59cc6-113">**1**</span></span>   |<span data-ttu-id="59cc6-114">팀 사용 활동 보고서는 지난 7 일 또는 28 일간의 추세에 대해 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59cc6-114">The Teams usage activity report can be viewed for trends over the last 7 days or 28 days.</span></span> |
|<span data-ttu-id="59cc6-115">**2**</span><span class="sxs-lookup"><span data-stu-id="59cc6-115">**2**</span></span>   |<span data-ttu-id="59cc6-116">각 보고서에는이 보고서가 생성 된 날짜에 대 한 날짜가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59cc6-116">Each report has a date for when this report was generated.</span></span> <span data-ttu-id="59cc6-117">일반적으로이 보고서에는 활동 시간부터 24 ~ 48 시간 대기 시간이 반영 됩니다.</span><span class="sxs-lookup"><span data-stu-id="59cc6-117">The reports usually reflect a 24 to 48 hour latency from time of activity.</span></span> |
|<span data-ttu-id="59cc6-118">**3-4**</span><span class="sxs-lookup"><span data-stu-id="59cc6-118">**3**</span></span>   |<ul><li><span data-ttu-id="59cc6-119">차트의 X 축은 보고서에 대해 선택 된 날짜 범위입니다.</span><span class="sxs-lookup"><span data-stu-id="59cc6-119">The X axis on the chart is the selected date range for the report.</span></span></li> <li> <span data-ttu-id="59cc6-120">Y 축은 활성 항목 또는 활동의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="59cc6-120">The Y axis is the count of active items or activity.</span></span></li> </ul><span data-ttu-id="59cc6-121">지정 된 날짜에 항목이 나 활동을 나타내는 점을 가리켜 해당 항목 또는 해당 날짜에 대 한 활동의 인스턴스 수를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="59cc6-121">Hover over the dot representing an item or activity on a given date to see the number of instances of that item or activity on that given date.</span></span>|
|<span data-ttu-id="59cc6-122">**4(tcp/ipv4)**</span><span class="sxs-lookup"><span data-stu-id="59cc6-122">**4**</span></span>   |<span data-ttu-id="59cc6-123">범례에서 항목을 클릭 하 여 차트에 표시 되는 내용을 필터링 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59cc6-123">You can filter what you see on the chart by clicking an item in the legend.</span></span> <span data-ttu-id="59cc6-124">예를 들어 **총 활성 사용자**, **팀 & 채널 활성 사용자**, **활성 채널**또는 **메시지** 를 클릭 하 여 각 항목에 관련 된 정보만 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="59cc6-124">For example, click  **Total active users**, **Teams & Channels active users**,  **Active channels**, or **Messages** to see only the info related to each one.</span></span> <span data-ttu-id="59cc6-125">이 선택을 변경 해도 표의 정보는 변경 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="59cc6-125">Changing this selection doesn’t change the information in the table.</span></span> |
|<span data-ttu-id="59cc6-126">**5mb**</span><span class="sxs-lookup"><span data-stu-id="59cc6-126">**5**</span></span>   |<span data-ttu-id="59cc6-127">이 표는 팀의 사용량을 분류 하 여 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="59cc6-127">The table gives you a breakdown of usage by team.</span></span> <ul><li><span data-ttu-id="59cc6-128">**팀 이름은** 팀의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="59cc6-128">**Team name** is the display name of the team.</span></span> <span data-ttu-id="59cc6-129">팀 이름을 클릭 하 여 Microsoft 팀 관리 센터의 팀 설정 페이지로 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59cc6-129">You can click the team name to go to the team's settings page in the Microsoft Teams admin center.</span></span> </li> <li><span data-ttu-id="59cc6-130">**개인 정보** 는 팀이 비공개 팀 인지 또는 공용 팀 인지를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="59cc6-130">**Privacy** refers to whether the team is a private team or public team.</span></span></li> <li><span data-ttu-id="59cc6-131">**활성 사용자** 는 지정 된 기간에 팀의 활성 사용자 수입니다.</span><span class="sxs-lookup"><span data-stu-id="59cc6-131">**Active users** is the number of active users in the team in the specified time period.</span></span></li><li><span data-ttu-id="59cc6-132">**게스트** 는 지정 된 기간에 팀의 게스트 수입니다.</span><span class="sxs-lookup"><span data-stu-id="59cc6-132">**Guests** is the number of guests in the team in the specified time period.</span></span></li> </li> </ul><span data-ttu-id="59cc6-133">사용자 계정이 더 이상 Azure AD에 존재 하지 않는 경우에는 테이블에 사용자 이름이 "--"로 표시 됨을 참고 하세요.</span><span class="sxs-lookup"><span data-stu-id="59cc6-133">Note that if a user account no longer exists in Azure AD, the user name is displayed as "--" in the table.</span></span> <br><br><span data-ttu-id="59cc6-134">표에 원하는 정보를 표시 하려면 표에 열을 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="59cc6-134">To see the information that you want in the table, make sure to add the columns to the table.</span></span> |
|<span data-ttu-id="59cc6-135">**26**</span><span class="sxs-lookup"><span data-stu-id="59cc6-135">**6**</span></span>   |<span data-ttu-id="59cc6-136">**열 편집** 을 선택 하 여 테이블에 열을 추가 하거나 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="59cc6-136">Select **Edit columns** to add or remove columns in the table.</span></span>|
|<span data-ttu-id="59cc6-137">**7**</span><span class="sxs-lookup"><span data-stu-id="59cc6-137">**7**</span></span>   |<span data-ttu-id="59cc6-138">오프 라인 분석을 위해 보고서를 CSV 파일로 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59cc6-138">You can export the report to a CSV file for offline analysis.</span></span> <span data-ttu-id="59cc6-139">**Excel로 내보내기를**클릭 한 다음 **다운로드** 탭에서 **다운로드** 를 클릭 하 여 준비 된 보고서를 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="59cc6-139">Click **Export to Excel**, and then on the **Downloads** tab, click **Download** to download the report when it's ready.</span></span><br><br><span data-ttu-id="59cc6-140">![내보낸 보고서를 다운로드 하 여 표시 하는 다운로드 탭 스크린샷](../media/teams-reports-export-to-csv.png)</span><span class="sxs-lookup"><span data-stu-id="59cc6-140">![Screen shot of the Downloads tab showing exported reports to download](../media/teams-reports-export-to-csv.png)</span></span>|

## <a name="related-topics"></a><span data-ttu-id="59cc6-141">관련 항목</span><span class="sxs-lookup"><span data-stu-id="59cc6-141">Related topics</span></span>

- [<span data-ttu-id="59cc6-142">팀 분석 및 보고</span><span class="sxs-lookup"><span data-stu-id="59cc6-142">Teams analytics and reporting</span></span>](teams-reporting-reference.md)
