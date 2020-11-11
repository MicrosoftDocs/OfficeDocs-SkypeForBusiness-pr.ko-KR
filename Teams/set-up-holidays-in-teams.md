---
title: Microsoft 팀에서 휴일 설정
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
description: 자동 전화 교환에 사용할 수 있도록 Microsoft 팀에서 휴일을 설정 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: ff87a3888bc98e1794f8074052aae4c0bbe3545d
ms.sourcegitcommit: 247b2587a60b1609947310ec82d51f47cf829703
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/11/2020
ms.locfileid: "48993474"
---
# <a name="set-up-holidays-in-microsoft-teams"></a><span data-ttu-id="3f5e4-103">Microsoft 팀에서 휴일 설정</span><span class="sxs-lookup"><span data-stu-id="3f5e4-103">Set up holidays in Microsoft Teams</span></span>

<span data-ttu-id="3f5e4-104">팀 공휴일 기능을 사용 하 여 부서, 통화 대기열 또는 조직의 사용자가 다른 근무 시간을 초과 하거나 사용할 수 없는 경우 특정 날짜와 시간에 대 한 대체 메시지와 라우팅을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f5e4-104">You can use the Teams Holidays feature to provide alternate messages and routing to callers for specific dates and times when departments, call queues or people in your organization will be following different working hours or won't be available.</span></span> <span data-ttu-id="3f5e4-105">예를 들어 조직을 닫을 수 있는 날에는 새 연도의 휴일을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f5e4-105">For example, you might create a holiday for New Year's day when your organization may be closed.</span></span>

<span data-ttu-id="3f5e4-106">여기서 만든 휴일은 고유한 인사말과 통화 회람 설정을 사용 하 여 [자동 전화 교환을 설정한](create-a-phone-system-auto-attendant.md)경우 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f5e4-106">The holidays you create here are available when you [set up an auto attendant](create-a-phone-system-auto-attendant.md), each with its own greeting and call routing settings.</span></span>

## <a name="create-a-holiday"></a><span data-ttu-id="3f5e4-107">명절 만들기</span><span class="sxs-lookup"><span data-stu-id="3f5e4-107">Create a holiday</span></span>

<span data-ttu-id="3f5e4-108">명절을 만들려면</span><span class="sxs-lookup"><span data-stu-id="3f5e4-108">To create a holiday</span></span>

1. <span data-ttu-id="3f5e4-109">Microsoft 팀 관리 센터에서 **조직 전체 설정**  >  **공휴일** 으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f5e4-109">In the Microsoft Teams admin center, go to **Org-wide settings** > **Holidays**.</span></span>

2. <span data-ttu-id="3f5e4-110">**새 공휴일** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f5e4-110">Select **New holiday**.</span></span>

3. <span data-ttu-id="3f5e4-111">명절의 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f5e4-111">Enter a name for the holiday.</span></span>

4. <span data-ttu-id="3f5e4-112">**새 날짜 추가** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f5e4-112">Select **Add new date**.</span></span>

5. <span data-ttu-id="3f5e4-113">**시작 시간** 에서 일정 아이콘을 선택 하 고 휴일을 시작할 날짜를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f5e4-113">Under **Start time** , select the calendar icon and choose the date when you'd like the holiday to begin.</span></span>

6. <span data-ttu-id="3f5e4-114">드롭다운 목록을 사용 하 여 휴일 시작 시간을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f5e4-114">Use the drop-down list to select a start time for the holiday.</span></span>

7. <span data-ttu-id="3f5e4-115">**종료 시간** 에서 달력 아이콘을 선택 하 고 휴일을 끝낼 날짜를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f5e4-115">Under **End time** , select the calendar icon and choose the date when you'd like the holiday to end.</span></span>

