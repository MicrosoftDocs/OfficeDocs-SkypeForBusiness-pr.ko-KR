---
title: 2015년 비즈니스용 Skype 서버 중앙 집중식 로깅 서비스에 대한 시나리오 구성
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
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
description: '요약: 비즈니스용 Skype 서버 2015에서 중앙 집중식 로깅 서비스에 대한 시나리오를 만들고, 수정하고, 제거하는 방법을 알아봅니다.'
ms.openlocfilehash: ecd96dc849030cb035f965c8cb52eb7607bd9667
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/25/2022
ms.locfileid: "65676360"
---
# <a name="configure-scenarios-for-the-centralized-logging-service-in-skype-for-business-server-2015"></a>2015년 비즈니스용 Skype 서버 중앙 집중식 로깅 서비스에 대한 시나리오 구성

**요약:** 비즈니스용 Skype 서버 2015에서 중앙 집중식 로깅 서비스에 대한 시나리오를 만들고 수정하고 제거하는 방법을 알아봅니다.

시나리오는 범위(즉, 전역, 사이트, 풀 또는 컴퓨터)와 중앙 집중식 로깅 서비스에서 사용할 공급자를 정의합니다. 시나리오를 사용하면 공급자(예: S4, SIPStack, IM 및 현재 상태)에서 추적을 사용하거나 사용하지 않도록 설정합니다. 시나리오를 구성하면 특정 문제 조건을 해결하는 지정된 논리 컬렉션에 대한 모든 공급자를 그룹화할 수 있습니다. 문제 해결 및 로깅 요구 사항에 맞게 시나리오를 수정해야 하는 경우 비즈니스용 Skype 서버 2015 디버그 도구는 ClsScenarioEdit.psm1이라는 Windows PowerShell 모듈을 제공합니다. 여기에는Edit-CsClsScenario라는 함수가 포함되어 있습니다. 모듈의 목적은 명명된 시나리오의 속성을 편집하는 것입니다. 이 모듈의 작동 방식에 대한 예제는 이 항목에 나와 있습니다. 더 나아가기 전에 비즈니스용 Skype 서버 2015 [디버깅 도구를 다운로드합니다](https://go.microsoft.com/fwlink/p/?LinkId=285257).

> [!IMPORTANT]
> 지정된 범위(사이트, 전역, 풀 또는 컴퓨터)의 경우 지정된 시간에 최대 두 개의 시나리오를 실행할 수 있습니다. 현재 실행 중인 시나리오를 확인하려면 Windows PowerShell 및 [Get-CsClsScenario를](/powershell/module/skype/get-csclsscenario) 사용합니다. Windows PowerShell 및 [Set-CsClsScenario를](/powershell/module/skype/set-csclsscenario) 사용하여 실행 중인 시나리오를 동적으로 변경할 수 있습니다. 로깅 세션 중에 실행 중인 시나리오를 수정하여 수집 중인 데이터와 공급자를 조정하거나 구체화할 수 있습니다.

비즈니스용 Skype 서버 관리 셸을 사용하여 중앙 집중식 로깅 서비스 함수를 실행하려면 CsAdministrator 또는 CsServerAdministrator RBAC(역할 기반 액세스 제어) 보안 그룹 또는 이러한 두 그룹 중 하나를 포함하는 사용자 지정 RBAC 역할의 멤버여야 합니다. 직접 만든 사용자 지정 RBAC 역할을 포함하여 이 cmdlet이 할당한 모든 RBAC 역할 목록을 반환하려면 비즈니스용 Skype 서버 관리 셸 또는 Windows PowerShell 프롬프트에서 다음 명령을 실행합니다.

```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Skype for Business Server 2015 cmdlet"}
```

예:

```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

이 항목의 나머지 부분에서는 시나리오를 정의하고, 시나리오를 수정하고, 실행 중인 시나리오를 검색하고, 시나리오를 제거하고, 문제 해결을 최적화하기 위해 포함된 시나리오를 지정하는 방법에 중점을 둡니다. 비즈니스용 Skype 서버 관리 셸을 사용하여 Windows PowerShell 명령을 실행할 수 있습니다. Windows PowerShell 사용하는 경우 로깅 세션에서 사용할 새 시나리오를 정의할 수 있습니다.

[2015년 비즈니스용 Skype 중앙 집중식 로깅 서비스에](centralized-logging-service.md) 도입된 시나리오의 요소는 다음과 같습니다.

- **공급자** OCSLogger에 익숙한 경우 공급자는 추적 엔진이 로그를 수집해야 하는 항목을 OCSLogger에 알리도록 선택하는 구성 요소입니다. 공급자는 동일한 구성 요소이며 대부분의 경우 OCSLogger의 구성 요소와 동일한 이름을 갖습니다. OCSLogger에 익숙하지 않은 경우 공급자는 중앙 로깅 서비스에서 로그를 수집할 수 있는 서버 역할 관련 구성 요소입니다. 공급자 구성에 대한 자세한 내용은 [비즈니스용 Skype 서버 2015의 중앙 집중식 로깅 서비스에 대한 공급자 구성](configure-providers.md)을 참조하세요.

- **Id** 매개 변수 -Identity는 시나리오의 범위와 이름을 설정합니다. 예를 들어 "global" 범위를 설정하고 "LyssServiceScenario"를 사용하여 시나리오를 식별할 수 있습니다. 둘을 결합하면 ID(예: "global/LyssServiceScenario")를 정의합니다.

    필요에 따라 -Name 및 -Parent 매개 변수를 사용할 수 있습니다. 시나리오를 고유하게 식별하는 Name 매개 변수를 정의합니다. Name을 사용하는 경우 부모도 사용하여 시나리오를 전역 또는 사이트에 추가해야 합니다.

    > [!IMPORTANT]
    > Name 및 Parent 매개 변수를 사용하는 경우 **-Identity** 매개 변수를 사용할 수 없습니다.

## <a name="to-create-a-new-scenario-with-the-new-csclsscenario-cmdlet"></a>New-CsClsScenario cmdlet을 사용하여 새 시나리오를 만들려면

1. 비즈니스용 Skype 서버 관리 셸 **을 시작** 합니다. 시작을 클릭하고 **모든 프로그램을** 클릭한 **다음 비즈니스용 Skype 2015** 를 클릭한 다음 **비즈니스용 Skype 서버 관리 셸** 을 클릭합니다.

2. 로깅 세션에 대한 새 시나리오를 만들려면 [New-CsClsProvider](/powershell/module/skype/new-csclsprovider) 를 사용하고 시나리오의 이름(즉, 고유하게 식별되는 방법)을 정의합니다. WPP(즉, 소프트웨어 추적 전처리기 및 기본값인 Windows), EventLog(즉, Windows 이벤트 로그 형식) 또는 IISLog(IIS 로그 파일 형식 기반 ASCII 형식 파일)에서 로깅 형식 유형을 선택합니다. 다음으로 수준(이 항목의 로깅 수준에 정의된 대로) 및 플래그(이 항목의 플래그 아래에 정의됨)를 정의합니다.

    이 예제 시나리오에서는 예제 공급자 변수로 LyssProvider를 사용합니다.

    정의된 옵션을 사용하여 시나리오를 만들려면 다음을 입력합니다.

   ```PowerShell
   New-CsClsScenario -Identity <scope>/<unique scenario name> -Provider <provider variable>
   ```

    예:

   ```PowerShell
   New-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider $LyssProvider
   ```

    -Name 및 -Parent를 사용하는 대체 형식:

   ```PowerShell
   New-CsClsScenario -Name "LyssServiceScenario" -Parent "site:Redmond" -Provider $LyssProvider
   ```

## <a name="to-create-a-new-scenario-with-multiple-providers-with-the-new-csclsscenario-cmdlet"></a>New-CsClsScenario cmdlet을 사용하여 여러 공급자를 사용하여 새 시나리오를 만들려면

1. 비즈니스용 Skype 서버 관리 셸 **을 시작** 합니다. 시작을 클릭하고 **모든 프로그램을** 클릭한 **다음 비즈니스용 Skype 2015** 를 클릭한 다음 **비즈니스용 Skype 서버 관리 셸** 을 클릭합니다.

2. 범위당 두 가지 시나리오로 제한됩니다. 그러나 설정된 공급자 수로 제한되지는 않습니다. 이 예제에서는 세 개의 공급자를 만들었으며 정의 중인 시나리오에 세 가지 모두를 할당한다고 가정합니다. 공급자 변수 이름은 LyssProvider, ABServerProvider 및 SIPStackProvider입니다. 시나리오에 여러 공급자를 정의하고 할당하려면 비즈니스용 Skype 서버 Management Shell 또는 Windows PowerShell 명령 프롬프트에 다음을 입력합니다.

   ```PowerShell
   New-CsClsScenario -Identity "site:Redmond/CollectDataScenario" -Provider @{Add=$LyssProvider, $ABServerProvider,  $SIPStackProvider}
   ```

    > [!NOTE]
    > Windows PowerShell 알려진 바와 같이, 사용 하 여 `@{<variable>=<value1>, <value2>, <value>...}` 값의 해시 테이블을 만들기 위한 규칙을 assplatting 라고 합니다. Windows PowerShell 스플래팅에 대한 자세한 내용은 을 참조하세요[https://go.microsoft.com/fwlink/p/?LinkId=267760](/previous-versions/technet-magazine/gg675931(v=msdn.10)).

## <a name="to-modify-an-existing-scenario-with-the-set-csclsscenario-cmdlet"></a>Set-CsClsScenario cmdlet을 사용하여 기존 시나리오를 수정하려면

1. 비즈니스용 Skype 서버 관리 셸 **을 시작** 합니다. 시작을 클릭하고 **모든 프로그램을** 클릭한 **다음 비즈니스용 Skype 2015** 를 클릭한 다음 **비즈니스용 Skype 서버 관리 셸** 을 클릭합니다.

2. 범위당 두 가지 시나리오로 제한됩니다. 로깅 캡처 세션이 처리 중인 경우에도 언제든지 실행 중인 시나리오를 변경할 수 있습니다. 실행 중인 시나리오를 다시 정의하면 현재 로깅 세션이 제거된 시나리오 사용을 중지한 다음 새 시나리오 사용을 시작합니다. 그러나 제거된 시나리오로 캡처된 로깅 정보는 캡처된 로그에 남아 있습니다. 새 시나리오를 정의하려면 다음을 수행합니다(즉, "S4Provider"라는 이미 정의된 공급자를 추가한다고 가정).

   ```PowerShell
   Set-CsClsScenario -Identity <name of scope and scenario defined by New-CsClsScenario> -Provider @{Add=<new provider to add>}
   ```

    예:

   ```PowerShell
   Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Add=$S4Provider}
   ```

    공급자를 바꾸려면 단일 공급자 또는 쉼표로 구분된 공급자 목록을 정의하여 현재 집합을 바꿉니다. 많은 공급자 중 하나만 바꾸려면 현재 공급자를 새 공급자로 추가하여 새 공급자와 기존 공급자를 모두 포함하는 새 공급자 집합을 만듭니다. 모든 공급자를 새 집합으로 바꾸려면 다음을 입력합니다.

   ```PowerShell
   Set-CsClsScenario -Identity <name of scope and scenario defined by New-CsClsScenario> -Provider @{Replace=<providers to replace existing provider set>}
   ```

    예를 들어 현재 $LyssProvider, $ABServerProvider 및 $SIPStackProvider 집합을 $LyssServiceProvider 대체하려면 다음을 수행합니다.

   ```PowerShell
   Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Replace=$LyssServiceProvider}
   ```

    현재 $LyssProvider, $ABServerProvider 및 $SIPStackProvider $LyssProvider 공급자만 $LyssServiceProvider 바꾸려면 다음을 입력합니다.

   ```PowerShell
   Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Replace=$LyssServiceProvider, $ABServerProvider, $SIPStackProvider}
   ```

## <a name="to-remove-an-existing-scenario-with-the-remove-csclsscenario-cmdlet"></a>Remove-CsClsScenario cmdlet을 사용하여 기존 시나리오를 제거하려면

1. 비즈니스용 Skype 서버 관리 셸 **을 시작** 합니다. 시작을 클릭하고 **모든 프로그램을** 클릭한 **다음 비즈니스용 Skype 2015** 를 클릭한 다음 **비즈니스용 Skype 서버 관리 셸** 을 클릭합니다.

2. 이전에 정의된 시나리오를 제거하려면 다음을 입력합니다.

   ```PowerShell
   Remove-CsClsScenario -Identity <name of scope and scenario>
   ```

    예를 들어 정의된 시나리오 사이트:Redmond/LyssServiceScenario를 제거하려면 다음을 수행합니다.

   ```PowerShell
   Remove-CsClsScenario -Identity "site:Redmond/LyssServiceScenario"
   ```

**Remove-CsClsScenario** cmdlet은 지정된 시나리오를 제거하지만 캡처된 추적은 검색할 수 있도록 로그에서 계속 사용할 수 있습니다.

## <a name="to-load-and-unload-the-edit-csclsscenario-cmdlet-using-the-clsscenarioeditpsm1-module"></a>ClsScenarioEdit.psm1 모듈을 사용하여 Edit-CsClsScenario cmdlet을 로드하고 언로드하려면

1. 비즈니스용 Skype 서버 관리 셸 **을 시작** 합니다. 시작을 클릭하고 **모든 프로그램을** 클릭한 **다음 비즈니스용 Skype 2015** 를 클릭한 다음 **비즈니스용 Skype 서버 관리 셸** 을 클릭합니다.

    > [!IMPORTANT]
    > ClsScenarioEdit.psm1 모듈은 별도의 웹 다운로드로 제공됩니다. 이 모듈은 비즈니스용 Skype 서버 2015 디버깅 도구의 일부입니다. 기본적으로 디버깅 도구는 디렉터리 C:\Program Files\비즈니스용 Skype 서버 2015\Debugging Tools에 설치됩니다.

2. Windows PowerShell 다음을 입력합니다.

   ```PowerShell
   Import-Module "CDBurn\OCO\amd64\Support"
   ```

    > [!TIP]
    > 모듈을 성공적으로 로드하면 Windows PowerShell 명령 프롬프트로 돌아갑니다. 모듈이 로드되고 Edit-CsClsScenario 사용할 수 있는지 확인하려면 .를 입력합니다  `Get-Help Edit-CsClsScenario`. EditCsClsScenario에 대한 구문의 기본 개요가 표시됩니다.

3. 모듈을 언로드하려면 다음을 입력합니다.

   ```PowerShell
   Remove-Module ClsController
   ```

    > [!TIP]
    > 모듈을 성공적으로 언로드하면 Windows PowerShell 명령 프롬프트로 돌아갑니다. 모듈이 언로드되어 있는지 확인하려면 .를 입력합니다  `Get-Help Edit-CsClsScenario`. Windows PowerShell cmdlet에 대한 도움말을 찾으려고 시도하고 실패합니다.

## <a name="to-remove-an-existing-provider-from-a-scenario-with-the-edit-clscontroller-module"></a>Edit-ClsController 모듈을 사용하여 시나리오에서 기존 공급자를 제거하려면

1. 비즈니스용 Skype 서버 관리 셸 **을 시작** 합니다. 시작을 클릭하고 **모든 프로그램을** 클릭한 **다음 비즈니스용 Skype 2015** 를 클릭한 다음 **비즈니스용 Skype 서버 관리 셸** 을 클릭합니다.

2. Windows PowerShell 다음을 입력합니다.

   ```PowerShell
   Import-Module "CDBurn\OCO\amd64\Support"
   ```

    > [!TIP]
    > 모듈을 성공적으로 로드하면 Windows PowerShell 명령 프롬프트로 돌아갑니다. 모듈이 로드되고 Edit-CsClsScenario 사용할 수 있는지 확인하려면 .를 입력합니다  `Get-Help Edit-CsClsScenario`. EditCsClsScenario에 대한 구문의 기본 개요가 표시됩니다.

3. AlwaysOn 시나리오에서 공급자를 제거하려면 다음을 입력합니다.

   ```PowerShell
   Edit-CsClsScenario -ScenarioName <string of the scenario to edit> -ProviderName <string of the provider to remove> -Remove
   ```

   예를 들어:

   ```PowerShell
   Edit-CsClsScenario -ScenarioName AlwaysOn -ProviderName ChatServer -Remove
   ```

   ScenarioName 및 ProviderName 매개 변수는 위치(즉, 명령줄의 예상 위치에 정의되어야 합니다) 매개 변수입니다. 시나리오 이름이 2 위치에 있고 공급자가 위치 1인 cmdlet의 이름을 기준으로 3 위치에 있는 경우 매개 변수 이름을 명시적으로 정의할 필요가 없습니다. 이 정보를 사용하여 이전 명령은 다음과 같이 입력됩니다.

   ```PowerShell
   Edit-CsClsScenario AlwaysOn ChatServer -Remove
   ```

   매개 변수 값의 위치 배치는 -Scenario 및 -Provider에만 적용됩니다. 다른 모든 매개 변수는 명시적으로 정의해야 합니다.

## <a name="to-add-a-provider-to-a-scenario-with-the-edit-clscontroller-module"></a>Edit-ClsController 모듈을 사용하여 시나리오에 공급자를 추가하려면

1. 비즈니스용 Skype 서버 관리 셸 **을 시작** 합니다. 시작을 클릭하고 **모든 프로그램을** 클릭한 **다음 비즈니스용 Skype 2015** 를 클릭한 다음 **비즈니스용 Skype 서버 관리 셸** 을 클릭합니다.

2. AlwaysOn 시나리오에 공급자를 추가하려면 다음을 입력합니다.

   ```PowerShell
   Edit-CsClsScenario -ScenarioName <string of the scenario to edit> -ProviderName <string of the provider to add> -Level <string of type level> -Flags <string of type flags>
   ```

    예를 들어:

   ```PowerShell
   Edit-CsClsScenario -ScenarioName AlwaysOn -ProviderName ChatServer -Level Info -Flags TF_COMPONENT
   ```

    -Loglevel은 치명적, 오류, 경고, 정보, 자세한 정보, 디버그 또는 모두 형식일 수 있습니다. -Flags는 공급자가 지원하는 플래그(예: TF_COMPONENT, TF_DIAG)일 수 있습니다. -플래그는 값이 ALL일 수도 있습니다.

   이전 예제는 cmdlet의 위치 기능을 사용하여 입력할 수도 있습니다. 예를 들어 공급자 ChatServer를 AlwaysOn 시나리오에 추가하려면 다음을 입력합니다.

   ```PowerShell
   Edit-CsClsScenario AlwaysOn ChatServer -Level Info -Flags ALL
   ```
