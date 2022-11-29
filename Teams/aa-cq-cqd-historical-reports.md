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
ms.openlocfilehash: 780d6057960c96713ac67be3e189d7982fd2fa46
ms.sourcegitcommit: e9718ad7e23317d490b238b3801267cb2e6b26e2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/28/2022
ms.locfileid: "69176695"
---
# <a name="updated-auto-attendant-and-call-queue-historical-reports"></a>자동 전화 교환 및 통화 큐 기록 보고서가 업데이트됨

>[!NOTE]
> GCC HIgh 및 DOD 고객은 [CQD(통화 큐 기록 보고서)& 자동 전화 교환](aa-cq-cqd-historical-reports-v163.md)의 V1.63을 계속 사용해야 합니다.

이 Power BI 템플릿은 조직에서 자동 전화 교환 및 통화 큐에서 처리되는 통화 수를 보고할 수 있는 세 가지 보고서를 제공합니다.  또한 에이전트 성능 인사이트를 제공합니다.

## <a name="v304-published-on-november-18-2022"></a>2022년 11월 18일에 게시된 V3.0.4

Teams 자동 전화 교환 & 통화 큐 기록 보고서 Power BI 템플릿은 다음 세 가지 보고서를 제공합니다.

- [자동 전화 교환](media/aa-cq-historical-report-sample-aa-v304.png) 보고서에는 자동 전화 교환으로 들어오는 통화에 대한 분석이 표시됩니다.
- [통화 큐 보고서에는 통화 큐](media/aa-cq-historical-report-sample-cq-v304.png)로 들어오는 통화에 대한 분석이 표시됩니다.
- [에이전트 타임라인](media/aa-cq-historical-report-sample-at-v304.png) 보고서에는 통화 큐 호출에서 활성 상태인 에이전트의 타임라인 보기가 표시됩니다.

이러한 보고서는 VAAC(음성 애플리케이션 분석 수집기) 서비스의 데이터를 사용합니다.

## <a name="v3xx-prerequisites"></a>V3.x.x 필수 구성 요소

### <a name="power-bi-desktop"></a>Power BI Desktop

