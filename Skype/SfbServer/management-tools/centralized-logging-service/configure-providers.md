---
title: 비즈니스용 Skype 2015에서 중앙 로깅 서비스에 대한 공급자 구성
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 6a197ecf-b56b-45e0-8e7c-f532ec5164ff
description: '요약: 비즈니스용 Skype Server 2015에서 중앙 집중화 된 로깅 서비스에 대 한 시나리오 공급자를 구성 하는 방법에 대해 알아봅니다.'
ms.openlocfilehash: a9987d99b2caf00acc92de92a8d997845ad8f921
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36186825"
---
# <a name="configure-providers-for-centralized-logging-service-in-skype-for-business-server-2015"></a>비즈니스용 Skype 2015에서 중앙 로깅 서비스에 대한 공급자 구성
 
**요약:** 비즈니스용 Skype 서버 2015에서 중앙 로깅 서비스에 대 한 시나리오 공급자를 구성 하는 방법에 대해 알아봅니다.
  
중앙 로깅 서비스의 공급자에 대 한 개념 및 구성은 가장 중요 하 게 이해 하는 방법 중 하나입니다. 이 공급자는 비즈니스용 skype 서버 추적 모델의 비즈니스용 Skype 서버 역할 구성 요소에 직접 매핑됩니다. 공급자는 추적할 비즈니스용 Skype Server 2015의 구성 요소, 수집할 메시지 유형 (예: 치명적, 오류 또는 경고) 및 플래그를 정의 합니다 (예: TF_Connection 또는 TF_Diag). 공급자는 각 비즈니스용 Skype 서버 역할의 추적 가능한 구성 요소입니다. 공급자를 사용 하 여 구성 요소 (예: S4, SIPStack, IM 및 현재 상태)에 추적의 수준과 유형을 정의 합니다. 정의 된 공급자는 특정 문제 조건을 처리 하는 지정 된 논리적 수집에 대 한 모든 공급자를 그룹화 하는 시나리오에서 사용 됩니다.
  
비즈니스용 Skype Server Management Shell을 사용 하 여 중앙 집중화 된 로깅 서비스 기능을 실행 하려면 CsAdministrator 또는 CsServerAdministrator 역할 기반 액세스 제어 (RBAC) 보안 그룹 또는 사용자 지정 RBAC 역할의 구성원 이어야 합니다. 두 그룹 중 하나를 포함 합니다. 이 cmdlet이 할당 된 모든 RBAC (역할 기반 액세스 제어) 역할 목록 (직접 만든 사용자 지정 RBAC 역할 포함)을 반환 하려면 비즈니스용 Skype Server 관리 셸 또는 Windows PowerShell에서 다음 명령을 실행 합니다. 명령줄
  
```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Skype for Business Server 2015 cmdlet"}
```

예를 들면 다음과 같습니다.
  
