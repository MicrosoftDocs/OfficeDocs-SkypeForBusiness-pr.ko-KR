---
title: Microsoft Teams PSTN 차단된 사용자 보고서
author: cichur
ms.author: v-cichur
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
description: Microsoft Teams 관리 센터에서 PSTN 차단 사용자 보고서를 사용하여 PSTN 통화를 걸 수 없습니다.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ed775c3796e40a775b3be2b78f22e162a047bf78
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809338"
---
# <a name="microsoft-teams-pstn-blocked-users-report"></a><span data-ttu-id="7e3b4-103">Microsoft Teams PSTN 차단된 사용자 보고서</span><span class="sxs-lookup"><span data-stu-id="7e3b4-103">Microsoft Teams PSTN blocked users report</span></span>

<span data-ttu-id="7e3b4-104">Microsoft Teams 관리 센터의 PSTN 차단 사용자 보고서에는 Teams에서 PSTN 통화를 걸 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7e3b4-104">The PSTN blocked users report in the Microsoft Teams admin center shows you the users in your organization who are blocked from making PSTN calls in Teams.</span></span> <span data-ttu-id="7e3b4-105">할당된 전화 번호 및 전화 걸기 차단 이유를 포함하여 차단된 각 사용자에 대한 자세한 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e3b4-105">You can view more information about each blocked user, including their assigned phone number and the reason they were blocked from making calls.</span></span>

## <a name="view-the-pstn-blocked-users-report"></a><span data-ttu-id="7e3b4-106">PSTN 차단된 사용자 보고서 보기</span><span class="sxs-lookup"><span data-stu-id="7e3b4-106">View the PSTN blocked users report</span></span>

<span data-ttu-id="7e3b4-107">Microsoft Teams 관리 센터의 왼쪽 탐색 모음에서 Analytics & **보고서를**  >  **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="7e3b4-107">In the left navigation of the Microsoft Teams admin center, click **Analytics & reports** > **Usage reports**.</span></span> <span data-ttu-id="7e3b4-108">보고서 **보기** 탭의 **보고서에서** **PSTN** 차단된 사용자를 선택한 다음 보고서 **실행을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="7e3b4-108">On the **View reports** tab, under **Report**, select **PSTN blocked users**, and then click **Run report**.</span></span>

<span data-ttu-id="7e3b4-109">![관리 센터의 PSTN 차단된 사용자 보고서 보고서 스크린샷](../media/teams-reports-pstn-blocked-users-with-callouts.png "번호가 매기기 설명선이 있는 Microsoft Teams 관리 센터의 PSTN 차단 사용자 보고서 스크린샷")</span><span class="sxs-lookup"><span data-stu-id="7e3b4-109">![Screenshot of the PSTN blocked users report report in the admin center](../media/teams-reports-pstn-blocked-users-with-callouts.png "Screenshot of the PSTN blocked users report in the Microsoft Teams admin center with numbered callouts")</span></span>

## <a name="interpret-the-report"></a><span data-ttu-id="7e3b4-110">보고서 해석</span><span class="sxs-lookup"><span data-stu-id="7e3b4-110">Interpret the report</span></span>

