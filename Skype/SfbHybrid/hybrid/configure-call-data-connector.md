---
title: 통화 데이터 커넥터 구성
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: 비즈니스용 Skype Online 도구를 사용 하 여 온-프레미스로 원격 분석을 볼 수 있도록 하는 Call Data Connector 구성에 대 한 지침입니다.
ms.openlocfilehash: 48af644523e9872107c814aa330d2af2d9a4272f
ms.sourcegitcommit: 1f84b0edc4e418259b9f6392370e2cc4dc70df82
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/30/2019
ms.locfileid: "37328377"
---
# <a name="configure-call-data-connector"></a>통화 데이터 커넥터 구성

이 문서에서는 비즈니스용 Skype Online for CQD (온라인 통화 품질 대시보드) 및 CA (전화 분석) 도구를 사용 하 여 비즈니스용 Skype 서버 통화 품질 데이터를 볼 수 있는 단일 도구 집합 인 Call Data Connector를 구성 하는 방법을 설명 합니다.

통화 데이터 커넥터 혜택 및 역할 요구 사항, 하이브리드 연결 설정 등의 필수 구성 요소에 대 한 자세한 내용은 [요금제 호출 데이터 커넥터](plan-call-data-connector.md)를 참고 하세요.

## <a name="enable-monitoring"></a>모니터링 사용
 
프론트 엔드 풀 모니터링에서 로컬 LCSCdr 및 QoEMetrics 데이터베이스를 사용 하 여 체감 품질 (Call Data 레코딩) 및 체험 (환경 품질) 데이터 수집을 구성 해야 합니다. 그렇지 않으면 통화 분석 및 통화 품질 대시보드에서 작업할 데이터를 가져올 수 없습니다. 통화 데이터 커넥터를 구성 하기 전에 [비즈니스용 Skype 서버에서 모니터링 배포](../../SfbServer/deploy/deploy-monitoring/deploy-monitoring.md) 에 제공 되는 단계를 따라 CDR 및 체감 품질 및 기본 모니터링을 모두 구성 합니다.

> [!IMPORTANT]
> 프런트 엔드 풀에서 모니터링을 사용할 수 없는 경우에는 Call Data Connector가 작동 하지 않습니다.

## <a name="enable-call-data-connector"></a>Call Data Connector 사용

Call Data Connector를 구성 하 고 사용 하도록 설정 하려면 다음 cmdlet을 사용 합니다.

| 은| 설명|
| :-----------------|---------------:|
| 새로운 CsCloudCallDataConnection | 온라인 데이터 수집기를 설정 하는 온라인 cmdlet.|
| Get-CsCloudCallDataConnection | 기존 온라인 데이터 수집기를 검색 하는 온라인 cmdlet입니다.|  
| Get-CsCloudCallDataConnector | CsCloudCallDataConnection cmdlet에서 만든 연결 정보를 검색 하는 온-프레미스 cmdlet입니다. |
| Set-CsCloudCallDataConnector | CsCloudCallDataConnection cmdlet에서 만든 연결 정보의 온-프레미스 복사본을 저장 하는 온-프레미스 cmdlet. |  
| Set-CsCloudCallDataConnectorConfiguration | 커넥터를 사용 하거나 사용 하지 않도록 설정 하 고 범위 수준을 사용자 지정할 수 있는 온-프레미스 cmdlet.|

> [!NOTE]
> 구성을 지우고 다시 시작 하려면 제거-csclouddat연결할 구성 cmdlet을 사용 하세요.

### <a name="configure-your-environment"></a>환경 구성 

온라인 데이터 수집기를 사용 하도록 환경을 구성 하려면 먼저 비즈니스용 Skype Online PowerShell에 관리자로 로그인 해야 합니다. 자세한 내용은 [Office 365 PowerShell을 사용 하 여 비즈니스용 Skype Online 관리](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)를 참조 하세요.

비즈니스용 Skype Online PowerShell에 로그인 하는 방법에는 다음 두 가지가 있습니다.

- 비즈니스용 Skype 서버 2019 관리 셸에서 (권장 방법)
- 다른 PowerShell 세션에서

#### <a name="log-in-to-skype-for-business-online-powershell-from-the-skype-for-business-server-management-shell-recommended-method"></a>비즈니스용 Skype 서버 관리 셸에서 비즈니스용 Skype Online PowerShell에 로그인 (권장 방법)

1. 커넥터를 처음 사용 하는 경우 다음 명령을 실행 합니다.

   ```
   New-CsCloudCallDataConnection | Set-CsCloudCallDataConnector -TenantId <tenant_id>
   ```

2. 연결이 이미 존재 한다는 오류가 표시 되 면 테 넌 트에 대 한 통화 데이터 연결이 이미 있는 것입니다. 이 경우 다음 명령을 실행 합니다. 

   ```
   Get-CsCloudCallDataConnection | Set-CsCloudCallDataConnector -TenantId <tenant_id>
   ```


#### <a name="log-in-to-skype-for-business-online-powershell-from-another-powershell-session-optional-method"></a>다른 PowerShell 세션에서 비즈니스용 Skype Online PowerShell에 로그인 (선택 방법)

1.  커넥터를 처음 사용 하는 경우 다음 명령을 실행 합니다. 

    ``` 
    New-CsCloudCallDataConnection 
    ```

