---
title: CQD(품질 대시보드) 자주 묻는 질문(FAQ)
ms.author: serdars
author: SerdarSoysal
manager: serdars
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
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Reporting
- seo-marvel-apr2020
description: 자주 묻는 질문(FAQ) 및 CQD(전화 Microsoft Teams 품질 대시보드)에 대한 답변을 읽습니다.
ms.openlocfilehash: bd36fe70d46a190289749a96fbaadb8f6c176251
ms.sourcegitcommit: 79dfda39db208cf943d0f7b4906883bb9d034281
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/09/2022
ms.locfileid: "62457178"
---
# <a name="call-quality-dashboard-cqd-frequently-asked-questions-faq"></a>CQD(품질 대시보드) 자주 묻는 질문(FAQ)

## <a name="frequently-asked-questions"></a>자주 묻는 질문

[하나 이상의 모임 참가자가 좋지 않은 경우 CQD에서 호출을 "Good"로 표시하는 이유는 무엇입니까?](#why-does-cqd-mark-a-call-as-good-if-one-or-more-meeting-participants-had-a-poor-experience)

[측정값에 대한 통화 및 사용자 수 값에 최대 0.2%의 차이를 표시하는 이유는 무엇일까요? ](#why-do-i-see-up-to-02-difference-in-call-and-user-count-values-on-measures-and-how-to-get-most-accurate-volumes)

[CQD에서 EUII를 볼 수 없는 이유는 무엇입니까?](#why-cant-i-see-euii-in-cqd)

[사용 유형 보고서에 CQD를 사용하려고 시도하고 일부 데이터가 불완전하다는 것을 확인하려고 합니다. 그 이유는 무엇입니까?](#im-trying-to-use-cqd-for-usage-type-reports-and-find-that-some-of-the-data-is-incomplete----why-is-that)

[데이터만 필터링한 비즈니스용 Skype CQD에 Teams 이유는 무엇입니까?](#why-am-i-seeing-skype-for-business-information-in-cqd-when-ive-filtered-for-teams-only)

[내 사용자 지정 보고서는 더 많은 항목이 있는 경우 최대 10,000개 행만 반환하는 이유는 무엇입니까?](#why-do-my-custom-reports-only-return-a-maximum-of-10000-rows-when-i-know-there-should-be-more-entries)

[VPN Wi-Fi Wi-Fi 대신 Wired로 표시되는 이유는 무엇입니까?](#why-do-wi-fi-vpn-connections-show-as-wired-instead-of-wi-fi)

[정책 기반 기록을 Teams 이제 피어 투 피어 통화가 회의로 표시되고 있습니다. 무슨 일이 있었나요?](#i-turned-on-policy-based-recording-in-teams-and-now-peer-to-peer-calls-are-being-marked-as-conferences----what-happened)

### <a name="why-does-cqd-mark-a-call-as-good-if-one-or-more-meeting-participants-had-a-poor-experience"></a>하나 이상의 모임 참가자가 좋지 않은 경우 CQD에서 호출을 "Good"로 표시하는 이유는 무엇입니까?

CQD가 스트림 분류에 사용하는 규칙을 [체크 아웃합니다](stream-classification-in-call-quality-dashboard.md).
 
오디오 스트림의 경우 5개의 분류자(호출 길이에 따라 평균 계산)는 모두 "양호" 매개 변수 내에 있을 수 있습니다. 사용자가 오디오 드롭아웃, 정적 또는 글리치에 기여한 것을 경험하지 않았다는 것을 의미하지는 않습니다. 

네트워크 문제가 있는지 확인하려면 세션의 평균 값과 최대 값 사이의 델타를 확인합니다. 최대 값은 세션 중에 검색되고 보고되는 최대값입니다.
 
이 문제를 해결하는 방법은 다음과 같습니다. 호출하는 동안 네트워크 추적을 취하고 처음 20분 동안 패킷 손실은 없지만 1.5초의 패킷 간격이 있으며 나머지 호출에 대해 좋습니다. Wireshark 추적 RTP 분석에서도 <10%(0.1) 패킷 손실이 평균적으로 감소합니다. 최대 패킷 손실이란? 5초 동안 1.5초는 30%(0.3)입니다. 5초 샘플링 기간 내에 발생했나요(샘플링 기간으로 분할될 수도 있습니다)?
 
네트워크 메트릭이 평균 및 최대 값에서 양호한 경우 다른 원격 분석 데이터를 확인합니다. 
- CPU 부족 이벤트 비율을 확인하여 사용 가능한 검색된 CPU 리소스가 부족하고 품질이 좋지 않은지 확인할 수 있습니다. 
- 오디오 디바이스가 스피커에 너무 가깝기 때문에 피드백을 방지하기 위한 절반 듀플렉스 모드인가요? 
- 디바이스 절반 듀플렉스 AEC 이벤트 비율을 확인합니다. 허브 또는 Docking Station에 연결할 때 USB 오디오 드롭아웃으로 인하여 마이크와 같은 디바이스에서 글리치가 발생하여 소음이나 정적이 발생하나요?  
- 디바이스 글리치 및 마이크 글리치 이벤트 비율을 확인합니다. 디바이스 자체가 제대로 작동하나요?  
- 이벤트 비율이 작동하지 않는 캡처 및 렌더링 디바이스를 확인합니다.


CQD 원격 분석에서 사용할 수 있는 차원 및 측정값에 대한 자세한 내용은 통화 품질 대시보드에서 사용할 수 있는 크기 및 측정값을 [읽어보아야 합니다](dimensions-and-measures-available-in-call-quality-dashboard.md).

배경 소음의 경우 음소거 이벤트 비율을 확인하여 참가자가 음소거된 시간의 길이를 확인할 수 있습니다.
 
CQD에서 자세한 보고서를 만들고 모임 ID를 필터링하여 모임의 모든 사용자 및 스트림을 보고 관심 있는 필드를 추가합니다. 문제를 보고하는 사용자가 문제가 있는 사용자일 수 있습니다. 그들은 단지 환경을 보고하고 있습니다.
 
원격 분석은 반드시 문제를 호출하지는 않지만 결정을 보고 알릴 위치를 더 잘 이해하는 데 도움이 될 수 있습니다. 네트워크, 디바이스, 드라이버 또는 펌웨어 업데이트, 사용량 또는 사용자인가요?

### <a name="why-do-i-see-up-to-02-difference-in-call-and-user-count-values-on-measures-and-how-to-get-most-accurate-volumes"></a>측정값에 대한 통화 및 사용자 수 값에 최대 0.2%의 차이를 표시하는 이유는 무엇일까요? 

호출 수 및 사용자 수 측정값을 계산하기 위해 데이터 집합의 호출 또는 사용자 식별자에 대해 고유한 카운트프 작업이 수행됩니다. 대규모 데이터 집합에는 고유 카운트프 연산이 내재된 최대 0.2%의 오류가 있습니다. 가장 정확한 볼륨의 경우 이 고유한 countif 작업에는 사용되지 않습니다. 스트림 수 측정값을 사용해야 합니다. 데이터 볼륨을 줄이기 위해 필터링하면 오류를 줄일 수 있지만 고유한 호출 및 사용자 수에서 이 오류 원본을 제거하지는 않을 수 있습니다. 측정값이 [영향을 받는 통화](dimensions-and-measures-available-in-call-quality-dashboard.md) 품질 대시보드에서 사용할 수 있는 차원 및 측정값을 참조하세요.

  
### <a name="why-cant-i-see-euii-in-cqd"></a>CQD에서 EUII를 볼 수 없는 이유는 무엇입니까?

이러한 관리자 역할은 CQD에 액세스할 수 있지만 EUII(최종 사용자 식별 정보)를 볼 수 없습니다.

- Microsoft 365 보고서 읽기
- Teams 통신 지원 전문가

EUII를 포함하여 CQD에 액세스할 수 있는 역할에 대한 자세한 내용은 CQD에 액세스하기 위한 역할 [할당을 읽습니다](turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd).

### <a name="im-trying-to-use-cqd-for-usage-type-reports-and-find-that-some-of-the-data-is-incomplete----why-is-that"></a>사용 유형 보고서에 CQD를 사용하려고 시도하고 일부 데이터가 불완전하다는 것을 확인하려고 합니다. 그 이유는 무엇입니까?

CQD, Call Analytics, CallRecord Graph API 및 실시간 분석과 같은 품질 관리 도구는 진단 원격 분석을 기반으로 합니다. 통화 품질 Teams 도구에 표시하는 정보는 통화에 참여하는 클라이언트에서 수신하는 원격 분석 데이터만큼만 완료됩니다. 네트워크 정전 또는 방화벽 또는 프록시 잘못 구성과 같은 완전한 원격 분석이 수신되지 않는 몇 가지 [이유가 있습니다](/microsoft-365/enterprise/urls-and-ip-address-ranges.md). 클라이언트가 서비스에 원격 분석 서비스를 제공하는 안정성 및 Teams 개선하기 위해 지속적으로 작업하고 있습니다.

이를 염두에 두어 통화 품질 관리 도구를 사용하여 사용량 보고를 지원하지 않습니다. 이러한 유형의 보고 시나리오를 수용하거나 사용할 수 있도록 설계되지 않으며, 많은 사용 통계는 이러한 도구 내에서 사용할 수 없습니다. Teams 관리 센터는 일련의 사용 현황 보고서를 제공[하며 모임 참석](teams-analytics-and-reports/teams-reporting-reference.md) 보고서는 [](teams-analytics-and-reports/meeting-attendance-report.md) 클라이언트에서 직접 Teams 있습니다.

### <a name="why-am-i-seeing-skype-for-business-information-in-cqd-when-ive-filtered-for-teams-only"></a>데이터만 필터링한 비즈니스용 Skype CQD에 Teams 이유는 무엇입니까?

CQD Teams(isTeams = 1)에서만 필터링하면 첫 번째 엔드포인트가 Teams. 두 *번째 엔드* 포인트가 비즈니스용 Skype CQD 보고서에 해당 정보가 표시됩니다. CQD는 고객의 시나리오에 따라 데이터 커넥터 호출을 비즈니스용 Skype 서버 2019 호출을 포함할 수 있습니다[](/skypeforbusiness/hybrid/plan-call-data-connector.md). 또한 봇 Skype(AA, CVI, VDI), 라이브 이벤트 및 PSTN 호출도 포함할 수 있습니다.

첫 번째 사용자 에이전트 비즈니스용 Skype 및 두 번째 사용자 에이전트 범주와 같은 차원을 필터링하여 쿼리에서 비즈니스용 Skype 정보를  제거할 *수 있습니다*. 첫 번째 및 두 번째 차원을 단일 필터로 결합하는 사용자 에이전트 *범주* 쌍을 사용할 수도 있습니다.

### <a name="why-do-my-custom-reports-only-return-a-maximum-of-10000-rows-when-i-know-there-should-be-more-entries"></a>내 사용자 지정 보고서는 더 많은 항목이 있는 경우 최대 10,000개 행만 반환하는 이유는 무엇입니까?

CQD는 요약된 데이터 쿼리를 위해 설계됐고 데이터 내보내기용으로 설계되지 않습니다. 가능한 경우 10,000개 행 제한을 초과하지 않도록 보고서를 다시 구조화하는 것이 좋습니다. 먼저 월, 연도, 날짜, 지역, 국가 등 보다 광범위하고 낮은 카디널리티 차원을 사용하여 KPIS를 확인부터 시작합니다. 거기에서 점점 더 높은 카디널리티 차원으로 드릴다운할 수 있습니다. 헬프데스크 및 Location-Enhanced 보고서는 모두 이 드릴다운 워크플로의 좋은 예제를 제공합니다.

### <a name="why-do-wi-fi-vpn-connections-show-as-wired-instead-of-wi-fi"></a>VPN Wi-Fi Wi-Fi 대신 Wired로 표시되는 이유는 무엇입니까?

이는 정상적인 동작입니다. VPN 공급 업체는 유선 연결로 처리되는 가상 이더넷 어댑터를 만들었다. 제대로 레이블이 지정되지 않은 운영 체제는 연결의 Wi-Fi 알지 못하고 유선으로 보고합니다.

### <a name="i-turned-on-policy-based-recording-in-teams-and-now-peer-to-peer-calls-are-being-marked-as-conferences----what-happened"></a>정책 기반 기록을 Teams 이제 피어 투 피어 통화가 회의로 표시되고 있습니다. 무슨 일이 있었나요?

이 동작은 정책 기반 기록을 사용할 때 Microsoft Teams. 정책 기반 기록은 Teams 배포된 Microsoft Azure 기록기 봇을 사용하여 규정 준수를 위해 모임 콘텐츠를 캡처합니다. 통화 품질 관리에서 "피어 투 피어"는 사용자 간의 상호 작용이 아닌 미디어 트래픽 흐름에 대한 설명입니다. Recorder Bot 자체가 호출의 파티이기 때문에 호출은 더 이상 피어 투 피어가 아니라 다자 호출입니다. 다자 통화는 CQD 및 기타 통화 품질 도구에서 이러한 호출을 볼 때 Microsoft Teams 전화 회의로 분류됩니다.

## <a name="related-articles"></a>관련 기사

[통화 품질 향상 및 모니터링 Teams](monitor-call-quality-qos.md)

[CQD란?](CQD-what-is-call-quality-dashboard.md)

[CQD(통화 품질 대시보드) 설정](turning-on-and-using-call-quality-dashboard.md)

[업로드 데이터 구축](CQD-upload-tenant-building-data.md)

[CQD 데이터 및 보고서](CQD-data-and-reports.md)

[CQD를 사용하여 통화 및 모임 품질 관리](quality-of-experience-review-guide.md)

[CQD에서 사용할 수 있는 차원 및 측정값](dimensions-and-measures-available-in-call-quality-dashboard.md)

[CQD의 스트림 분류](stream-classification-in-call-quality-dashboard.md)

[CQD Power BI 분석하는 데 Power BI 사용](CQD-Power-BI-query-templates.md)

[Teams 문제 해결](/MicrosoftTeams/troubleshoot/teams)
