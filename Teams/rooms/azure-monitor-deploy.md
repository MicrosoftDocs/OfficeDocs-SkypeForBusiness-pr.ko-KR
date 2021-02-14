---
title: Azure Monitor를 사용하여 Microsoft Teams 회의실 관리 배포
ms.author: dstrome
author: dstrome
ms.reviewer: Turgayo
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.assetid: d86ff657-ee92-4b06-aee3-d4c43090bdcb
description: 이 문서에서는 Azure Monitor를 사용하여 통합된 종단 방식으로 Microsoft Teams Rooms 디바이스의 관리를 배포하는 방법을 설명합니다.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: b05c490c157c9f6530ca79ecdd8df19f15d94c68
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662103"
---
# <a name="deploy-no-loc-textmicrosoft-teams-rooms-management-with-no-loc-textazure-monitor"></a>배포 :::no-loc text="Microsoft Teams Rooms"::: 관리 :::no-loc text="Azure Monitor":::

이 문서에서는 다음을 사용하여 통합된 종단식 디바이스 관리를 설정하고 배포하는 :::no-loc text="Microsoft Teams Rooms"::: 방법을 설명하고 :::no-loc text="Azure Monitor"::: 있습니다.

회의실 장치를 관리하는 데 도움이 되는 기본 원격 분석 및 알림을 제공하도록 구성할 :::no-loc text="Log Analytics"::: :::no-loc text="Azure Monitor"::: 수 :::no-loc text="Microsoft Teams Rooms"::: 있습니다. 관리 솔루션이 완성되면 디바이스 가용성 및 성능에 대한 자세한 보기를 만들기 위해 추가 데이터 및 관리 기능을 배포하기로 결정할 수 있습니다.

이 가이드에 따라 다음 예제와 같은 대시보드를 사용하여 디바이스 가용성, 애플리케이션 및 하드웨어 상태, 애플리케이션 및 운영 체제 버전 배포에 대한 자세한 상태 보고를 얻을 :::no-loc text="Microsoft Teams Rooms"::: 수 있습니다.

![Microsoft Teams 회의실에 대한 샘플 Log Analytics 보기 스크린샷](../media/Deploy-Azure-Monitor-1.png "Microsoft Teams 회의실에 대한 샘플 Log Analytics 보기")

높은 수준에서 다음 작업을 수행해야 합니다.