Power BI Desktop 설치해야 합니다. [Microsoft Windows 스토어](https://aka.ms/pbidesktopstore)에서 무료 버전을 설치하고 사용할 수 있습니다.

호환되는 최소 버전은 2.85.681.0(2020년 9월)입니다.

### <a name="permissions-to-access-the-cqd-pipeline"></a>CQD 파이프라인에 액세스할 수 있는 권한

이 버전의 보고서는 CQD(통화 품질 대시보드) 데이터 파이프라인을 사용하지 않지만 기록 데이터를 보는 데 사용되는 계정에는 통화 품질 대시보드에 대한 액세스 권한이 여전히 필요합니다. 자세한 내용은 [CQD 액세스 역할을 참조하세요](./turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd).

- 이 요구 사항은 향후 릴리스에서 제거될 예정입니다.

## <a name="v3xx-installation"></a>V3.x.x 설치 

다음 단계에서는 컴퓨터에 Power BI Desktop 이미 설치했으며 계정에 CQD 데이터 파이프라인에 액세스하는 데 필요한 권한이 있다고 가정합니다.

다음 단계를 수행합니다.

1. [Teams 자동 전화 교환 & 통화 큐 기록 보고서 V3.0.4.zip](https://www.microsoft.com/download/details.aspx?id=104623) 파일을 다운로드하여 컴퓨터에 저장합니다.

2. zip 파일을 엽니다.

3. `Teams Auto Attendant & Call Queue Historical Reports V3.0.4.pbit` 템플릿 파일을 엽니다. Power BI Desktop 시작되어야 합니다.

4. **데이터 원본** 을 선택하라는 메시지가 표시됩니다.  `api.interfaces.records.teams.microsoft.com` 항목을 선택합니다.

  :::image type="content" source="media/aa-cq-historical-report-01-v304.png" alt-text="api.interfaces.records.teams.microsoft.com Data Soure를 선택하는 스크린샷":::

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

## <a name="customization"></a>사용자화 

다양한 시각화에 표시할 필드 추가 또는 제거, 차트 종류 변경 등 보고서의 특정 시각화 측면을 사용자 지정할 수 있습니다.

보고서에는 현재 사용 가능한 모든 데이터 메트릭이 포함되어 있습니다.

### <a name="change-color-schema"></a>색 스키마 변경 

다음 단계에서는 설치 단계를 이미 완료한 것으로 가정합니다.

다음 단계를 수행합니다.

1. 리본에서 **보기 탭** 을 선택합니다.

  :::image type="content" source="media/aa-cq-historical-report-04.png" alt-text="보기 탭을 선택하여 색 구성표를 변경하는 스크린샷":::

2. 드롭다운 목록에서 색 스키마를 선택합니다.

  :::image type="content" source="media/aa-cq-historical-report-05.png" alt-text="다양한 색 구성표를 보여 주는 스크린샷":::
  
## <a name="dimensions-and-measurements"></a>차원 및 측정값

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
|FirstIsCaller<br>(부울)                             |                               |                                                                  |
|FirstUPN<br>(텍스트)                                     |                               |                                                                  |
|시간<br>(텍스트)                                         |                               |시간 호출 시작(UTC)                                           |
|분<br>(텍스트)                                       |                               |분 호출 시작(UTC)                                         |
|PSTNCallDuration<br>(정수)                     |                               |                                                                  |
|PSTNCallType<br>(텍스트)                                 |                               |                                                                  |
|                                                       |외부                       |                                                                  |
|                                                       |내부                       |                                                                  |
|PSTNConnectivityType<sup>1</sup><br>(텍스트)             |                               |                                                                  |
|                                                       |CallingPlan                    |                                                                  |
|                                                       |DirectRouting                  |                                                                  |
|두 번째<br>(텍스트)                                       |                               |두 번째 호출 시작(UTC)                                         |
|SecondUPN<br>(텍스트)                                    |                               |                                                                  |
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
|AutoAttendantChairDurationInSecs<br>(실수)      |                               |                                                                  |
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
|CallQueueDurationSeconds<br>(실수)              |                               |                                                                  |
|CallQueueFinaleStateAction<br>(텍스트)                   |                               |큐 최종 작업 호출                                           |
|                                                       |분리                     |time_out 호출                                                    |
|                                                       |disconnect_with_busy           |오버플로 호출                                                   |
|                                                       |failed_to_accept_call          |                                                                  |
|                                                       |전달                        |                                                                  |
|                                                       |shared_voicemail               |                                                                  |
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
|AACallerActionCount                     |정수             |요약: 합계<br>통화 중 자동 전화 교환에서 호출자가 선택한 작업 수  |
|AACallerActionCount(측정값)           |정수             |공백 대신 호출이 없으면 위와 동일하게 0이 됩니다.                              |
|AACallFlow                              |텍스트                     |자동 전화 교환 차원 -> AutoAttendantCallFlow를 참조하세요.                                   |
|AACallResult                            |텍스트                     |자동 전화 교환 차원 -> AutoAttendantCallResult를 참조하세요.                                 |
|AACallResultLegend                      |텍스트                     |AACallResult를 기반으로 범례 항목 설정                                               |
|AAChainDuration                         |10진수           |요약: 합계<br>자동 전화 교환의 통화 기간                                     |
|AAChainDuration(측정값)               |10진수           |공백 대신 호출이 없으면 위와 동일하게 0이 됩니다.                              |
|AAChainIndex                            |텍스트                     |                                                                                         |
|AAConnectivityType                      |텍스트                     |                                                                                         |
|AACount                                 |텍스트                     |통화에 관련된 자동 전화 교환 수                                               |
|AADirectorySearchMethod                 |텍스트                     |자동 전화 교환 차원 -> AutoAttendantDirectorySearchMethod를 참조하세요.                      |
|AADirectorySearchMethodLegend           |텍스트                     |AADirectorySearchMethod를 기반으로 범례 항목 설정                                    |
|AAStartHour                             |10진수           |자동 전화 교환 통화 시작 시간                                                           |
|AAStartTime                             |날짜/시간                |자동 전화 교환 통화 시작 시간                                                           |
|AATransferAction                        |텍스트                     |자동 전화 교환 차원 -> AutoAttendantTransferAction을 참조하세요.                             |
|호출 유형<sup>1</sup>                   |텍스트                     |Common Dimensions -> PSTNCallType을 참조하세요.                                                    |
|MM-DD                                   |텍스트                     |자동 전화 교환 통화 월-일                                                            |
|PSTNMinutes                             |정수             |요약: 합계<br>총 분 사용량                                                     |
|TotalCallCount                          |정수             |요약: 합계<br>Always 1 - 모든 호출의 합계를 제공하는 데 사용됩니다.                            |
|TotalCallCount의 합계(측정값)         |정수             |공백 대신 호출이 없으면 위와 동일하게 0이 됩니다.                              |


### <a name="cloud-call-queue-analytics-report"></a>Cloud Call Queue Analytics 보고서

#### <a name="report-description"></a>보고서 설명

|보고서 섹션                          |설명                                                        |
|:---------------------------------------|:------------------------------------------------------------------|
|들어오는 호출 원본                    |내부/외부 호출 원본별 호출 배포             |
|평균 대기 시간(초)             |응답된 통화 및 중단된 통화 대기 시간                          |
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

|이름                                    |데이터 형식                |설명                                                                |
|:---------------------------------------|:------------------------|:--------------------------------------------------------------------------|
|호출 수                              |정수             |요약: 합계<br>호출 수                                          |
|통화 큐 에이전트 수                  |정수             |요약: 합계<br>호출 큐에 구성된 에이전트 수            |
|통화 큐 에이전트 옵트인 수           |정수             |요약: 합계<br>통화 큐에 옵트인된 에이전트 수              |
|통화 큐 호출 결과                  |텍스트                     |통화 큐 차원 -> CallQueueCallResult를 참조하세요.                           |
|호출 큐 호출 결과 범례           |텍스트                     |통화 큐 결과에 따라 범례 항목 설정                            |
|호출 큐 대상 유형                  |텍스트                     |Call Queue Dimensions -> CallQueueTargetType을 참조하세요.                           |
|호출 큐 대상 형식 범례           |텍스트                     |통화 큐 대상 유형에 따라 범례 항목 설정                       |
|호출 유형                               |텍스트                     |Common Dimensions -> PSTNCallType을 참조하세요.                              |
|CQ 이름                                 |텍스트                     |통화 큐에 연결된 리소스 계정의 이름<br><br>전체 리소스 계정 이름이 **cq_test@microsoft.com** 경우 이 값은 **cq_test** |
|CQ 시간                                 |정수             |통화 큐 호출 시작 시간                                                 |
|날짜                                    |날짜/시간                |통화 큐 호출 시작 날짜 및 시간(시간)                                 | 
|DateTimeCQName                          |텍스트                     |fCallQueueFinalStateAction에서 필터링하기 위한 고유 키                     |
|PSTN 연결 유형                  |텍스트                     |Common Dimensions -> PSTNConnectivityType을 참조하세요.                              |
|PSTN 총 시간(분)                      |정수             |요약: 합계<br>PSTN 호출의 총 시간(분) 사용량                       |
|호출 수의 합계(측정값)             |정수             |호출 수와 같지만 호출이 없는 경우 0이 됩니다.                          |
|TotalCallCount(측정값)                |정수             |요약: 합계<br>호출 수                                               |


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
|호출 수                              |정수             |요약: 합계<br>에이전트가 응답한 통화 수     |
|통화 기간(분)                 |정수             |요약: 합계<br>응답된 통화 큐 통화의 총 통화 기간(분)(가장 가까운 분으로 반올림)  |
|CQ 이름                                 |텍스트                     |통화 큐에 연결된 리소스 계정의 이름<br><br>전체 리소스 계정 이름이 **cq_test@microsoft.com** 경우 이 값은 **cq_test** |
|날짜                                    |날짜                     |통화 날짜                                             |
|Datetime                                |Datetime                 |통화 날짜                                             |
|시간                                    |정수             |통화 시간                                             |
|MM-DD                                   |텍스트                     |통화 월 및 일                                    |


> [!NOTE]
> 호출이 첫 번째 호출 큐에 도착하면 해당 큐에서 이미 대기 중인 호출 수가 **통화 오버플로 처리** 제한에 도달하고 리디렉션 옵션이 두 번째 호출 큐에 새 호출을 보내는 경우 두 번째 통화 큐의 에이전트는 이 보고서의 첫 번째 통화 큐에 있는 것으로 표시됩니다. 

## <a name="known-issues"></a>알려진 문제

- 통화 큐 및 자동 전화 교환은 통화 큐/자동 전화 교환 이름 대신 리소스 계정의 ID로 표시됩니다.  자동 전화 교환 또는 통화 큐에 대한 모든 트래픽을 표시하려면 자동 전화 교환 또는 통화 큐에 할당된 모든 리소스 계정을 선택해야 합니다.

- 통화 큐/자동 전화 교환 데이터가 개인 데이터로 간주되고 데이터 개인 정보 보존 정책이 적용되므로 대시보드에서 28일의 기록만 사용할 수 있습니다.

- 일부 시나리오에서는 **클라우드 통화 큐 에이전트 타임라인** 보고서에서 에이전트가 응답한 통화 수가 Teams 클라이언트 통화 기록에 표시된 통화 수와 다를 수 있습니다. Teams 클라이언트 호출 기록이 올바르습니다. 지원은 조사 중이지만 현재 복구할 수 있는 예상 시간은 없습니다.

## <a name="version-3xx-history"></a>버전 3.x.x 기록

자세한 변경 내용은 Teams 자동 전화 교환 & 통화 큐 기록 보고서 - 다운로드한 zip 파일의 변경 Log.docx 참조하세요. 

|버전  |게시된 날짜     |파일                                                           |설명                                         |
|:--------|:------------------|:------------------------------------------------------------------|:---------------------------------------------------|
|3.0.4    |2022년 11월 18일  |Teams 자동 전화 교환 & 통화 큐 기록 보고서 V3.0.4        |오류 수정, 호출 분류 개선, 범례 추가 |
|3.0.3    |2022년 11월 8일   |Teams 자동 전화 교환 & 통화 큐 기록 보고서 V3.0.3        |오류 수정, 설명서 링크 추가, 최적화된 쿼리 |
|3.0.1    |2022년 10월 26일   |Teams 자동 전화 교환 & 통화 큐 기록 보고서 V3.0.1        |테스트 데이터 원본 항목이 제거됨                   |
|3.0.0    |2022년 10월 25일   |Teams 자동 전화 교환 & 통화 큐 기록 보고서 V3.0.0        |새 백 엔드 데이터 원본                             |
