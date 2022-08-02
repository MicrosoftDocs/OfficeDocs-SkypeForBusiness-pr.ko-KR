---
title: 호출 데이터 커넥터 구성
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.collection: ''
description: 비즈니스용 Skype Online 도구를 사용하여 비즈니스용 Skype 온-프레미스의 원격 분석을 볼 수 있도록 하는 통화 데이터 커넥터를 구성하기 위한 지침입니다.
ms.openlocfilehash: 0d92d31798cd4b3fb5a1b4c555ff0ff00c2bdf31
ms.sourcegitcommit: 07761c26b53d92fc36b82cab7b3e38a6de4ff945
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/02/2022
ms.locfileid: "67156936"
---
# <a name="configure-call-data-connector"></a>호출 데이터 커넥터 구성

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]


이 문서에서는 Microsoft CQD(통화 품질 대시보드) 및 CA(통화 분석) 도구를 사용하여 통화 품질 데이터를 볼 수 비즈니스용 Skype 서버 단일 도구 집합인 통화 데이터 커넥터를 구성하는 방법을 설명합니다.

호출 데이터 커넥터 혜택 및 필수 구성 요소(예: 역할 요구 사항 및 하이브리드 연결 설정)에 대한 자세한 내용은 [통화 데이터 커넥터 계획을](plan-call-data-connector.md) 참조하세요.

## <a name="enable-monitoring"></a>모니터링 사용
 
로컬 LCSCdr 및 QoEMetrics 데이터베이스를 사용하여 프런트 엔드 풀 모니터링에서 CDR(통화 데이터 기록) 및 QoE(품질) 데이터 수집을 구성해야 합니다. 그렇지 않으면 통화 분석 및 통화 품질 대시보드에서 작업할 데이터를 가져올 수 없습니다. 통화 데이터 커넥터를 구성하기 전에 [비즈니스용 Skype 서버 배포 모니터링에](../../SfbServer/deploy/deploy-monitoring/deploy-monitoring.md) 제공된 단계에 따라 CDR 및 QoE와 기본 모니터링을 모두 구성합니다.

> [!IMPORTANT]
> 프런트 엔드 풀에서 모니터링을 사용하도록 설정하지 않으면 호출 데이터 커넥터가 작동하지 않습니다.

## <a name="enable-call-data-connector"></a>통화 데이터 커넥터 사용

호출 데이터 커넥터를 구성하고 사용하도록 설정하려면 다음 cmdlet을 사용합니다.

| Cmdlet| 설명|
| :-----------------|---------------:|
| New-CsCloudCallDataConnection | 온라인 데이터 수집기를 설정하는 온라인 cmdlet입니다.|
| Get-CsCloudCallDataConnection | 기존 온라인 데이터 수집기를 검색하는 온라인 cmdlet입니다.|  
| Get-CsCloudCallDataConnector | New-CsCloudCallDataConnection cmdlet에서 만든 연결 정보를 검색하는 온-프레미스 cmdlet입니다. |
| Set-CsCloudCallDataConnector | New-CsCloudCallDataConnection cmdlet에서 만든 연결 정보의 온-프레미스 복사본을 저장하는 온-프레미스 cmdlet입니다. |  
| Set-CsCloudCallDataConnectorConfiguration | 커넥터를 사용하거나 사용하지 않도록 설정하고 범위 수준을 사용자 지정할 수 있는 온-프레미스 cmdlet입니다.|

> [!NOTE]
> 구성을 지우고 다시 시작하려면 Remove-csclouddatconnectorconfiguration cmdlet을 사용하세요.

### <a name="configure-your-environment"></a>환경 구성 

온라인 데이터 수집기를 사용하도록 환경을 구성하려면 먼저 관리자 권한으로 Microsoft Teams PowerShell 모듈에 로그인해야 합니다. 자세한 내용은 [Microsoft Teams PowerShell 개요](/microsoftteams/teams-powershell-overview)를 참조하세요.

Microsoft Teams PowerShell 모듈에 로그인하는 방법에는 두 가지가 있습니다.

- 비즈니스용 Skype 서버 2019 관리 셸에서(권장 방법)
- 다른 PowerShell 세션에서

#### <a name="log-in-to-microsoft-teams-powershell-module-from-the-skype-for-business-server-management-shell-recommended-method"></a>비즈니스용 Skype 서버 관리 셸에서 Microsoft Teams PowerShell 모듈에 로그인(권장 방법)

1. 커넥터를 처음으로 사용하도록 설정하는 경우 다음 명령을 실행합니다.

   ```PowerShell
   New-CsCloudCallDataConnection | Set-CsCloudCallDataConnector -TenantId <tenant_id>
   ```

2. 연결이 이미 있다는 오류가 발생하면 테넌트에 대한 호출 데이터 연결이 이미 있음을 의미합니다. 이 경우 다음 명령을 실행합니다. 

   ```PowerShell
   Get-CsCloudCallDataConnection | Set-CsCloudCallDataConnector -TenantId <tenant_id>
   ```


#### <a name="log-in-to-microsoft-teams-powershell-module-from-another-powershell-session-optional-method"></a>다른 PowerShell 세션에서 Microsoft Teams PowerShell 모듈에 로그인(선택적 방법)

