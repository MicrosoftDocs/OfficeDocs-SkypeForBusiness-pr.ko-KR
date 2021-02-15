---
title: 비즈니스용 Skype 서버에서 중앙 로깅 서비스에 대한 공급자 구성
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 6a197ecf-b56b-45e0-8e7c-f532ec5164ff
description: '요약: 비즈니스용 Skype 서버 2015에서 중앙 로깅 서비스에 대한 시나리오 공급자를 구성하는 방법을 설명합니다.'
ms.openlocfilehash: c96a87ea76930dbd99341667852a9731e56b88b5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49835168"
---
# <a name="configure-providers-for-centralized-logging-service-in-skype-for-business-server-2015"></a>비즈니스용 Skype 서버에서 중앙 로깅 서비스에 대한 공급자 구성
 
**요약:** 비즈니스용 Skype 서버 2015에서 중앙 로깅 서비스에 대한 시나리오 공급자를 구성하는 방법을 설명합니다.
  
중앙 로깅 서비스의 공급자 개념 및 구성은 파악하는 데 가장 중요한 요소 중 하나입니다. Theproviders map directly to Skype for Business Server server role components in the Skype for Business Server tracing model. 공급자는 추적할 비즈니스용 Skype 서버 2015의 구성 요소, 수집할 메시지 유형(예: 치명적, 오류 또는 경고) 및 플래그(예: TF_Connection 또는 TF_Diag)를 정의합니다. 공급자는 각 비즈니스용 Skype 서버 역할의 추적 가능한 구성 요소입니다. 공급자를 사용하여 구성 요소에 대한 추적 수준 및 유형(예: S4, SIPStack, IM 및 현재 상태)을 정의합니다. 정의된 공급자는 특정 문제 조건을 해결한 특정 논리적 컬렉션에 대한 모든 공급자를 그룹화하는 시나리오에서 사용됩니다.
  
비즈니스용 Skype 서버 관리 셸을 사용하여 중앙 로깅 서비스 기능을 실행하려면 CsAdministrator 또는 CsServerAdministrator RBAC(역할 기반 액세스 제어) 보안 그룹의 구성원 또는 이러한 두 그룹 중 하나를 포함하는 사용자 지정 RBAC 역할의 구성원이 되어야 합니다. 직접 만든 사용자 지정 RBAC(역할 기반 액세스 제어) 역할을 포함하여 이 cmdlet이 할당된 모든 RBAC 역할의 목록을 반환하기 위해 비즈니스용 Skype 서버 관리 셸 또는 Windows PowerShell 프롬프트에서 다음 명령을 실행합니다.
  
```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Skype for Business Server 2015 cmdlet"}
```

예시:
  
