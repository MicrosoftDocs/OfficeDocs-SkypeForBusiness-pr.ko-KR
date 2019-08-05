---
title: OMS (Operations Management Suite)를 사용 하 여 클라우드 커넥터 모니터링
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/31/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: edf4a04c-d4c9-4c05-aacc-9e084618bb55
description: 이 항목에서는 Microsoft OMS (Operations Management Suite)를 사용 하 여 클라우드 커넥터 버전 2.1 및 이후 배포를 모니터링 하는 방법을 알아봅니다.
ms.openlocfilehash: 6258ad9386b895f97a6f6dc0a1b40ce1076568aa
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190728"
---
# <a name="monitor-cloud-connector-using-operations-management-suite-oms"></a>OMS (Operations Management Suite)를 사용 하 여 클라우드 커넥터 모니터링

이 항목에서는 Microsoft OMS (Operations Management Suite)를 사용 하 여 클라우드 커넥터 버전 2.1 및 이후 배포를 모니터링 하는 방법을 알아봅니다.

이제 OMS (Operations Management Suite), Microsoft 클라우드 IT 관리 솔루션을 사용 하 여 클라우드 커넥터 버전 2.1 및 이후 배포를 모니터링할 수 있습니다. OMS 로그 분석 기능을 사용 하면 실제 및 가상 컴퓨터를 비롯 한 리소스의 가용성과 성능을 모니터링 하 고 분석할 수 있습니다. OMS 및 로그 분석에 대 한 자세한 내용은 [Operations Management Suite (OMS) 란?](https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-overview)을 참조 하세요.

이 항목에서는 다음 섹션을 다룹니다.

- 필요 조건

- OMS를 사용 하도록 클라우드 커넥터 구성

- OMS 구성

- 로그 분석 리포지토리에서 알림 분석

- 권장 되는 모니터링 설정

## <a name="prerequisites"></a>필요 조건

OMS를 사용 하 여 클라우드 커넥터 배포를 모니터링할 수 있으려면 먼저 다음이 필요 합니다.

