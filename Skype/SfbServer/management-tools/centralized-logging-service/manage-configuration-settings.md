---
title: 2015년 8월의 중앙 로깅 서비스 구성 비즈니스용 Skype 서버 관리
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 8/17/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 93b9a354-9aea-4b3a-a4fe-68a89f436196
description: '요약: 2015년 8월에 중앙 로깅 서비스의 구성 설정을 검색, 업데이트 및 만드는 방법을 비즈니스용 Skype 서버 있습니다.'
ms.openlocfilehash: 8b2809fd9b91859d0e32e9dfaf0ddb8cbebe7a53
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58628600"
---
# <a name="manage-centralized-logging-service-configuration-settings-in-skype-for-business-server-2015"></a>2015년 8월의 중앙 로깅 서비스 구성 비즈니스용 Skype 서버 관리

**요약:** 2015년 8월에 중앙 로깅 서비스에 대한 구성 설정을 검색, 업데이트 및 만드는 방법을 비즈니스용 Skype 서버 합니다.

중앙 로깅 서비스는 CLSController(중앙 로깅 서비스 컨트롤러)에서 만들어 개별 컴퓨터의 CLSAgent(중앙 로깅 서비스 에이전트)에 명령을 보내는 데 사용되는 설정 및 매개 변수에 의해 제어 및 구성됩니다. 에이전트는 전송된 명령을 처리하고(시작 명령의 경우) 시나리오, 공급자, 추적 기간 및 플래그의 구성을 사용하여 제공된 구성 정보에 따라 추적 로그 수집을 시작합니다.

> [!IMPORTANT]
>  중앙 로깅 Windows PowerShell 나열된 모든 cmdlet이 비즈니스용 Skype 서버 2015의 배포에서 사용하기 위한 것은 아닙니다. 이러한 cmdlet은 작동되는 것으로 보겠지만 다음 cmdlet은 2015년 비즈니스용 Skype 서버 배포에서 작동하도록 설계되지 않습니다.

-  **CsClsRegion cmdlet:** [Get-CsClsRegion,](/powershell/module/skype/get-csclsregion?view=skype-ps) [Set-CsClsRegion,](/powershell/module/skype/set-csclsregion?view=skype-ps) [New-CsClsRegion](/powershell/module/skype/new-csclsregion?view=skype-ps)및 [Remove-CsClsRegion](/powershell/module/skype/remove-csclsregion?view=skype-ps).
-  **CsClsSearchTerm cmdlet:** [Get-CsClsSearchTerm](/powershell/module/skype/get-csclssearchterm?view=skype-ps) 및 [Set-CsClsSearchTerm](/powershell/module/skype/set-csclssearchterm?view=skype-ps).
-  **CsClsSecurityGroup cmdlet:** [Get-CsClsSecurityGroup,](/powershell/module/skype/get-csclssecuritygroup?view=skype-ps) [Set-CsClsSecurityGroup,](/powershell/module/skype/set-csclssecuritygroup?view=skype-ps)  [New-CsClsSecurityGroup](/powershell/module/skype/new-csclssecuritygroup?view=skype-ps)및 [Remove-CsClsSecurityGroup](/powershell/module/skype/remove-csclssecuritygroup?view=skype-ps).

이러한 cmdlet에 정의된 설정은 방해가되거나 부정적인 동작을 유발하지 않지만 Microsoft 365 또는 Office 365 사용할 수 있도록 설계되어 있으며, 사내 배포에서 예상되는 결과를 얻지 못합니다. 이 말이 온-프레미스 배포에서 이러한 cmdlet을 사용할 수 없음을 의미하는 것은 아니지만 이 설명서에서는 이러한 cmdlet의 용도에 대해 설명하지 않겠습니다.

중앙 로깅 서비스는 단일 컴퓨터 또는 컴퓨터 풀을 포함하는 범위, 사이트 범위(즉, 배포의 컴퓨터 및 풀 컬렉션을 포함하는 Redmond 사이트와 같은 정의된 사이트) 또는 전역 범위(즉, 배포의 모든 컴퓨터 및 풀)에서 실행할 수 있습니다.

비즈니스용 Skype 서버 관리 셸을 사용하여 중앙 로깅 서비스 범위를 구성하려면 CsAdministrator 또는 CsServerAdministrator RBAC(역할 기반 액세스 제어) 보안 그룹 또는 이러한 두 그룹 중 하나를 포함하는 사용자 지정 RBAC 역할의 구성원이 되어야 합니다. 직접 만든 사용자 지정 RBAC 역할을 포함하여 이 cmdlet이 할당된 모든 RBAC 역할의 목록을 반환하기 위해 비즈니스용 Skype 서버 관리 셸 또는 Windows PowerShell 프롬프트에서 다음 명령을 실행합니다.

