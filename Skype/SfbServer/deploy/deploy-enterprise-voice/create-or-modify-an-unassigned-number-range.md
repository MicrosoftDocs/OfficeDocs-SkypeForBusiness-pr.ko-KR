---
title: 비즈니스용 Skype 서버에서 할당 되지 않은 번호 범위 만들기 또는 수정
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a102b226-0460-4d5c-82f9-79b8444fa958
description: 비즈니스용 Skype Server Enterprise Voice에서 알림 신청에 대해 할당 되지 않은 번호 범위를 만들거나 수정 하거나 삭제 합니다. 이는 할당 되지 않은 번호로의 호출이 처리 되는 방식에 영향을 줍니다.
ms.openlocfilehash: 5b9afa463d6eaff2f6ba3ed283d11556bd95bc03
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190413"
---
# <a name="create-or-modify-an-unassigned-number-range-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 할당 되지 않은 번호 범위 만들기 또는 수정
 
비즈니스용 Skype Server Enterprise Voice에서 알림 신청에 대해 할당 되지 않은 번호 범위를 만들거나 수정 하거나 삭제 합니다. 이는 할당 되지 않은 번호로의 호출이 처리 되는 방식에 영향을 줍니다.
  
비즈니스용 Skype Server를 사용 하면 조직에 유효 하지만 사용자 또는 휴대폰에 할당 되지 않은 전화 번호로 들어오는 호출에 대해 말할 수 있습니다. 이러한 호출을 처리 하려면 지정 하지 않은 번호 표를 설정 합니다. 표를 사용 하 여 알림 응용 프로그램이 나 Exchange UM 서버로 전화를 라우팅할 수 있습니다.
  
할당되지 않은 번호 테이블을 구성하는 방법은 테이블 사용 방법에 따라 다릅니다. 조직에 대해 유효한 모든 내선 번호로 또는 할당되지 않은 내선 번호만으로 또는 두 번호 유형의 결합으로 테이블을 구성할 수 있습니다. 할당되지 않은 번호 테이블은 할당된 번호와 할당되지 않은 번호를 모두 포함할 수 있지만 발신자가 현재 할당되지 않은 번호로 전화를 걸 때만 호출됩니다. 할당되지 않은 번호 테이블에 유효한 내선 번호를 모두 포함하면 테이블을 재구성하지 않고도 다른 사용자가 조직을 떠날 때마다 발생하는 동작을 지정할 수 있습니다. 표에 할당 되지 않은 확장명을 포함 하는 경우 특정 숫자에 대해 발생 하는 동작을 수정할 수 있습니다. 예를 들어 고객 서비스 데스크에 대 한 내선 번호를 변경 하는 경우에는 테이블에 이전의 고객 서비스 번호가 포함 된 다음 새 번호를 제공 하는 공지 사항에 할당할 수 있습니다.
  
## <a name="configure-unassigned-phone-numbers"></a>지정 하지 않은 전화 번호 구성

다음 절차 중 하나를 사용 하 여 알림 신청에 대해 할당 되지 않은 번호 범위를 구성 합니다.
  
> [!IMPORTANT]
> 할당 되지 않은 번호 테이블을 구성 하기 전에 시스템에 이미 공지가 정의 되어 있거나 UM (Exchange 통합 메시징) 자동 전화 교환이 설정 되어 있어야 합니다. 
  
> [!TIP]
> 다른 사용자가 지정 되지 않은 번호를 호출 하는 경우 비즈니스용 Skype 서버는 지정 되지 않은 번호 표를 위에서 아래로 검색 하 고 첫 번째 일치 범위를 사용 합니다. 따라서 표의 마지막 범위에 대해 마지막 수단으로 수행 하려는 작업을 지정 해야 합니다. 
  
### <a name="to-use-skype-for-business-server-control-panel-to-configure-unassigned-phone-numbers"></a>비즈니스용 Skype 서버 제어판을 사용 하 여 할당 되지 않은 전화 번호를 구성 하려면

1. RTCUniversalServerAdmins 그룹의 구성원 또는 CsVoiceAdministrator, CsServerAdministrator 또는 CsAdministrator 역할의 구성원으로 컴퓨터에 로그온 합니다. 자세한 내용은 **대리인 설정 사용**을 참조 하세요.
    
2. 브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다.  
    
3. 왼쪽 탐색 모음에서 **음성 기능**을 클릭 한 다음 지정 하지 **않은 번호**를 클릭 합니다.
    
