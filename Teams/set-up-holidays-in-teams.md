---
title: 공휴일을 Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.orgwidesettings.holidays.overview
- seo-marvel-apr2020
description: 자동 참석자와 함께 사용할 수 있도록 Microsoft Teams 공휴일을 설정하는 방법에 대해 자세히 알아보습니다.
ms.openlocfilehash: ff87a3888bc98e1794f8074052aae4c0bbe3545d
ms.sourcegitcommit: 247b2587a60b1609947310ec82d51f47cf829703
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/11/2020
ms.locfileid: "48993474"
---
# <a name="set-up-holidays-in-microsoft-teams"></a><span data-ttu-id="20a99-103">공휴일을 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="20a99-103">Set up holidays in Microsoft Teams</span></span>

<span data-ttu-id="20a99-104">휴일 Teams 기능을 사용하여 부서, 통화 큐 또는 조직의 사용자가 다른 근무 시간을 따라가거나 사용할 수 없는 특정 날짜 및 시간에 대한 대체 메시지 및 발신자 라우팅을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20a99-104">You can use the Teams Holidays feature to provide alternate messages and routing to callers for specific dates and times when departments, call queues or people in your organization will be following different working hours or won't be available.</span></span> <span data-ttu-id="20a99-105">예를 들어 조직이 닫혀 있을 수 있는 새해 날에 대한 공휴일을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20a99-105">For example, you might create a holiday for New Year's day when your organization may be closed.</span></span>

<span data-ttu-id="20a99-106">여기에서 만든 공휴일은 각각 [](create-a-phone-system-auto-attendant.md)자체 인사말 및 통화 라우팅 설정을 사용하여 자동 참석자 설정을 설정할 때 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20a99-106">The holidays you create here are available when you [set up an auto attendant](create-a-phone-system-auto-attendant.md), each with its own greeting and call routing settings.</span></span>

## <a name="create-a-holiday"></a><span data-ttu-id="20a99-107">휴일 만들기</span><span class="sxs-lookup"><span data-stu-id="20a99-107">Create a holiday</span></span>

<span data-ttu-id="20a99-108">공휴일을 만들면</span><span class="sxs-lookup"><span data-stu-id="20a99-108">To create a holiday</span></span>

1. <span data-ttu-id="20a99-109">Microsoft Teams 관리 센터에서 **Org-wide 설정 휴일로**  >  **이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="20a99-109">In the Microsoft Teams admin center, go to **Org-wide settings** > **Holidays**.</span></span>

2. <span data-ttu-id="20a99-110">새 **휴일을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="20a99-110">Select **New holiday**.</span></span>

3. <span data-ttu-id="20a99-111">휴일의 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="20a99-111">Enter a name for the holiday.</span></span>

4. <span data-ttu-id="20a99-112">새 **날짜 추가를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="20a99-112">Select **Add new date**.</span></span>

5. <span data-ttu-id="20a99-113">시작 **시간에서** 일정 아이콘을 선택하고 휴일을 시작할 날짜를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="20a99-113">Under **Start time**, select the calendar icon and choose the date when you'd like the holiday to begin.</span></span>

6. <span data-ttu-id="20a99-114">드롭다운 목록을 사용하여 휴일의 시작 시간을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="20a99-114">Use the drop-down list to select a start time for the holiday.</span></span>

7. <span data-ttu-id="20a99-115">종료 **시간에서** 일정 아이콘을 선택하고 휴일을 종료할 날짜를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="20a99-115">Under **End time**, select the calendar icon and choose the date when you'd like the holiday to end.</span></span>

8. <span data-ttu-id="20a99-116">드롭다운 목록을 사용하여 휴일의 종료 시간을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="20a99-116">Use the drop-down list to select an end time for the holiday.</span></span> <span data-ttu-id="20a99-117">종료 **시간은** 시작 시간 이후에 **되어야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="20a99-117">The **End time** must be after the **Start time**.</span></span>  

   > [!NOTE]
   > <span data-ttu-id="20a99-118">공휴일이 하루(예: 24시간 기간)인 경우 종료  시간은 다음 날로 설정하고 시간은 오전 12:00으로 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="20a99-118">If the holiday is for one full day (i.e., a 24 hour period), the **End time** should be set to the next day and the time to 12:00 AM.</span></span> <span data-ttu-id="20a99-119">예를 들어 조직이 새해 1월 1일로 종료된  경우 시작 시간을 1월 1일 오전 12:00으로 설정하고 종료 시간을 1월 2일 @ 12:00 AM으로 설정합니다. </span><span class="sxs-lookup"><span data-stu-id="20a99-119">For example, if your organization is closed on January 1 for New Year's day, set the **Start time** to January 1 12:00 AM and set the **End time** to January 2 @ 12:00 AM.</span></span>

9. <span data-ttu-id="20a99-120">선택적으로, 공휴일에 대한 날짜를 더 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="20a99-120">Optionally, add more dates for recurring holidays.</span></span>

10. <span data-ttu-id="20a99-121">**저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="20a99-121">Select **Save**.</span></span>

    ![3년 동안 설정된 날짜가 있는 휴일 사용자 인터페이스 스크린샷](media/holidays-set-up.png)

## <a name="change-a-holiday"></a><span data-ttu-id="20a99-123">휴일 변경</span><span class="sxs-lookup"><span data-stu-id="20a99-123">Change a holiday</span></span>

<span data-ttu-id="20a99-124">휴일을 변경하는 경우</span><span class="sxs-lookup"><span data-stu-id="20a99-124">To change a holiday</span></span>

1. <span data-ttu-id="20a99-125">Microsoft Teams 관리 센터에서 **Org-wide 설정 휴일로**  >  **이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="20a99-125">In the Microsoft Teams admin center, go to **Org-wide settings** > **Holidays**.</span></span>

2. <span data-ttu-id="20a99-126">목록에서 휴일을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="20a99-126">Select the holiday from the list.</span></span>

3. <span data-ttu-id="20a99-127">시작 **시간에서** 일정 아이콘을 선택하고 휴일을 시작할 날짜를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="20a99-127">Under **Start time**, select the calendar icon and choose the date when you'd like the holiday to begin.</span></span>

4. <span data-ttu-id="20a99-128">드롭다운 목록을 사용하여 휴일의 시작 시간을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="20a99-128">Use the drop-down list to select a start time for the holiday.</span></span>

5. <span data-ttu-id="20a99-129">종료 **시간에서** 일정 아이콘을 선택하고 휴일을 종료할 날짜를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="20a99-129">Under **End time**, select the calendar icon and choose the date when you'd like the holiday to end.</span></span> 

6. <span data-ttu-id="20a99-130">드롭다운 목록을 사용하여 휴일의 종료 시간을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="20a99-130">Use the drop-down list to select an end time for the holiday.</span></span> <span data-ttu-id="20a99-131">종료 **시간은** 시작 시간 이후에 **되어야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="20a99-131">The **End time** must be after the **Start time**.</span></span>  

7. <span data-ttu-id="20a99-132">**저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="20a99-132">Select **Save**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="20a99-133">관련 항목</span><span class="sxs-lookup"><span data-stu-id="20a99-133">Related topics</span></span>

<span data-ttu-id="20a99-134">[자동 Teams 큐에](plan-auto-attendant-call-queue.md)대한 계획?</span><span class="sxs-lookup"><span data-stu-id="20a99-134">[Plan for Teams auto attendants and call queues](plan-auto-attendant-call-queue.md)?</span></span>