```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

이 항목의 나머지에서는 문제 해결을 최적화하기 위해 공급자를 정의하고 공급자를 수정하는 방법 및 공급자 정의에 포함된 항목을 중점적으로 다 사용합니다. 중앙 로깅 서비스 명령을 발급하는 방법에는 두 가지가 있습니다. 기본적으로 C:\Program Files\Common Files\Skype for Business Server 2015\CLSAgent 디렉터리에 있는 CLSController.exe 사용할 수 있습니다. 또는 비즈니스용 Skype 서버 관리 셸을 사용하여 비즈니스용 Skype Windows PowerShell 있습니다. 이 Windows PowerShell 사용하여 로깅 세션에서 사용할 새 공급자를 정의하고 생성, 수집한 데이터 및 데이터를 수집하는 수준에 대한 모든 제어를 할 수 있습니다.
  
> [!IMPORTANT]
> 앞서 언급한 것 처럼 공급자는 매우 강력합니다. 그러나 시나리오는 공급자가 나타내는 구성 요소에 대해 추적을 설정하고 실행하는 데 필요한 모든 정보를 포함하기 때문에 더 강력합니다. 시나리오가 공급자 모음인 경우 명령줄에서 동시에 수백 개의 명령을 실행하는 경우와 많은 정보를 수집하는 명령이 포함된 배치 파일을 실행하는 경우와 느슨하게 비교할 수 있습니다. 
  
중앙 로깅 서비스는 공급자의 세부 정보를 자세히 조사하도록 요구하는 대신 이미 정의된 여러 시나리오를 제공합니다. 제공된 시나리오에는 발생할 수 있는 대부분의 문제가 다를 수 있습니다. 드문 경우지만 공급자를 만들고 정의하여 시나리오에 할당해야 할 수 있습니다. 새 공급자 및 시나리오를 만들어야 하는 필요성을 조사하기 전에 제공된 각 시나리오에 대해 잘 알고 있는 것이 좋습니다. 여기서는 시나리오에서 공급자 요소를 사용하여 추적 정보를 수집하는 방법을 익숙하게 설명하기 위해 공급자를 만드는 방법에 대한 정보가 제공된 반면, 현재는 공급자 자체에 대한 세부 정보가 제공되지 않습니다. 
  
비즈니스용 [Skype 2015의](centralized-logging-service.md)중앙 로깅 서비스에 도입된 시나리오에서 사용할 공급자를 정의하는 주요 요소는 다음입니다.
  
- **공급자** OCSLogger에 익숙한 경우 공급자는 추적 엔진이 로그를 수집할 것을 OCSLogger에 알려 주기 위해 선택하는 구성 요소입니다. 공급자는 구성 요소와 같고 대부분의 경우 OCSLogger의 구성 요소와 이름이 같습니다. OCSLogger에 익숙하지 않은 경우 공급자는 중앙 로깅 서비스에서 로그를 수집할 수 있는 서버 역할별 구성 요소입니다. 중앙 로깅 서비스의 경우 CLSAgent는 공급자 구성에서 정의하는 구성 요소의 추적을 수행하고 있는 중앙 로깅 서비스의 아키텍처 부분입니다.
    
- **로깅 수준** OCSLogger는 수집된 데이터에 대한 다양한 세부 정보를 선택할 수 있는 옵션을 제공했습니다. 이 기능은 중앙 로깅 서비스 및 시나리오의 핵심 부분으로, **Type** 매개 변수에 의해 정의됩니다. 다음 중에서 선택할 수 있습니다.
    
  - **모두** 정의된 공급자에 대한 로그에 치명적, 오류, 경고, 자세한 정보 및 디버그 정보 유형의 추적 메시지를 수집합니다.
    
  - **치명적** "Fatal"으로 정의된 추적 메시지만 수집합니다.
    
  - **오류** "오류" 또는 "치명적"으로 정의된 추적 메시지만 수집합니다.
    
  - **경고** "Warning", "Error" 및 "Fatal" 유형의 추적 메시지만 수집합니다.
    
  - **정보** 정의된 공급자에 대한 정보 메시지와 치명적, 오류 및 경고 메시지를 나타내는 추적 메시지만 수집합니다.
    
  - **Verbose** 정의된 공급자에 대한 치명적, 오류, 경고 및 자세한 유형의 추적 메시지를 모두 수집합니다.
    
  - **디버그는** 기본적으로 'All'과 동등합니다. 정의된 공급자에 대한 Fatal, Error, Warning, Info, Verbose 및 Debug 유형의 추적을 수집합니다.
    
- **플래그** OCSLogger는 추적 파일에서 검색할 수 있는 정보 유형을 정의하는 각 공급자에 대한 플래그를 선택할 수 있는 옵션을 제공했습니다. 공급자에 따라 다음 플래그를 선택해야 합니다.
    
  - **TF_Connection** 연결 관련 로그 항목을 제공합니다. 이러한 로그에는 특정 구성 요소와의 연결에 대한 정보가 포함됩니다. 여기에는 중요한 네트워크 수준 정보(즉, 연결 개념이 없는 구성 요소의 경우)도 포함됩니다.
    
  - **TF_Security** 보안과 관련된 모든 이벤트/로그 항목을 제공합니다. 예를 들어 SipStack의 경우 이러한 이벤트는 도메인 유효성 검사 실패, 클라이언트 인증/권한 부여 오류와 같은 보안 이벤트입니다.
    
  - **TF_Diag** 구성 요소를 진단하거나 문제를 해결하는 데 사용할 수 있는 진단 이벤트를 제공합니다. 예를 들어 SipStack의 경우 인증서 오류 또는 DNS 경고/오류입니다.
    
  - **TF_Protocol** SIP 및 결합 커뮤니티 코덱 팩 메시지와 같은 프로토콜 메시지를 제공합니다.
    
  - **TF_Component** 공급자의 일부로 지정된 구성 요소에 대한 로깅을 지원합니다.
    
  - **모두** 공급자에 사용할 수 있는 모든 플래그를 지정합니다.
    
### <a name="to-review-information-about-existing-centralized-logging-service-scenario-providers"></a>기존 중앙 로깅 서비스 시나리오 공급자에 대한 정보를 검토하기 위해

1. 비즈니스용 Skype 서버 관리 셸 시작: **시작,** **모든** 프로그램, 비즈니스용 **Skype 2015,** 비즈니스용 Skype 서버 관리 셸을 **클릭합니다.**
    
2. 기존 공급자의 구성을 검토하려면 다음을 입력합니다.
    
   ```PowerShell
   Get-CsClsScenario -Identity <scope and scenario name>
   ```

    예를 들어 전역 회의 참석자에 대한 정보를 검토하기 위해 다음을 입력합니다.
    
   ```PowerShell
   Get-CsClsScenario -Identity "global/CAA"
   ```

    이 명령은 연결된 플래그, 설정 및 구성 요소가 있는 공급자 목록을 표시합니다. 표시되는 정보가 충분하지 않은 경우 또는 목록이 기본 목록 Windows PowerShell 너무 긴 경우 다른 출력 방법을 정의하여 추가 정보를 표시할 수 있습니다. 이렇게 하려면 다음을 입력합니다.
    
   ```PowerShell
   Get-CsClsScenario -Identity "global/CAA" | Select-Object -ExpandProperty Provider
   ```

    이 명령의 출력은 공급자 이름, 로깅 유형, 로깅 수준, 플래그, GUID 및 역할이 각각 별도의 줄에 있는 5줄 형식으로 표시되는 각 공급자를 표시합니다. 
    
### <a name="to-define-a-new-centralized-logging-service-scenario-provider"></a>새 중앙 로깅 서비스 시나리오 공급자를 정의하기 위해

1. 비즈니스용 Skype 서버 관리 셸 시작: **시작,** **모든** 프로그램, 비즈니스용 **Skype 2015,** 비즈니스용 Skype 서버 관리 셸을 **클릭합니다.**
    
2. 시나리오 공급자는 추적할 구성 요소, 사용할 플래그 및 수집할 세부 정보 수준으로 구성됩니다. 이 작업을 위해 다음을 입력합니다.
    
   ```PowerShell
   $<variableName> = New-CsClsProvider -Name <provider component> -Type <log type> -Level <log level detail type> -Flags <provider trace log flags>
   ```

    예를 들어 수집할 내용과 Lyss 공급자의 세부 정보 수준을 정의하는 추적 공급자 정의는 다음과 같습니다.
    
   ```PowerShell
   $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Info" -Flags "All"
   ```

-Level은 치명적, 오류, 경고 및 정보 메시지를 수집합니다. 사용되는 플래그는 Lyss 공급자에 대해 정의된 모든 플래그로 TF_Connection, TF_Diag 및 TF_Protocol.변수 $LyssProvider 정의한 후 **New-CsClsScenario** cmdlet과 함께 사용하여 Lyss 공급자에서 추적을 수집할 수 있습니다. 공급자 만들기 및 새 시나리오에 공급자 할당을 완료하기 위해 다음을 입력합니다.

```PowerShell
New-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider $LyssProvider
```

여기서 $LyssProvider 변수는 **New-CsClsProvider로** 만든 정의된 시나리오를 포함하는 변수입니다.
### <a name="to-change-an-existing-centralized-logging-service-scenario-provider"></a>기존 중앙 로깅 서비스 시나리오 공급자를 변경합니다.

1. 비즈니스용 Skype 서버 관리 셸 시작: **시작,** **모든** 프로그램, 비즈니스용 **Skype 2015,** 비즈니스용 Skype 서버 관리 셸을 **클릭합니다.**
    
2. 기존 공급자의 구성을 업데이트하거나 변경하려면 다음을 입력합니다.
    
   ```PowerShell
   $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Debug" -Flags "TF_Connection, TF_Diag"
   ```

    그런 다음 다음을 입력하여 공급자를 할당하는 시나리오를 업데이트합니다.
    
   ```PowerShell
   Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider $LyssProvider
   ```

명령의 최종 결과는 시나리오 site:Redmond/RedmondLyssInfo에 할당된 공급자에 대한 플래그 및 수준이 업데이트됩니다. Get-CsClsScenario를 사용하여 새 시나리오를 볼 수 있습니다. 자세한 내용은 [Get-CsClsScenario를 참조합니다.](https://docs.microsoft.com/powershell/module/skype/get-csclsscenario?view=skype-ps)
> [!CAUTION]
> **New-ClsCsProvider는** 플래그가 유효한지 여부를 확인하지 않습니다. 플래그(예: TF_DIAG 또는 TF_CONNECTION)의 맞춤법을 올바르게 입력해야 합니다. 플래그의 철자가 제대로 지정되지 않으면 공급자가 예상한 로그 정보를 반환할 수 없습니다.
  
이 시나리오에 공급자를 더 추가하려는 경우 다음을 입력합니다.

```PowerShell
Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider @{Add=$ABSProvider, $CASProvider, S4Provider}
```

Add 지시문으로 정의된 각 공급자는 **New-CsClsProvider** 프로세스를 사용하여 이미 정의되어 있습니다.
### <a name="to-remove-a-scenario-provider"></a>시나리오 공급자를 제거하려면

1. 비즈니스용 Skype 서버 관리 셸 시작: **시작,** **모든** 프로그램, 비즈니스용 **Skype 2015,** 비즈니스용 Skype 서버 관리 셸을 **클릭합니다.**
    
2. 제공된 cmdlet을 사용하여 기존 공급자를 업데이트하고 새 공급자를 만들 수 있습니다. 공급자를 제거하려면 Provider 매개 변수에 대한 Replace 지시문을 **Set-CsClsScenario로 설정해야 합니다.** 공급자를 완전히 제거하는 유일한 방법은 공급자를 같은 이름의 다시 정의된 공급자로 바꾸고 업데이트 지시문을 사용하는 것입니다. 예를 들어 공급자 LyssProvider는 WPP를 로그 유형으로 정의하고, 수준이 디버그로 설정되고, 플래그 집합은 TF_CONNECTION TF_DIAG. 플래그를 "모두"로 변경해야 합니다. 공급자를 변경하기 위해 다음을 입력합니다.
    
   ```PowerShell
   $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Debug" -Flags "All"
   ```

   ```PowerShell
   Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider @{Replace=$LyssProvider}
   ```

3. 시나리오 및 시나리오와 연결된 공급자를 완전히 제거하려면 다음을 입력합니다.
    
   ```PowerShell
   Remove-CsClsScenario -Identity <scope and name of scenario>
   ```

    예시:
    
   ```PowerShell
   Remove-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo"
   ```

    > [!CAUTION]
    > **Remove-CsClsScenario** cmdlet은 확인 메시지를 표시하지 않습니다. 시나리오가 할당된 공급자와 함께 삭제됩니다. 시나리오를 처음 만드는 데 사용된 명령을 다시 실행하여 시나리오를 다시 만들 수 있습니다. 제거된 시나리오나 공급자를 복구하는 절차는 없습니다.
  
**Remove-CsClsScenario** cmdlet을 사용하여 시나리오를 제거하면 범위에서 시나리오가 완전히 제거됩니다. 시나리오의 일부인 시나리오와 공급자를 사용하기 위해 새 공급자를 만들어 새 시나리오에 할당합니다.
## <a name="see-also"></a>참고 항목

[Get-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/get-csclsscenario?view=skype-ps)
  
[New-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/new-csclsscenario?view=skype-ps)
  
[Remove-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/remove-csclsscenario?view=skype-ps)
  
[Set-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/set-csclsscenario?view=skype-ps)
  
[New-CsClsProvider](https://docs.microsoft.com/powershell/module/skype/new-csclsprovider?view=skype-ps)
