---
title: 자동 전화 교환 & 통화 큐 기록 보고서
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
description: Teams 자동 전화 교환 & 통화 큐 기록 보고서 Power BI 보고서를 사용하여 자동 전화 교환 및 통화 큐 기록 데이터를 보는 방법에 대해 알아봅니다.
ms.openlocfilehash: 3db0705ea1321b3ef6d2efef5a01e3283f091cc9
ms.sourcegitcommit: ff161779577ce9cc892f1b6b8861ad49ff4c3ca3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2022
ms.locfileid: "69131197"
---
# <a name="auto-attendant--call-queue-historical-report"></a>자동 전화 교환 & 통화 큐 기록 보고서

이 Power BI 템플릿은 조직에서 자동 전화 교환 및 통화 큐에서 처리되는 통화 수를 보고할 수 있는 세 가지 보고서를 제공합니다.  또한 에이전트 성능 인사이트를 제공합니다.

## <a name="v304-published-on-november-18-2022"></a>2022년 11월 18일에 게시된 V3.0.4

Teams 자동 전화 교환 & 통화 큐 기록 보고서 Power BI 템플릿은 다음 세 가지 보고서를 제공합니다.

- [자동 전화 교환](media/aa-cq-historical-report-sample-aa-v304.png) 보고서에는 자동 전화 교환으로 들어오는 통화에 대한 분석이 표시됩니다.
- [통화 큐 보고서에는 통화 큐](media/aa-cq-historical-report-sample-cq-v304.png)로 들어오는 통화에 대한 분석이 표시됩니다.
- [에이전트 타임라인](media/aa-cq-historical-report-sample-at-v304.png) 보고서에는 통화 큐 호출에서 활성 상태인 에이전트의 타임라인 보기가 표시됩니다.

이러한 보고서는 VAAC(음성 애플리케이션 분석 수집기) 서비스의 데이터를 사용합니다.

>[!NOTE]
> 기록 데이터 수집은 모든 지역에서 진행 중입니다.  2022년 11월 25일까지 모든 지역에 30일간의 데이터가 있는 30일간의 기록 데이터를 서로 다른 시간에 사용할 수 있습니다.
>
> GCCH/DOD 고객은 V1.63을 계속 사용해야 합니다.

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

1. zip 파일을 엽니다.

1. `Teams Auto Attendant & Call Queue Historical Reports V3.0.4.pbit` 템플릿 파일을 엽니다. Power BI Desktop 시작되어야 합니다.

1. **데이터 원본** 을 선택하라는 메시지가 표시됩니다.  `api.interfaces.records.teams.microsoft.com` 항목을 선택합니다.

  :::image type="content" source="media/aa-cq-historical-report-01-v304.png" alt-text="api.interfaces.records.teams.microsoft.com Data Soure를 선택하는 스크린샷":::

1. 계정으로 로그인하라는 메시지가 표시됩니다. **조직 계정을** 선택한 다음 **로그인을** 선택합니다.

  :::image type="content" source="media/aa-cq-historical-report-03-v300.png" alt-text="V3.0.0에 대한 로그인을 보여 주는 스크린샷":::

1. **연결을** 선택하면 데이터가 새로 고쳐집니다.

> [!NOTE]
> v1.63 이하를 사용하는 경우 v3.x.x가 VAAC에서 데이터를 검색하려고 할 때 오류가 발생할 수 있습니다.  이 오류를 해결하려면 Power BI에서 이전 자격 증명을 지워야 합니다.
> 
> 1. v3.x.x 템플릿을 열어 오류를 지웁합니다. 
> 1. **파일** > **옵션 & 설정** > **데이터 원본 설정을** 선택합니다.
> 1. **삭제 권한** 에 대한 드롭다운을 선택한 다음 **모든 권한 지우기를** 선택합니다.
> 1. 템플릿이 지워진 후 템플릿을 닫고 Power BI를 다시 시작합니다. 다시 권한을 부여하라는 메시지가 표시됩니다. 

