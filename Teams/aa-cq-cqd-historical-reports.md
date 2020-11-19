---
title: 자동 전화 교환 & 통화 대기열 히스토리 보고서
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
description: 통화 품질 대시보드 Power BI 보고서를 사용 하 여 자동 전화 교환 및 통화 대기열 기록 데이터를 보는 방법에 대해 알아봅니다.
ms.openlocfilehash: c74e7fed254dda24ec404cbebfa0702498f46f21
ms.sourcegitcommit: 7966991c398cd80f6bd0bb21e57a6b2a97c09ea9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/18/2020
ms.locfileid: "49130409"
---
# <a name="auto-attendant--call-queue-historical-report"></a>자동 전화 교환 & 통화 대기열 히스토리 보고서

CQD 팀 자동 전화 교환 & 통화 대기열 히스토리 보고서 Power BI 서식 파일에서는 다음과 같은 세 가지 보고서를 제공 합니다.

- 자동 전화 교환-자동 전화 교환으로 들어오는 통화에 대 한 분석을 표시 합니다.
- 통화 대기열 – 통화 대기열로 들어오는 통화에 대 한 분석을 표시 합니다.
- 에이전트 시간 표시 막대-통화 대기열 호출에서 활성 상태인 에이전트의 시간 표시 막대 보기를 표시 합니다.

이러한 보고서는 [통화 품질 대시보드](CQD-Power-BI-query-templates.md) 데이터 저장소의 데이터를 사용 하 고 조직이 자동 전화 교환 및 통화 대기열에서 처리 되는 호출 수에 대 한 보고를 허용 하 고 통화 대기열에는 에이전트 성능이 적용 됩니다.

## <a name="what-are-the-requirements"></a>요구 사항은 무엇 인가요? 

