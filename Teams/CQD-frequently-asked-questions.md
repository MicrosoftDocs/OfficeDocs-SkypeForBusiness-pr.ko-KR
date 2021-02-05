---
title: CQD(통화 품질 대시보드) FAQ(질문과 대답)
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
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Reporting
- seo-marvel-apr2020
description: Microsoft Teams 통화 품질 대시보드(CQD)에 대한 FAQ(질문과 대답)를 읽습니다.
ms.openlocfilehash: f622d197900faf632d94d659dae0a5b6eeaee2db
ms.sourcegitcommit: ac73536f790f83a61eeb2eb8c6b71662f7bd26fc
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/05/2021
ms.locfileid: "50110261"
---
# <a name="call-quality-dashboard-cqd-frequently-asked-questions-faq"></a>CQD(통화 품질 대시보드) FAQ(질문과 대답)

## <a name="frequently-asked-questions"></a>자주 묻는 질문

[한명 이상의 모임 참가자가 환경이 좋지 않은 경우 CQD에서 통화를 "양호"로 표시하는 이유는 무엇입니까?](#why-does-cqd-mark-a-call-as-good-if-one-or-more-meeting-participants-had-a-poor-experience)

[측정값에 대해 통화 및 사용자 수 값이 최대 0.2% 차이를 표시하는 이유는 무엇일까요? 가장 정확한 볼륨을 얻을 수 있는 방법 ](#why-do-i-see-up-to-02-difference-in-call-and-user-count-values-on-measures-and-how-to-get-most-accurate-volumes)

[비즈니스용 Skype의 CQD 데이터가 Teams의 CQD 데이터와 다른 이유는 무엇입니까? ](#why-is-cqd-data-from-skype-for-business-different-than-cqd-data-from-teams)

[CQD에서 EUII를 볼 수 없는 이유는 무엇입니까?](#why-cant-i-see-euii-in-cqd)

[Teams로만 필터링한 경우 CQD에 비즈니스용 Skype 정보가 표시되는 이유는 무엇입니까?](#why-am-i-seeing-skype-for-business-information-in-cqd-when-ive-filtered-for-teams-only)

[내 사용자 지정 보고서가 더 많은 항목이 있을 때 최대 10,000개 행만 반환하는 이유는 무엇입니까?](#why-do-my-custom-reports-only-return-a-maximum-of-10000-rows-when-i-know-there-should-be-more-entries)

### <a name="why-does-cqd-mark-a-call-as-good-if-one-or-more-meeting-participants-had-a-poor-experience"></a>한명 이상의 모임 참가자가 환경이 좋지 않은 경우 CQD에서 통화를 "양호"로 표시하는 이유는 무엇입니까?

스트림 분류에 CQD가 사용하는 [규칙을 확인해 1.](stream-classification-in-call-quality-dashboard.md)
 
오디오 스트림의 경우 호출 길이에 따라 평균으로 계산되는 5개 분류자 중 모두 "양호한" 매개 변수 내에 있을 수 있습니다. 사용자가 오디오 드롭아웃, 정적 또는 글리차에 기여한 것을 경험하지 않은 것은 아니며, 

네트워크 문제인지 확인하려면 세션의 평균 값과 최대 값 사이의 델타를 확인합니다. 최대 값은 세션 중에 검색되고 보고되는 최대값입니다.
 
이 문제를 해결하는 방법의 예는 다음과 같습니다. 호출 중에 네트워크 추적을 하고 처음 20분 동안 패킷 손실이 없지만 패킷 간격이 1.5초인 다음 나머지 호출에 대해 양호한 경우를 예를 들어보세요. Wireshark 추적 RTP <패킷 손실이 10%(0.1)로 평균됩니다. 최대 패킷 손실은 무엇입니까? 5초 기간의 1.5초는 30%(0.3)입니다. 5초 샘플링 기간 내에 발생했나요(샘플링 기간 동안 분할될 수 있나요)
 
네트워크 메트릭이 평균 및 최대 값에서 양호한 경우 다른 원격 분석 데이터를 확인합니다. 
- CPU 부족 이벤트 비율을 확인하여 사용 가능한 검색된 CPU 리소스가 부족하고 품질이 좋지 않은지 확인할 수 있습니다. 
- 스피커에 가까운 마이크로 인한 피드백을 방지하기 위해 오디오 장치가 반이중 모드인가요? 
- 디바이스 반이중 AEC 이벤트 비율을 확인합니다. 허브 또는 도킹 스테이션에 연결할 때 USB 오디오 드롭아웃으로 인해 디바이스가 떨어지거나 마이크가 떨어질 때 노이즈 또는 정적이 발생했습니다.  
- 디바이스 글리치 및 마이크의 이벤트 비율을 확인합니다. 디바이스 자체가 제대로 작동하나요?  
- 캡처 및 렌더링 디바이스가 작동하지 않는 이벤트 비율을 확인합니다.


CQD 원격 분석에서 사용할 수 있는 차원 및 측정값에 대한 자세한 내용은 통화 품질 대시보드에서 사용할 수 있는 차원 및 [측정값을 읽습니다.](dimensions-and-measures-available-in-call-quality-dashboard.md)

배경 소음의 경우 음소거 이벤트 비율을 확인하여 참가자가 음소거된 시간의 길이를 봐야 합니다.
 
CQD에서 자세한 보고서를 만들고 모임 ID를 필터링하여 모임의 모든 사용자와 스트림을 살펴보고 관심 있는 필드를 추가합니다. 문제를 보고하는 사용자가 문제가 있는 사용자가 아될 수 있습니다. 단지 환경을 보고하고 있습니다.
 
원격 분석이 반드시 문제를 호출하는 것은 아니며 의사 결정을 보고 알릴 위치를 더 잘 이해하는 데 도움이 될 수 있습니다. 네트워크, 디바이스, 드라이버 또는 펌웨어 업데이트, 사용량 또는 사용자인가요?

### <a name="why-do-i-see-up-to-02-difference-in-call-and-user-count-values-on-measures-and-how-to-get-most-accurate-volumes"></a>측정값에 대해 통화 및 사용자 수 값이 최대 0.2% 차이를 표시하는 이유는 무엇일까요? 가장 정확한 볼륨을 얻을 수 있는 방법 
호출 수 및 사용자 수 측정값을 계산하기 위해 데이터 집합의 호출 또는 사용자 식별자에 대해 고유한 countif 작업이 수행됩니다. 큰 데이터 집합에서는 고유 countif 연산에 내재된 최대 0.2% 오류가 있습니다. 가장 정확한 볼륨의 경우 이 고유 countif 작업에는 사용되지 않는 스트림 수 측정값을 사용해야 합니다. 데이터 볼륨을 줄이기 위해 필터링하면 오류가 감소할 수 있지만 고유한 호출 및 사용자 수에서 이 오류 원본을 제거하지 않을 수 있습니다. [측정값이 영향을](dimensions-and-measures-available-in-call-quality-dashboard.md) 미치는 통화 품질 대시보드에서 사용할 수 있는 차원 및 측정값을 참조하세요.


### <a name="why-is-cqd-data-from-skype-for-business-different-than-cqd-data-from-teams"></a>비즈니스용 Skype의 CQD 데이터가 Teams의 CQD 데이터와 다른 이유는 무엇입니까? 


> [!IMPORTANT]
> 2020년 7월 1일을 기점으로 이전 CQD(CQD.lync.com)는 최신 CQD(CQD)의 데이터를 사용하게 됩니다. Teams.microsoft.com) 이전 CQD 데이터를 더 이상 사용할 수 없습니다. 건물 또는 보고서 데이터를 내보낼 수 없습니다. 비즈니스용 Skype 관리 CQD.lync.com 사용 가능)을 계속 사용할 수 있지만, CQD로 이동해야 CQD.lync.com 수 있습니다. Teams.microsoft.com 아직 수행하지 않은 경우 다시 시작해야 합니다.


비즈니스용 Skype 레거시 포털(cqd.lync.com)의 이전 CQD와 Teams 관리 센터(cqd.teams.microsoft.com)의 최신 CQD 간에 데이터를 비교하려는 경우 데이터가 일치하지 않는 것을 빠르게 알 수 있습니다. 이는 최신 CQD가 많은 추가 호출 시나리오를 보고하기 때문에입니다. 이전 CQD의 보고서를 계속 사용 중이면 비즈니스용 Skype 서버용 통화 품질 대시보드와 같은 보고서를 해석할 수 있도록 이 [문서를 사용하세요.](https://docs.microsoft.com/skypeforbusiness/management-tools/call-quality-dashboard/call-quality-dashboard)


  
### <a name="why-cant-i-see-euii-in-cqd"></a>CQD에서 EUII를 볼 수 없는 이유는 무엇입니까?

이러한 관리자 역할은 CQD에 액세스할 수 있지만 EUII(최종 사용자 식별 정보)를 볼 수 없습니다.
- Microsoft 365 보고서 읽기 읽기
- Teams Communications 지원 전문가

EUII를 포함하여 CQD에 액세스할 수 있는 역할에 대한 자세한 내용은 CQD에 액세스하기 위한 역할 [할당을 읽어 읽습니다.](turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd)

### <a name="why-am-i-seeing-skype-for-business-information-in-cqd-when-ive-filtered-for-teams-only"></a>Teams로만 필터링한 경우 CQD에 비즈니스용 Skype 정보가 표시되는 이유는 무엇입니까?

CQD 보고서(isTeams = 1)에서만 Teams를 필터링하는 경우 첫 번째 엔드포인트가 Teams인 모든 *호출을* 필터링합니다. 두 *번째 엔드포인트가* 비즈니스용 Skype인 경우 해당 정보가 CQD 보고서에 표시 됩니다.

CQDv3에는 CQDv2가 없는 새로운 시나리오가 있을 것이기 때문에 CQDv2 및 CQDv3의 총 수는 항상 다릅니다. 이 때문에 필터가 없는 요약 합계 또는 집계된 모든 숫자를 비교하면 이러한 예상된 차이점이 있습니다.  

고객의 시나리오에 따라 CQDv3에는 SFB 2019의 프레미스 호출(SFB 2019가 데이터 커넥터와 함께 사용되는 경우), Skype 봇 호출(AA, CVI, VDI), 라이브 이벤트 및 PSTN 통화가 포함됩니다. 고객이 사용할 수 있지만 해당 데이터가 CQD V2에 없는 시나리오/기능입니다.

예를 들어 CQD V2 요약 보고서에서 5,000개 오류가 있는 200,000개 오디오 스트림이 고객에게 표시될 것으로 예상됩니다. CQD V3의 5500개 오류(2019년 온-프레미스 호출, CVI 호출, PSTN 호출 등에서 발생)가 있는 300,000개 오디오 스트림과 반대입니다.

예기치 않은 차이가 있는지 확인하려면 전체 데이터의 다양한 분석 데이터를 살펴봐야 합니다.  의도와 비교합니다.  사용자 에이전트 범주 쌍별로 데이터를 구분하는 것이 가장 먼저 권장되는 항목 중 하나입니다.  *첫 번째 제품* 및 *두 번째 제품도* 좋은 슬라이서입니다.  

### <a name="why-do-my-custom-reports-only-return-a-maximum-of-10000-rows-when-i-know-there-should-be-more-entries"></a>내 사용자 지정 보고서가 더 많은 항목이 있을 때 최대 10,000개 행만 반환하는 이유는 무엇입니까?

CQD는 요약된 데이터 쿼리용으로 설계됐고 데이터 내보내기용으로 설계되지 않습니다. 가능한 경우 10,000행 제한을 초과하지 않도록 보고서를 재구성하는 것이 좋습니다. 월, 연도, 날짜, 지역, 국가 등 더 넓은 카디널리티 차원을 사용하여 KP를 확인하여 시작할 수 있습니다. 거기에서 점점 더 높은 카디널리티 차원으로 드릴다운할 수 있습니다. Helpdesk 및 Location-Enhanced 보고서는 모두 이 드릴다운 워크플로의 좋은 예를 제공합니다.

## <a name="related-topics"></a>관련 항목

[Teams의 통화 품질 개선 및 모니터링](monitor-call-quality-qos.md)

[CQD란?](CQD-what-is-call-quality-dashboard.md)

[CQD(통화 품질 대시보드) 설정](turning-on-and-using-call-quality-dashboard.md)

[테넌트 업로드 및 데이터 구축](CQD-upload-tenant-building-data.md)

[CQD 데이터 및 보고서](CQD-data-and-reports.md)

[CQD를 사용하여 통화 및 모임 품질 관리](quality-of-experience-review-guide.md)

[CQD에서 사용할 수 있는 차원 및 측정값](dimensions-and-measures-available-in-call-quality-dashboard.md)

[CQD의 스트림 분류](stream-classification-in-call-quality-dashboard.md)

[Power BI를 사용하여 CQD 데이터 분석](CQD-Power-BI-query-templates.md)

[Teams 문제 해결](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)