```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "<Skype for Business cmdlet>"}
```

예를 들어 다음과 같은 가치를 제공해야 합니다.

```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

> [!NOTE]
> 명령줄 명령은 명령줄 명령과 CLSController에서 실행할 수 Windows PowerShell 있습니다. Windows PowerShell 시나리오를 구성 및 정의하고 해당 시나리오를 문제 해결 시나리오에 의미 있는 방식으로 다시 사용할 수 있는 풍부한 방법을 제공합니다. CLSController를 사용하면 빠르고 효율적으로 명령을 실행하고 결과를 얻을 수 있지만 CLSController의 명령 집합은 명령줄에서 사용할 수 있는 소수의 명령으로 한정됩니다. Windows PowerShell cmdlet과 달리 CLSController는 새 시나리오를 정의하고, 사이트 또는 전역 수준에서 범위를 관리하고, 동적으로 구성할 수 없는 유한 명령 집합의 많은 제한 사항을 정의할 수 없습니다. CLSController는 빠른 실행을 위한 수단을 Windows PowerShell CLSController를 통해 가능한 범위를 넘어 중앙 로깅 서비스 기능을 확장하는 수단을 제공합니다.

-Computers 매개 변수를 사용하여 [Search-CsClsLogging,](/powershell/module/skype/search-csclslogging?view=skype-ps) [Show-CsClsLogging,](/powershell/module/skype/show-csclslogging?view=skype-ps) [Start-CsClsLogging,](/powershell/module/skype/start-csclslogging?view=skype-ps) [Stop-CsClsLogging,](/powershell/module/skype/stop-csclslogging?view=skype-ps) [Sync-CsClsLogging](/powershell/module/skype/sync-csclslogging?view=skype-ps) 및 [Update-CsClsLogging](/powershell/module/skype/update-csclslogging?view=skype-ps) 명령을 실행하는 동안 단일 컴퓨터 범위를 정의할 수 있습니다. -Computers 매개 변수는 대상 컴퓨터의 FQDNS(완전히 정식 도메인 이름)의 0으로 구분된 목록을 허용합니다.

> [!TIP]
> -Pools 및 로깅 명령을 실행할 풀의 콤보로 구분된 목록을 정의할 수도 있습니다.

사이트 및 전역 범위는 **New-**, **Set-** 및 **Remove- Centralized** Logging Service cmdlet에 정의됩니다. 다음 예에서는 사이트 범위와 전역 범위를 설정하는 방법을 보여 줍니다.

> [!IMPORTANT]
> 예로 든 명령들에는 다른 섹션에서 설명하는 매개 변수와 개념이 포함되어 있을 수 있습니다. 예제 명령은 **-Identity** 매개 변수를 사용하여 범위를 정의하는 방법을 보여 주며, 다른 매개 변수는 완전성을 위해 포함하며 범위를 지정합니다. **Set-CsClsConfiguration** cmdlet에 대한 자세한 내용은 작업 설명서에서 [Set-CsClsConfiguration](/powershell/module/skype/set-csclsconfiguration?view=skype-ps)을 참조하십시오.

### <a name="to-retrieve-the-current-centralized-logging-service-configuration"></a>현재 중앙 로깅 서비스 구성을 검색하려면

1. 비즈니스용 Skype 서버 시작: **시작,** 모든 프로그램, 비즈니스용 Skype **2015를** 클릭한 다음 관리 **비즈니스용 Skype 서버 를 클릭합니다.**

2. 명령줄 프롬프트에 다음 명령을 입력합니다.

   ```PowerShell
   Get-CsClsConfiguration
   ```

**New-CsClsConfiguration** 및 **Set-CsClsConfiguration** cmdlet을 사용하여 새 구성을 만들거나 기존 구성을 업데이트합니다. **Get-CsClsConfiguration을** 실행하면 배포에 현재 기본 전역 구성이 있지만 사이트 구성이 정의되지 않은 다음 스크린샷과 유사한 정보가 표시됩니다.

![Get-CsClsConfiguration의 샘플 출력입니다.](../../media/Ops_Get-CsClsConfiguration_Basic.jpg)

### <a name="to-retrieve-the-current-centralized-logging-service-configuration-from-the-computer-local-store"></a>컴퓨터 로컬 저장소에서 현재 중앙 로깅 서비스 구성을 검색하려면

1. 비즈니스용 Skype 서버 시작: **시작,** 모든 프로그램, 비즈니스용 Skype **2015를** 클릭한 다음 관리 **비즈니스용 Skype 서버 를 클릭합니다.**

2. 명령줄 프롬프트에 다음 명령을 입력합니다.

   ```PowerShell
   Get-CsClsConfiguration -LocalStore
   ```

**Get-CsClsConfiguration에서** 매개 변수를 지정하지 않는 첫 번째 예제를 사용하는 경우 명령은 데이터에 대한 중앙 관리 저장소를 참조합니다. -LocalStore 매개 변수를 지정하면 명령은 중앙 관리 저장소 대신 컴퓨터 LocalStore를 참조합니다.
### <a name="to-retrieve-a-listing-of-scenarios-currently-defined"></a>현재 정의된 시나리오 목록을 검색하려면

1. 비즈니스용 Skype 서버 시작: **시작,** 모든 프로그램, 비즈니스용 Skype **2015를** 클릭한 다음 관리 **비즈니스용 Skype 서버 를 클릭합니다.**

2. 명령줄 프롬프트에 다음 명령을 입력합니다.

   ```PowerShell
   Get-CsClsConfiguration -Identity <scope and name> | Select-Object -ExpandProperty Scenarios
   ```

    예를 들어 전역 범위로 정의된 시나리오를 검색하려면 다음과 같이 합니다.

   ```PowerShell
   Get-CsClsConfiguration -Identity "global" | Select-Object -ExpandProperty Scenarios
   ```

**Get-CsClsConfiguration** cmdlet은 항상 지정한 범위 구성의 일부인 시나리오를 표시합니다. 대부분의 경우 시나리오가 모두 표시되지 않고 잘려서 표시됩니다. 여기에 사용된 명령은 모든 시나리오와 사용된 공급자, 설정 및 플래그에 대한 일부 정보를 표시합니다.
### <a name="to-update-a-global-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a>중앙 로깅 서비스를 사용하여 전역 범위를 업데이트 Windows PowerShell

1. 비즈니스용 Skype 서버 시작: **시작,** 모든 프로그램, 비즈니스용 Skype **2015를** 클릭한 다음 관리 **비즈니스용 Skype 서버 를 클릭합니다.**

2. 명령줄 프롬프트에 다음 명령을 입력합니다.

   ```PowerShell
   Set-CsClsConfiguration -Identity <scope> -EtlFileRolloverSizeMB <size for logging file in megabytes>
   ```

   예를 들면 다음과 같습니다.

   ```PowerShell
   Set-CsClsConfiguration -Identity "global" -EtlFileRolloverSizeMB 40
   ```

이 명령을 실행하면 배포에 포함된 각 컴퓨터와 풀의 CLSAgent에서 추적 파일 롤오버 크기 값이 40메가바이트로 설정됩니다. 이 명령은 모든 사이트의 컴퓨터와 풀에 영향을 미쳐 각각의 구성된 추적 로그 롤오버 값이 40메가바이트로 설정됩니다.
### <a name="to-update-a-site-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a>중앙 로깅 서비스를 사용하여 사이트 범위를 업데이트 Windows PowerShell

1. 비즈니스용 Skype 서버 시작: **시작,** 모든 프로그램, 비즈니스용 Skype **2015를** 클릭한 다음 관리 **비즈니스용 Skype 서버 를 클릭합니다.**

2. 명령줄 프롬프트에 다음 명령을 입력합니다.

   ```PowerShell
   Set-CsClsConfiguration -Identity <scope/site name> -EtlFileRolloverSizeMB <size for logging file in megabytes>
   ```

   예를 들면 다음과 같습니다.

   ```PowerShell
   Set-CsClsConfiguration -Identity "site/Redmond" -EtlFileRolloverSizeMB 40
   ```

> [!NOTE]
> 이 예에 나와 있듯이 로그 파일의 기본 위치는 %TEMP%\Tracing입니다. 그러나 실제로 파일을 기록하는 것은 CLSAgent이고 CSLAgent는 네트워크 서비스로 실행되므로 %TEMP% 변수는 %WINDIR%\ServiceProfiles\NetworkService\AppData\Local로 확장됩니다.

이 명령을 실행하면 Redmond 사이트에 포함된 각 컴퓨터와 풀의 CLSAgent에서 추적 파일 롤오버 크기 값이 40메가바이트로 설정됩니다. 다른 사이트의 컴퓨터와 풀은 이 명령의 영향을 받지 않으며 기본적으로 정의되어 있거나(20메가바이트) 로깅 세션을 시작할 때 정의되어 현재 구성된 추적 로그 롤오버 값을 계속 사용합니다.
### <a name="to-create-a-new-centralized-logging-service-configuration"></a>새 중앙 로깅 서비스 구성을 만들하려면

1. 비즈니스용 Skype 서버 시작: **시작,** 모든 프로그램, 비즈니스용 Skype **2015를** 클릭한 다음 관리 **비즈니스용 Skype 서버 를 클릭합니다.**

2. 명령줄 프롬프트에 다음 명령을 입력합니다.

   ```PowerShell
   New-CsClsConfiguration -Identity <scope and name> [CsClsConfiguration options for this site]
   ```

    > [!NOTE]
    > New-CsClsConfiguration을 사용하면 다수의 선택적 구성 설정에 액세스할 수 있습니다. 구성 옵션에 대한 자세한 내용은 [Get-CsClsConfiguration](/powershell/module/skype/get-csclsconfiguration?view=skype-ps) 및 [Understanding Centralized Logging Service Configuration 설정.](/previous-versions/office/lync-server-2013/lync-server-2013-understanding-centralized-logging-service-configuration-settings)

예를 들어 캐시 파일의 네트워크 폴더, 로그 파일의 롤오버 기간 및 로그 파일의 롤오버 크기를 정의하는 새로운 구성을 만들려면 다음 명령을 입력합니다.

  ```PowerShell
  New-CsClsConfiguration -Identity "site:Redmond" -CacheFileNetworkFolder "\\fs01.contoso.net\filestore\logfiles" -EtlFileRolloverMinutes 120 -EtlFileRolloverSizeMB 40
  ```

새 구성 만들기 및 중앙 로깅 서비스의 새 속성을 정의하는 방법을 신중하게 계획해야 합니다. 구성을 변경할 때에는 주의를 기울여야 하며 변경 후에 문제 시나리오를 올바르게 로깅할 수 있을지 확인해야 합니다. 적절한 크기와 롤오버 기간으로 로그를 더욱 효과적으로 관리하여 문제 발생 시 문제를 손쉽게 해결할 수 있도록 구성을 변경해야 합니다.
### <a name="to-remove-an-existing-centralized-logging-service-configuration"></a>기존 중앙 로깅 서비스 구성을 제거하려면

1. 비즈니스용 Skype 서버 시작: **시작,** 모든 프로그램, 비즈니스용 Skype **2015를** 클릭한 다음 관리 **비즈니스용 Skype 서버 를 클릭합니다.**

2. 명령줄 프롬프트에 다음 명령을 입력합니다.

   ```PowerShell
   Remove-CsClsConfiguration -Identity <scope and name>
   ```

예를 들어 로그 파일 롤오버 시간을 늘리기 위해 만든 중앙 로깅 서비스 구성을 제거하려면 롤오버 로그 파일 크기를 늘리고 로그 파일 캐시 위치를 다음과 같이 네트워크 공유로 설정할 수 있습니다.

  ```PowerShell
  Remove-CsClsConfiguration -Identity "site:Redmond"
  ```

> [!NOTE]
> 이 구성은 "새 중앙 로깅 서비스 구성을 만들 수 있습니다." 절차에서 만든 새 구성입니다.

사이트 수준 구성을 제거하는 경우 사이트에 전역 설정이 사용됩니다.
## <a name="see-also"></a>참고 항목

[2015년 8월의 중앙 로깅 서비스에 대한 비즈니스용 Skype 서버 구성](configure-providers.md)

[2015년 8월의 중앙 로깅 서비스에 대한 비즈니스용 Skype 서버 구성](configure-scenarios.md)

[비즈니스용 Skype 2015의 중앙 로깅 서비스](centralized-logging-service.md)

[Set-CsClsConfiguration](/powershell/module/skype/set-csclsconfiguration?view=skype-ps)

[Get-CsClsConfiguration](/powershell/module/skype/get-csclsconfiguration?view=skype-ps)

[New-CsClsConfiguration](/powershell/module/skype/new-csclsconfiguration?view=skype-ps)

[Remove-CsClsConfiguration](/powershell/module/skype/remove-csclsconfiguration?view=skype-ps)