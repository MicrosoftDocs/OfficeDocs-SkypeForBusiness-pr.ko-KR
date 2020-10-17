---
title: 'Lync Server 2013: (선택 사항) 응답 그룹 업무 시간 정의'
description: 'Lync Server 2013: (선택 사항) 응답 그룹 업무 시간을 정의 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: (Optional) Define Response Group business hours
ms:assetid: d62551b2-1847-4e1b-abe8-683b72aa94d5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205291(v=OCS.15)
ms:contentKeyID: 48185504
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d5780ee362ff11fc4b6fe2ccf8f119f35d0bee36
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565774"
---
# <a name="optional-define-response-group-business-hours-in-lync-server-2013"></a><span data-ttu-id="9765a-103">반드시 Lync Server 2013에서 응답 그룹 업무 시간 정의</span><span class="sxs-lookup"><span data-stu-id="9765a-103">(Optional) Define Response Group business hours in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9765a-104">_**마지막으로 수정 된 항목:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="9765a-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<div>

## <a name="defining-business-hours"></a><span data-ttu-id="9765a-105">업무 시간 정의</span><span class="sxs-lookup"><span data-stu-id="9765a-105">Defining Business Hours</span></span>

<span data-ttu-id="9765a-106">업무 시간 설정에서는 워크플로를 사용하여 통화에 응답할 수 있는 시간을 정의하고 업무 시간 외에 통화에 대해 수행할 작업을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9765a-106">Business hour settings define when the workflow is available to answer calls and specify the actions to take for calls outside of business hours.</span></span> <span data-ttu-id="9765a-107">응답 그룹 관리자는 **New-CsRgsHoursOfBusiness** cmdlet를 사용하여 임의의 응답 그룹에 사용할 수 있는 미리 정의된 일정을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9765a-107">Response Group administrators can use the **New-CsRgsHoursOfBusiness** cmdlet to create predefined schedules that you can use for any number of response groups.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="9765a-108">워크플로를 만들거나 수정할 때 해당 워크플로에만 적용되는 사용자 지정 일정을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9765a-108">When you create or modify a workflow, you can specify a custom schedule that applies only to that workflow.</span></span> <span data-ttu-id="9765a-109">자세한 내용은 Lync server <A href="lync-server-2013-create-or-modify-a-hunt-group-workflow.md">2013에서 헌트 그룹 워크플로 만들기 또는 수정</A> 또는 <A href="lync-server-2013-create-or-modify-an-interactive-workflow.md">lync server 2013에서 대화형 워크플로 만들기 또는 수정</A>를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9765a-109">For details, see <A href="lync-server-2013-create-or-modify-a-hunt-group-workflow.md">Create or modify a hunt group workflow in Lync Server 2013</A> or <A href="lync-server-2013-create-or-modify-an-interactive-workflow.md">Create or modify an interactive workflow in Lync Server 2013</A>.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="9765a-110">워크플로가 관리 워크플로로 정의되는 경우 CsResponseGroupManager 역할에 할당된 사용자는 관리할 워크플로의 사용자 지정 업무 시간을 설정하고 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9765a-110">If a workflow is defined as a Managed workflow, then any user who is assigned the CsResponseGroupManager role can set and modify custom business hours for workflows that they manage.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="9765a-111">다음 cmdlet의 매개 변수에 24시간 표기법을 사용하십시오(예: 20:00=오후 8:00).</span><span class="sxs-lookup"><span data-stu-id="9765a-111">Use 24-hour notation for the parameters in the following cmdlets (for example, 20:00=8:00 P.M.).</span></span>



</div>

<div>

## <a name="to-create-a-predefined-business-hours-collection"></a><span data-ttu-id="9765a-112">미리 정의된 업무 시간 컬렉션을 만들려면</span><span class="sxs-lookup"><span data-stu-id="9765a-112">To create a predefined business hours collection</span></span>

