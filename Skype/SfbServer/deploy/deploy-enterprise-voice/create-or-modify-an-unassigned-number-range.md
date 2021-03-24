---
title: 비즈니스용 Skype 서버에서 미지정 번호 범위 만들기 또는 수정
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
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a102b226-0460-4d5c-82f9-79b8444fa958
description: 비즈니스용 Skype 서버 2013에서 공지사항 응용 프로그램에 대한 미지정 번호 범위를 만들거나 수정하거나 Enterprise Voice. 이는 미지정 번호에 대한 호출이 처리된 방식에 영향을 미치게 됩니다.
ms.openlocfilehash: 72c9ec5b6b1e3d4577507ede0a5ed61560928f03
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093056"
---
# <a name="create-or-modify-an-unassigned-number-range-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 미지정 번호 범위 만들기 또는 수정
 
비즈니스용 Skype 서버 2013에서 공지사항 응용 프로그램에 대한 미지정 번호 범위를 만들거나 수정하거나 Enterprise Voice. 이는 미지정 번호에 대한 호출이 처리된 방식에 영향을 미치게 됩니다.
  
비즈니스용 Skype 서버를 사용하면 조직에 유효하지만 사용자나 전화에 할당되지 않은 전화 번호로 걸치는 수신 전화에 대해 어떤 일이 발생하는지 말할 수 있습니다. 이러한 호출을 처리하기 위해 미지정 번호 테이블을 설정해야 합니다. 이 표를 사용하여 호출을 공지 응용 프로그램 또는 Exchange UM 서버로 라우팅할 수 있습니다.
  
할당되지 않은 번호 테이블을 구성하는 방법은 테이블 사용 방법에 따라 다릅니다. 조직에 대해 유효한 모든 내선 번호로 또는 할당되지 않은 내선 번호만으로 또는 두 번호 유형의 결합으로 테이블을 구성할 수 있습니다. 할당되지 않은 번호 테이블은 할당된 번호와 할당되지 않은 번호를 모두 포함할 수 있지만 발신자가 현재 할당되지 않은 번호로 전화를 걸 때만 호출됩니다. 할당되지 않은 번호 테이블에 유효한 내선 번호를 모두 포함하면 테이블을 재구성하지 않고도 다른 사용자가 조직을 떠날 때마다 발생하는 동작을 지정할 수 있습니다. 테이블에 지정되지 않은 내선 번호를 포함하면 특정 번호에 대해 발생하는 작업을 수정할 수 있습니다. 예를 들어 고객 서비스 센터의 내선 번호를 변경하는 경우 테이블에 이전 고객 서비스 번호를 포함한 다음 새 번호를 제공하는 공지에 할당할 수 있습니다.
  
## <a name="configure-unassigned-phone-numbers"></a>미지정 전화 번호 구성

다음 절차 중 하나를 사용하여 공지사항 응용 프로그램에 대한 미지정 번호 범위를 구성합니다.
  
> [!IMPORTANT]
> 배정되지 않은 번호 테이블을 구성하기 전에 시스템에 이미 알림을 정의하거나 UM(Exchange 통합 메시징)을 설정해야 자동 전화 교환 합니다. 
  
> [!TIP]
> 누군가가 미지정 번호로 전화를 걸면 비즈니스용 Skype 서버가 미지정 번호 테이블을 위쪽에서 아래쪽으로 검색하고 첫 번째 일치 범위를 사용하게 됩니다. 따라서 마지막 수단으로 수행하려는 작업은 표의 마지막 범위에 대해 지정해야 합니다. 
  
### <a name="to-use-skype-for-business-server-control-panel-to-configure-unassigned-phone-numbers"></a>비즈니스용 Skype 서버 제어판을 사용하여 미지정 전화 번호를 구성

1. RTCUniversalServerAdmins 그룹의 구성원이나 CsVoiceAdministrator, CsServerAdministrator 또는 CsAdministrator 역할의 구성원으로 컴퓨터에 로그온합니다. 자세한 내용은 **Delegate Setup Permissions** 을 참조하십시오.
    
2. 브라우저 창을 열고 관리 URL을 입력하여 비즈니스용 Skype 서버 제어판을 니다.  
    
3. 왼쪽 탐색 모음에서 **음성 기능** 을 클릭하고 **지정되지 않은 번호** 를 클릭합니다.
    
