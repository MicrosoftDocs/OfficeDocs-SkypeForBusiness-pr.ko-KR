---
title: Microsoft 팀 PSTN으로 차단 된 사용자 보고서
author: LanaChin
ms.author: v-lanac
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: v-rifer
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
MS.collection:
- M365-voice
description: Microsoft 팀 관리 센터의 PSTN 차단 사용자 보고서를 사용 하 여 PSTN 통화를 차단 하는 조직의 팀 사용자에 대 한 개요를 얻을 수 있습니다.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: e6055533138f08bafbdc9c39b03350612075840f
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/03/2020
ms.locfileid: "43140689"
---
# <a name="microsoft-teams-pstn-blocked-users-report"></a><span data-ttu-id="d4b19-103">Microsoft 팀 PSTN으로 차단 된 사용자 보고서</span><span class="sxs-lookup"><span data-stu-id="d4b19-103">Microsoft Teams PSTN blocked users report</span></span>

<span data-ttu-id="d4b19-104">Microsoft 팀 관리 센터의 PSTN 차단 사용자 보고서에는 팀에서 PSTN 통화를 할 수 없도록 차단 된 조직의 사용자가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d4b19-104">The PSTN blocked users report in the Microsoft Teams admin center shows you the users in your organization who are blocked from making PSTN calls in Teams.</span></span> <span data-ttu-id="d4b19-105">지정 된 전화 번호를 포함 하 여 차단 된 각 사용자에 대 한 자세한 정보와 전화를 거는 차단 이유를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4b19-105">You can view more information about each blocked user, including their assigned phone number and the reason they were blocked from making calls.</span></span>

## <a name="view-the-report"></a><span data-ttu-id="d4b19-106">보고서 보기</span><span class="sxs-lookup"><span data-stu-id="d4b19-106">View the report</span></span>

<span data-ttu-id="d4b19-107">Microsoft 팀 관리 센터의 왼쪽 탐색 모음에서 **분석 & 보고서** > **사용 현황 보고서**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4b19-107">In the left navigation of the Microsoft Teams admin center, click **Analytics & reports** > **Usage reports**.</span></span> <span data-ttu-id="d4b19-108">**보고서 보기** 탭의 **보고서**에서 **PSTN 차단 된 사용자**를 선택한 다음 **보고서 실행**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4b19-108">On the **View reports** tab, under **Report**, select **PSTN blocked users**, and then click **Run report**.</span></span>

<span data-ttu-id="d4b19-109">![관리 센터의 PSTN 차단 사용자 보고서 보고서 스크린샷](../media/teams-reports-pstn-blocked-users-with-callouts.png "Microsoft 팀 관리 센터에서 번호가 매겨진 설명선이 포함 된 PSTN 차단 사용자 보고서 스크린샷")</span><span class="sxs-lookup"><span data-stu-id="d4b19-109">![Screenshot of the PSTN blocked users report report in the admin center](../media/teams-reports-pstn-blocked-users-with-callouts.png "Screenshot of the PSTN blocked users report in the Microsoft Teams admin center with numbered callouts")</span></span>

## <a name="interpret-the-report"></a><span data-ttu-id="d4b19-110">보고서 해석</span><span class="sxs-lookup"><span data-stu-id="d4b19-110">Interpret the report</span></span>

