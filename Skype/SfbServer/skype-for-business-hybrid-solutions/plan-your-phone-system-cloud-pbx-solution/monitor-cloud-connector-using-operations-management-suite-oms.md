---
title: 운영 관리 제품군(OMS)을 사용하여 클라우드 커넥터 모니터링
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/31/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: edf4a04c-d4c9-4c05-aacc-9e084618bb55
description: 이 항목을 읽고 Microsoft OMS(Operations Management Suite)를 사용하여 클라우드 커넥터 버전 2.1 이상 배포를 모니터링하는 방법을 설명합니다.
ms.openlocfilehash: eca2f56bf564e376717a42bd8d297710905f8dc6
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359094"
---
# <a name="monitor-cloud-connector-using-operations-management-suite-oms"></a>운영 관리 제품군(OMS)을 사용하여 클라우드 커넥터 모니터링

> [!Important]
> Cloud Connector Edition은 2021년 7월 31일 비즈니스용 Skype Online과 함께 사용 중지됩니다. 조직이 Teams로 업그레이드한 후 직접 라우팅을 사용하여 프레미스 전화 통신 네트워크를 Teams에 연결하는 [방법을 배워야 합니다.](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)

이 항목을 읽고 Microsoft OMS(Operations Management Suite)를 사용하여 클라우드 커넥터 버전 2.1 이상 배포를 모니터링하는 방법을 설명합니다.

이제 Microsoft 클라우드 IT 관리 솔루션인 OMS(Operations Management Suite)를 사용하여 클라우드 커넥터 버전 2.1 이상 배포를 모니터링할 수 있습니다. OMS Log Analytics를 사용하면 실제 및 가상 컴퓨터를 비롯한 리소스의 가용성 및 성능을 모니터링하고 분석할 수 있습니다. OMS 및 Log Analytics에 대한 자세한 내용은 [OMS(Operations Management Suite)란?](https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-overview)

이 항목에는 다음 섹션이 포함되어 있습니다.

- 필수 구성 요소

- OMS를 사용하도록 클라우드 커넥터 구성

- OMS 구성

- Log Analytics 리포지토리의 경고 분석

- 권장 모니터링 집합

## <a name="prerequisites"></a>필수 구성 요소

OMS를 사용하여 클라우드 커넥터 배포를 모니터링하려면 다음이 필요합니다.

