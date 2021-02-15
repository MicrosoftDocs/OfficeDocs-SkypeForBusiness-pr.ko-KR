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
description: 통화 품질 대시보드 Power BI 보고서를 사용하여 통화 대기열 기록 데이터를 자동 전화 교환 방법에 대해 자세히 배워야 합니다.
ms.openlocfilehash: ee54941150a5ba4ade64d6a54cb066f50df2e0a8
ms.sourcegitcommit: bfada4fd06c5cff12b0eefd3384bb3c10d10787f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/12/2021
ms.locfileid: "50196242"
---
# <a name="auto-attendant--call-queue-historical-report"></a>자동 전화 교환 & 기록 보고서 호출

CQD Teams 자동 전화 교환 & 기록 보고서 Power BI 템플릿은 다음 세 가지 보고서를 제공 합니다.

- 자동 전화 교환 - 자동 전화 회의로 들어오는 통화에 대한 분석을 보여 넣습니다.
- 통화 큐 – 통화 큐로 들어오는 호출에 대한 분석을 보여 주며,
- 에이전트 타임라인 - 호출 큐 호출에서 활성 상태인 에이전트의 타임라인 보기를 보여 줄 수 있습니다.

이러한 보고서는 통화 [](CQD-Power-BI-query-templates.md) 품질 대시보드 데이터 저장소의 데이터를 사용하며 조직에서 자동 전화 회의 및 통화 큐에서 처리되는 통화 수와 통화 큐의 에이전트 성능을 보고할 수 있도록 합니다.

## <a name="what-are-the-requirements"></a>요구 사항은 무엇입니까? 

