---
title: 비즈니스용 Skype 2015에서 중앙 로깅 서비스 구성 설정 관리
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 8/17/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 93b9a354-9aea-4b3a-a4fe-68a89f436196
description: '요약: 비즈니스용 Skype Server 2015에서 중앙 집중화 된 로깅 서비스의 구성 설정을 검색, 업데이트 및 만드는 방법에 대해 알아봅니다.'
ms.openlocfilehash: 95aa05cfcd31acda8e78927d674f3a19dff7ef56
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816587"
---
# <a name="manage-centralized-logging-service-configuration-settings-in-skype-for-business-server-2015"></a>비즈니스용 Skype 2015에서 중앙 로깅 서비스 구성 설정 관리

**요약:** 비즈니스용 Skype 서버 2015에서 중앙 로깅 서비스에 대 한 구성 설정을 검색, 업데이트 및 만드는 방법을 알아봅니다.

중앙 로깅 서비스는 각 컴퓨터의 중앙 로깅 서비스 에이전트에 명령을 전송 하기 위해 중앙 집중식 로깅 서비스 컨트롤러 (CLSController)에서 만들고 사용 하는 설정 및 매개 변수를 통해 제어 및 구성 됩니다 ( CLSAgent). 에이전트는 여기에 전송 된 명령을 처리 하 고 (시작 명령의 경우) 시나리오, 공급자, 추적 기간 및 플래그 구성을 사용 하 여 제공 되는 구성 정보에 따라 추적 로그 수집을 시작 합니다.

> [!IMPORTANT]
>  중앙 로깅 서비스에 대해 나열 된 모든 Windows PowerShell cmdlet은 비즈니스용 Skype Server 2015 온-프레미스 배포에만 사용할 수 있는 것은 아닙니다. 이는 작동 하는 것 처럼 보일 수 있지만, 다음 cmdlet는 비즈니스용 Skype Server 2015 온-프레미스 배포에서 작동 하도록 설계 되지 않았습니다.