|<span data-ttu-id="d4b19-111">호출</span><span class="sxs-lookup"><span data-stu-id="d4b19-111">Callout</span></span> |<span data-ttu-id="d4b19-112">Description</span><span class="sxs-lookup"><span data-stu-id="d4b19-112">Description</span></span>  |
|--------|-------------|
|<span data-ttu-id="d4b19-113">**1**</span><span class="sxs-lookup"><span data-stu-id="d4b19-113">**1**</span></span>   |<span data-ttu-id="d4b19-114">각 보고서에는 생성 된 날짜를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4b19-114">Each report has a date for when it was generated.</span></span> <span data-ttu-id="d4b19-115">일반적으로이 보고서에는 활동 시간부터 24 ~ 48 시간 대기 시간이 반영 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d4b19-115">The reports usually reflect a 24 to 48 hour latency from time of activity.</span></span> |
|<span data-ttu-id="d4b19-116">**2**</span><span class="sxs-lookup"><span data-stu-id="d4b19-116">**2**</span></span>   |<span data-ttu-id="d4b19-117">X 축은 날짜입니다.</span><span class="sxs-lookup"><span data-stu-id="d4b19-117">The X axis is the date.</span></span> <span data-ttu-id="d4b19-118">Y 축은 사용자 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d4b19-118">The Y axis is the number of users.</span></span> <br><span data-ttu-id="d4b19-119">지정 된 날짜의 점을 마우스로 가리켜 해당 날짜에 대해 차단 된 사용자 수를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4b19-119">Hover over the dot on a given date to see the number of users blocked on that date.</span></span> |
|<span data-ttu-id="d4b19-120">**3**</span><span class="sxs-lookup"><span data-stu-id="d4b19-120">**3**</span></span>   |<span data-ttu-id="d4b19-121">이 표는 PSTN 통화를 차단 하는 모든 사용자의 분석 결과를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4b19-121">The table gives a breakdown of all users who are blocked from making PSTN calls.</span></span>  <span data-ttu-id="d4b19-122">전화 시스템 또는 오디오 회의가 할당 된 모든 사용자를 보여 주고 각 사용자에 대 한 자세한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4b19-122">It shows all users who have Phone System or Audio Conferencing assigned and gives you more information about each user.</span></span> <ul><li><span data-ttu-id="d4b19-123">**표시 이름은** 사용자의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="d4b19-123">**Display name** is the display name of the user.</span></span> <span data-ttu-id="d4b19-124">표시 이름을 클릭 하 여 Microsoft 팀 관리 센터의 사용자 설정 페이지로 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4b19-124">You can click the display name to go to the user's setting page in the Microsoft Teams admin center.</span></span> </li> <li><span data-ttu-id="d4b19-125">**Phone** 은 사용자에 게 할당 된 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="d4b19-125">**Phone** is the number that's assigned to the user.</span></span></li> <li><span data-ttu-id="d4b19-126">**차단 된 이유** 는 사용자가 전화를 거는 것을 차단 하는 이유입니다.</span><span class="sxs-lookup"><span data-stu-id="d4b19-126">**Blocked reason** is the reason the user is blocked from making calls.</span></span></li><li><span data-ttu-id="d4b19-127">**차단 된 작업** 은 사용자가 팀에서 PSTN 호출을 차단 또는 해제 했는지 여부를 알려줍니다.</span><span class="sxs-lookup"><span data-stu-id="d4b19-127">**Blocked action**  tells you whether the user is blocked or unblocked from making PSTN calls in Teams.</span></span></li> <li><span data-ttu-id="d4b19-128">**차단 된 시간은** 사용자가 전화를 걸 수 없도록 차단 된 날짜 및 시간 (UTC)입니다.</span><span class="sxs-lookup"><span data-stu-id="d4b19-128">**Blocked time** is the date and time (UTC) that the user was blocked from making calls.</span></span></li></li> </ul><span data-ttu-id="d4b19-129">표에 원하는 정보를 표시 하려면 표에 열을 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4b19-129">To see the information that you want in the table, make sure to add the columns to the table.</span></span> |
|<span data-ttu-id="d4b19-130">**4(tcp/ipv4)**</span><span class="sxs-lookup"><span data-stu-id="d4b19-130">**4**</span></span>   |<span data-ttu-id="d4b19-131">**열 편집** 을 선택 하 여 테이블에 열을 추가 하거나 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4b19-131">Select **Edit columns** to add or remove columns in the table.</span></span>|
|<span data-ttu-id="d4b19-132">**5mb**</span><span class="sxs-lookup"><span data-stu-id="d4b19-132">**5**</span></span>   |<span data-ttu-id="d4b19-133">전체 화면 모드에서 보고서를 보려면 **full screen** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4b19-133">Select **Full screen** to view the report in full screen mode.</span></span>|

## <a name="related-topics"></a><span data-ttu-id="d4b19-134">관련 항목</span><span class="sxs-lookup"><span data-stu-id="d4b19-134">Related topics</span></span>

- [<span data-ttu-id="d4b19-135">팀 분석 및 보고</span><span class="sxs-lookup"><span data-stu-id="d4b19-135">Teams analytics and reporting</span></span>](teams-reporting-reference.md)