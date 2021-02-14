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
localization_priority: Normal
ms.collection: ''
description: 비즈니스용 Skype Online 도구를 사용하여 비즈니스용 Skype의 원격 분석이 볼 수 있도록 하는 통화 데이터 커넥터를 구성하기 위한 지침입니다.
ms.openlocfilehash: 0354f5a1fd1b4794af29d23e0a0fc1bf49dfebd2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726928"
---
# <a name="configure-call-data-connector"></a>호출 데이터 커넥터 구성

이 문서에서는 비즈니스용 Skype 온라인 통화 품질 대시보드(CQD) 및 CA(통화 분석) 도구를 사용하여 비즈니스용 Skype 서버 통화 품질 데이터를 볼 수 있도록 하는 단일 도구 집합인 통화 데이터 커넥터를 구성하는 방법을 설명합니다.

역할 요구 사항 및 하이브리드 연결 설정과 같은 통화 데이터 커넥터의 이점 및 선행 조건에 대한 자세한 내용은 통화 데이터 커넥터 [계획(Plan Call Data Connector)을 참조하십시오.](plan-call-data-connector.md)

## <a name="enable-monitoring"></a>모니터링 사용
 
로컬 LCSCdr 및 QoEMetrics 데이터베이스를 사용하여 프런트 엔드 풀 모니터링에서 CDR(통화 데이터 기록) 및 QoE(QoE) 데이터 수집을 구성해야 합니다. 그렇지 않으면 통화 분석 및 통화 품질 대시보드에서 사용할 데이터를 얻지 못합니다. 통화 데이터 커넥터를 구성하기 전에 비즈니스용 [Skype](../../SfbServer/deploy/deploy-monitoring/deploy-monitoring.md) 서버에서 모니터링 배포에 제공된 단계에 따라 CDR 및 QoE와 기본 모니터링을 모두 구성합니다.

> [!IMPORTANT]
> 프런트 엔드 풀에서 모니터링을 사용하도록 설정하지 않은 경우 통화 데이터 커넥터가 작동하지 않습니다.

## <a name="enable-call-data-connector"></a>통화 데이터 커넥터 사용

통화 데이터 커넥터를 구성하고 사용하도록 설정하려면 다음 cmdlet을 사용하게 됩니다.

| Cmdlet| 설명|
| :-----------------|---------------:|
| New-CsCloudCallDataConnection | 온라인 데이터 수집을 설정하는 온라인 cmdlet입니다.|
| Get-CsCloudCallDataConnection | 기존 온라인 데이터 수집기에서 검색하는 온라인 cmdlet입니다.|  
| Get-CsCloudCallDataConnector | 프레미스 cmdlet에서 만든 연결 정보를 검색하는 New-CsCloudCallDataConnection cmdlet입니다. |
| Set-CsCloudCallDataConnector | 프레미스 cmdlet에서 만든 연결 정보의 New-CsCloudCallDataConnection 저장하는 New-CsCloudCallDataConnection cmdlet입니다. |  
| Set-CsCloudCallDataConnectorConfiguration | 커넥터를 활성화 또는 사용하지 않도록 설정하고 범위 수준을 사용자 지정할 수 있는 On-프레미스 cmdlet입니다.|

> [!NOTE]
> 구성을 지우고 다시 시작하려면 Remove-csclouddatconnectorconfiguration cmdlet을 사용하시기 바랍니다.

### <a name="configure-your-environment"></a>환경 구성 

온라인 데이터 수집을 사용하도록 환경을 구성하려면 먼저 비즈니스용 Skype Online PowerShell에 관리자로 로그인해야 합니다. 자세한 내용은 [Office 365 PowerShell을](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)사용하여 비즈니스용 Skype Online 관리를 참조하세요.

비즈니스용 Skype Online PowerShell에 로그인하는 방법에는 두 가지가 있습니다.

- 비즈니스용 Skype 서버 2019 관리 셸에서(권장 방법)
- 다른 PowerShell 세션에서

#### <a name="log-in-to-skype-for-business-online-powershell-from-the-skype-for-business-server-management-shell-recommended-method"></a>비즈니스용 Skype 서버 관리 셸에서 비즈니스용 Skype Online PowerShell에 로그인(권장 방법)

1. 커넥터를 처음으로 사용하도록 설정하는 경우 다음 명령을 실행합니다.

   ```PowerShell
   New-CsCloudCallDataConnection | Set-CsCloudCallDataConnector -TenantId <tenant_id>
   ```

2. 연결이 이미 있는 경우 테넌트에 대한 통화 데이터 연결이 이미 있는 것입니다. 이 경우 다음 명령을 실행합니다. 

   ```PowerShell
   Get-CsCloudCallDataConnection | Set-CsCloudCallDataConnector -TenantId <tenant_id>
   ```


#### <a name="log-in-to-skype-for-business-online-powershell-from-another-powershell-session-optional-method"></a>다른 PowerShell 세션에서 비즈니스용 Skype Online PowerShell에 로그인합니다(선택 사항).

1.  커넥터를 처음으로 사용하도록 설정하는 경우 다음 명령을 실행합니다. 

    ```PowerShell 
    New-CsCloudCallDataConnection 
    ```

