---
title: 'Lync Server 2013: (선택 사항) 응답 그룹 업무 시간 정의'
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
ms.openlocfilehash: 891dd05caf5e2ec3411da73c1151ae61c2d0630c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48524465"
---
# <a name="optional-define-response-group-business-hours-in-lync-server-2013"></a>반드시 Lync Server 2013에서 응답 그룹 업무 시간 정의

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-11-01_

<div>

## <a name="defining-business-hours"></a>업무 시간 정의

업무 시간 설정에서는 워크플로를 사용하여 통화에 응답할 수 있는 시간을 정의하고 업무 시간 외에 통화에 대해 수행할 작업을 지정합니다. 응답 그룹 관리자는 **New-CsRgsHoursOfBusiness** cmdlet를 사용하여 임의의 응답 그룹에 사용할 수 있는 미리 정의된 일정을 만들 수 있습니다.

<div>


> [!TIP]  
> 워크플로를 만들거나 수정할 때 해당 워크플로에만 적용되는 사용자 지정 일정을 설정할 수 있습니다. 자세한 내용은 Lync server <A href="lync-server-2013-create-or-modify-a-hunt-group-workflow.md">2013에서 헌트 그룹 워크플로 만들기 또는 수정</A> 또는 <A href="lync-server-2013-create-or-modify-an-interactive-workflow.md">lync server 2013에서 대화형 워크플로 만들기 또는 수정</A>를 참조 하세요.



</div>

<div>


> [!NOTE]  
> 워크플로가 관리 워크플로로 정의되는 경우 CsResponseGroupManager 역할에 할당된 사용자는 관리할 워크플로의 사용자 지정 업무 시간을 설정하고 수정할 수 있습니다.



</div>

<div>


> [!IMPORTANT]  
> 다음 cmdlet의 매개 변수에 24시간 표기법을 사용하십시오(예: 20:00=오후 8:00).



</div>

<div>

## <a name="to-create-a-predefined-business-hours-collection"></a>미리 정의된 업무 시간 컬렉션을 만들려면

1.  RTCUniversalServerAdmins 그룹의 구성원이 나 응답 그룹을 지 원하는 미리 정의 된 관리 역할 중 하나의 구성원으로 로그온 합니다.

2.  **시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.

3.  정의할 각 고유 시간 범위에 대해 다음을 실행합니다.
    
        $x = New-CsRgsTimeRange [-Name <name of time range>] -OpenTime <time when business hours begin> -CloseTime <time when business hours end>
    
    정의한 범위를 사용하는 업무 시간 컬렉션을 만들려면 다음을 실행합니다.
    
        New-CsRgsHoursOfBusiness -Parent <service where the workflow is hosted> -Name <unique name for collection> [-MondayHours1 <first set of opening and closing times for Monday>] [-MondayHours2 <second set of opening and closing times for Monday>] [-TuesdayHours1 <first set of opening and closing times for Tuesday>] [-TuesdayHours2 <second set of opening and closing times for Tuesday>] [-WednesdayHours1 <first set of opening and closing times for Wednesday>] [-WednesdayHours2 <second set of opening and closing times for Wednesday>] [-ThursdayHours1 <first set of opening and closing times for Thursday>] [-ThursdayHours2 <second set of opening and closing times for Thursday>] [-FridayHours1 <first set of opening and closing times for Friday>] [-FridayHours2 <second set of opening and closing times for Friday>] [-SaturdayHours1 <first set of opening and closing times for Saturday>] [-SaturdayHours2 <second set of opening and closing times for Saturday>] [-SundayHours1 <first set of opening and closing times for Sunday>] [-SundayHours2 <second set of opening and closing times for Sunday>]
    
    다음 예에서는 평일 오전 9시~오후 5시, 토요일 오전 8시~오전 10시와 오후 2시~오후 6시를 업무 시간으로 지정하고 일요일은 휴무로 지정합니다.
    
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


[New-csrgstimerange](https://docs.microsoft.com/powershell/module/skype/New-CsRgsTimeRange)  
[Get-csrgshoursofbusiness](https://docs.microsoft.com/powershell/module/skype/New-CsRgsHoursOfBusiness)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

