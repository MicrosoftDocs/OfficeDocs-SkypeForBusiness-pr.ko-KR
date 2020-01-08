---
title: 'Lync Server 2013: (선택 사항) 응답 그룹 비즈니스 시간 정의'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: (Optional) Define Response Group business hours
ms:assetid: d62551b2-1847-4e1b-abe8-683b72aa94d5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205291(v=OCS.15)
ms:contentKeyID: 48185504
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e8ddd2bde582c66cf337deb9aa78178d3e22d1b0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985166"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="optional-define-response-group-business-hours-in-lync-server-2013"></a>) Lync Server 2013에서 응답 그룹 비즈니스 시간 정의

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-11-01_

<div>

## <a name="defining-business-hours"></a>업무 시간 정의

비즈니스 시간 설정 워크플로를 전화를 받을 수 있는 시간을 정의 하 고 업무 시간 외의 통화에 대해 수행할 작업을 지정 합니다. 응답 그룹 관리자는 **새 CsRgsHoursOfBusiness** cmdlet을 사용 하 여 여러 응답 그룹에 사용할 수 있는 미리 정의 된 일정을 만들 수 있습니다.

<div>


> [!TIP]  
> 워크플로를 만들거나 수정할 때 해당 워크플로에만 적용 되는 사용자 지정 일정을 지정할 수 있습니다. 자세한 내용은 <A href="lync-server-2013-create-or-modify-a-hunt-group-workflow.md">Lync server 2013에서 헌트 그룹 워크플로 만들기 또는 수정을</A> 참조 하거나 <A href="lync-server-2013-create-or-modify-an-interactive-workflow.md">lync server 2013에서 대화형 워크플로를 만들거나 수정</A>합니다.



</div>

<div>


> [!NOTE]  
> 워크플로가 관리 워크플로로 정의 된 경우 CsResponseGroupManager 역할에 할당 된 모든 사용자가 자신이 관리 하는 워크플로에 대 한 사용자 지정 업무 시간을 설정 하 고 수정할 수 있습니다.



</div>

<div>


> [!IMPORTANT]  
> 다음 cmdlet의 매개 변수에 24 시간 표시법을 사용 합니다 (예: 20:00 = 8:00 P.M.).



</div>

<div>

## <a name="to-create-a-predefined-business-hours-collection"></a>미리 정의 된 업무 시간 모음을 만들려면

1.  RTCUniversalServerAdmins 그룹의 구성원 또는 응답 그룹을 지 원하는 미리 정의 된 관리 역할 중 하나의 구성원으로 로그온 합니다.

2.  Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.

3.  정의 하려는 각 시간 범위에 대해 다음을 실행 합니다.
    
        $x = New-CsRgsTimeRange [-Name <name of time range>] -OpenTime <time when business hours begin> -CloseTime <time when business hours end>
    
    정의한 범위를 사용 하는 업무 시간 컬렉션을 만들려면 다음을 실행 합니다.
    
        New-CsRgsHoursOfBusiness -Parent <service where the workflow is hosted> -Name <unique name for collection> [-MondayHours1 <first set of opening and closing times for Monday>] [-MondayHours2 <second set of opening and closing times for Monday>] [-TuesdayHours1 <first set of opening and closing times for Tuesday>] [-TuesdayHours2 <second set of opening and closing times for Tuesday>] [-WednesdayHours1 <first set of opening and closing times for Wednesday>] [-WednesdayHours2 <second set of opening and closing times for Wednesday>] [-ThursdayHours1 <first set of opening and closing times for Thursday>] [-ThursdayHours2 <second set of opening and closing times for Thursday>] [-FridayHours1 <first set of opening and closing times for Friday>] [-FridayHours2 <second set of opening and closing times for Friday>] [-SaturdayHours1 <first set of opening and closing times for Saturday>] [-SaturdayHours2 <second set of opening and closing times for Saturday>] [-SundayHours1 <first set of opening and closing times for Sunday>] [-SundayHours2 <second set of opening and closing times for Sunday>]
    
    다음 예에서는 근무 시간 오전 9:00를 지정 합니다. 5:00 P.M. 평일, 오전 8:00 오전 10:00 2:00 P.M.부터 다시 시작 합니다. 6:00 P.M. 토요일과 일요일에 대 한 업무 시간 없음:
    
        $a = NewRgsTimeRange -Name "Weekday Hours" -OpenTime "9:00" -CloseTime "17:00"
        $b = NewRgsTimeRange -Name "Saturday Morning Hours" -OpenTime "8:00" -CloseTime "10:00" 
        $c = NewRgsTimeRange -Name "Saturday Afternoon Hours" -OpenTime "14:00" -CloseTime "18:00" 
        New-CsRgsHoursOfBusiness -Parent "ApplicationServer:Redmond.contoso.com" -Name "Help Desk Business Hours" -MondayHours1 $a -TuesdayHours1 $a -WednesdayHours1 $a -ThursdayHours1 $a -FridayHours1 $a -SaturdayHours1 $b -SaturdayHours2 $c

</div>

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에서 헌트 그룹 워크플로 만들기 또는 수정](lync-server-2013-create-or-modify-a-hunt-group-workflow.md)  
[Lync Server 2013에서 대화형 워크플로 만들기 또는 수정](lync-server-2013-create-or-modify-an-interactive-workflow.md)  


[새로운 CsRgsTimeRange](https://docs.microsoft.com/powershell/module/skype/New-CsRgsTimeRange)  
[새로운 CsRgsHoursOfBusiness](https://docs.microsoft.com/powershell/module/skype/New-CsRgsHoursOfBusiness)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

