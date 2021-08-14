---
title: CQD PSTN 직접 라우팅 보고서 사용
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.reviewer: siunies, fan.fan
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
description: CQD(전화 품질 Microsoft Teams) PSTN 직접 라우팅 보고서를 사용하여 전화 통화에서 PSTN 호출을 모니터링하고 Microsoft Teams.
ms.openlocfilehash: 692247e79a951b775bdca0f13811e3480dcb8cfbb0a5e78a8f8f7b4b69f97add
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54351258"
---
# <a name="using-the-cqd-pstn-direct-routing-report"></a>CQD PSTN 직접 라우팅 보고서 사용

2020년 3월에 [CQD에](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)대한 다운로드 가능한 쿼리 Microsoft Teams CQD(통화 품질 대시보드) PSTN 직접 라우팅 보고서가 Power BI 추가되었습니다. 


CQD PSTN 직접 라우팅 보고서(CQD PSTN 직접 라우팅 보고서.pbit)는 PSTN 서비스의 사용 패턴 및 품질을 이해하는 데 도움이 됩니다. 이 보고서를 사용하여 서비스 사용량, SBC(세션 경계 컨트롤러), 전화 통신 서비스, 네트워크 매개 변수 및 네트워크 효과 비율 세부 정보를 모니터링합니다. 이 정보는 호출이 삭제된 이유를 포함하여 문제를 식별하는 데 도움이 될 수 있습니다. 예를 들어 볼륨이 떨어지는 경우 또는 영향을 받는 호출 수 및 그 이유에 대해 볼 수 있습니다.