1.  <span data-ttu-id="9765a-113">RTCUniversalServerAdmins 그룹의 구성원이 나 응답 그룹을 지 원하는 미리 정의 된 관리 역할 중 하나의 구성원으로 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="9765a-113">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="9765a-114">**시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="9765a-114">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="9765a-115">정의할 각 고유 시간 범위에 대해 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="9765a-115">For each unique range of hours you want to define, run:</span></span>
    
        $x = New-CsRgsTimeRange [-Name <name of time range>] -OpenTime <time when business hours begin> -CloseTime <time when business hours end>
    
    <span data-ttu-id="9765a-116">정의한 범위를 사용하는 업무 시간 컬렉션을 만들려면 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="9765a-116">To create the business hours collection that uses the ranges you defined, run:</span></span>
    
        New-CsRgsHoursOfBusiness -Parent <service where the workflow is hosted> -Name <unique name for collection> [-MondayHours1 <first set of opening and closing times for Monday>] [-MondayHours2 <second set of opening and closing times for Monday>] [-TuesdayHours1 <first set of opening and closing times for Tuesday>] [-TuesdayHours2 <second set of opening and closing times for Tuesday>] [-WednesdayHours1 <first set of opening and closing times for Wednesday>] [-WednesdayHours2 <second set of opening and closing times for Wednesday>] [-ThursdayHours1 <first set of opening and closing times for Thursday>] [-ThursdayHours2 <second set of opening and closing times for Thursday>] [-FridayHours1 <first set of opening and closing times for Friday>] [-FridayHours2 <second set of opening and closing times for Friday>] [-SaturdayHours1 <first set of opening and closing times for Saturday>] [-SaturdayHours2 <second set of opening and closing times for Saturday>] [-SundayHours1 <first set of opening and closing times for Sunday>] [-SundayHours2 <second set of opening and closing times for Sunday>]
    
    <span data-ttu-id="9765a-p103">다음 예에서는 평일 오전 9시~오후 5시, 토요일 오전 8시~오전 10시와 오후 2시~오후 6시를 업무 시간으로 지정하고 일요일은 휴무로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9765a-p103">The following example specifies business hours of 9:00 A.M. to 5:00 P.M. for weekdays, 8:00 A.M. to 10:00 A.M. and again from 2:00 P.M. to 6:00 P.M. for Saturdays, and no business hours for Sundays:</span></span>
    
        $a = NewRgsTimeRange -Name "Weekday Hours" -OpenTime "9:00" -CloseTime "17:00"
        $b = NewRgsTimeRange -Name "Saturday Morning Hours" -OpenTime "8:00" -CloseTime "10:00" 
        $c = NewRgsTimeRange -Name "Saturday Afternoon Hours" -OpenTime "14:00" -CloseTime "18:00" 
        New-CsRgsHoursOfBusiness -Parent "ApplicationServer:Redmond.contoso.com" -Name "Help Desk Business Hours" -MondayHours1 $a -TuesdayHours1 $a -WednesdayHours1 $a -ThursdayHours1 $a -FridayHours1 $a -SaturdayHours1 $b -SaturdayHours2 $c

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="9765a-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9765a-124">See Also</span></span>


[<span data-ttu-id="9765a-125">Lync Server 2013에서 헌트 그룹 워크플로 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="9765a-125">Create or modify a hunt group workflow in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-hunt-group-workflow.md)  
[<span data-ttu-id="9765a-126">Lync Server 2013에서 대화형 워크플로 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="9765a-126">Create or modify an interactive workflow in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-an-interactive-workflow.md)  


[<span data-ttu-id="9765a-127">New-csrgstimerange</span><span class="sxs-lookup"><span data-stu-id="9765a-127">New-CsRgsTimeRange</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsRgsTimeRange)  
[<span data-ttu-id="9765a-128">Get-csrgshoursofbusiness</span><span class="sxs-lookup"><span data-stu-id="9765a-128">New-CsRgsHoursOfBusiness</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsRgsHoursOfBusiness)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

