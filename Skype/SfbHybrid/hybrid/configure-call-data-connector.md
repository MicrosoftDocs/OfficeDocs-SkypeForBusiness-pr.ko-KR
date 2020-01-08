---
title: Call Data Connector 구성
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: 비즈니스용 Skype Online 도구를 사용 하 여 온-프레미스에서 비즈니스용의 원격 분석을 볼 수 있도록 하는 Call Data Connector를 구성 하기 위한 지침입니다.
ms.openlocfilehash: 4d472ce49a3059df7286c647b013abe321b9fd15
ms.sourcegitcommit: afc7edd03f4baa1d75f9642d4dbce767fec69b00
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/07/2020
ms.locfileid: "40963046"
---
# <a name="configure-call-data-connector"></a>Call Data Connector 구성

이 문서에서는 Skype for Business 온라인 통화 품질 대시보드 (CQD) 및 CA (통화 분석) 도구를 사용 하 여 비즈니스용 Skype 서버 통화 품질 데이터를 볼 수 있도록 하는 단일 도구 집합이 있는 Call Data Connector를 구성 하는 방법을 설명 합니다.

통화 데이터 커넥터 이점과 필수 구성 요소 (예: 역할 요구 사항 및 하이브리드 연결 설정)에 대 한 자세한 내용은 [Plan Call Data Connector](plan-call-data-connector.md)를 참조 하십시오.

## <a name="enable-monitoring"></a>모니터링 사용
 
QoE (Call Data 레코딩) 및 프런트 엔드 풀 모니터링에서 로컬 LCSCdr 및 QoEMetrics 데이터베이스를 사용 하 여 데이터 수집을 구성 해야 합니다. 그렇지 않으면 통화 분석 및 통화 품질 대시보드가 작업할 데이터를 가져올 수 없습니다. 통화 데이터 커넥터를 구성 하기 전에 [비즈니스용 Skype 서버의 배포 모니터링](../../SfbServer/deploy/deploy-monitoring/deploy-monitoring.md) 에서 제공 되는 단계에 따라 CDR 및 QoE를 비롯 하 여 기본 모니터링을 모두 구성 합니다.

> [!IMPORTANT]
> 프런트 엔드 풀에서 모니터링을 사용 하지 않는 경우에는 Call Data Connector가 작동 하지 않습니다.

## <a name="enable-call-data-connector"></a>Call Data Connector 사용

Call Data Connector를 구성 하 고 사용 하도록 설정 하려면 다음 cmdlet을 사용 합니다.

| #A0| 설명|
| :-----------------|---------------:|
| CsCloudCallDataConnection | 온라인 데이터 수집기를 설정 하는 온라인 cmdlet|
| CsCloudCallDataConnection | 기존 온라인 데이터 수집기를 검색 하는 온라인 cmdlet입니다.|  
| CsCloudCallDataConnector | CsCloudCallDataConnection cmdlet을 사용 하 여 만든 연결 정보를 검색 하는 온-프레미스 cmdlet입니다. |
| CsCloudCallDataConnector | CsCloudCallDataConnection cmdlet을 사용 하 여 만든 연결 정보의 온-프레미스 복사본을 저장 하는 온-프레미스 cmdlet입니다. |  
| CsCloudCallDataConnectorConfiguration | 커넥터를 사용 하거나 사용 하지 않도록 설정 하 고 범위 수준을 사용자 지정할 수 있는 온-프레미스 cmdlet입니다.|

> [!NOTE]
> 구성을 지우고 다시 시작 하려면 Remove-csclouddat커넥터 구성 cmdlet을 사용 하세요.

### <a name="configure-your-environment"></a>환경 구성 

온라인 데이터 수집기를 사용 하도록 환경을 구성 하려면 먼저 비즈니스용 Skype Online PowerShell에 관리자로 로그인 해야 합니다. 자세한 내용은 [Office 365 PowerShell을 사용 하 여 비즈니스용 Skype Online 관리](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)를 참조 하세요.

비즈니스용 Skype Online PowerShell에 로그인 하는 방법에는 다음 두 가지가 있습니다.

- 비즈니스용 Skype 서버 2019 관리 셸 (권장 방법)
- 다른 PowerShell 세션에서

#### <a name="log-in-to-skype-for-business-online-powershell-from-the-skype-for-business-server-management-shell-recommended-method"></a>비즈니스용 skype 서버 관리 셸에서 비즈니스용 Skype Online PowerShell에 로그인 합니다 (권장 방법).

1. 처음으로 커넥터를 사용 하도록 설정 하는 경우 다음 명령을 실행 합니다.

   ```PowerShell
   New-CsCloudCallDataConnection | Set-CsCloudCallDataConnector -TenantId <tenant_id>
   ```

2. 연결이 이미 존재 한다는 오류가 표시 되 면 테 넌 트에 대 한 호출 데이터 연결이 이미 있는 것입니다. 이 경우에는 다음 명령을 실행 합니다. 

   ```PowerShell
   Get-CsCloudCallDataConnection | Set-CsCloudCallDataConnector -TenantId <tenant_id>
   ```


#### <a name="log-in-to-skype-for-business-online-powershell-from-another-powershell-session-optional-method"></a>다른 PowerShell 세션에서 비즈니스용 Skype Online PowerShell에 로그인 (optional 메서드)