```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

이 항목의 나머지 부분에서는 공급자를 정의 하 고, 공급자를 수정 하 고, 문제 해결을 최적화 하는 데 포함 된 공급자 정의에 대해 중점적으로 설명 합니다. 중앙 로깅 서비스 명령을 실행 하는 방법에는 두 가지가 있습니다. 기본적으로 directory C:\Program Files\Common Files\Skype for Business Server 2015 \ Clscontroller에 있는 CLSController .exe를 사용할 수 있습니다. 또는 비즈니스용 Skype Server Management Shell을 사용 하 여 Windows PowerShell 명령을 실행할 수 있습니다. Windows PowerShell을 사용 하 여 로깅 세션에서 사용할 새 공급자를 정의 하 고, 생성, 수집 하는 내용, 데이터를 수집 하는 수준에 대 한 완전 한 제어 권한을 가질 수 있습니다.
  
> [!IMPORTANT]
> 앞에서 언급 했 듯이 공급자는 매우 강력한 기능을 제공 합니다. 그러나 시나리오에는 공급자가 표시 하는 구성 요소에서 추적을 설정 하 고 실행 하는 데 필요한 모든 정보의 embodiment 포함 되어 있기 때문에 더 강력 합니다. 시나리오를 공급자 컬렉션으로 사용 하는 경우 많은 정보를 수집 하 고 명령줄에서 한 번에 하나씩 수백 개의 명령을 실행 하는 등 수백 개의 명령이 포함 된 배치 파일을 실행 하는 것에 비해 느슨하게 전환할 수 있습니다. 
  
공급자의 세부 정보를 자세히 설명 하는 대신 중앙 로깅 서비스는 이미 정의 된 다양 한 시나리오를 제공 합니다. 제공 되는 시나리오는 발생할 수 있는 대부분의 가능한 문제를 다룹니다. 드문 경우 지만, 공급자를 만들고 정의 하 고 시나리오에 할당 해야 할 수 있습니다. 새 공급자 및 시나리오를 만들어야 한다는 것을 조사 하기 전에 제공 되는 각 시나리오에 대해 잘 알고 있어야 합니다. 공급자를 만드는 방법에 대 한 정보를 참조 하는 것은 시나리오를 통해 추적 정보를 수집 하는 방법에 대 한 자세한 내용은 현재 제공 되지 않습니다. 
  
비즈니스의 [비즈니스용 Skype 2015 중앙 로깅 서비스](centralized-logging-service.md)에 도입 된 시나리오에서 사용할 공급자를 정의 하는 주요 요소는 다음과 같습니다.
  
- **공급자** OCSLogger 사용 하는 데 익숙한 경우 공급자는 OCSLogger 로그를 수집 하는 대상에 게 지정 하도록 선택 하는 구성 요소입니다. 공급자는 동일한 구성 요소 이며, 대부분의 경우에는 OCSLogger 구성 요소와 동일한 이름을 사용 합니다. OCSLogger 익숙하지 않은 경우 공급자는 중앙 로깅 서비스에서 로그를 수집할 수 있는 서버 역할 특정 구성 요소입니다. 중앙 로깅 서비스의 경우 CLSAgent는 공급자 구성에 정의 된 구성 요소의 추적을 수행 하는 중앙 로깅 서비스의 아키텍처 부분입니다.
    
- **로깅 수준** OCSLogger는 수집 된 데이터의 세부 수준 수를 선택 하는 옵션을 제공 합니다. 이 기능은 중앙 로깅 서비스 및 시나리오의 핵심 부분이 며 **Type** 매개 변수에 의해 정의 됩니다. 다음 중에서 선택할 수 있습니다.
    
  - **모든** 정의 된 공급자의 로그에 대 한 치명적인, 오류, 경고, 자세한 정보 및 디버그 정보 유형의 추적 메시지를 수집 합니다.
    
  - **치명적** "치명적"로 정의 된 추적 메시지만 수집 합니다.
    
  - **오류** "오류" 또는 "치명적"으로 정의 된 추적 메시지만 수집 합니다.
    
  - **경고가** "Warning" "" 오류 "및" 치명적 "유형의 추적 메시지만 수집 합니다.
    
  - **정보** 정의 된 공급자에 대 한 정보 메시지를 나타내는 추적 메시지와 치명적, 오류, 경고 메시지를 수집 합니다.
    
  - **자세한 정보** 정의 된 공급자에 대 한 치명적, 오류, 경고 및 자세한 유형의 모든 추적 메시지를 수집 합니다.
    
  - **디버그** 이는 본질적으로 "All ' (이에 해당)은 정의 된 공급자에 대 한 치명적, 오류, 경고, 정보, 자세한 정보 표시 및 디버그 유형의 추적을 수집 합니다.
    
- **플래그** OCSLogger는 추적 파일에서 검색할 수 있는 정보 유형을 정의한 각 공급자에 대 한 플래그를 선택 하는 옵션을 제공 합니다. 공급자에 따라 다음 플래그를 선택할 수 있습니다.
    
  - **TF_Connection** 연결 관련 로그 항목을 제공 합니다. 이러한 로그에는 특정 구성 요소에 설정 된 연결에 대 한 정보가 포함 됩니다. 여기에는 중요 한 네트워크 수준 정보 (즉, 연결 개념 없이 구성 요소)도 포함 될 수 있습니다.
    
  - **TF_Security** 보안과 관련 된 모든 이벤트/로그 항목을 제공 합니다. 예를 들어 SipStack의 경우 도메인 유효성 검사 오류, 클라이언트 인증/권한 부여 실패 등의 보안 이벤트입니다.
    
  - **TF_Diag** 구성 요소를 진단 하거나 문제를 해결 하는 데 사용할 수 있는 진단 이벤트를 제공 합니다. 예를 들어 SipStack의 경우 인증서 오류 또는 DNS 경고/오류입니다.
    
  - **TF_Protocol** SIP 및 결합 된 커뮤니티 코덱 팩 메시지 등의 프로토콜 메시지를 제공 합니다.
    
  - **TF_Component** 공급자의 일부로 지정 된 구성 요소에 대 한 로깅을 사용 하도록 설정 합니다.
    
  - **모든** 공급자에 대해 사용할 수 있는 모든 플래그를 설정 합니다.
    
### <a name="to-review-information-about-existing-centralized-logging-service-scenario-providers"></a>기존 중앙 집중화 된 로깅 서비스 시나리오 공급자에 대 한 정보를 검토 하려면

1. 비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **비즈니스용 skype 2015**을 차례로 클릭 한 다음 비즈니스용 **skype Server management Shell**을 클릭 합니다.
    
2. 기존 공급자의 구성을 검토 하려면 다음을 입력 합니다.
    
   ```
   Get-CsClsScenario -Identity <scope and scenario name>
   ```

    예를 들어 전역 회의 수행자에 대 한 정보를 검토 하려면 다음을 입력 합니다.
    
   ```
   Get-CsClsScenario -Identity "global/CAA"
   ```

    이 명령은 연결 된 플래그, 설정 및 구성 요소와 함께 공급자 목록을 표시 합니다. 표시 되는 정보가 부족 하거나 목록이 기본 Windows PowerShell 목록 형식에 비해 너무 긴 경우 다른 출력 방법을 정의 하 여 추가 정보를 표시할 수 있습니다. 이렇게 하려면 다음을 입력 합니다.
    
   ```
   Get-CsClsScenario -Identity "global/CAA" | Select-Object -ExpandProperty Provider
   ```

    이 명령의 출력은 공급자 이름, 로깅 형식, 로깅 수준, 플래그, GUID, 역할 등 5 개의 줄 형식으로 표시 되는 각 공급자를 각각 별도의 줄에 표시 합니다. 
    
### <a name="to-define-a-new-centralized-logging-service-scenario-provider"></a>중앙 집중화 된 새 로깅 서비스 시나리오 공급자를 정의 하려면

1. 비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **비즈니스용 skype 2015**을 차례로 클릭 한 다음 비즈니스용 **skype Server management Shell**을 클릭 합니다.
    
2. 시나리오 공급자는 추적 하는 구성 요소, 사용할 플래그, 수집할 세부 정보 수준으로 구성 됩니다. 다음을 입력 하 여이 작업을 수행 합니다.
    
   ```
   $<variableName> = New-CsClsProvider -Name <provider component> -Type <log type> -Level <log level detail type> -Flags <provider trace log flags>
   ```

    예를 들어 수집 대상을 정의 하 고 Lyss 공급자의 세부 정보 수준에 대 한 추적 공급자 정의는 다음과 같습니다.
    
   ```
   $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Info" -Flags "All"
   ```

-Level은 치명적, 오류, 경고 및 정보 메시지를 수집 합니다. 사용 된 플래그는 Lyss 공급자에 대해 정의 되 고 TF_Connection, TF_Diag 및 TF_Protocol을 포함 합니다. 변수 $LyssProvider 정의 된 후에는 **새 CsClsScenario** cmdlet을 사용 하 여 lyss 공급자에서 추적을 수집할 수 있습니다. 새 시나리오에 대 한 공급자 만들기 및 할당을 완료 하려면 다음을 입력 합니다.

```
New-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider $LyssProvider
```

여기서 $LyssProvider은 **새 CsClsProvider**를 사용 하 여 만든 정의 된 시나리오를 포함 하는 변수입니다.
### <a name="to-change-an-existing-centralized-logging-service-scenario-provider"></a>기존 중앙 집중화 된 로깅 서비스 시나리오 공급자를 변경 하려면

1. 비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **비즈니스용 skype 2015**을 차례로 클릭 한 다음 비즈니스용 **skype Server management Shell**을 클릭 합니다.
    
2. 기존 공급자의 구성을 업데이트 하거나 변경 하려면 다음을 입력 합니다.
    
   ```
   $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Debug" -Flags "TF_Connection, TF_Diag"
   ```

    그런 다음 시나리오를 업데이트 하 여 다음을 입력 하 여 공급자를 할당 합니다.
    
   ```
   Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider $LyssProvider
   ```

이 명령의 최종 결과는 시나리오 사이트: 레드먼드/RedmondLyssInfo에 할당 된 공급자에 대 한 플래그와 수준을 업데이트 하는 것입니다. Get-CsClsScenario를 사용 하 여 새 시나리오를 볼 수 있습니다. 자세한 내용은 [Get CsClsScenario](https://docs.microsoft.com/powershell/module/skype/get-csclsscenario?view=skype-ps)를 참조 하세요.
> [!CAUTION]
> **새-ClsCsProvider** 는 플래그가 유효한 지 여부를 확인 하지 않습니다. 플래그의 철자 (예: TF_DIAG 또는 TF_CONNECTION)가 정확한 지 확인 합니다. 플래그에 맞춤법이 잘못 된 경우 공급자는 필요한 로그 정보를 반환할 수 없습니다.
  
이 시나리오에 추가 공급자를 추가 하려면 다음을 입력 합니다.

```
Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider @{Add=$ABSProvider, $CASProvider, S4Provider}
```

Add 지시문을 사용 하 여 정의 된 각 공급자는 이미 **새 CsClsProvider** 프로세스를 사용 하 여 정의 되었습니다.
### <a name="to-remove-a-scenario-provider"></a>시나리오 공급자를 제거 하려면

1. 비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **비즈니스용 skype 2015**을 차례로 클릭 한 다음 비즈니스용 **skype Server management Shell**을 클릭 합니다.
    
2. 제공 된 cmdlet을 사용 하 여 기존 공급자를 업데이트 하 고 새 공급자를 만들 수 있습니다. 공급자를 제거 하려면 Provider 매개 변수에 대 한 Replace 지시문을 **Set-CsClsScenario**에 사용 해야 합니다. 공급자를 완전히 제거 하는 유일한 방법은 동일한 이름의 재정의 된 공급자로 바꾼 다음 Update 지시문을 사용 하는 것입니다. 예를 들어, 공급자 LyssProvider는 WPP를 사용 하 여 로그 유형으로 설정 되 고, TF_CONNECTION에 대 한 수준이 지정 되 고, 플래그 집합이 TF_DIAG로 정의 됩니다. 플래그를 "모두"로 변경 해야 합니다. 공급자를 변경 하려면 다음을 입력 합니다.
    
   ```
   $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Debug" -Flags "All"
   ```

   ```
   Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider @{Replace=$LyssProvider}
   ```

3. 시나리오 및이에 연결 된 공급자를 완전히 제거 하려면 다음을 입력 합니다.
    
   ```
   Remove-CsClsScenario -Identity <scope and name of scenario>
   ```

    예를 들면 다음과 같습니다.
    
   ```
   Remove-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo"
   ```

    > [!CAUTION]
    > Cmdlet **제거-CsClsScenario** 에서는 확인 메시지가 표시 되지 않습니다. 시나리오는 자신에 게 할당 된 공급자와 함께 삭제 됩니다. 처음으로 생성 하는 데 사용 된 명령을 다시 실행 하 여 시나리오를 다시 만들 수 있습니다. 제거 된 시나리오 또는 공급자를 복구 하는 방법은 없습니다.
  
**제거-CsClsScenario** cmdlet을 사용 하 여 시나리오를 제거 하면 범위에서 해당 시나리오가 완전히 제거 됩니다. 자신이 만든 시나리오와 시나리오의 일부인 공급자를 사용 하려면 새 공급자를 만들고 새 시나리오에 할당 합니다.
## <a name="see-also"></a>참고 항목

[Get-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/get-csclsscenario?view=skype-ps)
  
[신규-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/new-csclsscenario?view=skype-ps)
  
[-CsClsScenario 제거](https://docs.microsoft.com/powershell/module/skype/remove-csclsscenario?view=skype-ps)
  
[Set-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/set-csclsscenario?view=skype-ps)
  
[새-CsClsProvider](https://docs.microsoft.com/powershell/module/skype/new-csclsprovider?view=skype-ps)
