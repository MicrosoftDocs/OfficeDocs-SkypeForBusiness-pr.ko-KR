---
title: Microsoft 팀 장치 사용 보고서
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
- M365-collaboration
description: Microsoft 팀 관리 센터에서 팀 디바이스 사용 보고서를 사용 하 여 조직의 사용자가 팀에 연결 되는 방식을 확인 하는 방법에 대해 알아봅니다.
appliesto:
- Microsoft Teams
ms.openlocfilehash: c961b6c5897d0c494d0461a3533cae63fa613d41
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2019
ms.locfileid: "37568400"
---
# <a name="microsoft-teams-device-usage-report"></a><span data-ttu-id="b69c5-103">Microsoft 팀 장치 사용 보고서</span><span class="sxs-lookup"><span data-stu-id="b69c5-103">Microsoft Teams device usage report</span></span>

<span data-ttu-id="b69c5-104">Microsoft 팀 관리 센터의 팀 장치 사용 보고서에서 사용자가 팀에 연결 하는 방법에 대 한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b69c5-104">The Teams device usage report in the Microsoft Teams admin center provides you with information about how users connect to Teams.</span></span> <span data-ttu-id="b69c5-105">이 보고서를 사용 하 여 이동 중에 모바일 장치에서 사용 하는 팀의 수를 포함 하 여 조직에서 사용 하는 장치를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b69c5-105">You can use the report to see the devices that are used across your organization, including how many use Teams from their mobile devices when on-the-go.</span></span>  

## <a name="view-the-report"></a><span data-ttu-id="b69c5-106">보고서 보기</span><span class="sxs-lookup"><span data-stu-id="b69c5-106">View the report</span></span>

1. <span data-ttu-id="b69c5-107">Microsoft 팀 관리 센터의 왼쪽 탐색 모음에서 **분석 & 보고서** > **사용 현황 보고서**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b69c5-107">In the left navigation of the Microsoft Teams admin center, click **Analytics & reports** > **Usage reports**.</span></span> <span data-ttu-id="b69c5-108">보고서 **보기** 탭의 **보고서**에서 **팀 디바이스 사용**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b69c5-108">On the **View reports** tab, under **Report**, select **Teams device usage**.</span></span>
2. <span data-ttu-id="b69c5-109">**날짜 범위**아래에서 범위를 선택 하 고 **보고서 실행**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b69c5-109">Under **Date range**, select a range, and then click **Run report**.</span></span>

    <span data-ttu-id="b69c5-110">![팀 관리 센터에서 설명선이 포함 된 팀 디바이스 사용 보고서 스크린샷](../media/teams-reports-device-usage-with-callouts.png "팀 관리 센터에서 설명선이 포함 된 팀 디바이스 사용 보고서 스크린샷")</span><span class="sxs-lookup"><span data-stu-id="b69c5-110">![Screenshot of the Teams device usage report in the Teams admin center with callouts](../media/teams-reports-device-usage-with-callouts.png "Screenshot of the Teams device usage report in the Teams admin center  with callouts")</span></span>

## <a name="interpret-the-report"></a><span data-ttu-id="b69c5-111">보고서 해석</span><span class="sxs-lookup"><span data-stu-id="b69c5-111">Interpret the report</span></span>