1.  커넥터를 처음으로 사용하도록 설정하는 경우 다음 명령을 실행합니다. 

    ```PowerShell 
    New-CsCloudCallDataConnection 
    ```

2.  연결이 이미 있다는 오류가 발생하면 테넌트에 대한 호출 데이터 연결이 이미 있음을 의미합니다. 이 경우 다음 명령을 실행합니다. 

    ```PowerShell
    Get-CsCloudCallDataConnection  
    ```

위의 명령의 출력에는 다음과 같이 온-프레미스 환경을 구성할 때 필요한 토큰 값이 포함됩니다.

비즈니스용 Skype 서버 관리 셸 내에서 다음 명령을 지정합니다.

```PowerShell
Set-CsCloudCallDataConnector -Identity Global -TenantId <tenant_id> -Token <token-copied-from-online>
```

### <a name="configure-the-scope"></a>범위 구성

비즈니스용 Skype 서버 관리 셸 내에서 Set-CsCloudCallDataConnectorConfiguration cmdlet을 사용하여 특정 사이트 또는 전체 비즈니스용 Skype 서버 배포에 대해 통화 데이터 커넥터를 사용하도록 설정할 수 있습니다. 예를 들어 다음 명령은 전역 범위에서 데이터 커넥터 호출을 사용하도록 설정합니다.

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $True
```

전역 설정 외에도 호출 데이터 커넥터 구성 설정을 사이트 범위에 할당할 수 있습니다. 이를 통해 모니터링과 관련하여 추가적인 관리 유연성을 제공합니다. 예를 들어 관리자는 다음 예제와 같이 Redmond 사이트에 대해 통화 데이터 커넥터 전달을 사용하도록 설정할 수 있지만 더블린 사이트에 대한 통화 데이터 커넥터 전달을 사용하지 않도록 설정할 수 있습니다.

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "site:Redmond" -EnableCallDataConnector $True
```

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "site:Dublin" -EnableCallDataConnector $False
```

사이트 범위에서 구성된 설정이 전역 범위에서 구성된 설정보다 우선합니다. 예를 들어 호출 데이터 커넥터 전달이 전역 범위에서 사용하도록 설정되어 있지만 사이트 범위(Redmond 사이트의 경우)에서 사용하지 않도록 설정되었다고 가정합니다. 즉, Redmond 사이트의 사용자에 대해 통화 세부 정보 기록 및 QoE 정보가 전달되지 않습니다. 그러나 다른 사이트(즉, Redmond 사이트 설정 대신 전역 설정으로 관리되는 사용자)의 사용자는 통화 세부 정보 기록 및 QoE 정보를 전달합니다.

호출 데이터 커넥터에서 사용하는 가장 일반적으로 사용되는 설정에 대한 값은 다음 표에 나와 있습니다.  

|속성|설명|기본값|
|:-----|:-----|:-----|
|EnableCallDataConnector  <br/> |호출 데이터 커넥터를 사용할 수 있는지 여부를 나타냅니다. True이면 모니터링 레코드가 온라인 모니터링으로 전달됩니다.  <br/> |$False  <br/> |
| ID | 명령의 범위 수준(전역 또는 사이트)을 결정합니다.   | 글로벌  |

## <a name="disable-call-data-connector"></a>통화 데이터 커넥터 사용 안 함

통화 데이터 커넥터를 사용하지 않도록 설정해도 프런트 엔드 풀에서 모니터링 저장소가 연결되지 않으며 백 엔드 모니터링 데이터베이스를 제거하거나 영향을 주지 않습니다. 통화 데이터 커넥터를 사용하지 않도록 설정하면 비즈니스용 Skype 서버 호출 데이터를 클라우드에 업로드하는 것을 중지합니다. 

비즈니스용 Skype 서버 관리 셸 내에서 Set-CsCloudCallDataConnectorConfiguration cmdlet을 사용하여 호출 데이터 커넥터를 사용하지 않도록 설정합니다. 예를 들어 다음 명령은 EnableCallDataConnector 속성을 $False 설정하여 전역 범위에서 호출 데이터 커넥터를 사용하지 않도록 설정합니다.

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $False
```

클라우드에 호출 데이터 업로드를 다시 시작하려면 다음 예제와 같이 EnableCallDataConnector 속성을 다시 $True 설정합니다.

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $True
```

## <a name="view-on-premises-data-through-the-online-dashboard"></a>온라인 대시보드를 통해 온-프레미스 데이터 보기

 통화 데이터 커넥터를 사용하도록 설정한 후 통화 분석 사용 분석에서 설명한 대로 통화 분석 대시보드 또는 통화 품질 대시보드에서 온-프레미스 통화 데이터를 보고 [품질 저하 문제를 해결하고](/skypeforbusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality) [Microsoft Teams 및 비즈니스용 Skype Online용 통화 품질 대시보드를 켜고 사용할](/MicrosoftTeams/turning-on-and-using-call-quality-dashboard) 수 있습니다.

## <a name="for-more-information"></a>자세한 내용

cmdlet에 대한 자세한 내용은 비즈니스용 Skype 서버 관리 셸의 Get-Help 명령을 사용할 수 있습니다. 예시:

Get-Help Get-CsCloudCallDataConnector | 더

Get-Help Set-CsCloudCallDataConnector | 더

Get-Help Set-CsCloudCallDataConnectorConfiguration | 더