2.  연결이 이미 있는 경우 테넌트에 대한 통화 데이터 연결이 이미 있는 것입니다. 이 경우 다음 명령을 실행합니다. 

    ```PowerShell
    Get-CsCloudCallDataConnection  
    ```

위의 명령의 출력에는 다음과 같이 토큰 값이 포함되어 있으며, 이 토큰 값은 다음과 같이 프레미스 환경을 구성할 때 필요합니다.

비즈니스용 Skype 서버 관리 셸 내에서 다음 명령을 지정합니다.

```PowerShell
Set-CsCloudCallDataConnector -Identity Global -TenantId <tenant_id> -Token <token-copied-from-online>
```

### <a name="configure-the-scope"></a>범위 구성

비즈니스용 Skype 서버 관리 셸 내에서 Set-CsCloudCallDataConnectorConfiguration cmdlet을 사용하여 특정 사이트 또는 전체 비즈니스용 Skype 서버 배포에 대해 통화 데이터 커넥터를 사용하도록 설정할 수 있습니다. 예를 들어 다음 명령은 전역 범위에서 Call Data Connector를 사용할 수 있습니다.

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $True
```

전역 설정 외에도 통화 데이터 커넥터 구성 설정을 사이트 범위에 할당할 수 있습니다. 따라서 모니터링과 관련해 추가적인 관리 유연성을 제공합니다. 예를 들어 관리자는 다음 예와 같이 Redmond 사이트에 대해 통화 데이터 커넥터 전달을 사용하도록 설정하고 Dublin 사이트에 대해 통화 데이터 커넥터 전달을 사용하지 않도록 설정할 수 있습니다.

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "site:Redmond" -EnableCallDataConnector $True
```

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "site:Dublin" -EnableCallDataConnector $False
```

사이트 범위에서 구성된 설정이 전역 범위에서 구성된 설정보다 우선합니다. 예를 들어 Call Data Connector 전달이 전역 범위에서 사용되지만 사이트 범위(Redmond 사이트의 경우)에서 사용하지 않도록 설정되어 있는 경우를 가정해 보겠습니다. 즉, Redmond 사이트의 사용자에게 통화 정보 기록 및 QoE 정보가 전달되지 않습니다. 그러나 다른 사이트의 사용자(즉, Redmond 사이트 설정 대신 전역 설정으로 관리되는 사용자)는 통화 정보 기록 및 QoE 정보를 전달합니다.

통화 데이터 커넥터에서 사용하는 가장 일반적으로 사용되는 설정의 값은 다음 표에 나와 있습니다.  

|속성|설명|기본값|
|:-----|:-----|:-----|
|EnableCallDataConnector  <br/> |통화 데이터 커넥터를 사용할지 여부를 나타냅니다. True로 설정하면 모니터링 레코드가 온라인 모니터링으로 전달됩니다.  <br/> |$False  <br/> |
| ID | 명령의 범위 수준(전역 또는 사이트)을 지정합니다.   | global  |

## <a name="disable-call-data-connector"></a>통화 데이터 커넥터를 사용하지 않도록 설정

통화 데이터 커넥터를 설정하지 않으면 프런트 엔드 풀에서 모니터링 저장소의 연결이 되거나 백 엔드 모니터링 데이터베이스에 영향을 주지 않습니다. 통화 데이터 커넥터를 사용하지 않도록 설정하면 비즈니스용 Skype 서버가 클라우드에 통화 데이터를 업로드하지 못하게 합니다. 

비즈니스용 Skype 서버 관리 셸 내에서 Set-CsCloudCallDataConnectorConfiguration cmdlet을 사용하여 Call Data Connector를 사용하지 않도록 설정할 수 있습니다. 예를 들어 다음 명령은 EnableCallDataConnector 속성을 기본 설정으로 설정하여 전역 범위에서 Call Data Connector를 $False.

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $False
```

클라우드에 통화 데이터 업로드를 다시 시작하려면 다음 예제와 같이 EnableCallDataConnector 속성을 $True 다시 설정하십시오.

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $True
```

## <a name="view-on-premises-data-through-the-online-dashboard"></a>온라인 대시보드를 통해온-프레미스 데이터 보기

 통화 데이터 커넥터를 사용하도록 설정한 후 통화 분석을 사용하여 품질 불량 문제를 해결하고 [](https://docs.microsoft.com/skypeforbusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality) Microsoft Teams 및 비즈니스용 [Skype Online에](/MicrosoftTeams/turning-on-and-using-call-quality-dashboard)대해 통화 품질 대시보드를 켜고 사용하는 설명에 따라 통화 분석 대시보드 또는 통화 품질 대시보드에서온-프레미스 통화 데이터를 볼 수 있습니다.

## <a name="for-more-information"></a>자세한 내용

cmdlet에 대한 자세한 내용은 비즈니스용 Skype 서버 관리 셸에서 Get-Help 명령을 사용할 수 있습니다. 예시:

Get-Help Get-CsCloudCallDataConnector | more

Get-Help Set-CsCloudCallDataConnector | more

Get-Help Set-CsCloudCallDataConnectorConfiguration | more
