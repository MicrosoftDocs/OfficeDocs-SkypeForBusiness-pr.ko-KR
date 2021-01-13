---
title: (선택 사항) 비즈니스용 Skype에서 응답 그룹 휴일 집합 정의
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
ms.assetid: 56c37b3b-6517-49b9-86b7-ae48cc349119
description: 비즈니스용 Skype 서버 2016에서 응답 그룹 휴일 집합을 만들거나 Enterprise Voice.
ms.openlocfilehash: dd3144c687329f82542d5b658c47212dd390c9fb
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830988"
---
# <a name="optional-define-response-group-holiday-sets-in-skype-for-business"></a>(선택 사항) 비즈니스용 Skype에서 응답 그룹 휴일 집합 정의
 
비즈니스용 Skype 서버 2016에서 응답 그룹 휴일 집합을 만들거나 Enterprise Voice.
  
휴일 설정에서는 응답 그룹이 근무하지 않는 요일을 정의하고 해당 요일에 수행할 작업을 지정합니다. 휴일 집합은 응답 그룹에 적용되는 휴일의 컬렉션입니다.
  
> [!NOTE]
> 워크플로가 관리 워크플로로 정의되었고 모든 사용자가 여기에 지정된 경우, CsResponseGroupManager 역할이 자신이 관리하는 워크플로에 대한 휴일을 설정하고 수정할 수 있습니다. 
  
### <a name="to-create-a-holiday-set"></a>휴일 집합을 만들려면

1. RTCUniversalServerAdmins 그룹의 구성원으로 로그온하거나 응답 그룹을 지원하는 미리 정의한 관리 역할 중 하나의 구성원으로 로그온합니다.
    
2. 비즈니스용 Skype 서버 관리 셸 시작: **시작,** 모든 **프로그램,** 비즈니스용 **Skype 2015,** 비즈니스용 Skype 서버 관리 셸을 **클릭합니다.**
    
3. 정의할 각 휴일에 대해 다음을 실행합니다.
    
   ```powershell
   $x = New-CsRgsHoliday [-Name <holiday name>] -StartDate <starting date of holiday> -EndDate <ending date of holiday>
   ```

    정의한 휴일이 포함된 휴일 집합을 만들려면 다음을 실행합니다.
    
   ```powershell
   New-CsRgsHolidaySet -Parent <service where the workflow is hosted> -Name <unique name for holiday set> -HolidayList <one or more holidays to be included in the holiday set>
   ```

    다음 예에서는 두 개의 휴일이 포함된 휴일 집합을 보여 줍니다.
    
   ```powershell
   $a = New-CsRgsHoliday -Name "New Year's Day" -StartDate "1/1/2018 12:00 AM" -EndDate "1/2/2018 12:00 AM" 
   $b = New-CsRgsHoliday -Name "Independence Day" -StartDate "7/4/2018 12:00 AM" -EndDate "7/5/2018 12:00 AM" 
   New-CsRgsHolidaySet -Parent "ApplicationServer:Redmond.contoso.com" -Name "2018 Holidays" -HolidayList ($a, $b)
   ```

## <a name="see-also"></a>참고 항목

[비즈니스용 Skype에서 응답 그룹 워크플로 디자인 및 만들기](designing-and-creating-response-group-workflows.md)

[New-CsRgsHoliday](https://docs.microsoft.com/powershell/module/skype/new-csrgsholiday?view=skype-ps)

[New-CsRgsHolidaySet](https://docs.microsoft.com/powershell/module/skype/new-csrgsholidayset?view=skype-ps)
