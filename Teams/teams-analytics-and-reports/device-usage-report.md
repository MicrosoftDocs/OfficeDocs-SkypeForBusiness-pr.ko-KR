---
title: Microsoft Teams 장치 사용 현황 보고서
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: svemu
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Microsoft Teams 관리 센터에서 Teams 장치 사용 현황 보고서를 사용하여 조직의 사용자가 Teams에 연결하는 방법을 확인합니다.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 292632972396f5d4300fa2526f01e69a5555ff45
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815648"
---
# <a name="microsoft-teams-device-usage-report"></a><span data-ttu-id="2c147-103">Microsoft Teams 장치 사용 현황 보고서</span><span class="sxs-lookup"><span data-stu-id="2c147-103">Microsoft Teams device usage report</span></span>

<span data-ttu-id="2c147-104">Microsoft Teams 관리 센터의 Teams 장치 사용 현황 보고서는 사용자가 Teams에 연결하는 방법에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2c147-104">The Teams device usage report in the Microsoft Teams admin center provides you with information about how users connect to Teams.</span></span> <span data-ttu-id="2c147-105">이동 중 모바일 장치에서 Teams를 사용하는 수를 포함하여 보고서를 사용하여 조직 전체에서 사용되는 장치를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c147-105">You can use the report to see the devices that are used across your organization, including how many use Teams from their mobile devices when on-the-go.</span></span>  

## <a name="view-the-device-usage-report"></a><span data-ttu-id="2c147-106">디바이스 사용 보고서 보기</span><span class="sxs-lookup"><span data-stu-id="2c147-106">View the device usage report</span></span>

1. <span data-ttu-id="2c147-107">Microsoft Teams 관리 센터의 왼쪽 탐색 모음에서 Analytics & **보고서를**  >  **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="2c147-107">In the left navigation of the Microsoft Teams admin center, click **Analytics & reports** > **Usage reports**.</span></span> <span data-ttu-id="2c147-108">보고서 보기 **탭의** **보고서에서** Teams 장치 **사용 현황을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="2c147-108">On the **View reports** tab, under **Report**, select **Teams device usage**.</span></span>
2. <span data-ttu-id="2c147-109">날짜 **범위에서** 범위를 선택한 다음 보고서 **실행을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="2c147-109">Under **Date range**, select a range, and then click **Run report**.</span></span>

    <span data-ttu-id="2c147-110">![설명선이 있는 Teams 관리 센터의 Teams 장치 사용 현황 보고서 스크린샷](../media/teams-reports-device-usage-with-callouts.png "설명선이 있는 Teams 관리 센터의 Teams 장치 사용 현황 보고서 스크린샷")</span><span class="sxs-lookup"><span data-stu-id="2c147-110">![Screenshot of the Teams device usage report in the Teams admin center with callouts](../media/teams-reports-device-usage-with-callouts.png "Screenshot of the Teams device usage report in the Teams admin center  with callouts")</span></span>

## <a name="interpret-the-report"></a><span data-ttu-id="2c147-111">보고서 해석</span><span class="sxs-lookup"><span data-stu-id="2c147-111">Interpret the report</span></span>

