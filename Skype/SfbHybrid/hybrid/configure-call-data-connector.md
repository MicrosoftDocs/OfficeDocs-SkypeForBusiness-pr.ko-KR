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
description: 통화 데이터 커넥터를 구성하기 위한 지침으로, 비즈니스용 Skype 온라인 도구를 사용하여 비즈니스용 Skype 있습니다.
ms.openlocfilehash: bc9346919e3f70d8fe8fe3e43e61a0e715cf0eb9bf52534a2beb2f8604b920f8
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54323690"
---
# <a name="configure-call-data-connector"></a>호출 데이터 커넥터 구성

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]


이 문서에서는 CQD(온라인 통화 품질 대시보드) 및 CA(통화 분석) 도구를 사용하여 비즈니스용 Skype 서버 통화 품질 데이터를 볼 수 있도록 하는 단일 도구 집합인 통화 데이터 커넥터를 비즈니스용 Skype 방법을 설명합니다.

역할 요구 사항 및 하이브리드 연결 설정과 같은 통화 데이터 커넥터의 이점 및 선행 조건에 대한 자세한 내용은 [Plan Call Data Connector을 참조하십시오.](plan-call-data-connector.md)

## <a name="enable-monitoring"></a>모니터링 사용
 
로컬 LCSCdr 및 QoEMetrics 데이터베이스를 사용하여 프런트 엔드 풀 모니터링에서 CDR(통화 데이터 기록) 및 QoE(QoE) 데이터 수집을 구성해야 합니다. 그렇지 않으면 Call Analytics 및 통화 품질 대시보드에서 사용할 데이터를 얻지 못합니다. 통화 데이터 커넥터를 구성하기 전에 Deploy [monitoring in 비즈니스용 Skype 서버에](../../SfbServer/deploy/deploy-monitoring/deploy-monitoring.md) 제공된 단계에 따라 CDR 및 QoE와 기본 모니터링을 모두 구성합니다.

> [!IMPORTANT]
> 프런트 엔드 풀에서 모니터링을 사용하도록 설정하지 않은 경우 통화 데이터 커넥터가 작동하지 않습니다.

## <a name="enable-call-data-connector"></a>통화 데이터 커넥터 사용

통화 데이터 커넥터를 구성하고 사용하도록 설정하려면 다음 cmdlet을 사용하게 됩니다.

| Cmdlet| 설명|
| :-----------------|---------------:|
| New-CsCloudCallDataConnection | 온라인 데이터 수집을 설정하는 온라인 cmdlet입니다.|
| Get-CsCloudCallDataConnection | 기존 온라인 데이터 수집기에서 검색하는 온라인 cmdlet입니다.|  
| Get-CsCloudCallDataConnector | New-CsCloudCallDataConnection cmdlet에서 만든 연결 정보를 검색하는 New-CsCloudCallDataConnection cmdlet입니다. |
| Set-CsCloudCallDataConnector | 프레미스 cmdlet에서 만든 연결 정보의 사내 복사본을 저장하는 New-CsCloudCallDataConnection cmdlet입니다. |  
| Set-CsCloudCallDataConnectorConfiguration | 커넥터를 사용하도록 설정하거나 사용하지 않도록 설정하고 범위 수준을 사용자 지정할 수 있는 사내 cmdlet입니다.|

> [!NOTE]
> 구성을 지우고 다시 시작하려면 Remove-csclouddatconnectorconfiguration cmdlet을 사용하시기 바랍니다.

### <a name="configure-your-environment"></a>환경 구성 

온라인 데이터 수집을 사용하도록 환경을 구성하려면 먼저 온라인 PowerShell을 관리자로 비즈니스용 Skype 로그인해야 합니다. 자세한 내용은 [PowerShell을 사용하여 비즈니스용 Skype Online Office 365 참조하세요.](/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)

Online PowerShell에 로그인하는 방법에는 비즈니스용 Skype 있습니다.

- 2019 비즈니스용 Skype 서버 관리 셸(권장 방법)
- 다른 PowerShell 세션에서

#### <a name="log-in-to-skype-for-business-online-powershell-from-the-skype-for-business-server-management-shell-recommended-method"></a>비즈니스용 Skype 관리 셸에서 비즈니스용 Skype 서버 PowerShell에 로그인합니다(권장 방법).

1. 커넥터를 처음으로 사용하도록 설정하는 경우 다음 명령을 실행합니다.

   ```PowerShell
   New-CsCloudCallDataConnection | Set-CsCloudCallDataConnector -TenantId <tenant_id>
   ```

2. 연결이 이미 있는 경우 테넌트에 대한 통화 데이터 연결이 이미 존재하게 됩니다. 이 경우 다음 명령을 실행합니다. 

   ```PowerShell
   Get-CsCloudCallDataConnection | Set-CsCloudCallDataConnector -TenantId <tenant_id>
   ```


#### <a name="log-in-to-skype-for-business-online-powershell-from-another-powershell-session-optional-method"></a>다른 PowerShell 세션에서 비즈니스용 Skype PowerShell에 로그인합니다(선택적 방법).

