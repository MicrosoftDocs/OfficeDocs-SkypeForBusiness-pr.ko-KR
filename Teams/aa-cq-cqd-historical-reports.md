---
title: 자동 전화 교환 & 통화 큐 기록 보고서
author: CarolynRowe
ms.author: crowe
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
description: 통화 품질 대시보드 Power BI 보고서를 사용하여 자동 전화 교환 및 통화 큐 기록 데이터를 보는 방법에 대해 알아봅니다.
ms.openlocfilehash: b9bb3cf0990058cd16ed35d52d07f63be6cd90fb
ms.sourcegitcommit: 3266fde54b92a18865d666b98e4e7e8322b9dedc
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/26/2022
ms.locfileid: "67024011"
---
# <a name="auto-attendant--call-queue-historical-report"></a>자동 전화 교환 & 통화 큐 기록 보고서

Teams 자동 전화 교환 & 통화 큐 기록 보고서 Power BI 템플릿은 다음 세 가지 보고서를 제공합니다.

- [자동 전화 교환 - 자동](media/cqd-teams-aa-cq-historical-report-sample-aa.png) 전화 교환으로 들어오는 통화에 대한 분석을 보여 줍니다.
- [통화 큐 - 통화 큐](media/cqd-teams-aa-cq-historical-report-sample-cq.png) 로 들어오는 통화에 대한 분석을 보여 줍니다.
- [에이전트 타임라인](media/cqd-teams-aa-cq-historical-report-sample-at.png) - 통화 큐 호출에서 활성 상태인 에이전트의 타임라인 보기를 보여 줍니다.

이러한 보고서는 [통화 품질 대시보드](CQD-Power-BI-query-templates.md) 데이터 저장소의 데이터를 사용합니다. 보고서를 통해 조직은 자동 전화 교환 및 통화 큐에서 처리되는 통화 수를 보고할 수 있습니다.  또한 보고서는 호출 큐의 에이전트 성능에 대한 인사이트를 제공합니다.

### <a name="v160-published-on-july-22-2022"></a>2022년 7월 22일에 게시된 V1.60

## <a name="prerequisites"></a>필수 구성 요소

