---
title: ) 비즈니스용 Skype에서 응답 그룹 업무 시간 정의
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d62551b2-1847-4e1b-abe8-683b72aa94d5
description: 비즈니스용 Skype Server Enterprise Voice에서 응답 그룹 업무 시간을 만들거나 수정 합니다.
ms.openlocfilehash: 602494d014c1a3c7874c91462f88b4bcd84f0abb
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003108"
---
# <a name="optional-define-response-group-business-hours-in-skype-for-business"></a>) 비즈니스용 Skype에서 응답 그룹 업무 시간 정의 
 
비즈니스용 Skype Server Enterprise Voice에서 응답 그룹 업무 시간을 만들거나 수정 합니다.
  
## <a name="defining-business-hours"></a>업무 시간 정의

비즈니스 시간 설정 워크플로를 전화를 받을 수 있는 시간을 정의 하 고 업무 시간 외의 통화에 대해 수행할 작업을 지정 합니다. 응답 그룹 관리자는 **새 CsRgsHoursOfBusiness** cmdlet을 사용 하 여 여러 응답 그룹에 사용할 수 있는 미리 정의 된 일정을 만들 수 있습니다.
  
> [!TIP]
> 워크플로를 만들거나 수정할 때 해당 워크플로에만 적용 되는 사용자 지정 일정을 지정할 수 있습니다. 자세한 내용은 비즈니스용 [Skype에서 응답 그룹 워크플로 디자인 및 만들기](designing-and-creating-response-group-workflows.md)를 참조 하세요. 
  
> [!NOTE]
> 워크플로가 관리 워크플로로 정의 된 경우 CsResponseGroupManager 역할에 할당 된 모든 사용자가 자신이 관리 하는 워크플로에 대 한 사용자 지정 업무 시간을 설정 하 고 수정할 수 있습니다. 
  
> [!IMPORTANT]
> 다음 cmdlet의 매개 변수에 24 시간 표시법을 사용 합니다 (예: 20:00 = 8:00 P.M.). 
  
### <a name="to-create-a-predefined-business-hours-collection"></a>미리 정의 된 업무 시간 모음을 만들려면

1. RTCUniversalServerAdmins 그룹의 구성원 또는 응답 그룹을 지 원하는 미리 정의 된 관리 역할 중 하나의 구성원으로 로그온 합니다.
    
2. 비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **비즈니스용 skype 2015**을 차례로 클릭 한 다음 비즈니스용 **skype Server management Shell**을 클릭 합니다.
    
3. 정의 하려는 각 시간 범위에 대해 다음을 실행 합니다.
    
   ```powershell
   $x = New-CsRgsTimeRange [-Name <name of time range>] -OpenTime <time when business hours begin> -CloseTime <time when business hours end>
   ```

    정의한 범위를 사용 하는 업무 시간 컬렉션을 만들려면 다음을 실행 합니다.
    
   ```powershell
   New-CsRgsHoursOfBusiness -Parent <service where the workflow is hosted> -Name <unique name for collection> [-MondayHours1 <first set of opening and closing times for Monday>] [-MondayHours2 <second set of opening and closing times for Monday>] [-TuesdayHours1 <first set of opening and closing times for Tuesday>] [-TuesdayHours2 <second set of opening and closing times for Tuesday>] [-WednesdayHours1 <first set of opening and closing times for Wednesday>] [-WednesdayHours2 <second set of opening and closing times for Wednesday>] [-ThursdayHours1 <first set of opening and closing times for Thursday>] [-ThursdayHours2 <second set of opening and closing times for Thursday>] [-FridayHours1 <first set of opening and closing times for Friday>] [-FridayHours2 <second set of opening and closing times for Friday>] [-SaturdayHours1 <first set of opening and closing times for Saturday>] [-SaturdayHours2 <second set of opening and closing times for Saturday>] [-SundayHours1 <first set of opening and closing times for Sunday>] [-SundayHours2 <second set of opening and closing times for Sunday>]
   ```

    다음 예에서는 근무 시간 오전 9:00를 지정 합니다. 5:00 P.M. 평일, 오전 8:00 오전 10:00 2:00 P.M.부터 다시 시작 합니다. 6:00 P.M. 토요일과 일요일에 대 한 업무 시간 없음:
    
   ```powershell
   $a = New-CSRgsTimeRange -Name "Weekday Hours" -OpenTime "9:00" -CloseTime "17:00"
   $b = New-CSRgsTimeRange -Name "Saturday Morning Hours" -OpenTime "8:00" -CloseTime "10:00" 
   $c = New-CSRgsTimeRange -Name "Saturday Afternoon Hours" -OpenTime "14:00" -CloseTime "18:00" 
   New-CsRgsHoursOfBusiness -Parent "ApplicationServer:Redmond.contoso.com" -Name "Help Desk Business Hours" -MondayHours1 $a -TuesdayHours1 $a -WednesdayHours1 $a -ThursdayHours1 $a -FridayHours1 $a -SaturdayHours1 $b -SaturdayHours2 $c
   ```

## <a name="see-also"></a>참고 항목

[새로운 CsRgsTimeRange](https://docs.microsoft.com/powershell/module/skype/new-csrgstimerange?view=skype-ps)
  
[새로운 CsRgsHoursOfBusiness](https://docs.microsoft.com/powershell/module/skype/new-csrgshoursofbusiness?view=skype-ps)
