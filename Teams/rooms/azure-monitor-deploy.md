---
title: Azure Monitor를 사용하여 Microsoft Teams 룸 모니터링 배포
ms.author: dstrome
author: dstrome
ms.reviewer: Turgayo
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Rooms
ms.assetid: d86ff657-ee92-4b06-aee3-d4c43090bdcb
description: 이 문서에서는 Azure Monitor를 사용하여 통합된 엔드 투 엔드 방식으로 Microsoft Teams 룸 모니터링을 배포하는 방법을 설명합니다.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 2b6d1931b0a1818b5146f6ac0e02c225fea3af52
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2022
ms.locfileid: "67267453"
---
# <a name="deploy-no-loc-textmicrosoft-teams-rooms-monitoring-with-no-loc-textazure-monitor"></a>를 사용하여 모니터링 배포 :::no-loc text="Microsoft Teams Rooms"::::::no-loc text="Azure Monitor":::

이 문서에서는 디바이스를 사용하여 :::no-loc text="Azure Monitor":::통합된 엔드 투 엔드 모니터링을 설정하고 배포하는 :::no-loc text="Microsoft Teams Rooms"::: 방법을 설명합니다.

관리 하는 데 도움이 되는 기본 원격 분석 및 경고를 제공 하도록 내에서 :::no-loc text="Azure Monitor"::: 구성할 :::no-loc text="Log Analytics"::: 수 있습니다:::no-loc text="Microsoft Teams Rooms":::. 관리 솔루션이 완성되면 추가 데이터 및 관리 기능을 배포하여 디바이스 가용성 및 성능에 대한 자세한 보기를 만들 수 있습니다.

이 가이드에 따라 다음 예제와 같은 대시보드를 사용하여 디바이스 가용성, 애플리케이션 및 하드웨어 상태 :::no-loc text="Microsoft Teams Rooms"::: , 애플리케이션 및 운영 체제 버전 배포에 대한 자세한 상태 보고를 가져올 수 있습니다.

![Microsoft Teams 룸 대한 샘플 Log Analytics 보기의 스크린샷.](../media/Deploy-Azure-Monitor-1.png "Microsoft Teams 룸 대한 샘플 Log Analytics 보기")

높은 수준에서 다음 작업을 수행해야 합니다.


