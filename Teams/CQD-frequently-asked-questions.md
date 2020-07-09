---
title: 통화 품질 대시보드 (CQD) 자주 묻는 질문 사항 (FAQ)
ms.author: lolaj
author: LolaJacobsen
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
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Reporting
- seo-marvel-apr2020
description: Microsoft 팀 통화 품질 대시보드 (CQD)에 대 한 질문과 대답 (FAQ) 및 답변을 읽으십시오.
ms.openlocfilehash: f33d66d9c8abb465c6680bacbbd2ff200cf930c6
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/09/2020
ms.locfileid: "45086174"
---
# <a name="call-quality-dashboard-cqd-frequently-asked-questions-faq"></a>통화 품질 대시보드 (CQD) 자주 묻는 질문 사항 (FAQ)

## <a name="frequently-asked-questions"></a>자주하는 질문

[하나 이상의 모임 참가자에 게 좋지 않은 경험이 있는 경우 CQD 님이 "좋은" 것으로 표시 되는 이유는 무엇 인가요?](#why-does-cqd-mark-a-call-as-good-if-one-or-more-meeting-participants-had-a-poor-experience)

[측정에 대 한 통화 및 사용자 개수 값이 최대 0.2% 차이를 표시 하는 이유는 무엇 이며, 가장 정확한 볼륨을 얻는 방법은 무엇 인가요?](#why-do-i-see-up-to-02-difference-in-call-and-user-count-values-on-measures-and-how-to-get-most-accurate-volumes)

[CQD v2 보고서 데이터가 CQD v3 보고서 데이터와 다르게 보이는 이유는 무엇 인가요?](#why-does-my-cqd-v2-report-data-look-different-than-the-cqd-v3-report-data)

[비즈니스용 Skype 데이터가 팀의 CQD 데이터와 다른 이유는 무엇 인가요?](#why-is-cqd-data-from-skype-for-business-different-than-cqd-data-from-teams)

[CQD에 EUII이 표시 되지 않는 이유는 무엇 인가요?](#why-cant-i-see-euii-in-cqd)

[팀만 필터링 했을 때 CQD에 비즈니스용 Skype 정보가 표시 되는 이유는 무엇 인가요?](#why-am-i-seeing-skype-for-business-information-in-cqd-when-ive-filtered-for-teams-only)

### <a name="why-does-cqd-mark-a-call-as-good-if-one-or-more-meeting-participants-had-a-poor-experience"></a>하나 이상의 모임 참가자에 게 좋지 않은 경험이 있는 경우 CQD 님이 "좋은" 것으로 표시 되는 이유는 무엇 인가요?

[스트림 분류](stream-classification-in-call-quality-dashboard.md)에 대 한 CQD 사용 규칙을 확인 하세요.
 
오디오 스트림의 경우 통화 길이를 기준으로 평균을 계산 하는 5 개의 분류자는 모두 "우수한" 매개 변수 내에 있을 수 있습니다. 이는 사용자가 오디오 드롭, 정적 또는 결함에 기여 하지 않았음을 의미 하지는 않습니다. 

네트워크 문제 인지 확인 하려면 세션의 평균 값과 최대값 사이의 델타를 확인 합니다. 최대값은 세션 중에 검색 되 고 보고 된 최대 값입니다.
 
이 문제를 해결 하는 방법의 예는 다음과 같습니다. 통화 중에 네트워크 추적을 취하고, 손실 된 패킷이 없기 때문에 패킷 1 개가 1.5 초와 나머지 통화에 좋은 경우를 예로 들어 보겠습니다. 평균은 Wireshark 추적 RTP 분석 에서도 10% (0.1) 패킷 손실로 진행 <됩니다. 최대 패킷 손실에는 어떤 것이 있나요? 5 초 기간의 1.5 초는 30% (0.3)입니다. 5 두 번째 샘플 기간 내에 발생 한 경우 (또는 샘플링 기간 동안 분할 될 수 있음)
 
네트워크 메트릭이 평균 및 최대 값에 적합 한 경우 다른 원격 분석 데이터로 확인 합니다. 
- CPU 불충분 이벤트 비율을 확인 하 여 감지 된 CPU 리소스를 사용할 수 있는지, 그리고 품질이 저하 되었는지 확인해 보세요. 
- 스피커로 가까이 있는 마이크 때문에 피드백을 방지 하기 위해 반이중 모드의 오디오 장치는? 
- Device 반이중 AEC 이벤트 비율을 확인 합니다. 허브 또는 도킹 스테이션에 연결 되었을 때 USB 오디오 낙하 때문에 장치 결함 또는 마이크 결함 소음 또는 정전기가 발생 했습니다.  
- 장치 결함 및 마이크 결함 이벤트 비율을 확인 합니다. 장치 자체가 제대로 작동 했습니까?  
- 캡처를 확인 하 고 작동 하지 않는 이벤트 비율이 장치를 렌더링 합니다.


CQD 원격 분석에서 사용할 수 있는 차원과 측정값에 대 한 자세한 내용은 [통화 품질 대시보드에서 사용할 수 있는 차원과](dimensions-and-measures-available-in-call-quality-dashboard.md)측정값을 참조 하세요.

배경 잡음을 위해 참가자가 음소거 된 시간을 보려면 음소거 이벤트 비율을 확인 하세요.
 
CQD에서 자세한 보고서를 만들고 모임 ID를 필터링 하 여 모임에서 모든 사용자와 스트림을 보고 관심 있는 필드를 추가 합니다. 문제를 보고 하는 사용자가 문제가 발생 한 것이 아닐 수 있습니다. 귀하는 환경을 보고만 하 고 있습니다.
 
원격 분석은 반드시 문제를 해결 하는 것은 아니지만, 의사 결정을 확인 하 고 알리는 위치를 보다 잘 파악 하는 데 도움이 될 수 있습니다. 네트워크, 장치, 드라이버 또는 펌웨어 업데이트, 사용 또는 사용자 인가요?

### <a name="why-do-i-see-up-to-02-difference-in-call-and-user-count-values-on-measures-and-how-to-get-most-accurate-volumes"></a>측정에 대 한 통화 및 사용자 개수 값이 최대 0.2% 차이를 표시 하는 이유는 무엇 이며, 가장 정확한 볼륨을 얻는 방법은 무엇 인가요? 
통화 수 및 사용자 수 측정값을 계산 하려면 데이터 집합의 호출 또는 사용자 식별자에 대해 distinct countif 연산을 수행 합니다. 대규모 데이터 집합에는 distinct countif 연산에 기본적으로 0.2% 오류가 있습니다. 가장 정확한 볼륨에서는 이러한 distinct countif 연산에 의존 하지 않으므로 스트림 개수 측정값을 사용 해야 합니다. 데이터 볼륨을 줄이기 위해 필터링 하면 오류를 줄일 수 있지만, 별도의 통화 및 사용자 수에서이 오류 원인을 제거 하지 못할 수 있습니다. 영향을 받는 측정값에 대 한 [통화 품질 대시보드에서 사용할 수 있는 차원과 측정값](dimensions-and-measures-available-in-call-quality-dashboard.md) 을 참조 하세요.

### <a name="why-does-my-cqd-v2-report-data-look-different-than-the-cqd-v3-report-data"></a>CQD v2 보고서 데이터가 CQD v3 보고서 데이터와 다르게 보이는 이유는 무엇 인가요? 

CQD v2와 v3 간에 데이터 차이점이 표시 되는 경우, 집계 수준이 아닌 ' 사과 대 인 ' 및 좁은 수준에 대 한 데이터 비교가 나 유효성 검사가 수행 되도록 해야 합니다. 예를 들어, MSIT ' 건물 30 ' WiFi 팀 데스크톱 클라이언트 데이터에 대 한 보고서를 모두 필터링 하는 경우 낮은 품질의 백분율이 v2 및 v3에서 동일 해야 합니다.

CQDv2 분류는 "오디오" 모달 인 경우에만 가능 하며,이 분류는 모든 모달 (오디오, 비디오 및 Appsharing)에 대해 발생 하며 해당 하는 각 모달 스트림에 표시 됩니다. 

CQDv2 팀의 경우 모든 형식을 CQDv3에 동일한 사용자 의견을 적용 하 고 팀의 모달에 대 한 의견 기반을 적용 합니다.

CQD V3 포함 
1. 비즈니스용 Skype 서버 2019 통화 
2. Skype 봇 통화: 자동 전화 교환, 통화 대기열, 회의 알림 서비스 
3. 가상 데스크톱 인터페이스를
4. 컨퍼런스 비디오 Interop
3. 라이브 이벤트 게시자 및 발표자 통화 
4. PSTN 통화. 

이러한 Power BI 서식 파일을 사용 하 여 CQD 데이터를 분석 하 고 보고 하는 방법을 알아보려면 [cqd 보고서에 대 한 POWER BI 사용](cqd-power-bi-query-templates.md)을 참조 하세요.


### <a name="why-is-cqd-data-from-skype-for-business-different-than-cqd-data-from-teams"></a>비즈니스용 Skype 데이터가 팀의 CQD 데이터와 다른 이유는 무엇 인가요? 


> [!IMPORTANT]
> 2020 년 7 월 1 일부 터 이전 CQD는 최신 CQD의 데이터에 액세스 합니다. 이전의 CQD 데이터는 더 이상 사용할 수 없으며, 문서 또는 보고서 데이터를 내보낼 수 없습니다.


이전 CQD를 비즈니스용 Skype 레거시 포털 (cqd.lync.com)과 팀 관리 센터 (cqd.teams.microsoft.com)에서 최신 CQD ()와 비교 하려고 하면 데이터가 일치 하지 않는다는 것을 빠르게 확인할 수 있습니다. 최신 CQD는 여러 추가 통화 시나리오에 대 한 보고를 하기 때문입니다. 이전 CQD의 보고서를 계속 사용 하는 경우이 문서를 사용 하 여 [비즈니스용 Skype 서버용 통화 품질 대시보드](https://docs.microsoft.com/skypeforbusiness/management-tools/call-quality-dashboard/call-quality-dashboard)를 통해 해당 보고서를 해석 하는 데 도움이 될 수 있습니다.



다음은 CQD v2 및 CQD 데이터를 비교 하는 특정 필터를 적용 하는 예입니다.

1. 체감 품질 Record 사용 가능 = True

2. 다음 값을 사용 하 여 서버 쌍 필터 추가: 클라이언트: 클라이언트 및 클라이언트: 서버. 대부분의 테 넌 트는 서버 호출을 제외 하는 것을 선호 합니다.

3. 사용자 에이전트 범주에 대 한 필터를 추가 하 고 자동 전화 교환, 통화 대기열, 봇, 방 시스템, MediationServer, 컨퍼런스 알림 서비스, VDI 등을 필터링 합니다.

:::image type="content" source="media/turning-on-and-using-call-quality-dashboard1.png" alt-text="CQD v3에서 특정 필터를 적용 하는 스크린샷":::

:::image type="content" source="media/turning-on-and-using-call-quality-dashboard2.png" alt-text="CQD v2에서 특정 필터를 적용 하는 스크린샷":::

#### <a name="other-expected-differences-between-cqd-v2-and-cqd-v3"></a>CQD v2와 CQD v3 간의 다른 예상 차이점

이전 버전과 최신 CQD 간의 차이점에 대 한 자세한 내용은 2019 년 11 월 5 일에 [고급 통화 품질 대시보드 블로그 소개](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Introducing-the-Advanced-Call-Quality-Dashboard/ba-p/972586) 를 참조 하세요.


> [!IMPORTANT]
> 2020 년 7 월 1 일부 터 이전 CQD는 최신 CQD의 데이터에 액세스 합니다. 이전의 CQD 데이터는 더 이상 사용할 수 없으며, 문서 또는 보고서 데이터를 내보낼 수 없습니다.

집계 또는 요약 수준의 이전 및 최신 CQD 보고서 사이에 더 많은 데이터 차이가 표시 될 수 있습니다. 보다 세부적인 수준에서 데이터를 비교 하는 경우 "사과 투-사과" 비교가 표시 됩니다. 예를 들어 개별 건물에 대 한 데이터를 보고 있는 경우 이전 및 새 CQD 보고서 모두에서 낮은 품질의 백분율이 동일 해야 합니다.

- 기업 유선 연결, Windows 데스크톱 또는 단일 지역 또는 건물과 같은 밀접 한 초점으로 시나리오를 선택 합니다.
- 팀의 MR, TR 또는 MP IP 범위를 확인 합니다. 팀의 범위는 비즈니스용 Skype Online 보다 최신 이며, 방화벽과 관련 된 연결 문제가 발생할 수 있습니다.
- 요약 또는 상위 수준 번호를 비교 하지 않습니다. 이러한 비교를 통해 회사 유선 연결에서 비즈니스용 Skype Online 통화의 대규모 통화 볼륨을 LTE 또는 사설 네트워크의 소규모 팀 통화와 비교할 수 있습니다.
- 위치 편향 및 인구 차이에 대 한 주의: 매우 다양 한 비교 기능을 활용할 수 있습니다.
  - NOAM: APAC
  - 대 중: Goa
  - 유선: wifi
  - 회사 네트워크: 홈 네트워크
  
### <a name="why-cant-i-see-euii-in-cqd"></a>CQD에 EUII이 표시 되지 않는 이유는 무엇 인가요?

이러한 관리자 역할은 CQD에 액세스할 수 있지만, EUII (최종 사용자 식별 가능 정보)는 볼 수 없습니다.
- Microsoft 365 보고서 읽기 프로그램
- 팀 의사 소통 지원 전문가

EUII를 포함 하 여 CQD에 액세스할 수 있는 역할에 대 한 자세한 내용은 [CQD에 액세스 하기 위한 역할 할당](turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd)을 참조 하세요.

### <a name="why-am-i-seeing-skype-for-business-information-in-cqd-when-ive-filtered-for-teams-only"></a>팀만 필터링 했을 때 CQD에 비즈니스용 Skype 정보가 표시 되는 이유는 무엇 인가요?

CQD 보고서 (isTeams = 1) 에서만 팀을 필터링 하는 경우 *첫 번째 끝점이* 팀 인 모든 통화에 대해 필터링 하 고 있는 것입니다. *두 번째 종점이* 비즈니스용 Skype 인 경우 해당 정보는 CQD 보고서에 표시 됩니다.

CQDv3에는 CQDv2에는 없는 새로운 시나리오가 포함 되어 있기 때문에 CQDv2 및 CQDv3에는 항상 다른 총 카운트가 적용 됩니다. 이 때문에 필터 없이 요약 합계 또는 집계 된 모든 번호를 비교 하면 이러한 예상 차이점이 발생할 수 있습니다.  

고객의 시나리오에 따라 CQDv3에는 SFB 2019 온-프레미스 통화 (SFB 2019이 데이터 커넥터와 함께 사용 되는 경우), Skype Bot 통화 (AA, CVI, VDI), Live 이벤트 및 PSTN 통화가 포함 됩니다. 고객에 게 제공 되는 시나리오/기능 이지만 해당 데이터는 CQD V2에 없습니다.

예를 들어, 고객에 게 20만 오디오 스트림을 표시 하 고 CQD V2 요약 보고서에서 5000 오류가 발생 하는 것으로 예상 됩니다. 5500 오류와 30만 오디오 스트림 (2019 온-프레미스 통화, CVI 통화, PSTN 통화 등) 및 CQD V3

예기치 않은 차이점이 있는 경우에는 전체 데이터의 다양 한 분석를 확인 해야 합니다.  의도와 비교 합니다.  사용자 에이전트 범주 쌍으로 데이터를 분리 하는 것이 권장 되는 첫 번째 항목 중 하나입니다.  *첫 번째 제품과* *두 번째 제품은* 훌륭한 슬라이서 이기도 합니다.  


## <a name="related-topics"></a>관련 항목

[팀의 통화 품질 개선 및 모니터링](monitor-call-quality-qos.md)

[CQD 란 무엇 인가요?](CQD-what-is-call-quality-dashboard.md)

[CQD (통화 품질 대시보드) 설정](turning-on-and-using-call-quality-dashboard.md)

[테 넌 트 업로드 및 데이터 빌드](CQD-upload-tenant-building-data.md)

[CQD 데이터 및 보고서](CQD-data-and-reports.md)

[CQD를 사용 하 여 통화 및 모임 품질 관리](quality-of-experience-review-guide.md)

[CQD에서 사용할 수 있는 차원과 측정값](dimensions-and-measures-available-in-call-quality-dashboard.md)

[CQD의 스트림 분류](stream-classification-in-call-quality-dashboard.md)

[Power BI를 사용 하 여 CQD 데이터 분석](CQD-Power-BI-query-templates.md)

[Teams 문제 해결](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)