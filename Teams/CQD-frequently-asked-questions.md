---
title: CQD(통화 품질 대시보드) FAQ(질문과 대답)
author: CarolynRowe
ms.author: crowe
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
description: MICROSOFT Teams CQD(통화 품질 대시보드)에 대한 FAQ(질문과 대답)를 읽어보세요.
ms.openlocfilehash: 862967138321b1855f2fdc5b0c8b6ce6caca887f
ms.sourcegitcommit: 0dda332951df3b946097d90a4923eb191fd86b4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/14/2022
ms.locfileid: "66789399"
---
# <a name="call-quality-dashboard-cqd-frequently-asked-questions-faq"></a>CQD(통화 품질 대시보드) FAQ(질문과 대답)

## <a name="frequently-asked-questions"></a>자주 묻는 질문

[하나 이상의 모임 참가자가 환경이 좋지 않은 경우 CQD에서 통화를 "양호"로 표시하는 이유는 무엇인가요?](#why-does-cqd-mark-a-call-as-good-if-one-or-more-meeting-participants-had-a-poor-experience)

[측정값에 대한 호출 및 사용자 수 값의 최대 0.2% 차이를 확인하고 가장 정확한 볼륨을 얻는 방법은 무엇인가요? ](#why-do-i-see-up-to-02-difference-in-call-and-user-count-values-on-measures-and-how-to-get-most-accurate-volumes)

[CQD에서 EUII를 볼 수 없는 이유는 무엇인가요?](#why-cant-i-see-euii-in-cqd)

[사용량 유형 보고서에 CQD를 사용하고 일부 데이터가 불완전하다는 것을 발견하려고 합니다. 왜 그런가요?](#im-trying-to-use-cqd-for-usage-type-reports-and-find-that-some-of-the-data-is-incomplete----why-is-that)

[Teams에 대해서만 필터링했을 때 CQD에서 비즈니스용 Skype 정보가 표시되는 이유는 무엇인가요?](#why-am-i-seeing-skype-for-business-information-in-cqd-when-ive-filtered-for-teams-only)

[더 많은 항목이 있어야 한다는 것을 알고 있는 경우 사용자 지정 보고서에서 최대 10,000개의 행만 반환하는 이유는 무엇인가요?](#why-do-my-custom-reports-only-return-a-maximum-of-10000-rows-when-i-know-there-should-be-more-entries)

[Wi-Fi VPN 연결이 Wi-Fi 대신 유선으로 표시되는 이유는 무엇인가요?](#why-do-wi-fi-vpn-connections-show-as-wired-instead-of-wi-fi)

[Teams에서 정책 기반 녹음/녹화를 설정했는데 이제 피어 투 피어 통화가 회의로 표시되고 있습니다. 무슨 일이 일어났습니까?](#i-turned-on-policy-based-recording-in-teams-and-now-peer-to-peer-calls-are-being-marked-as-conferences----what-happened)

### <a name="why-does-cqd-mark-a-call-as-good-if-one-or-more-meeting-participants-had-a-poor-experience"></a>하나 이상의 모임 참가자가 환경이 좋지 않은 경우 CQD에서 통화를 "양호"로 표시하는 이유는 무엇인가요?

CQD에서 [스트림 분류](stream-classification-in-call-quality-dashboard.md)에 사용하는 규칙을 확인합니다.
 
오디오 스트림의 경우 다섯 개의 분류자(호출 길이에 따라 평균 계산됨)가 모두 "양호한" 매개 변수 내에 있을 수 있습니다. 그렇다고 해서 사용자가 오디오 중퇴, 정적 또는 결함에 기여한 것을 경험하지 못했다는 의미는 아닙니다. 

네트워크 문제인지 확인하려면 세션의 평균 값과 최대 값 사이의 델타를 확인합니다. 최대 값은 세션 중에 검색되고 보고된 최대값입니다.
 
이 상황을 해결하는 방법의 예는 다음과 같습니다. 호출 중에 네트워크 추적을 수행하고 처음 20분 동안 손실된 패킷은 없지만 1.5초의 패킷 간격이 있고 나머지 호출에 적합하다고 가정해 보겠습니다. Wireshark 추적 RTP 분석에서도 평균 <10%(0.1) 패킷 손실이 발생합니다. 최대 패킷 손실이란? 5초 동안 1.5초는 30%(0.3)입니다. 5초 샘플링 기간 내에 발생했나요(샘플링 기간 동안 분할될 수도 있음)?
 
네트워크 메트릭이 평균 및 최대 값에서 양호한 경우 다른 원격 분석 데이터를 확인합니다. 
- CPU 불충분 이벤트 비율을 확인하여 검색된 CPU 리소스가 부족하고 품질이 저하되었는지 확인합니다. 
- 오디오 장치가 스피커와 너무 가까운 마이크 때문에 피드백을 방지하기 위해 반 이중 모드인가요? 
- 디바이스 반 이중 AEC 이벤트 비율을 확인합니다. 허브 또는 도킹 스테이션에 연결할 때 USB 오디오 드롭아웃으로 인해 마이크와 같은 장치에서 결함이 발생했거나 소음 또는 정적이 발생하나요?  
- 디바이스 결함 및 마이크 결함 이벤트 비율을 확인합니다. 디바이스 자체가 제대로 작동되었나요?  
- 캡처 및 렌더링 디바이스가 작동하지 않는 이벤트 비율을 확인합니다.


CQD 원격 분석에서 사용할 수 있는 차원 및 측정값에 대한 자세한 내용은 [통화 품질 대시보드에서 사용할 수 있는 차원 및 측정값을 참조하세요](dimensions-and-measures-available-in-call-quality-dashboard.md).

배경 잡음의 경우 음소거 이벤트 비율을 확인하여 참가자가 음소거된 시간을 확인합니다.
 
CQD에서 자세한 보고서를 만들고 모임 ID를 필터링하여 모임의 모든 사용자 및 스트림을 확인하고 관심 있는 필드를 추가합니다. 문제를 보고하는 사용자가 문제가 있는 사용자가 아닐 수 있습니다. 그들은 단지 경험을보고하고 있습니다.
 
원격 분석이 반드시 문제를 해결하는 것은 아니지만, 의사 결정을 보고 알리는 위치를 더 잘 이해하는 데 도움이 될 수 있습니다. 네트워크, 디바이스, 드라이버 또는 펌웨어 업데이트, 사용량 또는 사용자인가요?

### <a name="why-do-i-see-up-to-02-difference-in-call-and-user-count-values-on-measures-and-how-to-get-most-accurate-volumes"></a>측정값에 대한 호출 및 사용자 수 값의 최대 0.2% 차이를 확인하고 가장 정확한 볼륨을 얻는 방법은 무엇인가요? 

호출 수 및 사용자 수 측정값을 계산하기 위해 데이터 집합의 호출 또는 사용자 식별자에 대해 고유한 countif 작업이 수행됩니다. 큰 데이터 집합에서는 고유 countif 작업에 내재된 최대 0.2% 오류가 있습니다. 가장 정확한 볼륨의 경우 이 고유 countif 작업에 의존하지 않으므로 스트림 개수 측정값을 사용해야 합니다. 데이터 볼륨을 줄이기 위한 필터링은 오류를 줄일 수 있지만 고유한 호출 및 사용자 수에서 이 오류 원본을 제거하지 못할 수 있습니다. 측정 [값이 영향을 받는 통화 품질 대시보드에서 사용할 수 있는 차원 및 측정](dimensions-and-measures-available-in-call-quality-dashboard.md) 값을 참조하세요.

  
### <a name="why-cant-i-see-euii-in-cqd"></a>CQD에서 EUII를 볼 수 없는 이유는 무엇인가요?

이러한 관리자 역할은 CQD에 액세스할 수 있지만 EUII(최종 사용자 식별 정보)를 볼 수는 없습니다.

- Microsoft 365 보고서 읽기 권한자
- Teams 커뮤니케이션 지원 전문가

EUII를 포함하여 CQD에 액세스할 수 있는 역할에 대해 자세히 알아보려면 [CQD에 액세스하기 위한 역할 할당을](turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd) 읽어보세요.

### <a name="im-trying-to-use-cqd-for-usage-type-reports-and-find-that-some-of-the-data-is-incomplete----why-is-that"></a>사용량 유형 보고서에 CQD를 사용하고 일부 데이터가 불완전하다는 것을 발견하려고 합니다. 왜 그런가요?

CQD, Call Analytics, CallRecord Graph API 및 실시간 분석과 같은 통화 품질 관리 도구는 진단 원격 분석을 기반으로 합니다. Teams 통화 품질 관리 도구에 표시되는 정보는 통화에 참여하는 클라이언트로부터 받은 원격 분석 데이터만큼만 완료됩니다. 네트워크 중단, [방화벽 또는 프록시 구성 오류](/microsoft-365/enterprise/urls-and-ip-address-ranges)와 같은 완전한 원격 분석을 수신하지 못할 수 있는 몇 가지 이유가 있습니다. Teams 클라이언트가 서비스에 원격 분석을 제공하는 안정성 및 복원력을 개선하기 위해 지속적으로 노력하고 있습니다.

이 점을 염두에 두고 사용 현황 보고를 위해 통화 품질 관리 도구를 사용할 수 없습니다. 이러한 유형의 보고 시나리오를 수용하거나 사용하도록 설계되지 않았으며, 많은 사용 통계는 이러한 도구 내에서 사용할 수 없으며 사용할 수 없습니다. Teams 관리 Center는 일련의 [사용 현황 보고서를](teams-analytics-and-reports/teams-reporting-reference.md) 제공하며 Teams 클라이언트에서 직접 [모임 참석 보고서를](teams-analytics-and-reports/meeting-attendance-report.md) 사용할 수 있습니다.

### <a name="why-am-i-seeing-skype-for-business-information-in-cqd-when-ive-filtered-for-teams-only"></a>Teams에 대해서만 필터링했을 때 CQD에서 비즈니스용 Skype 정보가 표시되는 이유는 무엇인가요?

CQD 보고서(isTeams = 1)에서만 Teams를 필터링하는 경우 *첫 번째 엔드포인트* 가 Teams인 모든 호출을 필터링합니다. *두 번째 엔드포인트* 가 비즈니스용 Skype 경우 해당 정보가 CQD 보고서에 표시됩니다. 고객의 시나리오에 따라 [CQD는 통화 데이터 커넥터](/skypeforbusiness/hybrid/plan-call-data-connector)를 구성할 때 비즈니스용 Skype 서버 2019 호출을 포함할 수 있습니다. Skype 봇 호출(AA, CVI, VDI), 라이브 이벤트 및 PSTN 호출도 포함될 수 있습니다.

*첫 번째 사용자 에이전트 범주* 및 *두 번째* 사용자 에이전트 범주와 같은 차원을 필터링하여 쿼리에서 비즈니스용 Skype 정보를 제거할 수 있습니다. 첫 번째 및 두 번째 차원을 단일 필터로 결합하는 *사용자 에이전트 범주 쌍* 을 사용할 수도 있습니다.

### <a name="why-do-my-custom-reports-only-return-a-maximum-of-10000-rows-when-i-know-there-should-be-more-entries"></a>더 많은 항목이 있어야 한다는 것을 알고 있는 경우 사용자 지정 보고서에서 최대 10,000개의 행만 반환하는 이유는 무엇인가요?

CQD는 요약된 데이터 쿼리용으로 설계되었으며 데이터 내보내기용으로 설계되지 않았습니다. 가능한 경우 10,000행 제한을 초과하지 않도록 보고서를 재구성하는 것이 좋습니다. 먼저 월, 연도, 날짜, 지역, 국가 등과 같은 더 넓은 하위 카디널리티 차원을 사용하여 KPI를 확인합니다. 여기에서 점점 더 높은 카디널리티 차원으로 드릴다운할 수 있습니다. 기술 지원팀과 Location-Enhanced 보고서는 모두 이 드릴다운 워크플로의 좋은 예를 제공합니다.

### <a name="why-do-wi-fi-vpn-connections-show-as-wired-instead-of-wi-fi"></a>Wi-Fi VPN 연결이 Wi-Fi 대신 유선으로 표시되는 이유는 무엇인가요?

이는 정상적인 동작입니다. VPN 공급업체는 유선 연결처럼 처리되는 가상 이더넷 어댑터를 만들었습니다. 제대로 레이블이 지정되지 않았기 때문에 운영 체제는 Wi-Fi 연결인지 모르고 유선으로 보고합니다.

### <a name="i-turned-on-policy-based-recording-in-teams-and-now-peer-to-peer-calls-are-being-marked-as-conferences----what-happened"></a>Teams에서 정책 기반 녹음/녹화를 설정했는데 이제 피어 투 피어 통화가 회의로 표시되고 있습니다. 무슨 일이 일어났습니까?

이는 Microsoft Teams에서 정책 기반 녹음/녹화를 사용하는 경우 예상되는 동작입니다. 정책 기반 녹음/녹화는 Microsoft Azure에 배포된 Teams 레코더 봇을 사용하여 규정 준수를 위해 모임 콘텐츠를 캡처합니다. 통화 품질 관리에서 "피어 투 피어"는 사용자 간의 상호 작용이 아니라 미디어 트래픽 흐름에 대한 설명입니다. 레코더 봇 자체가 호출의 당사자이기 때문에 호출은 더 이상 피어 투 피어가 아니라 다자간 호출입니다. 다자간 통화는 Microsoft Teams에서 회의로 분류되므로 CQD 및 기타 통화 품질 도구에서 이러한 호출을 볼 때 이와 같이 표시됩니다.

## <a name="related-articles"></a>관련 기사

[Teams의 통화 품질 개선 및 모니터링](monitor-call-quality-qos.md)

[CQD란?](CQD-what-is-call-quality-dashboard.md)

[CQD(통화 품질 대시보드) 설정](turning-on-and-using-call-quality-dashboard.md)

[테넌트 업로드 및 데이터 빌드](CQD-upload-tenant-building-data.md)

[CQD 데이터 및 보고서](CQD-data-and-reports.md)

[CQD를 사용하여 통화 및 모임 품질 관리](quality-of-experience-review-guide.md)

[CQD에서 사용할 수 있는 차원 및 측정값](dimensions-and-measures-available-in-call-quality-dashboard.md)

[CQD의 스트림 분류](stream-classification-in-call-quality-dashboard.md)

[Power BI를 사용하여 CQD 데이터 분석](CQD-Power-BI-query-templates.md)

[Teams 문제 해결](/MicrosoftTeams/troubleshoot/teams)
