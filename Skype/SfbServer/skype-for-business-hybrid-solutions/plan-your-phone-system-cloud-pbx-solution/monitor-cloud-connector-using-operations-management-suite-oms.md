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
description: OMS (Microsoft Operations Management Suite)를 사용 하 여 클라우드 커넥터 버전 2.1 이상 배포를 모니터링 하는 방법을 알아보려면이 항목을 읽어 보십시오.
ms.openlocfilehash: eca2f56bf564e376717a42bd8d297710905f8dc6
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359094"
---
# <a name="monitor-cloud-connector-using-operations-management-suite-oms"></a>운영 관리 제품군(OMS)을 사용하여 클라우드 커넥터 모니터링

> [!Important]
> 클라우드 커넥터 버전은 비즈니스용 Skype Online과 함께 2021 년 7 월 31 일에 사용 중지 됩니다. 조직이 팀으로 업그레이드 된 후에는 [직접 라우팅을](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)사용 하 여 팀에 온-프레미스 전화 통신 네트워크를 연결 하는 방법을 알아보세요.

OMS (Microsoft Operations Management Suite)를 사용 하 여 클라우드 커넥터 버전 2.1 이상 배포를 모니터링 하는 방법을 알아보려면이 항목을 읽어 보십시오.

이제 OMS (Operations Management Suite), Microsoft Cloud IT Management solution을 사용 하 여 클라우드 커넥터 버전 2.1 이상 배포를 모니터링할 수 있습니다. OMS 로그 분석을 사용 하면 실제 및 가상 컴퓨터를 포함 하 여 리소스의 가용성과 성능을 모니터링 하 고 분석할 수 있습니다. OMS 및 로그 분석에 대 한 자세한 내용은 [Operations Management Suite (OMS) 란?](https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-overview) 를 참조 하세요.

이 항목에는 다음 섹션이 포함 되어 있습니다.

- 필수 구성 요소

- OMS를 사용 하도록 클라우드 커넥터 구성

- OMS 구성

- 로그 분석 리포지토리에서 경고 분석

- 권장 되는 모니터링 설정

## <a name="prerequisites"></a>필수 구성 요소

OMS를 사용 하 여 클라우드 커넥터 배포를 모니터링 하려면 먼저 다음이 필요 합니다.