1.  처음으로 커넥터를 사용 하도록 설정 하는 경우 다음 명령을 실행 합니다. 

    ```PowerShell 
    New-CsCloudCallDataConnection 
    ```

2.  연결이 이미 존재 한다는 오류가 표시 되 면 테 넌 트에 대 한 호출 데이터 연결이 이미 있는 것입니다. 이 경우에는 다음 명령을 실행 합니다. 

    ```PowerShell
    Get-CsCloudCallDataConnection  
    ```

위의 명령 출력에는 다음과 같이 온-프레미스 환경을 구성할 때 필요한 토큰 값이 포함 됩니다.

비즈니스용 Skype 서버 관리 셸 내에서 다음 명령을 지정 합니다.

```PowerShell
Set-CsCloudCallDataConnector -Identity Global -TenantId <tenant_id> -Token <token-copied-from-online>
```

### <a name="configure-the-scope"></a>범위 구성

비즈니스용 Skype 서버 관리 셸에서 CsCloudCallDataConnectorConfiguration cmdlet을 사용 하 여 특정 사이트 또는 전체 비즈니스용 Skype 서버 배포에 대해 Call Data Connector를 사용 하도록 설정할 수 있습니다. 예를 들어 다음 명령은 전역 범위에서 Call Data Connector를 사용 하도록 설정 합니다.

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $True
```

전역 설정 외에도, 통화 데이터 커넥터 구성 설정이 사이트 범위에 할당 될 수 있습니다. 이렇게 하면 모니터링에 있어 추가 관리 유연성이 제공 됩니다. 예를 들어 관리자가 Redmond 사이트에 대 한 통화 데이터 커넥터 전달을 사용 하도록 설정할 수 있지만 다음 예제와 같이 더블린 사이트에 대 한 통화 데이터 커넥터 전달을 사용 하지 않도록 설정할 수도 있습니다.

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "site:Redmond" -EnableCallDataConnector $True
```

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "site:Dublin" -EnableCallDataConnector $False
```

사이트 범위에서 구성된 설정이 전역 범위에서 구성된 설정보다 우선합니다. 예를 들어 Call Data Connector 전달은 전역 범위에서 사용 하도록 설정 되어 있지만 사이트 범위에서 사용 하지 않도록 설정 되어 있습니다 (Redmond 사이트의 경우). 즉, Redmond 사이트의 사용자에 대해 통화 정보 기록 및 QoE 정보가 전달 되지 않습니다. 그러나 다른 사이트의 사용자, 즉 Redmond 사이트 설정 대신 전역 설정으로 관리 되는 사용자에 게는 통화 정보 기록 및 QoE 정보가 전달 됩니다.

Call Data Connector에서 사용 되는 가장 일반적으로 사용 되는 설정 값은 다음 표에 나와 있습니다.  

|속성|설명|기본값|
|:-----|:-----|:-----|
|EnableCallDataConnector  <br/> |Call Data Connector가 사용 하도록 설정 되어 있는지 여부를 나타냅니다. True 인 경우 모니터링 레코드가 온라인 모니터링으로 전달 됩니다.  <br/> |$False  <br/> |
| ID | 명령의 범위 수준 (전역 또는 사이트)을 지정 합니다.   | global  |

## <a name="disable-call-data-connector"></a>Call Data Connector 사용 안 함

Call Data Connector를 사용 하지 않도록 설정 해도 프런트 엔드 풀에서 모니터링 저장소의 연결이 해제 되지 않으며 백엔드 모니터링 데이터베이스도 제거 되거나 영향을 받지 않습니다. 통화 데이터 커넥터를 사용 하지 않도록 설정 하면 비즈니스용 Skype 서버가 클라우드로 호출 데이터를 업로드 하지 못합니다. 

비즈니스용 Skype 서버 관리 셸에서 CsCloudCallDataConnectorConfiguration cmdlet을 사용 하 여 Call Data Connector를 사용 하지 않도록 설정 합니다. 예를 들어 다음 명령은 EnableCallDataConnector 속성을 $False로 설정 하 여 전역 범위에서 Call Data Connector를 사용 하지 않도록 설정 합니다.

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $False
```

클라우드로의 통화 데이터 업로드를 다시 시작 하려면 다음 예제와 같이 EnableCallDataConnector 속성을 다시 $True로 설정 합니다.

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $True
```

## <a name="view-on-premises-data-through-the-online-dashboard"></a>온라인 대시보드를 통해 온-프레미스 데이터 보기

 Call Data Connector를 사용 하도록 설정한 후에는 통화 분석 대시보드에서 통화 품질 대시보드의 온-프레미스 통화 데이터를 확인 [하 여 사용 중인 품질 문제를 해결 하](https://docs.microsoft.com/skypeforbusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality) 고 [Microsoft 팀 및 비즈니스용 Skype Online에 대 한 통화 품질 대시보드를 켜고 사용할](/MicrosoftTeams/turning-on-and-using-call-quality-dashboard)수 있습니다.

## <a name="for-more-information"></a>자세한 내용

Cmdlet에 대 한 자세한 내용은 비즈니스용 Skype 서버 관리 셸에서 Get-Help 명령을 사용 하면 됩니다. 예를 들면 다음과 같습니다.

Get-help-CsCloudCallDataConnector | 자세한

Get-help CsCloudCallDataConnector | 자세한

Get-help CsCloudCallDataConnectorConfiguration | 자세한