### <a name="power-bi-desktop"></a>Power BI Desktop
Power BI Desktop 설치해야 합니다. [Microsoft Windows 스토어](https://aka.ms/pbidesktopstore)에서 설치할 수 있습니다.

무료 버전의 Power BI Desktop 사용할 수 있습니다. 호환되는 최소 버전은 2.85.681.0(2020년 9월)입니다.

### <a name="permissions-to-access-the-cqd-pipeline"></a>CQD 파이프라인에 액세스할 수 있는 권한

기록 보고서를 보는 데 사용하는 계정에는 CQD 데이터 파이프라인에 액세스할 수 있는 권한이 있어야 합니다. 자세한 내용은 [CQD 액세스 역할을](./turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd) 참조하세요.

## <a name="installation"></a>설치 

다음 단계에서는 컴퓨터에 Power BI Desktop 이미 설치했으며 계정에 CQD 데이터 파이프라인에 액세스하는 데 필요한 권한이 있다고 가정합니다.

다음 단계를 수행합니다.

- [CQD Power BI 쿼리 템플릿을](https://www.microsoft.com/download/details.aspx?id=102291) 다운로드하고 zip 파일을 컴퓨터의 디렉터리에 저장합니다.

- zip 파일을 두 번 클릭하여 엽니다.

- "CQD Teams 자동 전화 교환 & 통화 큐 기록 보고서 V1.60.pbit" 템플릿 파일을 두 번 클릭합니다. Power BI Desktop 시작되어야 합니다.

- CQD 데이터 파이프라인 지역을 선택하라는 메시지가 표시됩니다. 테넌트가 있는 지역을 선택합니다.

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-01.png" alt-text="CQD 데이터 파이프라인 지역을 선택하는 스크린샷":::

- 테넌트가 있는 지역은 [Get-CsTenant](/powershell/module/skype/get-cstenant) cmdlet을 사용하여 가져올 수 있습니다.

    ```PowerShell
    (Get-CsTenant).ServiceInstance


    microsoftcommunicationsonline/noam-4a-s7
    ```

    - 영역은 위의 예에서와 같이 영역이 noam인 경우와 **/** 같이 표시됩니다.

 - 샘플 데이터로 보고서가 시작됩니다.
 
 - 사용자 고유의 데이터를 보려면 Power BI Desktop 쿼리 아래의 홈 탭에서 **새로 고침** 을 선택합니다.

   :::image type="content" source="media/cqd-teams-aa-cq-historical-report-02.png" alt-text="새로 고침 옵션을 선택하는 스크린샷":::

- 로그인하라는 메시지가 표시됩니다. **조직 계정을** 선택한 다음 **, 로그인을** 선택합니다.

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-03.png" alt-text="로그인을 보여 주는 스크린샷":::

- **연결을** 선택하고 데이터 새로 고침을 확인합니다.

## <a name="data-latency-and-aa--cq-analytics"></a>데이터 대기 시간 및 AA & CQ 분석

데이터는 일반적으로 호출이 완료된 후 30분 이내에 사용할 수 있습니다. 그러나 데이터가 표시되는 데 몇 시간이 걸릴 수 있는 경우가 있습니다. 

새 데이터를 보려면 데이터를 새로 고쳐야 합니다.

## <a name="customization"></a>사용자화 

다양한 시각화에 표시할 필드 추가 또는 제거, 차트 종류 변경 등 보고서의 특정 시각화 측면을 사용자 지정할 수 있습니다.

보고서에는 현재 사용할 수 있는 모든 데이터 메트릭이 포함되어 있습니다.

### <a name="change-color-schema"></a>색 스키마 변경 

다음 단계에서는 설치 단계를 이미 완료한 것으로 가정합니다.

다음 단계를 수행합니다.
- 리본에서 **보기 탭** 을 선택합니다.

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-04.png" alt-text="색 구성표를 변경할 보기 탭을 선택하는 스크린샷":::

- 드롭다운 목록에서 색 스키마를 선택합니다.

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-05.png" alt-text="다양한 색 구성표를 보여 주는 스크린샷":::
  
## <a name="auto-attendant-and-call-queue-historical-reports-definitions"></a>자동 전화 교환 및 통화 큐 기록 보고서 정의

### <a name="cloud-auto-attendant-analytics"></a>클라우드 자동 전화 교환 분석

#### <a name="report-description"></a>보고서 설명

|보고서 섹션                          |설명                                                       |
|:---------------------------------------|:-----------------------------------------------------------------|
|수신 전화 원본<sup>1</sup>        |내부/외부 호출 원본별 호출 배포             |
|디렉터리 검색 방법 합계          |검색 유형별 호출 배포                               |
|호출자 작업                           |통화 수신자별 통화 배포                             |
|호출 결과                             |최종 호출 상태별 호출 배포                          |
|호출자 작업 수                     |호출 중에 사용되는 번호 동작별 호출 분포        |


#### <a name="report-to-cqd-table-and-field-mapping"></a>CQD 테이블 및 필드 매핑에 대한 보고서

|보고서 탭            |보고서 테이블 이름     |전역 필터                          |
|:---------------------|:---------------------|:--------------------------------------|
|자동 전화 교환        |fAutoAttendant        |AAStartTime은 지난 28일 이내입니다. |


|보고서 테이블 이름            |원본 테이블 이름            |처리       |
|:----------------------------|:----------------------------|:----------------|
|fAutoAttendant               |AutoAttendant                |원본 = AutoAttendant, <br>#"필터링된 행" = Table.SelectRows(Source, each true), <br>#"자동 전화 교환" = Table.AddColumn(#"필터링된 행", "AA 이름", 각 List.First(Text.Split([AAIdentity], "@")) <br>#"Changed Type" = Table.TransformColumnTypes(#"Auto Attendant",{{"AAStartTime", type datetime}}), <br>#"Removeed Columns" = Table.RemoveColumns(#"Changed Type",{"AAIdentity"}) |


|보고서 섹션                                  |필드 사용                              |적용된 필터     |
|:-----------------------------------------------|:------------------------------------------|:-------------------|
|날짜 선택기                                   |AAStartTime                                |없음                |
|자동 전화 교환                                  |AA 이름                                    |없음                |
|수신 전화 원본<sup>1</sup>                |호출 유형<br>TotalCallCount                |외부 호출: 호출 유형이 외부입니다.<br>내부 호출: 호출 유형이 내부입니다. |
|디렉터리 검색 방법 합계                  |AADirectorySearchMethod<br>TotalCallCount  |AADirectorySearchMethod가 abs_search_dtmf 또는 abs_search_name    |
|호출자 작업                                  |AATransferAction<br>TotalCallCount         |없음                                                             |
|AA의 평균 초<br>평균 호출자 작업 |AAChainDuration<br>AACallerActionCount     |없음                                                             |
|호출 결과                                    |AACallResult<br>TotalCallCount             |없음                                                             |
|호출자 작업 수                            |AACallerActionCount<br>TotalCallCount      |없음                                                             |
|보고서의 하위 섹션                         |AA 이름<br>AACallFlow<br>AACallResult<br>AAChainDuration<br>호출 유형<br>TotalCallCount |없음                |

#### <a name="fautoattendant-cqd-fields-description"></a>fAutoAttendant CQD 필드 설명

|이름                                    |데이터 형식                |설명                            |
|:---------------------------------------|:------------------------|:--------------------------------------|
|AA 이름                                 |텍스트                     |자동 전화 교환에 연결된 리소스 계정의 이름<br><br>전체 리소스 계정 이름이 **aa_test@microsoft.com** 경우 이 값은 **aa_test** |
|AACallerActionCount                     |정수             |요약: 합계<br>통화 중 자동 전화 교환에서 호출자가 선택한 작업 수  |
|AACallFlow                              |텍스트                     |자동 전화 교환 호출의 다양한 상태(가능한 값)를 캡슐화합니다.<br><br>§ abs_search<br>§ 공지 사항<br>§ automatic_menu<br>§ call_termination<br>§ call_transfer<br>§ first_level_menu<br>§ main_menu<br>§ speech_input_confirmation<br>§ user_selection |
|AACallResult                            |텍스트                     |최종 호출 결과-가능한 값:<br><br>§ failed_to_establish_media(통화의 미디어 부분을 설정할 수 없음)<br>§ failover_to_operator(일반적으로 시스템 오류로 인해 운영자에게 전송된 호출)<br>§ oaa_chain_too_long (AA에 너무 많은 다리)<br>§ oaa_session_too_long(AA 세션이 너무 오래 지속됨)<br>§ service_declined(AA가 통화를 수락하지 않음)<br>§ service_terminated(AA 구성에서 호출 연결 끊기)<br>§ terminated_automatic_selection(AA 구성으로 호출 연결 끊기)<br>§ terminated_no_operator(정의된 연산자가 없는 오류로 인해 호출이 종료됨) <br>§ terminated_transfer_failed(전송 실패로 종료된 호출 - 일반적으로 외래 번호로)<br>***§ transferred_to_operator*** (일반적으로 사용자 입력 오류로 인해 호출이 운영자에게 전송됨)<br>§ transferred_to_receptionist(transferred_to_operator 동일)<br>§ transferred_to_self (AA의 시작 부분에 호출이 반환되었습니다 - 일반적으로 메뉴 알림 옵션에서)<br>§ transferred_to_shared_voicemail(통화가 공유 음성 메일로 전송됨)<br>§ transferred_to_user(통화가 사용자에게 전송됨 - 통화 큐 포함)<br>§ 알 수 없음(알 수 없는 오류가 발생했습니다).<br>§ user_terminated(발신자가 전화를 끊었다) |
|AAChainDuration                         |10진수           |요약: 합계<br>자동 전화 교환의 통화 기간                     |
|AAChainIndex                            |텍스트                     |                                                                         |
|AAConnectivityType                      |텍스트                     |호출 유형- 가능한 값:<br><br>§ ExternalCall<br>§ InternalCall |
|AACount                                 |텍스트                     |통화에 관련된 자동 전화 교환 수                               |
|AADirectorySearchMethod                 |텍스트                     |마지막 주소록 검색 방법- 가능한 값:<br><br>§ abs_search_dtmf<br>§ abs_search_extension_x<br>§ abs_search_name |
|AAStartTime                             |날짜/시간                |자동 전화 교환 통화 시작 시간                                           |
|AATransferAction                        |텍스트                     |호출 전송 대상 유형-가능한 값:<br><br>***§ 애플리케이션 - 음성 애플리케이션 엔터티**_<br>§ external_pstn<br>_*_§ hunt_group - 통화 큐 엔터티_*_<br>_*_§ orgaa - 조직 자동 전화 교환 엔터티_**<br>§ shared_voicemail<br>§ 알 수 없음<br>§ 사용자 |
|통화 유형<sup>1</sup>                   |텍스트                     |호출 유형- 가능한 값:<br><br>§ 외부<br>§ 내부         |
|IsAAInvolved                            |텍스트                     |항상 1                                                                 |
|PSTNMinutes                             |정수             |요약: 합계<br>총 분 사용량                                     |
|TotalCallCount                          |정수             |요약: 합계<br>Always 1 - 모든 호출의 합계를 제공하는 데 사용됨            |


### <a name="cloud-call-queue-analytics"></a>클라우드 호출 큐 분석

#### <a name="report-description"></a>보고서 설명

|보고서 섹션                          |설명                                                        |
|:---------------------------------------|:------------------------------------------------------------------|
|수신 전화 원본<sup>1</sup>        |내부/외부 호출 원본별 호출 배포              |
|통화 볼륨                             |통화 큐별 통화 배포                                |
|호출자 결과                           |호출 결과별 호출 분포                                |
|시간 제한/오버플로 호출 총 작업      |호출 결과에 의한 전달되지 않음(중단된) 호출 배포       |
|전송/전달 대상 합계          |호출 결과에 의해 전달된 호출 배포                      |
|중단된 호출 비율                   |성공한 호출 수와 중단된 호출 수의 비율                        |
|평균 세션 길이(초)        |중단/성공한 호출로 그룹화된 통화 길이(초)       |

#### <a name="report-to-cqd-table-and-field-mapping"></a>CQD 테이블 및 필드 매핑에 대한 보고서

|보고서 탭         |보고서 테이블 이름                                                          |전역 필터 |
|:------------------|:---------------------------------------------------------------------------|:-------------|
|통화 큐         |날짜<br>dCQ-CQIdenity<br>fCallQueueAnalytics<br>fCallQueueFinalStateAction |없음          |
 
|보고서 테이블 이름            |원본 테이블 이름            |처리       |
|:----------------------------|:----------------------------|:----------------|
|날짜                        |날짜                        |없음             |
|dCQ-CQIdentity               |CallQueueAnalytics           |원본 = CallQueueAnalytics, <br>#"Removeed Columns" = Table.RemoveColumns(Source,{"Call Count", "Call Queue Call Result", "Date", "PSTN Connectivity Type", "Call Queue Target Type", "PSTN Total Minutes"}),<br>Distinct = Table.Distinct(#"제거된 열") |
|fCallQueueAnalytics          |CallQueueAnalytics           |없음             |
|fCallQueueFinalStateAction   |CallQueueFinalStateAction    |없음             |

|보고서 섹션                      |테이블 -> 필드 사용                |적용된 필터       |
|:-----------------------------------|:-------------------------------------|:---------------------|
|날짜 선택기                       |Date -> DateTime                     |없음                  |
|통화 큐 ID                 |dCQ-CQIdentity -> 호출 큐 ID |없음                  |
|수신 전화 원본<sup>1</sup>    |fCallQueueAnalytics -> 통화 수<br>fCallQueueAnalytics -> 통화 유형    |외부 호출: 호출 유형이 외부입니다.<br>내부 호출: 호출 유형이 내부입니다. |
|평균 대기 시간                    |fCallQueueFinalStateAction -> 평균 호출 기간(초) |전송 전: 통화 큐 호출 결과가 agent_joined_conference 또는 transferred_to_agent<br>중단 전: 통화 큐 호출 결과가 agent_joined_conference 않거나 transferred_to_agent 않습니다. |
|호출 결과                         |fCallQueueAnalytics -> 통화 수<br>fCallQueueAnalytics -> 통화 큐 호출 결과 | 없음 |
|시간 제한/오버플로 호출 총 작업 |fCallQueueFinalStateAction -> 호출 수<br>fCallQueueFinalStateAction -> 호출 큐 최종 상태 작업 |통화 큐 최종 상태 작업이 전달되지 않음 |
|전송/포라드 대상 합계       |fCallQueueAnalytics -> 통화 수<br>fCallQueueAnalytics -> 통화 큐 대상 유형 |없음 |
|통화 볼륨                        |fCallQueueAnalytics -> 통화 수<br>fCallQueueAnalytics -> 통화 큐 식별<br>fCallQueueAnalytics -> 날짜 |없음 |
|중단된 통화                     |fCallQueueAnalytics -> %Abandoned 호출<br>fCallQueueAnalytics -> 통화 수<br>fCallQueueAnalytics -> 날짜<br>fCallQueueAnalytics -> IsAbandoned |IsAbandoned is True |
|평균 세션 길이(초)    |fCallQueueFinalStateAction -> 평균 호출 기간<br>fCallQueueFinalStateAction -> 날짜<br>fCallQueueFinalStateAction -> IsAbandoned |없음 |

#### <a name="dcq-cqidenity-cqd-fields-description"></a>dCQ-CQIdenity CQD 필드 설명

|이름                                    |데이터 형식                |설명                            |
|:---------------------------------------|:------------------------|:--------------------------------------|
|통화 큐 ID                     |텍스트                     |통화 큐에 연결된 리소스 계정의 이름<br><br>전체 리소스 계정 이름이 **cq_test@microsoft.com** 경우 이 값은 **cq_test** |

#### <a name="fcallqueueanalytics-cqd-fields-description"></a>fCallQueueAnalytics CQD 필드 설명

|이름                                    |데이터 형식                |설명                                                                |
|:---------------------------------------|:------------------------|:--------------------------------------------------------------------------|
|통화 수                              |정수             |요약: 합계<br>호출 수                                          |
|통화 큐 호출 결과                  |텍스트                     |호출 큐 호출 최종 상태-가능한 값:<br><br>§ agent_joined_conference(응답된 전화 회의 모드 통화)<br>§ 거부됨<br>§ 연결이 끊김<br>§ 오류<br>§ 실패<br>§ 잘못되었습니다.<br>§ 오버플로(오버플로 조건이 충족됨)<br>§ timed_out(시간 제한 조건이 충족됨)<br>§ transferred_to_agent(응답된 트랜퍼 모드 호출 {default}) |
|통화 큐 ID                     |텍스트                     |통화 큐에 연결된 리소스 계정의 이름<br><br>전체 리소스 계정 이름이 **cq_test@microsoft.com** 경우 이 값은 **cq_test** |
|통화 큐 대상 유형                  |텍스트                     |***호출 리디렉션 대상 유형-가능한 값:***<br><br>§ ApplicationEndpoint<br>§ 사서함<br>§ 기타<br>§ 사용자 |
|통화 유형<sup>1</sup>                   |텍스트                     |호출 유형- 가능한 값:<br><br>§ 외부<br>§ 내부           |
|날짜                                    |날짜/시간                |통화 큐 호출 시작 날짜 및 시간(시간)(UTC)                           | 
|IsAbandoned                             |True/false               |에이전트에서 전화를 받지 못한 경우 True입니다.                                   |
|PSTN 연결 유형                  |텍스트                     |호출 유형- 가능한 값:<br><br>§ ExternalCall<br>§ InternalCall   |
|PSTN 총 시간(분)                      |정수             |요약: 합계<br>PSTN 호출의 총 시간(분)                       |

#### <a name="fcallqueueanalytics-measures-description"></a>fCallQueueAnalytics 측정값 설명

|이름                                    |데이터 형식                |설명                              |
|:---------------------------------------|:------------------------|:----------------------------------------|
|***% 중단된 통화***                 |비율               |측정값: 중단된 호출 수/총 호출 수    |
|총 호출 수                             |정수             |측정값: 에이전트 응답 전화 합계        |
|TotalCallCount                          |정수             |측정값: Sum(호출 수)                 |

#### <a name="fcallqueuefinalstateaction--cqd-fields-description"></a>fCallQueueFinalStateAction CQD 필드 설명

|이름                                    |데이터 형식                |설명                                        |
|:---------------------------------------|:------------------------|:--------------------------------------------------|
|평균 통화 기간(초)         |10진수           |요약: 합계<br>평균 통화 기간(초) |
|통화 수                              |정수             |요약: 합계<br>호출 수                  |
|통화 큐 호출 결과                  |텍스트                     |호출 큐 호출 최종 상태-가능한 값:<br><br>§ agent_joined_conference(응답된 전화 회의 모드 통화)<br>§ 거부됨<br>§ 연결이 끊김<br>§ 오류<br>§ 실패<br>§ 잘못되었습니다.<br>§ 오버플로(오버플로 조건이 충족됨)<br>§ timed_out(시간 제한 조건이 충족됨)<br>§ transferred_to_agent(응답된 전송 모드 호출 {default} |
|큐 최종 상태 작업 호출           |텍스트                     |큐 최종 작업 호출-가능한 값:<br><br>§ 연결 끊기(timed_out 통화)<br>§ disconnect_with_busy(오버플로 호출)<br>§ failed_to_accept_call<br>§ 앞으로<br>§ shared_voicemail<br>§ 기타<br>§ 음성 메일 |
|통화 큐 ID                     |텍스트                     |통화 큐에 연결된 리소스 계정의 이름<br><br>전체 리소스 계정 이름이 **cq_test@microsoft.com** 경우 이 값은 **cq_test** |
|날짜                                    |날짜/시간                |통화 큐 호출 시작 날짜 및 시간(시간)(UTC)   |
|IsAbandoned                             |True/false               |에이전트에서 전화를 받지 못한 경우 True입니다.           |


### <a name="cloud-call-queue-agent-timeline"></a>클라우드 호출 큐 에이전트 타임라인

#### <a name="report-description"></a>보고서 설명

|보고서 섹션                                          |설명                                                  |
|:-------------------------------------------------------|:------------------------------------------------------------|
|에이전트별 # 호출                                        |통화 큐 및 에이전트별 통화 배포                 |
|에이전트 및 통화 큐별 총 통화 기간(초)   |에이전트 및 통화 큐별 총 통화 기간(초)     |
|에이전트 이름별 평균 통화 기간(초)           |에이전트별 평균 통화 기간(초)                  |

#### <a name="report-to-cqd-table-and-field-mapping"></a>CQD 테이블 및 필드 매핑에 대한 보고서

|보고서 탭         |보고서 테이블 이름        |전역 필터 |
|:------------------|:-------------------------|:-------------|
|에이전트 타임라인     |fAgentTimelineAnalytics   |없음          |
 
|보고서 테이블 이름            |원본 테이블 이름            |처리       |
|:----------------------------|:----------------------------|:----------------|
|fAgentTimelineAnalytics      |AgentTimelineAnalytics       |원본 = AgentTimelineAnalytics, <br>#"Changed Type" = Table.TransformColumnTypes(Source,{{"Call Count", Int64.Type}, {"Call Duration (Minute)", Int64.Type}, {"Average Call Duration (Second)", type number}, {"Date", type date}})|

|보고서 섹션                                |필드 사용                         |적용된 필터       |
|:---------------------------------------------|:-------------------------------------|:---------------------|
|에이전트 이름                                    |에이전트 이름                            |없음                  |
|통화 큐 이름                               |통화 큐 이름                       |없음                  |
|에이전트별 #Calls                               |에이전트 이름<br>통화 수<br>날짜      |없음                  |
|에이전트 및 통화 큐별 배포          |에이전트 이름<br>통화 수<br>통화 기간(분)<br>통화 큐 이름 |없음                      |
|왼쪽 아래                                   |에이전트 이름<br>평균 통화 기간(초)<br>통화 수<br>통화 기간(분)<br>통화 큐 이름 | 없음 |
|에이전트 이름별 평균 통화 기간(초) |에이전트 이름<br>평균 통화 기간(초)<br>통화 수<br>통화 기간(분)<br>통화 큐 이름 | 없음 |

#### <a name="fagenttimelineanalytics-cqd-fields-description"></a>fAgentTimelineAnalytics CQD 필드 설명

|이름                                    |데이터 형식                |설명                                         |
|:---------------------------------------|:------------------------|:---------------------------------------------------|
|에이전트 이름                              |텍스트                     |사용자 UPN<br>전체 사용자 이름이 **user@microsoft.com** 경우 이 값은 **사용자** 입니다. |
|평균 통화 기간(초)          |10진수           |요약: 합계<br>응답된 통화 큐 호출의 평균 기간(초) |
|통화 수                              |정수             |요약: 합계<br>에이전트에 표시되는 호출 수     |
|통화 기간(분)                  |정수             |요약: 합계<br>응답된 통화 큐 호출의 총 통화 기간(분)(가장 가까운 분으로 반올림)  |
|통화 큐 이름                         |텍스트                     |통화 큐에 연결된 리소스 계정의 이름<br><br>전체 리소스 계정 이름이 **cq_test@microsoft.com** 경우 이 값은 **cq_test** |
|날짜                                    |날짜                     |                                                    |


> [!NOTE]
> 1) 이 보고서는 에이전트의 관점에서 호출 수를 보여 줍니다. 따라서 이 보고서의 총 호출 수는 일반적으로 **클라우드 호출 큐 분석** 보고서의 총 호출 수보다 높습니다. 큐의 각 호출은 응답하기 전에 하나 이상의 에이전트에 한 번 이상 표시될 수 있습니다. 에이전트가 응답하지 않더라도 에이전트에 표시되는 모든 통화 큐 호출은 이 보고서에 계산됩니다. 이러한 두 보고서 간의 통화 수 차이는 모든 통화에 대해 모든 에이전트를 울리는 **전화 교환 라우팅** 옵션으로 더욱 두드러집니다. 
> 2) 호출이 처음 첫 번째 호출 큐에 도착하면 해당 큐에서 이미 대기 중인 호출 수가 **통화 오버플로 처리** 제한을 초과하고 리디렉션 옵션이 두 번째 호출 큐에 호출을 보내는 경우 두 번째 호출 큐의 에이전트가 이 보고서의 첫 번째 호출 큐에 있는 것으로 표시됩니다. 

## <a name="known-issues"></a>알려진 문제

- 통화 큐 및 자동 전화 교환은 통화 큐/자동 전화 교환 이름 대신 리소스 계정의 ID로 표시됩니다.  자동 전화 교환 또는 통화 큐에 대한 모든 트래픽을 표시하려면 자동 전화 교환 또는 통화 큐에 할당된 모든 리소스 계정을 선택해야 합니다.

- 통화 큐/자동 전화 교환 데이터가 개인 데이터로 간주되고 데이터 개인 정보 보존 정책이 적용되므로 대시보드에서 28일의 기록만 사용할 수 있습니다.

- 일부 시나리오에서는 클라우드 통화 큐 에이전트 타임라인 보고서의 에이전트 응답 통화 수가 Teams 클라이언트 통화 기록에 표시된 통화 수와 다를 수 있습니다. Teams 클라이언트 통화 기록이 정확합니다. 지원은 조사 중이지만 현재 복구할 수 있는 예상 시간은 없습니다.

- <sup>1</sup> 자동 전화 교환 및 통화 큐 그래프에서 **들어오는 호출 원본** 은 초기 호출 레그 원본이 아닌 최종 통화 레그 원본을 표시합니다. 예를 들어 자동 전화 교환이 외부 전화를 받고 다른 자동 전화 교환 또는 통화 큐로 통화를 전송하는 경우 **수신 전화 원본** 은 내부로 보고됩니다.

## <a name="version-history"></a>버전 기록
|버전  |게시된 날짜     |파일                                                           |설명                                         |
|:--------|:------------------|:------------------------------------------------------------------|:---------------------------------------------------|
|1.60     |2022년 7월 22일      |CQD Teams 자동 전화 교환 & 통화 큐 기록 보고서 V1.60.pbit |다음을 참조하세요.<br>CQD Teams 자동 전화 교환 & 통화 큐 기록 보고서 - 변경 내용 목록에 대해 다운로드한 zip 파일의 변경 Log.docx                                                                             |
|1.00     |2020년 11월 5일   |CQ 및 AA 결합 분석 20201105.pbit                         |초기 릴리스                                     |