1. [구성 :::no-loc text="Log Analytics"::: 유효성 검사](azure-monitor-deploy.md#validate_LogAnalytics)
2. [관리 설정에 대한 :::no-loc text="Log Analytics"::: 테스트 디바이스 구성](azure-monitor-deploy.md#configure_test_devices)
3. [사용자 지정 필드 매핑](azure-monitor-deploy.md#Custom_fields)
4. [다음에서 :::no-loc text="Microsoft Teams Rooms"::: 보기 정의 :::no-loc text="Log Analytics":::](azure-monitor-deploy.md#Define_Views)
5. [경고 정의](azure-monitor-deploy.md#Alerts)
6. [모니터링을 위한 모든 디바이스 구성](azure-monitor-deploy.md#configure_all_devices)
7. [추가 솔루션 :::no-loc text="Azure Monitor"::: 구성](azure-monitor-deploy.md#Solutions)

> [!IMPORTANT]
> 최소한의 구성으로 운영 체제를 실행하는 컴퓨터를 모니터링할 수 있습니다. 하지만 모든 디바이스에 에이전트 배포를 시작하기 전에 몇 가지 –특정 단계를 :::no-loc text="Azure Monitor"::: :::no-loc text="Log Analytics"::: :::no-loc text="Windows"::: :::no-loc text="Microsoft Teams Rooms"::: 수행해야 :::no-loc text="Microsoft Teams Rooms"::: 합니다.
> 따라서 제어된 설정 및 구성에 대해 올바른 순서로 모든 구성 단계를 수행하는 것이 좋습니다. 최종 결과의 품질은 초기 구성의 품질에 따라 매우 다릅니다.

## <a name="validate-no-loc-textlog-analytics-configuration"></a>구성 :::no-loc text="Log Analytics"::: 유효성 검사
<a name="validate_LogAnalytics"> </a>

디바이스에서 로그 수집을 시작하려면 작업 :::no-loc text="Log Analytics"::: 영역이 :::no-loc text="Microsoft Teams Rooms"::: 필요합니다. 작업 영역은 자체 데이터 리포지토리, 데이터 원본 및 솔루션이 있는 고유한 :::no-loc text="Log Analytics"::: 환경입니다. 기존 작업 영역이 이미 있는 경우 배포를 모니터링하는 데 사용할 수도 있습니다. 또는 모니터링 요구에 특정한 전용 작업 영역도 만들 :::no-loc text="Log Analytics"::: :::no-loc text="Microsoft Teams Rooms"::: 수 :::no-loc text="Log Analytics"::: :::no-loc text="Microsoft Teams Rooms"::: 있습니다.

새 작업 영역 만들기가 필요한 경우 포털에서 작업 영역 만들기 문서의 :::no-loc text="Log Analytics"::: [지침을 :::no-loc text="Log Analytics"::: :::no-loc text="Azure"::: 따릅니다.](https://docs.microsoft.com/azure/azure-monitor/learn/quick-create-workspace)

> [!NOTE]
> 사용하려면 :::no-loc text="Log Analytics"::: :::no-loc text="Azure Monitor"::: 활성 구독이 :::no-loc text="Azure"::: 필요합니다. 구독이 없는 경우 무료 평가판 구독을 시작 :::no-loc text="Azure"::: 지점으로 만들 수 있습니다. [](https://azure.microsoft.com/free)

### <a name="configure-no-loc-textlog-analytics-to-collect-no-loc-textmicrosoft-teams-rooms-event-logs"></a>이벤트 :::no-loc text="Log Analytics"::: :::no-loc text="Microsoft Teams Rooms"::: 로그를 수집하도록 구성

:::no-loc text="Log Analytics"::: 설정에 지정된 이벤트 :::no-loc text="Windows"::: 로그에서만 이벤트를 수집합니다. 각 로그에 대해 선택한 심각도의 이벤트만 수집됩니다.

디바이스 및 애플리케이션 상태를 모니터링하는 데 필요한 로그를 수집하도록 :::no-loc text="Log Analytics"::: :::no-loc text="Microsoft Teams Rooms"::: 구성해야 합니다. :::no-loc text="Microsoft Teams Rooms"::: 디바이스는 이벤트 **:::no-loc text="Skype Room System":::** 로그를 사용 합니다.

이벤트를 :::no-loc text="Log Analytics"::: 수집하도록 :::no-loc text="Microsoft Teams Rooms"::: 구성하려면 [ :::no-loc text="Windows"::: :::no-loc text="Azure Monitor"::: ](https://docs.microsoft.com/azure/azure-monitor/platform/data-sources-windows-events)

![이벤트 로그 설정 스크린샷](../media/Deploy-Azure-Monitor-2.png "이벤트 로그 설정")

> [!IMPORTANT]
> 이벤트 로그 설정을 구성하고 이벤트 로그 이름으로 입력한 다음 오류, 경고 및 정보 :::no-loc text="Windows"::: **:::no-loc text="Skype Room System":::** 확인란을 선택합니다.   

## <a name="configure-test-devices-for-azure-monitoring"></a>Azure 모니터링에 대한 테스트 디바이스 구성
<a name="configure_test_devices"> </a>

관련 이벤트를 :::no-loc text="Log Analytics"::: 모니터링할 수 있게 :::no-loc text="Microsoft Teams Rooms"::: 준비해야 합니다. 먼저 물리적 액세스 권한이 있는 하나 또는 두 개의 디바이스에 에이전트를 배포하고 해당 테스트 디바이스가 일부 데이터를 생성하여 작업 영역으로 푸시하도록 :::no-loc text="Microsoft Monitoring"::: :::no-loc text="Microsoft Teams Rooms"::: 해야 :::no-loc text="Log Analytics"::: 합니다.

### <a name="install-no-loc-textmicrosoft-monitoring-agents-to-test-devices"></a>디바이스를 :::no-loc text="Microsoft Monitoring"::: 테스트하기 위해 에이전트 설치

서비스에 컴퓨터 연결에 제공된 지침을 사용하여 에이전트를 테스트 :::no-loc text="Microsoft Monitoring"::: [ :::no-loc text="Windows"::: 디바이스에 :::no-loc text="Log Analytics"::: 배포합니다. :::no-loc text="Azure"::: ](https://docs.microsoft.com/azure/azure-monitor/platform/agent-windows) 이 문서에서는 에이전트를 배포하는 단계, 배포에 연결된 디바이스를 얻기 위한 작업 영역 ID _ 및 기본 키를 얻기 위한 지침 및 인스턴스에 대한 에이전트 연결을 확인하는 단계에 대한 자세한 정보를 :::no-loc text="Microsoft Monitoring"::: :::no-loc text="Windows"::: :::no-loc text="Log Analytics":::  * ** _**_ :::no-loc text="Microsoft Teams Rooms"::: :::no-loc text="Azure Monitor"::: :::no-loc text="Log Analytics"::: 제공합니다.

### <a name="generate-sample-no-loc-textmicrosoft-teams-rooms-events"></a>샘플 :::no-loc text="Microsoft Teams Rooms"::: 이벤트 생성

에이전트를 테스트 디바이스에 배포한 후 필요한 이벤트 로그 데이터가 에 :::no-loc text="Microsoft Monitoring"::: 의해 수집되는지 확인 :::no-loc text="Azure Monitor":::

> [!NOTE]
> 에이전트를 설치한 후 디바이스를 다시 시작하고, 이벤트 로그에 새 이벤트를 생성할 수 있도록 모임 앱이 :::no-loc text="Microsoft Monitoring"::: :::no-loc text="Microsoft Teams Rooms"::: 시작된지 확인합니다.

1.  포털에 [ :::no-loc text="Microsoft Azure"::: 로그인하고](https://portal.azure.com) 작업 영역으로 :::no-loc text="Log Analytics"::: 이동하여 선택합니다.

2.  디바이스에서 생성된 하트비트 이벤트를 :::no-loc text="Microsoft Teams Rooms"::: 나열합니다.
    1.  작업 영역 선택 및 _ *로그** 로 이동하고 쿼리를 사용하여 사용자 지정 필드가 있는 하트비트 레코드를 :::no-loc text="Microsoft Teams Rooms"::: 검색합니다.
    2.  샘플 쿼리: `Event | where Source == "SRS-App" and EventID == 2000`

3.  쿼리가 모임 앱에서 생성된 이벤트를 포함 하는 로그 :::no-loc text="Microsoft Teams Rooms"::: 레코드를 반환하는지 확인 합니다.

4.  하드웨어 문제를 생성하고 필요한 이벤트가 로그인되어 있는지 유효성을 :::no-loc text="Azure Log Analytics"::: 검사합니다.
    1.  테스트 시스템에서 주변 장치 중 하나를 :::no-loc text="Microsoft Teams Rooms"::: 플러그합니다. 카메라, 스피커폰, 마이크 또는 전면 방 디스플레이일 수 있습니다.
    2.  이벤트 로그가 채워지기까지 10분 정도 :::no-loc text="Azure Log Analytics"::: 기다립니다.
    3.  쿼리를 사용하여 하드웨어 오류 이벤트를 나열합니다. `Event | where Source == "SRS-App" and EventID == 3001`

5.  애플리케이션 문제를 생성하고 필요한 이벤트가 기록되어 있는지 유효성을 검사합니다.
    1.  애플리케이션 :::no-loc text="Microsoft Teams Rooms"::: 구성을 수정하고 잘못된 SIP(세션 시작 프로토콜) 주소/암호 쌍을 입력합니다.
    2.  이벤트 로그가 채워지기까지 10분 정도 :::no-loc text="Azure Log Analytics"::: 기다립니다.
    3.  쿼리를 사용하여 애플리케이션 오류 이벤트를 나열합니다. `Event | where Source == "SRS-App" and EventID == 2001 and EventLevel == 1`

> [!IMPORTANT]
> 이러한 샘플 이벤트 로그는 사용자 지정 필드를 구성하기 전에 필요합니다. 필요한 이벤트 로그를 수집할 때까지 다음 단계를 진행하지 않습니다.

## <a name="map-custom-fields"></a>사용자 지정 필드 매핑
<a name="Custom_fields"> </a>

사용자 지정 필드를 사용하여 이벤트 로그에서 특정 데이터를 추출합니다. 나중에 타일, 대시보드 보기 및 경고에 사용할 사용자 지정 필드를 정의해야 합니다. 사용자 [지정 :::no-loc text="Log Analytics"::: 필드를 만들기](https://docs.microsoft.com/azure/azure-monitor/platform/custom-fields) 전에 사용자 지정 필드를 참조하고 개념을 익숙해 봐야 합니다.

캡처된 이벤트 로그에서 사용자 지정 필드를 추출하려면 다음 단계를 수행합니다.

1.  포털에 [ :::no-loc text="Microsoft Azure"::: 로그인하고](https://portal.azure.com) 작업 영역으로 :::no-loc text="Log Analytics"::: 이동하여 선택합니다.

2. 디바이스에서 생성된 이벤트를 :::no-loc text="Microsoft Teams Rooms"::: 나열합니다.
   1.  로그로 **이동하고** 쿼리를 사용하여 사용자 지정 필드가 있는 레코드를 검색합니다.
   2.  샘플 쿼리: `Event | where Source == "SRS-App" and EventID == 2000`

3. 레코드 중 하나를 선택하고 왼쪽에 있는 단추를 선택한 다음 필드 추출 마법사를 시작하세요.
4. RenderedDescription에서 추출할 데이터를 강조 표시하고 필드 제목을 제공합니다. 사용할 필드 이름은 표 1에 제공됩니다.
5. 표 *1에 표시된 매핑을 사용합니다.* :::no-loc text="Log Analytics":::새 필드를 정의할 때 **\_ CF** 문자열이 자동으로 추가됩니다.

> [!IMPORTANT]
> 모든 JSON 및 :::no-loc text="Log Analytics"::: 필드는 대소문자 구분입니다.
> 
> 아래 표의 각 사용자 지정 필드에 필요한 쿼리에 주의합니다. 사용자 지정 필드 값을 성공적으로 추출하려면 올바른 쿼리를 :::no-loc text="Log Analytics"::: 사용해야 합니다.
> 
**표 1**

| **JSON 필드**                   | **:::no-loc text="Log Analytics"::: 사용자 지정 필드** | **이벤트 ID** | **추출에 사용할 쿼리**                   |
|:---------------------------------|:-------------------------------|:-------------|:-------------------------------------------------------|
| 설명                      | SRSEventDescription         | **2000**     | Source \| == "SRS-App" 및 EventID == 2000인 이벤트 |
| ResourceState                    | SRSResourceState            | **2000**     | Source \| == "SRS-App" 및 EventID == 2000인 이벤트 |
| OperationName                    | SRSOperationName            | **2000**     | Source \| == "SRS-App" 및 EventID == 2000인 이벤트 |
| OperationResult                  | SRSOperationResult          | **2000**     | Source \| == "SRS-App" 및 EventID == 2000인 이벤트 |
| OS                               | SRSOSVersion                | **2000**     | Source \| == "SRS-App" 및 EventID == 2000인 이벤트 |
| OSVersion                        | SRSOSLongVersion            | **2000**     | Source \| == "SRS-App" 및 EventID == 2000인 이벤트 |
| 별칭                            | SRSAlias                    | **2000**     | Source \| == "SRS-App" 및 EventID == 2000인 이벤트 |
| DisplayName                      | SRSDisplayName              | **2000**     | Source \| == "SRS-App" 및 EventID == 2000인 이벤트 |
| AppVersion                       | SRSAppVersion               | **2000**     | Source \| == "SRS-App" 및 EventID == 2000인 이벤트 |
| IPv4Address                      | SRSIPv4Address              | **2000**     | Source \| == "SRS-App" 및 EventID == 2000인 이벤트 |
| IPv6Address                      | SRSIPv6Address              | **2000**     | Source \| == "SRS-App" 및 EventID == 2000인 이벤트 |
| 회의 마이크 상태     | SRSConfMicrophoneStatus     | **3001**     | Source \| == "SRS-App" 및 EventID == 3001인 이벤트 |
| 컨퍼런스 발표자 상태        | SRSConfSpeakerStatus        | **3001**     | Source \| == "SRS-App" 및 EventID == 3001인 이벤트 |
| 기본 발표자 상태           | SRSDefaultSpeakerStatus     | **3001**     | Source \| == "SRS-App" 및 EventID == 3001인 이벤트 |
| 카메라 상태                    | SRSCameraStatus             | **3001**     | Source \| == "SRS-App" 및 EventID == 3001인 이벤트 |
| 방 표시 상태 앞     | SRSFORDStatus               | **3001**     | Source \| == "SRS-App" 및 EventID == 3001인 이벤트 |
| 동작 센서 상태             | SRSMotionSensorStatus       | **3001**     | Source \| == "SRS-App" 및 EventID == 3001인 이벤트 |
| HDMI 인제스트 상태               | SRSHDMIIngestStatus         | **3001**     | Source \| == "SRS-App" 및 EventID == 3001인 이벤트 |


## <a name="define-the-no-loc-textmicrosoft-teams-rooms-views-in-no-loc-textlog-analytics"></a>다음에서 :::no-loc text="Microsoft Teams Rooms"::: 보기 정의 :::no-loc text="Log Analytics":::
<a name="Define_Views"> </a>

데이터가 수집되고 사용자 지정 필드가 매핑된 후 뷰 디자이너를 사용하여 이벤트를 모니터링하는 다양한 타일이 포함된 대시보드를 개발할 수 :::no-loc text="Microsoft Teams Rooms"::: 있습니다. 뷰 디자이너를 사용하여 다음 타일을 만들 수 있습니다. 자세한 내용은 뷰 디자이너를 사용하여 사용자 지정 [보기 만들기를 :::no-loc text="Log Analytics"::: 참조하세요.](https://docs.microsoft.com/azure/azure-monitor/platform/view-designer)

> [!NOTE]
> 대시보드 타일이 제대로 작동하려면 이 가이드의 이전 단계를 완료해야 합니다.

### <a name="create-a-microsoft-teams-rooms-dashboard-by-using-the-import-method"></a>가져오기 방법을 사용하여 Microsoft Teams 회의실 대시보드 만들기

대시보드를 가져오고 디바이스 :::no-loc text="Microsoft Teams Rooms"::: 모니터링을 빠르게 시작할 수 있습니다. 대시보드를 가져오는 다음 단계를 수행합니다.

1.  [SkypeRoomSystems_v2.omsview 대시보드 파일을](https://go.microsoft.com/fwlink/?linkid=835675) 얻습니다.
2.  포털에 [ :::no-loc text="Microsoft Azure"::: 로그인하고](https://portal.azure.com) 작업 영역으로 :::no-loc text="Log Analytics"::: 이동하여 선택합니다.
3.  뷰 **디자이너 열기.**
4.  가져오기 **및** **SkypeRoomSystems_v2.omsview 파일을** 선택합니다.
5.  저장을 **선택합니다.**

### <a name="create-a-microsoft-teams-rooms-dashboard-manually"></a>수동으로 Microsoft Teams 회의실 대시보드 만들기

또는 사용자 자신의 대시보드를 만들고 모니터링할 타일만 추가할 수 있습니다.

#### <a name="configure-the-overview-tile"></a>개요 타일 구성

1.  뷰 **디자이너 열기.**
2.  개요 **타일을** 선택한 다음 갤러리에서 **두** 숫자를 선택합니다.
3.  타일 이름을 **:::no-loc text="Microsoft Teams Rooms":::** 지정합니다.
4.  첫 번째 **타일 정의:**<br>
    **범례:** 지난 달 내에 하트비트가 한 번 이상 전송된 디바이스<br>
    **쿼리:**```Event | where EventLog == "Skype Room System" and TimeGenerated > ago(30d) | summarize TotalSRSDevices = dcount(Computer)```
5.  두 번째 **타일 정의:**<br>
    **범례:** 지난 1시간 내에 하트비트가 전송된 활성 디바이스<br>
    **쿼리:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(1h) | summarize TotalSRSDevices = dcount(Computer)```
6.  적용을 **선택합니다.**

### <a name="create-a-tile-that-displays-active-devices"></a>활성 디바이스를 표시하는 타일 만들기

1.  대시보드 **보기를 선택하여** 타일 추가를 시작하세요.
2.  갤러리에서 **&** 목록 선택
3.  일반 **속성을 정의합니다.**<br>
    **그룹 제목:** 하트비트 상태<br>
    **새 그룹:** 선택
4.  타일 **속성을 정의합니다.**<br>
    **범례:** 활성 디바이스(지난 20분 동안 전송된 하트비트)<br>
    **타일 쿼리:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(20m) | summarize AggregatedValue = count() by Computer | count```
5.  목록 속성을 **정의합니다.**<br>
    **쿼리 나열:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(20m) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```
6.  열 **제목 정의:**<br>
    **이름:** 컴퓨터 이름<br>
    **값:** 마지막 하트비트
7.  탐색 **쿼리를 정의합니다.**<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  **적용을** 선택한 다음 **닫습니다.**

### <a name="create-a-tile-that-displays-devices-that-have-connectivity-issues"></a>연결 문제가 있는 디바이스를 표시하는 타일 만들기

1.  갤러리에서 **&** 번호 매기기 목록을 선택한 다음 새 타일을 추가합니다.
2.  일반 **속성을 정의합니다.**<br>
    **그룹 제목:** 비워 두기<br>
    **새 그룹:** 선택되지 않았습니다.
3.  타일 **속성을 정의합니다.**<br>
    **범례:** 비활성 디바이스(지난 20분 동안 전송된 하트비트 메시지 없음)<br>
    **타일 쿼리:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize LastHB = max(TimeGenerated) by Computer | where LastHB < ago(20m) | count```
4.  목록 속성을 **정의합니다.**<br>
    **쿼리 나열:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize TimeGenerated = max(TimeGenerated) by Computer | where TimeGenerated < ago(20m) | order by TimeGenerated```
5.  열 **제목 정의:**<br>
    **이름:** 컴퓨터 이름<br>
    **값:** 마지막 하트비트
6.  탐색 **쿼리 정의:**<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
7.  **적용을** 선택한 다음 **닫습니다.**

### <a name="create-a-tile-that-displays-devices-that-have-a-hardware-error"></a>하드웨어 오류가 있는 디바이스를 표시하는 타일 만들기

1.  갤러리에서 **&** 번호 매기기 목록을 선택한 다음 새 타일을 추가합니다.
2.  일반 **속성을 정의합니다.**<br>
    **그룹 제목:** 하드웨어 상태<br>
    **새 그룹:** 선택
3.  타일 **속성을 정의합니다.**<br>
    **범례:** 지난 1시간 동안 하드웨어 오류가 발생한 디바이스<br>
    **타일 쿼리:**```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h) | summarize AggregatedValue = count() by Computer | count```
4.  목록 속성을 **정의합니다.**<br>
    **쿼리 나열:**```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```
5.  열 **제목 정의:**<br>
    **이름:** 컴퓨터 이름<br>
    **값:** 마지막 오류
6.  탐색 **쿼리 정의:**<br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == 3001 and EventLevelName == "Error" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSConfMicrophoneStatus_CF, SRSConfSpeakerStatus_CF, SRSDefaultSpeakerStatus_CF, SRSCameraStatus_CF, SRSFORDStatus_CF, SRSMotionSensorStatus_CF, SRSHDMIIngestStatus_CF, SRSEventDescription_CF | sort by TimeGenerated desc```
7.  **적용을** 선택한 다음 **닫습니다.**

### <a name="create-a-tile-that-displays-no-loc-textmicrosoft-teams-rooms-operating-system-versions"></a>운영 체제 버전을 :::no-loc text="Microsoft Teams Rooms"::: 표시하는 타일 만들기

1.  갤러리에서 **도넛형 &** 선택한 다음 새 타일을 추가합니다.
2.  일반 **속성을 정의합니다.**<br>
    **그룹 제목:** 운영 체제 세부 정보<br>
    **새 그룹:** 선택
3.  헤더 **속성을 정의합니다.**<br>
    **제목:** 운영 체제 버전<br>
    **자막:** 특정 OS 버전을 실행하는 디바이스
4.  도넛 **속성 정의:**<br>
    **쿼리:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize OS_Version = max(SRSOSLongVersion_CF) by Computer | summarize AggregatedValue = count() by OS_Version | sort by OS_Version asc```<br>
    **텍스트 가운데:** 디바이스<br>
    **작업:** 합계
5.  목록 속성을 **정의합니다.**<br>
    **쿼리 나열:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize SRSOSLongVersion_CF = max(SRSOSLongVersion_CF) by Computer | sort by Computer asc```<br>
    **그래프 숨기기:** 선택<br>
    **스파크라인 사용:** 선택되지 않았습니다.
6.  열 **제목을 정의합니다.**<br>
    **이름:** 컴퓨터 이름<br>
    **값:** 비워 두기
7.  탐색 **쿼리를 정의합니다.**<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSDisplayName_CF, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  적용을 **선택한** 다음 **닫습니다.**

### <a name="create-a-tile-that-displays-no-loc-textmicrosoft-teams-rooms-application-versions"></a>애플리케이션 버전을 표시하는 :::no-loc text="Microsoft Teams Rooms"::: 타일 만들기

1.  갤러리에서 **도넛형 &** 선택한 다음 새 타일을 추가합니다.
2.  일반 **속성을 정의합니다.**<br>
    **그룹 제목:** :::no-loc text="Microsoft Teams Rooms"::: 애플리케이션 세부 정보<br>
    **새 그룹:** 선택
3.  헤더 **속성을 정의합니다.**<br>
    **제목:** 애플리케이션 버전<br>
    **자막:** 특정 애플리케이션 버전을 실행하는 디바이스
4.  도넛 **속성 정의:**<br>
    **쿼리:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize App_Version = max(SRSAppVersion_CF) by Computer | summarize AggregatedValue = count() by App_Version | sort by App_Version asc```<br>
    **텍스트 가운데:** 디바이스<br>
    **작업:** 합계
5.  목록 속성을 **정의합니다.**<br>
    **쿼리 나열:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize SRSAppVersion_CF = max(SRSAppVersion_CF) by Computer | sort by Computer asc```<br>
    **그래프 숨기기:** 선택<br>
    **스파크라인 사용:** 선택되지 않았습니다.
6.  열 **제목을 정의합니다.**<br>
    **이름:** 컴퓨터 이름<br>
    **값:** 비워 두기
7.  탐색 **쿼리를 정의합니다.**<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  적용을 **선택한** 다음 **닫습니다.**

### <a name="create-a-tile-that-displays-devices-that-have-an-application-error"></a>애플리케이션 오류가 있는 디바이스를 표시하는 타일 만들기

1.  갤러리에서 **&** 번호 매기기 목록을 선택한 다음 새 타일을 추가합니다.
2.  일반 **속성을 정의합니다.**<br>
    **그룹 제목:** 비워 두기<br>
    **새 그룹:** 선택되지 않았습니다.
3.  타일 **속성을 정의합니다.**<br>
    **범례:** 지난 1시간 동안 애플리케이션 오류가 발생한 디바이스<br>
    **타일 쿼리:**```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h) | summarize AggregatedValue = count() by Computer | count```
4.  목록 속성을 **정의합니다.**<br>
    **쿼리 나열:**```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```
5.  열 **제목을 정의합니다.**<br>
    **이름:** 컴퓨터 이름<br>
    **값:** 마지막 오류
6.  탐색 **쿼리를 정의합니다.**<br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == 2001 and EventLevelName == "Error" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF | sort by TimeGenerated desc```
7.  적용을 **선택한** 다음 **닫습니다.**

### <a name="create-a-tile-that-displays-devices-that-have-been-restarted"></a>다시 시작된 디바이스를 표시하는 타일 만들기

1.  갤러리에서 **&** 번호 매기기 목록을 선택한 다음 새 타일을 추가합니다.
2.  일반 **속성을 정의합니다.**<br>
    **그룹 제목:** 비워 두기<br>
    **새 그룹:** 선택되지 않았습니다.
3.  타일 **속성을 정의합니다.**<br>
    **범례:** 지난 24시간 동안 애플리케이션이 다시 시작된 디바이스 및 다시 시작 횟수<br>
    **타일 쿼리:**```Event | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | summarize AggregatedValue = count() by Computer | count```
4.  목록 속성을 **정의합니다.**<br>
    **쿼리 나열:**```Event | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | order by TimeGenerated | summarize AggregatedValue = count(EventID) by Computer```
5.  열 **제목을 정의합니다.**<br>
    **이름:** 컴퓨터 이름<br>
    **값:** 다시 시작 횟수
6.  탐색 **쿼리를 정의합니다.**<br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
7.  적용을 **선택한** 다음 **닫습니다.**
8.  **저장을** 선택하여 대시보드를 저장합니다.

이제 보기 만들기를 완료합니다.

## <a name="configure-alerts-in-no-loc-textazure-monitor"></a>에서 경고 구성 :::no-loc text="Azure Monitor":::
<a name="Alerts"> </a>

:::no-loc text="Azure Monitor"::: 콘솔에서 문제가 발생하면 관리자에게 알리기 위해 :::no-loc text="Microsoft Teams Rooms"::: 경고를 발생할 수 있습니다.

:::no-loc text="Azure Monitor"::: 일정한 간격으로 예약된 로그 검색을 통해 실행되는 기본 제공 경고 메커니즘을 포함합니다. 로그 검색 결과가 특정 조건과 일치하는 경우 경고 레코드가 만들어집니다.

그런 다음 규칙은 자동으로 하나 이상의 작업을 실행하여 경고를 사전에 알리거나 다른 프로세스를 호출할 수 있습니다. 경고를 사용할 수 있는 옵션은 다음과 같습니다.
-   전자 메일 보내기
-   HTTP POST 요청을 통해 외부 프로세스 호출
-   서비스에서 Runbook :::no-loc text="Azure Automation"::: 시작

의 [경고에 :::no-loc text="Azure Monitor"::: ](https://docs.microsoft.com/azure/azure-monitor/platform/alerts-unified-log) 대한 자세한 내용은 로그 경고를 참조합니다. :::no-loc text="Azure Monitor":::

> [!NOTE]
> 다음 예제에서는 디바이스가 하드웨어 또는 애플리케이션 오류를 생성하는 경우 이메일 :::no-loc text="Microsoft Teams Rooms"::: 경고를 전송합니다.

### <a name="configure-an-email-alert-for-no-loc-textmicrosoft-teams-rooms-hardware-issues"></a>하드웨어 문제에 대한 전자 메일 :::no-loc text="Microsoft Teams Rooms"::: 경고 구성

지난 1시간 이내에 하드웨어 문제가 발생하는 디바이스를 검사하는 경고 :::no-loc text="Microsoft Teams Rooms"::: 규칙을 구성합니다.
1.  포털에 [ :::no-loc text="Microsoft Azure"::: 로그인하고](https://portal.azure.com) 작업 영역으로 :::no-loc text="Log Analytics"::: 이동하여 선택합니다.

2. 작업 :::no-loc text="Log Analytics"::: 영역으로 이동하여 **경고를** 선택한 다음 새 경고 **규칙을 선택합니다.**

3. 조건 **추가 및** 사용자 지정 로그 검색 **선택**

4.  검색 쿼리 텍스트 상자에 다음 쿼리를 입력합니다.<br>
    ```
    Event
    | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h)
    | summarize arg_max(TimeGenerated, *) by Computer
    | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSConfMicrophoneStatus_CF, SRSConfSpeakerStatus_CF, SRSDefaultSpeakerStatus_CF, SRSCameraStatus_CF, SRSFORDStatus_CF, SRSMotionSensorStatus_CF, SRSHDMIIngestStatus_CF, SRSEventDescription_CF
    |sort by TimeGenerated desc
    ```

5.  경고 논리 설정을 구성합니다.<br>
    **기준:** 결과 수<br>
    **조건:** 다음을 1보다 높게<br>
    **임계값:** 0<br>

6. 평가 설정을 구성하고 **완료:** <br>
    **기간(분):** 60<br>
    **빈도(분):** 60<br>

7. 작업 그룹을 구성합니다.
    1.  새로 **만들기 선택**
    2.  작업 그룹 이름  및 짧은 이름 필드에 *적합한 이름을* 제공합니다.
    3.  고유한 작업 *이름을 지정하고* **전자 메일/SMS/푸시/음성을** 선택한 다음 세부 정보 **편집을 선택합니다.**
    4.  전자 메일 **확인란을** 선택하고 알림을 받을 사용자 또는 그룹의 전자 메일 주소를 제공합니다.
    5.  SMS, 음성 통화 또는 둘 다로 알림을 받을 전화 번호를 제공할 수도 있습니다.
    6. 확인을 **선택합니다.**

8. **경고 전자** 메일의 제목 줄을 다시 정의할 경우 작업을 사용자 지정합니다.

9. 규칙 이름 및 설명을 지정합니다.<br>
    **규칙 이름:** :::no-loc text="Microsoft Teams Rooms"::: 하드웨어 오류 경고<br>
    **설명:** 지난 1시간 이내에 하드웨어 문제가 발생한 디바이스 목록<br>

10. 의도한 심각도 선택 및 규칙이 사용하도록 설정되어 있는지 확인합니다.

11. 경고 **규칙 만들기를 선택합니다.**

### <a name="configure-an-email-alert-for-no-loc-textmicrosoft-teams-rooms-application-issues"></a>애플리케이션 문제에 대한 이메일 :::no-loc text="Microsoft Teams Rooms"::: 경고 구성

동일한 절차를 반복하지만 다음 쿼리를 사용하여 지난 1시간 내에 애플리케이션 문제가 발생한 디바이스를 나열합니다.

    ```
    Event
    | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h)
    | summarize arg_max(TimeGenerated, *) by Computer
    | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF
    | sort by TimeGenerated desc
    ```

이제 경고 정의를 완료했습니다. 위의 예제를 사용하여 추가 경고를 정의할 수 있습니다.

경고가 생성될 때 지난 1시간 이내에 문제가 발생한 디바이스를 나열하는 전자 메일을 얻게 됩니다.

! [샘플 :::no-loc text="Azure Monitor"::: 경고 전자 메일](.. /media/Deploy-Azure-Monitor-6.png "샘플 :::no-loc text="Azure Monitor"::: 경고 전자 메일")

## <a name="configure-all-devices-for-no-loc-textazure-monitoring"></a>모든 디바이스 구성 :::no-loc text="Azure Monitoring":::
<a name="configure_all_devices"></a> 대시보드 및 경고를 구성한 후 모니터링 배포를 완료하도록 모든 디바이스에서 에이전트를 설정하고 :::no-loc text="Microsoft Monitoring"::: :::no-loc text="Microsoft Teams Rooms"::: 구성할 수 있습니다.

각 디바이스에서 에이전트를 수동으로 설치 및 구성할 수 있지만 기존 소프트웨어 배포 도구 및 방법을 :::no-loc text="Microsoft Monitoring"::: 활용하는 것이 좋습니다.

처음으로 디바이스를 빌드하는 경우 빌드 프로세스의 일부로 에이전트 설정 및 구성 단계를 포함할 :::no-loc text="Microsoft Teams Rooms"::: :::no-loc text="Microsoft Monitoring"::: 수 있습니다. 자세한 내용은 명령줄을 사용하여 [에이전트 설치를 참조하세요.](https://docs.microsoft.com/azure/azure-monitor/platform/agent-windows#install-the-agent-using-the-command-line)

### <a name="deploying-no-loc-textmicrosoft-monitoring-agent-by-using-a-group-policy-object-gpo"></a>:::no-loc text="Microsoft Monitoring":::GPO(그룹 정책 개체)를 사용하여 에이전트 배포

구현하기 전에 디바이스를 이미 배포한 경우 제공된 스크립트를 사용하여 그룹 정책 개체를 사용하여 에이전트를 설정하고 :::no-loc text="Microsoft Teams Rooms"::: :::no-loc text="Azure Monitoring"::: 구성할 :::no-loc text="Active Directory"::: 수 있습니다.

1.  공유 네트워크 경로를 만들고 도메인 컴퓨터 그룹에 대한 읽기 **액세스 권한을 부여합니다.**

2.  다음에서 에이전트의 64비트 :::no-loc text="Microsoft Monitoring"::: 버전을 :::no-loc text="Windows"::: 다운로드합니다. <https://go.microsoft.com/fwlink/?LinkID=517476>

3.  설치 패키지의 내용을 네트워크 공유에 추출합니다.
    1.  명령 프롬프트 창을 열고 **/c를MMASetup-AMD64.exe 실행합니다.**
    2.  방금 만든 공유를 지정하고 콘텐츠를 추출합니다.

4.  새 그룹 정책 개체를 만들고 컴퓨터 계정이 있는 조직 :::no-loc text="Microsoft Teams Rooms"::: 단위에 할당합니다.

5.  PowerShell 실행 정책을 구성합니다.
    1.  새로 만든 그룹 정책 개체를 편집하고 컴퓨터 구성 정책 관리 템플릿 구성 요소로 \\ \\ \\ :::no-loc text="Windows"::: 이동합니다. \\:::no-loc text="Windows PowerShell":::
    2.  스크립트 **실행을 켜고**  로컬 스크립트를 허용하도록 실행 **정책을 설정합니다.**

6.  시작 스크립트를 구성합니다.
    1.  다음 스크립트를 복사하고 다음 스크립트로 Install-MMAgent.ps1.
    2.  WorkspaceId, WorkspaceKey 및 SetupPath 매개 변수를 구성과 일치하도록 수정합니다.
    3.  동일한 그룹 정책 개체를 편집하고 컴퓨터 구성 정책 \\ \\ :::no-loc text="Windows"::: 설정 \\ 스크립트(시작/종료)로 이동합니다.
    4.  시작을 선택하려면 두 번 클릭한 다음 **PowerShell 스크립트를 선택합니다.**
    5.  파일 **표시를** 선택한 다음Install-MMAgent.ps1파일을 해당 **폴더에** 복사합니다.
    6.  **추가를** 선택한 다음 **찾아보기를 선택합니다.**
    7.  방금 복사한 ps1 스크립트를 선택합니다.

7.  :::no-loc text="Microsoft Teams Rooms"::: 디바이스는 두 번째 재부팅을 통해 에이전트를 설치하고 :::no-loc text="Microsoft Monitoring"::: 구성해야 합니다.

```PowerShell
# Install-MMAgent.ps1
<#
Date:        04/20/2018
Script:      Install-MMAgent.ps1
Version:     1.0
#>

# Set the parameters
$WorkspaceId = "<your workspace id>"
$WorkspaceKey = "<your workspace key>"
$SetupPath = "\\Server\Share"

$SetupParameters = "/qn NOAPM=1 ADD_OPINSIGHTS_WORKSPACE=1 OPINSIGHTS_WORKSPACE_AZURE_CLOUD_TYPE=0 OPINSIGHTS_WORKSPACE_ID=$WorkspaceId OPINSIGHTS_WORKSPACE_KEY=$WorkspaceKey AcceptEndUserLicenseAgreement=1"

# $SetupParameters = $SetupParameters + " OPINSIGHTS_PROXY_URL=<Proxy server URL> OPINSIGHTS_PROXY_USERNAME=<Proxy server username> OPINSIGHTS_PROXY_PASSWORD=<Proxy server password>"

# Start PowerShell logging
Start-Transcript -Path C:\Temp\MMA-Install.Log

# Check if the Microsoft Monitoring Agent is installed
$mma = New-Object -ComObject 'AgentConfigManager.MgmtSvcCfg'

# Check if the Microsoft Monitoring agent is installed
if (!$mma)
{
    #Install agent
    Start-Process -FilePath "$SetupPath\Setup.exe" -ArgumentList $SetupParameters -ErrorAction Stop -Wait
}

# Check if the agent has a valid configuration
$CheckMMA = $mma.GetCloudWorkspace($WorkspaceId).AgentId
if (!$CheckMMA)
{
    # Apply new configuration
    $mma.AddCloudWorkspace($WorkspaceId, $WorkspaceKey)
    $mma.ReloadConfiguration()
}

Stop-Transcript
```

> [!NOTE]
> 에이전트를 다시 구성하거나, 다른 작업 영역으로 이동하거나, 초기 설치 후 프록시 설정을 수정해야 하는 경우 에이전트 관리 및 유지 관리 문서를 참조할 수 있습니다. [ :::no-loc text="Log Analytics"::: ](https://docs.microsoft.com/azure/azure-monitor/platform/agent-manage)

## <a name="additional-solutions"></a>추가 솔루션
<a name="Solutions"> </a>

:::no-loc text="Azure Monitor":::환경을 추가로 모니터링할 수 [](https://docs.microsoft.com/azure/azure-monitor/insights/solutions) 있도록 솔루션 갤러리를 통해 기본 제공 관리 솔루션을 제공합니다. 작업 영역도 경고 [](https://docs.microsoft.com/azure/azure-monitor/platform/alert-management-solution) 관리 및 [ :::no-loc text="Azure Log Analytics"::: 에이전트 상태](https://docs.microsoft.com/azure/azure-monitor/insights/solution-agenthealth) 솔루션을 추가하는 것이 좋습니다.

> [!NOTE]
> 에이전트 상태 솔루션은 사용자 환경 내에서 사용되지 않은 에이전트 또는 손상된 에이전트를 식별하는 데 도움이 될 수 있으며, 경고 관리 솔루션은 특정 기간 내에 발생된 경고에 대한 세부 :::no-loc text="Microsoft Monitoring"::: 정보를 제공합니다.

## <a name="see-also"></a>참고 항목

[계획 :::no-loc text="Microsoft Teams Rooms"::: 관리 :::no-loc text="Azure Monitor":::](azure-monitor-plan.md)

[디바이스를 :::no-loc text="Microsoft Teams Rooms"::: 사용하여 관리 :::no-loc text="Azure Monitor":::](azure-monitor-manage.md)