8. <span data-ttu-id="3f5e4-116">드롭다운 목록을 사용 하 여 공휴일의 종료 시간을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f5e4-116">Use the drop-down list to select an end time for the holiday.</span></span> <span data-ttu-id="3f5e4-117">**종료 시간은** **시작 시간** 이후 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f5e4-117">The **End time** must be after the **Start time**.</span></span>  

   > [!NOTE]
   > <span data-ttu-id="3f5e4-118">공휴일이 하루 종일 (24 시간 기간) 인 경우 **종료 시간은** 다음 날짜로 설정 하 고 오전 12:00에 대 한 시간 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f5e4-118">If the holiday is for one full day (i.e., a 24 hour period), the **End time** should be set to the next day and the time to 12:00 AM.</span></span> <span data-ttu-id="3f5e4-119">예를 들어 새 연도의 하루에 대해 조직이 1 월 1 일에 마감 되는 경우 **시작 시간** 을 오전 1 월 1 12:00 일로 설정 하 고 **종료 시간** 을 1 월 2 @ 12:00 am으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f5e4-119">For example, if your organization is closed on January 1 for New Year's day, set the **Start time** to January 1 12:00 AM and set the **End time** to January 2 @ 12:00 AM.</span></span>

9. <span data-ttu-id="3f5e4-120">필요에 따라 되풀이 휴일에 대 한 날짜를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f5e4-120">Optionally, add more dates for recurring holidays.</span></span>

10. <span data-ttu-id="3f5e4-121">**저장** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f5e4-121">Select **Save**.</span></span>

    ![3 년 동안 날짜가 설정 된 휴일 사용자 인터페이스 스크린샷](media/holidays-set-up.png)

## <a name="change-a-holiday"></a><span data-ttu-id="3f5e4-123">휴일 변경</span><span class="sxs-lookup"><span data-stu-id="3f5e4-123">Change a holiday</span></span>

<span data-ttu-id="3f5e4-124">휴일을 변경 하려면</span><span class="sxs-lookup"><span data-stu-id="3f5e4-124">To change a holiday</span></span>

1. <span data-ttu-id="3f5e4-125">Microsoft 팀 관리 센터에서 **조직 전체 설정**  >  **공휴일** 으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f5e4-125">In the Microsoft Teams admin center, go to **Org-wide settings** > **Holidays**.</span></span>

2. <span data-ttu-id="3f5e4-126">목록에서 공휴일을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f5e4-126">Select the holiday from the list.</span></span>

3. <span data-ttu-id="3f5e4-127">**시작 시간** 에서 일정 아이콘을 선택 하 고 휴일을 시작할 날짜를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f5e4-127">Under **Start time** , select the calendar icon and choose the date when you'd like the holiday to begin.</span></span>

4. <span data-ttu-id="3f5e4-128">드롭다운 목록을 사용 하 여 휴일 시작 시간을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f5e4-128">Use the drop-down list to select a start time for the holiday.</span></span>

5. <span data-ttu-id="3f5e4-129">**종료 시간** 에서 달력 아이콘을 선택 하 고 휴일을 끝낼 날짜를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f5e4-129">Under **End time** , select the calendar icon and choose the date when you'd like the holiday to end.</span></span> 

6. <span data-ttu-id="3f5e4-130">드롭다운 목록을 사용 하 여 공휴일의 종료 시간을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f5e4-130">Use the drop-down list to select an end time for the holiday.</span></span> <span data-ttu-id="3f5e4-131">**종료 시간은** **시작 시간** 이후 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f5e4-131">The **End time** must be after the **Start time**.</span></span>  

7. <span data-ttu-id="3f5e4-132">**저장** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f5e4-132">Select **Save**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="3f5e4-133">관련 주제</span><span class="sxs-lookup"><span data-stu-id="3f5e4-133">Related topics</span></span>

<span data-ttu-id="3f5e4-134">[팀 자동 전화 교환 및 통화 대기열에 대 한 계획](plan-auto-attendant-call-queue.md)</span><span class="sxs-lookup"><span data-stu-id="3f5e4-134">[Plan for Teams auto attendants and call queues](plan-auto-attendant-call-queue.md)?</span></span>
