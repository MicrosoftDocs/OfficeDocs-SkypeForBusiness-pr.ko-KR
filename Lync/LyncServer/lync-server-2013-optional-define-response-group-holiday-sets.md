---
title: 'Lync Server 2013: (선택 사항) 응답 그룹 휴일 집합 정의'
description: 'Lync Server 2013: (선택 사항) 응답 그룹 휴일 집합을 정의 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: (Optional) Define Response Group holiday sets
ms:assetid: 56c37b3b-6517-49b9-86b7-ae48cc349119
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688063(v=OCS.15)
ms:contentKeyID: 49733657
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d7ba735cc62efb9d5553c8bd6aad1aa9484f70f4
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565764"
---
# <a name="optional-define-response-group-holiday-sets-in-lync-server-2013"></a><span data-ttu-id="0c8fc-103">반드시 Lync Server 2013에서 응답 그룹 휴일 집합 정의</span><span class="sxs-lookup"><span data-stu-id="0c8fc-103">(Optional) Define Response Group holiday sets in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0c8fc-104">_**마지막으로 수정 된 항목:** 2014-02-07_</span><span class="sxs-lookup"><span data-stu-id="0c8fc-104">_**Topic Last Modified:** 2014-02-07_</span></span>

<span data-ttu-id="0c8fc-p101">휴일 설정에서는 응답 그룹이 근무하지 않는 요일을 정의하고 해당 요일에 수행할 작업을 지정합니다. 휴일 집합은 응답 그룹에 적용되는 휴일의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="0c8fc-p101">Holiday settings define the days that a response group is closed for business and specify the action to take on those days. A holiday set is the collection of holidays that apply to a response group.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0c8fc-107">워크플로가 관리 워크플로로 정의되었고 모든 사용자가 여기에 지정된 경우, CsResponseGroupManager 역할이 자신이 관리하는 워크플로에 대한 휴일을 설정하고 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c8fc-107">If a workflow is defined as a Managed workflow, then any user is assigned the CsResponseGroupManager role can set and modify holidays for workflows that they manage.</span></span>



</div>

<div>

## <a name="to-create-a-holiday-set"></a><span data-ttu-id="0c8fc-108">휴일 집합을 만들려면</span><span class="sxs-lookup"><span data-stu-id="0c8fc-108">To create a holiday set</span></span>

1.  <span data-ttu-id="0c8fc-109">RTCUniversalServerAdmins 그룹의 구성원이 나 응답 그룹을 지 원하는 미리 정의 된 관리 역할 중 하나의 구성원으로 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c8fc-109">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="0c8fc-110">**시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="0c8fc-110">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="0c8fc-111">정의할 각 휴일에 대해 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="0c8fc-111">For each holiday you want to define, run:</span></span>
    
        $x = New-CsRgsHoliday [-Name <holiday name>] -StartDate <starting date of holiday> -EndDate <ending date of holiday>
    
    <span data-ttu-id="0c8fc-112">정의한 휴일이 포함된 휴일 집합을 만들려면 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="0c8fc-112">To create the holiday set that contains the holidays you defined, run:</span></span>
    
        New-CsRgsHolidaySet -Parent <service where the workflow is hosted> -Name <unique name for holiday set> -HolidayList <one or more holidays to be included in the holiday set>
    
    <span data-ttu-id="0c8fc-113">다음 예에서는 두 개의 휴일이 포함된 휴일 집합을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0c8fc-113">The following example shows a holiday set that includes two holidays:</span></span>
    
        $a = New-CsRgsHoliday -Name "New Year's Day" -StartDate "1/1/2013 12:00 AM" -EndDate "1/1/2013 12:00 AM" 
        $b = New-CsRgsHoliday -Name "Independence Day" -StartDate "7/4/2013 12:00 AM" -EndDate "7/5/2013 12:00 AM" 
        New-CsRgsHolidaySet -Parent "ApplicationServer:Redmond.contoso.com -Name "2013 Holidays" -HolidayList ($a, $b)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="0c8fc-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0c8fc-114">See Also</span></span>


[<span data-ttu-id="0c8fc-115">Lync Server 2013에서 헌트 그룹 워크플로 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="0c8fc-115">Create or modify a hunt group workflow in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-hunt-group-workflow.md)  
[<span data-ttu-id="0c8fc-116">Lync Server 2013에서 대화형 워크플로 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="0c8fc-116">Create or modify an interactive workflow in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-an-interactive-workflow.md)  


[<span data-ttu-id="0c8fc-117">New-csrgsholiday</span><span class="sxs-lookup"><span data-stu-id="0c8fc-117">New-CsRgsHoliday</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsRgsHoliday)  
[<span data-ttu-id="0c8fc-118">New-csrgsholidayset</span><span class="sxs-lookup"><span data-stu-id="0c8fc-118">New-CsRgsHolidaySet</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsRgsHolidaySet)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

