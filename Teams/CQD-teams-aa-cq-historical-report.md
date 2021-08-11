---
title: CQD Power BI 보고서를 사용하여 큐 기록 자동 전화 교환 & 보기
ms.author: colongma
author: clyvr
manager: roykuntz
ms.reviewer: mikedav, siunies, gageames
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
- seo-marvel-apr2020
description: 통화 품질 대시보드 Power BI 보고서를 사용하여 대기열 기록 데이터를 자동 전화 교환 방법에 대해 자세히 알아보면 됩니다.
ms.openlocfilehash: 844ab5caee23cb504420925c9f13bc261d4d839cce19f7ae557d4637562a963e
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54331090"
---
# <a name="what-are-the-requirements"></a>요구 사항은 무엇입니까? 
설치해야 Power BI Desktop 있습니다. Microsoft Windows [스토어에서 설치할 수 있습니다.](https://aka.ms/pbidesktopstore)

무료 버전의 버전을 사용할 Power BI Desktop. 최소 호환 버전은 2.85.681.0(2020년 9월)입니다.

## <a name="permissions-to-access-the-cqd-pipeline"></a>CQD 파이프라인에 액세스하는 권한
AA & CQ Analytics 기록 보고서를 보는 데 사용하는 계정은 CQD 데이터 파이프라인에 액세스할 수 있는 권한이 필요합니다. 자세한 내용은 [CQD 액세스 역할을](./turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd) 참조하세요.

## <a name="installation"></a>설치 
다음 단계는 컴퓨터에 이미 Power BI Desktop CQD 데이터 파이프라인에 액세스하는 데 필요한 권한이 계정에 있는 것으로 가정합니다.

다음 단계를 수행하세요.
- [CQD](./aa-cq-cqd-historical-reports.md) Teams 자동 전화 교환 & 큐 기록 보고서 템플릿을 다운로드하고 컴퓨터의 디렉터리에 저장합니다.

- 템플릿을 두 번 클릭하고 Power BI Desktop 시작해야 합니다.

- CQD 데이터 파이프라인 지역을 선택하라는 메시지가 표시됩니다. 테넌트가 있는 지역을 선택합니다.

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-01.png" alt-text="관리 센터의 통화 품질 대시보드 단추의 Teams 스크린샷":::

 - 온라인 PS cmdlet(Get-CsTenant)비즈니스용 Skype 지역을 볼 수 있습니다. ServiceInstance 출력입니다. 
 지역은 다음 예제의 /에 표시됩니다. 
 
   지역이 noam인 microsoftcommunicationsonline/noam-4a-s7.
   
 - 보고서는 샘플 데이터로 시작됩니다.
 
 - 사용자 자신의 데이터를 보려면  홈 탭의 쿼리 아래에서 새로 고침을 Power BI Desktop.

   :::image type="content" source="media/cqd-teams-aa-cq-historical-report-02.png" alt-text="관리 센터의 통화 품질 대시보드 단추의 Teams 스크린샷":::

- 그런 다음 로그인하라는 메시지가 표시됩니다. 조직 **계정을 선택한** 다음 로그인 **을 선택합니다.**

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-03.png" alt-text="관리 센터의 통화 품질 대시보드 단추의 Teams 스크린샷":::

- 커넥트  선택하고 데이터 새로 고침을 시청합니다.

## <a name="data-latency-any-aa--cq-analytics"></a>데이터 대기 시간 모든 AA & CQ 분석
데이터는 30분 이내에 CQD 데이터 파이프라인에서 사용할 수 있습니다.

새 분석 데이터를 표시하기 위해 데이터를 새로 고쳐야 합니다. 

## <a name="customization"></a>사용자 지정 
다양한 시각화에 표시될 필드 추가 또는 제거, 차트 유형 변경 등 보고서의 특정 시각화 측면을 사용자 지정할 수 있습니다.

보고서에 제공된 데이터 필드 이외에는 추가 데이터 필드를 추가할 수 없습니다.

### <a name="change-color-schema"></a>색계도 변경 
다음 단계는 설치 단계를 이미 완료했다고 가정합니다.

다음 단계를 수행하세요.
- 리본 **메뉴에서 보기** 탭을 선택합니다.

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-04.png" alt-text="관리 센터의 통화 품질 대시보드 단추의 Teams 스크린샷":::

- 드롭다운 목록에서 색스마를 선택합니다.

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-05.png" alt-text="관리 센터의 통화 품질 대시보드 단추의 Teams 스크린샷":::


## <a name="cqd-fields-description"></a>CQD 필드 설명

|이름                                    |데이터 형식                |설명                            |
|:---------------------------------------|:------------------------|:--------------------------------------|
|자동 전화 교환 ID                 |string                   |AA에 연결된 리소스 계정의 이름<br>예: aa_test@microsoft.com|
|자동 전화 교환 시작 시간         |datetime                 |AA 체인 시작 시간                    |
|자동 전화 교환 디렉터리 검색 방법  |string                   |마지막 주소서 검색 방법        |
|자동 전화 교환 전송 작업          |string                   |통화 전송 대상 유형<br>가능한 값:<br>§ 알 수 없음 - 엔터티 형식이 지정되지 않았습니다.<br>§ 사용자 - 사용자 엔터티<br>§ orgaa - 조직 자동 전화 교환 엔터티<br>§ hunt_group - 큐 엔터티 호출<br>§ 애플리케이션 - 음성 애플리케이션 엔터티<br>§ external_pstn - 외부 PSTN 엔터티<br>§ shared_voicemail - 공유 음성메일 엔터티|
|자동 전화 교환 결과              |string                   |호출 결과:<br>§ 알 수 없음 - 호출이 설정 또는 전송에 실패하고 서비스가 의미 있는 실패 이유를 받지 못했습니다. <br>§ transferred_to_user - 전화 걸기 이름/확장 또는 구성된 메뉴 옵션을 통해 사용자에게 전송된 통화 <br>§ transferred_to_operator - 호출이 구성된 연산자로 전송됩니다(예: AA가 시간 후 연산자로 구성된 경우) <br>§ failover_to_operator - 전송이 실패하거나 세 번의 실패한 후에 이름 인식이 작동하지 않을 때 연산자에 대한 폴백<br>§ user_terminated - 호출이 종료되었습니다. <br>§ service_declined - 서비스에서 호출이 거부되어 서비스가 구성을 페치하지 못하면 자동 전화 교환 수 있습니다. <br>§ service_terminated - 백 엔드 서비스가 호출을 종료했습니다. 대상 전송이 실패하고 운영자가 폴백으로 구성되지 않은 경우 <br>§ failed_to_establish_media - 발신자 및 서비스 간에 미디어 설치가 실패했습니다. <br>§ terminated_no_operator - 세 번의 작업 후에 이름 인식이 실패하고 연산자가 구성되지 않은 경우 <br>§ terminated_transfer_failed - 대상으로 전송이 실패하고 연산자가 구성되지 않습니다. <br>§ terminated_automatic_selection - 시간 중 또는 이후에 작업이 구성되지 않은 경우 호출은 기본적으로 종료됩니다. <br>§ transferred_to_shared_voicemail - 대상으로 구성된 경우 공유 음성함으로 전송된 통화 <br>§ oaa_chain_too_long - 연속적으로 자동 전화 교환 체인이 5개 자동 참석자 초과 시 호출이 종료되어 가능한 호출 루프를 방지합니다. <br>§ oaa_session_too_long - 통화가 허용 가능한 최대 세션 길이를 초과하고 시간 초과 |
|자동 전화 교환 전화 Flow                |string                   |호출의 다른 자동 전화 교환 캡슐화<br>§ abs_search<br>§ call_termination<br>§ call_transfer<br>§ main_menu<br>§ user_selection<br>§ speech_input_confirmation<br>§ first_level_menu<br>§ automatic_menu<br>§ 공지|
|관련 자동 전화 교환              |부울                  |호출에 AA가 관여하는지 표시 |
|자동 전화 교환 작업 수      |int                      |호출자에 의해 사용된 작업 수         |
|자동 전화 교환 기간 초   |int                      |AA에서 호출 기간                 |
|큐 호출 결과 호출                  |문자열                   |통화 큐 호출 최종 상태<br>가능한 값:<br>§ 오류<br>§ 거부<br>§ 오버플로<br>§ 실패<br>§ timed_out<br>§ transferred_to_agent<br>§ agent_joined_conference|
|큐 최종 상태 작업 호출           |문자열                   |큐 최종 작업 호출<br>가능한 값:<br>§ forward<br>§ 연결 끊기<br>§ 음성사서함<br>§ disconnect_with_busy<br>§ shared_voicemail<br>§ failed_to_accept_call<br>§ 기타|
|큐 ID 호출                     |문자열                   |CQ에 연결된 리소스 계정의 이름<br>예: aa_test@microsoft.com|
|통화 큐는 회의 모드입니다.           |부울                  |CQ에서 회의 모드를 사용하도록 설정한 경우 1로 설정 |
|큐 대상 유형 호출                  |문자열                   |예상 통화 리디렉션 대상 유형     |
|호출 큐 ID에서 전송    |부울                  |이 호출이 전송된 CQ에 연결된 리소스 계정의 이름<br>예: aa_test@microsoft.com|
|통화 큐 에이전트 옵트인 카운트           |int                      |통화 시 이 큐에 사용할 수 있는 에이전트 수 |
|큐 에이전트 수 호출                  |int                      |호출 시 이 큐에 할당된 에이전트 수 |
|호출 큐 관련                  |부울                  |호출 큐가 이 호출에 관련되어 있는 경우 1과 같음 |


### <a name="powerbi-data-model-dimensions"></a>PowerBI 데이터 모델 차원

|이름                                    |데이터 형식                |설명                            |
|:---------------------------------------|:------------------------|:--------------------------------------|
|AA 이름                                   |string                   |자동 전화 교환 ID(리소스 계정 ID) |
|AACallFlow                              |string                   |호출의 다른 자동 전화 교환 캡슐화<br>§ abs_search<br>§ call_termination<br>§ call_transfer<br>§ main_menu<br>§ user_selection<br>§ speech_input_confirmation<br>§ first_level_menu<br>§ automatic_menu<br>공지사항 |
|AACallResult                            |string                   |전화 걸기 자동 전화 교환 결과:<br>§ 알 수 없음<br>§ transferred_to_user<br>§ transferred_to_operator<br>§ failover_to_operator<br>§ user_terminated<br>§ service_declined - AA 구성 오류<br>§ service_terminated - 내부 AA 오류<br>§ failed_to_establish_media<br> terminated_no_operator<br>§ terminated_transfer_failed<br>§ terminated_automatic_selection<br>§ transferred_to_shared_voicemail<br>§ oaa_chain_too_long<br>§ oaa_session_too_long          |
|AAChainDuration                         |string                   |호출 자동 전화 교환 시간(초)입니다.  |
|AACount                                 |string                   |# 자동 전화 교환 관련         |
|AADirectorySearchMethod                 |string                   |호출에 사용되는 검색 메서드:<br>§ abs_search_dtmf<br>§ abs_search_extension<br>§ abs_search_name|
|AAStartTime                             |string                   |UTC의 통화 시간                            |
|AATransferAction                        |string                   |호출 수신자:<br>§ 알 수 없음 - 엔터티 형식이 지정되지 않았습니다.<br>§ 사용자 - 사용자 엔터티<br>§ AA - 조직 자동 전화 교환 엔터티<br>§ CQ - 큐 엔터티 호출<br>§ 애플리케이션 - 음성 애플리케이션 엔터티<br>§ external_pstn - 외부 PSTN 엔터티<br>§ shared_voicemail - 공유 음성메일 엔터티      |
|PSTNMinutes                             |int                      |총 분 사용량                          |
|큐 호출 결과 호출                  |string                   |통화 큐 호출 최종 상태<br>가능한 값:<br>§ 오류<br>§ 거부<br>§ 오버플로<br>§ 실패<br> timed_out<br>§ transferred_to_agent<br>§ agent_joined_conference    |
|큐 ID 호출                     |string                   |CQ에 연결된 리소스 계정의 이름     |
|큐 대상 유형 호출                  |string                   |예상 통화 리디렉션 대상 유형:<br>§ 사용자<br>§ 애플리케이션 엔드포인트<br>§ 기타     |
|큐 호출 결과 호출                  |string                   |통화 큐 호출 최종 상태<br>가능한 값:<br>§ 오류<br>§ 거부<br>§ 오버플로<br>§ 실패<br> timed_out<br>§ transferred_to_agent<br>agent_joined_conference           |
|큐 최종 상태 작업 호출           |string                   |큐 최종 작업 호출<br>가능한 값:<br>§ forward<br>§ 연결 끊기<br>§ 음성사서함<br>§ disconnect_with_busy<br>§ shared_voicemail<br>§ failed_to_accept_call<br>§ 기타             |
|에이전트 이름                              |string                   |사용자 UPN               |


### <a name="measures"></a>측정값

|이름                                      |유형                       |설명                            |
|:---------------------------------------|:------------------------|:--------------------------------------|
|AACallerActionCount                     |int                        |호출 중에 AA에서 사용자가 선택한 작업의 #  |
|PSTNMinutes                             |int                      |총 분 사용량                                  |
|TotalCallCount                          |int                      |호출의 #                                          |
|평균 통화 시간(초)         |int                      |호출 큐 호출의 총 기간(초)입니다.     |


### <a name="power-bi-graph-description-auto-attendant"></a>Power BI 그래프 설명 자동 전화 교환

|이름                                      |설명                            |
|:---------------------------------------|:--------------------------------------|
|들어오는 통화 원본                    |내부/외부 호출 원본에 의해 호출 배포      |
|디렉터리 검색 방법 합계          |검색 유형별로 호출 분포                         |
|발신자 작업                           |호출 수신기에서 호출 배포                       |
|호출 결과                             |최종 호출 상태로 호출 배포                    |
|발신자 작업 수                     |통화 중에 사용된 번호로 호출의 분포  |


### <a name="call-queue"></a>큐 호출

|이름                                      |설명                            |
|:---------------------------------------|:--------------------------------------|
|들어오는 통화 원본                    |내부/외부 호출 원본에 의해 호출 배포         |
|통화 볼륨                             |호출 큐에 의해 호출 배포                            |
|호출자 결과                           |호출 결과로 호출 분포                            |
|시간 제한/오버플로 호출 총 작업      |호출 결과로 NOT 전달(중단) 호출 배포   |
|전송/전달 대상 합계          |호출 결과로 전달된 호출 분포                  |
|중단된 호출 비율                   |성공한 콜 수와 중단된 호출 수의 비율                    |
|평균 세션 길이(초)        |중단/성공 호출로 그룹화된 초의 통화 길이   |



### <a name="agent-timeline"></a>에이전트 타임라인

|이름                                                      |설명                            |
|:-------------------------------------------------------|:--------------------------------------|
|# 에이전트 호출                                        |호출 큐 및 에이전트에 의해 호출 배포                 |
|에이전트 및 통화 큐의 총 통화 시간(초)입니다.   |에이전트 및 호출 큐의 총 통화 기간(초)입니다.     |
|에이전트 이름에 따라 평균 호출 기간(초)            |에이전트의 평균 통화 기간(초)입니다.                  |



## <a name="known-issues"></a>알려진 문제
- 현재 통화 큐 및 자동 참석자에는 전화 큐/자동 참석자 이름 대신 리소스 계정 ID가 표시됩니다.  자동 참석자 또는 통화 큐에 대한 모든 트래픽을 표시하려면 자동 참석자 또는 통화 큐에 할당된 모든 리소스 계정을 선택해야 합니다.

- 현재 대시보드에서 28일의 기록만 사용할 수 있습니다. 통화 큐/자동 참석자 데이터는 최종 사용자 식별 정보로 간주되어 데이터 개인 정보 보호 보존 정책이 적용됩니다.