- **Azure 계정 및 OMS 작업 영역** 아직 Azure 계정이 없는 경우에는 OMS 로그 분석을 사용 하는 계정 만들기를 수행 해야 합니다. Azure 계정을 만들고 OMS 작업 영역을 설정 하는 방법에 대 한 자세한 내용은 [Log Analytics 작업 영역 시작](https://docs.microsoft.com/azure/log-analytics/log-analytics-get-started)을 참조 하세요.

- **클라우드 커넥터 버전 2.1 이상**

- 로그 분석 클라우드 커넥터 모니터링에 **새 로그 검색이** 필요 합니다. 자세한 내용은 [Azure Log Analytics 작업 영역을 새 로그 검색으로 업그레이드를](https://docs.microsoft.com/azure/log-analytics/log-analytics-log-search-upgrade)참조 하세요.

## <a name="configure-cloud-connector-to-use-oms"></a>OMS를 사용 하도록 클라우드 커넥터 구성

OMS를 사용 하려면 온-프레미스 환경에서 클라우드 커넥터를 구성 해야 합니다. 이를 위해 oms 포털을 사용 하 여 찾을 수 있는 OMS 작업 영역 ID와 키 (설정-- \> 연결 원본--Windows 서버)가 필요 합니다 \> .

![클라우드 커넥터 OMS에 대 한 스크린샷](../../media/a4bb0a96-c940-435e-a3f5-5ef3062dea83.png)

OMS를 사용 하도록 클라우드 커넥터를 구성 하는 방법은 시나리오에 따라 다릅니다.

- **새 클라우드 커넥터 기기를 설치 하거나 기기를 다시 배포 하려는 경우**에는 설치-ccappliance를 실행 하기 전에 다음 단계를 수행 합니다.

    1. CloudConnector.ini 파일 [일반] 섹션에서 OMSEnabled 매개 변수를 True로 설정 합니다.

        클라우드 커넥터를 배포 하거나 업그레이드할 때마다 자동으로 해당 Vm에 OMS 에이전트를 설치 하려고 시도 합니다. 이 기능을 사용 하도록 설정 하면 OMS 에이전트가 클라우드 커넥터 자동 업데이트를 계속 사용할 수 있습니다.

    2. OMS ID 및 키를 구성 하려면 Set-CcCredential-AccountType OMSWorkspace를 실행 합니다. 

- **OMS 에이전트를 기존 클라우드 커넥터 기기에 설치 하는 경우**다음 단계를 수행 합니다.

    1. CloudConnector.ini 파일 [일반] 섹션에서 OMSEnabled = true로 설정 합니다. 

    2. 가져오기-CcConfiguration을 실행 합니다. 

    3. CcOMSAgent를 실행 합니다. 

        > [!NOTE]
        > OMSWorkspace 자격 증명을 설정 하지 않은 경우에는 CcOMSAgent를 실행할 때 자격 증명을 입력 하 라는 메시지가 표시 됩니다. 

- **OMS 에이전트를 이미 설치한 클라우드 커넥터 기기에서 OMS 작업 영역 ID 또는 키를 업데이트 하려면 다음을 수행 합니다.**

    1. OMS ID 및 키를 구성 하려면 Set-CcCredential-AccountType OMSWorkspace를 실행 합니다. 

    2. 업데이트를 적용 하려면 CcOMSAgent를 실행 합니다. 

- **모든 시나리오에 대해 에이전트가 다음과 같이 연결 되는지 확인 합니다.**

    OMS 포털에서 설정- \> 연결 된 원본- \> Windows 서버로 이동 합니다. 연결 된 컴퓨터 목록이 표시 됩니다. 

## <a name="configure-oms"></a>OMS 구성

다음으로, OMS 포털을 사용 하 여 OMS 구성을 지정 해야 합니다. 특히 다음 작업을 수행 해야 합니다.

- 이벤트 로그 및 성능 카운터에 대 한 정보를 지정 합니다.

- 알림을 만들 수 있습니다. 

### <a name="specify-information-about-event-logs-and-performance-counters"></a>이벤트 로그 및 성능 카운터에 대 한 정보 지정

OMS 포털에서 다음과 같이 이벤트 로그 및 성능 카운터에 대 한 정보를 지정 해야 합니다.

1. 설정- \> 데이터- \> Windows 이벤트 로그로 이동 하 고 다음에 대 한 이벤트 로그를 추가 합니다. 

   - Lync Server

   - 응용 프로그램

     > [!NOTE]
     > 텍스트 상자에 Lync Server를 수동으로 입력 해야 합니다. 드롭다운 목록에 옵션으로 표시 되지 않습니다. 

     자세한 내용은 [Log Analytics의 Windows 이벤트 로그 데이터 원본](https://docs.microsoft.com/azure/log-analytics/log-analytics-data-sources-windows-events) 를 참조 하세요.

2. 설정- \> 데이터- \> Windows 성능 카운터로 이동 하 고 다음에 대 한 성능 카운터를 추가 합니다. 

   - **OS 수준 카운터**입니다. 프로세서 사용량, 메모리 사용량, 네트워크 사용 등의 OS 수준 카운터를 추가 하거나, 카운터를 명시적으로 추가 하지 않고 용량 및 성능, 네트워크 성능 모니터와 같은 기존 솔루션을 사용할 수 있습니다. 모니터링을 결정 하는 방법에 관계 없이 이러한 OS 카운터를 모니터링 하는 것이 좋습니다.

   - **비즈니스용 Skype 카운터**입니다. 비즈니스용 Skype에서 제공 하는 다양 한 카운터가 있습니다. 이 카운터는 중재 서버에 로그온 하 고 성능 모니터를 여는 방법으로 찾을 수 있습니다. 이러한 카운터는 "LS:"로 시작 합니다. 최소한 다음 용량 카운터를 사용 하 여 작업을 시작 하 고 관심 있는 다른 항목을 추가 하는 것이 좋습니다.

     총 활성 통화:

       - LS: MediationServer-Inbound Calls (_Total) \- Current 

       - LS: MediationServer-아웃 바운드 호출 (_Total) \- 현재 

     총 활성 미디어 바이패스 통화:

       - LS: MediationServer-인바운드 호출 (_Total) \- 활성 미디어 바이패스 통화 

       - LS: MediationServer-아웃 바운드 호출 (_Total) \- 액티브 미디어 바이패스 통화 

     > [!NOTE]
     > 텍스트 상자에 성능 카운터를 수동으로 입력 해야 합니다. 드롭다운 목록에 옵션으로 표시 되지 않습니다. 

     자세한 내용은 [Log Analytics에서 Windows 및 Linux 성능 데이터 원본](https://docs.microsoft.com/azure/log-analytics/log-analytics-data-sources-performance-counters) 참조

### <a name="create-alerts"></a>알림 만들기

OMS에는 결과 경고의 수와 메트릭 측정 경고의 두 가지 유형이 있습니다. 경고를 만드는 방법에 대 한 자세한 내용은 [Log Analytics에서 경고 규칙 작업](https://docs.microsoft.com/azure/log-analytics/log-analytics-alerts-creating)을 참조 하십시오.

알림을 만들 때는 다음 사항을 고려해 야 합니다.

- 이 경고가 기본 선택 인 결과 수 경고 인지 확인 합니다. 

- 데모 쿼리를 수행 하려면 "결과 개수"가 "0 보다 큼"으로 설정 되어 있어야 합니다. 

- 시간대와 알림 빈도를 모두 5 분으로 설정 하는 것이 좋습니다. 

- 데모 경고에 대해서는 "경고 표시 안 함"을 사용 하도록 설정 하지 않는 것이 좋습니다. 

- 일반적인 경고 시나리오의 경우에는 하나의 오류 경고 및 하나의 리셋 알림과 같은 알림 쌍을 만드는 것이 좋습니다. 오류 경고에 대해 심각도 수준 중요를 선택 합니다. 재설정 알림에 대해 심각도 수준 정보를 선택 합니다.

다음 섹션에서는 예제 알림을 만드는 방법에 대해 설명 합니다.

 **"RTCMEDSRV이 중재 서버에서 실행 되 고 있지 않습니다." 및 "RTCMEDSRV은 중재 서버에서 실행 중입니다." 라는 경고 쌍을 만듭니다.**

이 경고 쌍을 만들려면

- 오류 경고에 대 한 쿼리는 다음과 같습니다.

  ```Kusto
  Event | where Computer contains "MediationServer" | where EventLog == "Lync Server" and (EventID == 25002 or EventID == 25003)  | summarize arg_max(TimeGenerated, EventID) by Computer | where EventID == 25003
  ```

    이 쿼리는  *컴퓨터에 "MediationServer"가 포함*  된 컴퓨터 필터를 사용 합니다. 필터는 이름에 문자열 "MediationServer"가 포함 된 컴퓨터만 선택 합니다.

     필터를 자체 컴퓨터 필터로 바꾸거나 제거 하면 됩니다. 정규식을 사용 하지 않고 복잡 한 문자열 필터를 만들 수 있습니다. 자세한 내용은 [문자열 연산자](https://docs.loganalytics.io/docs/Language-Reference/Scalar-operators/String-operators)를 참조 하십시오. 정규식을 사용 하도록 선택할 수도 있습니다. 또한 검색 쿼리를 저장 하 고 해당 그룹을 컴퓨터 필터로 사용 하 여 알림 쿼리의 컴퓨터 그룹을 만들 수도 있습니다. 자세한 내용은 [Log Analytics 로그 검색의 컴퓨터 그룹](https://docs.microsoft.com/azure/log-analytics/log-analytics-computer-groups)을 참조 하십시오.

    각 컴퓨터에 대해 오류 쿼리는 RTCMEDSRV 서비스 시작 및 서비스 중지 둘 다에 대 한 마지막 이벤트 로그를 가져옵니다. 마지막 이벤트가 서비스 중지 이벤트 인 경우 로그를 하나씩 반환 합니다. 마지막 이벤트가 서비스 시작 이벤트 인 경우 아무 것도 반환 하지 않습니다. 간단히 말해서 쿼리는 RTCMEDSRV가 시간 기간에 중지 된 서버 목록을 반환 합니다. 

- 재설정 경고에 대 한 쿼리는 다음과 같습니다.

  ```Kusto
  Event | where Computer contains "MediationServer" | where EventLog == "Lync Server" and (EventID == 25002 or EventID == 25003) | summarize arg_max(TimeGenerated, EventID) by Computer  | where EventID == 2500
  ```

    다시 설정 쿼리는 오류 쿼리를 정확히 반대 합니다. 마지막 이벤트가 서비스 시작 이벤트 인 경우 각 컴퓨터에 대해 1을 반환 합니다. 마지막 이벤트가 서비스 중지 이벤트 인 경우 아무 것도 반환 하지 않습니다.

**경고 쌍 만들기: "중재 서버에 너무 많은 동시 호출이 있습니다." 및 "동시 통화를 일반 로드로 대체"**

이 경고를 만들려면 다음을 수행 합니다.

- 오류 경고에 대 한 쿼리는 다음과 같습니다.

  ```Kusto
  Perf | where Computer contains "MediationServer" | where (ObjectName == "LS:MediationServer - Outbound Calls" or ObjectName == "LS:MediationServer - Inbound Calls") | summarize arg_max(TimeGenerated, CounterValue) by ObjectName, Computer | summarize  TotalCalls = sum(CounterValue) by Computer| where TotalCalls >= 500
  ```

    각 컴퓨터에 대해 쿼리는 인바운드 통화 및 아웃 바운드 호출에 대 한 마지막 카운터를 가져오고 해당 두 값의 합계를 계산 합니다. Sum 값이 500을 초과 하는 경우 로그 1 개를 반환 합니다. 그렇지 않으면 아무 것도 반환 하지 않습니다. 간단히 말해서 쿼리는 시간 시간대에 동시 통화가 너무 많은 서버 목록을 반환 합니다.

- 재설정 경고에 대 한 쿼리는 다음과 같습니다.

  ```Kusto
  Perf  | where Computer contains "MediationServer" | where (ObjectName == "LS:MediationServer - Outbound Calls" or ObjectName ==  "LS:MediationServer - Inbound Calls") | summarize arg_max(TimeGenerated, CounterValue) by ObjectName, Computer | summarize  TotalCalls = sum(CounterValue) by Computer| where TotalCalls < 500
  ```

    다시 설정 쿼리는 오류 쿼리를 정확히 반대 합니다. 각 컴퓨터에 대해 쿼리는 인바운드 통화 및 아웃 바운드 호출에 대 한 마지막 카운터를 가져오고 해당 두 값의 합계를 계산 합니다. Sum 값이 500 보다 작으면 로그가 1 개를 반환 하 고, 그렇지 않으면 그렇지 않으면 아무 것도 반환 되지 않습니다.

**경고 만들기: "CPU 사용 \> 90 또는 RTCMEDIARELAY이 (가) 서버에서 중지 되었습니다." 알림**

이 경고를 만들려면 쿼리는 다음과 같습니다.

```Kusto
search *| where Computer contains "MediationServer" | where (Type == "Perf" or Type == "Event") | where ((ObjectName ==  "Processor" and CounterName == "% Processor Time") or EventLog == "Lync Server") | where (CounterValue > 90 or EventID == 22003)
```

이 쿼리는 모든 컴퓨터에서 모든 프로세서 사용 카운터와 서비스 중지 이벤트를 가져오고, 프로세서 사용량이 90%를 초과 하거나 서비스가 중지 된 경우에는 로그를 하나씩 반환 합니다. 

## <a name="analyze-the-alerts-in-your-log-analytics-repository"></a>로그 분석 리포지토리에서 경고 분석

리포지토리에서 알림을 분석 하려면 경고 관리 솔루션을 사용 합니다. 자세한 내용은 [OMS (Operations Management Suite)에서 Alert Management solution](https://docs.microsoft.com/azure/log-analytics/log-analytics-solution-alert-management) 를 참조 하세요.

## <a name="recommended-minimal-monitoring-set"></a>권장 되는 최소 모니터링 설정

이벤트 로그 및 성능 카운터의 문제를 확인 하려면 다음을 수행 합니다. 

- **이벤트 로그** 어떤 문제를 해결 하려면 이벤트 쌍이 있는데, 이러한 이벤트 집합은 잘못 된 것으로 표시 되 고 다른 하나는 모든 것이 정상 임을 나타냅니다. 지정 된 기간 동안에는 마지막 이벤트가 기록 되어 해당 기간에 대 한 어떤 항목이 amiss 인지를 나타냅니다.

- **성능 카운터** 모니터링 되는 카운터에 대 한 임계값이 있어야 합니다.

다음 표에는 stop 및 start 이벤트 Id를 나열 하 여 Microsoft에서 모니터링을 권장 하는 서비스가 나와 있습니다.

|서비스 이름  <br/> |대상 서버 역할  <br/> |Stop 이벤트 ID  <br/> |시작 이벤트 ID  <br/> |
|:-----|:-----|:-----|:-----|
|RTCMEDSRV  <br/> |중재 서버  <br/> |25003  <br/> |25002  <br/> |
|RTCSRV  <br/> |에지 서버  <br/> |12289  <br/> |12288  <br/> |
|RTCMRAUTH  <br/> |에지 서버  <br/> |19003  <br/> |19002  <br/> |
|RTCMEDIARELAY  <br/> |에지 서버  <br/> |22003  <br/> |22002  <br/> |

다음 표에는 Microsoft에서 모니터링에 권장 되는 네트워크 문제가 나와 있습니다.


| 모니터 이름  <br/>                                        | 대상 서버 역할  <br/> | 성공 이벤트 ID 식  <br/> | 오류 이벤트 ID 식  <br/> | 오류 예  <br/> |
|:-----------------------------------------------------------|:--------------------------|:-----------------------------------|:---------------------------------|:-----------------------|
| 중재 서버에서 게이트웨이 연결에 오류가 발생 했습니다.  <br/>    | 중재 서버  <br/>   | 25062                              |                                  | 25002  <br/>           |
| 중재 서버에서 게이트웨이 호출을 완료 하지 못했습니다.  <br/> | 중재 서버  <br/>   | 25064                              |                                  | 25002  <br/>           |
| 중요 네트워크 문제  <br/>                           | 에지 서버  <br/>        | 14353                              |                                  | 12288  <br/>           |

다음 목록에는 모니터링 해야 하는 통화 용량 카운터가 나와 있습니다. 이 수치는 클라우드 커넥터 standard edition에 500 보다 작아야 합니다. 클라우드 커넥터 최소 버전의 경우 50 미만입니다.

- LS: MediationServer-Inbound Calls (_Total) \- Current 

- LS: MediationServer-아웃 바운드 호출 (_Total) \- 현재 

- LS: MediationServer-인바운드 호출 (_Total) \- 활성 미디어 바이패스 통화

- LS: MediationServer-아웃 바운드 호출 (_Total) \- 액티브 미디어 바이패스 통화

## <a name="see-also"></a>참고 항목

OMS 사용에 대 한 자세한 내용은 다음 항목을 참조 하십시오.

- [로그 분석에서 로그 검색을 사용 하 여 데이터 찾기](https://docs.microsoft.com/azure/log-analytics/log-analytics-log-searches)

- [Azure Log Analytics 언어 참조](https://docs.loganalytics.io/docs/Language-Reference)

- [로그 분석의 경고 이해](https://docs.microsoft.com/azure/log-analytics/log-analytics-alerts)

- [Azure의 Log Analytics service에 Windows 컴퓨터 연결](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents)


