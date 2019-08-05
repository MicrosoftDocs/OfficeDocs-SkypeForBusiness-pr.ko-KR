---
title: ) 비즈니스용 Skype에서 응답 그룹 업무 시간 정의
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d62551b2-1847-4e1b-abe8-683b72aa94d5
description: 비즈니스용 Skype Server Enterprise Voice에서 응답 그룹 업무 시간을 만들거나 수정 합니다.
ms.openlocfilehash: 9f00e89bede48af8c36de93da951df9b69a692e1
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36197708"
---
# <a name="optional-define-response-group-business-hours-in-skype-for-business"></a><span data-ttu-id="900ea-103">) 비즈니스용 Skype에서 응답 그룹 업무 시간 정의</span><span class="sxs-lookup"><span data-stu-id="900ea-103">(Optional) Define Response Group business hours in Skype for Business</span></span> 
 
<span data-ttu-id="900ea-104">비즈니스용 Skype Server Enterprise Voice에서 응답 그룹 업무 시간을 만들거나 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="900ea-104">Create or modify Response Group business hours, in Skype for Business Server Enterprise Voice.</span></span>
  
## <a name="defining-business-hours"></a><span data-ttu-id="900ea-105">업무 시간 정의</span><span class="sxs-lookup"><span data-stu-id="900ea-105">Defining Business Hours</span></span>

<span data-ttu-id="900ea-106">비즈니스 시간 설정 워크플로를 전화를 받을 수 있는 시간을 정의 하 고 업무 시간 외의 통화에 대해 수행할 작업을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="900ea-106">Business hour settings define when the workflow is available to answer calls and specify the actions to take for calls outside of business hours.</span></span> <span data-ttu-id="900ea-107">응답 그룹 관리자는 **새 CsRgsHoursOfBusiness** cmdlet을 사용 하 여 여러 응답 그룹에 사용할 수 있는 미리 정의 된 일정을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="900ea-107">Response Group administrators can use the **New-CsRgsHoursOfBusiness** cmdlet to create predefined schedules that you can use for any number of response groups.</span></span>
  
