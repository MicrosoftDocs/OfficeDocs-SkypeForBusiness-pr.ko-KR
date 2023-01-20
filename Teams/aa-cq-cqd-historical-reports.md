---
title: 자동 전화 교환 및 통화 큐 기록 보고서가 업데이트됨
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.reviewer: colongma
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Reporting
- ms.teamsadmincenter.directrouting.cqd
- ms.lync.lac.ToolsCallQualityDashboard
description: 업데이트된 Teams 자동 전화 교환 & 통화 큐 기록 보고서 Power BI 보고서를 사용하여 자동 전화 교환 및 통화 큐 기록 데이터를 보는 방법에 대해 알아봅니다.
ms.openlocfilehash: dad1fa07d476aa5bcfa1e39818d9d7a01b7fdc56
ms.sourcegitcommit: 776820a6c927fafabdfad9f50654fe7648d77bf3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/20/2023
ms.locfileid: "69845915"
---
# <a name="auto-attendant-and-call-queue-historical-reports"></a>자동 전화 교환 및 통화 큐 기록 보고서

>[!NOTE]
> GCC HIgh 및 DOD 고객은 [CQD(통화 큐 기록 보고서)& 자동 전화 교환](aa-cq-cqd-historical-reports-v163.md)의 V1.63을 계속 사용해야 합니다.

이 Power BI 템플릿은 조직에서 자동 전화 교환 및 통화 큐에서 처리되는 통화 수를 보고할 수 있는 세 가지 보고서를 제공합니다.  또한 에이전트 성능 인사이트를 제공합니다.

## <a name="v305-published-on-january-9-2023"></a>2023년 1월 9일에 게시된 V3.0.5

Teams 자동 전화 교환 & 통화 큐 기록 보고서 Power BI 템플릿은 다음 세 가지 보고서를 제공합니다.

- [자동 전화 교환](media/aa-cq-historical-report-sample-aa-v305.png) 보고서에는 자동 전화 교환으로 들어오는 통화에 대한 분석이 표시됩니다.
- [통화 큐 보고서에는 통화 큐](media/aa-cq-historical-report-sample-cq-v305.png)로 들어오는 통화에 대한 분석이 표시됩니다.
- [에이전트 타임라인](media/aa-cq-historical-report-sample-at-v305.png) 보고서에는 통화 큐 호출에서 활성 상태인 에이전트의 타임라인 보기가 표시됩니다.

이러한 보고서는 VAAC(음성 애플리케이션 분석 수집기) 서비스의 데이터를 사용합니다.

## <a name="v3xx-prerequisites"></a>V3.x.x 필수 구성 요소

### <a name="power-bi-desktop"></a>Power BI Desktop

