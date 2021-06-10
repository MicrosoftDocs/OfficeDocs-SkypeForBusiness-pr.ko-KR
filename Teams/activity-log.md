---
title: 관리 센터의 활동 로그에서 정책 Microsoft Teams 보기
author: cichur
ms.author: v-cichur
ms.reviewer: jastark
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: 관리 센터의 활동 로그에서 정책 할당 활동을 보는 Microsoft Teams 대해 자세히 알아보습니다.
localization_priority: Normal
f1.keywords:
- CSH
- ms.teamsadmincenter.dashboard.activitylog.overview
ms.custom: ''
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2a8d1d49d187808b768b4a92c64c4e667ca0ea8f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821318"
---
# <a name="view-your-policy-assignments-in-the-activity-log"></a><span data-ttu-id="42adf-103">활동 로그에서 정책 할당 보기</span><span class="sxs-lookup"><span data-stu-id="42adf-103">View your policy assignments in the Activity log</span></span>

<span data-ttu-id="42adf-104">관리 센터의 사용자에게 정책을 Microsoft Teams 경우 활동 로그에서 해당 정책 할당의 상태를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42adf-104">When you assign policies to users in the Microsoft Teams admin center, you can view the status of those policy assignments in the Activity log.</span></span> <span data-ttu-id="42adf-105">활동 로그는 지난 30일 동안 관리 센터를 통해 20명 Microsoft Teams 일괄 처리에 대한 정책 할당을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="42adf-105">The Activity log shows policy assignments to batches of more than 20 users through the Microsoft Teams admin center from the last 30 days.</span></span> <span data-ttu-id="42adf-106">활동 로그는 PowerShell을 통해 정책 패키지 할당, 20명 미만의 사용자 일괄 처리에 대한 정책 할당을 Microsoft Teams 없습니다.</span><span class="sxs-lookup"><span data-stu-id="42adf-106">Keep in mind that the Activity log doesn't show policy package assignments, policy assignments to batches of less than 20 users through the Microsoft Teams admin center, or policy assignments through PowerShell.</span></span>

![활동 로그 페이지의 스크린샷](media/activity-log.png)

## <a name="view-your-policy-assignment-activities-in-the-activity-log"></a><span data-ttu-id="42adf-108">활동 로그에서 정책 할당 활동 보기</span><span class="sxs-lookup"><span data-stu-id="42adf-108">View your policy assignment activities in the Activity log</span></span>

<span data-ttu-id="42adf-109">활동 로그에서 정책 할당을 확인하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="42adf-109">To view your policy assignments in the Activity log:</span></span>

1. <span data-ttu-id="42adf-110">관리 센터의 왼쪽 탐색에서 Microsoft Teams 대시보드로 이동한 다음 활동 로그에서 **세부** **정보 보기를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="42adf-110">In the left navigation of the Microsoft Teams admin center, go to **Dashboard**, and then under **Activity Log**, select **View details**.</span></span>
2. <span data-ttu-id="42adf-111">모든 정책 할당을 보거나 상태를 통해 목록을 필터링하여 시작되지 않은  **과제,** 진행 중 또는 완료된 과제만 **표시할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="42adf-111">You can view all policy assignments or filter the list by status to show only assignments that are **Not started**, **In progress**, or **Completed**.</span></span> <span data-ttu-id="42adf-112">각 과제에 대한 다음 정보가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="42adf-112">You'll see the following information about each assignment:</span></span>
    - <span data-ttu-id="42adf-113">**이름**: 정책 할당의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="42adf-113">**Name**: The name of the policy assignment.</span></span> <span data-ttu-id="42adf-114">링크를 클릭하여 자세한 내용을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42adf-114">Click the link to view more details.</span></span> <span data-ttu-id="42adf-115">여기에는 정책이 할당된 사용자 수와 완료된 과제 수가 포함되고 진행 중입니다.</span><span class="sxs-lookup"><span data-stu-id="42adf-115">This includes the number of users the policy was assigned to and the number of assignments completed, in progress, and not started.</span></span> <span data-ttu-id="42adf-116">또한 일괄 처리의 사용자 목록과 각 사용자의 상태 및 결과가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="42adf-116">You'll also see the list of users in the batch, and the status and result for each user.</span></span> <span data-ttu-id="42adf-117">다음은 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="42adf-117">Here's an example:</span></span>

        ![스크린샷](media/activity-log-policy-assignment-detail.png)

    - <span data-ttu-id="42adf-119">**제출**: 정책 할당이 제출된 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="42adf-119">**Submitted**: Date and time the policy assignment was submitted.</span></span>
    - <span data-ttu-id="42adf-120">**완료 시간**: 정책 할당이 완료된 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="42adf-120">**Completion time**: Date and time the policy assignment was completed.</span></span>
    - <span data-ttu-id="42adf-121">**영향**: 일괄 처리의 사용자 수입니다.</span><span class="sxs-lookup"><span data-stu-id="42adf-121">**Impact on**: Number of users in the batch.</span></span>
    - <span data-ttu-id="42adf-122">**전체 상태**: 정책 할당의 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="42adf-122">**Overall status**: Status of the policy assignment.</span></span>

> [!NOTE]
> <span data-ttu-id="42adf-123">사용자 페이지에서 활동 로그에 **얻을** 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42adf-123">You can also get to the Activity log from the **Users** page.</span></span> <span data-ttu-id="42adf-124">적용을  클릭하여 대량 정책 할당을 제출하면 페이지 맨 위에 배너가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="42adf-124">After you click **Apply** to submit a bulk policy assignment, you'll see a banner at the top of the page.</span></span> <span data-ttu-id="42adf-125">**배너에서 활동 로그** 링크를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="42adf-125">Click the **Activity log** link in the banner.</span></span>

## <a name="related-topics"></a><span data-ttu-id="42adf-126">관련 항목</span><span class="sxs-lookup"><span data-stu-id="42adf-126">Related topics</span></span>

- [<span data-ttu-id="42adf-127">사용자에게 정책 할당</span><span class="sxs-lookup"><span data-stu-id="42adf-127">Assign policies to users</span></span>](assign-policies.md)
