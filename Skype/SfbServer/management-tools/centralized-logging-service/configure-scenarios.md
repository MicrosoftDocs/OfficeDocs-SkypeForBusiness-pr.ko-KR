---
title: 비즈니스용 Skype 2015에서 중앙 로깅 서비스에 대한 시나리오 구성
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 6c3bf826-e7fd-4002-95dc-01020641ef01
description: '요약: 비즈니스용 Skype 서버 2015에서 중앙 집중화 된 로깅 서비스에 대 한 시나리오를 만들고, 수정 하 고, 제거 하는 방법에 대해 알아봅니다.'
ms.openlocfilehash: 89aa0c37dfb13f7614067b64e37ee9c9fb376331
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36186819"
---
# <a name="configure-scenarios-for-the-centralized-logging-service-in-skype-for-business-server-2015"></a>비즈니스용 Skype 2015에서 중앙 로깅 서비스에 대한 시나리오 구성
 
**요약:** 비즈니스용 Skype 서버 2015에서 중앙 집중화 된 로깅 서비스에 대 한 시나리오를 만들고, 수정 하 고, 제거 하는 방법에 대해 알아봅니다.
  
시나리오는 범위 (즉, 전역, 사이트, 풀 또는 컴퓨터)와 중앙 로깅 서비스에서 사용할 공급자를 정의 합니다. 시나리오를 사용 하 여 공급자 (예: S4, SIPStack, IM, 현재 상태) 추적을 사용 하거나 사용 하지 않도록 설정 합니다. 시나리오를 구성 하 여 특정 문제 조건을 처리 하는 지정 된 논리 컬렉션에 대 한 모든 공급자를 그룹화 할 수 있습니다. 문제 해결 및 로깅 요구 사항에 맞게 시나리오를 수정 해야 하는 경우 비즈니스용 Skype 서버 2015 디버그 도구는 psm1-CsClsScenario 함수가 포함 된 ClsScenarioEdit 라는 Windows PowerShell 모듈을 제공 합니다. 모듈의 목적은 명명 된 시나리오의 속성을 편집 하는 것입니다. 이 모듈의 작동 방식에 대 한 예는이 항목에서 제공 합니다. Skype for Business Server 2015 [디버깅 도구](https://go.microsoft.com/fwlink/p/?LinkId=285257) 를 다운로드 한 후 더 자세히 진행 하세요.
  
> [!IMPORTANT]
> 지정 된 범위 (사이트, 전역, 풀 또는 컴퓨터)에 대해 지정 된 시간에 최대 두 개의 시나리오를 실행할 수 있습니다. 현재 실행 중인 시나리오를 확인 하려면 Windows PowerShell 및 [가져오기-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/get-csclsscenario?view=skype-ps)를 사용 합니다. Windows PowerShell 및 [Set-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/set-csclsscenario?view=skype-ps)를 사용 하 여 실행 중인 시나리오를 동적으로 변경할 수 있습니다. 기록 세션 중에 실행 되는 시나리오를 수정 하 여 수집 하 고 있는 데이터와 공급자를 조정 하거나 조정할 수 있습니다. 
  
비즈니스용 Skype Server Management Shell을 사용 하 여 중앙 로깅 서비스 기능을 실행 하려면 CsAdministrator 또는 CsServerAdministrator 역할 기반 액세스 제어 (RBAC) 보안 그룹 또는 사용자 지정 RBAC 역할의 구성원 이어야 합니다. 두 그룹 중 하나를 포함 합니다. 직접 만든 사용자 지정 RBAC 역할을 포함 하 여이 cmdlet에 할당 된 모든 RBAC 역할 목록을 반환 하려면 비즈니스용 Skype Server 관리 셸 또는 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.
  
```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Skype for Business Server 2015 cmdlet"}
```

예를 들면 다음과 같습니다.
  
```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

이 항목의 나머지 부분에서는 시나리오를 정의 하 고, 시나리오를 수정 하 고, 실행 중인 시나리오를 검색 하 고, 시나리오를 제거 하 고, 문제 해결을 최적화 하기 위해 시나리오가 포함할 항목을 지정 하는 방법에 대해 설명 합니다. 비즈니스용 Skype Server Management Shell을 사용 하 여 Windows PowerShell 명령을 실행할 수 있습니다. Windows PowerShell을 사용 하는 경우 로깅 세션에서 사용할 새 시나리오를 정의할 수 있습니다.
  
[비즈니스의 비즈니스용 Skype 2015 중앙 로깅 서비스](centralized-logging-service.md)에 도입 된 것 처럼 시나리오의 요소는 다음과 같습니다.
  
- **공급자** OCSLogger 사용 하는 데 익숙한 경우 공급자는 OCSLogger 로그를 수집 하는 대상에 게 지정 하도록 선택 하는 구성 요소입니다. 공급자는 동일한 구성 요소 이며, 대부분의 경우에는 OCSLogger 구성 요소와 동일한 이름을 사용 합니다. OCSLogger 익숙하지 않은 경우 공급자는 중앙 로깅 서비스가 로그를 수집할 수 있는 서버 역할 특정 구성 요소입니다. 공급자 구성에 대 한 자세한 내용은 비즈니스용 [Skype 서버 2015에서 중앙 집중화 된 로깅 서비스에 대 한 공급자 구성을](configure-providers.md)참조 하세요.
    
- **Id** 매개 변수 Id는 시나리오의 범위와 이름을 설정 합니다. 예를 들어 "전역" 범위를 설정 하 고 "LyssServiceScenario"를 사용 하 여 시나리오를 식별할 수 있습니다. 두 가지를 결합 하면 Id를 정의 합니다 (예: "global/LyssServiceScenario").
    
    선택적으로-Name 및-Parent 매개 변수를 사용할 수 있습니다. Name 매개 변수를 정의 하 여 시나리오를 고유 하 게 식별 합니다. 이름을 사용 하는 경우에는 Parent를 사용 하 여 전역 또는 사이트 중 하나에 시나리오를 추가 해야 합니다. 
    
    > [!IMPORTANT]
    > Name 및 Parent 매개 변수를 사용 하는 경우 **-Identity** 매개 변수를 사용할 수 없습니다.
  
### <a name="to-create-a-new-scenario-with-the-new-csclsscenario-cmdlet"></a>새-CsClsScenario cmdlet을 사용 하 여 새 시나리오를 만들려면

1. 비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **비즈니스용 skype 2015**을 차례로 클릭 한 다음 비즈니스용 **skype Server management Shell**을 클릭 합니다.
    
2. 로깅 세션에 대 한 새 시나리오를 만들려면 [새 CsClsProvider](https://docs.microsoft.com/powershell/module/skype/new-csclsprovider?view=skype-ps) 를 사용 하 고 시나리오 이름 (즉, 고유 하 게 식별 되는 방법)을 정의 합니다. WPP (즉, Windows 소프트웨어 추적 전처리기를 사용 하는 경우 기본값), EventLog (Windows 이벤트 로그 형식) 또는 IISLog (즉, IIS 로그 파일 형식을 기반으로 하는 ASCII 형식 파일)의 로깅 형식 유형을 선택 합니다. 다음으로,이 항목의 로깅 수준 아래에 정의 된 대로 수준을 정의 하 고이 항목의 Flags 아래에 정의 된 플래그를 지정 합니다.
    
    이 예제 시나리오에서는 예제 공급자 변수로 LyssProvider를 사용 합니다.
    
    정의 된 옵션을 사용 하 여 시나리오를 만들려면 다음을 입력 합니다.
    
   ```
   New-CsClsScenario -Identity <scope>/<unique scenario name> -Provider <provider variable>
   ```

    예를 들면 다음과 같습니다.
    
   ```
   New-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider $LyssProvider
   ```

    -Name 및-Parent를 사용 하는 대체 형식은 다음과 같습니다.
    
   ```
   New-CsClsScenario -Name "LyssServiceScenario" -Parent "site:Redmond" -Provider $LyssProvider
   ```

### <a name="to-create-a-new-scenario-with-multiple-providers-with-the-new-csclsscenario-cmdlet"></a>새-CsClsScenario cmdlet을 사용 하는 여러 공급자를 사용 하 여 새 시나리오를 만들려면

1. 비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **비즈니스용 skype 2015**을 차례로 클릭 한 다음 비즈니스용 **skype Server management Shell**을 클릭 합니다.
    
2. 범위 당 두 개의 시나리오로 제한 됩니다. 그러나 설정 된 공급자 수로 제한 되지 않습니다. 이 예제에서는 세 개의 공급자를 만들었고이 세 가지를 정의 하는 시나리오에 모두 할당 하려고 한다고 가정 합니다. 공급자 변수 이름은 LyssProvider, ABServerProvider, SIPStackProvider입니다. 시나리오에 여러 공급자를 정의 하 고 할당 하려면 비즈니스용 Skype 서버 관리 셸 또는 Windows PowerShell 명령 프롬프트에서 다음을 입력 합니다.
    
   ```
   New-CsClsScenario -Identity "site:Redmond/CollectDataScenario" -Provider @{Add=$LyssProvider, $ABServerProvider,  $SIPStackProvider}
   ```

    > [!NOTE]
    > Windows PowerShell에서 알 수 있듯이, 사용 하 `@{<variable>=<value1>, <value2>, <value>…}` 는 해시 테이블 값을 만드는 규칙은 알려진 assplatting입니다. Windows PowerShell의 splatting에 대 한 자세한 내용은 [https://go.microsoft.com/fwlink/p/?LinkId=267760](https://go.microsoft.com/fwlink/p/?LinkId=267760)을 참조 하세요. 
  
### <a name="to-modify-an-existing-scenario-with-the-set-csclsscenario-cmdlet"></a>Set-CsClsScenario cmdlet을 사용 하 여 기존 시나리오를 수정 하려면

1. 비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **비즈니스용 skype 2015**을 차례로 클릭 한 다음 비즈니스용 **skype Server management Shell**을 클릭 합니다.
    
2. 범위 당 두 개의 시나리오로 제한 됩니다. 로깅 캡처 세션이 진행 중인 경우에도 언제 든 지 실행 되는 시나리오를 변경할 수 있습니다. 실행 중인 시나리오를 재정의 하는 경우 현재 로깅 세션은 제거 된 시나리오 사용을 중지 하 고 새 시나리오 사용을 시작 합니다. 그러나 제거 된 시나리오를 사용 하 여 캡처한 로깅 정보는 캡처한 로그에 남아 있습니다. 새 시나리오를 정의 하려면 다음을 수행 합니다 (즉, "S4Provider" 이라는 이미 정의 된 공급자가 추가 된 경우).
    
   ```
   Set-CsClsScenario -Identity <name of scope and scenario defined by New-CsClsScenario> -Provider @{Add=<new provider to add>}
   ```

    예를 들면 다음과 같습니다.
    
   ```
   Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Add=$S4Provider}
   ```

    공급자를 바꾸려면 단일 공급자나 쉼표로 구분 된 공급자 목록을 정의 하 여 현재 집합을 바꿉니다. 여러 공급자 중 하나만 바꾸려면 새 공급자와 현재 공급자를 추가 하 여 새 공급자 및 기존 공급자를 모두 포함 하는 새 공급자 집합을 만듭니다. 모든 공급자를 새 집합으로 바꾸려면 다음을 입력 합니다.
    
   ```
   Set-CsClsScenario -Identity <name of scope and scenario defined by New-CsClsScenario> -Provider @{Replace=<providers to replace existing provider set>}
   ```

    예를 들어 현재 $LyssProvider 집합, $ABServerProvider 및 $SIPStackProvider을 $LyssServiceProvider로 바꾸려면 다음을 실행 합니다.
    
   ```
   Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Replace=$LyssServiceProvider}
   ```

    현재 $LyssProvider 집합에서 $LyssProvider 공급자로, $ABServerProvider, $LyssServiceProvider으로 $SIPStackProvider를 바꾸려면 다음을 입력 합니다.
    
   ```
   Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Replace=$LyssServiceProvider, $ABServerProvider, $SIPStackProvider}
   ```

### <a name="to-remove-an-existing-scenario-with-the-remove-csclsscenario-cmdlet"></a>제거-CsClsScenario cmdlet을 사용 하 여 기존 시나리오를 제거 하려면

1. 비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **비즈니스용 skype 2015**을 차례로 클릭 한 다음 비즈니스용 **skype Server management Shell**을 클릭 합니다.
    
2. 이전에 정의한 시나리오를 제거 하려면 다음을 입력 합니다.
    
   ```
   Remove-CsClsScenario -Identity <name of scope and scenario>
   ```

    예를 들어 정의 된 시나리오 사이트를 제거 하려면: Redmond/LyssServiceScenario:
    
   ```
   Remove-CsClsScenario -Identity "site:Redmond/LyssServiceScenario"
   ```

지정 된 시나리오는 **제거-CsClsScenario** cmdlet을 통해 제거 되지만, 캡처한 추적은 검색에 사용할 수 있도록 로그에 남아 있습니다.
### <a name="to-load-and-unload-the-edit-csclsscenario-cmdlet-using-the-clsscenarioeditpsm1-module"></a>Psm1 모듈을 사용 하 여 편집-CsClsScenario cmdlet을 로드 하 고 언로드하려면 ClsScenarioEdit

1. 비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **비즈니스용 skype 2015**을 차례로 클릭 한 다음 비즈니스용 **skype Server management Shell**을 클릭 합니다.
    
    > [!IMPORTANT]
    > ClsScenarioEdit psm1 모듈은 별도의 웹 다운로드로 제공 됩니다. 모듈은 비즈니스용 Skype 서버 2015 디버깅 도구의 일부입니다. 기본적으로 디버깅 도구는 Business Server 2015 용 C:\Program Files\Skype 디렉터리 디버깅 도구에 설치 됩니다. 
  
2. Windows PowerShell에서 다음을 입력 합니다.
    
   ```
   Import-Module "CDBurn\OCO\amd64\Support"
   ```

    > [!TIP]
    > 모듈을 성공적으로 로드 하면 Windows PowerShell 명령 프롬프트로 돌아갑니다. 모듈이 로드 되 고 편집-CsClsScenario을 사용할 수 있는지 확인 하려면 다음을 입력 `Get-Help Edit-CsClsScenario`합니다. EditCsClsScenario에 대 한 구문의 기본 synopsis를 확인 해야 합니다. 
  
3. 모듈을 언로드하려면 다음을 입력 합니다.
    
   ```
   Remove-Module ClsController
   ```

    > [!TIP]
    > 모듈을 성공적으로 언로드하면 Windows PowerShell 명령 프롬프트로 돌아갑니다. 모듈이 언로드되는 지 확인 하려면를 입력 `Get-Help Edit-CsClsScenario`합니다. Windows PowerShell에서 cmdlet에 대 한 도움말을 찾으려고 시도 하 고 실패 합니다. 
  
### <a name="to-remove-an-existing-provider-from-a-scenario-with-the-edit-clscontroller-module"></a>ClsController 모듈을 사용 하 여 시나리오에서 기존 공급자를 제거 하려면

1. 비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **비즈니스용 skype 2015**을 차례로 클릭 한 다음 비즈니스용 **skype Server management Shell**을 클릭 합니다.
    
2. Windows PowerShell에서 다음을 입력 합니다.
    
   ```
   Import-Module "CDBurn\OCO\amd64\Support"
   ```

    > [!TIP]
    > 모듈을 성공적으로 로드 하면 Windows PowerShell 명령 프롬프트로 돌아갑니다. 모듈이 로드 되 고 편집-CsClsScenario을 사용할 수 있는지 확인 하려면 다음을 입력 `Get-Help Edit-CsClsScenario`합니다. EditCsClsScenario에 대 한 구문의 기본 synopsis를 확인 해야 합니다. 
  
3. AlwaysOn 시나리오에서 공급자를 제거 하려면 다음을 입력 합니다.
    
   ```
   Edit-CsClsScenario -ScenarioName <string of the scenario to edit> -ProviderName <string of the provider to remove> -Remove
   ```

   예를 들어:
    
   ```
   Edit-CsClsScenario -ScenarioName AlwaysOn -ProviderName ChatServer -Remove
   ```

   ScenarioName 및 ProviderName 매개 변수는 위치 (즉, 명령줄의 예상 위치에서 정의 되어야 함) 매개 변수입니다. 시나리오 이름이 두 위치에 있고 공급자가 cmdlet의 이름을 위치 1로 기준으로 하는 3 위치에 있는 경우 매개 변수 이름을 명시적으로 정의할 필요가 없습니다. 이 정보를 사용 하 여 이전 명령은 다음과 같이 입력 합니다.
    
   ```
   Edit-CsClsScenario AlwaysOn ChatServer -Remove
   ```

   매개 변수 값을 배치 하는 위치는 Scenario 및-Provider에만 적용 됩니다. 다른 모든 매개 변수는 명시적으로 정의 되어야 합니다.
    
### <a name="to-add-a-provider-to-a-scenario-with-the-edit-clscontroller-module"></a>ClsController 모듈을 사용 하 여 시나리오에 공급자를 추가 하려면

1. 비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **비즈니스용 skype 2015**을 차례로 클릭 한 다음 비즈니스용 **skype Server management Shell**을 클릭 합니다.
    
2. AlwaysOn 시나리오에 공급자를 추가 하려면 다음을 입력 합니다.
    
   ```
   Edit-CsClsScenario -ScenarioName <string of the scenario to edit> -ProviderName <string of the provider to add> -Level <string of type level> -Flags <string of type flags>
   ```

    예를 들어:
    
   ```
   Edit-CsClsScenario -ScenarioName AlwaysOn -ProviderName ChatServer -Level Info -Flags TF_COMPONENT
   ```

    -Loglevel은 치명적, 오류, 경고, 정보, 자세한 정보 표시, 디버그 또는 모두 유형이 될 수 있습니다. -Flags는 공급자가 지 원하는 모든 플래그 (예: TF_COMPONENT, TF_DIAG) 일 수 있습니다. -Flags는 모두 값 일 수 있습니다.
    
   앞의 예제는 cmdlet의 위치 기능을 사용 하 여 입력할 수도 있습니다. 예를 들어, AlwaysOn 시나리오에 공급자 이름 서버를 추가 하려면 다음을 입력 합니다.
    
   ```
   Edit-CsClsScenario AlwaysOn ChatServer -Level Info -Flags ALL
   ```