## <a name="v163-published-on-august-24-2022"></a>2022년 8월 24일에 게시된 V1.63

> [!IMPORTANT]
> V1.63 템플릿에 대한 퍼블릭 클라우드 지원은 2022년 11월 25일에 종료됩니다.
> 
> GCCH/DOD 고객은 V1.63을 계속 사용해야 합니다.

**Teams 자동 전화 교환 & 통화 큐 기록 보고서 Power BI 템플릿** 은 다음 세 가지 보고서를 제공합니다.

- [자동 전화 교환](media/aa-cq-historical-report-sample-aa-v163.png) 보고서에는 자동 전화 교환으로 들어오는 통화에 대한 분석이 표시됩니다.
- [통화 큐 보고서에는 통화 큐](media/aa-cq-historical-report-sample-cq-v163.png)로 들어오는 통화에 대한 분석이 표시됩니다.
- [에이전트 타임라인](media/aa-cq-historical-report-sample-at-v163.png) 보고서에는 통화 큐 호출에서 활성 상태인 에이전트의 타임라인 보기가 표시됩니다.

이러한 보고서는 [CQD(통화 품질 대시보드)](CQD-Power-BI-query-templates.md) 데이터 저장소의 데이터를 사용합니다. 

## <a name="v163-prerequisites"></a>V1.63 필수 구성 요소