Power BI Desktop이 설치 되어 있어야 합니다. [Microsoft Windows 스토어](https://aka.ms/pbidesktopstore)에서 설치할 수 있습니다.

무료 버전의 Power BI 데스크톱을 사용할 수 있습니다. 호환 되는 최소 버전은 2.85.681.0입니다 (2020 년 9 월).

## <a name="permissions-to-access-the-cqd-pipeline"></a>CQD 파이프라인에 대 한 액세스 권한

AA & CQ 분석 기록 보고서를 보는 데 사용 하는 계정에는 CQD 데이터 파이프라인에 액세스할 수 있는 권한이 있어야 합니다. 자세한 내용은 [Cqd 액세스 역할](https://docs.microsoft.com/microsoftteams/turning-on-and-using-call-quality-dashboard#assign-roles-for-accessing-cqd) 을 참조 하세요.

## <a name="installation"></a>설치용 

다음 단계에서는 컴퓨터에 Power BI Desktop이 이미 설치 되어 있고 사용자 계정에 CQD 데이터 파이프라인에 액세스 하는 데 필요한 권한이 있다고 가정 합니다.

다음 단계를 수행 하세요.

- [Cqd POWER BI 쿼리 서식 파일](https://www.microsoft.com/download/details.aspx?id=102291) 을 다운로드 하 고 컴퓨터의 디렉터리에 zip 파일을 저장 합니다.

- Zip 파일을 두 번 클릭 하 여 엽니다.

- "CQ 및 AA 총 분석 20201105. pbit" 서식 파일을 두 번 클릭 하 고 Power BI Desktop을 실행 해야 합니다.

- CQD 데이터 파이프라인 영역을 선택 하 라는 메시지가 표시 됩니다. 테 넌 트가 있는 지역을 선택 합니다.

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-01.png" alt-text="CQD 데이터 파이프라인 영역을 선택 하는 스크린샷":::

 - 비즈니스용 Skype Online PowerShell cmdlet (CsTenant)을 사용 하 여 지역을 볼 수 있습니다. ServiceInstance 출력. 
 이 영역은/like 다음에 표시 됩니다 (예:).

   microsoftcommunicationsonline/noam-4a-지역이 noam 인 s7.
 
 - 보고서가 예제 데이터로 실행 됩니다.
 
 - 자신의 데이터를 보려면 Power BI Desktop의 쿼리 아래에 있는 홈 탭에서 **새로 고침** 을 클릭 하세요.

   :::image type="content" source="media/cqd-teams-aa-cq-historical-report-02.png" alt-text="새로 고침 옵션 선택 스크린샷":::

- 로그인 하 라는 메시지가 표시 됩니다. **조직 계정을** 선택한 다음 **로그인** 을 선택 합니다.

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-03.png" alt-text="로그인을 보여 주는 스크린샷":::

- **연결** 을 선택 하 고 데이터 새로 고침을 시청 합니다.

## <a name="data-latency-and-aa--cq-analytics"></a>데이터 대기 시간 및 AA & CQ 분석

데이터는 30 분 내에 CQD 데이터 파이프라인에서 사용할 수 있습니다.

새 분석 데이터를 보려면 데이터를 새로 고쳐야 합니다. 

## <a name="customization"></a>Customization 

다양 한 시각화에 표시할 필드 추가 또는 제거, 차트 종류 변경 등 보고서의 특정 시각화 요소를 사용자 지정할 수 있습니다.

보고서에 제공 된 것과 다른 데이터 필드를 더 추가할 수 없습니다.

### <a name="change-color-schema"></a>색 스키마 변경 

다음 단계에서는 설치 단계를 이미 완료 했다고 가정 합니다.

다음 단계를 수행 하세요.
- 리본 메뉴에서 **보기 탭** 을 선택 합니다.

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-04.png" alt-text="스크린샷 색 구성표를 변경 하려면 보기 탭을 선택 합니다.":::

- 드롭다운 목록에서 색 스키마를 선택 합니다.

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-05.png" alt-text="다양 한 색 구성표를 보여 주는 스크린샷":::

## <a name="cqd-fields-description"></a>CQD 필드 설명

|이름                                    |데이터 형식                |설명                            |
|:---------------------------------------|:------------------------|:--------------------------------------|
|자동 전화 교환 Id                 |이름                   |AA에 연결 된 자원 계정 이름<br>예: aa_test@microsoft.com|
|자동 전화 교환 체인 시작 시간         |dmtf                 |AA 체인 시작 시간                    |
|자동 전화 교환 디렉터리 검색 방법  |이름                   |마지막 주소록 검색 방법        |
|자동 전화 교환 전송 작업          |이름                   |통화 전송 대상 유형<br>사용할 수 있는 값:<br>§ 알 수 없음-엔터티 형식이 지정 되지 않음<br>§ 사용자-사용자 엔터티<br>§ orgaa-조직 자동 전화 교환 엔터티<br>§ hunt_group-통화 대기열 엔터티<br>§ 응용 프로그램-음성 응용 프로그램 엔터티<br>§ external_pstn-외부 PSTN 엔터티<br>§ shared_voicemail 공유 음성 메일 엔터티|
|자동 전화 교환 전화 걸기 결과              |이름                   |통화 결과:<br>§ 알 수 없음<br>§ transferred_to_user<br>§ transferred_to_operator<br>§ failover_to_operator<br>§ user_terminated<br>§ service_declined<br>§ service_terminated<br>§ failed_to_establish_media<br>§ terminated_no_operator<br>§ terminated_transfer_failed<br>§ terminated_automatic_selection<br>§ transferred_to_shared_voicemail<br>§ oaa_chain_too_long<br>§ oaa_session_too_long|
|자동 전화 교환 통화 흐름                |이름                   |자동 전화 교환 통화의 여러 상태를 캡슐화 합니다.<br>§ abs_search<br>§ call_termination<br>§ call_transfer<br>§ main_menu<br>§ user_selection<br>§ speech_input_confirmation<br>§ first_level_menu<br>§ automatic_menu<br>§ 공지 사항|
|자동 전화 교환이 수반 됨              |부울                  |AA와 통화 관련 여부 표시 됨 |
|자동 전화 교환 발신자 작업 수      |int                      |호출자가 사용한 작업 수         |
|자동 전화 교환 체인 기간 (초)   |int                      |AA의 통화 시간                 |
|통화 대기열 통화 결과                  |문자열                   |통화 대기열 통화 최종 상태<br>사용할 수 있는 값:<br>§ 오류<br>§ 거부 됨<br>§ overflown<br>§ 실패<br>§ timed_out<br>§ transferred_to_agent<br>§ agent_joined_conference|
|통화 대기열 최종 상태 작업           |문자열                   |통화 대기열 최종 작업<br>사용할 수 있는 값:<br>§ 앞으로<br>§ 연결 끊기<br>§ 보이스 메일<br>§ disconnect_with_busy<br>§ shared_voicemail<br>§ failed_to_accept_call<br>§ 기타|
|통화 대기열 Id                     |문자열                   |CQ에 연결 된 자원 계정의 이름<br>예: aa_test@microsoft.com|
|통화 대기열이 컨퍼런스 모드입니다.           |부울                  |CQ에서 컨퍼런스 모드를 사용 하는 경우 1로 설정 |
|통화 대기열 대상 유형                  |문자열                   |통화 리디렉션 대상 형식 필요     |
|통화 대기열 Id에서 전송 됨    |부울                  |이 통화가 전송 된 CQ에 연결 된 자원 계정 이름<br>예: aa_test@microsoft.com|
|통화 대기열 에이전트 옵트인 (Opt In)           |int                      |통화 순간에이 대기열에 사용할 수 있는 에이전트 수 |
|통화 대기열 에이전트 수                  |int                      |통화 순간에이 대기열에 할당 된 에이전트 수 |
|통화 대기열이 포함 된 경우                  |부울                  |통화 대기열이이 통화와 동일 하 게 연결 되는 경우 1 |


### <a name="power-bi-data-model-dimensions"></a>Power BI 데이터 모델 차원

|이름                                    |데이터 형식                |설명                            |
|:---------------------------------------|:------------------------|:--------------------------------------|
|AA 이름                                   |이름                   |자동 전화 교환 ID (리소스 계정 ID) |
|AACallFlow                              |이름                   |자동 전화 교환 통화의 여러 상태를 캡슐화 합니다.<br>§ abs_search<br>§ call_termination<br>§ call_transfer<br>§ main_menu<br>§ user_selection<br>§ speech_input_confirmation<br>§ first_level_menu<br>§ automatic_menu<br>§ 공지 사항 |
|AACallResult                            |이름                   |자동 전화 교환 통화 결과:<br>§ 알 수 없음<br>§ transferred_to_user<br>§ transferred_to_operator<br>§ failover_to_operator<br>§ user_terminated<br>§ service_declined – AA 구성 오류<br>§ service_terminated – 내부 AA 오류<br>§ failed_to_establish_media<br>§ terminated_no_operator<br>§ terminated_transfer_failed<br>§ terminated_automatic_selection<br>§ transferred_to_shared_voicemail<br>§ oaa_chain_too_long<br>§ oaa_session_too_long          |
|AAChainDuration                         |이름                   |자동 전화 교환 통화의 기간 (초)  |
|AACount                                 |이름                   |통화에 포함 된 자동 전화 교환 #         |
|AADirectorySearchMethod                 |이름                   |통화에 사용 되는 검색 방법:<br>§ abs_search_dtmf<br>§ abs_search_extension<br>§ abs_search_name<br>
|AAStartTime                             |이름                   |UTC의 통화 시간      |
|AATransferAction                        |이름                   |통화 수신:<br>§ 알 수 없음-엔터티 형식이 지정 되지 않음<br>§ 사용자-사용자 엔터티<br>§ AA-조직 자동 전화 교환 엔터티<br>§ CQ-통화 대기열 엔터티<br>§ 응용 프로그램-음성 응용 프로그램 엔터티<br>§ external_pstn-외부 PSTN 엔터티<br>§ shared_voicemail 공유 음성 메일 엔터티      |
|PSTNMinutes                             |int                      |총 분 사용                          |
|통화 대기열 통화 결과                  |이름                   |통화 대기열 통화 최종 상태<br>사용할 수 있는 값:<br>§ 오류<br>§ 거부 됨<br>§ overflown<br>§ 실패<br>§ timed_out<br>§ transferred_to_agent<br>§ agent_joined_conference    |
|통화 대기열 Id                     |이름                   |CQ에 연결 된 자원 계정의 이름     |
|통화 대기열 대상 유형                  |이름                   |통화 리디렉션 대상 유형:<br>§ 사용자<br>§ 응용 프로그램 끝점<br>§ 기타     |
|통화 대기열 통화 결과                  |이름                   |통화 대기열 통화 최종 상태<br>사용할 수 있는 값:<br>§ 오류<br>§ 거부 됨<br>§ overflown<br>§ 실패<br>§ timed_out<br>§ transferred_to_agent<br>§ agent_joined_conference           |
|통화 대기열 최종 상태 작업           |이름                   |통화 대기열 최종 작업<br>사용할 수 있는 값:<br>§ 앞으로<br>§ 연결 끊기<br>§ 보이스 메일<br>§ disconnect_with_busy<br>§ shared_voicemail<br>§ failed_to_accept_call<br>§ 기타             |
|에이전트 이름                              |이름                   |사용자 UPN               |


### <a name="measures"></a>기준을

|이름                                      |유형                       |설명                            |
|:---------------------------------------|:------------------------|:--------------------------------------|
|AACallerActionCount                     |int                        |통화 중 AA에서 사용자가 선택한 작업 #  |
|PSTNMinutes                             |int                      |총 분 사용                                  |
|TotalCallCount                          |int                      |통화 횟수                                          |
|평균 통화 시간 (초)         |int                      |통화 대기열 통화의 총 지속 시간 (초)     |


### <a name="power-bi-graph-description-auto-attendant"></a>Power BI 그래프 설명 자동 전화 교환

|이름                                      |설명                            |
|:---------------------------------------|:--------------------------------------|
|수신 통화 원본                    |내부/외부 통화 원본에의 한 통화 배포      |
|디렉터리 검색 방법 합계          |검색 유형별 통화 배포                         |
|발신자 작업                           |통화 수신기 별 통화 배포                       |
|통화 결과                             |최종 통화 상태에의 한 통화 배포                    |
|발신자 작업 수                     |통화 중 사용 되는 번호로 전화 걸기 작업의 분배  |


### <a name="call-queue"></a>통화 대기열

|이름                                      |설명                            |
|:---------------------------------------|:--------------------------------------|
|수신 통화 원본                    |내부/외부 통화 원본에의 한 통화 배포         |
|통화 볼륨                             |통화 대기열에의 한 통화 분배                            |
|발신자 결과                           |통화 결과에의 한 배포                            |
|Timeout/오버플로 통화 총 동작      |착신 전환 되지 않은 통화 (중단 된)의 배포는 호출 결과를 기준으로 합니다.   |
|대상 총 전송/전달          |통화 결과에 의해 착신 전환 된 통화 배포                  |
|중단 통화 비율                   |중단 된 통화 수에 대 한 성공 비율                    |
|평균 세션 길이 (초)        |중단/성공한 통화를 통해 그룹화 된 통화 시간 (초)   |



### <a name="agent-timeline"></a>에이전트 시간 표시 막대

|이름                                                      |설명                            |
|:-------------------------------------------------------|:--------------------------------------|
|상담원 별 # 통화                                        |통화 대기열 및 상담원에의 한 통화 배포                 |
|에이전트 및 통화 전담팀의 총 통화 시간 (초)   |에이전트 및 통화 대기열의 총 통화 시간 (초)     |
|에이전트 이름별 평균 통화 시간 (초)            |에이전트에서 호출 하는 평균 시간 (초)                  |



## <a name="known-issues"></a>알려진 문제점

- 현재 통화 대기열 및 자동 전화 교환은 통화 대기열/자동 전화 교환 이름 대신 리소스 계정의 ID를 표시 합니다.  자동 전화 교환 또는 통화 대기열에 대 한 모든 트래픽을 표시 하려면 자동 전화 교환 또는 통화 대기열에 할당 된 모든 리소스 계정을 선택 해야 합니다.

- 현재, 사용자는 통화 대기열/자동 전화 교환 데이터를 사용 하는 것으로 간주 되는 것 처럼 대시보드에서 28 일간의 기록도 사용할 수 있습니다 데이터 개인 정보 보존 정책에 영향을 받습니다.
