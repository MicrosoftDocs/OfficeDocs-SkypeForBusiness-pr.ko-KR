---
title: Power BI를 사용하여 Microsoft Teams용 CQD 데이터 분석
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: siunies
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
- remotework
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
description: Power BI를 사용하여 Microsoft Teams의 CQD 데이터를 분석합니다.
ms.openlocfilehash: 66ae28125d743c647cd0d18376fb12a2cec7cdfd
ms.sourcegitcommit: 0dda332951df3b946097d90a4923eb191fd86b4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/14/2022
ms.locfileid: "66789843"
---
# <a name="use-power-bi-to-analyze-cqd-data-for-microsoft-teams"></a>Power BI를 사용하여 Microsoft Teams용 CQD 데이터 분석

2020년 1월의 새로운 [기능: CQD용 Power BI 쿼리 템플릿을 다운로드합니다](https://www.microsoft.com/download/details.aspx?id=102291). CQD 데이터를 분석하고 보고하는 데 사용할 수 있는 사용자 지정 가능한 Power BI 템플릿입니다.

Teams의 CQD(통화 품질 대시보드) 보고서의 경우 Power BI를 사용하여 데이터를 쿼리하고 보고하려면 CQD Power BI 템플릿을 다운로드합니다. Power BI에서 템플릿을 열면 CQD 관리자 자격 증명으로 로그인하라는 메시지가 표시됩니다. 이러한 쿼리 템플릿을 사용자 지정하고 Power BI 라이선스 및 CQD 관리자 권한이 있는 조직의 모든 사용자에게 배포할 수 있습니다.

이러한 PBIT 파일을 사용하려면 다운로드에 포함된 *MicrosoftCallQuality.pqx* 파일을 사용하여 [Microsoft CQD용 Power BI 커넥터](CQD-Power-BI-connector.md)[를](https://www.microsoft.com/download/details.aspx?id=102291) 설치해야 합니다. 

Power BI 보고서에 액세스할 수 있는 올바른 [CQD 액세스 역할이](turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd) 있는지 확인합니다. 

|Pbit |설명 |
|:----------|:---------|
|<strong>(신규!)</strong> QER.pbit     |  QER(경험 품질 보고서) 템플릿을 통해 고객은 에스컬레이션하기 전에 Teams 모임 및 통화 환경에 영향을 주는 문제를 사전에 식별할 수 있습니다. 또한 관리자가 에스컬레이션되는 문제에 신속하게 대응하고 "모임 중에 어떤 일이 일어났는가?"라는 질문에 답변할 수 있도록 보고서가 제공됩니다.  이 템플릿은 다음 보고서를 제공합니다.</p><li>검색 – 모임 URL, 회의 ID, 서브넷 또는 UPN을 통해 검색할 수 있습니다.</li><li>모임 상태 세부 정보 – 단일 모임에 대한 자세한 메트릭입니다.</li><li>사용자 상태 세부 정보 - 단일 사용자에 대한 자세한 메트릭입니다.</li><li>Media Health – 전체 테넌트 모임 및 통화 상태에 대한 KHI(키 상태 지표)의 개략적인 개요입니다.</li><li>미디어 설정 – 미디어 설정 실패를 분석합니다.</li><li>미디어 안정성 – 미디어 안정성 문제를 분석합니다.</li><li>오디오/비디오/공유 상태 – 오디오, 비디오 또는 공유 상태에 대한 중간 수준의KHI를 검토합니다.</li><li>오디오/비디오/공유 상태 세부 정보 – 오디오, 비디오 또는 공유 상태에 대한 자세한 메트릭을 검토합니다.</li><li>VPN – VPN이 모임 상태에 미치는 영향을 검토합니다. (예상 또는 매핑된 VPN)</li><li>상위 10개 보고서 – 테넌트에서 문제 영역을 식별합니다.</li><li>Dailies - KHI의 일일 보고서를 검토합니다.</li><li>사용량 – 일반 회의 및 통화 사용.</li><li>사용자 피드백 – 사용자 설문 조사 피드백(내 통화 속도라고도 함)을 검토합니다.</li><li>전송 – UDP를 차단하는 네트워크를 식별합니다.</li><li>디바이스 – 디바이스의 영향을 검토합니다.</li><li>클라이언트 - 클라이언트 중심 메트릭을 검토합니다.</li><li>데이터 빌드 – CQD에서 빌드 데이터 파일을 검토합니다.</li><li>PSTN 상태 및 사용자 세부 정보 – PSTN 기반 호출에 대한 개별 사용자 상태뿐만 아니라 높은 수준의 요약을 제공하는 두 보고서입니다.</li><li>네트워크 메트릭 – 지터, 패킷 손실 및 대기 시간에 대한 원시 네트워크 메트릭 세부 정보를 표시하는 두 보고서입니다.</li>  |
|CQD Teams 자동 전화 교환 & 통화 큐 기록 보고서.pbit     |  이 템플릿은 다음과 같은 세 가지 보고서를 제공합니다.</p><li>자동 전화 교환 - 자동 전화 교환으로 들어오는 통화에 대한 분석을 보여 줍니다.</li><li>통화 큐 - 통화 큐로 들어오는 통화에 대한 분석을 보여 줍니다.</li><li>에이전트 타임라인 - 통화 큐 호출에서 활성 상태인 에이전트의 타임라인 보기를 보여 줍니다.</li><br>자세한 내용은 [자동 전화 교환 & 통화 큐 기록 보고서를 참조하세요](aa-cq-cqd-historical-reports.md). |
|CQD 기술 지원팀 보고서.pbit     |빌드 및 EUII 데이터를 통합하는 이 보고서는 단일 사용자로부터 드릴업하여 해당 사용자에 대한 통화 품질 저하의 업스트림 근본 원인을 찾을 수 있도록 설계되었습니다(예: 사용자가 네트워크 문제가 발생한 건물에 있는 경우). |
|CQD 위치 고급 Report.pbit     | CQD SPD 위치 보고서를 다시 이미징합니다. 빌드 또는 사용자에 의한 추가 드릴스루와 함께 통화 품질, 빌드 WiFi, 안정성 및 내 호출 속도(RMC) 정보를 제공하는 9개의 보고서를 포함합니다. 빌드 데이터를 업로드하여 보고 환경을 최대화해야 합니다. |
|CQD 모바일 디바이스 Report.pbit     | 통화 품질, 안정성 및 내 통화 속도 등 모바일 디바이스 사용자를 위해 특별히 조정된 인사이트를 제공합니다. 모바일 네트워크, WiFi 네트워크 및 모바일 운영 체제 보고서(Android, iOS)를 봅니다. |
|CQD PSTN 직접 라우팅 Report.pbit     |직접 라우팅을 통과하는 PSTN 호출에 대한 인사이트를 제공합니다. 자세한 내용은 [CQD PSTN 직접 라우팅 보고서를 참조](CQD-PSTN-report.md)하세요. |
|CQD 요약 Report.pbit     |더 나은 시각화, 향상된 프레젠테이션, 향상된 정보 밀도 및 롤링 날짜 이러한 보고서를 사용하면 이상값을 쉽게 식별할 수 있습니다. 사용하기 쉬운 대화형 맵을 사용하여 위치별로 통화 품질을 드릴다운합니다. 9개의 새 보고서:</p>- 전체 품질<br>- 전반적인 안정성<br>- 전체 RMC(내 통화 평가)<br>- 회의 품질<br>- P2P 품질<br>- 회의 안정성<br>- P2P 안정성<br>- 컨퍼런스 RMC<br>- P2P RMC         |
|CQD Teams 사용률 보고서.pbit     | 조직의 사용자가 Teams를 사용하는 방법 및 양을 보여줍니다. 빌드 데이터를 업로드하여 보고 환경을 최대화해야 합니다. 자세한 내용은 [CQD Power BI 보고서를 사용하여 Microsoft Teams 사용률을 확인하세요](CQD-teams-utilization-report.md). |
|CQD 사용자 피드백(내 통화 평가) Report.pbit     | 조직에 대한 통화를 지원하는 데 쉽게 사용할 수 있는 방식으로 내 통화 속도 데이터를 표시합니다. 축자를 상호 참조하여 최종 사용자 교육 기회를 식별합니다. |

> [!TIP]
> CQD 데이터에 대한 Power BI 보고서를 설정했으면 채널에 탭으로 추가합니다. 채널에서 선택한 **+** 후 **Power BI** 를 선택한 다음 보고서를 찾습니다. 자세한 내용은 [Teams용 Power BI 탭을 사용하여 보고서 포함을 참조하세요](/power-bi/service-embed-report-microsoft-teams). Power BI 라이선스 및 CQD 관리자 자격 증명을 가진 사용자만 이러한 보고서에 액세스할 수 있습니다.

## <a name="related-topics"></a>관련 주제

[통화 품질 대시보드에서 사용할 수 있는 차원 및 측정값](dimensions-and-measures-available-in-call-quality-dashboard.md)

[통화 품질 대시보드의 분류 간소화](stream-classification-in-call-quality-dashboard.md)

[비즈니스용 Skype 통화 분석 설정](set-up-call-analytics.md)

[통화 분석을 사용하여 통화 품질 저하 문제 해결](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[통화 분석 및 통화 품질 대시보드](./monitor-call-quality-qos.md)
