---
title: (선택 사항) 비즈니스용 Skype에서 응답 그룹 업무 시간 정의
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d62551b2-1847-4e1b-abe8-683b72aa94d5
description: 비즈니스용 Skype 서버 2016에서 응답 그룹 업무 시간을 만들거나 Enterprise Voice.
ms.openlocfilehash: dcd2f7174a75eb68ef8d35759a1e454ede976bde
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830998"
---
# <a name="optional-define-response-group-business-hours-in-skype-for-business"></a><span data-ttu-id="92403-103">(선택 사항) 비즈니스용 Skype에서 응답 그룹 업무 시간 정의</span><span class="sxs-lookup"><span data-stu-id="92403-103">(Optional) Define Response Group business hours in Skype for Business</span></span> 
 
<span data-ttu-id="92403-104">비즈니스용 Skype 서버 2016에서 응답 그룹 업무 시간을 만들거나 Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="92403-104">Create or modify Response Group business hours, in Skype for Business Server Enterprise Voice.</span></span>
  
## <a name="defining-business-hours"></a><span data-ttu-id="92403-105">업무 시간 정의</span><span class="sxs-lookup"><span data-stu-id="92403-105">Defining Business Hours</span></span>

<span data-ttu-id="92403-106">업무 시간 설정에서는 워크플로를 사용하여 통화에 응답할 수 있는 시간을 정의하고 업무 시간 외에 통화에 대해 수행할 작업을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="92403-106">Business hour settings define when the workflow is available to answer calls and specify the actions to take for calls outside of business hours.</span></span> <span data-ttu-id="92403-107">응답 그룹 관리자는 **New-CsRgsHoursOfBusiness** cmdlet를 사용하여 임의의 응답 그룹에 사용할 수 있는 미리 정의된 일정을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92403-107">Response Group administrators can use the **New-CsRgsHoursOfBusiness** cmdlet to create predefined schedules that you can use for any number of response groups.</span></span>
  
> [!TIP]
> <span data-ttu-id="92403-108">워크플로를 만들거나 수정할 때 해당 워크플로에만 적용되는 사용자 지정 일정을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92403-108">When you create or modify a workflow, you can specify a custom schedule that applies only to that workflow.</span></span> <span data-ttu-id="92403-109">자세한 내용은 비즈니스용 Skype에서 응답 그룹 워크플로 디자인 [및 만들기를 참조하세요.](designing-and-creating-response-group-workflows.md)</span><span class="sxs-lookup"><span data-stu-id="92403-109">For details, see [Designing and creating response group workflows in Skype for Business](designing-and-creating-response-group-workflows.md).</span></span> 
  
> [!NOTE]
> <span data-ttu-id="92403-110">워크플로가 관리 워크플로로 정의되는 경우 CsResponseGroupManager 역할에 할당된 사용자는 관리할 워크플로의 사용자 지정 업무 시간을 설정하고 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92403-110">If a workflow is defined as a Managed workflow, then any user who is assigned the CsResponseGroupManager role can set and modify custom business hours for workflows that they manage.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="92403-111">다음 cmdlet의 매개 변수에 24시간 표기법을 사용하십시오(예: 20:00=오후 8:00).</span><span class="sxs-lookup"><span data-stu-id="92403-111">Use 24-hour notation for the parameters in the following cmdlets (for example, 20:00=8:00 P.M.).</span></span> 
  
### <a name="to-create-a-predefined-business-hours-collection"></a><span data-ttu-id="92403-112">미리 정의된 업무 시간 컬렉션을 만들려면</span><span class="sxs-lookup"><span data-stu-id="92403-112">To create a predefined business hours collection</span></span>

1. <span data-ttu-id="92403-113">RTCUniversalServerAdmins 그룹의 구성원으로 로그온하거나 응답 그룹을 지원하는 미리 정의한 관리 역할 중 하나의 구성원으로 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="92403-113">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>
    
2. <span data-ttu-id="92403-114">비즈니스용 Skype 서버 관리 셸 시작: **시작,** **모든** 프로그램, 비즈니스용 **Skype 2015,** 비즈니스용 Skype 서버 관리 셸을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="92403-114">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="92403-115">정의할 각 고유 시간 범위에 대해 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="92403-115">For each unique range of hours you want to define, run:</span></span>
    
   ```powershell
   $x = New-CsRgsTimeRange [-Name <name of time range>] -OpenTime <time when business hours begin> -CloseTime <time when business hours end>
   ```

    <span data-ttu-id="92403-116">정의한 범위를 사용하는 업무 시간 컬렉션을 만들려면 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="92403-116">To create the business hours collection that uses the ranges you defined, run:</span></span>
    
   ```powershell
   New-CsRgsHoursOfBusiness -Parent <service where the workflow is hosted> -Name <unique name for collection> [-MondayHours1 <first set of opening and closing times for Monday>] [-MondayHours2 <second set of opening and closing times for Monday>] [-TuesdayHours1 <first set of opening and closing times for Tuesday>] [-TuesdayHours2 <second set of opening and closing times for Tuesday>] [-WednesdayHours1 <first set of opening and closing times for Wednesday>] [-WednesdayHours2 <second set of opening and closing times for Wednesday>] [-ThursdayHours1 <first set of opening and closing times for Thursday>] [-ThursdayHours2 <second set of opening and closing times for Thursday>] [-FridayHours1 <first set of opening and closing times for Friday>] [-FridayHours2 <second set of opening and closing times for Friday>] [-SaturdayHours1 <first set of opening and closing times for Saturday>] [-SaturdayHours2 <second set of opening and closing times for Saturday>] [-SundayHours1 <first set of opening and closing times for Sunday>] [-SundayHours2 <second set of opening and closing times for Sunday>]
   ```

    <span data-ttu-id="92403-p103">다음 예에서는 평일 오전 9시~오후 5시, 토요일 오전 8시~오전 10시와 오후 2시~오후 6시를 업무 시간으로 지정하고 일요일은 휴무로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="92403-p103">The following example specifies business hours of 9:00 A.M. to 5:00 P.M. for weekdays, 8:00 A.M. to 10:00 A.M. and again from 2:00 P.M. to 6:00 P.M. for Saturdays, and no business hours for Sundays:</span></span>
    
   ```powershell
   $a = New-CSRgsTimeRange -Name "Weekday Hours" -OpenTime "9:00" -CloseTime "17:00"
   $b = New-CSRgsTimeRange -Name "Saturday Morning Hours" -OpenTime "8:00" -CloseTime "10:00" 
   $c = New-CSRgsTimeRange -Name "Saturday Afternoon Hours" -OpenTime "14:00" -CloseTime "18:00" 
   New-CsRgsHoursOfBusiness -Parent "ApplicationServer:Redmond.contoso.com" -Name "Help Desk Business Hours" -MondayHours1 $a -TuesdayHours1 $a -WednesdayHours1 $a -ThursdayHours1 $a -FridayHours1 $a -SaturdayHours1 $b -SaturdayHours2 $c
   ```

## <a name="see-also"></a><span data-ttu-id="92403-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="92403-124">See also</span></span>

[<span data-ttu-id="92403-125">New-CsRgsTimeRange</span><span class="sxs-lookup"><span data-stu-id="92403-125">New-CsRgsTimeRange</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csrgstimerange?view=skype-ps)
  
[<span data-ttu-id="92403-126">New-CsRgsHoursOfBusiness</span><span class="sxs-lookup"><span data-stu-id="92403-126">New-CsRgsHoursOfBusiness</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csrgshoursofbusiness?view=skype-ps)