|<span data-ttu-id="7e3b4-111">Callout</span><span class="sxs-lookup"><span data-stu-id="7e3b4-111">Callout</span></span> |<span data-ttu-id="7e3b4-112">설명</span><span class="sxs-lookup"><span data-stu-id="7e3b4-112">Description</span></span>  |
|--------|-------------|
|<span data-ttu-id="7e3b4-113">**1**</span><span class="sxs-lookup"><span data-stu-id="7e3b4-113">**1**</span></span>   |<span data-ttu-id="7e3b4-114">각 보고서에는 생성된 날짜가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e3b4-114">Each report has a date for when it was generated.</span></span> <span data-ttu-id="7e3b4-115">보고서는 일반적으로 활동 시간으로부터 24~48시간의 대기 시간을 반영합니다.</span><span class="sxs-lookup"><span data-stu-id="7e3b4-115">The reports usually reflect a 24 to 48 hour latency from time of activity.</span></span> |
|<span data-ttu-id="7e3b4-116">**2**</span><span class="sxs-lookup"><span data-stu-id="7e3b4-116">**2**</span></span>   |<span data-ttu-id="7e3b4-117">X축은 날짜입니다.</span><span class="sxs-lookup"><span data-stu-id="7e3b4-117">The X axis is the date.</span></span> <span data-ttu-id="7e3b4-118">Y축은 사용자 수입니다.</span><span class="sxs-lookup"><span data-stu-id="7e3b4-118">The Y axis is the number of users.</span></span> <br><span data-ttu-id="7e3b4-119">특정 날짜의 점 위에 마우스를 대면 해당 날짜에 차단된 사용자 수를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e3b4-119">Hover over the dot on a given date to see the number of users blocked on that date.</span></span> |
|<span data-ttu-id="7e3b4-120">**3**</span><span class="sxs-lookup"><span data-stu-id="7e3b4-120">**3**</span></span>   |<span data-ttu-id="7e3b4-121">이 표에서는 PSTN 호출을 차단하는 모든 사용자의 분석 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="7e3b4-121">The table gives a breakdown of all users who are blocked from making PSTN calls.</span></span>  <span data-ttu-id="7e3b4-122">전화 시스템 또는 오디오 회의가 할당된 모든 사용자를 표시하고 각 사용자에 대한 자세한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="7e3b4-122">It shows all users who have Phone System or Audio Conferencing assigned and gives you more information about each user.</span></span> <ul><li><span data-ttu-id="7e3b4-123">**표시 이름은** 사용자의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="7e3b4-123">**Display name** is the display name of the user.</span></span> <span data-ttu-id="7e3b4-124">표시 이름을 클릭하여 Microsoft Teams 관리 센터의 사용자 설정 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="7e3b4-124">You can click the display name to go to the user's setting page in the Microsoft Teams admin center.</span></span> </li> <li><span data-ttu-id="7e3b4-125">**전화는** 사용자에게 할당된 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="7e3b4-125">**Phone** is the number that's assigned to the user.</span></span></li> <li><span data-ttu-id="7e3b4-126">**차단된** 이유는 사용자가 호출을 차단하는 이유입니다.</span><span class="sxs-lookup"><span data-stu-id="7e3b4-126">**Blocked reason** is the reason the user is blocked from making calls.</span></span></li><li><span data-ttu-id="7e3b4-127">**차단된 작업은**  사용자가 Teams에서 PSTN 통화를 걸 수 없는지 또는 차단 해제하는지 여부를 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e3b4-127">**Blocked action**  tells you whether the user is blocked or unblocked from making PSTN calls in Teams.</span></span></li> <li><span data-ttu-id="7e3b4-128">**차단된 시간은** 사용자가 호출을 차단한 날짜 및 시간(UTC)입니다.</span><span class="sxs-lookup"><span data-stu-id="7e3b4-128">**Blocked time** is the date and time (UTC) that the user was blocked from making calls.</span></span></li></li> </ul><span data-ttu-id="7e3b4-129">표에서 원하는 정보를 확인하려는 경우 테이블에 열을 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e3b4-129">To see the information that you want in the table, make sure to add the columns to the table.</span></span> |
|<span data-ttu-id="7e3b4-130">**4**</span><span class="sxs-lookup"><span data-stu-id="7e3b4-130">**4**</span></span>   |<span data-ttu-id="7e3b4-131">열 **편집을 선택하여** 표에서 열을 추가하거나 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="7e3b4-131">Select **Edit columns** to add or remove columns in the table.</span></span>|
|<span data-ttu-id="7e3b4-132">**5**</span><span class="sxs-lookup"><span data-stu-id="7e3b4-132">**5**</span></span>   |<span data-ttu-id="7e3b4-133">전체 **화면을 선택하여** 전체 화면 모드에서 보고서를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e3b4-133">Select **Full screen** to view the report in full screen mode.</span></span>|

## <a name="related-topics"></a><span data-ttu-id="7e3b4-134">관련 항목</span><span class="sxs-lookup"><span data-stu-id="7e3b4-134">Related topics</span></span>

- [<span data-ttu-id="7e3b4-135">Teams 분석 및 보고</span><span class="sxs-lookup"><span data-stu-id="7e3b4-135">Teams analytics and reporting</span></span>](teams-reporting-reference.md)