- **Azure 계정 및 OMS 작업 영역** Azure 계정이 없는 경우 OMS Log Analytics를 사용할 계정을 만들어야 합니다. Azure 계정을 만들고 OMS 작업 영역 설정하는 방법에 대한 자세한 내용은 Log Analytics 작업 영역 시작을 [참조하세요.](https://docs.microsoft.com/azure/log-analytics/log-analytics-get-started)

- **클라우드 커넥터 버전 2.1 이상**

- **Log Analytics는** 클라우드 커넥터 모니터링에 새 로그 검색이 필요합니다. 자세한 내용은 Azure Log Analytics 작업 영역의 새 로그 검색 [업그레이드를 참조하세요.](https://docs.microsoft.com/azure/log-analytics/log-analytics-log-search-upgrade)

## <a name="configure-cloud-connector-to-use-oms"></a>OMS를 사용하도록 클라우드 커넥터 구성

OMS를 사용하도록 클라우드 커넥터를 구성해야 합니다. 이렇게하려면 다음과 같이 OMS 포털을 사용하여 찾을 수 있는 OMS 작업 영역 ID와 키가 필요합니다. 설정 - 연결된 원본 \> - \> Windows Server:

![클라우드 커넥터 OMS 스크린샷](../../media/a4bb0a96-c940-435e-a3f5-5ef3062dea83.png)

OMS를 사용하도록 클라우드 커넥터를 구성하는 방법은 시나리오에 따라 다릅니다.

- **새 Cloud Connector** 어플라이언스를 설치하거나 어플라이언스를 다시 배포하려는 경우 Install-CcAppliance를 실행하기 전에 다음 단계를 수행합니다.

    1. [common] CloudConnector.ini 파일에서 OMSEnabled 매개 변수를 True로 설정하십시오.

        클라우드 커넥터를 배포하거나 업그레이드할 때마다 OMS 에이전트를 VM에 자동으로 설치하려고 시도합니다. OMS 에이전트가 클라우드 커넥터 자동 업데이트에서 남을 수 있도록 이 기능을 사용하도록 설정하십시오.

    2. OMS ID 및 키를 구성하려면 Set-CcCredential -AccountType OMSWorkspace를 실행합니다. 

- **기존 Cloud Connector 어플라이언스에 OMS** 에이전트를 설치하는 경우 다음 단계를 수행합니다.

    1. [common] CloudConnector.ini 파일에서 OMSEnabled=true를 설정하십시오. 

    2. Import-CcConfiguration을 실행합니다. 

    3. Install-CcOMSAgent를 실행합니다. 

        > [!NOTE]
        > OMSWorkspace 자격 증명을 설정하지 않은 경우 install-CcOMSAgent를 실행할 때 자격 증명을 입력하라는 메시지가 표시될 수 있습니다. 

- **이미 OMS 에이전트를 설치한 클라우드 커넥터 어플라이언스에서 OMS 작업 영역 ID 또는 키를 업데이트하려는 경우:**

    1. OMS ID 및 키를 구성하려면 Set-CcCredential -AccountType OMSWorkspace를 실행합니다. 

    2. 업데이트를 적용하려면 Install-CcOMSAgent를 실행합니다. 

- **모든 시나리오에서 에이전트가 다음과 같이 연결되어 있는지 확인해야 합니다.**

    OMS 포털에서 설정 - 연결된 원본 \> - \> Windows Server로 이동합니다. 연결된 컴퓨터 목록이 표시됩니다. 

## <a name="configure-oms"></a>OMS 구성

다음으로 OMS 포털을 사용하여 OMS 구성을 지정해야 합니다. 특히 다음이 필요합니다.

- 이벤트 로그 및 성능 카운터에 대한 정보를 지정합니다.

- 알림을 만들 수 있습니다. 

### <a name="specify-information-about-event-logs-and-performance-counters"></a>이벤트 로그 및 성능 카운터에 대한 정보 지정

OMS 포털에서 다음과 같이 이벤트 로그 및 성능 카운터에 대한 정보를 지정해야 합니다.

1. 설정 - 데이터- Windows 이벤트 로그로 이동하고 \> \> 다음에 대한 이벤트 로그를 추가합니다. 

   - Lync Server

   - 응용 프로그램

     > [!NOTE]
     > 텍스트 상자에 Lync Server를 수동으로 입력해야 합니다. 드롭다운 목록에는 옵션으로 나타나지 않습니다. 

     자세한 내용은 Log Analytics에서 Windows 이벤트 [로그 데이터 원본을 참조하세요.](https://docs.microsoft.com/azure/log-analytics/log-analytics-data-sources-windows-events)

2. 설정 - 데이터- Windows 성능 카운터로 이동한 후 다음에 대한 성능 \> \> 카운터를 추가합니다. 

   - **OS 수준 카운터.** 프로세서 사용량, 메모리 사용량, 네트워크 사용량 등의 OS 수준 카운터를 추가하거나 카운터를 명시적으로 추가하지 않고 용량 및 성능, 네트워크 성능 모니터 등의 기존 솔루션을 사용할 수 있습니다. 모니터링하기로 결정한 방식에 상관없이 Microsoft는 이러한 OS 카운터를 모니터링하는 것이 좋습니다.

   - **비즈니스용 Skype 카운터.** 비즈니스용 Skype에서 제공하는 카운터는 매우 다양합니다. 중재 서버에 로그온하고 성능 모니터를 열면 이러한 카운터를 찾을 수 있습니다. 이러한 카운터는 "LS:"로 시작됩니다. 최소한 다음 용량 카운터로 시작하고 관심 있는 다른 카운터를 추가하는 것이 좋습니다.

     총 활성 통화 수:

       - LS:MediationServer - 인바운드 통화(_Total) \- 현재 

       - LS:MediationServer - 아웃바운드 통화(_Total) \- 현재 

     총 활성 미디어 우회 통화:

       - LS:MediationServer - 인바운드 통화(_Total) \- 활성 미디어 우회 통화 

       - LS:MediationServer - 아웃바운드 통화(_Total) \- 활성 미디어 우회 통화 

     > [!NOTE]
     > 텍스트 상자에 성능 카운터를 수동으로 입력해야 합니다. 드롭다운 목록에 옵션으로 나타나지 않습니다. 

     자세한 내용은 Log Analytics에서 Windows 및 Linux 성능 데이터 [원본을 참조하세요.](https://docs.microsoft.com/azure/log-analytics/log-analytics-data-sources-performance-counters)

### <a name="create-alerts"></a>경고 만들기

OMS에는 결과 경고의 수와 메트릭 측정 경고의 두 가지 유형이 있습니다. 경고를 만드는 데 대한 자세한 내용은 Log Analytics에서 경고 [규칙 사용을 참조하세요.](https://docs.microsoft.com/azure/log-analytics/log-analytics-alerts-creating)

경고를 만들 때 다음을 고려해야 합니다.

- 알림이 결과 수 알림(기본 선택)으로 설정되어 있는지 확인 

- 데모 쿼리를 사용하려면 "결과 수"가 "0보다 크다"로 설정되어 있습니다. 

- 시간 창과 경고 빈도를 모두 5분으로 설정하는 것이 좋습니다. 

- 데모 경고에 대해 "경고 표시 안 하도록 설정"을 설정하지 않는 것이 좋습니다. 

- 일반적인 경고 시나리오의 경우 한 쌍의 경고(오류 경고 1개와 재설정 경고 1개)를 만드는 것이 좋습니다. 오류 경고의 경우 심각도 수준 중요를 선택합니다. 다시 설정 경고의 경우 심각도 수준 정보.를 선택합니다.

다음 섹션에서는 예제 경고를 만드는 방법을 설명합니다.

 **경고 쌍 만들기: "RTCMEDSRV가 중재 서버에서 실행되고 있지 않습니다." 및 "RTCMEDSRV가 다시 중재 서버에서 실행 중입니다."**

이 경고 쌍을 만들 수 있습니다.

- 오류 경고에 대한 쿼리는 다음을 실행합니다.

  ```Kusto
  Event | where Computer contains "MediationServer" | where EventLog == "Lync Server" and (EventID == 25002 or EventID == 25003)  | summarize arg_max(TimeGenerated, EventID) by Computer | where EventID == 25003
  ```

    쿼리는 컴퓨터에  *"MediationServer"가*  포함된 컴퓨터 필터를 사용합니다. 필터는 이름에 문자열 "MediationServer"가 포함된 컴퓨터만 선택합니다.

     필터를 자체 컴퓨터 필터로 바꾸거나 간단히 제거하면 됩니다. 정규식 없이 복잡한 문자열 필터를 만들 수 있습니다. 자세한 내용은 [String 연산자를 참조하십시오.](https://docs.loganalytics.io/docs/Language-Reference/Scalar-operators/String-operators) 또한 정규식을 사용할 수 있습니다. 또한 검색 쿼리를 저장하고 해당 그룹을 경고 쿼리에서 컴퓨터 필터로 사용하여 컴퓨터 그룹을 만들 수 있습니다. 자세한 내용은 Log Analytics 로그 검색의 [컴퓨터 그룹을 참조하세요.](https://docs.microsoft.com/azure/log-analytics/log-analytics-computer-groups)

    각 컴퓨터에 대해 오류 쿼리는 RTCMEDSRV 서비스 시작 및 서비스 중지 둘 다에 대한 마지막 이벤트 로그를 얻습니다. 마지막 이벤트가 서비스 중지 이벤트인 경우 로그가 하나 반환됩니다. 마지막 이벤트가 서비스 시작 이벤트인 경우 아무 것도 반환하지 않습니다. 즉, 쿼리는 시간 창에서 RTCMEDSRV가 중지된 서버 목록을 반환합니다. 

- 다시 설정 경고에 대한 쿼리는 다음을 실행합니다.

  ```Kusto
  Event | where Computer contains "MediationServer" | where EventLog == "Lync Server" and (EventID == 25002 or EventID == 25003) | summarize arg_max(TimeGenerated, EventID) by Computer  | where EventID == 2500
  ```

    다시 설정 쿼리는 오류 쿼리와 정확히 반대입니다. 각 컴퓨터에 대해 마지막 이벤트가 서비스 시작 이벤트인 경우 1이 반환됩니다. 마지막 이벤트가 서비스 중지 이벤트인 경우 아무 것도 반환하지 않습니다.

**경고 쌍 만들기: "중재 서버에서 동시 통화 수가 너무 많지 않습니다." 및 "동시 통화가 정상 부하로 되돌아가기"**

이 경고를 만들 수 있는 경우:

- 오류 경고에 대한 쿼리는 다음을 실행합니다.

  ```Kusto
  Perf | where Computer contains "MediationServer" | where (ObjectName == "LS:MediationServer - Outbound Calls" or ObjectName == "LS:MediationServer - Inbound Calls") | summarize arg_max(TimeGenerated, CounterValue) by ObjectName, Computer | summarize  TotalCalls = sum(CounterValue) by Computer| where TotalCalls >= 500
  ```

    각 컴퓨터에 대해 쿼리는 인바운드 통화 및 아웃바운드 통화에 대한 마지막 카운터를 구하고 이러한 두 값을 합산합니다. 합계 값이 500을 초과하면 로그가 하나 반환됩니다. 그렇지 않은 경우 아무 것도 반환하지 않습니다. 즉, 쿼리는 동시 호출이 시간 창에서 너무 많은 서버 목록을 반환합니다.

- 다시 설정 경고에 대한 쿼리는 다음을 실행합니다.

  ```Kusto
  Perf  | where Computer contains "MediationServer" | where (ObjectName == "LS:MediationServer - Outbound Calls" or ObjectName ==  "LS:MediationServer - Inbound Calls") | summarize arg_max(TimeGenerated, CounterValue) by ObjectName, Computer | summarize  TotalCalls = sum(CounterValue) by Computer| where TotalCalls < 500
  ```

    다시 설정 쿼리는 오류 쿼리와 정확히 반대입니다. 각 컴퓨터에 대해 쿼리는 인바운드 통화 및 아웃바운드 통화에 대한 마지막 카운터를 구하고 이러한 두 값을 합산합니다. 합계 값이 500보다 작은 경우 하나의 로그가 반환됩니다. 그렇지 않으면 아무 것도 반환하지 않습니다.

**경고 만들기: "서버에서 CPU 사용량 \> 90 또는 RTCMEDIARELAY 중지됨" 경고**

이 경고를 만들 때 쿼리는 다음을 실행합니다.

```Kusto
search *| where Computer contains "MediationServer" | where (Type == "Perf" or Type == "Event") | where ((ObjectName ==  "Processor" and CounterName == "% Processor Time") or EventLog == "Lync Server") | where (CounterValue > 90 or EventID == 22003)
```

쿼리는 모든 컴퓨터에서 모든 프로세서 사용 카운터 및 서비스 중지 이벤트를 반환하고 프로세서 사용량이 90%를 초과하거나 서비스가 중지된 경우 하나의 로그를 반환합니다. 

## <a name="analyze-the-alerts-in-your-log-analytics-repository"></a>Log Analytics 리포지토리의 경고 분석

리포지토리에서 경고를 분석하기 위해 경고 관리 솔루션을 사용 합니다. 자세한 내용은 [OMS(Operations Management Suite)의 경고 관리](https://docs.microsoft.com/azure/log-analytics/log-analytics-solution-alert-management) 솔루션을 참조하십시오.

## <a name="recommended-minimal-monitoring-set"></a>권장되는 최소 모니터링 집합

이벤트 로그 및 성능 카운터 관련 문제를 식별하려면 

- **이벤트 로그입니다.** 모든 문제의 경우 이벤트 쌍이 하나씩 표시되어 잘못된 것을 나타내고 다른 하나는 모든 것이 양호하다는 것을 나타냅니다. 특정 기간에 대해 기록된 마지막 이벤트로, 해당 기간에 대한 아미스인지 여부를 나타냅니다.

- **성능 카운터.** 모니터링되는 카운터에 대한 임계값이 있습니다.

다음 표에는 중지 및 시작 이벤트 ID를 나열하여 Microsoft에서 모니터링을 권장하는 서비스가 나열됩니다.

|서비스 이름  <br/> |대상 서버 역할  <br/> |중지 이벤트 ID  <br/> |시작 이벤트 ID  <br/> |
|:-----|:-----|:-----|:-----|
|RTCMEDSRV  <br/> |중재 서버  <br/> |25003  <br/> |25002  <br/> |
|RTCSRV  <br/> |에지 서버  <br/> |12289  <br/> |12288  <br/> |
|RTCMRAUTH  <br/> |에지 서버  <br/> |19003  <br/> |19002  <br/> |
|RTCMEDIARELAY  <br/> |에지 서버  <br/> |22003  <br/> |22002  <br/> |

다음 표에는 Microsoft에서 모니터링을 권장하는 네트워크 문제가 나열됩니다.


| 모니터 이름  <br/>                                        | 대상 서버 역할  <br/> | Success 이벤트 ID 식  <br/> | 오류 이벤트 ID 식  <br/> | 오류 예제  <br/> |
|:-----------------------------------------------------------|:--------------------------|:-----------------------------------|:---------------------------------|:-----------------------|
| 게이트웨이 연결 오류에 대한 중재 서버  <br/>    | 중재 서버  <br/>   | 25062                              |                                  | 25002  <br/>           |
| 게이트웨이 호출 완료 오류에 대한 중재 서버  <br/> | 중재 서버  <br/>   | 25064                              |                                  | 25002  <br/>           |
| 중요한 네트워크 문제  <br/>                           | 에지 서버  <br/>        | 14353                              |                                  | 12288  <br/>           |

다음은 모니터링해야 하는 통화 용량 카운터를 나열하는 예제입니다. 이러한 숫자는 Cloud Connector Standard Edition의 경우 500보다 작아야 합니다. Cloud Connector 최소 버전은 50 미만입니다.

- LS:MediationServer - 인바운드 통화(_Total) \- 현재 

- LS:MediationServer - 아웃바운드 통화(_Total) \- 현재 

- LS:MediationServer - 인바운드 통화(_Total) \- 활성 미디어 우회 통화

- LS:MediationServer - 아웃바운드 통화(_Total) \- 활성 미디어 우회 통화

## <a name="see-also"></a>참고 항목

OMS 사용에 대한 자세한 내용은 다음을 참조하세요.

- [Log Analytics에서 로그 검색을 사용하여 데이터 찾기](https://docs.microsoft.com/azure/log-analytics/log-analytics-log-searches)

- [Azure Log Analytics 언어 참조](https://docs.loganalytics.io/docs/Language-Reference)

- [Log Analytics의 경고 이해](https://docs.microsoft.com/azure/log-analytics/log-analytics-alerts)

- [Azure의 Log Analytics 서비스에 Windows 컴퓨터 연결](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents)