Power BI Desktop 설치해야 합니다. [Microsoft Windows 스토어](https://aka.ms/pbidesktopstore)에서 무료 버전을 설치하고 사용할 수 있습니다.

호환되는 최소 버전은 2.85.681.0(2020년 9월)입니다.

### <a name="permissions-to-access-the-cqd-pipeline"></a>CQD 파이프라인에 액세스할 수 있는 권한

이 버전의 보고서는 CQD(통화 품질 대시보드) 데이터 파이프라인을 사용하지 않지만 기록 데이터를 보는 데 사용되는 계정에는 통화 품질 대시보드에 대한 액세스 권한이 여전히 필요합니다. 자세한 내용은 [CQD 액세스 역할을 참조하세요](./turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd).

**보고서 보기** 및 **EUIII 보기 필드** 가 **모두 예로** 설정된 CQD 역할은 모두 작동합니다.

- 이 요구 사항은 향후 릴리스에서 제거될 예정입니다.

## <a name="v3xx-installation"></a>V3.x.x 설치 

다음 단계에서는 컴퓨터에 Power BI Desktop 이미 설치했으며 계정에 CQD 데이터 파이프라인에 액세스하는 데 필요한 권한이 있다고 가정합니다.

다음 단계를 수행합니다.

1. [Teams 자동 전화 교환 & 통화 큐 기록 보고서 V3.0.5.zip](https://www.microsoft.com/download/details.aspx?id=104623) 파일을 다운로드하여 컴퓨터에 저장합니다.

2. zip 파일을 엽니다.

3. `Teams Auto Attendant & Call Queue Historical Reports V3.0.5.pbit` 템플릿 파일을 엽니다. Power BI Desktop 시작되어야 합니다.

4. **데이터 원본** 을 선택하라는 메시지가 표시됩니다.  `api.interfaces.records.teams.microsoft.com` 항목을 선택합니다.

  :::image type="content" source="media/aa-cq-historical-report-01-v305.png" alt-text="api.interfaces.records.teams.microsoft.com Data Soure를 선택하는 스크린샷":::

5. 계정으로 로그인하라는 메시지가 표시됩니다. **조직 계정을** 선택한 다음 **로그인을** 선택합니다.

  :::image type="content" source="media/aa-cq-historical-report-03-v300.png" alt-text="V3.0.0에 대한 로그인을 보여 주는 스크린샷":::

6. **연결을** 선택하면 데이터가 새로 고쳐집니다.

> [!NOTE]
> v1.63 이하를 사용하는 경우 v3.x.x가 VAAC에서 데이터를 검색하려고 할 때 오류가 발생할 수 있습니다.  이 오류를 해결하려면 Power BI에서 이전 자격 증명을 지워야 합니다.
> 
> 1. v3.x.x 템플릿을 열어 오류를 지웁합니다. 
> 1. **파일** > **옵션 & 설정** > **데이터 원본 설정을** 선택합니다.
> 1. **삭제 권한** 에 대한 드롭다운을 선택한 다음 **모든 권한 지우기를** 선택합니다.
> 1. 템플릿이 지워진 후 템플릿을 닫고 Power BI를 다시 시작합니다. 다시 권한을 부여하라는 메시지가 표시됩니다. 

## <a name="data-latency-for-auto-attendant-and-call-queue-analytics"></a>자동 전화 교환 및 통화 큐 분석에 대한 데이터 대기 시간

데이터는 일반적으로 호출이 완료된 후 30분 이내에 사용할 수 있습니다. 그러나 데이터가 표시되는 데 몇 시간이 걸릴 수 있는 경우가 있습니다. 

새 데이터를 보려면 데이터를 새로 고쳐야 합니다.

## <a name="auto-attendant-and-call-queue-historical-reports-definitions"></a>자동 전화 교환 및 통화 큐 기록 보고서 정의

### <a name="cloud-auto-attendant-analytics-report"></a>클라우드 자동 전화 교환 분석 보고서

#### <a name="report-description"></a>보고서 설명

|보고서 섹션                          |설명                                                       |
|:---------------------------------------|:-----------------------------------------------------------------|
|들어오는 호출 원본                    |내부/외부 호출 원본별 호출 배포            |
|디렉터리 검색 방법                 |검색 유형별 호출 배포                              |
|호출자 작업 수                     |통화 중에 사용되는 번호 동작별 호출 분포       |
|AA의 평균 초                   |호출자가 AA에서 소비하는 평균 시간(초)                 |
|평균 호출자 작업                  |호출자가 AA에서 수행하는 평균 작업 수               |
|호출 결과                            |최종 호출 상태별 호출 배포                         |
|보고서의 아래쪽 섹션                 |통화 흐름 분석                                               |

#### <a name="report-visual-and-field-mapping"></a>시각적 개체 및 필드 매핑 보고

|보고서 탭            |보고서 테이블 이름     |전역 필터                          |
|:---------------------|:---------------------|:--------------------------------------|
|자동 전화 교환        |fAutoAttendant        |없음                                   |

|보고서 섹션                               |사용된 필드                                                                                    |적용된 필터 |
|:--------------------------------------------|:------------------------------------------------------------------------------------------------|:----------|
|날짜 선택기                                |AAStartTime                                                                                      |없음       |
|시간 범위 선택기                          |AAStartHour                                                                                      |없음       |
|자동 전화 교환 리소스 계정             |AA 이름                                                                                          |없음       |
|들어오는 호출 원본                         |호출 유형<br>TotalCallCount의 합계         |외부 호출: 호출 유형이 외부입니다.<br>내부 호출: 호출 유형이 내부입니다. |
|디렉터리 검색 방법                      |AADirectorySearchMethod<br>AADirectorySearchMethodLegend<br>TotalCallCount  |AADirectorySearchMethod가 abs_search_dtmf 또는 abs_search_name    |
|호출자 작업 수                          |AACallerActionCount<br>TotalCallCount                                                            |없음       |
|AA의 평균 초                        |AAChainDuration                                                                                  |없음       |
|평균 호출자 작업                       |AACallerActionCount                                                                              |없음       |
|호출 결과                                 |AACallResult<br>AACallResultLegend<br>TotalCallCount                                             |없음       |
|보고서의 아래쪽 섹션                      |MM-DD<br>AA 이름<br>AACallFlow<br>호출 유형<br>AACallResult<br>TotalCallCount<br>AAChainDuration |없음       |

#### <a name="fautoattendant-field-description"></a>fAutoAttendant 필드 설명

|이름                                    |데이터 형식                |설명                            |
|:---------------------------------------|:------------------------|:--------------------------------------|
|AA 이름                                 |텍스트                     |자동 전화 교환에 연결된 리소스 계정의 이름<br><br>전체 리소스 계정 이름이 **aa_test@microsoft.com** 경우 이 값은 **aa_test** |
|AA 시작 시간 UTC                       |날짜/시간                |자동 전화 교환 통화 시작 시간 - UTC                                                     |
|AACallerActionCount                     |정수             |요약: 합계<br>통화 중 자동 전화 교환에서 호출자가 선택한 작업 수  |
|AACallerActionCount(측정값)           |정수             |비어 있는 대신 호출이 없으면 AACallerActionCount가 0인 경우를 제외하고 AACallerActionCount와 동일합니다.                |
|AACallFlow                              |텍스트                     |자동 전화 교환 차원 -> AutoAttendantCallFlow를 참조하세요.                                   |
|AACallResult                            |텍스트                     |자동 전화 교환 차원 -> AutoAttendantCallResult를 참조하세요.                                 |
|AACallResultLegend                      |텍스트                     |AACallResult를 기반으로 범례 항목 설정                                               |
|AAChainDuration                         |10진수           |요약: 합계<br>자동 전화 교환의 통화 기간                                     |
|AAChainDuration(측정값)               |10진수           |비어 있는 대신 호출이 없으면 AAChainDuration이 0인 경우를 제외하고 AAChainDuration과 동일합니다.                    |
|AAChainIndex                            |정수             |                                                                                         |
|AAConnectivityType                      |텍스트                     |일반 차원 -> PSTNConnectivityType을 참조하세요.                                            |
|AACount                                 |정수             |통화에 관련된 자동 전화 교환 수                                               |
|AADirectorySearchMethod                 |텍스트                     |자동 전화 교환 차원 -> AutoAttendantDirectorySearchMethod를 참조하세요.                      |
|AADirectorySearchMethodLegend           |텍스트                     |AADirectorySearchMethod를 기반으로 범례 항목 설정                                    |
|AAStartHour                             |정수             |자동 전화 교환 통화 시작 시간                                                           |
|AAStartTime                             |날짜/시간                |자동 전화 교환 통화 시작 시간                                                           |
|AATransferAction                        |텍스트                     |자동 전화 교환 차원 -> AutoAttendantTransferAction을 참조하세요.                             |
|통화 기간 초                   |정수             |통화 기간                                                                            |
|통화 종료 시간 로컬                     |날짜/시간                |통화 종료 시간 - 로컬(보고서를 실행하는 컴퓨터의 표준 시간대 기준)                    |
|통화 종료 시간 UTC                       |날짜/시간                |통화 종료 시간 - UTC                                                                      |
|통화 시작 시간 로컬                   |날짜/시간                |통화 시작 시간 - 로컬(보고서를 실행하는 컴퓨터의 표준 시간대 기준)                  |
|통화 시작 시간 UTC                     |날짜/시간                |통화 시작 시간 - UTC                                                                    |
|호출 유형<sup>1</sup>                   |텍스트                     |Common Dimensions -> PSTNCallType을 참조하세요.                                                    |
|ConferenceID                            |텍스트                     |문제 해결 목적으로 사용됨 - 티켓을 열 때 이 정보를 제공합니다.       |
|DialogID                                |텍스트                     |문제 해결 목적으로 사용됨 - 티켓을 열 때 이 정보를 제공합니다.       |
|DocumentID                              |텍스트                     |문제 해결 목적으로 사용됨 - 티켓을 열 때 이 정보를 제공합니다.       |
|MM-DD                                   |텍스트                     |자동 전화 교환 통화 월-일                                                            |
|PSTNMinutes                             |정수             |요약: 합계<br>총 분 사용량                                                     |
|TotalCallCount의 합계(측정값)         |정수             |빈 호출이 아닌 호출이 없으면 TotalCallCount가 0인 경우를 제외하고 TotalCallCount와 동일합니다.                     |
|TotalCallCount                          |정수             |요약: 합계<br>Always 1 - 모든 호출의 합계를 제공하는 데 사용됩니다.                            |


### <a name="cloud-call-queue-analytics-report"></a>Cloud Call Queue Analytics 보고서

#### <a name="report-description"></a>보고서 설명

|보고서 섹션                          |설명                                                        |
|:---------------------------------------|:------------------------------------------------------------------|
|들어오는 호출 원본                    |내부/외부 호출 원본별 호출 배포             |
|평균 대기 시간(초)             |응답된 통화 및 중단된 통화 대기 시간                         |
|통화 볼륨 및 에이전트 옵트인 수      |통화 큐별 호출 배포/최대 에이전트 옵트인 수  |
|호출 결과                            |호출 결과별 호출 분포                               |
|중단된 통화                         |통화 큐별 중단된 호출 배포                     |
|평균 세션 길이(초)        |호출 결과별로 그룹화된 통화 길이(초)                      |
|오버플로/시간 제한 대상 호출      |시간이 초과되거나 오버플로된 호출 배포                 |


#### <a name="report-visual-and-field-mapping"></a>시각적 개체 및 필드 매핑 보고

|보고서 탭            |보고서 테이블 이름                                   |전역 필터       |
|:---------------------|:---------------------------------------------------|:-------------------|
|통화 큐            |fCallQueueAnalytics<br>fCallQueueFinalStateAction   |없음                |

|보고서 섹션                      |테이블 -> 필드 사용                |적용된 필터       |
|:-----------------------------------|:-------------------------------------|:---------------------|
|날짜 선택기                       |fCallQueueAnalytics -> 날짜           |없음                  |
|시간 범위 선택기                 |fCallQueueAnalytics -> CQHour         |없음                  |
|큐 리소스 계정 호출         |fCallQueueAnalytics -> CQ 이름        |없음                  |
|들어오는 호출 원본                |fCallQueueAnalytics -> 호출 수의 합계(측정값)  |외부 호출: 호출 유형이 외부입니다.<br>내부 호출: 호출 유형이 내부입니다. |
|평균 대기 시간(초)-답변 전 |fCallQueueFinalStateAction -> 평균 CQ 기간의 평균(측정값) |호출 큐 호출 결과가 agent_joined_conference 또는 transferred_to_agent|
|평균 대기 시간(초)-중단 전 |fCallQueueFinalStateAction -> 평균 호출 기간의 평균(측정값) |호출 큐 호출 결과가 agent_joined_conference, transferred_to_agent, 오버플로, timed_out |
|통화 볼륨 및 에이전트 Opt-In 수   |fCallQueueAnalytics -> 통화 수<br>fCallQueueAnalytics -> 통화 큐 에이전트 옵트인 수<br>fCallQueueAnalytics -> CQ 이름<br>fCallQueueAnalytics -> 날짜 |없음 |
|중단된 통화                     |fCallQueueAnalytics -> 날짜<br>fCallQueueAnalytics -> TotalCallCount | 호출 큐 호출 결과 범례가 중단됨 |
|평균 세션 길이(초)    |fCallQueueFinalStateAction -> 평균 통화 큐 기간(초)<br>호출 큐 호출 결과 범례 |평균 통화 큐 기간(초) > 0 |
|오버플로/시간 제한 대상 호출  |fCallQueueAnalytics -> 통화 수<br>fCallQueueAnalytics -> 호출 큐 대상 유형<br>fCallQueue 대상 형식 범례 |호출 큐 대상 유형 범례에 중단됨 및 에이전트 응답이 포함되지 않음 |


#### <a name="fcallqueueanalytics-field-description"></a>fCallQueueAnalytics 필드 설명

|이름                                    |데이터 형식                |설명                                                                              |
|:---------------------------------------|:------------------------|:----------------------------------------------------------------------------------------|
|호출 수                              |정수             |요약: 합계<br>호출 수                                                        |
|통화 기간 초                   |정수             |통화 기간                                                                            |
|통화 종료 시간 로컬                     |날짜/시간                |통화 종료 시간 - 로컬(보고서를 실행하는 컴퓨터의 표준 시간대 기준)                    |
|통화 종료 시간 UTC                       |날짜/시간                |통화 종료 시간 - UTC                                                                      |
|통화 큐 에이전트 수                  |정수             |요약: 합계<br>호출 큐에 구성된 에이전트 수                          |
|통화 큐 에이전트 옵트인 수           |정수             |요약: 합계<br>통화 큐에 옵트인된 에이전트 수                            |
|통화 큐 호출 결과                  |텍스트                     |통화 큐 차원 -> CallQueueCallResult를 참조하세요.                                         |
|호출 큐 호출 결과 범례           |텍스트                     |통화 큐 결과에 따라 범례 항목 설정                                          |
|호출 큐 대상 유형                  |텍스트                     |Call Queue Dimensions -> CallQueueTargetType을 참조하세요.                                         |
|호출 큐 대상 형식 범례           |텍스트                     |통화 큐 대상 유형에 따라 범례 항목 설정                                     |
|통화 시작 시간 로컬                   |날짜/시간                |통화 시작 시간 - 로컬(보고서를 실행하는 컴퓨터의 표준 시간대 기준)                  |
|통화 시작 시간 UTC                     |날짜/시간                |통화 시작 시간 - UTC                                                                    |
|호출 유형                               |텍스트                     |Common Dimensions -> PSTNCallType을 참조하세요.                                                    |
|ConferenceID                            |텍스트                     |문제 해결 목적으로 사용됨 - 티켓을 열 때 이 정보를 제공합니다.       |
|CQ 이름                                 |텍스트                     |통화 큐에 연결된 리소스 계정의 이름<br><br>전체 리소스 계정 이름이 **cq_test@microsoft.com** 경우 이 값은 **cq_test** |
|CQ 시간                                 |정수             |통화 큐 호출 시작 시간                                                               |
|날짜                                    |날짜/시간                |통화 큐 호출 시작 날짜 및 시간(시간)                                               | 
|DateTimeCQName                          |텍스트                     |fCallQueueFinalStateAction에서 필터링하기 위한 고유 키                                   |
|DialogID                                |텍스트                     |문제 해결 목적으로 사용됨 - 티켓을 열 때 이 정보를 제공합니다.       |
|DocumentID                              |텍스트                     |문제 해결 목적으로 사용됨 - 티켓을 열 때 이 정보를 제공합니다.       |
|PSTN 연결 유형                  |텍스트                     |Common Dimensions -> PSTNConnectivityType을 참조하세요.                                            |
|PSTN 총 시간(분)                      |정수             |요약: 합계<br>PSTN 호출의 총 시간(분) 사용량                                     |
|호출 수의 합계(측정값)             |정수             |호출 수와 같지만 호출이 없는 경우 0이 됩니다.                                        |
|TotalCallCount(측정값)                |정수             |요약: 합계<br>호출 수                                                             |


#### <a name="fcallqueuefinalstateaction-field-description"></a>fCallQueueFinalStateAction 필드 설명

|이름                                    |데이터 형식                |설명                                                                |
|:---------------------------------------|:------------------------|:--------------------------------------------------------------------------|
|평균 호출 기간(초)         |10진수           |요약: 합계<br>중단된 호출의 평균 통화 기간(초)     |
|평균 통화 큐 기간(초)       |10진수           |요약: 합계<br>응답된 통화의 평균 대기 시간(초)       |
|평균 호출 기간(측정값)  |정수             |평균 호출 기간(초)과 같지만 호출이 없는 경우 0이 됩니다.    |
|평균 CQ 기간의 평균(측정값)    |정수             |평균 통화 큐 기간(초)과 같지만 호출이 없는 경우 0이 됩니다.  |
|호출 수                              |정수             |요약: 합계<br>호출 수                                          |
|통화 큐 호출 결과                  |텍스트                     |통화 큐 차원 -> CallQueueCallResult를 참조하세요.                           |
|호출 큐 호출 결과 범례           |텍스트                     |통화 큐 호출 결과에 따라 범례 항목 설정                       |
|큐 최종 상태 작업 호출           |텍스트                     |Call Queue Dimensions -> CallQueueFinaleStateAction을 참조하세요.                    |
|CQ 이름                                 |텍스트                     |통화 큐에 연결된 리소스 계정의 이름<br><br>전체 리소스 계정 이름이 **cq_test@microsoft.com** 경우 이 값은 **cq_test** |
|CQ 시간                                 |수                   |통화가 발생한 시간
|날짜                                    |날짜/시간                |통화 큐 호출 시작 날짜 및 시간(시간)                                 |
|DateTimeCQName                          |텍스트                     |fCallQueueFinalStateAction에서 필터링하기 위한 고유 키                     |
|IsAbandoned                             |True/false               |에이전트가 전화를 받지 않으면 True입니다.                                    |


### <a name="cloud-call-queue-agent-timeline-report"></a>클라우드 호출 큐 에이전트 타임라인 보고서

#### <a name="report-description"></a>보고서 설명

|보고서 섹션                                          |설명                                                         |
|:-------------------------------------------------------|:-------------------------------------------------------------------|
|에이전트별 호출 수                                |통화 큐 및 에이전트별 통화 배포                       |
|에이전트 및 모든 큐별 배포                     |에이전트 및 통화 큐별 통화 배포                       |
|표(왼쪽 아래)                                     |평균 및 총 통화 기간을 가진 에이전트별 호출 분포 |
|에이전트별 평균 통화 기간(초) (오른쪽 아래) |에이전트별 평균 호출 기간(초)                         |

#### <a name="report-visual-field-mapping"></a>시각적 개체 필드 매핑 보고

|보고서 탭            |보고서 테이블 이름           |전역 필터       |
|:---------------------|:---------------------------|:-------------------|
|에이전트 타임라인        |fAgentTimelineAnalytics     |없음                |


|보고서 섹션                                |사용된 필드                         |적용된 필터       |
|:---------------------------------------------|:-------------------------------------|:---------------------|
|날짜 선택기                                 |Datetime                              |없음                  |
|에이전트 사용자 이름 선택기                       |에이전트 이름                            |없음                  |
|큐 리소스 계정 선택기 호출         |CQ 이름                               |없음                  |
|에이전트별 호출 수                      |호출 수<br>에이전트 이름<br>날짜<br>시간      |없음                  |
|에이전트 및 통화 큐별 배포          |에이전트 이름<br>평균 호출 기간(초)<br>호출 수<br>CQ 이름 |없음                      |
|왼쪽 아래                                   |에이전트 이름<br>평균 호출 기간(초)<br>호출 수<br>통화 기간(분)<br>CQ 이름<br>시간<br>MM-DD | 없음 |
|에이전트별 평균 통화 기간(초)      |에이전트 이름<br>평균 호출 기간(초) | 없음 |

#### <a name="fagenttimelineanalytics-field-description"></a>fAgentTimelineAnalytics 필드 설명

|이름                                    |데이터 형식                |설명                                         |
|:---------------------------------------|:------------------------|:---------------------------------------------------|
|에이전트 이름                              |텍스트                     |사용자 UPN<br>전체 사용자 이름이 **user@microsoft.com** 경우 이 값은 **사용자** 입니다. |
|평균 호출 기간(초)         |10진수           |요약: 합계<br>응답된 통화 큐 호출의 평균 기간(초) |
|통화 기간(분)                 |정수             |요약: 합계<br>응답된 통화 큐 통화의 총 통화 기간(분)(가장 가까운 분으로 반올림)  |
|응답된 통화                          |정수             |에이전트가 응답한 통화 수                        |
|응답되지 않은 통화                      |정수             |에이전트가 응답하지 않는 통화 수                    |
|CQ 이름                                 |텍스트                     |통화 큐에 연결된 리소스 계정의 이름<br><br>전체 리소스 계정 이름이 **cq_test@microsoft.com** 경우 이 값은 **cq_test** |
|날짜                                    |날짜                     |통화 날짜                                             |
|Datetime                                |Datetime                 |통화 날짜                                             |
|시간                                    |정수             |통화 시간                                             |
|MM-DD                                   |텍스트                     |통화 월 및 일                                    |
|총 호출 수                        |정수             |요약: 합계<br>에이전트에 표시되는 호출 수     |

> [!NOTE]
> 호출이 첫 번째 호출 큐에 도착하면 해당 큐에서 이미 대기 중인 호출 수가 **통화 오버플로 처리** 제한에 도달하고 리디렉션 옵션이 두 번째 호출 큐에 새 호출을 보내는 경우 두 번째 통화 큐의 에이전트는 이 보고서의 첫 번째 통화 큐에 있는 것으로 표시됩니다. 

## <a name="known-issues"></a>알려진 문제

- **통화 큐** 보고서의 **통화 결과** 시각적 개체는 많은 수의 **_알 수 없는_** 호출을 보고할 수 있습니다. 이는 지원에서 수정하기 위해 작업 중인 호출 분류 문제 때문입니다.  이는 호출 분류 문제일 뿐이며 이러한 호출은 시스템에서 성공적으로 처리되었습니다.

- 첫 번째 자동 전화 교환 또는 통화 큐에서 호출에 응답하는 호출 및 호출자 작업만 보고됩니다.  연결된 자동 전화 교환(한 자동 전화 교환이 다른 자동 전화 교환으로 전송되는 경우) 또는 연결된 통화 큐(한 통화 큐가 다른 통화 큐로 전송되는 경우)의 통화 및 호출자 작업은 보고되지 않습니다. 

- 통화 큐 및 자동 전화 교환은 통화 큐 또는 자동 전화 교환 이름 대신 리소스 계정의 ID로 표시됩니다.  자동 전화 교환 또는 통화 큐에 대한 모든 트래픽을 표시하려면 자동 전화 교환 또는 통화 큐에 할당된 모든 리소스 계정을 선택해야 합니다.

- 통화 큐 및 자동 전화 교환 데이터는 개인 데이터로 간주되며 데이터 개인 정보 보존 정책의 적용을 받기 때문에 대시보드에서 28일의 기록만 사용할 수 있습니다.

- 일부 시나리오에서는 **클라우드 통화 큐 에이전트 타임라인** 보고서에서 에이전트가 응답한 통화 수가 Teams 클라이언트 통화 기록에 표시된 통화 수와 다를 수 있습니다. Teams 클라이언트 호출 기록이 올바르습니다. 지원은 조사 중이지만 현재 복구할 수 있는 예상 시간은 없습니다.

## <a name="customization"></a>사용자화 

다양한 시각화에 표시할 필드 추가 또는 제거, 차트 종류 변경 등 보고서의 특정 시각화 측면을 사용자 지정할 수 있습니다.

### <a name="change-color-schema"></a>색 스키마 변경 

다음 단계에서는 설치 단계를 이미 완료한 것으로 가정합니다.

다음 단계를 수행합니다.

1. 리본에서 **보기 탭** 을 선택합니다.

  :::image type="content" source="media/aa-cq-historical-report-04.png" alt-text="보기 탭을 선택하여 색 구성표를 변경하는 스크린샷":::

2. 드롭다운 목록에서 색 스키마를 선택합니다.

  :::image type="content" source="media/aa-cq-historical-report-05.png" alt-text="다양한 색 구성표를 보여 주는 스크린샷":::
  
## <a name="dimensions-and-measurements"></a>차원 및 측정값

다음 차원 및 측정값을 사용할 수 있습니다.

### <a name="common-dimensions"></a>일반 차원

이러한 차원은 자동 전화 교환 및 통화 큐에 공통적으로 적용됩니다.

|이름(형식)                                            |가능한 값                |설명                                                       |
|:------------------------------------------------------|:------------------------------|:-----------------------------------------------------------------|
|ConferenceId<br>(텍스트)                                 |Guid                           |호출 식별자                                                   |
|날짜<br>(DateTime)                                     |                               |통화 날짜(UTC)                                                |
|DialogId<br>(텍스트)                                     |Guid                           |호출 식별자                                                   |
|DocumentId<br>(텍스트)                                   |Guid                           |호출 식별자                                                   |
|기간<br>(정수)                             |                               |통화 기간(초)                                      |
|Endtime<br>(DateTime)                                  |                               |통화 종료 시간(UTC)                                             |
|FirstIsCaller<br>(부울)                             |                               |[첫 번째 및 두 번째 엔드포인트 분류](dimensions-and-measures-available-in-call-quality-dashboard.md)     |
|FirstUPN<br>(텍스트)                                     |                               |첫 번째 엔드포인트 사용자의 UPN(사용자 계정 이름)        |
|시간<br>(텍스트)                                         |                               |시간 호출 시작(UTC)                                           |
|분<br>(텍스트)                                       |                               |분 호출 시작(UTC)                                         |
|PSTNCallDuration<br>(정수)                     |                               |통화 기간                                              |
|PSTNCallType<br>(텍스트)                                 |                               |                                                                  |
|                                                       |외부                       |테넌트 외부에서 전화가 걸려오고 있습니다.                            |
|                                                       |내부                       |테넌트 내에서 호출이 수신됩니다.                             |
|PSTNConnectivityType<sup>1</sup><br>(텍스트)             |                               |                                                                  |
|                                                       |CallingPlan                    |                                                                  |
|                                                       |DirectRouting                  |                                                                  |
|두 번째<br>(텍스트)                                       |                               |두 번째 호출 시작(UTC)                                         |
|SecondUPN<br>(텍스트)                                    |                               |두 번째 엔드포인트 사용자의 UPN(사용자 계정 이름)       |
|TenantId<br>(텍스트)                                     |                               |테넌트 ID                                                         |
|타임 스탬프<br>(DateTime)                                |                               |기록된 시간 레코드(UTC)                                     |
|UserStartTimeUTC<br>(DateTime)                         |                               |시간 호출 시작(UTC)                                           |

- <sup>1</sup> **PSTNConnectivityType** 은 초기 호출 레그 원본이 아닌 최종 호출 레그 소스를 표시합니다. 예를 들어 자동 전화 교환이 외부 전화를 받고 다른 자동 전화 교환 또는 통화 큐로 통화를 전송하는 경우 **들어오는 통화 원본** 이 **내부** 로 보고됩니다.


### <a name="auto-attendant-dimensions"></a>자동 전화 교환 차원

|이름(형식)                                            |가능한 값                |설명                                                       |
|:------------------------------------------------------|:------------------------------|:-----------------------------------------------------------------|
|AutoAttendantCallFlow<br>(텍스트)                        |                               |자동 전화 교환 호출의 다양한 상태를 캡슐화합니다.          |
|                                                       |abs_search                     |                                                                  |
|                                                       |발표                   |                                                                  |
|                                                       |automatic_menu                 |                                                                  |
|                                                       |call_termination               |                                                                  |
|                                                       |call_transfer                  |                                                                  |
|                                                       |first_level_menu               |                                                                  |
|                                                       |main_menu                      |                                                                  |
|                                                       |speech_input_confirmation      |                                                                  |
|                                                       |user_selection                 |                                                                  |
|AutoAttendantCallResult<br>(텍스트)                      |                               |최종 호출 결과                                                 |
|                                                       |failed_to_establish_media      |통화의 미디어 부분을 설정할 수 없습니다.             |
|                                                       |failover_to_operator           |일반적으로 시스템 오류로 인해 운영자에게 전송된 호출      |
|                                                       |oaa_chain_too_long             |AA에서 다리가 너무 많습니다.                                           |
|                                                       |oaa_session_too_long           |AA 세션이 너무 오래 지속됨                                    |
|                                                       |service_declined               |AA가 통화를 수락하지 않았습니다.                                         |
|                                                       |service_terminated             |AA 구성이 전화를 끊거나 전화를 끊습니다.             |
|                                                       |terminated_automatic_selection |AA 구성이 호출 연결을 끊습니다.                           |
|                                                       |terminated_no_operator         |연산자가 정의되지 않은 오류로 인해 모두 종료됨                   |
|                                                       |terminated_transfer_failed     |전송 실패로 종료된 호출 - 일반적으로 외부 번호로 |
|                                                       |transfer_in_progress           |AA >AA 전송                                                   |
|                                                       |transferred_to_operator        |호출이 운영자에게 전송되었습니다.                                  |
|                                                       |transferred_to_cq              |통화 큐에 대한 호출이 전송되었습니다.                                |
|                                                       |transferred_to_receptionist    |transferred_to_operator                                   |
|                                                       |transferred_to_self            |호출이 AA의 시작 부분에 반환되었습니다.                          |
|                                                       |transferred_to_shared_voicemail |통화가 공유 음성 메일로 전송되었습니다.                         |
|                                                       |transferred_to_user            |통화가 사용자에게 전송되었습니다.                                    |
|                                                       |알려지지 않은                        |알 수 없는 조건이 발생했습니다.                                 |
|                                                       |user_terminated                |발신자가 전화를 끊었습니다.                                                    |
|AutoAttendantCallerActionCounts<br>(정수)      |                               |                                                                  |
|AutoAttendantChainDurationInSecs<br>(실수)      |                               |                                                                  |
|AutoAttendantChainIndex<br>(정수)              |                               |                                                                  |
|AutoAttendantChainStartTime<br>(DateTime)              |                               |                                                                  |
|AutoAttendantCount<br>(정수)                   |                               |                                                                  |
|AutoAttendantDirectorySearchMethod<br>(텍스트)           |                               |디렉터리 검색 방법                                           |
|                                                       |abs_search_dtmf                |터치 톤                                                        |
|                                                       |abs_search_voice               |음성                                                             |
|AutoAttendantIdentity<br>(텍스트)                        |                               |리소스 계정 URI 호출이 도착했습니다.                              |
|AutoAttendantTransferAction<br>(텍스트)                  |                               |호출 전송 대상 유형                                         |
|                                                       |Aa                             |AA로 전송됨                                              |
|                                                       |Cq                             |CQ로 전송됨                                               |
|                                                       |external_pstn                  |외부 번호로 전송됨                                 |
|                                                       |공유 음성 메일               |공유 음성 메일로 전송됨                                   |
|                                                       |알려지지 않은                        |알 수 없는 작업                                                    |
|HasAA<br>(부울)                                     |                               |AA가 통화에 관련되어 있는 경우                                            |


### <a name="call-queue-dimensions"></a>큐 차원 호출

|이름(형식)                                            |가능한 값                |설명                                                       |
|:------------------------------------------------------|:------------------------------|:-----------------------------------------------------------------|
|CallQueueAgentCount<br>(정수)                  |                               |통화 큐의 에이전트 수                                    |
|CallQueueAgentOptInCount<br>(정수)             |                               |큐를 호출하도록 옵트인된 에이전트 수                           |
|CallQueueCallResult<br>(텍스트)                          |                               |통화 큐 호출 최종 상태                                       |
|                                                       |agent_joined_conference        |통화 응답 - 회의 모드 CQ                                |
|                                                       |거부                       |                                                                  |
|                                                       |연결이 끊어진                   |                                                                  |
|                                                       |error                          |                                                                  |
|                                                       |실패                         |                                                                  |
|                                                       |올바르지 않음                        |                                                                  |
|                                                       |오버플로                      |오버플로 조건이 충족되었습니다.                                            |
|                                                       |timed_out                      |시간 제한 조건이 충족되었습니다.                                             |
|                                                       |transferred_to_agent           |응답된 통화 - 전송 모드 CQ                                  |
|CallQueueDurationSeconds<br>(실수)              |                               |통화 큐의 통화 기간                                   |
|CallQueueFinaleStateAction<br>(텍스트)                   |                               |큐 최종 작업 호출                                           |
|                                                       |분리                     |time_out 호출                                                    |
|                                                       |disconnect_with_busy           |오버플로 호출                                                   |
|                                                       |failed_to_accept_call          |                                                                  |
|                                                       |전달                        |통화가 사용자 또는 외부로 전달되었습니다.                        |
|                                                       |shared_voicemail               |공유 음성 메일로 전화가 전송되었습니다.                                 |
|                                                       |다른                          |                                                                  |
|                                                       |음성                      |                                                                  |
|CallQueueIdentity<br>(텍스트)                            |                               |리소스 계정 URI 호출이 도착했습니다.                              |
|CallQueueTargetType<br>(텍스트)                          |                               |호출 리디렉션 대상                                           |
|                                                       |ApplicationEndpoint            |                                                                  |
|                                                       |사서함                        |                                                                  |
|                                                       |기타                          |                                                                  |
|                                                       |전화                          |                                                                  |
|                                                       |사용자                           |                                                                  |
|HasCQ<br>(부울)                                     |                               |CQ가 호출에 관련되어 있는지 확인합니다.                                            |
|TransferredFromCallQueueIdentity<br>(텍스트)             |                               |                                                                  |

### <a name="measurements"></a>측정

|이름(형식)                                            |가능한 값                |설명                                                       |
|:------------------------------------------------------|:------------------------------|:-----------------------------------------------------------------|
|AvgAutoAttendantChainDurationSeconds<br>(실수)  |                               |                                                                  |
|AvgCallDuration<br>(실수)                       |                               |                                                                  |
|AvgCallQueueDurationSeconds<br>(실수)           |                               |                                                                  |
|PSTNTotalMinutes<br>(실수)                      |                               |                                                                  |
|TotalAudioStreamDuration<br>(실수)              |                               |                                                                  |
|TotalCallCount<br>(정수)                       |                               |                                                                  |

### <a name="constructing-a-valid-query"></a>유효한 쿼리 생성

유효한 쿼리는 JSON 개체의 여러 특성으로 구성됩니다.

```json
{
   "Filters":[
      {
         "DataModelName":"Date",
         "Value":"2022-04-01",
         "Operand":4
      },
      {
         "DataModelName":"Date",
         "Value":"2022-04-30",
         "Operand":6
      }
   ],
   "Dimensions":[
      {
         "DataModelName":"AutoAttendantIdentity"
      },
      {
         "DataModelName":"AutoAttendantDirectorySearchMethod"
      }
   ],
   "Measurements":[
      {
         "DataModelName":"PSTNTotalMinutes"
      },
      {
         "DataModelName":"TotalCallCount"
      }
   ],
   "Parameters":{
      "UserAgent":"Power BI Desktop"
   },
   "LimitResultRowsCount":100000
}
```

#### <a name="required-fields"></a>필수 필드

- 필터: VAAC에서 반환된 데이터를 필터링하는 데 사용됩니다.
- - DataModelName은 지원되는 차원 중 하나여야 합니다.
- - 값은 올바른 형식(datetime, string, number 등)이어야 합니다.
- - 피연산자:
- - - 0 - 같음
- - - 1 - 같지 않음
- - - 2 - 포함
- - - 3 - 시작
- - - 4 - 보다 큼
- - - 5 - 보다 크거나 같음
- - - 6 - 보다 작음
- - - 7 - 보다 작거나 같음
- - - 8 - 포함하지 않음
- - - 9 - 로 시작되지 않음

- 차원:
- - DataModelName은 지원되는 차원 중 하나여야 합니다.

- 측정:
- - DataModelName은 지원되는 측정값 중 하나여야 합니다.

- 매개 변수: 현재 UserAgent만 지원됩니다.

- LimitResultRowsCount: VAAC에서 반환한 최대 행 수

## <a name="accessing-vaac-outside-of-power-bi"></a>Power BI 외부에서 VAAC 액세스

VAAC API는 RESTful 애플리케이션에 액세스할 수 있는 모든 애플리케이션에서 액세스할 수 있습니다.  아래 예제에서는 [Postman](https://www.postman.com/) 이 사용됩니다.

### <a name="preparation"></a>준비

1. [Postman을 다운로드합니다](https://www.postman.com/).
1. 다운로드한 `sync_pstn_avs-analytics.zip` [zip 파일 지침에서 파일](#v3xx-installation)의 압축을 풉니다.
1. 폴더를 Postman으로 가져옵니다. 

:::image type="content" source="media/aa-cq-historical-report-postman-01.png" alt-text="가져오기 완료를 보여 주는 스크린샷":::

### <a name="accessing-vaac-using-postman"></a>Postman을 사용하여 VAAC 액세스

1. **VAAC -** 오른쪽 위에 있는 msit **_환경 없음_** 드롭다운을 선택합니다.
2. 왼쪽 레일 메뉴에서 **환경을** 선택합니다.
3. **전역 아래에서 VAAC - msit****를** 선택합니다.
4. **userName**, **password** 및 **tenantId** 를 해당 자격 증명으로 바꿉 있습니다.
5. 오른쪽 위 모서리에서 **모두 다시 설정을** 클릭합니다.
6. **저장** 을 클릭합니다.

:::image type="content" source="media/aa-cq-historical-report-postman-02.png" alt-text="구성된 사용자 이름, 암호 및 테넌트 ID 필드를 보여 주는 스크린샷":::

7. 왼쪽 레일 메뉴에서 **컬렉션을** 선택합니다.
8. **구성 API 액세스 토큰 - Prod를** 선택하고 **본문** 탭으로 이동합니다.
9. **보내기** 를 클릭합니다.

액세스 토큰이 반환됩니다.

:::image type="content" source="media/aa-cq-historical-report-postman-03.png" alt-text="액세스 토큰이 반환된 결과를 보여 주는 스크린샷":::

액세스 토큰이 반환되지 않으면 자격 증명을 확인하여 [충분한 권한이](#permissions-to-access-the-cqd-pipeline) 있는지 확인합니다.

10. **VAAC ConfigAPI Prod** 를 선택하고 **매개 변수** 탭으로 이동합니다.

- 아래에 설명된 대로 쿼리 [압축](#compress-the-json-query)
- URL은 아래에 설명된 대로 압축된 결과를 [인코딩](#url-encode-the-compressed-json-query)합니다.

11. [쿼리](#constructing-a-valid-query) 문자열을 입력합니다.
12. **보내기** 를 클릭합니다.

### <a name="reading-the-result"></a>결과 읽기

입력을 제출하면 다음과 같은 몇 가지 결과가 발생할 수 있습니다.

- 입력이 유효하지 않으면 실제 이유가 포함된 오류 메시지가 반환됩니다.
- 입력이 유효한 경우 결과는 다음과 같습니다.

:::image type="content" source="media/aa-cq-historical-report-postman-04.png" alt-text="dataResult 필드가 있는 쿼리 결과를 보여 주는 스크린샷":::

이 경우 데이터는 쿼리 차원 및 측정 특성에서 요청된 순서와 동일한 순서로 "dataResult" 필드에 있습니다.

### <a name="compress-the-json-query"></a>JSON 쿼리 압축

VAAC API는 GZip 압축 또는 Base64로 인코딩된 문자열만 입력으로 허용합니다.

GZIP 또는 Base64를 사용하여 JSON Blob을 압축할 웹 사이트를 찾습니다.

- GZIP: (https://www.multiutil.com/text-to-gzip-compress/)
- Base64: (https://www.multiutil.com/text-to-base64-converter/)

GZIP 출력은 다음과 같습니다.
````
H4sIAAAAAAAACq2SQWsCMRCF7/6KkLNC3EoPe9u6FISuFbW9lB4GM9TQbEaSCSLif+9mV4uCBwXnMkze5L0vkH1PCCFfjWX0QeZfaWxqf+xJLIGhIo12CjXKPM0o+2cLn2BjEjKVZQM1Gqjhhfy+QQ9Oy3x0PDz0H5HypK6nPJ9SUv9uV2RpanTBkLvxiUVkKpjRaXA80ejY8E7eg3/hUBqPKya/WyD41bpCXpP+tzvjrBBC9NjA8o2ks8VyuiQGWxkXGcNdkO3FMVg7puj4GtAMfLPa/Y2Tk/wI6IufhjHl0xa9eJmIEsMv06Y16cLlm6kNzzFEy3Pahi4kH6pUvcMfrAhUU3oCAAA=
````

Base64 출력은 다음과 같습니다.
````
ew==
IkZpbHRlcnMiOls=
ew==
IkRhdGFNb2RlbE5hbWUiOiJEYXRlIiw=
IlZhbHVlIjoiMjAyMi0wNC0wMSIs
Ik9wZXJhbmQiOjQ=
fSw=
ew==
IkRhdGFNb2RlbE5hbWUiOiJEYXRlIiw=
IlZhbHVlIjoiMjAyMi0wNC0zMCIs
Ik9wZXJhbmQiOjY=
fQ==
XSw=
IkRpbWVuc2lvbnMiOls=
ew==
IkRhdGFNb2RlbE5hbWUiOiJBdXRvQXR0ZW5kYW50SWRlbnRpdHki
fSw=
ew==
IkRhdGFNb2RlbE5hbWUiOiJBdXRvQXR0ZW5kYW50RGlyZWN0b3J5U2VhcmNoTWV0aG9kIg==
fQ==
XSw=
Ik1lYXN1cmVtZW50cyI6Ww==
ew==
IkRhdGFNb2RlbE5hbWUiOiJQU1ROVG90YWxNaW51dGVzIg==
fSw=
ew==
IkRhdGFNb2RlbE5hbWUiOiJUb3RhbENhbGxDb3VudCI=
fQ==
XSw=
IlBhcmFtZXRlcnMiOns=
IlVzZXJBZ2VudCI6IlBvd2VyIEJJIERlc2t0b3Ai
fSw=
IkxpbWl0UmVzdWx0Um93c0NvdW50IjoxMDAwMDA=
fQ==
````

### <a name="url-encode-the-compressed-json-query"></a>압축된 JSON 쿼리 URL-Encode

GZIP 또는 Base64 압축 JSON 쿼리는 [URL로 인코딩](https://meyerweb.com/eric/tools/dencoder/)되어야 합니다.

GZIP URL로 인코딩된 출력은 다음과 같습니다.
````
H4sIAAAAAAAACq2SQWsCMRCF7%2F6KkLNC3EoPe9u6FISuFbW9lB4GM9TQbEaSCSLif%2B9mV4uCBwXnMkze5L0vkH1PCCFfjWX0QeZfaWxqf%2BxJLIGhIo12CjXKPM0o%2B2cLn2BjEjKVZQM1Gqjhhfy%2BQQ9Oy3x0PDz0H5HypK6nPJ9SUv9uV2RpanTBkLvxiUVkKpjRaXA80ejY8E7eg3%2FhUBqPKya%2FWyD41bpCXpP%2BtzvjrBBC9NjA8o2ks8VyuiQGWxkXGcNdkO3FMVg7puj4GtAMfLPa%2FY2Tk%2FwI6IufhjHl0xa9eJmIEsMv06Y16cLlm6kNzzFEy3Pahi4kH6pUvcMfrAhUU3oCAAA%3D
````

Base64 URL로 인코딩된 출력은 다음과 같습니다.
````
%0Aew%3D%3D%0AIkZpbHRlcnMiOls%3D%0Aew%3D%3D%0AIkRhdGFNb2RlbE5hbWUiOiJEYXRlIiw%3D%0AIlZhbHVlIjoiMjAyMi0wNC0wMSIs%0AIk9wZXJhbmQiOjQ%3D%0AfSw%3D%0Aew%3D%3D%0AIkRhdGFNb2RlbE5hbWUiOiJEYXRlIiw%3D%0AIlZhbHVlIjoiMjAyMi0wNC0zMCIs%0AIk9wZXJhbmQiOjY%3D%0AfQ%3D%3D%0AXSw%3D%0AIkRpbWVuc2lvbnMiOls%3D%0Aew%3D%3D%0AIkRhdGFNb2RlbE5hbWUiOiJBdXRvQXR0ZW5kYW50SWRlbnRpdHki%0AfSw%3D%0Aew%3D%3D%0AIkRhdGFNb2RlbE5hbWUiOiJBdXRvQXR0ZW5kYW50RGlyZWN0b3J5U2VhcmNoTWV0aG9kIg%3D%3D%0AfQ%3D%3D%0AXSw%3D%0AIk1lYXN1cmVtZW50cyI6Ww%3D%3D%0Aew%3D%3D%0AIkRhdGFNb2RlbE5hbWUiOiJQU1ROVG90YWxNaW51dGVzIg%3D%3D%0AfSw%3D%0Aew%3D%3D%0AIkRhdGFNb2RlbE5hbWUiOiJUb3RhbENhbGxDb3VudCI%3D%0AfQ%3D%3D%0AXSw%3D%0AIlBhcmFtZXRlcnMiOns%3D%0AIlVzZXJBZ2VudCI6IlBvd2VyIEJJIERlc2t0b3Ai%0AfSw%3D%0AIkxpbWl0UmVzdWx0Um93c0NvdW50IjoxMDAwMDA%3D%0AfQ%3D%3D
````

## <a name="version-3xx-history"></a>버전 3.x.x 기록

자세한 변경 내용은 Teams 자동 전화 교환 & 통화 큐 기록 보고서 - 다운로드한 zip 파일의 변경 Log.docx 참조하세요. 

|버전  |게시된 날짜     |파일                                                    |설명                                                             |
|:--------|:------------------|:-----------------------------------------------------------|:-----------------------------------------------------------------------|
|3.0.5    |2023년 1월 9일    |Teams 자동 전화 교환 & 통화 큐 기록 보고서 V3.0.5 |향상된 호출 오버플로/시간 제한 대상 및 에이전트 타임라인 시각적 개체  |
|3.0.4    |2022년 11월 18일  |Teams 자동 전화 교환 & 통화 큐 기록 보고서 V3.0.4 |오류 수정, 호출 분류 개선, 범례 추가             |
|3.0.3    |2022년 11월 8일   |Teams 자동 전화 교환 & 통화 큐 기록 보고서 V3.0.3 |오류 수정, 설명서 링크 추가, 최적화된 쿼리            |
|3.0.1    |2022년 10월 26일   |Teams 자동 전화 교환 & 통화 큐 기록 보고서 V3.0.1 |테스트 데이터 원본 항목이 제거됨                                       |
|3.0.0    |2022년 10월 25일   |Teams 자동 전화 교환 & 통화 큐 기록 보고서 V3.0.0 |새 백 엔드 데이터 원본                                                 |