|<span data-ttu-id="2c147-112">Callout</span><span class="sxs-lookup"><span data-stu-id="2c147-112">Callout</span></span> |<span data-ttu-id="2c147-113">설명</span><span class="sxs-lookup"><span data-stu-id="2c147-113">Description</span></span>  |
|--------|-------------|
|<span data-ttu-id="2c147-114">**1**</span><span class="sxs-lookup"><span data-stu-id="2c147-114">**1**</span></span>   |<span data-ttu-id="2c147-115">Teams 장치 사용 현황 보고서에서 지난 7일 또는 30일간의 추세를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c147-115">The Teams device usage report can be viewed for trends over the last 7 days or 30 days.</span></span>  |
|<span data-ttu-id="2c147-116">**2**</span><span class="sxs-lookup"><span data-stu-id="2c147-116">**2**</span></span>   |<span data-ttu-id="2c147-117">각 보고서에는 보고서가 생성된 날짜가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c147-117">Each report has a date for when the report was generated.</span></span> <span data-ttu-id="2c147-118">보고서는 일반적으로 활동 시간으로부터 24시간의 대기 시간을 반영합니다.</span><span class="sxs-lookup"><span data-stu-id="2c147-118">The reports usually reflect a 24 hour latency from time of activity.</span></span> |
|<span data-ttu-id="2c147-119">**3**</span><span class="sxs-lookup"><span data-stu-id="2c147-119">**3**</span></span>   |<ul><li><span data-ttu-id="2c147-120">차트의 X축은 Teams에 연결하는 데 사용되는 다양한 **장치(Windows,** **Mac,** **Linux,** **iOS,** **Android Phone,** **Web)를** 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2c147-120">The X axis on the chart represents the different devices (**Windows**, **Mac**, **Linux**, **iOS**, **Android Phone**, **Web**) used to connect to Teams.</span></span> </li><li><span data-ttu-id="2c147-121">Y축은 선택한 기간 동안 디바이스를 사용하는 사용자 수입니다.</span><span class="sxs-lookup"><span data-stu-id="2c147-121">The Y axis is the number of users using the device over the selected time period.</span></span></li> </ul><span data-ttu-id="2c147-122">장치를 나타내는 막대 위에 마우스를 대면 Teams에 연결하는 장치를 사용하는 사용자 수를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c147-122">Hover over the bar representing a device to see the number of users using the device to connect to Teams.</span></span>|
|<span data-ttu-id="2c147-123">**4**</span><span class="sxs-lookup"><span data-stu-id="2c147-123">**4**</span></span>   |<span data-ttu-id="2c147-124">이 표에서는 사용자별 디바이스 사용량을 분석합니다.</span><span class="sxs-lookup"><span data-stu-id="2c147-124">The table gives you a breakdown of device usage by user.</span></span> <ul><li><span data-ttu-id="2c147-125">**사용자** 이름은 사용자의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="2c147-125">**Username** is the display name of the user.</span></span> <span data-ttu-id="2c147-126">표시 이름을 클릭하여 Microsoft Teams 관리 센터의 사용자 설정 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="2c147-126">You can click the display name to go to the user's setting page in the Microsoft Teams admin center.</span></span> </li><li><span data-ttu-id="2c147-127">**사용자가 Windows** 기반 컴퓨터의 Teams 데스크톱 클라이언트에서 활성 상태인 경우 Windows가 선택됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c147-127">**Windows** is selected if the user was active in the Teams desktop client on a Windows-based computer.</span></span></li><li><span data-ttu-id="2c147-128">**사용자가 macOS** 컴퓨터의 Teams 데스크톱 클라이언트에서 활성 상태인 경우 Mac이 선택됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c147-128">**Mac** is selected if the user was active in the Teams desktop client on a macOS computer.</span></span> </li> <li><span data-ttu-id="2c147-129">**사용자가 Linux** 컴퓨터의 Teams 데스크톱 클라이언트에서 활성 상태인 경우 Linux가 선택됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c147-129">**Linux** is selected if the user was active in the Teams desktop client on a Linux computer.</span></span> </li> <li><span data-ttu-id="2c147-130">**사용자가 iOS용** Teams 모바일 클라이언트에서 활성 상태인 경우 iOS가 선택됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c147-130">**iOS** is selected if the user was active on the Teams mobile client for iOS.</span></span></li><li><span data-ttu-id="2c147-131">**Android용** Teams 모바일 클라이언트에서 사용자가 활성 상태인 경우 Android 휴대폰이 선택됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c147-131">**Android phone** is selected if the user was active on the Teams mobile client for Android.</span></span> <li><li><span data-ttu-id="2c147-132">**사용자가** Teams 웹 클라이언트에서 활성 상태인 경우 웹이 선택됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c147-132">**Web** is selected if the user was active on the Teams web client.</span></span> <li><span data-ttu-id="2c147-133">**마지막 활동은** 사용자가 Teams 활동에 참여한 마지막 날짜(UTC)입니다.</span><span class="sxs-lookup"><span data-stu-id="2c147-133">**Last activity** is the last date (UTC) that the user participated in a Teams activity.</span></span></li> </ul> <span data-ttu-id="2c147-134">사용자 계정이 Azure AD에 더 이상 없는 경우 사용자 이름은 테이블에 "--"로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c147-134">Note that if a user account no longer exists in Azure AD, the user name is displayed as "--" in the table.</span></span> <br><br><span data-ttu-id="2c147-135">표에서 원하는 정보를 확인하려는 경우 테이블에 열을 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c147-135">To see the information that you want in the table, make sure to add the columns to the table.</span></span> |
|<span data-ttu-id="2c147-136">**5**</span><span class="sxs-lookup"><span data-stu-id="2c147-136">**5**</span></span>   |<span data-ttu-id="2c147-137">열 **편집을 선택하여** 표에서 열을 추가하거나 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="2c147-137">Select **Edit columns** to add or remove columns in the table.</span></span> |
|<span data-ttu-id="2c147-138">**6**</span><span class="sxs-lookup"><span data-stu-id="2c147-138">**6**</span></span>   |<span data-ttu-id="2c147-139">오프라인 분석을 위해 보고서를 CSV 파일로 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c147-139">You can export the report to a CSV file for offline analysis.</span></span> <span data-ttu-id="2c147-140">**Excel로 내보내기를** 클릭한  다음 다운로드 탭에서 다운로드를 클릭하여 준비가 되면 보고서를 다운로드합니다. </span><span class="sxs-lookup"><span data-stu-id="2c147-140">Click **Export to Excel**, and then on the **Downloads** tab, click **Download** to download the report when it's ready.</span></span><br><br><span data-ttu-id="2c147-141">![내보낼 보고서를 보여주는 다운로드 탭의 스크린샷](../media/teams-reports-export-to-csv.png)</span><span class="sxs-lookup"><span data-stu-id="2c147-141">![Screenshot of the Downloads tab showing exported reports](../media/teams-reports-export-to-csv.png)</span></span>|

## <a name="related-topics"></a><span data-ttu-id="2c147-142">관련 항목</span><span class="sxs-lookup"><span data-stu-id="2c147-142">Related topics</span></span>

- [<span data-ttu-id="2c147-143">Teams 분석 및 보고</span><span class="sxs-lookup"><span data-stu-id="2c147-143">Teams analytics and reporting</span></span>](teams-reporting-reference.md)