1. [구성 유효성 :::no-loc text="Log Analytics"::: 검사](azure-monitor-deploy.md#validate_LogAnalytics)
2. [관리 설정에 대한 :::no-loc text="Log Analytics"::: 테스트 디바이스 구성](azure-monitor-deploy.md#configure_test_devices)
3. [사용자 지정 필드 매핑](azure-monitor-deploy.md#Custom_fields)
4. [에서 :::no-loc text="Microsoft Teams Rooms"::: 뷰 정의 :::no-loc text="Log Analytics":::](azure-monitor-deploy.md#Define_Views)
5. [경고 정의](azure-monitor-deploy.md#Alerts)
6. [모니터링을 위해 모든 디바이스 구성](azure-monitor-deploy.md#configure_all_devices)
7. [추가 :::no-loc text="Azure Monitor"::: 솔루션 구성](azure-monitor-deploy.md#Solutions)

> [!IMPORTANT]
> 최소한의 구성 :::no-loc text="Azure Monitor"::: :::no-loc text="Log Analytics"::: 으로 운영 체제를 실행하는 :::no-loc text="Windows"::: 컴퓨터를 모니터링할 수 있지만 모든 :::no-loc text="Microsoft Teams Rooms"::: 디바이스에 에이전트 배포를 시작하기 전에 수행해야 하는 몇 가지 :::no-loc text="Microsoft Teams Rooms":::특정 단계가 여전히 있습니다.
> 따라서 제어된 설정 및 구성에 대해 올바른 순서로 모든 구성 단계를 수행하는 것이 좋습니다. 최종 결과의 품질은 초기 구성의 품질에 따라 크게 달라집니다.

## <a name="validate-no-loc-textlog-analytics-configuration"></a>구성 유효성 :::no-loc text="Log Analytics"::: 검사
<a name="validate_LogAnalytics"> </a>

에서 로그 수집을 :::no-loc text="Log Analytics"::: 시작하려면 작업 영역이 있어야 합니다 :::no-loc text="Microsoft Teams Rooms":::. 작업 영역은 자체 데이터 리포지토리, 데이터 원본 및 솔루션이 있는 고유한 :::no-loc text="Log Analytics"::: 환경입니다. 기존 :::no-loc text="Log Analytics"::: 작업 영역이 이미 있는 경우 배포를 모니터링 :::no-loc text="Microsoft Teams Rooms"::: 하는 데 사용할 수도 있고 또는 모니터링 요구 사항과 관련된 :::no-loc text="Microsoft Teams Rooms"::: 전용 :::no-loc text="Log Analytics"::: 작업 영역을 만들 수도 있습니다.

새 :::no-loc text="Log Analytics"::: 작업 영역을 만들어야 하는 경우 [포털에서 작업 영역 :::no-loc text="Azure"::: 만들기 :::no-loc text="Log Analytics":::](/azure/azure-monitor/learn/quick-create-workspace) 문서의 지침을 따릅니다.

> [!NOTE]
> 함께 사용 :::no-loc text="Log Analytics"::: :::no-loc text="Azure Monitor":::하려면 활성 :::no-loc text="Azure"::: 구독이 있어야 합니다. 구독이 :::no-loc text="Azure"::: 없는 경우 평가 [판 구독을](https://azure.microsoft.com/free) 시작점으로 만들 수 있습니다.

### <a name="configure-no-loc-textlog-analytics-to-collect-no-loc-textmicrosoft-teams-rooms-event-logs"></a>이벤트 로그를 수집 :::no-loc text="Microsoft Teams Rooms"::: 하도록 구성 :::no-loc text="Log Analytics":::

:::no-loc text="Log Analytics"::: 은 설정에 :::no-loc text="Windows"::: 지정된 이벤트 로그에서만 이벤트를 수집합니다. 각 로그에 대해 선택한 심각도가 있는 이벤트만 수집됩니다.

디바이스 및 애플리케이션 상태를 모니터링 :::no-loc text="Microsoft Teams Rooms"::: 하는 데 필요한 로그를 수집하도록 구성 :::no-loc text="Log Analytics"::: 해야 합니다. :::no-loc text="Microsoft Teams Rooms"::: 이벤트 로그를 **:::no-loc text="Skype Room System":::** 사용합니다.

이벤트를 수집하도록 구성 :::no-loc text="Log Analytics"::: 하려면 :::no-loc text="Microsoft Teams Rooms":::[에서 :::no-loc text="Azure Monitor":::이벤트 로그 데이터 원본을 참조:::no-loc text="Windows":::하세요.](/azure/azure-monitor/platform/data-sources-windows-events)

![이벤트 로그 설정의 스크린샷.](../media/Deploy-Azure-Monitor-2.png "이벤트 로그 설정")

> [!IMPORTANT]
> 이벤트 로그 설정을 구성 :::no-loc text="Windows"::: 하고 이벤트 로그 이름으로 입력 **:::no-loc text="Skype Room System":::** 한 다음 **오류**, **경고** 및 **정보** 확인란을 선택합니다.

## <a name="configure-test-devices-for-azure-monitoring"></a>Azure Monitoring에 대한 테스트 디바이스 구성
<a name="configure_test_devices"> </a>

관련 이벤트를 모니터링:::no-loc text="Microsoft Teams Rooms":::할 수 있도록 준비 :::no-loc text="Log Analytics"::: 해야 합니다. 먼저 물리적 액세스 권한이 있는 하나 또는 두 개의 :::no-loc text="Microsoft Teams Rooms"::: 디바이스에 에이전트를 배포 :::no-loc text="Microsoft Monitoring"::: 하고 해당 테스트 디바이스를 가져와서 일부 데이터를 생성하고 작업 영역에 푸시해야 :::no-loc text="Log Analytics"::: 합니다.

### <a name="install-no-loc-textmicrosoft-monitoring-agents-to-test-devices"></a>에이전트를 설치 :::no-loc text="Microsoft Monitoring"::: 하여 디바이스 테스트

:::no-loc text="Microsoft Monitoring"::: Connect 컴퓨터에 제공된 지침을 사용하여 테스트 디바이스에 [:::no-loc text="Windows"::: 에이전트를 배포합니다 :::no-loc text="Log Analytics"::: :::no-loc text="Azure":::](/azure/azure-monitor/platform/agent-windows). 이 문서에서는 에이전트를 배포하는 :::no-loc text="Microsoft Monitoring"::: 단계, 배포에 연결된 :::no-loc text="Azure Monitor"::: 디바이스를 :::no-loc text="Log Analytics"::: * 가져오기 위한 :::no-loc text="Windows":::**작업 영역 ID** _ 및 _ *_primary key_**:::no-loc text="Microsoft Teams Rooms":::를 가져오기 위한 지침 및 인스턴스에 대한 에이전트 연결을 :::no-loc text="Log Analytics"::: 확인하는 단계에 대한 자세한 정보를 제공합니다.

### <a name="generate-sample-no-loc-textmicrosoft-teams-rooms-events"></a>샘플 :::no-loc text="Microsoft Teams Rooms"::: 이벤트 생성

에이전트가 :::no-loc text="Microsoft Monitoring"::: 테스트 디바이스에 배포된 후 필요한 이벤트 로그 데이터가 수집 :::no-loc text="Azure Monitor":::되는지 확인합니다.

> [!NOTE]
> 에이전트를 설치한 후 디바이스를 :::no-loc text="Microsoft Monitoring"::: 다시 부팅하고, 이벤트 로그에 새 이벤트를 생성할 수 있도록 모임 앱이 시작되었는지 확인 :::no-loc text="Microsoft Teams Rooms"::: 합니다.

1.  포털에 [:::no-loc text="Microsoft Azure":::](https://portal.azure.com) 로그인하고 작업 영역으로 :::no-loc text="Log Analytics"::: 이동하여 선택합니다.

2.  디바이스에서 생성된 하트비트 이벤트를 나열합니다.:::no-loc text="Microsoft Teams Rooms":::
    1.  작업 영역을 선택하고 **로그** 로 이동하여 쿼리를 사용하여 사용자 지정 필드가 있는 하트비트 레코드를 :::no-loc text="Microsoft Teams Rooms":::검색합니다.
    2.  샘플 쿼리: `Event | where Source == "SRS-App" and EventID == 2000`

3.  쿼리가 모임 앱에서 생성된 이벤트를 포함하는 로그 레코드를 :::no-loc text="Microsoft Teams Rooms"::: 반환하는지 확인합니다.

4.  하드웨어 문제를 생성하고 필요한 이벤트가 로그인되어 :::no-loc text="Azure Log Analytics":::있는지 확인합니다.
    1.  테스트 :::no-loc text="Microsoft Teams Rooms"::: 시스템에서 주변 장치 중 하나를 분리합니다. 카메라, 스피커, 마이크 또는 프런트 룸 디스플레이일 수 있습니다.
    2.  이벤트 로그가 채워 :::no-loc text="Azure Log Analytics":::질 때까지 10분 정도 기다립니다.
    3.  쿼리를 사용하여 하드웨어 오류 이벤트를 나열합니다. `Event | where Source == "SRS-App" and EventID == 3001`

5.  애플리케이션 문제를 생성하고 필요한 이벤트가 기록되는지 확인합니다.
    1.  계정 구성을 수정 :::no-loc text="Microsoft Teams Rooms"::: 하고 잘못된 Email/암호 쌍을 입력합니다.
    2.  이벤트 로그가 채워 :::no-loc text="Azure Log Analytics":::질 때까지 10분 정도 기다립니다.
    3.  쿼리를 사용하여 애플리케이션 오류 이벤트를 나열합니다. `Event | where Source == "SRS-App" and EventID == 2001 and EventLevel == 1`

> [!IMPORTANT]
> 이러한 샘플 이벤트 로그는 사용자 지정 필드를 구성하기 전에 필요합니다. 필요한 이벤트 로그를 수집할 때까지 다음 단계로 진행하지 마세요.

## <a name="map-custom-fields"></a>사용자 지정 필드 매핑
<a name="Custom_fields"> </a>

사용자 지정 필드를 사용하여 이벤트 로그에서 특정 데이터를 추출합니다. 나중에 타일, 대시보드 보기 및 경고와 함께 사용할 사용자 지정 필드를 정의해야 합니다. 사용자 지정 필드 만들기를 시작하기 전에 사용자 [지정 필드를 :::no-loc text="Log Analytics":::](/azure/azure-monitor/platform/custom-fields) 보고 개념에 익숙해지세요.

캡처된 이벤트 로그에서 사용자 지정 필드를 추출하려면 다음 단계를 수행합니다.

1.  포털에 [:::no-loc text="Microsoft Azure":::](https://portal.azure.com) 로그인하고 작업 영역으로 :::no-loc text="Log Analytics"::: 이동하여 선택합니다.

2. 디바이스에서 생성된 이벤트를 나열합니다.:::no-loc text="Microsoft Teams Rooms":::
   1.  **로그** 로 이동하고 쿼리를 사용하여 사용자 지정 필드가 있는 레코드를 검색합니다.
   2.  샘플 쿼리: `Event | where Source == "SRS-App" and EventID == 2000`

3. 레코드 중 하나를 선택하고 왼쪽의 단추를 선택한 다음 필드 추출 마법사를 시작합니다.
4. RenderedDescription에서 추출하려는 데이터를 강조 표시하고 필드 제목을 제공합니다. 사용해야 하는 필드 이름은 표 1에 제공됩니다.
5. *표 1* 에 표시된 매핑을 사용합니다. :::no-loc text="Log Analytics"::: 는 새 필드를 정의할 **\_때 CF** 문자열을 자동으로 추가합니다.

> [!IMPORTANT]
> 모든 JSON 및 :::no-loc text="Log Analytics"::: 필드는 대/소문자를 구분합니다.
> 
> 아래 표의 각 사용자 지정 필드에 필요한 쿼리에 주의하세요. 사용자 지정 필드 값을 성공적으로 추출하려면 올바른 쿼리 :::no-loc text="Log Analytics"::: 를 사용해야 합니다.
> 
**표 1**

| **JSON 필드**                   | **:::no-loc text="Log Analytics"::: 사용자 지정 필드** | **이벤트 ID** | **추출과 함께 사용할 쿼리**                   |
|:---------------------------------|:-------------------------------|:-------------|:-------------------------------------------------------|
| 설명                      | SRSEventDescription         | **2000**     | \| Source == "SRS-App" 및 EventID == 2000 이벤트 |
| ResourceState                    | SRSResourceState            | **2000**     | \| Source == "SRS-App" 및 EventID == 2000 이벤트 |
| OperationName                    | SRSOperationName            | **2000**     | \| Source == "SRS-App" 및 EventID == 2000 이벤트 |
| OperationResult                  | SRSOperationResult          | **2000**     | \| Source == "SRS-App" 및 EventID == 2000 이벤트 |
| Os                               | SRSOSVersion                | **2000**     | \| Source == "SRS-App" 및 EventID == 2000 이벤트 |
| OSVersion                        | SRSOSLongVersion            | **2000**     | \| Source == "SRS-App" 및 EventID == 2000 이벤트 |
| 별칭                            | SRSAlias                    | **2000**     | \| Source == "SRS-App" 및 EventID == 2000 이벤트 |
| Displayname                      | SRSDisplayName              | **2000**     | \| Source == "SRS-App" 및 EventID == 2000 이벤트 |
| AppVersion                       | SRSAppVersion               | **2000**     | \| Source == "SRS-App" 및 EventID == 2000 이벤트 |
| IPv4Address                      | SRSIPv4Address              | **2000**     | \| Source == "SRS-App" 및 EventID == 2000 이벤트 |
| IPv6Address                      | SRSIPv6Address              | **2000**     | \| Source == "SRS-App" 및 EventID == 2000 이벤트 |
| 회의 마이크 상태     | SRSConfMicrophoneStatus     | **3001**     | Source \| == "SRS-App" 및 EventID == 3001 이벤트 |
| 컨퍼런스 발표자 상태        | SRSConfSpeakerStatus        | **3001**     | Source \| == "SRS-App" 및 EventID == 3001 이벤트 |
| 기본 화자 상태           | SRSDefaultSpeakerStatus     | **3001**     | Source \| == "SRS-App" 및 EventID == 3001 이벤트 |
| 카메라 상태                    | SRSCameraStatus             | **3001**     | Source \| == "SRS-App" 및 EventID == 3001 이벤트 |
| 방 전면 표시 상태     | SRSFORDStatus               | **3001**     | Source \| == "SRS-App" 및 EventID == 3001 이벤트 |
| 동작 센서 상태             | SRSMotionSensorStatus       | **3001**     | Source \| == "SRS-App" 및 EventID == 3001 이벤트 |
| HDMI 수집 상태               | SRSHDMIIngestStatus         | **3001**     | Source \| == "SRS-App" 및 EventID == 3001 이벤트 |


## <a name="define-the-no-loc-textmicrosoft-teams-rooms-views-in-no-loc-textlog-analytics"></a>에서 :::no-loc text="Microsoft Teams Rooms"::: 뷰 정의 :::no-loc text="Log Analytics":::
<a name="Define_Views"> </a>

데이터가 수집되고 사용자 지정 필드가 매핑된 후 뷰 디자이너를 사용하여 다양한 타일이 포함된 대시보드를 개발하여 이벤트를 모니터링 :::no-loc text="Microsoft Teams Rooms"::: 할 수 있습니다. 뷰 디자이너를 사용하여 다음 타일을 만듭니다. 자세한 내용은 [에서 뷰 디자이너를 사용하여 사용자 지정 보기 만들기를 참조하세요. :::no-loc text="Log Analytics":::](/azure/azure-monitor/platform/view-designer)

> [!NOTE]
> 대시보드 타일이 제대로 작동하려면 이 가이드의 이전 단계를 완료해야 합니다.
>
> [!IMPORTANT]
> [Azure Monitor의 뷰 디자이너는 2023년 8월 31일에 사용 중지되고 2020](https://azure.microsoft.com/updates/view-designer-in-azure-monitor-is-retiring-on-31-august-2023/) 년 11월 30일에 만들기 및 복제 기능이 비활성화되었습니다. 통합 문서를 대신 사용할 수 있습니다. 통합 문서로의 뷰 디자이너 전환 가이드에 대한 자세한 내용은 [미리 설정된 뷰 디자이너 템플릿이 있는 빠른 시작을 참조하세요](/azure/azure-monitor/visualize/view-designer-conversion-tasks#quickstart-with-preset-view-designer-templates).

### <a name="create-a-microsoft-teams-rooms-dashboard-manually"></a>수동으로 Microsoft Teams 룸 대시보드 만들기

또는 사용자 고유의 대시보드를 만들고 모니터링하려는 타일만 추가할 수 있습니다.

#### <a name="configure-the-overview-tile"></a>개요 타일 구성

1.  **뷰 디자이너를** 엽니다.
2.  **개요 타일** 을 선택한 다음 갤러리에서 **두 개의 숫자를** 선택합니다.
3.  타일 이름을 지정합니다 **:::no-loc text="Microsoft Teams Rooms":::**.
4.  **첫 번째 타일을 정의합니다.**<br>
    **범례:** 지난 달 내에 하트비트를 한 번 이상 보낸 디바이스<br>
    **쿼리:** ```Event | where EventLog == "Skype Room System" and TimeGenerated > ago(30d) | summarize TotalSRSDevices = dcount(Computer)```
5.  **두 번째 타일** 을 정의합니다.<br>
    **범례:** 지난 1시간 내에 하트비트를 보낸 활성 디바이스<br>
    **쿼리:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(1h) | summarize TotalSRSDevices = dcount(Computer)```
6.  **적용** 을 선택합니다.

### <a name="create-a-tile-that-displays-active-devices"></a>활성 디바이스를 표시하는 타일 만들기

1.  **대시보드 보기를** 선택하여 타일 추가를 시작합니다.
2.  갤러리에서 **번호 & 목록** 선택
3.  **일반** 속성을 정의합니다.<br>
    **그룹 제목:** 하트비트 상태<br>
    **새 그룹:** 선택한
4.  **타일** 속성을 정의합니다.<br>
    **범례:** 활성 디바이스(지난 20분 동안 전송된 하트비트)<br>
    **타일 쿼리:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(20m) | summarize AggregatedValue = count() by Computer | count```
5.  **목록** 속성을 정의합니다.<br>
    **목록 쿼리:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(20m) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```
6.  **열 제목** 정의:<br>
    **이름:** 컴퓨터 이름<br>
    **값:** 마지막 하트비트
7.  **탐색 쿼리** 를 정의합니다.<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  **적용** 을 선택한 다음 **닫기를** 선택합니다.

### <a name="create-a-tile-that-displays-devices-that-have-connectivity-issues"></a>연결 문제가 있는 디바이스를 표시하는 타일 만들기

1.  갤러리에서 **번호 & 목록을** 선택한 다음 새 타일을 추가합니다.
2.  **일반** 속성을 정의합니다.<br>
    **그룹 제목:** 비워 둡니다.<br>
    **새 그룹:** 선택되지 않음
3.  **타일** 속성을 정의합니다.<br>
    **범례:** 비활성 디바이스(지난 20분 동안 전송된 하트비트 메시지 없음)<br>
    **타일 쿼리:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize LastHB = max(TimeGenerated) by Computer | where LastHB < ago(20m) | count```
4.  **목록** 속성을 정의합니다.<br>
    **목록 쿼리:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize TimeGenerated = max(TimeGenerated) by Computer | where TimeGenerated < ago(20m) | order by TimeGenerated```
5.  **열 제목** 정의:<br>
    **이름:** 컴퓨터 이름<br>
    **값:** 마지막 하트비트
6.  **탐색 쿼리** 정의:<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
7.  **적용** 을 선택한 다음 **닫기를** 선택합니다.

### <a name="create-a-tile-that-displays-devices-that-have-a-hardware-error"></a>하드웨어 오류가 있는 디바이스를 표시하는 타일 만들기

1.  갤러리에서 **번호 & 목록을** 선택한 다음 새 타일을 추가합니다.
2.  **일반** 속성을 정의합니다.<br>
    **그룹 제목:** 하드웨어 상태<br>
    **새 그룹:** 선택한
3.  **타일** 속성을 정의합니다.<br>
    **범례:** 지난 1시간 동안 하드웨어 오류가 발생한 디바이스<br>
    **타일 쿼리:** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h) | summarize AggregatedValue = count() by Computer | count```
4.  **목록** 속성을 정의합니다.<br>
    **목록 쿼리:** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```
5.  **열 제목** 정의:<br>
    **이름:** 컴퓨터 이름<br>
    **값:** 마지막 오류
6.  **탐색 쿼리** 정의:<br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == 3001 and EventLevelName == "Error" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSConfMicrophoneStatus_CF, SRSConfSpeakerStatus_CF, SRSDefaultSpeakerStatus_CF, SRSCameraStatus_CF, SRSFORDStatus_CF, SRSMotionSensorStatus_CF, SRSHDMIIngestStatus_CF, SRSEventDescription_CF | sort by TimeGenerated desc```
7.  **적용** 을 선택한 다음 **닫기를** 선택합니다.

### <a name="create-a-tile-that-displays-no-loc-textmicrosoft-teams-rooms-operating-system-versions"></a>운영 체제 버전을 표시하는 :::no-loc text="Microsoft Teams Rooms"::: 타일 만들기

1.  갤러리에서 **도넛 & 목록을** 선택한 다음 새 타일을 추가합니다.
2.  **일반** 속성을 정의합니다.<br>
    **그룹 제목:** 운영 체제 세부 정보<br>
    **새 그룹:** 선택한
3.  **헤더** 속성을 정의합니다.<br>
    **제목:** 운영 체제 버전<br>
    **자막:** 특정 OS 버전을 실행하는 디바이스
4.  **Donut** 속성을 정의합니다.<br>
    **쿼리:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize OS_Version = max(SRSOSLongVersion_CF) by Computer | summarize AggregatedValue = count() by OS_Version | sort by OS_Version asc```<br>
    **가운데 텍스트:** 장치<br>
    **작업:** 합계
5.  **목록** 속성을 정의합니다.<br>
    **목록 쿼리:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize SRSOSLongVersion_CF = max(SRSOSLongVersion_CF) by Computer | sort by Computer asc```<br>
    **그래프 숨기기:** 선택한<br>
    **스파크라인 사용:** 선택되지 않음
6.  **열 제목을 정의합니다**.<br>
    **이름:** 컴퓨터 이름<br>
    **값:** 비워 둡니다.
7.  **탐색 쿼리** 를 정의합니다.<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSDisplayName_CF, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  **적용** 을 선택한 다음 **닫기를** 선택합니다.

### <a name="create-a-tile-that-displays-no-loc-textmicrosoft-teams-rooms-application-versions"></a>애플리케이션 버전을 표시하는 :::no-loc text="Microsoft Teams Rooms"::: 타일 만들기

1.  갤러리에서 **도넛 & 목록을** 선택한 다음 새 타일을 추가합니다.
2.  **일반** 속성을 정의합니다.<br>
    **그룹 제목:** :::no-loc text="Microsoft Teams Rooms"::: 애플리케이션 세부 정보<br>
    **새 그룹:** 선택한
3.  **헤더** 속성을 정의합니다.<br>
    **제목:** 애플리케이션 버전<br>
    **자막:** 특정 애플리케이션 버전을 실행하는 디바이스
4.  **Donut** 속성을 정의합니다.<br>
    **쿼리:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize App_Version = max(SRSAppVersion_CF) by Computer | summarize AggregatedValue = count() by App_Version | sort by App_Version asc```<br>
    **가운데 텍스트:** 장치<br>
    **작업:** 합계
5.  **목록** 속성을 정의합니다.<br>
    **목록 쿼리:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize SRSAppVersion_CF = max(SRSAppVersion_CF) by Computer | sort by Computer asc```<br>
    **그래프 숨기기:** 선택한<br>
    **스파크라인 사용:** 선택되지 않음
6.  **열 제목을 정의합니다**.<br>
    **이름:** 컴퓨터 이름<br>
    **값:** 비워 둡니다.
7.  **탐색 쿼리** 를 정의합니다.<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  **적용** 을 선택한 다음 **닫기를** 선택합니다.

### <a name="create-a-tile-that-displays-devices-that-have-an-application-error"></a>애플리케이션 오류가 있는 디바이스를 표시하는 타일 만들기

1.  갤러리에서 **번호 & 목록을** 선택한 다음 새 타일을 추가합니다.
2.  **일반** 속성을 정의합니다.<br>
    **그룹 제목:** 비워 둡니다.<br>
    **새 그룹:** 선택되지 않음
3.  타일 속성을 정의 **합니다** .<br>
    **범례:** 지난 1시간 동안 애플리케이션 오류가 발생한 디바이스<br>
    **타일 쿼리:** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h) | summarize AggregatedValue = count() by Computer | count```
4.  **목록** 속성을 정의합니다.<br>
    **목록 쿼리:** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```
5.  **열 제목을 정의합니다**.<br>
    **이름:** 컴퓨터 이름<br>
    **값:** 마지막 오류
6.  **탐색 쿼리** 를 정의합니다.<br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == 2001 and EventLevelName == "Error" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF | sort by TimeGenerated desc```
7.  **적용** 을 선택한 다음 **닫기를** 선택합니다.

### <a name="create-a-tile-that-displays-devices-that-have-been-restarted"></a>다시 시작한 디바이스를 표시하는 타일 만들기

1.  갤러리에서 **번호 & 목록을** 선택한 다음 새 타일을 추가합니다.
2.  **일반** 속성을 정의합니다.<br>
    **그룹 제목:** 비워 둡니다.<br>
    **새 그룹:** 선택되지 않음
3.  타일 속성을 정의 **합니다** .<br>
    **범례:** 지난 24시간 동안 애플리케이션을 다시 시작한 디바이스 및 다시 시작 횟수<br>
    **타일 쿼리:** ```Event | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | summarize AggregatedValue = count() by Computer | count```
4.  **목록** 속성을 정의합니다.<br>
    **목록 쿼리:** ```Event | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | order by TimeGenerated | summarize AggregatedValue = count(EventID) by Computer```
5.  **열 제목을 정의합니다**.<br>
    **이름:** 컴퓨터 이름<br>
    **값:** 다시 시작 횟수
6.  **탐색 쿼리** 를 정의합니다.<br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
7.  **적용** 을 선택한 다음 **닫기를** 선택합니다.
8.  **저장** 을 선택하여 대시보드를 저장합니다.

이제 보기 만들기를 완료했습니다.

## <a name="configure-alerts-in-no-loc-textazure-monitor"></a>에서 경고 구성 :::no-loc text="Azure Monitor":::
<a name="Alerts"> </a>

:::no-loc text="Azure Monitor"::: 는 콘솔에 문제가 발생할 때 :::no-loc text="Microsoft Teams Rooms"::: 관리자에게 알리기 위해 경고를 발생할 수 있습니다.

:::no-loc text="Azure Monitor"::: 에는 일정한 간격으로 예약된 로그 검색을 통해 실행되는 기본 제공 경고 메커니즘이 포함되어 있습니다. 로그 검색 결과가 특정 조건과 일치하면 경고 레코드가 만들어집니다.

그러면 규칙이 하나 이상의 작업을 자동으로 실행하여 경고를 사전에 알리거나 다른 프로세스를 호출할 수 있습니다. 경고가 있는 가능한 옵션은 다음과 같습니다.
-   전자 메일 보내기
-   HTTP POST 요청을 통해 외부 프로세스 호출
-   서비스에서 Runbook :::no-loc text="Azure Automation"::: 시작

[에서 경고에 :::no-loc text="Azure Monitor":::](/azure/azure-monitor/platform/alerts-unified-log) 대한 자세한 내용은 로그 경고를 참조하세요:::no-loc text="Azure Monitor":::.

> [!NOTE]
> 다음 예제에서는 디바이스에서 :::no-loc text="Microsoft Teams Rooms"::: 하드웨어 또는 애플리케이션 오류를 생성할 때 전자 메일 경고를 보냅니다.

### <a name="configure-an-email-alert-for-no-loc-textmicrosoft-teams-rooms-hardware-issues"></a>하드웨어 문제에 대한 :::no-loc text="Microsoft Teams Rooms"::: 전자 메일 경고 구성

지난 1시간 내에 하드웨어 문제가 발생한 디바이스를 확인하는 :::no-loc text="Microsoft Teams Rooms"::: 경고 규칙을 구성합니다.
1.  포털에 [:::no-loc text="Microsoft Azure":::](https://portal.azure.com) 로그인하고 작업 영역으로 :::no-loc text="Log Analytics"::: 이동하여 선택합니다.

2. 작업 영역으로 이동하고 :::no-loc text="Log Analytics"::: **경고를** 선택한 다음 **새 경고 규칙을** 선택합니다.

3. **조건 추가** 를 선택한 다음 **사용자 지정 로그 검색**

4.  검색 쿼리 텍스트 상자에 다음 쿼리를 입력합니다.<br>
    ```
    Event
    | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h)
    | summarize arg_max(TimeGenerated, *) by Computer
    | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSConfMicrophoneStatus_CF, SRSConfSpeakerStatus_CF, SRSDefaultSpeakerStatus_CF, SRSCameraStatus_CF, SRSFORDStatus_CF, SRSMotionSensorStatus_CF, SRSHDMIIngestStatus_CF, SRSEventDescription_CF
    |sort by TimeGenerated desc
    ```

5.  경고 논리 설정을 구성합니다.<br>
    **총:** 결과 수<br>
    **조건:** 보다 큼<br>
    **임계값:** 0<br>

6. 평가 설정을 구성하고 완료를 선택합니다 **.** <br>
    **기간(분):** 60<br>
    **빈도(분):** 60<br>

7. 작업 그룹 구성:
    1.  **새로 만들기** 선택
    2.  *작업 그룹 이름* 및 *짧은 이름* 필드에 적합한 이름을 제공합니다.
    3.  고유한 *작업 이름을* 지정하고 **Email/SMS/푸시/음성** 을 선택한 다음 **세부 정보 편집** 을 선택합니다.
    4.  **Email** 확인란을 선택하고 경고를 받을 사용자 또는 그룹의 전자 메일 주소를 제공합니다.
    5.  SMS, 음성 통화 또는 둘 다로 알림을 받을 수 있는 전화 번호를 제공할 수도 있습니다.
    6. **확인을** 선택합니다.

8. 경고 전자 메일의 제목 줄을 재정의하려는 경우 **작업을 사용자 지정** 합니다.

9. 규칙 이름 및 설명을 지정합니다.<br>
    **규칙 이름:** :::no-loc text="Microsoft Teams Rooms"::: 하드웨어 오류 경고<br>
    **설명:** 지난 1시간 이내에 하드웨어 문제가 발생한 디바이스 목록<br>

10. 의도한 심각도를 선택하고 규칙이 사용하도록 설정되어 있는지 확인합니다.

11. **경고 규칙 만들기** 를 선택합니다.

### <a name="configure-an-email-alert-for-no-loc-textmicrosoft-teams-rooms-application-issues"></a>애플리케이션 문제에 대한 :::no-loc text="Microsoft Teams Rooms"::: 이메일 경고 구성

동일한 절차를 반복하지만 다음 쿼리를 사용하여 지난 1시간 내에 애플리케이션 문제가 발생한 디바이스를 나열합니다.

 ```
 Event
 | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h)
 | summarize arg_max(TimeGenerated, *) by Computer
 | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF
 | sort by TimeGenerated desc
 ```

이제 경고 정의를 완료했습니다. 위의 예제를 사용하여 추가 경고를 정의할 수 있습니다.

경고가 생성되면 지난 1시간 내에 문제가 발생한 디바이스를 나열하는 전자 메일을 받게 됩니다.

! [샘플 :::no-loc text="Azure Monitor"::: 경고 이메일](.. /media/Deploy-Azure-Monitor-6.png "샘플 :::no-loc text="Azure Monitor"::: 경고 이메일")

## <a name="configure-all-devices-for-no-loc-textazure-monitoring"></a>에 대한 모든 디바이스 구성 :::no-loc text="Azure Monitoring":::
<a name="configure_all_devices"> </a> 대시보드 및 경고가 구성되면 모든 :::no-loc text="Microsoft Teams Rooms"::: 디바이스에서 에이전트를 설정하고 구성 :::no-loc text="Microsoft Monitoring"::: 하여 모니터링 배포를 완료할 수 있습니다.

각 디바이스에 에이전트를 :::no-loc text="Microsoft Monitoring"::: 수동으로 설치하고 구성할 수 있지만 기존 소프트웨어 배포 도구 및 방법을 활용하는 것이 좋습니다.

처음으로 디바이스를 빌드 :::no-loc text="Microsoft Teams Rooms"::: 하는 경우 빌드 프로세스의 일부로 에이전트 설정 및 구성 단계를 포함 :::no-loc text="Microsoft Monitoring"::: 할 수 있습니다. 자세한 내용은 [명령줄을 사용하여 에이전트 설치를 참조하세요](/azure/azure-monitor/platform/agent-windows#install-the-agent-using-the-command-line).

### <a name="deploying-no-loc-textmicrosoft-monitoring-agent-by-using-a-group-policy-object-gpo"></a>:::no-loc text="Microsoft Monitoring"::: GPO(그룹 정책 개체)를 사용하여 에이전트 배포

구현:::no-loc text="Azure Monitoring":::하기 전에 디바이스를 이미 배포한 :::no-loc text="Microsoft Teams Rooms"::: 경우 제공된 스크립트를 사용하여 그룹 정책 개체를 사용하여 :::no-loc text="Active Directory"::: 에이전트를 설정하고 구성할 수 있습니다.

1.  공유 네트워크 경로를 만들고 **도메인 컴퓨터** 그룹에 대한 읽기 권한을 부여합니다.

2.  64비트 버전의 :::no-loc text="Microsoft Monitoring"::: 에이전트를 다운로드합니다.:::no-loc text="Windows":::<https://go.microsoft.com/fwlink/?LinkID=517476>

3.  설치 패키지의 콘텐츠를 네트워크 공유에 추출합니다.
    1.  명령 프롬프트 창을 열고 **MMASetup-AMD64.exe /c** 를 실행합니다.
    2.  방금 만든 공유를 지정하고 콘텐츠를 추출합니다.

4.  새 그룹 정책 개체를 만들고 컴퓨터 계정이 있는 :::no-loc text="Microsoft Teams Rooms"::: 조직 구성 단위에 할당합니다.

5.  PowerShell 실행 정책 구성:
    1.  새로 만든 그룹 정책 개체를 편집하고 컴퓨터 구성 \\ 정책 \\ 관리 템플릿 :::no-loc text="Windows"::: \\ 구성 요소로 이동합니다.\\ :::no-loc text="Windows PowerShell":::
    2.  **스크립트 실행을 켜** 고 **실행 정책을** 설정하여 **로컬 스크립트를 허용합니다**.

6.  시작 스크립트를 구성합니다.
    1.  다음 스크립트를 복사하고 Install-MMAgent.ps1 저장합니다.
    2.  구성과 일치하도록 WorkspaceId, WorkspaceKey 및 SetupPath 매개 변수를 수정합니다.
    3.  동일한 그룹 정책 개체를 편집하고 컴퓨터 구성 \\ 정책 \\ :::no-loc text="Windows"::: 설정 \\ 스크립트로 이동합니다(시작/종료).
    4.  두 번 클릭하여 **시작을** 선택한 다음 **, PowerShell 스크립트를** 선택합니다.
    5.  **파일 표시** 를 선택한 다음 **Install-MMAgent.ps1** 파일을 해당 폴더에 복사합니다.
    6.  **추가** 를 선택한 다음 **찾아보기를** 선택합니다.
    7.  방금 복사한 ps1 스크립트를 선택합니다.

7.  :::no-loc text="Microsoft Teams Rooms"::: 는 두 번째 재부팅을 사용하여 :::no-loc text="Microsoft Monitoring"::: 에이전트를 설치하고 구성해야 합니다.

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
> 에이전트를 다시 구성하거나, 다른 작업 영역으로 이동하거나, 초기 설치 후 프록시 설정을 수정해야 하는 경우 에이전트 [관리 및 유지 관리 :::no-loc text="Log Analytics":::](/azure/azure-monitor/platform/agent-manage) 문서를 참조할 수 있습니다.

## <a name="additional-solutions"></a>추가 솔루션
<a name="Solutions"> </a>

:::no-loc text="Azure Monitor"::: 에서는 환경 모니터링에 도움이 되도록 [솔루션 갤러리](/azure/azure-monitor/insights/solutions) 를 통해 기본 제공 관리 솔루션을 제공합니다. 작업 영역에 [도 경고 관리](/azure/azure-monitor/platform/alert-management-solution) 및 [:::no-loc text="Azure Log Analytics"::: 에이전트 상태](/azure/azure-monitor/insights/solution-agenthealth) 솔루션을 추가하는 것이 좋습니다.

> [!NOTE]
> 에이전트 상태 솔루션은 사용자 환경 내에서 오래되었거나 손상된 :::no-loc text="Microsoft Monitoring"::: 에이전트를 식별하는 데 도움이 될 수 있으며 경고 관리 솔루션은 지정된 기간 내에 발생한 경고에 대한 세부 정보를 제공합니다.

## <a name="see-also"></a>참고 항목

[을 사용하여 관리 계획 :::no-loc text="Microsoft Teams Rooms"::::::no-loc text="Azure Monitor":::](azure-monitor-plan.md)

[를 사용하여 디바이스 관리 :::no-loc text="Microsoft Teams Rooms"::::::no-loc text="Azure Monitor":::](azure-monitor-manage.md)
