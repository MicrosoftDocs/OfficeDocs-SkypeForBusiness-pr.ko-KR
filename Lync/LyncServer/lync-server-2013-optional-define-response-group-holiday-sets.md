---
title: 'Lync Server 2013: (선택 사항) 응답 그룹 공휴일 집합 정의'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: (Optional) Define Response Group holiday sets
ms:assetid: 56c37b3b-6517-49b9-86b7-ae48cc349119
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688063(v=OCS.15)
ms:contentKeyID: 49733657
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2ca58b3e2c17ea70e9af7a9eba48df8582b1485c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984509"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="optional-define-response-group-holiday-sets-in-lync-server-2013"></a><span data-ttu-id="f401d-102">) Lync Server 2013에서 응답 그룹의 휴일 집합 정의</span><span class="sxs-lookup"><span data-stu-id="f401d-102">(Optional) Define Response Group holiday sets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f401d-103">_**마지막으로 수정한 주제:** 2014-02-07_</span><span class="sxs-lookup"><span data-stu-id="f401d-103">_**Topic Last Modified:** 2014-02-07_</span></span>

<span data-ttu-id="f401d-104">공휴일 설정은 비즈니스에 대해 응답 그룹을 닫은 날을 정의 하 고 해당 날짜에 수행할 작업을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f401d-104">Holiday settings define the days that a response group is closed for business and specify the action to take on those days.</span></span> <span data-ttu-id="f401d-105">휴일 집합은 응답 그룹에 적용 되는 휴일 모음입니다.</span><span class="sxs-lookup"><span data-stu-id="f401d-105">A holiday set is the collection of holidays that apply to a response group.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f401d-106">워크플로가 관리 워크플로로 정의 된 경우 모든 사용자에 게 할당 되는 경우 CsResponseGroupManager 역할은 자신이 관리 하는 워크플로에 대 한 휴일을 설정 하 고 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f401d-106">If a workflow is defined as a Managed workflow, then any user is assigned the CsResponseGroupManager role can set and modify holidays for workflows that they manage.</span></span>



</div>

<div>

## <a name="to-create-a-holiday-set"></a><span data-ttu-id="f401d-107">휴일 집합을 만들려면</span><span class="sxs-lookup"><span data-stu-id="f401d-107">To create a holiday set</span></span>

1.  <span data-ttu-id="f401d-108">RTCUniversalServerAdmins 그룹의 구성원 또는 응답 그룹을 지 원하는 미리 정의 된 관리 역할 중 하나의 구성원으로 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="f401d-108">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="f401d-109">Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f401d-109">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="f401d-110">정의 하려는 각 휴일에 대해 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="f401d-110">For each holiday you want to define, run:</span></span>
    
        $x = New-CsRgsHoliday [-Name <holiday name>] -StartDate <starting date of holiday> -EndDate <ending date of holiday>
    
    <span data-ttu-id="f401d-111">정의한 공휴일이 포함 된 휴일 집합을 만들려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="f401d-111">To create the holiday set that contains the holidays you defined, run:</span></span>
    
        New-CsRgsHolidaySet -Parent <service where the workflow is hosted> -Name <unique name for holiday set> -HolidayList <one or more holidays to be included in the holiday set>
    
    <span data-ttu-id="f401d-112">다음 예제에서는 두 개의 공휴일을 포함 하는 휴일 집합을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f401d-112">The following example shows a holiday set that includes two holidays:</span></span>
    
        $a = New-CsRgsHoliday -Name "New Year's Day" -StartDate "1/1/2013 12:00 AM" -EndDate "1/1/2013 12:00 AM" 
        $b = New-CsRgsHoliday -Name "Independence Day" -StartDate "7/4/2013 12:00 AM" -EndDate "7/5/2013 12:00 AM" 
        New-CsRgsHolidaySet -Parent "ApplicationServer:Redmond.contoso.com -Name "2013 Holidays" -HolidayList ($a, $b)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f401d-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f401d-113">See Also</span></span>


[<span data-ttu-id="f401d-114">Lync Server 2013에서 헌트 그룹 워크플로 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="f401d-114">Create or modify a hunt group workflow in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-hunt-group-workflow.md)  
[<span data-ttu-id="f401d-115">Lync Server 2013에서 대화형 워크플로 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="f401d-115">Create or modify an interactive workflow in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-an-interactive-workflow.md)  


[<span data-ttu-id="f401d-116">새로운 CsRgsHoliday</span><span class="sxs-lookup"><span data-stu-id="f401d-116">New-CsRgsHoliday</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsRgsHoliday)  
[<span data-ttu-id="f401d-117">New-CsRgsHolidaySet</span><span class="sxs-lookup"><span data-stu-id="f401d-117">New-CsRgsHolidaySet</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsRgsHolidaySet)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