- **Azure 계정 및 OMS 작업 영역** Azure 계정이 없는 경우에는 OMS 로그 분석을 사용 하는 계정 중 하나를 만들어야 합니다. Azure 계정을 만들고 OMS 작업 영역을 설정 하는 방법에 대 한 자세한 내용은 [로그 분석 작업 영역 시작](https://docs.microsoft.com/azure/log-analytics/log-analytics-get-started)을 참조 하세요.

- **클라우드 커넥터 버전 2.1 이상**

- 클라우드 커넥터 모니터링을 위해서는 **로그 분석에서 새 로그 검색이** 필요 합니다. 자세한 내용은 [Azure Log Analytics 작업 영역을 새 로그 검색으로 업그레이드를](https://docs.microsoft.com/azure/log-analytics/log-analytics-log-search-upgrade)참조 하세요.

## <a name="configure-cloud-connector-to-use-oms"></a>OMS를 사용 하도록 클라우드 커넥터 구성

OMS를 사용 하려면 클라우드 커넥터 온-프레미스 환경을 구성 해야 합니다. 이렇게 하려면 oms 포털을 사용 하 여 찾을 수 있는 OMS 작업 영역 ID 및 키가 필요 합니다. 설정--\>연결 된 원본--\> Windows server:

![클라우드 커넥터 OMS에 대 한 스크린샷](../../media/a4bb0a96-c940-435e-a3f5-5ef3062dea83.png)

OMS를 사용 하도록 클라우드 커넥터를 구성 하는 방법은 시나리오에 따라 다릅니다.

- **새 클라우드 커넥터 기기를 설치 하거나 기기를 다시 배포 하려는 경우**설치-ccappliance를 실행 하기 전에 다음 단계를 수행 합니다.

1. CloudConnector .ini 파일 [일반] 구역에서 OMSEnabled 매개 변수를 True로 설정 합니다.

    클라우드 커넥터를 배포 하거나 업그레이드할 때마다 자동으로 Vm에 OMS 에이전트를 설치 하려고 시도 합니다. 이 기능을 사용 하도록 설정 하면 OMS 에이전트가 클라우드 커넥터 자동 업데이트를 계속 사용할 수 있습니다.

2. OMS ID 및 키를 구성 하려면 Set-CcCredential-AccountType OMSWorkspace를 실행 합니다. 

- **OMS 에이전트를 기존 클라우드 커넥터 기기에 설치 하는 경우**다음 단계를 따릅니다.

1. CloudConnector .ini 파일 [일반] 구역에서 OMSEnabled = true로 설정 합니다. 

2. 가져오기-CcConfiguration을 실행 합니다. 

3. 설치-CcOMSAgent를 실행 합니다. 

    > [!NOTE]
    > OMSWorkspace 자격 증명을 설정 하지 않은 경우 CcOMSAgent를 실행할 때 자격 증명을 입력 하 라는 메시지가 표시 됩니다. 

- **OMS 에이전트를 이미 설치한 클라우드 커넥터 기기에서 OMS 작업 영역 ID 또는 키를 업데이트 하려면 다음을 수행 합니다.**

1. OMS ID 및 키를 구성 하려면 Set-CcCredential-AccountType OMSWorkspace를 실행 합니다. 

2. 업데이트를 적용 하려면 설치-CcOMSAgent를 실행 합니다. 

- **모든 시나리오의 경우 다음과 같이 에이전트가 연결 되어 있는지 확인 합니다.**

    OMS 포털에서 설정-\> 연결 된 원본-\> Windows 서버로 이동 합니다. 연결 된 컴퓨터 목록이 표시 됩니다. 

## <a name="configure-oms"></a>OMS 구성

다음에는 OMS 포털을 사용 하 여 OMS 구성을 지정 해야 합니다. 구체적으로 다음과 같은 작업을 수행 해야 합니다.

- 이벤트 로그 및 성능 카운터에 대 한 정보를 지정 합니다.

- 알림을 만듭니다. 

### <a name="specify-information-about-event-logs-and-performance-counters"></a>이벤트 로그 및 성능 카운터에 대 한 정보 지정

OMS 포털에서 다음과 같이 이벤트 로그 및 성능 카운터에 대 한 정보를 지정 해야 합니다.

1. 설정-\>데이터-\>Windows 이벤트 로그로 이동 하 여 다음에 대 한 이벤트 로그 추가: 

   - Lync Server

   - 프로그램

     > [!NOTE]
     > 텍스트 상자에 Lync Server를 수동으로 입력 해야 합니다. 드롭다운 목록에 옵션으로 표시 되지 않습니다. 

     자세한 내용은 [로그 분석에서 Windows 이벤트 로그 데이터 원본](https://docs.microsoft.com/azure/log-analytics/log-analytics-data-sources-windows-events) 을 참조 하세요.

2. 설정-\>데이터-\> Windows 성능 카운터로 이동 하 여 다음에 대 한 성능 카운터를 추가 합니다. 

   - **OS 수준 카운터**입니다. 프로세서 사용량, 메모리 사용량, 네트워크 사용량 등 OS 수준 카운터를 추가 하거나 카운터를 명시적으로 추가 하지 않고 용량 및 성능, 네트워크 성능 모니터 등의 기존 솔루션을 사용할 수 있습니다. 모니터링 하기로 결정 한 방법에 관계 없이 이러한 OS 카운터를 모니터링 하는 것이 좋습니다.

   - **비즈니스용 Skype 카운터**. 비즈니스용 Skype에서 제공 하는 여러 가지 카운터가 있습니다. 중재 서버에 로그온 하 고 성능 모니터를 열면 이러한 카운터를 찾을 수 있습니다. 이러한 카운터는 "LS:"로 시작 합니다. 최소한 다음 용량 카운터를 사용 하 여 작업을 시작 하 고 관심 있는 나머지를 추가 하는 것이 좋습니다.

     총 활성 통화:

   - LS: MediationServer-인바운드 통화 (_Total)\- 현재 

   - LS: MediationServer-아웃 바운드 통화 (_Total\- ) 전류 

     총 활성 미디어 바이패스 통화:

   - LS: MediationServer-인바운드 통화 (_Total)\- 액티브 미디어 건너뛰기 통화 

   - LS: MediationServer-아웃 바운드 통화 (_Total\- ) 액티브 미디어 건너뛰기 통화 

     > [!NOTE]
     > 텍스트 상자에 성능 카운터를 수동으로 입력 해야 합니다. 드롭다운 목록에 옵션으로 표시 되지 않습니다. 

     자세한 내용은 [로그 분석에서 Windows 및 Linux 성능 데이터 원본을](https://docs.microsoft.com/azure/log-analytics/log-analytics-data-sources-performance-counters) 참조 하세요.

### <a name="create-alerts"></a>알림 만들기

OMS에는 여러 가지 유형의 경고가 표시 됩니다 (결과 경고 수 및 미터법 단위 알림). 알림을 만드는 방법에 대 한 자세한 내용은 [로그 분석에서 알림 규칙 작업](https://docs.microsoft.com/azure/log-analytics/log-analytics-alerts-creating)을 참조 하세요.

알림을 만들 때 다음 사항을 고려해 야 합니다.

- 알림이 기본 선택 인 결과를 숫자로 표시 하는 알림 인지 확인 합니다. 

- 데모 쿼리에는 "결과 개수"가 "0 보다 큼"으로 설정 되어 있어야 합니다. 

- 시간 창과 알림 빈도를 5 분으로 설정 하는 것이 좋습니다. 

- 데모 알림에서 "경고 표시 안 함"을 사용 하도록 설정 하지 않는 것이 좋습니다. 

- 일반적인 알림 시나리오의 경우 하나의 오류 알림 및 한 번의 재설정 알림을 만드는 것이 좋습니다. 오류 경고의 경우 심각도 (위험 수준)를 선택 합니다. 다시 설정 알림에 대해 심각도 수준 정보를 선택 합니다.

다음 섹션에서는 예제 알림을 만드는 방법에 대해 설명 합니다.

 **"RTCMEDSRV는 중재 서버에서 실행 되 고 있지 않음" 및 "RTCMEDSRV는 중재 서버에서 실행 되 고 있습니다." 라는 경고 쌍을 만듭니다.**

이 알림 쌍을 만들려면 다음을 수행 합니다.

- 오류 경고에 대 한 쿼리는 다음과 같습니다.

  ```
  Event | where Computer contains "MediationServer" | where EventLog == "Lync Server" and (EventID == 25002 or EventID == 25003)  | summarize arg_max(TimeGenerated, EventID) by Computer | where EventID == 25003
  ```

    이 쿼리는 *컴퓨터에 "MediationServer"가 포함* 된 컴퓨터 필터를 사용 합니다. 필터는 이름에 문자열 "MediationServer"가 포함 되어 있는 컴퓨터만 선택 합니다.

     필터를 자신의 컴퓨터 필터로 바꾸거나 제거 하면 됩니다. 정규식 없이 복잡 한 문자열 필터를 만들 수 있습니다. 자세한 내용은 [문자열 연산자](https://docs.loganalytics.io/docs/Language-Reference/Scalar-operators/String-operators)를 참조 하세요. 정규식을 사용 하도록 선택할 수도 있습니다. 또한 검색 쿼리를 저장 하 고 해당 그룹을 컴퓨터 필터로 사용 하 여 컴퓨터 그룹을 만들 수 있습니다. 자세한 내용은 [로그 분석 로그 검색의 컴퓨터 그룹](https://docs.microsoft.com/azure/log-analytics/log-analytics-computer-groups)을 참조 하세요.

    각 컴퓨터에 대해 오류 쿼리는 RTCMEDSRV 서비스 시작 및 서비스 중지 모두에 대 한 마지막 이벤트 로그를 가져옵니다. 마지막 이벤트가 서비스 중지 이벤트 이면 하나의 로그를 반환 합니다. 마지막 이벤트가 서비스 시작 이벤트 인 경우 nothing이 반환 됩니다. 즉, 쿼리는 시간 창에서 RTCMEDSRV가 중지 된 서버 목록을 반환 합니다. 

- 다시 설정 알림에 대 한 쿼리는 다음과 같습니다.

  ```
  Event | where Computer contains "MediationServer" | where EventLog == "Lync Server" and (EventID == 25002 or EventID == 25003) | summarize arg_max(TimeGenerated, EventID) by Computer  | where EventID == 2500
  ```

    다시 설정 쿼리는 오류 쿼리의 반대 항목을 정확히 의미 합니다. 마지막 이벤트가 서비스 시작 이벤트 이면 각 컴퓨터에 대해 1이 반환 됩니다. 마지막 이벤트가 서비스 중지 이벤트 일 경우 nothing이 반환 됩니다.

  **"중재 서버에 너무 많은 동시 통화" 및 "동시 통화 정상 로드로 전환" 경고 쌍을 만듭니다.**

알림을 만들려면 다음을 실행 합니다.

- 오류 경고에 대 한 쿼리는 다음과 같습니다.

  ```
  Perf | where Computer contains "MediationServer" | where (ObjectName == "LS:MediationServer - Outbound Calls" or ObjectName == "LS:MediationServer - Inbound Calls") | summarize arg_max(TimeGenerated, CounterValue) by ObjectName, Computer | summarize  TotalCalls = sum(CounterValue) by Computer| where TotalCalls >= 500
  ```

    각 컴퓨터에 대해 쿼리는 인바운드 통화 및 발신 호출에 대 한 마지막 카운터를 가져오고 이러한 두 값의 합계를 계산 합니다. Sum 값이 500를 초과 하는 경우 1 개의 로그가 반환 됩니다. 그렇지 않으면 아무 것도 반환 되지 않습니다. 즉, 쿼리는 시간 창에 동시 호출이 너무 많은 서버 목록을 반환 합니다.

- 다시 설정 알림에 대 한 쿼리는 다음과 같습니다.

  ```
  Perf  | where Computer contains "MediationServer" | where (ObjectName == "LS:MediationServer - Outbound Calls" or ObjectName ==  "LS:MediationServer - Inbound Calls") | summarize arg_max(TimeGenerated, CounterValue) by ObjectName, Computer | summarize  TotalCalls = sum(CounterValue) by Computer| where TotalCalls < 500
  ```

    다시 설정 쿼리는 오류 쿼리의 반대 항목을 정확히 의미 합니다. 각 컴퓨터에 대해 쿼리는 인바운드 통화 및 발신 호출에 대 한 마지막 카운터를 가져오고 이러한 두 값의 합계를 계산 합니다. Sum 값이 500 보다 작으면 로그가 1 개 반환 되 고, 그렇지 않으면 아무 작업도 반환 하지 않습니다.

  **경고 만들기: "CPU 사용 \> 90 또는 RTCMEDIARELAY 중지 됨" 알림**

이 알림을 만들려면 쿼리는 다음과 같이 수행 합니다.

```
search *| where Computer contains "MediationServer" | where (Type == "Perf" or Type == "Event") | where ((ObjectName ==  "Processor" and CounterName == "% Processor Time") or EventLog == "Lync Server") | where (CounterValue > 90 or EventID == 22003)
```

쿼리는 모든 컴퓨터에서 모든 프로세서 사용 카운터 및 서비스 중지 이벤트를 받고, 프로세서 사용량이 90%를 초과 하거나 서비스가 중지 된 경우 하나의 로그를 반환 합니다. 

## <a name="analyze-the-alerts-in-your-log-analytics-repository"></a>로그 분석 리포지토리에서 알림 분석

리포지토리에서 알림을 분석 하려면 알림 관리 솔루션을 사용 합니다. 자세한 내용은 [OMS (Operations Management Suite)의 Alert Management solution](https://docs.microsoft.com/azure/log-analytics/log-analytics-solution-alert-management) 을 참조 하세요.

## <a name="recommended-minimal-monitoring-set"></a>권장 되는 최소 모니터링 집합

이벤트 로그 및 성능 카운터의 문제를 확인 하려면 다음을 수행 합니다. 

- **이벤트 로그.** 문제가 발생 하는 경우 어떤 이벤트 집합을 사용 하는 이벤트 쌍이 문제가 되는 반면 나머지는 모든 것이 잘 되었음을 나타냅니다. 지정 된 기간 동안에는 해당 기간에 대 한 amiss가 표시 될 때까지 마지막으로 기록 된 이벤트입니다.

- **성능 카운터** 모니터링 되는 카운터에 대 한 임계값이 있어야 합니다.

다음 표에는 중지 및 시작 이벤트 Id를 나열 하 여 Microsoft에서 모니터링을 권장 하는 서비스가 나와 있습니다.

|서비스 이름  <br/> |대상 서버 역할  <br/> |중지 이벤트 ID  <br/> |시작 이벤트 ID  <br/> |
|:-----|:-----|:-----|:-----|
|RTCMEDSRV  <br/> |중재 서버  <br/> |25003  <br/> |25002  <br/> |
|RTCSRV  <br/> |Edge 서버  <br/> |12289  <br/> |12288  <br/> |
|RTCMRAUTH  <br/> |Edge 서버  <br/> |19003  <br/> |19002  <br/> |
|RTCMEDIARELAY  <br/> |Edge 서버  <br/> |22003  <br/> |22002  <br/> |

다음 표에는 Microsoft에서 모니터링할 때 권장 하는 네트워크 문제가 나와 있습니다.


| 모니터 이름  <br/>                                        | 대상 서버 역할  <br/> | 성공 이벤트 ID 식  <br/> | 오류 이벤트 ID 식  <br/> | 실패 예  <br/> |
|:-----------------------------------------------------------|:--------------------------|:-----------------------------------|:---------------------------------|:-----------------------|
| 중재 서버에서 게이트웨이 연결에 실패 했습니다.  <br/>    | 중재 서버  <br/>   | 25062                              |                                  | 25002  <br/>           |
| 중재 서버에서 게이트웨이 호출 완료 실패  <br/> | 중재 서버  <br/>   | 25064                              |                                  | 25002  <br/>           |
| 심각한 네트워크 문제  <br/>                           | Edge 서버  <br/>        | 14353                              |                                  | 12288  <br/>           |

다음 목록에는 모니터링 해야 하는 통화 용량 카운터가 나와 있습니다. 이러한 번호는 클라우드 커넥터 standard edition의 500 미만 이어야 합니다. 클라우드 커넥터 최소 에디션의 50 미만

- LS: MediationServer-인바운드 통화 (_Total)\- 현재 

- LS: MediationServer-아웃 바운드 통화 (_Total\- ) 전류 

- LS: MediationServer-인바운드 통화 (_Total)\- 액티브 미디어 건너뛰기 통화

- LS: MediationServer-아웃 바운드 통화 (_Total\- ) 액티브 미디어 건너뛰기 통화

## <a name="see-also"></a>참고 항목

OMS 작업에 대 한 자세한 내용은 다음을 참고 하세요.

- [로그 분석에서 로그 검색을 사용 하 여 데이터 찾기](https://docs.microsoft.com/azure/log-analytics/log-analytics-log-searches)

- [Azure 로그 분석 언어 참조](https://docs.loganalytics.io/docs/Language-Reference)

- [로그 분석의 경고 이해](https://docs.microsoft.com/azure/log-analytics/log-analytics-alerts)

- [Azure의 Log Analytics 서비스에 Windows 컴퓨터 연결](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents)