4. 지정 하지 **않은 번호** 페이지에서 다음 중 하나를 수행 합니다.
    
   - 새 번호 범위를 만들려면 **새로**만들기를 클릭 합니다. **이름**에이 숫자 범위에 대 한 식별 이름을 입력 합니다.
    
     > [!NOTE]
     > 데이터베이스에 새 할당 되지 않은 번호 범위를 커밋한 후에는이 이름을 변경할 수 없습니다. 
  
   - 기존 번호 범위를 수정 하려면 검색 필드에 숫자 범위 이름 전체 또는 일부를 입력 합니다. 결과 번호 범위 목록에서 원하는 이름을 클릭 하 고 **편집**을 클릭 한 다음 **세부 정보 표시**를 클릭 합니다.
    
5. 첫 번째 **숫자 범위** 필드에 범위의 시작 번호를 입력 하 고 두 번째 **숫자 범위** 필드에 범위의 끝 번호를 입력 합니다.
    
   - 범위의 시작 번호는 범위의 마지막 번호보다 작거나 같아야 합니다.
    
   - 범위의 시작 번호 또는 범위의 끝 번호에 내선 번호가 포함 된 경우, 시작 번호와 범위의 끝 번호에는 확장명이 포함 되어야 하 고, 내선 번호는 시작 번호와이 둘 다에 대해 동일 해야 합니다. 끝 번호입니다.
    
   - 번호는 정규식 (tel:)과 일치 해야 합니다 ( \+)? [1-9] \d{0,17}(; ext = [1-9] \d{0,9})?. 즉,이 숫자는 문자열 tel로 시작 될 수 있습니다 (해당 문자열을 지정 하지 않으면 자동으로 추가 됩니다), 더하기 기호 (+), 숫자 1 ~ 9 전화 번호는 최대 17자리이며 ;ext= 뒤에 내선 번호가 오는 형식으로 내선 번호를 추가할 수 있습니다.
    
6. **알림 서비스**에서 다음 중 하나를 수행 합니다. 
    
   - **공지 사항을**클릭 합니다.
    
   - **EXCHANGE UM**을 클릭 합니다.
    
7. 이전 단계에서 **공지 사항을**클릭 한 경우 다음을 수행 합니다.
    
    에서. **대상 서버의 FQDN**아래에서 **선택을**클릭 하 고 알림 응용 프로그램을 실행 하는 응용 프로그램 서비스의 서비스 ID를 클릭 하 여이 범위의 지정 되지 않은 번호로 걸려오는 통화를 처리 하 고 **확인**을 클릭 합니다.
    
    b. **알림에서**이 지정 되지 않은 숫자 범위에 대해 재생할 공지 사항을 클릭 합니다.
    
8. 이전 단계에서 **EXCHANGE UM**을 클릭 한 후 **자동 전화 교환 전화 번호**아래에서 **선택을**클릭 하 고 지정 하지 않은이 범위의 번호에 사용할 전화 번호를 클릭 한 다음 **확인**을 클릭 합니다.
    
9. **확인**을 클릭합니다.
    
10. 지정 하지 않은 **번호** 페이지에서 지정 하지 않은 번호 범위가 원하는 순서 대로 정렬 되어 있는지 확인 합니다. 표에서 범위의 위치를 변경 하려면 범위 목록에서 하나 이상의 연속 된 이름을 클릭 한 다음 위쪽 화살표 또는 아래쪽 화살표를 클릭 합니다.
    
    > [!TIP]
    > 비즈니스용 Skype Server는 할당 되지 않은 번호 테이블을 위에서 아래로 검색 하 고 지정 된 번호와 일치 하는 첫 번째 범위를 사용 합니다. 겹치는 범위와 한 범위에서 마지막 리조트 작업을 지정 하는 경우 해당 범위가 목록의 맨 아래에 있는지 확인 합니다. 
  
11. 지정 하지 않은 번호 범위가 원하는 순서 대로 되어 있으면 **모두 커밋을**클릭 합니다.
    
### <a name="to-use-skype-for-business-server-management-shell-to-configure-unassigned-phone-numbers"></a>비즈니스용 Skype Server Management Shell을 사용 하 여 할당 되지 않은 전화 번호를 구성 하려면

1. 비즈니스용 Skype 서버 관리 셸이 설치 되어 있는 컴퓨터에 RTCUniversalServerAdmins 그룹의 구성원 또는 **대리인 설정 권한에**설명 된 대로 필요한 사용자 권한으로 로그온 합니다.
    
2. 비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **비즈니스용 skype 2015**을 차례로 클릭 한 다음 비즈니스용 **skype Server management Shell**을 클릭 합니다.
    
