---
title: 자동 전화 교환 & 기록 보고서 호출
ms.author: mikeplum
author: MikePlumleyMSFT
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
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Reporting
- ms.teamsadmincenter.directrouting.cqd
- ms.lync.lac.ToolsCallQualityDashboard
description: 통화 품질 대시보드 Power BI 보고서를 사용하여 대기열 기록 데이터를 자동 전화 교환 방법에 대해 자세히 알아보면 됩니다.
ms.openlocfilehash: 994e135cfd579d473da02879adde0d3603ab0ed2
ms.sourcegitcommit: 0122be629450e203e7143705ac2b395bf3792fd3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/25/2021
ms.locfileid: "53129338"
---
# <a name="auto-attendant--call-queue-historical-report"></a>자동 전화 교환 & 기록 보고서 호출

CQD Teams 자동 전화 교환 & 큐 기록 보고서 Power BI 템플릿은 다음 세 가지 보고서를 제공 합니다.

- [자동 전화 교환](media/cqd-teams-aa-cq-historical-report-sample-aa.png) - 자동 참석자에 오는 통화에 대한 분석을 보여 넣습니다.
- [통화 큐](media/cqd-teams-aa-cq-historical-report-sample-cq.png) - 통화 큐로 오는 통화에 대한 분석을 보여 넣습니다.
- [에이전트 타임라인](media/cqd-teams-aa-cq-historical-report-sample-at.png) – 통화 큐 호출에서 활성 상태인 에이전트의 타임라인 보기를 보여 입니다.

이러한 보고서는 통화 품질 대시보드 데이터 [저장소의 데이터를](CQD-Power-BI-query-templates.md) 사용 합니다. 조직에서 자동 참석자 및 호출 큐에서 처리되는 호출 수를 보고할 수 있습니다.  또한 호출 큐에서 에이전트 성능에 대한 인사이트를 제공합니다.

## <a name="prerequisites"></a>필수 구성 요소