-  **Csclsregion cmdlet:** [Get-csclsregion](https://docs.microsoft.com/powershell/module/skype/get-csclsregion?view=skype-ps) ,[Set-csclsregion](https://docs.microsoft.com/powershell/module/skype/set-csclsregion?view=skype-ps), [New-csclsregion](https://docs.microsoft.com/powershell/module/skype/new-csclsregion?view=skype-ps), [제거-csclsregion](https://docs.microsoft.com/powershell/module/skype/remove-csclsregion?view=skype-ps).
-  **Csclssearchterm cmdlet:** [Get-csclssearchterm](https://docs.microsoft.com/powershell/module/skype/get-csclssearchterm?view=skype-ps) 및 [Set csclssearchterm](https://docs.microsoft.com/powershell/module/skype/set-csclssearchterm?view=skype-ps)입니다.
-  **Csclssecuritygroup cmdlet:** [Get-csclssecuritygroup](https://docs.microsoft.com/powershell/module/skype/get-csclssecuritygroup?view=skype-ps), [Set-csclssecuritygroup](https://docs.microsoft.com/powershell/module/skype/set-csclssecuritygroup?view=skype-ps), [New-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/new-csclssecuritygroup?view=skype-ps)및 [Remove-csclssecuritygroup](https://docs.microsoft.com/powershell/module/skype/remove-csclssecuritygroup?view=skype-ps).

이러한 cmdlet에 정의 된 설정은 방해 하거나 부정적인 동작을 발생 시 키 지 않으며, Microsoft Office 365에서 사용 하도록 디자인 되었으며 온-프레미스 배포에서 예상 되는 결과가 생성 되지 않습니다. 이는 온-프레미스 배포에서 이러한 cmdlet을 사용 하지 않는 것이 아니라,이를 사용 하는 것이이 문서에서 다루지 않는 고급 항목입니다.

중앙 로깅 서비스는 사이트 범위 (즉, 배포의 컴퓨터 및 풀의 컬렉션을 포함 하는 사이트 Redmond) 또는 전역 범위 (즉, 지정 된 사이트)에서 단일 컴퓨터 또는 컴퓨터의 풀을 포함 하는 범위에서 실행할 수 있습니다. , 배포의 모든 컴퓨터 및 풀.

비즈니스용 Skype Server Management Shell을 사용 하 여 중앙 로깅 서비스 범위를 구성 하려면 CsAdministrator 또는 CsServerAdministrator 역할 기반 액세스 제어 (RBAC) 보안 그룹 또는 사용자 지정 RBAC 역할의 구성원 이어야 합니다. 두 그룹 중 하나를 포함 합니다. 이 cmdlet이 할당 된 모든 RBAC 역할 목록 (직접 만든 사용자 지정 RBAC 역할 포함)을 반환 하려면 비즈니스용 Skype Server 관리 셸 또는 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.

```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "<Skype for Business cmdlet>"}
```

예를 들면 다음과 같습니다.

```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

> [!NOTE]
> Windows PowerShell 또는 CLSController에서 실행할 수 있는 명령줄 명령 간에는 기본적인 차이점이 있습니다. Windows PowerShell은 시나리오를 구성 및 정의 하 고 문제 해결 시나리오에 의미 있는 방식으로 해당 시나리오를 다시 사용 하는 다양 한 방법을 제공 합니다. CLSController는 명령을 실행 하 고 결과를 얻을 수 있는 빠르고 효율적인 방법을 제공 하지만 CLSController에 대 한 명령 집합은 명령줄에서 사용할 수 있는 유한 명령으로 제한 됩니다. Windows PowerShell cmdlet과 달리 CLSController는 새 시나리오를 정의 하거나, 사이트 또는 전역 수준의 범위를 관리 하 고, 동적으로 구성할 수 없는 유한 명령 집합의 여러 다른 제한 사항에 대 한 다양 한 제한을 정의할 수 없습니다. CLSController는 빠른 실행을 위한 수단을 제공 하는 반면, Windows PowerShell은 CLSController에서 가능한 기능 외에 중앙 집중식 로깅 서비스 기능을 확장 하는 방법을 제공 합니다.

[Search-](https://docs.microsoft.com/powershell/module/skype/search-csclslogging?view=skype-ps)csclslogging, [표시-csclslogging](https://docs.microsoft.com/powershell/module/skype/show-csclslogging?view=skype-ps), [시작-csclslogging](https://docs.microsoft.com/powershell/module/skype/start-csclslogging?view=skype-ps),,- [Csclslogging](https://docs.microsoft.com/powershell/module/skype/stop-csclslogging?view=skype-ps), [동기화](https://docs.microsoft.com/powershell/module/skype/sync-csclslogging?view=skype-ps) 중이 고-Computers-컴퓨터 매개 변수를 사용 하 여 csclslogging [Update](https://docs.microsoft.com/powershell/module/skype/update-csclslogging?view=skype-ps) 명령을 실행 하는 동안 단일 컴퓨터 범위를 정의할 수 있습니다. -Computers 매개 변수는 대상 컴퓨터에 대 한 Fqdn (정규화 된 도메인 이름) 목록을 쉼표로 구분 하 여 받아들입니다.

> [!TIP]
> 또한 로깅 명령을 실행할 풀의 목록 및 쉼표로 구분 된 목록을 정의할 수 있습니다.

사이트 및 전역 범위는 **새로운** **중앙의 로깅**서비스 cmdlet에 정의 되어 있습니다 **** . 다음 예제에서는 사이트 및 전역 범위를 설정 하는 방법을 보여 줍니다.

> [!IMPORTANT]
> 표시 되는 명령에는 다른 섹션에서 설명 하는 매개 변수 및 개념이 포함 되어 있을 수 있습니다. 이 예제 명령은 **-Identity** 매개 변수를 사용 하 여 범위를 정의 하 고 나머지 매개 변수는 완전성을 위해 포함 하며 범위를 지정 하기 위한 것입니다. **Set-csclsconfiguration** cmdlet에 대 한 자세한 내용은 작업 설명서의 [Set-csclsconfiguration](https://docs.microsoft.com/powershell/module/skype/set-csclsconfiguration?view=skype-ps) 을 참조 하세요.

### <a name="to-retrieve-the-current-centralized-logging-service-configuration"></a>현재 중앙 집중화 된 로깅 서비스 구성을 검색 하려면

1. 비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **비즈니스용 skype 2015**을 차례로 클릭 한 다음 비즈니스용 **skype Server management Shell**을 클릭 합니다.

2. 명령줄 프롬프트에 다음을 입력 합니다.

   ```PowerShell
   Get-CsClsConfiguration
   ```

새 구성을 만들거나 기존 구성을 업데이트 하기 위해 **새로운 csclsconfiguration** 및 **Set csclsconfiguration** cmdlet을 사용 합니다. **Get-CsClsConfiguration**을 실행 하면 배포에 현재 기본 전역 구성이 있지만 사이트 구성이 정의 되지 않은 다음 스크린샷은 다음과 같은 정보가 표시 됩니다.

![Get-CsClsConfiguration의 샘플 출력.](../../media/Ops_Get-CsClsConfiguration_Basic.jpg)

### <a name="to-retrieve-the-current-centralized-logging-service-configuration-from-the-computer-local-store"></a>컴퓨터 로컬 저장소에서 현재 중앙 집중화 된 로깅 서비스 구성을 검색 하려면

1. 비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **비즈니스용 skype 2015**을 차례로 클릭 한 다음 비즈니스용 **skype Server management Shell**을 클릭 합니다.

2. 명령줄 프롬프트에 다음을 입력 합니다.

   ```PowerShell
   Get-CsClsConfiguration -LocalStore
   ```

**Get-CsClsConfiguration** 이 매개 변수를 지정 하지 않는 첫 번째 예제를 사용 하는 경우 명령은 데이터에 대 한 중앙 관리 저장소를 참조 합니다. 매개 변수-LocalStore를 지정 하는 경우이 명령은 중앙 관리 저장소 대신 컴퓨터 LocalStore를 참조 합니다.
### <a name="to-retrieve-a-listing-of-scenarios-currently-defined"></a>현재 정의 된 시나리오 목록을 검색 하려면

1. 비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **비즈니스용 skype 2015**을 차례로 클릭 한 다음 비즈니스용 **skype Server management Shell**을 클릭 합니다.

2. 명령줄 프롬프트에 다음을 입력 합니다.

   ```PowerShell
   Get-CsClsConfiguration -Identity <scope and name> | Select-Object -ExpandProperty Scenarios
   ```

    예를 들어 전역 범위에서 정의 된 시나리오를 검색 하려면 다음을 실행 합니다.

   ```PowerShell
   Get-CsClsConfiguration -Identity "global" | Select-Object -ExpandProperty Scenarios
   ```

Cmdlet **Get CsClsConfiguration** 은 항상 지정 된 범위의 구성에 속하는 시나리오를 표시 합니다. 대부분의 경우, 모든 시나리오가 표시 되지 않고 잘릴 수 있습니다. 여기에 사용 되는 명령에는 모든 시나리오와 사용 되는 공급자, 설정 및 플래그에 대 한 일부 정보가 나열 됩니다.
### <a name="to-update-a-global-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a>Windows PowerShell을 사용 하 여 중앙 로깅 서비스에 대 한 전역 범위를 업데이트 하려면

1. 비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **비즈니스용 skype 2015**을 차례로 클릭 한 다음 비즈니스용 **skype Server management Shell**을 클릭 합니다.

2. 명령줄 프롬프트에 다음을 입력 합니다.

   ```PowerShell
   Set-CsClsConfiguration -Identity <scope> -EtlFileRolloverSizeMB <size for logging file in megabytes>
   ```

   예를 들면 다음과 같습니다.

   ```PowerShell
   Set-CsClsConfiguration -Identity "global" -EtlFileRolloverSizeMB 40
   ```

이 명령은 배포의 각 컴퓨터와 풀에 CLSAgent를 알려 추적 파일의 롤오버 값 크기를 40 메가바이트 단위로 설정 합니다. 모든 사이트의 컴퓨터 및 풀은 명령의 영향을 받으며, 구성 된 추적 로그 롤오버 값을 40 메가바이트 ()로 설정 합니다.
### <a name="to-update-a-site-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a>Windows PowerShell을 사용 하 여 중앙 로깅 서비스의 사이트 범위를 업데이트 하려면

1. 비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **비즈니스용 skype 2015**을 차례로 클릭 한 다음 비즈니스용 **skype Server management Shell**을 클릭 합니다.

2. 명령줄 프롬프트에 다음을 입력 합니다.

   ```PowerShell
   Set-CsClsConfiguration -Identity <scope/site name> -EtlFileRolloverSizeMB <size for logging file in megabytes>
   ```

   예를 들면 다음과 같습니다.

   ```PowerShell
   Set-CsClsConfiguration -Identity "site/Redmond" -EtlFileRolloverSizeMB 40
   ```

> [!NOTE]
> 이 예제에 나와 있는 것 처럼 로그 파일의 기본 위치 는%TEMP%\Tracing.입니다. 그러나 파일을 기록 하 고 CSLAgent가 네트워크 서비스로 실행 되는 실제 CLSAgent 이기 때문 에% TEMP% 변수 는%WINDIR%\ServiceProfiles\NetworkService\AppData\Local.로 확장 됩니다.

이 명령은 사이트 Redmond의 각 컴퓨터와 풀의 CLSAgent에 게 추적 파일의 롤오버 값 크기를 40 mb로 설정 하도록 지시 합니다. 다른 사이트의 컴퓨터와 풀은 명령에 영향을 받지 않으며, 기본적으로 (20mb) 또는 로깅 세션 시작 중에 정의 된 현재 구성 되어 있는 추적 로그 롤오버 값이 계속 사용 됩니다.
### <a name="to-create-a-new-centralized-logging-service-configuration"></a>중앙 집중화 된 새 로깅 서비스 구성을 만들려면

1. 비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **비즈니스용 skype 2015**을 차례로 클릭 한 다음 비즈니스용 **skype Server management Shell**을 클릭 합니다.

2. 명령줄 프롬프트에 다음을 입력 합니다.

   ```PowerShell
   New-CsClsConfiguration -Identity <scope and name> [CsClsConfiguration options for this site]
   ```

    > [!NOTE]
    > 새로운-CsClsConfiguration을 사용 하면 많은 선택적 구성 설정에 액세스할 수 있습니다. 구성 옵션에 대 한 자세한 내용은 [CsClsConfiguration 가져오기](https://docs.microsoft.com/powershell/module/skype/get-csclsconfiguration?view=skype-ps) 및 [중앙 로깅 서비스 구성 설정 이해](https://technet.microsoft.com/library/3c34e600-0b91-43dc-b4cc-90b6a70ee12e.aspx)를 참조 하세요.

예를 들어 캐시 파일에 대 한 네트워크 폴더, 로그 파일에 대 한 롤오버 기간 및 로그 파일에 대 한 롤오버 크기를 정의 하는 새 구성을 만들려면 다음을 입력 합니다.

  ```PowerShell
  New-CsClsConfiguration -Identity "site:Redmond" -CacheFileNetworkFolder "\\fs01.contoso.net\filestore\logfiles" -EtlFileRolloverMinutes 120 -EtlFileRolloverSizeMB 40
  ```

새 구성 만들기와 중앙 로깅 서비스의 새 속성을 정의 하는 방법을 주의 깊게 계획 해야 합니다. 변경 하는 데는 주의를 기울여야 하며 문제 시나리오를 올바르게 기록 하는 기능에 대 한 영향을 이해 하 고 있는지 확인 해야 합니다. 로그를 크기와 관리 하는 기능을 개선 하 고 발생 하는 문제 해결을 가능 하 게 하는 구성 변경 작업을 수행 하는 것이 좋습니다.
### <a name="to-remove-an-existing-centralized-logging-service-configuration"></a>기존 중앙 로깅 서비스 구성을 제거 하려면

1. 비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **비즈니스용 skype 2015**을 차례로 클릭 한 다음 비즈니스용 **skype Server management Shell**을 클릭 합니다.

2. 명령줄 프롬프트에 다음을 입력 합니다.

   ```PowerShell
   Remove-CsClsConfiguration -Identity <scope and name>
   ```

예를 들어 로그 파일 롤오버 시간을 늘리기 위해 만든 중앙 로깅 서비스 구성을 제거 하려면 롤오버 로그 파일 크기를 늘리고 다음과 같이 로그 파일 캐시 위치를 네트워크 공유로 설정 합니다.

  ```PowerShell
  Remove-CsClsConfiguration -Identity "site:Redmond"
  ```

> [!NOTE]
> "새 중앙 로깅 서비스 구성을 만들려면" 절차에서 만든 새 구성입니다.

사이트 수준 구성을 제거 하도록 선택 하면 사이트에 전역 설정이 사용 됩니다.
## <a name="see-also"></a>참고 항목

[비즈니스용 Skype 2015에서 중앙 로깅 서비스에 대한 공급자 구성](configure-providers.md)

[비즈니스용 Skype 2015에서 중앙 로깅 서비스에 대한 시나리오 구성](configure-scenarios.md)

[비즈니스용 Skype 2015의 중앙 로깅 서비스](centralized-logging-service.md)

[Set-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csclsconfiguration?view=skype-ps)

[Get-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csclsconfiguration?view=skype-ps)

[New-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csclsconfiguration?view=skype-ps)

[-CsClsConfiguration 제거](https://docs.microsoft.com/powershell/module/skype/remove-csclsconfiguration?view=skype-ps)
