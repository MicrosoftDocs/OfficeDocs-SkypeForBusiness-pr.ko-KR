---
title: 'Lync Server 2013: (선택 사항) 응답 그룹 공휴일 집합 정의'
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
ms.openlocfilehash: 7e6751a5f5915e73d181efba40976640c65e0909
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755762"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="optional-define-response-group-holiday-sets-in-lync-server-2013"></a>) Lync Server 2013에서 응답 그룹의 휴일 집합 정의

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2014-02-07_

공휴일 설정은 비즈니스에 대해 응답 그룹을 닫은 날을 정의 하 고 해당 날짜에 수행할 작업을 지정 합니다. 휴일 집합은 응답 그룹에 적용 되는 휴일 모음입니다.

<div>


> [!NOTE]  
> 워크플로가 관리 워크플로로 정의 된 경우 모든 사용자에 게 할당 되는 경우 CsResponseGroupManager 역할은 자신이 관리 하는 워크플로에 대 한 휴일을 설정 하 고 수정할 수 있습니다.



</div>

<div>

## <a name="to-create-a-holiday-set"></a>휴일 집합을 만들려면

1.  RTCUniversalServerAdmins 그룹의 구성원 또는 응답 그룹을 지 원하는 미리 정의 된 관리 역할 중 하나의 구성원으로 로그온 합니다.

2.  Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.

3.  정의 하려는 각 휴일에 대해 다음을 실행 합니다.
    
        $x = New-CsRgsHoliday [-Name <holiday name>] -StartDate <starting date of holiday> -EndDate <ending date of holiday>
    
    정의한 공휴일이 포함 된 휴일 집합을 만들려면 다음을 실행 합니다.
    
        New-CsRgsHolidaySet -Parent <service where the workflow is hosted> -Name <unique name for holiday set> -HolidayList <one or more holidays to be included in the holiday set>
    
    다음 예제에서는 두 개의 공휴일을 포함 하는 휴일 집합을 보여 줍니다.
    
        $a = New-CsRgsHoliday -Name "New Year's Day" -StartDate "1/1/2013 12:00 AM" -EndDate "1/1/2013 12:00 AM" 
        $b = New-CsRgsHoliday -Name "Independence Day" -StartDate "7/4/2013 12:00 AM" -EndDate "7/5/2013 12:00 AM" 
        New-CsRgsHolidaySet -Parent "ApplicationServer:Redmond.contoso.com -Name "2013 Holidays" -HolidayList ($a, $b)

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에서 헌트 그룹 워크플로 만들기 또는 수정](lync-server-2013-create-or-modify-a-hunt-group-workflow.md)  
[Lync Server 2013에서 대화형 워크플로 만들기 또는 수정](lync-server-2013-create-or-modify-an-interactive-workflow.md)  


[새로운 CsRgsHoliday](https://docs.microsoft.com/powershell/module/skype/New-CsRgsHoliday)  
[New-CsRgsHolidaySet](https://docs.microsoft.com/powershell/module/skype/New-CsRgsHolidaySet)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

