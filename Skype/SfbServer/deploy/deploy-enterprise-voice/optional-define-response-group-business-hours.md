---
title: (선택 사항) 다음의 경우 응답 그룹 업무 시간을 비즈니스용 Skype
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: d62551b2-1847-4e1b-abe8-683b72aa94d5
description: 다음의 경우 응답 그룹 업무 시간을 만들거나 비즈니스용 Skype 서버 Enterprise Voice.
ms.openlocfilehash: 8cceee13e18e8b4a44ba1cffcca68be7c5fd3bf7
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58579982"
---
# <a name="optional-define-response-group-business-hours-in-skype-for-business"></a>(선택 사항) 다음의 경우 응답 그룹 업무 시간을 비즈니스용 Skype 
 
다음의 경우 응답 그룹 업무 시간을 만들거나 비즈니스용 Skype 서버 Enterprise Voice.
  
## <a name="defining-business-hours"></a>업무 시간 정의

업무 시간 설정에서는 워크플로를 사용하여 통화에 응답할 수 있는 시간을 정의하고 업무 시간 외에 통화에 대해 수행할 작업을 지정합니다. 응답 그룹 관리자는 **New-CsRgsHoursOfBusiness** cmdlet를 사용하여 임의의 응답 그룹에 사용할 수 있는 미리 정의된 일정을 만들 수 있습니다.
  
> [!TIP]
> 워크플로를 만들거나 수정할 때 해당 워크플로에만 적용되는 사용자 지정 일정을 설정할 수 있습니다. 자세한 내용은 에서 응답 그룹 워크플로 디자인 및 [만들기를 비즈니스용 Skype.](designing-and-creating-response-group-workflows.md) 
  
> [!NOTE]
> 워크플로가 관리 워크플로로 정의되는 경우 CsResponseGroupManager 역할에 할당된 사용자는 관리할 워크플로의 사용자 지정 업무 시간을 설정하고 수정할 수 있습니다. 
  
> [!IMPORTANT]
> 다음 cmdlet의 매개 변수에 24시간 표기법을 사용하십시오(예: 20:00=오후 8:00). 
  
### <a name="to-create-a-predefined-business-hours-collection"></a>미리 정의된 업무 시간 컬렉션을 만들려면

1. RTCUniversalServerAdmins 그룹의 구성원 또는 응답 그룹을 지원하는 미리 정의한 관리 역할 중 하나의 구성원으로 로그온합니다.
    
2. 비즈니스용 Skype 서버 시작: **시작,** 모든 프로그램, 비즈니스용 Skype **2015를** 클릭한 다음 관리 **비즈니스용 Skype 서버 를 클릭합니다.**
    
3. 정의할 각 고유 시간 범위에 대해 다음을 실행합니다.
    
   ```powershell
   $x = New-CsRgsTimeRange [-Name <name of time range>] -OpenTime <time when business hours begin> -CloseTime <time when business hours end>
   ```

    정의한 범위를 사용하는 업무 시간 컬렉션을 만들려면 다음을 실행합니다.
    
   ```powershell
   New-CsRgsHoursOfBusiness -Parent <service where the workflow is hosted> -Name <unique name for collection> [-MondayHours1 <first set of opening and closing times for Monday>] [-MondayHours2 <second set of opening and closing times for Monday>] [-TuesdayHours1 <first set of opening and closing times for Tuesday>] [-TuesdayHours2 <second set of opening and closing times for Tuesday>] [-WednesdayHours1 <first set of opening and closing times for Wednesday>] [-WednesdayHours2 <second set of opening and closing times for Wednesday>] [-ThursdayHours1 <first set of opening and closing times for Thursday>] [-ThursdayHours2 <second set of opening and closing times for Thursday>] [-FridayHours1 <first set of opening and closing times for Friday>] [-FridayHours2 <second set of opening and closing times for Friday>] [-SaturdayHours1 <first set of opening and closing times for Saturday>] [-SaturdayHours2 <second set of opening and closing times for Saturday>] [-SundayHours1 <first set of opening and closing times for Sunday>] [-SundayHours2 <second set of opening and closing times for Sunday>]
   ```

    다음 예에서는 평일 오전 9시~오후 5시, 토요일 오전 8시~오전 10시와 오후 2시~오후 6시를 업무 시간으로 지정하고 일요일은 휴무로 지정합니다.
    
   ```powershell
   $a = New-CSRgsTimeRange -Name "Weekday Hours" -OpenTime "9:00" -CloseTime "17:00"
   $b = New-CSRgsTimeRange -Name "Saturday Morning Hours" -OpenTime "8:00" -CloseTime "10:00" 
   $c = New-CSRgsTimeRange -Name "Saturday Afternoon Hours" -OpenTime "14:00" -CloseTime "18:00" 
   New-CsRgsHoursOfBusiness -Parent "ApplicationServer:Redmond.contoso.com" -Name "Help Desk Business Hours" -MondayHours1 $a -TuesdayHours1 $a -WednesdayHours1 $a -ThursdayHours1 $a -FridayHours1 $a -SaturdayHours1 $b -SaturdayHours2 $c
   ```

## <a name="see-also"></a>참고 항목

[New-CsRgsTimeRange](/powershell/module/skype/new-csrgstimerange?view=skype-ps)
  
[New-CsRgsHoursOfBusiness](/powershell/module/skype/new-csrgshoursofbusiness?view=skype-ps)