Power BI Desktop을 설치해야 합니다. Microsoft Windows 스토어에서 설치할 [수 있습니다.](https://aka.ms/pbidesktopstore)

Power BI Desktop의 무료 버전을 사용할 수 있습니다. 호환되는 최소 버전은 2.85.681.0(2020년 9월)입니다.

## <a name="permissions-to-access-the-cqd-pipeline"></a>CQD 파이프라인에 액세스하기 위한 권한

AA & CQ Analytics 기록 보고서를 보는 데 사용하는 계정에는 CQD 데이터 파이프라인에 액세스할 수 있는 권한이 필요합니다. 자세한 내용은 [CQD 액세스 역할을](https://docs.microsoft.com/microsoftteams/turning-on-and-using-call-quality-dashboard#assign-roles-for-accessing-cqd) 참조하세요.

## <a name="installation"></a>설치 

다음 단계에서는 컴퓨터에 Power BI Desktop을 이미 설치하고 계정에 CQD 데이터 파이프라인에 액세스하는 데 필요한 권한이 있는 것으로 가정합니다.

다음 단계를 수행하세요.

- [CQD Power BI](https://www.microsoft.com/download/details.aspx?id=102291) 쿼리 템플릿을 다운로드하고 zip 파일을 컴퓨터의 디렉터리에 저장합니다.

- zip 파일을 두 번 클릭하여 열 수 있습니다.

- "CQ 및 AA 결합 분석 20201105.pbit" 템플릿 파일을 두 번 클릭하면 Power BI Desktop이 실행됩니다.

- CQD 데이터 파이프라인 지역을 선택하라는 메시지가 표시됩니다. 테넌트가 있는 지역을 선택합니다.

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-01.png" alt-text="CQD 데이터 파이프라인 지역을 선택하는 스크린샷":::

 - 비즈니스용 Skype Online PowerShell cmdlet(Get-CsTenant)을 사용하여 지역을 볼 수 있습니다. ServiceInstance 출력입니다. 
 지역은 이 예제와 같이 /다음에 표시됩니다.

   지역이 noam인 microsoftcommunicationsonline/noam-4a-s7.
 
 - 보고서가 샘플 데이터와 함께 실행됩니다.
 
 - 자신의 데이터를 보려면 Power  BI Desktop의 쿼리 아래 홈 탭에서 새로 고침을 클릭합니다.

   :::image type="content" source="media/cqd-teams-aa-cq-historical-report-02.png" alt-text="새로 고침 옵션을 선택하는 스크린샷":::

- 그런 다음 로그인하라는 메시지가 표시될 것입니다. 조직 **계정을 선택한** 다음 **로그인을 선택합니다.**

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-03.png" alt-text="로그인을 보여주는 스크린샷":::

- 연결을 **선택하고** 데이터 새로 고침을 감시합니다.

## <a name="data-latency-and-aa--cq-analytics"></a>데이터 대기 시간 및 AA & CQ 분석

데이터는 30분 내에 CQD 데이터 파이프라인에서 사용할 수 있습니다.

새 분석 데이터를 표시하기 위해 데이터를 새로 고쳐야 합니다. 

## <a name="customization"></a>사용자 지정 

다양한 시각화에 표시될 필드 추가 또는 제거, 차트 종류 변경 등 보고서의 특정 시각화 측면을 사용자 지정할 수 있습니다.

보고서에 제공된 데이터 필드 이외에는 추가 데이터 필드를 추가할 수 없습니다.

### <a name="change-color-schema"></a>색 스위마 변경 

다음 단계에서는 설치 단계를 이미 완료했다고 가정합니다.

다음 단계를 수행하세요.
- 리본 **메뉴에서** 보기 탭을 선택합니다.

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-04.png" alt-text="색 구성표를 변경하는 보기 탭을 선택하는 스크린샷":::

- 드롭다운 목록에서 색표를 선택합니다.

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-05.png" alt-text="다양한 색 구성표를 보여주는 스크린샷":::

## <a name="cqd-fields-description"></a>CQD 필드 설명

|이름                                    |데이터 형식                |설명                            |
|:---------------------------------------|:------------------------|:--------------------------------------|
|자동 전화 교환 ID                 |string                   |AA에 연결된 리소스 계정의 이름<br>예: aa_test@microsoft.com|
|자동 전화 교환 체인 시작 시간         |datetime                 |AA 체인 시작 시간                    |
|자동 전화 교환 디렉터리 검색 방법  |string                   |마지막 주소부 검색 방법        |
|자동 전화 교환 전송 작업          |string                   |통화 전송 대상 유형<br>가능한 값:<br>§ unknown - 엔터티 형식이 지정되지 않았습니다.<br>§ user - 사용자 엔터티<br>§ orgaa - 조직 자동 전화 교환 엔터티<br>§ hunt_group - 큐 엔터티 호출<br>§ 애플리케이션 - 음성 애플리케이션 엔터티<br>§ external_pstn - 외부 PSTN 엔터티<br>§ shared_voicemail - 공유 음성메일 엔터티|
|자동 전화 교환 결과              |string                   |호출 결과:<br>§ 알 수 없음<br>§ transferred_to_user<br>§ transferred_to_operator<br>§ failover_to_operator<br>§ user_terminated<br>§ service_declined<br>§ service_terminated<br>§ failed_to_establish_media<br>§ terminated_no_operator<br>§ terminated_transfer_failed<br>§ terminated_automatic_selection<br>§ transferred_to_shared_voicemail<br>§ oaa_chain_too_long<br>§ oaa_session_too_long|
|자동 전화 교환 호출 흐름                |string                   |자동 전화 교환 호출의 다른 자동 전화 교환 캡슐화<br>§ abs_search<br>§ call_termination<br>§ call_transfer<br>§ main_menu<br>§ user_selection<br>§ speech_input_confirmation<br>§ first_level_menu<br>§ automatic_menu<br>§ 공지|
|관련 자동 전화 교환              |부울                  |AA가 호출에 참여하는 경우 표시 |
|자동 전화 교환 작업 수      |int                      |호출자에 의해 사용된 작업의 수         |
|자동 전화 교환 기간(초)   |int                      |AA의 통화 기간                 |
|호출 큐 호출 결과                  |문자열                   |호출 큐 호출 최종 상태<br>가능한 값:<br>§ 오류<br>§ 거부<br>§ overflown<br>§ 실패<br>§ timed_out<br>§ transferred_to_agent<br>§ agent_joined_conference|
|큐 최종 상태 작업 호출           |문자열                   |호출 큐 최종 작업<br>가능한 값:<br>§ forward<br>§ 연결 끊기<br>§ 음성메일<br>§ disconnect_with_busy<br>§ shared_voicemail<br>§ failed_to_accept_call<br>§ 기타|
|큐 ID 호출                     |문자열                   |CQ에 연결된 리소스 계정의 이름<br>예: aa_test@microsoft.com|
|통화 큐가 전화 회의 모드입니다.           |부울                  |CQ에서 회의 모드를 사용하도록 설정한 경우 1로 설정 |
|호출 큐 대상 유형                  |문자열                   |예상 호출 리디렉션 대상 유형     |
|호출 큐 ID에서 전송    |부울                  |이 호출이 전송된 CQ에 연결된 리소스 계정의 이름<br>예: aa_test@microsoft.com|
|호출 큐 에이전트 옵트인 횟수           |int                      |호출 시 이 큐에 사용할 수 있는 에이전트 수 |
|큐 에이전트 수 호출                  |int                      |호출 시 이 큐에 할당된 에이전트 수 |
|호출 큐가 관련되어 있습니다.                  |부울                  |호출 큐가 이 호출에 관련된 경우 1과 같음 |


### <a name="power-bi-data-model-dimensions"></a>Power BI 데이터 모델 차원

|이름                                    |데이터 형식                |설명                            |
|:---------------------------------------|:------------------------|:--------------------------------------|
|AA 이름                                   |string                   |자동 전화 교환 ID(리소스 계정 ID) |
|AACallFlow                              |string                   |자동 전화 교환 호출의 다른 자동 전화 교환 캡슐화<br>§ abs_search<br>§ call_termination<br>§ call_transfer<br>§ main_menu<br>§ user_selection<br>§ speech_input_confirmation<br>§ first_level_menu<br>§ automatic_menu<br>§ 공지 |
|AACallResult                            |string                   |호출 자동 전화 교환 결과:<br>§ 알 수 없음<br>§ transferred_to_user<br>§ transferred_to_operator<br>§ failover_to_operator<br>§ user_terminated<br>§ service_declined - AA 구성 오류<br>§ service_terminated - 내부 AA 오류<br>§ failed_to_establish_media<br>§ terminated_no_operator<br>§ terminated_transfer_failed<br>§ terminated_automatic_selection<br>§ transferred_to_shared_voicemail<br>§ oaa_chain_too_long<br>§ oaa_session_too_long          |
|AAChainDuration                         |string                   |통화 자동 전화 교환 시간(초)  |
|AACount                                 |string                   |통화에 자동 전화 교환 수         |
|AADirectorySearchMethod                 |string                   |호출에 사용되는 검색 방법:<br>§ abs_search_dtmf<br>§ abs_search_extension<br>§ abs_search_name<br>
|AAStartTime                             |string                   |통화 시간(UTC)      |
|AATransferAction                        |string                   |통화 수신자:<br>§ unknown - 엔터티 형식이 지정되지 않았습니다.<br>§ user - 사용자 엔터티<br>§ AA - 조직 자동 전화 교환 엔터티<br>§ CQ - 큐 엔터티 호출<br>§ 애플리케이션 - 음성 애플리케이션 엔터티<br>§ external_pstn - 외부 PSTN 엔터티<br>§ shared_voicemail - 공유 음성메일 엔터티      |
|PSTNMinutes                             |int                      |총 분 사용량                          |
|호출 큐 호출 결과                  |string                   |호출 큐 호출 최종 상태<br>가능한 값:<br>§ 오류<br>§ 거부<br>§ overflown<br>§ 실패<br>§ timed_out<br>§ transferred_to_agent<br>§ agent_joined_conference    |
|큐 ID 호출                     |string                   |CQ에 연결된 리소스 계정의 이름     |
|호출 큐 대상 유형                  |string                   |예상 호출 리디렉션 대상 유형:<br>§ 사용자<br>§ 애플리케이션 엔드포인트<br>§ 기타     |
|호출 큐 호출 결과                  |string                   |호출 큐 호출 최종 상태<br>가능한 값:<br>§ 오류<br>§ 거부<br>§ overflown<br>§ 실패<br>§ timed_out<br>§ transferred_to_agent<br>§ agent_joined_conference           |
|큐 최종 상태 작업 호출           |string                   |호출 큐 최종 작업<br>가능한 값:<br>§ forward<br>§ 연결 끊기<br>§ 음성메일<br>§ disconnect_with_busy<br>§ shared_voicemail<br>§ failed_to_accept_call<br>§ 기타             |
|에이전트 이름                              |string                   |사용자 UPN               |


### <a name="measures"></a>측정값

|이름                                      |유형                       |설명                            |
|:---------------------------------------|:------------------------|:--------------------------------------|
|AACallerActionCount                     |int                        |호출 중 AA에서 사용자가 선택한 작업 수  |
|PSTNMinutes                             |int                      |총 분 사용량                                  |
|TotalCallCount                          |int                      |통화 수                                          |
|평균 통화 기간(초)         |int                      |호출 큐 호출의 총 기간(초)     |


### <a name="power-bi-graph-description-auto-attendant"></a>Power BI 그래프 설명 자동 전화 교환

|이름                                      |설명                            |
|:---------------------------------------|:--------------------------------------|
|수신 전화 원본                    |내부/외부 통화 원본<sup>1에</sup> 의해 호출 배포|
|디렉터리 검색 방법 합계          |검색 유형별로 통화 분포                         |
|호출자 작업                           |통화 수신자에 의해 통화 분포                       |
|호출 결과                             |최종 통화 상태의 통화 분포                    |
|호출자 작업 수                     |통화 중에 사용되는 번호 매기기 작업으로의 통화 분포  |


### <a name="call-queue"></a>호출 큐

|이름                                      |설명                            |
|:---------------------------------------|:--------------------------------------|
|수신 전화 원본                    |내부/외부 통화 원본<sup>1에</sup> 의해 호출 배포   |
|통화 볼륨                             |호출 큐에 의해 호출 배포                            |
|호출자 결과                           |호출 결과로 통화 분포                            |
|시간 제한/오버플로 호출 총 작업      |호출 결과로 전달되지 않은(중단된) 호출의 배포   |
|전송/전달 대상 합계          |호출 결과로 전달된 호출의 분포                  |
|중단된 호출 비율                   |중단된 호출 수에 대한 성공 비율                    |
|평균 세션 길이(초)        |호출 길이(초)는 중단/성공한 호출로 그룹화됩니다.   |



### <a name="agent-timeline"></a>에이전트 타임라인

|이름                                                      |설명                            |
|:-------------------------------------------------------|:--------------------------------------|
|에이전트에 의해 # 호출                                        |호출 큐 및 에이전트에 의해 호출 배포                 |
|에이전트 및 통화 큐의 총 호출 기간(초)   |에이전트 및 호출 큐의 총 통화 기간(초)     |
|에이전트 이름에 대한 평균 호출 기간(초)            |에이전트의 평균 통화 기간(초)                  |



## <a name="known-issues"></a>알려진 문제

- 통화 큐 및 자동 전화 회의는 통화 큐/자동 전화 요청 이름 대신 리소스 계정의 ID로 표시됩니다.  자동 전화 걸기 또는 통화 큐에 대한 모든 트래픽을 표시하려면 자동 전화 걸기 또는 통화 큐에 할당된 모든 리소스 계정을 선택해야 합니다.

- 통화 큐/자동 전화 연결 데이터는 최종 사용자 식별 정보로 간주되어 데이터 개인 정보 보존 정책의 적용을 28일 동안 대시보드에서 사용할 수 있습니다.

- <sup>1</sup> 자동 전화 **걸기** 및 통화 큐 그래프의 수신 통화 원본은 초기 통화 레그 원본이 아닌 최종 통화 레그 원본을 보여줍니다. 예를 들어 자동 전화 발신자가 외부 전화를 받고 다른 자동 전화 대기열 또는  통화 큐로 통화를 전송하는 경우 들어오는 통화 원본은 내부로 보고됩니다.