4. **지정되지 않은 번호** 페이지에서 다음 중 하나를 수행합니다.
    
   - 새 번호 범위를 만들려면 **새로 만들기** 를 클릭하고 **이름** 에 이 번호 범위에 대한 식별 이름을 입력합니다.
    
     > [!NOTE]
     > 할당되지 않은 새 번호 범위를 데이터베이스에 커밋하고 나면 이 이름은 변경할 수 없습니다. 
  
   - 기존 번호 범위를 수정하려면 검색 필드에 번호 범위의 이름을 모두 또는 일부분 입력합니다. 결과 번호 범위 목록에서 수정할 이름을 클릭하고 **편집** 을 클릭한 다음 **자세한 정보 표시** 를 클릭합니다.
    
5. 첫 번째 **번호 범위** 필드에는 범위의 시작 번호를 입력하고, 두 번째 **번호 범위** 필드에는 해당 범위의 끝 번호를 입력합니다.
    
   - 범위의 시작 번호는 범위의 마지막 번호보다 작거나 같아야 합니다.
    
   - 범위의 시작 번호나 끝 번호에 내선 번호가 포함된 경우에는 범위의 시작 번호와 끝 번호 둘 다에 내선 번호가 포함되어야 하며, 내선 번호는 시작 번호와 끝 번호에 대해 같아야 합니다.
    
   - 숫자는 정규식과 일치해야 `(tel:)?(\+)?[1-9]\d{0,17}(;ext=[1-9]\d{0,9})?` 합니다. 즉, 숫자가 문자열로 시작될 수 있습니다(해당 문자열을 지정하지 않으면 자동으로 추가됩니다), 더하기 `tel:` 기호(+) 및 숫자 1-9. 전화 번호는 최대 17자리이며 ;ext= 뒤에 내선 번호가 오는 형식으로 내선 번호를 추가할 수 있습니다.
    
6. **알림 서비스** 에서 다음 중 하나를 수행합니다. 
    
   - **알림** 을 클릭합니다.
    
   - **Exchange UM** 을 클릭합니다.
    
7. 이전 단계에서 **알림** 을 클릭한 경우 다음을 수행합니다.
    
    a. **대상 서버의 FQDN** 에서 **선택** 을 클릭하고, 이 지정되지 않은 번호 범위에 대한 수신 전화를 처리할 알림 응용 프로그램을 실행하는 응용 프로그램 서비스의 서비스 ID를 클릭한 후에 **확인** 을 클릭합니다.
    
    b. **알림** 에서 이 지정되지 않은 번호 범위에 대해 재생할 알림을 클릭합니다.
    
8. 이전 단계에서 **Exchange UM** 을 클릭한 경우에는 **자동 전화 교환 전화 번호** 에서 **선택** 을 클릭하고 이 지정되지 않은 번호 범위에 사용할 전화 번호를 클릭한 후에 **확인** 을 클릭합니다.
    
9. **확인** 을 클릭합니다.
    
10. **지정되지 않은 번호** 페이지에서 지정되지 않은 번호 범위가 원하는 순서로 정렬되어 있는지 확인합니다. 표에서 범위 위치를 변경하려면 범위 목록에서 연속하는 이름을 하나 이상 클릭하고 위쪽 또는 아래쪽 화살표를 클릭합니다.
    
    > [!TIP]
    > 비즈니스용 Skype 서버는 미지정 번호 테이블을 위쪽에서 아래쪽으로 검색하고, 미지정 번호와 일치하는 첫 번째 범위를 사용 합니다. 겹치는 범위와 최후의 수단으로 수행할 작업을 지정하는 범위가 있는 경우에는 해당 범위가 목록 맨 밑에 오도록 하십시오. 
  
11. 할당되지 않은 번호 범위를 원하는 순서대로 표시하려면 **모두 커밋** 을 클릭합니다.
    
### <a name="to-use-skype-for-business-server-management-shell-to-configure-unassigned-phone-numbers"></a>비즈니스용 Skype 서버 관리 셸을 사용하여 미지정 전화 번호를 구성

1. 비즈니스용 Skype 서버 관리 셸이 설치된 컴퓨터에 RTCUniversalServerAdmins 그룹의 구성원 또는 설치 권한 위임에 설명된 필요한 사용자 권한으로 **로그온합니다.**
    
2. 비즈니스용 Skype 서버 관리 셸 시작: **시작,** 모든 **프로그램,** 비즈니스용 **Skype 2015,** 비즈니스용 Skype 서버 관리 셸을 **클릭합니다.**
    
