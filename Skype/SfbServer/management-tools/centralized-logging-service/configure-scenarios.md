---
title: 2015년 8월의 중앙 로깅 서비스에 대한 비즈니스용 Skype 서버 구성
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 6c3bf826-e7fd-4002-95dc-01020641ef01
description: '요약: 2015년 8월에 중앙 로깅 서비스에 대한 시나리오를 만들고 수정하고 제거하는 비즈니스용 Skype 서버 설명합니다.'
ms.openlocfilehash: da9a3c431be78a3abeab929fab86f1bf45e6cfa7
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60766346"
---
# <a name="configure-scenarios-for-the-centralized-logging-service-in-skype-for-business-server-2015"></a>2015년 8월의 중앙 로깅 서비스에 대한 비즈니스용 Skype 서버 구성
 
**요약:** 2015년 8월에 중앙 로깅 서비스에 대한 시나리오를 만들고 수정하고 제거하는 방법을 비즈니스용 Skype 서버 설명합니다.
  
시나리오는 범위(전역, 사이트, 풀 또는 컴퓨터)와 중앙 로깅 서비스에서 사용할 공급자를 정의합니다. 시나리오를 사용하면 공급자(예: S4, SIPStack, IM 및 현재 상태)에서 추적을 사용하도록 설정하거나 사용하지 않도록 설정할 수 있습니다. 시나리오를 구성하여 특정 문제 조건을 해결하는 특정 논리 컬렉션에 대한 모든 공급자를 그룹화할 수 있습니다. 문제 해결 및 로깅 요구를 충족하기 위해 시나리오를 수정해야 하는 경우 비즈니스용 Skype 서버 2015 디버그 도구는Edit-CsClsScenario라는 함수가 포함된 Windows PowerShell 모듈인 ClsScenarioEdit.psm1을 제공합니다. 모듈의 목적은 명명된 시나리오의 속성을 편집하는 것입니다. 이 항목에서는 이 모듈의 작동 방식에 대한 예제를 제공합니다. 계속하기 전에 비즈니스용 Skype 서버 2015 [디버깅](https://go.microsoft.com/fwlink/p/?LinkId=285257) 도구를 다운로드합니다.
  
> [!IMPORTANT]
> 특정 범위(사이트, 전역, 풀 또는 컴퓨터)에 대해 특정 시기에 최대 두 개의 시나리오를 실행할 수 있습니다. 현재 실행 중인 시나리오를 확인하기 위해 Windows PowerShell [및 Get-CsClsScenario를 사용 합니다.](/powershell/module/skype/get-csclsscenario?view=skype-ps) [Set-Windows PowerShell 및 Set-CsClsScenario를](/powershell/module/skype/set-csclsscenario?view=skype-ps)사용하여 실행 중인 시나리오를 동적으로 변경할 수 있습니다. 로깅 세션 중에 실행 중인 시나리오를 수정하여 수집 중인 데이터를 조정하거나 구체화하고 공급자를 구체화할 수 있습니다. 
  
비즈니스용 Skype 서버 관리 셸을 사용하여 중앙 로깅 서비스 기능을 실행하려면 CsAdministrator 또는 CsServerAdministrator RBAC(역할 기반 액세스 제어) 보안 그룹 또는 이러한 두 그룹 중 하나를 포함하는 사용자 지정 RBAC 역할의 구성원이 되어야 합니다. 직접 만든 사용자 지정 RBAC 역할을 포함하여 이 cmdlet이 할당된 모든 RBAC 역할의 목록을 반환하기 위해 비즈니스용 Skype 서버 관리 셸 또는 Windows PowerShell 프롬프트에서 다음 명령을 실행합니다.
  
```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Skype for Business Server 2015 cmdlet"}
```

예제:
  
```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

이 항목의 나머지에서는 시나리오를 정의하고, 시나리오를 수정하고, 실행 중인 시나리오를 검색하고, 시나리오를 제거하고, 문제 해결을 최적화하기 위해 시나리오에 포함된 항목을 지정하는 방법에 대해 중점적으로 설명합니다. 관리 셸을 사용하여 비즈니스용 Skype 서버 명령을 Windows PowerShell 있습니다. 로깅 Windows PowerShell 로깅 세션에서 사용할 새 시나리오를 정의할 수 있습니다.
  
비즈니스용 Skype [2015의](centralized-logging-service.md)중앙 로깅 서비스에 도입된 시나리오의 요소는 다음입니다.
  
- **공급자** OCSLogger에 익숙한 경우 공급자는 추적 엔진이 로그를 수집할지 OCSLogger에 알려 주기 위해 선택하는 구성 요소입니다. 공급자는 동일한 구성 요소로, 대부분의 경우 OCSLogger의 구성 요소와 이름이 같습니다. OCSLogger에 익숙하지 않은 경우 공급자는 중앙 로깅 서비스에서 로그를 수집할 수 있는 서버 역할별 구성 요소입니다. 공급자 구성에 대한 자세한 내용은 [Configure providers for Centralized Logging Service in 비즈니스용 Skype 서버 2015을 참조합니다.](configure-providers.md)
    
- **ID** 매개 변수 -Identity는 시나리오의 범위와 이름을 설정합니다. 예를 들어 범위를 "global"으로 설정하고 시나리오를 "LyssServiceScenario"로 식별할 수 있습니다. 이 두 가지를 결합할 때 ID를 정의합니다(예: "global/LyssServiceScenario").
    
    원하는 경우 -Name 및 -Parent 매개 변수를 사용할 수 있습니다. Name 매개 변수를 정의하여 시나리오를 고유하게 식별합니다. Name을 사용하는 경우 Parent를 사용하여 전역 또는 사이트에 시나리오를 추가해야 합니다. 
    
    > [!IMPORTANT]
    > Name 및 Parent 매개 변수를 사용하는 경우 **-Identity** 매개 변수를 사용할 수 없습니다.
  
### <a name="to-create-a-new-scenario-with-the-new-csclsscenario-cmdlet"></a>cmdlet을 사용하여 새 시나리오를 New-CsClsScenario

1. 비즈니스용 Skype 서버 시작: **시작,** 모든 프로그램, 비즈니스용 Skype **2015를** 클릭한 다음 관리 **비즈니스용 Skype 서버 를 클릭합니다.**
    
2. 로깅 세션에 대한 새 시나리오를 만들 경우 [New-CsClsProvider를](/powershell/module/skype/new-csclsprovider?view=skype-ps) 사용하여 시나리오의 이름(즉, 고유하게 식별되는 방법)을 정의합니다. WPP에서 로깅 형식 유형(예: Windows 소프트웨어 추적 전 처리기), EventLog(즉, Windows 이벤트 로그 형식) 또는 IISLog(IIS 로그 파일 형식을 기반으로 하는 ASCII 형식 파일)를 선택합니다. 그런 다음 Level(이 항목의 로깅 수준에 정의된 수준) 및 플래그(이 항목의 플래그에 정의되어 있는 경우)를 정의합니다.
    
    이 예제 시나리오에서는 예제 공급자 변수로 LyssProvider를 사용합니다.
    
    정의된 옵션을 사용하여 시나리오를 만들 경우 다음을 입력합니다.
    
   ```PowerShell
   New-CsClsScenario -Identity <scope>/<unique scenario name> -Provider <provider variable>
   ```

    예제:
    
   ```PowerShell
   New-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider $LyssProvider
   ```

    -Name 및 -Parent를 사용하는 대체 형식:
    
   ```PowerShell
   New-CsClsScenario -Name "LyssServiceScenario" -Parent "site:Redmond" -Provider $LyssProvider
   ```

### <a name="to-create-a-new-scenario-with-multiple-providers-with-the-new-csclsscenario-cmdlet"></a>cmdlet을 사용하여 여러 공급자를 사용하여 새 시나리오를 New-CsClsScenario

1. 비즈니스용 Skype 서버 시작: **시작,** 모든 프로그램, 비즈니스용 Skype **2015를** 클릭한 다음 관리 **비즈니스용 Skype 서버 를 클릭합니다.**
    
2. 범위당 두 가지 시나리오로 제한됩니다. 그러나 설정된 수의 공급자로 제한되지는 않습니다. 이 예제에서는 세 개의 공급자를 만들었다고 가정하고 정의하는 시나리오에 세 공급자를 모두 할당하려는 경우를 가정합니다. 공급자 변수 이름은 LyssProvider, ABServerProvider 및 SIPStackProvider입니다. 시나리오에 여러 공급자를 정의하고 할당하기 위해 비즈니스용 Skype 서버 관리 셸 또는 명령 프롬프트에 Windows PowerShell 입력합니다.
    
   ```PowerShell
   New-CsClsScenario -Identity "site:Redmond/CollectDataScenario" -Provider @{Add=$LyssProvider, $ABServerProvider,  $SIPStackProvider}
   ```

    > [!NOTE]
    > 이 규칙은 Windows PowerShell 사용하여 값의 해시 테이블을 만드는 규칙을 `@{<variable>=<value1>, <value2>, <value>…}` assplatting라고 합니다. 2016의 스플래팅에 대한 자세한 Windows PowerShell 를 [https://go.microsoft.com/fwlink/p/?LinkId=267760](/previous-versions/technet-magazine/gg675931(v=msdn.10)) 참조합니다. 
  
### <a name="to-modify-an-existing-scenario-with-the-set-csclsscenario-cmdlet"></a>cmdlet을 통해 기존 시나리오를 Set-CsClsScenario

1. 비즈니스용 Skype 서버 시작: **시작,** 모든 프로그램, 비즈니스용 Skype **2015를** 클릭한 다음 관리 **비즈니스용 Skype 서버 를 클릭합니다.**
    
2. 범위당 두 가지 시나리오로 제한됩니다. 로깅 캡처 세션이 진행 중인 경우에도 언제든 실행 중인 시나리오를 변경할 수 있습니다. 실행 중인 시나리오를 다시 디자인하면 현재 로깅 세션에서 제거된 시나리오의 사용을 중지한 다음 새 시나리오 사용을 시작하게 됩니다. 그러나 제거된 시나리오로 캡처된 로깅 정보는 캡처된 로그에 남아 있습니다. 새 시나리오를 정의하기 위해 다음을(즉, "S4Provider"라는 이미 정의된 공급자를 추가하는 경우) 다음을 사용합니다.
    
   ```PowerShell
   Set-CsClsScenario -Identity <name of scope and scenario defined by New-CsClsScenario> -Provider @{Add=<new provider to add>}
   ```

    예제:
    
   ```PowerShell
   Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Add=$S4Provider}
   ```

    공급자를 대체하려는 경우 현재 집합을 대체할 단일 공급자 또는 콤보로 구분된 공급자 목록을 정의합니다. 여러 공급자 중 하나만 교체하려는 경우 현재 공급자를 새 공급자로 추가하여 새 공급자와 기존 공급자를 모두 포함하는 새 공급자 집합을 만드면 됩니다. 모든 공급자를 새 집합으로 바꾸기 위해 다음을 입력합니다.
    
   ```PowerShell
   Set-CsClsScenario -Identity <name of scope and scenario defined by New-CsClsScenario> -Provider @{Replace=<providers to replace existing provider set>}
   ```

    예를 들어 현재 $LyssProvider, $ABServerProvider 및 $SIPStackProvider $LyssServiceProvider.
    
   ```PowerShell
   Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Replace=$LyssServiceProvider}
   ```

    현재 $LyssProvider, $ABServerProvider 및 $SIPStackProvider 집합의 $LyssProvider 공급자만 $LyssServiceProvider 다음을 입력합니다.
    
   ```PowerShell
   Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Replace=$LyssServiceProvider, $ABServerProvider, $SIPStackProvider}
   ```

### <a name="to-remove-an-existing-scenario-with-the-remove-csclsscenario-cmdlet"></a>cmdlet을 사용하여 기존 시나리오를 Remove-CsClsScenario

1. 비즈니스용 Skype 서버 시작: **시작,** 모든 프로그램, 비즈니스용 Skype **2015를** 클릭한 다음 관리 **비즈니스용 Skype 서버 를 클릭합니다.**
    
2. 이전에 정의한 시나리오를 제거하려면 다음을 입력합니다.
    
   ```PowerShell
   Remove-CsClsScenario -Identity <name of scope and scenario>
   ```

    예를 들어 정의된 시나리오 site:Redmond/LyssServiceScenario를 제거하려면
    
   ```PowerShell
   Remove-CsClsScenario -Identity "site:Redmond/LyssServiceScenario"
   ```

**Remove-CsClsScenario** cmdlet은 지정된 시나리오를 제거하지만, 캡처된 추적은 로그에서 계속 검색할 수 있습니다.
### <a name="to-load-and-unload-the-edit-csclsscenario-cmdlet-using-the-clsscenarioeditpsm1-module"></a>ClsScenarioEdit.psm1 Edit-CsClsScenario cmdlet을 로드하고 언로드

1. 비즈니스용 Skype 서버 시작: **시작,** 모든 프로그램, 비즈니스용 Skype **2015를** 클릭한 다음 관리 **비즈니스용 Skype 서버 를 클릭합니다.**
    
    > [!IMPORTANT]
    > ClsScenarioEdit.psm1 모듈은 별도의 웹 다운로드로 제공됩니다. 이 모듈은 2015 비즈니스용 Skype 서버 도구의 일부입니다. 기본적으로 디버깅 도구는 C:\Program Files\비즈니스용 Skype 서버 2015\Debugging Tools 디렉터리에 설치됩니다. 
  
2. 다음 Windows PowerShell 입력합니다.
    
   ```PowerShell
   Import-Module "CDBurn\OCO\amd64\Support"
   ```

    > [!TIP]
    > 모듈을 로드하면 명령 프롬프트가 Windows PowerShell 반환됩니다. 모듈이 로드되어 있으며 사용 가능한 Edit-CsClsScenario 확인을 위해 를  `Get-Help Edit-CsClsScenario` 입력합니다. EditCsClsScenario 구문의 기본 동의어가 표시해야 합니다. 
  
3. 모듈을 언로드하기 위해 다음을 입력합니다.
    
   ```PowerShell
   Remove-Module ClsController
   ```

    > [!TIP]
    > 모듈을 성공적으로 언로드하면 명령 프롬프트가 Windows PowerShell 반환됩니다. 모듈이 언로드된 것이면 을  `Get-Help Edit-CsClsScenario` 입력합니다. Windows PowerShell cmdlet에 대한 도움말을 찾으며 실패합니다. 
  
### <a name="to-remove-an-existing-provider-from-a-scenario-with-the-edit-clscontroller-module"></a>모듈을 사용하여 시나리오에서 기존 공급자를 Edit-ClsController

1. 비즈니스용 Skype 서버 시작: **시작,** 모든 프로그램, 비즈니스용 Skype **2015를** 클릭한 다음 관리 **비즈니스용 Skype 서버 를 클릭합니다.**
    
2. 다음 Windows PowerShell 입력합니다.
    
   ```PowerShell
   Import-Module "CDBurn\OCO\amd64\Support"
   ```

    > [!TIP]
    > 모듈을 로드하면 명령 프롬프트가 Windows PowerShell 반환됩니다. 모듈이 로드되어 있으며 사용 가능한 Edit-CsClsScenario 확인을 위해 를  `Get-Help Edit-CsClsScenario` 입력합니다. EditCsClsScenario 구문의 기본 동의어가 표시해야 합니다. 
  
3. AlwaysOn 시나리오에서 공급자를 제거하려면 다음을 입력합니다.
    
   ```PowerShell
   Edit-CsClsScenario -ScenarioName <string of the scenario to edit> -ProviderName <string of the provider to remove> -Remove
   ```

   예를 들어:
    
   ```PowerShell
   Edit-CsClsScenario -ScenarioName AlwaysOn -ProviderName ChatServer -Remove
   ```

   ScenarioName 및 ProviderName 매개 변수는 명령줄의 예상 위치에 정의되어야 하는 위치입니다. 시나리오 이름이 위치 2에 있으며 공급자가 위치 3에 있는 경우 위치 1로 cmdlet의 이름을 상대로 매개 변수 이름을 명시적으로 정의할 필요가 없습니다. 이 정보를 사용하여 이전 명령은 다음을 입력합니다.
    
   ```PowerShell
   Edit-CsClsScenario AlwaysOn ChatServer -Remove
   ```

   매개 변수 값의 위치 배치는 -Scenario 및 -Provider에만 적용됩니다. 다른 모든 매개 변수는 명시적으로 정의되어야 합니다.
    
### <a name="to-add-a-provider-to-a-scenario-with-the-edit-clscontroller-module"></a>모듈을 사용하여 시나리오에 공급자를 Edit-ClsController

1. 비즈니스용 Skype 서버 시작: **시작,** 모든 프로그램, 비즈니스용 Skype **2015를** 클릭한 다음 관리 **비즈니스용 Skype 서버 를 클릭합니다.**
    
2. AlwaysOn 시나리오에 공급자를 추가하기 위해 다음을 입력합니다.
    
   ```PowerShell
   Edit-CsClsScenario -ScenarioName <string of the scenario to edit> -ProviderName <string of the provider to add> -Level <string of type level> -Flags <string of type flags>
   ```

    예를 들어:
    
   ```PowerShell
   Edit-CsClsScenario -ScenarioName AlwaysOn -ProviderName ChatServer -Level Info -Flags TF_COMPONENT
   ```

    -Loglevel은 Fatal, Error, Warning, Info, Verbose, Debug 또는 All 유형일 수 있습니다. -Flags는 공급자가 지원하는 플래그(예: TF_COMPONENT, TF_DIAG. -Flags는 ALL 값일 수도 있습니다.
    
   이전 예제는 cmdlet의 위치 기능을 사용하여 입력할 수도 있습니다. 예를 들어 AlwaysOn 시나리오에 공급자 ChatServer를 추가하기 위해 다음을 입력합니다.
    
   ```PowerShell
   Edit-CsClsScenario AlwaysOn ChatServer -Level Info -Flags ALL
   ```