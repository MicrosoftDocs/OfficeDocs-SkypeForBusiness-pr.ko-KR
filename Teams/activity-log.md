---
title: Microsoft 팀 관리 센터의 활동 로그에서 정책 과제 보기
author: LanaChin
ms.author: v-lanac
ms.reviewer: jastark
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: Microsoft 팀 관리 센터의 활동 로그에서 정책 할당 활동을 보는 방법에 대해 알아봅니다.
localization_priority: Normal
f1.keywords:
- CSH
- ms.teamsadmincenter.dashboard.activitylog.overview
ms.custom: ''
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5f85899869a8578df59516d0e0d702f8e36bd951
ms.sourcegitcommit: 47637ed816b471fe689e7bdac27b73e6efced60c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/27/2020
ms.locfileid: "44374296"
---
# <a name="view-your-policy-assignments-in-the-activity-log"></a><span data-ttu-id="7d23c-103">활동 로그에서 정책 과제 보기</span><span class="sxs-lookup"><span data-stu-id="7d23c-103">View your policy assignments in the Activity log</span></span>

<span data-ttu-id="7d23c-104">Microsoft 팀 관리 센터에서 사용자에 게 정책을 할당 하면 활동 로그에서 해당 정책 할당의 상태를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d23c-104">When you assign policies to users in the Microsoft Teams admin center, you can view the status of those policy assignments in the Activity log.</span></span> <span data-ttu-id="7d23c-105">활동 로그에는 지난 30 일간 Microsoft 팀 관리 센터를 통해 20 명 이상의 사용자 일괄 처리에 대 한 정책 할당이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d23c-105">The Activity log shows policy assignments to batches of more than 20 users through the Microsoft Teams admin center from the last 30 days.</span></span> <span data-ttu-id="7d23c-106">활동 로그에는 정책 패키지 할당이 표시 되지 않으며, Microsoft 팀 관리 센터를 통해 20 명 미만의 사용자의 일괄 처리에 대 한 정책 할당 또는 PowerShell을 통한 정책 할당에는 아무런 변화가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7d23c-106">Keep in mind that the Activity log doesn't show policy package assignments, policy assignments to batches of less than 20 users through the Microsoft Teams admin center, or policy assignments through PowerShell.</span></span>

![활동 로그 페이지 스크린샷](media/activity-log.png)

## <a name="view-your-policy-assignment-activities-in-the-activity-log"></a><span data-ttu-id="7d23c-108">활동 로그에서 정책 할당 활동 보기</span><span class="sxs-lookup"><span data-stu-id="7d23c-108">View your policy assignment activities in the Activity log</span></span>

<span data-ttu-id="7d23c-109">활동 로그에서 정책 할당을 보려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d23c-109">To view your policy assignments in the Activity log:</span></span>

1. <span data-ttu-id="7d23c-110">Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **대시보드로**이동한 다음 **활동 로그**에서 **세부 정보 보기**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d23c-110">In the left navigation of the Microsoft Teams admin center, go to **Dashboard**, and then under **Activity Log**, select **View details**.</span></span>
2. <span data-ttu-id="7d23c-111">모든 정책 할당을 확인 하거나 상태별로 목록을 필터링 하 여 시작, **진행**중 또는 완료 **되지**않은 배정만 표시할 수 있습니다. **Completed**</span><span class="sxs-lookup"><span data-stu-id="7d23c-111">You can view all policy assignments or filter the list by status to show only assignments that are **Not started**, **In progress**, or **Completed**.</span></span> <span data-ttu-id="7d23c-112">각 과제에 대 한 다음 정보가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d23c-112">You'll see the following information about each assignment:</span></span>
    - <span data-ttu-id="7d23c-113">**Name**: 정책 할당의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="7d23c-113">**Name**: The name of the policy assignment.</span></span> <span data-ttu-id="7d23c-114">링크를 클릭 하 여 자세한 정보를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d23c-114">Click the link to view more details.</span></span> <span data-ttu-id="7d23c-115">여기에는 정책에 할당 된 사용자 수와 완료 된 배정 수 (진행 중) 및 시작 되지 않음이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d23c-115">This includes the number of users the policy was assigned to and the number of assignments completed, in progress, and not started.</span></span> <span data-ttu-id="7d23c-116">또한 일괄 작업의 사용자 목록과 각 사용자의 상태 및 결과를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d23c-116">You'll also see the list of users in the batch, and the status and result for each user.</span></span> <span data-ttu-id="7d23c-117">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="7d23c-117">Here's an example:</span></span>

        ![의 스크린샷](media/activity-log-policy-assignment-detail.png)

    - <span data-ttu-id="7d23c-119">**제출**: 정책 할당이 제출 된 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="7d23c-119">**Submitted**: Date and time the policy assignment was submitted.</span></span>
    - <span data-ttu-id="7d23c-120">**완료 시간**: 정책 할당이 완료 된 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="7d23c-120">**Completion time**: Date and time the policy assignment was completed.</span></span>
    - <span data-ttu-id="7d23c-121">**영향**: 일괄 작업의 사용자 수입니다.</span><span class="sxs-lookup"><span data-stu-id="7d23c-121">**Impact on**: Number of users in the batch.</span></span>
    - <span data-ttu-id="7d23c-122">**전체 상태**: 정책 할당의 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="7d23c-122">**Overall status**: Status of the policy assignment.</span></span>

> [!NOTE]
> <span data-ttu-id="7d23c-123">**사용자** 페이지에서 활동 로그로 이동할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d23c-123">You can also get to the Activity log from the **Users** page.</span></span> <span data-ttu-id="7d23c-124">**적용** 을 클릭 하 여 대량 정책 할당을 제출 하면 페이지 맨 위에 배너가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d23c-124">After you click **Apply** to submit a bulk policy assignment, you'll see a banner at the top of the page.</span></span> <span data-ttu-id="7d23c-125">배너에서 **활동 로그** 링크를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d23c-125">Click the **Activity log** link in the banner.</span></span>

## <a name="related-topics"></a><span data-ttu-id="7d23c-126">관련 항목</span><span class="sxs-lookup"><span data-stu-id="7d23c-126">Related topics</span></span>

- [<span data-ttu-id="7d23c-127">사용자에 게 정책 할당</span><span class="sxs-lookup"><span data-stu-id="7d23c-127">Assign policies to users</span></span>](assign-policies.md)