> [!TIP]
> <span data-ttu-id="900ea-108">워크플로를 만들거나 수정할 때 해당 워크플로에만 적용 되는 사용자 지정 일정을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="900ea-108">When you create or modify a workflow, you can specify a custom schedule that applies only to that workflow.</span></span> <span data-ttu-id="900ea-109">자세한 내용은 비즈니스용 [Skype에서 응답 그룹 워크플로 디자인 및 만들기](designing-and-creating-response-group-workflows.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="900ea-109">For details, see [Designing and creating response group workflows in Skype for Business](designing-and-creating-response-group-workflows.md).</span></span> 
  
> [!NOTE]
> <span data-ttu-id="900ea-110">워크플로가 관리 워크플로로 정의 된 경우 CsResponseGroupManager 역할에 할당 된 모든 사용자가 자신이 관리 하는 워크플로에 대 한 사용자 지정 업무 시간을 설정 하 고 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="900ea-110">If a workflow is defined as a Managed workflow, then any user who is assigned the CsResponseGroupManager role can set and modify custom business hours for workflows that they manage.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="900ea-111">다음 cmdlet의 매개 변수에 24 시간 표시법을 사용 합니다 (예: 20:00 = 8:00 P.M.).</span><span class="sxs-lookup"><span data-stu-id="900ea-111">Use 24-hour notation for the parameters in the following cmdlets (for example, 20:00=8:00 P.M.).</span></span> 
  
### <a name="to-create-a-predefined-business-hours-collection"></a><span data-ttu-id="900ea-112">미리 정의 된 업무 시간 모음을 만들려면</span><span class="sxs-lookup"><span data-stu-id="900ea-112">To create a predefined business hours collection</span></span>

1. <span data-ttu-id="900ea-113">RTCUniversalServerAdmins 그룹의 구성원 또는 응답 그룹을 지 원하는 미리 정의 된 관리 역할 중 하나의 구성원으로 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="900ea-113">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>
    
2. <span data-ttu-id="900ea-114">비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **비즈니스용 skype 2015**을 차례로 클릭 한 다음 비즈니스용 **skype Server management Shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="900ea-114">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="900ea-115">정의 하려는 각 시간 범위에 대해 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="900ea-115">For each unique range of hours you want to define, run:</span></span>
    
   ```
   $x = New-CsRgsTimeRange [-Name <name of time range>] -OpenTime <time when business hours begin> -CloseTime <time when business hours end>
   ```

    <span data-ttu-id="900ea-116">정의한 범위를 사용 하는 업무 시간 컬렉션을 만들려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="900ea-116">To create the business hours collection that uses the ranges you defined, run:</span></span>
    
   ```
   New-CsRgsHoursOfBusiness -Parent <service where the workflow is hosted> -Name <unique name for collection> [-MondayHours1 <first set of opening and closing times for Monday>] [-MondayHours2 <second set of opening and closing times for Monday>] [-TuesdayHours1 <first set of opening and closing times for Tuesday>] [-TuesdayHours2 <second set of opening and closing times for Tuesday>] [-WednesdayHours1 <first set of opening and closing times for Wednesday>] [-WednesdayHours2 <second set of opening and closing times for Wednesday>] [-ThursdayHours1 <first set of opening and closing times for Thursday>] [-ThursdayHours2 <second set of opening and closing times for Thursday>] [-FridayHours1 <first set of opening and closing times for Friday>] [-FridayHours2 <second set of opening and closing times for Friday>] [-SaturdayHours1 <first set of opening and closing times for Saturday>] [-SaturdayHours2 <second set of opening and closing times for Saturday>] [-SundayHours1 <first set of opening and closing times for Sunday>] [-SundayHours2 <second set of opening and closing times for Sunday>]
   ```

    <span data-ttu-id="900ea-117">다음 예에서는 근무 시간 오전 9:00를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="900ea-117">The following example specifies business hours of 9:00 A.M.</span></span> <span data-ttu-id="900ea-118">5:00 P.M.</span><span class="sxs-lookup"><span data-stu-id="900ea-118">to 5:00 P.M.</span></span> <span data-ttu-id="900ea-119">평일, 오전 8:00</span><span class="sxs-lookup"><span data-stu-id="900ea-119">for weekdays, 8:00 A.M.</span></span> <span data-ttu-id="900ea-120">오전 10:00</span><span class="sxs-lookup"><span data-stu-id="900ea-120">to 10:00 A.M.</span></span> <span data-ttu-id="900ea-121">2:00 P.M.부터 다시 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="900ea-121">and again from 2:00 P.M.</span></span> <span data-ttu-id="900ea-122">6:00 P.M.</span><span class="sxs-lookup"><span data-stu-id="900ea-122">to 6:00 P.M.</span></span> <span data-ttu-id="900ea-123">토요일과 일요일에 대 한 업무 시간 없음:</span><span class="sxs-lookup"><span data-stu-id="900ea-123">for Saturdays, and no business hours for Sundays:</span></span>
    
   ```
   $a = New-CSRgsTimeRange -Name "Weekday Hours" -OpenTime "9:00" -CloseTime "17:00"
   $b = New-CSRgsTimeRange -Name "Saturday Morning Hours" -OpenTime "8:00" -CloseTime "10:00" 
   $c = New-CSRgsTimeRange -Name "Saturday Afternoon Hours" -OpenTime "14:00" -CloseTime "18:00" 
   New-CsRgsHoursOfBusiness -Parent "ApplicationServer:Redmond.contoso.com" -Name "Help Desk Business Hours" -MondayHours1 $a -TuesdayHours1 $a -WednesdayHours1 $a -ThursdayHours1 $a -FridayHours1 $a -SaturdayHours1 $b -SaturdayHours2 $c
   ```

## <a name="see-also"></a><span data-ttu-id="900ea-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="900ea-124">See also</span></span>

[<span data-ttu-id="900ea-125">새로운 CsRgsTimeRange</span><span class="sxs-lookup"><span data-stu-id="900ea-125">New-CsRgsTimeRange</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csrgstimerange?view=skype-ps)
  
[<span data-ttu-id="900ea-126">새로운 CsRgsHoursOfBusiness</span><span class="sxs-lookup"><span data-stu-id="900ea-126">New-CsRgsHoursOfBusiness</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csrgshoursofbusiness?view=skype-ps)