3. **New-CsUnassignedNumber** 를 사용 하 여 할당 되지 않은 새 번호 범위를 만듭니다. **Set-CsUnassignedNumber** 를 사용 하 여 지정 되지 않은 기존 번호 범위를 수정 합니다.
    
    > [!TIP]
    > 범위가 겹쳐져 특정 순서로 범위를 적용 하려면 Priority 매개 변수를 포함 합니다. 우선 순위가 가장 높은 범위가 통화에 적용 됩니다. 값 0은 가장 높은 우선 순위를 나타냅니다.
  
    명령줄에서 다음 중 하나를 수행 합니다.
    
   - 알림 서비스에 대 한 번호 범위를 만들려면 다음을 실행 합니다.
    
     ```
     New-CsUnassignedNumber -Identity <unique identifier for unassigned number range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range> -AnnouncementName <announcement name> -AnnouncementService <FQDN or service ID of the Announcement service>
     ```

   - 또는 Exchange UM 자동 전화 교환에 대 한 숫자 범위를 만들려면 다음을 실행 합니다.
    
     ```
     New-CsUnassignedNumber -ExUmAutoAttendantPhoneNumber <phone number> -Identity <unique identifier for unassigned number range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range>
     ```

     예를 들면 다음과 같습니다.
    
     ```
     New-CsUnassignedNumber -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551100" -AnnouncementName "Welcome Announcement" -AnnouncementService ApplicationServer:Redmond.contoso.com
     ```

     또는
    
     ```
     New-CsUnassignedNumber -ExUmAutoAttendantPhoneNumber "+12065551234" -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551100"
     ```

     다음 예제에서는 기존에 할당 되지 않은 숫자 범위에서 숫자를 수정 하는 방법을 보여 줍니다.
    
     ```
     Set-CsUnassignedNumber -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551900"
     ```

## <a name="delete-an-unnasigned-number-range"></a>Unnasigned 번호 범위 삭제

### <a name="to-use-skype-for-business-server-control-panel-to-delete-an-unassigned-number-range"></a>비즈니스용 Skype Server 제어판을 사용 하 여 지정 되지 않은 번호 범위를 삭제 하려면

1.  RTCUniversalServerAdmins 그룹의 구성원 또는 CsVoiceAdministrator, CsServerAdministrator 또는 CsAdministrator 역할의 구성원으로 컴퓨터에 로그온 합니다. 자세한 내용은 **대리인 설정 사용**을 참조 하세요.
    
2. 브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다.  
    
3. 왼쪽 탐색 모음에서 **음성 기능** 을 클릭 한 다음 지정 하지 **않은 번호**를 클릭 합니다.
    
4. 지정 하지 **않은 번호** 페이지의 검색 필드에 삭제 하려는 배정 되지 않은 번호 범위 이름의 전부 또는 일부를 입력 합니다.
    
5. 결과 번호 범위 목록에서 이름을 클릭 하 고 **편집**을 클릭 한 다음 **삭제**를 클릭 합니다.
    
6. **모두 커밋을**클릭 합니다.
    
### <a name="to-use-skype-for-business-server-management-shell-to-delete-an-unassigned-number-range"></a>비즈니스용 Skype Server Management Shell을 사용 하 여 지정 되지 않은 번호 범위를 삭제 하려면

1. 비즈니스용 Skype 서버 관리 셸이 설치 되어 있는 컴퓨터에 RTCUniversalServerAdmins 그룹의 구성원 또는 **대리인 설정 권한에**설명 된 대로 필요한 사용자 권한으로 로그온 합니다.
    
2. 비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **비즈니스용 skype 2015**을 차례로 클릭 한 다음 비즈니스용 **skype Server management Shell**을 클릭 합니다.
    
3. 명령줄에 다음을 입력 합니다.
    
   ```
   Remove-CsUnassignedNumber -Identity "<name of unassigned number range>" 
   ```

    예를 들면 다음과 같습니다.
    
   ```
   Remove-CsUnassignedNumber -Identity "Unassigned range 1"
   ```

    > [!NOTE]
    > 추가 옵션에 대 한 자세한 내용은 [제거-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/remove-cscallparkorbit?view=skype-ps)를 참조 하세요. 
  
## <a name="see-also"></a>참고 항목

[New-CsUnassignedNumber](https://docs.microsoft.com/powershell/module/skype/new-csunassignednumber?view=skype-ps)
  
[Set-CsUnassignedNumber](https://docs.microsoft.com/powershell/module/skype/set-csunassignednumber?view=skype-ps)
  
[Get-CsUnassignedNumber](https://docs.microsoft.com/powershell/module/skype/get-csunassignednumber?view=skype-ps)