1.  커넥터를 처음으로 사용하도록 설정하는 경우 다음 명령을 실행합니다. 

    ```PowerShell 
    New-CsCloudCallDataConnection 
    ```

2.  연결이 이미 있는 경우 테넌트에 대한 통화 데이터 연결이 이미 존재하게 됩니다. 이 경우 다음 명령을 실행합니다. 

    ```PowerShell
    Get-CsCloudCallDataConnection  
    ```

위의 명령의 출력에는 다음과 같이 사내 환경을 구성할 때 필요한 토큰 값이 포함되어 있습니다.

관리 비즈니스용 Skype 서버 내에서 다음 명령을 지정합니다.

```PowerShell
Set-CsCloudCallDataConnector -Identity Global -TenantId <tenant_id> -Token <token-copied-from-online>
```

### <a name="configure-the-scope"></a>범위 구성

특정 사이트 또는 전체 비즈니스용 Skype 서버 관리 셸 내에서 Set-CsCloudCallDataConnectorConfiguration cmdlet을 사용하여 통화 데이터 커넥터를 사용하도록 설정할 비즈니스용 Skype 서버 있습니다. 예를 들어 다음 명령은 전역 범위에서 Call Data Connector를 사용할 수 있습니다.

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $True
```

전역 설정 외에도 통화 데이터 커넥터 구성 설정을 사이트 범위에 할당할 수 있습니다. 이렇게 하면 모니터링과 관련해 추가적인 관리 유연성을 제공합니다. 예를 들어 관리자는 다음 예와 같이 Redmond 사이트에 대해 통화 데이터 커넥터 전달을 사용하도록 설정하고 Dublin 사이트에 대해 통화 데이터 커넥터 전달을 사용하지 않도록 설정할 수 있습니다.

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "site:Redmond" -EnableCallDataConnector $True
```

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "site:Dublin" -EnableCallDataConnector $False
```

사이트 범위에서 구성된 설정이 전역 범위에서 구성된 설정보다 우선합니다. 예를 들어 통화 데이터 커넥터 전달이 전역 범위에서 사용하도록 설정되어 있지만 사이트 범위(Redmond 사이트의 경우)에서는 사용하지 않도록 설정되어 있는 경우를 가정해 보겠습니다. 즉, Redmond 사이트의 사용자에게 통화 정보 기록 및 QoE 정보가 전달되지 않습니다. 그러나 다른 사이트의 사용자(즉, Redmond 사이트 설정 대신 전역 설정으로 관리되는 사용자)의 통화 정보 기록 및 QoE 정보가 전달됩니다.

통화 데이터 커넥터에서 가장 일반적으로 사용되는 설정의 값은 다음 표에 나와 있습니다.  

|속성|설명|기본값|
|:-----|:-----|:-----|
|EnableCallDataConnector  <br/> |통화 데이터 커넥터를 사용할지 여부를 나타냅니다. True이면 모니터링 레코드가 온라인 모니터링으로 전달됩니다.  <br/> |$False  <br/> |
| ID | 명령의 범위 수준(global 또는 site)을 지정합니다.   | global  |

## <a name="disable-call-data-connector"></a>통화 데이터 커넥터를 사용하지 않도록 설정

통화 데이터 커넥터를 설정하지 않으면 프런트 엔드 풀에서 모니터링 저장소의 연결이 되거나 백 엔드 모니터링 데이터베이스에 영향을 주지 않습니다. 통화 데이터 커넥터를 사용하지 않도록 설정하면 통화 비즈니스용 Skype 서버 클라우드로 통화 데이터가 업로드되지 않습니다. 

Set-CsCloudCallDataConnectorConfiguration 관리 셸 내에서 호출 데이터 커넥터를 사용하지 않도록 비즈니스용 Skype 서버 있습니다. 예를 들어 다음 명령은 EnableCallDataConnector 속성을 전역 범위에서 호출 데이터 커넥터를 사용하지 않도록 $False.

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $False
```

통화 데이터를 클라우드에 다시 업로드하려면 다음 예제와 같이 EnableCallDataConnector 속성을 $True 다시 설정하십시오.

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $True
```

## <a name="view-on-premises-data-through-the-online-dashboard"></a>온라인 대시보드를 통해온-프레미스 데이터 보기

 통화 데이터 커넥터를 사용하도록 설정한 후 Call [Analytics를](/skypeforbusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality) 사용하여 품질 문제를 해결하고 통화 품질 대시보드를 켜고 Microsoft Teams 및 비즈니스용 Skype Online에 설명된 바와 같이 통화 분석 대시보드 또는 통화 품질 대시보드에서온-프레미스 통화 [데이터를 볼 수](/MicrosoftTeams/turning-on-and-using-call-quality-dashboard)있습니다.

## <a name="for-more-information"></a>자세한 내용

cmdlet에 대한 자세한 내용은 Get-Help 관리 셸에서 비즈니스용 Skype 서버 있습니다. 예:

Get-Help Get-CsCloudCallDataConnector | more

Get-Help Set-CsCloudCallDataConnector | more

Get-Help Set-CsCloudCallDataConnectorConfiguration | more