3. **New-CsUnassignedNumber를** 사용하여 새 미지정 번호 범위를 만들 수 있습니다. **Set-CsUnassignedNumber를** 사용하여 기존 미지정 번호 범위를 수정할 수 있습니다.
    
    > [!TIP]
    > 겹치는 범위가 있고 해당 범위가 특정 순서로 적용되게 하려는 경우에는 Priority 매개 변수를 포함합니다. 우선 순위가 가장 높은 범위가 통화 적용됩니다. 값 0은 가장 높은 우선 순위를 나타났습니다.
  
    명령줄에서 다음 중 하나를 수행합니다.
    
   - 알림 서비스에 대한 번호 범위를 만들려면 다음을 실행합니다.
    
     ```powershell
     New-CsUnassignedNumber -Identity <unique identifier for unassigned number range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range> -AnnouncementName <announcement name> -AnnouncementService <FQDN or service ID of the Announcement service>
     ```

   - 또는 Exchange UM 자동 전화 교환에 대한 번호 범위를 만들려면 다음을 실행합니다.
    
     ```powershell
     New-CsUnassignedNumber -ExUmAutoAttendantPhoneNumber <phone number> -Identity <unique identifier for unassigned number range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range>
     ```

     예:
    
     ```powershell
     New-CsUnassignedNumber -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551100" -AnnouncementName "Welcome Announcement" -AnnouncementService ApplicationServer:Redmond.contoso.com
     ```

     또는
    
     ```powershell
     New-CsUnassignedNumber -ExUmAutoAttendantPhoneNumber "+12065551234" -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551100"
     ```

     다음 예에서는 지정되지 않은 기존 번호 범위의 번호를 수정하는 방법을 보여 줍니다.
    
     ```powershell
     Set-CsUnassignedNumber -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551900"
     ```

## <a name="delete-an-unnasigned-number-range"></a>분석되지 않은 번호 범위 삭제

### <a name="to-use-skype-for-business-server-control-panel-to-delete-an-unassigned-number-range"></a>비즈니스용 Skype 서버 제어판을 사용하여 미지정 번호 범위를 삭제하려면

1.  RTCUniversalServerAdmins 그룹의 구성원이나 CsVoiceAdministrator, CsServerAdministrator 또는 CsAdministrator 역할의 구성원으로 컴퓨터에 로그온합니다. 자세한 내용은 **Delegate Setup Permissions** 을 참조하십시오.
    
2. 브라우저 창을 열고 관리 URL을 입력하여 비즈니스용 Skype 서버 제어판을 니다.  
    
3. 왼쪽 탐색 모음에서 **음성 기능** 을 클릭하고 **지정되지 않은 번호** 를 클릭합니다.
    
4. **지정되지 않은 번호** 페이지의 검색 필드에 삭제할 할당되지 않은 번호 범위의 이름 일부나 전체를 입력합니다.
    
5. 결과 번호 범위 목록에서 이름을 클릭하고 **편집** 을 클릭한 다음 **자세한 정보 표시** 를 클릭합니다.
    
6. **모두 커밋** 을 클릭합니다.
    
### <a name="to-use-skype-for-business-server-management-shell-to-delete-an-unassigned-number-range"></a>비즈니스용 Skype 서버 관리 셸을 사용하여 미지정 번호 범위를 삭제하려면

1. 비즈니스용 Skype 서버 관리 셸이 설치된 컴퓨터에 RTCUniversalServerAdmins 그룹의 구성원 또는 설치 권한 위임에 설명된 필요한 사용자 권한으로 **로그온합니다.**
    
2. 비즈니스용 Skype 서버 관리 셸 시작: **시작,** 모든 **프로그램,** 비즈니스용 **Skype 2015,** 비즈니스용 Skype 서버 관리 셸을 **클릭합니다.**
    
3. 명령줄에 다음을 입력합니다.
    
   ```powershell
   Remove-CsUnassignedNumber -Identity "<name of unassigned number range>" 
   ```

    예를 들면 다음과 같습니다.
    
   ```powershell
   Remove-CsUnassignedNumber -Identity "Unassigned range 1"
   ```

    > [!NOTE]
    > 추가 옵션에 대한 자세한 내용은 [Remove-CsCallParkOrbit을 참조하세요.](/powershell/module/skype/remove-cscallparkorbit?view=skype-ps) 
  
## <a name="see-also"></a>참고 항목

[New-CsUnassignedNumber](/powershell/module/skype/new-csunassignednumber?view=skype-ps)
  
[Set-CsUnassignedNumber](/powershell/module/skype/set-csunassignednumber?view=skype-ps)
  
[Get-CsUnassignedNumber](/powershell/module/skype/get-csunassignednumber?view=skype-ps)