### <a name="power-bi-desktop"></a>Power BI Desktop
Power BI Desktop 설치해야 합니다. [Microsoft Windows 스토어](https://aka.ms/pbidesktopstore)에서 무료 버전을 설치하고 사용할 수 있습니다.

호환되는 최소 버전은 2.85.681.0(2020년 9월)입니다.

### <a name="permissions-to-access-the-cqd-pipeline"></a>CQD 파이프라인에 액세스할 수 있는 권한

기록 보고서를 보는 데 사용하는 계정에는 CQD 데이터 파이프라인에 액세스할 수 있는 권한이 있어야 합니다. 자세한 내용은 [CQD 액세스 역할을 참조하세요](./turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd).

## <a name="v163-installation"></a>V1.63 설치 

다음 단계에서는 컴퓨터에 Power BI Desktop 이미 설치했으며 계정에 CQD 데이터 파이프라인에 액세스하는 데 필요한 권한이 있다고 가정합니다.

다음 단계를 수행합니다.

1. [컴퓨터에 CQD Power BI 쿼리 템플릿](https://www.microsoft.com/download/details.aspx?id=102291) zip 파일을 다운로드하여 저장합니다.

1. zip 파일을 엽니다.

1. `CQD Teams Auto Attendant & Call Queue Historical Report V1.60.pbit` 템플릿 파일을 엽니다. Power BI Desktop 시작되어야 합니다.

1. CQD 데이터 파이프라인 지역을 선택하라는 메시지가 표시됩니다. 테넌트가 있는 지역을 선택합니다.

  :::image type="content" source="media/aa-cq-historical-report-01-v163.png" alt-text="CQD 데이터 파이프라인 지역을 선택하는 스크린샷":::

1. 테넌트가 있는 지역은 [Get-CsTenant](/powershell/module/skype/get-cstenant) cmdlet을 사용하여 가져올 수 있습니다.

    ```powershell
    (Get-CsTenant).ServiceInstance


    microsoftcommunicationsonline/noam-4a-s7
    ```

    1. 영역이 인 위의 예제와 같이 지역 다음에 **/** 표시됩니다 `noam`.

 1. 이 보고서는 샘플 데이터로 시작됩니다.
 
 1. 사용자 고유의 데이터를 보려면 Power BI Desktop 쿼리 아래 **의 홈** 탭에서 **새로 고침****을** 선택합니다.

   :::image type="content" source="media/aa-cq-historical-report-02-v163.png" alt-text="새로 고침 옵션을 선택하는 스크린샷":::

1. 로그인하라는 메시지가 표시됩니다. **조직 계정을** 선택한 다음 **로그인을** 선택합니다.

  :::image type="content" source="media/aa-cq-historical-report-03-v163.png" alt-text="V1.63에 대한 로그인을 보여 주는 스크린샷":::

1. **연결을** 선택하면 데이터가 새로 고쳐집니다.

## <a name="data-latency-and-aa--cq-analytics"></a>데이터 대기 시간 및 AA & CQ 분석

데이터는 일반적으로 호출이 완료된 후 30분 이내에 사용할 수 있습니다. 그러나 데이터가 표시되는 데 몇 시간이 걸릴 수 있는 경우가 있습니다. 

새 데이터를 보려면 데이터를 새로 고쳐야 합니다.

## <a name="customization"></a>사용자화 

다양한 시각화에 표시할 필드 추가 또는 제거, 차트 종류 변경 등 보고서의 특정 시각화 측면을 사용자 지정할 수 있습니다.

보고서에는 현재 사용 가능한 모든 데이터 메트릭이 포함되어 있습니다.

### <a name="change-color-schema"></a>색 스키마 변경 

다음 단계에서는 설치 단계를 이미 완료한 것으로 가정합니다.

다음 단계를 수행합니다.

- 리본에서 **보기 탭** 을 선택합니다.

  :::image type="content" source="media/aa-cq-historical-report-04.png" alt-text="보기 탭을 선택하여 색 구성표를 변경하는 스크린샷":::

- 드롭다운 목록에서 색 스키마를 선택합니다.

  :::image type="content" source="media/aa-cq-historical-report-05.png" alt-text="다양한 색 구성표를 보여 주는 스크린샷":::
  
## <a name="auto-attendant-and-call-queue-historical-reports-definitions"></a>자동 전화 교환 및 통화 큐 기록 보고서 정의

### <a name="cloud-auto-attendant-analytics-report"></a>클라우드 자동 전화 교환 분석 보고서

#### <a name="report-description"></a>보고서 설명

|보고서 섹션                          |설명                                                       |
|:---------------------------------------|:-----------------------------------------------------------------|
|수신 전화 원본<sup>1</sup>        |내부/외부 호출 원본별 호출 배포            |
|디렉터리 검색 방법                 |검색 유형별 호출 배포                              |
|호출자 작업 수                     |통화 중에 사용되는 번호 동작별 호출 분포       |
|AA의 평균 초                   |호출자가 AA에서 소비하는 평균 시간(초)                 |
|평균 호출자 작업                  |호출자가 AA에서 수행하는 평균 작업 수               |
|호출 결과                            |최종 호출 상태별 호출 배포                         |
|보고서의 아래쪽 섹션                 |통화 흐름 분석                                               |



#### <a name="report-to-cqd-table-and-field-mapping"></a>CQD 테이블 및 필드 매핑에 보고

|보고서 탭            |보고서 테이블 이름     |원본 테이블 이름            |전역 필터                          |
|:---------------------|:---------------------|:----------------------------|:--------------------------------------|
|자동 전화 교환        |fAutoAttendant        |AutoAttendant                |없음                                   |

|보고서 섹션                                  |사용된 필드                              |적용된 필터     |
|:-----------------------------------------------|:------------------------------------------|:-------------------|
|날짜 선택기                                   |AAStartTime                                |없음                |
|시간 범위 선택기                             |AAStartHour                                |없음                |
|자동 전화 교환                                  |AA 이름                                    |없음                |
|수신 전화 원본<sup>1</sup>                |호출 유형<br>TotalCallCount의 합계(측정값) |외부 호출: 호출 유형이 외부입니다.<br>내부 호출: 호출 유형이 내부입니다. |
|디렉터리 검색 방법                         |AADirectorySearchMethod<br>TotalCallCount  |AADirectorySearchMethod가 abs_search_dtmf 또는 abs_search_name    |
|호출자 작업 수                             |AACallerActionCount<br>TotalCallCount      |없음                                                             |
|AA의 평균 초                           |AAChainDuration(측정값)                  |없음                                                             |
|평균 호출자 작업                          |AACallerActionCount(측정값)              |없음                                                             |
|호출 결과                                    |AACallResult<br>AACallResultLegend<br>TotalCallCount             |없음                                       |
|보고서의 아래쪽 섹션                         |AA 이름<br>AACallFlow<br>AACallResult<br>AAChainDuration<br>호출 유형<br>MM-DD<br>TotalCallCount |없음       |

#### <a name="fautoattendant-cqd-fields-description"></a>fAutoAttendant CQD 필드 설명

|이름                                    |데이터 형식                |설명                            |
|:---------------------------------------|:------------------------|:--------------------------------------|
|AA 이름                                 |텍스트                     |자동 전화 교환에 연결된 리소스 계정의 이름<br><br>전체 리소스 계정 이름이 **aa_test@microsoft.com** 경우 이 값은 **aa_test** |
|AACallerActionCount                     |정수             |요약: 합계<br>통화 중 자동 전화 교환에서 호출자가 선택한 작업 수  |
|AACallerActionCount(측정값)          |정수             |공백 대신 호출이 없으면 위와 동일하게 0이 됩니다.                              |
|AACallFlow                              |텍스트                     |자동 전화 교환 호출의 다양한 상태(가능한 값)를 캡슐화합니다.<br><br>§ abs_search<br>§ 공지 사항<br>§ automatic_menu<br>§ call_termination<br>§ call_transfer<br>§ first_level_menu<br>§ main_menu<br>§ speech_input_confirmation<br>§ user_selection |
|AACallResult                            |텍스트                     |최종 호출 결과-가능한 값:<br><br>§ failed_to_establish_media(통화의 미디어 부분을 설정할 수 없음)<br>§ failover_to_operator(일반적으로 시스템 오류로 인해 운영자에게 전송된 호출)<br>§ oaa_chain_too_long (AA에 너무 많은 다리)<br>§ oaa_session_too_long(AA 세션이 너무 오래 지속됨)<br>§ service_declined(AA가 통화를 수락하지 않음)<br>§ service_terminated(AA 구성이 전화를 끊거나 전화를 끊는 경우)<br>§ terminated_automatic_selection(AA 구성으로 호출 연결 끊기)<br>§ terminated_no_operator(정의된 연산자가 없는 오류로 인해 호출이 종료됨) <br>§ terminated_transfer_failed(전송 실패로 종료된 호출 - 일반적으로 외부 번호로)<br>§ transfer_in_progress(AA >AA 전송)<br>§ transferred_to_operator(호출이 운영자에게 전송되었습니다. 일반적으로 사용자 오류로 인해)<br>§ transferred_to_receptionist(transferred_to_operator 동일)<br>§ transferred_to_self(일반적으로 메뉴 알림 옵션에서 호출이 AA의 시작 부분에 반환됨)<br>§ transferred_to_shared_voicemail(통화가 공유 음성 메일로 전송됨)<br>§ transferred_to_user(통화가 사용자에게 전송됨 - 통화 큐 포함)<br>§ 알 수 없음(알 수 없는 상태가 발생했습니다).<br>§ user_terminated (발신자가 전화를 끊었다) |
|AA 호출 범례                          |텍스트                     |AACallResult를 기반으로 범례 항목 설정                               |
|AAChainDuration                         |10진수           |요약: 합계<br>자동 전화 교환의 통화 기간                     |
|AAChainDuration(측정값)               |10진수           |공백 대신 호출이 없으면 위와 동일하게 0이 됩니다.              |
|AAChainIndex                            |텍스트                     |                                                                         |
|AAConnectivityType                      |텍스트                     |호출 유형-가능한 값:<br><br>§ ExternalCall<br>§ InternalCall |
|AACount                                 |텍스트                     |통화에 관련된 자동 전화 교환 수                               |
|AADirectorySearchMethod                 |텍스트                     |마지막 주소록 검색 방법-가능한 값:<br><br>§ abs_search_dtmf<br>§ abs_search_extension_x<br>§ abs_search_name |
|AAStartHour                             |10진수           |자동 전화 교환 통화 시작 시간                                           |
|AAStartTime                             |날짜/시간                |자동 전화 교환 통화 시작 시간                                           |
|AATransferAction                        |텍스트                     |호출 전송 대상 유형-가능한 값:<br><br>§ 애플리케이션 - 음성 애플리케이션 엔터티<br>§ external_pstn<br>§ hunt_group - 통화 큐 엔터티<br>§ orgaa - 자동 전화 교환 엔터티<br>§ shared_voicemail<br>§ 알 수 없음<br>§ 사용자 |
|호출 유형<sup>1</sup>                   |텍스트                     |호출 유형-가능한 값:<br><br>§ 외부<br>§ 내부           |
|IsAAInvolved                            |텍스트                     |항상 1                                                                 |
|MM-DD                                   |텍스트                     |자동 전화 교환 통화 월-일                                            |
|PSTNMinutes                             |정수             |요약: 합계<br>총 분 사용량                                     |
|TotalCallCount                          |정수             |요약: 합계<br>Always 1 - 모든 호출의 합계를 제공하는 데 사용됩니다.            |
|TotalCallCount의 합계(측정값)         |정수             |공백 대신 호출이 없으면 위와 동일하게 0이 됩니다.              |


### <a name="cloud-call-queue-analytics-report"></a>Cloud Call Queue Analytics 보고서

#### <a name="report-description"></a>보고서 설명

|보고서 섹션                          |설명                                                        |
|:---------------------------------------|:------------------------------------------------------------------|
|수신 전화 원본<sup>1</sup>        |내부/외부 호출 원본별 호출 배포             |
|평균 대기 시간(초)             |응답된 통화 및 중단된 통화 대기 시간                          |
|통화 볼륨 및 에이전트 옵트인 수      |통화 큐별 호출 배포/최대 에이전트 옵트인 수  |
|호출 결과                            |호출 결과별 호출 분포                               |
|중단된 통화                         |통화 큐별 중단된 호출 배포                     |
|평균 세션 길이(초)        |호출 결과별로 그룹화된 통화 길이(초)                      |
|오버플로/시간 제한 대상 호출      |시간이 초과되거나 오버플로된 호출 배포                 |


#### <a name="report-to-cqd-table-and-field-mapping"></a>CQD 테이블 및 필드 매핑에 보고

|보고서 탭            |보고서 테이블 이름                                   |원본 테이블 이름                               |전역 필터       |
|:---------------------|:---------------------------------------------------|:-----------------------------------------------|:-------------------|
|통화 큐            |fCallQueueAnalytics<br>fCallQueueFinalStateAction   |CallQueueAnalytics<br>CallQueueFinalStateAction |없음                |

|보고서 섹션                      |테이블 -> 필드 사용                |적용된 필터       |
|:-----------------------------------|:-------------------------------------|:---------------------|
|날짜 선택기                       |fCallQueueAnalytics -> 날짜           |없음                  |
|시간 범위 선택기                 |fCallQueueAnalytics -> CQHour         |없음                  |
|큐 리소스 계정 호출         |fCallQueueAnalytics -> CQ 이름        |없음                  |
|들어오는 호출 원본<sup>1</sup>    |fCallQueueAnalytics -> 호출 수의 합계(측정값)<br>fCallQueueAnalytics -> 통화 유형    |외부 호출: 호출 유형이 외부입니다.<br>내부 호출: 호출 유형이 내부입니다. |
|평균 대기 시간(초)-답변 전 |fCallQueueFinalStateAction -> 평균 CQ 기간의 평균(측정값) |호출 큐 호출 결과가 agent_joined_conference 또는 transferred_to_agent|
|평균 대기 시간(초)-중단 전 |fCallQueueFinalStateAction -> 평균 호출 기간의 평균(측정값) |호출 큐 호출 결과가 agent_joined_conference, transferred_to_agent, 오버플로, timed_out |
|통화 볼륨 및 에이전트 Opt-In 수   |fCallQueueAnalytics -> 통화 수<br>fCallQueueAnalytics -> 통화 큐 에이전트 옵트인 수<br>fCallQueueAnalytics -> CQ 이름<br>fCallQueueAnalytics -> 날짜 |없음 |
|중단된 통화                     |fCallQueueAnalytics -> 날짜<br>fCallQueueAnalytics -> TotalCallCount | 호출 큐 호출 결과 범례가 중단됨 |
|평균 세션 길이(초)    |fCallQueueFinalStateAction -> 평균 통화 큐 기간(초)<br>호출 큐 호출 결과 범례 |평균 통화 큐 기간(초) > 0 |
|오버플로/시간 제한 대상 호출  |fCallQueueAnalytics -> 통화 수<br>fCallQueueAnalytics -> 호출 큐 대상 유형<br>fCallQueue 대상 형식 범례 |호출 큐 대상 유형 범례에 중단됨 및 에이전트 응답이 포함되지 않음 |


#### <a name="fcallqueueanalytics-cqd-fields-description"></a>fCallQueueAnalytics CQD 필드 설명

|이름                                    |데이터 형식                |설명                                                                |
|:---------------------------------------|:------------------------|:--------------------------------------------------------------------------|
|호출 수                              |정수             |요약: 합계<br>호출 수                                          |
|통화 큐 에이전트 수                  |정수             |요약: 합계<br>호출 큐에 구성된 에이전트 수            |
|통화 큐 에이전트 옵트인 수           |정수             |요약: 합계<br>통화 큐에 옵트인된 에이전트 수              |
|통화 큐 호출 결과                  |텍스트                     |호출 큐 호출 최종 상태-가능한 값:<br><br>§ agent_joined_conference(응답된 전화 회의 모드 통화)<br>§ 거부됨<br>§ 연결이 끊김<br>§ 오류<br>§ 실패<br>§ 유효하지 않음<br>§ 오버플로(오버플로 조건이 충족됨)<br>§ timed_out(시간 제한 조건이 충족됨)<br>§ transferred_to_agent(응답된 전송 모드 호출 {default}) |
|호출 큐 호출 결과 범례           |텍스트                     |통화 큐 결과에 따라 범례 항목 설정                             |
|호출 큐 대상 유형                  |텍스트                     |***호출 리디렉션 대상 유형-가능한 값:***<br><br>§ ApplicationEndpoint<br>§ 사서함<br>§ 기타<br>§ 사용자 |
|호출 큐 대상 형식 범례           |텍스트                     |통화 큐 대상 유형에 따라 범례 항목 설정                        |
|호출 유형<sup>1</sup>                   |텍스트                     |호출 유형-가능한 값:<br><br>§ 외부<br>§ 내부             |
|CQ 이름                                 |텍스트                     |통화 큐에 연결된 리소스 계정의 이름<br><br>전체 리소스 계정 이름이 **cq_test@microsoft.com** 경우 이 값은 **cq_test** |
|CQ 시간                                 |정수             |통화 큐 호출 시작 시간                                                 |
|날짜                                    |날짜/시간                |통화 큐 호출 시작 날짜 및 시간(시간)                                 | 
|DateTimeCQName                          |텍스트                     |fCallQueueFinalStateAction에서 필터링하기 위한 고유 키                     |
|PSTN 연결 유형                  |텍스트                     |호출 유형-가능한 값:<br><br>§ ExternalCall<br>§ InternalCall     |
|PSTN 총 시간(분)                      |정수             |요약: 합계<br>PSTN 호출의 총 시간(분) 사용량                       |
|호출 수의 합계(측정값)             |정수             |호출 수와 같지만 호출이 없는 경우 0이 됩니다.                          |
|TotalCallCount(측정값)                |정수             |요약: 합계<br>호출 수                                                |


#### <a name="fcallqueuefinalstateaction--cqd-fields-description"></a>fCallQueueFinalStateAction CQD 필드 설명

|이름                                    |데이터 형식                |설명                                        |
|:---------------------------------------|:------------------------|:--------------------------------------------------|
|평균 호출 기간(초)         |10진수           |요약: 합계<br>중단된 호출의 평균 통화 기간(초)    |
|평균 통화 큐 기간(초)       |10진수           |요약: 합계<br>응답된 통화에 대한 평균 대기 시간(초)           |
|평균 호출 기간(측정값)  |정수             |평균 호출 기간(초)과 같지만 호출이 없는 경우 0이 됩니다.   |
|평균 CQ 기간의 평균(측정값)    |정수             |평균 통화 큐 기간(초)과 같지만 호출이 없는 경우 0이 됩니다. |
|호출 수                              |정수             |요약: 합계<br>호출 수                                         |
|통화 큐 호출 결과                  |텍스트                     |호출 큐 호출 최종 상태-가능한 값:<br><br>§ agent_joined_conference(응답된 전화 회의 모드 통화)<br>§ 거부됨<br>§ 연결이 끊김<br>§ 오류<br>§ 실패<br>§ 유효하지 않음<br>§ 오버플로(오버플로 조건이 충족됨)<br>§ timed_out(시간 제한 조건이 충족됨)<br>§ transferred_to_agent(응답된 전송 모드 호출 {default} |
|호출 큐 호출 결과 범례           |텍스트                     |통화 큐 호출 결과에 따라 범례 항목 설정                      |
|큐 최종 상태 작업 호출           |텍스트                     |큐 최종 작업 호출-가능한 값:<br><br>§ 연결 끊기(timed_out 호출)<br>§ disconnect_with_busy(오버플로 호출)<br>§ failed_to_accept_call<br>§ 앞으로<br>§ shared_voicemail<br>§ 기타<br>§ 음성 메일                |
|CQ 이름                                 |텍스트                     |통화 큐에 연결된 리소스 계정의 이름<br><br>전체 리소스 계정 이름이 **cq_test@microsoft.com** 경우 이 값은 **cq_test** |
|날짜                                    |날짜/시간                |통화 큐 호출 시작 날짜 및 시간(시간)                                 |
|DateTimeCQName                          |텍스트                     |fCallQueueFinalStateAction에서 필터링하기 위한 고유 키                     |
|IsAbandoned                             |True/false               |에이전트가 전화를 받지 않으면 True입니다.                                   |


### <a name="cloud-call-queue-agent-timeline-report"></a>클라우드 호출 큐 에이전트 타임라인 보고서

#### <a name="report-description"></a>보고서 설명

|보고서 섹션                                          |설명                                                  |
|:-------------------------------------------------------|:------------------------------------------------------------|
|에이전트별 호출 수                                |통화 큐 및 에이전트별 통화 배포                |
|에이전트 및 모든 큐별 배포                     |에이전트 및 통화 큐별 통화 배포                |
|테이블(오른쪽 아래)                                    |평균 및 총 통화 기간을 가진 에이전트별 호출 분포 |
|에이전트별 평균 통화 기간(초)                |에이전트별 평균 호출 기간(초)                  |

#### <a name="report-to-cqd-table-and-field-mapping"></a>CQD 테이블 및 필드 매핑에 보고

|보고서 탭            |보고서 테이블 이름           |원본 테이블 이름         |전역 필터       |
|:---------------------|:---------------------------|:-------------------------|:-------------------|
|에이전트 타임라인        |fAgentTimelineAnalytics     |fAgentTimelineAnalytics   |없음                |


|보고서 섹션                                |사용된 필드                         |적용된 필터       |
|:---------------------------------------------|:-------------------------------------|:---------------------|
|날짜 선택기                                 |Datetime                              |없음                  |
|에이전트 사용자 이름 선택기                       |에이전트 이름                            |없음                  |
|큐 리소스 계정 선택기 호출          |CQ 이름                               |없음                  |
|에이전트별 호출 수                      |에이전트 이름<br>호출 수<br>시간      |없음                  |
|에이전트 및 통화 큐별 배포          |에이전트 이름<br>평균 호출 기간(초)<br>호출 수<br>CQ 이름 |없음                      |
|왼쪽 아래                                   |에이전트 이름<br>평균 호출 기간(초)<br>호출 수<br>통화 기간(분)<br>CQ 이름<br>시간<br>MM-DD | 없음 |
|에이전트별 평균 통화 기간(초)      |에이전트 이름<br>평균 호출 기간(초) | 없음 |

#### <a name="fagenttimelineanalytics-cqd-fields-description"></a>fAgentTimelineAnalytics CQD 필드 설명

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

- <sup>1</sup> 자동 전화 교환 및 통화 큐 그래프의 **들어오는 호출 원본** 은 초기 호출 레그 원본이 아닌 최종 통화 레그 원본을 표시합니다. 예를 들어 자동 전화 교환이 외부 전화를 받고 다른 자동 전화 교환 또는 통화 큐로 통화를 전송하는 경우 **들어오는 통화 원본** 이 내부로 보고됩니다.

## <a name="version-3xx-history"></a>버전 3.x.x 기록

자세한 변경 내용은 Teams 자동 전화 교환 & 통화 큐 기록 보고서 - 다운로드한 zip 파일의 변경 Log.docx 참조하세요. 

|버전  |게시된 날짜     |파일                                                           |설명                                         |
|:--------|:------------------|:------------------------------------------------------------------|:---------------------------------------------------|
|3.0.4    |2022년 11월 18일  |Teams 자동 전화 교환 & 통화 큐 기록 보고서 V3.0.4        |오류 수정, 호출 분류 개선, 범례 추가 |
|3.0.3    |2022년 11월 8일   |Teams 자동 전화 교환 & 통화 큐 기록 보고서 V3.0.3        |오류 수정, 설명서 링크 추가, 최적화된 쿼리 |
|3.0.1    |2022년 10월 26일   |Teams 자동 전화 교환 & 통화 큐 기록 보고서 V3.0.1        |테스트 데이터 원본 항목이 제거됨                   |
|3.0.0    |2022년 10월 25일   |Teams 자동 전화 교환 & 통화 큐 기록 보고서 V3.0.0        |새 백 엔드 데이터 원본                             |


## <a name="version-1xx-history"></a>버전 1.xx 기록

자세한 변경 내용은 CQD Teams 자동 전화 교환 & 통화 큐 기록 보고서 - 다운로드한 zip 파일의 변경 Log.docx 참조하세요.                         

|버전  |게시된 날짜     |파일                                                           |설명                                         |
|:--------|:------------------|:------------------------------------------------------------------|:---------------------------------------------------
|1.63     |2022년 8월 24일    |CQD Teams 자동 전화 교환 & 통화 큐 기록 보고서 V1.63.pbit |                                                    |
|1.60     |2022년 7월 22일      |CQD Teams 자동 전화 교환 & 통화 큐 기록 보고서 V1.60.pbit |                                                    |
|1.00     |2020년 11월 5일   |CQ 및 AA 결합 분석 20201105.pbit                         |초기 릴리스                                     |