CQD PSTN 직접 라우팅 보고서에는 다음 네 가지 섹션이 있습니다.

  - [PSTN 개요](#pstn-overview)

  - [서비스 세부 정보](#service-details)

  - [네트워크 효과 비율](#network-effectiveness-ratio)

  - [네트워크 매개 변수](#network-parameters)

## <a name="highlights"></a>주요 특징

1. 통화 유형, SBC, 발신자 및 발신자 국가별로 분석

   CQD PSTN 직접 라우팅 보고서는 지난 7, 30일 또는 180일(6개월) 동안 테넌트의 모든 SBC에 대한 안정성 및 사용 메트릭을 집계합니다. 통화 유형, SBC, 발신자 및 발신자 국가별로 데이터를 분석할 수 있습니다. 특정 SBC 또는 국가에 관심이 있는 경우 선택한 시간 범위에 대한 추세 변화를 식별할 수 있습니다.
   :::image type="content" source="media/CQD-PSTN-report8.png" alt-text="CQD PSTN 직접 라우팅 보고서에서 사용할 수 있는 필터 스크린샷":::
   
2. 추세 추적

    서비스 사용 현황 및 안정성을 이해하려는 경우 추세 분석이 필수적입니다. 시간별 추세는 실시간 인시던트 식별에 도움이 되는 일일 성능에 대해 잘 살펴 봐야 합니다. 매일 추세를 통해 장기적인 관점에서 서비스 상태가 볼 수 있습니다. 적절한 데이터 세분성을 사용하여 두 모드 간에 전환할 수 있는 것이 중요합니다. CQD PSTN 직접 라우팅 보고서는 각 수준에서 성능을 분석할 수 있도록 6개월 추세 개요, 7일 및 30일 일일 추세 및 시간별 추세를 제공합니다.
    :::image type="content" source="media/CQD-PSTN-report9.png" alt-text="CQD PSTN 직접 라우팅 보고서의 추세 그래프 스크린샷":::

3. SBC 또는 사용자 수준으로 드릴스루

   CQD의 많은 데이터 범주에 대해 드릴스루 기능을 구축하여 SBC 또는 사용자 수준에서 사용 또는 안정성 배포를 빠르게 이해할 수 있습니다. 드릴 스루를 사용하면 문제를 신속하게 포인포인트하고 실제 사용자 영향을 이해할 수 있습니다. CQD PSTN 직접 라우팅 보고서는 서비스 세부 정보 및 네트워크 효과 비율 메트릭을 자세히 설명하는 기능을 제공합니다. 관심 있는 데이터 지점을 클릭하여 SBC 또는 사용자 수준 세부 정보를 드릴링합니다.
   :::image type="content" source="media/CQD-PSTN-report10.png" alt-text="데이터 지점에서 드릴스루 기능을 보여주는 스크린샷":::


## <a name="pstn-overview"></a>PSTN 개요

CQD PSTN 직접 라우팅 보고서는 지난 180일 동안 서비스의 전반적인 상태와 관련된 다음 정보를 제공합니다.
![스크린샷: PSTN CQD 보고서](media/CQD-PSTN-report1.png)

예를 들어 SBC를 통해 진행되는 모든 인바운드 호출에 대한 전체 사용 현황 및 상태에 관심이 abc.bca.adatum.biz 국가는 다음과 같습니다.

| **통화** | **설명**                                                                                                                                                 |
| ------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1            | 맨 위에 있는 필터를 사용하여 ByotIn을 호출 유형으로 드릴다운하고 선택할 수 있으며, 세션 abc.bca.contoso.com 컨트롤러로, 미국을 내부 국가로 사용할 수 있습니다. |
| 2            | 지난 180일 동안의 사용량 추세입니다. 서비스 세부 정보 페이지에서 사용 현황 세부 정보를 찾을 수 있습니다.                                                                     |
| 3            | 지난 180일 동안 전화 걸기 지연, 대기 시간, 지터 및 패킷 손실 추세를 게시합니다. 네트워크 매개 변수 페이지에서 자세한 보고서를 찾을 수 있습니다.                           |
| 4            | 지난 180일 동안 동시 통화 및 일일 활성 사용자 추세입니다. 이 차트는 서비스의 최대 볼륨을 이해하는 데 도움이 될 수 있습니다.                            |
| 5            | 지난 180일 동안의 통화 종료 이유가 서비스 품질에 영향을 미쳤습니다. 네트워크 유효 비율(NER) 페이지에서 서비스 상태 세부 정보를 찾을 수 있습니다.                    |

## <a name="service-details"></a>서비스 세부 정보

이 페이지에서는 일별 서비스 사용량 추세 및 지리적으로 사용자 피드백 분석 정보를 제공합니다.

  - **총 시도 호출 –** 성공 및 실패한 호출을 포함하여 해당 시간 범위의 총 시도 호출

  - **총 연결된 통화 -** 이 시간 범위에서 연결된 총 통화

  - **총 분 –** 이 시간 범위의 총 분 사용량

  - **일일 활성 사용자(DAU) –** 해당 날에 하나 이상의 연결된 통화를 한 일별 활성 사용자 수

  - **동시 통화 –** 1분에 최대 동시 활성 호출

  - **사용자 피드백 –** "내 통화 평가" 점수는 사용자가 제공한 것입니다. 3-5는 좋은 호출로 간주됩니다. 1-2는 잘못된 호출로 간주됩니다.

![스크린샷: PSTN CQD 보고서](media/CQD-PSTN-report2.png)

예를 들면 다음과 같습니다.

1.  평균 통화 시간이 02/14/2020에서 0으로 떨어지는 경우 먼저 통화 볼륨이 정상으로 보이는지 확인하고 총 연결 호출과 총 시도 호출 간에 큰 불일치가 있는지 확인할 수 있습니다. 그런 다음 네트워크 효과 비율 페이지로 이동하여 호출 실패 이유에 투자합니다.

2.  사용자 피드백 맵에서 빨간색 반점 증가가 표시될 경우 네트워크 효과 비율 페이지 및 네트워크 매개 변수로 이동하여 문제가 발생하고 MS Service Desk를 사용하여 티켓을 올 수 있습니다.

## <a name="network-effectiveness-ratio"></a>네트워크 효과 비율

이는 전체 상태 대시보드에 나타나는 메트릭과 동일합니다. 시간당 네트워크 효과 비율 및 아래 통화 종료 이유 차트에서 통화 방향(인바운드/아웃바운드)에 대한 영향을 받는 호출 세부 정보를 사용하여 시간당 NER 번호를 확인할 수 있습니다.

  - **NER** - 보낸 전화 수와 받는 사람에게 전달된 호출 수를 측정하여 호출을 배달하는 네트워크의 능력(%)입니다.

  - **SIP 응답 코드**- 3자리 정수 응답 코드에 호출 상태가 표시됩니다.

  - **Microsoft 응답 코드**-Microsoft 구성 요소에서 보낸 응답 코드입니다.

  - **설명** - SIP 응답 코드 및 Microsoft 응답 코드에 해당하는 이유 단계입니다.

  - **영향을 받는 호출** 수 - 선택한 시간 범위 동안 총 호출 수가 영향을 미쳤습니다.

> ![스크린샷: PSTN CQD 보고서](media/CQD-PSTN-report3.png)
> 
예를 들면 다음과 같습니다.

![스크린샷: PSTN CQD 보고서](media/CQD-PSTN-report4.png)

Daily NER에 02/05/2020에 대한 축소가 있는 경우 날짜를 클릭할 수 있으며 다른 차트는 해당 특정 날짜로 확대됩니다.

![스크린샷: PSTN CQD 보고서](media/CQD-PSTN-report5.png)

NER 양호한 시간당 추세 21:00 정도의 디프가 발생합니다. 그런 다음 다시 클릭하여 21시간으로 확대하고 적용된 통화 세부 정보를 확인하여 해당 시간에서 실패한 호출 수와 통화 종료 이유가 무엇인지 확인할 수 있습니다. 문제가 SBC와 관련이 없는 경우 SBC 문제에서 자체 문제 촬영을 시작하거나 Service Desk에 보고할 수 있습니다.

## <a name="network-parameters"></a>네트워크 매개 변수

모든 네트워크 매개 변수는 직접 라우팅 인터페이스에서 세션 테두리 컨트롤러로 측정됩니다. 권장 값에 대한 자세한 [](prepare-network.md)내용은 조직의 네트워크 준비를 Microsoft Teams 참조하고, 고객 에지에서 권장 Microsoft Edge 참조하세요.

  - **Jitter** – RTCP(RTP 제어 프로토콜)를 사용하여 두 엔드포인트 간에 계산된 네트워크 전파 지연 시간의 변동을 밀리초 측정한 것입니다.

  - **패킷 손실** - 도착하지 못한 패킷의 측정값입니다. 두 엔드포인트 간에 계산됩니다.

  - **대기 시간** - (왕복 시간으로도 알려져 있습니다)는 신호가 전송되는 데 걸리는 시간과 해당 신호의 수신을 위해 걸리는 시간입니다. 이 시간 지연은 신호의 두 지점 간의 전파 시간으로 구성됩니다.

> ![스크린샷: PSTN CQD 보고서](media/CQD-PSTN-report6.png)

예를 들면 다음과 같습니다.

특정 날짜(예: 2020/02/14의 대기 시간)에 대한 4개 차트(대기 시간, 지터, 패키지 손실율, 후 다이얼 지연)에 대한 스파이크가 표시될 경우 날짜 지점을 클릭합니다. 아래쪽의 시간당 추세 차트가 새로 고쳐지며 시간당 수가 표시됩니다. SBC를 확인하거나 MS Service Desk를 사용하여 티켓을 인상할 수 있습니다.

![스크린샷: PSTN CQD 보고서](media/CQD-PSTN-report7.png)



## <a name="related-topics"></a>관련 항목

[데이터 Power BI CQD 데이터를 분석하는 데 Microsoft Teams](CQD-PSTN-report.md)

[Teams 문제 해결](/MicrosoftTeams/troubleshoot/teams)