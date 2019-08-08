---
title: ) 비즈니스용 Skype에서 응답 그룹의 공휴일 집합 정의
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 56c37b3b-6517-49b9-86b7-ae48cc349119
description: 비즈니스용 Skype Server Enterprise Voice에서 응답 그룹 휴일 집합을 만들거나 수정 합니다.
ms.openlocfilehash: 617966828e39aae1ffbbfe10a7452d9d40117a84
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36240413"
---
# <a name="optional-define-response-group-holiday-sets-in-skype-for-business"></a>) 비즈니스용 Skype에서 응답 그룹의 공휴일 집합 정의
 
비즈니스용 Skype Server Enterprise Voice에서 응답 그룹 휴일 집합을 만들거나 수정 합니다.
  
공휴일 설정은 비즈니스에 대해 응답 그룹을 닫은 날을 정의 하 고 해당 날짜에 수행할 작업을 지정 합니다. 휴일 집합은 응답 그룹에 적용 되는 휴일 모음입니다.
  
> [!NOTE]
> 워크플로가 관리 워크플로로 정의 된 경우 모든 사용자에 게 할당 되는 경우 CsResponseGroupManager 역할은 자신이 관리 하는 워크플로에 대 한 휴일을 설정 하 고 수정할 수 있습니다. 
  
### <a name="to-create-a-holiday-set"></a>휴일 집합을 만들려면

1. RTCUniversalServerAdmins 그룹의 구성원 또는 응답 그룹을 지 원하는 미리 정의 된 관리 역할 중 하나의 구성원으로 로그온 합니다.
    
2. 비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **비즈니스용 skype 2015**을 차례로 클릭 한 다음 비즈니스용 **skype Server management Shell**을 클릭 합니다.
    
3. 정의 하려는 각 휴일에 대해 다음을 실행 합니다.
    
   ```
   $x = New-CsRgsHoliday [-Name <holiday name>] -StartDate <starting date of holiday> -EndDate <ending date of holiday>
   ```

    정의한 공휴일이 포함 된 휴일 집합을 만들려면 다음을 실행 합니다.
    
   ```
   New-CsRgsHolidaySet -Parent <service where the workflow is hosted> -Name <unique name for holiday set> -HolidayList <one or more holidays to be included in the holiday set>
   ```

    다음 예제에서는 두 개의 공휴일을 포함 하는 휴일 집합을 보여 줍니다.
    
   ```
   $a = New-CsRgsHoliday -Name "New Year's Day" -StartDate "1/1/2018 12:00 AM" -EndDate "1/2/2018 12:00 AM" 
   $b = New-CsRgsHoliday -Name "Independence Day" -StartDate "7/4/2018 12:00 AM" -EndDate "7/5/2018 12:00 AM" 
   New-CsRgsHolidaySet -Parent "ApplicationServer:Redmond.contoso.com" -Name "2018 Holidays" -HolidayList ($a, $b)
   ```

## <a name="see-also"></a>참고 항목

[비즈니스용 Skype에서 응답 그룹 워크플로 디자인 및 만들기](designing-and-creating-response-group-workflows.md)

[새로운 CsRgsHoliday](https://docs.microsoft.com/powershell/module/skype/new-csrgsholiday?view=skype-ps)

[New-CsRgsHolidaySet](https://docs.microsoft.com/powershell/module/skype/new-csrgsholidayset?view=skype-ps)