2.  연결이 이미 존재 한다는 오류가 표시 되 면 테 넌 트에 대 한 통화 데이터 연결이 이미 있는 것입니다. 이 경우 다음 명령을 실행 합니다. 

    ```
    Get-CsCloudCallDataConnection  
    ```

위의 명령 출력에는 온-프레미스 환경을 다음과 같이 구성할 때 필요한 토큰 값이 포함 됩니다.

비즈니스용 Skype 서버 관리 셸에서는 다음 명령을 지정 합니다.

```
Set-CsCloudCallDataConnector -Identity Global -TenantId <tenant_id> -Token <token-copied-from-online>
```

### <a name="configure-the-scope"></a>범위 구성

비즈니스용 Skype 서버 관리 셸에서 CsCloudCallDataConnectorConfiguration cmdlet을 사용 하 여 특정 사이트 또는 전체 비즈니스용 Skype 서버 배포에 대 한 통화 데이터 커넥터를 사용 하도록 설정할 수 있습니다. 예를 들어 다음 명령은 전역 범위에서 Call 데이터 커넥터를 사용 하도록 설정 합니다.

```
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $True
```

전역 설정 외에도, 통화 데이터 커넥터 구성 설정을 사이트 범위에 할당할 수 있습니다. 이렇게 하면 모니터링할 때 추가적으로 관리 유연성을 제공할 수 있습니다. 예를 들어 관리자는 다음 예제와 같이 Redmond 사이트에 대 한 통화 데이터 커넥터 전달을 활성화할 수 있지만, 더블린 사이트에 대 한 Call Data 커넥터 전달은 사용 하지 않도록 설정 합니다.

```
Set-CsCloudCallDataConnectorConfiguration -Identity "site:Redmond" -EnableCallDataConnector $True
```

```
Set-CsCloudCallDataConnectorConfiguration -Identity "site:Dublin" -EnableCallDataConnector $False
```

사이트 범위에서 구성 된 설정은 전역 범위에서 구성 된 설정 보다 우선 합니다. 예를 들어 통화 데이터 커넥터 전달은 전역 범위에서 사용 하도록 설정 되어 있지만 사이트 범위 (Redmond 사이트의 경우)에서는 사용할 수 없습니다. 이는 Redmond 사이트의 사용자에 대해 통화 정보 기록 및 체감 품질 정보를 전달 하지 않는 것을 의미 합니다. 그러나 다른 사이트 (즉, Redmond 사이트 설정 대신 전역 설정으로 관리 되는 사용자)의 사용자에 게는 통화 정보 기록 및 체감 품질 정보가 전달 됩니다.

Call 데이터 커넥터에서 사용 하는 가장 일반적으로 사용 되는 설정 값은 다음 표에 나와 있습니다.  

|속성|설명|기본값|
|:-----|:-----|:-----|
|EnableCallDataConnector  <br/> |Call Data 커넥터를 사용할 수 있는지 여부를 나타냅니다. True 인 경우 모니터링 레코드는 온라인 모니터링으로 전달 됩니다.  <br/> |$False  <br/> |
| Identity | 명령에 대 한 범위 수준을 전역 또는 사이트 중에서 결정 합니다.   | 전체적  |

## <a name="disable-call-data-connector"></a>Call Data Connector 사용 안 함

Call Data Connector를 사용 하지 않도록 설정 하면 프런트 엔드 풀의 모니터링 저장소는 연결 되지 않으며, 백엔드 모니터링 데이터베이스에 대 한 제거 또는 다른 영향을 받지 않습니다. 통화 데이터 커넥터를 사용 하지 않도록 설정 하면 비즈니스용 Skype 서버가 클라우드에 대 한 통화 데이터를 업로드 하지 않습니다. 

비즈니스용 Skype Server management shell 내에서 CsCloudCallDataConnectorConfiguration cmdlet을 사용 하 여 통화 데이터 커넥터를 사용 하지 않도록 설정 합니다. 예를 들어 다음 명령은 EnableCallDataConnector 속성을 $False로 설정 하 여 전역 범위에서 Call 데이터 커넥터를 비활성화 합니다.

```
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $False
```

클라우드에 통화 데이터 업로드를 다시 시작 하려면 다음 예제와 같이 EnableCallDataConnector 속성을 다시 $True으로 설정 합니다.

```
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $True
```

## <a name="view-on-premises-data-through-the-online-dashboard"></a>온라인 대시보드를 통해 온-프레미스 데이터 보기

 통화 데이터 커넥터를 사용 하도록 설정한 후에는 통화 분석 대시보드에서의 온-프레미스 호출 데이터를 사용 하 여 콜 분석 대시보드의 통화 품질 대시보드에서 [문제 해결](https://docs.microsoft.com/skypeforbusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality) 에 대 한 자세한 음질을 확인 하 고 [통화 품질 대시보드를 켜고 사용할 수 있습니다. Microsoft 팀 및 비즈니스용 Skype Online](/MicrosoftTeams/turning-on-and-using-call-quality-dashboard).

## <a name="for-more-information"></a>자세한 내용은

Cmdlet에 대 한 자세한 내용은 비즈니스용 Skype 서버 관리 셸에서의 Get-help-Help 명령을 사용 하면 됩니다. 예를 들면 다음과 같습니다.

Get-help 가져오기-CsCloudCallDataConnector | 자세한

Get-help 설정-CsCloudCallDataConnector | 자세한

Get-help 설정-CsCloudCallDataConnectorConfiguration | 자세한