|<span data-ttu-id="b69c5-112">호출</span><span class="sxs-lookup"><span data-stu-id="b69c5-112">Callout</span></span> |<span data-ttu-id="b69c5-113">설명</span><span class="sxs-lookup"><span data-stu-id="b69c5-113">Description</span></span>  |
|--------|-------------|
|<span data-ttu-id="b69c5-114">**raid-1**</span><span class="sxs-lookup"><span data-stu-id="b69c5-114">**1**</span></span>   |<span data-ttu-id="b69c5-115">팀 디바이스 사용 보고서는 지난 7 일 또는 28 일 동안의 추세에 대해 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b69c5-115">The Teams device usage report can be viewed for trends over the last 7 days or 28 days.</span></span>  |
|<span data-ttu-id="b69c5-116">**2**</span><span class="sxs-lookup"><span data-stu-id="b69c5-116">**2**</span></span>   |<span data-ttu-id="b69c5-117">각 보고서에는 보고서가 생성 된 날짜를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="b69c5-117">Each report has a date for when the report was generated.</span></span> <span data-ttu-id="b69c5-118">일반적으로이 보고서에는 활동 시간부터 24 ~ 48 시간 대기 시간이 반영 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b69c5-118">The reports usually reflect a 24 to 48 hour latency from time of activity.</span></span> |
|<span data-ttu-id="b69c5-119">**3-4**</span><span class="sxs-lookup"><span data-stu-id="b69c5-119">**3**</span></span>   |<ul><li><span data-ttu-id="b69c5-120">차트의 X 축은 팀에 연결 하는 데 사용 되는 여러 장치 (**Windows**, **Mac**, **iOS**, **Android 휴대폰**)를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b69c5-120">The X axis on the chart represents the different devices (**Windows**, **Mac**, **iOS**, **Android Phone**) used to connect to Teams.</span></span> </li><li><span data-ttu-id="b69c5-121">Y 축은 선택한 기간 동안 디바이스를 사용 하는 사용자 수입니다.</span><span class="sxs-lookup"><span data-stu-id="b69c5-121">The Y axis is the number of users using the device over the selected time period.</span></span></li> </ul><span data-ttu-id="b69c5-122">장치를 나타내는 막대 위에 마우스를 놓아 장치를 사용 하 여 팀에 연결 하는 사용자 수를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="b69c5-122">Hover over the bar representing a device to see the number of users using the device to connect to Teams.</span></span>|
|<span data-ttu-id="b69c5-123">**4(tcp/ipv4)**</span><span class="sxs-lookup"><span data-stu-id="b69c5-123">**4**</span></span>   |<span data-ttu-id="b69c5-124">이 표는 사용자 별 장치 사용을 분석 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b69c5-124">The table gives you a breakdown of device usage by user.</span></span> <ul><li><span data-ttu-id="b69c5-125">**표시 이름은** 사용자의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="b69c5-125">**Display name** is the display name of the user.</span></span> <span data-ttu-id="b69c5-126">표시 이름을 클릭 하 여 Microsoft 팀 관리 센터의 사용자 설정 페이지로 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b69c5-126">You can click the display name to go to the user's setting page in the Microsoft Teams admin center.</span></span> </li><li><span data-ttu-id="b69c5-127">**Windows는** 사용자가 windows 기반 컴퓨터의 팀 데스크톱 클라이언트에서 활성 상태 였던 경우 선택 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b69c5-127">**Windows** is selected if the user was active in the Teams desktop client on a Windows-based computer.</span></span></li><li><span data-ttu-id="b69c5-128">**Mac** 은 사용자가 macos 컴퓨터의 팀 데스크톱 클라이언트에서 활성 상태 였던 경우 선택 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b69c5-128">**Mac** is selected if the user was active in the Teams desktop client on a macOS computer.</span></span> </li> <li><span data-ttu-id="b69c5-129">사용자가 iOS 용 팀 모바일 클라이언트에서 활성 상태 였던 경우 **ios** 가 선택 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b69c5-129">**iOS** is selected if the user was active on the Teams mobile client for iOS.</span></span></li><li><span data-ttu-id="b69c5-130">Android 용 팀 모바일 클라이언트에서 사용자가 활성 상태 였던 경우 **android 전화** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b69c5-130">**Android phone** is selected if the user was active on the Teams mobile client for Android.</span></span> <li><span data-ttu-id="b69c5-131">**마지막 활동** 은 사용자가 팀 활동에 참여 한 마지막 날짜 (UTC)입니다.</span><span class="sxs-lookup"><span data-stu-id="b69c5-131">**Last activity** is the last date (UTC) that the user participated in a Teams activity.</span></span></li> </ul> <span data-ttu-id="b69c5-132">사용자 계정이 더 이상 Azure AD에 존재 하지 않는 경우에는 테이블에 사용자 이름이 "--"로 표시 됨을 참고 하세요.</span><span class="sxs-lookup"><span data-stu-id="b69c5-132">Note that if a user account no longer exists in Azure AD, the user name is displayed as "--" in the table.</span></span> <br><br><span data-ttu-id="b69c5-133">표에 원하는 정보를 표시 하려면 표에 열을 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b69c5-133">To see the information that you want in the table, make sure to add the columns to the table.</span></span> |
|<span data-ttu-id="b69c5-134">**5mb**</span><span class="sxs-lookup"><span data-stu-id="b69c5-134">**5**</span></span>   |<span data-ttu-id="b69c5-135">**열 편집** 을 선택 하 여 테이블에 열을 추가 하거나 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="b69c5-135">Select **Edit columns** to add or remove columns in the table.</span></span> |
|<span data-ttu-id="b69c5-136">**26**</span><span class="sxs-lookup"><span data-stu-id="b69c5-136">**6**</span></span>   |<span data-ttu-id="b69c5-137">오프 라인 분석을 위해 보고서를 CSV 파일로 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b69c5-137">You can export the report to a CSV file for offline analysis.</span></span> <span data-ttu-id="b69c5-138">**Excel로 내보내기를**클릭 한 다음 **다운로드** 탭에서 **다운로드** 를 클릭 하 여 준비 된 보고서를 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="b69c5-138">Click **Export to Excel**, and then on the **Downloads** tab, click **Download** to download the report when it's ready.</span></span><br><br><span data-ttu-id="b69c5-139">![내보낸 보고서를 보여 주는 다운로드 탭의 스크린샷](../media/teams-reports-export-to-csv.png)</span><span class="sxs-lookup"><span data-stu-id="b69c5-139">![Screenshot of the Downloads tab showing exported reports](../media/teams-reports-export-to-csv.png)</span></span>|

## <a name="related-topics"></a><span data-ttu-id="b69c5-140">관련 항목</span><span class="sxs-lookup"><span data-stu-id="b69c5-140">Related topics</span></span>

- [<span data-ttu-id="b69c5-141">팀 분석 및 보고</span><span class="sxs-lookup"><span data-stu-id="b69c5-141">Teams analytics and reporting</span></span>](teams-reporting-reference.md)