### <a name="power-bi-desktop"></a>Power BI Desktop
설치해야 Power BI Desktop 있습니다. Microsoft Windows [스토어에서 설치할 수 있습니다.](https://aka.ms/pbidesktopstore)

무료 버전의 버전을 사용할 Power BI Desktop. 최소 호환 버전은 2.85.681.0(2020년 9월)입니다.

### <a name="permissions-to-access-the-cqd-pipeline"></a>CQD 파이프라인에 액세스하는 권한

AA & CQ Analytics 기록 보고서를 보는 데 사용하는 계정은 CQD 데이터 파이프라인에 액세스할 수 있는 권한이 필요합니다. 자세한 내용은 [CQD 액세스 역할 을 참조하세요.](./turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd)

## <a name="installation"></a>설치 

다음 단계는 컴퓨터에 이미 Power BI Desktop CQD 데이터 파이프라인에 액세스하는 데 필요한 권한이 계정에 있는 것으로 가정합니다.

다음 단계를 수행합니다.

- [CQD](https://www.microsoft.com/download/details.aspx?id=102291) Power BI 템플릿을 다운로드하고 zip 파일을 컴퓨터의 디렉터리에 저장합니다.

- zip 파일을 두 번 클릭하여 를 니다.

- "CQ 및 AA 결합 Analytics 20201105.pbit" 템플릿 파일을 두 번 클릭하고 Power BI Desktop 시작해야 합니다.

- CQD 데이터 파이프라인 지역을 선택하라는 메시지가 표시됩니다. 테넌트가 있는 지역을 선택합니다.

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-01.png" alt-text="CQD 데이터 파이프라인 지역을 선택하는 스크린샷":::

- 테넌트가 있는 지역은 [Get-CsTenant](/powershell/module/skype/get-cstenant) cmdlet을 사용하여 얻을 수 있습니다.

    ```PowerShell
    (Get-CsTenant).ServiceInstance


    microsoftcommunicationsonline/noam-4a-s7
    ```

    - 지역은 위의 예제와 같은 다음에 **/** 표시됩니다.

 - 보고서는 샘플 데이터로 시작됩니다.
 
 - 사용자 자신의 데이터를 확인하려면 홈 탭의 쿼리 아래에서 새로 고침을 Power BI Desktop. 

   :::image type="content" source="media/cqd-teams-aa-cq-historical-report-02.png" alt-text="새로 고침 옵션 선택 스크린샷":::

- 그런 다음 로그인하라는 메시지가 표시됩니다. 조직 **계정을 선택한** 다음 로그인 **을 선택합니다.**

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-03.png" alt-text="로그인을 보여주는 스크린샷":::

- 커넥트  선택하고 데이터 새로 고침을 시청합니다.

## <a name="data-latency-and-aa--cq-analytics"></a>데이터 대기 시간 및 AA & CQ 분석

데이터는 30분 이내에 CQD 데이터 파이프라인에서 사용할 수 있습니다.

새 분석 데이터를 표시하기 위해 데이터를 새로 고쳐야 합니다. 

## <a name="customization"></a>사용자 지정 

다양한 시각화에 표시될 필드 추가 또는 제거, 차트 유형 변경 등 보고서의 특정 시각화 측면을 사용자 지정할 수 있습니다.

보고서에 추가 데이터 필드를 추가할 수 없습니다.

### <a name="change-color-schema"></a>색계도 변경 

다음 단계는 설치 단계를 이미 완료했다고 가정합니다.

다음 단계를 수행합니다.
- 리본 **메뉴에서 보기** 탭을 선택합니다.

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-04.png" alt-text="색 구성표를 변경하기 위해 보기 탭을 선택하는 스크린샷":::

- 드롭다운 목록에서 색스마를 선택합니다.

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-05.png" alt-text="다양한 색 구성표를 보여주는 스크린샷":::
  
## <a name="auto-attendant-and-call-queue-historical-reports-definitions"></a>자동 전화 교환 기록 보고서 정의를 호출하고 호출합니다.

### <a name="cloud-auto-attendant-analytics"></a>클라우드 자동 전화 교환 분석

#### <a name="report-description"></a>보고서 설명

|보고서 섹션                          |설명                                                       |
|:---------------------------------------|:-----------------------------------------------------------------|
|들어오는 통화 원본<sup>1</sup>        |내부/외부 호출 원본에 의해 호출 분포             |
|디렉터리 검색 방법 합계          |검색 유형별로 호출 분포                               |
|발신자 작업                           |통화 수신자에 의해 통화 분포                             |
|호출 결과                             |최종 호출 상태로 호출 분포                          |
|발신자 작업 수                     |통화 중에 사용된 번호 작업으로 호출 분포        |


#### <a name="report-to-cqd-table-and-field-mapping"></a>CQD 테이블 및 필드 매핑에 보고

|보고서 탭            |보고서 테이블 이름     |전역 필터                          |
|:---------------------|:---------------------|:--------------------------------------|
|자동 전화 교환        |fAutoAttendant        |AAStartTime은 지난 28일 이내입니다. |


|보고서 테이블 이름            |원본 테이블 이름            |처리       |
|:----------------------------|:----------------------------|:----------------|
|fAutoAttendant               |AutoAttendant                |원본 = AutoAttendant, <br>#"필터링된 행" = Table.SelectRows(원본, 각 true) <br>#"자동 전화 교환" = Table.AddColumn(#"필터링된 행", "AA 이름", 각 List.First(Text.Split([AAIdentity], "@")) <br>#"변경된 형식" = Table.TransformColumnTypes(#"자동 전화 교환",{{"AAStartTime", datetime}}을 입력합니다. <br>#"제거된 열" = Table.RemoveColumns(#"변경된 형식",{"AAIdentity"}) |


|보고서 섹션                                  |필드 사용                              |적용된 필터     |
|:-----------------------------------------------|:------------------------------------------|:-------------------|
|날짜 선택기                                   |AAStartTime                                |없음                |
|자동 전화 교환                                  |AA 이름                                    |없음                |
|들어오는 통화 원본<sup>1</sup>                |통화 유형<br>TotalCallCount                |외부 통화: 통화 유형은 외부 호출입니다.<br>내부 통화: 통화 유형은 내부 호출입니다. |
|디렉터리 검색 방법 합계                  |AADirectorySearchMethod<br>TotalCallCount  |AADirectorySearchMethod는 abs_search_dtmf abs_search_name    |
|호출자 작업                                  |AATransferAction<br>TotalCallCount         |없음                                                             |
|AA의 평균 초<br>평균 호출자 작업 |AAChainDuration<br>AACallerActionCount     |없음                                                             |
|호출 결과                                    |AACallResult<br>TotalCallCount             |없음                                                             |
|발신자 작업 수                            |AACallerActionCount<br>TotalCallCount      |없음                                                             |
|보고서의 하위 섹션                         |AA 이름<br>AACallFlow<br>AACallResult<br>AAChainDuration<br>통화 유형<br>TotalCallCount |없음                |

#### <a name="fautoattendant-cqd-fields-description"></a>fAutoAttendant CQD 필드 설명

|이름                                    |데이터 형식                |설명                            |
|:---------------------------------------|:------------------------|:--------------------------------------|
|AA 이름                                 |텍스트                     |에 연결된 리소스 계정의 이름 자동 전화 교환<br><br>전체 리소스 계정 이름이 aa_test@microsoft.com **경우** 이 값은  aa_test |
|AACallerActionCount                     |정수             |요약: 합계<br>호출 중에 호출자에서 자동 전화 교환 작업 수  |
|AACallFlow                              |텍스트                     |가능한 값인 호출의 다양한 자동 전화 교환 캡슐화합니다.<br><br>§ abs_search<br>§ 공지<br>§ automatic_menu<br>§ call_termination<br>§ call_transfer<br>§ first_level_menu<br>§ main_menu<br>§ speech_input_confirmation<br>§ user_selection |
|AACallResult                            |텍스트                     |최종 호출 결과 - 가능한 값:<br><br>§ failed_to_establish_media<br>§ failover_to_operator<br>§ oaa_chain_too_long<br>§ oaa_session_too_long<br>§ service_declined<br>§ service_terminated<br>§ terminated_automatic_selection<br>§ terminated_no_operator<br>§ terminated_transfer_failed<br>***§ transferred_to_operator***<br>§ transferred_to_receptionist<br>§ transferred_to_self<br>§ transferred_to_shared_voicemail<br>§ transferred_to_user<br>§ 알 수 없음<br>§ user_terminated |
|AAChainDuration                         |10진수           |요약: 합계<br>전화 통화 자동 전화 교환                     |
|AAChainIndex                            |텍스트                     |                                                                         |
|AAConnectivityType                      |텍스트                     |호출 유형 - 가능한 값:<br><br>§ ExternalCall<br>§ InternalCall |
|AACount                                 |텍스트                     |통화에 관련된 자동 참석자 수                               |
|AADirectorySearchMethod                 |텍스트                     |마지막 주소서 검색 방법 - 가능한 값:<br><br>§ abs_search_dtmf<br>§ abs_search_extension_x<br>§ abs_search_name |
|AAStartTime                             |date/time                |자동 전화 교환 시작 시간                                           |
|AATransferAction                        |텍스트                     |통화 전송 대상 유형 -- 가능한 값:<br><br>***§ application - voice application entity**§_<br> external_pstn <br>_§ hunt_group - Call Queue *_entity_* _<br>_ * _§ orgaa - 조직 자동 전화 교환 엔터티_**<br>§ shared_voicemail<br>§ 알 수 없음<br>§ 사용자 |
|통화 유형<sup>1</sup>                   |텍스트                     |호출 유형 - 가능한 값:<br><br>§ 외부<br>§ 내부         |
|IsAAInvolved                            |텍스트                     |항상 1                                                                 |
|PSTNMinutes                             |정수             |요약: 합계<br>총 분 사용량                                     |
|TotalCallCount                          |정수             |요약: 합계<br>Always 1 - 모든 호출의 합계를 제공하는 데 사용됩니다.            |


### <a name="cloud-call-queue-analytics"></a>클라우드 호출 큐 분석

#### <a name="report-description"></a>보고서 설명

|보고서 섹션                          |설명                                                        |
|:---------------------------------------|:------------------------------------------------------------------|
|들어오는 통화 원본<sup>1</sup>        |내부/외부 호출 원본에 의해 호출 배포              |
|통화 볼륨                             |호출 큐에 의해 호출 배포                                |
|호출자 결과                           |호출 결과로 호출 분포                                |
|시간 제한/오버플로 호출 총 작업      |호출 결과로 NOT 전달(중단) 호출 배포       |
|전송/전달 대상 합계          |호출 결과로 전달된 호출 분포                      |
|중단된 호출 비율                   |성공한 콜 수와 중단된 호출 수의 비율                        |
|평균 세션 길이(초)        |중단/성공 호출로 그룹화된 초의 통화 길이       |

#### <a name="report-to-cqd-table-and-field-mapping"></a>CQD 테이블 및 필드 매핑에 보고

|보고서 탭         |표 이름 보고서                                                          |전역 필터 |
|:------------------|:---------------------------------------------------------------------------|:-------------|
|큐 호출         |날짜<br>dCQ-CQIdenity<br>fCallQueueAnalytics<br>fCallQueueFinalStateAction |없음          |
 
|보고서 테이블 이름            |원본 테이블 이름            |처리       |
|:----------------------------|:----------------------------|:----------------|
|날짜                        |날짜                        |없음             |
|dCQ-CQIdentity               |CallQueueAnalytics           |Source = CallQueueAnalytics, <br>#"제거된 열" = Table.RemoveColumns(Source,{"Call Count", "Call Queue Call Result", "Date", "PSTN 연결 유형", "통화 큐 대상 유형", "PSTN 총 분"})<br>Distinct = Table.Distinct(#"제거된 열") |
|fCallQueueAnalytics          |CallQueueAnalytics           |없음             |
|fCallQueueFinalStateAction   |CallQueueFinalStateAction    |없음             |

|보고서 섹션                      |Table -> 필드 사용                |적용된 필터       |
|:-----------------------------------|:-------------------------------------|:---------------------|
|날짜 선택기                       |Dates -> DateTime                     |없음                  |
|큐 ID 호출                 |dCQ-CQIdentity -> 큐 ID 호출 |없음                  |
|들어오는 통화 원본<sup>1</sup>    |fCallQueueAnalytics -> 통화 수<br>fCallQueueAnalytics -> 호출 유형    |외부 통화: 통화 유형은 외부 호출입니다.<br>내부 통화: 통화 유형은 내부 호출입니다. |
|Avg 대기 시간                    |fCallQueueFinalStateAction -> 평균 통화 시간(초) |전송 전에: 큐 호출 결과가 agent_joined_conference 또는 transferred_to_agent<br>중단하기 전에: 대기열 호출 결과가 agent_joined_conference 또는 transferred_to_agent |
|호출 결과                         |fCallQueueAnalytics -> 통화 수<br>fCallQueueAnalytics -> 큐 호출 결과 | 없음 |
|시간 제한/오버플로 호출 총 작업 |fCallQueueFinalStateAction -> 수<br>fCallQueueFinalStateAction -> 큐 최종 상태 작업 호출 |큐 최종 상태 작업 호출이 전달되지 않습니다. |
|전송/포어드 대상 합계       |fCallQueueAnalytics -> 통화 수<br>fCallQueueAnalytics -> 큐 대상 유형 호출 |없음 |
|통화 볼륨                        |fCallQueueAnalytics -> 통화 수<br>fCallQueueAnalytics -> 큐 식별<br>fCallQueueAnalytics -> 날짜 |없음 |
|중단된 통화                     |fCallQueueAnalytics -> %중단된 호출<br>fCallQueueAnalytics -> 통화 수<br>fCallQueueAnalytics -> 날짜<br>fCallQueueAnalytics -> IsAbandoned |IsAbandoned is True |
|평균 세션 길이(초)    |fCallQueueFinalStateAction -> 평균 통화 시간<br>fCallQueueFinalStateAction -> 날짜<br>fCallQueueFinalStateAction -> IsAbandoned |없음 |

#### <a name="dcq-cqidenity-cqd-fields-description"></a>dCQ-CQIdenity CQD 필드 설명

|이름                                    |데이터 형식                |설명                            |
|:---------------------------------------|:------------------------|:--------------------------------------|
|큐 ID 호출                     |텍스트                     |통화 큐에 연결된 리소스 계정의 이름<br><br>전체 리소스 계정 이름이 cq_test@microsoft.com **이** 값은 cq_test  |

#### <a name="fcallqueueanalytics-cqd-fields-description"></a>fCallQueueAnalytics CQD 필드 설명

|이름                                    |데이터 형식                |설명                                                                |
|:---------------------------------------|:------------------------|:--------------------------------------------------------------------------|
|통화 수                              |정수             |요약: 합계<br>호출 수                                          |
|큐 호출 결과 호출                  |텍스트                     |큐 호출 최종 상태 - 가능한 값:<br><br>§ agent_joined_conference<br>§ 거부<br>§ 연결이 끊어진 경우<br>§ 오류<br>§ 실패<br>§ 유효하지 않습니다.<br>§ 오버플로<br>§ timed_out<br>§ transferred_to_agent |
|큐 ID 호출                     |텍스트                     |통화 큐에 연결된 리소스 계정의 이름<br><br>전체 리소스 계정 이름이 cq_test@microsoft.com **이** 값은 cq_test  |
|큐 대상 유형 호출                  |텍스트                     |***리디렉션 대상 유형 호출 -- 가능한 값:***<br><br>§ ApplicationEndpoint<br>§ 사서함<br>§ 기타<br>§ 사용자 |
|통화 유형<sup>1</sup>                   |텍스트                     |호출 유형 - 가능한 값:<br><br>§ 외부<br>§ 내부           |
|날짜                                    |date/time                |큐 호출 시작 날짜 및 시간(시간) (UTC)                           | 
|IsAbandoned                             |true/false               |에이전트가 호출에 응답하지 않는 경우 True                                   |
|PSTN 연결 유형                  |텍스트                     |호출 유형 - 가능한 값:<br><br>§ ExternalCall<br>§ InternalCall   |
|PSTN 총 분                      |정수             |요약: 합계<br>PSTN 호출에 대한 총 분 사용량                       |

#### <a name="fcallqueueanalytics-measures-description"></a>fCallQueueAnalytics 측정값 설명

|이름                                    |데이터 형식                |설명                              |
|:---------------------------------------|:------------------------|:----------------------------------------|
|***중단된 통화 %***                 |백분율               |측정값: TotalCallCount / Total Calls<br>성공한 콜 수와 중단된 호출 수의 비율    |
|총 통화                             |정수             |측정값: Sum agent 응답 호출        |
|TotalCallCount                          |정수             |측정값: Sum(Call Count)                 |

#### <a name="fcallqueuefinalstateaction--cqd-fields-description"></a>fCallQueueFinalStateAction CQD 필드 설명

|이름                                    |데이터 형식                |설명                                        |
|:---------------------------------------|:------------------------|:--------------------------------------------------|
|평균 통화 시간(초)         |10진수           |요약: 합계<br>평균 통화 시간(초)입니다. |
|통화 수                              |정수             |요약: 합계<br>호출 수                  |
|큐 호출 결과 호출                  |텍스트                     |큐 호출 최종 상태 - 가능한 값:<br><br>§ agent_joined_conference<br>§ 거부<br>§ 연결이 끊어진 경우<br>§ 오류<br>§ 실패<br>§ 유효하지 않습니다.<br>§ 오버플로<br>§ timed_out<br>§ transferred_to_agent |
|큐 최종 상태 작업 호출           |텍스트                     |큐 최종 작업 호출 - 가능한 값:<br><br>§ 연결 끊기<br>§ disconnect_with_busy<br>§ failed_to_accept_call<br>§ forward<br>§ shared_voicemail<br>§ 기타<br>§ 음성사서함 |
|큐 ID 호출                     |텍스트                     |통화 큐에 연결된 리소스 계정의 이름<br><br>전체 리소스 계정 이름이 cq_test@microsoft.com **이** 값은 cq_test  |
|날짜                                    |date/time                |큐 호출 시작 날짜 및 시간(시간) (UTC)   |
|IsAbandoned                             |true/false               |에이전트가 호출에 응답하지 않는 경우 True           |


### <a name="cloud-call-queue-agent-timeline"></a>클라우드 호출 큐 에이전트 타임라인

#### <a name="report-description"></a>보고서 설명

|보고서 섹션                                          |설명                                                  |
|:-------------------------------------------------------|:------------------------------------------------------------|
|# 에이전트 호출                                        |호출 큐 및 에이전트에 의해 호출 배포                 |
|에이전트 및 통화 큐의 총 통화 시간(초)입니다.   |에이전트 및 호출 큐의 총 통화 기간(초)입니다.     |
|에이전트 이름에 따라 평균 호출 기간(초)           |에이전트의 평균 통화 기간(초)입니다.                  |

#### <a name="report-to-cqd-table-and-field-mapping"></a>CQD 테이블 및 필드 매핑에 보고

|보고서 탭         |표 이름 보고서        |전역 필터 |
|:------------------|:-------------------------|:-------------|
|에이전트 타임라인     |fAgentTimelineAnalytics   |없음          |
 
|보고서 테이블 이름            |원본 테이블 이름            |처리       |
|:----------------------------|:----------------------------|:----------------|
|fAgentTimelineAnalytics      |AgentTimelineAnalytics       |Source = AgentTimelineAnalytics, <br>#"변경된 형식" = Table.TransformColumnTypes(Source,{{"Call Count", Int64.Type}, {"Call Duration(분)", Int64.Type}, {"Average Call Duration(초)", 숫자}, {"Date}, date}를 입력합니다.|

|보고서 섹션                                |필드 사용                         |적용된 필터       |
|:---------------------------------------------|:-------------------------------------|:---------------------|
|에이전트 이름                                    |에이전트 이름                            |없음                  |
|큐 이름 호출                               |큐 이름 호출                       |없음                  |
|#Calls 에이전트로                               |에이전트 이름<br>통화 수<br>날짜      |없음                  |
|에이전트 및 통화 큐에 의해 배포          |에이전트 이름<br>통화 수<br>통화 시간(분)<br>큐 이름 호출 |없음                      |
|왼쪽 아래                                   |에이전트 이름<br>평균 통화 시간(두 번째)<br>통화 수<br>통화 시간(분)<br>큐 이름 호출 | 없음 |
|에이전트 이름의 평균 통화 시간(초) |에이전트 이름<br>평균 통화 시간(두 번째)<br>통화 수<br>통화 시간(분)<br>큐 이름 호출 | 없음 |

#### <a name="fagenttimelineanalytics-cqd-fields-description"></a>fAgentTimelineAnalytics CQD 필드 설명

|이름                                    |데이터 형식                |설명                                         |
|:---------------------------------------|:------------------------|:---------------------------------------------------|
|에이전트 이름                              |텍스트                     |사용자 UPN<br>전체 사용자 이름이 user@microsoft.com **경우** 이 값은 **사용자입니다.** |
|평균 통화 시간(두 번째)          |10진수           |요약: 합계<br>호출 큐 호출의 평균 기간(초)입니다. |
|통화 수                              |정수             |요약: 합계<br>에이전트가 처리하는 호출 수                    |
|통화 시간(분)                  |정수             |요약: 합계<br>통화 큐 호출의 총 통화 시간(분)입니다.  |
|큐 이름 호출                         |텍스트                     |통화 큐에 연결된 리소스 계정의 이름<br><br>전체 리소스 계정 이름이 cq_test@microsoft.com **이** 값은 cq_test  |
|날짜                                    |date                     |                                                    |


## <a name="known-issues"></a>알려진 문제

- 호출 큐 및 자동 참석자는 호출 큐/자동 참석자 이름 대신 리소스 계정의 ID로 표시됩니다.  자동 참석자 또는 호출 큐에 대한 모든 트래픽을 표시하려면 자동 참석자 또는 호출 큐에 할당된 모든 리소스 계정을 선택해야 합니다.

- 통화 큐/자동 참석자 데이터가 개인 데이터로 간주되어 데이터 개인 정보 보호 보존 정책이 적용되어 대시보드에서 28일간의 기록만 사용할 수 있습니다.

- <sup>1</sup> **자동 참석자** 및 호출 큐 그래프의 들어오는 호출 원본은 초기 통화 레그 원본이 아닌 최종 호출 레그 원본을 보여줍니다. 예를 들어 자동 참석자가 외부 통화를 수신하고 다른 자동 참석자 또는 통화  큐로 통화를 전송하는 경우 들어오는 호출 원본은 내부로 보고됩니다.
