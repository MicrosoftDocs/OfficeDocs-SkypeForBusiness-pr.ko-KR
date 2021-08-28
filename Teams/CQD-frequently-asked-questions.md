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
ms.openlocfilehash: 11b7691596192dbc96cd9deb7a0b64e363f6af4b
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58616304"
---
# <a name="call-quality-dashboard-cqd-frequently-asked-questions-faq"></a>CQD(품질 대시보드) 자주 묻는 질문(FAQ)

## <a name="frequently-asked-questions"></a>자주 묻는 질문

[하나 이상의 모임 참가자가 좋지 않은 경우 CQD에서 호출을 "Good"로 표시하는 이유는 무엇입니까?](#why-does-cqd-mark-a-call-as-good-if-one-or-more-meeting-participants-had-a-poor-experience)

[측정값에 대한 통화 및 사용자 수 값에 최대 0.2%의 차이를 표시하는 이유는 무엇일까요? ](#why-do-i-see-up-to-02-difference-in-call-and-user-count-values-on-measures-and-how-to-get-most-accurate-volumes)

[CQD에서 EUII를 볼 수 없는 이유는 무엇입니까?](#why-cant-i-see-euii-in-cqd)

[데이터만 필터링한 비즈니스용 Skype CQD에 Teams 이유는 무엇입니까?](#why-am-i-seeing-skype-for-business-information-in-cqd-when-ive-filtered-for-teams-only)

[내 사용자 지정 보고서는 더 많은 항목이 있는 경우 최대 10,000개 행만 반환하는 이유는 무엇입니까?](#why-do-my-custom-reports-only-return-a-maximum-of-10000-rows-when-i-know-there-should-be-more-entries)

[VPN Wi-Fi Wi-Fi 대신 Wired로 표시되는 이유는 무엇입니까?](#why-do-wi-fi-vpn-connections-show-as-wired-instead-of-wi-fi)

### <a name="why-does-cqd-mark-a-call-as-good-if-one-or-more-meeting-participants-had-a-poor-experience"></a>하나 이상의 모임 참가자가 좋지 않은 경우 CQD에서 호출을 "Good"로 표시하는 이유는 무엇입니까?

CQD가 스트림 분류에 사용하는 [규칙을 체크 아웃합니다.](stream-classification-in-call-quality-dashboard.md)
 
오디오 스트림의 경우 호출 길이에 따라 평균으로 계산되는 5개의 분류자 중 어느 것이든 "양호" 매개 변수 내에 있을 수 있습니다. 사용자가 오디오 드롭아웃, 정적 또는 글리치에 기여한 것을 경험하지 않았다는 것을 의미하지는 않습니다. 

네트워크 문제가 있는지 확인하려면 세션의 평균 값과 최대 값 사이의 델타를 확인합니다. 최대 값은 세션 중에 검색되고 보고되는 최대값입니다.
 
이 문제를 해결하는 방법은 다음과 같습니다. 호출하는 동안 네트워크 추적을 취하고 처음 20분 동안 패킷 손실은 없지만 1.5초의 패킷 간격이 있으며 나머지 호출에 대해 좋습니다. Wireshark 추적 RTP 분석에서도 <10%(0.1) 패킷 손실이 평균적으로 감소합니다. 최대 패킷 손실이란? 5초 동안 1.5초는 30%(0.3)입니다. 5초 샘플링 기간 내에 발생했나요(샘플링 기간으로 분할될 수도 있습니다)?
 
네트워크 메트릭이 평균 및 최대 값에서 양호한 경우 다른 원격 분석 데이터를 확인합니다. 
- CPU 부족 이벤트 비율을 확인하여 사용 가능한 검색된 CPU 리소스가 부족하고 품질이 좋지 않은지 확인할 수 있습니다. 
- 스피커에 가까운 마이크로 인한 피드백을 방지하기 위해 오디오 디바이스가 반이중 모드인가요? 
- 디바이스 절반 듀플렉스 AEC 이벤트 비율을 확인합니다. 허브 또는 도킹 스테이션에 연결할 때 USB 오디오 드롭아웃으로 인해 디바이스가 글리치 또는 마이크 글리치가 발생하여 소음이나 정적이 발생하나요?  
- 디바이스 글리치 및 마이크 글리치 이벤트 비율을 확인합니다. 디바이스 자체가 제대로 작동하나요?  
- 이벤트 비율이 작동하지 않는 캡처 및 렌더링 디바이스를 확인합니다.


CQD 원격 분석에서 사용할 수 있는 차원 및 측정값에 대한 자세한 내용은 통화 품질 대시보드에서 사용할 수 있는 크기 및 [측정값을 읽어보아야 합니다.](dimensions-and-measures-available-in-call-quality-dashboard.md)

배경 소음의 경우 음소거 이벤트 비율을 확인하여 참가자가 음소거된 시간의 길이를 확인할 수 있습니다.
 
CQD에서 자세한 보고서를 만들고 모임 ID를 필터링하여 모임의 모든 사용자 및 스트림을 보고 관심 있는 필드를 추가합니다. 문제를 보고하는 사용자가 문제가 있는 사용자일 수 있습니다. 그들은 단지 환경을 보고하고 있습니다.
 
원격 분석은 반드시 문제를 호출하지는 않지만 결정을 보고 알릴 위치를 더 잘 이해하는 데 도움이 될 수 있습니다. 네트워크, 디바이스, 드라이버 또는 펌웨어 업데이트, 사용량 또는 사용자인가요?

### <a name="why-do-i-see-up-to-02-difference-in-call-and-user-count-values-on-measures-and-how-to-get-most-accurate-volumes"></a>측정값에 대한 통화 및 사용자 수 값에 최대 0.2%의 차이를 표시하는 이유는 무엇일까요? 

호출 수 및 사용자 수 측정값을 계산하기 위해 데이터 집합의 호출 또는 사용자 식별자에 대해 고유한 카운트프 작업이 수행됩니다. 큰 데이터 집합에서 고유 카운트프 연산에 내재된 최대 0.2%의 오류가 있습니다. 가장 정확한 볼륨의 경우 이 고유한 countif 작업에는 사용되지 않습니다. 데이터 볼륨을 줄이기 위해 필터링하면 오류를 줄일 수 있지만 고유한 호출 및 사용자 수에서 이 오류 원본을 제거하지는 않을 수 있습니다. 측정값이 영향을 미치는 [통화](dimensions-and-measures-available-in-call-quality-dashboard.md) 품질 대시보드에서 사용할 수 있는 크기 및 측정값을 참조하세요.

  
### <a name="why-cant-i-see-euii-in-cqd"></a>CQD에서 EUII를 볼 수 없는 이유는 무엇입니까?

이러한 관리자 역할은 CQD에 액세스할 수 있지만 EUII(최종 사용자 식별 정보)를 볼 수 없습니다.

- Microsoft 365 보고서 읽기
- Teams 통신 지원 전문가

EUII를 포함하여 CQD에 액세스할 수 있는 역할에 대한 자세한 내용은 CQD에 액세스하기 위한 역할 [할당 을 읽어보아야 합니다.](turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd)

### <a name="why-am-i-seeing-skype-for-business-information-in-cqd-when-ive-filtered-for-teams-only"></a>데이터만 필터링한 비즈니스용 Skype CQD에 Teams 이유는 무엇입니까?

CQD Teams(isTeams = 1)에서만 필터링하면 첫 번째 엔드포인트가 Teams.  두 *번째 엔드포인트가* 비즈니스용 Skype CQD 보고서에 해당 정보가 표시됩니다.

CQDv2 및 CQDv3에는 CQDv2가 없는 새 시나리오가 있을 것이기 때문에 항상 총 수가 다릅니다. 이 때문에 필터가 없는 요약 합계 또는 집계된 올업 번호를 비교하면 이러한 예상되는 차이점이 있습니다.  

고객의 시나리오에 따라 CQDv3에는 SFB 2019-프레미스 호출(SFB 2019가 데이터 커넥터와 함께 사용되는 경우), AA, CVI, VDI Skype 봇 호출, 라이브 이벤트 및 PSTN 호출이 포함됩니다. 고객이 사용할 수 있지만 해당 데이터는 CQD V2에 없는 시나리오/기능입니다.

예를 들어 CQD V3에서 5500개 오류(2019 온-프레미스 호출, CVI 호출, PSTN 호출 등)가 있는 300,000개 오디오 스트림과 CQD V2 요약 보고서에서 500,000개 오류가 있는 200,000개 오디오 스트림이 표시될 것으로 예상됩니다.

예기치 않은 차이점이 있는지 확인하려면 전체 데이터의 다양한 분석 데이터를 살펴봐야 합니다.  의도와 비교합니다.  사용자 에이전트 범주 쌍별로 데이터를 구분하는 것이 가장 먼저 권장되는 항목 중 하나입니다.  *첫 번째 제품* 및 *두 번째 제품도* 좋은 슬라이서입니다.  

### <a name="why-do-my-custom-reports-only-return-a-maximum-of-10000-rows-when-i-know-there-should-be-more-entries"></a>내 사용자 지정 보고서는 더 많은 항목이 있는 경우 최대 10,000개 행만 반환하는 이유는 무엇입니까?

CQD는 요약된 데이터 쿼리를 위해 설계됐고 데이터 내보내기용으로 설계되지 않습니다. 가능한 경우 10,000개 행 제한을 초과하지 않도록 보고서를 다시 구조화하는 것이 좋습니다. 월, 연도, 날짜, 지역, 국가 등 더 광범위하고 낮은 카디널리티 차원을 사용하여 KPIS를 확인하여 시작 거기에서 점점 더 높은 카디널리티 차원으로 드릴다운할 수 있습니다. 헬프데스크 및 Location-Enhanced 보고서는 모두 이 드릴다운 워크플로의 좋은 예제를 제공합니다.

### <a name="why-do-wi-fi-vpn-connections-show-as-wired-instead-of-wi-fi"></a>VPN Wi-Fi Wi-Fi 대신 Wired로 표시되는 이유는 무엇입니까?

예상된 동작입니다. VPN 공급 업체는 유선 연결로 처리되는 가상 이더넷 어댑터를 만들었다. 제대로 레이블이 지정되지 않은 운영 체제는 WiFi 연결인지 모르고 유선으로 보고합니다.

## <a name="related-articles"></a>관련 문서

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
